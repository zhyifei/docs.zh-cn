---
title: '&lt;net.tcp&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8bc2f2be-11c1-4bab-9018-1d21ae568d94
caps.latest.revision: "15"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 6cd220b07c2d8f9a24591fc6e9614099e8460139
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="ltnettcpgt"></a><span data-ttu-id="68266-102">&lt;net.tcp&gt;</span><span class="sxs-lookup"><span data-stu-id="68266-102">&lt;net.tcp&gt;</span></span>
<span data-ttu-id="68266-103">指定允许多个进程共享同一 TCP 端口的 NET.TCP 端口共享服务的配置设置。</span><span class="sxs-lookup"><span data-stu-id="68266-103">Specifies configuration settings for the NET.TCP Port Sharing Service, which allows multiple processes to share the same TCP port.</span></span>  
  
 <span data-ttu-id="68266-104">\<system.serviceModel.activation ></span><span class="sxs-lookup"><span data-stu-id="68266-104">\<system.serviceModel.activation></span></span>  
<span data-ttu-id="68266-105">\<net.tcp ></span><span class="sxs-lookup"><span data-stu-id="68266-105">\<net.tcp></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="68266-106">语法</span><span class="sxs-lookup"><span data-stu-id="68266-106">Syntax</span></span>  
  
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
  
## <a name="type"></a><span data-ttu-id="68266-107">类型</span><span class="sxs-lookup"><span data-stu-id="68266-107">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="68266-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="68266-108">Attributes and Elements</span></span>  
 <span data-ttu-id="68266-109">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="68266-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="68266-110">特性</span><span class="sxs-lookup"><span data-stu-id="68266-110">Attributes</span></span>  
  
|<span data-ttu-id="68266-111">特性</span><span class="sxs-lookup"><span data-stu-id="68266-111">Attribute</span></span>|<span data-ttu-id="68266-112">描述</span><span class="sxs-lookup"><span data-stu-id="68266-112">Description</span></span>|  
|---------------|-----------------|  
|`listenBacklog`|<span data-ttu-id="68266-113">一个整数，指定从共享连接接受但仍未调度给 [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] 服务的最大未完成连接数。</span><span class="sxs-lookup"><span data-stu-id="68266-113">An integer that specifies the maximum outstanding connections that are accepted from the shared connection, but are not yet dispatched to [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] services.</span></span> <span data-ttu-id="68266-114">默认值为 10。</span><span class="sxs-lookup"><span data-stu-id="68266-114">The default is 10.</span></span>|  
|`maxPendingAccepts`|<span data-ttu-id="68266-115">一个整数，指定共享服务侦听终结点上的最大未完成并发接受线程数。</span><span class="sxs-lookup"><span data-stu-id="68266-115">An integer that specifies the maximum outstanding concurrent accepting threads on the listening endpoint for the sharing service.</span></span> <span data-ttu-id="68266-116">默认值为 2。</span><span class="sxs-lookup"><span data-stu-id="68266-116">The default is 2.</span></span>|  
|`MaxPendingConnections`|<span data-ttu-id="68266-117">侦听器可以拥有的正在等待应用程序接受的最大连接数。</span><span class="sxs-lookup"><span data-stu-id="68266-117">The maximum number of connections that the listener can have waiting to be accepted by the application.</span></span> <span data-ttu-id="68266-118">超出此配额值时，新的传入连接会被丢弃而不是等待接受。</span><span class="sxs-lookup"><span data-stu-id="68266-118">When this quota value is exceeded, new incoming connections are dropped rather than waiting to be accepted.</span></span> <span data-ttu-id="68266-119">连接功能（如消息安全）可能会使客户端打开多个连接。</span><span class="sxs-lookup"><span data-stu-id="68266-119">Connection features such as message security can cause a client to open more than one connection.</span></span> <span data-ttu-id="68266-120">在设置此配额值时，服务管理员应该考虑这些额外的连接。</span><span class="sxs-lookup"><span data-stu-id="68266-120">Service administrators should account for these additional connections when setting this quota value.</span></span> <span data-ttu-id="68266-121">默认值为 10。</span><span class="sxs-lookup"><span data-stu-id="68266-121">The default is 10.</span></span>|  
|`receiveTimeout`|<span data-ttu-id="68266-122">`TimeSpan`，它将为读取组帧数据并执行来自基础连接的连接调度指定超时值。</span><span class="sxs-lookup"><span data-stu-id="68266-122">A `TimeSpan` that specifies the timeout for reading the framing data and performing connection dispatching from the underlining connections.</span></span> <span data-ttu-id="68266-123">默认值为“00:00:10”。</span><span class="sxs-lookup"><span data-stu-id="68266-123">The default is "00:00:10".</span></span>|  
|`teredoEnabled`|<span data-ttu-id="68266-124">一个布尔值，指示端口共享服务是否使用 Microsoft Teredo 服务代表 [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] 服务侦听 TCP 端口。</span><span class="sxs-lookup"><span data-stu-id="68266-124">A Boolean value that indicates whether the port sharing service uses Microsoft Teredo service to listen on TCP ports on behalf of [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] services.</span></span> <span data-ttu-id="68266-125">默认值为 `false`。</span><span class="sxs-lookup"><span data-stu-id="68266-125">The default is `false`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="68266-126">子元素</span><span class="sxs-lookup"><span data-stu-id="68266-126">Child Elements</span></span>  
  
|<span data-ttu-id="68266-127">元素</span><span class="sxs-lookup"><span data-stu-id="68266-127">Element</span></span>|<span data-ttu-id="68266-128">描述</span><span class="sxs-lookup"><span data-stu-id="68266-128">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="68266-129">\<allowAccounts ></span><span class="sxs-lookup"><span data-stu-id="68266-129">\<allowAccounts></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/allowaccounts.md)|<span data-ttu-id="68266-130">一个配置元素集合，这些元素所包含的 `securityIdentifier` 属性用于指定进程的用户帐户，这些进程承载 [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] 服务并被授予了对该共享服务的连接访问权限。</span><span class="sxs-lookup"><span data-stu-id="68266-130">A collection of configuration elements that contain a `securityIdentifier` attribute to specify user accounts for processes that host [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] services, and are granted connection access to the sharing service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="68266-131">父元素</span><span class="sxs-lookup"><span data-stu-id="68266-131">Parent Elements</span></span>  
  
|<span data-ttu-id="68266-132">元素</span><span class="sxs-lookup"><span data-stu-id="68266-132">Element</span></span>|<span data-ttu-id="68266-133">描述</span><span class="sxs-lookup"><span data-stu-id="68266-133">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="68266-134">\<system.serviceModel.activation></span><span class="sxs-lookup"><span data-stu-id="68266-134">\<system.serviceModel.activation></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel-activation.md)|<span data-ttu-id="68266-135">包含侦听器进程 SMSvcHost.exe 的配置设置。</span><span class="sxs-lookup"><span data-stu-id="68266-135">Contains configuration settings for the listener process SMSvcHost.exe.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="68266-136">备注</span><span class="sxs-lookup"><span data-stu-id="68266-136">Remarks</span></span>  
 <span data-ttu-id="68266-137">端口共享的详细信息，请参阅[Net.TCP 端口共享](http://msdn.microsoft.com/en-us/f13692ee-a179-4439-ae72-50db9534eded)。</span><span class="sxs-lookup"><span data-stu-id="68266-137">For more information on port sharing, see [Net.TCP Port Sharing](http://msdn.microsoft.com/en-us/f13692ee-a179-4439-ae72-50db9534eded).</span></span> <span data-ttu-id="68266-138">若要了解如何配置端口共享服务，请参阅[配置 Net.TCP Port Sharing Service](http://msdn.microsoft.com/en-us/b6dd81fa-68b7-4e1b-868e-88e5901b7ea0)。</span><span class="sxs-lookup"><span data-stu-id="68266-138">To understand how to configure the port sharing service, see [Configuring the Net.TCP Port Sharing Service](http://msdn.microsoft.com/en-us/b6dd81fa-68b7-4e1b-868e-88e5901b7ea0).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="68266-139">另请参阅</span><span class="sxs-lookup"><span data-stu-id="68266-139">See Also</span></span>  
 <xref:System.ServiceModel.Activation.Configuration.NetTcpSection>  
 [<span data-ttu-id="68266-140">Net.TCP 端口共享</span><span class="sxs-lookup"><span data-stu-id="68266-140">Net.TCP Port Sharing</span></span>](http://msdn.microsoft.com/en-us/f13692ee-a179-4439-ae72-50db9534eded)  
 [<span data-ttu-id="68266-141">配置 Net.TCP 端口共享服务</span><span class="sxs-lookup"><span data-stu-id="68266-141">Configuring the Net.TCP Port Sharing Service</span></span>](http://msdn.microsoft.com/en-us/b6dd81fa-68b7-4e1b-868e-88e5901b7ea0)
