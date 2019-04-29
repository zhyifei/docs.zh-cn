---
title: <oneWay>
ms.date: 03/30/2017
ms.assetid: 00e67e0e-77c0-4695-9138-c0997b0e5f3c
ms.openlocfilehash: bfda2b9d7b3aa5219a3e4c344347d3b10419a7bd
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61783482"
---
# <a name="oneway"></a><span data-ttu-id="af07c-101">\<oneWay></span><span class="sxs-lookup"><span data-stu-id="af07c-101">\<oneWay></span></span>
<span data-ttu-id="af07c-102">对自定义绑定启用数据包路由并使用单向方法。</span><span class="sxs-lookup"><span data-stu-id="af07c-102">Enables packet routing and the use of one-way methods for a custom binding.</span></span>  
  
 <span data-ttu-id="af07c-103">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="af07c-103">\<system.serviceModel></span></span>  
<span data-ttu-id="af07c-104">\<bindings></span><span class="sxs-lookup"><span data-stu-id="af07c-104">\<bindings></span></span>  
<span data-ttu-id="af07c-105">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="af07c-105">\<customBinding></span></span>  
<span data-ttu-id="af07c-106">\<binding></span><span class="sxs-lookup"><span data-stu-id="af07c-106">\<binding></span></span>  
<span data-ttu-id="af07c-107">\<oneWay></span><span class="sxs-lookup"><span data-stu-id="af07c-107">\<oneWay></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="af07c-108">语法</span><span class="sxs-lookup"><span data-stu-id="af07c-108">Syntax</span></span>  
  
```xml  
<oneWay packetRoutable="Boolean">
  <channelPoolSettings idleTimeout="TimeSpan"
                       leaseTimeout="TimeSpan"
                       maxOutboundConnectionsPerEndpopint="Integer" />
</oneWay>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="af07c-109">特性和元素</span><span class="sxs-lookup"><span data-stu-id="af07c-109">Attributes and Elements</span></span>  
 <span data-ttu-id="af07c-110">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="af07c-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="af07c-111">特性</span><span class="sxs-lookup"><span data-stu-id="af07c-111">Attributes</span></span>  
  
|<span data-ttu-id="af07c-112">特性</span><span class="sxs-lookup"><span data-stu-id="af07c-112">Attribute</span></span>|<span data-ttu-id="af07c-113">描述</span><span class="sxs-lookup"><span data-stu-id="af07c-113">Description</span></span>|  
|---------------|-----------------|  
|`packetRoutable`|<span data-ttu-id="af07c-114">一个布尔值，指定是否启用数据包路由。</span><span class="sxs-lookup"><span data-stu-id="af07c-114">A Boolean value that specifies whether packet routing is enabled.</span></span> <span data-ttu-id="af07c-115">默认值为 `false`。</span><span class="sxs-lookup"><span data-stu-id="af07c-115">The default is `false`.</span></span>|  
|`MaxAcceptedChannels`|<span data-ttu-id="af07c-116">一个整数，指定可接受的最大通道数。</span><span class="sxs-lookup"><span data-stu-id="af07c-116">An integer that specifies the maximum number of channels that can be accepted.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="af07c-117">子元素</span><span class="sxs-lookup"><span data-stu-id="af07c-117">Child Elements</span></span>  
  
|<span data-ttu-id="af07c-118">元素</span><span class="sxs-lookup"><span data-stu-id="af07c-118">Element</span></span>|<span data-ttu-id="af07c-119">描述</span><span class="sxs-lookup"><span data-stu-id="af07c-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="af07c-120">\<channelPoolSettings></span><span class="sxs-lookup"><span data-stu-id="af07c-120">\<channelPoolSettings></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/channelpoolsettings.md)|<span data-ttu-id="af07c-121">一个 <xref:System.ServiceModel.Configuration.ChannelPoolSettingsElement> 对象，包含当前通道的通道池的属性。</span><span class="sxs-lookup"><span data-stu-id="af07c-121">A <xref:System.ServiceModel.Configuration.ChannelPoolSettingsElement> object that contains properties of the channel pool for the current channel.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="af07c-122">父元素</span><span class="sxs-lookup"><span data-stu-id="af07c-122">Parent Elements</span></span>  
  
|<span data-ttu-id="af07c-123">元素</span><span class="sxs-lookup"><span data-stu-id="af07c-123">Element</span></span>|<span data-ttu-id="af07c-124">描述</span><span class="sxs-lookup"><span data-stu-id="af07c-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="af07c-125">\<binding></span><span class="sxs-lookup"><span data-stu-id="af07c-125">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="af07c-126">定义自定义绑定的所有绑定功能。</span><span class="sxs-lookup"><span data-stu-id="af07c-126">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="af07c-127">备注</span><span class="sxs-lookup"><span data-stu-id="af07c-127">Remarks</span></span>  
 <span data-ttu-id="af07c-128">若要启用数据包路由，必须使用此元素提供的单向转换层。</span><span class="sxs-lookup"><span data-stu-id="af07c-128">To enable packet routing, a one-way conversion layer is required, which this element provides.</span></span> <span data-ttu-id="af07c-129">用户可以创建一个自定义绑定，将此绑定置于具有会话功能或请求/答复传输的上层，使之可进行数据包路由。</span><span class="sxs-lookup"><span data-stu-id="af07c-129">A user can create a custom binding that layers this binding over a session-aware or request-reply transport to make it packet routable.</span></span> <span data-ttu-id="af07c-130">如果希望以更自然的方式公开单向方法，则此元素也十分有用。</span><span class="sxs-lookup"><span data-stu-id="af07c-130">This element is also useful when you want to expose one-way methods in a more native fashion.</span></span> <span data-ttu-id="af07c-131">在这一层上可应用更多的转换，如复合双工和可靠消息。</span><span class="sxs-lookup"><span data-stu-id="af07c-131">More transformations can be applied over this layer, such as Composite Duplex and Reliable Messaging.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="af07c-132">请参阅</span><span class="sxs-lookup"><span data-stu-id="af07c-132">See also</span></span>

- <xref:System.ServiceModel.Channels.OneWayBindingElement>
- <xref:System.ServiceModel.Configuration.OneWayElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="af07c-133">绑定</span><span class="sxs-lookup"><span data-stu-id="af07c-133">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="af07c-134">扩展绑定</span><span class="sxs-lookup"><span data-stu-id="af07c-134">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)
- [<span data-ttu-id="af07c-135">自定义绑定</span><span class="sxs-lookup"><span data-stu-id="af07c-135">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)
- [<span data-ttu-id="af07c-136">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="af07c-136">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
