---
title: 使用 ref 和 out 传递数组（C# 编程指南）
ms.date: 07/20/2015
helpviewer_keywords:
- arrays [C#], passing using ref and out
ms.assetid: 6a2b261e-a1cc-49a6-b4f0-6cacae385a1e
ms.openlocfilehash: a186399125e01bb2535f3a8b488c6fbd85932246
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33313565"
---
# <a name="passing-arrays-using-ref-and-out-c-programming-guide"></a><span data-ttu-id="a33ab-102">使用 ref 和 out 传递数组（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="a33ab-102">Passing Arrays Using ref and out (C# Programming Guide)</span></span>
<span data-ttu-id="a33ab-103">与所有 [out](../../../csharp/language-reference/keywords/out-parameter-modifier.md) 参数一样，在使用数组类型的 `out` 参数前必须先为其赋值；即必须由被调用方为其赋值。</span><span class="sxs-lookup"><span data-stu-id="a33ab-103">Like all [out](../../../csharp/language-reference/keywords/out-parameter-modifier.md) parameters, an `out` parameter of an array type must be assigned before it is used; that is, it must be assigned by the callee.</span></span> <span data-ttu-id="a33ab-104">例如:</span><span class="sxs-lookup"><span data-stu-id="a33ab-104">For example:</span></span>  
  
 [!code-csharp[csProgGuideArrays#39](../../../csharp/programming-guide/arrays/codesnippet/CSharp/passing-arrays-using-ref-and-out_1.cs)]  
  
 <span data-ttu-id="a33ab-105">与所有 [ref](../../../csharp/language-reference/keywords/ref.md) 参数一样，数组类型的 `ref` 参数必须由调用方明确赋值。</span><span class="sxs-lookup"><span data-stu-id="a33ab-105">Like all [ref](../../../csharp/language-reference/keywords/ref.md) parameters, a `ref` parameter of an array type must be definitely assigned by the caller.</span></span> <span data-ttu-id="a33ab-106">因此，不需要由被调用方明确赋值。</span><span class="sxs-lookup"><span data-stu-id="a33ab-106">Therefore, there is no need to be definitely assigned by the callee.</span></span> <span data-ttu-id="a33ab-107">可以将数组类型的 `ref` 参数更改为调用的结果。</span><span class="sxs-lookup"><span data-stu-id="a33ab-107">A `ref` parameter of an array type may be altered as a result of the call.</span></span> <span data-ttu-id="a33ab-108">例如，可以为数组赋以 [null](../../../csharp/language-reference/keywords/null.md) 值，或将其初始化为另一个数组。</span><span class="sxs-lookup"><span data-stu-id="a33ab-108">For example, the array can be assigned the [null](../../../csharp/language-reference/keywords/null.md) value or can be initialized to a different array.</span></span> <span data-ttu-id="a33ab-109">例如:</span><span class="sxs-lookup"><span data-stu-id="a33ab-109">For example:</span></span>  
  
 [!code-csharp[csProgGuideArrays#40](../../../csharp/programming-guide/arrays/codesnippet/CSharp/passing-arrays-using-ref-and-out_2.cs)]  
  
 <span data-ttu-id="a33ab-110">下面两个示例演示了 `out` 与 `ref` 在将数组传递给方法时的用法差异。</span><span class="sxs-lookup"><span data-stu-id="a33ab-110">The following two examples demonstrate the difference between `out` and `ref` when used in passing arrays to methods.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a33ab-111">示例</span><span class="sxs-lookup"><span data-stu-id="a33ab-111">Example</span></span>  
 <span data-ttu-id="a33ab-112">在此示例中，在调用方（`theArray` 方法）中声明数组 `Main`，并在 `FillArray` 方法中初始化此数组。</span><span class="sxs-lookup"><span data-stu-id="a33ab-112">In this example, the array `theArray` is declared in the caller (the `Main` method), and initialized in the `FillArray` method.</span></span> <span data-ttu-id="a33ab-113">然后，数组元素将返回调用方并显示。</span><span class="sxs-lookup"><span data-stu-id="a33ab-113">Then, the array elements are returned to the caller and displayed.</span></span>  
  
 [!code-csharp[csProgGuideArrays#37](../../../csharp/programming-guide/arrays/codesnippet/CSharp/passing-arrays-using-ref-and-out_3.cs)]  
  
## <a name="example"></a><span data-ttu-id="a33ab-114">示例</span><span class="sxs-lookup"><span data-stu-id="a33ab-114">Example</span></span>  
 <span data-ttu-id="a33ab-115">在此示例中，在调用方（`theArray` 方法）中初始化数组 `Main`，并通过使用 `FillArray` 参数将其传递给 `ref` 方法。</span><span class="sxs-lookup"><span data-stu-id="a33ab-115">In this example, the array `theArray` is initialized in the caller (the `Main` method), and passed to the `FillArray` method by using the `ref` parameter.</span></span> <span data-ttu-id="a33ab-116">在 `FillArray` 方法中更新某些数组元素。</span><span class="sxs-lookup"><span data-stu-id="a33ab-116">Some of the array elements are updated in the `FillArray` method.</span></span> <span data-ttu-id="a33ab-117">然后，数组元素将返回调用方并显示。</span><span class="sxs-lookup"><span data-stu-id="a33ab-117">Then, the array elements are returned to the caller and displayed.</span></span>  
  
 [!code-csharp[csProgGuideArrays#38](../../../csharp/programming-guide/arrays/codesnippet/CSharp/passing-arrays-using-ref-and-out_4.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="a33ab-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="a33ab-118">See Also</span></span>  
 [<span data-ttu-id="a33ab-119">ref</span><span class="sxs-lookup"><span data-stu-id="a33ab-119">ref</span></span>](../../../csharp/language-reference/keywords/ref.md)  
 [<span data-ttu-id="a33ab-120">out 参数修饰符</span><span class="sxs-lookup"><span data-stu-id="a33ab-120">out parameter modifier</span></span>](../../../csharp/language-reference/keywords/out-parameter-modifier.md)  
 [<span data-ttu-id="a33ab-121">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="a33ab-121">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="a33ab-122">数组</span><span class="sxs-lookup"><span data-stu-id="a33ab-122">Arrays</span></span>](../../../csharp/programming-guide/arrays/index.md)  
 [<span data-ttu-id="a33ab-123">一维数组</span><span class="sxs-lookup"><span data-stu-id="a33ab-123">Single-Dimensional Arrays</span></span>](../../../csharp/programming-guide/arrays/single-dimensional-arrays.md)  
 [<span data-ttu-id="a33ab-124">多维数组</span><span class="sxs-lookup"><span data-stu-id="a33ab-124">Multidimensional Arrays</span></span>](../../../csharp/programming-guide/arrays/multidimensional-arrays.md)  
 [<span data-ttu-id="a33ab-125">交错数组</span><span class="sxs-lookup"><span data-stu-id="a33ab-125">Jagged Arrays</span></span>](../../../csharp/programming-guide/arrays/jagged-arrays.md)
