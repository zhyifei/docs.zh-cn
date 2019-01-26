---
title: '&lt;cryptoClasses&gt;元素'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/mscorlib/cryptographySettings/cryptoNameMapping/cryptoClasses
- http://schemas.microsoft.com/.NetConfiguration/v2.0#cryptoClasses
helpviewer_keywords:
- <cryptoClasses> element
- cryptoClasses element
ms.assetid: 290d5f96-946d-4f02-babb-1d31ec0b8295
ms.openlocfilehash: 85e47830649b0088d1e1645d73c4fb924ba5591f
ms.sourcegitcommit: b351b0781a035616c90c68ccae6dd60aae66a953
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2019
ms.locfileid: "55083322"
---
# <a name="ltcryptoclassesgt-element"></a><span data-ttu-id="5cef9-102">&lt;cryptoClasses&gt;元素</span><span class="sxs-lookup"><span data-stu-id="5cef9-102">&lt;cryptoClasses&gt; Element</span></span>
<span data-ttu-id="5cef9-103">包含密码类的列表，这些类具有到 [\<nameEntry>](../../../../../docs/framework/configure-apps/file-schema/cryptography/nameentry-element.md) 元素中的友好名称的映射。</span><span class="sxs-lookup"><span data-stu-id="5cef9-103">Contains a list of cryptography classes that have a mapping to a friendly name in the [\<nameEntry>](../../../../../docs/framework/configure-apps/file-schema/cryptography/nameentry-element.md) element.</span></span>  
  
 <span data-ttu-id="5cef9-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="5cef9-104">\<configuration></span></span>  
<span data-ttu-id="5cef9-105">\<mscorlib></span><span class="sxs-lookup"><span data-stu-id="5cef9-105">\<mscorlib></span></span>  
<span data-ttu-id="5cef9-106">\<cryptographySettings></span><span class="sxs-lookup"><span data-stu-id="5cef9-106">\<cryptographySettings></span></span>  
<span data-ttu-id="5cef9-107">\<cryptoNameMapping></span><span class="sxs-lookup"><span data-stu-id="5cef9-107">\<cryptoNameMapping></span></span>  
<span data-ttu-id="5cef9-108">\<cryptoClasses></span><span class="sxs-lookup"><span data-stu-id="5cef9-108">\<cryptoClasses></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5cef9-109">语法</span><span class="sxs-lookup"><span data-stu-id="5cef9-109">Syntax</span></span>  
  
```xml  
<cryptoClasses>   
</cryptoClasses>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5cef9-110">特性和元素</span><span class="sxs-lookup"><span data-stu-id="5cef9-110">Attributes and Elements</span></span>  
 <span data-ttu-id="5cef9-111">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="5cef9-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5cef9-112">特性</span><span class="sxs-lookup"><span data-stu-id="5cef9-112">Attributes</span></span>  
 <span data-ttu-id="5cef9-113">无。</span><span class="sxs-lookup"><span data-stu-id="5cef9-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="5cef9-114">子元素</span><span class="sxs-lookup"><span data-stu-id="5cef9-114">Child Elements</span></span>  
  
|<span data-ttu-id="5cef9-115">元素</span><span class="sxs-lookup"><span data-stu-id="5cef9-115">Element</span></span>|<span data-ttu-id="5cef9-116">描述</span><span class="sxs-lookup"><span data-stu-id="5cef9-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5cef9-117">\<cryptoClass></span><span class="sxs-lookup"><span data-stu-id="5cef9-117">\<cryptoClass></span></span>](../../../../../docs/framework/configure-apps/file-schema/cryptography/cryptoclass-element.md)|<span data-ttu-id="5cef9-118">包含一个密码类，该类具有到 **\<nameEntry>** 元素中的友好名称的映射。</span><span class="sxs-lookup"><span data-stu-id="5cef9-118">Contains a cryptography class that has a mapping to a friendly name in the **\<nameEntry>** element.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="5cef9-119">父元素</span><span class="sxs-lookup"><span data-stu-id="5cef9-119">Parent Elements</span></span>  
  
|<span data-ttu-id="5cef9-120">元素</span><span class="sxs-lookup"><span data-stu-id="5cef9-120">Element</span></span>|<span data-ttu-id="5cef9-121">描述</span><span class="sxs-lookup"><span data-stu-id="5cef9-121">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="5cef9-122">公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。</span><span class="sxs-lookup"><span data-stu-id="5cef9-122">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`cryptographySettings`|<span data-ttu-id="5cef9-123">包含加密设置。</span><span class="sxs-lookup"><span data-stu-id="5cef9-123">Contains cryptography settings.</span></span>|  
|`cryptoNameMapping`|<span data-ttu-id="5cef9-124">包含类到友好名称的映射。</span><span class="sxs-lookup"><span data-stu-id="5cef9-124">Contains mappings of classes to friendly names.</span></span>|  
|`mscorlib`|<span data-ttu-id="5cef9-125">包含`cryptographySettings`元素。</span><span class="sxs-lookup"><span data-stu-id="5cef9-125">Contains the `cryptographySettings` element.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="5cef9-126">示例</span><span class="sxs-lookup"><span data-stu-id="5cef9-126">Example</span></span>  
 <span data-ttu-id="5cef9-127">以下示例演示如何使用 **\<cryptoClass >** 元素来引用一个密码类并配置运行时。</span><span class="sxs-lookup"><span data-stu-id="5cef9-127">The following example shows how use the **\<cryptoClass>** element to reference a cryptography class and to configure the runtime.</span></span> <span data-ttu-id="5cef9-128">然后可以将字符串"RSA"传递给<xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType>方法，并使用<xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A>方法以返回`MyCryptoRSAClass`对象。</span><span class="sxs-lookup"><span data-stu-id="5cef9-128">You can then pass the string "RSA" to the <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> method and use the <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> method to return a `MyCryptoRSAClass` object.</span></span>  
  
```xml  
<configuration>  
   <mscorlib>  
      <cryptographySettings>  
         <cryptoNameMapping>  
            <cryptoClasses>  
               <cryptoClass   MyCryptoRSA="MyCryptoRSAClass, MyAssembly  
                  Culture=neutral, PublicKeyToken=a5d015c7d5a0b012,  
                  Version=1.0.0.0"/>  
               <!-- Other cryptography classes go here. -->  
            </cryptoClasses>  
            <nameEntry name="RSA" class="MyCryptoRSA"/>  
            <nameEntry name="System.Security.Cryptography.AsymmetricAlgorithm"  
                       class="MyCryptoRSA"/>  
             <!-- Mappings to other cryptography classes go here. -->  
         </cryptoNameMapping>  
      </cryptographySettings>  
   </mscorlib>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="5cef9-129">请参阅</span><span class="sxs-lookup"><span data-stu-id="5cef9-129">See also</span></span>
- <xref:System.Security.Cryptography>
- [<span data-ttu-id="5cef9-130">配置文件架构</span><span class="sxs-lookup"><span data-stu-id="5cef9-130">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)
- [<span data-ttu-id="5cef9-131">加密设置架构</span><span class="sxs-lookup"><span data-stu-id="5cef9-131">Cryptography Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/cryptography/index.md)
- [<span data-ttu-id="5cef9-132">Cryptographic Services</span><span class="sxs-lookup"><span data-stu-id="5cef9-132">Cryptographic Services</span></span>](../../../../../docs/standard/security/cryptographic-services.md)
- [<span data-ttu-id="5cef9-133">System.Security.Cryptography.CryptoConfig.CreateFromName</span><span class="sxs-lookup"><span data-stu-id="5cef9-133">System.Security.Cryptography.CryptoConfig.CreateFromName</span></span>](Overload:System.Security.Cryptography.CryptoConfig.CreateFromName)
- [<span data-ttu-id="5cef9-134">配置加密类</span><span class="sxs-lookup"><span data-stu-id="5cef9-134">Configuring Cryptography Classes</span></span>](../../../../../docs/framework/configure-apps/configure-cryptography-classes.md)
