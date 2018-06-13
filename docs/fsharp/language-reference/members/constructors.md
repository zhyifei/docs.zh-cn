---
title: 构造函数 (F#)
description: '了解如何定义和使用 F # 中的构造函数来创建和初始化类和结构的对象。'
ms.date: 05/16/2016
ms.openlocfilehash: 1773c111e0398aa83951afe14979d8a4ebc4907f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33564428"
---
# <a name="constructors"></a>构造函数

本主题介绍如何定义和使用构造函数来创建和初始化类和结构的对象。


## <a name="construction-of-class-objects"></a>类对象的构造
类类型的对象具有构造函数。 有两种类型的构造函数。 其中一个是主构造函数，其参数之后的类型名称出现在括号内。 使用指定另一个可选的其他构造函数`new`关键字。 任何此类其他构造函数必须调用主构造函数。

主构造函数包含`let`和`do`出现在类定义开头的绑定。 A`let`绑定声明私有字段和类; 方法`do`绑定执行代码。 有关详细信息`let`绑定中类的构造函数，请参阅[`let`类中的绑定](let-bindings-in-classes.md)。 有关详细信息`do`绑定在构造函数，请参阅[`do`类中的绑定](do-bindings-in-classes.md)。

无论你想要调用的构造函数是具有主构造函数或其他构造函数，你可以通过创建对象`new`表达式，或不带可选`new`关键字。 你初始化对象构造函数自变量，通过列出自变量的顺序以及用逗号分隔并括在括号内，或在括号中使用命名自变量和值。 你还可以设置属性的对象的对象的构造过程使用的属性名称和分配值，就像使用名为构造函数自变量。

下面的代码演示具有一个构造函数和创建对象的各种方法的类。

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet3501.fs)]

输出如下所示。

```console
Initialized object that has coordinates (1, 2, 3)
Initialized object that has coordinates (4, 5, 6)
Initialized object that has coordinates (7, 8, 9)
Initialized object that has coordinates (0, 0, 0)
```

## <a name="construction-of-structures"></a>构造的结构
结构遵循类的所有的规则。 因此，你可以具有主构造函数，并可以使用来提供其他构造函数`new`。 但是，没有结构和类的一个重要区别： 结构可以具有默认构造函数 （即，一个不带任何参数），即使定义没有主构造函数。 默认构造函数初始化为该类型，通常是零或它的等效项的默认值的所有字段。 为结构定义任何构造函数必须具有至少一个参数，以便它们不与默认构造函数冲突。

此外，结构通常具有通过使用创建的字段`val`关键字; 类也有这些字段。 结构和具有通过使用定义的字段的类`val`关键字可以还在中初始化其他构造函数通过使用记录的表达式，如下面的代码中所示。

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet3502.fs)]

有关详细信息，请参阅[显式字段：`val`关键字](explicit-fields-the-val-keyword.md)。


## <a name="executing-side-effects-in-constructors"></a>在构造函数中执行的副作用
类中的具有主构造函数可以执行中的代码`do`绑定。 但是，如果你需要在其他构造函数，而不执行代码`do`绑定？ 若要执行此操作，请使用`then`关键字。

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet3503.fs)]

仍执行主构造函数的副作用。 因此，输出如下所示。

```console
Created a person object.
Created a person object.
Created an invalid person object.
```

## <a name="self-identifiers-in-constructors"></a>在构造函数中的自我标识符
其他成员，可以提供每个成员的定义中的当前对象的名称。 你还可将自我标识符置于类定义的第一行使用`as`紧跟构造函数参数的关键字。 下面的示例阐释了此语法。

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet3504.fs)]

在其他构造函数，你还可以定义自我标识符置于`as`后构造函数参数的子句。 下面的示例阐释了此语法。

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet3505.fs)]

当你尝试使用的对象，它已完全定义之前，会发生问题。 因此，自我标识符的使用可能导致编译器发出警告并插入其他检查，以确保之前初始化了对象，不会访问对象的成员。 你只应使用中的自我标识符`do`绑定主构造函数，或后`then`在其他构造函数中的关键字。

自我标识符的名称不一定要`this`。 它可以是任何有效的标识符。


## <a name="assigning-values-to-properties-at-initialization"></a>将值分配给在初始化属性
你也可以通过追加形式的赋值的列表中的初始化代码的类对象的属性分配值`property = value`到一个构造函数的自变量列表。 下面的代码示例对此进行了演示。

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet3506.fs)]

以下版本的前面的代码演示普通自变量，可选自变量和一个构造函数调用中的属性设置的组合。

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet3507.fs)]
    
## <a name="constructors-in-inherited-class"></a>中继承的类的构造函数
从具有构造函数的基类继承时, 你必须在继承子句中指定其自变量。 有关详细信息，请参阅[构造函数和继承](../inheritance.md#constructors-and-inheritance)。

## <a name="static-constructors-or-type-constructors"></a>静态构造函数或类型构造函数
除了指定用于创建对象，静态代码`let`和`do`绑定可以编写在执行之前类型首次用于执行初始化类型级别的类类型。 有关详细信息，请参阅[`let`类中的绑定](let-bindings-in-classes.md)和[`do`类中的绑定](do-bindings-in-classes.md)。

## <a name="see-also"></a>请参阅
[成员](index.md)
