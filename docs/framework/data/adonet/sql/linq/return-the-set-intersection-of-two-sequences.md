---
title: "返回两个序列的交集"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: d09c344e-3548-4944-a3ed-051880e3f5b8
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 7ad505356c883969ddd044d89b5a33f5a2428f86
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="return-the-set-intersection-of-two-sequences"></a><span data-ttu-id="de993-102">返回两个序列的交集</span><span class="sxs-lookup"><span data-stu-id="de993-102">Return the Set Intersection of Two Sequences</span></span>
<span data-ttu-id="de993-103">使用 <xref:System.Linq.Queryable.Intersect%2A> 运算符可返回两个序列的交集。</span><span class="sxs-lookup"><span data-stu-id="de993-103">Use the <xref:System.Linq.Queryable.Intersect%2A> operator to return the set intersection of two sequences.</span></span>  
  
## <a name="example"></a><span data-ttu-id="de993-104">示例</span><span class="sxs-lookup"><span data-stu-id="de993-104">Example</span></span>  
 <span data-ttu-id="de993-105">此示例使用 <xref:System.Linq.Queryable.Intersect%2A> 返回既有 `Customers` 居住又有 `Employees` 居住的所有国家/地区的序列。</span><span class="sxs-lookup"><span data-stu-id="de993-105">This example uses <xref:System.Linq.Queryable.Intersect%2A> to return a sequence of all countries in which both `Customers` and `Employees` live.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#42](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#42)]
 [!code-vb[DLinqQueryExamples#42](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#42)]  
  
 <span data-ttu-id="de993-106">在 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 中，<xref:System.Linq.Queryable.Intersect%2A> 运算仅对集合而言是定义完善的。</span><span class="sxs-lookup"><span data-stu-id="de993-106">In [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], the <xref:System.Linq.Queryable.Intersect%2A> operation is well defined only on sets.</span></span> <span data-ttu-id="de993-107">针对多重集的语义尚未定义。</span><span class="sxs-lookup"><span data-stu-id="de993-107">The semantics for multisets is undefined.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="de993-108">请参阅</span><span class="sxs-lookup"><span data-stu-id="de993-108">See Also</span></span>  
 [<span data-ttu-id="de993-109">查询示例</span><span class="sxs-lookup"><span data-stu-id="de993-109">Query Examples</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/query-examples.md)  
 [<span data-ttu-id="de993-110">标准查询运算符转换</span><span class="sxs-lookup"><span data-stu-id="de993-110">Standard Query Operator Translation</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/standard-query-operator-translation.md)
