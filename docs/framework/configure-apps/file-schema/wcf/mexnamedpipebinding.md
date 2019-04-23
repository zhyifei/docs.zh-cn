---
title: <mexNamedPipeBinding>
ms.date: 03/30/2017
ms.assetid: 193412fa-3260-414c-92c6-b32ed3b94a34
ms.openlocfilehash: 9ac2b967e33571cbe0b4ad5ee81e13b009ffddd3
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59111353"
---
# <a name="mexnamedpipebinding"></a><span data-ttu-id="7fa4d-101">\<mexNamedPipeBinding></span><span class="sxs-lookup"><span data-stu-id="7fa4d-101">\<mexNamedPipeBinding></span></span>
<span data-ttu-id="7fa4d-102">指定用于通过命名管道进行的 WS-MetadataExchange (WS-MEX) 消息交换的绑定的设置。</span><span class="sxs-lookup"><span data-stu-id="7fa4d-102">Specifies the settings for a binding used for the WS-MetadataExchange (WS-MEX) message exchange over named pipe.</span></span>  
  
 <span data-ttu-id="7fa4d-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="7fa4d-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="7fa4d-104">\<bindings></span><span class="sxs-lookup"><span data-stu-id="7fa4d-104">\<bindings></span></span>  
<span data-ttu-id="7fa4d-105">\<mexNamedPipeBinding></span><span class="sxs-lookup"><span data-stu-id="7fa4d-105">\<mexNamedPipeBinding></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7fa4d-106">语法</span><span class="sxs-lookup"><span data-stu-id="7fa4d-106">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7fa4d-107">特性和元素</span><span class="sxs-lookup"><span data-stu-id="7fa4d-107">Attributes and Elements</span></span>  
 <span data-ttu-id="7fa4d-108">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="7fa4d-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7fa4d-109">特性</span><span class="sxs-lookup"><span data-stu-id="7fa4d-109">Attributes</span></span>  
  
|<span data-ttu-id="7fa4d-110">特性</span><span class="sxs-lookup"><span data-stu-id="7fa4d-110">Attribute</span></span>|<span data-ttu-id="7fa4d-111">描述</span><span class="sxs-lookup"><span data-stu-id="7fa4d-111">Description</span></span>|  
|---------------|-----------------|  
|`closeTimeout`|<span data-ttu-id="7fa4d-112">一个 <xref:System.TimeSpan> 值，指定为完成关闭操作提供的时间间隔。</span><span class="sxs-lookup"><span data-stu-id="7fa4d-112">A <xref:System.TimeSpan> value that specifies the interval of time provided for a close operation to complete.</span></span> <span data-ttu-id="7fa4d-113">此值应大于或等于 <xref:System.TimeSpan.Zero>。</span><span class="sxs-lookup"><span data-stu-id="7fa4d-113">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="7fa4d-114">默认值为 00:01:00。</span><span class="sxs-lookup"><span data-stu-id="7fa4d-114">The default is 00:01:00.</span></span>|  
|`name`|<span data-ttu-id="7fa4d-115">一个包含绑定的配置名称的字符串。</span><span class="sxs-lookup"><span data-stu-id="7fa4d-115">A string that contains the configuration name of the binding.</span></span> <span data-ttu-id="7fa4d-116">因为此值用作绑定的标识，所以它应该是唯一的。</span><span class="sxs-lookup"><span data-stu-id="7fa4d-116">This value should be unique because it is used as an identification for the binding.</span></span> <span data-ttu-id="7fa4d-117">每个绑定都具有 `name` 和 `namespace` 属性，它们共同在服务的元数据中唯一标识每个绑定。</span><span class="sxs-lookup"><span data-stu-id="7fa4d-117">Each binding has a `name` and `namespace` attribute that together uniquely identify it in the metadata of the service.</span></span> <span data-ttu-id="7fa4d-118">此外，在同一类型的绑定中，此名称是唯一的。</span><span class="sxs-lookup"><span data-stu-id="7fa4d-118">In addition, this name is unique among bindings of the same type.</span></span> <span data-ttu-id="7fa4d-119">从 [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)] 开始，不要求绑定和行为具有名称。</span><span class="sxs-lookup"><span data-stu-id="7fa4d-119">Starting with [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="7fa4d-120">有关默认配置以及无名称绑定和行为的详细信息，请参阅[Simplified Configuration](../../../../../docs/framework/wcf/simplified-configuration.md)并[WCF 服务的简化配置](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md)。</span><span class="sxs-lookup"><span data-stu-id="7fa4d-120">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../../../docs/framework/wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>|  
|`openTimeout`|<span data-ttu-id="7fa4d-121">一个 <xref:System.TimeSpan> 值，指定为完成打开操作提供的时间间隔。</span><span class="sxs-lookup"><span data-stu-id="7fa4d-121">A <xref:System.TimeSpan> value that specifies the interval of time provided for an open operation to complete.</span></span> <span data-ttu-id="7fa4d-122">此值应大于或等于 <xref:System.TimeSpan.Zero>。</span><span class="sxs-lookup"><span data-stu-id="7fa4d-122">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="7fa4d-123">默认值为 00:01:00。</span><span class="sxs-lookup"><span data-stu-id="7fa4d-123">The default is 00:01:00.</span></span>|  
|`receiveTimeout`|<span data-ttu-id="7fa4d-124">一个 <xref:System.TimeSpan> 值，指定为完成接收操作提供的时间间隔。</span><span class="sxs-lookup"><span data-stu-id="7fa4d-124">A <xref:System.TimeSpan> value that specifies the interval of time provided for a receive operation to complete.</span></span> <span data-ttu-id="7fa4d-125">此值应大于或等于 <xref:System.TimeSpan.Zero>。</span><span class="sxs-lookup"><span data-stu-id="7fa4d-125">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="7fa4d-126">默认值为 00:10:00。</span><span class="sxs-lookup"><span data-stu-id="7fa4d-126">The default is 00:10:00.</span></span>|  
|`sendTimeout`|<span data-ttu-id="7fa4d-127">一个 <xref:System.TimeSpan> 值，指定为完成发送操作提供的时间间隔。</span><span class="sxs-lookup"><span data-stu-id="7fa4d-127">A <xref:System.TimeSpan> value that specifies the interval of time provided for a send operation to complete.</span></span> <span data-ttu-id="7fa4d-128">此值应大于或等于 <xref:System.TimeSpan.Zero>。</span><span class="sxs-lookup"><span data-stu-id="7fa4d-128">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="7fa4d-129">默认值为 00:01:00。</span><span class="sxs-lookup"><span data-stu-id="7fa4d-129">The default is 00:01:00.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="7fa4d-130">子元素</span><span class="sxs-lookup"><span data-stu-id="7fa4d-130">Child Elements</span></span>  
 <span data-ttu-id="7fa4d-131">无。</span><span class="sxs-lookup"><span data-stu-id="7fa4d-131">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="7fa4d-132">父元素</span><span class="sxs-lookup"><span data-stu-id="7fa4d-132">Parent Elements</span></span>  
  
|<span data-ttu-id="7fa4d-133">元素</span><span class="sxs-lookup"><span data-stu-id="7fa4d-133">Element</span></span>|<span data-ttu-id="7fa4d-134">描述</span><span class="sxs-lookup"><span data-stu-id="7fa4d-134">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7fa4d-135">\<bindings></span><span class="sxs-lookup"><span data-stu-id="7fa4d-135">\<bindings></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md)|<span data-ttu-id="7fa4d-136">此元素包含标准绑定和自定义绑定的集合。</span><span class="sxs-lookup"><span data-stu-id="7fa4d-136">This element holds a collection of standard and custom bindings.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="7fa4d-137">请参阅</span><span class="sxs-lookup"><span data-stu-id="7fa4d-137">See also</span></span>

- <xref:System.ServiceModel.Description.MetadataExchangeBindings.CreateMexNamedPipeBinding%2A>
- <xref:System.ServiceModel.Configuration.MexNamedPipeBindingElement>
- [<span data-ttu-id="7fa4d-138">如何：发布使用配置文件服务的元数据</span><span class="sxs-lookup"><span data-stu-id="7fa4d-138">How to: Publish Metadata for a Service Using a Configuration File</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md)
- [<span data-ttu-id="7fa4d-139">通过自定义绑定发布和检索元数据</span><span class="sxs-lookup"><span data-stu-id="7fa4d-139">Publishing and Retrieving Metadata Over a Custom Binding</span></span>](../../../../../docs/framework/wcf/extending/publishing-and-retrieving-metadata-over-a-custom-binding.md)
- [<span data-ttu-id="7fa4d-140">元数据</span><span class="sxs-lookup"><span data-stu-id="7fa4d-140">Metadata</span></span>](../../../../../docs/framework/wcf/feature-details/metadata.md)
- [<span data-ttu-id="7fa4d-141">绑定</span><span class="sxs-lookup"><span data-stu-id="7fa4d-141">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="7fa4d-142">配置系统提供的绑定</span><span class="sxs-lookup"><span data-stu-id="7fa4d-142">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="7fa4d-143">使用绑定配置服务和客户端</span><span class="sxs-lookup"><span data-stu-id="7fa4d-143">Using Bindings to Configure Services and Clients</span></span>](../../../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="7fa4d-144">\<binding></span><span class="sxs-lookup"><span data-stu-id="7fa4d-144">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
