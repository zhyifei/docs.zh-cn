---
title: dataContractSerializer
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a47513a4-a96c-4350-8586-daacb05dee71
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: a64f5ae4573efbd8c0f7d622e6b94b7786585bb1
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2017
---
# <a name="datacontractserializer"></a><span data-ttu-id="86b3f-102">dataContractSerializer</span><span class="sxs-lookup"><span data-stu-id="86b3f-102">dataContractSerializer</span></span>
<span data-ttu-id="86b3f-103">包含 <xref:System.Runtime.Serialization.DataContractSerializer> 的配置数据。</span><span class="sxs-lookup"><span data-stu-id="86b3f-103">Contains configuration data for the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  
  
 <span data-ttu-id="86b3f-104">\<系统。ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="86b3f-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="86b3f-105">\<行为 ></span><span class="sxs-lookup"><span data-stu-id="86b3f-105">\<behaviors></span></span>  
<span data-ttu-id="86b3f-106">\<endpointBehaviors ></span><span class="sxs-lookup"><span data-stu-id="86b3f-106">\<endpointBehaviors></span></span>  
<span data-ttu-id="86b3f-107">\<行为 ></span><span class="sxs-lookup"><span data-stu-id="86b3f-107">\<behavior></span></span>  
<span data-ttu-id="86b3f-108">\<dataContractSerializer ></span><span class="sxs-lookup"><span data-stu-id="86b3f-108">\<dataContractSerializer></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="86b3f-109">语法</span><span class="sxs-lookup"><span data-stu-id="86b3f-109">Syntax</span></span>  
  
```xml  
<dataContractSerializer ignoreExtensionDataObject="Boolean"  
      maxItemsInObjectGraph="Integer" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="86b3f-110">特性和元素</span><span class="sxs-lookup"><span data-stu-id="86b3f-110">Attributes and Elements</span></span>  
 <span data-ttu-id="86b3f-111">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="86b3f-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="86b3f-112">特性</span><span class="sxs-lookup"><span data-stu-id="86b3f-112">Attributes</span></span>  
  
|<span data-ttu-id="86b3f-113">元素</span><span class="sxs-lookup"><span data-stu-id="86b3f-113">Element</span></span>|<span data-ttu-id="86b3f-114">描述</span><span class="sxs-lookup"><span data-stu-id="86b3f-114">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="86b3f-115">ignoreExtensionDataObject</span><span class="sxs-lookup"><span data-stu-id="86b3f-115">ignoreExtensionDataObject</span></span>|<span data-ttu-id="86b3f-116">一个布尔值，指定在对终结点进行序列化或反序列化时，是否要忽略由该终结点提供的数据。</span><span class="sxs-lookup"><span data-stu-id="86b3f-116">A Boolean value that specifies whether to ignore data supplied by the endpoint, when it is being serialized or deserialized.</span></span>|  
|<span data-ttu-id="86b3f-117">maxItemsInObjectGraph</span><span class="sxs-lookup"><span data-stu-id="86b3f-117">maxItemsInObjectGraph</span></span>|<span data-ttu-id="86b3f-118">一个整数，指定要序列化或反序列化的最大项数。</span><span class="sxs-lookup"><span data-stu-id="86b3f-118">An integer that specifies the maximum number of items to serialize or deserialize.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="86b3f-119">子元素</span><span class="sxs-lookup"><span data-stu-id="86b3f-119">Child Elements</span></span>  
 <span data-ttu-id="86b3f-120">无。</span><span class="sxs-lookup"><span data-stu-id="86b3f-120">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="86b3f-121">父元素</span><span class="sxs-lookup"><span data-stu-id="86b3f-121">Parent Elements</span></span>  
  
|<span data-ttu-id="86b3f-122">元素</span><span class="sxs-lookup"><span data-stu-id="86b3f-122">Element</span></span>|<span data-ttu-id="86b3f-123">描述</span><span class="sxs-lookup"><span data-stu-id="86b3f-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="86b3f-124">\<行为 ></span><span class="sxs-lookup"><span data-stu-id="86b3f-124">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="86b3f-125">指定终结点行为。</span><span class="sxs-lookup"><span data-stu-id="86b3f-125">Specifies an endpoint behavior.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="86b3f-126">备注</span><span class="sxs-lookup"><span data-stu-id="86b3f-126">Remarks</span></span>  
 <span data-ttu-id="86b3f-127">有关已知类型的更多信息，请参见 <xref:System.Runtime.Serialization.DataContractSerializer> 文档。</span><span class="sxs-lookup"><span data-stu-id="86b3f-127">See the <xref:System.Runtime.Serialization.DataContractSerializer> documentation for more information about known types.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="86b3f-128">在配置文件中，`<dataContractSerializer>` 行为元素（如果有）应始终在 `<enableWebScript>` 行为元素之前出现。</span><span class="sxs-lookup"><span data-stu-id="86b3f-128">The `<dataContractSerializer>` behavior element (if present) should always appear before the `<enableWebScript>` behavior element in the configuration file.</span></span> <span data-ttu-id="86b3f-129">否则，产生的行为将是不确定的。</span><span class="sxs-lookup"><span data-stu-id="86b3f-129">Otherwise, the resulting behavior is undefined.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="86b3f-130">另请参阅</span><span class="sxs-lookup"><span data-stu-id="86b3f-130">See Also</span></span>  
 <xref:System.Runtime.Serialization.DataContractSerializer>  
 <xref:System.ServiceModel.Description.DataContractSerializerOperationBehavior>  
 <xref:System.ServiceModel.Configuration.DataContractSerializerElement>  
 [<span data-ttu-id="86b3f-131">数据协定已知的类型</span><span class="sxs-lookup"><span data-stu-id="86b3f-131">Data Contract Known Types</span></span>](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md)  
 [<span data-ttu-id="86b3f-132">数据传输和序列化</span><span class="sxs-lookup"><span data-stu-id="86b3f-132">Data Transfer and Serialization</span></span>](../../../../../docs/framework/wcf/feature-details/data-transfer-and-serialization.md)
