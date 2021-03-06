---
title: 疑難排解：記錄檔接聽程式 (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- event logs, troubleshooting
- troubleshooting Visual Basic, event logs
- troubleshooting event logs
ms.assetid: ac6eb760-3d5d-461e-aedd-40599ee22e49
ms.openlocfilehash: 54c3ed0f607edf992fa3c40a8e6214252740587c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/04/2018
ms.locfileid: "33589031"
---
# <a name="troubleshooting-log-listeners-visual-basic"></a>疑難排解：記錄檔接聽程式 (Visual Basic)
您可以使用 `My.Application.Log` 和 `My.Log` 物件來記錄應用程式中發生之事件的相關資訊。  
  
 若要判斷哪些記錄檔接聽程式接收這些訊息，請參閱[逐步解說：判斷 My.Application.Log 寫入資訊的位置](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-determining-where-my-application-log-writes-information.md)。  
  
 `Log` 物件可以使用記錄檔篩選來限制記錄的資訊數量。 如果篩選條件設定錯誤，記錄檔可能包含錯誤的資訊。 如需詳細資訊，請參閱[逐步解說：篩選 My.Application.Log 輸出](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-filtering-my-application-log-output.md)。  
  
 不過，如果記錄檔設定不正確，您可能需要目前組態的詳細資訊。 您可以透過記錄檔的進階 `TraceSource` 屬性來取得這項資訊。  
  
### <a name="to-determine-the-log-listeners-for-the-log-object-in-code"></a>判斷程式碼中記錄檔物件的記錄檔接聽程式  
  
1.  在程式碼檔案的開頭處匯入 <xref:System.Diagnostics> 命名空間。 如需詳細資訊，請參閱 [Imports 陳述式 (.NET 命名空間和類型)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)。  
  
     [!code-vb[VbVbalrMyApplicationLog#13](../../../../visual-basic/developing-apps/programming/log-info/codesnippet/VisualBasic/troubleshooting-log-listeners_1.vb)]  
  
2.  建立會傳回字串的函式，而該字串包含每個記錄檔接聽程式的資訊。  
  
     [!code-vb[VbVbalrMyApplicationLog#14](../../../../visual-basic/developing-apps/programming/log-info/codesnippet/VisualBasic/troubleshooting-log-listeners_2.vb)]  
  
3.  將記錄檔的追蹤接聽程式集合傳遞至 `GetListeners` 函式，並顯示傳回值。  
  
     [!code-vb[VbVbalrMyApplicationLog#19](../../../../visual-basic/developing-apps/programming/log-info/codesnippet/VisualBasic/troubleshooting-log-listeners_3.vb)]  
  
     如需詳細資訊，請參閱<xref:Microsoft.VisualBasic.Logging.Log.TraceSource%2A>。  
  
## <a name="see-also"></a>請參閱  
 <xref:Microsoft.VisualBasic.Logging.Log?displayProperty=nameWithType>  
 [使用應用程式記錄檔](../../../../visual-basic/developing-apps/programming/log-info/working-with-application-logs.md)  
 [逐步解說：判斷 My.Application.Log 寫入資訊的位置](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-determining-where-my-application-log-writes-information.md)
