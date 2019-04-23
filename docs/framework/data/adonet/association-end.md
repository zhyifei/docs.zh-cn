---
title: 关联端
ms.date: 03/30/2017
ms.assetid: 2c345213-0296-4d90-ac6d-cef179798a75
ms.openlocfilehash: e549254533f8362ce3475fb3aa5dbaffb3e900e5
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59108285"
---
# <a name="association-end"></a><span data-ttu-id="94156-102">关联端</span><span class="sxs-lookup"><span data-stu-id="94156-102">association end</span></span>
<span data-ttu-id="94156-103">*关联端*标识[实体类型](../../../../docs/framework/data/adonet/entity-type.md)的另一端[关联](../../../../docs/framework/data/adonet/association-type.md)和关联的结束类型实例可以存在的实体数。</span><span class="sxs-lookup"><span data-stu-id="94156-103">An *association end* identifies the [entity type](../../../../docs/framework/data/adonet/entity-type.md) on one end of an [association](../../../../docs/framework/data/adonet/association-type.md) and the number of entity type instances that can exist at that end of an association.</span></span> <span data-ttu-id="94156-104">关联端定义为关联的一部分；关联必须正好有两个关联端。</span><span class="sxs-lookup"><span data-stu-id="94156-104">Association ends are defined as part of an association; an association must have exactly two association ends.</span></span> <span data-ttu-id="94156-105">[导航属性](../../../../docs/framework/data/adonet/navigation-property.md)允许导航到另一个关联端。</span><span class="sxs-lookup"><span data-stu-id="94156-105">[Navigation properties](../../../../docs/framework/data/adonet/navigation-property.md) allow for navigation from one association end to the other.</span></span>  
  
 <span data-ttu-id="94156-106">关联端定义包含以下信息：</span><span class="sxs-lookup"><span data-stu-id="94156-106">An association end definition contains the following information:</span></span>  
  
-   <span data-ttu-id="94156-107">关联中涉及的实体类型之一。</span><span class="sxs-lookup"><span data-stu-id="94156-107">One of the entity types involved in the association.</span></span> <span data-ttu-id="94156-108">（必需）</span><span class="sxs-lookup"><span data-stu-id="94156-108">(Required)</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="94156-109">对于某个给定的关联，为每个关联端指定的实体类型可以是相同的。</span><span class="sxs-lookup"><span data-stu-id="94156-109">For a given association, the entity type specified for each association end can be the same.</span></span> <span data-ttu-id="94156-110">这将创建一个自关联。</span><span class="sxs-lookup"><span data-stu-id="94156-110">This creates a self-association.</span></span>  
  
-   <span data-ttu-id="94156-111">[关联端重数](../../../../docs/framework/data/adonet/association-end-multiplicity.md)，该值指示关联的一端可以存在的实体类型实例数。</span><span class="sxs-lookup"><span data-stu-id="94156-111">An [association end multiplicity](../../../../docs/framework/data/adonet/association-end-multiplicity.md) that indicates the number of entity type instances that can be at one end of the association.</span></span> <span data-ttu-id="94156-112">关联端重数可以具有值为一 (1) 零或一 (0..1) 或许多 (\*)。</span><span class="sxs-lookup"><span data-stu-id="94156-112">An association end multiplicity can have a value of one (1), zero or one (0..1), or many (\*).</span></span>  
  
-   <span data-ttu-id="94156-113">关联端的名称。</span><span class="sxs-lookup"><span data-stu-id="94156-113">A name for the association end.</span></span> <span data-ttu-id="94156-114">（可选）</span><span class="sxs-lookup"><span data-stu-id="94156-114">(Optional)</span></span>  
  
-   <span data-ttu-id="94156-115">有关在关联端上执行的操作的信息，例如级联删除。</span><span class="sxs-lookup"><span data-stu-id="94156-115">Information about operations that are performed on the association end, such as cascade on delete.</span></span> <span data-ttu-id="94156-116">（可选）</span><span class="sxs-lookup"><span data-stu-id="94156-116">(Optional)</span></span>  
  
## <a name="example"></a><span data-ttu-id="94156-117">示例</span><span class="sxs-lookup"><span data-stu-id="94156-117">Example</span></span>  
 <span data-ttu-id="94156-118">下图显示了一个具有两个关联的概念模型：`PublishedBy` 和 `WrittenBy`。</span><span class="sxs-lookup"><span data-stu-id="94156-118">The diagram below shows a conceptual model with two associations: `PublishedBy` and `WrittenBy`.</span></span> <span data-ttu-id="94156-119">`PublishedBy` 关联的关联端是 `Book` 和 `Publisher` 实体类型。</span><span class="sxs-lookup"><span data-stu-id="94156-119">The association ends for the `PublishedBy` association are the `Book` and `Publisher` entity types.</span></span> <span data-ttu-id="94156-120">多重性`Publisher`最终为一 (1) 和重数`Book`最终为多个 (\*)，指示，出版商可以出版很多书而一本书只能由一个出版商出版。</span><span class="sxs-lookup"><span data-stu-id="94156-120">The multiplicity of the `Publisher` end is one (1) and the multiplicity of the `Book` end is many (\*), indicating that a publisher publishes many books and a book is published by one publisher.</span></span>  
  
 ![具有三个实体类型的示例模型](./media/association-end/example-model-three-entity-types.gif)  
  
 <span data-ttu-id="94156-122">ADO.NET 实体框架使用称为概念性架构定义语言的特定于域的语言 (DSL) ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) 来定义概念模型。</span><span class="sxs-lookup"><span data-stu-id="94156-122">The ADO.NET Entity Framework uses a domain-specific language (DSL) called conceptual schema definition language ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) to define conceptual models.</span></span> <span data-ttu-id="94156-123">下面的 CSDL 定义了上图中显示的 `PublishedBy` 关联。</span><span class="sxs-lookup"><span data-stu-id="94156-123">The CSDL below defines the `PublishedBy` association shown in the diagram above.</span></span> <span data-ttu-id="94156-124">请注意，每个关联端的类型、名称和重数由 XML 特性指定（分别是 `Type`、`Role` 和 `Multiplicity` 特性）。</span><span class="sxs-lookup"><span data-stu-id="94156-124">Note that the type, name, and multiplicity of each association end are specified by XML attributes (the `Type`, `Role`, and `Multiplicity` attributes, respectively).</span></span> <span data-ttu-id="94156-125">有关在端上执行的操作的可选信息在 XML 元素（`OnDelete` 元素）中指定。</span><span class="sxs-lookup"><span data-stu-id="94156-125">Optional information about operations performed on an end is specified in an XML element (the `OnDelete` element).</span></span> <span data-ttu-id="94156-126">在本例中，如果删除出版商，将同时删除所有关联的书籍。</span><span class="sxs-lookup"><span data-stu-id="94156-126">In this case, if a publisher is deleted, so are all associated books.</span></span>  
  
 [!code-xml[EDM_Example_Model#AssociationEnd](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books3.edmx#associationend)]  
  
## <a name="see-also"></a><span data-ttu-id="94156-127">请参阅</span><span class="sxs-lookup"><span data-stu-id="94156-127">See also</span></span>

- [<span data-ttu-id="94156-128">实体数据模型关键概念</span><span class="sxs-lookup"><span data-stu-id="94156-128">Entity Data Model Key Concepts</span></span>](../../../../docs/framework/data/adonet/entity-data-model-key-concepts.md)
- [<span data-ttu-id="94156-129">实体数据模型</span><span class="sxs-lookup"><span data-stu-id="94156-129">Entity Data Model</span></span>](../../../../docs/framework/data/adonet/entity-data-model.md)
