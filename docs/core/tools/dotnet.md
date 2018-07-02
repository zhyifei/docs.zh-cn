---
title: dotnet 命令 - .NET Core CLI
description: 了解 dotnet 命令（.NET Core CLI 工具的通用驱动程序）及其用法。
author: mairaw
ms.author: mairaw
ms.date: 06/04/2018
ms.openlocfilehash: 788dc746705f9328683019ab3ad9836204a1ea63
ms.sourcegitcommit: fc70fcb9c789b6a4aefcdace46f3643fd076450f
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/06/2018
ms.locfileid: "34805654"
---
# <a name="dotnet-command"></a><span data-ttu-id="bee2c-103">dotnet 命令</span><span class="sxs-lookup"><span data-stu-id="bee2c-103">dotnet command</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="bee2c-104">name</span><span class="sxs-lookup"><span data-stu-id="bee2c-104">Name</span></span>

<span data-ttu-id="bee2c-105">`dotnet` - 运行命令行命令的通用驱动程序。</span><span class="sxs-lookup"><span data-stu-id="bee2c-105">`dotnet` - General driver for running the command-line commands.</span></span>

## <a name="synopsis"></a><span data-ttu-id="bee2c-106">摘要</span><span class="sxs-lookup"><span data-stu-id="bee2c-106">Synopsis</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="bee2c-107">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="bee2c-107">.NET Core 2.1</span></span>](#tab/netcore21)
```
dotnet [command] [arguments] [--additional-deps] [--additionalprobingpath] [-d|--diagnostics] [--fx-version]
    [-h|--help] [--info] [--list-runtimes] [--list-sdks] [--roll-forward-on-no-candidate-fx] [-v|--verbosity] [--version]
```
# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="bee2c-108">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="bee2c-108">.NET Core 2.0</span></span>](#tab/netcore20)
```
dotnet [command] [arguments] [--additional-deps] [--additionalprobingpath] [-d|--diagnostics]
    [--fx-version] [-h|--help] [--info] [--roll-forward-on-no-candidate-fx] [-v|--verbosity] [--version]
```
# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="bee2c-109">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="bee2c-109">.NET Core 1.x</span></span>](#tab/netcore1x)
```
dotnet [command] [arguments] [--additionalprobingpath] [-d|--diagnostics] [--fx-version]
    [-h|--help] [--info] [-v|--verbosity] [--version]
```
---

## <a name="description"></a><span data-ttu-id="bee2c-110">描述</span><span class="sxs-lookup"><span data-stu-id="bee2c-110">Description</span></span>

<span data-ttu-id="bee2c-111">`dotnet` 是用于命令行接口 (CLI) 工具链的通用驱动程序。</span><span class="sxs-lookup"><span data-stu-id="bee2c-111">`dotnet` is a generic driver for the Command Line Interface (CLI) toolchain.</span></span> <span data-ttu-id="bee2c-112">它可自行调用，并提供简短的使用说明。</span><span class="sxs-lookup"><span data-stu-id="bee2c-112">Invoked on its own, it provides brief usage instructions.</span></span>

<span data-ttu-id="bee2c-113">每种特定功能均实现为命令。</span><span class="sxs-lookup"><span data-stu-id="bee2c-113">Each specific feature is implemented as a command.</span></span> <span data-ttu-id="bee2c-114">若要使用此功能，请在 `dotnet` 后指定该命令，例如 [`dotnet build`](dotnet-build.md)。</span><span class="sxs-lookup"><span data-stu-id="bee2c-114">To use the feature, the command is specified after `dotnet`, such as [`dotnet build`](dotnet-build.md).</span></span> <span data-ttu-id="bee2c-115">该命令后的所有参数均为其自有参数。</span><span class="sxs-lookup"><span data-stu-id="bee2c-115">All of the arguments following the command are its own arguments.</span></span>

<span data-ttu-id="bee2c-116">`dotnet` 自行作为命令使用的唯一情况是运行[依赖于框架的应用](../deploying/index.md)。</span><span class="sxs-lookup"><span data-stu-id="bee2c-116">The only time `dotnet` is used as a command on its own is to run [framework-dependent apps](../deploying/index.md).</span></span> <span data-ttu-id="bee2c-117">在 `dotnet` 谓词后指定应用程序 DLL 便可执行该应用程序（例如，`dotnet myapp.dll`）。</span><span class="sxs-lookup"><span data-stu-id="bee2c-117">Specify an application DLL after the `dotnet` verb to execute the application (for example, `dotnet myapp.dll`).</span></span>

## <a name="options"></a><span data-ttu-id="bee2c-118">选项</span><span class="sxs-lookup"><span data-stu-id="bee2c-118">Options</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="bee2c-119">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="bee2c-119">.NET Core 2.1</span></span>](#tab/netcore21)

`--additional-deps <PATH>`

<span data-ttu-id="bee2c-120">其他 deps.json 文件的路径。</span><span class="sxs-lookup"><span data-stu-id="bee2c-120">Path to additional *deps.json* file.</span></span>

`--additionalprobingpath <PATH>`

<span data-ttu-id="bee2c-121">包含要进行探测的探测策略和程序集的路径。</span><span class="sxs-lookup"><span data-stu-id="bee2c-121">Path containing probing policy and assemblies to probe.</span></span>

`-d|--diagnostics`

<span data-ttu-id="bee2c-122">启用诊断输出。</span><span class="sxs-lookup"><span data-stu-id="bee2c-122">Enables diagnostic output.</span></span>

`--fx-version <VERSION>`

<span data-ttu-id="bee2c-123">运行应用程序所使用的已安装 .NET Core 运行时的版本。</span><span class="sxs-lookup"><span data-stu-id="bee2c-123">Version of the installed .NET Core runtime to use to run the application.</span></span>

`-h|--help`

<span data-ttu-id="bee2c-124">打印出有关命令的简短帮助。</span><span class="sxs-lookup"><span data-stu-id="bee2c-124">Prints out a short help for the command.</span></span> <span data-ttu-id="bee2c-125">如果使用 `dotnet`，还会打印可用命令的列表。</span><span class="sxs-lookup"><span data-stu-id="bee2c-125">If using with `dotnet`, it also prints a list of the available commands.</span></span>

`--info`

<span data-ttu-id="bee2c-126">打印出有关 CLI 工具和环境的详细信息，例如当前操作系统、提交该版本的 SHA 和其他信息。</span><span class="sxs-lookup"><span data-stu-id="bee2c-126">Prints out detailed information about the CLI tooling and the environment, such as the current operating system, commit SHA for the version, and other information.</span></span>

`--list-runtimes`

<span data-ttu-id="bee2c-127">显示已安装的 .NET Core 运行时。</span><span class="sxs-lookup"><span data-stu-id="bee2c-127">Displays the installed .NET Core runtimes.</span></span>

`--list-sdks`

<span data-ttu-id="bee2c-128">显示已安装的 .NET Core SDK。</span><span class="sxs-lookup"><span data-stu-id="bee2c-128">Displays the installed .NET Core SDKs.</span></span>

`--roll-forward-on-no-candidate-fx`

 <span data-ttu-id="bee2c-129">在没有候选共享框架的情况下前滚。</span><span class="sxs-lookup"><span data-stu-id="bee2c-129">Rolls forward on no candidate shared framework.</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="bee2c-130">设置命令的详细级别。</span><span class="sxs-lookup"><span data-stu-id="bee2c-130">Sets the verbosity level of the command.</span></span> <span data-ttu-id="bee2c-131">允许使用的值为 `q[uiet]`、`m[inimal]`、`n[ormal]`、`d[etailed]` 和 `diag[nostic]`。</span><span class="sxs-lookup"><span data-stu-id="bee2c-131">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="bee2c-132">并非在每个命令中均受支持；请参阅特定的命令页，确定此选项是否可用。</span><span class="sxs-lookup"><span data-stu-id="bee2c-132">Not supported in every command; see specific command page to determine if this option is available.</span></span>

`--version`

<span data-ttu-id="bee2c-133">打印使用中的 .NET Core SDK 版本。</span><span class="sxs-lookup"><span data-stu-id="bee2c-133">Prints out the version of the .NET Core SDK in use.</span></span>

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="bee2c-134">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="bee2c-134">.NET Core 2.0</span></span>](#tab/netcore20)

`--additional-deps <PATH>`

<span data-ttu-id="bee2c-135">其他 deps.json 文件的路径。</span><span class="sxs-lookup"><span data-stu-id="bee2c-135">Path to additional *deps.json* file.</span></span>

`--additionalprobingpath <PATH>`

<span data-ttu-id="bee2c-136">包含要进行探测的探测策略和程序集的路径。</span><span class="sxs-lookup"><span data-stu-id="bee2c-136">Path containing probing policy and assemblies to probe.</span></span>

`-d|--diagnostics`

<span data-ttu-id="bee2c-137">启用诊断输出。</span><span class="sxs-lookup"><span data-stu-id="bee2c-137">Enables diagnostic output.</span></span>

`--fx-version <VERSION>`

<span data-ttu-id="bee2c-138">运行应用程序所使用的已安装 .NET Core 运行时的版本。</span><span class="sxs-lookup"><span data-stu-id="bee2c-138">Version of the installed .NET Core runtime to use to run the application.</span></span>

`-h|--help`

<span data-ttu-id="bee2c-139">打印出有关命令的简短帮助。</span><span class="sxs-lookup"><span data-stu-id="bee2c-139">Prints out a short help for the command.</span></span> <span data-ttu-id="bee2c-140">如果使用 `dotnet`，还会打印可用命令的列表。</span><span class="sxs-lookup"><span data-stu-id="bee2c-140">If using with `dotnet`, it also prints a list of the available commands.</span></span>

`--info`

<span data-ttu-id="bee2c-141">打印出有关 CLI 工具和环境的详细信息，例如当前操作系统、提交该版本的 SHA 和其他信息。</span><span class="sxs-lookup"><span data-stu-id="bee2c-141">Prints out detailed information about the CLI tooling and the environment, such as the current operating system, commit SHA for the version, and other information.</span></span>

`--roll-forward-on-no-candidate-fx`

 <span data-ttu-id="bee2c-142">在没有候选共享框架的情况下前滚。</span><span class="sxs-lookup"><span data-stu-id="bee2c-142">Rolls forward on no candidate shared framework.</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="bee2c-143">设置命令的详细级别。</span><span class="sxs-lookup"><span data-stu-id="bee2c-143">Sets the verbosity level of the command.</span></span> <span data-ttu-id="bee2c-144">允许使用的值为 `q[uiet]`、`m[inimal]`、`n[ormal]`、`d[etailed]` 和 `diag[nostic]`。</span><span class="sxs-lookup"><span data-stu-id="bee2c-144">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="bee2c-145">并非在每个命令中均受支持；请参阅特定的命令页，确定此选项是否可用。</span><span class="sxs-lookup"><span data-stu-id="bee2c-145">Not supported in every command; see specific command page to determine if this option is available.</span></span>

`--version`

<span data-ttu-id="bee2c-146">打印使用中的 .NET Core SDK 版本。</span><span class="sxs-lookup"><span data-stu-id="bee2c-146">Prints out the version of the .NET Core SDK in use.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="bee2c-147">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="bee2c-147">.NET Core 1.x</span></span>](#tab/netcore1x)

`--additionalprobingpath <PATH>`

<span data-ttu-id="bee2c-148">包含要进行探测的探测策略和程序集的路径。</span><span class="sxs-lookup"><span data-stu-id="bee2c-148">Path containing probing policy and assemblies to probe.</span></span>

`-d|--diagnostics`

<span data-ttu-id="bee2c-149">启用诊断输出。</span><span class="sxs-lookup"><span data-stu-id="bee2c-149">Enables diagnostic output.</span></span>

`--fx-version <VERSION>`

<span data-ttu-id="bee2c-150">运行应用程序所使用的已安装 .NET Core 运行时的版本。</span><span class="sxs-lookup"><span data-stu-id="bee2c-150">Version of the installed .NET Core runtime to use to run the application.</span></span>

`-h|--help`

<span data-ttu-id="bee2c-151">打印出有关命令的简短帮助。</span><span class="sxs-lookup"><span data-stu-id="bee2c-151">Prints out a short help for the command.</span></span> <span data-ttu-id="bee2c-152">如果使用 `dotnet`，还会打印可用命令的列表。</span><span class="sxs-lookup"><span data-stu-id="bee2c-152">If using with `dotnet`, it also prints a list of the available commands.</span></span>

`--info`

<span data-ttu-id="bee2c-153">打印出有关 CLI 工具和环境的详细信息，例如当前操作系统、提交该版本的 SHA 和其他信息。</span><span class="sxs-lookup"><span data-stu-id="bee2c-153">Prints out detailed information about the CLI tooling and the environment, such as the current operating system, commit SHA for the version, and other information.</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="bee2c-154">设置命令的详细级别。</span><span class="sxs-lookup"><span data-stu-id="bee2c-154">Sets the verbosity level of the command.</span></span> <span data-ttu-id="bee2c-155">允许使用的值为 `q[uiet]`、`m[inimal]`、`n[ormal]`、`d[etailed]` 和 `diag[nostic]`。</span><span class="sxs-lookup"><span data-stu-id="bee2c-155">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="bee2c-156">并非在每个命令中均受支持；请参阅特定的命令页，确定此选项是否可用。</span><span class="sxs-lookup"><span data-stu-id="bee2c-156">Not supported in every command; see specific command page to determine if this option is available.</span></span>

`--version`

<span data-ttu-id="bee2c-157">打印使用中的 .NET Core SDK 版本。</span><span class="sxs-lookup"><span data-stu-id="bee2c-157">Prints out the version of the .NET Core SDK in use.</span></span>

---

## <a name="dotnet-commands"></a><span data-ttu-id="bee2c-158">dotnet 命令</span><span class="sxs-lookup"><span data-stu-id="bee2c-158">dotnet commands</span></span>

### <a name="general"></a><span data-ttu-id="bee2c-159">常规</span><span class="sxs-lookup"><span data-stu-id="bee2c-159">General</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="bee2c-160">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="bee2c-160">.NET Core 2.1</span></span>](#tab/netcore21)

| <span data-ttu-id="bee2c-161">命令</span><span class="sxs-lookup"><span data-stu-id="bee2c-161">Command</span></span>                                       | <span data-ttu-id="bee2c-162">函数</span><span class="sxs-lookup"><span data-stu-id="bee2c-162">Function</span></span>                                                            |
| --------------------------------------------- | ------------------------------------------------------------------- |
| [<span data-ttu-id="bee2c-163">dotnet build</span><span class="sxs-lookup"><span data-stu-id="bee2c-163">dotnet build</span></span>](dotnet-build.md)               | <span data-ttu-id="bee2c-164">生成 .NET Core 应用程序。</span><span class="sxs-lookup"><span data-stu-id="bee2c-164">Builds a .NET Core application.</span></span>                                     |
| [<span data-ttu-id="bee2c-165">dotnet build-server</span><span class="sxs-lookup"><span data-stu-id="bee2c-165">dotnet build-server</span></span>](dotnet-build-server.md) | <span data-ttu-id="bee2c-166">与通过生成启动的服务器进行交互。</span><span class="sxs-lookup"><span data-stu-id="bee2c-166">Interacts with servers started by a build.</span></span>                          |
| [<span data-ttu-id="bee2c-167">dotnet clean</span><span class="sxs-lookup"><span data-stu-id="bee2c-167">dotnet clean</span></span>](dotnet-clean.md)               | <span data-ttu-id="bee2c-168">清除生成输出。</span><span class="sxs-lookup"><span data-stu-id="bee2c-168">Clean build outputs.</span></span>                                                |
| [<span data-ttu-id="bee2c-169">dotnet help</span><span class="sxs-lookup"><span data-stu-id="bee2c-169">dotnet help</span></span>](dotnet-help.md)                 | <span data-ttu-id="bee2c-170">显示命令更详细的在线文档。</span><span class="sxs-lookup"><span data-stu-id="bee2c-170">Shows more detailed documentation online for the command.</span></span>           |
| [<span data-ttu-id="bee2c-171">dotnet migrate</span><span class="sxs-lookup"><span data-stu-id="bee2c-171">dotnet migrate</span></span>](dotnet-migrate.md)           | <span data-ttu-id="bee2c-172">将有效的预览版 2 项目迁移到 .NET Core SDK 1.0 项目。</span><span class="sxs-lookup"><span data-stu-id="bee2c-172">Migrates a valid Preview 2 project to a .NET Core SDK 1.0 project.</span></span>  |
| [<span data-ttu-id="bee2c-173">dotnet msbuild</span><span class="sxs-lookup"><span data-stu-id="bee2c-173">dotnet msbuild</span></span>](dotnet-msbuild.md)           | <span data-ttu-id="bee2c-174">提供对 MSBuild 命令行的访问权限。</span><span class="sxs-lookup"><span data-stu-id="bee2c-174">Provides access to the MSBuild command line.</span></span>                        |
| [<span data-ttu-id="bee2c-175">dotnet new</span><span class="sxs-lookup"><span data-stu-id="bee2c-175">dotnet new</span></span>](dotnet-new.md)                   | <span data-ttu-id="bee2c-176">为给定的模板初始化 C# 或 F # 项目。</span><span class="sxs-lookup"><span data-stu-id="bee2c-176">Initializes a C# or F# project for a given template.</span></span>                |
| [<span data-ttu-id="bee2c-177">dotnet pack</span><span class="sxs-lookup"><span data-stu-id="bee2c-177">dotnet pack</span></span>](dotnet-pack.md)                 | <span data-ttu-id="bee2c-178">创建代码的 NuGet 包。</span><span class="sxs-lookup"><span data-stu-id="bee2c-178">Creates a NuGet package of your code.</span></span>                               |
| [<span data-ttu-id="bee2c-179">dotnet publish</span><span class="sxs-lookup"><span data-stu-id="bee2c-179">dotnet publish</span></span>](dotnet-publish.md)           | <span data-ttu-id="bee2c-180">发布 .NET 依赖于框架或独立应用程序。</span><span class="sxs-lookup"><span data-stu-id="bee2c-180">Publishes a .NET framework-dependent or self-contained application.</span></span> |
| [<span data-ttu-id="bee2c-181">dotnet restore</span><span class="sxs-lookup"><span data-stu-id="bee2c-181">dotnet restore</span></span>](dotnet-restore.md)           | <span data-ttu-id="bee2c-182">还原给定应用程序的依赖项。</span><span class="sxs-lookup"><span data-stu-id="bee2c-182">Restores the dependencies for a given application.</span></span>                  |
| [<span data-ttu-id="bee2c-183">dotnet run</span><span class="sxs-lookup"><span data-stu-id="bee2c-183">dotnet run</span></span>](dotnet-run.md)                   | <span data-ttu-id="bee2c-184">从源运行应用程序。</span><span class="sxs-lookup"><span data-stu-id="bee2c-184">Runs the application from source.</span></span>                                   |
| [<span data-ttu-id="bee2c-185">dotnet sln</span><span class="sxs-lookup"><span data-stu-id="bee2c-185">dotnet sln</span></span>](dotnet-sln.md)                   | <span data-ttu-id="bee2c-186">用于添加、删除和列出解决方案文件中项目的选项。</span><span class="sxs-lookup"><span data-stu-id="bee2c-186">Options to add, remove, and list projects in a solution file.</span></span>       |
| [<span data-ttu-id="bee2c-187">dotnet store</span><span class="sxs-lookup"><span data-stu-id="bee2c-187">dotnet store</span></span>](dotnet-store.md)               | <span data-ttu-id="bee2c-188">将程序集存储到运行时包存储区。</span><span class="sxs-lookup"><span data-stu-id="bee2c-188">Stores assemblies in the runtime package store.</span></span>                     |
| [<span data-ttu-id="bee2c-189">dotnet test</span><span class="sxs-lookup"><span data-stu-id="bee2c-189">dotnet test</span></span>](dotnet-test.md)                 | <span data-ttu-id="bee2c-190">使用测试运行程序运行测试。</span><span class="sxs-lookup"><span data-stu-id="bee2c-190">Runs tests using a test runner.</span></span>                                     |

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="bee2c-191">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="bee2c-191">.NET Core 2.0</span></span>](#tab/netcore20)

| <span data-ttu-id="bee2c-192">命令</span><span class="sxs-lookup"><span data-stu-id="bee2c-192">Command</span></span>                             | <span data-ttu-id="bee2c-193">函数</span><span class="sxs-lookup"><span data-stu-id="bee2c-193">Function</span></span>                                                            |
| ----------------------------------- | ------------------------------------------------------------------- |
| [<span data-ttu-id="bee2c-194">dotnet build</span><span class="sxs-lookup"><span data-stu-id="bee2c-194">dotnet build</span></span>](dotnet-build.md)     | <span data-ttu-id="bee2c-195">生成 .NET Core 应用程序。</span><span class="sxs-lookup"><span data-stu-id="bee2c-195">Builds a .NET Core application.</span></span>                                     |
| [<span data-ttu-id="bee2c-196">dotnet clean</span><span class="sxs-lookup"><span data-stu-id="bee2c-196">dotnet clean</span></span>](dotnet-clean.md)     | <span data-ttu-id="bee2c-197">清除生成输出。</span><span class="sxs-lookup"><span data-stu-id="bee2c-197">Clean build outputs.</span></span>                                              |
| [<span data-ttu-id="bee2c-198">dotnet help</span><span class="sxs-lookup"><span data-stu-id="bee2c-198">dotnet help</span></span>](dotnet-help.md)       | <span data-ttu-id="bee2c-199">显示命令更详细的在线文档。</span><span class="sxs-lookup"><span data-stu-id="bee2c-199">Shows more detailed documentation online for the command.</span></span>           |
| [<span data-ttu-id="bee2c-200">dotnet migrate</span><span class="sxs-lookup"><span data-stu-id="bee2c-200">dotnet migrate</span></span>](dotnet-migrate.md) | <span data-ttu-id="bee2c-201">将有效的预览版 2 项目迁移到 .NET Core SDK 1.0 项目。</span><span class="sxs-lookup"><span data-stu-id="bee2c-201">Migrates a valid Preview 2 project to a .NET Core SDK 1.0 project.</span></span>  |
| [<span data-ttu-id="bee2c-202">dotnet msbuild</span><span class="sxs-lookup"><span data-stu-id="bee2c-202">dotnet msbuild</span></span>](dotnet-msbuild.md) | <span data-ttu-id="bee2c-203">提供对 MSBuild 命令行的访问权限。</span><span class="sxs-lookup"><span data-stu-id="bee2c-203">Provides access to the MSBuild command line.</span></span>                        |
| [<span data-ttu-id="bee2c-204">dotnet new</span><span class="sxs-lookup"><span data-stu-id="bee2c-204">dotnet new</span></span>](dotnet-new.md)         | <span data-ttu-id="bee2c-205">为给定的模板初始化 C# 或 F # 项目。</span><span class="sxs-lookup"><span data-stu-id="bee2c-205">Initializes a C# or F# project for a given template.</span></span>                |
| [<span data-ttu-id="bee2c-206">dotnet pack</span><span class="sxs-lookup"><span data-stu-id="bee2c-206">dotnet pack</span></span>](dotnet-pack.md)       | <span data-ttu-id="bee2c-207">创建代码的 NuGet 包。</span><span class="sxs-lookup"><span data-stu-id="bee2c-207">Creates a NuGet package of your code.</span></span>                               |
| [<span data-ttu-id="bee2c-208">dotnet publish</span><span class="sxs-lookup"><span data-stu-id="bee2c-208">dotnet publish</span></span>](dotnet-publish.md) | <span data-ttu-id="bee2c-209">发布 .NET 依赖于框架或独立应用程序。</span><span class="sxs-lookup"><span data-stu-id="bee2c-209">Publishes a .NET framework-dependent or self-contained application.</span></span> |
| [<span data-ttu-id="bee2c-210">dotnet restore</span><span class="sxs-lookup"><span data-stu-id="bee2c-210">dotnet restore</span></span>](dotnet-restore.md) | <span data-ttu-id="bee2c-211">还原给定应用程序的依赖项。</span><span class="sxs-lookup"><span data-stu-id="bee2c-211">Restores the dependencies for a given application.</span></span>                  |
| [<span data-ttu-id="bee2c-212">dotnet run</span><span class="sxs-lookup"><span data-stu-id="bee2c-212">dotnet run</span></span>](dotnet-run.md)         | <span data-ttu-id="bee2c-213">从源运行应用程序。</span><span class="sxs-lookup"><span data-stu-id="bee2c-213">Runs the application from source.</span></span>                                   |
| [<span data-ttu-id="bee2c-214">dotnet sln</span><span class="sxs-lookup"><span data-stu-id="bee2c-214">dotnet sln</span></span>](dotnet-sln.md)         | <span data-ttu-id="bee2c-215">用于添加、删除和列出解决方案文件中项目的选项。</span><span class="sxs-lookup"><span data-stu-id="bee2c-215">Options to add, remove, and list projects in a solution file.</span></span>       |
| [<span data-ttu-id="bee2c-216">dotnet store</span><span class="sxs-lookup"><span data-stu-id="bee2c-216">dotnet store</span></span>](dotnet-store.md)     | <span data-ttu-id="bee2c-217">将程序集存储到运行时包存储区。</span><span class="sxs-lookup"><span data-stu-id="bee2c-217">Stores assemblies in the runtime package store.</span></span>                     |
| [<span data-ttu-id="bee2c-218">dotnet test</span><span class="sxs-lookup"><span data-stu-id="bee2c-218">dotnet test</span></span>](dotnet-test.md)       | <span data-ttu-id="bee2c-219">使用测试运行程序运行测试。</span><span class="sxs-lookup"><span data-stu-id="bee2c-219">Runs tests using a test runner.</span></span>                                     |

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="bee2c-220">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="bee2c-220">.NET Core 1.x</span></span>](#tab/netcore1x)

| <span data-ttu-id="bee2c-221">命令</span><span class="sxs-lookup"><span data-stu-id="bee2c-221">Command</span></span>                             | <span data-ttu-id="bee2c-222">函数</span><span class="sxs-lookup"><span data-stu-id="bee2c-222">Function</span></span>                                                            |
| ----------------------------------- | ------------------------------------------------------------------- |
| [<span data-ttu-id="bee2c-223">dotnet build</span><span class="sxs-lookup"><span data-stu-id="bee2c-223">dotnet build</span></span>](dotnet-build.md)     | <span data-ttu-id="bee2c-224">生成 .NET Core 应用程序。</span><span class="sxs-lookup"><span data-stu-id="bee2c-224">Builds a .NET Core application.</span></span>                                     |
| [<span data-ttu-id="bee2c-225">dotnet clean</span><span class="sxs-lookup"><span data-stu-id="bee2c-225">dotnet clean</span></span>](dotnet-clean.md)     | <span data-ttu-id="bee2c-226">清除生成输出。</span><span class="sxs-lookup"><span data-stu-id="bee2c-226">Clean build outputs.</span></span>                                              |
| [<span data-ttu-id="bee2c-227">dotnet migrate</span><span class="sxs-lookup"><span data-stu-id="bee2c-227">dotnet migrate</span></span>](dotnet-migrate.md) | <span data-ttu-id="bee2c-228">将有效的预览版 2 项目迁移到 .NET Core SDK 1.0 项目。</span><span class="sxs-lookup"><span data-stu-id="bee2c-228">Migrates a valid Preview 2 project to a .NET Core SDK 1.0 project.</span></span>  |
| [<span data-ttu-id="bee2c-229">dotnet msbuild</span><span class="sxs-lookup"><span data-stu-id="bee2c-229">dotnet msbuild</span></span>](dotnet-msbuild.md) | <span data-ttu-id="bee2c-230">提供对 MSBuild 命令行的访问权限。</span><span class="sxs-lookup"><span data-stu-id="bee2c-230">Provides access to the MSBuild command line.</span></span>                        |
| [<span data-ttu-id="bee2c-231">dotnet new</span><span class="sxs-lookup"><span data-stu-id="bee2c-231">dotnet new</span></span>](dotnet-new.md)         | <span data-ttu-id="bee2c-232">为给定的模板初始化 C# 或 F # 项目。</span><span class="sxs-lookup"><span data-stu-id="bee2c-232">Initializes a C# or F# project for a given template.</span></span>                |
| [<span data-ttu-id="bee2c-233">dotnet pack</span><span class="sxs-lookup"><span data-stu-id="bee2c-233">dotnet pack</span></span>](dotnet-pack.md)       | <span data-ttu-id="bee2c-234">创建代码的 NuGet 包。</span><span class="sxs-lookup"><span data-stu-id="bee2c-234">Creates a NuGet package of your code.</span></span>                               |
| [<span data-ttu-id="bee2c-235">dotnet publish</span><span class="sxs-lookup"><span data-stu-id="bee2c-235">dotnet publish</span></span>](dotnet-publish.md) | <span data-ttu-id="bee2c-236">发布 .NET 依赖于框架或独立应用程序。</span><span class="sxs-lookup"><span data-stu-id="bee2c-236">Publishes a .NET framework-dependent or self-contained application.</span></span> |
| [<span data-ttu-id="bee2c-237">dotnet restore</span><span class="sxs-lookup"><span data-stu-id="bee2c-237">dotnet restore</span></span>](dotnet-restore.md) | <span data-ttu-id="bee2c-238">还原给定应用程序的依赖项。</span><span class="sxs-lookup"><span data-stu-id="bee2c-238">Restores the dependencies for a given application.</span></span>                  |
| [<span data-ttu-id="bee2c-239">dotnet run</span><span class="sxs-lookup"><span data-stu-id="bee2c-239">dotnet run</span></span>](dotnet-run.md)         | <span data-ttu-id="bee2c-240">从源运行应用程序。</span><span class="sxs-lookup"><span data-stu-id="bee2c-240">Runs the application from source.</span></span>                                   |
| [<span data-ttu-id="bee2c-241">dotnet sln</span><span class="sxs-lookup"><span data-stu-id="bee2c-241">dotnet sln</span></span>](dotnet-sln.md)         | <span data-ttu-id="bee2c-242">用于添加、删除和列出解决方案文件中项目的选项。</span><span class="sxs-lookup"><span data-stu-id="bee2c-242">Options to add, remove, and list projects in a solution file.</span></span>       |
| [<span data-ttu-id="bee2c-243">dotnet test</span><span class="sxs-lookup"><span data-stu-id="bee2c-243">dotnet test</span></span>](dotnet-test.md)       | <span data-ttu-id="bee2c-244">使用测试运行程序运行测试。</span><span class="sxs-lookup"><span data-stu-id="bee2c-244">Runs tests using a test runner.</span></span>                                     |

---

### <a name="project-references"></a><span data-ttu-id="bee2c-245">项目引用</span><span class="sxs-lookup"><span data-stu-id="bee2c-245">Project references</span></span>

<span data-ttu-id="bee2c-246">命令</span><span class="sxs-lookup"><span data-stu-id="bee2c-246">Command</span></span> | <span data-ttu-id="bee2c-247">函数</span><span class="sxs-lookup"><span data-stu-id="bee2c-247">Function</span></span>
--- | ---
[<span data-ttu-id="bee2c-248">dotnet add reference</span><span class="sxs-lookup"><span data-stu-id="bee2c-248">dotnet add reference</span></span>](dotnet-add-reference.md) | <span data-ttu-id="bee2c-249">添加项目引用。</span><span class="sxs-lookup"><span data-stu-id="bee2c-249">Adds a project reference.</span></span>
[<span data-ttu-id="bee2c-250">dotnet list reference</span><span class="sxs-lookup"><span data-stu-id="bee2c-250">dotnet list reference</span></span>](dotnet-list-reference.md) | <span data-ttu-id="bee2c-251">列出项目引用。</span><span class="sxs-lookup"><span data-stu-id="bee2c-251">Lists project references.</span></span>
[<span data-ttu-id="bee2c-252">dotnet remove reference</span><span class="sxs-lookup"><span data-stu-id="bee2c-252">dotnet remove reference</span></span>](dotnet-remove-reference.md) | <span data-ttu-id="bee2c-253">删除项目引用。</span><span class="sxs-lookup"><span data-stu-id="bee2c-253">Removes a project reference.</span></span>

### <a name="nuget-packages"></a><span data-ttu-id="bee2c-254">NuGet 包</span><span class="sxs-lookup"><span data-stu-id="bee2c-254">NuGet packages</span></span>

<span data-ttu-id="bee2c-255">命令</span><span class="sxs-lookup"><span data-stu-id="bee2c-255">Command</span></span> | <span data-ttu-id="bee2c-256">函数</span><span class="sxs-lookup"><span data-stu-id="bee2c-256">Function</span></span>
--- | ---
[<span data-ttu-id="bee2c-257">dotnet add package</span><span class="sxs-lookup"><span data-stu-id="bee2c-257">dotnet add package</span></span>](dotnet-add-package.md) | <span data-ttu-id="bee2c-258">添加 NuGet 包。</span><span class="sxs-lookup"><span data-stu-id="bee2c-258">Adds a NuGet package.</span></span>
[<span data-ttu-id="bee2c-259">dotnet remove package</span><span class="sxs-lookup"><span data-stu-id="bee2c-259">dotnet remove package</span></span>](dotnet-remove-package.md) | <span data-ttu-id="bee2c-260">删除 NuGet 包。</span><span class="sxs-lookup"><span data-stu-id="bee2c-260">Removes a NuGet package.</span></span>

### <a name="nuget-commands"></a><span data-ttu-id="bee2c-261">NuGet 命令</span><span class="sxs-lookup"><span data-stu-id="bee2c-261">NuGet commands</span></span>

<span data-ttu-id="bee2c-262">命令</span><span class="sxs-lookup"><span data-stu-id="bee2c-262">Command</span></span> | <span data-ttu-id="bee2c-263">函数</span><span class="sxs-lookup"><span data-stu-id="bee2c-263">Function</span></span>
--- | ---
[<span data-ttu-id="bee2c-264">dotnet nuget delete</span><span class="sxs-lookup"><span data-stu-id="bee2c-264">dotnet nuget delete</span></span>](dotnet-nuget-delete.md) | <span data-ttu-id="bee2c-265">从服务器删除或取消列出包。</span><span class="sxs-lookup"><span data-stu-id="bee2c-265">Deletes or unlists a package from the server.</span></span>
[<span data-ttu-id="bee2c-266">dotnet nuget locals</span><span class="sxs-lookup"><span data-stu-id="bee2c-266">dotnet nuget locals</span></span>](dotnet-nuget-locals.md) | <span data-ttu-id="bee2c-267">清除或列出本地 NuGet 资源，例如 http 请求缓存、临时缓存或计算机范围的全局包文件夹。</span><span class="sxs-lookup"><span data-stu-id="bee2c-267">Clears or lists local NuGet resources such as http-request cache, temporary cache, or machine-wide global packages folder.</span></span>
[<span data-ttu-id="bee2c-268">dotnet nuget push</span><span class="sxs-lookup"><span data-stu-id="bee2c-268">dotnet nuget push</span></span>](dotnet-nuget-push.md) | <span data-ttu-id="bee2c-269">将包推送到服务器，并将其发布。</span><span class="sxs-lookup"><span data-stu-id="bee2c-269">Pushes a package to the server and publishes it.</span></span>

### <a name="global-tools-commands"></a><span data-ttu-id="bee2c-270">全局工具命令</span><span class="sxs-lookup"><span data-stu-id="bee2c-270">Global Tools commands</span></span>

<span data-ttu-id="bee2c-271">[.NET Core 全局工具](global-tools.md)可与 .NET Core SDK 2.1.300 一起开始使用：</span><span class="sxs-lookup"><span data-stu-id="bee2c-271">[.NET Core Global Tools](global-tools.md) are available starting with .NET Core SDK 2.1.300:</span></span>

<span data-ttu-id="bee2c-272">命令</span><span class="sxs-lookup"><span data-stu-id="bee2c-272">Command</span></span> | <span data-ttu-id="bee2c-273">函数</span><span class="sxs-lookup"><span data-stu-id="bee2c-273">Function</span></span>
--- | ---
[<span data-ttu-id="bee2c-274">dotnet tool install</span><span class="sxs-lookup"><span data-stu-id="bee2c-274">dotnet tool install</span></span>](dotnet-tool-install.md) | <span data-ttu-id="bee2c-275">在计算机上安装全局工具。</span><span class="sxs-lookup"><span data-stu-id="bee2c-275">Installs a Global Tool on your machine.</span></span>
[<span data-ttu-id="bee2c-276">dotnet tool list</span><span class="sxs-lookup"><span data-stu-id="bee2c-276">dotnet tool list</span></span>](dotnet-tool-list.md) | <span data-ttu-id="bee2c-277">列出当前安装在计算机上的默认目录中或指定路径中的所有全局工具。</span><span class="sxs-lookup"><span data-stu-id="bee2c-277">Lists all Global Tools currently installed in the default directory on your machine or in the specified path.</span></span>
[<span data-ttu-id="bee2c-278">dotnet tool uninstall</span><span class="sxs-lookup"><span data-stu-id="bee2c-278">dotnet tool uninstall</span></span>](dotnet-tool-uninstall.md) | <span data-ttu-id="bee2c-279">从计算机中卸载全局工具。</span><span class="sxs-lookup"><span data-stu-id="bee2c-279">Uninstalls a Global Tool from your machine.</span></span>
[<span data-ttu-id="bee2c-280">dotnet tool update</span><span class="sxs-lookup"><span data-stu-id="bee2c-280">dotnet tool update</span></span>](dotnet-tool-update.md) | <span data-ttu-id="bee2c-281">在计算机上更新全局工具。</span><span class="sxs-lookup"><span data-stu-id="bee2c-281">Updates a Global Tool on your machine.</span></span>

### <a name="additional-tools"></a><span data-ttu-id="bee2c-282">其他工具</span><span class="sxs-lookup"><span data-stu-id="bee2c-282">Additional tools</span></span>

<span data-ttu-id="bee2c-283">自 .NET Core SDK 2.1.300 开始，许多使用 `DotnetCliToolReference` 的仅在每个项目的基础上可用的工具现作为 .NET Core SDK 的一部分提供。</span><span class="sxs-lookup"><span data-stu-id="bee2c-283">Starting with .NET Core SDK 2.1.300, a number of tools that were available only on a per project basis using `DotnetCliToolReference` are now available as part of the .NET Core SDK.</span></span> <span data-ttu-id="bee2c-284">这些工具包括：</span><span class="sxs-lookup"><span data-stu-id="bee2c-284">These tools include:</span></span>

| <span data-ttu-id="bee2c-285">工具</span><span class="sxs-lookup"><span data-stu-id="bee2c-285">Tool</span></span>                                              | <span data-ttu-id="bee2c-286">函数</span><span class="sxs-lookup"><span data-stu-id="bee2c-286">Function</span></span>                                                     |
| ------------------------------------------------- | ------------------------------------------------------------ |
| <span data-ttu-id="bee2c-287">dev-certs</span><span class="sxs-lookup"><span data-stu-id="bee2c-287">dev-certs</span></span>                                         | <span data-ttu-id="bee2c-288">创建和管理开发证书。</span><span class="sxs-lookup"><span data-stu-id="bee2c-288">Creates and manages development certificates.</span></span>                |
| [<span data-ttu-id="bee2c-289">ef</span><span class="sxs-lookup"><span data-stu-id="bee2c-289">ef</span></span>](/ef/core/miscellaneous/cli/dotnet)           | <span data-ttu-id="bee2c-290">Entity Framework Core 命令行工具。</span><span class="sxs-lookup"><span data-stu-id="bee2c-290">Entity Framework Core command-line tools.</span></span>                    |
| <span data-ttu-id="bee2c-291">sql-cache</span><span class="sxs-lookup"><span data-stu-id="bee2c-291">sql-cache</span></span>                                         | <span data-ttu-id="bee2c-292">SQL Server 缓存命令行工具。</span><span class="sxs-lookup"><span data-stu-id="bee2c-292">SQL Server cache command-line tools.</span></span>                         |
| [<span data-ttu-id="bee2c-293">user-secrets</span><span class="sxs-lookup"><span data-stu-id="bee2c-293">user-secrets</span></span>](/aspnet/core/security/app-secrets) | <span data-ttu-id="bee2c-294">管理开发用户机密。</span><span class="sxs-lookup"><span data-stu-id="bee2c-294">Manages development user secrets.</span></span>                            |
| [<span data-ttu-id="bee2c-295">watch</span><span class="sxs-lookup"><span data-stu-id="bee2c-295">watch</span></span>](/aspnet/core/tutorials/dotnet-watch)      | <span data-ttu-id="bee2c-296">启动文件观察程序，以在更改文件时运行命令。</span><span class="sxs-lookup"><span data-stu-id="bee2c-296">Starts a file watcher that runs a command when files change.</span></span> |

<span data-ttu-id="bee2c-297">有关每个工具的更多信息，请执行 `dotnet <tool-name> --help`。</span><span class="sxs-lookup"><span data-stu-id="bee2c-297">For more information about each tool, execute `dotnet <tool-name> --help`.</span></span>

## <a name="examples"></a><span data-ttu-id="bee2c-298">示例</span><span class="sxs-lookup"><span data-stu-id="bee2c-298">Examples</span></span>

<span data-ttu-id="bee2c-299">创建新的 .NET Core 控制台应用程序：</span><span class="sxs-lookup"><span data-stu-id="bee2c-299">Creates a new .NET Core console application:</span></span>

`dotnet new console`

<span data-ttu-id="bee2c-300">还原给定应用程序的依赖项：</span><span class="sxs-lookup"><span data-stu-id="bee2c-300">Restore dependencies for a given application:</span></span>

`dotnet restore`

[!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]

<span data-ttu-id="bee2c-301">生成给定目录中的项目及其依赖项：</span><span class="sxs-lookup"><span data-stu-id="bee2c-301">Build a project and its dependencies in a given directory:</span></span>

`dotnet build`

<span data-ttu-id="bee2c-302">运行名为 `myapp.dll` 的依赖于框架的应用：</span><span class="sxs-lookup"><span data-stu-id="bee2c-302">Run a framework-dependent app named `myapp.dll`:</span></span>

`dotnet myapp.dll`

## <a name="environment-variables"></a><span data-ttu-id="bee2c-303">环境变量</span><span class="sxs-lookup"><span data-stu-id="bee2c-303">Environment variables</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="bee2c-304">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="bee2c-304">.NET Core 2.1</span></span>](#tab/netcore21)

`DOTNET_PACKAGES`

<span data-ttu-id="bee2c-305">主包缓存。</span><span class="sxs-lookup"><span data-stu-id="bee2c-305">The primary package cache.</span></span> <span data-ttu-id="bee2c-306">如果未设置，则默认为 Unix 上的 `$HOME/.nuget/packages` 或 Windows 上的 `%HOME%\NuGet\Packages`。</span><span class="sxs-lookup"><span data-stu-id="bee2c-306">If not set, it defaults to `$HOME/.nuget/packages` on Unix or `%HOME%\NuGet\Packages` on Windows.</span></span>

`DOTNET_SERVICING`

<span data-ttu-id="bee2c-307">指定加载运行时期间共享主机要使用的服务索引的位置。</span><span class="sxs-lookup"><span data-stu-id="bee2c-307">Specifies the location of the servicing index to use by the shared host when loading the runtime.</span></span>

`DOTNET_CLI_TELEMETRY_OPTOUT`

<span data-ttu-id="bee2c-308">指定是否收集并向 Microsoft 发送 .NET Core 工具使用情况的相关数据。</span><span class="sxs-lookup"><span data-stu-id="bee2c-308">Specifies whether data about the .NET Core tools usage is collected and sent to Microsoft.</span></span> <span data-ttu-id="bee2c-309">设置为 `true` 以选择退出遥测功能（接受的值为 `true`、`1` 或 `yes`）。</span><span class="sxs-lookup"><span data-stu-id="bee2c-309">Set to `true` to opt-out of the telemetry feature (values `true`, `1`, or `yes` accepted).</span></span> <span data-ttu-id="bee2c-310">否则，设置为 `false` 以选择加入遥测功能（接受的值为 `false`、`0` 或 `no`）。</span><span class="sxs-lookup"><span data-stu-id="bee2c-310">Otherwise, set to `false` to opt into the telemetry features (values `false`, `0`, or `no` accepted).</span></span> <span data-ttu-id="bee2c-311">如果未设置，则默认为 `false` 且遥测功能为活动状态。</span><span class="sxs-lookup"><span data-stu-id="bee2c-311">If not set, the default is `false` and the telemetry feature is active.</span></span>

`DOTNET_MULTILEVEL_LOOKUP`

<span data-ttu-id="bee2c-312">指定是否从全局位置解析 .NET Core 运行时、共享框架或 SDK。</span><span class="sxs-lookup"><span data-stu-id="bee2c-312">Specifies whether .NET Core runtime, shared framework, or SDK are resolved from the global location.</span></span> <span data-ttu-id="bee2c-313">如果未设置，则默认为 `true`。</span><span class="sxs-lookup"><span data-stu-id="bee2c-313">If not set, it defaults to `true`.</span></span> <span data-ttu-id="bee2c-314">设置为 `false` 不从全局位置解析，并且具有独立的 .NET Core 安装（接受的值为 `0` 或 `false`）。</span><span class="sxs-lookup"><span data-stu-id="bee2c-314">Set to `false` to not resolve from the global location and have isolated .NET Core installations (values `0` or `false` are accepted).</span></span> <span data-ttu-id="bee2c-315">有关多级别查找的详细信息，请参阅 [Multi-level SharedFX Lookup](https://github.com/dotnet/core-setup/blob/master/Documentation/design-docs/multilevel-sharedfx-lookup.md)（多级别 SharedFX 查找）。</span><span class="sxs-lookup"><span data-stu-id="bee2c-315">For more information about multi-level lookup, see [Multi-level SharedFX Lookup](https://github.com/dotnet/core-setup/blob/master/Documentation/design-docs/multilevel-sharedfx-lookup.md).</span></span>

`DOTNET_ROLL_FORWARD_ON_NO_CANDIDATE_FX`

<span data-ttu-id="bee2c-316">禁用次要版本前滚。</span><span class="sxs-lookup"><span data-stu-id="bee2c-316">Disables minor version roll forward.</span></span> <span data-ttu-id="bee2c-317">有关详细信息，请参阅[前滚](../whats-new/dotnet-core-2-1.md#roll-forward)。</span><span class="sxs-lookup"><span data-stu-id="bee2c-317">For more information, see [Roll forward](../whats-new/dotnet-core-2-1.md#roll-forward).</span></span>

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="bee2c-318">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="bee2c-318">.NET Core 2.0</span></span>](#tab/netcore20)

`DOTNET_PACKAGES`

<span data-ttu-id="bee2c-319">主包缓存。</span><span class="sxs-lookup"><span data-stu-id="bee2c-319">The primary package cache.</span></span> <span data-ttu-id="bee2c-320">如果未设置，则默认为 Unix 上的 `$HOME/.nuget/packages` 或 Windows 上的 `%HOME%\NuGet\Packages`。</span><span class="sxs-lookup"><span data-stu-id="bee2c-320">If not set, it defaults to `$HOME/.nuget/packages` on Unix or `%HOME%\NuGet\Packages` on Windows.</span></span>

`DOTNET_SERVICING`

<span data-ttu-id="bee2c-321">指定加载运行时期间共享主机要使用的服务索引的位置。</span><span class="sxs-lookup"><span data-stu-id="bee2c-321">Specifies the location of the servicing index to use by the shared host when loading the runtime.</span></span>

`DOTNET_CLI_TELEMETRY_OPTOUT`

<span data-ttu-id="bee2c-322">指定是否收集并向 Microsoft 发送 .NET Core 工具使用情况的相关数据。</span><span class="sxs-lookup"><span data-stu-id="bee2c-322">Specifies whether data about the .NET Core tools usage is collected and sent to Microsoft.</span></span> <span data-ttu-id="bee2c-323">设置为 `true` 以选择退出遥测功能（接受的值为 `true`、`1` 或 `yes`）。</span><span class="sxs-lookup"><span data-stu-id="bee2c-323">Set to `true` to opt-out of the telemetry feature (values `true`, `1`, or `yes` accepted).</span></span> <span data-ttu-id="bee2c-324">否则，设置为 `false` 以选择加入遥测功能（接受的值为 `false`、`0` 或 `no`）。</span><span class="sxs-lookup"><span data-stu-id="bee2c-324">Otherwise, set to `false` to opt into the telemetry features (values `false`, `0`, or `no` accepted).</span></span> <span data-ttu-id="bee2c-325">如果未设置，则默认为 `false` 且遥测功能为活动状态。</span><span class="sxs-lookup"><span data-stu-id="bee2c-325">If not set, the default is `false` and the telemetry feature is active.</span></span>

`DOTNET_MULTILEVEL_LOOKUP`

<span data-ttu-id="bee2c-326">指定是否从全局位置解析 .NET Core 运行时、共享框架或 SDK。</span><span class="sxs-lookup"><span data-stu-id="bee2c-326">Specifies whether .NET Core runtime, shared framework, or SDK are resolved from the global location.</span></span> <span data-ttu-id="bee2c-327">如果未设置，则默认为 `true`。</span><span class="sxs-lookup"><span data-stu-id="bee2c-327">If not set, it defaults to `true`.</span></span> <span data-ttu-id="bee2c-328">设置为 `false` 不从全局位置解析，并且具有独立的 .NET Core 安装（接受的值为 `0` 或 `false`）。</span><span class="sxs-lookup"><span data-stu-id="bee2c-328">Set to `false` to not resolve from the global location and have isolated .NET Core installations (values `0` or `false` are accepted).</span></span> <span data-ttu-id="bee2c-329">有关多级别查找的详细信息，请参阅 [Multi-level SharedFX Lookup](https://github.com/dotnet/core-setup/blob/master/Documentation/design-docs/multilevel-sharedfx-lookup.md)（多级别 SharedFX 查找）。</span><span class="sxs-lookup"><span data-stu-id="bee2c-329">For more information about multi-level lookup, see [Multi-level SharedFX Lookup](https://github.com/dotnet/core-setup/blob/master/Documentation/design-docs/multilevel-sharedfx-lookup.md).</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="bee2c-330">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="bee2c-330">.NET Core 1.x</span></span>](#tab/netcore1x)

`DOTNET_PACKAGES`

<span data-ttu-id="bee2c-331">主包缓存。</span><span class="sxs-lookup"><span data-stu-id="bee2c-331">The primary package cache.</span></span> <span data-ttu-id="bee2c-332">如果未设置，则默认为 Unix 上的 `$HOME/.nuget/packages` 或 Windows 上的 `%HOME%\NuGet\Packages`。</span><span class="sxs-lookup"><span data-stu-id="bee2c-332">If not set, it defaults to `$HOME/.nuget/packages` on Unix or `%HOME%\NuGet\Packages` on Windows.</span></span>

`DOTNET_SERVICING`

<span data-ttu-id="bee2c-333">指定加载运行时期间共享主机要使用的服务索引的位置。</span><span class="sxs-lookup"><span data-stu-id="bee2c-333">Specifies the location of the servicing index to use by the shared host when loading the runtime.</span></span>

`DOTNET_CLI_TELEMETRY_OPTOUT`

<span data-ttu-id="bee2c-334">指定是否收集并向 Microsoft 发送 .NET Core 工具使用情况的相关数据。</span><span class="sxs-lookup"><span data-stu-id="bee2c-334">Specifies whether data about the .NET Core tools usage is collected and sent to Microsoft.</span></span> <span data-ttu-id="bee2c-335">设置为 `true` 以选择退出遥测功能（接受的值为 `true`、`1` 或 `yes`）。</span><span class="sxs-lookup"><span data-stu-id="bee2c-335">Set to `true` to opt-out of the telemetry feature (values `true`, `1`, or `yes` accepted).</span></span> <span data-ttu-id="bee2c-336">否则，设置为 `false` 以选择加入遥测功能（接受的值为 `false`、`0` 或 `no`）。</span><span class="sxs-lookup"><span data-stu-id="bee2c-336">Otherwise, set to `false` to opt into the telemetry features (values `false`, `0`, or `no` accepted).</span></span> <span data-ttu-id="bee2c-337">如果未设置，则默认为 `false` 且遥测功能为活动状态。</span><span class="sxs-lookup"><span data-stu-id="bee2c-337">If not set, the default is `false` and the telemetry feature is active.</span></span>

---
