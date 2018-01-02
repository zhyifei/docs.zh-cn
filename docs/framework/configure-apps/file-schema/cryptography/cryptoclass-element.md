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
ms.workload: dotnet
ms.openlocfilehash: 69e844532ab7b9979687e54d7ad4076cd3f51f46
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="ltcryptoclassgt-element"></a><span data-ttu-id="03d85-102">&lt;cryptoClass&gt;元素</span><span class="sxs-lookup"><span data-stu-id="03d85-102">&lt;cryptoClass&gt; Element</span></span>
<span data-ttu-id="03d85-103">包含一个密码类，该类具有到 [\<nameEntry>](../../../../../docs/framework/configure-apps/file-schema/cryptography/nameentry-element.md) 元素中的友好名称的映射。</span><span class="sxs-lookup"><span data-stu-id="03d85-103">Contains a cryptography class that has a mapping to a friendly name in the [\<nameEntry>](../../../../../docs/framework/configure-apps/file-schema/cryptography/nameentry-element.md) element.</span></span>  
  
 <span data-ttu-id="03d85-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="03d85-104">\<configuration></span></span>  
<span data-ttu-id="03d85-105">\<mscorlib ></span><span class="sxs-lookup"><span data-stu-id="03d85-105">\<mscorlib></span></span>  
<span data-ttu-id="03d85-106">\<g s ></span><span class="sxs-lookup"><span data-stu-id="03d85-106">\<cryptographySettings></span></span>  
<span data-ttu-id="03d85-107">\<cryptoNameMapping ></span><span class="sxs-lookup"><span data-stu-id="03d85-107">\<cryptoNameMapping></span></span>  
<span data-ttu-id="03d85-108">\<cryptoClasses ></span><span class="sxs-lookup"><span data-stu-id="03d85-108">\<cryptoClasses></span></span>  
<span data-ttu-id="03d85-109">\<cryptoClass ></span><span class="sxs-lookup"><span data-stu-id="03d85-109">\<cryptoClass></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="03d85-110">语法</span><span class="sxs-lookup"><span data-stu-id="03d85-110">Syntax</span></span>  
  
```xml  
<cryptoClass customClassName="fully qualified type name" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="03d85-111">特性和元素</span><span class="sxs-lookup"><span data-stu-id="03d85-111">Attributes and Elements</span></span>  
 <span data-ttu-id="03d85-112">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="03d85-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="03d85-113">特性</span><span class="sxs-lookup"><span data-stu-id="03d85-113">Attributes</span></span>  
  
|<span data-ttu-id="03d85-114">特性</span><span class="sxs-lookup"><span data-stu-id="03d85-114">Attribute</span></span>|<span data-ttu-id="03d85-115">描述</span><span class="sxs-lookup"><span data-stu-id="03d85-115">Description</span></span>|  
|---------------|-----------------|  
|`customClassName`|<span data-ttu-id="03d85-116">必需的特性。</span><span class="sxs-lookup"><span data-stu-id="03d85-116">Required attribute.</span></span><br /><br /> <span data-ttu-id="03d85-117">包含加密类的信息。</span><span class="sxs-lookup"><span data-stu-id="03d85-117">Contains the information for the cryptography class.</span></span> <span data-ttu-id="03d85-118">使用此属性以提供您的类的短名称。</span><span class="sxs-lookup"><span data-stu-id="03d85-118">Use this attribute to provide a short name for your class.</span></span> <span data-ttu-id="03d85-119">必须指定满足要求中指定的字符串[指定完全限定的类型名称](../../../../../docs/framework/reflection-and-codedom/specifying-fully-qualified-type-names.md)。</span><span class="sxs-lookup"><span data-stu-id="03d85-119">You must specify a string that meets the requirements specified in [Specifying Fully Qualified Type Names](../../../../../docs/framework/reflection-and-codedom/specifying-fully-qualified-type-names.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="03d85-120">子元素</span><span class="sxs-lookup"><span data-stu-id="03d85-120">Child Elements</span></span>  
 <span data-ttu-id="03d85-121">无。</span><span class="sxs-lookup"><span data-stu-id="03d85-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="03d85-122">父元素</span><span class="sxs-lookup"><span data-stu-id="03d85-122">Parent Elements</span></span>  
  
|<span data-ttu-id="03d85-123">元素</span><span class="sxs-lookup"><span data-stu-id="03d85-123">Element</span></span>|<span data-ttu-id="03d85-124">说明</span><span class="sxs-lookup"><span data-stu-id="03d85-124">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="03d85-125">公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。</span><span class="sxs-lookup"><span data-stu-id="03d85-125">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`cryptoClasses`|<span data-ttu-id="03d85-126">包含密码类的列表，这些类具有到 [\<nameEntry>](../../../../../docs/framework/configure-apps/file-schema/cryptography/nameentry-element.md) 元素中的友好名称的映射。</span><span class="sxs-lookup"><span data-stu-id="03d85-126">Contains a list of cryptography classes that have a mapping to a friendly name in the [\<nameEntry>](../../../../../docs/framework/configure-apps/file-schema/cryptography/nameentry-element.md) element.</span></span>|  
|`cryptographySettings`|<span data-ttu-id="03d85-127">包含加密设置。</span><span class="sxs-lookup"><span data-stu-id="03d85-127">Contains cryptography settings.</span></span>|  
|`cryptoNameMapping`|<span data-ttu-id="03d85-128">包含类到友好名称的映射。</span><span class="sxs-lookup"><span data-stu-id="03d85-128">Contains mappings of classes to friendly names.</span></span>|  
|`mscorlib`|<span data-ttu-id="03d85-129">包含 [\<cryptographySettings>](../../../../../docs/framework/configure-apps/file-schema/cryptography/cryptographysettings-element.md) 元素。</span><span class="sxs-lookup"><span data-stu-id="03d85-129">Contains the [\<cryptographySettings>](../../../../../docs/framework/configure-apps/file-schema/cryptography/cryptographysettings-element.md) element.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="03d85-130">示例</span><span class="sxs-lookup"><span data-stu-id="03d85-130">Example</span></span>  
 <span data-ttu-id="03d85-131">下面的示例演示如何使用 **\<cryptoClass >**元素来引用密码类并配置运行时。</span><span class="sxs-lookup"><span data-stu-id="03d85-131">The following example shows how use the **\<cryptoClass>** element to reference a cryptography class and to configure the runtime.</span></span> <span data-ttu-id="03d85-132">然后，你可以将字符串"RSA"传递到<xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType>方法并使用<xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A>方法以返回`MyCryptoRSAClass`对象。</span><span class="sxs-lookup"><span data-stu-id="03d85-132">You can then pass the string "RSA" to the <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> method and use the <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> method to return a `MyCryptoRSAClass` object.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="03d85-133">请参阅</span><span class="sxs-lookup"><span data-stu-id="03d85-133">See Also</span></span>  
 [<span data-ttu-id="03d85-134">配置文件架构</span><span class="sxs-lookup"><span data-stu-id="03d85-134">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [<span data-ttu-id="03d85-135">加密设置架构</span><span class="sxs-lookup"><span data-stu-id="03d85-135">Cryptography Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/cryptography/index.md)  
 [<span data-ttu-id="03d85-136">加密服务</span><span class="sxs-lookup"><span data-stu-id="03d85-136">Cryptographic Services</span></span>](../../../../../docs/standard/security/cryptographic-services.md)  
 [<span data-ttu-id="03d85-137">配置加密类</span><span class="sxs-lookup"><span data-stu-id="03d85-137">Configuring Cryptography Classes</span></span>](../../../../../docs/framework/configure-apps/configure-cryptography-classes.md)
