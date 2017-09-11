---
title: "dotnet-pack 命令 - .NET Core CLI"
description: "dotnet-pack 命令可为 .NET Core 项目创建 NuGet 包。"
keywords: "dotnet-pack, CLI, CLI 命令, .NET Core"
author: blackdwarf
ms.author: mairaw
ms.date: 03/15/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: 8dbbb3f7-b817-4161-a6c8-a3489d05e051
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 04b967fdf6578098caae8c21604c5d6160eb6775
ms.contentlocale: zh-cn
ms.lasthandoff: 07/28/2017

---

# <a name="dotnet-pack"></a><span data-ttu-id="33167-104">dotnet-pack</span><span class="sxs-lookup"><span data-stu-id="33167-104">dotnet-pack</span></span>

## <a name="name"></a><span data-ttu-id="33167-105">名称</span><span class="sxs-lookup"><span data-stu-id="33167-105">Name</span></span>

<span data-ttu-id="33167-106">`dotnet-pack` - 将代码打包到 NuGet 包。</span><span class="sxs-lookup"><span data-stu-id="33167-106">`dotnet-pack` - Packs the code into a NuGet package.</span></span>

## <a name="synopsis"></a><span data-ttu-id="33167-107">摘要</span><span class="sxs-lookup"><span data-stu-id="33167-107">Synopsis</span></span>

`dotnet pack [<PROJECT>] [-o|--output] [--no-build] [--include-symbols] [--include-source] [-c|--configuration] [--version-suffix <VERSION_SUFFIX>] [-s|--serviceable] [-v|--verbosity] [-h|--help]`

## <a name="description"></a><span data-ttu-id="33167-108">描述</span><span class="sxs-lookup"><span data-stu-id="33167-108">Description</span></span>

<span data-ttu-id="33167-109">`dotnet pack` 命令生成项目并创建 NuGet 包。</span><span class="sxs-lookup"><span data-stu-id="33167-109">The `dotnet pack` command builds the project and creates NuGet packages.</span></span> <span data-ttu-id="33167-110">该命令的结果是一个 NuGet 包。</span><span class="sxs-lookup"><span data-stu-id="33167-110">The result of this command is a NuGet package.</span></span> <span data-ttu-id="33167-111">如果 `--include-symbols` 选项存在，则创建包含调试符号的另一个包。</span><span class="sxs-lookup"><span data-stu-id="33167-111">If the `--include-symbols` option is present, another package containing the debug symbols is created.</span></span> 

<span data-ttu-id="33167-112">将被打包项目的 NuGet 依赖项添加到 *.nuspec* 文件，以便在安装包时可以进行正确解析。</span><span class="sxs-lookup"><span data-stu-id="33167-112">NuGet dependencies of the packed project are added to the *.nuspec* file, so they're properly resolved when the package is installed.</span></span> <span data-ttu-id="33167-113">项目到项目的引用不会打包到项目内。</span><span class="sxs-lookup"><span data-stu-id="33167-113">Project-to-project references aren't packaged inside the project.</span></span> <span data-ttu-id="33167-114">目前，如果具有项目到项目的依赖项，则每个项目均必须包含一个包。</span><span class="sxs-lookup"><span data-stu-id="33167-114">Currently, you must have a package per project if you have project-to-project dependencies.</span></span>

<span data-ttu-id="33167-115">默认情况下，`dotnet pack` 先构建项目。</span><span class="sxs-lookup"><span data-stu-id="33167-115">By default, `dotnet pack` builds the project first.</span></span> <span data-ttu-id="33167-116">如果希望避免此行为，则传递 `--no-build` 选项。</span><span class="sxs-lookup"><span data-stu-id="33167-116">If you wish to avoid this behavior, pass the `--no-build` option.</span></span> <span data-ttu-id="33167-117">这通常在持续集成 (CI) 生成方案中非常有用，在其中你可以知道代码是之前生成的。</span><span class="sxs-lookup"><span data-stu-id="33167-117">This is often useful in Continuous Integration (CI) build scenarios where you know the code was previously built.</span></span>

<span data-ttu-id="33167-118">可向 `dotnet pack` 命令提供 MSBuild 属性，用于打包进程。</span><span class="sxs-lookup"><span data-stu-id="33167-118">You can provide MSBuild properties to the `dotnet pack` command for the packing process.</span></span> <span data-ttu-id="33167-119">有关详细信息，请参阅 [NuGet 元数据属性](csproj.md#nuget-metadata-properties)和 [MSBuild 命令行引用](/visualstudio/msbuild/msbuild-command-line-reference)。</span><span class="sxs-lookup"><span data-stu-id="33167-119">For more information, see [NuGet metadata properties](csproj.md#nuget-metadata-properties) and the [MSBuild Command-Line Reference](/visualstudio/msbuild/msbuild-command-line-reference).</span></span>

## <a name="arguments"></a><span data-ttu-id="33167-120">参数</span><span class="sxs-lookup"><span data-stu-id="33167-120">Arguments</span></span>

`PROJECT` 
    
<span data-ttu-id="33167-121">要打包的项目。</span><span class="sxs-lookup"><span data-stu-id="33167-121">The project to pack.</span></span> <span data-ttu-id="33167-122">它可能是 [csproj 文件](csproj.md)或目录的路径。</span><span class="sxs-lookup"><span data-stu-id="33167-122">It's either a path to a [csproj file](csproj.md) or to a directory.</span></span> <span data-ttu-id="33167-123">如果省略，则默认为当前目录。</span><span class="sxs-lookup"><span data-stu-id="33167-123">If omitted, it defaults to the current directory.</span></span> 

## <a name="options"></a><span data-ttu-id="33167-124">选项</span><span class="sxs-lookup"><span data-stu-id="33167-124">Options</span></span>

`-h|--help`

<span data-ttu-id="33167-125">打印出有关命令的简短帮助。</span><span class="sxs-lookup"><span data-stu-id="33167-125">Prints out a short help for the command.</span></span>  

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="33167-126">将生成的包放置在指定目录。</span><span class="sxs-lookup"><span data-stu-id="33167-126">Places the built packages in the directory specified.</span></span> 

`--no-build`

<span data-ttu-id="33167-127">打包前不生成项目。</span><span class="sxs-lookup"><span data-stu-id="33167-127">Don't build the project before packing.</span></span> 

`--include-symbols`

<span data-ttu-id="33167-128">生成符号 `nupkg`。</span><span class="sxs-lookup"><span data-stu-id="33167-128">Generates the symbols `nupkg`.</span></span> 

`--include-source`

<span data-ttu-id="33167-129">将源文件包括在 NuGet 包中。</span><span class="sxs-lookup"><span data-stu-id="33167-129">Includes the source files in the NuGet package.</span></span> <span data-ttu-id="33167-130">源文件包括在 `nupkg` 内的 `src` 文件夹中。</span><span class="sxs-lookup"><span data-stu-id="33167-130">The sources files are included in the `src` folder within the `nupkg`.</span></span> 

`-c|--configuration <CONFIGURATION>`

<span data-ttu-id="33167-131">生成项目时要使用的配置。</span><span class="sxs-lookup"><span data-stu-id="33167-131">Configuration to use when building the project.</span></span> <span data-ttu-id="33167-132">如果未指定，则配置默认为 `Debug`。</span><span class="sxs-lookup"><span data-stu-id="33167-132">If not specified, configuration defaults to `Debug`.</span></span>

`--version-suffix <VERSION_SUFFIX>`

<span data-ttu-id="33167-133">定义项目中 `$(VersionSuffix)` MSBuild 属性的值。</span><span class="sxs-lookup"><span data-stu-id="33167-133">Defines the value for the `$(VersionSuffix)` MSBuild property in the project.</span></span>

`-s|--serviceable`

<span data-ttu-id="33167-134">设置包中可用的标志。</span><span class="sxs-lookup"><span data-stu-id="33167-134">Sets the serviceable flag in the package.</span></span> <span data-ttu-id="33167-135">有关详细信息，请参阅 [.NET 博客：.NET 4.5.1 支持 .NET NuGet 库的 Microsoft 安全更新](https://aka.ms/nupkgservicing)。</span><span class="sxs-lookup"><span data-stu-id="33167-135">For more information, see [.NET Blog: .NET 4.5.1 Supports Microsoft Security Updates for .NET NuGet Libraries](https://aka.ms/nupkgservicing).</span></span>

`--verbosity <LEVEL>`

<span data-ttu-id="33167-136">设置命令的详细级别。</span><span class="sxs-lookup"><span data-stu-id="33167-136">Sets the verbosity level of the command.</span></span> <span data-ttu-id="33167-137">允许使用的值为 `q[uiet]`、`m[inimal]`、`n[ormal]`、`d[etailed]` 和 `diag[nostic]`。</span><span class="sxs-lookup"><span data-stu-id="33167-137">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

## <a name="examples"></a><span data-ttu-id="33167-138">示例</span><span class="sxs-lookup"><span data-stu-id="33167-138">Examples</span></span>

<span data-ttu-id="33167-139">打包当前目录中的项目：</span><span class="sxs-lookup"><span data-stu-id="33167-139">Pack the project in the current directory:</span></span>

`dotnet pack`

<span data-ttu-id="33167-140">打包 `app1` 项目：</span><span class="sxs-lookup"><span data-stu-id="33167-140">Pack the `app1` project:</span></span>

`dotnet pack ~/projects/app1/project.csproj`
    
<span data-ttu-id="33167-141">打包当前目录中的项目并将生成的包放置到 `nupkgs` 文件夹：</span><span class="sxs-lookup"><span data-stu-id="33167-141">Pack the project in the current directory and place the resulting packages into the `nupkgs` folder:</span></span>

`dotnet pack --output nupkgs`

<span data-ttu-id="33167-142">将当前目录中的项目打包到 `nupkgs` 文件夹并跳过生成步骤：</span><span class="sxs-lookup"><span data-stu-id="33167-142">Pack the project in the current directory into the `nupkgs` folder and skip the build step:</span></span>

`dotnet pack --no-build --output nupkgs`

<span data-ttu-id="33167-143">将项目的版本后缀配置为 *.csproj* 文件中的 `<VersionSuffix>$(VersionSuffix)</VersionSuffix>`，使用给定的后缀打包当前项目，并更新生成的程序包版本：</span><span class="sxs-lookup"><span data-stu-id="33167-143">With the project's version suffix configured as `<VersionSuffix>$(VersionSuffix)</VersionSuffix>` in the *.csproj* file, pack the current project and update the resulting package version with the given suffix:</span></span>

`dotnet pack --version-suffix "ci-1234"`

<span data-ttu-id="33167-144">使用 `PackageVersion` MSBuild 属性将包版本设置为 `2.1.0`：</span><span class="sxs-lookup"><span data-stu-id="33167-144">Set the package version to `2.1.0` with the `PackageVersion` MSBuild property:</span></span>

`dotnet pack /p:PackageVersion=2.1.0`

