---
title: 递归函数：rec 关键字 (F#)
description: '了解如何 F # 建议关键字用于使用 let 关键字定义的递归函数。'
ms.date: 05/16/2016
ms.openlocfilehash: 6039a48eae2b16aa1d82617176460d727a878d87
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="recursive-functions-the-rec-keyword"></a>递归函数：rec 关键字

`rec`连同使用关键字`let`关键字来定义的递归函数。


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
递归函数，自身，调用的函数进行显式标识的 F # 语言。 这使正在定义的标识符可在该函数的作用域。

下面的代码演示计算的递归函数*n*第斐波那契数。

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet4001.fs)]

>[!NOTE]
在实践中，上面这类代码是一种浪费的内存和处理器时间，因为它涉及的以前计算的值重新计算功能。


方法是隐式类型; 中的递归无需添加`rec`关键字。 类中的 let 的绑定不是隐式递归。


## <a name="mutually-recursive-functions"></a>相互递归函数
有时函数是*相互递归*，这意味着调用形成了循环，其中一个函数调用另后者又包含任意数量的调用将调用第一个之间。 你必须在一个一起定义此类函数`let`绑定，使用`and`关键字来将它们链接在一起。

下面的示例显示了两个相互递归函数。

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet4002.fs)]

## <a name="see-also"></a>请参阅
[函数](index.md)
