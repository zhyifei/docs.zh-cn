---
title: "&lt;g s&gt;元素"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/mscorlib/cryptographySettings
- http://schemas.microsoft.com/.NetConfiguration/v2.0#cryptographySettings
helpviewer_keywords:
- cryptographySettings element
- <cryptographySettings> element
ms.assetid: 6201b7da-bcb7-49f7-b9f5-ba1fe05573b9
caps.latest.revision: "11"
author: mcleblanc
ms.author: markl
manager: markl
ms.workload: dotnet
ms.openlocfilehash: 73a4f362be1612658e6911b7e7ea7a6c3e670e01
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="ltcryptographysettingsgt-element"></a><span data-ttu-id="87dff-102">&lt;g s&gt;元素</span><span class="sxs-lookup"><span data-stu-id="87dff-102">&lt;cryptographySettings&gt; Element</span></span>
<span data-ttu-id="87dff-103">包含加密设置。</span><span class="sxs-lookup"><span data-stu-id="87dff-103">Contains cryptography settings.</span></span>  
  
 <span data-ttu-id="87dff-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="87dff-104">\<configuration></span></span>  
<span data-ttu-id="87dff-105">\<mscorlib ></span><span class="sxs-lookup"><span data-stu-id="87dff-105">\<mscorlib></span></span>  
<span data-ttu-id="87dff-106">\<g s ></span><span class="sxs-lookup"><span data-stu-id="87dff-106">\<cryptographySettings></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="87dff-107">语法</span><span class="sxs-lookup"><span data-stu-id="87dff-107">Syntax</span></span>  
  
```xml  
      <cryptographySettings>   
</cryptographySettings>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="87dff-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="87dff-108">Attributes and Elements</span></span>  
 <span data-ttu-id="87dff-109">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="87dff-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="87dff-110">特性</span><span class="sxs-lookup"><span data-stu-id="87dff-110">Attributes</span></span>  
 <span data-ttu-id="87dff-111">无。</span><span class="sxs-lookup"><span data-stu-id="87dff-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="87dff-112">子元素</span><span class="sxs-lookup"><span data-stu-id="87dff-112">Child Elements</span></span>  
  
|<span data-ttu-id="87dff-113">元素</span><span class="sxs-lookup"><span data-stu-id="87dff-113">Element</span></span>|<span data-ttu-id="87dff-114">描述</span><span class="sxs-lookup"><span data-stu-id="87dff-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="87dff-115">\<cryptoNameMapping ></span><span class="sxs-lookup"><span data-stu-id="87dff-115">\<cryptoNameMapping></span></span>](../../../../../docs/framework/configure-apps/file-schema/cryptography/cryptonamemapping-element.md)|<span data-ttu-id="87dff-116">包含类到友好名称的映射。</span><span class="sxs-lookup"><span data-stu-id="87dff-116">Contains mappings of classes to friendly names.</span></span>|  
|[<span data-ttu-id="87dff-117">\<oidMap ></span><span class="sxs-lookup"><span data-stu-id="87dff-117">\<oidMap></span></span>](../../../../../docs/framework/configure-apps/file-schema/cryptography/oidmap-element.md)|<span data-ttu-id="87dff-118">包含 ASN.1 对象标识符 (OID) 映射到类。</span><span class="sxs-lookup"><span data-stu-id="87dff-118">Contains ASN.1 object identifier (OID) mappings to classes.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="87dff-119">父元素</span><span class="sxs-lookup"><span data-stu-id="87dff-119">Parent Elements</span></span>  
  
|<span data-ttu-id="87dff-120">元素</span><span class="sxs-lookup"><span data-stu-id="87dff-120">Element</span></span>|<span data-ttu-id="87dff-121">说明</span><span class="sxs-lookup"><span data-stu-id="87dff-121">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="87dff-122">公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。</span><span class="sxs-lookup"><span data-stu-id="87dff-122">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`mscorlib`|<span data-ttu-id="87dff-123">包含`cryptographySettings`元素。</span><span class="sxs-lookup"><span data-stu-id="87dff-123">Contains the `cryptographySettings` element.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="87dff-124">示例</span><span class="sxs-lookup"><span data-stu-id="87dff-124">Example</span></span>  
 <span data-ttu-id="87dff-125">下面的示例演示如何使用 **\<g s >**元素以包含加密名称映射和 OID 映射。</span><span class="sxs-lookup"><span data-stu-id="87dff-125">The following example shows how use the **\<cryptographySettings>** element to contain cryptography name mappings and OID mappings.</span></span> <span data-ttu-id="87dff-126">此示例将配置为运行时，以便<xref:System.Security.Cryptography.HashAlgorithm.Create%2A?displayProperty=nameWithType>返回`MyHashClass`对象和`MyCryptoClass`类映射到对象标识符 1.3.36.2.1。</span><span class="sxs-lookup"><span data-stu-id="87dff-126">This example configures the runtime so that <xref:System.Security.Cryptography.HashAlgorithm.Create%2A?displayProperty=nameWithType> returns a `MyHashClass` object and the `MyCryptoClass` class maps to the object identifier 1.3.36.2.1.</span></span>  
  
```xml  
<configuration>  
   <mscorlib>  
      <cryptographySettings>  
         <cryptoNameMapping>  
            <cryptoClasses>  
               <cryptoClass   MyHash="MyHashClass, MyAssembly  
                  Culture=neutral, PublicKeyToken=a5d015c7d5a0b012,  
                  Version=1.0.0.0"/>  
               <cryptoClass   MyCrypto="MyCryptoClass, MyAssembly  
                  Culture=neutral, PublicKeyToken=a5d015c7d5a0b012,  
                  Version=1.0.0.0"/>  
            </cryptoClasses>  
            <nameEntry name="System.Security.Cryptography.HashAlgorithm"  
                       class="MyHash"/>  
         </cryptoNameMapping>  
         <oidMap>  
            <oidEntry OID="1.3.36.3.2.1"   name="MyCryptoClass"/>  
         </oidMap>  
      </cryptographySettings>  
   </mscorlib>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="87dff-127">请参阅</span><span class="sxs-lookup"><span data-stu-id="87dff-127">See Also</span></span>  
 [<span data-ttu-id="87dff-128">配置文件架构</span><span class="sxs-lookup"><span data-stu-id="87dff-128">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [<span data-ttu-id="87dff-129">加密设置架构</span><span class="sxs-lookup"><span data-stu-id="87dff-129">Cryptography Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/cryptography/index.md)  
 [<span data-ttu-id="87dff-130">加密服务</span><span class="sxs-lookup"><span data-stu-id="87dff-130">Cryptographic Services</span></span>](../../../../../docs/standard/security/cryptographic-services.md)
