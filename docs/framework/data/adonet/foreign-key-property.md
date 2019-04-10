---
title: 外键属性
ms.date: 03/30/2017
ms.assetid: 23cb6729-544d-4f67-9ee7-44e8a6545587
ms.openlocfilehash: 74117b30ca54f7c57bd970003fc6f5dcc54d553f
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59218012"
---
# <a name="foreign-key-property"></a><span data-ttu-id="6c1d9-102">外键属性</span><span class="sxs-lookup"><span data-stu-id="6c1d9-102">foreign key property</span></span>
<span data-ttu-id="6c1d9-103">一个*外键属性*实体数据模型 (EDM) 中是基元类型[属性](../../../../docs/framework/data/adonet/property.md)（或一组基元类型属性） 上[实体类型](../../../../docs/framework/data/adonet/entity-type.md)，其中包含[实体键](../../../../docs/framework/data/adonet/entity-key.md)的另一个实体类型。</span><span class="sxs-lookup"><span data-stu-id="6c1d9-103">A *foreign key property* in the Entity Data Model (EDM) is a primitive type [property](../../../../docs/framework/data/adonet/property.md) (or a set of primitive type properties) on an [entity type](../../../../docs/framework/data/adonet/entity-type.md) that contains the [entity key](../../../../docs/framework/data/adonet/entity-key.md) of another entity type.</span></span>  
  
 <span data-ttu-id="6c1d9-104">外键属性相当于关系数据库中的外键列。</span><span class="sxs-lookup"><span data-stu-id="6c1d9-104">A foreign key property is analogous to a foreign key column in a relational database.</span></span> <span data-ttu-id="6c1d9-105">在关系数据库中使用外键列是表中的行之间创建关系的相同方式，在概念模型中的外键属性用于建立[关联](../../../../docs/framework/data/adonet/association-type.md)实体类型之间。</span><span class="sxs-lookup"><span data-stu-id="6c1d9-105">In the same way that foreign key columns are used in a relational database to create relationships between rows in tables, foreign key properties in a conceptual model are used to establish [associations](../../../../docs/framework/data/adonet/association-type.md) between entity types.</span></span> <span data-ttu-id="6c1d9-106">一个[引用完整性约束](../../../../docs/framework/data/adonet/referential-integrity-constraint.md)用于定义一种类型具有外键属性时的两个实体类型之间的关联。</span><span class="sxs-lookup"><span data-stu-id="6c1d9-106">A [referential integrity constraint](../../../../docs/framework/data/adonet/referential-integrity-constraint.md) is used to define an association between two entity types when one of the types has a foreign key property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6c1d9-107">示例</span><span class="sxs-lookup"><span data-stu-id="6c1d9-107">Example</span></span>  
 <span data-ttu-id="6c1d9-108">下图显示了一个具有三个实体类型的概念模型：`Book`、`Publisher` 和 `Author`。</span><span class="sxs-lookup"><span data-stu-id="6c1d9-108">The diagram below shows a conceptual model with three entity types: `Book`, `Publisher`, and `Author`.</span></span> <span data-ttu-id="6c1d9-109">`Book` 实体类型有一个属性 `PublisherId`，当您为 `Publisher` 关联定义一个引用完整性约束时，它将引用 `PublishedBy` 实体类型的实体键。</span><span class="sxs-lookup"><span data-stu-id="6c1d9-109">The `Book` entity type has a property, `PublisherId`, that references the entity key of the `Publisher` entity type when you define a referential integrity constraint on the `PublishedBy` association.</span></span>  
  
 <span data-ttu-id="6c1d9-110">![RefConstraintModel](./media/foreign-key-property/reference-constraint-model.gif "引用约束模型的示例")</span><span class="sxs-lookup"><span data-stu-id="6c1d9-110">![RefConstraintModel](./media/foreign-key-property/reference-constraint-model.gif "Example of a referential constraint model")</span></span>  
  
 <span data-ttu-id="6c1d9-111">[ADO.NET 实体框架](../../../../docs/framework/data/adonet/ef/index.md)使用称为概念性架构定义语言的特定于域的语言 (DSL) ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) 来定义概念模型。</span><span class="sxs-lookup"><span data-stu-id="6c1d9-111">The [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) uses a domain-specific language (DSL) called conceptual schema definition language ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) to define conceptual models.</span></span> <span data-ttu-id="6c1d9-112">下面的 CSDL 使用外键属性 `PublisherId` 为上图所示的概念模型中的 `PublishedBy` 关联定义了一个引用完整性约束。</span><span class="sxs-lookup"><span data-stu-id="6c1d9-112">The following CSDL uses the foreign key property `PublisherId` to define a referential integrity constraint on the `PublishedBy` association shown in the conceptual model shown above.</span></span>  
  
 [!code-xml[EDM_Example_Model#RefConstraint](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books4.edmx#refconstraint)]  
  
## <a name="see-also"></a><span data-ttu-id="6c1d9-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="6c1d9-113">See also</span></span>

- [<span data-ttu-id="6c1d9-114">实体数据模型关键概念</span><span class="sxs-lookup"><span data-stu-id="6c1d9-114">Entity Data Model Key Concepts</span></span>](../../../../docs/framework/data/adonet/entity-data-model-key-concepts.md)
- [<span data-ttu-id="6c1d9-115">实体数据模型</span><span class="sxs-lookup"><span data-stu-id="6c1d9-115">Entity Data Model</span></span>](../../../../docs/framework/data/adonet/entity-data-model.md)
