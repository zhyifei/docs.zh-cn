---
title: '&lt;parameter&gt;'
ms.date: 03/30/2017
ms.assetid: 0fb41e2d-64f7-44ab-993e-05892eac6d82
ms.openlocfilehash: 82a2f5c46c698508695fe5f13f67059860a50713
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/09/2019
ms.locfileid: "54148287"
---
# <a name="ltparametergt"></a><span data-ttu-id="db24c-102">&lt;parameter&gt;</span><span class="sxs-lookup"><span data-stu-id="db24c-102">&lt;parameter&gt;</span></span>
<span data-ttu-id="db24c-103">指定当声明类型是泛型类型时的泛型参数。</span><span class="sxs-lookup"><span data-stu-id="db24c-103">Specifies the generic parameter when a declared type is a generic type.</span></span>  
  
 <span data-ttu-id="db24c-104">\<system.runtime.serialization ></span><span class="sxs-lookup"><span data-stu-id="db24c-104">\<system.runtime.serialization></span></span>  
<span data-ttu-id="db24c-105">\<dataContractSerializer ></span><span class="sxs-lookup"><span data-stu-id="db24c-105">\<dataContractSerializer></span></span>  
<span data-ttu-id="db24c-106">\<declaredTypes > 元素</span><span class="sxs-lookup"><span data-stu-id="db24c-106">\<declaredTypes> Element</span></span>  
<span data-ttu-id="db24c-107">\<添加 > 元素\<declaredTypes ></span><span class="sxs-lookup"><span data-stu-id="db24c-107">\<add> element for \<declaredTypes></span></span>  
<span data-ttu-id="db24c-108">\<knownType > 元素</span><span class="sxs-lookup"><span data-stu-id="db24c-108">\<knownType> Element</span></span>  
<span data-ttu-id="db24c-109">\<参数 > 元素</span><span class="sxs-lookup"><span data-stu-id="db24c-109">\<parameter> Element</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="db24c-110">语法</span><span class="sxs-lookup"><span data-stu-id="db24c-110">Syntax</span></span>  
  
```xml  
<parameter index="Integer"
           type="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="db24c-111">特性和元素</span><span class="sxs-lookup"><span data-stu-id="db24c-111">Attributes and Elements</span></span>  
 <span data-ttu-id="db24c-112">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="db24c-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="db24c-113">特性</span><span class="sxs-lookup"><span data-stu-id="db24c-113">Attributes</span></span>  
  
|<span data-ttu-id="db24c-114">特性</span><span class="sxs-lookup"><span data-stu-id="db24c-114">Attribute</span></span>|<span data-ttu-id="db24c-115">描述</span><span class="sxs-lookup"><span data-stu-id="db24c-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="db24c-116">索引</span><span class="sxs-lookup"><span data-stu-id="db24c-116">index</span></span>|<span data-ttu-id="db24c-117">当声明类型是泛型类型时，指定将返回已知类型的泛型参数。</span><span class="sxs-lookup"><span data-stu-id="db24c-117">When the declared type is a generic type, specifies the generic parameter that will return the known type.</span></span>|  
|<span data-ttu-id="db24c-118">类型</span><span class="sxs-lookup"><span data-stu-id="db24c-118">type</span></span>|<span data-ttu-id="db24c-119">一个字符串，描述用于序列化和反序列化的已知类型。</span><span class="sxs-lookup"><span data-stu-id="db24c-119">A string that describes the known type used for serialization and deserialization.</span></span>|  
  
## <a name="index-attribute"></a><span data-ttu-id="db24c-120">index 特性</span><span class="sxs-lookup"><span data-stu-id="db24c-120">index Attribute</span></span>  
  
|<span data-ttu-id="db24c-121">值</span><span class="sxs-lookup"><span data-stu-id="db24c-121">Value</span></span>|<span data-ttu-id="db24c-122">描述</span><span class="sxs-lookup"><span data-stu-id="db24c-122">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="db24c-123">“0”</span><span class="sxs-lookup"><span data-stu-id="db24c-123">"0"</span></span>|<span data-ttu-id="db24c-124">泛型类型中的第一个参数。</span><span class="sxs-lookup"><span data-stu-id="db24c-124">The first parameter in the generic type.</span></span> <span data-ttu-id="db24c-125">例如，一个 <xref:System.Collections.Generic.List%601> 仅有一个参数。</span><span class="sxs-lookup"><span data-stu-id="db24c-125">For example, a <xref:System.Collections.Generic.List%601> has only one parameter.</span></span> <span data-ttu-id="db24c-126">如果此参数用作声明类型，则将 index 特性设置为“0”。</span><span class="sxs-lookup"><span data-stu-id="db24c-126">If it is used as the declared type, the index would be set to "0".</span></span>|  
|<span data-ttu-id="db24c-127">"1"</span><span class="sxs-lookup"><span data-stu-id="db24c-127">"1"</span></span>|<span data-ttu-id="db24c-128">泛型类型中的第二个参数。</span><span class="sxs-lookup"><span data-stu-id="db24c-128">The second parameter in a generic type.</span></span> <span data-ttu-id="db24c-129">例如，一个 <xref:System.Collections.Generic.Dictionary%602> 有两个参数。</span><span class="sxs-lookup"><span data-stu-id="db24c-129">For example, a <xref:System.Collections.Generic.Dictionary%602> has two parameters.</span></span> <span data-ttu-id="db24c-130">如果通过第二个参数返回已知类型，则将 index 特性设置为“1”。</span><span class="sxs-lookup"><span data-stu-id="db24c-130">If the known type is returned by the second parameter, set the index attribute to "1".</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="db24c-131">子元素</span><span class="sxs-lookup"><span data-stu-id="db24c-131">Child Elements</span></span>  
 <span data-ttu-id="db24c-132">无。</span><span class="sxs-lookup"><span data-stu-id="db24c-132">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="db24c-133">父元素</span><span class="sxs-lookup"><span data-stu-id="db24c-133">Parent Elements</span></span>  
  
|<span data-ttu-id="db24c-134">元素</span><span class="sxs-lookup"><span data-stu-id="db24c-134">Element</span></span>|<span data-ttu-id="db24c-135">描述</span><span class="sxs-lookup"><span data-stu-id="db24c-135">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="db24c-136">\<knownType ></span><span class="sxs-lookup"><span data-stu-id="db24c-136">\<knownType></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/knowntype.md)|<span data-ttu-id="db24c-137">指定一个可由声明类型的字段或属性返回的已知类型。</span><span class="sxs-lookup"><span data-stu-id="db24c-137">Specifies a known type that can be returned by a field or property of the declared type.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="db24c-138">备注</span><span class="sxs-lookup"><span data-stu-id="db24c-138">Remarks</span></span>  
 <span data-ttu-id="db24c-139">有关已知类型的详细信息，请参阅[Data Contract Known Types](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md)和<xref:System.Runtime.Serialization.DataContractSerializer>。</span><span class="sxs-lookup"><span data-stu-id="db24c-139">For more information about known types, see [Data Contract Known Types](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md) and <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  
  
 <span data-ttu-id="db24c-140">请参阅[ \<dataContractSerializer >](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-element.md)有关使用此元素的示例。</span><span class="sxs-lookup"><span data-stu-id="db24c-140">See the [\<dataContractSerializer>](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-element.md) for an example of using this element.</span></span>  
  
 <span data-ttu-id="db24c-141">此配置元素不能同时具有两个属性。</span><span class="sxs-lookup"><span data-stu-id="db24c-141">This configuration element cannot have both attributes at the same time.</span></span> <span data-ttu-id="db24c-142">如果设置两个属性，则发生 <xref:System.Configuration.ConfigurationErrorsException>。</span><span class="sxs-lookup"><span data-stu-id="db24c-142">If both attributes are set, a <xref:System.Configuration.ConfigurationErrorsException> occurs.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="db24c-143">请参阅</span><span class="sxs-lookup"><span data-stu-id="db24c-143">See Also</span></span>  
 <xref:System.Runtime.Serialization.DataContractSerializer>  
 [<span data-ttu-id="db24c-144">数据协定已知类型</span><span class="sxs-lookup"><span data-stu-id="db24c-144">Data Contract Known Types</span></span>](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md)  
 [<span data-ttu-id="db24c-145">\<dataContractSerializer ></span><span class="sxs-lookup"><span data-stu-id="db24c-145">\<dataContractSerializer></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-element.md)  
 [<span data-ttu-id="db24c-146">\<add></span><span class="sxs-lookup"><span data-stu-id="db24c-146">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-declaredtypes-element.md)
