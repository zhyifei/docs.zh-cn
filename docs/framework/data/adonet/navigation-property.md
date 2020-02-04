---
title: 导航属性
ms.date: 03/30/2017
ms.assetid: d0bf1a6a-1d84-484c-b7c3-b410fd8dc0b1
ms.openlocfilehash: b6c286e63322a66be0407c864295a20685df2b7f
ms.sourcegitcommit: 19014f9c081ca2ff19652ca12503828db8239d48
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "76980153"
---
# <a name="navigation-property"></a><span data-ttu-id="ade8f-102">导航属性</span><span class="sxs-lookup"><span data-stu-id="ade8f-102">Navigation property</span></span>

<span data-ttu-id="ade8f-103">*导航属性*是[实体类型](entity-type.md)上的一个可选属性，它允许从[关联](association-type.md)的[一端](association-end.md)导航到另一端。</span><span class="sxs-lookup"><span data-stu-id="ade8f-103">A *navigation property* is an optional property on an [entity type](entity-type.md) that allows for navigation from one [end](association-end.md) of an [association](association-type.md) to the other end.</span></span> <span data-ttu-id="ade8f-104">与其他[属性](property.md)不同，导航属性不包含数据。</span><span class="sxs-lookup"><span data-stu-id="ade8f-104">Unlike other [properties](property.md), navigation properties do not carry data.</span></span>

<span data-ttu-id="ade8f-105">导航属性定义包含以下信息：</span><span class="sxs-lookup"><span data-stu-id="ade8f-105">A navigation property definition includes the following:</span></span>

- <span data-ttu-id="ade8f-106">名称。</span><span class="sxs-lookup"><span data-stu-id="ade8f-106">A name.</span></span> <span data-ttu-id="ade8f-107">（必需）</span><span class="sxs-lookup"><span data-stu-id="ade8f-107">(Required)</span></span>

- <span data-ttu-id="ade8f-108">导航属性要导航的关联。</span><span class="sxs-lookup"><span data-stu-id="ade8f-108">The association that it navigates.</span></span> <span data-ttu-id="ade8f-109">（必需）</span><span class="sxs-lookup"><span data-stu-id="ade8f-109">(Required)</span></span>

- <span data-ttu-id="ade8f-110">导航属性要导航的关联端。</span><span class="sxs-lookup"><span data-stu-id="ade8f-110">The ends of the association that it navigates.</span></span> <span data-ttu-id="ade8f-111">（必需）</span><span class="sxs-lookup"><span data-stu-id="ade8f-111">(Required)</span></span>

<span data-ttu-id="ade8f-112">注意，对于关联两端的两种实体类型，导航属性都是可选的。</span><span class="sxs-lookup"><span data-stu-id="ade8f-112">Note that navigation properties are optional on both entity types at the ends of an association.</span></span> <span data-ttu-id="ade8f-113">如果您对于位于关联一端的实体类型定义一个导航属性，则不需要对于位于关联另一端的实体类型定义导航属性。</span><span class="sxs-lookup"><span data-stu-id="ade8f-113">If you define a navigation property on one entity type at the end of an association, you do not have to define a navigation property on the entity type at the other end of the association.</span></span>

<span data-ttu-id="ade8f-114">导航属性的数据类型由其远程[关联端](association-end.md)的重[数](association-end-multiplicity.md)决定。</span><span class="sxs-lookup"><span data-stu-id="ade8f-114">The data type of a navigation property is determined by the [multiplicity](association-end-multiplicity.md) of its remote [association end](association-end.md).</span></span> <span data-ttu-id="ade8f-115">例如，假设导航属性 `OrdersNavProp` 存在于 `Customer` 实体类型上并导航 `Customer` 与 `Order` 之间的一对多关系。</span><span class="sxs-lookup"><span data-stu-id="ade8f-115">For example, suppose a navigation property, `OrdersNavProp`, exists on a `Customer` entity type and navigates a one-to-many association between `Customer` and `Order`.</span></span> <span data-ttu-id="ade8f-116">因为导航属性的远程关联端的重数为 many （\*），所以其数据类型为集合（的 `Order`）。</span><span class="sxs-lookup"><span data-stu-id="ade8f-116">Because the remote association end for the navigation property has multiplicity of many (\*), its data type is a collection (of `Order`).</span></span> <span data-ttu-id="ade8f-117">同样，如果导航属性 `CustomerNavProp` 存在于 `Order` 实体类型上，但由于远程端的重数为“一 (1)”，所以其数据类型应为 `Customer`。</span><span class="sxs-lookup"><span data-stu-id="ade8f-117">Similarly, if a navigation property, `CustomerNavProp`, exists on the `Order` entity type, its data type would be `Customer`, because the multiplicity of the remote end is one (1).</span></span>

## <a name="example"></a><span data-ttu-id="ade8f-118">示例</span><span class="sxs-lookup"><span data-stu-id="ade8f-118">Example</span></span>

<span data-ttu-id="ade8f-119">下图显示了一个具有三个实体类型的概念模型：`Book`、`Publisher` 和 `Author`。</span><span class="sxs-lookup"><span data-stu-id="ade8f-119">The diagram below shows a conceptual model with three entity types: `Book`, `Publisher`, and `Author`.</span></span> <span data-ttu-id="ade8f-120">导航属性 `Publisher` 和 `Authors` 都是在 Book 实体类型上定义的。</span><span class="sxs-lookup"><span data-stu-id="ade8f-120">Navigation properties, `Publisher` and `Authors`, are defined on the Book entity type.</span></span> <span data-ttu-id="ade8f-121">导航属性 `Books` 是同时在 Publisher 实体类型和 `Author` 实体类型上定义的。</span><span class="sxs-lookup"><span data-stu-id="ade8f-121">Navigation property `Books` is defined on both the Publisher entity type and the `Author` entity type.</span></span>

 ![显示具有三个实体类型的概念模型的关系图。](./media/navigation-property/conceptual-model-entity-types-associations.gif)  

<span data-ttu-id="ade8f-123">[ADO.NET 实体框架](./ef/index.md)使用一种称为概念架构定义语言（[CSDL](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec)）的域特定语言（DSL）来定义概念模型。</span><span class="sxs-lookup"><span data-stu-id="ade8f-123">The [ADO.NET Entity Framework](./ef/index.md) uses a domain-specific language (DSL) called conceptual schema definition language ([CSDL](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec)) to define conceptual models.</span></span> <span data-ttu-id="ade8f-124">下面的 CSDL 定义了上图中显示的 `Book` 实体类型。</span><span class="sxs-lookup"><span data-stu-id="ade8f-124">The following CSDL defines the `Book` entity type shown in the diagram above:</span></span>

[!code-xml[EDM_Example_Model#EntityExample](~/samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books.edmx#entityexample)]

<span data-ttu-id="ade8f-125">请注意，XML 特性用于传达定义导航属性所需的信息：特性 `Name` 包含属性的名称，`Relationship` 包含属性要导航的关联名称，而 `FromRole` 和 `ToRole` 则包含关联各端。</span><span class="sxs-lookup"><span data-stu-id="ade8f-125">Note that XML attributes are used to communicate the information necessary to define a navigation property: The attribute `Name` contains the name of the property, `Relationship` contains the name of the association it navigates, and `FromRole` and `ToRole` contain the ends of the association.</span></span>

## <a name="see-also"></a><span data-ttu-id="ade8f-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ade8f-126">See also</span></span>

- [<span data-ttu-id="ade8f-127">实体数据模型关键概念</span><span class="sxs-lookup"><span data-stu-id="ade8f-127">Entity Data Model Key Concepts</span></span>](entity-data-model-key-concepts.md)
- [<span data-ttu-id="ade8f-128">实体数据模型</span><span class="sxs-lookup"><span data-stu-id="ade8f-128">Entity Data Model</span></span>](entity-data-model.md)
- [<span data-ttu-id="ade8f-129">关系、导航属性和外键</span><span class="sxs-lookup"><span data-stu-id="ade8f-129">Relationships, navigation properties and foreign keys</span></span>](/ef/ef6/fundamentals/relationships)
