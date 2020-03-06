---
title: dotnet publish 命令
description: dotnet publish 命令可将 .NET Core 项目或解决方案发布到目录。
ms.date: 02/24/2020
ms.openlocfilehash: cf41ee09244faad03feb8ccda19135b8c7780106
ms.sourcegitcommit: 00aa62e2f469c2272a457b04e66b4cc3c97a800b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/28/2020
ms.locfileid: "78156993"
---
# <a name="dotnet-publish"></a><span data-ttu-id="7fc14-103">dotnet publish</span><span class="sxs-lookup"><span data-stu-id="7fc14-103">dotnet publish</span></span>

<span data-ttu-id="7fc14-104"> 本文适用于： ✔️ .NET Core 2.1 SDK 及更高版本</span><span class="sxs-lookup"><span data-stu-id="7fc14-104">**This article applies to:** ✔️ .NET Core 2.1 SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="7fc14-105">“属性”</span><span class="sxs-lookup"><span data-stu-id="7fc14-105">Name</span></span>

<span data-ttu-id="7fc14-106">`dotnet publish` - 将应用程序及其依赖项发布到文件夹以部署到托管系统。</span><span class="sxs-lookup"><span data-stu-id="7fc14-106">`dotnet publish` - Publishes the application and its dependencies to a folder for deployment to a hosting system.</span></span>

## <a name="synopsis"></a><span data-ttu-id="7fc14-107">摘要</span><span class="sxs-lookup"><span data-stu-id="7fc14-107">Synopsis</span></span>

```dotnetcli
dotnet publish [<PROJECT>|<SOLUTION>] [-c|--configuration] 
    [-f|--framework] [--force] [--interactive] [--manifest]
    [--no-build] [--no-dependencies] [--no-restore] [--nologo]
    [-o|--output] [-r|--runtime] [--self-contained]
    [--no-self-contained] [-v|--verbosity] [--version-suffix]

dotnet publish [-h|--help]
```

## <a name="description"></a><span data-ttu-id="7fc14-108">描述</span><span class="sxs-lookup"><span data-stu-id="7fc14-108">Description</span></span>

<span data-ttu-id="7fc14-109">`dotnet publish` 编译应用程序、读取 project 文件中指定的所有依赖项并将生成的文件集发布到目录。</span><span class="sxs-lookup"><span data-stu-id="7fc14-109">`dotnet publish` compiles the application, reads through its dependencies specified in the project file, and publishes the resulting set of files to a directory.</span></span> <span data-ttu-id="7fc14-110">输出包括以下资产：</span><span class="sxs-lookup"><span data-stu-id="7fc14-110">The output includes the following assets:</span></span>

- <span data-ttu-id="7fc14-111">扩展名为 dll  的程序集中的中间语言 (IL) 代码。</span><span class="sxs-lookup"><span data-stu-id="7fc14-111">Intermediate Language (IL) code in an assembly with a *dll* extension.</span></span>
- <span data-ttu-id="7fc14-112">包含项目所有依赖项的 .deps.json 文件  。</span><span class="sxs-lookup"><span data-stu-id="7fc14-112">A *.deps.json* file that includes all of the dependencies of the project.</span></span>
- <span data-ttu-id="7fc14-113">.runtimeconfig.json 文件，其中指定了应用程序所需的共享运行时，以及运行时的其他配置选项（例如垃圾回收类型）  。</span><span class="sxs-lookup"><span data-stu-id="7fc14-113">A *.runtimeconfig.json* file that specifies the shared runtime that the application expects, as well as other configuration options for the runtime (for example, garbage collection type).</span></span>
- <span data-ttu-id="7fc14-114">应用程序的依赖项，将这些依赖项从 NuGet 缓存复制到输出文件夹。</span><span class="sxs-lookup"><span data-stu-id="7fc14-114">The application's dependencies, which are copied from the NuGet cache into the output folder.</span></span>

<span data-ttu-id="7fc14-115">`dotnet publish` 命令的输出可供部署至托管系统（例如服务器、电脑、Mac、笔记本电脑）以便执行。</span><span class="sxs-lookup"><span data-stu-id="7fc14-115">The `dotnet publish` command's output is ready for deployment to a hosting system (for example, a server, PC, Mac, laptop) for execution.</span></span> <span data-ttu-id="7fc14-116">若要准备用于部署的应用程序，这是唯一正式受支持的方法。</span><span class="sxs-lookup"><span data-stu-id="7fc14-116">It's the only officially supported way to prepare the application for deployment.</span></span> <span data-ttu-id="7fc14-117">根据项目指定的部署的类型，托管系统不一定已在其上安装 .NET Core 共享运行时。</span><span class="sxs-lookup"><span data-stu-id="7fc14-117">Depending on the type of deployment that the project specifies, the hosting system may or may not have the .NET Core shared runtime installed on it.</span></span>

## <a name="arguments"></a><span data-ttu-id="7fc14-118">自变量</span><span class="sxs-lookup"><span data-stu-id="7fc14-118">Arguments</span></span>

- **`PROJECT|SOLUTION`**

  <span data-ttu-id="7fc14-119">要发布的项目或解决方案。</span><span class="sxs-lookup"><span data-stu-id="7fc14-119">The project or solution to publish.</span></span>
  
  * <span data-ttu-id="7fc14-120">`PROJECT` 是 [C#](csproj.md)、F# 或 Visual Basic 项目文件的路径和文件名，或包含 C#、F# 或 Visual Basic 项目文件的目录的路径。</span><span class="sxs-lookup"><span data-stu-id="7fc14-120">`PROJECT` is the path and filename of a [C#](csproj.md), F#, or Visual Basic project file, or the path to a directory that contains a C#, F#, or Visual Basic project file.</span></span> <span data-ttu-id="7fc14-121">如果未指定目录，则默认为当前目录。</span><span class="sxs-lookup"><span data-stu-id="7fc14-121">If the directory is not specified, it defaults to the current directory.</span></span>

  * <span data-ttu-id="7fc14-122">`SOLUTION` 是解决方案文件（扩展名为 .sln）的路径和文件名，或包含解决方案文件的目录的路径  。</span><span class="sxs-lookup"><span data-stu-id="7fc14-122">`SOLUTION` is the path and filename of a solution file (*.sln* extension), or the path to a directory that contains a solution file.</span></span> <span data-ttu-id="7fc14-123">如果未指定目录，则默认为当前目录。</span><span class="sxs-lookup"><span data-stu-id="7fc14-123">If the directory is not specified, it defaults to the current directory.</span></span> <span data-ttu-id="7fc14-124">**自 .NET Core 3.0 SDK 起可用。**</span><span class="sxs-lookup"><span data-stu-id="7fc14-124">**Available starting with .NET Core 3.0 SDK.**</span></span> 

## <a name="options"></a><span data-ttu-id="7fc14-125">选项</span><span class="sxs-lookup"><span data-stu-id="7fc14-125">Options</span></span>

- **`-c|--configuration <CONFIGURATION>`**

  <span data-ttu-id="7fc14-126">定义生成配置。</span><span class="sxs-lookup"><span data-stu-id="7fc14-126">Defines the build configuration.</span></span> <span data-ttu-id="7fc14-127">大多数项目的默认配置为 `Debug`，但你可以覆盖项目中的生成配置设置。</span><span class="sxs-lookup"><span data-stu-id="7fc14-127">The default for most projects is `Debug`, but you can override the build configuration settings in your project.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="7fc14-128">为指定的[目标框架](../../standard/frameworks.md)发布应用程序。</span><span class="sxs-lookup"><span data-stu-id="7fc14-128">Publishes the application for the specified [target framework](../../standard/frameworks.md).</span></span> <span data-ttu-id="7fc14-129">必须在项目文件中指定目标框架。</span><span class="sxs-lookup"><span data-stu-id="7fc14-129">You must specify the target framework in the project file.</span></span>

- **`--force`**

  <span data-ttu-id="7fc14-130">强制解析所有依赖项，即使上次还原已成功，也不例外。</span><span class="sxs-lookup"><span data-stu-id="7fc14-130">Forces all dependencies to be resolved even if the last restore was successful.</span></span> <span data-ttu-id="7fc14-131">指定此标记等同于删除 project.assets.json 文件  。</span><span class="sxs-lookup"><span data-stu-id="7fc14-131">Specifying this flag is the same as deleting the *project.assets.json* file.</span></span>

- **`-h|--help`**

  <span data-ttu-id="7fc14-132">打印出有关命令的简短帮助。</span><span class="sxs-lookup"><span data-stu-id="7fc14-132">Prints out a short help for the command.</span></span>

- <span data-ttu-id="7fc14-133">**`--interactive`** **自 .NET Core 3.0 SDK 起可用。**</span><span class="sxs-lookup"><span data-stu-id="7fc14-133">**`--interactive`** **Available starting with .NET Core 3.0 SDK.**</span></span>

  <span data-ttu-id="7fc14-134">允许命令停止并等待用户输入或操作。</span><span class="sxs-lookup"><span data-stu-id="7fc14-134">Allows the command to stop and wait for user input or action.</span></span> <span data-ttu-id="7fc14-135">例如，完成身份验证。</span><span class="sxs-lookup"><span data-stu-id="7fc14-135">For example, to complete authentication.</span></span> 

- **`--manifest <PATH_TO_MANIFEST_FILE>`**

  <span data-ttu-id="7fc14-136">指定一个或多个[目标清单](../deploying/runtime-store.md)，用于剪裁与应用程序一同发布的一组包。</span><span class="sxs-lookup"><span data-stu-id="7fc14-136">Specifies one or several [target manifests](../deploying/runtime-store.md) to use to trim the set of packages published with the app.</span></span> <span data-ttu-id="7fc14-137">清单文件是 [`dotnet store` 命令](dotnet-store.md)输出的一部分。</span><span class="sxs-lookup"><span data-stu-id="7fc14-137">The manifest file is part of the output of the [`dotnet store` command](dotnet-store.md).</span></span> <span data-ttu-id="7fc14-138">若要指定多个清单，请为每个清单添加一个 `--manifest` 选项。</span><span class="sxs-lookup"><span data-stu-id="7fc14-138">To specify multiple manifests, add a `--manifest` option for each manifest.</span></span>

- **`--no-build`**

  <span data-ttu-id="7fc14-139">发布前不生成项目。</span><span class="sxs-lookup"><span data-stu-id="7fc14-139">Doesn't build the project before publishing.</span></span> <span data-ttu-id="7fc14-140">还将隐式设置 `--no-restore` 标记。</span><span class="sxs-lookup"><span data-stu-id="7fc14-140">It also implicitly sets the `--no-restore` flag.</span></span>

- **`--no-dependencies`**

  <span data-ttu-id="7fc14-141">忽略项目间引用，仅还原根项目。</span><span class="sxs-lookup"><span data-stu-id="7fc14-141">Ignores project-to-project references and only restores the root project.</span></span>

- <span data-ttu-id="7fc14-142">**`--nologo`** **自 .NET Core 3.0 SDK 起可用。**</span><span class="sxs-lookup"><span data-stu-id="7fc14-142">**`--nologo`** **Available starting with .NET Core 3.0 SDK.**</span></span>

  <span data-ttu-id="7fc14-143">不显示启动版权标志或版权消息。</span><span class="sxs-lookup"><span data-stu-id="7fc14-143">Doesn't display the startup banner or the copyright message.</span></span> 

- **`--no-restore`**

  <span data-ttu-id="7fc14-144">运行此命令时不执行隐式还原。</span><span class="sxs-lookup"><span data-stu-id="7fc14-144">Doesn't execute an implicit restore when running the command.</span></span>

- **`-o|--output <OUTPUT_DIRECTORY>`**

  <span data-ttu-id="7fc14-145">指定输出目录的路径。</span><span class="sxs-lookup"><span data-stu-id="7fc14-145">Specifies the path for the output directory.</span></span> <span data-ttu-id="7fc14-146">如果未指定，则默认为依赖于运行时的可执行文件和跨平台二进制文件的路径 /bin/[configuration]/[framework]/publish/  。</span><span class="sxs-lookup"><span data-stu-id="7fc14-146">If not specified, it defaults to *./bin/[configuration]/[framework]/publish/* for a runtime-dependent executable and cross-platform binaries.</span></span> <span data-ttu-id="7fc14-147">默认为独立的可执行文件路径 /bin/[configuration]/[framework]/[runtime]/publish/  。</span><span class="sxs-lookup"><span data-stu-id="7fc14-147">It defaults to *./bin/[configuration]/[framework]/[runtime]/publish/* for a self-contained executable.</span></span>

  <span data-ttu-id="7fc14-148">如果路径是相对的，则生成的输出目录与项目文件位置相关，而与当前工作目录不相关。</span><span class="sxs-lookup"><span data-stu-id="7fc14-148">If the path is relative, the output directory generated is relative to the project file location, not to the current working directory.</span></span>

- **`--self-contained [true|false]`**

  <span data-ttu-id="7fc14-149">与应用程序一同发布 .NET Core 运行时，因此无需在目标计算机上安装运行时。</span><span class="sxs-lookup"><span data-stu-id="7fc14-149">Publishes the .NET Core runtime with your application so the runtime doesn't need to be installed on the target machine.</span></span> <span data-ttu-id="7fc14-150">如果指定了运行时标识符，默认值为 `true`。</span><span class="sxs-lookup"><span data-stu-id="7fc14-150">Default is `true` if a runtime identifier is specified.</span></span> <span data-ttu-id="7fc14-151">有关详细信息，请参阅 [.NET Core 应用程序发布](../deploying/index.md)和[使用 .NET Core CLI 发布 .NET Core 应用](../deploying/deploy-with-cli.md)。</span><span class="sxs-lookup"><span data-stu-id="7fc14-151">For more information, see [.NET Core application publishing](../deploying/index.md) and [Publish .NET Core apps with the .NET Core CLI](../deploying/deploy-with-cli.md).</span></span>

- <span data-ttu-id="7fc14-152">**`--no-self-contained`**  **自 .NET Core 3.0 SDK 起可用。**</span><span class="sxs-lookup"><span data-stu-id="7fc14-152">**`--no-self-contained`**  **Available starting with .NET Core 3.0 SDK.**</span></span>

  <span data-ttu-id="7fc14-153">等效于 `--self-contained false`。</span><span class="sxs-lookup"><span data-stu-id="7fc14-153">Equivalent to `--self-contained false`.</span></span>

- **`-r|--runtime <RUNTIME_IDENTIFIER>`**

  <span data-ttu-id="7fc14-154">发布针对给定运行时的应用程序。</span><span class="sxs-lookup"><span data-stu-id="7fc14-154">Publishes the application for a given runtime.</span></span> <span data-ttu-id="7fc14-155">有关运行时标识符 (RID) 的列表，请参阅 [RID 目录](../rid-catalog.md)。</span><span class="sxs-lookup"><span data-stu-id="7fc14-155">For a list of Runtime Identifiers (RIDs), see the [RID catalog](../rid-catalog.md).</span></span> <span data-ttu-id="7fc14-156">有关详细信息，请参阅 [.NET Core 应用程序发布](../deploying/index.md)和[使用 .NET Core CLI 发布 .NET Core 应用](../deploying/deploy-with-cli.md)。</span><span class="sxs-lookup"><span data-stu-id="7fc14-156">For more information, see [.NET Core application publishing](../deploying/index.md) and [Publish .NET Core apps with the .NET Core CLI](../deploying/deploy-with-cli.md).</span></span>

- **`-v|--verbosity <LEVEL>`**

  <span data-ttu-id="7fc14-157">设置命令的详细级别。</span><span class="sxs-lookup"><span data-stu-id="7fc14-157">Sets the verbosity level of the command.</span></span> <span data-ttu-id="7fc14-158">允许使用的值为 `q[uiet]`、`m[inimal]`、`n[ormal]`、`d[etailed]` 和 `diag[nostic]`。</span><span class="sxs-lookup"><span data-stu-id="7fc14-158">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

- **`--version-suffix <VERSION_SUFFIX>`**

  <span data-ttu-id="7fc14-159">定义版本后缀来替换项目文件的版本字段中的星号 (`*`)。</span><span class="sxs-lookup"><span data-stu-id="7fc14-159">Defines the version suffix to replace the asterisk (`*`) in the version field of the project file.</span></span>

## <a name="examples"></a><span data-ttu-id="7fc14-160">示例</span><span class="sxs-lookup"><span data-stu-id="7fc14-160">Examples</span></span>

- <span data-ttu-id="7fc14-161">为当前目录中的项目创建一个 [依赖于运行时的跨平台二进制文件](../deploying/index.md#produce-a-cross-platform-binary)：</span><span class="sxs-lookup"><span data-stu-id="7fc14-161">Create a [runtime-dependent cross-platform binary](../deploying/index.md#produce-a-cross-platform-binary) for the project in the current directory:</span></span>

  ```dotnetcli
  dotnet publish
  ```

  <span data-ttu-id="7fc14-162">自 .NET Core 3.0 SDK 起，此示例还为当前平台创建[依赖于运行时的可执行文件](../deploying/index.md#publish-runtime-dependent)。</span><span class="sxs-lookup"><span data-stu-id="7fc14-162">Starting with .NET Core 3.0 SDK, this example also creates a [runtime-dependent executable](../deploying/index.md#publish-runtime-dependent) for the current platform.</span></span>

- <span data-ttu-id="7fc14-163">针对特定运行时，为当前目录中的项目创建[独立可执行文件](../deploying/index.md#publish-self-contained)：</span><span class="sxs-lookup"><span data-stu-id="7fc14-163">Create a [self-contained executable](../deploying/index.md#publish-self-contained) for the project in the current directory, for a specific runtime:</span></span>

  ```dotnetcli
  dotnet publish --runtime osx.10.11-x64
  ```

  <span data-ttu-id="7fc14-164">项目文件中必须包含 RID。</span><span class="sxs-lookup"><span data-stu-id="7fc14-164">The RID must be in the project file.</span></span>

- <span data-ttu-id="7fc14-165">针对特定平台，为当前目录中的项目创建[依赖于运行时的可执行文件](../deploying/index.md#publish-runtime-dependent)：</span><span class="sxs-lookup"><span data-stu-id="7fc14-165">Create a [runtime-dependent executable](../deploying/index.md#publish-runtime-dependent) for the project in the current directory, for a specific platform:</span></span>

  ```dotnetcli
  dotnet publish --runtime osx.10.11-x64 --self-contained false
  ```

  <span data-ttu-id="7fc14-166">项目文件中必须包含 RID。</span><span class="sxs-lookup"><span data-stu-id="7fc14-166">The RID must be in the project file.</span></span> <span data-ttu-id="7fc14-167">此示例适用于 .NET Core 3.0 SDK 及更高版本。</span><span class="sxs-lookup"><span data-stu-id="7fc14-167">This example applies to .NET Core 3.0 SDK and later versions.</span></span>

- <span data-ttu-id="7fc14-168">针对特定运行时和目标框架，在当前目录中发布项目：</span><span class="sxs-lookup"><span data-stu-id="7fc14-168">Publish the project in the current directory, for a specific runtime and target framework:</span></span>

  ```dotnetcli
  dotnet publish --framework netcoreapp3.1 --runtime osx.10.11-x64
  ```

- <span data-ttu-id="7fc14-169">发布指定的项目文件：</span><span class="sxs-lookup"><span data-stu-id="7fc14-169">Publish the specified project file:</span></span>

  ```dotnetcli
  dotnet publish ~/projects/app1/app1.csproj
  ```

- <span data-ttu-id="7fc14-170">发布当前应用程序，但在还原操作期间不还原项目到项目 (P2P) 引用，只还原根项目：</span><span class="sxs-lookup"><span data-stu-id="7fc14-170">Publish the current application but don't restore project-to-project (P2P) references, just the root project during the restore operation:</span></span>

  ```dotnetcli
  dotnet publish --no-dependencies
  ```

## <a name="see-also"></a><span data-ttu-id="7fc14-171">请参阅</span><span class="sxs-lookup"><span data-stu-id="7fc14-171">See also</span></span>

- [<span data-ttu-id="7fc14-172">.NET Core 应用程序发布概述</span><span class="sxs-lookup"><span data-stu-id="7fc14-172">.NET Core application publishing overview</span></span>](../deploying/index.md)
- [<span data-ttu-id="7fc14-173">使用 .NET Core CLI 发布 .NET Core 应用</span><span class="sxs-lookup"><span data-stu-id="7fc14-173">Publish .NET Core apps with the .NET Core CLI</span></span>](../deploying/deploy-with-cli.md)
- [<span data-ttu-id="7fc14-174">目标框架</span><span class="sxs-lookup"><span data-stu-id="7fc14-174">Target frameworks</span></span>](../../standard/frameworks.md)
- [<span data-ttu-id="7fc14-175">运行时标识符 (RID) 目录</span><span class="sxs-lookup"><span data-stu-id="7fc14-175">Runtime IDentifier (RID) catalog</span></span>](../rid-catalog.md)
- <span data-ttu-id="7fc14-176">[处理 macOS Catalina 公证](../install/macos-notarization-issues.md) 有关详细信息，请参阅下面的资源：</span><span class="sxs-lookup"><span data-stu-id="7fc14-176">[Working with macOS Catalina Notarization](../install/macos-notarization-issues.md) For more information, see he following resources:</span></span>
- [<span data-ttu-id="7fc14-177">已发布应用程序的目录结构</span><span class="sxs-lookup"><span data-stu-id="7fc14-177">Directory structure of a published application</span></span>](/aspnet/core/hosting/directory-structure)
