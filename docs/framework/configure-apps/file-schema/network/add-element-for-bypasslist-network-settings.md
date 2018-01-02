---
title: "&lt;添加&gt;将 bypasslist （网络设置） 的元素"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/defaultProxy/bypasslist/add
- http://schemas.microsoft.com/.NetConfiguration/v2.0#add
helpviewer_keywords:
- <bypasslist>, add element
- bypasslist, add element
- <add> element, bypasslist
- add element, bypasslist
ms.assetid: a0b86e28-86b4-4497-abe8-d5fd614c7926
caps.latest.revision: "17"
author: mcleblanc
ms.author: markl
manager: markl
ms.workload: dotnet
ms.openlocfilehash: bed3abd5522b748a2bd24ba03c7be5d991deae9a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="ltaddgt-element-for-bypasslist-network-settings"></a><span data-ttu-id="ac800-102">&lt;添加&gt;将 bypasslist （网络设置） 的元素</span><span class="sxs-lookup"><span data-stu-id="ac800-102">&lt;add&gt; Element for bypasslist (Network Settings)</span></span>
<span data-ttu-id="ac800-103">将 IP 地址或 DNS 名称添加到代理绕过列表。</span><span class="sxs-lookup"><span data-stu-id="ac800-103">Adds an IP address or DNS name to the proxy bypass list.</span></span>  
  
 <span data-ttu-id="ac800-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="ac800-104">\<configuration></span></span>  
<span data-ttu-id="ac800-105">\<system.net ></span><span class="sxs-lookup"><span data-stu-id="ac800-105">\<system.net></span></span>  
<span data-ttu-id="ac800-106">\<defaultProxy ></span><span class="sxs-lookup"><span data-stu-id="ac800-106">\<defaultProxy></span></span>  
<span data-ttu-id="ac800-107">\<将 bypasslist ></span><span class="sxs-lookup"><span data-stu-id="ac800-107">\<bypasslist></span></span>  
<span data-ttu-id="ac800-108">\<add></span><span class="sxs-lookup"><span data-stu-id="ac800-108">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ac800-109">语法</span><span class="sxs-lookup"><span data-stu-id="ac800-109">Syntax</span></span>  
  
```xml  
<add   
  address="regular expression"   
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ac800-110">特性和元素</span><span class="sxs-lookup"><span data-stu-id="ac800-110">Attributes and Elements</span></span>  
 <span data-ttu-id="ac800-111">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="ac800-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ac800-112">特性</span><span class="sxs-lookup"><span data-stu-id="ac800-112">Attributes</span></span>  
  
|<span data-ttu-id="ac800-113">**特性**</span><span class="sxs-lookup"><span data-stu-id="ac800-113">**Attribute**</span></span>|<span data-ttu-id="ac800-114">**说明**</span><span class="sxs-lookup"><span data-stu-id="ac800-114">**Description**</span></span>|  
|-------------------|---------------------|  
|<span data-ttu-id="ac800-115">**address**</span><span class="sxs-lookup"><span data-stu-id="ac800-115">**address**</span></span>|<span data-ttu-id="ac800-116">正则表达式描述的 IP 地址或 DNS 名称。</span><span class="sxs-lookup"><span data-stu-id="ac800-116">A regular expression describing an IP address or DNS name.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ac800-117">子元素</span><span class="sxs-lookup"><span data-stu-id="ac800-117">Child Elements</span></span>  
 <span data-ttu-id="ac800-118">无。</span><span class="sxs-lookup"><span data-stu-id="ac800-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="ac800-119">父元素</span><span class="sxs-lookup"><span data-stu-id="ac800-119">Parent Elements</span></span>  
  
|<span data-ttu-id="ac800-120">**元素**</span><span class="sxs-lookup"><span data-stu-id="ac800-120">**Element**</span></span>|<span data-ttu-id="ac800-121">**说明**</span><span class="sxs-lookup"><span data-stu-id="ac800-121">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="ac800-122">将 bypasslist</span><span class="sxs-lookup"><span data-stu-id="ac800-122">bypasslist</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/bypasslist-element-network-settings.md)|<span data-ttu-id="ac800-123">提供一组描述不使用代理的地址的正则表达式。</span><span class="sxs-lookup"><span data-stu-id="ac800-123">Provides a set of regular expressions that describe addresses that do not use a proxy.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ac800-124">备注</span><span class="sxs-lookup"><span data-stu-id="ac800-124">Remarks</span></span>  
 <span data-ttu-id="ac800-125">`add`元素插入正则表达式描述 IP 地址或 DNS 服务器名称的绕过代理服务器的地址的列表。</span><span class="sxs-lookup"><span data-stu-id="ac800-125">The `add` element inserts regular expressions describing IP addresses or DNS server names to the list of addresses that bypass a proxy server.</span></span>  
  
 <span data-ttu-id="ac800-126">值`address`属性应为正则表达式描述一组 IP 地址或主机名。</span><span class="sxs-lookup"><span data-stu-id="ac800-126">The value of the `address` attribute should be a regular expression that describes a set of IP addresses or host names.</span></span>  
  
 <span data-ttu-id="ac800-127">指定此元素的正则表达式时，应使用警告。</span><span class="sxs-lookup"><span data-stu-id="ac800-127">You should use caution when specifying a regular expression for this element.</span></span> <span data-ttu-id="ac800-128">正则表达式"[a 到 z] +\\.contoso\\.com"匹配任何承载在 contoso.com 域，但它还将匹配 contoso.com.cpandl.com 域中的任何主机。</span><span class="sxs-lookup"><span data-stu-id="ac800-128">The regular expression "[a-z]+\\.contoso\\.com" matches any host in the contoso.com domain, but it also matches any host in the contoso.com.cpandl.com domain.</span></span> <span data-ttu-id="ac800-129">若要匹配仅在 contoso.com 域中的主机，使用的定位点 （"$"）:"[a 到 z] +\\.contoso\\.com$"。</span><span class="sxs-lookup"><span data-stu-id="ac800-129">To match only a host in the contoso.com domain, use an anchor ("$"): "[a-z]+\\.contoso\\.com$".</span></span>  
  
 <span data-ttu-id="ac800-130">有关正则表达式的详细信息，请参阅。[.NET framework 正则表达式](../../../../../docs/standard/base-types/regular-expressions.md)。</span><span class="sxs-lookup"><span data-stu-id="ac800-130">For more information about regular expressions, see .[.NET Framework Regular Expressions](../../../../../docs/standard/base-types/regular-expressions.md).</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="ac800-131">配置文件</span><span class="sxs-lookup"><span data-stu-id="ac800-131">Configuration Files</span></span>  
 <span data-ttu-id="ac800-132">此元素可在应用程序配置文件或计算机配置文件 (Machine.config) 中使用。</span><span class="sxs-lookup"><span data-stu-id="ac800-132">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="ac800-133">示例</span><span class="sxs-lookup"><span data-stu-id="ac800-133">Example</span></span>  
 <span data-ttu-id="ac800-134">下面的示例将两个地址添加到跳过列表。</span><span class="sxs-lookup"><span data-stu-id="ac800-134">The following example adds two addresses to the bypass list.</span></span> <span data-ttu-id="ac800-135">第一个绕过用于 contoso.com 域; 中的所有服务器的代理第二个绕过用于与 192.168 其 IP 地址开始的所有服务器的代理。</span><span class="sxs-lookup"><span data-stu-id="ac800-135">The first bypasses the proxy for all servers in the contoso.com domain; the second bypasses the proxy for all servers whose IP address begins with 192.168.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="ac800-136">请参阅</span><span class="sxs-lookup"><span data-stu-id="ac800-136">See Also</span></span>  
 <xref:System.Net.WebProxy?displayProperty=nameWithType>  
 [<span data-ttu-id="ac800-137">网络设置架构</span><span class="sxs-lookup"><span data-stu-id="ac800-137">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
