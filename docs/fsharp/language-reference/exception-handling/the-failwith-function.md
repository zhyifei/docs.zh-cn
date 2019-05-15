---
title: 异常:failwith 函数
description: 了解如何为 failwith 函数生成F#异常。
ms.date: 05/16/2016
ms.openlocfilehash: 08107966ddc2f55625347deb92d224b286df7761
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/15/2019
ms.locfileid: "65641950"
---
# <a name="exceptions-the-failwith-function"></a>异常:failwith 函数

`failwith`函数生成F#异常。

## <a name="syntax"></a>语法

```fsharp
failwith error-message-string
```

## <a name="remarks"></a>备注

*错误消息字符串*在上述语法中是一个文本字符串或类型的值`string`。 它将成为`Message`异常属性。

由生成的异常`failwith`是`System.Exception`异常，它是具有名称的引用`Failure`在F#代码。 下面的代码演示如何使用`failwith`引发异常。

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet6001.fs)]

## <a name="see-also"></a>请参阅

- [异常处理](index.md)
- [异常类型](exception-types.md)
- [异常：`try...with`表达式](the-try-with-expression.md)
- [异常：`try...finally`表达式](the-try-finally-expression.md)
- [异常：`raise` 函数](the-raise-function.md)
