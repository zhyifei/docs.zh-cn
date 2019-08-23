---
title: <net.tcp>
ms.date: 03/30/2017
ms.assetid: 8bc2f2be-11c1-4bab-9018-1d21ae568d94
ms.openlocfilehash: 63cef2b85aa57b5c1c0e0add1794ebedc73d96c1
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69933054"
---
# <a name="nettcp"></a><span data-ttu-id="da3c2-102">\<net.tcp></span><span class="sxs-lookup"><span data-stu-id="da3c2-102">\<net.tcp></span></span>
<span data-ttu-id="da3c2-103">指定允许多个进程共享同一 TCP 端口的 NET.TCP 端口共享服务的配置设置。</span><span class="sxs-lookup"><span data-stu-id="da3c2-103">Specifies configuration settings for the NET.TCP Port Sharing Service, which allows multiple processes to share the same TCP port.</span></span>  
  
 <span data-ttu-id="da3c2-104">\<system.serviceModel.activation></span><span class="sxs-lookup"><span data-stu-id="da3c2-104">\<system.serviceModel.activation></span></span>  
<span data-ttu-id="da3c2-105">\<net.tcp></span><span class="sxs-lookup"><span data-stu-id="da3c2-105">\<net.tcp></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="da3c2-106">语法</span><span class="sxs-lookup"><span data-stu-id="da3c2-106">Syntax</span></span>  
  
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
  
## <a name="type"></a><span data-ttu-id="da3c2-107">类型</span><span class="sxs-lookup"><span data-stu-id="da3c2-107">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="da3c2-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="da3c2-108">Attributes and Elements</span></span>  
 <span data-ttu-id="da3c2-109">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="da3c2-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="da3c2-110">特性</span><span class="sxs-lookup"><span data-stu-id="da3c2-110">Attributes</span></span>  
  
|<span data-ttu-id="da3c2-111">特性</span><span class="sxs-lookup"><span data-stu-id="da3c2-111">Attribute</span></span>|<span data-ttu-id="da3c2-112">描述</span><span class="sxs-lookup"><span data-stu-id="da3c2-112">Description</span></span>|  
|---------------|-----------------|  
|`listenBacklog`|<span data-ttu-id="da3c2-113">一个整数, 指定已从共享连接接受但尚未调度到 Windows Communication Foundation (WCF) 服务的最大未处理连接数。</span><span class="sxs-lookup"><span data-stu-id="da3c2-113">An integer that specifies the maximum outstanding connections that are accepted from the shared connection, but are not yet dispatched to Windows Communication Foundation (WCF) services.</span></span> <span data-ttu-id="da3c2-114">默认值为 10。</span><span class="sxs-lookup"><span data-stu-id="da3c2-114">The default is 10.</span></span>|  
|`maxPendingAccepts`|<span data-ttu-id="da3c2-115">一个整数，指定共享服务侦听终结点上的最大未完成并发接受线程数。</span><span class="sxs-lookup"><span data-stu-id="da3c2-115">An integer that specifies the maximum outstanding concurrent accepting threads on the listening endpoint for the sharing service.</span></span> <span data-ttu-id="da3c2-116">默认值为 2。</span><span class="sxs-lookup"><span data-stu-id="da3c2-116">The default is 2.</span></span>|  
|`MaxPendingConnections`|<span data-ttu-id="da3c2-117">侦听器可以拥有的正在等待应用程序接受的最大连接数。</span><span class="sxs-lookup"><span data-stu-id="da3c2-117">The maximum number of connections that the listener can have waiting to be accepted by the application.</span></span> <span data-ttu-id="da3c2-118">超出此配额值时，新的传入连接会被丢弃而不是等待接受。</span><span class="sxs-lookup"><span data-stu-id="da3c2-118">When this quota value is exceeded, new incoming connections are dropped rather than waiting to be accepted.</span></span> <span data-ttu-id="da3c2-119">连接功能（如消息安全）可能会使客户端打开多个连接。</span><span class="sxs-lookup"><span data-stu-id="da3c2-119">Connection features such as message security can cause a client to open more than one connection.</span></span> <span data-ttu-id="da3c2-120">在设置此配额值时，服务管理员应该考虑这些额外的连接。</span><span class="sxs-lookup"><span data-stu-id="da3c2-120">Service administrators should account for these additional connections when setting this quota value.</span></span> <span data-ttu-id="da3c2-121">默认值为 10。</span><span class="sxs-lookup"><span data-stu-id="da3c2-121">The default is 10.</span></span>|  
|`receiveTimeout`|<span data-ttu-id="da3c2-122"><xref:System.TimeSpan>，它将为读取组帧数据并执行来自基础连接的连接调度指定超时值。</span><span class="sxs-lookup"><span data-stu-id="da3c2-122">A <xref:System.TimeSpan> that specifies the timeout for reading the framing data and performing connection dispatching from the underlining connections.</span></span> <span data-ttu-id="da3c2-123">默认值为“00:00:10”。</span><span class="sxs-lookup"><span data-stu-id="da3c2-123">The default is "00:00:10".</span></span>|  
|`teredoEnabled`|<span data-ttu-id="da3c2-124">一个布尔值, 指示端口共享服务是否使用 Microsoft Teredo 服务代表 WCF 服务在 TCP 端口上进行侦听。</span><span class="sxs-lookup"><span data-stu-id="da3c2-124">A Boolean value that indicates whether the port sharing service uses Microsoft Teredo service to listen on TCP ports on behalf of WCF services.</span></span> <span data-ttu-id="da3c2-125">默认值为 `false`。</span><span class="sxs-lookup"><span data-stu-id="da3c2-125">The default is `false`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="da3c2-126">子元素</span><span class="sxs-lookup"><span data-stu-id="da3c2-126">Child Elements</span></span>  
  
|<span data-ttu-id="da3c2-127">元素</span><span class="sxs-lookup"><span data-stu-id="da3c2-127">Element</span></span>|<span data-ttu-id="da3c2-128">描述</span><span class="sxs-lookup"><span data-stu-id="da3c2-128">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="da3c2-129">\<allowAccounts></span><span class="sxs-lookup"><span data-stu-id="da3c2-129">\<allowAccounts></span></span>](allowaccounts.md)|<span data-ttu-id="da3c2-130">一个配置元素的集合, 这些元素`securityIdentifier`包含一个属性, 用于为承载 WCF 服务并被授予对共享服务的连接访问权限的进程指定用户帐户。</span><span class="sxs-lookup"><span data-stu-id="da3c2-130">A collection of configuration elements that contain a `securityIdentifier` attribute to specify user accounts for processes that host WCF services, and are granted connection access to the sharing service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="da3c2-131">父元素</span><span class="sxs-lookup"><span data-stu-id="da3c2-131">Parent Elements</span></span>  
  
|<span data-ttu-id="da3c2-132">元素</span><span class="sxs-lookup"><span data-stu-id="da3c2-132">Element</span></span>|<span data-ttu-id="da3c2-133">描述</span><span class="sxs-lookup"><span data-stu-id="da3c2-133">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="da3c2-134">\<system.serviceModel.activation></span><span class="sxs-lookup"><span data-stu-id="da3c2-134">\<system.serviceModel.activation></span></span>](system-servicemodel-activation.md)|<span data-ttu-id="da3c2-135">包含侦听器进程 SMSvcHost.exe 的配置设置。</span><span class="sxs-lookup"><span data-stu-id="da3c2-135">Contains configuration settings for the listener process SMSvcHost.exe.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="da3c2-136">备注</span><span class="sxs-lookup"><span data-stu-id="da3c2-136">Remarks</span></span>  
 <span data-ttu-id="da3c2-137">有关端口共享的详细信息, 请参阅[Net.tcp 端口共享](../../../wcf/feature-details/net-tcp-port-sharing.md)。</span><span class="sxs-lookup"><span data-stu-id="da3c2-137">For more information on port sharing, see [Net.TCP Port Sharing](../../../wcf/feature-details/net-tcp-port-sharing.md).</span></span> <span data-ttu-id="da3c2-138">若要了解如何配置端口共享服务, 请参阅[配置 Net.tcp 端口共享服务](../../../wcf/feature-details/configuring-the-net-tcp-port-sharing-service.md)。</span><span class="sxs-lookup"><span data-stu-id="da3c2-138">To understand how to configure the port sharing service, see [Configuring the Net.TCP Port Sharing Service](../../../wcf/feature-details/configuring-the-net-tcp-port-sharing-service.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="da3c2-139">请参阅</span><span class="sxs-lookup"><span data-stu-id="da3c2-139">See also</span></span>

- <xref:System.ServiceModel.Activation.Configuration.NetTcpSection>
- [<span data-ttu-id="da3c2-140">Net.TCP 端口共享</span><span class="sxs-lookup"><span data-stu-id="da3c2-140">Net.TCP Port Sharing</span></span>](../../../wcf/feature-details/net-tcp-port-sharing.md)
- [<span data-ttu-id="da3c2-141">配置 Net.TCP 端口共享服务</span><span class="sxs-lookup"><span data-stu-id="da3c2-141">Configuring the Net.TCP Port Sharing Service</span></span>](../../../wcf/feature-details/configuring-the-net-tcp-port-sharing-service.md)
