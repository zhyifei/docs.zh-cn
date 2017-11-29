---
title: "列表 (F#)"
description: "了解有关 F # 列表，相同类型的元素的有序的、 不可变序列。"
keywords: "visual f#, f#, 函数编程"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: a1a6075f-064d-4aee-8222-2b59ff16cc12
ms.openlocfilehash: 5802a5a1c48ad05c1765c4c0fa2e8a81a92dee8d
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="lists"></a><span data-ttu-id="19669-104">列表</span><span class="sxs-lookup"><span data-stu-id="19669-104">Lists</span></span>

> [!NOTE]
<span data-ttu-id="19669-105">本文中的 API 参考链接将转至 MSDN。</span><span class="sxs-lookup"><span data-stu-id="19669-105">The API reference links in this article will take you to MSDN.</span></span>  <span data-ttu-id="19669-106">Docs.microsoft.com API 参考尚未完成。</span><span class="sxs-lookup"><span data-stu-id="19669-106">The docs.microsoft.com API reference is not complete.</span></span>

<span data-ttu-id="19669-107">F# 中的列表是一个有序的、不可变的同类型元素系列。</span><span class="sxs-lookup"><span data-stu-id="19669-107">A list in F# is an ordered, immutable series of elements of the same type.</span></span> <span data-ttu-id="19669-108">若要执行对列表的基本操作，使用中的函数[列表模块](https://msdn.microsoft.com/library/a2264ba3-2d45-40dd-9040-4f7aa2ad9788)。</span><span class="sxs-lookup"><span data-stu-id="19669-108">To perform basic operations on lists, use the functions in the [List module](https://msdn.microsoft.com/library/a2264ba3-2d45-40dd-9040-4f7aa2ad9788).</span></span>


## <a name="creating-and-initializing-lists"></a><span data-ttu-id="19669-109">创建和初始化列表</span><span class="sxs-lookup"><span data-stu-id="19669-109">Creating and Initializing Lists</span></span>
<span data-ttu-id="19669-110">可以通过以下方式来定义列表：显式列出元素并用分号分隔各个元素，然后将这些元素用方括号括起来，如下面的代码行所示。</span><span class="sxs-lookup"><span data-stu-id="19669-110">You can define a list by explicitly listing out the elements, separated by semicolons and enclosed in square brackets, as shown in the following line of code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1301.fs)]

<span data-ttu-id="19669-111">也可以在各个元素之间插入换行符，在这种情况下，分号是可选的。</span><span class="sxs-lookup"><span data-stu-id="19669-111">You can also put line breaks between elements, in which case the semicolons are optional.</span></span> <span data-ttu-id="19669-112">当元素初始化表达式较长或你希望为每个元素包含一个注释时，后一种语法会产生可读性更高的代码。</span><span class="sxs-lookup"><span data-stu-id="19669-112">The latter syntax can result in more readable code when the element initialization expressions are longer, or when you want to include a comment for each element.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet13011.fs)]

<span data-ttu-id="19669-113">通常，所有列表元素都必须是同一类型。</span><span class="sxs-lookup"><span data-stu-id="19669-113">Normally, all list elements must be the same type.</span></span> <span data-ttu-id="19669-114">但存在一种例外情况，即其元素被指定为基类型的列表中包含的元素可以是派生类型。</span><span class="sxs-lookup"><span data-stu-id="19669-114">An exception is that a list in which the elements are specified to be a base type can have elements that are derived types.</span></span> <span data-ttu-id="19669-115">由于 `Button` 和 `CheckBox` 都派生自 `Control`，因此以下内容是可接受的。</span><span class="sxs-lookup"><span data-stu-id="19669-115">Thus the following is acceptable, because both `Button` and `CheckBox` derive from `Control`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet13012.fs)]

<span data-ttu-id="19669-116">也可以使用由范围分隔符 (`..`) 分隔的整数所指示的范围来定义列表元素，如以下代码所示。</span><span class="sxs-lookup"><span data-stu-id="19669-116">You can also define list elements by using a range indicated by integers separated by the range operator (`..`), as shown in the following code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1302.fs)]

<span data-ttu-id="19669-117">可使用一对中间不包含任何内容的方括号来指定空列表。</span><span class="sxs-lookup"><span data-stu-id="19669-117">An empty list is specified by a pair of square brackets with nothing in between them.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1304.fs)]

<span data-ttu-id="19669-118">也可以使用序列表达式来创建列表。</span><span class="sxs-lookup"><span data-stu-id="19669-118">You can also use a sequence expression to create a list.</span></span> <span data-ttu-id="19669-119">请参阅[序列表达式](sequences.md#sequence-expressions)有关详细信息。</span><span class="sxs-lookup"><span data-stu-id="19669-119">See [Sequence Expressions](sequences.md#sequence-expressions) for more information.</span></span> <span data-ttu-id="19669-120">例如，以下代码创建一个从 1 到 10 的整数的平方值的列表。</span><span class="sxs-lookup"><span data-stu-id="19669-120">For example, the following code creates a list of squares of integers from 1 to 10.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1303.fs)]

## <a name="operators-for-working-with-lists"></a><span data-ttu-id="19669-121">用于处理列表的运算符</span><span class="sxs-lookup"><span data-stu-id="19669-121">Operators for Working with Lists</span></span>
<span data-ttu-id="19669-122">可以使用 `::` (cons) 运算符将元素附加到列表中。</span><span class="sxs-lookup"><span data-stu-id="19669-122">You can attach elements to a list by using the `::` (cons) operator.</span></span> <span data-ttu-id="19669-123">如果 `list1` 为 `[2; 3; 4]`，则以下代码会将 `list2` 创建为 `[100; 2; 3; 4]`。</span><span class="sxs-lookup"><span data-stu-id="19669-123">If `list1` is `[2; 3; 4]`, the following code creates `list2` as `[100; 2; 3; 4]`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1305.fs)]

<span data-ttu-id="19669-124">可以使用 `@` 运算符来串联具有可兼容类型的列表，如以下代码所示。</span><span class="sxs-lookup"><span data-stu-id="19669-124">You can concatenate lists that have compatible types by using the `@` operator, as in the following code.</span></span> <span data-ttu-id="19669-125">如果 `list1` 为 `[2; 3; 4]`，且 `list2` 为 `[100; 2; 3; 4 ]`，则此代码会将 `list3` 创建为 `[2; 3; 4; 100; 2; 3; 4]`。</span><span class="sxs-lookup"><span data-stu-id="19669-125">If `list1` is `[2; 3; 4]` and `list2` is `[100; 2; 3; 4 ]`, this code creates `list3` as `[2; 3; 4; 100; 2; 3; 4]`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1306.fs)]

<span data-ttu-id="19669-126">中提供了用于对列表执行操作的函数[列表模块](https://msdn.microsoft.com/library/a2264ba3-2d45-40dd-9040-4f7aa2ad9788)。</span><span class="sxs-lookup"><span data-stu-id="19669-126">Functions for performing operations on lists are available in the [List module](https://msdn.microsoft.com/library/a2264ba3-2d45-40dd-9040-4f7aa2ad9788).</span></span>

<span data-ttu-id="19669-127">由于 F# 中的列表是不可变的，因此任何修改操作都会生成新列表，而不是修改现有列表。</span><span class="sxs-lookup"><span data-stu-id="19669-127">Because lists in F# are immutable, any modifying operations generate new lists instead of modifying existing lists.</span></span>

<span data-ttu-id="19669-128">F # 中的列表作为单独链接的列表，这意味着访问仅列表头中的操作是 o （1），实现和元素访问复杂度为 O (*n*)。</span><span class="sxs-lookup"><span data-stu-id="19669-128">Lists in F# are implemented as singly linked lists, which means that operations that access only the head of the list are O(1), and element access is O(*n*).</span></span>


## <a name="properties"></a><span data-ttu-id="19669-129">属性</span><span class="sxs-lookup"><span data-stu-id="19669-129">Properties</span></span>
<span data-ttu-id="19669-130">列表类型支持以下属性：</span><span class="sxs-lookup"><span data-stu-id="19669-130">The list type supports the following properties:</span></span>

|<span data-ttu-id="19669-131">属性</span><span class="sxs-lookup"><span data-stu-id="19669-131">Property</span></span>|<span data-ttu-id="19669-132">类型</span><span class="sxs-lookup"><span data-stu-id="19669-132">Type</span></span>|<span data-ttu-id="19669-133">描述</span><span class="sxs-lookup"><span data-stu-id="19669-133">Description</span></span>|
|--------|----|-----------|
|[<span data-ttu-id="19669-134">Head</span><span class="sxs-lookup"><span data-stu-id="19669-134">Head</span></span>](https://msdn.microsoft.com/library/5f9414fd-6bdb-470a-8b72-40016db30740)|`'T`|<span data-ttu-id="19669-135">第一个元素。</span><span class="sxs-lookup"><span data-stu-id="19669-135">The first element.</span></span>|
|[<span data-ttu-id="19669-136">为空</span><span class="sxs-lookup"><span data-stu-id="19669-136">Empty</span></span>](https://msdn.microsoft.com/library/44406ecb-1918-4d32-b32a-ca1f69840386)|`'T list`|<span data-ttu-id="19669-137">返回适合类型的空列表的静态属性。</span><span class="sxs-lookup"><span data-stu-id="19669-137">A static property that returns an empty list of the appropriate type.</span></span>|
|[<span data-ttu-id="19669-138">IsEmpty</span><span class="sxs-lookup"><span data-stu-id="19669-138">IsEmpty</span></span>](https://msdn.microsoft.com/library/3ba087b2-2fc2-406d-b10a-cff6a19322da)|`bool`|<span data-ttu-id="19669-139">如果列表不包含任何元素，则为 `true`。</span><span class="sxs-lookup"><span data-stu-id="19669-139">`true` if the list has no elements.</span></span>|
|[<span data-ttu-id="19669-140">Item</span><span class="sxs-lookup"><span data-stu-id="19669-140">Item</span></span>](https://msdn.microsoft.com/library/bdb2553a-0e54-4ff8-baed-ab1aac8f5dae)|`'T`|<span data-ttu-id="19669-141">位于指定索引处（从零开始）的元素。</span><span class="sxs-lookup"><span data-stu-id="19669-141">The element at the specified index (zero-based).</span></span>|
|[<span data-ttu-id="19669-142">长度</span><span class="sxs-lookup"><span data-stu-id="19669-142">Length</span></span>](https://msdn.microsoft.com/library/25f715c8-9daa-4c4d-a6c7-26772f9dab4d)|`int`|<span data-ttu-id="19669-143">元素数量。</span><span class="sxs-lookup"><span data-stu-id="19669-143">The number of elements.</span></span>|
|[<span data-ttu-id="19669-144">结尾</span><span class="sxs-lookup"><span data-stu-id="19669-144">Tail</span></span>](https://msdn.microsoft.com/library/2a6f8eb9-dc32-41aa-8b62-2baffaface91)|`'T list`|<span data-ttu-id="19669-145">不带第一个元素的列表。</span><span class="sxs-lookup"><span data-stu-id="19669-145">The list without the first element.</span></span>|
<span data-ttu-id="19669-146">以下是一些使用这些属性的示例。</span><span class="sxs-lookup"><span data-stu-id="19669-146">Following are some examples of using these properties.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1307.fs)]
    
## <a name="using-lists"></a><span data-ttu-id="19669-147">使用列表</span><span class="sxs-lookup"><span data-stu-id="19669-147">Using Lists</span></span>
<span data-ttu-id="19669-148">利用列表进行编程，你可以使用少量代码来执行复杂的操作。</span><span class="sxs-lookup"><span data-stu-id="19669-148">Programming with lists enables you to perform complex operations with a small amount of code.</span></span> <span data-ttu-id="19669-149">本节介绍针对列表的常见操作，这些操作对于函数编程很重要。</span><span class="sxs-lookup"><span data-stu-id="19669-149">This section describes common operations on lists that are important to functional programming.</span></span>


### <a name="recursion-with-lists"></a><span data-ttu-id="19669-150">利用列表进行递归</span><span class="sxs-lookup"><span data-stu-id="19669-150">Recursion with Lists</span></span>
<span data-ttu-id="19669-151">列表特别适合于递归编程技术。</span><span class="sxs-lookup"><span data-stu-id="19669-151">Lists are uniquely suited to recursive programming techniques.</span></span> <span data-ttu-id="19669-152">假设要对列表的每个元素执行某个操作。</span><span class="sxs-lookup"><span data-stu-id="19669-152">Consider an operation that must be performed on every element of a list.</span></span> <span data-ttu-id="19669-153">可以通过以下方式来实现递归：对列表头执行操作，然后再次将列表尾（一个更小的列表，它由不带第一个元素的原始列表组成）传递回下一级递归。</span><span class="sxs-lookup"><span data-stu-id="19669-153">You can do this recursively by operating on the head of the list and then passing the tail of the list, which is a smaller list that consists of the original list without the first element, back again to the next level of recursion.</span></span>

<span data-ttu-id="19669-154">若要编写此类递归函数，可在模式匹配中使用 cons 运算符 (`::`)，以便将列表头与列表尾分离。</span><span class="sxs-lookup"><span data-stu-id="19669-154">To write such a recursive function, you use the cons operator (`::`) in pattern matching, which enables you to separate the head of a list from the tail.</span></span>

<span data-ttu-id="19669-155">以下代码示例显示了如何使用模式匹配来实现对列表执行操作的递归函数。</span><span class="sxs-lookup"><span data-stu-id="19669-155">The following code example shows how to use pattern matching to implement a recursive function that performs operations on a list.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet13071.fs)]

<span data-ttu-id="19669-156">上面的代码非常适用于小型列表，但对于大型列表，它可能会溢出堆栈。</span><span class="sxs-lookup"><span data-stu-id="19669-156">The previous code works well for small lists, but for larger lists, it could overflow the stack.</span></span> <span data-ttu-id="19669-157">以下代码通过使用累加器参数（一种用于处理递归函数的标准技术）对该代码进行了改进。</span><span class="sxs-lookup"><span data-stu-id="19669-157">The following code improves on this code by using an accumulator argument, a standard technique for working with recursive functions.</span></span> <span data-ttu-id="19669-158">使用累加器参数会使函数进行尾递归，这将节省堆栈空间。</span><span class="sxs-lookup"><span data-stu-id="19669-158">The use of the accumulator argument makes the function tail recursive, which saves stack space.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet13072.fs)]

<span data-ttu-id="19669-159">函数 `RemoveAllMultiples` 是一个递归函数，它采用两个列表。</span><span class="sxs-lookup"><span data-stu-id="19669-159">The function `RemoveAllMultiples` is a recursive function that takes two lists.</span></span> <span data-ttu-id="19669-160">第一个列表包含一些数字（将移除这些数字的倍数），第二个列表是要从中移除这些倍数数字的列表。</span><span class="sxs-lookup"><span data-stu-id="19669-160">The first list contains the numbers whose multiples will be removed, and the second list is the list from which to remove the numbers.</span></span> <span data-ttu-id="19669-161">以下示例中的代码使用此递归函数来消除列表中的所有非质数，结果是得到一个质数列表。</span><span class="sxs-lookup"><span data-stu-id="19669-161">The code in the following example uses this recursive function to eliminate all the non-prime numbers from a list, leaving a list of prime numbers as the result.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1308.fs)]

<span data-ttu-id="19669-162">输出如下所示：</span><span class="sxs-lookup"><span data-stu-id="19669-162">The output is as follows:</span></span>

```
Primes Up To 100:
[2; 3; 5; 7; 11; 13; 17; 19; 23; 29; 31; 37; 41; 43; 47; 53; 59; 61; 67; 71; 73; 79; 83; 89; 97]
```

## <a name="module-functions"></a><span data-ttu-id="19669-163">模块函数</span><span class="sxs-lookup"><span data-stu-id="19669-163">Module Functions</span></span>
<span data-ttu-id="19669-164">[列表模块](https://msdn.microsoft.com/library/a2264ba3-2d45-40dd-9040-4f7aa2ad9788)提供访问列表中的元素的函数。</span><span class="sxs-lookup"><span data-stu-id="19669-164">The [List module](https://msdn.microsoft.com/library/a2264ba3-2d45-40dd-9040-4f7aa2ad9788) provides functions that access the elements of a list.</span></span> <span data-ttu-id="19669-165">访问头元素的速度最快且最为容易。</span><span class="sxs-lookup"><span data-stu-id="19669-165">The head element is the fastest and easiest to access.</span></span> <span data-ttu-id="19669-166">使用属性[头](https://msdn.microsoft.com/library/5f9414fd-6bdb-470a-8b72-40016db30740)或模块函数[List.head](https://msdn.microsoft.com/library/22514cc5-0511-498b-a2cc-837b688a6da2)。</span><span class="sxs-lookup"><span data-stu-id="19669-166">Use the property [Head](https://msdn.microsoft.com/library/5f9414fd-6bdb-470a-8b72-40016db30740) or the module function [List.head](https://msdn.microsoft.com/library/22514cc5-0511-498b-a2cc-837b688a6da2).</span></span> <span data-ttu-id="19669-167">你可以通过使用访问列表尾[结尾](https://msdn.microsoft.com/library/2a6f8eb9-dc32-41aa-8b62-2baffaface91)属性或[List.tail](https://msdn.microsoft.com/library/da0a0638-4420-4571-84b6-d09ae601f601)函数。</span><span class="sxs-lookup"><span data-stu-id="19669-167">You can access the tail of a list by using the [Tail](https://msdn.microsoft.com/library/2a6f8eb9-dc32-41aa-8b62-2baffaface91) property or the [List.tail](https://msdn.microsoft.com/library/da0a0638-4420-4571-84b6-d09ae601f601) function.</span></span> <span data-ttu-id="19669-168">若要按索引查找元素，使用[List.nth](https://msdn.microsoft.com/library/1f717d57-89be-4007-a971-9cf5a28d83b1)函数。</span><span class="sxs-lookup"><span data-stu-id="19669-168">To find an element by index, use the [List.nth](https://msdn.microsoft.com/library/1f717d57-89be-4007-a971-9cf5a28d83b1) function.</span></span> <span data-ttu-id="19669-169">`List.nth` 将遍历列表。</span><span class="sxs-lookup"><span data-stu-id="19669-169">`List.nth` traverses the list.</span></span> <span data-ttu-id="19669-170">因此，它是 O (*n*)。</span><span class="sxs-lookup"><span data-stu-id="19669-170">Therefore, it is O(*n*).</span></span> <span data-ttu-id="19669-171">如果你的代码经常使用 `List.nth`，那么可能需要考虑使用数组而不是列表。</span><span class="sxs-lookup"><span data-stu-id="19669-171">If your code uses `List.nth` frequently, you might want to consider using an array instead of a list.</span></span> <span data-ttu-id="19669-172">数组中的元素访问的运算复杂度为 O(1)。</span><span class="sxs-lookup"><span data-stu-id="19669-172">Element access in arrays is O(1).</span></span>


### <a name="boolean-operations-on-lists"></a><span data-ttu-id="19669-173">针对列表的布尔操作</span><span class="sxs-lookup"><span data-stu-id="19669-173">Boolean Operations on Lists</span></span>
<span data-ttu-id="19669-174">[List.isEmpty](https://msdn.microsoft.com/library/a7941d44-9e92-427c-b806-c378f4558107)函数将确定一个列表是否包含任何元素。</span><span class="sxs-lookup"><span data-stu-id="19669-174">The [List.isEmpty](https://msdn.microsoft.com/library/a7941d44-9e92-427c-b806-c378f4558107) function determines whether a list has any elements.</span></span>

<span data-ttu-id="19669-175">[List.exists](https://msdn.microsoft.com/library/15a3ebd5-98f0-44c0-8220-7dedec3e68a8)函数应用布尔测试的元素列表和返回`true`在有元素满足该测试。</span><span class="sxs-lookup"><span data-stu-id="19669-175">The [List.exists](https://msdn.microsoft.com/library/15a3ebd5-98f0-44c0-8220-7dedec3e68a8) function applies a Boolean test to elements of a list and returns `true` if any element satisfies the test.</span></span> <span data-ttu-id="19669-176">[List.exists2](https://msdn.microsoft.com/library/7532b39e-3f4f-4534-a60b-d7721dc6fa7e)类似，但后续对两个列表中的元素进行操作。</span><span class="sxs-lookup"><span data-stu-id="19669-176">[List.exists2](https://msdn.microsoft.com/library/7532b39e-3f4f-4534-a60b-d7721dc6fa7e) is similar but operates on successive pairs of elements in two lists.</span></span>

<span data-ttu-id="19669-177">以下代码演示了 `List.exists` 的用法。</span><span class="sxs-lookup"><span data-stu-id="19669-177">The following code demonstrates the use of `List.exists`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lists/snippet1.fs)]

<span data-ttu-id="19669-178">输出如下所示：</span><span class="sxs-lookup"><span data-stu-id="19669-178">The output is as follows:</span></span>

```
For list [0; 1; 2; 3], contains zero is true
```

<span data-ttu-id="19669-179">以下示例演示了 `List.exists2` 的用法。</span><span class="sxs-lookup"><span data-stu-id="19669-179">The following example demonstrates the use of `List.exists2`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lists/snippet2.fs)]

<span data-ttu-id="19669-180">输出如下所示：</span><span class="sxs-lookup"><span data-stu-id="19669-180">The output is as follows:</span></span>

```
Lists [1; 2; 3; 4; 5] and [5; 4; 3; 2; 1] have at least one equal element at the same position.
```

<span data-ttu-id="19669-181">你可以使用[List.forall](https://msdn.microsoft.com/library/e11a5233-d612-40ac-833b-d5cf496900b7)如果你想要测试是否都列表中的所有元素都满足条件。</span><span class="sxs-lookup"><span data-stu-id="19669-181">You can use [List.forall](https://msdn.microsoft.com/library/e11a5233-d612-40ac-833b-d5cf496900b7) if you want to test whether all the elements of a list meet a condition.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lists/snippet3.fs)]

<span data-ttu-id="19669-182">输出如下所示：</span><span class="sxs-lookup"><span data-stu-id="19669-182">The output is as follows:</span></span>

```
true
false
```

<span data-ttu-id="19669-183">同样， [List.forall2](https://msdn.microsoft.com/library/bb611f02-8277-48f5-9af3-6194ae27d07e)确定两个列表中的相应位置中的所有元素是否都满足涉及每对元素的布尔表达式。</span><span class="sxs-lookup"><span data-stu-id="19669-183">Similarly, [List.forall2](https://msdn.microsoft.com/library/bb611f02-8277-48f5-9af3-6194ae27d07e) determines whether all elements in the corresponding positions in two lists satisfy a Boolean expression that involves each pair of elements.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lists/snippet4.fs)]

<span data-ttu-id="19669-184">输出如下所示：</span><span class="sxs-lookup"><span data-stu-id="19669-184">The output is as follows:</span></span>

```
true
false
```

### <a name="sort-operations-on-lists"></a><span data-ttu-id="19669-185">针对列表的排序操作</span><span class="sxs-lookup"><span data-stu-id="19669-185">Sort Operations on Lists</span></span>
<span data-ttu-id="19669-186">[List.sort](https://msdn.microsoft.com/library/17f1030e-aa7e-41dd-94ea-72cb6c04fd3d)， [List.sortBy](https://msdn.microsoft.com/library/955bfc5f-ad9c-4f2d-a7ab-91e43eb21359)，和[List.sortWith](https://msdn.microsoft.com/library/1d806a54-9166-4198-906d-15101f7916c7)函数对列表进行排序。</span><span class="sxs-lookup"><span data-stu-id="19669-186">The [List.sort](https://msdn.microsoft.com/library/17f1030e-aa7e-41dd-94ea-72cb6c04fd3d), [List.sortBy](https://msdn.microsoft.com/library/955bfc5f-ad9c-4f2d-a7ab-91e43eb21359), and [List.sortWith](https://msdn.microsoft.com/library/1d806a54-9166-4198-906d-15101f7916c7) functions sort lists.</span></span> <span data-ttu-id="19669-187">排序函数可确定要使用上面三个函数中的哪一个函数。</span><span class="sxs-lookup"><span data-stu-id="19669-187">The sorting function determines which of these three functions to use.</span></span> <span data-ttu-id="19669-188">`List.sort` 使用默认的泛型比较。</span><span class="sxs-lookup"><span data-stu-id="19669-188">`List.sort` uses default generic comparison.</span></span> <span data-ttu-id="19669-189">泛型比较根据泛型比较函数使用全局运算符来比较值。</span><span class="sxs-lookup"><span data-stu-id="19669-189">Generic comparison uses global operators based on the generic compare function to compare values.</span></span> <span data-ttu-id="19669-190">它能够有效地处理各种元素类型，例如简单数值类型、元组、记录、可区分联合、列表、数组以及任何实现 `System.IComparable` 的类型。</span><span class="sxs-lookup"><span data-stu-id="19669-190">It works efficiently with a wide variety of element types, such as simple numeric types, tuples, records, discriminated unions, lists, arrays, and any type that implements `System.IComparable`.</span></span> <span data-ttu-id="19669-191">对于实现 `System.IComparable` 的类型，泛型比较将使用 `System.IComparable.CompareTo()` 函数。</span><span class="sxs-lookup"><span data-stu-id="19669-191">For types that implement `System.IComparable`, generic comparison uses the `System.IComparable.CompareTo()` function.</span></span> <span data-ttu-id="19669-192">泛型比较还可处理字符串，只不过使用的是不依赖于区域性的排序顺序。</span><span class="sxs-lookup"><span data-stu-id="19669-192">Generic comparison also works with strings, but uses a culture-independent sorting order.</span></span> <span data-ttu-id="19669-193">不应对不支持的类型（例如函数类型）使用泛型比较。</span><span class="sxs-lookup"><span data-stu-id="19669-193">Generic comparison should not be used on unsupported types, such as function types.</span></span> <span data-ttu-id="19669-194">此外，默认泛型比较的性能最适用于小型结构化类型；对于需要经常比较和排序的大型结构化类型，请考虑实现 `System.IComparable` 并提供 `System.IComparable.CompareTo()` 方法的有效实现。</span><span class="sxs-lookup"><span data-stu-id="19669-194">Also, the performance of the default generic comparison is best for small structured types; for larger structured types that need to be compared and sorted frequently, consider implementing `System.IComparable` and providing an efficient implementation of the `System.IComparable.CompareTo()` method.</span></span>

<span data-ttu-id="19669-195">`List.sortBy` 使用一个函数，此函数返回一个用作排序条件的值，而 `List.sortWith` 将比较函数用作参数。</span><span class="sxs-lookup"><span data-stu-id="19669-195">`List.sortBy` takes a function that returns a value that is used as the sort criterion, and `List.sortWith` takes a comparison function as an argument.</span></span> <span data-ttu-id="19669-196">当你使用不支持比较的类型或比较需要更复杂的比较语义（对于区域性识别字符串）时，后面这两个函数会很有用。</span><span class="sxs-lookup"><span data-stu-id="19669-196">These latter two functions are useful when you are working with types that do not support comparison, or when the comparison requires more complex comparison semantics, as in the case of culture-aware strings.</span></span>

<span data-ttu-id="19669-197">以下示例演示了 `List.sort` 的用法。</span><span class="sxs-lookup"><span data-stu-id="19669-197">The following example demonstrates the use of `List.sort`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lists/snippet5.fs)]

<span data-ttu-id="19669-198">输出如下所示：</span><span class="sxs-lookup"><span data-stu-id="19669-198">The output is as follows:</span></span>

```
[-2; 1; 4; 5; 8]
```

<span data-ttu-id="19669-199">以下示例演示了 `List.sortBy` 的用法。</span><span class="sxs-lookup"><span data-stu-id="19669-199">The following example demonstrates the use of `List.sortBy`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lists/snippet6.fs)]

<span data-ttu-id="19669-200">输出如下所示：</span><span class="sxs-lookup"><span data-stu-id="19669-200">The output is as follows:</span></span>

```
[1; -2; 4; 5; 8]
```

<span data-ttu-id="19669-201">下一个示例演示了 `List.sortWith` 的用法。</span><span class="sxs-lookup"><span data-stu-id="19669-201">The next example demonstrates the use of `List.sortWith`.</span></span> <span data-ttu-id="19669-202">在此示例中，使用自定义比较函数 `compareWidgets` 首先比较自定义类型的一个字段，在第一个字段的值相等的情况下，再比较另一个字段。</span><span class="sxs-lookup"><span data-stu-id="19669-202">In this example, the custom comparison function `compareWidgets` is used to first compare one field of a custom type, and then another when the values of the first field are equal.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lists/snippet7.fs)]

<span data-ttu-id="19669-203">输出如下所示：</span><span class="sxs-lookup"><span data-stu-id="19669-203">The output is as follows:</span></span>

```
[{ID = 92;
Rev = 1;}; {ID = 92;
Rev = 1;}; {ID = 100;
Rev = 2;}; {ID = 100;
Rev = 5;}; {ID = 110;
Rev = 1;}]
```

### <a name="search-operations-on-lists"></a><span data-ttu-id="19669-204">针对列表的搜索操作</span><span class="sxs-lookup"><span data-stu-id="19669-204">Search Operations on Lists</span></span>
<span data-ttu-id="19669-205">可以对列表执行各种搜索操作。</span><span class="sxs-lookup"><span data-stu-id="19669-205">Numerous search operations are supported for lists.</span></span> <span data-ttu-id="19669-206">最简单[List.find](https://msdn.microsoft.com/library/0594593e-9c75-44c1-8f5a-a37b2e561c06)，可用于查找与给定的条件匹配的第一个元素。</span><span class="sxs-lookup"><span data-stu-id="19669-206">The simplest, [List.find](https://msdn.microsoft.com/library/0594593e-9c75-44c1-8f5a-a37b2e561c06), enables you to find the first element that matches a given condition.</span></span>

<span data-ttu-id="19669-207">以下代码示例演示了如何使用 `List.find` 来查找列表中可被 5 整除的第一个元素。</span><span class="sxs-lookup"><span data-stu-id="19669-207">The following code example demonstrates the use of `List.find` to find the first number that is divisible by 5 in a list.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lists/snippet8.fs)]

<span data-ttu-id="19669-208">结果为 5。</span><span class="sxs-lookup"><span data-stu-id="19669-208">The result is 5.</span></span>

<span data-ttu-id="19669-209">如果必须先转换元素，调用[List.pick](https://msdn.microsoft.com/library/0430b515-7fe4-49a1-a616-d2286d8b08b2)，它将采用一个函数，返回选项，并查找第一个选项值是`Some(x)`。</span><span class="sxs-lookup"><span data-stu-id="19669-209">If the elements must be transformed first, call [List.pick](https://msdn.microsoft.com/library/0430b515-7fe4-49a1-a616-d2286d8b08b2), which takes a function that returns an option, and looks for the first option value that is `Some(x)`.</span></span> <span data-ttu-id="19669-210">`List.pick` 返回结果 `x`，而不是返回元素。</span><span class="sxs-lookup"><span data-stu-id="19669-210">Instead of returning the element, `List.pick` returns the result `x`.</span></span> <span data-ttu-id="19669-211">如果未找到匹配的元素，则 `List.pick` 将引发 `System.Collections.Generic.KeyNotFoundException`。</span><span class="sxs-lookup"><span data-stu-id="19669-211">If no matching element is found, `List.pick` throws `System.Collections.Generic.KeyNotFoundException`.</span></span> <span data-ttu-id="19669-212">以下代码显示了 `List.pick` 的用法。</span><span class="sxs-lookup"><span data-stu-id="19669-212">The following code shows the use of `List.pick`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lists/snippet9.fs)]

<span data-ttu-id="19669-213">输出如下所示：</span><span class="sxs-lookup"><span data-stu-id="19669-213">The output is as follows:</span></span>

```
"b"
```

<span data-ttu-id="19669-214">另一组搜索操作[List.tryFind](https://msdn.microsoft.com/library/37f4532e-9fd0-4802-8bbd-e1aa2380287d)和相关的函数返回的选项值。</span><span class="sxs-lookup"><span data-stu-id="19669-214">Another group of search operations, [List.tryFind](https://msdn.microsoft.com/library/37f4532e-9fd0-4802-8bbd-e1aa2380287d) and related functions, return an option value.</span></span> <span data-ttu-id="19669-215">`List.tryFind` 函数返回列表中满足条件的第一个元素（如果该元素存在）；如果该元素不存在，则返回选项值 `None`。</span><span class="sxs-lookup"><span data-stu-id="19669-215">The `List.tryFind` function returns the first element of a list that satisfies a condition if such an element exists, but the option value `None` if not.</span></span> <span data-ttu-id="19669-216">变体[List.tryFindIndex](https://msdn.microsoft.com/library/5e31968c-c3d3-43d2-859a-0526825895ec)返回元素的索引，如果找到一个对象，而不是元素本身。</span><span class="sxs-lookup"><span data-stu-id="19669-216">The variation [List.tryFindIndex](https://msdn.microsoft.com/library/5e31968c-c3d3-43d2-859a-0526825895ec) returns the index of the element, if one is found, rather than the element itself.</span></span> <span data-ttu-id="19669-217">下面的代码中阐释了这些函数。</span><span class="sxs-lookup"><span data-stu-id="19669-217">These functions are illustrated in the following code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lists/snippet10.fs)]

<span data-ttu-id="19669-218">输出如下所示：</span><span class="sxs-lookup"><span data-stu-id="19669-218">The output is as follows:</span></span>

```
The first even value is 22.
The first even value is at position 8.
```

### <a name="arithmetic-operations-on-lists"></a><span data-ttu-id="19669-219">针对列表的算术运算</span><span class="sxs-lookup"><span data-stu-id="19669-219">Arithmetic Operations on Lists</span></span>
<span data-ttu-id="19669-220">常见的算术运算，如求和与求平均值内置于[列表模块](https://msdn.microsoft.com/library/a2264ba3-2d45-40dd-9040-4f7aa2ad9788)。</span><span class="sxs-lookup"><span data-stu-id="19669-220">Common arithmetic operations such as sum and average are built into the [List module](https://msdn.microsoft.com/library/a2264ba3-2d45-40dd-9040-4f7aa2ad9788).</span></span> <span data-ttu-id="19669-221">若要使用[List.sum](https://msdn.microsoft.com/library/54d47fe3-5ecf-4883-beb5-e915342a17f9)，列表元素类型必须支持`+`运算符和具有零值。</span><span class="sxs-lookup"><span data-stu-id="19669-221">To work with [List.sum](https://msdn.microsoft.com/library/54d47fe3-5ecf-4883-beb5-e915342a17f9), the list element type must support the `+` operator and have a zero value.</span></span> <span data-ttu-id="19669-222">所有内置算术类型都满足这些条件。</span><span class="sxs-lookup"><span data-stu-id="19669-222">All built-in arithmetic types satisfy these conditions.</span></span> <span data-ttu-id="19669-223">若要使用[List.average](https://msdn.microsoft.com/library/2b9a627b-106d-4548-8c4c-ab5058b8f8e1)，元素类型必须支持除法没有余数，其中排除整型类型，但允许浮点类型。</span><span class="sxs-lookup"><span data-stu-id="19669-223">To work with [List.average](https://msdn.microsoft.com/library/2b9a627b-106d-4548-8c4c-ab5058b8f8e1), the element type must support division without a remainder, which excludes integral types but allows for floating point types.</span></span> <span data-ttu-id="19669-224">[List.sumBy](https://msdn.microsoft.com/library/b7623389-0fe1-4762-9c67-51079903ab7d)和[List.averageBy](https://msdn.microsoft.com/library/936cc9ec-62af-464d-8726-7999c2f48403)函数采用一个函数作为参数，并使用此函数的结果来计算总和或平均值的值。</span><span class="sxs-lookup"><span data-stu-id="19669-224">The [List.sumBy](https://msdn.microsoft.com/library/b7623389-0fe1-4762-9c67-51079903ab7d) and [List.averageBy](https://msdn.microsoft.com/library/936cc9ec-62af-464d-8726-7999c2f48403) functions take a function as a parameter, and this function's results are used to calculate the values for the sum or average.</span></span>

<span data-ttu-id="19669-225">以下代码演示了 `List.sum`、`List.sumBy` 和 `List.average` 的用法。</span><span class="sxs-lookup"><span data-stu-id="19669-225">The following code demonstrates the use of `List.sum`, `List.sumBy`, and `List.average`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lists/snippet11.fs)]

<span data-ttu-id="19669-226">输出为 `1.000000`。</span><span class="sxs-lookup"><span data-stu-id="19669-226">The output is `1.000000`.</span></span>

<span data-ttu-id="19669-227">以下代码显示了 `List.averageBy` 的用法。</span><span class="sxs-lookup"><span data-stu-id="19669-227">The following code shows the use of `List.averageBy`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lists/snippet12.fs)]

<span data-ttu-id="19669-228">输出为 `5.5`。</span><span class="sxs-lookup"><span data-stu-id="19669-228">The output is `5.5`.</span></span>


### <a name="lists-and-tuples"></a><span data-ttu-id="19669-229">列表和元组</span><span class="sxs-lookup"><span data-stu-id="19669-229">Lists and Tuples</span></span>
<span data-ttu-id="19669-230">包含元组的列表可由压缩和解压缩函数操作。</span><span class="sxs-lookup"><span data-stu-id="19669-230">Lists that contain tuples can be manipulated by zip and unzip functions.</span></span> <span data-ttu-id="19669-231">这些函数将两个包含单值的列表合并为一个元组列表，或将一个元组列表分成两个包含单值的列表。</span><span class="sxs-lookup"><span data-stu-id="19669-231">These functions combine two lists of single values into one list of tuples or separate one list of tuples into two lists of single values.</span></span> <span data-ttu-id="19669-232">最简单[List.zip](https://msdn.microsoft.com/library/3028d790-8f48-4c94-bf08-b058bec3689c)函数采用两个列表的单个元素，并生成一个元组对的列表。</span><span class="sxs-lookup"><span data-stu-id="19669-232">The simplest [List.zip](https://msdn.microsoft.com/library/3028d790-8f48-4c94-bf08-b058bec3689c) function takes two lists of single elements and produces a single list of tuple pairs.</span></span> <span data-ttu-id="19669-233">另一个版本， [List.zip3](https://msdn.microsoft.com/library/003cc28e-0de3-4d99-89ed-cb19028e3c5b)、 采用三个列表的单个元素，并生成一个包含三个元素的元组列表。</span><span class="sxs-lookup"><span data-stu-id="19669-233">Another version, [List.zip3](https://msdn.microsoft.com/library/003cc28e-0de3-4d99-89ed-cb19028e3c5b), takes three lists of single elements and produces a single list of tuples that have three elements.</span></span> <span data-ttu-id="19669-234">以下代码示例演示了 `List.zip` 的用法。</span><span class="sxs-lookup"><span data-stu-id="19669-234">The following code example demonstrates the use of `List.zip`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lists/snippet13.fs)]

<span data-ttu-id="19669-235">输出如下所示：</span><span class="sxs-lookup"><span data-stu-id="19669-235">The output is as follows:</span></span>

```
[(1, -1); (2, -2); (3; -3)]
```

<span data-ttu-id="19669-236">以下代码示例演示了 `List.zip3` 的用法。</span><span class="sxs-lookup"><span data-stu-id="19669-236">The following code example demonstrates the use of `List.zip3`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lists/snippet14.fs)]

<span data-ttu-id="19669-237">输出如下所示：</span><span class="sxs-lookup"><span data-stu-id="19669-237">The output is as follows:</span></span>

```
[(1, -1, 0); (2, -2, 0); (3, -3, 0)]
```

<span data-ttu-id="19669-238">相应的解压缩版本， [List.unzip](https://msdn.microsoft.com/library/639db80c-41b5-45bb-a6b4-1eaa04d61d21)和[List.unzip3](https://msdn.microsoft.com/library/43078c77-32ec-4342-85b3-c31ccf984db4)返回列表中的一个元组，其中第一个列表包含了每个元组中的第一行的所有元素，并采取元组列表和第二个列表包含每个元组和等等的第二个元素。</span><span class="sxs-lookup"><span data-stu-id="19669-238">The corresponding unzip versions, [List.unzip](https://msdn.microsoft.com/library/639db80c-41b5-45bb-a6b4-1eaa04d61d21) and [List.unzip3](https://msdn.microsoft.com/library/43078c77-32ec-4342-85b3-c31ccf984db4), take lists of tuples and return lists in a tuple, where the first list contains all the elements that were first in each tuple, and the second list contains the second element of each tuple, and so on.</span></span>

<span data-ttu-id="19669-239">下面的代码示例演示如何将[List.unzip](https://msdn.microsoft.com/library/639db80c-41b5-45bb-a6b4-1eaa04d61d21)。</span><span class="sxs-lookup"><span data-stu-id="19669-239">The following code example demonstrates the use of [List.unzip](https://msdn.microsoft.com/library/639db80c-41b5-45bb-a6b4-1eaa04d61d21).</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lists/snippet15.fs)]

<span data-ttu-id="19669-240">输出如下所示：</span><span class="sxs-lookup"><span data-stu-id="19669-240">The output is as follows:</span></span>

```
([1; 3], [2; 4])
[1; 3] [2; 4]
```

<span data-ttu-id="19669-241">下面的代码示例演示如何将[List.unzip3](https://msdn.microsoft.com/library/43078c77-32ec-4342-85b3-c31ccf984db4)。</span><span class="sxs-lookup"><span data-stu-id="19669-241">The following code example demonstrates the use of [List.unzip3](https://msdn.microsoft.com/library/43078c77-32ec-4342-85b3-c31ccf984db4).</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lists/snippet16.fs)]

<span data-ttu-id="19669-242">输出如下所示：</span><span class="sxs-lookup"><span data-stu-id="19669-242">The output is as follows:</span></span>

```
([1; 4], [2; 5], [3; 6])
```

### <a name="operating-on-list-elements"></a><span data-ttu-id="19669-243">针对列表元素的操作</span><span class="sxs-lookup"><span data-stu-id="19669-243">Operating on List Elements</span></span>
<span data-ttu-id="19669-244">F# 支持针对列表元素执行各种操作。</span><span class="sxs-lookup"><span data-stu-id="19669-244">F# supports a variety of operations on list elements.</span></span> <span data-ttu-id="19669-245">最简单的是[List.iter](https://msdn.microsoft.com/library/f778d075-81a9-4994-af60-cddcc53a201f)，从而使你可以在列表中的每个元素调用的函数。</span><span class="sxs-lookup"><span data-stu-id="19669-245">The simplest is [List.iter](https://msdn.microsoft.com/library/f778d075-81a9-4994-af60-cddcc53a201f), which enables you to call a function on every element of a list.</span></span> <span data-ttu-id="19669-246">变体包括[List.iter2](https://msdn.microsoft.com/library/ea3b7761-916c-4016-9bd8-651124c98b40)，这样您就可以对两个列表的元素执行操作[List.iteri](https://msdn.microsoft.com/library/6dd21ae6-5c00-41cd-8306-821e513d8f60)，就像一样`List.iter`只不过作为传递每个元素的索引为每个元素，调用该函数参数和[List.iteri2](https://msdn.microsoft.com/library/9658d740-9be5-4bf7-b663-c8ab2b3e196c)，它是功能的组合`List.iter2`和`List.iteri`。</span><span class="sxs-lookup"><span data-stu-id="19669-246">Variations include [List.iter2](https://msdn.microsoft.com/library/ea3b7761-916c-4016-9bd8-651124c98b40), which enables you to perform an operation on elements of two lists, [List.iteri](https://msdn.microsoft.com/library/6dd21ae6-5c00-41cd-8306-821e513d8f60), which is like `List.iter` except that the index of each element is passed as an argument to the function that is called for each element, and [List.iteri2](https://msdn.microsoft.com/library/9658d740-9be5-4bf7-b663-c8ab2b3e196c), which is a combination of the functionality of `List.iter2` and `List.iteri`.</span></span> <span data-ttu-id="19669-247">以下代码示例阐释了这些函数。</span><span class="sxs-lookup"><span data-stu-id="19669-247">The following code example illustrates these functions.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lists/snippet17.fs)]

<span data-ttu-id="19669-248">输出如下所示：</span><span class="sxs-lookup"><span data-stu-id="19669-248">The output is as follows:</span></span>

```
List.iter: element is 1
List.iter: element is 2
List.iter: element is 3
List.iteri: element 0 is 1
List.iteri: element 1 is 2
List.iteri: element 2 is 3
List.iter2: elements are 1 4
List.iter2: elements are 2 5
List.iter2: elements are 3 6
List.iteri2: element 0 of list1 is 1; element 0 of list2 is 4
List.iteri2: element 1 of list1 is 2; element 1 of list2 is 5
List.iteri2: element 2 of list1 is 3; element 2 of list2 is 6
```

<span data-ttu-id="19669-249">另一个转换列表元素的常用的功能是[List.map](https://msdn.microsoft.com/library/c6b49c99-d4f3-4ba3-b1d0-85a312683dc6)，从中可以对列表中的每个元素应用一个函数，并将所有结果都放入一个新列表。</span><span class="sxs-lookup"><span data-stu-id="19669-249">Another frequently used function that transforms list elements is [List.map](https://msdn.microsoft.com/library/c6b49c99-d4f3-4ba3-b1d0-85a312683dc6), which enables you to apply a function to each element of a list and put all the results into a new list.</span></span> <span data-ttu-id="19669-250">[List.map2](https://msdn.microsoft.com/library/5f48cce7-6eaf-4e54-8996-2b04d3c31e57)和[List.map3](https://msdn.microsoft.com/library/dd9fb190-6980-4537-be96-5645a64908f8)是采用多个列表的变体。</span><span class="sxs-lookup"><span data-stu-id="19669-250">[List.map2](https://msdn.microsoft.com/library/5f48cce7-6eaf-4e54-8996-2b04d3c31e57) and [List.map3](https://msdn.microsoft.com/library/dd9fb190-6980-4537-be96-5645a64908f8) are variations that take multiple lists.</span></span> <span data-ttu-id="19669-251">你还可以使用[List.mapi](https://msdn.microsoft.com/library/284b9234-3d26-409b-b328-ac79638d9e14)和[List.mapi2](https://msdn.microsoft.com/library/680643af-233c-40a3-82f2-43d5af27ec49)，如果除了元素，该函数需要传递每个元素的索引。</span><span class="sxs-lookup"><span data-stu-id="19669-251">You can also use [List.mapi](https://msdn.microsoft.com/library/284b9234-3d26-409b-b328-ac79638d9e14) and [List.mapi2](https://msdn.microsoft.com/library/680643af-233c-40a3-82f2-43d5af27ec49), if, in addition to the element, the function needs to be passed the index of each element.</span></span> <span data-ttu-id="19669-252">`List.mapi2` 和 `List.mapi` 之间的唯一区别在于 `List.mapi2` 使用了两个列表。</span><span class="sxs-lookup"><span data-stu-id="19669-252">The only difference between `List.mapi2` and `List.mapi` is that `List.mapi2` works with two lists.</span></span> <span data-ttu-id="19669-253">下面的示例演示[List.map](https://msdn.microsoft.com/library/c6b49c99-d4f3-4ba3-b1d0-85a312683dc6)。</span><span class="sxs-lookup"><span data-stu-id="19669-253">The following example illustrates [List.map](https://msdn.microsoft.com/library/c6b49c99-d4f3-4ba3-b1d0-85a312683dc6).</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lists/snippet18.fs)]

<span data-ttu-id="19669-254">输出如下所示：</span><span class="sxs-lookup"><span data-stu-id="19669-254">The output is as follows:</span></span>

```
[2; 3; 4]
```

<span data-ttu-id="19669-255">以下示例显示了 `List.map2` 的用法。</span><span class="sxs-lookup"><span data-stu-id="19669-255">The following example shows the use of `List.map2`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lists/snippet19.fs)]

<span data-ttu-id="19669-256">输出如下所示：</span><span class="sxs-lookup"><span data-stu-id="19669-256">The output is as follows:</span></span>

```
[5; 7; 9]
```

<span data-ttu-id="19669-257">以下示例显示了 `List.map3` 的用法。</span><span class="sxs-lookup"><span data-stu-id="19669-257">The following example shows the use of `List.map3`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lists/snippet20.fs)]

<span data-ttu-id="19669-258">输出如下所示：</span><span class="sxs-lookup"><span data-stu-id="19669-258">The output is as follows:</span></span>

```
[7; 10; 13]
```

<span data-ttu-id="19669-259">以下示例显示了 `List.mapi` 的用法。</span><span class="sxs-lookup"><span data-stu-id="19669-259">The following example shows the use of `List.mapi`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lists/snippet21.fs)]

<span data-ttu-id="19669-260">输出如下所示：</span><span class="sxs-lookup"><span data-stu-id="19669-260">The output is as follows:</span></span>

```
[1; 3; 5]
```

<span data-ttu-id="19669-261">以下示例显示了 `List.mapi2` 的用法。</span><span class="sxs-lookup"><span data-stu-id="19669-261">The following example shows the use of `List.mapi2`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lists/snippet22.fs)]

<span data-ttu-id="19669-262">输出如下所示：</span><span class="sxs-lookup"><span data-stu-id="19669-262">The output is as follows:</span></span>

```
[0; 7; 18]
```

<span data-ttu-id="19669-263">[List.collect](https://msdn.microsoft.com/library/cd08bbc7-a3b9-40ab-8c20-4e85ec84664f)类似`List.map`，区别在于每个元素生成一个列表，并且所有这些列表将串联成一个最终列表。</span><span class="sxs-lookup"><span data-stu-id="19669-263">[List.collect](https://msdn.microsoft.com/library/cd08bbc7-a3b9-40ab-8c20-4e85ec84664f) is like `List.map`, except that each element produces a list and all these lists are concatenated into a final list.</span></span> <span data-ttu-id="19669-264">在以下代码中，列表的每个元素均生成三个数字。</span><span class="sxs-lookup"><span data-stu-id="19669-264">In the following code, each element of the list generates three numbers.</span></span> <span data-ttu-id="19669-265">所有这些数字将收集到一个列表中。</span><span class="sxs-lookup"><span data-stu-id="19669-265">These are all collected into one list.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lists/snippet23.fs)]

<span data-ttu-id="19669-266">输出如下所示：</span><span class="sxs-lookup"><span data-stu-id="19669-266">The output is as follows:</span></span>

```
[1; 2; 3; 2; 4; 6; 3; 6; 9]
```

<span data-ttu-id="19669-267">你还可以使用[List.filter](https://msdn.microsoft.com/library/11a8c926-547b-44dd-bbae-98d44f3dd248)，其采用布尔条件，并生成一个仅包含满足给定的条件的元素的新列表。</span><span class="sxs-lookup"><span data-stu-id="19669-267">You can also use [List.filter](https://msdn.microsoft.com/library/11a8c926-547b-44dd-bbae-98d44f3dd248), which takes a Boolean condition and produces a new list that consists only of elements that satisfy the given condition.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lists/snippet24.fs)]

<span data-ttu-id="19669-268">生成的列表为 `[2; 4; 6]`。</span><span class="sxs-lookup"><span data-stu-id="19669-268">The resulting list is `[2; 4; 6]`.</span></span>

<span data-ttu-id="19669-269">映射和筛选器，组合[List.choose](https://msdn.microsoft.com/library/2e21d3fb-ce35-4824-8a57-c4404616093d)使您能够转换和同时选择元素。</span><span class="sxs-lookup"><span data-stu-id="19669-269">A combination of map and filter, [List.choose](https://msdn.microsoft.com/library/2e21d3fb-ce35-4824-8a57-c4404616093d) enables you to transform and select elements at the same time.</span></span> <span data-ttu-id="19669-270">`List.choose` 对列表的每个元素应用一个返回选项的函数，并在该函数返回选项值 `Some` 时为元素返回新的结果列表。</span><span class="sxs-lookup"><span data-stu-id="19669-270">`List.choose` applies a function that returns an option to each element of a list, and returns a new list of the results for elements when the function returns the option value `Some`.</span></span>

<span data-ttu-id="19669-271">以下代码演示了如何使用 `List.choose` 从单词列表中选择大写单词。</span><span class="sxs-lookup"><span data-stu-id="19669-271">The following code demonstrates the use of `List.choose` to select capitalized words out of a list of words.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lists/snippet25.fs)]

<span data-ttu-id="19669-272">输出如下所示：</span><span class="sxs-lookup"><span data-stu-id="19669-272">The output is as follows:</span></span>

```
["Rome's"; "Bob's"]
```

### <a name="operating-on-multiple-lists"></a><span data-ttu-id="19669-273">针对多个列表的操作</span><span class="sxs-lookup"><span data-stu-id="19669-273">Operating on Multiple Lists</span></span>
<span data-ttu-id="19669-274">可以将多个列表联接在一起。</span><span class="sxs-lookup"><span data-stu-id="19669-274">Lists can be joined together.</span></span> <span data-ttu-id="19669-275">若要将两个列表联接成一个，使用[List.append](https://msdn.microsoft.com/library/2954da80-3f4a-4a4b-9371-794645c03426)。</span><span class="sxs-lookup"><span data-stu-id="19669-275">To join two lists into one, use [List.append](https://msdn.microsoft.com/library/2954da80-3f4a-4a4b-9371-794645c03426).</span></span> <span data-ttu-id="19669-276">若要加入两个以上的列表，请使用[List.concat](https://msdn.microsoft.com/library/c5afd433-8764-4ea8-a6a8-937fb4d77c4c)。</span><span class="sxs-lookup"><span data-stu-id="19669-276">To join more than two lists, use [List.concat](https://msdn.microsoft.com/library/c5afd433-8764-4ea8-a6a8-937fb4d77c4c).</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lists/snippet26.fs)]
    
### <a name="fold-and-scan-operations"></a><span data-ttu-id="19669-277">Fold 和 Scan 操作</span><span class="sxs-lookup"><span data-stu-id="19669-277">Fold and Scan Operations</span></span>
<span data-ttu-id="19669-278">一些列表操作涉及所有列表元素之间的相互依赖关系。</span><span class="sxs-lookup"><span data-stu-id="19669-278">Some list operations involve interdependencies between all of the list elements.</span></span> <span data-ttu-id="19669-279">Fold 和 scan 操作就像`List.iter`和`List.map`，因为调用一个函数对每个元素，但这些操作提供附加参数调用*累加器*，传送信息计算。</span><span class="sxs-lookup"><span data-stu-id="19669-279">The fold and scan operations are like `List.iter` and `List.map` in that you invoke a function on each element, but these operations provide an additional parameter called the *accumulator* that carries information through the computation.</span></span>

<span data-ttu-id="19669-280">使用 `List.fold` 可对列表执行计算。</span><span class="sxs-lookup"><span data-stu-id="19669-280">Use `List.fold` to perform a calculation on a list.</span></span>

<span data-ttu-id="19669-281">下面的代码示例演示如何将[List.fold](https://msdn.microsoft.com/library/c272779e-bae7-4983-8d7f-16b345bb33a0)以执行各种操作。</span><span class="sxs-lookup"><span data-stu-id="19669-281">The following code example demonstrates the use of [List.fold](https://msdn.microsoft.com/library/c272779e-bae7-4983-8d7f-16b345bb33a0) to perform various operations.</span></span>

<span data-ttu-id="19669-282">将遍历列表；累加器 `acc` 是一个在计算过程中不断传递的值。</span><span class="sxs-lookup"><span data-stu-id="19669-282">The list is traversed; the accumulator `acc` is a value that is passed along as the calculation proceeds.</span></span> <span data-ttu-id="19669-283">第一个参数采用累加器和列表元素，并返回针对列表元素的计算的中间结果。</span><span class="sxs-lookup"><span data-stu-id="19669-283">The first argument takes the accumulator and the list element, and returns the interim result of the calculation for that list element.</span></span> <span data-ttu-id="19669-284">第二个参数为累加器的初始值。</span><span class="sxs-lookup"><span data-stu-id="19669-284">The second argument is the initial value of the accumulator.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lists/snippet27.fs)]

<span data-ttu-id="19669-285">这些函数的各个版本（函数名中有一个数字）对多个列表执行操作。</span><span class="sxs-lookup"><span data-stu-id="19669-285">The versions of these functions that have a digit in the function name operate on more than one list.</span></span> <span data-ttu-id="19669-286">例如， [List.fold2](https://msdn.microsoft.com/library/6cfcd043-a65d-4423-805a-2ab234cb5343)对两个列表执行计算。</span><span class="sxs-lookup"><span data-stu-id="19669-286">For example, [List.fold2](https://msdn.microsoft.com/library/6cfcd043-a65d-4423-805a-2ab234cb5343) performs computations on two lists.</span></span>

<span data-ttu-id="19669-287">以下示例演示了 `List.fold2` 的用法。</span><span class="sxs-lookup"><span data-stu-id="19669-287">The following example demonstrates the use of `List.fold2`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lists/snippet28.fs)]

<span data-ttu-id="19669-288">`List.fold`和[List.scan](https://msdn.microsoft.com/library/21f636db-885c-4a72-970e-e3841f33a1b8)的差异在于`List.fold`返回额外参数的最终值但`List.scan`返回额外参数的中间值 （连同最终值） 的列表。</span><span class="sxs-lookup"><span data-stu-id="19669-288">`List.fold` and [List.scan](https://msdn.microsoft.com/library/21f636db-885c-4a72-970e-e3841f33a1b8) differ in that `List.fold` returns the final value of the extra parameter, but `List.scan` returns the list of the intermediate values (along with the final value) of the extra parameter.</span></span>

<span data-ttu-id="19669-289">其中每个函数包括反向变体，例如， [List.foldBack](https://msdn.microsoft.com/library/b9a58e66-efe1-445f-a90c-ac9ffb9d40c7)，在顺序中与它不同列表的遍历和自变量的顺序。</span><span class="sxs-lookup"><span data-stu-id="19669-289">Each of these functions includes a reverse variation, for example, [List.foldBack](https://msdn.microsoft.com/library/b9a58e66-efe1-445f-a90c-ac9ffb9d40c7), which differs in the order in which the list is traversed and the order of the arguments.</span></span> <span data-ttu-id="19669-290">此外，`List.fold`和`List.foldBack`具有变体， [List.fold2](https://msdn.microsoft.com/library/6cfcd043-a65d-4423-805a-2ab234cb5343)和[List.foldBack2](https://msdn.microsoft.com/library/56371d3e-5271-4183-9e8c-15a02eda9aa2)，它们采用两个列表的长度相等。</span><span class="sxs-lookup"><span data-stu-id="19669-290">Also, `List.fold` and `List.foldBack` have variations, [List.fold2](https://msdn.microsoft.com/library/6cfcd043-a65d-4423-805a-2ab234cb5343) and [List.foldBack2](https://msdn.microsoft.com/library/56371d3e-5271-4183-9e8c-15a02eda9aa2), that take two lists of equal length.</span></span> <span data-ttu-id="19669-291">对每个元素执行的函数可以使用两个列表的对应元素来执行一些操作。</span><span class="sxs-lookup"><span data-stu-id="19669-291">The function that executes on each element can use corresponding elements of both lists to perform some action.</span></span> <span data-ttu-id="19669-292">两个列表的元素类型可以不同（如以下示例所示），其中一个列表包含银行帐户的交易金额，而另一个列表包含交易的类型：存款或取款。</span><span class="sxs-lookup"><span data-stu-id="19669-292">The element types of the two lists can be different, as in the following example, in which one list contains transaction amounts for a bank account, and the other list contains the type of transaction: deposit or withdrawal.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lists/snippet29.fs)]

<span data-ttu-id="19669-293">对于类似于求和这样的计算，`List.fold` 和 `List.foldBack` 具有相同的效果，因为结果不依赖于遍历顺序。</span><span class="sxs-lookup"><span data-stu-id="19669-293">For a calculation like summation, `List.fold` and `List.foldBack` have the same effect because the result does not depend on the order of traversal.</span></span> <span data-ttu-id="19669-294">在以下示例中，`List.foldBack` 用于在列表中添加元素。</span><span class="sxs-lookup"><span data-stu-id="19669-294">In the following example, `List.foldBack` is used to add the elements in a list.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lists/snippet30.fs)]

<span data-ttu-id="19669-295">以下示例将返回到银行帐户示例。</span><span class="sxs-lookup"><span data-stu-id="19669-295">The following example returns to the bank account example.</span></span> <span data-ttu-id="19669-296">这次，添加一个新的交易类型：利息计算。</span><span class="sxs-lookup"><span data-stu-id="19669-296">This time a new transaction type is added: an interest calculation.</span></span> <span data-ttu-id="19669-297">期末余额现在取决于事务顺序。</span><span class="sxs-lookup"><span data-stu-id="19669-297">The ending balance now depends on the order of transactions.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lists/snippet34.fs)]

<span data-ttu-id="19669-298">该函数[List.reduce](https://msdn.microsoft.com/library/048e1f95-691b-49cb-bb99-fb85f68f3d8b)有些类似`List.fold`和`List.scan`，只不过它不是传递单独的累加器，`List.reduce`采用采用两个参数的元素类型而不是一个函数只是一个，并这些自变量之一将用作累加器，这意味着它将存储计算的中间结果。</span><span class="sxs-lookup"><span data-stu-id="19669-298">The function [List.reduce](https://msdn.microsoft.com/library/048e1f95-691b-49cb-bb99-fb85f68f3d8b) is somewhat like `List.fold` and `List.scan`, except that instead of passing around a separate accumulator, `List.reduce` takes a function that takes two arguments of the element type instead of just one, and one of those arguments acts as the accumulator, meaning that it stores the intermediate result of the computation.</span></span> <span data-ttu-id="19669-299">`List.reduce` 首先对前两个列表元素执行操作，然后将操作的结果和下一个元素一起使用。</span><span class="sxs-lookup"><span data-stu-id="19669-299">`List.reduce` starts by operating on the first two list elements, and then uses the result of the operation along with the next element.</span></span> <span data-ttu-id="19669-300">由于不存在具有自己的类型的单独累加器，因此只可以在累加器和元素类型的类型相同时，使用 `List.reduce` 代替 `List.fold`。</span><span class="sxs-lookup"><span data-stu-id="19669-300">Because there is not a separate accumulator that has its own type, `List.reduce` can be used in place of `List.fold` only when the accumulator and the element type have the same type.</span></span> <span data-ttu-id="19669-301">以下代码演示了 `List.reduce` 的用法。</span><span class="sxs-lookup"><span data-stu-id="19669-301">The following code demonstrates the use of `List.reduce`.</span></span> <span data-ttu-id="19669-302">如果提供的列表中不包含任何元素，则 `List.reduce` 将引发异常。</span><span class="sxs-lookup"><span data-stu-id="19669-302">`List.reduce` throws an exception if the list provided has no elements.</span></span>

<span data-ttu-id="19669-303">在以下代码中，对 lambda 表达式的第一个调用提供了参数 2 和 4，并返回 6；下一个调用提供了参数 6 和 10，因此结果为 16。</span><span class="sxs-lookup"><span data-stu-id="19669-303">In the following code, the first call to the lambda expression is given the arguments 2 and 4, and returns 6, and the next call is given the arguments 6 and 10, so the result is 16.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lists/snippet33.fs)]
    
### <a name="converting-between-lists-and-other-collection-types"></a><span data-ttu-id="19669-304">在列表和其他集合类型之间进行转换</span><span class="sxs-lookup"><span data-stu-id="19669-304">Converting Between Lists and Other Collection Types</span></span>
<span data-ttu-id="19669-305">`List` 模块提供了用于来回转换序列和数组的函数。</span><span class="sxs-lookup"><span data-stu-id="19669-305">The `List` module provides functions for converting to and from both sequences and arrays.</span></span> <span data-ttu-id="19669-306">若要将转换为或从一个序列，请使用[List.toSeq](https://msdn.microsoft.com/library/7024be4b-ee70-43cc-8d0a-e6564a4ff7c0)或[List.ofSeq](https://msdn.microsoft.com/library/74ab9289-4a59-4433-92eb-3f662d7f7db0)。</span><span class="sxs-lookup"><span data-stu-id="19669-306">To convert to or from a sequence, use [List.toSeq](https://msdn.microsoft.com/library/7024be4b-ee70-43cc-8d0a-e6564a4ff7c0) or [List.ofSeq](https://msdn.microsoft.com/library/74ab9289-4a59-4433-92eb-3f662d7f7db0).</span></span> <span data-ttu-id="19669-307">若要将转换为或从一个数组，使用[List.toArray](https://msdn.microsoft.com/library/ac87dd82-a0cd-40b3-b1fa-dd3168134547)或[List.ofArray](https://msdn.microsoft.com/library/f4bddc26-8c8f-4307-a6d7-a49dceb97032)。</span><span class="sxs-lookup"><span data-stu-id="19669-307">To convert to or from an array, use [List.toArray](https://msdn.microsoft.com/library/ac87dd82-a0cd-40b3-b1fa-dd3168134547) or [List.ofArray](https://msdn.microsoft.com/library/f4bddc26-8c8f-4307-a6d7-a49dceb97032).</span></span>


### <a name="additional-operations"></a><span data-ttu-id="19669-308">其他操作</span><span class="sxs-lookup"><span data-stu-id="19669-308">Additional Operations</span></span>
<span data-ttu-id="19669-309">有关更多的操作列表的信息，请参阅库参考主题[Collections.List 模块](https://msdn.microsoft.com/visualfsharpdocs/conceptual/collections.list-module-%5bfsharp%5d)。</span><span class="sxs-lookup"><span data-stu-id="19669-309">For information about additional operations on lists, see the library reference topic [Collections.List Module](https://msdn.microsoft.com/visualfsharpdocs/conceptual/collections.list-module-%5bfsharp%5d).</span></span>


## <a name="see-also"></a><span data-ttu-id="19669-310">另请参阅</span><span class="sxs-lookup"><span data-stu-id="19669-310">See Also</span></span>
[<span data-ttu-id="19669-311">F# 语言参考</span><span class="sxs-lookup"><span data-stu-id="19669-311">F# Language Reference</span></span>](index.md)

[<span data-ttu-id="19669-312">F# 类型</span><span class="sxs-lookup"><span data-stu-id="19669-312">F# Types</span></span>](fsharp-types.md)

[<span data-ttu-id="19669-313">序列</span><span class="sxs-lookup"><span data-stu-id="19669-313">Sequences</span></span>](sequences.md)

[<span data-ttu-id="19669-314">阵列</span><span class="sxs-lookup"><span data-stu-id="19669-314">Arrays</span></span>](arrays.md)

[<span data-ttu-id="19669-315">选项</span><span class="sxs-lookup"><span data-stu-id="19669-315">Options</span></span>](options.md)
