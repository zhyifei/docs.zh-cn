---
title: '&lt;mexHttpsBinding&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f2ed3774-78b9-4a15-b79b-655f1ad68b86
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a6725741e6e0e67f3d26dc3bc1e83a57f6fcd430
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/19/2018
---
# <a name="ltmexhttpsbindinggt"></a><span data-ttu-id="79b88-102">&lt;mexHttpsBinding&gt;</span><span class="sxs-lookup"><span data-stu-id="79b88-102">&lt;mexHttpsBinding&gt;</span></span>
<span data-ttu-id="79b88-103">指定用于通过 HTTPS 进行的 WS-MetadataExchange (WS-MEX) 消息交换的绑定的设置。</span><span class="sxs-lookup"><span data-stu-id="79b88-103">Specifies the settings for a binding used for the WS-MetadataExchange (WS-MEX) message exchange over HTTPS.</span></span>  
  
 <span data-ttu-id="79b88-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="79b88-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="79b88-105">\<bindings></span><span class="sxs-lookup"><span data-stu-id="79b88-105">\<bindings></span></span>  
<span data-ttu-id="79b88-106">\<mexHttpsBinding></span><span class="sxs-lookup"><span data-stu-id="79b88-106">\<mexHttpsBinding></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="79b88-107">语法</span><span class="sxs-lookup"><span data-stu-id="79b88-107">Syntax</span></span>  
  
```xml  
<mexHttpsBinding>  
   <binding   
       closeTimeout="TimeSpan"   
       name="string"   
       openTimeout="TimeSpan"   
       receiveTimeout="TimeSpan"  
       sendTimeout="TimeSpan">  
   </binding>  
</mexHttpsBinding>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="79b88-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="79b88-108">Attributes and Elements</span></span>  
 <span data-ttu-id="79b88-109">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="79b88-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="79b88-110">特性</span><span class="sxs-lookup"><span data-stu-id="79b88-110">Attributes</span></span>  
  
|<span data-ttu-id="79b88-111">特性</span><span class="sxs-lookup"><span data-stu-id="79b88-111">Attribute</span></span>|<span data-ttu-id="79b88-112">描述</span><span class="sxs-lookup"><span data-stu-id="79b88-112">Description</span></span>|  
|---------------|-----------------|  
|`closeTimeout`|<span data-ttu-id="79b88-113">一个 <xref:System.TimeSpan> 值，指定为完成关闭操作提供的时间间隔。</span><span class="sxs-lookup"><span data-stu-id="79b88-113">A <xref:System.TimeSpan> value that specifies the interval of time provided for a close operation to complete.</span></span> <span data-ttu-id="79b88-114">此值应大于或等于 <xref:System.TimeSpan.Zero>。</span><span class="sxs-lookup"><span data-stu-id="79b88-114">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="79b88-115">默认值为 00:01:00。</span><span class="sxs-lookup"><span data-stu-id="79b88-115">The default is 00:01:00.</span></span>|  
|`name`|<span data-ttu-id="79b88-116">一个包含绑定的配置名称的字符串。</span><span class="sxs-lookup"><span data-stu-id="79b88-116">A string that contains the configuration name of the binding.</span></span> <span data-ttu-id="79b88-117">因为此值用作绑定的标识，所以它应该是唯一的。</span><span class="sxs-lookup"><span data-stu-id="79b88-117">This value should be unique because it is used as an identification for the binding.</span></span> <span data-ttu-id="79b88-118">每个绑定都具有 `name` 和 `namespace` 属性，它们共同在服务的元数据中唯一标识每个绑定。</span><span class="sxs-lookup"><span data-stu-id="79b88-118">Each binding has a `name` and `namespace` attribute that together uniquely identify it in the metadata of the service.</span></span> <span data-ttu-id="79b88-119">此外，在同一类型的绑定中，此名称是唯一的。</span><span class="sxs-lookup"><span data-stu-id="79b88-119">In addition, this name is unique among bindings of the same type.</span></span> <span data-ttu-id="79b88-120">从 [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)] 开始，不要求绑定和行为具有名称。</span><span class="sxs-lookup"><span data-stu-id="79b88-120">Starting with [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="79b88-121">有关默认配置和无名称的绑定和行为的详细信息，请参阅[简化配置](../../../../../docs/framework/wcf/simplified-configuration.md)和[简化配置 WCF 服务](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md)。</span><span class="sxs-lookup"><span data-stu-id="79b88-121">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../../../docs/framework/wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>|  
|`openTimeout`|<span data-ttu-id="79b88-122">一个 <xref:System.TimeSpan> 值，指定为完成打开操作提供的时间间隔。</span><span class="sxs-lookup"><span data-stu-id="79b88-122">A <xref:System.TimeSpan> value that specifies the interval of time provided for an open operation to complete.</span></span> <span data-ttu-id="79b88-123">此值应大于或等于 <xref:System.TimeSpan.Zero>。</span><span class="sxs-lookup"><span data-stu-id="79b88-123">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="79b88-124">默认值为 00:01:00。</span><span class="sxs-lookup"><span data-stu-id="79b88-124">The default is 00:01:00.</span></span>|  
|`receiveTimeout`|<span data-ttu-id="79b88-125">一个 <xref:System.TimeSpan> 值，指定为完成接收操作提供的时间间隔。</span><span class="sxs-lookup"><span data-stu-id="79b88-125">A <xref:System.TimeSpan> value that specifies the interval of time provided for a receive operation to complete.</span></span> <span data-ttu-id="79b88-126">此值应大于或等于 <xref:System.TimeSpan.Zero>。</span><span class="sxs-lookup"><span data-stu-id="79b88-126">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="79b88-127">默认值为 00:10:00。</span><span class="sxs-lookup"><span data-stu-id="79b88-127">The default is 00:10:00.</span></span>|  
|`sendTimeout`|<span data-ttu-id="79b88-128">一个 <xref:System.TimeSpan> 值，指定为完成发送操作提供的时间间隔。</span><span class="sxs-lookup"><span data-stu-id="79b88-128">A <xref:System.TimeSpan> value that specifies the interval of time provided for a send operation to complete.</span></span> <span data-ttu-id="79b88-129">此值应大于或等于 <xref:System.TimeSpan.Zero>。</span><span class="sxs-lookup"><span data-stu-id="79b88-129">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="79b88-130">默认值为 00:01:00。</span><span class="sxs-lookup"><span data-stu-id="79b88-130">The default is 00:01:00.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="79b88-131">子元素</span><span class="sxs-lookup"><span data-stu-id="79b88-131">Child Elements</span></span>  
 <span data-ttu-id="79b88-132">无。</span><span class="sxs-lookup"><span data-stu-id="79b88-132">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="79b88-133">父元素</span><span class="sxs-lookup"><span data-stu-id="79b88-133">Parent Elements</span></span>  
  
|<span data-ttu-id="79b88-134">元素</span><span class="sxs-lookup"><span data-stu-id="79b88-134">Element</span></span>|<span data-ttu-id="79b88-135">描述</span><span class="sxs-lookup"><span data-stu-id="79b88-135">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="79b88-136">\<bindings></span><span class="sxs-lookup"><span data-stu-id="79b88-136">\<bindings></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md)|<span data-ttu-id="79b88-137">此元素包含标准绑定和自定义绑定的集合。</span><span class="sxs-lookup"><span data-stu-id="79b88-137">This element holds a collection of standard and custom bindings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="79b88-138">备注</span><span class="sxs-lookup"><span data-stu-id="79b88-138">Remarks</span></span>  
 <span data-ttu-id="79b88-139">此绑定实质上是支持使用证书的传输级安全性的 `WSHttpBinding` 绑定。</span><span class="sxs-lookup"><span data-stu-id="79b88-139">This binding is essentially a `WSHttpBinding` binding that supports transport-level security using certificates.</span></span> <span data-ttu-id="79b88-140">有关配置和使用此类的元数据终结点的详细信息，请参阅[如何： 配置自定义 Ws-metadata Exchange 绑定](../../../../../docs/framework/wcf/extending/how-to-configure-a-custom-ws-metadata-exchange-binding.md)，[如何： 检索元数据通过非 MEX 绑定](../../../../../docs/framework/wcf/extending/how-to-retrieve-metadata-over-a-non-mex-binding.md)，与示例[自定义安全元数据终结点](../../../../../docs/framework/wcf/samples/custom-secure-metadata-endpoint.md)。</span><span class="sxs-lookup"><span data-stu-id="79b88-140">For more information about configuring and using such a metadata endpoint, see [How to: Configure a Custom WS-Metadata Exchange Binding](../../../../../docs/framework/wcf/extending/how-to-configure-a-custom-ws-metadata-exchange-binding.md), [How to: Retrieve Metadata Over a non-MEX Binding](../../../../../docs/framework/wcf/extending/how-to-retrieve-metadata-over-a-non-mex-binding.md), and the sample [Custom Secure Metadata Endpoint](../../../../../docs/framework/wcf/samples/custom-secure-metadata-endpoint.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="79b88-141">请参阅</span><span class="sxs-lookup"><span data-stu-id="79b88-141">See Also</span></span>  
 <xref:System.ServiceModel.Description.MetadataExchangeBindings.CreateMexHttpsBinding%2A>  
 <xref:System.ServiceModel.Configuration.MexHttpsBindingElement>  
 [<span data-ttu-id="79b88-142">如何：使用配置文件发布服务的元数据</span><span class="sxs-lookup"><span data-stu-id="79b88-142">How to: Publish Metadata for a Service Using a Configuration File</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md)  
 [<span data-ttu-id="79b88-143">通过自定义绑定发布和检索元数据</span><span class="sxs-lookup"><span data-stu-id="79b88-143">Publishing and Retrieving Metadata Over a Custom Binding</span></span>](../../../../../docs/framework/wcf/extending/publishing-and-retrieving-metadata-over-a-custom-binding.md)  
 [<span data-ttu-id="79b88-144">如何：配置自定义 WS-Metadata Exchange 绑定</span><span class="sxs-lookup"><span data-stu-id="79b88-144">How to: Configure a Custom WS-Metadata Exchange Binding</span></span>](../../../../../docs/framework/wcf/extending/how-to-configure-a-custom-ws-metadata-exchange-binding.md)  
 [<span data-ttu-id="79b88-145">如何：通过非 MEX 绑定检索元数据</span><span class="sxs-lookup"><span data-stu-id="79b88-145">How to: Retrieve Metadata Over a non-MEX Binding</span></span>](../../../../../docs/framework/wcf/extending/how-to-retrieve-metadata-over-a-non-mex-binding.md)  
 [<span data-ttu-id="79b88-146">自定义元数据终结点</span><span class="sxs-lookup"><span data-stu-id="79b88-146">Custom Secure Metadata Endpoint</span></span>](../../../../../docs/framework/wcf/samples/custom-secure-metadata-endpoint.md)  
 [<span data-ttu-id="79b88-147">元数据</span><span class="sxs-lookup"><span data-stu-id="79b88-147">Metadata</span></span>](../../../../../docs/framework/wcf/feature-details/metadata.md)  
 [<span data-ttu-id="79b88-148">绑定</span><span class="sxs-lookup"><span data-stu-id="79b88-148">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="79b88-149">配置系统提供的绑定</span><span class="sxs-lookup"><span data-stu-id="79b88-149">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="79b88-150">使用绑定来配置 Windows Communication Foundation 服务和客户端</span><span class="sxs-lookup"><span data-stu-id="79b88-150">Using Bindings to Configure Windows Communication Foundation Services and Clients</span></span>](http://msdn.microsoft.com/library/bd8b277b-932f-472f-a42a-b02bb5257dfb)  
 [<span data-ttu-id="79b88-151">\<binding></span><span class="sxs-lookup"><span data-stu-id="79b88-151">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
