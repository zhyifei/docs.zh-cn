---
title: 关联集端
ms.date: 03/30/2017
ms.assetid: fe4bf1d3-047a-4a37-98c5-a66e70811346
ms.openlocfilehash: 7b6c646592c1878ea30396d98b4976dc8fa0be12
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61769563"
---
# <a name="association-set-end"></a><span data-ttu-id="13be4-102">关联集端</span><span class="sxs-lookup"><span data-stu-id="13be4-102">association set end</span></span>
<span data-ttu-id="13be4-103">*关联集端*标识[实体类型](../../../../docs/framework/data/adonet/entity-type.md)并[实体集](../../../../docs/framework/data/adonet/entity-set.md)末尾[关联集](../../../../docs/framework/data/adonet/association-set.md)。</span><span class="sxs-lookup"><span data-stu-id="13be4-103">An *association set end* identifies the [entity type](../../../../docs/framework/data/adonet/entity-type.md) and the [entity set](../../../../docs/framework/data/adonet/entity-set.md) at the end of an [association set](../../../../docs/framework/data/adonet/association-set.md).</span></span> <span data-ttu-id="13be4-104">关联集端定义为关联集的一部分；一个关联集必须有且只有两个关联集端。</span><span class="sxs-lookup"><span data-stu-id="13be4-104">Association set ends are defined as part of an association set; an association set must have exactly two association set ends.</span></span>  
  
 <span data-ttu-id="13be4-105">关联集端定义包含以下信息：</span><span class="sxs-lookup"><span data-stu-id="13be4-105">An association set end definition contains the following information:</span></span>  
  
- <span data-ttu-id="13be4-106">关联集中涉及的实体类型之一。</span><span class="sxs-lookup"><span data-stu-id="13be4-106">One of the entity types involved in the association set.</span></span> <span data-ttu-id="13be4-107">（必需）</span><span class="sxs-lookup"><span data-stu-id="13be4-107">(Required)</span></span>  
  
- <span data-ttu-id="13be4-108">关联集中涉及的实体类型的实体集。</span><span class="sxs-lookup"><span data-stu-id="13be4-108">The entity set for the entity type involved in the association set.</span></span> <span data-ttu-id="13be4-109">（必需）</span><span class="sxs-lookup"><span data-stu-id="13be4-109">(Required)</span></span>  
  
## <a name="example"></a><span data-ttu-id="13be4-110">示例</span><span class="sxs-lookup"><span data-stu-id="13be4-110">Example</span></span>  
 <span data-ttu-id="13be4-111">下图显示了一个具有两个关联的概念模型：`WrittenBy` 和 `PublishedBy`。</span><span class="sxs-lookup"><span data-stu-id="13be4-111">The diagram below shows a conceptual model with two associations: `WrittenBy` and `PublishedBy`.</span></span>  
  
 ![具有三个实体类型的示例模型](./media/association-set-end/example-model-three-entity-types.gif)  
  
 <span data-ttu-id="13be4-113">下图显示了基于上面所示的概念模型的一个关联集 (`PublishedBy`) 和两个实体集（`Books` 和 `Publishers`）。</span><span class="sxs-lookup"><span data-stu-id="13be4-113">The following diagram shows an association set (`PublishedBy`) and two entity sets (`Books` and `Publishers`) based on the conceptual model shown above.</span></span> <span data-ttu-id="13be4-114">关联集端是 `Books` 和 `Publishers` 实体集。</span><span class="sxs-lookup"><span data-stu-id="13be4-114">The association set ends are the `Books` and `Publishers` entity sets.</span></span> <span data-ttu-id="13be4-115">在 bi`Books`实体集表示的实例`Book`实体类型，在运行时。</span><span class="sxs-lookup"><span data-stu-id="13be4-115">Bi in the `Books` entity set represents an instance of the `Book` entity type at run time.</span></span> <span data-ttu-id="13be4-116">同样，表示 Pj`Publisher`实例中`Publishers`实体集。</span><span class="sxs-lookup"><span data-stu-id="13be4-116">Similarly, Pj represents a `Publisher` instance in the `Publishers` entity set.</span></span> <span data-ttu-id="13be4-117">BiPj 表示的实例`PublishedBy`中的关联`PublishedBy`关联集。</span><span class="sxs-lookup"><span data-stu-id="13be4-117">BiPj represents an instance of the `PublishedBy` association in the `PublishedBy` association set.</span></span>  
  
 ![显示设置示例的屏幕截图。](./media/association-set-end/sets-example-association.gif)  
  
 <span data-ttu-id="13be4-119">[ADO.NET 实体框架](../../../../docs/framework/data/adonet/ef/index.md)使用 DSL 称为概念架构定义语言 ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) 来定义概念模型。</span><span class="sxs-lookup"><span data-stu-id="13be4-119">The [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) uses a DSL called conceptual schema definition language ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) to define conceptual models.</span></span> <span data-ttu-id="13be4-120">下面的 CSDL 定义了一个实体容器，其中对于上图所示的每个关联都有一个关联集。</span><span class="sxs-lookup"><span data-stu-id="13be4-120">The following CSDL defines an entity container with one association set for each association in the diagram above.</span></span> <span data-ttu-id="13be4-121">请注意，关联集端定义为每个关联集定义的一部分。</span><span class="sxs-lookup"><span data-stu-id="13be4-121">Note that association set ends are defined as part of each association set definition.</span></span>  
  
 [!code-xml[EDM_Example_Model#EntityContainerExample](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books.edmx#entitycontainerexample)]  
  
## <a name="see-also"></a><span data-ttu-id="13be4-122">请参阅</span><span class="sxs-lookup"><span data-stu-id="13be4-122">See also</span></span>

- [<span data-ttu-id="13be4-123">实体数据模型关键概念</span><span class="sxs-lookup"><span data-stu-id="13be4-123">Entity Data Model Key Concepts</span></span>](../../../../docs/framework/data/adonet/entity-data-model-key-concepts.md)
- [<span data-ttu-id="13be4-124">实体数据模型</span><span class="sxs-lookup"><span data-stu-id="13be4-124">Entity Data Model</span></span>](../../../../docs/framework/data/adonet/entity-data-model.md)
