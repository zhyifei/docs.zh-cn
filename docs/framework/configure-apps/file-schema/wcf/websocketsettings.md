---
title: '&lt;webSocketSettings&gt;'
ms.date: 03/30/2017
ms.assetid: bbf97e02-8dd1-4922-acac-3cd33397b249
ms.openlocfilehash: e5f34dca83c8d3d08d27fb72bee5af2a89ac6b9f
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/01/2018
ms.locfileid: "43416423"
---
# <a name="ltwebsocketsettingsgt"></a><span data-ttu-id="a19c5-102">&lt;webSocketSettings&gt;</span><span class="sxs-lookup"><span data-stu-id="a19c5-102">&lt;webSocketSettings&gt;</span></span>
<span data-ttu-id="a19c5-103">用来指定 Web Socket 设置的配置元素。</span><span class="sxs-lookup"><span data-stu-id="a19c5-103">A configuration element used to specify Web Socket settings.</span></span>  
  
<span data-ttu-id="a19c5-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="a19c5-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="a19c5-105">\<绑定 ></span><span class="sxs-lookup"><span data-stu-id="a19c5-105">\<bindings></span></span>  
<span data-ttu-id="a19c5-106">\<netHttpBinding></span><span class="sxs-lookup"><span data-stu-id="a19c5-106">\<netHttpBinding></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a19c5-107">语法</span><span class="sxs-lookup"><span data-stu-id="a19c5-107">Syntax</span></span>  
  
```xml  
<netHttpBinding>  
  <binding>   
    <webSocketSettings createNotificationOnConnection="boolean" 
                       disablePayloadMasking="boolean" 
                       keepAliveInterval="TimeSpan" 
                       maxPendingConnections="Integer" 
                       receiveBufferSize="Integer" 
                       sendBufferSize="Integer" 
                       subProtocol="String" 
                       transportUsage="WhenDuplex/Always/Never"/>
  </binding>  
</netHttpBinding>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a19c5-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="a19c5-108">Attributes and Elements</span></span>  
 <span data-ttu-id="a19c5-109">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="a19c5-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a19c5-110">特性</span><span class="sxs-lookup"><span data-stu-id="a19c5-110">Attributes</span></span>  
  
|<span data-ttu-id="a19c5-111">特性</span><span class="sxs-lookup"><span data-stu-id="a19c5-111">Attribute</span></span>|<span data-ttu-id="a19c5-112">描述</span><span class="sxs-lookup"><span data-stu-id="a19c5-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="a19c5-113">createNotificationOnConnection</span><span class="sxs-lookup"><span data-stu-id="a19c5-113">createNotificationOnConnection</span></span>|<span data-ttu-id="a19c5-114">指定是否在连接时发送通知。</span><span class="sxs-lookup"><span data-stu-id="a19c5-114">Specifies whether a notification is sent upon connection.</span></span>|  
|<span data-ttu-id="a19c5-115">disablePayloadMasking</span><span class="sxs-lookup"><span data-stu-id="a19c5-115">disablePayloadMasking</span></span>|<span data-ttu-id="a19c5-116">指定是否禁用 Web Socket 掩码。</span><span class="sxs-lookup"><span data-stu-id="a19c5-116">Specifies whether Web Socket masking is disabled.</span></span>|  
|<span data-ttu-id="a19c5-117">keepAliveInterval</span><span class="sxs-lookup"><span data-stu-id="a19c5-117">keepAliveInterval</span></span>|<span data-ttu-id="a19c5-118">指定保持活动状态的间隔。</span><span class="sxs-lookup"><span data-stu-id="a19c5-118">Specifies the keep alive interval.</span></span>|  
|<span data-ttu-id="a19c5-119">maxPendingConnections</span><span class="sxs-lookup"><span data-stu-id="a19c5-119">maxPendingConnections</span></span>|<span data-ttu-id="a19c5-120">指定服务上等待调度的最大连接数。</span><span class="sxs-lookup"><span data-stu-id="a19c5-120">Specifies the maximum number of connections awaiting dispatch on the service.</span></span>|  
|<span data-ttu-id="a19c5-121">receiveBufferSize</span><span class="sxs-lookup"><span data-stu-id="a19c5-121">receiveBufferSize</span></span>|<span data-ttu-id="a19c5-122">指定接收缓冲区的大小。</span><span class="sxs-lookup"><span data-stu-id="a19c5-122">Specifies the size of the receive buffer.</span></span>|  
|<span data-ttu-id="a19c5-123">sendBufferSize</span><span class="sxs-lookup"><span data-stu-id="a19c5-123">sendBufferSize</span></span>|<span data-ttu-id="a19c5-124">指定发送缓冲区的大小。</span><span class="sxs-lookup"><span data-stu-id="a19c5-124">Specifies the size of the send buffer.</span></span>|  
|<span data-ttu-id="a19c5-125">subProtocol</span><span class="sxs-lookup"><span data-stu-id="a19c5-125">subProtocol</span></span>|<span data-ttu-id="a19c5-126">指定 Web Socket 子协议。</span><span class="sxs-lookup"><span data-stu-id="a19c5-126">Specifies the Web Socket subprotocol.</span></span>|  
|<span data-ttu-id="a19c5-127">transportUsage</span><span class="sxs-lookup"><span data-stu-id="a19c5-127">transportUsage</span></span>|<span data-ttu-id="a19c5-128">指定何时使用 Web Socket。</span><span class="sxs-lookup"><span data-stu-id="a19c5-128">Specifies when to use Web Sockets.</span></span>|  
  
## <a name="transportusage-attribute"></a><span data-ttu-id="a19c5-129">transportUsage 特性</span><span class="sxs-lookup"><span data-stu-id="a19c5-129">transportUsage Attribute</span></span>  
  
|<span data-ttu-id="a19c5-130">值</span><span class="sxs-lookup"><span data-stu-id="a19c5-130">Value</span></span>|<span data-ttu-id="a19c5-131">描述</span><span class="sxs-lookup"><span data-stu-id="a19c5-131">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="a19c5-132">WhenDuplex</span><span class="sxs-lookup"><span data-stu-id="a19c5-132">WhenDuplex</span></span>|<span data-ttu-id="a19c5-133">如果为双工协定，则使用 Web Socket 协议。</span><span class="sxs-lookup"><span data-stu-id="a19c5-133">Use the Web Socket protocol when the contract is duplex.</span></span>|  
|<span data-ttu-id="a19c5-134">Always</span><span class="sxs-lookup"><span data-stu-id="a19c5-134">Always</span></span>|<span data-ttu-id="a19c5-135">始终使用 Web Socket 协议，而不管协定类型。</span><span class="sxs-lookup"><span data-stu-id="a19c5-135">Always use the Web Socket protocol regardless of the contract.</span></span>|  
|<span data-ttu-id="a19c5-136">Never</span><span class="sxs-lookup"><span data-stu-id="a19c5-136">Never</span></span>|<span data-ttu-id="a19c5-137">永远不使用 Web Socket 协议。</span><span class="sxs-lookup"><span data-stu-id="a19c5-137">Never use the Web Socket protocol.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a19c5-138">子元素</span><span class="sxs-lookup"><span data-stu-id="a19c5-138">Child Elements</span></span>  
 <span data-ttu-id="a19c5-139">无</span><span class="sxs-lookup"><span data-stu-id="a19c5-139">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="a19c5-140">父元素</span><span class="sxs-lookup"><span data-stu-id="a19c5-140">Parent Elements</span></span>  
  
|<span data-ttu-id="a19c5-141">元素</span><span class="sxs-lookup"><span data-stu-id="a19c5-141">Element</span></span>|<span data-ttu-id="a19c5-142">描述</span><span class="sxs-lookup"><span data-stu-id="a19c5-142">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="a19c5-143">\<netHttpBinding></span><span class="sxs-lookup"><span data-stu-id="a19c5-143">\<netHttpBinding></span></span>|<span data-ttu-id="a19c5-144">指定 NetHttpBinding</span><span class="sxs-lookup"><span data-stu-id="a19c5-144">Specifies the NetHttpBinding</span></span>|  
  
## <a name="example"></a><span data-ttu-id="a19c5-145">示例</span><span class="sxs-lookup"><span data-stu-id="a19c5-145">Example</span></span>  
 <span data-ttu-id="a19c5-146">下面的示例演示如何使用\<webSocketSettings > 元素。</span><span class="sxs-lookup"><span data-stu-id="a19c5-146">The following example shows how to use the \<webSocketSettings> element.</span></span>  
  
```xml  
<netHttpBinding>  
        <binding>  
          <webSocketSettings createNotificationOnConnection="true"  
                              disablePayloadMasking="false  
                              keepAliveInterval="00:10:00"  
                              maxPendingConnections="100"  
                              receiveBufferSize="1000"  
                              sendBufferSize="1000"  
                              subProtocol="Soap"  
                              transportUsage="WhenDuplex/Always/Never"/>  
  
        </binding>  
      </netHttpBinding>  
```  
  
## <a name="see-also"></a><span data-ttu-id="a19c5-147">请参阅</span><span class="sxs-lookup"><span data-stu-id="a19c5-147">See Also</span></span>  
 <xref:System.ServiceModel.Channels.Binding>  
 <xref:System.ServiceModel.Channels.BindingElement>  
 <xref:System.ServiceModel.BasicHttpBinding>  
 <xref:System.ServiceModel.Configuration.BasicHttpBindingElement>  
 [<span data-ttu-id="a19c5-148">绑定</span><span class="sxs-lookup"><span data-stu-id="a19c5-148">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="a19c5-149">配置系统提供的绑定</span><span class="sxs-lookup"><span data-stu-id="a19c5-149">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="a19c5-150">使用绑定来配置 Windows Communication Foundation 服务和客户端</span><span class="sxs-lookup"><span data-stu-id="a19c5-150">Using Bindings to Configure Windows Communication Foundation Services and Clients</span></span>](https://msdn.microsoft.com/library/bd8b277b-932f-472f-a42a-b02bb5257dfb)  
 [<span data-ttu-id="a19c5-151">\<绑定 ></span><span class="sxs-lookup"><span data-stu-id="a19c5-151">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
