---
title: Oracle REF CURSOR
ms.date: 03/30/2017
ms.assetid: c6b25b8b-0bdd-41b2-9c7c-661f070c2247
ms.openlocfilehash: 7aae9b2e4b39cf164a93ba82212b5705f583d761
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/03/2018
---
# <a name="oracle-ref-cursors"></a>Oracle REF CURSOR
.NET Framework Data Provider for Oracle 支援 Oracle **REF CURSOR**資料型別。 透過資料提供者使用 Oracle REF CURSOR 時，您應考量下列行為。  
  
> [!NOTE]
>  某些行為與 Oracle 的 Microsoft OLE DB 提供者 (MSDAORA) 的行為不同。  
  
-   基於效能考量，Oracle 的資料提供者不會自動繫結**REF CURSOR**的資料類型，如 MSDAORA 一樣，除非您明確指定。  
  
-   該資料提供者不支援任何 ODBC 逸出序列，包括用來指定 REF CURSOR 參數的 {resultset} 逸出。  
  
-   若要執行傳回 REF Cursor 的預存程序，您必須定義中的參數<xref:System.Data.OracleClient.OracleParameterCollection>與<xref:System.Data.OracleClient.OracleType>的**游標**和<xref:System.Data.OracleClient.OracleParameter.Direction%2A>的**輸出**。 資料提供者僅支援將 REF CURSOR 繫結為輸出參數。 提供者不支援 REF CURSOR 做為輸入參數。  
  
-   不支援從參數值取得 <xref:System.Data.OracleClient.OracleDataReader>。 命令執行後，值的型別為 <xref:System.DBNull>。  
  
-   唯一**CommandBehavior** REF Cursor 的運作方式的列舉值 (例如，當呼叫<xref:System.Data.OracleClient.OracleCommand.ExecuteReader%2A>) 是**CloseConnection**; 忽略所有其他的。  
  
-   中的 REF Cursor 的順序**OracleDataReader**結餘中的參數取決於**OracleParameterCollection**。 忽略 <xref:System.Data.OracleClient.OracleParameter.ParameterName%2A> 屬性。  
  
-   PL/SQL**資料表**不支援資料類型。 然而，REF CURSOR 更有效率。 如果您必須使用**資料表**資料類型，使用 MSDAORA OLE DB.NET 資料提供者。  
  
## <a name="in-this-section"></a>本節內容  
 [REF CURSOR 範例](../../../../docs/framework/data/adonet/ref-cursor-examples.md)  
 包含示範如何使用 REF CURSOR 的三個範例。  
  
 [OracleDataReader 中的 REF CURSOR 參數](../../../../docs/framework/data/adonet/ref-cursor-parameters-in-an-oracledatareader.md)  
 示範如何執行傳回 REF CURSOR 參數，並讀取做為值的 PL/SQL 預存程序**OracleDataReader**。  
  
 [使用 OracleDataReader 從多個 REF CURSOR 擷取資料](../../../../docs/framework/data/adonet/retrieving-data-from-multiple-ref-cursors.md)  
 示範如何執行傳回兩個 REF CURSOR 參數，並讀取值使用的 PL/SQL 預存程序**OracleDataReader**。  
  
 [使用一或多個 REF CURSOR 填入資料集](../../../../docs/framework/data/adonet/filling-a-dataset-using-one-or-more-ref-cursors.md)  
 示範如何執行傳回兩個 REF CURSOR 參數的 PL/SQL 預存程序，並使用傳回的資料列填入 <xref:System.Data.DataSet>。  
  
## <a name="see-also"></a>另請參閱  
 [Oracle 和 ADO.NET](../../../../docs/framework/data/adonet/oracle-and-adonet.md)  
 [ADO.NET Managed 提供者和 DataSet 開發人員中心](http://go.microsoft.com/fwlink/?LinkId=217917)
