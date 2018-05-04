---
title: 将对象标识符映射到加密算法
ms.date: 03/30/2017
helpviewer_keywords:
- digital signatures
- identifiers, mapping object identifiers
- cryptographic algorithms
- mapping object identifiers
- cryptography, mapping object identifiers
ms.assetid: c9673f81-bf9e-47fd-bc6f-6bc1c1c4c15e
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 7801c55cf6b3334347788013d9052038d5d2f3ec
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
---
# <a name="mapping-object-identifiers-to-cryptography-algorithms"></a>将对象标识符映射到加密算法
数字签名确保数据不被篡改时它从一个程序发送到另一个。 通常通过将数学函数应用到的数据进行签名的哈希计算的数字签名。 在设置格式的哈希值进行签名，某些数字签名算法追加格式设置操作的一部分 ASN.1 对象标识符 (OID)。 OID 标识用于计算哈希算法。 你可以映射到对象标识符，以扩展加密机制，以便使用自定义算法的算法。 下面的示例演示如何将对象标识符映射到新的哈希算法。  
  
```xml  
<configuration>  
   <mscorlib>  
      <cryptographySettings>  
         <cryptoNameMapping>  
            <cryptoClasses>  
               <cryptoClass MyNewHash="MyNewHashClass, MyAssembly  
                  Culture='en', PublicKeyToken=a5d015c7d5a0b012,  
                  Version=1.0.0.0"/>  
            </cryptoClasses>  
            <nameEntry name="NewHash" class="MyNewHash"/>  
         </cryptoNameMapping>  
         <oidMap>  
            <oidEntry OID="1.3.14.33.42.46"  name="NewHash"/>  
         </oidMap>  
      </cryptographySettings>  
   </mscorlib>  
</configuration>  
```  
  
 [ \<OidEntry > 元素](../../../docs/framework/configure-apps/file-schema/cryptography/oidentry-element.md)包含两个属性。 **OID**属性是对象标识符编号。 **名称**属性为的值**名称**属性从[ \<nameEntry > 元素](../../../docs/framework/configure-apps/file-schema/cryptography/nameentry-element.md)。 对象标识符可以映射到的简单名称之前，必须是算法名称映射到的类。  
  
## <a name="see-also"></a>请参阅  
 [配置加密类](../../../docs/framework/configure-apps/configure-cryptography-classes.md)  
 [Cryptographic Services](../../../docs/standard/security/cryptographic-services.md)
