---
title: <dataContractSerializer>
ms.date: 03/30/2017
helpviewer_keywords:
- dataContractSerializer element
- <dataContractSerializer> element
- DataContractSerializer
- KnownTypes
ms.assetid: f41fb4d5-24e7-4059-8010-286a30bfea93
ms.openlocfilehash: b635f03d1e4a6628a76d678f7366482717276376
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61704136"
---
# <a name="datacontractserializer"></a><span data-ttu-id="4138f-101">\<dataContractSerializer></span><span class="sxs-lookup"><span data-stu-id="4138f-101">\<dataContractSerializer></span></span>
<span data-ttu-id="4138f-102">包含 <xref:System.Runtime.Serialization.DataContractSerializer> 的配置数据。</span><span class="sxs-lookup"><span data-stu-id="4138f-102">Contains configuration data for the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span> <span data-ttu-id="4138f-103">此元素出现在两个不同的层次结构中。</span><span class="sxs-lookup"><span data-stu-id="4138f-103">This element occurs in two different hierarchies.</span></span> <span data-ttu-id="4138f-104">这两个层次结构分别在下面的“架构层次结构”一节和“备注”一节中列出。</span><span class="sxs-lookup"><span data-stu-id="4138f-104">One is listed the following Schema Hierarchy section and the other is listed in the Remarks section.</span></span>  
  
 <span data-ttu-id="4138f-105">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="4138f-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="4138f-106">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="4138f-106">\<behaviors></span></span>  
<span data-ttu-id="4138f-107">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="4138f-107">\<serviceBehaviors></span></span>  
<span data-ttu-id="4138f-108">\<behavior></span><span class="sxs-lookup"><span data-stu-id="4138f-108">\<behavior></span></span>  
<span data-ttu-id="4138f-109">\<dataContractSerializer></span><span class="sxs-lookup"><span data-stu-id="4138f-109">\<dataContractSerializer></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4138f-110">语法</span><span class="sxs-lookup"><span data-stu-id="4138f-110">Syntax</span></span>  
  
```xml  
<dataContractSerializer ignoreExtensionDataObject="Boolean"
                        maxItemsInObjectGraph="Integer" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4138f-111">特性和元素</span><span class="sxs-lookup"><span data-stu-id="4138f-111">Attributes and Elements</span></span>  
 <span data-ttu-id="4138f-112">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="4138f-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4138f-113">特性</span><span class="sxs-lookup"><span data-stu-id="4138f-113">Attributes</span></span>  
  
|<span data-ttu-id="4138f-114">元素</span><span class="sxs-lookup"><span data-stu-id="4138f-114">Element</span></span>|<span data-ttu-id="4138f-115">描述</span><span class="sxs-lookup"><span data-stu-id="4138f-115">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="4138f-116">ignoreExtensionDataObject</span><span class="sxs-lookup"><span data-stu-id="4138f-116">ignoreExtensionDataObject</span></span>|<span data-ttu-id="4138f-117">一个布尔值，指定在对终结点进行序列化或反序列化时，是否要忽略由该终结点提供的数据。</span><span class="sxs-lookup"><span data-stu-id="4138f-117">A Boolean value that specifies whether to ignore data supplied by the endpoint when it is being serialized or deserialized.</span></span> <span data-ttu-id="4138f-118">只可对 `<dataContractSerializer>` 元素下的 `<behavior>` 设置此属性。</span><span class="sxs-lookup"><span data-stu-id="4138f-118">This attribute is settable only on the `<dataContractSerializer>` under the `<behavior>` element.</span></span>|  
|<span data-ttu-id="4138f-119">maxItemsInObjectGraph</span><span class="sxs-lookup"><span data-stu-id="4138f-119">maxItemsInObjectGraph</span></span>|<span data-ttu-id="4138f-120">一个整数，指定要序列化或反序列化的最大项数。</span><span class="sxs-lookup"><span data-stu-id="4138f-120">An integer that specifies the maximum number of items to serialize or deserialize.</span></span> <span data-ttu-id="4138f-121">此属性为 65536。</span><span class="sxs-lookup"><span data-stu-id="4138f-121">This attribute is 65536.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="4138f-122">子元素</span><span class="sxs-lookup"><span data-stu-id="4138f-122">Child Elements</span></span>  
 <span data-ttu-id="4138f-123">无。</span><span class="sxs-lookup"><span data-stu-id="4138f-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="4138f-124">父元素</span><span class="sxs-lookup"><span data-stu-id="4138f-124">Parent Elements</span></span>  
  
|<span data-ttu-id="4138f-125">元素</span><span class="sxs-lookup"><span data-stu-id="4138f-125">Element</span></span>|<span data-ttu-id="4138f-126">描述</span><span class="sxs-lookup"><span data-stu-id="4138f-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4138f-127">\<behavior></span><span class="sxs-lookup"><span data-stu-id="4138f-127">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-servicebehaviors.md)|<span data-ttu-id="4138f-128">服务行为的设置集合。</span><span class="sxs-lookup"><span data-stu-id="4138f-128">A collection of settings for the behavior of a service.</span></span>|  
|[<span data-ttu-id="4138f-129">\<system.runtime.serialization></span><span class="sxs-lookup"><span data-stu-id="4138f-129">\<system.runtime.serialization></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/system-runtime-serialization.md)|<span data-ttu-id="4138f-130">表示 <xref:System.Runtime.Serialization> 命名空间节的根元素，并包含 <xref:System.Runtime.Serialization.DataContractSerializer> 的设置选项的元素。</span><span class="sxs-lookup"><span data-stu-id="4138f-130">Represents the root element for the <xref:System.Runtime.Serialization> namespace section and contains elements for setting options of the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4138f-131">备注</span><span class="sxs-lookup"><span data-stu-id="4138f-131">Remarks</span></span>  
 <span data-ttu-id="4138f-132">如本主题的简介中所述，这是在其中的第二个层次结构\<X509Extension > 元素出现。</span><span class="sxs-lookup"><span data-stu-id="4138f-132">As stated in the Introduction of this topic, this is the second hierarchy in which the \<X509Extension> element occurs.</span></span>  
  
 [<span data-ttu-id="4138f-133">\<system.runtime.serialization></span><span class="sxs-lookup"><span data-stu-id="4138f-133">\<system.runtime.serialization></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/system-runtime-serialization.md)  
  
 [<span data-ttu-id="4138f-134">\<dataContractSerializer></span><span class="sxs-lookup"><span data-stu-id="4138f-134">\<dataContractSerializer></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-element.md)  
  
 <span data-ttu-id="4138f-135">有关已知类型的更多信息，请参见 <xref:System.Runtime.Serialization.DataContractSerializer>。</span><span class="sxs-lookup"><span data-stu-id="4138f-135">For more information about known types, see <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4138f-136">请参阅</span><span class="sxs-lookup"><span data-stu-id="4138f-136">See also</span></span>

- <xref:System.Runtime.Serialization.DataContractSerializer>
- <xref:System.ServiceModel.Description.DataContractSerializerOperationBehavior>
- <xref:System.ServiceModel.Configuration.DataContractSerializerElement>
- [<span data-ttu-id="4138f-137">数据协定已知类型</span><span class="sxs-lookup"><span data-stu-id="4138f-137">Data Contract Known Types</span></span>](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md)
- [<span data-ttu-id="4138f-138">数据传输和序列化</span><span class="sxs-lookup"><span data-stu-id="4138f-138">Data Transfer and Serialization</span></span>](../../../../../docs/framework/wcf/feature-details/data-transfer-and-serialization.md)
