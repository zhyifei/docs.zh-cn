---
title: 对象表达式 (F#)
description: '了解如何使用 F # 对象表达式，如果你想要避免额外的代码和创建一个新的所需的开销命名类型。'
ms.date: 05/16/2016
ms.openlocfilehash: fed78e2be52838eedf55759b195696f1210a8a20
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="object-expressions"></a>对象表达式

*对象表达式*表达式，用于创建动态创建、 匿名对象类型的新实例，根据现有的基类型、 接口或组的接口。


## <a name="syntax"></a>语法

```fsharp
// When typename is a class:
{ new typename [type-params]arguments with
    member-definitions
    [ additional-interface-definitions ]
}
// When typename is not a class:
{ new typename [generic-type-args] with
    member-definitions
    [ additional-interface-definitions ]
}
```

## <a name="remarks"></a>备注
在上述语法中， *typename*表示的现有类类型或接口类型。 *类型参数*介绍可选的泛型类型参数。 *参数*仅用于类类型，需要构造函数参数。 *成员定义*替代基类方法或抽象方法从基类或接口的实现。

下面的示例阐释了多种不同类型的对象表达式。

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4301.fs)]

## <a name="using-object-expressions"></a>使用对象表达式
当你想要避免额外的代码和所需创建一个新的名为类型的开销时，您可以使用对象表达式。 如果您使用对象表达式来创建在程序中的类型的数量降至最低，可以减少的代码的行数，并防止不必要的迅速普及的类型。 而不是创建许多类型只是为了处理的特定情况下，你可以使用自定义现有类型或为特定用例手头提供正确地实现接口的对象表达式。


## <a name="see-also"></a>请参阅
[F# 语言参考](index.md)
