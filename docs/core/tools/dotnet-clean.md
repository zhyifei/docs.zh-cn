---
title: "dotnet-clean 命令 - .NET Core CLI"
description: "dotnet-clean 命令可清除当前目录。"
keywords: "dotnet-clean, CLI, CLI 命令, .NET Core"
author: blackdwarf
ms.author: mairaw
ms.date: 03/15/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: eff65fa1-bab4-4421-8260-d0a284b690b2
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 10222781d5bff596d1b7883bc73097758e878235
ms.contentlocale: zh-cn
ms.lasthandoff: 07/28/2017

---

# <a name="dotnet-clean"></a><span data-ttu-id="3ddab-104">dotnet-clean</span><span class="sxs-lookup"><span data-stu-id="3ddab-104">dotnet-clean</span></span>

## <a name="name"></a><span data-ttu-id="3ddab-105">名称</span><span class="sxs-lookup"><span data-stu-id="3ddab-105">Name</span></span>

<span data-ttu-id="3ddab-106">`dotnet-clean` - 清除项目输出。</span><span class="sxs-lookup"><span data-stu-id="3ddab-106">`dotnet-clean` - Cleans the output of a project.</span></span> 

## <a name="synopsis"></a><span data-ttu-id="3ddab-107">摘要</span><span class="sxs-lookup"><span data-stu-id="3ddab-107">Synopsis</span></span>

`dotnet clean [<PROJECT>] [-o|--output] [-f|--framework] [-c|--configuration] [-v|--verbosity] [-h|--help]`

## <a name="description"></a><span data-ttu-id="3ddab-108">描述</span><span class="sxs-lookup"><span data-stu-id="3ddab-108">Description</span></span>

<span data-ttu-id="3ddab-109">`dotnet clean` 命令可清除上一个生成的输出。</span><span class="sxs-lookup"><span data-stu-id="3ddab-109">The `dotnet clean` command cleans the output of the previous build.</span></span> <span data-ttu-id="3ddab-110">它以 [MSBuild 目标](/visualstudio/msbuild/msbuild-targets) 的形式实现，以便在运行命令时对项目进行评估。</span><span class="sxs-lookup"><span data-stu-id="3ddab-110">It's implemented as an [MSBuild target](/visualstudio/msbuild/msbuild-targets), so the project is evaluated when the command is run.</span></span> <span data-ttu-id="3ddab-111">只会清除在生成过程中创建的输出。</span><span class="sxs-lookup"><span data-stu-id="3ddab-111">Only the outputs created during the build are cleaned.</span></span> <span data-ttu-id="3ddab-112">中间 (*obj*) 和最终输出 (*bin*) 文件夹都会被清除。</span><span class="sxs-lookup"><span data-stu-id="3ddab-112">Both intermediate (*obj*) and final output (*bin*) folders are cleaned.</span></span>

## <a name="arguments"></a><span data-ttu-id="3ddab-113">参数</span><span class="sxs-lookup"><span data-stu-id="3ddab-113">Arguments</span></span>

`PROJECT`

<span data-ttu-id="3ddab-114">要清除的 MSBuild 项目。</span><span class="sxs-lookup"><span data-stu-id="3ddab-114">The MSBuild project to clean.</span></span> <span data-ttu-id="3ddab-115">如果未指定项目文件，MSBuild 会在当前工作目录中搜索以 *proj* 结尾的文件扩展名并使用该文件。</span><span class="sxs-lookup"><span data-stu-id="3ddab-115">If a project file is not specified, MSBuild searches the current working directory for a file that has a file extension that ends in *proj* and uses that file.</span></span>

## <a name="options"></a><span data-ttu-id="3ddab-116">选项</span><span class="sxs-lookup"><span data-stu-id="3ddab-116">Options</span></span>

`-h|--help`

<span data-ttu-id="3ddab-117">打印出有关命令的简短帮助。</span><span class="sxs-lookup"><span data-stu-id="3ddab-117">Prints out a short help for the command.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="3ddab-118">包含已生成的输出的目录。</span><span class="sxs-lookup"><span data-stu-id="3ddab-118">Directory in which the build outputs are placed.</span></span> <span data-ttu-id="3ddab-119">如果在生成项目时指定了框架，则使用输出目录开关指定 `-f|--framework <FRAMEWORK>` 开关。</span><span class="sxs-lookup"><span data-stu-id="3ddab-119">Specify the `-f|--framework <FRAMEWORK>` switch with the output directory switch if you specified the framework when the project was built.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="3ddab-120">在生成时指定的[框架](../../standard/frameworks.md)。</span><span class="sxs-lookup"><span data-stu-id="3ddab-120">The [framework](../../standard/frameworks.md) that was specified at build time.</span></span> <span data-ttu-id="3ddab-121">必须在[项目文件](csproj.md)中定义该框架。</span><span class="sxs-lookup"><span data-stu-id="3ddab-121">The framework must be defined in the [project file](csproj.md).</span></span> <span data-ttu-id="3ddab-122">如果在生成时指定了框架，则必须在清除时指定框架。</span><span class="sxs-lookup"><span data-stu-id="3ddab-122">If you specified the framework at build time, you must specify the framework when cleaning.</span></span>

`-c|--configuration <CONFIGURATION>`

<span data-ttu-id="3ddab-123">定义配置。</span><span class="sxs-lookup"><span data-stu-id="3ddab-123">Defines the configuration.</span></span> <span data-ttu-id="3ddab-124">如果省略，则默认为 `Debug`。</span><span class="sxs-lookup"><span data-stu-id="3ddab-124">If omitted, it defaults to `Debug`.</span></span> <span data-ttu-id="3ddab-125">如果在生成时指定了属性，则仅在清除时需要该属性。</span><span class="sxs-lookup"><span data-stu-id="3ddab-125">This property is only required when cleaning if you specified it during build time.</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="3ddab-126">设置命令的详细级别。</span><span class="sxs-lookup"><span data-stu-id="3ddab-126">Sets the verbosity level of the command.</span></span> <span data-ttu-id="3ddab-127">允许的级别为 q[uiet]、m[inimal]、n[ormal]、d[etailed] 和 diag[nostic]。</span><span class="sxs-lookup"><span data-stu-id="3ddab-127">Allowed levels are q[uiet], m[inimal], n[ormal], d[etailed], and diag[nostic].</span></span>

## <a name="examples"></a><span data-ttu-id="3ddab-128">示例</span><span class="sxs-lookup"><span data-stu-id="3ddab-128">Examples</span></span>

<span data-ttu-id="3ddab-129">清除项目的默认生成：</span><span class="sxs-lookup"><span data-stu-id="3ddab-129">Clean a default build of the project:</span></span>

`dotnet clean`

<span data-ttu-id="3ddab-130">清除使用版本配置生成的项目：</span><span class="sxs-lookup"><span data-stu-id="3ddab-130">Clean a project built using the Release configuration:</span></span>

`dotnet clean --configuration Release`

