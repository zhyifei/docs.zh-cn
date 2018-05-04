---
title: '&lt;issuerTokenResolver&gt;'
ms.date: 03/30/2017
ms.assetid: f74392f6-3f5b-4880-bd8a-3a9130d31e65
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: 646833f277c3ef4675a835ca0af3daf647e01224
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
---
# <a name="ltissuertokenresolvergt"></a>&lt;issuerTokenResolver&gt;
注册的颁发者令牌解析程序由标记处理程序集合中的处理程序。 颁发者令牌解析程序用于解析在传入令牌和消息签名的令牌。  
  
 \<system.identityModel>  
\<identityConfiguration>  
\<securityTokenHandlers>  
\<securityTokenHandlerConfiguration >  
\<issuerTokenResolver >  
  
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
|类型|指定颁发者令牌解析程序的类型。 必须为<xref:System.IdentityModel.Tokens.IssuerTokenResolver>类或派生自类型<xref:System.IdentityModel.Tokens.IssuerTokenResolver>类。 必须的。|  
  
### <a name="child-elements"></a>子元素  
 无  
  
### <a name="parent-elements"></a>父元素  
  
|元素|描述|  
|-------------|-----------------|  
|[\<securityTokenHandlerConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md)|提供配置集合的安全令牌处理程序。|  
  
## <a name="remarks"></a>备注  
 颁发者令牌解析程序用于解析在传入令牌和消息签名的令牌。 它用于检索用于检查签名的加密材料。 必须指定`type`属性。 指定的类型可以是<xref:System.IdentityModel.Tokens.IssuerTokenResolver>或派生自的自定义类型<xref:System.IdentityModel.Tokens.IssuerTokenResolver>类。  
  
 某些令牌处理程序，可以在配置中指定颁发者的标记解析程序设置。 对于单个令牌处理程序的设置会覆盖上的安全令牌的处理程序集合的指定。  
  
> [!NOTE]
>  指定`<issuerTokenResolver>`元素的子元素作为[ \<identityConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md)元素已弃用，但仍支持向后兼容。 上的设置`<securityTokenHandlerConfiguration>`元素上会覆盖`<identityConfiguration>`元素。  
  
## <a name="example"></a>示例  
 下面的 XML 演示基于自定义类派生自颁发者令牌解析程序的配置<xref:System.IdentityModel.Tokens.IssuerTokenResolver>。 令牌解析程序维护的受众密钥对的自定义配置元素中初始化字典 (`<AddAudienceKeyPair>`) 为类定义。 类将重写<xref:System.IdentityModel.Selectors.SecurityTokenResolver.LoadCustomConfiguration%2A>方法来处理此元素。 重写显示在下面的示例;但是，它调用的方法不会显示为简洁起见中。 有关完整示例，请参阅`CustomToken`示例。  
  
```xml  
<issuerTokenResolver type="SimpleWebToken.CustomIssuerTokenResolver, SimpleWebToken">  
  <AddAudienceKeyPair  symmetricKey="wAVkldQiFypTQ+kdNdGWCYCHRcee8XmXxOvgmak8vSY=" audience="http://localhost:19851/" />  
</issuerTokenResolver>  
```  
  
## <a name="example"></a>示例  
  
```  
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
 <xref:System.IdentityModel.Tokens.IssuerTokenResolver>
