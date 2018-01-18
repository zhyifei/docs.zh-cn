---
title: "引用完整性约束"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3d3ba44b-4302-40d8-a7a9-62932e0395e5
caps.latest.revision: "3"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: c343a0eba2478e041186f7bef18a85400c54bb5c
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2018
---
# <a name="referential-integrity-constraint"></a><span data-ttu-id="db6fe-102">引用完整性约束</span><span class="sxs-lookup"><span data-stu-id="db6fe-102">referential integrity constraint</span></span>
<span data-ttu-id="db6fe-103">A*引用完整性约束*实体数据模型 (EDM) 中是类似于关系数据库中的引用完整性约束。</span><span class="sxs-lookup"><span data-stu-id="db6fe-103">A *referential integrity constraint* in the Entity Data Model (EDM) is similar to a referential integrity constraint in a relational database.</span></span> <span data-ttu-id="db6fe-104">与数据库表中一列 （或多） 可以引用另一个表的主键相同的方式[属性](../../../../docs/framework/data/adonet/property.md)（或属性） 的[实体类型](../../../../docs/framework/data/adonet/entity-type.md)可以引用[实体键](../../../../docs/framework/data/adonet/entity-key.md)另一个实体类型。</span><span class="sxs-lookup"><span data-stu-id="db6fe-104">In the same way that a column (or columns) from a database table can reference the primary key of another table, a [property](../../../../docs/framework/data/adonet/property.md) (or properties) of an [entity type](../../../../docs/framework/data/adonet/entity-type.md) can reference the [entity key](../../../../docs/framework/data/adonet/entity-key.md) of another entity type.</span></span> <span data-ttu-id="db6fe-105">引用的实体类型称为*主体端*的约束。</span><span class="sxs-lookup"><span data-stu-id="db6fe-105">The entity type that is referenced is called the *principal end* of the constraint.</span></span> <span data-ttu-id="db6fe-106">引用主体端的实体类型称为*依赖端*的约束。</span><span class="sxs-lookup"><span data-stu-id="db6fe-106">The entity type that references the principal end is called the *dependent end* of the constraint.</span></span>  
  
 <span data-ttu-id="db6fe-107">引用完整性约束定义的一部分[关联](../../../../docs/framework/data/adonet/association-type.md)两个实体类型之间。</span><span class="sxs-lookup"><span data-stu-id="db6fe-107">A referential integrity constraint is defined as part of an [association](../../../../docs/framework/data/adonet/association-type.md) between two entity types.</span></span> <span data-ttu-id="db6fe-108">引用完整性约束的定义指定了以下信息：</span><span class="sxs-lookup"><span data-stu-id="db6fe-108">The definition for a referential integrity constraint specifies the following information:</span></span>  
  
-   <span data-ttu-id="db6fe-109">约束的主体端。</span><span class="sxs-lookup"><span data-stu-id="db6fe-109">The principal end of the constraint.</span></span> <span data-ttu-id="db6fe-110">（一个实体类型，其实体键由依赖端引用。）</span><span class="sxs-lookup"><span data-stu-id="db6fe-110">(An entity type whose entity key is referenced by the dependent end.)</span></span>  
  
-   <span data-ttu-id="db6fe-111">主体端的实体键。</span><span class="sxs-lookup"><span data-stu-id="db6fe-111">The entity key of the principal end.</span></span>  
  
-   <span data-ttu-id="db6fe-112">约束的依赖端。</span><span class="sxs-lookup"><span data-stu-id="db6fe-112">The dependent end of the constraint.</span></span> <span data-ttu-id="db6fe-113">（一个实体类型，它的一个或多个属性引用主体端的实体键。）</span><span class="sxs-lookup"><span data-stu-id="db6fe-113">(An entity type that has a property or properties that reference the entity key of the principal end.)</span></span>  
  
-   <span data-ttu-id="db6fe-114">依赖端的一个或多个引用属性。</span><span class="sxs-lookup"><span data-stu-id="db6fe-114">The referencing property or properties of the dependent end.</span></span>  
  
 <span data-ttu-id="db6fe-115">EDM 中的引用完整性约束的用途是确保始终存在有效关联。</span><span class="sxs-lookup"><span data-stu-id="db6fe-115">The purpose of referential integrity constraints in the EDM is to ensure that valid associations always exist.</span></span> <span data-ttu-id="db6fe-116">有关详细信息，请参阅[外键属性](../../../../docs/framework/data/adonet/foreign-key-property.md)。</span><span class="sxs-lookup"><span data-stu-id="db6fe-116">For more information, see [foreign key property](../../../../docs/framework/data/adonet/foreign-key-property.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="db6fe-117">示例</span><span class="sxs-lookup"><span data-stu-id="db6fe-117">Example</span></span>  
 <span data-ttu-id="db6fe-118">下图显示了一个具有两个关联的概念模型：`WrittenBy` 和 `PublishedBy`。</span><span class="sxs-lookup"><span data-stu-id="db6fe-118">The diagram below shows a conceptual model with two associations: `WrittenBy` and `PublishedBy`.</span></span> <span data-ttu-id="db6fe-119">`Book` 实体类型有一个属性 `PublisherId`，当您为 `Publisher` 关联定义一个引用完整性约束时，它将引用 `PublishedBy` 实体类型的实体键。</span><span class="sxs-lookup"><span data-stu-id="db6fe-119">The `Book` entity type has a property, `PublisherId`, that references the entity key of the `Publisher` entity type when you define a referential integrity constraint on the `PublishedBy` association.</span></span>  
  
 <span data-ttu-id="db6fe-120">![RefConstraintModel](../../../../docs/framework/data/adonet/media/refconstraintmodel.gif "RefConstraintModel")</span><span class="sxs-lookup"><span data-stu-id="db6fe-120">![RefConstraintModel](../../../../docs/framework/data/adonet/media/refconstraintmodel.gif "RefConstraintModel")</span></span>  
  
 <span data-ttu-id="db6fe-121">[ADO.NET 实体框架](../../../../docs/framework/data/adonet/ef/index.md)使用域特定语言 (DSL) 称为概念架构定义语言 ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) 来定义概念模型。</span><span class="sxs-lookup"><span data-stu-id="db6fe-121">The [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) uses a domain-specific language (DSL) called conceptual schema definition language ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) to define conceptual models.</span></span> <span data-ttu-id="db6fe-122">下面的 CSDL 为上图所示的概念模型中的 `PublishedBy` 关联定义了一个引用完整性约束。</span><span class="sxs-lookup"><span data-stu-id="db6fe-122">The following CSDL defines a referential integrity constraint on the `PublishedBy` association shown in the conceptual model above.</span></span>  
  
 [!code-xml[EDM_Example_Model#RefConstraint](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books4.edmx#refconstraint)]  
  
## <a name="see-also"></a><span data-ttu-id="db6fe-123">请参阅</span><span class="sxs-lookup"><span data-stu-id="db6fe-123">See Also</span></span>  
 [<span data-ttu-id="db6fe-124">实体数据模型关键概念</span><span class="sxs-lookup"><span data-stu-id="db6fe-124">Entity Data Model Key Concepts</span></span>](../../../../docs/framework/data/adonet/entity-data-model-key-concepts.md)  
 [<span data-ttu-id="db6fe-125">实体数据模型</span><span class="sxs-lookup"><span data-stu-id="db6fe-125">Entity Data Model</span></span>](../../../../docs/framework/data/adonet/entity-data-model.md)
