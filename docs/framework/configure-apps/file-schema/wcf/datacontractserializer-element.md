---
title: '&lt;dataContractSerializer&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- dataContractSerializer element
- <dataContractSerializer> element
- DataContractSerializer
- KnownTypes
ms.assetid: f41fb4d5-24e7-4059-8010-286a30bfea93
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 27b80c831fdc66bd3b022645c3de9c0c31ee575a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="ltdatacontractserializergt"></a><span data-ttu-id="981e5-102">&lt;dataContractSerializer&gt;</span><span class="sxs-lookup"><span data-stu-id="981e5-102">&lt;dataContractSerializer&gt;</span></span>
<span data-ttu-id="981e5-103">包含 <xref:System.Runtime.Serialization.DataContractSerializer> 的配置数据。</span><span class="sxs-lookup"><span data-stu-id="981e5-103">Contains configuration data for the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span> <span data-ttu-id="981e5-104">此元素出现在两个不同的层次结构中。</span><span class="sxs-lookup"><span data-stu-id="981e5-104">This element occurs in two different hierarchies.</span></span> <span data-ttu-id="981e5-105">这两个层次结构分别在下面的“架构层次结构”一节和“备注”一节中列出。</span><span class="sxs-lookup"><span data-stu-id="981e5-105">One is listed the following Schema Hierarchy section and the other is listed in the Remarks section.</span></span>  
  
 <span data-ttu-id="981e5-106">\<系统。ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="981e5-106">\<system.ServiceModel></span></span>  
<span data-ttu-id="981e5-107">\<行为 ></span><span class="sxs-lookup"><span data-stu-id="981e5-107">\<behaviors></span></span>  
<span data-ttu-id="981e5-108">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="981e5-108">\<serviceBehaviors></span></span>  
<span data-ttu-id="981e5-109">\<行为 ></span><span class="sxs-lookup"><span data-stu-id="981e5-109">\<behavior></span></span>  
<span data-ttu-id="981e5-110">\<dataContractSerializer ></span><span class="sxs-lookup"><span data-stu-id="981e5-110">\<dataContractSerializer></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="981e5-111">语法</span><span class="sxs-lookup"><span data-stu-id="981e5-111">Syntax</span></span>  
  
```xml  
<dataContractSerializer ignoreExtensionDataObject="Boolean"  
   maxItemsInObjectGraph="Integer" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="981e5-112">特性和元素</span><span class="sxs-lookup"><span data-stu-id="981e5-112">Attributes and Elements</span></span>  
 <span data-ttu-id="981e5-113">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="981e5-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="981e5-114">特性</span><span class="sxs-lookup"><span data-stu-id="981e5-114">Attributes</span></span>  
  
|<span data-ttu-id="981e5-115">元素</span><span class="sxs-lookup"><span data-stu-id="981e5-115">Element</span></span>|<span data-ttu-id="981e5-116">描述</span><span class="sxs-lookup"><span data-stu-id="981e5-116">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="981e5-117">ignoreExtensionDataObject</span><span class="sxs-lookup"><span data-stu-id="981e5-117">ignoreExtensionDataObject</span></span>|<span data-ttu-id="981e5-118">一个布尔值，指定在对终结点进行序列化或反序列化时，是否要忽略由该终结点提供的数据。</span><span class="sxs-lookup"><span data-stu-id="981e5-118">A Boolean value that specifies whether to ignore data supplied by the endpoint when it is being serialized or deserialized.</span></span> <span data-ttu-id="981e5-119">只可对 `<dataContractSerializer>` 元素下的 `<behavior>` 设置此属性。</span><span class="sxs-lookup"><span data-stu-id="981e5-119">This attribute is settable only on the `<dataContractSerializer>` under the `<behavior>` element.</span></span>|  
|<span data-ttu-id="981e5-120">maxItemsInObjectGraph</span><span class="sxs-lookup"><span data-stu-id="981e5-120">maxItemsInObjectGraph</span></span>|<span data-ttu-id="981e5-121">一个整数，指定要序列化或反序列化的最大项数。</span><span class="sxs-lookup"><span data-stu-id="981e5-121">An integer that specifies the maximum number of items to serialize or deserialize.</span></span> <span data-ttu-id="981e5-122">此属性为 65536。</span><span class="sxs-lookup"><span data-stu-id="981e5-122">This attribute is 65536.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="981e5-123">子元素</span><span class="sxs-lookup"><span data-stu-id="981e5-123">Child Elements</span></span>  
 <span data-ttu-id="981e5-124">无。</span><span class="sxs-lookup"><span data-stu-id="981e5-124">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="981e5-125">父元素</span><span class="sxs-lookup"><span data-stu-id="981e5-125">Parent Elements</span></span>  
  
|<span data-ttu-id="981e5-126">元素</span><span class="sxs-lookup"><span data-stu-id="981e5-126">Element</span></span>|<span data-ttu-id="981e5-127">描述</span><span class="sxs-lookup"><span data-stu-id="981e5-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="981e5-128">\<行为 ></span><span class="sxs-lookup"><span data-stu-id="981e5-128">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-servicebehaviors.md)|<span data-ttu-id="981e5-129">服务行为的设置集合。</span><span class="sxs-lookup"><span data-stu-id="981e5-129">A collection of settings for the behavior of a service.</span></span>|  
|[<span data-ttu-id="981e5-130">\<system.runtime.serialization></span><span class="sxs-lookup"><span data-stu-id="981e5-130">\<system.runtime.serialization></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/system-runtime-serialization.md)|<span data-ttu-id="981e5-131">表示 <xref:System.Runtime.Serialization> 命名空间节的根元素，并包含 <xref:System.Runtime.Serialization.DataContractSerializer> 的设置选项的元素。</span><span class="sxs-lookup"><span data-stu-id="981e5-131">Represents the root element for the <xref:System.Runtime.Serialization> namespace section and contains elements for setting options of the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="981e5-132">备注</span><span class="sxs-lookup"><span data-stu-id="981e5-132">Remarks</span></span>  
 <span data-ttu-id="981e5-133">如本主题的简介中所述，这是在其中的第二个层次结构\<X509Extension > 元素出现。</span><span class="sxs-lookup"><span data-stu-id="981e5-133">As stated in the Introduction of this topic, this is the second hierarchy in which the \<X509Extension> element occurs.</span></span>  
  
 [<span data-ttu-id="981e5-134">\<system.runtime.serialization></span><span class="sxs-lookup"><span data-stu-id="981e5-134">\<system.runtime.serialization></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/system-runtime-serialization.md)  
  
 [<span data-ttu-id="981e5-135">\<dataContractSerializer ></span><span class="sxs-lookup"><span data-stu-id="981e5-135">\<dataContractSerializer></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-element.md)  
  
 <span data-ttu-id="981e5-136">有关已知类型的更多信息，请参见 <xref:System.Runtime.Serialization.DataContractSerializer>。</span><span class="sxs-lookup"><span data-stu-id="981e5-136">For more information about known types, see <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="981e5-137">请参阅</span><span class="sxs-lookup"><span data-stu-id="981e5-137">See Also</span></span>  
 <xref:System.Runtime.Serialization.DataContractSerializer>  
 <xref:System.ServiceModel.Description.DataContractSerializerOperationBehavior>  
 <xref:System.ServiceModel.Configuration.DataContractSerializerElement>  
 [<span data-ttu-id="981e5-138">数据协定已知类型</span><span class="sxs-lookup"><span data-stu-id="981e5-138">Data Contract Known Types</span></span>](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md)  
 [<span data-ttu-id="981e5-139">数据传输和序列化</span><span class="sxs-lookup"><span data-stu-id="981e5-139">Data Transfer and Serialization</span></span>](../../../../../docs/framework/wcf/feature-details/data-transfer-and-serialization.md)
