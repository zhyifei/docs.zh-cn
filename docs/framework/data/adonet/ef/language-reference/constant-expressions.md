---
title: "常量表达式"
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
ms.assetid: 9d98a7be-b110-4edb-8eba-bed10f250b6d
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: ccc54df7a69db8186c653afb415a5679b65ab50d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="constant-expressions"></a><span data-ttu-id="e26ee-102">常量表达式</span><span class="sxs-lookup"><span data-stu-id="e26ee-102">Constant Expressions</span></span>
<span data-ttu-id="e26ee-103">常量表达式由常量值组成。</span><span class="sxs-lookup"><span data-stu-id="e26ee-103">A constant expression consists of a constant value.</span></span> <span data-ttu-id="e26ee-104">常量值被直接转换为常量命令目录树表达式，而无需在客户端进行任何变换。</span><span class="sxs-lookup"><span data-stu-id="e26ee-104">Constant values are directly converted to constant command tree expressions, without any translation on the client.</span></span> <span data-ttu-id="e26ee-105">这包括产生常量值的表达式。</span><span class="sxs-lookup"><span data-stu-id="e26ee-105">This includes expressions that result in a constant value.</span></span> <span data-ttu-id="e26ee-106">因此，所有涉及常量的表达式都应具有数据源行为。</span><span class="sxs-lookup"><span data-stu-id="e26ee-106">Therefore, data source behavior should be expected for all expressions involving constants.</span></span> <span data-ttu-id="e26ee-107">这可能产生与 CLR 行为不同的行为。</span><span class="sxs-lookup"><span data-stu-id="e26ee-107">This can result in behavior that differs from CLR behavior.</span></span>  
  
 <span data-ttu-id="e26ee-108">下面的示例说明了一个在服务器上求值的常量表达式。</span><span class="sxs-lookup"><span data-stu-id="e26ee-108">The following example shows a constant expression that is evaluated on the server.</span></span>  
  
 [!code-csharp[DP L2E Conceptual Examples#ConstantExpression](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#constantexpression)]
 [!code-vb[DP L2E Conceptual Examples#ConstantExpression](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#constantexpression)]  
  
 [!INCLUDE[linq_entities](../../../../../../includes/linq-entities-md.md)]<span data-ttu-id="e26ee-109"> 不支持将用户类用作常量。</span><span class="sxs-lookup"><span data-stu-id="e26ee-109"> does not support using a user class as a constant.</span></span> <span data-ttu-id="e26ee-110">但是，用户类上的属性引用被视为常量，将转换为命令目录树常量表达式并在数据源上执行。</span><span class="sxs-lookup"><span data-stu-id="e26ee-110">However, a property reference on a user class is considered a constant, and will be converted to a command tree constant expression and executed on the data source.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e26ee-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="e26ee-111">See Also</span></span>  
 [<span data-ttu-id="e26ee-112">LINQ to Entities 查询中的表达式</span><span class="sxs-lookup"><span data-stu-id="e26ee-112">Expressions in LINQ to Entities Queries</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/expressions-in-linq-to-entities-queries.md)
