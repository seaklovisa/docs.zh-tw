---
title: 開放式並行存取
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: e380edac-da67-4276-80a5-b64decae4947
ms.openlocfilehash: b1395c3bd81f7f9d2f12d5b1ea2ec4b784f7aab9
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/03/2018
ms.locfileid: "32766224"
---
# <a name="optimistic-concurrency"></a>開放式並行存取
在多使用者環境中，更新資料庫中的資料時，有兩種模型可供使用：開放式並行存取和封閉式並行存取。 <xref:System.Data.DataSet> 物件的設計是要鼓勵使用者在進行長時間的活動 (如遠端處理資料以及與資料進行互動) 時，採用開放式同步存取。  
  
 封閉式同步存取涉及鎖定資料來源的資料列，以免其他使用者修改資料而影響目前的使用者。 在封閉式模型中，當使用者執行某項作業而造成鎖定時，其他使用者在鎖定擁有人解除鎖定前，都無法執行會與鎖定衝突的動作。 這個模型主要應用的環境是經常爭用資料，其鎖定保護資料的成本低於發生並行衝突時復原交易的成本。  
  
 因此在封閉式並行存取模型中，使用者若更新資料列，即會造成鎖定。 使用者尚未完成更新並解除鎖定前，其他人都不能變更這個資料列。 因此，封閉式同步存取最適合應用於鎖定時間短的情況，就像以程式設計的方式處理記錄的情況。 由於使用者與資料互動時，會使記錄被鎖定較長的時間，因此封閉式同步存取方式的彈性並不高。  
  
> [!NOTE]
>  如果您需要在相同作業中更新多個資料列，則建立交易是比使用封閉式鎖定 (Pessimistic Locking) 更具擴充性的選項。  
  
 相較下，採用開放式同步存取的使用者不需要鎖定資料列即可進行讀取。 使用者想要更新資料列時，應用程式必須判斷該資料列自從上次讀取後，是否已由另一位使用者變更。 開放式同步存取一般用於不常爭用資料的環境。 開放式同步存取不需鎖定記錄，因此能改善效能，而鎖定記錄則需要額外的伺服器資源。 此外，為了保持記錄鎖定，必須要持續連接至資料庫伺服器。 由於開放式同步存取模型沒有這種限制，因此可讓數量龐大的用戶端花費更少的時間連接至伺服器。  
  
 開放式同步存取模型中，如果使用者甲已收到來自資料庫的值，而這時使用者乙搶在使用者甲之前修改這個值，便會被視為發生違規。 若要瞭解伺服器解決並行存取違規的方式，最好先從下列範例的說明開始。  
  
 下列表格代表開放式同步存取的範例。  
  
 在下午 1:00 時，User1 從資料庫讀取出資料列，取得下列的值：  
  
 **CustID LastName FirstName**  
  
 101 Smith Bob  
  
|資料行名稱|原始值|目前值|資料庫中的值|  
|-----------------|--------------------|-------------------|-----------------------|  
|CustID|101|101|101|  
|LastName|Smith|Smith|Smith|  
|FirstName|Bob|Bob|Bob|  
  
 在下午 1:01 時，User2 讀取同一資料列。  
  
 在下午 1:03，User2 變更**FirstName**從"Bob"為"Robert"，並更新資料庫。  
  
|資料行名稱|原始值|目前值|資料庫中的值|  
|-----------------|--------------------|-------------------|-----------------------|  
|CustID|101|101|101|  
|LastName|Smith|Smith|Smith|  
|FirstName|Bob|Robert|Bob|  
  
 更新成功，因為更新時資料庫中的值符合 User2 擁有的原始值。  
  
 在下午 1:05 時，User1 將 "Bob" 的名字變更為 "James"，並嘗試更新資料列。  
  
|資料行名稱|原始值|目前值|資料庫中的值|  
|-----------------|--------------------|-------------------|-----------------------|  
|CustID|101|101|101|  
|LastName|Smith|Smith|Smith|  
|FirstName|Bob|James|Robert|  
  
 此時，User1 發生了開放式並行存取違規的情況，因為資料庫中的值 ("Robert") 不再符合 User1 原先預期的原始值 ("Bob")。 並行違規只是讓您瞭解更新失敗。 現在必須決定要用 User1 所做的變更覆寫 User2 的變更，或是取消 User1 做的變更。  
  
## <a name="testing-for-optimistic-concurrency-violations"></a>測試開放式同步存取違規  
 有數種技巧可測試開放式同步存取違規。 其中一種是將時間戳記資料行納入資料表中。 資料庫一般會提供時間戳記功能，可用來辨識記錄上回更新的日期和時間。 採用這項技巧時，資料表定義會包含時間戳記資料行。 只要記錄一更新，時間戳記便會隨之更新以反映目前的日期和時間。 開放式同步存取違規測試中，時間戳記資料行會隨著資料表的任何內容查詢傳回。 嘗試更新時，資料庫中時間戳記的值便會與修改過之資料列中所含的原始時間戳記值比較。 若兩值相符，就會執行更新，並以目前的時間來更新時間戳記資料行的值以反映更新。 若兩值不符，就會發生開放式同步存取違規。  
  
 另一個測試開放式同步存取違規的技巧，是驗證資料列內所有原始資料行的值是否仍然符合資料庫中的值。 例如，請考量下列查詢：  
  
```  
SELECT Col1, Col2, Col3 FROM Table1  
```  
  
 若要更新中的資料列時，是否有開放式並行存取違規測試**Table1**，您可以發出下列 UPDATE 陳述式：  
  
```  
UPDATE Table1 Set Col1 = @NewCol1Value,  
              Set Col2 = @NewCol2Value,  
              Set Col3 = @NewCol3Value  
WHERE Col1 = @OldCol1Value AND  
      Col2 = @OldCol2Value AND  
      Col3 = @OldCol3Value  
```  
  
 只要原始值符合資料庫中的值，便會執行更新。 若值已經修改，更新作業不會修改資料列，因為 WHERE 子句找不到符合的項目。  
  
 請注意，建議您永遠在查詢中傳回唯一的主索引鍵值； 否則，之前的 UPDATE 陳述式可能更新一個以上的資料列，而這可能與您的意圖相違。  
  
 若您資料來源內的資料行允許 Null，則可能必須擴充 WHERE 子句，以檢查區域資料表和資料來源內是否有相符的 Null 參考。 例如，下列 UPDATE 陳述式驗證區域資料列中的 Null 參考仍然與資料來源的 Null 參考相符，或是區域資料列的值仍然與資料來源的值相符。  
  
```  
UPDATE Table1 Set Col1 = @NewVal1  
  WHERE (@OldVal1 IS NULL AND Col1 IS NULL) OR Col1 = @OldVal1  
```  
  
 使用開放式同步存取模型時，您也可以選擇套用較寬鬆的準則。 例如，在 WHERE 子句中僅使用主索引鍵資料行時，不論另一個資料行在上次查詢後是否曾更新，都會覆寫資料。 您也可以只在特定資料行套用 WHERE 子句，以覆寫資料 (除非特定欄位在上次查詢後已經更新)。  
  
### <a name="the-dataadapterrowupdated-event"></a>DataAdapter.RowUpdated 事件  
 **RowUpdated**事件<xref:System.Data.Common.DataAdapter>物件可以搭配上述技術，以提供您的應用程式的開放式並行存取違規的通知。 **RowUpdated**每次嘗試更新之後，就會發生**Modified**中的資料列**資料集**。 如此可讓您加入特殊處理程式碼，包括發生例外狀況時的處理、加入自訂錯誤資訊、加入重試邏輯等等。 <xref:System.Data.Common.RowUpdatedEventArgs>物件會傳回**RecordsAffected**屬性包含資料表中修改之資料列的特定更新命令影響的資料列數目。 藉由設定更新命令以測試開放式同步存取， **RecordsAffected**屬性會如此一來，傳回值為 0 時已經發生開放式並行存取違規，因為已不更新任何記錄。 若發生這種情況，就會發生例外狀況。 **RowUpdated**事件可讓您處理出現在這裡，並避免例外狀況的適當設定**RowUpdatedEventArgs.Status**值，例如**UpdateStatus.SkipCurrentRow**。 如需有關**RowUpdated**事件，請參閱[處理 DataAdapter 事件](../../../../docs/framework/data/adonet/handling-dataadapter-events.md)。  
  
 （選擇性） 您可以設定**DataAdapter.ContinueUpdateOnError**至**true**，然後再呼叫**更新**，並回應錯誤資訊儲存在**RowError**屬性的特定資料列時**更新**完成。 如需詳細資訊，請參閱[資料列錯誤資訊](../../../../docs/framework/data/adonet/dataset-datatable-dataview/row-error-information.md)。  
  
## <a name="optimistic-concurrency-example"></a>開放式同步存取範例  
 以下是簡單的範例，以設定**UpdateCommand**的**DataAdapter**以測試開放式同步存取，然後使用**RowUpdated**來測試事件開放式並行存取違規。 發生開放式並行存取違規時，應用程式會設定**RowError**針對發出更新以反映開放式並行存取違規的資料列。  
  
 請注意，WHERE 子句的 UPDATE 命令傳遞的參數值會對應至**原始**其各自的資料行的值。  
  
```vb  
' Assumes connection is a valid SqlConnection.  
Dim adapter As SqlDataAdapter = New SqlDataAdapter( _  
  "SELECT CustomerID, CompanyName FROM Customers ORDER BY CustomerID", _  
  connection)  
  
' The Update command checks for optimistic concurrency violations  
' in the WHERE clause.  
adapter.UpdateCommand = New SqlCommand("UPDATE Customers " &  
  "(CustomerID, CompanyName) VALUES(@CustomerID, @CompanyName) " & _  
  "WHERE CustomerID = @oldCustomerID AND CompanyName = " &  
  "@oldCompanyName", connection)  
adapter.UpdateCommand.Parameters.Add( _  
  "@CustomerID", SqlDbType.NChar, 5, "CustomerID")  
adapter.UpdateCommand.Parameters.Add( _  
  "@CompanyName", SqlDbType.NVarChar, 30, "CompanyName")  
  
' Pass the original values to the WHERE clause parameters.  
Dim parameter As SqlParameter = dataSet.UpdateCommand.Parameters.Add( _  
  "@oldCustomerID", SqlDbType.NChar, 5, "CustomerID")  
parameter.SourceVersion = DataRowVersion.Original  
parameter = adapter.UpdateCommand.Parameters.Add( _  
  "@oldCompanyName", SqlDbType.NVarChar, 30, "CompanyName")  
parameter.SourceVersion = DataRowVersion.Original  
  
' Add the RowUpdated event handler.  
AddHandler adapter.RowUpdated, New SqlRowUpdatedEventHandler( _  
  AddressOf OnRowUpdated)  
  
Dim dataSet As DataSet = New DataSet()  
adapter.Fill(dataSet, "Customers")  
  
' Modify the DataSet contents.  
adapter.Update(dataSet, "Customers")  
  
Dim dataRow As DataRow  
  
For Each dataRow In dataSet.Tables("Customers").Rows  
    If dataRow.HasErrors Then   
       Console.WriteLine(dataRow (0) & vbCrLf & dataRow.RowError)  
    End If  
Next  
  
Private Shared Sub OnRowUpdated( _  
  sender As object, args As SqlRowUpdatedEventArgs)  
   If args.RecordsAffected = 0  
      args.Row.RowError = "Optimistic Concurrency Violation!"  
      args.Status = UpdateStatus.SkipCurrentRow  
   End If  
End Sub  
```  
  
```csharp  
// Assumes connection is a valid SqlConnection.  
SqlDataAdapter adapter = new SqlDataAdapter(  
  "SELECT CustomerID, CompanyName FROM Customers ORDER BY CustomerID",  
  connection);  
  
// The Update command checks for optimistic concurrency violations  
// in the WHERE clause.  
adapter.UpdateCommand = new SqlCommand("UPDATE Customers Set CustomerID = @CustomerID, CompanyName = @CompanyName " +  
   "WHERE CustomerID = @oldCustomerID AND CompanyName = @oldCompanyName, connection);  
adapter.UpdateCommand.Parameters.Add(  
  "@CustomerID", SqlDbType.NChar, 5, "CustomerID");  
adapter.UpdateCommand.Parameters.Add(  
  "@CompanyName", SqlDbType.NVarChar, 30, "CompanyName");  
  
// Pass the original values to the WHERE clause parameters.  
SqlParameter parameter = adapter.UpdateCommand.Parameters.Add(  
  "@oldCustomerID", SqlDbType.NChar, 5, "CustomerID");  
parameter.SourceVersion = DataRowVersion.Original;  
parameter = adapter.UpdateCommand.Parameters.Add(  
  "@oldCompanyName", SqlDbType.NVarChar, 30, "CompanyName");  
parameter.SourceVersion = DataRowVersion.Original;  
  
// Add the RowUpdated event handler.  
adapter.RowUpdated += new SqlRowUpdatedEventHandler(OnRowUpdated);  
  
DataSet dataSet = new DataSet();  
adapter.Fill(dataSet, "Customers");  
  
// Modify the DataSet contents.  
  
adapter.Update(dataSet, "Customers");  
  
foreach (DataRow dataRow in dataSet.Tables["Customers"].Rows)  
{  
    if (dataRow.HasErrors)  
       Console.WriteLine(dataRow [0] + "\n" + dataRow.RowError);  
}  
  
protected static void OnRowUpdated(object sender, SqlRowUpdatedEventArgs args)  
{  
  if (args.RecordsAffected == 0)   
  {  
    args.Row.RowError = "Optimistic Concurrency Violation Encountered";  
    args.Status = UpdateStatus.SkipCurrentRow;  
  }  
}  
```  
  
## <a name="see-also"></a>另請參閱  
 [在 ADO.NET 中擷取和修改資料](../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md)  
 [使用 DataAdapter 更新資料來源](../../../../docs/framework/data/adonet/updating-data-sources-with-dataadapters.md)  
 [資料列錯誤資訊](../../../../docs/framework/data/adonet/dataset-datatable-dataview/row-error-information.md)  
 [異動和並行存取](../../../../docs/framework/data/adonet/transactions-and-concurrency.md)  
 [ADO.NET Managed 提供者和 DataSet 開發人員中心](http://go.microsoft.com/fwlink/?LinkId=217917)
