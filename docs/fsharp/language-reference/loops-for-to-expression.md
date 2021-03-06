---
title: 迴圈：for...to 運算式 (F#)
description: '請參閱如何 F # for...in..運算式用來在迴圈中反覆迴圈變數的值範圍。'
ms.date: 05/16/2016
ms.openlocfilehash: 841c7d557abc11e0253cb87ab8081cc77671b44b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/04/2018
---
# <a name="loops-forto-expression"></a>迴圈：for...to 運算式

`for...to`運算式用來在迴圈中反覆查看的迴圈變數的值範圍。


## <a name="syntax"></a>語法

```fsharp
for identifier = start [ to | downto ] finish do
    body-expression
```

## <a name="remarks"></a>備註
識別項的類型推斷的型別*啟動*和*完成*運算式。 這些運算式的類型必須是 32 位元整數。

雖然技術上的運算式，`for...to`則更像命令式的程式語言中的傳統陳述式。 傳回型別*主體運算式*必須`unit`。 下列範例顯示的各種用法`for...to`運算式。

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5101.fs)]

上述程式碼的輸出如下。

```
1 2 3 4 5 6 7 8 9 10
10 9 8 7 6 5 4 3 2 1
2 3 4 5 6 7 8 9 10 11 12 13 14 15 16 17 18
```

## <a name="see-also"></a>另請參閱
[F# 語言參考](index.md)

[迴圈：`for...in` 運算式](loops-for-in-expression.md)

[迴圈：`while...do` 運算式](loops-while-do-expression.md)
