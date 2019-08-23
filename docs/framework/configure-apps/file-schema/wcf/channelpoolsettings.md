---
title: <channelPoolSettings>
ms.date: 03/30/2017
ms.assetid: 4755f3d3-4213-4c68-ae7f-45b67d744459
ms.openlocfilehash: dd81821c74678cae8602458fe796a72bf5d379e4
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69919557"
---
# <a name="channelpoolsettings"></a><span data-ttu-id="b138b-101">\<channelPoolSettings></span><span class="sxs-lookup"><span data-stu-id="b138b-101">\<channelPoolSettings></span></span>
<span data-ttu-id="b138b-102">指定自定义绑定的通道池设置。</span><span class="sxs-lookup"><span data-stu-id="b138b-102">Specifies the channel pool settings for a custom binding.</span></span>  
  
 <span data-ttu-id="b138b-103">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="b138b-103">\<system.serviceModel></span></span>  
<span data-ttu-id="b138b-104">\<bindings></span><span class="sxs-lookup"><span data-stu-id="b138b-104">\<bindings></span></span>  
<span data-ttu-id="b138b-105">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="b138b-105">\<customBinding></span></span>  
<span data-ttu-id="b138b-106">\<绑定 ></span><span class="sxs-lookup"><span data-stu-id="b138b-106">\<binding></span></span>  
<span data-ttu-id="b138b-107">\<oneWay></span><span class="sxs-lookup"><span data-stu-id="b138b-107">\<oneWay></span></span>  
<span data-ttu-id="b138b-108">\<channelPoolSettings></span><span class="sxs-lookup"><span data-stu-id="b138b-108">\<channelPoolSettings></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b138b-109">语法</span><span class="sxs-lookup"><span data-stu-id="b138b-109">Syntax</span></span>  
  
```xml  
<channelPoolSettings idleTimeout="TimeSpan"
                     leaseTimeout="TimeSpan"
                     maxOutboundConnectionsPerEndpoint="Integer" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b138b-110">特性和元素</span><span class="sxs-lookup"><span data-stu-id="b138b-110">Attributes and Elements</span></span>  
 <span data-ttu-id="b138b-111">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="b138b-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b138b-112">特性</span><span class="sxs-lookup"><span data-stu-id="b138b-112">Attributes</span></span>  
  
|<span data-ttu-id="b138b-113">特性</span><span class="sxs-lookup"><span data-stu-id="b138b-113">Attribute</span></span>|<span data-ttu-id="b138b-114">描述</span><span class="sxs-lookup"><span data-stu-id="b138b-114">Description</span></span>|  
|---------------|-----------------|  
|`idleTimeout`|<span data-ttu-id="b138b-115">一个值为正的 <xref:System.TimeSpan>，指定池中的通道在断开前可以空闲的最长时间。</span><span class="sxs-lookup"><span data-stu-id="b138b-115">A positive <xref:System.TimeSpan> that specifies the maximum time the channels in the pool can be idle before being disconnected.</span></span> <span data-ttu-id="b138b-116">默认值为 00:02:00。</span><span class="sxs-lookup"><span data-stu-id="b138b-116">The default is 00:02:00.</span></span>|  
|`leaseTimeout`|<span data-ttu-id="b138b-117"><xref:System.TimeSpan>，用于指定从通道返回池到通道关闭之间的时间间隔。</span><span class="sxs-lookup"><span data-stu-id="b138b-117">A <xref:System.TimeSpan> that specifies the interval of time after which a channel, when returned to the pool, is closed.</span></span> <span data-ttu-id="b138b-118">默认值为 00:10:00。</span><span class="sxs-lookup"><span data-stu-id="b138b-118">The default is 00:10:00.</span></span>|  
|`maxOutboundChannelsPerEndpoint`|<span data-ttu-id="b138b-119">一个正整数，指定对于每个远程端点可以存储在池中的通道的最大数目。</span><span class="sxs-lookup"><span data-stu-id="b138b-119">A positive integer that specifies the maximum number of channels that can be stored in the pool for each remote endpoint.</span></span> <span data-ttu-id="b138b-120">默认值为 10。</span><span class="sxs-lookup"><span data-stu-id="b138b-120">The default is 10.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b138b-121">子元素</span><span class="sxs-lookup"><span data-stu-id="b138b-121">Child Elements</span></span>  
 <span data-ttu-id="b138b-122">无。</span><span class="sxs-lookup"><span data-stu-id="b138b-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="b138b-123">父元素</span><span class="sxs-lookup"><span data-stu-id="b138b-123">Parent Elements</span></span>  
  
|<span data-ttu-id="b138b-124">元素</span><span class="sxs-lookup"><span data-stu-id="b138b-124">Element</span></span>|<span data-ttu-id="b138b-125">描述</span><span class="sxs-lookup"><span data-stu-id="b138b-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b138b-126">\<oneWay></span><span class="sxs-lookup"><span data-stu-id="b138b-126">\<oneWay></span></span>](oneway.md)|<span data-ttu-id="b138b-127">针对自定义绑定启用数据包路由。</span><span class="sxs-lookup"><span data-stu-id="b138b-127">Enables packet routing for a custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b138b-128">备注</span><span class="sxs-lookup"><span data-stu-id="b138b-128">Remarks</span></span>  
 <span data-ttu-id="b138b-129">配额用作一种策略机制，防止消耗过多资源。</span><span class="sxs-lookup"><span data-stu-id="b138b-129">Quotas are used as a policy mechanism to prevent the consumption of excessive resources.</span></span> <span data-ttu-id="b138b-130">它们可防止恶意或无意的拒绝服务 (DOS) 攻击。</span><span class="sxs-lookup"><span data-stu-id="b138b-130">They prevent Denial of Service (DOS) attacks that are either malicious or unintentional.</span></span> <span data-ttu-id="b138b-131">在设置自定义通道的通道配额时使用此元素。</span><span class="sxs-lookup"><span data-stu-id="b138b-131">Use this element when setting channel quotas on a custom channel.</span></span>  
  
 <span data-ttu-id="b138b-132">`ChannelPoolSettings` 指定三项配额：</span><span class="sxs-lookup"><span data-stu-id="b138b-132">`ChannelPoolSettings` specifies three quotas:</span></span>  
  
- <span data-ttu-id="b138b-133">`idleTimeout` 配额用于减少通过长时间占用资源来对服务器实施的拒绝服务 (DOS) 攻击。</span><span class="sxs-lookup"><span data-stu-id="b138b-133">The `idleTimeout` quota is used to mitigate Denial of Service (DOS) attacks on the server that rely on tying up resources for an extended period of time.</span></span> <span data-ttu-id="b138b-134">在客户端，设置正确的值可增加与服务连接的可靠性。</span><span class="sxs-lookup"><span data-stu-id="b138b-134">On the client, setting the correct value can increase the reliability of connecting with the service.</span></span> <span data-ttu-id="b138b-135">默认值基于资源的保守适度分配。</span><span class="sxs-lookup"><span data-stu-id="b138b-135">The default value is based on a conservatively modest allocation of resources.</span></span> <span data-ttu-id="b138b-136">该值适用于开发环境和小型安装方案。</span><span class="sxs-lookup"><span data-stu-id="b138b-136">It is suitable for a development environment and small installation scenarios.</span></span> <span data-ttu-id="b138b-137">如果某个安装耗尽了资源或是连接受到限制，则无论是否还有其他资源可用，服务管理员都应检查该值。</span><span class="sxs-lookup"><span data-stu-id="b138b-137">Service administrators should review the value if an installation is running out of resources or if connections are being limited despite the availability of additional resources.</span></span>  
  
- <span data-ttu-id="b138b-138">`leaseTimeout` 配额用于与负载均衡器的集成以及提高可靠性。</span><span class="sxs-lookup"><span data-stu-id="b138b-138">The `leaseTimeout` quota is used to for integration with load balancers and for improving reliability.</span></span> <span data-ttu-id="b138b-139">默认值基于资源的保守分配。</span><span class="sxs-lookup"><span data-stu-id="b138b-139">The default value is based on a conservative allocation of resources.</span></span> <span data-ttu-id="b138b-140">该值适用于开发环境和小型安装方案。</span><span class="sxs-lookup"><span data-stu-id="b138b-140">It is suitable for a development environment and small installation scenarios.</span></span> <span data-ttu-id="b138b-141">如果某个安装耗尽了资源或是连接受到限制，则无论是否还有其他资源可用，服务管理员都应检查该值。</span><span class="sxs-lookup"><span data-stu-id="b138b-141">Service administrators should review the value if an installation is running out of resources or if connections are being limited despite the availability of additional resources.</span></span>  
  
- <span data-ttu-id="b138b-142">`maxOutboundChannelsPerEndpoint` 配额设置服务器与客户端上的缓存限制，用于提高可靠性。</span><span class="sxs-lookup"><span data-stu-id="b138b-142">The `maxOutboundChannelsPerEndpoint` quota sets cache limits on both the server and the client and is used to improve reliability.</span></span> <span data-ttu-id="b138b-143">其默认值基于资源的保守适度分配，适用于开发环境和小型安装方案。</span><span class="sxs-lookup"><span data-stu-id="b138b-143">The default value is based on a conservatively modest allocation of resources that is suitable for a development environment and small installation scenarios.</span></span> <span data-ttu-id="b138b-144">如果某个安装耗尽了资源或是连接受到限制，则无论是否还有其他资源可用，服务管理员都应检查该值。</span><span class="sxs-lookup"><span data-stu-id="b138b-144">Service administrators should review the value if an installation is running out of resources or if connections are being limited despite the availability of additional resources.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b138b-145">请参阅</span><span class="sxs-lookup"><span data-stu-id="b138b-145">See also</span></span>

- <xref:System.ServiceModel.Channels.OneWayBindingElement.ChannelPoolSettings%2A>
- <xref:System.ServiceModel.Channels.ChannelPoolSettings>
- <xref:System.ServiceModel.Configuration.OneWayElement.ChannelPoolSettings%2A>
- <xref:System.ServiceModel.Configuration.ChannelPoolSettingsElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="b138b-146">\<oneWay></span><span class="sxs-lookup"><span data-stu-id="b138b-146">\<oneWay></span></span>](oneway.md)
- [<span data-ttu-id="b138b-147">绑定</span><span class="sxs-lookup"><span data-stu-id="b138b-147">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="b138b-148">扩展绑定</span><span class="sxs-lookup"><span data-stu-id="b138b-148">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="b138b-149">自定义绑定</span><span class="sxs-lookup"><span data-stu-id="b138b-149">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [<span data-ttu-id="b138b-150">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="b138b-150">\<customBinding></span></span>](custombinding.md)
