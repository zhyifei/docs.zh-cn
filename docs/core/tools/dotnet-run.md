---
title: "dotnet run 命令 - .NET Core CLI"
description: "dotnet run 命令可便于使用源代码运行应用程序。"
author: mairaw
ms.author: mairaw
ms.date: 03/10/2018
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.workload:
- dotnetcore
ms.openlocfilehash: 251aca6dcd3edb17fe86dc03ea8f5c6d7d699d48
ms.sourcegitcommit: 83dd5ec003e788ccb3e33f3412a7af39ae347646
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/15/2018
---
# <a name="dotnet-run"></a><span data-ttu-id="83262-103">dotnet 运行</span><span class="sxs-lookup"><span data-stu-id="83262-103">dotnet run</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="83262-104">name</span><span class="sxs-lookup"><span data-stu-id="83262-104">Name</span></span>

<span data-ttu-id="83262-105">`dotnet run` - 无需任何显式编译或启动命令即可运行源代码。</span><span class="sxs-lookup"><span data-stu-id="83262-105">`dotnet run` - Runs source code without any explicit compile or launch commands.</span></span>

## <a name="synopsis"></a><span data-ttu-id="83262-106">摘要</span><span class="sxs-lookup"><span data-stu-id="83262-106">Synopsis</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="83262-107">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="83262-107">.NET Core 2.x</span></span>](#tab/netcore2x)

```
dotnet run [-c|--configuration] [-f|--framework] [--force] [--launch-profile] [--no-build] [--no-dependencies] [--no-launch-profile] [--no-restore] [-p|--project] [--runtime] [[--] [application arguments]]
dotnet run [-h|--help]
```

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="83262-108">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="83262-108">.NET Core 1.x</span></span>](#tab/netcore1x)

```
dotnet run [-c|--configuration] [-f|--framework] [-p|--project] [[--] [application arguments]]
dotnet run [-h|--help]
```

---

## <a name="description"></a><span data-ttu-id="83262-109">描述</span><span class="sxs-lookup"><span data-stu-id="83262-109">Description</span></span>

<span data-ttu-id="83262-110">`dotnet run` 命令为从源代码使用一个命令运行应用程序提供了一个方便的选项。</span><span class="sxs-lookup"><span data-stu-id="83262-110">The `dotnet run` command provides a convenient option to run your application from the source code with one command.</span></span> <span data-ttu-id="83262-111">这对从命令行中进行快速迭代开发很有帮助。</span><span class="sxs-lookup"><span data-stu-id="83262-111">It's useful for fast iterative development from the command line.</span></span> <span data-ttu-id="83262-112">命令取决于生成代码的 [`dotnet build`](dotnet-build.md) 命令。</span><span class="sxs-lookup"><span data-stu-id="83262-112">The command depends on the [`dotnet build`](dotnet-build.md) command to build the code.</span></span> <span data-ttu-id="83262-113">对于此生成的任何要求，例如项目必须首先还原，同样适用于 `dotnet run`。</span><span class="sxs-lookup"><span data-stu-id="83262-113">Any requirements for the build, such as that the project must be restored first, apply to `dotnet run` as well.</span></span>

<span data-ttu-id="83262-114">输出文件会写入到默认位置，即 `bin/<configuration>/<target>`。</span><span class="sxs-lookup"><span data-stu-id="83262-114">Output files are written into the default location, which is `bin/<configuration>/<target>`.</span></span> <span data-ttu-id="83262-115">例如，如果具有 `netcoreapp1.0` 应用程序并且运行 `dotnet run`，则输出置于 `bin/Debug/netcoreapp1.0`。</span><span class="sxs-lookup"><span data-stu-id="83262-115">For example if you have a `netcoreapp1.0` application and you run `dotnet run`, the output is placed in `bin/Debug/netcoreapp1.0`.</span></span> <span data-ttu-id="83262-116">将根据需要覆盖文件。</span><span class="sxs-lookup"><span data-stu-id="83262-116">Files are overwritten as needed.</span></span> <span data-ttu-id="83262-117">临时文件将置于 `obj` 目录。</span><span class="sxs-lookup"><span data-stu-id="83262-117">Temporary files are placed in the `obj` directory.</span></span>

<span data-ttu-id="83262-118">如果该项目指定多个框架，在不使用 `-f|--framework <FRAMEWORK>` 选项指定框架时，执行 `dotnet run` 将导致错误。</span><span class="sxs-lookup"><span data-stu-id="83262-118">If the project specifies multiple frameworks, executing `dotnet run` results in an error unless the `-f|--framework <FRAMEWORK>` option is used to specify the framework.</span></span>

<span data-ttu-id="83262-119">在项目上下文，而不是生成程序集中使用 `dotnet run` 命令。</span><span class="sxs-lookup"><span data-stu-id="83262-119">The `dotnet run` command is used in the context of projects, not built assemblies.</span></span> <span data-ttu-id="83262-120">如果尝试改为运行依赖于框架的应用程序 DLL，则必须在不使用命令的情况下使用 [dotnet](dotnet.md)。</span><span class="sxs-lookup"><span data-stu-id="83262-120">If you're trying to run a framework-dependent application DLL instead, you must use [dotnet](dotnet.md) without a command.</span></span> <span data-ttu-id="83262-121">例如，若要运行 `myapp.dll`，请使用：</span><span class="sxs-lookup"><span data-stu-id="83262-121">For example, to run `myapp.dll`, use:</span></span>

```
dotnet myapp.dll
```

<span data-ttu-id="83262-122">有关 `dotnet` 驱动程序的详细信息，请参阅 [.NET Core 命令行工具 (CLI)](index.md) 主题。</span><span class="sxs-lookup"><span data-stu-id="83262-122">For more information on the `dotnet` driver, see the [.NET Core Command Line Tools (CLI)](index.md) topic.</span></span>

<span data-ttu-id="83262-123">若要运行应用程序，`dotnet run` 命令需从 NuGet 缓存解析共享运行时之外的应用程序依赖项。</span><span class="sxs-lookup"><span data-stu-id="83262-123">In order to run the application, the `dotnet run` command resolves the dependencies of the application that are outside of the shared runtime from the NuGet cache.</span></span> <span data-ttu-id="83262-124">因为它使用缓存的依赖项，因此，不推荐在生产中使用 `dotnet run` 来运行应用程序。</span><span class="sxs-lookup"><span data-stu-id="83262-124">Because it uses cached dependencies, it's not recommended to use `dotnet run` to run applications in production.</span></span> <span data-ttu-id="83262-125">相反，使用 [`dotnet publish`](dotnet-publish.md)[ 命令创建部署](../deploying/index.md)，并部署已发布的输出。</span><span class="sxs-lookup"><span data-stu-id="83262-125">Instead, [create a deployment](../deploying/index.md) using the [`dotnet publish`](dotnet-publish.md) command and deploy the published output.</span></span>

[!INCLUDE[dotnet restore note + options](~/includes/dotnet-restore-note-options.md)]

## <a name="options"></a><span data-ttu-id="83262-126">选项</span><span class="sxs-lookup"><span data-stu-id="83262-126">Options</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="83262-127">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="83262-127">.NET Core 2.x</span></span>](#tab/netcore2x)

`--`

<span data-ttu-id="83262-128">将参数分隔到正在运行的应用程序的参数的 `dotnet run`。</span><span class="sxs-lookup"><span data-stu-id="83262-128">Delimits arguments to `dotnet run` from arguments for the application being run.</span></span> <span data-ttu-id="83262-129">在此参数后的所有参数均传递给已运行的应用程序。</span><span class="sxs-lookup"><span data-stu-id="83262-129">All arguments after this one are passed to the application run.</span></span>

`-c|--configuration {Debug|Release}`

<span data-ttu-id="83262-130">定义生成配置。</span><span class="sxs-lookup"><span data-stu-id="83262-130">Defines the build configuration.</span></span> <span data-ttu-id="83262-131">默认值为 `Debug`。</span><span class="sxs-lookup"><span data-stu-id="83262-131">The default value is `Debug`.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="83262-132">使用指定[框架](../../standard/frameworks.md)生成并运行应用。</span><span class="sxs-lookup"><span data-stu-id="83262-132">Builds and runs the app using the specified [framework](../../standard/frameworks.md).</span></span> <span data-ttu-id="83262-133">框架必须在项目文件中进行指定。</span><span class="sxs-lookup"><span data-stu-id="83262-133">The framework must be specified in the project file.</span></span>

`--force`

<span data-ttu-id="83262-134">强制解析所有依赖项，即使上次还原已成功，也不例外。</span><span class="sxs-lookup"><span data-stu-id="83262-134">Forces all dependencies to be resolved even if the last restore was successful.</span></span> <span data-ttu-id="83262-135">这相当于删除 project.assets.json。</span><span class="sxs-lookup"><span data-stu-id="83262-135">This is equivalent to deleting *project.assets.json*.</span></span>

`-h|--help`

<span data-ttu-id="83262-136">打印出有关命令的简短帮助。</span><span class="sxs-lookup"><span data-stu-id="83262-136">Prints out a short help for the command.</span></span>

`--launch-profile <NAME>`

<span data-ttu-id="83262-137">启动应用程序时要使用的启动配置文件（若有）的名称。</span><span class="sxs-lookup"><span data-stu-id="83262-137">The name of the launch profile (if any) to use when launching the application.</span></span> <span data-ttu-id="83262-138">启动配置文件在 launchSettings.json 文件中进行定义，通常称为 `Development`、`Staging` 和 `Production`。</span><span class="sxs-lookup"><span data-stu-id="83262-138">Launch profiles are defined in the *launchSettings.json* file and are typically called `Development`, `Staging` and `Production`.</span></span> <span data-ttu-id="83262-139">有关详细信息，请参阅[使用多个环境](/aspnet/core/fundamentals/environments)。</span><span class="sxs-lookup"><span data-stu-id="83262-139">For more information, see [Working with multiple environments](/aspnet/core/fundamentals/environments).</span></span>

`--no-build`

<span data-ttu-id="83262-140">运行前不生成项目。</span><span class="sxs-lookup"><span data-stu-id="83262-140">Doesn't build the project before running.</span></span>

`--no-dependencies`

<span data-ttu-id="83262-141">当使用项目到项目 (P2P) 引用还原项目时，还原根项目，不还原引用。</span><span class="sxs-lookup"><span data-stu-id="83262-141">When restoring a project with project-to-project (P2P) references, restores the root project and not the references.</span></span>

`--no-launch-profile`

<span data-ttu-id="83262-142">不尝试使用 launchSettings.json 配置应用程序。</span><span class="sxs-lookup"><span data-stu-id="83262-142">Doesn't attempt to use *launchSettings.json* to configure the application.</span></span>

`--no-restore`

<span data-ttu-id="83262-143">运行此命令时不执行隐式还原。</span><span class="sxs-lookup"><span data-stu-id="83262-143">Doesn't perform an implicit restore when running the command.</span></span>

`-p|--project <PATH>`

<span data-ttu-id="83262-144">指定要运行的项目文件的路径（文件夹名称或完整路径）。</span><span class="sxs-lookup"><span data-stu-id="83262-144">Specifies the path of the project file to run (folder name or full path).</span></span> <span data-ttu-id="83262-145">如果未指定，则默认为当前目录。</span><span class="sxs-lookup"><span data-stu-id="83262-145">It defaults to the current directory if not specified.</span></span>

`--runtime <RUNTIME_IDENTIFIER>`

<span data-ttu-id="83262-146">指定要为其还原包的目标运行时。</span><span class="sxs-lookup"><span data-stu-id="83262-146">Specifies the target runtime to restore packages for.</span></span> <span data-ttu-id="83262-147">有关运行时标识符 (RID) 的列表，请参阅 [RID 目录](../rid-catalog.md)。</span><span class="sxs-lookup"><span data-stu-id="83262-147">For a list of Runtime Identifiers (RIDs), see the [RID catalog](../rid-catalog.md).</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="83262-148">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="83262-148">.NET Core 1.x</span></span>](#tab/netcore1x)

`--`

<span data-ttu-id="83262-149">将参数分隔到正在运行的应用程序的参数的 `dotnet run`。</span><span class="sxs-lookup"><span data-stu-id="83262-149">Delimits arguments to `dotnet run` from arguments for the application being run.</span></span> <span data-ttu-id="83262-150">在此参数后的所有参数均传递给已运行的应用程序。</span><span class="sxs-lookup"><span data-stu-id="83262-150">All arguments after this one are passed to the application run.</span></span>

`-c|--configuration {Debug|Release}`

<span data-ttu-id="83262-151">定义生成配置。</span><span class="sxs-lookup"><span data-stu-id="83262-151">Defines the build configuration.</span></span> <span data-ttu-id="83262-152">默认值为 `Debug`。</span><span class="sxs-lookup"><span data-stu-id="83262-152">The default value is `Debug`.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="83262-153">使用指定[框架](../../standard/frameworks.md)生成并运行应用。</span><span class="sxs-lookup"><span data-stu-id="83262-153">Builds and runs the app using the specified [framework](../../standard/frameworks.md).</span></span> <span data-ttu-id="83262-154">框架必须在项目文件中进行指定。</span><span class="sxs-lookup"><span data-stu-id="83262-154">The framework must be specified in the project file.</span></span>

`-h|--help`

<span data-ttu-id="83262-155">打印出有关命令的简短帮助。</span><span class="sxs-lookup"><span data-stu-id="83262-155">Prints out a short help for the command.</span></span>

`-p|--project <PATH/PROJECT.csproj>`

<span data-ttu-id="83262-156">指定项目文件的路径和名称。</span><span class="sxs-lookup"><span data-stu-id="83262-156">Specifies the path and name of the project file.</span></span> <span data-ttu-id="83262-157">（请参阅备注。）如果未指定，则默认为当前目录。</span><span class="sxs-lookup"><span data-stu-id="83262-157">(See the NOTE.) It defaults to the current directory if not specified.</span></span>

> [!NOTE]
> <span data-ttu-id="83262-158">通过 `-p|--project` 选项使用项目文件的路径和名称。</span><span class="sxs-lookup"><span data-stu-id="83262-158">Use the path and name of the project file with the `-p|--project` option.</span></span> <span data-ttu-id="83262-159">CLI 中的回归可阻止使用 .NET Core SDK 1.x 提供文件夹路径。</span><span class="sxs-lookup"><span data-stu-id="83262-159">A regression in the CLI prevents providing a folder path with .NET Core SDK 1.x.</span></span> <span data-ttu-id="83262-160">若要详细了解此问题，请参阅 [dotnet run -p - 无法启动项目 (dotnet/cli #5992)](https://github.com/dotnet/cli/issues/5992)。</span><span class="sxs-lookup"><span data-stu-id="83262-160">For more information about this issue, see [dotnet run -p, can not start a project (dotnet/cli #5992)](https://github.com/dotnet/cli/issues/5992).</span></span>

---

## <a name="examples"></a><span data-ttu-id="83262-161">示例</span><span class="sxs-lookup"><span data-stu-id="83262-161">Examples</span></span>

<span data-ttu-id="83262-162">运行当前目录中的项目：</span><span class="sxs-lookup"><span data-stu-id="83262-162">Run the project in the current directory:</span></span>

`dotnet run`

<span data-ttu-id="83262-163">运行指定的项目：</span><span class="sxs-lookup"><span data-stu-id="83262-163">Run the specified project:</span></span>

`dotnet run --project /projects/proj1/proj1.csproj`

<span data-ttu-id="83262-164">运行当前目录中的项目（在本例中，`--help` 参数被传递到应用程序，因为使用了 `--` 参数）：</span><span class="sxs-lookup"><span data-stu-id="83262-164">Run the project in the current directory (the `--help` argument in this example is passed to the application, since the `--` argument is used):</span></span>

`dotnet run --configuration Release -- --help`

<span data-ttu-id="83262-165">在当前仅显示最小输出的目录中还原项目的依赖项和工具，然后运行项目（.NET Core SDK 2.0 及更高版本）：</span><span class="sxs-lookup"><span data-stu-id="83262-165">Restore dependencies and tools for the project in the current directory only showing minimal output and then run the project: (.NET Core SDK 2.0 and later versions):</span></span>

`dotnet run --verbosity m`