---
title: "用户定义的函数 (Entity SQL)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3f9e6bbd-8e5a-43e1-809f-f8a61338e522
caps.latest.revision: "3"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 4e5cfc9685c1e088722b24b54b4a0368d52fda29
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/19/2018
---
# <a name="user-defined-functions-entity-sql"></a><span data-ttu-id="605c3-102">用户定义的函数 (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="605c3-102">User-Defined Functions (Entity SQL)</span></span>
<span data-ttu-id="605c3-103">Entity SQL 支持在查询中调用用户定义函数。</span><span class="sxs-lookup"><span data-stu-id="605c3-103">Entity SQL supports calling user-defined functions in a query.</span></span> <span data-ttu-id="605c3-104">你可以定义随查询一起这些函数的内联 (请参阅[如何： 调用用户定义函数](http://msdn.microsoft.com/library/ad131b86-8b4e-4747-8605-d4fc64fb9d02)) 或作为概念模型的一部分 (请参阅[如何： 在概念模型中定义自定义函数](http://msdn.microsoft.com/library/0dad7b8b-58f6-4271-b238-f34810d68e5f))。</span><span class="sxs-lookup"><span data-stu-id="605c3-104">You can define these functions inline with the query (see [How to: Call a User-Defined Function](http://msdn.microsoft.com/library/ad131b86-8b4e-4747-8605-d4fc64fb9d02)) or as part of the conceptual model (see [How to: Define Custom Functions in the Conceptual Model](http://msdn.microsoft.com/library/0dad7b8b-58f6-4271-b238-f34810d68e5f)).</span></span> <span data-ttu-id="605c3-105">概念模型函数定义中的 Entity SQL 命令为[DefiningExpression](http://msdn.microsoft.com/library/d3da8d8b-a048-47ee-8d81-0c2ea3acdd3e)元素[函数](http://msdn.microsoft.com/library/dc3beca7-55cf-4977-8db0-5064cdbab134)概念模型中的元素。</span><span class="sxs-lookup"><span data-stu-id="605c3-105">Conceptual model functions are defined as an Entity SQL command in the [DefiningExpression](http://msdn.microsoft.com/library/d3da8d8b-a048-47ee-8d81-0c2ea3acdd3e) element of a [Function](http://msdn.microsoft.com/library/dc3beca7-55cf-4977-8db0-5064cdbab134) element in the conceptual model.</span></span>  
  
 <span data-ttu-id="605c3-106">通过 Entity SQL，您可以在查询命令自身中定义函数。</span><span class="sxs-lookup"><span data-stu-id="605c3-106">Entity SQL enables you to define functions in the query command itself.</span></span> <span data-ttu-id="605c3-107">[函数](../../../../../../docs/framework/data/adonet/ef/language-reference/function-entity-sql.md)运算符定义内联函数。</span><span class="sxs-lookup"><span data-stu-id="605c3-107">The [FUNCTION](../../../../../../docs/framework/data/adonet/ef/language-reference/function-entity-sql.md) operator defines inline functions.</span></span> <span data-ttu-id="605c3-108">您可以在单个命令中定义多个函数，这些函数可以具有相同的函数名称，只要函数签名是唯一的。</span><span class="sxs-lookup"><span data-stu-id="605c3-108">You can define multiple functions in a single command, and these functions can have the same function name, as long as the function signatures are unique.</span></span> <span data-ttu-id="605c3-109">有关详细信息，请参阅 [Function Overload Resolution](../../../../../../docs/framework/data/adonet/ef/language-reference/function-overload-resolution-entity-sql.md)。</span><span class="sxs-lookup"><span data-stu-id="605c3-109">For more information, see [Function Overload Resolution](../../../../../../docs/framework/data/adonet/ef/language-reference/function-overload-resolution-entity-sql.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="605c3-110">请参阅</span><span class="sxs-lookup"><span data-stu-id="605c3-110">See Also</span></span>  
 [<span data-ttu-id="605c3-111">函数</span><span class="sxs-lookup"><span data-stu-id="605c3-111">Functions</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/functions-entity-sql.md)
