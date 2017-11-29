---
title: CAST (Entity SQL)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 07b6d750-dfd4-48a9-b86c-3badcbba6f70
caps.latest.revision: "4"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 353398f834aff5cefb3aed91899ce042df9df60a
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="cast-entity-sql"></a><span data-ttu-id="ae818-102">CAST (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="ae818-102">CAST (Entity SQL)</span></span>
<span data-ttu-id="ae818-103">将一种数据类型的表达式转换为另一种数据类型的表达式。</span><span class="sxs-lookup"><span data-stu-id="ae818-103">Converts an expression of one data type to another.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ae818-104">语法</span><span class="sxs-lookup"><span data-stu-id="ae818-104">Syntax</span></span>  
  
```  
CAST ( expression AS data_type )  
```  
  
## <a name="arguments"></a><span data-ttu-id="ae818-105">参数</span><span class="sxs-lookup"><span data-stu-id="ae818-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="ae818-106">任何可转换为 `data_type`的有效表达式。</span><span class="sxs-lookup"><span data-stu-id="ae818-106">Any valid expression that is convertible to `data_type`.</span></span>  
  
 `data_type`  
 <span data-ttu-id="ae818-107">系统提供的目标数据类型。</span><span class="sxs-lookup"><span data-stu-id="ae818-107">The target system-supplied data type.</span></span> <span data-ttu-id="ae818-108">该类型必须为基元（标量）类型。</span><span class="sxs-lookup"><span data-stu-id="ae818-108">It must be a primitive (scalar) type.</span></span> <span data-ttu-id="ae818-109">使用的 `data_type` 取决于查询空间。</span><span class="sxs-lookup"><span data-stu-id="ae818-109">The `data_type` used depends on the query space.</span></span> <span data-ttu-id="ae818-110">如果使用 <xref:System.Data.EntityClient.EntityCommand>执行查询，则数据类型为概念模型中定义的类型。</span><span class="sxs-lookup"><span data-stu-id="ae818-110">If a query is executed with the <xref:System.Data.EntityClient.EntityCommand>, the data type is a type defined in the conceptual model.</span></span> <span data-ttu-id="ae818-111">有关详细信息，请参阅 [CSDL Specification](../../../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)。</span><span class="sxs-lookup"><span data-stu-id="ae818-111">For more information, see [CSDL Specification](../../../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md).</span></span> <span data-ttu-id="ae818-112">如果使用 <xref:System.Data.Objects.ObjectQuery%601>执行查询，则数据类型为公共语言运行库 (CLR) 类型。</span><span class="sxs-lookup"><span data-stu-id="ae818-112">If a query is executed with <xref:System.Data.Objects.ObjectQuery%601>, the data type is a common language runtime (CLR) type.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ae818-113">返回值</span><span class="sxs-lookup"><span data-stu-id="ae818-113">Return Value</span></span>  
 <span data-ttu-id="ae818-114">返回与 `data_type`相同的值。</span><span class="sxs-lookup"><span data-stu-id="ae818-114">Returns the same value as `data_type`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ae818-115">备注</span><span class="sxs-lookup"><span data-stu-id="ae818-115">Remarks</span></span>  
 <span data-ttu-id="ae818-116">强制转换表达式的语义与 [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)] CONVERT 表达式类似。</span><span class="sxs-lookup"><span data-stu-id="ae818-116">The cast expression has similar semantics to the [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)] CONVERT expression.</span></span> <span data-ttu-id="ae818-117">强制转换表达式用于将一种类型的值转换为另一种类型的值。</span><span class="sxs-lookup"><span data-stu-id="ae818-117">The cast expression is used to convert a value of one type into a value of another type.</span></span>  
  
```  
CAST( e as T )  
```  
  
 <span data-ttu-id="ae818-118">如果 e 具有某种类型 S，且 S 可转换为 T，则上面的表达式是有效的强制转换表达式。</span><span class="sxs-lookup"><span data-stu-id="ae818-118">If e is of some type S, and S is convertible to T, then the above expression is a valid cast expression.</span></span> <span data-ttu-id="ae818-119">T 必须为基元（标量）类型。</span><span class="sxs-lookup"><span data-stu-id="ae818-119">T must be a primitive (scalar) type.</span></span>  
  
 <span data-ttu-id="ae818-120">精度和标量方面的值可以选择在强制转换为 `Edm.Decimal`时提供。</span><span class="sxs-lookup"><span data-stu-id="ae818-120">Values for the precision and scale facets may optionally be provided when casting to `Edm.Decimal`.</span></span> <span data-ttu-id="ae818-121">如果未显式提供，则精度和标量的默认值分别为 18 和 0。</span><span class="sxs-lookup"><span data-stu-id="ae818-121">If not explicitly provided, the default values for precision and scale are 18 and 0, respectively.</span></span> <span data-ttu-id="ae818-122">具体而言， `Decimal`支持以下重载：</span><span class="sxs-lookup"><span data-stu-id="ae818-122">Specifically, the following overloads are supported for `Decimal`:</span></span>  
  
-   `CAST( d as Edm.Decimal );`  
  
-   `CAST( d as Edm.Decimal(precision) );`  
  
-   `CAST( d as Edm.Decimal(precision, scale) );`  
  
 <span data-ttu-id="ae818-123">使用强制转换表达式视为显式转换。</span><span class="sxs-lookup"><span data-stu-id="ae818-123">The use of a cast expression is considered an explicit conversion.</span></span> <span data-ttu-id="ae818-124">显式转换可能截断数据或丧失精度。</span><span class="sxs-lookup"><span data-stu-id="ae818-124">Explicit conversions might truncate data or lose precision.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ae818-125">仅对基元类型和枚举成员类型支持 CAST。</span><span class="sxs-lookup"><span data-stu-id="ae818-125">CAST is only supported over primitive types and enumeration member types.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ae818-126">示例</span><span class="sxs-lookup"><span data-stu-id="ae818-126">Example</span></span>  
 <span data-ttu-id="ae818-127">下面的 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 查询使用 CAST 运算符将一种数据类型的表达式强制转换为另一种数据类型的表达式。</span><span class="sxs-lookup"><span data-stu-id="ae818-127">The following [!INCLUDE[esql](../../../../../../includes/esql-md.md)] query uses the CAST operator to cast an expression of one data type to another.</span></span> <span data-ttu-id="ae818-128">此查询基于 AdventureWorks 销售模型。</span><span class="sxs-lookup"><span data-stu-id="ae818-128">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="ae818-129">若要编译并运行此查询，请执行下列步骤：</span><span class="sxs-lookup"><span data-stu-id="ae818-129">To compile and run this query, follow these steps:</span></span>  
  
1.  <span data-ttu-id="ae818-130">按照中的步骤[如何： 执行查询该返回 PrimitiveType 结果](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-primitivetype-results.md)。</span><span class="sxs-lookup"><span data-stu-id="ae818-130">Follow the procedure in [How to: Execute a Query that Returns PrimitiveType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-primitivetype-results.md).</span></span>  
  
2.  <span data-ttu-id="ae818-131">将以下查询作为参数传递给 `ExecutePrimitiveTypeQuery` 方法：</span><span class="sxs-lookup"><span data-stu-id="ae818-131">Pass the following query as an argument to the `ExecutePrimitiveTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#CAST](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#cast)]  
  
## <a name="see-also"></a><span data-ttu-id="ae818-132">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ae818-132">See Also</span></span>  
 [<span data-ttu-id="ae818-133">实体 SQL 引用</span><span class="sxs-lookup"><span data-stu-id="ae818-133">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
