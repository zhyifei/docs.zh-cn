---
title: '&lt;parameter&gt;'
ms.date: 03/30/2017
ms.assetid: 0fb41e2d-64f7-44ab-993e-05892eac6d82
ms.openlocfilehash: a68fdecaba6ad4e64e4d3a4161d9fef6c099d60a
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54690730"
---
# <a name="ltparametergt"></a><span data-ttu-id="b077b-102">&lt;parameter&gt;</span><span class="sxs-lookup"><span data-stu-id="b077b-102">&lt;parameter&gt;</span></span>
<span data-ttu-id="b077b-103">指定当声明类型是泛型类型时的泛型参数。</span><span class="sxs-lookup"><span data-stu-id="b077b-103">Specifies the generic parameter when a declared type is a generic type.</span></span>  
  
 <span data-ttu-id="b077b-104">\<system.runtime.serialization></span><span class="sxs-lookup"><span data-stu-id="b077b-104">\<system.runtime.serialization></span></span>  
<span data-ttu-id="b077b-105">\<dataContractSerializer></span><span class="sxs-lookup"><span data-stu-id="b077b-105">\<dataContractSerializer></span></span>  
<span data-ttu-id="b077b-106">\<declaredTypes > 元素</span><span class="sxs-lookup"><span data-stu-id="b077b-106">\<declaredTypes> Element</span></span>  
<span data-ttu-id="b077b-107">\<添加 > 元素\<declaredTypes ></span><span class="sxs-lookup"><span data-stu-id="b077b-107">\<add> element for \<declaredTypes></span></span>  
<span data-ttu-id="b077b-108">\<knownType > 元素</span><span class="sxs-lookup"><span data-stu-id="b077b-108">\<knownType> Element</span></span>  
<span data-ttu-id="b077b-109">\<参数 > 元素</span><span class="sxs-lookup"><span data-stu-id="b077b-109">\<parameter> Element</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b077b-110">语法</span><span class="sxs-lookup"><span data-stu-id="b077b-110">Syntax</span></span>  
  
```xml  
<parameter index="Integer"
           type="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b077b-111">特性和元素</span><span class="sxs-lookup"><span data-stu-id="b077b-111">Attributes and Elements</span></span>  
 <span data-ttu-id="b077b-112">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="b077b-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b077b-113">特性</span><span class="sxs-lookup"><span data-stu-id="b077b-113">Attributes</span></span>  
  
|<span data-ttu-id="b077b-114">特性</span><span class="sxs-lookup"><span data-stu-id="b077b-114">Attribute</span></span>|<span data-ttu-id="b077b-115">描述</span><span class="sxs-lookup"><span data-stu-id="b077b-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="b077b-116">索引</span><span class="sxs-lookup"><span data-stu-id="b077b-116">index</span></span>|<span data-ttu-id="b077b-117">当声明类型是泛型类型时，指定将返回已知类型的泛型参数。</span><span class="sxs-lookup"><span data-stu-id="b077b-117">When the declared type is a generic type, specifies the generic parameter that will return the known type.</span></span>|  
|<span data-ttu-id="b077b-118">类型</span><span class="sxs-lookup"><span data-stu-id="b077b-118">type</span></span>|<span data-ttu-id="b077b-119">一个字符串，描述用于序列化和反序列化的已知类型。</span><span class="sxs-lookup"><span data-stu-id="b077b-119">A string that describes the known type used for serialization and deserialization.</span></span>|  
  
## <a name="index-attribute"></a><span data-ttu-id="b077b-120">index 特性</span><span class="sxs-lookup"><span data-stu-id="b077b-120">index Attribute</span></span>  
  
|<span data-ttu-id="b077b-121">值</span><span class="sxs-lookup"><span data-stu-id="b077b-121">Value</span></span>|<span data-ttu-id="b077b-122">描述</span><span class="sxs-lookup"><span data-stu-id="b077b-122">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="b077b-123">“0”</span><span class="sxs-lookup"><span data-stu-id="b077b-123">"0"</span></span>|<span data-ttu-id="b077b-124">泛型类型中的第一个参数。</span><span class="sxs-lookup"><span data-stu-id="b077b-124">The first parameter in the generic type.</span></span> <span data-ttu-id="b077b-125">例如，一个 <xref:System.Collections.Generic.List%601> 仅有一个参数。</span><span class="sxs-lookup"><span data-stu-id="b077b-125">For example, a <xref:System.Collections.Generic.List%601> has only one parameter.</span></span> <span data-ttu-id="b077b-126">如果此参数用作声明类型，则将 index 特性设置为“0”。</span><span class="sxs-lookup"><span data-stu-id="b077b-126">If it is used as the declared type, the index would be set to "0".</span></span>|  
|<span data-ttu-id="b077b-127">"1"</span><span class="sxs-lookup"><span data-stu-id="b077b-127">"1"</span></span>|<span data-ttu-id="b077b-128">泛型类型中的第二个参数。</span><span class="sxs-lookup"><span data-stu-id="b077b-128">The second parameter in a generic type.</span></span> <span data-ttu-id="b077b-129">例如，一个 <xref:System.Collections.Generic.Dictionary%602> 有两个参数。</span><span class="sxs-lookup"><span data-stu-id="b077b-129">For example, a <xref:System.Collections.Generic.Dictionary%602> has two parameters.</span></span> <span data-ttu-id="b077b-130">如果通过第二个参数返回已知类型，则将 index 特性设置为“1”。</span><span class="sxs-lookup"><span data-stu-id="b077b-130">If the known type is returned by the second parameter, set the index attribute to "1".</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b077b-131">子元素</span><span class="sxs-lookup"><span data-stu-id="b077b-131">Child Elements</span></span>  
 <span data-ttu-id="b077b-132">无。</span><span class="sxs-lookup"><span data-stu-id="b077b-132">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="b077b-133">父元素</span><span class="sxs-lookup"><span data-stu-id="b077b-133">Parent Elements</span></span>  
  
|<span data-ttu-id="b077b-134">元素</span><span class="sxs-lookup"><span data-stu-id="b077b-134">Element</span></span>|<span data-ttu-id="b077b-135">描述</span><span class="sxs-lookup"><span data-stu-id="b077b-135">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b077b-136">\<knownType></span><span class="sxs-lookup"><span data-stu-id="b077b-136">\<knownType></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/knowntype.md)|<span data-ttu-id="b077b-137">指定一个可由声明类型的字段或属性返回的已知类型。</span><span class="sxs-lookup"><span data-stu-id="b077b-137">Specifies a known type that can be returned by a field or property of the declared type.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b077b-138">备注</span><span class="sxs-lookup"><span data-stu-id="b077b-138">Remarks</span></span>  
 <span data-ttu-id="b077b-139">有关已知类型的详细信息，请参阅[Data Contract Known Types](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md)和<xref:System.Runtime.Serialization.DataContractSerializer>。</span><span class="sxs-lookup"><span data-stu-id="b077b-139">For more information about known types, see [Data Contract Known Types](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md) and <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  
  
 <span data-ttu-id="b077b-140">请参阅[ \<dataContractSerializer >](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-element.md)有关使用此元素的示例。</span><span class="sxs-lookup"><span data-stu-id="b077b-140">See the [\<dataContractSerializer>](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-element.md) for an example of using this element.</span></span>  
  
 <span data-ttu-id="b077b-141">此配置元素不能同时具有两个属性。</span><span class="sxs-lookup"><span data-stu-id="b077b-141">This configuration element cannot have both attributes at the same time.</span></span> <span data-ttu-id="b077b-142">如果设置两个属性，则发生 <xref:System.Configuration.ConfigurationErrorsException>。</span><span class="sxs-lookup"><span data-stu-id="b077b-142">If both attributes are set, a <xref:System.Configuration.ConfigurationErrorsException> occurs.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b077b-143">请参阅</span><span class="sxs-lookup"><span data-stu-id="b077b-143">See also</span></span>
- <xref:System.Runtime.Serialization.DataContractSerializer>
- [<span data-ttu-id="b077b-144">数据协定已知类型</span><span class="sxs-lookup"><span data-stu-id="b077b-144">Data Contract Known Types</span></span>](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md)
- [<span data-ttu-id="b077b-145">\<dataContractSerializer></span><span class="sxs-lookup"><span data-stu-id="b077b-145">\<dataContractSerializer></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-element.md)
- [<span data-ttu-id="b077b-146">\<add></span><span class="sxs-lookup"><span data-stu-id="b077b-146">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-declaredtypes-element.md)
