---
title: dotnet publish 命令 - .NET Core CLI
description: dotnet publish 命令可将 .NET Core 项目发布到目录。
author: mairaw
ms.author: mairaw
ms.date: 05/29/2018
ms.openlocfilehash: 38224aa8472f99df107e523667e18892384a20b0
ms.sourcegitcommit: f6343b070f3c66877338a05c8bfb0be9985255e2
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/24/2018
ms.locfileid: "39220667"
---
# <a name="dotnet-publish"></a><span data-ttu-id="21432-103">dotnet 发布</span><span class="sxs-lookup"><span data-stu-id="21432-103">dotnet publish</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="21432-104">name</span><span class="sxs-lookup"><span data-stu-id="21432-104">Name</span></span>

<span data-ttu-id="21432-105">`dotnet publish` - 将应用程序及其依赖项打包到文件夹以部署到托管系统。</span><span class="sxs-lookup"><span data-stu-id="21432-105">`dotnet publish` - Packs the application and its dependencies into a folder for deployment to a hosting system.</span></span>

## <a name="synopsis"></a><span data-ttu-id="21432-106">摘要</span><span class="sxs-lookup"><span data-stu-id="21432-106">Synopsis</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="21432-107">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="21432-107">.NET Core 2.1</span></span>](#tab/netcore21)
```
dotnet publish [<PROJECT>] [-c|--configuration] [-f|--framework] [--force] [--manifest] [--no-build] [--no-dependencies]
    [--no-restore] [-o|--output] [-r|--runtime] [--self-contained] [-v|--verbosity] [--version-suffix]
dotnet publish [-h|--help]
```
# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="21432-108">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="21432-108">.NET Core 2.0</span></span>](#tab/netcore20)
```
dotnet publish [<PROJECT>] [-c|--configuration] [-f|--framework] [--force] [--manifest] [--no-dependencies]
    [--no-restore] [-o|--output] [-r|--runtime] [--self-contained] [-v|--verbosity] [--version-suffix]
dotnet publish [-h|--help]
```
# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="21432-109">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="21432-109">.NET Core 1.x</span></span>](#tab/netcore1x)
```
dotnet publish [<PROJECT>] [-c|--configuration] [-f|--framework] [-o|--output] [-r|--runtime] [-v|--verbosity]
    [--version-suffix]
dotnet publish [-h|--help]
```
---

## <a name="description"></a><span data-ttu-id="21432-110">描述</span><span class="sxs-lookup"><span data-stu-id="21432-110">Description</span></span>

<span data-ttu-id="21432-111">`dotnet publish` 编译应用程序、读取 project 文件中指定的所有依赖项并将生成的文件集发布到目录。</span><span class="sxs-lookup"><span data-stu-id="21432-111">`dotnet publish` compiles the application, reads through its dependencies specified in the project file, and publishes the resulting set of files to a directory.</span></span> <span data-ttu-id="21432-112">输出包括以下资产：</span><span class="sxs-lookup"><span data-stu-id="21432-112">The output includes the following assets:</span></span>

* <span data-ttu-id="21432-113">扩展名为 dll 的程序集中的中间语言 (IL) 代码。</span><span class="sxs-lookup"><span data-stu-id="21432-113">Intermediate Language (IL) code in an assembly with a *dll* extension.</span></span>
* <span data-ttu-id="21432-114">包含项目所有依赖项的 .deps.json 文件。</span><span class="sxs-lookup"><span data-stu-id="21432-114">*.deps.json* file that includes all of the dependencies of the project.</span></span>
* <span data-ttu-id="21432-115">.runtime.config.json 文件，其中指定了应用程序所需的共享运行时，以及运行时的其他配置选项（例如，垃圾回收类型）。</span><span class="sxs-lookup"><span data-stu-id="21432-115">*.runtime.config.json* file that specifies the shared runtime that the application expects, as well as other configuration options for the runtime (for example, garbage collection type).</span></span>
* <span data-ttu-id="21432-116">应用程序的依赖项，将这些依赖项从 NuGet 缓存复制到输出文件夹。</span><span class="sxs-lookup"><span data-stu-id="21432-116">The application's dependencies, which are copied from the NuGet cache into the output folder.</span></span>

<span data-ttu-id="21432-117">`dotnet publish` 命令的输出可供部署至托管系统（例如服务器、电脑、Mac、笔记本电脑）以便执行。</span><span class="sxs-lookup"><span data-stu-id="21432-117">The `dotnet publish` command's output is ready for deployment to a hosting system (for example, a server, PC, Mac, laptop) for execution.</span></span> <span data-ttu-id="21432-118">若要准备用于部署的应用程序，这是唯一正式受支持的方法。</span><span class="sxs-lookup"><span data-stu-id="21432-118">It's the only officially supported way to prepare the application for deployment.</span></span> <span data-ttu-id="21432-119">根据项目指定的部署的类型，托管系统不一定已在其上安装 .NET Core 共享运行时。</span><span class="sxs-lookup"><span data-stu-id="21432-119">Depending on the type of deployment that the project specifies, the hosting system may or may not have the .NET Core shared runtime installed on it.</span></span> <span data-ttu-id="21432-120">有关详细信息，请参阅 [.NET Core 应用程序部署](../deploying/index.md)。</span><span class="sxs-lookup"><span data-stu-id="21432-120">For more information, see [.NET Core Application Deployment](../deploying/index.md).</span></span> <span data-ttu-id="21432-121">有关已发布应用程序的目录结构，请参阅[目录结构](/aspnet/core/hosting/directory-structure)。</span><span class="sxs-lookup"><span data-stu-id="21432-121">For the directory structure of a published application, see [Directory structure](/aspnet/core/hosting/directory-structure).</span></span>

[!INCLUDE[dotnet restore note + options](~/includes/dotnet-restore-note-options.md)]

## <a name="arguments"></a><span data-ttu-id="21432-122">参数</span><span class="sxs-lookup"><span data-stu-id="21432-122">Arguments</span></span>

`PROJECT`

<span data-ttu-id="21432-123">要发布的项目。</span><span class="sxs-lookup"><span data-stu-id="21432-123">The project to publish.</span></span> <span data-ttu-id="21432-124">如果未指定，则默认为当前目录。</span><span class="sxs-lookup"><span data-stu-id="21432-124">If not specified, it defaults to the current directory.</span></span>

## <a name="options"></a><span data-ttu-id="21432-125">选项</span><span class="sxs-lookup"><span data-stu-id="21432-125">Options</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="21432-126">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="21432-126">.NET Core 2.1</span></span>](#tab/netcore21)

`-c|--configuration {Debug|Release}`

<span data-ttu-id="21432-127">定义生成配置。</span><span class="sxs-lookup"><span data-stu-id="21432-127">Defines the build configuration.</span></span> <span data-ttu-id="21432-128">默认值为 `Debug`。</span><span class="sxs-lookup"><span data-stu-id="21432-128">The default value is `Debug`.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="21432-129">为指定的[目标框架](../../standard/frameworks.md)发布应用程序。</span><span class="sxs-lookup"><span data-stu-id="21432-129">Publishes the application for the specified [target framework](../../standard/frameworks.md).</span></span> <span data-ttu-id="21432-130">必须在项目文件中指定目标框架。</span><span class="sxs-lookup"><span data-stu-id="21432-130">You must specify the target framework in the project file.</span></span>

`--force`

<span data-ttu-id="21432-131">强制解析所有依赖项，即使上次还原已成功，也不例外。</span><span class="sxs-lookup"><span data-stu-id="21432-131">Forces all dependencies to be resolved even if the last restore was successful.</span></span> <span data-ttu-id="21432-132">指定此标记等同于删除 project.assets.json 文件。</span><span class="sxs-lookup"><span data-stu-id="21432-132">Specifying this flag is the same as deleting the *project.assets.json* file.</span></span>

`-h|--help`

<span data-ttu-id="21432-133">打印出有关命令的简短帮助。</span><span class="sxs-lookup"><span data-stu-id="21432-133">Prints out a short help for the command.</span></span>

`--manifest <PATH_TO_MANIFEST_FILE>`

<span data-ttu-id="21432-134">指定一个或多个[目标清单](../deploying/runtime-store.md)，用于剪裁与应用程序一同发布的一组包。</span><span class="sxs-lookup"><span data-stu-id="21432-134">Specifies one or several [target manifests](../deploying/runtime-store.md) to use to trim the set of packages published with the app.</span></span> <span data-ttu-id="21432-135">清单文件是 [`dotnet store` 命令](dotnet-store.md)输出的一部分。</span><span class="sxs-lookup"><span data-stu-id="21432-135">The manifest file is part of the output of the [`dotnet store` command](dotnet-store.md).</span></span> <span data-ttu-id="21432-136">若要指定多个清单，请为每个清单添加一个 `--manifest` 选项。</span><span class="sxs-lookup"><span data-stu-id="21432-136">To specify multiple manifests, add a `--manifest` option for each manifest.</span></span> <span data-ttu-id="21432-137">自 .NET Core 2.0 SDK 起，可以使用此选项。</span><span class="sxs-lookup"><span data-stu-id="21432-137">This option is available starting with .NET Core 2.0 SDK.</span></span>

`--no-build`

<span data-ttu-id="21432-138">发布前不生成项目。</span><span class="sxs-lookup"><span data-stu-id="21432-138">Doesn't build the project before publishing.</span></span> <span data-ttu-id="21432-139">还隐式设置 `--no-restore` 标记。</span><span class="sxs-lookup"><span data-stu-id="21432-139">It also implicit sets the `--no-restore` flag.</span></span>

`--no-dependencies`

<span data-ttu-id="21432-140">忽略项目间引用，仅还原根项目。</span><span class="sxs-lookup"><span data-stu-id="21432-140">Ignores project-to-project references and only restores the root project.</span></span>

`--no-restore`

<span data-ttu-id="21432-141">运行此命令时不执行隐式还原。</span><span class="sxs-lookup"><span data-stu-id="21432-141">Doesn't execute an implicit restore when running the command.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="21432-142">指定输出目录的路径。</span><span class="sxs-lookup"><span data-stu-id="21432-142">Specifies the path for the output directory.</span></span> <span data-ttu-id="21432-143">如未指定，对于依赖于框架的部署，将默认为 ./bin/[configuration]/[framework]/publish/ 或对于独立部署，将默认为 ./bin/[configuration]/[framework]/[runtime]/publish/。</span><span class="sxs-lookup"><span data-stu-id="21432-143">If not specified, it defaults to *./bin/[configuration]/[framework]/publish/* for a framework-dependent deployment or *./bin/[configuration]/[framework]/[runtime]/publish/* for a self-contained deployment.</span></span>
<span data-ttu-id="21432-144">如果路径是相对的，则生成的输出目录与项目文件位置相关，而与当前工作目录不相关。</span><span class="sxs-lookup"><span data-stu-id="21432-144">If the path is relative, the output directory generated is relative to the project file location, not to the current working directory.</span></span>

`--self-contained`

<span data-ttu-id="21432-145">与应用程序一同发布 .NET Core 运行时，因此无需在目标计算机上安装运行时。</span><span class="sxs-lookup"><span data-stu-id="21432-145">Publishes the .NET Core runtime with your application so the runtime doesn't need to be installed on the target machine.</span></span> <span data-ttu-id="21432-146">如果指定了运行时标识符，默认值为 `true`。</span><span class="sxs-lookup"><span data-stu-id="21432-146">If a runtime identifier is specified, its default value is `true`.</span></span> <span data-ttu-id="21432-147">若要详细了解不同的部署类型，请参阅 [.NET Core 应用程序部署](../deploying/index.md)。</span><span class="sxs-lookup"><span data-stu-id="21432-147">For more information about the different deployment types, see [.NET Core application deployment](../deploying/index.md).</span></span>

`-r|--runtime <RUNTIME_IDENTIFIER>`

<span data-ttu-id="21432-148">发布针对给定运行时的应用程序。</span><span class="sxs-lookup"><span data-stu-id="21432-148">Publishes the application for a given runtime.</span></span> <span data-ttu-id="21432-149">这将在创建[独立部署 (SCD)](../deploying/index.md#self-contained-deployments-scd) 时使用。</span><span class="sxs-lookup"><span data-stu-id="21432-149">This is used when creating a [self-contained deployment (SCD)](../deploying/index.md#self-contained-deployments-scd).</span></span> <span data-ttu-id="21432-150">有关运行时标识符 (RID) 的列表，请参阅 [RID 目录](../rid-catalog.md)。</span><span class="sxs-lookup"><span data-stu-id="21432-150">For a list of Runtime Identifiers (RIDs), see the [RID catalog](../rid-catalog.md).</span></span> <span data-ttu-id="21432-151">默认为发布[依赖于框架的部署 (FDD)](../deploying/index.md#framework-dependent-deployments-fdd)。</span><span class="sxs-lookup"><span data-stu-id="21432-151">Default is to publish a [framework-dependent deployment (FDD)](../deploying/index.md#framework-dependent-deployments-fdd).</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="21432-152">设置命令的详细级别。</span><span class="sxs-lookup"><span data-stu-id="21432-152">Sets the verbosity level of the command.</span></span> <span data-ttu-id="21432-153">允许使用的值为 `q[uiet]`、`m[inimal]`、`n[ormal]`、`d[etailed]` 和 `diag[nostic]`。</span><span class="sxs-lookup"><span data-stu-id="21432-153">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

`--version-suffix <VERSION_SUFFIX>`

<span data-ttu-id="21432-154">定义版本后缀来替换项目文件的版本字段中的星号 (`*`)。</span><span class="sxs-lookup"><span data-stu-id="21432-154">Defines the version suffix to replace the asterisk (`*`) in the version field of the project file.</span></span>

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="21432-155">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="21432-155">.NET Core 2.0</span></span>](#tab/netcore20)

`-c|--configuration {Debug|Release}`

<span data-ttu-id="21432-156">定义生成配置。</span><span class="sxs-lookup"><span data-stu-id="21432-156">Defines the build configuration.</span></span> <span data-ttu-id="21432-157">默认值为 `Debug`。</span><span class="sxs-lookup"><span data-stu-id="21432-157">The default value is `Debug`.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="21432-158">为指定的[目标框架](../../standard/frameworks.md)发布应用程序。</span><span class="sxs-lookup"><span data-stu-id="21432-158">Publishes the application for the specified [target framework](../../standard/frameworks.md).</span></span> <span data-ttu-id="21432-159">必须在项目文件中指定目标框架。</span><span class="sxs-lookup"><span data-stu-id="21432-159">You must specify the target framework in the project file.</span></span>

`--force`

<span data-ttu-id="21432-160">强制解析所有依赖项，即使上次还原已成功，也不例外。</span><span class="sxs-lookup"><span data-stu-id="21432-160">Forces all dependencies to be resolved even if the last restore was successful.</span></span> <span data-ttu-id="21432-161">指定此标记等同于删除 project.assets.json 文件。</span><span class="sxs-lookup"><span data-stu-id="21432-161">Specifying this flag is the same as deleting the *project.assets.json* file.</span></span>

`-h|--help`

<span data-ttu-id="21432-162">打印出有关命令的简短帮助。</span><span class="sxs-lookup"><span data-stu-id="21432-162">Prints out a short help for the command.</span></span>

`--manifest <PATH_TO_MANIFEST_FILE>`

<span data-ttu-id="21432-163">指定一个或多个[目标清单](../deploying/runtime-store.md)，用于剪裁与应用程序一同发布的一组包。</span><span class="sxs-lookup"><span data-stu-id="21432-163">Specifies one or several [target manifests](../deploying/runtime-store.md) to use to trim the set of packages published with the app.</span></span> <span data-ttu-id="21432-164">清单文件是 [`dotnet store` 命令](dotnet-store.md)输出的一部分。</span><span class="sxs-lookup"><span data-stu-id="21432-164">The manifest file is part of the output of the [`dotnet store` command](dotnet-store.md).</span></span> <span data-ttu-id="21432-165">若要指定多个清单，请为每个清单添加一个 `--manifest` 选项。</span><span class="sxs-lookup"><span data-stu-id="21432-165">To specify multiple manifests, add a `--manifest` option for each manifest.</span></span> <span data-ttu-id="21432-166">自 .NET Core 2.0 SDK 起，可以使用此选项。</span><span class="sxs-lookup"><span data-stu-id="21432-166">This option is available starting with .NET Core 2.0 SDK.</span></span>

`--no-dependencies`

<span data-ttu-id="21432-167">忽略项目间引用，仅还原根项目。</span><span class="sxs-lookup"><span data-stu-id="21432-167">Ignores project-to-project references and only restores the root project.</span></span>

`--no-restore`

<span data-ttu-id="21432-168">运行此命令时不执行隐式还原。</span><span class="sxs-lookup"><span data-stu-id="21432-168">Doesn't execute an implicit restore when running the command.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="21432-169">指定输出目录的路径。</span><span class="sxs-lookup"><span data-stu-id="21432-169">Specifies the path for the output directory.</span></span> <span data-ttu-id="21432-170">如未指定，对于依赖于框架的部署，将默认为 ./bin/[configuration]/[framework]/publish/ 或对于独立部署，将默认为 ./bin/[configuration]/[framework]/[runtime]/publish/。</span><span class="sxs-lookup"><span data-stu-id="21432-170">If not specified, it defaults to *./bin/[configuration]/[framework]/publish/* for a framework-dependent deployment or *./bin/[configuration]/[framework]/[runtime]/publish/* for a self-contained deployment.</span></span>
<span data-ttu-id="21432-171">如果路径是相对的，则生成的输出目录与项目文件位置相关，而与当前工作目录不相关。</span><span class="sxs-lookup"><span data-stu-id="21432-171">If the path is relative, the output directory generated is relative to the project file location, not to the current working directory.</span></span>

`--self-contained`

<span data-ttu-id="21432-172">与应用程序一同发布 .NET Core 运行时，因此无需在目标计算机上安装运行时。</span><span class="sxs-lookup"><span data-stu-id="21432-172">Publishes the .NET Core runtime with your application so the runtime doesn't need to be installed on the target machine.</span></span> <span data-ttu-id="21432-173">如果指定了运行时标识符，默认值为 `true`。</span><span class="sxs-lookup"><span data-stu-id="21432-173">If a runtime identifier is specified, its default value is `true`.</span></span> <span data-ttu-id="21432-174">若要详细了解不同的部署类型，请参阅 [.NET Core 应用程序部署](../deploying/index.md)。</span><span class="sxs-lookup"><span data-stu-id="21432-174">For more information about the different deployment types, see [.NET Core application deployment](../deploying/index.md).</span></span>

`-r|--runtime <RUNTIME_IDENTIFIER>`

<span data-ttu-id="21432-175">发布针对给定运行时的应用程序。</span><span class="sxs-lookup"><span data-stu-id="21432-175">Publishes the application for a given runtime.</span></span> <span data-ttu-id="21432-176">这将在创建[独立部署 (SCD)](../deploying/index.md#self-contained-deployments-scd) 时使用。</span><span class="sxs-lookup"><span data-stu-id="21432-176">This is used when creating a [self-contained deployment (SCD)](../deploying/index.md#self-contained-deployments-scd).</span></span> <span data-ttu-id="21432-177">有关运行时标识符 (RID) 的列表，请参阅 [RID 目录](../rid-catalog.md)。</span><span class="sxs-lookup"><span data-stu-id="21432-177">For a list of Runtime Identifiers (RIDs), see the [RID catalog](../rid-catalog.md).</span></span> <span data-ttu-id="21432-178">默认为发布[依赖于框架的部署 (FDD)](../deploying/index.md#framework-dependent-deployments-fdd)。</span><span class="sxs-lookup"><span data-stu-id="21432-178">Default is to publish a [framework-dependent deployment (FDD)](../deploying/index.md#framework-dependent-deployments-fdd).</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="21432-179">设置命令的详细级别。</span><span class="sxs-lookup"><span data-stu-id="21432-179">Sets the verbosity level of the command.</span></span> <span data-ttu-id="21432-180">允许使用的值为 `q[uiet]`、`m[inimal]`、`n[ormal]`、`d[etailed]` 和 `diag[nostic]`。</span><span class="sxs-lookup"><span data-stu-id="21432-180">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

`--version-suffix <VERSION_SUFFIX>`

<span data-ttu-id="21432-181">定义版本后缀来替换项目文件的版本字段中的星号 (`*`)。</span><span class="sxs-lookup"><span data-stu-id="21432-181">Defines the version suffix to replace the asterisk (`*`) in the version field of the project file.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="21432-182">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="21432-182">.NET Core 1.x</span></span>](#tab/netcore1x)

`-c|--configuration {Debug|Release}`

<span data-ttu-id="21432-183">定义生成配置。</span><span class="sxs-lookup"><span data-stu-id="21432-183">Defines the build configuration.</span></span> <span data-ttu-id="21432-184">默认值为 `Debug`。</span><span class="sxs-lookup"><span data-stu-id="21432-184">The default value is `Debug`.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="21432-185">为指定的[目标框架](../../standard/frameworks.md)发布应用程序。</span><span class="sxs-lookup"><span data-stu-id="21432-185">Publishes the application for the specified [target framework](../../standard/frameworks.md).</span></span> <span data-ttu-id="21432-186">必须在项目文件中指定目标框架。</span><span class="sxs-lookup"><span data-stu-id="21432-186">You must specify the target framework in the project file.</span></span>

`-h|--help`

<span data-ttu-id="21432-187">打印出有关命令的简短帮助。</span><span class="sxs-lookup"><span data-stu-id="21432-187">Prints out a short help for the command.</span></span>

`--manifest <PATH_TO_MANIFEST_FILE>`

<span data-ttu-id="21432-188">指定一个或多个[目标清单](../deploying/runtime-store.md)，用于剪裁与应用程序一同发布的一组包。</span><span class="sxs-lookup"><span data-stu-id="21432-188">Specifies one or several [target manifests](../deploying/runtime-store.md) to use to trim the set of packages published with the app.</span></span> <span data-ttu-id="21432-189">清单文件是 [`dotnet store` 命令](dotnet-store.md)输出的一部分。</span><span class="sxs-lookup"><span data-stu-id="21432-189">The manifest file is part of the output of the [`dotnet store` command](dotnet-store.md).</span></span> <span data-ttu-id="21432-190">若要指定多个清单，请为每个清单添加一个 `--manifest` 选项。</span><span class="sxs-lookup"><span data-stu-id="21432-190">To specify multiple manifests, add a `--manifest` option for each manifest.</span></span> <span data-ttu-id="21432-191">自 .NET Core 2.0 SDK 起，可以使用此选项。</span><span class="sxs-lookup"><span data-stu-id="21432-191">This option is available starting with .NET Core 2.0 SDK.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="21432-192">指定输出目录的路径。</span><span class="sxs-lookup"><span data-stu-id="21432-192">Specifies the path for the output directory.</span></span> <span data-ttu-id="21432-193">如未指定，对于依赖于框架的部署，将默认为 ./bin/[configuration]/[framework]/publish/ 或对于独立部署，将默认为 ./bin/[configuration]/[framework]/[runtime]/publish/。</span><span class="sxs-lookup"><span data-stu-id="21432-193">If not specified, it defaults to *./bin/[configuration]/[framework]/publish/* for a framework-dependent deployment or *./bin/[configuration]/[framework]/[runtime]/publish/* for a self-contained deployment.</span></span>
<span data-ttu-id="21432-194">如果路径是相对的，则生成的输出目录与项目文件位置相关，而与当前工作目录不相关。</span><span class="sxs-lookup"><span data-stu-id="21432-194">If the path is relative, the output directory generated is relative to the project file location, not to the current working directory.</span></span>

`-r|--runtime <RUNTIME_IDENTIFIER>`

<span data-ttu-id="21432-195">发布针对给定运行时的应用程序。</span><span class="sxs-lookup"><span data-stu-id="21432-195">Publishes the application for a given runtime.</span></span> <span data-ttu-id="21432-196">这将在创建[独立部署 (SCD)](../deploying/index.md#self-contained-deployments-scd) 时使用。</span><span class="sxs-lookup"><span data-stu-id="21432-196">This is used when creating a [self-contained deployment (SCD)](../deploying/index.md#self-contained-deployments-scd).</span></span> <span data-ttu-id="21432-197">有关运行时标识符 (RID) 的列表，请参阅 [RID 目录](../rid-catalog.md)。</span><span class="sxs-lookup"><span data-stu-id="21432-197">For a list of Runtime Identifiers (RIDs), see the [RID catalog](../rid-catalog.md).</span></span> <span data-ttu-id="21432-198">默认为发布[依赖于框架的部署 (FDD)](../deploying/index.md#framework-dependent-deployments-fdd)。</span><span class="sxs-lookup"><span data-stu-id="21432-198">Default is to publish a [framework-dependent deployment (FDD)](../deploying/index.md#framework-dependent-deployments-fdd).</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="21432-199">设置命令的详细级别。</span><span class="sxs-lookup"><span data-stu-id="21432-199">Sets the verbosity level of the command.</span></span> <span data-ttu-id="21432-200">允许使用的值为 `q[uiet]`、`m[inimal]`、`n[ormal]`、`d[etailed]` 和 `diag[nostic]`。</span><span class="sxs-lookup"><span data-stu-id="21432-200">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

`--version-suffix <VERSION_SUFFIX>`

<span data-ttu-id="21432-201">定义版本后缀来替换项目文件的版本字段中的星号 (`*`)。</span><span class="sxs-lookup"><span data-stu-id="21432-201">Defines the version suffix to replace the asterisk (`*`) in the version field of the project file.</span></span>

---

## <a name="examples"></a><span data-ttu-id="21432-202">示例</span><span class="sxs-lookup"><span data-stu-id="21432-202">Examples</span></span>

<span data-ttu-id="21432-203">在当前目录中发布项目：</span><span class="sxs-lookup"><span data-stu-id="21432-203">Publish the project in the current directory:</span></span>

`dotnet publish`

<span data-ttu-id="21432-204">使用指定的项目文件发布应用程序：</span><span class="sxs-lookup"><span data-stu-id="21432-204">Publish the application using the specified project file:</span></span>

`dotnet publish ~/projects/app1/app1.csproj`

<span data-ttu-id="21432-205">使用 `netcoreapp1.1` 框架发布当前目录中的项目：</span><span class="sxs-lookup"><span data-stu-id="21432-205">Publish the project in the current directory using the `netcoreapp1.1` framework:</span></span>

`dotnet publish --framework netcoreapp1.1`

<span data-ttu-id="21432-206">使用 `netcoreapp1.1` 框架和 `OS X 10.10` 的运行时发布当前应用程序（必须在项目文件中列出此 RID）。</span><span class="sxs-lookup"><span data-stu-id="21432-206">Publish the current application using the `netcoreapp1.1` framework and the runtime for `OS X 10.10` (you must list this RID in the project file).</span></span>

`dotnet publish --framework netcoreapp1.1 --runtime osx.10.11-x64`

<span data-ttu-id="21432-207">发布当前应用程序，但在还原操作期间不还原项目到项目 (P2P) 引用，只还原根项目（.NET Core SDK 2.0 及更高版本）：</span><span class="sxs-lookup"><span data-stu-id="21432-207">Publish the current application but don't restore project-to-project (P2P) references, just the root project during the restore operation (.NET Core SDK 2.0 and later versions):</span></span>

`dotnet publish --no-dependencies`

## <a name="see-also"></a><span data-ttu-id="21432-208">请参阅</span><span class="sxs-lookup"><span data-stu-id="21432-208">See also</span></span>

* [<span data-ttu-id="21432-209">目标框架</span><span class="sxs-lookup"><span data-stu-id="21432-209">Target frameworks</span></span>](../../standard/frameworks.md)
* [<span data-ttu-id="21432-210">运行时标识符 (RID) 目录</span><span class="sxs-lookup"><span data-stu-id="21432-210">Runtime IDentifier (RID) catalog</span></span>](../rid-catalog.md)
