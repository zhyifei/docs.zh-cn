---
title: <supportedRuntime> 配置元素的.NET
ms.date: 04/02/2019
ms.custom: updateeachrelease
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#supportedRuntime
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/startup/supportedRuntime
helpviewer_keywords:
- supportedRuntime element
- <supportedRuntime> element
ms.assetid: 1ae16e23-afbe-4de4-b413-bc457f37b69f
ms.openlocfilehash: cc55809ecaffa4cab4fa4336f9f7f5c06debde2d
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/15/2019
ms.locfileid: "65634206"
---
# <a name="supportedruntime-element"></a><span data-ttu-id="38520-102">\<supportedRuntime > 元素</span><span class="sxs-lookup"><span data-stu-id="38520-102">\<supportedRuntime> element</span></span>

<span data-ttu-id="38520-103">指定的公共语言运行时版本和 （可选） 应用程序的.NET Framework 版本支持。</span><span class="sxs-lookup"><span data-stu-id="38520-103">Specifies which common language runtime version and, optionally, .NET Framework version the application supports.</span></span>  

[<span data-ttu-id="38520-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="38520-104">\<configuration></span></span>](../configuration-element.md)  
<span data-ttu-id="38520-105">&nbsp;&nbsp;[\<startup>](../startup/startup-element.md)</span><span class="sxs-lookup"><span data-stu-id="38520-105">&nbsp;&nbsp;[\<startup>](../startup/startup-element.md)</span></span>  
<span data-ttu-id="38520-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<supportedRuntime>**</span><span class="sxs-lookup"><span data-stu-id="38520-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<supportedRuntime>**</span></span>  

## <a name="syntax"></a><span data-ttu-id="38520-107">语法</span><span class="sxs-lookup"><span data-stu-id="38520-107">Syntax</span></span>

```xml
<supportedRuntime version="runtime version" sku="sku id"/>
```

## <a name="attributes"></a><span data-ttu-id="38520-108">特性</span><span class="sxs-lookup"><span data-stu-id="38520-108">Attributes</span></span>

|<span data-ttu-id="38520-109">特性</span><span class="sxs-lookup"><span data-stu-id="38520-109">Attribute</span></span>|<span data-ttu-id="38520-110">描述</span><span class="sxs-lookup"><span data-stu-id="38520-110">Description</span></span>|
|---------------|-----------------|
|<span data-ttu-id="38520-111">**版本**</span><span class="sxs-lookup"><span data-stu-id="38520-111">**version**</span></span>|<span data-ttu-id="38520-112">可选特性。</span><span class="sxs-lookup"><span data-stu-id="38520-112">Optional attribute.</span></span><br /><br /> <span data-ttu-id="38520-113">一个字符串值，它指定此应用程序支持的公共语言运行时 (CLR) 版本。</span><span class="sxs-lookup"><span data-stu-id="38520-113">A string value that specifies the version of the common language runtime (CLR) that this application supports.</span></span> <span data-ttu-id="38520-114">有关的有效值`version`属性，请参阅["运行时版本"值](#version)部分。</span><span class="sxs-lookup"><span data-stu-id="38520-114">For valid values of the `version` attribute, see the ["runtime version" values](#version) section.</span></span> <span data-ttu-id="38520-115">**注意：** 通过.NET Framework 3.5"*运行时版本*"值的形式*主要*。*次要*。*生成*。</span><span class="sxs-lookup"><span data-stu-id="38520-115">**Note:**  Through the .NET Framework 3.5, the "*runtime version*" value takes the form *major*.*minor*.*build*.</span></span> <span data-ttu-id="38520-116">从 [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)] 开始，仅主版本号和次版本号是必需的（即“v4.0”而不是“v4.0.30319”）。</span><span class="sxs-lookup"><span data-stu-id="38520-116">Beginning with the [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)], only the major and minor version numbers are required (that is, "v4.0" instead of "v4.0.30319").</span></span> <span data-ttu-id="38520-117">建议使用较短字符串。</span><span class="sxs-lookup"><span data-stu-id="38520-117">The shorter string is recommended.</span></span>|
|<span data-ttu-id="38520-118">**sku**</span><span class="sxs-lookup"><span data-stu-id="38520-118">**sku**</span></span>|<span data-ttu-id="38520-119">可选特性。</span><span class="sxs-lookup"><span data-stu-id="38520-119">Optional attribute.</span></span><br /><br /> <span data-ttu-id="38520-120">一个字符串值，该值指定库存单位 (SKU)，库存单位则指定此应用程序支持的 .NET Framework 版本。</span><span class="sxs-lookup"><span data-stu-id="38520-120">A string value that specifies the stock-keeping unit (SKU), which in turn specifies which .NET Framework release this application supports.</span></span><br /><br /> <span data-ttu-id="38520-121">从 .NET Framework 4.0 起，建议使用 `sku` 特性。</span><span class="sxs-lookup"><span data-stu-id="38520-121">Starting with the .NET Framework 4.0, the use of the `sku` attribute is recommended.</span></span>  <span data-ttu-id="38520-122">若存在该特性，则它指示应用面向的 .NET Framework 版本。</span><span class="sxs-lookup"><span data-stu-id="38520-122">When present, it indicates the version of the .NET Framework that the app targets.</span></span><br /><br /> <span data-ttu-id="38520-123">有关有效的 sku 属性的值，请参阅["sku id"值](#sku)部分。</span><span class="sxs-lookup"><span data-stu-id="38520-123">For valid values of the sku attribute, see the ["sku id" values](#sku) section.</span></span>|

## <a name="remarks"></a><span data-ttu-id="38520-124">备注</span><span class="sxs-lookup"><span data-stu-id="38520-124">Remarks</span></span>

<span data-ttu-id="38520-125">如果 **\<supportedRuntime>** 元素不存在应用程序配置文件，请使用用于生成应用程序的运行时的版本。</span><span class="sxs-lookup"><span data-stu-id="38520-125">If the **\<supportedRuntime>** element is not present in the application configuration file, the version of the runtime used to build the application is used.</span></span>

<span data-ttu-id="38520-126">**\<SupportedRuntime>** 元素应由使用 1.1 版或更高版本的运行时版本生成的所有应用程序。</span><span class="sxs-lookup"><span data-stu-id="38520-126">The **\<supportedRuntime>** element should be used by all applications built using version 1.1 or later of the runtime.</span></span> <span data-ttu-id="38520-127">仅支持 1.0 版的运行时生成的应用程序必须使用[ \<requiredRuntime >](../startup/requiredruntime-element.md)元素。</span><span class="sxs-lookup"><span data-stu-id="38520-127">Applications built to support only version 1.0 of the runtime must use the [\<requiredRuntime>](../startup/requiredruntime-element.md) element.</span></span>

> [!NOTE]
> <span data-ttu-id="38520-128">如果您使用[CorBindToRuntimeByCfg](../../../unmanaged-api/hosting/corbindtoruntimebycfg-function.md)函数以指定配置文件，则必须使用`<requiredRuntime>`所有版本的运行时的元素。</span><span class="sxs-lookup"><span data-stu-id="38520-128">If you use the [CorBindToRuntimeByCfg](../../../unmanaged-api/hosting/corbindtoruntimebycfg-function.md) function to specify the configuration file, you must use the `<requiredRuntime>` element for all versions of the runtime.</span></span> <span data-ttu-id="38520-129">`<supportedRuntime>`使用时，将忽略元素[CorBindToRuntimeByCfg](../../../unmanaged-api/hosting/corbindtoruntimebycfg-function.md)。</span><span class="sxs-lookup"><span data-stu-id="38520-129">The `<supportedRuntime>` element is ignored when you use [CorBindToRuntimeByCfg](../../../unmanaged-api/hosting/corbindtoruntimebycfg-function.md).</span></span>  
  
<span data-ttu-id="38520-130">对于支持从 .NET Framework 1.1 到 3.5 的运行时版本的应用，支持多个运行时版本时，第一个元素应指定优先级最高的版本，最后一个元素应指定优先级最低的版本。</span><span class="sxs-lookup"><span data-stu-id="38520-130">For apps that support versions of the runtime from the .NET Framework 1.1 through 3.5, when multiple versions of the runtime are supported, the first element should specify the most preferred version of the runtime, and the last element should specify the least preferred version.</span></span> <span data-ttu-id="38520-131">对于支持的.NET Framework 4.0 或更高版本的应用`version`属性指示的 CLR 版本，这是普遍适用于.NET Framework 4 和更高版本，并且`sku`属性指示的单个.NET Framework 版本的应用程序的目标。</span><span class="sxs-lookup"><span data-stu-id="38520-131">For apps that support the .NET Framework 4.0 or later versions, the `version` attribute indicates the CLR version, which is common to the .NET Framework 4 and later versions, and the `sku` attribute indicates the single .NET Framework version that the app targets.</span></span> 

<span data-ttu-id="38520-132">如果 **\<supportedRuntime >** 具有元素`sku`属性配置文件中存在且已安装的.NET Framework 版本为较低则指定的受支持的版本，该应用程序无法运行，而是显示一条消息询问要安装受支持的版本。</span><span class="sxs-lookup"><span data-stu-id="38520-132">If the **\<supportedRuntime>** element with the `sku` attribute is present in the configuration file and the installed .NET Framework version is lower then the specified supported version, the application fails to run and instead displays a message asking to install the supported version.</span></span> <span data-ttu-id="38520-133">否则为应用程序尝试任何已安装的版本上运行，但它可能出现意外行为是否不与该版本完全兼容。</span><span class="sxs-lookup"><span data-stu-id="38520-133">Otherwise, the application attempts to run on any installed version, but it may behave unexpectedly if it is not fully compatible with that version.</span></span> <span data-ttu-id="38520-134">(有关兼容性的.NET Framework 版本之间的差异，请参阅[.NET Framework 中的应用程序兼容性](https://docs.microsoft.com/dotnet/framework/migration-guide/application-compatibility)。)因此，我们建议您在更容易错误诊断的应用程序配置文件中包含此元素。</span><span class="sxs-lookup"><span data-stu-id="38520-134">(For compatibility differences between versions of .NET Framework, see [Application compatibility in the .NET Framework](https://docs.microsoft.com/dotnet/framework/migration-guide/application-compatibility).) Therefore, we recommend that you include this element in the application configuration file for easier error diagnostics.</span></span> <span data-ttu-id="38520-135">（已创建新项目时由 Visual Studio 自动生成的配置文件包含它。）</span><span class="sxs-lookup"><span data-stu-id="38520-135">(The configuration file automatically generated by Visual Studio when creating a new project already contains it.)</span></span>
  
> [!NOTE]
> <span data-ttu-id="38520-136">如果你的应用程序使用旧式激活路径，如[CorBindToRuntimeEx 函数](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md)，并且希望这些路径来激活而不是早期版本的 CLR 版本 4 或如果你的应用程序使用生成[!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)]具有依赖关系，但在上使用.NET Framework 的早期版本构建的混合模式程序集，它不是只需指定[!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)]在受支持运行时列表中。</span><span class="sxs-lookup"><span data-stu-id="38520-136">If your application uses legacy activation paths, such as the [CorBindToRuntimeEx function](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md), and you want those paths to activate version 4 of the CLR instead of an earlier version, or if your application is built with the [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] but has a dependency on a mixed-mode assembly built with an earlier version of the .NET Framework, it is not sufficient to specify the [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] in the list of supported runtimes.</span></span> <span data-ttu-id="38520-137">此外，在[\<启动 > 元素](../startup/startup-element.md)在配置文件中，必须设置`useLegacyV2RuntimeActivationPolicy`归于`true`。</span><span class="sxs-lookup"><span data-stu-id="38520-137">In addition, in the [\<startup> element](../startup/startup-element.md) in your configuration file, you must set the `useLegacyV2RuntimeActivationPolicy` attribute to `true`.</span></span> <span data-ttu-id="38520-138">但是，将此特性设置为 `true` 意味着，用 .NET Framework 早期版本生成的所有组件都使用 [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)]（而不是生成它们时所用的运行时）运行。</span><span class="sxs-lookup"><span data-stu-id="38520-138">However, setting this attribute to `true` means that all components built with earlier versions of the .NET Framework are run using the [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] instead of the runtimes they were built with.</span></span>

<span data-ttu-id="38520-139">我们建议你使用应用程序可在其上运行的所有 .NET Framework 版本来测试这些应用程序。</span><span class="sxs-lookup"><span data-stu-id="38520-139">We recommend that you test applications with all the .NET Framework versions that they can run on.</span></span>

<a name="version"></a> 
## <a name="runtime-version-values"></a><span data-ttu-id="38520-140">“运行时版本”值</span><span class="sxs-lookup"><span data-stu-id="38520-140">"runtime version" values</span></span>
<span data-ttu-id="38520-141">`runtime`属性指定给定应用程序所需的公共语言运行时 (CLR) 版本。</span><span class="sxs-lookup"><span data-stu-id="38520-141">The `runtime` attribute specifies the Common Language Runtime (CLR) version that is required for a given application.</span></span> <span data-ttu-id="38520-142">请注意，所有.NET Framework v4.x 版本都指定`v4.0`CLR。</span><span class="sxs-lookup"><span data-stu-id="38520-142">Note that all .NET Framework v4.x versions specify the `v4.0` CLR.</span></span> <span data-ttu-id="38520-143">下表列出了有效值*运行时版本*的值`version`属性。</span><span class="sxs-lookup"><span data-stu-id="38520-143">The following table lists valid values for the *runtime version* value of the `version` attribute.</span></span>

|<span data-ttu-id="38520-144">.NET Framework 版本</span><span class="sxs-lookup"><span data-stu-id="38520-144">.NET Framework version</span></span>|<span data-ttu-id="38520-145">`version` 属性</span><span class="sxs-lookup"><span data-stu-id="38520-145">`version` attribute</span></span>|
|----------------------------|-------------------------|
|<span data-ttu-id="38520-146">1.0</span><span class="sxs-lookup"><span data-stu-id="38520-146">1.0</span></span>|<span data-ttu-id="38520-147">"v1.0.3705"</span><span class="sxs-lookup"><span data-stu-id="38520-147">"v1.0.3705"</span></span>|
|<span data-ttu-id="38520-148">1.1</span><span class="sxs-lookup"><span data-stu-id="38520-148">1.1</span></span>|<span data-ttu-id="38520-149">"v1.1.4322"</span><span class="sxs-lookup"><span data-stu-id="38520-149">"v1.1.4322"</span></span>|
|<span data-ttu-id="38520-150">2.0</span><span class="sxs-lookup"><span data-stu-id="38520-150">2.0</span></span>|<span data-ttu-id="38520-151">"v2.0.50727"</span><span class="sxs-lookup"><span data-stu-id="38520-151">"v2.0.50727"</span></span>|
|<span data-ttu-id="38520-152">3.0</span><span class="sxs-lookup"><span data-stu-id="38520-152">3.0</span></span>|<span data-ttu-id="38520-153">"v2.0.50727"</span><span class="sxs-lookup"><span data-stu-id="38520-153">"v2.0.50727"</span></span>|
|<span data-ttu-id="38520-154">3.5</span><span class="sxs-lookup"><span data-stu-id="38520-154">3.5</span></span>|<span data-ttu-id="38520-155">"v2.0.50727"</span><span class="sxs-lookup"><span data-stu-id="38520-155">"v2.0.50727"</span></span>|
|<span data-ttu-id="38520-156">4.0-4.8</span><span class="sxs-lookup"><span data-stu-id="38520-156">4.0-4.8</span></span>|<span data-ttu-id="38520-157">"v4.0"</span><span class="sxs-lookup"><span data-stu-id="38520-157">"v4.0"</span></span>|

## <a name="sku"></a> <span data-ttu-id="38520-158">"sku id"值</span><span class="sxs-lookup"><span data-stu-id="38520-158">"sku id" values</span></span>

<span data-ttu-id="38520-159">`sku`特性使用目标框架名字对象 (TFM) 以指示应用所面向并运行所需的.NET framework 版本。</span><span class="sxs-lookup"><span data-stu-id="38520-159">The `sku` attribute uses a target framework moniker (TFM) to indicate the version of the .NET Framework that the app targets and requires to run.</span></span> <span data-ttu-id="38520-160">下表列出了受支持的有效值`sku`属性，从.NET Framework 4 开始。</span><span class="sxs-lookup"><span data-stu-id="38520-160">The following table lists valid values that are supported by the `sku` attribute, starting with the .NET Framework 4.</span></span>

|<span data-ttu-id="38520-161">.NET Framework 版本</span><span class="sxs-lookup"><span data-stu-id="38520-161">.NET Framework version</span></span>|<span data-ttu-id="38520-162">`sku` 属性</span><span class="sxs-lookup"><span data-stu-id="38520-162">`sku` attribute</span></span>|
|----------------------------|---------------------|
|<span data-ttu-id="38520-163">4.0</span><span class="sxs-lookup"><span data-stu-id="38520-163">4.0</span></span>|<span data-ttu-id="38520-164">".NETFramework,Version=v4.0"</span><span class="sxs-lookup"><span data-stu-id="38520-164">".NETFramework,Version=v4.0"</span></span>|
|<span data-ttu-id="38520-165">4.0，客户端配置文件</span><span class="sxs-lookup"><span data-stu-id="38520-165">4.0, Client Profile</span></span>|<span data-ttu-id="38520-166">".NETFramework,Version=v4.0,Profile=Client"</span><span class="sxs-lookup"><span data-stu-id="38520-166">".NETFramework,Version=v4.0,Profile=Client"</span></span>|
|<span data-ttu-id="38520-167">4.0，平台更新 1</span><span class="sxs-lookup"><span data-stu-id="38520-167">4.0, platform update 1</span></span>|<span data-ttu-id="38520-168">".NETFramework,Version=v4.0.1"</span><span class="sxs-lookup"><span data-stu-id="38520-168">".NETFramework,Version=v4.0.1"</span></span>|
|<span data-ttu-id="38520-169">4.0，客户端配置文件，Update 1</span><span class="sxs-lookup"><span data-stu-id="38520-169">4.0, Client Profile, update 1</span></span>|<span data-ttu-id="38520-170">".NETFramework,Version=v4.0.1,Profile=Client"</span><span class="sxs-lookup"><span data-stu-id="38520-170">".NETFramework,Version=v4.0.1,Profile=Client"</span></span>|
|<span data-ttu-id="38520-171">4.0，平台更新 2</span><span class="sxs-lookup"><span data-stu-id="38520-171">4.0, platform update 2</span></span>|<span data-ttu-id="38520-172">".NETFramework,Version=v4.0.2"</span><span class="sxs-lookup"><span data-stu-id="38520-172">".NETFramework,Version=v4.0.2"</span></span>|
|<span data-ttu-id="38520-173">4.0，客户端配置文件，Update 2</span><span class="sxs-lookup"><span data-stu-id="38520-173">4.0, Client Profile, update 2</span></span>|<span data-ttu-id="38520-174">".NETFramework,Version=v4.0.2,Profile=Client"</span><span class="sxs-lookup"><span data-stu-id="38520-174">".NETFramework,Version=v4.0.2,Profile=Client"</span></span>|
|<span data-ttu-id="38520-175">4.0，平台更新 3</span><span class="sxs-lookup"><span data-stu-id="38520-175">4.0, platform update 3</span></span>|<span data-ttu-id="38520-176">".NETFramework,Version=v4.0.3"</span><span class="sxs-lookup"><span data-stu-id="38520-176">".NETFramework,Version=v4.0.3"</span></span>|
|<span data-ttu-id="38520-177">4.0，客户端配置文件，Update 3</span><span class="sxs-lookup"><span data-stu-id="38520-177">4.0, Client Profile, update 3</span></span>|<span data-ttu-id="38520-178">".NETFramework,Version=v4.0.3,Profile=Client"</span><span class="sxs-lookup"><span data-stu-id="38520-178">".NETFramework,Version=v4.0.3,Profile=Client"</span></span>|
|<span data-ttu-id="38520-179">4.5</span><span class="sxs-lookup"><span data-stu-id="38520-179">4.5</span></span>|<span data-ttu-id="38520-180">".NETFramework,Version=v4.5"</span><span class="sxs-lookup"><span data-stu-id="38520-180">".NETFramework,Version=v4.5"</span></span>|
|<span data-ttu-id="38520-181">4.5.1</span><span class="sxs-lookup"><span data-stu-id="38520-181">4.5.1</span></span>|<span data-ttu-id="38520-182">".NETFramework,Version=v4.5"</span><span class="sxs-lookup"><span data-stu-id="38520-182">".NETFramework,Version=v4.5.1"</span></span>|
|<span data-ttu-id="38520-183">4.5.2</span><span class="sxs-lookup"><span data-stu-id="38520-183">4.5.2</span></span>|<span data-ttu-id="38520-184">".NETFramework,Version=v4.5"</span><span class="sxs-lookup"><span data-stu-id="38520-184">".NETFramework,Version=v4.5.2"</span></span>|
|<span data-ttu-id="38520-185">4.6</span><span class="sxs-lookup"><span data-stu-id="38520-185">4.6</span></span>|<span data-ttu-id="38520-186">".NETFramework,Version=v4.5"</span><span class="sxs-lookup"><span data-stu-id="38520-186">".NETFramework,Version=v4.6"</span></span>|
|<span data-ttu-id="38520-187">4.6.1</span><span class="sxs-lookup"><span data-stu-id="38520-187">4.6.1</span></span>|<span data-ttu-id="38520-188">".NETFramework,Version=v4.5"</span><span class="sxs-lookup"><span data-stu-id="38520-188">".NETFramework,Version=v4.6.1"</span></span>|
|<span data-ttu-id="38520-189">4.6.2</span><span class="sxs-lookup"><span data-stu-id="38520-189">4.6.2</span></span>|<span data-ttu-id="38520-190">".NETFramework,Version=v4.6.2"</span><span class="sxs-lookup"><span data-stu-id="38520-190">".NETFramework,Version=v4.6.2"</span></span>|
|<span data-ttu-id="38520-191">4.7</span><span class="sxs-lookup"><span data-stu-id="38520-191">4.7</span></span>|<span data-ttu-id="38520-192">".NETFramework,Version=v4.7"</span><span class="sxs-lookup"><span data-stu-id="38520-192">".NETFramework,Version=v4.7"</span></span>|
|<span data-ttu-id="38520-193">4.7.1</span><span class="sxs-lookup"><span data-stu-id="38520-193">4.7.1</span></span>|<span data-ttu-id="38520-194">".NETFramework,Version=v4.7.1"</span><span class="sxs-lookup"><span data-stu-id="38520-194">".NETFramework,Version=v4.7.1"</span></span>|
|<span data-ttu-id="38520-195">4.7.2</span><span class="sxs-lookup"><span data-stu-id="38520-195">4.7.2</span></span>|<span data-ttu-id="38520-196">".NETFramework，版本 = v4.7.2"</span><span class="sxs-lookup"><span data-stu-id="38520-196">".NETFramework,Version=v4.7.2"</span></span>|
|<span data-ttu-id="38520-197">4.8</span><span class="sxs-lookup"><span data-stu-id="38520-197">4.8</span></span>|<span data-ttu-id="38520-198">".NETFramework,Version=v4.8"</span><span class="sxs-lookup"><span data-stu-id="38520-198">".NETFramework,Version=v4.8"</span></span>|

## <a name="example"></a><span data-ttu-id="38520-199">示例</span><span class="sxs-lookup"><span data-stu-id="38520-199">Example</span></span>

<span data-ttu-id="38520-200">下面的示例演示如何在配置文件中指定支持的运行时版本。</span><span class="sxs-lookup"><span data-stu-id="38520-200">The following example shows how to specify the supported runtime version in a configuration file.</span></span> <span data-ttu-id="38520-201">配置文件指示应用面向.NET Framework 4.7。</span><span class="sxs-lookup"><span data-stu-id="38520-201">The configuration file indicates that the app targets the .NET Framework 4.7.</span></span>

```xml
<configuration>
   <startup>
      <supportedRuntime version="v4.0" sku=".NETFramework,Version=v4.7" />
   </startup>
</configuration>
```

## <a name="configuration-file"></a><span data-ttu-id="38520-202">配置文件</span><span class="sxs-lookup"><span data-stu-id="38520-202">Configuration file</span></span>

<span data-ttu-id="38520-203">此元素可用于应用程序配置文件中。</span><span class="sxs-lookup"><span data-stu-id="38520-203">This element can be used in the application configuration file.</span></span>

## <a name="see-also"></a><span data-ttu-id="38520-204">请参阅</span><span class="sxs-lookup"><span data-stu-id="38520-204">See also</span></span>

- [<span data-ttu-id="38520-205">启动设置架构</span><span class="sxs-lookup"><span data-stu-id="38520-205">Startup Settings Schema</span></span>](../startup/index.md)
- [<span data-ttu-id="38520-206">配置文件架构</span><span class="sxs-lookup"><span data-stu-id="38520-206">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="38520-207">进程内并行执行</span><span class="sxs-lookup"><span data-stu-id="38520-207">In-Process Side-by-Side Execution</span></span>](../../../deployment/in-process-side-by-side-execution.md)
