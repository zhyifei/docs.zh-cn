---
title: "泛型和数组（C# 编程指南）"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- generics [C#], arrays
- arrays [C#], generics
ms.assetid: 7d956536-3851-41b5-94ad-3e7c0a5fe485
caps.latest.revision: 17
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
ms.openlocfilehash: 46cea2733504e56aec5e65a4c9a8b655bc9431cf
ms.contentlocale: zh-cn
ms.lasthandoff: 07/28/2017

---
# <a name="generics-and-arrays-c-programming-guide"></a><span data-ttu-id="fb804-102">泛型和数组（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="fb804-102">Generics and Arrays (C# Programming Guide)</span></span>
<span data-ttu-id="fb804-103">在 C# 2.0 和更高版本中，下限为零的单维数组自动实现 <xref:System.Collections.Generic.IList%601>。</span><span class="sxs-lookup"><span data-stu-id="fb804-103">In C# 2.0 and later, single-dimensional arrays that have a lower bound of zero automatically implement <xref:System.Collections.Generic.IList%601>.</span></span> <span data-ttu-id="fb804-104">这可使你创建可使用相同代码循环访问数组和其他集合类型的泛型方法。</span><span class="sxs-lookup"><span data-stu-id="fb804-104">This enables you to create generic methods that can use the same code to iterate through arrays and other collection types.</span></span> <span data-ttu-id="fb804-105">此技术的主要用处在于读取集合中的数据。</span><span class="sxs-lookup"><span data-stu-id="fb804-105">This technique is primarily useful for reading data in collections.</span></span> <span data-ttu-id="fb804-106"><xref:System.Collections.Generic.IList%601> 接口无法用于添加元素或从数组删除元素。</span><span class="sxs-lookup"><span data-stu-id="fb804-106">The <xref:System.Collections.Generic.IList%601> interface cannot be used to add or remove elements from an array.</span></span> <span data-ttu-id="fb804-107">如果在此上下文中尝试对数组调用 <xref:System.Collections.Generic.IList%601> 方法（例如 <xref:System.Collections.Generic.IList%601.RemoveAt%2A>），则会引发异常。</span><span class="sxs-lookup"><span data-stu-id="fb804-107">An exception will be thrown if you try to call an <xref:System.Collections.Generic.IList%601> method such as <xref:System.Collections.Generic.IList%601.RemoveAt%2A> on an array in this context.</span></span>  
  
 <span data-ttu-id="fb804-108">如下代码示例演示具有 <xref:System.Collections.Generic.IList%601> 输入参数的单个泛型方法如何可循环访问列表和数组（此例中为整数数组）。</span><span class="sxs-lookup"><span data-stu-id="fb804-108">The following code example demonstrates how a single generic method that takes an <xref:System.Collections.Generic.IList%601> input parameter can iterate through both a list and an array, in this case an array of integers.</span></span>  
  
 <span data-ttu-id="fb804-109">[!code-cs[csProgGuideGenerics#35](../../../csharp/programming-guide/generics/codesnippet/CSharp/generics-and-arrays_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="fb804-109">[!code-cs[csProgGuideGenerics#35](../../../csharp/programming-guide/generics/codesnippet/CSharp/generics-and-arrays_1.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fb804-110">另请参阅</span><span class="sxs-lookup"><span data-stu-id="fb804-110">See Also</span></span>  
 <span data-ttu-id="fb804-111"><xref:System.Collections.Generic></span><span class="sxs-lookup"><span data-stu-id="fb804-111"><xref:System.Collections.Generic></span></span>   
 <span data-ttu-id="fb804-112">[C# 编程指南](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="fb804-112">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="fb804-113">[泛型](../../../csharp/programming-guide/generics/index.md) </span><span class="sxs-lookup"><span data-stu-id="fb804-113">[Generics](../../../csharp/programming-guide/generics/index.md) </span></span>  
 <span data-ttu-id="fb804-114">[数组](../../../csharp/programming-guide/arrays/index.md) </span><span class="sxs-lookup"><span data-stu-id="fb804-114">[Arrays](../../../csharp/programming-guide/arrays/index.md) </span></span>  
 [<span data-ttu-id="fb804-115">泛型</span><span class="sxs-lookup"><span data-stu-id="fb804-115">Generics</span></span>](~/docs/standard/generics/index.md)

