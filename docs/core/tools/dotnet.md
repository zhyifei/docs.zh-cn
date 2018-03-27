---
title: dotnet 命令 - .NET Core CLI
description: 了解 dotnet 命令（.NET Core CLI 工具的通用驱动程序）及其用法。
author: mairaw
ms.author: mairaw
ms.date: 03/20/2018
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.workload:
- dotnetcore
ms.openlocfilehash: 2d22124cb613152df402046541650f3262e7e202
ms.sourcegitcommit: 6f967c86dde55472440f0c8669b0e910ee3c53ba
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/22/2018
---
# <a name="dotnet-command"></a><span data-ttu-id="b5f25-103">dotnet 命令</span><span class="sxs-lookup"><span data-stu-id="b5f25-103">dotnet command</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="b5f25-104">name</span><span class="sxs-lookup"><span data-stu-id="b5f25-104">Name</span></span>

<span data-ttu-id="b5f25-105">`dotnet` - 运行命令行命令的通用驱动程序。</span><span class="sxs-lookup"><span data-stu-id="b5f25-105">`dotnet` - General driver for running the command-line commands.</span></span>

## <a name="synopsis"></a><span data-ttu-id="b5f25-106">摘要</span><span class="sxs-lookup"><span data-stu-id="b5f25-106">Synopsis</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="b5f25-107">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="b5f25-107">.NET Core 2.x</span></span>](#tab/netcore2x)
```
dotnet [command] [arguments] [--additional-deps] [--additionalprobingpath] [-d|--diagnostics]
    [--fx-version] [-h|--help] [--info] [--roll-forward-on-no-candidate-fx] [-v|--verbosity] [--version]
```
# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="b5f25-108">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="b5f25-108">.NET Core 1.x</span></span>](#tab/netcore1x)
```
dotnet [command] [arguments] [--additionalprobingpath] [-d|--diagnostics] [--fx-version]
    [-h|--help] [--info] [-v|--verbosity] [--version]
```
---

## <a name="description"></a><span data-ttu-id="b5f25-109">描述</span><span class="sxs-lookup"><span data-stu-id="b5f25-109">Description</span></span>

<span data-ttu-id="b5f25-110">`dotnet` 是用于命令行接口 (CLI) 工具链的通用驱动程序。</span><span class="sxs-lookup"><span data-stu-id="b5f25-110">`dotnet` is a generic driver for the Command Line Interface (CLI) toolchain.</span></span> <span data-ttu-id="b5f25-111">它可自行调用，并提供简短的使用说明。</span><span class="sxs-lookup"><span data-stu-id="b5f25-111">Invoked on its own, it provides brief usage instructions.</span></span>

<span data-ttu-id="b5f25-112">每种特定功能均实现为命令。</span><span class="sxs-lookup"><span data-stu-id="b5f25-112">Each specific feature is implemented as a command.</span></span> <span data-ttu-id="b5f25-113">若要使用此功能，请在 `dotnet` 后指定该命令，例如 [`dotnet build`](dotnet-build.md)。</span><span class="sxs-lookup"><span data-stu-id="b5f25-113">In order to use the feature, the command is specified after `dotnet`, such as [`dotnet build`](dotnet-build.md).</span></span> <span data-ttu-id="b5f25-114">该命令后的所有参数均为其自有参数。</span><span class="sxs-lookup"><span data-stu-id="b5f25-114">All of the arguments following the command are its own arguments.</span></span>

<span data-ttu-id="b5f25-115">`dotnet` 自行作为命令使用的唯一情况是运行[依赖于框架的应用](../deploying/index.md)。</span><span class="sxs-lookup"><span data-stu-id="b5f25-115">The only time `dotnet` is used as a command on its own is to run [framework-dependent apps](../deploying/index.md).</span></span> <span data-ttu-id="b5f25-116">在 `dotnet` 谓词后指定应用程序 DLL 便可执行该应用程序（例如，`dotnet myapp.dll`）。</span><span class="sxs-lookup"><span data-stu-id="b5f25-116">Specify an application DLL after the `dotnet` verb to execute the application (for example, `dotnet myapp.dll`).</span></span>

## <a name="options"></a><span data-ttu-id="b5f25-117">选项</span><span class="sxs-lookup"><span data-stu-id="b5f25-117">Options</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="b5f25-118">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="b5f25-118">.NET Core 2.x</span></span>](#tab/netcore2x)

`--additional-deps <PATH>`

<span data-ttu-id="b5f25-119">其他 deps.json 文件的路径。</span><span class="sxs-lookup"><span data-stu-id="b5f25-119">Path to additional *deps.json* file.</span></span>

`--additionalprobingpath <PATH>`

<span data-ttu-id="b5f25-120">包含要进行探测的探测策略和程序集的路径。</span><span class="sxs-lookup"><span data-stu-id="b5f25-120">Path containing probing policy and assemblies to probe.</span></span>

`-d|--diagnostics`

<span data-ttu-id="b5f25-121">启用诊断输出。</span><span class="sxs-lookup"><span data-stu-id="b5f25-121">Enables diagnostic output.</span></span>

`--fx-version <VERSION>`

<span data-ttu-id="b5f25-122">运行应用程序所使用的已安装 .NET Core 运行时的版本。</span><span class="sxs-lookup"><span data-stu-id="b5f25-122">Version of the installed .NET Core runtime to use to run the application.</span></span>

`-h|--help`

<span data-ttu-id="b5f25-123">打印出有关命令的简短帮助。</span><span class="sxs-lookup"><span data-stu-id="b5f25-123">Prints out a short help for the command.</span></span> <span data-ttu-id="b5f25-124">如果使用 `dotnet`，还会打印可用命令的列表。</span><span class="sxs-lookup"><span data-stu-id="b5f25-124">If using with `dotnet`, it also prints a list of the available commands.</span></span>

`--info`

<span data-ttu-id="b5f25-125">打印出有关 CLI 工具和环境的详细信息，例如当前操作系统、提交该版本的 SHA 和其他信息。</span><span class="sxs-lookup"><span data-stu-id="b5f25-125">Prints out detailed information about the CLI tooling and the environment, such as the current operating system, commit SHA for the version, and other information.</span></span>

`--roll-forward-on-no-candidate-fx`

 <span data-ttu-id="b5f25-126">在没有候选共享框架的情况下前滚。</span><span class="sxs-lookup"><span data-stu-id="b5f25-126">Rolls forward on no candidate shared framework.</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="b5f25-127">设置命令的详细级别。</span><span class="sxs-lookup"><span data-stu-id="b5f25-127">Sets the verbosity level of the command.</span></span> <span data-ttu-id="b5f25-128">允许使用的值为 `q[uiet]`、`m[inimal]`、`n[ormal]`、`d[etailed]` 和 `diag[nostic]`。</span><span class="sxs-lookup"><span data-stu-id="b5f25-128">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="b5f25-129">并非在每个命令中均受支持；请参阅特定的命令页，确定此选项是否可用。</span><span class="sxs-lookup"><span data-stu-id="b5f25-129">Not supported in every command; see specific command page to determine if this option is available.</span></span>

`--version`

<span data-ttu-id="b5f25-130">打印使用中的 .NET Core SDK 版本。</span><span class="sxs-lookup"><span data-stu-id="b5f25-130">Prints out the version of the .NET Core SDK in use.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="b5f25-131">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="b5f25-131">.NET Core 1.x</span></span>](#tab/netcore1x)

`--additionalprobingpath <PATH>`

<span data-ttu-id="b5f25-132">包含要进行探测的探测策略和程序集的路径。</span><span class="sxs-lookup"><span data-stu-id="b5f25-132">Path containing probing policy and assemblies to probe.</span></span>

`-d|--diagnostics`

<span data-ttu-id="b5f25-133">启用诊断输出。</span><span class="sxs-lookup"><span data-stu-id="b5f25-133">Enables diagnostic output.</span></span>

`--fx-version <VERSION>`

<span data-ttu-id="b5f25-134">运行应用程序所使用的已安装 .NET Core 运行时的版本。</span><span class="sxs-lookup"><span data-stu-id="b5f25-134">Version of the installed .NET Core runtime to use to run the application.</span></span>

`-h|--help`

<span data-ttu-id="b5f25-135">打印出有关命令的简短帮助。</span><span class="sxs-lookup"><span data-stu-id="b5f25-135">Prints out a short help for the command.</span></span> <span data-ttu-id="b5f25-136">如果使用 `dotnet`，还会打印可用命令的列表。</span><span class="sxs-lookup"><span data-stu-id="b5f25-136">If using with `dotnet`, it also prints a list of the available commands.</span></span>

`--info`

<span data-ttu-id="b5f25-137">打印出有关 CLI 工具和环境的详细信息，例如当前操作系统、提交该版本的 SHA 和其他信息。</span><span class="sxs-lookup"><span data-stu-id="b5f25-137">Prints out detailed information about the CLI tooling and the environment, such as the current operating system, commit SHA for the version, and other information.</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="b5f25-138">设置命令的详细级别。</span><span class="sxs-lookup"><span data-stu-id="b5f25-138">Sets the verbosity level of the command.</span></span> <span data-ttu-id="b5f25-139">允许使用的值为 `q[uiet]`、`m[inimal]`、`n[ormal]`、`d[etailed]` 和 `diag[nostic]`。</span><span class="sxs-lookup"><span data-stu-id="b5f25-139">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="b5f25-140">并非在每个命令中均受支持；请参阅特定的命令页，确定此选项是否可用。</span><span class="sxs-lookup"><span data-stu-id="b5f25-140">Not supported in every command; see specific command page to determine if this option is available.</span></span>

`--version`

<span data-ttu-id="b5f25-141">打印使用中的 .NET Core SDK 版本。</span><span class="sxs-lookup"><span data-stu-id="b5f25-141">Prints out the version of the .NET Core SDK in use.</span></span>

---

## <a name="dotnet-commands"></a><span data-ttu-id="b5f25-142">dotnet 命令</span><span class="sxs-lookup"><span data-stu-id="b5f25-142">dotnet commands</span></span>

### <a name="general"></a><span data-ttu-id="b5f25-143">常规</span><span class="sxs-lookup"><span data-stu-id="b5f25-143">General</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="b5f25-144">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="b5f25-144">.NET Core 2.x</span></span>](#tab/netcore2x)

| <span data-ttu-id="b5f25-145">命令</span><span class="sxs-lookup"><span data-stu-id="b5f25-145">Command</span></span>                             | <span data-ttu-id="b5f25-146">函数</span><span class="sxs-lookup"><span data-stu-id="b5f25-146">Function</span></span>                                                            |
| ----------------------------------- | ------------------------------------------------------------------- |
| [<span data-ttu-id="b5f25-147">dotnet build</span><span class="sxs-lookup"><span data-stu-id="b5f25-147">dotnet build</span></span>](dotnet-build.md)     | <span data-ttu-id="b5f25-148">生成 .NET Core 应用程序。</span><span class="sxs-lookup"><span data-stu-id="b5f25-148">Builds a .NET Core application.</span></span>                                     |
| [<span data-ttu-id="b5f25-149">dotnet clean</span><span class="sxs-lookup"><span data-stu-id="b5f25-149">dotnet clean</span></span>](dotnet-clean.md)     | <span data-ttu-id="b5f25-150">清除生成输出。</span><span class="sxs-lookup"><span data-stu-id="b5f25-150">Clean build outputs.</span></span>                                              |
| [<span data-ttu-id="b5f25-151">dotnet help</span><span class="sxs-lookup"><span data-stu-id="b5f25-151">dotnet help</span></span>](dotnet-help.md)       | <span data-ttu-id="b5f25-152">显示命令更详细的在线文档。</span><span class="sxs-lookup"><span data-stu-id="b5f25-152">Shows more detailed documentation online for the command.</span></span>           |
| [<span data-ttu-id="b5f25-153">dotnet migrate</span><span class="sxs-lookup"><span data-stu-id="b5f25-153">dotnet migrate</span></span>](dotnet-migrate.md) | <span data-ttu-id="b5f25-154">将有效的预览版 2 项目迁移到 .NET Core SDK 1.0 项目。</span><span class="sxs-lookup"><span data-stu-id="b5f25-154">Migrates a valid Preview 2 project to a .NET Core SDK 1.0 project.</span></span>  |
| [<span data-ttu-id="b5f25-155">dotnet msbuild</span><span class="sxs-lookup"><span data-stu-id="b5f25-155">dotnet msbuild</span></span>](dotnet-msbuild.md) | <span data-ttu-id="b5f25-156">提供对 MSBuild 命令行的访问权限。</span><span class="sxs-lookup"><span data-stu-id="b5f25-156">Provides access to the MSBuild command line.</span></span>                        |
| [<span data-ttu-id="b5f25-157">dotnet new</span><span class="sxs-lookup"><span data-stu-id="b5f25-157">dotnet new</span></span>](dotnet-new.md)         | <span data-ttu-id="b5f25-158">为给定的模板初始化 C# 或 F # 项目。</span><span class="sxs-lookup"><span data-stu-id="b5f25-158">Initializes a C# or F# project for a given template.</span></span>                |
| [<span data-ttu-id="b5f25-159">dotnet pack</span><span class="sxs-lookup"><span data-stu-id="b5f25-159">dotnet pack</span></span>](dotnet-pack.md)       | <span data-ttu-id="b5f25-160">创建代码的 NuGet 包。</span><span class="sxs-lookup"><span data-stu-id="b5f25-160">Creates a NuGet package of your code.</span></span>                               |
| [<span data-ttu-id="b5f25-161">dotnet publish</span><span class="sxs-lookup"><span data-stu-id="b5f25-161">dotnet publish</span></span>](dotnet-publish.md) | <span data-ttu-id="b5f25-162">发布 .NET 依赖于框架或独立应用程序。</span><span class="sxs-lookup"><span data-stu-id="b5f25-162">Publishes a .NET framework-dependent or self-contained application.</span></span> |
| [<span data-ttu-id="b5f25-163">dotnet restore</span><span class="sxs-lookup"><span data-stu-id="b5f25-163">dotnet restore</span></span>](dotnet-restore.md) | <span data-ttu-id="b5f25-164">还原给定应用程序的依赖项。</span><span class="sxs-lookup"><span data-stu-id="b5f25-164">Restores the dependencies for a given application.</span></span>                  |
| [<span data-ttu-id="b5f25-165">dotnet run</span><span class="sxs-lookup"><span data-stu-id="b5f25-165">dotnet run</span></span>](dotnet-run.md)         | <span data-ttu-id="b5f25-166">从源运行应用程序。</span><span class="sxs-lookup"><span data-stu-id="b5f25-166">Runs the application from source.</span></span>                                   |
| [<span data-ttu-id="b5f25-167">dotnet sln</span><span class="sxs-lookup"><span data-stu-id="b5f25-167">dotnet sln</span></span>](dotnet-sln.md)         | <span data-ttu-id="b5f25-168">用于添加、删除和列出解决方案文件中项目的选项。</span><span class="sxs-lookup"><span data-stu-id="b5f25-168">Options to add, remove, and list projects in a solution file.</span></span>       |
| [<span data-ttu-id="b5f25-169">dotnet store</span><span class="sxs-lookup"><span data-stu-id="b5f25-169">dotnet store</span></span>](dotnet-store.md)     | <span data-ttu-id="b5f25-170">将程序集存储到运行时包存储区。</span><span class="sxs-lookup"><span data-stu-id="b5f25-170">Stores assemblies in the runtime package store.</span></span>                     |
| [<span data-ttu-id="b5f25-171">dotnet test</span><span class="sxs-lookup"><span data-stu-id="b5f25-171">dotnet test</span></span>](dotnet-test.md)       | <span data-ttu-id="b5f25-172">使用测试运行程序运行测试。</span><span class="sxs-lookup"><span data-stu-id="b5f25-172">Runs tests using a test runner.</span></span>                                     |

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="b5f25-173">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="b5f25-173">.NET Core 1.x</span></span>](#tab/netcore1x)

| <span data-ttu-id="b5f25-174">命令</span><span class="sxs-lookup"><span data-stu-id="b5f25-174">Command</span></span>                             | <span data-ttu-id="b5f25-175">函数</span><span class="sxs-lookup"><span data-stu-id="b5f25-175">Function</span></span>                                                            |
| ----------------------------------- | ------------------------------------------------------------------- |
| [<span data-ttu-id="b5f25-176">dotnet build</span><span class="sxs-lookup"><span data-stu-id="b5f25-176">dotnet build</span></span>](dotnet-build.md)     | <span data-ttu-id="b5f25-177">生成 .NET Core 应用程序。</span><span class="sxs-lookup"><span data-stu-id="b5f25-177">Builds a .NET Core application.</span></span>                                     |
| [<span data-ttu-id="b5f25-178">dotnet clean</span><span class="sxs-lookup"><span data-stu-id="b5f25-178">dotnet clean</span></span>](dotnet-clean.md)     | <span data-ttu-id="b5f25-179">清除生成输出。</span><span class="sxs-lookup"><span data-stu-id="b5f25-179">Clean build outputs.</span></span>                                              |
| [<span data-ttu-id="b5f25-180">dotnet migrate</span><span class="sxs-lookup"><span data-stu-id="b5f25-180">dotnet migrate</span></span>](dotnet-migrate.md) | <span data-ttu-id="b5f25-181">将有效的预览版 2 项目迁移到 .NET Core SDK 1.0 项目。</span><span class="sxs-lookup"><span data-stu-id="b5f25-181">Migrates a valid Preview 2 project to a .NET Core SDK 1.0 project.</span></span>  |
| [<span data-ttu-id="b5f25-182">dotnet msbuild</span><span class="sxs-lookup"><span data-stu-id="b5f25-182">dotnet msbuild</span></span>](dotnet-msbuild.md) | <span data-ttu-id="b5f25-183">提供对 MSBuild 命令行的访问权限。</span><span class="sxs-lookup"><span data-stu-id="b5f25-183">Provides access to the MSBuild command line.</span></span>                        |
| [<span data-ttu-id="b5f25-184">dotnet new</span><span class="sxs-lookup"><span data-stu-id="b5f25-184">dotnet new</span></span>](dotnet-new.md)         | <span data-ttu-id="b5f25-185">为给定的模板初始化 C# 或 F # 项目。</span><span class="sxs-lookup"><span data-stu-id="b5f25-185">Initializes a C# or F# project for a given template.</span></span>                |
| [<span data-ttu-id="b5f25-186">dotnet pack</span><span class="sxs-lookup"><span data-stu-id="b5f25-186">dotnet pack</span></span>](dotnet-pack.md)       | <span data-ttu-id="b5f25-187">创建代码的 NuGet 包。</span><span class="sxs-lookup"><span data-stu-id="b5f25-187">Creates a NuGet package of your code.</span></span>                               |
| [<span data-ttu-id="b5f25-188">dotnet publish</span><span class="sxs-lookup"><span data-stu-id="b5f25-188">dotnet publish</span></span>](dotnet-publish.md) | <span data-ttu-id="b5f25-189">发布 .NET 依赖于框架或独立应用程序。</span><span class="sxs-lookup"><span data-stu-id="b5f25-189">Publishes a .NET framework-dependent or self-contained application.</span></span> |
| [<span data-ttu-id="b5f25-190">dotnet restore</span><span class="sxs-lookup"><span data-stu-id="b5f25-190">dotnet restore</span></span>](dotnet-restore.md) | <span data-ttu-id="b5f25-191">还原给定应用程序的依赖项。</span><span class="sxs-lookup"><span data-stu-id="b5f25-191">Restores the dependencies for a given application.</span></span>                  |
| [<span data-ttu-id="b5f25-192">dotnet run</span><span class="sxs-lookup"><span data-stu-id="b5f25-192">dotnet run</span></span>](dotnet-run.md)         | <span data-ttu-id="b5f25-193">从源运行应用程序。</span><span class="sxs-lookup"><span data-stu-id="b5f25-193">Runs the application from source.</span></span>                                   |
| [<span data-ttu-id="b5f25-194">dotnet sln</span><span class="sxs-lookup"><span data-stu-id="b5f25-194">dotnet sln</span></span>](dotnet-sln.md)         | <span data-ttu-id="b5f25-195">用于添加、删除和列出解决方案文件中项目的选项。</span><span class="sxs-lookup"><span data-stu-id="b5f25-195">Options to add, remove, and list projects in a solution file.</span></span>       |
| [<span data-ttu-id="b5f25-196">dotnet test</span><span class="sxs-lookup"><span data-stu-id="b5f25-196">dotnet test</span></span>](dotnet-test.md)       | <span data-ttu-id="b5f25-197">使用测试运行程序运行测试。</span><span class="sxs-lookup"><span data-stu-id="b5f25-197">Runs tests using a test runner.</span></span>                                     |

---

### <a name="project-references"></a><span data-ttu-id="b5f25-198">项目引用</span><span class="sxs-lookup"><span data-stu-id="b5f25-198">Project references</span></span>

<span data-ttu-id="b5f25-199">命令</span><span class="sxs-lookup"><span data-stu-id="b5f25-199">Command</span></span> | <span data-ttu-id="b5f25-200">函数</span><span class="sxs-lookup"><span data-stu-id="b5f25-200">Function</span></span>
--- | ---
[<span data-ttu-id="b5f25-201">dotnet add reference</span><span class="sxs-lookup"><span data-stu-id="b5f25-201">dotnet add reference</span></span>](dotnet-add-reference.md) | <span data-ttu-id="b5f25-202">添加项目引用。</span><span class="sxs-lookup"><span data-stu-id="b5f25-202">Add a project reference.</span></span>
[<span data-ttu-id="b5f25-203">dotnet list reference</span><span class="sxs-lookup"><span data-stu-id="b5f25-203">dotnet list reference</span></span>](dotnet-list-reference.md) | <span data-ttu-id="b5f25-204">列出项目引用。</span><span class="sxs-lookup"><span data-stu-id="b5f25-204">List project references.</span></span>
[<span data-ttu-id="b5f25-205">dotnet remove reference</span><span class="sxs-lookup"><span data-stu-id="b5f25-205">dotnet remove reference</span></span>](dotnet-remove-reference.md) | <span data-ttu-id="b5f25-206">删除项目引用。</span><span class="sxs-lookup"><span data-stu-id="b5f25-206">Remove a project reference.</span></span>

### <a name="nuget-packages"></a><span data-ttu-id="b5f25-207">NuGet 包</span><span class="sxs-lookup"><span data-stu-id="b5f25-207">NuGet packages</span></span>

<span data-ttu-id="b5f25-208">命令</span><span class="sxs-lookup"><span data-stu-id="b5f25-208">Command</span></span> | <span data-ttu-id="b5f25-209">函数</span><span class="sxs-lookup"><span data-stu-id="b5f25-209">Function</span></span>
--- | ---
[<span data-ttu-id="b5f25-210">dotnet add package</span><span class="sxs-lookup"><span data-stu-id="b5f25-210">dotnet add package</span></span>](dotnet-add-package.md) | <span data-ttu-id="b5f25-211">添加 NuGet 包。</span><span class="sxs-lookup"><span data-stu-id="b5f25-211">Add a NuGet package.</span></span>
[<span data-ttu-id="b5f25-212">dotnet remove package</span><span class="sxs-lookup"><span data-stu-id="b5f25-212">dotnet remove package</span></span>](dotnet-remove-package.md) | <span data-ttu-id="b5f25-213">删除 NuGet 包。</span><span class="sxs-lookup"><span data-stu-id="b5f25-213">Remove a NuGet package.</span></span>

### <a name="nuget-commands"></a><span data-ttu-id="b5f25-214">NuGet 命令</span><span class="sxs-lookup"><span data-stu-id="b5f25-214">NuGet commands</span></span>

<span data-ttu-id="b5f25-215">命令</span><span class="sxs-lookup"><span data-stu-id="b5f25-215">Command</span></span> | <span data-ttu-id="b5f25-216">函数</span><span class="sxs-lookup"><span data-stu-id="b5f25-216">Function</span></span>
--- | ---
[<span data-ttu-id="b5f25-217">dotnet nuget delete</span><span class="sxs-lookup"><span data-stu-id="b5f25-217">dotnet nuget delete</span></span>](dotnet-nuget-delete.md) | <span data-ttu-id="b5f25-218">从服务器删除或取消列出包。</span><span class="sxs-lookup"><span data-stu-id="b5f25-218">Deletes or unlists a package from the server.</span></span>
[<span data-ttu-id="b5f25-219">dotnet nuget locals</span><span class="sxs-lookup"><span data-stu-id="b5f25-219">dotnet nuget locals</span></span>](dotnet-nuget-locals.md) | <span data-ttu-id="b5f25-220">清除或列出本地 NuGet 资源，例如 http 请求缓存、临时缓存或计算机范围的全局包文件夹。</span><span class="sxs-lookup"><span data-stu-id="b5f25-220">Clears or lists local NuGet resources such as http-request cache, temporary cache, or machine-wide global packages folder.</span></span>
[<span data-ttu-id="b5f25-221">dotnet nuget push</span><span class="sxs-lookup"><span data-stu-id="b5f25-221">dotnet nuget push</span></span>](dotnet-nuget-push.md) | <span data-ttu-id="b5f25-222">将包推送到服务器，并将其发布。</span><span class="sxs-lookup"><span data-stu-id="b5f25-222">Pushes a package to the server and publishes it.</span></span>

## <a name="examples"></a><span data-ttu-id="b5f25-223">示例</span><span class="sxs-lookup"><span data-stu-id="b5f25-223">Examples</span></span>

<span data-ttu-id="b5f25-224">初始化可以编译和运行的示例 .NET Core 控制台应用程序：</span><span class="sxs-lookup"><span data-stu-id="b5f25-224">Initialize a sample .NET Core console application that can be compiled and run:</span></span>

`dotnet new console`

<span data-ttu-id="b5f25-225">还原给定应用程序的依赖项：</span><span class="sxs-lookup"><span data-stu-id="b5f25-225">Restore dependencies for a given application:</span></span>

`dotnet restore`

[!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]

<span data-ttu-id="b5f25-226">生成给定目录中的项目及其依赖项：</span><span class="sxs-lookup"><span data-stu-id="b5f25-226">Build a project and its dependencies in a given directory:</span></span>

`dotnet build`

<span data-ttu-id="b5f25-227">运行名为 `myapp.dll` 的依赖于框架的应用：</span><span class="sxs-lookup"><span data-stu-id="b5f25-227">Run a framework-dependent app named `myapp.dll`:</span></span>

`dotnet myapp.dll`

## <a name="environment-variables"></a><span data-ttu-id="b5f25-228">环境变量</span><span class="sxs-lookup"><span data-stu-id="b5f25-228">Environment variables</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="b5f25-229">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="b5f25-229">.NET Core 2.x</span></span>](#tab/netcore2x)

`DOTNET_PACKAGES`

<span data-ttu-id="b5f25-230">主包缓存。</span><span class="sxs-lookup"><span data-stu-id="b5f25-230">The primary package cache.</span></span> <span data-ttu-id="b5f25-231">如果未设置，则默认为 Unix 上的 `$HOME/.nuget/packages` 或 Windows 上的 `%HOME%\NuGet\Packages`。</span><span class="sxs-lookup"><span data-stu-id="b5f25-231">If not set, it defaults to `$HOME/.nuget/packages` on Unix or `%HOME%\NuGet\Packages` on Windows.</span></span>

`DOTNET_SERVICING`

<span data-ttu-id="b5f25-232">指定加载运行时期间共享主机要使用的服务索引的位置。</span><span class="sxs-lookup"><span data-stu-id="b5f25-232">Specifies the location of the servicing index to use by the shared host when loading the runtime.</span></span>

`DOTNET_CLI_TELEMETRY_OPTOUT`

<span data-ttu-id="b5f25-233">指定是否收集并向 Microsoft 发送 .NET Core 工具使用情况的相关数据。</span><span class="sxs-lookup"><span data-stu-id="b5f25-233">Specifies whether data about the .NET Core tools usage is collected and sent to Microsoft.</span></span> <span data-ttu-id="b5f25-234">设置为 `true` 以选择退出遥测功能（接受值 `true`、`1` 或 `yes`）；否则，设置为 `false` 以选择加入遥测功能（接受值 `false`、`0` 或 `no`）。</span><span class="sxs-lookup"><span data-stu-id="b5f25-234">Set to `true` to opt-out of the telemetry feature (values `true`, `1`, or `yes` accepted); otherwise, set to `false` to opt-in to the telemetry features (values `false`, `0`, or `no` accepted).</span></span> <span data-ttu-id="b5f25-235">如果未设置，则默认为 `false` 且遥测功能为活动状态。</span><span class="sxs-lookup"><span data-stu-id="b5f25-235">If not set, the defaults is `false`, and the telemetry feature is active.</span></span>

`DOTNET_MULTILEVEL_LOOKUP`

<span data-ttu-id="b5f25-236">指定是否从全局位置解析 .NET Core 运行时、共享框架或 SDK。</span><span class="sxs-lookup"><span data-stu-id="b5f25-236">Specifies whether .NET Core runtime, shared framework or SDK are resolved from the global location.</span></span> <span data-ttu-id="b5f25-237">如果未设置，则默认为 `true`。</span><span class="sxs-lookup"><span data-stu-id="b5f25-237">If not set, it defaults to `true`.</span></span> <span data-ttu-id="b5f25-238">设置为 `false` 不从全局位置解析，并且具有独立的 .NET Core 安装（接受的值为 `0` 或 `false`）。</span><span class="sxs-lookup"><span data-stu-id="b5f25-238">Set to `false` to not resolve from the global location and have isolated .NET Core installations (values `0` or `false` are accepted).</span></span> <span data-ttu-id="b5f25-239">有关多级别查找的详细信息，请参阅 [Multi-level SharedFX Lookup](https://github.com/dotnet/core-setup/blob/master/Documentation/design-docs/multilevel-sharedfx-lookup.md)（多级别 SharedFX 查找）。</span><span class="sxs-lookup"><span data-stu-id="b5f25-239">For more information about multi-level lookup, see [Multi-level SharedFX Lookup](https://github.com/dotnet/core-setup/blob/master/Documentation/design-docs/multilevel-sharedfx-lookup.md).</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="b5f25-240">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="b5f25-240">.NET Core 1.x</span></span>](#tab/netcore1x)

`DOTNET_PACKAGES`

<span data-ttu-id="b5f25-241">主包缓存。</span><span class="sxs-lookup"><span data-stu-id="b5f25-241">The primary package cache.</span></span> <span data-ttu-id="b5f25-242">如果未设置，则默认为 Unix 上的 `$HOME/.nuget/packages` 或 Windows 上的 `%HOME%\NuGet\Packages`。</span><span class="sxs-lookup"><span data-stu-id="b5f25-242">If not set, it defaults to `$HOME/.nuget/packages` on Unix or `%HOME%\NuGet\Packages` on Windows.</span></span>

`DOTNET_SERVICING`

<span data-ttu-id="b5f25-243">指定加载运行时期间共享主机要使用的服务索引的位置。</span><span class="sxs-lookup"><span data-stu-id="b5f25-243">Specifies the location of the servicing index to use by the shared host when loading the runtime.</span></span>

`DOTNET_CLI_TELEMETRY_OPTOUT`

<span data-ttu-id="b5f25-244">指定是否收集并向 Microsoft 发送 .NET Core 工具使用情况的相关数据。</span><span class="sxs-lookup"><span data-stu-id="b5f25-244">Specifies whether data about the .NET Core tools usage is collected and sent to Microsoft.</span></span> <span data-ttu-id="b5f25-245">设置为 `true` 以选择退出遥测功能（接受值 `true`、`1` 或 `yes`）；否则，设置为 `false` 以选择加入遥测功能（接受值 `false`、`0` 或 `no`）。</span><span class="sxs-lookup"><span data-stu-id="b5f25-245">Set to `true` to opt-out of the telemetry feature (values `true`, `1`, or `yes` accepted); otherwise, set to `false` to opt-in to the telemetry features (values `false`, `0`, or `no` accepted).</span></span> <span data-ttu-id="b5f25-246">如果未设置，则默认为 `false` 且遥测功能为活动状态。</span><span class="sxs-lookup"><span data-stu-id="b5f25-246">If not set, the defaults is `false`, and the telemetry feature is active.</span></span>

---
