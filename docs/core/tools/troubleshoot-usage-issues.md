---
title: 排查 .NET Core 工具使用问题
description: 发现运行 .NET Core 工具出现的常见问题及可能的解决方案。
author: kdollard
ms.date: 09/23/2019
ms.openlocfilehash: fc6c520ab57235c78148a6b77717cbd80a989451
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/15/2019
ms.locfileid: "72318287"
---
# <a name="troubleshoot-net-core-tool-usage-issues"></a><span data-ttu-id="31a64-103">排查 .NET Core 工具使用问题</span><span class="sxs-lookup"><span data-stu-id="31a64-103">Troubleshoot .NET Core tool usage issues</span></span>

<span data-ttu-id="31a64-104">在尝试安装或运行 .NET Core 工具（可能是全局工具，也可能是本地工具）时，可能会遇到问题。</span><span class="sxs-lookup"><span data-stu-id="31a64-104">You might come across issues when trying to install or run a .NET Core tool, which can be a global tool or a local tool.</span></span> <span data-ttu-id="31a64-105">本文介绍了常见的根本原因及一些可能的解决方案。</span><span class="sxs-lookup"><span data-stu-id="31a64-105">This article describes the common root causes and some possible solutions.</span></span>

## <a name="installed-net-core-tool-fails-to-run"></a><span data-ttu-id="31a64-106">安装的 .NET Core 工具未能运行</span><span class="sxs-lookup"><span data-stu-id="31a64-106">Installed .NET Core tool fails to run</span></span>

<span data-ttu-id="31a64-107">当 .NET Core 工具未能运行时，你最可能遇到下述问题之一：</span><span class="sxs-lookup"><span data-stu-id="31a64-107">When a .NET Core tool fails to run, most likely you ran into one of the following issues:</span></span>

* <span data-ttu-id="31a64-108">找不到工具的可执行文件。</span><span class="sxs-lookup"><span data-stu-id="31a64-108">The executable file for the tool wasn't found.</span></span>
* <span data-ttu-id="31a64-109">找不到 .NET Core 运行时的正确版本。</span><span class="sxs-lookup"><span data-stu-id="31a64-109">The correct version of the .NET Core runtime wasn't found.</span></span>

### <a name="executable-file-not-found"></a><span data-ttu-id="31a64-110">找不到可执行文件</span><span class="sxs-lookup"><span data-stu-id="31a64-110">Executable file not found</span></span>

<span data-ttu-id="31a64-111">如果找不到可执行文件，则将看到如下所示的消息：</span><span class="sxs-lookup"><span data-stu-id="31a64-111">If the executable file isn't found, you'll see a message similar to the following:</span></span>

```
Could not execute because the specified command or file was not found.
Possible reasons for this include:
  * You misspelled a built-in dotnet command.
  * You intended to execute a .NET Core program, but dotnet-xyz does not exist.
  * You intended to run a global tool, but a dotnet-prefixed executable with this name could not be found on the PATH.
```

<span data-ttu-id="31a64-112">可执行文件的名称决定了调用工具的方式。</span><span class="sxs-lookup"><span data-stu-id="31a64-112">The name of the executable determines how you invoke the tool.</span></span> <span data-ttu-id="31a64-113">相关格式请参见下表：</span><span class="sxs-lookup"><span data-stu-id="31a64-113">The following table describes the format:</span></span>

| <span data-ttu-id="31a64-114">可执行文件名称的格式</span><span class="sxs-lookup"><span data-stu-id="31a64-114">Executable name format</span></span>  | <span data-ttu-id="31a64-115">调用格式</span><span class="sxs-lookup"><span data-stu-id="31a64-115">Invocation format</span></span>   |
|-------------------------|---------------------|
| `dotnet-<toolName>.exe` | `dotnet <toolName>` |
| `<toolName>.exe`        | `<toolName>`        |

* <span data-ttu-id="31a64-116">全局工具</span><span class="sxs-lookup"><span data-stu-id="31a64-116">Global tools</span></span>

    <span data-ttu-id="31a64-117">全局工具可安装在默认目录中，也可安装在特定位置中。</span><span class="sxs-lookup"><span data-stu-id="31a64-117">Global tools can be installed in the default directory or in a specific location.</span></span> <span data-ttu-id="31a64-118">默认目录为：</span><span class="sxs-lookup"><span data-stu-id="31a64-118">The default directories are:</span></span>

    | <span data-ttu-id="31a64-119">(OS)</span><span class="sxs-lookup"><span data-stu-id="31a64-119">OS</span></span>          | <span data-ttu-id="31a64-120">路径</span><span class="sxs-lookup"><span data-stu-id="31a64-120">Path</span></span>                          |
    |-------------|-------------------------------|
    | <span data-ttu-id="31a64-121">Linux/macOS</span><span class="sxs-lookup"><span data-stu-id="31a64-121">Linux/macOS</span></span> | `$HOME/.dotnet/tools`         |
    | <span data-ttu-id="31a64-122">Windows</span><span class="sxs-lookup"><span data-stu-id="31a64-122">Windows</span></span>     | `%USERPROFILE%\.dotnet\tools` |

    <span data-ttu-id="31a64-123">如果要尝试运行全局工具，请检查计算机上的 `PATH` 环境变量是否包含安装该全局工具的路径且可执行文件是否位于该路径中。</span><span class="sxs-lookup"><span data-stu-id="31a64-123">If you're trying to run a global tool, check that the `PATH` environment variable on your machine contains the path where you installed the global tool and that the executable is in that path.</span></span>

    <span data-ttu-id="31a64-124">.NET Core CLI 在首次使用时尝试将默认位置添加到 PATH 环境变量。</span><span class="sxs-lookup"><span data-stu-id="31a64-124">The .NET Core CLI tries to add the default locations to the PATH environment variable on its first usage.</span></span> <span data-ttu-id="31a64-125">但在一些情况下，位置不会自动添加到 PATH，因此你必须编辑 PATH，针对以下情况对其进行配置：</span><span class="sxs-lookup"><span data-stu-id="31a64-125">However, there are a couple of scenarios where the location might not be added to PATH automatically, so you'll have to edit PATH to configure it for the following cases:</span></span>

  * <span data-ttu-id="31a64-126">如果要使用 Linux，并且已使用 .tar.gz 文件（而非 apt-get 或 rpm）安装 .NET Core SDK  。</span><span class="sxs-lookup"><span data-stu-id="31a64-126">If you're using Linux and you've installed the .NET Core SDK using *.tar.gz* files and not apt-get or rpm.</span></span>
  * <span data-ttu-id="31a64-127">如果使用的是 macOS 10.15“Catalina”或更高版本。</span><span class="sxs-lookup"><span data-stu-id="31a64-127">If you're using macOS 10.15 "Catalina" or later versions.</span></span>
  * <span data-ttu-id="31a64-128">如果要使用 macOS 10.14“Mojave”或更低版本，并且已使用 .tar.gz 文件（而非 .pkg）安装 .NET Core SDK   。</span><span class="sxs-lookup"><span data-stu-id="31a64-128">If you're using macOS 10.14 "Mojave" or earlier versions, and you've installed the .NET Core SDK using *.tar.gz* files and not *.pkg*.</span></span>
  * <span data-ttu-id="31a64-129">如果已安装 .NET Core 3.0 SDK，并且已将 `DOTNET_ADD_GLOBAL_TOOLS_TO_PATH` 环境变量设置为 `false`。</span><span class="sxs-lookup"><span data-stu-id="31a64-129">If you've installed the .NET Core 3.0 SDK and you've set the `DOTNET_ADD_GLOBAL_TOOLS_TO_PATH` environment variable to `false`.</span></span>
  * <span data-ttu-id="31a64-130">如果已安装 .NET Core 2.2 SDK 或更低版本，并且已将 `DOTNET_SKIP_FIRST_TIME_EXPERIENCE` 环境变量设置为 `true`。</span><span class="sxs-lookup"><span data-stu-id="31a64-130">If you've installed .NET Core 2.2 SDK or earlier versions, and you've set the `DOTNET_SKIP_FIRST_TIME_EXPERIENCE` environment variable to `true`.</span></span>

  <span data-ttu-id="31a64-131">有关全局工具的详细信息，请参阅 [.NET Core 全局工具概述](global-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="31a64-131">For more information about global tools, see [.NET Core Global Tools overview](global-tools.md).</span></span>

* <span data-ttu-id="31a64-132">本地工具</span><span class="sxs-lookup"><span data-stu-id="31a64-132">Local tools</span></span>

  <span data-ttu-id="31a64-133">如果要尝试运行本地工具，请验证当前目录或其任何父目录中是否存在一个名为 dotnet-tools.json 的清单文件  。</span><span class="sxs-lookup"><span data-stu-id="31a64-133">If you're trying to run a local tool, verify that there's a manifest file called *dotnet-tools.json* in the current directory or any of its parent directories.</span></span> <span data-ttu-id="31a64-134">此文件还可位于项目文件夹层次结构中任意位置的 .config 文件夹下，而不是位于根文件夹中  。</span><span class="sxs-lookup"><span data-stu-id="31a64-134">This file can also live under a folder named *.config* anywhere in the project folder hierarchy, instead of the root folder.</span></span> <span data-ttu-id="31a64-135">如果存在 dotnet-tools.json，请将其打开，检查是否存在你要尝试运行的工具  。</span><span class="sxs-lookup"><span data-stu-id="31a64-135">If *dotnet-tools.json* exists, open it and check for the tool you're trying to run.</span></span> <span data-ttu-id="31a64-136">如果该文件不包含 `"isRoot": true` 的条目，则还要进一步检查文件层次结构中是否存在其他工具清单文件。</span><span class="sxs-lookup"><span data-stu-id="31a64-136">If the file doesn't contain an entry for `"isRoot": true`, then also check further up the file hierarchy for additional tool manifest files.</span></span>

  <span data-ttu-id="31a64-137">如果要尝试运行已通过指定的路径安装的 .NET Core 工具，则需要在使用该工具时包含该路径。</span><span class="sxs-lookup"><span data-stu-id="31a64-137">If you're trying to run a .NET Core tool that was installed with a specified path, you need to include that path when using the tool.</span></span> <span data-ttu-id="31a64-138">下面是使用安装了工具路径的工具的示例：</span><span class="sxs-lookup"><span data-stu-id="31a64-138">An example of using a tool-path installed tool is:</span></span>

  ```console
  ..\<toolDirectory>\dotnet-<toolName>
  ```

### <a name="runtime-not-found"></a><span data-ttu-id="31a64-139">找不到运行时</span><span class="sxs-lookup"><span data-stu-id="31a64-139">Runtime not found</span></span>

<span data-ttu-id="31a64-140">.NET Core 工具是[依赖框架的应用程序](../deploying/index.md#framework-dependent-deployments-fdd)，也就是说它们依赖于计算机上安装的 .NET Core 运行时。</span><span class="sxs-lookup"><span data-stu-id="31a64-140">.NET Core tools are [framework-dependent applications](../deploying/index.md#framework-dependent-deployments-fdd), which means they rely on a .NET Core runtime installed on your machine.</span></span> <span data-ttu-id="31a64-141">如果找不到所需的运行时，则遵循常规的 .NET Core 运行时前滚规则，例如：</span><span class="sxs-lookup"><span data-stu-id="31a64-141">If the expected runtime isn't found, they follow normal .NET Core runtime roll-forward rules such as:</span></span>

* <span data-ttu-id="31a64-142">应用程序前滚至指定的主要版本和次要版本的最高修补程序版本。</span><span class="sxs-lookup"><span data-stu-id="31a64-142">An application rolls forward to the highest patch release of the specified major and minor version.</span></span>
* <span data-ttu-id="31a64-143">如果主要版本号和次要版本号没有匹配的运行时，则使用下一个较高的次要版本。</span><span class="sxs-lookup"><span data-stu-id="31a64-143">If there's no matching runtime with a matching major and minor version number, the next higher minor version is used.</span></span>
* <span data-ttu-id="31a64-144">前滚不会发生在运行时的预览版之间，也不会发生在预览版和发行版之间。</span><span class="sxs-lookup"><span data-stu-id="31a64-144">Roll forward doesn't occur between preview versions of the runtime or between preview versions and release versions.</span></span> <span data-ttu-id="31a64-145">因此，使用预览版创建的 .NET Core 工具必须由作者重新生成和重新发布，再重新安装。</span><span class="sxs-lookup"><span data-stu-id="31a64-145">So, .NET Core tools created using preview versions must be rebuilt and republished by the author and reinstalled.</span></span>

<span data-ttu-id="31a64-146">在下面两种常见场景中，默认不进行前滚：</span><span class="sxs-lookup"><span data-stu-id="31a64-146">Roll-forward won't occur by default in two common scenarios:</span></span>

* <span data-ttu-id="31a64-147">只有运行时的较低版本可用。</span><span class="sxs-lookup"><span data-stu-id="31a64-147">Only lower versions of the runtime are available.</span></span> <span data-ttu-id="31a64-148">前滚仅选择运行时的较高版本。</span><span class="sxs-lookup"><span data-stu-id="31a64-148">Roll-forward only selects later versions of the runtime.</span></span>
* <span data-ttu-id="31a64-149">只有运行时的较高版本可用。</span><span class="sxs-lookup"><span data-stu-id="31a64-149">Only higher major versions of the runtime are available.</span></span> <span data-ttu-id="31a64-150">前滚不跨越主要版本边界。</span><span class="sxs-lookup"><span data-stu-id="31a64-150">Roll-forward doesn't cross major version boundaries.</span></span>

<span data-ttu-id="31a64-151">如果应用程序找不到合适的运行时，则它无法运行并报告错误。</span><span class="sxs-lookup"><span data-stu-id="31a64-151">If an application can't find an appropriate runtime, it fails to run and reports an error.</span></span>

<span data-ttu-id="31a64-152">要查看计算机上安装了哪些 .NET Core 运行时，可使用下述命令之一：</span><span class="sxs-lookup"><span data-stu-id="31a64-152">You can find out which .NET Core runtimes are installed on your machine using one of the following commands:</span></span>

```dotnetcli
dotnet --list-runtimes
dotnet --info
```

<span data-ttu-id="31a64-153">如果你认为此工具应支持你当前安装的运行时版本，可联系工具作者，询问他们是否可更新版本号或实现多目标。</span><span class="sxs-lookup"><span data-stu-id="31a64-153">If you think the tool should support the runtime version you currently have installed, you can contact the tool author and see if they can update the version number or multi-target.</span></span> <span data-ttu-id="31a64-154">在工具作者编译其工具包并使用更新后的版本号将其重新发布到 NuGet 之后，你可更新你的副本。</span><span class="sxs-lookup"><span data-stu-id="31a64-154">Once they've recompiled and republished their tool package to NuGet with an updated version number, you can update your copy.</span></span> <span data-ttu-id="31a64-155">虽然这种情况不会发生，但最快捷的解决方案是安装适合你要尝试运行的工具的运行时版本。</span><span class="sxs-lookup"><span data-stu-id="31a64-155">While that doesn't happen, the quickest solution for you is to install a version of the runtime that would work with the tool you're trying to run.</span></span> <span data-ttu-id="31a64-156">要下载特定的 .NET Core 运行时版本，请访问 [.NET Core 下载页](https://dotnet.microsoft.com/download/dotnet-core)。</span><span class="sxs-lookup"><span data-stu-id="31a64-156">To download a specific .NET Core runtime version, visit the [.NET Core download page](https://dotnet.microsoft.com/download/dotnet-core).</span></span>

<span data-ttu-id="31a64-157">如果将 .NET Core SDK 安装到非默认位置，则需要将环境变量 `DOTNET_ROOT` 设置到包含 `dotnet` 可执行文件的目录。</span><span class="sxs-lookup"><span data-stu-id="31a64-157">If you install the .NET Core SDK to a non-default location, you need to set the environment variable `DOTNET_ROOT` to the directory that contains the `dotnet` executable.</span></span>

## <a name="net-core-tool-installation-fails"></a><span data-ttu-id="31a64-158">.NET Core 工具安装失败</span><span class="sxs-lookup"><span data-stu-id="31a64-158">.NET Core tool installation fails</span></span>

<span data-ttu-id="31a64-159">.NET Core 全局或本地工具安装失败的原因有很多。</span><span class="sxs-lookup"><span data-stu-id="31a64-159">There are a number of reasons the installation of a .NET Core global or local tool may fail.</span></span> <span data-ttu-id="31a64-160">当工具安装失败时，你将看到如下所示的消息：</span><span class="sxs-lookup"><span data-stu-id="31a64-160">When the tool installation fails, you'll see a message similar to following one:</span></span>

```
Tool '{0}' failed to install. This failure may have been caused by:

* You are attempting to install a preview release and did not use the --version option to specify the version.
* A package by this name was found, but it was not a .NET Core tool.
* The required NuGet feed cannot be accessed, perhaps because of an Internet connection problem.
* You mistyped the name of the tool.

For more reasons, including package naming enforcement, visit https://aka.ms/failure-installing-tool
```

<span data-ttu-id="31a64-161">为帮助诊断这些失败情况，会随同之前的消息直接向用户显示 NuGet 消息。</span><span class="sxs-lookup"><span data-stu-id="31a64-161">To help diagnose these failures, NuGet messages are shown directly to the user, along with the previous message.</span></span> <span data-ttu-id="31a64-162">NuGet 消息可帮助你确定问题。</span><span class="sxs-lookup"><span data-stu-id="31a64-162">The NuGet message may help you identify the problem.</span></span>

### <a name="package-naming-enforcement"></a><span data-ttu-id="31a64-163">包命名强制</span><span class="sxs-lookup"><span data-stu-id="31a64-163">Package naming enforcement</span></span>

<span data-ttu-id="31a64-164">Microsoft 针对工具的包 ID 更改了相关指导，导致没法用预测出的名称找到很多工具。</span><span class="sxs-lookup"><span data-stu-id="31a64-164">Microsoft has changed its guidance on the Package ID for tools, resulting in a number of tools not being found with the predicted name.</span></span> <span data-ttu-id="31a64-165">新的指导是所有 Microsoft 工具均附上“Microsoft”这一前缀。</span><span class="sxs-lookup"><span data-stu-id="31a64-165">The new guidance is that all Microsoft tools be prefixed with "Microsoft."</span></span> <span data-ttu-id="31a64-166">此前缀已预留，仅用于使用 Microsoft 授权证书签名的包。</span><span class="sxs-lookup"><span data-stu-id="31a64-166">This prefix is reserved and can only be used for packages signed with a Microsoft authorized certificate.</span></span>

<span data-ttu-id="31a64-167">在过渡期间，一些 Microsoft 工具将采用包 ID 的旧格式，而另外一些将采用新格式：</span><span class="sxs-lookup"><span data-stu-id="31a64-167">During the transition, some Microsoft tools will have the old form of the package ID, while others will have the new form:</span></span>

```dotnetcli
dotnet tool install -g Microsoft.<toolName>
dotnet tool install -g <toolName>
```

<span data-ttu-id="31a64-168">更新包 ID 后，你将需要更改到新的包 ID 以获取最新更新。</span><span class="sxs-lookup"><span data-stu-id="31a64-168">As package IDs are updated, you'll need to change to the new package ID to get the latest updates.</span></span> <span data-ttu-id="31a64-169">带简化工具名称的包将遭到弃用。</span><span class="sxs-lookup"><span data-stu-id="31a64-169">Packages with the simplified tool name will be deprecated.</span></span>

### <a name="preview-releases"></a><span data-ttu-id="31a64-170">预览版本</span><span class="sxs-lookup"><span data-stu-id="31a64-170">Preview releases</span></span>

* <span data-ttu-id="31a64-171">你正在尝试安装预览版本，但未使用 `--version` 选项来指定该版本。</span><span class="sxs-lookup"><span data-stu-id="31a64-171">You're attempting to install a preview release and didn't use the `--version` option to specify the version.</span></span>

<span data-ttu-id="31a64-172">必须用名称的一部分指定处于预览版状态的 .NET Core 工具，这样才能指示它们现为预览版。</span><span class="sxs-lookup"><span data-stu-id="31a64-172">.NET Core tools that are in preview must be specified with a portion of the name to indicate that they are in preview.</span></span> <span data-ttu-id="31a64-173">不需要包含整个预览版。</span><span class="sxs-lookup"><span data-stu-id="31a64-173">You don't need to include the entire preview.</span></span> <span data-ttu-id="31a64-174">假定版本号都采用预期的格式，则你可使用与下例类似的内容：</span><span class="sxs-lookup"><span data-stu-id="31a64-174">Assuming the version numbers are in the expected format, you can use something like the following example:</span></span>

```dotnetcli
dotnet tool install -g --version 1.1.0-pre <toolName>
```

> [!NOTE]
> <span data-ttu-id="31a64-175">.NET Core CLI 正计划在未来版本中添加一个 `--preview` 开关来简化此操作。</span><span class="sxs-lookup"><span data-stu-id="31a64-175">The .NET Core CLI team is planning to add a `--preview` switch in a future release to make this easier.</span></span>

### <a name="package-isnt-a-net-core-tool"></a><span data-ttu-id="31a64-176">包不是 .NET Core 工具</span><span class="sxs-lookup"><span data-stu-id="31a64-176">Package isn't a .NET Core tool</span></span>

* <span data-ttu-id="31a64-177">已按此名称找到 NuGet 包，但它不是 .NET Core 工具。</span><span class="sxs-lookup"><span data-stu-id="31a64-177">A NuGet package by this name was found, but it wasn't a .NET Core tool.</span></span>

<span data-ttu-id="31a64-178">如果尝试安装是常规 NuGet 包（而非 .NET Core 工具）的 NuGet 包，你将看到如下所示的错误：</span><span class="sxs-lookup"><span data-stu-id="31a64-178">If you try to install a NuGet package that is a regular NuGet package and not a .NET Core tool, you'll see an error similar to the following:</span></span>

> <span data-ttu-id="31a64-179">NU1212：`<ToolName>` 的项目包组合无效。</span><span class="sxs-lookup"><span data-stu-id="31a64-179">NU1212: Invalid project-package combination for `<ToolName>`.</span></span> <span data-ttu-id="31a64-180">DotnetToolReference 项目类型仅可包含 DotnetTool 类型的引用。</span><span class="sxs-lookup"><span data-stu-id="31a64-180">DotnetToolReference project style can only contain references of the DotnetTool type.</span></span>

### <a name="nuget-feed-cant-be-accessed"></a><span data-ttu-id="31a64-181">无法访问 NuGet 源</span><span class="sxs-lookup"><span data-stu-id="31a64-181">NuGet feed can't be accessed</span></span>

* <span data-ttu-id="31a64-182">无法访问必需的 NuGet 源，这可能是由 Internet 连接问题造成的。</span><span class="sxs-lookup"><span data-stu-id="31a64-182">The required NuGet feed can't be accessed, perhaps because of an Internet connection problem.</span></span>

<span data-ttu-id="31a64-183">需要访问包含工具包的 NuGet 源才能安装工具。</span><span class="sxs-lookup"><span data-stu-id="31a64-183">Tool installation requires access to the NuGet feed that contains the tool package.</span></span> <span data-ttu-id="31a64-184">如果源不可用，则安装将失败。</span><span class="sxs-lookup"><span data-stu-id="31a64-184">It fails if the feed isn't available.</span></span> <span data-ttu-id="31a64-185">可使用 `nuget.config` 修改源、请求特定的 `nuget.config` 文件，也可使用 `--add-source` 开关指定其他源。</span><span class="sxs-lookup"><span data-stu-id="31a64-185">You can alter feeds with `nuget.config`, request a specific `nuget.config` file, or specify additional feeds with the `--add-source` switch.</span></span> <span data-ttu-id="31a64-186">默认情况下，对于无法连接的任何源，NuGet 都将引发错误。</span><span class="sxs-lookup"><span data-stu-id="31a64-186">By default, NuGet throws an error for any feed that can't connect.</span></span> <span data-ttu-id="31a64-187">标志 `--ignore-failed-sources` 可跳过这些不可访问的源。</span><span class="sxs-lookup"><span data-stu-id="31a64-187">The flag `--ignore-failed-sources` can skip these non-reachable sources.</span></span>

### <a name="package-id-incorrect"></a><span data-ttu-id="31a64-188">包 ID 错误</span><span class="sxs-lookup"><span data-stu-id="31a64-188">Package ID incorrect</span></span>

* <span data-ttu-id="31a64-189">工具的名称拼写错误。</span><span class="sxs-lookup"><span data-stu-id="31a64-189">You mistyped the name of the tool.</span></span>

<span data-ttu-id="31a64-190">常见的失败原因是工具名称不正确。</span><span class="sxs-lookup"><span data-stu-id="31a64-190">A common reason for failure is that the tool name isn't correct.</span></span> <span data-ttu-id="31a64-191">原因可能是拼写错误，或者工具已移动或已被弃用。</span><span class="sxs-lookup"><span data-stu-id="31a64-191">This can happen because of mistyping, or because the tool has moved or been deprecated.</span></span> <span data-ttu-id="31a64-192">对于 NuGet.org 上的工具，确保名称正确的一种方式是在 NuGet.org 处搜索该工具并复制安装命令。</span><span class="sxs-lookup"><span data-stu-id="31a64-192">For tools on NuGet.org, one way to ensure you have the name correct is to search for the tool at NuGet.org and copy the installation command.</span></span>

## <a name="see-also"></a><span data-ttu-id="31a64-193">请参阅</span><span class="sxs-lookup"><span data-stu-id="31a64-193">See also</span></span>

* [<span data-ttu-id="31a64-194">.NET Core 全局工具概述</span><span class="sxs-lookup"><span data-stu-id="31a64-194">.NET Core Global Tools overview</span></span>](global-tools.md)
