---
title: "dotnet-build 命令 - .NET Core CLI"
description: "dotnet-build 命令可生成项目及其所有依赖项。"
keywords: "dotnet-build, CLI, CLI 命令, .NET Core"
author: blackdwarf
ms.author: mairaw
ms.date: 03/15/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: 5e1a2bc4-a919-4a86-8f33-a9b218b1fcb3
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: d2006b15978f384e53e43a0a2562e81d10582abd
ms.contentlocale: zh-cn
ms.lasthandoff: 07/28/2017

---

# <a name="dotnet-build"></a><span data-ttu-id="32aa9-104">dotnet-build</span><span class="sxs-lookup"><span data-stu-id="32aa9-104">dotnet-build</span></span>

## <a name="name"></a><span data-ttu-id="32aa9-105">名称</span><span class="sxs-lookup"><span data-stu-id="32aa9-105">Name</span></span>

<span data-ttu-id="32aa9-106">`dotnet-build` - 生成项目及其所有依赖项。</span><span class="sxs-lookup"><span data-stu-id="32aa9-106">`dotnet-build` - Builds a project and all of its dependencies.</span></span>

## <a name="synopsis"></a><span data-ttu-id="32aa9-107">摘要</span><span class="sxs-lookup"><span data-stu-id="32aa9-107">Synopsis</span></span>

`dotnet build [<PROJECT>] [-o|--output] [-f|--framework] [-c|--configuration] [-r|--runtime] [--version-suffix] [--no-incremental] [--no-dependencies] [-v|--verbosity] [-h|--help]`

## <a name="description"></a><span data-ttu-id="32aa9-108">描述</span><span class="sxs-lookup"><span data-stu-id="32aa9-108">Description</span></span>

<span data-ttu-id="32aa9-109">`dotnet build` 命令将项目及其依赖项生成为一组二进制文件。</span><span class="sxs-lookup"><span data-stu-id="32aa9-109">The `dotnet build` command builds the project and its dependencies into a set of binaries.</span></span> <span data-ttu-id="32aa9-110">二进制文件包括中间语言 (IL) 文件（带 *.dll* 扩展名）和用于调试的符号文件（带 *.pdb* 扩展名）中的项目的代码。</span><span class="sxs-lookup"><span data-stu-id="32aa9-110">The binaries include the project's code in Intermediate Language (IL) files with a *.dll* extension and symbol files used for debugging with a *.pdb* extension.</span></span> <span data-ttu-id="32aa9-111">生成依赖项 JSON 文件 (*\*.deps.json*)，该文件列出了应用程序的依赖项。</span><span class="sxs-lookup"><span data-stu-id="32aa9-111">A dependencies JSON file (*\*.deps.json*) is produced that lists the dependencies of the application.</span></span> <span data-ttu-id="32aa9-112">生成 *\*.runtimeconfig.json* 文件，该文件指定应用程序的共享运行时及其版本。</span><span class="sxs-lookup"><span data-stu-id="32aa9-112">A *\*.runtimeconfig.json* file is produced, which specifies the shared runtime and its version for the application.</span></span>

<span data-ttu-id="32aa9-113">如果项目有第三方依赖项（如来自 NuGet 的库），将从 NuGet 缓存解析这些依赖项，并且它们不适用于项目的生成输出。</span><span class="sxs-lookup"><span data-stu-id="32aa9-113">If the project has third-party dependencies, such as libraries from NuGet, they're resolved from the NuGet cache and aren't available with the project's built output.</span></span> <span data-ttu-id="32aa9-114">考虑到这一点，`dotnet build` 的产品还未准备好转移到另一台计算机进行运行。</span><span class="sxs-lookup"><span data-stu-id="32aa9-114">With that in mind, the product of `dotnet build` isn't ready to be transferred to another machine to run.</span></span> <span data-ttu-id="32aa9-115">这与 .NET Framework 的行为相反，后者在构建可执行项目（一个应用程序）时，将生成可在任何已安装 .NET Framework 的计算机上运行的输出。</span><span class="sxs-lookup"><span data-stu-id="32aa9-115">This is in contrast to the behavior of the .NET Framework in which building an executable project (an application) produces output that's runnable on any machine where the .NET Framework is installed.</span></span> <span data-ttu-id="32aa9-116">为了在使用 .NET Core 时获得相似的体验，可使用 [dotnet publish](dotnet-publish.md) 命令。</span><span class="sxs-lookup"><span data-stu-id="32aa9-116">To have a similar experience with .NET Core, you use the [dotnet publish](dotnet-publish.md) command.</span></span> <span data-ttu-id="32aa9-117">有关详细信息，请参阅 [.NET Core 应用程序部署](../deploying/index.md)。</span><span class="sxs-lookup"><span data-stu-id="32aa9-117">For more information, see [.NET Core Application Deployment](../deploying/index.md).</span></span> 

<span data-ttu-id="32aa9-118">构建需要 *project.assets.json* 文件，该文件列出了你的应用程序的依赖项。</span><span class="sxs-lookup"><span data-stu-id="32aa9-118">Building requires the *project.assets.json* file, which lists the dependencies of your application.</span></span> <span data-ttu-id="32aa9-119">在构建项目前执行 [`dotnet restore`](dotnet-restore.md) 时创建了该文件。</span><span class="sxs-lookup"><span data-stu-id="32aa9-119">The file is created when you execute [`dotnet restore`](dotnet-restore.md) before building the project.</span></span> <span data-ttu-id="32aa9-120">如果未正确放置资产文件，则工具无法解析引用程序集，这会导致错误。</span><span class="sxs-lookup"><span data-stu-id="32aa9-120">Without the assets file in place, the tooling cannot resolve reference assemblies, which will result in errors.</span></span>

<span data-ttu-id="32aa9-121">`dotnet build` 使用 MSBuild 构建项目；因此，它支持并行生成和增量生成。</span><span class="sxs-lookup"><span data-stu-id="32aa9-121">`dotnet build` uses MSBuild to build the project; thus, it supports both parallel and incremental builds.</span></span> <span data-ttu-id="32aa9-122">有关详细信息，请参阅[增量生成](/visualstudio/msbuild/incremental-builds)。</span><span class="sxs-lookup"><span data-stu-id="32aa9-122">Refer to [Incremental Builds](/visualstudio/msbuild/incremental-builds) for more information.</span></span> 

<span data-ttu-id="32aa9-123">除其自己的选项外，`dotnet build` 命令也接受 MSBuild 选项，如用来设置属性的 `/p` 或用来定义记录器的 `/l`。</span><span class="sxs-lookup"><span data-stu-id="32aa9-123">In addition to its options, the `dotnet build` command accepts MSBuild options, such as `/p` for setting properties or `/l` to define a logger.</span></span> <span data-ttu-id="32aa9-124">在 [MSBuild 命令行引用](/visualstudio/msbuild/msbuild-command-line-reference)中了解这些选项的详细信息。</span><span class="sxs-lookup"><span data-stu-id="32aa9-124">Learn more about these options in the [MSBuild Command-Line Reference](/visualstudio/msbuild/msbuild-command-line-reference).</span></span> 

<span data-ttu-id="32aa9-125">项目是否可执行由项目文件中的 `<OutputType>` 属性决定。</span><span class="sxs-lookup"><span data-stu-id="32aa9-125">Whether the project is executable or not is determined by the `<OutputType>` property in the project file.</span></span> <span data-ttu-id="32aa9-126">以下示例显示会生成可执行代码的项目：</span><span class="sxs-lookup"><span data-stu-id="32aa9-126">The following example shows a project that will produce executable code:</span></span>

```xml
<PropertyGroup>
  <OutputType>Exe</OutputType>
</PropertyGroup>
```

<span data-ttu-id="32aa9-127">若要生成库，则省略 `<OutputType>` 属性。</span><span class="sxs-lookup"><span data-stu-id="32aa9-127">In order to produce a library, omit the `<OutputType>` property.</span></span> <span data-ttu-id="32aa9-128">生成输出中的主要区别在于，针对某个库的 IL DLL 不包含入口点，并且不能执行。</span><span class="sxs-lookup"><span data-stu-id="32aa9-128">The main difference in built output is that the IL DLL for a library doesn't contain entry points and can't be executed.</span></span> 

## <a name="arguments"></a><span data-ttu-id="32aa9-129">参数</span><span class="sxs-lookup"><span data-stu-id="32aa9-129">Arguments</span></span>

`PROJECT`

<span data-ttu-id="32aa9-130">要生成的项目文件。</span><span class="sxs-lookup"><span data-stu-id="32aa9-130">The project file to build.</span></span> <span data-ttu-id="32aa9-131">如果未指定项目文件，MSBuild 会在当前工作目录中搜索以 *proj* 结尾的文件扩展名并使用该文件。</span><span class="sxs-lookup"><span data-stu-id="32aa9-131">If a project file is not specified, MSBuild searches the current working directory for a file that has a file extension that ends in *proj* and uses that file.</span></span>

## <a name="options"></a><span data-ttu-id="32aa9-132">选项</span><span class="sxs-lookup"><span data-stu-id="32aa9-132">Options</span></span>

`-h|--help`

<span data-ttu-id="32aa9-133">打印出有关命令的简短帮助。</span><span class="sxs-lookup"><span data-stu-id="32aa9-133">Prints out a short help for the command.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="32aa9-134">放置生成二进制文件的目录。</span><span class="sxs-lookup"><span data-stu-id="32aa9-134">Directory in which to place the built binaries.</span></span> <span data-ttu-id="32aa9-135">指定此选项时还需要定义 `--framework`。</span><span class="sxs-lookup"><span data-stu-id="32aa9-135">You also need to define `--framework` when you specify this option.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="32aa9-136">编译特定[框架](../../standard/frameworks.md)。</span><span class="sxs-lookup"><span data-stu-id="32aa9-136">Compiles for a specific [framework](../../standard/frameworks.md).</span></span> <span data-ttu-id="32aa9-137">必须在[项目文件](csproj.md)中定义该框架。</span><span class="sxs-lookup"><span data-stu-id="32aa9-137">The framework must be defined in the [project file](csproj.md).</span></span>

`-c|--configuration <CONFIGURATION>`

<span data-ttu-id="32aa9-138">定义生成配置。</span><span class="sxs-lookup"><span data-stu-id="32aa9-138">Defines the build configuration.</span></span> <span data-ttu-id="32aa9-139">如果省略，则生成配置默认为 `Debug`。</span><span class="sxs-lookup"><span data-stu-id="32aa9-139">If omitted, the build configuration defaults to `Debug`.</span></span> <span data-ttu-id="32aa9-140">使用 `Release` 生成发布配置。</span><span class="sxs-lookup"><span data-stu-id="32aa9-140">Use `Release` build a Release configuration.</span></span>

`-r|--runtime <RUNTIME_IDENTIFIER>`

<span data-ttu-id="32aa9-141">指定目标运行时。</span><span class="sxs-lookup"><span data-stu-id="32aa9-141">Specifies the target runtime.</span></span> <span data-ttu-id="32aa9-142">有关运行时标识符 (RID) 的列表，请参阅 [RID 目录](../rid-catalog.md)。</span><span class="sxs-lookup"><span data-stu-id="32aa9-142">For a list of Runtime Identifiers (RIDs), see the [RID catalog](../rid-catalog.md).</span></span>

`--version-suffix <VERSION_SUFFIX>`

<span data-ttu-id="32aa9-143">在项目文件的版本字段中定义星号 (`*`) 版本后缀。</span><span class="sxs-lookup"><span data-stu-id="32aa9-143">Defines the version suffix for an asterisk (`*`) in the version field of the project file.</span></span> <span data-ttu-id="32aa9-144">格式遵循 NuGet 的版本准则。</span><span class="sxs-lookup"><span data-stu-id="32aa9-144">The format follows NuGet's version guidelines.</span></span>

`--no-incremental`

<span data-ttu-id="32aa9-145">将生成标记为对增量生成不安全。</span><span class="sxs-lookup"><span data-stu-id="32aa9-145">Marks the build as unsafe for incremental build.</span></span> <span data-ttu-id="32aa9-146">这将关闭增量编译并强制完全重新生成项目依赖项关系图。</span><span class="sxs-lookup"><span data-stu-id="32aa9-146">This turns off incremental compilation and forces a clean rebuild of the project's dependency graph.</span></span>

`--no-dependencies`

<span data-ttu-id="32aa9-147">忽略项目间 (P2P) 引用，并仅生成指定要生成的根项目。</span><span class="sxs-lookup"><span data-stu-id="32aa9-147">Ignores project-to-project (P2P) references and only builds the root project specified to build.</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="32aa9-148">设置命令的详细级别。</span><span class="sxs-lookup"><span data-stu-id="32aa9-148">Sets the verbosity level of the command.</span></span> <span data-ttu-id="32aa9-149">允许使用的值为 `q[uiet]`、`m[inimal]`、`n[ormal]`、`d[etailed]` 和 `diag[nostic]`。</span><span class="sxs-lookup"><span data-stu-id="32aa9-149">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

## <a name="examples"></a><span data-ttu-id="32aa9-150">示例</span><span class="sxs-lookup"><span data-stu-id="32aa9-150">Examples</span></span>

<span data-ttu-id="32aa9-151">生成项目及其依赖项：</span><span class="sxs-lookup"><span data-stu-id="32aa9-151">Build a project and its dependencies:</span></span>

`dotnet build`

<span data-ttu-id="32aa9-152">使用“发布”配置生成项目及其依赖项：</span><span class="sxs-lookup"><span data-stu-id="32aa9-152">Build a project and its dependencies using Release configuration:</span></span>

`dotnet build --configuration Release`

<span data-ttu-id="32aa9-153">针对特定运行时（本例中为 Ubuntu 16.04）生成项目及其依赖项：</span><span class="sxs-lookup"><span data-stu-id="32aa9-153">Build a project and its dependencies for a specific runtime (in this example, Ubuntu 16.04):</span></span>

`dotnet build --runtime ubuntu.16.04-x64`

