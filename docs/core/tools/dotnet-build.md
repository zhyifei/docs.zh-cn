---
title: dotnet build 命令 - .NET Core CLI
description: dotnet build 命令可生成项目及其所有依赖项。
author: mairaw
ms.author: mairaw
ms.date: 05/25/2018
ms.openlocfilehash: dc5970fa1c8f3172916676819fa7789d84a5386e
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/17/2018
ms.locfileid: "45692971"
---
# <a name="dotnet-build"></a><span data-ttu-id="68cc1-103">dotnet 生成</span><span class="sxs-lookup"><span data-stu-id="68cc1-103">dotnet build</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="68cc1-104">name</span><span class="sxs-lookup"><span data-stu-id="68cc1-104">Name</span></span>

<span data-ttu-id="68cc1-105">`dotnet build` - 生成项目及其所有依赖项。</span><span class="sxs-lookup"><span data-stu-id="68cc1-105">`dotnet build` - Builds a project and all of its dependencies.</span></span>

## <a name="synopsis"></a><span data-ttu-id="68cc1-106">摘要</span><span class="sxs-lookup"><span data-stu-id="68cc1-106">Synopsis</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="68cc1-107">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="68cc1-107">.NET Core 2.x</span></span>](#tab/netcore2x)
```
dotnet build [<PROJECT>] [-c|--configuration] [-f|--framework] [--force] [--no-dependencies] [--no-incremental]
    [--no-restore] [-o|--output] [-r|--runtime] [-v|--verbosity] [--version-suffix]
dotnet build [-h|--help]
```
# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="68cc1-108">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="68cc1-108">.NET Core 1.x</span></span>](#tab/netcore1x)
```
dotnet build [<PROJECT>] [-c|--configuration] [-f|--framework] [--no-dependencies] [--no-incremental] [-o|--output]
    [-r|--runtime] [-v|--verbosity] [--version-suffix]
dotnet build [-h|--help]
```
---

## <a name="description"></a><span data-ttu-id="68cc1-109">描述</span><span class="sxs-lookup"><span data-stu-id="68cc1-109">Description</span></span>

<span data-ttu-id="68cc1-110">`dotnet build` 命令将项目及其依赖项生成为一组二进制文件。</span><span class="sxs-lookup"><span data-stu-id="68cc1-110">The `dotnet build` command builds the project and its dependencies into a set of binaries.</span></span> <span data-ttu-id="68cc1-111">二进制文件包括中间语言 (IL) 文件（带 *.dll* 扩展名）和用于调试的符号文件（带 *.pdb* 扩展名）中的项目的代码。</span><span class="sxs-lookup"><span data-stu-id="68cc1-111">The binaries include the project's code in Intermediate Language (IL) files with a *.dll* extension and symbol files used for debugging with a *.pdb* extension.</span></span> <span data-ttu-id="68cc1-112">生成依赖项 JSON 文件 (*\*.deps.json*)，该文件列出了应用程序的依赖项。</span><span class="sxs-lookup"><span data-stu-id="68cc1-112">A dependencies JSON file (*\*.deps.json*) is produced that lists the dependencies of the application.</span></span> <span data-ttu-id="68cc1-113">生成 *\*.runtimeconfig.json* 文件，该文件指定应用程序的共享运行时及其版本。</span><span class="sxs-lookup"><span data-stu-id="68cc1-113">A *\*.runtimeconfig.json* file is produced, which specifies the shared runtime and its version for the application.</span></span>

<span data-ttu-id="68cc1-114">如果项目有第三方依赖项（如来自 NuGet 的库），将从 NuGet 缓存解析这些依赖项，并且它们不适用于项目的生成输出。</span><span class="sxs-lookup"><span data-stu-id="68cc1-114">If the project has third-party dependencies, such as libraries from NuGet, they're resolved from the NuGet cache and aren't available with the project's built output.</span></span> <span data-ttu-id="68cc1-115">考虑到这一点，`dotnet build` 的产品还未准备好转移到另一台计算机进行运行。</span><span class="sxs-lookup"><span data-stu-id="68cc1-115">With that in mind, the product of `dotnet build` isn't ready to be transferred to another machine to run.</span></span> <span data-ttu-id="68cc1-116">这与 .NET Framework 的行为相反，后者在构建可执行项目（一个应用程序）时，将生成可在任何已安装 .NET Framework 的计算机上运行的输出。</span><span class="sxs-lookup"><span data-stu-id="68cc1-116">This is in contrast to the behavior of the .NET Framework in which building an executable project (an application) produces output that's runnable on any machine where the .NET Framework is installed.</span></span> <span data-ttu-id="68cc1-117">为了能够获得相似的 .NET Core 使用体验，需要使用 [dotnet publish](dotnet-publish.md) 命令。</span><span class="sxs-lookup"><span data-stu-id="68cc1-117">To have a similar experience with .NET Core, you need to use the [dotnet publish](dotnet-publish.md) command.</span></span> <span data-ttu-id="68cc1-118">有关详细信息，请参阅 [.NET Core 应用程序部署](../deploying/index.md)。</span><span class="sxs-lookup"><span data-stu-id="68cc1-118">For more information, see [.NET Core Application Deployment](../deploying/index.md).</span></span>

<span data-ttu-id="68cc1-119">构建需要 *project.assets.json* 文件，该文件列出了你的应用程序的依赖项。</span><span class="sxs-lookup"><span data-stu-id="68cc1-119">Building requires the *project.assets.json* file, which lists the dependencies of your application.</span></span> <span data-ttu-id="68cc1-120">此文件在 [`dotnet restore`](dotnet-restore.md) 执行时创建。</span><span class="sxs-lookup"><span data-stu-id="68cc1-120">The file is created when [`dotnet restore`](dotnet-restore.md) is executed.</span></span> <span data-ttu-id="68cc1-121">如果资产文件未就位，那么工具将无法解析引用程序集，进而导致错误生成。</span><span class="sxs-lookup"><span data-stu-id="68cc1-121">Without the assets file in place, the tooling cannot resolve reference assemblies, which results in errors.</span></span> <span data-ttu-id="68cc1-122">使用 .NET Core 1.x SDK，需要在运行 `dotnet build` 之前显式运行 `dotnet restore`。</span><span class="sxs-lookup"><span data-stu-id="68cc1-122">With .NET Core 1.x SDK, you needed to explicitly run the `dotnet restore` before running `dotnet build`.</span></span> <span data-ttu-id="68cc1-123">自 .NET Core 2.0 SDK 起，`dotnet restore` 在 `dotnet build` 运行时隐式运行。</span><span class="sxs-lookup"><span data-stu-id="68cc1-123">Starting with .NET Core 2.0 SDK, `dotnet restore` runs implicitly when you run `dotnet build`.</span></span> <span data-ttu-id="68cc1-124">若要在运行 build 命令时禁用隐式还原，可以传递 `--no-restore` 选项。</span><span class="sxs-lookup"><span data-stu-id="68cc1-124">If you want to disable implicit restore when running the build command, you can pass the `--no-restore` option.</span></span>

[!INCLUDE[dotnet restore note + options](~/includes/dotnet-restore-note-options.md)]

<span data-ttu-id="68cc1-125">`dotnet build` 使用 MSBuild 生成项目，因此它支持并行生成和增量生成。</span><span class="sxs-lookup"><span data-stu-id="68cc1-125">`dotnet build` uses MSBuild to build the project, so it supports both parallel and incremental builds.</span></span> <span data-ttu-id="68cc1-126">有关详细信息，请参阅[增量生成](/visualstudio/msbuild/incremental-builds)。</span><span class="sxs-lookup"><span data-stu-id="68cc1-126">For more information, see [Incremental Builds](/visualstudio/msbuild/incremental-builds).</span></span>

<span data-ttu-id="68cc1-127">除其自己的选项外，`dotnet build` 命令也接受 MSBuild 选项，如用来设置属性的 `/p` 或用来定义记录器的 `/l`。</span><span class="sxs-lookup"><span data-stu-id="68cc1-127">In addition to its options, the `dotnet build` command accepts MSBuild options, such as `/p` for setting properties or `/l` to define a logger.</span></span> <span data-ttu-id="68cc1-128">有关这些选项的详细信息，请参阅 [MSBuild 命令行参考](/visualstudio/msbuild/msbuild-command-line-reference)。</span><span class="sxs-lookup"><span data-stu-id="68cc1-128">For more information about these options, see the [MSBuild Command-Line Reference](/visualstudio/msbuild/msbuild-command-line-reference).</span></span>

<span data-ttu-id="68cc1-129">项目是否可执行由项目文件中的 `<OutputType>` 属性决定。</span><span class="sxs-lookup"><span data-stu-id="68cc1-129">Whether the project is executable or not is determined by the `<OutputType>` property in the project file.</span></span> <span data-ttu-id="68cc1-130">以下示例显示生成可执行代码的项目：</span><span class="sxs-lookup"><span data-stu-id="68cc1-130">The following example shows a project that produces executable code:</span></span>

```xml
<PropertyGroup>
  <OutputType>Exe</OutputType>
</PropertyGroup>
```

<span data-ttu-id="68cc1-131">若要生成库，则省略 `<OutputType>` 属性。</span><span class="sxs-lookup"><span data-stu-id="68cc1-131">In order to produce a library, omit the `<OutputType>` property.</span></span> <span data-ttu-id="68cc1-132">生成输出中的主要区别在于，针对某个库的 IL DLL 不包含入口点，并且不能执行。</span><span class="sxs-lookup"><span data-stu-id="68cc1-132">The main difference in built output is that the IL DLL for a library doesn't contain entry points and can't be executed.</span></span>

## <a name="arguments"></a><span data-ttu-id="68cc1-133">自变量</span><span class="sxs-lookup"><span data-stu-id="68cc1-133">Arguments</span></span>

`PROJECT`

<span data-ttu-id="68cc1-134">要生成的项目文件。</span><span class="sxs-lookup"><span data-stu-id="68cc1-134">The project file to build.</span></span> <span data-ttu-id="68cc1-135">如果未指定项目文件，MSBuild 会在当前工作目录中搜索以 *proj* 结尾的文件扩展名并使用该文件。</span><span class="sxs-lookup"><span data-stu-id="68cc1-135">If a project file is not specified, MSBuild searches the current working directory for a file that has a file extension that ends in *proj* and uses that file.</span></span>

## <a name="options"></a><span data-ttu-id="68cc1-136">选项</span><span class="sxs-lookup"><span data-stu-id="68cc1-136">Options</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="68cc1-137">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="68cc1-137">.NET Core 2.x</span></span>](#tab/netcore2x)

`-c|--configuration {Debug|Release}`

<span data-ttu-id="68cc1-138">定义生成配置。</span><span class="sxs-lookup"><span data-stu-id="68cc1-138">Defines the build configuration.</span></span> <span data-ttu-id="68cc1-139">默认值为 `Debug`。</span><span class="sxs-lookup"><span data-stu-id="68cc1-139">The default value is `Debug`.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="68cc1-140">编译特定[框架](../../standard/frameworks.md)。</span><span class="sxs-lookup"><span data-stu-id="68cc1-140">Compiles for a specific [framework](../../standard/frameworks.md).</span></span> <span data-ttu-id="68cc1-141">必须在[项目文件](csproj.md)中定义该框架。</span><span class="sxs-lookup"><span data-stu-id="68cc1-141">The framework must be defined in the [project file](csproj.md).</span></span>

`--force`

<span data-ttu-id="68cc1-142">强制解析所有依赖项，即使上次还原已成功，也不例外。</span><span class="sxs-lookup"><span data-stu-id="68cc1-142">Forces all dependencies to be resolved even if the last restore was successful.</span></span> <span data-ttu-id="68cc1-143">指定此标记等同于删除 project.assets.json 文件。</span><span class="sxs-lookup"><span data-stu-id="68cc1-143">Specifying this flag is the same as deleting the *project.assets.json* file.</span></span>

`-h|--help`

<span data-ttu-id="68cc1-144">打印出有关命令的简短帮助。</span><span class="sxs-lookup"><span data-stu-id="68cc1-144">Prints out a short help for the command.</span></span>

`--no-dependencies`

<span data-ttu-id="68cc1-145">忽略项目到项目 (P2P) 引用，并仅生成指定的根项目。</span><span class="sxs-lookup"><span data-stu-id="68cc1-145">Ignores project-to-project (P2P) references and only builds the specified root project.</span></span>

`--no-incremental`

<span data-ttu-id="68cc1-146">将生成标记为对增量生成不安全。</span><span class="sxs-lookup"><span data-stu-id="68cc1-146">Marks the build as unsafe for incremental build.</span></span> <span data-ttu-id="68cc1-147">此标记关闭增量编译，并强制完全重新生成项目依赖项关系图。</span><span class="sxs-lookup"><span data-stu-id="68cc1-147">This flag turns off incremental compilation and forces a clean rebuild of the project's dependency graph.</span></span>

`--no-restore`

<span data-ttu-id="68cc1-148">在生成期间不执行隐式还原。</span><span class="sxs-lookup"><span data-stu-id="68cc1-148">Doesn't execute an implicit restore during build.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="68cc1-149">放置生成二进制文件的目录。</span><span class="sxs-lookup"><span data-stu-id="68cc1-149">Directory in which to place the built binaries.</span></span> <span data-ttu-id="68cc1-150">指定此选项时还需要定义 `--framework`。</span><span class="sxs-lookup"><span data-stu-id="68cc1-150">You also need to define `--framework` when you specify this option.</span></span>

`-r|--runtime <RUNTIME_IDENTIFIER>`

<span data-ttu-id="68cc1-151">指定目标运行时。</span><span class="sxs-lookup"><span data-stu-id="68cc1-151">Specifies the target runtime.</span></span> <span data-ttu-id="68cc1-152">有关运行时标识符 (RID) 的列表，请参阅 [RID 目录](../rid-catalog.md)。</span><span class="sxs-lookup"><span data-stu-id="68cc1-152">For a list of Runtime Identifiers (RIDs), see the [RID catalog](../rid-catalog.md).</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="68cc1-153">设置命令的详细级别。</span><span class="sxs-lookup"><span data-stu-id="68cc1-153">Sets the verbosity level of the command.</span></span> <span data-ttu-id="68cc1-154">允许使用的值为 `q[uiet]`、`m[inimal]`、`n[ormal]`、`d[etailed]` 和 `diag[nostic]`。</span><span class="sxs-lookup"><span data-stu-id="68cc1-154">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

`--version-suffix <VERSION_SUFFIX>`

<span data-ttu-id="68cc1-155">在项目文件的版本字段中定义星号 (`*`) 版本后缀。</span><span class="sxs-lookup"><span data-stu-id="68cc1-155">Defines the version suffix for an asterisk (`*`) in the version field of the project file.</span></span> <span data-ttu-id="68cc1-156">格式遵循 NuGet 的版本准则。</span><span class="sxs-lookup"><span data-stu-id="68cc1-156">The format follows NuGet's version guidelines.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="68cc1-157">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="68cc1-157">.NET Core 1.x</span></span>](#tab/netcore1x)

`-c|--configuration {Debug|Release}`

<span data-ttu-id="68cc1-158">定义生成配置。</span><span class="sxs-lookup"><span data-stu-id="68cc1-158">Defines the build configuration.</span></span> <span data-ttu-id="68cc1-159">默认值为 `Debug`。</span><span class="sxs-lookup"><span data-stu-id="68cc1-159">The default value is `Debug`.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="68cc1-160">编译特定[框架](../../standard/frameworks.md)。</span><span class="sxs-lookup"><span data-stu-id="68cc1-160">Compiles for a specific [framework](../../standard/frameworks.md).</span></span> <span data-ttu-id="68cc1-161">必须在[项目文件](csproj.md)中定义该框架。</span><span class="sxs-lookup"><span data-stu-id="68cc1-161">The framework must be defined in the [project file](csproj.md).</span></span>

`-h|--help`

<span data-ttu-id="68cc1-162">打印出有关命令的简短帮助。</span><span class="sxs-lookup"><span data-stu-id="68cc1-162">Prints out a short help for the command.</span></span>

`--no-dependencies`

<span data-ttu-id="68cc1-163">忽略项目到项目 (P2P) 引用，并仅生成指定的根项目。</span><span class="sxs-lookup"><span data-stu-id="68cc1-163">Ignores project-to-project (P2P) references and only builds the specified root project.</span></span>

`--no-incremental`

<span data-ttu-id="68cc1-164">将生成标记为对增量生成不安全。</span><span class="sxs-lookup"><span data-stu-id="68cc1-164">Marks the build as unsafe for incremental build.</span></span> <span data-ttu-id="68cc1-165">此标记关闭增量编译，并强制完全重新生成项目依赖项关系图。</span><span class="sxs-lookup"><span data-stu-id="68cc1-165">This flag turns off incremental compilation and forces a clean rebuild of the project's dependency graph.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="68cc1-166">放置生成二进制文件的目录。</span><span class="sxs-lookup"><span data-stu-id="68cc1-166">Directory in which to place the built binaries.</span></span> <span data-ttu-id="68cc1-167">指定此选项时还需要定义 `--framework`。</span><span class="sxs-lookup"><span data-stu-id="68cc1-167">You also need to define `--framework` when you specify this option.</span></span>

`-r|--runtime <RUNTIME_IDENTIFIER>`

<span data-ttu-id="68cc1-168">指定目标运行时。</span><span class="sxs-lookup"><span data-stu-id="68cc1-168">Specifies the target runtime.</span></span> <span data-ttu-id="68cc1-169">有关运行时标识符 (RID) 的列表，请参阅 [RID 目录](../rid-catalog.md)。</span><span class="sxs-lookup"><span data-stu-id="68cc1-169">For a list of Runtime Identifiers (RIDs), see the [RID catalog](../rid-catalog.md).</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="68cc1-170">设置命令的详细级别。</span><span class="sxs-lookup"><span data-stu-id="68cc1-170">Sets the verbosity level of the command.</span></span> <span data-ttu-id="68cc1-171">允许使用的值为 `q[uiet]`、`m[inimal]`、`n[ormal]`、`d[etailed]` 和 `diag[nostic]`。</span><span class="sxs-lookup"><span data-stu-id="68cc1-171">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

`--version-suffix <VERSION_SUFFIX>`

<span data-ttu-id="68cc1-172">在项目文件的版本字段中定义星号 (`*`) 版本后缀。</span><span class="sxs-lookup"><span data-stu-id="68cc1-172">Defines the version suffix for an asterisk (`*`) in the version field of the project file.</span></span> <span data-ttu-id="68cc1-173">格式遵循 NuGet 的版本准则。</span><span class="sxs-lookup"><span data-stu-id="68cc1-173">The format follows NuGet's version guidelines.</span></span>

---

## <a name="examples"></a><span data-ttu-id="68cc1-174">示例</span><span class="sxs-lookup"><span data-stu-id="68cc1-174">Examples</span></span>

<span data-ttu-id="68cc1-175">生成项目及其依赖项：</span><span class="sxs-lookup"><span data-stu-id="68cc1-175">Build a project and its dependencies:</span></span>

`dotnet build`

<span data-ttu-id="68cc1-176">使用“发布”配置生成项目及其依赖项：</span><span class="sxs-lookup"><span data-stu-id="68cc1-176">Build a project and its dependencies using Release configuration:</span></span>

`dotnet build --configuration Release`

<span data-ttu-id="68cc1-177">针对特定运行时（本例中为 Ubuntu 16.04）生成项目及其依赖项：</span><span class="sxs-lookup"><span data-stu-id="68cc1-177">Build a project and its dependencies for a specific runtime (in this example, Ubuntu 16.04):</span></span>

`dotnet build --runtime ubuntu.16.04-x64`

<span data-ttu-id="68cc1-178">生成项目，并在还原操作过程中使用指定的 NuGet 包源（.NET Core SDK 2.0 及更高版本）：</span><span class="sxs-lookup"><span data-stu-id="68cc1-178">Build the project and use the specified NuGet package source during the restore operation (.NET Core SDK 2.0 and later versions):</span></span>

`dotnet build --source c:\packages\mypackages`