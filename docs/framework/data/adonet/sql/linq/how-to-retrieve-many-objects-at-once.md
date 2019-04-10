---
title: 如何：一次检索多个对象
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 18aff4d8-bde8-461b-9960-ccabb24e9d22
ms.openlocfilehash: dd53c2fd16a82ce0f69a33e0b7d7ffef7815b91b
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59220521"
---
# <a name="how-to-retrieve-many-objects-at-once"></a><span data-ttu-id="e8d5e-102">如何：一次检索多个对象</span><span class="sxs-lookup"><span data-stu-id="e8d5e-102">How to: Retrieve Many Objects At Once</span></span>
<span data-ttu-id="e8d5e-103">通过使用 <xref:System.Data.Linq.DataLoadOptions.LoadWith%2A>，可以在一个查询中检索许多对象。</span><span class="sxs-lookup"><span data-stu-id="e8d5e-103">You can retrieve many objects in one query by using <xref:System.Data.Linq.DataLoadOptions.LoadWith%2A>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e8d5e-104">示例</span><span class="sxs-lookup"><span data-stu-id="e8d5e-104">Example</span></span>  
 <span data-ttu-id="e8d5e-105">下面的代码使用 <xref:System.Data.Linq.DataLoadOptions.LoadWith%2A> 方法来同时检索 `Customer` 和 `Order` 对象。</span><span class="sxs-lookup"><span data-stu-id="e8d5e-105">The following code uses the <xref:System.Data.Linq.DataLoadOptions.LoadWith%2A> method to retrieve both `Customer` and `Order` objects.</span></span>  
  
 [!code-csharp[DLinqQueryConcepts#9](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryConcepts/cs/Program.cs#9)]
 [!code-vb[DLinqQueryConcepts#9](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryConcepts/vb/Module1.vb#9)]  
  
## <a name="see-also"></a><span data-ttu-id="e8d5e-106">请参阅</span><span class="sxs-lookup"><span data-stu-id="e8d5e-106">See also</span></span>

- [<span data-ttu-id="e8d5e-107">查询概念</span><span class="sxs-lookup"><span data-stu-id="e8d5e-107">Query Concepts</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/query-concepts.md)
