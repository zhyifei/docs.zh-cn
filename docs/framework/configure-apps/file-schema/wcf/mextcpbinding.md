---
title: '&lt;mexTcpBinding&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 01baba8d-d784-4255-9ea2-7afff1482bf0
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: ef9df72d06c598cc641d884dadbf9d4f5cee9f5b
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2017
---
# <a name="ltmextcpbindinggt"></a><span data-ttu-id="a2bc8-102">&lt;mexTcpBinding&gt;</span><span class="sxs-lookup"><span data-stu-id="a2bc8-102">&lt;mexTcpBinding&gt;</span></span>
<span data-ttu-id="a2bc8-103">指定用于通过 TCP 进行的 WS-MetadataExchange (WS-MEX) 消息交换的绑定的设置。</span><span class="sxs-lookup"><span data-stu-id="a2bc8-103">Specifies the settings for a binding used for the WS-MetadataExchange (WS-MEX) message exchange over TCP.</span></span>  
  
 <span data-ttu-id="a2bc8-104">\<系统。ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="a2bc8-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="a2bc8-105">\<绑定 ></span><span class="sxs-lookup"><span data-stu-id="a2bc8-105">\<bindings></span></span>  
<span data-ttu-id="a2bc8-106">\<mexTcpBinding ></span><span class="sxs-lookup"><span data-stu-id="a2bc8-106">\<mexTcpBinding></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a2bc8-107">语法</span><span class="sxs-lookup"><span data-stu-id="a2bc8-107">Syntax</span></span>  
  
```xml  
<mexTcpBinding>  
   <binding   
       closeTimeout="TimeSpan"   
       name="string"   
       openTimeout="TimeSpan"   
       receiveTimeout="TimeSpan"  
       sendTimeout="TimeSpan">  
   </binding>  
</mexTcpBinding>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a2bc8-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="a2bc8-108">Attributes and Elements</span></span>  
 <span data-ttu-id="a2bc8-109">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="a2bc8-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a2bc8-110">特性</span><span class="sxs-lookup"><span data-stu-id="a2bc8-110">Attributes</span></span>  
  
|<span data-ttu-id="a2bc8-111">特性</span><span class="sxs-lookup"><span data-stu-id="a2bc8-111">Attribute</span></span>|<span data-ttu-id="a2bc8-112">描述</span><span class="sxs-lookup"><span data-stu-id="a2bc8-112">Description</span></span>|  
|---------------|-----------------|  
|`closeTimeout`|<span data-ttu-id="a2bc8-113">一个 <xref:System.TimeSpan> 值，指定为完成关闭操作提供的时间间隔。</span><span class="sxs-lookup"><span data-stu-id="a2bc8-113">A <xref:System.TimeSpan> value that specifies the interval of time provided for a close operation to complete.</span></span> <span data-ttu-id="a2bc8-114">此值应大于或等于 <xref:System.TimeSpan.Zero>。</span><span class="sxs-lookup"><span data-stu-id="a2bc8-114">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="a2bc8-115">默认值为 00:01:00。</span><span class="sxs-lookup"><span data-stu-id="a2bc8-115">The default is 00:01:00.</span></span>|  
|`name`|<span data-ttu-id="a2bc8-116">一个包含绑定的配置名称的字符串。</span><span class="sxs-lookup"><span data-stu-id="a2bc8-116">A string that contains the configuration name of the binding.</span></span> <span data-ttu-id="a2bc8-117">因为此值用作绑定的标识，所以它应该是唯一的。</span><span class="sxs-lookup"><span data-stu-id="a2bc8-117">This value should be unique because it is used as an identification for the binding.</span></span> <span data-ttu-id="a2bc8-118">每个绑定都具有 `name` 和 `namespace` 属性，它们共同在服务的元数据中唯一标识每个绑定。</span><span class="sxs-lookup"><span data-stu-id="a2bc8-118">Each binding has a `name` and `namespace` attribute that together uniquely identify it in the metadata of the service.</span></span> <span data-ttu-id="a2bc8-119">此外，在同一类型的绑定中，此名称是唯一的。</span><span class="sxs-lookup"><span data-stu-id="a2bc8-119">In addition, this name is unique among bindings of the same type.</span></span> <span data-ttu-id="a2bc8-120">从 [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)] 开始，不要求绑定和行为具有名称。</span><span class="sxs-lookup"><span data-stu-id="a2bc8-120">Starting with [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="a2bc8-121">有关默认配置和无名称的绑定和行为的详细信息，请参阅[简化配置](../../../../../docs/framework/wcf/simplified-configuration.md)和[简化配置 WCF 服务](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md)。</span><span class="sxs-lookup"><span data-stu-id="a2bc8-121">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../../../docs/framework/wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>|  
|`openTimeout`|<span data-ttu-id="a2bc8-122">一个 <xref:System.TimeSpan> 值，指定为完成打开操作提供的时间间隔。</span><span class="sxs-lookup"><span data-stu-id="a2bc8-122">A <xref:System.TimeSpan> value that specifies the interval of time provided for an open operation to complete.</span></span> <span data-ttu-id="a2bc8-123">此值应大于或等于 <xref:System.TimeSpan.Zero>。</span><span class="sxs-lookup"><span data-stu-id="a2bc8-123">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="a2bc8-124">默认值为 00:01:00。</span><span class="sxs-lookup"><span data-stu-id="a2bc8-124">The default is 00:01:00.</span></span>|  
|`receiveTimeout`|<span data-ttu-id="a2bc8-125">一个 <xref:System.TimeSpan> 值，指定为完成接收操作提供的时间间隔。</span><span class="sxs-lookup"><span data-stu-id="a2bc8-125">A <xref:System.TimeSpan> value that specifies the interval of time provided for a receive operation to complete.</span></span> <span data-ttu-id="a2bc8-126">此值应大于或等于 <xref:System.TimeSpan.Zero>。</span><span class="sxs-lookup"><span data-stu-id="a2bc8-126">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="a2bc8-127">默认值为 00:10:00。</span><span class="sxs-lookup"><span data-stu-id="a2bc8-127">The default is 00:10:00.</span></span>|  
|`sendTimeout`|<span data-ttu-id="a2bc8-128">一个 <xref:System.TimeSpan> 值，指定为完成发送操作提供的时间间隔。</span><span class="sxs-lookup"><span data-stu-id="a2bc8-128">A <xref:System.TimeSpan> value that specifies the interval of time provided for a send operation to complete.</span></span> <span data-ttu-id="a2bc8-129">此值应大于或等于 <xref:System.TimeSpan.Zero>。</span><span class="sxs-lookup"><span data-stu-id="a2bc8-129">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="a2bc8-130">默认值为 00:01:00。</span><span class="sxs-lookup"><span data-stu-id="a2bc8-130">The default is 00:01:00.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a2bc8-131">子元素</span><span class="sxs-lookup"><span data-stu-id="a2bc8-131">Child Elements</span></span>  
 <span data-ttu-id="a2bc8-132">无。</span><span class="sxs-lookup"><span data-stu-id="a2bc8-132">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="a2bc8-133">父元素</span><span class="sxs-lookup"><span data-stu-id="a2bc8-133">Parent Elements</span></span>  
  
|<span data-ttu-id="a2bc8-134">元素</span><span class="sxs-lookup"><span data-stu-id="a2bc8-134">Element</span></span>|<span data-ttu-id="a2bc8-135">描述</span><span class="sxs-lookup"><span data-stu-id="a2bc8-135">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a2bc8-136">\<绑定 ></span><span class="sxs-lookup"><span data-stu-id="a2bc8-136">\<bindings></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md)|<span data-ttu-id="a2bc8-137">此元素包含标准绑定和自定义绑定的集合。</span><span class="sxs-lookup"><span data-stu-id="a2bc8-137">This element holds a collection of standard and custom bindings.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a2bc8-138">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a2bc8-138">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.MexTcpBindingElement>  
 <xref:System.ServiceModel.Description.MetadataExchangeBindings.CreateMexTcpBinding%2A>  
 [<span data-ttu-id="a2bc8-139">如何： 使用配置文件为服务中发布元数据</span><span class="sxs-lookup"><span data-stu-id="a2bc8-139">How to: Publish Metadata for a Service Using a Configuration File</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md)  
 [<span data-ttu-id="a2bc8-140">发布和检索元数据通过自定义绑定</span><span class="sxs-lookup"><span data-stu-id="a2bc8-140">Publishing and Retrieving Metadata Over a Custom Binding</span></span>](../../../../../docs/framework/wcf/extending/publishing-and-retrieving-metadata-over-a-custom-binding.md)  
 [<span data-ttu-id="a2bc8-141">元数据</span><span class="sxs-lookup"><span data-stu-id="a2bc8-141">Metadata</span></span>](../../../../../docs/framework/wcf/feature-details/metadata.md)  
 [<span data-ttu-id="a2bc8-142">绑定</span><span class="sxs-lookup"><span data-stu-id="a2bc8-142">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="a2bc8-143">配置系统提供的绑定</span><span class="sxs-lookup"><span data-stu-id="a2bc8-143">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="a2bc8-144">使用绑定来配置 Windows Communication Foundation 服务和客户端</span><span class="sxs-lookup"><span data-stu-id="a2bc8-144">Using Bindings to Configure Windows Communication Foundation Services and Clients</span></span>](http://msdn.microsoft.com/en-us/bd8b277b-932f-472f-a42a-b02bb5257dfb)  
 [<span data-ttu-id="a2bc8-145">\<绑定 ></span><span class="sxs-lookup"><span data-stu-id="a2bc8-145">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
