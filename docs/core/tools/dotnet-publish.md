---
title: dotnet publish 命令 - .NET Core CLI
description: dotnet publish 命令可将 .NET Core 项目发布到目录。
author: mairaw
ms.author: mairaw
ms.date: 03/10/2018
ms.openlocfilehash: 5e7ce5ce1240f03f53f6e120dfce53d15917425f
ms.sourcegitcommit: 77d9a94dac4c05827ed0663d95e0f9ad35d6682e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/24/2018
ms.locfileid: "34472625"
---
# <a name="dotnet-publish"></a><span data-ttu-id="9c09e-103">dotnet 发布</span><span class="sxs-lookup"><span data-stu-id="9c09e-103">dotnet publish</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="9c09e-104">name</span><span class="sxs-lookup"><span data-stu-id="9c09e-104">Name</span></span>

<span data-ttu-id="9c09e-105">`dotnet publish` - 将应用程序及其依赖项打包到文件夹以部署到托管系统。</span><span class="sxs-lookup"><span data-stu-id="9c09e-105">`dotnet publish` - Packs the application and its dependencies into a folder for deployment to a hosting system.</span></span>

## <a name="synopsis"></a><span data-ttu-id="9c09e-106">摘要</span><span class="sxs-lookup"><span data-stu-id="9c09e-106">Synopsis</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="9c09e-107">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="9c09e-107">.NET Core 2.x</span></span>](#tab/netcore2x)

```
dotnet publish [<PROJECT>] [-c|--configuration] [-f|--framework] [--force] [--manifest] [--no-dependencies] [--no-restore] [-o|--output] [-r|--runtime] [--self-contained] [-v|--verbosity] [--version-suffix]
dotnet publish [-h|--help]
```

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="9c09e-108">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="9c09e-108">.NET Core 1.x</span></span>](#tab/netcore1x)

```
dotnet publish [<PROJECT>] [-c|--configuration] [-f|--framework] [-o|--output] [-r|--runtime] [-v|--verbosity] [--version-suffix]
dotnet publish [-h|--help]
```

---

## <a name="description"></a><span data-ttu-id="9c09e-109">描述</span><span class="sxs-lookup"><span data-stu-id="9c09e-109">Description</span></span>

<span data-ttu-id="9c09e-110">`dotnet publish` 编译应用程序、读取 project 文件中指定的所有依赖项并将生成的文件集发布到目录。</span><span class="sxs-lookup"><span data-stu-id="9c09e-110">`dotnet publish` compiles the application, reads through its dependencies specified in the project file, and publishes the resulting set of files to a directory.</span></span> <span data-ttu-id="9c09e-111">输出将包含以下信息：</span><span class="sxs-lookup"><span data-stu-id="9c09e-111">The output will contain the following:</span></span>

* <span data-ttu-id="9c09e-112">扩展名为 dll 的程序集中的中间语言 (IL) 代码。</span><span class="sxs-lookup"><span data-stu-id="9c09e-112">Intermediate Language (IL) code in an assembly with a *dll* extension.</span></span>
* <span data-ttu-id="9c09e-113">包含项目所有依赖项的 .deps.json 文件。</span><span class="sxs-lookup"><span data-stu-id="9c09e-113">*.deps.json* file that contains all of the dependencies of the project.</span></span>
* <span data-ttu-id="9c09e-114">.runtime.config.json 文件，其中指定了应用程序所需的共享运行时，以及运行时的其他配置选项（例如，垃圾回收类型）。</span><span class="sxs-lookup"><span data-stu-id="9c09e-114">*.runtime.config.json* file that specifies the shared runtime that the application expects, as well as other configuration options for the runtime (for example, garbage collection type).</span></span>
* <span data-ttu-id="9c09e-115">应用程序的依赖项。</span><span class="sxs-lookup"><span data-stu-id="9c09e-115">The application's dependencies.</span></span> <span data-ttu-id="9c09e-116">将这些依赖项从 NuGet 缓存复制到输出文件夹。</span><span class="sxs-lookup"><span data-stu-id="9c09e-116">These are copied from the NuGet cache into the output folder.</span></span>

<span data-ttu-id="9c09e-117">`dotnet publish` 命令的输出已准备好部署到托管系统（例如，服务器、电脑、Mac 和笔记本电脑）以供执行，它还是准备应用程序以供部署的唯一受官方支持的方法。</span><span class="sxs-lookup"><span data-stu-id="9c09e-117">The `dotnet publish` command's output is ready for deployment to a hosting system (for example, a server, PC, Mac, laptop) for execution and is the only officially supported way to prepare the application for deployment.</span></span> <span data-ttu-id="9c09e-118">根据项目指定的部署的类型，托管系统不一定已在其上安装 .NET Core 共享运行时。</span><span class="sxs-lookup"><span data-stu-id="9c09e-118">Depending on the type of deployment that the project specifies, the hosting system may or may not have the .NET Core shared runtime installed on it.</span></span> <span data-ttu-id="9c09e-119">有关详细信息，请参阅 [.NET 核心应用程序部署](../deploying/index.md)。</span><span class="sxs-lookup"><span data-stu-id="9c09e-119">For more information, see [.NET Core Application Deployment](../deploying/index.md).</span></span> <span data-ttu-id="9c09e-120">有关已发布应用程序的目录结构，请参阅[目录结构](/aspnet/core/hosting/directory-structure)。</span><span class="sxs-lookup"><span data-stu-id="9c09e-120">For the directory structure of a published application, see [Directory structure](/aspnet/core/hosting/directory-structure).</span></span>

[!INCLUDE[dotnet restore note + options](~/includes/dotnet-restore-note-options.md)]

## <a name="arguments"></a><span data-ttu-id="9c09e-121">参数</span><span class="sxs-lookup"><span data-stu-id="9c09e-121">Arguments</span></span>

`PROJECT`

<span data-ttu-id="9c09e-122">要发布的项目，如果未指定，则默认为当前目录。</span><span class="sxs-lookup"><span data-stu-id="9c09e-122">The project to publish, which defaults to the current directory if not specified.</span></span>

## <a name="options"></a><span data-ttu-id="9c09e-123">选项</span><span class="sxs-lookup"><span data-stu-id="9c09e-123">Options</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="9c09e-124">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="9c09e-124">.NET Core 2.x</span></span>](#tab/netcore2x)

`-c|--configuration {Debug|Release}`

<span data-ttu-id="9c09e-125">定义生成配置。</span><span class="sxs-lookup"><span data-stu-id="9c09e-125">Defines the build configuration.</span></span> <span data-ttu-id="9c09e-126">默认值为 `Debug`。</span><span class="sxs-lookup"><span data-stu-id="9c09e-126">The default value is `Debug`.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="9c09e-127">为指定的[目标框架](../../standard/frameworks.md)发布应用程序。</span><span class="sxs-lookup"><span data-stu-id="9c09e-127">Publishes the application for the specified [target framework](../../standard/frameworks.md).</span></span> <span data-ttu-id="9c09e-128">必须在项目文件中指定目标框架。</span><span class="sxs-lookup"><span data-stu-id="9c09e-128">You must specify the target framework in the project file.</span></span>

`--force`

<span data-ttu-id="9c09e-129">强制解析所有依赖项，即使上次还原已成功，也不例外。</span><span class="sxs-lookup"><span data-stu-id="9c09e-129">Forces all dependencies to be resolved even if the last restore was successful.</span></span> <span data-ttu-id="9c09e-130">这相当于删除 project.assets.json 文件。</span><span class="sxs-lookup"><span data-stu-id="9c09e-130">This is equivalent to deleting the *project.assets.json* file.</span></span>

`-h|--help`

<span data-ttu-id="9c09e-131">打印出有关命令的简短帮助。</span><span class="sxs-lookup"><span data-stu-id="9c09e-131">Prints out a short help for the command.</span></span>

`--manifest <PATH_TO_MANIFEST_FILE>`

<span data-ttu-id="9c09e-132">指定一个或多个[目标清单](../deploying/runtime-store.md)，用于剪裁与应用程序一同发布的一组包。</span><span class="sxs-lookup"><span data-stu-id="9c09e-132">Specifies one or several [target manifests](../deploying/runtime-store.md) to use to trim the set of packages published with the app.</span></span> <span data-ttu-id="9c09e-133">清单文件是 [`dotnet store` 命令](dotnet-store.md)输出的一部分。</span><span class="sxs-lookup"><span data-stu-id="9c09e-133">The manifest file is part of the output of the [`dotnet store` command](dotnet-store.md).</span></span> <span data-ttu-id="9c09e-134">若要指定多个清单，请为每个清单添加一个 `--manifest` 选项。</span><span class="sxs-lookup"><span data-stu-id="9c09e-134">To specify multiple manifests, add a `--manifest` option for each manifest.</span></span> <span data-ttu-id="9c09e-135">自 .NET Core 2.0 SDK 起，可以使用此选项。</span><span class="sxs-lookup"><span data-stu-id="9c09e-135">This option is available starting with .NET Core 2.0 SDK.</span></span>

`--no-dependencies`

<span data-ttu-id="9c09e-136">忽略项目间引用，仅还原根项目。</span><span class="sxs-lookup"><span data-stu-id="9c09e-136">Ignores project-to-project references and only restores the root project.</span></span>

`--no-restore`

<span data-ttu-id="9c09e-137">运行此命令时不执行隐式还原。</span><span class="sxs-lookup"><span data-stu-id="9c09e-137">Doesn't perform an implicit restore when running the command.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="9c09e-138">指定输出目录的路径。</span><span class="sxs-lookup"><span data-stu-id="9c09e-138">Specifies the path for the output directory.</span></span> <span data-ttu-id="9c09e-139">如未指定，对于依赖于框架的部署，将默认为 ./bin/[configuration]/[framework]/publish/ 或对于独立部署，将默认为 ./bin/[configuration]/[framework]/[runtime]/publish/。</span><span class="sxs-lookup"><span data-stu-id="9c09e-139">If not specified, it defaults to *./bin/[configuration]/[framework]/publish/* for a framework-dependent deployment or *./bin/[configuration]/[framework]/[runtime]/publish/* for a self-contained deployment.</span></span>
<span data-ttu-id="9c09e-140">如果路径是相对的，则生成的输出目录与项目文件位置相关，而与当前工作目录不相关。</span><span class="sxs-lookup"><span data-stu-id="9c09e-140">If the path is relative, the output directory generated is relative to the project file location, not to the current working directory.</span></span>

`--self-contained`

<span data-ttu-id="9c09e-141">与应用程序一同发布 .NET Core 运行时，因此无需在目标计算机上安装运行时。</span><span class="sxs-lookup"><span data-stu-id="9c09e-141">Publishes the .NET Core runtime with your application so the runtime doesn't need to be installed on the target machine.</span></span> <span data-ttu-id="9c09e-142">如果指定了运行时标识符，默认值为 `true`。</span><span class="sxs-lookup"><span data-stu-id="9c09e-142">If a runtime identifier is specified, its default value is `true`.</span></span> <span data-ttu-id="9c09e-143">若要详细了解不同的部署类型，请参阅 [.NET Core 应用程序部署](../deploying/index.md)。</span><span class="sxs-lookup"><span data-stu-id="9c09e-143">For more information about the different deployment types, see [.NET Core application deployment](../deploying/index.md).</span></span>

`-r|--runtime <RUNTIME_IDENTIFIER>`

<span data-ttu-id="9c09e-144">发布针对给定运行时的应用程序。</span><span class="sxs-lookup"><span data-stu-id="9c09e-144">Publishes the application for a given runtime.</span></span> <span data-ttu-id="9c09e-145">这将在创建[独立部署 (SCD)](../deploying/index.md#self-contained-deployments-scd) 时使用。</span><span class="sxs-lookup"><span data-stu-id="9c09e-145">This is used when creating a [self-contained deployment (SCD)](../deploying/index.md#self-contained-deployments-scd).</span></span> <span data-ttu-id="9c09e-146">有关运行时标识符 (RID) 的列表，请参阅 [RID 目录](../rid-catalog.md)。</span><span class="sxs-lookup"><span data-stu-id="9c09e-146">For a list of Runtime Identifiers (RIDs), see the [RID catalog](../rid-catalog.md).</span></span> <span data-ttu-id="9c09e-147">默认为发布[依赖于框架的部署 (FDD)](../deploying/index.md#framework-dependent-deployments-fdd)。</span><span class="sxs-lookup"><span data-stu-id="9c09e-147">Default is to publish a [framework-dependent deployment (FDD)](../deploying/index.md#framework-dependent-deployments-fdd).</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="9c09e-148">设置命令的详细级别。</span><span class="sxs-lookup"><span data-stu-id="9c09e-148">Sets the verbosity level of the command.</span></span> <span data-ttu-id="9c09e-149">允许使用的值为 `q[uiet]`、`m[inimal]`、`n[ormal]`、`d[etailed]` 和 `diag[nostic]`。</span><span class="sxs-lookup"><span data-stu-id="9c09e-149">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

`--version-suffix <VERSION_SUFFIX>`

<span data-ttu-id="9c09e-150">定义版本后缀来替换项目文件的版本字段中的星号 (`*`)。</span><span class="sxs-lookup"><span data-stu-id="9c09e-150">Defines the version suffix to replace the asterisk (`*`) in the version field of the project file.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="9c09e-151">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="9c09e-151">.NET Core 1.x</span></span>](#tab/netcore1x)

`-c|--configuration {Debug|Release}`

<span data-ttu-id="9c09e-152">定义生成配置。</span><span class="sxs-lookup"><span data-stu-id="9c09e-152">Defines the build configuration.</span></span> <span data-ttu-id="9c09e-153">默认值为 `Debug`。</span><span class="sxs-lookup"><span data-stu-id="9c09e-153">The default value is `Debug`.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="9c09e-154">为指定的[目标框架](../../standard/frameworks.md)发布应用程序。</span><span class="sxs-lookup"><span data-stu-id="9c09e-154">Publishes the application for the specified [target framework](../../standard/frameworks.md).</span></span> <span data-ttu-id="9c09e-155">必须在项目文件中指定目标框架。</span><span class="sxs-lookup"><span data-stu-id="9c09e-155">You must specify the target framework in the project file.</span></span>

`-h|--help`

<span data-ttu-id="9c09e-156">打印出有关命令的简短帮助。</span><span class="sxs-lookup"><span data-stu-id="9c09e-156">Prints out a short help for the command.</span></span>

`--manifest <PATH_TO_MANIFEST_FILE>`

<span data-ttu-id="9c09e-157">指定一个或多个[目标清单](../deploying/runtime-store.md)，用于剪裁与应用程序一同发布的一组包。</span><span class="sxs-lookup"><span data-stu-id="9c09e-157">Specifies one or several [target manifests](../deploying/runtime-store.md) to use to trim the set of packages published with the app.</span></span> <span data-ttu-id="9c09e-158">清单文件是 [`dotnet store` 命令](dotnet-store.md)输出的一部分。</span><span class="sxs-lookup"><span data-stu-id="9c09e-158">The manifest file is part of the output of the [`dotnet store` command](dotnet-store.md).</span></span> <span data-ttu-id="9c09e-159">若要指定多个清单，请为每个清单添加一个 `--manifest` 选项。</span><span class="sxs-lookup"><span data-stu-id="9c09e-159">To specify multiple manifests, add a `--manifest` option for each manifest.</span></span> <span data-ttu-id="9c09e-160">自 .NET Core 2.0 SDK 起，可以使用此选项。</span><span class="sxs-lookup"><span data-stu-id="9c09e-160">This option is available starting with .NET Core 2.0 SDK.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="9c09e-161">指定输出目录的路径。</span><span class="sxs-lookup"><span data-stu-id="9c09e-161">Specifies the path for the output directory.</span></span> <span data-ttu-id="9c09e-162">如未指定，对于依赖于框架的部署，将默认为 ./bin/[configuration]/[framework]/publish/ 或对于独立部署，将默认为 ./bin/[configuration]/[framework]/[runtime]/publish/。</span><span class="sxs-lookup"><span data-stu-id="9c09e-162">If not specified, it defaults to *./bin/[configuration]/[framework]/publish/* for a framework-dependent deployment or *./bin/[configuration]/[framework]/[runtime]/publish/* for a self-contained deployment.</span></span>
<span data-ttu-id="9c09e-163">如果路径是相对的，则生成的输出目录与项目文件位置相关，而与当前工作目录不相关。</span><span class="sxs-lookup"><span data-stu-id="9c09e-163">If the path is relative, the output directory generated is relative to the project file location, not to the current working directory.</span></span>

`-r|--runtime <RUNTIME_IDENTIFIER>`

<span data-ttu-id="9c09e-164">发布针对给定运行时的应用程序。</span><span class="sxs-lookup"><span data-stu-id="9c09e-164">Publishes the application for a given runtime.</span></span> <span data-ttu-id="9c09e-165">这将在创建[独立部署 (SCD)](../deploying/index.md#self-contained-deployments-scd) 时使用。</span><span class="sxs-lookup"><span data-stu-id="9c09e-165">This is used when creating a [self-contained deployment (SCD)](../deploying/index.md#self-contained-deployments-scd).</span></span> <span data-ttu-id="9c09e-166">有关运行时标识符 (RID) 的列表，请参阅 [RID 目录](../rid-catalog.md)。</span><span class="sxs-lookup"><span data-stu-id="9c09e-166">For a list of Runtime Identifiers (RIDs), see the [RID catalog](../rid-catalog.md).</span></span> <span data-ttu-id="9c09e-167">默认为发布[依赖于框架的部署 (FDD)](../deploying/index.md#framework-dependent-deployments-fdd)。</span><span class="sxs-lookup"><span data-stu-id="9c09e-167">Default is to publish a [framework-dependent deployment (FDD)](../deploying/index.md#framework-dependent-deployments-fdd).</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="9c09e-168">设置命令的详细级别。</span><span class="sxs-lookup"><span data-stu-id="9c09e-168">Sets the verbosity level of the command.</span></span> <span data-ttu-id="9c09e-169">允许使用的值为 `q[uiet]`、`m[inimal]`、`n[ormal]`、`d[etailed]` 和 `diag[nostic]`。</span><span class="sxs-lookup"><span data-stu-id="9c09e-169">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

`--version-suffix <VERSION_SUFFIX>`

<span data-ttu-id="9c09e-170">定义版本后缀来替换项目文件的版本字段中的星号 (`*`)。</span><span class="sxs-lookup"><span data-stu-id="9c09e-170">Defines the version suffix to replace the asterisk (`*`) in the version field of the project file.</span></span>

---

## <a name="examples"></a><span data-ttu-id="9c09e-171">示例</span><span class="sxs-lookup"><span data-stu-id="9c09e-171">Examples</span></span>

<span data-ttu-id="9c09e-172">在当前目录中发布项目：</span><span class="sxs-lookup"><span data-stu-id="9c09e-172">Publish the project in the current directory:</span></span>

`dotnet publish`

<span data-ttu-id="9c09e-173">使用指定的项目文件发布应用程序：</span><span class="sxs-lookup"><span data-stu-id="9c09e-173">Publish the application using the specified project file:</span></span>

`dotnet publish ~/projects/app1/app1.csproj`

<span data-ttu-id="9c09e-174">使用 `netcoreapp1.1` 框架发布当前目录中的项目：</span><span class="sxs-lookup"><span data-stu-id="9c09e-174">Publish the project in the current directory using the `netcoreapp1.1` framework:</span></span>

`dotnet publish --framework netcoreapp1.1`

<span data-ttu-id="9c09e-175">使用 `netcoreapp1.1` 框架和 `OS X 10.10` 的运行时发布当前应用程序（必须在项目文件中列出此 RID）。</span><span class="sxs-lookup"><span data-stu-id="9c09e-175">Publish the current application using the `netcoreapp1.1` framework and the runtime for `OS X 10.10` (you must list this RID in the project file).</span></span>

`dotnet publish --framework netcoreapp1.1 --runtime osx.10.11-x64`

<span data-ttu-id="9c09e-176">发布当前应用程序，但在还原操作期间不还原项目到项目 (P2P) 引用，只还原根项目（.NET Core SDK 2.0 及更高版本）：</span><span class="sxs-lookup"><span data-stu-id="9c09e-176">Publish the current application but don't restore project-to-project (P2P) references, just the root project during the restore operation (.NET Core SDK 2.0 and later versions):</span></span>

`dotnet publish --no-dependencies`

## <a name="see-also"></a><span data-ttu-id="9c09e-177">请参阅</span><span class="sxs-lookup"><span data-stu-id="9c09e-177">See also</span></span>

* [<span data-ttu-id="9c09e-178">目标框架</span><span class="sxs-lookup"><span data-stu-id="9c09e-178">Target frameworks</span></span>](../../standard/frameworks.md)
* [<span data-ttu-id="9c09e-179">运行时标识符 (RID) 目录</span><span class="sxs-lookup"><span data-stu-id="9c09e-179">Runtime IDentifier (RID) catalog</span></span>](../rid-catalog.md)
