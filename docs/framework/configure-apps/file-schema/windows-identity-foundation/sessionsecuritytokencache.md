---
title: <sessionSecurityTokenCache>
ms.date: 03/30/2017
ms.assetid: d43e676c-0153-485c-ab31-0257a2db7507
author: BrucePerlerMS
ms.openlocfilehash: 9be3bf980c3756678d26d8652271113d4daaba43
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69943714"
---
# <a name="sessionsecuritytokencache"></a>\<sessionSecurityTokenCache>
使用服务或安全标记处理程序集合为会话令牌注册缓存。  
  
 \<system.identityModel>  
\<identityConfiguration>  
\<缓存 >  
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
|type|派生自<xref:System.IdentityModel.Tokens.SessionSecurityTokenCache>类的类型。|  
  
### <a name="child-elements"></a>子元素  
 无  
  
### <a name="parent-elements"></a>父元素  
  
|元素|描述|  
|-------------|-----------------|  
|[\<caches>](caches.md)|注册服务使用的缓存或安全标记处理程序集合。|  
  
## <a name="example"></a>示例  
 下面的 XML 演示了用于保存会话安全令牌 (<xref:System.IdentityModel.Tokens.SessionSecurityToken>) 的自定义缓存配置。 此配置取自`ClaimsAwareWebFarm`示例。 有关此示例的详细信息, 请参阅[WIF 代码示例索引](../../../security/wif-code-sample-index.md)。  
  
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
