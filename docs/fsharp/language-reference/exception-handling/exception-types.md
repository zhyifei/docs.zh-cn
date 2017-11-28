---
title: "异常类型 (F#)"
description: "了解如何定义和使用 F # 异常类型。"
keywords: "visual f#, f#, 函数编程"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: e850205a-b8da-459e-8f6d-cb3510f8f173
ms.openlocfilehash: a0864218841396c0ebdf26c7585e0e5bb778f83e
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="exception-types"></a>异常类型

有两个类别的 F # 中的异常：.NET 异常类型和 F # 异常类型。 本主题介绍如何定义和使用 F # 异常类型。


## <a name="syntax"></a>语法

```fsharp
exception exception-type of argument-type
```

## <a name="remarks"></a>备注
在上述语法中，*异常类型*是新的 F # 异常类型，名称和*自变量类型*表示时引发此类型的异常可以提供自变量的类型。 你可以使用的元组类型来指定多个自变量*自变量类型*。

F # 异常的典型定义如下所示。

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet5501.fs)]

你可以通过使用生成此类型的异常`raise`函数，如下。

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet5502.fs)]

你可以在中的筛选器中直接使用 F # 异常类型`try...with`表达式，如下面的示例中所示。

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet5503.fs)]

使用定义的异常类型`exception`F # 中的关键字是一种新类型，继承自`System.Exception`。


## <a name="see-also"></a>另请参阅
[异常处理](index.md)

[异常：`raise` 函数](the-raise-function.md)

[异常层次结构](https://msdn.microsoft.com/library/z4c5tckx.aspx)
