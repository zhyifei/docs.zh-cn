---
title: "使用 ref 和 out 传递数组（C# 编程指南）"
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
helpviewer_keywords:
- arrays [C#], passing using ref and out
ms.assetid: 6a2b261e-a1cc-49a6-b4f0-6cacae385a1e
caps.latest.revision: 
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: f76f63aee0100c6af6bde73c8543b4e7136b1954
ms.sourcegitcommit: 83dd5ec003e788ccb3e33f3412a7af39ae347646
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/15/2018
---
# <a name="passing-arrays-using-ref-and-out-c-programming-guide"></a><span data-ttu-id="22e1a-102">使用 ref 和 out 传递数组（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="22e1a-102">Passing Arrays Using ref and out (C# Programming Guide)</span></span>
<span data-ttu-id="22e1a-103">与所有 [out](../../../csharp/language-reference/keywords/out-parameter-modifier.md) 参数一样，在使用数组类型的 `out` 参数前必须先为其赋值；即必须由被调用方为其赋值。</span><span class="sxs-lookup"><span data-stu-id="22e1a-103">Like all [out](../../../csharp/language-reference/keywords/out-parameter-modifier.md) parameters, an `out` parameter of an array type must be assigned before it is used; that is, it must be assigned by the callee.</span></span> <span data-ttu-id="22e1a-104">例如:</span><span class="sxs-lookup"><span data-stu-id="22e1a-104">For example:</span></span>  
  
 [!code-csharp[csProgGuideArrays#39](../../../csharp/programming-guide/arrays/codesnippet/CSharp/passing-arrays-using-ref-and-out_1.cs)]  
  
 <span data-ttu-id="22e1a-105">与所有 [ref](../../../csharp/language-reference/keywords/ref.md) 参数一样，数组类型的 `ref` 参数必须由调用方明确赋值。</span><span class="sxs-lookup"><span data-stu-id="22e1a-105">Like all [ref](../../../csharp/language-reference/keywords/ref.md) parameters, a `ref` parameter of an array type must be definitely assigned by the caller.</span></span> <span data-ttu-id="22e1a-106">因此，不需要由被调用方明确赋值。</span><span class="sxs-lookup"><span data-stu-id="22e1a-106">Therefore, there is no need to be definitely assigned by the callee.</span></span> <span data-ttu-id="22e1a-107">可以将数组类型的 `ref` 参数更改为调用的结果。</span><span class="sxs-lookup"><span data-stu-id="22e1a-107">A `ref` parameter of an array type may be altered as a result of the call.</span></span> <span data-ttu-id="22e1a-108">例如，可以为数组赋以 [null](../../../csharp/language-reference/keywords/null.md) 值，或将其初始化为另一个数组。</span><span class="sxs-lookup"><span data-stu-id="22e1a-108">For example, the array can be assigned the [null](../../../csharp/language-reference/keywords/null.md) value or can be initialized to a different array.</span></span> <span data-ttu-id="22e1a-109">例如:</span><span class="sxs-lookup"><span data-stu-id="22e1a-109">For example:</span></span>  
  
 [!code-csharp[csProgGuideArrays#40](../../../csharp/programming-guide/arrays/codesnippet/CSharp/passing-arrays-using-ref-and-out_2.cs)]  
  
 <span data-ttu-id="22e1a-110">下面两个示例演示了 `out` 与 `ref` 在将数组传递给方法时的用法差异。</span><span class="sxs-lookup"><span data-stu-id="22e1a-110">The following two examples demonstrate the difference between `out` and `ref` when used in passing arrays to methods.</span></span>  
  
## <a name="example"></a><span data-ttu-id="22e1a-111">示例</span><span class="sxs-lookup"><span data-stu-id="22e1a-111">Example</span></span>  
 <span data-ttu-id="22e1a-112">在此示例中，在调用方（`theArray` 方法）中声明数组 `Main`，并在 `FillArray` 方法中初始化此数组。</span><span class="sxs-lookup"><span data-stu-id="22e1a-112">In this example, the array `theArray` is declared in the caller (the `Main` method), and initialized in the `FillArray` method.</span></span> <span data-ttu-id="22e1a-113">然后，数组元素将返回调用方并显示。</span><span class="sxs-lookup"><span data-stu-id="22e1a-113">Then, the array elements are returned to the caller and displayed.</span></span>  
  
 [!code-csharp[csProgGuideArrays#37](../../../csharp/programming-guide/arrays/codesnippet/CSharp/passing-arrays-using-ref-and-out_3.cs)]  
  
## <a name="example"></a><span data-ttu-id="22e1a-114">示例</span><span class="sxs-lookup"><span data-stu-id="22e1a-114">Example</span></span>  
 <span data-ttu-id="22e1a-115">在此示例中，在调用方（`theArray` 方法）中初始化数组 `Main`，并通过使用 `FillArray` 参数将其传递给 `ref` 方法。</span><span class="sxs-lookup"><span data-stu-id="22e1a-115">In this example, the array `theArray` is initialized in the caller (the `Main` method), and passed to the `FillArray` method by using the `ref` parameter.</span></span> <span data-ttu-id="22e1a-116">在 `FillArray` 方法中更新某些数组元素。</span><span class="sxs-lookup"><span data-stu-id="22e1a-116">Some of the array elements are updated in the `FillArray` method.</span></span> <span data-ttu-id="22e1a-117">然后，数组元素将返回调用方并显示。</span><span class="sxs-lookup"><span data-stu-id="22e1a-117">Then, the array elements are returned to the caller and displayed.</span></span>  
  
 [!code-csharp[csProgGuideArrays#38](../../../csharp/programming-guide/arrays/codesnippet/CSharp/passing-arrays-using-ref-and-out_4.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="22e1a-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="22e1a-118">See Also</span></span>  
 [<span data-ttu-id="22e1a-119">ref</span><span class="sxs-lookup"><span data-stu-id="22e1a-119">ref</span></span>](../../../csharp/language-reference/keywords/ref.md)  
 [<span data-ttu-id="22e1a-120">out 参数修饰符</span><span class="sxs-lookup"><span data-stu-id="22e1a-120">out parameter modifier</span></span>](../../../csharp/language-reference/keywords/out-parameter-modifier.md)  
 [<span data-ttu-id="22e1a-121">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="22e1a-121">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="22e1a-122">数组</span><span class="sxs-lookup"><span data-stu-id="22e1a-122">Arrays</span></span>](../../../csharp/programming-guide/arrays/index.md)  
 [<span data-ttu-id="22e1a-123">一维数组</span><span class="sxs-lookup"><span data-stu-id="22e1a-123">Single-Dimensional Arrays</span></span>](../../../csharp/programming-guide/arrays/single-dimensional-arrays.md)  
 [<span data-ttu-id="22e1a-124">多维数组</span><span class="sxs-lookup"><span data-stu-id="22e1a-124">Multidimensional Arrays</span></span>](../../../csharp/programming-guide/arrays/multidimensional-arrays.md)  
 [<span data-ttu-id="22e1a-125">交错数组</span><span class="sxs-lookup"><span data-stu-id="22e1a-125">Jagged Arrays</span></span>](../../../csharp/programming-guide/arrays/jagged-arrays.md)
