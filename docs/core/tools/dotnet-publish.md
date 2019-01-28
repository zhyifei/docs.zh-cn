---
title: dotnet publish 命令
description: dotnet publish 命令可将 .NET Core 项目发布到目录。
ms.date: 05/29/2018
ms.openlocfilehash: 40ce31073ee3f6f94e110f3a4e1eeda0c7b2e48d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54559274"
---
# <a name="dotnet-publish"></a><span data-ttu-id="cdc05-103">dotnet 发布</span><span class="sxs-lookup"><span data-stu-id="cdc05-103">dotnet publish</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="cdc05-104">name</span><span class="sxs-lookup"><span data-stu-id="cdc05-104">Name</span></span>

<span data-ttu-id="cdc05-105">`dotnet publish` - 将应用程序及其依赖项打包到文件夹以部署到托管系统。</span><span class="sxs-lookup"><span data-stu-id="cdc05-105">`dotnet publish` - Packs the application and its dependencies into a folder for deployment to a hosting system.</span></span>

## <a name="synopsis"></a><span data-ttu-id="cdc05-106">摘要</span><span class="sxs-lookup"><span data-stu-id="cdc05-106">Synopsis</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="cdc05-107">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="cdc05-107">.NET Core 2.1</span></span>](#tab/netcore21)
```
dotnet publish [<PROJECT>] [-c|--configuration] [-f|--framework] [--force] [--manifest] [--no-build] [--no-dependencies]
    [--no-restore] [-o|--output] [-r|--runtime] [--self-contained] [-v|--verbosity] [--version-suffix]
dotnet publish [-h|--help]
```
# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="cdc05-108">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="cdc05-108">.NET Core 2.0</span></span>](#tab/netcore20)
```
dotnet publish [<PROJECT>] [-c|--configuration] [-f|--framework] [--force] [--manifest] [--no-dependencies]
    [--no-restore] [-o|--output] [-r|--runtime] [--self-contained] [-v|--verbosity] [--version-suffix]
dotnet publish [-h|--help]
```
# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="cdc05-109">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="cdc05-109">.NET Core 1.x</span></span>](#tab/netcore1x)
```
dotnet publish [<PROJECT>] [-c|--configuration] [-f|--framework] [-o|--output] [-r|--runtime] [-v|--verbosity]
    [--version-suffix]
dotnet publish [-h|--help]
```
---

## <a name="description"></a><span data-ttu-id="cdc05-110">说明</span><span class="sxs-lookup"><span data-stu-id="cdc05-110">Description</span></span>

<span data-ttu-id="cdc05-111">`dotnet publish` 编译应用程序、读取 project 文件中指定的所有依赖项并将生成的文件集发布到目录。</span><span class="sxs-lookup"><span data-stu-id="cdc05-111">`dotnet publish` compiles the application, reads through its dependencies specified in the project file, and publishes the resulting set of files to a directory.</span></span> <span data-ttu-id="cdc05-112">输出包括以下资产：</span><span class="sxs-lookup"><span data-stu-id="cdc05-112">The output includes the following assets:</span></span>

* <span data-ttu-id="cdc05-113">扩展名为 dll 的程序集中的中间语言 (IL) 代码。</span><span class="sxs-lookup"><span data-stu-id="cdc05-113">Intermediate Language (IL) code in an assembly with a *dll* extension.</span></span>
* <span data-ttu-id="cdc05-114">包含项目所有依赖项的 .deps.json 文件。</span><span class="sxs-lookup"><span data-stu-id="cdc05-114">*.deps.json* file that includes all of the dependencies of the project.</span></span>
* <span data-ttu-id="cdc05-115">.runtime.config.json 文件，其中指定了应用程序所需的共享运行时，以及运行时的其他配置选项（例如，垃圾回收类型）。</span><span class="sxs-lookup"><span data-stu-id="cdc05-115">*.runtime.config.json* file that specifies the shared runtime that the application expects, as well as other configuration options for the runtime (for example, garbage collection type).</span></span>
* <span data-ttu-id="cdc05-116">应用程序的依赖项，将这些依赖项从 NuGet 缓存复制到输出文件夹。</span><span class="sxs-lookup"><span data-stu-id="cdc05-116">The application's dependencies, which are copied from the NuGet cache into the output folder.</span></span>

<span data-ttu-id="cdc05-117">`dotnet publish` 命令的输出可供部署至托管系统（例如服务器、电脑、Mac、笔记本电脑）以便执行。</span><span class="sxs-lookup"><span data-stu-id="cdc05-117">The `dotnet publish` command's output is ready for deployment to a hosting system (for example, a server, PC, Mac, laptop) for execution.</span></span> <span data-ttu-id="cdc05-118">若要准备用于部署的应用程序，这是唯一正式受支持的方法。</span><span class="sxs-lookup"><span data-stu-id="cdc05-118">It's the only officially supported way to prepare the application for deployment.</span></span> <span data-ttu-id="cdc05-119">根据项目指定的部署的类型，托管系统不一定已在其上安装 .NET Core 共享运行时。</span><span class="sxs-lookup"><span data-stu-id="cdc05-119">Depending on the type of deployment that the project specifies, the hosting system may or may not have the .NET Core shared runtime installed on it.</span></span> <span data-ttu-id="cdc05-120">有关详细信息，请参阅 [.NET Core 应用程序部署](../deploying/index.md)。</span><span class="sxs-lookup"><span data-stu-id="cdc05-120">For more information, see [.NET Core Application Deployment](../deploying/index.md).</span></span> <span data-ttu-id="cdc05-121">有关已发布应用程序的目录结构，请参阅[目录结构](/aspnet/core/hosting/directory-structure)。</span><span class="sxs-lookup"><span data-stu-id="cdc05-121">For the directory structure of a published application, see [Directory structure](/aspnet/core/hosting/directory-structure).</span></span>

[!INCLUDE[dotnet restore note + options](~/includes/dotnet-restore-note-options.md)]

## <a name="arguments"></a><span data-ttu-id="cdc05-122">自变量</span><span class="sxs-lookup"><span data-stu-id="cdc05-122">Arguments</span></span>

`PROJECT`

<span data-ttu-id="cdc05-123">要发布的项目。</span><span class="sxs-lookup"><span data-stu-id="cdc05-123">The project to publish.</span></span> <span data-ttu-id="cdc05-124">它是 [C#](csproj.md)、F# 或 Visual Basic 项目文件的路径和文件名，或包含 C#、F# 或 Visual Basic 项目文件的目录的路径。</span><span class="sxs-lookup"><span data-stu-id="cdc05-124">It's either the path and filename of a [C#](csproj.md), F#, or Visual Basic project file, or the path to a directory that contains a C#, F#, or Visual Basic project file.</span></span> <span data-ttu-id="cdc05-125">如果未指定，则默认为当前目录。</span><span class="sxs-lookup"><span data-stu-id="cdc05-125">If not specified, it defaults to the current directory.</span></span>

## <a name="options"></a><span data-ttu-id="cdc05-126">选项</span><span class="sxs-lookup"><span data-stu-id="cdc05-126">Options</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="cdc05-127">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="cdc05-127">.NET Core 2.1</span></span>](#tab/netcore21)

`-c|--configuration {Debug|Release}`

<span data-ttu-id="cdc05-128">定义生成配置。</span><span class="sxs-lookup"><span data-stu-id="cdc05-128">Defines the build configuration.</span></span> <span data-ttu-id="cdc05-129">默认值为 `Debug`。</span><span class="sxs-lookup"><span data-stu-id="cdc05-129">The default value is `Debug`.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="cdc05-130">为指定的[目标框架](../../standard/frameworks.md)发布应用程序。</span><span class="sxs-lookup"><span data-stu-id="cdc05-130">Publishes the application for the specified [target framework](../../standard/frameworks.md).</span></span> <span data-ttu-id="cdc05-131">必须在项目文件中指定目标框架。</span><span class="sxs-lookup"><span data-stu-id="cdc05-131">You must specify the target framework in the project file.</span></span>

`--force`

<span data-ttu-id="cdc05-132">强制解析所有依赖项，即使上次还原已成功，也不例外。</span><span class="sxs-lookup"><span data-stu-id="cdc05-132">Forces all dependencies to be resolved even if the last restore was successful.</span></span> <span data-ttu-id="cdc05-133">指定此标记等同于删除 project.assets.json 文件。</span><span class="sxs-lookup"><span data-stu-id="cdc05-133">Specifying this flag is the same as deleting the *project.assets.json* file.</span></span>

`-h|--help`

<span data-ttu-id="cdc05-134">打印出有关命令的简短帮助。</span><span class="sxs-lookup"><span data-stu-id="cdc05-134">Prints out a short help for the command.</span></span>

`--manifest <PATH_TO_MANIFEST_FILE>`

<span data-ttu-id="cdc05-135">指定一个或多个[目标清单](../deploying/runtime-store.md)，用于剪裁与应用程序一同发布的一组包。</span><span class="sxs-lookup"><span data-stu-id="cdc05-135">Specifies one or several [target manifests](../deploying/runtime-store.md) to use to trim the set of packages published with the app.</span></span> <span data-ttu-id="cdc05-136">清单文件是 [`dotnet store` 命令](dotnet-store.md)输出的一部分。</span><span class="sxs-lookup"><span data-stu-id="cdc05-136">The manifest file is part of the output of the [`dotnet store` command](dotnet-store.md).</span></span> <span data-ttu-id="cdc05-137">若要指定多个清单，请为每个清单添加一个 `--manifest` 选项。</span><span class="sxs-lookup"><span data-stu-id="cdc05-137">To specify multiple manifests, add a `--manifest` option for each manifest.</span></span> <span data-ttu-id="cdc05-138">自 .NET Core 2.0 SDK 起，可以使用此选项。</span><span class="sxs-lookup"><span data-stu-id="cdc05-138">This option is available starting with .NET Core 2.0 SDK.</span></span>

`--no-build`

<span data-ttu-id="cdc05-139">发布前不生成项目。</span><span class="sxs-lookup"><span data-stu-id="cdc05-139">Doesn't build the project before publishing.</span></span> <span data-ttu-id="cdc05-140">还将隐式设置 `--no-restore` 标记。</span><span class="sxs-lookup"><span data-stu-id="cdc05-140">It also implicitly sets the `--no-restore` flag.</span></span>

`--no-dependencies`

<span data-ttu-id="cdc05-141">忽略项目间引用，仅还原根项目。</span><span class="sxs-lookup"><span data-stu-id="cdc05-141">Ignores project-to-project references and only restores the root project.</span></span>

`--no-restore`

<span data-ttu-id="cdc05-142">运行此命令时不执行隐式还原。</span><span class="sxs-lookup"><span data-stu-id="cdc05-142">Doesn't execute an implicit restore when running the command.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="cdc05-143">指定输出目录的路径。</span><span class="sxs-lookup"><span data-stu-id="cdc05-143">Specifies the path for the output directory.</span></span> <span data-ttu-id="cdc05-144">如未指定，对于依赖于框架的部署，将默认为 ./bin/[configuration]/[framework]/publish/ 或对于独立部署，将默认为 ./bin/[configuration]/[framework]/[runtime]/publish/。</span><span class="sxs-lookup"><span data-stu-id="cdc05-144">If not specified, it defaults to *./bin/[configuration]/[framework]/publish/* for a framework-dependent deployment or *./bin/[configuration]/[framework]/[runtime]/publish/* for a self-contained deployment.</span></span>
<span data-ttu-id="cdc05-145">如果路径是相对的，则生成的输出目录与项目文件位置相关，而与当前工作目录不相关。</span><span class="sxs-lookup"><span data-stu-id="cdc05-145">If the path is relative, the output directory generated is relative to the project file location, not to the current working directory.</span></span>

`--self-contained`

<span data-ttu-id="cdc05-146">与应用程序一同发布 .NET Core 运行时，因此无需在目标计算机上安装运行时。</span><span class="sxs-lookup"><span data-stu-id="cdc05-146">Publishes the .NET Core runtime with your application so the runtime doesn't need to be installed on the target machine.</span></span> <span data-ttu-id="cdc05-147">如果指定了运行时标识符，默认值为 `true`。</span><span class="sxs-lookup"><span data-stu-id="cdc05-147">If a runtime identifier is specified, its default value is `true`.</span></span> <span data-ttu-id="cdc05-148">若要详细了解不同的部署类型，请参阅 [.NET Core 应用程序部署](../deploying/index.md)。</span><span class="sxs-lookup"><span data-stu-id="cdc05-148">For more information about the different deployment types, see [.NET Core application deployment](../deploying/index.md).</span></span>

`-r|--runtime <RUNTIME_IDENTIFIER>`

<span data-ttu-id="cdc05-149">发布针对给定运行时的应用程序。</span><span class="sxs-lookup"><span data-stu-id="cdc05-149">Publishes the application for a given runtime.</span></span> <span data-ttu-id="cdc05-150">这将在创建[独立部署 (SCD)](../deploying/index.md#self-contained-deployments-scd) 时使用。</span><span class="sxs-lookup"><span data-stu-id="cdc05-150">This is used when creating a [self-contained deployment (SCD)](../deploying/index.md#self-contained-deployments-scd).</span></span> <span data-ttu-id="cdc05-151">有关运行时标识符 (RID) 的列表，请参阅 [RID 目录](../rid-catalog.md)。</span><span class="sxs-lookup"><span data-stu-id="cdc05-151">For a list of Runtime Identifiers (RIDs), see the [RID catalog](../rid-catalog.md).</span></span> <span data-ttu-id="cdc05-152">默认为发布[依赖于框架的部署 (FDD)](../deploying/index.md#framework-dependent-deployments-fdd)。</span><span class="sxs-lookup"><span data-stu-id="cdc05-152">Default is to publish a [framework-dependent deployment (FDD)](../deploying/index.md#framework-dependent-deployments-fdd).</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="cdc05-153">设置命令的详细级别。</span><span class="sxs-lookup"><span data-stu-id="cdc05-153">Sets the verbosity level of the command.</span></span> <span data-ttu-id="cdc05-154">允许使用的值为 `q[uiet]`、`m[inimal]`、`n[ormal]`、`d[etailed]` 和 `diag[nostic]`。</span><span class="sxs-lookup"><span data-stu-id="cdc05-154">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

`--version-suffix <VERSION_SUFFIX>`

<span data-ttu-id="cdc05-155">定义版本后缀来替换项目文件的版本字段中的星号 (`*`)。</span><span class="sxs-lookup"><span data-stu-id="cdc05-155">Defines the version suffix to replace the asterisk (`*`) in the version field of the project file.</span></span>

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="cdc05-156">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="cdc05-156">.NET Core 2.0</span></span>](#tab/netcore20)

`-c|--configuration {Debug|Release}`

<span data-ttu-id="cdc05-157">定义生成配置。</span><span class="sxs-lookup"><span data-stu-id="cdc05-157">Defines the build configuration.</span></span> <span data-ttu-id="cdc05-158">默认值为 `Debug`。</span><span class="sxs-lookup"><span data-stu-id="cdc05-158">The default value is `Debug`.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="cdc05-159">为指定的[目标框架](../../standard/frameworks.md)发布应用程序。</span><span class="sxs-lookup"><span data-stu-id="cdc05-159">Publishes the application for the specified [target framework](../../standard/frameworks.md).</span></span> <span data-ttu-id="cdc05-160">必须在项目文件中指定目标框架。</span><span class="sxs-lookup"><span data-stu-id="cdc05-160">You must specify the target framework in the project file.</span></span>

`--force`

<span data-ttu-id="cdc05-161">强制解析所有依赖项，即使上次还原已成功，也不例外。</span><span class="sxs-lookup"><span data-stu-id="cdc05-161">Forces all dependencies to be resolved even if the last restore was successful.</span></span> <span data-ttu-id="cdc05-162">指定此标记等同于删除 project.assets.json 文件。</span><span class="sxs-lookup"><span data-stu-id="cdc05-162">Specifying this flag is the same as deleting the *project.assets.json* file.</span></span>

`-h|--help`

<span data-ttu-id="cdc05-163">打印出有关命令的简短帮助。</span><span class="sxs-lookup"><span data-stu-id="cdc05-163">Prints out a short help for the command.</span></span>

`--manifest <PATH_TO_MANIFEST_FILE>`

<span data-ttu-id="cdc05-164">指定一个或多个[目标清单](../deploying/runtime-store.md)，用于剪裁与应用程序一同发布的一组包。</span><span class="sxs-lookup"><span data-stu-id="cdc05-164">Specifies one or several [target manifests](../deploying/runtime-store.md) to use to trim the set of packages published with the app.</span></span> <span data-ttu-id="cdc05-165">清单文件是 [`dotnet store` 命令](dotnet-store.md)输出的一部分。</span><span class="sxs-lookup"><span data-stu-id="cdc05-165">The manifest file is part of the output of the [`dotnet store` command](dotnet-store.md).</span></span> <span data-ttu-id="cdc05-166">若要指定多个清单，请为每个清单添加一个 `--manifest` 选项。</span><span class="sxs-lookup"><span data-stu-id="cdc05-166">To specify multiple manifests, add a `--manifest` option for each manifest.</span></span> <span data-ttu-id="cdc05-167">自 .NET Core 2.0 SDK 起，可以使用此选项。</span><span class="sxs-lookup"><span data-stu-id="cdc05-167">This option is available starting with .NET Core 2.0 SDK.</span></span>

`--no-dependencies`

<span data-ttu-id="cdc05-168">忽略项目间引用，仅还原根项目。</span><span class="sxs-lookup"><span data-stu-id="cdc05-168">Ignores project-to-project references and only restores the root project.</span></span>

`--no-restore`

<span data-ttu-id="cdc05-169">运行此命令时不执行隐式还原。</span><span class="sxs-lookup"><span data-stu-id="cdc05-169">Doesn't execute an implicit restore when running the command.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="cdc05-170">指定输出目录的路径。</span><span class="sxs-lookup"><span data-stu-id="cdc05-170">Specifies the path for the output directory.</span></span> <span data-ttu-id="cdc05-171">如未指定，对于依赖于框架的部署，将默认为 ./bin/[configuration]/[framework]/publish/ 或对于独立部署，将默认为 ./bin/[configuration]/[framework]/[runtime]/publish/。</span><span class="sxs-lookup"><span data-stu-id="cdc05-171">If not specified, it defaults to *./bin/[configuration]/[framework]/publish/* for a framework-dependent deployment or *./bin/[configuration]/[framework]/[runtime]/publish/* for a self-contained deployment.</span></span>
<span data-ttu-id="cdc05-172">如果路径是相对的，则生成的输出目录与项目文件位置相关，而与当前工作目录不相关。</span><span class="sxs-lookup"><span data-stu-id="cdc05-172">If the path is relative, the output directory generated is relative to the project file location, not to the current working directory.</span></span>

`--self-contained`

<span data-ttu-id="cdc05-173">与应用程序一同发布 .NET Core 运行时，因此无需在目标计算机上安装运行时。</span><span class="sxs-lookup"><span data-stu-id="cdc05-173">Publishes the .NET Core runtime with your application so the runtime doesn't need to be installed on the target machine.</span></span> <span data-ttu-id="cdc05-174">如果指定了运行时标识符，默认值为 `true`。</span><span class="sxs-lookup"><span data-stu-id="cdc05-174">If a runtime identifier is specified, its default value is `true`.</span></span> <span data-ttu-id="cdc05-175">若要详细了解不同的部署类型，请参阅 [.NET Core 应用程序部署](../deploying/index.md)。</span><span class="sxs-lookup"><span data-stu-id="cdc05-175">For more information about the different deployment types, see [.NET Core application deployment](../deploying/index.md).</span></span>

`-r|--runtime <RUNTIME_IDENTIFIER>`

<span data-ttu-id="cdc05-176">发布针对给定运行时的应用程序。</span><span class="sxs-lookup"><span data-stu-id="cdc05-176">Publishes the application for a given runtime.</span></span> <span data-ttu-id="cdc05-177">这将在创建[独立部署 (SCD)](../deploying/index.md#self-contained-deployments-scd) 时使用。</span><span class="sxs-lookup"><span data-stu-id="cdc05-177">This is used when creating a [self-contained deployment (SCD)](../deploying/index.md#self-contained-deployments-scd).</span></span> <span data-ttu-id="cdc05-178">有关运行时标识符 (RID) 的列表，请参阅 [RID 目录](../rid-catalog.md)。</span><span class="sxs-lookup"><span data-stu-id="cdc05-178">For a list of Runtime Identifiers (RIDs), see the [RID catalog](../rid-catalog.md).</span></span> <span data-ttu-id="cdc05-179">默认为发布[依赖于框架的部署 (FDD)](../deploying/index.md#framework-dependent-deployments-fdd)。</span><span class="sxs-lookup"><span data-stu-id="cdc05-179">Default is to publish a [framework-dependent deployment (FDD)](../deploying/index.md#framework-dependent-deployments-fdd).</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="cdc05-180">设置命令的详细级别。</span><span class="sxs-lookup"><span data-stu-id="cdc05-180">Sets the verbosity level of the command.</span></span> <span data-ttu-id="cdc05-181">允许使用的值为 `q[uiet]`、`m[inimal]`、`n[ormal]`、`d[etailed]` 和 `diag[nostic]`。</span><span class="sxs-lookup"><span data-stu-id="cdc05-181">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

`--version-suffix <VERSION_SUFFIX>`

<span data-ttu-id="cdc05-182">定义版本后缀来替换项目文件的版本字段中的星号 (`*`)。</span><span class="sxs-lookup"><span data-stu-id="cdc05-182">Defines the version suffix to replace the asterisk (`*`) in the version field of the project file.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="cdc05-183">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="cdc05-183">.NET Core 1.x</span></span>](#tab/netcore1x)

`-c|--configuration {Debug|Release}`

<span data-ttu-id="cdc05-184">定义生成配置。</span><span class="sxs-lookup"><span data-stu-id="cdc05-184">Defines the build configuration.</span></span> <span data-ttu-id="cdc05-185">默认值为 `Debug`。</span><span class="sxs-lookup"><span data-stu-id="cdc05-185">The default value is `Debug`.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="cdc05-186">为指定的[目标框架](../../standard/frameworks.md)发布应用程序。</span><span class="sxs-lookup"><span data-stu-id="cdc05-186">Publishes the application for the specified [target framework](../../standard/frameworks.md).</span></span> <span data-ttu-id="cdc05-187">必须在项目文件中指定目标框架。</span><span class="sxs-lookup"><span data-stu-id="cdc05-187">You must specify the target framework in the project file.</span></span>

`-h|--help`

<span data-ttu-id="cdc05-188">打印出有关命令的简短帮助。</span><span class="sxs-lookup"><span data-stu-id="cdc05-188">Prints out a short help for the command.</span></span>

`--manifest <PATH_TO_MANIFEST_FILE>`

<span data-ttu-id="cdc05-189">指定一个或多个[目标清单](../deploying/runtime-store.md)，用于剪裁与应用程序一同发布的一组包。</span><span class="sxs-lookup"><span data-stu-id="cdc05-189">Specifies one or several [target manifests](../deploying/runtime-store.md) to use to trim the set of packages published with the app.</span></span> <span data-ttu-id="cdc05-190">清单文件是 [`dotnet store` 命令](dotnet-store.md)输出的一部分。</span><span class="sxs-lookup"><span data-stu-id="cdc05-190">The manifest file is part of the output of the [`dotnet store` command](dotnet-store.md).</span></span> <span data-ttu-id="cdc05-191">若要指定多个清单，请为每个清单添加一个 `--manifest` 选项。</span><span class="sxs-lookup"><span data-stu-id="cdc05-191">To specify multiple manifests, add a `--manifest` option for each manifest.</span></span> <span data-ttu-id="cdc05-192">自 .NET Core 2.0 SDK 起，可以使用此选项。</span><span class="sxs-lookup"><span data-stu-id="cdc05-192">This option is available starting with .NET Core 2.0 SDK.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="cdc05-193">指定输出目录的路径。</span><span class="sxs-lookup"><span data-stu-id="cdc05-193">Specifies the path for the output directory.</span></span> <span data-ttu-id="cdc05-194">如未指定，对于依赖于框架的部署，将默认为 ./bin/[configuration]/[framework]/publish/ 或对于独立部署，将默认为 ./bin/[configuration]/[framework]/[runtime]/publish/。</span><span class="sxs-lookup"><span data-stu-id="cdc05-194">If not specified, it defaults to *./bin/[configuration]/[framework]/publish/* for a framework-dependent deployment or *./bin/[configuration]/[framework]/[runtime]/publish/* for a self-contained deployment.</span></span>
<span data-ttu-id="cdc05-195">如果路径是相对的，则生成的输出目录与项目文件位置相关，而与当前工作目录不相关。</span><span class="sxs-lookup"><span data-stu-id="cdc05-195">If the path is relative, the output directory generated is relative to the project file location, not to the current working directory.</span></span>

`-r|--runtime <RUNTIME_IDENTIFIER>`

<span data-ttu-id="cdc05-196">发布针对给定运行时的应用程序。</span><span class="sxs-lookup"><span data-stu-id="cdc05-196">Publishes the application for a given runtime.</span></span> <span data-ttu-id="cdc05-197">这将在创建[独立部署 (SCD)](../deploying/index.md#self-contained-deployments-scd) 时使用。</span><span class="sxs-lookup"><span data-stu-id="cdc05-197">This is used when creating a [self-contained deployment (SCD)](../deploying/index.md#self-contained-deployments-scd).</span></span> <span data-ttu-id="cdc05-198">有关运行时标识符 (RID) 的列表，请参阅 [RID 目录](../rid-catalog.md)。</span><span class="sxs-lookup"><span data-stu-id="cdc05-198">For a list of Runtime Identifiers (RIDs), see the [RID catalog](../rid-catalog.md).</span></span> <span data-ttu-id="cdc05-199">默认为发布[依赖于框架的部署 (FDD)](../deploying/index.md#framework-dependent-deployments-fdd)。</span><span class="sxs-lookup"><span data-stu-id="cdc05-199">Default is to publish a [framework-dependent deployment (FDD)](../deploying/index.md#framework-dependent-deployments-fdd).</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="cdc05-200">设置命令的详细级别。</span><span class="sxs-lookup"><span data-stu-id="cdc05-200">Sets the verbosity level of the command.</span></span> <span data-ttu-id="cdc05-201">允许使用的值为 `q[uiet]`、`m[inimal]`、`n[ormal]`、`d[etailed]` 和 `diag[nostic]`。</span><span class="sxs-lookup"><span data-stu-id="cdc05-201">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

`--version-suffix <VERSION_SUFFIX>`

<span data-ttu-id="cdc05-202">定义版本后缀来替换项目文件的版本字段中的星号 (`*`)。</span><span class="sxs-lookup"><span data-stu-id="cdc05-202">Defines the version suffix to replace the asterisk (`*`) in the version field of the project file.</span></span>

---

## <a name="examples"></a><span data-ttu-id="cdc05-203">示例</span><span class="sxs-lookup"><span data-stu-id="cdc05-203">Examples</span></span>

<span data-ttu-id="cdc05-204">在当前目录中发布项目：</span><span class="sxs-lookup"><span data-stu-id="cdc05-204">Publish the project in the current directory:</span></span>

`dotnet publish`

<span data-ttu-id="cdc05-205">使用指定的项目文件发布应用程序：</span><span class="sxs-lookup"><span data-stu-id="cdc05-205">Publish the application using the specified project file:</span></span>

`dotnet publish ~/projects/app1/app1.csproj`

<span data-ttu-id="cdc05-206">使用 `netcoreapp1.1` 框架发布当前目录中的项目：</span><span class="sxs-lookup"><span data-stu-id="cdc05-206">Publish the project in the current directory using the `netcoreapp1.1` framework:</span></span>

`dotnet publish --framework netcoreapp1.1`

<span data-ttu-id="cdc05-207">使用 `netcoreapp1.1` 框架和 `OS X 10.10` 的运行时发布当前应用程序（必须在项目文件中列出此 RID）。</span><span class="sxs-lookup"><span data-stu-id="cdc05-207">Publish the current application using the `netcoreapp1.1` framework and the runtime for `OS X 10.10` (you must list this RID in the project file).</span></span>

`dotnet publish --framework netcoreapp1.1 --runtime osx.10.11-x64`

<span data-ttu-id="cdc05-208">发布当前应用程序，但在还原操作期间不还原项目到项目 (P2P) 引用，只还原根项目（.NET Core SDK 2.0 及更高版本）：</span><span class="sxs-lookup"><span data-stu-id="cdc05-208">Publish the current application but don't restore project-to-project (P2P) references, just the root project during the restore operation (.NET Core SDK 2.0 and later versions):</span></span>

`dotnet publish --no-dependencies`

## <a name="see-also"></a><span data-ttu-id="cdc05-209">请参阅</span><span class="sxs-lookup"><span data-stu-id="cdc05-209">See also</span></span>

- [<span data-ttu-id="cdc05-210">目标框架</span><span class="sxs-lookup"><span data-stu-id="cdc05-210">Target frameworks</span></span>](../../standard/frameworks.md)
- [<span data-ttu-id="cdc05-211">运行时标识符 (RID) 目录</span><span class="sxs-lookup"><span data-stu-id="cdc05-211">Runtime IDentifier (RID) catalog</span></span>](../rid-catalog.md)
