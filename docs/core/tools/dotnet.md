---
title: "dotnet 命令 - .NET Core CLI"
description: "了解 dotnet 命令（.NET Core CLI 工具的通用驱动程序）及其用法。"
author: mairaw
ms.author: mairaw
ms.date: 08/14/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.workload: dotnetcore
ms.openlocfilehash: 6db2bb6003e630aab900222eb20e33af287cf9c5
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/23/2017
---
# <a name="dotnet-command"></a><span data-ttu-id="b99dd-103">dotnet 命令</span><span class="sxs-lookup"><span data-stu-id="b99dd-103">dotnet command</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="b99dd-104">name</span><span class="sxs-lookup"><span data-stu-id="b99dd-104">Name</span></span>

<span data-ttu-id="b99dd-105">`dotnet` - 运行命令行命令的通用驱动程序。</span><span class="sxs-lookup"><span data-stu-id="b99dd-105">`dotnet` - General driver for running the command-line commands.</span></span>

## <a name="synopsis"></a><span data-ttu-id="b99dd-106">摘要</span><span class="sxs-lookup"><span data-stu-id="b99dd-106">Synopsis</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="b99dd-107">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="b99dd-107">.NET Core 2.x</span></span>](#tab/netcore2x)
```
dotnet [command] [arguments] [--additional-deps] [--additionalprobingpath] [-d|--diagnostics] [--fx-version] [-h|--help] [--info] [--roll-forward-on-no-candidate-fx] [-v|--verbose] [--version]
```
# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="b99dd-108">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="b99dd-108">.NET Core 1.x</span></span>](#tab/netcore1x)
```
dotnet [command] [arguments] [--additionalprobingpath] [-d|--diagnostics] [--fx-version] [-h|--help] [--info] [-v|--verbose] [--version]
```
---

## <a name="description"></a><span data-ttu-id="b99dd-109">描述</span><span class="sxs-lookup"><span data-stu-id="b99dd-109">Description</span></span>

<span data-ttu-id="b99dd-110">`dotnet` 是用于命令行接口 (CLI) 工具链的通用驱动程序。</span><span class="sxs-lookup"><span data-stu-id="b99dd-110">`dotnet` is a generic driver for the Command Line Interface (CLI) toolchain.</span></span> <span data-ttu-id="b99dd-111">它可自行调用，并提供简短的使用说明。</span><span class="sxs-lookup"><span data-stu-id="b99dd-111">Invoked on its own, it provides brief usage instructions.</span></span>

<span data-ttu-id="b99dd-112">每种特定功能均实现为命令。</span><span class="sxs-lookup"><span data-stu-id="b99dd-112">Each specific feature is implemented as a command.</span></span> <span data-ttu-id="b99dd-113">若要使用此功能，请在 `dotnet` 后指定该命令，例如 [`dotnet build`](dotnet-build.md)。</span><span class="sxs-lookup"><span data-stu-id="b99dd-113">In order to use the feature, the command is specified after `dotnet`, such as [`dotnet build`](dotnet-build.md).</span></span> <span data-ttu-id="b99dd-114">该命令后的所有参数均为其自有参数。</span><span class="sxs-lookup"><span data-stu-id="b99dd-114">All of the arguments following the command are its own arguments.</span></span>

<span data-ttu-id="b99dd-115">`dotnet` 自行作为命令使用的唯一情况是运行[依赖于框架的应用](../deploying/index.md)。</span><span class="sxs-lookup"><span data-stu-id="b99dd-115">The only time `dotnet` is used as a command on its own is to run [framework-dependent apps](../deploying/index.md).</span></span> <span data-ttu-id="b99dd-116">在 `dotnet` 谓词后指定应用程序 DLL 便可执行该应用程序（例如，`dotnet myapp.dll`）。</span><span class="sxs-lookup"><span data-stu-id="b99dd-116">Specify an application DLL after the `dotnet` verb to execute the application (for example, `dotnet myapp.dll`).</span></span>

## <a name="options"></a><span data-ttu-id="b99dd-117">选项</span><span class="sxs-lookup"><span data-stu-id="b99dd-117">Options</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="b99dd-118">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="b99dd-118">.NET Core 2.x</span></span>](#tab/netcore2x)

`--additionaldeps <PATH>`

<span data-ttu-id="b99dd-119">其他 deps.json 文件的路径。</span><span class="sxs-lookup"><span data-stu-id="b99dd-119">Path to additional *deps.json* file.</span></span>

`--additionalprobingpath <PATH>`

<span data-ttu-id="b99dd-120">包含要进行探测的探测策略和程序集的路径。</span><span class="sxs-lookup"><span data-stu-id="b99dd-120">Path containing probing policy and assemblies to probe.</span></span>

`-d|--diagnostics`

<span data-ttu-id="b99dd-121">启用诊断输出。</span><span class="sxs-lookup"><span data-stu-id="b99dd-121">Enables diagnostic output.</span></span>

`--fx-version <VERSION>`

<span data-ttu-id="b99dd-122">运行应用程序所使用的已安装 .NET Core 运行时的版本。</span><span class="sxs-lookup"><span data-stu-id="b99dd-122">Version of the installed .NET Core runtime to use to run the application.</span></span>

`-h|--help`

<span data-ttu-id="b99dd-123">打印出有关命令的简短帮助。</span><span class="sxs-lookup"><span data-stu-id="b99dd-123">Prints out a short help for the command.</span></span> <span data-ttu-id="b99dd-124">如果使用 `dotnet`，还会打印可用命令的列表。</span><span class="sxs-lookup"><span data-stu-id="b99dd-124">If using with `dotnet`, it also prints a list of the available commands.</span></span>

`--info`

<span data-ttu-id="b99dd-125">打印出有关 CLI 工具和环境的详细信息，例如当前操作系统、提交该版本的 SHA 和其他信息。</span><span class="sxs-lookup"><span data-stu-id="b99dd-125">Prints out detailed information about the CLI tooling and the environment, such as the current operating system, commit SHA for the version, and other information.</span></span>

`--roll-forward-on-no-candidate-fx`

 <span data-ttu-id="b99dd-126">在没有候选共享框架的情况下前滚。</span><span class="sxs-lookup"><span data-stu-id="b99dd-126">Rolls forward on no candidate shared framework.</span></span>

`-v|--verbose`

<span data-ttu-id="b99dd-127">启用详细输出。</span><span class="sxs-lookup"><span data-stu-id="b99dd-127">Enables verbose output.</span></span>

`--version`

<span data-ttu-id="b99dd-128">打印使用中的 .NET Core SDK 版本。</span><span class="sxs-lookup"><span data-stu-id="b99dd-128">Prints out the version of the .NET Core SDK in use.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="b99dd-129">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="b99dd-129">.NET Core 1.x</span></span>](#tab/netcore1x)

`--additionalprobingpath <PATH>`

<span data-ttu-id="b99dd-130">包含要进行探测的探测策略和程序集的路径。</span><span class="sxs-lookup"><span data-stu-id="b99dd-130">Path containing probing policy and assemblies to probe.</span></span>

`-d|--diagnostics`

<span data-ttu-id="b99dd-131">启用诊断输出。</span><span class="sxs-lookup"><span data-stu-id="b99dd-131">Enables diagnostic output.</span></span>

`--fx-version <VERSION>`

<span data-ttu-id="b99dd-132">运行应用程序所使用的已安装 .NET Core 运行时的版本。</span><span class="sxs-lookup"><span data-stu-id="b99dd-132">Version of the installed .NET Core runtime to use to run the application.</span></span>

`-h|--help`

<span data-ttu-id="b99dd-133">打印出有关命令的简短帮助。</span><span class="sxs-lookup"><span data-stu-id="b99dd-133">Prints out a short help for the command.</span></span> <span data-ttu-id="b99dd-134">如果使用 `dotnet`，还会打印可用命令的列表。</span><span class="sxs-lookup"><span data-stu-id="b99dd-134">If using with `dotnet`, it also prints a list of the available commands.</span></span>

`--info`

<span data-ttu-id="b99dd-135">打印出有关 CLI 工具和环境的详细信息，例如当前操作系统、提交该版本的 SHA 和其他信息。</span><span class="sxs-lookup"><span data-stu-id="b99dd-135">Prints out detailed information about the CLI tooling and the environment, such as the current operating system, commit SHA for the version, and other information.</span></span>

`-v|--verbose`

<span data-ttu-id="b99dd-136">启用详细输出。</span><span class="sxs-lookup"><span data-stu-id="b99dd-136">Enables verbose output.</span></span>

`--version`

<span data-ttu-id="b99dd-137">打印使用中的 .NET Core SDK 版本。</span><span class="sxs-lookup"><span data-stu-id="b99dd-137">Prints out the version of the .NET Core SDK in use.</span></span>

---

## <a name="dotnet-commands"></a><span data-ttu-id="b99dd-138">dotnet 命令</span><span class="sxs-lookup"><span data-stu-id="b99dd-138">dotnet commands</span></span>

### <a name="general"></a><span data-ttu-id="b99dd-139">常规</span><span class="sxs-lookup"><span data-stu-id="b99dd-139">General</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="b99dd-140">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="b99dd-140">.NET Core 2.x</span></span>](#tab/netcore2x)

| <span data-ttu-id="b99dd-141">命令</span><span class="sxs-lookup"><span data-stu-id="b99dd-141">Command</span></span>                             | <span data-ttu-id="b99dd-142">函数</span><span class="sxs-lookup"><span data-stu-id="b99dd-142">Function</span></span>                                                            |
| ----------------------------------- | ------------------------------------------------------------------- |
| [<span data-ttu-id="b99dd-143">dotnet build</span><span class="sxs-lookup"><span data-stu-id="b99dd-143">dotnet build</span></span>](dotnet-build.md)     | <span data-ttu-id="b99dd-144">生成 .NET Core 应用程序。</span><span class="sxs-lookup"><span data-stu-id="b99dd-144">Builds a .NET Core application.</span></span>                                     |
| [<span data-ttu-id="b99dd-145">dotnet clean</span><span class="sxs-lookup"><span data-stu-id="b99dd-145">dotnet clean</span></span>](dotnet-clean.md)     | <span data-ttu-id="b99dd-146">清除生成输出。</span><span class="sxs-lookup"><span data-stu-id="b99dd-146">Clean build outputs.</span></span>                                              |
| [<span data-ttu-id="b99dd-147">dotnet help</span><span class="sxs-lookup"><span data-stu-id="b99dd-147">dotnet help</span></span>](dotnet-help.md)       | <span data-ttu-id="b99dd-148">显示命令更详细的在线文档。</span><span class="sxs-lookup"><span data-stu-id="b99dd-148">Shows more detailed documentation online for the command.</span></span>           |
| [<span data-ttu-id="b99dd-149">dotnet migrate</span><span class="sxs-lookup"><span data-stu-id="b99dd-149">dotnet migrate</span></span>](dotnet-migrate.md) | <span data-ttu-id="b99dd-150">将有效的预览版 2 项目迁移到 .NET Core SDK 1.0 项目。</span><span class="sxs-lookup"><span data-stu-id="b99dd-150">Migrates a valid Preview 2 project to a .NET Core SDK 1.0 project.</span></span>  |
| [<span data-ttu-id="b99dd-151">dotnet msbuild</span><span class="sxs-lookup"><span data-stu-id="b99dd-151">dotnet msbuild</span></span>](dotnet-msbuild.md) | <span data-ttu-id="b99dd-152">提供对 MSBuild 命令行的访问权限。</span><span class="sxs-lookup"><span data-stu-id="b99dd-152">Provides access to the MSBuild command line.</span></span>                        |
| [<span data-ttu-id="b99dd-153">dotnet new</span><span class="sxs-lookup"><span data-stu-id="b99dd-153">dotnet new</span></span>](dotnet-new.md)         | <span data-ttu-id="b99dd-154">为给定的模板初始化 C# 或 F # 项目。</span><span class="sxs-lookup"><span data-stu-id="b99dd-154">Initializes a C# or F# project for a given template.</span></span>                |
| [<span data-ttu-id="b99dd-155">dotnet pack</span><span class="sxs-lookup"><span data-stu-id="b99dd-155">dotnet pack</span></span>](dotnet-pack.md)       | <span data-ttu-id="b99dd-156">创建代码的 NuGet 包。</span><span class="sxs-lookup"><span data-stu-id="b99dd-156">Creates a NuGet package of your code.</span></span>                               |
| [<span data-ttu-id="b99dd-157">dotnet publish</span><span class="sxs-lookup"><span data-stu-id="b99dd-157">dotnet publish</span></span>](dotnet-publish.md) | <span data-ttu-id="b99dd-158">发布 .NET 依赖于框架或独立应用程序。</span><span class="sxs-lookup"><span data-stu-id="b99dd-158">Publishes a .NET framework-dependent or self-contained application.</span></span> |
| [<span data-ttu-id="b99dd-159">dotnet restore</span><span class="sxs-lookup"><span data-stu-id="b99dd-159">dotnet restore</span></span>](dotnet-restore.md) | <span data-ttu-id="b99dd-160">还原给定应用程序的依赖项。</span><span class="sxs-lookup"><span data-stu-id="b99dd-160">Restores the dependencies for a given application.</span></span>                  |
| [<span data-ttu-id="b99dd-161">dotnet run</span><span class="sxs-lookup"><span data-stu-id="b99dd-161">dotnet run</span></span>](dotnet-run.md)         | <span data-ttu-id="b99dd-162">从源运行应用程序。</span><span class="sxs-lookup"><span data-stu-id="b99dd-162">Runs the application from source.</span></span>                                   |
| [<span data-ttu-id="b99dd-163">dotnet sln</span><span class="sxs-lookup"><span data-stu-id="b99dd-163">dotnet sln</span></span>](dotnet-sln.md)         | <span data-ttu-id="b99dd-164">用于添加、删除和列出解决方案文件中项目的选项。</span><span class="sxs-lookup"><span data-stu-id="b99dd-164">Options to add, remove, and list projects in a solution file.</span></span>       |
| [<span data-ttu-id="b99dd-165">dotnet store</span><span class="sxs-lookup"><span data-stu-id="b99dd-165">dotnet store</span></span>](dotnet-store.md)     | <span data-ttu-id="b99dd-166">将程序集存储到运行时包存储区。</span><span class="sxs-lookup"><span data-stu-id="b99dd-166">Stores assemblies in the runtime package store.</span></span>                     |
| [<span data-ttu-id="b99dd-167">dotnet test</span><span class="sxs-lookup"><span data-stu-id="b99dd-167">dotnet test</span></span>](dotnet-test.md)       | <span data-ttu-id="b99dd-168">使用测试运行程序运行测试。</span><span class="sxs-lookup"><span data-stu-id="b99dd-168">Runs tests using a test runner.</span></span>                                     |

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="b99dd-169">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="b99dd-169">.NET Core 1.x</span></span>](#tab/netcore1x)

| <span data-ttu-id="b99dd-170">命令</span><span class="sxs-lookup"><span data-stu-id="b99dd-170">Command</span></span>                             | <span data-ttu-id="b99dd-171">函数</span><span class="sxs-lookup"><span data-stu-id="b99dd-171">Function</span></span>                                                            |
| ----------------------------------- | ------------------------------------------------------------------- |
| [<span data-ttu-id="b99dd-172">dotnet build</span><span class="sxs-lookup"><span data-stu-id="b99dd-172">dotnet build</span></span>](dotnet-build.md)     | <span data-ttu-id="b99dd-173">生成 .NET Core 应用程序。</span><span class="sxs-lookup"><span data-stu-id="b99dd-173">Builds a .NET Core application.</span></span>                                     |
| [<span data-ttu-id="b99dd-174">dotnet clean</span><span class="sxs-lookup"><span data-stu-id="b99dd-174">dotnet clean</span></span>](dotnet-clean.md)     | <span data-ttu-id="b99dd-175">清除生成输出。</span><span class="sxs-lookup"><span data-stu-id="b99dd-175">Clean build outputs.</span></span>                                              |
| [<span data-ttu-id="b99dd-176">dotnet migrate</span><span class="sxs-lookup"><span data-stu-id="b99dd-176">dotnet migrate</span></span>](dotnet-migrate.md) | <span data-ttu-id="b99dd-177">将有效的预览版 2 项目迁移到 .NET Core SDK 1.0 项目。</span><span class="sxs-lookup"><span data-stu-id="b99dd-177">Migrates a valid Preview 2 project to a .NET Core SDK 1.0 project.</span></span>  |
| [<span data-ttu-id="b99dd-178">dotnet msbuild</span><span class="sxs-lookup"><span data-stu-id="b99dd-178">dotnet msbuild</span></span>](dotnet-msbuild.md) | <span data-ttu-id="b99dd-179">提供对 MSBuild 命令行的访问权限。</span><span class="sxs-lookup"><span data-stu-id="b99dd-179">Provides access to the MSBuild command line.</span></span>                        |
| [<span data-ttu-id="b99dd-180">dotnet new</span><span class="sxs-lookup"><span data-stu-id="b99dd-180">dotnet new</span></span>](dotnet-new.md)         | <span data-ttu-id="b99dd-181">为给定的模板初始化 C# 或 F # 项目。</span><span class="sxs-lookup"><span data-stu-id="b99dd-181">Initializes a C# or F# project for a given template.</span></span>                |
| [<span data-ttu-id="b99dd-182">dotnet pack</span><span class="sxs-lookup"><span data-stu-id="b99dd-182">dotnet pack</span></span>](dotnet-pack.md)       | <span data-ttu-id="b99dd-183">创建代码的 NuGet 包。</span><span class="sxs-lookup"><span data-stu-id="b99dd-183">Creates a NuGet package of your code.</span></span>                               |
| [<span data-ttu-id="b99dd-184">dotnet publish</span><span class="sxs-lookup"><span data-stu-id="b99dd-184">dotnet publish</span></span>](dotnet-publish.md) | <span data-ttu-id="b99dd-185">发布 .NET 依赖于框架或独立应用程序。</span><span class="sxs-lookup"><span data-stu-id="b99dd-185">Publishes a .NET framework-dependent or self-contained application.</span></span> |
| [<span data-ttu-id="b99dd-186">dotnet restore</span><span class="sxs-lookup"><span data-stu-id="b99dd-186">dotnet restore</span></span>](dotnet-restore.md) | <span data-ttu-id="b99dd-187">还原给定应用程序的依赖项。</span><span class="sxs-lookup"><span data-stu-id="b99dd-187">Restores the dependencies for a given application.</span></span>                  |
| [<span data-ttu-id="b99dd-188">dotnet run</span><span class="sxs-lookup"><span data-stu-id="b99dd-188">dotnet run</span></span>](dotnet-run.md)         | <span data-ttu-id="b99dd-189">从源运行应用程序。</span><span class="sxs-lookup"><span data-stu-id="b99dd-189">Runs the application from source.</span></span>                                   |
| [<span data-ttu-id="b99dd-190">dotnet sln</span><span class="sxs-lookup"><span data-stu-id="b99dd-190">dotnet sln</span></span>](dotnet-sln.md)         | <span data-ttu-id="b99dd-191">用于添加、删除和列出解决方案文件中项目的选项。</span><span class="sxs-lookup"><span data-stu-id="b99dd-191">Options to add, remove, and list projects in a solution file.</span></span>       |
| [<span data-ttu-id="b99dd-192">dotnet test</span><span class="sxs-lookup"><span data-stu-id="b99dd-192">dotnet test</span></span>](dotnet-test.md)       | <span data-ttu-id="b99dd-193">使用测试运行程序运行测试。</span><span class="sxs-lookup"><span data-stu-id="b99dd-193">Runs tests using a test runner.</span></span>                                     |

---

### <a name="project-references"></a><span data-ttu-id="b99dd-194">项目引用</span><span class="sxs-lookup"><span data-stu-id="b99dd-194">Project references</span></span>

<span data-ttu-id="b99dd-195">命令</span><span class="sxs-lookup"><span data-stu-id="b99dd-195">Command</span></span> | <span data-ttu-id="b99dd-196">函数</span><span class="sxs-lookup"><span data-stu-id="b99dd-196">Function</span></span>
--- | ---
[<span data-ttu-id="b99dd-197">dotnet add reference</span><span class="sxs-lookup"><span data-stu-id="b99dd-197">dotnet add reference</span></span>](dotnet-add-reference.md) | <span data-ttu-id="b99dd-198">添加项目引用。</span><span class="sxs-lookup"><span data-stu-id="b99dd-198">Add a project reference.</span></span>
[<span data-ttu-id="b99dd-199">dotnet list reference</span><span class="sxs-lookup"><span data-stu-id="b99dd-199">dotnet list reference</span></span>](dotnet-list-reference.md) | <span data-ttu-id="b99dd-200">列出项目引用。</span><span class="sxs-lookup"><span data-stu-id="b99dd-200">List project references.</span></span>
[<span data-ttu-id="b99dd-201">dotnet remove reference</span><span class="sxs-lookup"><span data-stu-id="b99dd-201">dotnet remove reference</span></span>](dotnet-remove-reference.md) | <span data-ttu-id="b99dd-202">删除项目引用。</span><span class="sxs-lookup"><span data-stu-id="b99dd-202">Remove a project reference.</span></span>

### <a name="nuget-packages"></a><span data-ttu-id="b99dd-203">NuGet 包</span><span class="sxs-lookup"><span data-stu-id="b99dd-203">NuGet packages</span></span>

<span data-ttu-id="b99dd-204">命令</span><span class="sxs-lookup"><span data-stu-id="b99dd-204">Command</span></span> | <span data-ttu-id="b99dd-205">函数</span><span class="sxs-lookup"><span data-stu-id="b99dd-205">Function</span></span>
--- | ---
[<span data-ttu-id="b99dd-206">dotnet add package</span><span class="sxs-lookup"><span data-stu-id="b99dd-206">dotnet add package</span></span>](dotnet-add-package.md) | <span data-ttu-id="b99dd-207">添加 NuGet 包。</span><span class="sxs-lookup"><span data-stu-id="b99dd-207">Add a NuGet package.</span></span>
[<span data-ttu-id="b99dd-208">dotnet remove package</span><span class="sxs-lookup"><span data-stu-id="b99dd-208">dotnet remove package</span></span>](dotnet-remove-package.md) | <span data-ttu-id="b99dd-209">删除 NuGet 包。</span><span class="sxs-lookup"><span data-stu-id="b99dd-209">Remove a NuGet package.</span></span>

### <a name="nuget-commands"></a><span data-ttu-id="b99dd-210">NuGet 命令</span><span class="sxs-lookup"><span data-stu-id="b99dd-210">NuGet commands</span></span>

<span data-ttu-id="b99dd-211">命令</span><span class="sxs-lookup"><span data-stu-id="b99dd-211">Command</span></span> | <span data-ttu-id="b99dd-212">函数</span><span class="sxs-lookup"><span data-stu-id="b99dd-212">Function</span></span>
--- | ---
[<span data-ttu-id="b99dd-213">dotnet nuget delete</span><span class="sxs-lookup"><span data-stu-id="b99dd-213">dotnet nuget delete</span></span>](dotnet-nuget-delete.md) | <span data-ttu-id="b99dd-214">从服务器删除或取消列出包。</span><span class="sxs-lookup"><span data-stu-id="b99dd-214">Deletes or unlists a package from the server.</span></span>
[<span data-ttu-id="b99dd-215">dotnet nuget locals</span><span class="sxs-lookup"><span data-stu-id="b99dd-215">dotnet nuget locals</span></span>](dotnet-nuget-locals.md) | <span data-ttu-id="b99dd-216">清除或列出本地 NuGet 资源，例如 http 请求缓存、临时缓存或计算机范围的全局包文件夹。</span><span class="sxs-lookup"><span data-stu-id="b99dd-216">Clears or lists local NuGet resources such as http-request cache, temporary cache, or machine-wide global packages folder.</span></span>
[<span data-ttu-id="b99dd-217">dotnet nuget push</span><span class="sxs-lookup"><span data-stu-id="b99dd-217">dotnet nuget push</span></span>](dotnet-nuget-push.md) | <span data-ttu-id="b99dd-218">将包推送到服务器，并将其发布。</span><span class="sxs-lookup"><span data-stu-id="b99dd-218">Pushes a package to the server and publishes it.</span></span>

## <a name="examples"></a><span data-ttu-id="b99dd-219">示例</span><span class="sxs-lookup"><span data-stu-id="b99dd-219">Examples</span></span>

<span data-ttu-id="b99dd-220">初始化可以编译和运行的示例 .NET Core 控制台应用程序：</span><span class="sxs-lookup"><span data-stu-id="b99dd-220">Initialize a sample .NET Core console application that can be compiled and run:</span></span>

`dotnet new console`

<span data-ttu-id="b99dd-221">还原给定应用程序的依赖项：</span><span class="sxs-lookup"><span data-stu-id="b99dd-221">Restore dependencies for a given application:</span></span>

`dotnet restore`

[!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]

<span data-ttu-id="b99dd-222">生成给定目录中的项目及其依赖项：</span><span class="sxs-lookup"><span data-stu-id="b99dd-222">Build a project and its dependencies in a given directory:</span></span>

`dotnet build`

<span data-ttu-id="b99dd-223">运行名为 `myapp.dll` 的依赖于框架的应用：</span><span class="sxs-lookup"><span data-stu-id="b99dd-223">Run a framework-dependent app named `myapp.dll`:</span></span>

`dotnet myapp.dll`

## <a name="environment-variables"></a><span data-ttu-id="b99dd-224">环境变量</span><span class="sxs-lookup"><span data-stu-id="b99dd-224">Environment variables</span></span>

`DOTNET_PACKAGES`

<span data-ttu-id="b99dd-225">主包缓存。</span><span class="sxs-lookup"><span data-stu-id="b99dd-225">The primary package cache.</span></span> <span data-ttu-id="b99dd-226">如果未设置，则默认为 Unix 上的 `$HOME/.nuget/packages` 或 Windows 上的 `%HOME%\NuGet\Packages`。</span><span class="sxs-lookup"><span data-stu-id="b99dd-226">If not set, it defaults to `$HOME/.nuget/packages` on Unix or `%HOME%\NuGet\Packages` on Windows.</span></span>

`DOTNET_SERVICING`

<span data-ttu-id="b99dd-227">指定加载运行时期间共享主机要使用的服务索引的位置。</span><span class="sxs-lookup"><span data-stu-id="b99dd-227">Specifies the location of the servicing index to use by the shared host when loading the runtime.</span></span>

`DOTNET_CLI_TELEMETRY_OPTOUT`

<span data-ttu-id="b99dd-228">指定是否收集并向 Microsoft 发送 .NET Core 工具使用情况的相关数据。</span><span class="sxs-lookup"><span data-stu-id="b99dd-228">Specifies whether data about the .NET Core tools usage is collected and sent to Microsoft.</span></span> <span data-ttu-id="b99dd-229">设置为 `true` 以选择退出遥测功能（接受值 `true`、`1` 或 `yes`）；否则，设置为 `false` 以选择加入遥测功能（接受值 `false`、`0` 或 `no`）。</span><span class="sxs-lookup"><span data-stu-id="b99dd-229">Set to `true` to opt-out of the telemetry feature (values `true`, `1`, or `yes` accepted); otherwise, set to `false` to opt-in to the telemetry features (values `false`, `0`, or `no` accepted).</span></span> <span data-ttu-id="b99dd-230">如果未设置，则默认为 `false` 且遥测功能为活动状态。</span><span class="sxs-lookup"><span data-stu-id="b99dd-230">If not set, the defaults is `false`, and the telemetry feature is active.</span></span>
