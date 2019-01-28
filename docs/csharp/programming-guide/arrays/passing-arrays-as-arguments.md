---
title: 将数组作为参数传递 - C# 编程指南
ms.custom: seodec18
ms.date: 07/05/2018
helpviewer_keywords:
- arrays [C#], passing as arguments
ms.assetid: f3a0971e-c87c-4a1f-8262-bc0a3b712772
ms.openlocfilehash: 1538988c1145a19055074b440f04cbaac4ef7aa7
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54741173"
---
# <a name="passing-arrays-as-arguments-c-programming-guide"></a><span data-ttu-id="5da52-102">将数组作为参数传递（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="5da52-102">Passing arrays as arguments (C# Programming Guide)</span></span>

<span data-ttu-id="5da52-103">数组可以作为实参传递给方法形参。</span><span class="sxs-lookup"><span data-stu-id="5da52-103">Arrays can be passed as arguments to method parameters.</span></span> <span data-ttu-id="5da52-104">由于数组是引用类型，因此方法可以更改元素的值。</span><span class="sxs-lookup"><span data-stu-id="5da52-104">Because arrays are reference types, the method can change the value of the elements.</span></span>

## <a name="passing-single-dimensional-arrays-as-arguments"></a><span data-ttu-id="5da52-105">将一维数组作为参数传递</span><span class="sxs-lookup"><span data-stu-id="5da52-105">Passing single-dimensional arrays as arguments</span></span>

<span data-ttu-id="5da52-106">可将初始化的一维数组传递给方法。</span><span class="sxs-lookup"><span data-stu-id="5da52-106">You can pass an initialized single-dimensional array to a method.</span></span> <span data-ttu-id="5da52-107">例如，下列语句将一个数组发送给了 Print 方法。</span><span class="sxs-lookup"><span data-stu-id="5da52-107">For example, the following statement sends an array to a print method.</span></span>

[!code-csharp[csProgGuideArrays#34](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#34)]

<span data-ttu-id="5da52-108">下面的代码演示 Print 方法的部分实现。</span><span class="sxs-lookup"><span data-stu-id="5da52-108">The following code shows a partial implementation of the print method.</span></span>

[!code-csharp[csProgGuideArrays#33](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#33)]

<span data-ttu-id="5da52-109">可在同一步骤中初始化并传递新数组，如下例所示。</span><span class="sxs-lookup"><span data-stu-id="5da52-109">You can initialize and pass a new array in one step, as is shown in the following example.</span></span>

[!code-csharp[CsProgGuideArrays#35](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#35)]

### <a name="example"></a><span data-ttu-id="5da52-110">示例</span><span class="sxs-lookup"><span data-stu-id="5da52-110">Example</span></span>

<span data-ttu-id="5da52-111">在下面的示例中，先初始化一个字符串数组，然后将其作为参数传递给字符串的 `DisplayArray` 方法。</span><span class="sxs-lookup"><span data-stu-id="5da52-111">In the following example, an array of strings is initialized and passed as an argument to a `DisplayArray` method for strings.</span></span> <span data-ttu-id="5da52-112">该方法将显示数组的元素。</span><span class="sxs-lookup"><span data-stu-id="5da52-112">The method displays the elements of the array.</span></span> <span data-ttu-id="5da52-113">接下来，`ChangeArray` 方法会反转数组元素，然后由 `ChangeArrayElements` 方法修改该数组的前三个元素。</span><span class="sxs-lookup"><span data-stu-id="5da52-113">Next, the `ChangeArray` method reverses the array elements, and then the `ChangeArrayElements` method modifies the first three elements of the array.</span></span> <span data-ttu-id="5da52-114">每个方法返回后，`DisplayArray` 方法会显示按值传递数组不会阻止对数组元素的更改。</span><span class="sxs-lookup"><span data-stu-id="5da52-114">After each method returns, the `DisplayArray` method shows that passing an array by value doesn't prevent changes to the array elements.</span></span>

[!code-csharp[csProgGuideArrays#30](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/ArrayExample.cs)]

## <a name="passing-multidimensional-arrays-as-arguments"></a><span data-ttu-id="5da52-115">将多维数组作为参数传递</span><span class="sxs-lookup"><span data-stu-id="5da52-115">Passing multidimensional arrays as arguments</span></span>

<span data-ttu-id="5da52-116">通过与传递一维数组相同的方式，向方法传递初始化的多维数组。</span><span class="sxs-lookup"><span data-stu-id="5da52-116">You pass an initialized multidimensional array to a method in the same way that you pass a one-dimensional array.</span></span>

[!code-csharp[csProgGuideArrays#41](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#41)]

<span data-ttu-id="5da52-117">下列代码演示了 Print 方法的部分声明（该方法接受将二维数组作为其参数）。</span><span class="sxs-lookup"><span data-stu-id="5da52-117">The following code shows a partial declaration of a print method that accepts a two-dimensional array as its argument.</span></span>

[!code-csharp[csProgGuideArrays#36](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#36)]

<span data-ttu-id="5da52-118">可在一个步骤中初始化并传递新数组，如下例所示：</span><span class="sxs-lookup"><span data-stu-id="5da52-118">You can initialize and pass a new array in one step, as is shown in the following example:</span></span>

[!code-csharp[csProgGuideArrays#32](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#32)]

### <a name="example"></a><span data-ttu-id="5da52-119">示例</span><span class="sxs-lookup"><span data-stu-id="5da52-119">Example</span></span>

<span data-ttu-id="5da52-120">在下列示例中，初始化一个整数的二维数组，并将其传递至 `Print2DArray` 方法。</span><span class="sxs-lookup"><span data-stu-id="5da52-120">In the following example, a two-dimensional array of integers is initialized and passed to the `Print2DArray` method.</span></span> <span data-ttu-id="5da52-121">该方法将显示数组的元素。</span><span class="sxs-lookup"><span data-stu-id="5da52-121">The method displays the elements of the array.</span></span>

[!code-csharp[csProgGuideArrays#31](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#31)]

## <a name="see-also"></a><span data-ttu-id="5da52-122">请参阅</span><span class="sxs-lookup"><span data-stu-id="5da52-122">See also</span></span>

- [<span data-ttu-id="5da52-123">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="5da52-123">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="5da52-124">数组</span><span class="sxs-lookup"><span data-stu-id="5da52-124">Arrays</span></span>](index.md)
- [<span data-ttu-id="5da52-125">一维数组</span><span class="sxs-lookup"><span data-stu-id="5da52-125">Single-Dimensional Arrays</span></span>](single-dimensional-arrays.md)
- [<span data-ttu-id="5da52-126">多维数组</span><span class="sxs-lookup"><span data-stu-id="5da52-126">Multidimensional Arrays</span></span>](multidimensional-arrays.md)
- [<span data-ttu-id="5da52-127">交错数组</span><span class="sxs-lookup"><span data-stu-id="5da52-127">Jagged Arrays</span></span>](jagged-arrays.md)
