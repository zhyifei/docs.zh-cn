---
title: 将某一序列转换为泛型列表
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 7ab76d93-6898-4e75-b76f-290a66ecead8
ms.openlocfilehash: 43960d100cde7f746a56c023d305795e13bc04e7
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/04/2019
ms.locfileid: "70247872"
---
# <a name="convert-a-sequence-to-a-generic-list"></a><span data-ttu-id="a1cd2-102">将某一序列转换为泛型列表</span><span class="sxs-lookup"><span data-stu-id="a1cd2-102">Convert a Sequence to a Generic List</span></span>
<span data-ttu-id="a1cd2-103">使用 <xref:System.Linq.Enumerable.ToList%2A> 可从序列创建泛型列表。</span><span class="sxs-lookup"><span data-stu-id="a1cd2-103">Use <xref:System.Linq.Enumerable.ToList%2A> to create a generic List from a sequence.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a1cd2-104">示例</span><span class="sxs-lookup"><span data-stu-id="a1cd2-104">Example</span></span>  
 <span data-ttu-id="a1cd2-105">下面的示例使用 <xref:System.Linq.Enumerable.ToList%2A> 直接将查询的计算结果放入泛型 <xref:System.Collections.Generic.List%601>。</span><span class="sxs-lookup"><span data-stu-id="a1cd2-105">The following sample uses <xref:System.Linq.Enumerable.ToList%2A> to immediately evaluate a query into a generic <xref:System.Collections.Generic.List%601>.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#45](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#45)]
 [!code-vb[DLinqQueryExamples#45](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#45)]  
  
## <a name="see-also"></a><span data-ttu-id="a1cd2-106">请参阅</span><span class="sxs-lookup"><span data-stu-id="a1cd2-106">See also</span></span>

- [<span data-ttu-id="a1cd2-107">查询示例</span><span class="sxs-lookup"><span data-stu-id="a1cd2-107">Query Examples</span></span>](query-examples.md)
