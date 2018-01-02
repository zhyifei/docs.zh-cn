---
title: "&lt;mscorlib&gt;加密设置的元素"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#mscorlib
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/mscorlib
helpviewer_keywords:
- mscorlib element
- <mscorlib> element
ms.assetid: d549668f-31f1-4b92-8021-a9135c09ca3c
caps.latest.revision: "13"
author: mcleblanc
ms.author: markl
manager: markl
ms.workload: dotnet
ms.openlocfilehash: 18948d538b01304e90cac3b36988ccf29a586da0
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="ltmscorlibgt-element-for-cryptography-settings"></a><span data-ttu-id="ca989-102">&lt;mscorlib&gt;加密设置的元素</span><span class="sxs-lookup"><span data-stu-id="ca989-102">&lt;mscorlib&gt; Element for Cryptography Settings</span></span>
<span data-ttu-id="ca989-103">包含[ \<g s > 元素](../../../../../docs/framework/configure-apps/file-schema/cryptography/cryptographysettings-element.md)。</span><span class="sxs-lookup"><span data-stu-id="ca989-103">Contains the [\<cryptographySettings> element](../../../../../docs/framework/configure-apps/file-schema/cryptography/cryptographysettings-element.md).</span></span>  
  
 <span data-ttu-id="ca989-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="ca989-104">\<configuration></span></span>  
<span data-ttu-id="ca989-105">\<mscorlib ></span><span class="sxs-lookup"><span data-stu-id="ca989-105">\<mscorlib></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ca989-106">语法</span><span class="sxs-lookup"><span data-stu-id="ca989-106">Syntax</span></span>  
  
```xml  
      <mscorlib>   
</mscorlib>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ca989-107">特性和元素</span><span class="sxs-lookup"><span data-stu-id="ca989-107">Attributes and Elements</span></span>  
 <span data-ttu-id="ca989-108">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="ca989-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ca989-109">特性</span><span class="sxs-lookup"><span data-stu-id="ca989-109">Attributes</span></span>  
 <span data-ttu-id="ca989-110">无。</span><span class="sxs-lookup"><span data-stu-id="ca989-110">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="ca989-111">子元素</span><span class="sxs-lookup"><span data-stu-id="ca989-111">Child Elements</span></span>  
  
|<span data-ttu-id="ca989-112">元素</span><span class="sxs-lookup"><span data-stu-id="ca989-112">Element</span></span>|<span data-ttu-id="ca989-113">描述</span><span class="sxs-lookup"><span data-stu-id="ca989-113">Description</span></span>|  
|-------------|-----------------|  
|`cryptographySettings`|<span data-ttu-id="ca989-114">包含加密设置。</span><span class="sxs-lookup"><span data-stu-id="ca989-114">Contains cryptography settings.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="ca989-115">父元素</span><span class="sxs-lookup"><span data-stu-id="ca989-115">Parent Elements</span></span>  
  
|<span data-ttu-id="ca989-116">元素</span><span class="sxs-lookup"><span data-stu-id="ca989-116">Element</span></span>|<span data-ttu-id="ca989-117">说明</span><span class="sxs-lookup"><span data-stu-id="ca989-117">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="ca989-118">公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。</span><span class="sxs-lookup"><span data-stu-id="ca989-118">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="ca989-119">示例</span><span class="sxs-lookup"><span data-stu-id="ca989-119">Example</span></span>  
 <span data-ttu-id="ca989-120">下面的示例演示如何使用 **\<mscorlib >**元素来引用密码类并配置运行时。</span><span class="sxs-lookup"><span data-stu-id="ca989-120">The following example shows how to use the **\<mscorlib>** element to reference a cryptography class and to configure the runtime.</span></span> <span data-ttu-id="ca989-121">然后，你可以将字符串"RSA"传递到<xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType>方法并使用<xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A>方法以返回`MyCryptoRSAClass`对象。</span><span class="sxs-lookup"><span data-stu-id="ca989-121">You can then pass the string "RSA" to the <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> method and use the <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> method to return a `MyCryptoRSAClass` object.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="ca989-122">请参阅</span><span class="sxs-lookup"><span data-stu-id="ca989-122">See Also</span></span>  
 <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A>  
 <xref:System.Security.Cryptography>  
 [<span data-ttu-id="ca989-123">配置文件架构</span><span class="sxs-lookup"><span data-stu-id="ca989-123">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [<span data-ttu-id="ca989-124">加密设置架构</span><span class="sxs-lookup"><span data-stu-id="ca989-124">Cryptography Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/cryptography/index.md)  
 [<span data-ttu-id="ca989-125">加密服务</span><span class="sxs-lookup"><span data-stu-id="ca989-125">Cryptographic Services</span></span>](../../../../../docs/standard/security/cryptographic-services.md)  
 [<span data-ttu-id="ca989-126">配置加密类</span><span class="sxs-lookup"><span data-stu-id="ca989-126">Configuring Cryptography Classes</span></span>](../../../../../docs/framework/configure-apps/configure-cryptography-classes.md)
