---
title: "异常：try...finally 表达式 (F#)"
description: "了解如何使用 F # try … 最后表达式使您能够执行清理代码，即使的代码块将引发异常。"
keywords: "visual f#, f#, 函数编程"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: af06b20c-8d87-4496-a0aa-6fdfe8b3a786
ms.openlocfilehash: 2e2445c42bf8129ea81beef56cb725ac0e37d202
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="exceptions-the-tryfinally-expression"></a>异常：try...finally 表达式

`try...finally`表达式使您能够执行清理代码，即使的代码块将引发异常。


## <a name="syntax"></a>语法

```fsharp
try
    expression1
finally
    expression2
```

## <a name="remarks"></a>备注
`try...finally`表达式可以用于执行中的代码*expression2*在前面的语法而不考虑是否在执行期间生成异常*expression1*。

一种*expression2*不影响整个表达式; 的值返回时不会发生异常的类型是中的最后一个值*expression1*。 在异常确实发生，不返回任何值，并控制流将传输到下一步的匹配异常处理程序调用堆栈中向上。 如果找到没有异常处理程序，则程序终止。 执行匹配的处理程序中的代码或者程序终止中的代码之前`finally`执行分支。

下面的代码演示如何使用`try...finally`表达式。

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet5701.fs)]

向控制台输出如下所示。

```
Closing stream
Exception handled.
```

正如您可以看到输出中，在流关闭之前在外部异常已处理，和文件`test.txt`包含文本`test1`，指示已刷新缓冲区，并已将其写入到磁盘即使异常传输控制到外部异常处理程序。

请注意，`try...with`构造为单独从`try...finally`构造。 因此，如果你的代码同时需要`with`块和一个`finally`块中，你必须将嵌套的两个构造，如下面的代码示例所示。

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet5702.fs)]

在上下文中计算表达式，包括序列表达式和异步工作流， **try … 最后**表达式可能有一个自定义实现。 有关详细信息，请参阅[计算表达式](../computation-expressions.md)。


## <a name="see-also"></a>另请参阅
[异常处理](index.md)

[异常：`try...with` 表达式](the-try-with-expression.md)
