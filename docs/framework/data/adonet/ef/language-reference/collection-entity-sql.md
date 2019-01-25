---
title: COLLECTION (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 03228bfa-be3a-4ccc-82f8-eee429f85cf1
ms.openlocfilehash: d4e52bb62412e61e1a71e0fe9a8555068ca18dbd
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54506454"
---
# <a name="collection-entity-sql"></a><span data-ttu-id="24389-102">COLLECTION (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="24389-102">COLLECTION (Entity SQL)</span></span>
<span data-ttu-id="24389-103">COLLECTION 关键字仅在内联函数的定义中使用。</span><span class="sxs-lookup"><span data-stu-id="24389-103">The COLLECTION keyword is only used in the definition of an inline function.</span></span> <span data-ttu-id="24389-104">集合函数是对值的集合进行操作并生成标量输出的函数。</span><span class="sxs-lookup"><span data-stu-id="24389-104">Collection functions are functions that operate on a collection of values and produce a scalar output.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="24389-105">语法</span><span class="sxs-lookup"><span data-stu-id="24389-105">Syntax</span></span>  
  
```  
COLLECTION(type_definition)   
```  
  
## <a name="arguments"></a><span data-ttu-id="24389-106">自变量</span><span class="sxs-lookup"><span data-stu-id="24389-106">Arguments</span></span>  
 `type_definition`  
 <span data-ttu-id="24389-107">一个表达式，返回受支持类型、行或引用的集合。</span><span class="sxs-lookup"><span data-stu-id="24389-107">An expression that returns a collection of supported types, rows, or references.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="24389-108">备注</span><span class="sxs-lookup"><span data-stu-id="24389-108">Remarks</span></span>  
 <span data-ttu-id="24389-109">有关 COLLECTION 关键字的详细信息，请参阅 [Type Definitions](../../../../../../docs/framework/data/adonet/ef/language-reference/type-definitions-entity-sql.md)。</span><span class="sxs-lookup"><span data-stu-id="24389-109">For more information about the COLLECTION keyword, see [Type Definitions](../../../../../../docs/framework/data/adonet/ef/language-reference/type-definitions-entity-sql.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="24389-110">示例</span><span class="sxs-lookup"><span data-stu-id="24389-110">Example</span></span>  
 <span data-ttu-id="24389-111">下面的示例演示如何使用 COLLECTION 关键字将十进制值集合声明为内联查询函数的参数。</span><span class="sxs-lookup"><span data-stu-id="24389-111">The following sample shows how to use the COLLECTION keyword to declare a collection of decimals as an argument for an inline query function.</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#Collection_GroupPartition](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#collection_grouppartition)]  
  
## <a name="see-also"></a><span data-ttu-id="24389-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="24389-112">See also</span></span>
- [<span data-ttu-id="24389-113">实体 SQL 引用</span><span class="sxs-lookup"><span data-stu-id="24389-113">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
