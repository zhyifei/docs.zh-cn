---
title: <relativeBindForResources> 元素
ms.date: 03/30/2017
helpviewer_keywords:
- RelativeBindForResources element
- <relativeBindForResources> element
ms.assetid: 846ffa47-7257-4ce3-8cac-7ff627e0e34f
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 859e8a12421ea92aa48c54317e052683eb8e83f8
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/21/2019
ms.locfileid: "69663487"
---
# <a name="relativebindforresources-element"></a><span data-ttu-id="2def6-102">\<relativeBindForResources > 元素</span><span class="sxs-lookup"><span data-stu-id="2def6-102">\<relativeBindForResources> Element</span></span>
<span data-ttu-id="2def6-103">优化附属程序集的探测。</span><span class="sxs-lookup"><span data-stu-id="2def6-103">Optimizes the probe for satellite assemblies.</span></span>  
  
 <span data-ttu-id="2def6-104">\<配置 > 元素</span><span class="sxs-lookup"><span data-stu-id="2def6-104">\<configuration> Element</span></span>  
<span data-ttu-id="2def6-105">\<运行时 > 元素</span><span class="sxs-lookup"><span data-stu-id="2def6-105">\<runtime> Element</span></span>  
<span data-ttu-id="2def6-106">\<relativeBindForResources > 元素</span><span class="sxs-lookup"><span data-stu-id="2def6-106">\<relativeBindForResources> Element</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2def6-107">语法</span><span class="sxs-lookup"><span data-stu-id="2def6-107">Syntax</span></span>  
  
```xml
<relativeBindForResources    
   enabled="true|false" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2def6-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="2def6-108">Attributes and Elements</span></span>  
 <span data-ttu-id="2def6-109">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="2def6-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2def6-110">特性</span><span class="sxs-lookup"><span data-stu-id="2def6-110">Attributes</span></span>  
  
|<span data-ttu-id="2def6-111">特性</span><span class="sxs-lookup"><span data-stu-id="2def6-111">Attribute</span></span>|<span data-ttu-id="2def6-112">描述</span><span class="sxs-lookup"><span data-stu-id="2def6-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="2def6-113">必需的特性。</span><span class="sxs-lookup"><span data-stu-id="2def6-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="2def6-114">指定公共语言运行时是否优化附属程序集的探测。</span><span class="sxs-lookup"><span data-stu-id="2def6-114">Specifies whether the common language runtime optimizes the probe for satellite assemblies.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="2def6-115">enabled 特性</span><span class="sxs-lookup"><span data-stu-id="2def6-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="2def6-116">值</span><span class="sxs-lookup"><span data-stu-id="2def6-116">Value</span></span>|<span data-ttu-id="2def6-117">描述</span><span class="sxs-lookup"><span data-stu-id="2def6-117">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="2def6-118">运行时不会优化附属程序集的探测。</span><span class="sxs-lookup"><span data-stu-id="2def6-118">The runtime does not optimize the probe for satellite assemblies.</span></span> <span data-ttu-id="2def6-119">这是默认值。</span><span class="sxs-lookup"><span data-stu-id="2def6-119">This is the default value.</span></span>|  
|`true`|<span data-ttu-id="2def6-120">运行时优化附属程序集的探测。</span><span class="sxs-lookup"><span data-stu-id="2def6-120">The runtime optimizes the probe for satellite assemblies.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="2def6-121">子元素</span><span class="sxs-lookup"><span data-stu-id="2def6-121">Child Elements</span></span>  
 <span data-ttu-id="2def6-122">无。</span><span class="sxs-lookup"><span data-stu-id="2def6-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="2def6-123">父元素</span><span class="sxs-lookup"><span data-stu-id="2def6-123">Parent Elements</span></span>  
  
|<span data-ttu-id="2def6-124">元素</span><span class="sxs-lookup"><span data-stu-id="2def6-124">Element</span></span>|<span data-ttu-id="2def6-125">描述</span><span class="sxs-lookup"><span data-stu-id="2def6-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="2def6-126">公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。</span><span class="sxs-lookup"><span data-stu-id="2def6-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="2def6-127">包含有关运行时初始化选项的信息。</span><span class="sxs-lookup"><span data-stu-id="2def6-127">Contains information about runtime initialization options.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2def6-128">备注</span><span class="sxs-lookup"><span data-stu-id="2def6-128">Remarks</span></span>  
 <span data-ttu-id="2def6-129">一般情况下, 资源管理器探测资源, 如[打包和部署资源](../../../resources/packaging-and-deploying-resources-in-desktop-apps.md)主题中所述。</span><span class="sxs-lookup"><span data-stu-id="2def6-129">In general, Resource Manager probes for resources, as documented in the [Packaging and Deploying Resources](../../../resources/packaging-and-deploying-resources-in-desktop-apps.md) topic.</span></span> <span data-ttu-id="2def6-130">这意味着, 当资源管理器探测某个资源的特定本地化版本时, 它可能会在全局程序集缓存中查找, 在应用程序的基本代码中查找特定于区域性的文件夹, 为附属程序集查询 Windows Installer, 并引发<xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType>事件。</span><span class="sxs-lookup"><span data-stu-id="2def6-130">This means that when Resource Manager probes for a particular localized version of a resource, it may look in the global assembly cache, look in a culture-specific folder in the application's code base, query Windows Installer for satellite assemblies, and raise the <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType> event.</span></span> <span data-ttu-id="2def6-131">`<relativeBindForResources>`元素优化资源管理器探测附属程序集的方式。</span><span class="sxs-lookup"><span data-stu-id="2def6-131">The `<relativeBindForResources>` element optimizes the way in which Resource Manager probes for satellite assemblies.</span></span> <span data-ttu-id="2def6-132">当在以下条件下探测资源时, 它可以提高性能:</span><span class="sxs-lookup"><span data-stu-id="2def6-132">It can improve performance when probing for resources under the following conditions:</span></span>  
  
- <span data-ttu-id="2def6-133">当附属程序集部署在与代码程序集相同的位置时。</span><span class="sxs-lookup"><span data-stu-id="2def6-133">When the satellite assembly is deployed in the same location as the code assembly.</span></span> <span data-ttu-id="2def6-134">换言之, 如果代码程序集安装在全局程序集缓存中, 则还必须在该程序集中安装附属程序集。</span><span class="sxs-lookup"><span data-stu-id="2def6-134">In other words, if the code assembly is installed in the global assembly cache, the satellite assemblies must also be installed there.</span></span> <span data-ttu-id="2def6-135">如果代码程序集安装在应用程序的代码库中, 则附属程序集还必须安装在基本代码的特定于区域性的文件夹中。</span><span class="sxs-lookup"><span data-stu-id="2def6-135">If the code assembly is installed in the application's code base, the satellite assemblies must also be installed in a culture-specific folder in the code base.</span></span>  
  
- <span data-ttu-id="2def6-136">如果未使用 Windows Installer 或只是很少使用附属程序集的按需安装。</span><span class="sxs-lookup"><span data-stu-id="2def6-136">When Windows Installer is not used or is used only rarely for on-demand installation of satellite assemblies.</span></span>  
  
- <span data-ttu-id="2def6-137">当应用程序代码不处理<xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType>事件时。</span><span class="sxs-lookup"><span data-stu-id="2def6-137">When application code does not handle the <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType> event.</span></span>  
  
 <span data-ttu-id="2def6-138">`<relativeBindForResources>` `true`设置元素的属性,以优化资源管理器的附属程序集探测`enabled` , 如下所示:</span><span class="sxs-lookup"><span data-stu-id="2def6-138">Setting the `enabled` attribute of the `<relativeBindForResources>` element to `true` optimizes Resource Manager's probe for satellite assemblies as follows:</span></span>  
  
- <span data-ttu-id="2def6-139">它使用父代码程序集的位置来探测附属程序集。</span><span class="sxs-lookup"><span data-stu-id="2def6-139">It uses the location of the parent code assembly to probe for the satellite assembly.</span></span>  
  
- <span data-ttu-id="2def6-140">它不会为附属程序集查询 Windows Installer。</span><span class="sxs-lookup"><span data-stu-id="2def6-140">It does not query Windows Installer for satellite assemblies.</span></span>  
  
- <span data-ttu-id="2def6-141">它不会引发<xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType>事件。</span><span class="sxs-lookup"><span data-stu-id="2def6-141">It does not raise the <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType> event.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2def6-142">请参阅</span><span class="sxs-lookup"><span data-stu-id="2def6-142">See also</span></span>

- [<span data-ttu-id="2def6-143">打包和部署资源</span><span class="sxs-lookup"><span data-stu-id="2def6-143">Packaging and Deploying Resources</span></span>](../../../resources/packaging-and-deploying-resources-in-desktop-apps.md)
- [<span data-ttu-id="2def6-144">运行时设置架构</span><span class="sxs-lookup"><span data-stu-id="2def6-144">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="2def6-145">配置文件架构</span><span class="sxs-lookup"><span data-stu-id="2def6-145">Configuration File Schema</span></span>](../index.md)
