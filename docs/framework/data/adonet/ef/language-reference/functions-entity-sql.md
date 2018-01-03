---
title: "函数 (Entity SQL)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 52b3d776-5acc-4f69-b614-5a43ce56ef9f
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 11ce680f4a240c82b51b1651886e39d829976e84
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="functions-entity-sql"></a><span data-ttu-id="01cc8-102">函数 (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="01cc8-102">Functions (Entity SQL)</span></span>
<span data-ttu-id="01cc8-103">Entity SQL 支持用户定义函数、规范函数和提供程序特定的函数。</span><span class="sxs-lookup"><span data-stu-id="01cc8-103">Entity SQL supports user-defined functions, canonical functions, and provider-specific functions.</span></span> <span data-ttu-id="01cc8-104">用户定义函数在概念模型中指定，或在查询中内联指定。</span><span class="sxs-lookup"><span data-stu-id="01cc8-104">User-defined functions are specified in the conceptual model or inline in the query.</span></span> <span data-ttu-id="01cc8-105">有关详细信息，请参阅[用户定义函数](../../../../../../docs/framework/data/adonet/ef/language-reference/user-defined-functions-entity-sql.md)。</span><span class="sxs-lookup"><span data-stu-id="01cc8-105">For more information, see [User-Defined Functions](../../../../../../docs/framework/data/adonet/ef/language-reference/user-defined-functions-entity-sql.md).</span></span>  
  
 <span data-ttu-id="01cc8-106">在实体框架中对规范函数进行了预定义，因此数据提供程序将支持规范函数。</span><span class="sxs-lookup"><span data-stu-id="01cc8-106">Canonical functions are predefined in the Entity Framework and should be supported by data providers.</span></span> <span data-ttu-id="01cc8-107">如果用户调用提供程序不支持的函数，则 Entity SQL 命令将失败。</span><span class="sxs-lookup"><span data-stu-id="01cc8-107">Entity SQL commands will fail if a user calls a function that is not supported by a provider.</span></span> <span data-ttu-id="01cc8-108">因此，通常建议使用规范函数而不是存储特定的函数，后者位于提供程序特定的命名空间中。</span><span class="sxs-lookup"><span data-stu-id="01cc8-108">Therefore, canonical functions are generally recommended over store-specific functions, which are in a provider-specific namespace.</span></span> <span data-ttu-id="01cc8-109">有关详细信息，请参阅[规范函数](../../../../../../docs/framework/data/adonet/ef/language-reference/canonical-functions.md)。</span><span class="sxs-lookup"><span data-stu-id="01cc8-109">For more information, see [Canonical Functions](../../../../../../docs/framework/data/adonet/ef/language-reference/canonical-functions.md).</span></span>  
  
 <span data-ttu-id="01cc8-110">Microsoft SQL 客户端托管访问接口提供了一组提供程序特定的函数。</span><span class="sxs-lookup"><span data-stu-id="01cc8-110">The Microsoft SQL Client Managed Provider provides a set of provider-specific functions.</span></span> <span data-ttu-id="01cc8-111">有关详细信息，请参阅[用于实体框架函数的 SqlClient](../../../../../../docs/framework/data/adonet/ef/sqlclient-for-ef-functions.md)。</span><span class="sxs-lookup"><span data-stu-id="01cc8-111">For more information, see [SqlClient for Entity Framework Functions](../../../../../../docs/framework/data/adonet/ef/sqlclient-for-ef-functions.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="01cc8-112">本节内容</span><span class="sxs-lookup"><span data-stu-id="01cc8-112">In This Section</span></span>  
 [<span data-ttu-id="01cc8-113">用户定义的函数</span><span class="sxs-lookup"><span data-stu-id="01cc8-113">User-Defined Functions</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/user-defined-functions-entity-sql.md)  
  
 [<span data-ttu-id="01cc8-114">函数重载解析</span><span class="sxs-lookup"><span data-stu-id="01cc8-114">Function Overload Resolution</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/function-overload-resolution-entity-sql.md)  
  
 [<span data-ttu-id="01cc8-115">聚合函数</span><span class="sxs-lookup"><span data-stu-id="01cc8-115">Aggregate Functions</span></span>](../../../../../../docs/framework/data/adonet/ef/aggregate-functions-sqlclient-for-entity-framework.md)  
  
## <a name="see-also"></a><span data-ttu-id="01cc8-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="01cc8-116">See Also</span></span>  
 [<span data-ttu-id="01cc8-117">实体 SQL 概述</span><span class="sxs-lookup"><span data-stu-id="01cc8-117">Entity SQL Overview</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)
