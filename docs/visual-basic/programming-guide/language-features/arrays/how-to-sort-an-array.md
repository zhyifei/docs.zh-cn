---
title: 如何：对数组进行排序
ms.date: 07/20/2015
f1_keywords:
- Array.Sort
helpviewer_keywords:
- arrays [Visual Basic], sorting
- examples [Visual Basic], arrays
ms.assetid: 9289aeaa-9626-4698-94a7-1d1fd3702b87
ms.openlocfilehash: 3fb9af8de0fc86075fdccd64506c855c1c720660
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351856"
---
# <a name="how-to-sort-an-array-in-visual-basic"></a><span data-ttu-id="8218f-102">如何：在 Visual Basic 中对数组进行排序</span><span class="sxs-lookup"><span data-stu-id="8218f-102">How to: sort an array in Visual Basic</span></span>

<span data-ttu-id="8218f-103">本文演示如何对 Visual Basic 中的字符串数组进行排序。</span><span class="sxs-lookup"><span data-stu-id="8218f-103">This article shows an example of how to sort an array of strings in Visual Basic.</span></span>

## <a name="example"></a><span data-ttu-id="8218f-104">示例</span><span class="sxs-lookup"><span data-stu-id="8218f-104">Example</span></span>

<span data-ttu-id="8218f-105">此示例声明一个名为 `zooAnimals``String` 对象的数组，填充该数组，然后按字母顺序对其进行排序：</span><span class="sxs-lookup"><span data-stu-id="8218f-105">This example declares an array of `String` objects named `zooAnimals`, populates it, and then sorts it alphabetically:</span></span>
  
```vb
Private Sub SortAnimals()
    Dim zooAnimals(2) As String
    zooAnimals(0) = "lion"
    zooAnimals(1) = "turtle"
    zooAnimals(2) = "ostrich"
    Array.Sort(zooAnimals)
End Sub
```

## <a name="robust-programming"></a><span data-ttu-id="8218f-106">可靠编程</span><span class="sxs-lookup"><span data-stu-id="8218f-106">Robust programming</span></span>

<span data-ttu-id="8218f-107">以下情况可能会导致异常：</span><span class="sxs-lookup"><span data-stu-id="8218f-107">The following conditions may cause an exception:</span></span>

- <span data-ttu-id="8218f-108">数组为空（<xref:System.ArgumentNullException> 类）。</span><span class="sxs-lookup"><span data-stu-id="8218f-108">Array is empty (<xref:System.ArgumentNullException> class).</span></span>
- <span data-ttu-id="8218f-109">Array 为多维（<xref:System.RankException> 类）。</span><span class="sxs-lookup"><span data-stu-id="8218f-109">Array is multidimensional (<xref:System.RankException> class).</span></span>
- <span data-ttu-id="8218f-110">数组中的一个或多个元素未实现 <xref:System.IComparable> 接口（<xref:System.InvalidOperationException> 类）。</span><span class="sxs-lookup"><span data-stu-id="8218f-110">One or more elements of the array don't implement the <xref:System.IComparable> interface (<xref:System.InvalidOperationException> class).</span></span>

## <a name="see-also"></a><span data-ttu-id="8218f-111">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8218f-111">See also</span></span>

- <xref:System.Array.Sort%2A?displayProperty=nameWithType>
- [<span data-ttu-id="8218f-112">数组</span><span class="sxs-lookup"><span data-stu-id="8218f-112">Arrays</span></span>](index.md)
- [<span data-ttu-id="8218f-113">数组疑难解答</span><span class="sxs-lookup"><span data-stu-id="8218f-113">Troubleshooting Arrays</span></span>](troubleshooting-arrays.md)
- [<span data-ttu-id="8218f-114">集合</span><span class="sxs-lookup"><span data-stu-id="8218f-114">Collections</span></span>](../../concepts/collections.md)
- [<span data-ttu-id="8218f-115">For Each...Next 语句</span><span class="sxs-lookup"><span data-stu-id="8218f-115">For Each...Next Statement</span></span>](../../../language-reference/statements/for-each-next-statement.md)
