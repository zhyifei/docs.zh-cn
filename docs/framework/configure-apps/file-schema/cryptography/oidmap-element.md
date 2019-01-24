---
title: '&lt;oidMap&gt;元素'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#oidMap
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/mscorlib/cryptographySettings/oidMap
helpviewer_keywords:
- <oidMap> element
- oidMap element
ms.assetid: 7f0c2246-c070-4748-b96a-2f66a296c539
author: mcleblanc
ms.author: markl
ms.openlocfilehash: 19983e4d17ac2843385685a6b8b247d16f4cc081
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54700452"
---
# <a name="ltoidmapgt-element"></a><span data-ttu-id="e5dbd-102">&lt;oidMap&gt;元素</span><span class="sxs-lookup"><span data-stu-id="e5dbd-102">&lt;oidMap&gt; Element</span></span>
<span data-ttu-id="e5dbd-103">包含类的 ASN.1 对象标识符 (OID) 映射。</span><span class="sxs-lookup"><span data-stu-id="e5dbd-103">Contains ASN.1 object identifier (OID) mappings to classes.</span></span>  
  
 <span data-ttu-id="e5dbd-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="e5dbd-104">\<configuration></span></span>  
<span data-ttu-id="e5dbd-105">\<mscorlib></span><span class="sxs-lookup"><span data-stu-id="e5dbd-105">\<mscorlib></span></span>  
<span data-ttu-id="e5dbd-106">\<cryptographySettings></span><span class="sxs-lookup"><span data-stu-id="e5dbd-106">\<cryptographySettings></span></span>  
<span data-ttu-id="e5dbd-107">\<oidMap></span><span class="sxs-lookup"><span data-stu-id="e5dbd-107">\<oidMap></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e5dbd-108">语法</span><span class="sxs-lookup"><span data-stu-id="e5dbd-108">Syntax</span></span>  
  
```xml  
<oidMap>   
</oidMap>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e5dbd-109">特性和元素</span><span class="sxs-lookup"><span data-stu-id="e5dbd-109">Attributes and Elements</span></span>  
 <span data-ttu-id="e5dbd-110">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="e5dbd-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e5dbd-111">特性</span><span class="sxs-lookup"><span data-stu-id="e5dbd-111">Attributes</span></span>  
 <span data-ttu-id="e5dbd-112">无。</span><span class="sxs-lookup"><span data-stu-id="e5dbd-112">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="e5dbd-113">子元素</span><span class="sxs-lookup"><span data-stu-id="e5dbd-113">Child Elements</span></span>  
  
|<span data-ttu-id="e5dbd-114">元素</span><span class="sxs-lookup"><span data-stu-id="e5dbd-114">Element</span></span>|<span data-ttu-id="e5dbd-115">描述</span><span class="sxs-lookup"><span data-stu-id="e5dbd-115">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e5dbd-116">\<oidEntry></span><span class="sxs-lookup"><span data-stu-id="e5dbd-116">\<oidEntry></span></span>](../../../../../docs/framework/configure-apps/file-schema/cryptography/oidentry-element.md)|<span data-ttu-id="e5dbd-117">将 ASN.1 OID 映射到友好名称。</span><span class="sxs-lookup"><span data-stu-id="e5dbd-117">Maps an ASN.1 OID to a friendly name.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="e5dbd-118">父元素</span><span class="sxs-lookup"><span data-stu-id="e5dbd-118">Parent Elements</span></span>  
  
|<span data-ttu-id="e5dbd-119">元素</span><span class="sxs-lookup"><span data-stu-id="e5dbd-119">Element</span></span>|<span data-ttu-id="e5dbd-120">描述</span><span class="sxs-lookup"><span data-stu-id="e5dbd-120">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="e5dbd-121">公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。</span><span class="sxs-lookup"><span data-stu-id="e5dbd-121">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`cryptographySettings`|<span data-ttu-id="e5dbd-122">包含加密设置。</span><span class="sxs-lookup"><span data-stu-id="e5dbd-122">Contains cryptography settings.</span></span>|  
|`mscorlib`|<span data-ttu-id="e5dbd-123">包含`cryptographySettings`元素。</span><span class="sxs-lookup"><span data-stu-id="e5dbd-123">Contains the `cryptographySettings` element.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="e5dbd-124">示例</span><span class="sxs-lookup"><span data-stu-id="e5dbd-124">Example</span></span>  
 <span data-ttu-id="e5dbd-125">下面的示例演示如何使用 **\<oidMap >** 元素以包含该哈希算法的实现将 RIPEMD-160 哈希算法的 OID 的映射。</span><span class="sxs-lookup"><span data-stu-id="e5dbd-125">The following example shows how to use the **\<oidMap>** element to contain a mapping of an OID for the RIPEMD-160 hash algorithm to an implementation of that hash algorithm.</span></span>  
  
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
            <oidEntry OID="1.3.36.3.2.1"  name="MyCryptoClass"/>  
         </oidMap>  
      </cryptographySettings>  
   </mscorlib>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="e5dbd-126">请参阅</span><span class="sxs-lookup"><span data-stu-id="e5dbd-126">See also</span></span>
- [<span data-ttu-id="e5dbd-127">配置文件架构</span><span class="sxs-lookup"><span data-stu-id="e5dbd-127">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)
- [<span data-ttu-id="e5dbd-128">加密设置架构</span><span class="sxs-lookup"><span data-stu-id="e5dbd-128">Cryptography Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/cryptography/index.md)
- [<span data-ttu-id="e5dbd-129">Cryptographic Services</span><span class="sxs-lookup"><span data-stu-id="e5dbd-129">Cryptographic Services</span></span>](../../../../../docs/standard/security/cryptographic-services.md)
- [<span data-ttu-id="e5dbd-130">配置加密类</span><span class="sxs-lookup"><span data-stu-id="e5dbd-130">Configuring Cryptography Classes</span></span>](../../../../../docs/framework/configure-apps/configure-cryptography-classes.md)
- [<span data-ttu-id="e5dbd-131">将对象标识符映射到加密算法</span><span class="sxs-lookup"><span data-stu-id="e5dbd-131">Mapping Object Identifiers to Cryptography Algorithms</span></span>](../../../../../docs/framework/configure-apps/map-object-identifiers-to-cryptography-algorithms.md)
