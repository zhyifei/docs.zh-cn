---
title: 阵列
description: 了解如何以F#编程语言创建和使用数组。
ms.date: 05/16/2016
ms.openlocfilehash: 8470e01087e417635bcd5c528df9b9e089cbf59f
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/15/2019
ms.locfileid: "72320491"
---
# <a name="arrays"></a><span data-ttu-id="a0bbd-103">阵列</span><span class="sxs-lookup"><span data-stu-id="a0bbd-103">Arrays</span></span>

> [!NOTE]
> <span data-ttu-id="a0bbd-104">API 参考链接将转至 MSDN。</span><span class="sxs-lookup"><span data-stu-id="a0bbd-104">The API reference link will take you to MSDN.</span></span>  <span data-ttu-id="a0bbd-105">Docs.microsoft.com API 参考尚未完成。</span><span class="sxs-lookup"><span data-stu-id="a0bbd-105">The docs.microsoft.com API reference is not complete.</span></span>

<span data-ttu-id="a0bbd-106">数组是固定大小的、从零开始、可变的连续数据元素集合，这些元素属于同一类型。</span><span class="sxs-lookup"><span data-stu-id="a0bbd-106">Arrays are fixed-size, zero-based, mutable collections of consecutive data elements that are all of the same type.</span></span>

## <a name="creating-arrays"></a><span data-ttu-id="a0bbd-107">创建数组</span><span class="sxs-lookup"><span data-stu-id="a0bbd-107">Creating Arrays</span></span>

<span data-ttu-id="a0bbd-108">可以通过多种方式创建数组。</span><span class="sxs-lookup"><span data-stu-id="a0bbd-108">You can create arrays in several ways.</span></span> <span data-ttu-id="a0bbd-109">可以通过列出 `[|` 和 `|]` 之间的连续值并以分号分隔，来创建一个小型数组，如下面的示例中所示。</span><span class="sxs-lookup"><span data-stu-id="a0bbd-109">You can create a small array by listing consecutive values between `[|` and `|]` and separated by semicolons, as shown in the following examples.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet1.fs)]

<span data-ttu-id="a0bbd-110">您还可以将每个元素放在单独的行上，在这种情况下，分号分隔符是可选的。</span><span class="sxs-lookup"><span data-stu-id="a0bbd-110">You can also put each element on a separate line, in which case the semicolon separator is optional.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet2.fs)]

<span data-ttu-id="a0bbd-111">数组元素的类型是从使用的文本中推断出来的，并且必须一致。</span><span class="sxs-lookup"><span data-stu-id="a0bbd-111">The type of the array elements is inferred from the literals used and must be consistent.</span></span> <span data-ttu-id="a0bbd-112">下面的代码会导致错误，因为1.0 为 float，2和3是整数。</span><span class="sxs-lookup"><span data-stu-id="a0bbd-112">The following code causes an error because 1.0 is a float and 2 and 3 are integers.</span></span>

```fsharp
// Causes an error.
// let array2 = [| 1.0; 2; 3 |]
```

<span data-ttu-id="a0bbd-113">您还可以使用序列表达式来创建数组。</span><span class="sxs-lookup"><span data-stu-id="a0bbd-113">You can also use sequence expressions to create arrays.</span></span> <span data-ttu-id="a0bbd-114">下面的示例创建一个从1到10的整数的平方的数组。</span><span class="sxs-lookup"><span data-stu-id="a0bbd-114">Following is an example that creates an array of squares of integers from 1 to 10.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet3.fs)]

<span data-ttu-id="a0bbd-115">若要创建将所有元素都初始化为零的数组，请使用 `Array.zeroCreate`。</span><span class="sxs-lookup"><span data-stu-id="a0bbd-115">To create an array in which all the elements are initialized to zero, use `Array.zeroCreate`.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet4.fs)]

## <a name="accessing-elements"></a><span data-ttu-id="a0bbd-116">访问元素</span><span class="sxs-lookup"><span data-stu-id="a0bbd-116">Accessing Elements</span></span>

<span data-ttu-id="a0bbd-117">您可以使用点运算符（`.`）和方括号（`[` 和 `]`）访问数组元素。</span><span class="sxs-lookup"><span data-stu-id="a0bbd-117">You can access array elements by using a dot operator (`.`) and brackets (`[` and `]`).</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet5.fs)]

<span data-ttu-id="a0bbd-118">数组索引从0开始。</span><span class="sxs-lookup"><span data-stu-id="a0bbd-118">Array indexes start at 0.</span></span>

<span data-ttu-id="a0bbd-119">您还可以通过使用切片表示法来访问数组元素，这使您能够指定数组的子范围。</span><span class="sxs-lookup"><span data-stu-id="a0bbd-119">You can also access array elements by using slice notation, which enables you to specify a subrange of the array.</span></span> <span data-ttu-id="a0bbd-120">下面是切片表示法的示例。</span><span class="sxs-lookup"><span data-stu-id="a0bbd-120">Examples of slice notation follow.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet51.fs)]

<span data-ttu-id="a0bbd-121">使用切片表示法时，将创建数组的新副本。</span><span class="sxs-lookup"><span data-stu-id="a0bbd-121">When slice notation is used, a new copy of the array is created.</span></span>

## <a name="array-types-and-modules"></a><span data-ttu-id="a0bbd-122">数组类型和模块</span><span class="sxs-lookup"><span data-stu-id="a0bbd-122">Array Types and Modules</span></span>

<span data-ttu-id="a0bbd-123">所有F#数组的类型都是 <xref:System.Array?displayProperty=nameWithType> .NET Framework 类型。</span><span class="sxs-lookup"><span data-stu-id="a0bbd-123">The type of all F# arrays is the .NET Framework type <xref:System.Array?displayProperty=nameWithType>.</span></span> <span data-ttu-id="a0bbd-124">因此， F#数组支持 <xref:System.Array?displayProperty=nameWithType> 中提供的所有功能。</span><span class="sxs-lookup"><span data-stu-id="a0bbd-124">Therefore, F# arrays support all the functionality available in <xref:System.Array?displayProperty=nameWithType>.</span></span>

<span data-ttu-id="a0bbd-125">库模块[`Microsoft.FSharp.Collections.Array`](https://msdn.microsoft.com/library/0cda8040-9396-40dd-8dcd-cf48542165a1)支持对一维数组进行的操作。</span><span class="sxs-lookup"><span data-stu-id="a0bbd-125">The library module [`Microsoft.FSharp.Collections.Array`](https://msdn.microsoft.com/library/0cda8040-9396-40dd-8dcd-cf48542165a1) supports operations on one-dimensional arrays.</span></span> <span data-ttu-id="a0bbd-126">模块 `Array2D`、`Array3D` 和 `Array4D` 包含支持对两个、三个和四个维度的数组进行操作的函数。</span><span class="sxs-lookup"><span data-stu-id="a0bbd-126">The modules `Array2D`, `Array3D`, and `Array4D` contain functions that support operations on arrays of two, three, and four dimensions, respectively.</span></span> <span data-ttu-id="a0bbd-127">您可以使用 <xref:System.Array?displayProperty=nameWithType> 创建秩大于四的数组。</span><span class="sxs-lookup"><span data-stu-id="a0bbd-127">You can create arrays of rank greater than four by using <xref:System.Array?displayProperty=nameWithType>.</span></span>

### <a name="simple-functions"></a><span data-ttu-id="a0bbd-128">简单函数</span><span class="sxs-lookup"><span data-stu-id="a0bbd-128">Simple Functions</span></span>

<span data-ttu-id="a0bbd-129">[`Array.get`](https://msdn.microsoft.com/library/dd93e85d-7e80-4d76-8de0-b6d45bcf07bc)获取元素。</span><span class="sxs-lookup"><span data-stu-id="a0bbd-129">[`Array.get`](https://msdn.microsoft.com/library/dd93e85d-7e80-4d76-8de0-b6d45bcf07bc) gets an element.</span></span> <span data-ttu-id="a0bbd-130">[`Array.length`](https://msdn.microsoft.com/library/0d775b6a-4a8f-4bd1-83e5-843b3251725f)提供数组的长度。</span><span class="sxs-lookup"><span data-stu-id="a0bbd-130">[`Array.length`](https://msdn.microsoft.com/library/0d775b6a-4a8f-4bd1-83e5-843b3251725f) gives the length of an array.</span></span> <span data-ttu-id="a0bbd-131">[`Array.set`](https://msdn.microsoft.com/library/847edc0d-4dc5-4a39-98c7-d4320c60e790)将元素设置为指定值。</span><span class="sxs-lookup"><span data-stu-id="a0bbd-131">[`Array.set`](https://msdn.microsoft.com/library/847edc0d-4dc5-4a39-98c7-d4320c60e790) sets an element to a specified value.</span></span> <span data-ttu-id="a0bbd-132">下面的代码示例阐释了这些函数的用法。</span><span class="sxs-lookup"><span data-stu-id="a0bbd-132">The following code example illustrates the use of these functions.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet9.fs)]

<span data-ttu-id="a0bbd-133">输出如下所示。</span><span class="sxs-lookup"><span data-stu-id="a0bbd-133">The output is as follows.</span></span>

```console
0 1 2 3 4 5 6 7 8 9
```

### <a name="functions-that-create-arrays"></a><span data-ttu-id="a0bbd-134">创建数组的函数</span><span class="sxs-lookup"><span data-stu-id="a0bbd-134">Functions That Create Arrays</span></span>

<span data-ttu-id="a0bbd-135">多个函数创建数组，无需现有数组。</span><span class="sxs-lookup"><span data-stu-id="a0bbd-135">Several functions create arrays without requiring an existing array.</span></span> <span data-ttu-id="a0bbd-136">[`Array.empty`](https://msdn.microsoft.com/library/c3694b92-1c16-4c54-9bf2-fe398fadce32)创建不包含任何元素的新数组。</span><span class="sxs-lookup"><span data-stu-id="a0bbd-136">[`Array.empty`](https://msdn.microsoft.com/library/c3694b92-1c16-4c54-9bf2-fe398fadce32) creates a new array that does not contain any elements.</span></span> <span data-ttu-id="a0bbd-137">[`Array.create`](https://msdn.microsoft.com/library/e848c8d6-1142-4080-9727-8dacc26066be)创建一个指定大小的数组，并将所有元素设置为提供的值。</span><span class="sxs-lookup"><span data-stu-id="a0bbd-137">[`Array.create`](https://msdn.microsoft.com/library/e848c8d6-1142-4080-9727-8dacc26066be) creates an array of a specified size and sets all the elements to provided values.</span></span> <span data-ttu-id="a0bbd-138">[`Array.init`](https://msdn.microsoft.com/library/ee898089-63b0-40aa-910c-5ae7e32f6665)创建一个数组，给定一个维度和函数来生成元素。</span><span class="sxs-lookup"><span data-stu-id="a0bbd-138">[`Array.init`](https://msdn.microsoft.com/library/ee898089-63b0-40aa-910c-5ae7e32f6665) creates an array, given a dimension and a function to generate the elements.</span></span> <span data-ttu-id="a0bbd-139">[`Array.zeroCreate`](https://msdn.microsoft.com/library/fa5b8e7a-1b5b-411c-8622-b58d7a14d3b2)创建一个数组，其中所有元素都初始化为数组的类型的零值。</span><span class="sxs-lookup"><span data-stu-id="a0bbd-139">[`Array.zeroCreate`](https://msdn.microsoft.com/library/fa5b8e7a-1b5b-411c-8622-b58d7a14d3b2) creates an array in which all the elements are initialized to the zero value for the array's type.</span></span> <span data-ttu-id="a0bbd-140">下面的代码演示了这些函数。</span><span class="sxs-lookup"><span data-stu-id="a0bbd-140">The following code demonstrates these functions.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet91.fs)]

<span data-ttu-id="a0bbd-141">输出如下所示。</span><span class="sxs-lookup"><span data-stu-id="a0bbd-141">The output is as follows.</span></span>

```console
Length of empty array: 0
Area of floats set to 5.0: [|5.0; 5.0; 5.0; 5.0; 5.0; 5.0; 5.0; 5.0; 5.0; 5.0|]
Array of squares: [|0; 1; 4; 9; 16; 25; 36; 49; 64; 81|]
```

<span data-ttu-id="a0bbd-142">[`Array.copy`](https://msdn.microsoft.com/library/9d0202f1-1ea0-475e-9d66-4f8ccc3c5b5f)创建一个新数组，其中包含从现有数组中复制的元素。</span><span class="sxs-lookup"><span data-stu-id="a0bbd-142">[`Array.copy`](https://msdn.microsoft.com/library/9d0202f1-1ea0-475e-9d66-4f8ccc3c5b5f) creates a new array that contains elements that are copied from an existing array.</span></span> <span data-ttu-id="a0bbd-143">请注意，副本是一个浅表复制，这意味着，如果元素类型为引用类型，则仅复制引用，而不复制基础对象。</span><span class="sxs-lookup"><span data-stu-id="a0bbd-143">Note that the copy is a shallow copy, which means that if the element type is a reference type, only the reference is copied, not the underlying object.</span></span> <span data-ttu-id="a0bbd-144">下面的代码示例阐释了这一点。</span><span class="sxs-lookup"><span data-stu-id="a0bbd-144">The following code example illustrates this.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet11.fs)]

<span data-ttu-id="a0bbd-145">上述代码的输出如下所示：</span><span class="sxs-lookup"><span data-stu-id="a0bbd-145">The output of the preceding code is as follows:</span></span>

```console
[|Test1; Test2; |]
[|; Test2; |]
```

<span data-ttu-id="a0bbd-146">字符串 `Test1` 仅出现在第一个数组中，因为创建新元素的操作会覆盖 `firstArray` 中的引用，但不会影响对仍存在于 `secondArray` 中的空字符串的原始引用。</span><span class="sxs-lookup"><span data-stu-id="a0bbd-146">The string `Test1` appears only in the first array because the operation of creating a new element overwrites the reference in `firstArray` but does not affect the original reference to an empty string that is still present in `secondArray`.</span></span> <span data-ttu-id="a0bbd-147">字符串 `Test2` 出现在两个数组中，因为 <xref:System.Text.StringBuilder?displayProperty=nameWithType> 类型上的 `Insert` 操作会影响这两个数组中引用的基础 <xref:System.Text.StringBuilder?displayProperty=nameWithType> 对象。</span><span class="sxs-lookup"><span data-stu-id="a0bbd-147">The string `Test2` appears in both arrays because the `Insert` operation on the <xref:System.Text.StringBuilder?displayProperty=nameWithType> type affects the underlying <xref:System.Text.StringBuilder?displayProperty=nameWithType> object, which is referenced in both arrays.</span></span>

<span data-ttu-id="a0bbd-148">[`Array.sub`](https://msdn.microsoft.com/library/40fb12ba-41d7-4ef0-b33a-56727deeef9d)从数组的子范围生成新的数组。</span><span class="sxs-lookup"><span data-stu-id="a0bbd-148">[`Array.sub`](https://msdn.microsoft.com/library/40fb12ba-41d7-4ef0-b33a-56727deeef9d) generates a new array from a subrange of an array.</span></span> <span data-ttu-id="a0bbd-149">可以通过提供起始索引和长度来指定子范围。</span><span class="sxs-lookup"><span data-stu-id="a0bbd-149">You specify the subrange by providing the starting index and the length.</span></span> <span data-ttu-id="a0bbd-150">以下代码演示了 `Array.sub` 的用法。</span><span class="sxs-lookup"><span data-stu-id="a0bbd-150">The following code demonstrates the use of `Array.sub`.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet12.fs)]

<span data-ttu-id="a0bbd-151">输出显示子数组从元素5开始，包含10个元素。</span><span class="sxs-lookup"><span data-stu-id="a0bbd-151">The output shows that the subarray starts at element 5 and contains 10 elements.</span></span>

```console
[|5; 6; 7; 8; 9; 10; 11; 12; 13; 14|]
```

<span data-ttu-id="a0bbd-152">[`Array.append`](https://msdn.microsoft.com/library/08836310-5036-4474-b9a2-2c73e2293911)通过组合两个现有数组来创建新的数组。</span><span class="sxs-lookup"><span data-stu-id="a0bbd-152">[`Array.append`](https://msdn.microsoft.com/library/08836310-5036-4474-b9a2-2c73e2293911) creates a new array by combining two existing arrays.</span></span>

<span data-ttu-id="a0bbd-153">下面的代码演示了**数组 append**。</span><span class="sxs-lookup"><span data-stu-id="a0bbd-153">The following code demonstrates **Array.append**.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet13.fs)]

<span data-ttu-id="a0bbd-154">上述代码的输出如下所示。</span><span class="sxs-lookup"><span data-stu-id="a0bbd-154">The output of the preceding code is as follows.</span></span>

```console
[|1; 2; 3; 4; 5; 6|]
```

<span data-ttu-id="a0bbd-155">[`Array.choose`](https://msdn.microsoft.com/library/f5c8a5e2-637f-44d4-b35c-be96a6618b09)选择要包含在新数组中的数组元素。</span><span class="sxs-lookup"><span data-stu-id="a0bbd-155">[`Array.choose`](https://msdn.microsoft.com/library/f5c8a5e2-637f-44d4-b35c-be96a6618b09) selects elements of an array to include in a new array.</span></span> <span data-ttu-id="a0bbd-156">下面的代码演示 `Array.choose`。</span><span class="sxs-lookup"><span data-stu-id="a0bbd-156">The following code demonstrates `Array.choose`.</span></span> <span data-ttu-id="a0bbd-157">请注意，数组的元素类型不必与选项类型中返回的值的类型相匹配。</span><span class="sxs-lookup"><span data-stu-id="a0bbd-157">Note that the element type of the array does not have to match the type of the value returned in the option type.</span></span> <span data-ttu-id="a0bbd-158">在此示例中，元素类型是 `int` 的，并且选项是多项式函数的结果，`elem*elem - 1` 作为浮点数。</span><span class="sxs-lookup"><span data-stu-id="a0bbd-158">In this example, the element type is `int` and the option is the result of a polynomial function, `elem*elem - 1`, as a floating point number.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet14.fs)]

<span data-ttu-id="a0bbd-159">上述代码的输出如下所示。</span><span class="sxs-lookup"><span data-stu-id="a0bbd-159">The output of the preceding code is as follows.</span></span>

```console
[|3.0; 15.0; 35.0; 63.0; 99.0|]
```

<span data-ttu-id="a0bbd-160">[`Array.collect`](https://msdn.microsoft.com/library/c3b60c3b-9455-48c9-bc2b-e88f0434342a)在现有数组的每个数组元素上运行指定函数，然后收集该函数生成的元素，并将它们合并到新数组中。</span><span class="sxs-lookup"><span data-stu-id="a0bbd-160">[`Array.collect`](https://msdn.microsoft.com/library/c3b60c3b-9455-48c9-bc2b-e88f0434342a) runs a specified function on each array element of an existing array and then collects the elements generated by the function and combines them into a new array.</span></span> <span data-ttu-id="a0bbd-161">下面的代码演示 `Array.collect`。</span><span class="sxs-lookup"><span data-stu-id="a0bbd-161">The following code demonstrates `Array.collect`.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet15.fs)]

<span data-ttu-id="a0bbd-162">上述代码的输出如下所示。</span><span class="sxs-lookup"><span data-stu-id="a0bbd-162">The output of the preceding code is as follows.</span></span>

```console
[|0; 1; 0; 1; 2; 3; 4; 5; 0; 1; 2; 3; 4; 5; 6; 7; 8; 9; 10|]
```

<span data-ttu-id="a0bbd-163">[`Array.concat`](https://msdn.microsoft.com/library/f7219b79-1ec8-4a25-96b1-edbedb358302)采用一系列数组，并将它们合并到一个数组中。</span><span class="sxs-lookup"><span data-stu-id="a0bbd-163">[`Array.concat`](https://msdn.microsoft.com/library/f7219b79-1ec8-4a25-96b1-edbedb358302) takes a sequence of arrays and combines them into a single array.</span></span> <span data-ttu-id="a0bbd-164">下面的代码演示 `Array.concat`。</span><span class="sxs-lookup"><span data-stu-id="a0bbd-164">The following code demonstrates `Array.concat`.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet16.fs)]

<span data-ttu-id="a0bbd-165">上述代码的输出如下所示。</span><span class="sxs-lookup"><span data-stu-id="a0bbd-165">The output of the preceding code is as follows.</span></span>

```console
[|(1, 1, 1); (1, 2, 2); (1, 3, 3); (2, 1, 2); (2, 2, 4); (2, 3, 6); (3, 1, 3);
(3, 2, 6); (3, 3, 9)|]
```

<span data-ttu-id="a0bbd-166">[`Array.filter`](https://msdn.microsoft.com/library/b885b214-47fc-4639-9664-b8c183a39ede)采用布尔条件函数并生成一个新数组，该数组仅包含其条件为 true 的输入数组中的元素。</span><span class="sxs-lookup"><span data-stu-id="a0bbd-166">[`Array.filter`](https://msdn.microsoft.com/library/b885b214-47fc-4639-9664-b8c183a39ede) takes a Boolean condition function and generates a new array that contains only those elements from the input array for which the condition is true.</span></span> <span data-ttu-id="a0bbd-167">下面的代码演示 `Array.filter`。</span><span class="sxs-lookup"><span data-stu-id="a0bbd-167">The following code demonstrates `Array.filter`.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet17.fs)]

<span data-ttu-id="a0bbd-168">上述代码的输出如下所示。</span><span class="sxs-lookup"><span data-stu-id="a0bbd-168">The output of the preceding code is as follows.</span></span>

```console
[|2; 4; 6; 8; 10|]
```

<span data-ttu-id="a0bbd-169">[`Array.rev`](https://msdn.microsoft.com/library/1bbf822c-763b-4794-af21-97d2e48ef709)通过反转现有数组的顺序生成新的数组。</span><span class="sxs-lookup"><span data-stu-id="a0bbd-169">[`Array.rev`](https://msdn.microsoft.com/library/1bbf822c-763b-4794-af21-97d2e48ef709) generates a new array by reversing the order of an existing array.</span></span> <span data-ttu-id="a0bbd-170">下面的代码演示 `Array.rev`。</span><span class="sxs-lookup"><span data-stu-id="a0bbd-170">The following code demonstrates `Array.rev`.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet18.fs)]

<span data-ttu-id="a0bbd-171">上述代码的输出如下所示。</span><span class="sxs-lookup"><span data-stu-id="a0bbd-171">The output of the preceding code is as follows.</span></span>

```console
"Hello world!"
```

<span data-ttu-id="a0bbd-172">您可以轻松地组合使用管道运算符（`|>`）转换数组的数组模块中的函数，如下面的示例中所示。</span><span class="sxs-lookup"><span data-stu-id="a0bbd-172">You can easily combine functions in the array module that transform arrays by using the pipeline operator (`|>`), as shown in the following example.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet19.fs)]

<span data-ttu-id="a0bbd-173">输出为</span><span class="sxs-lookup"><span data-stu-id="a0bbd-173">The output is</span></span>

```console
[|100; 36; 16; 4|]
```

### <a name="multidimensional-arrays"></a><span data-ttu-id="a0bbd-174">多维数组</span><span class="sxs-lookup"><span data-stu-id="a0bbd-174">Multidimensional Arrays</span></span>

<span data-ttu-id="a0bbd-175">可以创建多维数组，但没有用于写入多维数组文本的语法。</span><span class="sxs-lookup"><span data-stu-id="a0bbd-175">A multidimensional array can be created, but there is no syntax for writing a multidimensional array literal.</span></span> <span data-ttu-id="a0bbd-176">使用运算符[`array2D`](https://msdn.microsoft.com/library/1d52503d-2990-49fc-8fd3-6b0e508aa236)从数组元素序列序列创建数组。</span><span class="sxs-lookup"><span data-stu-id="a0bbd-176">Use the operator [`array2D`](https://msdn.microsoft.com/library/1d52503d-2990-49fc-8fd3-6b0e508aa236) to create an array from a sequence of sequences of array elements.</span></span> <span data-ttu-id="a0bbd-177">序列可以是数组或列表文本。</span><span class="sxs-lookup"><span data-stu-id="a0bbd-177">The sequences can be array or list literals.</span></span> <span data-ttu-id="a0bbd-178">例如，下面的代码创建一个二维数组。</span><span class="sxs-lookup"><span data-stu-id="a0bbd-178">For example, the following code creates a two-dimensional array.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet20.fs)]

<span data-ttu-id="a0bbd-179">您还可以使用函数[`Array2D.init`](https://msdn.microsoft.com/library/9de07e95-bc21-4927-b5b4-08fdec882c7b)来初始化两个维度的数组，并且类似的函数可用于三个和四个维度的数组。</span><span class="sxs-lookup"><span data-stu-id="a0bbd-179">You can also use the function [`Array2D.init`](https://msdn.microsoft.com/library/9de07e95-bc21-4927-b5b4-08fdec882c7b) to initialize arrays of two dimensions, and similar functions are available for arrays of three and four dimensions.</span></span> <span data-ttu-id="a0bbd-180">这些函数采用用于创建元素的函数。</span><span class="sxs-lookup"><span data-stu-id="a0bbd-180">These functions take a function that is used to create the elements.</span></span> <span data-ttu-id="a0bbd-181">若要创建一个二维数组，其中包含设置为初始值的元素，而不是指定函数，请使用[`Array2D.create`](https://msdn.microsoft.com/library/36c9d980-b241-4a20-bc64-bcfa0205d804)函数，该函数也可用于最多四个维度的数组。</span><span class="sxs-lookup"><span data-stu-id="a0bbd-181">To create a two-dimensional array that contains elements set to an initial value instead of specifying a function, use the [`Array2D.create`](https://msdn.microsoft.com/library/36c9d980-b241-4a20-bc64-bcfa0205d804) function, which is also available for arrays up to four dimensions.</span></span> <span data-ttu-id="a0bbd-182">下面的代码示例首先演示如何创建包含所需元素的数组数组，然后使用 `Array2D.init` 生成所需的二维数组。</span><span class="sxs-lookup"><span data-stu-id="a0bbd-182">The following code example first shows how to create an array of arrays that contain the desired elements, and then uses `Array2D.init` to generate the desired two-dimensional array.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet21.fs)]

<span data-ttu-id="a0bbd-183">秩为4的数组支持数组索引和切片语法。</span><span class="sxs-lookup"><span data-stu-id="a0bbd-183">Array indexing and slicing syntax is supported for arrays up to rank 4.</span></span> <span data-ttu-id="a0bbd-184">当在多个维度中指定索引时，可以使用逗号分隔索引，如以下代码示例中所示。</span><span class="sxs-lookup"><span data-stu-id="a0bbd-184">When you specify an index in multiple dimensions, you use commas to separate the indexes, as illustrated in the following code example.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet22.fs)]

<span data-ttu-id="a0bbd-185">二维数组的类型作为 `<type>[,]` （例如，`int[,]`、`double[,]`）写出，而将三维数组的类型作为 `<type>[,,]` 编写，依此类推，依此类推数组的数组。</span><span class="sxs-lookup"><span data-stu-id="a0bbd-185">The type of a two-dimensional array is written out as `<type>[,]` (for example, `int[,]`, `double[,]`), and the type of a three-dimensional array is written as `<type>[,,]`, and so on for arrays of higher dimensions.</span></span>

<span data-ttu-id="a0bbd-186">对于多维数组，只能使用适用于一维数组的函数子集。</span><span class="sxs-lookup"><span data-stu-id="a0bbd-186">Only a subset of the functions available for one-dimensional arrays is also available for multidimensional arrays.</span></span> <span data-ttu-id="a0bbd-187">有关详细信息，请参阅[`Collections.Array Module`](https://msdn.microsoft.com/visualfsharpdocs/conceptual/collections.array-module-%5bfsharp%5d)、 [`Collections.Array2D Module`](https://msdn.microsoft.com/visualfsharpdocs/conceptual/collections.array2d-module-%5bfsharp%5d)、 [`Collections.Array3D Module`](https://msdn.microsoft.com/visualfsharpdocs/conceptual/collections.array3d-module-%5bfsharp%5d)和[`Collections.Array4D Module`](https://msdn.microsoft.com/visualfsharpdocs/conceptual/collections.array4d-module-%5bfsharp%5d)。</span><span class="sxs-lookup"><span data-stu-id="a0bbd-187">For more information, see [`Collections.Array Module`](https://msdn.microsoft.com/visualfsharpdocs/conceptual/collections.array-module-%5bfsharp%5d), [`Collections.Array2D Module`](https://msdn.microsoft.com/visualfsharpdocs/conceptual/collections.array2d-module-%5bfsharp%5d), [`Collections.Array3D Module`](https://msdn.microsoft.com/visualfsharpdocs/conceptual/collections.array3d-module-%5bfsharp%5d), and [`Collections.Array4D Module`](https://msdn.microsoft.com/visualfsharpdocs/conceptual/collections.array4d-module-%5bfsharp%5d).</span></span>

### <a name="array-slicing-and-multidimensional-arrays"></a><span data-ttu-id="a0bbd-188">数组切片和多维数组</span><span class="sxs-lookup"><span data-stu-id="a0bbd-188">Array Slicing and Multidimensional Arrays</span></span>

<span data-ttu-id="a0bbd-189">在二维数组（矩阵）中，可以通过指定范围并使用通配符（`*`）字符指定整行或多列来提取子矩阵。</span><span class="sxs-lookup"><span data-stu-id="a0bbd-189">In a two-dimensional array (a matrix), you can extract a sub-matrix by specifying ranges and using a wildcard (`*`) character to specify whole rows or columns.</span></span>

```fsharp
// Get rows 1 to N from an NxM matrix (returns a matrix):
matrix.[1.., *]

// Get rows 1 to 3 from a matrix (returns a matrix):
matrix.[1..3, *]

// Get columns 1 to 3 from a matrix (returns a matrix):
matrix.[*, 1..3]

// Get a 3x3 submatrix:
matrix.[1..3, 1..3]
```

<span data-ttu-id="a0bbd-190">从F# 3.1 到，你可以将多维数组分解为相同或较低维度的子。</span><span class="sxs-lookup"><span data-stu-id="a0bbd-190">As of F# 3.1, you can decompose a multidimensional array into subarrays of the same or lower dimension.</span></span> <span data-ttu-id="a0bbd-191">例如，您可以通过指定单个行或列从矩阵获取向量。</span><span class="sxs-lookup"><span data-stu-id="a0bbd-191">For example, you can obtain a vector from a matrix by specifying a single row or column.</span></span>

```fsharp
// Get row 3 from a matrix as a vector:
matrix.[3, *]

// Get column 3 from a matrix as a vector:
matrix.[*, 3]
```

<span data-ttu-id="a0bbd-192">可以将此切片语法用于实现元素访问运算符和重载 `GetSlice` 方法的类型。</span><span class="sxs-lookup"><span data-stu-id="a0bbd-192">You can use this slicing syntax for types that implement the element access operators and overloaded `GetSlice` methods.</span></span> <span data-ttu-id="a0bbd-193">例如，下面的代码创建一个用于包装F#二维数组的矩阵类型，实现一个项属性以提供对数组索引的支持，并实现三个版本的 `GetSlice`。</span><span class="sxs-lookup"><span data-stu-id="a0bbd-193">For example, the following code creates a Matrix type that wraps the F# 2D array, implements an Item property to provide support for array indexing, and implements three versions of `GetSlice`.</span></span> <span data-ttu-id="a0bbd-194">如果可以将此代码用作矩阵类型的模板，则可以使用本部分所述的所有切片操作。</span><span class="sxs-lookup"><span data-stu-id="a0bbd-194">If you can use this code as a template for your matrix types, you can use all the slicing operations that this section describes.</span></span>

```fsharp
type Matrix<'T>(N: int, M: int) =
    let internalArray = Array2D.zeroCreate<'T> N M

    member this.Item
        with get(a: int, b: int) = internalArray.[a, b]
        and set(a: int, b: int) (value:'T) = internalArray.[a, b] <- value

    member this.GetSlice(rowStart: int option, rowFinish : int option, colStart: int option, colFinish : int option) =
        let rowStart =
            match rowStart with
            | Some(v) -> v
            | None -> 0
        let rowFinish =
            match rowFinish with
            | Some(v) -> v
            | None -> internalArray.GetLength(0) - 1
        let colStart =
            match colStart with
            | Some(v) -> v
            | None -> 0
        let colFinish =
            match colFinish with
            | Some(v) -> v
            | None -> internalArray.GetLength(1) - 1
        internalArray.[rowStart..rowFinish, colStart..colFinish]

    member this.GetSlice(row: int, colStart: int option, colFinish: int option) =
        let colStart =
            match colStart with
            | Some(v) -> v
            | None -> 0
        let colFinish =
            match colFinish with
            | Some(v) -> v
            | None -> internalArray.GetLength(1) - 1
        internalArray.[row, colStart..colFinish]

    member this.GetSlice(rowStart: int option, rowFinish: int option, col: int) =
        let rowStart =
            match rowStart with
            | Some(v) -> v
            | None -> 0
        let rowFinish =
            match rowFinish with
            | Some(v) -> v
            | None -> internalArray.GetLength(0) - 1
        internalArray.[rowStart..rowFinish, col]

module test =
    let generateTestMatrix x y =
        let matrix = new Matrix<float>(3, 3)
        for i in 0..2 do
            for j in 0..2 do
                matrix.[i, j] <- float(i) * x - float(j) * y
        matrix

    let test1 = generateTestMatrix 2.3 1.1
    let submatrix = test1.[0..1, 0..1]
    printfn "%A" submatrix

    let firstRow = test1.[0,*]
    let secondRow = test1.[1,*]
    let firstCol = test1.[*,0]
    printfn "%A" firstCol
```

### <a name="boolean-functions-on-arrays"></a><span data-ttu-id="a0bbd-195">数组上的布尔函数</span><span class="sxs-lookup"><span data-stu-id="a0bbd-195">Boolean Functions on Arrays</span></span>

<span data-ttu-id="a0bbd-196">函数在一个或两个数组中分别[`Array.exists`](https://msdn.microsoft.com/library/8e47ad6c-c065-4876-8cb4-ec960ec3e5c9)和[`Array.exists2`](https://msdn.microsoft.com/library/2e384a6a-f99d-4e23-b677-250ffbc1dd8e)测试元素。</span><span class="sxs-lookup"><span data-stu-id="a0bbd-196">The functions [`Array.exists`](https://msdn.microsoft.com/library/8e47ad6c-c065-4876-8cb4-ec960ec3e5c9) and [`Array.exists2`](https://msdn.microsoft.com/library/2e384a6a-f99d-4e23-b677-250ffbc1dd8e) test elements in either one or two arrays, respectively.</span></span> <span data-ttu-id="a0bbd-197">如果有一个元素（或用于 `Array.exists2` 的元素对）满足条件，则这些函数将采用一个测试函数并返回 `true`。</span><span class="sxs-lookup"><span data-stu-id="a0bbd-197">These functions take a test function and return `true` if there is an element (or element pair for `Array.exists2`) that satisfies the condition.</span></span>

<span data-ttu-id="a0bbd-198">下面的代码演示如何使用 `Array.exists` 和 `Array.exists2`。</span><span class="sxs-lookup"><span data-stu-id="a0bbd-198">The following code demonstrates the use of `Array.exists` and `Array.exists2`.</span></span> <span data-ttu-id="a0bbd-199">在这些示例中，通过仅应用一个自变量（在这种情况下为函数参数）来创建新函数。</span><span class="sxs-lookup"><span data-stu-id="a0bbd-199">In these examples, new functions are created by applying only one of the arguments, in these cases, the function argument.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet23.fs)]

<span data-ttu-id="a0bbd-200">上述代码的输出如下所示。</span><span class="sxs-lookup"><span data-stu-id="a0bbd-200">The output of the preceding code is as follows.</span></span>

```console
true
false
false
true
```

<span data-ttu-id="a0bbd-201">同样，函数[`Array.forall`](https://msdn.microsoft.com/library/d88f2cd0-fa7f-45cf-ac15-31eae9086cc4)测试数组，以确定每个元素是否都满足布尔条件。</span><span class="sxs-lookup"><span data-stu-id="a0bbd-201">Similarly, the function [`Array.forall`](https://msdn.microsoft.com/library/d88f2cd0-fa7f-45cf-ac15-31eae9086cc4) tests an array to determine whether every element satisfies a Boolean condition.</span></span> <span data-ttu-id="a0bbd-202">变体[`Array.forall2`](https://msdn.microsoft.com/library/c68f61a1-030c-4024-b705-c4768b6c96b9)通过使用布尔函数执行相同的操作，该函数涉及两个长度相等的数组的元素。</span><span class="sxs-lookup"><span data-stu-id="a0bbd-202">The variation [`Array.forall2`](https://msdn.microsoft.com/library/c68f61a1-030c-4024-b705-c4768b6c96b9) does the same thing by using a Boolean function that involves elements of two arrays of equal length.</span></span> <span data-ttu-id="a0bbd-203">下面的代码阐释了这些函数的用法。</span><span class="sxs-lookup"><span data-stu-id="a0bbd-203">The following code illustrates the use of these functions.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet24.fs)]

<span data-ttu-id="a0bbd-204">这些示例的输出如下所示。</span><span class="sxs-lookup"><span data-stu-id="a0bbd-204">The output for these examples is as follows.</span></span>

```console
false
true
true
false
```

### <a name="searching-arrays"></a><span data-ttu-id="a0bbd-205">搜索数组</span><span class="sxs-lookup"><span data-stu-id="a0bbd-205">Searching Arrays</span></span>

<span data-ttu-id="a0bbd-206">[`Array.find`](https://msdn.microsoft.com/library/db6d920a-de19-4520-85a4-d83de77c1b33)采用布尔函数并返回函数为其返回 `true` 的第一个元素; 如果找不到满足条件的元素，则引发 <xref:System.Collections.Generic.KeyNotFoundException?displayProperty=nameWithType>。</span><span class="sxs-lookup"><span data-stu-id="a0bbd-206">[`Array.find`](https://msdn.microsoft.com/library/db6d920a-de19-4520-85a4-d83de77c1b33) takes a Boolean function and returns the first element for which the function returns `true`, or raises a <xref:System.Collections.Generic.KeyNotFoundException?displayProperty=nameWithType> if no element that satisfies the condition is found.</span></span> <span data-ttu-id="a0bbd-207">[`Array.findIndex`](https://msdn.microsoft.com/library/5ae3a8f9-7b8f-44ea-a740-d5700f4d899f)类似于 `Array.find`，但它返回元素的索引，而不是元素本身。</span><span class="sxs-lookup"><span data-stu-id="a0bbd-207">[`Array.findIndex`](https://msdn.microsoft.com/library/5ae3a8f9-7b8f-44ea-a740-d5700f4d899f) is like `Array.find`, except that it returns the index of the element instead of the element itself.</span></span>

<span data-ttu-id="a0bbd-208">下面的代码使用 `Array.find` 和 `Array.findIndex` 来查找同时为完全方形和完全相同的多维数据集的数字。</span><span class="sxs-lookup"><span data-stu-id="a0bbd-208">The following code uses `Array.find` and `Array.findIndex` to locate a number that is both a perfect square and perfect cube.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet25.fs)]

<span data-ttu-id="a0bbd-209">输出如下所示。</span><span class="sxs-lookup"><span data-stu-id="a0bbd-209">The output is as follows.</span></span>

```console
The first element that is both a square and a cube is 64 and its index is 62.
```

<span data-ttu-id="a0bbd-210">[`Array.tryFind`](https://msdn.microsoft.com/library/7bd65f6c-df77-454c-ac3a-6f7baecec9d9)类似于 `Array.find`，但其结果是选项类型，如果未找到任何元素，则它将返回 `None`。</span><span class="sxs-lookup"><span data-stu-id="a0bbd-210">[`Array.tryFind`](https://msdn.microsoft.com/library/7bd65f6c-df77-454c-ac3a-6f7baecec9d9) is like `Array.find`, except that its result is an option type, and it returns `None` if no element is found.</span></span> <span data-ttu-id="a0bbd-211">如果不知道匹配的元素是否在数组中，则应使用 `Array.tryFind` 而不是 `Array.find`。</span><span class="sxs-lookup"><span data-stu-id="a0bbd-211">`Array.tryFind` should be used instead of `Array.find` when you do not know whether a matching element is in the array.</span></span> <span data-ttu-id="a0bbd-212">同样， [`Array.tryFindIndex`](https://msdn.microsoft.com/library/da82f7fe-95e9-4fd5-a924-cd3c9d10618a)类似于[`Array.findIndex`](https://msdn.microsoft.com/library/5ae3a8f9-7b8f-44ea-a740-d5700f4d899f) ，只不过选项类型是返回值。</span><span class="sxs-lookup"><span data-stu-id="a0bbd-212">Similarly, [`Array.tryFindIndex`](https://msdn.microsoft.com/library/da82f7fe-95e9-4fd5-a924-cd3c9d10618a) is like [`Array.findIndex`](https://msdn.microsoft.com/library/5ae3a8f9-7b8f-44ea-a740-d5700f4d899f) except that the option type is the return value.</span></span> <span data-ttu-id="a0bbd-213">如果未找到元素，则 `None` 选项。</span><span class="sxs-lookup"><span data-stu-id="a0bbd-213">If no element is found, the option is `None`.</span></span>

<span data-ttu-id="a0bbd-214">以下代码演示了 `Array.tryFind` 的用法。</span><span class="sxs-lookup"><span data-stu-id="a0bbd-214">The following code demonstrates the use of `Array.tryFind`.</span></span> <span data-ttu-id="a0bbd-215">此代码依赖于前面的代码。</span><span class="sxs-lookup"><span data-stu-id="a0bbd-215">This code depends on the previous code.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet26.fs)]

<span data-ttu-id="a0bbd-216">输出如下所示。</span><span class="sxs-lookup"><span data-stu-id="a0bbd-216">The output is as follows.</span></span>

```console
Found an element: 1
Found an element: 729
Failed to find a matching element.
```

<span data-ttu-id="a0bbd-217">如果需要转换某个元素以及查找该元素，请使用[`Array.tryPick`](https://msdn.microsoft.com/library/72d45f85-037b-43a9-97fd-17239f72713e) 。</span><span class="sxs-lookup"><span data-stu-id="a0bbd-217">Use [`Array.tryPick`](https://msdn.microsoft.com/library/72d45f85-037b-43a9-97fd-17239f72713e) when you need to transform an element in addition to finding it.</span></span> <span data-ttu-id="a0bbd-218">结果是函数为其返回转换后的元素作为选项值的第一个元素; 如果未找到这样的元素，则为 `None`。</span><span class="sxs-lookup"><span data-stu-id="a0bbd-218">The result is the first element for which the function returns the transformed element as an option value, or `None` if no such element is found.</span></span>

<span data-ttu-id="a0bbd-219">以下代码显示了 `Array.tryPick` 的用法。</span><span class="sxs-lookup"><span data-stu-id="a0bbd-219">The following code shows the use of `Array.tryPick`.</span></span> <span data-ttu-id="a0bbd-220">在这种情况下，不是 lambda 表达式，而是定义了若干本地 helper 函数以简化代码。</span><span class="sxs-lookup"><span data-stu-id="a0bbd-220">In this case, instead of a lambda expression, several local helper functions are defined to simplify the code.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet27.fs)]

<span data-ttu-id="a0bbd-221">输出如下所示。</span><span class="sxs-lookup"><span data-stu-id="a0bbd-221">The output is as follows.</span></span>

```console
Found an element 1 with square root 1 and cube root 1.
Found an element 64 with square root 8 and cube root 4.
Found an element 729 with square root 27 and cube root 9.
Found an element 4096 with square root 64 and cube root 16.
Did not find an element that is both a perfect square and a perfect cube.
```

### <a name="performing-computations-on-arrays"></a><span data-ttu-id="a0bbd-222">对数组执行计算</span><span class="sxs-lookup"><span data-stu-id="a0bbd-222">Performing Computations on Arrays</span></span>

<span data-ttu-id="a0bbd-223">[@No__t_1](https://msdn.microsoft.com/library/7029f2b9-91ea-41cb-be1b-466a5a0db20e)函数返回数组中每个元素的平均值。</span><span class="sxs-lookup"><span data-stu-id="a0bbd-223">The [`Array.average`](https://msdn.microsoft.com/library/7029f2b9-91ea-41cb-be1b-466a5a0db20e) function returns the average of each element in an array.</span></span> <span data-ttu-id="a0bbd-224">它限制为支持完全除以整数的元素类型，包括浮点类型，但不支持整数类型。</span><span class="sxs-lookup"><span data-stu-id="a0bbd-224">It is limited to element types that support exact division by an integer, which includes floating point types but not integral types.</span></span> <span data-ttu-id="a0bbd-225">[@No__t_1](https://msdn.microsoft.com/library/e9d64609-06a3-48f0-bc07-226ab0f85c54)函数返回对每个元素调用函数的结果的平均值。</span><span class="sxs-lookup"><span data-stu-id="a0bbd-225">The [`Array.averageBy`](https://msdn.microsoft.com/library/e9d64609-06a3-48f0-bc07-226ab0f85c54) function returns the average of the results of calling a function on each element.</span></span> <span data-ttu-id="a0bbd-226">对于整型类型的数组，可以使用 `Array.averageBy`，并使函数将每个元素转换为浮点类型进行计算。</span><span class="sxs-lookup"><span data-stu-id="a0bbd-226">For an array of integral type, you can use `Array.averageBy` and have the function convert each element to a floating point type for the computation.</span></span>

<span data-ttu-id="a0bbd-227">如果元素类型支持，则使用[`Array.max`](https://msdn.microsoft.com/library/f03fbda0-fce6-40e2-a85d-79c9d81f710b)或[`Array.min`](https://msdn.microsoft.com/library/d6b3da5f-bac0-4355-9846-4b72d95bc3fd)获取最大或最小元素。</span><span class="sxs-lookup"><span data-stu-id="a0bbd-227">Use [`Array.max`](https://msdn.microsoft.com/library/f03fbda0-fce6-40e2-a85d-79c9d81f710b) or [`Array.min`](https://msdn.microsoft.com/library/d6b3da5f-bac0-4355-9846-4b72d95bc3fd) to get the maximum or minimum element, if the element type supports it.</span></span> <span data-ttu-id="a0bbd-228">同样， [`Array.maxBy`](https://msdn.microsoft.com/library/18dbe7c5-482e-4766-8e01-12a76f847045)和[`Array.minBy`](https://msdn.microsoft.com/library/24091583-be78-4cc9-9fab-de6d7506af4f)允许先执行函数，也许是转换为支持比较的类型。</span><span class="sxs-lookup"><span data-stu-id="a0bbd-228">Similarly, [`Array.maxBy`](https://msdn.microsoft.com/library/18dbe7c5-482e-4766-8e01-12a76f847045) and [`Array.minBy`](https://msdn.microsoft.com/library/24091583-be78-4cc9-9fab-de6d7506af4f) allow a function to be executed first, perhaps to transform to a type that supports comparison.</span></span>

<span data-ttu-id="a0bbd-229">[`Array.sum`](https://msdn.microsoft.com/library/4ffdb8c8-cd94-4b0b-9e5c-a7c9c17963c2)添加数组的元素， [`Array.sumBy`](https://msdn.microsoft.com/library/41698ba6-1adc-4169-8cc5-7a0e3f8de56b)对每个元素调用一个函数，并将结果添加到一起。</span><span class="sxs-lookup"><span data-stu-id="a0bbd-229">[`Array.sum`](https://msdn.microsoft.com/library/4ffdb8c8-cd94-4b0b-9e5c-a7c9c17963c2) adds the elements of an array, and [`Array.sumBy`](https://msdn.microsoft.com/library/41698ba6-1adc-4169-8cc5-7a0e3f8de56b) calls a function on each element and adds the results together.</span></span>

<span data-ttu-id="a0bbd-230">若要对数组中的每个元素执行函数而不存储返回值，请使用[`Array.iter`](https://msdn.microsoft.com/library/94eba0f1-ecd7-459f-b89f-ed2a2923e516)。</span><span class="sxs-lookup"><span data-stu-id="a0bbd-230">To execute a function on each element in an array without storing the return values, use [`Array.iter`](https://msdn.microsoft.com/library/94eba0f1-ecd7-459f-b89f-ed2a2923e516).</span></span> <span data-ttu-id="a0bbd-231">对于涉及两个相等长度数组的函数，请使用[`Array.iter2`](https://msdn.microsoft.com/library/018aa9b9-f186-4142-be8a-a62462794fdc)。</span><span class="sxs-lookup"><span data-stu-id="a0bbd-231">For a function involving two arrays of equal length, use [`Array.iter2`](https://msdn.microsoft.com/library/018aa9b9-f186-4142-be8a-a62462794fdc).</span></span> <span data-ttu-id="a0bbd-232">如果还需要保留函数结果的数组，请使用[`Array.map`](https://msdn.microsoft.com/library/38cbe824-0480-47be-85fd-df3afdd97a45)或[`Array.map2`](https://msdn.microsoft.com/library/bb7aafe8-4a1f-45b9-92fc-1af9eafbea5c)，这一次对两个数组执行操作。</span><span class="sxs-lookup"><span data-stu-id="a0bbd-232">If you also need to keep an array of the results of the function, use [`Array.map`](https://msdn.microsoft.com/library/38cbe824-0480-47be-85fd-df3afdd97a45) or [`Array.map2`](https://msdn.microsoft.com/library/bb7aafe8-4a1f-45b9-92fc-1af9eafbea5c), which operates on two arrays at a time.</span></span>

<span data-ttu-id="a0bbd-233">变体[`Array.iteri`](https://msdn.microsoft.com/library/8bbe2ed4-ada7-4906-ac3e-cb09f9db6486)和[`Array.iteri2`](https://msdn.microsoft.com/library/c041b91f-6080-45b7-867b-2ed983a90405)允许在计算中涉及元素的索引;[`Array.mapi`](https://msdn.microsoft.com/library/f7e45994-b0a1-49e6-8fb5-5641cea8fde4)和[`Array.mapi2`](https://msdn.microsoft.com/library/5edb33d2-47da-44e1-9290-40c00c47d5b0)也是如此。</span><span class="sxs-lookup"><span data-stu-id="a0bbd-233">The variations [`Array.iteri`](https://msdn.microsoft.com/library/8bbe2ed4-ada7-4906-ac3e-cb09f9db6486) and [`Array.iteri2`](https://msdn.microsoft.com/library/c041b91f-6080-45b7-867b-2ed983a90405) allow the index of the element to be involved in the computation; the same is true for [`Array.mapi`](https://msdn.microsoft.com/library/f7e45994-b0a1-49e6-8fb5-5641cea8fde4) and [`Array.mapi2`](https://msdn.microsoft.com/library/5edb33d2-47da-44e1-9290-40c00c47d5b0).</span></span>

<span data-ttu-id="a0bbd-234">函数[`Array.fold`](https://msdn.microsoft.com/library/5ed9dd3b-3694-4567-94d0-fd9a24474e09)、 [`Array.foldBack`](https://msdn.microsoft.com/library/1121a453-dead-4711-a0ca-cc147752989c)、 [`Array.reduce`](https://msdn.microsoft.com/library/fd62a985-89fe-4f49-a9d4-0c808ac6749d)、 [`Array.reduceBack`](https://msdn.microsoft.com/library/4fdd4cbe-2238-4c5c-b286-597a7e9036f9)、 [`Array.scan`](https://msdn.microsoft.com/library/f6893608-9146-450d-9ebb-a0016803fbb0)和[1](https://msdn.microsoft.com/library/7610f406-7a5c-41db-a0ca-8e2a2a4826ad)执行包含数组的所有元素的算法。</span><span class="sxs-lookup"><span data-stu-id="a0bbd-234">The functions [`Array.fold`](https://msdn.microsoft.com/library/5ed9dd3b-3694-4567-94d0-fd9a24474e09), [`Array.foldBack`](https://msdn.microsoft.com/library/1121a453-dead-4711-a0ca-cc147752989c), [`Array.reduce`](https://msdn.microsoft.com/library/fd62a985-89fe-4f49-a9d4-0c808ac6749d), [`Array.reduceBack`](https://msdn.microsoft.com/library/4fdd4cbe-2238-4c5c-b286-597a7e9036f9), [`Array.scan`](https://msdn.microsoft.com/library/f6893608-9146-450d-9ebb-a0016803fbb0), and [`Array.scanBack`](https://msdn.microsoft.com/library/7610f406-7a5c-41db-a0ca-8e2a2a4826ad) execute algorithms that involve all the elements of an array.</span></span> <span data-ttu-id="a0bbd-235">同样， [`Array.fold2`](https://msdn.microsoft.com/library/5c845087-d041-476e-8cc4-53ae6849ef79)和[`Array.foldBack2`](https://msdn.microsoft.com/library/aa51b405-df20-4c51-9998-a6530f7db862)的变体对两个数组执行计算。</span><span class="sxs-lookup"><span data-stu-id="a0bbd-235">Similarly, the variations [`Array.fold2`](https://msdn.microsoft.com/library/5c845087-d041-476e-8cc4-53ae6849ef79) and [`Array.foldBack2`](https://msdn.microsoft.com/library/aa51b405-df20-4c51-9998-a6530f7db862) perform computations on two arrays.</span></span>

<span data-ttu-id="a0bbd-236">用于执行计算的这些函数对应于[列表模块](https://msdn.microsoft.com/library/a2264ba3-2d45-40dd-9040-4f7aa2ad9788)中具有相同名称的函数。</span><span class="sxs-lookup"><span data-stu-id="a0bbd-236">These functions for performing computations correspond to the functions of the same name in the [List module](https://msdn.microsoft.com/library/a2264ba3-2d45-40dd-9040-4f7aa2ad9788).</span></span> <span data-ttu-id="a0bbd-237">有关用法示例，请参阅[列表](lists.md)。</span><span class="sxs-lookup"><span data-stu-id="a0bbd-237">For usage examples, see [Lists](lists.md).</span></span>

### <a name="modifying-arrays"></a><span data-ttu-id="a0bbd-238">修改数组</span><span class="sxs-lookup"><span data-stu-id="a0bbd-238">Modifying Arrays</span></span>

<span data-ttu-id="a0bbd-239">[`Array.set`](https://msdn.microsoft.com/library/847edc0d-4dc5-4a39-98c7-d4320c60e790)将元素设置为指定值。</span><span class="sxs-lookup"><span data-stu-id="a0bbd-239">[`Array.set`](https://msdn.microsoft.com/library/847edc0d-4dc5-4a39-98c7-d4320c60e790) sets an element to a specified value.</span></span> <span data-ttu-id="a0bbd-240">[`Array.fill`](https://msdn.microsoft.com/library/c83c9886-81d9-44f9-a195-61c7b87f7df2)将数组中的一系列元素设置为指定值。</span><span class="sxs-lookup"><span data-stu-id="a0bbd-240">[`Array.fill`](https://msdn.microsoft.com/library/c83c9886-81d9-44f9-a195-61c7b87f7df2) sets a range of elements in an array to a specified value.</span></span> <span data-ttu-id="a0bbd-241">下面的代码提供了一个 `Array.fill` 的示例。</span><span class="sxs-lookup"><span data-stu-id="a0bbd-241">The following code provides an example of `Array.fill`.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet28.fs)]

<span data-ttu-id="a0bbd-242">输出如下所示。</span><span class="sxs-lookup"><span data-stu-id="a0bbd-242">The output is as follows.</span></span>

```console
[|1; 2; 0; 0; 0; 0; 0; 0; 0; 0; 0; 0; 0; 0; 0; 0; 0; 0; 0; 0; 0; 0; 23; 24; 25|]
```

<span data-ttu-id="a0bbd-243">您可以使用[`Array.blit`](https://msdn.microsoft.com/library/675e13e4-7fb9-4e0d-a5be-a112830de667)将一个数组的子节复制到另一个数组。</span><span class="sxs-lookup"><span data-stu-id="a0bbd-243">You can use [`Array.blit`](https://msdn.microsoft.com/library/675e13e4-7fb9-4e0d-a5be-a112830de667) to copy a subsection of one array to another array.</span></span>

### <a name="converting-to-and-from-other-types"></a><span data-ttu-id="a0bbd-244">与其他类型相互转换</span><span class="sxs-lookup"><span data-stu-id="a0bbd-244">Converting to and from Other Types</span></span>

<span data-ttu-id="a0bbd-245">[`Array.ofList`](https://msdn.microsoft.com/library/e7225239-f561-45a4-b0b5-69a1cdcae78b)从列表创建数组。</span><span class="sxs-lookup"><span data-stu-id="a0bbd-245">[`Array.ofList`](https://msdn.microsoft.com/library/e7225239-f561-45a4-b0b5-69a1cdcae78b) creates an array from a list.</span></span> <span data-ttu-id="a0bbd-246">[`Array.ofSeq`](https://msdn.microsoft.com/library/6bedf5e0-4b22-46da-b09c-6aa09eff220c)从序列创建数组。</span><span class="sxs-lookup"><span data-stu-id="a0bbd-246">[`Array.ofSeq`](https://msdn.microsoft.com/library/6bedf5e0-4b22-46da-b09c-6aa09eff220c) creates an array from a sequence.</span></span> <span data-ttu-id="a0bbd-247">[`Array.toList`](https://msdn.microsoft.com/library/4deff724-0be4-4688-92e7-9d67a1097786)和[`Array.toSeq`](https://msdn.microsoft.com/library/ac28dbab-406c-4fe0-ab08-c1ce5e247af4)从数组类型转换为这些其他集合类型。</span><span class="sxs-lookup"><span data-stu-id="a0bbd-247">[`Array.toList`](https://msdn.microsoft.com/library/4deff724-0be4-4688-92e7-9d67a1097786) and [`Array.toSeq`](https://msdn.microsoft.com/library/ac28dbab-406c-4fe0-ab08-c1ce5e247af4) convert to these other collection types from the array type.</span></span>

### <a name="sorting-arrays"></a><span data-ttu-id="a0bbd-248">排序数组</span><span class="sxs-lookup"><span data-stu-id="a0bbd-248">Sorting Arrays</span></span>

<span data-ttu-id="a0bbd-249">使用[`Array.sort`](https://msdn.microsoft.com/library/c6679075-e7eb-463c-9be5-c89be140c312)通过泛型比较函数对数组进行排序。</span><span class="sxs-lookup"><span data-stu-id="a0bbd-249">Use [`Array.sort`](https://msdn.microsoft.com/library/c6679075-e7eb-463c-9be5-c89be140c312) to sort an array by using the generic comparison function.</span></span> <span data-ttu-id="a0bbd-250">使用[`Array.sortBy`](https://msdn.microsoft.com/library/144498dc-091d-4575-a229-c0bcbd61426b)指定一个函数，该函数通过对键使用泛型比较函数来生成值（称为*键*）进行排序。</span><span class="sxs-lookup"><span data-stu-id="a0bbd-250">Use [`Array.sortBy`](https://msdn.microsoft.com/library/144498dc-091d-4575-a229-c0bcbd61426b) to specify a function that generates a value, referred to as a *key*, to sort by using the generic comparison function on the key.</span></span> <span data-ttu-id="a0bbd-251">如果要提供自定义比较函数，请使用[`Array.sortWith`](https://msdn.microsoft.com/library/699d3638-4244-4f42-8496-45f53d43ce95) 。</span><span class="sxs-lookup"><span data-stu-id="a0bbd-251">Use [`Array.sortWith`](https://msdn.microsoft.com/library/699d3638-4244-4f42-8496-45f53d43ce95) if you want to provide a custom comparison function.</span></span> <span data-ttu-id="a0bbd-252">`Array.sort`、`Array.sortBy` 和 `Array.sortWith` 都作为新数组返回已排序的数组。</span><span class="sxs-lookup"><span data-stu-id="a0bbd-252">`Array.sort`, `Array.sortBy`, and `Array.sortWith` all return the sorted array as a new array.</span></span> <span data-ttu-id="a0bbd-253">变体[`Array.sortInPlace`](https://msdn.microsoft.com/library/36f39947-8a88-4823-9e9b-e9d838d292e0)、 [`Array.sortInPlaceBy`](https://msdn.microsoft.com/library/7fb9d2dd-d461-4c67-8b43-b5c59fc12c3f)和[`Array.sortInPlaceWith`](https://msdn.microsoft.com/library/454f9e11-972d-47a6-a854-8031cb0c7b0b)修改现有数组，而不是返回新数组。</span><span class="sxs-lookup"><span data-stu-id="a0bbd-253">The variations [`Array.sortInPlace`](https://msdn.microsoft.com/library/36f39947-8a88-4823-9e9b-e9d838d292e0), [`Array.sortInPlaceBy`](https://msdn.microsoft.com/library/7fb9d2dd-d461-4c67-8b43-b5c59fc12c3f), and [`Array.sortInPlaceWith`](https://msdn.microsoft.com/library/454f9e11-972d-47a6-a854-8031cb0c7b0b) modify the existing array instead of returning a new one.</span></span>

### <a name="arrays-and-tuples"></a><span data-ttu-id="a0bbd-254">数组和元组</span><span class="sxs-lookup"><span data-stu-id="a0bbd-254">Arrays and Tuples</span></span>

<span data-ttu-id="a0bbd-255">函数[`Array.zip`](https://msdn.microsoft.com/library/23e086b8-b266-4db2-8b68-e88e6a8e2187)和[`Array.unzip`](https://msdn.microsoft.com/library/a529b47c-2e2b-4f79-ad44-c578432d2f48)将元组对的数组转换为数组的元组，反之亦然。</span><span class="sxs-lookup"><span data-stu-id="a0bbd-255">The functions [`Array.zip`](https://msdn.microsoft.com/library/23e086b8-b266-4db2-8b68-e88e6a8e2187) and [`Array.unzip`](https://msdn.microsoft.com/library/a529b47c-2e2b-4f79-ad44-c578432d2f48) convert arrays of tuple pairs to tuples of arrays and vice versa.</span></span> <span data-ttu-id="a0bbd-256">[`Array.zip3`](https://msdn.microsoft.com/library/1745744a-d2ca-4c3e-b825-3f15d9f4000d)和[`Array.unzip3`](https://msdn.microsoft.com/library/bc3e6db0-f334-444f-8c30-813942880677)类似，只不过它们适用于三个元素的元组或三个数组的元组。</span><span class="sxs-lookup"><span data-stu-id="a0bbd-256">[`Array.zip3`](https://msdn.microsoft.com/library/1745744a-d2ca-4c3e-b825-3f15d9f4000d) and [`Array.unzip3`](https://msdn.microsoft.com/library/bc3e6db0-f334-444f-8c30-813942880677) are similar except that they work with tuples of three elements or tuples of three arrays.</span></span>

## <a name="parallel-computations-on-arrays"></a><span data-ttu-id="a0bbd-257">数组上的并行计算</span><span class="sxs-lookup"><span data-stu-id="a0bbd-257">Parallel Computations on Arrays</span></span>

<span data-ttu-id="a0bbd-258">模块[`Array.Parallel`](https://msdn.microsoft.com/library/60f30b77-5af4-4050-9a5c-bcdb3f5cbb09)包含用于对数组执行并行计算的函数。</span><span class="sxs-lookup"><span data-stu-id="a0bbd-258">The module [`Array.Parallel`](https://msdn.microsoft.com/library/60f30b77-5af4-4050-9a5c-bcdb3f5cbb09) contains functions for performing parallel computations on arrays.</span></span> <span data-ttu-id="a0bbd-259">此模块在面向版本4之前的 .NET Framework 版本的应用程序中不可用。</span><span class="sxs-lookup"><span data-stu-id="a0bbd-259">This module is not available in applications that target versions of the .NET Framework prior to version 4.</span></span>

## <a name="see-also"></a><span data-ttu-id="a0bbd-260">请参阅</span><span class="sxs-lookup"><span data-stu-id="a0bbd-260">See also</span></span>

- [<span data-ttu-id="a0bbd-261">F# 语言参考</span><span class="sxs-lookup"><span data-stu-id="a0bbd-261">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="a0bbd-262">F# 类型</span><span class="sxs-lookup"><span data-stu-id="a0bbd-262">F# Types</span></span>](fsharp-types.md)
