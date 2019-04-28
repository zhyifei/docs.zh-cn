---
title: <cryptoClass> 元素
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/mscorlib/cryptographySettings/cryptoNameMapping/cryptoClasses/cryptoClass
- http://schemas.microsoft.com/.NetConfiguration/v2.0#cryptoClass
helpviewer_keywords:
- cryptoClass element
- <cryptoClass> element
ms.assetid: 03db52ef-010e-44ea-b6fd-b9c900ecad50
ms.openlocfilehash: da78140806ab8dbe7b7cb5e321e82755774ff25d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61705254"
---
# <a name="cryptoclass-element"></a><span data-ttu-id="81815-102">\<cryptoClass > 元素</span><span class="sxs-lookup"><span data-stu-id="81815-102">\<cryptoClass> Element</span></span>
<span data-ttu-id="81815-103">包含一个密码类，该类具有到 [\<nameEntry>](../../../../../docs/framework/configure-apps/file-schema/cryptography/nameentry-element.md) 元素中的友好名称的映射。</span><span class="sxs-lookup"><span data-stu-id="81815-103">Contains a cryptography class that has a mapping to a friendly name in the [\<nameEntry>](../../../../../docs/framework/configure-apps/file-schema/cryptography/nameentry-element.md) element.</span></span>  
  
 <span data-ttu-id="81815-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="81815-104">\<configuration></span></span>  
<span data-ttu-id="81815-105">\<mscorlib></span><span class="sxs-lookup"><span data-stu-id="81815-105">\<mscorlib></span></span>  
<span data-ttu-id="81815-106">\<cryptographySettings></span><span class="sxs-lookup"><span data-stu-id="81815-106">\<cryptographySettings></span></span>  
<span data-ttu-id="81815-107">\<cryptoNameMapping></span><span class="sxs-lookup"><span data-stu-id="81815-107">\<cryptoNameMapping></span></span>  
<span data-ttu-id="81815-108">\<cryptoClasses></span><span class="sxs-lookup"><span data-stu-id="81815-108">\<cryptoClasses></span></span>  
<span data-ttu-id="81815-109">\<cryptoClass></span><span class="sxs-lookup"><span data-stu-id="81815-109">\<cryptoClass></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="81815-110">语法</span><span class="sxs-lookup"><span data-stu-id="81815-110">Syntax</span></span>  
  
```xml  
<cryptoClass customClassName="fully qualified type name" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="81815-111">特性和元素</span><span class="sxs-lookup"><span data-stu-id="81815-111">Attributes and Elements</span></span>  
 <span data-ttu-id="81815-112">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="81815-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="81815-113">特性</span><span class="sxs-lookup"><span data-stu-id="81815-113">Attributes</span></span>  
  
|<span data-ttu-id="81815-114">特性</span><span class="sxs-lookup"><span data-stu-id="81815-114">Attribute</span></span>|<span data-ttu-id="81815-115">描述</span><span class="sxs-lookup"><span data-stu-id="81815-115">Description</span></span>|  
|---------------|-----------------|  
|`customClassName`|<span data-ttu-id="81815-116">必需的特性。</span><span class="sxs-lookup"><span data-stu-id="81815-116">Required attribute.</span></span><br /><br /> <span data-ttu-id="81815-117">包含密码类的信息。</span><span class="sxs-lookup"><span data-stu-id="81815-117">Contains the information for the cryptography class.</span></span> <span data-ttu-id="81815-118">此属性用于提供您的类的短名称。</span><span class="sxs-lookup"><span data-stu-id="81815-118">Use this attribute to provide a short name for your class.</span></span> <span data-ttu-id="81815-119">必须指定一个字符串，满足中指定的要求[指定完全限定的类型名称](../../../../../docs/framework/reflection-and-codedom/specifying-fully-qualified-type-names.md)。</span><span class="sxs-lookup"><span data-stu-id="81815-119">You must specify a string that meets the requirements specified in [Specifying Fully Qualified Type Names](../../../../../docs/framework/reflection-and-codedom/specifying-fully-qualified-type-names.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="81815-120">子元素</span><span class="sxs-lookup"><span data-stu-id="81815-120">Child Elements</span></span>  
 <span data-ttu-id="81815-121">无。</span><span class="sxs-lookup"><span data-stu-id="81815-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="81815-122">父元素</span><span class="sxs-lookup"><span data-stu-id="81815-122">Parent Elements</span></span>  
  
|<span data-ttu-id="81815-123">元素</span><span class="sxs-lookup"><span data-stu-id="81815-123">Element</span></span>|<span data-ttu-id="81815-124">描述</span><span class="sxs-lookup"><span data-stu-id="81815-124">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="81815-125">公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。</span><span class="sxs-lookup"><span data-stu-id="81815-125">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`cryptoClasses`|<span data-ttu-id="81815-126">包含密码类的列表，这些类具有到 [\<nameEntry>](../../../../../docs/framework/configure-apps/file-schema/cryptography/nameentry-element.md) 元素中的友好名称的映射。</span><span class="sxs-lookup"><span data-stu-id="81815-126">Contains a list of cryptography classes that have a mapping to a friendly name in the [\<nameEntry>](../../../../../docs/framework/configure-apps/file-schema/cryptography/nameentry-element.md) element.</span></span>|  
|`cryptographySettings`|<span data-ttu-id="81815-127">包含加密设置。</span><span class="sxs-lookup"><span data-stu-id="81815-127">Contains cryptography settings.</span></span>|  
|`cryptoNameMapping`|<span data-ttu-id="81815-128">包含类到友好名称的映射。</span><span class="sxs-lookup"><span data-stu-id="81815-128">Contains mappings of classes to friendly names.</span></span>|  
|`mscorlib`|<span data-ttu-id="81815-129">包含 [\<cryptographySettings>](../../../../../docs/framework/configure-apps/file-schema/cryptography/cryptographysettings-element.md) 元素。</span><span class="sxs-lookup"><span data-stu-id="81815-129">Contains the [\<cryptographySettings>](../../../../../docs/framework/configure-apps/file-schema/cryptography/cryptographysettings-element.md) element.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="81815-130">示例</span><span class="sxs-lookup"><span data-stu-id="81815-130">Example</span></span>  
 <span data-ttu-id="81815-131">以下示例演示如何使用 **\<cryptoClass >** 元素来引用一个密码类并配置运行时。</span><span class="sxs-lookup"><span data-stu-id="81815-131">The following example shows how use the **\<cryptoClass>** element to reference a cryptography class and to configure the runtime.</span></span> <span data-ttu-id="81815-132">然后可以将字符串"RSA"传递给<xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType>方法，并使用<xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A>方法以返回`MyCryptoRSAClass`对象。</span><span class="sxs-lookup"><span data-stu-id="81815-132">You can then pass the string "RSA" to the <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> method and use the <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> method to return a `MyCryptoRSAClass` object.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="81815-133">请参阅</span><span class="sxs-lookup"><span data-stu-id="81815-133">See also</span></span>

- [<span data-ttu-id="81815-134">配置文件架构</span><span class="sxs-lookup"><span data-stu-id="81815-134">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)
- [<span data-ttu-id="81815-135">加密设置架构</span><span class="sxs-lookup"><span data-stu-id="81815-135">Cryptography Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/cryptography/index.md)
- [<span data-ttu-id="81815-136">Cryptographic Services</span><span class="sxs-lookup"><span data-stu-id="81815-136">Cryptographic Services</span></span>](../../../../../docs/standard/security/cryptographic-services.md)
- [<span data-ttu-id="81815-137">配置加密类</span><span class="sxs-lookup"><span data-stu-id="81815-137">Configuring Cryptography Classes</span></span>](../../../../../docs/framework/configure-apps/configure-cryptography-classes.md)
