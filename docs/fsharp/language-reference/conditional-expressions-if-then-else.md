---
title: 条件表达式：if... then...else (F#)
description: '了解如何编写 F # 可执行代码的不同分支中的条件的表达式。'
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: dotnet-fsharp
ms.devlang: fsharp
ms.openlocfilehash: bfb985f09be91034894e1d3eba88cebef6bb3fd4
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2018
---
# <a name="conditional-expressions-ifthenelse"></a>条件表达式： `if...then...else`

`if...then...else`表达式运行代码的不同分支，还可以计算为不同的值，具体取决于给定的布尔表达式。


## <a name="syntax"></a>语法

```fsharp
if boolean-expression then expression1 [ else expression2 ]
```

## <a name="remarks"></a>备注
在上述语法中， *expression1*运行时的布尔表达式的计算结果为`true`; 否则为*expression2*运行。

与其他语言版本，`if...then...else`构造是一个表达式，而不是语句。 这意味着它生成一个值，即执行的分支中的最后一个表达式的值。 每个分支中生成的值的类型必须匹配。 如果没有显式`else`分支，其类型是`unit`。 因此，如果的一种`then`分支是任何类型，而不`unit`，必须有`else`分支以及相同的返回类型。 在将链接时`if...then...else`表达式组合在一起，可以使用关键字`elif`而不是`else if`; 它们是等效的。

## <a name="example"></a>示例
下面的示例演示如何使用`if...then...else`表达式。

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4501.fs)]

```
10 is less than 20
What is your name? John
How old are you? 9
You are only 9 years old and already learning F#? Wow!
```

## <a name="see-also"></a>请参阅
[F# 语言参考](index.md)

