---
title: <parameter>
ms.date: 03/30/2017
ms.assetid: 0fb41e2d-64f7-44ab-993e-05892eac6d82
ms.openlocfilehash: 07fa410109a7bd2fa315132c4737301698bb3a93
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/06/2019
ms.locfileid: "70400116"
---
# <a name="parameter"></a><span data-ttu-id="27488-101">\<parameter></span><span class="sxs-lookup"><span data-stu-id="27488-101">\<parameter></span></span>
<span data-ttu-id="27488-102">指定当声明类型是泛型类型时的泛型参数。</span><span class="sxs-lookup"><span data-stu-id="27488-102">Specifies the generic parameter when a declared type is a generic type.</span></span>  
  
<span data-ttu-id="27488-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="27488-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="27488-104">&nbsp;&nbsp;[ **\<system.object >** ](system-runtime-serialization.md)</span><span class="sxs-lookup"><span data-stu-id="27488-104">&nbsp;&nbsp;[**\<system.runtime.serialization>**](system-runtime-serialization.md)</span></span>\
<span data-ttu-id="27488-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<dataContractSerializer >** ](datacontractserializer.md)</span><span class="sxs-lookup"><span data-stu-id="27488-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<dataContractSerializer>**](datacontractserializer.md)</span></span>\
<span data-ttu-id="27488-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<declaredTypes >** ](declaredtypes.md)</span><span class="sxs-lookup"><span data-stu-id="27488-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<declaredTypes>**](declaredtypes.md)</span></span>\
<span data-ttu-id="27488-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<添加 >** ](add-of-declaredtypes-element.md)</span><span class="sxs-lookup"><span data-stu-id="27488-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<add>**](add-of-declaredtypes-element.md)</span></span>\
<span data-ttu-id="27488-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<knownType >** ](knowntype.md)</span><span class="sxs-lookup"><span data-stu-id="27488-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<knownType>**](knowntype.md)</span></span>\
<span data-ttu-id="27488-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<参数 >**</span><span class="sxs-lookup"><span data-stu-id="27488-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<parameter>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="27488-110">语法</span><span class="sxs-lookup"><span data-stu-id="27488-110">Syntax</span></span>  
  
```xml  
<parameter index="Integer"
           type="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="27488-111">特性和元素</span><span class="sxs-lookup"><span data-stu-id="27488-111">Attributes and Elements</span></span>  
 <span data-ttu-id="27488-112">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="27488-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="27488-113">特性</span><span class="sxs-lookup"><span data-stu-id="27488-113">Attributes</span></span>  
  
|<span data-ttu-id="27488-114">特性</span><span class="sxs-lookup"><span data-stu-id="27488-114">Attribute</span></span>|<span data-ttu-id="27488-115">描述</span><span class="sxs-lookup"><span data-stu-id="27488-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="27488-116">索引</span><span class="sxs-lookup"><span data-stu-id="27488-116">index</span></span>|<span data-ttu-id="27488-117">当声明类型是泛型类型时，指定将返回已知类型的泛型参数。</span><span class="sxs-lookup"><span data-stu-id="27488-117">When the declared type is a generic type, specifies the generic parameter that will return the known type.</span></span>|  
|<span data-ttu-id="27488-118">type</span><span class="sxs-lookup"><span data-stu-id="27488-118">type</span></span>|<span data-ttu-id="27488-119">一个字符串，描述用于序列化和反序列化的已知类型。</span><span class="sxs-lookup"><span data-stu-id="27488-119">A string that describes the known type used for serialization and deserialization.</span></span>|  
  
## <a name="index-attribute"></a><span data-ttu-id="27488-120">index 特性</span><span class="sxs-lookup"><span data-stu-id="27488-120">index Attribute</span></span>  
  
|<span data-ttu-id="27488-121">值</span><span class="sxs-lookup"><span data-stu-id="27488-121">Value</span></span>|<span data-ttu-id="27488-122">描述</span><span class="sxs-lookup"><span data-stu-id="27488-122">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="27488-123">“0”</span><span class="sxs-lookup"><span data-stu-id="27488-123">"0"</span></span>|<span data-ttu-id="27488-124">泛型类型中的第一个参数。</span><span class="sxs-lookup"><span data-stu-id="27488-124">The first parameter in the generic type.</span></span> <span data-ttu-id="27488-125">例如，一个 <xref:System.Collections.Generic.List%601> 仅有一个参数。</span><span class="sxs-lookup"><span data-stu-id="27488-125">For example, a <xref:System.Collections.Generic.List%601> has only one parameter.</span></span> <span data-ttu-id="27488-126">如果此参数用作声明类型，则将 index 特性设置为“0”。</span><span class="sxs-lookup"><span data-stu-id="27488-126">If it is used as the declared type, the index would be set to "0".</span></span>|  
|<span data-ttu-id="27488-127">"1"</span><span class="sxs-lookup"><span data-stu-id="27488-127">"1"</span></span>|<span data-ttu-id="27488-128">泛型类型中的第二个参数。</span><span class="sxs-lookup"><span data-stu-id="27488-128">The second parameter in a generic type.</span></span> <span data-ttu-id="27488-129">例如，一个 <xref:System.Collections.Generic.Dictionary%602> 有两个参数。</span><span class="sxs-lookup"><span data-stu-id="27488-129">For example, a <xref:System.Collections.Generic.Dictionary%602> has two parameters.</span></span> <span data-ttu-id="27488-130">如果通过第二个参数返回已知类型，则将 index 特性设置为“1”。</span><span class="sxs-lookup"><span data-stu-id="27488-130">If the known type is returned by the second parameter, set the index attribute to "1".</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="27488-131">子元素</span><span class="sxs-lookup"><span data-stu-id="27488-131">Child Elements</span></span>  
 <span data-ttu-id="27488-132">无。</span><span class="sxs-lookup"><span data-stu-id="27488-132">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="27488-133">父元素</span><span class="sxs-lookup"><span data-stu-id="27488-133">Parent Elements</span></span>  
  
|<span data-ttu-id="27488-134">元素</span><span class="sxs-lookup"><span data-stu-id="27488-134">Element</span></span>|<span data-ttu-id="27488-135">描述</span><span class="sxs-lookup"><span data-stu-id="27488-135">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="27488-136">\<knownType></span><span class="sxs-lookup"><span data-stu-id="27488-136">\<knownType></span></span>](knowntype.md)|<span data-ttu-id="27488-137">指定一个可由声明类型的字段或属性返回的已知类型。</span><span class="sxs-lookup"><span data-stu-id="27488-137">Specifies a known type that can be returned by a field or property of the declared type.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="27488-138">备注</span><span class="sxs-lookup"><span data-stu-id="27488-138">Remarks</span></span>  
 <span data-ttu-id="27488-139">有关已知类型的详细信息，请参阅[数据协定已知类型](../../../wcf/feature-details/data-contract-known-types.md)和<xref:System.Runtime.Serialization.DataContractSerializer>。</span><span class="sxs-lookup"><span data-stu-id="27488-139">For more information about known types, see [Data Contract Known Types](../../../wcf/feature-details/data-contract-known-types.md) and <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  
  
 <span data-ttu-id="27488-140">有关使用此元素的示例，请参阅[ dataContractSerializer>。\<](datacontractserializer-element.md)</span><span class="sxs-lookup"><span data-stu-id="27488-140">See the [\<dataContractSerializer>](datacontractserializer-element.md) for an example of using this element.</span></span>  
  
 <span data-ttu-id="27488-141">此配置元素不能同时具有两个属性。</span><span class="sxs-lookup"><span data-stu-id="27488-141">This configuration element cannot have both attributes at the same time.</span></span> <span data-ttu-id="27488-142">如果设置两个属性，则发生 <xref:System.Configuration.ConfigurationErrorsException>。</span><span class="sxs-lookup"><span data-stu-id="27488-142">If both attributes are set, a <xref:System.Configuration.ConfigurationErrorsException> occurs.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="27488-143">请参阅</span><span class="sxs-lookup"><span data-stu-id="27488-143">See also</span></span>

- <xref:System.Runtime.Serialization.DataContractSerializer>
- [<span data-ttu-id="27488-144">数据协定已知类型</span><span class="sxs-lookup"><span data-stu-id="27488-144">Data Contract Known Types</span></span>](../../../wcf/feature-details/data-contract-known-types.md)
- [<span data-ttu-id="27488-145">\<dataContractSerializer></span><span class="sxs-lookup"><span data-stu-id="27488-145">\<dataContractSerializer></span></span>](datacontractserializer-element.md)
- [<span data-ttu-id="27488-146">\<add></span><span class="sxs-lookup"><span data-stu-id="27488-146">\<add></span></span>](add-of-declaredtypes-element.md)
