---
title: <samlSecurityTokenRequirement>
ms.date: 03/30/2017
ms.assetid: 09202d12-88d3-49cc-953b-703bcc1690eb
author: BrucePerlerMS
ms.openlocfilehash: b27f337189a7d0b66ffd38e032b5eb864e5094a1
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79152627"
---
# <a name="samlsecuritytokenrequirement"></a>\<samlSecurityToken 要求>
为这些<xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler>类之一的<xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>类、类或派生类提供配置。 由类<xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement>表示。  
  
[**\<配置>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<系统.身份模型>**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<身份配置>**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<安全令牌处理程序>**](securitytokenhandlers.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<添加>**](add.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<samlSecurityToken 要求>**  
  
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
  
### <a name="attributes"></a>属性  
  
|Attribute|说明|  
|---------------|-----------------|  
|地图到窗口|指定令牌处理程序是否应通过使用传入的 UPN 声明将验证令牌映射到 Windows 帐户。 默认值为“false”。|  
|颁发者证书重新调用模式|指定<xref:System.Security.Cryptography.X509Certificates.X509RevocationMode>要用于 X.509 证书的吊销模式的值。 默认值为"联机"。|  
|颁发者验证模式|指定<xref:System.ServiceModel.Security.X509CertificateValidationMode>要用于 X.509 证书的验证模式的值。 默认值为"对等或链信任"。|  
|颁发者证书信任存储位置|指定<xref:System.Security.Cryptography.X509Certificates.StoreLocation>X.509 证书存储的值。 默认值为"本地计算机"。|  
|颁发者证书验证器|派生自<xref:System.IdentityModel.Selectors.X509CertificateValidator>的自定义类型。 如果`issuerCertificateValidationMode`属性为"自定义"，则此类型的实例用于颁发者证书验证。|  
  
### <a name="child-elements"></a>子元素  
  
|元素|说明|  
|-------------|-----------------|  
|[\<名称 claimtype>](nameclaimtype.md)|设置指定<xref:System.Security.Principal.IIdentity.Name%2A>属性的声明类型。|  
|[\<角色声明类型>](roleclaimtype.md)|指定定义令牌处理程序<xref:System.Security.Claims.ClaimsIdentity><xref:System.IdentityModel.Tokens.SecurityTokenHandler.ValidateToken%2A>方法返回的对象集合中的角色类型声明的声明类型。|  
  
### <a name="parent-elements"></a>父元素  
  
|元素|说明|  
|-------------|-----------------|  
|[\<添加>](add.md)|将指定的安全令牌处理程序添加到令牌处理程序集合。|  
  
## <a name="remarks"></a>备注  
 元素`<samlSecurityTokenRequirement>`由<xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement>对象模型中的类表示，用于在`SamlSecurityTokenRequirement`<xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler>或 上配置属性。 <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>  
  
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
