---
title: "&lt;oidEntry&gt;元素"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/mscorlib/cryptographySettings/oidMap/oidEntry
- http://schemas.microsoft.com/.NetConfiguration/v2.0#oidEntry
helpviewer_keywords:
- <oidEntry> element
- oidEntry element
ms.assetid: 22fb88b0-bf27-489c-9ca0-e65950ac136c
caps.latest.revision: "11"
author: mcleblanc
ms.author: markl
manager: markl
ms.workload: dotnet
ms.openlocfilehash: 2d6dfe38f8e632a31f7a20191678f1fff7fd88ee
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="ltoidentrygt-element"></a>&lt;oidEntry&gt;元素
将 ASN.1 对象标识符 (OID) 映射到友好名称。  
  
 \<configuration>  
\<mscorlib >  
\<g s >  
\<oidMap >  
\<oidEntry >  
  
## <a name="syntax"></a>语法  
  
```xml  
<oidEntry OID="object identifier number" name="friendly name" />  
```  
  
## <a name="attributes-and-elements"></a>特性和元素  
 下列各节描述了特性、子元素和父元素。  
  
### <a name="attributes"></a>特性  
  
|特性|描述|  
|---------------|-----------------|  
|**OID**|必需的特性。<br /><br /> 指定对应于由您的类实现的算法 ASN.1 OID。|  
|**name**|必需的特性。<br /><br /> 指定的值**名称**属性中[ \<nameEntry >](../../../../../docs/framework/configure-apps/file-schema/cryptography/nameentry-element.md)标记。|  
  
### <a name="child-elements"></a>子元素  
 无。  
  
### <a name="parent-elements"></a>父元素  
  
|元素|说明|  
|-------------|-----------------|  
|`configuration`|公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。|  
|`cryptographySettings`|包含加密设置。|  
|`mscorlib`|包含`cryptographySettings`元素。|  
|`oidMap`|包含 ASN.1 对象标识符 (OID) 映射到类。|  
  
## <a name="remarks"></a>备注  
 ASN.1 对象标识符标识中某些加密格式的算法。 将对象标识符映射到你希望确定的算法的友好名称。  
  
## <a name="example"></a>示例  
 下面的示例演示如何使用 **\<oidEntry >**元素将 ripemd-160 哈希算法的对象标识符映射到该哈希算法实现。  
  
```xml  
<configuration>  
   <mscorlib>  
      <cryptographySettings>  
         <cryptoNameMapping>  
            <cryptoClasses>  
               <cryptoClass   MyCrypto="MyCryptoClass, MyAssembly  
                  Culture=neutral, PublicKeyToken=a5d015c7d5a0b012,  
                  Version=1.0.0.0"/>  
            </cryptoClasses>  
            <nameEntry name="RIPEMD-160" class="MyCrypto"/>  
         </cryptoNameMapping>  
         <oidMap>  
            <oidEntry OID="1.3.36.3.2.1"   name="MyCryptoClass"/>  
         </oidMap>  
      </cryptographySettings>  
   </mscorlib>  
</configuration>  
```  
  
## <a name="see-also"></a>请参阅  
 [配置文件架构](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [加密设置架构](../../../../../docs/framework/configure-apps/file-schema/cryptography/index.md)  
 [加密服务](../../../../../docs/standard/security/cryptographic-services.md)  
 [配置加密类](../../../../../docs/framework/configure-apps/configure-cryptography-classes.md)  
 [将对象标识符映射到加密算法](../../../../../docs/framework/configure-apps/map-object-identifiers-to-cryptography-algorithms.md)
