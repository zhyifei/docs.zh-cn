---
title: dotnet pack 命令 - .NET Core CLI
description: dotnet pack 命令可为 .NET Core 项目创建 NuGet 包。
author: mairaw
ms.author: mairaw
ms.date: 05/29/2018
ms.openlocfilehash: 8c2569ec7598b21fe9b673176143d0e54b9eb065
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/08/2018
ms.locfileid: "44204846"
---
# <a name="dotnet-pack"></a><span data-ttu-id="982e5-103">dotnet 包</span><span class="sxs-lookup"><span data-stu-id="982e5-103">dotnet pack</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="982e5-104">name</span><span class="sxs-lookup"><span data-stu-id="982e5-104">Name</span></span>

<span data-ttu-id="982e5-105">`dotnet pack` - 将代码打包到 NuGet 包。</span><span class="sxs-lookup"><span data-stu-id="982e5-105">`dotnet pack` - Packs the code into a NuGet package.</span></span>

## <a name="synopsis"></a><span data-ttu-id="982e5-106">摘要</span><span class="sxs-lookup"><span data-stu-id="982e5-106">Synopsis</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="982e5-107">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="982e5-107">.NET Core 2.x</span></span>](#tab/netcore2x)
```
dotnet pack [<PROJECT>] [-c|--configuration] [--force] [--include-source] [--include-symbols] [--no-build] [--no-dependencies]
    [--no-restore] [-o|--output] [--runtime] [-s|--serviceable] [-v|--verbosity] [--version-suffix]
dotnet pack [-h|--help]
```
# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="982e5-108">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="982e5-108">.NET Core 1.x</span></span>](#tab/netcore1x)
```
dotnet pack [<PROJECT>] [-c|--configuration] [--include-source] [--include-symbols] [--no-build] [-o|--output]
    [-s|--serviceable] [-v|--verbosity] [--version-suffix]
dotnet pack [-h|--help]
```
---

## <a name="description"></a><span data-ttu-id="982e5-109">描述</span><span class="sxs-lookup"><span data-stu-id="982e5-109">Description</span></span>

<span data-ttu-id="982e5-110">`dotnet pack` 命令生成项目并创建 NuGet 包。</span><span class="sxs-lookup"><span data-stu-id="982e5-110">The `dotnet pack` command builds the project and creates NuGet packages.</span></span> <span data-ttu-id="982e5-111">该命令的结果是一个 NuGet 包。</span><span class="sxs-lookup"><span data-stu-id="982e5-111">The result of this command is a NuGet package.</span></span> <span data-ttu-id="982e5-112">如果 `--include-symbols` 选项存在，则创建包含调试符号的另一个包。</span><span class="sxs-lookup"><span data-stu-id="982e5-112">If the `--include-symbols` option is present, another package containing the debug symbols is created.</span></span>

<span data-ttu-id="982e5-113">将被打包项目的 NuGet 依赖项添加到 *.nuspec* 文件，以便在安装包时可以进行正确解析。</span><span class="sxs-lookup"><span data-stu-id="982e5-113">NuGet dependencies of the packed project are added to the *.nuspec* file, so they're properly resolved when the package is installed.</span></span> <span data-ttu-id="982e5-114">项目到项目的引用不会打包到项目内。</span><span class="sxs-lookup"><span data-stu-id="982e5-114">Project-to-project references aren't packaged inside the project.</span></span> <span data-ttu-id="982e5-115">目前，如果具有项目到项目的依赖项，则每个项目均必须包含一个包。</span><span class="sxs-lookup"><span data-stu-id="982e5-115">Currently, you must have a package per project if you have project-to-project dependencies.</span></span>

<span data-ttu-id="982e5-116">默认情况下，`dotnet pack` 先构建项目。</span><span class="sxs-lookup"><span data-stu-id="982e5-116">By default, `dotnet pack` builds the project first.</span></span> <span data-ttu-id="982e5-117">如果希望避免此行为，则传递 `--no-build` 选项。</span><span class="sxs-lookup"><span data-stu-id="982e5-117">If you wish to avoid this behavior, pass the `--no-build` option.</span></span> <span data-ttu-id="982e5-118">此选项在持续集成 (CI) 生成方案中通常非常有用，你可以知道代码是之前生成的。</span><span class="sxs-lookup"><span data-stu-id="982e5-118">This option is often useful in Continuous Integration (CI) build scenarios where you know the code was previously built.</span></span>

<span data-ttu-id="982e5-119">可向 `dotnet pack` 命令提供 MSBuild 属性，用于打包进程。</span><span class="sxs-lookup"><span data-stu-id="982e5-119">You can provide MSBuild properties to the `dotnet pack` command for the packing process.</span></span> <span data-ttu-id="982e5-120">有关详细信息，请参阅 [NuGet 元数据属性](csproj.md#nuget-metadata-properties)和 [MSBuild 命令行引用](/visualstudio/msbuild/msbuild-command-line-reference)。</span><span class="sxs-lookup"><span data-stu-id="982e5-120">For more information, see [NuGet metadata properties](csproj.md#nuget-metadata-properties) and the [MSBuild Command-Line Reference](/visualstudio/msbuild/msbuild-command-line-reference).</span></span> <span data-ttu-id="982e5-121">[示例](#examples)部分介绍了如何在不同的情况下使用 MSBuild /p 开关。</span><span class="sxs-lookup"><span data-stu-id="982e5-121">The [Examples](#examples) section shows how to use the MSBuild /p switch for a couple of different scenarios.</span></span>

[!INCLUDE[dotnet restore note + options](~/includes/dotnet-restore-note-options.md)]

## <a name="arguments"></a><span data-ttu-id="982e5-122">自变量</span><span class="sxs-lookup"><span data-stu-id="982e5-122">Arguments</span></span>

`PROJECT`

<span data-ttu-id="982e5-123">要打包的项目。</span><span class="sxs-lookup"><span data-stu-id="982e5-123">The project to pack.</span></span> <span data-ttu-id="982e5-124">它可能是 [csproj 文件](csproj.md)或目录的路径。</span><span class="sxs-lookup"><span data-stu-id="982e5-124">It's either a path to a [csproj file](csproj.md) or to a directory.</span></span> <span data-ttu-id="982e5-125">如果未指定，则默认为当前目录。</span><span class="sxs-lookup"><span data-stu-id="982e5-125">If not specified, it defaults to the current directory.</span></span>

## <a name="options"></a><span data-ttu-id="982e5-126">选项</span><span class="sxs-lookup"><span data-stu-id="982e5-126">Options</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="982e5-127">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="982e5-127">.NET Core 2.x</span></span>](#tab/netcore2x)

`-c|--configuration {Debug|Release}`

<span data-ttu-id="982e5-128">定义生成配置。</span><span class="sxs-lookup"><span data-stu-id="982e5-128">Defines the build configuration.</span></span> <span data-ttu-id="982e5-129">默认值为 `Debug`。</span><span class="sxs-lookup"><span data-stu-id="982e5-129">The default value is `Debug`.</span></span>

`--force`

<span data-ttu-id="982e5-130">强制解析所有依赖项，即使上次还原已成功，也不例外。</span><span class="sxs-lookup"><span data-stu-id="982e5-130">Forces all dependencies to be resolved even if the last restore was successful.</span></span> <span data-ttu-id="982e5-131">指定此标记等同于删除 project.assets.json 文件。</span><span class="sxs-lookup"><span data-stu-id="982e5-131">Specifying this flag is the same as deleting the *project.assets.json* file.</span></span>

`-h|--help`

<span data-ttu-id="982e5-132">打印出有关命令的简短帮助。</span><span class="sxs-lookup"><span data-stu-id="982e5-132">Prints out a short help for the command.</span></span>

`--include-source`

<span data-ttu-id="982e5-133">将源文件包括在 NuGet 包中。</span><span class="sxs-lookup"><span data-stu-id="982e5-133">Includes the source files in the NuGet package.</span></span> <span data-ttu-id="982e5-134">源文件包括在 `nupkg` 内的 `src` 文件夹中。</span><span class="sxs-lookup"><span data-stu-id="982e5-134">The sources files are included in the `src` folder within the `nupkg`.</span></span>

`--include-symbols`

<span data-ttu-id="982e5-135">生成符号 `nupkg`。</span><span class="sxs-lookup"><span data-stu-id="982e5-135">Generates the symbols `nupkg`.</span></span>

`--no-build`

<span data-ttu-id="982e5-136">打包前不生成项目。</span><span class="sxs-lookup"><span data-stu-id="982e5-136">Doesn't build the project before packing.</span></span> <span data-ttu-id="982e5-137">还隐式设置 `--no-restore` 标记。</span><span class="sxs-lookup"><span data-stu-id="982e5-137">It also implicit sets the `--no-restore` flag.</span></span>

`--no-dependencies`

<span data-ttu-id="982e5-138">忽略项目间引用，仅还原根项目。</span><span class="sxs-lookup"><span data-stu-id="982e5-138">Ignores project-to-project references and only restores the root project.</span></span>

`--no-restore`

<span data-ttu-id="982e5-139">运行此命令时不执行隐式还原。</span><span class="sxs-lookup"><span data-stu-id="982e5-139">Doesn't execute an implicit restore when running the command.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="982e5-140">将生成的包放置在指定目录。</span><span class="sxs-lookup"><span data-stu-id="982e5-140">Places the built packages in the directory specified.</span></span>

`--runtime <RUNTIME_IDENTIFIER>`

<span data-ttu-id="982e5-141">指定要为其还原包的目标运行时。</span><span class="sxs-lookup"><span data-stu-id="982e5-141">Specifies the target runtime to restore packages for.</span></span> <span data-ttu-id="982e5-142">有关运行时标识符 (RID) 的列表，请参阅 [RID 目录](../rid-catalog.md)。</span><span class="sxs-lookup"><span data-stu-id="982e5-142">For a list of Runtime Identifiers (RIDs), see the [RID catalog](../rid-catalog.md).</span></span>

`-s|--serviceable`

<span data-ttu-id="982e5-143">设置包中可用的标志。</span><span class="sxs-lookup"><span data-stu-id="982e5-143">Sets the serviceable flag in the package.</span></span> <span data-ttu-id="982e5-144">有关详细信息，请参阅 [.NET 博客：.NET 4.5.1 支持 .NET NuGet 库的 Microsoft 安全更新](https://aka.ms/nupkgservicing)。</span><span class="sxs-lookup"><span data-stu-id="982e5-144">For more information, see [.NET Blog: .NET 4.5.1 Supports Microsoft Security Updates for .NET NuGet Libraries](https://aka.ms/nupkgservicing).</span></span>

`--version-suffix <VERSION_SUFFIX>`

<span data-ttu-id="982e5-145">定义项目中 `$(VersionSuffix)` MSBuild 属性的值。</span><span class="sxs-lookup"><span data-stu-id="982e5-145">Defines the value for the `$(VersionSuffix)` MSBuild property in the project.</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="982e5-146">设置命令的详细级别。</span><span class="sxs-lookup"><span data-stu-id="982e5-146">Sets the verbosity level of the command.</span></span> <span data-ttu-id="982e5-147">允许使用的值为 `q[uiet]`、`m[inimal]`、`n[ormal]`、`d[etailed]` 和 `diag[nostic]`。</span><span class="sxs-lookup"><span data-stu-id="982e5-147">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="982e5-148">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="982e5-148">.NET Core 1.x</span></span>](#tab/netcore1x)

`-c|--configuration {Debug|Release}`

<span data-ttu-id="982e5-149">定义生成配置。</span><span class="sxs-lookup"><span data-stu-id="982e5-149">Defines the build configuration.</span></span> <span data-ttu-id="982e5-150">默认值为 `Debug`。</span><span class="sxs-lookup"><span data-stu-id="982e5-150">The default value is `Debug`.</span></span>

`-h|--help`

<span data-ttu-id="982e5-151">打印出有关命令的简短帮助。</span><span class="sxs-lookup"><span data-stu-id="982e5-151">Prints out a short help for the command.</span></span>

`--include-source`

<span data-ttu-id="982e5-152">将源文件包括在 NuGet 包中。</span><span class="sxs-lookup"><span data-stu-id="982e5-152">Includes the source files in the NuGet package.</span></span> <span data-ttu-id="982e5-153">源文件包括在 `nupkg` 内的 `src` 文件夹中。</span><span class="sxs-lookup"><span data-stu-id="982e5-153">The sources files are included in the `src` folder within the `nupkg`.</span></span>

`--include-symbols`

<span data-ttu-id="982e5-154">生成符号 `nupkg`。</span><span class="sxs-lookup"><span data-stu-id="982e5-154">Generates the symbols `nupkg`.</span></span>

`--no-build`

<span data-ttu-id="982e5-155">打包前不生成项目。</span><span class="sxs-lookup"><span data-stu-id="982e5-155">Doesn't build the project before packing.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="982e5-156">将生成的包放置在指定目录。</span><span class="sxs-lookup"><span data-stu-id="982e5-156">Places the built packages in the directory specified.</span></span>

`-s|--serviceable`

<span data-ttu-id="982e5-157">设置包中可用的标志。</span><span class="sxs-lookup"><span data-stu-id="982e5-157">Sets the serviceable flag in the package.</span></span> <span data-ttu-id="982e5-158">有关详细信息，请参阅 [.NET 博客：.NET 4.5.1 支持 .NET NuGet 库的 Microsoft 安全更新](https://aka.ms/nupkgservicing)。</span><span class="sxs-lookup"><span data-stu-id="982e5-158">For more information, see [.NET Blog: .NET 4.5.1 Supports Microsoft Security Updates for .NET NuGet Libraries](https://aka.ms/nupkgservicing).</span></span>

`--version-suffix <VERSION_SUFFIX>`

<span data-ttu-id="982e5-159">定义项目中 `$(VersionSuffix)` MSBuild 属性的值。</span><span class="sxs-lookup"><span data-stu-id="982e5-159">Defines the value for the `$(VersionSuffix)` MSBuild property in the project.</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="982e5-160">设置命令的详细级别。</span><span class="sxs-lookup"><span data-stu-id="982e5-160">Sets the verbosity level of the command.</span></span> <span data-ttu-id="982e5-161">允许使用的值为 `q[uiet]`、`m[inimal]`、`n[ormal]`、`d[etailed]` 和 `diag[nostic]`。</span><span class="sxs-lookup"><span data-stu-id="982e5-161">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

---

## <a name="examples"></a><span data-ttu-id="982e5-162">示例</span><span class="sxs-lookup"><span data-stu-id="982e5-162">Examples</span></span>

<span data-ttu-id="982e5-163">打包当前目录中的项目：</span><span class="sxs-lookup"><span data-stu-id="982e5-163">Pack the project in the current directory:</span></span>

`dotnet pack`

<span data-ttu-id="982e5-164">打包 `app1` 项目：</span><span class="sxs-lookup"><span data-stu-id="982e5-164">Pack the `app1` project:</span></span>

`dotnet pack ~/projects/app1/project.csproj`

<span data-ttu-id="982e5-165">打包当前目录中的项目并将生成的包放置到 `nupkgs` 文件夹：</span><span class="sxs-lookup"><span data-stu-id="982e5-165">Pack the project in the current directory and place the resulting packages into the `nupkgs` folder:</span></span>

`dotnet pack --output nupkgs`

<span data-ttu-id="982e5-166">将当前目录中的项目打包到 `nupkgs` 文件夹并跳过生成步骤：</span><span class="sxs-lookup"><span data-stu-id="982e5-166">Pack the project in the current directory into the `nupkgs` folder and skip the build step:</span></span>

`dotnet pack --no-build --output nupkgs`

<span data-ttu-id="982e5-167">将项目的版本后缀配置为 *.csproj* 文件中的 `<VersionSuffix>$(VersionSuffix)</VersionSuffix>`，使用给定的后缀打包当前项目，并更新生成的程序包版本：</span><span class="sxs-lookup"><span data-stu-id="982e5-167">With the project's version suffix configured as `<VersionSuffix>$(VersionSuffix)</VersionSuffix>` in the *.csproj* file, pack the current project and update the resulting package version with the given suffix:</span></span>

`dotnet pack --version-suffix "ci-1234"`

<span data-ttu-id="982e5-168">使用 `PackageVersion` MSBuild 属性将包版本设置为 `2.1.0`：</span><span class="sxs-lookup"><span data-stu-id="982e5-168">Set the package version to `2.1.0` with the `PackageVersion` MSBuild property:</span></span>

`dotnet pack /p:PackageVersion=2.1.0`

<span data-ttu-id="982e5-169">打包特定[目标框架](../../standard/frameworks.md)的项目：</span><span class="sxs-lookup"><span data-stu-id="982e5-169">Pack the project for a specific [target framework](../../standard/frameworks.md):</span></span>

`dotnet pack /p:TargetFrameworks=net45`

<span data-ttu-id="982e5-170">打包项目，并使用特定运行时 (Windows 10) 进行还原操作（.NET Core SDK 2.0 及更高版本）：</span><span class="sxs-lookup"><span data-stu-id="982e5-170">Pack the project and use a specific runtime (Windows 10) for the restore operation (.NET Core SDK 2.0 and later versions):</span></span>

`dotnet pack --runtime win10-x64`