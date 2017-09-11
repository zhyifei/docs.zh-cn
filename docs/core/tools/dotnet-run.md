---
title: "dotnet-run 命令 - .NET Core CLI"
description: "dotnet-run 命令为从源代码运行应用程序提供了一个方便的选项。"
keywords: "dotnet-run, CLI, CLI 命令, .NET Core"
author: blackdwarf
ms.author: mairaw
ms.date: 03/22/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: 40d4e60f-9900-4a48-b03c-0bae06792d91
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: f0a6fce4f83808076b7cbcabdaa948badde2cf80
ms.contentlocale: zh-cn
ms.lasthandoff: 07/28/2017

---

# <a name="dotnet-run"></a><span data-ttu-id="4368b-104">dotnet-run</span><span class="sxs-lookup"><span data-stu-id="4368b-104">dotnet-run</span></span>

## <a name="name"></a><span data-ttu-id="4368b-105">名称</span><span class="sxs-lookup"><span data-stu-id="4368b-105">Name</span></span> 

<span data-ttu-id="4368b-106">`dotnet-run` - 无需任何显式编译或启动命令即可运行源代码。</span><span class="sxs-lookup"><span data-stu-id="4368b-106">`dotnet-run` - Runs source code without any explicit compile or launch commands.</span></span>

## <a name="synopsis"></a><span data-ttu-id="4368b-107">摘要</span><span class="sxs-lookup"><span data-stu-id="4368b-107">Synopsis</span></span>

`dotnet run [-c|--configuration] [-f|--framework] [-p|--project] [[--] [application arguments]] [-h|--help]`

## <a name="description"></a><span data-ttu-id="4368b-108">描述</span><span class="sxs-lookup"><span data-stu-id="4368b-108">Description</span></span>

<span data-ttu-id="4368b-109">`dotnet run` 命令为从源代码使用一个命令运行应用程序提供了一个方便的选项。</span><span class="sxs-lookup"><span data-stu-id="4368b-109">The `dotnet run` command provides a convenient option to run your application from the source code with one command.</span></span> <span data-ttu-id="4368b-110">这对从命令行中进行快速迭代开发很有帮助。</span><span class="sxs-lookup"><span data-stu-id="4368b-110">It's useful for fast iterative development from the command line.</span></span> <span data-ttu-id="4368b-111">命令取决于生成代码的 [`dotnet build`](dotnet-build.md) 命令。</span><span class="sxs-lookup"><span data-stu-id="4368b-111">The command depends on the [`dotnet build`](dotnet-build.md) command to build the code.</span></span> <span data-ttu-id="4368b-112">对于此生成的任何要求，例如项目必须首先还原，同样适用于 `dotnet run`。</span><span class="sxs-lookup"><span data-stu-id="4368b-112">Any requirements for the build, such as that the project must be restored first, apply to `dotnet run` as well.</span></span> 

<span data-ttu-id="4368b-113">输出文件会写入到默认位置，即 `bin/<configuration>/<target>`。</span><span class="sxs-lookup"><span data-stu-id="4368b-113">Output files are written into the default location, which is `bin/<configuration>/<target>`.</span></span> <span data-ttu-id="4368b-114">例如，如果具有 `netcoreapp1.0` 应用程序并且运行 `dotnet run`，则输出置于 `bin/Debug/netcoreapp1.0`。</span><span class="sxs-lookup"><span data-stu-id="4368b-114">For example if you have a `netcoreapp1.0` application and you run `dotnet run`, the output is placed in `bin/Debug/netcoreapp1.0`.</span></span> <span data-ttu-id="4368b-115">将根据需要覆盖文件。</span><span class="sxs-lookup"><span data-stu-id="4368b-115">Files are overwritten as needed.</span></span> <span data-ttu-id="4368b-116">临时文件将置于 `obj` 目录。</span><span class="sxs-lookup"><span data-stu-id="4368b-116">Temporary files are placed in the `obj` directory.</span></span> 

<span data-ttu-id="4368b-117">如果该项目指定多个框架，在不使用 `-f|--framework <FRAMEWORK>` 选项指定框架时，执行 `dotnet run` 将导致错误。</span><span class="sxs-lookup"><span data-stu-id="4368b-117">If the project specifies multiple frameworks, executing `dotnet run` results in an error unless the `-f|--framework <FRAMEWORK>` option is used to specify the framework.</span></span>

<span data-ttu-id="4368b-118">在项目上下文，而不是生成程序集中使用 `dotnet run` 命令。</span><span class="sxs-lookup"><span data-stu-id="4368b-118">The `dotnet run` command is used in the context of projects, not built assemblies.</span></span> <span data-ttu-id="4368b-119">如果尝试改为运行依赖于框架的应用程序 DLL，则必须在不使用命令的情况下使用 [dotnet](dotnet.md)。</span><span class="sxs-lookup"><span data-stu-id="4368b-119">If you're trying to run a framework-dependent application DLL instead, you must use [dotnet](dotnet.md) without a command.</span></span> <span data-ttu-id="4368b-120">例如，若要运行 `myapp.dll`，请使用：</span><span class="sxs-lookup"><span data-stu-id="4368b-120">For example, to run `myapp.dll`, use:</span></span>
 
```
dotnet myapp.dll
```

<span data-ttu-id="4368b-121">有关 `dotnet` 驱动程序的详细信息，请参阅 [.NET Core 命令行工具 (CLI)](index.md) 主题。</span><span class="sxs-lookup"><span data-stu-id="4368b-121">For more information on the `dotnet` driver, see the [.NET Core Command Line Tools (CLI)](index.md) topic.</span></span>

<span data-ttu-id="4368b-122">若要运行应用程序，`dotnet run` 命令需从 NuGet 缓存解析共享运行时之外的应用程序依赖项。</span><span class="sxs-lookup"><span data-stu-id="4368b-122">In order to run the application, the `dotnet run` command resolves the dependencies of the application that are outside of the shared runtime from the NuGet cache.</span></span> <span data-ttu-id="4368b-123">因为它使用缓存的依赖项，因此，不推荐在生产中使用 `dotnet run` 来运行应用程序。</span><span class="sxs-lookup"><span data-stu-id="4368b-123">Because it uses cached dependencies, it's not recommended to use `dotnet run` to run applications in production.</span></span> <span data-ttu-id="4368b-124">相反，使用 [`dotnet publish`](dotnet-publish.md)[ 命令创建部署](../deploying/index.md)，并部署已发布的输出。</span><span class="sxs-lookup"><span data-stu-id="4368b-124">Instead, [create a deployment](../deploying/index.md) using the [`dotnet publish`](dotnet-publish.md) command and deploy the published output.</span></span> 

## <a name="options"></a><span data-ttu-id="4368b-125">选项</span><span class="sxs-lookup"><span data-stu-id="4368b-125">Options</span></span>

`--`

<span data-ttu-id="4368b-126">将参数分隔到正在运行的应用程序的参数的 `dotnet run`。</span><span class="sxs-lookup"><span data-stu-id="4368b-126">Delimits arguments to `dotnet run` from arguments for the application being run.</span></span> <span data-ttu-id="4368b-127">在此参数后的所有参数均传递给已运行的应用程序。</span><span class="sxs-lookup"><span data-stu-id="4368b-127">All arguments after this one are passed to the application run.</span></span> 

`-h|--help`

<span data-ttu-id="4368b-128">打印出有关命令的简短帮助。</span><span class="sxs-lookup"><span data-stu-id="4368b-128">Prints out a short help for the command.</span></span>

`-c|--configuration <CONFIGURATION>`

<span data-ttu-id="4368b-129">用于生成项目的配置。</span><span class="sxs-lookup"><span data-stu-id="4368b-129">Configuration to use for building the project.</span></span> <span data-ttu-id="4368b-130">默认值为 `Debug`。</span><span class="sxs-lookup"><span data-stu-id="4368b-130">The default value is `Debug`.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="4368b-131">使用指定[框架](../../standard/frameworks.md)生成并运行应用。</span><span class="sxs-lookup"><span data-stu-id="4368b-131">Builds and runs the app using the specified [framework](../../standard/frameworks.md).</span></span> <span data-ttu-id="4368b-132">框架必须在项目文件中进行指定。</span><span class="sxs-lookup"><span data-stu-id="4368b-132">The framework must be specified in the project file.</span></span>

`-p|--project <PATH/PROJECT.csproj>`

<span data-ttu-id="4368b-133">指定项目文件的路径和名称。</span><span class="sxs-lookup"><span data-stu-id="4368b-133">Specifies the path and name of the project file.</span></span> <span data-ttu-id="4368b-134">（请参阅备注。）如果未指定，则默认为当前目录。</span><span class="sxs-lookup"><span data-stu-id="4368b-134">(See the NOTE.) It defaults to the current directory if not specified.</span></span>

> [!NOTE]
> <span data-ttu-id="4368b-135">通过 `-p|--project` 选项使用项目文件的路径和名称。</span><span class="sxs-lookup"><span data-stu-id="4368b-135">Use the path and name of the project file with the `-p|--project` option.</span></span> <span data-ttu-id="4368b-136">CLI 中的回归可阻止当前提供文件夹路径。</span><span class="sxs-lookup"><span data-stu-id="4368b-136">A regression in the CLI prevents providing a folder path at this time.</span></span> <span data-ttu-id="4368b-137">若要了解详细信息并跟踪此问题，请参阅 [dotnet run -p，无法启动项目 (dotnet/cli #5992)](https://github.com/dotnet/cli/issues/5992)。</span><span class="sxs-lookup"><span data-stu-id="4368b-137">For more information and to track this issue, see [dotnet run -p, can not start a project (dotnet/cli #5992)](https://github.com/dotnet/cli/issues/5992).</span></span>

## <a name="examples"></a><span data-ttu-id="4368b-138">示例</span><span class="sxs-lookup"><span data-stu-id="4368b-138">Examples</span></span>

<span data-ttu-id="4368b-139">运行当前目录中的项目：</span><span class="sxs-lookup"><span data-stu-id="4368b-139">Run the project in the current directory:</span></span>

`dotnet run` 

<span data-ttu-id="4368b-140">运行指定的项目：</span><span class="sxs-lookup"><span data-stu-id="4368b-140">Run the specified project:</span></span>

`dotnet run --project /projects/proj1/proj1.csproj`

<span data-ttu-id="4368b-141">运行当前目录中的项目（在本例中，`--help` 参数被传递到应用程序，因为使用了 `--` 参数）：</span><span class="sxs-lookup"><span data-stu-id="4368b-141">Run the project in the current directory (the `--help` argument in this example is passed to the application, since the `--` argument is used):</span></span>

`dotnet run --configuration Release -- --help`

