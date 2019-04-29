---
title: <parameter>
ms.date: 03/30/2017
ms.assetid: 0fb41e2d-64f7-44ab-993e-05892eac6d82
ms.openlocfilehash: 22ef3c3c6d23d6c68c27d6b5d1ed35b7c9910d48
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61783430"
---
# <a name="parameter"></a><span data-ttu-id="a407e-101">\<parameter></span><span class="sxs-lookup"><span data-stu-id="a407e-101">\<parameter></span></span>
<span data-ttu-id="a407e-102">指定当声明类型是泛型类型时的泛型参数。</span><span class="sxs-lookup"><span data-stu-id="a407e-102">Specifies the generic parameter when a declared type is a generic type.</span></span>  
  
 <span data-ttu-id="a407e-103">\<system.runtime.serialization></span><span class="sxs-lookup"><span data-stu-id="a407e-103">\<system.runtime.serialization></span></span>  
<span data-ttu-id="a407e-104">\<dataContractSerializer></span><span class="sxs-lookup"><span data-stu-id="a407e-104">\<dataContractSerializer></span></span>  
<span data-ttu-id="a407e-105">\<declaredTypes > 元素</span><span class="sxs-lookup"><span data-stu-id="a407e-105">\<declaredTypes> Element</span></span>  
<span data-ttu-id="a407e-106">\<添加 > 元素\<declaredTypes ></span><span class="sxs-lookup"><span data-stu-id="a407e-106">\<add> element for \<declaredTypes></span></span>  
<span data-ttu-id="a407e-107">\<knownType > 元素</span><span class="sxs-lookup"><span data-stu-id="a407e-107">\<knownType> Element</span></span>  
<span data-ttu-id="a407e-108">\<参数 > 元素</span><span class="sxs-lookup"><span data-stu-id="a407e-108">\<parameter> Element</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a407e-109">语法</span><span class="sxs-lookup"><span data-stu-id="a407e-109">Syntax</span></span>  
  
```xml  
<parameter index="Integer"
           type="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a407e-110">特性和元素</span><span class="sxs-lookup"><span data-stu-id="a407e-110">Attributes and Elements</span></span>  
 <span data-ttu-id="a407e-111">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="a407e-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a407e-112">特性</span><span class="sxs-lookup"><span data-stu-id="a407e-112">Attributes</span></span>  
  
|<span data-ttu-id="a407e-113">特性</span><span class="sxs-lookup"><span data-stu-id="a407e-113">Attribute</span></span>|<span data-ttu-id="a407e-114">描述</span><span class="sxs-lookup"><span data-stu-id="a407e-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="a407e-115">索引</span><span class="sxs-lookup"><span data-stu-id="a407e-115">index</span></span>|<span data-ttu-id="a407e-116">当声明类型是泛型类型时，指定将返回已知类型的泛型参数。</span><span class="sxs-lookup"><span data-stu-id="a407e-116">When the declared type is a generic type, specifies the generic parameter that will return the known type.</span></span>|  
|<span data-ttu-id="a407e-117">类型</span><span class="sxs-lookup"><span data-stu-id="a407e-117">type</span></span>|<span data-ttu-id="a407e-118">一个字符串，描述用于序列化和反序列化的已知类型。</span><span class="sxs-lookup"><span data-stu-id="a407e-118">A string that describes the known type used for serialization and deserialization.</span></span>|  
  
## <a name="index-attribute"></a><span data-ttu-id="a407e-119">index 特性</span><span class="sxs-lookup"><span data-stu-id="a407e-119">index Attribute</span></span>  
  
|<span data-ttu-id="a407e-120">“值”</span><span class="sxs-lookup"><span data-stu-id="a407e-120">Value</span></span>|<span data-ttu-id="a407e-121">描述</span><span class="sxs-lookup"><span data-stu-id="a407e-121">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="a407e-122">“0”</span><span class="sxs-lookup"><span data-stu-id="a407e-122">"0"</span></span>|<span data-ttu-id="a407e-123">泛型类型中的第一个参数。</span><span class="sxs-lookup"><span data-stu-id="a407e-123">The first parameter in the generic type.</span></span> <span data-ttu-id="a407e-124">例如，一个 <xref:System.Collections.Generic.List%601> 仅有一个参数。</span><span class="sxs-lookup"><span data-stu-id="a407e-124">For example, a <xref:System.Collections.Generic.List%601> has only one parameter.</span></span> <span data-ttu-id="a407e-125">如果此参数用作声明类型，则将 index 特性设置为“0”。</span><span class="sxs-lookup"><span data-stu-id="a407e-125">If it is used as the declared type, the index would be set to "0".</span></span>|  
|<span data-ttu-id="a407e-126">"1"</span><span class="sxs-lookup"><span data-stu-id="a407e-126">"1"</span></span>|<span data-ttu-id="a407e-127">泛型类型中的第二个参数。</span><span class="sxs-lookup"><span data-stu-id="a407e-127">The second parameter in a generic type.</span></span> <span data-ttu-id="a407e-128">例如，一个 <xref:System.Collections.Generic.Dictionary%602> 有两个参数。</span><span class="sxs-lookup"><span data-stu-id="a407e-128">For example, a <xref:System.Collections.Generic.Dictionary%602> has two parameters.</span></span> <span data-ttu-id="a407e-129">如果通过第二个参数返回已知类型，则将 index 特性设置为“1”。</span><span class="sxs-lookup"><span data-stu-id="a407e-129">If the known type is returned by the second parameter, set the index attribute to "1".</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a407e-130">子元素</span><span class="sxs-lookup"><span data-stu-id="a407e-130">Child Elements</span></span>  
 <span data-ttu-id="a407e-131">无。</span><span class="sxs-lookup"><span data-stu-id="a407e-131">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="a407e-132">父元素</span><span class="sxs-lookup"><span data-stu-id="a407e-132">Parent Elements</span></span>  
  
|<span data-ttu-id="a407e-133">元素</span><span class="sxs-lookup"><span data-stu-id="a407e-133">Element</span></span>|<span data-ttu-id="a407e-134">描述</span><span class="sxs-lookup"><span data-stu-id="a407e-134">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a407e-135">\<knownType></span><span class="sxs-lookup"><span data-stu-id="a407e-135">\<knownType></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/knowntype.md)|<span data-ttu-id="a407e-136">指定一个可由声明类型的字段或属性返回的已知类型。</span><span class="sxs-lookup"><span data-stu-id="a407e-136">Specifies a known type that can be returned by a field or property of the declared type.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a407e-137">备注</span><span class="sxs-lookup"><span data-stu-id="a407e-137">Remarks</span></span>  
 <span data-ttu-id="a407e-138">有关已知类型的详细信息，请参阅[Data Contract Known Types](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md)和<xref:System.Runtime.Serialization.DataContractSerializer>。</span><span class="sxs-lookup"><span data-stu-id="a407e-138">For more information about known types, see [Data Contract Known Types](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md) and <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  
  
 <span data-ttu-id="a407e-139">请参阅[ \<dataContractSerializer >](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-element.md)有关使用此元素的示例。</span><span class="sxs-lookup"><span data-stu-id="a407e-139">See the [\<dataContractSerializer>](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-element.md) for an example of using this element.</span></span>  
  
 <span data-ttu-id="a407e-140">此配置元素不能同时具有两个属性。</span><span class="sxs-lookup"><span data-stu-id="a407e-140">This configuration element cannot have both attributes at the same time.</span></span> <span data-ttu-id="a407e-141">如果设置两个属性，则发生 <xref:System.Configuration.ConfigurationErrorsException>。</span><span class="sxs-lookup"><span data-stu-id="a407e-141">If both attributes are set, a <xref:System.Configuration.ConfigurationErrorsException> occurs.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a407e-142">请参阅</span><span class="sxs-lookup"><span data-stu-id="a407e-142">See also</span></span>

- <xref:System.Runtime.Serialization.DataContractSerializer>
- [<span data-ttu-id="a407e-143">数据协定已知类型</span><span class="sxs-lookup"><span data-stu-id="a407e-143">Data Contract Known Types</span></span>](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md)
- [<span data-ttu-id="a407e-144">\<dataContractSerializer></span><span class="sxs-lookup"><span data-stu-id="a407e-144">\<dataContractSerializer></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-element.md)
- [<span data-ttu-id="a407e-145">\<add></span><span class="sxs-lookup"><span data-stu-id="a407e-145">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-declaredtypes-element.md)
