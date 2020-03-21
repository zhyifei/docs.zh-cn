---
title: <issuerTokenResolver>
ms.date: 03/30/2017
ms.assetid: f74392f6-3f5b-4880-bd8a-3a9130d31e65
author: BrucePerlerMS
ms.openlocfilehash: 67d7e0aa5b6b05bfe8b17a1b1efebb1fbddbb0eb
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79152666"
---
# <a name="issuertokenresolver"></a>\<颁发者令牌解析器>
注册令牌处理程序集合中处理程序使用的颁发者令牌解析器。 颁发者令牌解析器用于解析传入令牌和消息上的签名令牌。  
  
[**\<配置>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<系统.身份模型>**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<身份配置>**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<安全令牌处理程序>**](securitytokenhandlers.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<安全令牌处理程序配置>**](securitytokenhandlerconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<颁发者令牌解析器>**  
  
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
  
### <a name="attributes"></a>属性  
  
|Attribute|说明|  
|---------------|-----------------|  
|type|指定颁发者令牌解析器的类型。 必须是类<xref:System.IdentityModel.Tokens.IssuerTokenResolver>或从<xref:System.IdentityModel.Tokens.IssuerTokenResolver>类派生的类型。 必需。|  
  
### <a name="child-elements"></a>子元素  
 无  
  
### <a name="parent-elements"></a>父元素  
  
|元素|说明|  
|-------------|-----------------|  
|[\<安全令牌处理程序配置>](securitytokenhandlerconfiguration.md)|为安全令牌处理程序的集合提供配置。|  
  
## <a name="remarks"></a>备注  
 颁发者令牌解析器用于解析传入令牌和消息上的签名令牌。 它用于检索用于检查签名的加密材料。 必须指定该`type`属性。 指定的类型可以是 或<xref:System.IdentityModel.Tokens.IssuerTokenResolver>派生自类的<xref:System.IdentityModel.Tokens.IssuerTokenResolver>自定义类型。  
  
 某些令牌处理程序允许您在配置中指定颁发者令牌解析器设置。 各个令牌处理程序上的设置将覆盖在安全令牌处理程序集合上指定的设置。  
  
> [!NOTE]
> 将`<issuerTokenResolver>`元素指定为[\<标识配置>](identityconfiguration.md)元素的子元素已被弃用，但仍支持向后兼容性。 元素上的`<securityTokenHandlerConfiguration>`设置将覆盖元素上的`<identityConfiguration>`设置。  
  
## <a name="example"></a>示例  
 以下 XML 显示基于 派生的<xref:System.IdentityModel.Tokens.IssuerTokenResolver>自定义类的颁发者令牌解析器的配置。 令牌解析器维护从为类定义的自定义配置元素 （`<AddAudienceKeyPair>`） 初始化的访问键对字典。 类重写处理<xref:System.IdentityModel.Selectors.SecurityTokenResolver.LoadCustomConfiguration%2A>此元素的方法。 重写显示在以下示例中;如下例中所示。但是，它调用的方法不显示为简洁。 有关完整示例，请参阅示例`CustomToken`。  
  
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
  
## <a name="see-also"></a>另请参阅

- <xref:System.IdentityModel.Tokens.IssuerTokenResolver>
