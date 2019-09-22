---
title: dotnet 命令
description: 了解 dotnet 命令（.NET Core CLI 工具的通用驱动程序）及其用法。
ms.date: 06/04/2018
ms.openlocfilehash: a22340c26ca2e483e43857e2ecb31f2ab53b60f4
ms.sourcegitcommit: a4b10e1f2a8bb4e8ff902630855474a0c4f1b37a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/19/2019
ms.locfileid: "71117507"
---
# <a name="dotnet-command"></a><span data-ttu-id="12fae-103">dotnet 命令</span><span class="sxs-lookup"><span data-stu-id="12fae-103">dotnet command</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="12fae-104">name</span><span class="sxs-lookup"><span data-stu-id="12fae-104">Name</span></span>

<span data-ttu-id="12fae-105">`dotnet` - 一款管理 .NET 源代码和二进制文件的工具。</span><span class="sxs-lookup"><span data-stu-id="12fae-105">`dotnet` - A tool for managing .NET source code and binaries.</span></span>

## <a name="synopsis"></a><span data-ttu-id="12fae-106">摘要</span><span class="sxs-lookup"><span data-stu-id="12fae-106">Synopsis</span></span>

<!-- markdownlint-disable MD025 -->

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="12fae-107">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="12fae-107">.NET Core 2.1</span></span>](#tab/netcore21)

```dotnetcli
dotnet [command] [arguments] [--additional-deps] [--additionalprobingpath] [--depsfile]
    [-d|--diagnostics] [--fx-version] [-h|--help] [--info] [--list-runtimes] [--list-sdks] [--roll-forward-on-no-candidate-fx] [--runtimeconfig] [-v|--verbosity] [--version]
```

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="12fae-108">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="12fae-108">.NET Core 2.0</span></span>](#tab/netcore20)

```dotnetcli
dotnet [command] [arguments] [--additional-deps] [--additionalprobingpath] [--depsfile]
    [-d|--diagnostics] [--fx-version] [-h|--help] [--info] [--roll-forward-on-no-candidate-fx]
    [--runtimeconfig] [-v|--verbosity] [--version]
```

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="12fae-109">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="12fae-109">.NET Core 1.x</span></span>](#tab/netcore1x)

```dotnetcli
dotnet [command] [arguments] [--additionalprobingpath] [--depsfile] [-d|--diagnostics]
    [--fx-version] [-h|--help] [--info] [--runtimeconfig] [-v|--verbosity] [--version]
```

---

## <a name="description"></a><span data-ttu-id="12fae-110">说明</span><span class="sxs-lookup"><span data-stu-id="12fae-110">Description</span></span>

<span data-ttu-id="12fae-111">`dotnet` 是一款管理 .NET 源代码和二进制文件的工具。</span><span class="sxs-lookup"><span data-stu-id="12fae-111">`dotnet` is a tool for managing .NET source code and binaries.</span></span> <span data-ttu-id="12fae-112">它公开执行特定任务的命令，例如 [`dotnet build`](dotnet-build.md) 和 [`dotnet run`](dotnet-run.md)。</span><span class="sxs-lookup"><span data-stu-id="12fae-112">It exposes commands that perform specific tasks, such as [`dotnet build`](dotnet-build.md) and [`dotnet run`](dotnet-run.md).</span></span> <span data-ttu-id="12fae-113">每个命令都定义自己的参数。</span><span class="sxs-lookup"><span data-stu-id="12fae-113">Each command defines its own arguments.</span></span> <span data-ttu-id="12fae-114">在每个命令后键入 `--help` 以访问简要帮助文档。</span><span class="sxs-lookup"><span data-stu-id="12fae-114">Type `--help` after each command to access brief help documentation.</span></span>

<span data-ttu-id="12fae-115">可以使用 `dotnet` 来运行应用程序，方法是指定应用程序 DLL，如 `dotnet myapp.dll`.</span><span class="sxs-lookup"><span data-stu-id="12fae-115">`dotnet` can be used to run applications, by specifying an application DLL, such as `dotnet myapp.dll`.</span></span> <span data-ttu-id="12fae-116">要了解部署选项，请参阅 [.NET Core 应用程序部署](../deploying/index.md)。</span><span class="sxs-lookup"><span data-stu-id="12fae-116">See [.NET Core application deployment](../deploying/index.md) for to learn about deployment options.</span></span>

## <a name="options"></a><span data-ttu-id="12fae-117">选项</span><span class="sxs-lookup"><span data-stu-id="12fae-117">Options</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="12fae-118">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="12fae-118">.NET Core 2.1</span></span>](#tab/netcore21)

`--additional-deps <PATH>`

<span data-ttu-id="12fae-119">附加 .deps.json 文件的路径  。</span><span class="sxs-lookup"><span data-stu-id="12fae-119">Path to an additional *.deps.json* file.</span></span>

`--additionalprobingpath <PATH>`

<span data-ttu-id="12fae-120">包含要进行探测的探测策略和程序集的路径。</span><span class="sxs-lookup"><span data-stu-id="12fae-120">Path containing probing policy and assemblies to probe.</span></span>

`--depsfile`

<span data-ttu-id="12fae-121">deps.json 文件的路径  。</span><span class="sxs-lookup"><span data-stu-id="12fae-121">Path to a *deps.json* file.</span></span>

<span data-ttu-id="12fae-122">deps.json 文件包含依赖项、编译依赖项和用于解决程序集冲突的版本信息列表  。</span><span class="sxs-lookup"><span data-stu-id="12fae-122">A *deps.json* file contains a list of dependencies, compilation dependencies and version information used to address assembly conflicts.</span></span> <span data-ttu-id="12fae-123">有关此文件的详细信息，请参阅 GitHub 上的[运行时配置文件](https://github.com/dotnet/cli/blob/master/Documentation/specs/runtime-configuration-file.md)。</span><span class="sxs-lookup"><span data-stu-id="12fae-123">For more information about this file, see [Runtime Configuration Files](https://github.com/dotnet/cli/blob/master/Documentation/specs/runtime-configuration-file.md) on GitHub.</span></span>

`-d|--diagnostics`

<span data-ttu-id="12fae-124">启用诊断输出。</span><span class="sxs-lookup"><span data-stu-id="12fae-124">Enables diagnostic output.</span></span>

`--fx-version <VERSION>`

<span data-ttu-id="12fae-125">用于运行应用程序的 .NET Core 运行时版本。</span><span class="sxs-lookup"><span data-stu-id="12fae-125">Version of the .NET Core runtime to use to run the application.</span></span>

`-h|--help`

<span data-ttu-id="12fae-126">打印出给定命令的文档，如 `dotnet build --help`。</span><span class="sxs-lookup"><span data-stu-id="12fae-126">Prints out documentation for a given command, such as `dotnet build --help`.</span></span> <span data-ttu-id="12fae-127">`dotnet --help` 打印可用命令列表。</span><span class="sxs-lookup"><span data-stu-id="12fae-127">`dotnet --help` prints a list of available commands.</span></span>

`--info`

<span data-ttu-id="12fae-128">打印出有关 .NET Core 安装和计算机环境（如当前操作系统）的详细信息，并提交 .NET Core 版本的 SHA。</span><span class="sxs-lookup"><span data-stu-id="12fae-128">Prints out detailed information about a .NET Core installation and the machine environment, such as the current operating system, and commit SHA of the .NET Core version.</span></span>

`--list-runtimes`

<span data-ttu-id="12fae-129">显示已安装的 .NET Core 运行时。</span><span class="sxs-lookup"><span data-stu-id="12fae-129">Displays the installed .NET Core runtimes.</span></span>

`--list-sdks`

<span data-ttu-id="12fae-130">显示已安装的 .NET Core SDK。</span><span class="sxs-lookup"><span data-stu-id="12fae-130">Displays the installed .NET Core SDKs.</span></span>

`--roll-forward-on-no-candidate-fx <N>`

<span data-ttu-id="12fae-131">所需的共享框架不可用时，请定义行为。</span><span class="sxs-lookup"><span data-stu-id="12fae-131">Defines behavior when the required shared framework is not available.</span></span> <span data-ttu-id="12fae-132">`N` 可以是：</span><span class="sxs-lookup"><span data-stu-id="12fae-132">`N` can be:</span></span>

- <span data-ttu-id="12fae-133">`0` - 禁用次要版本前滚。</span><span class="sxs-lookup"><span data-stu-id="12fae-133">`0` - Disable even minor version roll forward.</span></span>
- <span data-ttu-id="12fae-134">`1` - 前滚次要版本，但不前滚主版本。</span><span class="sxs-lookup"><span data-stu-id="12fae-134">`1` - Roll forward on minor version, but not on major version.</span></span> <span data-ttu-id="12fae-135">这是默认行为。</span><span class="sxs-lookup"><span data-stu-id="12fae-135">This is the default behavior.</span></span>
- <span data-ttu-id="12fae-136">`2` - 前滚次要和主版本。</span><span class="sxs-lookup"><span data-stu-id="12fae-136">`2` - Roll forward on minor and major versions.</span></span>

 <span data-ttu-id="12fae-137">有关详细信息，请参阅[前滚](../whats-new/dotnet-core-2-1.md#roll-forward)。</span><span class="sxs-lookup"><span data-stu-id="12fae-137">For more information, see [Roll forward](../whats-new/dotnet-core-2-1.md#roll-forward).</span></span>

`--runtimeconfig`

<span data-ttu-id="12fae-138">runtimeconfig.template.json 文件的路径  。</span><span class="sxs-lookup"><span data-stu-id="12fae-138">Path to a *runtimeconfig.json* file.</span></span>

<span data-ttu-id="12fae-139">runtimeconfig.template.json 文件是包含运行时配置设置的配置文件  。</span><span class="sxs-lookup"><span data-stu-id="12fae-139">A *runtimeconfig.json* file is a configuration file containing runtime configuration settings.</span></span> <span data-ttu-id="12fae-140">有关详细信息，请参阅 GitHub 上的[运行时配置文件](https://github.com/dotnet/cli/blob/master/Documentation/specs/runtime-configuration-file.md)。</span><span class="sxs-lookup"><span data-stu-id="12fae-140">For more information, see [Runtime Configuration Files](https://github.com/dotnet/cli/blob/master/Documentation/specs/runtime-configuration-file.md) on GitHub.</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="12fae-141">设置命令的详细级别。</span><span class="sxs-lookup"><span data-stu-id="12fae-141">Sets the verbosity level of the command.</span></span> <span data-ttu-id="12fae-142">允许使用的值为 `q[uiet]`、`m[inimal]`、`n[ormal]`、`d[etailed]` 和 `diag[nostic]`。</span><span class="sxs-lookup"><span data-stu-id="12fae-142">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="12fae-143">并非在每个命令中均受支持；请参阅特定的命令页，确定此选项是否可用。</span><span class="sxs-lookup"><span data-stu-id="12fae-143">Not supported in every command; see specific command page to determine if this option is available.</span></span>

`--version`

<span data-ttu-id="12fae-144">打印使用中的 .NET Core SDK 版本。</span><span class="sxs-lookup"><span data-stu-id="12fae-144">Prints out the version of the .NET Core SDK in use.</span></span>

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="12fae-145">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="12fae-145">.NET Core 2.0</span></span>](#tab/netcore20)

`--additional-deps <PATH>`

<span data-ttu-id="12fae-146">附加 .deps.json 文件的路径  。</span><span class="sxs-lookup"><span data-stu-id="12fae-146">Path to an additional *.deps.json* file.</span></span>

`--additionalprobingpath <PATH>`

<span data-ttu-id="12fae-147">包含要进行探测的探测策略和程序集的路径。</span><span class="sxs-lookup"><span data-stu-id="12fae-147">Path containing probing policy and assemblies to probe.</span></span>

`--depsfile`

<span data-ttu-id="12fae-148">deps.json 文件的路径  。</span><span class="sxs-lookup"><span data-stu-id="12fae-148">Path to a *deps.json* file.</span></span>

<span data-ttu-id="12fae-149">deps.json 文件包含依赖项、编译依赖项和用于解决程序集冲突的版本信息列表  。</span><span class="sxs-lookup"><span data-stu-id="12fae-149">A *deps.json* file contains a list of dependencies, compilation dependencies and version information used to address assembly conflicts.</span></span> <span data-ttu-id="12fae-150">有关详细信息，请参阅 GitHub 上的[运行时配置文件](https://github.com/dotnet/cli/blob/master/Documentation/specs/runtime-configuration-file.md)。</span><span class="sxs-lookup"><span data-stu-id="12fae-150">For more details on this file, see [Runtime Configuration Files on GitHub](https://github.com/dotnet/cli/blob/master/Documentation/specs/runtime-configuration-file.md).</span></span>

`-d|--diagnostics`

<span data-ttu-id="12fae-151">启用诊断输出。</span><span class="sxs-lookup"><span data-stu-id="12fae-151">Enables diagnostic output.</span></span>

`--fx-version <VERSION>`

<span data-ttu-id="12fae-152">用于运行应用程序的 .NET Core 运行时版本。</span><span class="sxs-lookup"><span data-stu-id="12fae-152">Version of the .NET Core runtime to use to run the application.</span></span>

`-h|--help`

<span data-ttu-id="12fae-153">打印出给定命令的文档，如 `dotnet build --help`。</span><span class="sxs-lookup"><span data-stu-id="12fae-153">Prints out documentation for a given command, such as `dotnet build --help`.</span></span> <span data-ttu-id="12fae-154">`dotnet --help` 打印可用命令列表。</span><span class="sxs-lookup"><span data-stu-id="12fae-154">`dotnet --help` prints a list of available commands.</span></span>

`--info`

<span data-ttu-id="12fae-155">打印出有关 .NET Core 安装和计算机环境（如当前操作系统）的详细信息，并提交 .NET Core 版本的 SHA。</span><span class="sxs-lookup"><span data-stu-id="12fae-155">Prints out detailed information about a .NET Core installation and the machine environment, such as the current operating system, and commit SHA of the .NET Core version.</span></span>

`--roll-forward-on-no-candidate-fx`

 <span data-ttu-id="12fae-156">如果设置为 `0`，则禁用次要版本前滚。</span><span class="sxs-lookup"><span data-stu-id="12fae-156">Disables minor version roll forward, if set to `0`.</span></span> <span data-ttu-id="12fae-157">有关详细信息，请参阅[前滚](../whats-new/dotnet-core-2-1.md#roll-forward)。</span><span class="sxs-lookup"><span data-stu-id="12fae-157">For more information, see [Roll forward](../whats-new/dotnet-core-2-1.md#roll-forward).</span></span>

`--runtimeconfig`

<span data-ttu-id="12fae-158">runtimeconfig.template.json 文件的路径  。</span><span class="sxs-lookup"><span data-stu-id="12fae-158">Path to a *runtimeconfig.json* file.</span></span>

<span data-ttu-id="12fae-159">runtimeconfig.template.json 文件是包含运行时配置设置的配置文件  。</span><span class="sxs-lookup"><span data-stu-id="12fae-159">A *runtimeconfig.json* file is a configuration file containing runtime configuration settings.</span></span> <span data-ttu-id="12fae-160">有关详细信息，请参阅 GitHub 上的[运行时配置文件](https://github.com/dotnet/cli/blob/master/Documentation/specs/runtime-configuration-file.md)。</span><span class="sxs-lookup"><span data-stu-id="12fae-160">For more details, see [Runtime Configuration Files on GitHub](https://github.com/dotnet/cli/blob/master/Documentation/specs/runtime-configuration-file.md).</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="12fae-161">设置命令的详细级别。</span><span class="sxs-lookup"><span data-stu-id="12fae-161">Sets the verbosity level of the command.</span></span> <span data-ttu-id="12fae-162">允许使用的值为 `q[uiet]`、`m[inimal]`、`n[ormal]`、`d[etailed]` 和 `diag[nostic]`。</span><span class="sxs-lookup"><span data-stu-id="12fae-162">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="12fae-163">并非在每个命令中均受支持；请参阅特定的命令页，确定此选项是否可用。</span><span class="sxs-lookup"><span data-stu-id="12fae-163">Not supported in every command; see specific command page to determine if this option is available.</span></span>

`--version`

<span data-ttu-id="12fae-164">打印使用中的 .NET Core SDK 版本。</span><span class="sxs-lookup"><span data-stu-id="12fae-164">Prints out the version of the .NET Core SDK in use.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="12fae-165">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="12fae-165">.NET Core 1.x</span></span>](#tab/netcore1x)

`--additionalprobingpath <PATH>`

<span data-ttu-id="12fae-166">包含要进行探测的探测策略和程序集的路径。</span><span class="sxs-lookup"><span data-stu-id="12fae-166">Path containing probing policy and assemblies to probe.</span></span>

`--depsfile`

<span data-ttu-id="12fae-167">deps.json 文件的路径  。</span><span class="sxs-lookup"><span data-stu-id="12fae-167">Path to a *deps.json* file.</span></span>

<span data-ttu-id="12fae-168">deps.json 文件包含依赖项、编译依赖项和用于解决程序集冲突的版本信息列表  。</span><span class="sxs-lookup"><span data-stu-id="12fae-168">A *deps.json* file contains a list of dependencies, compilation dependencies and version information used to address assembly conflicts.</span></span> <span data-ttu-id="12fae-169">有关详细信息，请参阅 GitHub 上的[运行时配置文件](https://github.com/dotnet/cli/blob/master/Documentation/specs/runtime-configuration-file.md)。</span><span class="sxs-lookup"><span data-stu-id="12fae-169">For more details on this file, see [Runtime Configuration Files on GitHub](https://github.com/dotnet/cli/blob/master/Documentation/specs/runtime-configuration-file.md).</span></span>

`-d|--diagnostics`

<span data-ttu-id="12fae-170">启用诊断输出。</span><span class="sxs-lookup"><span data-stu-id="12fae-170">Enables diagnostic output.</span></span>

`--fx-version <VERSION>`

<span data-ttu-id="12fae-171">用于运行应用程序的 .NET Core 运行时版本。</span><span class="sxs-lookup"><span data-stu-id="12fae-171">Version of the .NET Core runtime to use to run the application.</span></span>

`-h|--help`

<span data-ttu-id="12fae-172">打印出给定命令的文档，如 `dotnet build --help`。</span><span class="sxs-lookup"><span data-stu-id="12fae-172">Prints out documentation for a given command, such as `dotnet build --help`.</span></span> <span data-ttu-id="12fae-173">`dotnet --help` 打印可用命令列表。</span><span class="sxs-lookup"><span data-stu-id="12fae-173">`dotnet --help` prints a list of available commands.</span></span>

`--info`

<span data-ttu-id="12fae-174">打印出有关 .NET Core 安装和计算机环境（如当前操作系统）的详细信息，并提交 .NET Core 版本的 SHA。</span><span class="sxs-lookup"><span data-stu-id="12fae-174">Prints out detailed information about a .NET Core installation and the machine environment, such as the current operating system, and commit SHA of the .NET Core version.</span></span>

`--runtimeconfig`

<span data-ttu-id="12fae-175">runtimeconfig.template.json 文件的路径  。</span><span class="sxs-lookup"><span data-stu-id="12fae-175">Path to a *runtimeconfig.json* file.</span></span>

<span data-ttu-id="12fae-176">runtimeconfig.template.json 文件是包含运行时配置设置的配置文件  。</span><span class="sxs-lookup"><span data-stu-id="12fae-176">A *runtimeconfig.json* file is a configuration file containing runtime configuration settings.</span></span> <span data-ttu-id="12fae-177">有关详细信息，请参阅 GitHub 上的[运行时配置文件](https://github.com/dotnet/cli/blob/master/Documentation/specs/runtime-configuration-file.md)。</span><span class="sxs-lookup"><span data-stu-id="12fae-177">For more details, see [Runtime Configuration Files on GitHub](https://github.com/dotnet/cli/blob/master/Documentation/specs/runtime-configuration-file.md).</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="12fae-178">设置命令的详细级别。</span><span class="sxs-lookup"><span data-stu-id="12fae-178">Sets the verbosity level of the command.</span></span> <span data-ttu-id="12fae-179">允许使用的值为 `q[uiet]`、`m[inimal]`、`n[ormal]`、`d[etailed]` 和 `diag[nostic]`。</span><span class="sxs-lookup"><span data-stu-id="12fae-179">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="12fae-180">并非在每个命令中均受支持；请参阅特定的命令页，确定此选项是否可用。</span><span class="sxs-lookup"><span data-stu-id="12fae-180">Not supported in every command; see specific command page to determine if this option is available.</span></span>

`--version`

<span data-ttu-id="12fae-181">打印使用中的 .NET Core SDK 版本。</span><span class="sxs-lookup"><span data-stu-id="12fae-181">Prints out the version of the .NET Core SDK in use.</span></span>

---

## <a name="dotnet-commands"></a><span data-ttu-id="12fae-182">dotnet 命令</span><span class="sxs-lookup"><span data-stu-id="12fae-182">dotnet commands</span></span>

### <a name="general"></a><span data-ttu-id="12fae-183">常规</span><span class="sxs-lookup"><span data-stu-id="12fae-183">General</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="12fae-184">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="12fae-184">.NET Core 2.1</span></span>](#tab/netcore21)

| <span data-ttu-id="12fae-185">命令</span><span class="sxs-lookup"><span data-stu-id="12fae-185">Command</span></span>                                       | <span data-ttu-id="12fae-186">函数</span><span class="sxs-lookup"><span data-stu-id="12fae-186">Function</span></span>                                                            |
| --------------------------------------------- | ------------------------------------------------------------------- |
| [<span data-ttu-id="12fae-187">dotnet build</span><span class="sxs-lookup"><span data-stu-id="12fae-187">dotnet build</span></span>](dotnet-build.md)               | <span data-ttu-id="12fae-188">生成 .NET Core 应用程序。</span><span class="sxs-lookup"><span data-stu-id="12fae-188">Builds a .NET Core application.</span></span>                                     |
| [<span data-ttu-id="12fae-189">dotnet build-server</span><span class="sxs-lookup"><span data-stu-id="12fae-189">dotnet build-server</span></span>](dotnet-build-server.md) | <span data-ttu-id="12fae-190">与通过生成启动的服务器进行交互。</span><span class="sxs-lookup"><span data-stu-id="12fae-190">Interacts with servers started by a build.</span></span>                          |
| [<span data-ttu-id="12fae-191">dotnet clean</span><span class="sxs-lookup"><span data-stu-id="12fae-191">dotnet clean</span></span>](dotnet-clean.md)               | <span data-ttu-id="12fae-192">清除生成输出。</span><span class="sxs-lookup"><span data-stu-id="12fae-192">Clean build outputs.</span></span>                                                |
| [<span data-ttu-id="12fae-193">dotnet help</span><span class="sxs-lookup"><span data-stu-id="12fae-193">dotnet help</span></span>](dotnet-help.md)                 | <span data-ttu-id="12fae-194">显示命令更详细的在线文档。</span><span class="sxs-lookup"><span data-stu-id="12fae-194">Shows more detailed documentation online for the command.</span></span>           |
| [<span data-ttu-id="12fae-195">dotnet migrate</span><span class="sxs-lookup"><span data-stu-id="12fae-195">dotnet migrate</span></span>](dotnet-migrate.md)           | <span data-ttu-id="12fae-196">将有效的预览版 2 项目迁移到 .NET Core SDK 1.0 项目。</span><span class="sxs-lookup"><span data-stu-id="12fae-196">Migrates a valid Preview 2 project to a .NET Core SDK 1.0 project.</span></span>  |
| [<span data-ttu-id="12fae-197">dotnet msbuild</span><span class="sxs-lookup"><span data-stu-id="12fae-197">dotnet msbuild</span></span>](dotnet-msbuild.md)           | <span data-ttu-id="12fae-198">提供对 MSBuild 命令行的访问权限。</span><span class="sxs-lookup"><span data-stu-id="12fae-198">Provides access to the MSBuild command line.</span></span>                        |
| [<span data-ttu-id="12fae-199">dotnet new</span><span class="sxs-lookup"><span data-stu-id="12fae-199">dotnet new</span></span>](dotnet-new.md)                   | <span data-ttu-id="12fae-200">为给定的模板初始化 C# 或 F# 项目。</span><span class="sxs-lookup"><span data-stu-id="12fae-200">Initializes a C# or F# project for a given template.</span></span>                |
| [<span data-ttu-id="12fae-201">dotnet pack</span><span class="sxs-lookup"><span data-stu-id="12fae-201">dotnet pack</span></span>](dotnet-pack.md)                 | <span data-ttu-id="12fae-202">创建代码的 NuGet 包。</span><span class="sxs-lookup"><span data-stu-id="12fae-202">Creates a NuGet package of your code.</span></span>                               |
| [<span data-ttu-id="12fae-203">dotnet publish</span><span class="sxs-lookup"><span data-stu-id="12fae-203">dotnet publish</span></span>](dotnet-publish.md)           | <span data-ttu-id="12fae-204">发布 .NET 依赖于框架或独立应用程序。</span><span class="sxs-lookup"><span data-stu-id="12fae-204">Publishes a .NET framework-dependent or self-contained application.</span></span> |
| [<span data-ttu-id="12fae-205">dotnet restore</span><span class="sxs-lookup"><span data-stu-id="12fae-205">dotnet restore</span></span>](dotnet-restore.md)           | <span data-ttu-id="12fae-206">还原给定应用程序的依赖项。</span><span class="sxs-lookup"><span data-stu-id="12fae-206">Restores the dependencies for a given application.</span></span>                  |
| [<span data-ttu-id="12fae-207">dotnet run</span><span class="sxs-lookup"><span data-stu-id="12fae-207">dotnet run</span></span>](dotnet-run.md)                   | <span data-ttu-id="12fae-208">从源运行应用程序。</span><span class="sxs-lookup"><span data-stu-id="12fae-208">Runs the application from source.</span></span>                                   |
| [<span data-ttu-id="12fae-209">dotnet sln</span><span class="sxs-lookup"><span data-stu-id="12fae-209">dotnet sln</span></span>](dotnet-sln.md)                   | <span data-ttu-id="12fae-210">用于添加、删除和列出解决方案文件中项目的选项。</span><span class="sxs-lookup"><span data-stu-id="12fae-210">Options to add, remove, and list projects in a solution file.</span></span>       |
| [<span data-ttu-id="12fae-211">dotnet store</span><span class="sxs-lookup"><span data-stu-id="12fae-211">dotnet store</span></span>](dotnet-store.md)               | <span data-ttu-id="12fae-212">将程序集存储到运行时包存储区。</span><span class="sxs-lookup"><span data-stu-id="12fae-212">Stores assemblies in the runtime package store.</span></span>                     |
| [<span data-ttu-id="12fae-213">dotnet test</span><span class="sxs-lookup"><span data-stu-id="12fae-213">dotnet test</span></span>](dotnet-test.md)                 | <span data-ttu-id="12fae-214">使用测试运行程序运行测试。</span><span class="sxs-lookup"><span data-stu-id="12fae-214">Runs tests using a test runner.</span></span>                                     |

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="12fae-215">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="12fae-215">.NET Core 2.0</span></span>](#tab/netcore20)

| <span data-ttu-id="12fae-216">命令</span><span class="sxs-lookup"><span data-stu-id="12fae-216">Command</span></span>                             | <span data-ttu-id="12fae-217">函数</span><span class="sxs-lookup"><span data-stu-id="12fae-217">Function</span></span>                                                            |
| ----------------------------------- | ------------------------------------------------------------------- |
| [<span data-ttu-id="12fae-218">dotnet build</span><span class="sxs-lookup"><span data-stu-id="12fae-218">dotnet build</span></span>](dotnet-build.md)     | <span data-ttu-id="12fae-219">生成 .NET Core 应用程序。</span><span class="sxs-lookup"><span data-stu-id="12fae-219">Builds a .NET Core application.</span></span>                                     |
| [<span data-ttu-id="12fae-220">dotnet clean</span><span class="sxs-lookup"><span data-stu-id="12fae-220">dotnet clean</span></span>](dotnet-clean.md)     | <span data-ttu-id="12fae-221">清除生成输出。</span><span class="sxs-lookup"><span data-stu-id="12fae-221">Clean build outputs.</span></span>                                              |
| [<span data-ttu-id="12fae-222">dotnet help</span><span class="sxs-lookup"><span data-stu-id="12fae-222">dotnet help</span></span>](dotnet-help.md)       | <span data-ttu-id="12fae-223">显示命令更详细的在线文档。</span><span class="sxs-lookup"><span data-stu-id="12fae-223">Shows more detailed documentation online for the command.</span></span>           |
| [<span data-ttu-id="12fae-224">dotnet migrate</span><span class="sxs-lookup"><span data-stu-id="12fae-224">dotnet migrate</span></span>](dotnet-migrate.md) | <span data-ttu-id="12fae-225">将有效的预览版 2 项目迁移到 .NET Core SDK 1.0 项目。</span><span class="sxs-lookup"><span data-stu-id="12fae-225">Migrates a valid Preview 2 project to a .NET Core SDK 1.0 project.</span></span>  |
| [<span data-ttu-id="12fae-226">dotnet msbuild</span><span class="sxs-lookup"><span data-stu-id="12fae-226">dotnet msbuild</span></span>](dotnet-msbuild.md) | <span data-ttu-id="12fae-227">提供对 MSBuild 命令行的访问权限。</span><span class="sxs-lookup"><span data-stu-id="12fae-227">Provides access to the MSBuild command line.</span></span>                        |
| [<span data-ttu-id="12fae-228">dotnet new</span><span class="sxs-lookup"><span data-stu-id="12fae-228">dotnet new</span></span>](dotnet-new.md)         | <span data-ttu-id="12fae-229">为给定的模板初始化 C# 或 F# 项目。</span><span class="sxs-lookup"><span data-stu-id="12fae-229">Initializes a C# or F# project for a given template.</span></span>                |
| [<span data-ttu-id="12fae-230">dotnet pack</span><span class="sxs-lookup"><span data-stu-id="12fae-230">dotnet pack</span></span>](dotnet-pack.md)       | <span data-ttu-id="12fae-231">创建代码的 NuGet 包。</span><span class="sxs-lookup"><span data-stu-id="12fae-231">Creates a NuGet package of your code.</span></span>                               |
| [<span data-ttu-id="12fae-232">dotnet publish</span><span class="sxs-lookup"><span data-stu-id="12fae-232">dotnet publish</span></span>](dotnet-publish.md) | <span data-ttu-id="12fae-233">发布 .NET 依赖于框架或独立应用程序。</span><span class="sxs-lookup"><span data-stu-id="12fae-233">Publishes a .NET framework-dependent or self-contained application.</span></span> |
| [<span data-ttu-id="12fae-234">dotnet restore</span><span class="sxs-lookup"><span data-stu-id="12fae-234">dotnet restore</span></span>](dotnet-restore.md) | <span data-ttu-id="12fae-235">还原给定应用程序的依赖项。</span><span class="sxs-lookup"><span data-stu-id="12fae-235">Restores the dependencies for a given application.</span></span>                  |
| [<span data-ttu-id="12fae-236">dotnet run</span><span class="sxs-lookup"><span data-stu-id="12fae-236">dotnet run</span></span>](dotnet-run.md)         | <span data-ttu-id="12fae-237">从源运行应用程序。</span><span class="sxs-lookup"><span data-stu-id="12fae-237">Runs the application from source.</span></span>                                   |
| [<span data-ttu-id="12fae-238">dotnet sln</span><span class="sxs-lookup"><span data-stu-id="12fae-238">dotnet sln</span></span>](dotnet-sln.md)         | <span data-ttu-id="12fae-239">用于添加、删除和列出解决方案文件中项目的选项。</span><span class="sxs-lookup"><span data-stu-id="12fae-239">Options to add, remove, and list projects in a solution file.</span></span>       |
| [<span data-ttu-id="12fae-240">dotnet store</span><span class="sxs-lookup"><span data-stu-id="12fae-240">dotnet store</span></span>](dotnet-store.md)     | <span data-ttu-id="12fae-241">将程序集存储到运行时包存储区。</span><span class="sxs-lookup"><span data-stu-id="12fae-241">Stores assemblies in the runtime package store.</span></span>                     |
| [<span data-ttu-id="12fae-242">dotnet test</span><span class="sxs-lookup"><span data-stu-id="12fae-242">dotnet test</span></span>](dotnet-test.md)       | <span data-ttu-id="12fae-243">使用测试运行程序运行测试。</span><span class="sxs-lookup"><span data-stu-id="12fae-243">Runs tests using a test runner.</span></span>                                     |

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="12fae-244">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="12fae-244">.NET Core 1.x</span></span>](#tab/netcore1x)

| <span data-ttu-id="12fae-245">命令</span><span class="sxs-lookup"><span data-stu-id="12fae-245">Command</span></span>                             | <span data-ttu-id="12fae-246">函数</span><span class="sxs-lookup"><span data-stu-id="12fae-246">Function</span></span>                                                            |
| ----------------------------------- | ------------------------------------------------------------------- |
| [<span data-ttu-id="12fae-247">dotnet build</span><span class="sxs-lookup"><span data-stu-id="12fae-247">dotnet build</span></span>](dotnet-build.md)     | <span data-ttu-id="12fae-248">生成 .NET Core 应用程序。</span><span class="sxs-lookup"><span data-stu-id="12fae-248">Builds a .NET Core application.</span></span>                                     |
| [<span data-ttu-id="12fae-249">dotnet clean</span><span class="sxs-lookup"><span data-stu-id="12fae-249">dotnet clean</span></span>](dotnet-clean.md)     | <span data-ttu-id="12fae-250">清除生成输出。</span><span class="sxs-lookup"><span data-stu-id="12fae-250">Clean build outputs.</span></span>                                              |
| [<span data-ttu-id="12fae-251">dotnet migrate</span><span class="sxs-lookup"><span data-stu-id="12fae-251">dotnet migrate</span></span>](dotnet-migrate.md) | <span data-ttu-id="12fae-252">将有效的预览版 2 项目迁移到 .NET Core SDK 1.0 项目。</span><span class="sxs-lookup"><span data-stu-id="12fae-252">Migrates a valid Preview 2 project to a .NET Core SDK 1.0 project.</span></span>  |
| [<span data-ttu-id="12fae-253">dotnet msbuild</span><span class="sxs-lookup"><span data-stu-id="12fae-253">dotnet msbuild</span></span>](dotnet-msbuild.md) | <span data-ttu-id="12fae-254">提供对 MSBuild 命令行的访问权限。</span><span class="sxs-lookup"><span data-stu-id="12fae-254">Provides access to the MSBuild command line.</span></span>                        |
| [<span data-ttu-id="12fae-255">dotnet new</span><span class="sxs-lookup"><span data-stu-id="12fae-255">dotnet new</span></span>](dotnet-new.md)         | <span data-ttu-id="12fae-256">为给定的模板初始化 C# 或 F# 项目。</span><span class="sxs-lookup"><span data-stu-id="12fae-256">Initializes a C# or F# project for a given template.</span></span>                |
| [<span data-ttu-id="12fae-257">dotnet pack</span><span class="sxs-lookup"><span data-stu-id="12fae-257">dotnet pack</span></span>](dotnet-pack.md)       | <span data-ttu-id="12fae-258">创建代码的 NuGet 包。</span><span class="sxs-lookup"><span data-stu-id="12fae-258">Creates a NuGet package of your code.</span></span>                               |
| [<span data-ttu-id="12fae-259">dotnet publish</span><span class="sxs-lookup"><span data-stu-id="12fae-259">dotnet publish</span></span>](dotnet-publish.md) | <span data-ttu-id="12fae-260">发布 .NET 依赖于框架或独立应用程序。</span><span class="sxs-lookup"><span data-stu-id="12fae-260">Publishes a .NET framework-dependent or self-contained application.</span></span> |
| [<span data-ttu-id="12fae-261">dotnet restore</span><span class="sxs-lookup"><span data-stu-id="12fae-261">dotnet restore</span></span>](dotnet-restore.md) | <span data-ttu-id="12fae-262">还原给定应用程序的依赖项。</span><span class="sxs-lookup"><span data-stu-id="12fae-262">Restores the dependencies for a given application.</span></span>                  |
| [<span data-ttu-id="12fae-263">dotnet run</span><span class="sxs-lookup"><span data-stu-id="12fae-263">dotnet run</span></span>](dotnet-run.md)         | <span data-ttu-id="12fae-264">从源运行应用程序。</span><span class="sxs-lookup"><span data-stu-id="12fae-264">Runs the application from source.</span></span>                                   |
| [<span data-ttu-id="12fae-265">dotnet sln</span><span class="sxs-lookup"><span data-stu-id="12fae-265">dotnet sln</span></span>](dotnet-sln.md)         | <span data-ttu-id="12fae-266">用于添加、删除和列出解决方案文件中项目的选项。</span><span class="sxs-lookup"><span data-stu-id="12fae-266">Options to add, remove, and list projects in a solution file.</span></span>       |
| [<span data-ttu-id="12fae-267">dotnet test</span><span class="sxs-lookup"><span data-stu-id="12fae-267">dotnet test</span></span>](dotnet-test.md)       | <span data-ttu-id="12fae-268">使用测试运行程序运行测试。</span><span class="sxs-lookup"><span data-stu-id="12fae-268">Runs tests using a test runner.</span></span>                                     |

---

### <a name="project-references"></a><span data-ttu-id="12fae-269">项目引用</span><span class="sxs-lookup"><span data-stu-id="12fae-269">Project references</span></span>

<span data-ttu-id="12fae-270">命令</span><span class="sxs-lookup"><span data-stu-id="12fae-270">Command</span></span> | <span data-ttu-id="12fae-271">函数</span><span class="sxs-lookup"><span data-stu-id="12fae-271">Function</span></span>
--- | ---
[<span data-ttu-id="12fae-272">dotnet add reference</span><span class="sxs-lookup"><span data-stu-id="12fae-272">dotnet add reference</span></span>](dotnet-add-reference.md) | <span data-ttu-id="12fae-273">添加项目引用。</span><span class="sxs-lookup"><span data-stu-id="12fae-273">Adds a project reference.</span></span>
[<span data-ttu-id="12fae-274">dotnet list reference</span><span class="sxs-lookup"><span data-stu-id="12fae-274">dotnet list reference</span></span>](dotnet-list-reference.md) | <span data-ttu-id="12fae-275">列出项目引用。</span><span class="sxs-lookup"><span data-stu-id="12fae-275">Lists project references.</span></span>
[<span data-ttu-id="12fae-276">dotnet remove reference</span><span class="sxs-lookup"><span data-stu-id="12fae-276">dotnet remove reference</span></span>](dotnet-remove-reference.md) | <span data-ttu-id="12fae-277">删除项目引用。</span><span class="sxs-lookup"><span data-stu-id="12fae-277">Removes a project reference.</span></span>

### <a name="nuget-packages"></a><span data-ttu-id="12fae-278">NuGet 包</span><span class="sxs-lookup"><span data-stu-id="12fae-278">NuGet packages</span></span>

<span data-ttu-id="12fae-279">命令</span><span class="sxs-lookup"><span data-stu-id="12fae-279">Command</span></span> | <span data-ttu-id="12fae-280">函数</span><span class="sxs-lookup"><span data-stu-id="12fae-280">Function</span></span>
--- | ---
[<span data-ttu-id="12fae-281">dotnet add package</span><span class="sxs-lookup"><span data-stu-id="12fae-281">dotnet add package</span></span>](dotnet-add-package.md) | <span data-ttu-id="12fae-282">添加 NuGet 包。</span><span class="sxs-lookup"><span data-stu-id="12fae-282">Adds a NuGet package.</span></span>
[<span data-ttu-id="12fae-283">dotnet remove package</span><span class="sxs-lookup"><span data-stu-id="12fae-283">dotnet remove package</span></span>](dotnet-remove-package.md) | <span data-ttu-id="12fae-284">删除 NuGet 包。</span><span class="sxs-lookup"><span data-stu-id="12fae-284">Removes a NuGet package.</span></span>

### <a name="nuget-commands"></a><span data-ttu-id="12fae-285">NuGet 命令</span><span class="sxs-lookup"><span data-stu-id="12fae-285">NuGet commands</span></span>

<span data-ttu-id="12fae-286">命令</span><span class="sxs-lookup"><span data-stu-id="12fae-286">Command</span></span> | <span data-ttu-id="12fae-287">函数</span><span class="sxs-lookup"><span data-stu-id="12fae-287">Function</span></span>
--- | ---
[<span data-ttu-id="12fae-288">dotnet nuget delete</span><span class="sxs-lookup"><span data-stu-id="12fae-288">dotnet nuget delete</span></span>](dotnet-nuget-delete.md) | <span data-ttu-id="12fae-289">从服务器删除或取消列出包。</span><span class="sxs-lookup"><span data-stu-id="12fae-289">Deletes or unlists a package from the server.</span></span>
[<span data-ttu-id="12fae-290">dotnet nuget locals</span><span class="sxs-lookup"><span data-stu-id="12fae-290">dotnet nuget locals</span></span>](dotnet-nuget-locals.md) | <span data-ttu-id="12fae-291">清除或列出本地 NuGet 资源，例如 http 请求缓存、临时缓存或计算机范围的全局包文件夹。</span><span class="sxs-lookup"><span data-stu-id="12fae-291">Clears or lists local NuGet resources such as http-request cache, temporary cache, or machine-wide global packages folder.</span></span>
[<span data-ttu-id="12fae-292">dotnet nuget push</span><span class="sxs-lookup"><span data-stu-id="12fae-292">dotnet nuget push</span></span>](dotnet-nuget-push.md) | <span data-ttu-id="12fae-293">将包推送到服务器，并将其发布。</span><span class="sxs-lookup"><span data-stu-id="12fae-293">Pushes a package to the server and publishes it.</span></span>

### <a name="global-tools-commands"></a><span data-ttu-id="12fae-294">全局工具命令</span><span class="sxs-lookup"><span data-stu-id="12fae-294">Global Tools commands</span></span>

<span data-ttu-id="12fae-295">[.NET Core 全局工具](global-tools.md)可与 .NET Core SDK 2.1.300 一起开始使用：</span><span class="sxs-lookup"><span data-stu-id="12fae-295">[.NET Core Global Tools](global-tools.md) are available starting with .NET Core SDK 2.1.300:</span></span>

<span data-ttu-id="12fae-296">命令</span><span class="sxs-lookup"><span data-stu-id="12fae-296">Command</span></span> | <span data-ttu-id="12fae-297">函数</span><span class="sxs-lookup"><span data-stu-id="12fae-297">Function</span></span>
--- | ---
[<span data-ttu-id="12fae-298">dotnet tool install</span><span class="sxs-lookup"><span data-stu-id="12fae-298">dotnet tool install</span></span>](dotnet-tool-install.md) | <span data-ttu-id="12fae-299">在计算机上安装全局工具。</span><span class="sxs-lookup"><span data-stu-id="12fae-299">Installs a Global Tool on your machine.</span></span>
[<span data-ttu-id="12fae-300">dotnet tool list</span><span class="sxs-lookup"><span data-stu-id="12fae-300">dotnet tool list</span></span>](dotnet-tool-list.md) | <span data-ttu-id="12fae-301">列出当前安装在计算机上的默认目录中或指定路径中的所有全局工具。</span><span class="sxs-lookup"><span data-stu-id="12fae-301">Lists all Global Tools currently installed in the default directory on your machine or in the specified path.</span></span>
[<span data-ttu-id="12fae-302">dotnet tool uninstall</span><span class="sxs-lookup"><span data-stu-id="12fae-302">dotnet tool uninstall</span></span>](dotnet-tool-uninstall.md) | <span data-ttu-id="12fae-303">从计算机中卸载全局工具。</span><span class="sxs-lookup"><span data-stu-id="12fae-303">Uninstalls a Global Tool from your machine.</span></span>
[<span data-ttu-id="12fae-304">dotnet tool update</span><span class="sxs-lookup"><span data-stu-id="12fae-304">dotnet tool update</span></span>](dotnet-tool-update.md) | <span data-ttu-id="12fae-305">在计算机上更新全局工具。</span><span class="sxs-lookup"><span data-stu-id="12fae-305">Updates a Global Tool on your machine.</span></span>

### <a name="additional-tools"></a><span data-ttu-id="12fae-306">其他工具</span><span class="sxs-lookup"><span data-stu-id="12fae-306">Additional tools</span></span>

<span data-ttu-id="12fae-307">自 .NET Core SDK 2.1.300 开始，许多使用 `DotnetCliToolReference` 的仅在每个项目的基础上可用的工具现作为 .NET Core SDK 的一部分提供。</span><span class="sxs-lookup"><span data-stu-id="12fae-307">Starting with .NET Core SDK 2.1.300, a number of tools that were available only on a per project basis using `DotnetCliToolReference` are now available as part of the .NET Core SDK.</span></span> <span data-ttu-id="12fae-308">下表中列出了这些工具：</span><span class="sxs-lookup"><span data-stu-id="12fae-308">These tools are listed in the following table:</span></span>

| <span data-ttu-id="12fae-309">工具</span><span class="sxs-lookup"><span data-stu-id="12fae-309">Tool</span></span>                                              | <span data-ttu-id="12fae-310">函数</span><span class="sxs-lookup"><span data-stu-id="12fae-310">Function</span></span>                                                     |
| ------------------------------------------------- | ------------------------------------------------------------ |
| <span data-ttu-id="12fae-311">dev-certs</span><span class="sxs-lookup"><span data-stu-id="12fae-311">dev-certs</span></span>                                         | <span data-ttu-id="12fae-312">创建和管理开发证书。</span><span class="sxs-lookup"><span data-stu-id="12fae-312">Creates and manages development certificates.</span></span>                |
| [<span data-ttu-id="12fae-313">ef</span><span class="sxs-lookup"><span data-stu-id="12fae-313">ef</span></span>](/ef/core/miscellaneous/cli/dotnet)           | <span data-ttu-id="12fae-314">Entity Framework Core 命令行工具。</span><span class="sxs-lookup"><span data-stu-id="12fae-314">Entity Framework Core command-line tools.</span></span>                    |
| <span data-ttu-id="12fae-315">sql-cache</span><span class="sxs-lookup"><span data-stu-id="12fae-315">sql-cache</span></span>                                         | <span data-ttu-id="12fae-316">SQL Server 缓存命令行工具。</span><span class="sxs-lookup"><span data-stu-id="12fae-316">SQL Server cache command-line tools.</span></span>                         |
| [<span data-ttu-id="12fae-317">user-secrets</span><span class="sxs-lookup"><span data-stu-id="12fae-317">user-secrets</span></span>](/aspnet/core/security/app-secrets) | <span data-ttu-id="12fae-318">管理开发用户机密。</span><span class="sxs-lookup"><span data-stu-id="12fae-318">Manages development user secrets.</span></span>                            |
| [<span data-ttu-id="12fae-319">watch</span><span class="sxs-lookup"><span data-stu-id="12fae-319">watch</span></span>](/aspnet/core/tutorials/dotnet-watch)      | <span data-ttu-id="12fae-320">启动文件观察程序，以在更改文件时运行命令。</span><span class="sxs-lookup"><span data-stu-id="12fae-320">Starts a file watcher that runs a command when files change.</span></span> |

<span data-ttu-id="12fae-321">有关每个工具的详细信息，请键入 `dotnet <tool-name> --help`。</span><span class="sxs-lookup"><span data-stu-id="12fae-321">For more information about each tool, type `dotnet <tool-name> --help`.</span></span>

## <a name="examples"></a><span data-ttu-id="12fae-322">示例</span><span class="sxs-lookup"><span data-stu-id="12fae-322">Examples</span></span>

<span data-ttu-id="12fae-323">创建新的 .NET Core 控制台应用程序：</span><span class="sxs-lookup"><span data-stu-id="12fae-323">Creates a new .NET Core console application:</span></span>

`dotnet new console`

<span data-ttu-id="12fae-324">还原给定应用程序的依赖项：</span><span class="sxs-lookup"><span data-stu-id="12fae-324">Restore dependencies for a given application:</span></span>

`dotnet restore`

[!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]

<span data-ttu-id="12fae-325">生成给定目录中的项目及其依赖项：</span><span class="sxs-lookup"><span data-stu-id="12fae-325">Build a project and its dependencies in a given directory:</span></span>

`dotnet build`

<span data-ttu-id="12fae-326">运行应用程序 DLL，如 `myapp.dll`：</span><span class="sxs-lookup"><span data-stu-id="12fae-326">Run an application DLL, such as `myapp.dll`:</span></span>

`dotnet myapp.dll`

## <a name="environment-variables"></a><span data-ttu-id="12fae-327">环境变量</span><span class="sxs-lookup"><span data-stu-id="12fae-327">Environment variables</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="12fae-328">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="12fae-328">.NET Core 2.1</span></span>](#tab/netcore21)

`DOTNET_PACKAGES`

<span data-ttu-id="12fae-329">全局包文件夹。</span><span class="sxs-lookup"><span data-stu-id="12fae-329">The global packages folder.</span></span> <span data-ttu-id="12fae-330">如果未设置，则默认为 Unix 上的 `~/.nuget/packages` 或 Windows 上的 `%userprofile%\.nuget\packages`。</span><span class="sxs-lookup"><span data-stu-id="12fae-330">If not set, it defaults to `~/.nuget/packages` on Unix or `%userprofile%\.nuget\packages` on Windows.</span></span>

`DOTNET_SERVICING`

<span data-ttu-id="12fae-331">指定加载运行时期间共享主机要使用的服务索引的位置。</span><span class="sxs-lookup"><span data-stu-id="12fae-331">Specifies the location of the servicing index to use by the shared host when loading the runtime.</span></span>

`DOTNET_CLI_TELEMETRY_OPTOUT`

<span data-ttu-id="12fae-332">指定是否收集并向 Microsoft 发送 .NET Core 工具使用情况的相关数据。</span><span class="sxs-lookup"><span data-stu-id="12fae-332">Specifies whether data about the .NET Core tools usage is collected and sent to Microsoft.</span></span> <span data-ttu-id="12fae-333">设置为 `true` 以选择退出遥测功能（接受的值为 `true`、`1` 或 `yes`）。</span><span class="sxs-lookup"><span data-stu-id="12fae-333">Set to `true` to opt-out of the telemetry feature (values `true`, `1`, or `yes` accepted).</span></span> <span data-ttu-id="12fae-334">否则，设置为 `false` 以选择加入遥测功能（接受的值为 `false`、`0` 或 `no`）。</span><span class="sxs-lookup"><span data-stu-id="12fae-334">Otherwise, set to `false` to opt into the telemetry features (values `false`, `0`, or `no` accepted).</span></span> <span data-ttu-id="12fae-335">如果未设置，则默认为 `false` 且遥测功能为活动状态。</span><span class="sxs-lookup"><span data-stu-id="12fae-335">If not set, the default is `false` and the telemetry feature is active.</span></span>

`DOTNET_MULTILEVEL_LOOKUP`

<span data-ttu-id="12fae-336">指定是否从全局位置解析 .NET Core 运行时、共享框架或 SDK。</span><span class="sxs-lookup"><span data-stu-id="12fae-336">Specifies whether .NET Core runtime, shared framework, or SDK are resolved from the global location.</span></span> <span data-ttu-id="12fae-337">如果未设置，则默认为 `true`。</span><span class="sxs-lookup"><span data-stu-id="12fae-337">If not set, it defaults to `true`.</span></span> <span data-ttu-id="12fae-338">设置为 `false` 不从全局位置解析，并且具有独立的 .NET Core 安装（接受的值为 `0` 或 `false`）。</span><span class="sxs-lookup"><span data-stu-id="12fae-338">Set to `false` to not resolve from the global location and have isolated .NET Core installations (values `0` or `false` are accepted).</span></span> <span data-ttu-id="12fae-339">有关多级别查找的详细信息，请参阅 [Multi-level SharedFX Lookup](https://github.com/dotnet/core-setup/blob/master/Documentation/design-docs/multilevel-sharedfx-lookup.md)（多级别 SharedFX 查找）。</span><span class="sxs-lookup"><span data-stu-id="12fae-339">For more information about multi-level lookup, see [Multi-level SharedFX Lookup](https://github.com/dotnet/core-setup/blob/master/Documentation/design-docs/multilevel-sharedfx-lookup.md).</span></span>

`DOTNET_ROLL_FORWARD_ON_NO_CANDIDATE_FX`

<span data-ttu-id="12fae-340">如果设置为 `0`，则禁用次要版本前滚。</span><span class="sxs-lookup"><span data-stu-id="12fae-340">Disables minor version roll forward, if set to `0`.</span></span> <span data-ttu-id="12fae-341">有关详细信息，请参阅[前滚](../whats-new/dotnet-core-2-1.md#roll-forward)。</span><span class="sxs-lookup"><span data-stu-id="12fae-341">For more information, see [Roll forward](../whats-new/dotnet-core-2-1.md#roll-forward).</span></span>

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="12fae-342">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="12fae-342">.NET Core 2.0</span></span>](#tab/netcore20)

`DOTNET_PACKAGES`

<span data-ttu-id="12fae-343">主包缓存。</span><span class="sxs-lookup"><span data-stu-id="12fae-343">The primary package cache.</span></span> <span data-ttu-id="12fae-344">如果未设置，则默认为 Unix 上的 `$HOME/.nuget/packages` 或 Windows 上的 `%userprofile%\.nuget\packages`。</span><span class="sxs-lookup"><span data-stu-id="12fae-344">If not set, it defaults to `$HOME/.nuget/packages` on Unix or `%userprofile%\.nuget\packages` on Windows.</span></span>

`DOTNET_SERVICING`

<span data-ttu-id="12fae-345">指定加载运行时期间共享主机要使用的服务索引的位置。</span><span class="sxs-lookup"><span data-stu-id="12fae-345">Specifies the location of the servicing index to use by the shared host when loading the runtime.</span></span>

`DOTNET_CLI_TELEMETRY_OPTOUT`

<span data-ttu-id="12fae-346">指定是否收集并向 Microsoft 发送 .NET Core 工具使用情况的相关数据。</span><span class="sxs-lookup"><span data-stu-id="12fae-346">Specifies whether data about the .NET Core tools usage is collected and sent to Microsoft.</span></span> <span data-ttu-id="12fae-347">设置为 `true` 以选择退出遥测功能（接受的值为 `true`、`1` 或 `yes`）。</span><span class="sxs-lookup"><span data-stu-id="12fae-347">Set to `true` to opt-out of the telemetry feature (values `true`, `1`, or `yes` accepted).</span></span> <span data-ttu-id="12fae-348">否则，设置为 `false` 以选择加入遥测功能（接受的值为 `false`、`0` 或 `no`）。</span><span class="sxs-lookup"><span data-stu-id="12fae-348">Otherwise, set to `false` to opt into the telemetry features (values `false`, `0`, or `no` accepted).</span></span> <span data-ttu-id="12fae-349">如果未设置，则默认为 `false` 且遥测功能为活动状态。</span><span class="sxs-lookup"><span data-stu-id="12fae-349">If not set, the default is `false` and the telemetry feature is active.</span></span>

`DOTNET_MULTILEVEL_LOOKUP`

<span data-ttu-id="12fae-350">指定是否从全局位置解析 .NET Core 运行时、共享框架或 SDK。</span><span class="sxs-lookup"><span data-stu-id="12fae-350">Specifies whether .NET Core runtime, shared framework, or SDK are resolved from the global location.</span></span> <span data-ttu-id="12fae-351">如果未设置，则默认为 `true`。</span><span class="sxs-lookup"><span data-stu-id="12fae-351">If not set, it defaults to `true`.</span></span> <span data-ttu-id="12fae-352">设置为 `false` 不从全局位置解析，并且具有独立的 .NET Core 安装（接受的值为 `0` 或 `false`）。</span><span class="sxs-lookup"><span data-stu-id="12fae-352">Set to `false` to not resolve from the global location and have isolated .NET Core installations (values `0` or `false` are accepted).</span></span> <span data-ttu-id="12fae-353">有关多级别查找的详细信息，请参阅 [Multi-level SharedFX Lookup](https://github.com/dotnet/core-setup/blob/master/Documentation/design-docs/multilevel-sharedfx-lookup.md)（多级别 SharedFX 查找）。</span><span class="sxs-lookup"><span data-stu-id="12fae-353">For more information about multi-level lookup, see [Multi-level SharedFX Lookup](https://github.com/dotnet/core-setup/blob/master/Documentation/design-docs/multilevel-sharedfx-lookup.md).</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="12fae-354">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="12fae-354">.NET Core 1.x</span></span>](#tab/netcore1x)

`DOTNET_PACKAGES`

<span data-ttu-id="12fae-355">主包缓存。</span><span class="sxs-lookup"><span data-stu-id="12fae-355">The primary package cache.</span></span> <span data-ttu-id="12fae-356">如果未设置，则默认为 Unix 上的 `$HOME/.nuget/packages` 或 Windows 上的 `%userprofile%\.nuget\packages`。</span><span class="sxs-lookup"><span data-stu-id="12fae-356">If not set, it defaults to `$HOME/.nuget/packages` on Unix or `%userprofile%\.nuget\packages` on Windows.</span></span>

`DOTNET_SERVICING`

<span data-ttu-id="12fae-357">指定加载运行时期间共享主机要使用的服务索引的位置。</span><span class="sxs-lookup"><span data-stu-id="12fae-357">Specifies the location of the servicing index to use by the shared host when loading the runtime.</span></span>

`DOTNET_CLI_TELEMETRY_OPTOUT`

<span data-ttu-id="12fae-358">指定是否收集并向 Microsoft 发送 .NET Core 工具使用情况的相关数据。</span><span class="sxs-lookup"><span data-stu-id="12fae-358">Specifies whether data about the .NET Core tools usage is collected and sent to Microsoft.</span></span> <span data-ttu-id="12fae-359">设置为 `true` 以选择退出遥测功能（接受的值为 `true`、`1` 或 `yes`）。</span><span class="sxs-lookup"><span data-stu-id="12fae-359">Set to `true` to opt-out of the telemetry feature (values `true`, `1`, or `yes` accepted).</span></span> <span data-ttu-id="12fae-360">否则，设置为 `false` 以选择加入遥测功能（接受的值为 `false`、`0` 或 `no`）。</span><span class="sxs-lookup"><span data-stu-id="12fae-360">Otherwise, set to `false` to opt into the telemetry features (values `false`, `0`, or `no` accepted).</span></span> <span data-ttu-id="12fae-361">如果未设置，则默认为 `false` 且遥测功能为活动状态。</span><span class="sxs-lookup"><span data-stu-id="12fae-361">If not set, the default is `false` and the telemetry feature is active.</span></span>

---

## <a name="see-also"></a><span data-ttu-id="12fae-362">请参阅</span><span class="sxs-lookup"><span data-stu-id="12fae-362">See also</span></span>

- [<span data-ttu-id="12fae-363">运行时配置文件</span><span class="sxs-lookup"><span data-stu-id="12fae-363">Runtime Configuration Files</span></span>](https://github.com/dotnet/cli/blob/master/Documentation/specs/runtime-configuration-file.md)
