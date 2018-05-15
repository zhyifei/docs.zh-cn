---
title: 可区分联合 (F#)
description: '了解如何使用 F # 可区分联合。'
ms.date: 05/16/2016
ms.openlocfilehash: 617c659e26df52819a98294bcbfa081ab82fed03
ms.sourcegitcommit: e5bb395ec86f536e114314184288f40a8c745e2e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/12/2018
---
# <a name="discriminated-unions"></a><span data-ttu-id="53410-103">可区分联合</span><span class="sxs-lookup"><span data-stu-id="53410-103">Discriminated Unions</span></span>

<span data-ttu-id="53410-104">可区分的联合可以是数量的已命名的情况下，可能是每个具有不同值和类型之一的值为提供支持。</span><span class="sxs-lookup"><span data-stu-id="53410-104">Discriminated unions provide support for values that can be one of a number of named cases, possibly each with different values and types.</span></span> <span data-ttu-id="53410-105">可区分的联合可用于异类数据;可以包括有效的特殊情况和错误情况; 的数据在从一个实例的类型到另一个; 中各不相同数据和为小对象层次结构的替代方法。</span><span class="sxs-lookup"><span data-stu-id="53410-105">Discriminated unions are useful for heterogeneous data; data that can have special cases, including valid and error cases; data that varies in type from one instance to another; and as an alternative for small object hierarchies.</span></span> <span data-ttu-id="53410-106">此外，递归可区分联合用于表示树数据结构。</span><span class="sxs-lookup"><span data-stu-id="53410-106">In addition, recursive discriminated unions are used to represent tree data structures.</span></span>

## <a name="syntax"></a><span data-ttu-id="53410-107">语法</span><span class="sxs-lookup"><span data-stu-id="53410-107">Syntax</span></span>

```fsharp
[ attributes ]
type [accessibility-modifier] type-name =
    | case-identifier1 [of [ fieldname1 : ] type1 [ * [ fieldname2 : ] type2 ...]
    | case-identifier2 [of [fieldname3 : ]type3 [ * [ fieldname4 : ]type4 ...]
...
```

## <a name="remarks"></a><span data-ttu-id="53410-108">备注</span><span class="sxs-lookup"><span data-stu-id="53410-108">Remarks</span></span>
<span data-ttu-id="53410-109">可区分的联合类似于其他语言版本，联合类型，但有差异。</span><span class="sxs-lookup"><span data-stu-id="53410-109">Discriminated unions are similar to union types in other languages, but there are differences.</span></span> <span data-ttu-id="53410-110">作为使用 c + + 中的联合类型或在 Visual Basic 中的变量类型的值中存储的数据不被固定;它可以是几个不同的选项之一。</span><span class="sxs-lookup"><span data-stu-id="53410-110">As with a union type in C++ or a variant type in Visual Basic, the data stored in the value is not fixed; it can be one of several distinct options.</span></span> <span data-ttu-id="53410-111">与联合不同这些其他语言中，但是，每个可能的选项提供*用例标识符*。</span><span class="sxs-lookup"><span data-stu-id="53410-111">Unlike unions in these other languages, however, each of the possible options is given a *case identifier*.</span></span> <span data-ttu-id="53410-112">用例标识符是各种可能的值可能是此类型的对象; 类型的名称值是可选的。</span><span class="sxs-lookup"><span data-stu-id="53410-112">The case identifiers are names for the various possible types of values that objects of this type could be; the values are optional.</span></span> <span data-ttu-id="53410-113">如果值不存在，这种情况相当于枚举用例。</span><span class="sxs-lookup"><span data-stu-id="53410-113">If values are not present, the case is equivalent to an enumeration case.</span></span> <span data-ttu-id="53410-114">如果值存在，则每个值可以是单个值的指定的类型或聚合的相同或不同类型的多个字段的元组。</span><span class="sxs-lookup"><span data-stu-id="53410-114">If values are present, each value can either be a single value of a specified type, or a tuple that aggregates multiple fields of the same or different types.</span></span> <span data-ttu-id="53410-115">可以为单个字段提供一个名称，但名称是可选的即使在相同情况下的其他字段的名称。</span><span class="sxs-lookup"><span data-stu-id="53410-115">You can give an individual field a name, but the name is optional, even if other fields in the same case are named.</span></span>

<span data-ttu-id="53410-116">可区分联合的辅助功能默认为`public`。</span><span class="sxs-lookup"><span data-stu-id="53410-116">Accessibility for discriminated unions defaults to `public`.</span></span>

<span data-ttu-id="53410-117">例如，考虑形状类型的以下声明。</span><span class="sxs-lookup"><span data-stu-id="53410-117">For example, consider the following declaration of a Shape type.</span></span>

```fsharp
type Shape =
    | Rectangle of width : float * length : float
    | Circle of radius : float
    | Prism of width : float * float * height : float
```

<span data-ttu-id="53410-118">上面的代码声明可区分的联合形状，可以具有的任何三个用例的值： 矩形、 圆形和 Prism。</span><span class="sxs-lookup"><span data-stu-id="53410-118">The preceding code declares a discriminated union Shape, which can have values of any of three cases: Rectangle, Circle, and Prism.</span></span> <span data-ttu-id="53410-119">每种情况下具有一组不同的字段。</span><span class="sxs-lookup"><span data-stu-id="53410-119">Each case has a different set of fields.</span></span> <span data-ttu-id="53410-120">用例有两个名为的矩形字段，这两个类型`float`，具有名称宽度和长度。</span><span class="sxs-lookup"><span data-stu-id="53410-120">The Rectangle case has two named fields, both of type `float`, that have the names width and length.</span></span> <span data-ttu-id="53410-121">圆用例都只是一个命名的字段，radius。</span><span class="sxs-lookup"><span data-stu-id="53410-121">The Circle case has just one named field, radius.</span></span> <span data-ttu-id="53410-122">Prism 用例具有三个字段，哪些 （宽度和高度） 的两个命名的字段。</span><span class="sxs-lookup"><span data-stu-id="53410-122">The Prism case has three fields, two of which (width and height) are named fields.</span></span> <span data-ttu-id="53410-123">未命名的字段称为匿名字段。</span><span class="sxs-lookup"><span data-stu-id="53410-123">Unnamed fields are referred to as anonymous fields.</span></span>

<span data-ttu-id="53410-124">通过提供根据下面的示例的匿名和命名的字段值构造对象。</span><span class="sxs-lookup"><span data-stu-id="53410-124">You construct objects by providing values for the named and anonymous fields according to the following examples.</span></span>

```fsharp
let rect = Rectangle(length = 1.3, width = 10.0)
let circ = Circle (1.0)
let prism = Prism(5., 2.0, height = 3.0)
```

<span data-ttu-id="53410-125">此代码演示你可以使用初始化中的命名的字段，也可以依赖于在声明中的字段的顺序，并只需提供值对于每个字段反过来。</span><span class="sxs-lookup"><span data-stu-id="53410-125">This code shows that you can either use the named fields in the initialization, or you can rely on the ordering of the fields in the declaration and just provide the values for each field in turn.</span></span> <span data-ttu-id="53410-126">对的构造函数调用`rect`在前面的代码使用命名的字段中，但对的构造函数调用`circ`使用的顺序。</span><span class="sxs-lookup"><span data-stu-id="53410-126">The constructor call for `rect` in the previous code uses the named fields, but the constructor call for `circ` uses the ordering.</span></span> <span data-ttu-id="53410-127">您可以混用的已排序的字段和命名的字段，如下所示的构造`prism`。</span><span class="sxs-lookup"><span data-stu-id="53410-127">You can mix the ordered fields and named fields, as in the construction of `prism`.</span></span>

<span data-ttu-id="53410-128">`option`类型是简单的可区分的联合中的 F # 核心库。</span><span class="sxs-lookup"><span data-stu-id="53410-128">The `option` type is a simple discriminated union in the F# core library.</span></span> <span data-ttu-id="53410-129">`option`类型声明，如下所示。</span><span class="sxs-lookup"><span data-stu-id="53410-129">The `option` type is declared as follows.</span></span>

```fsharp
// The option type is a discriminated union.
type Option<'a> =
    | Some of 'a
    | None
```

<span data-ttu-id="53410-130">前面的代码中指定类型`Option`是具有两种情况下，可区分的联合`Some`和`None`。</span><span class="sxs-lookup"><span data-stu-id="53410-130">The previous code specifies that the type `Option` is a discriminated union that has two cases, `Some` and `None`.</span></span> <span data-ttu-id="53410-131">`Some`用例都由其类型由类型参数的一个匿名字段组成的关联的值`'a`。</span><span class="sxs-lookup"><span data-stu-id="53410-131">The `Some` case has an associated value that consists of one anonymous field whose type is represented by the type parameter `'a`.</span></span> <span data-ttu-id="53410-132">`None`用例都没有关联的值。</span><span class="sxs-lookup"><span data-stu-id="53410-132">The `None` case has no associated value.</span></span> <span data-ttu-id="53410-133">因此`option`类型指定既可以具有某些类型或空值的值的泛型类型。</span><span class="sxs-lookup"><span data-stu-id="53410-133">Thus the `option` type specifies a generic type that either has a value of some type or no value.</span></span> <span data-ttu-id="53410-134">类型`Option`还有小写的类型别名`option`，即更常用。</span><span class="sxs-lookup"><span data-stu-id="53410-134">The type `Option` also has a lowercase type alias, `option`, that is more commonly used.</span></span>

<span data-ttu-id="53410-135">用例标识符可以用作可区分联合类型的构造函数。</span><span class="sxs-lookup"><span data-stu-id="53410-135">The case identifiers can be used as constructors for the discriminated union type.</span></span> <span data-ttu-id="53410-136">例如，下面的代码用于创建值`option`类型。</span><span class="sxs-lookup"><span data-stu-id="53410-136">For example, the following code is used to create values of the `option` type.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2001.fs)]

<span data-ttu-id="53410-137">用例标识符也用在匹配表达式的模式。</span><span class="sxs-lookup"><span data-stu-id="53410-137">The case identifiers are also used in pattern matching expressions.</span></span> <span data-ttu-id="53410-138">在模式匹配的表达式中，标识符提供了与各个事例关联的值。</span><span class="sxs-lookup"><span data-stu-id="53410-138">In a pattern matching expression, identifiers are provided for the values associated with the individual cases.</span></span> <span data-ttu-id="53410-139">例如，在下面的代码中，`x`标识符提供了与关联的值`Some`用例`option`类型。</span><span class="sxs-lookup"><span data-stu-id="53410-139">For example, in the following code, `x` is the identifier given the value that is associated with the `Some` case of the `option` type.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2002.fs)]

<span data-ttu-id="53410-140">在匹配表达式的模式中，你可以使用命名的字段指定可区分联合的匹配项。</span><span class="sxs-lookup"><span data-stu-id="53410-140">In pattern matching expressions, you can use named fields to specify discriminated union matches.</span></span> <span data-ttu-id="53410-141">对于以前已声明的形状类型，可以使用命名的字段，如下面的代码演示要提取的字段的值。</span><span class="sxs-lookup"><span data-stu-id="53410-141">For the Shape type that was declared previously, you can use the named fields as the following code shows to extract the values of the fields.</span></span>

```fsharp
let getShapeHeight shape =
    match shape with
    | Rectangle(height = h) -> h
    | Circle(radius = r) -> 2. * r
    | Prism(height = h) -> h
```

<span data-ttu-id="53410-142">通常情况下，用例标识符可以使用而不必限定它们具有联合的名称。</span><span class="sxs-lookup"><span data-stu-id="53410-142">Normally, the case identifiers can be used without qualifying them with the name of the union.</span></span> <span data-ttu-id="53410-143">如果你想要始终用联合的名称进行限定的名称，则可以应用[RequireQualifiedAccess](https://msdn.microsoft.com/library/8b9b6ade-0471-4413-ac5d-638cd0de5f15)属性设为的联合类型定义。</span><span class="sxs-lookup"><span data-stu-id="53410-143">If you want the name to always be qualified with the name of the union, you can apply the [RequireQualifiedAccess](https://msdn.microsoft.com/library/8b9b6ade-0471-4413-ac5d-638cd0de5f15) attribute to the union type definition.</span></span>

### <a name="unwrapping-discriminated-unions"></a><span data-ttu-id="53410-144">解包可区分的联合</span><span class="sxs-lookup"><span data-stu-id="53410-144">Unwrapping Discriminated Unions</span></span>

<span data-ttu-id="53410-145">在 F # 可区分联合通常用于在域建模包装单一类型。</span><span class="sxs-lookup"><span data-stu-id="53410-145">In F# Discriminated Unions are often used in domain-modeling for wrapping a single type.</span></span> <span data-ttu-id="53410-146">很容易通过模式以及匹配的基础价值。</span><span class="sxs-lookup"><span data-stu-id="53410-146">It's easy to extract the underlying value via pattern matching as well.</span></span> <span data-ttu-id="53410-147">你不需要要匹配表达式用于将单个用例：</span><span class="sxs-lookup"><span data-stu-id="53410-147">You don't need to use a match expression for a single case:</span></span>
```fsharp
let ([UnionCaseName] [values]) = [UnionValue]
```

<span data-ttu-id="53410-148">下面的示例演示这一操作：</span><span class="sxs-lookup"><span data-stu-id="53410-148">The following example demonstrates this:</span></span>

```fsharp
type ShaderProgram = | ShaderProgram of id:int

let someMethodUsingShaderProgram shaderProgram =
    let (ShaderProgram id) = shaderProgram
    // Use the unwrapped value
    ..
```

## <a name="struct-discriminated-unions"></a><span data-ttu-id="53410-149">结构可区分联合</span><span class="sxs-lookup"><span data-stu-id="53410-149">Struct Discriminated Unions</span></span>

<span data-ttu-id="53410-150">F # 4.1 开始，你还可以表示可区分联合为结构。</span><span class="sxs-lookup"><span data-stu-id="53410-150">Starting with F# 4.1, you can also represent Discriminated Unions as structs.</span></span>  <span data-ttu-id="53410-151">这通过完成`[<Struct>]`属性。</span><span class="sxs-lookup"><span data-stu-id="53410-151">This is done with the `[<Struct>]` attribute.</span></span>

```fsharp
[<Struct>]
type SingleCase = Case of string

[<Struct>]
type Multicase =
    | Case1 of Case1 : string
    | Case2 of Case2 : int
    | Case3 of Case3 : double
```

<span data-ttu-id="53410-152">因为这些是值类型和引用类型，所以一些额外注意事项与引用比较可区分联合：</span><span class="sxs-lookup"><span data-stu-id="53410-152">Because these are value types and not reference types, there are extra considerations compared with reference discriminated unions:</span></span>

1. <span data-ttu-id="53410-153">它们值类型作为复制，并且具有值类型语义。</span><span class="sxs-lookup"><span data-stu-id="53410-153">They are copied as value types and have value type semantics.</span></span>
2. <span data-ttu-id="53410-154">不能具有 multicase 的结构可区分联合使用递归类型定义。</span><span class="sxs-lookup"><span data-stu-id="53410-154">You cannot use a recursive type definition with a multicase struct Discriminated Union.</span></span>
3. <span data-ttu-id="53410-155">必须提供 multicase 结构可区分联合的唯一大小写的名称。</span><span class="sxs-lookup"><span data-stu-id="53410-155">You must provide unique case names for a multicase struct Discriminated Union.</span></span>

## <a name="using-discriminated-unions-instead-of-object-hierarchies"></a><span data-ttu-id="53410-156">而不对象层次结构中使用可区分的联合</span><span class="sxs-lookup"><span data-stu-id="53410-156">Using Discriminated Unions Instead of Object Hierarchies</span></span>
<span data-ttu-id="53410-157">通常，还可以使用可区分的联合作为小对象层次结构一个更简单的替代方法。</span><span class="sxs-lookup"><span data-stu-id="53410-157">You can often use a discriminated union as a simpler alternative to a small object hierarchy.</span></span> <span data-ttu-id="53410-158">例如，下面的可区分的联合无法使用而不是`Shape`基类包含派生类型圆形、 平方形，依次类推。</span><span class="sxs-lookup"><span data-stu-id="53410-158">For example, the following discriminated union could be used instead of a `Shape` base class that has derived types for circle, square, and so on.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2003.fs)]

<span data-ttu-id="53410-159">改为要计算的区域或外围虚拟方法，你将使用在面向对象的实现，你可以使用模式匹配分支到合适的公式来计算这些数量。</span><span class="sxs-lookup"><span data-stu-id="53410-159">Instead of a virtual method to compute an area or perimeter, as you would use in an object-oriented implementation, you can use pattern matching to branch to appropriate formulas to compute these quantities.</span></span> <span data-ttu-id="53410-160">在下面的示例中，不同的公式用于计算区域，具体取决于形状。</span><span class="sxs-lookup"><span data-stu-id="53410-160">In the following example, different formulas are used to compute the area, depending on the shape.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2004.fs)]

<span data-ttu-id="53410-161">输出如下所示：</span><span class="sxs-lookup"><span data-stu-id="53410-161">The output is as follows:</span></span>

```
Area of circle that has radius 15.000000: 706.858347
Area of square that has side 10.000000: 100.000000
Area of rectangle that has height 5.000000 and width 10.000000 is 50.000000
```

## <a name="using-discriminated-unions-for-tree-data-structures"></a><span data-ttu-id="53410-162">可区分的联合用于树数据结构</span><span class="sxs-lookup"><span data-stu-id="53410-162">Using Discriminated Unions for Tree Data Structures</span></span>
<span data-ttu-id="53410-163">可区分的联合可以是递归的这意味着，可以在类型的一个或多个用例中包含联合本身。</span><span class="sxs-lookup"><span data-stu-id="53410-163">Discriminated unions can be recursive, meaning that the union itself can be included in the type of one or more cases.</span></span> <span data-ttu-id="53410-164">递归可区分的联合可以用于创建树状结构，习惯于编程语言中的模型表达式。</span><span class="sxs-lookup"><span data-stu-id="53410-164">Recursive discriminated unions can be used to create tree structures, which are used to model expressions in programming languages.</span></span> <span data-ttu-id="53410-165">在下面的代码中，递归可区分联合用于创建二元树数据结构。</span><span class="sxs-lookup"><span data-stu-id="53410-165">In the following code, a recursive discriminated union is used to create a binary tree data structure.</span></span> <span data-ttu-id="53410-166">该联合的两种情况，包括`Node`，这是一个包含一个整数值和左侧和右侧子树节点和`Tip`，后者用于终结树。</span><span class="sxs-lookup"><span data-stu-id="53410-166">The union consists of two cases, `Node`, which is a node with an integer value and left and right subtrees, and `Tip`, which terminates the tree.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2005.fs)]

<span data-ttu-id="53410-167">在前面的代码中，`resultSumTree`具有值 10。</span><span class="sxs-lookup"><span data-stu-id="53410-167">In the previous code, `resultSumTree` has the value 10.</span></span> <span data-ttu-id="53410-168">下图显示树状结构`myTree`。</span><span class="sxs-lookup"><span data-stu-id="53410-168">The following illustration shows the tree structure for `myTree`.</span></span>

![MyTree 的树结构](../media/TreeStructureDiagram.png)

<span data-ttu-id="53410-170">如果在树中的节点是异类是可行的可区分的联合。</span><span class="sxs-lookup"><span data-stu-id="53410-170">Discriminated unions work well if the nodes in the tree are heterogeneous.</span></span> <span data-ttu-id="53410-171">在下面的代码中，类型`Expression`表示一种简单的编程语言支持添加中的表达式的抽象语法树和乘法的数字和变量。</span><span class="sxs-lookup"><span data-stu-id="53410-171">In the following code, the type `Expression` represents the abstract syntax tree of an expression in a simple programming language that supports addition and multiplication of numbers and variables.</span></span> <span data-ttu-id="53410-172">某些联合用例都不是递归的表示数字 (`Number`) 或变量 (`Variable`)。</span><span class="sxs-lookup"><span data-stu-id="53410-172">Some of the union cases are not recursive and represent either numbers (`Number`) or variables (`Variable`).</span></span> <span data-ttu-id="53410-173">其他情况下是递归的并且表示操作 (`Add`和`Multiply`)，其中操作数也是表达式。</span><span class="sxs-lookup"><span data-stu-id="53410-173">Other cases are recursive, and represent operations (`Add` and `Multiply`), where the operands are also expressions.</span></span> <span data-ttu-id="53410-174">`Evaluate`函数使用匹配到以递归方式进程语法树表达式。</span><span class="sxs-lookup"><span data-stu-id="53410-174">The `Evaluate` function uses a match expression to recursively process the syntax tree.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2006.fs)]

<span data-ttu-id="53410-175">执行此代码时，值`result`为 5。</span><span class="sxs-lookup"><span data-stu-id="53410-175">When this code is executed, the value of `result` is 5.</span></span>

## <a name="common-attributes"></a><span data-ttu-id="53410-176">通用属性</span><span class="sxs-lookup"><span data-stu-id="53410-176">Common Attributes</span></span>

<span data-ttu-id="53410-177">以下属性常见可区分联合中：</span><span class="sxs-lookup"><span data-stu-id="53410-177">The following attributes are commonly seen in discriminated unions:</span></span>

* `[RequireQualifiedAccess]`
* `[NoEquality]`
* `[NoComparison]`
* <span data-ttu-id="53410-178">`[Struct]` （F # 4.1 和更高版本）</span><span class="sxs-lookup"><span data-stu-id="53410-178">`[Struct]` (F# 4.1 and higher)</span></span>

## <a name="see-also"></a><span data-ttu-id="53410-179">请参阅</span><span class="sxs-lookup"><span data-stu-id="53410-179">See Also</span></span>
[<span data-ttu-id="53410-180">F# 语言参考</span><span class="sxs-lookup"><span data-stu-id="53410-180">F# Language Reference</span></span>](index.md)
