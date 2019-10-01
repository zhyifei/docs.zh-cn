---
title: 如何：在 Visual Basic 中对数组进行排序
ms.date: 07/20/2015
f1_keywords:
- Array.Sort
helpviewer_keywords:
- arrays [Visual Basic], sorting
- examples [Visual Basic], arrays
ms.assetid: 9289aeaa-9626-4698-94a7-1d1fd3702b87
ms.openlocfilehash: 467d1bcce6bda2feb5a8e59c152cb292d753e79b
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/01/2019
ms.locfileid: "71700977"
---
# <a name="how-to-sort-an-array-in-visual-basic"></a><span data-ttu-id="48212-102">如何：在 Visual Basic 中对数组进行排序</span><span class="sxs-lookup"><span data-stu-id="48212-102">How to: sort an array in Visual Basic</span></span>

<span data-ttu-id="48212-103">本文演示如何对 Visual Basic 中的字符串数组进行排序。</span><span class="sxs-lookup"><span data-stu-id="48212-103">This article shows an example of how to sort an array of strings in Visual Basic.</span></span>

## <a name="example"></a><span data-ttu-id="48212-104">示例</span><span class="sxs-lookup"><span data-stu-id="48212-104">Example</span></span>

<span data-ttu-id="48212-105">此示例声明一个名为 @no__t @no__t 0 个对象的数组，填充该数组，然后按字母顺序对其进行排序：</span><span class="sxs-lookup"><span data-stu-id="48212-105">This example declares an array of `String` objects named `zooAnimals`, populates it, and then sorts it alphabetically:</span></span>
  
```vb
Private Sub SortAnimals()
    Dim zooAnimals(2) As String
    zooAnimals(0) = "lion"
    zooAnimals(1) = "turtle"
    zooAnimals(2) = "ostrich"
    Array.Sort(zooAnimals)
End Sub
```

## <a name="robust-programming"></a><span data-ttu-id="48212-106">可靠编程</span><span class="sxs-lookup"><span data-stu-id="48212-106">Robust programming</span></span>

<span data-ttu-id="48212-107">以下情况可能会导致异常：</span><span class="sxs-lookup"><span data-stu-id="48212-107">The following conditions may cause an exception:</span></span>

- <span data-ttu-id="48212-108">数组为空（<xref:System.ArgumentNullException> 类）。</span><span class="sxs-lookup"><span data-stu-id="48212-108">Array is empty (<xref:System.ArgumentNullException> class).</span></span>
- <span data-ttu-id="48212-109">Array 为多维（@no__t 0 类）。</span><span class="sxs-lookup"><span data-stu-id="48212-109">Array is multidimensional (<xref:System.RankException> class).</span></span>
- <span data-ttu-id="48212-110">数组中的一个或多个元素未实现 @no__t 的接口（@no__t 1 类）。</span><span class="sxs-lookup"><span data-stu-id="48212-110">One or more elements of the array don't implement the <xref:System.IComparable> interface (<xref:System.InvalidOperationException> class).</span></span>

## <a name="see-also"></a><span data-ttu-id="48212-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="48212-111">See also</span></span>

- <xref:System.Array.Sort%2A?displayProperty=nameWithType>
- [<span data-ttu-id="48212-112">数组</span><span class="sxs-lookup"><span data-stu-id="48212-112">Arrays</span></span>](index.md)
- [<span data-ttu-id="48212-113">数组疑难解答</span><span class="sxs-lookup"><span data-stu-id="48212-113">Troubleshooting Arrays</span></span>](troubleshooting-arrays.md)
- [<span data-ttu-id="48212-114">集合</span><span class="sxs-lookup"><span data-stu-id="48212-114">Collections</span></span>](../../concepts/collections.md)
- [<span data-ttu-id="48212-115">For Each...Next 语句</span><span class="sxs-lookup"><span data-stu-id="48212-115">For Each...Next Statement</span></span>](../../../language-reference/statements/for-each-next-statement.md)
