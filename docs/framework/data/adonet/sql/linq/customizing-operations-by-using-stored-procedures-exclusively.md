---
title: 通过仅使用存储过程自定义操作
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 441e8ef3-998c-4d12-8825-ce66a178f90f
ms.openlocfilehash: 3c60a9e430b4228117fd03a43a30f27342154b1b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33357509"
---
# <a name="customizing-operations-by-using-stored-procedures-exclusively"></a><span data-ttu-id="5512e-102">通过仅使用存储过程自定义操作</span><span class="sxs-lookup"><span data-stu-id="5512e-102">Customizing Operations by Using Stored Procedures Exclusively</span></span>
<span data-ttu-id="5512e-103">通过仅使用存储过程来访问数据是常见的情况。</span><span class="sxs-lookup"><span data-stu-id="5512e-103">Access to data by using only stored procedures is a common scenario.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5512e-104">示例</span><span class="sxs-lookup"><span data-stu-id="5512e-104">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="5512e-105">描述</span><span class="sxs-lookup"><span data-stu-id="5512e-105">Description</span></span>  
 <span data-ttu-id="5512e-106">你可以修改提供的示例[自定义操作通过使用存储过程](../../../../../../docs/framework/data/adonet/sql/linq/customizing-operations-by-using-stored-procedures.md)通过甚至第一个查询 （这会导致动态 SQL 执行） 将替换为用于包装存储的过程的方法调用。</span><span class="sxs-lookup"><span data-stu-id="5512e-106">You can modify the example provided in [Customizing Operations By Using Stored Procedures](../../../../../../docs/framework/data/adonet/sql/linq/customizing-operations-by-using-stored-procedures.md) by replacing even the first query (which causes dynamic SQL execution) with a method call that wraps a stored procedure.</span></span>  
  
 <span data-ttu-id="5512e-107">假定 `CustomersByCity` 就是此方法，如下面的示例所示。</span><span class="sxs-lookup"><span data-stu-id="5512e-107">Assume `CustomersByCity` is the method, as in the following example.</span></span>  
  
### <a name="code"></a><span data-ttu-id="5512e-108">代码</span><span class="sxs-lookup"><span data-stu-id="5512e-108">Code</span></span>  
 [!code-csharp[DLinqOverrideDefaultSproc#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqOverrideDefaultSproc/cs/northwind.cs#4)]
 [!code-vb[DLinqOverrideDefaultSproc#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqOverrideDefaultSproc/vb/northwind.vb#4)]  
  
 <span data-ttu-id="5512e-109">下面的代码不用任何动态 SQL 即可执行。</span><span class="sxs-lookup"><span data-stu-id="5512e-109">The following code executes without any dynamic SQL.</span></span>  
  
 [!code-csharp[DLinqOverrideDefaultSproc#5](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqOverrideDefaultSproc/cs/Program.cs#5)]
 [!code-vb[DLinqOverrideDefaultSproc#5](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqOverrideDefaultSproc/vb/Module1.vb#5)]  
  
## <a name="see-also"></a><span data-ttu-id="5512e-110">请参阅</span><span class="sxs-lookup"><span data-stu-id="5512e-110">See Also</span></span>  
 [<span data-ttu-id="5512e-111">开发人员在重写默认行为中的责任</span><span class="sxs-lookup"><span data-stu-id="5512e-111">Responsibilities of the Developer In Overriding Default Behavior</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/responsibilities-of-the-developer-in-overriding-default-behavior.md)
