---
title: 使用索引和范围探索数据范围
description: 本高级教程教你使用索引和范围来探索数据，以检查顺序数据集的切片。
ms.date: 09/20/2019
ms.technology: csharp-fundamentals
ms.custom: mvc
ms.openlocfilehash: 3d4c022ff8d6e7f260632e34d6f28277014c85c8
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/25/2019
ms.locfileid: "75345623"
---
# <a name="indices-and-ranges"></a><span data-ttu-id="65fb8-103">索引和范围</span><span class="sxs-lookup"><span data-stu-id="65fb8-103">Indices and ranges</span></span>

<span data-ttu-id="65fb8-104">范围和索引为访问序列中的单个元素或范围提供了简洁的语法。</span><span class="sxs-lookup"><span data-stu-id="65fb8-104">Ranges and indices provide a succinct syntax for accessing single elements or ranges in a sequence.</span></span>

<span data-ttu-id="65fb8-105">在本教程中，你将了解：</span><span class="sxs-lookup"><span data-stu-id="65fb8-105">In this tutorial, you'll learn how to:</span></span>

> [!div class="checklist"]
>
> - <span data-ttu-id="65fb8-106">对某个序列中的范围使用该语法。</span><span class="sxs-lookup"><span data-stu-id="65fb8-106">Use the syntax for ranges in a sequence.</span></span>
> - <span data-ttu-id="65fb8-107">了解每个序列开头和末尾的设计决策。</span><span class="sxs-lookup"><span data-stu-id="65fb8-107">Understand the design decisions for the start and end of each sequence.</span></span>
> - <span data-ttu-id="65fb8-108">了解 <xref:System.Index> 和 <xref:System.Range> 类型的应用场景。</span><span class="sxs-lookup"><span data-stu-id="65fb8-108">Learn scenarios for the <xref:System.Index> and <xref:System.Range> types.</span></span>

## <a name="language-support-for-indices-and-ranges"></a><span data-ttu-id="65fb8-109">对索引和范围的语言支持</span><span class="sxs-lookup"><span data-stu-id="65fb8-109">Language support for indices and ranges</span></span>

<span data-ttu-id="65fb8-110">此语言支持依赖于两个新类型和两个新运算符：</span><span class="sxs-lookup"><span data-stu-id="65fb8-110">This language support relies on two new types and two new operators:</span></span>

- <span data-ttu-id="65fb8-111"><xref:System.Index?displayProperty=nameWithType> 表示一个序列索引。</span><span class="sxs-lookup"><span data-stu-id="65fb8-111"><xref:System.Index?displayProperty=nameWithType> represents an index into a sequence.</span></span>
- <span data-ttu-id="65fb8-112">来自末尾运算符 `^` 的索引，指定一个索引与序列末尾相关。</span><span class="sxs-lookup"><span data-stu-id="65fb8-112">The index from end operator `^`, which specifies that an index is relative to the end of a sequence.</span></span>
- <span data-ttu-id="65fb8-113"><xref:System.Range?displayProperty=nameWithType> 表示序列的子范围。</span><span class="sxs-lookup"><span data-stu-id="65fb8-113"><xref:System.Range?displayProperty=nameWithType> represents a sub range of a sequence.</span></span>
- <span data-ttu-id="65fb8-114">范围运算符 `..`，用于指定范围的开始和末尾，就像操作数一样。</span><span class="sxs-lookup"><span data-stu-id="65fb8-114">The range operator `..`, which specifies the start and end of a range as its operands.</span></span>

<span data-ttu-id="65fb8-115">让我们从索引规则开始。</span><span class="sxs-lookup"><span data-stu-id="65fb8-115">Let's start with the rules for indices.</span></span> <span data-ttu-id="65fb8-116">请考虑数组 `sequence`。</span><span class="sxs-lookup"><span data-stu-id="65fb8-116">Consider an array `sequence`.</span></span> <span data-ttu-id="65fb8-117">`0` 索引与 `sequence[0]` 相同。</span><span class="sxs-lookup"><span data-stu-id="65fb8-117">The `0` index is the same as `sequence[0]`.</span></span> <span data-ttu-id="65fb8-118">`^0` 索引与 `sequence[sequence.Length]` 相同。</span><span class="sxs-lookup"><span data-stu-id="65fb8-118">The `^0` index is the same as `sequence[sequence.Length]`.</span></span> <span data-ttu-id="65fb8-119">请注意，`sequence[^0]` 不会引发异常，就像 `sequence[sequence.Length]` 一样。</span><span class="sxs-lookup"><span data-stu-id="65fb8-119">Note that `sequence[^0]` does throw an exception, just as `sequence[sequence.Length]` does.</span></span> <span data-ttu-id="65fb8-120">对于任何数字 `n`，索引 `^n` 与 `sequence[sequence.Length - n]` 相同。</span><span class="sxs-lookup"><span data-stu-id="65fb8-120">For any number `n`, the index `^n` is the same as `sequence[sequence.Length - n]`.</span></span>

```csharp
string[] words = new string[]
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

<span data-ttu-id="65fb8-121">可以使用 `^1` 索引检索最后一个词。</span><span class="sxs-lookup"><span data-stu-id="65fb8-121">You can retrieve the last word with the `^1` index.</span></span> <span data-ttu-id="65fb8-122">在初始化下面添加以下代码：</span><span class="sxs-lookup"><span data-stu-id="65fb8-122">Add the following code below the initialization:</span></span>

[!code-csharp[LastIndex](~/samples/csharp/tutorials/RangesIndexes/IndicesAndRanges.cs#IndicesAndRanges_LastIndex)]

<span data-ttu-id="65fb8-123">范围指定范围的开始和末尾   。</span><span class="sxs-lookup"><span data-stu-id="65fb8-123">A range specifies the *start* and *end* of a range.</span></span> <span data-ttu-id="65fb8-124">范围是排除的，也就是说“末尾”不包含在范围内  。</span><span class="sxs-lookup"><span data-stu-id="65fb8-124">Ranges are exclusive, meaning the *end* is not included in the range.</span></span> <span data-ttu-id="65fb8-125">范围 `[0..^0]` 表示整个范围，就像 `[0..sequence.Length]` 表示整个范围。</span><span class="sxs-lookup"><span data-stu-id="65fb8-125">The range `[0..^0]` represents the entire range, just as `[0..sequence.Length]` represents the entire range.</span></span> 

<span data-ttu-id="65fb8-126">以下代码创建了一个包含单词“quick”、“brown”和“fox”的子范围。</span><span class="sxs-lookup"><span data-stu-id="65fb8-126">The following code creates a subrange with the words "quick", "brown", and "fox".</span></span> <span data-ttu-id="65fb8-127">它包括 `words[1]` 到 `words[3]`。</span><span class="sxs-lookup"><span data-stu-id="65fb8-127">It includes `words[1]` through `words[3]`.</span></span> <span data-ttu-id="65fb8-128">元素 `words[4]` 不在该范围内。</span><span class="sxs-lookup"><span data-stu-id="65fb8-128">The element `words[4]` isn't in the range.</span></span> <span data-ttu-id="65fb8-129">将以下代码添加到同一方法中。</span><span class="sxs-lookup"><span data-stu-id="65fb8-129">Add the following code to the same method.</span></span> <span data-ttu-id="65fb8-130">将其复制并粘贴到交互式窗口的底部。</span><span class="sxs-lookup"><span data-stu-id="65fb8-130">Copy and paste it at the bottom of the interactive window.</span></span>

[!code-csharp[Range](~/samples/csharp/tutorials/RangesIndexes/IndicesAndRanges.cs#IndicesAndRanges_Range)]

<span data-ttu-id="65fb8-131">以下代码使用“lazy”和“dog”创建一个子范围。</span><span class="sxs-lookup"><span data-stu-id="65fb8-131">The following code creates a subrange with "lazy" and "dog".</span></span> <span data-ttu-id="65fb8-132">它包括 `words[^2]` 和 `words[^1]`。</span><span class="sxs-lookup"><span data-stu-id="65fb8-132">It includes `words[^2]` and `words[^1]`.</span></span> <span data-ttu-id="65fb8-133">结束索引 `words[^0]` 不包括在内。</span><span class="sxs-lookup"><span data-stu-id="65fb8-133">The end index `words[^0]` isn't included.</span></span> <span data-ttu-id="65fb8-134">同样添加以下代码：</span><span class="sxs-lookup"><span data-stu-id="65fb8-134">Add the following code as well:</span></span>

[!code-csharp[LastRange](~/samples/csharp/tutorials/RangesIndexes/IndicesAndRanges.cs#IndicesAndRanges_LastRange)]

<span data-ttu-id="65fb8-135">下面的示例为开始和/或结束创建了开放范围：</span><span class="sxs-lookup"><span data-stu-id="65fb8-135">The following examples create ranges that are open ended for the start, end, or both:</span></span>

[!code-csharp[PartialRange](~/samples/csharp/tutorials/RangesIndexes/IndicesAndRanges.cs#IndicesAndRanges_PartialRanges)]

<span data-ttu-id="65fb8-136">还可以将范围或索引声明为变量。</span><span class="sxs-lookup"><span data-stu-id="65fb8-136">You can also declare ranges or indices as variables.</span></span> <span data-ttu-id="65fb8-137">然后可以在 `[` 和 `]` 字符中使用该变量：</span><span class="sxs-lookup"><span data-stu-id="65fb8-137">The variable can then be used inside the `[` and `]` characters:</span></span>

[!code-csharp[IndexRangeTypes](~/samples/csharp/tutorials/RangesIndexes/IndicesAndRanges.cs#IndicesAndRanges_RangeIndexTypes)]

<span data-ttu-id="65fb8-138">下面的示例展示了使用这些选项的多种原因。</span><span class="sxs-lookup"><span data-stu-id="65fb8-138">The following sample shows many of the reasons for those choices.</span></span> <span data-ttu-id="65fb8-139">请修改 `x`、`y` 和 `z` 以尝试不同的组合。</span><span class="sxs-lookup"><span data-stu-id="65fb8-139">Modify `x`, `y`, and `z` to try different combinations.</span></span> <span data-ttu-id="65fb8-140">在进行实验时，请使用 `x` 小于 `y`且 `y` 小于 `z` 的有效组合值。</span><span class="sxs-lookup"><span data-stu-id="65fb8-140">When you experiment, use values where `x` is less than `y`, and `y` is less than `z` for valid combinations.</span></span> <span data-ttu-id="65fb8-141">在新方法中添加以下代码。</span><span class="sxs-lookup"><span data-stu-id="65fb8-141">Add the following code in a new method.</span></span> <span data-ttu-id="65fb8-142">尝试不同的组合：</span><span class="sxs-lookup"><span data-stu-id="65fb8-142">Try different combinations:</span></span>

[!code-csharp[SemanticsExamples](~/samples/csharp/tutorials/RangesIndexes/IndicesAndRanges.cs#IndicesAndRanges_Semantics)]

## <a name="type-support-for-indices-and-ranges"></a><span data-ttu-id="65fb8-143">索引和范围的类型支持</span><span class="sxs-lookup"><span data-stu-id="65fb8-143">Type support for indices and ranges</span></span>

<span data-ttu-id="65fb8-144">索引和范围提供清晰、简洁的语法来访问序列中的单个元素或元素的子范围。</span><span class="sxs-lookup"><span data-stu-id="65fb8-144">Indexes and ranges provide clear, concise syntax to access a single element or a sub-range of elements in a sequence.</span></span> <span data-ttu-id="65fb8-145">索引表达式通常返回序列元素的类型。</span><span class="sxs-lookup"><span data-stu-id="65fb8-145">An index expression typically returns the type of the elements of a sequence.</span></span> <span data-ttu-id="65fb8-146">范围表达式通常返回与源序列相同的序列类型。</span><span class="sxs-lookup"><span data-stu-id="65fb8-146">A range expression typically returns the same sequence type as the source sequence.</span></span>

<span data-ttu-id="65fb8-147">若类型提供带 <xref:System.Index> 或 [ 参数的](../programming-guide/indexers/index.md)索引器<xref:System.Range>，则它将分别显式支持索引或范围。</span><span class="sxs-lookup"><span data-stu-id="65fb8-147">If a type provides an [indexer](../programming-guide/indexers/index.md) with an <xref:System.Index> or <xref:System.Range> parameter, it explicitly supports indices or ranges respectively.</span></span> <span data-ttu-id="65fb8-148">当类型提供采用单个 <xref:System.Range> 参数的索引器时，可能会选择返回不同的序列类型，如 <xref:System.Span%601?displayProperty=nameWithType>。</span><span class="sxs-lookup"><span data-stu-id="65fb8-148">When the type provides an indexer that takes a single <xref:System.Range> parameter, it may choose to return a different sequence type, such as <xref:System.Span%601?displayProperty=nameWithType>.</span></span>

<span data-ttu-id="65fb8-149">若类型包含名称为 `Length` 或 `Count` 的属性，属性有可访问的 Getter 并且其返回类型为 `int`，则此类型为可计数类型。 </span><span class="sxs-lookup"><span data-stu-id="65fb8-149">A type is **countable** if it has a property named `Length` or `Count` with an accessible getter and a return type of `int`.</span></span> <span data-ttu-id="65fb8-150">不显式支持索引或范围的可计数类型可能为它们提供隐式支持。</span><span class="sxs-lookup"><span data-stu-id="65fb8-150">A countable type that doesn't explicitly support indices or ranges may provide an implicit support for them.</span></span> <span data-ttu-id="65fb8-151">有关详细信息，请参阅[功能建议说明](~/_csharplang/proposals/csharp-8.0/ranges.md)的[隐式索引支持](~/_csharplang/proposals/csharp-8.0/ranges.md#implicit-index-support)和[隐式范围支持](~/_csharplang/proposals/csharp-8.0/ranges.md#implicit-range-support)部分。</span><span class="sxs-lookup"><span data-stu-id="65fb8-151">For more information, see the [Implicit Index support](~/_csharplang/proposals/csharp-8.0/ranges.md#implicit-index-support) and [Implicit Range support](~/_csharplang/proposals/csharp-8.0/ranges.md#implicit-range-support) sections of the [feature proposal note](~/_csharplang/proposals/csharp-8.0/ranges.md).</span></span> <span data-ttu-id="65fb8-152">使用隐式范围支持的范围将返回与源序列相同的序列类型。</span><span class="sxs-lookup"><span data-stu-id="65fb8-152">Ranges using implicit range support return the same sequence type as the source sequence.</span></span>

<span data-ttu-id="65fb8-153">例如，以下 .NET 类型同时支持索引和范围：<xref:System.Array>、<xref:System.String>、<xref:System.Span%601> 和 <xref:System.ReadOnlySpan%601>。</span><span class="sxs-lookup"><span data-stu-id="65fb8-153">For example, the following .NET types support both indices and ranges: <xref:System.Array>, <xref:System.String>, <xref:System.Span%601>, and <xref:System.ReadOnlySpan%601>.</span></span> <span data-ttu-id="65fb8-154"><xref:System.Collections.Generic.List%601> 支持索引，但不支持范围。</span><span class="sxs-lookup"><span data-stu-id="65fb8-154">The <xref:System.Collections.Generic.List%601> supports indices but doesn't support ranges.</span></span>

## <a name="scenarios-for-indices-and-ranges"></a><span data-ttu-id="65fb8-155">索引和范围的应用场景</span><span class="sxs-lookup"><span data-stu-id="65fb8-155">Scenarios for indices and ranges</span></span>

<span data-ttu-id="65fb8-156">如果要对整个序列的子范围执行某些分析，通常会使用范围和索引。</span><span class="sxs-lookup"><span data-stu-id="65fb8-156">You'll often use ranges and indices when you want to perform some analysis on subrange of an entire sequence.</span></span> <span data-ttu-id="65fb8-157">在准确读取所涉及的子范围这一方面，新语法更清晰。</span><span class="sxs-lookup"><span data-stu-id="65fb8-157">The new syntax is clearer in reading exactly what subrange is involved.</span></span> <span data-ttu-id="65fb8-158">本地函数 `MovingAverage` 以 <xref:System.Range> 为参数。</span><span class="sxs-lookup"><span data-stu-id="65fb8-158">The local function `MovingAverage` takes a <xref:System.Range> as its argument.</span></span> <span data-ttu-id="65fb8-159">然后，该方法在计算最小值、最大值和平均值时仅枚举该范围。</span><span class="sxs-lookup"><span data-stu-id="65fb8-159">The method then enumerates just that range when calculating the min, max, and average.</span></span> <span data-ttu-id="65fb8-160">在项目中尝试以下代码：</span><span class="sxs-lookup"><span data-stu-id="65fb8-160">Try the following code in your project:</span></span>

[!code-csharp[MovingAverages](~/samples/csharp/tutorials/RangesIndexes/IndicesAndRanges.cs#IndicesAndRanges_MovingAverage)]

<span data-ttu-id="65fb8-161">可以从 [dotnet/samples](https://github.com/dotnet/samples/tree/master/csharp/tutorials/RangesIndexes) 存储库下载完整代码。</span><span class="sxs-lookup"><span data-stu-id="65fb8-161">You can download the completed code from the [dotnet/samples](https://github.com/dotnet/samples/tree/master/csharp/tutorials/RangesIndexes) repository.</span></span>
