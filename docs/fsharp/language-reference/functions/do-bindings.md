---
title: do 绑定
description: 了解如何F#do 绑定用于执行代码而无需定义的函数或值。
ms.date: 05/16/2016
ms.openlocfilehash: d29f8557fda06097d2e85748ab6286f0415730b3
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61683374"
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