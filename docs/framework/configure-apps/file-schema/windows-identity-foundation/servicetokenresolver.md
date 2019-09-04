---
title: <serviceTokenResolver>
ms.date: 03/30/2017
ms.assetid: 6e9001e1-e064-4f47-84b2-46225c177746
author: BrucePerlerMS
ms.openlocfilehash: 30a53c11b551623311f7ca3f957143fc702568a1
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/04/2019
ms.locfileid: "70251848"
---
# <a name="servicetokenresolver"></a>\<serviceTokenResolver>
注册令牌处理程序集合中的处理程序使用的服务令牌解析程序。 服务令牌解析器用于解析传入令牌和消息的加密令牌。  
  
[ **\<configuration>** ](../configuration-element.md)\
&nbsp;&nbsp;[ **\<System.identitymodel >** ](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[ **\<identityConfiguration >** ](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<securityTokenHandlers >** ](securitytokenhandlers.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<securityTokenHandlerConfiguration >** ](securitytokenhandlerconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<serviceTokenResolver >**  
  
## <a name="syntax"></a>语法  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
      <securityTokenHandlerConfiguration>  
        <serviceTokenResolver type=xs:string>  
        </serviceTokenResolver>  
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
|type|指定服务令牌解析程序的类型。 类型或派生<xref:System.IdentityModel.Selectors.SecurityTokenResolver>自类的类型。 <xref:System.IdentityModel.Selectors.SecurityTokenResolver> 有关如何指定`type`属性的详细信息，请参阅 [自定义类型引用]。 必需。|  
  
### <a name="child-elements"></a>子元素  
 无  
  
### <a name="parent-elements"></a>父元素  
  
|元素|描述|  
|-------------|-----------------|  
|[\<securityTokenHandlerConfiguration>](securitytokenhandlerconfiguration.md)|为安全标记处理程序的集合提供配置。|  
  
## <a name="remarks"></a>备注  
 服务令牌解析程序可用于解析传入令牌和消息的加密令牌。 它用于检索应该用于解密传入令牌的密钥。 您必须指定`type`属性。 指定的类型可以是<xref:System.IdentityModel.Selectors.SecurityTokenResolver>或<xref:System.IdentityModel.Selectors.SecurityTokenResolver>从类派生的自定义类型。  
  
 某些标记处理程序允许您在配置中指定服务令牌解析器设置。 各个标记处理程序上的设置将替代在安全令牌处理程序集合中指定的设置。  
  
> [!NOTE]
> 将元素指定为[ \<identityConfiguration >](identityconfiguration.md)元素的子元素已被弃用，但仍支持向后兼容。 `<serviceTokenResolver>` 元素上的`<securityTokenHandlerConfiguration>`设置将替代`<identityConfiguration>`元素上的设置。  
  
## <a name="example"></a>示例  
  
```xml  
<serviceTokenResolver type="MyNamespace.CustomTokenResolver, MyAssembly" />  
```
 