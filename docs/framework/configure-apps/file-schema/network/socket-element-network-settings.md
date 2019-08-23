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
ms.openlocfilehash: aa455945b839ada4100138d5bdf9fc239376e5cb
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/21/2019
ms.locfileid: "69663976"
---
# <a name="socket-element-network-settings"></a>\<socket > 元素 (网络设置)
指定套接字操作是否使用完成端口。  
  
 \<configuration>  
\<system.net>  
\<设置 >  
\<socket>  
  
## <a name="syntax"></a>语法  
  
```xml  
<socket  
  alwaysUseCompletionPortsForConnect="true|false"  
  alwaysUseCompletionPortsForAccept="true|false"  
  ipProtectionLevel="EdgeRestricted|Restricted|Unrestricted|Unspecified"  
/>  
```  
  
## <a name="attributes-and-elements"></a>特性和元素  
 下列各节描述了特性、子元素和父元素。  
  
### <a name="attributes"></a>特性  
  
|**特性**|**说明**|  
|-------------------|---------------------|  
|`alwaysUseCompletionPortsForAccept`|指示套接字是否应始终对接受方法调用使用完成端口。 默认值为 `false`。|  
|`alwaysUseCompletionPortsForConnect`|指示套接字是否应始终对连接方法调用使用完成端口。 默认值为 `false`。|  
|`ipProtectionLevel`|指定要用于<xref:System.Net.Sockets.IPProtectionLevel?displayProperty=nameWithType>套接字的默认。 默认值取决于 Windows 的版本。|  
  
### <a name="child-elements"></a>子元素  
 无。  
  
### <a name="parent-elements"></a>父元素  
  
|**元素**|**说明**|  
|-----------------|---------------------|  
|[设置](settings-element-network-settings.md)|配置 <xref:System.Net> 命名空间的基本网络选项。|  
  
## <a name="remarks"></a>备注  
 `alwaysUseCompletionPortsForAccept` 和 `alwaysUseCompletionPortsForConnect` 特性用于指定 <xref:System.Net.Sockets?displayProperty=nameWithType>.namespace 中的类在使用完全端口时的默认行为。 对于高性能服务器应用程序, 建议使用完成端口。  
  
 `alwaysUseCompletionPortsForAccept` 和`alwaysUseCompletionPortsForConnect`特性的默认值为**false**。  
  
 可用于从适用的配置文件中获取`alwaysUseCompletionPortsForAccept`特性的当前值。 <xref:System.Net.Configuration.SocketElement.AlwaysUseCompletionPortsForAccept%2A> 可用于从适用的配置文件中获取`alwaysUseCompletionPortsForConnect`特性的当前值。 <xref:System.Net.Configuration.SocketElement.AlwaysUseCompletionPortsForConnect%2A>  
  
 特性指定要用于套接字的默认<xref:System.Net.Sockets.IPProtectionLevel?displayProperty=nameWithType>。 `ipProtectionLevel` <xref:System.Net.Configuration.SocketElement.IPProtectionLevel%2A>属性允许将 IPv6 套接字的限制配置为指定的作用域, 如具有相同的链接本地或站点本地前缀的地址。 此选项使应用程序可以对 IPv6 套接字设置访问限制。 通过应用此类限制，可让在专用局域网上运行的应用程序能够通过简单的方式很好地增强自身的安全性，以便防范外部攻击。 此选项扩大或缩小侦听套接字的范围, 在适当的时候启用从公共用户和私有用户进行的不受限制的访问, 或根据需要限制对同一站点的访问。  
  
 此`ipProtectionLevel`属性设置只影响初始传入流量:  
  
- 在套接字上侦听传入连接的 TCP 服务器。  
  
- 在套接字上接收数据包的 UDP 应用程序。  
  
 此配置设置不影响已建立的 TCP 连接 (流量在两个方向上无限制), 并且不影响发送 UDP 数据包的应用程序。  
  
 `ipProtectionLevel`属性设置的可能值与<xref:System.Net.Sockets.IPProtectionLevel?displayProperty=nameWithType>枚举中指定的已定义保护级别相对应, 如下所示:  
  
|**特性值**|**说明**|  
|-|-|  
|EdgeRestricted|IP 保护级别是 "边缘受限的"。 此值将由设计为在 Internet 上运行的应用程序使用。 此设置不允许使用 Windows Teredo 实现进行网络地址转换 (NAT) 遍历。 这些应用程序可能会绕过 IPv4 防火墙, 因此应用程序必须针对在打开的端口上定向的 Internet 攻击进行强化。 在 Windows Server 2003 和 Windows XP 上, 套接字的 IP 保护级别的默认值是 "边缘受限的"。|  
|限制|IP 保护级别是受限的。 此值将由未实现 Internet 方案的 intranet 应用程序使用。 通常, 这些应用程序不会针对 Internet 样式的攻击进行测试或强化。 此设置会将接收的流量仅限制为本地链接。|  
|不受限制|IP 保护级别是不受限制的。 此值将由设计为在 Internet 上运行的应用程序使用, 包括利用 Windows 内置的 IPv6 NAT 遍历功能的应用程序 (例如 Teredo)。 这些应用程序可能会绕过 IPv4 防火墙, 因此应用程序必须针对在打开的端口上定向的 Internet 攻击进行强化。 在 Windows Server 2008 R2 和 Windows Vista 上, 针对套接字的 IP 保护级别的默认值是不受限制的。|  
|未指定|未指定 IP 保护级别。 在 Windows 7 和 Windows Server 2008 R2 上, 未指定套接字上 IP 保护级别的默认值。|  
  
 `ipProtectionLevel` **未指定**该属性的默认值。  
  
 属性可用于从适用的配置文件中获取`ipProtectionLevel`特性的当前值。 <xref:System.Net.Configuration.SocketElement.IPProtectionLevel%2A>  
  
## <a name="configuration-files"></a>配置文件  
 此元素可在应用程序配置文件或计算机配置文件 (Machine.config) 中使用。  
  
## <a name="example"></a>示例  
 下面的示例演示如何指定应使用完成端口, 并且默认值<xref:System.Net.Sockets.IPProtectionLevel?displayProperty=nameWithType>应为 "无限制"。  
  
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
  
## <a name="see-also"></a>请参阅

- <xref:System.Net?displayProperty=nameWithType>
- <xref:System.Net.Configuration.SocketElement?displayProperty=nameWithType>
- <xref:System.Net.Sockets?displayProperty=nameWithType>
- <xref:System.Net.Sockets.IPProtectionLevel?displayProperty=nameWithType>
- <xref:System.Net.Sockets.SocketOptionName.IPProtectionLevel?displayProperty=nameWithType>
- [网络设置架构](index.md)
