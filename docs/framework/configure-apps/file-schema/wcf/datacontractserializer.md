---
title: dataContractSerializer
ms.date: 03/30/2017
ms.assetid: a47513a4-a96c-4350-8586-daacb05dee71
ms.openlocfilehash: e6524c18780c062c3b5b7dfc2509449cb208e270
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/06/2019
ms.locfileid: "70400436"
---
# <a name="datacontractserializer"></a><span data-ttu-id="59dd4-102">dataContractSerializer</span><span class="sxs-lookup"><span data-stu-id="59dd4-102">dataContractSerializer</span></span>
<span data-ttu-id="59dd4-103">包含 <xref:System.Runtime.Serialization.DataContractSerializer> 的配置数据。</span><span class="sxs-lookup"><span data-stu-id="59dd4-103">Contains configuration data for the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  
  
<span data-ttu-id="59dd4-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="59dd4-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="59dd4-105">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="59dd4-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="59dd4-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<行为 >** ](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="59dd4-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="59dd4-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<endpointBehaviors >** ](endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="59dd4-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)</span></span>\
<span data-ttu-id="59dd4-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<行为 >** ](behavior-of-endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="59dd4-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)</span></span>\
<span data-ttu-id="59dd4-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<dataContractSerializer >**</span><span class="sxs-lookup"><span data-stu-id="59dd4-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<dataContractSerializer>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="59dd4-110">语法</span><span class="sxs-lookup"><span data-stu-id="59dd4-110">Syntax</span></span>  
  
```xml  
<dataContractSerializer ignoreExtensionDataObject="Boolean"
                        maxItemsInObjectGraph="Integer" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="59dd4-111">特性和元素</span><span class="sxs-lookup"><span data-stu-id="59dd4-111">Attributes and Elements</span></span>  
 <span data-ttu-id="59dd4-112">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="59dd4-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="59dd4-113">特性</span><span class="sxs-lookup"><span data-stu-id="59dd4-113">Attributes</span></span>  
  
|<span data-ttu-id="59dd4-114">元素</span><span class="sxs-lookup"><span data-stu-id="59dd4-114">Element</span></span>|<span data-ttu-id="59dd4-115">描述</span><span class="sxs-lookup"><span data-stu-id="59dd4-115">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="59dd4-116">ignoreExtensionDataObject</span><span class="sxs-lookup"><span data-stu-id="59dd4-116">ignoreExtensionDataObject</span></span>|<span data-ttu-id="59dd4-117">一个布尔值，指定在对终结点进行序列化或反序列化时，是否要忽略由该终结点提供的数据。</span><span class="sxs-lookup"><span data-stu-id="59dd4-117">A Boolean value that specifies whether to ignore data supplied by the endpoint, when it is being serialized or deserialized.</span></span>|  
|<span data-ttu-id="59dd4-118">maxItemsInObjectGraph</span><span class="sxs-lookup"><span data-stu-id="59dd4-118">maxItemsInObjectGraph</span></span>|<span data-ttu-id="59dd4-119">一个整数，指定要序列化或反序列化的最大项数。</span><span class="sxs-lookup"><span data-stu-id="59dd4-119">An integer that specifies the maximum number of items to serialize or deserialize.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="59dd4-120">子元素</span><span class="sxs-lookup"><span data-stu-id="59dd4-120">Child Elements</span></span>  
 <span data-ttu-id="59dd4-121">无。</span><span class="sxs-lookup"><span data-stu-id="59dd4-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="59dd4-122">父元素</span><span class="sxs-lookup"><span data-stu-id="59dd4-122">Parent Elements</span></span>  
  
|<span data-ttu-id="59dd4-123">元素</span><span class="sxs-lookup"><span data-stu-id="59dd4-123">Element</span></span>|<span data-ttu-id="59dd4-124">描述</span><span class="sxs-lookup"><span data-stu-id="59dd4-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="59dd4-125">\<behavior></span><span class="sxs-lookup"><span data-stu-id="59dd4-125">\<behavior></span></span>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="59dd4-126">指定终结点行为。</span><span class="sxs-lookup"><span data-stu-id="59dd4-126">Specifies an endpoint behavior.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="59dd4-127">备注</span><span class="sxs-lookup"><span data-stu-id="59dd4-127">Remarks</span></span>  
 <span data-ttu-id="59dd4-128">有关已知类型的更多信息，请参见 <xref:System.Runtime.Serialization.DataContractSerializer> 文档。</span><span class="sxs-lookup"><span data-stu-id="59dd4-128">See the <xref:System.Runtime.Serialization.DataContractSerializer> documentation for more information about known types.</span></span>  
  
> [!CAUTION]
> <span data-ttu-id="59dd4-129">在配置文件中，`<dataContractSerializer>` 行为元素（如果有）应始终在 `<enableWebScript>` 行为元素之前出现。</span><span class="sxs-lookup"><span data-stu-id="59dd4-129">The `<dataContractSerializer>` behavior element (if present) should always appear before the `<enableWebScript>` behavior element in the configuration file.</span></span> <span data-ttu-id="59dd4-130">否则，产生的行为将是不确定的。</span><span class="sxs-lookup"><span data-stu-id="59dd4-130">Otherwise, the resulting behavior is undefined.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="59dd4-131">请参阅</span><span class="sxs-lookup"><span data-stu-id="59dd4-131">See also</span></span>

- <xref:System.Runtime.Serialization.DataContractSerializer>
- <xref:System.ServiceModel.Description.DataContractSerializerOperationBehavior>
- <xref:System.ServiceModel.Configuration.DataContractSerializerElement>
- [<span data-ttu-id="59dd4-132">数据协定已知类型</span><span class="sxs-lookup"><span data-stu-id="59dd4-132">Data Contract Known Types</span></span>](../../../wcf/feature-details/data-contract-known-types.md)
- [<span data-ttu-id="59dd4-133">数据传输和序列化</span><span class="sxs-lookup"><span data-stu-id="59dd4-133">Data Transfer and Serialization</span></span>](../../../wcf/feature-details/data-transfer-and-serialization.md)
