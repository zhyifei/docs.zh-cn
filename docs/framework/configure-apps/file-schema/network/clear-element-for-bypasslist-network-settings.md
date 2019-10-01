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
ms.openlocfilehash: 4d078dac14103560423bfccdd4a1717031e7a60f
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/01/2019
ms.locfileid: "71699502"
---
# <a name="clear-element-for-bypasslist-network-settings"></a><span data-ttu-id="0f91a-102">用于 bypasslist 的 0clear > 元素（网络设置） @no__t</span><span class="sxs-lookup"><span data-stu-id="0f91a-102">\<clear> Element for bypasslist (Network Settings)</span></span>
<span data-ttu-id="0f91a-103">清除代理跳过列表。</span><span class="sxs-lookup"><span data-stu-id="0f91a-103">Clears the proxy bypass list.</span></span>  
  
[<span data-ttu-id="0f91a-104"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="0f91a-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="0f91a-105">&nbsp; @ no__t[ **\<system >** ](system-net-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="0f91a-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span></span>  
<span data-ttu-id="0f91a-106">&nbsp; @ no__t-1 @ no__t-2 @ no__t[ **\<defaultProxy >** ](defaultproxy-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="0f91a-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<defaultProxy>**](defaultproxy-element-network-settings.md)</span></span>  
<span data-ttu-id="0f91a-107">&nbsp; @ no__t-1 @ no__t-2 @ no__t-3 @ no__t-4 @ no__t-5[ **\<bypasslist >** ](bypasslist-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="0f91a-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<bypasslist>**](bypasslist-element-network-settings.md)</span></span>  
<span data-ttu-id="0f91a-108">&nbsp; @ no__t-1 @ no__t-2 @ no__t-3 @ no__t-4 @ no__t-5 @ no__t-6 @ no__t-7 **\<clear >**</span><span class="sxs-lookup"><span data-stu-id="0f91a-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0f91a-109">语法</span><span class="sxs-lookup"><span data-stu-id="0f91a-109">Syntax</span></span>  
  
```xml  
<clear/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0f91a-110">特性和元素</span><span class="sxs-lookup"><span data-stu-id="0f91a-110">Attributes and Elements</span></span>  
 <span data-ttu-id="0f91a-111">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="0f91a-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0f91a-112">特性</span><span class="sxs-lookup"><span data-stu-id="0f91a-112">Attributes</span></span>  
 <span data-ttu-id="0f91a-113">无。</span><span class="sxs-lookup"><span data-stu-id="0f91a-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="0f91a-114">子元素</span><span class="sxs-lookup"><span data-stu-id="0f91a-114">Child Elements</span></span>  
 <span data-ttu-id="0f91a-115">无。</span><span class="sxs-lookup"><span data-stu-id="0f91a-115">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="0f91a-116">父元素</span><span class="sxs-lookup"><span data-stu-id="0f91a-116">Parent Elements</span></span>  
  
|<span data-ttu-id="0f91a-117">**元素**</span><span class="sxs-lookup"><span data-stu-id="0f91a-117">**Element**</span></span>|<span data-ttu-id="0f91a-118">**说明**</span><span class="sxs-lookup"><span data-stu-id="0f91a-118">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="0f91a-119">bypasslist</span><span class="sxs-lookup"><span data-stu-id="0f91a-119">bypasslist</span></span>](bypasslist-element-network-settings.md)|<span data-ttu-id="0f91a-120">提供了一组正则表达式，描述不使用代理的地址。</span><span class="sxs-lookup"><span data-stu-id="0f91a-120">Provides a set of regular expressions that describe addresses that do not use a proxy.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0f91a-121">备注</span><span class="sxs-lookup"><span data-stu-id="0f91a-121">Remarks</span></span>  
 <span data-ttu-id="0f91a-122">@No__t 0 元素会清除绕过列表中的所有条目。</span><span class="sxs-lookup"><span data-stu-id="0f91a-122">The `clear` element clears all entries from the bypass list.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="0f91a-123">配置文件</span><span class="sxs-lookup"><span data-stu-id="0f91a-123">Configuration Files</span></span>  
 <span data-ttu-id="0f91a-124">此元素可在应用程序配置文件或计算机配置文件 (Machine.config) 中使用。</span><span class="sxs-lookup"><span data-stu-id="0f91a-124">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="0f91a-125">示例</span><span class="sxs-lookup"><span data-stu-id="0f91a-125">Example</span></span>  
 <span data-ttu-id="0f91a-126">下面的示例清除了跳过列表，并将两个地址添加到了跳过列表。</span><span class="sxs-lookup"><span data-stu-id="0f91a-126">The following example clears the bypass list and then adds two addresses to the bypass list.</span></span> <span data-ttu-id="0f91a-127">首先，将跳过 contoso.com 域中所有服务器的代理;第二种方式是跳过其 IP 地址以192.168 开头的所有服务器的代理。</span><span class="sxs-lookup"><span data-stu-id="0f91a-127">The first bypasses the proxy for all servers in the contoso.com domain; the second bypasses the proxy for all servers whose IP address begins with 192.168.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="0f91a-128">请参阅</span><span class="sxs-lookup"><span data-stu-id="0f91a-128">See also</span></span>

- <xref:System.Net.WebProxy?displayProperty=nameWithType>
- [<span data-ttu-id="0f91a-129">网络设置架构</span><span class="sxs-lookup"><span data-stu-id="0f91a-129">Network Settings Schema</span></span>](index.md)
