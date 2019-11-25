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
ms.openlocfilehash: 4872fbd6fa043902e8c69f158bee5d0c915ec83a
ms.sourcegitcommit: 7f8eeef060ddeb2cabfa52843776faf652c5a1f5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/14/2019
ms.locfileid: "74088659"
---
# <a name="cryptoclass-element"></a><span data-ttu-id="48e86-102">\<cryptoClass > 元素</span><span class="sxs-lookup"><span data-stu-id="48e86-102">\<cryptoClass> Element</span></span>
<span data-ttu-id="48e86-103">包含一个密码类，该类具有到 [\<nameEntry>](nameentry-element.md) 元素中的友好名称的映射。</span><span class="sxs-lookup"><span data-stu-id="48e86-103">Contains a cryptography class that has a mapping to a friendly name in the [\<nameEntry>](nameentry-element.md) element.</span></span>  

<span data-ttu-id="48e86-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="48e86-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="48e86-105">&nbsp;&nbsp;[ **\<mscorlib >** ](mscorlib-element-for-cryptography-settings.md)</span><span class="sxs-lookup"><span data-stu-id="48e86-105">&nbsp;&nbsp;[**\<mscorlib>**](mscorlib-element-for-cryptography-settings.md)</span></span>\
<span data-ttu-id="48e86-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<g s >** ](cryptographysettings-element.md)</span><span class="sxs-lookup"><span data-stu-id="48e86-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<cryptographySettings>**](cryptographysettings-element.md)</span></span>\
<span data-ttu-id="48e86-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<cryptoNameMapping >** ](cryptonamemapping-element.md)</span><span class="sxs-lookup"><span data-stu-id="48e86-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<cryptoNameMapping>**](cryptonamemapping-element.md)</span></span>\
<span data-ttu-id="48e86-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<cryptoClasses >** ](cryptoclasses-element.md)</span><span class="sxs-lookup"><span data-stu-id="48e86-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<cryptoClasses>**](cryptoclasses-element.md)</span></span>\
<span data-ttu-id="48e86-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<cryptoClass >**</span><span class="sxs-lookup"><span data-stu-id="48e86-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<cryptoClass>**</span></span>

## <a name="syntax"></a><span data-ttu-id="48e86-110">语法</span><span class="sxs-lookup"><span data-stu-id="48e86-110">Syntax</span></span>  
  
```xml  
<cryptoClass customClassName="fully qualified type name" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="48e86-111">特性和元素</span><span class="sxs-lookup"><span data-stu-id="48e86-111">Attributes and Elements</span></span>  
 <span data-ttu-id="48e86-112">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="48e86-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="48e86-113">特性</span><span class="sxs-lookup"><span data-stu-id="48e86-113">Attributes</span></span>  
  
|<span data-ttu-id="48e86-114">特性</span><span class="sxs-lookup"><span data-stu-id="48e86-114">Attribute</span></span>|<span data-ttu-id="48e86-115">描述</span><span class="sxs-lookup"><span data-stu-id="48e86-115">Description</span></span>|  
|---------------|-----------------|  
|`customClassName`|<span data-ttu-id="48e86-116">必需的特性。</span><span class="sxs-lookup"><span data-stu-id="48e86-116">Required attribute.</span></span><br /><br /> <span data-ttu-id="48e86-117">包含加密类的信息。</span><span class="sxs-lookup"><span data-stu-id="48e86-117">Contains the information for the cryptography class.</span></span> <span data-ttu-id="48e86-118">使用此特性可为你的类提供一个短名称。</span><span class="sxs-lookup"><span data-stu-id="48e86-118">Use this attribute to provide a short name for your class.</span></span> <span data-ttu-id="48e86-119">您必须指定满足指定[完全限定的类型名称](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md)中指定的要求的字符串。</span><span class="sxs-lookup"><span data-stu-id="48e86-119">You must specify a string that meets the requirements specified in [Specifying Fully Qualified Type Names](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="48e86-120">子元素</span><span class="sxs-lookup"><span data-stu-id="48e86-120">Child Elements</span></span>  
 <span data-ttu-id="48e86-121">无。</span><span class="sxs-lookup"><span data-stu-id="48e86-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="48e86-122">父元素</span><span class="sxs-lookup"><span data-stu-id="48e86-122">Parent Elements</span></span>  
  
|<span data-ttu-id="48e86-123">元素</span><span class="sxs-lookup"><span data-stu-id="48e86-123">Element</span></span>|<span data-ttu-id="48e86-124">描述</span><span class="sxs-lookup"><span data-stu-id="48e86-124">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="48e86-125">公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。</span><span class="sxs-lookup"><span data-stu-id="48e86-125">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`cryptoClasses`|<span data-ttu-id="48e86-126">包含密码类的列表，这些类具有到 [\<nameEntry>](nameentry-element.md) 元素中的友好名称的映射。</span><span class="sxs-lookup"><span data-stu-id="48e86-126">Contains a list of cryptography classes that have a mapping to a friendly name in the [\<nameEntry>](nameentry-element.md) element.</span></span>|  
|`cryptographySettings`|<span data-ttu-id="48e86-127">包含加密设置。</span><span class="sxs-lookup"><span data-stu-id="48e86-127">Contains cryptography settings.</span></span>|  
|`cryptoNameMapping`|<span data-ttu-id="48e86-128">包含类到友好名称的映射。</span><span class="sxs-lookup"><span data-stu-id="48e86-128">Contains mappings of classes to friendly names.</span></span>|  
|`mscorlib`|<span data-ttu-id="48e86-129">包含 [\<cryptographySettings>](cryptographysettings-element.md) 元素。</span><span class="sxs-lookup"><span data-stu-id="48e86-129">Contains the [\<cryptographySettings>](cryptographysettings-element.md) element.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="48e86-130">示例</span><span class="sxs-lookup"><span data-stu-id="48e86-130">Example</span></span>  
 <span data-ttu-id="48e86-131">下面的示例演示如何使用 **\<cryptoClass >** 元素来引用加密类并配置运行时。</span><span class="sxs-lookup"><span data-stu-id="48e86-131">The following example shows how use the **\<cryptoClass>** element to reference a cryptography class and to configure the runtime.</span></span> <span data-ttu-id="48e86-132">然后，你可以将字符串 "RSA" 传递到 <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> 方法，并使用 <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> 方法返回 `MyCryptoRSAClass` 对象。</span><span class="sxs-lookup"><span data-stu-id="48e86-132">You can then pass the string "RSA" to the <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> method and use the <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> method to return a `MyCryptoRSAClass` object.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="48e86-133">请参阅</span><span class="sxs-lookup"><span data-stu-id="48e86-133">See also</span></span>

- [<span data-ttu-id="48e86-134">配置文件架构</span><span class="sxs-lookup"><span data-stu-id="48e86-134">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="48e86-135">加密设置架构</span><span class="sxs-lookup"><span data-stu-id="48e86-135">Cryptography Settings Schema</span></span>](index.md)
- [<span data-ttu-id="48e86-136">加密服务</span><span class="sxs-lookup"><span data-stu-id="48e86-136">Cryptographic Services</span></span>](../../../../standard/security/cryptographic-services.md)
- [<span data-ttu-id="48e86-137">配置加密类</span><span class="sxs-lookup"><span data-stu-id="48e86-137">Configuring Cryptography Classes</span></span>](../../configure-cryptography-classes.md)
