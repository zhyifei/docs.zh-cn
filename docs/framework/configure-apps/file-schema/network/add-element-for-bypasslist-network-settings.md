---
title: bypasslist 的 <add> 元素（网络设置）
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/defaultProxy/bypasslist/add
- http://schemas.microsoft.com/.NetConfiguration/v2.0#add
helpviewer_keywords:
- <bypasslist>, add element
- bypasslist, add element
- <add> element, bypasslist
- add element, bypasslist
ms.assetid: a0b86e28-86b4-4497-abe8-d5fd614c7926
ms.openlocfilehash: 652b8738a201aaa98fa2c5c435fee1a6da91673b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79155072"
---
# <a name="add-element-for-bypasslist-network-settings"></a><span data-ttu-id="f9ea6-102">\<添加>元素以进行绕过列表（网络设置）</span><span class="sxs-lookup"><span data-stu-id="f9ea6-102">\<add> Element for bypasslist (Network Settings)</span></span>
<span data-ttu-id="f9ea6-103">将 IP 地址或 DNS 名称添加到代理绕过列表中。</span><span class="sxs-lookup"><span data-stu-id="f9ea6-103">Adds an IP address or DNS name to the proxy bypass list.</span></span>  
  
[<span data-ttu-id="f9ea6-104">**\<配置>**</span><span class="sxs-lookup"><span data-stu-id="f9ea6-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="f9ea6-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="f9ea6-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span></span>  
<span data-ttu-id="f9ea6-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<默认代理>**](defaultproxy-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="f9ea6-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<defaultProxy>**](defaultproxy-element-network-settings.md)</span></span>  
<span data-ttu-id="f9ea6-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<绕过列表>**](bypasslist-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="f9ea6-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<bypasslist>**](bypasslist-element-network-settings.md)</span></span>  
<span data-ttu-id="f9ea6-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<添加>**</span><span class="sxs-lookup"><span data-stu-id="f9ea6-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f9ea6-109">语法</span><span class="sxs-lookup"><span data-stu-id="f9ea6-109">Syntax</span></span>  
  
```xml  
<add
  address="regular expression"
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f9ea6-110">特性和元素</span><span class="sxs-lookup"><span data-stu-id="f9ea6-110">Attributes and Elements</span></span>  
 <span data-ttu-id="f9ea6-111">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="f9ea6-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f9ea6-112">属性</span><span class="sxs-lookup"><span data-stu-id="f9ea6-112">Attributes</span></span>  
  
|<span data-ttu-id="f9ea6-113">**属性**</span><span class="sxs-lookup"><span data-stu-id="f9ea6-113">**Attribute**</span></span>|<span data-ttu-id="f9ea6-114">**说明**</span><span class="sxs-lookup"><span data-stu-id="f9ea6-114">**Description**</span></span>|  
|-------------------|---------------------|  
|<span data-ttu-id="f9ea6-115">**address**</span><span class="sxs-lookup"><span data-stu-id="f9ea6-115">**address**</span></span>|<span data-ttu-id="f9ea6-116">描述 IP 地址或 DNS 名称的正则表达式。</span><span class="sxs-lookup"><span data-stu-id="f9ea6-116">A regular expression describing an IP address or DNS name.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f9ea6-117">子元素</span><span class="sxs-lookup"><span data-stu-id="f9ea6-117">Child Elements</span></span>  
 <span data-ttu-id="f9ea6-118">无。</span><span class="sxs-lookup"><span data-stu-id="f9ea6-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="f9ea6-119">父元素</span><span class="sxs-lookup"><span data-stu-id="f9ea6-119">Parent Elements</span></span>  
  
|<span data-ttu-id="f9ea6-120">**元素**</span><span class="sxs-lookup"><span data-stu-id="f9ea6-120">**Element**</span></span>|<span data-ttu-id="f9ea6-121">**说明**</span><span class="sxs-lookup"><span data-stu-id="f9ea6-121">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="f9ea6-122">bypasslist</span><span class="sxs-lookup"><span data-stu-id="f9ea6-122">bypasslist</span></span>](bypasslist-element-network-settings.md)|<span data-ttu-id="f9ea6-123">提供一组常规表达式，用于描述不使用代理的地址。</span><span class="sxs-lookup"><span data-stu-id="f9ea6-123">Provides a set of regular expressions that describe addresses that do not use a proxy.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f9ea6-124">备注</span><span class="sxs-lookup"><span data-stu-id="f9ea6-124">Remarks</span></span>  
 <span data-ttu-id="f9ea6-125">该`add`元素将描述 IP 地址或 DNS 服务器名称的正则表达式插入绕过代理服务器的地址列表中。</span><span class="sxs-lookup"><span data-stu-id="f9ea6-125">The `add` element inserts regular expressions describing IP addresses or DNS server names to the list of addresses that bypass a proxy server.</span></span>  
  
 <span data-ttu-id="f9ea6-126">`address`属性的值应是描述一组 IP 地址或主机名的正则表达式。</span><span class="sxs-lookup"><span data-stu-id="f9ea6-126">The value of the `address` attribute should be a regular expression that describes a set of IP addresses or host names.</span></span>  
  
 <span data-ttu-id="f9ea6-127">为此元素指定正则表达式时应小心谨慎。</span><span class="sxs-lookup"><span data-stu-id="f9ea6-127">You should use caution when specifying a regular expression for this element.</span></span> <span data-ttu-id="f9ea6-128">正则表达式"[a-z].contoso\\\\.com"与contoso.com域中的任何主机匹配，但它也与contoso.com.cpandl.com域中的任何主机匹配。</span><span class="sxs-lookup"><span data-stu-id="f9ea6-128">The regular expression "[a-z]+\\.contoso\\.com" matches any host in the contoso.com domain, but it also matches any host in the contoso.com.cpandl.com domain.</span></span> <span data-ttu-id="f9ea6-129">要仅匹配contoso.com域中的主机，请使用锚点（"$"）："[a-z].contoso.com$"。\\\\</span><span class="sxs-lookup"><span data-stu-id="f9ea6-129">To match only a host in the contoso.com domain, use an anchor ("$"): "[a-z]+\\.contoso\\.com$".</span></span>  
  
 <span data-ttu-id="f9ea6-130">有关正则表达式的详细信息，请参阅。[.NET 框架正则表达式](../../../../standard/base-types/regular-expressions.md)。</span><span class="sxs-lookup"><span data-stu-id="f9ea6-130">For more information about regular expressions, see .[.NET Framework Regular Expressions](../../../../standard/base-types/regular-expressions.md).</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="f9ea6-131">配置文件</span><span class="sxs-lookup"><span data-stu-id="f9ea6-131">Configuration Files</span></span>  
 <span data-ttu-id="f9ea6-132">此元素可在应用程序配置文件或计算机配置文件 (Machine.config) 中使用。</span><span class="sxs-lookup"><span data-stu-id="f9ea6-132">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="f9ea6-133">示例</span><span class="sxs-lookup"><span data-stu-id="f9ea6-133">Example</span></span>  
 <span data-ttu-id="f9ea6-134">下面的示例将两个地址添加到旁路列表中。</span><span class="sxs-lookup"><span data-stu-id="f9ea6-134">The following example adds two addresses to the bypass list.</span></span> <span data-ttu-id="f9ea6-135">第一个绕过contoso.com域中所有服务器的代理;第二个服务器绕过其 IP 地址以 192.168 开头的所有服务器的代理。</span><span class="sxs-lookup"><span data-stu-id="f9ea6-135">The first bypasses the proxy for all servers in the contoso.com domain; the second bypasses the proxy for all servers whose IP address begins with 192.168.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="f9ea6-136">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f9ea6-136">See also</span></span>

- <xref:System.Net.WebProxy?displayProperty=nameWithType>
- [<span data-ttu-id="f9ea6-137">网络设置架构</span><span class="sxs-lookup"><span data-stu-id="f9ea6-137">Network Settings Schema</span></span>](index.md)
