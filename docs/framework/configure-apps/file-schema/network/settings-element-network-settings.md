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
ms.openlocfilehash: 7db55dd9d2ca79342cadb2320d08ca9235223def
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54671845"
---
# <a name="ltsettingsgt-element-network-settings"></a><span data-ttu-id="05ffc-102">&lt;设置&gt;元素 （网络设置）</span><span class="sxs-lookup"><span data-stu-id="05ffc-102">&lt;settings&gt; Element (Network Settings)</span></span>
<span data-ttu-id="05ffc-103">配置 <xref:System.Net?displayProperty=nameWithType> 命名空间的基本网络选项。</span><span class="sxs-lookup"><span data-stu-id="05ffc-103">Configures basic network options for the <xref:System.Net?displayProperty=nameWithType> namespace.</span></span>  
  
 <span data-ttu-id="05ffc-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="05ffc-104">\<configuration></span></span>  
<span data-ttu-id="05ffc-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="05ffc-105">\<system.net></span></span>  
<span data-ttu-id="05ffc-106">\<settings></span><span class="sxs-lookup"><span data-stu-id="05ffc-106">\<settings></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="05ffc-107">语法</span><span class="sxs-lookup"><span data-stu-id="05ffc-107">Syntax</span></span>  
  
```xml  
<settings>  
  <httpListener>...</httpListener>  
  <httpWebRequest>...</httpWebRequest>  
  <ipv6>...</ipv6>  
  <performanceCounters>...</performanceCounters>  
  <servicePointManager>...</servicePointManager>  
  <socket>...</socket>  
  <webProxyScript>...</webProxyScript>  
</settings>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="05ffc-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="05ffc-108">Attributes and Elements</span></span>  
 <span data-ttu-id="05ffc-109">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="05ffc-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="05ffc-110">特性</span><span class="sxs-lookup"><span data-stu-id="05ffc-110">Attributes</span></span>  
 <span data-ttu-id="05ffc-111">无。</span><span class="sxs-lookup"><span data-stu-id="05ffc-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="05ffc-112">子元素</span><span class="sxs-lookup"><span data-stu-id="05ffc-112">Child Elements</span></span>  
  
|<span data-ttu-id="05ffc-113">元素</span><span class="sxs-lookup"><span data-stu-id="05ffc-113">Element</span></span>|<span data-ttu-id="05ffc-114">描述</span><span class="sxs-lookup"><span data-stu-id="05ffc-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="05ffc-115">httpListener</span><span class="sxs-lookup"><span data-stu-id="05ffc-115">httpListener</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/httplistener-element-network-settings.md)|<span data-ttu-id="05ffc-116">自定义使用参数<xref:System.Net.HttpListener>类。</span><span class="sxs-lookup"><span data-stu-id="05ffc-116">Customizes parameters used by the <xref:System.Net.HttpListener> class.</span></span>|  
|[<span data-ttu-id="05ffc-117">httpWebRequest</span><span class="sxs-lookup"><span data-stu-id="05ffc-117">httpWebRequest</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/httpwebrequest-element-network-settings.md)|<span data-ttu-id="05ffc-118">自定义 Web 请求参数。</span><span class="sxs-lookup"><span data-stu-id="05ffc-118">Customizes Web request parameters.</span></span>|  
|[<span data-ttu-id="05ffc-119">ipv6</span><span class="sxs-lookup"><span data-stu-id="05ffc-119">ipv6</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/ipv6-element-network-settings.md)|<span data-ttu-id="05ffc-120">启用 Internet 协议版本 6 (IPv6) 支持。</span><span class="sxs-lookup"><span data-stu-id="05ffc-120">Enables Internet Protocol version 6 (IPv6) support.</span></span>|  
|[<span data-ttu-id="05ffc-121">\<performanceCounter > 元素 （网络设置）</span><span class="sxs-lookup"><span data-stu-id="05ffc-121">\<performanceCounter> Element (Network Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/performancecounter-element-network-settings.md)|<span data-ttu-id="05ffc-122">启用的网络性能计数器。</span><span class="sxs-lookup"><span data-stu-id="05ffc-122">Enables network performance counters.</span></span>|  
|[<span data-ttu-id="05ffc-123">servicePointManager</span><span class="sxs-lookup"><span data-stu-id="05ffc-123">servicePointManager</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/servicepointmanager-element-network-settings.md)|<span data-ttu-id="05ffc-124">配置连接到网络资源。</span><span class="sxs-lookup"><span data-stu-id="05ffc-124">Configures connections to network resources.</span></span>|  
|[<span data-ttu-id="05ffc-125">socket</span><span class="sxs-lookup"><span data-stu-id="05ffc-125">socket</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/socket-element-network-settings.md)|<span data-ttu-id="05ffc-126">指定套接字操作是否使用完成端口。</span><span class="sxs-lookup"><span data-stu-id="05ffc-126">Specifies whether socket operations use completion ports.</span></span>|  
|[<span data-ttu-id="05ffc-127">\<webProxyScript > 元素 （网络设置）</span><span class="sxs-lookup"><span data-stu-id="05ffc-127">\<webProxyScript> Element (Network Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/webproxyscript-element-network-settings.md)|<span data-ttu-id="05ffc-128">配置用于发现 Web 代理脚本的特征。</span><span class="sxs-lookup"><span data-stu-id="05ffc-128">Configures the characteristics of the script used to discover Web proxies.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="05ffc-129">父元素</span><span class="sxs-lookup"><span data-stu-id="05ffc-129">Parent Elements</span></span>  
  
|<span data-ttu-id="05ffc-130">元素</span><span class="sxs-lookup"><span data-stu-id="05ffc-130">Element</span></span>|<span data-ttu-id="05ffc-131">描述</span><span class="sxs-lookup"><span data-stu-id="05ffc-131">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="05ffc-132">system.net</span><span class="sxs-lookup"><span data-stu-id="05ffc-132">system.net</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/system-net-element-network-settings.md)|<span data-ttu-id="05ffc-133">包含指定 .NET Framework 如何连接到网络的设置。</span><span class="sxs-lookup"><span data-stu-id="05ffc-133">Contains settings that specify how the .NET Framework connects to the network.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="05ffc-134">备注</span><span class="sxs-lookup"><span data-stu-id="05ffc-134">Remarks</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="05ffc-135">配置文件</span><span class="sxs-lookup"><span data-stu-id="05ffc-135">Configuration Files</span></span>  
 <span data-ttu-id="05ffc-136">此元素可在应用程序配置文件或计算机配置文件 (Machine.config) 中使用。</span><span class="sxs-lookup"><span data-stu-id="05ffc-136">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="05ffc-137">请参阅</span><span class="sxs-lookup"><span data-stu-id="05ffc-137">See also</span></span>
- <xref:System.Net?displayProperty=nameWithType>
- [<span data-ttu-id="05ffc-138">网络设置架构</span><span class="sxs-lookup"><span data-stu-id="05ffc-138">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
