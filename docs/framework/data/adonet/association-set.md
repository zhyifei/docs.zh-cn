---
title: Association Set — 关联集
ms.date: 03/30/2017
ms.assetid: a65247b6-ce59-44ea-974c-14ae20a7995f
ms.openlocfilehash: 53eeac5c3408bc35a02a368c093feda81cc16378
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
ms.locfileid: "32756990"
---
# <a name="association-set"></a><span data-ttu-id="81bde-102">Association Set — 关联集</span><span class="sxs-lookup"><span data-stu-id="81bde-102">association set</span></span>
<span data-ttu-id="81bde-103">*关联集*是的逻辑容器[关联](../../../../docs/framework/data/adonet/association-type.md)相同类型的实例。</span><span class="sxs-lookup"><span data-stu-id="81bde-103">An *association set* is a logical container for [association](../../../../docs/framework/data/adonet/association-type.md) instances of the same type.</span></span> <span data-ttu-id="81bde-104">关联集不是一种数据建模构造，也就是说，它没有描述数据结构或关系。</span><span class="sxs-lookup"><span data-stu-id="81bde-104">An association set is not a data modeling construct; that is, it does not describe the structure of data or relationships.</span></span> <span data-ttu-id="81bde-105">相反，关联集提供了一种承载或存储环境构造（例如公共语言运行库或 SQL Server 数据库）来分组关联实例，以便可以将它们映射到某个数据存储区。</span><span class="sxs-lookup"><span data-stu-id="81bde-105">Instead, an association set provides a construct for a hosting or storage environment (such as the common language runtime or a SQL Server database) to group association instances so that they can be mapped to a data store.</span></span>  
  
 <span data-ttu-id="81bde-106">关联集定义中[实体容器](../../../../docs/framework/data/adonet/entity-container.md)，即的逻辑分组[实体集](../../../../docs/framework/data/adonet/entity-set.md)和关联集。</span><span class="sxs-lookup"><span data-stu-id="81bde-106">An association set is defined within an [entity container](../../../../docs/framework/data/adonet/entity-container.md), which is a logical grouping of [entity sets](../../../../docs/framework/data/adonet/entity-set.md) and association sets.</span></span>  
  
 <span data-ttu-id="81bde-107">关联集的定义包含以下信息：</span><span class="sxs-lookup"><span data-stu-id="81bde-107">A definition for an association set contains the following information:</span></span>  
  
-   <span data-ttu-id="81bde-108">关联集名称。</span><span class="sxs-lookup"><span data-stu-id="81bde-108">The association set name.</span></span> <span data-ttu-id="81bde-109">（必需）</span><span class="sxs-lookup"><span data-stu-id="81bde-109">(Required)</span></span>  
  
-   <span data-ttu-id="81bde-110">要包含其实例的关联。</span><span class="sxs-lookup"><span data-stu-id="81bde-110">The association of which it will contain instances.</span></span> <span data-ttu-id="81bde-111">（必需）</span><span class="sxs-lookup"><span data-stu-id="81bde-111">(Required)</span></span>  
  
-   <span data-ttu-id="81bde-112">两个[关联集端](../../../../docs/framework/data/adonet/association-set-end.md)。</span><span class="sxs-lookup"><span data-stu-id="81bde-112">Two [association set ends](../../../../docs/framework/data/adonet/association-set-end.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="81bde-113">示例</span><span class="sxs-lookup"><span data-stu-id="81bde-113">Example</span></span>  
 <span data-ttu-id="81bde-114">下图显示了一个具有两个关联的概念模型：`PublishedBy` 和 `WrittenBy`。</span><span class="sxs-lookup"><span data-stu-id="81bde-114">The diagram below shows a conceptual model with two associations: `PublishedBy`, and `WrittenBy`.</span></span> <span data-ttu-id="81bde-115">上图没有传达有关关联集的信息，但下图显示了一个基于此模型的关联集和实体集的示例。</span><span class="sxs-lookup"><span data-stu-id="81bde-115">Although information about association sets is not conveyed in the diagram, the next diagram shows an example of association sets and entity sets based on this model.</span></span>  
  
 <span data-ttu-id="81bde-116">![示例模型](../../../../docs/framework/data/adonet/media/examplemodel.gif "ExampleModel")</span><span class="sxs-lookup"><span data-stu-id="81bde-116">![Example Model](../../../../docs/framework/data/adonet/media/examplemodel.gif "ExampleModel")</span></span>  
  
 <span data-ttu-id="81bde-117">下面的示例显示了基于上面所示的概念模型的一个关联集 (`PublishedBy`) 和两个实体集（`Books` 和 `Publishers`）。</span><span class="sxs-lookup"><span data-stu-id="81bde-117">The following example shows an association set (`PublishedBy`) and two entity sets (`Books` and `Publishers`) based on the conceptual model shown above.</span></span> <span data-ttu-id="81bde-118">在 bi`Books`实体集表示的实例`Book`在运行时的实体类型。</span><span class="sxs-lookup"><span data-stu-id="81bde-118">Bi in the `Books` entity set represents an instance of the `Book` entity type at run time.</span></span> <span data-ttu-id="81bde-119">同样，Pj 表示`Publisher`实例中`Publishers`实体集。</span><span class="sxs-lookup"><span data-stu-id="81bde-119">Similarly, Pj represents a `Publisher` instance in the `Publishers` entity set.</span></span> <span data-ttu-id="81bde-120">BiPj 表示的实例`PublishedBy`中的关联`PublishedBy`关联集。</span><span class="sxs-lookup"><span data-stu-id="81bde-120">BiPj represents an instance of the `PublishedBy` association in the `PublishedBy` association set.</span></span>  
  
 <span data-ttu-id="81bde-121">![设置示例](../../../../docs/framework/data/adonet/media/setsexample.gif "SetsExample")</span><span class="sxs-lookup"><span data-stu-id="81bde-121">![Sets Example](../../../../docs/framework/data/adonet/media/setsexample.gif "SetsExample")</span></span>  
  
 <span data-ttu-id="81bde-122">[ADO.NET 实体框架](../../../../docs/framework/data/adonet/ef/index.md)使用域特定语言 (DSL) 称为概念架构定义语言 ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) 来定义概念模型。</span><span class="sxs-lookup"><span data-stu-id="81bde-122">The [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) uses a domain-specific language (DSL) called conceptual schema definition language ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) to define conceptual models.</span></span> <span data-ttu-id="81bde-123">下面的 CSDL 定义了一个实体容器，其中对于上图所示的每个关联都有一个关联集。</span><span class="sxs-lookup"><span data-stu-id="81bde-123">The following CSDL defines an entity container with one association set for each association in the diagram above.</span></span> <span data-ttu-id="81bde-124">请注意，每个关联集的名称和关联都是使用 XML 特性定义的。</span><span class="sxs-lookup"><span data-stu-id="81bde-124">Note that the name and association for each association set are defined using XML attributes.</span></span>  
  
 [!code-xml[EDM_Example_Model#EntityContainerExample](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books.edmx#entitycontainerexample)]  
  
 <span data-ttu-id="81bde-125">可以定义每个关联，只要没有两个关联集共享的多个关联集[关联集端](../../../../docs/framework/data/adonet/association-set-end.md)。</span><span class="sxs-lookup"><span data-stu-id="81bde-125">It is possible to define multiple association sets per association, as long as no two association sets share an [association set end](../../../../docs/framework/data/adonet/association-set-end.md).</span></span> <span data-ttu-id="81bde-126">下面的 CSDL 定义了一个实体容器，其中包含 `WrittenBy` 关联的两个关联集。</span><span class="sxs-lookup"><span data-stu-id="81bde-126">The following CSDL defines an entity container with two association sets for the `WrittenBy` association.</span></span> <span data-ttu-id="81bde-127">请注意，为 `Book` 和 `Author` 实体类型定义了多个实体集，并且没有关联集共享关联集端。</span><span class="sxs-lookup"><span data-stu-id="81bde-127">Notice that multiple entity sets have been defined for the `Book` and `Author` entity types and that no association set shares an association set end.</span></span>  
  
 [!code-xml[EDM_Example_Model#MultipleAssociationSets](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books3.edmx#multipleassociationsets)]  
  
## <a name="see-also"></a><span data-ttu-id="81bde-128">请参阅</span><span class="sxs-lookup"><span data-stu-id="81bde-128">See Also</span></span>  
 [<span data-ttu-id="81bde-129">实体数据模型关键概念</span><span class="sxs-lookup"><span data-stu-id="81bde-129">Entity Data Model Key Concepts</span></span>](../../../../docs/framework/data/adonet/entity-data-model-key-concepts.md)  
 [<span data-ttu-id="81bde-130">实体数据模型</span><span class="sxs-lookup"><span data-stu-id="81bde-130">Entity Data Model</span></span>](../../../../docs/framework/data/adonet/entity-data-model.md)  
 [<span data-ttu-id="81bde-131">外键属性</span><span class="sxs-lookup"><span data-stu-id="81bde-131">foreign key property</span></span>](../../../../docs/framework/data/adonet/foreign-key-property.md)
