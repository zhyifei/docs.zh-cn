---
title: '&lt;net.pipe&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6a0f0318-f8f6-466c-9fae-199d7274a82e
caps.latest.revision: "11"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 5d68c2113b08065f7ec74ae68d7f0b5918cab0aa
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="ltnetpipegt"></a><span data-ttu-id="960a9-102">&lt;net.pipe&gt;</span><span class="sxs-lookup"><span data-stu-id="960a9-102">&lt;net.pipe&gt;</span></span>
<span data-ttu-id="960a9-103">指定命名管道激活服务的配置设置，命名管道激活服务将管理命名管道连接的生存期，并处理通过命名管道到达的激活请求。</span><span class="sxs-lookup"><span data-stu-id="960a9-103">Specifies configuration settings for the Named Pipe Activation Service, which manages the lifetime of the named pipe connection, and handles activation requests that arrive over named pipes.</span></span>  
  
 <span data-ttu-id="960a9-104">\<system.serviceModel.activation ></span><span class="sxs-lookup"><span data-stu-id="960a9-104">\<system.serviceModel.activation></span></span>  
<span data-ttu-id="960a9-105">\<net.pipe ></span><span class="sxs-lookup"><span data-stu-id="960a9-105">\<net.pipe></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="960a9-106">语法</span><span class="sxs-lookup"><span data-stu-id="960a9-106">Syntax</span></span>  
  
```xml  
<configuration>  
   <system.serviceModel.activation>  
       <net.pipe maxPendingAccepts="Integer"  
                    maxPendingConnections="Integer"  
          receiveTimeout="TimeSpan">  
          <allowAccounts>  
             // LocalSystem account  
             <add securityIdentifier="S-1-5-18"/>  
             // LocalService account  
             <add securityIdentifier="S-1-5-19"/>  
             // Administrators account  
             <add securityIdentifier="S-1-5-20"/>  
             // Network Service account  
             <add securityIdentifier="S-1-5-32-544" />  
             // IIS_IUSRS account (Vista only)  
             <add securityIdentifier="S-1-5-32-568"/>  
           </allowAccounts>  
       </net.pipe>  
   </system.serviceModel.activation>  
</configuration>  
```  
  
## <a name="type"></a><span data-ttu-id="960a9-107">类型</span><span class="sxs-lookup"><span data-stu-id="960a9-107">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="960a9-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="960a9-108">Attributes and Elements</span></span>  
 <span data-ttu-id="960a9-109">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="960a9-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="960a9-110">特性</span><span class="sxs-lookup"><span data-stu-id="960a9-110">Attributes</span></span>  
  
|<span data-ttu-id="960a9-111">特性</span><span class="sxs-lookup"><span data-stu-id="960a9-111">Attribute</span></span>|<span data-ttu-id="960a9-112">描述</span><span class="sxs-lookup"><span data-stu-id="960a9-112">Description</span></span>|  
|---------------|-----------------|  
|`maxPendingAccepts`|<span data-ttu-id="960a9-113">一个整数，指定共享服务侦听终结点上的最大未完成并发接受线程数。</span><span class="sxs-lookup"><span data-stu-id="960a9-113">An integer that specifies the maximum outstanding concurrent accepting threads on the listening endpoint for the sharing service.</span></span> <span data-ttu-id="960a9-114">默认值为 2。</span><span class="sxs-lookup"><span data-stu-id="960a9-114">The default is 2.</span></span>|  
|`maxPendingConnections`|<span data-ttu-id="960a9-115">一个整数，指定可等待调度的最大连接数。</span><span class="sxs-lookup"><span data-stu-id="960a9-115">An integer that specifies the maximum number of connections that can wait for dispatch.</span></span> <span data-ttu-id="960a9-116">默认值为 100。</span><span class="sxs-lookup"><span data-stu-id="960a9-116">The default is 100.</span></span>|  
|`receiveTimeout`|<span data-ttu-id="960a9-117">`TimeSpan`，它将为读取组帧数据并执行来自基础连接的连接调度指定超时值。</span><span class="sxs-lookup"><span data-stu-id="960a9-117">A `TimeSpan` that specifies the timeout for reading the framing data and performing connection dispatching from the underlining connections.</span></span> <span data-ttu-id="960a9-118">默认值为“00:00:10”</span><span class="sxs-lookup"><span data-stu-id="960a9-118">The default is "00:00:10"</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="960a9-119">子元素</span><span class="sxs-lookup"><span data-stu-id="960a9-119">Child Elements</span></span>  
  
|<span data-ttu-id="960a9-120">元素</span><span class="sxs-lookup"><span data-stu-id="960a9-120">Element</span></span>|<span data-ttu-id="960a9-121">描述</span><span class="sxs-lookup"><span data-stu-id="960a9-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="960a9-122">\<allowAccounts ></span><span class="sxs-lookup"><span data-stu-id="960a9-122">\<allowAccounts></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/allowaccounts.md)|<span data-ttu-id="960a9-123">一个配置元素集合，这些元素所包含的 `securityIdentifier` 属性用于指定进程的用户帐户，这些进程承载 [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] 服务并被授予了对该共享服务的连接访问权限。</span><span class="sxs-lookup"><span data-stu-id="960a9-123">A collection of configuration elements that contain a `securityIdentifier` attribute to specify user accounts for processes that host [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] services, and are granted connection access to the sharing service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="960a9-124">父元素</span><span class="sxs-lookup"><span data-stu-id="960a9-124">Parent Elements</span></span>  
  
|<span data-ttu-id="960a9-125">元素</span><span class="sxs-lookup"><span data-stu-id="960a9-125">Element</span></span>|<span data-ttu-id="960a9-126">描述</span><span class="sxs-lookup"><span data-stu-id="960a9-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="960a9-127">\<system.serviceModel.activation></span><span class="sxs-lookup"><span data-stu-id="960a9-127">\<system.serviceModel.activation></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel-activation.md)|<span data-ttu-id="960a9-128">包含侦听器进程 SMSvcHost.exe 的配置设置。</span><span class="sxs-lookup"><span data-stu-id="960a9-128">Contains configuration settings for the listener process SMSvcHost.exe.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="960a9-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="960a9-129">See Also</span></span>  
 <xref:System.ServiceModel.Activation.Configuration.NetPipeSection>
