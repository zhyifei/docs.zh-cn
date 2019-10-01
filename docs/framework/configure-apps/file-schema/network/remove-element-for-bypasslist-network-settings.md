---
title: bypasslist 的 <remove> 元素（网络设置）
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/defaultProxy/bypasslist/remove
- http://schemas.microsoft.com/.NetConfiguration/v2.0#remove
helpviewer_keywords:
- <bypasslist>, remove element
- remove element, bypasslist
- bypasslist, remove element
- remove element, bypasslist
ms.assetid: 61dcfb4a-e3d9-4abf-a2cd-7d685fe2f64b
ms.openlocfilehash: 97b49a8a520d6a4f72945366874991d2deb18710
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/01/2019
ms.locfileid: "71697894"
---
# <a name="remove-element-for-bypasslist-network-settings"></a><span data-ttu-id="cf2e3-102">用于 bypasslist 的 0remove > 元素（网络设置） @no__t</span><span class="sxs-lookup"><span data-stu-id="cf2e3-102">\<remove> Element for bypasslist (Network Settings)</span></span>

<span data-ttu-id="cf2e3-103">从代理跳过列表中删除 IP 地址或 DNS 名称。</span><span class="sxs-lookup"><span data-stu-id="cf2e3-103">Removes an IP address or DNS name from the proxy bypass list.</span></span>

[<span data-ttu-id="cf2e3-104"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="cf2e3-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="cf2e3-105">&nbsp; @ no__t[ **\<system >** ](system-net-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="cf2e3-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span></span>  
<span data-ttu-id="cf2e3-106">&nbsp; @ no__t-1 @ no__t-2 @ no__t[ **\<defaultProxy >** ](defaultproxy-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="cf2e3-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<defaultProxy>**](defaultproxy-element-network-settings.md)</span></span>  
<span data-ttu-id="cf2e3-107">&nbsp; @ no__t-1 @ no__t-2 @ no__t-3 @ no__t-4 @ no__t-5[ **\<bypasslist >** ](bypasslist-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="cf2e3-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<bypasslist>**](bypasslist-element-network-settings.md)</span></span>  
<span data-ttu-id="cf2e3-108">&nbsp; @ no__t-1 @ no__t-2 @ no__t-3 @ no__t-4 @ no__t-5 @ no__t-6 @ no__t-7 **\<remove >**</span><span class="sxs-lookup"><span data-stu-id="cf2e3-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<remove>**</span></span>  

## <a name="syntax"></a><span data-ttu-id="cf2e3-109">语法</span><span class="sxs-lookup"><span data-stu-id="cf2e3-109">Syntax</span></span>

```xml
<remove
  address="regular expression"
/>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="cf2e3-110">特性和元素</span><span class="sxs-lookup"><span data-stu-id="cf2e3-110">Attributes and Elements</span></span>

<span data-ttu-id="cf2e3-111">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="cf2e3-111">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="cf2e3-112">特性</span><span class="sxs-lookup"><span data-stu-id="cf2e3-112">Attributes</span></span>

|<span data-ttu-id="cf2e3-113">**特性**</span><span class="sxs-lookup"><span data-stu-id="cf2e3-113">**Attribute**</span></span>|<span data-ttu-id="cf2e3-114">**说明**</span><span class="sxs-lookup"><span data-stu-id="cf2e3-114">**Description**</span></span>|
|-------------------|---------------------|
|`address`|<span data-ttu-id="cf2e3-115">描述 IP 地址或 DNS 名称的正则表达式。</span><span class="sxs-lookup"><span data-stu-id="cf2e3-115">A regular expression describing an IP address or DNS name.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="cf2e3-116">子元素</span><span class="sxs-lookup"><span data-stu-id="cf2e3-116">Child Elements</span></span>

<span data-ttu-id="cf2e3-117">无。</span><span class="sxs-lookup"><span data-stu-id="cf2e3-117">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="cf2e3-118">父元素</span><span class="sxs-lookup"><span data-stu-id="cf2e3-118">Parent Elements</span></span>

|<span data-ttu-id="cf2e3-119">**元素**</span><span class="sxs-lookup"><span data-stu-id="cf2e3-119">**Element**</span></span>|<span data-ttu-id="cf2e3-120">**说明**</span><span class="sxs-lookup"><span data-stu-id="cf2e3-120">**Description**</span></span>|
|-----------------|---------------------|
|[<span data-ttu-id="cf2e3-121">bypasslist</span><span class="sxs-lookup"><span data-stu-id="cf2e3-121">bypasslist</span></span>](bypasslist-element-network-settings.md)|<span data-ttu-id="cf2e3-122">提供了一组正则表达式，描述不使用代理的地址。</span><span class="sxs-lookup"><span data-stu-id="cf2e3-122">Provides a set of regular expressions that describe addresses that do not use a proxy.</span></span>|

## <a name="remarks"></a><span data-ttu-id="cf2e3-123">备注</span><span class="sxs-lookup"><span data-stu-id="cf2e3-123">Remarks</span></span>

<span data-ttu-id="cf2e3-124">@No__t 0 元素从绕过代理服务器的地址列表中删除描述 IP 地址或 DNS 服务器名称的正则表达式。</span><span class="sxs-lookup"><span data-stu-id="cf2e3-124">The `remove` element removes regular expressions describing IP addresses or DNS server names from the list of addresses that bypass a proxy server.</span></span> <span data-ttu-id="cf2e3-125">地址在配置文件中或配置层次结构中的更高级别定义。</span><span class="sxs-lookup"><span data-stu-id="cf2e3-125">The addresses were defined earlier in the configuration file or at a higher level in the configuration hierarchy.</span></span>

<span data-ttu-id="cf2e3-126">@No__t-0 属性的值应为描述一组 IP 地址或主机名的正则表达式。</span><span class="sxs-lookup"><span data-stu-id="cf2e3-126">The value for the `address` attribute should be a regular expression that describes a set of IP addresses or host names.</span></span>

<span data-ttu-id="cf2e3-127">有关正则表达式的详细信息，请参阅。[.NET Framework 正则表达式](../../../../standard/base-types/regular-expressions.md)。</span><span class="sxs-lookup"><span data-stu-id="cf2e3-127">For more information about regular expressions, see .[.NET Framework Regular Expressions](../../../../standard/base-types/regular-expressions.md).</span></span>

## <a name="configuration-files"></a><span data-ttu-id="cf2e3-128">配置文件</span><span class="sxs-lookup"><span data-stu-id="cf2e3-128">Configuration Files</span></span>

<span data-ttu-id="cf2e3-129">此元素可在应用程序配置文件或计算机配置文件 (Machine.config) 中使用。</span><span class="sxs-lookup"><span data-stu-id="cf2e3-129">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>

## <a name="example"></a><span data-ttu-id="cf2e3-130">示例</span><span class="sxs-lookup"><span data-stu-id="cf2e3-130">Example</span></span>

<span data-ttu-id="cf2e3-131">下面的示例删除 adventure-works.com 域的任何先前定义，然后将 contoso.com 域添加到跳过列表。</span><span class="sxs-lookup"><span data-stu-id="cf2e3-131">The following example removes any previous definition for the adventure-works.com domain, and then adds the contoso.com domain to the bypass list.</span></span>

```xml
<configuration>
  <system.net>
    <defaultProxy>
      <bypasslist>
        <remove address="[a-z]+\.adventure-works\.com$" />
        <add address="[a-z]+\.contoso\.com$" />
      </bypasslist>
    </defaultProxy>
  </system.net>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="cf2e3-132">请参阅</span><span class="sxs-lookup"><span data-stu-id="cf2e3-132">See also</span></span>

- <xref:System.Net.WebProxy?displayProperty=nameWithType>
- [<span data-ttu-id="cf2e3-133">网络设置架构</span><span class="sxs-lookup"><span data-stu-id="cf2e3-133">Network Settings Schema</span></span>](index.md)
