---
title: dotnet run 命令 - .NET Core CLI
description: dotnet run 命令可便于使用源代码运行应用程序。
author: mairaw
ms.author: mairaw
ms.date: 05/29/2018
ms.openlocfilehash: 609ac27f21e6801992b9e10c7d465a805492859e
ms.sourcegitcommit: 9e18e4a18284ae9e54c515e30d019c0bbff9cd37
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/28/2018
ms.locfileid: "37071755"
---
# <a name="dotnet-run"></a><span data-ttu-id="2f138-103">dotnet 运行</span><span class="sxs-lookup"><span data-stu-id="2f138-103">dotnet run</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="2f138-104">name</span><span class="sxs-lookup"><span data-stu-id="2f138-104">Name</span></span>

<span data-ttu-id="2f138-105">`dotnet run` - 无需任何显式编译或启动命令即可运行源代码。</span><span class="sxs-lookup"><span data-stu-id="2f138-105">`dotnet run` - Runs source code without any explicit compile or launch commands.</span></span>

## <a name="synopsis"></a><span data-ttu-id="2f138-106">摘要</span><span class="sxs-lookup"><span data-stu-id="2f138-106">Synopsis</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="2f138-107">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="2f138-107">.NET Core 2.1</span></span>](#tab/netcore21)
```
dotnet run [-c|--configuration] [-f|--framework] [--force] [--launch-profile] [--no-build] [--no-dependencies]
    [--no-launch-profile] [--no-restore] [-p|--project] [--runtime] [-v|--verbosity] [[--] [application arguments]]
dotnet run [-h|--help]
```
# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="2f138-108">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="2f138-108">.NET Core 2.0</span></span>](#tab/netcore20)
```
dotnet run [-c|--configuration] [-f|--framework] [--force] [--launch-profile] [--no-build] [--no-dependencies]
    [--no-launch-profile] [--no-restore] [-p|--project] [--runtime] [[--] [application arguments]]
dotnet run [-h|--help]
```
# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="2f138-109">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="2f138-109">.NET Core 1.x</span></span>](#tab/netcore1x)
```
dotnet run [-c|--configuration] [-f|--framework] [-p|--project] [[--] [application arguments]]
dotnet run [-h|--help]
```
---

## <a name="description"></a><span data-ttu-id="2f138-110">描述</span><span class="sxs-lookup"><span data-stu-id="2f138-110">Description</span></span>

<span data-ttu-id="2f138-111">`dotnet run` 命令为从源代码使用一个命令运行应用程序提供了一个方便的选项。</span><span class="sxs-lookup"><span data-stu-id="2f138-111">The `dotnet run` command provides a convenient option to run your application from the source code with one command.</span></span> <span data-ttu-id="2f138-112">这对从命令行中进行快速迭代开发很有帮助。</span><span class="sxs-lookup"><span data-stu-id="2f138-112">It's useful for fast iterative development from the command line.</span></span> <span data-ttu-id="2f138-113">命令取决于生成代码的 [`dotnet build`](dotnet-build.md) 命令。</span><span class="sxs-lookup"><span data-stu-id="2f138-113">The command depends on the [`dotnet build`](dotnet-build.md) command to build the code.</span></span> <span data-ttu-id="2f138-114">对于此生成的任何要求，例如项目必须首先还原，同样适用于 `dotnet run`。</span><span class="sxs-lookup"><span data-stu-id="2f138-114">Any requirements for the build, such as that the project must be restored first, apply to `dotnet run` as well.</span></span>

<span data-ttu-id="2f138-115">输出文件会写入到默认位置，即 `bin/<configuration>/<target>`。</span><span class="sxs-lookup"><span data-stu-id="2f138-115">Output files are written into the default location, which is `bin/<configuration>/<target>`.</span></span> <span data-ttu-id="2f138-116">例如，如果具有 `netcoreapp1.0` 应用程序并且运行 `dotnet run`，则输出置于 `bin/Debug/netcoreapp1.0`。</span><span class="sxs-lookup"><span data-stu-id="2f138-116">For example if you have a `netcoreapp1.0` application and you run `dotnet run`, the output is placed in `bin/Debug/netcoreapp1.0`.</span></span> <span data-ttu-id="2f138-117">将根据需要覆盖文件。</span><span class="sxs-lookup"><span data-stu-id="2f138-117">Files are overwritten as needed.</span></span> <span data-ttu-id="2f138-118">临时文件将置于 `obj` 目录。</span><span class="sxs-lookup"><span data-stu-id="2f138-118">Temporary files are placed in the `obj` directory.</span></span>

<span data-ttu-id="2f138-119">如果该项目指定多个框架，在不使用 `-f|--framework <FRAMEWORK>` 选项指定框架时，执行 `dotnet run` 将导致错误。</span><span class="sxs-lookup"><span data-stu-id="2f138-119">If the project specifies multiple frameworks, executing `dotnet run` results in an error unless the `-f|--framework <FRAMEWORK>` option is used to specify the framework.</span></span>

<span data-ttu-id="2f138-120">在项目上下文，而不是生成程序集中使用 `dotnet run` 命令。</span><span class="sxs-lookup"><span data-stu-id="2f138-120">The `dotnet run` command is used in the context of projects, not built assemblies.</span></span> <span data-ttu-id="2f138-121">如果尝试改为运行依赖于框架的应用程序 DLL，则必须在不使用命令的情况下使用 [dotnet](dotnet.md)。</span><span class="sxs-lookup"><span data-stu-id="2f138-121">If you're trying to run a framework-dependent application DLL instead, you must use [dotnet](dotnet.md) without a command.</span></span> <span data-ttu-id="2f138-122">例如，若要运行 `myapp.dll`，请使用：</span><span class="sxs-lookup"><span data-stu-id="2f138-122">For example, to run `myapp.dll`, use:</span></span>

```console
dotnet myapp.dll
```

<span data-ttu-id="2f138-123">有关 `dotnet` 驱动程序的详细信息，请参阅 [.NET Core 命令行工具 (CLI)](index.md) 主题。</span><span class="sxs-lookup"><span data-stu-id="2f138-123">For more information on the `dotnet` driver, see the [.NET Core Command Line Tools (CLI)](index.md) topic.</span></span>

<span data-ttu-id="2f138-124">若要运行应用程序，`dotnet run` 命令需从 NuGet 缓存解析共享运行时之外的应用程序依赖项。</span><span class="sxs-lookup"><span data-stu-id="2f138-124">To run the application, the `dotnet run` command resolves the dependencies of the application that are outside of the shared runtime from the NuGet cache.</span></span> <span data-ttu-id="2f138-125">因为它使用缓存的依赖项，因此，不推荐在生产中使用 `dotnet run` 来运行应用程序。</span><span class="sxs-lookup"><span data-stu-id="2f138-125">Because it uses cached dependencies, it's not recommended to use `dotnet run` to run applications in production.</span></span> <span data-ttu-id="2f138-126">相反，使用 [`dotnet publish`](dotnet-publish.md)[ 命令创建部署](../deploying/index.md)，并部署已发布的输出。</span><span class="sxs-lookup"><span data-stu-id="2f138-126">Instead, [create a deployment](../deploying/index.md) using the [`dotnet publish`](dotnet-publish.md) command and deploy the published output.</span></span>

[!INCLUDE[dotnet restore note + options](~/includes/dotnet-restore-note-options.md)]

## <a name="options"></a><span data-ttu-id="2f138-127">选项</span><span class="sxs-lookup"><span data-stu-id="2f138-127">Options</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="2f138-128">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="2f138-128">.NET Core 2.1</span></span>](#tab/netcore21)

`--`

<span data-ttu-id="2f138-129">将参数分隔到正在运行的应用程序的参数的 `dotnet run`。</span><span class="sxs-lookup"><span data-stu-id="2f138-129">Delimits arguments to `dotnet run` from arguments for the application being run.</span></span> <span data-ttu-id="2f138-130">在此分隔符后的所有参数均传递给已运行的应用程序。</span><span class="sxs-lookup"><span data-stu-id="2f138-130">All arguments after this delimiter are passed to the application run.</span></span>

`-c|--configuration {Debug|Release}`

<span data-ttu-id="2f138-131">定义生成配置。</span><span class="sxs-lookup"><span data-stu-id="2f138-131">Defines the build configuration.</span></span> <span data-ttu-id="2f138-132">默认值为 `Debug`。</span><span class="sxs-lookup"><span data-stu-id="2f138-132">The default value is `Debug`.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="2f138-133">使用指定[框架](../../standard/frameworks.md)生成并运行应用。</span><span class="sxs-lookup"><span data-stu-id="2f138-133">Builds and runs the app using the specified [framework](../../standard/frameworks.md).</span></span> <span data-ttu-id="2f138-134">框架必须在项目文件中进行指定。</span><span class="sxs-lookup"><span data-stu-id="2f138-134">The framework must be specified in the project file.</span></span>

`--force`

<span data-ttu-id="2f138-135">强制解析所有依赖项，即使上次还原已成功，也不例外。</span><span class="sxs-lookup"><span data-stu-id="2f138-135">Forces all dependencies to be resolved even if the last restore was successful.</span></span> <span data-ttu-id="2f138-136">指定此标记等同于删除 project.assets.json 文件。</span><span class="sxs-lookup"><span data-stu-id="2f138-136">Specifying this flag is the same as deleting the *project.assets.json* file.</span></span>

`-h|--help`

<span data-ttu-id="2f138-137">打印出有关命令的简短帮助。</span><span class="sxs-lookup"><span data-stu-id="2f138-137">Prints out a short help for the command.</span></span>

`--launch-profile <NAME>`

<span data-ttu-id="2f138-138">启动应用程序时要使用的启动配置文件（若有）的名称。</span><span class="sxs-lookup"><span data-stu-id="2f138-138">The name of the launch profile (if any) to use when launching the application.</span></span> <span data-ttu-id="2f138-139">启动配置文件在 launchSettings.json 文件中进行定义，通常称为 `Development`、`Staging` 和 `Production`。</span><span class="sxs-lookup"><span data-stu-id="2f138-139">Launch profiles are defined in the *launchSettings.json* file and are typically called `Development`, `Staging`, and `Production`.</span></span> <span data-ttu-id="2f138-140">有关详细信息，请参阅[使用多个环境](/aspnet/core/fundamentals/environments)。</span><span class="sxs-lookup"><span data-stu-id="2f138-140">For more information, see [Working with multiple environments](/aspnet/core/fundamentals/environments).</span></span>

`--no-build`

<span data-ttu-id="2f138-141">运行前不生成项目。</span><span class="sxs-lookup"><span data-stu-id="2f138-141">Doesn't build the project before running.</span></span> <span data-ttu-id="2f138-142">还隐式设置 `--no-restore` 标记。</span><span class="sxs-lookup"><span data-stu-id="2f138-142">It also implicit sets the `--no-restore` flag.</span></span>

`--no-dependencies`

<span data-ttu-id="2f138-143">当使用项目到项目 (P2P) 引用还原项目时，还原根项目，不还原引用。</span><span class="sxs-lookup"><span data-stu-id="2f138-143">When restoring a project with project-to-project (P2P) references, restores the root project and not the references.</span></span>

`--no-launch-profile`

<span data-ttu-id="2f138-144">不尝试使用 launchSettings.json 配置应用程序。</span><span class="sxs-lookup"><span data-stu-id="2f138-144">Doesn't try to use *launchSettings.json* to configure the application.</span></span>

`--no-restore`

<span data-ttu-id="2f138-145">运行此命令时不执行隐式还原。</span><span class="sxs-lookup"><span data-stu-id="2f138-145">Doesn't execute an implicit restore when running the command.</span></span>

`-p|--project <PATH>`

<span data-ttu-id="2f138-146">指定要运行的项目文件的路径（文件夹名称或完整路径）。</span><span class="sxs-lookup"><span data-stu-id="2f138-146">Specifies the path of the project file to run (folder name or full path).</span></span> <span data-ttu-id="2f138-147">如果未指定，则默认为当前目录。</span><span class="sxs-lookup"><span data-stu-id="2f138-147">If not specified, it defaults to the current directory.</span></span>

`--runtime <RUNTIME_IDENTIFIER>`

<span data-ttu-id="2f138-148">指定要为其还原包的目标运行时。</span><span class="sxs-lookup"><span data-stu-id="2f138-148">Specifies the target runtime to restore packages for.</span></span> <span data-ttu-id="2f138-149">有关运行时标识符 (RID) 的列表，请参阅 [RID 目录](../rid-catalog.md)。</span><span class="sxs-lookup"><span data-stu-id="2f138-149">For a list of Runtime Identifiers (RIDs), see the [RID catalog](../rid-catalog.md).</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="2f138-150">设置命令的详细级别。</span><span class="sxs-lookup"><span data-stu-id="2f138-150">Sets the verbosity level of the command.</span></span> <span data-ttu-id="2f138-151">允许使用的值为 `q[uiet]`、`m[inimal]`、`n[ormal]`、`d[etailed]` 和 `diag[nostic]`。</span><span class="sxs-lookup"><span data-stu-id="2f138-151">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="2f138-152">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="2f138-152">.NET Core 2.0</span></span>](#tab/netcore20)

`--`

<span data-ttu-id="2f138-153">将参数分隔到正在运行的应用程序的参数的 `dotnet run`。</span><span class="sxs-lookup"><span data-stu-id="2f138-153">Delimits arguments to `dotnet run` from arguments for the application being run.</span></span> <span data-ttu-id="2f138-154">在此分隔符后的所有参数均传递给已运行的应用程序。</span><span class="sxs-lookup"><span data-stu-id="2f138-154">All arguments after this delimiter are passed to the application run.</span></span>

`-c|--configuration {Debug|Release}`

<span data-ttu-id="2f138-155">定义生成配置。</span><span class="sxs-lookup"><span data-stu-id="2f138-155">Defines the build configuration.</span></span> <span data-ttu-id="2f138-156">默认值为 `Debug`。</span><span class="sxs-lookup"><span data-stu-id="2f138-156">The default value is `Debug`.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="2f138-157">使用指定[框架](../../standard/frameworks.md)生成并运行应用。</span><span class="sxs-lookup"><span data-stu-id="2f138-157">Builds and runs the app using the specified [framework](../../standard/frameworks.md).</span></span> <span data-ttu-id="2f138-158">框架必须在项目文件中进行指定。</span><span class="sxs-lookup"><span data-stu-id="2f138-158">The framework must be specified in the project file.</span></span>

`--force`

<span data-ttu-id="2f138-159">强制解析所有依赖项，即使上次还原已成功，也不例外。</span><span class="sxs-lookup"><span data-stu-id="2f138-159">Forces all dependencies to be resolved even if the last restore was successful.</span></span> <span data-ttu-id="2f138-160">指定此标记等同于删除 project.assets.json 文件。</span><span class="sxs-lookup"><span data-stu-id="2f138-160">Specifying this flag is the same as deleting the *project.assets.json* file.</span></span>

`-h|--help`

<span data-ttu-id="2f138-161">打印出有关命令的简短帮助。</span><span class="sxs-lookup"><span data-stu-id="2f138-161">Prints out a short help for the command.</span></span>

`--launch-profile <NAME>`

<span data-ttu-id="2f138-162">启动应用程序时要使用的启动配置文件（若有）的名称。</span><span class="sxs-lookup"><span data-stu-id="2f138-162">The name of the launch profile (if any) to use when launching the application.</span></span> <span data-ttu-id="2f138-163">启动配置文件在 launchSettings.json 文件中进行定义，通常称为 `Development`、`Staging` 和 `Production`。</span><span class="sxs-lookup"><span data-stu-id="2f138-163">Launch profiles are defined in the *launchSettings.json* file and are typically called `Development`, `Staging`, and `Production`.</span></span> <span data-ttu-id="2f138-164">有关详细信息，请参阅[使用多个环境](/aspnet/core/fundamentals/environments)。</span><span class="sxs-lookup"><span data-stu-id="2f138-164">For more information, see [Working with multiple environments](/aspnet/core/fundamentals/environments).</span></span>

`--no-build`

<span data-ttu-id="2f138-165">运行前不生成项目。</span><span class="sxs-lookup"><span data-stu-id="2f138-165">Doesn't build the project before running.</span></span> <span data-ttu-id="2f138-166">还隐式设置 `--no-restore` 标记。</span><span class="sxs-lookup"><span data-stu-id="2f138-166">It also implicit sets the `--no-restore` flag.</span></span>

`--no-dependencies`

<span data-ttu-id="2f138-167">当使用项目到项目 (P2P) 引用还原项目时，还原根项目，不还原引用。</span><span class="sxs-lookup"><span data-stu-id="2f138-167">When restoring a project with project-to-project (P2P) references, restores the root project and not the references.</span></span>

`--no-launch-profile`

<span data-ttu-id="2f138-168">不尝试使用 launchSettings.json 配置应用程序。</span><span class="sxs-lookup"><span data-stu-id="2f138-168">Doesn't try to use *launchSettings.json* to configure the application.</span></span>

`--no-restore`

<span data-ttu-id="2f138-169">运行此命令时不执行隐式还原。</span><span class="sxs-lookup"><span data-stu-id="2f138-169">Doesn't execute an implicit restore when running the command.</span></span>

`-p|--project <PATH>`

<span data-ttu-id="2f138-170">指定要运行的项目文件的路径（文件夹名称或完整路径）。</span><span class="sxs-lookup"><span data-stu-id="2f138-170">Specifies the path of the project file to run (folder name or full path).</span></span> <span data-ttu-id="2f138-171">如果未指定，则默认为当前目录。</span><span class="sxs-lookup"><span data-stu-id="2f138-171">If not specified, it defaults to the current directory.</span></span>

`--runtime <RUNTIME_IDENTIFIER>`

<span data-ttu-id="2f138-172">指定要为其还原包的目标运行时。</span><span class="sxs-lookup"><span data-stu-id="2f138-172">Specifies the target runtime to restore packages for.</span></span> <span data-ttu-id="2f138-173">有关运行时标识符 (RID) 的列表，请参阅 [RID 目录](../rid-catalog.md)。</span><span class="sxs-lookup"><span data-stu-id="2f138-173">For a list of Runtime Identifiers (RIDs), see the [RID catalog](../rid-catalog.md).</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="2f138-174">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="2f138-174">.NET Core 1.x</span></span>](#tab/netcore1x)

`--`

<span data-ttu-id="2f138-175">将参数分隔到正在运行的应用程序的参数的 `dotnet run`。</span><span class="sxs-lookup"><span data-stu-id="2f138-175">Delimits arguments to `dotnet run` from arguments for the application being run.</span></span> <span data-ttu-id="2f138-176">在此分隔符后的所有参数均传递给已运行的应用程序。</span><span class="sxs-lookup"><span data-stu-id="2f138-176">All arguments after this delimiter are passed to the application run.</span></span>

`-c|--configuration {Debug|Release}`

<span data-ttu-id="2f138-177">定义生成配置。</span><span class="sxs-lookup"><span data-stu-id="2f138-177">Defines the build configuration.</span></span> <span data-ttu-id="2f138-178">默认值为 `Debug`。</span><span class="sxs-lookup"><span data-stu-id="2f138-178">The default value is `Debug`.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="2f138-179">使用指定[框架](../../standard/frameworks.md)生成并运行应用。</span><span class="sxs-lookup"><span data-stu-id="2f138-179">Builds and runs the app using the specified [framework](../../standard/frameworks.md).</span></span> <span data-ttu-id="2f138-180">框架必须在项目文件中进行指定。</span><span class="sxs-lookup"><span data-stu-id="2f138-180">The framework must be specified in the project file.</span></span>

`-h|--help`

<span data-ttu-id="2f138-181">打印出有关命令的简短帮助。</span><span class="sxs-lookup"><span data-stu-id="2f138-181">Prints out a short help for the command.</span></span>

`-p|--project <PATH/PROJECT.csproj>`

<span data-ttu-id="2f138-182">指定项目文件的路径和名称。</span><span class="sxs-lookup"><span data-stu-id="2f138-182">Specifies the path and name of the project file.</span></span> <span data-ttu-id="2f138-183">（请参阅备注。）如果未指定，则默认为当前目录。</span><span class="sxs-lookup"><span data-stu-id="2f138-183">(See the NOTE.) If not specified, it defaults to the current directory.</span></span>

> [!NOTE]
> <span data-ttu-id="2f138-184">通过 `-p|--project` 选项使用项目文件的路径和名称。</span><span class="sxs-lookup"><span data-stu-id="2f138-184">Use the path and name of the project file with the `-p|--project` option.</span></span> <span data-ttu-id="2f138-185">CLI 中的回归可阻止使用 .NET Core SDK 1.x 提供文件夹路径。</span><span class="sxs-lookup"><span data-stu-id="2f138-185">A regression in the CLI prevents providing a folder path with .NET Core SDK 1.x.</span></span> <span data-ttu-id="2f138-186">若要详细了解此问题，请参阅 [dotnet run -p - 无法启动项目 (dotnet/cli #5992)](https://github.com/dotnet/cli/issues/5992)。</span><span class="sxs-lookup"><span data-stu-id="2f138-186">For more information about this issue, see [dotnet run -p, can not start a project (dotnet/cli #5992)](https://github.com/dotnet/cli/issues/5992).</span></span>

---

## <a name="examples"></a><span data-ttu-id="2f138-187">示例</span><span class="sxs-lookup"><span data-stu-id="2f138-187">Examples</span></span>

<span data-ttu-id="2f138-188">运行当前目录中的项目：</span><span class="sxs-lookup"><span data-stu-id="2f138-188">Run the project in the current directory:</span></span>

`dotnet run`

<span data-ttu-id="2f138-189">运行指定的项目：</span><span class="sxs-lookup"><span data-stu-id="2f138-189">Run the specified project:</span></span>

`dotnet run --project ./projects/proj1/proj1.csproj`

<span data-ttu-id="2f138-190">运行当前目录中的项目（在本例中，`--help` 参数被传递到应用程序，因为使用了空白的 `--` 选项）：</span><span class="sxs-lookup"><span data-stu-id="2f138-190">Run the project in the current directory (the `--help` argument in this example is passed to the application, since the blank `--` option is used):</span></span>

`dotnet run --configuration Release -- --help`

<span data-ttu-id="2f138-191">在当前仅显示最小输出的目录中还原项目的依赖项和工具，然后运行项目（.NET Core SDK 2.0 及更高版本）：</span><span class="sxs-lookup"><span data-stu-id="2f138-191">Restore dependencies and tools for the project in the current directory only showing minimal output and then run the project: (.NET Core SDK 2.0 and later versions):</span></span>

`dotnet run --verbosity m`