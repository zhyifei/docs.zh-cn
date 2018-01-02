---
title: "将对象标识符映射到加密算法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- digital signatures
- identifiers, mapping object identifiers
- cryptographic algorithms
- mapping object identifiers
- cryptography, mapping object identifiers
ms.assetid: c9673f81-bf9e-47fd-bc6f-6bc1c1c4c15e
caps.latest.revision: "8"
author: mcleblanc
ms.author: markl
manager: markl
ms.workload: dotnet
ms.openlocfilehash: bcde53450e3656ec958898864bb7d7200a4b03e2
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="mapping-object-identifiers-to-cryptography-algorithms"></a><span data-ttu-id="dd2da-102">将对象标识符映射到加密算法</span><span class="sxs-lookup"><span data-stu-id="dd2da-102">Mapping Object Identifiers to Cryptography Algorithms</span></span>
<span data-ttu-id="dd2da-103">数字签名确保数据不被篡改时它从一个程序发送到另一个。</span><span class="sxs-lookup"><span data-stu-id="dd2da-103">Digital signatures ensure that data is not tampered with when it is sent from one program to another.</span></span> <span data-ttu-id="dd2da-104">通常通过将数学函数应用到的数据进行签名的哈希计算的数字签名。</span><span class="sxs-lookup"><span data-stu-id="dd2da-104">Typically the digital signature is computed by applying a mathematical function to the hash of the data to be signed.</span></span> <span data-ttu-id="dd2da-105">在设置格式的哈希值进行签名，某些数字签名算法追加格式设置操作的一部分 ASN.1 对象标识符 (OID)。</span><span class="sxs-lookup"><span data-stu-id="dd2da-105">When formatting a hash value to be signed, some digital signature algorithms append an ASN.1 Object Identifier (OID) as part of the formatting operation.</span></span> <span data-ttu-id="dd2da-106">OID 标识用于计算哈希算法。</span><span class="sxs-lookup"><span data-stu-id="dd2da-106">The OID identifies the algorithm that was used to compute the hash.</span></span> <span data-ttu-id="dd2da-107">你可以映射到对象标识符，以扩展加密机制，以便使用自定义算法的算法。</span><span class="sxs-lookup"><span data-stu-id="dd2da-107">You can map algorithms to object identifiers to extend the cryptography mechanism to use custom algorithms.</span></span> <span data-ttu-id="dd2da-108">下面的示例演示如何将对象标识符映射到新的哈希算法。</span><span class="sxs-lookup"><span data-stu-id="dd2da-108">The following example shows how to map an object identifier to a new hash algorithm.</span></span>  
  
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
  
 <span data-ttu-id="dd2da-109">[ \<OidEntry > 元素](../../../docs/framework/configure-apps/file-schema/cryptography/oidentry-element.md)包含两个属性。</span><span class="sxs-lookup"><span data-stu-id="dd2da-109">The [\<oidEntry> element](../../../docs/framework/configure-apps/file-schema/cryptography/oidentry-element.md) contains two attributes.</span></span> <span data-ttu-id="dd2da-110">**OID**属性是对象标识符编号。</span><span class="sxs-lookup"><span data-stu-id="dd2da-110">The **OID** attribute is the object identifier number.</span></span> <span data-ttu-id="dd2da-111">**名称**属性为的值**名称**属性从[ \<nameEntry > 元素](../../../docs/framework/configure-apps/file-schema/cryptography/nameentry-element.md)。</span><span class="sxs-lookup"><span data-stu-id="dd2da-111">The **name** attribute is the value of the **name** attribute from the [\<nameEntry> element](../../../docs/framework/configure-apps/file-schema/cryptography/nameentry-element.md).</span></span> <span data-ttu-id="dd2da-112">对象标识符可以映射到的简单名称之前，必须是算法名称映射到的类。</span><span class="sxs-lookup"><span data-stu-id="dd2da-112">There must be a mapping from an algorithm name to a class before an object identifier can be mapped to a simple name.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dd2da-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="dd2da-113">See Also</span></span>  
 [<span data-ttu-id="dd2da-114">配置加密类</span><span class="sxs-lookup"><span data-stu-id="dd2da-114">Configuring Cryptography Classes</span></span>](../../../docs/framework/configure-apps/configure-cryptography-classes.md)  
 [<span data-ttu-id="dd2da-115">Cryptographic Services</span><span class="sxs-lookup"><span data-stu-id="dd2da-115">Cryptographic Services</span></span>](../../../docs/standard/security/cryptographic-services.md)
