---
title: <nameEntry> 元素
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#nameEntry
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/mscorlib/cryptographySettings/cryptoNameMapping/nameEntry
helpviewer_keywords:
- <nameEntry> element
- nameEntry element
ms.assetid: 7d7535e9-4b4a-4b8c-82e2-e40dff5a7821
ms.openlocfilehash: d8f4d4aa9c80990cdf858da9fcdf6465438866cf
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69927560"
---
# <a name="nameentry-element"></a><span data-ttu-id="96f36-102">\<y > 元素</span><span class="sxs-lookup"><span data-stu-id="96f36-102">\<nameEntry> Element</span></span>
<span data-ttu-id="96f36-103">将类名称映射到友好算法名称，允许一个类具有多个友好名称。</span><span class="sxs-lookup"><span data-stu-id="96f36-103">Maps a class name to a friendly algorithm name, which allows one class to have many friendly names.</span></span>  
  
 <span data-ttu-id="96f36-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="96f36-104">\<configuration></span></span>  
<span data-ttu-id="96f36-105">\<mscorlib></span><span class="sxs-lookup"><span data-stu-id="96f36-105">\<mscorlib></span></span>  
<span data-ttu-id="96f36-106">\<cryptographySettings></span><span class="sxs-lookup"><span data-stu-id="96f36-106">\<cryptographySettings></span></span>  
<span data-ttu-id="96f36-107">\<cryptoNameMapping></span><span class="sxs-lookup"><span data-stu-id="96f36-107">\<cryptoNameMapping></span></span>  
<span data-ttu-id="96f36-108">\<nameEntry></span><span class="sxs-lookup"><span data-stu-id="96f36-108">\<nameEntry></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="96f36-109">语法</span><span class="sxs-lookup"><span data-stu-id="96f36-109">Syntax</span></span>  
  
```xml  
<nameEntry name="friendly name" Class="class name" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="96f36-110">特性和元素</span><span class="sxs-lookup"><span data-stu-id="96f36-110">Attributes and Elements</span></span>  
 <span data-ttu-id="96f36-111">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="96f36-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="96f36-112">特性</span><span class="sxs-lookup"><span data-stu-id="96f36-112">Attributes</span></span>  
  
|<span data-ttu-id="96f36-113">特性</span><span class="sxs-lookup"><span data-stu-id="96f36-113">Attribute</span></span>|<span data-ttu-id="96f36-114">描述</span><span class="sxs-lookup"><span data-stu-id="96f36-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="96f36-115">**名称**</span><span class="sxs-lookup"><span data-stu-id="96f36-115">**name**</span></span>|<span data-ttu-id="96f36-116">必需的特性。</span><span class="sxs-lookup"><span data-stu-id="96f36-116">Required attribute.</span></span><br /><br /> <span data-ttu-id="96f36-117">指定密码类实现的算法的友好名称。</span><span class="sxs-lookup"><span data-stu-id="96f36-117">Specifies the friendly name of the algorithm that the cryptography class implements.</span></span>|  
|<span data-ttu-id="96f36-118">**class**</span><span class="sxs-lookup"><span data-stu-id="96f36-118">**class**</span></span>|<span data-ttu-id="96f36-119">必需的特性。</span><span class="sxs-lookup"><span data-stu-id="96f36-119">Required attribute.</span></span><br /><br /> <span data-ttu-id="96f36-120">[指定\<cryptoClass >](cryptoclass-element.md)元素中**name**属性的值。</span><span class="sxs-lookup"><span data-stu-id="96f36-120">Specifies the value for the **name** attribute in the [\<cryptoClass>](cryptoclass-element.md) element.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="96f36-121">子元素</span><span class="sxs-lookup"><span data-stu-id="96f36-121">Child Elements</span></span>  
 <span data-ttu-id="96f36-122">无。</span><span class="sxs-lookup"><span data-stu-id="96f36-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="96f36-123">父元素</span><span class="sxs-lookup"><span data-stu-id="96f36-123">Parent Elements</span></span>  
  
|<span data-ttu-id="96f36-124">元素</span><span class="sxs-lookup"><span data-stu-id="96f36-124">Element</span></span>|<span data-ttu-id="96f36-125">描述</span><span class="sxs-lookup"><span data-stu-id="96f36-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="96f36-126">公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。</span><span class="sxs-lookup"><span data-stu-id="96f36-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.web`|<span data-ttu-id="96f36-127">为 ASP.NET 配置节指定根元素。</span><span class="sxs-lookup"><span data-stu-id="96f36-127">Specifies the root element for the ASP.NET configuration section.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="96f36-128">备注</span><span class="sxs-lookup"><span data-stu-id="96f36-128">Remarks</span></span>  
 <span data-ttu-id="96f36-129">**Name**属性可以是在<xref:System.Security.Cryptography>命名空间中找到的某个抽象类的名称。</span><span class="sxs-lookup"><span data-stu-id="96f36-129">The **name** attribute can be the name of one of the abstract classes found in the <xref:System.Security.Cryptography> namespace.</span></span> <span data-ttu-id="96f36-130">对抽象加密类调用**Create**方法时, 会将抽象类名称传递给<xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A>方法。</span><span class="sxs-lookup"><span data-stu-id="96f36-130">When you call the **Create** method on an abstract cryptography class, the abstract class name is passed to the <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A> method.</span></span> <span data-ttu-id="96f36-131">**Cryptoconfig.createfromname**返回**类**特性指示的类型的实例。</span><span class="sxs-lookup"><span data-stu-id="96f36-131">**CreateFromName** returns an instance of the type indicated by the **class** attribute.</span></span> <span data-ttu-id="96f36-132">如果**name**属性是一个短名称, 例如 RSA, 则可以在调用**cryptoconfig.createfromname**方法时使用该名称。</span><span class="sxs-lookup"><span data-stu-id="96f36-132">If the **name** attribute is a short name, such as RSA, you can use that name when calling the **CreateFromName** method.</span></span>  
  
## <a name="example"></a><span data-ttu-id="96f36-133">示例</span><span class="sxs-lookup"><span data-stu-id="96f36-133">Example</span></span>  
 <span data-ttu-id="96f36-134">下面的示例演示如何使用 **\<y >** 元素来引用加密类并配置运行时。</span><span class="sxs-lookup"><span data-stu-id="96f36-134">The following example shows how to use the **\<nameEntry>** element to reference a cryptography class and to configure the runtime.</span></span> <span data-ttu-id="96f36-135">然后, 你可以将字符串 "RSA" 传递给<xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType>方法, 并<xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A>使用方法返回`MyCryptoRSAClass`对象。</span><span class="sxs-lookup"><span data-stu-id="96f36-135">You can then pass the string "RSA" to the <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> method and use the <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> method to return a `MyCryptoRSAClass` object.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="96f36-136">请参阅</span><span class="sxs-lookup"><span data-stu-id="96f36-136">See also</span></span>

- [<span data-ttu-id="96f36-137">配置文件架构</span><span class="sxs-lookup"><span data-stu-id="96f36-137">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="96f36-138">加密设置架构</span><span class="sxs-lookup"><span data-stu-id="96f36-138">Cryptography Settings Schema</span></span>](index.md)
- [<span data-ttu-id="96f36-139">Cryptographic Services</span><span class="sxs-lookup"><span data-stu-id="96f36-139">Cryptographic Services</span></span>](../../../../standard/security/cryptographic-services.md)
- [<span data-ttu-id="96f36-140">配置加密类</span><span class="sxs-lookup"><span data-stu-id="96f36-140">Configuring Cryptography Classes</span></span>](../../configure-cryptography-classes.md)
