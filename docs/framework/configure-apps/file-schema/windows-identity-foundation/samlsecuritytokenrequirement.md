---
title: '&lt;samlSecurityTokenRequirement&gt;'
ms.date: 03/30/2017
ms.assetid: 09202d12-88d3-49cc-953b-703bcc1690eb
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: 86a9b9dcf0b9f5971e50ff7d1f1c37ca2e5f778a
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
---
# <a name="ltsamlsecuritytokenrequirementgt"></a>&lt;samlSecurityTokenRequirement&gt;
提供有关配置<xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler>类，<xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>类或这些类之一的派生的类。 由<xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement>类。  
  
 \<system.identityModel>  
\<identityConfiguration>  
\<securityTokenHandlers>  
\<add>  
\<samlSecurityTokenRequirement >  
  
## <a name="syntax"></a>语法  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
      <add>  
        <samlSecurityTokenRequirement   
            issuerCertificateValidationMode="None||ChainTrust||PeerTrust||PeerOrChainTrust||Custom"  
            issuerCertificateRevocationMode="NoCheck||Offline||Online"  
            issuerCertificateTrustedStoreLocation="CurrentLocation||LocalMachine"  
            issuerCertificateValidator="Namespace.Class Assembly"  
            mapToWindows=xs:boolean  
          <nameClaimType value=xs:string />  
          <roleClaimType value=xs:string />  
        </samlSecurityTokenRequirement>  
      </add>  
    </securityTokenHandlers>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a>特性和元素  
 下列各节描述了特性、子元素和父元素。  
  
### <a name="attributes"></a>特性  
  
|特性|描述|  
|---------------|-----------------|  
|mapToWindows|指定令牌处理程序是否应通过使用传入的 UPN 声明到 Windows 帐户映射验证令牌。 默认值为"false"。|  
|issuerCertificateRevocationMode|<xref:System.Security.Cryptography.X509Certificates.X509RevocationMode>值，该值指定要使用的 X.509 证书的吊销模式。 默认值为"联机"。|  
|issuerCertificateValidationMode|<xref:System.ServiceModel.Security.X509CertificateValidationMode>值，该值指定要使用的 X.509 证书验证模式。 默认值为"PeerOrChainTrust"。|  
|issuerCertificateTrustedStoreLocation|A<xref:System.Security.Cryptography.X509Certificates.StoreLocation>值，该值指定的 X.509 证书存储区。 默认值为"LocalMachine"。|  
|issuerCertificateValidator|派生自的自定义类型<xref:System.IdentityModel.Selectors.X509CertificateValidator>。 如果`issuerCertificateValidationMode`属性为"Custom"，此类型的实例将使用颁发者证书验证。|  
  
### <a name="child-elements"></a>子元素  
  
|元素|描述|  
|-------------|-----------------|  
|[\<nameClaimType >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/nameclaimtype.md)|设置指定的声明类型<xref:System.Security.Principal.IIdentity.Name%2A>属性。|  
|[\<roleClaimType >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/roleclaimtype.md)|指定的集合中定义的角色类型声明的声明类型<xref:System.Security.Claims.ClaimsIdentity>返回的对象<xref:System.IdentityModel.Tokens.SecurityTokenHandler.ValidateToken%2A>令牌处理程序方法。|  
  
### <a name="parent-elements"></a>父元素  
  
|元素|描述|  
|-------------|-----------------|  
|[\<add>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/add.md)|将指定的安全令牌处理程序添加到令牌处理程序集合中。|  
  
## <a name="remarks"></a>备注  
 `<samlSecurityTokenRequirement>`元素表示由<xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement>类中的对象模型，并用于配置`SamlSecurityTokenRequirement`属性<xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler>或<xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>。  
  
## <a name="example"></a>示例  
  
```xml  
<add type="System.IdentityModel.Tokens.SamlSecurityTokenHandler, System.IdentityModel">  
    <samlSecurityTokenRequirement issuerCertificateValidationMode="PeerOrChainTrust"  
                                  issuerCertificateRevocationMode="Online"  
                                  issuerCertificateTrustedStoreLocation="LocalMachine"  
                                  mapToWindows="false">  
  
        <nameClaimType value="http://schemas.xmlsoap.org/ws/2005/05/identity/claims/name" />  
        <roleClaimType value="schemas.microsoft.com/ws/2006/04/identity/claims/role" />  
    </samlSecurityTokenRequirement>  
</add>  
```
