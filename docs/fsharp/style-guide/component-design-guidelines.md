---
title: F# 组件设计准则
description: 了解用于编写 F# 面向消费由其他调用方的组件的准则。
ms.date: 05/14/2018
ms.openlocfilehash: 446cba0f810af9517b655ef5741ddf7a919676d5
ms.sourcegitcommit: db8b83057d052c1f9f249d128b08d4423af0f7c2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/02/2018
ms.locfileid: "43488282"
---
# <a name="f-component-design-guidelines"></a>F# 组件设计准则

本文档是一组 F# 编程，基于 F# 组件设计准则，v14，Microsoft Research 的组件设计准则并[另一个版本](https://fsharp.org/specs/component-design-guidelines/)最初策划的和由 F# 软件基金会维护。

本文档假定您熟悉 F# 编程。 非常感谢 F# 社区的贡献和在本指南的各个版本的有用反馈。

## <a name="overview"></a>概述

本文档探讨一些与 F# 组件设计和编码相关的问题。 组件可能意味着以下任一项：

* 具有该项目中的外部使用者在 F# 项目中的层。
* 跨程序集边界中用于 F# 代码使用库。
* 跨程序集边界的任何.NET 语言适用于使用一个库。
* 一个库，如适用于通过包存储库，将其分发[NuGet](https://nuget.org)。

请按照本文中所述的技术[优秀的 F# 代码的五个原则](index.md#five-principles-of-good-f-code)，因此利用同时功能和对象根据编程。

方法，无论组件和库设计器时尝试创建一个 API，开发人员可以非常轻松地使用人脸可行且十分普通的问题的数。 下降的应用程序[.NET 类库设计准则](../../standard/design-guidelines/index.md)将引导你创建一组一致的愉快，若要使用的 Api。

## <a name="general-guidelines"></a>通用准则

有几个通用指导原则应用于 F# 库，而不考虑在库的目标受众。

### <a name="learn-the-net-library-design-guidelines"></a>了解.NET 类库设计准则

不论哪种 F# 编码执行操作，非常有价值有实际的了解[.NET 类库设计准则](../../standard/design-guidelines/index.md)。 大多数其他 F# 和.NET 编程人员将熟悉这些指导原则，并期望.NET 代码，以符合它们。

.NET 类库设计准则提供常规指南有关命名、 设计类和接口、 成员 （属性、 方法、 事件等） 的设计和的详细信息，并且引用的各种设计指南的有用的第一个点。

### <a name="add-xml-documentation-comments-to-your-code"></a>将 XML 文档注释添加到你的代码

公共 Api 的 XML 文档，请确保用户可以获得很好的 Intellisense 和快速信息，使用这些类型和成员，以及启用生成文档文件的库时。 请参阅[XML 文档](../language-reference/xml-documentation.md)有关各种可用于其他标记内 xmldoc 注释的 xml 标记。

```fsharp
/// A class for representing (x,y) coordinates
type Point =

    /// Computes the distance between this point and another
    member DistanceTo : otherPoint:Point -> float
```

您可以使用缩写形式 XML 注释 (`/// comment`)，或标准的 XML 注释 (`///<summary>comment</summary>`)。

### <a name="consider-using-explicit-signature-files-fsi-for-stable-library-and-component-apis"></a>请考虑使用稳定的库和组件 Api 显式签名文件 (.fsi)

使用 F# 库中的显式签名文件提供简洁的公共 API，这两者都可帮助确保，你知道你的库的完整公共接口，以及提供完全分离之间公共文档和内部摘要实现详细信息。 请注意，签名文件会将冲突添加到更改公共 API，通过要求在实现和签名文件中进行更改。 因此，签名文件通常只时应引入 API 变得日臻完善和不再需要显著更改。

### <a name="always-follow-best-practices-for-using-strings-in-net"></a>在.NET 中使用字符串的最佳实践，应始终遵循

请按照[在.NET 中使用字符串的最佳做法](../../standard/base-types/best-practices-strings.md)指南。 具体而言，始终显式声明*区域性意向*中转换和比较字符串 （如果适用）。

## <a name="guidelines-for-f-facing-libraries"></a>F# 的准则-面向库

本部分提供了建议，用于确定公共 F#-面向库;也就是说，公开旨在由 F# 开发人员使用的公共 Api 的库。 有特定于 F# 适用的各种库设计建议。 如果没有按照具体建议，.NET 类库设计准则是回退的指南。

### <a name="naming-conventions"></a>命名约定

#### <a name="use-net-naming-and-capitalization-conventions"></a>使用.NET 命名和大小写约定

下表遵循.NET 命名和大小写约定。 有小添加项。 还包括 F# 构造。

| 构造 | Case | 部件 | 示例 | 说明 |
|-----------|------|------|----------|-------|
| 具体的类型 | Pascal 命名法 | 名词 / 形容词 | 列表中，双精度，复杂 | 具体类型是结构、 类、 枚举、 委托、 记录和联合。 尽管类型名称是传统上在 OCaml 小写，但 F# 已采用了.NET 类型的命名方案。
| DLL           | Pascal 命名法 |                 | Fabrikam.Core.dll |  |
| 联合标记     | Pascal 命名法 | 名词 | 一些，添加成功 | 不要在公共 Api 中使用前缀。 （可选） 使用的前缀时内部的例如 '' 键入团队 = TAlpha | TBeta | TDelta。 ' ' |
| 事件          | Pascal 命名法 | 谓词 | ValueChanged / ValueChanging |  |
| 异常     | Pascal 命名法 |      | WebException | 名称应以"Exception"结尾。 |
| 字段          | Pascal 命名法 | 名词 | CurrentName  | |
| 接口类型 |  Pascal 命名法 | 名词 / 形容词 | IDisposable | 名称应以"I"开头。 |
| 方法 |  Pascal 命名法 |  谓词 | ToString | |
| 命名空间 | Pascal 命名法 | | Microsoft.FSharp.Core | 通常情况下使用`<Organization>.<Technology>[.<Subnamespace>]`，但是如果独立于组织的技术是删除组织。 |
| 参数 | 驼峰式大小写 | 名词 |  类型名称、 转换、 范围 | |
| 允许值 （内部） | 驼峰式大小写或 pascal 命名法 | 名词 / 动词 |  getValue myTable |
| 允许值 （外部） | 驼峰式大小写或 pascal 命名法 | 名词/动词  | List.map Dates.Today | let 绑定值通常是公共的遵循传统的功能性设计模式时。 但是，通常使用 pascal 命名法标识符可以使用从其他.NET 语言时如此。 |
| 属性  | Pascal 命名法  | 名词 / 形容词  | IsEndOfFile，背景色  | 布尔型属性通常使用是的可以并应该是肯定的如 IsEndOfFile，不 IsNotEndOfFile 中所示。

#### <a name="avoid-abbreviations"></a>避免缩写

.NET 指南不鼓励使用缩写的使用 (例如，"使用`OnButtonClick`而非`OnBtnClick`")。 常见的缩写词，如`Async`允许为"异步"。 对函数式编程; 有时还会忽略此准则例如，`List.iter`用于一个缩写词"迭代"。 出于此原因，使用缩写形式通常是可以容忍 F# 中是更大-到-F# 编程，但仍通常应避免在公共组件设计中。

#### <a name="avoid-casing-name-collisions"></a>避免名称冲突的大小写

.NET 指南中指出，单独的大小写不能用于消除名称冲突，因为某些客户端语言 (例如，Visual Basic 中) 都不区分大小写。

#### <a name="use-acronyms-where-appropriate"></a>在适用处使用首字母缩写词

首字母缩写词，如 XML 不缩写和首字母未大写形式 (Xml) 的.NET 库中广泛使用。 仅应使用的已知的普遍公认首字母缩写词。

#### <a name="use-pascalcase-for-generic-parameter-names"></a>为泛型参数名称使用 pascal 命名法

执行操作的公共 Api，包括 F# 中的泛型参数名称使用 pascal 命名法-面向库。 具体而言，使用类似的名称`T`， `U`， `T1`，`T2`任意泛型参数，和特定名称很有用，然后对于 F# 的面向公众的库使用类似的名称`Key`， `Value`， `Arg`(但不是能， `TKey`)。

#### <a name="use-either-pascalcase-or-camelcase-for-public-functions-and-values-in-f-modules"></a>有关公共函数和 F# 模块中的值使用 pascal 命名法或驼峰式大小写

对于设计用于的公共函数使用驼峰式大小写不合格 (例如， `invalidArg`)，以及"标准集合函数"（例如，List.map）。 在这两个这些情况下，函数名称作用类似语言中的关键字。

### <a name="object-type-and-module-design"></a>对象、 类型和模块的设计

#### <a name="use-namespaces-or-modules-to-contain-your-types-and-modules"></a>使用命名空间或模块包含类型和模块

在组件中的每个 F# 文件应命名空间声明或模块声明开头。

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

使用模块和命名空间来组织代码最高级别之间的区别是，如下所示：

* 命名空间可以跨多个文件
* 命名空间不能包含 F# 函数，除非它们是内部模块内
* 为任何给定模块的代码必须包含在单个文件
* 顶级模块可以包含 F# 函数，而无需内部模块

顶级命名空间或模块之间的选择会影响代码的已编译的形式，因此将影响其他.NET 语言中的视图应 API 最终使用 F# 代码之外。

#### <a name="use-methods-and-properties-for-operations-intrinsic-to-object-types"></a>使用方法和属性的对象类型中的内部操作

当使用对象，最好以确保可使用的功能作为方法和对该类型的属性。

```fsharp
type HardwareDevice() =

    member this.ID = ...

    member this.SupportedProtocols = ...

type HashTable<'Key,'Value>(comparer: IEqualityComparer<'Key>) =

    member this.Add(key, value) = ...

    member this.ContainsKey(key) = ...

    member this.ContainsValue(value) = ...
```

给定成员的大容量的功能需要不一定在中实现该成员，但应为可使用项的功能。

#### <a name="use-classes-to-encapsulate-mutable-state"></a>使用类来封装的可变状态

在 F# 中，这只需完成的状态未已封装由另一个语言构造，如闭包、 序列表达式或异步计算。

```fsharp
type Counter() =
    // let-bound values are private in classes.
    let mutable count = 0

    member this.Next() =
        count <- count + 1
        count
```

#### <a name="use-interfaces-to-group-related-operations"></a>使用接口来分组相关的操作

使用接口类型来表示一组操作。 这是优先于其他选项，例如元组的函数或函数的记录。

```fsharp
type Serializer =
    abstract Serialize<'T> : preserveRefEq: bool -> value: 'T -> string
    abstract Deserialize<'T> : preserveRefEq: bool -> pickle: string -> 'T
```

在优先于：

```fsharp
type Serializer<'T> = {
    Serialize : bool -> 'T -> string
    Deserialize : bool -> string -> 'T
}
```

接口是在.NET 中，这可用于实现什么函子将通常为您提供的第一级概念。 此外，它们可以用于编码为您的程序，记录的函数不能存在的类型。

#### <a name="use-a-module-to-group-functions-which-act-on-collections"></a>在集合上使用组函数执行操作的模块

在定义集合类型时，请考虑提供一组标准的操作等`CollectionType.map`和`CollectionType.iter`) 的新集合类型。

```fsharp
module CollectionType =
    let map f c =
        ...
    let iter f c =
        ...
```

如果包含此类模块，请按照找到 FSharp.Core 中的函数的标准命名约定。

#### <a name="use-a-module-to-group-functions-for-common-canonical-functions-especially-in-math-and-dsl-libraries"></a>对于常见的规范函数，特别是在数学和 DSL 库使用的模块组函数

例如，`Microsoft.FSharp.Core.Operators`是一个自动打开顶层函数的集合 (如`abs`和`sin`) 提供的 FSharp.Core.dll。

同样，一个库，统计信息可能包括具有函数的模块`erf`和`erfc`，而此模块用于显式或自动打开。

#### <a name="consider-using-requirequalifiedaccess-and-carefully-apply-autoopen-attributes"></a>请考虑使用 RequireQualifiedAccess 并仔细应用 AutoOpen 特性

添加`[<RequireQualifiedAccess>]`对模块的特性指示模块不能打开，并且对模块的元素的引用需要显式限定访问权限。 例如，`Microsoft.FSharp.Collections.List`模块具有此属性。

当函数和模块中的值具有名称可能与其他模块中的名称发生冲突时，这很有用。 需要限定的访问可以极大地提高的长期可维护性和可进化性的库。

添加`[<AutoOpen>]`对模块的属性就意味着，打开包含的命名空间时将打开该模块。 `[<AutoOpen>]`还可以将特性应用于程序集可指示模块引用的程序集时自动打开。

例如，统计信息库**MathsHeaven.Statistics**可能包含`module MathsHeaven.Statistics.Operators`包含函数`erf`和`erfc`。 它是合理地将标记为此模块`[<AutoOpen>]`。 这意味着`open MathsHeaven.Statistics`还将打开此模块并将名称`erf`和`erfc`纳入范围。 使用另一个良好`[<AutoOpen>]`是包含扩展方法的模块。

使用过度的`[<AutoOpen>]`导致受到污染命名空间和该属性应谨慎使用。 特定库中特定域，明智地使用`[<AutoOpen>]`可能会导致更好的可用性。

#### <a name="consider-defining-operator-members-on-classes-where-using-well-known-operators-is-appropriate"></a>请考虑在其中使用众所周知的运算符是适当的类上定义运算符成员

有时类用于建模数学构造，例如向量。 当要建模的域具有众所周知的运算符时，将其定义为类中的内部成员非常有用。

```fsharp
type Vector(x:float) =

    member v.X = x

    static member (*) (vector:Vector, scalar:float) = Vector(vector.X * scalar)

    static member (+) (vector1:Vector, vector2:Vector) = Vector(vector1.X + vector2.X)

let v = Vector(5.0)

let u = v * 10.0
```

本指南对应于这些类型的常规.NET 指南。 但是，它可以在 F# 编写代码因为这会使与 F# 函数一起使用和与成员约束，例如 List.sumBy 方法中使用这些类型非常重要。

#### <a name="consider-using-compiledname-to-provide-a-net-friendly-name-for-other-net-language-consumers"></a>请考虑使用 CompiledName 来提供。其他.NET 语言的使用者的 NET 的友好名称

有时你可能想要的 F# 使用者名称中一种样式的某些内容 (例如，以使其显示的小写形式是静态成员，就好像模块绑定函数)，但编译为程序集时具有不同的样式的名称。 可以使用`[<CompiledName>]`要为非 F# 代码使用程序集提供不同的样式属性。

```fsharp
type Vector(x:float, y:float) =

    member v.X = x
    member v.Y = y

    [<CompiledName("Create")>]
    static member create x y = Vector (x, y)

let v = Vector.create 5.0 3.0
```

通过使用`[<CompiledName>]`，可以为非 F# 程序集的使用者使用的.NET 命名约定。

#### <a name="use-method-overloading-for-member-functions-if-doing-so-provides-a-simpler-api"></a>如果这样做将提供更简单的 API，使用方法重载的成员函数

方法重载是功能强大的工具，用于简化一个 API，可能需要执行类似的功能，但具有不同的选项或参数。

```fsharp
type Logger() =

    member this.Log(message) =
        ...
    member this.Log(message, retryPolicy) =
        ...
```

在 F# 中，它是更常见的是重载的参数数目而不是参数的类型。

#### <a name="hide-the-representations-of-record-and-union-types-if-the-design-of-these-types-is-likely-to-evolve"></a>这些类型的设计是可能会不断变化的情况下隐藏的记录和联合类型的表示形式

避免泄露具体对象的表示形式。 例如，具体的表现形式的<xref:System.DateTime>值不会显示由外部的公共 API 的.NET 库设计。 在运行时，公共语言运行时知道将在整个执行过程中使用的提交的实现。 但是，已编译的代码不本身选取上具体的表现形式的依赖项。

#### <a name="avoid-the-use-of-implementation-inheritance-for-extensibility"></a>避免使用实现继承的可扩展性

在 F# 中，很少使用实现继承。 此外，继承层次结构通常是将复杂且难以实现，若要更改新的要求到达时。 继承实现仍存在于 F# 兼容性和极少数情况下，它是最佳解决方案到问题，但多态性，如接口实现的设计时，应在 F# 程序中查找其他方法。

### <a name="function-and-member-signatures"></a>函数和成员签名

#### <a name="use-tuples-for-return-values-when-returning-a-small-number-of-multiple-unrelated-values"></a>返回值返回少量的多个不相关的值时使用元组

下面是在返回类型中使用元组的一个很好示例：

```fsharp
val divrem : BigInteger -> BigInteger -> BigInteger * BigInteger
```

对于返回类型包含许多组件，或如果单个身份实体与相关组件，应考虑使用命名的类型而不元组。

#### <a name="use-asynct-for-async-programming-at-f-api-boundaries"></a>使用`Async<T>`有关 F# API 边界处的异步编程

如果没有名为相应的同步操作`Operation`，它返回`T`，则应命名为异步操作`AsyncOperation`如果它返回`Async<T>`或`OperationAsync`如果它返回`Task<T>`。 对于常用的.NET 类型公开 Begin/End 方法，请考虑使用`Async.FromBeginEnd`将扩展方法为提供的.NET Api 到 F# 异步编程模型的外观。

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

请参阅[错误管理](conventions.md#error-management)若要了解如何正确使用的异常、 结果和选项。

### <a name="extension-members"></a>扩展成员

#### <a name="carefully-apply-f-extension-members-in-f-to-f-components"></a>小心地将应用 F# 中的 F# 扩展成员-到-F# 组件

F# 扩展成员通常只应与在其模式使用大多数类型关联的内部操作的闭包中的操作。 一种常见用途是提供各种.NET 类型到 F# 更常用的 Api:

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

#### <a name="use-discriminated-unions-instead-of-class-hierarchies-for-tree-structured-data"></a>而不是类层次结构的可区分的联合用于树结构化数据

类似于树的结构是以递归方式定义。 这是包含继承、 困难但简洁的可区分联合。

```fsharp
type BST<'T> =
    | Empty
    | Node of 'T * BST<'T> * BST<'T>
```

表示可区分联合使用类似于树中的数据还使你可以从 exhaustiveness 在模式匹配中受益。

#### <a name="use-requirequalifiedaccess-on-union-types-whose-case-names-are-not-sufficiently-unique"></a>使用`[<RequireQualifiedAccess>]`上其大小写的名称不是足够唯一的联合类型

您可能发现自己在其中相同的名称是用于执行不同操作，例如可区分联合用例的最佳名称的域中。 可以使用`[<RequireQualifiedAccess>]`区分大小写的名称以避免触发由于隐藏依赖于的排序的混淆错误`open`语句

#### <a name="hide-the-representations-of-discriminated-unions-for-binary-compatible-apis-if-the-design-of-these-types-is-likely-to-evolve"></a>这些类型的设计是可能会不断变化的情况下隐藏二进制兼容的 Api 可区分联合的表示形式

联合类型依赖于 F# 模式匹配窗体的简洁的编程模型。 正如前面提到的应避免泄露具体数据表示形式，如果这些类型的设计是可能会不断变化。

例如，可区分联合的表示形式可以隐藏使用私有或内部声明，或通过使用签名文件。

```fsharp
type Union =
    private
    | CaseA of int
    | CaseB of string
```

如果不加选择地显示可区分的联合，你可能会发现它很难版本库而不会中断用户代码。 相反，应考虑显示一个或多个活动的模式，以允许针对您的类型的值的模式匹配。

活动模式提供 F# 使用者提供的模式匹配同时避免了直接公开 F# 联合类型的替代方法。

### <a name="inline-functions-and-member-constraints"></a>内联函数和成员约束

#### <a name="define-generic-numeric-algorithms-using-inline-functions-with-implied-member-constraints-and-statically-resolved-generic-types"></a>定义泛型数值算法中使用内联函数的隐式的成员约束和静态解析的泛型类型

算术成员约束和 F# 比较约束是 F# 编程的标准。 例如，考虑以下代码：

```fsharp
let inline highestCommonFactor a b =
    let rec loop a b =
        if a = LanguagePrimitives.GenericZero<_> then b
        elif a < b then loop a (b - a)
        else loop (a - b) b
    loop a b
```

此函数的类型是按如下所示：

```fsharp
val inline highestCommonFactor : ^T -> ^T -> ^T
                when ^T : (static member Zero : ^T)
                and ^T : (static member ( - ) : ^T * ^T -> ^T)
                and ^T : equality
                and ^T : comparison
```

这是合适的函数的数学库中的公共 API。

#### <a name="avoid-using-member-constraints-to-simulate-type-classes-and-duck-typing"></a>避免使用成员约束来模拟类型的类和鸭子类型化

可以模拟"鸭子类型键入"使用 F# 成员约束。 但是，成员，从而使利用这一点不在常规中应使用 F#-到-F# 库设计。 这是因为基于不熟悉或非标准的隐式约束的库设计可能会导致用户代码会变得不灵活且绑定到一个特定的框架模式。

此外，还有很可能会大量使用这种方式中的成员约束可能会很长的编译时间。

### <a name="operator-definitions"></a>运算符定义

#### <a name="avoid-defining-custom-symbolic-operators"></a>避免定义自定义的符号运算符

自定义运算符至关重要，在某些情况下，大量的实现代码中非常有用符号设备。 对于库的新用户，命名的函数通常是易于使用。 此外，自定义的符号运算符可能很难到文档中，并且用户找到更难以查找运算符，由于 IDE 和搜索引擎中的现有限制的帮助。

因此，最好发布您的功能作为命名的函数和成员，并仅当符号好处超过的文档和认知成本经历此外公开此功能的运算符。

### <a name="units-of-measure"></a>度量单位

#### <a name="carefully-use-units-of-measure-for-added-type-safety-in-f-code"></a>仔细的添加了的类型安全性，F# 代码中使用度量的单位

其他.NET 语言在查看时，将清除其他单元的度量值的类型化信息。 请注意，.NET 组件、 工具和反射将看到 san 单位类型。 例如，C# 使用者将看到`float`而非`float<kg>`。

### <a name="type-abbreviations"></a>类型缩写

#### <a name="carefully-use-type-abbreviations-to-simplify-f-code"></a>小心地使用类型缩写来简化 F# 代码

.NET 组件、 工具和反射不会看到类型的缩写的名称。 类型缩写的重要使用情况还可以显示比它变得更加复杂实际上是，这可以给消费者带来困惑的域。

#### <a name="avoid-type-abbreviations-for-public-types-whose-members-and-properties-should-be-intrinsically-different-to-those-available-on-the-type-being-abbreviated"></a>避免其成员和属性应为本质上不同可用正在缩写的类型的公共类型的类型缩写

在这种情况下，被缩写的类型将显示有关正在定义的实际类型的表示形式的过多信息。 相反，包装类类型或单用例可区分的联合中的缩写，请考虑 （或基本性能时，请考虑使用结构类型来包装缩写）。

例如，它很容易定义多重映射作为一种特殊情况的 F# 地图，例如：

```fsharp
type MultiMap<'Key,'Value> = Map<'Key,'Value list>
```

但是，此类型上的逻辑点表示法操作不是在地图上的操作相同 – 例如，它是合理 lookup 运算符映射。[key] 返回空列表如果该键不在字典中，而不引发异常。

## <a name="guidelines-for-libraries-for-use-from-other-net-languages"></a>用于从其他.NET 语言中使用的库的指导原则

在设计时从其他.NET 语言中使用的库，它是必须遵守[.NET 类库设计准则](../../standard/design-guidelines/index.md)。 在本文档中，这些库标记为普通的.NET 库，而不是 F#-不受限制地面向使用 F# 库构造。 设计普通的.NET 库意味着提供大家所熟悉且惯用 Api 与.NET Framework 的其余部分一致的最大程度减少使用 F# 的公共 API 中的特定构造。 以下各节中介绍了这些规则。

### <a name="namespace-and-type-design-for-libraries-for-use-from-other-net-languages"></a>Namespace 和类型设计 （适用于从其他.NET 语言中使用的库）

#### <a name="apply-the-net-naming-conventions-to-the-public-api-of-your-components"></a>适用于您的组件的公共 API 的.NET 命名约定

应特别注意的缩写的名称和.NET 的大小写准则的使用。

```fsharp
type pCoord = ...
    member this.theta = ...

type PolarCoordinate = ...
    member this.Theta = ...
```

#### <a name="use-namespaces-types-and-members-as-the-primary-organizational-structure-for-your-components"></a>使用命名空间、 类型和成员作为您的组件的主要组织结构

包含公共功能的所有文件应都以开头`namespace`声明，以及命名空间中唯一的面向公众的实体应为类型。 不要使用 F# 模块。

使用非公共模块用于保存实现代码、 实用程序类型和实用工具函数。

静态类型应当优先于模块，因为它们支持的 API 的未来发展使用重载和其他不能使用 F# 模块中的.NET API 设计概念。

例如，替代以下公共 API:

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

#### <a name="use-f-record-types-in-vanilla-net-apis-if-the-design-of-the-types-wont-evolve"></a>如果类型的设计不会改进在传统的.NET Api 中使用 F# 记录类型

F# 记录类型编译为一个简单的.NET 类。 这些是适用于 Api 中的一些简单的稳定类型。 应考虑使用`[<NoEquality>]`和`[<NoComparison>]`特性禁止显示自动生成的接口。 此外还应避免使用传统的.NET Api 中的可变记录字段作为这些公开一个公共字段。 应始终考虑到一个类是否将提供更灵活的 api 选项未来的发展。

例如，下面的 F# 代码公开给 C# 使用者的公共 API:

F# 中：

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

#### <a name="hide-the-representation-of-f-union-types-in-vanilla-net-apis"></a>隐藏 F# 联合类型的传统的.NET Api 中的表示形式

F# 联合类型不常用跨组件边界，即使对于 F#-到-F# 编写代码。 它们是一个极好实现设备时在组件和库内部使用。

在设计时传统的.NET API，请考虑使用专用的声明或签名文件中隐藏的联合类型的表示形式。

```fsharp
type PropLogic =
    private
    | And of PropLogic * PropLogic
    | Not of PropLogic
    | True
```

您可能会通过扩充联合的表示形式在内部使用与成员提供所需的类型。面向 NET 的 API。

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

#### <a name="design-gui-and-other-components-using-the-design-patterns-of-the-framework"></a>设计 GUI 和其他组件使用的 framework 的设计模式

在.NET 中，如 WinForms、 WPF 和 ASP.NET 提供了很多不同框架。 如果您正在设计用于在这些框架中使用的组件，应使用为每个命名和设计的约定。 例如，对于 WPF 编程中，采用设计的类的 WPF 设计的模式。 对于在用户界面编程模型，使用设计模式，例如事件，例如那些基于通知的集合中找到<xref:System.Collections.ObjectModel>。

### <a name="object-and-member-design-for-libraries-for-use-from-other-net-languages"></a>对象和成员设计 （适用于从其他.NET 语言中使用的库）

#### <a name="use-the-clievent-attribute-to-expose-net-events"></a>使用 CLIEvent 特性来公开.NET 事件

构造`DelegateEvent`与特定的.NET 委托采用对象的类型和`EventArgs`(而非`Event`，它只需使用`FSharpHandler`类型默认情况下)，以便事件要发布的方式与其他.NET 语言熟悉。

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

#### <a name="expose-asynchronous-operations-as-methods-which-return-net-tasks"></a>将异步操作公开为方法返回.NET 任务

在.NET 中使用任务来表示活动的异步计算。 任务是通常比 F# 不太复合`Async<T>`对象，因为它们表示"已在执行"任务，不能为一起组合方式执行并行组合，或其中隐藏取消信号和其他传播上下文参数。

但是，尽管如此，返回任务的方法是在.NET 异步编程的标准表示形式。

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

#### <a name="use-net-delegate-types-instead-of-f-function-types"></a>使用.NET 委托类型，而不是 F# 函数类型

此处"F# 函数类型"的含义"箭头"类型如`int -> int`。

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

F# 函数类型显示为`class FSharpFunc<T,U>`到了其他.NET 语言，并不太适用于了解委托类型的语言功能和工具。 创建面向.NET Framework 3.5 或更高版本，一个更高序位方法时`System.Func`和`System.Action`委托是正确的 Api 来发布使.NET 开发人员能够以低冲突的方式使用这些 Api。 (时定目标到.NET Framework 2.0，会限制更多系统定义的委托类型; 请考虑使用预定义的委托类型，如`System.Converter<T,U>`或定义特定委托类型。)

另一方面，.NET 委托不是 F# 自然的面向库 (请参阅下一步部分 F#-面向库)。 常见的实现策略开发普通的.NET 库的更高序位方法时，结果是编写所有使用 F# 函数类型的实现，然后创建使用委托作为在实际 F# 的精简外观的公共 API实现。

#### <a name="use-the-trygetvalue-pattern-instead-of-returning-f-option-values-and-prefer-method-overloading-to-taking-f-option-values-as-arguments"></a>使用 TryGetValue 模式而不是返回的 F# 选项值，并更喜欢方法重载，则可以考虑作为参数的 F# 选项值

在 Api 中的 F# 选项类型使用的常见模式是更好地实现在传统的.NET Api 使用标准.NET 设计技术。 而不是返回的 F# 选项值，请考虑使用 bool 返回类型以及如"TryGetValue"模式中所示的输出参数。 而不会采用 F# 选项值作为参数，请考虑使用方法重载或可选参数。

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

#### <a name="use-the-net-collection-interface-types-ienumerablet-and-idictionarykeyvalue-for-parameters-and-return-values"></a>使用.NET 集合接口类型 IEnumerable\<T\>和 IDictionary\<键，值\>参数和返回值

避免使用具体集合类型，如.NET 数组`T[]`，F# 类型`list<T>`，`Map<Key,Value>`并`Set<T>`，和.NET 具体集合类型，如`Dictionary<Key,Value>`。 .NET 类库设计准则有好的建议，有关何时使用各种集合类型，如`IEnumerable<T>`。 某些使用数组 (`T[]`) 是可以接受在某些情况下，性能的基础上。 请注意，尤其是`seq<T>`是只是 F# 的别名`IEnumerable<T>`，并因此 seq 通常是一个普通的.NET API 的相应类型。

而不是 F# 列表：

```fsharp
member this.PrintNames(names : string list) =
    ...
```

使用 F# 序列：

```fsharp
member this.PrintNames(names : seq<string>) =
    ...
```

#### <a name="use-the-unit-type-as-the-only-input-type-of-a-method-to-define-a-zero-argument-method-or-as-the-only-return-type-to-define-a-void-returning-method"></a>使用作为唯一的一种方法的输入类型的单位类型定义的零参数方法，或作为唯一返回类型来定义返回 void 的方法

避免单位类型的其他用法。 这些是很好：

```fsharp
✔ member this.NoArguments() = 3

✔ member this.ReturnVoid(x : int) = ()
```

这是错误的：

```fsharp
member this.WrongUnit( x:unit, z:int) = ((), ())
```

#### <a name="check-for-null-values-on-vanilla-net-api-boundaries"></a>检查在普通的.NET API 边界上的 null 值

F# 实现代码往往具有较少的 null 值，原因不可变的设计模式和使用的 F# 类型的 null 文本的限制。 其他.NET 语言通常使用 null 值频繁得多。 正因为如此，F# 代码公开了一个普通的.NET API 应该检查的 API 边界上的 null 参数，并防止这些值更深层次流入 F# 实现代码。 `isNull`函数或模式进行匹配`null`，可以使用模式。

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

相反，更倾向于返回命名的类型保存聚合数据，或使用 out 参数返回多个值。 尽管在.NET 中存在的元组和结构元组 （包括 C# 语言支持的结构元组），它们将最常提供理想和预期 API.NET 开发人员。

#### <a name="avoid-the-use-of-currying-of-parameters"></a>避免使用科的参数

请改用.NET 调用约定``Method(arg1,arg2,…,argN)``。

```fsharp
member this.TupledArguments(str, num) = String.replicate num str
```

提示： 如果您正在设计用于从任何.NET 语言中使用库，则没有什么可以替代实际执行的一些试验性 C# 和 Visual Basic 编程，确保您的库"感觉右"这些语言的操作。 此外可以使用.NET Reflector 和 Visual Studio 对象浏览器等工具来确保库和它们的文档显示预期的开发人员。

## <a name="appendix"></a>附录

### <a name="end-to-end-example-of-designing-f-code-for-use-by-other-net-languages"></a>由其他.NET 语言设计用于 F# 代码的端到端示例

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

推断的 F# 类型的此类是按如下所示：

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

让我们看一看此 F# 类型到使用另一种.NET 语言的程序员的显示方式。 例如，近似 C#"签名"是按如下所示：

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

有一些要注意 F# 如何表示构造此处的要点。 例如：

* 保留元数据，例如参数名称。

* 采用两个参数的 F# 方法成为 C# 方法采用两个自变量。

* 函数和列表会变得对 F# 库中的相应类型的引用。

下面的代码演示如何调整该代码需要考虑这些内容。

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

推断出的 F# 类型的代码如下所示：

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

C# 签名现在如下所示：

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

进行了修复，以准备用于此类型，因为普通的.NET 库的一部分，如下所示：

* 调整多个名称： `Point1`， `n`， `l`，和`f`变得`RadialPoint`， `count`， `factor`，和`transform`分别。

* 使用返回类型为`seq<RadialPoint>`而不是`RadialPoint list`通过更改列表构造使用`[ ... ]`序列构造使用`IEnumerable<RadialPoint>`。

* 使用.NET 委托类型`System.Func`而不是 F# 函数类型。

这样，就得好多了要在 C# 代码中使用。
