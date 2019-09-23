---
title: Ngen.exe（本机映像生成器）
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- Native Image Generator
- images [.NET Framework], native
- side-by-side execution, native images
- assemblies [.NET Framework], native image
- Ngen.exe
- native image generation
- native image cache
- publisher policy applied for native images
- invalid images
- BypassNGenAttribute
- System.Runtime.BypassNGenAttribute
ms.assetid: 44bf97aa-a9a4-4eba-9a0d-cfaa6fc53a66
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5079f0243faefaab6ada23cc98f5214a616c1d22
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/17/2019
ms.locfileid: "71044368"
---
# <a name="ngenexe-native-image-generator"></a><span data-ttu-id="1676b-102">Ngen.exe（本机映像生成器）</span><span class="sxs-lookup"><span data-stu-id="1676b-102">Ngen.exe (Native Image Generator)</span></span>

<span data-ttu-id="1676b-103">本机映像生成器 (Ngen.exe) 是一种提高托管应用程序性能的工具。</span><span class="sxs-lookup"><span data-stu-id="1676b-103">The Native Image Generator (Ngen.exe) is a tool that improves the performance of managed applications.</span></span> <span data-ttu-id="1676b-104">Ngen.exe 创建本机映像（包含经编译的特定于处理器的机器代码的文件），并将它们安装到本地计算机上的本机映像缓存中。</span><span class="sxs-lookup"><span data-stu-id="1676b-104">Ngen.exe creates native images, which are files containing compiled processor-specific machine code, and installs them into the native image cache on the local computer.</span></span> <span data-ttu-id="1676b-105">运行时可从缓存中使用本机映像，而不必使用实时 (JIT) 编译器编译原始程序集。</span><span class="sxs-lookup"><span data-stu-id="1676b-105">The runtime can use native images from the cache instead of using the just-in-time (JIT) compiler to compile the original assembly.</span></span>

> [!NOTE]
> <span data-ttu-id="1676b-106">Ngen.exe 编译仅面向 .NET Framework 的程序集的本机映像。</span><span class="sxs-lookup"><span data-stu-id="1676b-106">Ngen.exe compiles native images for assemblies that target the .NET Framework only.</span></span> <span data-ttu-id="1676b-107">适用于 .NET Core 的等效本机映像生成器为 [CrossGen](https://github.com/dotnet/coreclr/blob/master/Documentation/building/crossgen.md)。</span><span class="sxs-lookup"><span data-stu-id="1676b-107">The equivalent native image generator for .NET Core is [CrossGen](https://github.com/dotnet/coreclr/blob/master/Documentation/building/crossgen.md).</span></span> 

<span data-ttu-id="1676b-108">.NET Framework 4 中对 Ngen.exe 进行的更改：</span><span class="sxs-lookup"><span data-stu-id="1676b-108">Changes to Ngen.exe in the .NET Framework 4:</span></span>

- <span data-ttu-id="1676b-109">Ngen.exe 现在按照完全信任的状态编译程序集，并且不再评估代码访问安全性 (CAS) 策略。</span><span class="sxs-lookup"><span data-stu-id="1676b-109">Ngen.exe now compiles assemblies with full trust, and code access security (CAS) policy is no longer evaluated.</span></span>

- <span data-ttu-id="1676b-110">使用 Ngen.exe 生成的本机映像不再载入按照部分信任的状态运行的应用程序中。</span><span class="sxs-lookup"><span data-stu-id="1676b-110">Native images that are generated with Ngen.exe can no longer be loaded into applications that are running in partial trust.</span></span>

<span data-ttu-id="1676b-111">.NET Framework 2.0 版中对 Ngen.exe 进行的更改：</span><span class="sxs-lookup"><span data-stu-id="1676b-111">Changes to Ngen.exe in the .NET Framework version 2.0:</span></span>

- <span data-ttu-id="1676b-112">安装程序集时还将安装其依赖项，从而简化了 Ngen.exe 的语法。</span><span class="sxs-lookup"><span data-stu-id="1676b-112">Installing an assembly also installs its dependencies, simplifying the syntax of Ngen.exe.</span></span>

- <span data-ttu-id="1676b-113">现在可以在应用程序域之间共享本机映像。</span><span class="sxs-lookup"><span data-stu-id="1676b-113">Native images can now be shared across application domains.</span></span>

- <span data-ttu-id="1676b-114">可利用新增操作 `update` 重新创建已经失效的映像。</span><span class="sxs-lookup"><span data-stu-id="1676b-114">A new action, `update`, re-creates images that have been invalidated.</span></span>

- <span data-ttu-id="1676b-115">操作可由计算机上使用空闲时间生成和安装映像的服务推迟执行。</span><span class="sxs-lookup"><span data-stu-id="1676b-115">Actions can be deferred for execution by a service that uses idle time on the computer to generate and install images.</span></span>

- <span data-ttu-id="1676b-116">消除了一些导致映像无效的因素。</span><span class="sxs-lookup"><span data-stu-id="1676b-116">Some causes of image invalidation have been eliminated.</span></span>

<span data-ttu-id="1676b-117">在 Windows 8 中，请参阅[本机映像任务](#native-image-task)。</span><span class="sxs-lookup"><span data-stu-id="1676b-117">On Windows 8, see [Native Image Task](#native-image-task).</span></span>

<span data-ttu-id="1676b-118">有关使用 Ngen.exe 和本机映像服务的其他信息，请参阅[本机映像服务](#native-image-service)。</span><span class="sxs-lookup"><span data-stu-id="1676b-118">For additional information on using Ngen.exe and the native image service, see [Native Image Service](#native-image-service).</span></span>

> [!NOTE]
> <span data-ttu-id="1676b-119">在[本机映像生成器 (Ngen.exe) 旧式语法](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms165073(v=vs.100))中可以找到 .NET Framework 1.0 和 1.1 版的 Ngen.exe 语法。</span><span class="sxs-lookup"><span data-stu-id="1676b-119">Ngen.exe syntax for versions 1.0 and 1.1 of the .NET Framework can be found in [Native Image Generator (Ngen.exe) Legacy Syntax](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms165073(v=vs.100)).</span></span>

<span data-ttu-id="1676b-120">此工具会自动随 Visual Studio 一起安装。</span><span class="sxs-lookup"><span data-stu-id="1676b-120">This tool is automatically installed with Visual Studio.</span></span> <span data-ttu-id="1676b-121">若要运行此工具，请使用 Visual Studio 开发人员命令提示（或 Windows 7 中的 Visual Studio 命令提示）。</span><span class="sxs-lookup"><span data-stu-id="1676b-121">To run the tool, use the Developer Command Prompt for Visual Studio (or the Visual Studio Command Prompt in Windows 7).</span></span> <span data-ttu-id="1676b-122">有关详细信息，请参阅[命令提示](developer-command-prompt-for-vs.md)。</span><span class="sxs-lookup"><span data-stu-id="1676b-122">For more information, see [Command Prompts](developer-command-prompt-for-vs.md).</span></span>

<span data-ttu-id="1676b-123">在命令提示符处，键入以下内容：</span><span class="sxs-lookup"><span data-stu-id="1676b-123">At the command prompt, type the following:</span></span>

## <a name="syntax"></a><span data-ttu-id="1676b-124">语法</span><span class="sxs-lookup"><span data-stu-id="1676b-124">Syntax</span></span>

```console
ngen action [options]
```

```console
ngen /? | /help
```

## <a name="actions"></a><span data-ttu-id="1676b-125">操作</span><span class="sxs-lookup"><span data-stu-id="1676b-125">Actions</span></span>

<span data-ttu-id="1676b-126">下表显示了每个 `action` 的语法。</span><span class="sxs-lookup"><span data-stu-id="1676b-126">The following table shows the syntax of each `action`.</span></span> <span data-ttu-id="1676b-127">有关 `action` 的各个部分的说明，请参见[参数](#ArgumentTable)、[优先级别](#PriorityTable)、[方案](#ScenarioTable)和[配置](#ConfigTable)表。</span><span class="sxs-lookup"><span data-stu-id="1676b-127">For descriptions of the individual parts of an `action`, see the [Arguments](#ArgumentTable), [Priority Levels](#PriorityTable), [Scenarios](#ScenarioTable), and [Config](#ConfigTable) tables.</span></span> <span data-ttu-id="1676b-128">[选项`options`表描述了 ](#OptionTable) 和帮助开关。</span><span class="sxs-lookup"><span data-stu-id="1676b-128">The [Options](#OptionTable) table describes the `options` and the help switches.</span></span>

|<span data-ttu-id="1676b-129">操作</span><span class="sxs-lookup"><span data-stu-id="1676b-129">Action</span></span>|<span data-ttu-id="1676b-130">说明</span><span class="sxs-lookup"><span data-stu-id="1676b-130">Description</span></span>|
|------------|-----------------|
|<span data-ttu-id="1676b-131">`install` [`assemblyName` &#124; `assemblyPath`] [`scenarios`] [`config`] [`/queue`[`:`{`1`&#124;`2`&#124;`3`}]]</span><span class="sxs-lookup"><span data-stu-id="1676b-131">`install` [`assemblyName` &#124; `assemblyPath`] [`scenarios`] [`config`] [`/queue`[`:`{`1`&#124;`2`&#124;`3`}]]</span></span>|<span data-ttu-id="1676b-132">生成程序集及其依赖项的本机映像，并在本机映像缓存中安装这些映像。</span><span class="sxs-lookup"><span data-stu-id="1676b-132">Generate native images for an assembly and its dependencies and install the images in the native image cache.</span></span><br /><br /> <span data-ttu-id="1676b-133">如果指定了 `/queue`，则操作将排队等待本机映像服务。</span><span class="sxs-lookup"><span data-stu-id="1676b-133">If `/queue` is specified, the action is queued for the native image service.</span></span> <span data-ttu-id="1676b-134">默认优先级是 3。</span><span class="sxs-lookup"><span data-stu-id="1676b-134">The default priority is 3.</span></span> <span data-ttu-id="1676b-135">请参见[优先级级别](#PriorityTable)表。</span><span class="sxs-lookup"><span data-stu-id="1676b-135">See the [Priority Levels](#PriorityTable) table.</span></span>|
|<span data-ttu-id="1676b-136">`uninstall` [`assemblyName` &#124; `assemblyPath`] [`scenarios`] [`config`]</span><span class="sxs-lookup"><span data-stu-id="1676b-136">`uninstall` [`assemblyName` &#124; `assemblyPath`] [`scenarios`] [`config`]</span></span>|<span data-ttu-id="1676b-137">从本机映像缓存中删除程序集及其依赖项的本机映像。</span><span class="sxs-lookup"><span data-stu-id="1676b-137">Delete the native images of an assembly and its dependencies from the native image cache.</span></span><br /><br /> <span data-ttu-id="1676b-138">若要卸载单个映像及其依赖项，可使用与安装此映像时相同的命令行自变量。</span><span class="sxs-lookup"><span data-stu-id="1676b-138">To uninstall a single image and its dependencies, use the same command-line arguments that were used to install the image.</span></span> <span data-ttu-id="1676b-139">**注意：** 从 .NET Framework 4 开始，不再支持操作 `uninstall` \*。</span><span class="sxs-lookup"><span data-stu-id="1676b-139">**Note:**  Starting with the .NET Framework 4, the action `uninstall` \* is no longer supported.</span></span>|
|<span data-ttu-id="1676b-140">`update` [`/queue`]</span><span class="sxs-lookup"><span data-stu-id="1676b-140">`update` [`/queue`]</span></span>|<span data-ttu-id="1676b-141">更新已无效的本机映像。</span><span class="sxs-lookup"><span data-stu-id="1676b-141">Update native images that have become invalid.</span></span><br /><br /> <span data-ttu-id="1676b-142">如果指定了 `/queue`，则更新将排队等待本机映像服务。</span><span class="sxs-lookup"><span data-stu-id="1676b-142">If `/queue` is specified, the updates are queued for the native image service.</span></span> <span data-ttu-id="1676b-143">更新的优先级总是设定为 3，因此它们在计算机空闲时运行。</span><span class="sxs-lookup"><span data-stu-id="1676b-143">Updates are always scheduled at priority 3, so they run when the computer is idle.</span></span>|
|<span data-ttu-id="1676b-144">`display` [`assemblyName` &#124; `assemblyPath`]</span><span class="sxs-lookup"><span data-stu-id="1676b-144">`display` [`assemblyName` &#124; `assemblyPath`]</span></span>|<span data-ttu-id="1676b-145">显示程序集及其依赖项的本机映像的状态。</span><span class="sxs-lookup"><span data-stu-id="1676b-145">Display the state of the native images for an assembly and its dependencies.</span></span><br /><br /> <span data-ttu-id="1676b-146">如果未提供自变量，则显示本机映像缓存中的所有内容。</span><span class="sxs-lookup"><span data-stu-id="1676b-146">If no argument is supplied, everything in the native image cache is displayed.</span></span>|
|<span data-ttu-id="1676b-147">`executeQueuedItems` [<code>1&#124;2&#124;3</code>]</span><span class="sxs-lookup"><span data-stu-id="1676b-147">`executeQueuedItems` [<code>1&#124;2&#124;3</code>]</span></span><br /><br /> <span data-ttu-id="1676b-148">-或-</span><span class="sxs-lookup"><span data-stu-id="1676b-148">-or-</span></span><br /><br /> <span data-ttu-id="1676b-149">`eqi` [1&#124;2&#124;3]</span><span class="sxs-lookup"><span data-stu-id="1676b-149">`eqi` [1&#124;2&#124;3]</span></span>|<span data-ttu-id="1676b-150">执行排队的编译作业。</span><span class="sxs-lookup"><span data-stu-id="1676b-150">Execute queued compilation jobs.</span></span><br /><br /> <span data-ttu-id="1676b-151">如果指定了优先级，则执行具有较高或同等优先级的编译作业。</span><span class="sxs-lookup"><span data-stu-id="1676b-151">If a priority is specified, compilation jobs with greater or equal priority are executed.</span></span> <span data-ttu-id="1676b-152">如果未指定优先级，则执行所有排队的编译作业。</span><span class="sxs-lookup"><span data-stu-id="1676b-152">If no priority is specified, all queued compilation jobs are executed.</span></span>|
|<span data-ttu-id="1676b-153">`queue` {`pause` &#124; `continue` &#124; `status`}</span><span class="sxs-lookup"><span data-stu-id="1676b-153">`queue` {`pause` &#124; `continue` &#124; `status`}</span></span>|<span data-ttu-id="1676b-154">暂停本机映像服务，允许暂停的服务继续，或查询服务状态。</span><span class="sxs-lookup"><span data-stu-id="1676b-154">Pause the native image service, allow the paused service to continue, or query the status of the service.</span></span>|

<a name="ArgumentTable"></a>

## <a name="arguments"></a><span data-ttu-id="1676b-155">自变量</span><span class="sxs-lookup"><span data-stu-id="1676b-155">Arguments</span></span>

|<span data-ttu-id="1676b-156">参数</span><span class="sxs-lookup"><span data-stu-id="1676b-156">Argument</span></span>|<span data-ttu-id="1676b-157">说明</span><span class="sxs-lookup"><span data-stu-id="1676b-157">Description</span></span>|
|--------------|-----------------|
|`assemblyName`|<span data-ttu-id="1676b-158">程序集的完整显示名称。</span><span class="sxs-lookup"><span data-stu-id="1676b-158">The full display name of the assembly.</span></span> <span data-ttu-id="1676b-159">例如 `"myAssembly, Version=2.0.0.0, Culture=neutral, PublicKeyToken=0038abc9deabfle5"`。</span><span class="sxs-lookup"><span data-stu-id="1676b-159">For example, `"myAssembly, Version=2.0.0.0, Culture=neutral, PublicKeyToken=0038abc9deabfle5"`.</span></span> <span data-ttu-id="1676b-160">**注意：** 可以为 `myAssembly` 和 `display` 操作提供部分程序集名称（如 `uninstall`）。</span><span class="sxs-lookup"><span data-stu-id="1676b-160">**Note:**  You can supply a partial assembly name, such as `myAssembly`, for the `display` and `uninstall` actions.</span></span> <br /><br /> <span data-ttu-id="1676b-161">每个 Ngen.exe 命令行只能指定一个程序集。</span><span class="sxs-lookup"><span data-stu-id="1676b-161">Only one assembly can be specified per Ngen.exe command line.</span></span>|
|`assemblyPath`|<span data-ttu-id="1676b-162">程序集的显式路径。</span><span class="sxs-lookup"><span data-stu-id="1676b-162">The explicit path of the assembly.</span></span> <span data-ttu-id="1676b-163">可指定完整路径或相对路径。</span><span class="sxs-lookup"><span data-stu-id="1676b-163">You can specify a full or relative path.</span></span><br /><br /> <span data-ttu-id="1676b-164">如果指定文件名而不指定路径，则程序集必须位于当前目录中。</span><span class="sxs-lookup"><span data-stu-id="1676b-164">If you specify a file name without a path, the assembly must be located in the current directory.</span></span><br /><br /> <span data-ttu-id="1676b-165">每个 Ngen.exe 命令行只能指定一个程序集。</span><span class="sxs-lookup"><span data-stu-id="1676b-165">Only one assembly can be specified per Ngen.exe command line.</span></span>|

<a name="PriorityTable"></a>

## <a name="priority-levels"></a><span data-ttu-id="1676b-166">优先级级别</span><span class="sxs-lookup"><span data-stu-id="1676b-166">Priority Levels</span></span>

|<span data-ttu-id="1676b-167">优先级</span><span class="sxs-lookup"><span data-stu-id="1676b-167">Priority</span></span>|<span data-ttu-id="1676b-168">说明</span><span class="sxs-lookup"><span data-stu-id="1676b-168">Description</span></span>|
|--------------|-----------------|
|`1`|<span data-ttu-id="1676b-169">生成本机映像，并立即进行安装，而无需等待空闲时间。</span><span class="sxs-lookup"><span data-stu-id="1676b-169">Native images are generated and installed immediately, without waiting for idle time.</span></span>|
|`2`|<span data-ttu-id="1676b-170">生成本机映像，并立即进行安装，而无需等待空闲时间，但是在所有优先级为 1 的操作（及其依赖项）完成后。</span><span class="sxs-lookup"><span data-stu-id="1676b-170">Native images are generated and installed without waiting for idle time, but after all priority 1 actions (and their dependencies) have completed.</span></span>|
|`3`|<span data-ttu-id="1676b-171">在本机映像服务检测到计算机处于空闲状态时，安装本机映像。</span><span class="sxs-lookup"><span data-stu-id="1676b-171">Native images are installed when the native image service detects that the computer is idle.</span></span> <span data-ttu-id="1676b-172">请参阅[本机映像服务](#native-image-service)。</span><span class="sxs-lookup"><span data-stu-id="1676b-172">See [Native Image Service](#native-image-service).</span></span>|

<a name="ScenarioTable"></a>

## <a name="scenarios"></a><span data-ttu-id="1676b-173">方案</span><span class="sxs-lookup"><span data-stu-id="1676b-173">Scenarios</span></span>

|<span data-ttu-id="1676b-174">方案</span><span class="sxs-lookup"><span data-stu-id="1676b-174">Scenario</span></span>|<span data-ttu-id="1676b-175">说明</span><span class="sxs-lookup"><span data-stu-id="1676b-175">Description</span></span>|
|--------------|-----------------|
|`/Debug`|<span data-ttu-id="1676b-176">生成可在调试器下使用的本机映像。</span><span class="sxs-lookup"><span data-stu-id="1676b-176">Generate native images that can be used under a debugger.</span></span>|
|`/Profile`|<span data-ttu-id="1676b-177">生成可在探查器下使用的本机映像。</span><span class="sxs-lookup"><span data-stu-id="1676b-177">Generate native images that can be used under a profiler.</span></span>|
|`/NoDependencies`|<span data-ttu-id="1676b-178">生成指定方案选项所需的最小数目的本机映像。</span><span class="sxs-lookup"><span data-stu-id="1676b-178">Generate the minimum number of native images required by the specified scenario options.</span></span>|

<a name="ConfigTable"></a>

## <a name="config"></a><span data-ttu-id="1676b-179">配置</span><span class="sxs-lookup"><span data-stu-id="1676b-179">Config</span></span>

|<span data-ttu-id="1676b-180">配置</span><span class="sxs-lookup"><span data-stu-id="1676b-180">Configuration</span></span>|<span data-ttu-id="1676b-181">说明</span><span class="sxs-lookup"><span data-stu-id="1676b-181">Description</span></span>|
|-------------------|-----------------|
|<span data-ttu-id="1676b-182">`/ExeConfig:` `exePath`</span><span class="sxs-lookup"><span data-stu-id="1676b-182">`/ExeConfig:` `exePath`</span></span>|<span data-ttu-id="1676b-183">使用指定的可执行程序集的配置。</span><span class="sxs-lookup"><span data-stu-id="1676b-183">Use the configuration of the specified executable assembly.</span></span><br /><br /> <span data-ttu-id="1676b-184">绑定到依赖项时，Ngen.exe 需要做出与加载程序相同的决策。</span><span class="sxs-lookup"><span data-stu-id="1676b-184">Ngen.exe needs to make the same decisions as the loader when binding to dependencies.</span></span> <span data-ttu-id="1676b-185">如果在运行时使用 <xref:System.Reflection.Assembly.Load%2A> 方法加载共享组件，则应用程序的配置文件将决定为该共享组件加载的依赖项 - 例如，所加载依赖项的版本。</span><span class="sxs-lookup"><span data-stu-id="1676b-185">When a shared component is loaded at run time, using the <xref:System.Reflection.Assembly.Load%2A> method, the application's configuration file determines the dependencies that are loaded for the shared component — for example, the version of a dependency that is loaded.</span></span> <span data-ttu-id="1676b-186">`/ExeConfig` 开关就运行时将加载哪些依赖项为 Ngen.exe 提供了指导。</span><span class="sxs-lookup"><span data-stu-id="1676b-186">The `/ExeConfig` switch gives Ngen.exe guidance on which dependencies would be loaded at run time.</span></span>|
|<span data-ttu-id="1676b-187">`/AppBase:` `directoryPath`</span><span class="sxs-lookup"><span data-stu-id="1676b-187">`/AppBase:` `directoryPath`</span></span>|<span data-ttu-id="1676b-188">查找依赖项时，使用指定目录作为应用程序基础。</span><span class="sxs-lookup"><span data-stu-id="1676b-188">When locating dependencies, use the specified directory as the application base.</span></span>|

<a name="OptionTable"></a>

## <a name="options"></a><span data-ttu-id="1676b-189">选项</span><span class="sxs-lookup"><span data-stu-id="1676b-189">Options</span></span>

|<span data-ttu-id="1676b-190">选项</span><span class="sxs-lookup"><span data-stu-id="1676b-190">Option</span></span>|<span data-ttu-id="1676b-191">说明</span><span class="sxs-lookup"><span data-stu-id="1676b-191">Description</span></span>|
|------------|-----------------|
|`/nologo`|<span data-ttu-id="1676b-192">禁止显示 Microsoft 启动版权标志。</span><span class="sxs-lookup"><span data-stu-id="1676b-192">Suppress the Microsoft startup banner display.</span></span>|
|`/silent`|<span data-ttu-id="1676b-193">禁止显示成功消息。</span><span class="sxs-lookup"><span data-stu-id="1676b-193">Suppress the display of success messages.</span></span>|
|`/verbose`|<span data-ttu-id="1676b-194">显示详细的调试信息。</span><span class="sxs-lookup"><span data-stu-id="1676b-194">Display detailed information for debugging.</span></span> <span data-ttu-id="1676b-195">**注意：** 由于操作系统限制，此选项显示的附加信息比在 Windows 98 和 Windows Millennium Edition 上显示的少。</span><span class="sxs-lookup"><span data-stu-id="1676b-195">**Note:**  Due to operating system limitations, this option does not display as much additional information on Windows 98 and Windows Millennium Edition.</span></span>|
|<span data-ttu-id="1676b-196">`/help`， `/?`</span><span class="sxs-lookup"><span data-stu-id="1676b-196">`/help`, `/?`</span></span>|<span data-ttu-id="1676b-197">显示当前版本的命令语法和选项。</span><span class="sxs-lookup"><span data-stu-id="1676b-197">Display command syntax and options for the current release.</span></span>|

## <a name="remarks"></a><span data-ttu-id="1676b-198">备注</span><span class="sxs-lookup"><span data-stu-id="1676b-198">Remarks</span></span>

<span data-ttu-id="1676b-199">若要运行 Ngen.exe，你必须具有管理特权。</span><span class="sxs-lookup"><span data-stu-id="1676b-199">To run Ngen.exe, you must have administrative privileges.</span></span>

> [!CAUTION]
> <span data-ttu-id="1676b-200">不在未完全受信任的程序集上运行 Ngen.exe。</span><span class="sxs-lookup"><span data-stu-id="1676b-200">Do not run Ngen.exe on assemblies that are not fully trusted.</span></span> <span data-ttu-id="1676b-201">从 .NET Framework 4 开始，Ngen.exe 按照完全信任的状态编译程序集，并且不再评估代码访问安全性 (CAS) 策略。</span><span class="sxs-lookup"><span data-stu-id="1676b-201">Starting with the .NET Framework 4, Ngen.exe compiles assemblies with full trust, and code access security (CAS) policy is no longer evaluated.</span></span>

<span data-ttu-id="1676b-202">从 .NET Framework 4 开始，使用 Ngen.exe 生成的本机映像不再载入到按照部分信任的状态运行的应用程序中。</span><span class="sxs-lookup"><span data-stu-id="1676b-202">Starting with the .NET Framework 4, the native images that are generated with Ngen.exe can no longer be loaded into applications that are running in partial trust.</span></span> <span data-ttu-id="1676b-203">而是，调用了实时 (JIT) 编译器。</span><span class="sxs-lookup"><span data-stu-id="1676b-203">Instead, the just-in-time (JIT) compiler is invoked.</span></span>

<span data-ttu-id="1676b-204">Ngen.exe 为 `assemblyname` 参数对 `install` 操作指定的程序集及其所有依赖项生成本机映像。</span><span class="sxs-lookup"><span data-stu-id="1676b-204">Ngen.exe generates native images for the assembly specified by the `assemblyname` argument to the `install` action and all its dependencies.</span></span> <span data-ttu-id="1676b-205">依赖项是根据程序集清单中的引用来确定的。</span><span class="sxs-lookup"><span data-stu-id="1676b-205">Dependencies are determined from references in the assembly manifest.</span></span> <span data-ttu-id="1676b-206">仅在应用程序使用反射（例如，通过调用 <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType> 方法）来加载依赖项的情况下，你才需要单独安装依赖项。</span><span class="sxs-lookup"><span data-stu-id="1676b-206">The only scenario in which you need to install a dependency separately is when the application loads it using reflection, for example by calling the <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType> method.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1676b-207">不要将 <xref:System.Reflection.Assembly.LoadFrom%2A?displayProperty=nameWithType> 方法用于本机映像。</span><span class="sxs-lookup"><span data-stu-id="1676b-207">Do not use the <xref:System.Reflection.Assembly.LoadFrom%2A?displayProperty=nameWithType> method with native images.</span></span> <span data-ttu-id="1676b-208">使用此方法加载的映像不能由执行上下文中的其他程序集使用。</span><span class="sxs-lookup"><span data-stu-id="1676b-208">An image loaded with this method cannot be used by other assemblies in the execution context.</span></span>

<span data-ttu-id="1676b-209">Ngen.exe 维护一个与依赖项有关的计数。</span><span class="sxs-lookup"><span data-stu-id="1676b-209">Ngen.exe maintains a count on dependencies.</span></span> <span data-ttu-id="1676b-210">例如，假设本机映像缓存中同时安装了 `MyAssembly.exe` 和 `YourAssembly.exe`，而且它们都具有对 `OurDependency.dll` 的引用。</span><span class="sxs-lookup"><span data-stu-id="1676b-210">For example, suppose `MyAssembly.exe` and `YourAssembly.exe` are both installed in the native image cache, and both have references to `OurDependency.dll`.</span></span> <span data-ttu-id="1676b-211">如果卸载了 `MyAssembly.exe`，则不会卸载 `OurDependency.dll`。</span><span class="sxs-lookup"><span data-stu-id="1676b-211">If `MyAssembly.exe` is uninstalled, `OurDependency.dll` is not uninstalled.</span></span> <span data-ttu-id="1676b-212">只有当 `YourAssembly.exe` 也被卸载时才会将其移除。</span><span class="sxs-lookup"><span data-stu-id="1676b-212">It is only removed when `YourAssembly.exe` is also uninstalled.</span></span>

<span data-ttu-id="1676b-213">如果为全局程序集缓存中的程序集生成本机映像，请指定其显示名称。</span><span class="sxs-lookup"><span data-stu-id="1676b-213">If you are generating a native image for an assembly in the global assembly cache, specify its display name.</span></span> <span data-ttu-id="1676b-214">请参阅 <xref:System.Reflection.Assembly.FullName%2A?displayProperty=nameWithType>。</span><span class="sxs-lookup"><span data-stu-id="1676b-214">See <xref:System.Reflection.Assembly.FullName%2A?displayProperty=nameWithType>.</span></span>

<span data-ttu-id="1676b-215">Ngen.exe 生成的本机映像可以在应用程序域之间共享。</span><span class="sxs-lookup"><span data-stu-id="1676b-215">The native images that Ngen.exe generates can be shared across application domains.</span></span> <span data-ttu-id="1676b-216">这意味着，在要求在应用程序域之间共享程序集的应用程序方案中，可以使用 Ngen.exe。</span><span class="sxs-lookup"><span data-stu-id="1676b-216">This means you can use Ngen.exe in application scenarios that require assemblies to be shared across application domains.</span></span> <span data-ttu-id="1676b-217">若要指定域非特定性，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="1676b-217">To specify domain neutrality:</span></span>

- <span data-ttu-id="1676b-218">将 <xref:System.LoaderOptimizationAttribute> 特性应用于应用程序。</span><span class="sxs-lookup"><span data-stu-id="1676b-218">Apply the <xref:System.LoaderOptimizationAttribute> attribute to your application.</span></span>

- <span data-ttu-id="1676b-219">为新的应用程序域创建安装信息时，请设置 <xref:System.AppDomainSetup.LoaderOptimization%2A?displayProperty=nameWithType> 属性。</span><span class="sxs-lookup"><span data-stu-id="1676b-219">Set the <xref:System.AppDomainSetup.LoaderOptimization%2A?displayProperty=nameWithType> property when you create setup information for a new application domain.</span></span>

<span data-ttu-id="1676b-220">将同一个程序集加载到多个应用程序域中时，总是使用非特定于域的代码。</span><span class="sxs-lookup"><span data-stu-id="1676b-220">Always use domain-neutral code when loading the same assembly into multiple application domains.</span></span> <span data-ttu-id="1676b-221">如果本机映像在已加载到共享域之后又被加载到非共享的应用程序域中，则该映像将无法使用。</span><span class="sxs-lookup"><span data-stu-id="1676b-221">If a native image is loaded into a nonshared application domain after having been loaded into a shared domain, it cannot be used.</span></span>

> [!NOTE]
> <span data-ttu-id="1676b-222">非特定于域的代码无法卸载，并且性能可能会稍微降低，尤其是在访问静态成员时。</span><span class="sxs-lookup"><span data-stu-id="1676b-222">Domain-neutral code cannot be unloaded, and performance may be slightly slower, particularly when accessing static members.</span></span>

<span data-ttu-id="1676b-223">在此“注解”部分中：</span><span class="sxs-lookup"><span data-stu-id="1676b-223">In this Remarks section:</span></span>

- [<span data-ttu-id="1676b-224">为不同的方案生成映像</span><span class="sxs-lookup"><span data-stu-id="1676b-224">Generating images for different scenarios</span></span>](#Scenarios)

- [<span data-ttu-id="1676b-225">确定何时使用本机映像</span><span class="sxs-lookup"><span data-stu-id="1676b-225">Determining when to Use native images</span></span>](#WhenToUse)

  - [<span data-ttu-id="1676b-226">改善内存使用情况</span><span class="sxs-lookup"><span data-stu-id="1676b-226">Improved memory use</span></span>](#Memory)

  - [<span data-ttu-id="1676b-227">更快的应用程序启动速度</span><span class="sxs-lookup"><span data-stu-id="1676b-227">Faster application startup</span></span>](#Startup)

  - [<span data-ttu-id="1676b-228">使用注意事项摘要</span><span class="sxs-lookup"><span data-stu-id="1676b-228">Summary of usage considerations</span></span>](#UsageSummary)

- [<span data-ttu-id="1676b-229">程序集基址的重要性</span><span class="sxs-lookup"><span data-stu-id="1676b-229">Importance of assembly base addresses</span></span>](#BaseAddresses)

- [<span data-ttu-id="1676b-230">硬绑定</span><span class="sxs-lookup"><span data-stu-id="1676b-230">Hard binding</span></span>](#HardBinding)

  - [<span data-ttu-id="1676b-231">为依赖项指定绑定提示</span><span class="sxs-lookup"><span data-stu-id="1676b-231">Specifying a binding hint for a dependency</span></span>](#DependencyHint)

  - [<span data-ttu-id="1676b-232">为程序集指定默认绑定提示</span><span class="sxs-lookup"><span data-stu-id="1676b-232">Specifying a default binding hint for an assembly</span></span>](#AssemblyHint)

- [<span data-ttu-id="1676b-233">推迟处理</span><span class="sxs-lookup"><span data-stu-id="1676b-233">Deferred processing</span></span>](#Deferred)

- [<span data-ttu-id="1676b-234">本机映像和 JIT 编译</span><span class="sxs-lookup"><span data-stu-id="1676b-234">Native images and JIT compilation</span></span>](#JITCompilation)

  - [<span data-ttu-id="1676b-235">无效映像</span><span class="sxs-lookup"><span data-stu-id="1676b-235">Invalid images</span></span>](#InvalidImages)

- [<span data-ttu-id="1676b-236">疑难解答</span><span class="sxs-lookup"><span data-stu-id="1676b-236">Troubleshooting</span></span>](#Troubleshooting)

  - [<span data-ttu-id="1676b-237">程序集绑定日志查看器</span><span class="sxs-lookup"><span data-stu-id="1676b-237">Assembly Binding Log Viewer</span></span>](#Fusion)

  - [<span data-ttu-id="1676b-238">JITCompilationStart 托管调试助手</span><span class="sxs-lookup"><span data-stu-id="1676b-238">The JITCompilationStart managed debugging assistant</span></span>](#MDA)

  - [<span data-ttu-id="1676b-239">选择退出本机映像生成</span><span class="sxs-lookup"><span data-stu-id="1676b-239">Opting out of native image generation</span></span>](#OptOut)

<a name="Scenarios"></a>

## <a name="generating-images-for-----different-scenarios"></a><span data-ttu-id="1676b-240">为不同的方案生成映像</span><span class="sxs-lookup"><span data-stu-id="1676b-240">Generating images for     different scenarios</span></span>

<span data-ttu-id="1676b-241">生成一个程序集的本机映像后，每当运行时运行该程序集时，都会自动尝试找到并使用该本机映像。</span><span class="sxs-lookup"><span data-stu-id="1676b-241">After you have generated a native image for an assembly, the runtime automatically attempts to locate and use this native   image each time it runs the assembly.</span></span> <span data-ttu-id="1676b-242">根据使用方案的不同，可生成多个映像。</span><span class="sxs-lookup"><span data-stu-id="1676b-242">Multiple images can be generated, depending on usage scenarios.</span></span>

<span data-ttu-id="1676b-243">例如，如果你在调试或分析方案中运行程序集，则运行时将查找利用 `/Debug` 或 `/Profile` 选项生成的本机映像。</span><span class="sxs-lookup"><span data-stu-id="1676b-243">For example, if you run an assembly in a debugging or profiling scenario, the runtime looks for a native image that was generated with the `/Debug` or `/Profile` options.</span></span> <span data-ttu-id="1676b-244">如果运行时无法找到匹配的本机映像，它将恢复为标准的 JIT 编译。</span><span class="sxs-lookup"><span data-stu-id="1676b-244">If it is unable to find a matching native image, the runtime reverts to standard JIT compilation.</span></span> <span data-ttu-id="1676b-245">调试本机映像的唯一方式是使用 `/Debug` 选项创建本机映像。</span><span class="sxs-lookup"><span data-stu-id="1676b-245">The only way to debug native images is to create a native image with the `/Debug` option.</span></span>

<span data-ttu-id="1676b-246">`uninstall` 操作也能识别方案，因此你可以卸载所有方案或只卸载选择的方案。</span><span class="sxs-lookup"><span data-stu-id="1676b-246">The `uninstall` action also recognize scenarios, so you can uninstall all scenarios or only selected scenarios.</span></span>

<a name="WhenToUse"></a>

## <a name="determining-when-to-use-native-images"></a><span data-ttu-id="1676b-247">确定何时使用本机映像</span><span class="sxs-lookup"><span data-stu-id="1676b-247">Determining when to Use native images</span></span>

<span data-ttu-id="1676b-248">本机映像可从两方面提高性能：改善内存使用情况和减少启动时间。</span><span class="sxs-lookup"><span data-stu-id="1676b-248">Native images can provide performance improvements in two areas: improved memory use and reduced startup time.</span></span>

> [!NOTE]
> <span data-ttu-id="1676b-249">本机映像的性能取决于很多因素，这些因素使得分析难以进行，如代码和数据访问模式，有多少调用跨模块边界进行，以及多少依赖项已由其他应用程序加载。</span><span class="sxs-lookup"><span data-stu-id="1676b-249">Performance of native images depends on a number of factors that make analysis difficult, such as code and data access patterns, how many calls are made across module boundaries, and how many dependencies have already been loaded by other applications.</span></span> <span data-ttu-id="1676b-250">确定本机映像是否对应用程序有利的唯一方式是在关键部署方案中仔细进行性能测量。</span><span class="sxs-lookup"><span data-stu-id="1676b-250">The only way to determine whether native images benefit your application is by careful performance measurements in your key deployment scenarios.</span></span>

<a name="Memory"></a>

### <a name="improved-memory-use"></a><span data-ttu-id="1676b-251">改善内存使用情况</span><span class="sxs-lookup"><span data-stu-id="1676b-251">Improved memory use</span></span>

<span data-ttu-id="1676b-252">当代码在进程间共享时，本机映像可显著改善内存使用情况。</span><span class="sxs-lookup"><span data-stu-id="1676b-252">Native images can significantly improve memory use when code is shared between processes.</span></span> <span data-ttu-id="1676b-253">本机映像为 Windows PE 文件，因此一个 .dll 文件的单个副本可由多个进程共享；而 JIT 编译器生成的本机代码存储在私有内存中，并且不可共享。</span><span class="sxs-lookup"><span data-stu-id="1676b-253">Native images are Windows PE files, so a single copy of a .dll file can be shared by multiple processes; by contrast, native code produced by the JIT compiler is stored in private memory and cannot be shared.</span></span>

<span data-ttu-id="1676b-254">运行于终端服务下的应用程序也可从共享代码页中获益。</span><span class="sxs-lookup"><span data-stu-id="1676b-254">Applications that are run under terminal services can also benefit from shared code pages.</span></span>

<span data-ttu-id="1676b-255">此外，不加载 JIT 编译器会为每个应用程序实例节省固定量的内存。</span><span class="sxs-lookup"><span data-stu-id="1676b-255">In addition, not loading the JIT compiler saves a fixed amount of memory for each application instance.</span></span>

<a name="Startup"></a>

### <a name="faster-application-startup"></a><span data-ttu-id="1676b-256">更快的应用程序启动速度</span><span class="sxs-lookup"><span data-stu-id="1676b-256">Faster application startup</span></span>

<span data-ttu-id="1676b-257">使用 Ngen.exe 预编译程序集可减少某些应用程序的启动时间。</span><span class="sxs-lookup"><span data-stu-id="1676b-257">Precompiling assemblies with Ngen.exe can improve the startup time for some applications.</span></span> <span data-ttu-id="1676b-258">通常，如果应用程序共享组件程序集，则可从中获益，因为在第一个应用程序启动之后，共享组件即已加载，可供后续应用程序使用。</span><span class="sxs-lookup"><span data-stu-id="1676b-258">In general, gains can be made when applications share component assemblies because after the first application has been started the shared components are already loaded for subsequent applications.</span></span> <span data-ttu-id="1676b-259">而冷启动（应用程序中的所有程序集必须从硬盘上加载）则不会从本机映像中获得相同的益处，因为硬盘访问时间占了很大比重。</span><span class="sxs-lookup"><span data-stu-id="1676b-259">Cold startup, in which all the assemblies in an application must be loaded from the hard disk, does not benefit as much from native images because the hard disk access time predominates.</span></span>

<span data-ttu-id="1676b-260">硬绑定可影响启动时间，因为硬绑定至主应用程序程序集的所有映像必须同时加载。</span><span class="sxs-lookup"><span data-stu-id="1676b-260">Hard binding can affect startup time, because all images that are hard bound to the main application assembly must be loaded at the same time.</span></span>

> [!NOTE]
> <span data-ttu-id="1676b-261">在 .NET Framework 3.5 Service Pack 1 之前，你应该将共享且强命名的组件置于全局程序集缓存中，因为加载程序对未处于全局程序集缓存中的强命名程序集执行额外验证，实际抵消了使用本机映像在启动时间方面获得的任何改善。</span><span class="sxs-lookup"><span data-stu-id="1676b-261">Before the .NET Framework 3.5 Service Pack 1, you should put shared, strong-named components in the global assembly cache, because the loader performs extra validation on strong-named assemblies that are not in the global assembly cache, effectively eliminating any improvement in startup time gained by using native images.</span></span> <span data-ttu-id="1676b-262">在 .NET Framework 3.5 SP1 中引入的优化移除了多余的有效性。</span><span class="sxs-lookup"><span data-stu-id="1676b-262">Optimizations that were introduced in the .NET Framework 3.5 SP1 removed the extra validation.</span></span>

<a name="UsageSummary"></a>

### <a name="summary-of-usage-considerations"></a><span data-ttu-id="1676b-263">使用注意事项摘要</span><span class="sxs-lookup"><span data-stu-id="1676b-263">Summary of usage considerations</span></span>

<span data-ttu-id="1676b-264">下面的常规注意事项和应用程序注意事项可能有助于你决定是否对应用程序的本机映像进行评估：</span><span class="sxs-lookup"><span data-stu-id="1676b-264">The following general considerations and application considerations may assist you in deciding whether to undertake the effort of evaluating native images for your application:</span></span>

- <span data-ttu-id="1676b-265">本机映像的加载速度比 MSIL 更快，因为本机映像不必执行很多启动操作，如 JIT 编译和类型安全验证。</span><span class="sxs-lookup"><span data-stu-id="1676b-265">Native images load faster than MSIL because they eliminate the need for many startup activities, such as JIT compilation and type-safety verification.</span></span>

- <span data-ttu-id="1676b-266">本机映像需要较小的初始工作集，因为它不需要 JIT 编译器。</span><span class="sxs-lookup"><span data-stu-id="1676b-266">Native images require a smaller initial working set because there is no need for the JIT compiler.</span></span>

- <span data-ttu-id="1676b-267">本机映像允许在进程间共享代码。</span><span class="sxs-lookup"><span data-stu-id="1676b-267">Native images enable code sharing between processes.</span></span>

- <span data-ttu-id="1676b-268">本机映像需要占用比 MSIL 程序集更大的硬盘空间，并且可能需要相当长的时间才能生成。</span><span class="sxs-lookup"><span data-stu-id="1676b-268">Native images require more hard disk space than MSIL assemblies and may require considerable time to generate.</span></span>

- <span data-ttu-id="1676b-269">必须维护本机映像。</span><span class="sxs-lookup"><span data-stu-id="1676b-269">Native images must be maintained.</span></span>

  - <span data-ttu-id="1676b-270">在提供原始程序集或原始程序集的某个依赖项后，需要重新生成映像。</span><span class="sxs-lookup"><span data-stu-id="1676b-270">Images need to be regenerated when the original assembly or one of its dependencies is serviced.</span></span>

  - <span data-ttu-id="1676b-271">一个程序集可能需要多个本机映像，分别用在不同的应用程序或不同的方案中。</span><span class="sxs-lookup"><span data-stu-id="1676b-271">A single assembly may need multiple native images for use in different applications or different scenarios.</span></span> <span data-ttu-id="1676b-272">例如，两个应用程序中的配置信息可能为同一个依赖程序集生成不同的绑定决策。</span><span class="sxs-lookup"><span data-stu-id="1676b-272">For example, the configuration information in two applications might result in different binding decisions for the same dependent assembly.</span></span>

  - <span data-ttu-id="1676b-273">必须由管理员（也就是 Administrators 组中的某个 Windows 帐户）来生成本机映像。</span><span class="sxs-lookup"><span data-stu-id="1676b-273">Native images must be generated by an administrator; that is, from a Windows account in the Administrators group.</span></span>

<span data-ttu-id="1676b-274">除了这些常规注意事项之外，在确定本机映像是否可提供性能益处时，必须考虑应用程序的性质：</span><span class="sxs-lookup"><span data-stu-id="1676b-274">In addition to these general considerations, the nature of your application must be considered when determining whether native images might provide a performance benefit:</span></span>

- <span data-ttu-id="1676b-275">如果应用程序运行于使用很多共享组件的环境中，则本机映像允许多个进程共享组件。</span><span class="sxs-lookup"><span data-stu-id="1676b-275">If your application runs in an environment that uses many shared components, native images allow the components to be shared by multiple processes.</span></span>

- <span data-ttu-id="1676b-276">如果应用程序使用多个应用程序域，则本机映像允许跨域共享代码页。</span><span class="sxs-lookup"><span data-stu-id="1676b-276">If your application uses multiple application domains, native images allow code pages to be shared across domains.</span></span>

    > [!NOTE]
    > <span data-ttu-id="1676b-277">在 .NET Framework 1.0 和 1.1 版中，本机映像不能跨应用程序域共享。</span><span class="sxs-lookup"><span data-stu-id="1676b-277">In the .NET Framework versions 1.0 and 1.1, native images cannot be shared across application domains.</span></span> <span data-ttu-id="1676b-278">而在 2.0 版或更高版本中则并非如此。</span><span class="sxs-lookup"><span data-stu-id="1676b-278">This is not the case in version 2.0 or later.</span></span>

- <span data-ttu-id="1676b-279">如果应用程序将在终端服务器下运行，则本机映像允许共享代码页。</span><span class="sxs-lookup"><span data-stu-id="1676b-279">If your application will be run under Terminal Server, native images allow sharing of code pages.</span></span>

- <span data-ttu-id="1676b-280">编译为本机映像通常有利于大型应用程序。</span><span class="sxs-lookup"><span data-stu-id="1676b-280">Large applications generally benefit from compilation to native images.</span></span> <span data-ttu-id="1676b-281">小型应用程序通常不会获益。</span><span class="sxs-lookup"><span data-stu-id="1676b-281">Small applications generally do not benefit.</span></span>

- <span data-ttu-id="1676b-282">对于长时间运行的应用程序，运行时 JIT 编译的性能略高于本机映像。</span><span class="sxs-lookup"><span data-stu-id="1676b-282">For long-running applications, run-time JIT compilation performs slightly better than native images.</span></span> <span data-ttu-id="1676b-283">（硬绑定某种程度上可减少这一性能差别。）</span><span class="sxs-lookup"><span data-stu-id="1676b-283">(Hard binding can mitigate this performance difference to some degree.)</span></span>

<a name="BaseAddresses"></a>

## <a name="importance-of-assembly-base-addresses"></a><span data-ttu-id="1676b-284">程序集基址的重要性</span><span class="sxs-lookup"><span data-stu-id="1676b-284">Importance of assembly base addresses</span></span>

<span data-ttu-id="1676b-285">因为本机映像为 Windows PE 文件，所以它们和其他可执行文件一样有着相同的重定基址问题。</span><span class="sxs-lookup"><span data-stu-id="1676b-285">Because native images are Windows PE files, they are subject to the same rebasing issues as other executable files.</span></span> <span data-ttu-id="1676b-286">如果采用硬绑定，则重定位的性能开销甚至更显著。</span><span class="sxs-lookup"><span data-stu-id="1676b-286">The performance cost of relocation is even more pronounced if hard binding is employed.</span></span>

<span data-ttu-id="1676b-287">若要设置本机映像的基址，请使用编译器的相应选项设置程序集的基址。</span><span class="sxs-lookup"><span data-stu-id="1676b-287">To set the base address for a native image, use the appropriate option of your compiler to set the base address for the assembly.</span></span> <span data-ttu-id="1676b-288">Ngen.exe 对本机映像使用此基址。</span><span class="sxs-lookup"><span data-stu-id="1676b-288">Ngen.exe uses this base address for the native image.</span></span>

> [!NOTE]
> <span data-ttu-id="1676b-289">本机映像大于创建它时所基于的托管程序集。</span><span class="sxs-lookup"><span data-stu-id="1676b-289">Native images are larger than the managed assemblies from which they were created.</span></span> <span data-ttu-id="1676b-290">基址必须进行计算以允许使用这些更大的大小。</span><span class="sxs-lookup"><span data-stu-id="1676b-290">Base addresses must be calculated to allow for these larger sizes.</span></span>

<span data-ttu-id="1676b-291">可使用 dumpbin.exe 之类的工具查看本机映像的首选基址。</span><span class="sxs-lookup"><span data-stu-id="1676b-291">You can use a tool such as dumpbin.exe to view the preferred base address of a native image.</span></span>

<a name="HardBinding"></a>

## <a name="hard-binding"></a><span data-ttu-id="1676b-292">硬绑定</span><span class="sxs-lookup"><span data-stu-id="1676b-292">Hard binding</span></span>

<span data-ttu-id="1676b-293">硬绑定增加吞吐量并减少本机映像的工作集大小。</span><span class="sxs-lookup"><span data-stu-id="1676b-293">Hard binding increases throughput and reduces working set size for native images.</span></span> <span data-ttu-id="1676b-294">硬绑定的缺点是加载程序集时必须加载硬绑定到程序集的所有映像。</span><span class="sxs-lookup"><span data-stu-id="1676b-294">The disadvantage of hard binding is that all the images that are hard bound to an assembly must be loaded when the assembly is loaded.</span></span> <span data-ttu-id="1676b-295">对于大型应用程序，这会大大增加启动时间。</span><span class="sxs-lookup"><span data-stu-id="1676b-295">This can significantly increase startup time for a large application.</span></span>

<span data-ttu-id="1676b-296">硬绑定适合于在所有应用程序性能关键的方案中加载的依赖项。</span><span class="sxs-lookup"><span data-stu-id="1676b-296">Hard binding is appropriate for dependencies that are loaded in all your application's performance-critical scenarios.</span></span> <span data-ttu-id="1676b-297">与本机映像使用情况的任何方面一样，仔细测量性能是确定硬绑定是否可改善应用程序性能的唯一方式。</span><span class="sxs-lookup"><span data-stu-id="1676b-297">As with any aspect of native image use, careful performance measurements are the only way to determine whether hard binding improves your application's performance.</span></span>

<span data-ttu-id="1676b-298"><xref:System.Runtime.CompilerServices.DependencyAttribute> 和 <xref:System.Runtime.CompilerServices.DefaultDependencyAttribute> 特性可使你向 Ngen.exe 提供硬绑定提示。</span><span class="sxs-lookup"><span data-stu-id="1676b-298">The <xref:System.Runtime.CompilerServices.DependencyAttribute> and <xref:System.Runtime.CompilerServices.DefaultDependencyAttribute> attributes allow you to provide hard binding hints to Ngen.exe.</span></span>

> [!NOTE]
> <span data-ttu-id="1676b-299">这些特性是对 Ngen.exe 的提示，而不是命令。</span><span class="sxs-lookup"><span data-stu-id="1676b-299">These attributes are hints to Ngen.exe, not commands.</span></span> <span data-ttu-id="1676b-300">使用这些提示不保证进行硬绑定。</span><span class="sxs-lookup"><span data-stu-id="1676b-300">Using them does not guarantee hard binding.</span></span> <span data-ttu-id="1676b-301">这些特性的含义在将来版本中可能会更改。</span><span class="sxs-lookup"><span data-stu-id="1676b-301">The meaning of these attributes may change in future releases.</span></span>

<a name="DependencyHint"></a>

### <a name="specifying-a-binding-hint-for-a-dependency"></a><span data-ttu-id="1676b-302">为依赖项指定绑定提示</span><span class="sxs-lookup"><span data-stu-id="1676b-302">Specifying a binding hint for a dependency</span></span>

<span data-ttu-id="1676b-303">将 <xref:System.Runtime.CompilerServices.DependencyAttribute> 应用于程序集可指示加载指定依赖项的可能性。</span><span class="sxs-lookup"><span data-stu-id="1676b-303">Apply the <xref:System.Runtime.CompilerServices.DependencyAttribute> to an assembly to indicate the likelihood that a specified dependency will be loaded.</span></span> <span data-ttu-id="1676b-304"><xref:System.Runtime.CompilerServices.LoadHint.Always?displayProperty=nameWithType> 指示适合进行硬绑定，<xref:System.Runtime.CompilerServices.LoadHint.Default> 指示应使用依赖项的默认提示，而 <xref:System.Runtime.CompilerServices.LoadHint.Sometimes> 则指示不适合使用硬绑定。</span><span class="sxs-lookup"><span data-stu-id="1676b-304"><xref:System.Runtime.CompilerServices.LoadHint.Always?displayProperty=nameWithType> indicates that hard binding is appropriate, <xref:System.Runtime.CompilerServices.LoadHint.Default> indicates that the default for the dependency should be used, and <xref:System.Runtime.CompilerServices.LoadHint.Sometimes> indicates that hard binding is not appropriate.</span></span>

<span data-ttu-id="1676b-305">下面的代码显示有两个依赖项的程序集的特性。</span><span class="sxs-lookup"><span data-stu-id="1676b-305">The following code shows the attributes for an assembly that has two dependencies.</span></span> <span data-ttu-id="1676b-306">第一个依赖项 (Assembly1) 适合于进行硬绑定，而第二个 (Assembly2) 不适合进行硬绑定。</span><span class="sxs-lookup"><span data-stu-id="1676b-306">The first dependency (Assembly1) is an appropriate candidate for hard binding, and the second (Assembly2) is not.</span></span>

```vb
Imports System.Runtime.CompilerServices
<Assembly:DependencyAttribute("Assembly1", LoadHint.Always)>
<Assembly:DependencyAttribute("Assembly2", LoadHint.Sometimes)>
```

```csharp
using System.Runtime.CompilerServices;
[assembly:DependencyAttribute("Assembly1", LoadHint.Always)]
[assembly:DependencyAttribute("Assembly2", LoadHint.Sometimes)]
```

```cpp
using namespace System::Runtime::CompilerServices;
[assembly:DependencyAttribute("Assembly1", LoadHint.Always)];
[assembly:DependencyAttribute("Assembly2", LoadHint.Sometimes)];
```

<span data-ttu-id="1676b-307">程序集名称不包括文件扩展名。</span><span class="sxs-lookup"><span data-stu-id="1676b-307">The assembly name does not include the file name extension.</span></span> <span data-ttu-id="1676b-308">可使用显示名称。</span><span class="sxs-lookup"><span data-stu-id="1676b-308">Display names can be used.</span></span>

<a name="AssemblyHint"></a>

### <a name="specifying-a-default-binding-hint-for-an-assembly"></a><span data-ttu-id="1676b-309">为程序集指定默认绑定提示</span><span class="sxs-lookup"><span data-stu-id="1676b-309">Specifying a default binding hint for an assembly</span></span>

<span data-ttu-id="1676b-310">只有某些程序集需要默认绑定提示：这些程序集将由依赖于它们的任何应用程序直接并经常使用。</span><span class="sxs-lookup"><span data-stu-id="1676b-310">Default binding hints are only needed for assemblies that will be used immediately and frequently by any application that has a dependency on them.</span></span> <span data-ttu-id="1676b-311">将 <xref:System.Runtime.CompilerServices.DefaultDependencyAttribute> 以及 <xref:System.Runtime.CompilerServices.LoadHint.Always?displayProperty=nameWithType> 应用于这样的程序集可指定应使用硬绑定。</span><span class="sxs-lookup"><span data-stu-id="1676b-311">Apply the <xref:System.Runtime.CompilerServices.DefaultDependencyAttribute> with <xref:System.Runtime.CompilerServices.LoadHint.Always?displayProperty=nameWithType> to such assemblies to specify that hard binding should be used.</span></span>

> [!NOTE]
> <span data-ttu-id="1676b-312">不应将 <xref:System.Runtime.CompilerServices.DefaultDependencyAttribute> 应用于不属于此类别的 .dll 程序集，因为对除 <xref:System.Runtime.CompilerServices.LoadHint.Always?displayProperty=nameWithType> 之外的其他值应用该特性的效果与根本不应用该特性的效果相同。</span><span class="sxs-lookup"><span data-stu-id="1676b-312">There is no reason to apply <xref:System.Runtime.CompilerServices.DefaultDependencyAttribute> to .dll assemblies that do not fall into this category, because applying the attribute with any value other than <xref:System.Runtime.CompilerServices.LoadHint.Always?displayProperty=nameWithType> has the same effect as not applying the attribute at all.</span></span>

<span data-ttu-id="1676b-313">Microsoft 使用 <xref:System.Runtime.CompilerServices.DefaultDependencyAttribute> 指定硬绑定为 .NET Framework 中极少数程序集（如 mscorlib.dll）的默认绑定。</span><span class="sxs-lookup"><span data-stu-id="1676b-313">Microsoft uses the <xref:System.Runtime.CompilerServices.DefaultDependencyAttribute> to specify that hard binding is the default for a very small number of assemblies in the .NET Framework, such as mscorlib.dll.</span></span>

<a name="Deferred"></a>

## <a name="deferred-processing"></a><span data-ttu-id="1676b-314">推迟处理</span><span class="sxs-lookup"><span data-stu-id="1676b-314">Deferred processing</span></span>

<span data-ttu-id="1676b-315">超大型应用程序的本机映像生成过程可能需要相当长的时间。</span><span class="sxs-lookup"><span data-stu-id="1676b-315">Generation of native images for a very large application can take considerable time.</span></span> <span data-ttu-id="1676b-316">同样，更改共享组件或更改计算机设置可能需要更新很多本机映像。</span><span class="sxs-lookup"><span data-stu-id="1676b-316">Similarly, changes to a shared component or changes to computer settings might require many native images to be updated.</span></span> <span data-ttu-id="1676b-317">`install` 和 `update` 操作有一个 `/queue` 选项，该选项将该操作排入队列，以便由本机映像服务推迟执行。</span><span class="sxs-lookup"><span data-stu-id="1676b-317">The `install` and `update` actions have a `/queue` option that queues the operation for deferred execution by the native image service.</span></span> <span data-ttu-id="1676b-318">此外，Ngen.exe 具有 `queue` 和 `executeQueuedItems` 操作，这些操作提供了对本机映像服务的某些控制。</span><span class="sxs-lookup"><span data-stu-id="1676b-318">In addition, Ngen.exe has `queue` and `executeQueuedItems` actions that provide some control over the service.</span></span> <span data-ttu-id="1676b-319">有关详细信息，请参阅[本机映像服务](#native-image-service)。</span><span class="sxs-lookup"><span data-stu-id="1676b-319">For more information, see [Native Image Service](#native-image-service).</span></span>

<a name="JITCompilation"></a>

## <a name="native-images-and-jit-compilation"></a><span data-ttu-id="1676b-320">本机映像和 JIT 编译</span><span class="sxs-lookup"><span data-stu-id="1676b-320">Native images and JIT compilation</span></span>

<span data-ttu-id="1676b-321">如果 Ngen.exe 在程序集中遇到它无法生成的任何方法，则会将这些方法从本机映像中排除。</span><span class="sxs-lookup"><span data-stu-id="1676b-321">If Ngen.exe encounters any methods in an assembly that it cannot generate, it excludes them from the native image.</span></span> <span data-ttu-id="1676b-322">当运行时执行此程序集时，对于那些未包含在本机映像中的方法，它将恢复为 JIT 编译。</span><span class="sxs-lookup"><span data-stu-id="1676b-322">When the runtime executes this assembly, it reverts to JIT compilation for the methods that were not included in the native image.</span></span>

<span data-ttu-id="1676b-323">此外，如果程序集已升级，或者本机映像出于任何原因已失效，则不会使用本机映像。</span><span class="sxs-lookup"><span data-stu-id="1676b-323">In addition, native images are not used if the assembly has been upgraded, or if the image has been invalidated for any reason.</span></span>

<a name="InvalidImages"></a>

### <a name="invalid-images"></a><span data-ttu-id="1676b-324">无效映像</span><span class="sxs-lookup"><span data-stu-id="1676b-324">Invalid images</span></span>

<span data-ttu-id="1676b-325">当你使用 Ngen.exe 创建程序集的本机映像时，输出取决于你指定的命令行选项以及计算机上的某些设置。</span><span class="sxs-lookup"><span data-stu-id="1676b-325">When you use Ngen.exe to create a native image of an assembly, the output depends upon the command-line options that you specify and certain settings on your computer.</span></span> <span data-ttu-id="1676b-326">这些设置包括：</span><span class="sxs-lookup"><span data-stu-id="1676b-326">These settings include the following:</span></span>

- <span data-ttu-id="1676b-327">.NET Framework 的版本。</span><span class="sxs-lookup"><span data-stu-id="1676b-327">The version of the .NET Framework.</span></span>

- <span data-ttu-id="1676b-328">操作系统的版本（在从 Windows 9x 系列更改为 Windows NT 系列的情况下）。</span><span class="sxs-lookup"><span data-stu-id="1676b-328">The version of the operating system, if the change is from the Windows 9x family to the Windows NT family.</span></span>

- <span data-ttu-id="1676b-329">程序集的确切标识（重新编译将更改标识）。</span><span class="sxs-lookup"><span data-stu-id="1676b-329">The exact identity of the assembly (recompilation changes identity).</span></span>

- <span data-ttu-id="1676b-330">程序集引用的所有程序集的确切标识（重新编译将更改标识）。</span><span class="sxs-lookup"><span data-stu-id="1676b-330">The exact identity of all assemblies that the assembly references (recompilation changes identity).</span></span>

- <span data-ttu-id="1676b-331">安全因素。</span><span class="sxs-lookup"><span data-stu-id="1676b-331">Security factors.</span></span>

<span data-ttu-id="1676b-332">Ngen.exe 在生成本机映像时记录这些信息。</span><span class="sxs-lookup"><span data-stu-id="1676b-332">Ngen.exe records this information when it generates a native image.</span></span> <span data-ttu-id="1676b-333">当你执行程序集时，运行时将查找用匹配计算机的当前环境的选项和设置生成的本机映像。</span><span class="sxs-lookup"><span data-stu-id="1676b-333">When you execute an assembly, the runtime looks for the native image generated with options and settings that match the computer's current environment.</span></span> <span data-ttu-id="1676b-334">如果运行时无法找到匹配的本机映像，它将恢复为程序集的 JIT 编译。</span><span class="sxs-lookup"><span data-stu-id="1676b-334">The runtime reverts to JIT compilation of an assembly if it cannot find a matching native image.</span></span> <span data-ttu-id="1676b-335">对计算机的设置和环境进行以下更改会导致本机映像失效：</span><span class="sxs-lookup"><span data-stu-id="1676b-335">The following changes to a computer's settings and environment cause native images to become invalid:</span></span>

- <span data-ttu-id="1676b-336">.NET Framework 的版本。</span><span class="sxs-lookup"><span data-stu-id="1676b-336">The version of the .NET Framework.</span></span>

     <span data-ttu-id="1676b-337">如果将更新应用于 .NET Framework，则使用 Ngen.exe 创建的所有本机映像都将失效。</span><span class="sxs-lookup"><span data-stu-id="1676b-337">If you apply an update to the .NET Framework, all native images that you have created using Ngen.exe become invalid.</span></span> <span data-ttu-id="1676b-338">因此，.NET Framework 的所有更新都执行 `Ngen Update` 命令，以确保重新生成所有的本机映像。</span><span class="sxs-lookup"><span data-stu-id="1676b-338">For this reason, all updates of the .NET Framework execute the `Ngen Update` command, to ensure that all native images are regenerated.</span></span> <span data-ttu-id="1676b-339">.NET Framework 为它安装的 .NET Framework 库自动创建新的本机映像。</span><span class="sxs-lookup"><span data-stu-id="1676b-339">The .NET Framework automatically creates new native images for the .NET Framework libraries that it installs.</span></span>

- <span data-ttu-id="1676b-340">操作系统的版本（在从 Windows 9x 系列更改为 Windows NT 系列的情况下）。</span><span class="sxs-lookup"><span data-stu-id="1676b-340">The version of the operating system, if the change is from the Windows 9x family to the Windows NT family.</span></span>

     <span data-ttu-id="1676b-341">例如，如果计算机上运行的操作系统版本从 Windows 98 更改为 Windows XP，则存储在本机映像缓存中的所有本机映像都将失效。</span><span class="sxs-lookup"><span data-stu-id="1676b-341">For example, if the version of the operating system running on a computer changes from Windows 98 to Windows XP, all native images stored in the native image cache become invalid.</span></span> <span data-ttu-id="1676b-342">但是，如果将操作系统从 Windows 2000 更改为 Windows XP，则这些映像将不会失效。</span><span class="sxs-lookup"><span data-stu-id="1676b-342">However, if the operating system changes from Windows 2000 to Windows XP, the images are not invalidated.</span></span>

- <span data-ttu-id="1676b-343">程序集的确切标识。</span><span class="sxs-lookup"><span data-stu-id="1676b-343">The exact identity of the assembly.</span></span>

     <span data-ttu-id="1676b-344">如果重新编译程序集，则程序集的相应本机映像将失效。</span><span class="sxs-lookup"><span data-stu-id="1676b-344">If you recompile an assembly, the assembly's corresponding native image becomes invalid.</span></span>

- <span data-ttu-id="1676b-345">程序集引用的任何程序集的确切标识。</span><span class="sxs-lookup"><span data-stu-id="1676b-345">The exact identity of any assemblies the assembly references.</span></span>

     <span data-ttu-id="1676b-346">如果更新一个托管程序集，则所有直接或间接依赖该程序集的本机映像都将失效，并需要重新生成。</span><span class="sxs-lookup"><span data-stu-id="1676b-346">If you update a managed assembly, all native images that directly or indirectly depend on that assembly become invalid and need to be regenerated.</span></span> <span data-ttu-id="1676b-347">这既包括一般引用，也包括硬绑定依赖项。</span><span class="sxs-lookup"><span data-stu-id="1676b-347">This includes both ordinary references and hard-bound dependencies.</span></span> <span data-ttu-id="1676b-348">当应用软件更新时，安装程序应执行 `Ngen Update` 命令，以确保重新生成所有依赖的本机映像。</span><span class="sxs-lookup"><span data-stu-id="1676b-348">Whenever a software update is applied, the installation program should execute an `Ngen Update` command to ensure that all dependent native images are regenerated.</span></span>

- <span data-ttu-id="1676b-349">安全因素。</span><span class="sxs-lookup"><span data-stu-id="1676b-349">Security factors.</span></span>

     <span data-ttu-id="1676b-350">更改计算机安全策略以限制先前授予某个程序集的权限，这样会导致该程序集的先前编译的本机映像失效。</span><span class="sxs-lookup"><span data-stu-id="1676b-350">Changing machine security policy to restrict permissions previously granted to an assembly can cause a previously compiled native image for that assembly to become invalid.</span></span>

     <span data-ttu-id="1676b-351">有关公共语言运行时如何管理代码访问安全性以及如何使用权限的详细信息，请参阅[代码访问安全](../misc/code-access-security.md)。</span><span class="sxs-lookup"><span data-stu-id="1676b-351">For detailed information about how the common language runtime administers code access security and how to use permissions, see [Code Access Security](../misc/code-access-security.md).</span></span>

<a name="Troubleshooting"></a>

## <a name="troubleshooting"></a><span data-ttu-id="1676b-352">疑难解答</span><span class="sxs-lookup"><span data-stu-id="1676b-352">Troubleshooting</span></span>

<span data-ttu-id="1676b-353">可通过参阅以下疑难解答主题，了解应用程序正在使用和无法使用的本机映像，由此确定 JIT 编译器何时开始编译方法以及如何选择退出指定方法的本机映像编译。</span><span class="sxs-lookup"><span data-stu-id="1676b-353">The following troubleshooting topics allow you to see which native images are being used and which cannot be used by your application, to determine when the JIT compiler starts to compile a method, and shows how to opt out of native image compilation of specified methods.</span></span>

<a name="Fusion"></a>

### <a name="assembly-binding-log-viewer"></a><span data-ttu-id="1676b-354">程序集绑定日志查看器</span><span class="sxs-lookup"><span data-stu-id="1676b-354">Assembly Binding Log Viewer</span></span>

<span data-ttu-id="1676b-355">若要确认应用程序正在使用本机映像，可使用 [Fuslogvw.exe（程序集绑定日志查看器）](fuslogvw-exe-assembly-binding-log-viewer.md)。</span><span class="sxs-lookup"><span data-stu-id="1676b-355">To confirm that native images are being used by your application, you can use the [Fuslogvw.exe (Assembly Binding Log Viewer)](fuslogvw-exe-assembly-binding-log-viewer.md).</span></span> <span data-ttu-id="1676b-356">在绑定日志查看器窗口上，选择“日志类别”  框中的“本机映像”  。</span><span class="sxs-lookup"><span data-stu-id="1676b-356">Select **Native Images** in the **Log Categories** box on the binding log viewer window.</span></span> <span data-ttu-id="1676b-357">Fuslogvw.exe 提供了有关本机映像被拒绝的原因的信息。</span><span class="sxs-lookup"><span data-stu-id="1676b-357">Fuslogvw.exe provides information about why a native image was rejected.</span></span>

<a name="MDA"></a>

### <a name="the-jitcompilationstart-managed-debugging-assistant"></a><span data-ttu-id="1676b-358">JITCompilationStart 托管调试助手</span><span class="sxs-lookup"><span data-stu-id="1676b-358">The JITCompilationStart managed debugging assistant</span></span>

<span data-ttu-id="1676b-359">可使用 [jitCompilationStart](../debug-trace-profile/jitcompilationstart-mda.md) 托管调试助手 (MDA) 来确定 JIT 编译器何时开始编译函数。</span><span class="sxs-lookup"><span data-stu-id="1676b-359">You can use the [jitCompilationStart](../debug-trace-profile/jitcompilationstart-mda.md) managed debugging assistant (MDA) to determine when the JIT compiler starts to compile a function.</span></span>

<a name="OptOut"></a>

### <a name="opting-out-of-native-image-generation"></a><span data-ttu-id="1676b-360">选择退出本机映像生成</span><span class="sxs-lookup"><span data-stu-id="1676b-360">Opting out of native image generation</span></span>

<span data-ttu-id="1676b-361">在某些情况下，NGen.exe 可能难以为特定方法生成本机映像，或者操作者可能更愿意对方法进行 JIT 编译而不是将其编译为本机映像。</span><span class="sxs-lookup"><span data-stu-id="1676b-361">In some cases, NGen.exe may have difficulty generating a native image for a specific method, or you may prefer that the method be JIT compiled rather then compiled to a native image.</span></span> <span data-ttu-id="1676b-362">在这种情况下，可使用 `System.Runtime.BypassNGenAttribute` 特性阻止 NGen.exe 为特定方法生成本机映像。</span><span class="sxs-lookup"><span data-stu-id="1676b-362">In this case, you can use the `System.Runtime.BypassNGenAttribute` attribute to prevent NGen.exe from generating a native image for a particular method.</span></span> <span data-ttu-id="1676b-363">必须分别将该特性应用于不想将其中代码包含在本机映像中的各个方法。</span><span class="sxs-lookup"><span data-stu-id="1676b-363">The attribute must be applied individually to each method whose code you do not want to include in the native image.</span></span> <span data-ttu-id="1676b-364">NGen.exe 可识别该特性，但不会在本机映像中为相应的方法生成代码。</span><span class="sxs-lookup"><span data-stu-id="1676b-364">NGen.exe recognizes the attribute and does not generate code in the native image for the corresponding method.</span></span>

<span data-ttu-id="1676b-365">但请注意，`BypassNGenAttribute` 不定义为 .NET Framework 类库中的类型。</span><span class="sxs-lookup"><span data-stu-id="1676b-365">Note, however, that `BypassNGenAttribute` is not defined as a type in the .NET Framework Class Library.</span></span> <span data-ttu-id="1676b-366">为在代码中使用该特性，必须先按以下所示对其进行定义：</span><span class="sxs-lookup"><span data-stu-id="1676b-366">In order to consume the attribute in your code, you must first define it as follows:</span></span>

[!code-csharp[System.Runtime.BypassNGenAttribute#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/System.Runtime.BypassNGenAttribute/cs/Optout1.cs#1)]
[!code-vb[System.Runtime.BypassNGenAttribute#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/System.Runtime.BypassNGenAttribute/vb/Optout1.vb#1)]

<span data-ttu-id="1676b-367">然后就可对每个方法应用该特性。</span><span class="sxs-lookup"><span data-stu-id="1676b-367">You can then apply the attribute on a per-method basis.</span></span> <span data-ttu-id="1676b-368">以下示例指示本机映像生成器不应为 `ExampleClass.ToJITCompile` 方法生成本机映像。</span><span class="sxs-lookup"><span data-stu-id="1676b-368">The following example instructs the Native Image Generator that it should not generate a native image for the `ExampleClass.ToJITCompile` method.</span></span>

[!code-csharp[System.Runtime.BypassNGenAttribute#2](../../../samples/snippets/csharp/VS_Snippets_CLR_System/System.Runtime.BypassNGenAttribute/cs/Optout1.cs#2)]
[!code-vb[System.Runtime.BypassNGenAttribute#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/System.Runtime.BypassNGenAttribute/vb/Optout1.vb#2)]

## <a name="examples"></a><span data-ttu-id="1676b-369">示例</span><span class="sxs-lookup"><span data-stu-id="1676b-369">Examples</span></span>

<span data-ttu-id="1676b-370">下面的命令为当前目录中的 `ClientApp.exe` 生成本机映像，并在本机映像缓存中安装该映像。</span><span class="sxs-lookup"><span data-stu-id="1676b-370">The following command generates a native image for `ClientApp.exe`, located in the current directory, and installs the image in the native image cache.</span></span> <span data-ttu-id="1676b-371">如果该程序集存在配置文件，Ngen.exe 将使用它。</span><span class="sxs-lookup"><span data-stu-id="1676b-371">If a configuration file exists for the assembly, Ngen.exe uses it.</span></span> <span data-ttu-id="1676b-372">此外，还会为 `ClientApp.exe` 引用的所有 .dll 文件生成本机映像。</span><span class="sxs-lookup"><span data-stu-id="1676b-372">In addition, native images are generated for any .dll files that `ClientApp.exe` references.</span></span>

```console
ngen install ClientApp.exe
```

<span data-ttu-id="1676b-373">使用 Ngen.exe 安装的映像也称为根。</span><span class="sxs-lookup"><span data-stu-id="1676b-373">An image installed with Ngen.exe is also called a root.</span></span> <span data-ttu-id="1676b-374">根可以为应用程序或共享组件。</span><span class="sxs-lookup"><span data-stu-id="1676b-374">A root can be an application or a shared component.</span></span>

<span data-ttu-id="1676b-375">下面的命令生成具有指定路径的 `MyAssembly.exe` 的本机映像。</span><span class="sxs-lookup"><span data-stu-id="1676b-375">The following command generates a native image for `MyAssembly.exe` with the specified path.</span></span>

```console
ngen install c:\myfiles\MyAssembly.exe
```

<span data-ttu-id="1676b-376">当查找程序集及其依赖项时，Ngen.exe 使用与公共语言运行时所使用的相同的探查逻辑。</span><span class="sxs-lookup"><span data-stu-id="1676b-376">When locating assemblies and their dependencies, Ngen.exe uses the same probing logic used by the common language runtime.</span></span> <span data-ttu-id="1676b-377">默认情况下，包含 `ClientApp.exe` 的目录用作应用程序基目录，所有程序集的探查均从此目录开始。</span><span class="sxs-lookup"><span data-stu-id="1676b-377">By default, the directory that contains `ClientApp.exe` is used as the application base directory, and all assembly probing begins in this directory.</span></span> <span data-ttu-id="1676b-378">使用 `/AppBase` 选项可重写此行为。</span><span class="sxs-lookup"><span data-stu-id="1676b-378">You can override this behavior by using the `/AppBase` option.</span></span>

> [!NOTE]
> <span data-ttu-id="1676b-379">这是对 .NET Framework 1.0 和 1.1 版中的 Ngen.exe 行为的更改，在这些版本中，应用程序基目录设置为当前目录。</span><span class="sxs-lookup"><span data-stu-id="1676b-379">This is a change from Ngen.exe behavior in the .NET Framework versions 1.0 and 1.1, where the application base is set to the current directory.</span></span>

<span data-ttu-id="1676b-380">程序集可以具有不带引用的依赖项（例如，它使用 <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType> 方法加载 .dll 文件）。</span><span class="sxs-lookup"><span data-stu-id="1676b-380">An assembly can have a dependency without a reference, for example if it loads a .dll file by using the <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="1676b-381">你可以借助 `/ExeConfig` 使用应用程序程序集的配置信息来为这样的 .dll 文件创建本机映像。</span><span class="sxs-lookup"><span data-stu-id="1676b-381">You can create a native image for such a .dll file by using configuration information for the application assembly, with the `/ExeConfig` option.</span></span> <span data-ttu-id="1676b-382">下面的命令使用 `MyLib.dll,` 中的配置信息为 `MyApp.exe` 生成一个本机映像。</span><span class="sxs-lookup"><span data-stu-id="1676b-382">The following command generates a native image for `MyLib.dll,` using the configuration information from `MyApp.exe`.</span></span>

```console
ngen install c:\myfiles\MyLib.dll /ExeConfig:c:\myapps\MyApp.exe
```

<span data-ttu-id="1676b-383">在移除应用程序时将不移除以此方式安装的程序集。</span><span class="sxs-lookup"><span data-stu-id="1676b-383">Assemblies installed in this way are not removed when the application is removed.</span></span>

<span data-ttu-id="1676b-384">若要卸载依赖项，请使用与安装时相同的命令行选项。</span><span class="sxs-lookup"><span data-stu-id="1676b-384">To uninstall a dependency, use the same command-line options that were used to install it.</span></span> <span data-ttu-id="1676b-385">下面的命令卸载上一个示例中的 `MyLib.dll`。</span><span class="sxs-lookup"><span data-stu-id="1676b-385">The following command uninstalls the `MyLib.dll` from the previous example.</span></span>

```console
ngen uninstall c:\myfiles\MyLib.dll /ExeConfig:c:\myapps\MyApp.exe
```

<span data-ttu-id="1676b-386">若要在全局程序集缓存中为程序集创建本机映像，请使用该程序集的显示名称。</span><span class="sxs-lookup"><span data-stu-id="1676b-386">To create a native image for an assembly in the global assembly cache, use the display name of the assembly.</span></span> <span data-ttu-id="1676b-387">例如:</span><span class="sxs-lookup"><span data-stu-id="1676b-387">For example:</span></span>

```console
ngen install "ClientApp, Version=1.0.0.0, Culture=neutral,
  PublicKeyToken=3c7ba247adcd2081, processorArchitecture=MSIL"
```

<span data-ttu-id="1676b-388">NGen.exe 会为你安装的每个方案生成一个单独的映像集。</span><span class="sxs-lookup"><span data-stu-id="1676b-388">NGen.exe generates a separate set of images for each scenario you install.</span></span> <span data-ttu-id="1676b-389">例如，下面的命令为正常操作生成一个完整的本机映像集，为调试生成另一个完整的映像集，并为探测生成第三个映像集：</span><span class="sxs-lookup"><span data-stu-id="1676b-389">For example, the following commands install a complete set of native images for normal operation, another complete set for debugging, and a third for profiling:</span></span>

```console
ngen install MyApp.exe
ngen install MyApp.exe /debug
ngen install MyApp.exe /profile
```

### <a name="displaying-the-native-image-cache"></a><span data-ttu-id="1676b-390">显示本机映像缓存</span><span class="sxs-lookup"><span data-stu-id="1676b-390">Displaying the Native Image Cache</span></span>

<span data-ttu-id="1676b-391">一旦本机映像安装到缓存中，就可使用 Ngen.exe 显示它们。</span><span class="sxs-lookup"><span data-stu-id="1676b-391">Once native images are installed in the cache, they can be displayed using Ngen.exe.</span></span> <span data-ttu-id="1676b-392">下面的命令显示本机映像缓存中的所有本机映像。</span><span class="sxs-lookup"><span data-stu-id="1676b-392">The following command displays all native images in the native image cache.</span></span>

```console
ngen display
```

<span data-ttu-id="1676b-393">`display` 操作首先列出所有根程序集，然后列出计算机上所有本机映像的列表。</span><span class="sxs-lookup"><span data-stu-id="1676b-393">The `display` action lists all the root assemblies first, followed by a list of all the native images on the computer.</span></span>

<span data-ttu-id="1676b-394">使用程序集的简单名称仅显示该程序集的信息。</span><span class="sxs-lookup"><span data-stu-id="1676b-394">Use the simple name of an assembly to display information only for that assembly.</span></span> <span data-ttu-id="1676b-395">下面的命令显示本机映像缓存中与部分名称 `MyAssembly` 匹配的所有本机映像、其依赖项以及所有依赖 `MyAssembly` 的根：</span><span class="sxs-lookup"><span data-stu-id="1676b-395">The following command displays all native images in the native image cache that match the partial name `MyAssembly`, their dependencies, and all roots that have a dependency on `MyAssembly`:</span></span>

```console
ngen display MyAssembly
```

<span data-ttu-id="1676b-396">了解哪些根依赖于共享组件程序集对于在共享组件升级后确定 `update` 操作的影响非常有用。</span><span class="sxs-lookup"><span data-stu-id="1676b-396">Knowing what roots depend on a shared component assembly is useful in gauging the impact of an `update` action after the shared component is upgraded.</span></span>

<span data-ttu-id="1676b-397">如果指定了程序集的文件扩展名，则必须指定路径，或从包含该程序集的目录执行 Ngen.exe：</span><span class="sxs-lookup"><span data-stu-id="1676b-397">If you specify an assembly's file extension, you must either specify the path or execute Ngen.exe from the directory containing the assembly:</span></span>

```console
ngen display c:\myApps\MyAssembly.exe
```

<span data-ttu-id="1676b-398">下面的命令显示本机映像缓存中名为 `MyAssembly`、版本为 1.0.0.0 的所有本机映像。</span><span class="sxs-lookup"><span data-stu-id="1676b-398">The following command displays all native images in the native image cache with the name `MyAssembly` and the version 1.0.0.0.</span></span>

```console
ngen display "myAssembly, version=1.0.0.0"
```

### <a name="updating-images"></a><span data-ttu-id="1676b-399">更新映像</span><span class="sxs-lookup"><span data-stu-id="1676b-399">Updating Images</span></span>

<span data-ttu-id="1676b-400">映像通常是在共享组件升级之后进行更新的。</span><span class="sxs-lookup"><span data-stu-id="1676b-400">Images are typically updated after a shared component has been upgraded.</span></span> <span data-ttu-id="1676b-401">若要更新本身发生更改或者其依赖项发生了更改的所有本机映像，请使用不带任何参数的 `update` 操作。</span><span class="sxs-lookup"><span data-stu-id="1676b-401">To update all native images that have changed, or whose dependencies have changed, use the `update` action with no arguments.</span></span>

```console
ngen update
```

<span data-ttu-id="1676b-402">更新所有映像可能会耗费很长时间。</span><span class="sxs-lookup"><span data-stu-id="1676b-402">Updating all images can be a lengthy process.</span></span> <span data-ttu-id="1676b-403">使用 `/queue` 选项可对更新操作进行排队以等候本机映像服务执行。</span><span class="sxs-lookup"><span data-stu-id="1676b-403">You can queue the updates for execution by the native image service by using the `/queue` option.</span></span> <span data-ttu-id="1676b-404">有关 `/queue` 选项和安装优先级的详细信息，请参阅[本机映像服务](#native-image-service)。</span><span class="sxs-lookup"><span data-stu-id="1676b-404">For more information on the `/queue` option and installation priorities, see [Native Image Service](#native-image-service).</span></span>

```console
ngen update /queue
```

### <a name="uninstalling-images"></a><span data-ttu-id="1676b-405">卸载映像</span><span class="sxs-lookup"><span data-stu-id="1676b-405">Uninstalling Images</span></span>

<span data-ttu-id="1676b-406">Ngen.exe 维护依赖项的列表，因此，只有当依赖于这些共享组件的所有程序集都被移除后，才会移除这些共享组件。</span><span class="sxs-lookup"><span data-stu-id="1676b-406">Ngen.exe maintains a list of dependencies, so that shared components are removed only when all assemblies that depend on them have been removed.</span></span> <span data-ttu-id="1676b-407">此外，已安装为根的共享组件不会被移除。</span><span class="sxs-lookup"><span data-stu-id="1676b-407">In addition, a shared component is not removed if it has been installed as a root.</span></span>

<span data-ttu-id="1676b-408">下面的命令卸载根 `ClientApp.exe` 的所有方案：</span><span class="sxs-lookup"><span data-stu-id="1676b-408">The following command uninstalls all scenarios for the root `ClientApp.exe`:</span></span>

```console
ngen uninstall ClientApp
```

<span data-ttu-id="1676b-409">`uninstall` 操作可用于移除特定方案。</span><span class="sxs-lookup"><span data-stu-id="1676b-409">The `uninstall` action can be used to remove specific scenarios.</span></span> <span data-ttu-id="1676b-410">下面的命令卸载 `ClientApp.exe` 的所有调试方案：</span><span class="sxs-lookup"><span data-stu-id="1676b-410">The following command uninstalls all debug scenarios for `ClientApp.exe`:</span></span>

```console
ngen uninstall ClientApp /debug
```

> [!NOTE]
> <span data-ttu-id="1676b-411">卸载 `/debug` 方案不会卸载同时包含 `/profile` 和 `/debug.` 的方案</span><span class="sxs-lookup"><span data-stu-id="1676b-411">Uninstalling `/debug` scenarios does not uninstall a scenario that includes both `/profile` and `/debug.`</span></span>

<span data-ttu-id="1676b-412">下面的命令卸载特定版本的 `ClientApp.exe` 的所有方案：</span><span class="sxs-lookup"><span data-stu-id="1676b-412">The following command uninstalls all scenarios for a specific version of `ClientApp.exe`:</span></span>

```console
ngen uninstall "ClientApp, Version=1.0.0.0"
```

<span data-ttu-id="1676b-413">下面的命令卸载 `"ClientApp, Version=1.0.0.0, Culture=neutral, PublicKeyToken=3c7ba247adcd2081, processorArchitecture=MSIL",` 的所有方案，或者只卸载该程序集的调试方案：</span><span class="sxs-lookup"><span data-stu-id="1676b-413">The following commands uninstall all scenarios for `"ClientApp, Version=1.0.0.0, Culture=neutral, PublicKeyToken=3c7ba247adcd2081, processorArchitecture=MSIL",` or just the debug scenario for that assembly:</span></span>

```console
ngen uninstall "ClientApp, Version=1.0.0.0, Culture=neutral,
  PublicKeyToken=3c7ba247adcd2081, processorArchitecture=MSIL"
ngen uninstall "ClientApp, Version=1.0.0.0, Culture=neutral,
  PublicKeyToken=3c7ba247adcd2081, processorArchitecture=MSIL" /debug
```

<span data-ttu-id="1676b-414">与 `install` 操作一样，如果提供了扩展名，则需要从包含该程序集的目录执行 Ngen.exe，或者指定完整路径。</span><span class="sxs-lookup"><span data-stu-id="1676b-414">As with the `install` action, supplying an extension requires either executing Ngen.exe from the directory containing the assembly or specifying a full path.</span></span>

<span data-ttu-id="1676b-415">有关本机映像服务的相关示例，请参阅[本机映像服务](#native-image-service)。</span><span class="sxs-lookup"><span data-stu-id="1676b-415">For examples relating to the native image service, see [Native Image Service](#native-image-service).</span></span>

## <a name="native-image-task"></a><span data-ttu-id="1676b-416">本机映像任务</span><span class="sxs-lookup"><span data-stu-id="1676b-416">Native Image Task</span></span>

<span data-ttu-id="1676b-417">本机映像任务是生成和维护本机映像的 Windows 任务。</span><span class="sxs-lookup"><span data-stu-id="1676b-417">The native image task is a Windows task that generates and maintains native images.</span></span> <span data-ttu-id="1676b-418">本机映像任务为支持方案自动生成并回收本机映像。</span><span class="sxs-lookup"><span data-stu-id="1676b-418">The native image task generates and reclaims native images automatically for supported scenarios.</span></span> <span data-ttu-id="1676b-419">它还使安装程序能使用 [Ngen.exe（本机映像生成器）](ngen-exe-native-image-generator.md)来创建和更新在延迟时间的本机映像。</span><span class="sxs-lookup"><span data-stu-id="1676b-419">It also enables installers to use [Ngen.exe (Native Image Generator)](ngen-exe-native-image-generator.md) to create and update native images at a deferred time.</span></span>

<span data-ttu-id="1676b-420">本机映像任务对计算机上受支持的每个 CPU 体系结构进行注册后，允许对以每个体系结构为目标的应用程序进行编译：</span><span class="sxs-lookup"><span data-stu-id="1676b-420">The native image task is registered once for each CPU architecture supported on a computer, to allow compilation for applications that target each architecture:</span></span>

|<span data-ttu-id="1676b-421">任务名称</span><span class="sxs-lookup"><span data-stu-id="1676b-421">Task name</span></span>|<span data-ttu-id="1676b-422">32 位计算机</span><span class="sxs-lookup"><span data-stu-id="1676b-422">32-bit computer</span></span>|<span data-ttu-id="1676b-423">64 位计算机</span><span class="sxs-lookup"><span data-stu-id="1676b-423">64-bit computer</span></span>|
|---------------|----------------------|----------------------|
|<span data-ttu-id="1676b-424">NET Framework NGEN v4.0.30319</span><span class="sxs-lookup"><span data-stu-id="1676b-424">NET Framework NGEN v4.0.30319</span></span>|<span data-ttu-id="1676b-425">是</span><span class="sxs-lookup"><span data-stu-id="1676b-425">Yes</span></span>|<span data-ttu-id="1676b-426">是</span><span class="sxs-lookup"><span data-stu-id="1676b-426">Yes</span></span>|
|<span data-ttu-id="1676b-427">NET Framework NGEN v4.0.30319 64</span><span class="sxs-lookup"><span data-stu-id="1676b-427">NET Framework NGEN v4.0.30319 64</span></span>|<span data-ttu-id="1676b-428">No</span><span class="sxs-lookup"><span data-stu-id="1676b-428">No</span></span>|<span data-ttu-id="1676b-429">是</span><span class="sxs-lookup"><span data-stu-id="1676b-429">Yes</span></span>|

<span data-ttu-id="1676b-430">在运行 Windows 8 或更高版本时，本机映像任务在 .NET Framework 4.5 和更高版本中可用。</span><span class="sxs-lookup"><span data-stu-id="1676b-430">The native image task is available in the .NET Framework 4.5 and later versions, when running on Windows 8 or later.</span></span> <span data-ttu-id="1676b-431">在 Windows 早期版本中，.NET Framework 使用 [本机映像服务](#native-image-service)。</span><span class="sxs-lookup"><span data-stu-id="1676b-431">On earlier versions of Windows, the .NET Framework uses the [Native Image Service](#native-image-service).</span></span>

### <a name="task-lifetime"></a><span data-ttu-id="1676b-432">任务生存期</span><span class="sxs-lookup"><span data-stu-id="1676b-432">Task Lifetime</span></span>

<span data-ttu-id="1676b-433">一般情况下，计算机处于空闲状态时，Windows 任务计划程序将每晚启动本机映像任务。</span><span class="sxs-lookup"><span data-stu-id="1676b-433">In general, the Windows Task Scheduler starts the native image task every night when the computer is idle.</span></span> <span data-ttu-id="1676b-434">该任务检查由应用程序安装程序排列的任何延时工作、任何延时本机映像更新请求和任何自动化映像创建。</span><span class="sxs-lookup"><span data-stu-id="1676b-434">The task checks for any deferred work that is queued by application installers, any deferred native image update requests, and any automatic image creation.</span></span> <span data-ttu-id="1676b-435">任务完成未完成的工作项，然后关闭。</span><span class="sxs-lookup"><span data-stu-id="1676b-435">The task completes outstanding work items and then shuts down.</span></span> <span data-ttu-id="1676b-436">如果计算机在任务运行时停止空闲状态，该任务将停止。</span><span class="sxs-lookup"><span data-stu-id="1676b-436">If the computer stops being idle while the task is running, the task stops.</span></span>

<span data-ttu-id="1676b-437">此外还可以通过任务计划程序 UI 或手动调用 NGen.exe 来启动本机映像任务。</span><span class="sxs-lookup"><span data-stu-id="1676b-437">You can also start the native image task manually through the Task Scheduler UI or through manual calls to NGen.exe.</span></span> <span data-ttu-id="1676b-438">如果通过上述任一方法启动了该任务，则计算机不处于空闲状态时，它将继续运行。</span><span class="sxs-lookup"><span data-stu-id="1676b-438">If the task is started through either of these methods, it will continue running when the computer is no longer idle.</span></span> <span data-ttu-id="1676b-439">优先使用 NGen.exe 手动创建的映像，以启用应用程序安装程序的可预知行为。</span><span class="sxs-lookup"><span data-stu-id="1676b-439">Images created manually by using NGen.exe are prioritized to enable predictable behavior for application installers.</span></span>

## <a name="native-image-service"></a><span data-ttu-id="1676b-440">本机映像服务</span><span class="sxs-lookup"><span data-stu-id="1676b-440">Native Image Service</span></span>

<span data-ttu-id="1676b-441">本机映像任务是生成和维护本机映像的 Windows 任务。</span><span class="sxs-lookup"><span data-stu-id="1676b-441">The native image service is a Windows service that generates and maintains native images.</span></span> <span data-ttu-id="1676b-442">本机映像服务允许开发人员将本机映像的安装和更新延迟到计算机空闲的时段。</span><span class="sxs-lookup"><span data-stu-id="1676b-442">The native image service allows the developer to defer the installation and update of native images to periods when the computer is idle.</span></span>

<span data-ttu-id="1676b-443">通常情况下，本机映像服务通过应用程序安装程序或更新安装程序（安装程序）启动的。</span><span class="sxs-lookup"><span data-stu-id="1676b-443">Normally, the native image service is initiated by the installation program (installer) for an application or update.</span></span> <span data-ttu-id="1676b-444">对于优先级 3 操作，该服务在计算机空闲时执行。</span><span class="sxs-lookup"><span data-stu-id="1676b-444">For priority 3 actions, the service executes during idle time on the computer.</span></span> <span data-ttu-id="1676b-445">该服务将保存其状态，如有必要，能通过多次重新启动后继续运行。</span><span class="sxs-lookup"><span data-stu-id="1676b-445">The service saves its state and is capable of continuing through multiple reboots if necessary.</span></span> <span data-ttu-id="1676b-446">可以对多个映像编译进行排队。</span><span class="sxs-lookup"><span data-stu-id="1676b-446">Multiple image compilations can be queued.</span></span>

<span data-ttu-id="1676b-447">该服务还与手动 Ngen.exe 命令进行交互。</span><span class="sxs-lookup"><span data-stu-id="1676b-447">The service also interacts with the manual Ngen.exe command.</span></span> <span data-ttu-id="1676b-448">手动命令优先于后台活动。</span><span class="sxs-lookup"><span data-stu-id="1676b-448">Manual commands take precedence over background activity.</span></span>

> [!NOTE]
> <span data-ttu-id="1676b-449">在 Windows Vista 上，为本机映像服务显示的名称为“Microsoft.NET Framework NGEN v2.0.50727_X86”或“Microsoft.NET Framework NGEN v2.0.50727_X64”。</span><span class="sxs-lookup"><span data-stu-id="1676b-449">On Windows Vista, the name displayed for the native image service is "Microsoft.NET Framework NGEN v2.0.50727_X86" or "Microsoft.NET Framework NGEN v2.0.50727_X64".</span></span> <span data-ttu-id="1676b-450">在 Microsoft Windows 的所有早期版本上，名称为“.NET 运行时优化服务 v2.0.50727_X86”或“.NET 运行时优化服务 v2.0.50727_X64”。</span><span class="sxs-lookup"><span data-stu-id="1676b-450">On all earlier versions of Microsoft Windows, the name is ".NET Runtime Optimization Service v2.0.50727_X86" or ".NET Runtime Optimization Service v2.0.50727_X64".</span></span>

### <a name="launching-deferred-operations"></a><span data-ttu-id="1676b-451">启动推迟的操作</span><span class="sxs-lookup"><span data-stu-id="1676b-451">Launching Deferred Operations</span></span>

<span data-ttu-id="1676b-452">在开始安装或升级之前，建议暂停该服务。</span><span class="sxs-lookup"><span data-stu-id="1676b-452">Before beginning an installation or upgrade, pausing the service is recommended.</span></span> <span data-ttu-id="1676b-453">这可确保该服务不会在安装程序正在复制文件或将程序集放在全局程序集缓存中时执行。</span><span class="sxs-lookup"><span data-stu-id="1676b-453">This ensures that the service does not execute while the installer is copying files or putting assemblies in the global assembly cache.</span></span> <span data-ttu-id="1676b-454">下面的 Ngen.exe 命令行可以暂停该服务：</span><span class="sxs-lookup"><span data-stu-id="1676b-454">The following Ngen.exe command line pauses the service:</span></span>

```console
ngen queue pause
```

<span data-ttu-id="1676b-455">当已排队所有的延迟操作时，下面的命令会允许恢复服务：</span><span class="sxs-lookup"><span data-stu-id="1676b-455">When all deferred operations have been queued, the following command allows the service to resume:</span></span>

```console
ngen queue continue
```

<span data-ttu-id="1676b-456">若要在安装新应用程序或更新共享组件时，延迟本机映像生成，请将 `/queue` 选项用于 `install` 或 `update` 操作 。</span><span class="sxs-lookup"><span data-stu-id="1676b-456">To defer native image generation when installing a new application or when updating a shared component, use the `/queue` option with the `install` or `update` actions.</span></span> <span data-ttu-id="1676b-457">以下的 Ngen.exe 命令行安装共享组件的本机映像并执行可能已被影响的所有根的更新：</span><span class="sxs-lookup"><span data-stu-id="1676b-457">The following Ngen.exe command lines install a native image for a shared component and perform an update of all roots that may have been affected:</span></span>

```console
ngen install MyComponent /queue
ngen update /queue
```

<span data-ttu-id="1676b-458">`update` 操作将重新生成所有失效的本机映像，而不仅仅是那些使用 `MyComponent` 的本机映像。</span><span class="sxs-lookup"><span data-stu-id="1676b-458">The `update` action regenerates all native images that have been invalidated, not just those that use `MyComponent`.</span></span>

<span data-ttu-id="1676b-459">如果你的应用程序包含多个根，则可以控制延迟操作的优先级。</span><span class="sxs-lookup"><span data-stu-id="1676b-459">If your application consists of many roots, you can control the priority of the deferred actions.</span></span> <span data-ttu-id="1676b-460">以下命令将三个根的安装进行排队。</span><span class="sxs-lookup"><span data-stu-id="1676b-460">The following commands queue the installation of three roots.</span></span> <span data-ttu-id="1676b-461">首先安装 `Assembly1`，无需等待空闲时间。</span><span class="sxs-lookup"><span data-stu-id="1676b-461">`Assembly1` is installed first, without waiting for idle time.</span></span> <span data-ttu-id="1676b-462">此外还可以安装 `Assembly2`，无需等待空闲时间，但要在优先级为 1 的所有操作都完成后。</span><span class="sxs-lookup"><span data-stu-id="1676b-462">`Assembly2` is also installed without waiting for idle time, but after all priority 1 actions have completed.</span></span> <span data-ttu-id="1676b-463">在服务检测到计算机处于空闲状态时安装 `Assembly3`。</span><span class="sxs-lookup"><span data-stu-id="1676b-463">`Assembly3` is installed when the service detects that the computer is idle.</span></span>

```console
ngen install Assembly1 /queue:1
ngen install Assembly2 /queue:2
ngen install Assembly3 /queue:3
```

<span data-ttu-id="1676b-464">可以使用 `executeQueuedItems` 操作强制排队操作同步发生。</span><span class="sxs-lookup"><span data-stu-id="1676b-464">You can force queued actions to occur synchronously by using the `executeQueuedItems` action.</span></span> <span data-ttu-id="1676b-465">如果你提供可选优先级，此操作将仅影响具有相等或较低优先级的已排队操作。</span><span class="sxs-lookup"><span data-stu-id="1676b-465">If you supply the optional priority, this action affects only the queued actions that have equal or lower priority.</span></span> <span data-ttu-id="1676b-466">默认优先级为 3，因此下面的 Ngen.exe 命令将立即处理所有排队的操作，并且在完成前不会返回：</span><span class="sxs-lookup"><span data-stu-id="1676b-466">The default priority is 3, so the following Ngen.exe command processes all queued actions immediately, and does not return until they are finished:</span></span>

```console
ngen executeQueuedItems
```

<span data-ttu-id="1676b-467">通过 Ngen.exe 执行同步命令，并且不使用本机映像服务。</span><span class="sxs-lookup"><span data-stu-id="1676b-467">Synchronous commands are executed by Ngen.exe and do not use the native image service.</span></span> <span data-ttu-id="1676b-468">本机映像服务运行时，可以使用 Ngen.exe 执行操作。</span><span class="sxs-lookup"><span data-stu-id="1676b-468">You can execute actions using Ngen.exe while the native image service is running.</span></span>

### <a name="service-shutdown"></a><span data-ttu-id="1676b-469">服务关闭</span><span class="sxs-lookup"><span data-stu-id="1676b-469">Service Shutdown</span></span>

<span data-ttu-id="1676b-470">通过执行包括 `/queue` 选项的 Ngen.exe 命令启动后，该服务会在后台运行，直到完成所有操作。</span><span class="sxs-lookup"><span data-stu-id="1676b-470">After being initiated by the execution of an Ngen.exe command that includes the `/queue` option, the service runs in the background until all actions have been completed.</span></span> <span data-ttu-id="1676b-471">该服务将保存其状态，以便必要时能通过多次重新启动继续运行。</span><span class="sxs-lookup"><span data-stu-id="1676b-471">The service saves its state so that it can continue through multiple reboots if necessary.</span></span> <span data-ttu-id="1676b-472">当服务检测到没有更多的排队操作时，它将重置其状态，以便它不会在下次计算机启动时重新启动，随后自动关闭。</span><span class="sxs-lookup"><span data-stu-id="1676b-472">When the service detects that there are no more actions queued, it resets its status so that it will not restart the next time the computer is booted, and then it shuts itself down.</span></span>

### <a name="service-interaction-with-clients"></a><span data-ttu-id="1676b-473">与客户端进行服务交互</span><span class="sxs-lookup"><span data-stu-id="1676b-473">Service Interaction with Clients</span></span>

<span data-ttu-id="1676b-474">在.NET Framework 2.0 版中，与本机映像服务的唯一交互是通过命令行工具 Ngen.exe 进行的。</span><span class="sxs-lookup"><span data-stu-id="1676b-474">In the .NET Framework version 2.0, the only interaction with the native image service is through the command-line tool Ngen.exe.</span></span> <span data-ttu-id="1676b-475">使用安装脚本中的命令行工具对本机映像服务的操作进行排队，并与服务交互。</span><span class="sxs-lookup"><span data-stu-id="1676b-475">Use the command-line tool in installation scripts to queue actions for the native image service and to interact with the service.</span></span>

## <a name="see-also"></a><span data-ttu-id="1676b-476">请参阅</span><span class="sxs-lookup"><span data-stu-id="1676b-476">See also</span></span>

- [<span data-ttu-id="1676b-477">工具</span><span class="sxs-lookup"><span data-stu-id="1676b-477">Tools</span></span>](index.md)
- [<span data-ttu-id="1676b-478">托管执行过程</span><span class="sxs-lookup"><span data-stu-id="1676b-478">Managed Execution Process</span></span>](../../standard/managed-execution-process.md)
- [<span data-ttu-id="1676b-479">运行时如何定位程序集</span><span class="sxs-lookup"><span data-stu-id="1676b-479">How the Runtime Locates Assemblies</span></span>](../deployment/how-the-runtime-locates-assemblies.md)
- [<span data-ttu-id="1676b-480">命令提示</span><span class="sxs-lookup"><span data-stu-id="1676b-480">Command Prompts</span></span>](developer-command-prompt-for-vs.md)
