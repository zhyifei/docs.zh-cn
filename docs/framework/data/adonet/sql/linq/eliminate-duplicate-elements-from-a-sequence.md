---
title: "从序列中消除重复的元素"
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
ms.assetid: 2b224a84-bad5-4843-adcc-14e784d280f5
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 568b5e7553895c346f6a9de524ad6dd93117da43
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="eliminate-duplicate-elements-from-a-sequence"></a><span data-ttu-id="e62d5-102">从序列中消除重复的元素</span><span class="sxs-lookup"><span data-stu-id="e62d5-102">Eliminate Duplicate Elements from a Sequence</span></span>
<span data-ttu-id="e62d5-103">使用 <xref:System.Linq.Queryable.Distinct%2A> 运算符可从序列中消除重复元素。</span><span class="sxs-lookup"><span data-stu-id="e62d5-103">Use the <xref:System.Linq.Queryable.Distinct%2A> operator to eliminate duplicate elements from a sequence.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e62d5-104">示例</span><span class="sxs-lookup"><span data-stu-id="e62d5-104">Example</span></span>  
 <span data-ttu-id="e62d5-105">下面的示例使用 <xref:System.Linq.Queryable.Distinct%2A> 来选择有客户的唯一城市序列。</span><span class="sxs-lookup"><span data-stu-id="e62d5-105">The following example uses <xref:System.Linq.Queryable.Distinct%2A> to select a sequence of the unique cities that have customers.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#36](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#36)]
 [!code-vb[DLinqQueryExamples#36](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#36)]  
  
## <a name="see-also"></a><span data-ttu-id="e62d5-106">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e62d5-106">See Also</span></span>  
 [<span data-ttu-id="e62d5-107">查询示例</span><span class="sxs-lookup"><span data-stu-id="e62d5-107">Query Examples</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/query-examples.md)
