---
title: <disableCachingBindingFailures> 元素
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#disableCachingBindingFailures
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/disableCachingBindingFailures
helpviewer_keywords:
- assemblies [.NET Framework],caching binding failures
- caching assembly binding failures
- <disableCachingBindingFailures> element
- disableCachingBindingFailures element
ms.assetid: bf598873-83b7-48de-8955-00b0504fbad0
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c99eb6b77a969a1c5003743b0407821e2537b683
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/30/2019
ms.locfileid: "55289713"
---
# <a name="disablecachingbindingfailures-element"></a><span data-ttu-id="d10d0-102">\<disableCachingBindingFailures > 元素</span><span class="sxs-lookup"><span data-stu-id="d10d0-102">\<disableCachingBindingFailures> Element</span></span>
<span data-ttu-id="d10d0-103">指定是否禁用缓存绑定故障的原因是通过探测找不到程序集。</span><span class="sxs-lookup"><span data-stu-id="d10d0-103">Specifies whether to disable the caching of binding failures that occur because the assembly was not found by probing.</span></span>  
  
 <span data-ttu-id="d10d0-104">\<配置 > 元素</span><span class="sxs-lookup"><span data-stu-id="d10d0-104">\<configuration> Element</span></span>  
<span data-ttu-id="d10d0-105">\<运行时 > 元素</span><span class="sxs-lookup"><span data-stu-id="d10d0-105">\<runtime> Element</span></span>  
<span data-ttu-id="d10d0-106">\<disableCachingBindingFailures></span><span class="sxs-lookup"><span data-stu-id="d10d0-106">\<disableCachingBindingFailures></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d10d0-107">语法</span><span class="sxs-lookup"><span data-stu-id="d10d0-107">Syntax</span></span>  
  
```xml  
<disableCachingBindingFailures enabled="0|1"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d10d0-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="d10d0-108">Attributes and Elements</span></span>  
 <span data-ttu-id="d10d0-109">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="d10d0-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d10d0-110">特性</span><span class="sxs-lookup"><span data-stu-id="d10d0-110">Attributes</span></span>  
  
|<span data-ttu-id="d10d0-111">特性</span><span class="sxs-lookup"><span data-stu-id="d10d0-111">Attribute</span></span>|<span data-ttu-id="d10d0-112">描述</span><span class="sxs-lookup"><span data-stu-id="d10d0-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="d10d0-113">enabled</span><span class="sxs-lookup"><span data-stu-id="d10d0-113">enabled</span></span>|<span data-ttu-id="d10d0-114">必需的特性。</span><span class="sxs-lookup"><span data-stu-id="d10d0-114">Required attribute.</span></span><br /><br /> <span data-ttu-id="d10d0-115">指定是否禁用缓存绑定故障的原因是通过探测找不到程序集。</span><span class="sxs-lookup"><span data-stu-id="d10d0-115">Specifies whether to disable the caching of binding failures that occur because the assembly was not found by probing.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="d10d0-116">enabled 特性</span><span class="sxs-lookup"><span data-stu-id="d10d0-116">enabled Attribute</span></span>  
  
|<span data-ttu-id="d10d0-117">值</span><span class="sxs-lookup"><span data-stu-id="d10d0-117">Value</span></span>|<span data-ttu-id="d10d0-118">描述</span><span class="sxs-lookup"><span data-stu-id="d10d0-118">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="d10d0-119">0</span><span class="sxs-lookup"><span data-stu-id="d10d0-119">0</span></span>|<span data-ttu-id="d10d0-120">不要禁用绑定失败的原因是通过探测找不到程序集缓存。</span><span class="sxs-lookup"><span data-stu-id="d10d0-120">Do not disable the caching of binding failures that occur because the assembly was not found by probing.</span></span> <span data-ttu-id="d10d0-121">这是从.NET Framework 2.0 版的默认绑定行为。</span><span class="sxs-lookup"><span data-stu-id="d10d0-121">This is the default binding behavior starting with the .NET Framework version 2.0.</span></span>|  
|<span data-ttu-id="d10d0-122">1</span><span class="sxs-lookup"><span data-stu-id="d10d0-122">1</span></span>|<span data-ttu-id="d10d0-123">禁用的绑定失败的原因是通过探测找不到程序集缓存。</span><span class="sxs-lookup"><span data-stu-id="d10d0-123">Disable the caching of binding failures that occur because the assembly was not found by probing.</span></span> <span data-ttu-id="d10d0-124">此设置将恢复为.NET Framework 1.1 版的绑定行为。</span><span class="sxs-lookup"><span data-stu-id="d10d0-124">This setting reverts to the binding behavior of the .NET Framework version 1.1.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d10d0-125">子元素</span><span class="sxs-lookup"><span data-stu-id="d10d0-125">Child Elements</span></span>  
 <span data-ttu-id="d10d0-126">无。</span><span class="sxs-lookup"><span data-stu-id="d10d0-126">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="d10d0-127">父元素</span><span class="sxs-lookup"><span data-stu-id="d10d0-127">Parent Elements</span></span>  
  
|<span data-ttu-id="d10d0-128">元素</span><span class="sxs-lookup"><span data-stu-id="d10d0-128">Element</span></span>|<span data-ttu-id="d10d0-129">描述</span><span class="sxs-lookup"><span data-stu-id="d10d0-129">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="d10d0-130">公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。</span><span class="sxs-lookup"><span data-stu-id="d10d0-130">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="d10d0-131">包含有关程序集绑定和垃圾回收的信息。</span><span class="sxs-lookup"><span data-stu-id="d10d0-131">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d10d0-132">备注</span><span class="sxs-lookup"><span data-stu-id="d10d0-132">Remarks</span></span>  
 <span data-ttu-id="d10d0-133">从.NET Framework 2.0 版开始，加载程序集的默认行为是缓存所有绑定和加载失败。</span><span class="sxs-lookup"><span data-stu-id="d10d0-133">Starting with the .NET Framework version 2.0, the default behavior for loading assemblies is to cache all binding and loading failures.</span></span> <span data-ttu-id="d10d0-134">即，如果尝试加载程序集失败，后续请求同一程序集加载立即失败，而无需任何尝试查找程序集。</span><span class="sxs-lookup"><span data-stu-id="d10d0-134">That is, if an attempt to load an assembly fails, subsequent requests to load the same assembly fail immediately, without any attempt to locate the assembly.</span></span> <span data-ttu-id="d10d0-135">此元素将禁用绑定失败的原因是探测路径中找不到程序集的默认行为。</span><span class="sxs-lookup"><span data-stu-id="d10d0-135">This element disables that default behavior for binding failures that occur because the assembly could not be found in the probing path.</span></span> <span data-ttu-id="d10d0-136">这些失败引发<xref:System.IO.FileNotFoundException>。</span><span class="sxs-lookup"><span data-stu-id="d10d0-136">These failures throw <xref:System.IO.FileNotFoundException>.</span></span>  
  
 <span data-ttu-id="d10d0-137">一些绑定和加载失败不受此元素，并始终进行缓存。</span><span class="sxs-lookup"><span data-stu-id="d10d0-137">Some binding and loading failures are not affected by this element, and are always cached.</span></span> <span data-ttu-id="d10d0-138">这些失败原因是该程序集已找到，但无法加载。</span><span class="sxs-lookup"><span data-stu-id="d10d0-138">These failures occur because the assembly was found but could not be loaded.</span></span> <span data-ttu-id="d10d0-139">它们将引发<xref:System.BadImageFormatException>或<xref:System.IO.FileLoadException>。</span><span class="sxs-lookup"><span data-stu-id="d10d0-139">They throw <xref:System.BadImageFormatException> or <xref:System.IO.FileLoadException>.</span></span> <span data-ttu-id="d10d0-140">以下列表包含此类故障的一些示例。</span><span class="sxs-lookup"><span data-stu-id="d10d0-140">The following list includes some examples of such failures.</span></span>  
  
-   <span data-ttu-id="d10d0-141">如果你尝试加载文件不是有效的程序集，即使错误的文件将被替换为正确的程序集加载程序集的后续尝试将失败。</span><span class="sxs-lookup"><span data-stu-id="d10d0-141">If you attempt to load a file is not a valid assembly, subsequent attempts to load the assembly will fail even if the bad file is replaced with the correct assembly.</span></span>  
  
-   <span data-ttu-id="d10d0-142">如果尝试加载已锁定的文件系统程序集，加载程序集的后续尝试将失败，即使文件系统发布程序集。</span><span class="sxs-lookup"><span data-stu-id="d10d0-142">If you attempt to load an assembly that is locked by the file system, subsequent attempts to load the assembly will fail even after the assembly is released by the file system.</span></span>  
  
-   <span data-ttu-id="d10d0-143">如果尝试加载的程序集的一个或多个版本位于探测路径中，但在它们之间的不是你请求的特定版本，加载该版本的后续尝试将失败，即使正确的版本将移到探测路径。</span><span class="sxs-lookup"><span data-stu-id="d10d0-143">If one or more versions of the assembly that you are attempting to load is in the probing path, but the specific version you are requesting is not among them, subsequent attempts to load that version will fail even if the correct version is moved into the probing path.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d10d0-144">示例</span><span class="sxs-lookup"><span data-stu-id="d10d0-144">Example</span></span>  
 <span data-ttu-id="d10d0-145">下面的示例演示如何禁用的原因是通过探测找不到程序集的程序集绑定故障缓存。</span><span class="sxs-lookup"><span data-stu-id="d10d0-145">The following example shows how to disable the caching of assembly binding failures that occur because the assembly was not found by probing.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <disableCachingBindingFailures enabled="1" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="d10d0-146">请参阅</span><span class="sxs-lookup"><span data-stu-id="d10d0-146">See also</span></span>
- [<span data-ttu-id="d10d0-147">运行时设置架构</span><span class="sxs-lookup"><span data-stu-id="d10d0-147">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)
- [<span data-ttu-id="d10d0-148">配置文件架构</span><span class="sxs-lookup"><span data-stu-id="d10d0-148">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)
- [<span data-ttu-id="d10d0-149">运行时如何定位程序集</span><span class="sxs-lookup"><span data-stu-id="d10d0-149">How the Runtime Locates Assemblies</span></span>](../../../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)
