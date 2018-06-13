---
title: 异常：invalidArg 函数 (F#)
description: '了解如何 F # invalidArg 函数生成参数异常。'
ms.date: 05/16/2016
ms.openlocfilehash: 43e1b6f3f36774ac50aeff147f75f133d6e3e5dc
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33564503"
---
# <a name="exceptions-the-invalidarg-function"></a>异常：invalidArg 函数

`invalidArg`函数将生成自变量异常。


## <a name="syntax"></a>语法

```fsharp
invalidArg parameter-name error-message-string
```

## <a name="remarks"></a>备注
在上述语法中的参数名称是参数的带有其自变量无效的名称的字符串。 *错误消息字符串*是一个文本字符串或类型的值`string`。 它将成为`Message`异常对象的属性。

生成的异常`invalidArg`是`System.ArgumentException`异常。 下面的代码演示如何使用`invalidArg`引发异常。

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet6101.fs)]

输出为以下内容，然后由堆栈跟踪 （未显示）。

```
December
January
System.ArgumentException: Month parameter out of range.
```

## <a name="see-also"></a>请参阅
[异常处理](index.md)

[异常类型](exception-types.md)

[异常：`try...with` 表达式](the-try-with-expression.md)

[异常：`try...finally` 表达式](the-try-finally-expression.md)

[异常：`raise` 函数](the-raise-function.md)

[异常：`failwith` 函数](the-failwith-function.md)
