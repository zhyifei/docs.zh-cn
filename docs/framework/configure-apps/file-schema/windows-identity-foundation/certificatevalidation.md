---
title: '&lt;certificateValidation&gt;'
ms.date: 03/30/2017
ms.assetid: 6c54c704-b55e-4631-88ff-4d4a5621554c
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: af4dc459da49b46d70276d3f4bcd5f94d2a91ffe
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
ms.locfileid: "32756054"
---
# <a name="ltcertificatevalidationgt"></a>&lt;certificateValidation&gt;
控制令牌处理程序用来验证证书的设置。 如果使用自己的验证程序配置特定的处理程序，则将重写这些设置。  
  
 \<system.identityModel>  
\<identityConfiguration>  
\<certificateValidation >  
  
## <a name="syntax"></a>语法  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <certificateValidation  
      certificateValidationMode="None||ChainTrust||PeerTrust||PeerOrChainTrust||Custom"  
      revocationMode="NoCheck||Offline||Online"  
      trustedStoreLocation="CurrentLocation||LocalMachine" >  
    </certificateValidation>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a>特性和元素  
 下列各节描述了特性、子元素和父元素。  
  
### <a name="attributes"></a>特性  
  
|特性|描述|  
|---------------|-----------------|  
|certificateValidationMode|<xref:System.ServiceModel.Security.X509CertificateValidationMode>值，该值指定要使用的 X.509 证书验证模式。 默认值为"PeerOrChainTrust"。 若要指定自定义验证程序，此特性设置为"Custom"并指定使用的验证程序[ \<certificateValidator >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/certificatevalidator.md)元素。 可选。|  
|revocationMode|<xref:System.Security.Cryptography.X509Certificates.X509RevocationMode>值，该值指定要使用的 X.509 证书的吊销模式。 默认值为"联机"。 可选。|  
|trustedStoreLocation|A<xref:System.Security.Cryptography.X509Certificates.StoreLocation>值，该值指定的 X.509 证书存储区。 默认值为"LocalMachine"。 可选。|  
  
### <a name="child-elements"></a>子元素  
  
|元素|描述|  
|-------------|-----------------|  
|[\<certificateValidator >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/certificatevalidator.md)|指定证书验证的自定义类型。 仅当使用此类型`certificateValidationMode`属性[ \<certificateValidation >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/certificatevalidation.md)元素设置为"Custom"。|  
  
### <a name="parent-elements"></a>父元素  
  
|元素|描述|  
|-------------|-----------------|  
|[\<identityConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md)|指定服务级别标识设置。|  
|[\<securityTokenHandlerConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md)|提供配置集合的安全令牌处理程序。|  
  
## <a name="remarks"></a>备注  
 A`<certificateValidation>`可以在服务级别下指定元素`<identityConfiguration>`元素或下位于安全令牌处理程序集合级别`<securityTokenHandlerConfiguration>`元素。 令牌处理程序集合上的设置会覆盖在服务上指定。 某些令牌处理程序，可以在配置中指定证书验证设置。 在服务级别和对安全令牌处理程序集合中，重写这些指定上各个标记处理程序的设置。  
  
## <a name="example"></a>示例  
  
```xml  
<certificateValidation certificateValidationMode="PeerOrChainTrust"  
                       revocationMode="Online"  
                       trustedStoreLocation="LocalMachine" />  
```
