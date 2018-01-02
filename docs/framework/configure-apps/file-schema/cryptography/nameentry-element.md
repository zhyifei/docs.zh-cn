---
title: "&lt;nameEntry&gt;元素"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#nameEntry
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/mscorlib/cryptographySettings/cryptoNameMapping/nameEntry
helpviewer_keywords:
- <nameEntry> element
- nameEntry element
ms.assetid: 7d7535e9-4b4a-4b8c-82e2-e40dff5a7821
caps.latest.revision: "14"
author: mcleblanc
ms.author: markl
manager: markl
ms.workload: dotnet
ms.openlocfilehash: 7c9a4b4532d98b7dfc2484dab1bb57e5a26fa392
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="ltnameentrygt-element"></a>&lt;nameEntry&gt;元素
将类名称映射到友好算法名称，允许一个类具有多个友好名称。  
  
 \<configuration>  
\<mscorlib >  
\<g s >  
\<cryptoNameMapping >  
\<nameEntry >  
  
## <a name="syntax"></a>语法  
  
```xml  
<nameEntry name="friendly name" Class="class name" />  
```  
  
## <a name="attributes-and-elements"></a>特性和元素  
 下列各节描述了特性、子元素和父元素。  
  
### <a name="attributes"></a>特性  
  
|特性|描述|  
|---------------|-----------------|  
|**name**|必需的特性。<br /><br /> 指定加密类实现的算法的友好名称。|  
|**类**|必需的特性。<br /><br /> 指定的值**名称**属性中[ \<cryptoClass >](../../../../../docs/framework/configure-apps/file-schema/cryptography/cryptoclass-element.md)元素。|  
  
### <a name="child-elements"></a>子元素  
 无。  
  
### <a name="parent-elements"></a>父元素  
  
|元素|说明|  
|-------------|-----------------|  
|`configuration`|公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。|  
|`system.web`|为 ASP.NET 配置节指定根元素。|  
  
## <a name="remarks"></a>备注  
 **名称**属性可以是之一中找到的抽象类的名称<xref:System.Security.Cryptography>命名空间。 当调用**创建**抽象加密类的方法，抽象类名称传递给<xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A>方法。 **CreateFromName**返回一个指示的类型的实例**类**属性。 如果**名称**特性是一个短名称，例如 RSA，你可以使用该名称，在调用时**CreateFromName**方法。  
  
## <a name="example"></a>示例  
 下面的示例演示如何使用 **\<nameEntry >**元素来引用密码类并配置运行时。 然后，你可以将字符串"RSA"传递到<xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType>方法并使用<xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A>方法以返回`MyCryptoRSAClass`对象。  
  
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
  
## <a name="see-also"></a>请参阅  
 [配置文件架构](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [加密设置架构](../../../../../docs/framework/configure-apps/file-schema/cryptography/index.md)  
 [加密服务](../../../../../docs/standard/security/cryptographic-services.md)  
 [配置加密类](../../../../../docs/framework/configure-apps/configure-cryptography-classes.md)
