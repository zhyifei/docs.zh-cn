---
title: bypasslist 的 <add> 元素（网络设置）
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/defaultProxy/bypasslist/add
- http://schemas.microsoft.com/.NetConfiguration/v2.0#add
helpviewer_keywords:
- <bypasslist>, add element
- bypasslist, add element
- <add> element, bypasslist
- add element, bypasslist
ms.assetid: a0b86e28-86b4-4497-abe8-d5fd614c7926
ms.openlocfilehash: 652b8738a201aaa98fa2c5c435fee1a6da91673b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79155072"
---
# <a name="add-element-for-bypasslist-network-settings"></a>\<添加>元素以进行绕过列表（网络设置）
将 IP 地址或 DNS 名称添加到代理绕过列表中。  
  
[**\<配置>**](../configuration-element.md)  
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)  
&nbsp;&nbsp;&nbsp;&nbsp;[**\<默认代理>**](defaultproxy-element-network-settings.md)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<绕过列表>**](bypasslist-element-network-settings.md)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<添加>**  
  
## <a name="syntax"></a>语法  
  
```xml  
<add
  address="regular expression"
/>  
```  
  
## <a name="attributes-and-elements"></a>特性和元素  
 下列各节描述了特性、子元素和父元素。  
  
### <a name="attributes"></a>属性  
  
|**属性**|**说明**|  
|-------------------|---------------------|  
|**address**|描述 IP 地址或 DNS 名称的正则表达式。|  
  
### <a name="child-elements"></a>子元素  
 无。  
  
### <a name="parent-elements"></a>父元素  
  
|**元素**|**说明**|  
|-----------------|---------------------|  
|[bypasslist](bypasslist-element-network-settings.md)|提供一组常规表达式，用于描述不使用代理的地址。|  
  
## <a name="remarks"></a>备注  
 该`add`元素将描述 IP 地址或 DNS 服务器名称的正则表达式插入绕过代理服务器的地址列表中。  
  
 `address`属性的值应是描述一组 IP 地址或主机名的正则表达式。  
  
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
