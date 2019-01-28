---
title: 对数组使用 foreach - C# 编程指南
ms.custom: seodec18
ms.date: 05/23/2018
helpviewer_keywords:
- arrays [C#], foreach
- foreach statement [C#], using with arrays
ms.assetid: 5f2da2a9-1f56-4de5-94cc-e07f4f7a0244
ms.openlocfilehash: 16f65bc4ddcc37bbc1abb5dfa6299670a738073b
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54503568"
---
# <a name="using-foreach-with-arrays-c-programming-guide"></a><span data-ttu-id="57545-102">对数组使用 foreach（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="57545-102">Using foreach with arrays (C# Programming Guide)</span></span>

<span data-ttu-id="57545-103">[foreach](../../language-reference/keywords/foreach-in.md) 语句提供一种简单、明了的方法来循环访问数组的元素。</span><span class="sxs-lookup"><span data-stu-id="57545-103">The [foreach](../../language-reference/keywords/foreach-in.md) statement provides a simple, clean way to iterate through the elements of an array.</span></span>

<span data-ttu-id="57545-104">对于单维数组，`foreach` 语句以递增索引顺序处理元素（从索引 0 开始并以索引 `Length - 1` 结束）：</span><span class="sxs-lookup"><span data-stu-id="57545-104">For single-dimensional arrays, the `foreach` statement processes elements in increasing index order, starting with index 0 and ending with index `Length - 1`:</span></span>

[!code-csharp[csProgGuideArrays#28](./codesnippet/CSharp/using-foreach-with-arrays_1.cs)]

<span data-ttu-id="57545-105">对于多维数组，遍历元素的方式为：首先增加最右边维度的索引，然后是它左边的一个维度，以此类推，向左遍历元素：</span><span class="sxs-lookup"><span data-stu-id="57545-105">For multi-dimensional arrays, elements are traversed such that the indices of the rightmost dimension are increased first, then the next left dimension, and so on to the left:</span></span>

[!code-csharp[csProgGuideArrays#29](./codesnippet/CSharp/using-foreach-with-arrays_2.cs)]

<span data-ttu-id="57545-106">但对于多维数组，使用嵌套的 [for](../../language-reference/keywords/for.md) 循环可以更好地控制处理数组元素的顺序。</span><span class="sxs-lookup"><span data-stu-id="57545-106">However, with multidimensional arrays, using a nested [for](../../language-reference/keywords/for.md) loop gives you more control over the order in which to process the array elements.</span></span>

## <a name="see-also"></a><span data-ttu-id="57545-107">请参阅</span><span class="sxs-lookup"><span data-stu-id="57545-107">See also</span></span>

- <xref:System.Array>
- [<span data-ttu-id="57545-108">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="57545-108">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="57545-109">数组</span><span class="sxs-lookup"><span data-stu-id="57545-109">Arrays</span></span>](index.md)
- [<span data-ttu-id="57545-110">一维数组</span><span class="sxs-lookup"><span data-stu-id="57545-110">Single-Dimensional Arrays</span></span>](single-dimensional-arrays.md)
- [<span data-ttu-id="57545-111">多维数组</span><span class="sxs-lookup"><span data-stu-id="57545-111">Multidimensional Arrays</span></span>](multidimensional-arrays.md)
- [<span data-ttu-id="57545-112">交错数组</span><span class="sxs-lookup"><span data-stu-id="57545-112">Jagged Arrays</span></span>](jagged-arrays.md)
