---
title: 用户定义的函数 (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 3f9e6bbd-8e5a-43e1-809f-f8a61338e522
ms.openlocfilehash: 9ddafb18a10ff2313fd27eab453907054a35218a
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/04/2019
ms.locfileid: "70248773"
---
# <a name="user-defined-functions-entity-sql"></a><span data-ttu-id="bfd55-102">用户定义的函数 (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="bfd55-102">User-Defined Functions (Entity SQL)</span></span>
<span data-ttu-id="bfd55-103">Entity SQL 支持在查询中调用用户定义函数。</span><span class="sxs-lookup"><span data-stu-id="bfd55-103">Entity SQL supports calling user-defined functions in a query.</span></span> <span data-ttu-id="bfd55-104">您可以通过查询以内联方式定义这些函数（ [请参阅如何：调用用户定义函数](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/dd490951(v=vs.100))）或作为概念模型的一部分（请参阅[如何：在概念模型](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/dd456812(v=vs.100))中定义自定义函数。</span><span class="sxs-lookup"><span data-stu-id="bfd55-104">You can define these functions inline with the query (see [How to: Call a User-Defined Function](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/dd490951(v=vs.100))) or as part of the conceptual model (see [How to: Define Custom Functions in the Conceptual Model](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/dd456812(v=vs.100))).</span></span> <span data-ttu-id="bfd55-105">概念模型函数在概念模型中的[函数](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec#function-element-csdl)元素的[DefiningExpression](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec#definingexpression-element-csdl)元素中定义为实体 SQL 命令。</span><span class="sxs-lookup"><span data-stu-id="bfd55-105">Conceptual model functions are defined as an Entity SQL command in the [DefiningExpression](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec#definingexpression-element-csdl) element of a [Function](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec#function-element-csdl) element in the conceptual model.</span></span>  
  
 <span data-ttu-id="bfd55-106">通过 Entity SQL，您可以在查询命令自身中定义函数。</span><span class="sxs-lookup"><span data-stu-id="bfd55-106">Entity SQL enables you to define functions in the query command itself.</span></span> <span data-ttu-id="bfd55-107">[函数](function-entity-sql.md)运算符定义内联函数。</span><span class="sxs-lookup"><span data-stu-id="bfd55-107">The [FUNCTION](function-entity-sql.md) operator defines inline functions.</span></span> <span data-ttu-id="bfd55-108">您可以在单个命令中定义多个函数，这些函数可以具有相同的函数名称，只要函数签名是唯一的。</span><span class="sxs-lookup"><span data-stu-id="bfd55-108">You can define multiple functions in a single command, and these functions can have the same function name, as long as the function signatures are unique.</span></span> <span data-ttu-id="bfd55-109">有关详细信息，请参阅 [Function Overload Resolution](function-overload-resolution-entity-sql.md)。</span><span class="sxs-lookup"><span data-stu-id="bfd55-109">For more information, see [Function Overload Resolution](function-overload-resolution-entity-sql.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bfd55-110">请参阅</span><span class="sxs-lookup"><span data-stu-id="bfd55-110">See also</span></span>

- [<span data-ttu-id="bfd55-111">函数</span><span class="sxs-lookup"><span data-stu-id="bfd55-111">Functions</span></span>](functions-entity-sql.md)
