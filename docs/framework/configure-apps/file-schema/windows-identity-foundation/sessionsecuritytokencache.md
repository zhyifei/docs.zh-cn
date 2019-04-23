---
title: <sessionSecurityTokenCache>
ms.date: 03/30/2017
ms.assetid: d43e676c-0153-485c-ab31-0257a2db7507
author: BrucePerlerMS
ms.openlocfilehash: 5c68fe618f965f364a3716c3bc65de5e165b12ec
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59207794"
---
# <a name="sessionsecuritytokencache"></a>\<sessionSecurityTokenCache>
使用的服务或安全令牌处理程序集合注册会话令牌的缓存。  
  
 \<system.identityModel>  
\<identityConfiguration>  
\<caches>  
\<sessionSecurityTokenCache>  
  
## <a name="syntax"></a>语法  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <caches>  
      <sessionSecurityTokenCache type=xs:string>  
      </sessionSecurityTokenCache>  
    </caches>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a>特性和元素  
 下列各节描述了特性、子元素和父元素。  
  
### <a name="attributes"></a>特性  
  
|特性|描述|  
|---------------|-----------------|  
|类型|从派生的类型的<xref:System.IdentityModel.Tokens.SessionSecurityTokenCache>类。|  
  
### <a name="child-elements"></a>子元素  
 None  
  
### <a name="parent-elements"></a>父元素  
  
|元素|描述|  
|-------------|-----------------|  
|[\<caches>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/caches.md)|注册服务或安全令牌处理程序集合使用的缓存。|  
  
## <a name="example"></a>示例  
 下面的 XML 演示的用于保存会话安全令牌的自定义缓存配置 (<xref:System.IdentityModel.Tokens.SessionSecurityToken>)。 配置来自`ClaimsAwareWebFarm`示例。 有关此示例的详细信息，请参阅[WIF 代码示例索引](../../../../../docs/framework/security/wif-code-sample-index.md)。  
  
```xml  
<caches>  
  <sessionSecurityTokenCache type="CacheLibrary.SharedSessionSecurityTokenCache, CacheLibrary">  
    <!--cacheServiceAddress points to the centralized session security token cache service running in the web farm.-->  
    <cacheServiceAddress url="http://localhost:4161/SessionSecurityTokenCacheService.svc" />  
  </sessionSecurityTokenCache>  
</caches>  
```  
  
## <a name="see-also"></a>请参阅

- <xref:System.IdentityModel.Tokens.SessionSecurityTokenCache>
