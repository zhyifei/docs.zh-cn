---
title: <net.tcp>
ms.date: 03/30/2017
ms.assetid: 8bc2f2be-11c1-4bab-9018-1d21ae568d94
ms.openlocfilehash: 589bae5d1f91e0424eb19cee62fe758aa7846191
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59166512"
---
# <a name="nettcp"></a><span data-ttu-id="96bde-102">\<net.tcp></span><span class="sxs-lookup"><span data-stu-id="96bde-102">\<net.tcp></span></span>
<span data-ttu-id="96bde-103">指定允许多个进程共享同一 TCP 端口的 NET.TCP 端口共享服务的配置设置。</span><span class="sxs-lookup"><span data-stu-id="96bde-103">Specifies configuration settings for the NET.TCP Port Sharing Service, which allows multiple processes to share the same TCP port.</span></span>  
  
 <span data-ttu-id="96bde-104">\<system.serviceModel.activation></span><span class="sxs-lookup"><span data-stu-id="96bde-104">\<system.serviceModel.activation></span></span>  
<span data-ttu-id="96bde-105">\<net.tcp></span><span class="sxs-lookup"><span data-stu-id="96bde-105">\<net.tcp></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="96bde-106">语法</span><span class="sxs-lookup"><span data-stu-id="96bde-106">Syntax</span></span>  
  
```xml  
<configuration>
  <system.serviceModel.activation>
    <net.tcp listenBacklog="Integer"
             maxPendingAccepts="Integer"
             maxPendingConnections="Integer"
             receiveTimeout="TimeSpan"
             teredoEnabled="Boolean">
      <allowAccounts>
        <!-- LocalSystem account -->
        <add securityIdentifier="S-1-5-18"/>
        <!-- LocalService account -->
        <add securityIdentifier="S-1-5-19"/>
        <!-- Administrators account -->
        <add securityIdentifier="S-1-5-20"/>
        <!-- Network Service account -->
        <add securityIdentifier="S-1-5-32-544" />
        <!-- IIS_IUSRS account (Vista only)-->
        <add securityIdentifier="S-1-5-32-568"/>
      </allowAccounts>
    </net.tcp>
  </system.serviceModel.activation>
</configuration>
```  
  
## <a name="type"></a><span data-ttu-id="96bde-107">类型</span><span class="sxs-lookup"><span data-stu-id="96bde-107">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="96bde-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="96bde-108">Attributes and Elements</span></span>  
 <span data-ttu-id="96bde-109">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="96bde-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="96bde-110">特性</span><span class="sxs-lookup"><span data-stu-id="96bde-110">Attributes</span></span>  
  
|<span data-ttu-id="96bde-111">特性</span><span class="sxs-lookup"><span data-stu-id="96bde-111">Attribute</span></span>|<span data-ttu-id="96bde-112">描述</span><span class="sxs-lookup"><span data-stu-id="96bde-112">Description</span></span>|  
|---------------|-----------------|  
|`listenBacklog`|<span data-ttu-id="96bde-113">一个整数，指定从共享连接接受但仍未调度给 Windows Communication Foundation (WCF) 服务的最大未完成连接。</span><span class="sxs-lookup"><span data-stu-id="96bde-113">An integer that specifies the maximum outstanding connections that are accepted from the shared connection, but are not yet dispatched to Windows Communication Foundation (WCF) services.</span></span> <span data-ttu-id="96bde-114">默认值为 10。</span><span class="sxs-lookup"><span data-stu-id="96bde-114">The default is 10.</span></span>|  
|`maxPendingAccepts`|<span data-ttu-id="96bde-115">一个整数，指定共享服务侦听终结点上的最大未完成并发接受线程数。</span><span class="sxs-lookup"><span data-stu-id="96bde-115">An integer that specifies the maximum outstanding concurrent accepting threads on the listening endpoint for the sharing service.</span></span> <span data-ttu-id="96bde-116">默认值为 2。</span><span class="sxs-lookup"><span data-stu-id="96bde-116">The default is 2.</span></span>|  
|`MaxPendingConnections`|<span data-ttu-id="96bde-117">侦听器可以拥有的正在等待应用程序接受的最大连接数。</span><span class="sxs-lookup"><span data-stu-id="96bde-117">The maximum number of connections that the listener can have waiting to be accepted by the application.</span></span> <span data-ttu-id="96bde-118">超出此配额值时，新的传入连接会被丢弃而不是等待接受。</span><span class="sxs-lookup"><span data-stu-id="96bde-118">When this quota value is exceeded, new incoming connections are dropped rather than waiting to be accepted.</span></span> <span data-ttu-id="96bde-119">连接功能（如消息安全）可能会使客户端打开多个连接。</span><span class="sxs-lookup"><span data-stu-id="96bde-119">Connection features such as message security can cause a client to open more than one connection.</span></span> <span data-ttu-id="96bde-120">在设置此配额值时，服务管理员应该考虑这些额外的连接。</span><span class="sxs-lookup"><span data-stu-id="96bde-120">Service administrators should account for these additional connections when setting this quota value.</span></span> <span data-ttu-id="96bde-121">默认值为 10。</span><span class="sxs-lookup"><span data-stu-id="96bde-121">The default is 10.</span></span>|  
|`receiveTimeout`|<span data-ttu-id="96bde-122"><xref:System.TimeSpan>，它将为读取组帧数据并执行来自基础连接的连接调度指定超时值。</span><span class="sxs-lookup"><span data-stu-id="96bde-122">A <xref:System.TimeSpan> that specifies the timeout for reading the framing data and performing connection dispatching from the underlining connections.</span></span> <span data-ttu-id="96bde-123">默认值为“00:00:10”。</span><span class="sxs-lookup"><span data-stu-id="96bde-123">The default is "00:00:10".</span></span>|  
|`teredoEnabled`|<span data-ttu-id="96bde-124">一个布尔值，该值指示端口共享服务是否使用 Microsoft Teredo 服务代表 WCF 服务的 TCP 端口上进行侦听。</span><span class="sxs-lookup"><span data-stu-id="96bde-124">A Boolean value that indicates whether the port sharing service uses Microsoft Teredo service to listen on TCP ports on behalf of WCF services.</span></span> <span data-ttu-id="96bde-125">默认值为 `false`。</span><span class="sxs-lookup"><span data-stu-id="96bde-125">The default is `false`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="96bde-126">子元素</span><span class="sxs-lookup"><span data-stu-id="96bde-126">Child Elements</span></span>  
  
|<span data-ttu-id="96bde-127">元素</span><span class="sxs-lookup"><span data-stu-id="96bde-127">Element</span></span>|<span data-ttu-id="96bde-128">描述</span><span class="sxs-lookup"><span data-stu-id="96bde-128">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="96bde-129">\<allowAccounts></span><span class="sxs-lookup"><span data-stu-id="96bde-129">\<allowAccounts></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/allowaccounts.md)|<span data-ttu-id="96bde-130">包含的配置元素的集合`securityIdentifier`属性指定的进程的承载 WCF 服务并被授予对共享服务的连接访问权限的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="96bde-130">A collection of configuration elements that contain a `securityIdentifier` attribute to specify user accounts for processes that host WCF services, and are granted connection access to the sharing service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="96bde-131">父元素</span><span class="sxs-lookup"><span data-stu-id="96bde-131">Parent Elements</span></span>  
  
|<span data-ttu-id="96bde-132">元素</span><span class="sxs-lookup"><span data-stu-id="96bde-132">Element</span></span>|<span data-ttu-id="96bde-133">描述</span><span class="sxs-lookup"><span data-stu-id="96bde-133">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="96bde-134">\<system.serviceModel.activation></span><span class="sxs-lookup"><span data-stu-id="96bde-134">\<system.serviceModel.activation></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel-activation.md)|<span data-ttu-id="96bde-135">包含侦听器进程 SMSvcHost.exe 的配置设置。</span><span class="sxs-lookup"><span data-stu-id="96bde-135">Contains configuration settings for the listener process SMSvcHost.exe.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="96bde-136">备注</span><span class="sxs-lookup"><span data-stu-id="96bde-136">Remarks</span></span>  
 <span data-ttu-id="96bde-137">端口共享的详细信息，请参阅[Net.TCP 端口共享](../../../../../docs/framework/wcf/feature-details/net-tcp-port-sharing.md)。</span><span class="sxs-lookup"><span data-stu-id="96bde-137">For more information on port sharing, see [Net.TCP Port Sharing](../../../../../docs/framework/wcf/feature-details/net-tcp-port-sharing.md).</span></span> <span data-ttu-id="96bde-138">若要了解如何配置端口共享服务，请参阅[配置 Net.TCP 端口共享服务](../../../../../docs/framework/wcf/feature-details/configuring-the-net-tcp-port-sharing-service.md)。</span><span class="sxs-lookup"><span data-stu-id="96bde-138">To understand how to configure the port sharing service, see [Configuring the Net.TCP Port Sharing Service](../../../../../docs/framework/wcf/feature-details/configuring-the-net-tcp-port-sharing-service.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="96bde-139">请参阅</span><span class="sxs-lookup"><span data-stu-id="96bde-139">See also</span></span>

- <xref:System.ServiceModel.Activation.Configuration.NetTcpSection>
- [<span data-ttu-id="96bde-140">Net.TCP 端口共享</span><span class="sxs-lookup"><span data-stu-id="96bde-140">Net.TCP Port Sharing</span></span>](../../../../../docs/framework/wcf/feature-details/net-tcp-port-sharing.md)
- [<span data-ttu-id="96bde-141">配置 Net.TCP 端口共享服务</span><span class="sxs-lookup"><span data-stu-id="96bde-141">Configuring the Net.TCP Port Sharing Service</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-the-net-tcp-port-sharing-service.md)
