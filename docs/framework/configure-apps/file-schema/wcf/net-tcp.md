---
title: <net.tcp>
ms.date: 03/30/2017
ms.assetid: 8bc2f2be-11c1-4bab-9018-1d21ae568d94
ms.openlocfilehash: 4a3a17655f5469fe84c0b684ebdac9848bbfba84
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/06/2019
ms.locfileid: "70397698"
---
# <a name="nettcp"></a><span data-ttu-id="1c2a3-102">\<net.tcp></span><span class="sxs-lookup"><span data-stu-id="1c2a3-102">\<net.tcp></span></span>
<span data-ttu-id="1c2a3-103">指定允许多个进程共享同一 TCP 端口的 NET.TCP 端口共享服务的配置设置。</span><span class="sxs-lookup"><span data-stu-id="1c2a3-103">Specifies configuration settings for the NET.TCP Port Sharing Service, which allows multiple processes to share the same TCP port.</span></span>  
  
<span data-ttu-id="1c2a3-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="1c2a3-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="1c2a3-105">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel-activation.md)</span><span class="sxs-lookup"><span data-stu-id="1c2a3-105">&nbsp;&nbsp;[**\<system.serviceModel.activation>**](system-servicemodel-activation.md)</span></span>\
<span data-ttu-id="1c2a3-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<net.tcp >**</span><span class="sxs-lookup"><span data-stu-id="1c2a3-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<net.tcp>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1c2a3-107">语法</span><span class="sxs-lookup"><span data-stu-id="1c2a3-107">Syntax</span></span>  
  
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
  
## <a name="type"></a><span data-ttu-id="1c2a3-108">类型</span><span class="sxs-lookup"><span data-stu-id="1c2a3-108">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1c2a3-109">特性和元素</span><span class="sxs-lookup"><span data-stu-id="1c2a3-109">Attributes and Elements</span></span>  
 <span data-ttu-id="1c2a3-110">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="1c2a3-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1c2a3-111">特性</span><span class="sxs-lookup"><span data-stu-id="1c2a3-111">Attributes</span></span>  
  
|<span data-ttu-id="1c2a3-112">特性</span><span class="sxs-lookup"><span data-stu-id="1c2a3-112">Attribute</span></span>|<span data-ttu-id="1c2a3-113">描述</span><span class="sxs-lookup"><span data-stu-id="1c2a3-113">Description</span></span>|  
|---------------|-----------------|  
|`listenBacklog`|<span data-ttu-id="1c2a3-114">一个整数，指定已从共享连接接受但尚未调度到 Windows Communication Foundation （WCF）服务的最大未处理连接数。</span><span class="sxs-lookup"><span data-stu-id="1c2a3-114">An integer that specifies the maximum outstanding connections that are accepted from the shared connection, but are not yet dispatched to Windows Communication Foundation (WCF) services.</span></span> <span data-ttu-id="1c2a3-115">默认值为 10。</span><span class="sxs-lookup"><span data-stu-id="1c2a3-115">The default is 10.</span></span>|  
|`maxPendingAccepts`|<span data-ttu-id="1c2a3-116">一个整数，指定共享服务侦听终结点上的最大未完成并发接受线程数。</span><span class="sxs-lookup"><span data-stu-id="1c2a3-116">An integer that specifies the maximum outstanding concurrent accepting threads on the listening endpoint for the sharing service.</span></span> <span data-ttu-id="1c2a3-117">默认值为 2。</span><span class="sxs-lookup"><span data-stu-id="1c2a3-117">The default is 2.</span></span>|  
|`MaxPendingConnections`|<span data-ttu-id="1c2a3-118">侦听器可以拥有的正在等待应用程序接受的最大连接数。</span><span class="sxs-lookup"><span data-stu-id="1c2a3-118">The maximum number of connections that the listener can have waiting to be accepted by the application.</span></span> <span data-ttu-id="1c2a3-119">超出此配额值时，新的传入连接会被丢弃而不是等待接受。</span><span class="sxs-lookup"><span data-stu-id="1c2a3-119">When this quota value is exceeded, new incoming connections are dropped rather than waiting to be accepted.</span></span> <span data-ttu-id="1c2a3-120">连接功能（如消息安全）可能会使客户端打开多个连接。</span><span class="sxs-lookup"><span data-stu-id="1c2a3-120">Connection features such as message security can cause a client to open more than one connection.</span></span> <span data-ttu-id="1c2a3-121">在设置此配额值时，服务管理员应该考虑这些额外的连接。</span><span class="sxs-lookup"><span data-stu-id="1c2a3-121">Service administrators should account for these additional connections when setting this quota value.</span></span> <span data-ttu-id="1c2a3-122">默认值为 10。</span><span class="sxs-lookup"><span data-stu-id="1c2a3-122">The default is 10.</span></span>|  
|`receiveTimeout`|<span data-ttu-id="1c2a3-123"><xref:System.TimeSpan>，它将为读取组帧数据并执行来自基础连接的连接调度指定超时值。</span><span class="sxs-lookup"><span data-stu-id="1c2a3-123">A <xref:System.TimeSpan> that specifies the timeout for reading the framing data and performing connection dispatching from the underlining connections.</span></span> <span data-ttu-id="1c2a3-124">默认值为“00:00:10”。</span><span class="sxs-lookup"><span data-stu-id="1c2a3-124">The default is "00:00:10".</span></span>|  
|`teredoEnabled`|<span data-ttu-id="1c2a3-125">一个布尔值，指示端口共享服务是否使用 Microsoft Teredo 服务代表 WCF 服务在 TCP 端口上进行侦听。</span><span class="sxs-lookup"><span data-stu-id="1c2a3-125">A Boolean value that indicates whether the port sharing service uses Microsoft Teredo service to listen on TCP ports on behalf of WCF services.</span></span> <span data-ttu-id="1c2a3-126">默认值为 `false`。</span><span class="sxs-lookup"><span data-stu-id="1c2a3-126">The default is `false`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="1c2a3-127">子元素</span><span class="sxs-lookup"><span data-stu-id="1c2a3-127">Child Elements</span></span>  
  
|<span data-ttu-id="1c2a3-128">元素</span><span class="sxs-lookup"><span data-stu-id="1c2a3-128">Element</span></span>|<span data-ttu-id="1c2a3-129">描述</span><span class="sxs-lookup"><span data-stu-id="1c2a3-129">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1c2a3-130">\<allowAccounts></span><span class="sxs-lookup"><span data-stu-id="1c2a3-130">\<allowAccounts></span></span>](allowaccounts.md)|<span data-ttu-id="1c2a3-131">一个配置元素的集合，这些元素`securityIdentifier`包含一个属性，用于为承载 WCF 服务并被授予对共享服务的连接访问权限的进程指定用户帐户。</span><span class="sxs-lookup"><span data-stu-id="1c2a3-131">A collection of configuration elements that contain a `securityIdentifier` attribute to specify user accounts for processes that host WCF services, and are granted connection access to the sharing service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="1c2a3-132">父元素</span><span class="sxs-lookup"><span data-stu-id="1c2a3-132">Parent Elements</span></span>  
  
|<span data-ttu-id="1c2a3-133">元素</span><span class="sxs-lookup"><span data-stu-id="1c2a3-133">Element</span></span>|<span data-ttu-id="1c2a3-134">描述</span><span class="sxs-lookup"><span data-stu-id="1c2a3-134">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1c2a3-135">\<system.serviceModel.activation></span><span class="sxs-lookup"><span data-stu-id="1c2a3-135">\<system.serviceModel.activation></span></span>](system-servicemodel-activation.md)|<span data-ttu-id="1c2a3-136">包含侦听器进程 SMSvcHost.exe 的配置设置。</span><span class="sxs-lookup"><span data-stu-id="1c2a3-136">Contains configuration settings for the listener process SMSvcHost.exe.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1c2a3-137">备注</span><span class="sxs-lookup"><span data-stu-id="1c2a3-137">Remarks</span></span>  
 <span data-ttu-id="1c2a3-138">有关端口共享的详细信息，请参阅[Net.tcp 端口共享](../../../wcf/feature-details/net-tcp-port-sharing.md)。</span><span class="sxs-lookup"><span data-stu-id="1c2a3-138">For more information on port sharing, see [Net.TCP Port Sharing](../../../wcf/feature-details/net-tcp-port-sharing.md).</span></span> <span data-ttu-id="1c2a3-139">若要了解如何配置端口共享服务，请参阅[配置 Net.tcp 端口共享服务](../../../wcf/feature-details/configuring-the-net-tcp-port-sharing-service.md)。</span><span class="sxs-lookup"><span data-stu-id="1c2a3-139">To understand how to configure the port sharing service, see [Configuring the Net.TCP Port Sharing Service](../../../wcf/feature-details/configuring-the-net-tcp-port-sharing-service.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1c2a3-140">请参阅</span><span class="sxs-lookup"><span data-stu-id="1c2a3-140">See also</span></span>

- <xref:System.ServiceModel.Activation.Configuration.NetTcpSection>
- [<span data-ttu-id="1c2a3-141">Net.TCP 端口共享</span><span class="sxs-lookup"><span data-stu-id="1c2a3-141">Net.TCP Port Sharing</span></span>](../../../wcf/feature-details/net-tcp-port-sharing.md)
- [<span data-ttu-id="1c2a3-142">配置 Net.TCP 端口共享服务</span><span class="sxs-lookup"><span data-stu-id="1c2a3-142">Configuring the Net.TCP Port Sharing Service</span></span>](../../../wcf/feature-details/configuring-the-net-tcp-port-sharing-service.md)
