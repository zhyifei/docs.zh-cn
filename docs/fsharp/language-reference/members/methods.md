---
title: 方法 (F#)
description: '了解如何与用于公开和实现的功能和行为的对象和类型的类型关联的函数的 F # 方法。'
ms.date: 05/16/2016
ms.openlocfilehash: 6cd354eaa4698bb194fd8fc04b09348e708cb0f8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="methods"></a>方法

A*方法*是一个函数，则与该类型关联。 在面向对象编程中，方法用于公开和实现的功能和行为的对象和类型。


## <a name="syntax"></a>语法

```fsharp
// Instance method definition.
[ attributes ]
member [inline] self-identifier.method-nameparameter-list [ : return-type ]=
    method-body

// Static method definition.
[ attributes ]
static member [inline] method-nameparameter-list [ : return-type ]=
    method-body

// Abstract method declaration or virtual dispatch slot.
[ attributes ]
abstract member self-identifier.method-name : type-signature

// Virtual method declaration and default implementation.
[ attributes ]
abstract member [inline] self-identifier.method-name : type-signature
[ attributes ]
default member [inline] self-identifier.method-nameparameter-list[ : return-type ] =
    method-body

// Override of inherited virtual method.
[ attributes ]
override member [inline] self-identifier.method-nameparameter-list [ : return-type ]=
    method-body

// Optional and DefaultParameterValue attributes on input parameters
[ attributes ]
[ modifier ] member [inline] self-identifier.method-name ([<Optional; DefaultParameterValue([ default-value ])>] input) [ : return-type ]
```

## <a name="remarks"></a>备注
在上述语法中，你可以看到各种形式的方法声明和定义。 在更长的方法体合并等号 （=） 后, 跟换行符和缩进整个方法体。

特性可以应用于任何方法声明中。 它们位于方法定义的语法，并且通常在单独的行上列出。 有关更多信息，请参阅[特性](../attributes.md)。

可以将方法标记为`inline`。 有关 `inline` 的信息，请参阅[内联函数](../functions/inline-functions.md)。

可以使用以递归方式在类型; 非内联的方法。没有无需显式使用`rec`关键字。


## <a name="instance-methods"></a>实例方法
实例方法声明与`member`关键字和*自我标识符*后, 跟一个句点 （.） 的方法名称和参数。 这种情况原样`let`绑定，*参数列表*可以是一种模式。 通常情况下，你括在圆括号中元组形式，即方式方法的参数出现的方法 F # 创建在其他.NET Framework 语言时。 但是，扩充窗体 （由空格分隔参数） 也很常见，并且还支持其他模式。

下面的示例阐释的定义和使用非抽象实例方法。

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3401.fs)]

实例方法内不要到由使用 let 的绑定定义的访问字段使用自我标识符。 访问其他成员和属性时，请使用自我标识符。


## <a name="static-methods"></a>静态方法
关键字`static`可用于指定一种方法，可以调用实例情况下并不是与对象实例相关联。 否则，方法是实例方法。

下一节中的示例演示使用声明的字段`let`关键字，使用声明的属性成员`member`关键字，然后使用声明的静态方法`static`关键字。

下面的示例阐释的定义和使用静态方法。 假定这些方法定义中`SomeType`上一节中的类。

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3402.fs)]

## <a name="abstract-and-virtual-methods"></a>抽象方法和虚方法
关键字`abstract`表示一种方法是具有虚拟调度槽，可能没有一个定义的类中。 A*虚拟调度槽*是面向对象的类型中的调用在运行时中用于查找虚函数的函数的内部维护表中的条目。 虚拟调度机制是实现的机制*多态性*，面向对象的编程的一个重要功能。 具有至少一个抽象方法没有定义的类是*抽象类*，这意味着该类的情况下，可以创建任何实例。 有关抽象类的详细信息，请参阅[抽象类](../abstract-classes.md)。

抽象方法声明不包含方法体。 相反，该方法的名称后跟一个冒号 （:） 和方法的类型签名。 一种方法的类型签名是所示 intellisense，当你将鼠标指针悬停方法名称在 Visual Studio 代码编辑器中，除不使用参数名称相同。 当您正在以交互方式，解释器，fsi.exe，也会显示类型签名。 方法的类型签名格式则为 out 参数，返回类型，使用适当的分隔符符号后跟类型的列表。 扩充的参数由分隔`->`元组参数隔开`*`。 返回值始终从由自变量分隔`->`符号。 可以使用括号，组复杂的参数，如当一种函数类型是一个参数，或者以指示当元组将被视为单个参数，而不是两个参数。

此外可以为抽象方法默认定义通过向类添加定义和使用`default`关键字，如本主题中的语法块中所示。 具有同一类中定义一个抽象方法相当于其他.NET Framework 语言中的虚拟方法。 定义是否存在，`abstract`关键字虚函数表类中创建一个新的调度槽。

无论是否基类实现其抽象方法，派生的类可以提供抽象方法的实现。 若要实现派生类中的一个抽象方法，定义一个方法在派生类中，除使用具有相同名称和签名`override`或`default`关键字，并提供方法体。 关键字`override`和`default`意味着完全相同的目标。 使用`override`的新方法重写的基类实现; 如果使用`default`当你创建与原始的抽象声明相同的类中实现。 不要使用`abstract`实现抽象基类中声明的方法的方法上关键字。

下面的示例演示一个抽象方法`Rotate`、 具有默认实现，.NET Framework 虚方法的等效项。

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3403.fs)]

下面的示例阐释派生的类重写基类方法。 在这种情况下，重写更改行为，以便该方法不执行任何操作。

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3404.fs)]

## <a name="overloaded-methods"></a>重载方法
重载的方法是在给定类型中具有相同名称但具有不同的自变量的方法。 在 F # 中，可选自变量通常使用而不是重载方法。 但是，重载的方法允许在语言中，自变量中的元组形式，不是扩充形式。

## <a name="optional-arguments"></a>可选实参

F # 4.1 开始，你还可以使用默认参数值的可选自变量在方法中。  这是为了帮助实现包含 C# 代码间的互操作。  下面的示例演示的语法：

```fsharp
// A class with a method M, which takes in an optional integer argument.
type C() =
    __.M([<Optional; DefaultParameterValue(12)>] i) = i + 1
```

请注意，传递的值时为`DefaultParameterValue`必须匹配的输入的类型。  在上面的示例中，它是`int`。  尝试传递非整数值转换为`DefaultParameterValue`将导致编译错误。

## <a name="example-properties-and-methods"></a>示例： 属性和方法
下面的示例包含具有字段、 私有函数、 属性和静态方法的示例的类型。

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3406.fs)]

## <a name="see-also"></a>请参阅
[成员](index.md)
