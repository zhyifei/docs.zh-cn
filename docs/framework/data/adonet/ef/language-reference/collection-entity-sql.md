---
title: COLLECTION (Entity SQL)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 03228bfa-be3a-4ccc-82f8-eee429f85cf1
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 8d078749d20740cdade323edab975ce221e72cfa
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="collection-entity-sql"></a><span data-ttu-id="13c11-102">COLLECTION (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="13c11-102">COLLECTION (Entity SQL)</span></span>
<span data-ttu-id="13c11-103">COLLECTION 关键字仅在内联函数的定义中使用。</span><span class="sxs-lookup"><span data-stu-id="13c11-103">The COLLECTION keyword is only used in the definition of an inline function.</span></span> <span data-ttu-id="13c11-104">集合函数是对值的集合进行操作并生成标量输出的函数。</span><span class="sxs-lookup"><span data-stu-id="13c11-104">Collection functions are functions that operate on a collection of values and produce a scalar output.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="13c11-105">语法</span><span class="sxs-lookup"><span data-stu-id="13c11-105">Syntax</span></span>  
  
```  
COLLECTION(type_definition)   
```  
  
## <a name="arguments"></a><span data-ttu-id="13c11-106">参数</span><span class="sxs-lookup"><span data-stu-id="13c11-106">Arguments</span></span>  
 `type_definition`  
 <span data-ttu-id="13c11-107">一个表达式，返回受支持类型、行或引用的集合。</span><span class="sxs-lookup"><span data-stu-id="13c11-107">An expression that returns a collection of supported types, rows, or references.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="13c11-108">备注</span><span class="sxs-lookup"><span data-stu-id="13c11-108">Remarks</span></span>  
 <span data-ttu-id="13c11-109">有关 COLLECTION 关键字的详细信息，请参阅 [Type Definitions](../../../../../../docs/framework/data/adonet/ef/language-reference/type-definitions-entity-sql.md)。</span><span class="sxs-lookup"><span data-stu-id="13c11-109">For more information about the COLLECTION keyword, see [Type Definitions](../../../../../../docs/framework/data/adonet/ef/language-reference/type-definitions-entity-sql.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="13c11-110">示例</span><span class="sxs-lookup"><span data-stu-id="13c11-110">Example</span></span>  
 <span data-ttu-id="13c11-111">下面的示例演示如何使用 COLLECTION 关键字将十进制值集合声明为内联查询函数的参数。</span><span class="sxs-lookup"><span data-stu-id="13c11-111">The following sample shows how to use the COLLECTION keyword to declare a collection of decimals as an argument for an inline query function.</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#Collection_GroupPartition](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#collection_grouppartition)]  
  
## <a name="see-also"></a><span data-ttu-id="13c11-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="13c11-112">See Also</span></span>  
 [<span data-ttu-id="13c11-113">实体 SQL 引用</span><span class="sxs-lookup"><span data-stu-id="13c11-113">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
