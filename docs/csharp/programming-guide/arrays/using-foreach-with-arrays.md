---
title: 对数组使用 foreach - C# 编程指南
ms.custom: seodec18
ms.date: 05/23/2018
helpviewer_keywords:
- arrays [C#], foreach
- foreach statement [C#], using with arrays
ms.assetid: 5f2da2a9-1f56-4de5-94cc-e07f4f7a0244
ms.openlocfilehash: a22cb939370b38780881eca0d9585a14002c8250
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/28/2019
ms.locfileid: "56966406"
---
# <a name="using-foreach-with-arrays-c-programming-guide"></a><span data-ttu-id="98941-102">对数组使用 foreach（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="98941-102">Using foreach with arrays (C# Programming Guide)</span></span>

<span data-ttu-id="98941-103">[foreach](../../language-reference/keywords/foreach-in.md) 语句提供一种简单、明了的方法来循环访问数组的元素。</span><span class="sxs-lookup"><span data-stu-id="98941-103">The [foreach](../../language-reference/keywords/foreach-in.md) statement provides a simple, clean way to iterate through the elements of an array.</span></span>

<span data-ttu-id="98941-104">对于单维数组，`foreach` 语句以递增索引顺序处理元素（从索引 0 开始并以索引 `Length - 1` 结束）：</span><span class="sxs-lookup"><span data-stu-id="98941-104">For single-dimensional arrays, the `foreach` statement processes elements in increasing index order, starting with index 0 and ending with index `Length - 1`:</span></span>

 [!code-csharp[csProgGuideArrays#28](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#28)]

<span data-ttu-id="98941-105">对于多维数组，遍历元素的方式为：首先增加最右边维度的索引，然后是它左边的一个维度，以此类推，向左遍历元素：</span><span class="sxs-lookup"><span data-stu-id="98941-105">For multi-dimensional arrays, elements are traversed such that the indices of the rightmost dimension are increased first, then the next left dimension, and so on to the left:</span></span>

 [!code-csharp[csProgGuideArrays#29](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#29)]

<span data-ttu-id="98941-106">但对于多维数组，使用嵌套的 [for](../../language-reference/keywords/for.md) 循环可以更好地控制处理数组元素的顺序。</span><span class="sxs-lookup"><span data-stu-id="98941-106">However, with multidimensional arrays, using a nested [for](../../language-reference/keywords/for.md) loop gives you more control over the order in which to process the array elements.</span></span>

## <a name="see-also"></a><span data-ttu-id="98941-107">请参阅</span><span class="sxs-lookup"><span data-stu-id="98941-107">See also</span></span>

- <xref:System.Array>
- [<span data-ttu-id="98941-108">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="98941-108">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="98941-109">数组</span><span class="sxs-lookup"><span data-stu-id="98941-109">Arrays</span></span>](index.md)
- [<span data-ttu-id="98941-110">一维数组</span><span class="sxs-lookup"><span data-stu-id="98941-110">Single-Dimensional Arrays</span></span>](single-dimensional-arrays.md)
- [<span data-ttu-id="98941-111">多维数组</span><span class="sxs-lookup"><span data-stu-id="98941-111">Multidimensional Arrays</span></span>](multidimensional-arrays.md)
- [<span data-ttu-id="98941-112">交错数组</span><span class="sxs-lookup"><span data-stu-id="98941-112">Jagged Arrays</span></span>](jagged-arrays.md)
