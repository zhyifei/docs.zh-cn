---
title: <x509SecurityTokenHandlerRequirement>
ms.date: 03/30/2017
ms.assetid: aca22c2c-5ae7-42af-9bbd-15c2524692ce
author: BrucePerlerMS
ms.openlocfilehash: 30ce69a35cfdd34e0dfea5c682347eb9187e04ed
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79152445"
---
# <a name="x509securitytokenhandlerrequirement"></a>\<x509 安全令牌处理程序要求>
为<xref:System.IdentityModel.Tokens.X509SecurityTokenHandler>类或派生类提供可选配置。  
  
[**\<配置>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<系统.身份模型>**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<身份配置>**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<安全令牌处理程序>**](securitytokenhandlers.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<添加>**](add.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<x509 安全令牌处理程序要求>**  
  
## <a name="syntax"></a>语法  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
      <add type="System.IdentityModel.Tokens.X509SecurityTokenHandler, System.IdentityModel">  
        <x509SecurityTokenHandlerRequirement>  
          mapToWindows=xs:boolean  
          certificateValidationMode="None||ChainTrust||PeerTrust||PeerOrChainTrust||Custom"  
          certificateValidator="Namespace.Class, Assembly"  
          revocationMode="NoCheck||Offline||Online"  
          trustedStoreLocation="CurrentUser||LocalMachine"  
        </x509SecurityTokenHandlerRequirement>  
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
|certificateValidationMode|指定<xref:System.ServiceModel.Security.X509CertificateValidationMode>要用于 X.509 证书的验证模式的值。 默认值为"对等或链信任"。|  
|地图到窗口|指定令牌处理程序是否应通过使用传入的 UPN 声明将验证令牌映射到 Windows 帐户。 默认值为“false”。|  
|revocationMode|指定<xref:System.Security.Cryptography.X509Certificates.X509RevocationMode>要用于 X.509 证书的吊销模式的值。 默认值为"联机"。|  
|trustedStoreLocation|指定<xref:System.Security.Cryptography.X509Certificates.StoreLocation>X.509 证书存储的值。 默认值为"本地计算机"。|  
|证书验证器|派生自<xref:System.IdentityModel.Selectors.X509CertificateValidator>的自定义类型。 如果`certificateValidationMode`属性为"自定义"，则此类型的实例用于颁发者证书验证。|  
  
### <a name="child-elements"></a>子元素  
 无  
  
### <a name="parent-elements"></a>父元素  
  
|元素|说明|  
|-------------|-----------------|  
|[\<添加>](add.md)|将指定的安全令牌处理程序添加到令牌处理程序集合。|  
  
## <a name="example"></a>示例  
  
```xml  
<add type="System.IdentityModel.Tokens.X509SecurityTokenHandler, System.IdentityModel">  
    <x509SecurityTokenHandlerRequirement mapToWindows="true"
                                         certificateValidationMode="PeerOrChainTrust"
                                         revocationMode="Online"
                                         trustedStoreLocation="LocalMachine" />  
</add>  
```
