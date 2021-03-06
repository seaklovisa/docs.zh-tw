---
title: 操作說明：使用 PointAnimation 建立物件位置的動畫
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- graphics [WPF], animation
- animation [WPF], PointAnimation
ms.assetid: 42310977-cc90-438a-8a47-0345898e01be
ms.openlocfilehash: 326b71c10ad608e2481673e1c4a8cbc9ecbdc0dc
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/04/2018
ms.locfileid: "33559166"
---
# <a name="how-to-animate-the-position-of-an-object-by-using-pointanimation"></a>操作說明：使用 PointAnimation 建立物件位置的動畫
這個範例示範如何使用<xref:System.Windows.Media.Animation.PointAnimation>類別以動畫方式顯示物件沿著<xref:System.Windows.Shapes.Path>。  
  
## <a name="example"></a>範例  
 下列範例會沿著移動橢圓形<xref:System.Windows.Shapes.Path>從另一個螢幕上的一個點。 此範例的位置以動畫方式顯示<xref:System.Windows.Media.EllipseGeometry>使用<xref:System.Windows.Media.Animation.PointAnimation>以動畫方式顯示<xref:System.Windows.Media.EllipseGeometry.Center%2A>屬性。  
  
 [!code-csharp[BasicAnimations_snip#PointAnimationWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BasicAnimations_snip/CSharp/PointAnimationExample.cs#pointanimationwholepage)]
 [!code-vb[BasicAnimations_snip#PointAnimationWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BasicAnimations_snip/VisualBasic/PointAnimationExample.vb#pointanimationwholepage)]  
  
## <a name="see-also"></a>另請參閱  
 <xref:System.Windows.Media.Animation.PointAnimation>  
 <xref:System.Windows.Shapes.Path>  
 <xref:System.Windows.Media.EllipseGeometry>  
 <xref:System.Windows.Media.EllipseGeometry.Center%2A>  
 [動畫概觀](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [圖形和多媒體](../../../../docs/framework/wpf/graphics-multimedia/index.md)  
 [HOW-TO 主題](../../../../docs/framework/wpf/graphics-multimedia/graphics-how-to-topics.md)  
 [動畫和計時](http://msdn.microsoft.com/library/7d83765b-d5ae-41b1-b423-80206e1124aa)  
 [HOW-TO 主題](../../../../docs/framework/wpf/graphics-multimedia/animation-and-timing-how-to-topics.md)
