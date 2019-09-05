---
title: <caches>
ms.date: 03/30/2017
ms.assetid: 4651091b-3a20-40d8-b293-4408c0710143
author: BrucePerlerMS
ms.openlocfilehash: 80f435b52fd7657c5cd44538028d6080beffe0b5
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/04/2019
ms.locfileid: "70252159"
---
# <a name="caches"></a>\<缓存 >
注册用于会话令牌和令牌重播检测的缓存。  
  
[ **\<configuration>** ](../configuration-element.md)\
&nbsp;&nbsp;[ **\<System.identitymodel >** ](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[ **\<identityConfiguration >** ](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<缓存 >**  
  
## <a name="syntax"></a>语法  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <caches>  
    </caches>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a>特性和元素  
 下列各节描述了特性、子元素和父元素。  
  
### <a name="attributes"></a>特性  
 无  
  
### <a name="child-elements"></a>子元素  
  
|元素|描述|  
|-------------|-----------------|  
|[\<sessionSecurityTokenCache>](sessionsecuritytokencache.md)|使用服务或安全标记处理程序集合为会话令牌注册缓存。|  
|[\<tokenReplayCache>](tokenreplaycache.md)|向服务或安全标记处理程序集合注册令牌重播缓存。|  
  
### <a name="parent-elements"></a>父元素  
  
|元素|描述|  
|-------------|-----------------|  
|[\<identityConfiguration>](identityconfiguration.md)|指定服务级别标识设置。|  
|[\<securityTokenHandlerConfiguration>](securitytokenhandlerconfiguration.md)|为安全标记处理程序的集合提供配置。|  
  
## <a name="remarks"></a>备注  
 可以在元素`<identityConfiguration>`下的服务级别指定元素，或在`<securityTokenHandlerConfiguration>`元素下的安全令牌处理程序集合级别指定元素。`<caches>` 标记处理程序集合上的设置将重写服务上指定的设置。  
  
 元素由<xref:System.IdentityModel.Configuration.IdentityModelCachesElement>类表示。 `<caches>` 配置的缓存由<xref:System.IdentityModel.Configuration.IdentityModelCaches>类表示。  
  
## <a name="example"></a>示例  
 下面的 XML 演示了用于保存会话安全令牌（<xref:System.IdentityModel.Tokens.SessionSecurityToken>）的自定义缓存配置。 此配置取自`ClaimsAwareWebFarm`示例。  
  
```xml  
<caches>  
  <sessionSecurityTokenCache type="CacheLibrary.SharedSessionSecurityTokenCache, CacheLibrary">  
    <!--cacheServiceAddress points to the centralized session security token cache service running in the web farm.-->  
    <cacheServiceAddress url="http://localhost:4161/SessionSecurityTokenCacheService.svc" />  
  </sessionSecurityTokenCache>  
</caches>  
```
