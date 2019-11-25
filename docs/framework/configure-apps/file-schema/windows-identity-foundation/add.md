---
title: <add>
ms.date: 03/30/2017
ms.assetid: 4712a888-f154-4395-8887-ef14a88a6497
author: BrucePerlerMS
ms.openlocfilehash: 83ba51cbbd5100bf7412f9914a270cac88f7faa1
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/12/2019
ms.locfileid: "73973804"
---
# <a name="add"></a>\<add>
将指定的安全令牌处理程序添加到令牌处理程序集合。  
  
[ **\<configuration>** ](../configuration-element.md)\
&nbsp;&nbsp;[ **\<system.identitymodel >** ](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[ **\<identityConfiguration >** ](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<securityTokenHandlers >** ](securitytokenhandlers.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<添加 >**  
  
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
|类型|要添加的令牌处理程序的 CLR 类型名称。 有关如何指定 `type` 属性的详细信息，请参阅[自定义类型引用](https://docs.microsoft.com/previous-versions/windows-identity-foundation/gg638728(v=msdn.10)#custom-type-references)。|  
  
### <a name="child-elements"></a>子元素  
  
|元素|描述|  
|-------------|-----------------|  
|[\<samlSecurityTokenRequirement >](samlsecuritytokenrequirement.md)|为 <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> 类、<xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> 类或其中任何一个类的派生类提供配置。|  
|[\<sessionTokenRequirement >](sessiontokenrequirement.md)|提供 <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler> 类或派生类的配置。|  
|[\<userNameSecurityTokenHandlerRequirement >](usernamesecuritytokenhandlerrequirement.md)|提供 <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler> 类或派生类的配置。|  
|[\<x509SecurityTokenHandlerRequirement >](x509securitytokenhandlerrequirement.md)|提供 <xref:System.IdentityModel.Tokens.X509SecurityTokenHandler> 类或派生类的可选配置。|  
  
### <a name="parent-elements"></a>父元素  
  
|元素|描述|  
|-------------|-----------------|  
|[\<securityTokenHandlers >](securitytokenhandlers.md)|指定注册到终结点的安全令牌处理程序的集合。|  
  
## <a name="remarks"></a>备注  
 `<add>` 元素可以采用单个子元素，该元素指定标记处理程序的配置。 这取决于通过 `<add>` 元素的 `type` 特性引用的处理程序类是否为此功能提供支持。 提供此功能的令牌处理程序类必须公开采用 <xref:System.Xml.XmlElement> 对象的构造函数。  

```csharp  
public class CustomTokenHandler : Microsoft.IdentityModel.Tokens.SecurityTokenHandler  
{  
    public CustomTokenHandler( XmlElement customConfig )  
    {  
    }  
}  
```  
  
 某些内置安全令牌处理程序类提供此功能。 这些类 <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler>、<xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>、<xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler>、<xref:System.IdentityModel.Tokens.X509SecurityTokenHandler>和 <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler>。  
  
> [!IMPORTANT]
> 标记处理程序集合只能包含任何给定类型的单个处理程序。 这意味着，例如，如果要将派生自 <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> 类的处理程序添加到集合中，则必须先从集合中删除默认存在的 <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>。 您可以使用[\<remove >](remove.md)元素从集合中删除单个处理程序，也可以使用[\<clear >](clear.md)元素从集合中移除所有处理程序。  
  
 在处理程序上指定的设置会重写[\<securityTokenHandlerConfiguration >](securitytokenhandlerconfiguration.md)元素下的标记处理程序集合中指定的等效设置，以及在[\<identityConfiguration >](identityconfiguration.md)元素下的服务级别指定的设置。  
  
## <a name="example"></a>示例  
 下面的 XML 演示了如何使用 `<add>` 和 `<remove>` 元素将默认会话标记处理程序替换为自定义会话标记处理程序。 XML 取自 `ClaimsAwareWebFarm` 示例。  
  
```xml  
<securityTokenHandlers>  
  <remove type="System.IdentityModel.Tokens.SessionSecurityTokenHandler, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
  <add type="System.IdentityModel.Services.Tokens.MachineKeySessionSecurityTokenHandler, System.IdentityModel.Services, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
</securityTokenHandlers>  
```
