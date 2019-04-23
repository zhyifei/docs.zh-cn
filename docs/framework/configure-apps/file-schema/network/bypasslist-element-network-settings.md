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
ms.openlocfilehash: d3d986dae478f49504dae21b9f39574b7887b4d2
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59202217"
---
# <a name="bypasslist-element-network-settings"></a><span data-ttu-id="a0273-102">\<bypasslist > 元素 （网络设置）</span><span class="sxs-lookup"><span data-stu-id="a0273-102">\<bypasslist> Element (Network Settings)</span></span>
<span data-ttu-id="a0273-103">提供一组描述不使用代理的地址的正则表达式。</span><span class="sxs-lookup"><span data-stu-id="a0273-103">Provides a set of regular expressions that describe addresses that do not use a proxy.</span></span>  
  
 <span data-ttu-id="a0273-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="a0273-104">\<configuration></span></span>  
<span data-ttu-id="a0273-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="a0273-105">\<system.net></span></span>  
<span data-ttu-id="a0273-106">\<defaultProxy ></span><span class="sxs-lookup"><span data-stu-id="a0273-106">\<defaultProxy></span></span>  
<span data-ttu-id="a0273-107">\<bypasslist ></span><span class="sxs-lookup"><span data-stu-id="a0273-107">\<bypasslist></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a0273-108">语法</span><span class="sxs-lookup"><span data-stu-id="a0273-108">Syntax</span></span>  
  
```xml  
<bypasslist>   
</bypasslist>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a0273-109">特性和元素</span><span class="sxs-lookup"><span data-stu-id="a0273-109">Attributes and Elements</span></span>  
 <span data-ttu-id="a0273-110">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="a0273-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a0273-111">特性</span><span class="sxs-lookup"><span data-stu-id="a0273-111">Attributes</span></span>  
 <span data-ttu-id="a0273-112">无。</span><span class="sxs-lookup"><span data-stu-id="a0273-112">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="a0273-113">子元素</span><span class="sxs-lookup"><span data-stu-id="a0273-113">Child Elements</span></span>  
  
|<span data-ttu-id="a0273-114">**元素**</span><span class="sxs-lookup"><span data-stu-id="a0273-114">**Element**</span></span>|<span data-ttu-id="a0273-115">**说明**</span><span class="sxs-lookup"><span data-stu-id="a0273-115">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="a0273-116">add</span><span class="sxs-lookup"><span data-stu-id="a0273-116">add</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/add-element-for-bypasslist-network-settings.md)|<span data-ttu-id="a0273-117">将 IP 地址或 DNS 名称添加到代理跳过列表。</span><span class="sxs-lookup"><span data-stu-id="a0273-117">Adds an IP address or DNS name to the proxy bypass list.</span></span>|  
|[<span data-ttu-id="a0273-118">clear</span><span class="sxs-lookup"><span data-stu-id="a0273-118">clear</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/clear-element-for-bypasslist-network-settings.md)|<span data-ttu-id="a0273-119">清除跳过列表。</span><span class="sxs-lookup"><span data-stu-id="a0273-119">Clears the bypass list.</span></span>|  
|[<span data-ttu-id="a0273-120">remove</span><span class="sxs-lookup"><span data-stu-id="a0273-120">remove</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/remove-element-for-bypasslist-network-settings.md)|<span data-ttu-id="a0273-121">从代理跳过列表中删除 IP 地址或 DNS 名称。</span><span class="sxs-lookup"><span data-stu-id="a0273-121">Removes an IP address or DNS name from the proxy bypass list.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="a0273-122">父元素</span><span class="sxs-lookup"><span data-stu-id="a0273-122">Parent Elements</span></span>  
  
|<span data-ttu-id="a0273-123">**元素**</span><span class="sxs-lookup"><span data-stu-id="a0273-123">**Element**</span></span>|<span data-ttu-id="a0273-124">**说明**</span><span class="sxs-lookup"><span data-stu-id="a0273-124">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="a0273-125">defaultProxy</span><span class="sxs-lookup"><span data-stu-id="a0273-125">defaultProxy</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/defaultproxy-element-network-settings.md)|<span data-ttu-id="a0273-126">配置超文本传输协议 (HTTP) 代理服务器。</span><span class="sxs-lookup"><span data-stu-id="a0273-126">Configures the Hypertext Transfer Protocol (HTTP) proxy server.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a0273-127">备注</span><span class="sxs-lookup"><span data-stu-id="a0273-127">Remarks</span></span>  
 <span data-ttu-id="a0273-128">跳过列表包含描述 Uri 的正则表达式的<xref:System.Net.WebRequest>实例而不是直接访问通过代理服务器。</span><span class="sxs-lookup"><span data-stu-id="a0273-128">The bypass list contains regular expressions that describe URIs that <xref:System.Net.WebRequest> instances access directly instead of through the proxy server.</span></span>  
  
 <span data-ttu-id="a0273-129">指定此元素的正则表达式时应十分小心。</span><span class="sxs-lookup"><span data-stu-id="a0273-129">You should use caution when specifying a regular expression for this element.</span></span> <span data-ttu-id="a0273-130">正则表达式"[a-z] +\\.contoso\\.com"匹配任意主机在 contoso.com 域，但它还将匹配 contoso.com.cpandl.com 域中的任何主机。</span><span class="sxs-lookup"><span data-stu-id="a0273-130">The regular expression "[a-z]+\\.contoso\\.com" matches any host in the contoso.com domain, but it also matches any host in the contoso.com.cpandl.com domain.</span></span> <span data-ttu-id="a0273-131">若要匹配仅在 contoso.com 域中的主机，使用的定位点 （"$"）:"[a-z] +\\.contoso\\.com$"。</span><span class="sxs-lookup"><span data-stu-id="a0273-131">To match only a host in the contoso.com domain, use an anchor ("$"): "[a-z]+\\.contoso\\.com$".</span></span>  
  
 <span data-ttu-id="a0273-132">有关正则表达式的详细信息，请参阅。[.NET framework 正则表达式](../../../../../docs/standard/base-types/regular-expressions.md)。</span><span class="sxs-lookup"><span data-stu-id="a0273-132">For more information about regular expressions, see .[.NET Framework Regular Expressions](../../../../../docs/standard/base-types/regular-expressions.md).</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="a0273-133">配置文件</span><span class="sxs-lookup"><span data-stu-id="a0273-133">Configuration Files</span></span>  
 <span data-ttu-id="a0273-134">此元素可在应用程序配置文件或计算机配置文件 (Machine.config) 中使用。</span><span class="sxs-lookup"><span data-stu-id="a0273-134">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="a0273-135">示例</span><span class="sxs-lookup"><span data-stu-id="a0273-135">Example</span></span>  
 <span data-ttu-id="a0273-136">下面的示例将两个地址添加到忽略列表。</span><span class="sxs-lookup"><span data-stu-id="a0273-136">The following example adds two addresses to the bypass list.</span></span> <span data-ttu-id="a0273-137">第一个跳过 contoso.com 域; 中的所有服务器的代理第二个跳过与 192.168 其 IP 地址开始的所有服务器的代理。</span><span class="sxs-lookup"><span data-stu-id="a0273-137">The first bypasses the proxy for all servers in the contoso.com domain; the second bypasses the proxy for all servers whose IP addresses begin with 192.168.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="a0273-138">请参阅</span><span class="sxs-lookup"><span data-stu-id="a0273-138">See also</span></span>

- <xref:System.Net.WebProxy?displayProperty=nameWithType>
- [<span data-ttu-id="a0273-139">网络设置架构</span><span class="sxs-lookup"><span data-stu-id="a0273-139">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
