---
title: '&lt;supportedRuntime&gt;元素'
ms.date: 04/10/2018
ms.custom: updateeachrelease
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#supportedRuntime
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/startup/supportedRuntime
helpviewer_keywords:
- supportedRuntime element
- <supportedRuntime> element
ms.assetid: 1ae16e23-afbe-4de4-b413-bc457f37b69f
author: mcleblanc
ms.author: markl
ms.openlocfilehash: b86ffdd242a95a0c5c34efb3f38b3501f3f2ba6c
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/26/2018
ms.locfileid: "47197794"
---
# <a name="ltsupportedruntimegt-element"></a><span data-ttu-id="5fa91-102">&lt;supportedRuntime&gt;元素</span><span class="sxs-lookup"><span data-stu-id="5fa91-102">&lt;supportedRuntime&gt; Element</span></span>

<span data-ttu-id="5fa91-103">指定应用程序支持的公共语言运行时版本。</span><span class="sxs-lookup"><span data-stu-id="5fa91-103">Specifies which versions of the common language runtime the application supports.</span></span> <span data-ttu-id="5fa91-104">此元素应由用 .NET Framework 1.1 版或更高版本生成的所有应用程序使用。</span><span class="sxs-lookup"><span data-stu-id="5fa91-104">This element should be used by all applications built with version 1.1 or later of the .NET Framework.</span></span>  
  
[<span data-ttu-id="5fa91-105">\<configuration></span><span class="sxs-lookup"><span data-stu-id="5fa91-105">\<configuration></span></span>](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)  
<span data-ttu-id="5fa91-106">&nbsp;&nbsp;[\<startup>](../../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md)</span><span class="sxs-lookup"><span data-stu-id="5fa91-106">&nbsp;&nbsp;[\<startup>](../../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md)</span></span>  
<span data-ttu-id="5fa91-107">&nbsp;&nbsp;&nbsp;&nbsp;**\<supportedRuntime>**</span><span class="sxs-lookup"><span data-stu-id="5fa91-107">&nbsp;&nbsp;&nbsp;&nbsp;**\<supportedRuntime>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5fa91-108">语法</span><span class="sxs-lookup"><span data-stu-id="5fa91-108">Syntax</span></span>
  
```xml  
<supportedRuntime version="runtime version" sku="sku id"/>  
```  
  
## <a name="attributes"></a><span data-ttu-id="5fa91-109">特性</span><span class="sxs-lookup"><span data-stu-id="5fa91-109">Attributes</span></span>
  
|<span data-ttu-id="5fa91-110">特性</span><span class="sxs-lookup"><span data-stu-id="5fa91-110">Attribute</span></span>|<span data-ttu-id="5fa91-111">描述</span><span class="sxs-lookup"><span data-stu-id="5fa91-111">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="5fa91-112">**version**</span><span class="sxs-lookup"><span data-stu-id="5fa91-112">**version**</span></span>|<span data-ttu-id="5fa91-113">可选特性。</span><span class="sxs-lookup"><span data-stu-id="5fa91-113">Optional attribute.</span></span><br /><br /> <span data-ttu-id="5fa91-114">一个字符串值，它指定此应用程序支持的公共语言运行时 (CLR) 版本。</span><span class="sxs-lookup"><span data-stu-id="5fa91-114">A string value that specifies the version of the common language runtime (CLR) that this application supports.</span></span> <span data-ttu-id="5fa91-115">有关的有效值`version`属性，请参阅["运行时版本"值](#version)部分。</span><span class="sxs-lookup"><span data-stu-id="5fa91-115">For valid values of the `version` attribute, see the ["runtime version" values](#version) section.</span></span> <span data-ttu-id="5fa91-116">**注意：** .NET Framework 3.5 中，通过"*运行时版本*"值的形式*主要*。*次要*。*生成*。</span><span class="sxs-lookup"><span data-stu-id="5fa91-116">**Note:**  Through the .NET Framework 3.5, the "*runtime version*" value takes the form *major*.*minor*.*build*.</span></span> <span data-ttu-id="5fa91-117">从 [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)] 开始，仅主版本号和次版本号是必需的（即“v4.0”而不是“v4.0.30319”）。</span><span class="sxs-lookup"><span data-stu-id="5fa91-117">Beginning with the [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)], only the major and minor version numbers are required (that is, "v4.0" instead of "v4.0.30319").</span></span> <span data-ttu-id="5fa91-118">建议使用较短字符串。</span><span class="sxs-lookup"><span data-stu-id="5fa91-118">The shorter string is recommended.</span></span>|  
|<span data-ttu-id="5fa91-119">**sku**</span><span class="sxs-lookup"><span data-stu-id="5fa91-119">**sku**</span></span>|<span data-ttu-id="5fa91-120">可选特性。</span><span class="sxs-lookup"><span data-stu-id="5fa91-120">Optional attribute.</span></span><br /><br /> <span data-ttu-id="5fa91-121">一个字符串值，该值指定库存单位 (SKU)，库存单位则指定此应用程序支持的 .NET Framework 版本。</span><span class="sxs-lookup"><span data-stu-id="5fa91-121">A string value that specifies the stock-keeping unit (SKU), which in turn specifies which .NET Framework release this application supports.</span></span><br /><br /> <span data-ttu-id="5fa91-122">从.NET Framework 4.0 使用`sku`建议属性。</span><span class="sxs-lookup"><span data-stu-id="5fa91-122">Starting with the .NET Framework 4.0, the use of the `sku` attribute is recommended.</span></span>  <span data-ttu-id="5fa91-123">若存在该特性，则它指示应用面向的 .NET Framework 版本。</span><span class="sxs-lookup"><span data-stu-id="5fa91-123">When present, it indicates the version of the .NET Framework that the app targets.</span></span><br /><br /> <span data-ttu-id="5fa91-124">有关有效的 sku 属性的值，请参阅["sku id"值](#sku)部分。</span><span class="sxs-lookup"><span data-stu-id="5fa91-124">For valid values of the sku attribute, see the ["sku id" values](#sku) section.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5fa91-125">备注</span><span class="sxs-lookup"><span data-stu-id="5fa91-125">Remarks</span></span>

<span data-ttu-id="5fa91-126">如果 **\<supportedRuntime >** 元素不存在应用程序配置文件，请使用用于生成应用程序的运行时的版本。</span><span class="sxs-lookup"><span data-stu-id="5fa91-126">If the **\<supportedRuntime>** element is not present in the application configuration file, the version of the runtime used to build the application is used.</span></span>  

<span data-ttu-id="5fa91-127">**\<SupportedRuntime >** 元素应由使用 1.1 版或更高版本的运行时版本生成的所有应用程序。</span><span class="sxs-lookup"><span data-stu-id="5fa91-127">The **\<supportedRuntime>** element should be used by all applications built using version 1.1 or later of the runtime.</span></span> <span data-ttu-id="5fa91-128">仅支持 1.0 版的运行时生成的应用程序必须使用[ \<requiredRuntime >](../../../../../docs/framework/configure-apps/file-schema/startup/requiredruntime-element.md)元素。</span><span class="sxs-lookup"><span data-stu-id="5fa91-128">Applications built to support only version 1.0 of the runtime must use the [\<requiredRuntime>](../../../../../docs/framework/configure-apps/file-schema/startup/requiredruntime-element.md) element.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5fa91-129">如果您使用[CorBindToRuntimeByCfg](../../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimebycfg-function.md)函数以指定配置文件，则必须使用`<requiredRuntime>`所有版本的运行时的元素。</span><span class="sxs-lookup"><span data-stu-id="5fa91-129">If you use the [CorBindToRuntimeByCfg](../../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimebycfg-function.md) function to specify the configuration file, you must use the `<requiredRuntime>` element for all versions of the runtime.</span></span> <span data-ttu-id="5fa91-130">`<supportedRuntime>`使用时，将忽略元素[CorBindToRuntimeByCfg](../../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimebycfg-function.md)。</span><span class="sxs-lookup"><span data-stu-id="5fa91-130">The `<supportedRuntime>` element is ignored when you use [CorBindToRuntimeByCfg](../../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimebycfg-function.md).</span></span>  
  
<span data-ttu-id="5fa91-131">对于支持从 .NET Framework 1.1 到 3.5 的运行时版本的应用，支持多个运行时版本时，第一个元素应指定优先级最高的版本，最后一个元素应指定优先级最低的版本。</span><span class="sxs-lookup"><span data-stu-id="5fa91-131">For apps that support versions of the runtime from the .NET Framework 1.1 through 3.5, when multiple versions of the runtime are supported, the first element should specify the most preferred version of the runtime, and the last element should specify the least preferred version.</span></span> <span data-ttu-id="5fa91-132">对于支持的.NET Framework 4.0 或更高版本的应用`version`属性指示的 CLR 版本，这是普遍适用于.NET Framework 4 和更高版本，和`sku`属性指示单个.NET Framework 版本的应用程序目标。</span><span class="sxs-lookup"><span data-stu-id="5fa91-132">For apps that support the .NET Framework 4.0 or later versions, the `version` attribute indicates the CLR version, which is common to the .NET Framework 4 and later versions, and the `sku` attribute indicates single .NET Framework version that the app targets.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5fa91-133">如果你的应用程序使用旧式激活路径，如[CorBindToRuntimeEx 函数](../../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md)，并且希望这些路径来激活而不是早期版本的 CLR 版本 4 或如果你的应用程序使用生成[!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)]具有依赖关系，但在上使用.NET Framework 的早期版本构建的混合模式程序集，它不是只需指定[!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)]在受支持运行时列表中。</span><span class="sxs-lookup"><span data-stu-id="5fa91-133">If your application uses legacy activation paths, such as the [CorBindToRuntimeEx function](../../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md), and you want those paths to activate version 4 of the CLR instead of an earlier version, or if your application is built with the [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] but has a dependency on a mixed-mode assembly built with an earlier version of the .NET Framework, it is not sufficient to specify the [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] in the list of supported runtimes.</span></span> <span data-ttu-id="5fa91-134">此外，在[\<启动 > 元素](../../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md)在配置文件中，必须设置`useLegacyV2RuntimeActivationPolicy`归于`true`。</span><span class="sxs-lookup"><span data-stu-id="5fa91-134">In addition, in the [\<startup> element](../../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md) in your configuration file, you must set the `useLegacyV2RuntimeActivationPolicy` attribute to `true`.</span></span> <span data-ttu-id="5fa91-135">但是，将此特性设置为 `true` 意味着，用 .NET Framework 早期版本生成的所有组件都使用 [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)]（而不是生成它们时所用的运行时）运行。</span><span class="sxs-lookup"><span data-stu-id="5fa91-135">However, setting this attribute to `true` means that all components built with earlier versions of the .NET Framework are run using the [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] instead of the runtimes they were built with.</span></span>  
  
<span data-ttu-id="5fa91-136">我们建议你使用应用程序可在其上运行的所有 .NET Framework 版本来测试这些应用程序。</span><span class="sxs-lookup"><span data-stu-id="5fa91-136">We recommend that you test applications with all the .NET Framework versions that they can run on.</span></span>  
  
<a name="version"></a>   
## <a name="runtime-version-values"></a><span data-ttu-id="5fa91-137">“运行时版本”值</span><span class="sxs-lookup"><span data-stu-id="5fa91-137">"runtime version" values</span></span>  
<span data-ttu-id="5fa91-138">`runtime`属性指定给定应用程序所需的公共语言运行时 (CLR) 版本。</span><span class="sxs-lookup"><span data-stu-id="5fa91-138">The `runtime` attribute specifies the Common Language Runtime (CLR) version that is required for a given application.</span></span> <span data-ttu-id="5fa91-139">请注意，所有.NET Framework v4.x 版本都指定`v4.0`CLR。</span><span class="sxs-lookup"><span data-stu-id="5fa91-139">Note that all .NET Framework v4.x versions specify the `v4.0` CLR.</span></span> <span data-ttu-id="5fa91-140">下表列出了有效值*运行时版本*的值`version`属性。</span><span class="sxs-lookup"><span data-stu-id="5fa91-140">The following table lists valid values for the *runtime version* value of the `version` attribute.</span></span>  

|<span data-ttu-id="5fa91-141">.NET Framework 版本</span><span class="sxs-lookup"><span data-stu-id="5fa91-141">.NET Framework version</span></span>|<span data-ttu-id="5fa91-142">`version` 特性</span><span class="sxs-lookup"><span data-stu-id="5fa91-142">`version` attribute</span></span>|  
|----------------------------|-------------------------|  
|<span data-ttu-id="5fa91-143">1.0</span><span class="sxs-lookup"><span data-stu-id="5fa91-143">1.0</span></span>|<span data-ttu-id="5fa91-144">"v1.0.3705"</span><span class="sxs-lookup"><span data-stu-id="5fa91-144">"v1.0.3705"</span></span>|  
|<span data-ttu-id="5fa91-145">1.1</span><span class="sxs-lookup"><span data-stu-id="5fa91-145">1.1</span></span>|<span data-ttu-id="5fa91-146">"v1.1.4322"</span><span class="sxs-lookup"><span data-stu-id="5fa91-146">"v1.1.4322"</span></span>|  
|<span data-ttu-id="5fa91-147">2.0</span><span class="sxs-lookup"><span data-stu-id="5fa91-147">2.0</span></span>|<span data-ttu-id="5fa91-148">"v2.0.50727"</span><span class="sxs-lookup"><span data-stu-id="5fa91-148">"v2.0.50727"</span></span>|  
|<span data-ttu-id="5fa91-149">3.0</span><span class="sxs-lookup"><span data-stu-id="5fa91-149">3.0</span></span>|<span data-ttu-id="5fa91-150">"v2.0.50727"</span><span class="sxs-lookup"><span data-stu-id="5fa91-150">"v2.0.50727"</span></span>|  
|<span data-ttu-id="5fa91-151">3.5</span><span class="sxs-lookup"><span data-stu-id="5fa91-151">3.5</span></span>|<span data-ttu-id="5fa91-152">"v2.0.50727"</span><span class="sxs-lookup"><span data-stu-id="5fa91-152">"v2.0.50727"</span></span>|  
|<span data-ttu-id="5fa91-153">4.0 4.7.2</span><span class="sxs-lookup"><span data-stu-id="5fa91-153">4.0-4.7.2</span></span>|<span data-ttu-id="5fa91-154">"v4.0"</span><span class="sxs-lookup"><span data-stu-id="5fa91-154">"v4.0"</span></span>|  

<a name="sku"></a>   
## <a name="sku-id-values"></a><span data-ttu-id="5fa91-155">“SKU ID”值</span><span class="sxs-lookup"><span data-stu-id="5fa91-155">"sku id" values</span></span>

<span data-ttu-id="5fa91-156">`sku`特性使用目标框架名字对象 (TFM) 以指示应用所面向并运行所需的.NET framework 版本。</span><span class="sxs-lookup"><span data-stu-id="5fa91-156">The `sku` attribute uses a target framework moniker (TFM) to indicate the version of the .NET Framework that the app targets and requires to run.</span></span> <span data-ttu-id="5fa91-157">下表列出了受支持的有效值`sku`属性，从.NET Framework 4 开始。</span><span class="sxs-lookup"><span data-stu-id="5fa91-157">The following table lists valid values that are supported by the `sku` attribute, starting with the .NET Framework 4.</span></span>
  
|<span data-ttu-id="5fa91-158">.NET Framework 版本</span><span class="sxs-lookup"><span data-stu-id="5fa91-158">.NET Framework version</span></span>|<span data-ttu-id="5fa91-159">`sku` 特性</span><span class="sxs-lookup"><span data-stu-id="5fa91-159">`sku` attribute</span></span>|  
|----------------------------|---------------------|  
|<span data-ttu-id="5fa91-160">4.0</span><span class="sxs-lookup"><span data-stu-id="5fa91-160">4.0</span></span>|<span data-ttu-id="5fa91-161">".NETFramework,Version=v4.0"</span><span class="sxs-lookup"><span data-stu-id="5fa91-161">".NETFramework,Version=v4.0"</span></span>|  
|<span data-ttu-id="5fa91-162">4.0，客户端配置文件</span><span class="sxs-lookup"><span data-stu-id="5fa91-162">4.0, Client Profile</span></span>|<span data-ttu-id="5fa91-163">".NETFramework,Version=v4.0,Profile=Client"</span><span class="sxs-lookup"><span data-stu-id="5fa91-163">".NETFramework,Version=v4.0,Profile=Client"</span></span>|  
|<span data-ttu-id="5fa91-164">4.0，平台更新 1</span><span class="sxs-lookup"><span data-stu-id="5fa91-164">4.0, platform update 1</span></span>|<span data-ttu-id="5fa91-165">.NETFramework,Version=v4.0.1</span><span class="sxs-lookup"><span data-stu-id="5fa91-165">.NETFramework,Version=v4.0.1</span></span>|  
|<span data-ttu-id="5fa91-166">4.0，客户端配置文件，Update 1</span><span class="sxs-lookup"><span data-stu-id="5fa91-166">4.0, Client Profile, update 1</span></span>|<span data-ttu-id="5fa91-167">.NETFramework,Version=v4.0.1,Profile=Client</span><span class="sxs-lookup"><span data-stu-id="5fa91-167">.NETFramework,Version=v4.0.1,Profile=Client</span></span>|  
|<span data-ttu-id="5fa91-168">4.0，平台更新 2</span><span class="sxs-lookup"><span data-stu-id="5fa91-168">4.0, platform update 2</span></span>|<span data-ttu-id="5fa91-169">.NETFramework,Version=v4.0.2</span><span class="sxs-lookup"><span data-stu-id="5fa91-169">.NETFramework,Version=v4.0.2</span></span>|  
|<span data-ttu-id="5fa91-170">4.0，客户端配置文件，Update 2</span><span class="sxs-lookup"><span data-stu-id="5fa91-170">4.0, Client Profile, update 2</span></span>|<span data-ttu-id="5fa91-171">.NETFramework,Version=v4.0.2,Profile=Client</span><span class="sxs-lookup"><span data-stu-id="5fa91-171">.NETFramework,Version=v4.0.2,Profile=Client</span></span>|  
|<span data-ttu-id="5fa91-172">4.0，平台更新 3</span><span class="sxs-lookup"><span data-stu-id="5fa91-172">4.0, platform update 3</span></span>|<span data-ttu-id="5fa91-173">.NETFramework,Version=v4.0.3</span><span class="sxs-lookup"><span data-stu-id="5fa91-173">.NETFramework,Version=v4.0.3</span></span>|  
|<span data-ttu-id="5fa91-174">4.0，客户端配置文件，Update 3</span><span class="sxs-lookup"><span data-stu-id="5fa91-174">4.0, Client Profile, update 3</span></span>|<span data-ttu-id="5fa91-175">.NETFramework,Version=v4.0.3,Profile=Client</span><span class="sxs-lookup"><span data-stu-id="5fa91-175">.NETFramework,Version=v4.0.3,Profile=Client</span></span>|  
|<span data-ttu-id="5fa91-176">4.5</span><span class="sxs-lookup"><span data-stu-id="5fa91-176">4.5</span></span>|<span data-ttu-id="5fa91-177">".NETFramework,Version=v4.5"</span><span class="sxs-lookup"><span data-stu-id="5fa91-177">".NETFramework,Version=v4.5"</span></span>|  
|<span data-ttu-id="5fa91-178">4.5.1</span><span class="sxs-lookup"><span data-stu-id="5fa91-178">4.5.1</span></span>|<span data-ttu-id="5fa91-179">".NETFramework,Version=v4.5"</span><span class="sxs-lookup"><span data-stu-id="5fa91-179">".NETFramework,Version=v4.5.1"</span></span>|  
|<span data-ttu-id="5fa91-180">4.5.2</span><span class="sxs-lookup"><span data-stu-id="5fa91-180">4.5.2</span></span>|<span data-ttu-id="5fa91-181">".NETFramework,Version=v4.5"</span><span class="sxs-lookup"><span data-stu-id="5fa91-181">".NETFramework,Version=v4.5.2"</span></span>|  
|<span data-ttu-id="5fa91-182">4.6</span><span class="sxs-lookup"><span data-stu-id="5fa91-182">4.6</span></span>|<span data-ttu-id="5fa91-183">".NETFramework,Version=v4.5"</span><span class="sxs-lookup"><span data-stu-id="5fa91-183">".NETFramework,Version=v4.6"</span></span>|  
|<span data-ttu-id="5fa91-184">4.6.1</span><span class="sxs-lookup"><span data-stu-id="5fa91-184">4.6.1</span></span>|<span data-ttu-id="5fa91-185">".NETFramework,Version=v4.5"</span><span class="sxs-lookup"><span data-stu-id="5fa91-185">".NETFramework,Version=v4.6.1"</span></span>|  
|<span data-ttu-id="5fa91-186">4.6.2</span><span class="sxs-lookup"><span data-stu-id="5fa91-186">4.6.2</span></span>|<span data-ttu-id="5fa91-187">".NETFramework,Version=v4.6.2"</span><span class="sxs-lookup"><span data-stu-id="5fa91-187">".NETFramework,Version=v4.6.2"</span></span>|  
|<span data-ttu-id="5fa91-188">4.7</span><span class="sxs-lookup"><span data-stu-id="5fa91-188">4.7</span></span>|<span data-ttu-id="5fa91-189">".NETFramework,Version=v4.7"</span><span class="sxs-lookup"><span data-stu-id="5fa91-189">".NETFramework,Version=v4.7"</span></span>|
|<span data-ttu-id="5fa91-190">4.7.1</span><span class="sxs-lookup"><span data-stu-id="5fa91-190">4.7.1</span></span>|<span data-ttu-id="5fa91-191">".NETFramework,Version=v4.7.1"</span><span class="sxs-lookup"><span data-stu-id="5fa91-191">".NETFramework,Version=v4.7.1"</span></span>|
|<span data-ttu-id="5fa91-192">4.7.2</span><span class="sxs-lookup"><span data-stu-id="5fa91-192">4.7.2</span></span>|<span data-ttu-id="5fa91-193">".NETFramework，版本 = v4.7.2"</span><span class="sxs-lookup"><span data-stu-id="5fa91-193">".NETFramework,Version=v4.7.2"</span></span>|

## <a name="example"></a><span data-ttu-id="5fa91-194">示例</span><span class="sxs-lookup"><span data-stu-id="5fa91-194">Example</span></span>  
 <span data-ttu-id="5fa91-195">下面的示例演示如何在配置文件中指定支持的运行时版本。</span><span class="sxs-lookup"><span data-stu-id="5fa91-195">The following example shows how to specify the supported runtime version in a configuration file.</span></span> <span data-ttu-id="5fa91-196">配置文件指示应用面向.NET Framework 4.7。</span><span class="sxs-lookup"><span data-stu-id="5fa91-196">The configuration file indicates that the app targets the .NET Framework 4.7.</span></span>  
  
```xml  
<configuration>  
   <startup>  
      <supportedRuntime version="v4.0" sku=".NETFramework,Version=v4.7" />  
   </startup>  
</configuration>  
```  
  
## <a name="configuration-file"></a><span data-ttu-id="5fa91-197">配置文件</span><span class="sxs-lookup"><span data-stu-id="5fa91-197">Configuration file</span></span>

<span data-ttu-id="5fa91-198">此元素可用于应用程序配置文件中。</span><span class="sxs-lookup"><span data-stu-id="5fa91-198">This element can be used in the application configuration file.</span></span>

## <a name="see-also"></a><span data-ttu-id="5fa91-199">请参阅</span><span class="sxs-lookup"><span data-stu-id="5fa91-199">See also</span></span>

 [<span data-ttu-id="5fa91-200">启动设置架构</span><span class="sxs-lookup"><span data-stu-id="5fa91-200">Startup Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/startup/index.md)  
 [<span data-ttu-id="5fa91-201">配置文件架构</span><span class="sxs-lookup"><span data-stu-id="5fa91-201">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [<span data-ttu-id="5fa91-202">进程内并行执行</span><span class="sxs-lookup"><span data-stu-id="5fa91-202">In-Process Side-by-Side Execution</span></span>](../../../../../docs/framework/deployment/in-process-side-by-side-execution.md)  
