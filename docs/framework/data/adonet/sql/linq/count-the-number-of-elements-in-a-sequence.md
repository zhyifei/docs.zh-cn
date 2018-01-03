---
title: "对序列中元素的数目进行计数"
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
ms.assetid: ccbe5d54-c9eb-4b14-b0ab-f628483c5f99
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: f6d1403384b8725720abbe9a81f98cbbfdb9c6e3
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="count-the-number-of-elements-in-a-sequence"></a><span data-ttu-id="97f92-102">对序列中元素的数目进行计数</span><span class="sxs-lookup"><span data-stu-id="97f92-102">Count the Number of Elements in a Sequence</span></span>
<span data-ttu-id="97f92-103">使用 <xref:System.Linq.Enumerable.Count%2A> 运算符可计算序列中的元素数目。</span><span class="sxs-lookup"><span data-stu-id="97f92-103">Use the <xref:System.Linq.Enumerable.Count%2A> operator to count the number of elements in a sequence.</span></span>  
  
 <span data-ttu-id="97f92-104">对 Northwind 示例数据库运行此查询产生的输出为 `91`。</span><span class="sxs-lookup"><span data-stu-id="97f92-104">Running this query against the Northwind sample database produces an output of `91`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="97f92-105">示例</span><span class="sxs-lookup"><span data-stu-id="97f92-105">Example</span></span>  
 <span data-ttu-id="97f92-106">下面的示例计算数据库中的 `Customers` 数目。</span><span class="sxs-lookup"><span data-stu-id="97f92-106">The following example counts the number of `Customers` in the database.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#4)]
 [!code-vb[DLinqQueryExamples#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#4)]  
  
## <a name="example"></a><span data-ttu-id="97f92-107">示例</span><span class="sxs-lookup"><span data-stu-id="97f92-107">Example</span></span>  
 <span data-ttu-id="97f92-108">下面的示例计算数据库中尚未停产的产品数目。</span><span class="sxs-lookup"><span data-stu-id="97f92-108">The following example counts the number of products in the database that have not been discontinued.</span></span>  
  
 <span data-ttu-id="97f92-109">对 Northwind 示例数据库运行此示例产生的输出为 `69`。</span><span class="sxs-lookup"><span data-stu-id="97f92-109">Running this example against the Northwind sample database produces an output of `69`.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#5](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#5)]
 [!code-vb[DLinqQueryExamples#5](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#5)]  
  
## <a name="see-also"></a><span data-ttu-id="97f92-110">请参阅</span><span class="sxs-lookup"><span data-stu-id="97f92-110">See Also</span></span>  
 [<span data-ttu-id="97f92-111">聚合查询</span><span class="sxs-lookup"><span data-stu-id="97f92-111">Aggregate Queries</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/aggregate-queries.md)  
 [<span data-ttu-id="97f92-112">下载示例数据库</span><span class="sxs-lookup"><span data-stu-id="97f92-112">Downloading Sample Databases</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md)
