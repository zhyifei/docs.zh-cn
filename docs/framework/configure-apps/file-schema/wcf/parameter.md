---
title: '&lt;parameter&gt;'
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0fb41e2d-64f7-44ab-993e-05892eac6d82
caps.latest.revision: 9
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: aa4b2c870864a4359ebca0a1ae47fc1c8aaebca0
ms.sourcegitcommit: 94d33cadc5ff81d2ac389bf5f26422c227832052
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/30/2018
---
# <a name="ltparametergt"></a><span data-ttu-id="081f8-102">&lt;parameter&gt;</span><span class="sxs-lookup"><span data-stu-id="081f8-102">&lt;parameter&gt;</span></span>
<span data-ttu-id="081f8-103">指定当声明类型是泛型类型时的泛型参数。</span><span class="sxs-lookup"><span data-stu-id="081f8-103">Specifies the generic parameter when a declared type is a generic type.</span></span>  
  
 <span data-ttu-id="081f8-104">\<system.runtime.serialization ></span><span class="sxs-lookup"><span data-stu-id="081f8-104">\<system.runtime.serialization></span></span>  
<span data-ttu-id="081f8-105">\<dataContractSerializer ></span><span class="sxs-lookup"><span data-stu-id="081f8-105">\<dataContractSerializer></span></span>  
<span data-ttu-id="081f8-106">\<d d > 元素</span><span class="sxs-lookup"><span data-stu-id="081f8-106">\<declaredTypes> Element</span></span>  
<span data-ttu-id="081f8-107">\<添加 > 元素\<d d ></span><span class="sxs-lookup"><span data-stu-id="081f8-107">\<add> element for \<declaredTypes></span></span>  
<span data-ttu-id="081f8-108">\<knownType > 元素</span><span class="sxs-lookup"><span data-stu-id="081f8-108">\<knownType> Element</span></span>  
<span data-ttu-id="081f8-109">\<参数 > 元素</span><span class="sxs-lookup"><span data-stu-id="081f8-109">\<parameter> Element</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="081f8-110">语法</span><span class="sxs-lookup"><span data-stu-id="081f8-110">Syntax</span></span>  
  
```xml  
<parameter index="integer"  
                      type=String" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="081f8-111">特性和元素</span><span class="sxs-lookup"><span data-stu-id="081f8-111">Attributes and Elements</span></span>  
 <span data-ttu-id="081f8-112">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="081f8-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="081f8-113">特性</span><span class="sxs-lookup"><span data-stu-id="081f8-113">Attributes</span></span>  
  
|<span data-ttu-id="081f8-114">特性</span><span class="sxs-lookup"><span data-stu-id="081f8-114">Attribute</span></span>|<span data-ttu-id="081f8-115">描述</span><span class="sxs-lookup"><span data-stu-id="081f8-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="081f8-116">索引</span><span class="sxs-lookup"><span data-stu-id="081f8-116">index</span></span>|<span data-ttu-id="081f8-117">当声明类型是泛型类型时，指定将返回已知类型的泛型参数。</span><span class="sxs-lookup"><span data-stu-id="081f8-117">When the declared type is a generic type, specifies the generic parameter that will return the known type.</span></span>|  
|<span data-ttu-id="081f8-118">类型</span><span class="sxs-lookup"><span data-stu-id="081f8-118">type</span></span>|<span data-ttu-id="081f8-119">一个字符串，描述用于序列化和反序列化的已知类型。</span><span class="sxs-lookup"><span data-stu-id="081f8-119">A string that describes the known type used for serialization and deserialization.</span></span>|  
  
## <a name="index-attribute"></a><span data-ttu-id="081f8-120">index 特性</span><span class="sxs-lookup"><span data-stu-id="081f8-120">index Attribute</span></span>  
  
|<span data-ttu-id="081f8-121">值</span><span class="sxs-lookup"><span data-stu-id="081f8-121">Value</span></span>|<span data-ttu-id="081f8-122">描述</span><span class="sxs-lookup"><span data-stu-id="081f8-122">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="081f8-123">“0”</span><span class="sxs-lookup"><span data-stu-id="081f8-123">"0"</span></span>|<span data-ttu-id="081f8-124">泛型类型中的第一个参数。</span><span class="sxs-lookup"><span data-stu-id="081f8-124">The first parameter in the generic type.</span></span> <span data-ttu-id="081f8-125">例如，一个 <xref:System.Collections.Generic.List%601> 仅有一个参数。</span><span class="sxs-lookup"><span data-stu-id="081f8-125">For example, a <xref:System.Collections.Generic.List%601> has only one parameter.</span></span> <span data-ttu-id="081f8-126">如果此参数用作声明类型，则将 index 特性设置为“0”。</span><span class="sxs-lookup"><span data-stu-id="081f8-126">If it is used as the declared type, the index would be set to "0".</span></span>|  
|<span data-ttu-id="081f8-127">"1"</span><span class="sxs-lookup"><span data-stu-id="081f8-127">"1"</span></span>|<span data-ttu-id="081f8-128">泛型类型中的第二个参数。</span><span class="sxs-lookup"><span data-stu-id="081f8-128">The second parameter in a generic type.</span></span> <span data-ttu-id="081f8-129">例如，一个 <xref:System.Collections.Generic.Dictionary%602> 有两个参数。</span><span class="sxs-lookup"><span data-stu-id="081f8-129">For example, a <xref:System.Collections.Generic.Dictionary%602> has two parameters.</span></span> <span data-ttu-id="081f8-130">如果通过第二个参数返回已知类型，则将 index 特性设置为“1”。</span><span class="sxs-lookup"><span data-stu-id="081f8-130">If the known type is returned by the second parameter, set the index attribute to "1".</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="081f8-131">子元素</span><span class="sxs-lookup"><span data-stu-id="081f8-131">Child Elements</span></span>  
 <span data-ttu-id="081f8-132">无。</span><span class="sxs-lookup"><span data-stu-id="081f8-132">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="081f8-133">父元素</span><span class="sxs-lookup"><span data-stu-id="081f8-133">Parent Elements</span></span>  
  
|<span data-ttu-id="081f8-134">元素</span><span class="sxs-lookup"><span data-stu-id="081f8-134">Element</span></span>|<span data-ttu-id="081f8-135">描述</span><span class="sxs-lookup"><span data-stu-id="081f8-135">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="081f8-136">\<knownType ></span><span class="sxs-lookup"><span data-stu-id="081f8-136">\<knownType></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/knowntype.md)|<span data-ttu-id="081f8-137">指定一个可由声明类型的字段或属性返回的已知类型。</span><span class="sxs-lookup"><span data-stu-id="081f8-137">Specifies a known type that can be returned by a field or property of the declared type.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="081f8-138">备注</span><span class="sxs-lookup"><span data-stu-id="081f8-138">Remarks</span></span>  
 <span data-ttu-id="081f8-139">有关已知类型的详细信息，请参阅[数据协定已知类型](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md)和<xref:System.Runtime.Serialization.DataContractSerializer>。</span><span class="sxs-lookup"><span data-stu-id="081f8-139">For more information about known types, see [Data Contract Known Types](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md) and <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  
  
 <span data-ttu-id="081f8-140">请参阅[ \<dataContractSerializer >](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-element.md)有关使用此元素的示例。</span><span class="sxs-lookup"><span data-stu-id="081f8-140">See the [\<dataContractSerializer>](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-element.md) for an example of using this element.</span></span>  
  
 <span data-ttu-id="081f8-141">此配置元素不能同时具有两个属性。</span><span class="sxs-lookup"><span data-stu-id="081f8-141">This configuration element cannot have both attributes at the same time.</span></span> <span data-ttu-id="081f8-142">如果设置两个属性，则发生 <xref:System.Configuration.ConfigurationErrorsException>。</span><span class="sxs-lookup"><span data-stu-id="081f8-142">If both attributes are set, a <xref:System.Configuration.ConfigurationErrorsException> occurs.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="081f8-143">请参阅</span><span class="sxs-lookup"><span data-stu-id="081f8-143">See Also</span></span>  
 <xref:System.Runtime.Serialization.DataContractSerializer>  
 [<span data-ttu-id="081f8-144">数据协定已知类型</span><span class="sxs-lookup"><span data-stu-id="081f8-144">Data Contract Known Types</span></span>](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md)  
 [<span data-ttu-id="081f8-145">\<dataContractSerializer ></span><span class="sxs-lookup"><span data-stu-id="081f8-145">\<dataContractSerializer></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-element.md)  
 [<span data-ttu-id="081f8-146">\<add></span><span class="sxs-lookup"><span data-stu-id="081f8-146">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-declaredtypes-element.md)
