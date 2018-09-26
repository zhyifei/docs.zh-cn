---
title: '&lt;清除&gt;bypasslist （网络设置） 的元素'
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
author: mcleblanc
ms.author: markl
ms.openlocfilehash: ca6c8e9334bdfcdf4d79c5a91612ee117445d9cb
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/25/2018
ms.locfileid: "47170634"
---
# <a name="ltcleargt-element-for-bypasslist-network-settings"></a><span data-ttu-id="35c53-102">&lt;清除&gt;bypasslist （网络设置） 的元素</span><span class="sxs-lookup"><span data-stu-id="35c53-102">&lt;clear&gt; Element for bypasslist (Network Settings)</span></span>
<span data-ttu-id="35c53-103">清除代理跳过列表。</span><span class="sxs-lookup"><span data-stu-id="35c53-103">Clears the proxy bypass list.</span></span>  
  
 <span data-ttu-id="35c53-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="35c53-104">\<configuration></span></span>  
<span data-ttu-id="35c53-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="35c53-105">\<system.net></span></span>  
<span data-ttu-id="35c53-106">\<defaultProxy ></span><span class="sxs-lookup"><span data-stu-id="35c53-106">\<defaultProxy></span></span>  
<span data-ttu-id="35c53-107">\<bypasslist ></span><span class="sxs-lookup"><span data-stu-id="35c53-107">\<bypasslist></span></span>  
<span data-ttu-id="35c53-108">\<清除 ></span><span class="sxs-lookup"><span data-stu-id="35c53-108">\<clear></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="35c53-109">语法</span><span class="sxs-lookup"><span data-stu-id="35c53-109">Syntax</span></span>  
  
```xml  
<clear/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="35c53-110">特性和元素</span><span class="sxs-lookup"><span data-stu-id="35c53-110">Attributes and Elements</span></span>  
 <span data-ttu-id="35c53-111">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="35c53-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="35c53-112">特性</span><span class="sxs-lookup"><span data-stu-id="35c53-112">Attributes</span></span>  
 <span data-ttu-id="35c53-113">无。</span><span class="sxs-lookup"><span data-stu-id="35c53-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="35c53-114">子元素</span><span class="sxs-lookup"><span data-stu-id="35c53-114">Child Elements</span></span>  
 <span data-ttu-id="35c53-115">无。</span><span class="sxs-lookup"><span data-stu-id="35c53-115">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="35c53-116">父元素</span><span class="sxs-lookup"><span data-stu-id="35c53-116">Parent Elements</span></span>  
  
|<span data-ttu-id="35c53-117">**元素**</span><span class="sxs-lookup"><span data-stu-id="35c53-117">**Element**</span></span>|<span data-ttu-id="35c53-118">**说明**</span><span class="sxs-lookup"><span data-stu-id="35c53-118">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="35c53-119">bypasslist</span><span class="sxs-lookup"><span data-stu-id="35c53-119">bypasslist</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/bypasslist-element-network-settings.md)|<span data-ttu-id="35c53-120">提供一组描述不使用代理的地址的正则表达式。</span><span class="sxs-lookup"><span data-stu-id="35c53-120">Provides a set of regular expressions that describe addresses that do not use a proxy.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="35c53-121">备注</span><span class="sxs-lookup"><span data-stu-id="35c53-121">Remarks</span></span>  
 <span data-ttu-id="35c53-122">`clear`元素清除跳过列表中的所有条目。</span><span class="sxs-lookup"><span data-stu-id="35c53-122">The `clear` element clears all entries from the bypass list.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="35c53-123">配置文件</span><span class="sxs-lookup"><span data-stu-id="35c53-123">Configuration Files</span></span>  
 <span data-ttu-id="35c53-124">此元素可在应用程序配置文件或计算机配置文件 (Machine.config) 中使用。</span><span class="sxs-lookup"><span data-stu-id="35c53-124">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="35c53-125">示例</span><span class="sxs-lookup"><span data-stu-id="35c53-125">Example</span></span>  
 <span data-ttu-id="35c53-126">下面的示例清除跳过列表，然后将两个地址添加到忽略列表。</span><span class="sxs-lookup"><span data-stu-id="35c53-126">The following example clears the bypass list and then adds two addresses to the bypass list.</span></span> <span data-ttu-id="35c53-127">第一个跳过 contoso.com 域; 中的所有服务器的代理第二个跳过与 192.168 其 IP 地址开始的所有服务器的代理。</span><span class="sxs-lookup"><span data-stu-id="35c53-127">The first bypasses the proxy for all servers in the contoso.com domain; the second bypasses the proxy for all servers whose IP address begins with 192.168.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="35c53-128">请参阅</span><span class="sxs-lookup"><span data-stu-id="35c53-128">See Also</span></span>  
 <xref:System.Net.WebProxy?displayProperty=nameWithType>  
 [<span data-ttu-id="35c53-129">网络设置架构</span><span class="sxs-lookup"><span data-stu-id="35c53-129">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
