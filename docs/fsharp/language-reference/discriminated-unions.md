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
# <a name="discriminated-unions"></a><span data-ttu-id="4fb25-103">可区分联合</span><span class="sxs-lookup"><span data-stu-id="4fb25-103">Discriminated Unions</span></span>

<span data-ttu-id="4fb25-104">歧视联合为值提供支持，这些值可以是许多命名案例之一，可能每个值和类型不同。</span><span class="sxs-lookup"><span data-stu-id="4fb25-104">Discriminated unions provide support for values that can be one of a number of named cases, possibly each with different values and types.</span></span> <span data-ttu-id="4fb25-105">受歧视结合对异构数据很有用;可能有特殊情况的数据，包括有效和错误案例;因类型而异的数据;并作为小对象层次结构的替代方案。</span><span class="sxs-lookup"><span data-stu-id="4fb25-105">Discriminated unions are useful for heterogeneous data; data that can have special cases, including valid and error cases; data that varies in type from one instance to another; and as an alternative for small object hierarchies.</span></span> <span data-ttu-id="4fb25-106">此外，递归区分结合用于表示树数据结构。</span><span class="sxs-lookup"><span data-stu-id="4fb25-106">In addition, recursive discriminated unions are used to represent tree data structures.</span></span>

## <a name="syntax"></a><span data-ttu-id="4fb25-107">语法</span><span class="sxs-lookup"><span data-stu-id="4fb25-107">Syntax</span></span>

```fsharp
[ attributes ]
type [accessibility-modifier] type-name =
    | case-identifier1 [of [ fieldname1 : ] type1 [ * [ fieldname2 : ] type2 ...]
    | case-identifier2 [of [fieldname3 : ]type3 [ * [ fieldname4 : ]type4 ...]

    [ member-list ]
```

## <a name="remarks"></a><span data-ttu-id="4fb25-108">备注</span><span class="sxs-lookup"><span data-stu-id="4fb25-108">Remarks</span></span>

<span data-ttu-id="4fb25-109">歧视联合与其他语言中的联合类型类似，但存在差异。</span><span class="sxs-lookup"><span data-stu-id="4fb25-109">Discriminated unions are similar to union types in other languages, but there are differences.</span></span> <span data-ttu-id="4fb25-110">与 C++ 中的联合类型或 Visual Basic 中的变体类型一样，存储在值中的数据不是固定的;它可以是几个不同的选项之一。</span><span class="sxs-lookup"><span data-stu-id="4fb25-110">As with a union type in C++ or a variant type in Visual Basic, the data stored in the value is not fixed; it can be one of several distinct options.</span></span> <span data-ttu-id="4fb25-111">但是，与这些其他语言中的联合不同，每个可能的选项都给定一个*案例标识符*。</span><span class="sxs-lookup"><span data-stu-id="4fb25-111">Unlike unions in these other languages, however, each of the possible options is given a *case identifier*.</span></span> <span data-ttu-id="4fb25-112">案例标识符是此类型对象可能具有的各种可能类型的值的名称;值是可选的。</span><span class="sxs-lookup"><span data-stu-id="4fb25-112">The case identifiers are names for the various possible types of values that objects of this type could be; the values are optional.</span></span> <span data-ttu-id="4fb25-113">如果不存在值，则大小写等效于枚举大小写。</span><span class="sxs-lookup"><span data-stu-id="4fb25-113">If values are not present, the case is equivalent to an enumeration case.</span></span> <span data-ttu-id="4fb25-114">如果存在值，则每个值可以是指定类型的单个值，也可以是聚合相同或不同类型的多个字段的元组。</span><span class="sxs-lookup"><span data-stu-id="4fb25-114">If values are present, each value can either be a single value of a specified type, or a tuple that aggregates multiple fields of the same or different types.</span></span> <span data-ttu-id="4fb25-115">您可以为单个字段指定名称，但该名称是可选的，即使在同一情况下命名了其他字段也是如此。</span><span class="sxs-lookup"><span data-stu-id="4fb25-115">You can give an individual field a name, but the name is optional, even if other fields in the same case are named.</span></span>

<span data-ttu-id="4fb25-116">受歧视联合的可访问性`public`默认为 。</span><span class="sxs-lookup"><span data-stu-id="4fb25-116">Accessibility for discriminated unions defaults to `public`.</span></span>

<span data-ttu-id="4fb25-117">例如，请考虑以下形状类型的声明。</span><span class="sxs-lookup"><span data-stu-id="4fb25-117">For example, consider the following declaration of a Shape type.</span></span>

```fsharp
type Shape =
    | Rectangle of width : float * length : float
    | Circle of radius : float
    | Prism of width : float * float * height : float
```

<span data-ttu-id="4fb25-118">前面的代码声明一个受歧视的联合形状，它可以具有三种情况中的任何一个的值：矩形、圆体和棱镜。</span><span class="sxs-lookup"><span data-stu-id="4fb25-118">The preceding code declares a discriminated union Shape, which can have values of any of three cases: Rectangle, Circle, and Prism.</span></span> <span data-ttu-id="4fb25-119">每个案例都有一组不同的字段。</span><span class="sxs-lookup"><span data-stu-id="4fb25-119">Each case has a different set of fields.</span></span> <span data-ttu-id="4fb25-120">矩形大小写有两个命名字段，两个`float`命名字段的类型，具有名称宽度和长度。</span><span class="sxs-lookup"><span data-stu-id="4fb25-120">The Rectangle case has two named fields, both of type `float`, that have the names width and length.</span></span> <span data-ttu-id="4fb25-121">圆大小写只有一个命名字段，半径。</span><span class="sxs-lookup"><span data-stu-id="4fb25-121">The Circle case has just one named field, radius.</span></span> <span data-ttu-id="4fb25-122">棱镜大小写有三个字段，其中两个字段（宽度和高度）被命名为字段。</span><span class="sxs-lookup"><span data-stu-id="4fb25-122">The Prism case has three fields, two of which (width and height) are named fields.</span></span> <span data-ttu-id="4fb25-123">未命名的字段称为匿名字段。</span><span class="sxs-lookup"><span data-stu-id="4fb25-123">Unnamed fields are referred to as anonymous fields.</span></span>

<span data-ttu-id="4fb25-124">通过根据以下示例为命名字段和匿名字段提供值来构造对象。</span><span class="sxs-lookup"><span data-stu-id="4fb25-124">You construct objects by providing values for the named and anonymous fields according to the following examples.</span></span>

```fsharp
let rect = Rectangle(length = 1.3, width = 10.0)
let circ = Circle (1.0)
let prism = Prism(5., 2.0, height = 3.0)
```

<span data-ttu-id="4fb25-125">此代码显示，您可以在初始化中使用命名字段，也可以依赖声明中字段的顺序，并依次为每个字段提供值。</span><span class="sxs-lookup"><span data-stu-id="4fb25-125">This code shows that you can either use the named fields in the initialization, or you can rely on the ordering of the fields in the declaration and just provide the values for each field in turn.</span></span> <span data-ttu-id="4fb25-126">上一个代码`rect`中的构造函数调用使用命名字段，但构造函数调用`circ`使用排序。</span><span class="sxs-lookup"><span data-stu-id="4fb25-126">The constructor call for `rect` in the previous code uses the named fields, but the constructor call for `circ` uses the ordering.</span></span> <span data-ttu-id="4fb25-127">可以混合有序字段和命名字段，如 在 构造 中`prism`。</span><span class="sxs-lookup"><span data-stu-id="4fb25-127">You can mix the ordered fields and named fields, as in the construction of `prism`.</span></span>

<span data-ttu-id="4fb25-128">该`option`类型是 F# 核心库中的简单区分联合。</span><span class="sxs-lookup"><span data-stu-id="4fb25-128">The `option` type is a simple discriminated union in the F# core library.</span></span> <span data-ttu-id="4fb25-129">类型`option`声明如下。</span><span class="sxs-lookup"><span data-stu-id="4fb25-129">The `option` type is declared as follows.</span></span>

```fsharp
// The option type is a discriminated union.
type Option<'a> =
    | Some of 'a
    | None
```

<span data-ttu-id="4fb25-130">前面的代码指定类型`Option`是具有两个案例的受歧视联合，`Some`和`None`。</span><span class="sxs-lookup"><span data-stu-id="4fb25-130">The previous code specifies that the type `Option` is a discriminated union that has two cases, `Some` and `None`.</span></span> <span data-ttu-id="4fb25-131">案例`Some`具有一个关联值，该值由一个匿名字段组成，其类型由类型`'a`参数表示。</span><span class="sxs-lookup"><span data-stu-id="4fb25-131">The `Some` case has an associated value that consists of one anonymous field whose type is represented by the type parameter `'a`.</span></span> <span data-ttu-id="4fb25-132">案例`None`没有关联的值。</span><span class="sxs-lookup"><span data-stu-id="4fb25-132">The `None` case has no associated value.</span></span> <span data-ttu-id="4fb25-133">因此，`option`类型指定具有特定类型值或无值的泛型类型。</span><span class="sxs-lookup"><span data-stu-id="4fb25-133">Thus the `option` type specifies a generic type that either has a value of some type or no value.</span></span> <span data-ttu-id="4fb25-134">类型`Option`还有一个小写类型别名`option`，这是更常用的。</span><span class="sxs-lookup"><span data-stu-id="4fb25-134">The type `Option` also has a lowercase type alias, `option`, that is more commonly used.</span></span>

<span data-ttu-id="4fb25-135">案例标识符可用作区分联合类型的构造函数。</span><span class="sxs-lookup"><span data-stu-id="4fb25-135">The case identifiers can be used as constructors for the discriminated union type.</span></span> <span data-ttu-id="4fb25-136">例如，以下代码用于创建`option`类型的值。</span><span class="sxs-lookup"><span data-stu-id="4fb25-136">For example, the following code is used to create values of the `option` type.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2001.fs)]

<span data-ttu-id="4fb25-137">大小写标识符也用于模式匹配表达式。</span><span class="sxs-lookup"><span data-stu-id="4fb25-137">The case identifiers are also used in pattern matching expressions.</span></span> <span data-ttu-id="4fb25-138">在模式匹配表达式中，为与单个情况关联的值提供标识符。</span><span class="sxs-lookup"><span data-stu-id="4fb25-138">In a pattern matching expression, identifiers are provided for the values associated with the individual cases.</span></span> <span data-ttu-id="4fb25-139">例如，在以下代码中，`x`是给定与`Some``option`类型大小写关联的值的标识符。</span><span class="sxs-lookup"><span data-stu-id="4fb25-139">For example, in the following code, `x` is the identifier given the value that is associated with the `Some` case of the `option` type.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2002.fs)]

<span data-ttu-id="4fb25-140">在模式匹配表达式中，可以使用命名字段指定受区别的联合匹配。</span><span class="sxs-lookup"><span data-stu-id="4fb25-140">In pattern matching expressions, you can use named fields to specify discriminated union matches.</span></span> <span data-ttu-id="4fb25-141">对于以前声明的 Shape 类型，可以使用命名字段，如以下代码所示，以提取字段的值。</span><span class="sxs-lookup"><span data-stu-id="4fb25-141">For the Shape type that was declared previously, you can use the named fields as the following code shows to extract the values of the fields.</span></span>

```fsharp
let getShapeWidth shape =
    match shape with
    | Rectangle(width = w) -> w
    | Circle(radius = r) -> 2. * r
    | Prism(width = w) -> w
```

<span data-ttu-id="4fb25-142">通常，可以使用案例标识符，而无需使用联合名称对其进行限定。</span><span class="sxs-lookup"><span data-stu-id="4fb25-142">Normally, the case identifiers can be used without qualifying them with the name of the union.</span></span> <span data-ttu-id="4fb25-143">如果希望名称始终与联合的名称限定，则可以将["需要限定Access"](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.requirequalifiedaccessattribute-class-[fsharp])属性应用于联合类型定义。</span><span class="sxs-lookup"><span data-stu-id="4fb25-143">If you want the name to always be qualified with the name of the union, you can apply the [RequireQualifiedAccess](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.requirequalifiedaccessattribute-class-[fsharp]) attribute to the union type definition.</span></span>

### <a name="unwrapping-discriminated-unions"></a><span data-ttu-id="4fb25-144">未包装的受歧视联合</span><span class="sxs-lookup"><span data-stu-id="4fb25-144">Unwrapping Discriminated Unions</span></span>

<span data-ttu-id="4fb25-145">在 F# 中，区分联合通常用于域建模，用于包装单个类型。</span><span class="sxs-lookup"><span data-stu-id="4fb25-145">In F# Discriminated Unions are often used in domain-modeling for wrapping a single type.</span></span> <span data-ttu-id="4fb25-146">通过模式匹配也很容易提取基础值。</span><span class="sxs-lookup"><span data-stu-id="4fb25-146">It's easy to extract the underlying value via pattern matching as well.</span></span> <span data-ttu-id="4fb25-147">不需要对单个情况使用匹配表达式：</span><span class="sxs-lookup"><span data-stu-id="4fb25-147">You don't need to use a match expression for a single case:</span></span>

```fsharp
let ([UnionCaseIdentifier] [values]) = [UnionValue]
```

<span data-ttu-id="4fb25-148">下面的示例演示这一操作：</span><span class="sxs-lookup"><span data-stu-id="4fb25-148">The following example demonstrates this:</span></span>

```fsharp
type ShaderProgram = | ShaderProgram of id:int

let someFunctionUsingShaderProgram shaderProgram =
    let (ShaderProgram id) = shaderProgram
    // Use the unwrapped value
    ...
```

<span data-ttu-id="4fb25-149">模式匹配也直接允许在函数参数中进行，因此您可以在那里打开单个大小写：</span><span class="sxs-lookup"><span data-stu-id="4fb25-149">Pattern matching is also allowed directly in function parameters, so you can unwrap a single case there:</span></span>

```fsharp
let someFunctionUsingShaderProgram (ShaderProgram id) =
    // Use the unwrapped value
    ...
```

## <a name="struct-discriminated-unions"></a><span data-ttu-id="4fb25-150">结构歧视联盟</span><span class="sxs-lookup"><span data-stu-id="4fb25-150">Struct Discriminated Unions</span></span>

<span data-ttu-id="4fb25-151">您还可以将"受歧视联合"表示为结构。</span><span class="sxs-lookup"><span data-stu-id="4fb25-151">You can also represent Discriminated Unions as structs.</span></span>  <span data-ttu-id="4fb25-152">这使用属性`[<Struct>]`完成。</span><span class="sxs-lookup"><span data-stu-id="4fb25-152">This is done with the `[<Struct>]` attribute.</span></span>

```fsharp
[<Struct>]
type SingleCase = Case of string

[<Struct>]
type Multicase =
    | Case1 of Case1 : string
    | Case2 of Case2 : int
    | Case3 of Case3 : double
```

<span data-ttu-id="4fb25-153">由于这些值类型而不是引用类型，因此与引用区分结合相比，存在额外的注意事项：</span><span class="sxs-lookup"><span data-stu-id="4fb25-153">Because these are value types and not reference types, there are extra considerations compared with reference discriminated unions:</span></span>

1. <span data-ttu-id="4fb25-154">它们作为值类型复制，并且具有值类型语义。</span><span class="sxs-lookup"><span data-stu-id="4fb25-154">They are copied as value types and have value type semantics.</span></span>
2. <span data-ttu-id="4fb25-155">不能使用具有多大小写结构的区分联合的递归类型定义。</span><span class="sxs-lookup"><span data-stu-id="4fb25-155">You cannot use a recursive type definition with a multicase struct Discriminated Union.</span></span>
3. <span data-ttu-id="4fb25-156">您必须为多大小写结构区分联合提供唯一的案例名称。</span><span class="sxs-lookup"><span data-stu-id="4fb25-156">You must provide unique case names for a multicase struct Discriminated Union.</span></span>

## <a name="using-discriminated-unions-instead-of-object-hierarchies"></a><span data-ttu-id="4fb25-157">使用可区分联合而不是对象层次结构</span><span class="sxs-lookup"><span data-stu-id="4fb25-157">Using Discriminated Unions Instead of Object Hierarchies</span></span>

<span data-ttu-id="4fb25-158">通常可以使用受歧视的联合作为小对象层次结构的更简单的替代方法。</span><span class="sxs-lookup"><span data-stu-id="4fb25-158">You can often use a discriminated union as a simpler alternative to a small object hierarchy.</span></span> <span data-ttu-id="4fb25-159">例如，可以使用以下受歧视联合来代替具有圆、平方等`Shape`派生类型的基类。</span><span class="sxs-lookup"><span data-stu-id="4fb25-159">For example, the following discriminated union could be used instead of a `Shape` base class that has derived types for circle, square, and so on.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2003.fs)]

<span data-ttu-id="4fb25-160">可以使用模式匹配到分支到适当的公式来计算这些数量，而不是像在面向对象的实现中使用那样计算区域或外围的虚拟方法。</span><span class="sxs-lookup"><span data-stu-id="4fb25-160">Instead of a virtual method to compute an area or perimeter, as you would use in an object-oriented implementation, you can use pattern matching to branch to appropriate formulas to compute these quantities.</span></span> <span data-ttu-id="4fb25-161">在下面的示例中，使用不同的公式来计算区域，具体取决于形状。</span><span class="sxs-lookup"><span data-stu-id="4fb25-161">In the following example, different formulas are used to compute the area, depending on the shape.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2004.fs)]

<span data-ttu-id="4fb25-162">输出如下所示：</span><span class="sxs-lookup"><span data-stu-id="4fb25-162">The output is as follows:</span></span>

```console
Area of circle that has radius 15.000000: 706.858347
Area of square that has side 10.000000: 100.000000
Area of rectangle that has height 5.000000 and width 10.000000 is 50.000000
```

## <a name="using-discriminated-unions-for-tree-data-structures"></a><span data-ttu-id="4fb25-163">对树数据结构使用区分联合</span><span class="sxs-lookup"><span data-stu-id="4fb25-163">Using Discriminated Unions for Tree Data Structures</span></span>

<span data-ttu-id="4fb25-164">可进行递归，这意味着工会本身可以包含在一个或多个案例的类型中。</span><span class="sxs-lookup"><span data-stu-id="4fb25-164">Discriminated unions can be recursive, meaning that the union itself can be included in the type of one or more cases.</span></span> <span data-ttu-id="4fb25-165">递归区分结合可用于创建树结构，这些结构用于对编程语言中的表达式建模。</span><span class="sxs-lookup"><span data-stu-id="4fb25-165">Recursive discriminated unions can be used to create tree structures, which are used to model expressions in programming languages.</span></span> <span data-ttu-id="4fb25-166">在以下代码中，递归区分联合用于创建二进制树数据结构。</span><span class="sxs-lookup"><span data-stu-id="4fb25-166">In the following code, a recursive discriminated union is used to create a binary tree data structure.</span></span> <span data-ttu-id="4fb25-167">联合由两个案例组成，`Node`即具有整数值的节点和左右子树，以及`Tip`终止树。</span><span class="sxs-lookup"><span data-stu-id="4fb25-167">The union consists of two cases, `Node`, which is a node with an integer value and left and right subtrees, and `Tip`, which terminates the tree.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2005.fs)]

<span data-ttu-id="4fb25-168">在前面的代码中，`resultSumTree`具有值 10。</span><span class="sxs-lookup"><span data-stu-id="4fb25-168">In the previous code, `resultSumTree` has the value 10.</span></span> <span data-ttu-id="4fb25-169">下图显示了 的`myTree`树结构。</span><span class="sxs-lookup"><span data-stu-id="4fb25-169">The following illustration shows the tree structure for `myTree`.</span></span>

![显示 MyTree 的树形结构的图表。](../media/discriminated-unions/tree-structure-mytree.png)

<span data-ttu-id="4fb25-171">如果树中的节点是异构的，则区分结合可以很好地工作。</span><span class="sxs-lookup"><span data-stu-id="4fb25-171">Discriminated unions work well if the nodes in the tree are heterogeneous.</span></span> <span data-ttu-id="4fb25-172">在以下代码中，类型`Expression`表示表达式的抽象语法树，该语言支持数字和变量的添加和乘法。</span><span class="sxs-lookup"><span data-stu-id="4fb25-172">In the following code, the type `Expression` represents the abstract syntax tree of an expression in a simple programming language that supports addition and multiplication of numbers and variables.</span></span> <span data-ttu-id="4fb25-173">某些联合案例不是递归的，表示数字 （`Number`） 或变量 （`Variable`） 。</span><span class="sxs-lookup"><span data-stu-id="4fb25-173">Some of the union cases are not recursive and represent either numbers (`Number`) or variables (`Variable`).</span></span> <span data-ttu-id="4fb25-174">其他情况是递归的，并表示操作 （`Add`和`Multiply`），其中操作数也是表达式。</span><span class="sxs-lookup"><span data-stu-id="4fb25-174">Other cases are recursive, and represent operations (`Add` and `Multiply`), where the operands are also expressions.</span></span> <span data-ttu-id="4fb25-175">函数`Evaluate`使用匹配表达式递归处理语法树。</span><span class="sxs-lookup"><span data-stu-id="4fb25-175">The `Evaluate` function uses a match expression to recursively process the syntax tree.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2006.fs)]

<span data-ttu-id="4fb25-176">执行此代码时，值`result`为 5。</span><span class="sxs-lookup"><span data-stu-id="4fb25-176">When this code is executed, the value of `result` is 5.</span></span>

## <a name="members"></a><span data-ttu-id="4fb25-177">成员</span><span class="sxs-lookup"><span data-stu-id="4fb25-177">Members</span></span>

<span data-ttu-id="4fb25-178">可以定义受歧视工会的成员。</span><span class="sxs-lookup"><span data-stu-id="4fb25-178">It is possible to define members on discriminated unions.</span></span> <span data-ttu-id="4fb25-179">下面的示例演示如何定义属性和实现接口：</span><span class="sxs-lookup"><span data-stu-id="4fb25-179">The following example shows how to define a property and implement an interface:</span></span>

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

## <a name="common-attributes"></a><span data-ttu-id="4fb25-180">常见属性</span><span class="sxs-lookup"><span data-stu-id="4fb25-180">Common attributes</span></span>

<span data-ttu-id="4fb25-181">以下属性常见于受歧视联合：</span><span class="sxs-lookup"><span data-stu-id="4fb25-181">The following attributes are commonly seen in discriminated unions:</span></span>

- `[<RequireQualifiedAccess>]`
- `[<NoEquality>]`
- `[<NoComparison>]`
- `[<Struct>]`

## <a name="see-also"></a><span data-ttu-id="4fb25-182">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4fb25-182">See also</span></span>

- [<span data-ttu-id="4fb25-183">F# 语言参考</span><span class="sxs-lookup"><span data-stu-id="4fb25-183">F# Language Reference</span></span>](index.md)
