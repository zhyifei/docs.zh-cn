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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ec72b1a1e3a2526dfb52f562be9fe92c677747ec
ms.sourcegitcommit: b8ace47d839f943f785b89e2fff8092b0bf8f565
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/03/2019
ms.locfileid: "55674667"
---
# <a name="qualifyassembly-element"></a><span data-ttu-id="50809-102">\<qualifyAssembly > 元素</span><span class="sxs-lookup"><span data-stu-id="50809-102">\<qualifyAssembly> Element</span></span>
<span data-ttu-id="50809-103">指定使用部分名称时应动态加载的程序集全名。</span><span class="sxs-lookup"><span data-stu-id="50809-103">Specifies the full name of the assembly that should be dynamically loaded when a partial name is used.</span></span>  
  
 <span data-ttu-id="50809-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="50809-104">\<configuration></span></span>  
<span data-ttu-id="50809-105">\<运行时 ></span><span class="sxs-lookup"><span data-stu-id="50809-105">\<runtime></span></span>  
<span data-ttu-id="50809-106">\<assemblyBinding></span><span class="sxs-lookup"><span data-stu-id="50809-106">\<assemblyBinding></span></span>  
<span data-ttu-id="50809-107">\<qualifyAssembly></span><span class="sxs-lookup"><span data-stu-id="50809-107">\<qualifyAssembly></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="50809-108">语法</span><span class="sxs-lookup"><span data-stu-id="50809-108">Syntax</span></span>  
  
```xml  
      <qualifyAssembly partialName=  
      "PartialAssemblyName"  
                 fullName="FullAssemblyName"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="50809-109">特性和元素</span><span class="sxs-lookup"><span data-stu-id="50809-109">Attributes and Elements</span></span>  
 <span data-ttu-id="50809-110">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="50809-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="50809-111">特性</span><span class="sxs-lookup"><span data-stu-id="50809-111">Attributes</span></span>  
  
|<span data-ttu-id="50809-112">特性</span><span class="sxs-lookup"><span data-stu-id="50809-112">Attribute</span></span>|<span data-ttu-id="50809-113">描述</span><span class="sxs-lookup"><span data-stu-id="50809-113">Description</span></span>|  
|---------------|-----------------|  
|`partialName`|<span data-ttu-id="50809-114">必需的特性。</span><span class="sxs-lookup"><span data-stu-id="50809-114">Required attribute.</span></span><br /><br /> <span data-ttu-id="50809-115">显示在代码中指定的程序集的部分名称。</span><span class="sxs-lookup"><span data-stu-id="50809-115">Specifies the partial name of the assembly as it appears in the code.</span></span>|  
|`fullName`|<span data-ttu-id="50809-116">必需的特性。</span><span class="sxs-lookup"><span data-stu-id="50809-116">Required attribute.</span></span><br /><br /> <span data-ttu-id="50809-117">显示在全局程序集缓存中指定的程序集的全名。</span><span class="sxs-lookup"><span data-stu-id="50809-117">Specifies the full name of the assembly as it appears in the global assembly cache.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="50809-118">子元素</span><span class="sxs-lookup"><span data-stu-id="50809-118">Child Elements</span></span>  
 <span data-ttu-id="50809-119">无。</span><span class="sxs-lookup"><span data-stu-id="50809-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="50809-120">父元素</span><span class="sxs-lookup"><span data-stu-id="50809-120">Parent Elements</span></span>  
  
|<span data-ttu-id="50809-121">元素</span><span class="sxs-lookup"><span data-stu-id="50809-121">Element</span></span>|<span data-ttu-id="50809-122">描述</span><span class="sxs-lookup"><span data-stu-id="50809-122">Description</span></span>|  
|-------------|-----------------|  
|`assemblyBinding`|<span data-ttu-id="50809-123">包含有关程序集版本重定向和程序集位置的信息。</span><span class="sxs-lookup"><span data-stu-id="50809-123">Contains information about assembly version redirection and the locations of assemblies.</span></span>|  
|`configuration`|<span data-ttu-id="50809-124">公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。</span><span class="sxs-lookup"><span data-stu-id="50809-124">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="50809-125">包含有关程序集绑定和垃圾回收的信息。</span><span class="sxs-lookup"><span data-stu-id="50809-125">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="50809-126">备注</span><span class="sxs-lookup"><span data-stu-id="50809-126">Remarks</span></span>  
 <span data-ttu-id="50809-127">调用<xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType>使用部分程序集名称的方法会导致公共语言运行时查找仅在应用程序基目录中的程序集。</span><span class="sxs-lookup"><span data-stu-id="50809-127">Calling the <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType> method using partial assembly names causes the common language runtime to look for the assembly only in the application base directory.</span></span> <span data-ttu-id="50809-128">使用 **\<qualifyAssembly >** 可提供完整的程序集信息 （名称、 版本、 公钥标记和区域性） 并且使公共语言运行时搜索应用程序配置文件中的元素有关全局程序集缓存中的程序集。</span><span class="sxs-lookup"><span data-stu-id="50809-128">Use the **\<qualifyAssembly>** element in your application configuration file to provide the full assembly information (name, version, public key token, and culture) and cause the common language runtime to search for the assembly in the global assembly cache.</span></span>  
  
 <span data-ttu-id="50809-129">**FullName**属性必须包含程序集标识的四个字段： 名称、 版本、 公钥标记和区域性。</span><span class="sxs-lookup"><span data-stu-id="50809-129">The **fullName** attribute must include the four fields of assembly identity: name, version, public key token, and culture.</span></span> <span data-ttu-id="50809-130">**PartialName**属性部分必须引用的程序集。</span><span class="sxs-lookup"><span data-stu-id="50809-130">The **partialName** attribute must partially reference an assembly.</span></span> <span data-ttu-id="50809-131">您必须至少指定程序集的文本名称 （最常见的情况），但您还可以包含版本、 公钥标记或区域性 （或四个，但并非所有四个的任意组合）。</span><span class="sxs-lookup"><span data-stu-id="50809-131">You must specify at least the assembly's text name (the most common case), but you can also include version, public key token, or culture (or any combination of the four, but not all four).</span></span> <span data-ttu-id="50809-132">**PartialName**的调用中指定的名称必须匹配。</span><span class="sxs-lookup"><span data-stu-id="50809-132">The **partialName** must match the name specified in your call.</span></span> <span data-ttu-id="50809-133">例如，不能指定`"math"`作为**partialName**属性中，配置文件并调用`Assembly.Load("math, Version=3.3.3.3")`在代码中。</span><span class="sxs-lookup"><span data-stu-id="50809-133">For example, you cannot specify `"math"` as the **partialName** attribute in your configuration file and call `Assembly.Load("math, Version=3.3.3.3")` in your code.</span></span>  
  
## <a name="example"></a><span data-ttu-id="50809-134">示例</span><span class="sxs-lookup"><span data-stu-id="50809-134">Example</span></span>  
 <span data-ttu-id="50809-135">下面的示例以逻辑方式调用变成`Assembly.Load("math")`到`Assembly.Load("math,version=1.0.0.0,publicKeyToken=a1690a5ea44bab32,culture=neutral")`。</span><span class="sxs-lookup"><span data-stu-id="50809-135">The following example logically turns the call `Assembly.Load("math")` into `Assembly.Load("math,version=1.0.0.0,publicKeyToken=a1690a5ea44bab32,culture=neutral")`.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="50809-136">请参阅</span><span class="sxs-lookup"><span data-stu-id="50809-136">See also</span></span>
- [<span data-ttu-id="50809-137">运行时设置架构</span><span class="sxs-lookup"><span data-stu-id="50809-137">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)
- [<span data-ttu-id="50809-138">运行时如何定位程序集</span><span class="sxs-lookup"><span data-stu-id="50809-138">How the Runtime Locates Assemblies</span></span>](../../../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)
- <span data-ttu-id="50809-139">[部分程序集引用](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/0a7zy9z5(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="50809-139">[Partial Assembly References](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/0a7zy9z5(v=vs.100))</span></span>
