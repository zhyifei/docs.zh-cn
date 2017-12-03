---
title: '&lt;channelPoolSettings&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4755f3d3-4213-4c68-ae7f-45b67d744459
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: d48f3b304b337ba61f53bbd81cac8601bc68cb0a
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2017
---
# <a name="ltchannelpoolsettingsgt"></a><span data-ttu-id="ee803-102">&lt;channelPoolSettings&gt;</span><span class="sxs-lookup"><span data-stu-id="ee803-102">&lt;channelPoolSettings&gt;</span></span>
<span data-ttu-id="ee803-103">指定自定义绑定的通道池设置。</span><span class="sxs-lookup"><span data-stu-id="ee803-103">Specifies the channel pool settings for a custom binding.</span></span>  
  
 <span data-ttu-id="ee803-104">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="ee803-104">\<system.serviceModel></span></span>  
<span data-ttu-id="ee803-105">\<绑定 ></span><span class="sxs-lookup"><span data-stu-id="ee803-105">\<bindings></span></span>  
<span data-ttu-id="ee803-106">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="ee803-106">\<customBinding></span></span>  
<span data-ttu-id="ee803-107">\<绑定 ></span><span class="sxs-lookup"><span data-stu-id="ee803-107">\<binding></span></span>  
<span data-ttu-id="ee803-108">\<oneWay ></span><span class="sxs-lookup"><span data-stu-id="ee803-108">\<oneWay></span></span>  
<span data-ttu-id="ee803-109">\<channelPoolSettings ></span><span class="sxs-lookup"><span data-stu-id="ee803-109">\<channelPoolSettings></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ee803-110">语法</span><span class="sxs-lookup"><span data-stu-id="ee803-110">Syntax</span></span>  
  
```xml  
<channelPoolSettings  
    idleTimeout"TimeSpan"  
        leaseTimeout"TimeSpan"  
    maxOutboundConnectionsPerEndpopint="Integer" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ee803-111">特性和元素</span><span class="sxs-lookup"><span data-stu-id="ee803-111">Attributes and Elements</span></span>  
 <span data-ttu-id="ee803-112">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="ee803-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ee803-113">特性</span><span class="sxs-lookup"><span data-stu-id="ee803-113">Attributes</span></span>  
  
|<span data-ttu-id="ee803-114">特性</span><span class="sxs-lookup"><span data-stu-id="ee803-114">Attribute</span></span>|<span data-ttu-id="ee803-115">描述</span><span class="sxs-lookup"><span data-stu-id="ee803-115">Description</span></span>|  
|---------------|-----------------|  
|`idleTimeout`|<span data-ttu-id="ee803-116">一个值为正的 <xref:System.TimeSpan>，指定池中的通道在断开前可以空闲的最长时间。</span><span class="sxs-lookup"><span data-stu-id="ee803-116">A positive <xref:System.TimeSpan> that specifies the maximum time the channels in the pool can be idle before being disconnected.</span></span> <span data-ttu-id="ee803-117">默认值为 00:02:00。</span><span class="sxs-lookup"><span data-stu-id="ee803-117">The default is 00:02:00.</span></span>|  
|`leaseTimeout`|<span data-ttu-id="ee803-118"><xref:System.TimeSpan>，用于指定从通道返回池到通道关闭之间的时间间隔。</span><span class="sxs-lookup"><span data-stu-id="ee803-118">A <xref:System.TimeSpan> that specifies the interval of time after which a channel, when returned to the pool, is closed.</span></span> <span data-ttu-id="ee803-119">默认值为 00:10:00。</span><span class="sxs-lookup"><span data-stu-id="ee803-119">The default is 00:10:00.</span></span>|  
|`maxOutboundChannelsPerEndpoint`|<span data-ttu-id="ee803-120">一个正整数，指定对于每个远程端点可以存储在池中的通道的最大数目。</span><span class="sxs-lookup"><span data-stu-id="ee803-120">A positive integer that specifies the maximum number of channels that can be stored in the pool for each remote endpoint.</span></span> <span data-ttu-id="ee803-121">默认值为 10。</span><span class="sxs-lookup"><span data-stu-id="ee803-121">The default is 10.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ee803-122">子元素</span><span class="sxs-lookup"><span data-stu-id="ee803-122">Child Elements</span></span>  
 <span data-ttu-id="ee803-123">无。</span><span class="sxs-lookup"><span data-stu-id="ee803-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="ee803-124">父元素</span><span class="sxs-lookup"><span data-stu-id="ee803-124">Parent Elements</span></span>  
  
|<span data-ttu-id="ee803-125">元素</span><span class="sxs-lookup"><span data-stu-id="ee803-125">Element</span></span>|<span data-ttu-id="ee803-126">描述</span><span class="sxs-lookup"><span data-stu-id="ee803-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ee803-127">\<oneWay ></span><span class="sxs-lookup"><span data-stu-id="ee803-127">\<oneWay></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/oneway.md)|<span data-ttu-id="ee803-128">针对自定义绑定启用数据包路由。</span><span class="sxs-lookup"><span data-stu-id="ee803-128">Enables packet routing for a custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ee803-129">备注</span><span class="sxs-lookup"><span data-stu-id="ee803-129">Remarks</span></span>  
 <span data-ttu-id="ee803-130">配额用作一种策略机制，防止消耗过多资源。</span><span class="sxs-lookup"><span data-stu-id="ee803-130">Quotas are used as a policy mechanism to prevent the consumption of excessive resources.</span></span> <span data-ttu-id="ee803-131">它们可防止恶意或无意的拒绝服务 (DOS) 攻击。</span><span class="sxs-lookup"><span data-stu-id="ee803-131">They prevent Denial of Service (DOS) attacks that are either malicious or unintentional.</span></span> <span data-ttu-id="ee803-132">在设置自定义通道的通道配额时使用此元素。</span><span class="sxs-lookup"><span data-stu-id="ee803-132">Use this element when setting channel quotas on a custom channel.</span></span>  
  
 <span data-ttu-id="ee803-133">`ChannelPoolSettings` 指定三项配额：</span><span class="sxs-lookup"><span data-stu-id="ee803-133">`ChannelPoolSettings` specifies three quotas:</span></span>  
  
-   <span data-ttu-id="ee803-134">`idleTimeout` 配额用于减少通过长时间占用资源来对服务器实施的拒绝服务 (DOS) 攻击。</span><span class="sxs-lookup"><span data-stu-id="ee803-134">The `idleTimeout` quota is used to mitigate Denial of Service (DOS) attacks on the server that rely on tying up resources for an extended period of time.</span></span> <span data-ttu-id="ee803-135">在客户端，设置正确的值可增加与服务连接的可靠性。</span><span class="sxs-lookup"><span data-stu-id="ee803-135">On the client, setting the correct value can increase the reliability of connecting with the service.</span></span> <span data-ttu-id="ee803-136">默认值基于资源的保守适度分配。</span><span class="sxs-lookup"><span data-stu-id="ee803-136">The default value is based on a conservatively modest allocation of resources.</span></span> <span data-ttu-id="ee803-137">该值适用于开发环境和小型安装方案。</span><span class="sxs-lookup"><span data-stu-id="ee803-137">It is suitable for a development environment and small installation scenarios.</span></span> <span data-ttu-id="ee803-138">如果某个安装耗尽了资源或是连接受到限制，则无论是否还有其他资源可用，服务管理员都应检查该值。</span><span class="sxs-lookup"><span data-stu-id="ee803-138">Service administrators should review the value if an installation is running out of resources or if connections are being limited despite the availability of additional resources.</span></span>  
  
-   <span data-ttu-id="ee803-139">`leaseTimeout` 配额用于与负载平衡器的集成以及提高可靠性。</span><span class="sxs-lookup"><span data-stu-id="ee803-139">The `leaseTimeout` quota is used to for integration with load balancers and for improving reliability.</span></span> <span data-ttu-id="ee803-140">默认值基于资源的保守分配。</span><span class="sxs-lookup"><span data-stu-id="ee803-140">The default value is based on a conservative allocation of resources.</span></span> <span data-ttu-id="ee803-141">该值适用于开发环境和小型安装方案。</span><span class="sxs-lookup"><span data-stu-id="ee803-141">It is suitable for a development environment and small installation scenarios.</span></span> <span data-ttu-id="ee803-142">如果某个安装耗尽了资源或是连接受到限制，则无论是否还有其他资源可用，服务管理员都应检查该值。</span><span class="sxs-lookup"><span data-stu-id="ee803-142">Service administrators should review the value if an installation is running out of resources or if connections are being limited despite the availability of additional resources.</span></span>  
  
-   <span data-ttu-id="ee803-143">`maxOutboundChannelsPerEndpoint` 配额设置服务器与客户端上的缓存限制，用于提高可靠性。</span><span class="sxs-lookup"><span data-stu-id="ee803-143">The `maxOutboundChannelsPerEndpoint` quota sets cache limits on both the server and the client and is used to improve reliability.</span></span> <span data-ttu-id="ee803-144">其默认值基于资源的保守适度分配，适用于开发环境和小型安装方案。</span><span class="sxs-lookup"><span data-stu-id="ee803-144">The default value is based on a conservatively modest allocation of resources that is suitable for a development environment and small installation scenarios.</span></span> <span data-ttu-id="ee803-145">如果某个安装耗尽了资源或是连接受到限制，则无论是否还有其他资源可用，服务管理员都应检查该值。</span><span class="sxs-lookup"><span data-stu-id="ee803-145">Service administrators should review the value if an installation is running out of resources or if connections are being limited despite the availability of additional resources.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ee803-146">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ee803-146">See Also</span></span>  
 <xref:System.ServiceModel.Channels.OneWayBindingElement.ChannelPoolSettings%2A>  
 <xref:System.ServiceModel.Channels.ChannelPoolSettings>  
 <xref:System.ServiceModel.Configuration.OneWayElement.ChannelPoolSettings%2A>  
 <xref:System.ServiceModel.Configuration.ChannelPoolSettingsElement>  
 <xref:System.ServiceModel.Channels.CustomBinding>  
 [<span data-ttu-id="ee803-147">\<oneWay ></span><span class="sxs-lookup"><span data-stu-id="ee803-147">\<oneWay></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/oneway.md)  
 [<span data-ttu-id="ee803-148">绑定</span><span class="sxs-lookup"><span data-stu-id="ee803-148">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="ee803-149">扩展绑定</span><span class="sxs-lookup"><span data-stu-id="ee803-149">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)  
 [<span data-ttu-id="ee803-150">自定义绑定</span><span class="sxs-lookup"><span data-stu-id="ee803-150">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)  
 [<span data-ttu-id="ee803-151">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="ee803-151">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
