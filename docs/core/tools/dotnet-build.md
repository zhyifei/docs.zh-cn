---
title: dotnet build 命令
description: dotnet build 命令可生成项目及其所有依赖项。
ms.date: 02/14/2020
ms.openlocfilehash: 27deca4ab1c12314db5214c73660862a8a57a398
ms.sourcegitcommit: 927b7ea6b2ea5a440c8f23e3e66503152eb85591
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2020
ms.locfileid: "81463709"
---
# <a name="dotnet-build"></a><span data-ttu-id="37707-103">dotnet 生成</span><span class="sxs-lookup"><span data-stu-id="37707-103">dotnet build</span></span>

<span data-ttu-id="37707-104">**本文适用于：** ✔️ .NET Core 2.x SDK 及更高版本</span><span class="sxs-lookup"><span data-stu-id="37707-104">**This article applies to:** ✔️ .NET Core 2.x SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="37707-105">名称</span><span class="sxs-lookup"><span data-stu-id="37707-105">Name</span></span>

<span data-ttu-id="37707-106">`dotnet build` - 生成项目及其所有依赖项。</span><span class="sxs-lookup"><span data-stu-id="37707-106">`dotnet build` - Builds a project and all of its dependencies.</span></span>

## <a name="synopsis"></a><span data-ttu-id="37707-107">摘要</span><span class="sxs-lookup"><span data-stu-id="37707-107">Synopsis</span></span>

```dotnetcli
dotnet build [<PROJECT>|<SOLUTION>] [-c|--configuration <CONFIGURATION>]
    [-f|--framework <FRAMEWORK>] [--force] [--interactive] [--no-dependencies]
    [--no-incremental] [--no-restore] [--nologo] [-o|--output <OUTPUT_DIRECTORY>]
    [-r|--runtime <RUNTIME_IDENTIFIER>] [-v|--verbosity <LEVEL>]
    [--version-suffix <VERSION_SUFFIX>]

dotnet build -h|--help
```

## <a name="description"></a><span data-ttu-id="37707-108">说明</span><span class="sxs-lookup"><span data-stu-id="37707-108">Description</span></span>

<span data-ttu-id="37707-109">`dotnet build` 命令将项目及其依赖项生成为一组二进制文件。</span><span class="sxs-lookup"><span data-stu-id="37707-109">The `dotnet build` command builds the project and its dependencies into a set of binaries.</span></span> <span data-ttu-id="37707-110">二进制文件包括扩展名为 .dll 的中间语言 (IL) 文件中的项目代码  。</span><span class="sxs-lookup"><span data-stu-id="37707-110">The binaries include the project's code in Intermediate Language (IL) files with a *.dll* extension.</span></span>  <span data-ttu-id="37707-111">根据项目类型和设置，可能会包含其他文件，例如：</span><span class="sxs-lookup"><span data-stu-id="37707-111">Depending on the project type and settings, other files may be included, such as:</span></span>

- <span data-ttu-id="37707-112">可用于运行应用程序的可执行文件（如果项目类型是面向 .NET Core 3.0 或更高版本的可执行文件）。</span><span class="sxs-lookup"><span data-stu-id="37707-112">An executable that can be used to run the application, if the project type is an executable targeting .NET Core 3.0 or later.</span></span>
- <span data-ttu-id="37707-113">用于调试的扩展名为 .pdb  的符号文件。</span><span class="sxs-lookup"><span data-stu-id="37707-113">Symbol files used for debugging with a *.pdb* extension.</span></span>
- <span data-ttu-id="37707-114">列出了应用程序或库的依赖项的 .deps.json  文件。</span><span class="sxs-lookup"><span data-stu-id="37707-114">A *.deps.json* file, which lists the dependencies of the application or library.</span></span>
- <span data-ttu-id="37707-115">用于指定应用程序的共享运行时及其版本的 .runtimeconfig.json  文件。</span><span class="sxs-lookup"><span data-stu-id="37707-115">A *.runtimeconfig.json* file, which specifies the shared runtime and its version for an application.</span></span>
- <span data-ttu-id="37707-116">项目通过项目引用或 NuGet 包引用所依赖的其他库。</span><span class="sxs-lookup"><span data-stu-id="37707-116">Other libraries that the project depends on (via project references or NuGet package references).</span></span>

<span data-ttu-id="37707-117">对于目标版本低于 .NET Core 3.0 的可执行项目，通常不会将 NuGet 中的库依赖项复制到输出文件夹。</span><span class="sxs-lookup"><span data-stu-id="37707-117">For executable projects targeting versions earlier than .NET Core 3.0, library dependencies from NuGet are typically NOT copied to the output folder.</span></span>  <span data-ttu-id="37707-118">而是在运行时从 NuGet 全局包文件夹中对其进行解析。</span><span class="sxs-lookup"><span data-stu-id="37707-118">They're resolved from the NuGet global packages folder at run time.</span></span> <span data-ttu-id="37707-119">考虑到这一点，`dotnet build` 的产品还未准备好转移到另一台计算机进行运行。</span><span class="sxs-lookup"><span data-stu-id="37707-119">With that in mind, the product of `dotnet build` isn't ready to be transferred to another machine to run.</span></span> <span data-ttu-id="37707-120">要创建可部署的应用程序版本，需要发布该应用程序（例如，使用 [dotnet publish](dotnet-publish.md) 命令）。</span><span class="sxs-lookup"><span data-stu-id="37707-120">To create a version of the application that can be deployed, you need to publish it (for example, with the [dotnet publish](dotnet-publish.md) command).</span></span> <span data-ttu-id="37707-121">有关详细信息，请参阅 [.NET Core 应用程序部署](../deploying/index.md)。</span><span class="sxs-lookup"><span data-stu-id="37707-121">For more information, see [.NET Core Application Deployment](../deploying/index.md).</span></span>

<span data-ttu-id="37707-122">对于面向 .NET Core 3.0 及更高版本的可执行项目，库依赖项会被复制到输出文件夹。</span><span class="sxs-lookup"><span data-stu-id="37707-122">For executable projects targeting .NET Core 3.0 and later, library dependencies are copied to the output folder.</span></span> <span data-ttu-id="37707-123">这意味着如果没有其他任何特定于发布的逻辑（例如，Web 项目具有的逻辑），则应可部署生成输出。</span><span class="sxs-lookup"><span data-stu-id="37707-123">This means that if there isn't any other publish-specific logic (such as Web projects have), the build output should be deployable.</span></span>

<span data-ttu-id="37707-124">构建需要 *project.assets.json* 文件，该文件列出了你的应用程序的依赖项。</span><span class="sxs-lookup"><span data-stu-id="37707-124">Building requires the *project.assets.json* file, which lists the dependencies of your application.</span></span> <span data-ttu-id="37707-125">此文件在 [`dotnet restore`](dotnet-restore.md) 执行时创建。</span><span class="sxs-lookup"><span data-stu-id="37707-125">The file is created when [`dotnet restore`](dotnet-restore.md) is executed.</span></span> <span data-ttu-id="37707-126">如果资产文件未就位，那么工具将无法解析引用程序集，进而导致错误生成。</span><span class="sxs-lookup"><span data-stu-id="37707-126">Without the assets file in place, the tooling can't resolve reference assemblies, which results in errors.</span></span> <span data-ttu-id="37707-127">使用 .NET Core 1.x SDK，需要在运行 `dotnet restore` 之前显式运行 `dotnet build`。</span><span class="sxs-lookup"><span data-stu-id="37707-127">With .NET Core 1.x SDK, you needed to explicitly run `dotnet restore` before running `dotnet build`.</span></span> <span data-ttu-id="37707-128">自 .NET Core 2.0 SDK 起，`dotnet restore` 在 `dotnet build` 运行时隐式运行。</span><span class="sxs-lookup"><span data-stu-id="37707-128">Starting with .NET Core 2.0 SDK, `dotnet restore` runs implicitly when you run `dotnet build`.</span></span> <span data-ttu-id="37707-129">若要在运行 build 命令时禁用隐式还原，可以传递 `--no-restore` 选项。</span><span class="sxs-lookup"><span data-stu-id="37707-129">If you want to disable implicit restore when running the build command, you can pass the `--no-restore` option.</span></span>

[!INCLUDE[dotnet restore note + options](~/includes/dotnet-restore-note-options.md)]

<span data-ttu-id="37707-130">项目是否可执行由项目文件中的 `<OutputType>` 属性决定。</span><span class="sxs-lookup"><span data-stu-id="37707-130">Whether the project is executable or not is determined by the `<OutputType>` property in the project file.</span></span> <span data-ttu-id="37707-131">以下示例显示生成可执行代码的项目：</span><span class="sxs-lookup"><span data-stu-id="37707-131">The following example shows a project that produces executable code:</span></span>

```xml
<PropertyGroup>
  <OutputType>Exe</OutputType>
</PropertyGroup>
```

<span data-ttu-id="37707-132">要生成库，请省略 `<OutputType>` 属性或将其值更改为 `Library`。</span><span class="sxs-lookup"><span data-stu-id="37707-132">To produce a library, omit the `<OutputType>` property or change its value to `Library`.</span></span> <span data-ttu-id="37707-133">库的 IL DLL 不包含入口点，因此无法执行。</span><span class="sxs-lookup"><span data-stu-id="37707-133">The IL DLL for a library doesn't contain entry points and can't be executed.</span></span>

### <a name="msbuild"></a><span data-ttu-id="37707-134">MSBuild</span><span class="sxs-lookup"><span data-stu-id="37707-134">MSBuild</span></span>

<span data-ttu-id="37707-135">`dotnet build` 使用 MSBuild 生成项目，因此它支持并行生成和增量生成。</span><span class="sxs-lookup"><span data-stu-id="37707-135">`dotnet build` uses MSBuild to build the project, so it supports both parallel and incremental builds.</span></span> <span data-ttu-id="37707-136">有关详细信息，请参阅[增量生成](/visualstudio/msbuild/incremental-builds)。</span><span class="sxs-lookup"><span data-stu-id="37707-136">For more information, see [Incremental Builds](/visualstudio/msbuild/incremental-builds).</span></span>

<span data-ttu-id="37707-137">除其自己的选项外，`dotnet build` 命令也接受 MSBuild 选项，如用来设置属性的 `-p` 或用来定义记录器的 `-l`。</span><span class="sxs-lookup"><span data-stu-id="37707-137">In addition to its options, the `dotnet build` command accepts MSBuild options, such as `-p` for setting properties or `-l` to define a logger.</span></span> <span data-ttu-id="37707-138">有关这些选项的详细信息，请参阅 [MSBuild 命令行参考](/visualstudio/msbuild/msbuild-command-line-reference)。</span><span class="sxs-lookup"><span data-stu-id="37707-138">For more information about these options, see the [MSBuild Command-Line Reference](/visualstudio/msbuild/msbuild-command-line-reference).</span></span> <span data-ttu-id="37707-139">或者也可以使用 [dotnet msbuild](dotnet-msbuild.md) 命令。</span><span class="sxs-lookup"><span data-stu-id="37707-139">Or you can also use the [dotnet msbuild](dotnet-msbuild.md) command.</span></span>

<span data-ttu-id="37707-140">运行 `dotnet build` 等同于运行 `dotnet msbuild -restore`；但是，输出的默认详细程度不同。</span><span class="sxs-lookup"><span data-stu-id="37707-140">Running `dotnet build` is equivalent to running `dotnet msbuild -restore`; however, the default verbosity of the output is different.</span></span>

## <a name="arguments"></a><span data-ttu-id="37707-141">参数</span><span class="sxs-lookup"><span data-stu-id="37707-141">Arguments</span></span>

`PROJECT | SOLUTION`

<span data-ttu-id="37707-142">要生成的项目或解决方案文件。</span><span class="sxs-lookup"><span data-stu-id="37707-142">The project or solution file to build.</span></span> <span data-ttu-id="37707-143">如果未指定项目或解决方案文件，MSBuild 会在当前工作目录中搜索文件扩展名以 *proj* 或 *sln* 结尾的文件并使用该文件。</span><span class="sxs-lookup"><span data-stu-id="37707-143">If a project or solution file isn't specified, MSBuild searches the current working directory for a file that has a file extension that ends in either *proj* or *sln* and uses that file.</span></span>

## <a name="options"></a><span data-ttu-id="37707-144">选项</span><span class="sxs-lookup"><span data-stu-id="37707-144">Options</span></span>

- **`-c|--configuration <CONFIGURATION>`**

  <span data-ttu-id="37707-145">定义生成配置。</span><span class="sxs-lookup"><span data-stu-id="37707-145">Defines the build configuration.</span></span> <span data-ttu-id="37707-146">大多数项目的默认配置为 `Debug`，但你可以覆盖项目中的生成配置设置。</span><span class="sxs-lookup"><span data-stu-id="37707-146">The default for most projects is `Debug`, but you can override the build configuration settings in your project.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="37707-147">编译特定[框架](../../standard/frameworks.md)。</span><span class="sxs-lookup"><span data-stu-id="37707-147">Compiles for a specific [framework](../../standard/frameworks.md).</span></span> <span data-ttu-id="37707-148">必须在[项目文件](csproj.md)中定义该框架。</span><span class="sxs-lookup"><span data-stu-id="37707-148">The framework must be defined in the [project file](csproj.md).</span></span>

- **`--force`**

  <span data-ttu-id="37707-149">强制解析所有依赖项，即使上次还原已成功，也不例外。</span><span class="sxs-lookup"><span data-stu-id="37707-149">Forces all dependencies to be resolved even if the last restore was successful.</span></span> <span data-ttu-id="37707-150">指定此标记等同于删除 project.assets.json 文件  。</span><span class="sxs-lookup"><span data-stu-id="37707-150">Specifying this flag is the same as deleting the *project.assets.json* file.</span></span>

- **`-h|--help`**

  <span data-ttu-id="37707-151">打印出有关命令的简短帮助。</span><span class="sxs-lookup"><span data-stu-id="37707-151">Prints out a short help for the command.</span></span>

- **`--interactive`**

  <span data-ttu-id="37707-152">允许命令停止并等待用户输入或操作。</span><span class="sxs-lookup"><span data-stu-id="37707-152">Allows the command to stop and wait for user input or action.</span></span> <span data-ttu-id="37707-153">例如，完成身份验证。</span><span class="sxs-lookup"><span data-stu-id="37707-153">For example, to complete authentication.</span></span> <span data-ttu-id="37707-154">自 .NET Core 3.0 SDK 起可用。</span><span class="sxs-lookup"><span data-stu-id="37707-154">Available since .NET Core 3.0 SDK.</span></span>

- **`--no-dependencies`**

  <span data-ttu-id="37707-155">忽略项目到项目 (P2P) 引用，并仅生成指定的根项目。</span><span class="sxs-lookup"><span data-stu-id="37707-155">Ignores project-to-project (P2P) references and only builds the specified root project.</span></span>

- **`--no-incremental`**

  <span data-ttu-id="37707-156">将生成标记为对增量生成不安全。</span><span class="sxs-lookup"><span data-stu-id="37707-156">Marks the build as unsafe for incremental build.</span></span> <span data-ttu-id="37707-157">此标记关闭增量编译，并强制完全重新生成项目依赖项关系图。</span><span class="sxs-lookup"><span data-stu-id="37707-157">This flag turns off incremental compilation and forces a clean rebuild of the project's dependency graph.</span></span>

- **`--no-restore`**

  <span data-ttu-id="37707-158">在生成期间不执行隐式还原。</span><span class="sxs-lookup"><span data-stu-id="37707-158">Doesn't execute an implicit restore during build.</span></span>

- **`--nologo`**

  <span data-ttu-id="37707-159">不显示启动版权标志或版权消息。</span><span class="sxs-lookup"><span data-stu-id="37707-159">Doesn't display the startup banner or the copyright message.</span></span> <span data-ttu-id="37707-160">自 .NET Core 3.0 SDK 起可用。</span><span class="sxs-lookup"><span data-stu-id="37707-160">Available since .NET Core 3.0 SDK.</span></span>

- **`-o|--output <OUTPUT_DIRECTORY>`**

  <span data-ttu-id="37707-161">放置生成二进制文件的目录。</span><span class="sxs-lookup"><span data-stu-id="37707-161">Directory in which to place the built binaries.</span></span> <span data-ttu-id="37707-162">如果未指定，则默认路径为 `./bin/<configuration>/<framework>/`。</span><span class="sxs-lookup"><span data-stu-id="37707-162">If not specified, the default path is `./bin/<configuration>/<framework>/`.</span></span>  <span data-ttu-id="37707-163">对于具有多个目标框架的项目（通过 `TargetFrameworks` 属性），在指定此选项时还需要定义 `--framework`。</span><span class="sxs-lookup"><span data-stu-id="37707-163">For projects with multiple target frameworks (via the `TargetFrameworks` property), you also need to define `--framework` when you specify this option.</span></span>

- **`-r|--runtime <RUNTIME_IDENTIFIER>`**

  <span data-ttu-id="37707-164">指定目标运行时。</span><span class="sxs-lookup"><span data-stu-id="37707-164">Specifies the target runtime.</span></span> <span data-ttu-id="37707-165">有关运行时标识符 (RID) 的列表，请参阅 [RID 目录](../rid-catalog.md)。</span><span class="sxs-lookup"><span data-stu-id="37707-165">For a list of Runtime Identifiers (RIDs), see the [RID catalog](../rid-catalog.md).</span></span>

- **`-v|--verbosity <LEVEL>`**

  <span data-ttu-id="37707-166">设置 MSBuild 详细级别。</span><span class="sxs-lookup"><span data-stu-id="37707-166">Sets the MSBuild verbosity level.</span></span> <span data-ttu-id="37707-167">允许使用的值为 `q[uiet]`、`m[inimal]`、`n[ormal]`、`d[etailed]` 和 `diag[nostic]`。</span><span class="sxs-lookup"><span data-stu-id="37707-167">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="37707-168">默认值为 `minimal`。</span><span class="sxs-lookup"><span data-stu-id="37707-168">The default is `minimal`.</span></span>

- **`--version-suffix <VERSION_SUFFIX>`**

  <span data-ttu-id="37707-169">设置生成项目时使用的 `$(VersionSuffix)` 属性的值。</span><span class="sxs-lookup"><span data-stu-id="37707-169">Sets the value of the `$(VersionSuffix)` property to use when building the project.</span></span> <span data-ttu-id="37707-170">这仅在未设置 `$(Version)` 属性时有效。</span><span class="sxs-lookup"><span data-stu-id="37707-170">This only works if the `$(Version)` property isn't set.</span></span> <span data-ttu-id="37707-171">然后，`$(Version)` 设置为 `$(VersionPrefix)` 与 `$(VersionSuffix)` 组合，并用短划线分隔。</span><span class="sxs-lookup"><span data-stu-id="37707-171">Then, `$(Version)` is set to the `$(VersionPrefix)` combined with the `$(VersionSuffix)`, separated by a dash.</span></span>

## <a name="examples"></a><span data-ttu-id="37707-172">示例</span><span class="sxs-lookup"><span data-stu-id="37707-172">Examples</span></span>

- <span data-ttu-id="37707-173">生成项目及其依赖项：</span><span class="sxs-lookup"><span data-stu-id="37707-173">Build a project and its dependencies:</span></span>

  ```dotnetcli
  dotnet build
  ```

- <span data-ttu-id="37707-174">使用“发布”配置生成项目及其依赖项：</span><span class="sxs-lookup"><span data-stu-id="37707-174">Build a project and its dependencies using Release configuration:</span></span>

  ```dotnetcli
  dotnet build --configuration Release
  ```

- <span data-ttu-id="37707-175">针对特定运行时（本例中为 Ubuntu 18.04）生成项目及其依赖项：</span><span class="sxs-lookup"><span data-stu-id="37707-175">Build a project and its dependencies for a specific runtime (in this example, Ubuntu 18.04):</span></span>

  ```dotnetcli
  dotnet build --runtime ubuntu.18.04-x64
  ```

- <span data-ttu-id="37707-176">生成项目，并在还原操作过程中使用指定的 NuGet 包源（.NET Core 2.0 SDK 及更高版本）：</span><span class="sxs-lookup"><span data-stu-id="37707-176">Build the project and use the specified NuGet package source during the restore operation (.NET Core 2.0 SDK and later versions):</span></span>

  ```dotnetcli
  dotnet build --source c:\packages\mypackages
  ```

- <span data-ttu-id="37707-177">生成项目并设置版本 1.2.3.4 作为使用 `-p` [MSBuild 选项](#msbuild)的生成参数：</span><span class="sxs-lookup"><span data-stu-id="37707-177">Build the project and set version 1.2.3.4 as a build parameter using the `-p` [MSBuild option](#msbuild):</span></span>

  ```dotnetcli
  dotnet build -p:Version=1.2.3.4
  ```
