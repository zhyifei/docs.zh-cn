---
title: .NET Core 的 csproj 格式的新增内容
description: 了解现有文件和 .NET Core csproj 文件之间的区别
ms.date: 04/08/2019
ms.openlocfilehash: 89f0bbab1f9887295a68ffc6434340f1c6f10d5d
ms.sourcegitcommit: 438919211260bb415fc8f96ca3eabc33cf2d681d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2019
ms.locfileid: "59611089"
---
# <a name="additions-to-the-csproj-format-for-net-core"></a><span data-ttu-id="29d79-103">.NET Core 的 csproj 格式的新增内容</span><span class="sxs-lookup"><span data-stu-id="29d79-103">Additions to the csproj format for .NET Core</span></span>

<span data-ttu-id="29d79-104">本文档概述了作为从 *project.json* 移动到 *csproj* 和 [MSBuild](https://github.com/Microsoft/MSBuild) 的一部分，添加到项目文件的更改。</span><span class="sxs-lookup"><span data-stu-id="29d79-104">This document outlines the changes that were added to the project files as part of the move from *project.json* to *csproj* and [MSBuild](https://github.com/Microsoft/MSBuild).</span></span> <span data-ttu-id="29d79-105">有关常规项目文件的语法和引用的详细信息，请参阅 [MSBuild 项目文件](/visualstudio/msbuild/msbuild-project-file-schema-reference)文档。</span><span class="sxs-lookup"><span data-stu-id="29d79-105">For more information about general project file syntax and reference, see [the MSBuild project file](/visualstudio/msbuild/msbuild-project-file-schema-reference) documentation.</span></span>

## <a name="implicit-package-references"></a><span data-ttu-id="29d79-106">隐式包引用</span><span class="sxs-lookup"><span data-stu-id="29d79-106">Implicit package references</span></span>

<span data-ttu-id="29d79-107">基于项目文件的 `<TargetFramework>` 或 `<TargetFrameworks>` 属性中指定的目标框架对元包进行隐式引用。</span><span class="sxs-lookup"><span data-stu-id="29d79-107">Metapackages are implicitly referenced based on the target framework(s) specified in the `<TargetFramework>` or `<TargetFrameworks>` property of your project file.</span></span> <span data-ttu-id="29d79-108">如果指定了 `<TargetFramework>`，则忽略 `<TargetFrameworks>`，而与顺序无关。</span><span class="sxs-lookup"><span data-stu-id="29d79-108">`<TargetFrameworks>` is ignored if `<TargetFramework>` is specified, independent of order.</span></span> <span data-ttu-id="29d79-109">有关详细信息，请参阅[包、元包和框架](../packages.md)。</span><span class="sxs-lookup"><span data-stu-id="29d79-109">For more information, see [Packages, metapackages and frameworks](../packages.md).</span></span> 

```xml
 <PropertyGroup>
   <TargetFramework>netcoreapp2.1</TargetFramework>
 </PropertyGroup>
 ```

 ```xml
 <PropertyGroup>
   <TargetFrameworks>netcoreapp2.1;net462</TargetFrameworks>
 </PropertyGroup>
 ```

### <a name="recommendations"></a><span data-ttu-id="29d79-110">建议</span><span class="sxs-lookup"><span data-stu-id="29d79-110">Recommendations</span></span>

<span data-ttu-id="29d79-111">由于隐式引用了 `Microsoft.NETCore.App` 或 `NETStandard.Library` 元包，以下是建议的最佳做法：</span><span class="sxs-lookup"><span data-stu-id="29d79-111">Since `Microsoft.NETCore.App` or `NETStandard.Library` metapackages are implicitly referenced, the following are our recommended best practices:</span></span>

* <span data-ttu-id="29d79-112">面向 .NET Core 或 .NET Standard 时，绝不通过项目文件中的 `<PackageReference>` 项，对 `Microsoft.NETCore.App` 或 `NETStandard.Library` 元包进行显式引用。</span><span class="sxs-lookup"><span data-stu-id="29d79-112">When targeting .NET Core or .NET Standard, never have an explicit reference to the `Microsoft.NETCore.App` or `NETStandard.Library` metapackages via a `<PackageReference>` item in your project file.</span></span>
* <span data-ttu-id="29d79-113">面向 .NET Core 时，如果需要特定版本的运行时，应使用项目中的 `<RuntimeFrameworkVersion>` 属性（例如，`1.0.4`），而不是引用元包。</span><span class="sxs-lookup"><span data-stu-id="29d79-113">If you need a specific version of the runtime when targeting .NET Core, you should use the `<RuntimeFrameworkVersion>` property in your project (for example, `1.0.4`) instead of referencing the metapackage.</span></span>
  * <span data-ttu-id="29d79-114">例如，如果使用[独立部署](../deploying/index.md#self-contained-deployments-scd)且需要 1.0.0 LTS 运行时的特定修补程序版本，可能会发生这种情况。</span><span class="sxs-lookup"><span data-stu-id="29d79-114">This might happen if you are using [self-contained deployments](../deploying/index.md#self-contained-deployments-scd) and you need a specific patch version of 1.0.0 LTS runtime, for example.</span></span>
* <span data-ttu-id="29d79-115">面向 .NET Standard 时，如果需要特定版本的 `NETStandard.Library` 元包，可以使用 `<NetStandardImplicitPackageVersion>` 属性并设置所需版本。</span><span class="sxs-lookup"><span data-stu-id="29d79-115">If you need a specific version of the `NETStandard.Library` metapackage when targeting .NET Standard, you can use the `<NetStandardImplicitPackageVersion>` property and set the version you need.</span></span>
* <span data-ttu-id="29d79-116">请勿在 .NET Framework 项目中显式添加或更新对 `Microsoft.NETCore.App` 或 `NETStandard.Library` 元包的引用。</span><span class="sxs-lookup"><span data-stu-id="29d79-116">Don't explicitly add or update references to either the `Microsoft.NETCore.App` or `NETStandard.Library` metapackage in .NET Framework projects.</span></span> <span data-ttu-id="29d79-117">使用基于 .NET Standard 的 NuGet 包时，如果需要任意版本的 `NETStandard.Library`，NuGet 可自动安装该版本。</span><span class="sxs-lookup"><span data-stu-id="29d79-117">If any version of `NETStandard.Library` is needed when using a .NET Standard-based NuGet package, NuGet automatically installs that version.</span></span>

## <a name="implicit-version-for-some-package-references"></a><span data-ttu-id="29d79-118">一些包引用的隐式版本</span><span class="sxs-lookup"><span data-stu-id="29d79-118">Implicit version for some package references</span></span>

<span data-ttu-id="29d79-119">[`<PackageReference>`](#packagereference) 的大多数用法都要求设置 `Version` 属性，用于指定要使用的 NuGet 包版本。</span><span class="sxs-lookup"><span data-stu-id="29d79-119">Most usages of [`<PackageReference>`](#packagereference) require setting the `Version` attribute to specify the NuGet package version to be used.</span></span> <span data-ttu-id="29d79-120">不过，如果使用的是 .NET Core 2.1 或 2.2，且引用 [Microsoft.AspNetCore.App](/aspnet/core/fundamentals/metapackage-app) 或 [Microsoft.AspNetCore.All](/aspnet/core/fundamentals/metapackage)，就没有必要设置此属性。</span><span class="sxs-lookup"><span data-stu-id="29d79-120">When using .NET Core 2.1 or 2.2 and referencing [Microsoft.AspNetCore.App](/aspnet/core/fundamentals/metapackage-app) or [Microsoft.AspNetCore.All](/aspnet/core/fundamentals/metapackage), however, the  attribute is unnecessary.</span></span> <span data-ttu-id="29d79-121">.NET Core SDK 可自动选择应使用的包版本。</span><span class="sxs-lookup"><span data-stu-id="29d79-121">The .NET Core SDK can automatically select the version of these packages that should be used.</span></span>

### <a name="recommendation"></a><span data-ttu-id="29d79-122">建议</span><span class="sxs-lookup"><span data-stu-id="29d79-122">Recommendation</span></span>

<span data-ttu-id="29d79-123">引用 `Microsoft.AspNetCore.App` 或 `Microsoft.AspNetCore.All` 包时，不要指定包版本。</span><span class="sxs-lookup"><span data-stu-id="29d79-123">When referencing the `Microsoft.AspNetCore.App` or `Microsoft.AspNetCore.All` packages, do not specify their version.</span></span> <span data-ttu-id="29d79-124">如果你指定版本，SDK 可能会生成警告 NETSDK1071。</span><span class="sxs-lookup"><span data-stu-id="29d79-124">If a version is specified, the SDK may produce warning NETSDK1071.</span></span> <span data-ttu-id="29d79-125">若要修复此警告，请删除包版本，如下面的示例所示：</span><span class="sxs-lookup"><span data-stu-id="29d79-125">To fix this warning, remove the package version like in the following example:</span></span>

```xml
<ItemGroup>
  <PackageReference Include="Microsoft.AspNetCore.App" />
</ItemGroup>
```

> <span data-ttu-id="29d79-126">已知问题：.NET Core 2.1 SDK 只在项目还使用 Microsoft.NET.Sdk.Web 时才支持这种语法。</span><span class="sxs-lookup"><span data-stu-id="29d79-126">Known issue: the .NET Core 2.1 SDK only supported this syntax when the project also uses Microsoft.NET.Sdk.Web.</span></span> <span data-ttu-id="29d79-127">.NET Core 2.2 SDK 中解决了此问题。</span><span class="sxs-lookup"><span data-stu-id="29d79-127">This is resolved in the .NET Core 2.2 SDK.</span></span>

<span data-ttu-id="29d79-128">这些对 ASP.NET Core 元包的引用行为与大多数普通 NuGet 包略有不同。</span><span class="sxs-lookup"><span data-stu-id="29d79-128">These references to ASP.NET Core metapackages have a slightly different behavior from most normal NuGet packages.</span></span> <span data-ttu-id="29d79-129">使用这些元包的应用的[框架依赖部署](../deploying/index.md#framework-dependent-deployments-fdd)自动使用 ASP.NET Core 共享框架。</span><span class="sxs-lookup"><span data-stu-id="29d79-129">[Framework-dependent deployments](../deploying/index.md#framework-dependent-deployments-fdd) of applications that use these metapackages automatically take advantage of the ASP.NET Core shared framework.</span></span> <span data-ttu-id="29d79-130">使用元包时，引用的 ASP.NET Core NuGet 包中的任何资产都不会与应用一起部署。也就是说，ASP.NET Core 共享框架包含这些资产。</span><span class="sxs-lookup"><span data-stu-id="29d79-130">When you use the metapackages, **no** assets from the referenced ASP.NET Core NuGet packages are deployed with the application—the ASP.NET Core shared framework contains these assets.</span></span> <span data-ttu-id="29d79-131">共享框架中的资产更适合目标平台，旨在缩短应用启动时间。</span><span class="sxs-lookup"><span data-stu-id="29d79-131">The assets in the shared framework are optimized for the target platform to improve application startup time.</span></span> <span data-ttu-id="29d79-132">若要详细了解共享框架，请参阅 [.NET Core 分发打包](../build/distribution-packaging.md)。</span><span class="sxs-lookup"><span data-stu-id="29d79-132">For more information about shared framework, see [.NET Core distribution packaging](../build/distribution-packaging.md).</span></span>

<span data-ttu-id="29d79-133">如果指定版本，这会被视为框架依赖部署的 ASP.NET Core 共享框架的最低版本，并被视为独立式部署的确切版本。</span><span class="sxs-lookup"><span data-stu-id="29d79-133">If a version *is* specified, it's treated as the *minimum* version of ASP.NET Core shared framework for framework-dependent deployments and as an *exact* version for self-contained deployments.</span></span> <span data-ttu-id="29d79-134">这可能会导致以下后果：</span><span class="sxs-lookup"><span data-stu-id="29d79-134">This can have the following consequences:</span></span>

* <span data-ttu-id="29d79-135">如果服务器上安装的 ASP.NET Core 版本低于 PackageReference 中指定的版本，.NET Core 进程便会无法启动。</span><span class="sxs-lookup"><span data-stu-id="29d79-135">If the version of ASP.NET Core installed on the server is less than the version specified on the PackageReference, the .NET Core process fails to launch.</span></span> <span data-ttu-id="29d79-136">元包更新通常先可用于 NuGet.org，再可用于托管环境（如 Azure）。</span><span class="sxs-lookup"><span data-stu-id="29d79-136">Updates to the metapackage are often available on NuGet.org before updates have been made available in hosting environments such as Azure.</span></span> <span data-ttu-id="29d79-137">将 PackageReference 中的版本更新为 ASP.NET Core 可能会导致部署的应用失败。</span><span class="sxs-lookup"><span data-stu-id="29d79-137">Updating the version on the PackageReference to ASP.NET Core could cause a deployed application to fail.</span></span>
* <span data-ttu-id="29d79-138">如果应用部署为[独立式部署](../deploying/index.md#self-contained-deployments-scd)，应用可能不包含 .NET Core 的最新安全更新程序。</span><span class="sxs-lookup"><span data-stu-id="29d79-138">If the application is deployed as a [self-contained deployment](../deploying/index.md#self-contained-deployments-scd), the application may not contain the latest security updates to .NET Core.</span></span> <span data-ttu-id="29d79-139">如果未指定版本，SDK 可以自动在独立式部署中包含 ASP.NET Core 的最新版本。</span><span class="sxs-lookup"><span data-stu-id="29d79-139">When a version isn't specified, the SDK can automatically include the newest version of ASP.NET Core in the self-contained deployment.</span></span>

## <a name="default-compilation-includes-in-net-core-projects"></a><span data-ttu-id="29d79-140">.NET Core 项目中默认包含的编译项</span><span class="sxs-lookup"><span data-stu-id="29d79-140">Default compilation includes in .NET Core projects</span></span>

<span data-ttu-id="29d79-141">已通过移动到最新 SDK 版本中的 *csproj* 格式，将默认的编译项和嵌入资源的包含项和排除项移至 SDK 属性文件。</span><span class="sxs-lookup"><span data-stu-id="29d79-141">With the move to the *csproj* format in the latest SDK versions, we've moved the default includes and excludes for compile items and embedded resources to the SDK properties files.</span></span> <span data-ttu-id="29d79-142">这意味着不需要再在项目文件中指定这些项。</span><span class="sxs-lookup"><span data-stu-id="29d79-142">This means that you no longer need to specify these items in your project file.</span></span>

<span data-ttu-id="29d79-143">执行此操作的主要目的是减少项目文件中的混杂。</span><span class="sxs-lookup"><span data-stu-id="29d79-143">The main reason for doing this is to reduce the clutter in your project file.</span></span> <span data-ttu-id="29d79-144">SDK 中的默认设置应涵盖最常见的用例，由此便无需在创建的每个项目中重复这些设置。</span><span class="sxs-lookup"><span data-stu-id="29d79-144">The defaults that are present in the SDK should cover most common use cases, so there is no need to repeat them in every project that you create.</span></span> <span data-ttu-id="29d79-145">这可使项目文件更小，更易于理解和进行手动编辑（如果需要）。</span><span class="sxs-lookup"><span data-stu-id="29d79-145">This leads to smaller project files that are much easier to understand as well as edit by hand, if needed.</span></span>

<span data-ttu-id="29d79-146">下表显示同时在 SDK 中包含和排除的元素和 [globs](https://en.wikipedia.org/wiki/Glob_(programming))：</span><span class="sxs-lookup"><span data-stu-id="29d79-146">The following table shows which element and which [globs](https://en.wikipedia.org/wiki/Glob_(programming)) are both included and excluded in the SDK:</span></span>

| <span data-ttu-id="29d79-147">元素</span><span class="sxs-lookup"><span data-stu-id="29d79-147">Element</span></span>           | <span data-ttu-id="29d79-148">包含 glob</span><span class="sxs-lookup"><span data-stu-id="29d79-148">Include glob</span></span>                              | <span data-ttu-id="29d79-149">排除 glob</span><span class="sxs-lookup"><span data-stu-id="29d79-149">Exclude glob</span></span>                                                  | <span data-ttu-id="29d79-150">删除 glob</span><span class="sxs-lookup"><span data-stu-id="29d79-150">Remove glob</span></span>              |
|-------------------|-------------------------------------------|---------------------------------------------------------------|----------------------------|
| <span data-ttu-id="29d79-151">Compile</span><span class="sxs-lookup"><span data-stu-id="29d79-151">Compile</span></span>           | <span data-ttu-id="29d79-152">\*\*/\*.cs（或其他语言扩展名）</span><span class="sxs-lookup"><span data-stu-id="29d79-152">\*\*/\*.cs (or other language extensions)</span></span> | <span data-ttu-id="29d79-153">\*\*/\*.user;  \*\*/\*.\*proj;  \*\*/\*.sln;  \*\*/\*.vssscc</span><span class="sxs-lookup"><span data-stu-id="29d79-153">\*\*/\*.user;  \*\*/\*.\*proj;  \*\*/\*.sln;  \*\*/\*.vssscc</span></span>  | <span data-ttu-id="29d79-154">不可用</span><span class="sxs-lookup"><span data-stu-id="29d79-154">N/A</span></span>                      |
| <span data-ttu-id="29d79-155">EmbeddedResource</span><span class="sxs-lookup"><span data-stu-id="29d79-155">EmbeddedResource</span></span>  | <span data-ttu-id="29d79-156">\*\*/\*.resx</span><span class="sxs-lookup"><span data-stu-id="29d79-156">\*\*/\*.resx</span></span>                              | <span data-ttu-id="29d79-157">\*\*/\*.user; \*\*/\*.\*proj; \*\*/\*.sln; \*\*/\*.vssscc</span><span class="sxs-lookup"><span data-stu-id="29d79-157">\*\*/\*.user; \*\*/\*.\*proj; \*\*/\*.sln; \*\*/\*.vssscc</span></span>     | <span data-ttu-id="29d79-158">不可用</span><span class="sxs-lookup"><span data-stu-id="29d79-158">N/A</span></span>                      |
| <span data-ttu-id="29d79-159">None</span><span class="sxs-lookup"><span data-stu-id="29d79-159">None</span></span>              | \*\*/\*                                   | <span data-ttu-id="29d79-160">\*\*/\*.user; \*\*/\*.\*proj; \*\*/\*.sln; \*\*/\*.vssscc</span><span class="sxs-lookup"><span data-stu-id="29d79-160">\*\*/\*.user; \*\*/\*.\*proj; \*\*/\*.sln; \*\*/\*.vssscc</span></span>     | <span data-ttu-id="29d79-161">\*\*/\*.cs; \*\*/\*.resx</span><span class="sxs-lookup"><span data-stu-id="29d79-161">\*\*/\*.cs; \*\*/\*.resx</span></span>   |

> [!NOTE]
> <span data-ttu-id="29d79-162">排除 glob 始终排除 `./bin` 和 `./obj` 文件夹，它们分别由 MSBuild 属性 `$(BaseOutputPath)` 和 `$(BaseIntermediateOutputPath)` 表示。</span><span class="sxs-lookup"><span data-stu-id="29d79-162">**Exclude glob** always excludes the `./bin` and `./obj` folders, which are represented by the `$(BaseOutputPath)` and `$(BaseIntermediateOutputPath)` MSBuild properties, respectively.</span></span> <span data-ttu-id="29d79-163">总体上来说，所有排除都由 `$(DefaultItemExcludes)` 表示。</span><span class="sxs-lookup"><span data-stu-id="29d79-163">As a whole, all excludes are represented by `$(DefaultItemExcludes)`.</span></span>

<span data-ttu-id="29d79-164">如果项目中有 glob，却又尝试使用最新的 SDK 生成它，则将收到以下错误：</span><span class="sxs-lookup"><span data-stu-id="29d79-164">If you have globs in your project and you try to build it using the newest SDK, you'll get the following error:</span></span>

> <span data-ttu-id="29d79-165">包含重复的编译项。</span><span class="sxs-lookup"><span data-stu-id="29d79-165">Duplicate Compile items were included.</span></span> <span data-ttu-id="29d79-166">默认情况下，.NET SDK 包括项目目录中的编译项。</span><span class="sxs-lookup"><span data-stu-id="29d79-166">The .NET SDK includes Compile items from your project directory by default.</span></span> <span data-ttu-id="29d79-167">可从项目文件中删除这些项，或如果想要在项目文件中显式包括它们，则将“EnableDefaultCompileItems”属性设为“false”。</span><span class="sxs-lookup"><span data-stu-id="29d79-167">You can either remove these items from your project file, or set the 'EnableDefaultCompileItems' property to 'false' if you want to explicitly include them in your project file.</span></span>

<span data-ttu-id="29d79-168">要解决此错误，可以删除与前表中所列项匹配的显式 `Compile` 项，也可以将 `<EnableDefaultCompileItems>` 属性设置为 `false`，如下所示：</span><span class="sxs-lookup"><span data-stu-id="29d79-168">In order to get around this error, you can either remove the explicit `Compile` items that match the ones listed on the previous table, or you can set the `<EnableDefaultCompileItems>` property to `false`, like this:</span></span>

```xml
<PropertyGroup>
    <EnableDefaultCompileItems>false</EnableDefaultCompileItems>
</PropertyGroup>
```

<span data-ttu-id="29d79-169">将此属性设置为 `false` 将禁用隐式包含，并还原到以前 SDK 的行为，在这种情况下，必须在项目中指定默认 glob。</span><span class="sxs-lookup"><span data-stu-id="29d79-169">Setting this property to `false` will disable implicit inclusion, reverting to the behavior of previous SDKs where you had to specify the default globs in your project.</span></span>

<span data-ttu-id="29d79-170">此更改不会修改其他包含项的主要机制。</span><span class="sxs-lookup"><span data-stu-id="29d79-170">This change does not modify the main mechanics of other includes.</span></span> <span data-ttu-id="29d79-171">但是，如果要指定（例如，指定某些文件通过应用发布），仍可以使用 *csproj* 中相应的已知机制来实现（例如，`<Content>` 元素）。</span><span class="sxs-lookup"><span data-stu-id="29d79-171">However, if you wish to specify, for example, some files to get published with your app, you can still use the known mechanisms in *csproj* for that (for example, the `<Content>` element).</span></span>

<span data-ttu-id="29d79-172">`<EnableDefaultCompileItems>` 仅禁用 `Compile` glob，但不会影响其他 glob（如隐式 `None` glob），这也适用于 \*.cs 项。</span><span class="sxs-lookup"><span data-stu-id="29d79-172">`<EnableDefaultCompileItems>` only disables `Compile` globs but doesn't affect other globs, like the implicit `None` glob, which also applies to \*.cs items.</span></span> <span data-ttu-id="29d79-173">因此，解决方案资源管理器继续显示在项目中作为 `None` 项的 \*.cs 项。</span><span class="sxs-lookup"><span data-stu-id="29d79-173">Because of that, **Solution Explorer** will continue show \*.cs items as part of the project, included as `None` items.</span></span> <span data-ttu-id="29d79-174">以类似的方式，可以将 `<EnableDefaultNoneItems>` 设置为 false 以禁用隐式 `None` glob，如下所示：</span><span class="sxs-lookup"><span data-stu-id="29d79-174">In a similar way, you can set `<EnableDefaultNoneItems>` to false to disable the implicit `None` glob, like this:</span></span>

```xml
<PropertyGroup>
    <EnableDefaultNoneItems>false</EnableDefaultNoneItems>
</PropertyGroup>
```

<span data-ttu-id="29d79-175">要禁用所有隐式 glob，可将 `<EnableDefaultItems>` 属性设置为 `false`，如以下示例所示：</span><span class="sxs-lookup"><span data-stu-id="29d79-175">To disable **all implicit globs**, you can set the `<EnableDefaultItems>` property to `false` as in the following example:</span></span>

```xml
<PropertyGroup>
    <EnableDefaultItems>false</EnableDefaultItems>
</PropertyGroup>
```

## <a name="how-to-see-the-whole-project-as-msbuild-sees-it"></a><span data-ttu-id="29d79-176">如何像 MSBuild 一样查看整个项目</span><span class="sxs-lookup"><span data-stu-id="29d79-176">How to see the whole project as MSBuild sees it</span></span>

<span data-ttu-id="29d79-177">虽然这些 csproj 更改极大地简化了项目文件，但建议查看完全展开的项目，就像 MSBuild 查看添加了 SDK 及其目标的项目一样。</span><span class="sxs-lookup"><span data-stu-id="29d79-177">While those csproj changes greatly simplify project files, you might want to see the fully expanded project as MSBuild sees it once the SDK and its targets are included.</span></span> <span data-ttu-id="29d79-178">使用 [`dotnet msbuild`](dotnet-msbuild.md) 命令的 [`/pp` 开关](/visualstudio/msbuild/msbuild-command-line-reference#preprocess)预处理项目，显示导入的文件、文件源及其在生成中的参与情况，而无需实际生成项目：</span><span class="sxs-lookup"><span data-stu-id="29d79-178">Preprocess the project with [the `/pp` switch](/visualstudio/msbuild/msbuild-command-line-reference#preprocess) of the [`dotnet msbuild`](dotnet-msbuild.md) command, which shows which files are imported, their sources, and their contributions to the build without actually building the project:</span></span>

`dotnet msbuild -pp:fullproject.xml`

<span data-ttu-id="29d79-179">如果项目有多个目标框架，命令结果应仅侧重于框架之一，具体方法为将相应框架指定为 MSBuild 属性：</span><span class="sxs-lookup"><span data-stu-id="29d79-179">If the project has multiple target frameworks, the results of the command should be focused on only one of them by specifying it as an MSBuild property:</span></span>

`dotnet msbuild -p:TargetFramework=netcoreapp2.0 -pp:fullproject.xml`

## <a name="additions"></a><span data-ttu-id="29d79-180">新增内容</span><span class="sxs-lookup"><span data-stu-id="29d79-180">Additions</span></span>

### <a name="sdk-attribute"></a><span data-ttu-id="29d79-181">Sdk 特性</span><span class="sxs-lookup"><span data-stu-id="29d79-181">Sdk attribute</span></span>

<span data-ttu-id="29d79-182">.csproj 文件的根 `<Project>` 元素具有名为 `Sdk` 的新特性。</span><span class="sxs-lookup"><span data-stu-id="29d79-182">The root `<Project>` element of the *.csproj* file has a new attribute called `Sdk`.</span></span> <span data-ttu-id="29d79-183">`Sdk` 指定项目将使用的 SDK。</span><span class="sxs-lookup"><span data-stu-id="29d79-183">`Sdk` specifies which SDK will be used by the project.</span></span> <span data-ttu-id="29d79-184">如[分层文档](cli-msbuild-architecture.md)中所述，SDK 是一组可生成 .NET Core 代码的 MSBuild [任务](/visualstudio/msbuild/msbuild-tasks)和[目标](/visualstudio/msbuild/msbuild-targets)。</span><span class="sxs-lookup"><span data-stu-id="29d79-184">The SDK, as the [layering document](cli-msbuild-architecture.md) describes, is a set of MSBuild [tasks](/visualstudio/msbuild/msbuild-tasks) and [targets](/visualstudio/msbuild/msbuild-targets) that can build .NET Core code.</span></span> <span data-ttu-id="29d79-185">.NET Core 工具随附了三个主要 SDK：</span><span class="sxs-lookup"><span data-stu-id="29d79-185">We ship three main SDKs with the .NET Core tools:</span></span>

1. <span data-ttu-id="29d79-186">ID 为 `Microsoft.NET.Sdk` 的 .NET Core SDK</span><span class="sxs-lookup"><span data-stu-id="29d79-186">The .NET Core SDK with the ID of `Microsoft.NET.Sdk`</span></span>
2. <span data-ttu-id="29d79-187">ID 为 `Microsoft.NET.Sdk.Web` 的 .NET Core Web SDK</span><span class="sxs-lookup"><span data-stu-id="29d79-187">The .NET Core web SDK with the ID of `Microsoft.NET.Sdk.Web`</span></span>
3. <span data-ttu-id="29d79-188">ID 为 `Microsoft.NET.Sdk.Razor` 的 .NET Core Razor 类库 SDK</span><span class="sxs-lookup"><span data-stu-id="29d79-188">The .NET Core Razor Class Library SDK with the ID of `Microsoft.NET.Sdk.Razor`</span></span>

<span data-ttu-id="29d79-189">需要在 `<Project>` 元素上将 `Sdk` 属性设置为这两个 ID 之一，以使用 .NET Core 工具和生成代码。</span><span class="sxs-lookup"><span data-stu-id="29d79-189">You need to have the `Sdk` attribute set to one of those IDs on the `<Project>` element in order to use the .NET Core tools and build your code.</span></span>

### <a name="packagereference"></a><span data-ttu-id="29d79-190">PackageReference</span><span class="sxs-lookup"><span data-stu-id="29d79-190">PackageReference</span></span>

<span data-ttu-id="29d79-191">`<PackageReference>` 项元素指定[项目中的 NuGet 依赖项](/nuget/consume-packages/package-references-in-project-files)。</span><span class="sxs-lookup"><span data-stu-id="29d79-191">A `<PackageReference>` item element specifies a [NuGet dependency in the project](/nuget/consume-packages/package-references-in-project-files).</span></span> <span data-ttu-id="29d79-192">`Include` 属性指定包 ID。</span><span class="sxs-lookup"><span data-stu-id="29d79-192">The `Include` attribute specifies the package ID.</span></span>

```xml
<PackageReference Include="<package-id>" Version="" PrivateAssets="" IncludeAssets="" ExcludeAssets="" />
```

#### <a name="version"></a><span data-ttu-id="29d79-193">Version</span><span class="sxs-lookup"><span data-stu-id="29d79-193">Version</span></span>

<span data-ttu-id="29d79-194">所需的 `Version` 属性指定要还原的包的版本。</span><span class="sxs-lookup"><span data-stu-id="29d79-194">The required `Version` attribute specifies the version of the package to restore.</span></span> <span data-ttu-id="29d79-195">此属性遵循 [NuGet 版本控制](/nuget/reference/package-versioning#version-ranges-and-wildcards)方案规则。</span><span class="sxs-lookup"><span data-stu-id="29d79-195">The attribute respects the rules of the [NuGet versioning](/nuget/reference/package-versioning#version-ranges-and-wildcards) scheme.</span></span> <span data-ttu-id="29d79-196">默认行为是精确的版本匹配。</span><span class="sxs-lookup"><span data-stu-id="29d79-196">The default behavior is an exact version match.</span></span> <span data-ttu-id="29d79-197">例如，指定 `Version="1.2.3"` 等效于包的 1.2.3 版本的 NuGet 表示法 `[1.2.3]`。</span><span class="sxs-lookup"><span data-stu-id="29d79-197">For example, specifying `Version="1.2.3"` is equivalent to NuGet notation `[1.2.3]` for the exact 1.2.3 version of the package.</span></span>

#### <a name="includeassets-excludeassets-and-privateassets"></a><span data-ttu-id="29d79-198">IncludeAssets、ExcludeAssets 和 PrivateAssets</span><span class="sxs-lookup"><span data-stu-id="29d79-198">IncludeAssets, ExcludeAssets and PrivateAssets</span></span>

<span data-ttu-id="29d79-199">`IncludeAssets` 属性指定应使用 `<PackageReference>` 指定的包中的哪些资产。</span><span class="sxs-lookup"><span data-stu-id="29d79-199">`IncludeAssets` attribute specifies which assets belonging to the package specified by `<PackageReference>` should be consumed.</span></span> <span data-ttu-id="29d79-200">默认情况下，包含所有包资产。</span><span class="sxs-lookup"><span data-stu-id="29d79-200">By default, all package assets are included.</span></span>

<span data-ttu-id="29d79-201">`ExcludeAssets` 属性指定不应使用 `<PackageReference>` 指定的包中的哪些资产。</span><span class="sxs-lookup"><span data-stu-id="29d79-201">`ExcludeAssets` attribute specifies which assets belonging to the package specified by `<PackageReference>` should not be consumed.</span></span>

<span data-ttu-id="29d79-202">`PrivateAssets` 属性指定应使用 `<PackageReference>` 指定的包中的哪些资产，但不得将这些资产传递到下一个项目。</span><span class="sxs-lookup"><span data-stu-id="29d79-202">`PrivateAssets` attribute specifies which assets belonging to the package specified by `<PackageReference>` should be consumed but not flow to the next project.</span></span> <span data-ttu-id="29d79-203">不存在此属性时，`Analyzers`、`Build` 和 `ContentFiles` 资产默认为私有。</span><span class="sxs-lookup"><span data-stu-id="29d79-203">The `Analyzers`, `Build` and `ContentFiles` assets are private by default when this attribute is not present.</span></span>

> [!NOTE]
> <span data-ttu-id="29d79-204">`PrivateAssets` 等效于 *project.json*/*xproj* `SuppressParent` 元素。</span><span class="sxs-lookup"><span data-stu-id="29d79-204">`PrivateAssets` is equivalent to the *project.json*/*xproj* `SuppressParent` element.</span></span>

<span data-ttu-id="29d79-205">这些属性可以包含以下一个或多个项，如果列出多个项，则用分号 `;` 字符进行分隔：</span><span class="sxs-lookup"><span data-stu-id="29d79-205">These attributes can contain one or more of the following items, separated by the semicolon `;` character if more than one is listed:</span></span>

* <span data-ttu-id="29d79-206">`Compile` - 可对 lib 文件夹内容进行编译。</span><span class="sxs-lookup"><span data-stu-id="29d79-206">`Compile` – the contents of the lib folder are available to compile against.</span></span>
* <span data-ttu-id="29d79-207">`Runtime` - 分发运行时文件夹内容。</span><span class="sxs-lookup"><span data-stu-id="29d79-207">`Runtime` – the contents of the runtime folder are distributed.</span></span>
* <span data-ttu-id="29d79-208">`ContentFiles` - 使用 *contentfiles* 文件夹的内容。</span><span class="sxs-lookup"><span data-stu-id="29d79-208">`ContentFiles` – the contents of the *contentfiles* folder are used.</span></span>
* <span data-ttu-id="29d79-209">`Build` - 使用生成文件夹中的属性/目标。</span><span class="sxs-lookup"><span data-stu-id="29d79-209">`Build` – the props/targets in the build folder are used.</span></span>
* <span data-ttu-id="29d79-210">`Native` - 将本机资产内容复制到运行时输出文件夹。</span><span class="sxs-lookup"><span data-stu-id="29d79-210">`Native` – the contents from native assets are copied to the output folder for runtime.</span></span>
* <span data-ttu-id="29d79-211">`Analyzers` - 使用分析器。</span><span class="sxs-lookup"><span data-stu-id="29d79-211">`Analyzers` – the analyzers are used.</span></span>

<span data-ttu-id="29d79-212">此属性也可以包含：</span><span class="sxs-lookup"><span data-stu-id="29d79-212">Alternatively, the attribute can contain:</span></span>

* <span data-ttu-id="29d79-213">`None` - 不使用任何资产。</span><span class="sxs-lookup"><span data-stu-id="29d79-213">`None` – none of the assets are used.</span></span>
* <span data-ttu-id="29d79-214">`All` - 使用所有资产。</span><span class="sxs-lookup"><span data-stu-id="29d79-214">`All` – all assets are used.</span></span>

### <a name="dotnetclitoolreference"></a><span data-ttu-id="29d79-215">DotNetCliToolReference</span><span class="sxs-lookup"><span data-stu-id="29d79-215">DotNetCliToolReference</span></span>
<span data-ttu-id="29d79-216">`<DotNetCliToolReference>` 项元素指定用户想要在项目的上下文中还原的 CLI 工具。</span><span class="sxs-lookup"><span data-stu-id="29d79-216">A `<DotNetCliToolReference>` item element specifies the CLI tool that the user wants to restore in the context of the project.</span></span> <span data-ttu-id="29d79-217">在 *project.json* 中，它可以替换 `tools` 节点。</span><span class="sxs-lookup"><span data-stu-id="29d79-217">It's a replacement for the `tools` node in *project.json*.</span></span>

```xml
<DotNetCliToolReference Include="<package-id>" Version="" />
```

#### <a name="version"></a><span data-ttu-id="29d79-218">Version</span><span class="sxs-lookup"><span data-stu-id="29d79-218">Version</span></span>

<span data-ttu-id="29d79-219">`Version` 指定要还原的包的版本。</span><span class="sxs-lookup"><span data-stu-id="29d79-219">`Version` specifies the version of the package to restore.</span></span> <span data-ttu-id="29d79-220">此属性遵循 [NuGet 版本控制](/nuget/create-packages/dependency-versions#version-ranges)方案规则。</span><span class="sxs-lookup"><span data-stu-id="29d79-220">The attribute respects the rules of the [NuGet versioning](/nuget/create-packages/dependency-versions#version-ranges) scheme.</span></span> <span data-ttu-id="29d79-221">默认行为是精确的版本匹配。</span><span class="sxs-lookup"><span data-stu-id="29d79-221">The default behavior is an exact version match.</span></span> <span data-ttu-id="29d79-222">例如，指定 `Version="1.2.3"` 等效于包的 1.2.3 版本的 NuGet 表示法 `[1.2.3]`。</span><span class="sxs-lookup"><span data-stu-id="29d79-222">For example, specifying `Version="1.2.3"` is equivalent to NuGet notation `[1.2.3]` for the exact 1.2.3 version of the package.</span></span>

### <a name="runtimeidentifiers"></a><span data-ttu-id="29d79-223">RuntimeIdentifiers</span><span class="sxs-lookup"><span data-stu-id="29d79-223">RuntimeIdentifiers</span></span>

<span data-ttu-id="29d79-224">`<RuntimeIdentifiers>` 属性元素可用于指定项目的[运行时标识符 (RID)](../rid-catalog.md) 的列表（以分号分隔）。</span><span class="sxs-lookup"><span data-stu-id="29d79-224">The `<RuntimeIdentifiers>` property element lets you specify a semicolon-delimited list of [Runtime Identifiers (RIDs)](../rid-catalog.md) for the project.</span></span>
<span data-ttu-id="29d79-225">RID 允许发布独立部署。</span><span class="sxs-lookup"><span data-stu-id="29d79-225">RIDs enable publishing self-contained deployments.</span></span>

```xml
<RuntimeIdentifiers>win10-x64;osx.10.11-x64;ubuntu.16.04-x64</RuntimeIdentifiers>
```

### <a name="runtimeidentifier"></a><span data-ttu-id="29d79-226">RuntimeIdentifier</span><span class="sxs-lookup"><span data-stu-id="29d79-226">RuntimeIdentifier</span></span>

<span data-ttu-id="29d79-227">`<RuntimeIdentifier>` 属性元素可用于指定项目的唯一[运行时标识符 (RID)](../rid-catalog.md)。</span><span class="sxs-lookup"><span data-stu-id="29d79-227">The `<RuntimeIdentifier>` property element allows you to specify only one [Runtime Identifier (RID)](../rid-catalog.md) for the project.</span></span> <span data-ttu-id="29d79-228">RID 支持发布独立部署。</span><span class="sxs-lookup"><span data-stu-id="29d79-228">The RID enables publishing a self-contained deployment.</span></span>

```xml
<RuntimeIdentifier>ubuntu.16.04-x64</RuntimeIdentifier>
```

<span data-ttu-id="29d79-229">如果需要为多个运行时发布，请使用 `<RuntimeIdentifiers>`（复数）。</span><span class="sxs-lookup"><span data-stu-id="29d79-229">Use `<RuntimeIdentifiers>` (plural) instead if you need to publish for multiple runtimes.</span></span> <span data-ttu-id="29d79-230">如果只需要单个运行时，`<RuntimeIdentifier>` 可以进行较快的生成。</span><span class="sxs-lookup"><span data-stu-id="29d79-230">`<RuntimeIdentifier>` can provide faster builds when only a single runtime is required.</span></span>

### <a name="packagetargetfallback"></a><span data-ttu-id="29d79-231">PackageTargetFallback</span><span class="sxs-lookup"><span data-stu-id="29d79-231">PackageTargetFallback</span></span>

<span data-ttu-id="29d79-232">`<PackageTargetFallback>` 属性元素可用于指定要在还原包时使用的一组兼容目标。</span><span class="sxs-lookup"><span data-stu-id="29d79-232">The `<PackageTargetFallback>` property element allows you to specify a set of compatible targets to be used when restoring packages.</span></span> <span data-ttu-id="29d79-233">旨在允许使用 dotnet [TxM（目标 x 名字对象）](/nuget/schema/target-frameworks) 的包处理未声明 dotnet TxM 的包。</span><span class="sxs-lookup"><span data-stu-id="29d79-233">It's designed to allow packages that use the dotnet [TxM (Target x Moniker)](/nuget/schema/target-frameworks) to operate with packages that don't declare a dotnet TxM.</span></span> <span data-ttu-id="29d79-234">如果项目使用 dotnet TxM，那么所依赖的所有包也必须有 dotnet TxM，除非将 `<PackageTargetFallback>` 添加到项目中，以允许非 dotnet 平台与 dotnet 兼容。</span><span class="sxs-lookup"><span data-stu-id="29d79-234">If your project uses the dotnet TxM, then all the packages it depends on must also have a dotnet TxM, unless you add the `<PackageTargetFallback>` to your project in order to allow non-dotnet platforms to be compatible with dotnet.</span></span>

<span data-ttu-id="29d79-235">以下示例展示了项目中所有目标的回退：</span><span class="sxs-lookup"><span data-stu-id="29d79-235">The following example provides the fallbacks for all targets in your project:</span></span>

```xml
<PackageTargetFallback>
    $(PackageTargetFallback);portable-net45+win8+wpa81+wp8
</PackageTargetFallback >
```

<span data-ttu-id="29d79-236">以下示例仅指定了 `netcoreapp2.1` 目标的回退：</span><span class="sxs-lookup"><span data-stu-id="29d79-236">The following example specifies the fallbacks only for the `netcoreapp2.1` target:</span></span>

```xml
<PackageTargetFallback Condition="'$(TargetFramework)'=='netcoreapp2.1'">
    $(PackageTargetFallback);portable-net45+win8+wpa81+wp8
</PackageTargetFallback >
```

## <a name="nuget-metadata-properties"></a><span data-ttu-id="29d79-237">NugetMetadataProperties</span><span class="sxs-lookup"><span data-stu-id="29d79-237">NuGet metadata properties</span></span>

<span data-ttu-id="29d79-238">迁移到 MSBuild 后，我们已将在打包 NuGet 包时使用的输入元数据从 project.json 移到 .csproj 文件中。</span><span class="sxs-lookup"><span data-stu-id="29d79-238">With the move to MSBuild, we have moved the input metadata that is used when packing a NuGet package from *project.json* to *.csproj* files.</span></span> <span data-ttu-id="29d79-239">输入为 MSBuild 属性，因此它们必须转到 `<PropertyGroup>` 组中。</span><span class="sxs-lookup"><span data-stu-id="29d79-239">The inputs are MSBuild properties so they have to go within a `<PropertyGroup>` group.</span></span> <span data-ttu-id="29d79-240">下面列出了在使用 `dotnet pack` 命令或属于 SDK 的 `Pack` MSBuild 目标时，用作打包进程的输入的属性。</span><span class="sxs-lookup"><span data-stu-id="29d79-240">The following is the list of properties that are used as inputs to the packing process when using the `dotnet pack` command or the `Pack` MSBuild target that is part of the SDK.</span></span>

### <a name="ispackable"></a><span data-ttu-id="29d79-241">IsPackable</span><span class="sxs-lookup"><span data-stu-id="29d79-241">IsPackable</span></span>

<span data-ttu-id="29d79-242">一个指定能否打包项目的布尔值。</span><span class="sxs-lookup"><span data-stu-id="29d79-242">A Boolean value that specifies whether the project can be packed.</span></span> <span data-ttu-id="29d79-243">默认值为 `true`。</span><span class="sxs-lookup"><span data-stu-id="29d79-243">The default value is `true`.</span></span>

### <a name="packageversion"></a><span data-ttu-id="29d79-244">PackageVersion</span><span class="sxs-lookup"><span data-stu-id="29d79-244">PackageVersion</span></span>

<span data-ttu-id="29d79-245">指定生成的包所具有的版本。</span><span class="sxs-lookup"><span data-stu-id="29d79-245">Specifies the version that the resulting package will have.</span></span> <span data-ttu-id="29d79-246">接受所有形式的 NuGet 版本字符串。</span><span class="sxs-lookup"><span data-stu-id="29d79-246">Accepts all forms of NuGet version string.</span></span> <span data-ttu-id="29d79-247">默认为值 `$(Version)`，即项目中 `Version` 属性的值。</span><span class="sxs-lookup"><span data-stu-id="29d79-247">Default is the value of `$(Version)`, that is, of the property `Version` in the project.</span></span>

### <a name="packageid"></a><span data-ttu-id="29d79-248">PackageId</span><span class="sxs-lookup"><span data-stu-id="29d79-248">PackageId</span></span>

<span data-ttu-id="29d79-249">指定生成的包的名称。</span><span class="sxs-lookup"><span data-stu-id="29d79-249">Specifies the name for the resulting package.</span></span> <span data-ttu-id="29d79-250">如果未指定，`pack` 操作将默认使用 `AssemblyName` 或目录名称作为包的名称。</span><span class="sxs-lookup"><span data-stu-id="29d79-250">If not specified, the `pack` operation will default to using the `AssemblyName` or directory name as the name of the package.</span></span>

### <a name="title"></a><span data-ttu-id="29d79-251">Title</span><span class="sxs-lookup"><span data-stu-id="29d79-251">Title</span></span>

<span data-ttu-id="29d79-252">明了易用的包标题，通常用在 UI 显示中，如 nuget.org 上和 Visual Studio 中包管理器上的那样。</span><span class="sxs-lookup"><span data-stu-id="29d79-252">A human-friendly title of the package, typically used in UI displays as on nuget.org and the Package Manager in Visual Studio.</span></span> <span data-ttu-id="29d79-253">如果未指定，则改为使用包 ID。</span><span class="sxs-lookup"><span data-stu-id="29d79-253">If not specified, the package ID is used instead.</span></span>

### <a name="authors"></a><span data-ttu-id="29d79-254">Authors</span><span class="sxs-lookup"><span data-stu-id="29d79-254">Authors</span></span>

<span data-ttu-id="29d79-255">其中名称以分号分隔的包作者列表，其中名称与 nuget.org 上的配置文件名称匹配。这些信息显示在 nuget.org 上的 NuGet 库中，并用于交叉引用同一作者的包。</span><span class="sxs-lookup"><span data-stu-id="29d79-255">A semicolon-separated list of packages authors, matching the profile names on nuget.org. These are displayed in the NuGet Gallery on nuget.org and are used to cross-reference packages by the same authors.</span></span>

### <a name="packagedescription"></a><span data-ttu-id="29d79-256">PackageDescription</span><span class="sxs-lookup"><span data-stu-id="29d79-256">PackageDescription</span></span>

<span data-ttu-id="29d79-257">用于 UI 显示的包的详细说明。</span><span class="sxs-lookup"><span data-stu-id="29d79-257">A long description of the package for UI display.</span></span>

### <a name="description"></a><span data-ttu-id="29d79-258">Description</span><span class="sxs-lookup"><span data-stu-id="29d79-258">Description</span></span>

<span data-ttu-id="29d79-259">程序集的详细说明。</span><span class="sxs-lookup"><span data-stu-id="29d79-259">A long description for the assembly.</span></span> <span data-ttu-id="29d79-260">如果未指定 `PackageDescription`，则此属性还可用作程序包的说明。</span><span class="sxs-lookup"><span data-stu-id="29d79-260">If `PackageDescription` is not specified then this property is also used as the description of the package.</span></span>

### <a name="copyright"></a><span data-ttu-id="29d79-261">Copyright</span><span class="sxs-lookup"><span data-stu-id="29d79-261">Copyright</span></span>

<span data-ttu-id="29d79-262">包的版权详细信息。</span><span class="sxs-lookup"><span data-stu-id="29d79-262">Copyright details for the package.</span></span>

### <a name="packagerequirelicenseacceptance"></a><span data-ttu-id="29d79-263">PackageRequireLicenseAcceptance</span><span class="sxs-lookup"><span data-stu-id="29d79-263">PackageRequireLicenseAcceptance</span></span>

<span data-ttu-id="29d79-264">一个布尔值，指定客户端是否必须提示使用者接受包许可证后才可安装包。</span><span class="sxs-lookup"><span data-stu-id="29d79-264">A Boolean value that specifies whether the client must prompt the consumer to accept the package license before installing the package.</span></span> <span data-ttu-id="29d79-265">默认值为 `false`。</span><span class="sxs-lookup"><span data-stu-id="29d79-265">The default is `false`.</span></span>

### <a name="packagelicenseexpression"></a><span data-ttu-id="29d79-266">PackageLicenseExpression</span><span class="sxs-lookup"><span data-stu-id="29d79-266">PackageLicenseExpression</span></span>

<span data-ttu-id="29d79-267">[SPDX 许可证标识符](https://spdx.org/licenses/)或表达式。</span><span class="sxs-lookup"><span data-stu-id="29d79-267">An [SPDX license identifier](https://spdx.org/licenses/) or expression.</span></span> <span data-ttu-id="29d79-268">例如 `Apache-2.0`。</span><span class="sxs-lookup"><span data-stu-id="29d79-268">For example, `Apache-2.0`.</span></span>

<span data-ttu-id="29d79-269">下面是 [SPDX 许可证标识符](https://spdx.org/licenses/)的完整列表。</span><span class="sxs-lookup"><span data-stu-id="29d79-269">Here is the complete list of [SPDX license identifiers](https://spdx.org/licenses/).</span></span> <span data-ttu-id="29d79-270">NuGet.org 在使用许可证类型表达式时只接受 OSI 或 FSF 批准的许可证。</span><span class="sxs-lookup"><span data-stu-id="29d79-270">NuGet.org accepts only OSI or FSF approved licenses when using license type expression.</span></span>

<span data-ttu-id="29d79-271">许可证表达式的准确语法如下面的 [ABNF](https://tools.ietf.org/html/rfc5234) 所述。</span><span class="sxs-lookup"><span data-stu-id="29d79-271">The exact syntax of the license expressions is described below in [ABNF](https://tools.ietf.org/html/rfc5234).</span></span>

```cli
license-id            = <short form license identifier from https://spdx.org/spdx-specification-21-web-version#h.luq9dgcle9mo>

license-exception-id  = <short form license exception identifier from https://spdx.org/spdx-specification-21-web-version#h.ruv3yl8g6czd>

simple-expression = license-id / license-id”+”

compound-expression =  1*1(simple-expression /
                simple-expression "WITH" license-exception-id /
                compound-expression "AND" compound-expression /
                compound-expression "OR" compound-expression ) /
                "(" compound-expression ")" )

license-expression =  1*1(simple-expression / compound-expression / UNLICENSED)
```

> [!NOTE]
> <span data-ttu-id="29d79-272">一次只能指定 `PackageLicenseExpression`、`PackageLicenseFile` 和 `PackageLicenseUrl` 中的一个。</span><span class="sxs-lookup"><span data-stu-id="29d79-272">Only one of `PackageLicenseExpression`, `PackageLicenseFile` and `PackageLicenseUrl` can be specified at a time.</span></span>

### <a name="packagelicensefile"></a><span data-ttu-id="29d79-273">PackageLicenseFile</span><span class="sxs-lookup"><span data-stu-id="29d79-273">PackageLicenseFile</span></span>

<span data-ttu-id="29d79-274">如果使用的许可证没有分配 SPDX 标识符，或者它是自定义许可证，则它是包中许可证文件的路径（否则，优先选择 `PackageLicenseExpression`）</span><span class="sxs-lookup"><span data-stu-id="29d79-274">Path to a license file within the package if you are using a license that hasn’t been assigned an SPDX identifier, or it is a custom license (Otherwise `PackageLicenseExpression` is prefered)</span></span>

<span data-ttu-id="29d79-275">替换 `PackageLicenseUrl`，不能与 `PackageLicenseExpression` 结合使用，并且需要 Visual Studio 15.9.4、.NET SDK 2.1.502 或 2.2.101 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="29d79-275">Replaces `PackageLicenseUrl`, can't be combined with `PackageLicenseExpression` and requires Visual Studio 15.9.4, .NET SDK 2.1.502 or 2.2.101, or newer.</span></span>

<span data-ttu-id="29d79-276">将需要通过显式地将许可证文件添加到项目中来确保许可证文件已打包，示例用法如下：</span><span class="sxs-lookup"><span data-stu-id="29d79-276">You will need to ensure the license file is packed by adding it explicitly to the project, example usage:</span></span>

```xml
<PropertyGroup>
  <PackageLicenseFile>LICENSE.txt</PackageLicenseFile>
</PropertyGroup>
<ItemGroup>
  <None Include="licenses\LICENSE.txt" Pack="true" PackagePath="$(PackageLicenseFile)"/>
</ItemGroup>
```

### <a name="packagelicenseurl"></a><span data-ttu-id="29d79-277">PackageLicenseUrl</span><span class="sxs-lookup"><span data-stu-id="29d79-277">PackageLicenseUrl</span></span>

<span data-ttu-id="29d79-278">适用于包的许可证的 URL。</span><span class="sxs-lookup"><span data-stu-id="29d79-278">An URL to the license that is applicable to the package.</span></span> <span data-ttu-id="29d79-279">（自 Visual Studio 15.9.4、.NET SDK 2.1.502 和 2.2.101 起已弃用）</span><span class="sxs-lookup"><span data-stu-id="29d79-279">(_deprecated since Visual Studio 15.9.4, .NET SDK 2.1.502 and 2.2.101_)</span></span>

### <a name="packageiconurl"></a><span data-ttu-id="29d79-280">PackageIconUrl</span><span class="sxs-lookup"><span data-stu-id="29d79-280">PackageIconUrl</span></span>

<span data-ttu-id="29d79-281">64x64 透明背景图像的 URL，用作 UI 显示中包的图标。</span><span class="sxs-lookup"><span data-stu-id="29d79-281">A URL for a 64x64 image with transparent background to use as the icon for the package in UI display.</span></span>

### <a name="packagereleasenotes"></a><span data-ttu-id="29d79-282">PackageReleaseNotes</span><span class="sxs-lookup"><span data-stu-id="29d79-282">PackageReleaseNotes</span></span>

<span data-ttu-id="29d79-283">包的发行说明。</span><span class="sxs-lookup"><span data-stu-id="29d79-283">Release notes for the package.</span></span>

### <a name="packagetags"></a><span data-ttu-id="29d79-284">PackageTags</span><span class="sxs-lookup"><span data-stu-id="29d79-284">PackageTags</span></span>

<span data-ttu-id="29d79-285">标记的分号分隔列表，这些标记用于指定包。</span><span class="sxs-lookup"><span data-stu-id="29d79-285">A semicolon-delimited list of tags that designates the package.</span></span>

### <a name="packageoutputpath"></a><span data-ttu-id="29d79-286">PackageOutputPath</span><span class="sxs-lookup"><span data-stu-id="29d79-286">PackageOutputPath</span></span>

<span data-ttu-id="29d79-287">确定用于已打包的包的输出路径。</span><span class="sxs-lookup"><span data-stu-id="29d79-287">Determines the output path in which the packed package will be dropped.</span></span> <span data-ttu-id="29d79-288">默认值为 `$(OutputPath)`。</span><span class="sxs-lookup"><span data-stu-id="29d79-288">Default is `$(OutputPath)`.</span></span>

### <a name="includesymbols"></a><span data-ttu-id="29d79-289">IncludeSymbols</span><span class="sxs-lookup"><span data-stu-id="29d79-289">IncludeSymbols</span></span>
<span data-ttu-id="29d79-290">此布尔值指示在打包项目时，包是否应创建一个附加的符号包。</span><span class="sxs-lookup"><span data-stu-id="29d79-290">This Boolean value indicates whether the package should create an additional symbols package when the project is packed.</span></span> <span data-ttu-id="29d79-291">符号包的格式由 `SymbolPackageFormat` 属性控制。</span><span class="sxs-lookup"><span data-stu-id="29d79-291">The symbols package's format is controlled by the `SymbolPackageFormat` property.</span></span>

### <a name="symbolpackageformat"></a><span data-ttu-id="29d79-292">SymbolPackageFormat</span><span class="sxs-lookup"><span data-stu-id="29d79-292">SymbolPackageFormat</span></span>
<span data-ttu-id="29d79-293">指定符号包的格式。</span><span class="sxs-lookup"><span data-stu-id="29d79-293">Specifies the format of the symbols package.</span></span> <span data-ttu-id="29d79-294">如果为“symbols.nupkg”，将使用包含 PDB、DLL 和其他输出文件的 .symbols.nupkg 扩展创建旧符号包。</span><span class="sxs-lookup"><span data-stu-id="29d79-294">If "symbols.nupkg", a legacy symbols package will be created with a *.symbols.nupkg* extension containing PDBs, DLLs, and other output files.</span></span> <span data-ttu-id="29d79-295">如果为“snupkg”，将创建包含可移植 PDB 的 snupkg 符号包。</span><span class="sxs-lookup"><span data-stu-id="29d79-295">If "snupkg", a snupkg symbol package will be created containing the portable PDBs.</span></span> <span data-ttu-id="29d79-296">默认值为“symbols.nupkg”。</span><span class="sxs-lookup"><span data-stu-id="29d79-296">Default is "symbols.nupkg".</span></span>

### <a name="includesource"></a><span data-ttu-id="29d79-297">IncludeSource</span><span class="sxs-lookup"><span data-stu-id="29d79-297">IncludeSource</span></span>

<span data-ttu-id="29d79-298">此布尔值指示包进程是否应创建源包。</span><span class="sxs-lookup"><span data-stu-id="29d79-298">This Boolean value indicates whether the pack process should create a source package.</span></span> <span data-ttu-id="29d79-299">源包中包含库的源代码以及 PDB 文件。</span><span class="sxs-lookup"><span data-stu-id="29d79-299">The source package contains the library's source code as well as PDB files.</span></span> <span data-ttu-id="29d79-300">源文件置于生成的包文件中的 `src/ProjectName` 目录下。</span><span class="sxs-lookup"><span data-stu-id="29d79-300">Source files are put under the `src/ProjectName` directory in the resulting package file.</span></span>

### <a name="istool"></a><span data-ttu-id="29d79-301">IsTool</span><span class="sxs-lookup"><span data-stu-id="29d79-301">IsTool</span></span>

<span data-ttu-id="29d79-302">指定是否将所有输出文件复制到 *tools* 文件夹，而不是 *lib* 文件夹。</span><span class="sxs-lookup"><span data-stu-id="29d79-302">Specifies whether all output files are copied to the *tools* folder instead of the *lib* folder.</span></span> <span data-ttu-id="29d79-303">请注意，这不同于 `DotNetCliTool`，后者通过在 *.csproj* 文件中设置 `PackageType` 进行指定。</span><span class="sxs-lookup"><span data-stu-id="29d79-303">Note that this is different from a `DotNetCliTool` which is specified by setting the `PackageType` in the *.csproj* file.</span></span>

### <a name="repositoryurl"></a><span data-ttu-id="29d79-304">RepositoryUrl</span><span class="sxs-lookup"><span data-stu-id="29d79-304">RepositoryUrl</span></span>

<span data-ttu-id="29d79-305">指定存储库的 URL，该存储库是包的源代码所驻留和/或生成的位置。</span><span class="sxs-lookup"><span data-stu-id="29d79-305">Specifies the URL for the repository where the source code for the package resides and/or from which it's being built.</span></span>

### <a name="repositorytype"></a><span data-ttu-id="29d79-306">RepositoryType</span><span class="sxs-lookup"><span data-stu-id="29d79-306">RepositoryType</span></span>

<span data-ttu-id="29d79-307">指定存储库的类型。</span><span class="sxs-lookup"><span data-stu-id="29d79-307">Specifies the type of the repository.</span></span> <span data-ttu-id="29d79-308">默认值为“git”。</span><span class="sxs-lookup"><span data-stu-id="29d79-308">Default is "git".</span></span>

### <a name="nopackageanalysis"></a><span data-ttu-id="29d79-309">NoPackageAnalysis</span><span class="sxs-lookup"><span data-stu-id="29d79-309">NoPackageAnalysis</span></span>

<span data-ttu-id="29d79-310">指定 pack 不应在生成包后运行包分析。</span><span class="sxs-lookup"><span data-stu-id="29d79-310">Specifies that pack should not run package analysis after building the package.</span></span>

### <a name="minclientversion"></a><span data-ttu-id="29d79-311">MinClientVersion</span><span class="sxs-lookup"><span data-stu-id="29d79-311">MinClientVersion</span></span>

<span data-ttu-id="29d79-312">指定可安装此包的最低 NuGet 客户端版本，并由 nuget.exe 和 Visual Studio 程序包管理器强制实施。</span><span class="sxs-lookup"><span data-stu-id="29d79-312">Specifies the minimum version of the NuGet client that can install this package, enforced by nuget.exe and the Visual Studio Package Manager.</span></span>

### <a name="includebuildoutput"></a><span data-ttu-id="29d79-313">IncludeBuildOutput</span><span class="sxs-lookup"><span data-stu-id="29d79-313">IncludeBuildOutput</span></span>

<span data-ttu-id="29d79-314">此布尔值指定是否应将生成输出程序集打包到 *.nupkg* 文件中。</span><span class="sxs-lookup"><span data-stu-id="29d79-314">This Boolean values specifies whether the build output assemblies should be packed into the *.nupkg* file or not.</span></span>

### <a name="includecontentinpack"></a><span data-ttu-id="29d79-315">IncludeContentInPack</span><span class="sxs-lookup"><span data-stu-id="29d79-315">IncludeContentInPack</span></span>

<span data-ttu-id="29d79-316">此布尔值指定是否将含有 `Content` 类型的任何项自动包含在生成的包中。</span><span class="sxs-lookup"><span data-stu-id="29d79-316">This Boolean value specifies whether any items that have a type of `Content` will be included in the resulting package automatically.</span></span> <span data-ttu-id="29d79-317">默认值为 `true`。</span><span class="sxs-lookup"><span data-stu-id="29d79-317">The default is `true`.</span></span>

### <a name="buildoutputtargetfolder"></a><span data-ttu-id="29d79-318">BuildOutputTargetFolder</span><span class="sxs-lookup"><span data-stu-id="29d79-318">BuildOutputTargetFolder</span></span>

<span data-ttu-id="29d79-319">指定放置输出程序集的文件夹。</span><span class="sxs-lookup"><span data-stu-id="29d79-319">Specifies the folder where to place the output assemblies.</span></span> <span data-ttu-id="29d79-320">输出程序集（和其他输出文件）会复制到各自的框架文件夹中。</span><span class="sxs-lookup"><span data-stu-id="29d79-320">The output assemblies (and other output files) are copied into their respective framework folders.</span></span>

### <a name="contenttargetfolders"></a><span data-ttu-id="29d79-321">ContentTargetFolders</span><span class="sxs-lookup"><span data-stu-id="29d79-321">ContentTargetFolders</span></span>

<span data-ttu-id="29d79-322">此属性指定放置所有内容文件的默认位置（如果未为其指定 `PackagePath`）。</span><span class="sxs-lookup"><span data-stu-id="29d79-322">This property specifies the default location of where all the content files should go if `PackagePath` is not specified for them.</span></span> <span data-ttu-id="29d79-323">默认值为“content;contentFiles”。</span><span class="sxs-lookup"><span data-stu-id="29d79-323">The default value is "content;contentFiles".</span></span>

### <a name="nuspecfile"></a><span data-ttu-id="29d79-324">NuspecFile</span><span class="sxs-lookup"><span data-stu-id="29d79-324">NuspecFile</span></span>

<span data-ttu-id="29d79-325">用于打包的 *.nuspec* 文件的相对或绝对路径。</span><span class="sxs-lookup"><span data-stu-id="29d79-325">Relative or absolute path to the *.nuspec* file being used for packing.</span></span>

> [!NOTE]
> <span data-ttu-id="29d79-326">如果指定了 *.nuspec* 文件，则**以独占方式**将其用于打包信息，并且不使用项目中的任何信息。</span><span class="sxs-lookup"><span data-stu-id="29d79-326">If the *.nuspec* file is specified, it's used **exclusively** for packaging information and any information in the projects is not used.</span></span>

### <a name="nuspecbasepath"></a><span data-ttu-id="29d79-327">NuspecBasePath</span><span class="sxs-lookup"><span data-stu-id="29d79-327">NuspecBasePath</span></span>

<span data-ttu-id="29d79-328">*.nuspec* 文件的基路径。</span><span class="sxs-lookup"><span data-stu-id="29d79-328">Base path for the *.nuspec* file.</span></span>

### <a name="nuspecproperties"></a><span data-ttu-id="29d79-329">NuspecProperties</span><span class="sxs-lookup"><span data-stu-id="29d79-329">NuspecProperties</span></span>

<span data-ttu-id="29d79-330">键=值对的分号分隔列表。</span><span class="sxs-lookup"><span data-stu-id="29d79-330">Semicolon separated list of key=value pairs.</span></span>

## <a name="assemblyinfo-properties"></a><span data-ttu-id="29d79-331">AssemblyInfoProperties</span><span class="sxs-lookup"><span data-stu-id="29d79-331">AssemblyInfo properties</span></span>

<span data-ttu-id="29d79-332">现在，*AssemblyInfo* 文件中通常存在的[程序集特性](../../framework/app-domains/set-assembly-attributes.md)将自动从属性生成。</span><span class="sxs-lookup"><span data-stu-id="29d79-332">[Assembly attributes](../../framework/app-domains/set-assembly-attributes.md) that were typically present in an *AssemblyInfo* file are now automatically generated from properties.</span></span>

### <a name="properties-per-attribute"></a><span data-ttu-id="29d79-333">PropertiesPerAttribute</span><span class="sxs-lookup"><span data-stu-id="29d79-333">Properties per attribute</span></span>

<span data-ttu-id="29d79-334">每个特性都有一个可控制其内容的属性，还有一个可以禁用其生成的属性，如下表所示：</span><span class="sxs-lookup"><span data-stu-id="29d79-334">Each attribute has a property that control its content and another to disable its generation as shown in the following table:</span></span>

| <span data-ttu-id="29d79-335">特性</span><span class="sxs-lookup"><span data-stu-id="29d79-335">Attribute</span></span>                                                      | <span data-ttu-id="29d79-336">Property</span><span class="sxs-lookup"><span data-stu-id="29d79-336">Property</span></span>               | <span data-ttu-id="29d79-337">要禁用的属性</span><span class="sxs-lookup"><span data-stu-id="29d79-337">Property to disable</span></span>                             |
|----------------------------------------------------------------|------------------------|-------------------------------------------------|
| <xref:System.Reflection.AssemblyCompanyAttribute>              | `Company`              | `GenerateAssemblyCompanyAttribute`              |
| <xref:System.Reflection.AssemblyConfigurationAttribute>        | `Configuration`        | `GenerateAssemblyConfigurationAttribute`        |
| <xref:System.Reflection.AssemblyCopyrightAttribute>            | `Copyright`            | `GenerateAssemblyCopyrightAttribute`            |
| <xref:System.Reflection.AssemblyDescriptionAttribute>          | `Description`          | `GenerateAssemblyDescriptionAttribute`          |
| <xref:System.Reflection.AssemblyFileVersionAttribute>          | `FileVersion`          | `GenerateAssemblyFileVersionAttribute`          |
| <xref:System.Reflection.AssemblyInformationalVersionAttribute> | `InformationalVersion` | `GenerateAssemblyInformationalVersionAttribute` |
| <xref:System.Reflection.AssemblyProductAttribute>              | `Product`              | `GenerateAssemblyProductAttribute`              |
| <xref:System.Reflection.AssemblyTitleAttribute>                | `AssemblyTitle`        | `GenerateAssemblyTitleAttribute`                |
| <xref:System.Reflection.AssemblyVersionAttribute>              | `AssemblyVersion`      | `GenerateAssemblyVersionAttribute`              |
| <xref:System.Resources.NeutralResourcesLanguageAttribute>      | `NeutralLanguage`      | `GenerateNeutralResourcesLanguageAttribute`     |

<span data-ttu-id="29d79-338">注意：</span><span class="sxs-lookup"><span data-stu-id="29d79-338">Notes:</span></span>

* <span data-ttu-id="29d79-339">`AssemblyVersion` 和 `FileVersion` 默认采用 `$(Version)` 的值而不带后缀。</span><span class="sxs-lookup"><span data-stu-id="29d79-339">`AssemblyVersion` and `FileVersion` default is to take the value of `$(Version)` without suffix.</span></span> <span data-ttu-id="29d79-340">例如，如果 `$(Version)` 为 `1.2.3-beta.4`，则值将为 `1.2.3`。</span><span class="sxs-lookup"><span data-stu-id="29d79-340">For example, if `$(Version)` is `1.2.3-beta.4`, then the value would be `1.2.3`.</span></span>
* <span data-ttu-id="29d79-341">`InformationalVersion` 默认是 `$(Version)` 的值。</span><span class="sxs-lookup"><span data-stu-id="29d79-341">`InformationalVersion` defaults to the value of `$(Version)`.</span></span>
* <span data-ttu-id="29d79-342">如果存在此属性，则 `InformationalVersion` 附加 `$(SourceRevisionId)`。</span><span class="sxs-lookup"><span data-stu-id="29d79-342">`InformationalVersion` has `$(SourceRevisionId)` appended if the property is present.</span></span> <span data-ttu-id="29d79-343">可以使用 `IncludeSourceRevisionInInformationalVersion` 来禁用它。</span><span class="sxs-lookup"><span data-stu-id="29d79-343">It can be disabled using `IncludeSourceRevisionInInformationalVersion`.</span></span>
* <span data-ttu-id="29d79-344">`Copyright` 和 `Description` 属性也可用于 NuGet 元数据。</span><span class="sxs-lookup"><span data-stu-id="29d79-344">`Copyright` and `Description` properties are also used for NuGet metadata.</span></span>
* <span data-ttu-id="29d79-345">`Configuration` 与所有生成过程共享，并通过 `dotnet` 命令的 `--configuration` 参数进行设置。</span><span class="sxs-lookup"><span data-stu-id="29d79-345">`Configuration` is shared with all the build process and set via the `--configuration` parameter of `dotnet` commands.</span></span>

### <a name="generateassemblyinfo"></a><span data-ttu-id="29d79-346">GenerateAssemblyInfo</span><span class="sxs-lookup"><span data-stu-id="29d79-346">GenerateAssemblyInfo</span></span>

<span data-ttu-id="29d79-347">一个布尔值，用于启用或禁用所有 AssemblyInfo 生成。</span><span class="sxs-lookup"><span data-stu-id="29d79-347">A Boolean that enable or disable all the AssemblyInfo generation.</span></span> <span data-ttu-id="29d79-348">默认值为 `true`。</span><span class="sxs-lookup"><span data-stu-id="29d79-348">The default value is `true`.</span></span>

### <a name="generatedassemblyinfofile"></a><span data-ttu-id="29d79-349">GeneratedAssemblyInfoFile</span><span class="sxs-lookup"><span data-stu-id="29d79-349">GeneratedAssemblyInfoFile</span></span>

<span data-ttu-id="29d79-350">生成的程序集信息文件的路径。</span><span class="sxs-lookup"><span data-stu-id="29d79-350">The path of the generated assembly info file.</span></span> <span data-ttu-id="29d79-351">默认为 `$(IntermediateOutputPath)` (obj) 目录中的某个文件。</span><span class="sxs-lookup"><span data-stu-id="29d79-351">Default to a file in the `$(IntermediateOutputPath)` (obj) directory.</span></span>
