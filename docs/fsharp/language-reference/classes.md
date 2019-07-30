---
title: 类
description: 了解F#类的类型, 这些类型表示可以具有属性、方法和事件的对象。
ms.date: 05/16/2016
ms.openlocfilehash: 5c012d028bc1f89e3e9f5969b3461faab9aad3a0
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/30/2019
ms.locfileid: "68630439"
---
# <a name="classes"></a>类

*类*是表示可以具有属性、方法和事件的对象的类型。

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

类表示 .NET 对象类型的基本说明;类是在中F#支持面向对象的编程的主要类型概念。

在上述语法中, 是`type-name`任何有效的标识符。 `type-params`描述可选的泛型类型参数。 它包含类型参数名称和括在尖括号 (`<`和`>`) 中的约束。 有关详细信息, 请参阅[泛型](./generics/index.md)和[约束](./generics/constraints.md)。 `parameter-list`描述构造函数参数。 第一个访问修饰符适用于类型;第二种情况适用于主构造函数。 在这两种情况下, `public`默认值为。

使用`inherit`关键字指定类的基类。 您必须为基类构造函数提供参数 (在括号中)。

使用`let`绑定声明类的本地字段或函数值, 并且必须遵循`let`绑定的通用规则。 `do-bindings`部分包含在对象构造时要执行的代码。

`member-list`包含其他构造函数、实例和静态方法声明、接口声明、抽象绑定以及属性和事件声明。 [成员](./members/index.md)中对它们进行了介绍。

与`identifier` 可选`as`关键字一起使用的可为实例变量提供名称, 也可以在类型定义中使用它来引用类型的实例。 有关详细信息, 请参阅本主题后面的自我标识符部分。

标记定义`class`的`end`开头和结尾的关键字和都是可选的。

相互引用的相互递归类型与`and`关键字联接在一起, 就像相互递归函数一样。 有关示例, 请参阅 "互相递归类型" 一节。

## <a name="constructors"></a>构造函数

构造函数是创建类类型的实例的代码。 类的构造函数的工作方式F#与其他 .net 语言的不同。 在F#类中, 始终存在一个主构造函数, 其自变量`parameter-list`位于类型名称之后, 其`let`正文包含类声明开头的 (和`let rec`) 绑定,`do`跟随的绑定。 主构造函数的参数在整个类声明的范围内。

您可以使用`new`关键字添加其他构造函数来添加成员, 如下所示:

`new`(`argument-list`) = `constructor-body`

新构造函数的主体必须调用在类声明顶部指定的主构造函数。

下面的示例阐释了这一概念。 在下面的代码中`MyClass` , 有两个构造函数, 这是一个带有两个自变量的主构造函数, 另一个不采用参数的构造函数。

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2401.fs)]

## <a name="let-and-do-bindings"></a>let 和 do Bindings

类`let`定义`do`中的和绑定构成了主类构造函数的主体, 因此每当创建类实例时它们都将运行。 `let`如果绑定是函数, 则将其编译到成员中。 `let`如果绑定是未在任何函数或成员中使用的值, 则将其编译为构造函数的局部变量。 否则, 将编译为类的字段。 接`do`下来的表达式编译到主构造函数中, 并为每个实例执行初始化代码。 由于任何其他构造函数始终调用主构造函数, `let`因此绑定`do`和绑定始终执行, 而不考虑调用哪个构造函数。

通过`let`绑定创建的字段可以在类的方法和属性中进行访问; 但是, 即使静态方法采用实例变量作为参数, 也不能从静态方法访问这些字段。 不能使用 self 标识符 (如果存在) 访问这些项。

## <a name="self-identifiers"></a>自我标识符

*自我标识符*是表示当前实例的名称。 自标识符类似于`this` C#或C++ `Me`中的关键字, Visual Basic。 您可以通过两种不同的方式来定义自我标识符, 具体情况取决于您是希望自标识符在整个类定义的范围内还是仅适用于单个方法。

若要为整个类定义自我标识符, 请在构造`as`函数参数列表的右括号后使用关键字, 并指定标识符名称。

若要只为一个方法定义一个自标识符, 请在成员声明中提供自标识符, 紧靠在方法名称和句点 (.) 前面作为分隔符。

下面的代码示例演示了创建自我标识符的两种方法。 在第一行中, `as`关键字用于定义自我标识符。 在第五行, 标识符`this`用于定义其作用域限制为方法`PrintMessage`的自定义标识符。

```fsharp
type MyClass2(dataIn) as self =
    let data = dataIn
    do
        self.PrintMessage()
    member this.PrintMessage() =
        printf "Creating MyClass2 with Data %d" data
```

与其他 .NET 语言不同, 你可以将自己的标识符命名为你所需的名称;你不能只限于`self`、 `Me`或`this`之类的名称。

在执行`let`绑定之前, 不会初始化`as`用关键字声明的 self 标识符。 因此, 它不能在`let`绑定中使用。 您可以使用 "绑定" `do`部分中的 "自标识符"。

## <a name="generic-type-parameters"></a>泛型类型参数

泛型类型参数在尖括号 (`<`和`>`) 中指定, 其形式为一个引号, 后跟一个标识符。 多个泛型类型参数由逗号分隔。 泛型类型参数在整个声明范围内。 下面的代码示例演示如何指定泛型类型参数。

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2403.fs)]

当使用类型时, 将推理类型参数。 在下面的代码中, 推理出的类型是元组的序列。

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet24031.fs)]

## <a name="specifying-inheritance"></a>指定继承

`inherit`子句标识直接基类 (如果有)。 在F#中, 只允许一个直接基类。 类实现的接口不是基类。 接口[主题中](Interfaces.md)讨论了接口。

通过使用 language 关键字`base`作为标识符, 后跟句点 (.) 和成员名称, 你可以从派生类访问基类的方法和属性。

有关详细信息，请参阅[继承](inheritance.md)。

## <a name="members-section"></a>成员部分

您可以在此部分中定义静态方法、属性、接口实现、抽象成员、事件声明和其他构造函数。 此部分中不能出现 Let 和 do 绑定。 因为成员可以添加到各种F#类型, 而不是类, 因此, 它们将在单独的主题[成员](./members/index.md)中进行讨论。

## <a name="mutually-recursive-types"></a>相互递归类型

如果以循环方式定义彼此引用的类型, 则可以使用`and`关键字将类型定义组合在一起。 关键字替换除第一个定义外的所有关键字,如下所示。`type` `and`

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2404.fs)]

输出为当前目录中的所有文件的列表。

## <a name="when-to-use-classes-unions-records-and-structures"></a>何时使用类、联合、记录和结构

由于要选择各种类型, 您需要充分了解每种类型的设计目的, 以便为特定情况选择适当的类型。 类设计用于面向对象的编程上下文。 面向对象的编程是在为 .NET Framework 编写的应用程序中使用的主要范例。 如果你F#的代码必须与 .NET Framework 或另一个面向对象的库密切合作, 尤其是在需要从面向对象的类型系统 (如 UI 库) 中进行扩展时, 类可能是合适的。

如果你不与面向对象的代码密切互操作, 或者如果你正在编写自包含的代码, 从而保护其不受面向对象代码的频繁交互, 则应考虑使用记录和可区分联合。 与相应的模式匹配代码一起使用的一种非常好的方法是, 通常可以将其用作对象层次结构的更简单的替代方法。 有关可区分联合的详细信息, 请参阅可[区分联合](discriminated-unions.md)。

记录的优点是比类简单, 但当类型的需求超过了可通过其简易性实现的需求时, 记录不适当。 记录基本上是值的简单聚合, 无需单独的构造函数来执行自定义操作, 无需隐藏字段, 并且无需继承或接口实现。 尽管可以将属性和方法等成员添加到记录中以使它们的行为更加复杂, 但存储在记录中的字段仍是值的简单聚合。 有关记录的详细信息, 请参阅[记录](records.md)。

对于少量的数据聚合, 结构也很有用, 但它们不同于类和记录, 因为它们是 .NET 值类型。 类和记录是 .NET 引用类型。 值类型和引用类型的语义不同于值类型通过值传递。 这意味着, 在将它们作为参数传递或从函数返回时, 它们将被复制到位。 它们还存储在堆栈上, 或者, 如果用作字段, 则嵌入到父对象中, 而不是存储在堆上各自不同的位置。 因此, 当访问堆的开销是一个问题时, 结构适用于经常访问的数据。 有关结构的详细信息, 请参阅[结构](structures.md)。

## <a name="see-also"></a>请参阅

- [F# 语言参考](index.md)
- [成员](./members/index.md)
- [继承](inheritance.md)
- [接口](interfaces.md)
