---
title: <tokenReplayDetection>
ms.date: 03/30/2017
ms.assetid: ac3f588e-5f75-4275-b969-2d492ecc3b47
author: BrucePerlerMS
ms.openlocfilehash: 2e2159a73ca79fc362a8138eea95dbd173dafb11
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69944294"
---
# <a name="tokenreplaydetection"></a>\<tokenReplayDetection>
启用令牌重播检测并指定令牌的过期时间。  
  
 \<system.identityModel>  
\<identityConfiguration>  
\<tokenReplayDetection>  
  
## <a name="syntax"></a>语法  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <tokenReplayDetection enabled=xs:boolean expirationPeriod=TimeSpan>  
    </tokenReplayDetection>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="type"></a>类型  
 <xref:System.IdentityModel.Configuration.TokenReplayDetectionElement>  
  
## <a name="attributes-and-elements"></a>特性和元素  
 下列各节描述了特性、子元素和父元素。  
  
### <a name="attributes"></a>特性  
  
|特性|描述|  
|---------------|-----------------|  
|enabled|一个值, 该值指定是否启用令牌重放检测;"true" 表示启用令牌重播检测。|  
|expirationPeriod|一个<xref:System.TimeSpan> , 指定项目被视为过期并从缓存中删除之前的最大时间量。  有关如何指定<xref:System.TimeSpan>值的详细信息, 请参阅[Timespan 值](../windows-workflow-foundation/index.md)。|  
  
### <a name="child-elements"></a>子元素  
 无  
  
### <a name="parent-elements"></a>父元素  
  
|元素|描述|  
|-------------|-----------------|  
|[\<identityConfiguration>](identityconfiguration.md)|指定服务级别标识设置。|  
|[\<securityTokenHandlerConfiguration>](securitytokenhandlerconfiguration.md)|为安全标记处理程序的集合提供配置。|  
  
## <a name="remarks"></a>备注  
 可以在元素`<identityConfiguration>`下的服务级别指定元素, 或在`<securityTokenHandlerConfiguration>`元素下的安全令牌处理程序集合级别指定元素。`<tokenReplayDetection>` 标记处理程序集合上的设置将重写服务上指定的设置。  
  
 令牌重播缓存的类型由[ \<tokenReplayCache >](tokenreplaycache.md)元素指定。
