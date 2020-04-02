---
title: dotnet 命令
description: 了解 dotnet 命令（.NET Core CLI 的通用驱动程序）及其用法。
ms.date: 02/13/2020
ms.openlocfilehash: 8692d419afd528bf49e1dc7dc1a7a5fd698b363b
ms.sourcegitcommit: 07123a475af89b6da5bb6cc51ea40ab1e8a488f0
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/24/2020
ms.locfileid: "80134079"
---
# <a name="dotnet-command"></a><span data-ttu-id="ea731-103">dotnet 命令</span><span class="sxs-lookup"><span data-stu-id="ea731-103">dotnet command</span></span>

<span data-ttu-id="ea731-104"> 本文适用于： ✔️ .NET Core 2.1 SDK 及更高版本</span><span class="sxs-lookup"><span data-stu-id="ea731-104">**This article applies to:** ✔️ .NET Core 2.1 SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="ea731-105">“属性”</span><span class="sxs-lookup"><span data-stu-id="ea731-105">Name</span></span>

<span data-ttu-id="ea731-106">`dotnet` - .NET Core CLI 的通用驱动程序。</span><span class="sxs-lookup"><span data-stu-id="ea731-106">`dotnet` - The generic driver for the .NET Core CLI.</span></span>

## <a name="synopsis"></a><span data-ttu-id="ea731-107">摘要</span><span class="sxs-lookup"><span data-stu-id="ea731-107">Synopsis</span></span>

<span data-ttu-id="ea731-108">获取有关可用命令和环境的信息：</span><span class="sxs-lookup"><span data-stu-id="ea731-108">To get information about the available commands and the environment:</span></span>

```dotnetcli
dotnet [-h|--help] [--version] [--info]
    [--list-runtimes] [--list-sdks]
```

<span data-ttu-id="ea731-109">运行命令（需要 SDK 安装）：</span><span class="sxs-lookup"><span data-stu-id="ea731-109">To run a command (requires SDK installation):</span></span>

```dotnetcli
dotnet <COMMAND> [-d|--diagnostics] [-h|--help] [--verbosity]
    [command-options] [arguments]
```

<span data-ttu-id="ea731-110">运行应用程序：</span><span class="sxs-lookup"><span data-stu-id="ea731-110">To run an application:</span></span>

```dotnetcli
dotnet [--additionalprobingpath] [--additional-deps]
    [--fx-version]  [--roll-forward]
    <PATH_TO_APPLICATION> [arguments]

dotnet exec [--additionalprobingpath] [--additional-deps]
    [--fx-version]  [--roll-forward]
    <PATH_TO_APPLICATION> [arguments]
```

<span data-ttu-id="ea731-111">`--roll-forward` 自 .NET Core 3.x 起可用。</span><span class="sxs-lookup"><span data-stu-id="ea731-111">`--roll-forward` is available since .NET Core 3.x.</span></span> <span data-ttu-id="ea731-112">使用 .NET Core 2.x 的 `--roll-forward-on-no-candidate-fx`。</span><span class="sxs-lookup"><span data-stu-id="ea731-112">Use `--roll-forward-on-no-candidate-fx` for .NET Core 2.x.</span></span>

## <a name="description"></a><span data-ttu-id="ea731-113">描述</span><span class="sxs-lookup"><span data-stu-id="ea731-113">Description</span></span>

<span data-ttu-id="ea731-114">`dotnet` 命令有两个函数：</span><span class="sxs-lookup"><span data-stu-id="ea731-114">The `dotnet` command has two functions:</span></span>

- <span data-ttu-id="ea731-115">它提供了用于处理 .NET Core 项目的命令。</span><span class="sxs-lookup"><span data-stu-id="ea731-115">It provides commands for working with .NET Core projects.</span></span>

  <span data-ttu-id="ea731-116">例如，[`dotnet build`](dotnet-build.md) 生成项目。</span><span class="sxs-lookup"><span data-stu-id="ea731-116">For example, [`dotnet build`](dotnet-build.md) builds a project.</span></span> <span data-ttu-id="ea731-117">每个命令定义自己的选项和参数。</span><span class="sxs-lookup"><span data-stu-id="ea731-117">Each command defines its own options and arguments.</span></span> <span data-ttu-id="ea731-118">所有命令都支持 `--help` 选项，用于打印有关如何使用命令的简短文档。</span><span class="sxs-lookup"><span data-stu-id="ea731-118">All commands support the `--help` option for printing out brief documentation about how to use the command.</span></span>

- <span data-ttu-id="ea731-119">它运行 .NET Core 应用程序。</span><span class="sxs-lookup"><span data-stu-id="ea731-119">It runs .NET Core applications.</span></span>

  <span data-ttu-id="ea731-120">指定应用程序 `.dll` 文件的路径以运行应用程序。</span><span class="sxs-lookup"><span data-stu-id="ea731-120">You specify the path to an application `.dll` file to run the application.</span></span> <span data-ttu-id="ea731-121">例如，`dotnet myapp.dll` 运行 `myapp` 应用程序。</span><span class="sxs-lookup"><span data-stu-id="ea731-121">For example, `dotnet myapp.dll` runs the `myapp` application.</span></span> <span data-ttu-id="ea731-122">要了解部署选项，请参阅 [.NET Core 应用程序部署](../deploying/index.md)。</span><span class="sxs-lookup"><span data-stu-id="ea731-122">See [.NET Core application deployment](../deploying/index.md) to learn about deployment options.</span></span>

## <a name="options"></a><span data-ttu-id="ea731-123">选项</span><span class="sxs-lookup"><span data-stu-id="ea731-123">Options</span></span>

<span data-ttu-id="ea731-124">`dotnet` 本身有不同的选项，可用于运行命令和运行应用程序。</span><span class="sxs-lookup"><span data-stu-id="ea731-124">Different options are available for `dotnet` by itself, for running a command, and for running an application.</span></span>

### <a name="options-for-dotnet-by-itself"></a><span data-ttu-id="ea731-125">dotnet 本身的选项</span><span class="sxs-lookup"><span data-stu-id="ea731-125">Options for dotnet by itself</span></span>

<span data-ttu-id="ea731-126">以下是 `dotnet` 本身的选项。</span><span class="sxs-lookup"><span data-stu-id="ea731-126">The following options are for `dotnet` by itself.</span></span> <span data-ttu-id="ea731-127">例如 `dotnet --info`。</span><span class="sxs-lookup"><span data-stu-id="ea731-127">For example, `dotnet --info`.</span></span> <span data-ttu-id="ea731-128">这些选项打印出有关环境的信息。</span><span class="sxs-lookup"><span data-stu-id="ea731-128">They print out information about the environment.</span></span>

- **`--info`**

  <span data-ttu-id="ea731-129">打印出有关 .NET Core 安装和计算机环境（如当前操作系统）的详细信息，并提交 .NET Core 版本的 SHA。</span><span class="sxs-lookup"><span data-stu-id="ea731-129">Prints out detailed information about a .NET Core installation and the machine environment, such as the current operating system, and commit SHA of the .NET Core version.</span></span>

- **`--version`**

  <span data-ttu-id="ea731-130">打印使用中的 .NET Core SDK 版本。</span><span class="sxs-lookup"><span data-stu-id="ea731-130">Prints out the version of the .NET Core SDK in use.</span></span>

- **`--list-runtimes`**

  <span data-ttu-id="ea731-131">打印已安装的 .NET Core 运行时的列表。</span><span class="sxs-lookup"><span data-stu-id="ea731-131">Prints out a list of the installed .NET Core runtimes.</span></span>

- **`--list-sdks`**

  <span data-ttu-id="ea731-132">打印已安装的 .NET Core SDK 的列表。</span><span class="sxs-lookup"><span data-stu-id="ea731-132">Prints out a list of the installed .NET Core SDKs.</span></span>

- **`-h|--help`**

  <span data-ttu-id="ea731-133">打印可用命令列表。</span><span class="sxs-lookup"><span data-stu-id="ea731-133">Prints out a list of available commands.</span></span>

### <a name="sdk-options-for-running-a-command"></a><span data-ttu-id="ea731-134">用于运行命令的 SDK 选项</span><span class="sxs-lookup"><span data-stu-id="ea731-134">SDK options for running a command</span></span>

<span data-ttu-id="ea731-135">以下选项适用于使用命令的 `dotnet`。</span><span class="sxs-lookup"><span data-stu-id="ea731-135">The following options are for `dotnet` with a command.</span></span> <span data-ttu-id="ea731-136">例如 `dotnet build --help`。</span><span class="sxs-lookup"><span data-stu-id="ea731-136">For example, `dotnet build --help`.</span></span>

- **`-d|--diagnostics`**

  <span data-ttu-id="ea731-137">启用诊断输出。</span><span class="sxs-lookup"><span data-stu-id="ea731-137">Enables diagnostic output.</span></span>

- **`-v|--verbosity <LEVEL>`**

  <span data-ttu-id="ea731-138">设置命令的详细级别。</span><span class="sxs-lookup"><span data-stu-id="ea731-138">Sets the verbosity level of the command.</span></span> <span data-ttu-id="ea731-139">允许使用的值为 `q[uiet]`、`m[inimal]`、`n[ormal]`、`d[etailed]` 和 `diag[nostic]`。</span><span class="sxs-lookup"><span data-stu-id="ea731-139">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="ea731-140">并非在每个命令中均受支持。</span><span class="sxs-lookup"><span data-stu-id="ea731-140">Not supported in every command.</span></span> <span data-ttu-id="ea731-141">请参阅特定的命令页，确定此选项是否可用。</span><span class="sxs-lookup"><span data-stu-id="ea731-141">See specific command page to determine if this option is available.</span></span>

- **`-h|--help`**

  <span data-ttu-id="ea731-142">打印出给定命令的文档，如 `dotnet build --help`。</span><span class="sxs-lookup"><span data-stu-id="ea731-142">Prints out documentation for a given command, such as `dotnet build --help`.</span></span>

- **`command options`**

  <span data-ttu-id="ea731-143">每个命令定义特定于该命令的选项。</span><span class="sxs-lookup"><span data-stu-id="ea731-143">Each command defines options specific to that command.</span></span> <span data-ttu-id="ea731-144">有关可用选项的列表，请参阅特定命令页。</span><span class="sxs-lookup"><span data-stu-id="ea731-144">See specific command page for a list of available options.</span></span>

### <a name="runtime-options"></a><span data-ttu-id="ea731-145">运行时选项</span><span class="sxs-lookup"><span data-stu-id="ea731-145">Runtime options</span></span>

<span data-ttu-id="ea731-146">`dotnet` 运行应用程序时，可以使用以下选项。</span><span class="sxs-lookup"><span data-stu-id="ea731-146">The following options are available when `dotnet` runs an application.</span></span> <span data-ttu-id="ea731-147">例如 `dotnet myapp.dll --fx-version 3.1.1`。</span><span class="sxs-lookup"><span data-stu-id="ea731-147">For example, `dotnet myapp.dll --fx-version 3.1.1`.</span></span>

- **`--additionalprobingpath <PATH>`**

  <span data-ttu-id="ea731-148">包含要进行探测的探测策略和程序集的路径。</span><span class="sxs-lookup"><span data-stu-id="ea731-148">Path containing probing policy and assemblies to probe.</span></span>

- **`--additional-deps <PATH>`**

  <span data-ttu-id="ea731-149">附加 .deps.json 文件的路径  。</span><span class="sxs-lookup"><span data-stu-id="ea731-149">Path to an additional *.deps.json* file.</span></span> <span data-ttu-id="ea731-150">deps.json 文件包含依赖项、编译依赖项和用于解决程序集冲突的版本信息列表  。</span><span class="sxs-lookup"><span data-stu-id="ea731-150">A *deps.json* file contains a list of dependencies, compilation dependencies, and version information used to address assembly conflicts.</span></span> <span data-ttu-id="ea731-151">有关详细信息，请参阅 GitHub 上的[运行时配置文件](https://github.com/dotnet/cli/blob/master/Documentation/specs/runtime-configuration-file.md)。</span><span class="sxs-lookup"><span data-stu-id="ea731-151">For more information, see [Runtime Configuration Files](https://github.com/dotnet/cli/blob/master/Documentation/specs/runtime-configuration-file.md) on GitHub.</span></span>

- **`--fx-version <VERSION>`**

  <span data-ttu-id="ea731-152">用于运行应用程序的 .NET Core 运行时版本。</span><span class="sxs-lookup"><span data-stu-id="ea731-152">Version of the .NET Core runtime to use to run the application.</span></span>

- **`--runtimeconfig`**

  <span data-ttu-id="ea731-153">runtimeconfig.template.json 文件的路径  。</span><span class="sxs-lookup"><span data-stu-id="ea731-153">Path to a *runtimeconfig.json* file.</span></span> <span data-ttu-id="ea731-154">runtimeconfig.template.json 文件是包含运行时设置的配置文件  。</span><span class="sxs-lookup"><span data-stu-id="ea731-154">A *runtimeconfig.json* file is a configuration file that contains run-time settings.</span></span> <span data-ttu-id="ea731-155">有关详细信息，请参阅 [.NET Core 运行时配置设置](../run-time-config/index.md#runtimeconfigjson)。</span><span class="sxs-lookup"><span data-stu-id="ea731-155">For more information, see [.NET Core run-time configuration settings](../run-time-config/index.md#runtimeconfigjson).</span></span>

- <span data-ttu-id="ea731-156">`--roll-forward-on-no-candidate-fx <N>` 在 .NET Core 2.x SDK 中可用   。</span><span class="sxs-lookup"><span data-stu-id="ea731-156">**`--roll-forward-on-no-candidate-fx <N>`** **Available in .NET Core 2.x SDK.**</span></span>

  <span data-ttu-id="ea731-157">所需的共享框架不可用时，请定义行为。</span><span class="sxs-lookup"><span data-stu-id="ea731-157">Defines behavior when the required shared framework is not available.</span></span> <span data-ttu-id="ea731-158">`N` 可以是：</span><span class="sxs-lookup"><span data-stu-id="ea731-158">`N` can be:</span></span>

  - <span data-ttu-id="ea731-159">`0` - 禁用次要版本前滚。</span><span class="sxs-lookup"><span data-stu-id="ea731-159">`0` - Disable even minor version roll forward.</span></span>
  - <span data-ttu-id="ea731-160">`1` - 前滚次要版本，但不前滚主版本。</span><span class="sxs-lookup"><span data-stu-id="ea731-160">`1` - Roll forward on minor version, but not on major version.</span></span> <span data-ttu-id="ea731-161">这是默认行为。</span><span class="sxs-lookup"><span data-stu-id="ea731-161">This is the default behavior.</span></span>
  - <span data-ttu-id="ea731-162">`2` - 前滚次要和主版本。</span><span class="sxs-lookup"><span data-stu-id="ea731-162">`2` - Roll forward on minor and major versions.</span></span>

   <span data-ttu-id="ea731-163">有关详细信息，请参阅[前滚](../whats-new/dotnet-core-2-1.md#roll-forward)。</span><span class="sxs-lookup"><span data-stu-id="ea731-163">For more information, see [Roll forward](../whats-new/dotnet-core-2-1.md#roll-forward).</span></span>

- <span data-ttu-id="ea731-164">`--roll-forward <SETTING>` 自 .NET Core SDK 3.0 起可用   。</span><span class="sxs-lookup"><span data-stu-id="ea731-164">**`--roll-forward <SETTING>`** **Available starting with .NET Core SDK 3.0.**</span></span>

  <span data-ttu-id="ea731-165">控制将前滚操作应用于应用的方式。</span><span class="sxs-lookup"><span data-stu-id="ea731-165">Controls how roll forward is applied to the app.</span></span> <span data-ttu-id="ea731-166">`SETTING` 可以为下列值之一。</span><span class="sxs-lookup"><span data-stu-id="ea731-166">The `SETTING` can be one of the following values.</span></span> <span data-ttu-id="ea731-167">如果未指定，则 `Minor` 为默认类型。</span><span class="sxs-lookup"><span data-stu-id="ea731-167">If not specified, `Minor` is the default.</span></span>

  - <span data-ttu-id="ea731-168">`LatestPatch` - 前滚到最高补丁版本。</span><span class="sxs-lookup"><span data-stu-id="ea731-168">`LatestPatch` - Roll forward to the highest patch version.</span></span> <span data-ttu-id="ea731-169">这会禁用次要版本前滚。</span><span class="sxs-lookup"><span data-stu-id="ea731-169">This disables minor version roll forward.</span></span>
  - <span data-ttu-id="ea731-170">`Minor` - 如果缺少所请求的次要版本，则前滚到最低的较高次要版本。</span><span class="sxs-lookup"><span data-stu-id="ea731-170">`Minor` - Roll forward to the lowest higher minor version, if requested minor version is missing.</span></span> <span data-ttu-id="ea731-171">如果存在所请求的次要版本，则使用 LatestPatch 策略。</span><span class="sxs-lookup"><span data-stu-id="ea731-171">If the requested minor version is present, then the LatestPatch policy is used.</span></span>
  - <span data-ttu-id="ea731-172">`Major` - 如果缺少所请求的主要版本，则前滚到最低的较高主要版本和最低的次要版本。</span><span class="sxs-lookup"><span data-stu-id="ea731-172">`Major` - Roll forward to lowest higher major version, and lowest minor version, if requested major version is missing.</span></span> <span data-ttu-id="ea731-173">如果存在所请求的主要版本，则使用 Minor 策略。</span><span class="sxs-lookup"><span data-stu-id="ea731-173">If the requested major version is present, then the Minor policy is used.</span></span>
  - <span data-ttu-id="ea731-174">`LatestMinor` - 即使存在所请求的次要版本，仍前滚到最高次要版本。</span><span class="sxs-lookup"><span data-stu-id="ea731-174">`LatestMinor` - Roll forward to highest minor version, even if requested minor version is present.</span></span> <span data-ttu-id="ea731-175">适用于组件托管方案。</span><span class="sxs-lookup"><span data-stu-id="ea731-175">Intended for component hosting scenarios.</span></span>
  - <span data-ttu-id="ea731-176">`LatestMajor` - 即使存在所请求的主要版本，仍前滚到最高主要版本和最高次要版本。</span><span class="sxs-lookup"><span data-stu-id="ea731-176">`LatestMajor` - Roll forward to highest major and highest minor version, even if requested major is present.</span></span> <span data-ttu-id="ea731-177">适用于组件托管方案。</span><span class="sxs-lookup"><span data-stu-id="ea731-177">Intended for component hosting scenarios.</span></span>
  - <span data-ttu-id="ea731-178">`Disable` - 不前滚。</span><span class="sxs-lookup"><span data-stu-id="ea731-178">`Disable` - Don't roll forward.</span></span> <span data-ttu-id="ea731-179">仅绑定到指定的版本。</span><span class="sxs-lookup"><span data-stu-id="ea731-179">Only bind to specified version.</span></span> <span data-ttu-id="ea731-180">建议不要将此策略用于一般用途，因为它会禁用前滚到最新补丁的功能。</span><span class="sxs-lookup"><span data-stu-id="ea731-180">This policy isn't recommended for general use because it disables the ability to roll forward to the latest patches.</span></span> <span data-ttu-id="ea731-181">该值仅建议用于测试。</span><span class="sxs-lookup"><span data-stu-id="ea731-181">This value is only recommended for testing.</span></span>

<span data-ttu-id="ea731-182">除 `Disable` 外，所有设置都将使用可用的最高补丁版本。</span><span class="sxs-lookup"><span data-stu-id="ea731-182">With the exception of `Disable`, all settings will use the highest available patch version.</span></span>

<span data-ttu-id="ea731-183">前滚行为还可以在项目文件属性、运行时配置文件属性和环境变量中进行配置。</span><span class="sxs-lookup"><span data-stu-id="ea731-183">Roll forward behavior can also be configured in a project file property, a run-time configuration file property, and an environment variable.</span></span> <span data-ttu-id="ea731-184">有关详细信息，请参阅[主版本运行时前滚](../whats-new/dotnet-core-3-0.md#major-version-runtime-roll-forward)。</span><span class="sxs-lookup"><span data-stu-id="ea731-184">For more information, see [Major-version runtime roll forward](../whats-new/dotnet-core-3-0.md#major-version-runtime-roll-forward).</span></span>

## <a name="dotnet-commands"></a><span data-ttu-id="ea731-185">dotnet 命令</span><span class="sxs-lookup"><span data-stu-id="ea731-185">dotnet commands</span></span>

### <a name="general"></a><span data-ttu-id="ea731-186">常规</span><span class="sxs-lookup"><span data-stu-id="ea731-186">General</span></span>

| <span data-ttu-id="ea731-187">命令</span><span class="sxs-lookup"><span data-stu-id="ea731-187">Command</span></span>                                       | <span data-ttu-id="ea731-188">函数</span><span class="sxs-lookup"><span data-stu-id="ea731-188">Function</span></span>                                                            |
| --------------------------------------------- | ------------------------------------------------------------------- |
| [<span data-ttu-id="ea731-189">dotnet build</span><span class="sxs-lookup"><span data-stu-id="ea731-189">dotnet build</span></span>](dotnet-build.md)               | <span data-ttu-id="ea731-190">生成 .NET Core 应用程序。</span><span class="sxs-lookup"><span data-stu-id="ea731-190">Builds a .NET Core application.</span></span>                                     |
| [<span data-ttu-id="ea731-191">dotnet build-server</span><span class="sxs-lookup"><span data-stu-id="ea731-191">dotnet build-server</span></span>](dotnet-build-server.md) | <span data-ttu-id="ea731-192">与通过生成启动的服务器进行交互。</span><span class="sxs-lookup"><span data-stu-id="ea731-192">Interacts with servers started by a build.</span></span>                          |
| [<span data-ttu-id="ea731-193">dotnet clean</span><span class="sxs-lookup"><span data-stu-id="ea731-193">dotnet clean</span></span>](dotnet-clean.md)               | <span data-ttu-id="ea731-194">清除生成输出。</span><span class="sxs-lookup"><span data-stu-id="ea731-194">Clean build outputs.</span></span>                                                |
| [<span data-ttu-id="ea731-195">dotnet help</span><span class="sxs-lookup"><span data-stu-id="ea731-195">dotnet help</span></span>](dotnet-help.md)                 | <span data-ttu-id="ea731-196">显示命令更详细的在线文档。</span><span class="sxs-lookup"><span data-stu-id="ea731-196">Shows more detailed documentation online for the command.</span></span>           |
| [<span data-ttu-id="ea731-197">dotnet migrate</span><span class="sxs-lookup"><span data-stu-id="ea731-197">dotnet migrate</span></span>](dotnet-migrate.md)           | <span data-ttu-id="ea731-198">将有效的预览版 2 项目迁移到 .NET Core SDK 1.0 项目。</span><span class="sxs-lookup"><span data-stu-id="ea731-198">Migrates a valid Preview 2 project to a .NET Core SDK 1.0 project.</span></span>  |
| [<span data-ttu-id="ea731-199">dotnet msbuild</span><span class="sxs-lookup"><span data-stu-id="ea731-199">dotnet msbuild</span></span>](dotnet-msbuild.md)           | <span data-ttu-id="ea731-200">提供对 MSBuild 命令行的访问权限。</span><span class="sxs-lookup"><span data-stu-id="ea731-200">Provides access to the MSBuild command line.</span></span>                        |
| [<span data-ttu-id="ea731-201">dotnet new</span><span class="sxs-lookup"><span data-stu-id="ea731-201">dotnet new</span></span>](dotnet-new.md)                   | <span data-ttu-id="ea731-202">为给定的模板初始化 C# 或 F# 项目。</span><span class="sxs-lookup"><span data-stu-id="ea731-202">Initializes a C# or F# project for a given template.</span></span>                |
| [<span data-ttu-id="ea731-203">dotnet pack</span><span class="sxs-lookup"><span data-stu-id="ea731-203">dotnet pack</span></span>](dotnet-pack.md)                 | <span data-ttu-id="ea731-204">创建代码的 NuGet 包。</span><span class="sxs-lookup"><span data-stu-id="ea731-204">Creates a NuGet package of your code.</span></span>                               |
| [<span data-ttu-id="ea731-205">dotnet publish</span><span class="sxs-lookup"><span data-stu-id="ea731-205">dotnet publish</span></span>](dotnet-publish.md)           | <span data-ttu-id="ea731-206">发布 .NET 依赖于框架或独立应用程序。</span><span class="sxs-lookup"><span data-stu-id="ea731-206">Publishes a .NET framework-dependent or self-contained application.</span></span> |
| [<span data-ttu-id="ea731-207">dotnet restore</span><span class="sxs-lookup"><span data-stu-id="ea731-207">dotnet restore</span></span>](dotnet-restore.md)           | <span data-ttu-id="ea731-208">还原给定应用程序的依赖项。</span><span class="sxs-lookup"><span data-stu-id="ea731-208">Restores the dependencies for a given application.</span></span>                  |
| [<span data-ttu-id="ea731-209">dotnet run</span><span class="sxs-lookup"><span data-stu-id="ea731-209">dotnet run</span></span>](dotnet-run.md)                   | <span data-ttu-id="ea731-210">从源运行应用程序。</span><span class="sxs-lookup"><span data-stu-id="ea731-210">Runs the application from source.</span></span>                                   |
| [<span data-ttu-id="ea731-211">dotnet sln</span><span class="sxs-lookup"><span data-stu-id="ea731-211">dotnet sln</span></span>](dotnet-sln.md)                   | <span data-ttu-id="ea731-212">用于添加、删除和列出解决方案文件中项目的选项。</span><span class="sxs-lookup"><span data-stu-id="ea731-212">Options to add, remove, and list projects in a solution file.</span></span>       |
| [<span data-ttu-id="ea731-213">dotnet store</span><span class="sxs-lookup"><span data-stu-id="ea731-213">dotnet store</span></span>](dotnet-store.md)               | <span data-ttu-id="ea731-214">将程序集存储到运行时包存储区。</span><span class="sxs-lookup"><span data-stu-id="ea731-214">Stores assemblies in the runtime package store.</span></span>                     |
| [<span data-ttu-id="ea731-215">dotnet test</span><span class="sxs-lookup"><span data-stu-id="ea731-215">dotnet test</span></span>](dotnet-test.md)                 | <span data-ttu-id="ea731-216">使用测试运行程序运行测试。</span><span class="sxs-lookup"><span data-stu-id="ea731-216">Runs tests using a test runner.</span></span>                                     |

### <a name="project-references"></a><span data-ttu-id="ea731-217">项目引用</span><span class="sxs-lookup"><span data-stu-id="ea731-217">Project references</span></span>

<span data-ttu-id="ea731-218">命令</span><span class="sxs-lookup"><span data-stu-id="ea731-218">Command</span></span> | <span data-ttu-id="ea731-219">函数</span><span class="sxs-lookup"><span data-stu-id="ea731-219">Function</span></span>
--- | ---
[<span data-ttu-id="ea731-220">dotnet add reference</span><span class="sxs-lookup"><span data-stu-id="ea731-220">dotnet add reference</span></span>](dotnet-add-reference.md) | <span data-ttu-id="ea731-221">添加项目引用。</span><span class="sxs-lookup"><span data-stu-id="ea731-221">Adds a project reference.</span></span>
[<span data-ttu-id="ea731-222">dotnet list reference</span><span class="sxs-lookup"><span data-stu-id="ea731-222">dotnet list reference</span></span>](dotnet-list-reference.md) | <span data-ttu-id="ea731-223">列出项目引用。</span><span class="sxs-lookup"><span data-stu-id="ea731-223">Lists project references.</span></span>
[<span data-ttu-id="ea731-224">dotnet remove reference</span><span class="sxs-lookup"><span data-stu-id="ea731-224">dotnet remove reference</span></span>](dotnet-remove-reference.md) | <span data-ttu-id="ea731-225">删除项目引用。</span><span class="sxs-lookup"><span data-stu-id="ea731-225">Removes a project reference.</span></span>

### <a name="nuget-packages"></a><span data-ttu-id="ea731-226">NuGet 包</span><span class="sxs-lookup"><span data-stu-id="ea731-226">NuGet packages</span></span>

<span data-ttu-id="ea731-227">命令</span><span class="sxs-lookup"><span data-stu-id="ea731-227">Command</span></span> | <span data-ttu-id="ea731-228">函数</span><span class="sxs-lookup"><span data-stu-id="ea731-228">Function</span></span>
--- | ---
[<span data-ttu-id="ea731-229">dotnet add package</span><span class="sxs-lookup"><span data-stu-id="ea731-229">dotnet add package</span></span>](dotnet-add-package.md) | <span data-ttu-id="ea731-230">添加 NuGet 包。</span><span class="sxs-lookup"><span data-stu-id="ea731-230">Adds a NuGet package.</span></span>
[<span data-ttu-id="ea731-231">dotnet remove package</span><span class="sxs-lookup"><span data-stu-id="ea731-231">dotnet remove package</span></span>](dotnet-remove-package.md) | <span data-ttu-id="ea731-232">删除 NuGet 包。</span><span class="sxs-lookup"><span data-stu-id="ea731-232">Removes a NuGet package.</span></span>

### <a name="nuget-commands"></a><span data-ttu-id="ea731-233">NuGet 命令</span><span class="sxs-lookup"><span data-stu-id="ea731-233">NuGet commands</span></span>

<span data-ttu-id="ea731-234">命令</span><span class="sxs-lookup"><span data-stu-id="ea731-234">Command</span></span> | <span data-ttu-id="ea731-235">函数</span><span class="sxs-lookup"><span data-stu-id="ea731-235">Function</span></span>
--- | ---
[<span data-ttu-id="ea731-236">dotnet nuget delete</span><span class="sxs-lookup"><span data-stu-id="ea731-236">dotnet nuget delete</span></span>](dotnet-nuget-delete.md) | <span data-ttu-id="ea731-237">从服务器删除或取消列出包。</span><span class="sxs-lookup"><span data-stu-id="ea731-237">Deletes or unlists a package from the server.</span></span>
[<span data-ttu-id="ea731-238">dotnet nuget push</span><span class="sxs-lookup"><span data-stu-id="ea731-238">dotnet nuget push</span></span>](dotnet-nuget-push.md) | <span data-ttu-id="ea731-239">将包推送到服务器，并将其发布。</span><span class="sxs-lookup"><span data-stu-id="ea731-239">Pushes a package to the server and publishes it.</span></span>
[<span data-ttu-id="ea731-240">dotnet nuget locals</span><span class="sxs-lookup"><span data-stu-id="ea731-240">dotnet nuget locals</span></span>](dotnet-nuget-locals.md) | <span data-ttu-id="ea731-241">清除或列出本地 NuGet 资源，例如 http 请求缓存、临时缓存或计算机范围的全局包文件夹。</span><span class="sxs-lookup"><span data-stu-id="ea731-241">Clears or lists local NuGet resources such as http-request cache, temporary cache, or machine-wide global packages folder.</span></span>
[<span data-ttu-id="ea731-242">dotnet nuget add source</span><span class="sxs-lookup"><span data-stu-id="ea731-242">dotnet nuget add source</span></span>](dotnet-nuget-add-source.md) | <span data-ttu-id="ea731-243">添加 NuGet 源。</span><span class="sxs-lookup"><span data-stu-id="ea731-243">Adds a NuGet source.</span></span>
[<span data-ttu-id="ea731-244">dotnet nuget disable source</span><span class="sxs-lookup"><span data-stu-id="ea731-244">dotnet nuget disable source</span></span>](dotnet-nuget-disable-source.md) | <span data-ttu-id="ea731-245">禁用 NuGet 源。</span><span class="sxs-lookup"><span data-stu-id="ea731-245">Disables a NuGet source.</span></span>
[<span data-ttu-id="ea731-246">dotnet nuget enable source</span><span class="sxs-lookup"><span data-stu-id="ea731-246">dotnet nuget enable source</span></span>](dotnet-nuget-enable-source.md) | <span data-ttu-id="ea731-247">启用 NuGet 源。</span><span class="sxs-lookup"><span data-stu-id="ea731-247">Enables a NuGet source.</span></span>
[<span data-ttu-id="ea731-248">dotnet nuget list source</span><span class="sxs-lookup"><span data-stu-id="ea731-248">dotnet nuget list source</span></span>](dotnet-nuget-list-source.md) | <span data-ttu-id="ea731-249">列出所有已配置的 NuGet 源。</span><span class="sxs-lookup"><span data-stu-id="ea731-249">Lists all configured NuGet sources.</span></span>
[<span data-ttu-id="ea731-250">dotnet nuget remove source</span><span class="sxs-lookup"><span data-stu-id="ea731-250">dotnet nuget remove source</span></span>](dotnet-nuget-remove-source.md) | <span data-ttu-id="ea731-251">删除 NuGet 源。</span><span class="sxs-lookup"><span data-stu-id="ea731-251">Removes a NuGet source.</span></span>
[<span data-ttu-id="ea731-252">dotnet nuget update source</span><span class="sxs-lookup"><span data-stu-id="ea731-252">dotnet nuget update source</span></span>](dotnet-nuget-update-source.md) | <span data-ttu-id="ea731-253">更新 NuGet 源。</span><span class="sxs-lookup"><span data-stu-id="ea731-253">Updates a NuGet source.</span></span>

### <a name="global-tool-path-and-local-tools-commands"></a><span data-ttu-id="ea731-254">全局、工具路径和本地工具命令</span><span class="sxs-lookup"><span data-stu-id="ea731-254">Global, tool-path, and local tools commands</span></span>

<span data-ttu-id="ea731-255">工具是控制台应用程序，它们从 NuGet 包中安装并从命令提示符处进行调用。</span><span class="sxs-lookup"><span data-stu-id="ea731-255">Tools are console applications that are installed from NuGet packages and are invoked from the command prompt.</span></span> <span data-ttu-id="ea731-256">你可自行编写工具，也可安装由第三方编写的工具。</span><span class="sxs-lookup"><span data-stu-id="ea731-256">You can write tools yourself or install tools written by third parties.</span></span> <span data-ttu-id="ea731-257">工具也称为全局工具、工具路径工具和本地工具。</span><span class="sxs-lookup"><span data-stu-id="ea731-257">Tools are also known as global tools, tool-path tools, and local tools.</span></span> <span data-ttu-id="ea731-258">有关详细信息，请参阅 [.NET Core 工具概述](global-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="ea731-258">For more information, see [.NET Core tools overview](global-tools.md).</span></span> <span data-ttu-id="ea731-259">全局和工具路径工具从 .NET Core SDK 2.1 开始可用。</span><span class="sxs-lookup"><span data-stu-id="ea731-259">Global and tool-path tools are available starting with .NET Core SDK 2.1.</span></span> <span data-ttu-id="ea731-260">本地工具从 .NET Core SDK 3.0 开始可用。</span><span class="sxs-lookup"><span data-stu-id="ea731-260">Local tools are available starting with .NET Core SDK 3.0.</span></span>

<span data-ttu-id="ea731-261">命令</span><span class="sxs-lookup"><span data-stu-id="ea731-261">Command</span></span> | <span data-ttu-id="ea731-262">函数</span><span class="sxs-lookup"><span data-stu-id="ea731-262">Function</span></span>
--- | ---
[<span data-ttu-id="ea731-263">dotnet tool install</span><span class="sxs-lookup"><span data-stu-id="ea731-263">dotnet tool install</span></span>](dotnet-tool-install.md) | <span data-ttu-id="ea731-264">在计算机上安装工具。</span><span class="sxs-lookup"><span data-stu-id="ea731-264">Installs a tool on your machine.</span></span>
[<span data-ttu-id="ea731-265">dotnet tool list</span><span class="sxs-lookup"><span data-stu-id="ea731-265">dotnet tool list</span></span>](dotnet-tool-list.md) | <span data-ttu-id="ea731-266">列出计算机上当前安装的所有全局、工具路径或本地工具。</span><span class="sxs-lookup"><span data-stu-id="ea731-266">Lists all global, tool-path, or local tools currently installed on your machine.</span></span>
[<span data-ttu-id="ea731-267">dotnet tool uninstall</span><span class="sxs-lookup"><span data-stu-id="ea731-267">dotnet tool uninstall</span></span>](dotnet-tool-uninstall.md) | <span data-ttu-id="ea731-268">从计算机中卸载工具。</span><span class="sxs-lookup"><span data-stu-id="ea731-268">Uninstalls a tool from your machine.</span></span>
[<span data-ttu-id="ea731-269">dotnet tool update</span><span class="sxs-lookup"><span data-stu-id="ea731-269">dotnet tool update</span></span>](dotnet-tool-update.md) | <span data-ttu-id="ea731-270">更新计算机上安装的工具。</span><span class="sxs-lookup"><span data-stu-id="ea731-270">Updates a tool that is installed on your machine.</span></span>

### <a name="additional-tools"></a><span data-ttu-id="ea731-271">其他工具</span><span class="sxs-lookup"><span data-stu-id="ea731-271">Additional tools</span></span>

<span data-ttu-id="ea731-272">自 .NET Core SDK 2.1.300 开始，许多使用 `DotnetCliToolReference` 的仅在每个项目的基础上可用的工具现作为 .NET Core SDK 的一部分提供。</span><span class="sxs-lookup"><span data-stu-id="ea731-272">Starting with .NET Core SDK 2.1.300, a number of tools that were available only on a per project basis using `DotnetCliToolReference` are now available as part of the .NET Core SDK.</span></span> <span data-ttu-id="ea731-273">下表中列出了这些工具：</span><span class="sxs-lookup"><span data-stu-id="ea731-273">These tools are listed in the following table:</span></span>

| <span data-ttu-id="ea731-274">工具</span><span class="sxs-lookup"><span data-stu-id="ea731-274">Tool</span></span>                                              | <span data-ttu-id="ea731-275">函数</span><span class="sxs-lookup"><span data-stu-id="ea731-275">Function</span></span>                                                     |
| ------------------------------------------------- | ------------------------------------------------------------ |
| <span data-ttu-id="ea731-276">dev-certs</span><span class="sxs-lookup"><span data-stu-id="ea731-276">dev-certs</span></span>                                         | <span data-ttu-id="ea731-277">创建和管理开发证书。</span><span class="sxs-lookup"><span data-stu-id="ea731-277">Creates and manages development certificates.</span></span>                |
| [<span data-ttu-id="ea731-278">ef</span><span class="sxs-lookup"><span data-stu-id="ea731-278">ef</span></span>](/ef/core/miscellaneous/cli/dotnet)           | <span data-ttu-id="ea731-279">Entity Framework Core 命令行工具。</span><span class="sxs-lookup"><span data-stu-id="ea731-279">Entity Framework Core command-line tools.</span></span>                    |
| <span data-ttu-id="ea731-280">sql-cache</span><span class="sxs-lookup"><span data-stu-id="ea731-280">sql-cache</span></span>                                         | <span data-ttu-id="ea731-281">SQL Server 缓存命令行工具。</span><span class="sxs-lookup"><span data-stu-id="ea731-281">SQL Server cache command-line tools.</span></span>                         |
| [<span data-ttu-id="ea731-282">user-secrets</span><span class="sxs-lookup"><span data-stu-id="ea731-282">user-secrets</span></span>](/aspnet/core/security/app-secrets) | <span data-ttu-id="ea731-283">管理开发用户机密。</span><span class="sxs-lookup"><span data-stu-id="ea731-283">Manages development user secrets.</span></span>                            |
| [<span data-ttu-id="ea731-284">watch</span><span class="sxs-lookup"><span data-stu-id="ea731-284">watch</span></span>](/aspnet/core/tutorials/dotnet-watch)      | <span data-ttu-id="ea731-285">启动文件观察程序，以在更改文件时运行命令。</span><span class="sxs-lookup"><span data-stu-id="ea731-285">Starts a file watcher that runs a command when files change.</span></span> |

<span data-ttu-id="ea731-286">有关每个工具的详细信息，请键入 `dotnet <tool-name> --help`。</span><span class="sxs-lookup"><span data-stu-id="ea731-286">For more information about each tool, type `dotnet <tool-name> --help`.</span></span>

## <a name="examples"></a><span data-ttu-id="ea731-287">示例</span><span class="sxs-lookup"><span data-stu-id="ea731-287">Examples</span></span>

<span data-ttu-id="ea731-288">创建新的 .NET Core 控制台应用程序：</span><span class="sxs-lookup"><span data-stu-id="ea731-288">Create a new .NET Core console application:</span></span>

```dotnetcli
dotnet new console
```

<span data-ttu-id="ea731-289">生成给定目录中的项目及其依赖项：</span><span class="sxs-lookup"><span data-stu-id="ea731-289">Build a project and its dependencies in a given directory:</span></span>

```dotnetcli
dotnet build
```

<span data-ttu-id="ea731-290">运行应用程序：</span><span class="sxs-lookup"><span data-stu-id="ea731-290">Run an application:</span></span>

```dotnetcli
dotnet myapp.dll
```

## <a name="environment-variables"></a><span data-ttu-id="ea731-291">环境变量</span><span class="sxs-lookup"><span data-stu-id="ea731-291">Environment variables</span></span>

- <span data-ttu-id="ea731-292">`DOTNET_ROOT`，`DOTNET_ROOT(x86)`</span><span class="sxs-lookup"><span data-stu-id="ea731-292">`DOTNET_ROOT`, `DOTNET_ROOT(x86)`</span></span>

  <span data-ttu-id="ea731-293">指定 .NET Core 运行时的位置（如果运行时未安装在默认位置）。</span><span class="sxs-lookup"><span data-stu-id="ea731-293">Specifies the location of the .NET Core runtimes, if they are not installed in the default location.</span></span> <span data-ttu-id="ea731-294">Windows 上的默认位置为 `C:\Program Files\dotnet`。</span><span class="sxs-lookup"><span data-stu-id="ea731-294">The default location on Windows is `C:\Program Files\dotnet`.</span></span> <span data-ttu-id="ea731-295">Linux 和 macOS 上的默认位置为 `/usr/share/dotnet`。</span><span class="sxs-lookup"><span data-stu-id="ea731-295">The default location on Linux and macOS is `/usr/share/dotnet`.</span></span> <span data-ttu-id="ea731-296">此环境变量仅在通过生成的可执行文件 (apphosts) 运行应用时使用。</span><span class="sxs-lookup"><span data-stu-id="ea731-296">This environment variable is used only when running apps via generated executables (apphosts).</span></span> <span data-ttu-id="ea731-297">在 64 位 OS 上运行 32 位可执行文件时，改用 `DOTNET_ROOT(x86)`。</span><span class="sxs-lookup"><span data-stu-id="ea731-297">`DOTNET_ROOT(x86)` is used instead when running a 32-bit executable on a 64-bit OS.</span></span>

- `DOTNET_PACKAGES`

  <span data-ttu-id="ea731-298">全局包文件夹。</span><span class="sxs-lookup"><span data-stu-id="ea731-298">The global packages folder.</span></span> <span data-ttu-id="ea731-299">如果未设置，则默认为 Unix 上的 `~/.nuget/packages` 或 Windows 上的 `%userprofile%\.nuget\packages`。</span><span class="sxs-lookup"><span data-stu-id="ea731-299">If not set, it defaults to `~/.nuget/packages` on Unix or `%userprofile%\.nuget\packages` on Windows.</span></span>

- `DOTNET_SERVICING`

  <span data-ttu-id="ea731-300">指定加载运行时期间共享主机要使用的服务索引的位置。</span><span class="sxs-lookup"><span data-stu-id="ea731-300">Specifies the location of the servicing index to use by the shared host when loading the runtime.</span></span>

- `DOTNET_NOLOGO`

  <span data-ttu-id="ea731-301">指定是否在首次运行时显示 .NET Core 欢迎消息和遥测消息。</span><span class="sxs-lookup"><span data-stu-id="ea731-301">Specifies whether .NET Core welcome and telemetry messages are displayed on first run.</span></span> <span data-ttu-id="ea731-302">设置为 `true` 可将这些消息静音（接受 `true`、`1` 或 `yes` 值），或者，设置为 `false` 可允许显示消息（接受 `false`、`0` 或 `no` 值）。</span><span class="sxs-lookup"><span data-stu-id="ea731-302">Set to `true` to mute these messages (values `true`, `1`, or `yes` accepted) or set to `false` to allow (values `false`, `0`, or `no` accepted).</span></span> <span data-ttu-id="ea731-303">如果未设置，则默认值为 `false`，表示在首次运行时将显示消息。</span><span class="sxs-lookup"><span data-stu-id="ea731-303">If not set, the default is `false` and the messages will be displayed on first run.</span></span> <span data-ttu-id="ea731-304">请注意，此标志对遥测不起作用（请参阅 `DOTNET_CLI_TELEMETRY_OPTOUT` 中关于如何选择不发送遥测数据的信息）。</span><span class="sxs-lookup"><span data-stu-id="ea731-304">Note that this flag has no effect on telemetry (see `DOTNET_CLI_TELEMETRY_OPTOUT` for opting out of sending telemetry).</span></span>

- `DOTNET_CLI_TELEMETRY_OPTOUT`

  <span data-ttu-id="ea731-305">指定是否收集并向 Microsoft 发送 .NET Core 工具使用情况的相关数据。</span><span class="sxs-lookup"><span data-stu-id="ea731-305">Specifies whether data about the .NET Core tools usage is collected and sent to Microsoft.</span></span> <span data-ttu-id="ea731-306">设置为 `true` 以选择退出遥测功能（接受的值为 `true`、`1` 或 `yes`）。</span><span class="sxs-lookup"><span data-stu-id="ea731-306">Set to `true` to opt-out of the telemetry feature (values `true`, `1`, or `yes` accepted).</span></span> <span data-ttu-id="ea731-307">否则，设置为 `false` 以选择加入遥测功能（接受的值为 `false`、`0` 或 `no`）。</span><span class="sxs-lookup"><span data-stu-id="ea731-307">Otherwise, set to `false` to opt into the telemetry features (values `false`, `0`, or `no` accepted).</span></span> <span data-ttu-id="ea731-308">如果未设置，则默认为 `false` 且遥测功能为活动状态。</span><span class="sxs-lookup"><span data-stu-id="ea731-308">If not set, the default is `false` and the telemetry feature is active.</span></span>

- `DOTNET_MULTILEVEL_LOOKUP`

  <span data-ttu-id="ea731-309">指定是否从全局位置解析 .NET Core 运行时、共享框架或 SDK。</span><span class="sxs-lookup"><span data-stu-id="ea731-309">Specifies whether .NET Core runtime, shared framework, or SDK are resolved from the global location.</span></span> <span data-ttu-id="ea731-310">如果未设置，则默认为 1（逻辑 `true`）。</span><span class="sxs-lookup"><span data-stu-id="ea731-310">If not set, it defaults to 1 (logical `true`).</span></span> <span data-ttu-id="ea731-311">设置为 0（逻辑 `false`），不从全局位置解析，并且具有独立的 .NET Core 安装。</span><span class="sxs-lookup"><span data-stu-id="ea731-311">Set to 0 (logical `false`) to not resolve from the global location and have isolated .NET Core installations.</span></span> <span data-ttu-id="ea731-312">有关多级别查找的详细信息，请参阅 [Multi-level SharedFX Lookup](https://github.com/dotnet/core-setup/blob/master/Documentation/design-docs/multilevel-sharedfx-lookup.md)（多级别 SharedFX 查找）。</span><span class="sxs-lookup"><span data-stu-id="ea731-312">For more information about multi-level lookup, see [Multi-level SharedFX Lookup](https://github.com/dotnet/core-setup/blob/master/Documentation/design-docs/multilevel-sharedfx-lookup.md).</span></span>

- <span data-ttu-id="ea731-313">`DOTNET_ROLL_FORWARD` 自 .NET Core 3.x SDK 起可用  。</span><span class="sxs-lookup"><span data-stu-id="ea731-313">`DOTNET_ROLL_FORWARD` **Available starting with .NET Core 3.x SDK.**</span></span>

  <span data-ttu-id="ea731-314">确定前滚行为。</span><span class="sxs-lookup"><span data-stu-id="ea731-314">Determines roll forward behavior.</span></span> <span data-ttu-id="ea731-315">有关详细信息，请参阅本文章前面介绍的 `--roll-forward` 选项。</span><span class="sxs-lookup"><span data-stu-id="ea731-315">For more information, see the `--roll-forward` option earlier in this article.</span></span>

- <span data-ttu-id="ea731-316">`DOTNET_ROLL_FORWARD_ON_NO_CANDIDATE_FX` 在 .NET Core 2.x SDK 中可用  。</span><span class="sxs-lookup"><span data-stu-id="ea731-316">`DOTNET_ROLL_FORWARD_ON_NO_CANDIDATE_FX` **Available in .NET Core 2.x SDK.**</span></span>

  <span data-ttu-id="ea731-317">如果设置为 `0`，则禁用次要版本前滚。</span><span class="sxs-lookup"><span data-stu-id="ea731-317">Disables minor version roll forward, if set to `0`.</span></span> <span data-ttu-id="ea731-318">有关详细信息，请参阅[前滚](../whats-new/dotnet-core-2-1.md#roll-forward)。</span><span class="sxs-lookup"><span data-stu-id="ea731-318">For more information, see [Roll forward](../whats-new/dotnet-core-2-1.md#roll-forward).</span></span>

- `DOTNET_CLI_UI_LANGUAGE`

  <span data-ttu-id="ea731-319">使用区域设置值（如 `en-us`）设置 CLI UI 的语言。</span><span class="sxs-lookup"><span data-stu-id="ea731-319">Sets the language of the CLI UI using a locale value such as `en-us`.</span></span> <span data-ttu-id="ea731-320">支持的值与 Visual Studio 中的值相同。</span><span class="sxs-lookup"><span data-stu-id="ea731-320">The supported values are the same as for Visual Studio.</span></span> <span data-ttu-id="ea731-321">有关详细信息，请参阅 [Visual Studio 安装文档](https://docs.microsoft.com/visualstudio/install/install-visual-studio?view=vs-2019)中有关更改安装程序语言一节。</span><span class="sxs-lookup"><span data-stu-id="ea731-321">For more information, see the section on changing the installer language in the [Visual Studio installation documentation](https://docs.microsoft.com/visualstudio/install/install-visual-studio?view=vs-2019).</span></span> <span data-ttu-id="ea731-322">.NET 资源管理器规则适用，因此你无需选取精确匹配项 &mdash; 你还可以在 `CultureInfo` 树中选取后代。</span><span class="sxs-lookup"><span data-stu-id="ea731-322">The .NET resource manager rules apply, so you don't have to pick an exact match&mdash;you can also pick descendants in the `CultureInfo` tree.</span></span> <span data-ttu-id="ea731-323">例如，如果将其设置为 `fr-CA`，CLI 将查找并使用 `fr` 翻译。</span><span class="sxs-lookup"><span data-stu-id="ea731-323">For example, if you set it to `fr-CA`, the CLI will find and use the `fr` translations.</span></span> <span data-ttu-id="ea731-324">如果你将其设置为不受支持的语言，CLI 会退回到英语。</span><span class="sxs-lookup"><span data-stu-id="ea731-324">If you set it to a language that is not supported, the CLI falls back to English.</span></span>

- `DOTNET_DISABLE_GUI_ERRORS`

  <span data-ttu-id="ea731-325">对于启用了 GUI 的已生成可执行文件 - 禁用对话框弹出窗口，此窗口通常显示某些类错误。</span><span class="sxs-lookup"><span data-stu-id="ea731-325">For GUI-enabled generated executables - disables dialog popup, which normally shows for certain classes of errors.</span></span> <span data-ttu-id="ea731-326">在这些情况下，它仅写入到 `stderr` 并退出。</span><span class="sxs-lookup"><span data-stu-id="ea731-326">It only writes to `stderr` and exits in those cases.</span></span>
  
- `DOTNET_ADDITIONAL_DEPS`

  <span data-ttu-id="ea731-327">等效于 CLI 选项 `--additional-deps`。</span><span class="sxs-lookup"><span data-stu-id="ea731-327">Equivalent to CLI option `--additional-deps`.</span></span>

- `DOTNET_RUNTIME_ID`

  <span data-ttu-id="ea731-328">替代检测到的 RID。</span><span class="sxs-lookup"><span data-stu-id="ea731-328">Overrides the detected RID.</span></span>

- `DOTNET_SHARED_STORE`

  <span data-ttu-id="ea731-329">程序集解析在某些情况下将回退到的“共享存储”的位置。</span><span class="sxs-lookup"><span data-stu-id="ea731-329">Location of the "shared store" which assembly resolution falls back to in some cases.</span></span>

- `DOTNET_STARTUP_HOOKS`

  <span data-ttu-id="ea731-330">要从中加载和执行启动挂钩的程序集列表。</span><span class="sxs-lookup"><span data-stu-id="ea731-330">List of assemblies to load and execute startup hooks from.</span></span>

- <span data-ttu-id="ea731-331">`COREHOST_TRACE`, `COREHOST_TRACEFILE`, `COREHOST_TRACE_VERBOSITY`</span><span class="sxs-lookup"><span data-stu-id="ea731-331">`COREHOST_TRACE`, `COREHOST_TRACEFILE`, `COREHOST_TRACE_VERBOSITY`</span></span>

  <span data-ttu-id="ea731-332">控制来自托管组件（例如 `dotnet.exe`、`hostfxr` 和 `hostpolicy`）的诊断跟踪。</span><span class="sxs-lookup"><span data-stu-id="ea731-332">Controls diagnostics tracing from the hosting components, such as `dotnet.exe`, `hostfxr`, and `hostpolicy`.</span></span>

## <a name="see-also"></a><span data-ttu-id="ea731-333">请参阅</span><span class="sxs-lookup"><span data-stu-id="ea731-333">See also</span></span>

- [<span data-ttu-id="ea731-334">运行时配置文件</span><span class="sxs-lookup"><span data-stu-id="ea731-334">Runtime Configuration Files</span></span>](https://github.com/dotnet/cli/blob/master/Documentation/specs/runtime-configuration-file.md)
- [<span data-ttu-id="ea731-335">.NET Core 运行时配置设置</span><span class="sxs-lookup"><span data-stu-id="ea731-335">.NET Core run-time configuration settings</span></span>](../run-time-config/index.md)
