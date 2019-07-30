---
title: 异常：invalidArg 函数
description: 了解F# "invalidArg" 函数如何生成自变量异常。
ms.date: 05/16/2016
ms.openlocfilehash: 010dbfe313f539093b4ee7a19984ef54500b072d
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/30/2019
ms.locfileid: "68630305"
---
# <a name="exceptions-the-invalidarg-function"></a>异常：invalidArg 函数

`invalidArg`函数生成参数异常。

## <a name="syntax"></a>语法

```fsharp
invalidArg parameter-name error-message-string
```

## <a name="remarks"></a>备注

前面的语法中的参数名称是一个字符串, 其参数的名称无效。 *错误消息字符串*是文本字符串或类型`string`的值。 它将成为`Message`异常对象的属性。

生成`invalidArg`的异常是一个`System.ArgumentException`异常。 下面的代码演示`invalidArg`如何使用来引发异常。

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet6101.fs)]

输出如下所示, 后跟堆栈跟踪 (未显示)。

```
December
January
System.ArgumentException: Month parameter out of range.
```

## <a name="see-also"></a>请参阅

- [异常处理](index.md)
- [异常类型](exception-types.md)
- [异常：`try...with`表达式](the-try-with-expression.md)
- [异常：`try...finally`表达式](the-try-finally-expression.md)
- [异常：`raise` 函数](the-raise-function.md)
- [异常：`failwith`函数](the-failwith-function.md)
