---
title: USING (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 20f58b8f-6070-4456-b7e8-5ff3d6269273
ms.openlocfilehash: 9495e5daf88326c5a682172d835c3349fe79e571
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/04/2019
ms.locfileid: "70248749"
---
# <a name="using-entity-sql"></a><span data-ttu-id="3e623-102">USING (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="3e623-102">USING (Entity SQL)</span></span>
<span data-ttu-id="3e623-103">指定查询表达式中使用的命名空间。</span><span class="sxs-lookup"><span data-stu-id="3e623-103">Specifies namespaces used in a query expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3e623-104">语法</span><span class="sxs-lookup"><span data-stu-id="3e623-104">Syntax</span></span>  
  
```  
USING [ alias = ] namespace  
```  
  
## <a name="arguments"></a><span data-ttu-id="3e623-105">自变量</span><span class="sxs-lookup"><span data-stu-id="3e623-105">Arguments</span></span>  
 `alias`  
 <span data-ttu-id="3e623-106">指定用于限定命名空间的较短别名。</span><span class="sxs-lookup"><span data-stu-id="3e623-106">Specifies a shorter alias to qualify a namespace with.</span></span>  
  
 `namespace`  
 <span data-ttu-id="3e623-107">任何有效的命名空间。</span><span class="sxs-lookup"><span data-stu-id="3e623-107">Any valid namespace.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3e623-108">示例</span><span class="sxs-lookup"><span data-stu-id="3e623-108">Example</span></span>  
 <span data-ttu-id="3e623-109">以下 Entity SQL 查询使用 USING 运算符以指定查询表达式中使用的命名空间。</span><span class="sxs-lookup"><span data-stu-id="3e623-109">The following Entity SQL query uses the USING operator to specify namespaces used in a query expression.</span></span> <span data-ttu-id="3e623-110">若要编译并运行此查询，请执行下列步骤：</span><span class="sxs-lookup"><span data-stu-id="3e623-110">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="3e623-111">[按照如何：执行返回 PrimitiveType 结果](../how-to-execute-a-query-that-returns-primitivetype-results.md)的查询。</span><span class="sxs-lookup"><span data-stu-id="3e623-111">Follow the procedure in [How to: Execute a Query that Returns PrimitiveType Results](../how-to-execute-a-query-that-returns-primitivetype-results.md).</span></span>  
  
2. <span data-ttu-id="3e623-112">将以下查询作为参数传递给 `ExecutePrimitiveTypeQuery` 方法：</span><span class="sxs-lookup"><span data-stu-id="3e623-112">Pass the following query as an argument to the `ExecutePrimitiveTypeQuery` method:</span></span>  
  
```  
using SqlServer; RAND()  
```  
  
## <a name="see-also"></a><span data-ttu-id="3e623-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="3e623-113">See also</span></span>

- [<span data-ttu-id="3e623-114">命名空间</span><span class="sxs-lookup"><span data-stu-id="3e623-114">Namespaces</span></span>](namespaces-entity-sql.md)
- [<span data-ttu-id="3e623-115">实体 SQL 引用</span><span class="sxs-lookup"><span data-stu-id="3e623-115">Entity SQL Reference</span></span>](entity-sql-reference.md)
