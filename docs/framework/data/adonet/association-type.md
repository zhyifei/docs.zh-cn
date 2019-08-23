---
title: 关联类型
ms.date: 03/30/2017
ms.assetid: 26c409f6-06e8-4441-ac78-1b1076a3c005
ms.openlocfilehash: 17465dbec3f5e2896cf755a1f8585734388f54ca
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69948304"
---
# <a name="association-type"></a><span data-ttu-id="4f4dc-102">关联类型</span><span class="sxs-lookup"><span data-stu-id="4f4dc-102">association type</span></span>
<span data-ttu-id="4f4dc-103">*关联类型*(也称为关联) 是用于描述实体数据模型 (EDM) 中的关系的基本构造块。</span><span class="sxs-lookup"><span data-stu-id="4f4dc-103">An *association type* (also called an association) is the fundamental building block for describing relationships in the Entity Data Model (EDM).</span></span> <span data-ttu-id="4f4dc-104">在概念模型中, 关联表示两个[实体类型](../../../../docs/framework/data/adonet/entity-type.md)(如`Customer`和`Order`) 之间的关系。</span><span class="sxs-lookup"><span data-stu-id="4f4dc-104">In a conceptual model, an association represents a relationship between two [entity types](../../../../docs/framework/data/adonet/entity-type.md) (such as `Customer` and `Order`).</span></span> <span data-ttu-id="4f4dc-105">在应用程序中，一个关联实例表示一个特定的关联（例如 `Customer` 实例与 `Order` 实例之间的关联）。</span><span class="sxs-lookup"><span data-stu-id="4f4dc-105">In an application, an instance of an association represents a specific association (such as an association between an instance of `Customer` and an instance of `Order`).</span></span> <span data-ttu-id="4f4dc-106">关联实例按逻辑分组到一个[关联集](../../../../docs/framework/data/adonet/association-set.md)。</span><span class="sxs-lookup"><span data-stu-id="4f4dc-106">Association instances are logically grouped in an [association set](../../../../docs/framework/data/adonet/association-set.md).</span></span>  
  
 <span data-ttu-id="4f4dc-107">关联定义包含以下信息：</span><span class="sxs-lookup"><span data-stu-id="4f4dc-107">An association definition contains the following information:</span></span>  
  
- <span data-ttu-id="4f4dc-108">唯一名称。</span><span class="sxs-lookup"><span data-stu-id="4f4dc-108">A unique name.</span></span> <span data-ttu-id="4f4dc-109">（必需）</span><span class="sxs-lookup"><span data-stu-id="4f4dc-109">(Required)</span></span>  
  
- <span data-ttu-id="4f4dc-110">两个[关联结束](../../../../docs/framework/data/adonet/association-end.md), 关系中的每个实体类型都有一个。</span><span class="sxs-lookup"><span data-stu-id="4f4dc-110">Two [association ends](../../../../docs/framework/data/adonet/association-end.md), one for each entity type in the relationship.</span></span> <span data-ttu-id="4f4dc-111">（必需）</span><span class="sxs-lookup"><span data-stu-id="4f4dc-111">(Required)</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="4f4dc-112">关联不能表示两个以上的实体类型之间的关系。</span><span class="sxs-lookup"><span data-stu-id="4f4dc-112">An association cannot represent a relationship among more than two entity types.</span></span> <span data-ttu-id="4f4dc-113">但是，通过为每个关联端指定相同的实体类型，关联可以定义自身关系。</span><span class="sxs-lookup"><span data-stu-id="4f4dc-113">An association can, however, define a self-relationship by specifying the same entity type for each of its association ends.</span></span>  
  
- <span data-ttu-id="4f4dc-114">[引用完整性约束](../../../../docs/framework/data/adonet/referential-integrity-constraint.md)。</span><span class="sxs-lookup"><span data-stu-id="4f4dc-114">A [referential integrity constraint](../../../../docs/framework/data/adonet/referential-integrity-constraint.md).</span></span> <span data-ttu-id="4f4dc-115">（可选）</span><span class="sxs-lookup"><span data-stu-id="4f4dc-115">(Optional)</span></span>  
  
 <span data-ttu-id="4f4dc-116">每个关联端都必须指定一个[关联端多重性](../../../../docs/framework/data/adonet/association-end-multiplicity.md), 以指示可以位于关联一端的实体类型实例的数量。</span><span class="sxs-lookup"><span data-stu-id="4f4dc-116">Each association end must specify an [association end multiplicity](../../../../docs/framework/data/adonet/association-end-multiplicity.md) that indicates the number of entity type instances that can be at one end of the association.</span></span> <span data-ttu-id="4f4dc-117">Association 端重数的值可以为一 (1)、零或一 (0 ..1) 或多 (\*)。</span><span class="sxs-lookup"><span data-stu-id="4f4dc-117">An association end multiplicity can have a value of one (1), zero or one (0..1), or many (\*).</span></span> <span data-ttu-id="4f4dc-118">可以通过[导航属性](../../../../docs/framework/data/adonet/navigation-property.md)或外键 (如果在实体类型上公开) 来访问关联一端的实体类型实例。</span><span class="sxs-lookup"><span data-stu-id="4f4dc-118">Entity type instances at one end of an association can be accessed through [navigation properties](../../../../docs/framework/data/adonet/navigation-property.md) or foreign keys if they are exposed on an entity type.</span></span> <span data-ttu-id="4f4dc-119">有关详细信息, 请[参阅实体数据模型:外键](../../../../docs/framework/data/adonet/foreign-key-property.md)。</span><span class="sxs-lookup"><span data-stu-id="4f4dc-119">For more information, see [Entity Data Model: Foreign Keys](../../../../docs/framework/data/adonet/foreign-key-property.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="4f4dc-120">示例</span><span class="sxs-lookup"><span data-stu-id="4f4dc-120">Example</span></span>  
 <span data-ttu-id="4f4dc-121">下图显示了一个具有两个关联的概念模型：`PublishedBy` 和 `WrittenBy`。</span><span class="sxs-lookup"><span data-stu-id="4f4dc-121">The diagram below shows a conceptual model with two associations: `PublishedBy` and `WrittenBy`.</span></span> <span data-ttu-id="4f4dc-122">`PublishedBy` 关联的关联端是 `Book` 和 `Publisher` 实体类型。</span><span class="sxs-lookup"><span data-stu-id="4f4dc-122">The association ends for the `PublishedBy` association are the `Book` and `Publisher` entity types.</span></span> <span data-ttu-id="4f4dc-123">`Publisher` End 的重数为一 (1), 而`Book`结尾的重数为多 (\*), 这表示发布者发布了许多书籍, 书籍发布了一个出版商。</span><span class="sxs-lookup"><span data-stu-id="4f4dc-123">The multiplicity of the `Publisher` end is one (1) and the multiplicity of the `Book` end is many (\*), indicating that a publisher publishes many books and a book is published by one publisher.</span></span>  
  
 ![具有三个实体类型的示例模型](./media/association-type/example-model-three-entity-types.gif)  
  
 <span data-ttu-id="4f4dc-125">[ADO.NET 实体框架](../../../../docs/framework/data/adonet/ef/index.md)使用一种称为概念架构定义语言 ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) 的域特定语言 (DSL) 来定义概念模型。</span><span class="sxs-lookup"><span data-stu-id="4f4dc-125">The [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) uses a domain-specific language (DSL) called conceptual schema definition language ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) to define conceptual models.</span></span> <span data-ttu-id="4f4dc-126">下面的 CSDL 定义了上图中显示的 `PublishedBy` 关联：</span><span class="sxs-lookup"><span data-stu-id="4f4dc-126">The following CSDL defines the `PublishedBy` association shown in the diagram above:</span></span>  
  
 [!code-xml[EDM_Example_Model#AssociationExample](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books.edmx#associationexample)]  
  
## <a name="see-also"></a><span data-ttu-id="4f4dc-127">请参阅</span><span class="sxs-lookup"><span data-stu-id="4f4dc-127">See also</span></span>

- [<span data-ttu-id="4f4dc-128">实体数据模型关键概念</span><span class="sxs-lookup"><span data-stu-id="4f4dc-128">Entity Data Model Key Concepts</span></span>](../../../../docs/framework/data/adonet/entity-data-model-key-concepts.md)
- [<span data-ttu-id="4f4dc-129">实体数据模型</span><span class="sxs-lookup"><span data-stu-id="4f4dc-129">Entity Data Model</span></span>](../../../../docs/framework/data/adonet/entity-data-model.md)
