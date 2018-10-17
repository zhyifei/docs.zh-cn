---
title: NuGet 和.NET 库
description: 最佳实践建议打包 nuget 的.NET 库。
author: jamesnk
ms.author: mairaw
ms.date: 10/02/2018
ms.openlocfilehash: d0ea462a7f52dd9a6b2f14be9ed5770160bf66b1
ms.sourcegitcommit: e42d09e5966dd9fd02847d3e7eeb4ec0877069f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2018
ms.locfileid: "49374483"
---
# <a name="nuget"></a><span data-ttu-id="3e047-103">NuGet</span><span class="sxs-lookup"><span data-stu-id="3e047-103">NuGet</span></span>

<span data-ttu-id="3e047-104">NuGet 是.NET 生态系统的包管理器，并且是主要方法开发人员发现，并获取.NET 开放源代码库。</span><span class="sxs-lookup"><span data-stu-id="3e047-104">NuGet is a package manager for the .NET ecosystem and is the primary way developers discover and acquire .NET open-source libraries.</span></span> <span data-ttu-id="3e047-105">[NuGet.org](https://www.nuget.org/)，为托管 NuGet 包，由 Microsoft 提供的免费服务是主要主机的公共 NuGet 包，但可以发布到自定义 NuGet 服务，如[MyGet](https://www.myget.org/)和[Azure 项目](https://azure.microsoft.com/services/devops/artifacts/).</span><span class="sxs-lookup"><span data-stu-id="3e047-105">[NuGet.org](https://www.nuget.org/), a free service provided by Microsoft for hosting NuGet packages, is the primary host for public NuGet packages, but you can publish to custom NuGet services like [MyGet](https://www.myget.org/) and [Azure Artifacts](https://azure.microsoft.com/services/devops/artifacts/).</span></span>

<span data-ttu-id="3e047-106">![NuGet](./media/nuget/nuget-logo.png "NuGet")</span><span class="sxs-lookup"><span data-stu-id="3e047-106">![NuGet](./media/nuget/nuget-logo.png "NuGet")</span></span>

## <a name="create-a-nuget-package"></a><span data-ttu-id="3e047-107">创建 NuGet 包</span><span class="sxs-lookup"><span data-stu-id="3e047-107">Create a NuGet package</span></span>

<span data-ttu-id="3e047-108">NuGet 包 (`*.nupkg`) 是一个 zip 文件，其中包含.NET 程序集和关联的元数据。</span><span class="sxs-lookup"><span data-stu-id="3e047-108">A NuGet package (`*.nupkg`) is a zip file that contains .NET assemblies and associated metadata.</span></span>

<span data-ttu-id="3e047-109">有两种主要方法来创建 NuGet 包。</span><span class="sxs-lookup"><span data-stu-id="3e047-109">There are two main ways to create a NuGet package.</span></span> <span data-ttu-id="3e047-110">更新和推荐方法是从 SDK 样式项目创建包 (项目文件的内容开头`<Project Sdk="Microsoft.NET.Sdk">`)。</span><span class="sxs-lookup"><span data-stu-id="3e047-110">The newer and recommended way is to create a package from a SDK-style project (project file whose content starts with `<Project Sdk="Microsoft.NET.Sdk">`).</span></span> <span data-ttu-id="3e047-111">自动添加到包程序集和目标和剩余的元数据添加到 MSBuild 文件，如包名称和版本号码。</span><span class="sxs-lookup"><span data-stu-id="3e047-111">Assemblies and targets are automatically added to the package and remaining metadata is added to the MSBuild file, like package name and version number.</span></span> <span data-ttu-id="3e047-112">使用编译[ `dotnet pack` ](../../core/tools/dotnet-pack.md)命令输出`*.nupkg`文件而不是程序集。</span><span class="sxs-lookup"><span data-stu-id="3e047-112">Compiling with the [`dotnet pack`](../../core/tools/dotnet-pack.md) command outputs a `*.nupkg` file instead of assemblies.</span></span>

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

<span data-ttu-id="3e047-113">创建 NuGet 包的较旧的方法是使用`*.nuspec`文件和`nuget.exe`命令行工具。</span><span class="sxs-lookup"><span data-stu-id="3e047-113">The older way of creating a NuGet package is with a `*.nuspec` file and the `nuget.exe` command-line tool.</span></span> <span data-ttu-id="3e047-114">Nuspec 文件为您提供了更好地控制，但必须小心地指定要包含在最终的 NuGet 包中哪些程序集和目标。</span><span class="sxs-lookup"><span data-stu-id="3e047-114">A nuspec file gives you great control but you must carefully specify what assemblies and targets to include in the final NuGet package.</span></span> <span data-ttu-id="3e047-115">很容易犯错或其他人进行更改时，更新 nuspec 忘了。</span><span class="sxs-lookup"><span data-stu-id="3e047-115">It's easy to make a mistake or for someone to forget to update the nuspec when making changes.</span></span> <span data-ttu-id="3e047-116">Nuspec 的优点是可以使用它创建尚不支持的 SDK 样式项目文件的框架的 NuGet 包。</span><span class="sxs-lookup"><span data-stu-id="3e047-116">The advantage of a nuspec is you can use it create NuGet packages for frameworks that don't yet support an SDK-style project file.</span></span>

<span data-ttu-id="3e047-117">**请考虑 ✔️**使用 SDK 样式项目文件创建 NuGet 包。</span><span class="sxs-lookup"><span data-stu-id="3e047-117">**✔️ CONSIDER** using an SDK-style project file to create the NuGet package.</span></span>

<span data-ttu-id="3e047-118">**请考虑 ✔️**设置 SourceLink，以将源控件元数据添加到你的程序集和 NuGet 包。</span><span class="sxs-lookup"><span data-stu-id="3e047-118">**✔️ CONSIDER** setting up SourceLink to add source control metadata to your assemblies and NuGet package.</span></span>

## <a name="package-dependencies"></a><span data-ttu-id="3e047-119">包的依赖项</span><span class="sxs-lookup"><span data-stu-id="3e047-119">Package dependencies</span></span>

<span data-ttu-id="3e047-120">中详细介绍了 NuGet 包依赖项[依赖项](./dependencies.md)一文。</span><span class="sxs-lookup"><span data-stu-id="3e047-120">NuGet package dependencies are covered in detail in the [Dependencies](./dependencies.md) article.</span></span>

## <a name="important-nuget-package-metadata"></a><span data-ttu-id="3e047-121">重要的 NuGet 包元数据</span><span class="sxs-lookup"><span data-stu-id="3e047-121">Important NuGet package metadata</span></span>

<span data-ttu-id="3e047-122">NuGet 包支持许多[元数据属性](/nuget/reference/nuspec)。</span><span class="sxs-lookup"><span data-stu-id="3e047-122">A NuGet package supports many [metadata properties](/nuget/reference/nuspec).</span></span> <span data-ttu-id="3e047-123">下表包含每个开放源代码项目应提供的核心元数据：</span><span class="sxs-lookup"><span data-stu-id="3e047-123">The following table contains the core metadata that every open-source project should provide:</span></span>

| <span data-ttu-id="3e047-124">MSBuild 属性名称</span><span class="sxs-lookup"><span data-stu-id="3e047-124">MSBuild Property name</span></span>              | <span data-ttu-id="3e047-125">Nuspec 名称</span><span class="sxs-lookup"><span data-stu-id="3e047-125">Nuspec name</span></span>              | <span data-ttu-id="3e047-126">描述</span><span class="sxs-lookup"><span data-stu-id="3e047-126">Description</span></span>  |
| ---------------------------------- | ------------------------ | ------------ |
| `PackageId`                        | `id`                       | <span data-ttu-id="3e047-127">包标识符。</span><span class="sxs-lookup"><span data-stu-id="3e047-127">The package identifier.</span></span> <span data-ttu-id="3e047-128">如果满足，则可以保留与标识符的前缀[条件](/nuget/reference/id-prefix-reservation)。</span><span class="sxs-lookup"><span data-stu-id="3e047-128">A prefix from the identifier can be reserved if it meets the [criteria](/nuget/reference/id-prefix-reservation).</span></span> |
| `PackageVersion`                   | `version`                  | <span data-ttu-id="3e047-129">NuGet 包版本。</span><span class="sxs-lookup"><span data-stu-id="3e047-129">NuGet package version.</span></span> <span data-ttu-id="3e047-130">有关详细信息，请参阅[NuGet 包版本](./versioning.md#nuget-package-version)。</span><span class="sxs-lookup"><span data-stu-id="3e047-130">For more information, see [NuGet package version](./versioning.md#nuget-package-version).</span></span>             |
| `Title`                            | `title`                    | <span data-ttu-id="3e047-131">包的用户友好标题。</span><span class="sxs-lookup"><span data-stu-id="3e047-131">A human-friendly title of the package.</span></span> <span data-ttu-id="3e047-132">它将默认为`PackageId`。</span><span class="sxs-lookup"><span data-stu-id="3e047-132">It defaults to the `PackageId`.</span></span>             |
| `Description`                      | `description`              | <span data-ttu-id="3e047-133">在 UI 中显示的包的详细说明。</span><span class="sxs-lookup"><span data-stu-id="3e047-133">A long description of the package displayed in UI.</span></span>             |
| `Authors`                          | `authors`                  | <span data-ttu-id="3e047-134">逗号分隔的包创建者，匹配在 nuget.org 上的配置文件名称列表。</span><span class="sxs-lookup"><span data-stu-id="3e047-134">A comma-separated list of package authors, matching the profile names on nuget.org.</span></span>             |
| `PackageTags`                      | `tags`                     | <span data-ttu-id="3e047-135">以空格分隔的标记和描述包的关键字列表。</span><span class="sxs-lookup"><span data-stu-id="3e047-135">A space-delimited list of tags and keywords that describe the package.</span></span> <span data-ttu-id="3e047-136">搜索包时使用标记。</span><span class="sxs-lookup"><span data-stu-id="3e047-136">Tags are used when searching for packages.</span></span>             |
| `PackageIconUrl`                   | `iconUrl`                  | <span data-ttu-id="3e047-137">要用作包的图标图像 URL。</span><span class="sxs-lookup"><span data-stu-id="3e047-137">A URL for an image to use as the icon for the package.</span></span> <span data-ttu-id="3e047-138">URL 应当采用 https 格式和图像应为 64 x 64 和具有透明背景。</span><span class="sxs-lookup"><span data-stu-id="3e047-138">URL should be HTTPS and the image should be 64x64 and have a transparent background.</span></span>             |
| `PackageProjectUrl`                | `projectUrl`               | <span data-ttu-id="3e047-139">项目主页或源存储库的 URL。</span><span class="sxs-lookup"><span data-stu-id="3e047-139">A URL for the project homepage or source repository.</span></span>             |
| `PackageLicenseUrl`                | `licenseUrl`               | <span data-ttu-id="3e047-140">指向项目许可证的 URL。</span><span class="sxs-lookup"><span data-stu-id="3e047-140">A URL to the project license.</span></span> <span data-ttu-id="3e047-141">可以是指向 URL`LICENSE`在源代码管理中的文件。</span><span class="sxs-lookup"><span data-stu-id="3e047-141">Can be the URL to the `LICENSE` file in source control.</span></span>             |

<span data-ttu-id="3e047-142">**请考虑 ✔️**选择 NuGet 包名称与满足 NuGet 的前缀保留的前缀[条件](/nuget/reference/id-prefix-reservation)。</span><span class="sxs-lookup"><span data-stu-id="3e047-142">**✔️ CONSIDER** choosing a NuGet package name with a prefix that meets NuGet's prefix reservation [criteria](/nuget/reference/id-prefix-reservation).</span></span>

<span data-ttu-id="3e047-143">**请考虑 ✔️**使用`LICENSE`作为源代码管理中的文件`LicenseUrl`。</span><span class="sxs-lookup"><span data-stu-id="3e047-143">**✔️ CONSIDER** using the `LICENSE` file in source control as the `LicenseUrl`.</span></span> <span data-ttu-id="3e047-144">例如， [LICENSE.md](https://github.com/JamesNK/Newtonsoft.Json/blob/c4af75c8e91ca0d75aa6c335e8c106780c4f7712/LICENSE.md)。</span><span class="sxs-lookup"><span data-stu-id="3e047-144">For example, [LICENSE.md](https://github.com/JamesNK/Newtonsoft.Json/blob/c4af75c8e91ca0d75aa6c335e8c106780c4f7712/LICENSE.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3e047-145">一个项目没有许可证的默认值为[独占版权所有](https://choosealicense.com/no-permission/)，从而使其他人使用。</span><span class="sxs-lookup"><span data-stu-id="3e047-145">A project without a license defaults to [exclusive copyright](https://choosealicense.com/no-permission/), making it impossible for other people to use.</span></span>

<span data-ttu-id="3e047-146">**✔️ 执行**使用 HTTPS href 为您的包图标。</span><span class="sxs-lookup"><span data-stu-id="3e047-146">**✔️ DO** use an HTTPS href to your package icon.</span></span>

> <span data-ttu-id="3e047-147">NuGet.org 等网站运行与启用 HTTPS 并显示一个非 HTTPS 的图像将创建混合内容警告。</span><span class="sxs-lookup"><span data-stu-id="3e047-147">Sites like NuGet.org run with HTTPS enabled and displaying a non-HTTPS image will create a mixed content warning.</span></span>

<span data-ttu-id="3e047-148">**✔️ 执行**使用包图标图像，为 64 x 64 和具有透明背景地查看结果。</span><span class="sxs-lookup"><span data-stu-id="3e047-148">**✔️ DO** use a package icon image that is 64x64 and has a transparent background for best viewing results.</span></span>

## <a name="pre-release-packages"></a><span data-ttu-id="3e047-149">预发行包</span><span class="sxs-lookup"><span data-stu-id="3e047-149">Pre-release packages</span></span>

<span data-ttu-id="3e047-150">具有版本后缀的 NuGet 包被视为[预发行版](/nuget/create-packages/prerelease-packages)。</span><span class="sxs-lookup"><span data-stu-id="3e047-150">NuGet packages with a version suffix are considered [pre-release](/nuget/create-packages/prerelease-packages).</span></span> <span data-ttu-id="3e047-151">默认情况下，NuGet 包管理器 UI 显示稳定版本，除非用户选择在中以预发行包，使预发行包适用于受限的用户测试。</span><span class="sxs-lookup"><span data-stu-id="3e047-151">By default, the NuGet Package Manager UI shows stable releases unless a user opts-in to pre-release packages, making pre-release packages ideal for limited user testing.</span></span>

```xml
<PackageVersion>1.0.1-beta1</PackageVersion>
```

> [!NOTE]
> <span data-ttu-id="3e047-152">稳定的包不能依赖于预发行包。</span><span class="sxs-lookup"><span data-stu-id="3e047-152">A stable package cannot depend on a pre-release package.</span></span> <span data-ttu-id="3e047-153">必须使预发行版的你自己的包或依赖于较旧的稳定版本。</span><span class="sxs-lookup"><span data-stu-id="3e047-153">You must either make your own package pre-release or depend on an older stable version.</span></span>

<span data-ttu-id="3e047-154">![NuGet 预发行包依赖项](./media/nuget/nuget-prerelease-package.png "NuGet 预发行包依赖项")</span><span class="sxs-lookup"><span data-stu-id="3e047-154">![NuGet pre-release package dependency](./media/nuget/nuget-prerelease-package.png "NuGet pre-release package dependency")</span></span>

<span data-ttu-id="3e047-155">**✔️ 执行**发布时测试、 预览或试用的预发行包。</span><span class="sxs-lookup"><span data-stu-id="3e047-155">**✔️ DO** publish a pre-release package when testing, previewing, or experimenting.</span></span>

<span data-ttu-id="3e047-156">**✔️ 执行**发布稳定的包时其就绪以便其他稳定包可以引用它。</span><span class="sxs-lookup"><span data-stu-id="3e047-156">**✔️ DO** publish a stable package when its ready so other stable packages can reference it.</span></span>

## <a name="symbol-packages"></a><span data-ttu-id="3e047-157">符号包</span><span class="sxs-lookup"><span data-stu-id="3e047-157">Symbol packages</span></span>

<span data-ttu-id="3e047-158">NuGet 支持[生成单独的符号包](/nuget/create-packages/symbol-packages)包含调试 PDB 文件与主包包含.NET 程序集一起。</span><span class="sxs-lookup"><span data-stu-id="3e047-158">NuGet supports [generating a separate symbol package](/nuget/create-packages/symbol-packages) containing debug PDB files alongside the main package containing .NET assemblies.</span></span> <span data-ttu-id="3e047-159">符号包的理念是它们在符号服务器上承载，并且只会由 Visual Studio 等工具创建按需下载。</span><span class="sxs-lookup"><span data-stu-id="3e047-159">The idea of symbol packages is they're hosted on a symbol server and are only downloaded by a tool like Visual Studio on demand.</span></span>

<span data-ttu-id="3e047-160">当前符号的主要公共主机[SymbolSource](http://www.symbolsource.org/) -不支持创建可移植 Pdb 由 SDK 样式项目和符号包不是很有用。</span><span class="sxs-lookup"><span data-stu-id="3e047-160">Currently the main public host for symbols - [SymbolSource](http://www.symbolsource.org/) - doesn't support the portable PDBs created by SDK-style projects and symbol packages aren't useful.</span></span>

<span data-ttu-id="3e047-161">**请考虑 ✔️**在主要的 NuGet 包中嵌入 Pdb。</span><span class="sxs-lookup"><span data-stu-id="3e047-161">**✔️ CONSIDER** embedding PDBs in the main NuGet package.</span></span>

<span data-ttu-id="3e047-162">**请避免 ❌**创建符号包包含的 Pdb。</span><span class="sxs-lookup"><span data-stu-id="3e047-162">**❌ AVOID** creating a symbols package containing PDBs.</span></span>

>[!div class="step-by-step"]
<span data-ttu-id="3e047-163">[上一页](./strong-naming.md)
[下一页](./dependencies.md)</span><span class="sxs-lookup"><span data-stu-id="3e047-163">[Previous](./strong-naming.md)
[Next](./dependencies.md)</span></span>
