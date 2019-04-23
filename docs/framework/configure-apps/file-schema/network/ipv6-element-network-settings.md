---
title: <ipv6> 元素（网络设置）
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/settings/ipv6
- http://schemas.microsoft.com/.NetConfiguration/v2.0#ipv6
helpviewer_keywords:
- <ipv6> element
- ipv6 element
ms.assetid: 10b79aef-327b-4718-a892-e11f55e4d169
ms.openlocfilehash: b8969cecf8ffb2ef23522f193bb322b1170e6111
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59089206"
---
# <a name="ipv6-element-network-settings"></a><span data-ttu-id="4da12-102">\<ipv6 > 元素 （网络设置）</span><span class="sxs-lookup"><span data-stu-id="4da12-102">\<ipv6> Element (Network Settings)</span></span>
<span data-ttu-id="4da12-103">启用 Internet 协议版本 6 (IPv6) 的过时成员的响应<xref:System.Net.Dns>类。</span><span class="sxs-lookup"><span data-stu-id="4da12-103">Enables Internet Protocol version 6 (IPv6) responses from obsolete members of the <xref:System.Net.Dns> class.</span></span>  
  
 <span data-ttu-id="4da12-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="4da12-104">\<configuration></span></span>  
<span data-ttu-id="4da12-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="4da12-105">\<system.net></span></span>  
<span data-ttu-id="4da12-106">\<settings></span><span class="sxs-lookup"><span data-stu-id="4da12-106">\<settings></span></span>  
<span data-ttu-id="4da12-107">\<ipv6></span><span class="sxs-lookup"><span data-stu-id="4da12-107">\<ipv6></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4da12-108">语法</span><span class="sxs-lookup"><span data-stu-id="4da12-108">Syntax</span></span>  
  
```xml  
<ipv6  
  enabled="true|false"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4da12-109">特性和元素</span><span class="sxs-lookup"><span data-stu-id="4da12-109">Attributes and Elements</span></span>  
 <span data-ttu-id="4da12-110">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="4da12-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4da12-111">特性</span><span class="sxs-lookup"><span data-stu-id="4da12-111">Attributes</span></span>  
  
|<span data-ttu-id="4da12-112">**特性**</span><span class="sxs-lookup"><span data-stu-id="4da12-112">**Attribute**</span></span>|<span data-ttu-id="4da12-113">**说明**</span><span class="sxs-lookup"><span data-stu-id="4da12-113">**Description**</span></span>|  
|-------------------|---------------------|  
|`enabled`|<span data-ttu-id="4da12-114">指定是否隶属于<xref:System.Net.Dns>类返回 Internet 协议版本 6 (IPv6) 地址。</span><span class="sxs-lookup"><span data-stu-id="4da12-114">Specifies whether members of the <xref:System.Net.Dns> class return Internet Protocol version 6 (IPv6) addresses.</span></span> <span data-ttu-id="4da12-115">默认值为 `false`。</span><span class="sxs-lookup"><span data-stu-id="4da12-115">The default value is `false`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="4da12-116">子元素</span><span class="sxs-lookup"><span data-stu-id="4da12-116">Child Elements</span></span>  
 <span data-ttu-id="4da12-117">无。</span><span class="sxs-lookup"><span data-stu-id="4da12-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="4da12-118">父元素</span><span class="sxs-lookup"><span data-stu-id="4da12-118">Parent Elements</span></span>  
  
|<span data-ttu-id="4da12-119">**元素**</span><span class="sxs-lookup"><span data-stu-id="4da12-119">**Element**</span></span>|<span data-ttu-id="4da12-120">**说明**</span><span class="sxs-lookup"><span data-stu-id="4da12-120">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="4da12-121">settings</span><span class="sxs-lookup"><span data-stu-id="4da12-121">settings</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/settings-element-network-settings.md)|<span data-ttu-id="4da12-122">配置 <xref:System.Net> 命名空间的基本网络选项。</span><span class="sxs-lookup"><span data-stu-id="4da12-122">Configures basic network options for the <xref:System.Net> namespace.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4da12-123">备注</span><span class="sxs-lookup"><span data-stu-id="4da12-123">Remarks</span></span>  
 <span data-ttu-id="4da12-124">此设置启用 IPv6 支持的过时成员<xref:System.Net.Dns>类： <xref:System.Net.Dns.BeginGetHostByName%2A>， <xref:System.Net.Dns.BeginResolve%2A>， <xref:System.Net.Dns.EndGetHostByName%2A>， <xref:System.Net.Dns.EndResolve%2A>， <xref:System.Net.Dns.GetHostByAddress%2A>， <xref:System.Net.Dns.GetHostByName%2A>，和<xref:System.Net.Dns.Resolve%2A>。</span><span class="sxs-lookup"><span data-stu-id="4da12-124">This setting enables IPv6 support for the obsolete members of the <xref:System.Net.Dns> class: <xref:System.Net.Dns.BeginGetHostByName%2A>, <xref:System.Net.Dns.BeginResolve%2A>, <xref:System.Net.Dns.EndGetHostByName%2A>, <xref:System.Net.Dns.EndResolve%2A>, <xref:System.Net.Dns.GetHostByAddress%2A>, <xref:System.Net.Dns.GetHostByName%2A>, and <xref:System.Net.Dns.Resolve%2A>.</span></span> <span data-ttu-id="4da12-125">有关的其他成员<xref:System.Net?displayProperty=nameWithType>命名空间中，如果在操作系统中启用了 IPv6，则可能会返回 IPv6 地址。</span><span class="sxs-lookup"><span data-stu-id="4da12-125">For other members of the <xref:System.Net?displayProperty=nameWithType> namespace, IPv6 addresses may be returned if IPv6 is enabled in the operating system.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="4da12-126">配置文件</span><span class="sxs-lookup"><span data-stu-id="4da12-126">Configuration Files</span></span>  
 <span data-ttu-id="4da12-127">此元素可在应用程序配置文件或计算机配置文件 (Machine.config) 中使用。</span><span class="sxs-lookup"><span data-stu-id="4da12-127">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="4da12-128">示例</span><span class="sxs-lookup"><span data-stu-id="4da12-128">Example</span></span>  
 <span data-ttu-id="4da12-129">下面的示例演示如何启用 IPv6 支持<xref:System.Net.Dns>类。</span><span class="sxs-lookup"><span data-stu-id="4da12-129">The following example shows how to enable IPv6 support for the <xref:System.Net.Dns> class.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <settings>  
      <ipv6 enabled="true"/>  
    </settings>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="4da12-130">请参阅</span><span class="sxs-lookup"><span data-stu-id="4da12-130">See also</span></span>

- <xref:System.Net?displayProperty=nameWithType>
- <xref:System.Net.Dns?displayProperty=nameWithType>
- <xref:System.Net.Sockets.Socket.OSSupportsIPv6%2A?displayProperty=nameWithType>
- [<span data-ttu-id="4da12-131">网络设置架构</span><span class="sxs-lookup"><span data-stu-id="4da12-131">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
