---
title: <oidMap> 元素
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#oidMap
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/mscorlib/cryptographySettings/oidMap
helpviewer_keywords:
- <oidMap> element
- oidMap element
ms.assetid: 7f0c2246-c070-4748-b96a-2f66a296c539
ms.openlocfilehash: 80564c5895e08884f78a4ec7c955ecdb11126e35
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59146869"
---
# <a name="oidmap-element"></a><span data-ttu-id="9b0ea-102">\<oidMap > 元素</span><span class="sxs-lookup"><span data-stu-id="9b0ea-102">\<oidMap> Element</span></span>
<span data-ttu-id="9b0ea-103">包含类的 ASN.1 对象标识符 (OID) 映射。</span><span class="sxs-lookup"><span data-stu-id="9b0ea-103">Contains ASN.1 object identifier (OID) mappings to classes.</span></span>  
  
 <span data-ttu-id="9b0ea-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="9b0ea-104">\<configuration></span></span>  
<span data-ttu-id="9b0ea-105">\<mscorlib></span><span class="sxs-lookup"><span data-stu-id="9b0ea-105">\<mscorlib></span></span>  
<span data-ttu-id="9b0ea-106">\<cryptographySettings></span><span class="sxs-lookup"><span data-stu-id="9b0ea-106">\<cryptographySettings></span></span>  
<span data-ttu-id="9b0ea-107">\<oidMap></span><span class="sxs-lookup"><span data-stu-id="9b0ea-107">\<oidMap></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9b0ea-108">语法</span><span class="sxs-lookup"><span data-stu-id="9b0ea-108">Syntax</span></span>  
  
```xml  
<oidMap>   
</oidMap>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9b0ea-109">特性和元素</span><span class="sxs-lookup"><span data-stu-id="9b0ea-109">Attributes and Elements</span></span>  
 <span data-ttu-id="9b0ea-110">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="9b0ea-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9b0ea-111">特性</span><span class="sxs-lookup"><span data-stu-id="9b0ea-111">Attributes</span></span>  
 <span data-ttu-id="9b0ea-112">无。</span><span class="sxs-lookup"><span data-stu-id="9b0ea-112">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="9b0ea-113">子元素</span><span class="sxs-lookup"><span data-stu-id="9b0ea-113">Child Elements</span></span>  
  
|<span data-ttu-id="9b0ea-114">元素</span><span class="sxs-lookup"><span data-stu-id="9b0ea-114">Element</span></span>|<span data-ttu-id="9b0ea-115">描述</span><span class="sxs-lookup"><span data-stu-id="9b0ea-115">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9b0ea-116">\<oidEntry></span><span class="sxs-lookup"><span data-stu-id="9b0ea-116">\<oidEntry></span></span>](../../../../../docs/framework/configure-apps/file-schema/cryptography/oidentry-element.md)|<span data-ttu-id="9b0ea-117">将 ASN.1 OID 映射到友好名称。</span><span class="sxs-lookup"><span data-stu-id="9b0ea-117">Maps an ASN.1 OID to a friendly name.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="9b0ea-118">父元素</span><span class="sxs-lookup"><span data-stu-id="9b0ea-118">Parent Elements</span></span>  
  
|<span data-ttu-id="9b0ea-119">元素</span><span class="sxs-lookup"><span data-stu-id="9b0ea-119">Element</span></span>|<span data-ttu-id="9b0ea-120">描述</span><span class="sxs-lookup"><span data-stu-id="9b0ea-120">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="9b0ea-121">公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。</span><span class="sxs-lookup"><span data-stu-id="9b0ea-121">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`cryptographySettings`|<span data-ttu-id="9b0ea-122">包含加密设置。</span><span class="sxs-lookup"><span data-stu-id="9b0ea-122">Contains cryptography settings.</span></span>|  
|`mscorlib`|<span data-ttu-id="9b0ea-123">包含`cryptographySettings`元素。</span><span class="sxs-lookup"><span data-stu-id="9b0ea-123">Contains the `cryptographySettings` element.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="9b0ea-124">示例</span><span class="sxs-lookup"><span data-stu-id="9b0ea-124">Example</span></span>  
 <span data-ttu-id="9b0ea-125">下面的示例演示如何使用 **\<oidMap >** 元素以包含该哈希算法的实现将 RIPEMD-160 哈希算法的 OID 的映射。</span><span class="sxs-lookup"><span data-stu-id="9b0ea-125">The following example shows how to use the **\<oidMap>** element to contain a mapping of an OID for the RIPEMD-160 hash algorithm to an implementation of that hash algorithm.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="9b0ea-126">请参阅</span><span class="sxs-lookup"><span data-stu-id="9b0ea-126">See also</span></span>

- [<span data-ttu-id="9b0ea-127">配置文件架构</span><span class="sxs-lookup"><span data-stu-id="9b0ea-127">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)
- [<span data-ttu-id="9b0ea-128">加密设置架构</span><span class="sxs-lookup"><span data-stu-id="9b0ea-128">Cryptography Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/cryptography/index.md)
- [<span data-ttu-id="9b0ea-129">Cryptographic Services</span><span class="sxs-lookup"><span data-stu-id="9b0ea-129">Cryptographic Services</span></span>](../../../../../docs/standard/security/cryptographic-services.md)
- [<span data-ttu-id="9b0ea-130">配置加密类</span><span class="sxs-lookup"><span data-stu-id="9b0ea-130">Configuring Cryptography Classes</span></span>](../../../../../docs/framework/configure-apps/configure-cryptography-classes.md)
- [<span data-ttu-id="9b0ea-131">将对象标识符映射到加密算法</span><span class="sxs-lookup"><span data-stu-id="9b0ea-131">Mapping Object Identifiers to Cryptography Algorithms</span></span>](../../../../../docs/framework/configure-apps/map-object-identifiers-to-cryptography-algorithms.md)
