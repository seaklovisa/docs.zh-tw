---
title: Windows Form 控制項中的事件
ms.date: 03/30/2017
helpviewer_keywords:
- events [Windows Forms], custom controls (using code)
- custom controls [Windows Forms], events overview (using code)
ms.assetid: 7e3d1379-87aa-437c-afce-c99454eff30e
ms.openlocfilehash: 5d51b6a71bffb546c85ba253181453f6deecfa64
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/04/2018
ms.locfileid: "33525879"
---
# <a name="events-in-windows-forms-controls"></a>Windows Form 控制項中的事件
Windows Form 控制項繼承來自多個六十事件<xref:System.Windows.Forms.Control?displayProperty=nameWithType>。 這些包括<xref:System.Windows.Forms.Control.Paint>會導致要繪製控制項的事件，例如顯示視窗，與相關的事件<xref:System.Windows.Forms.Control.Resize>和<xref:System.Windows.Forms.Control.Layout>事件，以及低階滑鼠和鍵盤事件。 某些低階事件，可由合成<xref:System.Windows.Forms.Control>成語意的事件，例如<xref:System.Windows.Forms.Control.Click>和<xref:System.Windows.Forms.Control.DoubleClick>。 如需繼承的事件的詳細資訊，請參閱<xref:System.Windows.Forms.Control>。  
  
 如果您的自訂控制項需要覆寫繼承的事件功能，請覆寫繼承的 `On` *EventName* 方法，而不要附加委派。 如果您不熟悉 .NET Framework 中的事件模型，請參閱[從元件引發事件](http://msdn.microsoft.com/library/9aebf605-a87d-470b-b7c8-f9abfc8360a0)。  
  
## <a name="see-also"></a>另請參閱  
 [覆寫 OnPaint 方法](../../../../docs/framework/winforms/controls/overriding-the-onpaint-method.md)  
 [處理使用者輸入](../../../../docs/framework/winforms/controls/handling-user-input.md)  
 [定義事件](../../../../docs/framework/winforms/controls/defining-an-event-in-windows-forms-controls.md)  
 [事件](../../../../docs/standard/events/index.md)
