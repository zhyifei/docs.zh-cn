---
title: "&lt;cryptoClass&gt;元素"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/mscorlib/cryptographySettings/cryptoNameMapping/cryptoClasses/cryptoClass
- http://schemas.microsoft.com/.NetConfiguration/v2.0#cryptoClass
helpviewer_keywords:
- cryptoClass element
- <cryptoClass> element
ms.assetid: 03db52ef-010e-44ea-b6fd-b9c900ecad50
caps.latest.revision: "14"
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 448e2c83f6897fd876bb79dfb781bcf4ddd2252b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="ltcryptoclassgt-element"></a><span data-ttu-id="17758-102">&lt;cryptoClass&gt;元素</span><span class="sxs-lookup"><span data-stu-id="17758-102">&lt;cryptoClass&gt; Element</span></span>
<span data-ttu-id="17758-103">包含一个密码类，该类具有到 [\<nameEntry>](../../../../../docs/framework/configure-apps/file-schema/cryptography/nameentry-element.md) 元素中的友好名称的映射。</span><span class="sxs-lookup"><span data-stu-id="17758-103">Contains a cryptography class that has a mapping to a friendly name in the [\<nameEntry>](../../../../../docs/framework/configure-apps/file-schema/cryptography/nameentry-element.md) element.</span></span>  
  
 <span data-ttu-id="17758-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="17758-104">\<configuration></span></span>  
<span data-ttu-id="17758-105">\<mscorlib ></span><span class="sxs-lookup"><span data-stu-id="17758-105">\<mscorlib></span></span>  
<span data-ttu-id="17758-106">\<g s ></span><span class="sxs-lookup"><span data-stu-id="17758-106">\<cryptographySettings></span></span>  
<span data-ttu-id="17758-107">\<cryptoNameMapping ></span><span class="sxs-lookup"><span data-stu-id="17758-107">\<cryptoNameMapping></span></span>  
<span data-ttu-id="17758-108">\<cryptoClasses ></span><span class="sxs-lookup"><span data-stu-id="17758-108">\<cryptoClasses></span></span>  
<span data-ttu-id="17758-109">\<cryptoClass ></span><span class="sxs-lookup"><span data-stu-id="17758-109">\<cryptoClass></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="17758-110">语法</span><span class="sxs-lookup"><span data-stu-id="17758-110">Syntax</span></span>  
  
```xml  
<cryptoClass customClassName="fully qualified type name" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="17758-111">特性和元素</span><span class="sxs-lookup"><span data-stu-id="17758-111">Attributes and Elements</span></span>  
 <span data-ttu-id="17758-112">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="17758-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="17758-113">特性</span><span class="sxs-lookup"><span data-stu-id="17758-113">Attributes</span></span>  
  
|<span data-ttu-id="17758-114">特性</span><span class="sxs-lookup"><span data-stu-id="17758-114">Attribute</span></span>|<span data-ttu-id="17758-115">描述</span><span class="sxs-lookup"><span data-stu-id="17758-115">Description</span></span>|  
|---------------|-----------------|  
|`customClassName`|<span data-ttu-id="17758-116">必需的特性。</span><span class="sxs-lookup"><span data-stu-id="17758-116">Required attribute.</span></span><br /><br /> <span data-ttu-id="17758-117">包含加密类的信息。</span><span class="sxs-lookup"><span data-stu-id="17758-117">Contains the information for the cryptography class.</span></span> <span data-ttu-id="17758-118">使用此属性以提供您的类的短名称。</span><span class="sxs-lookup"><span data-stu-id="17758-118">Use this attribute to provide a short name for your class.</span></span> <span data-ttu-id="17758-119">必须指定满足要求中指定的字符串[指定完全限定的类型名称](../../../../../docs/framework/reflection-and-codedom/specifying-fully-qualified-type-names.md)。</span><span class="sxs-lookup"><span data-stu-id="17758-119">You must specify a string that meets the requirements specified in [Specifying Fully Qualified Type Names](../../../../../docs/framework/reflection-and-codedom/specifying-fully-qualified-type-names.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="17758-120">子元素</span><span class="sxs-lookup"><span data-stu-id="17758-120">Child Elements</span></span>  
 <span data-ttu-id="17758-121">无。</span><span class="sxs-lookup"><span data-stu-id="17758-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="17758-122">父元素</span><span class="sxs-lookup"><span data-stu-id="17758-122">Parent Elements</span></span>  
  
|<span data-ttu-id="17758-123">元素</span><span class="sxs-lookup"><span data-stu-id="17758-123">Element</span></span>|<span data-ttu-id="17758-124">描述</span><span class="sxs-lookup"><span data-stu-id="17758-124">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="17758-125">公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。</span><span class="sxs-lookup"><span data-stu-id="17758-125">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`cryptoClasses`|<span data-ttu-id="17758-126">包含密码类的列表，这些类具有到 [\<nameEntry>](../../../../../docs/framework/configure-apps/file-schema/cryptography/nameentry-element.md) 元素中的友好名称的映射。</span><span class="sxs-lookup"><span data-stu-id="17758-126">Contains a list of cryptography classes that have a mapping to a friendly name in the [\<nameEntry>](../../../../../docs/framework/configure-apps/file-schema/cryptography/nameentry-element.md) element.</span></span>|  
|`cryptographySettings`|<span data-ttu-id="17758-127">包含加密设置。</span><span class="sxs-lookup"><span data-stu-id="17758-127">Contains cryptography settings.</span></span>|  
|`cryptoNameMapping`|<span data-ttu-id="17758-128">包含类到友好名称的映射。</span><span class="sxs-lookup"><span data-stu-id="17758-128">Contains mappings of classes to friendly names.</span></span>|  
|`mscorlib`|<span data-ttu-id="17758-129">包含 [\<cryptographySettings>](../../../../../docs/framework/configure-apps/file-schema/cryptography/cryptographysettings-element.md) 元素。</span><span class="sxs-lookup"><span data-stu-id="17758-129">Contains the [\<cryptographySettings>](../../../../../docs/framework/configure-apps/file-schema/cryptography/cryptographysettings-element.md) element.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="17758-130">示例</span><span class="sxs-lookup"><span data-stu-id="17758-130">Example</span></span>  
 <span data-ttu-id="17758-131">下面的示例演示如何使用 **\<cryptoClass >**元素来引用密码类并配置运行时。</span><span class="sxs-lookup"><span data-stu-id="17758-131">The following example shows how use the **\<cryptoClass>** element to reference a cryptography class and to configure the runtime.</span></span> <span data-ttu-id="17758-132">然后，你可以将字符串"RSA"传递到<xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType>方法并使用<xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A>方法以返回`MyCryptoRSAClass`对象。</span><span class="sxs-lookup"><span data-stu-id="17758-132">You can then pass the string "RSA" to the <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> method and use the <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> method to return a `MyCryptoRSAClass` object.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="17758-133">另请参阅</span><span class="sxs-lookup"><span data-stu-id="17758-133">See Also</span></span>  
 [<span data-ttu-id="17758-134">配置文件架构</span><span class="sxs-lookup"><span data-stu-id="17758-134">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [<span data-ttu-id="17758-135">加密设置架构</span><span class="sxs-lookup"><span data-stu-id="17758-135">Cryptography Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/cryptography/index.md)  
 [<span data-ttu-id="17758-136">加密服务</span><span class="sxs-lookup"><span data-stu-id="17758-136">Cryptographic Services</span></span>](../../../../../docs/standard/security/cryptographic-services.md)  
 [<span data-ttu-id="17758-137">配置加密类</span><span class="sxs-lookup"><span data-stu-id="17758-137">Configuring Cryptography Classes</span></span>](../../../../../docs/framework/configure-apps/configure-cryptography-classes.md)
