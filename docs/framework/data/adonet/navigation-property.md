---
title: Navigation Property — 导航属性
ms.date: 03/30/2017
ms.assetid: d0bf1a6a-1d84-484c-b7c3-b410fd8dc0b1
ms.openlocfilehash: 09c0e5e5dbc7b2be89e044c4d111fdd65fada7c7
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54662174"
---
# <a name="navigation-property"></a><span data-ttu-id="d7c46-102">Navigation Property — 导航属性</span><span class="sxs-lookup"><span data-stu-id="d7c46-102">navigation property</span></span>
<span data-ttu-id="d7c46-103">一个*导航属性*上为可选属性[实体类型](../../../../docs/framework/data/adonet/entity-type.md)允许进行从一个导航[最终](../../../../docs/framework/data/adonet/association-end.md)的[关联](../../../../docs/framework/data/adonet/association-type.md)到另一端。</span><span class="sxs-lookup"><span data-stu-id="d7c46-103">A *navigation property* is an optional property on an [entity type](../../../../docs/framework/data/adonet/entity-type.md) that allows for navigation from one [end](../../../../docs/framework/data/adonet/association-end.md) of an [association](../../../../docs/framework/data/adonet/association-type.md) to the other end.</span></span> <span data-ttu-id="d7c46-104">与其他不同[属性](../../../../docs/framework/data/adonet/property.md)，导航属性并不携带数据。</span><span class="sxs-lookup"><span data-stu-id="d7c46-104">Unlike other [properties](../../../../docs/framework/data/adonet/property.md), navigation properties do not carry data.</span></span>  
  
 <span data-ttu-id="d7c46-105">导航属性定义包含以下信息：</span><span class="sxs-lookup"><span data-stu-id="d7c46-105">A navigation property definition includes the following:</span></span>  
  
-   <span data-ttu-id="d7c46-106">名称。</span><span class="sxs-lookup"><span data-stu-id="d7c46-106">A name.</span></span> <span data-ttu-id="d7c46-107">（必需）</span><span class="sxs-lookup"><span data-stu-id="d7c46-107">(Required)</span></span>  
  
-   <span data-ttu-id="d7c46-108">导航属性要导航的关联。</span><span class="sxs-lookup"><span data-stu-id="d7c46-108">The association that it navigates.</span></span> <span data-ttu-id="d7c46-109">（必需）</span><span class="sxs-lookup"><span data-stu-id="d7c46-109">(Required)</span></span>  
  
-   <span data-ttu-id="d7c46-110">导航属性要导航的关联端。</span><span class="sxs-lookup"><span data-stu-id="d7c46-110">The ends of the association that it navigates.</span></span> <span data-ttu-id="d7c46-111">（必需）</span><span class="sxs-lookup"><span data-stu-id="d7c46-111">(Required)</span></span>  
  
 <span data-ttu-id="d7c46-112">注意，对于关联两端的两种实体类型，导航属性都是可选的。</span><span class="sxs-lookup"><span data-stu-id="d7c46-112">Note that navigation properties are optional on both entity types at the ends of an association.</span></span> <span data-ttu-id="d7c46-113">如果您对于位于关联一端的实体类型定义一个导航属性，则不需要对于位于关联另一端的实体类型定义导航属性。</span><span class="sxs-lookup"><span data-stu-id="d7c46-113">If you define a navigation property on one entity type at the end of an association, you do not have to define a navigation property on the entity type at the other end of the association.</span></span>  
  
 <span data-ttu-id="d7c46-114">一个导航属性的数据类型由[多重性](../../../../docs/framework/data/adonet/association-end-multiplicity.md)的其远程[关联端](../../../../docs/framework/data/adonet/association-end.md)。</span><span class="sxs-lookup"><span data-stu-id="d7c46-114">The data type of a navigation property is determined by the [multiplicity](../../../../docs/framework/data/adonet/association-end-multiplicity.md) of its remote [association end](../../../../docs/framework/data/adonet/association-end.md).</span></span> <span data-ttu-id="d7c46-115">例如，假设导航属性 `OrdersNavProp` 存在于 `Customer` 实体类型上并导航 `Customer` 与 `Order` 之间的一对多关系。</span><span class="sxs-lookup"><span data-stu-id="d7c46-115">For example, suppose a navigation property, `OrdersNavProp`, exists on a `Customer` entity type and navigates a one-to-many association between `Customer` and `Order`.</span></span> <span data-ttu-id="d7c46-116">因为导航属性的远程关联端的重数为多 (\*)，所以其数据类型是一个集合（属于 `Order`）。</span><span class="sxs-lookup"><span data-stu-id="d7c46-116">Because the remote association end for the navigation property has multiplicity of many (\*), its data type is a collection (of `Order`).</span></span> <span data-ttu-id="d7c46-117">同样，如果导航属性 `CustomerNavProp` 存在于 `Order` 实体类型上，但由于远程端的重数为“一 (1)”，所以其数据类型应为 `Customer`。</span><span class="sxs-lookup"><span data-stu-id="d7c46-117">Similarly, if a navigation property, `CustomerNavProp`, exists on the `Order` entity type, its data type would be `Customer`, because the multiplicity of the remote end is one (1).</span></span>  
  
## <a name="example"></a><span data-ttu-id="d7c46-118">示例</span><span class="sxs-lookup"><span data-stu-id="d7c46-118">Example</span></span>  
 <span data-ttu-id="d7c46-119">下图显示了一个具有三个实体类型的概念模型：`Book`、`Publisher` 和 `Author`。</span><span class="sxs-lookup"><span data-stu-id="d7c46-119">The diagram below shows a conceptual model with three entity types: `Book`, `Publisher`, and `Author`.</span></span> <span data-ttu-id="d7c46-120">导航属性 `Publisher` 和 `Authors` 都是在 Book 实体类型上定义的。</span><span class="sxs-lookup"><span data-stu-id="d7c46-120">Navigation properties, `Publisher` and `Authors`, are defined on the Book entity type.</span></span> <span data-ttu-id="d7c46-121">导航属性 `Books` 是同时在 Publisher 实体类型和 `Author` 实体类型上定义的。</span><span class="sxs-lookup"><span data-stu-id="d7c46-121">Navigation property `Books` is defined on both the Publisher entity type and the `Author` entity type.</span></span>  
  
 <span data-ttu-id="d7c46-122">![具有导航属性的模型](../../../../docs/framework/data/adonet/media/modelwithnavprops.gif "ModelWithNavProps")</span><span class="sxs-lookup"><span data-stu-id="d7c46-122">![Model with Navigation Properties](../../../../docs/framework/data/adonet/media/modelwithnavprops.gif "ModelWithNavProps")</span></span>  
  
 <span data-ttu-id="d7c46-123">[ADO.NET 实体框架](../../../../docs/framework/data/adonet/ef/index.md)使用称为概念性架构定义语言的特定于域的语言 (DSL) ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) 来定义概念模型。</span><span class="sxs-lookup"><span data-stu-id="d7c46-123">The [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) uses a domain-specific language (DSL) called conceptual schema definition language ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) to define conceptual models.</span></span> <span data-ttu-id="d7c46-124">下面的 CSDL 定义了上图中显示的 `Book` 实体类型。</span><span class="sxs-lookup"><span data-stu-id="d7c46-124">The following CSDL defines the `Book` entity type shown in the diagram above:</span></span>  
  
 [!code-xml[EDM_Example_Model#EntityExample](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books.edmx#entityexample)]  
  
 <span data-ttu-id="d7c46-125">请注意，XML 特性用于传达定义导航属性所需信息：该属性`Name`包含的属性名称`Relationship`包含它导航时，关联的名称和`FromRole`和`ToRole`包含关联的两端。</span><span class="sxs-lookup"><span data-stu-id="d7c46-125">Note that XML attributes are used to communicate the information necessary to define a navigation property: The attribute `Name` contains the name of the property, `Relationship` contains the name of the association it navigates, and `FromRole` and `ToRole` contain the ends of the association.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d7c46-126">请参阅</span><span class="sxs-lookup"><span data-stu-id="d7c46-126">See also</span></span>
- [<span data-ttu-id="d7c46-127">实体数据模型关键概念</span><span class="sxs-lookup"><span data-stu-id="d7c46-127">Entity Data Model Key Concepts</span></span>](../../../../docs/framework/data/adonet/entity-data-model-key-concepts.md)
- [<span data-ttu-id="d7c46-128">实体数据模型</span><span class="sxs-lookup"><span data-stu-id="d7c46-128">Entity Data Model</span></span>](../../../../docs/framework/data/adonet/entity-data-model.md)
