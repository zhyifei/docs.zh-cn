---
title: "&lt;oidMap&gt;元素"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#oidMap
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/mscorlib/cryptographySettings/oidMap
helpviewer_keywords:
- <oidMap> element
- oidMap element
ms.assetid: 7f0c2246-c070-4748-b96a-2f66a296c539
caps.latest.revision: "9"
author: mcleblanc
ms.author: markl
manager: markl
ms.workload: dotnet
ms.openlocfilehash: 08f7eb8e4531d27586bede11bacf598e472b158f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="ltoidmapgt-element"></a><span data-ttu-id="a19f4-102">&lt;oidMap&gt;元素</span><span class="sxs-lookup"><span data-stu-id="a19f4-102">&lt;oidMap&gt; Element</span></span>
<span data-ttu-id="a19f4-103">包含 ASN.1 对象标识符 (OID) 映射到类。</span><span class="sxs-lookup"><span data-stu-id="a19f4-103">Contains ASN.1 object identifier (OID) mappings to classes.</span></span>  
  
 <span data-ttu-id="a19f4-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="a19f4-104">\<configuration></span></span>  
<span data-ttu-id="a19f4-105">\<mscorlib ></span><span class="sxs-lookup"><span data-stu-id="a19f4-105">\<mscorlib></span></span>  
<span data-ttu-id="a19f4-106">\<g s ></span><span class="sxs-lookup"><span data-stu-id="a19f4-106">\<cryptographySettings></span></span>  
<span data-ttu-id="a19f4-107">\<oidMap ></span><span class="sxs-lookup"><span data-stu-id="a19f4-107">\<oidMap></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a19f4-108">语法</span><span class="sxs-lookup"><span data-stu-id="a19f4-108">Syntax</span></span>  
  
```xml  
<oidMap>   
</oidMap>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a19f4-109">特性和元素</span><span class="sxs-lookup"><span data-stu-id="a19f4-109">Attributes and Elements</span></span>  
 <span data-ttu-id="a19f4-110">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="a19f4-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a19f4-111">特性</span><span class="sxs-lookup"><span data-stu-id="a19f4-111">Attributes</span></span>  
 <span data-ttu-id="a19f4-112">无。</span><span class="sxs-lookup"><span data-stu-id="a19f4-112">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="a19f4-113">子元素</span><span class="sxs-lookup"><span data-stu-id="a19f4-113">Child Elements</span></span>  
  
|<span data-ttu-id="a19f4-114">元素</span><span class="sxs-lookup"><span data-stu-id="a19f4-114">Element</span></span>|<span data-ttu-id="a19f4-115">描述</span><span class="sxs-lookup"><span data-stu-id="a19f4-115">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a19f4-116">\<oidEntry ></span><span class="sxs-lookup"><span data-stu-id="a19f4-116">\<oidEntry></span></span>](../../../../../docs/framework/configure-apps/file-schema/cryptography/oidentry-element.md)|<span data-ttu-id="a19f4-117">将 ASN.1 OID 映射到一个友好名称。</span><span class="sxs-lookup"><span data-stu-id="a19f4-117">Maps an ASN.1 OID to a friendly name.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="a19f4-118">父元素</span><span class="sxs-lookup"><span data-stu-id="a19f4-118">Parent Elements</span></span>  
  
|<span data-ttu-id="a19f4-119">元素</span><span class="sxs-lookup"><span data-stu-id="a19f4-119">Element</span></span>|<span data-ttu-id="a19f4-120">说明</span><span class="sxs-lookup"><span data-stu-id="a19f4-120">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="a19f4-121">公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。</span><span class="sxs-lookup"><span data-stu-id="a19f4-121">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`cryptographySettings`|<span data-ttu-id="a19f4-122">包含加密设置。</span><span class="sxs-lookup"><span data-stu-id="a19f4-122">Contains cryptography settings.</span></span>|  
|`mscorlib`|<span data-ttu-id="a19f4-123">包含`cryptographySettings`元素。</span><span class="sxs-lookup"><span data-stu-id="a19f4-123">Contains the `cryptographySettings` element.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="a19f4-124">示例</span><span class="sxs-lookup"><span data-stu-id="a19f4-124">Example</span></span>  
 <span data-ttu-id="a19f4-125">下面的示例演示如何使用 **\<oidMap >**元素以包含该哈希算法的实现的 ripemd-160 哈希算法的 oid 的映射。</span><span class="sxs-lookup"><span data-stu-id="a19f4-125">The following example shows how to use the **\<oidMap>** element to contain a mapping of an OID for the RIPEMD-160 hash algorithm to an implementation of that hash algorithm.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="a19f4-126">请参阅</span><span class="sxs-lookup"><span data-stu-id="a19f4-126">See Also</span></span>  
 [<span data-ttu-id="a19f4-127">配置文件架构</span><span class="sxs-lookup"><span data-stu-id="a19f4-127">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [<span data-ttu-id="a19f4-128">加密设置架构</span><span class="sxs-lookup"><span data-stu-id="a19f4-128">Cryptography Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/cryptography/index.md)  
 [<span data-ttu-id="a19f4-129">加密服务</span><span class="sxs-lookup"><span data-stu-id="a19f4-129">Cryptographic Services</span></span>](../../../../../docs/standard/security/cryptographic-services.md)  
 [<span data-ttu-id="a19f4-130">配置加密类</span><span class="sxs-lookup"><span data-stu-id="a19f4-130">Configuring Cryptography Classes</span></span>](../../../../../docs/framework/configure-apps/configure-cryptography-classes.md)  
 [<span data-ttu-id="a19f4-131">将对象标识符映射到加密算法</span><span class="sxs-lookup"><span data-stu-id="a19f4-131">Mapping Object Identifiers to Cryptography Algorithms</span></span>](../../../../../docs/framework/configure-apps/map-object-identifiers-to-cryptography-algorithms.md)
