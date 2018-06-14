---
title: '&lt;issuerNameRegistry&gt;'
ms.date: 03/30/2017
ms.assetid: 58b39d12-c953-40c4-88af-d7eb3343ca28
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: b695cc6d66e5b9e45bb6a5fd22d594bc22ea3cba
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
ms.locfileid: "32757523"
---
# <a name="ltissuernameregistrygt"></a>&lt;issuerNameRegistry&gt;
配置的颁发者名称注册表，由标记处理程序集合中的处理程序。  
  
 \<system.identityModel>  
\<identityConfiguration>  
\<securityTokenHandlers>  
\<securityTokenHandlerConfiguration >  
\<issuerNameRegistry >  
  
## <a name="syntax"></a>语法  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
      <securityTokenHandlerConfiguration>  
        <issuerNameRegistry type=xs:string>  
          <optionalCustomConfigurationElements />  
        </issuerNameRegistry>  
      </securityTokenHandlerConfiguration>  
    </securityTokenHandlers>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a>特性和元素  
 下列各节描述了特性、子元素和父元素。  
  
### <a name="attributes"></a>特性  
  
|特性|描述|  
|---------------|-----------------|  
|类型|派生自类型<xref:System.IdentityModel.Tokens.IssuerNameRegistry>类。 有关如何指定自定义的详细信息`type`，请参阅 [自定义类型引用]。|  
  
### <a name="child-elements"></a>子元素  
  
|元素|描述|  
|-------------|-----------------|  
|[\<trustedIssuers >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/trustedissuers.md)|当`type`属性指定基于配置的颁发者名称注册表 (<xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry>类)，则[ \<trustedIssuers >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/trustedissuers.md)必须指定元素。 [ \<TrustedIssuers >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/trustedissuers.md)元素可以`<add>`， `<clear>`，或`<remove>`元素作为子元素。|  
  
### <a name="parent-elements"></a>父元素  
  
|元素|描述|  
|-------------|-----------------|  
|[\<securityTokenHandlerConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md)|提供配置集合的安全令牌处理程序。|  
  
## <a name="remarks"></a>备注  
 颁发者的所有令牌使用颁发者名称注册表进行都验证。 这是一个对象，派生自<xref:System.IdentityModel.Tokens.IssuerNameRegistry>类。 颁发者名称注册表用于将验证由相应的颁发者的令牌的签名所需的加密材料的助记键名称相关联。 颁发者名称注册表维护受信任的信赖方 (RP) 应用程序的颁发者的列表。 使用指定的颁发者名称注册表类型`type`属性。 `<issuerNameRegistry>`元素可以拥有一个或多个提供指定类型的配置的子元素。 提供通过重写处理这些子元素的逻辑<xref:System.IdentityModel.Tokens.IssuerNameRegistry.LoadCustomConfiguration%2A>方法。  
  
 WIF 提供单个颁发者名称注册表类型超出了框中，<xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry>类。 此类使用一的组配置中指定的受信任颁发者证书。 它需要子配置元素，`<trustedIssuers>`下配置的受信任颁发者证书的集合。 受信任的证书指定使用 ASN.1 编码形式的证书指纹和添加或从集合中移除使用`<add>`， `<clear>`，或`<remove>`元素。  
  
 `<issuerNameRegistry>`元素表示由<xref:System.IdentityModel.Configuration.IssuerNameRegistryElement>类。  
  
> [!NOTE]
>  指定`<issuerNameRegistry>`元素的子元素作为[ \<identityConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md)元素已弃用，但仍支持向后兼容。 上的设置`<securityTokenHandlerConfiguration>`元素上会覆盖`<identityConfiguration>`元素。  
  
## <a name="example"></a>示例  
 下面的 XML 演示如何指定配置基于颁发者名称注册表。  
  
```xml  
<issuerNameRegistry type="System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089">  
  <trustedIssuers>  
    <add thumbprint="9B74CB … 1EF40D0" name="LocalSTS" />  
  </trustedIssuers>  
</issuerNameRegistry>  
```  
  
## <a name="see-also"></a>请参阅  
 <xref:System.IdentityModel.Tokens.IssuerNameRegistry>  
 <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry>
