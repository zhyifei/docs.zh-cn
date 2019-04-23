---
title: dotnet restore 命令
description: 了解如何使用 dotnet-restore 命令还原依赖项和特定于项目的工具。
ms.date: 05/29/2018
ms.openlocfilehash: 3ddb9f679cfcab972483a4cb53ffe2b075867614
ms.sourcegitcommit: 438919211260bb415fc8f96ca3eabc33cf2d681d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2019
ms.locfileid: "59613965"
---
# <a name="dotnet-restore"></a><span data-ttu-id="b52f6-103">dotnet restore</span><span class="sxs-lookup"><span data-stu-id="b52f6-103">dotnet restore</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="b52f6-104">name</span><span class="sxs-lookup"><span data-stu-id="b52f6-104">Name</span></span>

<span data-ttu-id="b52f6-105">`dotnet restore` - 恢复项目的依赖项和工具。</span><span class="sxs-lookup"><span data-stu-id="b52f6-105">`dotnet restore` - Restores the dependencies and tools of a project.</span></span>

## <a name="synopsis"></a><span data-ttu-id="b52f6-106">摘要</span><span class="sxs-lookup"><span data-stu-id="b52f6-106">Synopsis</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="b52f6-107">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="b52f6-107">.NET Core 2.x</span></span>](#tab/netcore2x)

```
dotnet restore [<ROOT>] [--configfile] [--disable-parallel] [--force] [--ignore-failed-sources] [--no-cache]
    [--no-dependencies] [--packages] [-r|--runtime] [-s|--source] [-v|--verbosity] [--interactive]
dotnet restore [-h|--help]
```

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="b52f6-108">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="b52f6-108">.NET Core 1.x</span></span>](#tab/netcore1x)

```
dotnet restore [<ROOT>] [--configfile] [--disable-parallel] [--ignore-failed-sources] [--no-cache]
    [--no-dependencies] [--packages] [-r|--runtime] [-s|--source] [-v|--verbosity]
dotnet restore [-h|--help]
```

---

## <a name="description"></a><span data-ttu-id="b52f6-109">说明</span><span class="sxs-lookup"><span data-stu-id="b52f6-109">Description</span></span>

<span data-ttu-id="b52f6-110">`dotnet restore` 命令使用 NuGet 还原依赖项以及在 project 文件中指定的特定于项目的工具。</span><span class="sxs-lookup"><span data-stu-id="b52f6-110">The `dotnet restore` command uses NuGet to restore dependencies as well as project-specific tools that are specified in the project file.</span></span> <span data-ttu-id="b52f6-111">默认情况下会并行执行对依赖项和工具的还原。</span><span class="sxs-lookup"><span data-stu-id="b52f6-111">By default, the restoration of dependencies and tools are executed in parallel.</span></span>

[!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]

<span data-ttu-id="b52f6-112">为了还原依赖项，NuGet 需要包所在的源。</span><span class="sxs-lookup"><span data-stu-id="b52f6-112">To restore the dependencies, NuGet needs the feeds where the packages are located.</span></span> <span data-ttu-id="b52f6-113">通常通过 *NuGet.config* 配置文件提供源。</span><span class="sxs-lookup"><span data-stu-id="b52f6-113">Feeds are usually provided via the *NuGet.config* configuration file.</span></span> <span data-ttu-id="b52f6-114">安装 CLI 工具时提供一个默认的配置文件。</span><span class="sxs-lookup"><span data-stu-id="b52f6-114">A default configuration file is provided when the CLI tools are installed.</span></span> <span data-ttu-id="b52f6-115">可以通过在项目目录中创建自己的 *NuGet.config* 文件来指定其他源。</span><span class="sxs-lookup"><span data-stu-id="b52f6-115">You specify additional feeds by creating your own *NuGet.config* file in the project directory.</span></span> <span data-ttu-id="b52f6-116">也可以在命令提示符处指定每次调用的其他源。</span><span class="sxs-lookup"><span data-stu-id="b52f6-116">You also specify additional feeds per invocation at a command prompt.</span></span>

<span data-ttu-id="b52f6-117">对于依赖项，使用 `--packages` 参数指定还原操作期间放置还原包的位置。</span><span class="sxs-lookup"><span data-stu-id="b52f6-117">For dependencies, you specify where the restored packages are placed during the restore operation using the `--packages` argument.</span></span> <span data-ttu-id="b52f6-118">如未指定，将使用默认的 NuGet 包缓存，可在所有操作系统上的用户主目录中的 `.nuget/packages` 目录找到它。</span><span class="sxs-lookup"><span data-stu-id="b52f6-118">If not specified, the default NuGet package cache is used, which is found in the `.nuget/packages` directory in the user's home directory on all operating systems.</span></span> <span data-ttu-id="b52f6-119">例如 Linux 上的 /home/user1 或 Windows 上的 C:\Users\user1。</span><span class="sxs-lookup"><span data-stu-id="b52f6-119">For example, */home/user1* on Linux or *C:\Users\user1* on Windows.</span></span>

<span data-ttu-id="b52f6-120">对于特定于项目的工具，`dotnet restore` 首先还原打包工具所在的包，然后继续还原 project 文件中指定的工具依赖项。</span><span class="sxs-lookup"><span data-stu-id="b52f6-120">For project-specific tooling, `dotnet restore` first restores the package in which the tool is packed, and then proceeds to restore the tool's dependencies as specified in its project file.</span></span>

<span data-ttu-id="b52f6-121">`dotnet restore` 命令的行为会受 Nuget.Config 文件（如果有）中某些设置的影响。</span><span class="sxs-lookup"><span data-stu-id="b52f6-121">The behavior of the `dotnet restore` command is affected by some of the settings in the *Nuget.Config* file, if present.</span></span> <span data-ttu-id="b52f6-122">例如，在 NuGet.Config 中设置 `globalPackagesFolder` 会将还原的 NuGet 包置于指定的文件夹中。</span><span class="sxs-lookup"><span data-stu-id="b52f6-122">For example, setting the `globalPackagesFolder` in *NuGet.Config* places the restored NuGet packages in the specified folder.</span></span> <span data-ttu-id="b52f6-123">这是在 `dotnet restore` 命令中指定 `--packages` 选项的替代方法。</span><span class="sxs-lookup"><span data-stu-id="b52f6-123">This is an alternative to specifying the `--packages` option on the `dotnet restore` command.</span></span> <span data-ttu-id="b52f6-124">有关详细信息，请参阅 [NuGet.Config reference](/nuget/schema/nuget-config-file)（NuGet.Config 引用）。</span><span class="sxs-lookup"><span data-stu-id="b52f6-124">For more information, see the [NuGet.Config reference](/nuget/schema/nuget-config-file).</span></span>

## <a name="implicit-dotnet-restore"></a><span data-ttu-id="b52f6-125">隐式 `dotnet restore`</span><span class="sxs-lookup"><span data-stu-id="b52f6-125">Implicit `dotnet restore`</span></span>

<span data-ttu-id="b52f6-126">从 .Net Core 2.0 开始，当发出下列命令时，如有必要，将隐式运行 `dotnet restore`。</span><span class="sxs-lookup"><span data-stu-id="b52f6-126">Starting with .NET Core 2.0, `dotnet restore` is run implicitly if necessary when you issue the following commands:</span></span>

- [`dotnet new`](dotnet-new.md)
- [`dotnet build`](dotnet-build.md)
- [`dotnet build-server`](dotnet-build-server.md)
- [`dotnet run`](dotnet-run.md)
- [`dotnet test`](dotnet-test.md)
- [`dotnet publish`](dotnet-publish.md)
- [`dotnet pack`](dotnet-pack.md)

<span data-ttu-id="b52f6-127">在大多数情况下，不再需要显式使用 `dotnet restore` 命令。</span><span class="sxs-lookup"><span data-stu-id="b52f6-127">In most cases, you no longer need to explicitly use the `dotnet restore` command.</span></span>

<span data-ttu-id="b52f6-128">有时，隐式运行 `dotnet restore` 可能不方便。</span><span class="sxs-lookup"><span data-stu-id="b52f6-128">Sometimes, it might be inconvenient to run `dotnet restore` implicitly.</span></span> <span data-ttu-id="b52f6-129">例如，某些自动化系统（如生成系统）需要显式调用 `dotnet restore`，以控制还原发生的时间，以便可以控制网络使用量。</span><span class="sxs-lookup"><span data-stu-id="b52f6-129">For example, some automated systems, such as build systems, need to call `dotnet restore` explicitly to control when the restore occurs so that they can control network usage.</span></span> <span data-ttu-id="b52f6-130">要防止隐式运行 `dotnet restore`，可以通过上述任意命令使用 `--no-restore` 标记以禁用隐式还原。</span><span class="sxs-lookup"><span data-stu-id="b52f6-130">To prevent `dotnet restore` from running implicitly, you can use the `--no-restore` flag with any of these commands to disable implicit restore.</span></span>

## <a name="arguments"></a><span data-ttu-id="b52f6-131">自变量</span><span class="sxs-lookup"><span data-stu-id="b52f6-131">Arguments</span></span>

`ROOT`

<span data-ttu-id="b52f6-132">要还原的项目文件的可选路径。</span><span class="sxs-lookup"><span data-stu-id="b52f6-132">Optional path to the project file to restore.</span></span>

## <a name="options"></a><span data-ttu-id="b52f6-133">选项</span><span class="sxs-lookup"><span data-stu-id="b52f6-133">Options</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="b52f6-134">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="b52f6-134">.NET Core 2.x</span></span>](#tab/netcore2x)

`--configfile <FILE>`

<span data-ttu-id="b52f6-135">供还原操作使用的 NuGet 配置文件 (*NuGet.config*)。</span><span class="sxs-lookup"><span data-stu-id="b52f6-135">The NuGet configuration file (*NuGet.config*) to use for the restore operation.</span></span>

`--disable-parallel`

<span data-ttu-id="b52f6-136">禁用并行还原多个项目。</span><span class="sxs-lookup"><span data-stu-id="b52f6-136">Disables restoring multiple projects in parallel.</span></span>

`--force`

<span data-ttu-id="b52f6-137">强制解析所有依赖项，即使上次还原已成功，也不例外。</span><span class="sxs-lookup"><span data-stu-id="b52f6-137">Forces all dependencies to be resolved even if the last restore was successful.</span></span> <span data-ttu-id="b52f6-138">指定此标记等同于删除 project.assets.json 文件。</span><span class="sxs-lookup"><span data-stu-id="b52f6-138">Specifying this flag is the same as deleting the *project.assets.json* file.</span></span>

`-h|--help`

<span data-ttu-id="b52f6-139">打印出有关命令的简短帮助。</span><span class="sxs-lookup"><span data-stu-id="b52f6-139">Prints out a short help for the command.</span></span>

`--ignore-failed-sources`

<span data-ttu-id="b52f6-140">如果存在符合版本要求的包，则源失败时警告。</span><span class="sxs-lookup"><span data-stu-id="b52f6-140">Only warn about failed sources if there are packages meeting the version requirement.</span></span>

`--no-cache`

<span data-ttu-id="b52f6-141">指定不缓存包和 HTTP 请求。</span><span class="sxs-lookup"><span data-stu-id="b52f6-141">Specifies to not cache packages and HTTP requests.</span></span>

`--no-dependencies`

<span data-ttu-id="b52f6-142">当使用项目到项目 (P2P) 引用还原项目时，还原根项目，不还原引用。</span><span class="sxs-lookup"><span data-stu-id="b52f6-142">When restoring a project with project-to-project (P2P) references, restores the root project and not the references.</span></span>

`--packages <PACKAGES_DIRECTORY>`

<span data-ttu-id="b52f6-143">指定还原包的目录。</span><span class="sxs-lookup"><span data-stu-id="b52f6-143">Specifies the directory for restored packages.</span></span>

`-r|--runtime <RUNTIME_IDENTIFIER>`

<span data-ttu-id="b52f6-144">指定程序包还原的运行时。</span><span class="sxs-lookup"><span data-stu-id="b52f6-144">Specifies a runtime for the package restore.</span></span> <span data-ttu-id="b52f6-145">这用于还原 *.csproj* 文件中的 `<RuntimeIdentifiers>` 标记中未显式列出的运行时的程序包。</span><span class="sxs-lookup"><span data-stu-id="b52f6-145">This is used to restore packages for runtimes not explicitly listed in the `<RuntimeIdentifiers>` tag in the *.csproj* file.</span></span> <span data-ttu-id="b52f6-146">有关运行时标识符 (RID) 的列表，请参阅 [RID 目录](../rid-catalog.md)。</span><span class="sxs-lookup"><span data-stu-id="b52f6-146">For a list of Runtime Identifiers (RIDs), see the [RID catalog](../rid-catalog.md).</span></span> <span data-ttu-id="b52f6-147">通过多次指定此选项提供多个 RID。</span><span class="sxs-lookup"><span data-stu-id="b52f6-147">Provide multiple RIDs by specifying this option multiple times.</span></span>

`-s|--source <SOURCE>`

<span data-ttu-id="b52f6-148">指定要在还原操作期间使用的 NuGet 包源。</span><span class="sxs-lookup"><span data-stu-id="b52f6-148">Specifies a NuGet package source to use during the restore operation.</span></span> <span data-ttu-id="b52f6-149">此设置会替代 NuGet.config 文件中指定的所有源。</span><span class="sxs-lookup"><span data-stu-id="b52f6-149">This setting overrides all of the sources specified in the *NuGet.config* files.</span></span> <span data-ttu-id="b52f6-150">多次指定此选项可以提供多个源。</span><span class="sxs-lookup"><span data-stu-id="b52f6-150">Multiple sources can be provided by specifying this option multiple times.</span></span>

`--verbosity <LEVEL>`

<span data-ttu-id="b52f6-151">设置命令的详细级别。</span><span class="sxs-lookup"><span data-stu-id="b52f6-151">Sets the verbosity level of the command.</span></span> <span data-ttu-id="b52f6-152">允许使用的值为 `q[uiet]`、`m[inimal]`、`n[ormal]`、`d[etailed]` 和 `diag[nostic]`。</span><span class="sxs-lookup"><span data-stu-id="b52f6-152">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

`--interactive`

<span data-ttu-id="b52f6-153">允许命令停止并等待用户输入或操作（例如，完成身份验证）。</span><span class="sxs-lookup"><span data-stu-id="b52f6-153">Allows the command to stop and wait for user input or action (for example to complete authentication).</span></span> <span data-ttu-id="b52f6-154">从 .NET Core 2.1.400 开始。</span><span class="sxs-lookup"><span data-stu-id="b52f6-154">Since .NET Core 2.1.400.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="b52f6-155">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="b52f6-155">.NET Core 1.x</span></span>](#tab/netcore1x)

`--configfile <FILE>`

<span data-ttu-id="b52f6-156">供还原操作使用的 NuGet 配置文件 (*NuGet.config*)。</span><span class="sxs-lookup"><span data-stu-id="b52f6-156">The NuGet configuration file (*NuGet.config*) to use for the restore operation.</span></span>

`--disable-parallel`

<span data-ttu-id="b52f6-157">禁用并行还原多个项目。</span><span class="sxs-lookup"><span data-stu-id="b52f6-157">Disables restoring multiple projects in parallel.</span></span>

`-h|--help`

<span data-ttu-id="b52f6-158">打印出有关命令的简短帮助。</span><span class="sxs-lookup"><span data-stu-id="b52f6-158">Prints out a short help for the command.</span></span>

`--ignore-failed-sources`

<span data-ttu-id="b52f6-159">如果存在符合版本要求的包，则源失败时警告。</span><span class="sxs-lookup"><span data-stu-id="b52f6-159">Only warn about failed sources if there are packages meeting the version requirement.</span></span>

`--no-cache`

<span data-ttu-id="b52f6-160">指定不缓存包和 HTTP 请求。</span><span class="sxs-lookup"><span data-stu-id="b52f6-160">Specifies to not cache packages and HTTP requests.</span></span>

`--no-dependencies`

<span data-ttu-id="b52f6-161">当使用项目到项目 (P2P) 引用还原项目时，还原根项目，不还原引用。</span><span class="sxs-lookup"><span data-stu-id="b52f6-161">When restoring a project with project-to-project (P2P) references, restores the root project and not the references.</span></span>

`--packages <PACKAGES_DIRECTORY>`

<span data-ttu-id="b52f6-162">指定还原包的目录。</span><span class="sxs-lookup"><span data-stu-id="b52f6-162">Specifies the directory for restored packages.</span></span>

`-r|--runtime <RUNTIME_IDENTIFIER>`

<span data-ttu-id="b52f6-163">指定程序包还原的运行时。</span><span class="sxs-lookup"><span data-stu-id="b52f6-163">Specifies a runtime for the package restore.</span></span> <span data-ttu-id="b52f6-164">这用于还原 *.csproj* 文件中的 `<RuntimeIdentifiers>` 标记中未显式列出的运行时的程序包。</span><span class="sxs-lookup"><span data-stu-id="b52f6-164">This is used to restore packages for runtimes not explicitly listed in the `<RuntimeIdentifiers>` tag in the *.csproj* file.</span></span> <span data-ttu-id="b52f6-165">有关运行时标识符 (RID) 的列表，请参阅 [RID 目录](../rid-catalog.md)。</span><span class="sxs-lookup"><span data-stu-id="b52f6-165">For a list of Runtime Identifiers (RIDs), see the [RID catalog](../rid-catalog.md).</span></span> <span data-ttu-id="b52f6-166">通过多次指定此选项提供多个 RID。</span><span class="sxs-lookup"><span data-stu-id="b52f6-166">Provide multiple RIDs by specifying this option multiple times.</span></span>

`-s|--source <SOURCE>`

<span data-ttu-id="b52f6-167">指定要在还原操作期间使用的 NuGet 包源。</span><span class="sxs-lookup"><span data-stu-id="b52f6-167">Specifies a NuGet package source to use during the restore operation.</span></span> <span data-ttu-id="b52f6-168">这会替代 NuGet.config 文件中指定的所有源。</span><span class="sxs-lookup"><span data-stu-id="b52f6-168">This overrides all of the sources specified in the *NuGet.config* files.</span></span> <span data-ttu-id="b52f6-169">多次指定此选项可以提供多个源。</span><span class="sxs-lookup"><span data-stu-id="b52f6-169">Multiple sources can be provided by specifying this option multiple times.</span></span>

`--verbosity <LEVEL>`

<span data-ttu-id="b52f6-170">设置命令的详细级别。</span><span class="sxs-lookup"><span data-stu-id="b52f6-170">Sets the verbosity level of the command.</span></span> <span data-ttu-id="b52f6-171">允许使用的值为 `q[uiet]`、`m[inimal]`、`n[ormal]`、`d[etailed]` 和 `diag[nostic]`。</span><span class="sxs-lookup"><span data-stu-id="b52f6-171">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

---

## <a name="examples"></a><span data-ttu-id="b52f6-172">示例</span><span class="sxs-lookup"><span data-stu-id="b52f6-172">Examples</span></span>

<span data-ttu-id="b52f6-173">还原当前目录中项目的依赖项和工具：</span><span class="sxs-lookup"><span data-stu-id="b52f6-173">Restore dependencies and tools for the project in the current directory:</span></span>

`dotnet restore`

<span data-ttu-id="b52f6-174">还原在给定路径中找到的 `app1` 项目的依赖项和工具：</span><span class="sxs-lookup"><span data-stu-id="b52f6-174">Restore dependencies and tools for the `app1` project found in the given path:</span></span>

`dotnet restore ~/projects/app1/app1.csproj`

<span data-ttu-id="b52f6-175">通过将提供的文件路径用作源，在当前目录中还原项目的依赖项和工具：</span><span class="sxs-lookup"><span data-stu-id="b52f6-175">Restore the dependencies and tools for the project in the current directory using the file path provided as the source:</span></span>

`dotnet restore -s c:\packages\mypackages`

<span data-ttu-id="b52f6-176">通过将提供的两个文件路径用作源，在当前目录中还原项目的依赖项和工具：</span><span class="sxs-lookup"><span data-stu-id="b52f6-176">Restore the dependencies and tools for the project in the current directory using the two file paths provided as sources:</span></span>

`dotnet restore -s c:\packages\mypackages -s c:\packages\myotherpackages`

<span data-ttu-id="b52f6-177">还原当前目录中项目的依赖项和工具，并仅显示最少的输出：</span><span class="sxs-lookup"><span data-stu-id="b52f6-177">Restore dependencies and tools for the project in the current directory and shows only minimal output:</span></span>

`dotnet restore --verbosity minimal`
