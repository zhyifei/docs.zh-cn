---
title: 可区分联合
description: 了解如何使用 F# 歧视结合。
ms.date: 05/16/2016
ms.openlocfilehash: 539e2843c0bbc8c5ac9c0597ffc5443f8cd127f8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/14/2020
ms.locfileid: "79401069"
---
# <a name="discriminated-unions"></a>可区分联合

歧视联合为值提供支持，这些值可以是许多命名案例之一，可能每个值和类型不同。 受歧视结合对异构数据很有用;可能有特殊情况的数据，包括有效和错误案例;因类型而异的数据;并作为小对象层次结构的替代方案。 此外，递归区分结合用于表示树数据结构。

## <a name="syntax"></a>语法

```fsharp
[ attributes ]
type [accessibility-modifier] type-name =
    | case-identifier1 [of [ fieldname1 : ] type1 [ * [ fieldname2 : ] type2 ...]
    | case-identifier2 [of [fieldname3 : ]type3 [ * [ fieldname4 : ]type4 ...]

    [ member-list ]
```

## <a name="remarks"></a>备注

歧视联合与其他语言中的联合类型类似，但存在差异。 与 C++ 中的联合类型或 Visual Basic 中的变体类型一样，存储在值中的数据不是固定的;它可以是几个不同的选项之一。 但是，与这些其他语言中的联合不同，每个可能的选项都给定一个*案例标识符*。 案例标识符是此类型对象可能具有的各种可能类型的值的名称;值是可选的。 如果不存在值，则大小写等效于枚举大小写。 如果存在值，则每个值可以是指定类型的单个值，也可以是聚合相同或不同类型的多个字段的元组。 您可以为单个字段指定名称，但该名称是可选的，即使在同一情况下命名了其他字段也是如此。

受歧视联合的可访问性`public`默认为 。

例如，请考虑以下形状类型的声明。

```fsharp
type Shape =
    | Rectangle of width : float * length : float
    | Circle of radius : float
    | Prism of width : float * float * height : float
```

前面的代码声明一个受歧视的联合形状，它可以具有三种情况中的任何一个的值：矩形、圆体和棱镜。 每个案例都有一组不同的字段。 矩形大小写有两个命名字段，两个`float`命名字段的类型，具有名称宽度和长度。 圆大小写只有一个命名字段，半径。 棱镜大小写有三个字段，其中两个字段（宽度和高度）被命名为字段。 未命名的字段称为匿名字段。

通过根据以下示例为命名字段和匿名字段提供值来构造对象。

```fsharp
let rect = Rectangle(length = 1.3, width = 10.0)
let circ = Circle (1.0)
let prism = Prism(5., 2.0, height = 3.0)
```

此代码显示，您可以在初始化中使用命名字段，也可以依赖声明中字段的顺序，并依次为每个字段提供值。 上一个代码`rect`中的构造函数调用使用命名字段，但构造函数调用`circ`使用排序。 可以混合有序字段和命名字段，如 在 构造 中`prism`。

该`option`类型是 F# 核心库中的简单区分联合。 类型`option`声明如下。

```fsharp
// The option type is a discriminated union.
type Option<'a> =
    | Some of 'a
    | None
```

前面的代码指定类型`Option`是具有两个案例的受歧视联合，`Some`和`None`。 案例`Some`具有一个关联值，该值由一个匿名字段组成，其类型由类型`'a`参数表示。 案例`None`没有关联的值。 因此，`option`类型指定具有特定类型值或无值的泛型类型。 类型`Option`还有一个小写类型别名`option`，这是更常用的。

案例标识符可用作区分联合类型的构造函数。 例如，以下代码用于创建`option`类型的值。

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2001.fs)]

大小写标识符也用于模式匹配表达式。 在模式匹配表达式中，为与单个情况关联的值提供标识符。 例如，在以下代码中，`x`是给定与`Some``option`类型大小写关联的值的标识符。

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2002.fs)]

在模式匹配表达式中，可以使用命名字段指定受区别的联合匹配。 对于以前声明的 Shape 类型，可以使用命名字段，如以下代码所示，以提取字段的值。

```fsharp
let getShapeWidth shape =
    match shape with
    | Rectangle(width = w) -> w
    | Circle(radius = r) -> 2. * r
    | Prism(width = w) -> w
```

通常，可以使用案例标识符，而无需使用联合名称对其进行限定。 如果希望名称始终与联合的名称限定，则可以将["需要限定Access"](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.requirequalifiedaccessattribute-class-[fsharp])属性应用于联合类型定义。

### <a name="unwrapping-discriminated-unions"></a>未包装的受歧视联合

在 F# 中，区分联合通常用于域建模，用于包装单个类型。 通过模式匹配也很容易提取基础值。 不需要对单个情况使用匹配表达式：

```fsharp
let ([UnionCaseIdentifier] [values]) = [UnionValue]
```

下面的示例演示这一操作：

```fsharp
type ShaderProgram = | ShaderProgram of id:int

let someFunctionUsingShaderProgram shaderProgram =
    let (ShaderProgram id) = shaderProgram
    // Use the unwrapped value
    ...
```

模式匹配也直接允许在函数参数中进行，因此您可以在那里打开单个大小写：

```fsharp
let someFunctionUsingShaderProgram (ShaderProgram id) =
    // Use the unwrapped value
    ...
```

## <a name="struct-discriminated-unions"></a>结构歧视联盟

您还可以将"受歧视联合"表示为结构。  这使用属性`[<Struct>]`完成。

```fsharp
[<Struct>]
type SingleCase = Case of string

[<Struct>]
type Multicase =
    | Case1 of Case1 : string
    | Case2 of Case2 : int
    | Case3 of Case3 : double
```

由于这些值类型而不是引用类型，因此与引用区分结合相比，存在额外的注意事项：

1. 它们作为值类型复制，并且具有值类型语义。
2. 不能使用具有多大小写结构的区分联合的递归类型定义。
3. 您必须为多大小写结构区分联合提供唯一的案例名称。

## <a name="using-discriminated-unions-instead-of-object-hierarchies"></a>使用可区分联合而不是对象层次结构

通常可以使用受歧视的联合作为小对象层次结构的更简单的替代方法。 例如，可以使用以下受歧视联合来代替具有圆、平方等`Shape`派生类型的基类。

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2003.fs)]

可以使用模式匹配到分支到适当的公式来计算这些数量，而不是像在面向对象的实现中使用那样计算区域或外围的虚拟方法。 在下面的示例中，使用不同的公式来计算区域，具体取决于形状。

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2004.fs)]

输出如下所示：

```console
Area of circle that has radius 15.000000: 706.858347
Area of square that has side 10.000000: 100.000000
Area of rectangle that has height 5.000000 and width 10.000000 is 50.000000
```

## <a name="using-discriminated-unions-for-tree-data-structures"></a>对树数据结构使用区分联合

可进行递归，这意味着工会本身可以包含在一个或多个案例的类型中。 递归区分结合可用于创建树结构，这些结构用于对编程语言中的表达式建模。 在以下代码中，递归区分联合用于创建二进制树数据结构。 联合由两个案例组成，`Node`即具有整数值的节点和左右子树，以及`Tip`终止树。

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2005.fs)]

在前面的代码中，`resultSumTree`具有值 10。 下图显示了 的`myTree`树结构。

![显示 MyTree 的树形结构的图表。](../media/discriminated-unions/tree-structure-mytree.png)

如果树中的节点是异构的，则区分结合可以很好地工作。 在以下代码中，类型`Expression`表示表达式的抽象语法树，该语言支持数字和变量的添加和乘法。 某些联合案例不是递归的，表示数字 （`Number`） 或变量 （`Variable`） 。 其他情况是递归的，并表示操作 （`Add`和`Multiply`），其中操作数也是表达式。 函数`Evaluate`使用匹配表达式递归处理语法树。

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2006.fs)]

执行此代码时，值`result`为 5。

## <a name="members"></a>成员

可以定义受歧视工会的成员。 下面的示例演示如何定义属性和实现接口：

```fsharp
open System

type IPrintable =
    abstract Print: unit -> unit

type Shape =
    | Circle of float
    | EquilateralTriangle of float
    | Square of float
    | Rectangle of float * float

    member this.Area =
        match this with
        | Circle r -> 2.0 * Math.PI * r
        | EquilateralTriangle s -> s * s * sqrt 3.0 / 4.0
        | Square s -> s * s
        | Rectangle(l, w) -> l * w

    interface IPrintable with
        member this.Print () =
            match this with
            | Circle r -> printfn "Circle with radius %f" r
            | EquilateralTriangle s -> printfn "Equilateral Triangle of side %f" s
            | Square s -> printfn "Square with side %f" s
            | Rectangle(l, w) -> printfn "Rectangle with length %f and width %f" l w
```

## <a name="common-attributes"></a>常见属性

以下属性常见于受歧视联合：

- `[<RequireQualifiedAccess>]`
- `[<NoEquality>]`
- `[<NoComparison>]`
- `[<Struct>]`

## <a name="see-also"></a>另请参阅

- [F# 语言参考](index.md)
