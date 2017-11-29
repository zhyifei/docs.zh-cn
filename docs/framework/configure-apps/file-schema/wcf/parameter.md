---
title: "&lt;参数&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0fb41e2d-64f7-44ab-993e-05892eac6d82
caps.latest.revision: "9"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: e9db1921e2a6ee1ae2780f744c45fdb25efbf797
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="ltparametergt"></a><span data-ttu-id="9b79d-102">&lt;参数&gt;</span><span class="sxs-lookup"><span data-stu-id="9b79d-102">&lt;parameter&gt;</span></span>
<span data-ttu-id="9b79d-103">指定当声明类型是泛型类型时的泛型参数。</span><span class="sxs-lookup"><span data-stu-id="9b79d-103">Specifies the generic parameter when a declared type is a generic type.</span></span>  
  
 <span data-ttu-id="9b79d-104">\<system.runtime.serialization ></span><span class="sxs-lookup"><span data-stu-id="9b79d-104">\<system.runtime.serialization></span></span>  
<span data-ttu-id="9b79d-105">\<dataContractSerializer ></span><span class="sxs-lookup"><span data-stu-id="9b79d-105">\<dataContractSerializer></span></span>  
<span data-ttu-id="9b79d-106">\<d d > 元素</span><span class="sxs-lookup"><span data-stu-id="9b79d-106">\<declaredTypes> Element</span></span>  
<span data-ttu-id="9b79d-107">\<添加 > 元素\<d d ></span><span class="sxs-lookup"><span data-stu-id="9b79d-107">\<add> element for \<declaredTypes></span></span>  
<span data-ttu-id="9b79d-108">\<knownType > 元素</span><span class="sxs-lookup"><span data-stu-id="9b79d-108">\<knownType> Element</span></span>  
<span data-ttu-id="9b79d-109">\<参数 > 元素</span><span class="sxs-lookup"><span data-stu-id="9b79d-109">\<parameter> Element</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9b79d-110">语法</span><span class="sxs-lookup"><span data-stu-id="9b79d-110">Syntax</span></span>  
  
```xml  
<parameter index="integer"  
                      type=String" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9b79d-111">特性和元素</span><span class="sxs-lookup"><span data-stu-id="9b79d-111">Attributes and Elements</span></span>  
 <span data-ttu-id="9b79d-112">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="9b79d-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9b79d-113">特性</span><span class="sxs-lookup"><span data-stu-id="9b79d-113">Attributes</span></span>  
  
|<span data-ttu-id="9b79d-114">特性</span><span class="sxs-lookup"><span data-stu-id="9b79d-114">Attribute</span></span>|<span data-ttu-id="9b79d-115">描述</span><span class="sxs-lookup"><span data-stu-id="9b79d-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="9b79d-116">索引</span><span class="sxs-lookup"><span data-stu-id="9b79d-116">index</span></span>|<span data-ttu-id="9b79d-117">当声明类型是泛型类型时，指定将返回已知类型的泛型参数。</span><span class="sxs-lookup"><span data-stu-id="9b79d-117">When the declared type is a generic type, specifies the generic parameter that will return the known type.</span></span>|  
|<span data-ttu-id="9b79d-118">类型</span><span class="sxs-lookup"><span data-stu-id="9b79d-118">type</span></span>|<span data-ttu-id="9b79d-119">一个字符串，描述用于序列化和反序列化的已知类型。</span><span class="sxs-lookup"><span data-stu-id="9b79d-119">A string that describes the known type used for serialization and deserialization.</span></span>|  
  
## <a name="index-attribute"></a><span data-ttu-id="9b79d-120">index 特性</span><span class="sxs-lookup"><span data-stu-id="9b79d-120">index Attribute</span></span>  
  
|<span data-ttu-id="9b79d-121">值</span><span class="sxs-lookup"><span data-stu-id="9b79d-121">Value</span></span>|<span data-ttu-id="9b79d-122">描述</span><span class="sxs-lookup"><span data-stu-id="9b79d-122">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="9b79d-123">“0”</span><span class="sxs-lookup"><span data-stu-id="9b79d-123">"0"</span></span>|<span data-ttu-id="9b79d-124">泛型类型中的第一个参数。</span><span class="sxs-lookup"><span data-stu-id="9b79d-124">The first parameter in the generic type.</span></span> <span data-ttu-id="9b79d-125">例如，一个 <xref:System.Collections.Generic.List%601> 仅有一个参数。</span><span class="sxs-lookup"><span data-stu-id="9b79d-125">For example, a <xref:System.Collections.Generic.List%601> has only one parameter.</span></span> <span data-ttu-id="9b79d-126">如果此参数用作声明类型，则将 index 特性设置为“0”。</span><span class="sxs-lookup"><span data-stu-id="9b79d-126">If it is used as the declared type, the index would be set to "0".</span></span>|  
|<span data-ttu-id="9b79d-127">"1"</span><span class="sxs-lookup"><span data-stu-id="9b79d-127">"1"</span></span>|<span data-ttu-id="9b79d-128">泛型类型中的第二个参数。</span><span class="sxs-lookup"><span data-stu-id="9b79d-128">The second parameter in a generic type.</span></span> <span data-ttu-id="9b79d-129">例如，一个 <xref:System.Collections.Generic.Dictionary%602> 有两个参数。</span><span class="sxs-lookup"><span data-stu-id="9b79d-129">For example, a <xref:System.Collections.Generic.Dictionary%602> has two parameters.</span></span> <span data-ttu-id="9b79d-130">如果通过第二个参数返回已知类型，则将 index 特性设置为“1”。</span><span class="sxs-lookup"><span data-stu-id="9b79d-130">If the known type is returned by the second parameter, set the index attribute to "1".</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="9b79d-131">子元素</span><span class="sxs-lookup"><span data-stu-id="9b79d-131">Child Elements</span></span>  
 <span data-ttu-id="9b79d-132">无。</span><span class="sxs-lookup"><span data-stu-id="9b79d-132">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="9b79d-133">父元素</span><span class="sxs-lookup"><span data-stu-id="9b79d-133">Parent Elements</span></span>  
  
|<span data-ttu-id="9b79d-134">元素</span><span class="sxs-lookup"><span data-stu-id="9b79d-134">Element</span></span>|<span data-ttu-id="9b79d-135">描述</span><span class="sxs-lookup"><span data-stu-id="9b79d-135">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9b79d-136">\<knownType ></span><span class="sxs-lookup"><span data-stu-id="9b79d-136">\<knownType></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/knowntype.md)|<span data-ttu-id="9b79d-137">指定一个可由声明类型的字段或属性返回的已知类型。</span><span class="sxs-lookup"><span data-stu-id="9b79d-137">Specifies a known type that can be returned by a field or property of the declared type.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9b79d-138">备注</span><span class="sxs-lookup"><span data-stu-id="9b79d-138">Remarks</span></span>  
 [!INCLUDE[crabout](../../../../../includes/crabout-md.md)]<span data-ttu-id="9b79d-139">已知类型，请参阅[数据协定已知类型](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md)和<xref:System.Runtime.Serialization.DataContractSerializer>。</span><span class="sxs-lookup"><span data-stu-id="9b79d-139"> known types, see [Data Contract Known Types](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md) and <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  
  
 <span data-ttu-id="9b79d-140">请参阅[ \<dataContractSerializer >](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-element.md)有关使用此元素的示例。</span><span class="sxs-lookup"><span data-stu-id="9b79d-140">See the [\<dataContractSerializer>](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-element.md) for an example of using this element.</span></span>  
  
 <span data-ttu-id="9b79d-141">此配置元素不能同时具有两个属性。</span><span class="sxs-lookup"><span data-stu-id="9b79d-141">This configuration element cannot have both attributes at the same time.</span></span> <span data-ttu-id="9b79d-142">如果设置两个属性，则发生 <xref:System.Configuration.ConfigurationErrorsException>。</span><span class="sxs-lookup"><span data-stu-id="9b79d-142">If both attributes are set, a <xref:System.Configuration.ConfigurationErrorsException> occurs.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9b79d-143">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9b79d-143">See Also</span></span>  
 <xref:System.Runtime.Serialization.DataContractSerializer>  
 [<span data-ttu-id="9b79d-144">数据协定已知的类型</span><span class="sxs-lookup"><span data-stu-id="9b79d-144">Data Contract Known Types</span></span>](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md)  
 [<span data-ttu-id="9b79d-145">\<dataContractSerializer ></span><span class="sxs-lookup"><span data-stu-id="9b79d-145">\<dataContractSerializer></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-element.md)  
 [<span data-ttu-id="9b79d-146">\<add></span><span class="sxs-lookup"><span data-stu-id="9b79d-146">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-declaredtypes-element.md)
