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
manager: markl
ms.openlocfilehash: db39d7de3566647b5171b71940c78a9a0ab6f5f1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33350217"
---
# <a name="ltoidmapgt-element"></a><span data-ttu-id="72ee5-102">&lt;oidMap&gt;元素</span><span class="sxs-lookup"><span data-stu-id="72ee5-102">&lt;oidMap&gt; Element</span></span>
<span data-ttu-id="72ee5-103">包含 ASN.1 对象标识符 (OID) 映射到类。</span><span class="sxs-lookup"><span data-stu-id="72ee5-103">Contains ASN.1 object identifier (OID) mappings to classes.</span></span>  
  
 <span data-ttu-id="72ee5-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="72ee5-104">\<configuration></span></span>  
<span data-ttu-id="72ee5-105">\<mscorlib ></span><span class="sxs-lookup"><span data-stu-id="72ee5-105">\<mscorlib></span></span>  
<span data-ttu-id="72ee5-106">\<g s ></span><span class="sxs-lookup"><span data-stu-id="72ee5-106">\<cryptographySettings></span></span>  
<span data-ttu-id="72ee5-107">\<oidMap ></span><span class="sxs-lookup"><span data-stu-id="72ee5-107">\<oidMap></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="72ee5-108">语法</span><span class="sxs-lookup"><span data-stu-id="72ee5-108">Syntax</span></span>  
  
```xml  
<oidMap>   
</oidMap>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="72ee5-109">特性和元素</span><span class="sxs-lookup"><span data-stu-id="72ee5-109">Attributes and Elements</span></span>  
 <span data-ttu-id="72ee5-110">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="72ee5-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="72ee5-111">特性</span><span class="sxs-lookup"><span data-stu-id="72ee5-111">Attributes</span></span>  
 <span data-ttu-id="72ee5-112">无。</span><span class="sxs-lookup"><span data-stu-id="72ee5-112">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="72ee5-113">子元素</span><span class="sxs-lookup"><span data-stu-id="72ee5-113">Child Elements</span></span>  
  
|<span data-ttu-id="72ee5-114">元素</span><span class="sxs-lookup"><span data-stu-id="72ee5-114">Element</span></span>|<span data-ttu-id="72ee5-115">描述</span><span class="sxs-lookup"><span data-stu-id="72ee5-115">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="72ee5-116">\<oidEntry ></span><span class="sxs-lookup"><span data-stu-id="72ee5-116">\<oidEntry></span></span>](../../../../../docs/framework/configure-apps/file-schema/cryptography/oidentry-element.md)|<span data-ttu-id="72ee5-117">将 ASN.1 OID 映射到一个友好名称。</span><span class="sxs-lookup"><span data-stu-id="72ee5-117">Maps an ASN.1 OID to a friendly name.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="72ee5-118">父元素</span><span class="sxs-lookup"><span data-stu-id="72ee5-118">Parent Elements</span></span>  
  
|<span data-ttu-id="72ee5-119">元素</span><span class="sxs-lookup"><span data-stu-id="72ee5-119">Element</span></span>|<span data-ttu-id="72ee5-120">描述</span><span class="sxs-lookup"><span data-stu-id="72ee5-120">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="72ee5-121">公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。</span><span class="sxs-lookup"><span data-stu-id="72ee5-121">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`cryptographySettings`|<span data-ttu-id="72ee5-122">包含加密设置。</span><span class="sxs-lookup"><span data-stu-id="72ee5-122">Contains cryptography settings.</span></span>|  
|`mscorlib`|<span data-ttu-id="72ee5-123">包含`cryptographySettings`元素。</span><span class="sxs-lookup"><span data-stu-id="72ee5-123">Contains the `cryptographySettings` element.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="72ee5-124">示例</span><span class="sxs-lookup"><span data-stu-id="72ee5-124">Example</span></span>  
 <span data-ttu-id="72ee5-125">下面的示例演示如何使用 **\<oidMap >** 元素以包含该哈希算法的实现的 ripemd-160 哈希算法的 oid 的映射。</span><span class="sxs-lookup"><span data-stu-id="72ee5-125">The following example shows how to use the **\<oidMap>** element to contain a mapping of an OID for the RIPEMD-160 hash algorithm to an implementation of that hash algorithm.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="72ee5-126">请参阅</span><span class="sxs-lookup"><span data-stu-id="72ee5-126">See Also</span></span>  
 [<span data-ttu-id="72ee5-127">配置文件架构</span><span class="sxs-lookup"><span data-stu-id="72ee5-127">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [<span data-ttu-id="72ee5-128">加密设置架构</span><span class="sxs-lookup"><span data-stu-id="72ee5-128">Cryptography Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/cryptography/index.md)  
 [<span data-ttu-id="72ee5-129">加密服务</span><span class="sxs-lookup"><span data-stu-id="72ee5-129">Cryptographic Services</span></span>](../../../../../docs/standard/security/cryptographic-services.md)  
 [<span data-ttu-id="72ee5-130">配置加密类</span><span class="sxs-lookup"><span data-stu-id="72ee5-130">Configuring Cryptography Classes</span></span>](../../../../../docs/framework/configure-apps/configure-cryptography-classes.md)  
 [<span data-ttu-id="72ee5-131">将对象标识符映射到加密算法</span><span class="sxs-lookup"><span data-stu-id="72ee5-131">Mapping Object Identifiers to Cryptography Algorithms</span></span>](../../../../../docs/framework/configure-apps/map-object-identifiers-to-cryptography-algorithms.md)
