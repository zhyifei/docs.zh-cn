---
title: USING (Entity SQL)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 20f58b8f-6070-4456-b7e8-5ff3d6269273
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: cc69dba9e70bb6bcc870b1cb92e98cb656cad98e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="using-entity-sql"></a><span data-ttu-id="123b6-102">USING (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="123b6-102">USING (Entity SQL)</span></span>
<span data-ttu-id="123b6-103">指定查询表达式中使用的命名空间。</span><span class="sxs-lookup"><span data-stu-id="123b6-103">Specifies namespaces used in a query expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="123b6-104">语法</span><span class="sxs-lookup"><span data-stu-id="123b6-104">Syntax</span></span>  
  
```  
USING [ alias = ] namespace  
```  
  
## <a name="arguments"></a><span data-ttu-id="123b6-105">自变量</span><span class="sxs-lookup"><span data-stu-id="123b6-105">Arguments</span></span>  
 `alias`  
 <span data-ttu-id="123b6-106">指定用于限定命名空间的较短别名。</span><span class="sxs-lookup"><span data-stu-id="123b6-106">Specifies a shorter alias to qualify a namespace with.</span></span>  
  
 `namespace`  
 <span data-ttu-id="123b6-107">任何有效的命名空间。</span><span class="sxs-lookup"><span data-stu-id="123b6-107">Any valid namespace.</span></span>  
  
## <a name="example"></a><span data-ttu-id="123b6-108">示例</span><span class="sxs-lookup"><span data-stu-id="123b6-108">Example</span></span>  
 <span data-ttu-id="123b6-109">以下 Entity SQL 查询使用 USING 运算符以指定查询表达式中使用的命名空间。</span><span class="sxs-lookup"><span data-stu-id="123b6-109">The following Entity SQL query uses the USING operator to specify namespaces used in a query expression.</span></span> <span data-ttu-id="123b6-110">若要编译并运行此查询，请执行下列步骤：</span><span class="sxs-lookup"><span data-stu-id="123b6-110">To compile and run this query, follow these steps:</span></span>  
  
1.  <span data-ttu-id="123b6-111">按照中的步骤[如何： 执行查询该返回 PrimitiveType 结果](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-primitivetype-results.md)。</span><span class="sxs-lookup"><span data-stu-id="123b6-111">Follow the procedure in [How to: Execute a Query that Returns PrimitiveType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-primitivetype-results.md).</span></span>  
  
2.  <span data-ttu-id="123b6-112">将以下查询作为参数传递给 `ExecutePrimitiveTypeQuery` 方法：</span><span class="sxs-lookup"><span data-stu-id="123b6-112">Pass the following query as an argument to the `ExecutePrimitiveTypeQuery` method:</span></span>  
  
```  
using SqlServer; RAND()  
```  
  
## <a name="see-also"></a><span data-ttu-id="123b6-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="123b6-113">See Also</span></span>  
 [<span data-ttu-id="123b6-114">命名空间</span><span class="sxs-lookup"><span data-stu-id="123b6-114">Namespaces</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/namespaces-entity-sql.md)  
 [<span data-ttu-id="123b6-115">实体 SQL 引用</span><span class="sxs-lookup"><span data-stu-id="123b6-115">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
