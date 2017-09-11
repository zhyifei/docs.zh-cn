---
title: "将数组作为自变量传递（C# 编程指南）"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- arrays [C#], passing as arguments
ms.assetid: f3a0971e-c87c-4a1f-8262-bc0a3b712772
caps.latest.revision: 21
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 5e83c0c119bc1448be76f83416098158c7f5d684
ms.contentlocale: zh-cn
ms.lasthandoff: 07/28/2017

---
# <a name="passing-arrays-as-arguments-c-programming-guide"></a><span data-ttu-id="58213-102">将数组作为自变量传递（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="58213-102">Passing Arrays as Arguments (C# Programming Guide)</span></span>
<span data-ttu-id="58213-103">数组可以作为实参传递给方法形参。</span><span class="sxs-lookup"><span data-stu-id="58213-103">Arrays can be passed as arguments to method parameters.</span></span> <span data-ttu-id="58213-104">由于数组是引用类型，因此方法可以更改元素的值。</span><span class="sxs-lookup"><span data-stu-id="58213-104">Because arrays are reference types, the method can change the value of the elements.</span></span>  
  
## <a name="passing-single-dimensional-arrays-as-arguments"></a><span data-ttu-id="58213-105">将一维数组作为参数传递</span><span class="sxs-lookup"><span data-stu-id="58213-105">Passing Single-Dimensional Arrays As Arguments</span></span>  
 <span data-ttu-id="58213-106">可将初始化的一维数组传递给方法。</span><span class="sxs-lookup"><span data-stu-id="58213-106">You can pass an initialized single-dimensional array to a method.</span></span> <span data-ttu-id="58213-107">例如，下列语句将一个数组发送给了 Print 方法。</span><span class="sxs-lookup"><span data-stu-id="58213-107">For example, the following statement sends an array to a print method.</span></span>  
  
 <span data-ttu-id="58213-108">[!code-cs[csProgGuideArrays#34](../../../csharp/programming-guide/arrays/codesnippet/CSharp/passing-arrays-as-arguments_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="58213-108">[!code-cs[csProgGuideArrays#34](../../../csharp/programming-guide/arrays/codesnippet/CSharp/passing-arrays-as-arguments_1.cs)]</span></span>  
  
 <span data-ttu-id="58213-109">下面的代码演示 Print 方法的部分实现。</span><span class="sxs-lookup"><span data-stu-id="58213-109">The following code shows a partial implementation of the print method.</span></span>  
  
 <span data-ttu-id="58213-110">[!code-cs[csProgGuideArrays#33](../../../csharp/programming-guide/arrays/codesnippet/CSharp/passing-arrays-as-arguments_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="58213-110">[!code-cs[csProgGuideArrays#33](../../../csharp/programming-guide/arrays/codesnippet/CSharp/passing-arrays-as-arguments_2.cs)]</span></span>  
  
 <span data-ttu-id="58213-111">可在同一步骤中初始化并传递新数组，如下例所示。</span><span class="sxs-lookup"><span data-stu-id="58213-111">You can initialize and pass a new array in one step, as is shown in the following example.</span></span>  
  
 <span data-ttu-id="58213-112">[!code-cs[CsProgGuideArrays#35](../../../csharp/programming-guide/arrays/codesnippet/CSharp/passing-arrays-as-arguments_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="58213-112">[!code-cs[CsProgGuideArrays#35](../../../csharp/programming-guide/arrays/codesnippet/CSharp/passing-arrays-as-arguments_3.cs)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="58213-113">示例</span><span class="sxs-lookup"><span data-stu-id="58213-113">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="58213-114">描述</span><span class="sxs-lookup"><span data-stu-id="58213-114">Description</span></span>  
 <span data-ttu-id="58213-115">在下面的示例中，先初始化一个字符串数组，然后将其作为参数传递给字符串的 `PrintArray` 方法。</span><span class="sxs-lookup"><span data-stu-id="58213-115">In the following example, an array of strings is initialized and passed as an argument to a `PrintArray` method for strings.</span></span> <span data-ttu-id="58213-116">该方法将显示数组的元素。</span><span class="sxs-lookup"><span data-stu-id="58213-116">The method displays the elements of the array.</span></span> <span data-ttu-id="58213-117">然后，调用 `ChangeArray` 和 `ChangeArrayElement` 方法，演示根据值发送数组参数不会阻止对数组元素的更改。</span><span class="sxs-lookup"><span data-stu-id="58213-117">Next, methods `ChangeArray` and `ChangeArrayElement` are called to demonstrate that sending an array argument by value does not prevent changes to the array elements.</span></span>  
  
### <a name="code"></a><span data-ttu-id="58213-118">代码</span><span class="sxs-lookup"><span data-stu-id="58213-118">Code</span></span>  
 <span data-ttu-id="58213-119">[!code-cs[csProgGuideArrays#30](../../../csharp/programming-guide/arrays/codesnippet/CSharp/passing-arrays-as-arguments_4.cs)]</span><span class="sxs-lookup"><span data-stu-id="58213-119">[!code-cs[csProgGuideArrays#30](../../../csharp/programming-guide/arrays/codesnippet/CSharp/passing-arrays-as-arguments_4.cs)]</span></span>  
  
## <a name="passing-multidimensional-arrays-as-arguments"></a><span data-ttu-id="58213-120">将多维数组作为参数传递</span><span class="sxs-lookup"><span data-stu-id="58213-120">Passing Multidimensional Arrays As Arguments</span></span>  
 <span data-ttu-id="58213-121">通过与传递一维数组相同的方式，向方法传递初始化的多维数组。</span><span class="sxs-lookup"><span data-stu-id="58213-121">You pass an initialized multidimensional array to a method in the same way that you pass a one-dimensional array.</span></span>  
  
 <span data-ttu-id="58213-122">[!code-cs[csProgGuideArrays#41](../../../csharp/programming-guide/arrays/codesnippet/CSharp/passing-arrays-as-arguments_5.cs)]</span><span class="sxs-lookup"><span data-stu-id="58213-122">[!code-cs[csProgGuideArrays#41](../../../csharp/programming-guide/arrays/codesnippet/CSharp/passing-arrays-as-arguments_5.cs)]</span></span>  
  
 <span data-ttu-id="58213-123">下列代码演示了 Print 方法的部分声明（该方法接受将二维数组作为其参数）。</span><span class="sxs-lookup"><span data-stu-id="58213-123">The following code shows a partial declaration of a print method that accepts a two-dimensional array as its argument.</span></span>  
  
 <span data-ttu-id="58213-124">[!code-cs[csProgGuideArrays#36](../../../csharp/programming-guide/arrays/codesnippet/CSharp/passing-arrays-as-arguments_6.cs)]</span><span class="sxs-lookup"><span data-stu-id="58213-124">[!code-cs[csProgGuideArrays#36](../../../csharp/programming-guide/arrays/codesnippet/CSharp/passing-arrays-as-arguments_6.cs)]</span></span>  
  
 <span data-ttu-id="58213-125">可在同一步骤中初始化并传递新数组，如下例所示。</span><span class="sxs-lookup"><span data-stu-id="58213-125">You can initialize and pass a new array in one step, as is shown in the following example.</span></span>  
  
 <span data-ttu-id="58213-126">[!code-cs[csProgGuideArrays#32](../../../csharp/programming-guide/arrays/codesnippet/CSharp/passing-arrays-as-arguments_7.cs)]</span><span class="sxs-lookup"><span data-stu-id="58213-126">[!code-cs[csProgGuideArrays#32](../../../csharp/programming-guide/arrays/codesnippet/CSharp/passing-arrays-as-arguments_7.cs)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="58213-127">示例</span><span class="sxs-lookup"><span data-stu-id="58213-127">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="58213-128">描述</span><span class="sxs-lookup"><span data-stu-id="58213-128">Description</span></span>  
 <span data-ttu-id="58213-129">在下列示例中，初始化一个整数的二维数组，并将其传递至 `Print2DArray` 方法。</span><span class="sxs-lookup"><span data-stu-id="58213-129">In the following example, a two-dimensional array of integers is initialized and passed to the `Print2DArray` method.</span></span> <span data-ttu-id="58213-130">该方法将显示数组的元素。</span><span class="sxs-lookup"><span data-stu-id="58213-130">The method displays the elements of the array.</span></span>  
  
### <a name="code"></a><span data-ttu-id="58213-131">代码</span><span class="sxs-lookup"><span data-stu-id="58213-131">Code</span></span>  
 <span data-ttu-id="58213-132">[!code-cs[csProgGuideArrays#31](../../../csharp/programming-guide/arrays/codesnippet/CSharp/passing-arrays-as-arguments_8.cs)]</span><span class="sxs-lookup"><span data-stu-id="58213-132">[!code-cs[csProgGuideArrays#31](../../../csharp/programming-guide/arrays/codesnippet/CSharp/passing-arrays-as-arguments_8.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="58213-133">另请参阅</span><span class="sxs-lookup"><span data-stu-id="58213-133">See Also</span></span>  
 <span data-ttu-id="58213-134">[C# 编程指南](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="58213-134">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="58213-135">[数组](../../../csharp/programming-guide/arrays/index.md) </span><span class="sxs-lookup"><span data-stu-id="58213-135">[Arrays](../../../csharp/programming-guide/arrays/index.md) </span></span>  
 <span data-ttu-id="58213-136">[一维数组](../../../csharp/programming-guide/arrays/single-dimensional-arrays.md) </span><span class="sxs-lookup"><span data-stu-id="58213-136">[Single-Dimensional Arrays](../../../csharp/programming-guide/arrays/single-dimensional-arrays.md) </span></span>  
 <span data-ttu-id="58213-137">[多维数组](../../../csharp/programming-guide/arrays/multidimensional-arrays.md) </span><span class="sxs-lookup"><span data-stu-id="58213-137">[Multidimensional Arrays](../../../csharp/programming-guide/arrays/multidimensional-arrays.md) </span></span>  
 [<span data-ttu-id="58213-138">交错数组</span><span class="sxs-lookup"><span data-stu-id="58213-138">Jagged Arrays</span></span>](../../../csharp/programming-guide/arrays/jagged-arrays.md)

