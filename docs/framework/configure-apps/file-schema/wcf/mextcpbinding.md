---
title: <mexTcpBinding>
ms.date: 03/30/2017
ms.assetid: 01baba8d-d784-4255-9ea2-7afff1482bf0
ms.openlocfilehash: 491597da508487c3988b284c84411123d434fe72
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69932535"
---
# <a name="mextcpbinding"></a><span data-ttu-id="8c207-101">\<mexTcpBinding></span><span class="sxs-lookup"><span data-stu-id="8c207-101">\<mexTcpBinding></span></span>
<span data-ttu-id="8c207-102">指定用于通过 TCP 进行的 WS-MetadataExchange (WS-MEX) 消息交换的绑定的设置。</span><span class="sxs-lookup"><span data-stu-id="8c207-102">Specifies the settings for a binding used for the WS-MetadataExchange (WS-MEX) message exchange over TCP.</span></span>  
  
 <span data-ttu-id="8c207-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="8c207-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="8c207-104">\<bindings></span><span class="sxs-lookup"><span data-stu-id="8c207-104">\<bindings></span></span>  
<span data-ttu-id="8c207-105">\<mexTcpBinding></span><span class="sxs-lookup"><span data-stu-id="8c207-105">\<mexTcpBinding></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8c207-106">语法</span><span class="sxs-lookup"><span data-stu-id="8c207-106">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8c207-107">特性和元素</span><span class="sxs-lookup"><span data-stu-id="8c207-107">Attributes and Elements</span></span>  
 <span data-ttu-id="8c207-108">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="8c207-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8c207-109">特性</span><span class="sxs-lookup"><span data-stu-id="8c207-109">Attributes</span></span>  
  
|<span data-ttu-id="8c207-110">特性</span><span class="sxs-lookup"><span data-stu-id="8c207-110">Attribute</span></span>|<span data-ttu-id="8c207-111">描述</span><span class="sxs-lookup"><span data-stu-id="8c207-111">Description</span></span>|  
|---------------|-----------------|  
|`closeTimeout`|<span data-ttu-id="8c207-112">一个 <xref:System.TimeSpan> 值，指定为完成关闭操作提供的时间间隔。</span><span class="sxs-lookup"><span data-stu-id="8c207-112">A <xref:System.TimeSpan> value that specifies the interval of time provided for a close operation to complete.</span></span> <span data-ttu-id="8c207-113">此值应大于或等于 <xref:System.TimeSpan.Zero>。</span><span class="sxs-lookup"><span data-stu-id="8c207-113">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="8c207-114">默认值为 00:01:00。</span><span class="sxs-lookup"><span data-stu-id="8c207-114">The default is 00:01:00.</span></span>|  
|`name`|<span data-ttu-id="8c207-115">一个包含绑定的配置名称的字符串。</span><span class="sxs-lookup"><span data-stu-id="8c207-115">A string that contains the configuration name of the binding.</span></span> <span data-ttu-id="8c207-116">因为此值用作绑定的标识，所以它应该是唯一的。</span><span class="sxs-lookup"><span data-stu-id="8c207-116">This value should be unique because it is used as an identification for the binding.</span></span> <span data-ttu-id="8c207-117">每个绑定都具有 `name` 和 `namespace` 属性，它们共同在服务的元数据中唯一标识每个绑定。</span><span class="sxs-lookup"><span data-stu-id="8c207-117">Each binding has a `name` and `namespace` attribute that together uniquely identify it in the metadata of the service.</span></span> <span data-ttu-id="8c207-118">此外，在同一类型的绑定中，此名称是唯一的。</span><span class="sxs-lookup"><span data-stu-id="8c207-118">In addition, this name is unique among bindings of the same type.</span></span> <span data-ttu-id="8c207-119">从 [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)] 开始，不要求绑定和行为具有名称。</span><span class="sxs-lookup"><span data-stu-id="8c207-119">Starting with [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="8c207-120">有关默认配置和无值绑定和行为的详细信息, 请参阅[WCF 服务的](../../../wcf/samples/simplified-configuration-for-wcf-services.md)[简化配置](../../../wcf/simplified-configuration.md)和简化配置。</span><span class="sxs-lookup"><span data-stu-id="8c207-120">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>|  
|`openTimeout`|<span data-ttu-id="8c207-121">一个 <xref:System.TimeSpan> 值，指定为完成打开操作提供的时间间隔。</span><span class="sxs-lookup"><span data-stu-id="8c207-121">A <xref:System.TimeSpan> value that specifies the interval of time provided for an open operation to complete.</span></span> <span data-ttu-id="8c207-122">此值应大于或等于 <xref:System.TimeSpan.Zero>。</span><span class="sxs-lookup"><span data-stu-id="8c207-122">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="8c207-123">默认值为 00:01:00。</span><span class="sxs-lookup"><span data-stu-id="8c207-123">The default is 00:01:00.</span></span>|  
|`receiveTimeout`|<span data-ttu-id="8c207-124">一个 <xref:System.TimeSpan> 值，指定为完成接收操作提供的时间间隔。</span><span class="sxs-lookup"><span data-stu-id="8c207-124">A <xref:System.TimeSpan> value that specifies the interval of time provided for a receive operation to complete.</span></span> <span data-ttu-id="8c207-125">此值应大于或等于 <xref:System.TimeSpan.Zero>。</span><span class="sxs-lookup"><span data-stu-id="8c207-125">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="8c207-126">默认值为 00:10:00。</span><span class="sxs-lookup"><span data-stu-id="8c207-126">The default is 00:10:00.</span></span>|  
|`sendTimeout`|<span data-ttu-id="8c207-127">一个 <xref:System.TimeSpan> 值，指定为完成发送操作提供的时间间隔。</span><span class="sxs-lookup"><span data-stu-id="8c207-127">A <xref:System.TimeSpan> value that specifies the interval of time provided for a send operation to complete.</span></span> <span data-ttu-id="8c207-128">此值应大于或等于 <xref:System.TimeSpan.Zero>。</span><span class="sxs-lookup"><span data-stu-id="8c207-128">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="8c207-129">默认值为 00:01:00。</span><span class="sxs-lookup"><span data-stu-id="8c207-129">The default is 00:01:00.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="8c207-130">子元素</span><span class="sxs-lookup"><span data-stu-id="8c207-130">Child Elements</span></span>  
 <span data-ttu-id="8c207-131">无。</span><span class="sxs-lookup"><span data-stu-id="8c207-131">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="8c207-132">父元素</span><span class="sxs-lookup"><span data-stu-id="8c207-132">Parent Elements</span></span>  
  
|<span data-ttu-id="8c207-133">元素</span><span class="sxs-lookup"><span data-stu-id="8c207-133">Element</span></span>|<span data-ttu-id="8c207-134">描述</span><span class="sxs-lookup"><span data-stu-id="8c207-134">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8c207-135">\<bindings></span><span class="sxs-lookup"><span data-stu-id="8c207-135">\<bindings></span></span>](bindings.md)|<span data-ttu-id="8c207-136">此元素包含标准绑定和自定义绑定的集合。</span><span class="sxs-lookup"><span data-stu-id="8c207-136">This element holds a collection of standard and custom bindings.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="8c207-137">请参阅</span><span class="sxs-lookup"><span data-stu-id="8c207-137">See also</span></span>

- <xref:System.ServiceModel.Configuration.MexTcpBindingElement>
- <xref:System.ServiceModel.Description.MetadataExchangeBindings.CreateMexTcpBinding%2A>
- [<span data-ttu-id="8c207-138">如何：使用配置文件发布服务的元数据</span><span class="sxs-lookup"><span data-stu-id="8c207-138">How to: Publish Metadata for a Service Using a Configuration File</span></span>](../../../wcf/feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md)
- [<span data-ttu-id="8c207-139">通过自定义绑定发布和检索元数据</span><span class="sxs-lookup"><span data-stu-id="8c207-139">Publishing and Retrieving Metadata Over a Custom Binding</span></span>](../../../wcf/extending/publishing-and-retrieving-metadata-over-a-custom-binding.md)
- [<span data-ttu-id="8c207-140">元数据</span><span class="sxs-lookup"><span data-stu-id="8c207-140">Metadata</span></span>](../../../wcf/feature-details/metadata.md)
- [<span data-ttu-id="8c207-141">绑定</span><span class="sxs-lookup"><span data-stu-id="8c207-141">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="8c207-142">配置系统提供的绑定</span><span class="sxs-lookup"><span data-stu-id="8c207-142">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="8c207-143">使用绑定配置服务和客户端</span><span class="sxs-lookup"><span data-stu-id="8c207-143">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="8c207-144">\<binding></span><span class="sxs-lookup"><span data-stu-id="8c207-144">\<binding></span></span>](../../../misc/binding.md)
