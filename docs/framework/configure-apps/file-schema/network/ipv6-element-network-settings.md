---
title: '&lt;ipv6&gt;元素 （网络设置）'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/settings/ipv6
- http://schemas.microsoft.com/.NetConfiguration/v2.0#ipv6
helpviewer_keywords:
- <ipv6> element
- ipv6 element
ms.assetid: 10b79aef-327b-4718-a892-e11f55e4d169
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 4b73e5d781829292513e809c39ac9de9dfc6d0e8
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
ms.locfileid: "32742479"
---
# <a name="ltipv6gt-element-network-settings"></a><span data-ttu-id="01b33-102">&lt;ipv6&gt;元素 （网络设置）</span><span class="sxs-lookup"><span data-stu-id="01b33-102">&lt;ipv6&gt; Element (Network Settings)</span></span>
<span data-ttu-id="01b33-103">启用 Internet 协议版本 6 (IPv6) 响应的过时成员<xref:System.Net.Dns>类。</span><span class="sxs-lookup"><span data-stu-id="01b33-103">Enables Internet Protocol version 6 (IPv6) responses from obsolete members of the <xref:System.Net.Dns> class.</span></span>  
  
 <span data-ttu-id="01b33-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="01b33-104">\<configuration></span></span>  
<span data-ttu-id="01b33-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="01b33-105">\<system.net></span></span>  
<span data-ttu-id="01b33-106">\<设置 ></span><span class="sxs-lookup"><span data-stu-id="01b33-106">\<settings></span></span>  
<span data-ttu-id="01b33-107">\<ipv6 ></span><span class="sxs-lookup"><span data-stu-id="01b33-107">\<ipv6></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="01b33-108">语法</span><span class="sxs-lookup"><span data-stu-id="01b33-108">Syntax</span></span>  
  
```xml  
<ipv6  
  enabled="true|false"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="01b33-109">特性和元素</span><span class="sxs-lookup"><span data-stu-id="01b33-109">Attributes and Elements</span></span>  
 <span data-ttu-id="01b33-110">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="01b33-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="01b33-111">特性</span><span class="sxs-lookup"><span data-stu-id="01b33-111">Attributes</span></span>  
  
|<span data-ttu-id="01b33-112">**特性**</span><span class="sxs-lookup"><span data-stu-id="01b33-112">**Attribute**</span></span>|<span data-ttu-id="01b33-113">**说明**</span><span class="sxs-lookup"><span data-stu-id="01b33-113">**Description**</span></span>|  
|-------------------|---------------------|  
|`enabled`|<span data-ttu-id="01b33-114">指定是否的成员<xref:System.Net.Dns>类返回 Internet 协议版本 6 (IPv6) 地址。</span><span class="sxs-lookup"><span data-stu-id="01b33-114">Specifies whether members of the <xref:System.Net.Dns> class return Internet Protocol version 6 (IPv6) addresses.</span></span> <span data-ttu-id="01b33-115">默认值为 `false`。</span><span class="sxs-lookup"><span data-stu-id="01b33-115">The default value is `false`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="01b33-116">子元素</span><span class="sxs-lookup"><span data-stu-id="01b33-116">Child Elements</span></span>  
 <span data-ttu-id="01b33-117">无。</span><span class="sxs-lookup"><span data-stu-id="01b33-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="01b33-118">父元素</span><span class="sxs-lookup"><span data-stu-id="01b33-118">Parent Elements</span></span>  
  
|<span data-ttu-id="01b33-119">**元素**</span><span class="sxs-lookup"><span data-stu-id="01b33-119">**Element**</span></span>|<span data-ttu-id="01b33-120">**说明**</span><span class="sxs-lookup"><span data-stu-id="01b33-120">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="01b33-121">设置</span><span class="sxs-lookup"><span data-stu-id="01b33-121">settings</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/settings-element-network-settings.md)|<span data-ttu-id="01b33-122">配置 <xref:System.Net> 命名空间的基本网络选项。</span><span class="sxs-lookup"><span data-stu-id="01b33-122">Configures basic network options for the <xref:System.Net> namespace.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="01b33-123">备注</span><span class="sxs-lookup"><span data-stu-id="01b33-123">Remarks</span></span>  
 <span data-ttu-id="01b33-124">此设置启用 IPv6 支持的过时成员<xref:System.Net.Dns>类： <xref:System.Net.Dns.BeginGetHostByName%2A>， <xref:System.Net.Dns.BeginResolve%2A>， <xref:System.Net.Dns.EndGetHostByName%2A>， <xref:System.Net.Dns.EndResolve%2A>， <xref:System.Net.Dns.GetHostByAddress%2A>， <xref:System.Net.Dns.GetHostByName%2A>，和<xref:System.Net.Dns.Resolve%2A>。</span><span class="sxs-lookup"><span data-stu-id="01b33-124">This setting enables IPv6 support for the obsolete members of the <xref:System.Net.Dns> class: <xref:System.Net.Dns.BeginGetHostByName%2A>, <xref:System.Net.Dns.BeginResolve%2A>, <xref:System.Net.Dns.EndGetHostByName%2A>, <xref:System.Net.Dns.EndResolve%2A>, <xref:System.Net.Dns.GetHostByAddress%2A>, <xref:System.Net.Dns.GetHostByName%2A>, and <xref:System.Net.Dns.Resolve%2A>.</span></span> <span data-ttu-id="01b33-125">有关的其他成员<xref:System.Net?displayProperty=nameWithType>命名空间，如果在操作系统中启用了 IPv6，则可能会返回 IPv6 地址。</span><span class="sxs-lookup"><span data-stu-id="01b33-125">For other members of the <xref:System.Net?displayProperty=nameWithType> namespace, IPv6 addresses may be returned if IPv6 is enabled in the operating system.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="01b33-126">配置文件</span><span class="sxs-lookup"><span data-stu-id="01b33-126">Configuration Files</span></span>  
 <span data-ttu-id="01b33-127">此元素可在应用程序配置文件或计算机配置文件 (Machine.config) 中使用。</span><span class="sxs-lookup"><span data-stu-id="01b33-127">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="01b33-128">示例</span><span class="sxs-lookup"><span data-stu-id="01b33-128">Example</span></span>  
 <span data-ttu-id="01b33-129">下面的示例演示如何启用 IPv6 的支持<xref:System.Net.Dns>类。</span><span class="sxs-lookup"><span data-stu-id="01b33-129">The following example shows how to enable IPv6 support for the <xref:System.Net.Dns> class.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <settings>  
      <ipv6 enabled="true"/>  
    </settings>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="01b33-130">请参阅</span><span class="sxs-lookup"><span data-stu-id="01b33-130">See Also</span></span>  
 <xref:System.Net?displayProperty=nameWithType>  
 <xref:System.Net.Dns?displayProperty=nameWithType>  
 <xref:System.Net.Sockets.Socket.OSSupportsIPv6%2A?displayProperty=nameWithType>  
 [<span data-ttu-id="01b33-131">网络设置架构</span><span class="sxs-lookup"><span data-stu-id="01b33-131">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
