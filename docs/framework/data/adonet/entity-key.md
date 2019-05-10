---
title: 实体键
ms.date: 03/30/2017
ms.assetid: 0d447a6d-fa7a-4db0-8e7a-fd45e385fca0
ms.openlocfilehash: bf8ab7ffacd7565e408e4851ed0f1ef4636b5d80
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "64599646"
---
# <a name="entity-key"></a><span data-ttu-id="7f993-102">实体键</span><span class="sxs-lookup"><span data-stu-id="7f993-102">entity key</span></span>
<span data-ttu-id="7f993-103">*实体键*是[属性](../../../../docs/framework/data/adonet/property.md)或一组的属性[实体类型](../../../../docs/framework/data/adonet/entity-type.md)，用于确定标识。</span><span class="sxs-lookup"><span data-stu-id="7f993-103">An *entity key* is a [property](../../../../docs/framework/data/adonet/property.md) or a set of properties of an [entity type](../../../../docs/framework/data/adonet/entity-type.md) that are used to determine identity.</span></span> <span data-ttu-id="7f993-104">构成实体键的属性是在设计时选择的。</span><span class="sxs-lookup"><span data-stu-id="7f993-104">The properties that make up an entity key are chosen at design time.</span></span> <span data-ttu-id="7f993-105">实体键属性的值必须唯一标识实体类型实例中的[实体集](../../../../docs/framework/data/adonet/entity-set.md)在运行时。</span><span class="sxs-lookup"><span data-stu-id="7f993-105">The values of entity key properties must uniquely identify an entity type instance within an [entity set](../../../../docs/framework/data/adonet/entity-set.md) at run time.</span></span> <span data-ttu-id="7f993-106">在选择构成实体键的属性时应确保实例在实体集中的唯一性。</span><span class="sxs-lookup"><span data-stu-id="7f993-106">The properties that make up an entity key should be chosen to guarantee uniqueness of instances in an entity set.</span></span>  
  
 <span data-ttu-id="7f993-107">下面是将一组属性用作实体键的要求：</span><span class="sxs-lookup"><span data-stu-id="7f993-107">The following are the requirements for a set of properties to be an entity key:</span></span>  
  
- <span data-ttu-id="7f993-108">实体集中不能存在两个相同的实体键。</span><span class="sxs-lookup"><span data-stu-id="7f993-108">No two entity keys within an entity set can be identical.</span></span> <span data-ttu-id="7f993-109">也就是说，对于实体集中的任意两个实体，构成一个键的所有属性的值不能全部相同。</span><span class="sxs-lookup"><span data-stu-id="7f993-109">That is, for any two entities within an entity set, the values for all of the properties that constitute a key cannot be the same.</span></span> <span data-ttu-id="7f993-110">但是，构成实体键的部分（而不是全部）值可以相同。</span><span class="sxs-lookup"><span data-stu-id="7f993-110">However, some (but not all) of the values that make up an entity key can be the same.</span></span>  
  
- <span data-ttu-id="7f993-111">实体键必须包含一系列不可以为 null 且不可变[基元类型属性](../../../../docs/framework/data/adonet/entity-data-model-primitive-data-types.md)。</span><span class="sxs-lookup"><span data-stu-id="7f993-111">An entity key must consist of a set of non-nullable, immutable, [primitive type properties](../../../../docs/framework/data/adonet/entity-data-model-primitive-data-types.md).</span></span>  
  
- <span data-ttu-id="7f993-112">构成给定实体类型的实体键的属性不可更改。</span><span class="sxs-lookup"><span data-stu-id="7f993-112">The properties that make up an entity key for a given entity type cannot change.</span></span> <span data-ttu-id="7f993-113">对于某个给定实体类型，不能允许存在多个可能的实体键；不支持代理键。</span><span class="sxs-lookup"><span data-stu-id="7f993-113">You cannot allow more than one possible entity key for a given entity type; surrogate keys are not supported.</span></span>  
  
- <span data-ttu-id="7f993-114">当实体位于继承层次结构中时，根实体必须包含构成实体键的所有属性，并且必须在根实体类型上定义实体键。</span><span class="sxs-lookup"><span data-stu-id="7f993-114">When an entity is involved in an inheritance hierarchy, the root entity must contain all the properties that make up the entity key, and the entity key must be defined on the root entity type.</span></span> <span data-ttu-id="7f993-115">有关详细信息，请参阅[实体数据模型：继承](../../../../docs/framework/data/adonet/entity-data-model-inheritance.md)。</span><span class="sxs-lookup"><span data-stu-id="7f993-115">For more information, see [Entity Data Model: Inheritance](../../../../docs/framework/data/adonet/entity-data-model-inheritance.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="7f993-116">示例</span><span class="sxs-lookup"><span data-stu-id="7f993-116">Example</span></span>  
 <span data-ttu-id="7f993-117">下图显示了一个具有三个实体类型的概念模型：`Book`、`Publisher` 和 `Author`。</span><span class="sxs-lookup"><span data-stu-id="7f993-117">The diagram below shows a conceptual model with three entity types: `Book`, `Publisher`, and `Author`.</span></span> <span data-ttu-id="7f993-118">构成其实体键的每个实体类型的属性均用“(Key)”标示出来。</span><span class="sxs-lookup"><span data-stu-id="7f993-118">The properties of each entity type that make up its entity key are denoted with "(Key)".</span></span> <span data-ttu-id="7f993-119">请注意，`Author` 实体类型有一个包含两个属性（`Name` 和 `Address`）的实体键。</span><span class="sxs-lookup"><span data-stu-id="7f993-119">Note that the `Author` entity type has an entity key that consists of two properties, `Name` and `Address`.</span></span>  
  
 ![具有三个实体类型的示例模型](./media/entity-key/example-model-three-entity-types.gif)  
  
 <span data-ttu-id="7f993-121">[ADO.NET 实体框架](../../../../docs/framework/data/adonet/ef/index.md)使用称为概念性架构定义语言的特定于域的语言 (DSL) ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) 来定义概念模型。</span><span class="sxs-lookup"><span data-stu-id="7f993-121">The [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) uses a domain-specific language (DSL) called conceptual schema definition language ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) to define conceptual models.</span></span> <span data-ttu-id="7f993-122">下面的 CSDL 定义了上图中显示的 `Book` 实体类型。</span><span class="sxs-lookup"><span data-stu-id="7f993-122">The CSDL below defines the `Book` entity type shown in the diagram above.</span></span> <span data-ttu-id="7f993-123">请注意，实体键通过引用实体类型的 `ISBN` 属性来定义。</span><span class="sxs-lookup"><span data-stu-id="7f993-123">Note that the entity key is defined by referencing the `ISBN` property of the entity type.</span></span>  
  
 [!code-xml[EDM_Example_Model#EntityExample](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books.edmx#entityexample)]  
  
 <span data-ttu-id="7f993-124">对实体键使用 `ISBN` 属性是一个不错的选择，因为国际标准书号 (ISBN) 可以唯一地标识一本书。</span><span class="sxs-lookup"><span data-stu-id="7f993-124">The `ISBN` property is a good choice for the entity key because an International Standard Book Number (ISBN) uniquely identifies a book.</span></span>  
  
 <span data-ttu-id="7f993-125">下面的 CSDL 定义了上图中显示的 `Author` 实体类型。</span><span class="sxs-lookup"><span data-stu-id="7f993-125">The CSDL below defines the `Author` entity type shown in the diagram above.</span></span> <span data-ttu-id="7f993-126">请注意，该实体键包含两个属性，`Name` 和 `Address`。</span><span class="sxs-lookup"><span data-stu-id="7f993-126">Note that the entity key consists of two properties, `Name` and `Address`.</span></span>  
  
 [!code-xml[EDM_Example_Model#CompositeKeyExample](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books.edmx#compositekeyexample)]  
  
 <span data-ttu-id="7f993-127">对实体键使用 `Name` 和 `Address` 是一个合理的选择，因为两个同名作者住址相同的可能性很小。</span><span class="sxs-lookup"><span data-stu-id="7f993-127">Using `Name` and `Address` for the entity key is a reasonable choice, because two authors of the same name are unlikely to live at the same address.</span></span> <span data-ttu-id="7f993-128">但是，针对实体键的这种选择并不能绝对确保实体键在实体集中的唯一性。</span><span class="sxs-lookup"><span data-stu-id="7f993-128">However, this choice for an entity key does not absolutely guarantee unique entity keys in an entity set.</span></span> <span data-ttu-id="7f993-129">在这种情况下，建议添加一个可用来唯一标识作者的属性，例如 `AuthorId`。</span><span class="sxs-lookup"><span data-stu-id="7f993-129">Adding a property, such as `AuthorId`, that could be used to uniquely identify an author would be recommended in this case.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7f993-130">请参阅</span><span class="sxs-lookup"><span data-stu-id="7f993-130">See also</span></span>

- [<span data-ttu-id="7f993-131">实体数据模型关键概念</span><span class="sxs-lookup"><span data-stu-id="7f993-131">Entity Data Model Key Concepts</span></span>](../../../../docs/framework/data/adonet/entity-data-model-key-concepts.md)
- [<span data-ttu-id="7f993-132">实体数据模型</span><span class="sxs-lookup"><span data-stu-id="7f993-132">Entity Data Model</span></span>](../../../../docs/framework/data/adonet/entity-data-model.md)
