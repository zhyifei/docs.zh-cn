---
title: '&lt;add&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4712a888-f154-4395-8887-ef14a88a6497
caps.latest.revision: "7"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload: dotnet
ms.openlocfilehash: d863a0fc2b575aceef12370a57f7f7807261cb5a
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/19/2018
---
# <a name="ltaddgt"></a>&lt;add&gt;
将指定的安全令牌处理程序添加到令牌处理程序集合中。  
  
 \<system.identityModel>  
\<identityConfiguration>  
\<securityTokenHandlers>  
\<add>  
  
## <a name="syntax"></a>语法  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
      <add type=xs:string>  
        <optionalConfigurationElement>  
        </optionalConfigurationElement>  
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
|类型|令牌处理程序中，要添加的 CLR 类型名称。 有关如何指定详细信息`type`属性，请参阅[自定义类型引用](http://msdn.microsoft.com/library/7286d2e3-c63d-49fd-abdc-ce2705f22c24)。|  
  
### <a name="child-elements"></a>子元素  
  
|元素|描述|  
|-------------|-----------------|  
|[\<samlSecurityTokenRequirement>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/samlsecuritytokenrequirement.md)|提供有关配置<xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler>类，<xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>类或这些类之一的派生的类。|  
|[\<sessionTokenRequirement>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/sessiontokenrequirement.md)|提供有关配置<xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler>类或派生的类。|  
|[\<userNameSecurityTokenHandlerRequirement>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/usernamesecuritytokenhandlerrequirement.md)|提供有关配置<xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler>类或派生的类。|  
|[\<x509SecurityTokenHandlerRequirement>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/x509securitytokenhandlerrequirement.md)|提供的可选配置<xref:System.IdentityModel.Tokens.X509SecurityTokenHandler>类或派生的类。|  
  
### <a name="parent-elements"></a>父元素  
  
|元素|描述|  
|-------------|-----------------|  
|[\<securityTokenHandlers>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlers.md)|指定与终结点注册的安全令牌处理程序的集合。|  
  
## <a name="remarks"></a>备注  
 `<add>`元素可能需要一个指定令牌处理程序的配置的单个子元素。 这是依赖于处理程序类是否通过引用`type`属性`<add>`元素为此功能提供支持。 提供此功能的令牌处理程序类必须公开的构造函数的<xref:System.Xml.XmlElement>对象。  
  
```  
public class CustomTokenHandler : Microsoft.IdentityModel.Tokens.SecurityTokenHandler  
{  
    public CustomTokenHandler( XmlElement customConfig )  
    {  
    }  
}  
```  
  
 多个内置的安全令牌处理程序类提供此功能。 这些类是<xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler>， <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>， <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler>， <xref:System.IdentityModel.Tokens.X509SecurityTokenHandler>，和<xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler>。  
  
> [!IMPORTANT]
>  令牌处理程序集合只能包含单个处理任何的程序给定的类型。 这意味着，例如，如果你想要添加的处理程序派生自<xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>类到集合中，你必须首先删除<xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>，则显示默认情况下，从集合。 你可以使用[\<删除 >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/remove.md)要从集合或使用移除单个处理程序元素[\<清除 >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/clear.md)要从集合中移除所有处理程序元素。  
  
 上一个处理程序指定的设置覆盖指定的下的标记处理程序集合的等效设置[ \<securityTokenHandlerConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md)元素和在服务级别下指定[ \<identityConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md)元素。  
  
## <a name="example"></a>示例  
 下面的 XML 演示如何使用`<add>`和`<remove>`元素使用的自定义会话令牌处理程序替换默认会话令牌处理程序。 XML 取自`ClaimsAwareWebFarm`示例。  
  
```xml  
<securityTokenHandlers>  
  <remove type="System.IdentityModel.Tokens.SessionSecurityTokenHandler, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
  <add type="System.IdentityModel.Services.Tokens.MachineKeySessionSecurityTokenHandler, System.IdentityModel.Services, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
</securityTokenHandlers>  
```
