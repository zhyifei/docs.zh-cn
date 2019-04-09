---
title: 用户定义的函数 (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 3f9e6bbd-8e5a-43e1-809f-f8a61338e522
ms.openlocfilehash: 4922e7fada676a6c26042236ccdb6315d6d455ae
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59104619"
---
# <a name="user-defined-functions-entity-sql"></a><span data-ttu-id="f555d-102">用户定义的函数 (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="f555d-102">User-Defined Functions (Entity SQL)</span></span>
<span data-ttu-id="f555d-103">Entity SQL 支持在查询中调用用户定义函数。</span><span class="sxs-lookup"><span data-stu-id="f555d-103">Entity SQL supports calling user-defined functions in a query.</span></span> <span data-ttu-id="f555d-104">您可以定义与查询这些函数内联 (请参阅[如何：调用用户定义的函数](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/dd490951(v=vs.100))) 或为概念模型的一部分 (请参阅[如何：概念模型中定义自定义函数](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/dd456812(v=vs.100)))。</span><span class="sxs-lookup"><span data-stu-id="f555d-104">You can define these functions inline with the query (see [How to: Call a User-Defined Function](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/dd490951(v=vs.100))) or as part of the conceptual model (see [How to: Define Custom Functions in the Conceptual Model](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/dd456812(v=vs.100))).</span></span> <span data-ttu-id="f555d-105">概念模型函数定义为中的 Entity SQL 命令[DefiningExpression](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec#definingexpression-element-csdl)的元素[函数](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec#function-element-csdl)概念模型中的元素。</span><span class="sxs-lookup"><span data-stu-id="f555d-105">Conceptual model functions are defined as an Entity SQL command in the [DefiningExpression](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec#definingexpression-element-csdl) element of a [Function](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec#function-element-csdl) element in the conceptual model.</span></span>  
  
 <span data-ttu-id="f555d-106">通过 Entity SQL，您可以在查询命令自身中定义函数。</span><span class="sxs-lookup"><span data-stu-id="f555d-106">Entity SQL enables you to define functions in the query command itself.</span></span> <span data-ttu-id="f555d-107">[函数](../../../../../../docs/framework/data/adonet/ef/language-reference/function-entity-sql.md)运算符定义内联函数。</span><span class="sxs-lookup"><span data-stu-id="f555d-107">The [FUNCTION](../../../../../../docs/framework/data/adonet/ef/language-reference/function-entity-sql.md) operator defines inline functions.</span></span> <span data-ttu-id="f555d-108">您可以在单个命令中定义多个函数，这些函数可以具有相同的函数名称，只要函数签名是唯一的。</span><span class="sxs-lookup"><span data-stu-id="f555d-108">You can define multiple functions in a single command, and these functions can have the same function name, as long as the function signatures are unique.</span></span> <span data-ttu-id="f555d-109">有关详细信息，请参阅 [Function Overload Resolution](../../../../../../docs/framework/data/adonet/ef/language-reference/function-overload-resolution-entity-sql.md)。</span><span class="sxs-lookup"><span data-stu-id="f555d-109">For more information, see [Function Overload Resolution](../../../../../../docs/framework/data/adonet/ef/language-reference/function-overload-resolution-entity-sql.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f555d-110">请参阅</span><span class="sxs-lookup"><span data-stu-id="f555d-110">See also</span></span>

- [<span data-ttu-id="f555d-111">函数</span><span class="sxs-lookup"><span data-stu-id="f555d-111">Functions</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/functions-entity-sql.md)
