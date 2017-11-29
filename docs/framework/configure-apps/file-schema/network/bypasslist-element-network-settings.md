---
title: "&lt;将 bypasslist&gt;元素 （网络设置）"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#bypasslist
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/defaultProxy/bypasslist
helpviewer_keywords:
- bypasslist element
- <bypasslist> element
ms.assetid: 124446b7-abb1-4e5e-a492-b64398f268f1
caps.latest.revision: "17"
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 3d349f14535de806e0b130ef64b58333e63f1b86
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="ltbypasslistgt-element-network-settings"></a><span data-ttu-id="e9469-102">&lt;将 bypasslist&gt;元素 （网络设置）</span><span class="sxs-lookup"><span data-stu-id="e9469-102">&lt;bypasslist&gt; Element (Network Settings)</span></span>
<span data-ttu-id="e9469-103">提供一组描述不使用代理的地址的正则表达式。</span><span class="sxs-lookup"><span data-stu-id="e9469-103">Provides a set of regular expressions that describe addresses that do not use a proxy.</span></span>  
  
 <span data-ttu-id="e9469-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="e9469-104">\<configuration></span></span>  
<span data-ttu-id="e9469-105">\<system.net ></span><span class="sxs-lookup"><span data-stu-id="e9469-105">\<system.net></span></span>  
<span data-ttu-id="e9469-106">\<defaultProxy ></span><span class="sxs-lookup"><span data-stu-id="e9469-106">\<defaultProxy></span></span>  
<span data-ttu-id="e9469-107">\<将 bypasslist ></span><span class="sxs-lookup"><span data-stu-id="e9469-107">\<bypasslist></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e9469-108">语法</span><span class="sxs-lookup"><span data-stu-id="e9469-108">Syntax</span></span>  
  
```xml  
<bypasslist>   
</bypasslist>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e9469-109">特性和元素</span><span class="sxs-lookup"><span data-stu-id="e9469-109">Attributes and Elements</span></span>  
 <span data-ttu-id="e9469-110">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="e9469-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e9469-111">特性</span><span class="sxs-lookup"><span data-stu-id="e9469-111">Attributes</span></span>  
 <span data-ttu-id="e9469-112">无。</span><span class="sxs-lookup"><span data-stu-id="e9469-112">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="e9469-113">子元素</span><span class="sxs-lookup"><span data-stu-id="e9469-113">Child Elements</span></span>  
  
|<span data-ttu-id="e9469-114">**元素**</span><span class="sxs-lookup"><span data-stu-id="e9469-114">**Element**</span></span>|<span data-ttu-id="e9469-115">**描述**</span><span class="sxs-lookup"><span data-stu-id="e9469-115">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="e9469-116">add</span><span class="sxs-lookup"><span data-stu-id="e9469-116">add</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/add-element-for-bypasslist-network-settings.md)|<span data-ttu-id="e9469-117">将 IP 地址或 DNS 名称添加到代理绕过列表。</span><span class="sxs-lookup"><span data-stu-id="e9469-117">Adds an IP address or DNS name to the proxy bypass list.</span></span>|  
|[<span data-ttu-id="e9469-118">clear</span><span class="sxs-lookup"><span data-stu-id="e9469-118">clear</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/clear-element-for-bypasslist-network-settings.md)|<span data-ttu-id="e9469-119">清除跳过列表。</span><span class="sxs-lookup"><span data-stu-id="e9469-119">Clears the bypass list.</span></span>|  
|[<span data-ttu-id="e9469-120">remove</span><span class="sxs-lookup"><span data-stu-id="e9469-120">remove</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/remove-element-for-bypasslist-network-settings.md)|<span data-ttu-id="e9469-121">从代理绕过列表中删除 IP 地址或 DNS 名称。</span><span class="sxs-lookup"><span data-stu-id="e9469-121">Removes an IP address or DNS name from the proxy bypass list.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="e9469-122">父元素</span><span class="sxs-lookup"><span data-stu-id="e9469-122">Parent Elements</span></span>  
  
|<span data-ttu-id="e9469-123">**元素**</span><span class="sxs-lookup"><span data-stu-id="e9469-123">**Element**</span></span>|<span data-ttu-id="e9469-124">**描述**</span><span class="sxs-lookup"><span data-stu-id="e9469-124">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="e9469-125">defaultProxy</span><span class="sxs-lookup"><span data-stu-id="e9469-125">defaultProxy</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/defaultproxy-element-network-settings.md)|<span data-ttu-id="e9469-126">配置超文本传输协议 (HTTP) 代理服务器。</span><span class="sxs-lookup"><span data-stu-id="e9469-126">Configures the Hypertext Transfer Protocol (HTTP) proxy server.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e9469-127">备注</span><span class="sxs-lookup"><span data-stu-id="e9469-127">Remarks</span></span>  
 <span data-ttu-id="e9469-128">跳过列表包含描述 Uri 的正则表达式，<xref:System.Net.WebRequest>实例而不是直接访问通过代理服务器。</span><span class="sxs-lookup"><span data-stu-id="e9469-128">The bypass list contains regular expressions that describe URIs that <xref:System.Net.WebRequest> instances access directly instead of through the proxy server.</span></span>  
  
 <span data-ttu-id="e9469-129">指定此元素的正则表达式时，应使用警告。</span><span class="sxs-lookup"><span data-stu-id="e9469-129">You should use caution when specifying a regular expression for this element.</span></span> <span data-ttu-id="e9469-130">正则表达式"[a 到 z] +\\.contoso\\.com"匹配任何承载在 contoso.com 域，但它还将匹配 contoso.com.cpandl.com 域中的任何主机。</span><span class="sxs-lookup"><span data-stu-id="e9469-130">The regular expression "[a-z]+\\.contoso\\.com" matches any host in the contoso.com domain, but it also matches any host in the contoso.com.cpandl.com domain.</span></span> <span data-ttu-id="e9469-131">若要匹配仅在 contoso.com 域中的主机，使用的定位点 （"$"）:"[a 到 z] +\\.contoso\\.com$"。</span><span class="sxs-lookup"><span data-stu-id="e9469-131">To match only a host in the contoso.com domain, use an anchor ("$"): "[a-z]+\\.contoso\\.com$".</span></span>  
  
 <span data-ttu-id="e9469-132">有关正则表达式的详细信息，请参阅。[.NET framework 正则表达式](../../../../../docs/standard/base-types/regular-expressions.md)。</span><span class="sxs-lookup"><span data-stu-id="e9469-132">For more information about regular expressions, see .[.NET Framework Regular Expressions](../../../../../docs/standard/base-types/regular-expressions.md).</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="e9469-133">配置文件</span><span class="sxs-lookup"><span data-stu-id="e9469-133">Configuration Files</span></span>  
 <span data-ttu-id="e9469-134">此元素可在应用程序配置文件或计算机配置文件 (Machine.config) 中使用。</span><span class="sxs-lookup"><span data-stu-id="e9469-134">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="e9469-135">示例</span><span class="sxs-lookup"><span data-stu-id="e9469-135">Example</span></span>  
 <span data-ttu-id="e9469-136">下面的示例将两个地址添加到跳过列表。</span><span class="sxs-lookup"><span data-stu-id="e9469-136">The following example adds two addresses to the bypass list.</span></span> <span data-ttu-id="e9469-137">第一个绕过用于 contoso.com 域; 中的所有服务器的代理第二个绕过用于与 192.168 其 IP 地址开始的所有服务器的代理。</span><span class="sxs-lookup"><span data-stu-id="e9469-137">The first bypasses the proxy for all servers in the contoso.com domain; the second bypasses the proxy for all servers whose IP addresses begin with 192.168.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <defaultProxy>  
      <bypasslist>  
        <add address="[a-z]+\.contoso\.com$" />  
        <add address="192\.168\.\d{1,3}\.\d{1,3}" />  
      </bypasslist>  
    </defaultProxy>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="e9469-138">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e9469-138">See Also</span></span>  
 <xref:System.Net.WebProxy?displayProperty=nameWithType>  
 [<span data-ttu-id="e9469-139">网络设置架构</span><span class="sxs-lookup"><span data-stu-id="e9469-139">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
