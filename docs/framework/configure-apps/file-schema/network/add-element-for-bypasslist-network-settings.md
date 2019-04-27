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
ms.openlocfilehash: 904c8e23f7a09a975a6f3b9322ed6bc4148d9ba4
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61674658"
---
# <a name="add-element-for-bypasslist-network-settings"></a><span data-ttu-id="3ddf7-102">\<添加 > bypasslist （网络设置） 的元素</span><span class="sxs-lookup"><span data-stu-id="3ddf7-102">\<add> Element for bypasslist (Network Settings)</span></span>
<span data-ttu-id="3ddf7-103">将 IP 地址或 DNS 名称添加到代理跳过列表。</span><span class="sxs-lookup"><span data-stu-id="3ddf7-103">Adds an IP address or DNS name to the proxy bypass list.</span></span>  
  
 <span data-ttu-id="3ddf7-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="3ddf7-104">\<configuration></span></span>  
<span data-ttu-id="3ddf7-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="3ddf7-105">\<system.net></span></span>  
<span data-ttu-id="3ddf7-106">\<defaultProxy ></span><span class="sxs-lookup"><span data-stu-id="3ddf7-106">\<defaultProxy></span></span>  
<span data-ttu-id="3ddf7-107">\<bypasslist ></span><span class="sxs-lookup"><span data-stu-id="3ddf7-107">\<bypasslist></span></span>  
<span data-ttu-id="3ddf7-108">\<add></span><span class="sxs-lookup"><span data-stu-id="3ddf7-108">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3ddf7-109">语法</span><span class="sxs-lookup"><span data-stu-id="3ddf7-109">Syntax</span></span>  
  
```xml  
<add   
  address="regular expression"   
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3ddf7-110">特性和元素</span><span class="sxs-lookup"><span data-stu-id="3ddf7-110">Attributes and Elements</span></span>  
 <span data-ttu-id="3ddf7-111">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="3ddf7-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3ddf7-112">特性</span><span class="sxs-lookup"><span data-stu-id="3ddf7-112">Attributes</span></span>  
  
|<span data-ttu-id="3ddf7-113">**特性**</span><span class="sxs-lookup"><span data-stu-id="3ddf7-113">**Attribute**</span></span>|<span data-ttu-id="3ddf7-114">**说明**</span><span class="sxs-lookup"><span data-stu-id="3ddf7-114">**Description**</span></span>|  
|-------------------|---------------------|  
|<span data-ttu-id="3ddf7-115">**address**</span><span class="sxs-lookup"><span data-stu-id="3ddf7-115">**address**</span></span>|<span data-ttu-id="3ddf7-116">正则表达式描述 IP 地址或 DNS 名称。</span><span class="sxs-lookup"><span data-stu-id="3ddf7-116">A regular expression describing an IP address or DNS name.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="3ddf7-117">子元素</span><span class="sxs-lookup"><span data-stu-id="3ddf7-117">Child Elements</span></span>  
 <span data-ttu-id="3ddf7-118">无。</span><span class="sxs-lookup"><span data-stu-id="3ddf7-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="3ddf7-119">父元素</span><span class="sxs-lookup"><span data-stu-id="3ddf7-119">Parent Elements</span></span>  
  
|<span data-ttu-id="3ddf7-120">**元素**</span><span class="sxs-lookup"><span data-stu-id="3ddf7-120">**Element**</span></span>|<span data-ttu-id="3ddf7-121">**说明**</span><span class="sxs-lookup"><span data-stu-id="3ddf7-121">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="3ddf7-122">bypasslist</span><span class="sxs-lookup"><span data-stu-id="3ddf7-122">bypasslist</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/bypasslist-element-network-settings.md)|<span data-ttu-id="3ddf7-123">提供一组描述不使用代理的地址的正则表达式。</span><span class="sxs-lookup"><span data-stu-id="3ddf7-123">Provides a set of regular expressions that describe addresses that do not use a proxy.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3ddf7-124">备注</span><span class="sxs-lookup"><span data-stu-id="3ddf7-124">Remarks</span></span>  
 <span data-ttu-id="3ddf7-125">`add`元素插入正则表达式描述 IP 地址或 DNS 服务器名称的绕过代理服务器的地址的列表。</span><span class="sxs-lookup"><span data-stu-id="3ddf7-125">The `add` element inserts regular expressions describing IP addresses or DNS server names to the list of addresses that bypass a proxy server.</span></span>  
  
 <span data-ttu-id="3ddf7-126">值`address`属性应为描述一组 IP 地址或主机名的正则表达式。</span><span class="sxs-lookup"><span data-stu-id="3ddf7-126">The value of the `address` attribute should be a regular expression that describes a set of IP addresses or host names.</span></span>  
  
 <span data-ttu-id="3ddf7-127">指定此元素的正则表达式时应十分小心。</span><span class="sxs-lookup"><span data-stu-id="3ddf7-127">You should use caution when specifying a regular expression for this element.</span></span> <span data-ttu-id="3ddf7-128">正则表达式"[a-z] +\\.contoso\\.com"匹配任意主机在 contoso.com 域，但它还将匹配 contoso.com.cpandl.com 域中的任何主机。</span><span class="sxs-lookup"><span data-stu-id="3ddf7-128">The regular expression "[a-z]+\\.contoso\\.com" matches any host in the contoso.com domain, but it also matches any host in the contoso.com.cpandl.com domain.</span></span> <span data-ttu-id="3ddf7-129">若要匹配仅在 contoso.com 域中的主机，使用的定位点 （"$"）:"[a-z] +\\.contoso\\.com$"。</span><span class="sxs-lookup"><span data-stu-id="3ddf7-129">To match only a host in the contoso.com domain, use an anchor ("$"): "[a-z]+\\.contoso\\.com$".</span></span>  
  
 <span data-ttu-id="3ddf7-130">有关正则表达式的详细信息，请参阅。[.NET framework 正则表达式](../../../../../docs/standard/base-types/regular-expressions.md)。</span><span class="sxs-lookup"><span data-stu-id="3ddf7-130">For more information about regular expressions, see .[.NET Framework Regular Expressions](../../../../../docs/standard/base-types/regular-expressions.md).</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="3ddf7-131">配置文件</span><span class="sxs-lookup"><span data-stu-id="3ddf7-131">Configuration Files</span></span>  
 <span data-ttu-id="3ddf7-132">此元素可在应用程序配置文件或计算机配置文件 (Machine.config) 中使用。</span><span class="sxs-lookup"><span data-stu-id="3ddf7-132">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="3ddf7-133">示例</span><span class="sxs-lookup"><span data-stu-id="3ddf7-133">Example</span></span>  
 <span data-ttu-id="3ddf7-134">下面的示例将两个地址添加到忽略列表。</span><span class="sxs-lookup"><span data-stu-id="3ddf7-134">The following example adds two addresses to the bypass list.</span></span> <span data-ttu-id="3ddf7-135">第一个跳过 contoso.com 域; 中的所有服务器的代理第二个跳过与 192.168 其 IP 地址开始的所有服务器的代理。</span><span class="sxs-lookup"><span data-stu-id="3ddf7-135">The first bypasses the proxy for all servers in the contoso.com domain; the second bypasses the proxy for all servers whose IP address begins with 192.168.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="3ddf7-136">请参阅</span><span class="sxs-lookup"><span data-stu-id="3ddf7-136">See also</span></span>

- <xref:System.Net.WebProxy?displayProperty=nameWithType>
- [<span data-ttu-id="3ddf7-137">网络设置架构</span><span class="sxs-lookup"><span data-stu-id="3ddf7-137">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
