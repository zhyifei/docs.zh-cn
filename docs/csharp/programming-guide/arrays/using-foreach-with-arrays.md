---
title: "对数组使用 foreach（C# 编程指南）"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- arrays [C#], foreach
- foreach statement [C#], using with arrays
ms.assetid: 5f2da2a9-1f56-4de5-94cc-e07f4f7a0244
caps.latest.revision: 14
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
ms.openlocfilehash: a1d0b704233b110b5f499b8186a4a901f9b5408f
ms.contentlocale: zh-cn
ms.lasthandoff: 07/28/2017

---
# <a name="using-foreach-with-arrays-c-programming-guide"></a><span data-ttu-id="4a28e-102">对数组使用 foreach（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="4a28e-102">Using foreach with Arrays (C# Programming Guide)</span></span>
<span data-ttu-id="4a28e-103">C# 还提供 [foreach](../../../csharp/language-reference/keywords/foreach-in.md) 语句。</span><span class="sxs-lookup"><span data-stu-id="4a28e-103">C# also provides the [foreach](../../../csharp/language-reference/keywords/foreach-in.md) statement.</span></span> <span data-ttu-id="4a28e-104">该语句提供一种简单、明了的方法来循环访问数组或任何可枚举集合的元素。</span><span class="sxs-lookup"><span data-stu-id="4a28e-104">This statement provides a simple, clean way to iterate through the elements of an array or any enumerable collection.</span></span> <span data-ttu-id="4a28e-105">`foreach` 语句按数组或集合类型的枚举器返回的顺序处理元素，该顺序通常是从第 0 个元素到最后一个元素。</span><span class="sxs-lookup"><span data-stu-id="4a28e-105">The `foreach` statement processes elements in the order returned by the array or collection type’s enumerator, which is usually from the 0th element to the last.</span></span> <span data-ttu-id="4a28e-106">例如，以下代码创建一个名为 `numbers` 的数组，并使用 `foreach` 语句循环访问该数组：</span><span class="sxs-lookup"><span data-stu-id="4a28e-106">For example, the following code creates an array called `numbers` and iterates through it with the `foreach` statement:</span></span>  
  
 <span data-ttu-id="4a28e-107">[!code-cs[csProgGuideArrays#28](../../../csharp/programming-guide/arrays/codesnippet/CSharp/using-foreach-with-arrays_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="4a28e-107">[!code-cs[csProgGuideArrays#28](../../../csharp/programming-guide/arrays/codesnippet/CSharp/using-foreach-with-arrays_1.cs)]</span></span>  
  
 <span data-ttu-id="4a28e-108">借助多维数组，你可以使用相同的方法来循环访问元素，例如：</span><span class="sxs-lookup"><span data-stu-id="4a28e-108">With multidimensional arrays, you can use the same method to iterate through the elements, for example:</span></span>  
  
 <span data-ttu-id="4a28e-109">[!code-cs[csProgGuideArrays#29](../../../csharp/programming-guide/arrays/codesnippet/CSharp/using-foreach-with-arrays_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="4a28e-109">[!code-cs[csProgGuideArrays#29](../../../csharp/programming-guide/arrays/codesnippet/CSharp/using-foreach-with-arrays_2.cs)]</span></span>  
  
 <span data-ttu-id="4a28e-110">但对于多维数组，使用嵌套的 [for](../../../csharp/language-reference/keywords/for.md) 循环可以更好地控制数组元素。</span><span class="sxs-lookup"><span data-stu-id="4a28e-110">However, with multidimensional arrays, using a nested [for](../../../csharp/language-reference/keywords/for.md) loop gives you more control over the array elements.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4a28e-111">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4a28e-111">See Also</span></span>  
 <span data-ttu-id="4a28e-112"><xref:System.Array></span><span class="sxs-lookup"><span data-stu-id="4a28e-112"><xref:System.Array></span></span>   
 <span data-ttu-id="4a28e-113">[C# 编程指南](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="4a28e-113">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="4a28e-114">[数组](../../../csharp/programming-guide/arrays/index.md) </span><span class="sxs-lookup"><span data-stu-id="4a28e-114">[Arrays](../../../csharp/programming-guide/arrays/index.md) </span></span>  
 <span data-ttu-id="4a28e-115">[一维数组](../../../csharp/programming-guide/arrays/single-dimensional-arrays.md) </span><span class="sxs-lookup"><span data-stu-id="4a28e-115">[Single-Dimensional Arrays](../../../csharp/programming-guide/arrays/single-dimensional-arrays.md) </span></span>  
 <span data-ttu-id="4a28e-116">[多维数组](../../../csharp/programming-guide/arrays/multidimensional-arrays.md) </span><span class="sxs-lookup"><span data-stu-id="4a28e-116">[Multidimensional Arrays](../../../csharp/programming-guide/arrays/multidimensional-arrays.md) </span></span>  
 [<span data-ttu-id="4a28e-117">交错数组</span><span class="sxs-lookup"><span data-stu-id="4a28e-117">Jagged Arrays</span></span>](../../../csharp/programming-guide/arrays/jagged-arrays.md)

