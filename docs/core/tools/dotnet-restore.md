---
title: dotnet restore 命令
description: 了解如何使用 dotnet-restore 命令还原依赖项和特定于项目的工具。
ms.date: 02/27/2020
ms.openlocfilehash: e74027ba70ddf6905a12f9691caeb0a406428ad6
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/14/2020
ms.locfileid: "78157019"
---
# <a name="dotnet-restore"></a><span data-ttu-id="5f7db-103">dotnet restore</span><span class="sxs-lookup"><span data-stu-id="5f7db-103">dotnet restore</span></span>

<span data-ttu-id="5f7db-104"> 本文适用于： ✔️ .NET Core 2.1 SDK 及更高版本</span><span class="sxs-lookup"><span data-stu-id="5f7db-104">**This article applies to:** ✔️ .NET Core 2.1 SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="5f7db-105">“属性”</span><span class="sxs-lookup"><span data-stu-id="5f7db-105">Name</span></span>

<span data-ttu-id="5f7db-106">`dotnet restore` - 恢复项目的依赖项和工具。</span><span class="sxs-lookup"><span data-stu-id="5f7db-106">`dotnet restore` - Restores the dependencies and tools of a project.</span></span>

## <a name="synopsis"></a><span data-ttu-id="5f7db-107">摘要</span><span class="sxs-lookup"><span data-stu-id="5f7db-107">Synopsis</span></span>

```dotnetcli
dotnet restore [<ROOT>] [--configfile] [--disable-parallel]
    [--force] [--ignore-failed-sources] [--no-cache]
    [--no-dependencies] [--packages] [-r|--runtime]
    [-s|--source] [-v|--verbosity] [--interactive]

dotnet restore [-h|--help]
```

## <a name="description"></a><span data-ttu-id="5f7db-108">描述</span><span class="sxs-lookup"><span data-stu-id="5f7db-108">Description</span></span>

<span data-ttu-id="5f7db-109">`dotnet restore` 命令使用 NuGet 还原依赖项以及在 project 文件中指定的特定于项目的工具。</span><span class="sxs-lookup"><span data-stu-id="5f7db-109">The `dotnet restore` command uses NuGet to restore dependencies as well as project-specific tools that are specified in the project file.</span></span> <span data-ttu-id="5f7db-110">默认情况下会并行执行对依赖项和工具的还原。</span><span class="sxs-lookup"><span data-stu-id="5f7db-110">By default, the restoration of dependencies and tools are executed in parallel.</span></span>

<span data-ttu-id="5f7db-111">为了还原依赖项，NuGet 需要包所在的源。</span><span class="sxs-lookup"><span data-stu-id="5f7db-111">To restore the dependencies, NuGet needs the feeds where the packages are located.</span></span> <span data-ttu-id="5f7db-112">通常通过“nuGet.config”配置文件提供源  。</span><span class="sxs-lookup"><span data-stu-id="5f7db-112">Feeds are usually provided via the *nuget.config* configuration file.</span></span> <span data-ttu-id="5f7db-113">安装 .NET Core SDK 时提供一个默认的配置文件。</span><span class="sxs-lookup"><span data-stu-id="5f7db-113">A default configuration file is provided when the .NET Core SDK is installed.</span></span> <span data-ttu-id="5f7db-114">可以通过在项目目录中创建自己的 nuGet.config 文件来指定其他源  。</span><span class="sxs-lookup"><span data-stu-id="5f7db-114">You specify additional feeds by creating your own *nuget.config* file in the project directory.</span></span> <span data-ttu-id="5f7db-115">可以使用 - `-s` 选项替代 nuget.config 源  。</span><span class="sxs-lookup"><span data-stu-id="5f7db-115">You can override the *nuget.config* feeds with the - `-s` option.</span></span>

<span data-ttu-id="5f7db-116">对于依赖项，使用 `--packages` 参数指定还原操作期间放置还原包的位置。</span><span class="sxs-lookup"><span data-stu-id="5f7db-116">For dependencies, you specify where the restored packages are placed during the restore operation using the `--packages` argument.</span></span> <span data-ttu-id="5f7db-117">如未指定，将使用默认的 NuGet 包缓存，可在所有操作系统上的用户主目录中的 `.nuget/packages` 目录找到它。</span><span class="sxs-lookup"><span data-stu-id="5f7db-117">If not specified, the default NuGet package cache is used, which is found in the `.nuget/packages` directory in the user's home directory on all operating systems.</span></span> <span data-ttu-id="5f7db-118">例如 Linux 上的 /home/user1 或 Windows 上的 C:\Users\user1   。</span><span class="sxs-lookup"><span data-stu-id="5f7db-118">For example, */home/user1* on Linux or *C:\Users\user1* on Windows.</span></span>

<span data-ttu-id="5f7db-119">对于特定于项目的工具，`dotnet restore` 首先还原打包工具所在的包，然后继续还原 project 文件中指定的工具依赖项。</span><span class="sxs-lookup"><span data-stu-id="5f7db-119">For project-specific tooling, `dotnet restore` first restores the package in which the tool is packed, and then proceeds to restore the tool's dependencies as specified in its project file.</span></span>

### <a name="nugetconfig-differences"></a><span data-ttu-id="5f7db-120">nuget.config 差异</span><span class="sxs-lookup"><span data-stu-id="5f7db-120">nuget.config differences</span></span>

<span data-ttu-id="5f7db-121">`dotnet restore` 命令的行为会受 Nuget.Config 文件（如果有）中某些设置的影响  。</span><span class="sxs-lookup"><span data-stu-id="5f7db-121">The behavior of the `dotnet restore` command is affected by the settings in the *nuget.config* file, if present.</span></span> <span data-ttu-id="5f7db-122">例如，在 NuGet.Config 中设置 `globalPackagesFolder` 会将还原的 NuGet 包置于指定的文件夹中  。</span><span class="sxs-lookup"><span data-stu-id="5f7db-122">For example, setting the `globalPackagesFolder` in *nuget.config* places the restored NuGet packages in the specified folder.</span></span> <span data-ttu-id="5f7db-123">这是在 `dotnet restore` 命令中指定 `--packages` 选项的替代方法。</span><span class="sxs-lookup"><span data-stu-id="5f7db-123">This is an alternative to specifying the `--packages` option on the `dotnet restore` command.</span></span> <span data-ttu-id="5f7db-124">有关详细信息，请参阅 [nuget.config 参考](/nuget/schema/nuget-config-file)。</span><span class="sxs-lookup"><span data-stu-id="5f7db-124">For more information, see the [nuget.config reference](/nuget/schema/nuget-config-file).</span></span>

<span data-ttu-id="5f7db-125">有三个 `dotnet restore` 可忽略的特定设置：</span><span class="sxs-lookup"><span data-stu-id="5f7db-125">There are three specific settings that `dotnet restore` ignores:</span></span>

- [<span data-ttu-id="5f7db-126">bindingRedirects</span><span class="sxs-lookup"><span data-stu-id="5f7db-126">bindingRedirects</span></span>](/nuget/schema/nuget-config-file#bindingredirects-section)

  <span data-ttu-id="5f7db-127">绑定重定向不适用于 `<PackageReference>` 元素，并且 .NET Core 仅支持 NuGet 包的 `<PackageReference>` 元素。</span><span class="sxs-lookup"><span data-stu-id="5f7db-127">Binding redirects don't work with `<PackageReference>` elements and .NET Core only supports `<PackageReference>` elements for NuGet packages.</span></span>

- [<span data-ttu-id="5f7db-128">解决方案</span><span class="sxs-lookup"><span data-stu-id="5f7db-128">solution</span></span>](/nuget/schema/nuget-config-file#solution-section)

  <span data-ttu-id="5f7db-129">此设置特定于 Visual Studio，不适用于 .NET Core。</span><span class="sxs-lookup"><span data-stu-id="5f7db-129">This setting is Visual Studio specific and doesn't apply to .NET Core.</span></span> <span data-ttu-id="5f7db-130">.Net Core 不使用 `packages.config` 文件，而是使用 NuGet 包的 `<PackageReference>` 元素。</span><span class="sxs-lookup"><span data-stu-id="5f7db-130">.NET Core doesn't use a `packages.config` file and instead uses `<PackageReference>` elements for NuGet packages.</span></span>

- [<span data-ttu-id="5f7db-131">trustedSigners</span><span class="sxs-lookup"><span data-stu-id="5f7db-131">trustedSigners</span></span>](/nuget/schema/nuget-config-file#trustedsigners-section)

  <span data-ttu-id="5f7db-132">此设置不适用，如 [NuGet 尚不支持跨平台验证](https://github.com/NuGet/Home/issues/7939)受信任包所述。</span><span class="sxs-lookup"><span data-stu-id="5f7db-132">This setting isn't applicable as [NuGet doesn't yet support cross-platform verification](https://github.com/NuGet/Home/issues/7939) of trusted packages.</span></span>

## <a name="implicit-restore"></a><span data-ttu-id="5f7db-133">隐式还原</span><span class="sxs-lookup"><span data-stu-id="5f7db-133">Implicit restore</span></span>

<span data-ttu-id="5f7db-134">在运行下列命令时，如有必要，会隐式运行 `dotnet restore` 命令：</span><span class="sxs-lookup"><span data-stu-id="5f7db-134">The `dotnet restore` command is run implicitly if necessary when you run the following commands:</span></span>

- [`dotnet new`](dotnet-new.md)
- [`dotnet build`](dotnet-build.md)
- [`dotnet build-server`](dotnet-build-server.md)
- [`dotnet run`](dotnet-run.md)
- [`dotnet test`](dotnet-test.md)
- [`dotnet publish`](dotnet-publish.md)
- [`dotnet pack`](dotnet-pack.md)

<span data-ttu-id="5f7db-135">在大多数情况下无需显式使用 `dotnet restore` 命令。</span><span class="sxs-lookup"><span data-stu-id="5f7db-135">In most cases, you don't need to explicitly use the `dotnet restore` command.</span></span>

<span data-ttu-id="5f7db-136">有时，隐式运行 `dotnet restore` 可能不方便。</span><span class="sxs-lookup"><span data-stu-id="5f7db-136">Sometimes, it might be inconvenient to run `dotnet restore` implicitly.</span></span> <span data-ttu-id="5f7db-137">例如，某些自动化系统（如生成系统）需要显式调用 `dotnet restore`，以控制还原发生的时间，以便可以控制网络使用量。</span><span class="sxs-lookup"><span data-stu-id="5f7db-137">For example, some automated systems, such as build systems, need to call `dotnet restore` explicitly to control when the restore occurs so that they can control network usage.</span></span> <span data-ttu-id="5f7db-138">要防止隐式运行 `dotnet restore`，可以通过上述任意命令使用 `--no-restore` 标记以禁用隐式还原。</span><span class="sxs-lookup"><span data-stu-id="5f7db-138">To prevent `dotnet restore` from running implicitly, you can use the `--no-restore` flag with any of these commands to disable implicit restore.</span></span>

## <a name="arguments"></a><span data-ttu-id="5f7db-139">自变量</span><span class="sxs-lookup"><span data-stu-id="5f7db-139">Arguments</span></span>

- **`ROOT`**

  <span data-ttu-id="5f7db-140">要还原的项目文件的可选路径。</span><span class="sxs-lookup"><span data-stu-id="5f7db-140">Optional path to the project file to restore.</span></span>

## <a name="options"></a><span data-ttu-id="5f7db-141">选项</span><span class="sxs-lookup"><span data-stu-id="5f7db-141">Options</span></span>

- **`--configfile <FILE>`**

  <span data-ttu-id="5f7db-142">供还原操作使用的 NuGet 配置文件 (nuget.config)  。</span><span class="sxs-lookup"><span data-stu-id="5f7db-142">The NuGet configuration file (*nuget.config*) to use for the restore operation.</span></span>

- **`--disable-parallel`**

  <span data-ttu-id="5f7db-143">禁用并行还原多个项目。</span><span class="sxs-lookup"><span data-stu-id="5f7db-143">Disables restoring multiple projects in parallel.</span></span>

- **`--force`**

  <span data-ttu-id="5f7db-144">强制解析所有依赖项，即使上次还原已成功，也不例外。</span><span class="sxs-lookup"><span data-stu-id="5f7db-144">Forces all dependencies to be resolved even if the last restore was successful.</span></span> <span data-ttu-id="5f7db-145">指定此标记等同于删除 project.assets.json 文件  。</span><span class="sxs-lookup"><span data-stu-id="5f7db-145">Specifying this flag is the same as deleting the *project.assets.json* file.</span></span>

- **`-h|--help`**

  <span data-ttu-id="5f7db-146">打印出有关命令的简短帮助。</span><span class="sxs-lookup"><span data-stu-id="5f7db-146">Prints out a short help for the command.</span></span>

- **`--ignore-failed-sources`**

  <span data-ttu-id="5f7db-147">如果存在符合版本要求的包，则源失败时警告。</span><span class="sxs-lookup"><span data-stu-id="5f7db-147">Only warn about failed sources if there are packages meeting the version requirement.</span></span>

- **`--no-cache`**

  <span data-ttu-id="5f7db-148">指定不缓存包和 HTTP 请求。</span><span class="sxs-lookup"><span data-stu-id="5f7db-148">Specifies to not cache packages and HTTP requests.</span></span>

- **`--no-dependencies`**

  <span data-ttu-id="5f7db-149">当使用项目到项目 (P2P) 引用还原项目时，还原根项目，不还原引用。</span><span class="sxs-lookup"><span data-stu-id="5f7db-149">When restoring a project with project-to-project (P2P) references, restores the root project and not the references.</span></span>

- **`--packages <PACKAGES_DIRECTORY>`**

  <span data-ttu-id="5f7db-150">指定还原包的目录。</span><span class="sxs-lookup"><span data-stu-id="5f7db-150">Specifies the directory for restored packages.</span></span>

- **`-r|--runtime <RUNTIME_IDENTIFIER>`**

  <span data-ttu-id="5f7db-151">指定程序包还原的运行时。</span><span class="sxs-lookup"><span data-stu-id="5f7db-151">Specifies a runtime for the package restore.</span></span> <span data-ttu-id="5f7db-152">这用于还原 *.csproj* 文件中的 `<RuntimeIdentifiers>` 标记中未显式列出的运行时的程序包。</span><span class="sxs-lookup"><span data-stu-id="5f7db-152">This is used to restore packages for runtimes not explicitly listed in the `<RuntimeIdentifiers>` tag in the *.csproj* file.</span></span> <span data-ttu-id="5f7db-153">有关运行时标识符 (RID) 的列表，请参阅 [RID 目录](../rid-catalog.md)。</span><span class="sxs-lookup"><span data-stu-id="5f7db-153">For a list of Runtime Identifiers (RIDs), see the [RID catalog](../rid-catalog.md).</span></span> <span data-ttu-id="5f7db-154">通过多次指定此选项提供多个 RID。</span><span class="sxs-lookup"><span data-stu-id="5f7db-154">Provide multiple RIDs by specifying this option multiple times.</span></span>

- **`-s|--source <SOURCE>`**

  <span data-ttu-id="5f7db-155">指定要在还原操作期间使用的 NuGet 包源。</span><span class="sxs-lookup"><span data-stu-id="5f7db-155">Specifies a NuGet package source to use during the restore operation.</span></span> <span data-ttu-id="5f7db-156">此设置会替代 nuget.config 文件中指定的所有源  。</span><span class="sxs-lookup"><span data-stu-id="5f7db-156">This setting overrides all of the sources specified in the *nuget.config* files.</span></span> <span data-ttu-id="5f7db-157">多次指定此选项可以提供多个源。</span><span class="sxs-lookup"><span data-stu-id="5f7db-157">Multiple sources can be provided by specifying this option multiple times.</span></span>

- **`--verbosity <LEVEL>`**

  <span data-ttu-id="5f7db-158">设置命令的详细级别。</span><span class="sxs-lookup"><span data-stu-id="5f7db-158">Sets the verbosity level of the command.</span></span> <span data-ttu-id="5f7db-159">允许使用的值为 `q[uiet]`、`m[inimal]`、`n[ormal]`、`d[etailed]` 和 `diag[nostic]`。</span><span class="sxs-lookup"><span data-stu-id="5f7db-159">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="5f7db-160">默认值是 `minimal`。</span><span class="sxs-lookup"><span data-stu-id="5f7db-160">Default value is `minimal`.</span></span>

- **`--interactive`**

  <span data-ttu-id="5f7db-161">允许命令停止并等待用户输入或操作（例如，完成身份验证）。</span><span class="sxs-lookup"><span data-stu-id="5f7db-161">Allows the command to stop and wait for user input or action (for example to complete authentication).</span></span> <span data-ttu-id="5f7db-162">从 .NET Core 2.1.400 开始。</span><span class="sxs-lookup"><span data-stu-id="5f7db-162">Since .NET Core 2.1.400.</span></span>

## <a name="examples"></a><span data-ttu-id="5f7db-163">示例</span><span class="sxs-lookup"><span data-stu-id="5f7db-163">Examples</span></span>

- <span data-ttu-id="5f7db-164">还原当前目录中项目的依赖项和工具：</span><span class="sxs-lookup"><span data-stu-id="5f7db-164">Restore dependencies and tools for the project in the current directory:</span></span>

  ```dotnetcli
  dotnet restore
  ```

- <span data-ttu-id="5f7db-165">还原在给定路径中找到的 `app1` 项目的依赖项和工具：</span><span class="sxs-lookup"><span data-stu-id="5f7db-165">Restore dependencies and tools for the `app1` project found in the   given path:</span></span>

  ```dotnetcli
  dotnet restore ~/projects/app1/app1.csproj
  ```

- <span data-ttu-id="5f7db-166">通过将提供的文件路径用作源，在当前目录中还原项目的依赖项和工具：</span><span class="sxs-lookup"><span data-stu-id="5f7db-166">Restore the dependencies and tools for the project in the current   directory using the file path provided as the source:</span></span>

  ```dotnetcli
  dotnet restore -s c:\packages\mypackages
  ```

- <span data-ttu-id="5f7db-167">通过将提供的两个文件路径用作源，在当前目录中还原项目的依赖项和工具：</span><span class="sxs-lookup"><span data-stu-id="5f7db-167">Restore the dependencies and tools for the project in the current   directory using the two file paths provided as sources:</span></span>

  ```dotnetcli
  dotnet restore -s c:\packages\mypackages -s c:\packages\myotherpackages
  ```

- <span data-ttu-id="5f7db-168">还原当前目录中项目的依赖项和工具，并显示详细的输出：</span><span class="sxs-lookup"><span data-stu-id="5f7db-168">Restore dependencies and tools for the project in the current directory   showing detailed output:</span></span>

  ```dotnetcli
  dotnet restore --verbosity detailed
  ```
