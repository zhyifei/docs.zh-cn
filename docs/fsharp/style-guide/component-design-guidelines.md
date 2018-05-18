---
title: 'F # 组件设计准则'
description: '了解有关编写 F # 组件消耗旨在由其他调用方的准则。'
ms.date: 05/14/2018
ms.openlocfilehash: 7859baac76be01b2cfbdc8602b6cc417cfe5106f
ms.sourcegitcommit: 89c93d05c2281b4c834f48f6c8df1047e1410980
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/15/2018
---
# <a name="f-component-design-guidelines"></a>F # 组件设计准则

本文档是一组的 F # 编程，F # 组件设计准则，v14，Microsoft Research 所基于的组件设计指导原则和[另一个版本](https://fsharp.org/specs/component-design-guidelines/)最初策展和 F # Software Foundation 由维护。

本文档假定你熟悉 F # 编程。 非常感谢 F # 社区的贡献和在本指南的各个版本很有帮助的反馈。

## <a name="overview"></a>概述

本文档考察某些 F # 组件设计和编码与相关的问题。 组件可能意味着以下任一项：

* 你已在该项目中的外部使用者的 F # 项目中的图层。
* 跨程序集边界中适合由 F # 代码使用库。
* 跨程序集边界中适合由任何.NET 语言消耗库。
* 如适用于分发的包存储库中，通过库[NuGet](https://nuget.org)。

请按照本文中所述的技术[的良好的 F # 代码的五个原则](index.md#five-principles-of-good-f-code)，从而利用同时功能和对象根据编程。

方法，无论组件和库设计器将尝试创建一个 API，可轻松由开发人员时面临实际和实际问题很的多。 负责任的应用程序的[.NET 库设计准则](../../standard/design-guidelines/index.md)将引导你创建一组一致的愉快若要使用的 Api。

## <a name="general-guidelines"></a>通用准则

有几个通用准则适用于 F # 库，而不考虑库的目标受众。

### <a name="learn-the-net-library-design-guidelines"></a>了解.NET 库设计准则

F # 编码你正在的种类，无论它是有价值的工作掌握[.NET 库设计准则](../../standard/design-guidelines/index.md)。 大多数其他 F #.NET 程序员熟悉这些准则，并预期.NET 代码以符合它们。

.NET 类库设计指南提供有关命名、 设计类和接口、 成员 （属性、 方法、 事件等） 的设计和的详细信息，常规指南，并且是有用的第一个点的各种不同的设计指南的引用。

### <a name="add-xml-documentation-comments-to-your-code"></a>将 XML 文档注释添加到你的代码

公共 Api 的 XML 文档确保用户可以获得很好的 Intellisense 和快速信息，使用这些类型和成员，以及启用生成文档文件库时。 请参阅[XML 文档](../language-reference/xml-documentation.md)有关可以用于 xmldoc 注释内的附加标记的各种 xml 标记。

```fsharp
/// A class for representing (x,y) coordinates
type Point =

    /// Computes the distance between this point and another
    member DistanceTo : otherPoint:Point -> float
```

你可以使用缩写形式 XML 注释 (`/// comment`)，或标准的 XML 注释 (`///<summary>comment</summary>`)。

### <a name="consider-using-explicit-signature-files-fsi-for-stable-library-and-component-apis"></a>请考虑稳定的库和组件 Api 使用显式的签名文件 (.fsi)

使用显式的签名文件的 F # 库中提供公共 API，这两者都可帮助确保，你知道的完整公共接口的你的库，以及提供完全分离之间公用文档和内部简洁的摘要实现详细信息。 请注意，签名文件将摩擦添加到更改公共 API，通过要求在实现和签名文件中进行更改。 因此，签名文件应通常仅引入时 API 具有成为巩固并且不再需要重大更改。

### <a name="always-follow-best-practices-for-using-strings-in-net"></a>始终遵循在.NET 中使用字符串的最佳实践

请按照[在.NET 中使用字符串的最佳实践](../../standard/base-types/best-practices-strings.md)指南。 具体而言，始终显式声明*区域性意向*中的转换和比较字符串 （如果适用）。

## <a name="guidelines-for-f-facing-libraries"></a>F # 的准则-面向库

本节提供有关在开发公共 F # 的建议-面向库;也就是说，公开公共 Api 旨在由 F # 开发人员使用的库。 没有特定于 F # 适用的各种库设计建议。 如果未指定特定后面的建议，在.NET 库设计准则是回退的指南。

### <a name="naming-conventions"></a>命名约定

#### <a name="use-net-naming-and-capitalization-conventions"></a>使用.NET 命名和大小写约定

下表遵循.NET 命名和大小写约定。 有小添加项。 还包括 F # 构造。

| 构造 | Case | 部件 | 示例 | 说明 |
|-----------|------|------|----------|-------|
| 具体类型 | PascalCase | 名词 / 形容词 | 列表中，双精度，复杂 | 具体类型是结构、 类、 枚举、 委托、 记录和联合。 尽管类型名称是在 OCaml 传统上小写，F # 已采用了.NET 类型的命名方案。
| DLL           | PascalCase |                 | Fabrikam.Core.dll |  |
| 联合标记     | PascalCase | 名词 | 一些，添加成功 | 不要在公共 Api 中使用前缀。 （可选） 使用的前缀时内部，如键入团队 = TAlpha | TBeta | TDelta。 ' ' |
| 事件          | PascalCase | 谓词 | ValueChanged / ValueChanging |  |
| 异常     | PascalCase |      | WebException | 名称应以"异常"结尾。 |
| 字段          | PascalCase | 名词 | CurrentName  | |
| 接口类型 |  PascalCase | 名词 / 形容词 | IDisposable | 名称应以"I"开头。 |
| 方法 |  PascalCase |  谓词 | ToString | |
| 命名空间 | PascalCase | | Microsoft.FSharp.Core | 通常使用`<Organization>.<Technology>[.<Subnamespace>]`，但删除组织如果技术无关的组织。 |
| 参数 | 驼峰匹配 | 名词 |  类型名称、 转换、 范围 | |
| 允许值 （内部） | 驼峰匹配或 PascalCase | 名词 / 谓词 |  getValue myTable |
| 允许值 （外部） | 驼峰匹配或 PascalCase | 名词/谓词  | List.map Dates.Today | let 绑定值通常是公共的遵循传统功能的设计模式时。 但是，通常使用出现可从其他.NET 语言中使用标识符的 PascalCase。 |
| 属性  | PascalCase  | 名词 / 形容词  | IsEndOfFile，背景色  | 布尔值属性通常使用并且可以并且应该赞成，如下所示 IsEndOfFile，不 IsNotEndOfFile。

#### <a name="avoid-abbreviations"></a>避免缩写

.NET 准则禁止使用缩写 (例如，"使用`OnButtonClick`而非`OnBtnClick`")。 常见的缩写，如`Async`允许为"异步"。 对于函数编程;，有时将忽略此原则例如，`List.iter`用于缩写"循环"。 因此，使用缩写倾向于 F # 中在更大程度容忍-到-F # 编程，但仍通常应当避免在公共组件设计。

#### <a name="avoid-casing-name-collisions"></a>避免名称冲突的大小写

.NET 准则说，单独的大小写不能用于消除歧义名称冲突，因为某些客户端语言 (例如，Visual Basic 中) 不区分大小写。

#### <a name="use-acronyms-where-appropriate"></a>在适用处使用首字母缩写词

首字母缩写词，如 XML 不缩写，并在首字母未大写形式 (Xml) 的.NET 库中广泛使用。 仅应使用的已知的广泛认可首字母缩写词。

#### <a name="use-pascalcase-for-generic-parameter-names"></a>为泛型参数的名称使用 PascalCase

为用于公共 Api，包括 F # 中的泛型参数名称 PascalCase-面向库。 具体而言，使用类似名称`T`， `U`， `T1`，`T2`任意泛型参数，并且当特定的名称会使其意义上，然后对于 F #-面向库使用类似名称`Key`， `Value`， `Arg`(但不是例如`TKey`)。

#### <a name="use-either-pascalcase-or-camelcase-for-public-functions-and-values-in-f-modules"></a>对公共函数和 F # 模块中的值使用 PascalCase 或驼峰匹配

驼峰匹配用于为用于而设计的公共函数不合格 (例如， `invalidArg`)，和"标准集合函数"（例如 List.map）。 在这两个这些情况下，函数名称作用类似语言中的关键字。

### <a name="object-type-and-module-design"></a>对象、 类型和模块的设计

#### <a name="use-namespaces-or-modules-to-contain-your-types-and-modules"></a>使用命名空间或模块来包含类型和模块

组件中的每个 F # 文件应命名空间声明或模块声明开头。

```fsharp
namespace Fabrikam.BasicOperationsAndTypes

type ObjectType1() =
    ...

type ObjectType2() =
     ...

module CommonOperations =
    ...
```

或

```fsharp
module Fabrikam.BasicOperationsAndTypes

type ObjectType1() =
    ...

type ObjectType2() =
    ...

module CommonOperations =
    ...
```

使用模块和命名空间将代码最高级别组织之间的差异如下所示：

* 命名空间可以跨多个文件
* 命名空间不能包含 F # 函数，除非它们是在一个内部模块
* 任何给定模块的代码必须包含在单个文件
* 顶级模块可以包含无需内部模块的 F # 函数

顶级命名空间或模块之间的选择会影响的代码的已编译的形式，因此将影响将视图从其他.NET 语言应你的 API 最终使用 F # 代码外部。

#### <a name="use-methods-and-properties-for-operations-intrinsic-to-object-types"></a>用于操作固有的对象类型的方法和属性

当使用对象时，最好是以确保可使用的功能实现与方法和该类型上的属性。

```fsharp
type HardwareDevice() =

    member this.ID = ...

    member this.SupportedProtocols = ...

type HashTable<'Key,'Value>(comparer: IEqualityComparer<'Key>) =

    member this.Add(key, value) = ...

    member this.ContainsKey(key) = ...

    member this.ContainsValue(value) = ...
```

给定成员的大容量的功能需要不一定在中实现该成员，但该功能的使用部分应。

#### <a name="use-classes-to-encapsulate-mutable-state"></a>使用类来封装可变状态

在 F # 中，这只需进行其中状态不已封装由另一种语言构造，如闭包、 序列表达式或异步计算。

```fsharp
type Counter() =
    // let-bound values are private in classes.
    let mutable count = 0

    member this.Next() =
        count <- count + 1
        count
```

#### <a name="use-interfaces-to-group-related-operations"></a>接口用于组相关的操作

使用接口类型来表示一组的操作。 这是优先于其他选项，如元组的函数或函数的记录。

```fsharp
type Serializer =
    abstract Serialize<'T> : preserveRefEq: bool -> value: 'T -> string
    abstract Deserialize<'T> : preserveRefEq: bool -> pickle: string -> 'T
```

优先于：

```fsharp
type Serializer<'T> = {
    Serialize : bool -> 'T -> string
    Deserialize : bool -> string -> 'T
}
```

接口是在.NET 中，可以用于实现什么函子将通常为您提供的第一类概念。 此外，它们可以用于对现有类型到你的程序，记录的函数不能进行编码。

#### <a name="use-a-module-to-group-functions-which-act-on-collections"></a>在集合上使用组功能的作用到模块

在定义集合类型时，请考虑提供一组标准的操作如`CollectionType.map`和`CollectionType.iter`) 的新集合类型。

```fsharp
module CollectionType =
    let map f c =
        ...
    let iter f c =
        ...
```

如果包含此类模块，请按照在 FSharp.Core 中找到的函数的标准命名约定。

#### <a name="use-a-module-to-group-functions-for-common-canonical-functions-especially-in-math-and-dsl-libraries"></a>对于通用、 规范函数，特别是在数学和 DSL 库使用的组函数的模块

例如，`Microsoft.FSharp.Core.Operators`为自动打开的集合的顶级函数 (如`abs`和`sin`) 由 FSharp.Core.dll。

同样，统计信息库可能包含函数的模块`erf`和`erfc`，而此模块用于显式或自动打开。

#### <a name="consider-using-requirequalifiedaccess-and-carefully-apply-autoopen-attributes"></a>请考虑使用 RequireQualifiedAccess 并仔细应用 AutoOpen 特性

添加`[<RequireQualifiedAccess>]`模块的属性指示模块可能无法打开，并对该模块的元素的引用，需要显式限定访问权限。 例如，`Microsoft.FSharp.Collections.List`模块具有此属性。

时函数和模块中的值可能与其他模块中的名称发生冲突的名称，这会很有用。 需限定的访问会大大增加的长期的可维护性和 evolvability 的库。

添加`[<AutoOpen>]`模块特性意味着打开包含的命名空间时，将打开模块。 `[<AutoOpen>]`属性还可应用于程序集可指示引用的程序集时自动打开模块。

例如，统计信息库**MathsHeaven.Statistics**可能包含`module MathsHeaven.Statistics.Operators`包含函数`erf`和`erfc`。 可以将标记为此模块是合理的`[<AutoOpen>]`。 这意味着`open MathsHeaven.Statistics`也将打开此模块并将名称`erf`和`erfc`纳入范围。 使用另一个良好`[<AutoOpen>]`为包含扩展方法的模块。

因为过度使用的`[<AutoOpen>]`应谨慎使用导致生成受到污染命名空间和属性。 在特定域中，合理地使用的特定库`[<AutoOpen>]`可能会导致更好的可用性。

#### <a name="consider-defining-operator-members-on-classes-where-using-well-known-operators-is-appropriate"></a>请考虑在其中使用的已知运算符是适当的类上定义运算符成员

有时使用类来建模数学构造，如向量。 当要建模的域具有已知的运算符时，作为成员固有的类定义它们非常有用。

```fsharp
type Vector(x:float) =

    member v.X = x

    static member (*) (vector:Vector, scalar:float) = Vector(vector.X * scalar)

    static member (+) (vector1:Vector, vector2:Vector) = Vector(vector1.X + vector2.X)

let v = Vector(5.0)

let u = v * 10.0
```

本指南对应于为这些类型的常规.NET 指南。 但是，它可以是此外重要的 F # 编码因为这会使这些类型以在 F # 函数结合和成员的约束，如 List.sumBy 方法中使用。

#### <a name="consider-using-compiledname-to-provide-a-net-friendly-name-for-other-net-language-consumers"></a>请考虑使用 CompiledName 来提供。用于其他.NET 语言消耗者的网络的友好名称

有时你可能想要的 F # 使用者名称中一种样式的某些内容 (例如，采用小写，使其显示的是静态成员就像它是模块绑定函数)，但它会编译成程序集时产生的名称不同的样式。 你可以使用`[<CompiledName>]`属性的非 F # 代码使用程序集提供不同的样式。

```fsharp
type Vector(x:float, y:float) =

    member v.X = x
    member v.Y = y

    [<CompiledName("Create")>]
    static member create x y = Vector (x, y)

let v = Vector.create 5.0 3.0
```

通过使用`[<CompiledName>]`，你可用于非 F # 使用者的程序集的.NET 命名约定。

#### <a name="use-method-overloading-for-member-functions-if-doing-so-provides-a-simpler-api"></a>如果这样做将提供更简单的 API，使用方法重载成员函数

方法重载是功能强大的工具，用于简化一个 API，可能需要执行类似的功能，但具有不同的选项或参数。

```fsharp
type Logger() =

    member this.Log(message) =
        ...
    member this.Log(message, retryPolicy) =
        ...
```

在 F # 中，是更常见的是上的参数数目，而不是类型参数的重载。

#### <a name="hide-the-representations-of-record-and-union-types-if-the-design-of-these-types-is-likely-to-evolve"></a>如果这些类型的设计非常可能会不断变化，则隐藏的表示形式记录和联合类型

避免泄露具体对象表示形式。 例如的具体表示形式<xref:System.DateTime>通过.NET 库设计的外部的公共 API 不显示值。 在运行时，公共语言运行时知道将执行中使用的提交的实现。 但是，已编译的代码不本身选取对具体的表示形式的依赖关系。

#### <a name="avoid-the-use-of-implementation-inheritance-for-extensibility"></a>避免实现继承用于扩展性

在 F # 中，实现继承很少使用。 此外，继承层次结构通常是将复杂且难以实现，若要更改新要求到达时。 继承的实现仍在 F # 的兼容性和极少数情况下，这是最佳的解决方案到问题，但多态性，如接口的实现的设计时，应在 F # 程序中查找其他方法。

### <a name="function-and-member-signatures"></a>函数和成员的签名

#### <a name="use-tuples-for-return-values-when-returning-a-small-number-of-multiple-unrelated-values"></a>返回值返回少量的多个不相关的值时使用元组

下面是在返回类型中使用一个元组的一个很好示例：

```fsharp
val divrem : BigInteger -> BigInteger -> BigInteger * BigInteger
```

有关返回类型包含许多组件，或如果组件将与单个身份实体，请考虑使用命名的类型而不元组。

#### <a name="use-asynct-for-async-programming-at-f-api-boundaries"></a>使用`Async<T>`为在 F # API 边界进行异步编程

如果没有相应的同步操作名为`Operation`返回`T`，则应命名为异步操作`AsyncOperation`如果它返回`Async<T>`或`OperationAsync`如果它返回`Task<T>`。 常用的.NET 类型来公开 Begin/End 方法，请考虑使用`Async.FromBeginEnd`作为外观以提供对这些.NET Api 的 F # 异步编程模型编写扩展方法。

```fsharp
type SomeType =
    member this.Compute(x:int) : int =
        ...
    member this.AsyncCompute(x:int) : Async<int> =
        ...

type System.ServiceModel.Channels.IInputChannel with
    member this.AsyncReceive() =
        ...
```

### <a name="exceptions"></a>异常

例外情况是在.NET; 异常也就是说，它们应不频繁发生在运行时。 当他们执行时，它们包含的信息是有价值。 例外情况是核心的.NET; 第一类概念it 因此如下所示，相应的异常的应用程序应使用的组件的接口的设计的一部分。

#### <a name="follow-the-net-guidelines-for-exceptions"></a>遵循异常的.NET 指南

[.NET 库设计准则](../../standard/design-guidelines/exceptions.md)为极好的建议提供有关使用的上下文中的所有.NET 编程的异常。 某些这些准则如下所示：

* 请在正常控制流中使用异常。 虽然在 OCaml 等语言中经常使用此技术，它 bug 容易，并可能在.NET 效率很低。 相反，请考虑返回`None`选项值以指示失败引起的是一种常见的或预期的情况。

* 记录错误地使用了函数时，由你的组件引发的异常。

* 如果可能，采用 System 命名空间中的现有异常。 避免<xref:System.ApplicationException>，不过。

* 不会引发<xref:System.Exception>时它将在其中转义到用户代码。 这包括避免使用`failwith`， `failwithf`，这是方便函数在脚本中使用而使正在开发的代码，但应从 F # 库代码而引发的更具体的异常类型中移除。

* 使用`nullArg`， `invalidArg`，和`invalidOp`作为机制引发<xref:System.ArgumentNullException>， <xref:System.ArgumentException>，和<xref:System.InvalidOperationException>在适当的时候。

#### <a name="consider-using-option-values-for-return-types-when-failure-is-not-an-exceptional-scenario"></a>请考虑使用返回类型的选项值时的失败不是异常的方案

异常的.NET 方法是，它们应是"异常";也就是说，它们应出现频率相对较低。 但是，某些操作 （例如，搜索表） 可能会经常失败。 F # 选项值是表示这些操作的返回类型的极佳途径。 这些操作通常开头的名称前缀"try":

```fsharp
// bad: throws exception if no element meets criteria
member this.FindFirstIndex(pred : 'T -> bool) : int =
    ...

// bad: returns -1 if no element meets criteria
member this.FindFirstIndex(pred : 'T -> bool) : int =
    ...

// good: returns None if no element meets criteria
member this.TryFindFirstIndex(pred : 'T -> bool) : int option =
    ...
```

### <a name="extension-members"></a>扩展成员

#### <a name="carefully-apply-f-extension-members-in-f-to-f-components"></a>仔细应用 F # 中的 F # 扩展成员-到-F # 组件

F # 扩展成员通常只应与在使用其模式的大多数类型相关联的内部操作的闭包中的操作。 一种常见用途是提供的 Api，对 F # 更惯例为各种.NET 类型：

```fsharp
type System.ServiceModel.Channels.IInputChannel with
    member this.AsyncReceive() =
        Async.FromBeginEnd(this.BeginReceive, this.EndReceive)

type System.Collections.Generic.IDictionary<'Key,'Value> with
    member this.TryGet key =
        let ok, v = this.TryGetValue key
        if ok then Some v else None
```

### <a name="union-types"></a>联合类型

#### <a name="use-discriminated-unions-instead-of-class-hierarchies-for-tree-structured-data"></a>使用可区分的联合而不是类层次结构树结构数据

树形结构是以递归方式定义。 这是繁琐利用继承，但与可区分联合简洁。

```fsharp
type BST<'T> =
    | Empty
    | Node of 'T * BST<'T> * BST<'T>
```

表示与可区分联合的树式数据还允许你可以受益于 exhaustiveness 在模式匹配。

#### <a name="use-requirequalifiedaccess-on-union-types-whose-case-names-are-not-sufficiently-unique"></a>使用`[<RequireQualifiedAccess>]`上其大小写的名称并不足够唯一的联合类型

您可能发现自己位于相同的名称其中是不同的元素，如可区分联合用例的最佳名称的域。 你可以使用`[<RequireQualifiedAccess>]`若要以避免触发由于隐藏依赖于排序的令人困惑错误区分大小写的名称`open`语句

#### <a name="hide-the-representations-of-discriminated-unions-for-binary-compatible-apis-if-the-design-of-these-types-is-likely-to-evolve"></a>如果这些类型的设计非常可能会不断变化，则隐藏二进制兼容的 Api 可区分联合表示形式

联合类型依赖于 F # 模式匹配窗体简洁的编程模型。 如前所述，应避免泄露具体数据表示形式，如果这些类型的设计非常可能会不断变化。

例如的表示形式可区分联合可以隐藏使用私有或内部声明，或使用签名文件。

```fsharp
type Union =
    private
    | CaseA of int
    | CaseB of string
```

如果不加选择地显示可区分的联合，则可能很难进行版本你的库而不会破坏用户代码。 相反，请考虑泄露一个或多个活动的模式，以允许你类型的值针对的模式匹配。

活动模式提供了另一种方法为提供同时可避免直接公开 F # 联合类型匹配的模式的 F # 使用者。

### <a name="inline-functions-and-member-constraints"></a>内联函数和成员约束

#### <a name="define-generic-numeric-algorithms-using-inline-functions-with-implied-member-constraints-and-statically-resolved-generic-types"></a>定义中使用内联函数的隐式的成员约束和静态解析的泛型类型的泛型数值算法

算术成员约束和 F # 比较约束是一种标准 F # 编程。 例如，考虑以下代码：

```fsharp
let inline highestCommonFactor a b =
    let rec loop a b =
        if a = LanguagePrimitives.GenericZero<_> then b
        elif a < b then loop a (b - a)
        else loop (a - b) b
    loop a b
```

此函数的类型如下所示：

```fsharp
val inline highestCommonFactor : ^T -> ^T -> ^T
                when ^T : (static member Zero : ^T)
                and ^T : (static member ( - ) : ^T * ^T -> ^T)
                and ^T : equality
                and ^T : comparison
```

这是一个数学库中的公共 API 的合适的函数。

#### <a name="avoid-using-member-constraints-to-simulate-type-classes-and-duck-typing"></a>避免使用成员约束模拟类型类和鸭子类型化

可以模拟"回避键入"使用 F # 成员约束。 但是，成员，请使用此应不在常规使用 F # 中-到-F # 库设计。 这是因为库设计基于不熟悉或非标准的隐式约束可能会导致用户代码可以灵活地绑定到一个特定的框架模式。

此外，还有很可能会使用大量的这种方式中的成员约束可能会很长的编译时间。

### <a name="operator-definitions"></a>运算符定义

#### <a name="avoid-defining-custom-symbolic-operators"></a>避免定义自定义的符号运算符

自定义运算符是基本在某些情况下，大量的实现代码中的非常有用符号设备。 对于的库的新用户，命名的函数通常是使用起来更为简便。 此外，自定义的符号运算符可以将其硬到文档中，并且用户找到它更难查找运算符，由于 IDE 和搜索引擎中的现有限制的帮助。

因此，最好发布你的功能作为命名的函数和成员，并仅当符号好处超过文档并认知开销，让它们此外公开此功能的运算符。

### <a name="units-of-measure"></a>度量单位

#### <a name="carefully-use-units-of-measure-for-added-type-safety-in-f-code"></a>仔细使用的度量值的单位来实现 F # 代码中添加的类型安全

查看其他.NET 语言时，将清除的部门的度量值的附加键入的信息。 请注意，.NET 组件、 工具和反射将看到类型 san 单位。 例如，C# 使用者将看到`float`而非`float<kg>`。

### <a name="type-abbreviations"></a>类型缩写

#### <a name="carefully-use-type-abbreviations-to-simplify-f-code"></a>仔细使用类型缩写来简化 F # 代码

.NET 组件、 工具和反射看不到类型的缩写的名称。 长时间使用的类型缩写还可以显示变得更加复杂比它实际上是，其无法混淆使用者域。

#### <a name="avoid-type-abbreviations-for-public-types-whose-members-and-properties-should-be-intrinsically-different-to-those-available-on-the-type-being-abbreviated"></a>避免其成员和属性应本质上可用的正在缩写的类型不同的公共类型的类型缩写

在这种情况下，正在缩写的类型将显示有关正在定义的实际类型表示的过多信息。 相反，请考虑包装类类型或单用例可区分的联合中的缩写 （或时性能至关重要，请考虑使用结构类型包装缩写）。

例如，它很容易定义为 F # 映射的一种特殊情况多地图，例如：

```fsharp
type MultiMap<'Key,'Value> = Map<'Key,'Value list>
```

但是，此类型上的逻辑点表示法操作不是在地图上的操作相同 – 例如，它位于合理查找运算符映射。[键] 返回空列表如果该键不在字典中，而不是引发异常。

## <a name="guidelines-for-libraries-for-use-from-other-net-languages"></a>适用于从其他.NET 语言中使用的库的准则

在设计时用于其他.NET 语言使用的库，请务必遵守[.NET 库设计准则](../../standard/design-guidelines/index.md)。 在此文档中，这些库都标记为香草.NET 库，而不是 F #-面向使用 F # 库构造不受限制。 设计香草.NET 库意味着通过最小化使用 F # 提供熟悉且惯用 Api 与.NET Framework 的其余部分一致的公共 API 中的特定构造。 规则将在以下各节中介绍。

### <a name="namespace-and-type-sesign-for-libraries-for-use-from-other-net-languages"></a>Namespace 和类型 sesign （用于从其他.NET 语言中使用的库）

#### <a name="apply-the-net-naming-conventions-to-the-public-api-of-your-components"></a>适用于你的组件的公共 API 的.NET 命名约定

请特别注意到使用缩写的名称和.NET 大小写准则。

```fsharp
type pCoord = ...
    member this.theta = ...

type PolarCoordinate = ...
    member this.Theta = ...
```

#### <a name="use-namespaces-types-and-members-as-the-primary-organizational-structure-for-your-components"></a>使用命名空间、 类型和成员作为你的组件的主要组织结构

包含公共的功能的所有文件应都开头`namespace`声明和命名空间中的唯一的面向公众的实体应是类型。 不要使用 F # 模块。

使用非公共模块保存实现代码、 实用程序类型和实用工具函数。

静态类型应优先模块，因为它们允许的未来发展的 api 用于重载和其他不能在 F # 模块内使用的.NET API 设计概念。

例如，替代以下的公共 API:

```fsharp
module Fabrikam

module Utilities =
    let Name = "Bob"
    let Add2 x y = x + y
    let Add3 x y z = x + y + z
```

请考虑改为：

```fsharp
namespace Fabrikam

[<AbstractClass; Sealed>]
type Utilities =
    static member Name = "Bob"
    static member Add(x,y) = x + y
    static member Add(x,y,z) = x + y + z
```

#### <a name="use-f-record-types-in-vanilla-net-apis-if-the-design-of-the-types-wont-evolve"></a>如果类型的设计不会不断发展，在香草.NET Api 中使用 F # 记录类型

F # 记录类型编译为一个简单的.NET 类。 这些是适用于 Api 中的某些简单、 稳定的类型。 你应考虑使用`[<NoEquality>]`和`[<NoComparison>]`属性来取消自动生成的接口。 此外避免使用与这些公开的公共字段的香草.NET Api 中的可变记录字段。 应始终考虑是否的类将提供更灵活的 api 选项未来变化情况。

例如，下面的 F # 代码公开的公共 API 的 C# 使用者：

F # 中：

```fsharp
[<NoEquality; NoComparison>]
type MyRecord =
    { FirstThing : int
        SecondThing : string }
```

C#：

```csharp
public sealed class MyRecord
{
    public MyRecord(int firstThing, string secondThing);
    public int FirstThing { get; }
    public string SecondThing { get; }
}
```

#### <a name="hide-the-representation-of-f-union-types-in-vanilla-net-apis"></a>隐藏的表示形式香草.NET Api 联合类型 F #

F # 联合类型不常用于跨组件边界进行，即使对于 F #-到-F # 编码。 它们是一种绝佳实现设备时在组件和库内部使用。

在设计时一个普通的.NET API，请考虑使用专用的声明或签名文件中隐藏的表示形式的联合类型。

```fsharp
type PropLogic =
    private
    | And of PropLogic * PropLogic
    | Not of PropLogic
    | True
```

你还可能增加使用联合表示形式内部与成员来提供所需的类型。NET 面向 API。

```fsharp
type PropLogic =
    private
    | And of PropLogic * PropLogic
    | Not of PropLogic
    | True

    /// A public member for use from C#
    member x.Evaluate =
        match x with
        | And(a,b) -> a.Evaluate && b.Evaluate
        | Not a -> not a.Evaluate
        | True -> true

    /// A public member for use from C#
    static member CreateAnd(a,b) = And(a,b)
```

#### <a name="design-gui-and-other-components-using-the-design-patterns-of-the-framework"></a>设计 GUI 和其他组件使用的框架的设计模式

在.NET 中，如 WinForms、 WPF 和 ASP.NET 中有可用的很多不同的框架。 如果您正在设计用于这些框架组件，则应使用每个命名和设计约定。 例如，对于 WPF 编程，采用设计的类的 WPF 设计的模式。 对于在用户界面编程模型，使用如事件的设计模式和基于通知的集合，如位于<xref:System.Collections.ObjectModel>。

### <a name="object-and-member-design-for-libraries-for-use-from-other-net-languages"></a>（对于从其他.NET 语言中使用的库） 的对象和成员设计

#### <a name="use-the-clievent-attribute-to-expose-net-events"></a>CLIEvent 特性用于公开.NET 事件

构造`DelegateEvent`与特定的.NET 委托采用对象的类型和`EventArgs`(而非`Event`，只需使用`FSharpHandler`类型默认情况下的)，以便事件要发布到其他.NET 语言熟悉的方式。

```fsharp
type MyBadType() =
    let myEv = new Event<int>()

    [<CLIEvent>]
    member this.MyEvent = myEv.Publish

type MyEventArgs(x:int) =
    inherit System.EventArgs()
    member this.X = x

    /// A type in a component designed for use from other .NET languages
type MyGoodType() =
    let myEv = new DelegateEvent<EventHandler<MyEventArgs>>()

    [<CLIEvent>]
    member this.MyEvent = myEv.Publish
```

#### <a name="expose-asynchronous-operations-as-methods-which-return-net-tasks"></a>公开异步操作作为方法返回.NET 任务

在.NET 中使用任务来表示活动的异步计算。 任务是通常比 F # 不太组合`Async<T>`对象，因为它们表示"已经在执行"任务，不能由在一起，可以执行并行组合，或该隐藏取消信号和其他的传播用的方式上下文参数。

但是，尽管此操作，请返回任务的方法是于.NET 的异步编程的标准表示。

```fsharp
/// A type in a component designed for use from other .NET languages
type MyType() =

    let compute (x: int) : Async<int> = async { ... }

    member this.ComputeAsync(x) = compute x |> Async.StartAsTask
```

经常将还想要接受显式取消标记：

```fsharp
/// A type in a component designed for use from other .NET languages
type MyType() =
    let compute(x:int) : Async<int> = async { ... }
    member this.ComputeAsTask(x, cancellationToken) = Async.StartAsTask(compute x, cancellationToken)
```

#### <a name="use-net-delegate-types-instead-of-f-function-types"></a>使用.NET 委托类型，而不是 F # 函数类型

此处"F # 函数类型"意味着"箭头"类型喜欢`int -> int`。

而不是以下内容：

```fsharp
member this.Transform(f:int->int) =
    ...
```

执行此操作：

```fsharp
member this.Transform(f:Func<int,int>) =
    ...
```

F # 函数类型显示为`class FSharpFunc<T,U>`到其他.NET 语言，且不太适用于了解委托类型的语言功能和工具。 创建面向.NET Framework 3.5 或更高版本，更高序位方法时`System.Func`和`System.Action`委托是正确的 Api 来发布可让.NET 开发人员要低冲突的方式使用这些 Api。 (如果目标.NET Framework 2.0，系统定义的委托类型是受限更多; 请考虑使用预定义的委托类型，例如`System.Converter<T,U>`或定义特定委托类型。)

另一方面，.NET 委托不自然的 F #-面向库 (请参阅在 F # 的下一步部分-面向库)。 因此，常见的实现策略开发香草.NET 库的更高序位方法时是以创作所有使用 F # 函数类型的实现，然后创建使用委托作为之上的实际 F # 的精简外观的公共 API实现。

#### <a name="use-the-trygetvalue-pattern-instead-of-returning-f-option-values-and-prefer-method-overloading-to-taking-f-option-values-as-arguments"></a>使用 TryGetValue 模式而不是返回 F # 选项值，并首选采用 F # 选项值作为自变量的重载方法

使用 Api 中的 F # 选项类型性的常见模式是更好地在香草中实现使用标准.NET 的.NET Api 设计技巧。 而不是返回的 F # 选项值，请考虑使用 bool 返回类型以及输出参数如下所示的"TryGetValue"模式。 而不是采用 F # 选项值作为参数，请考虑使用方法重载或可选自变量。

```fsharp
member this.ReturnOption() = Some 3

member this.ReturnBoolAndOut(outVal : byref<int>) =
    outVal <- 3
    true

member this.ParamOption(x : int, y : int option) =
    match y with
    | Some y2 -> x + y2
    | None -> x

member this.ParamOverload(x : int) = x

member this.ParamOverload(x : int, y : int) = x + y
```

#### <a name="use-the-net-collection-interface-types-ienumerablet-and-idictionarykeyvalue-for-parameters-and-return-values"></a>使用.NET 集合接口类型 IEnumerable\<T\>和 IDictionary\<键、 值\>为参数和返回值

避免使用的具体集合类型，如.NET 数组`T[]`，F # 类型`list<T>`，`Map<Key,Value>`和`Set<T>`，和.NET 具体集合类型，如`Dictionary<Key,Value>`。 .NET 库设计准则已了解有关何时使用各种集合类型，如好的建议`IEnumerable<T>`。 某些使用数组 (`T[]`) 是在某些情况下，在性能地面可以接受的。 请注意，尤其是`seq<T>`是只需 F # 别名`IEnumerable<T>`，并因此 seq 通常是一个普通的.NET API 的相应类型。

而不是 F # 列表：

```fsharp
member this.PrintNames(names : string list) =
    ...
```

使用 F # 序列：

```fsharp
member this.PrintNames(names : seq<string>) =
    ...
```

#### <a name="use-the-unit-type-as-the-only-input-type-of-a-method-to-define-a-zero-argument-method-or-as-the-only-return-type-to-define-a-void-returning-method"></a>用作唯一的一种方法的输入类型的单位类型定义一个零参数的方法，或作为唯一返回类型来定义一个返回 void 的方法

避免的单位类型的其他用法。 这些是很好：

```fsharp
✔ member this.NoArguments() = 3

✔ member this.ReturnVoid(x : int) = ()
```

这是错误的：

```fsharp
member this.WrongUnit( x:unit, z:int) = ((), ())
```

#### <a name="check-for-null-values-on-vanilla-net-api-boundaries"></a>检查在香草.NET API 边界上的 null 值

F # 实现代码往往具有较少的 null 值，由于不可变的设计模式和使用限制的 F # 类型的 null 文本。 其他.NET 语言通常使用 null 作为值更频繁。 因此，公开了一个普通的.NET API 的 F # 代码应检查在 API 边界处的 null 的参数，并防止这些值更深入地流入的 F # 实现代码。 `isNull`函数或在进行匹配的模式`null`模式可用。

```fsharp
let checkNonNull argName (arg: obj) =
    match arg with
    | null -> nullArg argName
    | _ -> ()

let checkNonNull` argName (arg: obj) =
    if isNull arg then nullArg argName
    else ()
```

#### <a name="avoid-using-tuples-as-return-values"></a>避免使用元组作为返回值

相反，希望返回的已命名的类型保存聚合的数据，或使用输出参数返回多个值。 尽管.NET 中存在的元组和结构元组 （包括 C# 语言支持的结构元组），它们将最常未提供理想和预期 API 为.NET 开发人员。

#### <a name="avoid-the-use-of-currying-of-parameters"></a>避免使用参数的扩充

请改为使用.NET 调用约定``Method(arg1,arg2,…,argN)``。

```fsharp
member this.TupledArguments(str, num) = String.replicate num str
```

提示： 如果您正在设计用于从任何.NET 语言的库，则没有任何替代的实际执行的一些实验性 C# 和 Visual Basic 编程以确保你的库"感觉右"从这些语言操作。 你可以使用.NET 反射器和 Visual Studio 对象浏览器等工具以确保库和其文档显示按预期给开发人员。

## <a name="appendix"></a>附录

### <a name="end-to-end-example-of-designing-f-code-for-use-by-other-net-languages"></a>由其他.NET 语言设计的使用 F # 代码的端到端示例

请考虑以下类：

```fsharp
open System

type Point1(angle,radius) =
    new() = Point1(angle=0.0, radius=0.0)
    member x.Angle = angle
    member x.Radius = radius
    member x.Stretch(l) = Point1(angle=x.Angle, radius=x.Radius * l)
    member x.Warp(f) = Point1(angle=f(x.Angle), radius=x.Radius)
    static member Circle(n) =
        [ for i in 1..n -> Point1(angle=2.0*Math.PI/float(n), radius=1.0) ]
```

此类的推断的 F # 个类型如下所示：

```fsharp
type Point1 =
    new : unit -> Point1
    new : angle:double * radius:double -> Point1
    static member Circle : n:int -> Point1 list
    member Stretch : l:double -> Point1
    member Warp : f:(double -> double) -> Point1
    member Angle : double
    member Radius : double
```

让我们看看此 F # 类型到程序员使用其他.NET 语言的显示方式。 例如，近似 C#"签名"是，如下所示：

```csharp
// C# signature for the unadjusted Point1 class
public class Point1
{
    public Point1();

    public Point1(double angle, double radius);

    public static Microsoft.FSharp.Collections.List<Point1> Circle(int count);

    public Point1 Stretch(double factor);

    public Point1 Warp(Microsoft.FSharp.Core.FastFunc<double,double> transform);

    public double Angle { get; }

    public double Radius { get; }
}
```

有一些重要事项需要注意有关 F # 如何表示此处构造。 例如：

* 已保留元数据，例如自变量名称。

* F # 方法采用两个参数成为采用两个参数的 C# 方法。

* 函数和列表会变得对 F # 库中的相应类型的引用。

下面的代码演示如何调整此代码，以考虑以下事项。

```fsharp
namespace SuperDuperFSharpLibrary.Types

type RadialPoint(angle:double, radius:double) =

    /// Return a point at the origin
    new() = RadialPoint(angle=0.0, radius=0.0)

    /// The angle to the point, from the x-axis
    member x.Angle = angle

    /// The distance to the point, from the origin
    member x.Radius = radius

    /// Return a new point, with radius multiplied by the given factor
    member x.Stretch(factor) =
        RadialPoint(angle=angle, radius=radius * factor)

    /// Return a new point, with angle transformed by the function
    member x.Warp(transform:Func<_,_>) =
        RadialPoint(angle=transform.Invoke angle, radius=radius)

    /// Return a sequence of points describing an approximate circle using
    /// the given count of points
    static member Circle(count) =
        seq { for i in 1..count ->
                RadialPoint(angle=2.0*Math.PI/float(count), radius=1.0) }
```

推断的 F # 代码的类型，如下所示：

```fsharp
type RadialPoint =
    new : unit -> RadialPoint
    new : angle:double * radius:double -> RadialPoint
    static member Circle : count:int -> seq<RadialPoint>
    member Stretch : factor:double -> RadialPoint
    member Warp : transform:System.Func<double,double> -> RadialPoint
    member Angle : double
    member Radius : double
```

C# 签名现，如下所示：

```csharp
public class RadialPoint
{
    public RadialPoint();

    public RadialPoint(double angle, double radius);

    public static System.Collections.Generic.IEnumerable<RadialPoint> Circle(int count);

    public RadialPoint Stretch(double factor);

    public RadialPoint Warp(System.Func<double,double> transform);

    public double Angle { get; }

    public double Radius { get; }
}
```

修复进行准备以便使用此类型，因为香草.NET 库的一部分，如下所示：

* 调整多个名称： `Point1`， `n`， `l`，和`f`变为`RadialPoint`， `count`， `factor`，和`transform`分别。

* 使用返回类型为`seq<RadialPoint>`而不是`RadialPoint list`通过更改列表构造使用`[ ... ]`序列构造使用`IEnumerable<RadialPoint>`。

* 使用.NET 委托类型`System.Func`而不使用 F # 函数类型。

这使得更不用去涉猎，若要在 C# 代码中使用。
