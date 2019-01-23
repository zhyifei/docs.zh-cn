---
title: 命名类型构造函数 (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 549dea04-d93d-4c87-a292-f81b1598dbfd
ms.openlocfilehash: f6577b49c299e1497da2692daef6d22cba1473b2
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54626688"
---
# <a name="named-type-constructor-entity-sql"></a><span data-ttu-id="cc7e9-102">命名类型构造函数 (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="cc7e9-102">Named Type Constructor (Entity SQL)</span></span>
<span data-ttu-id="cc7e9-103">用于创建概念模型名义类型（如实体或复杂类型）的实例。</span><span class="sxs-lookup"><span data-stu-id="cc7e9-103">Used to create instances of conceptual model nominal types such as Entity or Complex types.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cc7e9-104">语法</span><span class="sxs-lookup"><span data-stu-id="cc7e9-104">Syntax</span></span>  
  
```  
[{identifier. }] identifier( [expression [{, expression }]] )  
```  
  
## <a name="arguments"></a><span data-ttu-id="cc7e9-105">自变量</span><span class="sxs-lookup"><span data-stu-id="cc7e9-105">Arguments</span></span>  
 `identifier`  
 <span data-ttu-id="cc7e9-106">作为简单标识符或带引号的标识符的值。</span><span class="sxs-lookup"><span data-stu-id="cc7e9-106">Value that is a simple or quoted identifier.</span></span> <span data-ttu-id="cc7e9-107">有关详细信息，请参阅[标识符](../../../../../../docs/framework/data/adonet/ef/language-reference/identifiers-entity-sql.md)</span><span class="sxs-lookup"><span data-stu-id="cc7e9-107">For more information see, [Identifiers](../../../../../../docs/framework/data/adonet/ef/language-reference/identifiers-entity-sql.md)</span></span>  
  
 `expression`  
 <span data-ttu-id="cc7e9-108">类型的属性，假设这些属性的顺序与它们在类型声明中的顺序相同。</span><span class="sxs-lookup"><span data-stu-id="cc7e9-108">Attributes of the type that are assumed to be in the same order as they appear in the declaration of the type.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="cc7e9-109">返回值</span><span class="sxs-lookup"><span data-stu-id="cc7e9-109">Return Value</span></span>  
 <span data-ttu-id="cc7e9-110">命名复杂类型和实体类型的实例。</span><span class="sxs-lookup"><span data-stu-id="cc7e9-110">Instances of named complex types and entity types.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cc7e9-111">备注</span><span class="sxs-lookup"><span data-stu-id="cc7e9-111">Remarks</span></span>  
 <span data-ttu-id="cc7e9-112">下面的示例演示如何构造名义类型和复杂类型：</span><span class="sxs-lookup"><span data-stu-id="cc7e9-112">The following examples show how to construct nominal and complex types:</span></span>  
  
 <span data-ttu-id="cc7e9-113">下面的表达式创建 `Person` 类型的实例：</span><span class="sxs-lookup"><span data-stu-id="cc7e9-113">The expression below creates an instance of a `Person` type:</span></span>  
  
 `Person("abc", 12)`  
  
 <span data-ttu-id="cc7e9-114">下面的表达式创建复杂类型的实例：</span><span class="sxs-lookup"><span data-stu-id="cc7e9-114">The expression below creates an instance of a complex type:</span></span>  
  
 `MyModel.ZipCode(‘98118’, ‘4567’)`  
  
 <span data-ttu-id="cc7e9-115">下面的表达式创建嵌套复杂类型的实例：</span><span class="sxs-lookup"><span data-stu-id="cc7e9-115">The expression below creates an instance of a nested complex type:</span></span>  
  
 `MyModel.AddressInfo('My street address', 'Seattle', 'WA', MyModel.ZipCode('98118', '4567'))`  
  
 <span data-ttu-id="cc7e9-116">下面的表达式创建具有嵌套复杂类型的实体的实例：</span><span class="sxs-lookup"><span data-stu-id="cc7e9-116">The expression below creates an instance of an entity with a nested complex type:</span></span>  
  
 `MyModel.Person("Bill", MyModel.AddressInfo('My street address', 'Seattle', 'WA', MyModel.ZipCode('98118', '4567')))`  
  
 <span data-ttu-id="cc7e9-117">下面的示例演示如何将复杂类型的属性初始化为 null：`MyModel.ZipCode(‘98118’, null)`</span><span class="sxs-lookup"><span data-stu-id="cc7e9-117">The following example shows how to initialize a property of a complex type to null:`MyModel.ZipCode(‘98118’, null)`</span></span>  
  
## <a name="example"></a><span data-ttu-id="cc7e9-118">示例</span><span class="sxs-lookup"><span data-stu-id="cc7e9-118">Example</span></span>  
 <span data-ttu-id="cc7e9-119">下面的 Entity SQL 查询使用命名类型构造函数创建概念模型类型的实例。</span><span class="sxs-lookup"><span data-stu-id="cc7e9-119">The following Entity SQL query uses the named type constructor to create an instance of a conceptual model type.</span></span> <span data-ttu-id="cc7e9-120">此查询基于 AdventureWorks 销售模型。</span><span class="sxs-lookup"><span data-stu-id="cc7e9-120">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="cc7e9-121">若要编译并运行此查询，请执行下列步骤：</span><span class="sxs-lookup"><span data-stu-id="cc7e9-121">To compile and run this query, follow these steps:</span></span>  
  
1.  <span data-ttu-id="cc7e9-122">按照中的过程[如何：执行返回 StructuralType 结果的查询](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md)。</span><span class="sxs-lookup"><span data-stu-id="cc7e9-122">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2.  <span data-ttu-id="cc7e9-123">将以下查询作为参数传递给 `ExecuteStructuralTypeQuery` 方法：</span><span class="sxs-lookup"><span data-stu-id="cc7e9-123">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#NAMED_TYPE_CONSTRUCTOR](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#named_type_constructor)]  
  
## <a name="see-also"></a><span data-ttu-id="cc7e9-124">请参阅</span><span class="sxs-lookup"><span data-stu-id="cc7e9-124">See also</span></span>
- [<span data-ttu-id="cc7e9-125">构造类型</span><span class="sxs-lookup"><span data-stu-id="cc7e9-125">Constructing Types</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/constructing-types-entity-sql.md)
- [<span data-ttu-id="cc7e9-126">实体 SQL 引用</span><span class="sxs-lookup"><span data-stu-id="cc7e9-126">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
