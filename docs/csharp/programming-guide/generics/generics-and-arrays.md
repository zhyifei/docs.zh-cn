---
title: "泛型和数组（C# 编程指南）"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords:
- generics [C#], arrays
- arrays [C#], generics
ms.assetid: 7d956536-3851-41b5-94ad-3e7c0a5fe485
caps.latest.revision: "17"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 94b144075fac44ff749474a5bfa8e81aaadc0a0c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="generics-and-arrays-c-programming-guide"></a><span data-ttu-id="15149-102">泛型和数组（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="15149-102">Generics and Arrays (C# Programming Guide)</span></span>
<span data-ttu-id="15149-103">在 C# 2.0 和更高版本中，下限为零的单维数组自动实现 <xref:System.Collections.Generic.IList%601>。</span><span class="sxs-lookup"><span data-stu-id="15149-103">In C# 2.0 and later, single-dimensional arrays that have a lower bound of zero automatically implement <xref:System.Collections.Generic.IList%601>.</span></span> <span data-ttu-id="15149-104">这可使你创建可使用相同代码循环访问数组和其他集合类型的泛型方法。</span><span class="sxs-lookup"><span data-stu-id="15149-104">This enables you to create generic methods that can use the same code to iterate through arrays and other collection types.</span></span> <span data-ttu-id="15149-105">此技术的主要用处在于读取集合中的数据。</span><span class="sxs-lookup"><span data-stu-id="15149-105">This technique is primarily useful for reading data in collections.</span></span> <span data-ttu-id="15149-106"><xref:System.Collections.Generic.IList%601> 接口无法用于添加元素或从数组删除元素。</span><span class="sxs-lookup"><span data-stu-id="15149-106">The <xref:System.Collections.Generic.IList%601> interface cannot be used to add or remove elements from an array.</span></span> <span data-ttu-id="15149-107">如果在此上下文中尝试对数组调用 <xref:System.Collections.Generic.IList%601> 方法（例如 <xref:System.Collections.Generic.IList%601.RemoveAt%2A>），则会引发异常。</span><span class="sxs-lookup"><span data-stu-id="15149-107">An exception will be thrown if you try to call an <xref:System.Collections.Generic.IList%601> method such as <xref:System.Collections.Generic.IList%601.RemoveAt%2A> on an array in this context.</span></span>  
  
 <span data-ttu-id="15149-108">如下代码示例演示具有 <xref:System.Collections.Generic.IList%601> 输入参数的单个泛型方法如何可循环访问列表和数组（此例中为整数数组）。</span><span class="sxs-lookup"><span data-stu-id="15149-108">The following code example demonstrates how a single generic method that takes an <xref:System.Collections.Generic.IList%601> input parameter can iterate through both a list and an array, in this case an array of integers.</span></span>  
  
 [!code-csharp[csProgGuideGenerics#35](../../../csharp/programming-guide/generics/codesnippet/CSharp/generics-and-arrays_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="15149-109">另请参阅</span><span class="sxs-lookup"><span data-stu-id="15149-109">See Also</span></span>  
 <xref:System.Collections.Generic>  
 [<span data-ttu-id="15149-110">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="15149-110">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="15149-111">泛型</span><span class="sxs-lookup"><span data-stu-id="15149-111">Generics</span></span>](../../../csharp/programming-guide/generics/index.md)  
 [<span data-ttu-id="15149-112">阵列</span><span class="sxs-lookup"><span data-stu-id="15149-112">Arrays</span></span>](../../../csharp/programming-guide/arrays/index.md)  
 [<span data-ttu-id="15149-113">泛型</span><span class="sxs-lookup"><span data-stu-id="15149-113">Generics</span></span>](~/docs/standard/generics/index.md)
