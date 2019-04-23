---
title: dotnet 命令
description: 了解 dotnet 命令（.NET Core CLI 工具的通用驱动程序）及其用法。
ms.date: 06/04/2018
ms.openlocfilehash: 5278adf44d12e428cdeacf1d475377ce9155c314
ms.sourcegitcommit: 438919211260bb415fc8f96ca3eabc33cf2d681d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2019
ms.locfileid: "59613000"
---
# <a name="dotnet-command"></a><span data-ttu-id="2fc81-103">dotnet 命令</span><span class="sxs-lookup"><span data-stu-id="2fc81-103">dotnet command</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="2fc81-104">name</span><span class="sxs-lookup"><span data-stu-id="2fc81-104">Name</span></span>

<span data-ttu-id="2fc81-105">`dotnet` - 一款管理 .NET 源代码和二进制文件的工具。</span><span class="sxs-lookup"><span data-stu-id="2fc81-105">`dotnet` - A tool for managing .NET source code and binaries.</span></span>

## <a name="synopsis"></a><span data-ttu-id="2fc81-106">摘要</span><span class="sxs-lookup"><span data-stu-id="2fc81-106">Synopsis</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="2fc81-107">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="2fc81-107">.NET Core 2.1</span></span>](#tab/netcore21)

```
dotnet [command] [arguments] [--additional-deps] [--additionalprobingpath] [-d|--diagnostics] [--fx-version]
    [-h|--help] [--info] [--list-runtimes] [--list-sdks] [--roll-forward-on-no-candidate-fx] [-v|--verbosity] [--version]
```

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="2fc81-108">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="2fc81-108">.NET Core 2.0</span></span>](#tab/netcore20)

```
dotnet [command] [arguments] [--additional-deps] [--additionalprobingpath] [-d|--diagnostics]
    [--fx-version] [-h|--help] [--info] [--roll-forward-on-no-candidate-fx] [-v|--verbosity] [--version]
```

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="2fc81-109">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="2fc81-109">.NET Core 1.x</span></span>](#tab/netcore1x)

```
dotnet [command] [arguments] [--additionalprobingpath] [-d|--diagnostics] [--fx-version]
    [-h|--help] [--info] [-v|--verbosity] [--version]
```

---

## <a name="description"></a><span data-ttu-id="2fc81-110">说明</span><span class="sxs-lookup"><span data-stu-id="2fc81-110">Description</span></span>

<span data-ttu-id="2fc81-111">`dotnet` 是一款管理 .NET 源代码和二进制文件的工具。</span><span class="sxs-lookup"><span data-stu-id="2fc81-111">`dotnet` is a tool for managing .NET source code and binaries.</span></span> <span data-ttu-id="2fc81-112">它公开执行特定任务的命令，例如 [`dotnet build`](dotnet-build.md) 和 [`dotnet run`](dotnet-run.md)。</span><span class="sxs-lookup"><span data-stu-id="2fc81-112">It exposes commands that perform specific tasks, such as [`dotnet build`](dotnet-build.md) and [`dotnet run`](dotnet-run.md).</span></span> <span data-ttu-id="2fc81-113">每个命令都定义自己的参数。</span><span class="sxs-lookup"><span data-stu-id="2fc81-113">Each command defines its own arguments.</span></span> <span data-ttu-id="2fc81-114">在每个命令后键入 `--help` 以访问简要帮助文档。</span><span class="sxs-lookup"><span data-stu-id="2fc81-114">Type `--help` after each command to access brief help documentation.</span></span>

<span data-ttu-id="2fc81-115">可以使用 `dotnet` 来运行应用程序，方法是指定应用程序 DLL，如 `dotnet myapp.dll`.</span><span class="sxs-lookup"><span data-stu-id="2fc81-115">`dotnet` can be used to run applications, by specifying an application DLL, such as `dotnet myapp.dll`.</span></span> <span data-ttu-id="2fc81-116">要了解部署选项，请参阅 [.NET Core 应用程序部署](../deploying/index.md)。</span><span class="sxs-lookup"><span data-stu-id="2fc81-116">See [.NET Core application deployment](../deploying/index.md) for to learn about deployment options.</span></span>

## <a name="options"></a><span data-ttu-id="2fc81-117">选项</span><span class="sxs-lookup"><span data-stu-id="2fc81-117">Options</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="2fc81-118">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="2fc81-118">.NET Core 2.1</span></span>](#tab/netcore21)

`--additional-deps <PATH>`

<span data-ttu-id="2fc81-119">其他 deps.json 文件的路径。</span><span class="sxs-lookup"><span data-stu-id="2fc81-119">Path to additional *deps.json* file.</span></span>

`--additionalprobingpath <PATH>`

<span data-ttu-id="2fc81-120">包含要进行探测的探测策略和程序集的路径。</span><span class="sxs-lookup"><span data-stu-id="2fc81-120">Path containing probing policy and assemblies to probe.</span></span>

`-d|--diagnostics`

<span data-ttu-id="2fc81-121">启用诊断输出。</span><span class="sxs-lookup"><span data-stu-id="2fc81-121">Enables diagnostic output.</span></span>

`--fx-version <VERSION>`

<span data-ttu-id="2fc81-122">用于运行应用程序的 .NET Core 运行时版本。</span><span class="sxs-lookup"><span data-stu-id="2fc81-122">Version of the .NET Core runtime to use to run the application.</span></span>

`-h|--help`

<span data-ttu-id="2fc81-123">打印出给定命令的文档，如 `dotnet build --help`。</span><span class="sxs-lookup"><span data-stu-id="2fc81-123">Prints out documentation for a given command, such as `dotnet build --help`.</span></span> <span data-ttu-id="2fc81-124">`dotnet --help` 打印可用命令列表。</span><span class="sxs-lookup"><span data-stu-id="2fc81-124">`dotnet --help` prints a list of available commands.</span></span>

`--info`

<span data-ttu-id="2fc81-125">打印出有关 .NET Core 安装和计算机环境（如当前操作系统）的详细信息，并提交 .NET Core 版本的 SHA。</span><span class="sxs-lookup"><span data-stu-id="2fc81-125">Prints out detailed information about a .NET Core installation and the machine environment, such as the current operating system, and commit SHA of the .NET Core version.</span></span>

`--list-runtimes`

<span data-ttu-id="2fc81-126">显示已安装的 .NET Core 运行时。</span><span class="sxs-lookup"><span data-stu-id="2fc81-126">Displays the installed .NET Core runtimes.</span></span>

`--list-sdks`

<span data-ttu-id="2fc81-127">显示已安装的 .NET Core SDK。</span><span class="sxs-lookup"><span data-stu-id="2fc81-127">Displays the installed .NET Core SDKs.</span></span>

`--roll-forward-on-no-candidate-fx <N>`

<span data-ttu-id="2fc81-128">所需的共享框架不可用时，请定义行为。</span><span class="sxs-lookup"><span data-stu-id="2fc81-128">Defines behavior when the required shared framework is not available.</span></span> <span data-ttu-id="2fc81-129">`N` 可以是：</span><span class="sxs-lookup"><span data-stu-id="2fc81-129">`N` can be:</span></span>
* <span data-ttu-id="2fc81-130">`0` - 禁用次要版本前滚。</span><span class="sxs-lookup"><span data-stu-id="2fc81-130">`0` - Disable even minor version roll forward.</span></span>
* <span data-ttu-id="2fc81-131">`1` - 前滚次要版本，但不前滚主版本。</span><span class="sxs-lookup"><span data-stu-id="2fc81-131">`1` - Roll forward on minor version, but not on major version.</span></span> <span data-ttu-id="2fc81-132">这是默认行为。</span><span class="sxs-lookup"><span data-stu-id="2fc81-132">This is the default behavior.</span></span>
* <span data-ttu-id="2fc81-133">`2` - 前滚次要和主版本。</span><span class="sxs-lookup"><span data-stu-id="2fc81-133">`2` - Roll forward on minor and major versions.</span></span>

 <span data-ttu-id="2fc81-134">有关详细信息，请参阅[前滚](../whats-new/dotnet-core-2-1.md#roll-forward)。</span><span class="sxs-lookup"><span data-stu-id="2fc81-134">For more information, see [Roll forward](../whats-new/dotnet-core-2-1.md#roll-forward).</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="2fc81-135">设置命令的详细级别。</span><span class="sxs-lookup"><span data-stu-id="2fc81-135">Sets the verbosity level of the command.</span></span> <span data-ttu-id="2fc81-136">允许使用的值为 `q[uiet]`、`m[inimal]`、`n[ormal]`、`d[etailed]` 和 `diag[nostic]`。</span><span class="sxs-lookup"><span data-stu-id="2fc81-136">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="2fc81-137">并非在每个命令中均受支持；请参阅特定的命令页，确定此选项是否可用。</span><span class="sxs-lookup"><span data-stu-id="2fc81-137">Not supported in every command; see specific command page to determine if this option is available.</span></span>

`--version`

<span data-ttu-id="2fc81-138">打印使用中的 .NET Core SDK 版本。</span><span class="sxs-lookup"><span data-stu-id="2fc81-138">Prints out the version of the .NET Core SDK in use.</span></span>

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="2fc81-139">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="2fc81-139">.NET Core 2.0</span></span>](#tab/netcore20)

`--additional-deps <PATH>`

<span data-ttu-id="2fc81-140">其他 deps.json 文件的路径。</span><span class="sxs-lookup"><span data-stu-id="2fc81-140">Path to additional *deps.json* file.</span></span>

`--additionalprobingpath <PATH>`

<span data-ttu-id="2fc81-141">包含要进行探测的探测策略和程序集的路径。</span><span class="sxs-lookup"><span data-stu-id="2fc81-141">Path containing probing policy and assemblies to probe.</span></span>

`-d|--diagnostics`

<span data-ttu-id="2fc81-142">启用诊断输出。</span><span class="sxs-lookup"><span data-stu-id="2fc81-142">Enables diagnostic output.</span></span>

`--fx-version <VERSION>`

<span data-ttu-id="2fc81-143">用于运行应用程序的 .NET Core 运行时版本。</span><span class="sxs-lookup"><span data-stu-id="2fc81-143">Version of the .NET Core runtime to use to run the application.</span></span>

`-h|--help`

<span data-ttu-id="2fc81-144">打印出给定命令的文档，如 `dotnet build --help`。</span><span class="sxs-lookup"><span data-stu-id="2fc81-144">Prints out documentation for a given command, such as `dotnet build --help`.</span></span> <span data-ttu-id="2fc81-145">`dotnet --help` 打印可用命令列表。</span><span class="sxs-lookup"><span data-stu-id="2fc81-145">`dotnet --help` prints a list of available commands.</span></span>

`--info`

<span data-ttu-id="2fc81-146">打印出有关 .NET Core 安装和计算机环境（如当前操作系统）的详细信息，并提交 .NET Core 版本的 SHA。</span><span class="sxs-lookup"><span data-stu-id="2fc81-146">Prints out detailed information about a .NET Core installation and the machine environment, such as the current operating system, and commit SHA of the .NET Core version.</span></span>

`--roll-forward-on-no-candidate-fx`

 <span data-ttu-id="2fc81-147">如果设置为 `0`，则禁用次要版本前滚。</span><span class="sxs-lookup"><span data-stu-id="2fc81-147">Disables minor version roll forward, if set to `0`.</span></span> <span data-ttu-id="2fc81-148">有关详细信息，请参阅[前滚](../whats-new/dotnet-core-2-1.md#roll-forward)。</span><span class="sxs-lookup"><span data-stu-id="2fc81-148">For more information, see [Roll forward](../whats-new/dotnet-core-2-1.md#roll-forward).</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="2fc81-149">设置命令的详细级别。</span><span class="sxs-lookup"><span data-stu-id="2fc81-149">Sets the verbosity level of the command.</span></span> <span data-ttu-id="2fc81-150">允许使用的值为 `q[uiet]`、`m[inimal]`、`n[ormal]`、`d[etailed]` 和 `diag[nostic]`。</span><span class="sxs-lookup"><span data-stu-id="2fc81-150">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="2fc81-151">并非在每个命令中均受支持；请参阅特定的命令页，确定此选项是否可用。</span><span class="sxs-lookup"><span data-stu-id="2fc81-151">Not supported in every command; see specific command page to determine if this option is available.</span></span>

`--version`

<span data-ttu-id="2fc81-152">打印使用中的 .NET Core SDK 版本。</span><span class="sxs-lookup"><span data-stu-id="2fc81-152">Prints out the version of the .NET Core SDK in use.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="2fc81-153">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="2fc81-153">.NET Core 1.x</span></span>](#tab/netcore1x)

`--additionalprobingpath <PATH>`

<span data-ttu-id="2fc81-154">包含要进行探测的探测策略和程序集的路径。</span><span class="sxs-lookup"><span data-stu-id="2fc81-154">Path containing probing policy and assemblies to probe.</span></span>

`-d|--diagnostics`

<span data-ttu-id="2fc81-155">启用诊断输出。</span><span class="sxs-lookup"><span data-stu-id="2fc81-155">Enables diagnostic output.</span></span>

`--fx-version <VERSION>`

<span data-ttu-id="2fc81-156">用于运行应用程序的 .NET Core 运行时版本。</span><span class="sxs-lookup"><span data-stu-id="2fc81-156">Version of the .NET Core runtime to use to run the application.</span></span>

`-h|--help`

<span data-ttu-id="2fc81-157">打印出给定命令的文档，如 `dotnet build --help`。</span><span class="sxs-lookup"><span data-stu-id="2fc81-157">Prints out documentation for a given command, such as `dotnet build --help`.</span></span> <span data-ttu-id="2fc81-158">`dotnet --help` 打印可用命令列表。</span><span class="sxs-lookup"><span data-stu-id="2fc81-158">`dotnet --help` prints a list of available commands.</span></span>

`--info`

<span data-ttu-id="2fc81-159">打印出有关 .NET Core 安装和计算机环境（如当前操作系统）的详细信息，并提交 .NET Core 版本的 SHA。</span><span class="sxs-lookup"><span data-stu-id="2fc81-159">Prints out detailed information about a .NET Core installation and the machine environment, such as the current operating system, and commit SHA of the .NET Core version.</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="2fc81-160">设置命令的详细级别。</span><span class="sxs-lookup"><span data-stu-id="2fc81-160">Sets the verbosity level of the command.</span></span> <span data-ttu-id="2fc81-161">允许使用的值为 `q[uiet]`、`m[inimal]`、`n[ormal]`、`d[etailed]` 和 `diag[nostic]`。</span><span class="sxs-lookup"><span data-stu-id="2fc81-161">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="2fc81-162">并非在每个命令中均受支持；请参阅特定的命令页，确定此选项是否可用。</span><span class="sxs-lookup"><span data-stu-id="2fc81-162">Not supported in every command; see specific command page to determine if this option is available.</span></span>

`--version`

<span data-ttu-id="2fc81-163">打印使用中的 .NET Core SDK 版本。</span><span class="sxs-lookup"><span data-stu-id="2fc81-163">Prints out the version of the .NET Core SDK in use.</span></span>

---

## <a name="dotnet-commands"></a><span data-ttu-id="2fc81-164">dotnet 命令</span><span class="sxs-lookup"><span data-stu-id="2fc81-164">dotnet commands</span></span>

### <a name="general"></a><span data-ttu-id="2fc81-165">常规</span><span class="sxs-lookup"><span data-stu-id="2fc81-165">General</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="2fc81-166">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="2fc81-166">.NET Core 2.1</span></span>](#tab/netcore21)

| <span data-ttu-id="2fc81-167">命令</span><span class="sxs-lookup"><span data-stu-id="2fc81-167">Command</span></span>                                       | <span data-ttu-id="2fc81-168">函数</span><span class="sxs-lookup"><span data-stu-id="2fc81-168">Function</span></span>                                                            |
| --------------------------------------------- | ------------------------------------------------------------------- |
| [<span data-ttu-id="2fc81-169">dotnet build</span><span class="sxs-lookup"><span data-stu-id="2fc81-169">dotnet build</span></span>](dotnet-build.md)               | <span data-ttu-id="2fc81-170">生成 .NET Core 应用程序。</span><span class="sxs-lookup"><span data-stu-id="2fc81-170">Builds a .NET Core application.</span></span>                                     |
| [<span data-ttu-id="2fc81-171">dotnet build-server</span><span class="sxs-lookup"><span data-stu-id="2fc81-171">dotnet build-server</span></span>](dotnet-build-server.md) | <span data-ttu-id="2fc81-172">与通过生成启动的服务器进行交互。</span><span class="sxs-lookup"><span data-stu-id="2fc81-172">Interacts with servers started by a build.</span></span>                          |
| [<span data-ttu-id="2fc81-173">dotnet clean</span><span class="sxs-lookup"><span data-stu-id="2fc81-173">dotnet clean</span></span>](dotnet-clean.md)               | <span data-ttu-id="2fc81-174">清除生成输出。</span><span class="sxs-lookup"><span data-stu-id="2fc81-174">Clean build outputs.</span></span>                                                |
| [<span data-ttu-id="2fc81-175">dotnet help</span><span class="sxs-lookup"><span data-stu-id="2fc81-175">dotnet help</span></span>](dotnet-help.md)                 | <span data-ttu-id="2fc81-176">显示命令更详细的在线文档。</span><span class="sxs-lookup"><span data-stu-id="2fc81-176">Shows more detailed documentation online for the command.</span></span>           |
| [<span data-ttu-id="2fc81-177">dotnet migrate</span><span class="sxs-lookup"><span data-stu-id="2fc81-177">dotnet migrate</span></span>](dotnet-migrate.md)           | <span data-ttu-id="2fc81-178">将有效的预览版 2 项目迁移到 .NET Core SDK 1.0 项目。</span><span class="sxs-lookup"><span data-stu-id="2fc81-178">Migrates a valid Preview 2 project to a .NET Core SDK 1.0 project.</span></span>  |
| [<span data-ttu-id="2fc81-179">dotnet msbuild</span><span class="sxs-lookup"><span data-stu-id="2fc81-179">dotnet msbuild</span></span>](dotnet-msbuild.md)           | <span data-ttu-id="2fc81-180">提供对 MSBuild 命令行的访问权限。</span><span class="sxs-lookup"><span data-stu-id="2fc81-180">Provides access to the MSBuild command line.</span></span>                        |
| [<span data-ttu-id="2fc81-181">dotnet new</span><span class="sxs-lookup"><span data-stu-id="2fc81-181">dotnet new</span></span>](dotnet-new.md)                   | <span data-ttu-id="2fc81-182">为给定的模板初始化 C# 或 F# 项目。</span><span class="sxs-lookup"><span data-stu-id="2fc81-182">Initializes a C# or F# project for a given template.</span></span>                |
| [<span data-ttu-id="2fc81-183">dotnet pack</span><span class="sxs-lookup"><span data-stu-id="2fc81-183">dotnet pack</span></span>](dotnet-pack.md)                 | <span data-ttu-id="2fc81-184">创建代码的 NuGet 包。</span><span class="sxs-lookup"><span data-stu-id="2fc81-184">Creates a NuGet package of your code.</span></span>                               |
| [<span data-ttu-id="2fc81-185">dotnet publish</span><span class="sxs-lookup"><span data-stu-id="2fc81-185">dotnet publish</span></span>](dotnet-publish.md)           | <span data-ttu-id="2fc81-186">发布 .NET 依赖于框架或独立应用程序。</span><span class="sxs-lookup"><span data-stu-id="2fc81-186">Publishes a .NET framework-dependent or self-contained application.</span></span> |
| [<span data-ttu-id="2fc81-187">dotnet restore</span><span class="sxs-lookup"><span data-stu-id="2fc81-187">dotnet restore</span></span>](dotnet-restore.md)           | <span data-ttu-id="2fc81-188">还原给定应用程序的依赖项。</span><span class="sxs-lookup"><span data-stu-id="2fc81-188">Restores the dependencies for a given application.</span></span>                  |
| [<span data-ttu-id="2fc81-189">dotnet run</span><span class="sxs-lookup"><span data-stu-id="2fc81-189">dotnet run</span></span>](dotnet-run.md)                   | <span data-ttu-id="2fc81-190">从源运行应用程序。</span><span class="sxs-lookup"><span data-stu-id="2fc81-190">Runs the application from source.</span></span>                                   |
| [<span data-ttu-id="2fc81-191">dotnet sln</span><span class="sxs-lookup"><span data-stu-id="2fc81-191">dotnet sln</span></span>](dotnet-sln.md)                   | <span data-ttu-id="2fc81-192">用于添加、删除和列出解决方案文件中项目的选项。</span><span class="sxs-lookup"><span data-stu-id="2fc81-192">Options to add, remove, and list projects in a solution file.</span></span>       |
| [<span data-ttu-id="2fc81-193">dotnet store</span><span class="sxs-lookup"><span data-stu-id="2fc81-193">dotnet store</span></span>](dotnet-store.md)               | <span data-ttu-id="2fc81-194">将程序集存储到运行时包存储区。</span><span class="sxs-lookup"><span data-stu-id="2fc81-194">Stores assemblies in the runtime package store.</span></span>                     |
| [<span data-ttu-id="2fc81-195">dotnet test</span><span class="sxs-lookup"><span data-stu-id="2fc81-195">dotnet test</span></span>](dotnet-test.md)                 | <span data-ttu-id="2fc81-196">使用测试运行程序运行测试。</span><span class="sxs-lookup"><span data-stu-id="2fc81-196">Runs tests using a test runner.</span></span>                                     |

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="2fc81-197">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="2fc81-197">.NET Core 2.0</span></span>](#tab/netcore20)

| <span data-ttu-id="2fc81-198">命令</span><span class="sxs-lookup"><span data-stu-id="2fc81-198">Command</span></span>                             | <span data-ttu-id="2fc81-199">函数</span><span class="sxs-lookup"><span data-stu-id="2fc81-199">Function</span></span>                                                            |
| ----------------------------------- | ------------------------------------------------------------------- |
| [<span data-ttu-id="2fc81-200">dotnet build</span><span class="sxs-lookup"><span data-stu-id="2fc81-200">dotnet build</span></span>](dotnet-build.md)     | <span data-ttu-id="2fc81-201">生成 .NET Core 应用程序。</span><span class="sxs-lookup"><span data-stu-id="2fc81-201">Builds a .NET Core application.</span></span>                                     |
| [<span data-ttu-id="2fc81-202">dotnet clean</span><span class="sxs-lookup"><span data-stu-id="2fc81-202">dotnet clean</span></span>](dotnet-clean.md)     | <span data-ttu-id="2fc81-203">清除生成输出。</span><span class="sxs-lookup"><span data-stu-id="2fc81-203">Clean build outputs.</span></span>                                              |
| [<span data-ttu-id="2fc81-204">dotnet help</span><span class="sxs-lookup"><span data-stu-id="2fc81-204">dotnet help</span></span>](dotnet-help.md)       | <span data-ttu-id="2fc81-205">显示命令更详细的在线文档。</span><span class="sxs-lookup"><span data-stu-id="2fc81-205">Shows more detailed documentation online for the command.</span></span>           |
| [<span data-ttu-id="2fc81-206">dotnet migrate</span><span class="sxs-lookup"><span data-stu-id="2fc81-206">dotnet migrate</span></span>](dotnet-migrate.md) | <span data-ttu-id="2fc81-207">将有效的预览版 2 项目迁移到 .NET Core SDK 1.0 项目。</span><span class="sxs-lookup"><span data-stu-id="2fc81-207">Migrates a valid Preview 2 project to a .NET Core SDK 1.0 project.</span></span>  |
| [<span data-ttu-id="2fc81-208">dotnet msbuild</span><span class="sxs-lookup"><span data-stu-id="2fc81-208">dotnet msbuild</span></span>](dotnet-msbuild.md) | <span data-ttu-id="2fc81-209">提供对 MSBuild 命令行的访问权限。</span><span class="sxs-lookup"><span data-stu-id="2fc81-209">Provides access to the MSBuild command line.</span></span>                        |
| [<span data-ttu-id="2fc81-210">dotnet new</span><span class="sxs-lookup"><span data-stu-id="2fc81-210">dotnet new</span></span>](dotnet-new.md)         | <span data-ttu-id="2fc81-211">为给定的模板初始化 C# 或 F# 项目。</span><span class="sxs-lookup"><span data-stu-id="2fc81-211">Initializes a C# or F# project for a given template.</span></span>                |
| [<span data-ttu-id="2fc81-212">dotnet pack</span><span class="sxs-lookup"><span data-stu-id="2fc81-212">dotnet pack</span></span>](dotnet-pack.md)       | <span data-ttu-id="2fc81-213">创建代码的 NuGet 包。</span><span class="sxs-lookup"><span data-stu-id="2fc81-213">Creates a NuGet package of your code.</span></span>                               |
| [<span data-ttu-id="2fc81-214">dotnet publish</span><span class="sxs-lookup"><span data-stu-id="2fc81-214">dotnet publish</span></span>](dotnet-publish.md) | <span data-ttu-id="2fc81-215">发布 .NET 依赖于框架或独立应用程序。</span><span class="sxs-lookup"><span data-stu-id="2fc81-215">Publishes a .NET framework-dependent or self-contained application.</span></span> |
| [<span data-ttu-id="2fc81-216">dotnet restore</span><span class="sxs-lookup"><span data-stu-id="2fc81-216">dotnet restore</span></span>](dotnet-restore.md) | <span data-ttu-id="2fc81-217">还原给定应用程序的依赖项。</span><span class="sxs-lookup"><span data-stu-id="2fc81-217">Restores the dependencies for a given application.</span></span>                  |
| [<span data-ttu-id="2fc81-218">dotnet run</span><span class="sxs-lookup"><span data-stu-id="2fc81-218">dotnet run</span></span>](dotnet-run.md)         | <span data-ttu-id="2fc81-219">从源运行应用程序。</span><span class="sxs-lookup"><span data-stu-id="2fc81-219">Runs the application from source.</span></span>                                   |
| [<span data-ttu-id="2fc81-220">dotnet sln</span><span class="sxs-lookup"><span data-stu-id="2fc81-220">dotnet sln</span></span>](dotnet-sln.md)         | <span data-ttu-id="2fc81-221">用于添加、删除和列出解决方案文件中项目的选项。</span><span class="sxs-lookup"><span data-stu-id="2fc81-221">Options to add, remove, and list projects in a solution file.</span></span>       |
| [<span data-ttu-id="2fc81-222">dotnet store</span><span class="sxs-lookup"><span data-stu-id="2fc81-222">dotnet store</span></span>](dotnet-store.md)     | <span data-ttu-id="2fc81-223">将程序集存储到运行时包存储区。</span><span class="sxs-lookup"><span data-stu-id="2fc81-223">Stores assemblies in the runtime package store.</span></span>                     |
| [<span data-ttu-id="2fc81-224">dotnet test</span><span class="sxs-lookup"><span data-stu-id="2fc81-224">dotnet test</span></span>](dotnet-test.md)       | <span data-ttu-id="2fc81-225">使用测试运行程序运行测试。</span><span class="sxs-lookup"><span data-stu-id="2fc81-225">Runs tests using a test runner.</span></span>                                     |

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="2fc81-226">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="2fc81-226">.NET Core 1.x</span></span>](#tab/netcore1x)

| <span data-ttu-id="2fc81-227">命令</span><span class="sxs-lookup"><span data-stu-id="2fc81-227">Command</span></span>                             | <span data-ttu-id="2fc81-228">函数</span><span class="sxs-lookup"><span data-stu-id="2fc81-228">Function</span></span>                                                            |
| ----------------------------------- | ------------------------------------------------------------------- |
| [<span data-ttu-id="2fc81-229">dotnet build</span><span class="sxs-lookup"><span data-stu-id="2fc81-229">dotnet build</span></span>](dotnet-build.md)     | <span data-ttu-id="2fc81-230">生成 .NET Core 应用程序。</span><span class="sxs-lookup"><span data-stu-id="2fc81-230">Builds a .NET Core application.</span></span>                                     |
| [<span data-ttu-id="2fc81-231">dotnet clean</span><span class="sxs-lookup"><span data-stu-id="2fc81-231">dotnet clean</span></span>](dotnet-clean.md)     | <span data-ttu-id="2fc81-232">清除生成输出。</span><span class="sxs-lookup"><span data-stu-id="2fc81-232">Clean build outputs.</span></span>                                              |
| [<span data-ttu-id="2fc81-233">dotnet migrate</span><span class="sxs-lookup"><span data-stu-id="2fc81-233">dotnet migrate</span></span>](dotnet-migrate.md) | <span data-ttu-id="2fc81-234">将有效的预览版 2 项目迁移到 .NET Core SDK 1.0 项目。</span><span class="sxs-lookup"><span data-stu-id="2fc81-234">Migrates a valid Preview 2 project to a .NET Core SDK 1.0 project.</span></span>  |
| [<span data-ttu-id="2fc81-235">dotnet msbuild</span><span class="sxs-lookup"><span data-stu-id="2fc81-235">dotnet msbuild</span></span>](dotnet-msbuild.md) | <span data-ttu-id="2fc81-236">提供对 MSBuild 命令行的访问权限。</span><span class="sxs-lookup"><span data-stu-id="2fc81-236">Provides access to the MSBuild command line.</span></span>                        |
| [<span data-ttu-id="2fc81-237">dotnet new</span><span class="sxs-lookup"><span data-stu-id="2fc81-237">dotnet new</span></span>](dotnet-new.md)         | <span data-ttu-id="2fc81-238">为给定的模板初始化 C# 或 F# 项目。</span><span class="sxs-lookup"><span data-stu-id="2fc81-238">Initializes a C# or F# project for a given template.</span></span>                |
| [<span data-ttu-id="2fc81-239">dotnet pack</span><span class="sxs-lookup"><span data-stu-id="2fc81-239">dotnet pack</span></span>](dotnet-pack.md)       | <span data-ttu-id="2fc81-240">创建代码的 NuGet 包。</span><span class="sxs-lookup"><span data-stu-id="2fc81-240">Creates a NuGet package of your code.</span></span>                               |
| [<span data-ttu-id="2fc81-241">dotnet publish</span><span class="sxs-lookup"><span data-stu-id="2fc81-241">dotnet publish</span></span>](dotnet-publish.md) | <span data-ttu-id="2fc81-242">发布 .NET 依赖于框架或独立应用程序。</span><span class="sxs-lookup"><span data-stu-id="2fc81-242">Publishes a .NET framework-dependent or self-contained application.</span></span> |
| [<span data-ttu-id="2fc81-243">dotnet restore</span><span class="sxs-lookup"><span data-stu-id="2fc81-243">dotnet restore</span></span>](dotnet-restore.md) | <span data-ttu-id="2fc81-244">还原给定应用程序的依赖项。</span><span class="sxs-lookup"><span data-stu-id="2fc81-244">Restores the dependencies for a given application.</span></span>                  |
| [<span data-ttu-id="2fc81-245">dotnet run</span><span class="sxs-lookup"><span data-stu-id="2fc81-245">dotnet run</span></span>](dotnet-run.md)         | <span data-ttu-id="2fc81-246">从源运行应用程序。</span><span class="sxs-lookup"><span data-stu-id="2fc81-246">Runs the application from source.</span></span>                                   |
| [<span data-ttu-id="2fc81-247">dotnet sln</span><span class="sxs-lookup"><span data-stu-id="2fc81-247">dotnet sln</span></span>](dotnet-sln.md)         | <span data-ttu-id="2fc81-248">用于添加、删除和列出解决方案文件中项目的选项。</span><span class="sxs-lookup"><span data-stu-id="2fc81-248">Options to add, remove, and list projects in a solution file.</span></span>       |
| [<span data-ttu-id="2fc81-249">dotnet test</span><span class="sxs-lookup"><span data-stu-id="2fc81-249">dotnet test</span></span>](dotnet-test.md)       | <span data-ttu-id="2fc81-250">使用测试运行程序运行测试。</span><span class="sxs-lookup"><span data-stu-id="2fc81-250">Runs tests using a test runner.</span></span>                                     |

---

### <a name="project-references"></a><span data-ttu-id="2fc81-251">项目引用</span><span class="sxs-lookup"><span data-stu-id="2fc81-251">Project references</span></span>

<span data-ttu-id="2fc81-252">命令</span><span class="sxs-lookup"><span data-stu-id="2fc81-252">Command</span></span> | <span data-ttu-id="2fc81-253">函数</span><span class="sxs-lookup"><span data-stu-id="2fc81-253">Function</span></span>
--- | ---
[<span data-ttu-id="2fc81-254">dotnet add reference</span><span class="sxs-lookup"><span data-stu-id="2fc81-254">dotnet add reference</span></span>](dotnet-add-reference.md) | <span data-ttu-id="2fc81-255">添加项目引用。</span><span class="sxs-lookup"><span data-stu-id="2fc81-255">Adds a project reference.</span></span>
[<span data-ttu-id="2fc81-256">dotnet list reference</span><span class="sxs-lookup"><span data-stu-id="2fc81-256">dotnet list reference</span></span>](dotnet-list-reference.md) | <span data-ttu-id="2fc81-257">列出项目引用。</span><span class="sxs-lookup"><span data-stu-id="2fc81-257">Lists project references.</span></span>
[<span data-ttu-id="2fc81-258">dotnet remove reference</span><span class="sxs-lookup"><span data-stu-id="2fc81-258">dotnet remove reference</span></span>](dotnet-remove-reference.md) | <span data-ttu-id="2fc81-259">删除项目引用。</span><span class="sxs-lookup"><span data-stu-id="2fc81-259">Removes a project reference.</span></span>

### <a name="nuget-packages"></a><span data-ttu-id="2fc81-260">NuGet 包</span><span class="sxs-lookup"><span data-stu-id="2fc81-260">NuGet packages</span></span>

<span data-ttu-id="2fc81-261">命令</span><span class="sxs-lookup"><span data-stu-id="2fc81-261">Command</span></span> | <span data-ttu-id="2fc81-262">函数</span><span class="sxs-lookup"><span data-stu-id="2fc81-262">Function</span></span>
--- | ---
[<span data-ttu-id="2fc81-263">dotnet add package</span><span class="sxs-lookup"><span data-stu-id="2fc81-263">dotnet add package</span></span>](dotnet-add-package.md) | <span data-ttu-id="2fc81-264">添加 NuGet 包。</span><span class="sxs-lookup"><span data-stu-id="2fc81-264">Adds a NuGet package.</span></span>
[<span data-ttu-id="2fc81-265">dotnet remove package</span><span class="sxs-lookup"><span data-stu-id="2fc81-265">dotnet remove package</span></span>](dotnet-remove-package.md) | <span data-ttu-id="2fc81-266">删除 NuGet 包。</span><span class="sxs-lookup"><span data-stu-id="2fc81-266">Removes a NuGet package.</span></span>

### <a name="nuget-commands"></a><span data-ttu-id="2fc81-267">NuGet 命令</span><span class="sxs-lookup"><span data-stu-id="2fc81-267">NuGet commands</span></span>

<span data-ttu-id="2fc81-268">命令</span><span class="sxs-lookup"><span data-stu-id="2fc81-268">Command</span></span> | <span data-ttu-id="2fc81-269">函数</span><span class="sxs-lookup"><span data-stu-id="2fc81-269">Function</span></span>
--- | ---
[<span data-ttu-id="2fc81-270">dotnet nuget delete</span><span class="sxs-lookup"><span data-stu-id="2fc81-270">dotnet nuget delete</span></span>](dotnet-nuget-delete.md) | <span data-ttu-id="2fc81-271">从服务器删除或取消列出包。</span><span class="sxs-lookup"><span data-stu-id="2fc81-271">Deletes or unlists a package from the server.</span></span>
[<span data-ttu-id="2fc81-272">dotnet nuget locals</span><span class="sxs-lookup"><span data-stu-id="2fc81-272">dotnet nuget locals</span></span>](dotnet-nuget-locals.md) | <span data-ttu-id="2fc81-273">清除或列出本地 NuGet 资源，例如 http 请求缓存、临时缓存或计算机范围的全局包文件夹。</span><span class="sxs-lookup"><span data-stu-id="2fc81-273">Clears or lists local NuGet resources such as http-request cache, temporary cache, or machine-wide global packages folder.</span></span>
[<span data-ttu-id="2fc81-274">dotnet nuget push</span><span class="sxs-lookup"><span data-stu-id="2fc81-274">dotnet nuget push</span></span>](dotnet-nuget-push.md) | <span data-ttu-id="2fc81-275">将包推送到服务器，并将其发布。</span><span class="sxs-lookup"><span data-stu-id="2fc81-275">Pushes a package to the server and publishes it.</span></span>

### <a name="global-tools-commands"></a><span data-ttu-id="2fc81-276">全局工具命令</span><span class="sxs-lookup"><span data-stu-id="2fc81-276">Global Tools commands</span></span>

<span data-ttu-id="2fc81-277">[.NET Core 全局工具](global-tools.md)可与 .NET Core SDK 2.1.300 一起开始使用：</span><span class="sxs-lookup"><span data-stu-id="2fc81-277">[.NET Core Global Tools](global-tools.md) are available starting with .NET Core SDK 2.1.300:</span></span>

<span data-ttu-id="2fc81-278">命令</span><span class="sxs-lookup"><span data-stu-id="2fc81-278">Command</span></span> | <span data-ttu-id="2fc81-279">函数</span><span class="sxs-lookup"><span data-stu-id="2fc81-279">Function</span></span>
--- | ---
[<span data-ttu-id="2fc81-280">dotnet tool install</span><span class="sxs-lookup"><span data-stu-id="2fc81-280">dotnet tool install</span></span>](dotnet-tool-install.md) | <span data-ttu-id="2fc81-281">在计算机上安装全局工具。</span><span class="sxs-lookup"><span data-stu-id="2fc81-281">Installs a Global Tool on your machine.</span></span>
[<span data-ttu-id="2fc81-282">dotnet tool list</span><span class="sxs-lookup"><span data-stu-id="2fc81-282">dotnet tool list</span></span>](dotnet-tool-list.md) | <span data-ttu-id="2fc81-283">列出当前安装在计算机上的默认目录中或指定路径中的所有全局工具。</span><span class="sxs-lookup"><span data-stu-id="2fc81-283">Lists all Global Tools currently installed in the default directory on your machine or in the specified path.</span></span>
[<span data-ttu-id="2fc81-284">dotnet tool uninstall</span><span class="sxs-lookup"><span data-stu-id="2fc81-284">dotnet tool uninstall</span></span>](dotnet-tool-uninstall.md) | <span data-ttu-id="2fc81-285">从计算机中卸载全局工具。</span><span class="sxs-lookup"><span data-stu-id="2fc81-285">Uninstalls a Global Tool from your machine.</span></span>
[<span data-ttu-id="2fc81-286">dotnet tool update</span><span class="sxs-lookup"><span data-stu-id="2fc81-286">dotnet tool update</span></span>](dotnet-tool-update.md) | <span data-ttu-id="2fc81-287">在计算机上更新全局工具。</span><span class="sxs-lookup"><span data-stu-id="2fc81-287">Updates a Global Tool on your machine.</span></span>

### <a name="additional-tools"></a><span data-ttu-id="2fc81-288">其他工具</span><span class="sxs-lookup"><span data-stu-id="2fc81-288">Additional tools</span></span>

<span data-ttu-id="2fc81-289">自 .NET Core SDK 2.1.300 开始，许多使用 `DotnetCliToolReference` 的仅在每个项目的基础上可用的工具现作为 .NET Core SDK 的一部分提供。</span><span class="sxs-lookup"><span data-stu-id="2fc81-289">Starting with .NET Core SDK 2.1.300, a number of tools that were available only on a per project basis using `DotnetCliToolReference` are now available as part of the .NET Core SDK.</span></span> <span data-ttu-id="2fc81-290">下表中列出了这些工具：</span><span class="sxs-lookup"><span data-stu-id="2fc81-290">These tools are listed in the following table:</span></span>

| <span data-ttu-id="2fc81-291">工具</span><span class="sxs-lookup"><span data-stu-id="2fc81-291">Tool</span></span>                                              | <span data-ttu-id="2fc81-292">函数</span><span class="sxs-lookup"><span data-stu-id="2fc81-292">Function</span></span>                                                     |
| ------------------------------------------------- | ------------------------------------------------------------ |
| <span data-ttu-id="2fc81-293">dev-certs</span><span class="sxs-lookup"><span data-stu-id="2fc81-293">dev-certs</span></span>                                         | <span data-ttu-id="2fc81-294">创建和管理开发证书。</span><span class="sxs-lookup"><span data-stu-id="2fc81-294">Creates and manages development certificates.</span></span>                |
| [<span data-ttu-id="2fc81-295">ef</span><span class="sxs-lookup"><span data-stu-id="2fc81-295">ef</span></span>](/ef/core/miscellaneous/cli/dotnet)           | <span data-ttu-id="2fc81-296">Entity Framework Core 命令行工具。</span><span class="sxs-lookup"><span data-stu-id="2fc81-296">Entity Framework Core command-line tools.</span></span>                    |
| <span data-ttu-id="2fc81-297">sql-cache</span><span class="sxs-lookup"><span data-stu-id="2fc81-297">sql-cache</span></span>                                         | <span data-ttu-id="2fc81-298">SQL Server 缓存命令行工具。</span><span class="sxs-lookup"><span data-stu-id="2fc81-298">SQL Server cache command-line tools.</span></span>                         |
| [<span data-ttu-id="2fc81-299">user-secrets</span><span class="sxs-lookup"><span data-stu-id="2fc81-299">user-secrets</span></span>](/aspnet/core/security/app-secrets) | <span data-ttu-id="2fc81-300">管理开发用户机密。</span><span class="sxs-lookup"><span data-stu-id="2fc81-300">Manages development user secrets.</span></span>                            |
| [<span data-ttu-id="2fc81-301">watch</span><span class="sxs-lookup"><span data-stu-id="2fc81-301">watch</span></span>](/aspnet/core/tutorials/dotnet-watch)      | <span data-ttu-id="2fc81-302">启动文件观察程序，以在更改文件时运行命令。</span><span class="sxs-lookup"><span data-stu-id="2fc81-302">Starts a file watcher that runs a command when files change.</span></span> |

<span data-ttu-id="2fc81-303">有关每个工具的详细信息，请键入 `dotnet <tool-name> --help`。</span><span class="sxs-lookup"><span data-stu-id="2fc81-303">For more information about each tool, type `dotnet <tool-name> --help`.</span></span>

## <a name="examples"></a><span data-ttu-id="2fc81-304">示例</span><span class="sxs-lookup"><span data-stu-id="2fc81-304">Examples</span></span>

<span data-ttu-id="2fc81-305">创建新的 .NET Core 控制台应用程序：</span><span class="sxs-lookup"><span data-stu-id="2fc81-305">Creates a new .NET Core console application:</span></span>

`dotnet new console`

<span data-ttu-id="2fc81-306">还原给定应用程序的依赖项：</span><span class="sxs-lookup"><span data-stu-id="2fc81-306">Restore dependencies for a given application:</span></span>

`dotnet restore`

[!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]

<span data-ttu-id="2fc81-307">生成给定目录中的项目及其依赖项：</span><span class="sxs-lookup"><span data-stu-id="2fc81-307">Build a project and its dependencies in a given directory:</span></span>

`dotnet build`

<span data-ttu-id="2fc81-308">运行应用程序 DLL，如 `myapp.dll`：</span><span class="sxs-lookup"><span data-stu-id="2fc81-308">Run an application DLL, such as `myapp.dll`:</span></span>

`dotnet myapp.dll`

## <a name="environment-variables"></a><span data-ttu-id="2fc81-309">环境变量</span><span class="sxs-lookup"><span data-stu-id="2fc81-309">Environment variables</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="2fc81-310">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="2fc81-310">.NET Core 2.1</span></span>](#tab/netcore21)

`DOTNET_PACKAGES`

<span data-ttu-id="2fc81-311">主包缓存。</span><span class="sxs-lookup"><span data-stu-id="2fc81-311">The primary package cache.</span></span> <span data-ttu-id="2fc81-312">如果未设置，则默认为 Unix 上的 `$HOME/.nuget/packages` 或 Windows 上的 `%HOME%\NuGet\Packages`。</span><span class="sxs-lookup"><span data-stu-id="2fc81-312">If not set, it defaults to `$HOME/.nuget/packages` on Unix or `%HOME%\NuGet\Packages` on Windows.</span></span>

`DOTNET_SERVICING`

<span data-ttu-id="2fc81-313">指定加载运行时期间共享主机要使用的服务索引的位置。</span><span class="sxs-lookup"><span data-stu-id="2fc81-313">Specifies the location of the servicing index to use by the shared host when loading the runtime.</span></span>

`DOTNET_CLI_TELEMETRY_OPTOUT`

<span data-ttu-id="2fc81-314">指定是否收集并向 Microsoft 发送 .NET Core 工具使用情况的相关数据。</span><span class="sxs-lookup"><span data-stu-id="2fc81-314">Specifies whether data about the .NET Core tools usage is collected and sent to Microsoft.</span></span> <span data-ttu-id="2fc81-315">设置为 `true` 以选择退出遥测功能（接受的值为 `true`、`1` 或 `yes`）。</span><span class="sxs-lookup"><span data-stu-id="2fc81-315">Set to `true` to opt-out of the telemetry feature (values `true`, `1`, or `yes` accepted).</span></span> <span data-ttu-id="2fc81-316">否则，设置为 `false` 以选择加入遥测功能（接受的值为 `false`、`0` 或 `no`）。</span><span class="sxs-lookup"><span data-stu-id="2fc81-316">Otherwise, set to `false` to opt into the telemetry features (values `false`, `0`, or `no` accepted).</span></span> <span data-ttu-id="2fc81-317">如果未设置，则默认为 `false` 且遥测功能为活动状态。</span><span class="sxs-lookup"><span data-stu-id="2fc81-317">If not set, the default is `false` and the telemetry feature is active.</span></span>

`DOTNET_MULTILEVEL_LOOKUP`

<span data-ttu-id="2fc81-318">指定是否从全局位置解析 .NET Core 运行时、共享框架或 SDK。</span><span class="sxs-lookup"><span data-stu-id="2fc81-318">Specifies whether .NET Core runtime, shared framework, or SDK are resolved from the global location.</span></span> <span data-ttu-id="2fc81-319">如果未设置，则默认为 `true`。</span><span class="sxs-lookup"><span data-stu-id="2fc81-319">If not set, it defaults to `true`.</span></span> <span data-ttu-id="2fc81-320">设置为 `false` 不从全局位置解析，并且具有独立的 .NET Core 安装（接受的值为 `0` 或 `false`）。</span><span class="sxs-lookup"><span data-stu-id="2fc81-320">Set to `false` to not resolve from the global location and have isolated .NET Core installations (values `0` or `false` are accepted).</span></span> <span data-ttu-id="2fc81-321">有关多级别查找的详细信息，请参阅 [Multi-level SharedFX Lookup](https://github.com/dotnet/core-setup/blob/master/Documentation/design-docs/multilevel-sharedfx-lookup.md)（多级别 SharedFX 查找）。</span><span class="sxs-lookup"><span data-stu-id="2fc81-321">For more information about multi-level lookup, see [Multi-level SharedFX Lookup](https://github.com/dotnet/core-setup/blob/master/Documentation/design-docs/multilevel-sharedfx-lookup.md).</span></span>

`DOTNET_ROLL_FORWARD_ON_NO_CANDIDATE_FX`

<span data-ttu-id="2fc81-322">如果设置为 `0`，则禁用次要版本前滚。</span><span class="sxs-lookup"><span data-stu-id="2fc81-322">Disables minor version roll forward, if set to `0`.</span></span> <span data-ttu-id="2fc81-323">有关详细信息，请参阅[前滚](../whats-new/dotnet-core-2-1.md#roll-forward)。</span><span class="sxs-lookup"><span data-stu-id="2fc81-323">For more information, see [Roll forward](../whats-new/dotnet-core-2-1.md#roll-forward).</span></span>

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="2fc81-324">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="2fc81-324">.NET Core 2.0</span></span>](#tab/netcore20)

`DOTNET_PACKAGES`

<span data-ttu-id="2fc81-325">主包缓存。</span><span class="sxs-lookup"><span data-stu-id="2fc81-325">The primary package cache.</span></span> <span data-ttu-id="2fc81-326">如果未设置，则默认为 Unix 上的 `$HOME/.nuget/packages` 或 Windows 上的 `%HOME%\NuGet\Packages`。</span><span class="sxs-lookup"><span data-stu-id="2fc81-326">If not set, it defaults to `$HOME/.nuget/packages` on Unix or `%HOME%\NuGet\Packages` on Windows.</span></span>

`DOTNET_SERVICING`

<span data-ttu-id="2fc81-327">指定加载运行时期间共享主机要使用的服务索引的位置。</span><span class="sxs-lookup"><span data-stu-id="2fc81-327">Specifies the location of the servicing index to use by the shared host when loading the runtime.</span></span>

`DOTNET_CLI_TELEMETRY_OPTOUT`

<span data-ttu-id="2fc81-328">指定是否收集并向 Microsoft 发送 .NET Core 工具使用情况的相关数据。</span><span class="sxs-lookup"><span data-stu-id="2fc81-328">Specifies whether data about the .NET Core tools usage is collected and sent to Microsoft.</span></span> <span data-ttu-id="2fc81-329">设置为 `true` 以选择退出遥测功能（接受的值为 `true`、`1` 或 `yes`）。</span><span class="sxs-lookup"><span data-stu-id="2fc81-329">Set to `true` to opt-out of the telemetry feature (values `true`, `1`, or `yes` accepted).</span></span> <span data-ttu-id="2fc81-330">否则，设置为 `false` 以选择加入遥测功能（接受的值为 `false`、`0` 或 `no`）。</span><span class="sxs-lookup"><span data-stu-id="2fc81-330">Otherwise, set to `false` to opt into the telemetry features (values `false`, `0`, or `no` accepted).</span></span> <span data-ttu-id="2fc81-331">如果未设置，则默认为 `false` 且遥测功能为活动状态。</span><span class="sxs-lookup"><span data-stu-id="2fc81-331">If not set, the default is `false` and the telemetry feature is active.</span></span>

`DOTNET_MULTILEVEL_LOOKUP`

<span data-ttu-id="2fc81-332">指定是否从全局位置解析 .NET Core 运行时、共享框架或 SDK。</span><span class="sxs-lookup"><span data-stu-id="2fc81-332">Specifies whether .NET Core runtime, shared framework, or SDK are resolved from the global location.</span></span> <span data-ttu-id="2fc81-333">如果未设置，则默认为 `true`。</span><span class="sxs-lookup"><span data-stu-id="2fc81-333">If not set, it defaults to `true`.</span></span> <span data-ttu-id="2fc81-334">设置为 `false` 不从全局位置解析，并且具有独立的 .NET Core 安装（接受的值为 `0` 或 `false`）。</span><span class="sxs-lookup"><span data-stu-id="2fc81-334">Set to `false` to not resolve from the global location and have isolated .NET Core installations (values `0` or `false` are accepted).</span></span> <span data-ttu-id="2fc81-335">有关多级别查找的详细信息，请参阅 [Multi-level SharedFX Lookup](https://github.com/dotnet/core-setup/blob/master/Documentation/design-docs/multilevel-sharedfx-lookup.md)（多级别 SharedFX 查找）。</span><span class="sxs-lookup"><span data-stu-id="2fc81-335">For more information about multi-level lookup, see [Multi-level SharedFX Lookup](https://github.com/dotnet/core-setup/blob/master/Documentation/design-docs/multilevel-sharedfx-lookup.md).</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="2fc81-336">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="2fc81-336">.NET Core 1.x</span></span>](#tab/netcore1x)

`DOTNET_PACKAGES`

<span data-ttu-id="2fc81-337">主包缓存。</span><span class="sxs-lookup"><span data-stu-id="2fc81-337">The primary package cache.</span></span> <span data-ttu-id="2fc81-338">如果未设置，则默认为 Unix 上的 `$HOME/.nuget/packages` 或 Windows 上的 `%HOME%\NuGet\Packages`。</span><span class="sxs-lookup"><span data-stu-id="2fc81-338">If not set, it defaults to `$HOME/.nuget/packages` on Unix or `%HOME%\NuGet\Packages` on Windows.</span></span>

`DOTNET_SERVICING`

<span data-ttu-id="2fc81-339">指定加载运行时期间共享主机要使用的服务索引的位置。</span><span class="sxs-lookup"><span data-stu-id="2fc81-339">Specifies the location of the servicing index to use by the shared host when loading the runtime.</span></span>

`DOTNET_CLI_TELEMETRY_OPTOUT`

<span data-ttu-id="2fc81-340">指定是否收集并向 Microsoft 发送 .NET Core 工具使用情况的相关数据。</span><span class="sxs-lookup"><span data-stu-id="2fc81-340">Specifies whether data about the .NET Core tools usage is collected and sent to Microsoft.</span></span> <span data-ttu-id="2fc81-341">设置为 `true` 以选择退出遥测功能（接受的值为 `true`、`1` 或 `yes`）。</span><span class="sxs-lookup"><span data-stu-id="2fc81-341">Set to `true` to opt-out of the telemetry feature (values `true`, `1`, or `yes` accepted).</span></span> <span data-ttu-id="2fc81-342">否则，设置为 `false` 以选择加入遥测功能（接受的值为 `false`、`0` 或 `no`）。</span><span class="sxs-lookup"><span data-stu-id="2fc81-342">Otherwise, set to `false` to opt into the telemetry features (values `false`, `0`, or `no` accepted).</span></span> <span data-ttu-id="2fc81-343">如果未设置，则默认为 `false` 且遥测功能为活动状态。</span><span class="sxs-lookup"><span data-stu-id="2fc81-343">If not set, the default is `false` and the telemetry feature is active.</span></span>

---
