---
title: 异常类型 (F#)
description: '了解如何定义和使用 F # 异常类型。'
ms.date: 05/16/2016
ms.openlocfilehash: b8d648a3649153a3604856deb61ce41db8c40bf2
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/06/2018
ms.locfileid: "43858816"
---
# <a name="exception-types"></a>异常类型

有两个类别的 F # 中的异常：.NET 异常类型和 F # 异常类型。 本主题介绍如何定义和使用 F # 异常类型。

## <a name="syntax"></a>语法

```fsharp
exception exception-type of argument-type
```

## <a name="remarks"></a>备注

在上述语法中，*异常类型*是新的 F # 异常类型、 名称和*自变量类型*表示当引发此类型的异常时，可以提供的参数的类型。 可以使用的元组类型来指定多个自变量*自变量类型*。

F # 异常的典型定义如下所示。

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet5501.fs)]

可以使用生成此类型的异常`raise`函数，请按如下所示。

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet5502.fs)]

您可以直接在筛选器中使用 F # 异常类型`try...with`表达式，如下面的示例中所示。

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet5503.fs)]

使用定义的异常类型`exception`F # 中的关键字是继承的新类型`System.Exception`。

## <a name="see-also"></a>请参阅

- [异常处理](index.md)
- [异常：`raise` 函数](the-raise-function.md)
- [异常层次结构](https://msdn.microsoft.com/library/z4c5tckx.aspx)
