---
title: <system.Net> 元素（网络设置）
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#system.Net
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.Net
helpviewer_keywords:
- system.Net element
- <system.Net> element
ms.assetid: 52de4d6c-b24d-44aa-ba7d-6b5061f1357e
ms.openlocfilehash: 449146612938700f59f5e2ec761526d1dc66a3fc
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/21/2019
ms.locfileid: "69663961"
---
# <a name="systemnet-element-network-settings"></a>\<system.Net> 元素（网络设置）
包含指定 .NET Framework 如何连接到网络的设置。  
  
 \<configuration>  
\<system.net>  
  
## <a name="syntax"></a>语法  
  
```xml  
<system.net>   
</system.net>  
```  
  
## <a name="attributes-and-elements"></a>特性和元素  
 下列各节描述了特性、子元素和父元素。  
  
### <a name="attributes"></a>特性  
 无。  
  
### <a name="child-elements"></a>子元素  
  
|**元素**|**说明**|  
|-----------------|---------------------|  
|[authenticationModules](authenticationmodules-element-network-settings.md)|指定用于对 Internet 请求进行身份验证的模块。|  
|[connectionManagement](connectionmanagement-element-network-settings.md)|指定与 Internet 主机的最大连接数。|  
|[defaultProxy](defaultproxy-element-network-settings.md)|配置超文本传输协议 (HTTP) 代理服务器。|  
|[mailSettings](mailsettings-element-network-settings.md)|配置简单邮件传输协议 (SMTP) 邮件发送选项。|  
|[requestCaching](requestcaching-element-network-settings.md)|控制网络请求的缓存机制。|  
|[设置](settings-element-network-settings.md)|为<xref:System.Net>和相关子命名空间中的类配置基本网络选项。|  
|[webRequestModules](webrequestmodules-element-network-settings.md)|指定用于从 Internet 主机请求信息的模块。|  
  
### <a name="parent-elements"></a>父元素  
  
|**元素**|**说明**|  
|-----------------|---------------------|  
|[configuration](../configuration-element.md)|包含所有命名空间的设置。|  
  
## <a name="remarks"></a>备注  
 System.object > 元素包含<xref:System.Net>和相关子命名空间中的类的设置。 [ \<](system-net-element-network-settings.md) 设置配置身份验证模块、连接管理、邮件设置、代理服务器和 Internet 请求模块, 用于接收来自 Internet 主机的信息。  
  
## <a name="example"></a>示例  
 下面的示例演示了<xref:System.Net>类使用的典型配置。  
  
```xml  
<configuration>  
  <system.net>  
    <authenticationModules>  
      <add type="System.Net.DigestClient" />  
      <add type="System.Net.NegotiateClient" />  
      <add type="System.Net.KerberosClient" />  
      <add type="System.Net.NtlmClient" />  
      <add type="System.Net.BasicClient" />  
    </authenticationModules>  
    <connectionManagement>  
      <add address="*" maxconnection="2" />  
    </connectionManagement>  
    <defaultProxy>  
      <proxy  
        usesystemdefault="true"  
        bypassonlocal="true"  
      />  
    </defaultProxy>  
    <webRequestModules>  
      <add prefix="http"  
           type="System.Net.HttpRequestCreator"  
      />  
      <add prefix="https"  
           type="System.Net.HttpRequestCreator"  
      />  
      <add prefix="file"  
           type="System.Net.FileWebRequestCreator"  
      />  
    </webRequestModules>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a>请参阅

- [网络设置架构](index.md)
