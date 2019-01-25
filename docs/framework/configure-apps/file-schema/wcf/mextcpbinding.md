---
title: '&lt;mexTcpBinding&gt;'
ms.date: 03/30/2017
ms.assetid: 01baba8d-d784-4255-9ea2-7afff1482bf0
ms.openlocfilehash: 4c3858ee0dc7fd20bd1269c74a4499998d530f03
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54733982"
---
# <a name="ltmextcpbindinggt"></a><span data-ttu-id="b258a-102">&lt;mexTcpBinding&gt;</span><span class="sxs-lookup"><span data-stu-id="b258a-102">&lt;mexTcpBinding&gt;</span></span>
<span data-ttu-id="b258a-103">指定用于通过 TCP 进行的 WS-MetadataExchange (WS-MEX) 消息交换的绑定的设置。</span><span class="sxs-lookup"><span data-stu-id="b258a-103">Specifies the settings for a binding used for the WS-MetadataExchange (WS-MEX) message exchange over TCP.</span></span>  
  
 <span data-ttu-id="b258a-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="b258a-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="b258a-105">\<bindings></span><span class="sxs-lookup"><span data-stu-id="b258a-105">\<bindings></span></span>  
<span data-ttu-id="b258a-106">\<mexTcpBinding></span><span class="sxs-lookup"><span data-stu-id="b258a-106">\<mexTcpBinding></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b258a-107">语法</span><span class="sxs-lookup"><span data-stu-id="b258a-107">Syntax</span></span>  
  
```xml  
<mexTcpBinding>
  <binding closeTimeout="TimeSpan"
           name="string"
           openTimeout="TimeSpan"
           receiveTimeout="TimeSpan"
           sendTimeout="TimeSpan">
  </binding>
</mexTcpBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b258a-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="b258a-108">Attributes and Elements</span></span>  
 <span data-ttu-id="b258a-109">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="b258a-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b258a-110">特性</span><span class="sxs-lookup"><span data-stu-id="b258a-110">Attributes</span></span>  
  
|<span data-ttu-id="b258a-111">特性</span><span class="sxs-lookup"><span data-stu-id="b258a-111">Attribute</span></span>|<span data-ttu-id="b258a-112">描述</span><span class="sxs-lookup"><span data-stu-id="b258a-112">Description</span></span>|  
|---------------|-----------------|  
|`closeTimeout`|<span data-ttu-id="b258a-113">一个 <xref:System.TimeSpan> 值，指定为完成关闭操作提供的时间间隔。</span><span class="sxs-lookup"><span data-stu-id="b258a-113">A <xref:System.TimeSpan> value that specifies the interval of time provided for a close operation to complete.</span></span> <span data-ttu-id="b258a-114">此值应大于或等于 <xref:System.TimeSpan.Zero>。</span><span class="sxs-lookup"><span data-stu-id="b258a-114">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="b258a-115">默认值为 00:01:00。</span><span class="sxs-lookup"><span data-stu-id="b258a-115">The default is 00:01:00.</span></span>|  
|`name`|<span data-ttu-id="b258a-116">一个包含绑定的配置名称的字符串。</span><span class="sxs-lookup"><span data-stu-id="b258a-116">A string that contains the configuration name of the binding.</span></span> <span data-ttu-id="b258a-117">因为此值用作绑定的标识，所以它应该是唯一的。</span><span class="sxs-lookup"><span data-stu-id="b258a-117">This value should be unique because it is used as an identification for the binding.</span></span> <span data-ttu-id="b258a-118">每个绑定都具有 `name` 和 `namespace` 属性，它们共同在服务的元数据中唯一标识每个绑定。</span><span class="sxs-lookup"><span data-stu-id="b258a-118">Each binding has a `name` and `namespace` attribute that together uniquely identify it in the metadata of the service.</span></span> <span data-ttu-id="b258a-119">此外，在同一类型的绑定中，此名称是唯一的。</span><span class="sxs-lookup"><span data-stu-id="b258a-119">In addition, this name is unique among bindings of the same type.</span></span> <span data-ttu-id="b258a-120">从 [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)] 开始，不要求绑定和行为具有名称。</span><span class="sxs-lookup"><span data-stu-id="b258a-120">Starting with [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="b258a-121">有关默认配置以及无名称绑定和行为的详细信息，请参阅[Simplified Configuration](../../../../../docs/framework/wcf/simplified-configuration.md)并[WCF 服务的简化配置](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md)。</span><span class="sxs-lookup"><span data-stu-id="b258a-121">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../../../docs/framework/wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>|  
|`openTimeout`|<span data-ttu-id="b258a-122">一个 <xref:System.TimeSpan> 值，指定为完成打开操作提供的时间间隔。</span><span class="sxs-lookup"><span data-stu-id="b258a-122">A <xref:System.TimeSpan> value that specifies the interval of time provided for an open operation to complete.</span></span> <span data-ttu-id="b258a-123">此值应大于或等于 <xref:System.TimeSpan.Zero>。</span><span class="sxs-lookup"><span data-stu-id="b258a-123">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="b258a-124">默认值为 00:01:00。</span><span class="sxs-lookup"><span data-stu-id="b258a-124">The default is 00:01:00.</span></span>|  
|`receiveTimeout`|<span data-ttu-id="b258a-125">一个 <xref:System.TimeSpan> 值，指定为完成接收操作提供的时间间隔。</span><span class="sxs-lookup"><span data-stu-id="b258a-125">A <xref:System.TimeSpan> value that specifies the interval of time provided for a receive operation to complete.</span></span> <span data-ttu-id="b258a-126">此值应大于或等于 <xref:System.TimeSpan.Zero>。</span><span class="sxs-lookup"><span data-stu-id="b258a-126">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="b258a-127">默认值为 00:10:00。</span><span class="sxs-lookup"><span data-stu-id="b258a-127">The default is 00:10:00.</span></span>|  
|`sendTimeout`|<span data-ttu-id="b258a-128">一个 <xref:System.TimeSpan> 值，指定为完成发送操作提供的时间间隔。</span><span class="sxs-lookup"><span data-stu-id="b258a-128">A <xref:System.TimeSpan> value that specifies the interval of time provided for a send operation to complete.</span></span> <span data-ttu-id="b258a-129">此值应大于或等于 <xref:System.TimeSpan.Zero>。</span><span class="sxs-lookup"><span data-stu-id="b258a-129">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="b258a-130">默认值为 00:01:00。</span><span class="sxs-lookup"><span data-stu-id="b258a-130">The default is 00:01:00.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b258a-131">子元素</span><span class="sxs-lookup"><span data-stu-id="b258a-131">Child Elements</span></span>  
 <span data-ttu-id="b258a-132">无。</span><span class="sxs-lookup"><span data-stu-id="b258a-132">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="b258a-133">父元素</span><span class="sxs-lookup"><span data-stu-id="b258a-133">Parent Elements</span></span>  
  
|<span data-ttu-id="b258a-134">元素</span><span class="sxs-lookup"><span data-stu-id="b258a-134">Element</span></span>|<span data-ttu-id="b258a-135">描述</span><span class="sxs-lookup"><span data-stu-id="b258a-135">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b258a-136">\<bindings></span><span class="sxs-lookup"><span data-stu-id="b258a-136">\<bindings></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md)|<span data-ttu-id="b258a-137">此元素包含标准绑定和自定义绑定的集合。</span><span class="sxs-lookup"><span data-stu-id="b258a-137">This element holds a collection of standard and custom bindings.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="b258a-138">请参阅</span><span class="sxs-lookup"><span data-stu-id="b258a-138">See also</span></span>
- <xref:System.ServiceModel.Configuration.MexTcpBindingElement>
- <xref:System.ServiceModel.Description.MetadataExchangeBindings.CreateMexTcpBinding%2A>
- [<span data-ttu-id="b258a-139">如何：发布使用配置文件服务的元数据</span><span class="sxs-lookup"><span data-stu-id="b258a-139">How to: Publish Metadata for a Service Using a Configuration File</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md)
- [<span data-ttu-id="b258a-140">通过自定义绑定发布和检索元数据</span><span class="sxs-lookup"><span data-stu-id="b258a-140">Publishing and Retrieving Metadata Over a Custom Binding</span></span>](../../../../../docs/framework/wcf/extending/publishing-and-retrieving-metadata-over-a-custom-binding.md)
- [<span data-ttu-id="b258a-141">元数据</span><span class="sxs-lookup"><span data-stu-id="b258a-141">Metadata</span></span>](../../../../../docs/framework/wcf/feature-details/metadata.md)
- [<span data-ttu-id="b258a-142">绑定</span><span class="sxs-lookup"><span data-stu-id="b258a-142">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="b258a-143">配置系统提供的绑定</span><span class="sxs-lookup"><span data-stu-id="b258a-143">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="b258a-144">使用绑定配置服务和客户端</span><span class="sxs-lookup"><span data-stu-id="b258a-144">Using Bindings to Configure Services and Clients</span></span>](../../../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="b258a-145">\<binding></span><span class="sxs-lookup"><span data-stu-id="b258a-145">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
