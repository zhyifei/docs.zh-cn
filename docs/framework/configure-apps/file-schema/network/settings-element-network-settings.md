---
title: '&lt;设置&gt;元素 （网络设置）'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#settings
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/settings
helpviewer_keywords:
- settings element
- <settings> element
ms.assetid: 189ce989-c39b-427d-b004-6b82a668b931
author: mcleblanc
ms.author: markl
ms.openlocfilehash: 9d6189c736e1f2843a986c3a96f8547e9a231db0
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/26/2018
ms.locfileid: "47231396"
---
# <a name="ltsettingsgt-element-network-settings"></a><span data-ttu-id="b4cc0-102">&lt;设置&gt;元素 （网络设置）</span><span class="sxs-lookup"><span data-stu-id="b4cc0-102">&lt;settings&gt; Element (Network Settings)</span></span>
<span data-ttu-id="b4cc0-103">配置 <xref:System.Net?displayProperty=nameWithType> 命名空间的基本网络选项。</span><span class="sxs-lookup"><span data-stu-id="b4cc0-103">Configures basic network options for the <xref:System.Net?displayProperty=nameWithType> namespace.</span></span>  
  
 <span data-ttu-id="b4cc0-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="b4cc0-104">\<configuration></span></span>  
<span data-ttu-id="b4cc0-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="b4cc0-105">\<system.net></span></span>  
<span data-ttu-id="b4cc0-106">\<设置 ></span><span class="sxs-lookup"><span data-stu-id="b4cc0-106">\<settings></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b4cc0-107">语法</span><span class="sxs-lookup"><span data-stu-id="b4cc0-107">Syntax</span></span>  
  
```xml  
<settings>  
  <httpListener> … </httpListener>  
  <httpWebRequest> … </httpWebRequest>  
  <ipv6> … </ipv6>  
  <performanceCounters> … </performanceCounters>  
  <servicePointManager> … </servicePointManager>  
  <socket> … </socket>  
  <webProxyScript> … </webProxyScript>  
</settings>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b4cc0-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="b4cc0-108">Attributes and Elements</span></span>  
 <span data-ttu-id="b4cc0-109">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="b4cc0-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b4cc0-110">特性</span><span class="sxs-lookup"><span data-stu-id="b4cc0-110">Attributes</span></span>  
 <span data-ttu-id="b4cc0-111">无。</span><span class="sxs-lookup"><span data-stu-id="b4cc0-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="b4cc0-112">子元素</span><span class="sxs-lookup"><span data-stu-id="b4cc0-112">Child Elements</span></span>  
  
|<span data-ttu-id="b4cc0-113">元素</span><span class="sxs-lookup"><span data-stu-id="b4cc0-113">Element</span></span>|<span data-ttu-id="b4cc0-114">描述</span><span class="sxs-lookup"><span data-stu-id="b4cc0-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b4cc0-115">httpListener</span><span class="sxs-lookup"><span data-stu-id="b4cc0-115">httpListener</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/httplistener-element-network-settings.md)|<span data-ttu-id="b4cc0-116">自定义使用参数<xref:System.Net.HttpListener>类。</span><span class="sxs-lookup"><span data-stu-id="b4cc0-116">Customizes parameters used by the <xref:System.Net.HttpListener> class.</span></span>|  
|[<span data-ttu-id="b4cc0-117">httpWebRequest</span><span class="sxs-lookup"><span data-stu-id="b4cc0-117">httpWebRequest</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/httpwebrequest-element-network-settings.md)|<span data-ttu-id="b4cc0-118">自定义 Web 请求参数。</span><span class="sxs-lookup"><span data-stu-id="b4cc0-118">Customizes Web request parameters.</span></span>|  
|[<span data-ttu-id="b4cc0-119">ipv6</span><span class="sxs-lookup"><span data-stu-id="b4cc0-119">ipv6</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/ipv6-element-network-settings.md)|<span data-ttu-id="b4cc0-120">启用 Internet 协议版本 6 (IPv6) 支持。</span><span class="sxs-lookup"><span data-stu-id="b4cc0-120">Enables Internet Protocol version 6 (IPv6) support.</span></span>|  
|[<span data-ttu-id="b4cc0-121">\<performanceCounter > 元素 （网络设置）</span><span class="sxs-lookup"><span data-stu-id="b4cc0-121">\<performanceCounter> Element (Network Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/performancecounter-element-network-settings.md)|<span data-ttu-id="b4cc0-122">启用的网络性能计数器。</span><span class="sxs-lookup"><span data-stu-id="b4cc0-122">Enables network performance counters.</span></span>|  
|[<span data-ttu-id="b4cc0-123">servicePointManager</span><span class="sxs-lookup"><span data-stu-id="b4cc0-123">servicePointManager</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/servicepointmanager-element-network-settings.md)|<span data-ttu-id="b4cc0-124">配置连接到网络资源。</span><span class="sxs-lookup"><span data-stu-id="b4cc0-124">Configures connections to network resources.</span></span>|  
|[<span data-ttu-id="b4cc0-125">套接字</span><span class="sxs-lookup"><span data-stu-id="b4cc0-125">socket</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/socket-element-network-settings.md)|<span data-ttu-id="b4cc0-126">指定套接字操作是否使用完成端口。</span><span class="sxs-lookup"><span data-stu-id="b4cc0-126">Specifies whether socket operations use completion ports.</span></span>|  
|[<span data-ttu-id="b4cc0-127">\<webProxyScript > 元素 （网络设置）</span><span class="sxs-lookup"><span data-stu-id="b4cc0-127">\<webProxyScript> Element (Network Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/webproxyscript-element-network-settings.md)|<span data-ttu-id="b4cc0-128">配置用于发现 Web 代理脚本的特征。</span><span class="sxs-lookup"><span data-stu-id="b4cc0-128">Configures the characteristics of the script used to discover Web proxies.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="b4cc0-129">父元素</span><span class="sxs-lookup"><span data-stu-id="b4cc0-129">Parent Elements</span></span>  
  
|<span data-ttu-id="b4cc0-130">元素</span><span class="sxs-lookup"><span data-stu-id="b4cc0-130">Element</span></span>|<span data-ttu-id="b4cc0-131">描述</span><span class="sxs-lookup"><span data-stu-id="b4cc0-131">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b4cc0-132">system.net</span><span class="sxs-lookup"><span data-stu-id="b4cc0-132">system.net</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/system-net-element-network-settings.md)|<span data-ttu-id="b4cc0-133">包含指定 .NET Framework 如何连接到网络的设置。</span><span class="sxs-lookup"><span data-stu-id="b4cc0-133">Contains settings that specify how the .NET Framework connects to the network.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b4cc0-134">备注</span><span class="sxs-lookup"><span data-stu-id="b4cc0-134">Remarks</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="b4cc0-135">配置文件</span><span class="sxs-lookup"><span data-stu-id="b4cc0-135">Configuration Files</span></span>  
 <span data-ttu-id="b4cc0-136">此元素可在应用程序配置文件或计算机配置文件 (Machine.config) 中使用。</span><span class="sxs-lookup"><span data-stu-id="b4cc0-136">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b4cc0-137">请参阅</span><span class="sxs-lookup"><span data-stu-id="b4cc0-137">See Also</span></span>  
 <xref:System.Net?displayProperty=nameWithType>  
 [<span data-ttu-id="b4cc0-138">网络设置架构</span><span class="sxs-lookup"><span data-stu-id="b4cc0-138">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
