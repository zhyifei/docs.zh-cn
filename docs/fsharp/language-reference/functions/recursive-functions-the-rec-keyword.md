---
title: 递归函数:Rec 关键字
description: 了解如何将F# "rec" 关键字与 "let" 关键字一起使用, 以定义递归函数。
ms.date: 05/16/2016
ms.openlocfilehash: 7edaa7206b2109c7b1a405624b9b2330968f9c52
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/30/2019
ms.locfileid: "68630652"
---
# <a name="recursive-functions-the-rec-keyword"></a>递归函数:Rec 关键字

`rec` 关键字`let`与关键字一起用于定义递归函数。

## <a name="syntax"></a>语法

```fsharp
// Recursive function:
let rec function-nameparameter-list =
function-body

// Mutually recursive functions:
let rec function1-nameparameter-list =
function1-body
and function2-nameparameter-list =
function2-body
...
```

## <a name="remarks"></a>备注

递归函数 (调用自身的函数) 是在F#语言中显式标识的。 这会使正在定义的标识符在函数作用域内可用。

下面的代码演示了计算<sup>第</sup> *n*个斐波那契数的递归函数。

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet4001.fs)]

> [!NOTE]
> 在实践中, 类似于上面的代码会浪费内存和处理器时间, 因为它涉及到重新计算以前计算的值。

方法在类型内隐式递归;无需添加`rec`关键字。 类中的 Let 绑定不隐式递归。

## <a name="mutually-recursive-functions"></a>相互递归函数

有时, 函数是*相互递归*的, 这意味着, 调用会形成一个圆圈, 其中一个函数调用另一个函数, 而后者又调用第一个, 并在之间进行任意数量的调用。 必须在一个`let`绑定中一起定义此类函数, `and`使用关键字将它们链接在一起。

下面的示例演示两个相互递归函数。

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet4002.fs)]

## <a name="see-also"></a>请参阅

- [函数](index.md)
