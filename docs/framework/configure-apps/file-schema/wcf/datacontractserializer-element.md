---
title: '&lt;DataContractSerializer&gt;'
ms.date: 03/30/2017
helpviewer_keywords:
- dataContractSerializer element
- <dataContractSerializer> element
- DataContractSerializer
- KnownTypes
ms.assetid: f41fb4d5-24e7-4059-8010-286a30bfea93
ms.openlocfilehash: c79c8e8db2a4ea4526000bcbe336d1e664f9c4c2
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/09/2019
ms.locfileid: "54150950"
---
# <a name="ltdatacontractserializergt"></a><span data-ttu-id="34905-102">&lt;DataContractSerializer&gt;</span><span class="sxs-lookup"><span data-stu-id="34905-102">&lt;dataContractSerializer&gt;</span></span>
<span data-ttu-id="34905-103">包含 <xref:System.Runtime.Serialization.DataContractSerializer> 的配置数据。</span><span class="sxs-lookup"><span data-stu-id="34905-103">Contains configuration data for the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span> <span data-ttu-id="34905-104">此元素出现在两个不同的层次结构中。</span><span class="sxs-lookup"><span data-stu-id="34905-104">This element occurs in two different hierarchies.</span></span> <span data-ttu-id="34905-105">这两个层次结构分别在下面的“架构层次结构”一节和“备注”一节中列出。</span><span class="sxs-lookup"><span data-stu-id="34905-105">One is listed the following Schema Hierarchy section and the other is listed in the Remarks section.</span></span>  
  
 <span data-ttu-id="34905-106">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="34905-106">\<system.ServiceModel></span></span>  
<span data-ttu-id="34905-107">\<行为 ></span><span class="sxs-lookup"><span data-stu-id="34905-107">\<behaviors></span></span>  
<span data-ttu-id="34905-108">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="34905-108">\<serviceBehaviors></span></span>  
<span data-ttu-id="34905-109">\<行为 ></span><span class="sxs-lookup"><span data-stu-id="34905-109">\<behavior></span></span>  
<span data-ttu-id="34905-110">\<dataContractSerializer ></span><span class="sxs-lookup"><span data-stu-id="34905-110">\<dataContractSerializer></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="34905-111">语法</span><span class="sxs-lookup"><span data-stu-id="34905-111">Syntax</span></span>  
  
```xml  
<dataContractSerializer ignoreExtensionDataObject="Boolean"
                        maxItemsInObjectGraph="Integer" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="34905-112">特性和元素</span><span class="sxs-lookup"><span data-stu-id="34905-112">Attributes and Elements</span></span>  
 <span data-ttu-id="34905-113">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="34905-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="34905-114">特性</span><span class="sxs-lookup"><span data-stu-id="34905-114">Attributes</span></span>  
  
|<span data-ttu-id="34905-115">元素</span><span class="sxs-lookup"><span data-stu-id="34905-115">Element</span></span>|<span data-ttu-id="34905-116">描述</span><span class="sxs-lookup"><span data-stu-id="34905-116">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="34905-117">ignoreExtensionDataObject</span><span class="sxs-lookup"><span data-stu-id="34905-117">ignoreExtensionDataObject</span></span>|<span data-ttu-id="34905-118">一个布尔值，指定在对终结点进行序列化或反序列化时，是否要忽略由该终结点提供的数据。</span><span class="sxs-lookup"><span data-stu-id="34905-118">A Boolean value that specifies whether to ignore data supplied by the endpoint when it is being serialized or deserialized.</span></span> <span data-ttu-id="34905-119">只可对 `<dataContractSerializer>` 元素下的 `<behavior>` 设置此属性。</span><span class="sxs-lookup"><span data-stu-id="34905-119">This attribute is settable only on the `<dataContractSerializer>` under the `<behavior>` element.</span></span>|  
|<span data-ttu-id="34905-120">maxItemsInObjectGraph</span><span class="sxs-lookup"><span data-stu-id="34905-120">maxItemsInObjectGraph</span></span>|<span data-ttu-id="34905-121">一个整数，指定要序列化或反序列化的最大项数。</span><span class="sxs-lookup"><span data-stu-id="34905-121">An integer that specifies the maximum number of items to serialize or deserialize.</span></span> <span data-ttu-id="34905-122">此属性为 65536。</span><span class="sxs-lookup"><span data-stu-id="34905-122">This attribute is 65536.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="34905-123">子元素</span><span class="sxs-lookup"><span data-stu-id="34905-123">Child Elements</span></span>  
 <span data-ttu-id="34905-124">无。</span><span class="sxs-lookup"><span data-stu-id="34905-124">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="34905-125">父元素</span><span class="sxs-lookup"><span data-stu-id="34905-125">Parent Elements</span></span>  
  
|<span data-ttu-id="34905-126">元素</span><span class="sxs-lookup"><span data-stu-id="34905-126">Element</span></span>|<span data-ttu-id="34905-127">描述</span><span class="sxs-lookup"><span data-stu-id="34905-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="34905-128">\<行为 ></span><span class="sxs-lookup"><span data-stu-id="34905-128">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-servicebehaviors.md)|<span data-ttu-id="34905-129">服务行为的设置集合。</span><span class="sxs-lookup"><span data-stu-id="34905-129">A collection of settings for the behavior of a service.</span></span>|  
|[<span data-ttu-id="34905-130">\<system.runtime.serialization></span><span class="sxs-lookup"><span data-stu-id="34905-130">\<system.runtime.serialization></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/system-runtime-serialization.md)|<span data-ttu-id="34905-131">表示 <xref:System.Runtime.Serialization> 命名空间节的根元素，并包含 <xref:System.Runtime.Serialization.DataContractSerializer> 的设置选项的元素。</span><span class="sxs-lookup"><span data-stu-id="34905-131">Represents the root element for the <xref:System.Runtime.Serialization> namespace section and contains elements for setting options of the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="34905-132">备注</span><span class="sxs-lookup"><span data-stu-id="34905-132">Remarks</span></span>  
 <span data-ttu-id="34905-133">如本主题的简介中所述，这是在其中的第二个层次结构\<X509Extension > 元素出现。</span><span class="sxs-lookup"><span data-stu-id="34905-133">As stated in the Introduction of this topic, this is the second hierarchy in which the \<X509Extension> element occurs.</span></span>  
  
 [<span data-ttu-id="34905-134">\<system.runtime.serialization></span><span class="sxs-lookup"><span data-stu-id="34905-134">\<system.runtime.serialization></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/system-runtime-serialization.md)  
  
 [<span data-ttu-id="34905-135">\<dataContractSerializer ></span><span class="sxs-lookup"><span data-stu-id="34905-135">\<dataContractSerializer></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-element.md)  
  
 <span data-ttu-id="34905-136">有关已知类型的更多信息，请参见 <xref:System.Runtime.Serialization.DataContractSerializer>。</span><span class="sxs-lookup"><span data-stu-id="34905-136">For more information about known types, see <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="34905-137">请参阅</span><span class="sxs-lookup"><span data-stu-id="34905-137">See Also</span></span>  
 <xref:System.Runtime.Serialization.DataContractSerializer>  
 <xref:System.ServiceModel.Description.DataContractSerializerOperationBehavior>  
 <xref:System.ServiceModel.Configuration.DataContractSerializerElement>  
 [<span data-ttu-id="34905-138">数据协定已知类型</span><span class="sxs-lookup"><span data-stu-id="34905-138">Data Contract Known Types</span></span>](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md)  
 [<span data-ttu-id="34905-139">数据传输和序列化</span><span class="sxs-lookup"><span data-stu-id="34905-139">Data Transfer and Serialization</span></span>](../../../../../docs/framework/wcf/feature-details/data-transfer-and-serialization.md)
