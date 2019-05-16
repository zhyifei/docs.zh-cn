---
title: 异常类型
description: 了解如何定义和使用F#异常类型。
ms.date: 05/16/2016
ms.openlocfilehash: b7203dc042c7207bca95cfd0372790bfe52e0226
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/15/2019
ms.locfileid: "65645567"
---
# <a name="exception-types"></a>异常类型

有两个类别中的异常的F#:.NET 异常类型和F#异常类型。 本主题介绍如何定义和使用F#异常类型。

## <a name="syntax"></a>语法

```fsharp
exception exception-type of argument-type
```

## <a name="remarks"></a>备注

在上述语法中，*异常类型*的新名称F#异常类型和*自变量类型*表示当引发此类型的异常时，可以提供的参数的类型。 可以使用的元组类型来指定多个自变量*自变量类型*。

典型定义F#异常将如下所示。

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet5501.fs)]

可以使用生成此类型的异常`raise`函数，请按如下所示。

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet5502.fs)]

可以使用F#直接在中的筛选器中的异常类型`try...with`表达式，如下面的示例中所示。

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet5503.fs)]

使用定义的异常类型`exception`中的关键字F#是一种新类型，继承自`System.Exception`。

## <a name="see-also"></a>请参阅

- [异常处理](index.md)
- [异常：`raise` 函数](the-raise-function.md)
- [异常层次结构](https://msdn.microsoft.com/library/z4c5tckx.aspx)
