---
title: <cryptoClasses> 元素
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/mscorlib/cryptographySettings/cryptoNameMapping/cryptoClasses
- http://schemas.microsoft.com/.NetConfiguration/v2.0#cryptoClasses
helpviewer_keywords:
- <cryptoClasses> element
- cryptoClasses element
ms.assetid: 290d5f96-946d-4f02-babb-1d31ec0b8295
ms.openlocfilehash: 89f1d89ea397794e366b53205ac23b94d7892869
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/01/2019
ms.locfileid: "71699759"
---
# <a name="cryptoclasses-element"></a><span data-ttu-id="dcc60-102">\<cryptoClasses > 元素</span><span class="sxs-lookup"><span data-stu-id="dcc60-102">\<cryptoClasses> Element</span></span>
<span data-ttu-id="dcc60-103">包含密码类的列表，这些类具有到 [\<nameEntry>](nameentry-element.md) 元素中的友好名称的映射。</span><span class="sxs-lookup"><span data-stu-id="dcc60-103">Contains a list of cryptography classes that have a mapping to a friendly name in the [\<nameEntry>](nameentry-element.md) element.</span></span>  
  
[<span data-ttu-id="dcc60-104"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="dcc60-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="dcc60-105">&nbsp; @ no__t-1[ **\<mscorlib >** ](mscorlib-element-for-cryptography-settings.md)</span><span class="sxs-lookup"><span data-stu-id="dcc60-105">&nbsp;&nbsp;[**\<mscorlib>**](mscorlib-element-for-cryptography-settings.md)</span></span>  
<span data-ttu-id="dcc60-106">&nbsp; @ no__t-1 @ no__t-2 @ no__t[ **\<cryptographySettings >** ](cryptographysettings-element.md)</span><span class="sxs-lookup"><span data-stu-id="dcc60-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<cryptographySettings>**](cryptographysettings-element.md)</span></span>  
<span data-ttu-id="dcc60-107">&nbsp; @ no__t-1 @ no__t-2 @ no__t-3 @ no__t-4 @ no__t-5[ **\<cryptoNameMapping >** ](cryptonamemapping-element.md)</span><span class="sxs-lookup"><span data-stu-id="dcc60-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<cryptoNameMapping>**](cryptonamemapping-element.md)</span></span>  
<span data-ttu-id="dcc60-108">&nbsp; @ no__t-1 @ no__t-2 @ no__t-3 @ no__t-4 @ no__t-5 @ no__t-6 @ no__t-7 **\<cryptoClasses >**</span><span class="sxs-lookup"><span data-stu-id="dcc60-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<cryptoClasses>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dcc60-109">语法</span><span class="sxs-lookup"><span data-stu-id="dcc60-109">Syntax</span></span>  
  
```xml  
<cryptoClasses>   
</cryptoClasses>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="dcc60-110">特性和元素</span><span class="sxs-lookup"><span data-stu-id="dcc60-110">Attributes and Elements</span></span>  
 <span data-ttu-id="dcc60-111">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="dcc60-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="dcc60-112">特性</span><span class="sxs-lookup"><span data-stu-id="dcc60-112">Attributes</span></span>  
 <span data-ttu-id="dcc60-113">无。</span><span class="sxs-lookup"><span data-stu-id="dcc60-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="dcc60-114">子元素</span><span class="sxs-lookup"><span data-stu-id="dcc60-114">Child Elements</span></span>  
  
|<span data-ttu-id="dcc60-115">元素</span><span class="sxs-lookup"><span data-stu-id="dcc60-115">Element</span></span>|<span data-ttu-id="dcc60-116">描述</span><span class="sxs-lookup"><span data-stu-id="dcc60-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="dcc60-117">\<cryptoClass></span><span class="sxs-lookup"><span data-stu-id="dcc60-117">\<cryptoClass></span></span>](cryptoclass-element.md)|<span data-ttu-id="dcc60-118">包含一个密码类，该类具有到 **\<nameEntry>** 元素中的友好名称的映射。</span><span class="sxs-lookup"><span data-stu-id="dcc60-118">Contains a cryptography class that has a mapping to a friendly name in the **\<nameEntry>** element.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="dcc60-119">父元素</span><span class="sxs-lookup"><span data-stu-id="dcc60-119">Parent Elements</span></span>  
  
|<span data-ttu-id="dcc60-120">元素</span><span class="sxs-lookup"><span data-stu-id="dcc60-120">Element</span></span>|<span data-ttu-id="dcc60-121">描述</span><span class="sxs-lookup"><span data-stu-id="dcc60-121">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="dcc60-122">公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。</span><span class="sxs-lookup"><span data-stu-id="dcc60-122">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`cryptographySettings`|<span data-ttu-id="dcc60-123">包含加密设置。</span><span class="sxs-lookup"><span data-stu-id="dcc60-123">Contains cryptography settings.</span></span>|  
|`cryptoNameMapping`|<span data-ttu-id="dcc60-124">包含类到友好名称的映射。</span><span class="sxs-lookup"><span data-stu-id="dcc60-124">Contains mappings of classes to friendly names.</span></span>|  
|`mscorlib`|<span data-ttu-id="dcc60-125">`cryptographySettings`包含元素。</span><span class="sxs-lookup"><span data-stu-id="dcc60-125">Contains the `cryptographySettings` element.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="dcc60-126">示例</span><span class="sxs-lookup"><span data-stu-id="dcc60-126">Example</span></span>  
 <span data-ttu-id="dcc60-127">下面的示例演示如何使用 **\<cryptoClass >** 元素来引用加密类并配置运行时。</span><span class="sxs-lookup"><span data-stu-id="dcc60-127">The following example shows how use the **\<cryptoClass>** element to reference a cryptography class and to configure the runtime.</span></span> <span data-ttu-id="dcc60-128">然后，你可以将字符串 "RSA" 传递到 @no__t 0 方法，并使用 <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> 方法返回 @no__t 2 对象。</span><span class="sxs-lookup"><span data-stu-id="dcc60-128">You can then pass the string "RSA" to the <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> method and use the <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> method to return a `MyCryptoRSAClass` object.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="dcc60-129">请参阅</span><span class="sxs-lookup"><span data-stu-id="dcc60-129">See also</span></span>

- <xref:System.Security.Cryptography>
- [<span data-ttu-id="dcc60-130">配置文件架构</span><span class="sxs-lookup"><span data-stu-id="dcc60-130">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="dcc60-131">加密设置架构</span><span class="sxs-lookup"><span data-stu-id="dcc60-131">Cryptography Settings Schema</span></span>](index.md)
- [<span data-ttu-id="dcc60-132">Cryptographic Services</span><span class="sxs-lookup"><span data-stu-id="dcc60-132">Cryptographic Services</span></span>](../../../../standard/security/cryptographic-services.md)
- [<span data-ttu-id="dcc60-133">System.Security.Cryptography.CryptoConfig.CreateFromName</span><span class="sxs-lookup"><span data-stu-id="dcc60-133">System.Security.Cryptography.CryptoConfig.CreateFromName</span></span>](Overload:System.Security.Cryptography.CryptoConfig.CreateFromName)
- [<span data-ttu-id="dcc60-134">配置加密类</span><span class="sxs-lookup"><span data-stu-id="dcc60-134">Configuring Cryptography Classes</span></span>](../../configure-cryptography-classes.md)
