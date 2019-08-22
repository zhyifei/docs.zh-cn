---
title: <cryptoClasses> 元素
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/mscorlib/cryptographySettings/cryptoNameMapping/cryptoClasses
- http://schemas.microsoft.com/.NetConfiguration/v2.0#cryptoClasses
helpviewer_keywords:
- <cryptoClasses> element
- cryptoClasses element
ms.assetid: 290d5f96-946d-4f02-babb-1d31ec0b8295
ms.openlocfilehash: dbe46e0b36d247005f933c82ee83687886b283d1
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/21/2019
ms.locfileid: "69659658"
---
# <a name="cryptoclasses-element"></a>\<cryptoClasses > 元素
包含密码类的列表，这些类具有到 [\<nameEntry>](nameentry-element.md) 元素中的友好名称的映射。  
  
 \<configuration>  
\<mscorlib>  
\<cryptographySettings>  
\<cryptoNameMapping>  
\<cryptoClasses >  
  
## <a name="syntax"></a>语法  
  
```xml  
<cryptoClasses>   
</cryptoClasses>  
```  
  
## <a name="attributes-and-elements"></a>特性和元素  
 下列各节描述了特性、子元素和父元素。  
  
### <a name="attributes"></a>特性  
 无。  
  
### <a name="child-elements"></a>子元素  
  
|元素|描述|  
|-------------|-----------------|  
|[\<cryptoClass>](cryptoclass-element.md)|包含一个密码类，该类具有到 **\<nameEntry>** 元素中的友好名称的映射。|  
  
### <a name="parent-elements"></a>父元素  
  
|元素|描述|  
|-------------|-----------------|  
|`configuration`|公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。|  
|`cryptographySettings`|包含加密设置。|  
|`cryptoNameMapping`|包含类到友好名称的映射。|  
|`mscorlib`|`cryptographySettings`包含元素。|  
  
## <a name="example"></a>示例  
 下面的示例演示如何使用 **\<cryptoClass >** 元素来引用加密类并配置运行时。 然后, 你可以将字符串 "RSA" 传递给<xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType>方法, 并<xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A>使用方法返回`MyCryptoRSAClass`对象。  
  
```xml  
<configuration>  
   <mscorlib>  
      <cryptographySettings>  
         <cryptoNameMapping>  
            <cryptoClasses>  
               <cryptoClass   MyCryptoRSA="MyCryptoRSAClass, MyAssembly  
                  Culture=neutral, PublicKeyToken=a5d015c7d5a0b012,  
                  Version=1.0.0.0"/>  
               <!-- Other cryptography classes go here. -->  
            </cryptoClasses>  
            <nameEntry name="RSA" class="MyCryptoRSA"/>  
            <nameEntry name="System.Security.Cryptography.AsymmetricAlgorithm"  
                       class="MyCryptoRSA"/>  
             <!-- Mappings to other cryptography classes go here. -->  
         </cryptoNameMapping>  
      </cryptographySettings>  
   </mscorlib>  
</configuration>  
```  
  
## <a name="see-also"></a>请参阅

- <xref:System.Security.Cryptography>
- [配置文件架构](../index.md)
- [加密设置架构](index.md)
- [Cryptographic Services](../../../../../docs/standard/security/cryptographic-services.md)
- [System.Security.Cryptography.CryptoConfig.CreateFromName](Overload:System.Security.Cryptography.CryptoConfig.CreateFromName)
- [配置加密类](../../configure-cryptography-classes.md)
