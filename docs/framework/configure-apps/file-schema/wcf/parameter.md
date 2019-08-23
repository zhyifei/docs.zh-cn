---
title: <parameter>
ms.date: 03/30/2017
ms.assetid: 0fb41e2d-64f7-44ab-993e-05892eac6d82
ms.openlocfilehash: c3f2179835ad1232e115cad0decdd3d41bbdc160
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69932837"
---
# <a name="parameter"></a><span data-ttu-id="bd67b-101">\<parameter></span><span class="sxs-lookup"><span data-stu-id="bd67b-101">\<parameter></span></span>
<span data-ttu-id="bd67b-102">指定当声明类型是泛型类型时的泛型参数。</span><span class="sxs-lookup"><span data-stu-id="bd67b-102">Specifies the generic parameter when a declared type is a generic type.</span></span>  
  
 <span data-ttu-id="bd67b-103">\<system.runtime.serialization></span><span class="sxs-lookup"><span data-stu-id="bd67b-103">\<system.runtime.serialization></span></span>  
<span data-ttu-id="bd67b-104">\<dataContractSerializer></span><span class="sxs-lookup"><span data-stu-id="bd67b-104">\<dataContractSerializer></span></span>  
<span data-ttu-id="bd67b-105">\<declaredTypes > 元素</span><span class="sxs-lookup"><span data-stu-id="bd67b-105">\<declaredTypes> Element</span></span>  
<span data-ttu-id="bd67b-106">\<添加 declaredTypes 的\<> 元素 ></span><span class="sxs-lookup"><span data-stu-id="bd67b-106">\<add> element for \<declaredTypes></span></span>  
<span data-ttu-id="bd67b-107">\<knownType > 元素</span><span class="sxs-lookup"><span data-stu-id="bd67b-107">\<knownType> Element</span></span>  
<span data-ttu-id="bd67b-108">\<参数 > 元素</span><span class="sxs-lookup"><span data-stu-id="bd67b-108">\<parameter> Element</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bd67b-109">语法</span><span class="sxs-lookup"><span data-stu-id="bd67b-109">Syntax</span></span>  
  
```xml  
<parameter index="Integer"
           type="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="bd67b-110">特性和元素</span><span class="sxs-lookup"><span data-stu-id="bd67b-110">Attributes and Elements</span></span>  
 <span data-ttu-id="bd67b-111">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="bd67b-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="bd67b-112">特性</span><span class="sxs-lookup"><span data-stu-id="bd67b-112">Attributes</span></span>  
  
|<span data-ttu-id="bd67b-113">特性</span><span class="sxs-lookup"><span data-stu-id="bd67b-113">Attribute</span></span>|<span data-ttu-id="bd67b-114">描述</span><span class="sxs-lookup"><span data-stu-id="bd67b-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="bd67b-115">索引</span><span class="sxs-lookup"><span data-stu-id="bd67b-115">index</span></span>|<span data-ttu-id="bd67b-116">当声明类型是泛型类型时，指定将返回已知类型的泛型参数。</span><span class="sxs-lookup"><span data-stu-id="bd67b-116">When the declared type is a generic type, specifies the generic parameter that will return the known type.</span></span>|  
|<span data-ttu-id="bd67b-117">type</span><span class="sxs-lookup"><span data-stu-id="bd67b-117">type</span></span>|<span data-ttu-id="bd67b-118">一个字符串，描述用于序列化和反序列化的已知类型。</span><span class="sxs-lookup"><span data-stu-id="bd67b-118">A string that describes the known type used for serialization and deserialization.</span></span>|  
  
## <a name="index-attribute"></a><span data-ttu-id="bd67b-119">index 特性</span><span class="sxs-lookup"><span data-stu-id="bd67b-119">index Attribute</span></span>  
  
|<span data-ttu-id="bd67b-120">值</span><span class="sxs-lookup"><span data-stu-id="bd67b-120">Value</span></span>|<span data-ttu-id="bd67b-121">描述</span><span class="sxs-lookup"><span data-stu-id="bd67b-121">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="bd67b-122">“0”</span><span class="sxs-lookup"><span data-stu-id="bd67b-122">"0"</span></span>|<span data-ttu-id="bd67b-123">泛型类型中的第一个参数。</span><span class="sxs-lookup"><span data-stu-id="bd67b-123">The first parameter in the generic type.</span></span> <span data-ttu-id="bd67b-124">例如，一个 <xref:System.Collections.Generic.List%601> 仅有一个参数。</span><span class="sxs-lookup"><span data-stu-id="bd67b-124">For example, a <xref:System.Collections.Generic.List%601> has only one parameter.</span></span> <span data-ttu-id="bd67b-125">如果此参数用作声明类型，则将 index 特性设置为“0”。</span><span class="sxs-lookup"><span data-stu-id="bd67b-125">If it is used as the declared type, the index would be set to "0".</span></span>|  
|<span data-ttu-id="bd67b-126">"1"</span><span class="sxs-lookup"><span data-stu-id="bd67b-126">"1"</span></span>|<span data-ttu-id="bd67b-127">泛型类型中的第二个参数。</span><span class="sxs-lookup"><span data-stu-id="bd67b-127">The second parameter in a generic type.</span></span> <span data-ttu-id="bd67b-128">例如，一个 <xref:System.Collections.Generic.Dictionary%602> 有两个参数。</span><span class="sxs-lookup"><span data-stu-id="bd67b-128">For example, a <xref:System.Collections.Generic.Dictionary%602> has two parameters.</span></span> <span data-ttu-id="bd67b-129">如果通过第二个参数返回已知类型，则将 index 特性设置为“1”。</span><span class="sxs-lookup"><span data-stu-id="bd67b-129">If the known type is returned by the second parameter, set the index attribute to "1".</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="bd67b-130">子元素</span><span class="sxs-lookup"><span data-stu-id="bd67b-130">Child Elements</span></span>  
 <span data-ttu-id="bd67b-131">无。</span><span class="sxs-lookup"><span data-stu-id="bd67b-131">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="bd67b-132">父元素</span><span class="sxs-lookup"><span data-stu-id="bd67b-132">Parent Elements</span></span>  
  
|<span data-ttu-id="bd67b-133">元素</span><span class="sxs-lookup"><span data-stu-id="bd67b-133">Element</span></span>|<span data-ttu-id="bd67b-134">描述</span><span class="sxs-lookup"><span data-stu-id="bd67b-134">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="bd67b-135">\<knownType></span><span class="sxs-lookup"><span data-stu-id="bd67b-135">\<knownType></span></span>](knowntype.md)|<span data-ttu-id="bd67b-136">指定一个可由声明类型的字段或属性返回的已知类型。</span><span class="sxs-lookup"><span data-stu-id="bd67b-136">Specifies a known type that can be returned by a field or property of the declared type.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bd67b-137">备注</span><span class="sxs-lookup"><span data-stu-id="bd67b-137">Remarks</span></span>  
 <span data-ttu-id="bd67b-138">有关已知类型的详细信息, 请参阅[数据协定已知类型](../../../wcf/feature-details/data-contract-known-types.md)和<xref:System.Runtime.Serialization.DataContractSerializer>。</span><span class="sxs-lookup"><span data-stu-id="bd67b-138">For more information about known types, see [Data Contract Known Types](../../../wcf/feature-details/data-contract-known-types.md) and <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  
  
 <span data-ttu-id="bd67b-139">有关使用此元素的示例, 请参阅[ dataContractSerializer>。\<](datacontractserializer-element.md)</span><span class="sxs-lookup"><span data-stu-id="bd67b-139">See the [\<dataContractSerializer>](datacontractserializer-element.md) for an example of using this element.</span></span>  
  
 <span data-ttu-id="bd67b-140">此配置元素不能同时具有两个属性。</span><span class="sxs-lookup"><span data-stu-id="bd67b-140">This configuration element cannot have both attributes at the same time.</span></span> <span data-ttu-id="bd67b-141">如果设置两个属性，则发生 <xref:System.Configuration.ConfigurationErrorsException>。</span><span class="sxs-lookup"><span data-stu-id="bd67b-141">If both attributes are set, a <xref:System.Configuration.ConfigurationErrorsException> occurs.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bd67b-142">请参阅</span><span class="sxs-lookup"><span data-stu-id="bd67b-142">See also</span></span>

- <xref:System.Runtime.Serialization.DataContractSerializer>
- [<span data-ttu-id="bd67b-143">数据协定已知类型</span><span class="sxs-lookup"><span data-stu-id="bd67b-143">Data Contract Known Types</span></span>](../../../wcf/feature-details/data-contract-known-types.md)
- [<span data-ttu-id="bd67b-144">\<dataContractSerializer></span><span class="sxs-lookup"><span data-stu-id="bd67b-144">\<dataContractSerializer></span></span>](datacontractserializer-element.md)
- [<span data-ttu-id="bd67b-145">\<add></span><span class="sxs-lookup"><span data-stu-id="bd67b-145">\<add></span></span>](add-of-declaredtypes-element.md)
