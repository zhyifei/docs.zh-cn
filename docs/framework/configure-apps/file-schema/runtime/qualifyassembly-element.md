---
title: <qualifyAssembly> 元素
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#qualifyAssembly
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/assemblyBinding/qualifyAssembly
helpviewer_keywords:
- container tags, <qualifyAssembly> element
- <qualifyAssembly> element
- qualifyAssembly element
ms.assetid: ad6442f6-1a9d-43b6-b733-04ac1b7f9b82
ms.openlocfilehash: 74e83900c68ab4b3fe01beb3f97657b0140d78ad
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79153914"
---
# <a name="qualifyassembly-element"></a><span data-ttu-id="f68b7-102">\<限定装配>元素</span><span class="sxs-lookup"><span data-stu-id="f68b7-102">\<qualifyAssembly> Element</span></span>
<span data-ttu-id="f68b7-103">指定使用部分名称时应动态加载的程序集全名。</span><span class="sxs-lookup"><span data-stu-id="f68b7-103">Specifies the full name of the assembly that should be dynamically loaded when a partial name is used.</span></span>  
  
<span data-ttu-id="f68b7-104">[**\<配置>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="f68b7-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="f68b7-105">&nbsp;&nbsp;[**\<运行时>**](runtime-element.md)</span><span class="sxs-lookup"><span data-stu-id="f68b7-105">&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)</span></span>\
<span data-ttu-id="f68b7-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<程序集绑定>**](assemblybinding-element-for-runtime.md)</span><span class="sxs-lookup"><span data-stu-id="f68b7-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<assemblyBinding>**](assemblybinding-element-for-runtime.md)</span></span>\
<span data-ttu-id="f68b7-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<符合条件>**</span><span class="sxs-lookup"><span data-stu-id="f68b7-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<qualifyAssembly>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f68b7-108">语法</span><span class="sxs-lookup"><span data-stu-id="f68b7-108">Syntax</span></span>  
  
```xml  
      <qualifyAssembly partialName=  
      "PartialAssemblyName"  
                 fullName="FullAssemblyName"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f68b7-109">特性和元素</span><span class="sxs-lookup"><span data-stu-id="f68b7-109">Attributes and Elements</span></span>  
 <span data-ttu-id="f68b7-110">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="f68b7-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f68b7-111">属性</span><span class="sxs-lookup"><span data-stu-id="f68b7-111">Attributes</span></span>  
  
|<span data-ttu-id="f68b7-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="f68b7-112">Attribute</span></span>|<span data-ttu-id="f68b7-113">说明</span><span class="sxs-lookup"><span data-stu-id="f68b7-113">Description</span></span>|  
|---------------|-----------------|  
|`partialName`|<span data-ttu-id="f68b7-114">必需的特性。</span><span class="sxs-lookup"><span data-stu-id="f68b7-114">Required attribute.</span></span><br /><br /> <span data-ttu-id="f68b7-115">指定程序集的部分名称，因为它出现在代码中。</span><span class="sxs-lookup"><span data-stu-id="f68b7-115">Specifies the partial name of the assembly as it appears in the code.</span></span>|  
|`fullName`|<span data-ttu-id="f68b7-116">必需的特性。</span><span class="sxs-lookup"><span data-stu-id="f68b7-116">Required attribute.</span></span><br /><br /> <span data-ttu-id="f68b7-117">指定程序集的全名，因为它出现在全局程序集缓存中。</span><span class="sxs-lookup"><span data-stu-id="f68b7-117">Specifies the full name of the assembly as it appears in the global assembly cache.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f68b7-118">子元素</span><span class="sxs-lookup"><span data-stu-id="f68b7-118">Child Elements</span></span>  
 <span data-ttu-id="f68b7-119">无。</span><span class="sxs-lookup"><span data-stu-id="f68b7-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="f68b7-120">父元素</span><span class="sxs-lookup"><span data-stu-id="f68b7-120">Parent Elements</span></span>  
  
|<span data-ttu-id="f68b7-121">元素</span><span class="sxs-lookup"><span data-stu-id="f68b7-121">Element</span></span>|<span data-ttu-id="f68b7-122">说明</span><span class="sxs-lookup"><span data-stu-id="f68b7-122">Description</span></span>|  
|-------------|-----------------|  
|`assemblyBinding`|<span data-ttu-id="f68b7-123">包含有关程序集版本重定向和程序集位置的信息。</span><span class="sxs-lookup"><span data-stu-id="f68b7-123">Contains information about assembly version redirection and the locations of assemblies.</span></span>|  
|`configuration`|<span data-ttu-id="f68b7-124">公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。</span><span class="sxs-lookup"><span data-stu-id="f68b7-124">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="f68b7-125">包含有关程序集绑定和垃圾回收的信息。</span><span class="sxs-lookup"><span data-stu-id="f68b7-125">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f68b7-126">备注</span><span class="sxs-lookup"><span data-stu-id="f68b7-126">Remarks</span></span>  
 <span data-ttu-id="f68b7-127">使用部分<xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType>程序集名称调用 方法会导致公共语言运行时仅在应用程序基目录中查找程序集。</span><span class="sxs-lookup"><span data-stu-id="f68b7-127">Calling the <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType> method using partial assembly names causes the common language runtime to look for the assembly only in the application base directory.</span></span> <span data-ttu-id="f68b7-128">使用应用程序配置文件中的**\<限定程序集>** 元素提供完整的程序集信息（名称、版本、公钥令牌和区域性），并导致通用语言运行时在全局程序集缓存中搜索程序集。</span><span class="sxs-lookup"><span data-stu-id="f68b7-128">Use the **\<qualifyAssembly>** element in your application configuration file to provide the full assembly information (name, version, public key token, and culture) and cause the common language runtime to search for the assembly in the global assembly cache.</span></span>  
  
 <span data-ttu-id="f68b7-129">**fullName**属性必须包括程序集标识的四个字段：名称、版本、公钥令牌和区域性。</span><span class="sxs-lookup"><span data-stu-id="f68b7-129">The **fullName** attribute must include the four fields of assembly identity: name, version, public key token, and culture.</span></span> <span data-ttu-id="f68b7-130">**部分名称**属性必须部分引用程序集。</span><span class="sxs-lookup"><span data-stu-id="f68b7-130">The **partialName** attribute must partially reference an assembly.</span></span> <span data-ttu-id="f68b7-131">必须至少指定程序集的文本名称（最常见的情况），但还可以包括版本、公钥令牌或区域性（或四者中的任何组合，但不是全部四个）。</span><span class="sxs-lookup"><span data-stu-id="f68b7-131">You must specify at least the assembly's text name (the most common case), but you can also include version, public key token, or culture (or any combination of the four, but not all four).</span></span> <span data-ttu-id="f68b7-132">**部分名称**必须与呼叫中指定的名称匹配。</span><span class="sxs-lookup"><span data-stu-id="f68b7-132">The **partialName** must match the name specified in your call.</span></span> <span data-ttu-id="f68b7-133">例如，您不能在配置文件中`"math"`指定为**部分Name**属性，并在代码中调用`Assembly.Load("math, Version=3.3.3.3")`。</span><span class="sxs-lookup"><span data-stu-id="f68b7-133">For example, you cannot specify `"math"` as the **partialName** attribute in your configuration file and call `Assembly.Load("math, Version=3.3.3.3")` in your code.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f68b7-134">示例</span><span class="sxs-lookup"><span data-stu-id="f68b7-134">Example</span></span>  
 <span data-ttu-id="f68b7-135">以下示例从逻辑上将调用`Assembly.Load("math")`转换为`Assembly.Load("math,version=1.0.0.0,publicKeyToken=a1690a5ea44bab32,culture=neutral")`。</span><span class="sxs-lookup"><span data-stu-id="f68b7-135">The following example logically turns the call `Assembly.Load("math")` into `Assembly.Load("math,version=1.0.0.0,publicKeyToken=a1690a5ea44bab32,culture=neutral")`.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
         <qualifyAssembly partialName="math"
                         fullName=  
"math,version=1.0.0.0,publicKeyToken=a1690a5ea44bab32,culture=neutral"/>  
      </assemblyBinding>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="f68b7-136">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f68b7-136">See also</span></span>

- [<span data-ttu-id="f68b7-137">运行时设置架构</span><span class="sxs-lookup"><span data-stu-id="f68b7-137">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="f68b7-138">运行时如何定位程序集</span><span class="sxs-lookup"><span data-stu-id="f68b7-138">How the Runtime Locates Assemblies</span></span>](../../../deployment/how-the-runtime-locates-assemblies.md)
- <span data-ttu-id="f68b7-139">[部分程序集引用](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/0a7zy9z5(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="f68b7-139">[Partial Assembly References](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/0a7zy9z5(v=vs.100))</span></span>
