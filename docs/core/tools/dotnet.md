---
title: dotnet 命令
description: 了解 dotnet 命令（.NET Core CLI 工具的通用驱动程序）及其用法。
ms.date: 06/04/2018
ms.openlocfilehash: 801320bf7f3527ac70f1d5b9fe3d0ce537e50e93
ms.sourcegitcommit: 7b1ce327e8c84f115f007be4728d29a89efe11ef
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/13/2019
ms.locfileid: "70969778"
---
# <a name="dotnet-command"></a><span data-ttu-id="fcc0c-103">dotnet 命令</span><span class="sxs-lookup"><span data-stu-id="fcc0c-103">dotnet command</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="fcc0c-104">name</span><span class="sxs-lookup"><span data-stu-id="fcc0c-104">Name</span></span>

<span data-ttu-id="fcc0c-105">`dotnet` - 一款管理 .NET 源代码和二进制文件的工具。</span><span class="sxs-lookup"><span data-stu-id="fcc0c-105">`dotnet` - A tool for managing .NET source code and binaries.</span></span>

## <a name="synopsis"></a><span data-ttu-id="fcc0c-106">摘要</span><span class="sxs-lookup"><span data-stu-id="fcc0c-106">Synopsis</span></span>

<!-- markdownlint-disable MD025 -->

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="fcc0c-107">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="fcc0c-107">.NET Core 2.1</span></span>](#tab/netcore21)

```console
dotnet [command] [arguments] [--additional-deps] [--additionalprobingpath] [--depsfile]
    [-d|--diagnostics] [--fx-version] [-h|--help] [--info] [--list-runtimes] [--list-sdks] [--roll-forward-on-no-candidate-fx] [--runtimeconfig] [-v|--verbosity] [--version]
```

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="fcc0c-108">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="fcc0c-108">.NET Core 2.0</span></span>](#tab/netcore20)

```console
dotnet [command] [arguments] [--additional-deps] [--additionalprobingpath] [--depsfile]
    [-d|--diagnostics] [--fx-version] [-h|--help] [--info] [--roll-forward-on-no-candidate-fx]
    [--runtimeconfig] [-v|--verbosity] [--version]
```

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="fcc0c-109">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="fcc0c-109">.NET Core 1.x</span></span>](#tab/netcore1x)

```console
dotnet [command] [arguments] [--additionalprobingpath] [--depsfile] [-d|--diagnostics]
    [--fx-version] [-h|--help] [--info] [--runtimeconfig] [-v|--verbosity] [--version]
```

---

## <a name="description"></a><span data-ttu-id="fcc0c-110">说明</span><span class="sxs-lookup"><span data-stu-id="fcc0c-110">Description</span></span>

<span data-ttu-id="fcc0c-111">`dotnet` 是一款管理 .NET 源代码和二进制文件的工具。</span><span class="sxs-lookup"><span data-stu-id="fcc0c-111">`dotnet` is a tool for managing .NET source code and binaries.</span></span> <span data-ttu-id="fcc0c-112">它公开执行特定任务的命令，例如 [`dotnet build`](dotnet-build.md) 和 [`dotnet run`](dotnet-run.md)。</span><span class="sxs-lookup"><span data-stu-id="fcc0c-112">It exposes commands that perform specific tasks, such as [`dotnet build`](dotnet-build.md) and [`dotnet run`](dotnet-run.md).</span></span> <span data-ttu-id="fcc0c-113">每个命令都定义自己的参数。</span><span class="sxs-lookup"><span data-stu-id="fcc0c-113">Each command defines its own arguments.</span></span> <span data-ttu-id="fcc0c-114">在每个命令后键入 `--help` 以访问简要帮助文档。</span><span class="sxs-lookup"><span data-stu-id="fcc0c-114">Type `--help` after each command to access brief help documentation.</span></span>

<span data-ttu-id="fcc0c-115">可以使用 `dotnet` 来运行应用程序，方法是指定应用程序 DLL，如 `dotnet myapp.dll`.</span><span class="sxs-lookup"><span data-stu-id="fcc0c-115">`dotnet` can be used to run applications, by specifying an application DLL, such as `dotnet myapp.dll`.</span></span> <span data-ttu-id="fcc0c-116">要了解部署选项，请参阅 [.NET Core 应用程序部署](../deploying/index.md)。</span><span class="sxs-lookup"><span data-stu-id="fcc0c-116">See [.NET Core application deployment](../deploying/index.md) for to learn about deployment options.</span></span>

## <a name="options"></a><span data-ttu-id="fcc0c-117">选项</span><span class="sxs-lookup"><span data-stu-id="fcc0c-117">Options</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="fcc0c-118">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="fcc0c-118">.NET Core 2.1</span></span>](#tab/netcore21)

`--additional-deps <PATH>`

<span data-ttu-id="fcc0c-119">附加 .deps.json 文件的路径  。</span><span class="sxs-lookup"><span data-stu-id="fcc0c-119">Path to an additional *.deps.json* file.</span></span>

`--additionalprobingpath <PATH>`

<span data-ttu-id="fcc0c-120">包含要进行探测的探测策略和程序集的路径。</span><span class="sxs-lookup"><span data-stu-id="fcc0c-120">Path containing probing policy and assemblies to probe.</span></span>

`--depsfile`

<span data-ttu-id="fcc0c-121">deps.json 文件的路径  。</span><span class="sxs-lookup"><span data-stu-id="fcc0c-121">Path to a *deps.json* file.</span></span>

<span data-ttu-id="fcc0c-122">deps.json 文件包含依赖项、编译依赖项和用于解决程序集冲突的版本信息列表  。</span><span class="sxs-lookup"><span data-stu-id="fcc0c-122">A *deps.json* file contains a list of dependencies, compilation dependencies and version information used to address assembly conflicts.</span></span> <span data-ttu-id="fcc0c-123">有关此文件的详细信息，请参阅 GitHub 上的[运行时配置文件](https://github.com/dotnet/cli/blob/master/Documentation/specs/runtime-configuration-file.md)。</span><span class="sxs-lookup"><span data-stu-id="fcc0c-123">For more information about this file, see [Runtime Configuration Files](https://github.com/dotnet/cli/blob/master/Documentation/specs/runtime-configuration-file.md) on GitHub.</span></span>

`-d|--diagnostics`

<span data-ttu-id="fcc0c-124">启用诊断输出。</span><span class="sxs-lookup"><span data-stu-id="fcc0c-124">Enables diagnostic output.</span></span>

`--fx-version <VERSION>`

<span data-ttu-id="fcc0c-125">用于运行应用程序的 .NET Core 运行时版本。</span><span class="sxs-lookup"><span data-stu-id="fcc0c-125">Version of the .NET Core runtime to use to run the application.</span></span>

`-h|--help`

<span data-ttu-id="fcc0c-126">打印出给定命令的文档，如 `dotnet build --help`。</span><span class="sxs-lookup"><span data-stu-id="fcc0c-126">Prints out documentation for a given command, such as `dotnet build --help`.</span></span> <span data-ttu-id="fcc0c-127">`dotnet --help` 打印可用命令列表。</span><span class="sxs-lookup"><span data-stu-id="fcc0c-127">`dotnet --help` prints a list of available commands.</span></span>

`--info`

<span data-ttu-id="fcc0c-128">打印出有关 .NET Core 安装和计算机环境（如当前操作系统）的详细信息，并提交 .NET Core 版本的 SHA。</span><span class="sxs-lookup"><span data-stu-id="fcc0c-128">Prints out detailed information about a .NET Core installation and the machine environment, such as the current operating system, and commit SHA of the .NET Core version.</span></span>

`--list-runtimes`

<span data-ttu-id="fcc0c-129">显示已安装的 .NET Core 运行时。</span><span class="sxs-lookup"><span data-stu-id="fcc0c-129">Displays the installed .NET Core runtimes.</span></span>

`--list-sdks`

<span data-ttu-id="fcc0c-130">显示已安装的 .NET Core SDK。</span><span class="sxs-lookup"><span data-stu-id="fcc0c-130">Displays the installed .NET Core SDKs.</span></span>

`--roll-forward-on-no-candidate-fx <N>`

<span data-ttu-id="fcc0c-131">所需的共享框架不可用时，请定义行为。</span><span class="sxs-lookup"><span data-stu-id="fcc0c-131">Defines behavior when the required shared framework is not available.</span></span> <span data-ttu-id="fcc0c-132">`N` 可以是：</span><span class="sxs-lookup"><span data-stu-id="fcc0c-132">`N` can be:</span></span>

- <span data-ttu-id="fcc0c-133">`0` - 禁用次要版本前滚。</span><span class="sxs-lookup"><span data-stu-id="fcc0c-133">`0` - Disable even minor version roll forward.</span></span>
- <span data-ttu-id="fcc0c-134">`1` - 前滚次要版本，但不前滚主版本。</span><span class="sxs-lookup"><span data-stu-id="fcc0c-134">`1` - Roll forward on minor version, but not on major version.</span></span> <span data-ttu-id="fcc0c-135">这是默认行为。</span><span class="sxs-lookup"><span data-stu-id="fcc0c-135">This is the default behavior.</span></span>
- <span data-ttu-id="fcc0c-136">`2` - 前滚次要和主版本。</span><span class="sxs-lookup"><span data-stu-id="fcc0c-136">`2` - Roll forward on minor and major versions.</span></span>

 <span data-ttu-id="fcc0c-137">有关详细信息，请参阅[前滚](../whats-new/dotnet-core-2-1.md#roll-forward)。</span><span class="sxs-lookup"><span data-stu-id="fcc0c-137">For more information, see [Roll forward](../whats-new/dotnet-core-2-1.md#roll-forward).</span></span>

`--runtimeconfig`

<span data-ttu-id="fcc0c-138">runtimeconfig.template.json 文件的路径  。</span><span class="sxs-lookup"><span data-stu-id="fcc0c-138">Path to a *runtimeconfig.json* file.</span></span>

<span data-ttu-id="fcc0c-139">runtimeconfig.template.json 文件是包含运行时配置设置的配置文件  。</span><span class="sxs-lookup"><span data-stu-id="fcc0c-139">A *runtimeconfig.json* file is a configuration file containing runtime configuration settings.</span></span> <span data-ttu-id="fcc0c-140">有关详细信息，请参阅 GitHub 上的[运行时配置文件](https://github.com/dotnet/cli/blob/master/Documentation/specs/runtime-configuration-file.md)。</span><span class="sxs-lookup"><span data-stu-id="fcc0c-140">For more information, see [Runtime Configuration Files](https://github.com/dotnet/cli/blob/master/Documentation/specs/runtime-configuration-file.md) on GitHub.</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="fcc0c-141">设置命令的详细级别。</span><span class="sxs-lookup"><span data-stu-id="fcc0c-141">Sets the verbosity level of the command.</span></span> <span data-ttu-id="fcc0c-142">允许使用的值为 `q[uiet]`、`m[inimal]`、`n[ormal]`、`d[etailed]` 和 `diag[nostic]`。</span><span class="sxs-lookup"><span data-stu-id="fcc0c-142">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="fcc0c-143">并非在每个命令中均受支持；请参阅特定的命令页，确定此选项是否可用。</span><span class="sxs-lookup"><span data-stu-id="fcc0c-143">Not supported in every command; see specific command page to determine if this option is available.</span></span>

`--version`

<span data-ttu-id="fcc0c-144">打印使用中的 .NET Core SDK 版本。</span><span class="sxs-lookup"><span data-stu-id="fcc0c-144">Prints out the version of the .NET Core SDK in use.</span></span>

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="fcc0c-145">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="fcc0c-145">.NET Core 2.0</span></span>](#tab/netcore20)

`--additional-deps <PATH>`

<span data-ttu-id="fcc0c-146">附加 .deps.json 文件的路径  。</span><span class="sxs-lookup"><span data-stu-id="fcc0c-146">Path to an additional *.deps.json* file.</span></span>

`--additionalprobingpath <PATH>`

<span data-ttu-id="fcc0c-147">包含要进行探测的探测策略和程序集的路径。</span><span class="sxs-lookup"><span data-stu-id="fcc0c-147">Path containing probing policy and assemblies to probe.</span></span>

`--depsfile`

<span data-ttu-id="fcc0c-148">deps.json 文件的路径  。</span><span class="sxs-lookup"><span data-stu-id="fcc0c-148">Path to a *deps.json* file.</span></span>

<span data-ttu-id="fcc0c-149">deps.json 文件包含依赖项、编译依赖项和用于解决程序集冲突的版本信息列表  。</span><span class="sxs-lookup"><span data-stu-id="fcc0c-149">A *deps.json* file contains a list of dependencies, compilation dependencies and version information used to address assembly conflicts.</span></span> <span data-ttu-id="fcc0c-150">有关详细信息，请参阅 GitHub 上的[运行时配置文件](https://github.com/dotnet/cli/blob/master/Documentation/specs/runtime-configuration-file.md)。</span><span class="sxs-lookup"><span data-stu-id="fcc0c-150">For more details on this file, see [Runtime Configuration Files on GitHub](https://github.com/dotnet/cli/blob/master/Documentation/specs/runtime-configuration-file.md).</span></span>

`-d|--diagnostics`

<span data-ttu-id="fcc0c-151">启用诊断输出。</span><span class="sxs-lookup"><span data-stu-id="fcc0c-151">Enables diagnostic output.</span></span>

`--fx-version <VERSION>`

<span data-ttu-id="fcc0c-152">用于运行应用程序的 .NET Core 运行时版本。</span><span class="sxs-lookup"><span data-stu-id="fcc0c-152">Version of the .NET Core runtime to use to run the application.</span></span>

`-h|--help`

<span data-ttu-id="fcc0c-153">打印出给定命令的文档，如 `dotnet build --help`。</span><span class="sxs-lookup"><span data-stu-id="fcc0c-153">Prints out documentation for a given command, such as `dotnet build --help`.</span></span> <span data-ttu-id="fcc0c-154">`dotnet --help` 打印可用命令列表。</span><span class="sxs-lookup"><span data-stu-id="fcc0c-154">`dotnet --help` prints a list of available commands.</span></span>

`--info`

<span data-ttu-id="fcc0c-155">打印出有关 .NET Core 安装和计算机环境（如当前操作系统）的详细信息，并提交 .NET Core 版本的 SHA。</span><span class="sxs-lookup"><span data-stu-id="fcc0c-155">Prints out detailed information about a .NET Core installation and the machine environment, such as the current operating system, and commit SHA of the .NET Core version.</span></span>

`--roll-forward-on-no-candidate-fx`

 <span data-ttu-id="fcc0c-156">如果设置为 `0`，则禁用次要版本前滚。</span><span class="sxs-lookup"><span data-stu-id="fcc0c-156">Disables minor version roll forward, if set to `0`.</span></span> <span data-ttu-id="fcc0c-157">有关详细信息，请参阅[前滚](../whats-new/dotnet-core-2-1.md#roll-forward)。</span><span class="sxs-lookup"><span data-stu-id="fcc0c-157">For more information, see [Roll forward](../whats-new/dotnet-core-2-1.md#roll-forward).</span></span>

`--runtimeconfig`

<span data-ttu-id="fcc0c-158">runtimeconfig.template.json 文件的路径  。</span><span class="sxs-lookup"><span data-stu-id="fcc0c-158">Path to a *runtimeconfig.json* file.</span></span>

<span data-ttu-id="fcc0c-159">runtimeconfig.template.json 文件是包含运行时配置设置的配置文件  。</span><span class="sxs-lookup"><span data-stu-id="fcc0c-159">A *runtimeconfig.json* file is a configuration file containing runtime configuration settings.</span></span> <span data-ttu-id="fcc0c-160">有关详细信息，请参阅 GitHub 上的[运行时配置文件](https://github.com/dotnet/cli/blob/master/Documentation/specs/runtime-configuration-file.md)。</span><span class="sxs-lookup"><span data-stu-id="fcc0c-160">For more details, see [Runtime Configuration Files on GitHub](https://github.com/dotnet/cli/blob/master/Documentation/specs/runtime-configuration-file.md).</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="fcc0c-161">设置命令的详细级别。</span><span class="sxs-lookup"><span data-stu-id="fcc0c-161">Sets the verbosity level of the command.</span></span> <span data-ttu-id="fcc0c-162">允许使用的值为 `q[uiet]`、`m[inimal]`、`n[ormal]`、`d[etailed]` 和 `diag[nostic]`。</span><span class="sxs-lookup"><span data-stu-id="fcc0c-162">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="fcc0c-163">并非在每个命令中均受支持；请参阅特定的命令页，确定此选项是否可用。</span><span class="sxs-lookup"><span data-stu-id="fcc0c-163">Not supported in every command; see specific command page to determine if this option is available.</span></span>

`--version`

<span data-ttu-id="fcc0c-164">打印使用中的 .NET Core SDK 版本。</span><span class="sxs-lookup"><span data-stu-id="fcc0c-164">Prints out the version of the .NET Core SDK in use.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="fcc0c-165">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="fcc0c-165">.NET Core 1.x</span></span>](#tab/netcore1x)

`--additionalprobingpath <PATH>`

<span data-ttu-id="fcc0c-166">包含要进行探测的探测策略和程序集的路径。</span><span class="sxs-lookup"><span data-stu-id="fcc0c-166">Path containing probing policy and assemblies to probe.</span></span>

`--depsfile`

<span data-ttu-id="fcc0c-167">deps.json 文件的路径  。</span><span class="sxs-lookup"><span data-stu-id="fcc0c-167">Path to a *deps.json* file.</span></span>

<span data-ttu-id="fcc0c-168">deps.json 文件包含依赖项、编译依赖项和用于解决程序集冲突的版本信息列表  。</span><span class="sxs-lookup"><span data-stu-id="fcc0c-168">A *deps.json* file contains a list of dependencies, compilation dependencies and version information used to address assembly conflicts.</span></span> <span data-ttu-id="fcc0c-169">有关详细信息，请参阅 GitHub 上的[运行时配置文件](https://github.com/dotnet/cli/blob/master/Documentation/specs/runtime-configuration-file.md)。</span><span class="sxs-lookup"><span data-stu-id="fcc0c-169">For more details on this file, see [Runtime Configuration Files on GitHub](https://github.com/dotnet/cli/blob/master/Documentation/specs/runtime-configuration-file.md).</span></span>

`-d|--diagnostics`

<span data-ttu-id="fcc0c-170">启用诊断输出。</span><span class="sxs-lookup"><span data-stu-id="fcc0c-170">Enables diagnostic output.</span></span>

`--fx-version <VERSION>`

<span data-ttu-id="fcc0c-171">用于运行应用程序的 .NET Core 运行时版本。</span><span class="sxs-lookup"><span data-stu-id="fcc0c-171">Version of the .NET Core runtime to use to run the application.</span></span>

`-h|--help`

<span data-ttu-id="fcc0c-172">打印出给定命令的文档，如 `dotnet build --help`。</span><span class="sxs-lookup"><span data-stu-id="fcc0c-172">Prints out documentation for a given command, such as `dotnet build --help`.</span></span> <span data-ttu-id="fcc0c-173">`dotnet --help` 打印可用命令列表。</span><span class="sxs-lookup"><span data-stu-id="fcc0c-173">`dotnet --help` prints a list of available commands.</span></span>

`--info`

<span data-ttu-id="fcc0c-174">打印出有关 .NET Core 安装和计算机环境（如当前操作系统）的详细信息，并提交 .NET Core 版本的 SHA。</span><span class="sxs-lookup"><span data-stu-id="fcc0c-174">Prints out detailed information about a .NET Core installation and the machine environment, such as the current operating system, and commit SHA of the .NET Core version.</span></span>

`--runtimeconfig`

<span data-ttu-id="fcc0c-175">runtimeconfig.template.json 文件的路径  。</span><span class="sxs-lookup"><span data-stu-id="fcc0c-175">Path to a *runtimeconfig.json* file.</span></span>

<span data-ttu-id="fcc0c-176">runtimeconfig.template.json 文件是包含运行时配置设置的配置文件  。</span><span class="sxs-lookup"><span data-stu-id="fcc0c-176">A *runtimeconfig.json* file is a configuration file containing runtime configuration settings.</span></span> <span data-ttu-id="fcc0c-177">有关详细信息，请参阅 GitHub 上的[运行时配置文件](https://github.com/dotnet/cli/blob/master/Documentation/specs/runtime-configuration-file.md)。</span><span class="sxs-lookup"><span data-stu-id="fcc0c-177">For more details, see [Runtime Configuration Files on GitHub](https://github.com/dotnet/cli/blob/master/Documentation/specs/runtime-configuration-file.md).</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="fcc0c-178">设置命令的详细级别。</span><span class="sxs-lookup"><span data-stu-id="fcc0c-178">Sets the verbosity level of the command.</span></span> <span data-ttu-id="fcc0c-179">允许使用的值为 `q[uiet]`、`m[inimal]`、`n[ormal]`、`d[etailed]` 和 `diag[nostic]`。</span><span class="sxs-lookup"><span data-stu-id="fcc0c-179">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="fcc0c-180">并非在每个命令中均受支持；请参阅特定的命令页，确定此选项是否可用。</span><span class="sxs-lookup"><span data-stu-id="fcc0c-180">Not supported in every command; see specific command page to determine if this option is available.</span></span>

`--version`

<span data-ttu-id="fcc0c-181">打印使用中的 .NET Core SDK 版本。</span><span class="sxs-lookup"><span data-stu-id="fcc0c-181">Prints out the version of the .NET Core SDK in use.</span></span>

---

## <a name="dotnet-commands"></a><span data-ttu-id="fcc0c-182">dotnet 命令</span><span class="sxs-lookup"><span data-stu-id="fcc0c-182">dotnet commands</span></span>

### <a name="general"></a><span data-ttu-id="fcc0c-183">常规</span><span class="sxs-lookup"><span data-stu-id="fcc0c-183">General</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="fcc0c-184">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="fcc0c-184">.NET Core 2.1</span></span>](#tab/netcore21)

| <span data-ttu-id="fcc0c-185">命令</span><span class="sxs-lookup"><span data-stu-id="fcc0c-185">Command</span></span>                                       | <span data-ttu-id="fcc0c-186">函数</span><span class="sxs-lookup"><span data-stu-id="fcc0c-186">Function</span></span>                                                            |
| --------------------------------------------- | ------------------------------------------------------------------- |
| [<span data-ttu-id="fcc0c-187">dotnet build</span><span class="sxs-lookup"><span data-stu-id="fcc0c-187">dotnet build</span></span>](dotnet-build.md)               | <span data-ttu-id="fcc0c-188">生成 .NET Core 应用程序。</span><span class="sxs-lookup"><span data-stu-id="fcc0c-188">Builds a .NET Core application.</span></span>                                     |
| [<span data-ttu-id="fcc0c-189">dotnet build-server</span><span class="sxs-lookup"><span data-stu-id="fcc0c-189">dotnet build-server</span></span>](dotnet-build-server.md) | <span data-ttu-id="fcc0c-190">与通过生成启动的服务器进行交互。</span><span class="sxs-lookup"><span data-stu-id="fcc0c-190">Interacts with servers started by a build.</span></span>                          |
| [<span data-ttu-id="fcc0c-191">dotnet clean</span><span class="sxs-lookup"><span data-stu-id="fcc0c-191">dotnet clean</span></span>](dotnet-clean.md)               | <span data-ttu-id="fcc0c-192">清除生成输出。</span><span class="sxs-lookup"><span data-stu-id="fcc0c-192">Clean build outputs.</span></span>                                                |
| [<span data-ttu-id="fcc0c-193">dotnet help</span><span class="sxs-lookup"><span data-stu-id="fcc0c-193">dotnet help</span></span>](dotnet-help.md)                 | <span data-ttu-id="fcc0c-194">显示命令更详细的在线文档。</span><span class="sxs-lookup"><span data-stu-id="fcc0c-194">Shows more detailed documentation online for the command.</span></span>           |
| [<span data-ttu-id="fcc0c-195">dotnet migrate</span><span class="sxs-lookup"><span data-stu-id="fcc0c-195">dotnet migrate</span></span>](dotnet-migrate.md)           | <span data-ttu-id="fcc0c-196">将有效的预览版 2 项目迁移到 .NET Core SDK 1.0 项目。</span><span class="sxs-lookup"><span data-stu-id="fcc0c-196">Migrates a valid Preview 2 project to a .NET Core SDK 1.0 project.</span></span>  |
| [<span data-ttu-id="fcc0c-197">dotnet msbuild</span><span class="sxs-lookup"><span data-stu-id="fcc0c-197">dotnet msbuild</span></span>](dotnet-msbuild.md)           | <span data-ttu-id="fcc0c-198">提供对 MSBuild 命令行的访问权限。</span><span class="sxs-lookup"><span data-stu-id="fcc0c-198">Provides access to the MSBuild command line.</span></span>                        |
| [<span data-ttu-id="fcc0c-199">dotnet new</span><span class="sxs-lookup"><span data-stu-id="fcc0c-199">dotnet new</span></span>](dotnet-new.md)                   | <span data-ttu-id="fcc0c-200">为给定的模板初始化 C# 或 F# 项目。</span><span class="sxs-lookup"><span data-stu-id="fcc0c-200">Initializes a C# or F# project for a given template.</span></span>                |
| [<span data-ttu-id="fcc0c-201">dotnet pack</span><span class="sxs-lookup"><span data-stu-id="fcc0c-201">dotnet pack</span></span>](dotnet-pack.md)                 | <span data-ttu-id="fcc0c-202">创建代码的 NuGet 包。</span><span class="sxs-lookup"><span data-stu-id="fcc0c-202">Creates a NuGet package of your code.</span></span>                               |
| [<span data-ttu-id="fcc0c-203">dotnet publish</span><span class="sxs-lookup"><span data-stu-id="fcc0c-203">dotnet publish</span></span>](dotnet-publish.md)           | <span data-ttu-id="fcc0c-204">发布 .NET 依赖于框架或独立应用程序。</span><span class="sxs-lookup"><span data-stu-id="fcc0c-204">Publishes a .NET framework-dependent or self-contained application.</span></span> |
| [<span data-ttu-id="fcc0c-205">dotnet restore</span><span class="sxs-lookup"><span data-stu-id="fcc0c-205">dotnet restore</span></span>](dotnet-restore.md)           | <span data-ttu-id="fcc0c-206">还原给定应用程序的依赖项。</span><span class="sxs-lookup"><span data-stu-id="fcc0c-206">Restores the dependencies for a given application.</span></span>                  |
| [<span data-ttu-id="fcc0c-207">dotnet run</span><span class="sxs-lookup"><span data-stu-id="fcc0c-207">dotnet run</span></span>](dotnet-run.md)                   | <span data-ttu-id="fcc0c-208">从源运行应用程序。</span><span class="sxs-lookup"><span data-stu-id="fcc0c-208">Runs the application from source.</span></span>                                   |
| [<span data-ttu-id="fcc0c-209">dotnet sln</span><span class="sxs-lookup"><span data-stu-id="fcc0c-209">dotnet sln</span></span>](dotnet-sln.md)                   | <span data-ttu-id="fcc0c-210">用于添加、删除和列出解决方案文件中项目的选项。</span><span class="sxs-lookup"><span data-stu-id="fcc0c-210">Options to add, remove, and list projects in a solution file.</span></span>       |
| [<span data-ttu-id="fcc0c-211">dotnet store</span><span class="sxs-lookup"><span data-stu-id="fcc0c-211">dotnet store</span></span>](dotnet-store.md)               | <span data-ttu-id="fcc0c-212">将程序集存储到运行时包存储区。</span><span class="sxs-lookup"><span data-stu-id="fcc0c-212">Stores assemblies in the runtime package store.</span></span>                     |
| [<span data-ttu-id="fcc0c-213">dotnet test</span><span class="sxs-lookup"><span data-stu-id="fcc0c-213">dotnet test</span></span>](dotnet-test.md)                 | <span data-ttu-id="fcc0c-214">使用测试运行程序运行测试。</span><span class="sxs-lookup"><span data-stu-id="fcc0c-214">Runs tests using a test runner.</span></span>                                     |

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="fcc0c-215">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="fcc0c-215">.NET Core 2.0</span></span>](#tab/netcore20)

| <span data-ttu-id="fcc0c-216">命令</span><span class="sxs-lookup"><span data-stu-id="fcc0c-216">Command</span></span>                             | <span data-ttu-id="fcc0c-217">函数</span><span class="sxs-lookup"><span data-stu-id="fcc0c-217">Function</span></span>                                                            |
| ----------------------------------- | ------------------------------------------------------------------- |
| [<span data-ttu-id="fcc0c-218">dotnet build</span><span class="sxs-lookup"><span data-stu-id="fcc0c-218">dotnet build</span></span>](dotnet-build.md)     | <span data-ttu-id="fcc0c-219">生成 .NET Core 应用程序。</span><span class="sxs-lookup"><span data-stu-id="fcc0c-219">Builds a .NET Core application.</span></span>                                     |
| [<span data-ttu-id="fcc0c-220">dotnet clean</span><span class="sxs-lookup"><span data-stu-id="fcc0c-220">dotnet clean</span></span>](dotnet-clean.md)     | <span data-ttu-id="fcc0c-221">清除生成输出。</span><span class="sxs-lookup"><span data-stu-id="fcc0c-221">Clean build outputs.</span></span>                                              |
| [<span data-ttu-id="fcc0c-222">dotnet help</span><span class="sxs-lookup"><span data-stu-id="fcc0c-222">dotnet help</span></span>](dotnet-help.md)       | <span data-ttu-id="fcc0c-223">显示命令更详细的在线文档。</span><span class="sxs-lookup"><span data-stu-id="fcc0c-223">Shows more detailed documentation online for the command.</span></span>           |
| [<span data-ttu-id="fcc0c-224">dotnet migrate</span><span class="sxs-lookup"><span data-stu-id="fcc0c-224">dotnet migrate</span></span>](dotnet-migrate.md) | <span data-ttu-id="fcc0c-225">将有效的预览版 2 项目迁移到 .NET Core SDK 1.0 项目。</span><span class="sxs-lookup"><span data-stu-id="fcc0c-225">Migrates a valid Preview 2 project to a .NET Core SDK 1.0 project.</span></span>  |
| [<span data-ttu-id="fcc0c-226">dotnet msbuild</span><span class="sxs-lookup"><span data-stu-id="fcc0c-226">dotnet msbuild</span></span>](dotnet-msbuild.md) | <span data-ttu-id="fcc0c-227">提供对 MSBuild 命令行的访问权限。</span><span class="sxs-lookup"><span data-stu-id="fcc0c-227">Provides access to the MSBuild command line.</span></span>                        |
| [<span data-ttu-id="fcc0c-228">dotnet new</span><span class="sxs-lookup"><span data-stu-id="fcc0c-228">dotnet new</span></span>](dotnet-new.md)         | <span data-ttu-id="fcc0c-229">为给定的模板初始化 C# 或 F# 项目。</span><span class="sxs-lookup"><span data-stu-id="fcc0c-229">Initializes a C# or F# project for a given template.</span></span>                |
| [<span data-ttu-id="fcc0c-230">dotnet pack</span><span class="sxs-lookup"><span data-stu-id="fcc0c-230">dotnet pack</span></span>](dotnet-pack.md)       | <span data-ttu-id="fcc0c-231">创建代码的 NuGet 包。</span><span class="sxs-lookup"><span data-stu-id="fcc0c-231">Creates a NuGet package of your code.</span></span>                               |
| [<span data-ttu-id="fcc0c-232">dotnet publish</span><span class="sxs-lookup"><span data-stu-id="fcc0c-232">dotnet publish</span></span>](dotnet-publish.md) | <span data-ttu-id="fcc0c-233">发布 .NET 依赖于框架或独立应用程序。</span><span class="sxs-lookup"><span data-stu-id="fcc0c-233">Publishes a .NET framework-dependent or self-contained application.</span></span> |
| [<span data-ttu-id="fcc0c-234">dotnet restore</span><span class="sxs-lookup"><span data-stu-id="fcc0c-234">dotnet restore</span></span>](dotnet-restore.md) | <span data-ttu-id="fcc0c-235">还原给定应用程序的依赖项。</span><span class="sxs-lookup"><span data-stu-id="fcc0c-235">Restores the dependencies for a given application.</span></span>                  |
| [<span data-ttu-id="fcc0c-236">dotnet run</span><span class="sxs-lookup"><span data-stu-id="fcc0c-236">dotnet run</span></span>](dotnet-run.md)         | <span data-ttu-id="fcc0c-237">从源运行应用程序。</span><span class="sxs-lookup"><span data-stu-id="fcc0c-237">Runs the application from source.</span></span>                                   |
| [<span data-ttu-id="fcc0c-238">dotnet sln</span><span class="sxs-lookup"><span data-stu-id="fcc0c-238">dotnet sln</span></span>](dotnet-sln.md)         | <span data-ttu-id="fcc0c-239">用于添加、删除和列出解决方案文件中项目的选项。</span><span class="sxs-lookup"><span data-stu-id="fcc0c-239">Options to add, remove, and list projects in a solution file.</span></span>       |
| [<span data-ttu-id="fcc0c-240">dotnet store</span><span class="sxs-lookup"><span data-stu-id="fcc0c-240">dotnet store</span></span>](dotnet-store.md)     | <span data-ttu-id="fcc0c-241">将程序集存储到运行时包存储区。</span><span class="sxs-lookup"><span data-stu-id="fcc0c-241">Stores assemblies in the runtime package store.</span></span>                     |
| [<span data-ttu-id="fcc0c-242">dotnet test</span><span class="sxs-lookup"><span data-stu-id="fcc0c-242">dotnet test</span></span>](dotnet-test.md)       | <span data-ttu-id="fcc0c-243">使用测试运行程序运行测试。</span><span class="sxs-lookup"><span data-stu-id="fcc0c-243">Runs tests using a test runner.</span></span>                                     |

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="fcc0c-244">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="fcc0c-244">.NET Core 1.x</span></span>](#tab/netcore1x)

| <span data-ttu-id="fcc0c-245">命令</span><span class="sxs-lookup"><span data-stu-id="fcc0c-245">Command</span></span>                             | <span data-ttu-id="fcc0c-246">函数</span><span class="sxs-lookup"><span data-stu-id="fcc0c-246">Function</span></span>                                                            |
| ----------------------------------- | ------------------------------------------------------------------- |
| [<span data-ttu-id="fcc0c-247">dotnet build</span><span class="sxs-lookup"><span data-stu-id="fcc0c-247">dotnet build</span></span>](dotnet-build.md)     | <span data-ttu-id="fcc0c-248">生成 .NET Core 应用程序。</span><span class="sxs-lookup"><span data-stu-id="fcc0c-248">Builds a .NET Core application.</span></span>                                     |
| [<span data-ttu-id="fcc0c-249">dotnet clean</span><span class="sxs-lookup"><span data-stu-id="fcc0c-249">dotnet clean</span></span>](dotnet-clean.md)     | <span data-ttu-id="fcc0c-250">清除生成输出。</span><span class="sxs-lookup"><span data-stu-id="fcc0c-250">Clean build outputs.</span></span>                                              |
| [<span data-ttu-id="fcc0c-251">dotnet migrate</span><span class="sxs-lookup"><span data-stu-id="fcc0c-251">dotnet migrate</span></span>](dotnet-migrate.md) | <span data-ttu-id="fcc0c-252">将有效的预览版 2 项目迁移到 .NET Core SDK 1.0 项目。</span><span class="sxs-lookup"><span data-stu-id="fcc0c-252">Migrates a valid Preview 2 project to a .NET Core SDK 1.0 project.</span></span>  |
| [<span data-ttu-id="fcc0c-253">dotnet msbuild</span><span class="sxs-lookup"><span data-stu-id="fcc0c-253">dotnet msbuild</span></span>](dotnet-msbuild.md) | <span data-ttu-id="fcc0c-254">提供对 MSBuild 命令行的访问权限。</span><span class="sxs-lookup"><span data-stu-id="fcc0c-254">Provides access to the MSBuild command line.</span></span>                        |
| [<span data-ttu-id="fcc0c-255">dotnet new</span><span class="sxs-lookup"><span data-stu-id="fcc0c-255">dotnet new</span></span>](dotnet-new.md)         | <span data-ttu-id="fcc0c-256">为给定的模板初始化 C# 或 F# 项目。</span><span class="sxs-lookup"><span data-stu-id="fcc0c-256">Initializes a C# or F# project for a given template.</span></span>                |
| [<span data-ttu-id="fcc0c-257">dotnet pack</span><span class="sxs-lookup"><span data-stu-id="fcc0c-257">dotnet pack</span></span>](dotnet-pack.md)       | <span data-ttu-id="fcc0c-258">创建代码的 NuGet 包。</span><span class="sxs-lookup"><span data-stu-id="fcc0c-258">Creates a NuGet package of your code.</span></span>                               |
| [<span data-ttu-id="fcc0c-259">dotnet publish</span><span class="sxs-lookup"><span data-stu-id="fcc0c-259">dotnet publish</span></span>](dotnet-publish.md) | <span data-ttu-id="fcc0c-260">发布 .NET 依赖于框架或独立应用程序。</span><span class="sxs-lookup"><span data-stu-id="fcc0c-260">Publishes a .NET framework-dependent or self-contained application.</span></span> |
| [<span data-ttu-id="fcc0c-261">dotnet restore</span><span class="sxs-lookup"><span data-stu-id="fcc0c-261">dotnet restore</span></span>](dotnet-restore.md) | <span data-ttu-id="fcc0c-262">还原给定应用程序的依赖项。</span><span class="sxs-lookup"><span data-stu-id="fcc0c-262">Restores the dependencies for a given application.</span></span>                  |
| [<span data-ttu-id="fcc0c-263">dotnet run</span><span class="sxs-lookup"><span data-stu-id="fcc0c-263">dotnet run</span></span>](dotnet-run.md)         | <span data-ttu-id="fcc0c-264">从源运行应用程序。</span><span class="sxs-lookup"><span data-stu-id="fcc0c-264">Runs the application from source.</span></span>                                   |
| [<span data-ttu-id="fcc0c-265">dotnet sln</span><span class="sxs-lookup"><span data-stu-id="fcc0c-265">dotnet sln</span></span>](dotnet-sln.md)         | <span data-ttu-id="fcc0c-266">用于添加、删除和列出解决方案文件中项目的选项。</span><span class="sxs-lookup"><span data-stu-id="fcc0c-266">Options to add, remove, and list projects in a solution file.</span></span>       |
| [<span data-ttu-id="fcc0c-267">dotnet test</span><span class="sxs-lookup"><span data-stu-id="fcc0c-267">dotnet test</span></span>](dotnet-test.md)       | <span data-ttu-id="fcc0c-268">使用测试运行程序运行测试。</span><span class="sxs-lookup"><span data-stu-id="fcc0c-268">Runs tests using a test runner.</span></span>                                     |

---

### <a name="project-references"></a><span data-ttu-id="fcc0c-269">项目引用</span><span class="sxs-lookup"><span data-stu-id="fcc0c-269">Project references</span></span>

<span data-ttu-id="fcc0c-270">命令</span><span class="sxs-lookup"><span data-stu-id="fcc0c-270">Command</span></span> | <span data-ttu-id="fcc0c-271">函数</span><span class="sxs-lookup"><span data-stu-id="fcc0c-271">Function</span></span>
--- | ---
[<span data-ttu-id="fcc0c-272">dotnet add reference</span><span class="sxs-lookup"><span data-stu-id="fcc0c-272">dotnet add reference</span></span>](dotnet-add-reference.md) | <span data-ttu-id="fcc0c-273">添加项目引用。</span><span class="sxs-lookup"><span data-stu-id="fcc0c-273">Adds a project reference.</span></span>
[<span data-ttu-id="fcc0c-274">dotnet list reference</span><span class="sxs-lookup"><span data-stu-id="fcc0c-274">dotnet list reference</span></span>](dotnet-list-reference.md) | <span data-ttu-id="fcc0c-275">列出项目引用。</span><span class="sxs-lookup"><span data-stu-id="fcc0c-275">Lists project references.</span></span>
[<span data-ttu-id="fcc0c-276">dotnet remove reference</span><span class="sxs-lookup"><span data-stu-id="fcc0c-276">dotnet remove reference</span></span>](dotnet-remove-reference.md) | <span data-ttu-id="fcc0c-277">删除项目引用。</span><span class="sxs-lookup"><span data-stu-id="fcc0c-277">Removes a project reference.</span></span>

### <a name="nuget-packages"></a><span data-ttu-id="fcc0c-278">NuGet 包</span><span class="sxs-lookup"><span data-stu-id="fcc0c-278">NuGet packages</span></span>

<span data-ttu-id="fcc0c-279">命令</span><span class="sxs-lookup"><span data-stu-id="fcc0c-279">Command</span></span> | <span data-ttu-id="fcc0c-280">函数</span><span class="sxs-lookup"><span data-stu-id="fcc0c-280">Function</span></span>
--- | ---
[<span data-ttu-id="fcc0c-281">dotnet add package</span><span class="sxs-lookup"><span data-stu-id="fcc0c-281">dotnet add package</span></span>](dotnet-add-package.md) | <span data-ttu-id="fcc0c-282">添加 NuGet 包。</span><span class="sxs-lookup"><span data-stu-id="fcc0c-282">Adds a NuGet package.</span></span>
[<span data-ttu-id="fcc0c-283">dotnet remove package</span><span class="sxs-lookup"><span data-stu-id="fcc0c-283">dotnet remove package</span></span>](dotnet-remove-package.md) | <span data-ttu-id="fcc0c-284">删除 NuGet 包。</span><span class="sxs-lookup"><span data-stu-id="fcc0c-284">Removes a NuGet package.</span></span>

### <a name="nuget-commands"></a><span data-ttu-id="fcc0c-285">NuGet 命令</span><span class="sxs-lookup"><span data-stu-id="fcc0c-285">NuGet commands</span></span>

<span data-ttu-id="fcc0c-286">命令</span><span class="sxs-lookup"><span data-stu-id="fcc0c-286">Command</span></span> | <span data-ttu-id="fcc0c-287">函数</span><span class="sxs-lookup"><span data-stu-id="fcc0c-287">Function</span></span>
--- | ---
[<span data-ttu-id="fcc0c-288">dotnet nuget delete</span><span class="sxs-lookup"><span data-stu-id="fcc0c-288">dotnet nuget delete</span></span>](dotnet-nuget-delete.md) | <span data-ttu-id="fcc0c-289">从服务器删除或取消列出包。</span><span class="sxs-lookup"><span data-stu-id="fcc0c-289">Deletes or unlists a package from the server.</span></span>
[<span data-ttu-id="fcc0c-290">dotnet nuget locals</span><span class="sxs-lookup"><span data-stu-id="fcc0c-290">dotnet nuget locals</span></span>](dotnet-nuget-locals.md) | <span data-ttu-id="fcc0c-291">清除或列出本地 NuGet 资源，例如 http 请求缓存、临时缓存或计算机范围的全局包文件夹。</span><span class="sxs-lookup"><span data-stu-id="fcc0c-291">Clears or lists local NuGet resources such as http-request cache, temporary cache, or machine-wide global packages folder.</span></span>
[<span data-ttu-id="fcc0c-292">dotnet nuget push</span><span class="sxs-lookup"><span data-stu-id="fcc0c-292">dotnet nuget push</span></span>](dotnet-nuget-push.md) | <span data-ttu-id="fcc0c-293">将包推送到服务器，并将其发布。</span><span class="sxs-lookup"><span data-stu-id="fcc0c-293">Pushes a package to the server and publishes it.</span></span>

### <a name="global-tools-commands"></a><span data-ttu-id="fcc0c-294">全局工具命令</span><span class="sxs-lookup"><span data-stu-id="fcc0c-294">Global Tools commands</span></span>

<span data-ttu-id="fcc0c-295">[.NET Core 全局工具](global-tools.md)可与 .NET Core SDK 2.1.300 一起开始使用：</span><span class="sxs-lookup"><span data-stu-id="fcc0c-295">[.NET Core Global Tools](global-tools.md) are available starting with .NET Core SDK 2.1.300:</span></span>

<span data-ttu-id="fcc0c-296">命令</span><span class="sxs-lookup"><span data-stu-id="fcc0c-296">Command</span></span> | <span data-ttu-id="fcc0c-297">函数</span><span class="sxs-lookup"><span data-stu-id="fcc0c-297">Function</span></span>
--- | ---
[<span data-ttu-id="fcc0c-298">dotnet tool install</span><span class="sxs-lookup"><span data-stu-id="fcc0c-298">dotnet tool install</span></span>](dotnet-tool-install.md) | <span data-ttu-id="fcc0c-299">在计算机上安装全局工具。</span><span class="sxs-lookup"><span data-stu-id="fcc0c-299">Installs a Global Tool on your machine.</span></span>
[<span data-ttu-id="fcc0c-300">dotnet tool list</span><span class="sxs-lookup"><span data-stu-id="fcc0c-300">dotnet tool list</span></span>](dotnet-tool-list.md) | <span data-ttu-id="fcc0c-301">列出当前安装在计算机上的默认目录中或指定路径中的所有全局工具。</span><span class="sxs-lookup"><span data-stu-id="fcc0c-301">Lists all Global Tools currently installed in the default directory on your machine or in the specified path.</span></span>
[<span data-ttu-id="fcc0c-302">dotnet tool uninstall</span><span class="sxs-lookup"><span data-stu-id="fcc0c-302">dotnet tool uninstall</span></span>](dotnet-tool-uninstall.md) | <span data-ttu-id="fcc0c-303">从计算机中卸载全局工具。</span><span class="sxs-lookup"><span data-stu-id="fcc0c-303">Uninstalls a Global Tool from your machine.</span></span>
[<span data-ttu-id="fcc0c-304">dotnet tool update</span><span class="sxs-lookup"><span data-stu-id="fcc0c-304">dotnet tool update</span></span>](dotnet-tool-update.md) | <span data-ttu-id="fcc0c-305">在计算机上更新全局工具。</span><span class="sxs-lookup"><span data-stu-id="fcc0c-305">Updates a Global Tool on your machine.</span></span>

### <a name="additional-tools"></a><span data-ttu-id="fcc0c-306">其他工具</span><span class="sxs-lookup"><span data-stu-id="fcc0c-306">Additional tools</span></span>

<span data-ttu-id="fcc0c-307">自 .NET Core SDK 2.1.300 开始，许多使用 `DotnetCliToolReference` 的仅在每个项目的基础上可用的工具现作为 .NET Core SDK 的一部分提供。</span><span class="sxs-lookup"><span data-stu-id="fcc0c-307">Starting with .NET Core SDK 2.1.300, a number of tools that were available only on a per project basis using `DotnetCliToolReference` are now available as part of the .NET Core SDK.</span></span> <span data-ttu-id="fcc0c-308">下表中列出了这些工具：</span><span class="sxs-lookup"><span data-stu-id="fcc0c-308">These tools are listed in the following table:</span></span>

| <span data-ttu-id="fcc0c-309">工具</span><span class="sxs-lookup"><span data-stu-id="fcc0c-309">Tool</span></span>                                              | <span data-ttu-id="fcc0c-310">函数</span><span class="sxs-lookup"><span data-stu-id="fcc0c-310">Function</span></span>                                                     |
| ------------------------------------------------- | ------------------------------------------------------------ |
| <span data-ttu-id="fcc0c-311">dev-certs</span><span class="sxs-lookup"><span data-stu-id="fcc0c-311">dev-certs</span></span>                                         | <span data-ttu-id="fcc0c-312">创建和管理开发证书。</span><span class="sxs-lookup"><span data-stu-id="fcc0c-312">Creates and manages development certificates.</span></span>                |
| [<span data-ttu-id="fcc0c-313">ef</span><span class="sxs-lookup"><span data-stu-id="fcc0c-313">ef</span></span>](/ef/core/miscellaneous/cli/dotnet)           | <span data-ttu-id="fcc0c-314">Entity Framework Core 命令行工具。</span><span class="sxs-lookup"><span data-stu-id="fcc0c-314">Entity Framework Core command-line tools.</span></span>                    |
| <span data-ttu-id="fcc0c-315">sql-cache</span><span class="sxs-lookup"><span data-stu-id="fcc0c-315">sql-cache</span></span>                                         | <span data-ttu-id="fcc0c-316">SQL Server 缓存命令行工具。</span><span class="sxs-lookup"><span data-stu-id="fcc0c-316">SQL Server cache command-line tools.</span></span>                         |
| [<span data-ttu-id="fcc0c-317">user-secrets</span><span class="sxs-lookup"><span data-stu-id="fcc0c-317">user-secrets</span></span>](/aspnet/core/security/app-secrets) | <span data-ttu-id="fcc0c-318">管理开发用户机密。</span><span class="sxs-lookup"><span data-stu-id="fcc0c-318">Manages development user secrets.</span></span>                            |
| [<span data-ttu-id="fcc0c-319">watch</span><span class="sxs-lookup"><span data-stu-id="fcc0c-319">watch</span></span>](/aspnet/core/tutorials/dotnet-watch)      | <span data-ttu-id="fcc0c-320">启动文件观察程序，以在更改文件时运行命令。</span><span class="sxs-lookup"><span data-stu-id="fcc0c-320">Starts a file watcher that runs a command when files change.</span></span> |

<span data-ttu-id="fcc0c-321">有关每个工具的详细信息，请键入 `dotnet <tool-name> --help`。</span><span class="sxs-lookup"><span data-stu-id="fcc0c-321">For more information about each tool, type `dotnet <tool-name> --help`.</span></span>

## <a name="examples"></a><span data-ttu-id="fcc0c-322">示例</span><span class="sxs-lookup"><span data-stu-id="fcc0c-322">Examples</span></span>

<span data-ttu-id="fcc0c-323">创建新的 .NET Core 控制台应用程序：</span><span class="sxs-lookup"><span data-stu-id="fcc0c-323">Creates a new .NET Core console application:</span></span>

`dotnet new console`

<span data-ttu-id="fcc0c-324">还原给定应用程序的依赖项：</span><span class="sxs-lookup"><span data-stu-id="fcc0c-324">Restore dependencies for a given application:</span></span>

`dotnet restore`

[!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]

<span data-ttu-id="fcc0c-325">生成给定目录中的项目及其依赖项：</span><span class="sxs-lookup"><span data-stu-id="fcc0c-325">Build a project and its dependencies in a given directory:</span></span>

`dotnet build`

<span data-ttu-id="fcc0c-326">运行应用程序 DLL，如 `myapp.dll`：</span><span class="sxs-lookup"><span data-stu-id="fcc0c-326">Run an application DLL, such as `myapp.dll`:</span></span>

`dotnet myapp.dll`

## <a name="environment-variables"></a><span data-ttu-id="fcc0c-327">环境变量</span><span class="sxs-lookup"><span data-stu-id="fcc0c-327">Environment variables</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="fcc0c-328">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="fcc0c-328">.NET Core 2.1</span></span>](#tab/netcore21)

`DOTNET_PACKAGES`

<span data-ttu-id="fcc0c-329">全局包文件夹。</span><span class="sxs-lookup"><span data-stu-id="fcc0c-329">The global packages folder.</span></span> <span data-ttu-id="fcc0c-330">如果未设置，则默认为 Unix 上的 `~/.nuget/packages` 或 Windows 上的 `%userprofile%\.nuget\packages`。</span><span class="sxs-lookup"><span data-stu-id="fcc0c-330">If not set, it defaults to `~/.nuget/packages` on Unix or `%userprofile%\.nuget\packages` on Windows.</span></span>

`DOTNET_SERVICING`

<span data-ttu-id="fcc0c-331">指定加载运行时期间共享主机要使用的服务索引的位置。</span><span class="sxs-lookup"><span data-stu-id="fcc0c-331">Specifies the location of the servicing index to use by the shared host when loading the runtime.</span></span>

`DOTNET_CLI_TELEMETRY_OPTOUT`

<span data-ttu-id="fcc0c-332">指定是否收集并向 Microsoft 发送 .NET Core 工具使用情况的相关数据。</span><span class="sxs-lookup"><span data-stu-id="fcc0c-332">Specifies whether data about the .NET Core tools usage is collected and sent to Microsoft.</span></span> <span data-ttu-id="fcc0c-333">设置为 `true` 以选择退出遥测功能（接受的值为 `true`、`1` 或 `yes`）。</span><span class="sxs-lookup"><span data-stu-id="fcc0c-333">Set to `true` to opt-out of the telemetry feature (values `true`, `1`, or `yes` accepted).</span></span> <span data-ttu-id="fcc0c-334">否则，设置为 `false` 以选择加入遥测功能（接受的值为 `false`、`0` 或 `no`）。</span><span class="sxs-lookup"><span data-stu-id="fcc0c-334">Otherwise, set to `false` to opt into the telemetry features (values `false`, `0`, or `no` accepted).</span></span> <span data-ttu-id="fcc0c-335">如果未设置，则默认为 `false` 且遥测功能为活动状态。</span><span class="sxs-lookup"><span data-stu-id="fcc0c-335">If not set, the default is `false` and the telemetry feature is active.</span></span>

`DOTNET_MULTILEVEL_LOOKUP`

<span data-ttu-id="fcc0c-336">指定是否从全局位置解析 .NET Core 运行时、共享框架或 SDK。</span><span class="sxs-lookup"><span data-stu-id="fcc0c-336">Specifies whether .NET Core runtime, shared framework, or SDK are resolved from the global location.</span></span> <span data-ttu-id="fcc0c-337">如果未设置，则默认为 `true`。</span><span class="sxs-lookup"><span data-stu-id="fcc0c-337">If not set, it defaults to `true`.</span></span> <span data-ttu-id="fcc0c-338">设置为 `false` 不从全局位置解析，并且具有独立的 .NET Core 安装（接受的值为 `0` 或 `false`）。</span><span class="sxs-lookup"><span data-stu-id="fcc0c-338">Set to `false` to not resolve from the global location and have isolated .NET Core installations (values `0` or `false` are accepted).</span></span> <span data-ttu-id="fcc0c-339">有关多级别查找的详细信息，请参阅 [Multi-level SharedFX Lookup](https://github.com/dotnet/core-setup/blob/master/Documentation/design-docs/multilevel-sharedfx-lookup.md)（多级别 SharedFX 查找）。</span><span class="sxs-lookup"><span data-stu-id="fcc0c-339">For more information about multi-level lookup, see [Multi-level SharedFX Lookup](https://github.com/dotnet/core-setup/blob/master/Documentation/design-docs/multilevel-sharedfx-lookup.md).</span></span>

`DOTNET_ROLL_FORWARD_ON_NO_CANDIDATE_FX`

<span data-ttu-id="fcc0c-340">如果设置为 `0`，则禁用次要版本前滚。</span><span class="sxs-lookup"><span data-stu-id="fcc0c-340">Disables minor version roll forward, if set to `0`.</span></span> <span data-ttu-id="fcc0c-341">有关详细信息，请参阅[前滚](../whats-new/dotnet-core-2-1.md#roll-forward)。</span><span class="sxs-lookup"><span data-stu-id="fcc0c-341">For more information, see [Roll forward](../whats-new/dotnet-core-2-1.md#roll-forward).</span></span>

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="fcc0c-342">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="fcc0c-342">.NET Core 2.0</span></span>](#tab/netcore20)

`DOTNET_PACKAGES`

<span data-ttu-id="fcc0c-343">主包缓存。</span><span class="sxs-lookup"><span data-stu-id="fcc0c-343">The primary package cache.</span></span> <span data-ttu-id="fcc0c-344">如果未设置，则默认为 Unix 上的 `$HOME/.nuget/packages` 或 Windows 上的 `%userprofile%\.nuget\packages`。</span><span class="sxs-lookup"><span data-stu-id="fcc0c-344">If not set, it defaults to `$HOME/.nuget/packages` on Unix or `%userprofile%\.nuget\packages` on Windows.</span></span>

`DOTNET_SERVICING`

<span data-ttu-id="fcc0c-345">指定加载运行时期间共享主机要使用的服务索引的位置。</span><span class="sxs-lookup"><span data-stu-id="fcc0c-345">Specifies the location of the servicing index to use by the shared host when loading the runtime.</span></span>

`DOTNET_CLI_TELEMETRY_OPTOUT`

<span data-ttu-id="fcc0c-346">指定是否收集并向 Microsoft 发送 .NET Core 工具使用情况的相关数据。</span><span class="sxs-lookup"><span data-stu-id="fcc0c-346">Specifies whether data about the .NET Core tools usage is collected and sent to Microsoft.</span></span> <span data-ttu-id="fcc0c-347">设置为 `true` 以选择退出遥测功能（接受的值为 `true`、`1` 或 `yes`）。</span><span class="sxs-lookup"><span data-stu-id="fcc0c-347">Set to `true` to opt-out of the telemetry feature (values `true`, `1`, or `yes` accepted).</span></span> <span data-ttu-id="fcc0c-348">否则，设置为 `false` 以选择加入遥测功能（接受的值为 `false`、`0` 或 `no`）。</span><span class="sxs-lookup"><span data-stu-id="fcc0c-348">Otherwise, set to `false` to opt into the telemetry features (values `false`, `0`, or `no` accepted).</span></span> <span data-ttu-id="fcc0c-349">如果未设置，则默认为 `false` 且遥测功能为活动状态。</span><span class="sxs-lookup"><span data-stu-id="fcc0c-349">If not set, the default is `false` and the telemetry feature is active.</span></span>

`DOTNET_MULTILEVEL_LOOKUP`

<span data-ttu-id="fcc0c-350">指定是否从全局位置解析 .NET Core 运行时、共享框架或 SDK。</span><span class="sxs-lookup"><span data-stu-id="fcc0c-350">Specifies whether .NET Core runtime, shared framework, or SDK are resolved from the global location.</span></span> <span data-ttu-id="fcc0c-351">如果未设置，则默认为 `true`。</span><span class="sxs-lookup"><span data-stu-id="fcc0c-351">If not set, it defaults to `true`.</span></span> <span data-ttu-id="fcc0c-352">设置为 `false` 不从全局位置解析，并且具有独立的 .NET Core 安装（接受的值为 `0` 或 `false`）。</span><span class="sxs-lookup"><span data-stu-id="fcc0c-352">Set to `false` to not resolve from the global location and have isolated .NET Core installations (values `0` or `false` are accepted).</span></span> <span data-ttu-id="fcc0c-353">有关多级别查找的详细信息，请参阅 [Multi-level SharedFX Lookup](https://github.com/dotnet/core-setup/blob/master/Documentation/design-docs/multilevel-sharedfx-lookup.md)（多级别 SharedFX 查找）。</span><span class="sxs-lookup"><span data-stu-id="fcc0c-353">For more information about multi-level lookup, see [Multi-level SharedFX Lookup](https://github.com/dotnet/core-setup/blob/master/Documentation/design-docs/multilevel-sharedfx-lookup.md).</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="fcc0c-354">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="fcc0c-354">.NET Core 1.x</span></span>](#tab/netcore1x)

`DOTNET_PACKAGES`

<span data-ttu-id="fcc0c-355">主包缓存。</span><span class="sxs-lookup"><span data-stu-id="fcc0c-355">The primary package cache.</span></span> <span data-ttu-id="fcc0c-356">如果未设置，则默认为 Unix 上的 `$HOME/.nuget/packages` 或 Windows 上的 `%userprofile%\.nuget\packages`。</span><span class="sxs-lookup"><span data-stu-id="fcc0c-356">If not set, it defaults to `$HOME/.nuget/packages` on Unix or `%userprofile%\.nuget\packages` on Windows.</span></span>

`DOTNET_SERVICING`

<span data-ttu-id="fcc0c-357">指定加载运行时期间共享主机要使用的服务索引的位置。</span><span class="sxs-lookup"><span data-stu-id="fcc0c-357">Specifies the location of the servicing index to use by the shared host when loading the runtime.</span></span>

`DOTNET_CLI_TELEMETRY_OPTOUT`

<span data-ttu-id="fcc0c-358">指定是否收集并向 Microsoft 发送 .NET Core 工具使用情况的相关数据。</span><span class="sxs-lookup"><span data-stu-id="fcc0c-358">Specifies whether data about the .NET Core tools usage is collected and sent to Microsoft.</span></span> <span data-ttu-id="fcc0c-359">设置为 `true` 以选择退出遥测功能（接受的值为 `true`、`1` 或 `yes`）。</span><span class="sxs-lookup"><span data-stu-id="fcc0c-359">Set to `true` to opt-out of the telemetry feature (values `true`, `1`, or `yes` accepted).</span></span> <span data-ttu-id="fcc0c-360">否则，设置为 `false` 以选择加入遥测功能（接受的值为 `false`、`0` 或 `no`）。</span><span class="sxs-lookup"><span data-stu-id="fcc0c-360">Otherwise, set to `false` to opt into the telemetry features (values `false`, `0`, or `no` accepted).</span></span> <span data-ttu-id="fcc0c-361">如果未设置，则默认为 `false` 且遥测功能为活动状态。</span><span class="sxs-lookup"><span data-stu-id="fcc0c-361">If not set, the default is `false` and the telemetry feature is active.</span></span>

---

## <a name="see-also"></a><span data-ttu-id="fcc0c-362">请参阅</span><span class="sxs-lookup"><span data-stu-id="fcc0c-362">See also</span></span>

- [<span data-ttu-id="fcc0c-363">运行时配置文件</span><span class="sxs-lookup"><span data-stu-id="fcc0c-363">Runtime Configuration Files</span></span>](https://github.com/dotnet/cli/blob/master/Documentation/specs/runtime-configuration-file.md)
