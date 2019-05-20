---
title: dotnet build 命令
description: dotnet build 命令可生成项目及其所有依赖项。
ms.date: 04/24/2019
ms.openlocfilehash: 6564aacbe520797b47095929cfe72c6b180b99a7
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/15/2019
ms.locfileid: "65632137"
---
# <a name="dotnet-build"></a><span data-ttu-id="1cf27-103">dotnet 生成</span><span class="sxs-lookup"><span data-stu-id="1cf27-103">dotnet build</span></span>

<span data-ttu-id="1cf27-104">**本文适用于：✓** .NET Core 1.x SDK 及更高版本</span><span class="sxs-lookup"><span data-stu-id="1cf27-104">**This article applies to: ✓** .NET Core 1.x SDK and later versions</span></span>

<!-- todo: uncomment when all CLI commands are reviewed
[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]
-->

## <a name="name"></a><span data-ttu-id="1cf27-105">name</span><span class="sxs-lookup"><span data-stu-id="1cf27-105">Name</span></span>

<span data-ttu-id="1cf27-106">`dotnet build` - 生成项目及其所有依赖项。</span><span class="sxs-lookup"><span data-stu-id="1cf27-106">`dotnet build` - Builds a project and all of its dependencies.</span></span>

## <a name="synopsis"></a><span data-ttu-id="1cf27-107">摘要</span><span class="sxs-lookup"><span data-stu-id="1cf27-107">Synopsis</span></span>

```
dotnet build [<PROJECT>|<SOLUTION>] [-c|--configuration] [-f|--framework] [--force] [--interactive] [--no-dependencies]
    [--no-incremental] [--nologo] [--no-restore] [-o|--output] [-r|--runtime] [-v|--verbosity] [--version-suffix]

dotnet build [-h|--help]
```

## <a name="description"></a><span data-ttu-id="1cf27-108">说明</span><span class="sxs-lookup"><span data-stu-id="1cf27-108">Description</span></span>

<span data-ttu-id="1cf27-109">`dotnet build` 命令将项目及其依赖项生成为一组二进制文件。</span><span class="sxs-lookup"><span data-stu-id="1cf27-109">The `dotnet build` command builds the project and its dependencies into a set of binaries.</span></span> <span data-ttu-id="1cf27-110">二进制文件包括中间语言 (IL) 文件（带 *.dll* 扩展名）和用于调试的符号文件（带 *.pdb* 扩展名）中的项目的代码。</span><span class="sxs-lookup"><span data-stu-id="1cf27-110">The binaries include the project's code in Intermediate Language (IL) files with a *.dll* extension and symbol files used for debugging with a *.pdb* extension.</span></span> <span data-ttu-id="1cf27-111">生成依赖项 JSON 文件 (*\*.deps.json*)，该文件列出了应用程序的依赖项。</span><span class="sxs-lookup"><span data-stu-id="1cf27-111">A dependencies JSON file (*\*.deps.json*) is produced that lists the dependencies of the application.</span></span> <span data-ttu-id="1cf27-112">生成 *\*.runtimeconfig.json* 文件，该文件指定应用程序的共享运行时及其版本。</span><span class="sxs-lookup"><span data-stu-id="1cf27-112">A *\*.runtimeconfig.json* file is produced, which specifies the shared runtime and its version for the application.</span></span>

<span data-ttu-id="1cf27-113">如果项目有第三方依赖项（如来自 NuGet 的库），将从 NuGet 缓存解析这些依赖项，并且它们不适用于项目的生成输出。</span><span class="sxs-lookup"><span data-stu-id="1cf27-113">If the project has third-party dependencies, such as libraries from NuGet, they're resolved from the NuGet cache and aren't available with the project's built output.</span></span> <span data-ttu-id="1cf27-114">考虑到这一点，`dotnet build` 的产品还未准备好转移到另一台计算机进行运行。</span><span class="sxs-lookup"><span data-stu-id="1cf27-114">With that in mind, the product of `dotnet build` isn't ready to be transferred to another machine to run.</span></span> <span data-ttu-id="1cf27-115">这与 .NET Framework 的行为相反，后者在构建可执行项目（一个应用程序）时，将生成可在任何已安装 .NET Framework 的计算机上运行的输出。</span><span class="sxs-lookup"><span data-stu-id="1cf27-115">This is in contrast to the behavior of the .NET Framework in which building an executable project (an application) produces output that's runnable on any machine where the .NET Framework is installed.</span></span> <span data-ttu-id="1cf27-116">为了能够获得相似的 .NET Core 使用体验，需要使用 [dotnet publish](dotnet-publish.md) 命令。</span><span class="sxs-lookup"><span data-stu-id="1cf27-116">To have a similar experience with .NET Core, you need to use the [dotnet publish](dotnet-publish.md) command.</span></span> <span data-ttu-id="1cf27-117">有关详细信息，请参阅 [.NET Core 应用程序部署](../deploying/index.md)。</span><span class="sxs-lookup"><span data-stu-id="1cf27-117">For more information, see [.NET Core Application Deployment](../deploying/index.md).</span></span>

<span data-ttu-id="1cf27-118">构建需要 *project.assets.json* 文件，该文件列出了你的应用程序的依赖项。</span><span class="sxs-lookup"><span data-stu-id="1cf27-118">Building requires the *project.assets.json* file, which lists the dependencies of your application.</span></span> <span data-ttu-id="1cf27-119">此文件在 [`dotnet restore`](dotnet-restore.md) 执行时创建。</span><span class="sxs-lookup"><span data-stu-id="1cf27-119">The file is created when [`dotnet restore`](dotnet-restore.md) is executed.</span></span> <span data-ttu-id="1cf27-120">如果资产文件未就位，那么工具将无法解析引用程序集，进而导致错误生成。</span><span class="sxs-lookup"><span data-stu-id="1cf27-120">Without the assets file in place, the tooling can't resolve reference assemblies, which results in errors.</span></span> <span data-ttu-id="1cf27-121">使用 .NET Core 1.x SDK，需要在运行 `dotnet build` 之前显式运行 `dotnet restore`。</span><span class="sxs-lookup"><span data-stu-id="1cf27-121">With .NET Core 1.x SDK, you needed to explicitly run the `dotnet restore` before running `dotnet build`.</span></span> <span data-ttu-id="1cf27-122">自 .NET Core 2.0 SDK 起，`dotnet restore` 在 `dotnet build` 运行时隐式运行。</span><span class="sxs-lookup"><span data-stu-id="1cf27-122">Starting with .NET Core 2.0 SDK, `dotnet restore` runs implicitly when you run `dotnet build`.</span></span> <span data-ttu-id="1cf27-123">若要在运行 build 命令时禁用隐式还原，可以传递 `--no-restore` 选项。</span><span class="sxs-lookup"><span data-stu-id="1cf27-123">If you want to disable implicit restore when running the build command, you can pass the `--no-restore` option.</span></span>

[!INCLUDE[dotnet restore note + options](~/includes/dotnet-restore-note-options.md)]

<span data-ttu-id="1cf27-124">项目是否可执行由项目文件中的 `<OutputType>` 属性决定。</span><span class="sxs-lookup"><span data-stu-id="1cf27-124">Whether the project is executable or not is determined by the `<OutputType>` property in the project file.</span></span> <span data-ttu-id="1cf27-125">以下示例显示生成可执行代码的项目：</span><span class="sxs-lookup"><span data-stu-id="1cf27-125">The following example shows a project that produces executable code:</span></span>

```xml
<PropertyGroup>
  <OutputType>Exe</OutputType>
</PropertyGroup>
```

<span data-ttu-id="1cf27-126">若要生成库，请省略 `<OutputType>` 属性。</span><span class="sxs-lookup"><span data-stu-id="1cf27-126">To produce a library, omit the `<OutputType>` property.</span></span> <span data-ttu-id="1cf27-127">生成输出中的主要区别在于，针对某个库的 IL DLL 不包含入口点，并且不能执行。</span><span class="sxs-lookup"><span data-stu-id="1cf27-127">The main difference in built output is that the IL DLL for a library doesn't contain entry points and can't be executed.</span></span>

### <a name="msbuild"></a><span data-ttu-id="1cf27-128">MSBuild</span><span class="sxs-lookup"><span data-stu-id="1cf27-128">MSBuild</span></span>

<span data-ttu-id="1cf27-129">`dotnet build` 使用 MSBuild 生成项目，因此它支持并行生成和增量生成。</span><span class="sxs-lookup"><span data-stu-id="1cf27-129">`dotnet build` uses MSBuild to build the project, so it supports both parallel and incremental builds.</span></span> <span data-ttu-id="1cf27-130">有关详细信息，请参阅[增量生成](/visualstudio/msbuild/incremental-builds)。</span><span class="sxs-lookup"><span data-stu-id="1cf27-130">For more information, see [Incremental Builds](/visualstudio/msbuild/incremental-builds).</span></span>

<span data-ttu-id="1cf27-131">除其自己的选项外，`dotnet build` 命令也接受 MSBuild 选项，如用来设置属性的 `-p` 或用来定义记录器的 `-l`。</span><span class="sxs-lookup"><span data-stu-id="1cf27-131">In addition to its options, the `dotnet build` command accepts MSBuild options, such as `-p` for setting properties or `-l` to define a logger.</span></span> <span data-ttu-id="1cf27-132">有关这些选项的详细信息，请参阅 [MSBuild 命令行参考](/visualstudio/msbuild/msbuild-command-line-reference)。</span><span class="sxs-lookup"><span data-stu-id="1cf27-132">For more information about these options, see the [MSBuild Command-Line Reference](/visualstudio/msbuild/msbuild-command-line-reference).</span></span> <span data-ttu-id="1cf27-133">或者也可以使用 [dotnet msbuild](dotnet-msbuild.md) 命令。</span><span class="sxs-lookup"><span data-stu-id="1cf27-133">Or you can also use the [dotnet msbuild](dotnet-msbuild.md) command.</span></span>

<span data-ttu-id="1cf27-134">运行 `dotnet build` 相当于 `dotnet msbuild -restore -target:Build`。</span><span class="sxs-lookup"><span data-stu-id="1cf27-134">Running `dotnet build` is equivalent to `dotnet msbuild -restore -target:Build`.</span></span>

## <a name="arguments"></a><span data-ttu-id="1cf27-135">自变量</span><span class="sxs-lookup"><span data-stu-id="1cf27-135">Arguments</span></span>

`PROJECT | SOLUTION`

<span data-ttu-id="1cf27-136">要生成的项目或解决方案文件。</span><span class="sxs-lookup"><span data-stu-id="1cf27-136">The project or solution file to build.</span></span> <span data-ttu-id="1cf27-137">如果未指定项目或解决方案文件，MSBuild 会在当前工作目录中搜索文件扩展名以 *proj* 或 *sln* 结尾的文件并使用该文件。</span><span class="sxs-lookup"><span data-stu-id="1cf27-137">If a project or solution file isn't specified, MSBuild searches the current working directory for a file that has a file extension that ends in either *proj* or *sln* and uses that file.</span></span>

## <a name="options"></a><span data-ttu-id="1cf27-138">选项</span><span class="sxs-lookup"><span data-stu-id="1cf27-138">Options</span></span>

* **`-c|--configuration {Debug|Release}`**

  <span data-ttu-id="1cf27-139">定义生成配置。</span><span class="sxs-lookup"><span data-stu-id="1cf27-139">Defines the build configuration.</span></span> <span data-ttu-id="1cf27-140">默认值为 `Debug`。</span><span class="sxs-lookup"><span data-stu-id="1cf27-140">The default value is `Debug`.</span></span>

* **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="1cf27-141">编译特定[框架](../../standard/frameworks.md)。</span><span class="sxs-lookup"><span data-stu-id="1cf27-141">Compiles for a specific [framework](../../standard/frameworks.md).</span></span> <span data-ttu-id="1cf27-142">必须在[项目文件](csproj.md)中定义该框架。</span><span class="sxs-lookup"><span data-stu-id="1cf27-142">The framework must be defined in the [project file](csproj.md).</span></span>

* **`--force`**

  <span data-ttu-id="1cf27-143">强制解析所有依赖项，即使上次还原已成功，也不例外。</span><span class="sxs-lookup"><span data-stu-id="1cf27-143">Forces all dependencies to be resolved even if the last restore was successful.</span></span> <span data-ttu-id="1cf27-144">指定此标记等同于删除 project.assets.json 文件。</span><span class="sxs-lookup"><span data-stu-id="1cf27-144">Specifying this flag is the same as deleting the *project.assets.json* file.</span></span> <span data-ttu-id="1cf27-145">自 .NET Core 2.0 SDK 起可用。</span><span class="sxs-lookup"><span data-stu-id="1cf27-145">Available since .NET Core 2.0 SDK.</span></span>

* **`-h|--help`**

  <span data-ttu-id="1cf27-146">打印出有关命令的简短帮助。</span><span class="sxs-lookup"><span data-stu-id="1cf27-146">Prints out a short help for the command.</span></span>

* **`--interactive`**

  <span data-ttu-id="1cf27-147">允许命令停止并等待用户输入或操作。</span><span class="sxs-lookup"><span data-stu-id="1cf27-147">Allows the command to stop and wait for user input or action.</span></span> <span data-ttu-id="1cf27-148">例如，完成身份验证。</span><span class="sxs-lookup"><span data-stu-id="1cf27-148">For example, to complete authentication.</span></span> <span data-ttu-id="1cf27-149">自 .NET Core 3.0 SDK 起可用。</span><span class="sxs-lookup"><span data-stu-id="1cf27-149">Available since .NET Core 3.0 SDK.</span></span>

* **`--no-dependencies`**

  <span data-ttu-id="1cf27-150">忽略项目到项目 (P2P) 引用，并仅生成指定的根项目。</span><span class="sxs-lookup"><span data-stu-id="1cf27-150">Ignores project-to-project (P2P) references and only builds the specified root project.</span></span>

* **`--no-incremental`**

  <span data-ttu-id="1cf27-151">将生成标记为对增量生成不安全。</span><span class="sxs-lookup"><span data-stu-id="1cf27-151">Marks the build as unsafe for incremental build.</span></span> <span data-ttu-id="1cf27-152">此标记关闭增量编译，并强制完全重新生成项目依赖项关系图。</span><span class="sxs-lookup"><span data-stu-id="1cf27-152">This flag turns off incremental compilation and forces a clean rebuild of the project's dependency graph.</span></span>

* **`--no-logo`**

  <span data-ttu-id="1cf27-153">不显示启动版权标志或版权消息。</span><span class="sxs-lookup"><span data-stu-id="1cf27-153">Doesn't display the startup banner or the copyright message.</span></span> <span data-ttu-id="1cf27-154">自 .NET Core 3.0 SDK 起可用。</span><span class="sxs-lookup"><span data-stu-id="1cf27-154">Available since .NET Core 3.0 SDK.</span></span>

* **`--no-restore`**

  <span data-ttu-id="1cf27-155">在生成期间不执行隐式还原。</span><span class="sxs-lookup"><span data-stu-id="1cf27-155">Doesn't execute an implicit restore during build.</span></span> <span data-ttu-id="1cf27-156">自 .NET Core 2.0 SDK 起可用。</span><span class="sxs-lookup"><span data-stu-id="1cf27-156">Available since .NET Core 2.0 SDK.</span></span>

* **`-o|--output <OUTPUT_DIRECTORY>`**

  <span data-ttu-id="1cf27-157">放置生成二进制文件的目录。</span><span class="sxs-lookup"><span data-stu-id="1cf27-157">Directory in which to place the built binaries.</span></span> <span data-ttu-id="1cf27-158">指定此选项时还需要定义 `--framework`。</span><span class="sxs-lookup"><span data-stu-id="1cf27-158">You also need to define `--framework` when you specify this option.</span></span> <span data-ttu-id="1cf27-159">如果未指定，则默认路径为 `./bin/<configuration>/<framework>/`。</span><span class="sxs-lookup"><span data-stu-id="1cf27-159">If not specified, the default path is `./bin/<configuration>/<framework>/`.</span></span>

* **`-r|--runtime <RUNTIME_IDENTIFIER>`**

  <span data-ttu-id="1cf27-160">指定目标运行时。</span><span class="sxs-lookup"><span data-stu-id="1cf27-160">Specifies the target runtime.</span></span> <span data-ttu-id="1cf27-161">有关运行时标识符 (RID) 的列表，请参阅 [RID 目录](../rid-catalog.md)。</span><span class="sxs-lookup"><span data-stu-id="1cf27-161">For a list of Runtime Identifiers (RIDs), see the [RID catalog](../rid-catalog.md).</span></span>

* **`-v|--verbosity <LEVEL>`**

  <span data-ttu-id="1cf27-162">设置 MSBuild 详细级别。</span><span class="sxs-lookup"><span data-stu-id="1cf27-162">Sets the MSBuild verbosity level.</span></span> <span data-ttu-id="1cf27-163">允许使用的值为 `q[uiet]`、`m[inimal]`、`n[ormal]`、`d[etailed]` 和 `diag[nostic]`。</span><span class="sxs-lookup"><span data-stu-id="1cf27-163">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="1cf27-164">默认值为 `minimal`。</span><span class="sxs-lookup"><span data-stu-id="1cf27-164">The default is `minimal`.</span></span>

* **`--version-suffix <VERSION_SUFFIX>`**

  <span data-ttu-id="1cf27-165">设置生成项目时使用的 `$(VersionSuffix)` 属性的值。</span><span class="sxs-lookup"><span data-stu-id="1cf27-165">Sets the value of the `$(VersionSuffix)` property to use when building the project.</span></span> <span data-ttu-id="1cf27-166">这仅在未设置 `$(Version)` 属性时有效。</span><span class="sxs-lookup"><span data-stu-id="1cf27-166">This only works if the `$(Version)` property isn't set.</span></span> <span data-ttu-id="1cf27-167">然后，`$(Version)` 设置为 `$(VersionPrefix)` 与 `$(VersionSuffix)` 组合，并用短划线分隔。</span><span class="sxs-lookup"><span data-stu-id="1cf27-167">Then, `$(Version)` is set to the `$(VersionPrefix)` combined with the `$(VersionSuffix)`, separated by a dash.</span></span>

## <a name="examples"></a><span data-ttu-id="1cf27-168">示例</span><span class="sxs-lookup"><span data-stu-id="1cf27-168">Examples</span></span>

* <span data-ttu-id="1cf27-169">生成项目及其依赖项：</span><span class="sxs-lookup"><span data-stu-id="1cf27-169">Build a project and its dependencies:</span></span>

  ```console
  dotnet build
  ```

* <span data-ttu-id="1cf27-170">使用“发布”配置生成项目及其依赖项：</span><span class="sxs-lookup"><span data-stu-id="1cf27-170">Build a project and its dependencies using Release configuration:</span></span>

  ```console
  dotnet build --configuration Release
  ```

* <span data-ttu-id="1cf27-171">针对特定运行时（本例中为 Ubuntu 18.04）生成项目及其依赖项：</span><span class="sxs-lookup"><span data-stu-id="1cf27-171">Build a project and its dependencies for a specific runtime (in this example, Ubuntu 18.04):</span></span>

  ```console
  dotnet build --runtime ubuntu.18.04-x64
  ```

* <span data-ttu-id="1cf27-172">生成项目，并在还原操作过程中使用指定的 NuGet 包源（.NET Core 2.0 SDK 及更高版本）：</span><span class="sxs-lookup"><span data-stu-id="1cf27-172">Build the project and use the specified NuGet package source during the restore operation (.NET Core 2.0 SDK and later versions):</span></span>

  ```console
  dotnet build --source c:\packages\mypackages
  ```

* <span data-ttu-id="1cf27-173">生成项目，并将 1.2.3.4 版本设置为生成参数：</span><span class="sxs-lookup"><span data-stu-id="1cf27-173">Build the project and set 1.2.3.4 version as a build parameter:</span></span>

  ```console
  dotnet build -p:Version=1.2.3.4
  ```
