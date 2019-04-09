---
title: TREAT (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 5b77f156-55de-4cb4-8154-87f707d4c635
ms.openlocfilehash: e1382c4daa513477011a1d1c2132840dfae84de0
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59077337"
---
# <a name="treat-entity-sql"></a><span data-ttu-id="15b42-102">TREAT (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="15b42-102">TREAT (Entity SQL)</span></span>
<span data-ttu-id="15b42-103">将特定基类型的对象视为指定派生类型的对象。</span><span class="sxs-lookup"><span data-stu-id="15b42-103">Treats an object of a particular base type as an object of the specified derived type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="15b42-104">语法</span><span class="sxs-lookup"><span data-stu-id="15b42-104">Syntax</span></span>  
  
```  
TREAT ( expression as type)  
```  
  
## <a name="arguments"></a><span data-ttu-id="15b42-105">自变量</span><span class="sxs-lookup"><span data-stu-id="15b42-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="15b42-106">任何返回实体的有效查询表达式。</span><span class="sxs-lookup"><span data-stu-id="15b42-106">Any valid query expression that returns an entity.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="15b42-107">指定表达式的类型必须为指定数据类型的子类型，或者该数据类型必须为表达式的类型的子类型。</span><span class="sxs-lookup"><span data-stu-id="15b42-107">The type of the specified expression must be a subtype of the specified data type, or the data type must be a subtype of the type of expression.</span></span>  
  
 `type`  
 <span data-ttu-id="15b42-108">一个实体类型。</span><span class="sxs-lookup"><span data-stu-id="15b42-108">An entity type.</span></span> <span data-ttu-id="15b42-109">该类型必须由命名空间进行限定。</span><span class="sxs-lookup"><span data-stu-id="15b42-109">The type must be qualified by a namespace.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="15b42-110">指定表达式必须为指定数据类型的子类型，或者该数据类型必须为该表达式的子类型。</span><span class="sxs-lookup"><span data-stu-id="15b42-110">The specified expression must be a subtype of the specified data type, or the data type must be a subtype of the expression.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="15b42-111">返回值</span><span class="sxs-lookup"><span data-stu-id="15b42-111">Return Value</span></span>  
 <span data-ttu-id="15b42-112">一个具有指定数据类型的值。</span><span class="sxs-lookup"><span data-stu-id="15b42-112">A value of the specified data type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="15b42-113">备注</span><span class="sxs-lookup"><span data-stu-id="15b42-113">Remarks</span></span>  
 <span data-ttu-id="15b42-114">TREAT 用于在相关类之间执行向上转换。</span><span class="sxs-lookup"><span data-stu-id="15b42-114">TREAT is used to perform upcasting between related classes.</span></span> <span data-ttu-id="15b42-115">例如，如果 `Employee` 派生自 `Person` 且 p 的类型为 `Person`，则 `TREAT(p AS NamespaceName.Employee)` 会将泛型 `Person` 实例向上转换为 `Employee`；即，使您可以将 p 视为 `Employee`。</span><span class="sxs-lookup"><span data-stu-id="15b42-115">For example, if `Employee` derives from `Person` and p is of type `Person`, `TREAT(p AS NamespaceName.Employee)` upcasts a generic `Person` instance to `Employee`; that is, it allows you to treat p as `Employee`.</span></span>  
  
 <span data-ttu-id="15b42-116">TREAT 用于可以执行类似于以下查询的继承方案：</span><span class="sxs-lookup"><span data-stu-id="15b42-116">TREAT is used in inheritance scenarios where you can do a query like the following:</span></span>  
  
```  
SELECT TREAT(p AS NamespaceName.Employee)  
FROM ContainerName.Person AS p  
WHERE p IS OF (NamespaceName.Employee)   
```  
  
 <span data-ttu-id="15b42-117">此查询将 `Person` 实体向上转换为 `Employee` 类型。</span><span class="sxs-lookup"><span data-stu-id="15b42-117">This query upcasts `Person` entities to the `Employee` type.</span></span> <span data-ttu-id="15b42-118">如果 p 的值的实际类型不是 `Employee`，则表达式会生成值 `null`。</span><span class="sxs-lookup"><span data-stu-id="15b42-118">If the value of p is not actually of type `Employee`, the expression yields the value `null`.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="15b42-119">指定的表达式`Employee`必须是指定的数据类型的子类型`Person`，或者该数据类型必须为表达式的子类型。</span><span class="sxs-lookup"><span data-stu-id="15b42-119">The specified expression `Employee` must be a subtype of the specified data type `Person`, or the data type must be a subtype of the expression.</span></span> <span data-ttu-id="15b42-120">否则，表达式会导致编译时错误。</span><span class="sxs-lookup"><span data-stu-id="15b42-120">Otherwise, the expression will result in a compile-time error.</span></span>  
  
 <span data-ttu-id="15b42-121">下表显示了 TREAT 在某些典型模式和非常见模式下的行为。</span><span class="sxs-lookup"><span data-stu-id="15b42-121">The following table shows the behavior of treat over some typical patterns and some less common patterns.</span></span> <span data-ttu-id="15b42-122">所有异常都在调用提供程序之前从客户端引发：</span><span class="sxs-lookup"><span data-stu-id="15b42-122">All exceptions are thrown from the client side before the provider gets invoked:</span></span>  
  
|<span data-ttu-id="15b42-123">模式</span><span class="sxs-lookup"><span data-stu-id="15b42-123">Pattern</span></span>|<span data-ttu-id="15b42-124">行为</span><span class="sxs-lookup"><span data-stu-id="15b42-124">Behavior</span></span>|  
|-------------|--------------|  
|`TREAT (null AS EntityType)`|<span data-ttu-id="15b42-125">返回 `DbNull`。</span><span class="sxs-lookup"><span data-stu-id="15b42-125">Returns `DbNull`.</span></span>|  
|`TREAT (null AS ComplexType)`|<span data-ttu-id="15b42-126">引发异常。</span><span class="sxs-lookup"><span data-stu-id="15b42-126">Throws an exception.</span></span>|  
|`TREAT (null AS RowType)`|<span data-ttu-id="15b42-127">引发异常。</span><span class="sxs-lookup"><span data-stu-id="15b42-127">Throws an exception/</span></span>|  
|`TREAT (EntityType AS EntityType)`|<span data-ttu-id="15b42-128">返回 `EntityType` 或 `null`。</span><span class="sxs-lookup"><span data-stu-id="15b42-128">Returns `EntityType` or `null`.</span></span>|  
|`TREAT (ComplexType AS ComplexType)`|<span data-ttu-id="15b42-129">引发异常。</span><span class="sxs-lookup"><span data-stu-id="15b42-129">Throws an exception.</span></span>|  
|`TREAT (RowType AS RowType)`|<span data-ttu-id="15b42-130">引发异常。</span><span class="sxs-lookup"><span data-stu-id="15b42-130">Throws an exception.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="15b42-131">示例</span><span class="sxs-lookup"><span data-stu-id="15b42-131">Example</span></span>  
 <span data-ttu-id="15b42-132">下面的 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 查询使用 TREAT 运算符将类型为 Course 的对象转换为类型为 OnsiteCourse 的对象的集合。</span><span class="sxs-lookup"><span data-stu-id="15b42-132">The following [!INCLUDE[esql](../../../../../../includes/esql-md.md)] query uses the TREAT operator to convert an object of the type Course to a collection of objects of the type OnsiteCourse.</span></span> <span data-ttu-id="15b42-133">该查询基于 [School 模型](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb896300(v=vs.100))。</span><span class="sxs-lookup"><span data-stu-id="15b42-133">The query is based on the [School Model](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb896300(v=vs.100)).</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#TREAT_ISOF](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#treat_isof)]  
  
## <a name="see-also"></a><span data-ttu-id="15b42-134">请参阅</span><span class="sxs-lookup"><span data-stu-id="15b42-134">See also</span></span>

- [<span data-ttu-id="15b42-135">实体 SQL 引用</span><span class="sxs-lookup"><span data-stu-id="15b42-135">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
- [<span data-ttu-id="15b42-136">可以为 NULL 的结构化类型</span><span class="sxs-lookup"><span data-stu-id="15b42-136">Nullable Structured Types</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/nullable-structured-types-entity-sql.md)
