---
title: "&lt;requestCaching&gt;元素 （网络设置）"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#requestCaching
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/requestCaching
helpviewer_keywords:
- requestCaching element
- <requestCaching> element
ms.assetid: 9962a2fe-cbda-41a6-9377-571811eaea84
caps.latest.revision: "20"
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: f2737e67fe1fe1e33b2600f448b02321f6ce1888
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="ltrequestcachinggt-element-network-settings"></a>&lt;requestCaching&gt;元素 （网络设置）
控制网络请求的缓存机制。  
  
 \<configuration>  
\<system.net >  
\<requestCaching >  
  
## <a name="syntax"></a>语法  
  
```xml  
      <requestCaching>  
        isPrivateCache ="true|false"  
        disableAllCaching="true|false"  
        defaultPolicyLevel="BypassCache|Default|CacheOnly|CacheIfAvailable|Revalidate|Reload|NoCacheNoStore|Revalidate"  
        unspecifiedMaximumAge= "d.hh.mm.ss">  
          <defaultHttpCachePolicy> … </defaultHttpCachePolicy>  
          <defaultFtpCachePolicy> … </defaultFtpCachePolicy>  
      </requestCaching>
```  
  
## <a name="attributes-and-elements"></a>特性和元素  
 下列各节描述了特性、子元素和父元素。  
  
### <a name="attributes"></a>特性  
  
|特性|描述|  
|---------------|-----------------|  
|`isPrivateCache`|指定是否缓存之间提供隔离的不同用户的信息。 默认值为 `true`。 此值应为`false`中间层应用程序。|  
|`disableAllCaching`|指定缓存禁用对所有的 Web 响应，并且不能以编程方式重写。|  
|`defaultPolicyLevel`|<xref:System.Net.Cache.RequestCacheLevel> 枚举中的值之一。 默认值为 `BypassCache`。|  
|`unspecifiedMaximumAge`|指定在其后内容标记为过期的默认时间。|  
  
## <a name="policylevel-attribute"></a>policyLevel 属性  
  
|值|描述|  
|-----------|-----------------|  
|`Default`|如果资源是最新，内容的长度是准确的并且存在过期、 修改和内容长度属性将，返回缓存的资源。|  
|`BypassCache`|从服务器返回的资源。|  
|`CacheOnly`|如果内容长度存在并且匹配的项大小，则返回缓存的资源。|  
|`CacheIfAvailable`|如果提供了内容的长度，并且匹配的项大小;，返回缓存的资源否则为该资源从服务器下载，并返回到调用方。|  
|`Revalidate`|如果缓存的资源的时间戳是与服务器; 上的资源的时间戳相同，则返回缓存的资源否则为该资源在服务器上，存储在缓存中，下载，并返回到调用方。|  
|`Reload`|从服务器下载的资源、 将其存储在缓存中，和将资源返回给调用方。|  
|`NoCacheNoStore`|如果缓存的资源存在，则删除它。 资源从服务器下载，并返回到调用方。|  
|`Revalidate`|通过使用资源的缓存的副本，如果时间戳服务器; 上的资源的时间戳相同满足请求否则为资源在服务器上，提供给调用方，下载并存储在缓存中，|  
  
### <a name="child-elements"></a>子元素  
  
|元素|描述|  
|-------------|-----------------|  
|[defaultHttpCachePolicy](../../../../../docs/framework/configure-apps/file-schema/network/defaulthttpcachepolicy-element-network-settings.md)|可选元素。<br /><br /> 描述 HTTP 缓存功能是否处于活动状态并描述默认缓存策略。|  
|[\<defaultFtpCachePolicy > 元素 （网络设置）](../../../../../docs/framework/configure-apps/file-schema/network/defaultftpcachepolicy-element-network-settings.md)|可选元素。<br /><br /> 描述 FTP 缓存功能是否处于活动状态并描述默认缓存策略。|  
  
### <a name="parent-elements"></a>父元素  
  
|元素|描述|  
|-------------|-----------------|  
|[system.net](../../../../../docs/framework/configure-apps/file-schema/network/system-net-element-network-settings.md)|包含指定 .NET Framework 如何连接到网络的设置。|  
  
## <a name="example"></a>示例  
 下面的示例演示如何禁用所有缓存。  
  
```xml  
<configuration>  
  <system.net>  
    <requestCaching  
      disableAllCaching="true"  
    />  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a>另请参阅  
 <xref:System.Net.Cache?displayProperty=nameWithType>  
 [网络设置架构](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
