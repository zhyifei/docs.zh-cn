---
title: <cryptoNameMapping> 元素
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#cryptoNameMapping
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/mscorlib/cryptographySettings/cryptoNameMapping
helpviewer_keywords:
- <cryptoNameMapping> element
- cryptoNameMapping element
ms.assetid: c59c9494-149b-4ce6-b38d-371f896ae85c
ms.openlocfilehash: d31c5cd52ffe0e2a6eb5784735e76436d216444b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79155214"
---
# <a name="cryptonamemapping-element"></a>\<加密名称映射>元素
包含类到友好名称的映射。  

[**\<配置>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<姆斯科利布>**](mscorlib-element-for-cryptography-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<密码设置>**](cryptographysettings-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<加密名称映射>**

## <a name="syntax"></a>语法  
  
```xml  
      <cryptoNameMapping>
</cryptoNameMapping>  
```  
  
## <a name="attributes-and-elements"></a>特性和元素  
 下列各节描述了特性、子元素和父元素。  
  
### <a name="attributes"></a>属性  
 无。  
  
### <a name="child-elements"></a>子元素  
  
|元素|说明|  
|-------------|-----------------|  
|`cryptoClasses`|包含具有映射到**\<nameentry>** 元素中的友好名称的加密类的列表。|  
|`nameEntry`|将类名称映射到友好算法名称，允许一个类具有多个友好名称。|  
  
### <a name="parent-elements"></a>父元素  
  
|元素|说明|  
|-------------|-----------------|  
|`configuration`|公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。|  
|`cryptographySettings`|包含加密设置。|  
|`cryptoNameMapping`|包含类到友好名称的映射。|  
|`mscorlib`|包含 \<cryptographySettings> 元素。|  
  
## <a name="example"></a>示例  
 下面的示例演示如何使用**\<加密NameMapping>** 元素来引用加密类并配置运行时。 然后，可以将字符串"RSA"传递给 方法，<xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType>并使用 方法<xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A>返回对象`MyCryptoRSAClass`。  
  
```xml  
<configuration>  
   <mscorlib>  
      <cryptographySettings>  
         <cryptoNameMapping>  
            <cryptoClasses>  
               <cryptoClass   MyCryptoRSA="MyCryptoRSAClass, MyAssembly  
                  Culture=neutral, PublicKeyToken=a5d015c7d5a0b012,  
                  Version=1.0.0.0"/>  
            </cryptoClasses>  
            <nameEntry name="RSA" class="MyCryptoRSA"/>  
            <nameEntry name="System.Security.Cryptography.AsymmetricAlgorithm"  
                       class="MyCryptoRSA"/>  
         </cryptoNameMapping>  
      </cryptographySettings>  
   </mscorlib>  
</configuration>  
```  
  
## <a name="see-also"></a>另请参阅

- [配置文件架构](../index.md)
- [密码设置架构](index.md)
- [加密服务](../../../../standard/security/cryptographic-services.md)
- [配置加密类](../../configure-cryptography-classes.md)
