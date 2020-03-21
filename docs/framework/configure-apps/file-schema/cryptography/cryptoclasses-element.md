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
ms.openlocfilehash: c93fadf51297d59ab499e25de283700364903049
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79155241"
---
# <a name="cryptoclasses-element"></a><span data-ttu-id="ac347-102">\<加密类>元素</span><span class="sxs-lookup"><span data-stu-id="ac347-102">\<cryptoClasses> Element</span></span>
<span data-ttu-id="ac347-103">包含具有映射到[\<nameentry>](nameentry-element.md)元素中的友好名称的加密类的列表。</span><span class="sxs-lookup"><span data-stu-id="ac347-103">Contains a list of cryptography classes that have a mapping to a friendly name in the [\<nameEntry>](nameentry-element.md) element.</span></span>  
  
[<span data-ttu-id="ac347-104">**\<配置>**</span><span class="sxs-lookup"><span data-stu-id="ac347-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="ac347-105">&nbsp;&nbsp;[**\<姆斯科利布>**](mscorlib-element-for-cryptography-settings.md)</span><span class="sxs-lookup"><span data-stu-id="ac347-105">&nbsp;&nbsp;[**\<mscorlib>**](mscorlib-element-for-cryptography-settings.md)</span></span>  
<span data-ttu-id="ac347-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<密码设置>**](cryptographysettings-element.md)</span><span class="sxs-lookup"><span data-stu-id="ac347-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<cryptographySettings>**](cryptographysettings-element.md)</span></span>  
<span data-ttu-id="ac347-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<加密名称映射>**](cryptonamemapping-element.md)</span><span class="sxs-lookup"><span data-stu-id="ac347-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<cryptoNameMapping>**](cryptonamemapping-element.md)</span></span>  
<span data-ttu-id="ac347-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<加密类>**</span><span class="sxs-lookup"><span data-stu-id="ac347-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<cryptoClasses>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ac347-109">语法</span><span class="sxs-lookup"><span data-stu-id="ac347-109">Syntax</span></span>  
  
```xml  
<cryptoClasses>
</cryptoClasses>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ac347-110">特性和元素</span><span class="sxs-lookup"><span data-stu-id="ac347-110">Attributes and Elements</span></span>  
 <span data-ttu-id="ac347-111">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="ac347-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ac347-112">属性</span><span class="sxs-lookup"><span data-stu-id="ac347-112">Attributes</span></span>  
 <span data-ttu-id="ac347-113">无。</span><span class="sxs-lookup"><span data-stu-id="ac347-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="ac347-114">子元素</span><span class="sxs-lookup"><span data-stu-id="ac347-114">Child Elements</span></span>  
  
|<span data-ttu-id="ac347-115">元素</span><span class="sxs-lookup"><span data-stu-id="ac347-115">Element</span></span>|<span data-ttu-id="ac347-116">说明</span><span class="sxs-lookup"><span data-stu-id="ac347-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ac347-117">\<加密类></span><span class="sxs-lookup"><span data-stu-id="ac347-117">\<cryptoClass></span></span>](cryptoclass-element.md)|<span data-ttu-id="ac347-118">包含一个加密类，该类具有与**\<nameentry>** 元素中的友好名称的映射。</span><span class="sxs-lookup"><span data-stu-id="ac347-118">Contains a cryptography class that has a mapping to a friendly name in the **\<nameEntry>** element.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="ac347-119">父元素</span><span class="sxs-lookup"><span data-stu-id="ac347-119">Parent Elements</span></span>  
  
|<span data-ttu-id="ac347-120">元素</span><span class="sxs-lookup"><span data-stu-id="ac347-120">Element</span></span>|<span data-ttu-id="ac347-121">说明</span><span class="sxs-lookup"><span data-stu-id="ac347-121">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="ac347-122">公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。</span><span class="sxs-lookup"><span data-stu-id="ac347-122">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`cryptographySettings`|<span data-ttu-id="ac347-123">包含加密设置。</span><span class="sxs-lookup"><span data-stu-id="ac347-123">Contains cryptography settings.</span></span>|  
|`cryptoNameMapping`|<span data-ttu-id="ac347-124">包含类到友好名称的映射。</span><span class="sxs-lookup"><span data-stu-id="ac347-124">Contains mappings of classes to friendly names.</span></span>|  
|`mscorlib`|<span data-ttu-id="ac347-125">包含元素`cryptographySettings`。</span><span class="sxs-lookup"><span data-stu-id="ac347-125">Contains the `cryptographySettings` element.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="ac347-126">示例</span><span class="sxs-lookup"><span data-stu-id="ac347-126">Example</span></span>  
 <span data-ttu-id="ac347-127">下面的示例演示如何使用**\<cryptoclass>** 元素来引用加密类和配置运行时。</span><span class="sxs-lookup"><span data-stu-id="ac347-127">The following example shows how use the **\<cryptoClass>** element to reference a cryptography class and to configure the runtime.</span></span> <span data-ttu-id="ac347-128">然后，可以将字符串"RSA"传递给 方法，<xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType>并使用 方法<xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A>返回对象`MyCryptoRSAClass`。</span><span class="sxs-lookup"><span data-stu-id="ac347-128">You can then pass the string "RSA" to the <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> method and use the <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> method to return a `MyCryptoRSAClass` object.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="ac347-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ac347-129">See also</span></span>

- <xref:System.Security.Cryptography>
- [<span data-ttu-id="ac347-130">配置文件架构</span><span class="sxs-lookup"><span data-stu-id="ac347-130">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="ac347-131">密码设置架构</span><span class="sxs-lookup"><span data-stu-id="ac347-131">Cryptography Settings Schema</span></span>](index.md)
- [<span data-ttu-id="ac347-132">加密服务</span><span class="sxs-lookup"><span data-stu-id="ac347-132">Cryptographic Services</span></span>](../../../../standard/security/cryptographic-services.md)
- [<span data-ttu-id="ac347-133">系统.安全.加密.加密配置.创建从名称</span><span class="sxs-lookup"><span data-stu-id="ac347-133">System.Security.Cryptography.CryptoConfig.CreateFromName</span></span>](xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A)
- [<span data-ttu-id="ac347-134">配置加密类</span><span class="sxs-lookup"><span data-stu-id="ac347-134">Configuring Cryptography Classes</span></span>](../../configure-cryptography-classes.md)
