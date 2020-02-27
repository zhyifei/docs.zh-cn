---
title: dotnet 命令
description: 了解 dotnet 命令（.NET Core CLI 的通用驱动程序）及其用法。
ms.date: 02/13/2020
ms.openlocfilehash: 364978465b63401907b46ead64dbceb2f15c8169
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "77451163"
---
# <a name="dotnet-command"></a><span data-ttu-id="2f9d4-103">dotnet 命令</span><span class="sxs-lookup"><span data-stu-id="2f9d4-103">dotnet command</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="2f9d4-104">“属性”</span><span class="sxs-lookup"><span data-stu-id="2f9d4-104">Name</span></span>

<span data-ttu-id="2f9d4-105">`dotnet` - 一款管理 .NET 源代码和二进制文件的工具。</span><span class="sxs-lookup"><span data-stu-id="2f9d4-105">`dotnet` - A tool for managing .NET source code and binaries.</span></span>

## <a name="synopsis"></a><span data-ttu-id="2f9d4-106">摘要</span><span class="sxs-lookup"><span data-stu-id="2f9d4-106">Synopsis</span></span>

<!-- markdownlint-disable MD025 -->

# <a name="net-core-21"></a>[<span data-ttu-id="2f9d4-107">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="2f9d4-107">.NET Core 2.1</span></span>](#tab/netcore21)

```dotnetcli
dotnet [command] [arguments] [--additional-deps] [--additionalprobingpath] [--depsfile]
    [-d|--diagnostics] [--fx-version] [-h|--help] [--info] [--list-runtimes] [--list-sdks] [--roll-forward-on-no-candidate-fx] [--runtimeconfig] [-v|--verbosity] [--version]
```

# <a name="net-core-20"></a>[<span data-ttu-id="2f9d4-108">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="2f9d4-108">.NET Core 2.0</span></span>](#tab/netcore20)

```dotnetcli
dotnet [command] [arguments] [--additional-deps] [--additionalprobingpath] [--depsfile]
    [-d|--diagnostics] [--fx-version] [-h|--help] [--info] [--roll-forward-on-no-candidate-fx]
    [--runtimeconfig] [-v|--verbosity] [--version]
```

# <a name="net-core-1x"></a>[<span data-ttu-id="2f9d4-109">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="2f9d4-109">.NET Core 1.x</span></span>](#tab/netcore1x)

```dotnetcli
dotnet [command] [arguments] [--additionalprobingpath] [--depsfile] [-d|--diagnostics]
    [--fx-version] [-h|--help] [--info] [--runtimeconfig] [-v|--verbosity] [--version]
```

---

## <a name="description"></a><span data-ttu-id="2f9d4-110">描述</span><span class="sxs-lookup"><span data-stu-id="2f9d4-110">Description</span></span>

<span data-ttu-id="2f9d4-111">`dotnet` 是一款管理 .NET 源代码和二进制文件的工具。</span><span class="sxs-lookup"><span data-stu-id="2f9d4-111">`dotnet` is a tool for managing .NET source code and binaries.</span></span> <span data-ttu-id="2f9d4-112">它公开执行特定任务的命令，例如 [`dotnet build`](dotnet-build.md) 和 [`dotnet run`](dotnet-run.md)。</span><span class="sxs-lookup"><span data-stu-id="2f9d4-112">It exposes commands that perform specific tasks, such as [`dotnet build`](dotnet-build.md) and [`dotnet run`](dotnet-run.md).</span></span> <span data-ttu-id="2f9d4-113">每个命令都定义自己的参数。</span><span class="sxs-lookup"><span data-stu-id="2f9d4-113">Each command defines its own arguments.</span></span> <span data-ttu-id="2f9d4-114">在每个命令后键入 `--help` 以访问简要帮助文档。</span><span class="sxs-lookup"><span data-stu-id="2f9d4-114">Type `--help` after each command to access brief help documentation.</span></span>

<span data-ttu-id="2f9d4-115">可以使用 `dotnet` 来运行应用程序，方法是指定应用程序 DLL，如 `dotnet myapp.dll`.</span><span class="sxs-lookup"><span data-stu-id="2f9d4-115">`dotnet` can be used to run applications, by specifying an application DLL, such as `dotnet myapp.dll`.</span></span> <span data-ttu-id="2f9d4-116">要了解部署选项，请参阅 [.NET Core 应用程序部署](../deploying/index.md)。</span><span class="sxs-lookup"><span data-stu-id="2f9d4-116">See [.NET Core application deployment](../deploying/index.md) for to learn about deployment options.</span></span>

## <a name="options"></a><span data-ttu-id="2f9d4-117">选项</span><span class="sxs-lookup"><span data-stu-id="2f9d4-117">Options</span></span>

# <a name="net-core-21"></a>[<span data-ttu-id="2f9d4-118">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="2f9d4-118">.NET Core 2.1</span></span>](#tab/netcore21)

`--additional-deps <PATH>`

<span data-ttu-id="2f9d4-119">附加 .deps.json 文件的路径  。</span><span class="sxs-lookup"><span data-stu-id="2f9d4-119">Path to an additional *.deps.json* file.</span></span>

`--additionalprobingpath <PATH>`

<span data-ttu-id="2f9d4-120">包含要进行探测的探测策略和程序集的路径。</span><span class="sxs-lookup"><span data-stu-id="2f9d4-120">Path containing probing policy and assemblies to probe.</span></span>

`--depsfile`

<span data-ttu-id="2f9d4-121">deps.json 文件的路径  。</span><span class="sxs-lookup"><span data-stu-id="2f9d4-121">Path to a *deps.json* file.</span></span>

<span data-ttu-id="2f9d4-122">deps.json 文件包含依赖项、编译依赖项和用于解决程序集冲突的版本信息列表  。</span><span class="sxs-lookup"><span data-stu-id="2f9d4-122">A *deps.json* file contains a list of dependencies, compilation dependencies, and version information used to address assembly conflicts.</span></span> <span data-ttu-id="2f9d4-123">有关此文件的详细信息，请参阅 GitHub 上的[运行时配置文件](https://github.com/dotnet/cli/blob/master/Documentation/specs/runtime-configuration-file.md)。</span><span class="sxs-lookup"><span data-stu-id="2f9d4-123">For more information about this file, see [Runtime Configuration Files](https://github.com/dotnet/cli/blob/master/Documentation/specs/runtime-configuration-file.md) on GitHub.</span></span>

`-d|--diagnostics`

<span data-ttu-id="2f9d4-124">启用诊断输出。</span><span class="sxs-lookup"><span data-stu-id="2f9d4-124">Enables diagnostic output.</span></span>

`--fx-version <VERSION>`

<span data-ttu-id="2f9d4-125">用于运行应用程序的 .NET Core 运行时版本。</span><span class="sxs-lookup"><span data-stu-id="2f9d4-125">Version of the .NET Core runtime to use to run the application.</span></span>

`-h|--help`

<span data-ttu-id="2f9d4-126">打印出给定命令的文档，如 `dotnet build --help`。</span><span class="sxs-lookup"><span data-stu-id="2f9d4-126">Prints out documentation for a given command, such as `dotnet build --help`.</span></span> <span data-ttu-id="2f9d4-127">`dotnet --help` 打印可用命令列表。</span><span class="sxs-lookup"><span data-stu-id="2f9d4-127">`dotnet --help` prints a list of available commands.</span></span>

`--info`

<span data-ttu-id="2f9d4-128">打印出有关 .NET Core 安装和计算机环境（如当前操作系统）的详细信息，并提交 .NET Core 版本的 SHA。</span><span class="sxs-lookup"><span data-stu-id="2f9d4-128">Prints out detailed information about a .NET Core installation and the machine environment, such as the current operating system, and commit SHA of the .NET Core version.</span></span>

`--list-runtimes`

<span data-ttu-id="2f9d4-129">显示已安装的 .NET Core 运行时。</span><span class="sxs-lookup"><span data-stu-id="2f9d4-129">Displays the installed .NET Core runtimes.</span></span>

`--list-sdks`

<span data-ttu-id="2f9d4-130">显示已安装的 .NET Core SDK。</span><span class="sxs-lookup"><span data-stu-id="2f9d4-130">Displays the installed .NET Core SDKs.</span></span>

`--roll-forward-on-no-candidate-fx <N>`

<span data-ttu-id="2f9d4-131">所需的共享框架不可用时，请定义行为。</span><span class="sxs-lookup"><span data-stu-id="2f9d4-131">Defines behavior when the required shared framework is not available.</span></span> <span data-ttu-id="2f9d4-132">`N` 可以是：</span><span class="sxs-lookup"><span data-stu-id="2f9d4-132">`N` can be:</span></span>

- <span data-ttu-id="2f9d4-133">`0` - 禁用次要版本前滚。</span><span class="sxs-lookup"><span data-stu-id="2f9d4-133">`0` - Disable even minor version roll forward.</span></span>
- <span data-ttu-id="2f9d4-134">`1` - 前滚次要版本，但不前滚主版本。</span><span class="sxs-lookup"><span data-stu-id="2f9d4-134">`1` - Roll forward on minor version, but not on major version.</span></span> <span data-ttu-id="2f9d4-135">这是默认行为。</span><span class="sxs-lookup"><span data-stu-id="2f9d4-135">This is the default behavior.</span></span>
- <span data-ttu-id="2f9d4-136">`2` - 前滚次要和主版本。</span><span class="sxs-lookup"><span data-stu-id="2f9d4-136">`2` - Roll forward on minor and major versions.</span></span>

 <span data-ttu-id="2f9d4-137">有关详细信息，请参阅[前滚](../whats-new/dotnet-core-2-1.md#roll-forward)。</span><span class="sxs-lookup"><span data-stu-id="2f9d4-137">For more information, see [Roll forward](../whats-new/dotnet-core-2-1.md#roll-forward).</span></span>

`--runtimeconfig`

<span data-ttu-id="2f9d4-138">runtimeconfig.template.json 文件的路径  。</span><span class="sxs-lookup"><span data-stu-id="2f9d4-138">Path to a *runtimeconfig.json* file.</span></span>

<span data-ttu-id="2f9d4-139">runtimeconfig.template.json 文件是包含运行时设置的配置文件  。</span><span class="sxs-lookup"><span data-stu-id="2f9d4-139">A *runtimeconfig.json* file is a configuration file containing run-time settings.</span></span> <span data-ttu-id="2f9d4-140">有关详细信息，请参阅 [.NET Core 运行时配置设置](../run-time-config/index.md#runtimeconfigjson)。</span><span class="sxs-lookup"><span data-stu-id="2f9d4-140">For more information, see [.NET Core run-time configuration settings](../run-time-config/index.md#runtimeconfigjson).</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="2f9d4-141">设置命令的详细级别。</span><span class="sxs-lookup"><span data-stu-id="2f9d4-141">Sets the verbosity level of the command.</span></span> <span data-ttu-id="2f9d4-142">允许使用的值为 `q[uiet]`、`m[inimal]`、`n[ormal]`、`d[etailed]` 和 `diag[nostic]`。</span><span class="sxs-lookup"><span data-stu-id="2f9d4-142">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="2f9d4-143">并非在每个命令中均受支持；请参阅特定的命令页，确定此选项是否可用。</span><span class="sxs-lookup"><span data-stu-id="2f9d4-143">Not supported in every command; see specific command page to determine if this option is available.</span></span>

`--version`

<span data-ttu-id="2f9d4-144">打印使用中的 .NET Core SDK 版本。</span><span class="sxs-lookup"><span data-stu-id="2f9d4-144">Prints out the version of the .NET Core SDK in use.</span></span>

# <a name="net-core-20"></a>[<span data-ttu-id="2f9d4-145">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="2f9d4-145">.NET Core 2.0</span></span>](#tab/netcore20)

`--additional-deps <PATH>`

<span data-ttu-id="2f9d4-146">附加 .deps.json 文件的路径  。</span><span class="sxs-lookup"><span data-stu-id="2f9d4-146">Path to an additional *.deps.json* file.</span></span>

`--additionalprobingpath <PATH>`

<span data-ttu-id="2f9d4-147">包含要进行探测的探测策略和程序集的路径。</span><span class="sxs-lookup"><span data-stu-id="2f9d4-147">Path containing probing policy and assemblies to probe.</span></span>

`--depsfile`

<span data-ttu-id="2f9d4-148">deps.json 文件的路径  。</span><span class="sxs-lookup"><span data-stu-id="2f9d4-148">Path to a *deps.json* file.</span></span>

<span data-ttu-id="2f9d4-149">deps.json 文件包含依赖项、编译依赖项和用于解决程序集冲突的版本信息列表  。</span><span class="sxs-lookup"><span data-stu-id="2f9d4-149">A *deps.json* file contains a list of dependencies, compilation dependencies and version information used to address assembly conflicts.</span></span> <span data-ttu-id="2f9d4-150">有关详细信息，请参阅 GitHub 上的[运行时配置文件](https://github.com/dotnet/cli/blob/master/Documentation/specs/runtime-configuration-file.md)。</span><span class="sxs-lookup"><span data-stu-id="2f9d4-150">For more details on this file, see [Runtime Configuration Files on GitHub](https://github.com/dotnet/cli/blob/master/Documentation/specs/runtime-configuration-file.md).</span></span>

`-d|--diagnostics`

<span data-ttu-id="2f9d4-151">启用诊断输出。</span><span class="sxs-lookup"><span data-stu-id="2f9d4-151">Enables diagnostic output.</span></span>

`--fx-version <VERSION>`

<span data-ttu-id="2f9d4-152">用于运行应用程序的 .NET Core 运行时版本。</span><span class="sxs-lookup"><span data-stu-id="2f9d4-152">Version of the .NET Core runtime to use to run the application.</span></span>

`-h|--help`

<span data-ttu-id="2f9d4-153">打印出给定命令的文档，如 `dotnet build --help`。</span><span class="sxs-lookup"><span data-stu-id="2f9d4-153">Prints out documentation for a given command, such as `dotnet build --help`.</span></span> <span data-ttu-id="2f9d4-154">`dotnet --help` 打印可用命令列表。</span><span class="sxs-lookup"><span data-stu-id="2f9d4-154">`dotnet --help` prints a list of available commands.</span></span>

`--info`

<span data-ttu-id="2f9d4-155">打印出有关 .NET Core 安装和计算机环境（如当前操作系统）的详细信息，并提交 .NET Core 版本的 SHA。</span><span class="sxs-lookup"><span data-stu-id="2f9d4-155">Prints out detailed information about a .NET Core installation and the machine environment, such as the current operating system, and commit SHA of the .NET Core version.</span></span>

`--roll-forward-on-no-candidate-fx`

 <span data-ttu-id="2f9d4-156">如果设置为 `0`，则禁用次要版本前滚。</span><span class="sxs-lookup"><span data-stu-id="2f9d4-156">Disables minor version roll forward, if set to `0`.</span></span> <span data-ttu-id="2f9d4-157">有关详细信息，请参阅[前滚](../whats-new/dotnet-core-2-1.md#roll-forward)。</span><span class="sxs-lookup"><span data-stu-id="2f9d4-157">For more information, see [Roll forward](../whats-new/dotnet-core-2-1.md#roll-forward).</span></span>

`--runtimeconfig`

<span data-ttu-id="2f9d4-158">runtimeconfig.template.json 文件的路径  。</span><span class="sxs-lookup"><span data-stu-id="2f9d4-158">Path to a *runtimeconfig.json* file.</span></span>

<span data-ttu-id="2f9d4-159">runtimeconfig.template.json 文件是包含运行时设置的配置文件  。</span><span class="sxs-lookup"><span data-stu-id="2f9d4-159">A *runtimeconfig.json* file is a configuration file containing run-time settings.</span></span> <span data-ttu-id="2f9d4-160">有关详细信息，请参阅 [.NET Core 运行时配置设置](../run-time-config/index.md#runtimeconfigjson)。</span><span class="sxs-lookup"><span data-stu-id="2f9d4-160">For more information, see [.NET Core run-time configuration settings](../run-time-config/index.md#runtimeconfigjson).</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="2f9d4-161">设置命令的详细级别。</span><span class="sxs-lookup"><span data-stu-id="2f9d4-161">Sets the verbosity level of the command.</span></span> <span data-ttu-id="2f9d4-162">允许使用的值为 `q[uiet]`、`m[inimal]`、`n[ormal]`、`d[etailed]` 和 `diag[nostic]`。</span><span class="sxs-lookup"><span data-stu-id="2f9d4-162">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="2f9d4-163">并非在每个命令中均受支持；请参阅特定的命令页，确定此选项是否可用。</span><span class="sxs-lookup"><span data-stu-id="2f9d4-163">Not supported in every command; see specific command page to determine if this option is available.</span></span>

`--version`

<span data-ttu-id="2f9d4-164">打印使用中的 .NET Core SDK 版本。</span><span class="sxs-lookup"><span data-stu-id="2f9d4-164">Prints out the version of the .NET Core SDK in use.</span></span>

# <a name="net-core-1x"></a>[<span data-ttu-id="2f9d4-165">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="2f9d4-165">.NET Core 1.x</span></span>](#tab/netcore1x)

`--additionalprobingpath <PATH>`

<span data-ttu-id="2f9d4-166">包含要进行探测的探测策略和程序集的路径。</span><span class="sxs-lookup"><span data-stu-id="2f9d4-166">Path containing probing policy and assemblies to probe.</span></span>

`--depsfile`

<span data-ttu-id="2f9d4-167">deps.json 文件的路径  。</span><span class="sxs-lookup"><span data-stu-id="2f9d4-167">Path to a *deps.json* file.</span></span>

<span data-ttu-id="2f9d4-168">deps.json 文件包含依赖项、编译依赖项和用于解决程序集冲突的版本信息列表  。</span><span class="sxs-lookup"><span data-stu-id="2f9d4-168">A *deps.json* file contains a list of dependencies, compilation dependencies and version information used to address assembly conflicts.</span></span> <span data-ttu-id="2f9d4-169">有关详细信息，请参阅 GitHub 上的[运行时配置文件](https://github.com/dotnet/cli/blob/master/Documentation/specs/runtime-configuration-file.md)。</span><span class="sxs-lookup"><span data-stu-id="2f9d4-169">For more details on this file, see [Runtime Configuration Files on GitHub](https://github.com/dotnet/cli/blob/master/Documentation/specs/runtime-configuration-file.md).</span></span>

`-d|--diagnostics`

<span data-ttu-id="2f9d4-170">启用诊断输出。</span><span class="sxs-lookup"><span data-stu-id="2f9d4-170">Enables diagnostic output.</span></span>

`--fx-version <VERSION>`

<span data-ttu-id="2f9d4-171">用于运行应用程序的 .NET Core 运行时版本。</span><span class="sxs-lookup"><span data-stu-id="2f9d4-171">Version of the .NET Core runtime to use to run the application.</span></span>

`-h|--help`

<span data-ttu-id="2f9d4-172">打印出给定命令的文档，如 `dotnet build --help`。</span><span class="sxs-lookup"><span data-stu-id="2f9d4-172">Prints out documentation for a given command, such as `dotnet build --help`.</span></span> <span data-ttu-id="2f9d4-173">`dotnet --help` 打印可用命令列表。</span><span class="sxs-lookup"><span data-stu-id="2f9d4-173">`dotnet --help` prints a list of available commands.</span></span>

`--info`

<span data-ttu-id="2f9d4-174">打印出有关 .NET Core 安装和计算机环境（如当前操作系统）的详细信息，并提交 .NET Core 版本的 SHA。</span><span class="sxs-lookup"><span data-stu-id="2f9d4-174">Prints out detailed information about a .NET Core installation and the machine environment, such as the current operating system, and commit SHA of the .NET Core version.</span></span>

`--runtimeconfig`

<span data-ttu-id="2f9d4-175">runtimeconfig.template.json 文件的路径  。</span><span class="sxs-lookup"><span data-stu-id="2f9d4-175">Path to a *runtimeconfig.json* file.</span></span>

<span data-ttu-id="2f9d4-176">runtimeconfig.template.json 文件是包含运行时设置的配置文件  。</span><span class="sxs-lookup"><span data-stu-id="2f9d4-176">A *runtimeconfig.json* file is a configuration file containing run-time settings.</span></span> <span data-ttu-id="2f9d4-177">有关详细信息，请参阅 [.NET Core 运行时配置设置](../run-time-config/index.md#runtimeconfigjson)。</span><span class="sxs-lookup"><span data-stu-id="2f9d4-177">For more information, see [.NET Core run-time configuration settings](../run-time-config/index.md#runtimeconfigjson).</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="2f9d4-178">设置命令的详细级别。</span><span class="sxs-lookup"><span data-stu-id="2f9d4-178">Sets the verbosity level of the command.</span></span> <span data-ttu-id="2f9d4-179">允许使用的值为 `q[uiet]`、`m[inimal]`、`n[ormal]`、`d[etailed]` 和 `diag[nostic]`。</span><span class="sxs-lookup"><span data-stu-id="2f9d4-179">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="2f9d4-180">并非在每个命令中均受支持；请参阅特定的命令页，确定此选项是否可用。</span><span class="sxs-lookup"><span data-stu-id="2f9d4-180">Not supported in every command; see specific command page to determine if this option is available.</span></span>

`--version`

<span data-ttu-id="2f9d4-181">打印使用中的 .NET Core SDK 版本。</span><span class="sxs-lookup"><span data-stu-id="2f9d4-181">Prints out the version of the .NET Core SDK in use.</span></span>

---

## <a name="dotnet-commands"></a><span data-ttu-id="2f9d4-182">dotnet 命令</span><span class="sxs-lookup"><span data-stu-id="2f9d4-182">dotnet commands</span></span>

### <a name="general"></a><span data-ttu-id="2f9d4-183">常规</span><span class="sxs-lookup"><span data-stu-id="2f9d4-183">General</span></span>

# <a name="net-core-21"></a>[<span data-ttu-id="2f9d4-184">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="2f9d4-184">.NET Core 2.1</span></span>](#tab/netcore21)

| <span data-ttu-id="2f9d4-185">命令</span><span class="sxs-lookup"><span data-stu-id="2f9d4-185">Command</span></span>                                       | <span data-ttu-id="2f9d4-186">函数</span><span class="sxs-lookup"><span data-stu-id="2f9d4-186">Function</span></span>                                                            |
| --------------------------------------------- | ------------------------------------------------------------------- |
| [<span data-ttu-id="2f9d4-187">dotnet build</span><span class="sxs-lookup"><span data-stu-id="2f9d4-187">dotnet build</span></span>](dotnet-build.md)               | <span data-ttu-id="2f9d4-188">生成 .NET Core 应用程序。</span><span class="sxs-lookup"><span data-stu-id="2f9d4-188">Builds a .NET Core application.</span></span>                                     |
| [<span data-ttu-id="2f9d4-189">dotnet build-server</span><span class="sxs-lookup"><span data-stu-id="2f9d4-189">dotnet build-server</span></span>](dotnet-build-server.md) | <span data-ttu-id="2f9d4-190">与通过生成启动的服务器进行交互。</span><span class="sxs-lookup"><span data-stu-id="2f9d4-190">Interacts with servers started by a build.</span></span>                          |
| [<span data-ttu-id="2f9d4-191">dotnet clean</span><span class="sxs-lookup"><span data-stu-id="2f9d4-191">dotnet clean</span></span>](dotnet-clean.md)               | <span data-ttu-id="2f9d4-192">清除生成输出。</span><span class="sxs-lookup"><span data-stu-id="2f9d4-192">Clean build outputs.</span></span>                                                |
| [<span data-ttu-id="2f9d4-193">dotnet help</span><span class="sxs-lookup"><span data-stu-id="2f9d4-193">dotnet help</span></span>](dotnet-help.md)                 | <span data-ttu-id="2f9d4-194">显示命令更详细的在线文档。</span><span class="sxs-lookup"><span data-stu-id="2f9d4-194">Shows more detailed documentation online for the command.</span></span>           |
| [<span data-ttu-id="2f9d4-195">dotnet migrate</span><span class="sxs-lookup"><span data-stu-id="2f9d4-195">dotnet migrate</span></span>](dotnet-migrate.md)           | <span data-ttu-id="2f9d4-196">将有效的预览版 2 项目迁移到 .NET Core SDK 1.0 项目。</span><span class="sxs-lookup"><span data-stu-id="2f9d4-196">Migrates a valid Preview 2 project to a .NET Core SDK 1.0 project.</span></span>  |
| [<span data-ttu-id="2f9d4-197">dotnet msbuild</span><span class="sxs-lookup"><span data-stu-id="2f9d4-197">dotnet msbuild</span></span>](dotnet-msbuild.md)           | <span data-ttu-id="2f9d4-198">提供对 MSBuild 命令行的访问权限。</span><span class="sxs-lookup"><span data-stu-id="2f9d4-198">Provides access to the MSBuild command line.</span></span>                        |
| [<span data-ttu-id="2f9d4-199">dotnet new</span><span class="sxs-lookup"><span data-stu-id="2f9d4-199">dotnet new</span></span>](dotnet-new.md)                   | <span data-ttu-id="2f9d4-200">为给定的模板初始化 C# 或 F# 项目。</span><span class="sxs-lookup"><span data-stu-id="2f9d4-200">Initializes a C# or F# project for a given template.</span></span>                |
| [<span data-ttu-id="2f9d4-201">dotnet pack</span><span class="sxs-lookup"><span data-stu-id="2f9d4-201">dotnet pack</span></span>](dotnet-pack.md)                 | <span data-ttu-id="2f9d4-202">创建代码的 NuGet 包。</span><span class="sxs-lookup"><span data-stu-id="2f9d4-202">Creates a NuGet package of your code.</span></span>                               |
| [<span data-ttu-id="2f9d4-203">dotnet publish</span><span class="sxs-lookup"><span data-stu-id="2f9d4-203">dotnet publish</span></span>](dotnet-publish.md)           | <span data-ttu-id="2f9d4-204">发布 .NET 依赖于框架或独立应用程序。</span><span class="sxs-lookup"><span data-stu-id="2f9d4-204">Publishes a .NET framework-dependent or self-contained application.</span></span> |
| [<span data-ttu-id="2f9d4-205">dotnet restore</span><span class="sxs-lookup"><span data-stu-id="2f9d4-205">dotnet restore</span></span>](dotnet-restore.md)           | <span data-ttu-id="2f9d4-206">还原给定应用程序的依赖项。</span><span class="sxs-lookup"><span data-stu-id="2f9d4-206">Restores the dependencies for a given application.</span></span>                  |
| [<span data-ttu-id="2f9d4-207">dotnet run</span><span class="sxs-lookup"><span data-stu-id="2f9d4-207">dotnet run</span></span>](dotnet-run.md)                   | <span data-ttu-id="2f9d4-208">从源运行应用程序。</span><span class="sxs-lookup"><span data-stu-id="2f9d4-208">Runs the application from source.</span></span>                                   |
| [<span data-ttu-id="2f9d4-209">dotnet sln</span><span class="sxs-lookup"><span data-stu-id="2f9d4-209">dotnet sln</span></span>](dotnet-sln.md)                   | <span data-ttu-id="2f9d4-210">用于添加、删除和列出解决方案文件中项目的选项。</span><span class="sxs-lookup"><span data-stu-id="2f9d4-210">Options to add, remove, and list projects in a solution file.</span></span>       |
| [<span data-ttu-id="2f9d4-211">dotnet store</span><span class="sxs-lookup"><span data-stu-id="2f9d4-211">dotnet store</span></span>](dotnet-store.md)               | <span data-ttu-id="2f9d4-212">将程序集存储到运行时包存储区。</span><span class="sxs-lookup"><span data-stu-id="2f9d4-212">Stores assemblies in the runtime package store.</span></span>                     |
| [<span data-ttu-id="2f9d4-213">dotnet test</span><span class="sxs-lookup"><span data-stu-id="2f9d4-213">dotnet test</span></span>](dotnet-test.md)                 | <span data-ttu-id="2f9d4-214">使用测试运行程序运行测试。</span><span class="sxs-lookup"><span data-stu-id="2f9d4-214">Runs tests using a test runner.</span></span>                                     |

# <a name="net-core-20"></a>[<span data-ttu-id="2f9d4-215">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="2f9d4-215">.NET Core 2.0</span></span>](#tab/netcore20)

| <span data-ttu-id="2f9d4-216">命令</span><span class="sxs-lookup"><span data-stu-id="2f9d4-216">Command</span></span>                             | <span data-ttu-id="2f9d4-217">函数</span><span class="sxs-lookup"><span data-stu-id="2f9d4-217">Function</span></span>                                                            |
| ----------------------------------- | ------------------------------------------------------------------- |
| [<span data-ttu-id="2f9d4-218">dotnet build</span><span class="sxs-lookup"><span data-stu-id="2f9d4-218">dotnet build</span></span>](dotnet-build.md)     | <span data-ttu-id="2f9d4-219">生成 .NET Core 应用程序。</span><span class="sxs-lookup"><span data-stu-id="2f9d4-219">Builds a .NET Core application.</span></span>                                     |
| [<span data-ttu-id="2f9d4-220">dotnet clean</span><span class="sxs-lookup"><span data-stu-id="2f9d4-220">dotnet clean</span></span>](dotnet-clean.md)     | <span data-ttu-id="2f9d4-221">清除生成输出。</span><span class="sxs-lookup"><span data-stu-id="2f9d4-221">Clean build outputs.</span></span>                                              |
| [<span data-ttu-id="2f9d4-222">dotnet help</span><span class="sxs-lookup"><span data-stu-id="2f9d4-222">dotnet help</span></span>](dotnet-help.md)       | <span data-ttu-id="2f9d4-223">显示命令更详细的在线文档。</span><span class="sxs-lookup"><span data-stu-id="2f9d4-223">Shows more detailed documentation online for the command.</span></span>           |
| [<span data-ttu-id="2f9d4-224">dotnet migrate</span><span class="sxs-lookup"><span data-stu-id="2f9d4-224">dotnet migrate</span></span>](dotnet-migrate.md) | <span data-ttu-id="2f9d4-225">将有效的预览版 2 项目迁移到 .NET Core SDK 1.0 项目。</span><span class="sxs-lookup"><span data-stu-id="2f9d4-225">Migrates a valid Preview 2 project to a .NET Core SDK 1.0 project.</span></span>  |
| [<span data-ttu-id="2f9d4-226">dotnet msbuild</span><span class="sxs-lookup"><span data-stu-id="2f9d4-226">dotnet msbuild</span></span>](dotnet-msbuild.md) | <span data-ttu-id="2f9d4-227">提供对 MSBuild 命令行的访问权限。</span><span class="sxs-lookup"><span data-stu-id="2f9d4-227">Provides access to the MSBuild command line.</span></span>                        |
| [<span data-ttu-id="2f9d4-228">dotnet new</span><span class="sxs-lookup"><span data-stu-id="2f9d4-228">dotnet new</span></span>](dotnet-new.md)         | <span data-ttu-id="2f9d4-229">为给定的模板初始化 C# 或 F# 项目。</span><span class="sxs-lookup"><span data-stu-id="2f9d4-229">Initializes a C# or F# project for a given template.</span></span>                |
| [<span data-ttu-id="2f9d4-230">dotnet pack</span><span class="sxs-lookup"><span data-stu-id="2f9d4-230">dotnet pack</span></span>](dotnet-pack.md)       | <span data-ttu-id="2f9d4-231">创建代码的 NuGet 包。</span><span class="sxs-lookup"><span data-stu-id="2f9d4-231">Creates a NuGet package of your code.</span></span>                               |
| [<span data-ttu-id="2f9d4-232">dotnet publish</span><span class="sxs-lookup"><span data-stu-id="2f9d4-232">dotnet publish</span></span>](dotnet-publish.md) | <span data-ttu-id="2f9d4-233">发布 .NET 依赖于框架或独立应用程序。</span><span class="sxs-lookup"><span data-stu-id="2f9d4-233">Publishes a .NET framework-dependent or self-contained application.</span></span> |
| [<span data-ttu-id="2f9d4-234">dotnet restore</span><span class="sxs-lookup"><span data-stu-id="2f9d4-234">dotnet restore</span></span>](dotnet-restore.md) | <span data-ttu-id="2f9d4-235">还原给定应用程序的依赖项。</span><span class="sxs-lookup"><span data-stu-id="2f9d4-235">Restores the dependencies for a given application.</span></span>                  |
| [<span data-ttu-id="2f9d4-236">dotnet run</span><span class="sxs-lookup"><span data-stu-id="2f9d4-236">dotnet run</span></span>](dotnet-run.md)         | <span data-ttu-id="2f9d4-237">从源运行应用程序。</span><span class="sxs-lookup"><span data-stu-id="2f9d4-237">Runs the application from source.</span></span>                                   |
| [<span data-ttu-id="2f9d4-238">dotnet sln</span><span class="sxs-lookup"><span data-stu-id="2f9d4-238">dotnet sln</span></span>](dotnet-sln.md)         | <span data-ttu-id="2f9d4-239">用于添加、删除和列出解决方案文件中项目的选项。</span><span class="sxs-lookup"><span data-stu-id="2f9d4-239">Options to add, remove, and list projects in a solution file.</span></span>       |
| [<span data-ttu-id="2f9d4-240">dotnet store</span><span class="sxs-lookup"><span data-stu-id="2f9d4-240">dotnet store</span></span>](dotnet-store.md)     | <span data-ttu-id="2f9d4-241">将程序集存储到运行时包存储区。</span><span class="sxs-lookup"><span data-stu-id="2f9d4-241">Stores assemblies in the runtime package store.</span></span>                     |
| [<span data-ttu-id="2f9d4-242">dotnet test</span><span class="sxs-lookup"><span data-stu-id="2f9d4-242">dotnet test</span></span>](dotnet-test.md)       | <span data-ttu-id="2f9d4-243">使用测试运行程序运行测试。</span><span class="sxs-lookup"><span data-stu-id="2f9d4-243">Runs tests using a test runner.</span></span>                                     |

# <a name="net-core-1x"></a>[<span data-ttu-id="2f9d4-244">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="2f9d4-244">.NET Core 1.x</span></span>](#tab/netcore1x)

| <span data-ttu-id="2f9d4-245">命令</span><span class="sxs-lookup"><span data-stu-id="2f9d4-245">Command</span></span>                             | <span data-ttu-id="2f9d4-246">函数</span><span class="sxs-lookup"><span data-stu-id="2f9d4-246">Function</span></span>                                                            |
| ----------------------------------- | ------------------------------------------------------------------- |
| [<span data-ttu-id="2f9d4-247">dotnet build</span><span class="sxs-lookup"><span data-stu-id="2f9d4-247">dotnet build</span></span>](dotnet-build.md)     | <span data-ttu-id="2f9d4-248">生成 .NET Core 应用程序。</span><span class="sxs-lookup"><span data-stu-id="2f9d4-248">Builds a .NET Core application.</span></span>                                     |
| [<span data-ttu-id="2f9d4-249">dotnet clean</span><span class="sxs-lookup"><span data-stu-id="2f9d4-249">dotnet clean</span></span>](dotnet-clean.md)     | <span data-ttu-id="2f9d4-250">清除生成输出。</span><span class="sxs-lookup"><span data-stu-id="2f9d4-250">Clean build outputs.</span></span>                                              |
| [<span data-ttu-id="2f9d4-251">dotnet migrate</span><span class="sxs-lookup"><span data-stu-id="2f9d4-251">dotnet migrate</span></span>](dotnet-migrate.md) | <span data-ttu-id="2f9d4-252">将有效的预览版 2 项目迁移到 .NET Core SDK 1.0 项目。</span><span class="sxs-lookup"><span data-stu-id="2f9d4-252">Migrates a valid Preview 2 project to a .NET Core SDK 1.0 project.</span></span>  |
| [<span data-ttu-id="2f9d4-253">dotnet msbuild</span><span class="sxs-lookup"><span data-stu-id="2f9d4-253">dotnet msbuild</span></span>](dotnet-msbuild.md) | <span data-ttu-id="2f9d4-254">提供对 MSBuild 命令行的访问权限。</span><span class="sxs-lookup"><span data-stu-id="2f9d4-254">Provides access to the MSBuild command line.</span></span>                        |
| [<span data-ttu-id="2f9d4-255">dotnet new</span><span class="sxs-lookup"><span data-stu-id="2f9d4-255">dotnet new</span></span>](dotnet-new.md)         | <span data-ttu-id="2f9d4-256">为给定的模板初始化 C# 或 F# 项目。</span><span class="sxs-lookup"><span data-stu-id="2f9d4-256">Initializes a C# or F# project for a given template.</span></span>                |
| [<span data-ttu-id="2f9d4-257">dotnet pack</span><span class="sxs-lookup"><span data-stu-id="2f9d4-257">dotnet pack</span></span>](dotnet-pack.md)       | <span data-ttu-id="2f9d4-258">创建代码的 NuGet 包。</span><span class="sxs-lookup"><span data-stu-id="2f9d4-258">Creates a NuGet package of your code.</span></span>                               |
| [<span data-ttu-id="2f9d4-259">dotnet publish</span><span class="sxs-lookup"><span data-stu-id="2f9d4-259">dotnet publish</span></span>](dotnet-publish.md) | <span data-ttu-id="2f9d4-260">发布 .NET 依赖于框架或独立应用程序。</span><span class="sxs-lookup"><span data-stu-id="2f9d4-260">Publishes a .NET framework-dependent or self-contained application.</span></span> |
| [<span data-ttu-id="2f9d4-261">dotnet restore</span><span class="sxs-lookup"><span data-stu-id="2f9d4-261">dotnet restore</span></span>](dotnet-restore.md) | <span data-ttu-id="2f9d4-262">还原给定应用程序的依赖项。</span><span class="sxs-lookup"><span data-stu-id="2f9d4-262">Restores the dependencies for a given application.</span></span>                  |
| [<span data-ttu-id="2f9d4-263">dotnet run</span><span class="sxs-lookup"><span data-stu-id="2f9d4-263">dotnet run</span></span>](dotnet-run.md)         | <span data-ttu-id="2f9d4-264">从源运行应用程序。</span><span class="sxs-lookup"><span data-stu-id="2f9d4-264">Runs the application from source.</span></span>                                   |
| [<span data-ttu-id="2f9d4-265">dotnet sln</span><span class="sxs-lookup"><span data-stu-id="2f9d4-265">dotnet sln</span></span>](dotnet-sln.md)         | <span data-ttu-id="2f9d4-266">用于添加、删除和列出解决方案文件中项目的选项。</span><span class="sxs-lookup"><span data-stu-id="2f9d4-266">Options to add, remove, and list projects in a solution file.</span></span>       |
| [<span data-ttu-id="2f9d4-267">dotnet test</span><span class="sxs-lookup"><span data-stu-id="2f9d4-267">dotnet test</span></span>](dotnet-test.md)       | <span data-ttu-id="2f9d4-268">使用测试运行程序运行测试。</span><span class="sxs-lookup"><span data-stu-id="2f9d4-268">Runs tests using a test runner.</span></span>                                     |

---

### <a name="project-references"></a><span data-ttu-id="2f9d4-269">项目引用</span><span class="sxs-lookup"><span data-stu-id="2f9d4-269">Project references</span></span>

<span data-ttu-id="2f9d4-270">命令</span><span class="sxs-lookup"><span data-stu-id="2f9d4-270">Command</span></span> | <span data-ttu-id="2f9d4-271">函数</span><span class="sxs-lookup"><span data-stu-id="2f9d4-271">Function</span></span>
--- | ---
[<span data-ttu-id="2f9d4-272">dotnet add reference</span><span class="sxs-lookup"><span data-stu-id="2f9d4-272">dotnet add reference</span></span>](dotnet-add-reference.md) | <span data-ttu-id="2f9d4-273">添加项目引用。</span><span class="sxs-lookup"><span data-stu-id="2f9d4-273">Adds a project reference.</span></span>
[<span data-ttu-id="2f9d4-274">dotnet list reference</span><span class="sxs-lookup"><span data-stu-id="2f9d4-274">dotnet list reference</span></span>](dotnet-list-reference.md) | <span data-ttu-id="2f9d4-275">列出项目引用。</span><span class="sxs-lookup"><span data-stu-id="2f9d4-275">Lists project references.</span></span>
[<span data-ttu-id="2f9d4-276">dotnet remove reference</span><span class="sxs-lookup"><span data-stu-id="2f9d4-276">dotnet remove reference</span></span>](dotnet-remove-reference.md) | <span data-ttu-id="2f9d4-277">删除项目引用。</span><span class="sxs-lookup"><span data-stu-id="2f9d4-277">Removes a project reference.</span></span>

### <a name="nuget-packages"></a><span data-ttu-id="2f9d4-278">NuGet 包</span><span class="sxs-lookup"><span data-stu-id="2f9d4-278">NuGet packages</span></span>

<span data-ttu-id="2f9d4-279">命令</span><span class="sxs-lookup"><span data-stu-id="2f9d4-279">Command</span></span> | <span data-ttu-id="2f9d4-280">函数</span><span class="sxs-lookup"><span data-stu-id="2f9d4-280">Function</span></span>
--- | ---
[<span data-ttu-id="2f9d4-281">dotnet add package</span><span class="sxs-lookup"><span data-stu-id="2f9d4-281">dotnet add package</span></span>](dotnet-add-package.md) | <span data-ttu-id="2f9d4-282">添加 NuGet 包。</span><span class="sxs-lookup"><span data-stu-id="2f9d4-282">Adds a NuGet package.</span></span>
[<span data-ttu-id="2f9d4-283">dotnet remove package</span><span class="sxs-lookup"><span data-stu-id="2f9d4-283">dotnet remove package</span></span>](dotnet-remove-package.md) | <span data-ttu-id="2f9d4-284">删除 NuGet 包。</span><span class="sxs-lookup"><span data-stu-id="2f9d4-284">Removes a NuGet package.</span></span>

### <a name="nuget-commands"></a><span data-ttu-id="2f9d4-285">NuGet 命令</span><span class="sxs-lookup"><span data-stu-id="2f9d4-285">NuGet commands</span></span>

<span data-ttu-id="2f9d4-286">命令</span><span class="sxs-lookup"><span data-stu-id="2f9d4-286">Command</span></span> | <span data-ttu-id="2f9d4-287">函数</span><span class="sxs-lookup"><span data-stu-id="2f9d4-287">Function</span></span>
--- | ---
[<span data-ttu-id="2f9d4-288">dotnet nuget delete</span><span class="sxs-lookup"><span data-stu-id="2f9d4-288">dotnet nuget delete</span></span>](dotnet-nuget-delete.md) | <span data-ttu-id="2f9d4-289">从服务器删除或取消列出包。</span><span class="sxs-lookup"><span data-stu-id="2f9d4-289">Deletes or unlists a package from the server.</span></span>
[<span data-ttu-id="2f9d4-290">dotnet nuget locals</span><span class="sxs-lookup"><span data-stu-id="2f9d4-290">dotnet nuget locals</span></span>](dotnet-nuget-locals.md) | <span data-ttu-id="2f9d4-291">清除或列出本地 NuGet 资源，例如 http 请求缓存、临时缓存或计算机范围的全局包文件夹。</span><span class="sxs-lookup"><span data-stu-id="2f9d4-291">Clears or lists local NuGet resources such as http-request cache, temporary cache, or machine-wide global packages folder.</span></span>
[<span data-ttu-id="2f9d4-292">dotnet nuget push</span><span class="sxs-lookup"><span data-stu-id="2f9d4-292">dotnet nuget push</span></span>](dotnet-nuget-push.md) | <span data-ttu-id="2f9d4-293">将包推送到服务器，并将其发布。</span><span class="sxs-lookup"><span data-stu-id="2f9d4-293">Pushes a package to the server and publishes it.</span></span>

### <a name="global-tool-path-and-local-tools-commands"></a><span data-ttu-id="2f9d4-294">全局、工具路径和本地工具命令</span><span class="sxs-lookup"><span data-stu-id="2f9d4-294">Global, tool-path, and local tools commands</span></span>

<span data-ttu-id="2f9d4-295">工具是控制台应用程序，它们从 NuGet 包中安装并从命令提示符处进行调用。</span><span class="sxs-lookup"><span data-stu-id="2f9d4-295">Tools are console applications that are installed from NuGet packages and are invoked from the command prompt.</span></span> <span data-ttu-id="2f9d4-296">你可自行编写工具，也可安装由第三方编写的工具。</span><span class="sxs-lookup"><span data-stu-id="2f9d4-296">You can write tools yourself or install tools written by third parties.</span></span> <span data-ttu-id="2f9d4-297">工具也称为全局工具、工具路径工具和本地工具。</span><span class="sxs-lookup"><span data-stu-id="2f9d4-297">Tools are also known as global tools, tool-path tools, and local tools.</span></span> <span data-ttu-id="2f9d4-298">有关详细信息，请参阅 [.NET Core 工具概述](global-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="2f9d4-298">For more information, see [.NET Core tools overview](global-tools.md).</span></span> <span data-ttu-id="2f9d4-299">全局和工具路径工具从 .NET Core SDK 2.1 开始可用。</span><span class="sxs-lookup"><span data-stu-id="2f9d4-299">Global and tool-path tools are available starting with .NET Core SDK 2.1.</span></span> <span data-ttu-id="2f9d4-300">本地工具从 .NET Core SDK 3.0 开始可用。</span><span class="sxs-lookup"><span data-stu-id="2f9d4-300">Local tools are available starting with .NET Core SDK 3.0.</span></span>

<span data-ttu-id="2f9d4-301">命令</span><span class="sxs-lookup"><span data-stu-id="2f9d4-301">Command</span></span> | <span data-ttu-id="2f9d4-302">函数</span><span class="sxs-lookup"><span data-stu-id="2f9d4-302">Function</span></span>
--- | ---
[<span data-ttu-id="2f9d4-303">dotnet tool install</span><span class="sxs-lookup"><span data-stu-id="2f9d4-303">dotnet tool install</span></span>](dotnet-tool-install.md) | <span data-ttu-id="2f9d4-304">在计算机上安装工具。</span><span class="sxs-lookup"><span data-stu-id="2f9d4-304">Installs a tool on your machine.</span></span>
[<span data-ttu-id="2f9d4-305">dotnet tool list</span><span class="sxs-lookup"><span data-stu-id="2f9d4-305">dotnet tool list</span></span>](dotnet-tool-list.md) | <span data-ttu-id="2f9d4-306">列出计算机上当前安装的所有全局、工具路径或本地工具。</span><span class="sxs-lookup"><span data-stu-id="2f9d4-306">Lists all global, tool-path, or local tools currently installed on your machine.</span></span>
[<span data-ttu-id="2f9d4-307">dotnet tool uninstall</span><span class="sxs-lookup"><span data-stu-id="2f9d4-307">dotnet tool uninstall</span></span>](dotnet-tool-uninstall.md) | <span data-ttu-id="2f9d4-308">从计算机中卸载工具。</span><span class="sxs-lookup"><span data-stu-id="2f9d4-308">Uninstalls a tool from your machine.</span></span>
[<span data-ttu-id="2f9d4-309">dotnet tool update</span><span class="sxs-lookup"><span data-stu-id="2f9d4-309">dotnet tool update</span></span>](dotnet-tool-update.md) | <span data-ttu-id="2f9d4-310">更新计算机上安装的工具。</span><span class="sxs-lookup"><span data-stu-id="2f9d4-310">Updates a tool that is installed on your machine.</span></span>

### <a name="additional-tools"></a><span data-ttu-id="2f9d4-311">其他工具</span><span class="sxs-lookup"><span data-stu-id="2f9d4-311">Additional tools</span></span>

<span data-ttu-id="2f9d4-312">自 .NET Core SDK 2.1.300 开始，许多使用 `DotnetCliToolReference` 的仅在每个项目的基础上可用的工具现作为 .NET Core SDK 的一部分提供。</span><span class="sxs-lookup"><span data-stu-id="2f9d4-312">Starting with .NET Core SDK 2.1.300, a number of tools that were available only on a per project basis using `DotnetCliToolReference` are now available as part of the .NET Core SDK.</span></span> <span data-ttu-id="2f9d4-313">下表中列出了这些工具：</span><span class="sxs-lookup"><span data-stu-id="2f9d4-313">These tools are listed in the following table:</span></span>

| <span data-ttu-id="2f9d4-314">工具</span><span class="sxs-lookup"><span data-stu-id="2f9d4-314">Tool</span></span>                                              | <span data-ttu-id="2f9d4-315">函数</span><span class="sxs-lookup"><span data-stu-id="2f9d4-315">Function</span></span>                                                     |
| ------------------------------------------------- | ------------------------------------------------------------ |
| <span data-ttu-id="2f9d4-316">dev-certs</span><span class="sxs-lookup"><span data-stu-id="2f9d4-316">dev-certs</span></span>                                         | <span data-ttu-id="2f9d4-317">创建和管理开发证书。</span><span class="sxs-lookup"><span data-stu-id="2f9d4-317">Creates and manages development certificates.</span></span>                |
| [<span data-ttu-id="2f9d4-318">ef</span><span class="sxs-lookup"><span data-stu-id="2f9d4-318">ef</span></span>](/ef/core/miscellaneous/cli/dotnet)           | <span data-ttu-id="2f9d4-319">Entity Framework Core 命令行工具。</span><span class="sxs-lookup"><span data-stu-id="2f9d4-319">Entity Framework Core command-line tools.</span></span>                    |
| <span data-ttu-id="2f9d4-320">sql-cache</span><span class="sxs-lookup"><span data-stu-id="2f9d4-320">sql-cache</span></span>                                         | <span data-ttu-id="2f9d4-321">SQL Server 缓存命令行工具。</span><span class="sxs-lookup"><span data-stu-id="2f9d4-321">SQL Server cache command-line tools.</span></span>                         |
| [<span data-ttu-id="2f9d4-322">user-secrets</span><span class="sxs-lookup"><span data-stu-id="2f9d4-322">user-secrets</span></span>](/aspnet/core/security/app-secrets) | <span data-ttu-id="2f9d4-323">管理开发用户机密。</span><span class="sxs-lookup"><span data-stu-id="2f9d4-323">Manages development user secrets.</span></span>                            |
| [<span data-ttu-id="2f9d4-324">watch</span><span class="sxs-lookup"><span data-stu-id="2f9d4-324">watch</span></span>](/aspnet/core/tutorials/dotnet-watch)      | <span data-ttu-id="2f9d4-325">启动文件观察程序，以在更改文件时运行命令。</span><span class="sxs-lookup"><span data-stu-id="2f9d4-325">Starts a file watcher that runs a command when files change.</span></span> |

<span data-ttu-id="2f9d4-326">有关每个工具的详细信息，请键入 `dotnet <tool-name> --help`。</span><span class="sxs-lookup"><span data-stu-id="2f9d4-326">For more information about each tool, type `dotnet <tool-name> --help`.</span></span>

## <a name="examples"></a><span data-ttu-id="2f9d4-327">示例</span><span class="sxs-lookup"><span data-stu-id="2f9d4-327">Examples</span></span>

<span data-ttu-id="2f9d4-328">创建新的 .NET Core 控制台应用程序：</span><span class="sxs-lookup"><span data-stu-id="2f9d4-328">Creates a new .NET Core console application:</span></span>

`dotnet new console`

<span data-ttu-id="2f9d4-329">还原给定应用程序的依赖项：</span><span class="sxs-lookup"><span data-stu-id="2f9d4-329">Restore dependencies for a given application:</span></span>

`dotnet restore`

[!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]

<span data-ttu-id="2f9d4-330">生成给定目录中的项目及其依赖项：</span><span class="sxs-lookup"><span data-stu-id="2f9d4-330">Build a project and its dependencies in a given directory:</span></span>

`dotnet build`

<span data-ttu-id="2f9d4-331">运行应用程序 DLL，如 `myapp.dll`：</span><span class="sxs-lookup"><span data-stu-id="2f9d4-331">Run an application DLL, such as `myapp.dll`:</span></span>

`dotnet myapp.dll`

## <a name="environment-variables"></a><span data-ttu-id="2f9d4-332">环境变量</span><span class="sxs-lookup"><span data-stu-id="2f9d4-332">Environment variables</span></span>

# <a name="net-core-21"></a>[<span data-ttu-id="2f9d4-333">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="2f9d4-333">.NET Core 2.1</span></span>](#tab/netcore21)

`DOTNET_PACKAGES`

<span data-ttu-id="2f9d4-334">全局包文件夹。</span><span class="sxs-lookup"><span data-stu-id="2f9d4-334">The global packages folder.</span></span> <span data-ttu-id="2f9d4-335">如果未设置，则默认为 Unix 上的 `~/.nuget/packages` 或 Windows 上的 `%userprofile%\.nuget\packages`。</span><span class="sxs-lookup"><span data-stu-id="2f9d4-335">If not set, it defaults to `~/.nuget/packages` on Unix or `%userprofile%\.nuget\packages` on Windows.</span></span>

`DOTNET_SERVICING`

<span data-ttu-id="2f9d4-336">指定加载运行时期间共享主机要使用的服务索引的位置。</span><span class="sxs-lookup"><span data-stu-id="2f9d4-336">Specifies the location of the servicing index to use by the shared host when loading the runtime.</span></span>

`DOTNET_CLI_TELEMETRY_OPTOUT`

<span data-ttu-id="2f9d4-337">指定是否收集并向 Microsoft 发送 .NET Core 工具使用情况的相关数据。</span><span class="sxs-lookup"><span data-stu-id="2f9d4-337">Specifies whether data about the .NET Core tools usage is collected and sent to Microsoft.</span></span> <span data-ttu-id="2f9d4-338">设置为 `true` 以选择退出遥测功能（接受的值为 `true`、`1` 或 `yes`）。</span><span class="sxs-lookup"><span data-stu-id="2f9d4-338">Set to `true` to opt-out of the telemetry feature (values `true`, `1`, or `yes` accepted).</span></span> <span data-ttu-id="2f9d4-339">否则，设置为 `false` 以选择加入遥测功能（接受的值为 `false`、`0` 或 `no`）。</span><span class="sxs-lookup"><span data-stu-id="2f9d4-339">Otherwise, set to `false` to opt into the telemetry features (values `false`, `0`, or `no` accepted).</span></span> <span data-ttu-id="2f9d4-340">如果未设置，则默认为 `false` 且遥测功能为活动状态。</span><span class="sxs-lookup"><span data-stu-id="2f9d4-340">If not set, the default is `false` and the telemetry feature is active.</span></span>

`DOTNET_MULTILEVEL_LOOKUP`

<span data-ttu-id="2f9d4-341">指定是否从全局位置解析 .NET Core 运行时、共享框架或 SDK。</span><span class="sxs-lookup"><span data-stu-id="2f9d4-341">Specifies whether .NET Core runtime, shared framework, or SDK are resolved from the global location.</span></span> <span data-ttu-id="2f9d4-342">如果未设置，则默认为 `true`。</span><span class="sxs-lookup"><span data-stu-id="2f9d4-342">If not set, it defaults to `true`.</span></span> <span data-ttu-id="2f9d4-343">设置为 `false` 不从全局位置解析，并且具有独立的 .NET Core 安装（接受的值为 `0` 或 `false`）。</span><span class="sxs-lookup"><span data-stu-id="2f9d4-343">Set to `false` to not resolve from the global location and have isolated .NET Core installations (values `0` or `false` are accepted).</span></span> <span data-ttu-id="2f9d4-344">有关多级别查找的详细信息，请参阅 [Multi-level SharedFX Lookup](https://github.com/dotnet/core-setup/blob/master/Documentation/design-docs/multilevel-sharedfx-lookup.md)（多级别 SharedFX 查找）。</span><span class="sxs-lookup"><span data-stu-id="2f9d4-344">For more information about multi-level lookup, see [Multi-level SharedFX Lookup](https://github.com/dotnet/core-setup/blob/master/Documentation/design-docs/multilevel-sharedfx-lookup.md).</span></span>

`DOTNET_ROLL_FORWARD_ON_NO_CANDIDATE_FX`

<span data-ttu-id="2f9d4-345">如果设置为 `0`，则禁用次要版本前滚。</span><span class="sxs-lookup"><span data-stu-id="2f9d4-345">Disables minor version roll forward, if set to `0`.</span></span> <span data-ttu-id="2f9d4-346">有关详细信息，请参阅[前滚](../whats-new/dotnet-core-2-1.md#roll-forward)。</span><span class="sxs-lookup"><span data-stu-id="2f9d4-346">For more information, see [Roll forward](../whats-new/dotnet-core-2-1.md#roll-forward).</span></span>

# <a name="net-core-20"></a>[<span data-ttu-id="2f9d4-347">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="2f9d4-347">.NET Core 2.0</span></span>](#tab/netcore20)

`DOTNET_PACKAGES`

<span data-ttu-id="2f9d4-348">主包缓存。</span><span class="sxs-lookup"><span data-stu-id="2f9d4-348">The primary package cache.</span></span> <span data-ttu-id="2f9d4-349">如果未设置，则默认为 Unix 上的 `$HOME/.nuget/packages` 或 Windows 上的 `%userprofile%\.nuget\packages`。</span><span class="sxs-lookup"><span data-stu-id="2f9d4-349">If not set, it defaults to `$HOME/.nuget/packages` on Unix or `%userprofile%\.nuget\packages` on Windows.</span></span>

`DOTNET_SERVICING`

<span data-ttu-id="2f9d4-350">指定加载运行时期间共享主机要使用的服务索引的位置。</span><span class="sxs-lookup"><span data-stu-id="2f9d4-350">Specifies the location of the servicing index to use by the shared host when loading the runtime.</span></span>

`DOTNET_CLI_TELEMETRY_OPTOUT`

<span data-ttu-id="2f9d4-351">指定是否收集并向 Microsoft 发送 .NET Core 工具使用情况的相关数据。</span><span class="sxs-lookup"><span data-stu-id="2f9d4-351">Specifies whether data about the .NET Core tools usage is collected and sent to Microsoft.</span></span> <span data-ttu-id="2f9d4-352">设置为 `true` 以选择退出遥测功能（接受的值为 `true`、`1` 或 `yes`）。</span><span class="sxs-lookup"><span data-stu-id="2f9d4-352">Set to `true` to opt-out of the telemetry feature (values `true`, `1`, or `yes` accepted).</span></span> <span data-ttu-id="2f9d4-353">否则，设置为 `false` 以选择加入遥测功能（接受的值为 `false`、`0` 或 `no`）。</span><span class="sxs-lookup"><span data-stu-id="2f9d4-353">Otherwise, set to `false` to opt into the telemetry features (values `false`, `0`, or `no` accepted).</span></span> <span data-ttu-id="2f9d4-354">如果未设置，则默认为 `false` 且遥测功能为活动状态。</span><span class="sxs-lookup"><span data-stu-id="2f9d4-354">If not set, the default is `false` and the telemetry feature is active.</span></span>

`DOTNET_MULTILEVEL_LOOKUP`

<span data-ttu-id="2f9d4-355">指定是否从全局位置解析 .NET Core 运行时、共享框架或 SDK。</span><span class="sxs-lookup"><span data-stu-id="2f9d4-355">Specifies whether .NET Core runtime, shared framework, or SDK are resolved from the global location.</span></span> <span data-ttu-id="2f9d4-356">如果未设置，则默认为 `true`。</span><span class="sxs-lookup"><span data-stu-id="2f9d4-356">If not set, it defaults to `true`.</span></span> <span data-ttu-id="2f9d4-357">设置为 `false` 不从全局位置解析，并且具有独立的 .NET Core 安装（接受的值为 `0` 或 `false`）。</span><span class="sxs-lookup"><span data-stu-id="2f9d4-357">Set to `false` to not resolve from the global location and have isolated .NET Core installations (values `0` or `false` are accepted).</span></span> <span data-ttu-id="2f9d4-358">有关多级别查找的详细信息，请参阅 [Multi-level SharedFX Lookup](https://github.com/dotnet/core-setup/blob/master/Documentation/design-docs/multilevel-sharedfx-lookup.md)（多级别 SharedFX 查找）。</span><span class="sxs-lookup"><span data-stu-id="2f9d4-358">For more information about multi-level lookup, see [Multi-level SharedFX Lookup](https://github.com/dotnet/core-setup/blob/master/Documentation/design-docs/multilevel-sharedfx-lookup.md).</span></span>

# <a name="net-core-1x"></a>[<span data-ttu-id="2f9d4-359">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="2f9d4-359">.NET Core 1.x</span></span>](#tab/netcore1x)

`DOTNET_PACKAGES`

<span data-ttu-id="2f9d4-360">主包缓存。</span><span class="sxs-lookup"><span data-stu-id="2f9d4-360">The primary package cache.</span></span> <span data-ttu-id="2f9d4-361">如果未设置，则默认为 Unix 上的 `$HOME/.nuget/packages` 或 Windows 上的 `%userprofile%\.nuget\packages`。</span><span class="sxs-lookup"><span data-stu-id="2f9d4-361">If not set, it defaults to `$HOME/.nuget/packages` on Unix or `%userprofile%\.nuget\packages` on Windows.</span></span>

`DOTNET_SERVICING`

<span data-ttu-id="2f9d4-362">指定加载运行时期间共享主机要使用的服务索引的位置。</span><span class="sxs-lookup"><span data-stu-id="2f9d4-362">Specifies the location of the servicing index to use by the shared host when loading the runtime.</span></span>

`DOTNET_CLI_TELEMETRY_OPTOUT`

<span data-ttu-id="2f9d4-363">指定是否收集并向 Microsoft 发送 .NET Core 工具使用情况的相关数据。</span><span class="sxs-lookup"><span data-stu-id="2f9d4-363">Specifies whether data about the .NET Core tools usage is collected and sent to Microsoft.</span></span> <span data-ttu-id="2f9d4-364">设置为 `true` 以选择退出遥测功能（接受的值为 `true`、`1` 或 `yes`）。</span><span class="sxs-lookup"><span data-stu-id="2f9d4-364">Set to `true` to opt-out of the telemetry feature (values `true`, `1`, or `yes` accepted).</span></span> <span data-ttu-id="2f9d4-365">否则，设置为 `false` 以选择加入遥测功能（接受的值为 `false`、`0` 或 `no`）。</span><span class="sxs-lookup"><span data-stu-id="2f9d4-365">Otherwise, set to `false` to opt into the telemetry features (values `false`, `0`, or `no` accepted).</span></span> <span data-ttu-id="2f9d4-366">如果未设置，则默认为 `false` 且遥测功能为活动状态。</span><span class="sxs-lookup"><span data-stu-id="2f9d4-366">If not set, the default is `false` and the telemetry feature is active.</span></span>

---

## <a name="see-also"></a><span data-ttu-id="2f9d4-367">请参阅</span><span class="sxs-lookup"><span data-stu-id="2f9d4-367">See also</span></span>

- [<span data-ttu-id="2f9d4-368">运行时配置文件</span><span class="sxs-lookup"><span data-stu-id="2f9d4-368">Runtime Configuration Files</span></span>](https://github.com/dotnet/cli/blob/master/Documentation/specs/runtime-configuration-file.md)
- [<span data-ttu-id="2f9d4-369">.NET Core 运行时配置设置</span><span class="sxs-lookup"><span data-stu-id="2f9d4-369">.NET Core run-time configuration settings</span></span>](../run-time-config/index.md)
