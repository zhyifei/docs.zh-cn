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
ms.locfileid: "32756613"
---
# <a name="mapping-object-identifiers-to-cryptography-algorithms"></a><span data-ttu-id="16a6c-102">将对象标识符映射到加密算法</span><span class="sxs-lookup"><span data-stu-id="16a6c-102">Mapping Object Identifiers to Cryptography Algorithms</span></span>
<span data-ttu-id="16a6c-103">数字签名确保数据不被篡改时它从一个程序发送到另一个。</span><span class="sxs-lookup"><span data-stu-id="16a6c-103">Digital signatures ensure that data is not tampered with when it is sent from one program to another.</span></span> <span data-ttu-id="16a6c-104">通常通过将数学函数应用到的数据进行签名的哈希计算的数字签名。</span><span class="sxs-lookup"><span data-stu-id="16a6c-104">Typically the digital signature is computed by applying a mathematical function to the hash of the data to be signed.</span></span> <span data-ttu-id="16a6c-105">在设置格式的哈希值进行签名，某些数字签名算法追加格式设置操作的一部分 ASN.1 对象标识符 (OID)。</span><span class="sxs-lookup"><span data-stu-id="16a6c-105">When formatting a hash value to be signed, some digital signature algorithms append an ASN.1 Object Identifier (OID) as part of the formatting operation.</span></span> <span data-ttu-id="16a6c-106">OID 标识用于计算哈希算法。</span><span class="sxs-lookup"><span data-stu-id="16a6c-106">The OID identifies the algorithm that was used to compute the hash.</span></span> <span data-ttu-id="16a6c-107">你可以映射到对象标识符，以扩展加密机制，以便使用自定义算法的算法。</span><span class="sxs-lookup"><span data-stu-id="16a6c-107">You can map algorithms to object identifiers to extend the cryptography mechanism to use custom algorithms.</span></span> <span data-ttu-id="16a6c-108">下面的示例演示如何将对象标识符映射到新的哈希算法。</span><span class="sxs-lookup"><span data-stu-id="16a6c-108">The following example shows how to map an object identifier to a new hash algorithm.</span></span>  
  
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
  
 <span data-ttu-id="16a6c-109">[ \<OidEntry > 元素](../../../docs/framework/configure-apps/file-schema/cryptography/oidentry-element.md)包含两个属性。</span><span class="sxs-lookup"><span data-stu-id="16a6c-109">The [\<oidEntry> element](../../../docs/framework/configure-apps/file-schema/cryptography/oidentry-element.md) contains two attributes.</span></span> <span data-ttu-id="16a6c-110">**OID**属性是对象标识符编号。</span><span class="sxs-lookup"><span data-stu-id="16a6c-110">The **OID** attribute is the object identifier number.</span></span> <span data-ttu-id="16a6c-111">**名称**属性为的值**名称**属性从[ \<nameEntry > 元素](../../../docs/framework/configure-apps/file-schema/cryptography/nameentry-element.md)。</span><span class="sxs-lookup"><span data-stu-id="16a6c-111">The **name** attribute is the value of the **name** attribute from the [\<nameEntry> element](../../../docs/framework/configure-apps/file-schema/cryptography/nameentry-element.md).</span></span> <span data-ttu-id="16a6c-112">对象标识符可以映射到的简单名称之前，必须是算法名称映射到的类。</span><span class="sxs-lookup"><span data-stu-id="16a6c-112">There must be a mapping from an algorithm name to a class before an object identifier can be mapped to a simple name.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="16a6c-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="16a6c-113">See Also</span></span>  
 [<span data-ttu-id="16a6c-114">配置加密类</span><span class="sxs-lookup"><span data-stu-id="16a6c-114">Configuring Cryptography Classes</span></span>](../../../docs/framework/configure-apps/configure-cryptography-classes.md)  
 [<span data-ttu-id="16a6c-115">Cryptographic Services</span><span class="sxs-lookup"><span data-stu-id="16a6c-115">Cryptographic Services</span></span>](../../../docs/standard/security/cryptographic-services.md)
