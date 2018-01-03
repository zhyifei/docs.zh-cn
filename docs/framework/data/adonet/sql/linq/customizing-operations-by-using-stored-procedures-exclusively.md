---
title: "通过仅使用存储过程自定义操作"
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
ms.assetid: 441e8ef3-998c-4d12-8825-ce66a178f90f
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: eba9e4462c1a71708173994dfb3efaf4199248c6
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="customizing-operations-by-using-stored-procedures-exclusively"></a><span data-ttu-id="d7fec-102">通过仅使用存储过程自定义操作</span><span class="sxs-lookup"><span data-stu-id="d7fec-102">Customizing Operations by Using Stored Procedures Exclusively</span></span>
<span data-ttu-id="d7fec-103">通过仅使用存储过程来访问数据是常见的情况。</span><span class="sxs-lookup"><span data-stu-id="d7fec-103">Access to data by using only stored procedures is a common scenario.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d7fec-104">示例</span><span class="sxs-lookup"><span data-stu-id="d7fec-104">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="d7fec-105">描述</span><span class="sxs-lookup"><span data-stu-id="d7fec-105">Description</span></span>  
 <span data-ttu-id="d7fec-106">你可以修改提供的示例[自定义操作通过使用存储过程](../../../../../../docs/framework/data/adonet/sql/linq/customizing-operations-by-using-stored-procedures.md)通过甚至第一个查询 （这会导致动态 SQL 执行） 将替换为用于包装存储的过程的方法调用。</span><span class="sxs-lookup"><span data-stu-id="d7fec-106">You can modify the example provided in [Customizing Operations By Using Stored Procedures](../../../../../../docs/framework/data/adonet/sql/linq/customizing-operations-by-using-stored-procedures.md) by replacing even the first query (which causes dynamic SQL execution) with a method call that wraps a stored procedure.</span></span>  
  
 <span data-ttu-id="d7fec-107">假定 `CustomersByCity` 就是此方法，如下面的示例所示。</span><span class="sxs-lookup"><span data-stu-id="d7fec-107">Assume `CustomersByCity` is the method, as in the following example.</span></span>  
  
### <a name="code"></a><span data-ttu-id="d7fec-108">代码</span><span class="sxs-lookup"><span data-stu-id="d7fec-108">Code</span></span>  
 [!code-csharp[DLinqOverrideDefaultSproc#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqOverrideDefaultSproc/cs/northwind.cs#4)]
 [!code-vb[DLinqOverrideDefaultSproc#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqOverrideDefaultSproc/vb/northwind.vb#4)]  
  
 <span data-ttu-id="d7fec-109">下面的代码不用任何动态 SQL 即可执行。</span><span class="sxs-lookup"><span data-stu-id="d7fec-109">The following code executes without any dynamic SQL.</span></span>  
  
 [!code-csharp[DLinqOverrideDefaultSproc#5](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqOverrideDefaultSproc/cs/Program.cs#5)]
 [!code-vb[DLinqOverrideDefaultSproc#5](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqOverrideDefaultSproc/vb/Module1.vb#5)]  
  
## <a name="see-also"></a><span data-ttu-id="d7fec-110">请参阅</span><span class="sxs-lookup"><span data-stu-id="d7fec-110">See Also</span></span>  
 [<span data-ttu-id="d7fec-111">开发人员在重写默认行为中的责任</span><span class="sxs-lookup"><span data-stu-id="d7fec-111">Responsibilities of the Developer In Overriding Default Behavior</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/responsibilities-of-the-developer-in-overriding-default-behavior.md)
