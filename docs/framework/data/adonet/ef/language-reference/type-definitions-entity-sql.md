---
title: 类型定义 (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 306b204a-ade5-47ef-95b5-c785d2da4a7e
ms.openlocfilehash: 2e068db0ce202c26cad36c8ed7adf0acdfb8e363
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59096018"
---
# <a name="type-definitions-entity-sql"></a><span data-ttu-id="46fc4-102">类型定义 (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="46fc4-102">Type Definitions (Entity SQL)</span></span>
<span data-ttu-id="46fc4-103">类型定义用在 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 内联函数的声明语句中。</span><span class="sxs-lookup"><span data-stu-id="46fc4-103">A type definition is used in the declaration statement of an [!INCLUDE[esql](../../../../../../includes/esql-md.md)] Inline function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="46fc4-104">备注</span><span class="sxs-lookup"><span data-stu-id="46fc4-104">Remarks</span></span>  
 <span data-ttu-id="46fc4-105">内联函数的声明语句组成[函数](../../../../../../docs/framework/data/adonet/ef/language-reference/function-entity-sql.md)关键字后跟表示函数名称 (例如，"MyAvg") 后跟用括号括起来 （适用于的参数定义列表的标识符示例中，"dues Collection(Decimal)")。</span><span class="sxs-lookup"><span data-stu-id="46fc4-105">The declaration statement for an inline function consists of the [FUNCTION](../../../../../../docs/framework/data/adonet/ef/language-reference/function-entity-sql.md) keyword followed by the identifier representing the function name (for example, "MyAvg") followed by a parameter definition list in parenthesis (for example, "dues Collection(Decimal)").</span></span>  
  
 <span data-ttu-id="46fc4-106">参数定义列表由零个或多个参数定义组成。</span><span class="sxs-lookup"><span data-stu-id="46fc4-106">The parameter definition list consists of zero or more parameter definitions.</span></span> <span data-ttu-id="46fc4-107">每个参数定义均由一个标识符（该函数的参数的名称，例如“dues”）后跟类型定义（例如，“Collection(Decimal)”）组成。</span><span class="sxs-lookup"><span data-stu-id="46fc4-107">Each parameter definition consists of an identifier (the name of the parameter to the function, for example, "dues") followed by a type definition (for example, "Collection(Decimal)").</span></span>  
  
 <span data-ttu-id="46fc4-108">类型定义可以为以下任一情况：</span><span class="sxs-lookup"><span data-stu-id="46fc4-108">The type definitions can be either:</span></span>  
  
-   <span data-ttu-id="46fc4-109">标识符的类型（例如，“Int32”或“AdventureWorks.Order”）。</span><span class="sxs-lookup"><span data-stu-id="46fc4-109">The type of the identifier (for example, "Int32" or "AdventureWorks.Order").</span></span>  
  
-   <span data-ttu-id="46fc4-110">关键字 `COLLECTION` 后跟放在括号中的另一个类型定义（例如，“Collection(AdventureWorks.Order)”）。</span><span class="sxs-lookup"><span data-stu-id="46fc4-110">The keyword `COLLECTION` followed by another type definition in parenthesis (for example, "Collection(AdventureWorks.Order)").</span></span>  
  
-   <span data-ttu-id="46fc4-111">关键字 ROW 后跟放在括号中的属性定义列表（例如，“Row(x AdventureWorks.Order)”）。</span><span class="sxs-lookup"><span data-stu-id="46fc4-111">The keyword ROW followed by a list of property definitions in parenthesis (for example, "Row(x AdventureWorks.Order)").</span></span> <span data-ttu-id="46fc4-112">属性定义具有格式，如"`identifier type_definition`， `identifier type_definition`，..."。</span><span class="sxs-lookup"><span data-stu-id="46fc4-112">Property definitions have a format such as "`identifier type_definition`, `identifier type_definition`, ...".</span></span>  
  
-   <span data-ttu-id="46fc4-113">关键字 REF 后跟放在括号中的标识符类型（例如，“Ref(AdventureWorks.Order)”）。</span><span class="sxs-lookup"><span data-stu-id="46fc4-113">The keyword REF followed by the type of the identifier in parenthesis (for example, "Ref(AdventureWorks.Order)").</span></span> <span data-ttu-id="46fc4-114">REF 类型定义运算符要求将实体类型作为自变量。</span><span class="sxs-lookup"><span data-stu-id="46fc4-114">The REF type definition operator requires an entity type as the argument.</span></span> <span data-ttu-id="46fc4-115">您不能指定基元类型作为参数。</span><span class="sxs-lookup"><span data-stu-id="46fc4-115">You cannot specify a primitive type as the argument.</span></span>  
  
 <span data-ttu-id="46fc4-116">还可以嵌套类型定义（例如，“Collection(Row(x Ref(AdventureWorks.Order)))”）。</span><span class="sxs-lookup"><span data-stu-id="46fc4-116">You can also nest type definitions (for example, "Collection(Row(x Ref(AdventureWorks.Order)))").</span></span>  
  
 <span data-ttu-id="46fc4-117">类型定义选项为：</span><span class="sxs-lookup"><span data-stu-id="46fc4-117">The type definition options are:</span></span>  
  
-   <span data-ttu-id="46fc4-118">`IdentifierName supported_type`或</span><span class="sxs-lookup"><span data-stu-id="46fc4-118">`IdentifierName supported_type`, or</span></span>  
  
-   <span data-ttu-id="46fc4-119">`IdentifierName` COLLECTION(`type_definition`) 或</span><span class="sxs-lookup"><span data-stu-id="46fc4-119">`IdentifierName` COLLECTION(`type_definition`), or</span></span>  
  
-   <span data-ttu-id="46fc4-120">`IdentifierName` ROW(`property_definition`) 或</span><span class="sxs-lookup"><span data-stu-id="46fc4-120">`IdentifierName` ROW(`property_definition`), or</span></span>  
  
-   <span data-ttu-id="46fc4-121">`IdentifierName` REF(`supported_entity_type`)</span><span class="sxs-lookup"><span data-stu-id="46fc4-121">`IdentifierName` REF(`supported_entity_type`)</span></span>  
  
 <span data-ttu-id="46fc4-122">属性定义选项为 `IdentifierName type_definition`。</span><span class="sxs-lookup"><span data-stu-id="46fc4-122">The property definition option is `IdentifierName type_definition`.</span></span>  
  
 <span data-ttu-id="46fc4-123">支持的类型为当前命名空间中的任何类型。</span><span class="sxs-lookup"><span data-stu-id="46fc4-123">Supported types are any types in the current namespace.</span></span> <span data-ttu-id="46fc4-124">它们包括基元类型和实体类型。</span><span class="sxs-lookup"><span data-stu-id="46fc4-124">These include both primitive and entity types.</span></span>  
  
 <span data-ttu-id="46fc4-125">支持的实体类型仅仅是当前命名空间中的实体类型。</span><span class="sxs-lookup"><span data-stu-id="46fc4-125">Supported entity types refer to only entity types in the current namespace.</span></span> <span data-ttu-id="46fc4-126">而不包括基元类型。</span><span class="sxs-lookup"><span data-stu-id="46fc4-126">They do not include primitive types.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="46fc4-127">示例</span><span class="sxs-lookup"><span data-stu-id="46fc4-127">Examples</span></span>  
 <span data-ttu-id="46fc4-128">下面是一个简单类型定义的示例。</span><span class="sxs-lookup"><span data-stu-id="46fc4-128">The following is an example of a simple type definition.</span></span>  
  
```  
USING Microsoft.Samples.Entity  
Function MyRound(p1 EDM.Decimal) AS (  
   Round(p1)  
)  
MyRound(CAST(1.7 as EDM.Decimal))  
```  
  
 <span data-ttu-id="46fc4-129">下面是 COLLECTION 类型定义的示例。</span><span class="sxs-lookup"><span data-stu-id="46fc4-129">The following is an example of a COLLECTION type definition.</span></span>  
  
```  
USING Microsoft.Samples.Entity  
Function MyRound(p1 Collection(EDM.Decimal)) AS (  
   Select Round(p1) from p1  
)  
MyRound({CAST(1.7 as EDM.Decimal), CAST(2.7 as EDM.Decimal)})  
```  
  
 <span data-ttu-id="46fc4-130">下面是 ROW 类型定义的示例。</span><span class="sxs-lookup"><span data-stu-id="46fc4-130">The following is an example of a ROW type definition.</span></span>  
  
```  
USING Microsoft.Samples.Entity  
Function MyRound(p1 Row(x EDM.Decimal)) AS (  
   Round(p1.x)  
)  
select MyRound(row(a as x)) from {CAST(1.7 as EDM.Decimal), CAST(2.7 as EDM.Decimal)} as a  
```  
  
 <span data-ttu-id="46fc4-131">下面是 REF 类型定义的示例。</span><span class="sxs-lookup"><span data-stu-id="46fc4-131">The following is an example of a REF type definition.</span></span>  
  
```  
USING Microsoft.Samples.Entity  
Function UnReference(p1 Ref(AdventureWorks.Order)) AS (  
   Deref(p1)  
)  
select Ref(x) from AdventureWorksEntities.SalesOrderHeaders as x  
```  
  
## <a name="see-also"></a><span data-ttu-id="46fc4-132">请参阅</span><span class="sxs-lookup"><span data-stu-id="46fc4-132">See also</span></span>

- [<span data-ttu-id="46fc4-133">实体 SQL 概述</span><span class="sxs-lookup"><span data-stu-id="46fc4-133">Entity SQL Overview</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)
- [<span data-ttu-id="46fc4-134">实体 SQL 引用</span><span class="sxs-lookup"><span data-stu-id="46fc4-134">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
