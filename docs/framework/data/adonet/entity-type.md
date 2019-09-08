---
title: Entity Type — 实体类型
ms.date: 03/30/2017
ms.assetid: a6dee9ab-9e4a-48f2-a169-3f79cc15821c
ms.openlocfilehash: efd3ea0972148e885d4b22b49040640539bb28cd
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2019
ms.locfileid: "70795128"
---
# <a name="entity-type"></a><span data-ttu-id="c8f50-102">Entity Type — 实体类型</span><span class="sxs-lookup"><span data-stu-id="c8f50-102">entity type</span></span>
<span data-ttu-id="c8f50-103">*实体类型*是用于描述实体数据模型（EDM）的数据结构的基本构造块。</span><span class="sxs-lookup"><span data-stu-id="c8f50-103">The *entity type* is the fundamental building block for describing the structure of data with the Entity Data Model (EDM).</span></span> <span data-ttu-id="c8f50-104">在概念模型中，实体类型表示顶级概念（例如客户或订单）的结构。</span><span class="sxs-lookup"><span data-stu-id="c8f50-104">In a conceptual model, an entity type represents the structure of top-level concepts, such as customers or orders.</span></span> <span data-ttu-id="c8f50-105">实体类型是实体类型实例的模板。</span><span class="sxs-lookup"><span data-stu-id="c8f50-105">An entity type is a template for entity type instances.</span></span> <span data-ttu-id="c8f50-106">每个模板都包含以下信息：</span><span class="sxs-lookup"><span data-stu-id="c8f50-106">Each template contains the following information:</span></span>  
  
- <span data-ttu-id="c8f50-107">唯一名称。</span><span class="sxs-lookup"><span data-stu-id="c8f50-107">A unique name.</span></span> <span data-ttu-id="c8f50-108">（必选。）</span><span class="sxs-lookup"><span data-stu-id="c8f50-108">(Required.)</span></span>  
  
- <span data-ttu-id="c8f50-109">由一个或多个属性定义的[实体键](entity-key.md)。</span><span class="sxs-lookup"><span data-stu-id="c8f50-109">An [entity key](entity-key.md) defined by one or more properties.</span></span> <span data-ttu-id="c8f50-110">（必选。）</span><span class="sxs-lookup"><span data-stu-id="c8f50-110">(Required.)</span></span>  
  
- <span data-ttu-id="c8f50-111">[属性](property.md)形式的数据。</span><span class="sxs-lookup"><span data-stu-id="c8f50-111">Data in the form of [properties](property.md).</span></span> <span data-ttu-id="c8f50-112">（可选）。</span><span class="sxs-lookup"><span data-stu-id="c8f50-112">(Optional.)</span></span>  
  
- <span data-ttu-id="c8f50-113">允许从[关联](association-type.md)的[一端](association-end.md)导航到另一端的[导航属性](navigation-property.md)。</span><span class="sxs-lookup"><span data-stu-id="c8f50-113">[Navigation properties](navigation-property.md) that allow for navigation from one [end](association-end.md) of an [association](association-type.md) to the other end.</span></span> <span data-ttu-id="c8f50-114">（可选）</span><span class="sxs-lookup"><span data-stu-id="c8f50-114">(Optional)</span></span>  
  
 <span data-ttu-id="c8f50-115">在应用程序中，实体类型的实例表示一个特定对象（例如特定客户或订单）。</span><span class="sxs-lookup"><span data-stu-id="c8f50-115">In an application, an instance of an entity type represents a specific object (such as a specific customer or order).</span></span> <span data-ttu-id="c8f50-116">实体类型的每个实例都必须在[实体集中](entity-set.md)具有唯一的[实体键](entity-key.md)。</span><span class="sxs-lookup"><span data-stu-id="c8f50-116">Each instance of an entity type must have a unique [entity key](entity-key.md) within an [entity set](entity-set.md).</span></span>  
  
 <span data-ttu-id="c8f50-117">只有两个实体类型实例的类型相同且其实体键的值也相同时，才认为它们是相等的。</span><span class="sxs-lookup"><span data-stu-id="c8f50-117">Two entity type instances are considered equal only if they are of the same type and the values of their entity keys are the same.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c8f50-118">示例</span><span class="sxs-lookup"><span data-stu-id="c8f50-118">Example</span></span>  
 <span data-ttu-id="c8f50-119">下图显示了一个具有三个实体类型的概念模型：`Book`、`Publisher` 和 `Author`：</span><span class="sxs-lookup"><span data-stu-id="c8f50-119">The diagram below shows a conceptual model with three entity types: `Book`, `Publisher`, and `Author`:</span></span>  
  
 ![具有三个实体类型的示例模型](./media/entity-type/example-model-three-entity-types.gif)  
  
 <span data-ttu-id="c8f50-121">请注意，构成其实体键的每个实体类型的属性均用“(Key)”标示出来。</span><span class="sxs-lookup"><span data-stu-id="c8f50-121">Note that the properties of each entity type that make up its entity key are denoted with "(Key)".</span></span>  
  
 <span data-ttu-id="c8f50-122">[ADO.NET 实体框架](./ef/index.md)使用一种称为概念架构定义语言（[CSDL](./ef/language-reference/csdl-specification.md)）的域特定语言（DSL）来定义概念模型。</span><span class="sxs-lookup"><span data-stu-id="c8f50-122">The [ADO.NET Entity Framework](./ef/index.md) uses a domain-specific language (DSL) called conceptual schema definition language ([CSDL](./ef/language-reference/csdl-specification.md)) to define conceptual models.</span></span> <span data-ttu-id="c8f50-123">下面的 CSDL 定义了上图中显示的 `Book` 实体类型。</span><span class="sxs-lookup"><span data-stu-id="c8f50-123">The following CSDL defines the `Book` entity type shown in the diagram above:</span></span>  
  
 [!code-xml[EDM_Example_Model#EntityExample](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books.edmx#entityexample)]  
  
## <a name="see-also"></a><span data-ttu-id="c8f50-124">请参阅</span><span class="sxs-lookup"><span data-stu-id="c8f50-124">See also</span></span>

- [<span data-ttu-id="c8f50-125">实体数据模型关键概念</span><span class="sxs-lookup"><span data-stu-id="c8f50-125">Entity Data Model Key Concepts</span></span>](entity-data-model-key-concepts.md)
- [<span data-ttu-id="c8f50-126">实体数据模型</span><span class="sxs-lookup"><span data-stu-id="c8f50-126">Entity Data Model</span></span>](entity-data-model.md)
- [<span data-ttu-id="c8f50-127">facet</span><span class="sxs-lookup"><span data-stu-id="c8f50-127">facet</span></span>](facet.md)
