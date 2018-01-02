---
title: "&lt;套接字&gt;元素 （网络设置）"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/settings/socket
- http://schemas.microsoft.com/.NetConfiguration/v2.0#socket
helpviewer_keywords:
- <socket> element
- socket element
ms.assetid: 366c634c-7d16-478f-aedf-053eda94a1a0
caps.latest.revision: "21"
author: mcleblanc
ms.author: markl
manager: markl
ms.workload: dotnet
ms.openlocfilehash: fefb8e119d428d86501e1c8cdd5eec5ef0809cbd
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="ltsocketgt-element-network-settings"></a><span data-ttu-id="3cd7d-102">&lt;套接字&gt;元素 （网络设置）</span><span class="sxs-lookup"><span data-stu-id="3cd7d-102">&lt;socket&gt; Element (Network Settings)</span></span>
<span data-ttu-id="3cd7d-103">指定的套接字操作是否使用完成端口。</span><span class="sxs-lookup"><span data-stu-id="3cd7d-103">Specifies whether socket operations use completion ports.</span></span>  
  
 <span data-ttu-id="3cd7d-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="3cd7d-104">\<configuration></span></span>  
<span data-ttu-id="3cd7d-105">\<system.net ></span><span class="sxs-lookup"><span data-stu-id="3cd7d-105">\<system.net></span></span>  
<span data-ttu-id="3cd7d-106">\<设置 ></span><span class="sxs-lookup"><span data-stu-id="3cd7d-106">\<settings></span></span>  
<span data-ttu-id="3cd7d-107">\<套接字 ></span><span class="sxs-lookup"><span data-stu-id="3cd7d-107">\<socket></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3cd7d-108">语法</span><span class="sxs-lookup"><span data-stu-id="3cd7d-108">Syntax</span></span>  
  
```xml  
<socket  
  alwaysUseCompletionPortsForConnect="true|false"  
  alwaysUseCompletionPortsForAccept="true|false"  
  ipProtectionLevel="EdgeRestricted|Restricted|Unrestricted|Unspecified"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3cd7d-109">特性和元素</span><span class="sxs-lookup"><span data-stu-id="3cd7d-109">Attributes and Elements</span></span>  
 <span data-ttu-id="3cd7d-110">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="3cd7d-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3cd7d-111">特性</span><span class="sxs-lookup"><span data-stu-id="3cd7d-111">Attributes</span></span>  
  
|<span data-ttu-id="3cd7d-112">**特性**</span><span class="sxs-lookup"><span data-stu-id="3cd7d-112">**Attribute**</span></span>|<span data-ttu-id="3cd7d-113">**说明**</span><span class="sxs-lookup"><span data-stu-id="3cd7d-113">**Description**</span></span>|  
|-------------------|---------------------|  
|`alwaysUseCompletionPortsForAccept`|<span data-ttu-id="3cd7d-114">指示是否套接字始终应该使用完成端口用于接受方法调用。</span><span class="sxs-lookup"><span data-stu-id="3cd7d-114">Indicates whether the socket should always use completion ports for Accept method calls.</span></span> <span data-ttu-id="3cd7d-115">默认值为 `false`。</span><span class="sxs-lookup"><span data-stu-id="3cd7d-115">The default value is `false`.</span></span>|  
|`alwaysUseCompletionPortsForConnect`|<span data-ttu-id="3cd7d-116">指示是否套接字始终应连接方法调用使用完成端口。</span><span class="sxs-lookup"><span data-stu-id="3cd7d-116">Indicates whether the socket should always use completion ports for Connect method calls.</span></span> <span data-ttu-id="3cd7d-117">默认值为 `false`。</span><span class="sxs-lookup"><span data-stu-id="3cd7d-117">The default value is `false`.</span></span>|  
|`ipProtectionLevel`|<span data-ttu-id="3cd7d-118">指定的默认<xref:System.Net.Sockets.IPProtectionLevel?displayProperty=nameWithType>用于套接字。</span><span class="sxs-lookup"><span data-stu-id="3cd7d-118">Specifies the default <xref:System.Net.Sockets.IPProtectionLevel?displayProperty=nameWithType> to use for a socket.</span></span> <span data-ttu-id="3cd7d-119">默认值取决于 Windows 的版本。</span><span class="sxs-lookup"><span data-stu-id="3cd7d-119">The default value depends on the version of Windows.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="3cd7d-120">子元素</span><span class="sxs-lookup"><span data-stu-id="3cd7d-120">Child Elements</span></span>  
 <span data-ttu-id="3cd7d-121">无。</span><span class="sxs-lookup"><span data-stu-id="3cd7d-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="3cd7d-122">父元素</span><span class="sxs-lookup"><span data-stu-id="3cd7d-122">Parent Elements</span></span>  
  
|<span data-ttu-id="3cd7d-123">**元素**</span><span class="sxs-lookup"><span data-stu-id="3cd7d-123">**Element**</span></span>|<span data-ttu-id="3cd7d-124">**说明**</span><span class="sxs-lookup"><span data-stu-id="3cd7d-124">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="3cd7d-125">设置</span><span class="sxs-lookup"><span data-stu-id="3cd7d-125">settings</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/settings-element-network-settings.md)|<span data-ttu-id="3cd7d-126">配置 <xref:System.Net> 命名空间的基本网络选项。</span><span class="sxs-lookup"><span data-stu-id="3cd7d-126">Configures basic network options for the <xref:System.Net> namespace.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3cd7d-127">备注</span><span class="sxs-lookup"><span data-stu-id="3cd7d-127">Remarks</span></span>  
 <span data-ttu-id="3cd7d-128">`alwaysUseCompletionPortsForAccept` 和 `alwaysUseCompletionPortsForConnect` 特性用于指定 <xref:System.Net.Sockets?displayProperty=nameWithType>.namespace 中的类在使用完全端口时的默认行为。</span><span class="sxs-lookup"><span data-stu-id="3cd7d-128">The `alwaysUseCompletionPortsForAccept` and `alwaysUseCompletionPortsForConnect` attributes are used to specify the default behavior regarding the use of completion ports by the classes in the <xref:System.Net.Sockets?displayProperty=nameWithType>.namespace.</span></span> <span data-ttu-id="3cd7d-129">对于高性能服务器应用程序建议使用完成端口。</span><span class="sxs-lookup"><span data-stu-id="3cd7d-129">Completion ports are recommended for high performance server applications.</span></span>  
  
 <span data-ttu-id="3cd7d-130">默认值为`alwaysUseCompletionPortsForAccept`和`alwaysUseCompletionPortsForConnect`属性， **false**。</span><span class="sxs-lookup"><span data-stu-id="3cd7d-130">The default value for the `alwaysUseCompletionPortsForAccept` and `alwaysUseCompletionPortsForConnect` attributes is **false**.</span></span>  
  
 <span data-ttu-id="3cd7d-131"><xref:System.Net.Configuration.SocketElement.AlwaysUseCompletionPortsForAccept%2A>可以用于获取的当前值`alwaysUseCompletionPortsForAccept`从适用的配置文件的属性。</span><span class="sxs-lookup"><span data-stu-id="3cd7d-131">The <xref:System.Net.Configuration.SocketElement.AlwaysUseCompletionPortsForAccept%2A> can be used to get the current value of the `alwaysUseCompletionPortsForAccept` attribute from applicable configuration files.</span></span> <span data-ttu-id="3cd7d-132"><xref:System.Net.Configuration.SocketElement.AlwaysUseCompletionPortsForConnect%2A>可以用于获取的当前值`alwaysUseCompletionPortsForConnect`从适用的配置文件的属性。</span><span class="sxs-lookup"><span data-stu-id="3cd7d-132">The <xref:System.Net.Configuration.SocketElement.AlwaysUseCompletionPortsForConnect%2A> can be used to get the current value of the `alwaysUseCompletionPortsForConnect` attribute from applicable configuration files.</span></span>  
  
 <span data-ttu-id="3cd7d-133">`ipProtectionLevel`属性指定的默认<xref:System.Net.Sockets.IPProtectionLevel?displayProperty=nameWithType>用于套接字。</span><span class="sxs-lookup"><span data-stu-id="3cd7d-133">The `ipProtectionLevel` attribute specifies the default <xref:System.Net.Sockets.IPProtectionLevel?displayProperty=nameWithType> to use for a socket.</span></span> <span data-ttu-id="3cd7d-134"><xref:System.Net.Configuration.SocketElement.IPProtectionLevel%2A>属性可配置到指定的作用域，将 IPv6 套接字的限制，如具有相同的地址的链接本地或站点本地前缀。</span><span class="sxs-lookup"><span data-stu-id="3cd7d-134">The <xref:System.Net.Configuration.SocketElement.IPProtectionLevel%2A> property enables configuration of a restriction for an IPv6 socket to a specified scope, such as addresses with the same link local or site local prefix.</span></span> <span data-ttu-id="3cd7d-135">此选项使应用程序可以限制对 IPv6 套接字的访问。</span><span class="sxs-lookup"><span data-stu-id="3cd7d-135">This option enables applications to place access restrictions on IPv6 sockets.</span></span> <span data-ttu-id="3cd7d-136">通过应用此类限制，可让在专用局域网上运行的应用程序能够通过简单的方式很好地增强自身的安全性，以便防范外部攻击。</span><span class="sxs-lookup"><span data-stu-id="3cd7d-136">Such restrictions enable an application running on a private LAN to simply and robustly harden itself against external attacks.</span></span> <span data-ttu-id="3cd7d-137">此选项可以扩大或缩小侦听套接字，从而使得公共和私有用户如果合适的话，或对同一站点中，根据需要限制的访问的不受限制访问的范围。</span><span class="sxs-lookup"><span data-stu-id="3cd7d-137">This option widens or narrows the scope of a listening socket, enabling unrestricted access from public and private users when appropriate, or restricting access only to the same site, as required.</span></span>  
  
 <span data-ttu-id="3cd7d-138">这`ipProtectionLevel`属性设置会影响仅初始的传入流量：</span><span class="sxs-lookup"><span data-stu-id="3cd7d-138">This `ipProtectionLevel` attribute setting affects only initial incoming traffic:</span></span>  
  
-   <span data-ttu-id="3cd7d-139">TCP 服务器侦听套接字上的传入连接。</span><span class="sxs-lookup"><span data-stu-id="3cd7d-139">A TCP server listening for incoming connections on a socket.</span></span>  
  
-   <span data-ttu-id="3cd7d-140">接收套接字上的数据包一个 UDP 应用程序。</span><span class="sxs-lookup"><span data-stu-id="3cd7d-140">A UDP application receiving a packet on a socket.</span></span>  
  
 <span data-ttu-id="3cd7d-141">此配置设置不会影响已建立的 TCP 连接 （两个方向对流量无限制），不影响应用程序发送 UDP 数据包。</span><span class="sxs-lookup"><span data-stu-id="3cd7d-141">This configuration setting does not affect already established TCP connections (traffic is unrestricted in both directions) and does not affect an application sending UDP packets.</span></span>  
  
 <span data-ttu-id="3cd7d-142">可能值`ipProtectionLevel`属性设置中指定的已定义的保护级别与对应<xref:System.Net.Sockets.IPProtectionLevel?displayProperty=nameWithType>枚举，如下所示：</span><span class="sxs-lookup"><span data-stu-id="3cd7d-142">The possible values for the `ipProtectionLevel` attribute setting correspond with the defined protection levels specified in the <xref:System.Net.Sockets.IPProtectionLevel?displayProperty=nameWithType> enumeration as follows:</span></span>  
  
|<span data-ttu-id="3cd7d-143">**属性值**</span><span class="sxs-lookup"><span data-stu-id="3cd7d-143">**Attribute Value**</span></span>|<span data-ttu-id="3cd7d-144">**说明**</span><span class="sxs-lookup"><span data-stu-id="3cd7d-144">**Description**</span></span>|  
|-|-|  
|<span data-ttu-id="3cd7d-145">EdgeRestricted</span><span class="sxs-lookup"><span data-stu-id="3cd7d-145">EdgeRestricted</span></span>|<span data-ttu-id="3cd7d-146">IP 保护级别是受限的边缘。</span><span class="sxs-lookup"><span data-stu-id="3cd7d-146">The IP protection level is edge restricted.</span></span> <span data-ttu-id="3cd7d-147">设计在 internet 上运行的应用程序将使用此值。</span><span class="sxs-lookup"><span data-stu-id="3cd7d-147">This value would be used by applications designed to operate across the Internet.</span></span> <span data-ttu-id="3cd7d-148">此设置不允许使用 Windows Teredo 实现的网络地址转换 (NAT) 遍历。</span><span class="sxs-lookup"><span data-stu-id="3cd7d-148">This setting does not allow Network Address Translation (NAT) traversal using the Windows Teredo implementation.</span></span> <span data-ttu-id="3cd7d-149">这些应用程序可能会绕过 IPv4 防火墙，因此必须针对 Internet 攻击在打开的端口定向强化应用程序。</span><span class="sxs-lookup"><span data-stu-id="3cd7d-149">These applications may bypass IPv4 firewalls, so applications must be hardened against Internet attacks directed at the opened port.</span></span> <span data-ttu-id="3cd7d-150">在 Windows Server 2003 和 Windows XP，套接字上的 IP 保护级别的默认值是受限的边缘。</span><span class="sxs-lookup"><span data-stu-id="3cd7d-150">On Windows Server 2003 and Windows XP, the default value for the IP Protection level on a socket is edge restricted.</span></span>|  
|<span data-ttu-id="3cd7d-151">限制</span><span class="sxs-lookup"><span data-stu-id="3cd7d-151">Restricted</span></span>|<span data-ttu-id="3cd7d-152">IP 保护级别是受限的。</span><span class="sxs-lookup"><span data-stu-id="3cd7d-152">The IP protection level is restricted.</span></span> <span data-ttu-id="3cd7d-153">未实现 Internet 方案的 intranet 应用程序将使用此值。</span><span class="sxs-lookup"><span data-stu-id="3cd7d-153">This value would be used by intranet applications that do not implement Internet scenarios.</span></span> <span data-ttu-id="3cd7d-154">通常，这些应用程序是不要测试或者针对 Internet 样式攻击强化。</span><span class="sxs-lookup"><span data-stu-id="3cd7d-154">These applications are generally not tested or hardened against Internet-style attacks.</span></span> <span data-ttu-id="3cd7d-155">此设置将限制到仅链接本地的接收的流量。</span><span class="sxs-lookup"><span data-stu-id="3cd7d-155">This setting will limit the received traffic to link-local only.</span></span>|  
|<span data-ttu-id="3cd7d-156">不受限制</span><span class="sxs-lookup"><span data-stu-id="3cd7d-156">Unrestricted</span></span>|<span data-ttu-id="3cd7d-157">IP 保护级别是不受限制。</span><span class="sxs-lookup"><span data-stu-id="3cd7d-157">The IP protection level is unrestricted.</span></span> <span data-ttu-id="3cd7d-158">应用程序设计为在 Internet 上，包括利用内置的 IPv6 NAT 遍历功能的应用程序运行时将使用此值为 Windows (例如，Teredo)。</span><span class="sxs-lookup"><span data-stu-id="3cd7d-158">This value would be used by applications designed to operate across the Internet, including applications taking advantage of IPv6 NAT traversal capabilities built into Windows (Teredo, for example).</span></span> <span data-ttu-id="3cd7d-159">这些应用程序可能会绕过 IPv4 防火墙，因此必须针对 Internet 攻击在打开的端口定向强化应用程序。</span><span class="sxs-lookup"><span data-stu-id="3cd7d-159">These applications may bypass IPv4 firewalls, so applications must be hardened against Internet attacks directed at the opened port.</span></span> <span data-ttu-id="3cd7d-160">在 Windows Server 2008 R2 和 Windows Vista，套接字上的 IP 保护级别的默认值是不受限制。</span><span class="sxs-lookup"><span data-stu-id="3cd7d-160">On Windows Server 2008 R2 and Windows Vista, the default value for the IP Protection level on a socket is unrestricted.</span></span>|  
|<span data-ttu-id="3cd7d-161">未指定</span><span class="sxs-lookup"><span data-stu-id="3cd7d-161">Unspecified</span></span>|<span data-ttu-id="3cd7d-162">IP 保护级别是未指定。</span><span class="sxs-lookup"><span data-stu-id="3cd7d-162">The IP protection level is unspecified.</span></span> <span data-ttu-id="3cd7d-163">在 Windows 7 和 Windows Server 2008 R2，套接字上的 IP 保护级别的默认值是未指定。</span><span class="sxs-lookup"><span data-stu-id="3cd7d-163">On Windows 7 and Windows Server 2008 R2, the default value for the IP Protection level on a socket is unspecified.</span></span>|  
  
 <span data-ttu-id="3cd7d-164">默认值为`ipProtectionLevel`属性是**未指定**。</span><span class="sxs-lookup"><span data-stu-id="3cd7d-164">The default value for the `ipProtectionLevel` attribute is **Unspecified**.</span></span>  
  
 <span data-ttu-id="3cd7d-165"><xref:System.Net.Configuration.SocketElement.IPProtectionLevel%2A>属性可以用于获取的当前值`ipProtectionLevel`从适用的配置文件的属性。</span><span class="sxs-lookup"><span data-stu-id="3cd7d-165">The <xref:System.Net.Configuration.SocketElement.IPProtectionLevel%2A> property can be used to get the current value of the `ipProtectionLevel` attribute from applicable configuration files.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="3cd7d-166">配置文件</span><span class="sxs-lookup"><span data-stu-id="3cd7d-166">Configuration Files</span></span>  
 <span data-ttu-id="3cd7d-167">此元素可在应用程序配置文件或计算机配置文件 (Machine.config) 中使用。</span><span class="sxs-lookup"><span data-stu-id="3cd7d-167">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="3cd7d-168">示例</span><span class="sxs-lookup"><span data-stu-id="3cd7d-168">Example</span></span>  
 <span data-ttu-id="3cd7d-169">下面的示例演示如何指定应使用完成端口，以及默认值<xref:System.Net.Sockets.IPProtectionLevel?displayProperty=nameWithType>应为不受限制。</span><span class="sxs-lookup"><span data-stu-id="3cd7d-169">The following example shows how to specify that completion ports should be used and that the default <xref:System.Net.Sockets.IPProtectionLevel?displayProperty=nameWithType> should be unrestricted.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <settings>  
      <socket  
        alwaysUseCompletionPortsForAccept="true"  
        alwaysUseCompletionPortsForConnect="true"  
        ipProtectionLevel="Unrestricted"  
       />  
    </settings>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="3cd7d-170">请参阅</span><span class="sxs-lookup"><span data-stu-id="3cd7d-170">See Also</span></span>  
 <xref:System.Net?displayProperty=nameWithType>  
 <xref:System.Net.Configuration.SocketElement?displayProperty=nameWithType>  
 <xref:System.Net.Sockets?displayProperty=nameWithType>  
 <xref:System.Net.Sockets.IPProtectionLevel?displayProperty=nameWithType>  
 <xref:System.Net.Sockets.SocketOptionName.IPProtectionLevel?displayProperty=nameWithType>  
 [<span data-ttu-id="3cd7d-171">网络设置架构</span><span class="sxs-lookup"><span data-stu-id="3cd7d-171">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
