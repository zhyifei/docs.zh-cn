---
title: dotnet restore 命令 - .NET Core CLI
description: 了解如何使用 dotnet-restore 命令还原依赖项和特定于项目的工具。
author: mairaw
ms.author: mairaw
ms.date: 05/29/2018
ms.openlocfilehash: fcfa3f2f7133c3add2b02823937dd26fce690453
ms.sourcegitcommit: bbf70abe6b46073148f78cbf0619de6092b5800c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/04/2018
ms.locfileid: "34696580"
---
# <a name="dotnet-restore"></a><span data-ttu-id="c4c93-103">dotnet restore</span><span class="sxs-lookup"><span data-stu-id="c4c93-103">dotnet restore</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="c4c93-104">name</span><span class="sxs-lookup"><span data-stu-id="c4c93-104">Name</span></span>

<span data-ttu-id="c4c93-105">`dotnet restore` - 恢复项目的依赖项和工具。</span><span class="sxs-lookup"><span data-stu-id="c4c93-105">`dotnet restore` - Restores the dependencies and tools of a project.</span></span>

## <a name="synopsis"></a><span data-ttu-id="c4c93-106">摘要</span><span class="sxs-lookup"><span data-stu-id="c4c93-106">Synopsis</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="c4c93-107">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="c4c93-107">.NET Core 2.x</span></span>](#tab/netcore2x)
```
dotnet restore [<ROOT>] [--configfile] [--disable-parallel] [--force] [--ignore-failed-sources] [--no-cache]
    [--no-dependencies] [--packages] [-r|--runtime] [-s|--source] [-v|--verbosity]
dotnet restore [-h|--help]
```
# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="c4c93-108">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="c4c93-108">.NET Core 1.x</span></span>](#tab/netcore1x)
```
dotnet restore [<ROOT>] [--configfile] [--disable-parallel] [--ignore-failed-sources] [--no-cache]
    [--no-dependencies] [--packages] [-r|--runtime] [-s|--source] [-v|--verbosity]
dotnet restore [-h|--help]
```
---

## <a name="description"></a><span data-ttu-id="c4c93-109">描述</span><span class="sxs-lookup"><span data-stu-id="c4c93-109">Description</span></span>

<span data-ttu-id="c4c93-110">`dotnet restore` 命令使用 NuGet 还原依赖项以及在 project 文件中指定的特定于项目的工具。</span><span class="sxs-lookup"><span data-stu-id="c4c93-110">The `dotnet restore` command uses NuGet to restore dependencies as well as project-specific tools that are specified in the project file.</span></span> <span data-ttu-id="c4c93-111">默认情况下会并行执行对依赖项和工具的还原。</span><span class="sxs-lookup"><span data-stu-id="c4c93-111">By default, the restoration of dependencies and tools are executed in parallel.</span></span>

[!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]

<span data-ttu-id="c4c93-112">为了还原依赖项，NuGet 需要包所在的源。</span><span class="sxs-lookup"><span data-stu-id="c4c93-112">To restore the dependencies, NuGet needs the feeds where the packages are located.</span></span> <span data-ttu-id="c4c93-113">通常通过 *NuGet.config* 配置文件提供源。</span><span class="sxs-lookup"><span data-stu-id="c4c93-113">Feeds are usually provided via the *NuGet.config* configuration file.</span></span> <span data-ttu-id="c4c93-114">安装 CLI 工具时提供一个默认的配置文件。</span><span class="sxs-lookup"><span data-stu-id="c4c93-114">A default configuration file is provided when the CLI tools are installed.</span></span> <span data-ttu-id="c4c93-115">可以通过在项目目录中创建自己的 *NuGet.config* 文件来指定其他源。</span><span class="sxs-lookup"><span data-stu-id="c4c93-115">You specify additional feeds by creating your own *NuGet.config* file in the project directory.</span></span> <span data-ttu-id="c4c93-116">也可以在命令提示符处指定每次调用的其他源。</span><span class="sxs-lookup"><span data-stu-id="c4c93-116">You also specify additional feeds per invocation at a command prompt.</span></span>

<span data-ttu-id="c4c93-117">对于依赖项，使用 `--packages` 参数指定还原操作期间放置还原包的位置。</span><span class="sxs-lookup"><span data-stu-id="c4c93-117">For dependencies, you specify where the restored packages are placed during the restore operation using the `--packages` argument.</span></span> <span data-ttu-id="c4c93-118">如未指定，将使用默认的 NuGet 包缓存，可在所有操作系统上的用户主目录中的 `.nuget/packages` 目录找到它。</span><span class="sxs-lookup"><span data-stu-id="c4c93-118">If not specified, the default NuGet package cache is used, which is found in the `.nuget/packages` directory in the user's home directory on all operating systems.</span></span> <span data-ttu-id="c4c93-119">例如 Linux 上的 /home/user1 或 Windows 上的 C:\Users\user1。</span><span class="sxs-lookup"><span data-stu-id="c4c93-119">For example, */home/user1* on Linux or *C:\Users\user1* on Windows.</span></span>

<span data-ttu-id="c4c93-120">对于特定于项目的工具，`dotnet restore` 首先还原打包工具所在的包，然后继续还原 project 文件中指定的工具依赖项。</span><span class="sxs-lookup"><span data-stu-id="c4c93-120">For project-specific tooling, `dotnet restore` first restores the package in which the tool is packed, and then proceeds to restore the tool's dependencies as specified in its project file.</span></span>

<span data-ttu-id="c4c93-121">`dotnet restore` 命令的行为会受 Nuget.Config 文件（如果有）中某些设置的影响。</span><span class="sxs-lookup"><span data-stu-id="c4c93-121">The behavior of the `dotnet restore` command is affected by some of the settings in the *Nuget.Config* file, if present.</span></span> <span data-ttu-id="c4c93-122">例如，在 NuGet.Config 中设置 `globalPackagesFolder` 会将还原的 NuGet 包置于指定的文件夹中。</span><span class="sxs-lookup"><span data-stu-id="c4c93-122">For example, setting the `globalPackagesFolder` in *NuGet.Config* places the restored NuGet packages in the specified folder.</span></span> <span data-ttu-id="c4c93-123">这是在 `dotnet restore` 命令中指定 `--packages` 选项的替代方法。</span><span class="sxs-lookup"><span data-stu-id="c4c93-123">This is an alternative to specifying the `--packages` option on the `dotnet restore` command.</span></span> <span data-ttu-id="c4c93-124">有关详细信息，请参阅 [NuGet.Config reference](/nuget/schema/nuget-config-file)（NuGet.Config 引用）。</span><span class="sxs-lookup"><span data-stu-id="c4c93-124">For more information, see the [NuGet.Config reference](/nuget/schema/nuget-config-file).</span></span>

## <a name="implicit-dotnet-restore"></a><span data-ttu-id="c4c93-125">隐式 `dotnet restore`</span><span class="sxs-lookup"><span data-stu-id="c4c93-125">Implicit `dotnet restore`</span></span>

<span data-ttu-id="c4c93-126">从 .Net Core 2.0 开始，当发出下列命令时，如有必要，将隐式运行 `dotnet restore`。</span><span class="sxs-lookup"><span data-stu-id="c4c93-126">Starting with .NET Core 2.0, `dotnet restore` is run implicitly if necessary when you issue the following commands:</span></span>

- [`dotnet new`](dotnet-new.md)
- [`dotnet build`](dotnet-build.md)
- [`dotnet build server`](dotnet-build-server.md)
- [`dotnet run`](dotnet-run.md)
- [`dotnet test`](dotnet-test.md)
- [`dotnet publish`](dotnet-publish.md)
- [`dotnet pack`](dotnet-pack.md)

<span data-ttu-id="c4c93-127">在大多数情况下，不再需要显式使用 `dotnet restore` 命令。</span><span class="sxs-lookup"><span data-stu-id="c4c93-127">In most cases, you no longer need to explicitly use the `dotnet restore` command.</span></span>

<span data-ttu-id="c4c93-128">有时，隐式运行 `dotnet restore` 可能不方便。</span><span class="sxs-lookup"><span data-stu-id="c4c93-128">Sometimes, it might be inconvenient to run `dotnet restore` implicitly.</span></span> <span data-ttu-id="c4c93-129">例如，某些自动化系统（如生成系统）需要显式调用 `dotnet restore`，以控制还原发生的时间，以便可以控制网络使用量。</span><span class="sxs-lookup"><span data-stu-id="c4c93-129">For example, some automated systems, such as build systems, need to call `dotnet restore` explicitly to control when the restore occurs so that they can control network usage.</span></span> <span data-ttu-id="c4c93-130">要防止隐式运行 `dotnet restore`，可以通过上述任意命令使用 `--no-restore` 标记以禁用隐式还原。</span><span class="sxs-lookup"><span data-stu-id="c4c93-130">To prevent `dotnet restore` from running implicitly, you can use the `--no-restore` flag with any of these commands to disable implicit restore.</span></span>

## <a name="arguments"></a><span data-ttu-id="c4c93-131">自变量</span><span class="sxs-lookup"><span data-stu-id="c4c93-131">Arguments</span></span>

`ROOT`

<span data-ttu-id="c4c93-132">要还原的项目文件的可选路径。</span><span class="sxs-lookup"><span data-stu-id="c4c93-132">Optional path to the project file to restore.</span></span>

## <a name="options"></a><span data-ttu-id="c4c93-133">选项</span><span class="sxs-lookup"><span data-stu-id="c4c93-133">Options</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="c4c93-134">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="c4c93-134">.NET Core 2.x</span></span>](#tab/netcore2x)

`--configfile <FILE>`

<span data-ttu-id="c4c93-135">供还原操作使用的 NuGet 配置文件 (*NuGet.config*)。</span><span class="sxs-lookup"><span data-stu-id="c4c93-135">The NuGet configuration file (*NuGet.config*) to use for the restore operation.</span></span>

`--disable-parallel`

<span data-ttu-id="c4c93-136">禁用并行还原多个项目。</span><span class="sxs-lookup"><span data-stu-id="c4c93-136">Disables restoring multiple projects in parallel.</span></span>

`--force`

<span data-ttu-id="c4c93-137">强制解析所有依赖项，即使上次还原已成功，也不例外。</span><span class="sxs-lookup"><span data-stu-id="c4c93-137">Forces all dependencies to be resolved even if the last restore was successful.</span></span> <span data-ttu-id="c4c93-138">指定此标记等同于删除 project.assets.json 文件。</span><span class="sxs-lookup"><span data-stu-id="c4c93-138">Specifying this flag is the same as deleting the *project.assets.json* file.</span></span>

`-h|--help`

<span data-ttu-id="c4c93-139">打印出有关命令的简短帮助。</span><span class="sxs-lookup"><span data-stu-id="c4c93-139">Prints out a short help for the command.</span></span>

`--ignore-failed-sources`

<span data-ttu-id="c4c93-140">如果存在符合版本要求的包，则源失败时警告。</span><span class="sxs-lookup"><span data-stu-id="c4c93-140">Only warn about failed sources if there are packages meeting the version requirement.</span></span>

`--no-cache`

<span data-ttu-id="c4c93-141">指定不缓存包和 HTTP 请求。</span><span class="sxs-lookup"><span data-stu-id="c4c93-141">Specifies to not cache packages and HTTP requests.</span></span>

`--no-dependencies`

<span data-ttu-id="c4c93-142">当使用项目到项目 (P2P) 引用还原项目时，还原根项目，不还原引用。</span><span class="sxs-lookup"><span data-stu-id="c4c93-142">When restoring a project with project-to-project (P2P) references, restores the root project and not the references.</span></span>

`--packages <PACKAGES_DIRECTORY>`

<span data-ttu-id="c4c93-143">指定还原包的目录。</span><span class="sxs-lookup"><span data-stu-id="c4c93-143">Specifies the directory for restored packages.</span></span>

`-r|--runtime <RUNTIME_IDENTIFIER>`

<span data-ttu-id="c4c93-144">指定程序包还原的运行时。</span><span class="sxs-lookup"><span data-stu-id="c4c93-144">Specifies a runtime for the package restore.</span></span> <span data-ttu-id="c4c93-145">这用于还原 *.csproj* 文件中的 `<RuntimeIdentifiers>` 标记中未显式列出的运行时的程序包。</span><span class="sxs-lookup"><span data-stu-id="c4c93-145">This is used to restore packages for runtimes not explicitly listed in the `<RuntimeIdentifiers>` tag in the *.csproj* file.</span></span> <span data-ttu-id="c4c93-146">有关运行时标识符 (RID) 的列表，请参阅 [RID 目录](../rid-catalog.md)。</span><span class="sxs-lookup"><span data-stu-id="c4c93-146">For a list of Runtime Identifiers (RIDs), see the [RID catalog](../rid-catalog.md).</span></span> <span data-ttu-id="c4c93-147">通过多次指定此选项提供多个 RID。</span><span class="sxs-lookup"><span data-stu-id="c4c93-147">Provide multiple RIDs by specifying this option multiple times.</span></span>

`-s|--source <SOURCE>`

<span data-ttu-id="c4c93-148">指定要在还原操作期间使用的 NuGet 包源。</span><span class="sxs-lookup"><span data-stu-id="c4c93-148">Specifies a NuGet package source to use during the restore operation.</span></span> <span data-ttu-id="c4c93-149">此设置会替代 NuGet.config 文件中指定的所有源。</span><span class="sxs-lookup"><span data-stu-id="c4c93-149">This setting overrides all of the sources specified in the *NuGet.config* files.</span></span> <span data-ttu-id="c4c93-150">多次指定此选项可以提供多个源。</span><span class="sxs-lookup"><span data-stu-id="c4c93-150">Multiple sources can be provided by specifying this option multiple times.</span></span>

`--verbosity <LEVEL>`

<span data-ttu-id="c4c93-151">设置命令的详细级别。</span><span class="sxs-lookup"><span data-stu-id="c4c93-151">Sets the verbosity level of the command.</span></span> <span data-ttu-id="c4c93-152">允许使用的值为 `q[uiet]`、`m[inimal]`、`n[ormal]`、`d[etailed]` 和 `diag[nostic]`。</span><span class="sxs-lookup"><span data-stu-id="c4c93-152">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="c4c93-153">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="c4c93-153">.NET Core 1.x</span></span>](#tab/netcore1x)

`--configfile <FILE>`

<span data-ttu-id="c4c93-154">供还原操作使用的 NuGet 配置文件 (*NuGet.config*)。</span><span class="sxs-lookup"><span data-stu-id="c4c93-154">The NuGet configuration file (*NuGet.config*) to use for the restore operation.</span></span>

`--disable-parallel`

<span data-ttu-id="c4c93-155">禁用并行还原多个项目。</span><span class="sxs-lookup"><span data-stu-id="c4c93-155">Disables restoring multiple projects in parallel.</span></span>

`-h|--help`

<span data-ttu-id="c4c93-156">打印出有关命令的简短帮助。</span><span class="sxs-lookup"><span data-stu-id="c4c93-156">Prints out a short help for the command.</span></span>

`--ignore-failed-sources`

<span data-ttu-id="c4c93-157">如果存在符合版本要求的包，则源失败时警告。</span><span class="sxs-lookup"><span data-stu-id="c4c93-157">Only warn about failed sources if there are packages meeting the version requirement.</span></span>

`--no-cache`

<span data-ttu-id="c4c93-158">指定不缓存包和 HTTP 请求。</span><span class="sxs-lookup"><span data-stu-id="c4c93-158">Specifies to not cache packages and HTTP requests.</span></span>

`--no-dependencies`

<span data-ttu-id="c4c93-159">当使用项目到项目 (P2P) 引用还原项目时，还原根项目，不还原引用。</span><span class="sxs-lookup"><span data-stu-id="c4c93-159">When restoring a project with project-to-project (P2P) references, restores the root project and not the references.</span></span>

`--packages <PACKAGES_DIRECTORY>`

<span data-ttu-id="c4c93-160">指定还原包的目录。</span><span class="sxs-lookup"><span data-stu-id="c4c93-160">Specifies the directory for restored packages.</span></span>

`-r|--runtime <RUNTIME_IDENTIFIER>`

<span data-ttu-id="c4c93-161">指定程序包还原的运行时。</span><span class="sxs-lookup"><span data-stu-id="c4c93-161">Specifies a runtime for the package restore.</span></span> <span data-ttu-id="c4c93-162">这用于还原 *.csproj* 文件中的 `<RuntimeIdentifiers>` 标记中未显式列出的运行时的程序包。</span><span class="sxs-lookup"><span data-stu-id="c4c93-162">This is used to restore packages for runtimes not explicitly listed in the `<RuntimeIdentifiers>` tag in the *.csproj* file.</span></span> <span data-ttu-id="c4c93-163">有关运行时标识符 (RID) 的列表，请参阅 [RID 目录](../rid-catalog.md)。</span><span class="sxs-lookup"><span data-stu-id="c4c93-163">For a list of Runtime Identifiers (RIDs), see the [RID catalog](../rid-catalog.md).</span></span> <span data-ttu-id="c4c93-164">通过多次指定此选项提供多个 RID。</span><span class="sxs-lookup"><span data-stu-id="c4c93-164">Provide multiple RIDs by specifying this option multiple times.</span></span>

`-s|--source <SOURCE>`

<span data-ttu-id="c4c93-165">指定要在还原操作期间使用的 NuGet 包源。</span><span class="sxs-lookup"><span data-stu-id="c4c93-165">Specifies a NuGet package source to use during the restore operation.</span></span> <span data-ttu-id="c4c93-166">这会替代 NuGet.config 文件中指定的所有源。</span><span class="sxs-lookup"><span data-stu-id="c4c93-166">This overrides all of the sources specified in the *NuGet.config* files.</span></span> <span data-ttu-id="c4c93-167">多次指定此选项可以提供多个源。</span><span class="sxs-lookup"><span data-stu-id="c4c93-167">Multiple sources can be provided by specifying this option multiple times.</span></span>

`--verbosity <LEVEL>`

<span data-ttu-id="c4c93-168">设置命令的详细级别。</span><span class="sxs-lookup"><span data-stu-id="c4c93-168">Sets the verbosity level of the command.</span></span> <span data-ttu-id="c4c93-169">允许使用的值为 `q[uiet]`、`m[inimal]`、`n[ormal]`、`d[etailed]` 和 `diag[nostic]`。</span><span class="sxs-lookup"><span data-stu-id="c4c93-169">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

## <a name="examples"></a><span data-ttu-id="c4c93-170">示例</span><span class="sxs-lookup"><span data-stu-id="c4c93-170">Examples</span></span>

<span data-ttu-id="c4c93-171">还原当前目录中项目的依赖项和工具：</span><span class="sxs-lookup"><span data-stu-id="c4c93-171">Restore dependencies and tools for the project in the current directory:</span></span>

`dotnet restore`

<span data-ttu-id="c4c93-172">还原在给定路径中找到的 `app1` 项目的依赖项和工具：</span><span class="sxs-lookup"><span data-stu-id="c4c93-172">Restore dependencies and tools for the `app1` project found in the given path:</span></span>

`dotnet restore ~/projects/app1/app1.csproj`

<span data-ttu-id="c4c93-173">通过将提供的文件路径用作源，在当前目录中还原项目的依赖项和工具：</span><span class="sxs-lookup"><span data-stu-id="c4c93-173">Restore the dependencies and tools for the project in the current directory using the file path provided as the source:</span></span>

`dotnet restore -s c:\packages\mypackages`

<span data-ttu-id="c4c93-174">通过将提供的两个文件路径用作源，在当前目录中还原项目的依赖项和工具：</span><span class="sxs-lookup"><span data-stu-id="c4c93-174">Restore the dependencies and tools for the project in the current directory using the two file paths provided as sources:</span></span>

`dotnet restore -s c:\packages\mypackages -s c:\packages\myotherpackages`

<span data-ttu-id="c4c93-175">还原当前目录中项目的依赖项和工具，并仅显示最少的输出：</span><span class="sxs-lookup"><span data-stu-id="c4c93-175">Restore dependencies and tools for the project in the current directory and shows only minimal output:</span></span>

`dotnet restore --verbosity minimal`
