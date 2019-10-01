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
ms.openlocfilehash: 1dda43be8c0e0c94bdf7b57b67aa4d403b547f97
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/01/2019
ms.locfileid: "71699546"
---
# <a name="bypasslist-element-network-settings"></a><span data-ttu-id="80a18-102">\<bypasslist > 元素（网络设置）</span><span class="sxs-lookup"><span data-stu-id="80a18-102">\<bypasslist> Element (Network Settings)</span></span>
<span data-ttu-id="80a18-103">提供了一组正则表达式，描述不使用代理的地址。</span><span class="sxs-lookup"><span data-stu-id="80a18-103">Provides a set of regular expressions that describe addresses that do not use a proxy.</span></span>  
  
[<span data-ttu-id="80a18-104"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="80a18-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="80a18-105">&nbsp; @ no__t[ **\<system >** ](system-net-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="80a18-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span></span>  
<span data-ttu-id="80a18-106">&nbsp; @ no__t-1 @ no__t-2 @ no__t[ **\<defaultProxy >** ](defaultproxy-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="80a18-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<defaultProxy>**](defaultproxy-element-network-settings.md)</span></span>  
<span data-ttu-id="80a18-107">&nbsp; @ no__t-1 @ no__t-2 @ no__t-3 @ no__t-4 @ no__t-5 **\<bypasslist >**</span><span class="sxs-lookup"><span data-stu-id="80a18-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<bypasslist>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="80a18-108">语法</span><span class="sxs-lookup"><span data-stu-id="80a18-108">Syntax</span></span>  
  
```xml  
<bypasslist>   
</bypasslist>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="80a18-109">特性和元素</span><span class="sxs-lookup"><span data-stu-id="80a18-109">Attributes and Elements</span></span>  
 <span data-ttu-id="80a18-110">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="80a18-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="80a18-111">特性</span><span class="sxs-lookup"><span data-stu-id="80a18-111">Attributes</span></span>  
 <span data-ttu-id="80a18-112">无。</span><span class="sxs-lookup"><span data-stu-id="80a18-112">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="80a18-113">子元素</span><span class="sxs-lookup"><span data-stu-id="80a18-113">Child Elements</span></span>  
  
|<span data-ttu-id="80a18-114">**元素**</span><span class="sxs-lookup"><span data-stu-id="80a18-114">**Element**</span></span>|<span data-ttu-id="80a18-115">**说明**</span><span class="sxs-lookup"><span data-stu-id="80a18-115">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="80a18-116">add</span><span class="sxs-lookup"><span data-stu-id="80a18-116">add</span></span>](add-element-for-bypasslist-network-settings.md)|<span data-ttu-id="80a18-117">将 IP 地址或 DNS 名称添加到代理跳过列表。</span><span class="sxs-lookup"><span data-stu-id="80a18-117">Adds an IP address or DNS name to the proxy bypass list.</span></span>|  
|[<span data-ttu-id="80a18-118">clear</span><span class="sxs-lookup"><span data-stu-id="80a18-118">clear</span></span>](clear-element-for-bypasslist-network-settings.md)|<span data-ttu-id="80a18-119">清除跳过列表。</span><span class="sxs-lookup"><span data-stu-id="80a18-119">Clears the bypass list.</span></span>|  
|[<span data-ttu-id="80a18-120">remove</span><span class="sxs-lookup"><span data-stu-id="80a18-120">remove</span></span>](remove-element-for-bypasslist-network-settings.md)|<span data-ttu-id="80a18-121">从代理跳过列表中删除 IP 地址或 DNS 名称。</span><span class="sxs-lookup"><span data-stu-id="80a18-121">Removes an IP address or DNS name from the proxy bypass list.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="80a18-122">父元素</span><span class="sxs-lookup"><span data-stu-id="80a18-122">Parent Elements</span></span>  
  
|<span data-ttu-id="80a18-123">**元素**</span><span class="sxs-lookup"><span data-stu-id="80a18-123">**Element**</span></span>|<span data-ttu-id="80a18-124">**说明**</span><span class="sxs-lookup"><span data-stu-id="80a18-124">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="80a18-125">defaultProxy</span><span class="sxs-lookup"><span data-stu-id="80a18-125">defaultProxy</span></span>](defaultproxy-element-network-settings.md)|<span data-ttu-id="80a18-126">配置超文本传输协议 (HTTP) 代理服务器。</span><span class="sxs-lookup"><span data-stu-id="80a18-126">Configures the Hypertext Transfer Protocol (HTTP) proxy server.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="80a18-127">备注</span><span class="sxs-lookup"><span data-stu-id="80a18-127">Remarks</span></span>  
 <span data-ttu-id="80a18-128">"绕过列表" 包含描述 <xref:System.Net.WebRequest> 实例直接访问而不是通过代理服务器访问的 Uri 的正则表达式。</span><span class="sxs-lookup"><span data-stu-id="80a18-128">The bypass list contains regular expressions that describe URIs that <xref:System.Net.WebRequest> instances access directly instead of through the proxy server.</span></span>  
  
 <span data-ttu-id="80a18-129">为此元素指定正则表达式时，应格外小心。</span><span class="sxs-lookup"><span data-stu-id="80a18-129">You should use caution when specifying a regular expression for this element.</span></span> <span data-ttu-id="80a18-130">正则表达式 "[a-z] + \\.contoso\\.com" 可匹配 contoso.com 域中的任何主机，但它还匹配 contoso.com.cpandl.com 域中的任何主机。</span><span class="sxs-lookup"><span data-stu-id="80a18-130">The regular expression "[a-z]+\\.contoso\\.com" matches any host in the contoso.com domain, but it also matches any host in the contoso.com.cpandl.com domain.</span></span> <span data-ttu-id="80a18-131">若要只匹配 contoso.com 域中的主机，请使用定位点（"$"）： "[a-z] + \\.contoso\\.com $"。</span><span class="sxs-lookup"><span data-stu-id="80a18-131">To match only a host in the contoso.com domain, use an anchor ("$"): "[a-z]+\\.contoso\\.com$".</span></span>  
  
 <span data-ttu-id="80a18-132">有关正则表达式的详细信息，请参阅。[.NET Framework 正则表达式](../../../../standard/base-types/regular-expressions.md)。</span><span class="sxs-lookup"><span data-stu-id="80a18-132">For more information about regular expressions, see .[.NET Framework Regular Expressions](../../../../standard/base-types/regular-expressions.md).</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="80a18-133">配置文件</span><span class="sxs-lookup"><span data-stu-id="80a18-133">Configuration Files</span></span>  
 <span data-ttu-id="80a18-134">此元素可在应用程序配置文件或计算机配置文件 (Machine.config) 中使用。</span><span class="sxs-lookup"><span data-stu-id="80a18-134">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="80a18-135">示例</span><span class="sxs-lookup"><span data-stu-id="80a18-135">Example</span></span>  
 <span data-ttu-id="80a18-136">下面的示例将两个地址添加到跳过列表。</span><span class="sxs-lookup"><span data-stu-id="80a18-136">The following example adds two addresses to the bypass list.</span></span> <span data-ttu-id="80a18-137">首先，将跳过 contoso.com 域中所有服务器的代理;第二种方式是跳过其 IP 地址以192.168 开头的所有服务器的代理。</span><span class="sxs-lookup"><span data-stu-id="80a18-137">The first bypasses the proxy for all servers in the contoso.com domain; the second bypasses the proxy for all servers whose IP addresses begin with 192.168.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="80a18-138">请参阅</span><span class="sxs-lookup"><span data-stu-id="80a18-138">See also</span></span>

- <xref:System.Net.WebProxy?displayProperty=nameWithType>
- [<span data-ttu-id="80a18-139">网络设置架构</span><span class="sxs-lookup"><span data-stu-id="80a18-139">Network Settings Schema</span></span>](index.md)
