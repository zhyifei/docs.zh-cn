---
title: "&lt;编译器&gt;元素"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#compilers
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.codedom/compilers
helpviewer_keywords:
- compiler configuration elements, <compilers> element
- <compilers> element
- compilers element
ms.assetid: d40fba59-98f9-4783-ae0c-2ebea27ce77b
caps.latest.revision: "14"
author: mcleblanc
ms.author: markl
manager: markl
ms.workload: dotnet
ms.openlocfilehash: deb9f99253c4cf523c8fe5052b1f30823e5e9944
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="ltcompilersgt-element"></a><span data-ttu-id="1ff2b-102">&lt;编译器&gt;元素</span><span class="sxs-lookup"><span data-stu-id="1ff2b-102">&lt;compilers&gt; Element</span></span>
<span data-ttu-id="1ff2b-103">编译器配置元素的容器；包含零个或多个 [\<compiler>](../../../../../docs/framework/configure-apps/file-schema/compiler/compiler-element.md) 元素。</span><span class="sxs-lookup"><span data-stu-id="1ff2b-103">Container for compiler configuration elements; contains zero or more [\<compiler>](../../../../../docs/framework/configure-apps/file-schema/compiler/compiler-element.md) elements.</span></span>  
  
 <span data-ttu-id="1ff2b-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="1ff2b-104">\<configuration></span></span>  
<span data-ttu-id="1ff2b-105">\<system.codedom ></span><span class="sxs-lookup"><span data-stu-id="1ff2b-105">\<system.codedom></span></span>  
<span data-ttu-id="1ff2b-106">\<编译器 > 元素</span><span class="sxs-lookup"><span data-stu-id="1ff2b-106">\<compilers> Element</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1ff2b-107">语法</span><span class="sxs-lookup"><span data-stu-id="1ff2b-107">Syntax</span></span>  
  
```xml  
<compilers>  
  <compiler ... />  
</compilers>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1ff2b-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="1ff2b-108">Attributes and Elements</span></span>  
 <span data-ttu-id="1ff2b-109">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="1ff2b-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1ff2b-110">特性</span><span class="sxs-lookup"><span data-stu-id="1ff2b-110">Attributes</span></span>  
 <span data-ttu-id="1ff2b-111">无。</span><span class="sxs-lookup"><span data-stu-id="1ff2b-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="1ff2b-112">子元素</span><span class="sxs-lookup"><span data-stu-id="1ff2b-112">Child Elements</span></span>  
  
|<span data-ttu-id="1ff2b-113">元素</span><span class="sxs-lookup"><span data-stu-id="1ff2b-113">Element</span></span>|<span data-ttu-id="1ff2b-114">描述</span><span class="sxs-lookup"><span data-stu-id="1ff2b-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1ff2b-115">\<compiler> Element</span><span class="sxs-lookup"><span data-stu-id="1ff2b-115">\<compiler> Element</span></span>](../../../../../docs/framework/configure-apps/file-schema/compiler/compiler-element.md)|<span data-ttu-id="1ff2b-116">指定语言提供程序的编译器配置属性。</span><span class="sxs-lookup"><span data-stu-id="1ff2b-116">Specifies the compiler configuration attributes for a language provider.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="1ff2b-117">父元素</span><span class="sxs-lookup"><span data-stu-id="1ff2b-117">Parent Elements</span></span>  
  
|<span data-ttu-id="1ff2b-118">元素</span><span class="sxs-lookup"><span data-stu-id="1ff2b-118">Element</span></span>|<span data-ttu-id="1ff2b-119">描述</span><span class="sxs-lookup"><span data-stu-id="1ff2b-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1ff2b-120">\<configuration> 元素</span><span class="sxs-lookup"><span data-stu-id="1ff2b-120">\<configuration> Element</span></span>](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)|<span data-ttu-id="1ff2b-121">公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。</span><span class="sxs-lookup"><span data-stu-id="1ff2b-121">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|[<span data-ttu-id="1ff2b-122">\<system.codedom > 元素</span><span class="sxs-lookup"><span data-stu-id="1ff2b-122">\<system.codedom> Element</span></span>](../../../../../docs/framework/configure-apps/file-schema/compiler/system-codedom-element.md)|<span data-ttu-id="1ff2b-123">指定可用语言提供程序的编译器配置设置。</span><span class="sxs-lookup"><span data-stu-id="1ff2b-123">Specifies compiler configuration settings for available language providers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1ff2b-124">备注</span><span class="sxs-lookup"><span data-stu-id="1ff2b-124">Remarks</span></span>  
 <span data-ttu-id="1ff2b-125">[\<编译器 >](../../../../../docs/framework/configure-apps/file-schema/compiler/compilers-element.md)元素包含的计算机上的语言提供程序的编译器配置设置。</span><span class="sxs-lookup"><span data-stu-id="1ff2b-125">The [\<compilers>](../../../../../docs/framework/configure-apps/file-schema/compiler/compilers-element.md) element contains the compiler configuration settings for language providers on a computer.</span></span> <span data-ttu-id="1ff2b-126">每个[\<编译器 >](../../../../../docs/framework/configure-apps/file-schema/compiler/compiler-element.md)元素指定特定的语言提供程序的编译器配置特性。</span><span class="sxs-lookup"><span data-stu-id="1ff2b-126">Each [\<compiler>](../../../../../docs/framework/configure-apps/file-schema/compiler/compiler-element.md) element specifies the compiler configuration attributes for a specific language provider.</span></span>  
  
 <span data-ttu-id="1ff2b-127">.NET Framework 在计算机配置文件 (Machine.config) 中定义的初始编译器和语言提供程序设置。</span><span class="sxs-lookup"><span data-stu-id="1ff2b-127">The .NET Framework defines the initial compiler and language provider settings in the machine configuration file (Machine.config).</span></span> <span data-ttu-id="1ff2b-128">开发人员和编译器供应商可以添加新 <xref:System.CodeDom.Compiler.CodeDomProvider?displayProperty=nameWithType> 实现的配置设置。</span><span class="sxs-lookup"><span data-stu-id="1ff2b-128">Developers and compiler vendors can add configuration settings for a new <xref:System.CodeDom.Compiler.CodeDomProvider?displayProperty=nameWithType> implementation.</span></span> <span data-ttu-id="1ff2b-129">使用 <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A?displayProperty=nameWithType> 方法，以编程方式枚举计算机上的语言提供程序和编译器配置设置。</span><span class="sxs-lookup"><span data-stu-id="1ff2b-129">Use the <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A?displayProperty=nameWithType> method to programmatically enumerate language provider and compiler configuration settings on a computer.</span></span>  
  
## <a name="configuration-file"></a><span data-ttu-id="1ff2b-130">配置文件</span><span class="sxs-lookup"><span data-stu-id="1ff2b-130">Configuration File</span></span>  
 <span data-ttu-id="1ff2b-131">计算机配置文件和应用程序配置文件中，可以使用此元素。</span><span class="sxs-lookup"><span data-stu-id="1ff2b-131">This element can be used in the machine configuration file and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1ff2b-132">示例</span><span class="sxs-lookup"><span data-stu-id="1ff2b-132">Example</span></span>  
 <span data-ttu-id="1ff2b-133">以下示例说明典型的编译器配置元素。</span><span class="sxs-lookup"><span data-stu-id="1ff2b-133">The following example illustrates a typical compiler configuration element.</span></span>  
  
```xml  
<configuration>  
   <system.codedom>  
     <compilers>  
       <!-- zero or more compiler elements -->  
       <compiler   
          language="c#;cs;csharp"   
          extension=".cs"  
          type="Microsoft.CSharp.CSharpCodeProvider, System, Version=1.0.5000.0, Culture=neutral, PublicKeyToken=b77a5c561934e089"  
          compilerOptions=""    
          warningLevel="1" />  
     </compilers>  
   </system.codedom>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="1ff2b-134">请参阅</span><span class="sxs-lookup"><span data-stu-id="1ff2b-134">See Also</span></span>  
 <xref:System.CodeDom.Compiler.CompilerInfo>  
 <xref:System.CodeDom.Compiler.CodeDomProvider>  
 [<span data-ttu-id="1ff2b-135">配置文件架构</span><span class="sxs-lookup"><span data-stu-id="1ff2b-135">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [<span data-ttu-id="1ff2b-136">编译器和语言提供程序设置架构</span><span class="sxs-lookup"><span data-stu-id="1ff2b-136">Compiler and Language Provider Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/compiler/index.md)  
 [<span data-ttu-id="1ff2b-137">\<compiler> Element</span><span class="sxs-lookup"><span data-stu-id="1ff2b-137">\<compiler> Element</span></span>](../../../../../docs/framework/configure-apps/file-schema/compiler/compiler-element.md)
