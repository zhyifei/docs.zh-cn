---
title: <supportedRuntime> 配置元素-.NET
ms.date: 04/02/2019
ms.custom: updateeachrelease
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#supportedRuntime
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/startup/supportedRuntime
helpviewer_keywords:
- supportedRuntime element
- <supportedRuntime> element
ms.assetid: 1ae16e23-afbe-4de4-b413-bc457f37b69f
ms.openlocfilehash: 5e7fc5f81468ff7c4eba8145ee42a4c7cf8bc0b8
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/01/2019
ms.locfileid: "71697524"
---
# <a name="supportedruntime-element"></a><span data-ttu-id="48b15-102">\<supportedRuntime > 元素</span><span class="sxs-lookup"><span data-stu-id="48b15-102">\<supportedRuntime> element</span></span>

<span data-ttu-id="48b15-103">指定应用程序支持的公共语言运行时版本和（可选） .NET Framework 版本。</span><span class="sxs-lookup"><span data-stu-id="48b15-103">Specifies which common language runtime version and, optionally, .NET Framework version the application supports.</span></span>  

[<span data-ttu-id="48b15-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="48b15-104">\<configuration></span></span>](../configuration-element.md)  
<span data-ttu-id="48b15-105">&nbsp;&nbsp;[\<startup>](startup-element.md)</span><span class="sxs-lookup"><span data-stu-id="48b15-105">&nbsp;&nbsp;[\<startup>](startup-element.md)</span></span>  
<span data-ttu-id="48b15-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<supportedRuntime>**</span><span class="sxs-lookup"><span data-stu-id="48b15-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<supportedRuntime>**</span></span>  

## <a name="syntax"></a><span data-ttu-id="48b15-107">语法</span><span class="sxs-lookup"><span data-stu-id="48b15-107">Syntax</span></span>

```xml
<supportedRuntime version="runtime version" sku="sku id"/>
```

## <a name="attributes"></a><span data-ttu-id="48b15-108">特性</span><span class="sxs-lookup"><span data-stu-id="48b15-108">Attributes</span></span>

|<span data-ttu-id="48b15-109">特性</span><span class="sxs-lookup"><span data-stu-id="48b15-109">Attribute</span></span>|<span data-ttu-id="48b15-110">描述</span><span class="sxs-lookup"><span data-stu-id="48b15-110">Description</span></span>|
|---------------|-----------------|
|<span data-ttu-id="48b15-111">**版本**</span><span class="sxs-lookup"><span data-stu-id="48b15-111">**version**</span></span>|<span data-ttu-id="48b15-112">可选特性。</span><span class="sxs-lookup"><span data-stu-id="48b15-112">Optional attribute.</span></span><br /><br /> <span data-ttu-id="48b15-113">一个字符串值，它指定此应用程序支持的公共语言运行时 (CLR) 版本。</span><span class="sxs-lookup"><span data-stu-id="48b15-113">A string value that specifies the version of the common language runtime (CLR) that this application supports.</span></span> <span data-ttu-id="48b15-114">对于 `version` 属性的有效值，请参阅["运行时版本" 值](#version)部分。</span><span class="sxs-lookup"><span data-stu-id="48b15-114">For valid values of the `version` attribute, see the ["runtime version" values](#version) section.</span></span> <span data-ttu-id="48b15-115">**注意：** 通过 .NET Framework 3.5，"*运行时版本*" 值采用*主*格式。*次要*。*生成*。</span><span class="sxs-lookup"><span data-stu-id="48b15-115">**Note:**  Through the .NET Framework 3.5, the "*runtime version*" value takes the form *major*.*minor*.*build*.</span></span> <span data-ttu-id="48b15-116">从 .NET Framework 4 开始，只需要主要版本号和次要版本号（即，"4.0.30319" 而不是 "v"）。</span><span class="sxs-lookup"><span data-stu-id="48b15-116">Beginning with the .NET Framework 4, only the major and minor version numbers are required (that is, "v4.0" instead of "v4.0.30319").</span></span> <span data-ttu-id="48b15-117">建议使用较短字符串。</span><span class="sxs-lookup"><span data-stu-id="48b15-117">The shorter string is recommended.</span></span>|
|<span data-ttu-id="48b15-118">**sku**</span><span class="sxs-lookup"><span data-stu-id="48b15-118">**sku**</span></span>|<span data-ttu-id="48b15-119">可选特性。</span><span class="sxs-lookup"><span data-stu-id="48b15-119">Optional attribute.</span></span><br /><br /> <span data-ttu-id="48b15-120">一个字符串值，该值指定库存单位 (SKU)，库存单位则指定此应用程序支持的 .NET Framework 版本。</span><span class="sxs-lookup"><span data-stu-id="48b15-120">A string value that specifies the stock-keeping unit (SKU), which in turn specifies which .NET Framework release this application supports.</span></span><br /><br /> <span data-ttu-id="48b15-121">从 .NET Framework 4.0 起，建议使用 `sku` 特性。</span><span class="sxs-lookup"><span data-stu-id="48b15-121">Starting with the .NET Framework 4.0, the use of the `sku` attribute is recommended.</span></span>  <span data-ttu-id="48b15-122">若存在该特性，则它指示应用面向的 .NET Framework 版本。</span><span class="sxs-lookup"><span data-stu-id="48b15-122">When present, it indicates the version of the .NET Framework that the app targets.</span></span><br /><br /> <span data-ttu-id="48b15-123">有关 sku 属性的有效值，请参阅["sku id" 值](#sku)一节。</span><span class="sxs-lookup"><span data-stu-id="48b15-123">For valid values of the sku attribute, see the ["sku id" values](#sku) section.</span></span>|

## <a name="remarks"></a><span data-ttu-id="48b15-124">备注</span><span class="sxs-lookup"><span data-stu-id="48b15-124">Remarks</span></span>

<span data-ttu-id="48b15-125">如果 **\<supportedRuntime>** 元素不存在应用程序配置文件，请使用用于生成应用程序的运行时的版本。</span><span class="sxs-lookup"><span data-stu-id="48b15-125">If the **\<supportedRuntime>** element is not present in the application configuration file, the version of the runtime used to build the application is used.</span></span>

<span data-ttu-id="48b15-126">**\<SupportedRuntime>** 元素应由使用 1.1 版或更高版本的运行时版本生成的所有应用程序。</span><span class="sxs-lookup"><span data-stu-id="48b15-126">The **\<supportedRuntime>** element should be used by all applications built using version 1.1 or later of the runtime.</span></span> <span data-ttu-id="48b15-127">构建为仅支持1.0 版运行时的应用程序必须使用[@no__t 1requiredRuntime >](../startup/requiredruntime-element.md)元素。</span><span class="sxs-lookup"><span data-stu-id="48b15-127">Applications built to support only version 1.0 of the runtime must use the [\<requiredRuntime>](../startup/requiredruntime-element.md) element.</span></span>

> [!NOTE]
> <span data-ttu-id="48b15-128">如果使用[CorBindToRuntimeByCfg](../../../unmanaged-api/hosting/corbindtoruntimebycfg-function.md)函数来指定配置文件，则必须对所有版本的运行时使用 `<requiredRuntime>` 元素。</span><span class="sxs-lookup"><span data-stu-id="48b15-128">If you use the [CorBindToRuntimeByCfg](../../../unmanaged-api/hosting/corbindtoruntimebycfg-function.md) function to specify the configuration file, you must use the `<requiredRuntime>` element for all versions of the runtime.</span></span> <span data-ttu-id="48b15-129">当使用[CorBindToRuntimeByCfg](../../../unmanaged-api/hosting/corbindtoruntimebycfg-function.md)时，将忽略 `<supportedRuntime>` 元素。</span><span class="sxs-lookup"><span data-stu-id="48b15-129">The `<supportedRuntime>` element is ignored when you use [CorBindToRuntimeByCfg](../../../unmanaged-api/hosting/corbindtoruntimebycfg-function.md).</span></span>  
  
<span data-ttu-id="48b15-130">对于支持从 .NET Framework 1.1 到 3.5 的运行时版本的应用，支持多个运行时版本时，第一个元素应指定优先级最高的版本，最后一个元素应指定优先级最低的版本。</span><span class="sxs-lookup"><span data-stu-id="48b15-130">For apps that support versions of the runtime from the .NET Framework 1.1 through 3.5, when multiple versions of the runtime are supported, the first element should specify the most preferred version of the runtime, and the last element should specify the least preferred version.</span></span> <span data-ttu-id="48b15-131">对于支持 .NET Framework 4.0 或更高版本的应用程序，@no__t 属性指示 CLR 版本（这是 .NET Framework 4 及更高版本所共有的版本），而 `sku` 属性指示应用面向的单个 .NET Framework 版本。</span><span class="sxs-lookup"><span data-stu-id="48b15-131">For apps that support the .NET Framework 4.0 or later versions, the `version` attribute indicates the CLR version, which is common to the .NET Framework 4 and later versions, and the `sku` attribute indicates the single .NET Framework version that the app targets.</span></span> 

<span data-ttu-id="48b15-132">如果配置文件中存在具有 `sku` 属性的 **@no__t 1supportedRuntime >** 元素，并且安装的 .NET Framework 版本低于指定的受支持版本，则应用程序将无法运行，而是显示要求安装受支持版本的消息。</span><span class="sxs-lookup"><span data-stu-id="48b15-132">If the **\<supportedRuntime>** element with the `sku` attribute is present in the configuration file and the installed .NET Framework version is lower then the specified supported version, the application fails to run and instead displays a message asking to install the supported version.</span></span> <span data-ttu-id="48b15-133">否则，应用程序会尝试在任何已安装的版本上运行，但如果该版本与该版本不完全兼容，则它可能会发生意外行为。</span><span class="sxs-lookup"><span data-stu-id="48b15-133">Otherwise, the application attempts to run on any installed version, but it may behave unexpectedly if it is not fully compatible with that version.</span></span> <span data-ttu-id="48b15-134">（若要了解 .NET Framework 版本之间的兼容性差异，请参阅[.NET Framework 中的应用程序兼容性](https://docs.microsoft.com/dotnet/framework/migration-guide/application-compatibility)。）因此，建议你在应用程序配置文件中包括此元素，以便更轻松地诊断错误。</span><span class="sxs-lookup"><span data-stu-id="48b15-134">(For compatibility differences between versions of .NET Framework, see [Application compatibility in the .NET Framework](https://docs.microsoft.com/dotnet/framework/migration-guide/application-compatibility).) Therefore, we recommend that you include this element in the application configuration file for easier error diagnostics.</span></span> <span data-ttu-id="48b15-135">（创建新项目时，由 Visual Studio 自动生成的配置文件已经包含了该文件。）</span><span class="sxs-lookup"><span data-stu-id="48b15-135">(The configuration file automatically generated by Visual Studio when creating a new project already contains it.)</span></span>
  
> [!NOTE]
> <span data-ttu-id="48b15-136">如果你的应用程序使用旧的激活路径（如[CorBindToRuntimeEx 函数](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md)），并且你希望这些路径激活 CLR 的版本4（而不是早期版本），或者如果你的应用程序是使用 .NET Framework 4 生成但具有依赖项，则为; 否则为。在使用 .NET Framework 的早期版本生成的混合模式程序集上，在支持的运行时列表中指定 .NET Framework 4 并不足。</span><span class="sxs-lookup"><span data-stu-id="48b15-136">If your application uses legacy activation paths, such as the [CorBindToRuntimeEx function](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md), and you want those paths to activate version 4 of the CLR instead of an earlier version, or if your application is built with the .NET Framework 4 but has a dependency on a mixed-mode assembly built with an earlier version of the .NET Framework, it is not sufficient to specify the .NET Framework 4 in the list of supported runtimes.</span></span> <span data-ttu-id="48b15-137">此外，在配置文件中的[\<startup > 元素](../startup/startup-element.md)内，必须将 `useLegacyV2RuntimeActivationPolicy` 特性设置为 `true`。</span><span class="sxs-lookup"><span data-stu-id="48b15-137">In addition, in the [\<startup> element](../startup/startup-element.md) in your configuration file, you must set the `useLegacyV2RuntimeActivationPolicy` attribute to `true`.</span></span> <span data-ttu-id="48b15-138">但是，如果将此属性设置为 `true`，则意味着使用 .NET Framework 的早期版本生成的所有组件都是使用 .NET Framework 4 （而不是生成它们的运行时）运行的。</span><span class="sxs-lookup"><span data-stu-id="48b15-138">However, setting this attribute to `true` means that all components built with earlier versions of the .NET Framework are run using the .NET Framework 4 instead of the runtimes they were built with.</span></span>

<span data-ttu-id="48b15-139">我们建议你使用应用程序可在其上运行的所有 .NET Framework 版本来测试这些应用程序。</span><span class="sxs-lookup"><span data-stu-id="48b15-139">We recommend that you test applications with all the .NET Framework versions that they can run on.</span></span>

<a name="version"></a> 
## <a name="runtime-version-values"></a><span data-ttu-id="48b15-140">“运行时版本”值</span><span class="sxs-lookup"><span data-stu-id="48b15-140">"runtime version" values</span></span>
<span data-ttu-id="48b15-141">@No__t-0 特性指定给定应用程序所需的公共语言运行时（CLR）版本。</span><span class="sxs-lookup"><span data-stu-id="48b15-141">The `runtime` attribute specifies the Common Language Runtime (CLR) version that is required for a given application.</span></span> <span data-ttu-id="48b15-142">请注意，所有 .NET Framework v4. x 版本都指定了 @no__t 的 CLR。</span><span class="sxs-lookup"><span data-stu-id="48b15-142">Note that all .NET Framework v4.x versions specify the `v4.0` CLR.</span></span> <span data-ttu-id="48b15-143">下表列出了 `version` 属性的*运行时版本*值的有效值。</span><span class="sxs-lookup"><span data-stu-id="48b15-143">The following table lists valid values for the *runtime version* value of the `version` attribute.</span></span>

|<span data-ttu-id="48b15-144">.NET Framework 版本</span><span class="sxs-lookup"><span data-stu-id="48b15-144">.NET Framework version</span></span>|<span data-ttu-id="48b15-145">`version` 特性</span><span class="sxs-lookup"><span data-stu-id="48b15-145">`version` attribute</span></span>|
|----------------------------|-------------------------|
|<span data-ttu-id="48b15-146">1.0</span><span class="sxs-lookup"><span data-stu-id="48b15-146">1.0</span></span>|<span data-ttu-id="48b15-147">"v1.0.3705"</span><span class="sxs-lookup"><span data-stu-id="48b15-147">"v1.0.3705"</span></span>|
|<span data-ttu-id="48b15-148">1.1</span><span class="sxs-lookup"><span data-stu-id="48b15-148">1.1</span></span>|<span data-ttu-id="48b15-149">"v1.1.4322"</span><span class="sxs-lookup"><span data-stu-id="48b15-149">"v1.1.4322"</span></span>|
|<span data-ttu-id="48b15-150">2.0</span><span class="sxs-lookup"><span data-stu-id="48b15-150">2.0</span></span>|<span data-ttu-id="48b15-151">"v2.0.50727"</span><span class="sxs-lookup"><span data-stu-id="48b15-151">"v2.0.50727"</span></span>|
|<span data-ttu-id="48b15-152">3.0</span><span class="sxs-lookup"><span data-stu-id="48b15-152">3.0</span></span>|<span data-ttu-id="48b15-153">"v2.0.50727"</span><span class="sxs-lookup"><span data-stu-id="48b15-153">"v2.0.50727"</span></span>|
|<span data-ttu-id="48b15-154">3.5</span><span class="sxs-lookup"><span data-stu-id="48b15-154">3.5</span></span>|<span data-ttu-id="48b15-155">"v2.0.50727"</span><span class="sxs-lookup"><span data-stu-id="48b15-155">"v2.0.50727"</span></span>|
|<span data-ttu-id="48b15-156">4.0-4.8</span><span class="sxs-lookup"><span data-stu-id="48b15-156">4.0-4.8</span></span>|<span data-ttu-id="48b15-157">"v4.0"</span><span class="sxs-lookup"><span data-stu-id="48b15-157">"v4.0"</span></span>|

## <a name="sku"></a><span data-ttu-id="48b15-158">"sku id" 值</span><span class="sxs-lookup"><span data-stu-id="48b15-158">"sku id" values</span></span>

<span data-ttu-id="48b15-159">@No__t-0 属性使用目标框架名字对象（TFM）来指示应用面向的 .NET Framework 版本，并需要运行。</span><span class="sxs-lookup"><span data-stu-id="48b15-159">The `sku` attribute uses a target framework moniker (TFM) to indicate the version of the .NET Framework that the app targets and requires to run.</span></span> <span data-ttu-id="48b15-160">下表列出了 `sku` 特性支持的有效值，从 .NET Framework 4 开始。</span><span class="sxs-lookup"><span data-stu-id="48b15-160">The following table lists valid values that are supported by the `sku` attribute, starting with the .NET Framework 4.</span></span>

|<span data-ttu-id="48b15-161">.NET Framework 版本</span><span class="sxs-lookup"><span data-stu-id="48b15-161">.NET Framework version</span></span>|<span data-ttu-id="48b15-162">`sku` 特性</span><span class="sxs-lookup"><span data-stu-id="48b15-162">`sku` attribute</span></span>|
|----------------------------|---------------------|
|<span data-ttu-id="48b15-163">4.0</span><span class="sxs-lookup"><span data-stu-id="48b15-163">4.0</span></span>|<span data-ttu-id="48b15-164">".NETFramework,Version=v4.0"</span><span class="sxs-lookup"><span data-stu-id="48b15-164">".NETFramework,Version=v4.0"</span></span>|
|<span data-ttu-id="48b15-165">4.0，客户端配置文件</span><span class="sxs-lookup"><span data-stu-id="48b15-165">4.0, Client Profile</span></span>|<span data-ttu-id="48b15-166">".NETFramework,Version=v4.0,Profile=Client"</span><span class="sxs-lookup"><span data-stu-id="48b15-166">".NETFramework,Version=v4.0,Profile=Client"</span></span>|
|<span data-ttu-id="48b15-167">4.0，平台更新 1</span><span class="sxs-lookup"><span data-stu-id="48b15-167">4.0, platform update 1</span></span>|<span data-ttu-id="48b15-168">"..Netframework，Version = v 4.0.1 "</span><span class="sxs-lookup"><span data-stu-id="48b15-168">".NETFramework,Version=v4.0.1"</span></span>|
|<span data-ttu-id="48b15-169">4.0，客户端配置文件，Update 1</span><span class="sxs-lookup"><span data-stu-id="48b15-169">4.0, Client Profile, update 1</span></span>|<span data-ttu-id="48b15-170">"..Netframework，Version = v 4.0.1，Profile = Client "</span><span class="sxs-lookup"><span data-stu-id="48b15-170">".NETFramework,Version=v4.0.1,Profile=Client"</span></span>|
|<span data-ttu-id="48b15-171">4.0，平台更新 2</span><span class="sxs-lookup"><span data-stu-id="48b15-171">4.0, platform update 2</span></span>|<span data-ttu-id="48b15-172">"..Netframework，Version = v 4.0.2 "</span><span class="sxs-lookup"><span data-stu-id="48b15-172">".NETFramework,Version=v4.0.2"</span></span>|
|<span data-ttu-id="48b15-173">4.0，客户端配置文件，Update 2</span><span class="sxs-lookup"><span data-stu-id="48b15-173">4.0, Client Profile, update 2</span></span>|<span data-ttu-id="48b15-174">"..Netframework，Version = v 4.0.2，Profile = Client "</span><span class="sxs-lookup"><span data-stu-id="48b15-174">".NETFramework,Version=v4.0.2,Profile=Client"</span></span>|
|<span data-ttu-id="48b15-175">4.0，平台更新 3</span><span class="sxs-lookup"><span data-stu-id="48b15-175">4.0, platform update 3</span></span>|<span data-ttu-id="48b15-176">"..Netframework，Version = v 4.0.3 "</span><span class="sxs-lookup"><span data-stu-id="48b15-176">".NETFramework,Version=v4.0.3"</span></span>|
|<span data-ttu-id="48b15-177">4.0，客户端配置文件，Update 3</span><span class="sxs-lookup"><span data-stu-id="48b15-177">4.0, Client Profile, update 3</span></span>|<span data-ttu-id="48b15-178">"..Netframework，Version = v 4.0.3，Profile = Client "</span><span class="sxs-lookup"><span data-stu-id="48b15-178">".NETFramework,Version=v4.0.3,Profile=Client"</span></span>|
|<span data-ttu-id="48b15-179">4.5</span><span class="sxs-lookup"><span data-stu-id="48b15-179">4.5</span></span>|<span data-ttu-id="48b15-180">".NETFramework,Version=v4.5"</span><span class="sxs-lookup"><span data-stu-id="48b15-180">".NETFramework,Version=v4.5"</span></span>|
|<span data-ttu-id="48b15-181">4.5.1</span><span class="sxs-lookup"><span data-stu-id="48b15-181">4.5.1</span></span>|<span data-ttu-id="48b15-182">".NETFramework,Version=v4.5"</span><span class="sxs-lookup"><span data-stu-id="48b15-182">".NETFramework,Version=v4.5.1"</span></span>|
|<span data-ttu-id="48b15-183">4.5.2</span><span class="sxs-lookup"><span data-stu-id="48b15-183">4.5.2</span></span>|<span data-ttu-id="48b15-184">".NETFramework,Version=v4.5"</span><span class="sxs-lookup"><span data-stu-id="48b15-184">".NETFramework,Version=v4.5.2"</span></span>|
|<span data-ttu-id="48b15-185">4.6</span><span class="sxs-lookup"><span data-stu-id="48b15-185">4.6</span></span>|<span data-ttu-id="48b15-186">".NETFramework,Version=v4.5"</span><span class="sxs-lookup"><span data-stu-id="48b15-186">".NETFramework,Version=v4.6"</span></span>|
|<span data-ttu-id="48b15-187">4.6.1</span><span class="sxs-lookup"><span data-stu-id="48b15-187">4.6.1</span></span>|<span data-ttu-id="48b15-188">".NETFramework,Version=v4.5"</span><span class="sxs-lookup"><span data-stu-id="48b15-188">".NETFramework,Version=v4.6.1"</span></span>|
|<span data-ttu-id="48b15-189">4.6.2</span><span class="sxs-lookup"><span data-stu-id="48b15-189">4.6.2</span></span>|<span data-ttu-id="48b15-190">".NETFramework,Version=v4.6.2"</span><span class="sxs-lookup"><span data-stu-id="48b15-190">".NETFramework,Version=v4.6.2"</span></span>|
|<span data-ttu-id="48b15-191">4.7</span><span class="sxs-lookup"><span data-stu-id="48b15-191">4.7</span></span>|<span data-ttu-id="48b15-192">".NETFramework,Version=v4.7"</span><span class="sxs-lookup"><span data-stu-id="48b15-192">".NETFramework,Version=v4.7"</span></span>|
|<span data-ttu-id="48b15-193">4.7.1</span><span class="sxs-lookup"><span data-stu-id="48b15-193">4.7.1</span></span>|<span data-ttu-id="48b15-194">".NETFramework,Version=v4.7.1"</span><span class="sxs-lookup"><span data-stu-id="48b15-194">".NETFramework,Version=v4.7.1"</span></span>|
|<span data-ttu-id="48b15-195">4.7.2</span><span class="sxs-lookup"><span data-stu-id="48b15-195">4.7.2</span></span>|<span data-ttu-id="48b15-196">"..Netframework，Version = v 4.7.2 "</span><span class="sxs-lookup"><span data-stu-id="48b15-196">".NETFramework,Version=v4.7.2"</span></span>|
|<span data-ttu-id="48b15-197">4.8</span><span class="sxs-lookup"><span data-stu-id="48b15-197">4.8</span></span>|<span data-ttu-id="48b15-198">"..Netframework，Version = v4.0 "</span><span class="sxs-lookup"><span data-stu-id="48b15-198">".NETFramework,Version=v4.8"</span></span>|

## <a name="example"></a><span data-ttu-id="48b15-199">示例</span><span class="sxs-lookup"><span data-stu-id="48b15-199">Example</span></span>

<span data-ttu-id="48b15-200">下面的示例演示如何在配置文件中指定支持的运行时版本。</span><span class="sxs-lookup"><span data-stu-id="48b15-200">The following example shows how to specify the supported runtime version in a configuration file.</span></span> <span data-ttu-id="48b15-201">配置文件指示应用面向 .NET Framework 4.7。</span><span class="sxs-lookup"><span data-stu-id="48b15-201">The configuration file indicates that the app targets the .NET Framework 4.7.</span></span>

```xml
<configuration>
   <startup>
      <supportedRuntime version="v4.0" sku=".NETFramework,Version=v4.7" />
   </startup>
</configuration>
```

## <a name="configuration-file"></a><span data-ttu-id="48b15-202">配置文件</span><span class="sxs-lookup"><span data-stu-id="48b15-202">Configuration file</span></span>

<span data-ttu-id="48b15-203">此元素可用于应用程序配置文件中。</span><span class="sxs-lookup"><span data-stu-id="48b15-203">This element can be used in the application configuration file.</span></span>

## <a name="see-also"></a><span data-ttu-id="48b15-204">请参阅</span><span class="sxs-lookup"><span data-stu-id="48b15-204">See also</span></span>

- [<span data-ttu-id="48b15-205">启动设置架构</span><span class="sxs-lookup"><span data-stu-id="48b15-205">Startup Settings Schema</span></span>](../startup/index.md)
- [<span data-ttu-id="48b15-206">配置文件架构</span><span class="sxs-lookup"><span data-stu-id="48b15-206">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="48b15-207">进程内并行执行</span><span class="sxs-lookup"><span data-stu-id="48b15-207">In-Process Side-by-Side Execution</span></span>](../../../deployment/in-process-side-by-side-execution.md)
