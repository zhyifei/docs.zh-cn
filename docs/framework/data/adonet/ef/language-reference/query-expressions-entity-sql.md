---
title: "查询表达式 (Entity SQL)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c36f327b-e230-48d4-bbd5-78dc6478c447
caps.latest.revision: "2"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 46777cbe47e7d97fd3baaa1353787f33cff9f0aa
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2018
---
# <a name="query-expressions-entity-sql"></a><span data-ttu-id="0bfae-102">查询表达式 (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="0bfae-102">Query Expressions (Entity SQL)</span></span>
<span data-ttu-id="0bfae-103">查询表达式将许多不同的查询运算符组合成单个语法。</span><span class="sxs-lookup"><span data-stu-id="0bfae-103">A query expression combines many different query operators into a single syntax.</span></span> [!INCLUDE[esql](../../../../../../includes/esql-md.md)]<span data-ttu-id="0bfae-104">提供了各种类型的表达式，包括以下：[文本](../../../../../../docs/framework/data/adonet/ef/language-reference/literals-entity-sql.md)，[参数](../../../../../../docs/framework/data/adonet/ef/language-reference/parameters-entity-sql.md)，[变量](../../../../../../docs/framework/data/adonet/ef/language-reference/variables-entity-sql.md)，运算符，[函数](../../../../../../docs/framework/data/adonet/ef/language-reference/functions-entity-sql.md)、 集运算符，依次类推。</span><span class="sxs-lookup"><span data-stu-id="0bfae-104"> provides various kinds of expressions, including the following: [literals](../../../../../../docs/framework/data/adonet/ef/language-reference/literals-entity-sql.md), [parameters](../../../../../../docs/framework/data/adonet/ef/language-reference/parameters-entity-sql.md), [variables](../../../../../../docs/framework/data/adonet/ef/language-reference/variables-entity-sql.md), operators, [functions](../../../../../../docs/framework/data/adonet/ef/language-reference/functions-entity-sql.md), set operators, and so on.</span></span> <span data-ttu-id="0bfae-105">有关详细信息，请参阅[实体 SQL 引用](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)。</span><span class="sxs-lookup"><span data-stu-id="0bfae-105">For more information, see [Entity SQL Reference](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md).</span></span>  
  
## <a name="clauses"></a><span data-ttu-id="0bfae-106">子句</span><span class="sxs-lookup"><span data-stu-id="0bfae-106">Clauses</span></span>  
 <span data-ttu-id="0bfae-107">查询表达式由一系列子句组成，这些子句将连续的操作应用于一个对象集合。</span><span class="sxs-lookup"><span data-stu-id="0bfae-107">A query expression is composed of a series of clauses that apply successive operations to a collection of objects.</span></span> <span data-ttu-id="0bfae-108">基于位于标准 SQL select 语句的相同子句：[选择](../../../../../../docs/framework/data/adonet/ef/language-reference/select-entity-sql.md)， [FROM](../../../../../../docs/framework/data/adonet/ef/language-reference/from-entity-sql.md)，[其中](../../../../../../docs/framework/data/adonet/ef/language-reference/where-entity-sql.md)， [GROUP BY](../../../../../../docs/framework/data/adonet/ef/language-reference/group-by-entity-sql.md)， [具有](../../../../../../docs/framework/data/adonet/ef/language-reference/having-entity-sql.md)，和[ORDER BY](../../../../../../docs/framework/data/adonet/ef/language-reference/order-by-entity-sql.md)。</span><span class="sxs-lookup"><span data-stu-id="0bfae-108">They are based on the same clauses found in standard a SQL select statement: [SELECT](../../../../../../docs/framework/data/adonet/ef/language-reference/select-entity-sql.md), [FROM](../../../../../../docs/framework/data/adonet/ef/language-reference/from-entity-sql.md), [WHERE](../../../../../../docs/framework/data/adonet/ef/language-reference/where-entity-sql.md), [GROUP BY](../../../../../../docs/framework/data/adonet/ef/language-reference/group-by-entity-sql.md), [HAVING](../../../../../../docs/framework/data/adonet/ef/language-reference/having-entity-sql.md), and [ORDER BY](../../../../../../docs/framework/data/adonet/ef/language-reference/order-by-entity-sql.md).</span></span>  
  
## <a name="scope"></a><span data-ttu-id="0bfae-109">范围</span><span class="sxs-lookup"><span data-stu-id="0bfae-109">Scope</span></span>  
 <span data-ttu-id="0bfae-110">在 FROM 子句中定义的名称以从左到右的出现顺序引入到 FROM 作用域。</span><span class="sxs-lookup"><span data-stu-id="0bfae-110">Names defined in the FROM clause are introduced into the FROM scope in order of appearance, left to right.</span></span> <span data-ttu-id="0bfae-111">在 JOIN 列表中，表达式可以引用以前在列表中定义的名称。</span><span class="sxs-lookup"><span data-stu-id="0bfae-111">In the JOIN list, expressions can refer to names defined earlier in the list.</span></span> <span data-ttu-id="0bfae-112">在 FROM 子句中标识的元素的公共属性不添加到 FROM 作用域：始终必须通过别名限定名称来引用这些属性。</span><span class="sxs-lookup"><span data-stu-id="0bfae-112">Public properties of elements identified in the FROM clause are not added to the FROM scope: They must be always referenced through the alias-qualified name.</span></span> <span data-ttu-id="0bfae-113">通常，SELECT 表达式的所有部分都视作在 FROM 作用域内。</span><span class="sxs-lookup"><span data-stu-id="0bfae-113">Normally, all parts of the select expression are considered within the FROM scope.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0bfae-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="0bfae-114">See Also</span></span>  
 [<span data-ttu-id="0bfae-115">实体 SQL 引用</span><span class="sxs-lookup"><span data-stu-id="0bfae-115">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
