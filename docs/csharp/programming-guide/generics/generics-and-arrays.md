---
title: 泛型和数组 - C# 编程指南
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- generics [C#], arrays
- arrays [C#], generics
ms.assetid: 7d956536-3851-41b5-94ad-3e7c0a5fe485
ms.openlocfilehash: 145203d259b943bea1f43a9e49db2c7889bf914a
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/28/2019
ms.locfileid: "56978901"
---
# <a name="generics-and-arrays-c-programming-guide"></a><span data-ttu-id="fdfd9-102">泛型和数组（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="fdfd9-102">Generics and Arrays (C# Programming Guide)</span></span>
<span data-ttu-id="fdfd9-103">在 C# 2.0 和更高版本中，下限为零的单维数组自动实现 <xref:System.Collections.Generic.IList%601>。</span><span class="sxs-lookup"><span data-stu-id="fdfd9-103">In C# 2.0 and later, single-dimensional arrays that have a lower bound of zero automatically implement <xref:System.Collections.Generic.IList%601>.</span></span> <span data-ttu-id="fdfd9-104">这可使你创建可使用相同代码循环访问数组和其他集合类型的泛型方法。</span><span class="sxs-lookup"><span data-stu-id="fdfd9-104">This enables you to create generic methods that can use the same code to iterate through arrays and other collection types.</span></span> <span data-ttu-id="fdfd9-105">此技术的主要用处在于读取集合中的数据。</span><span class="sxs-lookup"><span data-stu-id="fdfd9-105">This technique is primarily useful for reading data in collections.</span></span> <span data-ttu-id="fdfd9-106"><xref:System.Collections.Generic.IList%601> 接口无法用于添加元素或从数组删除元素。</span><span class="sxs-lookup"><span data-stu-id="fdfd9-106">The <xref:System.Collections.Generic.IList%601> interface cannot be used to add or remove elements from an array.</span></span> <span data-ttu-id="fdfd9-107">如果在此上下文中尝试对数组调用 <xref:System.Collections.Generic.IList%601> 方法（例如 <xref:System.Collections.Generic.IList%601.RemoveAt%2A>），则会引发异常。</span><span class="sxs-lookup"><span data-stu-id="fdfd9-107">An exception will be thrown if you try to call an <xref:System.Collections.Generic.IList%601> method such as <xref:System.Collections.Generic.IList%601.RemoveAt%2A> on an array in this context.</span></span>  
  
 <span data-ttu-id="fdfd9-108">如下代码示例演示具有 <xref:System.Collections.Generic.IList%601> 输入参数的单个泛型方法如何可循环访问列表和数组（此例中为整数数组）。</span><span class="sxs-lookup"><span data-stu-id="fdfd9-108">The following code example demonstrates how a single generic method that takes an <xref:System.Collections.Generic.IList%601> input parameter can iterate through both a list and an array, in this case an array of integers.</span></span>  
  
 [!code-csharp[csProgGuideGenerics#35](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#35)]  
  
## <a name="see-also"></a><span data-ttu-id="fdfd9-109">请参阅</span><span class="sxs-lookup"><span data-stu-id="fdfd9-109">See also</span></span>

- <xref:System.Collections.Generic>
- [<span data-ttu-id="fdfd9-110">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="fdfd9-110">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="fdfd9-111">泛型</span><span class="sxs-lookup"><span data-stu-id="fdfd9-111">Generics</span></span>](../../../csharp/programming-guide/generics/index.md)
- [<span data-ttu-id="fdfd9-112">数组</span><span class="sxs-lookup"><span data-stu-id="fdfd9-112">Arrays</span></span>](../../../csharp/programming-guide/arrays/index.md)
- [<span data-ttu-id="fdfd9-113">泛型</span><span class="sxs-lookup"><span data-stu-id="fdfd9-113">Generics</span></span>](~/docs/standard/generics/index.md)
