---
title: <proxy> 元素（网络设置）
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/defaultProxy/proxy
- http://schemas.microsoft.com/.NetConfiguration/v2.0#proxy
helpviewer_keywords:
- <proxy> element
- proxy element
ms.assetid: 37a548d8-fade-4ac5-82ec-b49b6c6cb22a
ms.openlocfilehash: a183c4160c4cd55b05c5c23f7a10e3a1d1c74ea4
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/21/2019
ms.locfileid: "69659290"
---
# <a name="proxy-element-network-settings"></a>\<proxy > 元素 (网络设置)
定义代理服务器。  
  
 \<configuration>  
\<system.net>  
\<defaultProxy >  
\<代理 >  
  
## <a name="syntax"></a>语法  
  
```xml  
<proxy
  autoDetect="true|false|unspecified" 
  bypassonlocal="true|false|unspecified"
  proxyaddress="uriString"
  scriptLocation="uriString"
  usesystemdefault="true|false|unspecified"
/>
```  
  
## <a name="attributes-and-elements"></a>特性和元素  
 下列各节描述了特性、子元素和父元素。  
  
### <a name="attributes"></a>特性  
  
|**特性**|**说明**|  
|-------------------|---------------------|  
|`autoDetect`|指定是否自动检测代理。 默认值为 `unspecified`。|  
|`bypassonlocal`|指定对于本地资源是否跳过代理。 本地资源包括本地服务器`http://localhost`(、 `http://loopback`或`http://127.0.0.1`) 和没有句点 (`http://webserver`) 的 URI。 默认值为 `unspecified`。|  
|`proxyaddress`|指定要使用的代理 URI。|  
|`scriptLocation`|指定配置脚本的位置。 不要将`bypassonlocal`属性与此属性一起使用。 |  
|`usesystemdefault`|指定是否使用 Internet Explorer 代理设置。 如果设置为`true`, 则后续特性将重写 Internet Explorer 代理设置。 默认值为 `unspecified`。|  
  
### <a name="child-elements"></a>子元素  
 无。  
  
### <a name="parent-elements"></a>父元素  
  
|**元素**|**说明**|  
|-----------------|---------------------|  
|[defaultProxy](defaultproxy-element-network-settings.md)|配置超文本传输协议 (HTTP) 代理服务器。|  
  
## <a name="text-value"></a>文本值  
  
## <a name="remarks"></a>备注  
 `proxy`元素为应用程序定义代理服务器。 如果配置文件中缺少此元素, 则 .NET Framework 将使用 Internet Explorer 中的代理设置。  
  
 `proxyaddress`特性的值应为格式正确的统一资源标识符 (URI)。  
  
 `scriptLocation`属性指自动检测代理配置脚本。 在<xref:System.Net.WebProxy> Internet Explorer 中选择 "**使用自动配置脚本**" 选项后, 类将尝试查找配置脚本 (通常名为 Wpad)。 如果`bypassonlocal`设置为任何值, `scriptLocation`则将被忽略。
  
 将 .NET Framework 版本1.1 应用程序的属性迁移到版本2.0。`usesystemdefault`  
  
 如果`proxyaddress`特性指定了无效的默认代理, 则会引发异常。 异常的 <xref:System.Exception.InnerException%2A> 属性应具有错误根本原因的详细信息。  
  
## <a name="configuration-files"></a>配置文件  
 此元素可在应用程序配置文件或计算机配置文件 (Machine.config) 中使用。  
  
## <a name="example"></a>示例  
 以下示例使用 Internet Explorer 代理中的默认值, 指定代理地址, 并绕过代理进行本地访问。  
  
```xml  
<configuration>  
  <system.net>  
    <defaultProxy>  
      <proxy  
        usesystemdefault="true"  
        proxyaddress="http://192.168.1.10:3128"  
        bypassonlocal="true"  
      />  
    </defaultProxy>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a>请参阅

- <xref:System.Net.WebProxy?displayProperty=nameWithType>
- [网络设置架构](index.md)
