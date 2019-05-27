---
title: C# 8.0 中的新增功能 - C# 指南
description: 简要介绍 C# 8.0 中提供的新功能。 本文使用最新的预览版 5。
ms.date: 02/12/2019
ms.openlocfilehash: dd4aca99a19134ed3ffff859c9c9554d4d480816
ms.sourcegitcommit: 682c64df0322c7bda016f8bfea8954e9b31f1990
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/13/2019
ms.locfileid: "65557152"
---
# <a name="whats-new-in-c-80"></a><span data-ttu-id="e0ed1-104">C# 8.0 中的新增功能</span><span class="sxs-lookup"><span data-stu-id="e0ed1-104">What's new in C# 8.0</span></span>

<span data-ttu-id="e0ed1-105">C# 语言有许多增强功能，可以进行试用。</span><span class="sxs-lookup"><span data-stu-id="e0ed1-105">There are many enhancements to the C# language that you can try out already.</span></span> 

- [<span data-ttu-id="e0ed1-106">Readonly 成员</span><span class="sxs-lookup"><span data-stu-id="e0ed1-106">Readonly members</span></span>](#readonly-members)
- [<span data-ttu-id="e0ed1-107">默认接口成员</span><span class="sxs-lookup"><span data-stu-id="e0ed1-107">Default interface members</span></span>](#default-interface-members)
- <span data-ttu-id="e0ed1-108">[模式匹配增强功能](#more-patterns-in-more-places)：</span><span class="sxs-lookup"><span data-stu-id="e0ed1-108">[Pattern matching enhancements](#more-patterns-in-more-places):</span></span>
  * [<span data-ttu-id="e0ed1-109">Switch 表达式</span><span class="sxs-lookup"><span data-stu-id="e0ed1-109">Switch expressions</span></span>](#switch-expressions)
  * [<span data-ttu-id="e0ed1-110">属性模式</span><span class="sxs-lookup"><span data-stu-id="e0ed1-110">Property patterns</span></span>](#property-patterns)
  * [<span data-ttu-id="e0ed1-111">元组模式</span><span class="sxs-lookup"><span data-stu-id="e0ed1-111">Tuple patterns</span></span>](#tuple-patterns)
  * [<span data-ttu-id="e0ed1-112">位置模式</span><span class="sxs-lookup"><span data-stu-id="e0ed1-112">Positional patterns</span></span>](#positional-patterns)
- [<span data-ttu-id="e0ed1-113">Using 声明</span><span class="sxs-lookup"><span data-stu-id="e0ed1-113">Using declarations</span></span>](#using-declarations)
- [<span data-ttu-id="e0ed1-114">静态本地函数</span><span class="sxs-lookup"><span data-stu-id="e0ed1-114">Static local functions</span></span>](#static-local-functions)
- [<span data-ttu-id="e0ed1-115">可处置的 ref 结构</span><span class="sxs-lookup"><span data-stu-id="e0ed1-115">Disposable ref structs</span></span>](#disposable-ref-structs)
- [<span data-ttu-id="e0ed1-116">可为空引用类型</span><span class="sxs-lookup"><span data-stu-id="e0ed1-116">Nullable reference types</span></span>](#nullable-reference-types)
- [<span data-ttu-id="e0ed1-117">异步流</span><span class="sxs-lookup"><span data-stu-id="e0ed1-117">Asynchronous streams</span></span>](#asynchronous-streams)
- [<span data-ttu-id="e0ed1-118">索引和范围</span><span class="sxs-lookup"><span data-stu-id="e0ed1-118">Indices and ranges</span></span>](#indices-and-ranges)

> [!NOTE]
> <span data-ttu-id="e0ed1-119">本文针对 C# 8.0 预览版 5 进行了最后一次更新。</span><span class="sxs-lookup"><span data-stu-id="e0ed1-119">This article was last updated for C# 8.0 preview 5.</span></span>

<span data-ttu-id="e0ed1-120">本文的剩余部分将简要介绍这些功能。</span><span class="sxs-lookup"><span data-stu-id="e0ed1-120">The remainder of this article briefly describes these features.</span></span> <span data-ttu-id="e0ed1-121">如果有详细讲解的文章，则将提供指向这些教程和概述的链接。</span><span class="sxs-lookup"><span data-stu-id="e0ed1-121">Where in-depth articles are available, links to those tutorials and overviews are provided.</span></span>

## <a name="readonly-members"></a><span data-ttu-id="e0ed1-122">Readonly 成员</span><span class="sxs-lookup"><span data-stu-id="e0ed1-122">Readonly members</span></span>

<span data-ttu-id="e0ed1-123">可将 `readonly` 修饰符应用于结构的任何成员。</span><span class="sxs-lookup"><span data-stu-id="e0ed1-123">You can apply the `readonly` modifier to any member of a struct.</span></span> <span data-ttu-id="e0ed1-124">它指示该成员不会修改状态。</span><span class="sxs-lookup"><span data-stu-id="e0ed1-124">It indicates that the member does not modify state.</span></span> <span data-ttu-id="e0ed1-125">这比将 `readonly` 修饰符应用于 `struct` 声明更精细。</span><span class="sxs-lookup"><span data-stu-id="e0ed1-125">It's more granular than applying the `readonly` modifier to a `struct` declaration.</span></span>  <span data-ttu-id="e0ed1-126">请考虑以下可变结构：</span><span class="sxs-lookup"><span data-stu-id="e0ed1-126">Consider the following mutable struct:</span></span>

```csharp
public struct Point
{
    public double X { get; set; }
    public double Y { get; set; }
    public double Distance => Math.Sqrt(X * X + Y * Y);

    public override string ToString() =>
        $"({X}, {Y}) is {Distance} from the origin";
}
```

<span data-ttu-id="e0ed1-127">像大多数结构一样， `ToString()` 方法不会修改状态。</span><span class="sxs-lookup"><span data-stu-id="e0ed1-127">Like most structs, the `ToString()` method does not modify state.</span></span> <span data-ttu-id="e0ed1-128">可以通过将 `readonly` 修饰符添加到 `ToString()` 的声明来对此进行指示：</span><span class="sxs-lookup"><span data-stu-id="e0ed1-128">You could indicate that by adding the `readonly` modifier to the declaration of `ToString()`:</span></span>

```csharp
public readonly override string ToString() =>
    $"({X}, {Y}) is {Distance} from the origin";
```

<span data-ttu-id="e0ed1-129">上述更改会生成编译器警告，因为 `ToString` 访问 `Distance` 属性，该属性未标记为 `readonly`：</span><span class="sxs-lookup"><span data-stu-id="e0ed1-129">The preceding change generates a compiler warning, because `ToString` accesses the `Distance` property, which is not marked `readonly`:</span></span>

```console
warning CS8656: Call to non-readonly member 'Point.Distance.get' from a 'readonly' member results in an implicit copy of 'this'
```

<span data-ttu-id="e0ed1-130">需要创建防御性副本时，编译器会发出警告。</span><span class="sxs-lookup"><span data-stu-id="e0ed1-130">The compiler warns you when it needs to create a defensive copy.</span></span>  <span data-ttu-id="e0ed1-131">`Distance` 属性不会更改状态，因此可以通过将 `readonly` 修饰符添加到声明来修复此警告：</span><span class="sxs-lookup"><span data-stu-id="e0ed1-131">The `Distance` property does not change state, so you can fix this warning by adding the `readonly` modifier to the declaration:</span></span>

```csharp
public readonly double Distance => Math.Sqrt(X * X + Y * Y);
```

<span data-ttu-id="e0ed1-132">请注意，`readonly` 修饰符对于只读属性是必需的。</span><span class="sxs-lookup"><span data-stu-id="e0ed1-132">Notice that the `readonly` modifier is necessary on a read only property.</span></span> <span data-ttu-id="e0ed1-133">编译器不会假设 `get` 访问器不修改状态；必须明确声明 `readonly`。</span><span class="sxs-lookup"><span data-stu-id="e0ed1-133">The compiler doesn't assume `get` accessors do not modify state; you must declare `readonly` explicitly.</span></span> <span data-ttu-id="e0ed1-134">编译器会强制实施以下规则：`readonly` 成员不修改状态。</span><span class="sxs-lookup"><span data-stu-id="e0ed1-134">The compiler does enforce the rule that `readonly` members do not modify state.</span></span> <span data-ttu-id="e0ed1-135">除非删除 `readonly` 修饰符，否则不会编译以下方法：</span><span class="sxs-lookup"><span data-stu-id="e0ed1-135">The following method will not compile unless you remove the `readonly` modifier:</span></span>

```csharp
public readonly void Translate(int xOffset, int yOffset)
{
    X += xOffset;
    Y += yOffset;
}
```

<span data-ttu-id="e0ed1-136">通过此功能，可以指定设计意图，使编译器可以强制执行该意图，并基于该意图进行优化。</span><span class="sxs-lookup"><span data-stu-id="e0ed1-136">This feature lets you specify your design intent so the compiler can enforce it, and make optimizations based on that intent.</span></span>

## <a name="default-interface-members"></a><span data-ttu-id="e0ed1-137">默认接口成员</span><span class="sxs-lookup"><span data-stu-id="e0ed1-137">Default interface members</span></span>

<span data-ttu-id="e0ed1-138">现在可以将成员添加到接口，并为这些成员提供实现。</span><span class="sxs-lookup"><span data-stu-id="e0ed1-138">You can now add members to interfaces and provide an implementation for those members.</span></span> <span data-ttu-id="e0ed1-139">借助此语言功能，API 作者可以将方法添加到以后版本的接口中，而不会破坏与该接口当前实现的源或二进制文件兼容性。</span><span class="sxs-lookup"><span data-stu-id="e0ed1-139">This language feature enables API authors to add methods to an interface in later versions without breaking source or binary compatibility with existing implementations of that interface.</span></span> <span data-ttu-id="e0ed1-140">现有的实现继承默认实现。</span><span class="sxs-lookup"><span data-stu-id="e0ed1-140">Existing implementations *inherit* the default implementation.</span></span> <span data-ttu-id="e0ed1-141">此功能使 C# 与面向 Android 或 Swift 的 API 进行互操作，此类 API 支持类似功能。</span><span class="sxs-lookup"><span data-stu-id="e0ed1-141">This feature also enables C# to interoperate with APIs that target Android or Swift, which support similar features.</span></span> <span data-ttu-id="e0ed1-142">默认接口成员还支持类似于“特征”语言功能的方案。</span><span class="sxs-lookup"><span data-stu-id="e0ed1-142">Default interface members also enable scenarios similar to a "traits" language feature.</span></span>

<span data-ttu-id="e0ed1-143">默认接口成员会影响很多方案和语言元素。</span><span class="sxs-lookup"><span data-stu-id="e0ed1-143">Default interface members affects many scenarios and language elements.</span></span> <span data-ttu-id="e0ed1-144">我们的第一个教程介绍如何[使用默认实现更新接口](../tutorials/default-interface-members-versions.md)。</span><span class="sxs-lookup"><span data-stu-id="e0ed1-144">Our first tutorial covers [updating an interface with default implementations](../tutorials/default-interface-members-versions.md).</span></span> <span data-ttu-id="e0ed1-145">其他教程和参考更新将适时公开发布。</span><span class="sxs-lookup"><span data-stu-id="e0ed1-145">Other tutorials and reference updates are coming in time for general release.</span></span>

## <a name="more-patterns-in-more-places"></a><span data-ttu-id="e0ed1-146">在更多位置中使用更多模式</span><span class="sxs-lookup"><span data-stu-id="e0ed1-146">More patterns in more places</span></span>

<span data-ttu-id="e0ed1-147">模式匹配提供了在相关但不同类型的数据中提供形状相关功能的工具。</span><span class="sxs-lookup"><span data-stu-id="e0ed1-147">**Pattern matching** gives tools to provide shape-dependent functionality across related but different kinds of data.</span></span> <span data-ttu-id="e0ed1-148">C# 7.0 通过使用 [`is`](../language-reference/keywords/is.md) 表达式和 [`switch`](../language-reference/keywords/switch.md) 语句引入了类型模式和常量模式的语法。</span><span class="sxs-lookup"><span data-stu-id="e0ed1-148">C# 7.0 introduced syntax for type patterns and constant patterns by using the [`is`](../language-reference/keywords/is.md) expression and the [`switch`](../language-reference/keywords/switch.md) statement.</span></span> <span data-ttu-id="e0ed1-149">这些功能代表了支持数据和功能分离的编程范例的初步尝试。</span><span class="sxs-lookup"><span data-stu-id="e0ed1-149">These features represented the first tentative steps toward supporting programming paradigms where data and functionality live apart.</span></span> <span data-ttu-id="e0ed1-150">随着行业转向更多微服务和其他基于云的体系结构，还需要其他语言工具。</span><span class="sxs-lookup"><span data-stu-id="e0ed1-150">As the industry moves toward more microservices and other cloud-based architectures, other language tools are needed.</span></span>

<span data-ttu-id="e0ed1-151">C# 8.0 扩展了此词汇表，这样就可以在代码中的更多位置使用更多模式表达式。</span><span class="sxs-lookup"><span data-stu-id="e0ed1-151">C# 8.0 expands this vocabulary so you can use more pattern expressions in more places in your code.</span></span> <span data-ttu-id="e0ed1-152">当数据和功能分离时，请考虑使用这些功能。</span><span class="sxs-lookup"><span data-stu-id="e0ed1-152">Consider these features when your data and functionality are separate.</span></span> <span data-ttu-id="e0ed1-153">当算法依赖于对象运行时类型以外的事实时，请考虑使用模式匹配。</span><span class="sxs-lookup"><span data-stu-id="e0ed1-153">Consider pattern matching when your algorithms depend on a fact other than the runtime type of an object.</span></span> <span data-ttu-id="e0ed1-154">这些技术提供了另一种表达设计的方式。</span><span class="sxs-lookup"><span data-stu-id="e0ed1-154">These techniques provide another way to express designs.</span></span>

<span data-ttu-id="e0ed1-155">除了可以在新位置使用新模式之外，C# 8.0 还添加了“递归模式”。</span><span class="sxs-lookup"><span data-stu-id="e0ed1-155">In addition to new patterns in new places, C# 8.0 adds **recursive patterns**.</span></span> <span data-ttu-id="e0ed1-156">任何模式表达式的结果都是一个表达式。</span><span class="sxs-lookup"><span data-stu-id="e0ed1-156">The result of any pattern expression is an expression.</span></span> <span data-ttu-id="e0ed1-157">递归模式只是应用于另一个模式表达式输出的模式表达式。</span><span class="sxs-lookup"><span data-stu-id="e0ed1-157">A recursive pattern is simply a pattern expression applied to the output of another pattern expression.</span></span>

### <a name="switch-expressions"></a><span data-ttu-id="e0ed1-158">Switch 表达式</span><span class="sxs-lookup"><span data-stu-id="e0ed1-158">switch expressions</span></span>

<span data-ttu-id="e0ed1-159">通常情况下，[`switch`](../language-reference/keywords/switch.md) 语句在其每个 `case` 块中生成一个值。</span><span class="sxs-lookup"><span data-stu-id="e0ed1-159">Often, a [`switch`](../language-reference/keywords/switch.md) statement produces a value in each of its `case` blocks.</span></span> <span data-ttu-id="e0ed1-160">借助 Switch 表达式，可以使用更简洁的表达式语法。</span><span class="sxs-lookup"><span data-stu-id="e0ed1-160">**Switch expressions** enable you to use more concise expression syntax.</span></span> <span data-ttu-id="e0ed1-161">只有些许重复的 `case` 和 `break` 关键字和大括号。</span><span class="sxs-lookup"><span data-stu-id="e0ed1-161">There are fewer repetitive `case` and `break` keywords, and fewer curly braces.</span></span>  <span data-ttu-id="e0ed1-162">以下面列出彩虹颜色的枚举为例：</span><span class="sxs-lookup"><span data-stu-id="e0ed1-162">As an example, consider the following enum that lists the colors of the rainbow:</span></span>

```csharp
public enum Rainbow
{
    Red,
    Orange,
    Yellow,
    Green,
    Blue,
    Indigo,
    Violet
}
```

<span data-ttu-id="e0ed1-163">如果应用定义了通过 `R`、`G` 和 `B` 组件构造而成的 `RGBColor` 类型，可使用以下包含 switch 表达式的方法，将 `Rainbow` 转换为 RGB 值：</span><span class="sxs-lookup"><span data-stu-id="e0ed1-163">If your application defined an `RGBColor` type that is constructed from the `R`, `G` and `B` components, you could convert a `Rainbow` value to its RGB values using the following method containing a switch expression:</span></span>

```csharp
public static RGBColor FromRainbow(Rainbow colorBand) =>
    colorBand switch
    {
        Rainbow.Red    => new RGBColor(0xFF, 0x00, 0x00),
        Rainbow.Orange => new RGBColor(0xFF, 0x7F, 0x00),
        Rainbow.Yellow => new RGBColor(0xFF, 0xFF, 0x00),
        Rainbow.Green  => new RGBColor(0x00, 0xFF, 0x00),
        Rainbow.Blue   => new RGBColor(0x00, 0x00, 0xFF),
        Rainbow.Indigo => new RGBColor(0x4B, 0x00, 0x82),
        Rainbow.Violet => new RGBColor(0x94, 0x00, 0xD3),
        _              => throw new ArgumentException(message: "invalid enum value", paramName: nameof(colorBand)),
    };
```

<span data-ttu-id="e0ed1-164">这里有几个语法改进：</span><span class="sxs-lookup"><span data-stu-id="e0ed1-164">There are several syntax improvements here:</span></span>

- <span data-ttu-id="e0ed1-165">变量位于 `switch` 关键字之前。</span><span class="sxs-lookup"><span data-stu-id="e0ed1-165">The variable comes before the `switch` keyword.</span></span> <span data-ttu-id="e0ed1-166">不同的顺序使得在视觉上可以很轻松地区分 switch 表达式和 switch 语句。</span><span class="sxs-lookup"><span data-stu-id="e0ed1-166">The different order makes it visually easy to distinguish the switch expression from the switch statement.</span></span>
- <span data-ttu-id="e0ed1-167">将 `case` 和 `:` 元素替换为 `=>`。</span><span class="sxs-lookup"><span data-stu-id="e0ed1-167">The `case` and `:` elements are replaced with `=>`.</span></span> <span data-ttu-id="e0ed1-168">它更简洁，更直观。</span><span class="sxs-lookup"><span data-stu-id="e0ed1-168">It's more concise and intuitive.</span></span>
- <span data-ttu-id="e0ed1-169">将 `default` 事例替换为 `_` 弃元。</span><span class="sxs-lookup"><span data-stu-id="e0ed1-169">The `default` case is replaced with a `_` discard.</span></span>
- <span data-ttu-id="e0ed1-170">正文是表达式，不是语句。</span><span class="sxs-lookup"><span data-stu-id="e0ed1-170">The bodies are expressions, not statements.</span></span>

<span data-ttu-id="e0ed1-171">将其与使用经典 `switch` 语句的等效代码进行对比：</span><span class="sxs-lookup"><span data-stu-id="e0ed1-171">Contrast that with the equivalent code using the classic `switch` statement:</span></span>

```csharp
public static RGBColor FromRainbowClassic(Rainbow colorBand)
{
    switch (colorBand)
    {
        case Rainbow.Red:
            return new RGBColor(0xFF, 0x00, 0x00);
        case Rainbow.Orange:
            return new RGBColor(0xFF, 0x7F, 0x00);
        case Rainbow.Yellow:
            return new RGBColor(0xFF, 0xFF, 0x00);
        case Rainbow.Green:
            return new RGBColor(0x00, 0xFF, 0x00);
        case Rainbow.Blue:
            return new RGBColor(0x00, 0x00, 0xFF);
        case Rainbow.Indigo:
            return new RGBColor(0x4B, 0x00, 0x82);
        case Rainbow.Violet:
            return new RGBColor(0x94, 0x00, 0xD3);
        default:
            throw new ArgumentException(message: "invalid enum value", paramName: nameof(colorBand));
    };
}
```

### <a name="property-patterns"></a><span data-ttu-id="e0ed1-172">属性模式</span><span class="sxs-lookup"><span data-stu-id="e0ed1-172">Property patterns</span></span>

<span data-ttu-id="e0ed1-173">借助属性模式，可以匹配所检查的对象的属性。</span><span class="sxs-lookup"><span data-stu-id="e0ed1-173">The **property pattern** enables you to match on properties of the object examined.</span></span> <span data-ttu-id="e0ed1-174">请看一个电子商务网站的示例，该网站必须根据买家地址计算销售税。</span><span class="sxs-lookup"><span data-stu-id="e0ed1-174">Consider an eCommerce site that must compute sales tax based on the buyer's address.</span></span> <span data-ttu-id="e0ed1-175">这种计算不是 `Address` 类的核心职责。</span><span class="sxs-lookup"><span data-stu-id="e0ed1-175">That computation is not a core responsibility of an `Address` class.</span></span> <span data-ttu-id="e0ed1-176">它会随时间变化，可能比地址格式的更改更频繁。</span><span class="sxs-lookup"><span data-stu-id="e0ed1-176">It will change over time, likely more often than address format changes.</span></span> <span data-ttu-id="e0ed1-177">销售税的金额取决于地址的 `State` 属性。</span><span class="sxs-lookup"><span data-stu-id="e0ed1-177">The amount of sales tax depends on the `State` property of the address.</span></span> <span data-ttu-id="e0ed1-178">下面的方法使用属性模式从地址和价格计算销售税：</span><span class="sxs-lookup"><span data-stu-id="e0ed1-178">The following method uses the property pattern to compute the sales tax from the address and the price:</span></span>

```csharp
public static decimal ComputeSalesTax(Address location, decimal salePrice) =>
    location switch
    {
        { State: "WA" } => salePrice * 0.06M,
        { State: "MN" } => salePrice * 0.75M,
        { State: "MI" } => salePrice * 0.05M,
        // other cases removed for brevity...
        _ => 0M
    };
```

<span data-ttu-id="e0ed1-179">模式匹配为表达此算法创建了简洁的语法。</span><span class="sxs-lookup"><span data-stu-id="e0ed1-179">Pattern matching creates a concise syntax for expressing this algorithm.</span></span>

### <a name="tuple-patterns"></a><span data-ttu-id="e0ed1-180">元组模式</span><span class="sxs-lookup"><span data-stu-id="e0ed1-180">Tuple patterns</span></span>

<span data-ttu-id="e0ed1-181">一些算法依赖于多个输入。</span><span class="sxs-lookup"><span data-stu-id="e0ed1-181">Some algorithms depend on multiple inputs.</span></span> <span data-ttu-id="e0ed1-182">使用元组模式，可根据表示为[元组](../tuples.md)的多个值进行切换。</span><span class="sxs-lookup"><span data-stu-id="e0ed1-182">**Tuple patterns** allow you to switch based on multiple values expressed as a [tuple](../tuples.md).</span></span>  <span data-ttu-id="e0ed1-183">以下代码显示了游戏“rock, paper, scissors（石头剪刀布）”的切换表达式：：</span><span class="sxs-lookup"><span data-stu-id="e0ed1-183">The following code shows a switch expression for the game *rock, paper, scissors*:</span></span>

```csharp
public static string RockPaperScissors(string first, string second)
    => (first, second) switch
    {
        ("rock", "paper") => "rock is covered by paper. Paper wins.",
        ("rock", "scissors") => "rock breaks scissors. Rock wins.",
        ("paper", "rock") => "paper covers rock. Paper wins.",
        ("paper", "scissors") => "paper is cut by scissors. Scissors wins.",
        ("scissors", "rock") => "scissors is broken by rock. Rock wins.",
        ("scissors", "paper") => "scissors cuts paper. Scissors wins.",
        (_, _) => "tie"
    };
```

<span data-ttu-id="e0ed1-184">消息指示获胜者。</span><span class="sxs-lookup"><span data-stu-id="e0ed1-184">The messages indicate the winner.</span></span> <span data-ttu-id="e0ed1-185">弃元表示平局(石头剪刀布游戏)的三种组合或其他文本输入。</span><span class="sxs-lookup"><span data-stu-id="e0ed1-185">The discard case represents the three combinations for ties, or other text inputs.</span></span>

### <a name="positional-patterns"></a><span data-ttu-id="e0ed1-186">位置模式</span><span class="sxs-lookup"><span data-stu-id="e0ed1-186">Positional patterns</span></span>

<span data-ttu-id="e0ed1-187">某些类型包含 `Deconstruct` 方法，该方法将其属性解构为离散变量。</span><span class="sxs-lookup"><span data-stu-id="e0ed1-187">Some types include a `Deconstruct` method that deconstructs its properties into discrete variables.</span></span> <span data-ttu-id="e0ed1-188">如果可以访问 `Deconstruct` 方法，就可以使用位置模式检查对象的属性并将这些属性用于模式。</span><span class="sxs-lookup"><span data-stu-id="e0ed1-188">When a `Deconstruct` method is accessible, you can use **positional patterns** to inspect properties of the object and use those properties for a pattern.</span></span>  <span data-ttu-id="e0ed1-189">考虑以下 `Point` 类，其中包含用于为 `X` 和 `Y` 创建离散变量的 `Deconstruct` 方法：</span><span class="sxs-lookup"><span data-stu-id="e0ed1-189">Consider the following `Point` class that includes a `Deconstruct` method to create discrete variables for `X` and `Y`:</span></span>

```csharp
public class Point
{
    public int X { get; }
    public int Y { get; }

    public Point(int x, int y) => (X, Y) = (x, y);

    public void Deconstruct(out int x, out int y) =>
        (x, y) = (X, Y);
}
```

<span data-ttu-id="e0ed1-190">此外，请考虑以下表示象限的各种位置的枚举：</span><span class="sxs-lookup"><span data-stu-id="e0ed1-190">Additionally, consider the following enum that represents various positions of a quadrant:</span></span>

```csharp
public enum Quadrant
{
    Unknown,
    Origin,
    One,
    Two,
    Three,
    Four,
    OnBorder
}
```

<span data-ttu-id="e0ed1-191">下面的方法使用位置模式来提取 `x` 和 `y` 的值。</span><span class="sxs-lookup"><span data-stu-id="e0ed1-191">The following method uses the **positional pattern** to extract the values of `x` and `y`.</span></span> <span data-ttu-id="e0ed1-192">然后，它使用 `when` 子句来确定该点的 `Quadrant`：</span><span class="sxs-lookup"><span data-stu-id="e0ed1-192">Then, it uses a `when` clause to determine the `Quadrant` of the point:</span></span>

```csharp
static Quadrant GetQuadrant(Point point) => point switch
{
    (0, 0) => Quadrant.Origin,
    var (x, y) when x > 0 && y > 0 => Quadrant.One,
    var (x, y) when x < 0 && y > 0 => Quadrant.Two,
    var (x, y) when x < 0 && y < 0 => Quadrant.Three,
    var (x, y) when x > 0 && y < 0 => Quadrant.Four,
    var (_, _) => Quadrant.OnBorder,
    _ => Quadrant.Unknown
};
```

<span data-ttu-id="e0ed1-193">当 `x` 或 `y` 为 0（但不是两者同时为 0）时，前一个开关中的弃元模式匹配。</span><span class="sxs-lookup"><span data-stu-id="e0ed1-193">The discard pattern in the preceding switch matches when either `x` or `y` is 0, but not both.</span></span> <span data-ttu-id="e0ed1-194">Switch 表达式必须要么生成值，要么引发异常。</span><span class="sxs-lookup"><span data-stu-id="e0ed1-194">A switch expression must either produce a value or throw an exception.</span></span> <span data-ttu-id="e0ed1-195">如果这些情况都不匹配，则 switch 表达式将引发异常。</span><span class="sxs-lookup"><span data-stu-id="e0ed1-195">If none of the cases match, the switch expression throws an exception.</span></span> <span data-ttu-id="e0ed1-196">如果没有在 switch 表达式中涵盖所有可能的情况，编译器将生成一个警告。</span><span class="sxs-lookup"><span data-stu-id="e0ed1-196">The compiler generates a warning for you if you do not cover all possible cases in your switch expression.</span></span>

<span data-ttu-id="e0ed1-197">可在此[模式匹配高级教程](../tutorials/pattern-matching.md)中探索模式匹配方法。</span><span class="sxs-lookup"><span data-stu-id="e0ed1-197">You can explore pattern matching techniques in this [advanced tutorial on pattern matching](../tutorials/pattern-matching.md).</span></span>

## <a name="using-declarations"></a><span data-ttu-id="e0ed1-198">using 声明</span><span class="sxs-lookup"><span data-stu-id="e0ed1-198">using declarations</span></span>

<span data-ttu-id="e0ed1-199">using 声明是前面带 `using` 关键字的变量声明。</span><span class="sxs-lookup"><span data-stu-id="e0ed1-199">A **using declaration** is a variable declaration preceded by the `using` keyword.</span></span> <span data-ttu-id="e0ed1-200">它指示编译器声明的变量应在封闭范围的末尾进行处理。</span><span class="sxs-lookup"><span data-stu-id="e0ed1-200">It tells the compiler that the variable being declared should be disposed at the end of the enclosing scope.</span></span> <span data-ttu-id="e0ed1-201">以下面编写文本文件的代码为例：</span><span class="sxs-lookup"><span data-stu-id="e0ed1-201">For example, consider the following code that writes a text file:</span></span>

```csharp
static void WriteLinesToFile(IEnumerable<string> lines)
{
    using var file = new System.IO.StreamWriter("WriteLines2.txt");
    foreach (string line in lines)
    {
        // If the line doesn't contain the word 'Second', write the line to the file.
        if (!line.Contains("Second"))
        {
            file.WriteLine(line);
        }
    }
// file is disposed here
}
```

<span data-ttu-id="e0ed1-202">在前面的示例中，当到达方法的右括号时，将对该文件进行处理。</span><span class="sxs-lookup"><span data-stu-id="e0ed1-202">In the preceding example, the file is disposed when the closing brace for the method is reached.</span></span> <span data-ttu-id="e0ed1-203">这是声明 `file` 的范围的末尾。</span><span class="sxs-lookup"><span data-stu-id="e0ed1-203">That's the end of the scope in which `file` is declared.</span></span> <span data-ttu-id="e0ed1-204">前面的代码相当于下面使用经典 [using 语句](../language-reference/keywords/using-statement.md)语句的代码：</span><span class="sxs-lookup"><span data-stu-id="e0ed1-204">The preceding code is equivalent to the following code using the classic [using statements](../language-reference/keywords/using-statement.md) statement:</span></span>

```csharp
static void WriteLinesToFile(IEnumerable<string> lines)
{
    using (var file = new System.IO.StreamWriter("WriteLines2.txt"))
    {
        foreach (string line in lines)
        {
            // If the line doesn't contain the word 'Second', write the line to the file.
            if (!line.Contains("Second"))
            {
                file.WriteLine(line);
            }
        }
    } // file is disposed here
}
```

<span data-ttu-id="e0ed1-205">在前面的示例中，当到达与 `using` 语句关联的右括号时，将对该文件进行处理。</span><span class="sxs-lookup"><span data-stu-id="e0ed1-205">In the preceding example, the file is disposed when the closing brace associated with the `using` statement is reached.</span></span>

<span data-ttu-id="e0ed1-206">在这两种情况下，编译器将生成对 `Dispose()` 的调用。</span><span class="sxs-lookup"><span data-stu-id="e0ed1-206">In both cases, the compiler generates the call to `Dispose()`.</span></span> <span data-ttu-id="e0ed1-207">如果 using 语句中的表达式不可处置，编译器将生成一个错误。</span><span class="sxs-lookup"><span data-stu-id="e0ed1-207">The compiler generates an error if the expression in the using statement is not disposable.</span></span>

## <a name="static-local-functions"></a><span data-ttu-id="e0ed1-208">静态本地函数</span><span class="sxs-lookup"><span data-stu-id="e0ed1-208">Static local functions</span></span>

<span data-ttu-id="e0ed1-209">现在可以向本地函数添加 `static` 修饰符，以确保本地函数不会从封闭范围捕获（引用）任何变量。</span><span class="sxs-lookup"><span data-stu-id="e0ed1-209">You can now add the `static` modifier to local functions to ensure that local function doesn't capture (reference) any variables from the enclosing scope.</span></span> <span data-ttu-id="e0ed1-210">这样做会生成 `CS8421`，“静态本地函数不能包含对 \<variable> 的引用”。</span><span class="sxs-lookup"><span data-stu-id="e0ed1-210">Doing so generates `CS8421`, "A static local function can't contain a reference to \<variable>."</span></span> 

<span data-ttu-id="e0ed1-211">考虑下列代码。</span><span class="sxs-lookup"><span data-stu-id="e0ed1-211">Consider the following code.</span></span> <span data-ttu-id="e0ed1-212">本地函数 `LocalFunction` 访问在封闭范围（方法 `M`）中声明的变量 `y`。</span><span class="sxs-lookup"><span data-stu-id="e0ed1-212">The local function `LocalFunction` accesses the variable `y`, declared in the enclosing scope (the method `M`).</span></span> <span data-ttu-id="e0ed1-213">因此，不能用 `static` 修饰符来声明 `LocalFunction`：</span><span class="sxs-lookup"><span data-stu-id="e0ed1-213">Therefore, `LocalFunction` can't be declared with the `static` modifier:</span></span>

```csharp
int M()
{
    int y;
    LocalFunction();
    return y;

    void LocalFunction() => y = 0;
}
```

<span data-ttu-id="e0ed1-214">下面的代码包含一个静态本地函数。</span><span class="sxs-lookup"><span data-stu-id="e0ed1-214">The following code contains a static local function.</span></span> <span data-ttu-id="e0ed1-215">它可以是静态的，因为它不访问封闭范围中的任何变量：</span><span class="sxs-lookup"><span data-stu-id="e0ed1-215">It can be static because it doesn't access any variables in the enclosing scope:</span></span>

```csharp
int M()
{
    int y = 5;
    int x = 7;
    return Add(x, y);

    static int Add(int left, int right) => left + right;
}
```

## <a name="disposable-ref-structs"></a><span data-ttu-id="e0ed1-216">可处置的 ref 结构</span><span class="sxs-lookup"><span data-stu-id="e0ed1-216">Disposable ref structs</span></span>

<span data-ttu-id="e0ed1-217">用 `ref` 修饰符声明的 `struct` 可能无法实现任何接口，因此无法实现 <xref:System.IDisposable>。</span><span class="sxs-lookup"><span data-stu-id="e0ed1-217">A `struct` declared with the `ref` modifier may not implement any interfaces and so cannot implement <xref:System.IDisposable>.</span></span> <span data-ttu-id="e0ed1-218">因此，要能够处理 `ref struct`，它必须有一个可访问的 `void Dispose()` 方法。</span><span class="sxs-lookup"><span data-stu-id="e0ed1-218">Therefore, to enable a `ref struct` to be disposed, it must have an accessible `void Dispose()` method.</span></span> <span data-ttu-id="e0ed1-219">这同样适用于 `readonly ref struct` 声明。</span><span class="sxs-lookup"><span data-stu-id="e0ed1-219">This also applies to `readonly ref struct` declarations.</span></span>

## <a name="nullable-reference-types"></a><span data-ttu-id="e0ed1-220">可为空引用类型</span><span class="sxs-lookup"><span data-stu-id="e0ed1-220">Nullable reference types</span></span>

<span data-ttu-id="e0ed1-221">在可为空注释上下文中，引用类型的任何变量都被视为不可为空引用类型。</span><span class="sxs-lookup"><span data-stu-id="e0ed1-221">Inside a nullable annotation context, any variable of a reference type is considered to be a **nonnullable reference type**.</span></span> <span data-ttu-id="e0ed1-222">若要指示一个变量可能为 null，必须在类型名称后面附加 `?`，以将该变量声明为可为空引用类型。</span><span class="sxs-lookup"><span data-stu-id="e0ed1-222">If you want to indicate that a variable may be null, you must append the type name with the `?` to declare the variable as a **nullable reference type**.</span></span>

<span data-ttu-id="e0ed1-223">对于不可为空引用类型，编译器使用流分析来确保在声明时将本地变量初始化为非 Null 值。</span><span class="sxs-lookup"><span data-stu-id="e0ed1-223">For nonnullable reference types, the compiler uses flow analysis to ensure that local variables are initialized to a non-null value when declared.</span></span> <span data-ttu-id="e0ed1-224">字段必须在构造过程中初始化。</span><span class="sxs-lookup"><span data-stu-id="e0ed1-224">Fields must be initialized during construction.</span></span> <span data-ttu-id="e0ed1-225">如果没有通过调用任何可用的构造函数或通过初始化表达式来设置变量，编译器将生成警告。</span><span class="sxs-lookup"><span data-stu-id="e0ed1-225">The compiler generates a warning if the variable is not set by a call to any of the available constructors or by an initializer.</span></span> <span data-ttu-id="e0ed1-226">此外，不能向不可为空引用类型分配一个可以为 Null 的值。</span><span class="sxs-lookup"><span data-stu-id="e0ed1-226">Furthermore, nonnullable reference types can't be assigned a value that could be null.</span></span>

<span data-ttu-id="e0ed1-227">不对可为空引用类型进行检查以确保它们没有被赋予 Null 值或初始化为 Null。</span><span class="sxs-lookup"><span data-stu-id="e0ed1-227">Nullable reference types aren't checked to ensure they aren't assigned or initialized to null.</span></span> <span data-ttu-id="e0ed1-228">不过，编译器使用流分析来确保可为空引用类型的任何变量在被访问或分配给不可为空引用类型之前，都会对其 Null 性进行检查。</span><span class="sxs-lookup"><span data-stu-id="e0ed1-228">However, the compiler uses flow analysis to ensure that any variable of a nullable reference type is checked against null before it's accessed or assigned to a nonnullable reference type.</span></span>

<span data-ttu-id="e0ed1-229">可以在[可为空引用类型](../nullable-references.md)的概述中了解该功能的更多信息。</span><span class="sxs-lookup"><span data-stu-id="e0ed1-229">You can learn more about the feature in the overview of [nullable reference types](../nullable-references.md).</span></span> <span data-ttu-id="e0ed1-230">可以在此[可为空引用类型教程](../tutorials/nullable-reference-types.md)中的新应用程序中自行尝试。</span><span class="sxs-lookup"><span data-stu-id="e0ed1-230">Try it yourself in a new application in this [nullable reference types tutorial](../tutorials/nullable-reference-types.md).</span></span> <span data-ttu-id="e0ed1-231">在[迁移应用程序以使用可为空引用类型教程](../tutorials/upgrade-to-nullable-references.md)中了解迁移现有代码库以使用可为空引用类型的步骤。</span><span class="sxs-lookup"><span data-stu-id="e0ed1-231">Learn about the steps to migrate an existing codebase to make use of nullable reference types in the [migrating an application to use nullable reference types tutorial](../tutorials/upgrade-to-nullable-references.md).</span></span>

## <a name="asynchronous-streams"></a><span data-ttu-id="e0ed1-232">异步流</span><span class="sxs-lookup"><span data-stu-id="e0ed1-232">Asynchronous streams</span></span>

<span data-ttu-id="e0ed1-233">从 C# 8.0 开始，可以创建并以异步方式使用流。</span><span class="sxs-lookup"><span data-stu-id="e0ed1-233">Starting with C# 8.0, you can create and consume streams asynchronously.</span></span> <span data-ttu-id="e0ed1-234">返回异步流的方法有三个属性：</span><span class="sxs-lookup"><span data-stu-id="e0ed1-234">A method that returns an asynchronous stream has three properties:</span></span>

1. <span data-ttu-id="e0ed1-235">它是用 `async` 修饰符声明的。</span><span class="sxs-lookup"><span data-stu-id="e0ed1-235">It's declared with the `async` modifier.</span></span>
1. <span data-ttu-id="e0ed1-236">它将返回 <xref:System.Collections.Generic.IAsyncEnumerable%601>。</span><span class="sxs-lookup"><span data-stu-id="e0ed1-236">It returns an <xref:System.Collections.Generic.IAsyncEnumerable%601>.</span></span>
1. <span data-ttu-id="e0ed1-237">该方法包含用于在异步流中返回连续元素的 `yield return` 语句。</span><span class="sxs-lookup"><span data-stu-id="e0ed1-237">The method contains `yield return` statements to return successive elements in the asynchronous stream.</span></span>

<span data-ttu-id="e0ed1-238">使用异步流需要在枚举流元素时在 `foreach` 关键字前面添加 `await` 关键字。</span><span class="sxs-lookup"><span data-stu-id="e0ed1-238">Consuming an asynchronous stream requires you to add the `await` keyword before the `foreach` keyword when you enumerate the elements of the stream.</span></span> <span data-ttu-id="e0ed1-239">添加 `await` 关键字需要枚举异步流的方法，以使用 `async` 修饰符进行声明并返回 `async` 方法允许的类型。</span><span class="sxs-lookup"><span data-stu-id="e0ed1-239">Adding the `await` keyword requires the method that enumerates the asynchronous stream to be declared with the `async` modifier and to return a type allowed for an `async` method.</span></span> <span data-ttu-id="e0ed1-240">通常这意味着返回 <xref:System.Threading.Tasks.Task> 或 <xref:System.Threading.Tasks.Task%601>。</span><span class="sxs-lookup"><span data-stu-id="e0ed1-240">Typically that means returning a <xref:System.Threading.Tasks.Task> or <xref:System.Threading.Tasks.Task%601>.</span></span> <span data-ttu-id="e0ed1-241">也可以为 <xref:System.Threading.Tasks.ValueTask> 或 <xref:System.Threading.Tasks.ValueTask%601>。</span><span class="sxs-lookup"><span data-stu-id="e0ed1-241">It can also be a <xref:System.Threading.Tasks.ValueTask> or <xref:System.Threading.Tasks.ValueTask%601>.</span></span> <span data-ttu-id="e0ed1-242">方法既可以使用异步流，也可以生成异步流，这意味着它将返回 <xref:System.Collections.Generic.IAsyncEnumerable%601>。</span><span class="sxs-lookup"><span data-stu-id="e0ed1-242">A method can both consume and produce an asynchronous stream, which means it would return an <xref:System.Collections.Generic.IAsyncEnumerable%601>.</span></span> <span data-ttu-id="e0ed1-243">下面的代码生成一个从 0 到 19 的序列，在生成每个数字之间等待 100 毫秒：</span><span class="sxs-lookup"><span data-stu-id="e0ed1-243">The following code generates a sequence from 0 to 19, waiting 100 ms between generating each number:</span></span>

```csharp
public static async System.Collections.Generic.IAsyncEnumerable<int> GenerateSequence()
{
    for (int i = 0; i < 20; i++)
    {
        await Task.Delay(100);
        yield return i;
    }
}
```

<span data-ttu-id="e0ed1-244">可以使用 `await foreach` 语句来枚举序列：</span><span class="sxs-lookup"><span data-stu-id="e0ed1-244">You would enumerate the sequence using the `await foreach` statement:</span></span>

```csharp
await foreach (var number in GenerateSequence())
{
    Console.WriteLine(number);
}
```

<span data-ttu-id="e0ed1-245">可以在[创建和使用异步流](../tutorials/generate-consume-asynchronous-stream.md)的教程中自行尝试异步流。</span><span class="sxs-lookup"><span data-stu-id="e0ed1-245">You can try asynchronous streams yourself in our tutorial on [creating and consuming async streams](../tutorials/generate-consume-asynchronous-stream.md).</span></span>

## <a name="indices-and-ranges"></a><span data-ttu-id="e0ed1-246">索引和范围</span><span class="sxs-lookup"><span data-stu-id="e0ed1-246">Indices and ranges</span></span>

<span data-ttu-id="e0ed1-247">范围和索引为在数组中指定子范围（<xref:System.Span%601> 或 <xref:System.ReadOnlySpan%601>）提供了简洁语法。</span><span class="sxs-lookup"><span data-stu-id="e0ed1-247">Ranges and indices provide a succinct syntax for specifying subranges in an array, <xref:System.Span%601>, or <xref:System.ReadOnlySpan%601>.</span></span>

<span data-ttu-id="e0ed1-248">此语言支持依赖于两个新类型和两个新运算符。</span><span class="sxs-lookup"><span data-stu-id="e0ed1-248">This language support relies on two new types, and two new operators.</span></span>
- <span data-ttu-id="e0ed1-249"><xref:System.Index?displayProperty=nameWithType> 表示一个序列索引。</span><span class="sxs-lookup"><span data-stu-id="e0ed1-249"><xref:System.Index?displayProperty=nameWithType> represents an index into a sequence.</span></span>
- <span data-ttu-id="e0ed1-250">`^` 运算符，指定一个索引与序列末尾相关。</span><span class="sxs-lookup"><span data-stu-id="e0ed1-250">The `^` operator, which specifies that an index is relative to the end of the sequence.</span></span>
- <span data-ttu-id="e0ed1-251"><xref:System.Range?displayProperty=nameWithType> 表示序列的子范围。</span><span class="sxs-lookup"><span data-stu-id="e0ed1-251"><xref:System.Range?displayProperty=nameWithType> represents a sub range of a sequence.</span></span>
- <span data-ttu-id="e0ed1-252">范围运算符 (`..`)，用于指定范围的开始和末尾，就像操作数一样。</span><span class="sxs-lookup"><span data-stu-id="e0ed1-252">The Range operator (`..`), which specifies the start and end of a range as is operands.</span></span>

<span data-ttu-id="e0ed1-253">让我们从索引规则开始。</span><span class="sxs-lookup"><span data-stu-id="e0ed1-253">Let's start with the rules for indexes.</span></span> <span data-ttu-id="e0ed1-254">请考虑数组 `sequence`。</span><span class="sxs-lookup"><span data-stu-id="e0ed1-254">Consider an array `sequence`.</span></span> <span data-ttu-id="e0ed1-255">`0` 索引与 `sequence[0]` 相同。</span><span class="sxs-lookup"><span data-stu-id="e0ed1-255">The `0` index is the same as `sequence[0]`.</span></span> <span data-ttu-id="e0ed1-256">`^0` 索引与 `sequence[sequence.Length]` 相同。</span><span class="sxs-lookup"><span data-stu-id="e0ed1-256">The `^0` index is the same as `sequence[sequence.Length]`.</span></span> <span data-ttu-id="e0ed1-257">请注意，`sequence[^0]` 不会引发异常，就像 `sequence[sequence.Length]` 一样。</span><span class="sxs-lookup"><span data-stu-id="e0ed1-257">Note that `sequence[^0]` does throw an exception, just as `sequence[sequence.Length]` does.</span></span> <span data-ttu-id="e0ed1-258">对于任何数字 `n`，索引 `^n` 与 `sequence.Length - n` 相同。</span><span class="sxs-lookup"><span data-stu-id="e0ed1-258">For any number `n`, the index `^n` is the same as `sequence.Length - n`.</span></span>

<span data-ttu-id="e0ed1-259">范围指定范围的开始和末尾。</span><span class="sxs-lookup"><span data-stu-id="e0ed1-259">A range specifies the *start* and *end* of a range.</span></span> <span data-ttu-id="e0ed1-260">范围是排除的，也就是说“末尾”不包含在范围内。</span><span class="sxs-lookup"><span data-stu-id="e0ed1-260">Ranges are exclusive, meaning the *end* is not included in the range.</span></span> <span data-ttu-id="e0ed1-261">范围 `[0..^0]` 表示整个范围，就像 `[0..sequence.Length]` 表示整个范围。</span><span class="sxs-lookup"><span data-stu-id="e0ed1-261">The range `[0..^0]` represents the entire range, just as `[0..sequence.Length]` represents the entire range.</span></span> 

<span data-ttu-id="e0ed1-262">请看以下几个示例。</span><span class="sxs-lookup"><span data-stu-id="e0ed1-262">Let's look at a few examples.</span></span> <span data-ttu-id="e0ed1-263">请考虑以下数组，用其顺数索引和倒数索引进行注释：</span><span class="sxs-lookup"><span data-stu-id="e0ed1-263">Consider the following array, annotated with its index from the start and from the end:</span></span>

```csharp
var words = new string[]
{
                // index from start    index from end
    "The",      // 0                   ^9
    "quick",    // 1                   ^8
    "brown",    // 2                   ^7
    "fox",      // 3                   ^6
    "jumped",   // 4                   ^5
    "over",     // 5                   ^4
    "the",      // 6                   ^3
    "lazy",     // 7                   ^2
    "dog"       // 8                   ^1
};              // 9 (or words.Length) ^0
```

<span data-ttu-id="e0ed1-264">可以使用 `^1` 索引检索最后一个词：</span><span class="sxs-lookup"><span data-stu-id="e0ed1-264">You can retrieve the last word with the `^1` index:</span></span>

```csharp
Console.WriteLine($"The last word is {words[^1]}");
// writes "dog"
```

<span data-ttu-id="e0ed1-265">以下代码创建了一个包含单词“quick”、“brown”和“fox”的子范围。</span><span class="sxs-lookup"><span data-stu-id="e0ed1-265">The following code creates a subrange with the words "quick", "brown", and "fox".</span></span> <span data-ttu-id="e0ed1-266">它包括 `words[1]` 到 `words[3]`。</span><span class="sxs-lookup"><span data-stu-id="e0ed1-266">It includes `words[1]` through `words[3]`.</span></span> <span data-ttu-id="e0ed1-267">元素 `words[4]` 不在此范围内。</span><span class="sxs-lookup"><span data-stu-id="e0ed1-267">The element `words[4]` is not in the range.</span></span>

```csharp
var quickBrownFox = words[1..4];
```

<span data-ttu-id="e0ed1-268">以下代码使用“lazy”和“dog”创建一个子范围。</span><span class="sxs-lookup"><span data-stu-id="e0ed1-268">The following code creates a subrange with "lazy" and "dog".</span></span> <span data-ttu-id="e0ed1-269">它包括 `words[^2]` 和 `words[^1]`。</span><span class="sxs-lookup"><span data-stu-id="e0ed1-269">It includes `words[^2]` and `words[^1]`.</span></span> <span data-ttu-id="e0ed1-270">不包括结束索引 `words[^0]`：</span><span class="sxs-lookup"><span data-stu-id="e0ed1-270">The end index `words[^0]` is not included:</span></span>

```csharp
var lazyDog = words[^2..^0];
```

<span data-ttu-id="e0ed1-271">下面的示例为开始和/或结束创建了开放范围：</span><span class="sxs-lookup"><span data-stu-id="e0ed1-271">The following examples create ranges that are open ended for the start, end, or both:</span></span>

```csharp
var allWords = words[..]; // contains "The" through "dog".
var firstPhrase = words[..4]; // contains "The" through "fox"
var lastPhrase = words[6..]; // contains "the, "lazy" and "dog"
```

<span data-ttu-id="e0ed1-272">此外可以将范围声明为变量：</span><span class="sxs-lookup"><span data-stu-id="e0ed1-272">You can also declare ranges as variables:</span></span>

```csharp
Range phrase = 1..4;
```

<span data-ttu-id="e0ed1-273">然后可以在 `[` 和 `]` 字符中使用该范围：</span><span class="sxs-lookup"><span data-stu-id="e0ed1-273">The range can then be used inside the `[` and `]` characters:</span></span>

```csharp
var text = words[phrase];
```

<span data-ttu-id="e0ed1-274">可在有关[索引和范围](../tutorials/ranges-indexes.md)的教程中详细了解索引和范围。</span><span class="sxs-lookup"><span data-stu-id="e0ed1-274">You can explore more about indices and ranges in the tutorial on [indices and ranges](../tutorials/ranges-indexes.md).</span></span>
