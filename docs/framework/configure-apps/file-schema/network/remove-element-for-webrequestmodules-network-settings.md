---
title: webRequestModules 的 <remove> 元素（网络设置）
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/webRequestModules/remove
- http://schemas.microsoft.com/.NetConfiguration/v2.0#remove
helpviewer_keywords:
- remove element, webRequestModules
- webRequestModules, remove element
- <remove> element, webRequestModules
- <webRequestModules>, remove element
ms.assetid: dd84d2fe-2f4f-457a-9d3c-441d0d21cc10
ms.openlocfilehash: 20a586e945a889d1fd8a8d4c5c09c8b790c56fc3
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/21/2019
ms.locfileid: "69664019"
---
# <a name="remove-element-for-webrequestmodules-network-settings"></a>\<删除 webRequestModules 的 > 元素 (网络设置)
从应用程序中移除自定义 Web 请求模块。  
  
 \<configuration>  
\<system.net>  
\<webRequestModules>  
\<remove>  
  
## <a name="syntax"></a>语法  
  
```xml  
<remove   
  prefix="URI prefix"   
/>  
```  
  
## <a name="attributes-and-elements"></a>特性和元素  
 下列各节描述了特性、子元素和父元素。  
  
### <a name="attributes"></a>特性  
  
|**特性**|**说明**|  
|-------------------|---------------------|  
|`prefix`|此 Web 请求模块处理的请求的 URI 前缀。|  
  
### <a name="child-elements"></a>子元素  
 无。  
  
### <a name="parent-elements"></a>父元素  
  
|**元素**|**说明**|  
|-----------------|---------------------|  
|[webRequestModules](webrequestmodules-element-network-settings.md)|指定用于从网络主机请求信息的模块。|  
  
## <a name="remarks"></a>备注  
 `remove`元素将为指定的 URI 前缀删除已注册的 Web 请求模块。  
  
 `prefix`特性的值应为有效 URI 的前导字符, 例如, "`http`" 或 "`http://www.contoso.com`"。  
  
## <a name="configuration-files"></a>配置文件  
 此元素可在应用程序配置文件或计算机配置文件 (Machine.config) 中使用。  
  
## <a name="example"></a>示例  

下面的示例将删除 HTTP 的现有 Web 请求模块, 然后将新的自定义 Web 请求模块注册到`www.contoso.com`的 http 请求。
  
```xml  
<configuration>  
  <system.net>  
    <webRequestModules>  
      <remove prefix="http">  
      <add prefix="http"  
           type="System.Net.HttpRequestCreator, System, Version=2.0.3600.0,  
           Culture=neutral, PublicKeyToken=b77a5c561934e089"  
      />  
    </webRequestModules>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a>请参阅

- <xref:System.Net.WebRequest>
- [网络设置架构](index.md)
