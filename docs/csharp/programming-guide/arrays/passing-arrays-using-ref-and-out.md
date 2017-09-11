---
title: "使用 ref 和 out 传递数组（C# 编程指南）"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- arrays [C#], passing using ref and out
ms.assetid: 6a2b261e-a1cc-49a6-b4f0-6cacae385a1e
caps.latest.revision: 16
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
ms.openlocfilehash: 58fc359881295a9e6627ac1269ef17aa298009c7
ms.contentlocale: zh-cn
ms.lasthandoff: 07/28/2017

---
# <a name="passing-arrays-using-ref-and-out-c-programming-guide"></a><span data-ttu-id="9f72d-102">使用 ref 和 out 传递数组（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="9f72d-102">Passing Arrays Using ref and out (C# Programming Guide)</span></span>
<span data-ttu-id="9f72d-103">与所有 [out](../../../csharp/language-reference/keywords/out.md) 参数一样，在使用数组类型的 `out` 参数前必须先为其赋值；即必须由被调用方为其赋值。</span><span class="sxs-lookup"><span data-stu-id="9f72d-103">Like all [out](../../../csharp/language-reference/keywords/out.md) parameters, an `out` parameter of an array type must be assigned before it is used; that is, it must be assigned by the callee.</span></span> <span data-ttu-id="9f72d-104">例如: </span><span class="sxs-lookup"><span data-stu-id="9f72d-104">For example:</span></span>  
  
 <span data-ttu-id="9f72d-105">[!code-cs[csProgGuideArrays#39](../../../csharp/programming-guide/arrays/codesnippet/CSharp/passing-arrays-using-ref-and-out_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="9f72d-105">[!code-cs[csProgGuideArrays#39](../../../csharp/programming-guide/arrays/codesnippet/CSharp/passing-arrays-using-ref-and-out_1.cs)]</span></span>  
  
 <span data-ttu-id="9f72d-106">与所有 [ref](../../../csharp/language-reference/keywords/ref.md) 参数一样，数组类型的 `ref` 参数必须由调用方明确赋值。</span><span class="sxs-lookup"><span data-stu-id="9f72d-106">Like all [ref](../../../csharp/language-reference/keywords/ref.md) parameters, a `ref` parameter of an array type must be definitely assigned by the caller.</span></span> <span data-ttu-id="9f72d-107">因此，不需要由被调用方明确赋值。</span><span class="sxs-lookup"><span data-stu-id="9f72d-107">Therefore, there is no need to be definitely assigned by the callee.</span></span> <span data-ttu-id="9f72d-108">可以将数组类型的 `ref` 参数更改为调用的结果。</span><span class="sxs-lookup"><span data-stu-id="9f72d-108">A `ref` parameter of an array type may be altered as a result of the call.</span></span> <span data-ttu-id="9f72d-109">例如，可以为数组赋以 [null](../../../csharp/language-reference/keywords/null.md) 值，或将其初始化为另一个数组。</span><span class="sxs-lookup"><span data-stu-id="9f72d-109">For example, the array can be assigned the [null](../../../csharp/language-reference/keywords/null.md) value or can be initialized to a different array.</span></span> <span data-ttu-id="9f72d-110">例如: </span><span class="sxs-lookup"><span data-stu-id="9f72d-110">For example:</span></span>  
  
 <span data-ttu-id="9f72d-111">[!code-cs[csProgGuideArrays#40](../../../csharp/programming-guide/arrays/codesnippet/CSharp/passing-arrays-using-ref-and-out_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="9f72d-111">[!code-cs[csProgGuideArrays#40](../../../csharp/programming-guide/arrays/codesnippet/CSharp/passing-arrays-using-ref-and-out_2.cs)]</span></span>  
  
 <span data-ttu-id="9f72d-112">下面两个示例演示了 `out` 与 `ref` 在将数组传递给方法时的用法差异。</span><span class="sxs-lookup"><span data-stu-id="9f72d-112">The following two examples demonstrate the difference between `out` and `ref` when used in passing arrays to methods.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9f72d-113">示例</span><span class="sxs-lookup"><span data-stu-id="9f72d-113">Example</span></span>  
 <span data-ttu-id="9f72d-114">在此示例中，在调用方（`theArray` 方法）中声明数组 `Main`，并在 `FillArray` 方法中初始化此数组。</span><span class="sxs-lookup"><span data-stu-id="9f72d-114">In this example, the array `theArray` is declared in the caller (the `Main` method), and initialized in the `FillArray` method.</span></span> <span data-ttu-id="9f72d-115">然后，数组元素将返回调用方并显示。</span><span class="sxs-lookup"><span data-stu-id="9f72d-115">Then, the array elements are returned to the caller and displayed.</span></span>  
  
 <span data-ttu-id="9f72d-116">[!code-cs[csProgGuideArrays#37](../../../csharp/programming-guide/arrays/codesnippet/CSharp/passing-arrays-using-ref-and-out_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="9f72d-116">[!code-cs[csProgGuideArrays#37](../../../csharp/programming-guide/arrays/codesnippet/CSharp/passing-arrays-using-ref-and-out_3.cs)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="9f72d-117">示例</span><span class="sxs-lookup"><span data-stu-id="9f72d-117">Example</span></span>  
 <span data-ttu-id="9f72d-118">在此示例中，在调用方（`theArray` 方法）中初始化数组 `Main`，并通过使用 `FillArray` 参数将其传递给 `ref` 方法。</span><span class="sxs-lookup"><span data-stu-id="9f72d-118">In this example, the array `theArray` is initialized in the caller (the `Main` method), and passed to the `FillArray` method by using the `ref` parameter.</span></span> <span data-ttu-id="9f72d-119">在 `FillArray` 方法中更新某些数组元素。</span><span class="sxs-lookup"><span data-stu-id="9f72d-119">Some of the array elements are updated in the `FillArray` method.</span></span> <span data-ttu-id="9f72d-120">然后，数组元素将返回调用方并显示。</span><span class="sxs-lookup"><span data-stu-id="9f72d-120">Then, the array elements are returned to the caller and displayed.</span></span>  
  
 <span data-ttu-id="9f72d-121">[!code-cs[csProgGuideArrays#38](../../../csharp/programming-guide/arrays/codesnippet/CSharp/passing-arrays-using-ref-and-out_4.cs)]</span><span class="sxs-lookup"><span data-stu-id="9f72d-121">[!code-cs[csProgGuideArrays#38](../../../csharp/programming-guide/arrays/codesnippet/CSharp/passing-arrays-using-ref-and-out_4.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9f72d-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9f72d-122">See Also</span></span>  
 <span data-ttu-id="9f72d-123">[ref](../../../csharp/language-reference/keywords/ref.md) </span><span class="sxs-lookup"><span data-stu-id="9f72d-123">[ref](../../../csharp/language-reference/keywords/ref.md) </span></span>  
 <span data-ttu-id="9f72d-124">[out（参数修饰符）](../../../csharp/language-reference/keywords/out-parameter-modifier.md) </span><span class="sxs-lookup"><span data-stu-id="9f72d-124">[out parameter modifier](../../../csharp/language-reference/keywords/out-parameter-modifier.md) </span></span>  
 <span data-ttu-id="9f72d-125">[C# 编程指南](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="9f72d-125">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="9f72d-126">[数组](../../../csharp/programming-guide/arrays/index.md) </span><span class="sxs-lookup"><span data-stu-id="9f72d-126">[Arrays](../../../csharp/programming-guide/arrays/index.md) </span></span>  
 <span data-ttu-id="9f72d-127">[一维数组](../../../csharp/programming-guide/arrays/single-dimensional-arrays.md) </span><span class="sxs-lookup"><span data-stu-id="9f72d-127">[Single-Dimensional Arrays](../../../csharp/programming-guide/arrays/single-dimensional-arrays.md) </span></span>  
 <span data-ttu-id="9f72d-128">[多维数组](../../../csharp/programming-guide/arrays/multidimensional-arrays.md) </span><span class="sxs-lookup"><span data-stu-id="9f72d-128">[Multidimensional Arrays](../../../csharp/programming-guide/arrays/multidimensional-arrays.md) </span></span>  
 [<span data-ttu-id="9f72d-129">交错数组</span><span class="sxs-lookup"><span data-stu-id="9f72d-129">Jagged Arrays</span></span>](../../../csharp/programming-guide/arrays/jagged-arrays.md)

