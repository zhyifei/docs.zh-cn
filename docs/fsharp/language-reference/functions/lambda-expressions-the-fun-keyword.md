---
title: "Lambda 表达式：fun 关键字 (F#)"
description: "了解如何使用 F # 的有趣关键字定义 lambda 表达式，这是一个匿名函数。"
keywords: "visual f#, f#, 函数编程"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: e5d3565c-d7cc-433f-a619-886ed92523a7
ms.openlocfilehash: 09f1c1787bbb4b86ec40f9e973e08104919631aa
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="lambda-expressions-the-fun-keyword-f"></a>Lambda 表达式：fun 关键字 (F#)

`fun`关键字用于定义 lambda 表达式，即一个匿名函数。


## <a name="syntax"></a>语法

```fsharp
fun parameter-list -> expression
```

## <a name="remarks"></a>备注
*参数列表*通常由名称和参数类型，（可选） 组成。 一般来说，*参数列表*可由任何 F # 模式组成。 有关可能模式的完整列表，请参阅[模式匹配](../pattern-matching.md)。 有效参数列表包含下面的示例。

```fsharp
// Lambda expressions with parameter lists.
fun a b c -> ...
fun (a: int) b c -> ...
fun (a : int) (b : string) (c:float) -> ...

// A lambda expression with a tuple pattern.
fun (a, b) -> …

// A lambda expression with a list pattern.
fun head :: tail -> …
```

*表达式*是的函数，其中的最后一个表达式将生成一个返回值的正文。 有效的 lambda 表达式的示例包括：

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet301.fs)]
    
## <a name="using-lambda-expressions"></a>使用 Lambda 表达式
如果你想要对列表或其他集合执行操作并想要避免定义函数的额外工作，lambda 表达式是特别有用。 许多 F # 库函数采用函数值作为参数，而且还会特别方便在这些情况下使用 lambda 表达式。 下面的代码将 lambda 表达式应用于列表中的元素。 在这种情况下，匿名函数将 1 添加到列表中的每个元素。

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet302.fs)]
    
## <a name="see-also"></a>另请参阅
[函数](index.md)
