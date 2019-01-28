---
title: 作为对象的数组 - C# 编程指南
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- arrays [C#], as objects
ms.assetid: f76d4403-bd0a-42a0-9bc8-694c55b2c926
ms.openlocfilehash: 0c4b5dcbd9e227e4edd5f549b687e3ded90ee9bc
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54740484"
---
# <a name="arrays-as-objects-c-programming-guide"></a><span data-ttu-id="c8c56-102">作为对象的数组（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="c8c56-102">Arrays as Objects (C# Programming Guide)</span></span>

<span data-ttu-id="c8c56-103">在 C# 中，数组实际上是对象，而不只是如在 C 和 C++ 中的连续内存的可寻址区域。</span><span class="sxs-lookup"><span data-stu-id="c8c56-103">In C#, arrays are actually objects, and not just addressable regions of contiguous memory as in C and C++.</span></span> <span data-ttu-id="c8c56-104"><xref:System.Array> 是所有数组类型的抽象基类型。</span><span class="sxs-lookup"><span data-stu-id="c8c56-104"><xref:System.Array> is the abstract base type of all array types.</span></span> <span data-ttu-id="c8c56-105">可以使用 <xref:System.Array> 具有的属性和其他类成员。</span><span class="sxs-lookup"><span data-stu-id="c8c56-105">You can use the properties, and other class members, that <xref:System.Array> has.</span></span> <span data-ttu-id="c8c56-106">例如，使用 <xref:System.Array.Length%2A> 属性来获取数组的长度。</span><span class="sxs-lookup"><span data-stu-id="c8c56-106">An example of this would be using the <xref:System.Array.Length%2A> property to get the length of an array.</span></span> <span data-ttu-id="c8c56-107">以下代码可将 `numbers` 数组的长度 `5` 分配给名为 `lengthOfNumbers` 的变量：</span><span class="sxs-lookup"><span data-stu-id="c8c56-107">The following code assigns the length of the `numbers` array, which is `5`, to a variable called `lengthOfNumbers`:</span></span>  
  
 [!code-csharp[csProgGuideArrays#3](../../../csharp/programming-guide/arrays/codesnippet/CSharp/arrays-as-objects_1.cs)]  
  
 <span data-ttu-id="c8c56-108"><xref:System.Array> 类可提供多种其他有用的方法和属性，用于对数组进行排序、搜索和复制。</span><span class="sxs-lookup"><span data-stu-id="c8c56-108">The <xref:System.Array> class provides many other useful methods and properties for sorting, searching, and copying arrays.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c8c56-109">示例</span><span class="sxs-lookup"><span data-stu-id="c8c56-109">Example</span></span>

 <span data-ttu-id="c8c56-110">此示例使用 <xref:System.Array.Rank%2A> 属性显示数组的维数。</span><span class="sxs-lookup"><span data-stu-id="c8c56-110">This example uses the <xref:System.Array.Rank%2A> property to display the number of dimensions of an array.</span></span>  
  
 [!code-csharp[csProgGuideArrays#2](../../../csharp/programming-guide/arrays/codesnippet/CSharp/arrays-as-objects_2.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="c8c56-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="c8c56-111">See also</span></span>

- [<span data-ttu-id="c8c56-112">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="c8c56-112">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="c8c56-113">数组</span><span class="sxs-lookup"><span data-stu-id="c8c56-113">Arrays</span></span>](../../../csharp/programming-guide/arrays/index.md)
- [<span data-ttu-id="c8c56-114">一维数组</span><span class="sxs-lookup"><span data-stu-id="c8c56-114">Single-Dimensional Arrays</span></span>](../../../csharp/programming-guide/arrays/single-dimensional-arrays.md)
- [<span data-ttu-id="c8c56-115">多维数组</span><span class="sxs-lookup"><span data-stu-id="c8c56-115">Multidimensional Arrays</span></span>](../../../csharp/programming-guide/arrays/multidimensional-arrays.md)
- [<span data-ttu-id="c8c56-116">交错数组</span><span class="sxs-lookup"><span data-stu-id="c8c56-116">Jagged Arrays</span></span>](../../../csharp/programming-guide/arrays/jagged-arrays.md)
