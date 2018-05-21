---
title: dotnet migrate 命令 - .NET Core CLI
description: dotnet migrate 命令可迁移项目及其所有依赖项。
author: mairaw
ms.author: mairaw
ms.date: 08/14/2017
ms.openlocfilehash: bdc1da5c1b70fdceac0170b2f002059a66ca5880
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="dotnet-migrate"></a><span data-ttu-id="c4718-103">dotnet migrate</span><span class="sxs-lookup"><span data-stu-id="c4718-103">dotnet migrate</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="c4718-104">name</span><span class="sxs-lookup"><span data-stu-id="c4718-104">Name</span></span>

<span data-ttu-id="c4718-105">`dotnet migrate` - 将预览版 2 .NET Core 项目迁移到 .NET Core SDK 1.0 项目。</span><span class="sxs-lookup"><span data-stu-id="c4718-105">`dotnet migrate` - Migrates a Preview 2 .NET Core project to a .NET Core SDK 1.0 project.</span></span>

## <a name="synopsis"></a><span data-ttu-id="c4718-106">摘要</span><span class="sxs-lookup"><span data-stu-id="c4718-106">Synopsis</span></span>

`dotnet migrate [<SOLUTION_FILE|PROJECT_DIR>] [-t|--template-file] [-v|--sdk-package-version] [-x|--xproj-file] [-s|--skip-project-references] [-r|--report-file] [--format-report-file-json] [--skip-backup] [-h|--help]`

## <a name="description"></a><span data-ttu-id="c4718-107">描述</span><span class="sxs-lookup"><span data-stu-id="c4718-107">Description</span></span>

<span data-ttu-id="c4718-108">`dotnet migrate` 命令将有效的基于预览版 2 *project.json* 的项目迁移到有效的 .NET Core SDK 1.0 *csproj* 项目。</span><span class="sxs-lookup"><span data-stu-id="c4718-108">The `dotnet migrate` command migrates a valid Preview 2 *project.json*-based project to a valid .NET Core SDK 1.0 *csproj* project.</span></span> 

<span data-ttu-id="c4718-109">默认情况下，命令迁移根项目和根项目包含的任何项目引用。</span><span class="sxs-lookup"><span data-stu-id="c4718-109">By default, the command migrates the root project and any project references that the root project contains.</span></span> <span data-ttu-id="c4718-110">在运行时使用 `--skip-project-references` 选项禁用此行为。</span><span class="sxs-lookup"><span data-stu-id="c4718-110">This behavior is disabled using the `--skip-project-references` option at runtime.</span></span> 

<span data-ttu-id="c4718-111">在以下情况下执行迁移：</span><span class="sxs-lookup"><span data-stu-id="c4718-111">Migration is performed on the following:</span></span>

* <span data-ttu-id="c4718-112">通过指定 *project.json* 文件进行迁移的单个项目。</span><span class="sxs-lookup"><span data-stu-id="c4718-112">A single project by specifying the *project.json* file to migrate.</span></span>
* <span data-ttu-id="c4718-113">通过将路径传递到 *global.json* 文件在 *global.json* 文件中指定的所有目录。</span><span class="sxs-lookup"><span data-stu-id="c4718-113">All of the directories specified in the *global.json* file by passing in a path to the *global.json* file.</span></span>
* <span data-ttu-id="c4718-114">一个 *solution.sln* 文件，它迁移在解决方案中引用的项目。</span><span class="sxs-lookup"><span data-stu-id="c4718-114">A *solution.sln* file, where it migrates the projects referenced in the solution.</span></span>
* <span data-ttu-id="c4718-115">以递归方式迁移给定目录的所有子目录。</span><span class="sxs-lookup"><span data-stu-id="c4718-115">On all sub-directories of the given directory recursively.</span></span>

<span data-ttu-id="c4718-116">`dotnet migrate` 命令将迁移的 *project.json* 文件保存在 `backup` 目录中，如果该目录不存在，将创建一个。</span><span class="sxs-lookup"><span data-stu-id="c4718-116">The `dotnet migrate` command keeps the migrated *project.json* file inside a `backup` directory, which it creates if the directory doesn't exist.</span></span> <span data-ttu-id="c4718-117">使用 `--skip-backup` 选项重写此行为。</span><span class="sxs-lookup"><span data-stu-id="c4718-117">This behavior is overridden using the `--skip-backup` option.</span></span>

<span data-ttu-id="c4718-118">默认情况下，迁移操作会将迁移过程的状态输出到标准输出 (STDOUT)。</span><span class="sxs-lookup"><span data-stu-id="c4718-118">By default, the migration operation outputs the state of the migration process to standard output (STDOUT).</span></span> <span data-ttu-id="c4718-119">如果使用 `--report-file <REPORT_FILE>` 选项，输出将保存到指定的文件中。</span><span class="sxs-lookup"><span data-stu-id="c4718-119">If you use the `--report-file <REPORT_FILE>` option, the output is saved to the file specify.</span></span> 

<span data-ttu-id="c4718-120">`dotnet migrate` 命令仅支持有效的预览版 2 基于 *project.json* 的项目。</span><span class="sxs-lookup"><span data-stu-id="c4718-120">The `dotnet migrate` command only supports valid Preview 2 *project.json*-based projects.</span></span> <span data-ttu-id="c4718-121">这意味着，不能使用它将 DNX 或预览版 1 基于 *project.json* 的项目直接迁移到 MSBuild/csproj 项目。</span><span class="sxs-lookup"><span data-stu-id="c4718-121">This means that you cannot use it to migrate DNX or Preview 1 *project.json*-based projects directly to MSBuild/csproj projects.</span></span> <span data-ttu-id="c4718-122">首先需要将项目手动迁移到预览版 2 基于 *project.json* 的项目，然后使用 `dotnet migrate` 命令迁移该项目。</span><span class="sxs-lookup"><span data-stu-id="c4718-122">You first need to manually migrate the project to a Preview 2 *project.json*-based project and then use the `dotnet migrate` command to migrate the project.</span></span>

## <a name="arguments"></a><span data-ttu-id="c4718-123">自变量</span><span class="sxs-lookup"><span data-stu-id="c4718-123">Arguments</span></span>

`PROJECT_JSON/GLOBAL_JSON/SOLUTION_FILE/PROJECT_DIR`

<span data-ttu-id="c4718-124">下列路径之一：</span><span class="sxs-lookup"><span data-stu-id="c4718-124">The path to one of the following:</span></span>

* <span data-ttu-id="c4718-125">要迁移的 *project.json* 文件。</span><span class="sxs-lookup"><span data-stu-id="c4718-125">a *project.json* file to migrate.</span></span>
* <span data-ttu-id="c4718-126">*global.json*文件，用于迁移 *global.json* 中指定的文件夹。</span><span class="sxs-lookup"><span data-stu-id="c4718-126">a *global.json* file, it will migrate the folders specified in *global.json*.</span></span>
* <span data-ttu-id="c4718-127">*solution.sln* 文件，它将迁移解决方案中引用的项目。</span><span class="sxs-lookup"><span data-stu-id="c4718-127">a *solution.sln* file, it will migrate the projects referenced in the solution.</span></span>
* <span data-ttu-id="c4718-128">要迁移的目录，它将以递归方式搜索要迁移的 *project.json* 文件。</span><span class="sxs-lookup"><span data-stu-id="c4718-128">a directory to migrate, it will recursively search for *project.json* files to migrate.</span></span>

<span data-ttu-id="c4718-129">如未指定，则默认为当前目录。</span><span class="sxs-lookup"><span data-stu-id="c4718-129">Defaults to current directory if nothing is specified.</span></span>

## <a name="options"></a><span data-ttu-id="c4718-130">选项</span><span class="sxs-lookup"><span data-stu-id="c4718-130">Options</span></span>

`-h|--help`

<span data-ttu-id="c4718-131">打印出有关命令的简短帮助。</span><span class="sxs-lookup"><span data-stu-id="c4718-131">Prints out a short help for the command.</span></span>

`-t|--template-file <TEMPLATE_FILE>`

<span data-ttu-id="c4718-132">用于迁移的模板 csproj 文件。</span><span class="sxs-lookup"><span data-stu-id="c4718-132">Template csproj file to use for migration.</span></span> <span data-ttu-id="c4718-133">默认情况下，使用与被 `dotnet new console` 删除的模板相同的模板。</span><span class="sxs-lookup"><span data-stu-id="c4718-133">By default, the same template as the one dropped by `dotnet new console` is used.</span></span>

`-v|--sdk-package-version <VERSION>`

<span data-ttu-id="c4718-134">在已迁移应用中将被引用的 sdk 包的版本。</span><span class="sxs-lookup"><span data-stu-id="c4718-134">The version of the sdk package that's referenced in the migrated app.</span></span> <span data-ttu-id="c4718-135">默认为 `dotnet new` 中 SDK 的版本。</span><span class="sxs-lookup"><span data-stu-id="c4718-135">The default is the version of the SDK in `dotnet new`.</span></span>

`-x|--xproj-file <FILE>`

<span data-ttu-id="c4718-136">要使用的 xproj 文件的路径。</span><span class="sxs-lookup"><span data-stu-id="c4718-136">The path to the xproj file to use.</span></span> <span data-ttu-id="c4718-137">当项目目录中有多个 xproj 时需要。</span><span class="sxs-lookup"><span data-stu-id="c4718-137">Required when there is more than one xproj in a project directory.</span></span>

`-s|--skip-project-references [Debug|Release]`

<span data-ttu-id="c4718-138">跳过迁移项目引用。</span><span class="sxs-lookup"><span data-stu-id="c4718-138">Skip migrating project references.</span></span> <span data-ttu-id="c4718-139">默认情况下，以递归方式迁移项目引用。</span><span class="sxs-lookup"><span data-stu-id="c4718-139">By default, project references are migrated recursively.</span></span>

`-r|--report-file <REPORT_FILE>`

<span data-ttu-id="c4718-140">除控制台外，还将迁移报告输出到文件。</span><span class="sxs-lookup"><span data-stu-id="c4718-140">Output migration report to a file in addition to the console.</span></span>

`--format-report-file-json <REPORT_FILE>`

<span data-ttu-id="c4718-141">将迁移报告文件（而非用户消息）作为 JSON 输出。</span><span class="sxs-lookup"><span data-stu-id="c4718-141">Output migration report file as JSON rather than user messages.</span></span>

`--skip-backup`

<span data-ttu-id="c4718-142">在成功迁移后，跳过将 *project.json*、*global.json* 和 *\*.xproj* 移动到 `backup` 目录的步骤。</span><span class="sxs-lookup"><span data-stu-id="c4718-142">Skip moving *project.json*, *global.json*, and *\*.xproj* to a `backup` directory after successful migration.</span></span>

## <a name="examples"></a><span data-ttu-id="c4718-143">示例</span><span class="sxs-lookup"><span data-stu-id="c4718-143">Examples</span></span>

<span data-ttu-id="c4718-144">将当前目录中的项目及其所有项目迁移到项目依赖项：</span><span class="sxs-lookup"><span data-stu-id="c4718-144">Migrate a project in the current directory and all of its project-to-project dependencies:</span></span>

`dotnet migrate`

<span data-ttu-id="c4718-145">迁移 *global.json* 文件所包含的所有项目：</span><span class="sxs-lookup"><span data-stu-id="c4718-145">Migrate all projects that *global.json* file includes:</span></span>

`dotnet migrate path/to/global.json`

<span data-ttu-id="c4718-146">仅迁移当前项目，不迁移项目到项目 (P2P) 的依赖项。</span><span class="sxs-lookup"><span data-stu-id="c4718-146">Migrate only the current project and no project-to-project (P2P) dependencies.</span></span> <span data-ttu-id="c4718-147">此外，使用特定的 SDK 版本：</span><span class="sxs-lookup"><span data-stu-id="c4718-147">Also, use a specific SDK version:</span></span>

`dotnet migrate -s -v 1.0.0-preview4`
