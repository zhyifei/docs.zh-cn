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
ms.openlocfilehash: e5305d9aed09b6c4d1ad4201e5e08e007a14c7c0
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/21/2019
ms.locfileid: "69664190"
---
# <a name="clear-element-for-bypasslist-network-settings"></a><span data-ttu-id="6c065-102">\<清除 bypasslist 的 > 元素 (网络设置)</span><span class="sxs-lookup"><span data-stu-id="6c065-102">\<clear> Element for bypasslist (Network Settings)</span></span>
<span data-ttu-id="6c065-103">清除代理跳过列表。</span><span class="sxs-lookup"><span data-stu-id="6c065-103">Clears the proxy bypass list.</span></span>  
  
 <span data-ttu-id="6c065-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="6c065-104">\<configuration></span></span>  
<span data-ttu-id="6c065-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="6c065-105">\<system.net></span></span>  
<span data-ttu-id="6c065-106">\<defaultProxy ></span><span class="sxs-lookup"><span data-stu-id="6c065-106">\<defaultProxy></span></span>  
<span data-ttu-id="6c065-107">\<bypasslist ></span><span class="sxs-lookup"><span data-stu-id="6c065-107">\<bypasslist></span></span>  
<span data-ttu-id="6c065-108">\<清除 ></span><span class="sxs-lookup"><span data-stu-id="6c065-108">\<clear></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6c065-109">语法</span><span class="sxs-lookup"><span data-stu-id="6c065-109">Syntax</span></span>  
  
```xml  
<clear/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6c065-110">特性和元素</span><span class="sxs-lookup"><span data-stu-id="6c065-110">Attributes and Elements</span></span>  
 <span data-ttu-id="6c065-111">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="6c065-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6c065-112">特性</span><span class="sxs-lookup"><span data-stu-id="6c065-112">Attributes</span></span>  
 <span data-ttu-id="6c065-113">无。</span><span class="sxs-lookup"><span data-stu-id="6c065-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="6c065-114">子元素</span><span class="sxs-lookup"><span data-stu-id="6c065-114">Child Elements</span></span>  
 <span data-ttu-id="6c065-115">无。</span><span class="sxs-lookup"><span data-stu-id="6c065-115">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="6c065-116">父元素</span><span class="sxs-lookup"><span data-stu-id="6c065-116">Parent Elements</span></span>  
  
|<span data-ttu-id="6c065-117">**元素**</span><span class="sxs-lookup"><span data-stu-id="6c065-117">**Element**</span></span>|<span data-ttu-id="6c065-118">**说明**</span><span class="sxs-lookup"><span data-stu-id="6c065-118">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="6c065-119">bypasslist</span><span class="sxs-lookup"><span data-stu-id="6c065-119">bypasslist</span></span>](bypasslist-element-network-settings.md)|<span data-ttu-id="6c065-120">提供了一组正则表达式, 描述不使用代理的地址。</span><span class="sxs-lookup"><span data-stu-id="6c065-120">Provides a set of regular expressions that describe addresses that do not use a proxy.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6c065-121">备注</span><span class="sxs-lookup"><span data-stu-id="6c065-121">Remarks</span></span>  
 <span data-ttu-id="6c065-122">`clear`元素清除跳过列表中的所有条目。</span><span class="sxs-lookup"><span data-stu-id="6c065-122">The `clear` element clears all entries from the bypass list.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="6c065-123">配置文件</span><span class="sxs-lookup"><span data-stu-id="6c065-123">Configuration Files</span></span>  
 <span data-ttu-id="6c065-124">此元素可在应用程序配置文件或计算机配置文件 (Machine.config) 中使用。</span><span class="sxs-lookup"><span data-stu-id="6c065-124">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="6c065-125">示例</span><span class="sxs-lookup"><span data-stu-id="6c065-125">Example</span></span>  
 <span data-ttu-id="6c065-126">下面的示例清除了跳过列表, 并将两个地址添加到了跳过列表。</span><span class="sxs-lookup"><span data-stu-id="6c065-126">The following example clears the bypass list and then adds two addresses to the bypass list.</span></span> <span data-ttu-id="6c065-127">首先, 将跳过 contoso.com 域中所有服务器的代理;第二种方式是跳过其 IP 地址以192.168 开头的所有服务器的代理。</span><span class="sxs-lookup"><span data-stu-id="6c065-127">The first bypasses the proxy for all servers in the contoso.com domain; the second bypasses the proxy for all servers whose IP address begins with 192.168.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="6c065-128">请参阅</span><span class="sxs-lookup"><span data-stu-id="6c065-128">See also</span></span>

- <xref:System.Net.WebProxy?displayProperty=nameWithType>
- [<span data-ttu-id="6c065-129">网络设置架构</span><span class="sxs-lookup"><span data-stu-id="6c065-129">Network Settings Schema</span></span>](index.md)
