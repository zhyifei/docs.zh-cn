---
title: "网络设置架构"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- elements [.NET Framework], network configuration elements
- sending data, network configuration elements
- receiving data, network configuration elements
- configuration settings [.NET Framework], networks
- Internet, network configuration elements
- network configuration elements
- network settings
- connections [.NET Framework], network configuration elements
- network resources, network configuration elements
ms.assetid: f1de5a0f-76c5-4833-819f-5222b8146340
caps.latest.revision: "14"
author: mcleblanc
ms.author: markl
manager: markl
ms.workload: dotnet
ms.openlocfilehash: d8f13b75d0558c002fd29938ce98d85f358acc9a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="network-settings-schema"></a><span data-ttu-id="c6a15-102">网络设置架构</span><span class="sxs-lookup"><span data-stu-id="c6a15-102">Network Settings Schema</span></span>
<span data-ttu-id="c6a15-103">网络设置指定 .NET Framework 与 Internet 的连接方式。</span><span class="sxs-lookup"><span data-stu-id="c6a15-103">Network settings specify how the .NET Framework connects to the Internet.</span></span> <span data-ttu-id="c6a15-104">下表描述 [\<system.Net> 元素（网络设置）](../../../../../docs/framework/configure-apps/file-schema/network/system-net-element-network-settings.md)下每个子配置元素的功能。</span><span class="sxs-lookup"><span data-stu-id="c6a15-104">The following table describes the function of each child configuration element under the [\<system.Net> Element (Network Settings)](../../../../../docs/framework/configure-apps/file-schema/network/system-net-element-network-settings.md).</span></span>  
  
|<span data-ttu-id="c6a15-105">元素</span><span class="sxs-lookup"><span data-stu-id="c6a15-105">Element</span></span>|<span data-ttu-id="c6a15-106">描述</span><span class="sxs-lookup"><span data-stu-id="c6a15-106">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c6a15-107">\<authenticationModules> 元素（网络设置）</span><span class="sxs-lookup"><span data-stu-id="c6a15-107">\<authenticationModules> Element (Network Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/authenticationmodules-element-network-settings.md)|<span data-ttu-id="c6a15-108">指定用于验证 Internet 请求的模块。</span><span class="sxs-lookup"><span data-stu-id="c6a15-108">Specifies the modules used to authenticate Internet requests.</span></span>|  
|[<span data-ttu-id="c6a15-109">\<connectionManagement> 元素（网络设置）</span><span class="sxs-lookup"><span data-stu-id="c6a15-109">\<connectionManagement> Element (Network Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/connectionmanagement-element-network-settings.md)|<span data-ttu-id="c6a15-110">指定到 Internet 主机的最大连接数。</span><span class="sxs-lookup"><span data-stu-id="c6a15-110">Specifies the maximum number of connections to Internet hosts.</span></span>|  
|[<span data-ttu-id="c6a15-111">\<defaultProxy> 元素（网络设置）</span><span class="sxs-lookup"><span data-stu-id="c6a15-111">\<defaultProxy> Element (Network Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/defaultproxy-element-network-settings.md)|<span data-ttu-id="c6a15-112">指定用于路由到 Internet 的 HTTP 请求的代理服务器。</span><span class="sxs-lookup"><span data-stu-id="c6a15-112">Specifies the proxy server used for HTTP requests to the Internet.</span></span>|  
|[<span data-ttu-id="c6a15-113">\<mailSettings> 元素（网络设置）</span><span class="sxs-lookup"><span data-stu-id="c6a15-113">\<mailSettings> Element (Network Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/mailsettings-element-network-settings.md)|<span data-ttu-id="c6a15-114">包含邮件发送选项的设置。</span><span class="sxs-lookup"><span data-stu-id="c6a15-114">Contains settings for mail sending options.</span></span>|  
|[<span data-ttu-id="c6a15-115">\<requestCaching> 元素（网络设置）</span><span class="sxs-lookup"><span data-stu-id="c6a15-115">\<requestCaching> Element (Network Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/requestcaching-element-network-settings.md)|<span data-ttu-id="c6a15-116">指定用于从 Internet 主机请求信息的模块。</span><span class="sxs-lookup"><span data-stu-id="c6a15-116">Specifies the modules used to request information from Internet hosts.</span></span>|  
|[<span data-ttu-id="c6a15-117">\<requestCaching> 元素（网络设置）</span><span class="sxs-lookup"><span data-stu-id="c6a15-117">\<requestCaching> Element (Network Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/requestcaching-element-network-settings.md)|<span data-ttu-id="c6a15-118">配置 <xref:System.Net?displayProperty=nameWithType> 命名空间的基本网络选项。</span><span class="sxs-lookup"><span data-stu-id="c6a15-118">Configures basic network options for the <xref:System.Net?displayProperty=nameWithType> namespace.</span></span>|  
|[<span data-ttu-id="c6a15-119">\<webRequestModules> 元素（网络设置）</span><span class="sxs-lookup"><span data-stu-id="c6a15-119">\<webRequestModules> Element (Network Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/webrequestmodules-element-network-settings.md)|<span data-ttu-id="c6a15-120">指定用于从 Internet 主机请求信息的模块。</span><span class="sxs-lookup"><span data-stu-id="c6a15-120">Specifies the modules used to request information from Internet hosts.</span></span>|  
  
 <span data-ttu-id="c6a15-121">URI 设置指定 .NET Framework 如何处理使用统一资源标识符 (URI) 表示的 Web 地址。</span><span class="sxs-lookup"><span data-stu-id="c6a15-121">Uri settings specify how the .NET Framework handles web addresses expressed using uniform resource identifiers (URIs).</span></span> <span data-ttu-id="c6a15-122">下表描述 [\<Uri> 元素（Uri 设置）](../../../../../docs/framework/configure-apps/file-schema/network/uri-element-uri-settings.md)下每个子配置元素的函数。</span><span class="sxs-lookup"><span data-stu-id="c6a15-122">The following table describes the function of each child configuration element under the [\<Uri> Element (Uri Settings)](../../../../../docs/framework/configure-apps/file-schema/network/uri-element-uri-settings.md).</span></span>  
  
|<span data-ttu-id="c6a15-123">元素</span><span class="sxs-lookup"><span data-stu-id="c6a15-123">Element</span></span>|<span data-ttu-id="c6a15-124">描述</span><span class="sxs-lookup"><span data-stu-id="c6a15-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c6a15-125">\<idn> 元素（Uri 设置）</span><span class="sxs-lookup"><span data-stu-id="c6a15-125">\<idn> Element (Uri Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/idn-element-uri-settings.md)|<span data-ttu-id="c6a15-126">指定是否对域名应用国际化域名 (IDN) 分析。</span><span class="sxs-lookup"><span data-stu-id="c6a15-126">Specifies if Internationalized Domain Name (IDN) parsing is applied to domain names.</span></span>|  
|[<span data-ttu-id="c6a15-127">\<iriParsing> 元素（Uri 设置）</span><span class="sxs-lookup"><span data-stu-id="c6a15-127">\<iriParsing> Element (Uri Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/iriparsing-element-uri-settings.md)|<span data-ttu-id="c6a15-128">指定是否对 <xref:System.Uri> 应用国际资源标识符 (IRI) 分析以及是否应该应用 IRI 分析规则。</span><span class="sxs-lookup"><span data-stu-id="c6a15-128">Specifies if International Resource Identifier (IRI) parsing is applied to a <xref:System.Uri> and whether IRI parsing rules should be applied.</span></span>|  
|[<span data-ttu-id="c6a15-129">\<schemeSettings> 元素（Uri 设置）</span><span class="sxs-lookup"><span data-stu-id="c6a15-129">\<schemeSettings> Element (Uri Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/schemesettings-element-uri-settings.md)|<span data-ttu-id="c6a15-130">指定如何分析特定方案的 <xref:System.Uri>。</span><span class="sxs-lookup"><span data-stu-id="c6a15-130">Specifies how a <xref:System.Uri> will be parsed for specific schemes.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c6a15-131">请参阅</span><span class="sxs-lookup"><span data-stu-id="c6a15-131">See Also</span></span>  
 [<span data-ttu-id="c6a15-132">配置 Internet 应用程序</span><span class="sxs-lookup"><span data-stu-id="c6a15-132">Configuring Internet Applications</span></span>](../../../../../docs/framework/network-programming/configuring-internet-applications.md)  
 [<span data-ttu-id="c6a15-133">配置文件架构</span><span class="sxs-lookup"><span data-stu-id="c6a15-133">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)
