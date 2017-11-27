---
title: "类 (F#)"
description: "了解如何表示可以具有属性、 方法和事件的对象的类型 F # 类。"
keywords: "visual f#, f#, 函数编程"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: d58679d5-7753-4b3b-a12f-6e9f00ed5ba3
ms.openlocfilehash: 2a73baba1f7c1b0d3bd09d22c9d6d9f0524daef3
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="classes"></a>类

*类*是表示可以具有属性、 方法和事件的对象的类型。


## <a name="syntax"></a>语法

```fsharp
// Class definition:
type [access-modifier] type-name [type-params] [access-modifier] ( parameter-list ) [ as identifier ] =
[ class ]
[ inherit base-type-name(base-constructor-args) ]
[ let-bindings ]
[ do-bindings ]
member-list
...
[ end ]
// Mutually recursive class definitions:
type [access-modifier] type-name1 ...
and [access-modifier] type-name2 ...
...
```

## <a name="remarks"></a>备注
类表示.NET 对象类型; 的基本说明此类是在 F # 支持面向对象编程的主要类型概念。

在前面的语法中，`type-name`是任何有效的标识符。 `type-params`介绍可选的泛型类型参数。 它包含的类型参数名称和括在尖括号中的约束 (`<`和`>`)。 有关详细信息，请参阅[泛型](generics/index.md)和[约束](generics/constraints.md)。 `parameter-list`介绍构造函数参数。 与类型; 相关的第一个访问修饰符第二个与主构造函数。 在这两种情况下，默认值是`public`。

使用指定的类的基类`inherit`关键字。 你必须提供参数，在括号内，基类构造函数。

声明字段或函数通过使用本地到类的值`let`绑定，并且必须遵循的一般规则`let`绑定。 `do-bindings`一部分包括在对象构造时要执行的代码。

`member-list`包含其他构造函数、 实例和静态方法声明、 接口声明，抽象绑定，以及属性和事件声明。 描述了这些内容在[成员](members/index.md)。

`identifier`使用带有可选`as`关键字到实例变量或自我标识符，可在类型定义用来引用类型的实例为指定的名称。 有关详细信息，请参阅本主题中后面的部分自我标识符。

关键字`class`和`end`标记的开始和结束的定义是可选的。

相互递归类型，它们是互相引用的类型，联接连同`and`关键字允许进行相互递归函数。 有关示例，请参阅部分相互递归类型。


## <a name="constructors"></a>构造函数
构造函数是创建的类类型的实例的代码。 类构造函数在 F # 中工作方式略有不同，与它们在其他.NET 语言中执行操作。 在 F # 类中，没有始终主构造函数中所述该形参的实参`parameter-list`后面类型名称，以及其正文组成`let`(和`let rec`) 开头的类声明和绑定`do`按照的绑定。 在主构造函数的自变量是在类声明整个范围内。

你可以通过添加其他构造函数`new`关键字将成员添加，如下所示：

`new`(`argument-list`) = `constructor-body`

新的构造函数的主体必须调用指定的类声明顶部的主构造函数。

下面的示例阐释了这一概念。 在下面的代码中，`MyClass`具有两个构造函数，采用两个自变量和另一个构造函数具有主构造函数不采用任何参数。

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2401.fs)]
    
## <a name="let-and-do-bindings"></a>let 和 do 绑定

`let`和`do`类定义中的绑定窗体的主类构造函数中，正文，因此它们运行每当创建类实例。 如果`let`绑定是一个函数，则将它编译为一个成员。 如果`let`绑定是一个值，不用于任何函数或成员，则将编译为一个变量，是为构造函数。 否则，它会编译成类的字段。 `do`按照的表达式被编译到主构造函数和执行初始化代码的每个实例。 任何其他构造函数始终调用主构造函数，因为`let`绑定和`do`绑定始终执行而与所调用构造函数。

通过创建的字段`let`绑定可以访问在这些方法和类的属性; 但是，它们不能从访问静态方法，即使的静态方法采用实例变量作为参数。 它们不能通过使用自我标识符，如果存在访问。


## <a name="self-identifiers"></a>自我标识符

A*自我标识符*是表示的当前实例的名称。 自我标识符类似于`this`C# 或 c + + 中的关键字或`Me`在 Visual Basic 中。 可以在两种不同方式，具体取决于是否想自我标识符处于作用域为整个类定义，或仅有关单个方法来定义自我标识符。

若要定义整个类自我标识符，使用`as`构造函数参数的右括号后关键字列表，并指定标识符名称。

若要定义自我标识符仅为一个方法，提供在成员声明中之前的方法名称和句点 （.） 作为分隔符, 的自我标识符。

下面的代码示例说明了创建自我标识符的两种方法。 在第一个行中，`as`关键字用于定义自我标识符。 在第五个行中，标识符`this`用于定义其作用域仅限于方法自我标识符`PrintMessage`。

```fsharp
type MyClass2(dataIn) as self =
    let data = dataIn
    do
        self.PrintMessage()
    member this.PrintMessage() =
        printf "Creating MyClass2 with Data %d" data
```

与在其他.NET 语言中，您可以命名自我标识符随意;你并不限制为名称如`self`， `Me`，或`this`。

使用声明的自我标识符`as`之前未初始化关键字后`let`执行绑定。 因此，它不能在`let`绑定。 你可以使用中的自我标识符`do`绑定部分。


## <a name="generic-type-parameters"></a>泛型类型参数

在尖括号中指定泛型类型参数 (`<`和`>`)，单引号跟一个标识符的形式。 用逗号分隔多个泛型类型参数。 泛型类型参数是在声明整个范围内。 下面的代码示例演示如何指定泛型类型参数。

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2403.fs)]

使用类型时，会被推断类型参数。 在下面的代码中，推断出的类型是一个元组序列。

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet24031.fs)]
    
## <a name="specifying-inheritance"></a>指定继承

`inherit`子句标识直接基类，如果有一个。 在 F # 中，只有一个直接基类被允许。 类实现的接口不被视为基类。 接口中讨论了[接口](Interfaces.md)主题。

你可以访问的方法和属性的基类派生类中使用该语言关键字`base`作为标识符后, 跟一个句点 （.） 和成员的名称。

有关详细信息，请参阅[继承](inheritance.md)。


## <a name="members-section"></a>成员部分
你可以在本部分中定义静态或实例方法、 属性、 接口实现、 抽象成员、 事件声明和其他构造函数。 允许和执行操作的绑定不能出现在此部分。 因为成员可以添加到不同的 F # 类型除了类之外，因此将讨论在单独主题中，[成员](members/index.md)。


## <a name="mutually-recursive-types"></a>相互递归类型
在定义相互以循环方式引用的类型时，你将排列在一起的类型定义通过使用`and`关键字。 `and`关键字将替换`type`上除外，如下所示的第一个定义的关键字。

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2404.fs)]

输出为当前目录中的所有文件的列表。


## <a name="when-to-use-classes-unions-records-and-structures"></a>何时使用类、 联合、 记录和结构
给定的各种类型可供选择，需要更好地理解什么每个类型都旨在为选择的特定情况下的相应类型。 类旨在在面向对象编程的上下文中使用。 面向对象的编程是为.NET Framework 编写的应用程序中使用的基准范例。 如果你的 F # 代码必须与.NET Framework 或另一个面向对象的库，紧密合作，尤其是如果你需要从面向对象的类型系统如 UI 库扩展，类则和可能适用。

如果你不与互操作性密切面向对象的代码，或者你正在编写是自包含且与面向对象的代码进行频繁交互因此受保护的代码，你应该考虑使用记录和可区分联合。 单个精心构思的可区分的联合，以及适当的模式匹配的代码中，通常可用作对象层次结构一个更简单的替代方法。 有关可区分联合的详细信息，请参阅[可区分联合](discriminated-unions.md)。

记录具有比类，更简单的优点，但是记录将不适用的一种类型的需求超过了所实现的简单性。 记录是基本上简单值的聚合，可以执行自定义操作的单独构造函数，而无需隐藏的字段，而无需继承或接口的实现。 虽然如属性和方法的成员可以添加到记录以使其行为更复杂，存储在记录中的字段仍是一个简单值的聚合。 记录有关的详细信息，请参阅[记录](records.md)。

结构还可以用于的少量聚合数据，但它们可以将其与类和记录的区别在于它们是.NET 值类型。 类和记录是.NET 引用类型。 值类型和引用类型的语义的不同，在于，按值传递的值类型。 这意味着，它们将会复制在作为参数传递或从函数返回时的位位。 客户还存储在堆栈上或者，如果用作字段，则嵌入在父对象而不是存储在堆上其自己单独的位置。 因此，结构适于经常访问的数据访问堆的开销时出现问题。 有关结构的详细信息，请参阅[结构](structures.md)。


## <a name="see-also"></a>另请参阅
[F# 语言参考](index.md)

[成员](members/index.md)

[继承](inheritance.md)

[接口](interfaces.md)

