---
title: + （添加）
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-ado
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 51769b02-a8f7-4177-9e99-bbd10e77092c
caps.latest.revision: ''
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload:
- dotnet
ms.openlocfilehash: 6014b2b37d3574af8462ec178f943340af6d7146
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/19/2018
---
# <a name="-add"></a><span data-ttu-id="1c433-102">+（添加）</span><span class="sxs-lookup"><span data-stu-id="1c433-102">+ (Add)</span></span>
<span data-ttu-id="1c433-103">将两个数相加。</span><span class="sxs-lookup"><span data-stu-id="1c433-103">Adds two numbers.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1c433-104">语法</span><span class="sxs-lookup"><span data-stu-id="1c433-104">Syntax</span></span>  
  
```  
expression + expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="1c433-105">自变量</span><span class="sxs-lookup"><span data-stu-id="1c433-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="1c433-106">任何一种数值数据类型的任何有效表达式。</span><span class="sxs-lookup"><span data-stu-id="1c433-106">Any valid expression of any one of the numeric data types.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="1c433-107">结果类型</span><span class="sxs-lookup"><span data-stu-id="1c433-107">Result Types</span></span>  
 <span data-ttu-id="1c433-108">对这两个参数进行隐式类型提升而产生的数据类型。</span><span class="sxs-lookup"><span data-stu-id="1c433-108">The data type that results from the implicit type promotion of the two arguments.</span></span> <span data-ttu-id="1c433-109">有关隐式类型提升的详细信息，请参阅[类型系统](../../../../../../docs/framework/data/adonet/ef/language-reference/type-system-entity-sql.md)。</span><span class="sxs-lookup"><span data-stu-id="1c433-109">For more information about implicit type promotion, see [Type System](../../../../../../docs/framework/data/adonet/ef/language-reference/type-system-entity-sql.md).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1c433-110">备注</span><span class="sxs-lookup"><span data-stu-id="1c433-110">Remarks</span></span>  
 <span data-ttu-id="1c433-111">对于 EDM.String 类型，加法指的是串联。</span><span class="sxs-lookup"><span data-stu-id="1c433-111">For EDM.String types, addition is concatenation.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1c433-112">示例</span><span class="sxs-lookup"><span data-stu-id="1c433-112">Example</span></span>  
 <span data-ttu-id="1c433-113">以下 Entity SQL 查询使用 + 算术运算符将两个数值相加。</span><span class="sxs-lookup"><span data-stu-id="1c433-113">The following Entity SQL query uses the + arithmetic operator to add two numbers.</span></span> <span data-ttu-id="1c433-114">此查询基于 AdventureWorks 销售模型。</span><span class="sxs-lookup"><span data-stu-id="1c433-114">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="1c433-115">若要编译并运行此查询，请执行下列步骤：</span><span class="sxs-lookup"><span data-stu-id="1c433-115">To compile and run this query, follow these steps:</span></span>  
  
1.  <span data-ttu-id="1c433-116">执行 [如何：执行返回 StructuralType 结果的查询](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md)中的过程。</span><span class="sxs-lookup"><span data-stu-id="1c433-116">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2.  <span data-ttu-id="1c433-117">将以下查询作为参数传递给 `ExecuteStructuralTypeQuery` 方法：</span><span class="sxs-lookup"><span data-stu-id="1c433-117">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#ADD](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#add)]  
  
## <a name="see-also"></a><span data-ttu-id="1c433-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="1c433-118">See Also</span></span>  
 [<span data-ttu-id="1c433-119">实体 SQL 引用</span><span class="sxs-lookup"><span data-stu-id="1c433-119">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)  
 [<span data-ttu-id="1c433-120">概念模型类型 (CSDL)</span><span class="sxs-lookup"><span data-stu-id="1c433-120">Conceptual Model Types (CSDL)</span></span>](http://msdn.microsoft.com/library/987b995f-e429-4569-9559-b4146744def4)
