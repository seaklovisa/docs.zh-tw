---
title: WCF 測試用戶端 (WcfTestClient.exe)
ms.date: 03/30/2017
ms.assetid: d4302855-677f-4640-aa90-c5d785d72fb7
ms.openlocfilehash: 78be40268b46c4c85ee034db67d67ee0fbf2158f
ms.sourcegitcommit: 15109844229ade1c6449f48f3834db1b26907824
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/07/2018
ms.locfileid: "33809741"
---
# <a name="wcf-test-client-wcftestclientexe"></a>WCF 測試用戶端 (WcfTestClient.exe)
Windows Communication Foundation (WCF) 測試用戶端 (WcfTestClient.exe) 是一種 GUI 工具，可讓使用者輸入測試參數，請送出該輸入至服務，並檢視服務傳回的回應。 它提供了完善的服務測試經驗結合 WCF 服務主機時。  
  
 您通常可以找到 WCF 測試用戶端 (WcfTestClient.exe) 中的下列位置： C:\Program Files (x86) \Microsoft Visual Studio\2017\Community\Common7\IDE-社群可能是"Enterprise"、"專業 」 或 「 社群 」 取決於其中之一已安裝的 Visual Studio 層級。
  
## <a name="scenarios-for-using-test-client"></a>使用測試用戶端的案例  
 下列章節會討論最常見的案例，讓您可以使用 WCF 測試用戶端簡化開發程序。  
  
### <a name="inside-visual-studio"></a>在 Visual Studio 內部  
  
#### <a name="wcf-service-host-starts-wcf-test-client-with-a-single-service"></a>WCF 服務主機啟動具有單一服務的 WCF 測試用戶端  
 建立新的 WCF 服務專案後，當您按 f5 鍵啟動偵錯工具時，WCF 服務主機會開始裝載您的專案中的服務。 然後，WCF 測試用戶端開啟，並顯示組態檔中定義的服務端點的清單。 您可以測試參數並叫用服務，然後重複這個程序以持續測試及驗證服務。  
  
#### <a name="wcf-service-host-starts-wcf-test-client-with-multiple-services"></a>WCF 服務主機啟動具有多個服務的 WCF 測試用戶端  
 您也可以使用 WCF 測試用戶端協助偵錯包含多個服務的服務專案。 WCF 測試用戶端開啟時，它會自動反覆運算的專案中的服務清單，並開啟這些測試。  
  
### <a name="outside-visual-studio"></a>在 Visual Studio 外部  
 您也可以使用以測試網際網路上的任意服務的 Visual Studio 外部叫用 WCF 測試用戶端 (WcfTestClient.exe)。 若要找出該工具，請移至下列位置：  
  
 C:\Program Files\Microsoft Visual Studio 9.0\Common7\IDE\  
  
 若要使用該工具，按兩下檔名即可從這個位置開啟，或者是從命令列進行啟動。  
  
 WCF 測試用戶端可以採用任意數目的 Uri 做為命令列引數。  這些引數是可以測試的服務 URI。  
  
 `wcfTestClient.exe URI1 URI2 …`  
  
 WCF 測試用戶端視窗開啟後，按一下**檔案**->**加入服務**，並輸入您想要開啟的服務的端點位址。  
  
## <a name="wcf-test-client-user-interface"></a>WCF 測試用戶端使用者介面  
 您可以使用 WCF 測試用戶端使用單一的服務或多個服務。  
  
### <a name="service-operations"></a>服務作業  
 WCF 測試用戶端主視窗的左的窗格會列出所有可用的服務，以及它們各自的端點和作業。  
  
 按兩下某項作業時，您可以在右窗格中具有該作業名稱的新索引標籤內，檢視其內容。  
  
 左窗格還會列出用戶端組態檔。 按兩下任何項目，即可在右窗格中新出現的索引視窗上看見檔案的內容。  
  
### <a name="entering-test-parameters"></a>輸入測試參數  
 若要檢視測試參數，請按兩下作業，在右窗格中開啟它。 參數會顯示在**格式化**依預設，檢視，而且您可以輸入任意測試服務的參數值。  
  
 若要檢視訊息的 XML，請按一下**XML**。 若要將它們傳送至服務，按一下**Invoke**。  
  
 資料集參數，按一下  **...** 下一步按鈕**編輯...** 若要在新視窗顯示 DataGrid 中進行編輯。 請注意，出現**複製資料集**和**貼上資料集**按鈕。 如果在第一次編輯時 DataSet 物件的結構描述為未知，DataGrid 為空白。 您必須將具有相同結構描述的 DataSet 物件貼入 DataGrid 中的目前物件  (請注意，您必須在貼上作業前從其他地方複製結構描述)。您也可以按一下 [複製 Dataset 物件供未來使用**複製資料集**] 按鈕。  
  
 服務的回應會出現在測試參數下方。  
  
> [!NOTE]
>  如果預期的傳回值是字串，則結果會顯示為引號括住的字串，即使提供的輸入並未以引號括住。  
  
 如果您在建立服務合約時將特定作業指定為單向，就不會顯示任何服務回應。 訊息一旦排入佇列中準備傳遞，快顯對話方塊就會出現，通知您已成功傳送訊息。  
  
### <a name="session-support"></a>工作階段支援  
 **啟動新 proxy**服務作業的索引標籤中的核取方塊可讓您切換工作階段支援。 這個方塊預設為清除。  
  
 當您輸入的特定作業 （或另一個作業中相同的服務端點） 的測試參數，並按一下**Invoke**多次清除該核取方塊，這些作業會共用一個 proxy，而服務狀態為保留跨多個作業。  
  
 如果**啟動新 proxy**核取方塊已核取，新的 proxy 啟動每個**Invoke**早的工作階段就會結束，且會重設服務狀態。  
  
### <a name="editing-client-configuration"></a>編輯用戶端組態  
 WCF 測試用戶端主視窗的左的窗格會列出用戶端組態檔。 按兩下任何項目，即可在右窗格中顯示檔案的內容。  
  
#### <a name="edit-with-service-configuration-editor"></a>使用服務組態編輯器進行編輯  
 以滑鼠右鍵按一下**組態檔**在左的窗格中選取內容功能表**使用 SvcConfigEditor 編輯**。 服務組態編輯器隨即啟動，並顯示用戶端組態內容。 您可以在該工具內編輯組態並進行儲存。  
  
 之後將檔案儲存在服務組態編輯器，WCF 測試用戶端會顯示警告訊息，通知您檔案已在外部經過修改，並詢問您是否要重新載入。  
  
 如果您選取**是**，[Client.dll.config] 索引標籤中的組態內容會反映您在編輯器中所做的變更。  
  
 如果您選取**否**，[Client.dll.config] 索引標籤中的組態內容會維持不變，和原始程式檔都會自動儲存修改過的內容。  
  
#### <a name="restore-to-default-configuration"></a>還原至預設組態  
 如果您想要取消所有變更並還原為預設用戶端設定，以滑鼠右鍵按一下**組態檔**在左的窗格中選取內容功能表**還原至預設組態**。載入預設組態值，並還原 Client.dll.config 索引標籤中的內容。  
  
#### <a name="validate-changes"></a>驗證變更  
 當在 WCF 測試用戶端正在載入儲存的變更時，組態會檢查針對 WCF 結構描述的有效性。 如果發現錯誤，會顯示對話方塊說明錯誤詳細資料。  
  
 在 proxy 產生、 二進位編譯或服務叫用，已停用支援編輯 （亦即，[編輯]、 [還原]，等等） 的功能表項目。 載入 WCF 測試用戶端更新組態時，也會停用服務叫用。  
  
#### <a name="persist-client-configuration"></a>保存用戶端組態  
 **工具**->**選項**->**用戶端設定** 索引標籤包含**永遠重新產生組態時啟動服務**選項，預設會啟用此選項。 這個選項會指定，每次 WCF 測試用戶端載入服務時，它會重新產生組態檔的最新的服務合約和服務 App.config 檔案。  
  
 如果您編輯用戶端設定 WCF 服務，並想要一律使用這個更新的檔案進行偵錯您的服務，您可以取消核取**重新產生**選項。 如此一來，即使當您更新服務並重新開啟 WCF 測試用戶端，Client.dll.config 檔案是您先前更新而不是重新產生其中根據更新的服務。  
  
 但是，您可能需要編輯組態檔，讓其跟重新產生的 Proxy 一致。 如果重新產生的 Proxy 和組態檔因更新服務而不相符，則在叫用服務時將發生錯誤。  
  
> [!CAUTION]
>  如果您修改過用戶端組態檔並選擇供往後重複使用，則可以在下列位置找到該檔案：  
>   
>  \Documents and 設定\\[使用者帳戶] \My Documents\Test 用戶端專案。  
>   
>  任何儲存在用戶端組態檔中經過更新的認證資訊，皆受到這個資料夾的存取控制清單 (ACL) 所保護。  
  
### <a name="adding-removing-and-refreshing-services"></a>新增、移除和重新整理服務  
  
#### <a name="add-service"></a>新增服務  
 按一下**檔案**->**加入服務**將服務加入至 WCF 測試用戶端。 接著會要求您輸入要新增之服務的 URI (端點位址)。 服務位址可以是 Mex 位址或 WSDL 位址。  
  
 您也可以尋找清單中的 10 個最近新增的服務端點的**最近使用的服務**子功能表。 如果您選取其中一個，指定的服務便會加入 WCF 測試用戶端。  
  
 您也可以以滑鼠右鍵按一下服務樹狀目錄的根目錄**我的服務專案**，然後選取**加入服務**以達成相同結果。  
  
 在 Proxy 產生、二進位編譯或服務叫用期間，會停用支援新增服務的功能表項目。 同時也會停用服務叫用。  
  
#### <a name="remove-service"></a>移除服務  
 以滑鼠右鍵按一下要移除，然後選取服務的服務根目錄**移除服務**從 WCF 測試用戶端移除服務。  
  
 在 Proxy 產生、二進位編譯或服務叫用期間，會停用支援移除服務的功能表項目。 同時也會停用服務叫用。  
  
#### <a name="refresh-service"></a>重新整理服務  
 如果服務進行變更，而 WCF 測試用戶端正在執行，而且您想要確保是最新的 WCF 測試用戶端實作，該服務，以滑鼠右鍵按一下服務，然後選取的服務根目錄**重新整理服務**。 請注意，重新整理後會重設服務狀態。  
  
 在 Proxy 產生、二進位編譯或服務叫用期間，會停用支援重新整理服務的功能表項目。 同時也會停用服務叫用。  
  
## <a name="location-of-files-generated-by-the-test-client"></a>測試用戶端產生的檔案位置  
 根據預設，WCF 測試用戶端會將產生的用戶端程式碼和組態檔在"%appdata%\Local\temp\Test Client Projects"資料夾中。 WCF 測試用戶端結束後，會刪除此資料夾。 如果在 WCF 測試用戶端修改設定檔和**重新產生組態啟動服務時永遠**選項已停用，已修改的檔案會複製到"My Documents\Test Client Projects 下的"Cached Config"資料夾Documents\Test Client Projects"並做為索引的對應 （中繼資料-位址-到-檔名） XML 檔案。  
  
 您也可以在 命令列使用啟動 WCF 測試用戶端`/ProjectPath`參數指定新的目標的路徑，用於儲存產生的檔案，或是使用`/RestoreProjectPath`參數還原預設位置。 語法如下：  
  
 `wcfTestClient.exe /ProjectPath [desired location]`  
  
 執行此命令不會開啟 WCF 測試用戶端。 只是會變更資料夾位置。 您可以執行此命令是否正在執行 WCF 測試用戶端。 重新啟動 WCF 測試用戶端時，會套用新的位置。 在登錄中，或在"%appdata%\Local\temp\Test Client Projects"資料夾中的 wcftestclient.exe.option 檔案中，可以儲存的位置資訊。  
  
## <a name="features-supported-by-wcf-test-client"></a>WCF 測試用戶端支援的功能  
 下列是 WCF 測試用戶端支援的功能清單：  
  
-   服務叫用：要求/回應和單向訊息。  
  
-   繫結：Svcutil.exe 支援的所有繫結。  
  
-   控制工作階段。  
  
-   訊息合約。  
  
-   XML 序列化。  
  
 下列是 WCF 測試用戶端不支援的功能清單：  
  
-   型別：<xref:System.IO.Stream>、<xref:System.ServiceModel.Channels.Message>、<xref:System.Xml.XmlElement>、<xref:System.Xml.XmlAttribute>、<xref:System.Xml.XmlNode>、實作 <xref:System.Xml.Serialization.IXmlSerializable> 介面的型別，包括相關 <xref:System.Xml.Serialization.XmlSchemaProviderAttribute> 屬性、<xref:System.Xml.Linq.XDocument> 和 <xref:System.Xml.Linq.XElement> 型別，以及 ADO.NET <xref:System.Data.DataTable> 型別。  
  
-   雙工合約。  
  
-   交易。  
  
-   安全性：[!INCLUDE[infocard](../../../includes/infocard-md.md)]、憑證和使用者名稱/密碼。  
  
-   繫結：WSFederationbinding、任何 Context 繫結和 Https 繫結、WebHttpbinding (Json 回應訊息支援)。  
  
## <a name="closing-wcf-test-client"></a>關閉 WCF 測試用戶端  
 您可以下列方式來關閉 WCF 測試用戶端：  
  
-   在**檔案**功能表上，按一下 **結束**。 或者，在 WCF 測試用戶端主視窗中，按一下**關閉**。 這些動作也關閉 WCF 服務自動主機和停止 Visual Studio 偵錯程序，如果由 Visual Studio 啟動 WCF 測試用戶端。  
  
-   以滑鼠右鍵按一下**WCF 服務主機**圖示在通知區域中，然後按一下**結束。** 這會關閉 WCF 服務自動主機和 WCF 測試用戶端，並停止 Visual Studio 偵錯處理序。  
  
## <a name="see-also"></a>另請參閱  
 [WCF 服務主機 (WcfSvcHost.exe)](../../../docs/framework/wcf/wcf-service-host-wcfsvchost-exe.md)
