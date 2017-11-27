---
title: "异常：failwith 函数 (F#)"
description: "了解如何 failwith 函数生成 F # 异常。"
keywords: "visual f#, f#, 函数编程"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 2e0c1f28-cc6c-4ecd-bb93-3816c4dd7cd3
ms.openlocfilehash: 295a4d754e0df015ba67daa9cf80d7df5b40199c
ms.sourcegitcommit: ffb9aa26cd5211dc6d96ebb42968d8357048880e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/09/2017
---
# <a name="exceptions-the-failwith-function"></a>异常：failwith 函数

`failwith`函数将生成 F # 异常。


## <a name="syntax"></a>语法

```fsharp
failwith error-message-string
```

## <a name="remarks"></a>备注
*错误消息字符串*在前面的语法是一个文本字符串或类型的值`string`。 它将成为`Message`该异常的属性。

由生成的异常`failwith`是`System.Exception`异常，这是一个引用，它具有名称`Failure`F # 代码中。 下面的代码演示如何使用`failwith`引发异常。

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet6001.fs)]
    
## <a name="see-also"></a>另请参阅
[异常处理](index.md)

[异常类型](exception-types.md)

[异常：`try...with` 表达式](the-try-with-expression.md)

[异常：`try...finally` 表达式](the-try-finally-expression.md)

[异常：`raise` 函数](the-raise-function.md)
