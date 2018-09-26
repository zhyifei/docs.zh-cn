---
title: '&lt;cryptographySettings&gt;元素'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/mscorlib/cryptographySettings
- http://schemas.microsoft.com/.NetConfiguration/v2.0#cryptographySettings
helpviewer_keywords:
- cryptographySettings element
- <cryptographySettings> element
ms.assetid: 6201b7da-bcb7-49f7-b9f5-ba1fe05573b9
author: mcleblanc
ms.author: markl
ms.openlocfilehash: dc55acd7a698ef37d45e8a412db684c13a3b8b16
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/26/2018
ms.locfileid: "47203364"
---
# <a name="ltcryptographysettingsgt-element"></a><span data-ttu-id="6de1b-102">&lt;cryptographySettings&gt;元素</span><span class="sxs-lookup"><span data-stu-id="6de1b-102">&lt;cryptographySettings&gt; Element</span></span>
<span data-ttu-id="6de1b-103">包含加密设置。</span><span class="sxs-lookup"><span data-stu-id="6de1b-103">Contains cryptography settings.</span></span>  
  
 <span data-ttu-id="6de1b-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="6de1b-104">\<configuration></span></span>  
<span data-ttu-id="6de1b-105">\<mscorlib ></span><span class="sxs-lookup"><span data-stu-id="6de1b-105">\<mscorlib></span></span>  
<span data-ttu-id="6de1b-106">\<cryptographySettings ></span><span class="sxs-lookup"><span data-stu-id="6de1b-106">\<cryptographySettings></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6de1b-107">语法</span><span class="sxs-lookup"><span data-stu-id="6de1b-107">Syntax</span></span>  
  
```xml  
      <cryptographySettings>   
</cryptographySettings>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6de1b-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="6de1b-108">Attributes and Elements</span></span>  
 <span data-ttu-id="6de1b-109">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="6de1b-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6de1b-110">特性</span><span class="sxs-lookup"><span data-stu-id="6de1b-110">Attributes</span></span>  
 <span data-ttu-id="6de1b-111">无。</span><span class="sxs-lookup"><span data-stu-id="6de1b-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="6de1b-112">子元素</span><span class="sxs-lookup"><span data-stu-id="6de1b-112">Child Elements</span></span>  
  
|<span data-ttu-id="6de1b-113">元素</span><span class="sxs-lookup"><span data-stu-id="6de1b-113">Element</span></span>|<span data-ttu-id="6de1b-114">描述</span><span class="sxs-lookup"><span data-stu-id="6de1b-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6de1b-115">\<cryptoNameMapping ></span><span class="sxs-lookup"><span data-stu-id="6de1b-115">\<cryptoNameMapping></span></span>](../../../../../docs/framework/configure-apps/file-schema/cryptography/cryptonamemapping-element.md)|<span data-ttu-id="6de1b-116">包含类到友好名称的映射。</span><span class="sxs-lookup"><span data-stu-id="6de1b-116">Contains mappings of classes to friendly names.</span></span>|  
|[<span data-ttu-id="6de1b-117">\<oidMap ></span><span class="sxs-lookup"><span data-stu-id="6de1b-117">\<oidMap></span></span>](../../../../../docs/framework/configure-apps/file-schema/cryptography/oidmap-element.md)|<span data-ttu-id="6de1b-118">包含类的 ASN.1 对象标识符 (OID) 映射。</span><span class="sxs-lookup"><span data-stu-id="6de1b-118">Contains ASN.1 object identifier (OID) mappings to classes.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="6de1b-119">父元素</span><span class="sxs-lookup"><span data-stu-id="6de1b-119">Parent Elements</span></span>  
  
|<span data-ttu-id="6de1b-120">元素</span><span class="sxs-lookup"><span data-stu-id="6de1b-120">Element</span></span>|<span data-ttu-id="6de1b-121">描述</span><span class="sxs-lookup"><span data-stu-id="6de1b-121">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="6de1b-122">公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。</span><span class="sxs-lookup"><span data-stu-id="6de1b-122">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`mscorlib`|<span data-ttu-id="6de1b-123">包含`cryptographySettings`元素。</span><span class="sxs-lookup"><span data-stu-id="6de1b-123">Contains the `cryptographySettings` element.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="6de1b-124">示例</span><span class="sxs-lookup"><span data-stu-id="6de1b-124">Example</span></span>  
 <span data-ttu-id="6de1b-125">以下示例演示如何使用 **\<cryptographySettings >** 元素以包含加密名称映射和 OID 映射。</span><span class="sxs-lookup"><span data-stu-id="6de1b-125">The following example shows how use the **\<cryptographySettings>** element to contain cryptography name mappings and OID mappings.</span></span> <span data-ttu-id="6de1b-126">此示例将在运行时配置，以便<xref:System.Security.Cryptography.HashAlgorithm.Create%2A?displayProperty=nameWithType>将返回`MyHashClass`对象和`MyCryptoClass`类映射到的对象标识符 1.3.36.2.1。</span><span class="sxs-lookup"><span data-stu-id="6de1b-126">This example configures the runtime so that <xref:System.Security.Cryptography.HashAlgorithm.Create%2A?displayProperty=nameWithType> returns a `MyHashClass` object and the `MyCryptoClass` class maps to the object identifier 1.3.36.2.1.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="6de1b-127">请参阅</span><span class="sxs-lookup"><span data-stu-id="6de1b-127">See Also</span></span>  
 [<span data-ttu-id="6de1b-128">配置文件架构</span><span class="sxs-lookup"><span data-stu-id="6de1b-128">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [<span data-ttu-id="6de1b-129">加密设置架构</span><span class="sxs-lookup"><span data-stu-id="6de1b-129">Cryptography Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/cryptography/index.md)  
 [<span data-ttu-id="6de1b-130">加密服务</span><span class="sxs-lookup"><span data-stu-id="6de1b-130">Cryptographic Services</span></span>](../../../../../docs/standard/security/cryptographic-services.md)
