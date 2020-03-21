---
title: <relativeBindForResources> 元素
ms.date: 03/30/2017
helpviewer_keywords:
- RelativeBindForResources element
- <relativeBindForResources> element
ms.assetid: 846ffa47-7257-4ce3-8cac-7ff627e0e34f
ms.openlocfilehash: cd49d424019a4e8422fee0ae16217d49cfc456b1
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79153901"
---
# <a name="relativebindforresources-element"></a><span data-ttu-id="b164b-102">\<相对绑定资源>元素</span><span class="sxs-lookup"><span data-stu-id="b164b-102">\<relativeBindForResources> Element</span></span>
<span data-ttu-id="b164b-103">优化附属程序集的探测。</span><span class="sxs-lookup"><span data-stu-id="b164b-103">Optimizes the probe for satellite assemblies.</span></span>  
  
<span data-ttu-id="b164b-104">[**\<配置>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="b164b-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="b164b-105">&nbsp;&nbsp;[**\<运行时>**](runtime-element.md)</span><span class="sxs-lookup"><span data-stu-id="b164b-105">&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)</span></span>\
<span data-ttu-id="b164b-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<相对绑定资源>**</span><span class="sxs-lookup"><span data-stu-id="b164b-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<relativeBindForResources>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b164b-107">语法</span><span class="sxs-lookup"><span data-stu-id="b164b-107">Syntax</span></span>  
  
```xml
<relativeBindForResources
   enabled="true|false" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b164b-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="b164b-108">Attributes and Elements</span></span>  
 <span data-ttu-id="b164b-109">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="b164b-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b164b-110">属性</span><span class="sxs-lookup"><span data-stu-id="b164b-110">Attributes</span></span>  
  
|<span data-ttu-id="b164b-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="b164b-111">Attribute</span></span>|<span data-ttu-id="b164b-112">说明</span><span class="sxs-lookup"><span data-stu-id="b164b-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="b164b-113">必需的特性。</span><span class="sxs-lookup"><span data-stu-id="b164b-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="b164b-114">指定通用语言运行时是否优化了附属程序集的探测。</span><span class="sxs-lookup"><span data-stu-id="b164b-114">Specifies whether the common language runtime optimizes the probe for satellite assemblies.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="b164b-115">enabled 特性</span><span class="sxs-lookup"><span data-stu-id="b164b-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="b164b-116">值</span><span class="sxs-lookup"><span data-stu-id="b164b-116">Value</span></span>|<span data-ttu-id="b164b-117">说明</span><span class="sxs-lookup"><span data-stu-id="b164b-117">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="b164b-118">运行时不优化卫星组件的探测。</span><span class="sxs-lookup"><span data-stu-id="b164b-118">The runtime does not optimize the probe for satellite assemblies.</span></span> <span data-ttu-id="b164b-119">这是默认值。</span><span class="sxs-lookup"><span data-stu-id="b164b-119">This is the default value.</span></span>|  
|`true`|<span data-ttu-id="b164b-120">运行时优化了卫星组件的探测。</span><span class="sxs-lookup"><span data-stu-id="b164b-120">The runtime optimizes the probe for satellite assemblies.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b164b-121">子元素</span><span class="sxs-lookup"><span data-stu-id="b164b-121">Child Elements</span></span>  
 <span data-ttu-id="b164b-122">无。</span><span class="sxs-lookup"><span data-stu-id="b164b-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="b164b-123">父元素</span><span class="sxs-lookup"><span data-stu-id="b164b-123">Parent Elements</span></span>  
  
|<span data-ttu-id="b164b-124">元素</span><span class="sxs-lookup"><span data-stu-id="b164b-124">Element</span></span>|<span data-ttu-id="b164b-125">说明</span><span class="sxs-lookup"><span data-stu-id="b164b-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="b164b-126">公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。</span><span class="sxs-lookup"><span data-stu-id="b164b-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="b164b-127">包含有关运行时初始化选项的信息。</span><span class="sxs-lookup"><span data-stu-id="b164b-127">Contains information about runtime initialization options.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b164b-128">备注</span><span class="sxs-lookup"><span data-stu-id="b164b-128">Remarks</span></span>  
 <span data-ttu-id="b164b-129">通常，资源管理器会调查资源，如["打包和部署资源](../../../resources/packaging-and-deploying-resources-in-desktop-apps.md)"主题中所述。</span><span class="sxs-lookup"><span data-stu-id="b164b-129">In general, Resource Manager probes for resources, as documented in the [Packaging and Deploying Resources](../../../resources/packaging-and-deploying-resources-in-desktop-apps.md) topic.</span></span> <span data-ttu-id="b164b-130">这意味着，当资源管理器探测资源的特定本地化版本时，它可能会查看全局程序集缓存、在应用程序代码库中查看特定于区域性的文件夹、查询 Windows 安装程序以查找附属程序集以及引发<xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType>事件。</span><span class="sxs-lookup"><span data-stu-id="b164b-130">This means that when Resource Manager probes for a particular localized version of a resource, it may look in the global assembly cache, look in a culture-specific folder in the application's code base, query Windows Installer for satellite assemblies, and raise the <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType> event.</span></span> <span data-ttu-id="b164b-131">该`<relativeBindForResources>`元素优化了资源管理器探测附属程序集的方式。</span><span class="sxs-lookup"><span data-stu-id="b164b-131">The `<relativeBindForResources>` element optimizes the way in which Resource Manager probes for satellite assemblies.</span></span> <span data-ttu-id="b164b-132">在以下条件下探测资源时，它可以提高性能：</span><span class="sxs-lookup"><span data-stu-id="b164b-132">It can improve performance when probing for resources under the following conditions:</span></span>  
  
- <span data-ttu-id="b164b-133">当附属程序集部署在同一位置的代码程序集时。</span><span class="sxs-lookup"><span data-stu-id="b164b-133">When the satellite assembly is deployed in the same location as the code assembly.</span></span> <span data-ttu-id="b164b-134">换句话说，如果代码程序集安装在全局程序集缓存中，则还必须在那里安装附属程序集。</span><span class="sxs-lookup"><span data-stu-id="b164b-134">In other words, if the code assembly is installed in the global assembly cache, the satellite assemblies must also be installed there.</span></span> <span data-ttu-id="b164b-135">如果代码程序集安装在应用程序的代码库中，则附属程序集也必须安装在代码库中特定于区域性的文件夹中。</span><span class="sxs-lookup"><span data-stu-id="b164b-135">If the code assembly is installed in the application's code base, the satellite assemblies must also be installed in a culture-specific folder in the code base.</span></span>  
  
- <span data-ttu-id="b164b-136">当不使用 Windows 安装程序或很少用于按需安装附属程序集时。</span><span class="sxs-lookup"><span data-stu-id="b164b-136">When Windows Installer is not used or is used only rarely for on-demand installation of satellite assemblies.</span></span>  
  
- <span data-ttu-id="b164b-137">当应用程序代码不处理事件<xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType>时。</span><span class="sxs-lookup"><span data-stu-id="b164b-137">When application code does not handle the <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType> event.</span></span>  
  
 <span data-ttu-id="b164b-138">设置`enabled``<relativeBindForResources>`元素的属性以`true`优化资源管理器对附属程序集的探测，如下所示：</span><span class="sxs-lookup"><span data-stu-id="b164b-138">Setting the `enabled` attribute of the `<relativeBindForResources>` element to `true` optimizes Resource Manager's probe for satellite assemblies as follows:</span></span>  
  
- <span data-ttu-id="b164b-139">它使用父代码程序集的位置来探测附属程序集。</span><span class="sxs-lookup"><span data-stu-id="b164b-139">It uses the location of the parent code assembly to probe for the satellite assembly.</span></span>  
  
- <span data-ttu-id="b164b-140">它不查询 Windows 安装程序的附属程序集。</span><span class="sxs-lookup"><span data-stu-id="b164b-140">It does not query Windows Installer for satellite assemblies.</span></span>  
  
- <span data-ttu-id="b164b-141">它不引发事件<xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType>。</span><span class="sxs-lookup"><span data-stu-id="b164b-141">It does not raise the <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType> event.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b164b-142">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b164b-142">See also</span></span>

- [<span data-ttu-id="b164b-143">Packaging and Deploying Resources</span><span class="sxs-lookup"><span data-stu-id="b164b-143">Packaging and Deploying Resources</span></span>](../../../resources/packaging-and-deploying-resources-in-desktop-apps.md)
- [<span data-ttu-id="b164b-144">运行时设置架构</span><span class="sxs-lookup"><span data-stu-id="b164b-144">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="b164b-145">配置文件架构</span><span class="sxs-lookup"><span data-stu-id="b164b-145">Configuration File Schema</span></span>](../index.md)
