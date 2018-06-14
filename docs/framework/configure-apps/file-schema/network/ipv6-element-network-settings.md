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
# <a name="ltipv6gt-element-network-settings"></a>&lt;ipv6&gt;元素 （网络设置）
启用 Internet 协议版本 6 (IPv6) 响应的过时成员<xref:System.Net.Dns>类。  
  
 \<configuration>  
\<system.net>  
\<设置 >  
\<ipv6 >  
  
## <a name="syntax"></a>语法  
  
```xml  
<ipv6  
  enabled="true|false"  
/>  
```  
  
## <a name="attributes-and-elements"></a>特性和元素  
 下列各节描述了特性、子元素和父元素。  
  
### <a name="attributes"></a>特性  
  
|**特性**|**说明**|  
|-------------------|---------------------|  
|`enabled`|指定是否的成员<xref:System.Net.Dns>类返回 Internet 协议版本 6 (IPv6) 地址。 默认值为 `false`。|  
  
### <a name="child-elements"></a>子元素  
 无。  
  
### <a name="parent-elements"></a>父元素  
  
|**元素**|**说明**|  
|-----------------|---------------------|  
|[设置](../../../../../docs/framework/configure-apps/file-schema/network/settings-element-network-settings.md)|配置 <xref:System.Net> 命名空间的基本网络选项。|  
  
## <a name="remarks"></a>备注  
 此设置启用 IPv6 支持的过时成员<xref:System.Net.Dns>类： <xref:System.Net.Dns.BeginGetHostByName%2A>， <xref:System.Net.Dns.BeginResolve%2A>， <xref:System.Net.Dns.EndGetHostByName%2A>， <xref:System.Net.Dns.EndResolve%2A>， <xref:System.Net.Dns.GetHostByAddress%2A>， <xref:System.Net.Dns.GetHostByName%2A>，和<xref:System.Net.Dns.Resolve%2A>。 有关的其他成员<xref:System.Net?displayProperty=nameWithType>命名空间，如果在操作系统中启用了 IPv6，则可能会返回 IPv6 地址。  
  
## <a name="configuration-files"></a>配置文件  
 此元素可在应用程序配置文件或计算机配置文件 (Machine.config) 中使用。  
  
## <a name="example"></a>示例  
 下面的示例演示如何启用 IPv6 的支持<xref:System.Net.Dns>类。  
  
```xml  
<configuration>  
  <system.net>  
    <settings>  
      <ipv6 enabled="true"/>  
    </settings>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Net?displayProperty=nameWithType>  
 <xref:System.Net.Dns?displayProperty=nameWithType>  
 <xref:System.Net.Sockets.Socket.OSSupportsIPv6%2A?displayProperty=nameWithType>  
 [网络设置架构](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
