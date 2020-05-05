---
title: dotnet 命令
description: 了解 dotnet 命令（.NET Core CLI 的通用驱动程序）及其用法。
ms.date: 02/13/2020
ms.openlocfilehash: 6a08297499d955db44e342dc82fed25b7b9b8171
ms.sourcegitcommit: 465547886a1224a5435c3ac349c805e39ce77706
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/21/2020
ms.locfileid: "81739068"
---
# <a name="dotnet-command"></a><span data-ttu-id="6861c-103">dotnet 命令</span><span class="sxs-lookup"><span data-stu-id="6861c-103">dotnet command</span></span>

<span data-ttu-id="6861c-104"> 本文适用于： ✔️ .NET Core 2.1 SDK 及更高版本</span><span class="sxs-lookup"><span data-stu-id="6861c-104">**This article applies to:** ✔️ .NET Core 2.1 SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="6861c-105">“属性”</span><span class="sxs-lookup"><span data-stu-id="6861c-105">Name</span></span>

<span data-ttu-id="6861c-106">`dotnet` - .NET Core CLI 的通用驱动程序。</span><span class="sxs-lookup"><span data-stu-id="6861c-106">`dotnet` - The generic driver for the .NET Core CLI.</span></span>

## <a name="synopsis"></a><span data-ttu-id="6861c-107">摘要</span><span class="sxs-lookup"><span data-stu-id="6861c-107">Synopsis</span></span>

<span data-ttu-id="6861c-108">获取有关可用命令和环境的信息：</span><span class="sxs-lookup"><span data-stu-id="6861c-108">To get information about the available commands and the environment:</span></span>

```dotnetcli
dotnet [--version] [--info] [--list-runtimes] [--list-sdks]

dotnet -h|--help
```

<span data-ttu-id="6861c-109">运行命令（需要 SDK 安装）：</span><span class="sxs-lookup"><span data-stu-id="6861c-109">To run a command (requires SDK installation):</span></span>

```dotnetcli
dotnet <COMMAND> [-d|--diagnostics] [-h|--help] [--verbosity <LEVEL>]
    [command-options] [arguments]
```

<span data-ttu-id="6861c-110">运行应用程序：</span><span class="sxs-lookup"><span data-stu-id="6861c-110">To run an application:</span></span>

```dotnetcli
dotnet [--additionalprobingpath <PATH>] [--additional-deps <PATH>]
    [--fx-version <VERSION>]  [--roll-forward <SETTING>]
    <PATH_TO_APPLICATION> [arguments]

dotnet exec [--additionalprobingpath] [--additional-deps <PATH>]
    [--fx-version <VERSION>]  [--roll-forward <SETTING>]
    <PATH_TO_APPLICATION> [arguments]
```

<span data-ttu-id="6861c-111">`--roll-forward` 自 .NET Core 3.x 起可用。</span><span class="sxs-lookup"><span data-stu-id="6861c-111">`--roll-forward` is available since .NET Core 3.x.</span></span> <span data-ttu-id="6861c-112">使用 .NET Core 2.x 的 `--roll-forward-on-no-candidate-fx`。</span><span class="sxs-lookup"><span data-stu-id="6861c-112">Use `--roll-forward-on-no-candidate-fx` for .NET Core 2.x.</span></span>

## <a name="description"></a><span data-ttu-id="6861c-113">描述</span><span class="sxs-lookup"><span data-stu-id="6861c-113">Description</span></span>

<span data-ttu-id="6861c-114">`dotnet` 命令有两个函数：</span><span class="sxs-lookup"><span data-stu-id="6861c-114">The `dotnet` command has two functions:</span></span>

- <span data-ttu-id="6861c-115">它提供了用于处理 .NET Core 项目的命令。</span><span class="sxs-lookup"><span data-stu-id="6861c-115">It provides commands for working with .NET Core projects.</span></span>

  <span data-ttu-id="6861c-116">例如，[`dotnet build`](dotnet-build.md) 生成项目。</span><span class="sxs-lookup"><span data-stu-id="6861c-116">For example, [`dotnet build`](dotnet-build.md) builds a project.</span></span> <span data-ttu-id="6861c-117">每个命令定义自己的选项和参数。</span><span class="sxs-lookup"><span data-stu-id="6861c-117">Each command defines its own options and arguments.</span></span> <span data-ttu-id="6861c-118">所有命令都支持 `--help` 选项，用于打印有关如何使用命令的简短文档。</span><span class="sxs-lookup"><span data-stu-id="6861c-118">All commands support the `--help` option for printing out brief documentation about how to use the command.</span></span>

- <span data-ttu-id="6861c-119">它运行 .NET Core 应用程序。</span><span class="sxs-lookup"><span data-stu-id="6861c-119">It runs .NET Core applications.</span></span>

  <span data-ttu-id="6861c-120">指定应用程序 `.dll` 文件的路径以运行应用程序。</span><span class="sxs-lookup"><span data-stu-id="6861c-120">You specify the path to an application `.dll` file to run the application.</span></span>  <span data-ttu-id="6861c-121">运行应用程序即意味着找到并执行入口点，对于控制台应用，入口点是 `Main` 方法。</span><span class="sxs-lookup"><span data-stu-id="6861c-121">To run the application means to find and execute the entry point, which in the case of console apps is the `Main` method.</span></span> <span data-ttu-id="6861c-122">例如，`dotnet myapp.dll` 运行 `myapp` 应用程序。</span><span class="sxs-lookup"><span data-stu-id="6861c-122">For example, `dotnet myapp.dll` runs the `myapp` application.</span></span> <span data-ttu-id="6861c-123">要了解部署选项，请参阅 [.NET Core 应用程序部署](../deploying/index.md)。</span><span class="sxs-lookup"><span data-stu-id="6861c-123">See [.NET Core application deployment](../deploying/index.md) to learn about deployment options.</span></span>

## <a name="options"></a><span data-ttu-id="6861c-124">选项</span><span class="sxs-lookup"><span data-stu-id="6861c-124">Options</span></span>

<span data-ttu-id="6861c-125">`dotnet` 本身有不同的选项，可用于运行命令和运行应用程序。</span><span class="sxs-lookup"><span data-stu-id="6861c-125">Different options are available for `dotnet` by itself, for running a command, and for running an application.</span></span>

### <a name="options-for-dotnet-by-itself"></a><span data-ttu-id="6861c-126">dotnet 本身的选项</span><span class="sxs-lookup"><span data-stu-id="6861c-126">Options for dotnet by itself</span></span>

<span data-ttu-id="6861c-127">以下是 `dotnet` 本身的选项。</span><span class="sxs-lookup"><span data-stu-id="6861c-127">The following options are for `dotnet` by itself.</span></span> <span data-ttu-id="6861c-128">例如 `dotnet --info`。</span><span class="sxs-lookup"><span data-stu-id="6861c-128">For example, `dotnet --info`.</span></span> <span data-ttu-id="6861c-129">这些选项打印出有关环境的信息。</span><span class="sxs-lookup"><span data-stu-id="6861c-129">They print out information about the environment.</span></span>

- **`--info`**

  <span data-ttu-id="6861c-130">打印出有关 .NET Core 安装和计算机环境（如当前操作系统）的详细信息，并提交 .NET Core 版本的 SHA。</span><span class="sxs-lookup"><span data-stu-id="6861c-130">Prints out detailed information about a .NET Core installation and the machine environment, such as the current operating system, and commit SHA of the .NET Core version.</span></span>

- **`--version`**

  <span data-ttu-id="6861c-131">打印使用中的 .NET Core SDK 版本。</span><span class="sxs-lookup"><span data-stu-id="6861c-131">Prints out the version of the .NET Core SDK in use.</span></span>

- **`--list-runtimes`**

  <span data-ttu-id="6861c-132">打印已安装的 .NET Core 运行时的列表。</span><span class="sxs-lookup"><span data-stu-id="6861c-132">Prints out a list of the installed .NET Core runtimes.</span></span> <span data-ttu-id="6861c-133">x86 版本的 SDK 只列出 x86 运行时，而 x64 版本的 SDK 只列出 x64 运行时。</span><span class="sxs-lookup"><span data-stu-id="6861c-133">An x86 version of the SDK lists only x86 runtimes, and an x64 version of the SDK lists only x64 runtimes.</span></span>

- **`--list-sdks`**

  <span data-ttu-id="6861c-134">打印已安装的 .NET Core SDK 的列表。</span><span class="sxs-lookup"><span data-stu-id="6861c-134">Prints out a list of the installed .NET Core SDKs.</span></span>

- **`-h|--help`**

  <span data-ttu-id="6861c-135">打印可用命令列表。</span><span class="sxs-lookup"><span data-stu-id="6861c-135">Prints out a list of available commands.</span></span>

### <a name="sdk-options-for-running-a-command"></a><span data-ttu-id="6861c-136">用于运行命令的 SDK 选项</span><span class="sxs-lookup"><span data-stu-id="6861c-136">SDK options for running a command</span></span>

<span data-ttu-id="6861c-137">以下选项适用于使用命令的 `dotnet`。</span><span class="sxs-lookup"><span data-stu-id="6861c-137">The following options are for `dotnet` with a command.</span></span> <span data-ttu-id="6861c-138">例如 `dotnet build --help`。</span><span class="sxs-lookup"><span data-stu-id="6861c-138">For example, `dotnet build --help`.</span></span>

- **`-d|--diagnostics`**

  <span data-ttu-id="6861c-139">启用诊断输出。</span><span class="sxs-lookup"><span data-stu-id="6861c-139">Enables diagnostic output.</span></span>

- **`-v|--verbosity <LEVEL>`**

  <span data-ttu-id="6861c-140">设置命令的详细级别。</span><span class="sxs-lookup"><span data-stu-id="6861c-140">Sets the verbosity level of the command.</span></span> <span data-ttu-id="6861c-141">允许使用的值为 `q[uiet]`、`m[inimal]`、`n[ormal]`、`d[etailed]` 和 `diag[nostic]`。</span><span class="sxs-lookup"><span data-stu-id="6861c-141">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="6861c-142">并非在每个命令中均受支持。</span><span class="sxs-lookup"><span data-stu-id="6861c-142">Not supported in every command.</span></span> <span data-ttu-id="6861c-143">请参阅特定的命令页，确定此选项是否可用。</span><span class="sxs-lookup"><span data-stu-id="6861c-143">See specific command page to determine if this option is available.</span></span>

- **`-h|--help`**

  <span data-ttu-id="6861c-144">打印出给定命令的文档，如 `dotnet build --help`。</span><span class="sxs-lookup"><span data-stu-id="6861c-144">Prints out documentation for a given command, such as `dotnet build --help`.</span></span>

- **`command options`**

  <span data-ttu-id="6861c-145">每个命令定义特定于该命令的选项。</span><span class="sxs-lookup"><span data-stu-id="6861c-145">Each command defines options specific to that command.</span></span> <span data-ttu-id="6861c-146">有关可用选项的列表，请参阅特定命令页。</span><span class="sxs-lookup"><span data-stu-id="6861c-146">See specific command page for a list of available options.</span></span>

### <a name="runtime-options"></a><span data-ttu-id="6861c-147">运行时选项</span><span class="sxs-lookup"><span data-stu-id="6861c-147">Runtime options</span></span>

<span data-ttu-id="6861c-148">`dotnet` 运行应用程序时，可以使用以下选项。</span><span class="sxs-lookup"><span data-stu-id="6861c-148">The following options are available when `dotnet` runs an application.</span></span> <span data-ttu-id="6861c-149">例如 `dotnet myapp.dll --fx-version 3.1.1`。</span><span class="sxs-lookup"><span data-stu-id="6861c-149">For example, `dotnet myapp.dll --fx-version 3.1.1`.</span></span>

- **`--additionalprobingpath <PATH>`**

  <span data-ttu-id="6861c-150">包含要进行探测的探测策略和程序集的路径。</span><span class="sxs-lookup"><span data-stu-id="6861c-150">Path containing probing policy and assemblies to probe.</span></span>

- **`--additional-deps <PATH>`**

  <span data-ttu-id="6861c-151">附加 .deps.json 文件的路径  。</span><span class="sxs-lookup"><span data-stu-id="6861c-151">Path to an additional *.deps.json* file.</span></span> <span data-ttu-id="6861c-152">deps.json 文件包含依赖项、编译依赖项和用于解决程序集冲突的版本信息列表  。</span><span class="sxs-lookup"><span data-stu-id="6861c-152">A *deps.json* file contains a list of dependencies, compilation dependencies, and version information used to address assembly conflicts.</span></span> <span data-ttu-id="6861c-153">有关详细信息，请参阅 GitHub 上的[运行时配置文件](https://github.com/dotnet/cli/blob/master/Documentation/specs/runtime-configuration-file.md)。</span><span class="sxs-lookup"><span data-stu-id="6861c-153">For more information, see [Runtime Configuration Files](https://github.com/dotnet/cli/blob/master/Documentation/specs/runtime-configuration-file.md) on GitHub.</span></span>

- **`--fx-version <VERSION>`**

  <span data-ttu-id="6861c-154">用于运行应用程序的 .NET Core 运行时版本。</span><span class="sxs-lookup"><span data-stu-id="6861c-154">Version of the .NET Core runtime to use to run the application.</span></span>

- **`--runtimeconfig`**

  <span data-ttu-id="6861c-155">runtimeconfig.template.json 文件的路径  。</span><span class="sxs-lookup"><span data-stu-id="6861c-155">Path to a *runtimeconfig.json* file.</span></span> <span data-ttu-id="6861c-156">runtimeconfig.template.json 文件是包含运行时设置的配置文件  。</span><span class="sxs-lookup"><span data-stu-id="6861c-156">A *runtimeconfig.json* file is a configuration file that contains run-time settings.</span></span> <span data-ttu-id="6861c-157">有关详细信息，请参阅 [.NET Core 运行时配置设置](../run-time-config/index.md#runtimeconfigjson)。</span><span class="sxs-lookup"><span data-stu-id="6861c-157">For more information, see [.NET Core run-time configuration settings](../run-time-config/index.md#runtimeconfigjson).</span></span>

- <span data-ttu-id="6861c-158">`--roll-forward-on-no-candidate-fx <N>` 在 .NET Core 2.x SDK 中可用   。</span><span class="sxs-lookup"><span data-stu-id="6861c-158">**`--roll-forward-on-no-candidate-fx <N>`** **Available in .NET Core 2.x SDK.**</span></span>

  <span data-ttu-id="6861c-159">所需的共享框架不可用时，请定义行为。</span><span class="sxs-lookup"><span data-stu-id="6861c-159">Defines behavior when the required shared framework is not available.</span></span> <span data-ttu-id="6861c-160">`N` 可以是：</span><span class="sxs-lookup"><span data-stu-id="6861c-160">`N` can be:</span></span>

  - <span data-ttu-id="6861c-161">`0` - 禁用次要版本前滚。</span><span class="sxs-lookup"><span data-stu-id="6861c-161">`0` - Disable even minor version roll forward.</span></span>
  - <span data-ttu-id="6861c-162">`1` - 前滚次要版本，但不前滚主版本。</span><span class="sxs-lookup"><span data-stu-id="6861c-162">`1` - Roll forward on minor version, but not on major version.</span></span> <span data-ttu-id="6861c-163">这是默认行为。</span><span class="sxs-lookup"><span data-stu-id="6861c-163">This is the default behavior.</span></span>
  - <span data-ttu-id="6861c-164">`2` - 前滚次要和主版本。</span><span class="sxs-lookup"><span data-stu-id="6861c-164">`2` - Roll forward on minor and major versions.</span></span>

   <span data-ttu-id="6861c-165">有关详细信息，请参阅[前滚](../whats-new/dotnet-core-2-1.md#roll-forward)。</span><span class="sxs-lookup"><span data-stu-id="6861c-165">For more information, see [Roll forward](../whats-new/dotnet-core-2-1.md#roll-forward).</span></span>

- <span data-ttu-id="6861c-166">`--roll-forward <SETTING>` 自 .NET Core SDK 3.0 起可用   。</span><span class="sxs-lookup"><span data-stu-id="6861c-166">**`--roll-forward <SETTING>`** **Available starting with .NET Core SDK 3.0.**</span></span>

  <span data-ttu-id="6861c-167">控制将前滚操作应用于应用的方式。</span><span class="sxs-lookup"><span data-stu-id="6861c-167">Controls how roll forward is applied to the app.</span></span> <span data-ttu-id="6861c-168">`SETTING` 可以为下列值之一。</span><span class="sxs-lookup"><span data-stu-id="6861c-168">The `SETTING` can be one of the following values.</span></span> <span data-ttu-id="6861c-169">如果未指定，则 `Minor` 为默认类型。</span><span class="sxs-lookup"><span data-stu-id="6861c-169">If not specified, `Minor` is the default.</span></span>

  - <span data-ttu-id="6861c-170">`LatestPatch` - 前滚到最高补丁版本。</span><span class="sxs-lookup"><span data-stu-id="6861c-170">`LatestPatch` - Roll forward to the highest patch version.</span></span> <span data-ttu-id="6861c-171">这会禁用次要版本前滚。</span><span class="sxs-lookup"><span data-stu-id="6861c-171">This disables minor version roll forward.</span></span>
  - <span data-ttu-id="6861c-172">`Minor` - 如果缺少所请求的次要版本，则前滚到最低的较高次要版本。</span><span class="sxs-lookup"><span data-stu-id="6861c-172">`Minor` - Roll forward to the lowest higher minor version, if requested minor version is missing.</span></span> <span data-ttu-id="6861c-173">如果存在所请求的次要版本，则使用 LatestPatch 策略。</span><span class="sxs-lookup"><span data-stu-id="6861c-173">If the requested minor version is present, then the LatestPatch policy is used.</span></span>
  - <span data-ttu-id="6861c-174">`Major` - 如果缺少所请求的主要版本，则前滚到最低的较高主要版本和最低的次要版本。</span><span class="sxs-lookup"><span data-stu-id="6861c-174">`Major` - Roll forward to lowest higher major version, and lowest minor version, if requested major version is missing.</span></span> <span data-ttu-id="6861c-175">如果存在所请求的主要版本，则使用 Minor 策略。</span><span class="sxs-lookup"><span data-stu-id="6861c-175">If the requested major version is present, then the Minor policy is used.</span></span>
  - <span data-ttu-id="6861c-176">`LatestMinor` - 即使存在所请求的次要版本，仍前滚到最高次要版本。</span><span class="sxs-lookup"><span data-stu-id="6861c-176">`LatestMinor` - Roll forward to highest minor version, even if requested minor version is present.</span></span> <span data-ttu-id="6861c-177">适用于组件托管方案。</span><span class="sxs-lookup"><span data-stu-id="6861c-177">Intended for component hosting scenarios.</span></span>
  - <span data-ttu-id="6861c-178">`LatestMajor` - 即使存在所请求的主要版本，仍前滚到最高主要版本和最高次要版本。</span><span class="sxs-lookup"><span data-stu-id="6861c-178">`LatestMajor` - Roll forward to highest major and highest minor version, even if requested major is present.</span></span> <span data-ttu-id="6861c-179">适用于组件托管方案。</span><span class="sxs-lookup"><span data-stu-id="6861c-179">Intended for component hosting scenarios.</span></span>
  - <span data-ttu-id="6861c-180">`Disable` - 不前滚。</span><span class="sxs-lookup"><span data-stu-id="6861c-180">`Disable` - Don't roll forward.</span></span> <span data-ttu-id="6861c-181">仅绑定到指定的版本。</span><span class="sxs-lookup"><span data-stu-id="6861c-181">Only bind to specified version.</span></span> <span data-ttu-id="6861c-182">建议不要将此策略用于一般用途，因为它会禁用前滚到最新补丁的功能。</span><span class="sxs-lookup"><span data-stu-id="6861c-182">This policy isn't recommended for general use because it disables the ability to roll forward to the latest patches.</span></span> <span data-ttu-id="6861c-183">该值仅建议用于测试。</span><span class="sxs-lookup"><span data-stu-id="6861c-183">This value is only recommended for testing.</span></span>

<span data-ttu-id="6861c-184">除 `Disable` 外，所有设置都将使用可用的最高补丁版本。</span><span class="sxs-lookup"><span data-stu-id="6861c-184">With the exception of `Disable`, all settings will use the highest available patch version.</span></span>

<span data-ttu-id="6861c-185">前滚行为还可以在项目文件属性、运行时配置文件属性和环境变量中进行配置。</span><span class="sxs-lookup"><span data-stu-id="6861c-185">Roll forward behavior can also be configured in a project file property, a run-time configuration file property, and an environment variable.</span></span> <span data-ttu-id="6861c-186">有关详细信息，请参阅[主版本运行时前滚](../whats-new/dotnet-core-3-0.md#major-version-runtime-roll-forward)。</span><span class="sxs-lookup"><span data-stu-id="6861c-186">For more information, see [Major-version runtime roll forward](../whats-new/dotnet-core-3-0.md#major-version-runtime-roll-forward).</span></span>

## <a name="dotnet-commands"></a><span data-ttu-id="6861c-187">dotnet 命令</span><span class="sxs-lookup"><span data-stu-id="6861c-187">dotnet commands</span></span>

### <a name="general"></a><span data-ttu-id="6861c-188">常规</span><span class="sxs-lookup"><span data-stu-id="6861c-188">General</span></span>

| <span data-ttu-id="6861c-189">命令</span><span class="sxs-lookup"><span data-stu-id="6861c-189">Command</span></span>                                       | <span data-ttu-id="6861c-190">函数</span><span class="sxs-lookup"><span data-stu-id="6861c-190">Function</span></span>                                                            |
| --------------------------------------------- | ------------------------------------------------------------------- |
| [<span data-ttu-id="6861c-191">dotnet build</span><span class="sxs-lookup"><span data-stu-id="6861c-191">dotnet build</span></span>](dotnet-build.md)               | <span data-ttu-id="6861c-192">生成 .NET Core 应用程序。</span><span class="sxs-lookup"><span data-stu-id="6861c-192">Builds a .NET Core application.</span></span>                                     |
| [<span data-ttu-id="6861c-193">dotnet build-server</span><span class="sxs-lookup"><span data-stu-id="6861c-193">dotnet build-server</span></span>](dotnet-build-server.md) | <span data-ttu-id="6861c-194">与通过生成启动的服务器进行交互。</span><span class="sxs-lookup"><span data-stu-id="6861c-194">Interacts with servers started by a build.</span></span>                          |
| [<span data-ttu-id="6861c-195">dotnet clean</span><span class="sxs-lookup"><span data-stu-id="6861c-195">dotnet clean</span></span>](dotnet-clean.md)               | <span data-ttu-id="6861c-196">清除生成输出。</span><span class="sxs-lookup"><span data-stu-id="6861c-196">Clean build outputs.</span></span>                                                |
| [<span data-ttu-id="6861c-197">dotnet help</span><span class="sxs-lookup"><span data-stu-id="6861c-197">dotnet help</span></span>](dotnet-help.md)                 | <span data-ttu-id="6861c-198">显示命令更详细的在线文档。</span><span class="sxs-lookup"><span data-stu-id="6861c-198">Shows more detailed documentation online for the command.</span></span>           |
| [<span data-ttu-id="6861c-199">dotnet migrate</span><span class="sxs-lookup"><span data-stu-id="6861c-199">dotnet migrate</span></span>](dotnet-migrate.md)           | <span data-ttu-id="6861c-200">将有效的预览版 2 项目迁移到 .NET Core SDK 1.0 项目。</span><span class="sxs-lookup"><span data-stu-id="6861c-200">Migrates a valid Preview 2 project to a .NET Core SDK 1.0 project.</span></span>  |
| [<span data-ttu-id="6861c-201">dotnet msbuild</span><span class="sxs-lookup"><span data-stu-id="6861c-201">dotnet msbuild</span></span>](dotnet-msbuild.md)           | <span data-ttu-id="6861c-202">提供对 MSBuild 命令行的访问权限。</span><span class="sxs-lookup"><span data-stu-id="6861c-202">Provides access to the MSBuild command line.</span></span>                        |
| [<span data-ttu-id="6861c-203">dotnet new</span><span class="sxs-lookup"><span data-stu-id="6861c-203">dotnet new</span></span>](dotnet-new.md)                   | <span data-ttu-id="6861c-204">为给定的模板初始化 C# 或 F# 项目。</span><span class="sxs-lookup"><span data-stu-id="6861c-204">Initializes a C# or F# project for a given template.</span></span>                |
| [<span data-ttu-id="6861c-205">dotnet pack</span><span class="sxs-lookup"><span data-stu-id="6861c-205">dotnet pack</span></span>](dotnet-pack.md)                 | <span data-ttu-id="6861c-206">创建代码的 NuGet 包。</span><span class="sxs-lookup"><span data-stu-id="6861c-206">Creates a NuGet package of your code.</span></span>                               |
| [<span data-ttu-id="6861c-207">dotnet publish</span><span class="sxs-lookup"><span data-stu-id="6861c-207">dotnet publish</span></span>](dotnet-publish.md)           | <span data-ttu-id="6861c-208">发布 .NET 依赖于框架或独立应用程序。</span><span class="sxs-lookup"><span data-stu-id="6861c-208">Publishes a .NET framework-dependent or self-contained application.</span></span> |
| [<span data-ttu-id="6861c-209">dotnet restore</span><span class="sxs-lookup"><span data-stu-id="6861c-209">dotnet restore</span></span>](dotnet-restore.md)           | <span data-ttu-id="6861c-210">还原给定应用程序的依赖项。</span><span class="sxs-lookup"><span data-stu-id="6861c-210">Restores the dependencies for a given application.</span></span>                  |
| [<span data-ttu-id="6861c-211">dotnet run</span><span class="sxs-lookup"><span data-stu-id="6861c-211">dotnet run</span></span>](dotnet-run.md)                   | <span data-ttu-id="6861c-212">从源运行应用程序。</span><span class="sxs-lookup"><span data-stu-id="6861c-212">Runs the application from source.</span></span>                                   |
| [<span data-ttu-id="6861c-213">dotnet sln</span><span class="sxs-lookup"><span data-stu-id="6861c-213">dotnet sln</span></span>](dotnet-sln.md)                   | <span data-ttu-id="6861c-214">用于添加、删除和列出解决方案文件中项目的选项。</span><span class="sxs-lookup"><span data-stu-id="6861c-214">Options to add, remove, and list projects in a solution file.</span></span>       |
| [<span data-ttu-id="6861c-215">dotnet store</span><span class="sxs-lookup"><span data-stu-id="6861c-215">dotnet store</span></span>](dotnet-store.md)               | <span data-ttu-id="6861c-216">将程序集存储到运行时包存储区。</span><span class="sxs-lookup"><span data-stu-id="6861c-216">Stores assemblies in the runtime package store.</span></span>                     |
| [<span data-ttu-id="6861c-217">dotnet test</span><span class="sxs-lookup"><span data-stu-id="6861c-217">dotnet test</span></span>](dotnet-test.md)                 | <span data-ttu-id="6861c-218">使用测试运行程序运行测试。</span><span class="sxs-lookup"><span data-stu-id="6861c-218">Runs tests using a test runner.</span></span>                                     |

### <a name="project-references"></a><span data-ttu-id="6861c-219">项目引用</span><span class="sxs-lookup"><span data-stu-id="6861c-219">Project references</span></span>

<span data-ttu-id="6861c-220">命令</span><span class="sxs-lookup"><span data-stu-id="6861c-220">Command</span></span> | <span data-ttu-id="6861c-221">函数</span><span class="sxs-lookup"><span data-stu-id="6861c-221">Function</span></span>
--- | ---
[<span data-ttu-id="6861c-222">dotnet add reference</span><span class="sxs-lookup"><span data-stu-id="6861c-222">dotnet add reference</span></span>](dotnet-add-reference.md) | <span data-ttu-id="6861c-223">添加项目引用。</span><span class="sxs-lookup"><span data-stu-id="6861c-223">Adds a project reference.</span></span>
[<span data-ttu-id="6861c-224">dotnet list reference</span><span class="sxs-lookup"><span data-stu-id="6861c-224">dotnet list reference</span></span>](dotnet-list-reference.md) | <span data-ttu-id="6861c-225">列出项目引用。</span><span class="sxs-lookup"><span data-stu-id="6861c-225">Lists project references.</span></span>
[<span data-ttu-id="6861c-226">dotnet remove reference</span><span class="sxs-lookup"><span data-stu-id="6861c-226">dotnet remove reference</span></span>](dotnet-remove-reference.md) | <span data-ttu-id="6861c-227">删除项目引用。</span><span class="sxs-lookup"><span data-stu-id="6861c-227">Removes a project reference.</span></span>

### <a name="nuget-packages"></a><span data-ttu-id="6861c-228">NuGet 包</span><span class="sxs-lookup"><span data-stu-id="6861c-228">NuGet packages</span></span>

<span data-ttu-id="6861c-229">命令</span><span class="sxs-lookup"><span data-stu-id="6861c-229">Command</span></span> | <span data-ttu-id="6861c-230">函数</span><span class="sxs-lookup"><span data-stu-id="6861c-230">Function</span></span>
--- | ---
[<span data-ttu-id="6861c-231">dotnet add package</span><span class="sxs-lookup"><span data-stu-id="6861c-231">dotnet add package</span></span>](dotnet-add-package.md) | <span data-ttu-id="6861c-232">添加 NuGet 包。</span><span class="sxs-lookup"><span data-stu-id="6861c-232">Adds a NuGet package.</span></span>
[<span data-ttu-id="6861c-233">dotnet remove package</span><span class="sxs-lookup"><span data-stu-id="6861c-233">dotnet remove package</span></span>](dotnet-remove-package.md) | <span data-ttu-id="6861c-234">删除 NuGet 包。</span><span class="sxs-lookup"><span data-stu-id="6861c-234">Removes a NuGet package.</span></span>

### <a name="nuget-commands"></a><span data-ttu-id="6861c-235">NuGet 命令</span><span class="sxs-lookup"><span data-stu-id="6861c-235">NuGet commands</span></span>

<span data-ttu-id="6861c-236">命令</span><span class="sxs-lookup"><span data-stu-id="6861c-236">Command</span></span> | <span data-ttu-id="6861c-237">函数</span><span class="sxs-lookup"><span data-stu-id="6861c-237">Function</span></span>
--- | ---
[<span data-ttu-id="6861c-238">dotnet nuget delete</span><span class="sxs-lookup"><span data-stu-id="6861c-238">dotnet nuget delete</span></span>](dotnet-nuget-delete.md) | <span data-ttu-id="6861c-239">从服务器删除或取消列出包。</span><span class="sxs-lookup"><span data-stu-id="6861c-239">Deletes or unlists a package from the server.</span></span>
[<span data-ttu-id="6861c-240">dotnet nuget push</span><span class="sxs-lookup"><span data-stu-id="6861c-240">dotnet nuget push</span></span>](dotnet-nuget-push.md) | <span data-ttu-id="6861c-241">将包推送到服务器，并将其发布。</span><span class="sxs-lookup"><span data-stu-id="6861c-241">Pushes a package to the server and publishes it.</span></span>
[<span data-ttu-id="6861c-242">dotnet nuget locals</span><span class="sxs-lookup"><span data-stu-id="6861c-242">dotnet nuget locals</span></span>](dotnet-nuget-locals.md) | <span data-ttu-id="6861c-243">清除或列出本地 NuGet 资源，例如 http 请求缓存、临时缓存或计算机范围的全局包文件夹。</span><span class="sxs-lookup"><span data-stu-id="6861c-243">Clears or lists local NuGet resources such as http-request cache, temporary cache, or machine-wide global packages folder.</span></span>
[<span data-ttu-id="6861c-244">dotnet nuget add source</span><span class="sxs-lookup"><span data-stu-id="6861c-244">dotnet nuget add source</span></span>](dotnet-nuget-add-source.md) | <span data-ttu-id="6861c-245">添加 NuGet 源。</span><span class="sxs-lookup"><span data-stu-id="6861c-245">Adds a NuGet source.</span></span>
[<span data-ttu-id="6861c-246">dotnet nuget disable source</span><span class="sxs-lookup"><span data-stu-id="6861c-246">dotnet nuget disable source</span></span>](dotnet-nuget-disable-source.md) | <span data-ttu-id="6861c-247">禁用 NuGet 源。</span><span class="sxs-lookup"><span data-stu-id="6861c-247">Disables a NuGet source.</span></span>
[<span data-ttu-id="6861c-248">dotnet nuget enable source</span><span class="sxs-lookup"><span data-stu-id="6861c-248">dotnet nuget enable source</span></span>](dotnet-nuget-enable-source.md) | <span data-ttu-id="6861c-249">启用 NuGet 源。</span><span class="sxs-lookup"><span data-stu-id="6861c-249">Enables a NuGet source.</span></span>
[<span data-ttu-id="6861c-250">dotnet nuget list source</span><span class="sxs-lookup"><span data-stu-id="6861c-250">dotnet nuget list source</span></span>](dotnet-nuget-list-source.md) | <span data-ttu-id="6861c-251">列出所有已配置的 NuGet 源。</span><span class="sxs-lookup"><span data-stu-id="6861c-251">Lists all configured NuGet sources.</span></span>
[<span data-ttu-id="6861c-252">dotnet nuget remove source</span><span class="sxs-lookup"><span data-stu-id="6861c-252">dotnet nuget remove source</span></span>](dotnet-nuget-remove-source.md) | <span data-ttu-id="6861c-253">删除 NuGet 源。</span><span class="sxs-lookup"><span data-stu-id="6861c-253">Removes a NuGet source.</span></span>
[<span data-ttu-id="6861c-254">dotnet nuget update source</span><span class="sxs-lookup"><span data-stu-id="6861c-254">dotnet nuget update source</span></span>](dotnet-nuget-update-source.md) | <span data-ttu-id="6861c-255">更新 NuGet 源。</span><span class="sxs-lookup"><span data-stu-id="6861c-255">Updates a NuGet source.</span></span>

### <a name="global-tool-path-and-local-tools-commands"></a><span data-ttu-id="6861c-256">全局、工具路径和本地工具命令</span><span class="sxs-lookup"><span data-stu-id="6861c-256">Global, tool-path, and local tools commands</span></span>

<span data-ttu-id="6861c-257">工具是控制台应用程序，它们从 NuGet 包中安装并从命令提示符处进行调用。</span><span class="sxs-lookup"><span data-stu-id="6861c-257">Tools are console applications that are installed from NuGet packages and are invoked from the command prompt.</span></span> <span data-ttu-id="6861c-258">你可自行编写工具，也可安装由第三方编写的工具。</span><span class="sxs-lookup"><span data-stu-id="6861c-258">You can write tools yourself or install tools written by third parties.</span></span> <span data-ttu-id="6861c-259">工具也称为全局工具、工具路径工具和本地工具。</span><span class="sxs-lookup"><span data-stu-id="6861c-259">Tools are also known as global tools, tool-path tools, and local tools.</span></span> <span data-ttu-id="6861c-260">有关详细信息，请参阅 [.NET Core 工具概述](global-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="6861c-260">For more information, see [.NET Core tools overview](global-tools.md).</span></span> <span data-ttu-id="6861c-261">全局和工具路径工具从 .NET Core SDK 2.1 开始可用。</span><span class="sxs-lookup"><span data-stu-id="6861c-261">Global and tool-path tools are available starting with .NET Core SDK 2.1.</span></span> <span data-ttu-id="6861c-262">本地工具从 .NET Core SDK 3.0 开始可用。</span><span class="sxs-lookup"><span data-stu-id="6861c-262">Local tools are available starting with .NET Core SDK 3.0.</span></span>

<span data-ttu-id="6861c-263">命令</span><span class="sxs-lookup"><span data-stu-id="6861c-263">Command</span></span> | <span data-ttu-id="6861c-264">函数</span><span class="sxs-lookup"><span data-stu-id="6861c-264">Function</span></span>
--- | ---
[<span data-ttu-id="6861c-265">dotnet tool install</span><span class="sxs-lookup"><span data-stu-id="6861c-265">dotnet tool install</span></span>](dotnet-tool-install.md) | <span data-ttu-id="6861c-266">在计算机上安装工具。</span><span class="sxs-lookup"><span data-stu-id="6861c-266">Installs a tool on your machine.</span></span>
[<span data-ttu-id="6861c-267">dotnet tool list</span><span class="sxs-lookup"><span data-stu-id="6861c-267">dotnet tool list</span></span>](dotnet-tool-list.md) | <span data-ttu-id="6861c-268">列出计算机上当前安装的所有全局、工具路径或本地工具。</span><span class="sxs-lookup"><span data-stu-id="6861c-268">Lists all global, tool-path, or local tools currently installed on your machine.</span></span>
[<span data-ttu-id="6861c-269">dotnet tool uninstall</span><span class="sxs-lookup"><span data-stu-id="6861c-269">dotnet tool uninstall</span></span>](dotnet-tool-uninstall.md) | <span data-ttu-id="6861c-270">从计算机中卸载工具。</span><span class="sxs-lookup"><span data-stu-id="6861c-270">Uninstalls a tool from your machine.</span></span>
[<span data-ttu-id="6861c-271">dotnet tool update</span><span class="sxs-lookup"><span data-stu-id="6861c-271">dotnet tool update</span></span>](dotnet-tool-update.md) | <span data-ttu-id="6861c-272">更新计算机上安装的工具。</span><span class="sxs-lookup"><span data-stu-id="6861c-272">Updates a tool that is installed on your machine.</span></span>

### <a name="additional-tools"></a><span data-ttu-id="6861c-273">其他工具</span><span class="sxs-lookup"><span data-stu-id="6861c-273">Additional tools</span></span>

<span data-ttu-id="6861c-274">自 .NET Core SDK 2.1.300 开始，许多使用 `DotnetCliToolReference` 的仅在每个项目的基础上可用的工具现作为 .NET Core SDK 的一部分提供。</span><span class="sxs-lookup"><span data-stu-id="6861c-274">Starting with .NET Core SDK 2.1.300, a number of tools that were available only on a per project basis using `DotnetCliToolReference` are now available as part of the .NET Core SDK.</span></span> <span data-ttu-id="6861c-275">下表中列出了这些工具：</span><span class="sxs-lookup"><span data-stu-id="6861c-275">These tools are listed in the following table:</span></span>

| <span data-ttu-id="6861c-276">工具</span><span class="sxs-lookup"><span data-stu-id="6861c-276">Tool</span></span>                                              | <span data-ttu-id="6861c-277">函数</span><span class="sxs-lookup"><span data-stu-id="6861c-277">Function</span></span>                                                     |
| ------------------------------------------------- | ------------------------------------------------------------ |
| <span data-ttu-id="6861c-278">dev-certs</span><span class="sxs-lookup"><span data-stu-id="6861c-278">dev-certs</span></span>                                         | <span data-ttu-id="6861c-279">创建和管理开发证书。</span><span class="sxs-lookup"><span data-stu-id="6861c-279">Creates and manages development certificates.</span></span>                |
| [<span data-ttu-id="6861c-280">ef</span><span class="sxs-lookup"><span data-stu-id="6861c-280">ef</span></span>](/ef/core/miscellaneous/cli/dotnet)           | <span data-ttu-id="6861c-281">Entity Framework Core 命令行工具。</span><span class="sxs-lookup"><span data-stu-id="6861c-281">Entity Framework Core command-line tools.</span></span>                    |
| <span data-ttu-id="6861c-282">sql-cache</span><span class="sxs-lookup"><span data-stu-id="6861c-282">sql-cache</span></span>                                         | <span data-ttu-id="6861c-283">SQL Server 缓存命令行工具。</span><span class="sxs-lookup"><span data-stu-id="6861c-283">SQL Server cache command-line tools.</span></span>                         |
| [<span data-ttu-id="6861c-284">user-secrets</span><span class="sxs-lookup"><span data-stu-id="6861c-284">user-secrets</span></span>](/aspnet/core/security/app-secrets) | <span data-ttu-id="6861c-285">管理开发用户机密。</span><span class="sxs-lookup"><span data-stu-id="6861c-285">Manages development user secrets.</span></span>                            |
| [<span data-ttu-id="6861c-286">watch</span><span class="sxs-lookup"><span data-stu-id="6861c-286">watch</span></span>](/aspnet/core/tutorials/dotnet-watch)      | <span data-ttu-id="6861c-287">启动文件观察程序，以在更改文件时运行命令。</span><span class="sxs-lookup"><span data-stu-id="6861c-287">Starts a file watcher that runs a command when files change.</span></span> |

<span data-ttu-id="6861c-288">有关每个工具的详细信息，请键入 `dotnet <tool-name> --help`。</span><span class="sxs-lookup"><span data-stu-id="6861c-288">For more information about each tool, type `dotnet <tool-name> --help`.</span></span>

## <a name="examples"></a><span data-ttu-id="6861c-289">示例</span><span class="sxs-lookup"><span data-stu-id="6861c-289">Examples</span></span>

<span data-ttu-id="6861c-290">创建新的 .NET Core 控制台应用程序：</span><span class="sxs-lookup"><span data-stu-id="6861c-290">Create a new .NET Core console application:</span></span>

```dotnetcli
dotnet new console
```

<span data-ttu-id="6861c-291">生成给定目录中的项目及其依赖项：</span><span class="sxs-lookup"><span data-stu-id="6861c-291">Build a project and its dependencies in a given directory:</span></span>

```dotnetcli
dotnet build
```

<span data-ttu-id="6861c-292">运行应用程序：</span><span class="sxs-lookup"><span data-stu-id="6861c-292">Run an application:</span></span>

```dotnetcli
dotnet myapp.dll
```

## <a name="environment-variables"></a><span data-ttu-id="6861c-293">环境变量</span><span class="sxs-lookup"><span data-stu-id="6861c-293">Environment variables</span></span>

- <span data-ttu-id="6861c-294">`DOTNET_ROOT`，`DOTNET_ROOT(x86)`</span><span class="sxs-lookup"><span data-stu-id="6861c-294">`DOTNET_ROOT`, `DOTNET_ROOT(x86)`</span></span>

  <span data-ttu-id="6861c-295">指定 .NET Core 运行时的位置（如果运行时未安装在默认位置）。</span><span class="sxs-lookup"><span data-stu-id="6861c-295">Specifies the location of the .NET Core runtimes, if they are not installed in the default location.</span></span> <span data-ttu-id="6861c-296">Windows 上的默认位置为 `C:\Program Files\dotnet`。</span><span class="sxs-lookup"><span data-stu-id="6861c-296">The default location on Windows is `C:\Program Files\dotnet`.</span></span> <span data-ttu-id="6861c-297">Linux 和 macOS 上的默认位置为 `/usr/share/dotnet`。</span><span class="sxs-lookup"><span data-stu-id="6861c-297">The default location on Linux and macOS is `/usr/share/dotnet`.</span></span> <span data-ttu-id="6861c-298">此环境变量仅在通过生成的可执行文件 (apphosts) 运行应用时使用。</span><span class="sxs-lookup"><span data-stu-id="6861c-298">This environment variable is used only when running apps via generated executables (apphosts).</span></span> <span data-ttu-id="6861c-299">在 64 位 OS 上运行 32 位可执行文件时，改用 `DOTNET_ROOT(x86)`。</span><span class="sxs-lookup"><span data-stu-id="6861c-299">`DOTNET_ROOT(x86)` is used instead when running a 32-bit executable on a 64-bit OS.</span></span>

- `DOTNET_PACKAGES`

  <span data-ttu-id="6861c-300">全局包文件夹。</span><span class="sxs-lookup"><span data-stu-id="6861c-300">The global packages folder.</span></span> <span data-ttu-id="6861c-301">如果未设置，则默认为 Unix 上的 `~/.nuget/packages` 或 Windows 上的 `%userprofile%\.nuget\packages`。</span><span class="sxs-lookup"><span data-stu-id="6861c-301">If not set, it defaults to `~/.nuget/packages` on Unix or `%userprofile%\.nuget\packages` on Windows.</span></span>

- `DOTNET_SERVICING`

  <span data-ttu-id="6861c-302">指定加载运行时期间共享主机要使用的服务索引的位置。</span><span class="sxs-lookup"><span data-stu-id="6861c-302">Specifies the location of the servicing index to use by the shared host when loading the runtime.</span></span>

- `DOTNET_NOLOGO`

  <span data-ttu-id="6861c-303">指定是否在首次运行时显示 .NET Core 欢迎消息和遥测消息。</span><span class="sxs-lookup"><span data-stu-id="6861c-303">Specifies whether .NET Core welcome and telemetry messages are displayed on first run.</span></span> <span data-ttu-id="6861c-304">设置为 `true` 可将这些消息静音（接受 `true`、`1` 或 `yes` 值），或者，设置为 `false` 可允许显示消息（接受 `false`、`0` 或 `no` 值）。</span><span class="sxs-lookup"><span data-stu-id="6861c-304">Set to `true` to mute these messages (values `true`, `1`, or `yes` accepted) or set to `false` to allow (values `false`, `0`, or `no` accepted).</span></span> <span data-ttu-id="6861c-305">如果未设置，则默认值为 `false`，表示在首次运行时将显示消息。</span><span class="sxs-lookup"><span data-stu-id="6861c-305">If not set, the default is `false` and the messages will be displayed on first run.</span></span> <span data-ttu-id="6861c-306">此标志对遥测不起作用（请参阅 `DOTNET_CLI_TELEMETRY_OPTOUT` 中关于如何选择不发送遥测数据的信息）。</span><span class="sxs-lookup"><span data-stu-id="6861c-306">This flag has no effect on telemetry (see `DOTNET_CLI_TELEMETRY_OPTOUT` for opting out of sending telemetry).</span></span>

- `DOTNET_CLI_TELEMETRY_OPTOUT`

  <span data-ttu-id="6861c-307">指定是否收集并向 Microsoft 发送 .NET Core 工具使用情况的相关数据。</span><span class="sxs-lookup"><span data-stu-id="6861c-307">Specifies whether data about the .NET Core tools usage is collected and sent to Microsoft.</span></span> <span data-ttu-id="6861c-308">设置为 `true` 以选择退出遥测功能（接受的值为 `true`、`1` 或 `yes`）。</span><span class="sxs-lookup"><span data-stu-id="6861c-308">Set to `true` to opt-out of the telemetry feature (values `true`, `1`, or `yes` accepted).</span></span> <span data-ttu-id="6861c-309">否则，设置为 `false` 以选择加入遥测功能（接受的值为 `false`、`0` 或 `no`）。</span><span class="sxs-lookup"><span data-stu-id="6861c-309">Otherwise, set to `false` to opt into the telemetry features (values `false`, `0`, or `no` accepted).</span></span> <span data-ttu-id="6861c-310">如果未设置，则默认为 `false` 且遥测功能为活动状态。</span><span class="sxs-lookup"><span data-stu-id="6861c-310">If not set, the default is `false` and the telemetry feature is active.</span></span>

- `DOTNET_MULTILEVEL_LOOKUP`

  <span data-ttu-id="6861c-311">指定是否从全局位置解析 .NET Core 运行时、共享框架或 SDK。</span><span class="sxs-lookup"><span data-stu-id="6861c-311">Specifies whether .NET Core runtime, shared framework, or SDK are resolved from the global location.</span></span> <span data-ttu-id="6861c-312">如果未设置，则默认为 1（逻辑 `true`）。</span><span class="sxs-lookup"><span data-stu-id="6861c-312">If not set, it defaults to 1 (logical `true`).</span></span> <span data-ttu-id="6861c-313">设置为 0（逻辑 `false`），不从全局位置解析，并且具有独立的 .NET Core 安装。</span><span class="sxs-lookup"><span data-stu-id="6861c-313">Set to 0 (logical `false`) to not resolve from the global location and have isolated .NET Core installations.</span></span> <span data-ttu-id="6861c-314">有关多级别查找的详细信息，请参阅 [Multi-level SharedFX Lookup](https://github.com/dotnet/core-setup/blob/master/Documentation/design-docs/multilevel-sharedfx-lookup.md)（多级别 SharedFX 查找）。</span><span class="sxs-lookup"><span data-stu-id="6861c-314">For more information about multi-level lookup, see [Multi-level SharedFX Lookup](https://github.com/dotnet/core-setup/blob/master/Documentation/design-docs/multilevel-sharedfx-lookup.md).</span></span>

- <span data-ttu-id="6861c-315">`DOTNET_ROLL_FORWARD` 自 .NET Core 3.x SDK 起可用  。</span><span class="sxs-lookup"><span data-stu-id="6861c-315">`DOTNET_ROLL_FORWARD` **Available starting with .NET Core 3.x SDK.**</span></span>

  <span data-ttu-id="6861c-316">确定前滚行为。</span><span class="sxs-lookup"><span data-stu-id="6861c-316">Determines roll forward behavior.</span></span> <span data-ttu-id="6861c-317">有关详细信息，请参阅本文章前面介绍的 `--roll-forward` 选项。</span><span class="sxs-lookup"><span data-stu-id="6861c-317">For more information, see the `--roll-forward` option earlier in this article.</span></span>

- <span data-ttu-id="6861c-318">`DOTNET_ROLL_FORWARD_ON_NO_CANDIDATE_FX` 在 .NET Core 2.x SDK 中可用  。</span><span class="sxs-lookup"><span data-stu-id="6861c-318">`DOTNET_ROLL_FORWARD_ON_NO_CANDIDATE_FX` **Available in .NET Core 2.x SDK.**</span></span>

  <span data-ttu-id="6861c-319">如果设置为 `0`，则禁用次要版本前滚。</span><span class="sxs-lookup"><span data-stu-id="6861c-319">Disables minor version roll forward, if set to `0`.</span></span> <span data-ttu-id="6861c-320">有关详细信息，请参阅[前滚](../whats-new/dotnet-core-2-1.md#roll-forward)。</span><span class="sxs-lookup"><span data-stu-id="6861c-320">For more information, see [Roll forward](../whats-new/dotnet-core-2-1.md#roll-forward).</span></span>

- `DOTNET_CLI_UI_LANGUAGE`

  <span data-ttu-id="6861c-321">使用区域设置值（如 `en-us`）设置 CLI UI 的语言。</span><span class="sxs-lookup"><span data-stu-id="6861c-321">Sets the language of the CLI UI using a locale value such as `en-us`.</span></span> <span data-ttu-id="6861c-322">支持的值与 Visual Studio 中的值相同。</span><span class="sxs-lookup"><span data-stu-id="6861c-322">The supported values are the same as for Visual Studio.</span></span> <span data-ttu-id="6861c-323">有关详细信息，请参阅 [Visual Studio 安装文档](https://docs.microsoft.com/visualstudio/install/install-visual-studio?view=vs-2019)中有关更改安装程序语言一节。</span><span class="sxs-lookup"><span data-stu-id="6861c-323">For more information, see the section on changing the installer language in the [Visual Studio installation documentation](https://docs.microsoft.com/visualstudio/install/install-visual-studio?view=vs-2019).</span></span> <span data-ttu-id="6861c-324">.NET 资源管理器规则适用，因此你无需选取精确匹配项 &mdash; 你还可以在 `CultureInfo` 树中选取后代。</span><span class="sxs-lookup"><span data-stu-id="6861c-324">The .NET resource manager rules apply, so you don't have to pick an exact match&mdash;you can also pick descendants in the `CultureInfo` tree.</span></span> <span data-ttu-id="6861c-325">例如，如果将其设置为 `fr-CA`，CLI 将查找并使用 `fr` 翻译。</span><span class="sxs-lookup"><span data-stu-id="6861c-325">For example, if you set it to `fr-CA`, the CLI will find and use the `fr` translations.</span></span> <span data-ttu-id="6861c-326">如果你将其设置为不受支持的语言，CLI 会退回到英语。</span><span class="sxs-lookup"><span data-stu-id="6861c-326">If you set it to a language that is not supported, the CLI falls back to English.</span></span>

- `DOTNET_DISABLE_GUI_ERRORS`

  <span data-ttu-id="6861c-327">对于启用了 GUI 的已生成可执行文件 - 禁用对话框弹出窗口，此窗口通常显示某些类错误。</span><span class="sxs-lookup"><span data-stu-id="6861c-327">For GUI-enabled generated executables - disables dialog popup, which normally shows for certain classes of errors.</span></span> <span data-ttu-id="6861c-328">在这些情况下，它仅写入到 `stderr` 并退出。</span><span class="sxs-lookup"><span data-stu-id="6861c-328">It only writes to `stderr` and exits in those cases.</span></span>
  
- `DOTNET_ADDITIONAL_DEPS`

  <span data-ttu-id="6861c-329">等效于 CLI 选项 `--additional-deps`。</span><span class="sxs-lookup"><span data-stu-id="6861c-329">Equivalent to CLI option `--additional-deps`.</span></span>

- `DOTNET_RUNTIME_ID`

  <span data-ttu-id="6861c-330">替代检测到的 RID。</span><span class="sxs-lookup"><span data-stu-id="6861c-330">Overrides the detected RID.</span></span>

- `DOTNET_SHARED_STORE`

  <span data-ttu-id="6861c-331">程序集解析在某些情况下将回退到的“共享存储”的位置。</span><span class="sxs-lookup"><span data-stu-id="6861c-331">Location of the "shared store" which assembly resolution falls back to in some cases.</span></span>

- `DOTNET_STARTUP_HOOKS`

  <span data-ttu-id="6861c-332">要从中加载和执行启动挂钩的程序集列表。</span><span class="sxs-lookup"><span data-stu-id="6861c-332">List of assemblies to load and execute startup hooks from.</span></span>

- <span data-ttu-id="6861c-333">`COREHOST_TRACE`, `COREHOST_TRACEFILE`, `COREHOST_TRACE_VERBOSITY`</span><span class="sxs-lookup"><span data-stu-id="6861c-333">`COREHOST_TRACE`, `COREHOST_TRACEFILE`, `COREHOST_TRACE_VERBOSITY`</span></span>

  <span data-ttu-id="6861c-334">控制来自托管组件（例如 `dotnet.exe`、`hostfxr` 和 `hostpolicy`）的诊断跟踪。</span><span class="sxs-lookup"><span data-stu-id="6861c-334">Controls diagnostics tracing from the hosting components, such as `dotnet.exe`, `hostfxr`, and `hostpolicy`.</span></span>

## <a name="see-also"></a><span data-ttu-id="6861c-335">请参阅</span><span class="sxs-lookup"><span data-stu-id="6861c-335">See also</span></span>

- [<span data-ttu-id="6861c-336">运行时配置文件</span><span class="sxs-lookup"><span data-stu-id="6861c-336">Runtime Configuration Files</span></span>](https://github.com/dotnet/cli/blob/master/Documentation/specs/runtime-configuration-file.md)
- [<span data-ttu-id="6861c-337">.NET Core 运行时配置设置</span><span class="sxs-lookup"><span data-stu-id="6861c-337">.NET Core run-time configuration settings</span></span>](../run-time-config/index.md)
