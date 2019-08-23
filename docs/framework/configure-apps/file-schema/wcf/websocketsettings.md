---
title: <webSocketSettings>
ms.date: 03/30/2017
ms.assetid: bbf97e02-8dd1-4922-acac-3cd33397b249
ms.openlocfilehash: 5c9dbec13dd0d71ba1b92ea971d067540013b6f9
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69940322"
---
# <a name="websocketsettings"></a><span data-ttu-id="8ce3d-101">\<webSocketSettings></span><span class="sxs-lookup"><span data-stu-id="8ce3d-101">\<webSocketSettings></span></span>
<span data-ttu-id="8ce3d-102">用来指定 Web Socket 设置的配置元素。</span><span class="sxs-lookup"><span data-stu-id="8ce3d-102">A configuration element used to specify Web Socket settings.</span></span>  
  
<span data-ttu-id="8ce3d-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="8ce3d-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="8ce3d-104">\<bindings></span><span class="sxs-lookup"><span data-stu-id="8ce3d-104">\<bindings></span></span>  
<span data-ttu-id="8ce3d-105">\<netHttpBinding></span><span class="sxs-lookup"><span data-stu-id="8ce3d-105">\<netHttpBinding></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8ce3d-106">语法</span><span class="sxs-lookup"><span data-stu-id="8ce3d-106">Syntax</span></span>  
  
```xml  
<netHttpBinding>
  <binding>
    <webSocketSettings createNotificationOnConnection="Boolean"
                       disablePayloadMasking="Boolean"
                       keepAliveInterval="TimeSpan"
                       maxPendingConnections="Integer"
                       receiveBufferSize="Integer"
                       sendBufferSize="Integer"
                       subProtocol="String"
                       transportUsage="WhenDuplex/Always/Never" />
  </binding>
</netHttpBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8ce3d-107">特性和元素</span><span class="sxs-lookup"><span data-stu-id="8ce3d-107">Attributes and Elements</span></span>  
 <span data-ttu-id="8ce3d-108">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="8ce3d-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8ce3d-109">特性</span><span class="sxs-lookup"><span data-stu-id="8ce3d-109">Attributes</span></span>  
  
|<span data-ttu-id="8ce3d-110">特性</span><span class="sxs-lookup"><span data-stu-id="8ce3d-110">Attribute</span></span>|<span data-ttu-id="8ce3d-111">描述</span><span class="sxs-lookup"><span data-stu-id="8ce3d-111">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="8ce3d-112">createNotificationOnConnection</span><span class="sxs-lookup"><span data-stu-id="8ce3d-112">createNotificationOnConnection</span></span>|<span data-ttu-id="8ce3d-113">指定是否在连接时发送通知。</span><span class="sxs-lookup"><span data-stu-id="8ce3d-113">Specifies whether a notification is sent upon connection.</span></span>|  
|<span data-ttu-id="8ce3d-114">disablePayloadMasking</span><span class="sxs-lookup"><span data-stu-id="8ce3d-114">disablePayloadMasking</span></span>|<span data-ttu-id="8ce3d-115">指定是否禁用 Web Socket 掩码。</span><span class="sxs-lookup"><span data-stu-id="8ce3d-115">Specifies whether Web Socket masking is disabled.</span></span>|  
|<span data-ttu-id="8ce3d-116">keepAliveInterval</span><span class="sxs-lookup"><span data-stu-id="8ce3d-116">keepAliveInterval</span></span>|<span data-ttu-id="8ce3d-117">指定保持活动状态的间隔。</span><span class="sxs-lookup"><span data-stu-id="8ce3d-117">Specifies the keep alive interval.</span></span>|  
|<span data-ttu-id="8ce3d-118">maxPendingConnections</span><span class="sxs-lookup"><span data-stu-id="8ce3d-118">maxPendingConnections</span></span>|<span data-ttu-id="8ce3d-119">指定服务上等待调度的最大连接数。</span><span class="sxs-lookup"><span data-stu-id="8ce3d-119">Specifies the maximum number of connections awaiting dispatch on the service.</span></span>|  
|<span data-ttu-id="8ce3d-120">receiveBufferSize</span><span class="sxs-lookup"><span data-stu-id="8ce3d-120">receiveBufferSize</span></span>|<span data-ttu-id="8ce3d-121">指定接收缓冲区的大小。</span><span class="sxs-lookup"><span data-stu-id="8ce3d-121">Specifies the size of the receive buffer.</span></span>|  
|<span data-ttu-id="8ce3d-122">sendBufferSize</span><span class="sxs-lookup"><span data-stu-id="8ce3d-122">sendBufferSize</span></span>|<span data-ttu-id="8ce3d-123">指定发送缓冲区的大小。</span><span class="sxs-lookup"><span data-stu-id="8ce3d-123">Specifies the size of the send buffer.</span></span>|  
|<span data-ttu-id="8ce3d-124">subProtocol</span><span class="sxs-lookup"><span data-stu-id="8ce3d-124">subProtocol</span></span>|<span data-ttu-id="8ce3d-125">指定 Web Socket 子协议。</span><span class="sxs-lookup"><span data-stu-id="8ce3d-125">Specifies the Web Socket subprotocol.</span></span>|  
|<span data-ttu-id="8ce3d-126">transportUsage</span><span class="sxs-lookup"><span data-stu-id="8ce3d-126">transportUsage</span></span>|<span data-ttu-id="8ce3d-127">指定何时使用 Web Socket。</span><span class="sxs-lookup"><span data-stu-id="8ce3d-127">Specifies when to use Web Sockets.</span></span>|  
  
## <a name="transportusage-attribute"></a><span data-ttu-id="8ce3d-128">transportUsage 特性</span><span class="sxs-lookup"><span data-stu-id="8ce3d-128">transportUsage Attribute</span></span>  
  
|<span data-ttu-id="8ce3d-129">值</span><span class="sxs-lookup"><span data-stu-id="8ce3d-129">Value</span></span>|<span data-ttu-id="8ce3d-130">描述</span><span class="sxs-lookup"><span data-stu-id="8ce3d-130">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="8ce3d-131">WhenDuplex</span><span class="sxs-lookup"><span data-stu-id="8ce3d-131">WhenDuplex</span></span>|<span data-ttu-id="8ce3d-132">如果为双工协定，则使用 Web Socket 协议。</span><span class="sxs-lookup"><span data-stu-id="8ce3d-132">Use the Web Socket protocol when the contract is duplex.</span></span>|  
|<span data-ttu-id="8ce3d-133">Always</span><span class="sxs-lookup"><span data-stu-id="8ce3d-133">Always</span></span>|<span data-ttu-id="8ce3d-134">始终使用 Web Socket 协议，而不管协定类型。</span><span class="sxs-lookup"><span data-stu-id="8ce3d-134">Always use the Web Socket protocol regardless of the contract.</span></span>|  
|<span data-ttu-id="8ce3d-135">Never</span><span class="sxs-lookup"><span data-stu-id="8ce3d-135">Never</span></span>|<span data-ttu-id="8ce3d-136">永远不使用 Web Socket 协议。</span><span class="sxs-lookup"><span data-stu-id="8ce3d-136">Never use the Web Socket protocol.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="8ce3d-137">子元素</span><span class="sxs-lookup"><span data-stu-id="8ce3d-137">Child Elements</span></span>  
 <span data-ttu-id="8ce3d-138">无</span><span class="sxs-lookup"><span data-stu-id="8ce3d-138">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="8ce3d-139">父元素</span><span class="sxs-lookup"><span data-stu-id="8ce3d-139">Parent Elements</span></span>  
  
|<span data-ttu-id="8ce3d-140">元素</span><span class="sxs-lookup"><span data-stu-id="8ce3d-140">Element</span></span>|<span data-ttu-id="8ce3d-141">描述</span><span class="sxs-lookup"><span data-stu-id="8ce3d-141">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="8ce3d-142">\<netHttpBinding></span><span class="sxs-lookup"><span data-stu-id="8ce3d-142">\<netHttpBinding></span></span>|<span data-ttu-id="8ce3d-143">指定 NetHttpBinding</span><span class="sxs-lookup"><span data-stu-id="8ce3d-143">Specifies the NetHttpBinding</span></span>|  
  
## <a name="example"></a><span data-ttu-id="8ce3d-144">示例</span><span class="sxs-lookup"><span data-stu-id="8ce3d-144">Example</span></span>  
 <span data-ttu-id="8ce3d-145">下面的示例演示如何使用\<s > 元素。</span><span class="sxs-lookup"><span data-stu-id="8ce3d-145">The following example shows how to use the \<webSocketSettings> element.</span></span>  
  
```xml  
<netHttpBinding>
  <binding>
    <webSocketSettings createNotificationOnConnection="true"
                       disablePayloadMasking="false"
                       keepAliveInterval="00:10:00"
                       maxPendingConnections="100"
                       receiveBufferSize="1000"
                       sendBufferSize="1000"
                       subProtocol="Soap"
                       transportUsage="WhenDuplex/Always/Never" />
  </binding>
</netHttpBinding>
```  
  
## <a name="see-also"></a><span data-ttu-id="8ce3d-146">请参阅</span><span class="sxs-lookup"><span data-stu-id="8ce3d-146">See also</span></span>

- <xref:System.ServiceModel.Channels.Binding>
- <xref:System.ServiceModel.Channels.BindingElement>
- <xref:System.ServiceModel.BasicHttpBinding>
- <xref:System.ServiceModel.Configuration.BasicHttpBindingElement>
- [<span data-ttu-id="8ce3d-147">绑定</span><span class="sxs-lookup"><span data-stu-id="8ce3d-147">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="8ce3d-148">配置系统提供的绑定</span><span class="sxs-lookup"><span data-stu-id="8ce3d-148">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="8ce3d-149">使用绑定配置服务和客户端</span><span class="sxs-lookup"><span data-stu-id="8ce3d-149">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="8ce3d-150">\<binding></span><span class="sxs-lookup"><span data-stu-id="8ce3d-150">\<binding></span></span>](../../../misc/binding.md)
