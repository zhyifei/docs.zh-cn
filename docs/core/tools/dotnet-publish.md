---
title: "dotnet-publish 命令 - .NET Core CLI"
description: "dotnet-publish 命令可将 .NET Core 项目发布到目录。"
keywords: "dotnet-publish, CLI, CLI 命令, .NET Core"
author: blackdwarf
ms.author: mairaw
ms.date: 03/15/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: f2ef275a-7c5e-430a-8c30-65f52af62771
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: a8a37b1eacab13682d4f4a2bea2f9ea248cdd9eb
ms.contentlocale: zh-cn
ms.lasthandoff: 07/28/2017

---

# <a name="dotnet-publish"></a><span data-ttu-id="4ce63-104">dotnet-publish</span><span class="sxs-lookup"><span data-stu-id="4ce63-104">dotnet-publish</span></span>

## <a name="name"></a><span data-ttu-id="4ce63-105">名称</span><span class="sxs-lookup"><span data-stu-id="4ce63-105">Name</span></span>

<span data-ttu-id="4ce63-106">`dotnet-publish` - 将应用程序及其依赖项打包到文件夹以部署到托管系统。</span><span class="sxs-lookup"><span data-stu-id="4ce63-106">`dotnet-publish` - Packs the application and its dependencies into a folder for deployment to a hosting system.</span></span>

## <a name="synopsis"></a><span data-ttu-id="4ce63-107">摘要</span><span class="sxs-lookup"><span data-stu-id="4ce63-107">Synopsis</span></span>

`dotnet publish [<PROJECT>] [-f|--framework] [-r|--runtime] [-o|--output] [-c|--configuration] [--version-suffix] [-v|--verbosity] [-h|--help]`

## <a name="description"></a><span data-ttu-id="4ce63-108">说明</span><span class="sxs-lookup"><span data-stu-id="4ce63-108">Description</span></span>

<span data-ttu-id="4ce63-109">`dotnet publish` 编译应用程序、读取 project 文件中指定的所有依赖项并将生成的文件集发布到目录。</span><span class="sxs-lookup"><span data-stu-id="4ce63-109">`dotnet publish` compiles the application, reads through its dependencies specified in the project file, and publishes the resulting set of files to a directory.</span></span> <span data-ttu-id="4ce63-110">输出将包含以下信息：</span><span class="sxs-lookup"><span data-stu-id="4ce63-110">The output will contain the following:</span></span>

* <span data-ttu-id="4ce63-111">扩展名为 `*.dll` 的程序集中的中间语言 (IL) 代码。</span><span class="sxs-lookup"><span data-stu-id="4ce63-111">Intermediate Language (IL) code in an assembly with a `*.dll` extension.</span></span>
* <span data-ttu-id="4ce63-112">*\*.deps.json* 文件，包含项目的所有依赖项。</span><span class="sxs-lookup"><span data-stu-id="4ce63-112">*\*.deps.json* file that contains all of the dependencies of the project.</span></span>
* <span data-ttu-id="4ce63-113">*\*.runtime.config.json* 文件，指定应用程序所要求的共享运行时以及该运行时的其他配置选项（例如，垃圾回收类型）。</span><span class="sxs-lookup"><span data-stu-id="4ce63-113">*\*.runtime.config.json* file that specifies the shared runtime that the application expects, as well as other configuration options for the runtime (for example, garbage collection type).</span></span>
* <span data-ttu-id="4ce63-114">应用程序的依赖项。</span><span class="sxs-lookup"><span data-stu-id="4ce63-114">The application's dependencies.</span></span> <span data-ttu-id="4ce63-115">将这些依赖项从 NuGet 缓存复制到输出文件夹。</span><span class="sxs-lookup"><span data-stu-id="4ce63-115">These are copied from the NuGet cache into the output folder.</span></span>

<span data-ttu-id="4ce63-116">`dotnet publish` 命令的输出已准备好部署到托管系统（例如，服务器、电脑、Mac 和笔记本电脑）以供执行，它还是准备应用程序以供部署的唯一受官方支持的方法。</span><span class="sxs-lookup"><span data-stu-id="4ce63-116">The `dotnet publish` command's output is ready for deployment to a hosting system (for example, a server, PC, Mac, laptop) for execution and is the only officially supported way to prepare the application for deployment.</span></span> <span data-ttu-id="4ce63-117">根据项目指定的部署的类型，托管系统不一定已在其上安装 .NET Core 共享运行时。</span><span class="sxs-lookup"><span data-stu-id="4ce63-117">Depending on the type of deployment that the project specifies, the hosting system may or may not have the .NET Core shared runtime installed on it.</span></span> <span data-ttu-id="4ce63-118">有关详细信息，请参阅 [.NET Core 应用程序部署](../deploying/index.md)。</span><span class="sxs-lookup"><span data-stu-id="4ce63-118">For more information, see [.NET Core Application Deployment](../deploying/index.md).</span></span> <span data-ttu-id="4ce63-119">有关已发布应用程序的目录结构，请参阅[目录结构](/aspnet/core/hosting/directory-structure)。</span><span class="sxs-lookup"><span data-stu-id="4ce63-119">For the directory structure of a published application, see [Directory structure](/aspnet/core/hosting/directory-structure).</span></span>

## <a name="arguments"></a><span data-ttu-id="4ce63-120">参数</span><span class="sxs-lookup"><span data-stu-id="4ce63-120">Arguments</span></span>

`PROJECT` 

<span data-ttu-id="4ce63-121">要发布的项目，如果未指定，则默认为当前目录。</span><span class="sxs-lookup"><span data-stu-id="4ce63-121">The project to publish, which defaults to the current directory if not specified.</span></span> 

## <a name="options"></a><span data-ttu-id="4ce63-122">选项</span><span class="sxs-lookup"><span data-stu-id="4ce63-122">Options</span></span>

`-h|--help`

<span data-ttu-id="4ce63-123">打印出有关命令的简短帮助。</span><span class="sxs-lookup"><span data-stu-id="4ce63-123">Prints out a short help for the command.</span></span>  

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="4ce63-124">为指定的[目标框架](../../standard/frameworks.md)发布应用程序。</span><span class="sxs-lookup"><span data-stu-id="4ce63-124">Publishes the application for the specified [target framework](../../standard/frameworks.md).</span></span> <span data-ttu-id="4ce63-125">必须在项目文件中指定目标框架。</span><span class="sxs-lookup"><span data-stu-id="4ce63-125">You must specify the target framework in the project file.</span></span>

`-r|--runtime <RUNTIME_IDENTIFIER>`

<span data-ttu-id="4ce63-126">发布针对给定运行时的应用程序。</span><span class="sxs-lookup"><span data-stu-id="4ce63-126">Publishes the application for a given runtime.</span></span> <span data-ttu-id="4ce63-127">这将在创建[独立部署 (SCD)](../deploying/index.md#self-contained-deployments-scd) 时使用。</span><span class="sxs-lookup"><span data-stu-id="4ce63-127">This is used when creating a [self-contained deployment (SCD)](../deploying/index.md#self-contained-deployments-scd).</span></span> <span data-ttu-id="4ce63-128">有关运行时标识符 (RID) 的列表，请参阅 [RID 目录](../rid-catalog.md)。</span><span class="sxs-lookup"><span data-stu-id="4ce63-128">For a list of Runtime Identifiers (RIDs), see the [RID catalog](../rid-catalog.md).</span></span> <span data-ttu-id="4ce63-129">默认为发布[依赖于框架的部署 (FDD)](../deploying/index.md#framework-dependent-deployments-fdd)。</span><span class="sxs-lookup"><span data-stu-id="4ce63-129">Default is to publish a [framework-dependent deployment (FDD)](../deploying/index.md#framework-dependent-deployments-fdd).</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="4ce63-130">指定输出目录的路径。</span><span class="sxs-lookup"><span data-stu-id="4ce63-130">Specifies the path for the output directory.</span></span> <span data-ttu-id="4ce63-131">如未指定，对于依赖于框架的部署，将默认为 *./bin/[configuration]/[framework]/* 或对于独立部署，将默认为 *./bin/[configuration]/[framework]/[runtime]*。</span><span class="sxs-lookup"><span data-stu-id="4ce63-131">If not specified, it defaults to *./bin/[configuration]/[framework]/* for a framework-dependent deployment or *./bin/[configuration]/[framework]/[runtime]* for a self-contained deployment.</span></span>

`-c|--configuration <CONFIGURATION>`

<span data-ttu-id="4ce63-132">生成项目时要使用的配置。</span><span class="sxs-lookup"><span data-stu-id="4ce63-132">Configuration to use when building the project.</span></span> <span data-ttu-id="4ce63-133">默认值为 `Debug`。</span><span class="sxs-lookup"><span data-stu-id="4ce63-133">The default value is `Debug`.</span></span>

`--version-suffix <VERSION_SUFFIX>`

<span data-ttu-id="4ce63-134">定义版本后缀来替换项目文件的版本字段中的星号 (`*`)。</span><span class="sxs-lookup"><span data-stu-id="4ce63-134">Defines the version suffix to replace the asterisk (`*`) in the version field of the project file.</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="4ce63-135">设置命令的详细级别。</span><span class="sxs-lookup"><span data-stu-id="4ce63-135">Sets the verbosity level of the command.</span></span> <span data-ttu-id="4ce63-136">允许使用的值为 `q[uiet]`、`m[inimal]`、`n[ormal]`、`d[etailed]` 和 `diag[nostic]`。</span><span class="sxs-lookup"><span data-stu-id="4ce63-136">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

## <a name="examples"></a><span data-ttu-id="4ce63-137">示例</span><span class="sxs-lookup"><span data-stu-id="4ce63-137">Examples</span></span>

<span data-ttu-id="4ce63-138">在当前目录中发布项目：</span><span class="sxs-lookup"><span data-stu-id="4ce63-138">Publish the project in the current directory:</span></span>

`dotnet publish`

<span data-ttu-id="4ce63-139">使用指定的项目文件发布应用程序：</span><span class="sxs-lookup"><span data-stu-id="4ce63-139">Publish the application using the specified project file:</span></span>

`dotnet publish ~/projects/app1/app1.csproj`
    
<span data-ttu-id="4ce63-140">使用 `netcoreapp1.1` 框架发布当前目录中的项目：</span><span class="sxs-lookup"><span data-stu-id="4ce63-140">Publish the project in the current directory using the `netcoreapp1.1` framework:</span></span>

`dotnet publish --framework netcoreapp1.1`
    
<span data-ttu-id="4ce63-141">使用 `netcoreapp1.1` 框架和 `OS X 10.10` 的运行时发布当前应用程序（必须在项目文件中列出此 RID）。</span><span class="sxs-lookup"><span data-stu-id="4ce63-141">Publish the current application using the `netcoreapp1.1` framework and the runtime for `OS X 10.10` (you must list this RID in the project file).</span></span>

`dotnet publish --framework netcoreapp1.1 --runtime osx.10.11-x64`

## <a name="see-also"></a><span data-ttu-id="4ce63-142">请参阅</span><span class="sxs-lookup"><span data-stu-id="4ce63-142">See also</span></span>

* [<span data-ttu-id="4ce63-143">目标框架</span><span class="sxs-lookup"><span data-stu-id="4ce63-143">Target frameworks</span></span>](../../standard/frameworks.md)
* [<span data-ttu-id="4ce63-144">运行时标识符 (RID) 目录</span><span class="sxs-lookup"><span data-stu-id="4ce63-144">Runtime IDentifier (RID) catalog</span></span>](../rid-catalog.md)

