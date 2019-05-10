---
title: 属性
ms.date: 03/30/2017
ms.assetid: a941c53f-fc97-42c2-8832-0fb9f1d55c06
ms.openlocfilehash: 97bb41305bd9b736fd67b51d77ee15ad9efa3f29
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "64645237"
---
# <a name="property"></a><span data-ttu-id="1def3-102">属性</span><span class="sxs-lookup"><span data-stu-id="1def3-102">property</span></span>
<span data-ttu-id="1def3-103">*属性*是的基本构建基块[实体类型](../../../../docs/framework/data/adonet/entity-type.md)并[复杂类型](../../../../docs/framework/data/adonet/complex-type.md)。</span><span class="sxs-lookup"><span data-stu-id="1def3-103">*Properties* are the fundamental building blocks of [entity types](../../../../docs/framework/data/adonet/entity-type.md) and [complex types](../../../../docs/framework/data/adonet/complex-type.md).</span></span> <span data-ttu-id="1def3-104">属性定义了实体类型实例或复杂类型实例要包含的数据的形状和特征。</span><span class="sxs-lookup"><span data-stu-id="1def3-104">Properties define the shape and characteristics of data that an entity type instance or complex type instance will contain.</span></span> <span data-ttu-id="1def3-105">概念模型中的属性类似于为类定义的属性。</span><span class="sxs-lookup"><span data-stu-id="1def3-105">Properties in a conceptual model are analogous to properties defined on a class.</span></span> <span data-ttu-id="1def3-106">正如类的属性定义类的形状和携带有关对象的信息一样，概念模型中的属性也定义实体类型的形状和携带有关实体类型实例的信息。</span><span class="sxs-lookup"><span data-stu-id="1def3-106">In the same way that properties on a class define the shape of the class and carry information about objects, properties in a conceptual model define the shape of an entity type and carry information about entity type instances.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1def3-107">本主题中描述的属性不同于导航属性。</span><span class="sxs-lookup"><span data-stu-id="1def3-107">Properties, as described in this topic, are different from navigation properties.</span></span> <span data-ttu-id="1def3-108">有关详细信息，请参阅[导航属性](../../../../docs/framework/data/adonet/navigation-property.md)。</span><span class="sxs-lookup"><span data-stu-id="1def3-108">For more information, see [navigation properties](../../../../docs/framework/data/adonet/navigation-property.md).</span></span>  
  
 <span data-ttu-id="1def3-109">属性定义包含以下信息：</span><span class="sxs-lookup"><span data-stu-id="1def3-109">A property definition contains the following information:</span></span>  
  
- <span data-ttu-id="1def3-110">属性名。</span><span class="sxs-lookup"><span data-stu-id="1def3-110">A property name.</span></span> <span data-ttu-id="1def3-111">（必需）</span><span class="sxs-lookup"><span data-stu-id="1def3-111">(Required)</span></span>  
  
- <span data-ttu-id="1def3-112">属性类型。</span><span class="sxs-lookup"><span data-stu-id="1def3-112">A property type.</span></span> <span data-ttu-id="1def3-113">（必需）</span><span class="sxs-lookup"><span data-stu-id="1def3-113">(Required)</span></span>  
  
- <span data-ttu-id="1def3-114">一套[方面](../../../../docs/framework/data/adonet/facet.md)。</span><span class="sxs-lookup"><span data-stu-id="1def3-114">A set of [facets](../../../../docs/framework/data/adonet/facet.md).</span></span> <span data-ttu-id="1def3-115">（可选）</span><span class="sxs-lookup"><span data-stu-id="1def3-115">(Optional)</span></span>  
  
 <span data-ttu-id="1def3-116">属性可以包含基元数据（例如字符串、整数或布尔值）或结构化数据（例如复杂类型）。</span><span class="sxs-lookup"><span data-stu-id="1def3-116">A property can contain primitive data (such as a string, an integer, or a Boolean value), or structured data (such as a complex type).</span></span> <span data-ttu-id="1def3-117">基元类型的属性也称为标量属性。</span><span class="sxs-lookup"><span data-stu-id="1def3-117">Properties that are of primitive type are also called scalar properties.</span></span> <span data-ttu-id="1def3-118">有关详细信息，请参阅[实体数据模型：基元数据类型](../../../../docs/framework/data/adonet/entity-data-model-primitive-data-types.md)。</span><span class="sxs-lookup"><span data-stu-id="1def3-118">For more information, see [Entity Data Model: Primitive Data Types](../../../../docs/framework/data/adonet/entity-data-model-primitive-data-types.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1def3-119">复杂类型本身可以具有复杂类型的属性。</span><span class="sxs-lookup"><span data-stu-id="1def3-119">A complex type can, itself, have properties that are complex types.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1def3-120">示例</span><span class="sxs-lookup"><span data-stu-id="1def3-120">Example</span></span>  
 <span data-ttu-id="1def3-121">下图显示了一个具有三个实体类型的概念模型：`Book`、`Publisher` 和 `Author`。</span><span class="sxs-lookup"><span data-stu-id="1def3-121">The diagram below shows a conceptual model with three entity types: `Book`, `Publisher`, and `Author`.</span></span> <span data-ttu-id="1def3-122">每个实体类型具有多个属性，但图中没有传达每个属性的类型信息。</span><span class="sxs-lookup"><span data-stu-id="1def3-122">Each entity type has several properties, although type information for each property is not conveyed in the diagram.</span></span> <span data-ttu-id="1def3-123">属性是[实体键](../../../../docs/framework/data/adonet/entity-key.md)用 (Key) 标示出来。</span><span class="sxs-lookup"><span data-stu-id="1def3-123">Properties that are [entity keys](../../../../docs/framework/data/adonet/entity-key.md) are denoted with (Key).</span></span>  
  
 ![具有三个实体类型的示例模型](./media/property/example-model-three-entity-types.gif)  
  
 <span data-ttu-id="1def3-125">[ADO.NET 实体框架](../../../../docs/framework/data/adonet/ef/index.md)使用称为概念性架构定义语言的特定于域的语言 (DSL) ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) 来定义概念模型。</span><span class="sxs-lookup"><span data-stu-id="1def3-125">The [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) uses a domain-specific language (DSL) called conceptual schema definition language ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) to define conceptual models.</span></span> <span data-ttu-id="1def3-126">下面的 CSDL 定义了 `Book` 实体类型（如上图所示）并使用 XML 特性表明了每个属性的类型和名称。</span><span class="sxs-lookup"><span data-stu-id="1def3-126">The following CSDL defines the `Book` entity type (as shown in the diagram above) and indicates the type and name of each property by using XML attributes.</span></span> <span data-ttu-id="1def3-127">此外，还使用 XML 特性定义了一个可选方面 `Nullable`。</span><span class="sxs-lookup"><span data-stu-id="1def3-127">An optional facet, `Nullable`, is also defined by using an XML attribute.</span></span>  
  
 [!code-xml[EDM_Example_Model#EntityExample](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books.edmx#entityexample)]  
  
 <span data-ttu-id="1def3-128">图中所示的其中一个属性还可以是复杂类型属性。</span><span class="sxs-lookup"><span data-stu-id="1def3-128">It is possible that one of the properties shown in the diagram is a complex type property.</span></span> <span data-ttu-id="1def3-129">例如，`Address` 实体类型的 `Publisher` 属性可以是由多个标量属性（例如 `StreetAddress`、`City`、`StateOrProvince`、`Country` 和 `PostalCode`）构成的复杂类型属性。</span><span class="sxs-lookup"><span data-stu-id="1def3-129">For example, the `Address` property on the `Publisher` entity type could be a complex type property composed of several scalar properties, such as `StreetAddress`, `City`, `StateOrProvince`, `Country`, and `PostalCode`.</span></span> <span data-ttu-id="1def3-130">这种复杂类型的 CSDL 表示方式如下所示：</span><span class="sxs-lookup"><span data-stu-id="1def3-130">The CSDL representation of such a complex type would be as follows:</span></span>  
  
 [!code-xml[EDM_Example_Model#ComplexTypeExample](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books2.edmx#complextypeexample)]  
  
## <a name="see-also"></a><span data-ttu-id="1def3-131">请参阅</span><span class="sxs-lookup"><span data-stu-id="1def3-131">See also</span></span>

- [<span data-ttu-id="1def3-132">实体数据模型关键概念</span><span class="sxs-lookup"><span data-stu-id="1def3-132">Entity Data Model Key Concepts</span></span>](../../../../docs/framework/data/adonet/entity-data-model-key-concepts.md)
- [<span data-ttu-id="1def3-133">实体数据模型</span><span class="sxs-lookup"><span data-stu-id="1def3-133">Entity Data Model</span></span>](../../../../docs/framework/data/adonet/entity-data-model.md)
