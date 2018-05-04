---
title: '&lt;httpWebRequest&gt;元素 （网络设置）'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/settings/httpWebRequest
- http://schemas.microsoft.com/.NetConfiguration/v2.0#httpWebRequest
helpviewer_keywords:
- <httpWebRequest> element
- httpWebRequest element
ms.assetid: 52acd9d2-5bdc-4dc4-9c2a-f0a476ccbb31
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 1d1dce38e5188824ba1412d3f2a285bd2304f147
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
---
# <a name="lthttpwebrequestgt-element-network-settings"></a>&lt;httpWebRequest&gt;元素 （网络设置）
自定义 Web 请求参数。  
  
 \<configuration>  
\<system.net>  
\<设置 >  
\<httpWebRequest >  
  
## <a name="syntax"></a>语法  
  
```xml  
<httpWebRequest  
  maximumResponseHeadersLength="size"  
  maximumErrorResponseLength="size"  
  maximumUnauthorizedUploadLength="size"  
  useUnsafeHeaderParsing="true|false"  
/>  
```  
  
## <a name="attributes-and-elements"></a>特性和元素  
 下列各节描述了特性、子元素和父元素。  
  
### <a name="attributes"></a>特性  
  
|**特性**|**说明**|  
|-------------------|---------------------|  
|`maximumResponseHeadersLength`|指定以千字节为单位的响应标头的最大长度。 默认值为 64。 值-1 指示没有大小限制将施加的响应标头。|  
|`maximumErrorResponseLength`|指定错误响应，最大的长度，以千字节为单位。 默认值为 64。 值-1 指示没有大小限制将施加错误响应。|  
|`maximumUnauthorizedUploadLength`|指定为未经授权的错误代码，以字节为单位的响应中上载的最大长度。 默认值为 -1。 值-1 指示没有大小限制将施加上载。|  
|`useUnsafeHeaderParsing`|指定是否启用不安全标头分析。 默认值为 `false`。|  
  
### <a name="child-elements"></a>子元素  
 无。  
  
### <a name="parent-elements"></a>父元素  
  
|**元素**|**说明**|  
|-----------------|---------------------|  
|[设置](../../../../../docs/framework/configure-apps/file-schema/network/settings-element-network-settings.md)|配置 <xref:System.Net> 命名空间的基本网络选项。|  
  
## <a name="remarks"></a>备注  
 默认情况下，.NET Framework 严格强制 RFC 2616 实施 URI 分析。 某些服务器响应可能包括禁止字段，这将导致中的控制字符<xref:System.Net.HttpWebRequest.GetResponse?displayProperty=nameWithType>方法会引发<xref:System.Net.WebException>。 如果**useUnsafeHeaderParsing**设置为**true**，<xref:System.Net.HttpWebRequest.GetResponse?displayProperty=nameWithType>将不会引发这种情况下; 但是，你的应用程序将很容易受到几种形式的 URI 分析攻击。 最佳解决方案是更改服务器，使响应不包含控制字符。  
  
## <a name="configuration-files"></a>配置文件  
 此元素可在应用程序配置文件或计算机配置文件 (Machine.config) 中使用。  
  
## <a name="example"></a>示例  
 下面的示例演示如何指定更大超过正常的最大标头的长度。  
  
```xml  
<configuration>  
  <system.net>  
    <settings>  
      <httpWebRequest  
        maximumResponseHeadersLength="128"  
      />  
    </settings>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Net.HttpWebRequest.MaximumResponseHeadersLength%2A>  
 [网络设置架构](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
