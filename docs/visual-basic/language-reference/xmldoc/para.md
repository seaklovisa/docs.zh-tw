---
title: '&lt;para&gt; (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- <para> XML tag
- para XML tag
ms.assetid: a3a18b6c-6416-4358-94ec-37b22675fd37
ms.openlocfilehash: cb80f4b39bee128790b311732adf1202dbbc6993
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/04/2018
ms.locfileid: "33601721"
---
# <a name="ltparagt-visual-basic"></a>&lt;para&gt; (Visual Basic)
指定內容的格式設段落。  
  
## <a name="syntax"></a>語法  
  
```xml  
<para>content</para>  
```  
  
#### <a name="parameters"></a>參數  
 `content`  
 段落的文字。  
  
## <a name="remarks"></a>備註  
 `<para>`標記是供使用的標記內，例如[\<摘要 >](../../../visual-basic/language-reference/xmldoc/summary.md)， [\<備註 >](../../../visual-basic/language-reference/xmldoc/remarks.md)，或[\<傳回 >](../../../visual-basic/language-reference/xmldoc/returns.md)，可讓您加入至文字的結構。  
  
 編譯搭配 [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) 可處理檔案的文件註解。  
  
## <a name="example"></a>範例  
 這個範例會使用`<para>`分割的 remarks 區段標記`UpdateRecord`方法分成兩個段落。  
  
 [!code-vb[VbVbcnXmlDocComments#6](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/para_1.vb)]  
  
## <a name="see-also"></a>另請參閱  
 [XML 註解標記](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md)
