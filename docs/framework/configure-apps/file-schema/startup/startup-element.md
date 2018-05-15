---
title: '&lt;启动&gt;元素'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/startup
- http://schemas.microsoft.com/.NetConfiguration/v2.0#startup
helpviewer_keywords:
- container tags, <startup> element
- <startup> element
- startup element
ms.assetid: 536acfd8-f827-452f-838a-e14fa3b87621
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 60699f0335bb35589341558800cfd64503d0aa0a
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
---
# <a name="ltstartupgt-element"></a><span data-ttu-id="f2e87-102">&lt;启动&gt;元素</span><span class="sxs-lookup"><span data-stu-id="f2e87-102">&lt;startup&gt; Element</span></span>
<span data-ttu-id="f2e87-103">指定公共语言运行时启动信息。</span><span class="sxs-lookup"><span data-stu-id="f2e87-103">Specifies common language runtime startup information.</span></span>  
  
 <span data-ttu-id="f2e87-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="f2e87-104">\<configuration></span></span>  
<span data-ttu-id="f2e87-105">\<启动 ></span><span class="sxs-lookup"><span data-stu-id="f2e87-105">\<startup></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f2e87-106">语法</span><span class="sxs-lookup"><span data-stu-id="f2e87-106">Syntax</span></span>  
  
```xml  
<startup useLegacyV2RuntimeActivationPolicy="true|false" >   
</startup>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f2e87-107">特性和元素</span><span class="sxs-lookup"><span data-stu-id="f2e87-107">Attributes and Elements</span></span>  
 <span data-ttu-id="f2e87-108">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="f2e87-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f2e87-109">特性</span><span class="sxs-lookup"><span data-stu-id="f2e87-109">Attributes</span></span>  
  
|<span data-ttu-id="f2e87-110">特性</span><span class="sxs-lookup"><span data-stu-id="f2e87-110">Attribute</span></span>|<span data-ttu-id="f2e87-111">描述</span><span class="sxs-lookup"><span data-stu-id="f2e87-111">Description</span></span>|  
|---------------|-----------------|  
|`useLegacyV2RuntimeActivationPolicy`|<span data-ttu-id="f2e87-112">可选特性。</span><span class="sxs-lookup"><span data-stu-id="f2e87-112">Optional attribute.</span></span><br /><br /> <span data-ttu-id="f2e87-113">指定是否启用[!INCLUDE[dnprdnext](../../../../../includes/dnprdnext-md.md)]运行时激活策略或使用[!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)]激活策略。</span><span class="sxs-lookup"><span data-stu-id="f2e87-113">Specifies whether to enable the [!INCLUDE[dnprdnext](../../../../../includes/dnprdnext-md.md)] runtime activation policy or to use the [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)] activation policy.</span></span>|  
  
## <a name="uselegacyv2runtimeactivationpolicy-attribute"></a><span data-ttu-id="f2e87-114">useLegacyV2RuntimeActivationPolicy 属性</span><span class="sxs-lookup"><span data-stu-id="f2e87-114">useLegacyV2RuntimeActivationPolicy Attribute</span></span>  
  
|<span data-ttu-id="f2e87-115">值</span><span class="sxs-lookup"><span data-stu-id="f2e87-115">Value</span></span>|<span data-ttu-id="f2e87-116">描述</span><span class="sxs-lookup"><span data-stu-id="f2e87-116">Description</span></span>|  
|-----------|-----------------|  
|`true`|<span data-ttu-id="f2e87-117">启用[!INCLUDE[dnprdnext](../../../../../includes/dnprdnext-md.md)]选运行时，是将绑定旧式运行时激活技术的运行时激活策略 (如[CorBindToRuntimeEx 函数](../../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md)) 为运行时从配置文件而不是选择上限它们设置在 CLR 版本 2.0。</span><span class="sxs-lookup"><span data-stu-id="f2e87-117">Enable [!INCLUDE[dnprdnext](../../../../../includes/dnprdnext-md.md)] runtime activation policy for the chosen runtime, which is to bind legacy runtime activation techniques (such as the [CorBindToRuntimeEx function](../../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md)) to the runtime chosen from the configuration file instead of capping them at CLR version 2.0.</span></span> <span data-ttu-id="f2e87-118">因此，如果从配置文件选择 CLR 版本 4 或更高版本，则使用.NET Framework 的早期版本创建的混合模式程序集是加载与选择的 CLR 版本。</span><span class="sxs-lookup"><span data-stu-id="f2e87-118">Thus, if CLR version 4 or later is chosen from the configuration file, mixed-mode assemblies created with earlier versions of the .NET Framework are loaded with the chosen CLR version.</span></span> <span data-ttu-id="f2e87-119">将设置此值可防止 CLR 版本 1.1 或 CLR 版本 2.0 加载到相同的过程中，有效地禁用进程内并行的功能。</span><span class="sxs-lookup"><span data-stu-id="f2e87-119">Setting this value prevents CLR version 1.1 or CLR version 2.0 from loading into the same process, effectively disabling the in-process side-by-side feature.</span></span>|  
|`false`|<span data-ttu-id="f2e87-120">使用的默认激活策略[!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)]和更高版本，即允许旧式运行时加载到进程的 CLR 版本 1.1 或 2.0 的激活方法。</span><span class="sxs-lookup"><span data-stu-id="f2e87-120">Use the default activation policy for the [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] and later, which is to allow legacy runtime activation techniques to load CLR version 1.1 or 2.0 into the process.</span></span> <span data-ttu-id="f2e87-121">设置此值禁止从加载到.NET Framework 4 或更高版本，除非它们生成.NET Framework 4 或更高版本的混合模式程序集。</span><span class="sxs-lookup"><span data-stu-id="f2e87-121">Setting this value prevents mixed-mode assemblies from loading into the .NET Framework 4 or later unless they were built with the .NET Framework 4 or later.</span></span> <span data-ttu-id="f2e87-122">此值是默认值。</span><span class="sxs-lookup"><span data-stu-id="f2e87-122">This value is the default.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f2e87-123">子元素</span><span class="sxs-lookup"><span data-stu-id="f2e87-123">Child Elements</span></span>  
  
|<span data-ttu-id="f2e87-124">元素</span><span class="sxs-lookup"><span data-stu-id="f2e87-124">Element</span></span>|<span data-ttu-id="f2e87-125">描述</span><span class="sxs-lookup"><span data-stu-id="f2e87-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f2e87-126">\<requiredRuntime></span><span class="sxs-lookup"><span data-stu-id="f2e87-126">\<requiredRuntime></span></span>](../../../../../docs/framework/configure-apps/file-schema/startup/requiredruntime-element.md)|<span data-ttu-id="f2e87-127">指定应用程序仅支持 1.0 版本的公共语言运行时。</span><span class="sxs-lookup"><span data-stu-id="f2e87-127">Specifies that the application supports only version 1.0 of the common language runtime.</span></span> <span data-ttu-id="f2e87-128">运行时 1.1 版或更高版本生成的应用程序应使用 **\<supportedRuntime >** 元素。</span><span class="sxs-lookup"><span data-stu-id="f2e87-128">Applications built with runtime version 1.1 or later should use the **\<supportedRuntime>** element.</span></span>|  
|[<span data-ttu-id="f2e87-129">\<supportedRuntime></span><span class="sxs-lookup"><span data-stu-id="f2e87-129">\<supportedRuntime></span></span>](../../../../../docs/framework/configure-apps/file-schema/startup/supportedruntime-element.md)|<span data-ttu-id="f2e87-130">指定应用程序支持的公共语言运行时版本。</span><span class="sxs-lookup"><span data-stu-id="f2e87-130">Specifies which versions of the common language runtime the application supports.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="f2e87-131">父元素</span><span class="sxs-lookup"><span data-stu-id="f2e87-131">Parent Elements</span></span>  
  
|<span data-ttu-id="f2e87-132">元素</span><span class="sxs-lookup"><span data-stu-id="f2e87-132">Element</span></span>|<span data-ttu-id="f2e87-133">描述</span><span class="sxs-lookup"><span data-stu-id="f2e87-133">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="f2e87-134">公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。</span><span class="sxs-lookup"><span data-stu-id="f2e87-134">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f2e87-135">备注</span><span class="sxs-lookup"><span data-stu-id="f2e87-135">Remarks</span></span>  
 <span data-ttu-id="f2e87-136">**\<SupportedRuntime >** 元素应由使用版本 1.1 或更高版本的运行时生成的所有应用程序。</span><span class="sxs-lookup"><span data-stu-id="f2e87-136">The **\<supportedRuntime>** element should be used by all applications built using version 1.1 or later of the runtime.</span></span> <span data-ttu-id="f2e87-137">为支持仅运行时 1.0 版而生成的应用程序必须使用 **\<requiredRuntime >** 元素。</span><span class="sxs-lookup"><span data-stu-id="f2e87-137">Applications built to support only version 1.0 of the runtime must use the **\<requiredRuntime>** element.</span></span>  
  
 <span data-ttu-id="f2e87-138">在 Microsoft Internet Explorer 中托管的应用程序的启动代码将忽略**\<启动 >** 元素及其子元素。</span><span class="sxs-lookup"><span data-stu-id="f2e87-138">The startup code for an application hosted in Microsoft Internet Explorer ignores the **\<startup>** element and its child elements.</span></span>  
  
## <a name="the-uselegacyv2runtimeactivationpolicy-attribute"></a><span data-ttu-id="f2e87-139">UseLegacyV2RuntimeActivationPolicy 属性</span><span class="sxs-lookup"><span data-stu-id="f2e87-139">The useLegacyV2RuntimeActivationPolicy Attribute</span></span>  
 <span data-ttu-id="f2e87-140">此属性是很有用，如果你的应用程序使用旧式激活路径，如[CorBindToRuntimeEx 函数](../../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md)，并且你希望这些路径激活而不是早期版本，CLR 版本 4 或如果你的应用程序使用生成[!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)]但在使用.NET Framework 的早期版本生成的混合模式程序集具有的依赖关系。</span><span class="sxs-lookup"><span data-stu-id="f2e87-140">This attribute is useful if your application uses legacy activation paths, such as the [CorBindToRuntimeEx function](../../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md), and you want those paths to activate version 4 of the CLR instead of an earlier version, or if your application is built with the [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] but has a dependency on a mixed-mode assembly built with an earlier version of the .NET Framework.</span></span> <span data-ttu-id="f2e87-141">在这些情况下，将属性设置为`true`。</span><span class="sxs-lookup"><span data-stu-id="f2e87-141">In those scenarios, set the attribute to `true`.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f2e87-142">将属性设置为`true`阻止到相同的过程中，有效地禁用进程内的并行功能加载的 CLR 版本 1.1 或 CLR 版本 2.0 (请参阅[为 COM 互操作的并行执行](http://msdn.microsoft.com/library/4302318c-3586-49bf-8620-b9a39cdf4a32))。</span><span class="sxs-lookup"><span data-stu-id="f2e87-142">Setting the attribute to `true` prevents CLR version 1.1 or CLR version 2.0 from loading into the same process, effectively disabling the in-process side-by-side feature (see [Side-by-Side Execution for COM Interop](http://msdn.microsoft.com/library/4302318c-3586-49bf-8620-b9a39cdf4a32)).</span></span>  
  
## <a name="example"></a><span data-ttu-id="f2e87-143">示例</span><span class="sxs-lookup"><span data-stu-id="f2e87-143">Example</span></span>  
 <span data-ttu-id="f2e87-144">下面的示例演示如何在配置文件中指定的运行时版本。</span><span class="sxs-lookup"><span data-stu-id="f2e87-144">The following example shows how to specify the runtime version in a configuration file.</span></span>  
  
```xml  
<!-- When used with version 1.0 of the .NET Framework runtime -->  
<configuration>  
   <startup>  
      <requiredRuntime version="v1.0.3705" safemode="true"/>  
   </startup>  
</configuration>  
<!-- When used with version 1.1 (or later) of the runtime -->  
<configuration>  
   <startup>  
      <supportedRuntime version="v1.1.4322"/>  
      <supportedRuntime version="v1.0.3705"/>  
   </startup>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="f2e87-145">请参阅</span><span class="sxs-lookup"><span data-stu-id="f2e87-145">See Also</span></span>  
 [<span data-ttu-id="f2e87-146">启动设置架构</span><span class="sxs-lookup"><span data-stu-id="f2e87-146">Startup Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/startup/index.md)  
 [<span data-ttu-id="f2e87-147">配置文件架构</span><span class="sxs-lookup"><span data-stu-id="f2e87-147">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [<span data-ttu-id="f2e87-148">\<PaveOver> 指定要使用的运行时版本</span><span class="sxs-lookup"><span data-stu-id="f2e87-148">\<PaveOver> Specifying Which Runtime Version to Use</span></span>](http://msdn.microsoft.com/library/c376208d-980d-42b4-865b-fbe0d9cc97c2)  
 [<span data-ttu-id="f2e87-149">COM 互操作的的并行执行</span><span class="sxs-lookup"><span data-stu-id="f2e87-149">Side-by-Side Execution for COM Interop</span></span>](http://msdn.microsoft.com/library/4302318c-3586-49bf-8620-b9a39cdf4a32)  
 [<span data-ttu-id="f2e87-150">进程内并行执行</span><span class="sxs-lookup"><span data-stu-id="f2e87-150">In-Process Side-by-Side Execution</span></span>](../../../../../docs/framework/deployment/in-process-side-by-side-execution.md)
