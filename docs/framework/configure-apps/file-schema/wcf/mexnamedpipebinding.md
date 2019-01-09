---
title: '&lt;mexNamedPipeBinding&gt;'
ms.date: 03/30/2017
ms.assetid: 193412fa-3260-414c-92c6-b32ed3b94a34
ms.openlocfilehash: a5dac6c5b4409f71e8360c174061d4d12ffac5d2
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/09/2019
ms.locfileid: "54151502"
---
# <a name="ltmexnamedpipebindinggt"></a><span data-ttu-id="58d78-102">&lt;mexNamedPipeBinding&gt;</span><span class="sxs-lookup"><span data-stu-id="58d78-102">&lt;mexNamedPipeBinding&gt;</span></span>
<span data-ttu-id="58d78-103">指定用于通过命名管道进行的 WS-MetadataExchange (WS-MEX) 消息交换的绑定的设置。</span><span class="sxs-lookup"><span data-stu-id="58d78-103">Specifies the settings for a binding used for the WS-MetadataExchange (WS-MEX) message exchange over named pipe.</span></span>  
  
 <span data-ttu-id="58d78-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="58d78-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="58d78-105">\<绑定 ></span><span class="sxs-lookup"><span data-stu-id="58d78-105">\<bindings></span></span>  
<span data-ttu-id="58d78-106">\<mexNamedPipeBinding></span><span class="sxs-lookup"><span data-stu-id="58d78-106">\<mexNamedPipeBinding></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="58d78-107">语法</span><span class="sxs-lookup"><span data-stu-id="58d78-107">Syntax</span></span>  
  
```xml  
<mexNamedPipeBinding>
  <binding closeTimeout="TimeSpan"
           name="string"
           openTimeout="TimeSpan"
           receiveTimeout="TimeSpan"
           sendTimeout="TimeSpan">
  </binding>
</mexNamedPipeBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="58d78-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="58d78-108">Attributes and Elements</span></span>  
 <span data-ttu-id="58d78-109">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="58d78-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="58d78-110">特性</span><span class="sxs-lookup"><span data-stu-id="58d78-110">Attributes</span></span>  
  
|<span data-ttu-id="58d78-111">特性</span><span class="sxs-lookup"><span data-stu-id="58d78-111">Attribute</span></span>|<span data-ttu-id="58d78-112">描述</span><span class="sxs-lookup"><span data-stu-id="58d78-112">Description</span></span>|  
|---------------|-----------------|  
|`closeTimeout`|<span data-ttu-id="58d78-113">一个 <xref:System.TimeSpan> 值，指定为完成关闭操作提供的时间间隔。</span><span class="sxs-lookup"><span data-stu-id="58d78-113">A <xref:System.TimeSpan> value that specifies the interval of time provided for a close operation to complete.</span></span> <span data-ttu-id="58d78-114">此值应大于或等于 <xref:System.TimeSpan.Zero>。</span><span class="sxs-lookup"><span data-stu-id="58d78-114">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="58d78-115">默认值为 00:01:00。</span><span class="sxs-lookup"><span data-stu-id="58d78-115">The default is 00:01:00.</span></span>|  
|`name`|<span data-ttu-id="58d78-116">一个包含绑定的配置名称的字符串。</span><span class="sxs-lookup"><span data-stu-id="58d78-116">A string that contains the configuration name of the binding.</span></span> <span data-ttu-id="58d78-117">因为此值用作绑定的标识，所以它应该是唯一的。</span><span class="sxs-lookup"><span data-stu-id="58d78-117">This value should be unique because it is used as an identification for the binding.</span></span> <span data-ttu-id="58d78-118">每个绑定都具有 `name` 和 `namespace` 属性，它们共同在服务的元数据中唯一标识每个绑定。</span><span class="sxs-lookup"><span data-stu-id="58d78-118">Each binding has a `name` and `namespace` attribute that together uniquely identify it in the metadata of the service.</span></span> <span data-ttu-id="58d78-119">此外，在同一类型的绑定中，此名称是唯一的。</span><span class="sxs-lookup"><span data-stu-id="58d78-119">In addition, this name is unique among bindings of the same type.</span></span> <span data-ttu-id="58d78-120">从 [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)] 开始，不要求绑定和行为具有名称。</span><span class="sxs-lookup"><span data-stu-id="58d78-120">Starting with [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="58d78-121">有关默认配置以及无名称绑定和行为的详细信息，请参阅[Simplified Configuration](../../../../../docs/framework/wcf/simplified-configuration.md)并[WCF 服务的简化配置](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md)。</span><span class="sxs-lookup"><span data-stu-id="58d78-121">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../../../docs/framework/wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>|  
|`openTimeout`|<span data-ttu-id="58d78-122">一个 <xref:System.TimeSpan> 值，指定为完成打开操作提供的时间间隔。</span><span class="sxs-lookup"><span data-stu-id="58d78-122">A <xref:System.TimeSpan> value that specifies the interval of time provided for an open operation to complete.</span></span> <span data-ttu-id="58d78-123">此值应大于或等于 <xref:System.TimeSpan.Zero>。</span><span class="sxs-lookup"><span data-stu-id="58d78-123">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="58d78-124">默认值为 00:01:00。</span><span class="sxs-lookup"><span data-stu-id="58d78-124">The default is 00:01:00.</span></span>|  
|`receiveTimeout`|<span data-ttu-id="58d78-125">一个 <xref:System.TimeSpan> 值，指定为完成接收操作提供的时间间隔。</span><span class="sxs-lookup"><span data-stu-id="58d78-125">A <xref:System.TimeSpan> value that specifies the interval of time provided for a receive operation to complete.</span></span> <span data-ttu-id="58d78-126">此值应大于或等于 <xref:System.TimeSpan.Zero>。</span><span class="sxs-lookup"><span data-stu-id="58d78-126">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="58d78-127">默认值为 00:10:00。</span><span class="sxs-lookup"><span data-stu-id="58d78-127">The default is 00:10:00.</span></span>|  
|`sendTimeout`|<span data-ttu-id="58d78-128">一个 <xref:System.TimeSpan> 值，指定为完成发送操作提供的时间间隔。</span><span class="sxs-lookup"><span data-stu-id="58d78-128">A <xref:System.TimeSpan> value that specifies the interval of time provided for a send operation to complete.</span></span> <span data-ttu-id="58d78-129">此值应大于或等于 <xref:System.TimeSpan.Zero>。</span><span class="sxs-lookup"><span data-stu-id="58d78-129">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="58d78-130">默认值为 00:01:00。</span><span class="sxs-lookup"><span data-stu-id="58d78-130">The default is 00:01:00.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="58d78-131">子元素</span><span class="sxs-lookup"><span data-stu-id="58d78-131">Child Elements</span></span>  
 <span data-ttu-id="58d78-132">无。</span><span class="sxs-lookup"><span data-stu-id="58d78-132">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="58d78-133">父元素</span><span class="sxs-lookup"><span data-stu-id="58d78-133">Parent Elements</span></span>  
  
|<span data-ttu-id="58d78-134">元素</span><span class="sxs-lookup"><span data-stu-id="58d78-134">Element</span></span>|<span data-ttu-id="58d78-135">描述</span><span class="sxs-lookup"><span data-stu-id="58d78-135">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="58d78-136">\<绑定 ></span><span class="sxs-lookup"><span data-stu-id="58d78-136">\<bindings></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md)|<span data-ttu-id="58d78-137">此元素包含标准绑定和自定义绑定的集合。</span><span class="sxs-lookup"><span data-stu-id="58d78-137">This element holds a collection of standard and custom bindings.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="58d78-138">请参阅</span><span class="sxs-lookup"><span data-stu-id="58d78-138">See Also</span></span>  
 <xref:System.ServiceModel.Description.MetadataExchangeBindings.CreateMexNamedPipeBinding%2A>  
 <xref:System.ServiceModel.Configuration.MexNamedPipeBindingElement>  
 [<span data-ttu-id="58d78-139">如何：发布使用配置文件服务的元数据</span><span class="sxs-lookup"><span data-stu-id="58d78-139">How to: Publish Metadata for a Service Using a Configuration File</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md)  
 [<span data-ttu-id="58d78-140">通过自定义绑定发布和检索元数据</span><span class="sxs-lookup"><span data-stu-id="58d78-140">Publishing and Retrieving Metadata Over a Custom Binding</span></span>](../../../../../docs/framework/wcf/extending/publishing-and-retrieving-metadata-over-a-custom-binding.md)  
 [<span data-ttu-id="58d78-141">元数据</span><span class="sxs-lookup"><span data-stu-id="58d78-141">Metadata</span></span>](../../../../../docs/framework/wcf/feature-details/metadata.md)  
 [<span data-ttu-id="58d78-142">绑定</span><span class="sxs-lookup"><span data-stu-id="58d78-142">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="58d78-143">配置系统提供的绑定</span><span class="sxs-lookup"><span data-stu-id="58d78-143">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="58d78-144">使用绑定配置服务和客户端</span><span class="sxs-lookup"><span data-stu-id="58d78-144">Using Bindings to Configure Services and Clients</span></span>](../../../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)  
 [<span data-ttu-id="58d78-145">\<绑定 ></span><span class="sxs-lookup"><span data-stu-id="58d78-145">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
