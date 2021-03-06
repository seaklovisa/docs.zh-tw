---
title: WPF 和 Win32 互通
ms.date: 03/30/2017
helpviewer_keywords:
- hosting WPF content in Win32 window [WPF]
- HWND interop [WPF]
- Win32 code [WPF], WPF interoperation
- interoperability [WPF], Win32
ms.assetid: 0ffbde0d-701d-45a3-a6fa-dd71f4d9772e
ms.openlocfilehash: 8a0e27d46248bdfd782c2cf650faaf8f3bc29960
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/04/2018
ms.locfileid: "33549418"
---
# <a name="wpf-and-win32-interoperation"></a>WPF 和 Win32 互通
本主題概述如何交互操作 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 和 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 程式碼。 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 提供用來建立應用程式的豐富環境。 不過，如果您已長期開發 [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)] 程式碼，則重複使用該程式碼的一部分可能會更有效率。  
  

  
<a name="basics"></a>   
## <a name="wpf-and-win32-interoperation-basics"></a>WPF 和 Win32 交互操作基本概念  
 針對 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 與 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 程式碼之間的交互操作，有兩個基本技術。  
  
-   在 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 視窗中裝載 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 內容。 使用此技術，您可以使用標準 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 視窗和應用程式架構內 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 的進階圖形功能。  
  
-   在 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 內容中裝載 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 視窗。 使用此技術，您可以在其他 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 內容的內容中使用現有的自訂 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 控制項，並跨界限傳遞資料。  
  
 本主題會在概念上介紹所有這些技術。 如需有關在 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 中裝載 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 之程式碼導向的進階說明，請參閱[逐步解說：在 Win32 中裝載 WPF 內容](../../../../docs/framework/wpf/advanced/walkthrough-hosting-wpf-content-in-win32.md)。 如需在 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 中裝載 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 的其他程式碼導向圖例，請參閱[逐步解說：在 Win32 中裝載 WPF 內容](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-win32-control-in-wpf.md)。  
  
<a name="projects"></a>   
## <a name="wpf-interoperation-projects"></a>WPF 交互操作專案  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)] 是 Managed 程式碼，但大部分現有 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 程式都是使用 Unmanaged [!INCLUDE[TLA2#tla_cpp](../../../../includes/tla2sharptla-cpp-md.md)] 所撰寫。  您無法從真正的 Unmanaged 程式呼叫 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)]。 不過，搭配使用 `/clr` 選項與 [!INCLUDE[TLA#tla_visualcpp](../../../../includes/tlasharptla-visualcpp-md.md)] 編譯器，即可建立混合式 Managed/Unmanaged 程式，以順暢地混用 Managed 和 Unmanaged [!INCLUDE[TLA2#tla_api](../../../../includes/tla2sharptla-api-md.md)] 呼叫。  
  
 其中一個專案層級複雜在於您無法將 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] 檔案編譯至 [!INCLUDE[TLA2#tla_cpp](../../../../includes/tla2sharptla-cpp-md.md)] 專案。  有數個專案部門技術可彌補這一點。  
  
-   建立 C# DLL，其中包含所有您[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]做為編譯的組件頁面，然後讓您[!INCLUDE[TLA2#tla_cpp](../../../../includes/tla2sharptla-cpp-md.md)]可執行檔包含該[!INCLUDE[TLA2#tla_dll](../../../../includes/tla2sharptla-dll-md.md)]做為參考。  
  
-   建立 C# 可執行檔[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]內容，並讓它參考[!INCLUDE[TLA2#tla_cpp](../../../../includes/tla2sharptla-cpp-md.md)][!INCLUDE[TLA2#tla_dll](../../../../includes/tla2sharptla-dll-md.md)]包含[!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]內容。  
  
-   使用<xref:System.Windows.Markup.XamlReader.Load%2A>載入任何[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]在執行階段，而不是編譯您[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]。  
  
-   請勿使用[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]，和寫入所有您[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]在程式碼中的項目樹狀結構建置<xref:System.Windows.Application>。  
  
 請使用最適合您的方法。  
  
> [!NOTE]
>  如果您之前未曾使用過 [!INCLUDE[TLA#tla_cppcli](../../../../includes/tlasharptla-cppcli-md.md)]，則會在交互操作程式碼範例中注意到一些「新」關鍵字，例如 `gcnew` 和 `nullptr`。 這些關鍵字取代較舊的雙底線語法 (`__gc`)，並提供 [!INCLUDE[TLA2#tla_cpp](../../../../includes/tla2sharptla-cpp-md.md)] 中 Managed 程式碼的更自然語法。  若要深入了解 [!INCLUDE[TLA#tla_cppcli](../../../../includes/tlasharptla-cppcli-md.md)] Managed 功能，請參閱[執行階段平台的元件延伸功能](/cpp/windows/component-extensions-for-runtime-platforms)和 [Hello, C++/CLI](http://go.microsoft.com/fwlink/?LinkId=98739)。  
  
<a name="hwnds"></a>   
## <a name="how-wpf-uses-hwnds"></a>WPF 如何使用 Hwnd  
 若要將大部分的 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 設為 "HWND interop"，您需要了解 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 如何使用 HWND。 針對任何 HWND，您都無法混合使用 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 轉譯與 [!INCLUDE[TLA2#tla_dx](../../../../includes/tla2sharptla-dx-md.md)] 轉譯或 [!INCLUDE[TLA2#tla_gdi](../../../../includes/tla2sharptla-gdi-md.md)] / [!INCLUDE[TLA2#tla_gdiplus](../../../../includes/tla2sharptla-gdiplus-md.md)] 轉譯。 這有幾個隱含意義。 主要，若要完全混合使用這些轉譯模型，您必須建立交互操作方案，並使用您選擇使用之每個轉譯模型的指定區段交互操作。 此外，轉譯行為還會建立交互操作方案可完成之作業的「空間」限制。 [技術領域概觀](../../../../docs/framework/wpf/advanced/technology-regions-overview.md)主題會更詳細地說明「空間」概念。  
  
 HWND 最後會支援畫面上的所有 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 項目。 當您建立[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Window>，[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]會建立最上層的 HWND，並使用<xref:System.Windows.Interop.HwndSource>放置<xref:System.Windows.Window>及其[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]HWND 內部內容。  應用程式中 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 內容的其餘部分會共用該單一 HWND。 例外狀況是功能表、下拉式方塊下拉式清單和其他快顯視窗。 這些項目會建立自己的最上層視窗，這就是 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 功能表為什麼可以通過包含它的視窗 HWND 邊緣。 當您使用<xref:System.Windows.Interop.HwndHost>放置內 HWND [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]，[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]通知[!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]如何將新的子系 HWND 相對於[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Window> HWND。  
  
 在每個 HWND 之內和之間，相關的 HWND 概念都十分清楚。 [技術領域概觀](../../../../docs/framework/wpf/advanced/technology-regions-overview.md)主題也會討論這點。  
  
<a name="hosting_a_wpf_page"></a>   
## <a name="hosting-wpf-content-in-a-microsoft-win32-window"></a>將 WPF 內容裝載在 Microsoft Win32 視窗中  
 要裝載的索引鍵[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]上[!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]視窗是<xref:System.Windows.Interop.HwndSource>類別。 這個類別會包裝 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 視窗中的 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 內容，以將 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 內容併入 [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] 中作為子視窗。 下列方法會將 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 和 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 合併在單一應用程式中。  
  
1.  將 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 內容 (內容根項目) 實作為 Managed 類別。 一般而言，在類別繼承自一個類別可以包含多個子項目和/或做為根項目，例如<xref:System.Windows.Controls.DockPanel>或<xref:System.Windows.Controls.Page>。 在後續步驟中，這個類別指的是 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 內容類別，而且類別的執行個體指的是 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 內容物件。  
  
2.  以 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 實作 [!INCLUDE[TLA2#tla_cppcli](../../../../includes/tla2sharptla-cppcli-md.md)] 應用程式。 如果您是使用現有 Unmanaged [!INCLUDE[TLA2#tla_cpp](../../../../includes/tla2sharptla-cpp-md.md)] 應用程式開始進行，通常只要變更專案設定來包含 `/clr` 編譯器旗標，該應用程式就可以呼叫 Managed 程式碼 (本主題未描述支援 `/clr` 編譯所需項目的完整範圍)。  
  
3.  將執行緒模型設為單一執行緒 Apartment (STA)。 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 使用此執行緒模型。  
  
4.  處理視窗程序中的 WM_CREATE 通知。  
  
5.  在此處理常式 (或處理常式所呼叫的函式) 內，執行下列動作︰  
  
    1.  建立新<xref:System.Windows.Interop.HwndSource>與父視窗 HWND 物件做為其`parent`參數。  
  
    2.  建立 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 內容類別的執行個體。  
  
    3.  指定的參考[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]內容物件<xref:System.Windows.Interop.HwndSource>物件<xref:System.Windows.Interop.HwndSource.RootVisual%2A>屬性。  
  
    4.  <xref:System.Windows.Interop.HwndSource>物件<xref:System.Windows.Interop.HwndSource.Handle%2A>屬性包含視窗控制代碼 (HWND)。 若要取得可用於應用程式 Unmanaged 部分的 HWND，請將 `Handle.ToPointer()` 轉型為 HWND。  
  
6.  實作 Managed 類別，其中包含靜態欄位來保存 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 內容物件的參考。 這個類別可讓您取得的參考[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]內容的物件，從您[!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]程式碼，但更重要的是它會阻止您<xref:System.Windows.Interop.HwndSource>防止不小心收集到的記憶體回收。  
  
7.  將處理常式附加到一或多個 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 內容物件事件，以接收 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 內容物件的通知。  
  
8.  使用儲存在靜態欄位中的參考來設定屬性及呼叫方法等等，以與 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 內容物件通訊。  
  
> [!NOTE]
>  如果您產生不同的組件，然後參考它，則可以針對使用內容類別之預設部分類別的 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 中的步驟一，執行部分或所有 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 內容類別定義。 雖然您通常會包括<xref:System.Windows.Application>物件做為編譯的組件[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]組件中，您不最後，使用<xref:System.Windows.Application>互通的一部分，您只使用一個以上的根類別[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]檔案參考若要由應用程式並參考它們的部分類別。 此程序的其餘部分基本上與上述類似。  
>   
>  所有這些步驟都是透過[逐步解說：在 Win32 中裝載 WPF 內容](../../../../docs/framework/wpf/advanced/walkthrough-hosting-wpf-content-in-win32.md)主題中的程式碼予以說明。  
  
<a name="hosting_an_hwnd"></a>   
## <a name="hosting-a-microsoft-win32-window-in-wpf"></a>在 WPF 中裝載 Microsoft Win32 視窗  
 要裝載的索引鍵[!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 視窗內其他[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]內容<xref:System.Windows.Interop.HwndHost>類別。 此類別會將視窗包裝在 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 項目中，而此項目可以新增至 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 項目樹狀結構。 <xref:System.Windows.Interop.HwndHost> 也支援[!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)]可讓您執行裝載視窗的處理序訊息等工作。 基本程序如下：  
  
1.  建立 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 應用程式的項目樹狀結構 (可以透過程式碼或標記)。 項目樹狀中尋找適當和允許的點位置<xref:System.Windows.Interop.HwndHost>實作可以加入做為子項目。 在後續步驟中，這個項目稱為保留項目。  
  
2.  衍生自<xref:System.Windows.Interop.HwndHost>建立的物件，包含您[!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]內容。  
  
3.  在該主機類別，覆寫<xref:System.Windows.Interop.HwndHost>方法<xref:System.Windows.Interop.HwndHost.BuildWindowCore%2A>。 傳回裝載之視窗的 HWND。 您可能想要將實際控制項包裝為所傳回視窗的子視窗；在主視窗中包裝控制項可提供簡單方式，讓 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 內容接收來自控制項的通知。 這項技術可協助修正與託管控制項界限的訊息處理相關的一些 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 問題。  
  
4.  覆寫<xref:System.Windows.Interop.HwndHost>方法<xref:System.Windows.Interop.HwndHost.DestroyWindowCore%2A>和<xref:System.Windows.Interop.HwndHost.WndProc%2A>。 這裡的目的是處理裝載之內容的清除和移除參考，特別是您已建立未受管理物件的參考時。  
  
5.  在程式碼後置檔案中，建立控制項裝載類別的執行個體，並將它設定為保留項目的子系。 通常您會使用事件處理常式，例如<xref:System.Windows.FrameworkElement.Loaded>，或使用部分類別建構函式。 但是，您也可以透過執行階段行為來新增交互操作內容。  
  
6.  處理選取的視窗訊息，例如控制項通知。 有兩種方法。 兩者都提供訊息資料流的相同存取權，因此您的選擇大部分取決於程式設計便利性。  
  
    -   實作訊息處理的所有訊息 （不只是關閉的訊息） 的覆寫中<xref:System.Windows.Interop.HwndHost>方法<xref:System.Windows.Interop.HwndHost.WndProc%2A>。  
  
    -   已裝載[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]項目處理的訊息處理<xref:System.Windows.Interop.HwndHost.MessageHook>事件。 針對傳送至裝載視窗之主要視窗程序的每個訊息，都會引發此事件。  
  
    -   您無法處理來自超出處理程序使用的 windows 訊息<xref:System.Windows.Interop.HwndHost.WndProc%2A>。  
  
7.  使用平台叫用來呼叫 Unmanaged `SendMessage` 函式，以與裝載的視窗通訊。  
  
 遵循下列步驟會建立可使用滑鼠輸入的應用程式。 您可以主控視窗加入 tab 鍵移動的支援，藉由實作<xref:System.Windows.Interop.IKeyboardInputSink>介面。  
  
 所有這些步驟都是透過[逐步解說：在 WPF 中裝載 Win32 控制項](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-win32-control-in-wpf.md)主題中的程式碼予以說明。  
  
### <a name="hwnds-inside-wpf"></a>WPF 內的 Hwnd  
 您可以將<xref:System.Windows.Interop.HwndHost>做為特殊的控制項。 (技術上來說，<xref:System.Windows.Interop.HwndHost>是<xref:System.Windows.FrameworkElement>不衍生的類別，<xref:System.Windows.Controls.Control>衍生的類別，但它可以視為的互通性目的的控制項。)<xref:System.Windows.Interop.HwndHost>抽象化基礎[!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]裝載內容的本質如此的其餘部分[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]認為是另一個類似控制項的物件，它應該轉譯和處理輸入裝載的內容。 <xref:System.Windows.Interop.HwndHost> 一般行為如同任何其他[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.FrameworkElement>，但是有一些重要差異周圍輸出 （繪圖和圖形），而且可支援輸入 （滑鼠及鍵盤） 根據將基礎 Hwnd 的限制。  
  
#### <a name="notable-differences-in-output-behavior"></a>輸出行為的顯著差異  
  
-   <xref:System.Windows.FrameworkElement>這是<xref:System.Windows.Interop.HwndHost>基底類別，具有極多的暗示 ui 變更的屬性。 這包括屬性，例如<xref:System.Windows.FrameworkElement.FlowDirection%2A?displayProperty=nameWithType>，該元素的父系內的項目配置的變更。 不過，這些屬性大部分都不會對應至可能的 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 對等項目，即使這類對等項目可能存在。 這些屬性的絶大多數和其意義太特定於轉譯技術，以致對應成為實際。 因此，設定屬性，例如<xref:System.Windows.FrameworkElement.FlowDirection%2A>上<xref:System.Windows.Interop.HwndHost>沒有任何作用。  
  
-   <xref:System.Windows.Interop.HwndHost> 無法旋轉、 縮放、 扭曲，或者受到轉換。  
  
-   <xref:System.Windows.Interop.HwndHost> 不支援<xref:System.Windows.UIElement.Opacity%2A>（alpha 混色） 的屬性。 如果內容內<xref:System.Windows.Interop.HwndHost>執行<xref:System.Drawing>作業，包括 alpha 相關資訊，本身不是違規情形，但<xref:System.Windows.Interop.HwndHost>因為整個只支援的不透明度 = 1.0 （100%)。  
  
-   <xref:System.Windows.Interop.HwndHost> 將會出現在其他頂端[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]相同的最上層視窗中的項目。 不過，<xref:System.Windows.Controls.ToolTip>或<xref:System.Windows.Controls.ContextMenu>產生的 是個別的最上層視窗，並因此行為會正確地與<xref:System.Windows.Interop.HwndHost>。  
  
-   <xref:System.Windows.Interop.HwndHost> 不會遵守其父代的裁剪區域<xref:System.Windows.UIElement>。 這是潛在的問題，如果您嘗試將<xref:System.Windows.Interop.HwndHost>捲軸的區域內的類別或<xref:System.Windows.Controls.Canvas>。  
  
#### <a name="notable-differences-in-input-behavior"></a>輸入行為的顯著差異  
  
-   一般而言，而範圍內的輸入的裝置<xref:System.Windows.Interop.HwndHost>裝載[!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]區域中，輸入的事件直接前往[!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]。  
  
-   當滑鼠經過<xref:System.Windows.Interop.HwndHost>，您的應用程式不會收到[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]滑鼠事件和值[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]屬性<xref:System.Windows.UIElement.IsMouseOver%2A>會`false`。  
  
-   雖然<xref:System.Windows.Interop.HwndHost>具有鍵盤焦點，您的應用程式將不會收到[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]鍵盤事件和值[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]屬性<xref:System.Windows.UIElement.IsKeyboardFocusWithin%2A>會`false`。  
  
-   當焦點是在<xref:System.Windows.Interop.HwndHost>和變更為其他控制項內<xref:System.Windows.Interop.HwndHost>，您的應用程式將不會收到[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]事件<xref:System.Windows.UIElement.GotFocus>或<xref:System.Windows.UIElement.LostFocus>。  
  
-   相關手寫筆屬性和事件類似，且不會回報資訊手寫筆上的同時<xref:System.Windows.Interop.HwndHost>。  
  
<a name="tabbing_mnemonics_accelerators"></a>   
## <a name="tabbing-mnemonics-and-accelerators"></a>定位處理、助憶鍵和加速器  
 <xref:System.Windows.Interop.IKeyboardInputSink>和<xref:System.Windows.Interop.IKeyboardInputSite>介面可讓您可以建立無縫式鍵盤經驗，針對混合[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]和[!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]應用程式：  
  
-   [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 與 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 元件之間的定位處理  
  
-   焦點在 Win32 元件內以及在 WPF 元件內時所使用的助憶鍵和加速器。  
  
 <xref:System.Windows.Interop.HwndHost>和<xref:System.Windows.Interop.HwndSource>這兩種類別提供的實作<xref:System.Windows.Interop.IKeyboardInputSink>，但它們可能不會處理所有您想要用於更進階案例的輸入的訊息。 覆寫適當的方法，以取得您想要的鍵盤行為。  
  
 這些介面僅支援在 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 與 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 區域之間轉換時所發生的情況。 在 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 區域內，定位處理行為完全是透過 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 實作的定位處理邏輯所控制 (如果有的話)。  
  
## <a name="see-also"></a>另請參閱  
 <xref:System.Windows.Interop.HwndHost>  
 <xref:System.Windows.Interop.HwndSource>  
 <xref:System.Windows.Interop>  
 [逐步解說：在 WPF 中裝載 Win32 控制項](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-win32-control-in-wpf.md)  
 [逐步解說：在 Win32 中裝載 WPF 內容](../../../../docs/framework/wpf/advanced/walkthrough-hosting-wpf-content-in-win32.md)
