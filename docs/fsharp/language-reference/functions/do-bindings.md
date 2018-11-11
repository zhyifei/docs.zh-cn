---
title: do 绑定 (F#)
description: 了解如何将 F# do 绑定用来执行代码而无需定义的函数或值。
ms.date: 05/16/2016
ms.openlocfilehash: 78dbf8da0fe40b5af566ad98693df1109eede7e4
ms.sourcegitcommit: db8b83057d052c1f9f249d128b08d4423af0f7c2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/02/2018
ms.locfileid: "45973139"
---
# <a name="do-bindings"></a>do 绑定

一个`do`绑定用于执行代码而无需定义的函数或值。 此外，不要绑定可以是在类中使用，请参阅[`do`类中的绑定](../members/do-bindings-in-classes.md)。

## <a name="syntax"></a>语法

```fsharp
[ attributes ]
[ do ]expression
```

## <a name="remarks"></a>备注

使用`do`绑定时要执行独立于函数或值定义的代码。 中的表达式`do`绑定必须返回`unit`。 中的顶级代码`do`初始化模块时执行绑定。 关键字`do`是可选的。

特性可以应用于顶级`do`绑定。 例如，如果程序使用 COM 互操作，你可能想要应用`STAThread`属性到你的程序。 要做到这一点上使用属性`do`绑定，如下面的代码中所示。

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet201.fs)]

## <a name="see-also"></a>请参阅

- [F# 语言参考](../index.md)
- [函数](index.md)
