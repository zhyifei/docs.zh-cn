---
title: <caches>
ms.date: 03/30/2017
ms.assetid: 4651091b-3a20-40d8-b293-4408c0710143
author: BrucePerlerMS
ms.openlocfilehash: 5ad75ae18772d6e7c724f2cbf40c1e3083d5c345
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69941967"
---
# <a name="caches"></a>\<缓存 >
注册用于会话令牌和令牌重播检测的缓存。  
  
 \<system.identityModel>  
\<identityConfiguration>  
\<缓存 >  
  
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
 可以在元素`<identityConfiguration>`下的服务级别指定元素, 或在`<securityTokenHandlerConfiguration>`元素下的安全令牌处理程序集合级别指定元素。`<caches>` 标记处理程序集合上的设置将重写服务上指定的设置。  
  
 元素由<xref:System.IdentityModel.Configuration.IdentityModelCachesElement>类表示。 `<caches>` 配置的缓存由<xref:System.IdentityModel.Configuration.IdentityModelCaches>类表示。  
  
## <a name="example"></a>示例  
 下面的 XML 演示了用于保存会话安全令牌 (<xref:System.IdentityModel.Tokens.SessionSecurityToken>) 的自定义缓存配置。 此配置取自`ClaimsAwareWebFarm`示例。  
  
```xml  
<caches>  
  <sessionSecurityTokenCache type="CacheLibrary.SharedSessionSecurityTokenCache, CacheLibrary">  
    <!--cacheServiceAddress points to the centralized session security token cache service running in the web farm.-->  
    <cacheServiceAddress url="http://localhost:4161/SessionSecurityTokenCacheService.svc" />  
  </sessionSecurityTokenCache>  
</caches>  
```
