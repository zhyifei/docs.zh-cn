---
title: facet
ms.date: 03/30/2017
ms.assetid: 91c4e6aa-3e54-4b6c-a38a-abf27808cc85
ms.openlocfilehash: 9353b143a328e0fb183b7870332462a0a2c91b10
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59094497"
---
# <a name="facet"></a><span data-ttu-id="1da27-102">facet</span><span class="sxs-lookup"><span data-stu-id="1da27-102">facet</span></span>
<span data-ttu-id="1da27-103">一个*方面*用于添加对基元类型属性定义的详细信息。</span><span class="sxs-lookup"><span data-stu-id="1da27-103">A *facet* is used to add detail to a primitive type property definition.</span></span> <span data-ttu-id="1da27-104">一个[属性](../../../../docs/framework/data/adonet/property.md)定义包含有关属性类型的信息，但通常需要更多详细信息。</span><span class="sxs-lookup"><span data-stu-id="1da27-104">A [property](../../../../docs/framework/data/adonet/property.md) definition contains information about the property type, but often more detail is necessary.</span></span> <span data-ttu-id="1da27-105">例如，概念模型中的实体类型可能有一个类型为 `String` 的属性，其值不能设置为 null。</span><span class="sxs-lookup"><span data-stu-id="1da27-105">For example, an entity type in a conceptual model might have a property of type `String` whose value cannot be set to null.</span></span> <span data-ttu-id="1da27-106">通过方面可以指定这种详细程度。</span><span class="sxs-lookup"><span data-stu-id="1da27-106">Facets allow you to specify this level of detail.</span></span>  
  
 <span data-ttu-id="1da27-107">下表描述了 EDM 中支持的方面。</span><span class="sxs-lookup"><span data-stu-id="1da27-107">The table below describes the facets that are supported in the EDM.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1da27-108">方面的确切值和行为由使用 EDM 实现的运行时环境确定。</span><span class="sxs-lookup"><span data-stu-id="1da27-108">The exact values and behaviors of facets are determined by the run-time environment that uses an EDM implementation.</span></span>  
  
|<span data-ttu-id="1da27-109">方面</span><span class="sxs-lookup"><span data-stu-id="1da27-109">Facet</span></span>|<span data-ttu-id="1da27-110">描述</span><span class="sxs-lookup"><span data-stu-id="1da27-110">Description</span></span>|<span data-ttu-id="1da27-111">适用对象</span><span class="sxs-lookup"><span data-stu-id="1da27-111">Applies to</span></span>|  
|-----------|-----------------|----------------|  
|`Collation`|<span data-ttu-id="1da27-112">指定在对属性值执行比较和排序操作时要使用的排序序列。</span><span class="sxs-lookup"><span data-stu-id="1da27-112">Specifies the collating sequence (or sorting sequence) to be used when performing comparison and ordering operations on values of the property.</span></span>|`String`|  
|`ConcurrencyMode`|<span data-ttu-id="1da27-113">表示应使用属性的值来进行开放式并发检查。</span><span class="sxs-lookup"><span data-stu-id="1da27-113">Indicates that the value of the property should be used for optimistic concurrency checks.</span></span>|<span data-ttu-id="1da27-114">所有基元类型属性</span><span class="sxs-lookup"><span data-stu-id="1da27-114">All primitive type properties</span></span>|  
|`Default`|<span data-ttu-id="1da27-115">如果在安装时未提供值，则指定属性的默认值。</span><span class="sxs-lookup"><span data-stu-id="1da27-115">Specifies the default value of the property if no value is supplied upon instantiation.</span></span>|<span data-ttu-id="1da27-116">所有基元类型属性</span><span class="sxs-lookup"><span data-stu-id="1da27-116">All primitive type properties</span></span>|  
|`FixedLength`|<span data-ttu-id="1da27-117">指定属性值的长度是否可变。</span><span class="sxs-lookup"><span data-stu-id="1da27-117">Specifies whether the length of the property value can vary.</span></span>|`Binary`<span data-ttu-id="1da27-118">,</span><span class="sxs-lookup"><span data-stu-id="1da27-118">,</span></span> `String`|  
|`MaxLength`|<span data-ttu-id="1da27-119">指定属性值的最大长度。</span><span class="sxs-lookup"><span data-stu-id="1da27-119">Specifies the maximum length of the property value.</span></span>|`Binary`<span data-ttu-id="1da27-120">,</span><span class="sxs-lookup"><span data-stu-id="1da27-120">,</span></span> `String`|  
|`Nullable`|<span data-ttu-id="1da27-121">指定属性是否可以具有 null 值。</span><span class="sxs-lookup"><span data-stu-id="1da27-121">Specifies whether the property can have a null value.</span></span>|<span data-ttu-id="1da27-122">所有基元类型属性</span><span class="sxs-lookup"><span data-stu-id="1da27-122">All primitive type properties</span></span>|  
|`Precision`|<span data-ttu-id="1da27-123">对于类型 `Decimal` 的属性，指定属性值可以具有的位数。</span><span class="sxs-lookup"><span data-stu-id="1da27-123">For properties of type `Decimal`, specifies the number of digits a property value can have.</span></span> <span data-ttu-id="1da27-124">对于类型 `Time`、`DateTime` 和 `DateTimeOffset` 的属性，指定属性值的秒的小数部分的位数。</span><span class="sxs-lookup"><span data-stu-id="1da27-124">For properties of type `Time`, `DateTime`, and `DateTimeOffset`, specifies the number of digits for the fractional part of seconds of the property value.</span></span>|`DateTime`<span data-ttu-id="1da27-125">, `DateTimeOffset`, `Decimal`, `Time`,</span><span class="sxs-lookup"><span data-stu-id="1da27-125">, `DateTimeOffset`, `Decimal`, `Time`,</span></span>|  
|`Scale`|<span data-ttu-id="1da27-126">指定属性值小数点右侧的位数。</span><span class="sxs-lookup"><span data-stu-id="1da27-126">Specifies the number of digits to the right of the decimal point for the property value.</span></span>|<span data-ttu-id="1da27-127">十进制</span><span class="sxs-lookup"><span data-stu-id="1da27-127">Decimal</span></span>|  
|`Unicode`|<span data-ttu-id="1da27-128">指示是否将属性值存储为 Unicode。</span><span class="sxs-lookup"><span data-stu-id="1da27-128">Indicates whether the property value is stored as Unicode.</span></span>|`String`|  
  
## <a name="example"></a><span data-ttu-id="1da27-129">示例</span><span class="sxs-lookup"><span data-stu-id="1da27-129">Example</span></span>  
 <span data-ttu-id="1da27-130">[ADO.NET 实体框架](../../../../docs/framework/data/adonet/ef/index.md)使用称为概念性架构定义语言的特定于域的语言 (DSL) ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) 来定义概念模型。</span><span class="sxs-lookup"><span data-stu-id="1da27-130">The [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) uses a domain-specific language (DSL) called conceptual schema definition language ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) to define conceptual models.</span></span> <span data-ttu-id="1da27-131">下面的 CSDL 定义了一个 `Book` 实体类型。</span><span class="sxs-lookup"><span data-stu-id="1da27-131">The following CSDL defines a `Book` entity type.</span></span> <span data-ttu-id="1da27-132">请注意，方面是作为 XML 特性实现的。</span><span class="sxs-lookup"><span data-stu-id="1da27-132">Note that facets are implemented as XML attributes.</span></span> <span data-ttu-id="1da27-133">方面值表明不能将属性设置为 null，并且 `Scale` 属性的 `Precision` 和 `Revision` 都设置为 29。</span><span class="sxs-lookup"><span data-stu-id="1da27-133">The facet values indicate that no property can be set to null, and that the `Scale` and `Precision` of the `Revision` property are each set to 29.</span></span>  
  
 [!code-xml[EDM_Example_Model#EntityExample](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books.edmx#entityexample)]  
  
## <a name="see-also"></a><span data-ttu-id="1da27-134">请参阅</span><span class="sxs-lookup"><span data-stu-id="1da27-134">See also</span></span>

- [<span data-ttu-id="1da27-135">实体数据模型关键概念</span><span class="sxs-lookup"><span data-stu-id="1da27-135">Entity Data Model Key Concepts</span></span>](../../../../docs/framework/data/adonet/entity-data-model-key-concepts.md)
- [<span data-ttu-id="1da27-136">实体数据模型</span><span class="sxs-lookup"><span data-stu-id="1da27-136">Entity Data Model</span></span>](../../../../docs/framework/data/adonet/entity-data-model.md)
