---
title: new 運算子 (C# 參考)
ms.date: 03/15/2018
helpviewer_keywords:
- new operator keyword [C#]
ms.assetid: a212b697-a79b-4105-9923-1f7b108036e8
ms.openlocfilehash: 2ba3c574897ae5f1ec66e3810e23f0af74bd8872
ms.sourcegitcommit: 70c76a12449439bac0f7a359866be5a0311ce960
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/25/2018
ms.locfileid: "39243943"
---
# <a name="new-operator-c-reference"></a>new 運算子 (C# 參考)
用以建立物件及叫用建構函式。 例如:   
  
```csharp
Class1 obj  = new Class1();  
```  
  
 它也用來建立匿名型別的執行個體︰  
  
```csharp
var query = from cust in customers  
            select new { Name = cust.Name, Address = cust.PrimaryAddress };  
```  
  
 `new` 運算子也可以用來叫用實值型別的預設建構函式。 例如:   
  
```csharp
int i = new int();  
```  
  
 在前一個陳述式中，`i` 會初始化為 `0`，這是 `int` 型別的預設值。 此陳述式與下例效果相同：  
  
```csharp
int i = 0;  
```  
  
 如需預設值的完整清單，請參閱[預設值表](../../../csharp/language-reference/keywords/default-values-table.md)。  
  
 請記住，為 [struct](../../../csharp/language-reference/keywords/struct.md) 宣告預設建構函式是錯誤，因為每一個實值型別都有隱含的公用預設建構函式。 在結構型別上宣告參數化建構函式以設定其初始值是可能的，但只有需要預設值以外的值時才為必要。  
  
 實質型別物件 (如結構) 與參考型別物件 (如類別) 皆會自動終結，但實質型別物件會在其包含的內容終結時終結，而參考型別物件則會在以其為目標的上一個參考移除時，在非指定時間由記憶體回收行程終結。 對於包含檔案處理常式或網路連線等資源的類型而言，最好採用確定性清除來確保其包含的資源盡早釋出。 如需詳細資訊，請參閱[使用陳述式](../../../csharp/language-reference/keywords/using-statement.md)。  
  
 無法多載 `new` 運算子。  
  
 如果 `new` 運算子無法配置記憶體，則會擲回例外狀況 <xref:System.OutOfMemoryException>。  
  
## <a name="example"></a>範例  
 下例使用 `new` 運算子建立並初始化 `struct` 物件和類別物件，然後為物件指派值。 顯示預設值和指派的值。  
  
 [!code-csharp[csrefKeywordsOperator#7](codesnippet/CSharp/new-operator_1.cs)]  
  
 請注意，範例中的字串預設值是 `null`。 因此，不會顯示。  
  
## <a name="c-language-specification"></a>C# 語言規格  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>請參閱  
 [C# 參考](../../../csharp/language-reference/index.md)  
 [C# 程式設計指南](../../../csharp/programming-guide/index.md)  
 [C# 關鍵字](../../../csharp/language-reference/keywords/index.md)  
 [運算子關鍵字](../../../csharp/language-reference/keywords/operator-keywords.md)  
 [new](../../../csharp/language-reference/keywords/new.md)  
 [匿名類型](../../../csharp/programming-guide/classes-and-structs/anonymous-types.md)
