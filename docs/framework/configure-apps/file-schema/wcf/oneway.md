---
title: <oneWay>
ms.date: 03/30/2017
ms.assetid: 00e67e0e-77c0-4695-9138-c0997b0e5f3c
ms.openlocfilehash: a5c773ea91de882920775ac8dc0ecc1da68a6c9f
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/07/2019
ms.locfileid: "73738788"
---
# <a name="oneway"></a><span data-ttu-id="ddbb5-101">\<单向 ></span><span class="sxs-lookup"><span data-stu-id="ddbb5-101">\<oneWay></span></span>
<span data-ttu-id="ddbb5-102">对自定义绑定启用数据包路由并使用单向方法。</span><span class="sxs-lookup"><span data-stu-id="ddbb5-102">Enables packet routing and the use of one-way methods for a custom binding.</span></span>  
  
<span data-ttu-id="ddbb5-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="ddbb5-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="ddbb5-104">\<system &nbsp; &nbsp;[ **>** ](system-servicemodel.md) </span><span class="sxs-lookup"><span data-stu-id="ddbb5-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="ddbb5-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<绑定**](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="ddbb5-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="ddbb5-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<customBinding >** ](custombinding.md)</span><span class="sxs-lookup"><span data-stu-id="ddbb5-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)</span></span>\
<span data-ttu-id="ddbb5-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<绑定 >** </span><span class="sxs-lookup"><span data-stu-id="ddbb5-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="ddbb5-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<单向 >**</span><span class="sxs-lookup"><span data-stu-id="ddbb5-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<oneWay>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ddbb5-109">语法</span><span class="sxs-lookup"><span data-stu-id="ddbb5-109">Syntax</span></span>  
  
```xml  
<oneWay packetRoutable="Boolean">
  <channelPoolSettings idleTimeout="TimeSpan"
                       leaseTimeout="TimeSpan"
                       maxOutboundConnectionsPerEndpoint="Integer" />
</oneWay>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ddbb5-110">特性和元素</span><span class="sxs-lookup"><span data-stu-id="ddbb5-110">Attributes and Elements</span></span>  
 <span data-ttu-id="ddbb5-111">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="ddbb5-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ddbb5-112">特性</span><span class="sxs-lookup"><span data-stu-id="ddbb5-112">Attributes</span></span>  
  
|<span data-ttu-id="ddbb5-113">特性</span><span class="sxs-lookup"><span data-stu-id="ddbb5-113">Attribute</span></span>|<span data-ttu-id="ddbb5-114">描述</span><span class="sxs-lookup"><span data-stu-id="ddbb5-114">Description</span></span>|  
|---------------|-----------------|  
|`packetRoutable`|<span data-ttu-id="ddbb5-115">一个布尔值，指定是否启用数据包路由。</span><span class="sxs-lookup"><span data-stu-id="ddbb5-115">A Boolean value that specifies whether packet routing is enabled.</span></span> <span data-ttu-id="ddbb5-116">默认值为 `false`。</span><span class="sxs-lookup"><span data-stu-id="ddbb5-116">The default is `false`.</span></span>|  
|`MaxAcceptedChannels`|<span data-ttu-id="ddbb5-117">一个整数，指定可接受的最大通道数。</span><span class="sxs-lookup"><span data-stu-id="ddbb5-117">An integer that specifies the maximum number of channels that can be accepted.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ddbb5-118">子元素</span><span class="sxs-lookup"><span data-stu-id="ddbb5-118">Child Elements</span></span>  
  
|<span data-ttu-id="ddbb5-119">元素</span><span class="sxs-lookup"><span data-stu-id="ddbb5-119">Element</span></span>|<span data-ttu-id="ddbb5-120">描述</span><span class="sxs-lookup"><span data-stu-id="ddbb5-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ddbb5-121">\<channelPoolSettings ></span><span class="sxs-lookup"><span data-stu-id="ddbb5-121">\<channelPoolSettings></span></span>](channelpoolsettings.md)|<span data-ttu-id="ddbb5-122">一个 <xref:System.ServiceModel.Configuration.ChannelPoolSettingsElement> 对象，包含当前通道的通道池的属性。</span><span class="sxs-lookup"><span data-stu-id="ddbb5-122">A <xref:System.ServiceModel.Configuration.ChannelPoolSettingsElement> object that contains properties of the channel pool for the current channel.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="ddbb5-123">父元素</span><span class="sxs-lookup"><span data-stu-id="ddbb5-123">Parent Elements</span></span>  
  
|<span data-ttu-id="ddbb5-124">元素</span><span class="sxs-lookup"><span data-stu-id="ddbb5-124">Element</span></span>|<span data-ttu-id="ddbb5-125">描述</span><span class="sxs-lookup"><span data-stu-id="ddbb5-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ddbb5-126">\<binding ></span><span class="sxs-lookup"><span data-stu-id="ddbb5-126">\<binding></span></span>](bindings.md)|<span data-ttu-id="ddbb5-127">定义自定义绑定的所有绑定功能。</span><span class="sxs-lookup"><span data-stu-id="ddbb5-127">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ddbb5-128">备注</span><span class="sxs-lookup"><span data-stu-id="ddbb5-128">Remarks</span></span>  
 <span data-ttu-id="ddbb5-129">若要启用数据包路由，必须使用此元素提供的单向转换层。</span><span class="sxs-lookup"><span data-stu-id="ddbb5-129">To enable packet routing, a one-way conversion layer is required, which this element provides.</span></span> <span data-ttu-id="ddbb5-130">用户可以创建一个自定义绑定，将此绑定置于具有会话功能或请求/答复传输的上层，使之可进行数据包路由。</span><span class="sxs-lookup"><span data-stu-id="ddbb5-130">A user can create a custom binding that layers this binding over a session-aware or request-reply transport to make it packet routable.</span></span> <span data-ttu-id="ddbb5-131">如果希望以更自然的方式公开单向方法，则此元素也十分有用。</span><span class="sxs-lookup"><span data-stu-id="ddbb5-131">This element is also useful when you want to expose one-way methods in a more native fashion.</span></span> <span data-ttu-id="ddbb5-132">在这一层上可应用更多的转换，如复合双工和可靠消息。</span><span class="sxs-lookup"><span data-stu-id="ddbb5-132">More transformations can be applied over this layer, such as Composite Duplex and Reliable Messaging.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ddbb5-133">请参阅</span><span class="sxs-lookup"><span data-stu-id="ddbb5-133">See also</span></span>

- <xref:System.ServiceModel.Channels.OneWayBindingElement>
- <xref:System.ServiceModel.Configuration.OneWayElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="ddbb5-134">绑定</span><span class="sxs-lookup"><span data-stu-id="ddbb5-134">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="ddbb5-135">扩展绑定</span><span class="sxs-lookup"><span data-stu-id="ddbb5-135">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="ddbb5-136">自定义绑定</span><span class="sxs-lookup"><span data-stu-id="ddbb5-136">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [<span data-ttu-id="ddbb5-137">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="ddbb5-137">\<customBinding></span></span>](custombinding.md)
