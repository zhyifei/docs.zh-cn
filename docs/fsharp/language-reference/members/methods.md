---
title: 方法
description: 了解 F# 方法如何与用于公开和实现对象和类型的功能和行为的类型关联的函数。
ms.date: 11/04/2019
ms.openlocfilehash: 6f5ae76ea450b07763eb58d0c95b18b30f634551
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/14/2020
ms.locfileid: "79401063"
---
# <a name="methods"></a>方法

*方法*是与类型关联的函数。 在面向对象的编程中，使用方法公开和实现对象和类型的功能和行为。

## <a name="syntax"></a>语法

```fsharp
// Instance method definition.
[ attributes ]
member [inline] self-identifier.method-name parameter-list [ : return-type ] =
    method-body

// Static method definition.
[ attributes ]
static member [inline] method-name parameter-list [ : return-type ] =
    method-body

// Abstract method declaration or virtual dispatch slot.
[ attributes ]
abstract member method-name : type-signature

// Virtual method declaration and default implementation.
[ attributes ]
abstract member method-name : type-signature
[ attributes ]
default self-identifier.method-name parameter-list [ : return-type ] =
    method-body

// Override of inherited virtual method.
[ attributes ]
override self-identifier.method-name parameter-list [ : return-type ] =
    method-body

// Optional and DefaultParameterValue attributes on input parameters
[ attributes ]
[ modifier ] member [inline] self-identifier.method-name ([<Optional; DefaultParameterValue( default-value )>] input) [ : return-type ]
```

## <a name="remarks"></a>备注

在前面的语法中，您可以看到各种形式的方法声明和定义。 在较长的方法实体中，换行符遵循等号 （*），整个方法体缩进。

属性可以应用于任何方法声明。 它们先于方法定义的语法，通常列在单独的行上。 有关更多信息，请参阅[特性](../attributes.md)。

可以标记`inline`方法。 有关 `inline` 的信息，请参阅[内联函数](../functions/inline-functions.md)。

非内联方法可以在类型中递归使用;无需显式使用 关键字`rec`。

## <a name="instance-methods"></a>实例方法

实例方法使用`member`关键字和*自标识符*声明，后跟句点 （.） 和方法名称和参数。 与绑定的情况`let`一样，*参数列表*可以是一种模式。 通常，将方法参数以元组形式包裹在括号中，这是方法在其他 .NET Framework 语言中创建时在 F# 中显示的方法。 但是，咖喱形式（由空格分隔的参数）也很常见，并且还支持其他模式。

下面的示例说明了非抽象实例方法的定义和使用。

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet3401.fs)]

在实例方法中，不要使用自标识符访问使用 let 绑定定义的字段。 访问其他成员和属性时，请使用自标识符。

## <a name="static-methods"></a>静态方法

关键字`static`用于指定可以在没有实例的情况下调用方法，并且不与对象实例关联。 否则，方法是实例方法。

下一节中的示例显示使用 关键字声明的`let`字段、使用`member`关键字声明的属性成员以及用 关键字声明的`static`静态方法。

下面的示例说明了静态方法的定义和使用。 假设这些方法定义位于上一节中的`SomeType`类中。

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet3402.fs)]

## <a name="abstract-and-virtual-methods"></a>抽象方法和虚方法

关键字`abstract`指示方法具有虚拟调度槽，并且类中可能没有定义。 *虚拟调度槽*是内部维护的函数表中的条目，用于在运行时查找面向对象的类型的虚拟函数调用。 虚拟调度机制是实现*多态性的*机制，是面向对象编程的一个重要特征。 至少有一个没有定义的抽象方法的类是*抽象类*，这意味着不能创建该类的实例。 有关抽象类的详细信息，请参阅[抽象类](../abstract-classes.md)。

抽象方法声明不包括方法体。 相反，方法的名称后跟冒号 （:)和 方法的类型签名。 方法的类型签名与 IntelliSense 在 Visual Studio 代码编辑器中将鼠标指针悬停在方法名称上时显示的签名相同，但没有参数名称。 当您以交互方式工作时，解释器 fsi.exe 也会显示类型签名。 方法的类型签名是通过列出参数的类型（后跟返回类型）以及适当的分隔符符号来形成的。 咖喱参数由 分隔`->`，元组参数由 分隔。 `*` 返回值始终由`->`符号与参数分隔。 括号可用于对复杂参数进行分组，例如当函数类型为参数时，或指示元组何时被视为单个参数而不是两个参数。

还可以通过将定义添加到类并使用`default`关键字来提供抽象方法默认定义，如本主题中的语法块所示。 在同一类中具有定义的抽象方法等效于其他 .NET Framework 语言中的虚拟方法。 无论定义是否存在，关键字都会`abstract`在类的虚拟函数表中创建一个新的调度槽。

无论基类是否实现其抽象方法，派生类都可以提供抽象方法的实现。 要在派生类中实现抽象方法，请定义派生类中具有相同名称和签名的方法，但使用`override`or`default`关键字除外，并提供方法正文。 关键字`override`和`default`含义完全相同的东西。 如果`override`新方法重写基类实现，请使用 ;在`default`与原始抽象声明相同的类中创建实现时使用。 不要在`abstract`实现基类中声明为抽象的方法上使用 关键字。

下面的示例演示了具有默认实现`Rotate`（等效于 .NET Framework 虚拟方法）的抽象方法。

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet3403.fs)]

下面的示例演示了重写基类方法的派生类。 在这种情况下，重写会更改行为，以便方法不执行任何操作。

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet3404.fs)]

## <a name="overloaded-methods"></a>重载方法

重载方法是给定类型中名称相同但参数不同的方法。 在 F# 中，通常使用可选参数而不是重载方法。 但是，在语言中允许重载方法，前提是参数以元组形式，而不是咖喱形式。

## <a name="optional-arguments"></a>可选实参

从 F# 4.1 开始，还可以在方法中具有具有默认参数值的可选参数。  这有助于促进 C# 代码的互操作。  下面的示例演示了语法：

```fsharp
// A class with a method M, which takes in an optional integer argument.
type C() =
    _.M([<Optional; DefaultParameterValue(12)>] i) = i + 1
```

请注意，传入`DefaultParameterValue`的值必须与输入类型匹配。  在上述示例中，它是 一个`int`。  尝试将非整数值传递到中`DefaultParameterValue`将导致编译错误。

## <a name="example-properties-and-methods"></a>示例：属性和方法

下面的示例包含一个类型，其中包含字段、私有函数、属性和静态方法的示例。

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet3406.fs)]

## <a name="see-also"></a>另请参阅

- [成员](index.md)
