---
title: '&lt;defaultHttpCachePolicy&gt;元素 （网络设置）'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/requestCaching/defaultHttpCachePolicy
- http://schemas.microsoft.com/.NetConfiguration/v2.0#defaultHttpCachePolicy
helpviewer_keywords:
- defaultHttpCachePolicy element
- <defaultHttpCachePolicy> element
ms.assetid: 2c1247d0-39b0-4c12-919a-a925ce075c79
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 0425711687a2f8b40f2c645e1c478d52b56ad979
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
---
# <a name="ltdefaulthttpcachepolicygt-element-network-settings"></a>&lt;defaultHttpCachePolicy&gt;元素 （网络设置）
描述 HTTP 缓存功能是否处于活动状态并描述默认缓存策略。  
  
 \<configuration>  
\<system.net>  
\<requestCaching >  
\<defaultHttpCachePolicy >  
  
## <a name="syntax"></a>语法  
  
```xml  
<defaultHttpCachePolicy  
  policyLevel="BypassCache|Default"  
  minimumFresh="d.hh:mm:ss|minValue|maxValue"  
  maximumAge="d.hh:mm:ss|minValue|maxValue"  
  maximumStale="d.hh:mm:ss|minValue|maxValue"  
/>  
```  
  
## <a name="attributes-and-elements"></a>特性和元素  
 下列各节描述了特性、子元素和父元素。  
  
### <a name="attributes"></a>特性  
  
|特性|描述|  
|---------------|-----------------|  
|`maximumAge`|将缓存的对象标记为过期之前，请指定最大时间间隔。|  
|`maximumStale`|指定超过计算出的新鲜时间缓存的对象标记为过期之前的最长时间。|  
|`minimumFresh`|指定缓存的对象被视为新鲜的最小时间。|  
|`policyLevel`|指定的缓存策略是否自动进行的或是否会绕过缓存。 默认值为 `BypassCache`。|  
  
### <a name="child-elements"></a>子元素  
 无  
  
### <a name="parent-elements"></a>父元素  
  
|元素|描述|  
|-------------|-----------------|  
|[requestCaching](../../../../../docs/framework/configure-apps/file-schema/network/requestcaching-element-network-settings.md)|控制网络请求的缓存机制。|  
  
## <a name="remarks"></a>备注  
 值`policyLevel`属性是`BypassCache`或`Default`。  
  
 值为`maximumAge`， `maximumStale`，和`minimumFresh`元素是格式为显式的时间间隔*d*。*hh*:*mm*:*ss* （天、 小时、 分钟和秒为单位） 或常量`minValue`或`maxValue`适当。  
  
## <a name="configuration-files"></a>配置文件  
 此元素可在应用程序配置文件或计算机配置文件 (Machine.config) 中使用。  
  
## <a name="example"></a>示例  
 下面的示例演示如何指定六个小时，为两天，最长使用期限时间和四个小时的最长过期时间的最小全新时间。  
  
```xml  
<configuration>  
  <system.net>  
    <requestCaching>  
      <defaultHttpCachePolicy  
        minimumFresh="0.06:00:00"  
        maximumAge="2.00:00:00"  
        maximumStale="0.04:00:00"
      />  
    </requestCaching>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Net.Cache>  
 <xref:System.Net.WebRequest>  
 <xref:System.Net.Cache.RequestCacheLevel>  
 [网络设置架构](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
