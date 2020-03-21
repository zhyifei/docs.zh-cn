---
title: <compilers> 元素
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#compilers
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.codedom/compilers
helpviewer_keywords:
- compiler configuration elements, <compilers> element
- <compilers> element
- compilers element
ms.assetid: d40fba59-98f9-4783-ae0c-2ebea27ce77b
ms.openlocfilehash: 09b1efe321c39402c9280eda0e9def9112462470
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79155409"
---
# <a name="compilers-element"></a><span data-ttu-id="7e816-102">\<编译器>元素</span><span class="sxs-lookup"><span data-stu-id="7e816-102">\<compilers> Element</span></span>
<span data-ttu-id="7e816-103">用于编译器配置元素的容器;包含零个或多个[\<编译器>](compiler-element.md)元素。</span><span class="sxs-lookup"><span data-stu-id="7e816-103">Container for compiler configuration elements; contains zero or more [\<compiler>](compiler-element.md) elements.</span></span>  

<span data-ttu-id="7e816-104">[**\<配置>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="7e816-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="7e816-105">&nbsp;&nbsp;[**\<系统.代码>**](system-codedom-element.md)</span><span class="sxs-lookup"><span data-stu-id="7e816-105">&nbsp;&nbsp;[**\<system.codedom>**](system-codedom-element.md)</span></span>\
<span data-ttu-id="7e816-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<编译器>**</span><span class="sxs-lookup"><span data-stu-id="7e816-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<compilers>**</span></span>

## <a name="syntax"></a><span data-ttu-id="7e816-107">语法</span><span class="sxs-lookup"><span data-stu-id="7e816-107">Syntax</span></span>  
  
```xml  
<compilers>  
  <compiler ... />  
</compilers>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7e816-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="7e816-108">Attributes and Elements</span></span>  
 <span data-ttu-id="7e816-109">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="7e816-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7e816-110">属性</span><span class="sxs-lookup"><span data-stu-id="7e816-110">Attributes</span></span>  
 <span data-ttu-id="7e816-111">无。</span><span class="sxs-lookup"><span data-stu-id="7e816-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="7e816-112">子元素</span><span class="sxs-lookup"><span data-stu-id="7e816-112">Child Elements</span></span>  
  
|<span data-ttu-id="7e816-113">元素</span><span class="sxs-lookup"><span data-stu-id="7e816-113">Element</span></span>|<span data-ttu-id="7e816-114">说明</span><span class="sxs-lookup"><span data-stu-id="7e816-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7e816-115">\<编译器>元素</span><span class="sxs-lookup"><span data-stu-id="7e816-115">\<compiler> Element</span></span>](compiler-element.md)|<span data-ttu-id="7e816-116">指定语言提供程序的编译器配置属性。</span><span class="sxs-lookup"><span data-stu-id="7e816-116">Specifies the compiler configuration attributes for a language provider.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="7e816-117">父元素</span><span class="sxs-lookup"><span data-stu-id="7e816-117">Parent Elements</span></span>  
  
|<span data-ttu-id="7e816-118">元素</span><span class="sxs-lookup"><span data-stu-id="7e816-118">Element</span></span>|<span data-ttu-id="7e816-119">说明</span><span class="sxs-lookup"><span data-stu-id="7e816-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7e816-120">\<配置>元素</span><span class="sxs-lookup"><span data-stu-id="7e816-120">\<configuration> Element</span></span>](../configuration-element.md)|<span data-ttu-id="7e816-121">公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。</span><span class="sxs-lookup"><span data-stu-id="7e816-121">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|[<span data-ttu-id="7e816-122">\<系统.代码>元素</span><span class="sxs-lookup"><span data-stu-id="7e816-122">\<system.codedom> Element</span></span>](system-codedom-element.md)|<span data-ttu-id="7e816-123">指定可用语言提供程序的编译器配置设置。</span><span class="sxs-lookup"><span data-stu-id="7e816-123">Specifies compiler configuration settings for available language providers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7e816-124">备注</span><span class="sxs-lookup"><span data-stu-id="7e816-124">Remarks</span></span>  
 <span data-ttu-id="7e816-125">[ \<>元素的编译器](compilers-element.md)包含计算机上的语言提供程序的编译器配置设置。</span><span class="sxs-lookup"><span data-stu-id="7e816-125">The [\<compilers>](compilers-element.md) element contains the compiler configuration settings for language providers on a computer.</span></span> <span data-ttu-id="7e816-126">每个[\<编译器>](compiler-element.md)元素指定特定语言提供程序的编译器配置属性。</span><span class="sxs-lookup"><span data-stu-id="7e816-126">Each [\<compiler>](compiler-element.md) element specifies the compiler configuration attributes for a specific language provider.</span></span>  
  
 <span data-ttu-id="7e816-127">.NET 框架定义计算机配置文件 （Machine.config） 中的初始编译器和语言提供程序设置。</span><span class="sxs-lookup"><span data-stu-id="7e816-127">The .NET Framework defines the initial compiler and language provider settings in the machine configuration file (Machine.config).</span></span> <span data-ttu-id="7e816-128">开发人员和编译器供应商可以添加新 <xref:System.CodeDom.Compiler.CodeDomProvider?displayProperty=nameWithType> 实现的配置设置。</span><span class="sxs-lookup"><span data-stu-id="7e816-128">Developers and compiler vendors can add configuration settings for a new <xref:System.CodeDom.Compiler.CodeDomProvider?displayProperty=nameWithType> implementation.</span></span> <span data-ttu-id="7e816-129">使用 <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A?displayProperty=nameWithType> 方法，以编程方式枚举计算机上的语言提供程序和编译器配置设置。</span><span class="sxs-lookup"><span data-stu-id="7e816-129">Use the <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A?displayProperty=nameWithType> method to programmatically enumerate language provider and compiler configuration settings on a computer.</span></span>  
  
## <a name="configuration-file"></a><span data-ttu-id="7e816-130">配置文件</span><span class="sxs-lookup"><span data-stu-id="7e816-130">Configuration File</span></span>  
 <span data-ttu-id="7e816-131">此元素可用于计算机配置文件和应用程序配置文件。</span><span class="sxs-lookup"><span data-stu-id="7e816-131">This element can be used in the machine configuration file and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7e816-132">示例</span><span class="sxs-lookup"><span data-stu-id="7e816-132">Example</span></span>  
 <span data-ttu-id="7e816-133">以下示例说明典型的编译器配置元素。</span><span class="sxs-lookup"><span data-stu-id="7e816-133">The following example illustrates a typical compiler configuration element.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="7e816-134">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7e816-134">See also</span></span>

- <xref:System.CodeDom.Compiler.CompilerInfo>
- <xref:System.CodeDom.Compiler.CodeDomProvider>
- [<span data-ttu-id="7e816-135">配置文件架构</span><span class="sxs-lookup"><span data-stu-id="7e816-135">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="7e816-136">编译器和语言提供程序设置架构</span><span class="sxs-lookup"><span data-stu-id="7e816-136">Compiler and Language Provider Settings Schema</span></span>](index.md)
- [<span data-ttu-id="7e816-137">\<编译器>元素</span><span class="sxs-lookup"><span data-stu-id="7e816-137">\<compiler> Element</span></span>](compiler-element.md)
