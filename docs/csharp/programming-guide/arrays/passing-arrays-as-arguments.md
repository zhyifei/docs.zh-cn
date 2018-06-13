---
title: 将数组作为自变量传递（C# 编程指南）
ms.date: 07/20/2015
helpviewer_keywords:
- arrays [C#], passing as arguments
ms.assetid: f3a0971e-c87c-4a1f-8262-bc0a3b712772
ms.openlocfilehash: d863cdc33a8a1a844aabbea9ba5876614e6e8dba
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33315511"
---
# <a name="passing-arrays-as-arguments-c-programming-guide"></a><span data-ttu-id="c6450-102">将数组作为自变量传递（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="c6450-102">Passing Arrays as Arguments (C# Programming Guide)</span></span>
<span data-ttu-id="c6450-103">数组可以作为实参传递给方法形参。</span><span class="sxs-lookup"><span data-stu-id="c6450-103">Arrays can be passed as arguments to method parameters.</span></span> <span data-ttu-id="c6450-104">由于数组是引用类型，因此方法可以更改元素的值。</span><span class="sxs-lookup"><span data-stu-id="c6450-104">Because arrays are reference types, the method can change the value of the elements.</span></span>  
  
## <a name="passing-single-dimensional-arrays-as-arguments"></a><span data-ttu-id="c6450-105">将一维数组作为参数传递</span><span class="sxs-lookup"><span data-stu-id="c6450-105">Passing Single-Dimensional Arrays As Arguments</span></span>  
 <span data-ttu-id="c6450-106">可将初始化的一维数组传递给方法。</span><span class="sxs-lookup"><span data-stu-id="c6450-106">You can pass an initialized single-dimensional array to a method.</span></span> <span data-ttu-id="c6450-107">例如，下列语句将一个数组发送给了 Print 方法。</span><span class="sxs-lookup"><span data-stu-id="c6450-107">For example, the following statement sends an array to a print method.</span></span>  
  
 [!code-csharp[csProgGuideArrays#34](../../../csharp/programming-guide/arrays/codesnippet/CSharp/passing-arrays-as-arguments_1.cs)]  
  
 <span data-ttu-id="c6450-108">下面的代码演示 Print 方法的部分实现。</span><span class="sxs-lookup"><span data-stu-id="c6450-108">The following code shows a partial implementation of the print method.</span></span>  
  
 [!code-csharp[csProgGuideArrays#33](../../../csharp/programming-guide/arrays/codesnippet/CSharp/passing-arrays-as-arguments_2.cs)]  
  
 <span data-ttu-id="c6450-109">可在同一步骤中初始化并传递新数组，如下例所示。</span><span class="sxs-lookup"><span data-stu-id="c6450-109">You can initialize and pass a new array in one step, as is shown in the following example.</span></span>  
  
 [!code-csharp[CsProgGuideArrays#35](../../../csharp/programming-guide/arrays/codesnippet/CSharp/passing-arrays-as-arguments_3.cs)]  
  
## <a name="example"></a><span data-ttu-id="c6450-110">示例</span><span class="sxs-lookup"><span data-stu-id="c6450-110">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="c6450-111">描述</span><span class="sxs-lookup"><span data-stu-id="c6450-111">Description</span></span>  
 <span data-ttu-id="c6450-112">在下面的示例中，先初始化一个字符串数组，然后将其作为参数传递给字符串的 `PrintArray` 方法。</span><span class="sxs-lookup"><span data-stu-id="c6450-112">In the following example, an array of strings is initialized and passed as an argument to a `PrintArray` method for strings.</span></span> <span data-ttu-id="c6450-113">该方法将显示数组的元素。</span><span class="sxs-lookup"><span data-stu-id="c6450-113">The method displays the elements of the array.</span></span> <span data-ttu-id="c6450-114">然后，调用 `ChangeArray` 和 `ChangeArrayElement` 方法，演示根据值发送数组参数不会阻止对数组元素的更改。</span><span class="sxs-lookup"><span data-stu-id="c6450-114">Next, methods `ChangeArray` and `ChangeArrayElement` are called to demonstrate that sending an array argument by value does not prevent changes to the array elements.</span></span>  
  
### <a name="code"></a><span data-ttu-id="c6450-115">代码</span><span class="sxs-lookup"><span data-stu-id="c6450-115">Code</span></span>  
 [!code-csharp[csProgGuideArrays#30](../../../csharp/programming-guide/arrays/codesnippet/CSharp/passing-arrays-as-arguments_4.cs)]  
  
## <a name="passing-multidimensional-arrays-as-arguments"></a><span data-ttu-id="c6450-116">将多维数组作为参数传递</span><span class="sxs-lookup"><span data-stu-id="c6450-116">Passing Multidimensional Arrays As Arguments</span></span>  
 <span data-ttu-id="c6450-117">通过与传递一维数组相同的方式，向方法传递初始化的多维数组。</span><span class="sxs-lookup"><span data-stu-id="c6450-117">You pass an initialized multidimensional array to a method in the same way that you pass a one-dimensional array.</span></span>  
  
 [!code-csharp[csProgGuideArrays#41](../../../csharp/programming-guide/arrays/codesnippet/CSharp/passing-arrays-as-arguments_5.cs)]  
  
 <span data-ttu-id="c6450-118">下列代码演示了 Print 方法的部分声明（该方法接受将二维数组作为其参数）。</span><span class="sxs-lookup"><span data-stu-id="c6450-118">The following code shows a partial declaration of a print method that accepts a two-dimensional array as its argument.</span></span>  
  
 [!code-csharp[csProgGuideArrays#36](../../../csharp/programming-guide/arrays/codesnippet/CSharp/passing-arrays-as-arguments_6.cs)]  
  
 <span data-ttu-id="c6450-119">可在同一步骤中初始化并传递新数组，如下例所示。</span><span class="sxs-lookup"><span data-stu-id="c6450-119">You can initialize and pass a new array in one step, as is shown in the following example.</span></span>  
  
 [!code-csharp[csProgGuideArrays#32](../../../csharp/programming-guide/arrays/codesnippet/CSharp/passing-arrays-as-arguments_7.cs)]  
  
## <a name="example"></a><span data-ttu-id="c6450-120">示例</span><span class="sxs-lookup"><span data-stu-id="c6450-120">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="c6450-121">描述</span><span class="sxs-lookup"><span data-stu-id="c6450-121">Description</span></span>  
 <span data-ttu-id="c6450-122">在下列示例中，初始化一个整数的二维数组，并将其传递至 `Print2DArray` 方法。</span><span class="sxs-lookup"><span data-stu-id="c6450-122">In the following example, a two-dimensional array of integers is initialized and passed to the `Print2DArray` method.</span></span> <span data-ttu-id="c6450-123">该方法将显示数组的元素。</span><span class="sxs-lookup"><span data-stu-id="c6450-123">The method displays the elements of the array.</span></span>  
  
### <a name="code"></a><span data-ttu-id="c6450-124">代码</span><span class="sxs-lookup"><span data-stu-id="c6450-124">Code</span></span>  
 [!code-csharp[csProgGuideArrays#31](../../../csharp/programming-guide/arrays/codesnippet/CSharp/passing-arrays-as-arguments_8.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="c6450-125">请参阅</span><span class="sxs-lookup"><span data-stu-id="c6450-125">See Also</span></span>  
 [<span data-ttu-id="c6450-126">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="c6450-126">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="c6450-127">数组</span><span class="sxs-lookup"><span data-stu-id="c6450-127">Arrays</span></span>](../../../csharp/programming-guide/arrays/index.md)  
 [<span data-ttu-id="c6450-128">一维数组</span><span class="sxs-lookup"><span data-stu-id="c6450-128">Single-Dimensional Arrays</span></span>](../../../csharp/programming-guide/arrays/single-dimensional-arrays.md)  
 [<span data-ttu-id="c6450-129">多维数组</span><span class="sxs-lookup"><span data-stu-id="c6450-129">Multidimensional Arrays</span></span>](../../../csharp/programming-guide/arrays/multidimensional-arrays.md)  
 [<span data-ttu-id="c6450-130">交错数组</span><span class="sxs-lookup"><span data-stu-id="c6450-130">Jagged Arrays</span></span>](../../../csharp/programming-guide/arrays/jagged-arrays.md)
