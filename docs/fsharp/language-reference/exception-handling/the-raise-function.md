---
title: 异常：raise 函数 (F#)
description: '了解如何使用 F # 引发函数以指示已发生的错误或异常情况。'
ms.date: 05/16/2016
ms.openlocfilehash: bad18bfbccd738a12e16a0e026ade22e96d4cfcb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33564735"
---
# <a name="exceptions-the-raise-function"></a>异常：raise 函数

`raise`函数用于指示已发生的错误或异常情况。 在异常对象中捕获有关错误的信息。


## <a name="syntax"></a>语法

```fsharp
raise (expression)
```

## <a name="remarks"></a>备注
`raise`函数将生成的异常对象，并启动堆栈展开过程。 在堆栈展开过程是由公共语言运行时 (CLR) 托管，因此此进程的行为是相同因为它是任何其他.NET 语言中。 在堆栈展开过程是一个搜索匹配所生成的异常的异常处理程序。 在当前开始搜索`try...with`表达式，如果有一个。 在每个模式`with`按顺序块检查。 当找到匹配的异常处理程序时，将异常认为是已处理。否则，堆栈的展开和`with`直到找到匹配的处理，则检查调用链中向上的块。 任何`finally`当堆栈展开，按顺序还执行的调用链中遇到的块。

`raise`函数等同于`throw`C# 或 c + +。 使用`reraise`catch 处理程序来传播此同一异常向上的调用链中。

下面的代码示例阐释使用`raise`函数生成异常。

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet5801.fs)]

`raise`函数还可引发.NET 异常，如下面的示例中所示。

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet5802.fs)]
    
## <a name="see-also"></a>请参阅
[异常处理](index.md)

[异常类型](exception-types.md)

[异常：`try...with` 表达式](the-try-with-expression.md)

[异常：`try...finally` 表达式](the-try-finally-expression.md)

[异常：`failwith` 函数](the-failwith-function.md)

[异常：`invalidArg` 函数](the-invalidArg-function.md)
