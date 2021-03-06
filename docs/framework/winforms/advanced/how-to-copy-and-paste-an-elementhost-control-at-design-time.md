---
title: 如何：在設計階段複製和貼上 ElementHost 控制項
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms, content copying and pasting
- interoperability [WPF]
- ElementHost control [Windows Forms], copying and pasting at design time
- WPF user control [Windows Forms], hosting in Windows Forms
ms.assetid: e570375d-2a68-44ba-b4f7-c781af2d20e8
ms.openlocfilehash: 1a9938500287b3b44f13f0aa664da85b7fdb4675
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/04/2018
ms.locfileid: "33524848"
---
# <a name="how-to-copy-and-paste-an-elementhost-control-at-design-time"></a>如何：在設計階段複製和貼上 ElementHost 控制項
此程序會示範如何複製 Windows Form 上的 Windows Presentation Foundation (WPF) 控制項。  
  
> [!NOTE]
>  根據您目前使用的設定或版本，您所看到的對話方塊與功能表命令可能會與 [說明] 中描述的不同。 若要變更設定，請從 [ **工具** ] 功能表中選取 [ **匯入和匯出設定** ]。 如需詳細資訊，請參閱 [在 Visual Studio 中自訂開發設定](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3)  
  
### <a name="to-copy-and-paste-an-elementhost-control-at-design-time"></a>複製和貼上 ElementHost 控制項，在設計階段  
  
1.  將新的 WPF<xref:System.Windows.Controls.UserControl>至您的 Windows Form 專案。 使用控制項類型的預設名稱 `UserControl1.xaml`。 如需詳細資訊，請參閱[逐步解說： 建立的新 WPF 內容在設計階段的 Windows Form 上](../../../../docs/framework/winforms/advanced/walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md)。  
  
2.  在**屬性**視窗中，設定的值<xref:System.Windows.FrameworkElement.Width%2A>和<xref:System.Windows.FrameworkElement.Height%2A>屬性`UserControl1`至`200`。  
  
3.  將 <xref:System.Windows.Controls.Control.Background%2A> 屬性值設定為 `Blue`。  
  
4.  建置專案。  
  
5.  在 Windows Form 設計工具中開啟 `Form1`。  
  
6.  從**工具箱**，拖曳的執行個體`UserControl1`拖曳至表單。  
  
     `UserControl1` 的執行個體裝載於名為 `elementHost1` 的新 <xref:System.Windows.Forms.Integration.ElementHost> 控制項中。  
  
7.  在選取 `elementHost1` 時，按 CTRL+C 將其複製到剪貼簿。  
  
8.  按 CTRL + V 鍵貼上複製的控制項拖曳至表單。  
  
     新<xref:System.Windows.Forms.Integration.ElementHost>控制項，名為`elementHost2`建立表單上。  
  
## <a name="see-also"></a>另請參閱  
 <xref:System.Windows.Forms.Integration.ElementHost>  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>  
 [逐步解說：將 ElementHost 控制項複製並貼至另外的 Windows Forms](../../../../docs/framework/winforms/advanced/copy--paste-an-elementhost-control-into-forms.md)  
 [移轉和互通性](../../../../docs/framework/wpf/advanced/migration-and-interoperability.md)  
 [使用 WPF 控制項](../../../../docs/framework/winforms/advanced/using-wpf-controls.md)  
 [WPF 設計工具](http://msdn.microsoft.com/library/c6c65214-8411-4e16-b254-163ed4099c26)
