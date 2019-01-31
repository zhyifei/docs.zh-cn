---
title: <net.pipe>
ms.date: 03/30/2017
ms.assetid: 6a0f0318-f8f6-466c-9fae-199d7274a82e
ms.openlocfilehash: ddd25d3d25f4c4be1a9e26d444fa799a55c9cccc
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/30/2019
ms.locfileid: "55283278"
---
# <a name="netpipe"></a><span data-ttu-id="14c88-102">\<net.pipe></span><span class="sxs-lookup"><span data-stu-id="14c88-102">\<net.pipe></span></span>
<span data-ttu-id="14c88-103">指定命名管道激活服务的配置设置，命名管道激活服务将管理命名管道连接的生存期，并处理通过命名管道到达的激活请求。</span><span class="sxs-lookup"><span data-stu-id="14c88-103">Specifies configuration settings for the Named Pipe Activation Service, which manages the lifetime of the named pipe connection, and handles activation requests that arrive over named pipes.</span></span>  
  
 <span data-ttu-id="14c88-104">\<system.serviceModel.activation></span><span class="sxs-lookup"><span data-stu-id="14c88-104">\<system.serviceModel.activation></span></span>  
<span data-ttu-id="14c88-105">\<net.pipe></span><span class="sxs-lookup"><span data-stu-id="14c88-105">\<net.pipe></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="14c88-106">语法</span><span class="sxs-lookup"><span data-stu-id="14c88-106">Syntax</span></span>  
  
```xml  
<configuration>
  <system.serviceModel.activation>
    <net.pipe maxPendingAccepts="Integer"
              maxPendingConnections="Integer"
              receiveTimeout="TimeSpan">
      <allowAccounts>
        <!-- LocalSystem account -->
        <add securityIdentifier="S-1-5-18" />
        <!-- LocalService account -->
        <add securityIdentifier="S-1-5-19" />
        <!-- Administrators account -->
        <add securityIdentifier="S-1-5-20" />
        <!-- Network Service account -->
        <add securityIdentifier="S-1-5-32-544" />
        <!-- IIS_IUSRS account (Vista only) -->
        <add securityIdentifier="S-1-5-32-568" />
      </allowAccounts>
    </net.pipe>
  </system.serviceModel.activation>
</configuration>
```  
  
## <a name="type"></a><span data-ttu-id="14c88-107">类型</span><span class="sxs-lookup"><span data-stu-id="14c88-107">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="14c88-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="14c88-108">Attributes and Elements</span></span>  
 <span data-ttu-id="14c88-109">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="14c88-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="14c88-110">特性</span><span class="sxs-lookup"><span data-stu-id="14c88-110">Attributes</span></span>  
  
|<span data-ttu-id="14c88-111">特性</span><span class="sxs-lookup"><span data-stu-id="14c88-111">Attribute</span></span>|<span data-ttu-id="14c88-112">描述</span><span class="sxs-lookup"><span data-stu-id="14c88-112">Description</span></span>|  
|---------------|-----------------|  
|`maxPendingAccepts`|<span data-ttu-id="14c88-113">一个整数，指定共享服务侦听终结点上的最大未完成并发接受线程数。</span><span class="sxs-lookup"><span data-stu-id="14c88-113">An integer that specifies the maximum outstanding concurrent accepting threads on the listening endpoint for the sharing service.</span></span> <span data-ttu-id="14c88-114">默认值为 2。</span><span class="sxs-lookup"><span data-stu-id="14c88-114">The default is 2.</span></span>|  
|`maxPendingConnections`|<span data-ttu-id="14c88-115">一个整数，指定可等待调度的最大连接数。</span><span class="sxs-lookup"><span data-stu-id="14c88-115">An integer that specifies the maximum number of connections that can wait for dispatch.</span></span> <span data-ttu-id="14c88-116">默认值为 100。</span><span class="sxs-lookup"><span data-stu-id="14c88-116">The default is 100.</span></span>|  
|`receiveTimeout`|<span data-ttu-id="14c88-117">`TimeSpan`，它将为读取组帧数据并执行来自基础连接的连接调度指定超时值。</span><span class="sxs-lookup"><span data-stu-id="14c88-117">A `TimeSpan` that specifies the timeout for reading the framing data and performing connection dispatching from the underlining connections.</span></span> <span data-ttu-id="14c88-118">默认值为“00:00:10”</span><span class="sxs-lookup"><span data-stu-id="14c88-118">The default is "00:00:10"</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="14c88-119">子元素</span><span class="sxs-lookup"><span data-stu-id="14c88-119">Child Elements</span></span>  
  
|<span data-ttu-id="14c88-120">元素</span><span class="sxs-lookup"><span data-stu-id="14c88-120">Element</span></span>|<span data-ttu-id="14c88-121">描述</span><span class="sxs-lookup"><span data-stu-id="14c88-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="14c88-122">\<allowAccounts></span><span class="sxs-lookup"><span data-stu-id="14c88-122">\<allowAccounts></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/allowaccounts.md)|<span data-ttu-id="14c88-123">包含的配置元素的集合`securityIdentifier`属性指定的进程的承载 WCF 服务并被授予对共享服务的连接访问权限的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="14c88-123">A collection of configuration elements that contain a `securityIdentifier` attribute to specify user accounts for processes that host WCF services, and are granted connection access to the sharing service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="14c88-124">父元素</span><span class="sxs-lookup"><span data-stu-id="14c88-124">Parent Elements</span></span>  
  
|<span data-ttu-id="14c88-125">元素</span><span class="sxs-lookup"><span data-stu-id="14c88-125">Element</span></span>|<span data-ttu-id="14c88-126">描述</span><span class="sxs-lookup"><span data-stu-id="14c88-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="14c88-127">\<system.serviceModel.activation></span><span class="sxs-lookup"><span data-stu-id="14c88-127">\<system.serviceModel.activation></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel-activation.md)|<span data-ttu-id="14c88-128">包含侦听器进程 SMSvcHost.exe 的配置设置。</span><span class="sxs-lookup"><span data-stu-id="14c88-128">Contains configuration settings for the listener process SMSvcHost.exe.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="14c88-129">请参阅</span><span class="sxs-lookup"><span data-stu-id="14c88-129">See also</span></span>
- <xref:System.ServiceModel.Activation.Configuration.NetPipeSection>
