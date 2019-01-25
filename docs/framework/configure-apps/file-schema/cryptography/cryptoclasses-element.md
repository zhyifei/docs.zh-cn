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
author: mcleblanc
ms.author: markl
ms.openlocfilehash: e3bc8fbb103d59b825e07cc52b155f1ea8061f31
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54649370"
---
# <a name="ltcryptoclassesgt-element"></a><span data-ttu-id="f2099-102">&lt;cryptoClasses&gt;元素</span><span class="sxs-lookup"><span data-stu-id="f2099-102">&lt;cryptoClasses&gt; Element</span></span>
<span data-ttu-id="f2099-103">包含密码类的列表，这些类具有到 [\<nameEntry>](../../../../../docs/framework/configure-apps/file-schema/cryptography/nameentry-element.md) 元素中的友好名称的映射。</span><span class="sxs-lookup"><span data-stu-id="f2099-103">Contains a list of cryptography classes that have a mapping to a friendly name in the [\<nameEntry>](../../../../../docs/framework/configure-apps/file-schema/cryptography/nameentry-element.md) element.</span></span>  
  
 <span data-ttu-id="f2099-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="f2099-104">\<configuration></span></span>  
<span data-ttu-id="f2099-105">\<mscorlib></span><span class="sxs-lookup"><span data-stu-id="f2099-105">\<mscorlib></span></span>  
<span data-ttu-id="f2099-106">\<cryptographySettings></span><span class="sxs-lookup"><span data-stu-id="f2099-106">\<cryptographySettings></span></span>  
<span data-ttu-id="f2099-107">\<cryptoNameMapping></span><span class="sxs-lookup"><span data-stu-id="f2099-107">\<cryptoNameMapping></span></span>  
<span data-ttu-id="f2099-108">\<cryptoClasses></span><span class="sxs-lookup"><span data-stu-id="f2099-108">\<cryptoClasses></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f2099-109">语法</span><span class="sxs-lookup"><span data-stu-id="f2099-109">Syntax</span></span>  
  
```xml  
<cryptoClasses>   
</cryptoClasses>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f2099-110">特性和元素</span><span class="sxs-lookup"><span data-stu-id="f2099-110">Attributes and Elements</span></span>  
 <span data-ttu-id="f2099-111">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="f2099-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f2099-112">特性</span><span class="sxs-lookup"><span data-stu-id="f2099-112">Attributes</span></span>  
 <span data-ttu-id="f2099-113">无。</span><span class="sxs-lookup"><span data-stu-id="f2099-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="f2099-114">子元素</span><span class="sxs-lookup"><span data-stu-id="f2099-114">Child Elements</span></span>  
  
|<span data-ttu-id="f2099-115">元素</span><span class="sxs-lookup"><span data-stu-id="f2099-115">Element</span></span>|<span data-ttu-id="f2099-116">描述</span><span class="sxs-lookup"><span data-stu-id="f2099-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f2099-117">\<cryptoClass></span><span class="sxs-lookup"><span data-stu-id="f2099-117">\<cryptoClass></span></span>](../../../../../docs/framework/configure-apps/file-schema/cryptography/cryptoclass-element.md)|<span data-ttu-id="f2099-118">包含一个密码类，该类具有到 **\<nameEntry>** 元素中的友好名称的映射。</span><span class="sxs-lookup"><span data-stu-id="f2099-118">Contains a cryptography class that has a mapping to a friendly name in the **\<nameEntry>** element.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="f2099-119">父元素</span><span class="sxs-lookup"><span data-stu-id="f2099-119">Parent Elements</span></span>  
  
|<span data-ttu-id="f2099-120">元素</span><span class="sxs-lookup"><span data-stu-id="f2099-120">Element</span></span>|<span data-ttu-id="f2099-121">描述</span><span class="sxs-lookup"><span data-stu-id="f2099-121">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="f2099-122">公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。</span><span class="sxs-lookup"><span data-stu-id="f2099-122">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`cryptographySettings`|<span data-ttu-id="f2099-123">包含加密设置。</span><span class="sxs-lookup"><span data-stu-id="f2099-123">Contains cryptography settings.</span></span>|  
|`cryptoNameMapping`|<span data-ttu-id="f2099-124">包含类到友好名称的映射。</span><span class="sxs-lookup"><span data-stu-id="f2099-124">Contains mappings of classes to friendly names.</span></span>|  
|`mscorlib`|<span data-ttu-id="f2099-125">包含`cryptographySettings`元素。</span><span class="sxs-lookup"><span data-stu-id="f2099-125">Contains the `cryptographySettings` element.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="f2099-126">示例</span><span class="sxs-lookup"><span data-stu-id="f2099-126">Example</span></span>  
 <span data-ttu-id="f2099-127">以下示例演示如何使用 **\<cryptoClass >** 元素来引用一个密码类并配置运行时。</span><span class="sxs-lookup"><span data-stu-id="f2099-127">The following example shows how use the **\<cryptoClass>** element to reference a cryptography class and to configure the runtime.</span></span> <span data-ttu-id="f2099-128">然后可以将字符串"RSA"传递给<xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType>方法，并使用<xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A>方法以返回`MyCryptoRSAClass`对象。</span><span class="sxs-lookup"><span data-stu-id="f2099-128">You can then pass the string "RSA" to the <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> method and use the <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> method to return a `MyCryptoRSAClass` object.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="f2099-129">请参阅</span><span class="sxs-lookup"><span data-stu-id="f2099-129">See also</span></span>
- <xref:System.Security.Cryptography>
- [<span data-ttu-id="f2099-130">配置文件架构</span><span class="sxs-lookup"><span data-stu-id="f2099-130">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)
- [<span data-ttu-id="f2099-131">加密设置架构</span><span class="sxs-lookup"><span data-stu-id="f2099-131">Cryptography Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/cryptography/index.md)
- [<span data-ttu-id="f2099-132">Cryptographic Services</span><span class="sxs-lookup"><span data-stu-id="f2099-132">Cryptographic Services</span></span>](../../../../../docs/standard/security/cryptographic-services.md)
- [<span data-ttu-id="f2099-133">System.Security.Cryptography.CryptoConfig.CreateFromName</span><span class="sxs-lookup"><span data-stu-id="f2099-133">System.Security.Cryptography.CryptoConfig.CreateFromName</span></span>](Overload:System.Security.Cryptography.CryptoConfig.CreateFromName)
- [<span data-ttu-id="f2099-134">配置加密类</span><span class="sxs-lookup"><span data-stu-id="f2099-134">Configuring Cryptography Classes</span></span>](../../../../../docs/framework/configure-apps/configure-cryptography-classes.md)
