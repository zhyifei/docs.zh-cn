---
title: <issuerTokenResolver>
ms.date: 03/30/2017
ms.assetid: f74392f6-3f5b-4880-bd8a-3a9130d31e65
author: BrucePerlerMS
ms.openlocfilehash: 451750a1facd9a886b53427a8d54580d1a939fa5
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/12/2019
ms.locfileid: "73968511"
---
# <a name="issuertokenresolver"></a>\<issuerTokenResolver >
注册由标记处理程序集合中的处理程序使用的颁发者令牌解析程序。 颁发者令牌解析器用于解析传入令牌和消息的签名令牌。  
  
[ **\<configuration>** ](../configuration-element.md)\
&nbsp;&nbsp;[ **\<system.identitymodel >** ](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[ **\<identityConfiguration >** ](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<securityTokenHandlers >** ](securitytokenhandlers.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<securityTokenHandlerConfiguration >** ](securitytokenhandlerconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<issuerTokenResolver >**  
  
## <a name="syntax"></a>语法  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
      <securityTokenHandlerConfiguration>  
        <issuerTokenResolver type=xs:string>  
        </issuerTokenResolver>  
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
|类型|指定颁发者令牌解析程序的类型。 必须是 <xref:System.IdentityModel.Tokens.IssuerTokenResolver> 类或派生自 <xref:System.IdentityModel.Tokens.IssuerTokenResolver> 类的类型。 必须的。|  
  
### <a name="child-elements"></a>子元素  
 None  
  
### <a name="parent-elements"></a>父元素  
  
|元素|描述|  
|-------------|-----------------|  
|[\<securityTokenHandlerConfiguration >](securitytokenhandlerconfiguration.md)|为安全标记处理程序的集合提供配置。|  
  
## <a name="remarks"></a>备注  
 颁发者令牌解析器用于解析传入令牌和消息的签名令牌。 它用于检索用于检查签名的加密材料。 您必须指定 `type` 特性。 指定的类型可以是 <xref:System.IdentityModel.Tokens.IssuerTokenResolver> 或从 <xref:System.IdentityModel.Tokens.IssuerTokenResolver> 类派生的自定义类型。  
  
 某些标记处理程序允许您在配置中指定颁发者令牌解析器设置。 各个标记处理程序上的设置将替代在安全令牌处理程序集合中指定的设置。  
  
> [!NOTE]
> 将 `<issuerTokenResolver>` 元素指定为[\<identityConfiguration >](identityconfiguration.md)元素的子元素已被弃用，但仍支持向后兼容。 `<securityTokenHandlerConfiguration>` 元素上的设置将覆盖 `<identityConfiguration>` 元素上的设置。  
  
## <a name="example"></a>示例  
 下面的 XML 演示颁发者令牌解析程序的配置，该解析程序基于从 <xref:System.IdentityModel.Tokens.IssuerTokenResolver>派生的自定义类。 令牌解析程序维护从为类定义的自定义配置元素（`<AddAudienceKeyPair>`）初始化的受众密钥对字典。 类将重写 <xref:System.IdentityModel.Selectors.SecurityTokenResolver.LoadCustomConfiguration%2A> 方法来处理此元素。 下面的示例显示了替代：但对于简洁起见，它调用的方法不会显示。 有关完整示例，请参阅 `CustomToken` 示例。  
  
```xml  
<issuerTokenResolver type="SimpleWebToken.CustomIssuerTokenResolver, SimpleWebToken">  
  <AddAudienceKeyPair  symmetricKey="wAVkldQiFypTQ+kdNdGWCYCHRcee8XmXxOvgmak8vSY=" audience="http://localhost:19851/" />  
</issuerTokenResolver>  
```  
  
## <a name="example"></a>示例
  
```csharp
public override void LoadCustomConfiguration(System.Xml.XmlNodeList nodelist)  
{  
    foreach (XmlNode node in nodelist)  
    {  
        XmlDictionaryReader rdr = XmlDictionaryReader.CreateDictionaryReader(new XmlTextReader(new StringReader(node.OuterXml)));  
        rdr.MoveToContent();  
  
        string symmetricKey = rdr.GetAttribute("symmetricKey");  
        string audience = rdr.GetAttribute("audience");  
  
        this.AddAudienceKeyPair(audience, symmetricKey);  
    }  
}  
``` 
  
## <a name="see-also"></a>请参阅

- <xref:System.IdentityModel.Tokens.IssuerTokenResolver>
