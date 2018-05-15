---
title: COLLECTION (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 03228bfa-be3a-4ccc-82f8-eee429f85cf1
ms.openlocfilehash: 2b13d373e6c54221249b17de4fa91347cbc0f9e6
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
---
# <a name="collection-entity-sql"></a><span data-ttu-id="d7719-102">COLLECTION (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="d7719-102">COLLECTION (Entity SQL)</span></span>
<span data-ttu-id="d7719-103">COLLECTION 关键字仅在内联函数的定义中使用。</span><span class="sxs-lookup"><span data-stu-id="d7719-103">The COLLECTION keyword is only used in the definition of an inline function.</span></span> <span data-ttu-id="d7719-104">集合函数是对值的集合进行操作并生成标量输出的函数。</span><span class="sxs-lookup"><span data-stu-id="d7719-104">Collection functions are functions that operate on a collection of values and produce a scalar output.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d7719-105">语法</span><span class="sxs-lookup"><span data-stu-id="d7719-105">Syntax</span></span>  
  
```  
COLLECTION(type_definition)   
```  
  
## <a name="arguments"></a><span data-ttu-id="d7719-106">自变量</span><span class="sxs-lookup"><span data-stu-id="d7719-106">Arguments</span></span>  
 `type_definition`  
 <span data-ttu-id="d7719-107">一个表达式，返回受支持类型、行或引用的集合。</span><span class="sxs-lookup"><span data-stu-id="d7719-107">An expression that returns a collection of supported types, rows, or references.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d7719-108">备注</span><span class="sxs-lookup"><span data-stu-id="d7719-108">Remarks</span></span>  
 <span data-ttu-id="d7719-109">有关 COLLECTION 关键字的详细信息，请参阅 [Type Definitions](../../../../../../docs/framework/data/adonet/ef/language-reference/type-definitions-entity-sql.md)。</span><span class="sxs-lookup"><span data-stu-id="d7719-109">For more information about the COLLECTION keyword, see [Type Definitions](../../../../../../docs/framework/data/adonet/ef/language-reference/type-definitions-entity-sql.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="d7719-110">示例</span><span class="sxs-lookup"><span data-stu-id="d7719-110">Example</span></span>  
 <span data-ttu-id="d7719-111">下面的示例演示如何使用 COLLECTION 关键字将十进制值集合声明为内联查询函数的参数。</span><span class="sxs-lookup"><span data-stu-id="d7719-111">The following sample shows how to use the COLLECTION keyword to declare a collection of decimals as an argument for an inline query function.</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#Collection_GroupPartition](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#collection_grouppartition)]  
  
## <a name="see-also"></a><span data-ttu-id="d7719-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="d7719-112">See Also</span></span>  
 [<span data-ttu-id="d7719-113">实体 SQL 引用</span><span class="sxs-lookup"><span data-stu-id="d7719-113">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
