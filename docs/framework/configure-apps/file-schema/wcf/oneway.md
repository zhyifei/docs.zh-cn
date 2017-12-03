---
title: '&lt;oneWay&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 00e67e0e-77c0-4695-9138-c0997b0e5f3c
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: be70abe745879b5d6f6e8cdde802a6403f90174b
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2017
---
# <a name="ltonewaygt"></a><span data-ttu-id="73da6-102">&lt;oneWay&gt;</span><span class="sxs-lookup"><span data-stu-id="73da6-102">&lt;oneWay&gt;</span></span>
<span data-ttu-id="73da6-103">对自定义绑定启用数据包路由并使用单向方法。</span><span class="sxs-lookup"><span data-stu-id="73da6-103">Enables packet routing and the use of one-way methods for a custom binding.</span></span>  
  
 <span data-ttu-id="73da6-104">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="73da6-104">\<system.serviceModel></span></span>  
<span data-ttu-id="73da6-105">\<绑定 ></span><span class="sxs-lookup"><span data-stu-id="73da6-105">\<bindings></span></span>  
<span data-ttu-id="73da6-106">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="73da6-106">\<customBinding></span></span>  
<span data-ttu-id="73da6-107">\<绑定 ></span><span class="sxs-lookup"><span data-stu-id="73da6-107">\<binding></span></span>  
<span data-ttu-id="73da6-108">\<oneWay ></span><span class="sxs-lookup"><span data-stu-id="73da6-108">\<oneWay></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="73da6-109">语法</span><span class="sxs-lookup"><span data-stu-id="73da6-109">Syntax</span></span>  
  
```xml  
<oneWay packetRoutable="Boolean">  
        <channelPoolSettings  
           idleTimeout"TimeSpan"  
          leaseTimeout"TimeSpan"  
          maxOutboundConnectionsPerEndpopint="Integer" />  
```  
  
```xml  
</oneWay>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="73da6-110">特性和元素</span><span class="sxs-lookup"><span data-stu-id="73da6-110">Attributes and Elements</span></span>  
 <span data-ttu-id="73da6-111">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="73da6-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="73da6-112">特性</span><span class="sxs-lookup"><span data-stu-id="73da6-112">Attributes</span></span>  
  
|<span data-ttu-id="73da6-113">特性</span><span class="sxs-lookup"><span data-stu-id="73da6-113">Attribute</span></span>|<span data-ttu-id="73da6-114">描述</span><span class="sxs-lookup"><span data-stu-id="73da6-114">Description</span></span>|  
|---------------|-----------------|  
|`packetRoutable`|<span data-ttu-id="73da6-115">一个布尔值，指定是否启用数据包路由。</span><span class="sxs-lookup"><span data-stu-id="73da6-115">A Boolean value that specifies whether packet routing is enabled.</span></span> <span data-ttu-id="73da6-116">默认值为 `false`。</span><span class="sxs-lookup"><span data-stu-id="73da6-116">The default is `false`.</span></span>|  
|`MaxAcceptedChannels`|<span data-ttu-id="73da6-117">一个整数，指定可接受的最大通道数。</span><span class="sxs-lookup"><span data-stu-id="73da6-117">An integer that specifies the maximum number of channels that can be accepted.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="73da6-118">子元素</span><span class="sxs-lookup"><span data-stu-id="73da6-118">Child Elements</span></span>  
  
|<span data-ttu-id="73da6-119">元素</span><span class="sxs-lookup"><span data-stu-id="73da6-119">Element</span></span>|<span data-ttu-id="73da6-120">描述</span><span class="sxs-lookup"><span data-stu-id="73da6-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="73da6-121">\<channelPoolSettings ></span><span class="sxs-lookup"><span data-stu-id="73da6-121">\<channelPoolSettings></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/channelpoolsettings.md)|<span data-ttu-id="73da6-122">一个 <xref:System.ServiceModel.Configuration.ChannelPoolSettingsElement> 对象，包含当前通道的通道池的属性。</span><span class="sxs-lookup"><span data-stu-id="73da6-122">A <xref:System.ServiceModel.Configuration.ChannelPoolSettingsElement> object that contains properties of the channel pool for the current channel.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="73da6-123">父元素</span><span class="sxs-lookup"><span data-stu-id="73da6-123">Parent Elements</span></span>  
  
|<span data-ttu-id="73da6-124">元素</span><span class="sxs-lookup"><span data-stu-id="73da6-124">Element</span></span>|<span data-ttu-id="73da6-125">描述</span><span class="sxs-lookup"><span data-stu-id="73da6-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="73da6-126">\<绑定 ></span><span class="sxs-lookup"><span data-stu-id="73da6-126">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="73da6-127">定义自定义绑定的所有绑定功能。</span><span class="sxs-lookup"><span data-stu-id="73da6-127">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="73da6-128">备注</span><span class="sxs-lookup"><span data-stu-id="73da6-128">Remarks</span></span>  
 <span data-ttu-id="73da6-129">若要启用数据包路由，必须使用此元素提供的单向转换层。</span><span class="sxs-lookup"><span data-stu-id="73da6-129">To enable packet routing, a one-way conversion layer is required, which this element provides.</span></span> <span data-ttu-id="73da6-130">用户可以创建一个自定义绑定，将此绑定置于具有会话功能或请求/答复传输的上层，使之可进行数据包路由。</span><span class="sxs-lookup"><span data-stu-id="73da6-130">A user can create a custom binding that layers this binding over a session-aware or request-reply transport to make it packet routable.</span></span> <span data-ttu-id="73da6-131">如果希望以更自然的方式公开单向方法，则此元素也十分有用。</span><span class="sxs-lookup"><span data-stu-id="73da6-131">This element is also useful when you want to expose one-way methods in a more native fashion.</span></span> <span data-ttu-id="73da6-132">在这一层上可应用更多的转换，如复合双工和可靠消息。</span><span class="sxs-lookup"><span data-stu-id="73da6-132">More transformations can be applied over this layer, such as Composite Duplex and Reliable Messaging.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="73da6-133">另请参阅</span><span class="sxs-lookup"><span data-stu-id="73da6-133">See Also</span></span>  
 <xref:System.ServiceModel.Channels.OneWayBindingElement>  
 <xref:System.ServiceModel.Configuration.OneWayElement>  
 <xref:System.ServiceModel.Channels.CustomBinding>  
 [<span data-ttu-id="73da6-134">绑定</span><span class="sxs-lookup"><span data-stu-id="73da6-134">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="73da6-135">扩展绑定</span><span class="sxs-lookup"><span data-stu-id="73da6-135">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)  
 [<span data-ttu-id="73da6-136">自定义绑定</span><span class="sxs-lookup"><span data-stu-id="73da6-136">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)  
 [<span data-ttu-id="73da6-137">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="73da6-137">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
