---
title: <mexTcpBinding>
ms.date: 03/30/2017
ms.assetid: 01baba8d-d784-4255-9ea2-7afff1482bf0
ms.openlocfilehash: 8d0ae2a1848eaf28c2e408542b8209cf968de4c1
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74430301"
---
# <a name="mextcpbinding"></a><span data-ttu-id="4ca3f-101">\<mexTcpBinding></span><span class="sxs-lookup"><span data-stu-id="4ca3f-101">\<mexTcpBinding></span></span>
<span data-ttu-id="4ca3f-102">指定用于通过 TCP 进行的 WS-MetadataExchange (WS-MEX) 消息交换的绑定的设置。</span><span class="sxs-lookup"><span data-stu-id="4ca3f-102">Specifies the settings for a binding used for the WS-MetadataExchange (WS-MEX) message exchange over TCP.</span></span>  
  
<span data-ttu-id="4ca3f-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="4ca3f-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="4ca3f-104">&nbsp;&nbsp;[ **\<system.serviceModel>** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="4ca3f-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="4ca3f-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<bindings>** ](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="4ca3f-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="4ca3f-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<mexTcpBinding>**</span><span class="sxs-lookup"><span data-stu-id="4ca3f-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<mexTcpBinding>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4ca3f-107">语法</span><span class="sxs-lookup"><span data-stu-id="4ca3f-107">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4ca3f-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="4ca3f-108">Attributes and Elements</span></span>  
 <span data-ttu-id="4ca3f-109">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="4ca3f-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4ca3f-110">特性</span><span class="sxs-lookup"><span data-stu-id="4ca3f-110">Attributes</span></span>  
  
|<span data-ttu-id="4ca3f-111">特性</span><span class="sxs-lookup"><span data-stu-id="4ca3f-111">Attribute</span></span>|<span data-ttu-id="4ca3f-112">描述</span><span class="sxs-lookup"><span data-stu-id="4ca3f-112">Description</span></span>|  
|---------------|-----------------|  
|`closeTimeout`|<span data-ttu-id="4ca3f-113">一个 <xref:System.TimeSpan> 值，指定为完成关闭操作提供的时间间隔。</span><span class="sxs-lookup"><span data-stu-id="4ca3f-113">A <xref:System.TimeSpan> value that specifies the interval of time provided for a close operation to complete.</span></span> <span data-ttu-id="4ca3f-114">此值应大于或等于 <xref:System.TimeSpan.Zero>。</span><span class="sxs-lookup"><span data-stu-id="4ca3f-114">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="4ca3f-115">默认值为 00:01:00。</span><span class="sxs-lookup"><span data-stu-id="4ca3f-115">The default is 00:01:00.</span></span>|  
|`name`|<span data-ttu-id="4ca3f-116">一个包含绑定的配置名称的字符串。</span><span class="sxs-lookup"><span data-stu-id="4ca3f-116">A string that contains the configuration name of the binding.</span></span> <span data-ttu-id="4ca3f-117">因为此值用作绑定的标识，所以它应该是唯一的。</span><span class="sxs-lookup"><span data-stu-id="4ca3f-117">This value should be unique because it is used as an identification for the binding.</span></span> <span data-ttu-id="4ca3f-118">Starting with .NET Framework 4, bindings and behaviors are not required to have a name.</span><span class="sxs-lookup"><span data-stu-id="4ca3f-118">Starting with .NET Framework 4, bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="4ca3f-119">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="4ca3f-119">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>|  
|`openTimeout`|<span data-ttu-id="4ca3f-120">一个 <xref:System.TimeSpan> 值，指定为完成打开操作提供的时间间隔。</span><span class="sxs-lookup"><span data-stu-id="4ca3f-120">A <xref:System.TimeSpan> value that specifies the interval of time provided for an open operation to complete.</span></span> <span data-ttu-id="4ca3f-121">此值应大于或等于 <xref:System.TimeSpan.Zero>。</span><span class="sxs-lookup"><span data-stu-id="4ca3f-121">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="4ca3f-122">默认值为 00:01:00。</span><span class="sxs-lookup"><span data-stu-id="4ca3f-122">The default is 00:01:00.</span></span>|  
|`receiveTimeout`|<span data-ttu-id="4ca3f-123">一个 <xref:System.TimeSpan> 值，指定为完成接收操作提供的时间间隔。</span><span class="sxs-lookup"><span data-stu-id="4ca3f-123">A <xref:System.TimeSpan> value that specifies the interval of time provided for a receive operation to complete.</span></span> <span data-ttu-id="4ca3f-124">此值应大于或等于 <xref:System.TimeSpan.Zero>。</span><span class="sxs-lookup"><span data-stu-id="4ca3f-124">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="4ca3f-125">默认值为 00:10:00。</span><span class="sxs-lookup"><span data-stu-id="4ca3f-125">The default is 00:10:00.</span></span>|  
|`sendTimeout`|<span data-ttu-id="4ca3f-126">一个 <xref:System.TimeSpan> 值，指定为完成发送操作提供的时间间隔。</span><span class="sxs-lookup"><span data-stu-id="4ca3f-126">A <xref:System.TimeSpan> value that specifies the interval of time provided for a send operation to complete.</span></span> <span data-ttu-id="4ca3f-127">此值应大于或等于 <xref:System.TimeSpan.Zero>。</span><span class="sxs-lookup"><span data-stu-id="4ca3f-127">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="4ca3f-128">默认值为 00:01:00。</span><span class="sxs-lookup"><span data-stu-id="4ca3f-128">The default is 00:01:00.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="4ca3f-129">子元素</span><span class="sxs-lookup"><span data-stu-id="4ca3f-129">Child Elements</span></span>  
 <span data-ttu-id="4ca3f-130">无。</span><span class="sxs-lookup"><span data-stu-id="4ca3f-130">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="4ca3f-131">父元素</span><span class="sxs-lookup"><span data-stu-id="4ca3f-131">Parent Elements</span></span>  
  
|<span data-ttu-id="4ca3f-132">元素</span><span class="sxs-lookup"><span data-stu-id="4ca3f-132">Element</span></span>|<span data-ttu-id="4ca3f-133">描述</span><span class="sxs-lookup"><span data-stu-id="4ca3f-133">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4ca3f-134">\<bindings></span><span class="sxs-lookup"><span data-stu-id="4ca3f-134">\<bindings></span></span>](bindings.md)|<span data-ttu-id="4ca3f-135">此元素包含标准绑定和自定义绑定的集合。</span><span class="sxs-lookup"><span data-stu-id="4ca3f-135">This element holds a collection of standard and custom bindings.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="4ca3f-136">请参阅</span><span class="sxs-lookup"><span data-stu-id="4ca3f-136">See also</span></span>

- <xref:System.ServiceModel.Configuration.MexTcpBindingElement>
- <xref:System.ServiceModel.Description.MetadataExchangeBindings.CreateMexTcpBinding%2A>
- [<span data-ttu-id="4ca3f-137">如何：使用配置文件发布服务的元数据</span><span class="sxs-lookup"><span data-stu-id="4ca3f-137">How to: Publish Metadata for a Service Using a Configuration File</span></span>](../../../wcf/feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md)
- [<span data-ttu-id="4ca3f-138">通过自定义绑定发布和检索元数据</span><span class="sxs-lookup"><span data-stu-id="4ca3f-138">Publishing and Retrieving Metadata Over a Custom Binding</span></span>](../../../wcf/extending/publishing-and-retrieving-metadata-over-a-custom-binding.md)
- [<span data-ttu-id="4ca3f-139">元数据</span><span class="sxs-lookup"><span data-stu-id="4ca3f-139">Metadata</span></span>](../../../wcf/feature-details/metadata.md)
- [<span data-ttu-id="4ca3f-140">绑定</span><span class="sxs-lookup"><span data-stu-id="4ca3f-140">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="4ca3f-141">配置系统提供的绑定</span><span class="sxs-lookup"><span data-stu-id="4ca3f-141">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="4ca3f-142">使用绑定配置服务和客户端</span><span class="sxs-lookup"><span data-stu-id="4ca3f-142">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="4ca3f-143">\<binding></span><span class="sxs-lookup"><span data-stu-id="4ca3f-143">\<binding></span></span>](bindings.md)
