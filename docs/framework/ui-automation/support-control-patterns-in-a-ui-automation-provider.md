---
title: 支援 UI 自動化提供者的控制項模式
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- control patterns, supporting in UI Automation provider
- UI Automation, supporting control patterns in provider
ms.assetid: 0d635c35-ffa8-4dc8-bbc9-12fcd5445776
author: Xansky
ms.author: mhopkins
manager: markl
ms.openlocfilehash: 0c7ca4507ce5e7d2f6f295caace23134a8a6d492
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/04/2018
ms.locfileid: "33398982"
---
# <a name="support-control-patterns-in-a-ui-automation-provider"></a>支援 UI 自動化提供者的控制項模式
> [!NOTE]
>  這份文件適用於想要使用 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 命名空間中定義之 Managed <xref:System.Windows.Automation> 類別的 .NET Framework 開發人員。 如需 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]的最新資訊，請參閱 [Windows Automation API：使用者介面自動化](http://go.microsoft.com/fwlink/?LinkID=156746)。  
  
 本主題說明如何在使用者介面自動化提供者上實作一個或多個控制項模式，讓用戶端應用程式能夠操作控制項並從中取得資料。  
  
### <a name="support-control-patterns"></a>支援控制項模式  
  
1.  針對項目應該支援的控制項模式，實作適當的介面，例如適用於 <xref:System.Windows.Automation.Provider.IInvokeProvider> 的 <xref:System.Windows.Automation.InvokePattern>。  
  
2.  傳回物件，其中包含您的實作中的每個控制項介面的實作 <xref:System.Windows.Automation.Provider.IRawElementProviderSimple.GetPatternProvider%2A?displayProperty=nameWithType>  
  
## <a name="example"></a>範例  
 下列範例示範單一選取自訂清單方塊的 <xref:System.Windows.Automation.Provider.ISelectionProvider> 實作。 它會傳回三個屬性並取得目前選取的項目。  
  
 [!code-csharp[UIAFragmentProvider_snip#119](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAFragmentProvider_snip/CSharp/ListPattern.cs#119)]
 [!code-vb[UIAFragmentProvider_snip#119](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAFragmentProvider_snip/VisualBasic/ListPattern.vb#119)]  
  
## <a name="example"></a>範例  
 下列範例示範 <xref:System.Windows.Automation.Provider.IRawElementProviderSimple.GetPatternProvider%2A> 的實作，它會傳回實作 <xref:System.Windows.Automation.Provider.ISelectionProvider>的類別。 大部分清單方塊控制項會支援其他模式，但在此範例中為 null 參考 (`Nothing`在 Microsoft Visual Basic.NET) 傳回的所有其他模式識別項。  
  
 [!code-csharp[UIAFragmentProvider_snip#120](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAFragmentProvider_snip/CSharp/ListFragment.cs#120)]
 [!code-vb[UIAFragmentProvider_snip#120](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAFragmentProvider_snip/VisualBasic/ListFragment.vb#120)]  
  
## <a name="see-also"></a>另請參閱  
 [UI 自動化提供者概觀](../../../docs/framework/ui-automation/ui-automation-providers-overview.md)  
 [伺服器端 UI 自動化提供者實作](../../../docs/framework/ui-automation/server-side-ui-automation-provider-implementation.md)
