---
title: dotnet 命令 - .NET Core CLI
description: 了解 dotnet 命令（.NET Core CLI 工具的通用驱动程序）及其用法。
author: mairaw
ms.author: mairaw
ms.date: 06/04/2018
ms.openlocfilehash: 53e8f8bab1cbaabaa7926aa68197c18843b0b637
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/16/2018
ms.locfileid: "45615568"
---
# <a name="dotnet-command"></a><span data-ttu-id="df627-103">dotnet 命令</span><span class="sxs-lookup"><span data-stu-id="df627-103">dotnet command</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="df627-104">name</span><span class="sxs-lookup"><span data-stu-id="df627-104">Name</span></span>

<span data-ttu-id="df627-105">`dotnet` - 一款管理 .NET 源代码和二进制文件的工具。</span><span class="sxs-lookup"><span data-stu-id="df627-105">`dotnet` - A tool for managing .NET source code and binaries.</span></span>

## <a name="synopsis"></a><span data-ttu-id="df627-106">摘要</span><span class="sxs-lookup"><span data-stu-id="df627-106">Synopsis</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="df627-107">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="df627-107">.NET Core 2.1</span></span>](#tab/netcore21)
```
dotnet [command] [arguments] [--additional-deps] [--additionalprobingpath] [-d|--diagnostics] [--fx-version]
    [-h|--help] [--info] [--list-runtimes] [--list-sdks] [--roll-forward-on-no-candidate-fx] [-v|--verbosity] [--version]
```
# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="df627-108">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="df627-108">.NET Core 2.0</span></span>](#tab/netcore20)
```
dotnet [command] [arguments] [--additional-deps] [--additionalprobingpath] [-d|--diagnostics]
    [--fx-version] [-h|--help] [--info] [--roll-forward-on-no-candidate-fx] [-v|--verbosity] [--version]
```
# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="df627-109">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="df627-109">.NET Core 1.x</span></span>](#tab/netcore1x)
```
dotnet [command] [arguments] [--additionalprobingpath] [-d|--diagnostics] [--fx-version]
    [-h|--help] [--info] [-v|--verbosity] [--version]
```
---

## <a name="description"></a><span data-ttu-id="df627-110">描述</span><span class="sxs-lookup"><span data-stu-id="df627-110">Description</span></span>

<span data-ttu-id="df627-111">`dotnet` 是一款管理 .NET 源代码和二进制文件的工具。</span><span class="sxs-lookup"><span data-stu-id="df627-111">`dotnet` is a tool for managing .NET source code and binaries.</span></span> <span data-ttu-id="df627-112">它公开执行特定任务的命令，例如 [`dotnet build`](dotnet-build.md) 和 [`dotnet run`](dotnet-run.md)。</span><span class="sxs-lookup"><span data-stu-id="df627-112">It exposes commands that perform specific tasks, such as [`dotnet build`](dotnet-build.md) and [`dotnet run`](dotnet-run.md).</span></span> <span data-ttu-id="df627-113">每个命令都定义自己的参数。</span><span class="sxs-lookup"><span data-stu-id="df627-113">Each command defines its own arguments.</span></span> <span data-ttu-id="df627-114">在每个命令后键入 `--help` 以访问简要帮助文档。</span><span class="sxs-lookup"><span data-stu-id="df627-114">Type `--help` after each command to access brief help documentation.</span></span>

<span data-ttu-id="df627-115">可以使用 `dotnet` 来运行应用程序，方法是指定应用程序 DLL，如 `dotnet myapp.dll`.</span><span class="sxs-lookup"><span data-stu-id="df627-115">`dotnet` can be used to run applications, by specifying an application DLL, such as `dotnet myapp.dll`.</span></span> <span data-ttu-id="df627-116">要了解部署选项，请参阅 [.NET Core 应用程序部署](../deploying/index.md)。</span><span class="sxs-lookup"><span data-stu-id="df627-116">See [.NET Core application deployment](../deploying/index.md) for to learn about deployment options.</span></span>

## <a name="options"></a><span data-ttu-id="df627-117">选项</span><span class="sxs-lookup"><span data-stu-id="df627-117">Options</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="df627-118">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="df627-118">.NET Core 2.1</span></span>](#tab/netcore21)

`--additional-deps <PATH>`

<span data-ttu-id="df627-119">其他 deps.json 文件的路径。</span><span class="sxs-lookup"><span data-stu-id="df627-119">Path to additional *deps.json* file.</span></span>

`--additionalprobingpath <PATH>`

<span data-ttu-id="df627-120">包含要进行探测的探测策略和程序集的路径。</span><span class="sxs-lookup"><span data-stu-id="df627-120">Path containing probing policy and assemblies to probe.</span></span>

`-d|--diagnostics`

<span data-ttu-id="df627-121">启用诊断输出。</span><span class="sxs-lookup"><span data-stu-id="df627-121">Enables diagnostic output.</span></span>

`--fx-version <VERSION>`

<span data-ttu-id="df627-122">用于运行应用程序的 .NET Core 运行时版本。</span><span class="sxs-lookup"><span data-stu-id="df627-122">Version of the .NET Core runtime to use to run the application.</span></span>

`-h|--help`

<span data-ttu-id="df627-123">打印出给定命令的文档，如 `dotnet build --help`。</span><span class="sxs-lookup"><span data-stu-id="df627-123">Prints out documentation for a given command, such as `dotnet build --help`.</span></span> <span data-ttu-id="df627-124">`dotnet --help` 打印可用命令列表。</span><span class="sxs-lookup"><span data-stu-id="df627-124">`dotnet --help` prints a list of available commands.</span></span>

`--info`

<span data-ttu-id="df627-125">打印出有关 .NET Core 安装和计算机环境（如当前操作系统）的详细信息，并提交 .NET Core 版本的 SHA。</span><span class="sxs-lookup"><span data-stu-id="df627-125">Prints out detailed information about a .NET Core installation and the machine environment, such as the current operating system, and commit SHA of the .NET Core version.</span></span>

`--list-runtimes`

<span data-ttu-id="df627-126">显示已安装的 .NET Core 运行时。</span><span class="sxs-lookup"><span data-stu-id="df627-126">Displays the installed .NET Core runtimes.</span></span>

`--list-sdks`

<span data-ttu-id="df627-127">显示已安装的 .NET Core SDK。</span><span class="sxs-lookup"><span data-stu-id="df627-127">Displays the installed .NET Core SDKs.</span></span>

`--roll-forward-on-no-candidate-fx`

 <span data-ttu-id="df627-128">如果设置为 `0`，则禁用次要版本前滚。</span><span class="sxs-lookup"><span data-stu-id="df627-128">Disables minor version roll forward, if set to `0`.</span></span> <span data-ttu-id="df627-129">有关详细信息，请参阅[前滚](../whats-new/dotnet-core-2-1.md#roll-forward)。</span><span class="sxs-lookup"><span data-stu-id="df627-129">For more information, see [Roll forward](../whats-new/dotnet-core-2-1.md#roll-forward).</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="df627-130">设置命令的详细级别。</span><span class="sxs-lookup"><span data-stu-id="df627-130">Sets the verbosity level of the command.</span></span> <span data-ttu-id="df627-131">允许使用的值为 `q[uiet]`、`m[inimal]`、`n[ormal]`、`d[etailed]` 和 `diag[nostic]`。</span><span class="sxs-lookup"><span data-stu-id="df627-131">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="df627-132">并非在每个命令中均受支持；请参阅特定的命令页，确定此选项是否可用。</span><span class="sxs-lookup"><span data-stu-id="df627-132">Not supported in every command; see specific command page to determine if this option is available.</span></span>

`--version`

<span data-ttu-id="df627-133">打印使用中的 .NET Core SDK 版本。</span><span class="sxs-lookup"><span data-stu-id="df627-133">Prints out the version of the .NET Core SDK in use.</span></span>

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="df627-134">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="df627-134">.NET Core 2.0</span></span>](#tab/netcore20)

`--additional-deps <PATH>`

<span data-ttu-id="df627-135">其他 deps.json 文件的路径。</span><span class="sxs-lookup"><span data-stu-id="df627-135">Path to additional *deps.json* file.</span></span>

`--additionalprobingpath <PATH>`

<span data-ttu-id="df627-136">包含要进行探测的探测策略和程序集的路径。</span><span class="sxs-lookup"><span data-stu-id="df627-136">Path containing probing policy and assemblies to probe.</span></span>

`-d|--diagnostics`

<span data-ttu-id="df627-137">启用诊断输出。</span><span class="sxs-lookup"><span data-stu-id="df627-137">Enables diagnostic output.</span></span>

`--fx-version <VERSION>`

<span data-ttu-id="df627-138">用于运行应用程序的 .NET Core 运行时版本。</span><span class="sxs-lookup"><span data-stu-id="df627-138">Version of the .NET Core runtime to use to run the application.</span></span>

`-h|--help`

<span data-ttu-id="df627-139">打印出给定命令的文档，如 `dotnet build --help`。</span><span class="sxs-lookup"><span data-stu-id="df627-139">Prints out documentation for a given command, such as `dotnet build --help`.</span></span> <span data-ttu-id="df627-140">`dotnet --help` 打印可用命令列表。</span><span class="sxs-lookup"><span data-stu-id="df627-140">`dotnet --help` prints a list of available commands.</span></span>

`--info`

<span data-ttu-id="df627-141">打印出有关 .NET Core 安装和计算机环境（如当前操作系统）的详细信息，并提交 .NET Core 版本的 SHA。</span><span class="sxs-lookup"><span data-stu-id="df627-141">Prints out detailed information about a .NET Core installation and the machine environment, such as the current operating system, and commit SHA of the .NET Core version.</span></span>

`--roll-forward-on-no-candidate-fx`

 <span data-ttu-id="df627-142">如果设置为 `0`，则禁用次要版本前滚。</span><span class="sxs-lookup"><span data-stu-id="df627-142">Disables minor version roll forward, if set to `0`.</span></span> <span data-ttu-id="df627-143">有关详细信息，请参阅[前滚](../whats-new/dotnet-core-2-1.md#roll-forward)。</span><span class="sxs-lookup"><span data-stu-id="df627-143">For more information, see [Roll forward](../whats-new/dotnet-core-2-1.md#roll-forward).</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="df627-144">设置命令的详细级别。</span><span class="sxs-lookup"><span data-stu-id="df627-144">Sets the verbosity level of the command.</span></span> <span data-ttu-id="df627-145">允许使用的值为 `q[uiet]`、`m[inimal]`、`n[ormal]`、`d[etailed]` 和 `diag[nostic]`。</span><span class="sxs-lookup"><span data-stu-id="df627-145">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="df627-146">并非在每个命令中均受支持；请参阅特定的命令页，确定此选项是否可用。</span><span class="sxs-lookup"><span data-stu-id="df627-146">Not supported in every command; see specific command page to determine if this option is available.</span></span>

`--version`

<span data-ttu-id="df627-147">打印使用中的 .NET Core SDK 版本。</span><span class="sxs-lookup"><span data-stu-id="df627-147">Prints out the version of the .NET Core SDK in use.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="df627-148">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="df627-148">.NET Core 1.x</span></span>](#tab/netcore1x)

`--additionalprobingpath <PATH>`

<span data-ttu-id="df627-149">包含要进行探测的探测策略和程序集的路径。</span><span class="sxs-lookup"><span data-stu-id="df627-149">Path containing probing policy and assemblies to probe.</span></span>

`-d|--diagnostics`

<span data-ttu-id="df627-150">启用诊断输出。</span><span class="sxs-lookup"><span data-stu-id="df627-150">Enables diagnostic output.</span></span>

`--fx-version <VERSION>`

<span data-ttu-id="df627-151">用于运行应用程序的 .NET Core 运行时版本。</span><span class="sxs-lookup"><span data-stu-id="df627-151">Version of the .NET Core runtime to use to run the application.</span></span>

`-h|--help`

<span data-ttu-id="df627-152">打印出给定命令的文档，如 `dotnet build --help`。</span><span class="sxs-lookup"><span data-stu-id="df627-152">Prints out documentation for a given command, such as `dotnet build --help`.</span></span> <span data-ttu-id="df627-153">`dotnet --help` 打印可用命令列表。</span><span class="sxs-lookup"><span data-stu-id="df627-153">`dotnet --help` prints a list of available commands.</span></span>

`--info`

<span data-ttu-id="df627-154">打印出有关 .NET Core 安装和计算机环境（如当前操作系统）的详细信息，并提交 .NET Core 版本的 SHA。</span><span class="sxs-lookup"><span data-stu-id="df627-154">Prints out detailed information about a .NET Core installation and the machine environment, such as the current operating system, and commit SHA of the .NET Core version.</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="df627-155">设置命令的详细级别。</span><span class="sxs-lookup"><span data-stu-id="df627-155">Sets the verbosity level of the command.</span></span> <span data-ttu-id="df627-156">允许使用的值为 `q[uiet]`、`m[inimal]`、`n[ormal]`、`d[etailed]` 和 `diag[nostic]`。</span><span class="sxs-lookup"><span data-stu-id="df627-156">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="df627-157">并非在每个命令中均受支持；请参阅特定的命令页，确定此选项是否可用。</span><span class="sxs-lookup"><span data-stu-id="df627-157">Not supported in every command; see specific command page to determine if this option is available.</span></span>

`--version`

<span data-ttu-id="df627-158">打印使用中的 .NET Core SDK 版本。</span><span class="sxs-lookup"><span data-stu-id="df627-158">Prints out the version of the .NET Core SDK in use.</span></span>

---

## <a name="dotnet-commands"></a><span data-ttu-id="df627-159">dotnet 命令</span><span class="sxs-lookup"><span data-stu-id="df627-159">dotnet commands</span></span>

### <a name="general"></a><span data-ttu-id="df627-160">常规</span><span class="sxs-lookup"><span data-stu-id="df627-160">General</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="df627-161">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="df627-161">.NET Core 2.1</span></span>](#tab/netcore21)

| <span data-ttu-id="df627-162">命令</span><span class="sxs-lookup"><span data-stu-id="df627-162">Command</span></span>                                       | <span data-ttu-id="df627-163">函数</span><span class="sxs-lookup"><span data-stu-id="df627-163">Function</span></span>                                                            |
| --------------------------------------------- | ------------------------------------------------------------------- |
| [<span data-ttu-id="df627-164">dotnet build</span><span class="sxs-lookup"><span data-stu-id="df627-164">dotnet build</span></span>](dotnet-build.md)               | <span data-ttu-id="df627-165">生成 .NET Core 应用程序。</span><span class="sxs-lookup"><span data-stu-id="df627-165">Builds a .NET Core application.</span></span>                                     |
| [<span data-ttu-id="df627-166">dotnet build-server</span><span class="sxs-lookup"><span data-stu-id="df627-166">dotnet build-server</span></span>](dotnet-build-server.md) | <span data-ttu-id="df627-167">与通过生成启动的服务器进行交互。</span><span class="sxs-lookup"><span data-stu-id="df627-167">Interacts with servers started by a build.</span></span>                          |
| [<span data-ttu-id="df627-168">dotnet clean</span><span class="sxs-lookup"><span data-stu-id="df627-168">dotnet clean</span></span>](dotnet-clean.md)               | <span data-ttu-id="df627-169">清除生成输出。</span><span class="sxs-lookup"><span data-stu-id="df627-169">Clean build outputs.</span></span>                                                |
| [<span data-ttu-id="df627-170">dotnet help</span><span class="sxs-lookup"><span data-stu-id="df627-170">dotnet help</span></span>](dotnet-help.md)                 | <span data-ttu-id="df627-171">显示命令更详细的在线文档。</span><span class="sxs-lookup"><span data-stu-id="df627-171">Shows more detailed documentation online for the command.</span></span>           |
| [<span data-ttu-id="df627-172">dotnet migrate</span><span class="sxs-lookup"><span data-stu-id="df627-172">dotnet migrate</span></span>](dotnet-migrate.md)           | <span data-ttu-id="df627-173">将有效的预览版 2 项目迁移到 .NET Core SDK 1.0 项目。</span><span class="sxs-lookup"><span data-stu-id="df627-173">Migrates a valid Preview 2 project to a .NET Core SDK 1.0 project.</span></span>  |
| [<span data-ttu-id="df627-174">dotnet msbuild</span><span class="sxs-lookup"><span data-stu-id="df627-174">dotnet msbuild</span></span>](dotnet-msbuild.md)           | <span data-ttu-id="df627-175">提供对 MSBuild 命令行的访问权限。</span><span class="sxs-lookup"><span data-stu-id="df627-175">Provides access to the MSBuild command line.</span></span>                        |
| [<span data-ttu-id="df627-176">dotnet new</span><span class="sxs-lookup"><span data-stu-id="df627-176">dotnet new</span></span>](dotnet-new.md)                   | <span data-ttu-id="df627-177">为给定的模板初始化 C# 或 F# 项目。</span><span class="sxs-lookup"><span data-stu-id="df627-177">Initializes a C# or F# project for a given template.</span></span>                |
| [<span data-ttu-id="df627-178">dotnet pack</span><span class="sxs-lookup"><span data-stu-id="df627-178">dotnet pack</span></span>](dotnet-pack.md)                 | <span data-ttu-id="df627-179">创建代码的 NuGet 包。</span><span class="sxs-lookup"><span data-stu-id="df627-179">Creates a NuGet package of your code.</span></span>                               |
| [<span data-ttu-id="df627-180">dotnet publish</span><span class="sxs-lookup"><span data-stu-id="df627-180">dotnet publish</span></span>](dotnet-publish.md)           | <span data-ttu-id="df627-181">发布 .NET 依赖于框架或独立应用程序。</span><span class="sxs-lookup"><span data-stu-id="df627-181">Publishes a .NET framework-dependent or self-contained application.</span></span> |
| [<span data-ttu-id="df627-182">dotnet restore</span><span class="sxs-lookup"><span data-stu-id="df627-182">dotnet restore</span></span>](dotnet-restore.md)           | <span data-ttu-id="df627-183">还原给定应用程序的依赖项。</span><span class="sxs-lookup"><span data-stu-id="df627-183">Restores the dependencies for a given application.</span></span>                  |
| [<span data-ttu-id="df627-184">dotnet run</span><span class="sxs-lookup"><span data-stu-id="df627-184">dotnet run</span></span>](dotnet-run.md)                   | <span data-ttu-id="df627-185">从源运行应用程序。</span><span class="sxs-lookup"><span data-stu-id="df627-185">Runs the application from source.</span></span>                                   |
| [<span data-ttu-id="df627-186">dotnet sln</span><span class="sxs-lookup"><span data-stu-id="df627-186">dotnet sln</span></span>](dotnet-sln.md)                   | <span data-ttu-id="df627-187">用于添加、删除和列出解决方案文件中项目的选项。</span><span class="sxs-lookup"><span data-stu-id="df627-187">Options to add, remove, and list projects in a solution file.</span></span>       |
| [<span data-ttu-id="df627-188">dotnet store</span><span class="sxs-lookup"><span data-stu-id="df627-188">dotnet store</span></span>](dotnet-store.md)               | <span data-ttu-id="df627-189">将程序集存储到运行时包存储区。</span><span class="sxs-lookup"><span data-stu-id="df627-189">Stores assemblies in the runtime package store.</span></span>                     |
| [<span data-ttu-id="df627-190">dotnet test</span><span class="sxs-lookup"><span data-stu-id="df627-190">dotnet test</span></span>](dotnet-test.md)                 | <span data-ttu-id="df627-191">使用测试运行程序运行测试。</span><span class="sxs-lookup"><span data-stu-id="df627-191">Runs tests using a test runner.</span></span>                                     |

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="df627-192">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="df627-192">.NET Core 2.0</span></span>](#tab/netcore20)

| <span data-ttu-id="df627-193">命令</span><span class="sxs-lookup"><span data-stu-id="df627-193">Command</span></span>                             | <span data-ttu-id="df627-194">函数</span><span class="sxs-lookup"><span data-stu-id="df627-194">Function</span></span>                                                            |
| ----------------------------------- | ------------------------------------------------------------------- |
| [<span data-ttu-id="df627-195">dotnet build</span><span class="sxs-lookup"><span data-stu-id="df627-195">dotnet build</span></span>](dotnet-build.md)     | <span data-ttu-id="df627-196">生成 .NET Core 应用程序。</span><span class="sxs-lookup"><span data-stu-id="df627-196">Builds a .NET Core application.</span></span>                                     |
| [<span data-ttu-id="df627-197">dotnet clean</span><span class="sxs-lookup"><span data-stu-id="df627-197">dotnet clean</span></span>](dotnet-clean.md)     | <span data-ttu-id="df627-198">清除生成输出。</span><span class="sxs-lookup"><span data-stu-id="df627-198">Clean build outputs.</span></span>                                              |
| [<span data-ttu-id="df627-199">dotnet help</span><span class="sxs-lookup"><span data-stu-id="df627-199">dotnet help</span></span>](dotnet-help.md)       | <span data-ttu-id="df627-200">显示命令更详细的在线文档。</span><span class="sxs-lookup"><span data-stu-id="df627-200">Shows more detailed documentation online for the command.</span></span>           |
| [<span data-ttu-id="df627-201">dotnet migrate</span><span class="sxs-lookup"><span data-stu-id="df627-201">dotnet migrate</span></span>](dotnet-migrate.md) | <span data-ttu-id="df627-202">将有效的预览版 2 项目迁移到 .NET Core SDK 1.0 项目。</span><span class="sxs-lookup"><span data-stu-id="df627-202">Migrates a valid Preview 2 project to a .NET Core SDK 1.0 project.</span></span>  |
| [<span data-ttu-id="df627-203">dotnet msbuild</span><span class="sxs-lookup"><span data-stu-id="df627-203">dotnet msbuild</span></span>](dotnet-msbuild.md) | <span data-ttu-id="df627-204">提供对 MSBuild 命令行的访问权限。</span><span class="sxs-lookup"><span data-stu-id="df627-204">Provides access to the MSBuild command line.</span></span>                        |
| [<span data-ttu-id="df627-205">dotnet new</span><span class="sxs-lookup"><span data-stu-id="df627-205">dotnet new</span></span>](dotnet-new.md)         | <span data-ttu-id="df627-206">为给定的模板初始化 C# 或 F# 项目。</span><span class="sxs-lookup"><span data-stu-id="df627-206">Initializes a C# or F# project for a given template.</span></span>                |
| [<span data-ttu-id="df627-207">dotnet pack</span><span class="sxs-lookup"><span data-stu-id="df627-207">dotnet pack</span></span>](dotnet-pack.md)       | <span data-ttu-id="df627-208">创建代码的 NuGet 包。</span><span class="sxs-lookup"><span data-stu-id="df627-208">Creates a NuGet package of your code.</span></span>                               |
| [<span data-ttu-id="df627-209">dotnet publish</span><span class="sxs-lookup"><span data-stu-id="df627-209">dotnet publish</span></span>](dotnet-publish.md) | <span data-ttu-id="df627-210">发布 .NET 依赖于框架或独立应用程序。</span><span class="sxs-lookup"><span data-stu-id="df627-210">Publishes a .NET framework-dependent or self-contained application.</span></span> |
| [<span data-ttu-id="df627-211">dotnet restore</span><span class="sxs-lookup"><span data-stu-id="df627-211">dotnet restore</span></span>](dotnet-restore.md) | <span data-ttu-id="df627-212">还原给定应用程序的依赖项。</span><span class="sxs-lookup"><span data-stu-id="df627-212">Restores the dependencies for a given application.</span></span>                  |
| [<span data-ttu-id="df627-213">dotnet run</span><span class="sxs-lookup"><span data-stu-id="df627-213">dotnet run</span></span>](dotnet-run.md)         | <span data-ttu-id="df627-214">从源运行应用程序。</span><span class="sxs-lookup"><span data-stu-id="df627-214">Runs the application from source.</span></span>                                   |
| [<span data-ttu-id="df627-215">dotnet sln</span><span class="sxs-lookup"><span data-stu-id="df627-215">dotnet sln</span></span>](dotnet-sln.md)         | <span data-ttu-id="df627-216">用于添加、删除和列出解决方案文件中项目的选项。</span><span class="sxs-lookup"><span data-stu-id="df627-216">Options to add, remove, and list projects in a solution file.</span></span>       |
| [<span data-ttu-id="df627-217">dotnet store</span><span class="sxs-lookup"><span data-stu-id="df627-217">dotnet store</span></span>](dotnet-store.md)     | <span data-ttu-id="df627-218">将程序集存储到运行时包存储区。</span><span class="sxs-lookup"><span data-stu-id="df627-218">Stores assemblies in the runtime package store.</span></span>                     |
| [<span data-ttu-id="df627-219">dotnet test</span><span class="sxs-lookup"><span data-stu-id="df627-219">dotnet test</span></span>](dotnet-test.md)       | <span data-ttu-id="df627-220">使用测试运行程序运行测试。</span><span class="sxs-lookup"><span data-stu-id="df627-220">Runs tests using a test runner.</span></span>                                     |

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="df627-221">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="df627-221">.NET Core 1.x</span></span>](#tab/netcore1x)

| <span data-ttu-id="df627-222">命令</span><span class="sxs-lookup"><span data-stu-id="df627-222">Command</span></span>                             | <span data-ttu-id="df627-223">函数</span><span class="sxs-lookup"><span data-stu-id="df627-223">Function</span></span>                                                            |
| ----------------------------------- | ------------------------------------------------------------------- |
| [<span data-ttu-id="df627-224">dotnet build</span><span class="sxs-lookup"><span data-stu-id="df627-224">dotnet build</span></span>](dotnet-build.md)     | <span data-ttu-id="df627-225">生成 .NET Core 应用程序。</span><span class="sxs-lookup"><span data-stu-id="df627-225">Builds a .NET Core application.</span></span>                                     |
| [<span data-ttu-id="df627-226">dotnet clean</span><span class="sxs-lookup"><span data-stu-id="df627-226">dotnet clean</span></span>](dotnet-clean.md)     | <span data-ttu-id="df627-227">清除生成输出。</span><span class="sxs-lookup"><span data-stu-id="df627-227">Clean build outputs.</span></span>                                              |
| [<span data-ttu-id="df627-228">dotnet migrate</span><span class="sxs-lookup"><span data-stu-id="df627-228">dotnet migrate</span></span>](dotnet-migrate.md) | <span data-ttu-id="df627-229">将有效的预览版 2 项目迁移到 .NET Core SDK 1.0 项目。</span><span class="sxs-lookup"><span data-stu-id="df627-229">Migrates a valid Preview 2 project to a .NET Core SDK 1.0 project.</span></span>  |
| [<span data-ttu-id="df627-230">dotnet msbuild</span><span class="sxs-lookup"><span data-stu-id="df627-230">dotnet msbuild</span></span>](dotnet-msbuild.md) | <span data-ttu-id="df627-231">提供对 MSBuild 命令行的访问权限。</span><span class="sxs-lookup"><span data-stu-id="df627-231">Provides access to the MSBuild command line.</span></span>                        |
| [<span data-ttu-id="df627-232">dotnet new</span><span class="sxs-lookup"><span data-stu-id="df627-232">dotnet new</span></span>](dotnet-new.md)         | <span data-ttu-id="df627-233">为给定的模板初始化 C# 或 F# 项目。</span><span class="sxs-lookup"><span data-stu-id="df627-233">Initializes a C# or F# project for a given template.</span></span>                |
| [<span data-ttu-id="df627-234">dotnet pack</span><span class="sxs-lookup"><span data-stu-id="df627-234">dotnet pack</span></span>](dotnet-pack.md)       | <span data-ttu-id="df627-235">创建代码的 NuGet 包。</span><span class="sxs-lookup"><span data-stu-id="df627-235">Creates a NuGet package of your code.</span></span>                               |
| [<span data-ttu-id="df627-236">dotnet publish</span><span class="sxs-lookup"><span data-stu-id="df627-236">dotnet publish</span></span>](dotnet-publish.md) | <span data-ttu-id="df627-237">发布 .NET 依赖于框架或独立应用程序。</span><span class="sxs-lookup"><span data-stu-id="df627-237">Publishes a .NET framework-dependent or self-contained application.</span></span> |
| [<span data-ttu-id="df627-238">dotnet restore</span><span class="sxs-lookup"><span data-stu-id="df627-238">dotnet restore</span></span>](dotnet-restore.md) | <span data-ttu-id="df627-239">还原给定应用程序的依赖项。</span><span class="sxs-lookup"><span data-stu-id="df627-239">Restores the dependencies for a given application.</span></span>                  |
| [<span data-ttu-id="df627-240">dotnet run</span><span class="sxs-lookup"><span data-stu-id="df627-240">dotnet run</span></span>](dotnet-run.md)         | <span data-ttu-id="df627-241">从源运行应用程序。</span><span class="sxs-lookup"><span data-stu-id="df627-241">Runs the application from source.</span></span>                                   |
| [<span data-ttu-id="df627-242">dotnet sln</span><span class="sxs-lookup"><span data-stu-id="df627-242">dotnet sln</span></span>](dotnet-sln.md)         | <span data-ttu-id="df627-243">用于添加、删除和列出解决方案文件中项目的选项。</span><span class="sxs-lookup"><span data-stu-id="df627-243">Options to add, remove, and list projects in a solution file.</span></span>       |
| [<span data-ttu-id="df627-244">dotnet test</span><span class="sxs-lookup"><span data-stu-id="df627-244">dotnet test</span></span>](dotnet-test.md)       | <span data-ttu-id="df627-245">使用测试运行程序运行测试。</span><span class="sxs-lookup"><span data-stu-id="df627-245">Runs tests using a test runner.</span></span>                                     |

---

### <a name="project-references"></a><span data-ttu-id="df627-246">项目引用</span><span class="sxs-lookup"><span data-stu-id="df627-246">Project references</span></span>

<span data-ttu-id="df627-247">命令</span><span class="sxs-lookup"><span data-stu-id="df627-247">Command</span></span> | <span data-ttu-id="df627-248">函数</span><span class="sxs-lookup"><span data-stu-id="df627-248">Function</span></span>
--- | ---
[<span data-ttu-id="df627-249">dotnet add reference</span><span class="sxs-lookup"><span data-stu-id="df627-249">dotnet add reference</span></span>](dotnet-add-reference.md) | <span data-ttu-id="df627-250">添加项目引用。</span><span class="sxs-lookup"><span data-stu-id="df627-250">Adds a project reference.</span></span>
[<span data-ttu-id="df627-251">dotnet list reference</span><span class="sxs-lookup"><span data-stu-id="df627-251">dotnet list reference</span></span>](dotnet-list-reference.md) | <span data-ttu-id="df627-252">列出项目引用。</span><span class="sxs-lookup"><span data-stu-id="df627-252">Lists project references.</span></span>
[<span data-ttu-id="df627-253">dotnet remove reference</span><span class="sxs-lookup"><span data-stu-id="df627-253">dotnet remove reference</span></span>](dotnet-remove-reference.md) | <span data-ttu-id="df627-254">删除项目引用。</span><span class="sxs-lookup"><span data-stu-id="df627-254">Removes a project reference.</span></span>

### <a name="nuget-packages"></a><span data-ttu-id="df627-255">NuGet 包</span><span class="sxs-lookup"><span data-stu-id="df627-255">NuGet packages</span></span>

<span data-ttu-id="df627-256">命令</span><span class="sxs-lookup"><span data-stu-id="df627-256">Command</span></span> | <span data-ttu-id="df627-257">函数</span><span class="sxs-lookup"><span data-stu-id="df627-257">Function</span></span>
--- | ---
[<span data-ttu-id="df627-258">dotnet add package</span><span class="sxs-lookup"><span data-stu-id="df627-258">dotnet add package</span></span>](dotnet-add-package.md) | <span data-ttu-id="df627-259">添加 NuGet 包。</span><span class="sxs-lookup"><span data-stu-id="df627-259">Adds a NuGet package.</span></span>
[<span data-ttu-id="df627-260">dotnet remove package</span><span class="sxs-lookup"><span data-stu-id="df627-260">dotnet remove package</span></span>](dotnet-remove-package.md) | <span data-ttu-id="df627-261">删除 NuGet 包。</span><span class="sxs-lookup"><span data-stu-id="df627-261">Removes a NuGet package.</span></span>

### <a name="nuget-commands"></a><span data-ttu-id="df627-262">NuGet 命令</span><span class="sxs-lookup"><span data-stu-id="df627-262">NuGet commands</span></span>

<span data-ttu-id="df627-263">命令</span><span class="sxs-lookup"><span data-stu-id="df627-263">Command</span></span> | <span data-ttu-id="df627-264">函数</span><span class="sxs-lookup"><span data-stu-id="df627-264">Function</span></span>
--- | ---
[<span data-ttu-id="df627-265">dotnet nuget delete</span><span class="sxs-lookup"><span data-stu-id="df627-265">dotnet nuget delete</span></span>](dotnet-nuget-delete.md) | <span data-ttu-id="df627-266">从服务器删除或取消列出包。</span><span class="sxs-lookup"><span data-stu-id="df627-266">Deletes or unlists a package from the server.</span></span>
[<span data-ttu-id="df627-267">dotnet nuget locals</span><span class="sxs-lookup"><span data-stu-id="df627-267">dotnet nuget locals</span></span>](dotnet-nuget-locals.md) | <span data-ttu-id="df627-268">清除或列出本地 NuGet 资源，例如 http 请求缓存、临时缓存或计算机范围的全局包文件夹。</span><span class="sxs-lookup"><span data-stu-id="df627-268">Clears or lists local NuGet resources such as http-request cache, temporary cache, or machine-wide global packages folder.</span></span>
[<span data-ttu-id="df627-269">dotnet nuget push</span><span class="sxs-lookup"><span data-stu-id="df627-269">dotnet nuget push</span></span>](dotnet-nuget-push.md) | <span data-ttu-id="df627-270">将包推送到服务器，并将其发布。</span><span class="sxs-lookup"><span data-stu-id="df627-270">Pushes a package to the server and publishes it.</span></span>

### <a name="global-tools-commands"></a><span data-ttu-id="df627-271">全局工具命令</span><span class="sxs-lookup"><span data-stu-id="df627-271">Global Tools commands</span></span>

<span data-ttu-id="df627-272">[.NET Core 全局工具](global-tools.md)可与 .NET Core SDK 2.1.300 一起开始使用：</span><span class="sxs-lookup"><span data-stu-id="df627-272">[.NET Core Global Tools](global-tools.md) are available starting with .NET Core SDK 2.1.300:</span></span>

<span data-ttu-id="df627-273">命令</span><span class="sxs-lookup"><span data-stu-id="df627-273">Command</span></span> | <span data-ttu-id="df627-274">函数</span><span class="sxs-lookup"><span data-stu-id="df627-274">Function</span></span>
--- | ---
[<span data-ttu-id="df627-275">dotnet tool install</span><span class="sxs-lookup"><span data-stu-id="df627-275">dotnet tool install</span></span>](dotnet-tool-install.md) | <span data-ttu-id="df627-276">在计算机上安装全局工具。</span><span class="sxs-lookup"><span data-stu-id="df627-276">Installs a Global Tool on your machine.</span></span>
[<span data-ttu-id="df627-277">dotnet tool list</span><span class="sxs-lookup"><span data-stu-id="df627-277">dotnet tool list</span></span>](dotnet-tool-list.md) | <span data-ttu-id="df627-278">列出当前安装在计算机上的默认目录中或指定路径中的所有全局工具。</span><span class="sxs-lookup"><span data-stu-id="df627-278">Lists all Global Tools currently installed in the default directory on your machine or in the specified path.</span></span>
[<span data-ttu-id="df627-279">dotnet tool uninstall</span><span class="sxs-lookup"><span data-stu-id="df627-279">dotnet tool uninstall</span></span>](dotnet-tool-uninstall.md) | <span data-ttu-id="df627-280">从计算机中卸载全局工具。</span><span class="sxs-lookup"><span data-stu-id="df627-280">Uninstalls a Global Tool from your machine.</span></span>
[<span data-ttu-id="df627-281">dotnet tool update</span><span class="sxs-lookup"><span data-stu-id="df627-281">dotnet tool update</span></span>](dotnet-tool-update.md) | <span data-ttu-id="df627-282">在计算机上更新全局工具。</span><span class="sxs-lookup"><span data-stu-id="df627-282">Updates a Global Tool on your machine.</span></span>

### <a name="additional-tools"></a><span data-ttu-id="df627-283">其他工具</span><span class="sxs-lookup"><span data-stu-id="df627-283">Additional tools</span></span>

<span data-ttu-id="df627-284">自 .NET Core SDK 2.1.300 开始，许多使用 `DotnetCliToolReference` 的仅在每个项目的基础上可用的工具现作为 .NET Core SDK 的一部分提供。</span><span class="sxs-lookup"><span data-stu-id="df627-284">Starting with .NET Core SDK 2.1.300, a number of tools that were available only on a per project basis using `DotnetCliToolReference` are now available as part of the .NET Core SDK.</span></span> <span data-ttu-id="df627-285">下表中列出了这些工具：</span><span class="sxs-lookup"><span data-stu-id="df627-285">These tools are listed in the following table:</span></span>

| <span data-ttu-id="df627-286">工具</span><span class="sxs-lookup"><span data-stu-id="df627-286">Tool</span></span>                                              | <span data-ttu-id="df627-287">函数</span><span class="sxs-lookup"><span data-stu-id="df627-287">Function</span></span>                                                     |
| ------------------------------------------------- | ------------------------------------------------------------ |
| <span data-ttu-id="df627-288">dev-certs</span><span class="sxs-lookup"><span data-stu-id="df627-288">dev-certs</span></span>                                         | <span data-ttu-id="df627-289">创建和管理开发证书。</span><span class="sxs-lookup"><span data-stu-id="df627-289">Creates and manages development certificates.</span></span>                |
| [<span data-ttu-id="df627-290">ef</span><span class="sxs-lookup"><span data-stu-id="df627-290">ef</span></span>](/ef/core/miscellaneous/cli/dotnet)           | <span data-ttu-id="df627-291">Entity Framework Core 命令行工具。</span><span class="sxs-lookup"><span data-stu-id="df627-291">Entity Framework Core command-line tools.</span></span>                    |
| <span data-ttu-id="df627-292">sql-cache</span><span class="sxs-lookup"><span data-stu-id="df627-292">sql-cache</span></span>                                         | <span data-ttu-id="df627-293">SQL Server 缓存命令行工具。</span><span class="sxs-lookup"><span data-stu-id="df627-293">SQL Server cache command-line tools.</span></span>                         |
| [<span data-ttu-id="df627-294">user-secrets</span><span class="sxs-lookup"><span data-stu-id="df627-294">user-secrets</span></span>](/aspnet/core/security/app-secrets) | <span data-ttu-id="df627-295">管理开发用户机密。</span><span class="sxs-lookup"><span data-stu-id="df627-295">Manages development user secrets.</span></span>                            |
| [<span data-ttu-id="df627-296">watch</span><span class="sxs-lookup"><span data-stu-id="df627-296">watch</span></span>](/aspnet/core/tutorials/dotnet-watch)      | <span data-ttu-id="df627-297">启动文件观察程序，以在更改文件时运行命令。</span><span class="sxs-lookup"><span data-stu-id="df627-297">Starts a file watcher that runs a command when files change.</span></span> |

<span data-ttu-id="df627-298">有关每个工具的详细信息，请键入 `dotnet <tool-name> --help`。</span><span class="sxs-lookup"><span data-stu-id="df627-298">For more information about each tool, type `dotnet <tool-name> --help`.</span></span>

## <a name="examples"></a><span data-ttu-id="df627-299">示例</span><span class="sxs-lookup"><span data-stu-id="df627-299">Examples</span></span>

<span data-ttu-id="df627-300">创建新的 .NET Core 控制台应用程序：</span><span class="sxs-lookup"><span data-stu-id="df627-300">Creates a new .NET Core console application:</span></span>

`dotnet new console`

<span data-ttu-id="df627-301">还原给定应用程序的依赖项：</span><span class="sxs-lookup"><span data-stu-id="df627-301">Restore dependencies for a given application:</span></span>

`dotnet restore`

[!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]

<span data-ttu-id="df627-302">生成给定目录中的项目及其依赖项：</span><span class="sxs-lookup"><span data-stu-id="df627-302">Build a project and its dependencies in a given directory:</span></span>

`dotnet build`

<span data-ttu-id="df627-303">运行应用程序 DLL，如 `myapp.dll`：</span><span class="sxs-lookup"><span data-stu-id="df627-303">Run an application DLL, such as `myapp.dll`:</span></span>

`dotnet myapp.dll`

## <a name="environment-variables"></a><span data-ttu-id="df627-304">环境变量</span><span class="sxs-lookup"><span data-stu-id="df627-304">Environment variables</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="df627-305">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="df627-305">.NET Core 2.1</span></span>](#tab/netcore21)

`DOTNET_PACKAGES`

<span data-ttu-id="df627-306">主包缓存。</span><span class="sxs-lookup"><span data-stu-id="df627-306">The primary package cache.</span></span> <span data-ttu-id="df627-307">如果未设置，则默认为 Unix 上的 `$HOME/.nuget/packages` 或 Windows 上的 `%HOME%\NuGet\Packages`。</span><span class="sxs-lookup"><span data-stu-id="df627-307">If not set, it defaults to `$HOME/.nuget/packages` on Unix or `%HOME%\NuGet\Packages` on Windows.</span></span>

`DOTNET_SERVICING`

<span data-ttu-id="df627-308">指定加载运行时期间共享主机要使用的服务索引的位置。</span><span class="sxs-lookup"><span data-stu-id="df627-308">Specifies the location of the servicing index to use by the shared host when loading the runtime.</span></span>

`DOTNET_CLI_TELEMETRY_OPTOUT`

<span data-ttu-id="df627-309">指定是否收集并向 Microsoft 发送 .NET Core 工具使用情况的相关数据。</span><span class="sxs-lookup"><span data-stu-id="df627-309">Specifies whether data about the .NET Core tools usage is collected and sent to Microsoft.</span></span> <span data-ttu-id="df627-310">设置为 `true` 以选择退出遥测功能（接受的值为 `true`、`1` 或 `yes`）。</span><span class="sxs-lookup"><span data-stu-id="df627-310">Set to `true` to opt-out of the telemetry feature (values `true`, `1`, or `yes` accepted).</span></span> <span data-ttu-id="df627-311">否则，设置为 `false` 以选择加入遥测功能（接受的值为 `false`、`0` 或 `no`）。</span><span class="sxs-lookup"><span data-stu-id="df627-311">Otherwise, set to `false` to opt into the telemetry features (values `false`, `0`, or `no` accepted).</span></span> <span data-ttu-id="df627-312">如果未设置，则默认为 `false` 且遥测功能为活动状态。</span><span class="sxs-lookup"><span data-stu-id="df627-312">If not set, the default is `false` and the telemetry feature is active.</span></span>

`DOTNET_MULTILEVEL_LOOKUP`

<span data-ttu-id="df627-313">指定是否从全局位置解析 .NET Core 运行时、共享框架或 SDK。</span><span class="sxs-lookup"><span data-stu-id="df627-313">Specifies whether .NET Core runtime, shared framework, or SDK are resolved from the global location.</span></span> <span data-ttu-id="df627-314">如果未设置，则默认为 `true`。</span><span class="sxs-lookup"><span data-stu-id="df627-314">If not set, it defaults to `true`.</span></span> <span data-ttu-id="df627-315">设置为 `false` 不从全局位置解析，并且具有独立的 .NET Core 安装（接受的值为 `0` 或 `false`）。</span><span class="sxs-lookup"><span data-stu-id="df627-315">Set to `false` to not resolve from the global location and have isolated .NET Core installations (values `0` or `false` are accepted).</span></span> <span data-ttu-id="df627-316">有关多级别查找的详细信息，请参阅 [Multi-level SharedFX Lookup](https://github.com/dotnet/core-setup/blob/master/Documentation/design-docs/multilevel-sharedfx-lookup.md)（多级别 SharedFX 查找）。</span><span class="sxs-lookup"><span data-stu-id="df627-316">For more information about multi-level lookup, see [Multi-level SharedFX Lookup](https://github.com/dotnet/core-setup/blob/master/Documentation/design-docs/multilevel-sharedfx-lookup.md).</span></span>

`DOTNET_ROLL_FORWARD_ON_NO_CANDIDATE_FX`

<span data-ttu-id="df627-317">如果设置为 `0`，则禁用次要版本前滚。</span><span class="sxs-lookup"><span data-stu-id="df627-317">Disables minor version roll forward, if set to `0`.</span></span> <span data-ttu-id="df627-318">有关详细信息，请参阅[前滚](../whats-new/dotnet-core-2-1.md#roll-forward)。</span><span class="sxs-lookup"><span data-stu-id="df627-318">For more information, see [Roll forward](../whats-new/dotnet-core-2-1.md#roll-forward).</span></span>

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="df627-319">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="df627-319">.NET Core 2.0</span></span>](#tab/netcore20)

`DOTNET_PACKAGES`

<span data-ttu-id="df627-320">主包缓存。</span><span class="sxs-lookup"><span data-stu-id="df627-320">The primary package cache.</span></span> <span data-ttu-id="df627-321">如果未设置，则默认为 Unix 上的 `$HOME/.nuget/packages` 或 Windows 上的 `%HOME%\NuGet\Packages`。</span><span class="sxs-lookup"><span data-stu-id="df627-321">If not set, it defaults to `$HOME/.nuget/packages` on Unix or `%HOME%\NuGet\Packages` on Windows.</span></span>

`DOTNET_SERVICING`

<span data-ttu-id="df627-322">指定加载运行时期间共享主机要使用的服务索引的位置。</span><span class="sxs-lookup"><span data-stu-id="df627-322">Specifies the location of the servicing index to use by the shared host when loading the runtime.</span></span>

`DOTNET_CLI_TELEMETRY_OPTOUT`

<span data-ttu-id="df627-323">指定是否收集并向 Microsoft 发送 .NET Core 工具使用情况的相关数据。</span><span class="sxs-lookup"><span data-stu-id="df627-323">Specifies whether data about the .NET Core tools usage is collected and sent to Microsoft.</span></span> <span data-ttu-id="df627-324">设置为 `true` 以选择退出遥测功能（接受的值为 `true`、`1` 或 `yes`）。</span><span class="sxs-lookup"><span data-stu-id="df627-324">Set to `true` to opt-out of the telemetry feature (values `true`, `1`, or `yes` accepted).</span></span> <span data-ttu-id="df627-325">否则，设置为 `false` 以选择加入遥测功能（接受的值为 `false`、`0` 或 `no`）。</span><span class="sxs-lookup"><span data-stu-id="df627-325">Otherwise, set to `false` to opt into the telemetry features (values `false`, `0`, or `no` accepted).</span></span> <span data-ttu-id="df627-326">如果未设置，则默认为 `false` 且遥测功能为活动状态。</span><span class="sxs-lookup"><span data-stu-id="df627-326">If not set, the default is `false` and the telemetry feature is active.</span></span>

`DOTNET_MULTILEVEL_LOOKUP`

<span data-ttu-id="df627-327">指定是否从全局位置解析 .NET Core 运行时、共享框架或 SDK。</span><span class="sxs-lookup"><span data-stu-id="df627-327">Specifies whether .NET Core runtime, shared framework, or SDK are resolved from the global location.</span></span> <span data-ttu-id="df627-328">如果未设置，则默认为 `true`。</span><span class="sxs-lookup"><span data-stu-id="df627-328">If not set, it defaults to `true`.</span></span> <span data-ttu-id="df627-329">设置为 `false` 不从全局位置解析，并且具有独立的 .NET Core 安装（接受的值为 `0` 或 `false`）。</span><span class="sxs-lookup"><span data-stu-id="df627-329">Set to `false` to not resolve from the global location and have isolated .NET Core installations (values `0` or `false` are accepted).</span></span> <span data-ttu-id="df627-330">有关多级别查找的详细信息，请参阅 [Multi-level SharedFX Lookup](https://github.com/dotnet/core-setup/blob/master/Documentation/design-docs/multilevel-sharedfx-lookup.md)（多级别 SharedFX 查找）。</span><span class="sxs-lookup"><span data-stu-id="df627-330">For more information about multi-level lookup, see [Multi-level SharedFX Lookup](https://github.com/dotnet/core-setup/blob/master/Documentation/design-docs/multilevel-sharedfx-lookup.md).</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="df627-331">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="df627-331">.NET Core 1.x</span></span>](#tab/netcore1x)

`DOTNET_PACKAGES`

<span data-ttu-id="df627-332">主包缓存。</span><span class="sxs-lookup"><span data-stu-id="df627-332">The primary package cache.</span></span> <span data-ttu-id="df627-333">如果未设置，则默认为 Unix 上的 `$HOME/.nuget/packages` 或 Windows 上的 `%HOME%\NuGet\Packages`。</span><span class="sxs-lookup"><span data-stu-id="df627-333">If not set, it defaults to `$HOME/.nuget/packages` on Unix or `%HOME%\NuGet\Packages` on Windows.</span></span>

`DOTNET_SERVICING`

<span data-ttu-id="df627-334">指定加载运行时期间共享主机要使用的服务索引的位置。</span><span class="sxs-lookup"><span data-stu-id="df627-334">Specifies the location of the servicing index to use by the shared host when loading the runtime.</span></span>

`DOTNET_CLI_TELEMETRY_OPTOUT`

<span data-ttu-id="df627-335">指定是否收集并向 Microsoft 发送 .NET Core 工具使用情况的相关数据。</span><span class="sxs-lookup"><span data-stu-id="df627-335">Specifies whether data about the .NET Core tools usage is collected and sent to Microsoft.</span></span> <span data-ttu-id="df627-336">设置为 `true` 以选择退出遥测功能（接受的值为 `true`、`1` 或 `yes`）。</span><span class="sxs-lookup"><span data-stu-id="df627-336">Set to `true` to opt-out of the telemetry feature (values `true`, `1`, or `yes` accepted).</span></span> <span data-ttu-id="df627-337">否则，设置为 `false` 以选择加入遥测功能（接受的值为 `false`、`0` 或 `no`）。</span><span class="sxs-lookup"><span data-stu-id="df627-337">Otherwise, set to `false` to opt into the telemetry features (values `false`, `0`, or `no` accepted).</span></span> <span data-ttu-id="df627-338">如果未设置，则默认为 `false` 且遥测功能为活动状态。</span><span class="sxs-lookup"><span data-stu-id="df627-338">If not set, the default is `false` and the telemetry feature is active.</span></span>

---
