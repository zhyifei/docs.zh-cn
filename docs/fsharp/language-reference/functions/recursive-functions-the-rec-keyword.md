---
title: 递归函数：rec 关键字 (F#)
description: '了解如何使用 let 关键字使用 F # rec 关键字定义的递归函数。'
ms.date: 05/16/2016
ms.openlocfilehash: 5aab6ed8ab0fc3c0f0bcfc93c3ce6518ec53254f
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/29/2018
ms.locfileid: "47456098"
---
# <a name="recursive-functions-the-rec-keyword"></a>递归函数：rec 关键字

`rec`一起使用关键字`let`关键字来定义的递归函数。

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

递归函数，函数调用自身，F # 语言中显式标识。 这使正在定义的标识符可在函数的作用域中。

以下代码演示了递归函数，用于计算*n*<sup>th</sup>斐波纳契数。

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet4001.fs)]

>[!NOTE]
在实践中，上面这类代码是一种浪费的内存和处理器时间，因为它涉及的以前计算的值重新计算。

方法是隐式类型; 中递归无需添加`rec`关键字。 类中的 let 的绑定不是隐式递归。

## <a name="mutually-recursive-functions"></a>相互递归函数

函数是有时*相互递归*，这意味着调用形成了循环，其中一个函数调用另一个后者又调用第一个具有任意数量的调用之间。 您必须在一个一起定义此类函数`let`使用的绑定`and`关键字来将它们链接在一起。

下面的示例演示两个相互递归函数。

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet4002.fs)]

## <a name="see-also"></a>请参阅

- [函数](index.md)
