---
title: 可区分联合
description: 了解如何使用F#可区分联合。
ms.date: 05/16/2016
ms.openlocfilehash: 539e2843c0bbc8c5ac9c0597ffc5443f8cd127f8
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "77452638"
---
# <a name="discriminated-unions"></a><span data-ttu-id="d5362-103">可区分联合</span><span class="sxs-lookup"><span data-stu-id="d5362-103">Discriminated Unions</span></span>

<span data-ttu-id="d5362-104">可区分联合提供的值支持可以是多个命名用例中的一个，可能每个值都有不同的值和类型。</span><span class="sxs-lookup"><span data-stu-id="d5362-104">Discriminated unions provide support for values that can be one of a number of named cases, possibly each with different values and types.</span></span> <span data-ttu-id="d5362-105">可区分联合适用于异类数据;可能有特殊情况的数据，包括有效和错误事例;不同类型的数据的不同之处在于：作为小型对象层次结构的替代方法。</span><span class="sxs-lookup"><span data-stu-id="d5362-105">Discriminated unions are useful for heterogeneous data; data that can have special cases, including valid and error cases; data that varies in type from one instance to another; and as an alternative for small object hierarchies.</span></span> <span data-ttu-id="d5362-106">此外，递归的可区分联合用于表示树数据结构。</span><span class="sxs-lookup"><span data-stu-id="d5362-106">In addition, recursive discriminated unions are used to represent tree data structures.</span></span>

## <a name="syntax"></a><span data-ttu-id="d5362-107">语法</span><span class="sxs-lookup"><span data-stu-id="d5362-107">Syntax</span></span>

```fsharp
[ attributes ]
type [accessibility-modifier] type-name =
    | case-identifier1 [of [ fieldname1 : ] type1 [ * [ fieldname2 : ] type2 ...]
    | case-identifier2 [of [fieldname3 : ]type3 [ * [ fieldname4 : ]type4 ...]

    [ member-list ]
```

## <a name="remarks"></a><span data-ttu-id="d5362-108">备注</span><span class="sxs-lookup"><span data-stu-id="d5362-108">Remarks</span></span>

<span data-ttu-id="d5362-109">可区分联合类似于其他语言中的联合类型，但有一些差异。</span><span class="sxs-lookup"><span data-stu-id="d5362-109">Discriminated unions are similar to union types in other languages, but there are differences.</span></span> <span data-ttu-id="d5362-110">与 Visual Basic 中的联合类型C++或变体类型一样，值中存储的数据不是固定的;它可以是几个不同的选项之一。</span><span class="sxs-lookup"><span data-stu-id="d5362-110">As with a union type in C++ or a variant type in Visual Basic, the data stored in the value is not fixed; it can be one of several distinct options.</span></span> <span data-ttu-id="d5362-111">与其他这些语言中的联合不同，每个可能的选项都有一个*case 标识符*。</span><span class="sxs-lookup"><span data-stu-id="d5362-111">Unlike unions in these other languages, however, each of the possible options is given a *case identifier*.</span></span> <span data-ttu-id="d5362-112">Case 标识符是此类型的对象可能具有的各种类型的值的名称;值是可选的。</span><span class="sxs-lookup"><span data-stu-id="d5362-112">The case identifiers are names for the various possible types of values that objects of this type could be; the values are optional.</span></span> <span data-ttu-id="d5362-113">如果值不存在，则该事例等效于枚举用例。</span><span class="sxs-lookup"><span data-stu-id="d5362-113">If values are not present, the case is equivalent to an enumeration case.</span></span> <span data-ttu-id="d5362-114">如果存在值，则每个值可以是指定类型的单个值，也可以是聚合同一类型或不同类型的多个字段的元组。</span><span class="sxs-lookup"><span data-stu-id="d5362-114">If values are present, each value can either be a single value of a specified type, or a tuple that aggregates multiple fields of the same or different types.</span></span> <span data-ttu-id="d5362-115">您可以为单个字段指定一个名称，但该名称是可选的，即使在同一种情况下，也是如此。</span><span class="sxs-lookup"><span data-stu-id="d5362-115">You can give an individual field a name, but the name is optional, even if other fields in the same case are named.</span></span>

<span data-ttu-id="d5362-116">可区分的联合的辅助功能默认为 `public`。</span><span class="sxs-lookup"><span data-stu-id="d5362-116">Accessibility for discriminated unions defaults to `public`.</span></span>

<span data-ttu-id="d5362-117">例如，请考虑下面的形状类型声明。</span><span class="sxs-lookup"><span data-stu-id="d5362-117">For example, consider the following declaration of a Shape type.</span></span>

```fsharp
type Shape =
    | Rectangle of width : float * length : float
    | Circle of radius : float
    | Prism of width : float * float * height : float
```

<span data-ttu-id="d5362-118">前面的代码声明了一个可区分的联合形状，该形状的值可以是以下三种情况中的任何一种：矩形、圆形和 Prism。</span><span class="sxs-lookup"><span data-stu-id="d5362-118">The preceding code declares a discriminated union Shape, which can have values of any of three cases: Rectangle, Circle, and Prism.</span></span> <span data-ttu-id="d5362-119">每个事例都有一组不同的字段。</span><span class="sxs-lookup"><span data-stu-id="d5362-119">Each case has a different set of fields.</span></span> <span data-ttu-id="d5362-120">矩形用例有两个命名字段，两个均为类型 `float`，都具有名称 width 和 length。</span><span class="sxs-lookup"><span data-stu-id="d5362-120">The Rectangle case has two named fields, both of type `float`, that have the names width and length.</span></span> <span data-ttu-id="d5362-121">圆形大小写只包含一个命名字段 "半径"。</span><span class="sxs-lookup"><span data-stu-id="d5362-121">The Circle case has just one named field, radius.</span></span> <span data-ttu-id="d5362-122">Prism 用例有三个字段，其中两个字段（宽度和高度）为 "命名字段"。</span><span class="sxs-lookup"><span data-stu-id="d5362-122">The Prism case has three fields, two of which (width and height) are named fields.</span></span> <span data-ttu-id="d5362-123">未命名字段称为匿名字段。</span><span class="sxs-lookup"><span data-stu-id="d5362-123">Unnamed fields are referred to as anonymous fields.</span></span>

<span data-ttu-id="d5362-124">您可以根据以下示例，为已命名和匿名字段提供值来构造对象。</span><span class="sxs-lookup"><span data-stu-id="d5362-124">You construct objects by providing values for the named and anonymous fields according to the following examples.</span></span>

```fsharp
let rect = Rectangle(length = 1.3, width = 10.0)
let circ = Circle (1.0)
let prism = Prism(5., 2.0, height = 3.0)
```

<span data-ttu-id="d5362-125">此代码显示，您可以在初始化中使用已命名的字段，也可以依赖于声明中的字段顺序，而只是提供每个字段的值。</span><span class="sxs-lookup"><span data-stu-id="d5362-125">This code shows that you can either use the named fields in the initialization, or you can rely on the ordering of the fields in the declaration and just provide the values for each field in turn.</span></span> <span data-ttu-id="d5362-126">前面代码中 `rect` 的构造函数调用使用指定的字段，但 `circ` 的构造函数调用使用排序。</span><span class="sxs-lookup"><span data-stu-id="d5362-126">The constructor call for `rect` in the previous code uses the named fields, but the constructor call for `circ` uses the ordering.</span></span> <span data-ttu-id="d5362-127">可以混用有序字段和命名字段，就像 `prism`的构造一样。</span><span class="sxs-lookup"><span data-stu-id="d5362-127">You can mix the ordered fields and named fields, as in the construction of `prism`.</span></span>

<span data-ttu-id="d5362-128">`option` 类型是F#核心库中的一个简单的可区分联合。</span><span class="sxs-lookup"><span data-stu-id="d5362-128">The `option` type is a simple discriminated union in the F# core library.</span></span> <span data-ttu-id="d5362-129">按如下所示声明 `option` 类型。</span><span class="sxs-lookup"><span data-stu-id="d5362-129">The `option` type is declared as follows.</span></span>

```fsharp
// The option type is a discriminated union.
type Option<'a> =
    | Some of 'a
    | None
```

<span data-ttu-id="d5362-130">上面的代码指定 `Option` 类型是具有两个用例（`Some` 和 `None`）的可区分联合。</span><span class="sxs-lookup"><span data-stu-id="d5362-130">The previous code specifies that the type `Option` is a discriminated union that has two cases, `Some` and `None`.</span></span> <span data-ttu-id="d5362-131">`Some` 用例具有一个关联的值，它包含一个匿名字段，该字段的类型由类型参数 `'a`表示。</span><span class="sxs-lookup"><span data-stu-id="d5362-131">The `Some` case has an associated value that consists of one anonymous field whose type is represented by the type parameter `'a`.</span></span> <span data-ttu-id="d5362-132">`None` 用例没有关联值。</span><span class="sxs-lookup"><span data-stu-id="d5362-132">The `None` case has no associated value.</span></span> <span data-ttu-id="d5362-133">因此，`option` 类型指定泛型类型，该类型具有某种类型的值或没有值。</span><span class="sxs-lookup"><span data-stu-id="d5362-133">Thus the `option` type specifies a generic type that either has a value of some type or no value.</span></span> <span data-ttu-id="d5362-134">类型 `Option` 还具有更常用的小写类型别名 `option`。</span><span class="sxs-lookup"><span data-stu-id="d5362-134">The type `Option` also has a lowercase type alias, `option`, that is more commonly used.</span></span>

<span data-ttu-id="d5362-135">Case 标识符可用作可区分联合类型的构造函数。</span><span class="sxs-lookup"><span data-stu-id="d5362-135">The case identifiers can be used as constructors for the discriminated union type.</span></span> <span data-ttu-id="d5362-136">例如，下面的代码用于创建 `option` 类型的值。</span><span class="sxs-lookup"><span data-stu-id="d5362-136">For example, the following code is used to create values of the `option` type.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2001.fs)]

<span data-ttu-id="d5362-137">Case 标识符还用于模式匹配表达式。</span><span class="sxs-lookup"><span data-stu-id="d5362-137">The case identifiers are also used in pattern matching expressions.</span></span> <span data-ttu-id="d5362-138">在模式匹配表达式中，会为与单个用例关联的值提供标识符。</span><span class="sxs-lookup"><span data-stu-id="d5362-138">In a pattern matching expression, identifiers are provided for the values associated with the individual cases.</span></span> <span data-ttu-id="d5362-139">例如，在下面的代码中，`x` 是给定与 `option` 类型的 `Some` 大小写关联的值的标识符。</span><span class="sxs-lookup"><span data-stu-id="d5362-139">For example, in the following code, `x` is the identifier given the value that is associated with the `Some` case of the `option` type.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2002.fs)]

<span data-ttu-id="d5362-140">在模式匹配表达式中，可以使用命名字段来指定可区分的联合匹配。</span><span class="sxs-lookup"><span data-stu-id="d5362-140">In pattern matching expressions, you can use named fields to specify discriminated union matches.</span></span> <span data-ttu-id="d5362-141">对于之前声明的形状类型，可以使用命名字段，如以下代码所示，以便提取字段的值。</span><span class="sxs-lookup"><span data-stu-id="d5362-141">For the Shape type that was declared previously, you can use the named fields as the following code shows to extract the values of the fields.</span></span>

```fsharp
let getShapeWidth shape =
    match shape with
    | Rectangle(width = w) -> w
    | Circle(radius = r) -> 2. * r
    | Prism(width = w) -> w
```

<span data-ttu-id="d5362-142">通常情况下，可以使用 case 标识符，无需使用联合名称来限定它们。</span><span class="sxs-lookup"><span data-stu-id="d5362-142">Normally, the case identifiers can be used without qualifying them with the name of the union.</span></span> <span data-ttu-id="d5362-143">如果希望名称始终使用联合的名称进行限定，则可将[RequireQualifiedAccess](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.requirequalifiedaccessattribute-class-[fsharp])特性应用于联合类型定义。</span><span class="sxs-lookup"><span data-stu-id="d5362-143">If you want the name to always be qualified with the name of the union, you can apply the [RequireQualifiedAccess](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.requirequalifiedaccessattribute-class-[fsharp]) attribute to the union type definition.</span></span>

### <a name="unwrapping-discriminated-unions"></a><span data-ttu-id="d5362-144">解包可区分联合</span><span class="sxs-lookup"><span data-stu-id="d5362-144">Unwrapping Discriminated Unions</span></span>

<span data-ttu-id="d5362-145">在F#可区分联合中，通常用于包装单个类型的域建模。</span><span class="sxs-lookup"><span data-stu-id="d5362-145">In F# Discriminated Unions are often used in domain-modeling for wrapping a single type.</span></span> <span data-ttu-id="d5362-146">也可以通过模式匹配轻松提取基础值。</span><span class="sxs-lookup"><span data-stu-id="d5362-146">It's easy to extract the underlying value via pattern matching as well.</span></span> <span data-ttu-id="d5362-147">对于一个事例，无需使用 match 表达式：</span><span class="sxs-lookup"><span data-stu-id="d5362-147">You don't need to use a match expression for a single case:</span></span>

```fsharp
let ([UnionCaseIdentifier] [values]) = [UnionValue]
```

<span data-ttu-id="d5362-148">下面的示例演示这一操作：</span><span class="sxs-lookup"><span data-stu-id="d5362-148">The following example demonstrates this:</span></span>

```fsharp
type ShaderProgram = | ShaderProgram of id:int

let someFunctionUsingShaderProgram shaderProgram =
    let (ShaderProgram id) = shaderProgram
    // Use the unwrapped value
    ...
```

<span data-ttu-id="d5362-149">函数参数中也可以直接使用模式匹配，因此，可以将一个事例解包到其中：</span><span class="sxs-lookup"><span data-stu-id="d5362-149">Pattern matching is also allowed directly in function parameters, so you can unwrap a single case there:</span></span>

```fsharp
let someFunctionUsingShaderProgram (ShaderProgram id) =
    // Use the unwrapped value
    ...
```

## <a name="struct-discriminated-unions"></a><span data-ttu-id="d5362-150">结构可区分联合</span><span class="sxs-lookup"><span data-stu-id="d5362-150">Struct Discriminated Unions</span></span>

<span data-ttu-id="d5362-151">您还可以将可区分联合表示为结构。</span><span class="sxs-lookup"><span data-stu-id="d5362-151">You can also represent Discriminated Unions as structs.</span></span>  <span data-ttu-id="d5362-152">此操作通过 `[<Struct>]` 属性完成。</span><span class="sxs-lookup"><span data-stu-id="d5362-152">This is done with the `[<Struct>]` attribute.</span></span>

```fsharp
[<Struct>]
type SingleCase = Case of string

[<Struct>]
type Multicase =
    | Case1 of Case1 : string
    | Case2 of Case2 : int
    | Case3 of Case3 : double
```

<span data-ttu-id="d5362-153">由于这些是值类型而不是引用类型，因此与引用可区分联合相比，有一些额外的注意事项：</span><span class="sxs-lookup"><span data-stu-id="d5362-153">Because these are value types and not reference types, there are extra considerations compared with reference discriminated unions:</span></span>

1. <span data-ttu-id="d5362-154">它们被复制为值类型并具有值类型语义。</span><span class="sxs-lookup"><span data-stu-id="d5362-154">They are copied as value types and have value type semantics.</span></span>
2. <span data-ttu-id="d5362-155">不能将递归类型定义用于 multicase 结构可区分联合。</span><span class="sxs-lookup"><span data-stu-id="d5362-155">You cannot use a recursive type definition with a multicase struct Discriminated Union.</span></span>
3. <span data-ttu-id="d5362-156">必须为 multicase 结构可区分联合提供唯一的事例名称。</span><span class="sxs-lookup"><span data-stu-id="d5362-156">You must provide unique case names for a multicase struct Discriminated Union.</span></span>

## <a name="using-discriminated-unions-instead-of-object-hierarchies"></a><span data-ttu-id="d5362-157">使用可区分联合而不是对象层次结构</span><span class="sxs-lookup"><span data-stu-id="d5362-157">Using Discriminated Unions Instead of Object Hierarchies</span></span>

<span data-ttu-id="d5362-158">通常，可以将可区分联合用作小型对象层次结构的更简单的替代方法。</span><span class="sxs-lookup"><span data-stu-id="d5362-158">You can often use a discriminated union as a simpler alternative to a small object hierarchy.</span></span> <span data-ttu-id="d5362-159">例如，可以使用以下可区分联合，而不是具有圆、正方形等派生类型的 `Shape` 基类。</span><span class="sxs-lookup"><span data-stu-id="d5362-159">For example, the following discriminated union could be used instead of a `Shape` base class that has derived types for circle, square, and so on.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2003.fs)]

<span data-ttu-id="d5362-160">与在面向对象的实现中使用的一样，可以使用模式匹配分支到适当的公式来计算这些数量，而不是使用虚方法来计算区域或外围网络。</span><span class="sxs-lookup"><span data-stu-id="d5362-160">Instead of a virtual method to compute an area or perimeter, as you would use in an object-oriented implementation, you can use pattern matching to branch to appropriate formulas to compute these quantities.</span></span> <span data-ttu-id="d5362-161">在下面的示例中，使用不同的公式来计算区域，具体取决于形状。</span><span class="sxs-lookup"><span data-stu-id="d5362-161">In the following example, different formulas are used to compute the area, depending on the shape.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2004.fs)]

<span data-ttu-id="d5362-162">输出如下所示：</span><span class="sxs-lookup"><span data-stu-id="d5362-162">The output is as follows:</span></span>

```console
Area of circle that has radius 15.000000: 706.858347
Area of square that has side 10.000000: 100.000000
Area of rectangle that has height 5.000000 and width 10.000000 is 50.000000
```

## <a name="using-discriminated-unions-for-tree-data-structures"></a><span data-ttu-id="d5362-163">对树形数据结构使用可区分联合</span><span class="sxs-lookup"><span data-stu-id="d5362-163">Using Discriminated Unions for Tree Data Structures</span></span>

<span data-ttu-id="d5362-164">可区分联合可以是递归的，这意味着可将联合本身包含在一个或多个事例的类型中。</span><span class="sxs-lookup"><span data-stu-id="d5362-164">Discriminated unions can be recursive, meaning that the union itself can be included in the type of one or more cases.</span></span> <span data-ttu-id="d5362-165">递归的可区分联合可用于创建树结构，用于在编程语言中为表达式建模。</span><span class="sxs-lookup"><span data-stu-id="d5362-165">Recursive discriminated unions can be used to create tree structures, which are used to model expressions in programming languages.</span></span> <span data-ttu-id="d5362-166">在下面的代码中，递归的可区分联合用于创建二进制树数据结构。</span><span class="sxs-lookup"><span data-stu-id="d5362-166">In the following code, a recursive discriminated union is used to create a binary tree data structure.</span></span> <span data-ttu-id="d5362-167">联合包括两个事例，`Node`，这是一个具有整数值、左右子树的节点和 `Tip`（用于终止树）。</span><span class="sxs-lookup"><span data-stu-id="d5362-167">The union consists of two cases, `Node`, which is a node with an integer value and left and right subtrees, and `Tip`, which terminates the tree.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2005.fs)]

<span data-ttu-id="d5362-168">在前面的代码中，`resultSumTree` 的值为10。</span><span class="sxs-lookup"><span data-stu-id="d5362-168">In the previous code, `resultSumTree` has the value 10.</span></span> <span data-ttu-id="d5362-169">下图显示了 `myTree`的树结构。</span><span class="sxs-lookup"><span data-stu-id="d5362-169">The following illustration shows the tree structure for `myTree`.</span></span>

![显示 myTree 的树结构的关系图。](../media/discriminated-unions/tree-structure-mytree.png)

<span data-ttu-id="d5362-171">如果树中的节点是异类的，则可区分的联合工作良好。</span><span class="sxs-lookup"><span data-stu-id="d5362-171">Discriminated unions work well if the nodes in the tree are heterogeneous.</span></span> <span data-ttu-id="d5362-172">在下面的代码中，类型 `Expression` 表示简单编程语言中表达式的抽象语法树，它支持数字和变量的加法和乘法。</span><span class="sxs-lookup"><span data-stu-id="d5362-172">In the following code, the type `Expression` represents the abstract syntax tree of an expression in a simple programming language that supports addition and multiplication of numbers and variables.</span></span> <span data-ttu-id="d5362-173">某些联合用例不是递归的，表示数字（`Number`）或变量（`Variable`）。</span><span class="sxs-lookup"><span data-stu-id="d5362-173">Some of the union cases are not recursive and represent either numbers (`Number`) or variables (`Variable`).</span></span> <span data-ttu-id="d5362-174">其他情况是递归的，表示运算（`Add` 和 `Multiply`），其中操作数也是表达式。</span><span class="sxs-lookup"><span data-stu-id="d5362-174">Other cases are recursive, and represent operations (`Add` and `Multiply`), where the operands are also expressions.</span></span> <span data-ttu-id="d5362-175">`Evaluate` 函数使用 match 表达式以递归方式处理语法树。</span><span class="sxs-lookup"><span data-stu-id="d5362-175">The `Evaluate` function uses a match expression to recursively process the syntax tree.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2006.fs)]

<span data-ttu-id="d5362-176">执行此代码时，`result` 的值为5。</span><span class="sxs-lookup"><span data-stu-id="d5362-176">When this code is executed, the value of `result` is 5.</span></span>

## <a name="members"></a><span data-ttu-id="d5362-177">Members</span><span class="sxs-lookup"><span data-stu-id="d5362-177">Members</span></span>

<span data-ttu-id="d5362-178">可以在可区分的联合上定义成员。</span><span class="sxs-lookup"><span data-stu-id="d5362-178">It is possible to define members on discriminated unions.</span></span> <span data-ttu-id="d5362-179">下面的示例演示如何定义属性和实现接口：</span><span class="sxs-lookup"><span data-stu-id="d5362-179">The following example shows how to define a property and implement an interface:</span></span>

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

## <a name="common-attributes"></a><span data-ttu-id="d5362-180">常见属性</span><span class="sxs-lookup"><span data-stu-id="d5362-180">Common attributes</span></span>

<span data-ttu-id="d5362-181">以下属性通常出现在可区分联合中：</span><span class="sxs-lookup"><span data-stu-id="d5362-181">The following attributes are commonly seen in discriminated unions:</span></span>

- `[<RequireQualifiedAccess>]`
- `[<NoEquality>]`
- `[<NoComparison>]`
- `[<Struct>]`

## <a name="see-also"></a><span data-ttu-id="d5362-182">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d5362-182">See also</span></span>

- [<span data-ttu-id="d5362-183">F# 语言参考</span><span class="sxs-lookup"><span data-stu-id="d5362-183">F# Language Reference</span></span>](index.md)
