---
title: <socket> 元素（网络设置）
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/settings/socket
- http://schemas.microsoft.com/.NetConfiguration/v2.0#socket
helpviewer_keywords:
- <socket> element
- socket element
ms.assetid: 366c634c-7d16-478f-aedf-053eda94a1a0
ms.openlocfilehash: ec2c8388411e24940041dc9dcb7f6a6755e89805
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/01/2019
ms.locfileid: "71697576"
---
# <a name="socket-element-network-settings"></a><span data-ttu-id="ce505-102">\<socket > 元素（网络设置）</span><span class="sxs-lookup"><span data-stu-id="ce505-102">\<socket> Element (Network Settings)</span></span>
<span data-ttu-id="ce505-103">指定套接字操作是否使用完成端口。</span><span class="sxs-lookup"><span data-stu-id="ce505-103">Specifies whether socket operations use completion ports.</span></span>  
  
[<span data-ttu-id="ce505-104"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="ce505-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="ce505-105">&nbsp; @ no__t[ **\<system >** ](system-net-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="ce505-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span></span>  
<span data-ttu-id="ce505-106">&nbsp; @ no__t-1 @ no__t-2 @ no__t[ **\<settings >** ](settings-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="ce505-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<settings>**](settings-element-network-settings.md)</span></span>  
<span data-ttu-id="ce505-107">&nbsp; @ no__t-1 @ no__t-2 @ no__t-3 @ no__t-4 @ no__t-5 **\<socket >**</span><span class="sxs-lookup"><span data-stu-id="ce505-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<socket>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ce505-108">语法</span><span class="sxs-lookup"><span data-stu-id="ce505-108">Syntax</span></span>  
  
```xml  
<socket  
  alwaysUseCompletionPortsForConnect="true|false"  
  alwaysUseCompletionPortsForAccept="true|false"  
  ipProtectionLevel="EdgeRestricted|Restricted|Unrestricted|Unspecified"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ce505-109">特性和元素</span><span class="sxs-lookup"><span data-stu-id="ce505-109">Attributes and Elements</span></span>  
 <span data-ttu-id="ce505-110">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="ce505-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ce505-111">特性</span><span class="sxs-lookup"><span data-stu-id="ce505-111">Attributes</span></span>  
  
|<span data-ttu-id="ce505-112">**特性**</span><span class="sxs-lookup"><span data-stu-id="ce505-112">**Attribute**</span></span>|<span data-ttu-id="ce505-113">**说明**</span><span class="sxs-lookup"><span data-stu-id="ce505-113">**Description**</span></span>|  
|-------------------|---------------------|  
|`alwaysUseCompletionPortsForAccept`|<span data-ttu-id="ce505-114">指示套接字是否应始终对接受方法调用使用完成端口。</span><span class="sxs-lookup"><span data-stu-id="ce505-114">Indicates whether the socket should always use completion ports for Accept method calls.</span></span> <span data-ttu-id="ce505-115">默认值为 `false`。</span><span class="sxs-lookup"><span data-stu-id="ce505-115">The default value is `false`.</span></span>|  
|`alwaysUseCompletionPortsForConnect`|<span data-ttu-id="ce505-116">指示套接字是否应始终对连接方法调用使用完成端口。</span><span class="sxs-lookup"><span data-stu-id="ce505-116">Indicates whether the socket should always use completion ports for Connect method calls.</span></span> <span data-ttu-id="ce505-117">默认值为 `false`。</span><span class="sxs-lookup"><span data-stu-id="ce505-117">The default value is `false`.</span></span>|  
|`ipProtectionLevel`|<span data-ttu-id="ce505-118">指定要用于套接字的默认 <xref:System.Net.Sockets.IPProtectionLevel?displayProperty=nameWithType>。</span><span class="sxs-lookup"><span data-stu-id="ce505-118">Specifies the default <xref:System.Net.Sockets.IPProtectionLevel?displayProperty=nameWithType> to use for a socket.</span></span> <span data-ttu-id="ce505-119">默认值取决于 Windows 的版本。</span><span class="sxs-lookup"><span data-stu-id="ce505-119">The default value depends on the version of Windows.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ce505-120">子元素</span><span class="sxs-lookup"><span data-stu-id="ce505-120">Child Elements</span></span>  
 <span data-ttu-id="ce505-121">无。</span><span class="sxs-lookup"><span data-stu-id="ce505-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="ce505-122">父元素</span><span class="sxs-lookup"><span data-stu-id="ce505-122">Parent Elements</span></span>  
  
|<span data-ttu-id="ce505-123">**元素**</span><span class="sxs-lookup"><span data-stu-id="ce505-123">**Element**</span></span>|<span data-ttu-id="ce505-124">**说明**</span><span class="sxs-lookup"><span data-stu-id="ce505-124">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="ce505-125">设置</span><span class="sxs-lookup"><span data-stu-id="ce505-125">settings</span></span>](settings-element-network-settings.md)|<span data-ttu-id="ce505-126">配置 <xref:System.Net> 命名空间的基本网络选项。</span><span class="sxs-lookup"><span data-stu-id="ce505-126">Configures basic network options for the <xref:System.Net> namespace.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ce505-127">备注</span><span class="sxs-lookup"><span data-stu-id="ce505-127">Remarks</span></span>  
 <span data-ttu-id="ce505-128">`alwaysUseCompletionPortsForAccept` 和 `alwaysUseCompletionPortsForConnect` 特性用于指定 <xref:System.Net.Sockets?displayProperty=nameWithType>.namespace 中的类在使用完全端口时的默认行为。</span><span class="sxs-lookup"><span data-stu-id="ce505-128">The `alwaysUseCompletionPortsForAccept` and `alwaysUseCompletionPortsForConnect` attributes are used to specify the default behavior regarding the use of completion ports by the classes in the <xref:System.Net.Sockets?displayProperty=nameWithType>.namespace.</span></span> <span data-ttu-id="ce505-129">对于高性能服务器应用程序，建议使用完成端口。</span><span class="sxs-lookup"><span data-stu-id="ce505-129">Completion ports are recommended for high performance server applications.</span></span>  
  
 <span data-ttu-id="ce505-130">@No__t 的默认值为-0，`alwaysUseCompletionPortsForConnect` 属性为**false**。</span><span class="sxs-lookup"><span data-stu-id="ce505-130">The default value for the `alwaysUseCompletionPortsForAccept` and `alwaysUseCompletionPortsForConnect` attributes is **false**.</span></span>  
  
 <span data-ttu-id="ce505-131">@No__t-0 可用于从适用的配置文件中获取 @no__t 的属性的当前值。</span><span class="sxs-lookup"><span data-stu-id="ce505-131">The <xref:System.Net.Configuration.SocketElement.AlwaysUseCompletionPortsForAccept%2A> can be used to get the current value of the `alwaysUseCompletionPortsForAccept` attribute from applicable configuration files.</span></span> <span data-ttu-id="ce505-132">@No__t-0 可用于从适用的配置文件中获取 @no__t 的属性的当前值。</span><span class="sxs-lookup"><span data-stu-id="ce505-132">The <xref:System.Net.Configuration.SocketElement.AlwaysUseCompletionPortsForConnect%2A> can be used to get the current value of the `alwaysUseCompletionPortsForConnect` attribute from applicable configuration files.</span></span>  
  
 <span data-ttu-id="ce505-133">@No__t-0 特性指定要用于套接字的默认 <xref:System.Net.Sockets.IPProtectionLevel?displayProperty=nameWithType>。</span><span class="sxs-lookup"><span data-stu-id="ce505-133">The `ipProtectionLevel` attribute specifies the default <xref:System.Net.Sockets.IPProtectionLevel?displayProperty=nameWithType> to use for a socket.</span></span> <span data-ttu-id="ce505-134">@No__t-0 属性可将 IPv6 套接字的限制配置为指定的作用域，如具有相同的链接本地或站点本地前缀的地址。</span><span class="sxs-lookup"><span data-stu-id="ce505-134">The <xref:System.Net.Configuration.SocketElement.IPProtectionLevel%2A> property enables configuration of a restriction for an IPv6 socket to a specified scope, such as addresses with the same link local or site local prefix.</span></span> <span data-ttu-id="ce505-135">此选项使应用程序可以对 IPv6 套接字设置访问限制。</span><span class="sxs-lookup"><span data-stu-id="ce505-135">This option enables applications to place access restrictions on IPv6 sockets.</span></span> <span data-ttu-id="ce505-136">通过应用此类限制，可让在专用局域网上运行的应用程序能够通过简单的方式很好地增强自身的安全性，以便防范外部攻击。</span><span class="sxs-lookup"><span data-stu-id="ce505-136">Such restrictions enable an application running on a private LAN to simply and robustly harden itself against external attacks.</span></span> <span data-ttu-id="ce505-137">此选项扩大或缩小侦听套接字的范围，在适当的时候启用从公共用户和私有用户进行的不受限制的访问，或根据需要限制对同一站点的访问。</span><span class="sxs-lookup"><span data-stu-id="ce505-137">This option widens or narrows the scope of a listening socket, enabling unrestricted access from public and private users when appropriate, or restricting access only to the same site, as required.</span></span>  
  
 <span data-ttu-id="ce505-138">此 `ipProtectionLevel` 属性设置仅影响初始传入流量：</span><span class="sxs-lookup"><span data-stu-id="ce505-138">This `ipProtectionLevel` attribute setting affects only initial incoming traffic:</span></span>  
  
- <span data-ttu-id="ce505-139">在套接字上侦听传入连接的 TCP 服务器。</span><span class="sxs-lookup"><span data-stu-id="ce505-139">A TCP server listening for incoming connections on a socket.</span></span>  
  
- <span data-ttu-id="ce505-140">在套接字上接收数据包的 UDP 应用程序。</span><span class="sxs-lookup"><span data-stu-id="ce505-140">A UDP application receiving a packet on a socket.</span></span>  
  
 <span data-ttu-id="ce505-141">此配置设置不影响已建立的 TCP 连接（流量在两个方向上无限制），并且不影响发送 UDP 数据包的应用程序。</span><span class="sxs-lookup"><span data-stu-id="ce505-141">This configuration setting does not affect already established TCP connections (traffic is unrestricted in both directions) and does not affect an application sending UDP packets.</span></span>  
  
 <span data-ttu-id="ce505-142">@No__t-0 属性设置的可能值与 <xref:System.Net.Sockets.IPProtectionLevel?displayProperty=nameWithType> 枚举中指定的已定义保护级别相对应，如下所示：</span><span class="sxs-lookup"><span data-stu-id="ce505-142">The possible values for the `ipProtectionLevel` attribute setting correspond with the defined protection levels specified in the <xref:System.Net.Sockets.IPProtectionLevel?displayProperty=nameWithType> enumeration as follows:</span></span>  
  
|<span data-ttu-id="ce505-143">**特性值**</span><span class="sxs-lookup"><span data-stu-id="ce505-143">**Attribute Value**</span></span>|<span data-ttu-id="ce505-144">**说明**</span><span class="sxs-lookup"><span data-stu-id="ce505-144">**Description**</span></span>|  
|-|-|  
|<span data-ttu-id="ce505-145">EdgeRestricted</span><span class="sxs-lookup"><span data-stu-id="ce505-145">EdgeRestricted</span></span>|<span data-ttu-id="ce505-146">IP 保护级别是 "边缘受限的"。</span><span class="sxs-lookup"><span data-stu-id="ce505-146">The IP protection level is edge restricted.</span></span> <span data-ttu-id="ce505-147">此值将由设计为在 Internet 上运行的应用程序使用。</span><span class="sxs-lookup"><span data-stu-id="ce505-147">This value would be used by applications designed to operate across the Internet.</span></span> <span data-ttu-id="ce505-148">此设置不允许使用 Windows Teredo 实现进行网络地址转换（NAT）遍历。</span><span class="sxs-lookup"><span data-stu-id="ce505-148">This setting does not allow Network Address Translation (NAT) traversal using the Windows Teredo implementation.</span></span> <span data-ttu-id="ce505-149">这些应用程序可能会绕过 IPv4 防火墙，因此应用程序必须针对在打开的端口上定向的 Internet 攻击进行强化。</span><span class="sxs-lookup"><span data-stu-id="ce505-149">These applications may bypass IPv4 firewalls, so applications must be hardened against Internet attacks directed at the opened port.</span></span> <span data-ttu-id="ce505-150">在 Windows Server 2003 和 Windows XP 上，套接字的 IP 保护级别的默认值是 "边缘受限的"。</span><span class="sxs-lookup"><span data-stu-id="ce505-150">On Windows Server 2003 and Windows XP, the default value for the IP Protection level on a socket is edge restricted.</span></span>|  
|<span data-ttu-id="ce505-151">限制</span><span class="sxs-lookup"><span data-stu-id="ce505-151">Restricted</span></span>|<span data-ttu-id="ce505-152">IP 保护级别是受限的。</span><span class="sxs-lookup"><span data-stu-id="ce505-152">The IP protection level is restricted.</span></span> <span data-ttu-id="ce505-153">此值将由未实现 Internet 方案的 intranet 应用程序使用。</span><span class="sxs-lookup"><span data-stu-id="ce505-153">This value would be used by intranet applications that do not implement Internet scenarios.</span></span> <span data-ttu-id="ce505-154">通常，这些应用程序不会针对 Internet 样式的攻击进行测试或强化。</span><span class="sxs-lookup"><span data-stu-id="ce505-154">These applications are generally not tested or hardened against Internet-style attacks.</span></span> <span data-ttu-id="ce505-155">此设置会将接收的流量仅限制为本地链接。</span><span class="sxs-lookup"><span data-stu-id="ce505-155">This setting will limit the received traffic to link-local only.</span></span>|  
|<span data-ttu-id="ce505-156">不受限制</span><span class="sxs-lookup"><span data-stu-id="ce505-156">Unrestricted</span></span>|<span data-ttu-id="ce505-157">IP 保护级别是不受限制的。</span><span class="sxs-lookup"><span data-stu-id="ce505-157">The IP protection level is unrestricted.</span></span> <span data-ttu-id="ce505-158">此值将由设计为在 Internet 上运行的应用程序使用，包括利用 Windows 内置的 IPv6 NAT 遍历功能的应用程序（例如 Teredo）。</span><span class="sxs-lookup"><span data-stu-id="ce505-158">This value would be used by applications designed to operate across the Internet, including applications taking advantage of IPv6 NAT traversal capabilities built into Windows (Teredo, for example).</span></span> <span data-ttu-id="ce505-159">这些应用程序可能会绕过 IPv4 防火墙，因此应用程序必须针对在打开的端口上定向的 Internet 攻击进行强化。</span><span class="sxs-lookup"><span data-stu-id="ce505-159">These applications may bypass IPv4 firewalls, so applications must be hardened against Internet attacks directed at the opened port.</span></span> <span data-ttu-id="ce505-160">在 Windows Server 2008 R2 和 Windows Vista 上，针对套接字的 IP 保护级别的默认值是不受限制的。</span><span class="sxs-lookup"><span data-stu-id="ce505-160">On Windows Server 2008 R2 and Windows Vista, the default value for the IP Protection level on a socket is unrestricted.</span></span>|  
|<span data-ttu-id="ce505-161">未指定</span><span class="sxs-lookup"><span data-stu-id="ce505-161">Unspecified</span></span>|<span data-ttu-id="ce505-162">未指定 IP 保护级别。</span><span class="sxs-lookup"><span data-stu-id="ce505-162">The IP protection level is unspecified.</span></span> <span data-ttu-id="ce505-163">在 Windows 7 和 Windows Server 2008 R2 上，未指定套接字上 IP 保护级别的默认值。</span><span class="sxs-lookup"><span data-stu-id="ce505-163">On Windows 7 and Windows Server 2008 R2, the default value for the IP Protection level on a socket is unspecified.</span></span>|  
  
 <span data-ttu-id="ce505-164">**未指定**`ipProtectionLevel` 属性的默认值。</span><span class="sxs-lookup"><span data-stu-id="ce505-164">The default value for the `ipProtectionLevel` attribute is **Unspecified**.</span></span>  
  
 <span data-ttu-id="ce505-165">@No__t-0 属性可用于从适用的配置文件中获取 @no__t 的属性的当前值。</span><span class="sxs-lookup"><span data-stu-id="ce505-165">The <xref:System.Net.Configuration.SocketElement.IPProtectionLevel%2A> property can be used to get the current value of the `ipProtectionLevel` attribute from applicable configuration files.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="ce505-166">配置文件</span><span class="sxs-lookup"><span data-stu-id="ce505-166">Configuration Files</span></span>  
 <span data-ttu-id="ce505-167">此元素可在应用程序配置文件或计算机配置文件 (Machine.config) 中使用。</span><span class="sxs-lookup"><span data-stu-id="ce505-167">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="ce505-168">示例</span><span class="sxs-lookup"><span data-stu-id="ce505-168">Example</span></span>  
 <span data-ttu-id="ce505-169">下面的示例演示如何指定应使用完成端口，并且默认 <xref:System.Net.Sockets.IPProtectionLevel?displayProperty=nameWithType> 应是不受限制的。</span><span class="sxs-lookup"><span data-stu-id="ce505-169">The following example shows how to specify that completion ports should be used and that the default <xref:System.Net.Sockets.IPProtectionLevel?displayProperty=nameWithType> should be unrestricted.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="ce505-170">请参阅</span><span class="sxs-lookup"><span data-stu-id="ce505-170">See also</span></span>

- <xref:System.Net?displayProperty=nameWithType>
- <xref:System.Net.Configuration.SocketElement?displayProperty=nameWithType>
- <xref:System.Net.Sockets?displayProperty=nameWithType>
- <xref:System.Net.Sockets.IPProtectionLevel?displayProperty=nameWithType>
- <xref:System.Net.Sockets.SocketOptionName.IPProtectionLevel?displayProperty=nameWithType>
- [<span data-ttu-id="ce505-171">网络设置架构</span><span class="sxs-lookup"><span data-stu-id="ce505-171">Network Settings Schema</span></span>](index.md)
