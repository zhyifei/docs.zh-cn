---
title: Cryptography 设置的 <mscorlib> 元素
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#mscorlib
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/mscorlib
helpviewer_keywords:
- mscorlib element
- <mscorlib> element
ms.assetid: d549668f-31f1-4b92-8021-a9135c09ca3c
ms.openlocfilehash: 4e2159cda5f35b5795804dede09ec17d07d71b23
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/01/2019
ms.locfileid: "71699736"
---
# <a name="mscorlib-element-for-cryptography-settings"></a><span data-ttu-id="10f93-102">用于加密设置的 \<mscorlib > 元素</span><span class="sxs-lookup"><span data-stu-id="10f93-102">\<mscorlib> Element for Cryptography Settings</span></span>
<span data-ttu-id="10f93-103">包含[\<g s > 元素](cryptographysettings-element.md)。</span><span class="sxs-lookup"><span data-stu-id="10f93-103">Contains the [\<cryptographySettings> element](cryptographysettings-element.md).</span></span>  
  
[<span data-ttu-id="10f93-104"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="10f93-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="10f93-105">&nbsp;&nbsp; **\<mscorlib >**</span><span class="sxs-lookup"><span data-stu-id="10f93-105">&nbsp;&nbsp;**\<mscorlib>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="10f93-106">语法</span><span class="sxs-lookup"><span data-stu-id="10f93-106">Syntax</span></span>  
  
```xml  
      <mscorlib>   
</mscorlib>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="10f93-107">属性和元素</span><span class="sxs-lookup"><span data-stu-id="10f93-107">Attributes and Elements</span></span>  
 <span data-ttu-id="10f93-108">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="10f93-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="10f93-109">Attributes</span><span class="sxs-lookup"><span data-stu-id="10f93-109">Attributes</span></span>  
 <span data-ttu-id="10f93-110">无。</span><span class="sxs-lookup"><span data-stu-id="10f93-110">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="10f93-111">子元素</span><span class="sxs-lookup"><span data-stu-id="10f93-111">Child Elements</span></span>  
  
|<span data-ttu-id="10f93-112">元素</span><span class="sxs-lookup"><span data-stu-id="10f93-112">Element</span></span>|<span data-ttu-id="10f93-113">说明</span><span class="sxs-lookup"><span data-stu-id="10f93-113">Description</span></span>|  
|-------------|-----------------|  
|`cryptographySettings`|<span data-ttu-id="10f93-114">包含加密设置。</span><span class="sxs-lookup"><span data-stu-id="10f93-114">Contains cryptography settings.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="10f93-115">父元素</span><span class="sxs-lookup"><span data-stu-id="10f93-115">Parent Elements</span></span>  
  
|<span data-ttu-id="10f93-116">元素</span><span class="sxs-lookup"><span data-stu-id="10f93-116">Element</span></span>|<span data-ttu-id="10f93-117">说明</span><span class="sxs-lookup"><span data-stu-id="10f93-117">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="10f93-118">公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。</span><span class="sxs-lookup"><span data-stu-id="10f93-118">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="10f93-119">示例</span><span class="sxs-lookup"><span data-stu-id="10f93-119">Example</span></span>  
 <span data-ttu-id="10f93-120">下面的示例演示如何使用 **\<mscorlib >** 元素来引用加密类并配置运行时。</span><span class="sxs-lookup"><span data-stu-id="10f93-120">The following example shows how to use the **\<mscorlib>** element to reference a cryptography class and to configure the runtime.</span></span> <span data-ttu-id="10f93-121">然后，你可以将字符串 "RSA" 传递到 <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> 方法，并使用 <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> 方法返回 `MyCryptoRSAClass` 对象。</span><span class="sxs-lookup"><span data-stu-id="10f93-121">You can then pass the string "RSA" to the <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> method and use the <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> method to return a `MyCryptoRSAClass` object.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="10f93-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="10f93-122">See also</span></span>

- <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A>
- <xref:System.Security.Cryptography>
- [<span data-ttu-id="10f93-123">配置文件架构</span><span class="sxs-lookup"><span data-stu-id="10f93-123">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="10f93-124">加密设置架构</span><span class="sxs-lookup"><span data-stu-id="10f93-124">Cryptography Settings Schema</span></span>](index.md)
- [<span data-ttu-id="10f93-125">加密服务</span><span class="sxs-lookup"><span data-stu-id="10f93-125">Cryptographic Services</span></span>](../../../../standard/security/cryptographic-services.md)
- [<span data-ttu-id="10f93-126">配置加密类</span><span class="sxs-lookup"><span data-stu-id="10f93-126">Configuring Cryptography Classes</span></span>](../../configure-cryptography-classes.md)
