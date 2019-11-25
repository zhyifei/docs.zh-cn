---
title: <settings> 元素（网络设置）
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#settings
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/settings
helpviewer_keywords:
- settings element
- <settings> element
ms.assetid: 189ce989-c39b-427d-b004-6b82a668b931
ms.openlocfilehash: d510c445c585a36005ed415b14188efc4be03984
ms.sourcegitcommit: 7f8eeef060ddeb2cabfa52843776faf652c5a1f5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/14/2019
ms.locfileid: "74089109"
---
# <a name="settings-element-network-settings"></a><span data-ttu-id="e107c-102">\<设置 > 元素（网络设置）</span><span class="sxs-lookup"><span data-stu-id="e107c-102">\<settings> Element (Network Settings)</span></span>
<span data-ttu-id="e107c-103">配置 <xref:System.Net?displayProperty=nameWithType> 命名空间的基本网络选项。</span><span class="sxs-lookup"><span data-stu-id="e107c-103">Configures basic network options for the <xref:System.Net?displayProperty=nameWithType> namespace.</span></span>  

<span data-ttu-id="e107c-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="e107c-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="e107c-105">\<&nbsp;&nbsp;[ **> 的**](system-net-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="e107c-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span></span>\
<span data-ttu-id="e107c-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<设置 >**</span><span class="sxs-lookup"><span data-stu-id="e107c-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<settings>**</span></span>

## <a name="syntax"></a><span data-ttu-id="e107c-107">语法</span><span class="sxs-lookup"><span data-stu-id="e107c-107">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e107c-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="e107c-108">Attributes and Elements</span></span>  
 <span data-ttu-id="e107c-109">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="e107c-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e107c-110">特性</span><span class="sxs-lookup"><span data-stu-id="e107c-110">Attributes</span></span>  
 <span data-ttu-id="e107c-111">无。</span><span class="sxs-lookup"><span data-stu-id="e107c-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="e107c-112">子元素</span><span class="sxs-lookup"><span data-stu-id="e107c-112">Child Elements</span></span>  
  
|<span data-ttu-id="e107c-113">元素</span><span class="sxs-lookup"><span data-stu-id="e107c-113">Element</span></span>|<span data-ttu-id="e107c-114">描述</span><span class="sxs-lookup"><span data-stu-id="e107c-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e107c-115">httpListener</span><span class="sxs-lookup"><span data-stu-id="e107c-115">httpListener</span></span>](httplistener-element-network-settings.md)|<span data-ttu-id="e107c-116">自定义 <xref:System.Net.HttpListener> 类使用的参数。</span><span class="sxs-lookup"><span data-stu-id="e107c-116">Customizes parameters used by the <xref:System.Net.HttpListener> class.</span></span>|  
|[<span data-ttu-id="e107c-117">httpWebRequest</span><span class="sxs-lookup"><span data-stu-id="e107c-117">httpWebRequest</span></span>](httpwebrequest-element-network-settings.md)|<span data-ttu-id="e107c-118">自定义 Web 请求参数。</span><span class="sxs-lookup"><span data-stu-id="e107c-118">Customizes Web request parameters.</span></span>|  
|[<span data-ttu-id="e107c-119">ipv6</span><span class="sxs-lookup"><span data-stu-id="e107c-119">ipv6</span></span>](ipv6-element-network-settings.md)|<span data-ttu-id="e107c-120">启用 Internet 协议版本6（IPv6）支持。</span><span class="sxs-lookup"><span data-stu-id="e107c-120">Enables Internet Protocol version 6 (IPv6) support.</span></span>|  
|[<span data-ttu-id="e107c-121">\<performanceCounter > 元素（网络设置）</span><span class="sxs-lookup"><span data-stu-id="e107c-121">\<performanceCounter> Element (Network Settings)</span></span>](performancecounter-element-network-settings.md)|<span data-ttu-id="e107c-122">启用网络性能计数器。</span><span class="sxs-lookup"><span data-stu-id="e107c-122">Enables network performance counters.</span></span>|  
|[<span data-ttu-id="e107c-123">servicePointManager</span><span class="sxs-lookup"><span data-stu-id="e107c-123">servicePointManager</span></span>](servicepointmanager-element-network-settings.md)|<span data-ttu-id="e107c-124">配置与网络资源的连接。</span><span class="sxs-lookup"><span data-stu-id="e107c-124">Configures connections to network resources.</span></span>|  
|[<span data-ttu-id="e107c-125">片</span><span class="sxs-lookup"><span data-stu-id="e107c-125">socket</span></span>](socket-element-network-settings.md)|<span data-ttu-id="e107c-126">指定套接字操作是否使用完成端口。</span><span class="sxs-lookup"><span data-stu-id="e107c-126">Specifies whether socket operations use completion ports.</span></span>|  
|[<span data-ttu-id="e107c-127">\<w > 元素（网络设置）</span><span class="sxs-lookup"><span data-stu-id="e107c-127">\<webProxyScript> Element (Network Settings)</span></span>](webproxyscript-element-network-settings.md)|<span data-ttu-id="e107c-128">配置用于发现 Web 代理的脚本的特征。</span><span class="sxs-lookup"><span data-stu-id="e107c-128">Configures the characteristics of the script used to discover Web proxies.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="e107c-129">父元素</span><span class="sxs-lookup"><span data-stu-id="e107c-129">Parent Elements</span></span>  
  
|<span data-ttu-id="e107c-130">元素</span><span class="sxs-lookup"><span data-stu-id="e107c-130">Element</span></span>|<span data-ttu-id="e107c-131">描述</span><span class="sxs-lookup"><span data-stu-id="e107c-131">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e107c-132">system.net</span><span class="sxs-lookup"><span data-stu-id="e107c-132">system.net</span></span>](system-net-element-network-settings.md)|<span data-ttu-id="e107c-133">包含指定 .NET Framework 如何连接到网络的设置。</span><span class="sxs-lookup"><span data-stu-id="e107c-133">Contains settings that specify how the .NET Framework connects to the network.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e107c-134">备注</span><span class="sxs-lookup"><span data-stu-id="e107c-134">Remarks</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="e107c-135">配置文件</span><span class="sxs-lookup"><span data-stu-id="e107c-135">Configuration Files</span></span>  
 <span data-ttu-id="e107c-136">此元素可在应用程序配置文件或计算机配置文件 (Machine.config) 中使用。</span><span class="sxs-lookup"><span data-stu-id="e107c-136">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e107c-137">请参阅</span><span class="sxs-lookup"><span data-stu-id="e107c-137">See also</span></span>

- <xref:System.Net?displayProperty=nameWithType>
- [<span data-ttu-id="e107c-138">网络设置架构</span><span class="sxs-lookup"><span data-stu-id="e107c-138">Network Settings Schema</span></span>](index.md)
