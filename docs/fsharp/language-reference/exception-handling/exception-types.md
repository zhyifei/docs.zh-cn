---
title: 异常类型
description: 了解如何定义和使用F#异常类型。
ms.date: 05/16/2016
ms.openlocfilehash: 8545fab50ff6338d1f1621710a838a200f9ac705
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/30/2019
ms.locfileid: "68630309"
---
# <a name="exception-types"></a>异常类型

中F#有两类异常: .net 异常类型和F#异常类型。 本主题介绍如何定义和使用F#异常类型。

## <a name="syntax"></a>语法

```fsharp
exception exception-type of argument-type
```

## <a name="remarks"></a>备注

在前面的语法中, *exception 类型*是新F#异常类型的名称,*参数类型*表示在引发此类型的异常时可以提供的参数的类型。 您可以通过使用*参数类型*的元组类型指定多个参数。

F#异常的典型定义如下所示。

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5501.fs)]

您可以使用`raise`函数生成此类型的异常, 如下所示。

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5502.fs)]

您可以直接在F# `try...with`表达式的筛选器中使用异常类型, 如下面的示例中所示。

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5503.fs)]

使用中`exception` F#的关键字定义的异常类型是从`System.Exception`继承的新类型。

## <a name="see-also"></a>请参阅

- [异常处理](index.md)
- [异常：`raise` 函数](the-raise-function.md)
- [异常层次结构](https://msdn.microsoft.com/library/z4c5tckx.aspx)
