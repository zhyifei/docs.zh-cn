---
title: <bypasslist> 元素（网络设置）
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#bypasslist
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/defaultProxy/bypasslist
helpviewer_keywords:
- bypasslist element
- <bypasslist> element
ms.assetid: 124446b7-abb1-4e5e-a492-b64398f268f1
ms.openlocfilehash: 97e69a4978aa4700d13a994619a65312cf70aeaa
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79154941"
---
# <a name="bypasslist-element-network-settings"></a>\<绕过列表>元素（网络设置）
提供一组常规表达式，用于描述不使用代理的地址。  

[**\<配置>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<默认代理>**](defaultproxy-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<绕过列表>**

## <a name="syntax"></a>语法  
  
```xml  
<bypasslist>
</bypasslist>  
```  
  
## <a name="attributes-and-elements"></a>特性和元素  
 下列各节描述了特性、子元素和父元素。  
  
### <a name="attributes"></a>属性  
 无。  
  
### <a name="child-elements"></a>子元素  
  
|**元素**|**说明**|  
|-----------------|---------------------|  
|[添加](add-element-for-bypasslist-network-settings.md)|将 IP 地址或 DNS 名称添加到代理绕过列表中。|  
|[清楚](clear-element-for-bypasslist-network-settings.md)|清除旁路列表。|  
|[删除](remove-element-for-bypasslist-network-settings.md)|从代理绕过列表中删除 IP 地址或 DNS 名称。|  
  
### <a name="parent-elements"></a>父元素  
  
|**元素**|**说明**|  
|-----------------|---------------------|  
|[defaultProxy](defaultproxy-element-network-settings.md)|配置超文本传输协议 (HTTP) 代理服务器。|  
  
## <a name="remarks"></a>备注  
 旁路列表包含常规表达式，用于描述<xref:System.Net.WebRequest>实例直接访问而不是通过代理服务器访问的 URI。  
  
 为此元素指定正则表达式时应小心谨慎。 正则表达式"[a-z].contoso\\\\.com"与contoso.com域中的任何主机匹配，但它也与contoso.com.cpandl.com域中的任何主机匹配。 要仅匹配contoso.com域中的主机，请使用锚点（"$"）："[a-z].contoso.com$"。\\\\  
  
 有关正则表达式的详细信息，请参阅。[.NET 框架正则表达式](../../../../standard/base-types/regular-expressions.md)。  
  
## <a name="configuration-files"></a>配置文件  
 此元素可在应用程序配置文件或计算机配置文件 (Machine.config) 中使用。  
  
## <a name="example"></a>示例  
 下面的示例将两个地址添加到旁路列表中。 第一个绕过contoso.com域中所有服务器的代理;第二个服务器绕过其 IP 地址以 192.168 开头的所有服务器的代理。  
  
```xml  
<configuration>  
  <system.net>  
    <defaultProxy>  
      <bypasslist>  
        <add address="[a-z]+\.contoso\.com$" />  
        <add address="192\.168\.\d{1,3}\.\d{1,3}" />  
      </bypasslist>  
    </defaultProxy>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Net.WebProxy?displayProperty=nameWithType>
- [网络设置架构](index.md)
