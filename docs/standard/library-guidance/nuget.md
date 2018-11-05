---
title: NuGet 和 .NET 库
description: 使用 .NET 库的 NuGet 打包的最佳实践建议。
author: jamesnk
ms.author: mairaw
ms.date: 10/02/2018
ms.openlocfilehash: 479d1786c232ef1f843877169954e847453681c9
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2018
ms.locfileid: "50185611"
---
# <a name="nuget"></a><span data-ttu-id="784f8-103">NuGet</span><span class="sxs-lookup"><span data-stu-id="784f8-103">NuGet</span></span>

<span data-ttu-id="784f8-104">NuGet 是 .NET 生态系统的包管理器，并且是开发人员用来发现并获取 .NET 开放源代码库的主要方法。</span><span class="sxs-lookup"><span data-stu-id="784f8-104">NuGet is a package manager for the .NET ecosystem and is the primary way developers discover and acquire .NET open-source libraries.</span></span> <span data-ttu-id="784f8-105">[NuGet.org](https://www.nuget.org/)（由托管 NuGet 包的 Microsoft 提供的免费服务）是公共 NuGet 包的主要主机，但可以发布到自定义 NuGet 服务，如 [MyGet](https://www.myget.org/) 和 [Azure Artifacts](https://azure.microsoft.com/services/devops/artifacts/)。</span><span class="sxs-lookup"><span data-stu-id="784f8-105">[NuGet.org](https://www.nuget.org/), a free service provided by Microsoft for hosting NuGet packages, is the primary host for public NuGet packages, but you can publish to custom NuGet services like [MyGet](https://www.myget.org/) and [Azure Artifacts](https://azure.microsoft.com/services/devops/artifacts/).</span></span>

<span data-ttu-id="784f8-106">![NuGet](./media/nuget/nuget-logo.png "NuGet")</span><span class="sxs-lookup"><span data-stu-id="784f8-106">![NuGet](./media/nuget/nuget-logo.png "NuGet")</span></span>

## <a name="create-a-nuget-package"></a><span data-ttu-id="784f8-107">创建 NuGet 包</span><span class="sxs-lookup"><span data-stu-id="784f8-107">Create a NuGet package</span></span>

<span data-ttu-id="784f8-108">NuGet 包 (`*.nupkg`) 是一个 zip 文件，其中包含 .NET 程序集和关联的元数据。</span><span class="sxs-lookup"><span data-stu-id="784f8-108">A NuGet package (`*.nupkg`) is a zip file that contains .NET assemblies and associated metadata.</span></span>

<span data-ttu-id="784f8-109">创建 NuGet 包有两种主要方式。</span><span class="sxs-lookup"><span data-stu-id="784f8-109">There are two main ways to create a NuGet package.</span></span> <span data-ttu-id="784f8-110">较新的推荐方式是从 SDK 样式项目（其内容以 `<Project Sdk="Microsoft.NET.Sdk">` 开头的项目文件）创建包。</span><span class="sxs-lookup"><span data-stu-id="784f8-110">The newer and recommended way is to create a package from a SDK-style project (project file whose content starts with `<Project Sdk="Microsoft.NET.Sdk">`).</span></span> <span data-ttu-id="784f8-111">程序集和目标会自动添加到包，剩余元数据会添加到 MSBuild 文件，如包名称和版本号。</span><span class="sxs-lookup"><span data-stu-id="784f8-111">Assemblies and targets are automatically added to the package and remaining metadata is added to the MSBuild file, like package name and version number.</span></span> <span data-ttu-id="784f8-112">使用 [`dotnet pack`](../../core/tools/dotnet-pack.md) 命令编译会输出 `*.nupkg` 文件，而不是程序集。</span><span class="sxs-lookup"><span data-stu-id="784f8-112">Compiling with the [`dotnet pack`](../../core/tools/dotnet-pack.md) command outputs a `*.nupkg` file instead of assemblies.</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <TargetFramework>netstandard2.0</TargetFramework>
    <AssemblyName>Contoso.Api</AssemblyName>
    <PackageVersion>1.1.0</PackageVersion>
    <Authors>John Doe</Authors>
  </PropertyGroup>
</Project>
```

<span data-ttu-id="784f8-113">创建 NuGet 包的较旧方式是使用 `*.nuspec` 文件和 `nuget.exe` 命令行工具。</span><span class="sxs-lookup"><span data-stu-id="784f8-113">The older way of creating a NuGet package is with a `*.nuspec` file and the `nuget.exe` command-line tool.</span></span> <span data-ttu-id="784f8-114">nuspec 文件为你提供更好的控制，但必须仔细指定要包含在最终 NuGet 包中的程序集和目标。</span><span class="sxs-lookup"><span data-stu-id="784f8-114">A nuspec file gives you great control but you must carefully specify what assemblies and targets to include in the final NuGet package.</span></span> <span data-ttu-id="784f8-115">很容易犯错或很容易忘记在发生更改时更新 nuspec。</span><span class="sxs-lookup"><span data-stu-id="784f8-115">It's easy to make a mistake or for someone to forget to update the nuspec when making changes.</span></span> <span data-ttu-id="784f8-116">nuspec 的优点是可以将其用于创建尚不支持 SDK 样式项目文件的框架的 NuGet 包。</span><span class="sxs-lookup"><span data-stu-id="784f8-116">The advantage of a nuspec is you can use it create NuGet packages for frameworks that don't yet support an SDK-style project file.</span></span>

<span data-ttu-id="784f8-117">✔️请考虑使用 SDK 样式项目文件创建 NuGet 包。</span><span class="sxs-lookup"><span data-stu-id="784f8-117">**✔️ CONSIDER** using an SDK-style project file to create the NuGet package.</span></span>

<span data-ttu-id="784f8-118">✔️请考虑设置 SourceLink 以将源代码管理元数据添加到你的程序集和 NuGet 包。</span><span class="sxs-lookup"><span data-stu-id="784f8-118">**✔️ CONSIDER** setting up SourceLink to add source control metadata to your assemblies and NuGet package.</span></span>

## <a name="package-dependencies"></a><span data-ttu-id="784f8-119">包依赖项</span><span class="sxs-lookup"><span data-stu-id="784f8-119">Package dependencies</span></span>

<span data-ttu-id="784f8-120">[依赖项](./dependencies.md)一文详细介绍了 NuGet 包依赖项。</span><span class="sxs-lookup"><span data-stu-id="784f8-120">NuGet package dependencies are covered in detail in the [Dependencies](./dependencies.md) article.</span></span>

## <a name="important-nuget-package-metadata"></a><span data-ttu-id="784f8-121">重要的 NuGet 包元数据</span><span class="sxs-lookup"><span data-stu-id="784f8-121">Important NuGet package metadata</span></span>

<span data-ttu-id="784f8-122">NuGet 包支持多个[元数据属性](/nuget/reference/nuspec)。</span><span class="sxs-lookup"><span data-stu-id="784f8-122">A NuGet package supports many [metadata properties](/nuget/reference/nuspec).</span></span> <span data-ttu-id="784f8-123">下表包含每个开放源代码项目应提供的核心元数据：</span><span class="sxs-lookup"><span data-stu-id="784f8-123">The following table contains the core metadata that every open-source project should provide:</span></span>

| <span data-ttu-id="784f8-124">MSBuild 属性名称</span><span class="sxs-lookup"><span data-stu-id="784f8-124">MSBuild Property name</span></span>              | <span data-ttu-id="784f8-125">Nuspec 名称</span><span class="sxs-lookup"><span data-stu-id="784f8-125">Nuspec name</span></span>              | <span data-ttu-id="784f8-126">描述</span><span class="sxs-lookup"><span data-stu-id="784f8-126">Description</span></span>  |
| ---------------------------------- | ------------------------ | ------------ |
| `PackageId`                        | `id`                       | <span data-ttu-id="784f8-127">包标识符。</span><span class="sxs-lookup"><span data-stu-id="784f8-127">The package identifier.</span></span> <span data-ttu-id="784f8-128">如果标识符的前缀满足[条件](/nuget/reference/id-prefix-reservation)，则可以保留该前缀。</span><span class="sxs-lookup"><span data-stu-id="784f8-128">A prefix from the identifier can be reserved if it meets the [criteria](/nuget/reference/id-prefix-reservation).</span></span> |
| `PackageVersion`                   | `version`                  | <span data-ttu-id="784f8-129">NuGet 包版本。</span><span class="sxs-lookup"><span data-stu-id="784f8-129">NuGet package version.</span></span> <span data-ttu-id="784f8-130">有关详细信息，请参阅 [NuGet 包版本](./versioning.md#nuget-package-version)。</span><span class="sxs-lookup"><span data-stu-id="784f8-130">For more information, see [NuGet package version](./versioning.md#nuget-package-version).</span></span>             |
| `Title`                            | `title`                    | <span data-ttu-id="784f8-131">明了易用的包标题。</span><span class="sxs-lookup"><span data-stu-id="784f8-131">A human-friendly title of the package.</span></span> <span data-ttu-id="784f8-132">默认为 `PackageId`。</span><span class="sxs-lookup"><span data-stu-id="784f8-132">It defaults to the `PackageId`.</span></span>             |
| `Description`                      | `description`              | <span data-ttu-id="784f8-133">UI 中显示的包的详细说明。</span><span class="sxs-lookup"><span data-stu-id="784f8-133">A long description of the package displayed in UI.</span></span>             |
| `Authors`                          | `authors`                  | <span data-ttu-id="784f8-134">包创建者的逗号分隔列表，与 nuget.org 上的配置文件名称一致。</span><span class="sxs-lookup"><span data-stu-id="784f8-134">A comma-separated list of package authors, matching the profile names on nuget.org.</span></span>             |
| `PackageTags`                      | `tags`                     | <span data-ttu-id="784f8-135">描述包的标记和关键字的空格分隔列表。</span><span class="sxs-lookup"><span data-stu-id="784f8-135">A space-delimited list of tags and keywords that describe the package.</span></span> <span data-ttu-id="784f8-136">搜索包时使用标记。</span><span class="sxs-lookup"><span data-stu-id="784f8-136">Tags are used when searching for packages.</span></span>             |
| `PackageIconUrl`                   | `iconUrl`                  | <span data-ttu-id="784f8-137">要用作包的图标的图像 URL。</span><span class="sxs-lookup"><span data-stu-id="784f8-137">A URL for an image to use as the icon for the package.</span></span> <span data-ttu-id="784f8-138">URL 应为 HTTPS，图像应为 64x64 并具有透明背景。</span><span class="sxs-lookup"><span data-stu-id="784f8-138">URL should be HTTPS and the image should be 64x64 and have a transparent background.</span></span>             |
| `PackageProjectUrl`                | `projectUrl`               | <span data-ttu-id="784f8-139">项目主页或源存储库的 URL。</span><span class="sxs-lookup"><span data-stu-id="784f8-139">A URL for the project homepage or source repository.</span></span>             |
| `PackageLicenseUrl`                | `licenseUrl`               | <span data-ttu-id="784f8-140">指向项目许可证的 URL。</span><span class="sxs-lookup"><span data-stu-id="784f8-140">A URL to the project license.</span></span> <span data-ttu-id="784f8-141">可以是指向源代码管理中的 `LICENSE` 文件的 URL。</span><span class="sxs-lookup"><span data-stu-id="784f8-141">Can be the URL to the `LICENSE` file in source control.</span></span>             |

<span data-ttu-id="784f8-142">✔️请考虑选择带有满足 NuGet 前缀保留[条件](/nuget/reference/id-prefix-reservation)的前缀的 NuGet 包名称。</span><span class="sxs-lookup"><span data-stu-id="784f8-142">**✔️ CONSIDER** choosing a NuGet package name with a prefix that meets NuGet's prefix reservation [criteria](/nuget/reference/id-prefix-reservation).</span></span>

<span data-ttu-id="784f8-143">✔️请考虑将源代码管理中的 `LICENSE` 文件用作 `LicenseUrl`。</span><span class="sxs-lookup"><span data-stu-id="784f8-143">**✔️ CONSIDER** using the `LICENSE` file in source control as the `LicenseUrl`.</span></span> <span data-ttu-id="784f8-144">例如，[LICENSE.md](https://github.com/JamesNK/Newtonsoft.Json/blob/c4af75c8e91ca0d75aa6c335e8c106780c4f7712/LICENSE.md)。</span><span class="sxs-lookup"><span data-stu-id="784f8-144">For example, [LICENSE.md](https://github.com/JamesNK/Newtonsoft.Json/blob/c4af75c8e91ca0d75aa6c335e8c106780c4f7712/LICENSE.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="784f8-145">无许可证的项目默认为 [exclusive copyright](https://choosealicense.com/no-permission/)（独占版权所有），从而无法供其他人使用。</span><span class="sxs-lookup"><span data-stu-id="784f8-145">A project without a license defaults to [exclusive copyright](https://choosealicense.com/no-permission/), making it impossible for other people to use.</span></span>

<span data-ttu-id="784f8-146">✔️ 请使用指向包图标的 HTTPS href。</span><span class="sxs-lookup"><span data-stu-id="784f8-146">**✔️ DO** use an HTTPS href to your package icon.</span></span>

> <span data-ttu-id="784f8-147">启用 HTTPS 运行并显示非 HTTPS 图像的 NuGet.org 等网站将创建混合内容警告。</span><span class="sxs-lookup"><span data-stu-id="784f8-147">Sites like NuGet.org run with HTTPS enabled and displaying a non-HTTPS image will create a mixed content warning.</span></span>

<span data-ttu-id="784f8-148">✔️请使用属于 64x64 并具有透明背景的包图标图像以获得最佳查看结果。</span><span class="sxs-lookup"><span data-stu-id="784f8-148">**✔️ DO** use a package icon image that is 64x64 and has a transparent background for best viewing results.</span></span>

## <a name="pre-release-packages"></a><span data-ttu-id="784f8-149">预发行包</span><span class="sxs-lookup"><span data-stu-id="784f8-149">Pre-release packages</span></span>

<span data-ttu-id="784f8-150">具有版本后缀的 NuGet 包被视为[预发行版](/nuget/create-packages/prerelease-packages)。</span><span class="sxs-lookup"><span data-stu-id="784f8-150">NuGet packages with a version suffix are considered [pre-release](/nuget/create-packages/prerelease-packages).</span></span> <span data-ttu-id="784f8-151">默认情况下，NuGet 包管理器 UI 显示稳定版本，除非用户选择预发行包，使预发行包适用于受限的用户测试。</span><span class="sxs-lookup"><span data-stu-id="784f8-151">By default, the NuGet Package Manager UI shows stable releases unless a user opts-in to pre-release packages, making pre-release packages ideal for limited user testing.</span></span>

```xml
<PackageVersion>1.0.1-beta1</PackageVersion>
```

> [!NOTE]
> <span data-ttu-id="784f8-152">稳定版包不能依赖于预发行包。</span><span class="sxs-lookup"><span data-stu-id="784f8-152">A stable package cannot depend on a pre-release package.</span></span> <span data-ttu-id="784f8-153">必须创建自己的预发行包或依赖于较旧的稳定版本。</span><span class="sxs-lookup"><span data-stu-id="784f8-153">You must either make your own package pre-release or depend on an older stable version.</span></span>

<span data-ttu-id="784f8-154">![NuGet 预发行包依赖项](./media/nuget/nuget-prerelease-package.png "NuGet 预发行包依赖项")</span><span class="sxs-lookup"><span data-stu-id="784f8-154">![NuGet pre-release package dependency](./media/nuget/nuget-prerelease-package.png "NuGet pre-release package dependency")</span></span>

<span data-ttu-id="784f8-155">✔️请在测试、预览或试用预发行包后进行发布。</span><span class="sxs-lookup"><span data-stu-id="784f8-155">**✔️ DO** publish a pre-release package when testing, previewing, or experimenting.</span></span>

<span data-ttu-id="784f8-156">✔️请在稳定版包就绪后进行发布，以便其他稳定版包可以引用它。</span><span class="sxs-lookup"><span data-stu-id="784f8-156">**✔️ DO** publish a stable package when its ready so other stable packages can reference it.</span></span>

## <a name="symbol-packages"></a><span data-ttu-id="784f8-157">符号包</span><span class="sxs-lookup"><span data-stu-id="784f8-157">Symbol packages</span></span>

<span data-ttu-id="784f8-158">符号文件 (`*.pdb`) 由 .NET 编译器与程序集一起生成。</span><span class="sxs-lookup"><span data-stu-id="784f8-158">Symbol files (`*.pdb`) are produced by the .NET compiler alongside assemblies.</span></span> <span data-ttu-id="784f8-159">符号文件将执行位置映射到原始源代码，以便可以逐行执行源代码（因为它使用调试程序运行）。</span><span class="sxs-lookup"><span data-stu-id="784f8-159">Symbol files map execution locations to the original source code so you can step through source code as it is running using a debugger.</span></span> <span data-ttu-id="784f8-160">NuGet 支持[生成单独的符号包](/nuget/create-packages/symbol-packages)（包含符号文件）以及主包（包含 .NET 程序集）。</span><span class="sxs-lookup"><span data-stu-id="784f8-160">NuGet supports [generating a separate symbol package](/nuget/create-packages/symbol-packages) containing symbol files alongside the main package containing .NET assemblies.</span></span> <span data-ttu-id="784f8-161">符号包的理念是它们托管在符号服务器上并仅由 Visual Studio 等工具按需下载。</span><span class="sxs-lookup"><span data-stu-id="784f8-161">The idea of symbol packages is they're hosted on a symbol server and are only downloaded by a tool like Visual Studio on demand.</span></span>

<span data-ttu-id="784f8-162">目前，符号 ([SymbolSource](http://www.symbolsource.org/)) 的主要公共主机不支持由 SDK 样式项目创建的新[可移植符号文件](https://github.com/dotnet/core/blob/master/Documentation/diagnostics/portable_pdb.md) (`*.pdb`)，并且符号包没有用处。</span><span class="sxs-lookup"><span data-stu-id="784f8-162">Currently the main public host for symbols - [SymbolSource](http://www.symbolsource.org/) - doesn't support the new [portable symbol files](https://github.com/dotnet/core/blob/master/Documentation/diagnostics/portable_pdb.md) (`*.pdb`) created by SDK-style projects, and symbol packages aren't useful.</span></span> <span data-ttu-id="784f8-163">除非符号包有推荐的主机，才能将符号文件嵌入在主 NuGet 包中。</span><span class="sxs-lookup"><span data-stu-id="784f8-163">Until there is a recommended host for symbol packages, symbol files can be embedded in the main NuGet package.</span></span> <span data-ttu-id="784f8-164">如果使用 SDK 样式项目生成 NuGet 包，则可以通过设置 `AllowedOutputExtensionsInPackageBuildOutputFolder` 属性来嵌入符号文件：</span><span class="sxs-lookup"><span data-stu-id="784f8-164">If you are building your NuGet package using an SDK-style project you can embed symbol files by setting the `AllowedOutputExtensionsInPackageBuildOutputFolder` property:</span></span> 

```xml
<Project Sdk="Microsoft.NET.Sdk">
 <PropertyGroup>
    <!-- Include symbol files (*.pdb) in the built .nupkg -->
    <AllowedOutputExtensionsInPackageBuildOutputFolder>$(AllowedOutputExtensionsInPackageBuildOutputFolder);.pdb</AllowedOutputExtensionsInPackageBuildOutputFolder>
  </PropertyGroup>
</Project>
```

<span data-ttu-id="784f8-165">✔️请考虑将符号文件嵌入在主 NuGet 包中。</span><span class="sxs-lookup"><span data-stu-id="784f8-165">**✔️ CONSIDER** embedding symbol files in the main NuGet package.</span></span>

<span data-ttu-id="784f8-166">❌请避免创建包含符号文件的符号包。</span><span class="sxs-lookup"><span data-stu-id="784f8-166">**❌ AVOID** creating a symbols package containing symbol files.</span></span>

>[!div class="step-by-step"]
<span data-ttu-id="784f8-167">[上一页](./strong-naming.md)
[下一页](./dependencies.md)</span><span class="sxs-lookup"><span data-stu-id="784f8-167">[Previous](./strong-naming.md)
[Next](./dependencies.md)</span></span>
