---
title: <bypasslist> 元素（网络设置）
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#bypasslist
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/defaultProxy/bypasslist
helpviewer_keywords:
- bypasslist element
- <bypasslist> element
ms.assetid: 124446b7-abb1-4e5e-a492-b64398f268f1
ms.openlocfilehash: 97e69a4978aa4700d13a994619a65312cf70aeaa
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79154941"
---
# <a name="bypasslist-element-network-settings"></a><span data-ttu-id="e5a3b-102">\<绕过列表>元素（网络设置）</span><span class="sxs-lookup"><span data-stu-id="e5a3b-102">\<bypasslist> Element (Network Settings)</span></span>
<span data-ttu-id="e5a3b-103">提供一组常规表达式，用于描述不使用代理的地址。</span><span class="sxs-lookup"><span data-stu-id="e5a3b-103">Provides a set of regular expressions that describe addresses that do not use a proxy.</span></span>  

<span data-ttu-id="e5a3b-104">[**\<配置>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="e5a3b-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="e5a3b-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="e5a3b-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span></span>\
<span data-ttu-id="e5a3b-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<默认代理>**](defaultproxy-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="e5a3b-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<defaultProxy>**](defaultproxy-element-network-settings.md)</span></span>\
<span data-ttu-id="e5a3b-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<绕过列表>**</span><span class="sxs-lookup"><span data-stu-id="e5a3b-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<bypasslist>**</span></span>

## <a name="syntax"></a><span data-ttu-id="e5a3b-108">语法</span><span class="sxs-lookup"><span data-stu-id="e5a3b-108">Syntax</span></span>  
  
```xml  
<bypasslist>
</bypasslist>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e5a3b-109">特性和元素</span><span class="sxs-lookup"><span data-stu-id="e5a3b-109">Attributes and Elements</span></span>  
 <span data-ttu-id="e5a3b-110">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="e5a3b-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e5a3b-111">属性</span><span class="sxs-lookup"><span data-stu-id="e5a3b-111">Attributes</span></span>  
 <span data-ttu-id="e5a3b-112">无。</span><span class="sxs-lookup"><span data-stu-id="e5a3b-112">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="e5a3b-113">子元素</span><span class="sxs-lookup"><span data-stu-id="e5a3b-113">Child Elements</span></span>  
  
|<span data-ttu-id="e5a3b-114">**元素**</span><span class="sxs-lookup"><span data-stu-id="e5a3b-114">**Element**</span></span>|<span data-ttu-id="e5a3b-115">**说明**</span><span class="sxs-lookup"><span data-stu-id="e5a3b-115">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="e5a3b-116">添加</span><span class="sxs-lookup"><span data-stu-id="e5a3b-116">add</span></span>](add-element-for-bypasslist-network-settings.md)|<span data-ttu-id="e5a3b-117">将 IP 地址或 DNS 名称添加到代理绕过列表中。</span><span class="sxs-lookup"><span data-stu-id="e5a3b-117">Adds an IP address or DNS name to the proxy bypass list.</span></span>|  
|[<span data-ttu-id="e5a3b-118">清楚</span><span class="sxs-lookup"><span data-stu-id="e5a3b-118">clear</span></span>](clear-element-for-bypasslist-network-settings.md)|<span data-ttu-id="e5a3b-119">清除旁路列表。</span><span class="sxs-lookup"><span data-stu-id="e5a3b-119">Clears the bypass list.</span></span>|  
|[<span data-ttu-id="e5a3b-120">删除</span><span class="sxs-lookup"><span data-stu-id="e5a3b-120">remove</span></span>](remove-element-for-bypasslist-network-settings.md)|<span data-ttu-id="e5a3b-121">从代理绕过列表中删除 IP 地址或 DNS 名称。</span><span class="sxs-lookup"><span data-stu-id="e5a3b-121">Removes an IP address or DNS name from the proxy bypass list.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="e5a3b-122">父元素</span><span class="sxs-lookup"><span data-stu-id="e5a3b-122">Parent Elements</span></span>  
  
|<span data-ttu-id="e5a3b-123">**元素**</span><span class="sxs-lookup"><span data-stu-id="e5a3b-123">**Element**</span></span>|<span data-ttu-id="e5a3b-124">**说明**</span><span class="sxs-lookup"><span data-stu-id="e5a3b-124">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="e5a3b-125">defaultProxy</span><span class="sxs-lookup"><span data-stu-id="e5a3b-125">defaultProxy</span></span>](defaultproxy-element-network-settings.md)|<span data-ttu-id="e5a3b-126">配置超文本传输协议 (HTTP) 代理服务器。</span><span class="sxs-lookup"><span data-stu-id="e5a3b-126">Configures the Hypertext Transfer Protocol (HTTP) proxy server.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e5a3b-127">备注</span><span class="sxs-lookup"><span data-stu-id="e5a3b-127">Remarks</span></span>  
 <span data-ttu-id="e5a3b-128">旁路列表包含常规表达式，用于描述<xref:System.Net.WebRequest>实例直接访问而不是通过代理服务器访问的 URI。</span><span class="sxs-lookup"><span data-stu-id="e5a3b-128">The bypass list contains regular expressions that describe URIs that <xref:System.Net.WebRequest> instances access directly instead of through the proxy server.</span></span>  
  
 <span data-ttu-id="e5a3b-129">为此元素指定正则表达式时应小心谨慎。</span><span class="sxs-lookup"><span data-stu-id="e5a3b-129">You should use caution when specifying a regular expression for this element.</span></span> <span data-ttu-id="e5a3b-130">正则表达式"[a-z].contoso\\\\.com"与contoso.com域中的任何主机匹配，但它也与contoso.com.cpandl.com域中的任何主机匹配。</span><span class="sxs-lookup"><span data-stu-id="e5a3b-130">The regular expression "[a-z]+\\.contoso\\.com" matches any host in the contoso.com domain, but it also matches any host in the contoso.com.cpandl.com domain.</span></span> <span data-ttu-id="e5a3b-131">要仅匹配contoso.com域中的主机，请使用锚点（"$"）："[a-z].contoso.com$"。\\\\</span><span class="sxs-lookup"><span data-stu-id="e5a3b-131">To match only a host in the contoso.com domain, use an anchor ("$"): "[a-z]+\\.contoso\\.com$".</span></span>  
  
 <span data-ttu-id="e5a3b-132">有关正则表达式的详细信息，请参阅。[.NET 框架正则表达式](../../../../standard/base-types/regular-expressions.md)。</span><span class="sxs-lookup"><span data-stu-id="e5a3b-132">For more information about regular expressions, see .[.NET Framework Regular Expressions](../../../../standard/base-types/regular-expressions.md).</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="e5a3b-133">配置文件</span><span class="sxs-lookup"><span data-stu-id="e5a3b-133">Configuration Files</span></span>  
 <span data-ttu-id="e5a3b-134">此元素可在应用程序配置文件或计算机配置文件 (Machine.config) 中使用。</span><span class="sxs-lookup"><span data-stu-id="e5a3b-134">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="e5a3b-135">示例</span><span class="sxs-lookup"><span data-stu-id="e5a3b-135">Example</span></span>  
 <span data-ttu-id="e5a3b-136">下面的示例将两个地址添加到旁路列表中。</span><span class="sxs-lookup"><span data-stu-id="e5a3b-136">The following example adds two addresses to the bypass list.</span></span> <span data-ttu-id="e5a3b-137">第一个绕过contoso.com域中所有服务器的代理;第二个服务器绕过其 IP 地址以 192.168 开头的所有服务器的代理。</span><span class="sxs-lookup"><span data-stu-id="e5a3b-137">The first bypasses the proxy for all servers in the contoso.com domain; the second bypasses the proxy for all servers whose IP addresses begin with 192.168.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="e5a3b-138">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e5a3b-138">See also</span></span>

- <xref:System.Net.WebProxy?displayProperty=nameWithType>
- [<span data-ttu-id="e5a3b-139">网络设置架构</span><span class="sxs-lookup"><span data-stu-id="e5a3b-139">Network Settings Schema</span></span>](index.md)
