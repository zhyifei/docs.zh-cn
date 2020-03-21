---
title: <serviceTokenResolver>
ms.date: 03/30/2017
ms.assetid: 6e9001e1-e064-4f47-84b2-46225c177746
author: BrucePerlerMS
ms.openlocfilehash: 0983380e553acfe246d6b987784d818b8ae85b17
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79152575"
---
# <a name="servicetokenresolver"></a>\<服务令牌解析器>
注册令牌处理程序集合中处理程序使用的服务令牌解析器。 服务令牌解析器用于解析传入令牌和消息上的加密令牌。  
  
[**\<配置>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<系统.身份模型>**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<身份配置>**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<安全令牌处理程序>**](securitytokenhandlers.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<安全令牌处理程序配置>**](securitytokenhandlerconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<服务令牌解析器>**  
  
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
  
### <a name="attributes"></a>属性  
  
|Attribute|说明|  
|---------------|-----------------|  
|type|指定服务令牌解析器的类型。 派生自<xref:System.IdentityModel.Selectors.SecurityTokenResolver><xref:System.IdentityModel.Selectors.SecurityTokenResolver>类的类型或类型。 有关如何指定属性的详细信息，`type`请参阅 [自定义类型引用]。 必需。|  
  
### <a name="child-elements"></a>子元素  
 无  
  
### <a name="parent-elements"></a>父元素  
  
|元素|说明|  
|-------------|-----------------|  
|[\<安全令牌处理程序配置>](securitytokenhandlerconfiguration.md)|为安全令牌处理程序的集合提供配置。|  
  
## <a name="remarks"></a>备注  
 服务令牌解析器可用于解析传入令牌和消息上的加密令牌。 它用于检索应用于解密传入令牌的密钥。 必须指定该`type`属性。 指定的类型可以是 或<xref:System.IdentityModel.Selectors.SecurityTokenResolver>派生自类的<xref:System.IdentityModel.Selectors.SecurityTokenResolver>自定义类型。  
  
 某些令牌处理程序允许您在配置中指定服务令牌解析器设置。 各个令牌处理程序上的设置将覆盖在安全令牌处理程序集合上指定的设置。  
  
> [!NOTE]
> 将`<serviceTokenResolver>`元素指定为[\<标识配置>](identityconfiguration.md)元素的子元素已被弃用，但仍支持向后兼容性。 元素上的`<securityTokenHandlerConfiguration>`设置将覆盖元素上的`<identityConfiguration>`设置。  
  
## <a name="example"></a>示例  
  
```xml  
<serviceTokenResolver type="MyNamespace.CustomTokenResolver, MyAssembly" />  
```
