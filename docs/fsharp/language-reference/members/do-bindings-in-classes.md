---
title: 类中的 do 绑定 (F#)
description: '了解如何使用 F # do 在类定义中，该对象构造时或者如果第一次使用类型执行操作的绑定。'
ms.date: 05/16/2016
ms.openlocfilehash: 779b33c44b1518135f4c7f270173ec8124fec101
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="do-bindings-in-classes"></a>类中的 do 绑定

A`do`类定义中的绑定操作时，对象构造或者执行，对于静态`do`绑定，当类型是首次使用。


## <a name="syntax"></a>语法

```fsharp
[static] do expression
```

## <a name="remarks"></a>备注
A`do`绑定出现连同或之后`let`绑定但之前的类定义中的成员定义。 尽管`do`关键字是可选的`do`绑定在模块级别中，为不可选`do`类定义中的绑定。

有关构造的每个对象的任何给定类型，非静态`do`绑定和非静态`let`绑定执行类定义中出现的顺序。 多个`do`绑定可以出现在一个类型。 非静态`let`绑定和非静态`do`绑定成为主构造函数的主体。 中非静态的代码`do`主构造函数参数和任何值或定义中的函数，可以引用绑定部分`let`绑定部分。

非静态`do`绑定可以访问类的成员，只要类具有定义的自我标识符`as`类列名，和，只要这些成员的所有使用都限定为类的自我标识符中的关键字。

因为`let`绑定初始化的私有字段的一个类，这通常是为保证成员正常工作所必需的`do`绑定通常置于后`let`绑定中的代码以便`do`绑定可以执行完全初始化的对象。 如果你的代码尝试使用成员之前初始化已完成，将引发 InvalidOperationException。

静态`do`绑定可以引用静态成员或字段的封闭类，但不是实例成员或字段。 静态`do`绑定成为类，该类可保证执行之前第一次使用类的静态初始值设定项的一部分。

属性为忽略`do`类型中的绑定。 如果属性是必需中执行的代码的`do`绑定，它必须将应用于主构造函数。

在下面的代码中，类具有静态`do`绑定和非静态`do`绑定。 该对象具有具有两个参数的构造函数`a`和`b`，并且两个私有字段将在定义`let`类的绑定。 此外定义了两个属性。 所有这些都在非静态的范围内`do`绑定部分中，将所有这些值输出的行所示。

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3101.fs)]

输出如下所示。

```console
Initializing MyType.
Initializing object 1 2 2 4 8 16
```

## <a name="see-also"></a>请参阅
[成员](index.md)

[类](../classes.md)

[构造函数](constructors.md)

[类中的 `let` 绑定](let-bindings-in-classes.md)

[`do` 绑定](../functions/do-Bindings.md)
