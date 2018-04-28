---
title: dotnet clean 命令 - .NET Core CLI
description: dotnet clean 命令可清除当前目录。
author: mairaw
ms.author: mairaw
ms.date: 08/13/2017
ms.topic: conceptual
ms.prod: dotnet-core
ms.technology: dotnet-cli
ms.workload:
- dotnetcore
ms.openlocfilehash: 92db35df770b1e1d2438127c4b529d4cb480c8df
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2018
---
# <a name="dotnet-clean"></a><span data-ttu-id="ca334-103">dotnet-clean</span><span class="sxs-lookup"><span data-stu-id="ca334-103">dotnet-clean</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="ca334-104">name</span><span class="sxs-lookup"><span data-stu-id="ca334-104">Name</span></span>

<span data-ttu-id="ca334-105">`dotnet clean` - 清除项目输出。</span><span class="sxs-lookup"><span data-stu-id="ca334-105">`dotnet clean` - Cleans the output of a project.</span></span>

## <a name="synopsis"></a><span data-ttu-id="ca334-106">摘要</span><span class="sxs-lookup"><span data-stu-id="ca334-106">Synopsis</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="ca334-107">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="ca334-107">.NET Core 2.x</span></span>](#tab/netcore2x)
```
dotnet clean [<PROJECT>] [-c|--configuration] [-f|--framework] [-o|--output] [-r|--runtime] [-v|--verbosity]
dotnet clean [-h|--help]
```
# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="ca334-108">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="ca334-108">.NET Core 1.x</span></span>](#tab/netcore1x)
```
dotnet clean [<PROJECT>] [-c|--configuration] [-f|--framework] [-o|--output] [-v|--verbosity]
dotnet clean [-h|--help]
```
---

## <a name="description"></a><span data-ttu-id="ca334-109">描述</span><span class="sxs-lookup"><span data-stu-id="ca334-109">Description</span></span>

<span data-ttu-id="ca334-110">`dotnet clean` 命令可清除上一个生成的输出。</span><span class="sxs-lookup"><span data-stu-id="ca334-110">The `dotnet clean` command cleans the output of the previous build.</span></span> <span data-ttu-id="ca334-111">它以 [MSBuild 目标](/visualstudio/msbuild/msbuild-targets) 的形式实现，以便在运行命令时对项目进行评估。</span><span class="sxs-lookup"><span data-stu-id="ca334-111">It's implemented as an [MSBuild target](/visualstudio/msbuild/msbuild-targets), so the project is evaluated when the command is run.</span></span> <span data-ttu-id="ca334-112">只会清除在生成过程中创建的输出。</span><span class="sxs-lookup"><span data-stu-id="ca334-112">Only the outputs created during the build are cleaned.</span></span> <span data-ttu-id="ca334-113">中间 (*obj*) 和最终输出 (*bin*) 文件夹都会被清除。</span><span class="sxs-lookup"><span data-stu-id="ca334-113">Both intermediate (*obj*) and final output (*bin*) folders are cleaned.</span></span>

## <a name="arguments"></a><span data-ttu-id="ca334-114">自变量</span><span class="sxs-lookup"><span data-stu-id="ca334-114">Arguments</span></span>

`PROJECT`

<span data-ttu-id="ca334-115">要清除的 MSBuild 项目。</span><span class="sxs-lookup"><span data-stu-id="ca334-115">The MSBuild project to clean.</span></span> <span data-ttu-id="ca334-116">如果未指定项目文件，MSBuild 会在当前工作目录中搜索以 *proj* 结尾的文件扩展名并使用该文件。</span><span class="sxs-lookup"><span data-stu-id="ca334-116">If a project file is not specified, MSBuild searches the current working directory for a file that has a file extension that ends in *proj* and uses that file.</span></span>

## <a name="options"></a><span data-ttu-id="ca334-117">选项</span><span class="sxs-lookup"><span data-stu-id="ca334-117">Options</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="ca334-118">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="ca334-118">.NET Core 2.x</span></span>](#tab/netcore2x)

`-c|--configuration {Debug|Release}`

<span data-ttu-id="ca334-119">定义生成配置。</span><span class="sxs-lookup"><span data-stu-id="ca334-119">Defines the build configuration.</span></span> <span data-ttu-id="ca334-120">默认值为 `Debug`。</span><span class="sxs-lookup"><span data-stu-id="ca334-120">The default value is `Debug`.</span></span> <span data-ttu-id="ca334-121">只有在生成期间指定了此选项，才必须在清除时使用此选项。</span><span class="sxs-lookup"><span data-stu-id="ca334-121">This option is only required when cleaning if you specified it during build time.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="ca334-122">在生成时指定的[框架](../../standard/frameworks.md)。</span><span class="sxs-lookup"><span data-stu-id="ca334-122">The [framework](../../standard/frameworks.md) that was specified at build time.</span></span> <span data-ttu-id="ca334-123">必须在[项目文件](csproj.md)中定义该框架。</span><span class="sxs-lookup"><span data-stu-id="ca334-123">The framework must be defined in the [project file](csproj.md).</span></span> <span data-ttu-id="ca334-124">如果在生成时指定了框架，则必须在清除时指定框架。</span><span class="sxs-lookup"><span data-stu-id="ca334-124">If you specified the framework at build time, you must specify the framework when cleaning.</span></span>

`-h|--help`

<span data-ttu-id="ca334-125">打印出有关命令的简短帮助。</span><span class="sxs-lookup"><span data-stu-id="ca334-125">Prints out a short help for the command.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="ca334-126">包含已生成的输出的目录。</span><span class="sxs-lookup"><span data-stu-id="ca334-126">Directory in which the build outputs are placed.</span></span> <span data-ttu-id="ca334-127">如果在生成项目时指定了框架，则使用输出目录开关指定 `-f|--framework <FRAMEWORK>` 开关。</span><span class="sxs-lookup"><span data-stu-id="ca334-127">Specify the `-f|--framework <FRAMEWORK>` switch with the output directory switch if you specified the framework when the project was built.</span></span>

`-r|--runtime <RUNTIME_IDENTIFIER>`

<span data-ttu-id="ca334-128">清除指定运行时的输出文件夹。</span><span class="sxs-lookup"><span data-stu-id="ca334-128">Cleans the output folder of the specified runtime.</span></span> <span data-ttu-id="ca334-129">在创建[独立部署 (SCD)](../deploying/index.md#self-contained-deployments-scd) 时使用此选项。</span><span class="sxs-lookup"><span data-stu-id="ca334-129">This is used when a [self-contained deployment](../deploying/index.md#self-contained-deployments-scd) was created.</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="ca334-130">设置命令的详细级别。</span><span class="sxs-lookup"><span data-stu-id="ca334-130">Sets the verbosity level of the command.</span></span> <span data-ttu-id="ca334-131">允许的级别为 q[uiet]、m[inimal]、n[ormal]、d[etailed] 和 diag[nostic]。</span><span class="sxs-lookup"><span data-stu-id="ca334-131">Allowed levels are q[uiet], m[inimal], n[ormal], d[etailed], and diag[nostic].</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="ca334-132">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="ca334-132">.NET Core 1.x</span></span>](#tab/netcore1x)

`-c|--configuration {Debug|Release}`

<span data-ttu-id="ca334-133">定义生成配置。</span><span class="sxs-lookup"><span data-stu-id="ca334-133">Defines the build configuration.</span></span> <span data-ttu-id="ca334-134">默认值为 `Debug`。</span><span class="sxs-lookup"><span data-stu-id="ca334-134">The default value is `Debug`.</span></span> <span data-ttu-id="ca334-135">只有在生成期间指定了此选项，才必须在清除时使用此选项。</span><span class="sxs-lookup"><span data-stu-id="ca334-135">This option is only required when cleaning if you specified it during build time.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="ca334-136">在生成时指定的[框架](../../standard/frameworks.md)。</span><span class="sxs-lookup"><span data-stu-id="ca334-136">The [framework](../../standard/frameworks.md) that was specified at build time.</span></span> <span data-ttu-id="ca334-137">必须在[项目文件](csproj.md)中定义该框架。</span><span class="sxs-lookup"><span data-stu-id="ca334-137">The framework must be defined in the [project file](csproj.md).</span></span> <span data-ttu-id="ca334-138">如果在生成时指定了框架，则必须在清除时指定框架。</span><span class="sxs-lookup"><span data-stu-id="ca334-138">If you specified the framework at build time, you must specify the framework when cleaning.</span></span>

`-h|--help`

<span data-ttu-id="ca334-139">打印出有关命令的简短帮助。</span><span class="sxs-lookup"><span data-stu-id="ca334-139">Prints out a short help for the command.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="ca334-140">包含已生成的输出的目录。</span><span class="sxs-lookup"><span data-stu-id="ca334-140">Directory in which the build outputs are placed.</span></span> <span data-ttu-id="ca334-141">如果在生成项目时指定了框架，则使用输出目录开关指定 `-f|--framework <FRAMEWORK>` 开关。</span><span class="sxs-lookup"><span data-stu-id="ca334-141">Specify the `-f|--framework <FRAMEWORK>` switch with the output directory switch if you specified the framework when the project was built.</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="ca334-142">设置命令的详细级别。</span><span class="sxs-lookup"><span data-stu-id="ca334-142">Sets the verbosity level of the command.</span></span> <span data-ttu-id="ca334-143">允许的级别为 q[uiet]、m[inimal]、n[ormal]、d[etailed] 和 diag[nostic]。</span><span class="sxs-lookup"><span data-stu-id="ca334-143">Allowed levels are q[uiet], m[inimal], n[ormal], d[etailed], and diag[nostic].</span></span>

---

## <a name="examples"></a><span data-ttu-id="ca334-144">示例</span><span class="sxs-lookup"><span data-stu-id="ca334-144">Examples</span></span>

<span data-ttu-id="ca334-145">清除项目的默认生成：</span><span class="sxs-lookup"><span data-stu-id="ca334-145">Clean a default build of the project:</span></span>

`dotnet clean`

<span data-ttu-id="ca334-146">清除使用版本配置生成的项目：</span><span class="sxs-lookup"><span data-stu-id="ca334-146">Clean a project built using the Release configuration:</span></span>

`dotnet clean --configuration Release`
