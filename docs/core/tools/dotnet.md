---
title: dotnet 命令
description: 了解 dotnet 命令（.NET Core CLI 工具的通用驱动程序）及其用法。
ms.date: 06/04/2018
ms.openlocfilehash: 2134bf8ed66157619499b027f01d39e03e84411f
ms.sourcegitcommit: 83ecdf731dc1920bca31f017b1556c917aafd7a0
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/12/2019
ms.locfileid: "67859555"
---
# <a name="dotnet-command"></a><span data-ttu-id="78c02-103">dotnet 命令</span><span class="sxs-lookup"><span data-stu-id="78c02-103">dotnet command</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="78c02-104">name</span><span class="sxs-lookup"><span data-stu-id="78c02-104">Name</span></span>

<span data-ttu-id="78c02-105">`dotnet` - 一款管理 .NET 源代码和二进制文件的工具。</span><span class="sxs-lookup"><span data-stu-id="78c02-105">`dotnet` - A tool for managing .NET source code and binaries.</span></span>

## <a name="synopsis"></a><span data-ttu-id="78c02-106">摘要</span><span class="sxs-lookup"><span data-stu-id="78c02-106">Synopsis</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="78c02-107">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="78c02-107">.NET Core 2.1</span></span>](#tab/netcore21)

```
dotnet [command] [arguments] [--additional-deps] [--additionalprobingpath] [-d|--diagnostics] [--fx-version]
    [-h|--help] [--info] [--list-runtimes] [--list-sdks] [--roll-forward-on-no-candidate-fx] [-v|--verbosity] [--version]
```

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="78c02-108">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="78c02-108">.NET Core 2.0</span></span>](#tab/netcore20)

```
dotnet [command] [arguments] [--additional-deps] [--additionalprobingpath] [-d|--diagnostics]
    [--fx-version] [-h|--help] [--info] [--roll-forward-on-no-candidate-fx] [-v|--verbosity] [--version]
```

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="78c02-109">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="78c02-109">.NET Core 1.x</span></span>](#tab/netcore1x)

```
dotnet [command] [arguments] [--additionalprobingpath] [-d|--diagnostics] [--fx-version]
    [-h|--help] [--info] [-v|--verbosity] [--version]
```

---

## <a name="description"></a><span data-ttu-id="78c02-110">说明</span><span class="sxs-lookup"><span data-stu-id="78c02-110">Description</span></span>

<span data-ttu-id="78c02-111">`dotnet` 是一款管理 .NET 源代码和二进制文件的工具。</span><span class="sxs-lookup"><span data-stu-id="78c02-111">`dotnet` is a tool for managing .NET source code and binaries.</span></span> <span data-ttu-id="78c02-112">它公开执行特定任务的命令，例如 [`dotnet build`](dotnet-build.md) 和 [`dotnet run`](dotnet-run.md)。</span><span class="sxs-lookup"><span data-stu-id="78c02-112">It exposes commands that perform specific tasks, such as [`dotnet build`](dotnet-build.md) and [`dotnet run`](dotnet-run.md).</span></span> <span data-ttu-id="78c02-113">每个命令都定义自己的参数。</span><span class="sxs-lookup"><span data-stu-id="78c02-113">Each command defines its own arguments.</span></span> <span data-ttu-id="78c02-114">在每个命令后键入 `--help` 以访问简要帮助文档。</span><span class="sxs-lookup"><span data-stu-id="78c02-114">Type `--help` after each command to access brief help documentation.</span></span>

<span data-ttu-id="78c02-115">可以使用 `dotnet` 来运行应用程序，方法是指定应用程序 DLL，如 `dotnet myapp.dll`.</span><span class="sxs-lookup"><span data-stu-id="78c02-115">`dotnet` can be used to run applications, by specifying an application DLL, such as `dotnet myapp.dll`.</span></span> <span data-ttu-id="78c02-116">要了解部署选项，请参阅 [.NET Core 应用程序部署](../deploying/index.md)。</span><span class="sxs-lookup"><span data-stu-id="78c02-116">See [.NET Core application deployment](../deploying/index.md) for to learn about deployment options.</span></span>

## <a name="options"></a><span data-ttu-id="78c02-117">选项</span><span class="sxs-lookup"><span data-stu-id="78c02-117">Options</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="78c02-118">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="78c02-118">.NET Core 2.1</span></span>](#tab/netcore21)

`--additional-deps <PATH>`

<span data-ttu-id="78c02-119">其他 deps.json  文件的路径。</span><span class="sxs-lookup"><span data-stu-id="78c02-119">Path to additional *deps.json* file.</span></span>

`--additionalprobingpath <PATH>`

<span data-ttu-id="78c02-120">包含要进行探测的探测策略和程序集的路径。</span><span class="sxs-lookup"><span data-stu-id="78c02-120">Path containing probing policy and assemblies to probe.</span></span>

`-d|--diagnostics`

<span data-ttu-id="78c02-121">启用诊断输出。</span><span class="sxs-lookup"><span data-stu-id="78c02-121">Enables diagnostic output.</span></span>

`--fx-version <VERSION>`

<span data-ttu-id="78c02-122">用于运行应用程序的 .NET Core 运行时版本。</span><span class="sxs-lookup"><span data-stu-id="78c02-122">Version of the .NET Core runtime to use to run the application.</span></span>

`-h|--help`

<span data-ttu-id="78c02-123">打印出给定命令的文档，如 `dotnet build --help`。</span><span class="sxs-lookup"><span data-stu-id="78c02-123">Prints out documentation for a given command, such as `dotnet build --help`.</span></span> <span data-ttu-id="78c02-124">`dotnet --help` 打印可用命令列表。</span><span class="sxs-lookup"><span data-stu-id="78c02-124">`dotnet --help` prints a list of available commands.</span></span>

`--info`

<span data-ttu-id="78c02-125">打印出有关 .NET Core 安装和计算机环境（如当前操作系统）的详细信息，并提交 .NET Core 版本的 SHA。</span><span class="sxs-lookup"><span data-stu-id="78c02-125">Prints out detailed information about a .NET Core installation and the machine environment, such as the current operating system, and commit SHA of the .NET Core version.</span></span>

`--list-runtimes`

<span data-ttu-id="78c02-126">显示已安装的 .NET Core 运行时。</span><span class="sxs-lookup"><span data-stu-id="78c02-126">Displays the installed .NET Core runtimes.</span></span>

`--list-sdks`

<span data-ttu-id="78c02-127">显示已安装的 .NET Core SDK。</span><span class="sxs-lookup"><span data-stu-id="78c02-127">Displays the installed .NET Core SDKs.</span></span>

`--roll-forward-on-no-candidate-fx <N>`

<span data-ttu-id="78c02-128">所需的共享框架不可用时，请定义行为。</span><span class="sxs-lookup"><span data-stu-id="78c02-128">Defines behavior when the required shared framework is not available.</span></span> <span data-ttu-id="78c02-129">`N` 可以是：</span><span class="sxs-lookup"><span data-stu-id="78c02-129">`N` can be:</span></span>
* <span data-ttu-id="78c02-130">`0` - 禁用次要版本前滚。</span><span class="sxs-lookup"><span data-stu-id="78c02-130">`0` - Disable even minor version roll forward.</span></span>
* <span data-ttu-id="78c02-131">`1` - 前滚次要版本，但不前滚主版本。</span><span class="sxs-lookup"><span data-stu-id="78c02-131">`1` - Roll forward on minor version, but not on major version.</span></span> <span data-ttu-id="78c02-132">这是默认行为。</span><span class="sxs-lookup"><span data-stu-id="78c02-132">This is the default behavior.</span></span>
* <span data-ttu-id="78c02-133">`2` - 前滚次要和主版本。</span><span class="sxs-lookup"><span data-stu-id="78c02-133">`2` - Roll forward on minor and major versions.</span></span>

 <span data-ttu-id="78c02-134">有关详细信息，请参阅[前滚](../whats-new/dotnet-core-2-1.md#roll-forward)。</span><span class="sxs-lookup"><span data-stu-id="78c02-134">For more information, see [Roll forward](../whats-new/dotnet-core-2-1.md#roll-forward).</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="78c02-135">设置命令的详细级别。</span><span class="sxs-lookup"><span data-stu-id="78c02-135">Sets the verbosity level of the command.</span></span> <span data-ttu-id="78c02-136">允许使用的值为 `q[uiet]`、`m[inimal]`、`n[ormal]`、`d[etailed]` 和 `diag[nostic]`。</span><span class="sxs-lookup"><span data-stu-id="78c02-136">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="78c02-137">并非在每个命令中均受支持；请参阅特定的命令页，确定此选项是否可用。</span><span class="sxs-lookup"><span data-stu-id="78c02-137">Not supported in every command; see specific command page to determine if this option is available.</span></span>

`--version`

<span data-ttu-id="78c02-138">打印使用中的 .NET Core SDK 版本。</span><span class="sxs-lookup"><span data-stu-id="78c02-138">Prints out the version of the .NET Core SDK in use.</span></span>

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="78c02-139">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="78c02-139">.NET Core 2.0</span></span>](#tab/netcore20)

`--additional-deps <PATH>`

<span data-ttu-id="78c02-140">其他 deps.json  文件的路径。</span><span class="sxs-lookup"><span data-stu-id="78c02-140">Path to additional *deps.json* file.</span></span>

`--additionalprobingpath <PATH>`

<span data-ttu-id="78c02-141">包含要进行探测的探测策略和程序集的路径。</span><span class="sxs-lookup"><span data-stu-id="78c02-141">Path containing probing policy and assemblies to probe.</span></span>

`-d|--diagnostics`

<span data-ttu-id="78c02-142">启用诊断输出。</span><span class="sxs-lookup"><span data-stu-id="78c02-142">Enables diagnostic output.</span></span>

`--fx-version <VERSION>`

<span data-ttu-id="78c02-143">用于运行应用程序的 .NET Core 运行时版本。</span><span class="sxs-lookup"><span data-stu-id="78c02-143">Version of the .NET Core runtime to use to run the application.</span></span>

`-h|--help`

<span data-ttu-id="78c02-144">打印出给定命令的文档，如 `dotnet build --help`。</span><span class="sxs-lookup"><span data-stu-id="78c02-144">Prints out documentation for a given command, such as `dotnet build --help`.</span></span> <span data-ttu-id="78c02-145">`dotnet --help` 打印可用命令列表。</span><span class="sxs-lookup"><span data-stu-id="78c02-145">`dotnet --help` prints a list of available commands.</span></span>

`--info`

<span data-ttu-id="78c02-146">打印出有关 .NET Core 安装和计算机环境（如当前操作系统）的详细信息，并提交 .NET Core 版本的 SHA。</span><span class="sxs-lookup"><span data-stu-id="78c02-146">Prints out detailed information about a .NET Core installation and the machine environment, such as the current operating system, and commit SHA of the .NET Core version.</span></span>

`--roll-forward-on-no-candidate-fx`

 <span data-ttu-id="78c02-147">如果设置为 `0`，则禁用次要版本前滚。</span><span class="sxs-lookup"><span data-stu-id="78c02-147">Disables minor version roll forward, if set to `0`.</span></span> <span data-ttu-id="78c02-148">有关详细信息，请参阅[前滚](../whats-new/dotnet-core-2-1.md#roll-forward)。</span><span class="sxs-lookup"><span data-stu-id="78c02-148">For more information, see [Roll forward](../whats-new/dotnet-core-2-1.md#roll-forward).</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="78c02-149">设置命令的详细级别。</span><span class="sxs-lookup"><span data-stu-id="78c02-149">Sets the verbosity level of the command.</span></span> <span data-ttu-id="78c02-150">允许使用的值为 `q[uiet]`、`m[inimal]`、`n[ormal]`、`d[etailed]` 和 `diag[nostic]`。</span><span class="sxs-lookup"><span data-stu-id="78c02-150">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="78c02-151">并非在每个命令中均受支持；请参阅特定的命令页，确定此选项是否可用。</span><span class="sxs-lookup"><span data-stu-id="78c02-151">Not supported in every command; see specific command page to determine if this option is available.</span></span>

`--version`

<span data-ttu-id="78c02-152">打印使用中的 .NET Core SDK 版本。</span><span class="sxs-lookup"><span data-stu-id="78c02-152">Prints out the version of the .NET Core SDK in use.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="78c02-153">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="78c02-153">.NET Core 1.x</span></span>](#tab/netcore1x)

`--additionalprobingpath <PATH>`

<span data-ttu-id="78c02-154">包含要进行探测的探测策略和程序集的路径。</span><span class="sxs-lookup"><span data-stu-id="78c02-154">Path containing probing policy and assemblies to probe.</span></span>

`-d|--diagnostics`

<span data-ttu-id="78c02-155">启用诊断输出。</span><span class="sxs-lookup"><span data-stu-id="78c02-155">Enables diagnostic output.</span></span>

`--fx-version <VERSION>`

<span data-ttu-id="78c02-156">用于运行应用程序的 .NET Core 运行时版本。</span><span class="sxs-lookup"><span data-stu-id="78c02-156">Version of the .NET Core runtime to use to run the application.</span></span>

`-h|--help`

<span data-ttu-id="78c02-157">打印出给定命令的文档，如 `dotnet build --help`。</span><span class="sxs-lookup"><span data-stu-id="78c02-157">Prints out documentation for a given command, such as `dotnet build --help`.</span></span> <span data-ttu-id="78c02-158">`dotnet --help` 打印可用命令列表。</span><span class="sxs-lookup"><span data-stu-id="78c02-158">`dotnet --help` prints a list of available commands.</span></span>

`--info`

<span data-ttu-id="78c02-159">打印出有关 .NET Core 安装和计算机环境（如当前操作系统）的详细信息，并提交 .NET Core 版本的 SHA。</span><span class="sxs-lookup"><span data-stu-id="78c02-159">Prints out detailed information about a .NET Core installation and the machine environment, such as the current operating system, and commit SHA of the .NET Core version.</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="78c02-160">设置命令的详细级别。</span><span class="sxs-lookup"><span data-stu-id="78c02-160">Sets the verbosity level of the command.</span></span> <span data-ttu-id="78c02-161">允许使用的值为 `q[uiet]`、`m[inimal]`、`n[ormal]`、`d[etailed]` 和 `diag[nostic]`。</span><span class="sxs-lookup"><span data-stu-id="78c02-161">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="78c02-162">并非在每个命令中均受支持；请参阅特定的命令页，确定此选项是否可用。</span><span class="sxs-lookup"><span data-stu-id="78c02-162">Not supported in every command; see specific command page to determine if this option is available.</span></span>

`--version`

<span data-ttu-id="78c02-163">打印使用中的 .NET Core SDK 版本。</span><span class="sxs-lookup"><span data-stu-id="78c02-163">Prints out the version of the .NET Core SDK in use.</span></span>

---

## <a name="dotnet-commands"></a><span data-ttu-id="78c02-164">dotnet 命令</span><span class="sxs-lookup"><span data-stu-id="78c02-164">dotnet commands</span></span>

### <a name="general"></a><span data-ttu-id="78c02-165">常规</span><span class="sxs-lookup"><span data-stu-id="78c02-165">General</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="78c02-166">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="78c02-166">.NET Core 2.1</span></span>](#tab/netcore21)

| <span data-ttu-id="78c02-167">命令</span><span class="sxs-lookup"><span data-stu-id="78c02-167">Command</span></span>                                       | <span data-ttu-id="78c02-168">函数</span><span class="sxs-lookup"><span data-stu-id="78c02-168">Function</span></span>                                                            |
| --------------------------------------------- | ------------------------------------------------------------------- |
| [<span data-ttu-id="78c02-169">dotnet build</span><span class="sxs-lookup"><span data-stu-id="78c02-169">dotnet build</span></span>](dotnet-build.md)               | <span data-ttu-id="78c02-170">生成 .NET Core 应用程序。</span><span class="sxs-lookup"><span data-stu-id="78c02-170">Builds a .NET Core application.</span></span>                                     |
| [<span data-ttu-id="78c02-171">dotnet build-server</span><span class="sxs-lookup"><span data-stu-id="78c02-171">dotnet build-server</span></span>](dotnet-build-server.md) | <span data-ttu-id="78c02-172">与通过生成启动的服务器进行交互。</span><span class="sxs-lookup"><span data-stu-id="78c02-172">Interacts with servers started by a build.</span></span>                          |
| [<span data-ttu-id="78c02-173">dotnet clean</span><span class="sxs-lookup"><span data-stu-id="78c02-173">dotnet clean</span></span>](dotnet-clean.md)               | <span data-ttu-id="78c02-174">清除生成输出。</span><span class="sxs-lookup"><span data-stu-id="78c02-174">Clean build outputs.</span></span>                                                |
| [<span data-ttu-id="78c02-175">dotnet help</span><span class="sxs-lookup"><span data-stu-id="78c02-175">dotnet help</span></span>](dotnet-help.md)                 | <span data-ttu-id="78c02-176">显示命令更详细的在线文档。</span><span class="sxs-lookup"><span data-stu-id="78c02-176">Shows more detailed documentation online for the command.</span></span>           |
| [<span data-ttu-id="78c02-177">dotnet migrate</span><span class="sxs-lookup"><span data-stu-id="78c02-177">dotnet migrate</span></span>](dotnet-migrate.md)           | <span data-ttu-id="78c02-178">将有效的预览版 2 项目迁移到 .NET Core SDK 1.0 项目。</span><span class="sxs-lookup"><span data-stu-id="78c02-178">Migrates a valid Preview 2 project to a .NET Core SDK 1.0 project.</span></span>  |
| [<span data-ttu-id="78c02-179">dotnet msbuild</span><span class="sxs-lookup"><span data-stu-id="78c02-179">dotnet msbuild</span></span>](dotnet-msbuild.md)           | <span data-ttu-id="78c02-180">提供对 MSBuild 命令行的访问权限。</span><span class="sxs-lookup"><span data-stu-id="78c02-180">Provides access to the MSBuild command line.</span></span>                        |
| [<span data-ttu-id="78c02-181">dotnet new</span><span class="sxs-lookup"><span data-stu-id="78c02-181">dotnet new</span></span>](dotnet-new.md)                   | <span data-ttu-id="78c02-182">为给定的模板初始化 C# 或 F# 项目。</span><span class="sxs-lookup"><span data-stu-id="78c02-182">Initializes a C# or F# project for a given template.</span></span>                |
| [<span data-ttu-id="78c02-183">dotnet pack</span><span class="sxs-lookup"><span data-stu-id="78c02-183">dotnet pack</span></span>](dotnet-pack.md)                 | <span data-ttu-id="78c02-184">创建代码的 NuGet 包。</span><span class="sxs-lookup"><span data-stu-id="78c02-184">Creates a NuGet package of your code.</span></span>                               |
| [<span data-ttu-id="78c02-185">dotnet publish</span><span class="sxs-lookup"><span data-stu-id="78c02-185">dotnet publish</span></span>](dotnet-publish.md)           | <span data-ttu-id="78c02-186">发布 .NET 依赖于框架或独立应用程序。</span><span class="sxs-lookup"><span data-stu-id="78c02-186">Publishes a .NET framework-dependent or self-contained application.</span></span> |
| [<span data-ttu-id="78c02-187">dotnet restore</span><span class="sxs-lookup"><span data-stu-id="78c02-187">dotnet restore</span></span>](dotnet-restore.md)           | <span data-ttu-id="78c02-188">还原给定应用程序的依赖项。</span><span class="sxs-lookup"><span data-stu-id="78c02-188">Restores the dependencies for a given application.</span></span>                  |
| [<span data-ttu-id="78c02-189">dotnet run</span><span class="sxs-lookup"><span data-stu-id="78c02-189">dotnet run</span></span>](dotnet-run.md)                   | <span data-ttu-id="78c02-190">从源运行应用程序。</span><span class="sxs-lookup"><span data-stu-id="78c02-190">Runs the application from source.</span></span>                                   |
| [<span data-ttu-id="78c02-191">dotnet sln</span><span class="sxs-lookup"><span data-stu-id="78c02-191">dotnet sln</span></span>](dotnet-sln.md)                   | <span data-ttu-id="78c02-192">用于添加、删除和列出解决方案文件中项目的选项。</span><span class="sxs-lookup"><span data-stu-id="78c02-192">Options to add, remove, and list projects in a solution file.</span></span>       |
| [<span data-ttu-id="78c02-193">dotnet store</span><span class="sxs-lookup"><span data-stu-id="78c02-193">dotnet store</span></span>](dotnet-store.md)               | <span data-ttu-id="78c02-194">将程序集存储到运行时包存储区。</span><span class="sxs-lookup"><span data-stu-id="78c02-194">Stores assemblies in the runtime package store.</span></span>                     |
| [<span data-ttu-id="78c02-195">dotnet test</span><span class="sxs-lookup"><span data-stu-id="78c02-195">dotnet test</span></span>](dotnet-test.md)                 | <span data-ttu-id="78c02-196">使用测试运行程序运行测试。</span><span class="sxs-lookup"><span data-stu-id="78c02-196">Runs tests using a test runner.</span></span>                                     |

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="78c02-197">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="78c02-197">.NET Core 2.0</span></span>](#tab/netcore20)

| <span data-ttu-id="78c02-198">命令</span><span class="sxs-lookup"><span data-stu-id="78c02-198">Command</span></span>                             | <span data-ttu-id="78c02-199">函数</span><span class="sxs-lookup"><span data-stu-id="78c02-199">Function</span></span>                                                            |
| ----------------------------------- | ------------------------------------------------------------------- |
| [<span data-ttu-id="78c02-200">dotnet build</span><span class="sxs-lookup"><span data-stu-id="78c02-200">dotnet build</span></span>](dotnet-build.md)     | <span data-ttu-id="78c02-201">生成 .NET Core 应用程序。</span><span class="sxs-lookup"><span data-stu-id="78c02-201">Builds a .NET Core application.</span></span>                                     |
| [<span data-ttu-id="78c02-202">dotnet clean</span><span class="sxs-lookup"><span data-stu-id="78c02-202">dotnet clean</span></span>](dotnet-clean.md)     | <span data-ttu-id="78c02-203">清除生成输出。</span><span class="sxs-lookup"><span data-stu-id="78c02-203">Clean build outputs.</span></span>                                              |
| [<span data-ttu-id="78c02-204">dotnet help</span><span class="sxs-lookup"><span data-stu-id="78c02-204">dotnet help</span></span>](dotnet-help.md)       | <span data-ttu-id="78c02-205">显示命令更详细的在线文档。</span><span class="sxs-lookup"><span data-stu-id="78c02-205">Shows more detailed documentation online for the command.</span></span>           |
| [<span data-ttu-id="78c02-206">dotnet migrate</span><span class="sxs-lookup"><span data-stu-id="78c02-206">dotnet migrate</span></span>](dotnet-migrate.md) | <span data-ttu-id="78c02-207">将有效的预览版 2 项目迁移到 .NET Core SDK 1.0 项目。</span><span class="sxs-lookup"><span data-stu-id="78c02-207">Migrates a valid Preview 2 project to a .NET Core SDK 1.0 project.</span></span>  |
| [<span data-ttu-id="78c02-208">dotnet msbuild</span><span class="sxs-lookup"><span data-stu-id="78c02-208">dotnet msbuild</span></span>](dotnet-msbuild.md) | <span data-ttu-id="78c02-209">提供对 MSBuild 命令行的访问权限。</span><span class="sxs-lookup"><span data-stu-id="78c02-209">Provides access to the MSBuild command line.</span></span>                        |
| [<span data-ttu-id="78c02-210">dotnet new</span><span class="sxs-lookup"><span data-stu-id="78c02-210">dotnet new</span></span>](dotnet-new.md)         | <span data-ttu-id="78c02-211">为给定的模板初始化 C# 或 F# 项目。</span><span class="sxs-lookup"><span data-stu-id="78c02-211">Initializes a C# or F# project for a given template.</span></span>                |
| [<span data-ttu-id="78c02-212">dotnet pack</span><span class="sxs-lookup"><span data-stu-id="78c02-212">dotnet pack</span></span>](dotnet-pack.md)       | <span data-ttu-id="78c02-213">创建代码的 NuGet 包。</span><span class="sxs-lookup"><span data-stu-id="78c02-213">Creates a NuGet package of your code.</span></span>                               |
| [<span data-ttu-id="78c02-214">dotnet publish</span><span class="sxs-lookup"><span data-stu-id="78c02-214">dotnet publish</span></span>](dotnet-publish.md) | <span data-ttu-id="78c02-215">发布 .NET 依赖于框架或独立应用程序。</span><span class="sxs-lookup"><span data-stu-id="78c02-215">Publishes a .NET framework-dependent or self-contained application.</span></span> |
| [<span data-ttu-id="78c02-216">dotnet restore</span><span class="sxs-lookup"><span data-stu-id="78c02-216">dotnet restore</span></span>](dotnet-restore.md) | <span data-ttu-id="78c02-217">还原给定应用程序的依赖项。</span><span class="sxs-lookup"><span data-stu-id="78c02-217">Restores the dependencies for a given application.</span></span>                  |
| [<span data-ttu-id="78c02-218">dotnet run</span><span class="sxs-lookup"><span data-stu-id="78c02-218">dotnet run</span></span>](dotnet-run.md)         | <span data-ttu-id="78c02-219">从源运行应用程序。</span><span class="sxs-lookup"><span data-stu-id="78c02-219">Runs the application from source.</span></span>                                   |
| [<span data-ttu-id="78c02-220">dotnet sln</span><span class="sxs-lookup"><span data-stu-id="78c02-220">dotnet sln</span></span>](dotnet-sln.md)         | <span data-ttu-id="78c02-221">用于添加、删除和列出解决方案文件中项目的选项。</span><span class="sxs-lookup"><span data-stu-id="78c02-221">Options to add, remove, and list projects in a solution file.</span></span>       |
| [<span data-ttu-id="78c02-222">dotnet store</span><span class="sxs-lookup"><span data-stu-id="78c02-222">dotnet store</span></span>](dotnet-store.md)     | <span data-ttu-id="78c02-223">将程序集存储到运行时包存储区。</span><span class="sxs-lookup"><span data-stu-id="78c02-223">Stores assemblies in the runtime package store.</span></span>                     |
| [<span data-ttu-id="78c02-224">dotnet test</span><span class="sxs-lookup"><span data-stu-id="78c02-224">dotnet test</span></span>](dotnet-test.md)       | <span data-ttu-id="78c02-225">使用测试运行程序运行测试。</span><span class="sxs-lookup"><span data-stu-id="78c02-225">Runs tests using a test runner.</span></span>                                     |

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="78c02-226">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="78c02-226">.NET Core 1.x</span></span>](#tab/netcore1x)

| <span data-ttu-id="78c02-227">命令</span><span class="sxs-lookup"><span data-stu-id="78c02-227">Command</span></span>                             | <span data-ttu-id="78c02-228">函数</span><span class="sxs-lookup"><span data-stu-id="78c02-228">Function</span></span>                                                            |
| ----------------------------------- | ------------------------------------------------------------------- |
| [<span data-ttu-id="78c02-229">dotnet build</span><span class="sxs-lookup"><span data-stu-id="78c02-229">dotnet build</span></span>](dotnet-build.md)     | <span data-ttu-id="78c02-230">生成 .NET Core 应用程序。</span><span class="sxs-lookup"><span data-stu-id="78c02-230">Builds a .NET Core application.</span></span>                                     |
| [<span data-ttu-id="78c02-231">dotnet clean</span><span class="sxs-lookup"><span data-stu-id="78c02-231">dotnet clean</span></span>](dotnet-clean.md)     | <span data-ttu-id="78c02-232">清除生成输出。</span><span class="sxs-lookup"><span data-stu-id="78c02-232">Clean build outputs.</span></span>                                              |
| [<span data-ttu-id="78c02-233">dotnet migrate</span><span class="sxs-lookup"><span data-stu-id="78c02-233">dotnet migrate</span></span>](dotnet-migrate.md) | <span data-ttu-id="78c02-234">将有效的预览版 2 项目迁移到 .NET Core SDK 1.0 项目。</span><span class="sxs-lookup"><span data-stu-id="78c02-234">Migrates a valid Preview 2 project to a .NET Core SDK 1.0 project.</span></span>  |
| [<span data-ttu-id="78c02-235">dotnet msbuild</span><span class="sxs-lookup"><span data-stu-id="78c02-235">dotnet msbuild</span></span>](dotnet-msbuild.md) | <span data-ttu-id="78c02-236">提供对 MSBuild 命令行的访问权限。</span><span class="sxs-lookup"><span data-stu-id="78c02-236">Provides access to the MSBuild command line.</span></span>                        |
| [<span data-ttu-id="78c02-237">dotnet new</span><span class="sxs-lookup"><span data-stu-id="78c02-237">dotnet new</span></span>](dotnet-new.md)         | <span data-ttu-id="78c02-238">为给定的模板初始化 C# 或 F# 项目。</span><span class="sxs-lookup"><span data-stu-id="78c02-238">Initializes a C# or F# project for a given template.</span></span>                |
| [<span data-ttu-id="78c02-239">dotnet pack</span><span class="sxs-lookup"><span data-stu-id="78c02-239">dotnet pack</span></span>](dotnet-pack.md)       | <span data-ttu-id="78c02-240">创建代码的 NuGet 包。</span><span class="sxs-lookup"><span data-stu-id="78c02-240">Creates a NuGet package of your code.</span></span>                               |
| [<span data-ttu-id="78c02-241">dotnet publish</span><span class="sxs-lookup"><span data-stu-id="78c02-241">dotnet publish</span></span>](dotnet-publish.md) | <span data-ttu-id="78c02-242">发布 .NET 依赖于框架或独立应用程序。</span><span class="sxs-lookup"><span data-stu-id="78c02-242">Publishes a .NET framework-dependent or self-contained application.</span></span> |
| [<span data-ttu-id="78c02-243">dotnet restore</span><span class="sxs-lookup"><span data-stu-id="78c02-243">dotnet restore</span></span>](dotnet-restore.md) | <span data-ttu-id="78c02-244">还原给定应用程序的依赖项。</span><span class="sxs-lookup"><span data-stu-id="78c02-244">Restores the dependencies for a given application.</span></span>                  |
| [<span data-ttu-id="78c02-245">dotnet run</span><span class="sxs-lookup"><span data-stu-id="78c02-245">dotnet run</span></span>](dotnet-run.md)         | <span data-ttu-id="78c02-246">从源运行应用程序。</span><span class="sxs-lookup"><span data-stu-id="78c02-246">Runs the application from source.</span></span>                                   |
| [<span data-ttu-id="78c02-247">dotnet sln</span><span class="sxs-lookup"><span data-stu-id="78c02-247">dotnet sln</span></span>](dotnet-sln.md)         | <span data-ttu-id="78c02-248">用于添加、删除和列出解决方案文件中项目的选项。</span><span class="sxs-lookup"><span data-stu-id="78c02-248">Options to add, remove, and list projects in a solution file.</span></span>       |
| [<span data-ttu-id="78c02-249">dotnet test</span><span class="sxs-lookup"><span data-stu-id="78c02-249">dotnet test</span></span>](dotnet-test.md)       | <span data-ttu-id="78c02-250">使用测试运行程序运行测试。</span><span class="sxs-lookup"><span data-stu-id="78c02-250">Runs tests using a test runner.</span></span>                                     |

---

### <a name="project-references"></a><span data-ttu-id="78c02-251">项目引用</span><span class="sxs-lookup"><span data-stu-id="78c02-251">Project references</span></span>

<span data-ttu-id="78c02-252">命令</span><span class="sxs-lookup"><span data-stu-id="78c02-252">Command</span></span> | <span data-ttu-id="78c02-253">函数</span><span class="sxs-lookup"><span data-stu-id="78c02-253">Function</span></span>
--- | ---
[<span data-ttu-id="78c02-254">dotnet add reference</span><span class="sxs-lookup"><span data-stu-id="78c02-254">dotnet add reference</span></span>](dotnet-add-reference.md) | <span data-ttu-id="78c02-255">添加项目引用。</span><span class="sxs-lookup"><span data-stu-id="78c02-255">Adds a project reference.</span></span>
[<span data-ttu-id="78c02-256">dotnet list reference</span><span class="sxs-lookup"><span data-stu-id="78c02-256">dotnet list reference</span></span>](dotnet-list-reference.md) | <span data-ttu-id="78c02-257">列出项目引用。</span><span class="sxs-lookup"><span data-stu-id="78c02-257">Lists project references.</span></span>
[<span data-ttu-id="78c02-258">dotnet remove reference</span><span class="sxs-lookup"><span data-stu-id="78c02-258">dotnet remove reference</span></span>](dotnet-remove-reference.md) | <span data-ttu-id="78c02-259">删除项目引用。</span><span class="sxs-lookup"><span data-stu-id="78c02-259">Removes a project reference.</span></span>

### <a name="nuget-packages"></a><span data-ttu-id="78c02-260">NuGet 包</span><span class="sxs-lookup"><span data-stu-id="78c02-260">NuGet packages</span></span>

<span data-ttu-id="78c02-261">命令</span><span class="sxs-lookup"><span data-stu-id="78c02-261">Command</span></span> | <span data-ttu-id="78c02-262">函数</span><span class="sxs-lookup"><span data-stu-id="78c02-262">Function</span></span>
--- | ---
[<span data-ttu-id="78c02-263">dotnet add package</span><span class="sxs-lookup"><span data-stu-id="78c02-263">dotnet add package</span></span>](dotnet-add-package.md) | <span data-ttu-id="78c02-264">添加 NuGet 包。</span><span class="sxs-lookup"><span data-stu-id="78c02-264">Adds a NuGet package.</span></span>
[<span data-ttu-id="78c02-265">dotnet remove package</span><span class="sxs-lookup"><span data-stu-id="78c02-265">dotnet remove package</span></span>](dotnet-remove-package.md) | <span data-ttu-id="78c02-266">删除 NuGet 包。</span><span class="sxs-lookup"><span data-stu-id="78c02-266">Removes a NuGet package.</span></span>

### <a name="nuget-commands"></a><span data-ttu-id="78c02-267">NuGet 命令</span><span class="sxs-lookup"><span data-stu-id="78c02-267">NuGet commands</span></span>

<span data-ttu-id="78c02-268">命令</span><span class="sxs-lookup"><span data-stu-id="78c02-268">Command</span></span> | <span data-ttu-id="78c02-269">函数</span><span class="sxs-lookup"><span data-stu-id="78c02-269">Function</span></span>
--- | ---
[<span data-ttu-id="78c02-270">dotnet nuget delete</span><span class="sxs-lookup"><span data-stu-id="78c02-270">dotnet nuget delete</span></span>](dotnet-nuget-delete.md) | <span data-ttu-id="78c02-271">从服务器删除或取消列出包。</span><span class="sxs-lookup"><span data-stu-id="78c02-271">Deletes or unlists a package from the server.</span></span>
[<span data-ttu-id="78c02-272">dotnet nuget locals</span><span class="sxs-lookup"><span data-stu-id="78c02-272">dotnet nuget locals</span></span>](dotnet-nuget-locals.md) | <span data-ttu-id="78c02-273">清除或列出本地 NuGet 资源，例如 http 请求缓存、临时缓存或计算机范围的全局包文件夹。</span><span class="sxs-lookup"><span data-stu-id="78c02-273">Clears or lists local NuGet resources such as http-request cache, temporary cache, or machine-wide global packages folder.</span></span>
[<span data-ttu-id="78c02-274">dotnet nuget push</span><span class="sxs-lookup"><span data-stu-id="78c02-274">dotnet nuget push</span></span>](dotnet-nuget-push.md) | <span data-ttu-id="78c02-275">将包推送到服务器，并将其发布。</span><span class="sxs-lookup"><span data-stu-id="78c02-275">Pushes a package to the server and publishes it.</span></span>

### <a name="global-tools-commands"></a><span data-ttu-id="78c02-276">全局工具命令</span><span class="sxs-lookup"><span data-stu-id="78c02-276">Global Tools commands</span></span>

<span data-ttu-id="78c02-277">[.NET Core 全局工具](global-tools.md)可与 .NET Core SDK 2.1.300 一起开始使用：</span><span class="sxs-lookup"><span data-stu-id="78c02-277">[.NET Core Global Tools](global-tools.md) are available starting with .NET Core SDK 2.1.300:</span></span>

<span data-ttu-id="78c02-278">命令</span><span class="sxs-lookup"><span data-stu-id="78c02-278">Command</span></span> | <span data-ttu-id="78c02-279">函数</span><span class="sxs-lookup"><span data-stu-id="78c02-279">Function</span></span>
--- | ---
[<span data-ttu-id="78c02-280">dotnet tool install</span><span class="sxs-lookup"><span data-stu-id="78c02-280">dotnet tool install</span></span>](dotnet-tool-install.md) | <span data-ttu-id="78c02-281">在计算机上安装全局工具。</span><span class="sxs-lookup"><span data-stu-id="78c02-281">Installs a Global Tool on your machine.</span></span>
[<span data-ttu-id="78c02-282">dotnet tool list</span><span class="sxs-lookup"><span data-stu-id="78c02-282">dotnet tool list</span></span>](dotnet-tool-list.md) | <span data-ttu-id="78c02-283">列出当前安装在计算机上的默认目录中或指定路径中的所有全局工具。</span><span class="sxs-lookup"><span data-stu-id="78c02-283">Lists all Global Tools currently installed in the default directory on your machine or in the specified path.</span></span>
[<span data-ttu-id="78c02-284">dotnet tool uninstall</span><span class="sxs-lookup"><span data-stu-id="78c02-284">dotnet tool uninstall</span></span>](dotnet-tool-uninstall.md) | <span data-ttu-id="78c02-285">从计算机中卸载全局工具。</span><span class="sxs-lookup"><span data-stu-id="78c02-285">Uninstalls a Global Tool from your machine.</span></span>
[<span data-ttu-id="78c02-286">dotnet tool update</span><span class="sxs-lookup"><span data-stu-id="78c02-286">dotnet tool update</span></span>](dotnet-tool-update.md) | <span data-ttu-id="78c02-287">在计算机上更新全局工具。</span><span class="sxs-lookup"><span data-stu-id="78c02-287">Updates a Global Tool on your machine.</span></span>

### <a name="additional-tools"></a><span data-ttu-id="78c02-288">其他工具</span><span class="sxs-lookup"><span data-stu-id="78c02-288">Additional tools</span></span>

<span data-ttu-id="78c02-289">自 .NET Core SDK 2.1.300 开始，许多使用 `DotnetCliToolReference` 的仅在每个项目的基础上可用的工具现作为 .NET Core SDK 的一部分提供。</span><span class="sxs-lookup"><span data-stu-id="78c02-289">Starting with .NET Core SDK 2.1.300, a number of tools that were available only on a per project basis using `DotnetCliToolReference` are now available as part of the .NET Core SDK.</span></span> <span data-ttu-id="78c02-290">下表中列出了这些工具：</span><span class="sxs-lookup"><span data-stu-id="78c02-290">These tools are listed in the following table:</span></span>

| <span data-ttu-id="78c02-291">工具</span><span class="sxs-lookup"><span data-stu-id="78c02-291">Tool</span></span>                                              | <span data-ttu-id="78c02-292">函数</span><span class="sxs-lookup"><span data-stu-id="78c02-292">Function</span></span>                                                     |
| ------------------------------------------------- | ------------------------------------------------------------ |
| <span data-ttu-id="78c02-293">dev-certs</span><span class="sxs-lookup"><span data-stu-id="78c02-293">dev-certs</span></span>                                         | <span data-ttu-id="78c02-294">创建和管理开发证书。</span><span class="sxs-lookup"><span data-stu-id="78c02-294">Creates and manages development certificates.</span></span>                |
| [<span data-ttu-id="78c02-295">ef</span><span class="sxs-lookup"><span data-stu-id="78c02-295">ef</span></span>](/ef/core/miscellaneous/cli/dotnet)           | <span data-ttu-id="78c02-296">Entity Framework Core 命令行工具。</span><span class="sxs-lookup"><span data-stu-id="78c02-296">Entity Framework Core command-line tools.</span></span>                    |
| <span data-ttu-id="78c02-297">sql-cache</span><span class="sxs-lookup"><span data-stu-id="78c02-297">sql-cache</span></span>                                         | <span data-ttu-id="78c02-298">SQL Server 缓存命令行工具。</span><span class="sxs-lookup"><span data-stu-id="78c02-298">SQL Server cache command-line tools.</span></span>                         |
| [<span data-ttu-id="78c02-299">user-secrets</span><span class="sxs-lookup"><span data-stu-id="78c02-299">user-secrets</span></span>](/aspnet/core/security/app-secrets) | <span data-ttu-id="78c02-300">管理开发用户机密。</span><span class="sxs-lookup"><span data-stu-id="78c02-300">Manages development user secrets.</span></span>                            |
| [<span data-ttu-id="78c02-301">watch</span><span class="sxs-lookup"><span data-stu-id="78c02-301">watch</span></span>](/aspnet/core/tutorials/dotnet-watch)      | <span data-ttu-id="78c02-302">启动文件观察程序，以在更改文件时运行命令。</span><span class="sxs-lookup"><span data-stu-id="78c02-302">Starts a file watcher that runs a command when files change.</span></span> |

<span data-ttu-id="78c02-303">有关每个工具的详细信息，请键入 `dotnet <tool-name> --help`。</span><span class="sxs-lookup"><span data-stu-id="78c02-303">For more information about each tool, type `dotnet <tool-name> --help`.</span></span>

## <a name="examples"></a><span data-ttu-id="78c02-304">示例</span><span class="sxs-lookup"><span data-stu-id="78c02-304">Examples</span></span>

<span data-ttu-id="78c02-305">创建新的 .NET Core 控制台应用程序：</span><span class="sxs-lookup"><span data-stu-id="78c02-305">Creates a new .NET Core console application:</span></span>

`dotnet new console`

<span data-ttu-id="78c02-306">还原给定应用程序的依赖项：</span><span class="sxs-lookup"><span data-stu-id="78c02-306">Restore dependencies for a given application:</span></span>

`dotnet restore`

[!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]

<span data-ttu-id="78c02-307">生成给定目录中的项目及其依赖项：</span><span class="sxs-lookup"><span data-stu-id="78c02-307">Build a project and its dependencies in a given directory:</span></span>

`dotnet build`

<span data-ttu-id="78c02-308">运行应用程序 DLL，如 `myapp.dll`：</span><span class="sxs-lookup"><span data-stu-id="78c02-308">Run an application DLL, such as `myapp.dll`:</span></span>

`dotnet myapp.dll`

## <a name="environment-variables"></a><span data-ttu-id="78c02-309">环境变量</span><span class="sxs-lookup"><span data-stu-id="78c02-309">Environment variables</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="78c02-310">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="78c02-310">.NET Core 2.1</span></span>](#tab/netcore21)

`DOTNET_PACKAGES`

<span data-ttu-id="78c02-311">全局包文件夹。</span><span class="sxs-lookup"><span data-stu-id="78c02-311">The global packages folder.</span></span> <span data-ttu-id="78c02-312">如果未设置，则默认为 Unix 上的 `~/.nuget/packages` 或 Windows 上的 `%userprofile%\.nuget\packages`。</span><span class="sxs-lookup"><span data-stu-id="78c02-312">If not set, it defaults to `~/.nuget/packages` on Unix or `%userprofile%\.nuget\packages` on Windows.</span></span>

`DOTNET_SERVICING`

<span data-ttu-id="78c02-313">指定加载运行时期间共享主机要使用的服务索引的位置。</span><span class="sxs-lookup"><span data-stu-id="78c02-313">Specifies the location of the servicing index to use by the shared host when loading the runtime.</span></span>

`DOTNET_CLI_TELEMETRY_OPTOUT`

<span data-ttu-id="78c02-314">指定是否收集并向 Microsoft 发送 .NET Core 工具使用情况的相关数据。</span><span class="sxs-lookup"><span data-stu-id="78c02-314">Specifies whether data about the .NET Core tools usage is collected and sent to Microsoft.</span></span> <span data-ttu-id="78c02-315">设置为 `true` 以选择退出遥测功能（接受的值为 `true`、`1` 或 `yes`）。</span><span class="sxs-lookup"><span data-stu-id="78c02-315">Set to `true` to opt-out of the telemetry feature (values `true`, `1`, or `yes` accepted).</span></span> <span data-ttu-id="78c02-316">否则，设置为 `false` 以选择加入遥测功能（接受的值为 `false`、`0` 或 `no`）。</span><span class="sxs-lookup"><span data-stu-id="78c02-316">Otherwise, set to `false` to opt into the telemetry features (values `false`, `0`, or `no` accepted).</span></span> <span data-ttu-id="78c02-317">如果未设置，则默认为 `false` 且遥测功能为活动状态。</span><span class="sxs-lookup"><span data-stu-id="78c02-317">If not set, the default is `false` and the telemetry feature is active.</span></span>

`DOTNET_MULTILEVEL_LOOKUP`

<span data-ttu-id="78c02-318">指定是否从全局位置解析 .NET Core 运行时、共享框架或 SDK。</span><span class="sxs-lookup"><span data-stu-id="78c02-318">Specifies whether .NET Core runtime, shared framework, or SDK are resolved from the global location.</span></span> <span data-ttu-id="78c02-319">如果未设置，则默认为 `true`。</span><span class="sxs-lookup"><span data-stu-id="78c02-319">If not set, it defaults to `true`.</span></span> <span data-ttu-id="78c02-320">设置为 `false` 不从全局位置解析，并且具有独立的 .NET Core 安装（接受的值为 `0` 或 `false`）。</span><span class="sxs-lookup"><span data-stu-id="78c02-320">Set to `false` to not resolve from the global location and have isolated .NET Core installations (values `0` or `false` are accepted).</span></span> <span data-ttu-id="78c02-321">有关多级别查找的详细信息，请参阅 [Multi-level SharedFX Lookup](https://github.com/dotnet/core-setup/blob/master/Documentation/design-docs/multilevel-sharedfx-lookup.md)（多级别 SharedFX 查找）。</span><span class="sxs-lookup"><span data-stu-id="78c02-321">For more information about multi-level lookup, see [Multi-level SharedFX Lookup](https://github.com/dotnet/core-setup/blob/master/Documentation/design-docs/multilevel-sharedfx-lookup.md).</span></span>

`DOTNET_ROLL_FORWARD_ON_NO_CANDIDATE_FX`

<span data-ttu-id="78c02-322">如果设置为 `0`，则禁用次要版本前滚。</span><span class="sxs-lookup"><span data-stu-id="78c02-322">Disables minor version roll forward, if set to `0`.</span></span> <span data-ttu-id="78c02-323">有关详细信息，请参阅[前滚](../whats-new/dotnet-core-2-1.md#roll-forward)。</span><span class="sxs-lookup"><span data-stu-id="78c02-323">For more information, see [Roll forward](../whats-new/dotnet-core-2-1.md#roll-forward).</span></span>

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="78c02-324">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="78c02-324">.NET Core 2.0</span></span>](#tab/netcore20)

`DOTNET_PACKAGES`

<span data-ttu-id="78c02-325">主包缓存。</span><span class="sxs-lookup"><span data-stu-id="78c02-325">The primary package cache.</span></span> <span data-ttu-id="78c02-326">如果未设置，则默认为 Unix 上的 `$HOME/.nuget/packages` 或 Windows 上的 `%userprofile%\.nuget\packages`。</span><span class="sxs-lookup"><span data-stu-id="78c02-326">If not set, it defaults to `$HOME/.nuget/packages` on Unix or `%userprofile%\.nuget\packages` on Windows.</span></span>

`DOTNET_SERVICING`

<span data-ttu-id="78c02-327">指定加载运行时期间共享主机要使用的服务索引的位置。</span><span class="sxs-lookup"><span data-stu-id="78c02-327">Specifies the location of the servicing index to use by the shared host when loading the runtime.</span></span>

`DOTNET_CLI_TELEMETRY_OPTOUT`

<span data-ttu-id="78c02-328">指定是否收集并向 Microsoft 发送 .NET Core 工具使用情况的相关数据。</span><span class="sxs-lookup"><span data-stu-id="78c02-328">Specifies whether data about the .NET Core tools usage is collected and sent to Microsoft.</span></span> <span data-ttu-id="78c02-329">设置为 `true` 以选择退出遥测功能（接受的值为 `true`、`1` 或 `yes`）。</span><span class="sxs-lookup"><span data-stu-id="78c02-329">Set to `true` to opt-out of the telemetry feature (values `true`, `1`, or `yes` accepted).</span></span> <span data-ttu-id="78c02-330">否则，设置为 `false` 以选择加入遥测功能（接受的值为 `false`、`0` 或 `no`）。</span><span class="sxs-lookup"><span data-stu-id="78c02-330">Otherwise, set to `false` to opt into the telemetry features (values `false`, `0`, or `no` accepted).</span></span> <span data-ttu-id="78c02-331">如果未设置，则默认为 `false` 且遥测功能为活动状态。</span><span class="sxs-lookup"><span data-stu-id="78c02-331">If not set, the default is `false` and the telemetry feature is active.</span></span>

`DOTNET_MULTILEVEL_LOOKUP`

<span data-ttu-id="78c02-332">指定是否从全局位置解析 .NET Core 运行时、共享框架或 SDK。</span><span class="sxs-lookup"><span data-stu-id="78c02-332">Specifies whether .NET Core runtime, shared framework, or SDK are resolved from the global location.</span></span> <span data-ttu-id="78c02-333">如果未设置，则默认为 `true`。</span><span class="sxs-lookup"><span data-stu-id="78c02-333">If not set, it defaults to `true`.</span></span> <span data-ttu-id="78c02-334">设置为 `false` 不从全局位置解析，并且具有独立的 .NET Core 安装（接受的值为 `0` 或 `false`）。</span><span class="sxs-lookup"><span data-stu-id="78c02-334">Set to `false` to not resolve from the global location and have isolated .NET Core installations (values `0` or `false` are accepted).</span></span> <span data-ttu-id="78c02-335">有关多级别查找的详细信息，请参阅 [Multi-level SharedFX Lookup](https://github.com/dotnet/core-setup/blob/master/Documentation/design-docs/multilevel-sharedfx-lookup.md)（多级别 SharedFX 查找）。</span><span class="sxs-lookup"><span data-stu-id="78c02-335">For more information about multi-level lookup, see [Multi-level SharedFX Lookup](https://github.com/dotnet/core-setup/blob/master/Documentation/design-docs/multilevel-sharedfx-lookup.md).</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="78c02-336">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="78c02-336">.NET Core 1.x</span></span>](#tab/netcore1x)

`DOTNET_PACKAGES`

<span data-ttu-id="78c02-337">主包缓存。</span><span class="sxs-lookup"><span data-stu-id="78c02-337">The primary package cache.</span></span> <span data-ttu-id="78c02-338">如果未设置，则默认为 Unix 上的 `$HOME/.nuget/packages` 或 Windows 上的 `%userprofile%\.nuget\packages`。</span><span class="sxs-lookup"><span data-stu-id="78c02-338">If not set, it defaults to `$HOME/.nuget/packages` on Unix or `%userprofile%\.nuget\packages` on Windows.</span></span>

`DOTNET_SERVICING`

<span data-ttu-id="78c02-339">指定加载运行时期间共享主机要使用的服务索引的位置。</span><span class="sxs-lookup"><span data-stu-id="78c02-339">Specifies the location of the servicing index to use by the shared host when loading the runtime.</span></span>

`DOTNET_CLI_TELEMETRY_OPTOUT`

<span data-ttu-id="78c02-340">指定是否收集并向 Microsoft 发送 .NET Core 工具使用情况的相关数据。</span><span class="sxs-lookup"><span data-stu-id="78c02-340">Specifies whether data about the .NET Core tools usage is collected and sent to Microsoft.</span></span> <span data-ttu-id="78c02-341">设置为 `true` 以选择退出遥测功能（接受的值为 `true`、`1` 或 `yes`）。</span><span class="sxs-lookup"><span data-stu-id="78c02-341">Set to `true` to opt-out of the telemetry feature (values `true`, `1`, or `yes` accepted).</span></span> <span data-ttu-id="78c02-342">否则，设置为 `false` 以选择加入遥测功能（接受的值为 `false`、`0` 或 `no`）。</span><span class="sxs-lookup"><span data-stu-id="78c02-342">Otherwise, set to `false` to opt into the telemetry features (values `false`, `0`, or `no` accepted).</span></span> <span data-ttu-id="78c02-343">如果未设置，则默认为 `false` 且遥测功能为活动状态。</span><span class="sxs-lookup"><span data-stu-id="78c02-343">If not set, the default is `false` and the telemetry feature is active.</span></span>

---
