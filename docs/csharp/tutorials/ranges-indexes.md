---
title: 使用索引和范围探索数据范围
description: 本高级教程教你使用索引和范围来探索数据，以检查顺序数据集的切片。
ms.date: 04/19/2019
ms.custom: mvc
ms.openlocfilehash: 64fae4581e265d4f70b8356d5c651b4fdaca3fe9
ms.sourcegitcommit: dd3b897feb5c4ac39732bb165848e37a344b0765
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/25/2019
ms.locfileid: "64431492"
---
# <a name="indices-and-ranges"></a><span data-ttu-id="ea42c-103">索引和范围</span><span class="sxs-lookup"><span data-stu-id="ea42c-103">Indices and ranges</span></span>

<span data-ttu-id="ea42c-104">范围和索引为访问 <xref:System.Array>、<xref:System.Span%601> 或 <xref:System.ReadOnlySpan%601> 中的单个元素或范围提供了简洁的语法。</span><span class="sxs-lookup"><span data-stu-id="ea42c-104">Ranges and indices provide a succinct syntax for accessing single elements or ranges in an <xref:System.Array>, <xref:System.Span%601>, or <xref:System.ReadOnlySpan%601>.</span></span> <span data-ttu-id="ea42c-105">这些功能启用更简洁清晰的语法来访问某个序列中的单个元素或元素范围。</span><span class="sxs-lookup"><span data-stu-id="ea42c-105">These features enable more concise, clear syntax to access single elements or ranges of elements in a sequence.</span></span>

<span data-ttu-id="ea42c-106">在本教程中，你将了解：</span><span class="sxs-lookup"><span data-stu-id="ea42c-106">In this tutorial, you'll learn how to:</span></span>

> [!div class="checklist"]
> * <span data-ttu-id="ea42c-107">对某个序列中的范围使用该语法。</span><span class="sxs-lookup"><span data-stu-id="ea42c-107">Use the syntax for ranges in a sequence.</span></span>
> * <span data-ttu-id="ea42c-108">了解每个序列开头和末尾的设计决策。</span><span class="sxs-lookup"><span data-stu-id="ea42c-108">Understand the design decisions for the start and end of each sequence.</span></span>
> * <span data-ttu-id="ea42c-109">了解 <xref:System.Index> 和 <xref:System.Range> 类型的应用场景。</span><span class="sxs-lookup"><span data-stu-id="ea42c-109">Learn scenarios for the <xref:System.Index> and <xref:System.Range> types.</span></span>

## <a name="language-support-for-indices-and-ranges"></a><span data-ttu-id="ea42c-110">对索引和范围的语言支持</span><span class="sxs-lookup"><span data-stu-id="ea42c-110">Language support for indices and ranges</span></span>

<span data-ttu-id="ea42c-111">通过在索引前面使用 `^` 字符，可以**从末尾**指定索引。</span><span class="sxs-lookup"><span data-stu-id="ea42c-111">You can specify an index **from the end** using the `^` character before the index.</span></span> <span data-ttu-id="ea42c-112">从末尾编制索引将从 `0..^0` 指定整个范围的规则开始。</span><span class="sxs-lookup"><span data-stu-id="ea42c-112">Indexing from the end starts from the rule that `0..^0` specifies the entire range.</span></span> <span data-ttu-id="ea42c-113">若要枚举整个数组，请从*第一个元素*开始，一直到*最后一个元素之后*。</span><span class="sxs-lookup"><span data-stu-id="ea42c-113">To enumerate an entire array, you start *at the first element*, and continue until you are *past the last element*.</span></span> <span data-ttu-id="ea42c-114">想想枚举器上 `MoveNext` 方法的行为：如果枚举到最后一个元素之后，它会返回 false。</span><span class="sxs-lookup"><span data-stu-id="ea42c-114">Think of the behavior of the `MoveNext` method on an enumerator: it returns false when the enumeration passes the last element.</span></span> <span data-ttu-id="ea42c-115">索引 `^0` 表示“结尾”、`array[array.Length]` 或最后一个元素后面的索引。</span><span class="sxs-lookup"><span data-stu-id="ea42c-115">The index `^0` means "the end", `array[array.Length]`, or the index that follows the last element.</span></span> <span data-ttu-id="ea42c-116">你熟悉表示元素“顺数第 2”的 `array[2]`。</span><span class="sxs-lookup"><span data-stu-id="ea42c-116">You are familiar with `array[2]` meaning the element "2 from the start".</span></span> <span data-ttu-id="ea42c-117">现在，`array[^2]` 意味着元素“倒数第 2”。</span><span class="sxs-lookup"><span data-stu-id="ea42c-117">Now, `array[^2]` means the element "2 from the end".</span></span> 

<span data-ttu-id="ea42c-118">可以使用范围运算符指定范围：`..`。</span><span class="sxs-lookup"><span data-stu-id="ea42c-118">You can specify a **range** with the **range operator**: `..`.</span></span> <span data-ttu-id="ea42c-119">例如，`0..^0` 指定数组的整个范围：从起始 0 开始，但不包括最后的 0。</span><span class="sxs-lookup"><span data-stu-id="ea42c-119">For example, `0..^0` specifies the entire range of the array: 0 from the start up to, but not including 0 from the end.</span></span> <span data-ttu-id="ea42c-120">两个操作数都可以使用“顺数”或“倒数”。</span><span class="sxs-lookup"><span data-stu-id="ea42c-120">Either operand may use "from the start" or "from the end".</span></span> <span data-ttu-id="ea42c-121">此外，可以省略其中一个操作数。</span><span class="sxs-lookup"><span data-stu-id="ea42c-121">Furthermore, either operand may be omitted.</span></span> <span data-ttu-id="ea42c-122">默认值为起始索引的 `0` 和结束索引的 `^0`。</span><span class="sxs-lookup"><span data-stu-id="ea42c-122">The defaults are `0` for the start index, and `^0` for the end index.</span></span>

```csharp-interactive
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

<span data-ttu-id="ea42c-123">每个元素的索引均强化了“顺数”和“倒数”的概念，且范围不包括结束范围。</span><span class="sxs-lookup"><span data-stu-id="ea42c-123">The index of each element reinforces the concept of "from the start", and "from the end", and that ranges are exclusive of the end of the range.</span></span> <span data-ttu-id="ea42c-124">整个数组的“start”是第一个元素。</span><span class="sxs-lookup"><span data-stu-id="ea42c-124">The "start" of the entire array is the first element.</span></span> <span data-ttu-id="ea42c-125">整个数组的“end”在最后一个元素之后。</span><span class="sxs-lookup"><span data-stu-id="ea42c-125">The "end" of the entire array is *past* the last element.</span></span>

<span data-ttu-id="ea42c-126">可以使用 `^1` 索引检索最后一个词。</span><span class="sxs-lookup"><span data-stu-id="ea42c-126">You can retrieve the last word with the `^1` index.</span></span> <span data-ttu-id="ea42c-127">在初始化下面添加以下代码：</span><span class="sxs-lookup"><span data-stu-id="ea42c-127">Add the following code below the initialization:</span></span>

[!code-csharp[LastIndex](~/samples/csharp/tutorials/RangesIndexes/IndicesAndRanges.cs#IndicesAndRanges_LastIndex)]

<span data-ttu-id="ea42c-128">以下代码创建了一个包含单词“quick”、“brown”和“fox”的子范围。</span><span class="sxs-lookup"><span data-stu-id="ea42c-128">The following code creates a subrange with the words "quick", "brown", and "fox".</span></span> <span data-ttu-id="ea42c-129">它包括 `words[1]` 到 `words[3]`。</span><span class="sxs-lookup"><span data-stu-id="ea42c-129">It includes `words[1]` through `words[3]`.</span></span> <span data-ttu-id="ea42c-130">元素 `words[4]` 不在该范围内。</span><span class="sxs-lookup"><span data-stu-id="ea42c-130">The element `words[4]` isn't in the range.</span></span> <span data-ttu-id="ea42c-131">将以下代码添加到同一方法中。</span><span class="sxs-lookup"><span data-stu-id="ea42c-131">Add the following code to the same method.</span></span> <span data-ttu-id="ea42c-132">将其复制并粘贴到交互式窗口的底部。</span><span class="sxs-lookup"><span data-stu-id="ea42c-132">Copy and paste it at the bottom of the interactive window.</span></span>

[!code-csharp[Range](~/samples/csharp/tutorials/RangesIndexes/IndicesAndRanges.cs#IndicesAndRanges_Range)]

<span data-ttu-id="ea42c-133">以下代码使用“lazy”和“dog”创建一个子范围。</span><span class="sxs-lookup"><span data-stu-id="ea42c-133">The following code creates a subrange with "lazy" and "dog".</span></span> <span data-ttu-id="ea42c-134">它包括 `words[^2]` 和 `words[^1]`。</span><span class="sxs-lookup"><span data-stu-id="ea42c-134">It includes `words[^2]` and `words[^1]`.</span></span> <span data-ttu-id="ea42c-135">结束索引 `words[^0]` 不包括在内。</span><span class="sxs-lookup"><span data-stu-id="ea42c-135">The end index `words[^0]` isn't included.</span></span> <span data-ttu-id="ea42c-136">同样添加以下代码：</span><span class="sxs-lookup"><span data-stu-id="ea42c-136">Add the following code as well:</span></span>

[!code-csharp[LastRange](~/samples/csharp/tutorials/RangesIndexes/IndicesAndRanges.cs#IndicesAndRanges_LastRange)]

<span data-ttu-id="ea42c-137">下面的示例为开始和/或结束创建了开放范围：</span><span class="sxs-lookup"><span data-stu-id="ea42c-137">The following examples create ranges that are open ended for the start, end, or both:</span></span>

[!code-csharp[PartialRange](~/samples/csharp/tutorials/RangesIndexes/IndicesAndRanges.cs#IndicesAndRanges_PartialRanges)]

<span data-ttu-id="ea42c-138">还可以将范围或索引声明为变量。</span><span class="sxs-lookup"><span data-stu-id="ea42c-138">You can also declare ranges or indices as variables.</span></span> <span data-ttu-id="ea42c-139">然后可以在 `[` 和 `]` 字符中使用该变量：</span><span class="sxs-lookup"><span data-stu-id="ea42c-139">The variable can then be used inside the `[` and `]` characters:</span></span>

[!code-csharp[IndexRangeTypes](~/samples/csharp/tutorials/RangesIndexes/IndicesAndRanges.cs#IndicesAndRanges_RangeIndexTypes)]

<span data-ttu-id="ea42c-140">前面的示例展示了两个需要详细说明的设计决策：</span><span class="sxs-lookup"><span data-stu-id="ea42c-140">The previous examples show two design decisions that require more explanation:</span></span>

- <span data-ttu-id="ea42c-141">范围具有*独占性*，这意味着最后一个索引处的元素不在范围内。</span><span class="sxs-lookup"><span data-stu-id="ea42c-141">Ranges are *exclusive*, meaning the element at the last index isn't in the range.</span></span>
- <span data-ttu-id="ea42c-142">索引 `^0` 是集合的*结尾*，而不是集合中的*最后一个元素*。</span><span class="sxs-lookup"><span data-stu-id="ea42c-142">The index `^0` is *the end* of the collection, not *the last element* in the collection.</span></span>

<span data-ttu-id="ea42c-143">下面的示例展示了使用这些选项的多种原因。</span><span class="sxs-lookup"><span data-stu-id="ea42c-143">The following sample shows many of the reasons for those choices.</span></span> <span data-ttu-id="ea42c-144">请修改 `x`、`y` 和 `z` 以尝试不同的组合。</span><span class="sxs-lookup"><span data-stu-id="ea42c-144">Modify `x`, `y`, and `z` to try different combinations.</span></span> <span data-ttu-id="ea42c-145">在进行实验时，请使用 `x` 小于 `y`且 `y` 小于 `z` 的有效组合值。</span><span class="sxs-lookup"><span data-stu-id="ea42c-145">When you experiment, use values where `x` is less than `y`, and `y` is less than `z` for valid combinations.</span></span> <span data-ttu-id="ea42c-146">在新方法中添加以下代码。</span><span class="sxs-lookup"><span data-stu-id="ea42c-146">Add the following code in a new method.</span></span> <span data-ttu-id="ea42c-147">尝试不同的组合：</span><span class="sxs-lookup"><span data-stu-id="ea42c-147">Try different combinations:</span></span>

[!code-csharp[SemanticsExamples](~/samples/csharp/tutorials/RangesIndexes/IndicesAndRanges.cs#IndicesAndRanges_Semantics)]

## <a name="scenarios-for-indices-and-ranges"></a><span data-ttu-id="ea42c-148">索引和范围的应用场景</span><span class="sxs-lookup"><span data-stu-id="ea42c-148">Scenarios for Indices and Ranges</span></span>

<span data-ttu-id="ea42c-149">如果要对整个序列的子范围执行某些分析，通常会使用范围和索引。</span><span class="sxs-lookup"><span data-stu-id="ea42c-149">You'll often use ranges and indices when you want to perform some analysis on subrange of an entire sequence.</span></span> <span data-ttu-id="ea42c-150">在准确读取所涉及的子范围这一方面，新语法更清晰。</span><span class="sxs-lookup"><span data-stu-id="ea42c-150">The new syntax is clearer in reading exactly what subrange is involved.</span></span> <span data-ttu-id="ea42c-151">本地函数 `MovingAverage` 以 <xref:System.Range> 为参数。</span><span class="sxs-lookup"><span data-stu-id="ea42c-151">The local function `MovingAverage` takes a <xref:System.Range> as its argument.</span></span> <span data-ttu-id="ea42c-152">然后，该方法在计算最小值、最大值和平均值时仅枚举该范围。</span><span class="sxs-lookup"><span data-stu-id="ea42c-152">The method then enumerates just that range when calculating the min, max, and average.</span></span> <span data-ttu-id="ea42c-153">在项目中尝试以下代码：</span><span class="sxs-lookup"><span data-stu-id="ea42c-153">Try the following code in your project:</span></span>

[!code-csharp[MovingAverages](~/samples/csharp/tutorials/RangesIndexes/IndicesAndRanges.cs#IndicesAndRanges_MovingAverage)]

<span data-ttu-id="ea42c-154">可以从 [dotnet/samples](https://github.com/dotnet/samples/tree/master/csharp/tutorials/RangesIndexes) 存储库下载完整代码。</span><span class="sxs-lookup"><span data-stu-id="ea42c-154">You can download the completed code from the [dotnet/samples](https://github.com/dotnet/samples/tree/master/csharp/tutorials/RangesIndexes) repository.</span></span>
