---
title: bypasslist 的 <clear> 元素（网络设置）
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/defaultProxy/bypasslist/clear
- http://schemas.microsoft.com/.NetConfiguration/v2.0#clear
helpviewer_keywords:
- clear element, bypasslist
- <clear> element, bypasslist
- <bypasslist>, clear element
- bypasslist, clear element
ms.assetid: 301584ca-a914-4100-b180-3b288d3b099e
ms.openlocfilehash: c25477c2c99be66b34b07e1f7e50115bfa8d14e9
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79154928"
---
# <a name="clear-element-for-bypasslist-network-settings"></a><span data-ttu-id="45743-102">\<清除>元素以进行绕过列表（网络设置）</span><span class="sxs-lookup"><span data-stu-id="45743-102">\<clear> Element for bypasslist (Network Settings)</span></span>
<span data-ttu-id="45743-103">清除代理绕过列表。</span><span class="sxs-lookup"><span data-stu-id="45743-103">Clears the proxy bypass list.</span></span>  
  
<span data-ttu-id="45743-104">[**\<配置>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="45743-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="45743-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="45743-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span></span>\
<span data-ttu-id="45743-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<默认代理>**](defaultproxy-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="45743-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<defaultProxy>**](defaultproxy-element-network-settings.md)</span></span>\
<span data-ttu-id="45743-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<绕过列表>**](bypasslist-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="45743-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<bypasslist>**](bypasslist-element-network-settings.md)</span></span>\
<span data-ttu-id="45743-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<明确>**</span><span class="sxs-lookup"><span data-stu-id="45743-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**</span></span>

## <a name="syntax"></a><span data-ttu-id="45743-109">语法</span><span class="sxs-lookup"><span data-stu-id="45743-109">Syntax</span></span>  
  
```xml  
<clear/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="45743-110">特性和元素</span><span class="sxs-lookup"><span data-stu-id="45743-110">Attributes and Elements</span></span>  
 <span data-ttu-id="45743-111">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="45743-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="45743-112">属性</span><span class="sxs-lookup"><span data-stu-id="45743-112">Attributes</span></span>  
 <span data-ttu-id="45743-113">无。</span><span class="sxs-lookup"><span data-stu-id="45743-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="45743-114">子元素</span><span class="sxs-lookup"><span data-stu-id="45743-114">Child Elements</span></span>  
 <span data-ttu-id="45743-115">无。</span><span class="sxs-lookup"><span data-stu-id="45743-115">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="45743-116">父元素</span><span class="sxs-lookup"><span data-stu-id="45743-116">Parent Elements</span></span>  
  
|<span data-ttu-id="45743-117">**元素**</span><span class="sxs-lookup"><span data-stu-id="45743-117">**Element**</span></span>|<span data-ttu-id="45743-118">**说明**</span><span class="sxs-lookup"><span data-stu-id="45743-118">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="45743-119">bypasslist</span><span class="sxs-lookup"><span data-stu-id="45743-119">bypasslist</span></span>](bypasslist-element-network-settings.md)|<span data-ttu-id="45743-120">提供一组常规表达式，用于描述不使用代理的地址。</span><span class="sxs-lookup"><span data-stu-id="45743-120">Provides a set of regular expressions that describe addresses that do not use a proxy.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="45743-121">备注</span><span class="sxs-lookup"><span data-stu-id="45743-121">Remarks</span></span>  
 <span data-ttu-id="45743-122">该`clear`元素清除旁路列表中的所有条目。</span><span class="sxs-lookup"><span data-stu-id="45743-122">The `clear` element clears all entries from the bypass list.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="45743-123">配置文件</span><span class="sxs-lookup"><span data-stu-id="45743-123">Configuration Files</span></span>  
 <span data-ttu-id="45743-124">此元素可在应用程序配置文件或计算机配置文件 (Machine.config) 中使用。</span><span class="sxs-lookup"><span data-stu-id="45743-124">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="45743-125">示例</span><span class="sxs-lookup"><span data-stu-id="45743-125">Example</span></span>  
 <span data-ttu-id="45743-126">下面的示例清除旁路列表，然后将两个地址添加到旁路列表中。</span><span class="sxs-lookup"><span data-stu-id="45743-126">The following example clears the bypass list and then adds two addresses to the bypass list.</span></span> <span data-ttu-id="45743-127">第一个绕过contoso.com域中所有服务器的代理;第二个服务器绕过其 IP 地址以 192.168 开头的所有服务器的代理。</span><span class="sxs-lookup"><span data-stu-id="45743-127">The first bypasses the proxy for all servers in the contoso.com domain; the second bypasses the proxy for all servers whose IP address begins with 192.168.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <defaultProxy>  
      <bypasslist>  
         <clear/>  
        <add address="[a-z]+\.contoso\.com$" />  
        <add address="192\.168\.\d{1,3}\.\d{1,3}" />  
      </bypasslist>  
    </defaultProxy>  
  </system.net>  
</configuration>
```  
  
## <a name="see-also"></a><span data-ttu-id="45743-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="45743-128">See also</span></span>

- <xref:System.Net.WebProxy?displayProperty=nameWithType>
- [<span data-ttu-id="45743-129">网络设置架构</span><span class="sxs-lookup"><span data-stu-id="45743-129">Network Settings Schema</span></span>](index.md)
