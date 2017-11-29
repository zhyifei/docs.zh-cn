---
title: "对数组使用 foreach（C# 编程指南）"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords:
- arrays [C#], foreach
- foreach statement [C#], using with arrays
ms.assetid: 5f2da2a9-1f56-4de5-94cc-e07f4f7a0244
caps.latest.revision: "14"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 797cb9a63a5e1009b170b2afda8634bd21a50035
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="using-foreach-with-arrays-c-programming-guide"></a><span data-ttu-id="a5b94-102">对数组使用 foreach（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="a5b94-102">Using foreach with Arrays (C# Programming Guide)</span></span>
<span data-ttu-id="a5b94-103">C# 还提供 [foreach](../../../csharp/language-reference/keywords/foreach-in.md) 语句。</span><span class="sxs-lookup"><span data-stu-id="a5b94-103">C# also provides the [foreach](../../../csharp/language-reference/keywords/foreach-in.md) statement.</span></span> <span data-ttu-id="a5b94-104">该语句提供一种简单、明了的方法来循环访问数组或任何可枚举集合的元素。</span><span class="sxs-lookup"><span data-stu-id="a5b94-104">This statement provides a simple, clean way to iterate through the elements of an array or any enumerable collection.</span></span> <span data-ttu-id="a5b94-105">`foreach` 语句按数组或集合类型的枚举器返回的顺序处理元素，该顺序通常是从第 0 个元素到最后一个元素。</span><span class="sxs-lookup"><span data-stu-id="a5b94-105">The `foreach` statement processes elements in the order returned by the array or collection type’s enumerator, which is usually from the 0th element to the last.</span></span> <span data-ttu-id="a5b94-106">例如，以下代码创建一个名为 `numbers` 的数组，并使用 `foreach` 语句循环访问该数组：</span><span class="sxs-lookup"><span data-stu-id="a5b94-106">For example, the following code creates an array called `numbers` and iterates through it with the `foreach` statement:</span></span>  
  
 [!code-csharp[csProgGuideArrays#28](../../../csharp/programming-guide/arrays/codesnippet/CSharp/using-foreach-with-arrays_1.cs)]  
  
 <span data-ttu-id="a5b94-107">借助多维数组，你可以使用相同的方法来循环访问元素，例如：</span><span class="sxs-lookup"><span data-stu-id="a5b94-107">With multidimensional arrays, you can use the same method to iterate through the elements, for example:</span></span>  
  
 [!code-csharp[csProgGuideArrays#29](../../../csharp/programming-guide/arrays/codesnippet/CSharp/using-foreach-with-arrays_2.cs)]  
  
 <span data-ttu-id="a5b94-108">但对于多维数组，使用嵌套的 [for](../../../csharp/language-reference/keywords/for.md) 循环可以更好地控制数组元素。</span><span class="sxs-lookup"><span data-stu-id="a5b94-108">However, with multidimensional arrays, using a nested [for](../../../csharp/language-reference/keywords/for.md) loop gives you more control over the array elements.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a5b94-109">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a5b94-109">See Also</span></span>  
 <xref:System.Array>  
 [<span data-ttu-id="a5b94-110">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="a5b94-110">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="a5b94-111">阵列</span><span class="sxs-lookup"><span data-stu-id="a5b94-111">Arrays</span></span>](../../../csharp/programming-guide/arrays/index.md)  
 [<span data-ttu-id="a5b94-112">一维数组</span><span class="sxs-lookup"><span data-stu-id="a5b94-112">Single-Dimensional Arrays</span></span>](../../../csharp/programming-guide/arrays/single-dimensional-arrays.md)  
 [<span data-ttu-id="a5b94-113">多维数组</span><span class="sxs-lookup"><span data-stu-id="a5b94-113">Multidimensional Arrays</span></span>](../../../csharp/programming-guide/arrays/multidimensional-arrays.md)  
 [<span data-ttu-id="a5b94-114">交错数组</span><span class="sxs-lookup"><span data-stu-id="a5b94-114">Jagged Arrays</span></span>](../../../csharp/programming-guide/arrays/jagged-arrays.md)
