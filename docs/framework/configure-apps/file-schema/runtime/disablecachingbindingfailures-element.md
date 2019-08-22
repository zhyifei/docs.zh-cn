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
ms.openlocfilehash: ba74907e2f6fc2ca14e12a24113fa7654c9b967e
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/21/2019
ms.locfileid: "69663803"
---
# <a name="disablecachingbindingfailures-element"></a><span data-ttu-id="e2f4c-102">\<disableCachingBindingFailures > 元素</span><span class="sxs-lookup"><span data-stu-id="e2f4c-102">\<disableCachingBindingFailures> Element</span></span>
<span data-ttu-id="e2f4c-103">指定是否禁止缓存发生的绑定故障, 因为探查找不到该程序集。</span><span class="sxs-lookup"><span data-stu-id="e2f4c-103">Specifies whether to disable the caching of binding failures that occur because the assembly was not found by probing.</span></span>  
  
 <span data-ttu-id="e2f4c-104">\<配置 > 元素</span><span class="sxs-lookup"><span data-stu-id="e2f4c-104">\<configuration> Element</span></span>  
<span data-ttu-id="e2f4c-105">\<运行时 > 元素</span><span class="sxs-lookup"><span data-stu-id="e2f4c-105">\<runtime> Element</span></span>  
<span data-ttu-id="e2f4c-106">\<disableCachingBindingFailures></span><span class="sxs-lookup"><span data-stu-id="e2f4c-106">\<disableCachingBindingFailures></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e2f4c-107">语法</span><span class="sxs-lookup"><span data-stu-id="e2f4c-107">Syntax</span></span>  
  
```xml  
<disableCachingBindingFailures enabled="0|1"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e2f4c-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="e2f4c-108">Attributes and Elements</span></span>  
 <span data-ttu-id="e2f4c-109">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="e2f4c-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e2f4c-110">特性</span><span class="sxs-lookup"><span data-stu-id="e2f4c-110">Attributes</span></span>  
  
|<span data-ttu-id="e2f4c-111">特性</span><span class="sxs-lookup"><span data-stu-id="e2f4c-111">Attribute</span></span>|<span data-ttu-id="e2f4c-112">描述</span><span class="sxs-lookup"><span data-stu-id="e2f4c-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="e2f4c-113">enabled</span><span class="sxs-lookup"><span data-stu-id="e2f4c-113">enabled</span></span>|<span data-ttu-id="e2f4c-114">必需的特性。</span><span class="sxs-lookup"><span data-stu-id="e2f4c-114">Required attribute.</span></span><br /><br /> <span data-ttu-id="e2f4c-115">指定是否禁止缓存发生的绑定故障, 因为探查找不到该程序集。</span><span class="sxs-lookup"><span data-stu-id="e2f4c-115">Specifies whether to disable the caching of binding failures that occur because the assembly was not found by probing.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="e2f4c-116">enabled 特性</span><span class="sxs-lookup"><span data-stu-id="e2f4c-116">enabled Attribute</span></span>  
  
|<span data-ttu-id="e2f4c-117">值</span><span class="sxs-lookup"><span data-stu-id="e2f4c-117">Value</span></span>|<span data-ttu-id="e2f4c-118">Description</span><span class="sxs-lookup"><span data-stu-id="e2f4c-118">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="e2f4c-119">0</span><span class="sxs-lookup"><span data-stu-id="e2f4c-119">0</span></span>|<span data-ttu-id="e2f4c-120">请勿禁止缓存发生的绑定故障, 因为探查找不到该程序集。</span><span class="sxs-lookup"><span data-stu-id="e2f4c-120">Do not disable the caching of binding failures that occur because the assembly was not found by probing.</span></span> <span data-ttu-id="e2f4c-121">这是默认绑定行为, 从 .NET Framework 版本2.0 开始。</span><span class="sxs-lookup"><span data-stu-id="e2f4c-121">This is the default binding behavior starting with the .NET Framework version 2.0.</span></span>|  
|<span data-ttu-id="e2f4c-122">1</span><span class="sxs-lookup"><span data-stu-id="e2f4c-122">1</span></span>|<span data-ttu-id="e2f4c-123">禁止缓存发生的绑定故障, 因为探查找不到该程序集。</span><span class="sxs-lookup"><span data-stu-id="e2f4c-123">Disable the caching of binding failures that occur because the assembly was not found by probing.</span></span> <span data-ttu-id="e2f4c-124">此设置将恢复为 .NET Framework 版本1.1 的绑定行为。</span><span class="sxs-lookup"><span data-stu-id="e2f4c-124">This setting reverts to the binding behavior of the .NET Framework version 1.1.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e2f4c-125">子元素</span><span class="sxs-lookup"><span data-stu-id="e2f4c-125">Child Elements</span></span>  
 <span data-ttu-id="e2f4c-126">无。</span><span class="sxs-lookup"><span data-stu-id="e2f4c-126">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e2f4c-127">父元素</span><span class="sxs-lookup"><span data-stu-id="e2f4c-127">Parent Elements</span></span>  
  
|<span data-ttu-id="e2f4c-128">元素</span><span class="sxs-lookup"><span data-stu-id="e2f4c-128">Element</span></span>|<span data-ttu-id="e2f4c-129">描述</span><span class="sxs-lookup"><span data-stu-id="e2f4c-129">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="e2f4c-130">公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。</span><span class="sxs-lookup"><span data-stu-id="e2f4c-130">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="e2f4c-131">包含有关程序集绑定和垃圾回收的信息。</span><span class="sxs-lookup"><span data-stu-id="e2f4c-131">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e2f4c-132">备注</span><span class="sxs-lookup"><span data-stu-id="e2f4c-132">Remarks</span></span>  
 <span data-ttu-id="e2f4c-133">从 .NET Framework 版本2.0 开始, 加载程序集的默认行为是缓存所有绑定和加载失败。</span><span class="sxs-lookup"><span data-stu-id="e2f4c-133">Starting with the .NET Framework version 2.0, the default behavior for loading assemblies is to cache all binding and loading failures.</span></span> <span data-ttu-id="e2f4c-134">也就是说, 如果尝试加载程序集失败, 则加载同一程序集的后续请求将立即失败, 而不会尝试查找程序集。</span><span class="sxs-lookup"><span data-stu-id="e2f4c-134">That is, if an attempt to load an assembly fails, subsequent requests to load the same assembly fail immediately, without any attempt to locate the assembly.</span></span> <span data-ttu-id="e2f4c-135">此元素将禁用发生的绑定故障的默认行为, 因为在探测路径中找不到该程序集。</span><span class="sxs-lookup"><span data-stu-id="e2f4c-135">This element disables that default behavior for binding failures that occur because the assembly could not be found in the probing path.</span></span> <span data-ttu-id="e2f4c-136">这些失败会<xref:System.IO.FileNotFoundException>引发。</span><span class="sxs-lookup"><span data-stu-id="e2f4c-136">These failures throw <xref:System.IO.FileNotFoundException>.</span></span>  
  
 <span data-ttu-id="e2f4c-137">某些绑定和加载失败不受此元素影响, 并且始终会进行缓存。</span><span class="sxs-lookup"><span data-stu-id="e2f4c-137">Some binding and loading failures are not affected by this element, and are always cached.</span></span> <span data-ttu-id="e2f4c-138">出现这些失败是因为程序集已找到, 但无法加载。</span><span class="sxs-lookup"><span data-stu-id="e2f4c-138">These failures occur because the assembly was found but could not be loaded.</span></span> <span data-ttu-id="e2f4c-139">它们引发<xref:System.BadImageFormatException>或<xref:System.IO.FileLoadException>。</span><span class="sxs-lookup"><span data-stu-id="e2f4c-139">They throw <xref:System.BadImageFormatException> or <xref:System.IO.FileLoadException>.</span></span> <span data-ttu-id="e2f4c-140">以下列表包括此类故障的一些示例。</span><span class="sxs-lookup"><span data-stu-id="e2f4c-140">The following list includes some examples of such failures.</span></span>  
  
- <span data-ttu-id="e2f4c-141">如果尝试加载文件不是有效的程序集, 则即使将错误文件替换为正确的程序集, 以后尝试加载程序集也会失败。</span><span class="sxs-lookup"><span data-stu-id="e2f4c-141">If you attempt to load a file is not a valid assembly, subsequent attempts to load the assembly will fail even if the bad file is replaced with the correct assembly.</span></span>  
  
- <span data-ttu-id="e2f4c-142">如果尝试加载文件系统锁定的程序集, 则即使在文件系统释放程序集之后, 加载程序集的后续尝试也将失败。</span><span class="sxs-lookup"><span data-stu-id="e2f4c-142">If you attempt to load an assembly that is locked by the file system, subsequent attempts to load the assembly will fail even after the assembly is released by the file system.</span></span>  
  
- <span data-ttu-id="e2f4c-143">如果尝试加载的程序集的一个或多个版本位于探测路径中, 但你请求的特定版本不在其中, 则即使将正确的版本移入探测路径, 后续尝试加载该版本也会失败。</span><span class="sxs-lookup"><span data-stu-id="e2f4c-143">If one or more versions of the assembly that you are attempting to load is in the probing path, but the specific version you are requesting is not among them, subsequent attempts to load that version will fail even if the correct version is moved into the probing path.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e2f4c-144">示例</span><span class="sxs-lookup"><span data-stu-id="e2f4c-144">Example</span></span>  
 <span data-ttu-id="e2f4c-145">下面的示例演示如何禁止缓存发生的程序集绑定故障, 因为探查找不到该程序集。</span><span class="sxs-lookup"><span data-stu-id="e2f4c-145">The following example shows how to disable the caching of assembly binding failures that occur because the assembly was not found by probing.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <disableCachingBindingFailures enabled="1" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="e2f4c-146">请参阅</span><span class="sxs-lookup"><span data-stu-id="e2f4c-146">See also</span></span>

- [<span data-ttu-id="e2f4c-147">运行时设置架构</span><span class="sxs-lookup"><span data-stu-id="e2f4c-147">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="e2f4c-148">配置文件架构</span><span class="sxs-lookup"><span data-stu-id="e2f4c-148">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="e2f4c-149">运行时如何定位程序集</span><span class="sxs-lookup"><span data-stu-id="e2f4c-149">How the Runtime Locates Assemblies</span></span>](../../../deployment/how-the-runtime-locates-assemblies.md)
