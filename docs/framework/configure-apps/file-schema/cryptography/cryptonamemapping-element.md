---
title: '&lt;cryptoNameMapping&gt;元素'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#cryptoNameMapping
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/mscorlib/cryptographySettings/cryptoNameMapping
helpviewer_keywords:
- <cryptoNameMapping> element
- cryptoNameMapping element
ms.assetid: c59c9494-149b-4ce6-b38d-371f896ae85c
author: mcleblanc
ms.author: markl
ms.openlocfilehash: ad1611701dca48244f3b2a93ecc3ea86363081ed
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/25/2018
ms.locfileid: "47170504"
---
# <a name="ltcryptonamemappinggt-element"></a><span data-ttu-id="a848c-102">&lt;cryptoNameMapping&gt;元素</span><span class="sxs-lookup"><span data-stu-id="a848c-102">&lt;cryptoNameMapping&gt; Element</span></span>
<span data-ttu-id="a848c-103">包含类到友好名称的映射。</span><span class="sxs-lookup"><span data-stu-id="a848c-103">Contains mappings of classes to friendly names.</span></span>  
  
 <span data-ttu-id="a848c-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="a848c-104">\<configuration></span></span>  
<span data-ttu-id="a848c-105">\<mscorlib ></span><span class="sxs-lookup"><span data-stu-id="a848c-105">\<mscorlib></span></span>  
<span data-ttu-id="a848c-106">\<cryptographySettings ></span><span class="sxs-lookup"><span data-stu-id="a848c-106">\<cryptographySettings></span></span>  
<span data-ttu-id="a848c-107">\<cryptoNameMapping ></span><span class="sxs-lookup"><span data-stu-id="a848c-107">\<cryptoNameMapping></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a848c-108">语法</span><span class="sxs-lookup"><span data-stu-id="a848c-108">Syntax</span></span>  
  
```xml  
      <cryptoNameMapping>   
</cryptoNameMapping>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a848c-109">特性和元素</span><span class="sxs-lookup"><span data-stu-id="a848c-109">Attributes and Elements</span></span>  
 <span data-ttu-id="a848c-110">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="a848c-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a848c-111">特性</span><span class="sxs-lookup"><span data-stu-id="a848c-111">Attributes</span></span>  
 <span data-ttu-id="a848c-112">无。</span><span class="sxs-lookup"><span data-stu-id="a848c-112">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="a848c-113">子元素</span><span class="sxs-lookup"><span data-stu-id="a848c-113">Child Elements</span></span>  
  
|<span data-ttu-id="a848c-114">元素</span><span class="sxs-lookup"><span data-stu-id="a848c-114">Element</span></span>|<span data-ttu-id="a848c-115">描述</span><span class="sxs-lookup"><span data-stu-id="a848c-115">Description</span></span>|  
|-------------|-----------------|  
|`cryptoClasses`|<span data-ttu-id="a848c-116">包含密码类的列表，这些类具有到 **\<nameEntry>** 元素中的友好名称的映射。</span><span class="sxs-lookup"><span data-stu-id="a848c-116">Contains a list of cryptography classes that have a mapping to a friendly name in the **\<nameEntry>** element.</span></span>|  
|`nameEntry`|<span data-ttu-id="a848c-117">将类名称映射到友好算法名称，允许一个类具有多个友好名称。</span><span class="sxs-lookup"><span data-stu-id="a848c-117">Maps a class name to a friendly algorithm name, which allows one class to have many friendly names.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="a848c-118">父元素</span><span class="sxs-lookup"><span data-stu-id="a848c-118">Parent Elements</span></span>  
  
|<span data-ttu-id="a848c-119">元素</span><span class="sxs-lookup"><span data-stu-id="a848c-119">Element</span></span>|<span data-ttu-id="a848c-120">描述</span><span class="sxs-lookup"><span data-stu-id="a848c-120">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="a848c-121">公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。</span><span class="sxs-lookup"><span data-stu-id="a848c-121">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`cryptographySettings`|<span data-ttu-id="a848c-122">包含加密设置。</span><span class="sxs-lookup"><span data-stu-id="a848c-122">Contains cryptography settings.</span></span>|  
|`cryptoNameMapping`|<span data-ttu-id="a848c-123">包含类到友好名称的映射。</span><span class="sxs-lookup"><span data-stu-id="a848c-123">Contains mappings of classes to friendly names.</span></span>|  
|`mscorlib`|<span data-ttu-id="a848c-124">包含\<cryptographySettings > 元素。</span><span class="sxs-lookup"><span data-stu-id="a848c-124">Contains the \<cryptographySettings> element.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="a848c-125">示例</span><span class="sxs-lookup"><span data-stu-id="a848c-125">Example</span></span>  
 <span data-ttu-id="a848c-126">下面的示例演示如何使用 **\<cryptoNameMapping >** 元素来引用一个密码类并配置运行时。</span><span class="sxs-lookup"><span data-stu-id="a848c-126">The following example shows how to use the **\<cryptoNameMapping>** element to reference a cryptography class and to configure the runtime.</span></span> <span data-ttu-id="a848c-127">然后可以将字符串"RSA"传递给<xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType>方法，并使用<xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A>方法以返回`MyCryptoRSAClass`对象。</span><span class="sxs-lookup"><span data-stu-id="a848c-127">You can then pass the string "RSA" to the <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> method and use the <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> method to return a `MyCryptoRSAClass` object.</span></span>  
  
```xml  
<configuration>  
   <mscorlib>  
      <cryptographySettings>  
         <cryptoNameMapping>  
            <cryptoClasses>  
               <cryptoClass   MyCryptoRSA="MyCryptoRSAClass, MyAssembly  
                  Culture=neutral, PublicKeyToken=a5d015c7d5a0b012,  
                  Version=1.0.0.0"/>  
            </cryptoClasses>  
            <nameEntry name="RSA" class="MyCryptoRSA"/>  
            <nameEntry name="System.Security.Cryptography.AsymmetricAlgorithm"  
                       class="MyCryptoRSA"/>  
         </cryptoNameMapping>  
      </cryptographySettings>  
   </mscorlib>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="a848c-128">请参阅</span><span class="sxs-lookup"><span data-stu-id="a848c-128">See Also</span></span>  
 [<span data-ttu-id="a848c-129">配置文件架构</span><span class="sxs-lookup"><span data-stu-id="a848c-129">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [<span data-ttu-id="a848c-130">加密设置架构</span><span class="sxs-lookup"><span data-stu-id="a848c-130">Cryptography Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/cryptography/index.md)  
 [<span data-ttu-id="a848c-131">加密服务</span><span class="sxs-lookup"><span data-stu-id="a848c-131">Cryptographic Services</span></span>](../../../../../docs/standard/security/cryptographic-services.md)  
 [<span data-ttu-id="a848c-132">配置加密类</span><span class="sxs-lookup"><span data-stu-id="a848c-132">Configuring Cryptography Classes</span></span>](../../../../../docs/framework/configure-apps/configure-cryptography-classes.md)
