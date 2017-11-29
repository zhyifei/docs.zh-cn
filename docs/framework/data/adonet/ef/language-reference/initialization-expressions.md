---
title: "初始化表达式"
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
ms.assetid: 98daef1f-15d4-483e-985c-d78ea3abe8c8
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: dd5706c2eb09b0161d7eb1a4412471e9e75fcf75
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="initialization-expressions"></a><span data-ttu-id="23539-102">初始化表达式</span><span class="sxs-lookup"><span data-stu-id="23539-102">Initialization Expressions</span></span>
<span data-ttu-id="23539-103">初始化表达式用于初始化新的对象。</span><span class="sxs-lookup"><span data-stu-id="23539-103">An initialization expression initializes a new object.</span></span> <span data-ttu-id="23539-104">大多数初始化表达式都受到支持，其中包括大多数新的 C# 3.0 和 Visual Basic 9.0 初始化表达式。</span><span class="sxs-lookup"><span data-stu-id="23539-104">Most initialization expressions are supported, including most new C# 3.0 and Visual Basic 9.0 initialization expressions.</span></span> <span data-ttu-id="23539-105">LINQ to Entities 查询可以初始化并返回以下类型：</span><span class="sxs-lookup"><span data-stu-id="23539-105">The following types can be initialized and returned by a LINQ to Entities query:</span></span>  
  
-   <span data-ttu-id="23539-106">在概念模型中定义的零个或多个类型化实体对象的集合或复杂类型的投影。</span><span class="sxs-lookup"><span data-stu-id="23539-106">A collection of zero or more typed entity objects or a projection of complex types that are defined in the conceptual model.</span></span>  
  
-   <span data-ttu-id="23539-107">[!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)]支持的 CLR 类型。</span><span class="sxs-lookup"><span data-stu-id="23539-107">CLR types supported by the [!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)].</span></span>  
  
-   <span data-ttu-id="23539-108">内联集合。</span><span class="sxs-lookup"><span data-stu-id="23539-108">Inline collections.</span></span>  
  
-   <span data-ttu-id="23539-109">匿名类型。</span><span class="sxs-lookup"><span data-stu-id="23539-109">Anonymous types.</span></span>  
  
 <span data-ttu-id="23539-110">下面的示例中以查询表达式语法演示了匿名类型初始化：</span><span class="sxs-lookup"><span data-stu-id="23539-110">Anonymous type initialization is shown in the following example in query expression syntax:</span></span>  
  
 [!code-csharp[DP L2E Conceptual Examples#AnonymousTypeInitialization](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#anonymoustypeinitialization)]
 [!code-vb[DP L2E Conceptual Examples#AnonymousTypeInitialization](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#anonymoustypeinitialization)]  
  
 <span data-ttu-id="23539-111">下面的基于方法的查询语法示例说明了匿名类型初始化：</span><span class="sxs-lookup"><span data-stu-id="23539-111">The following example in method-based query syntax shows anonymous type initialization:</span></span>  
  
 [!code-csharp[DP L2E Conceptual Examples#AnonymousTypeInitialization_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#anonymoustypeinitialization_mq)]
 [!code-vb[DP L2E Conceptual Examples#AnonymousTypeInitialization_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#anonymoustypeinitialization_mq)]  
  
 <span data-ttu-id="23539-112">用户定义类的初始化也受到支持。</span><span class="sxs-lookup"><span data-stu-id="23539-112">User-defined class initialization is also supported.</span></span> <span data-ttu-id="23539-113">C# 3.0 和 Visual Basic 9.0 初始化模式受到支持，并且假定属性获取程序和设置程序是对称的。</span><span class="sxs-lookup"><span data-stu-id="23539-113">The C# 3.0 and Visual Basic 9.0 initialization pattern is supported and assumes that the property getter and setter are symmetric.</span></span> <span data-ttu-id="23539-114">下面的查询表达式语法示例说明了如何在查询中初始化自定义类：</span><span class="sxs-lookup"><span data-stu-id="23539-114">The following example in query expression syntax shows a custom class being initialized in the query:</span></span>  
  
 [!code-csharp[DP L2E Conceptual Examples#MyOrder](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#myorder)]
 [!code-vb[DP L2E Conceptual Examples#MyOrder](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#myorder)]  
  
 [!code-csharp[DP L2E Conceptual Examples#TypeInitialization](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#typeinitialization)]
 [!code-vb[DP L2E Conceptual Examples#TypeInitialization](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#typeinitialization)]  
  
 <span data-ttu-id="23539-115">下面的基于方法的查询语法示例说明了如何在查询中初始化自定义类：</span><span class="sxs-lookup"><span data-stu-id="23539-115">The following example in method-based query syntax shows a custom class being initialized in the query:</span></span>  
  
 [!code-csharp[DP L2E Conceptual Examples#TypeInitialization_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#typeinitialization_mq)]
 [!code-vb[DP L2E Conceptual Examples#TypeInitialization_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#typeinitialization_mq)]  
  
## <a name="see-also"></a><span data-ttu-id="23539-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="23539-116">See Also</span></span>  
 [<span data-ttu-id="23539-117">LINQ to Entities 查询中的表达式</span><span class="sxs-lookup"><span data-stu-id="23539-117">Expressions in LINQ to Entities Queries</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/expressions-in-linq-to-entities-queries.md)
