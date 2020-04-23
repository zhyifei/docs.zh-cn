---
title: Microsoft.NET.Sdk 的 MSBuild 属性
description: .NET Core SDK 可以理解的 MSBuild 属性的引用。
ms.date: 02/14/2020
ms.topic: reference
ms.openlocfilehash: d4a204a1e0216313418d278ec3bd333f72db8751
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/14/2020
ms.locfileid: "81386656"
---
# <a name="msbuild-properties-for-net-core-sdk-projects"></a><span data-ttu-id="a35a3-103">.NET Core SDK 项目的 MSBuild 属性</span><span class="sxs-lookup"><span data-stu-id="a35a3-103">MSBuild properties for .NET Core SDK projects</span></span>

<span data-ttu-id="a35a3-104">本页介绍用于配置 .NET Core 项目的 MSBuild 属性。</span><span class="sxs-lookup"><span data-stu-id="a35a3-104">This page describes MSBuild properties for configuring .NET Core projects.</span></span>

> [!NOTE]
> <span data-ttu-id="a35a3-105">此页面正在运行中，未列出 .NET Core SDK 的所有有用的 MSBuild 属性。</span><span class="sxs-lookup"><span data-stu-id="a35a3-105">This page is a work in progress and does not list all of the useful MSBuild properties for the .NET Core SDK.</span></span> <span data-ttu-id="a35a3-106">有关通用 MSBuild 属性的列表，请参阅[通用 MSBuild 属性](/visualstudio/msbuild/common-msbuild-project-properties)。</span><span class="sxs-lookup"><span data-stu-id="a35a3-106">For a list of common MSBuild properties, see [Common MSBuild properties](/visualstudio/msbuild/common-msbuild-project-properties).</span></span>

## <a name="framework-properties"></a><span data-ttu-id="a35a3-107">框架属性</span><span class="sxs-lookup"><span data-stu-id="a35a3-107">Framework properties</span></span>

- [<span data-ttu-id="a35a3-108">TargetFramework</span><span class="sxs-lookup"><span data-stu-id="a35a3-108">TargetFramework</span></span>](#targetframework)
- [<span data-ttu-id="a35a3-109">TargetFrameworks</span><span class="sxs-lookup"><span data-stu-id="a35a3-109">TargetFrameworks</span></span>](#targetframeworks)
- [<span data-ttu-id="a35a3-110">NetStandardImplicitPackageVersion</span><span class="sxs-lookup"><span data-stu-id="a35a3-110">NetStandardImplicitPackageVersion</span></span>](#netstandardimplicitpackageversion)

### <a name="targetframework"></a><span data-ttu-id="a35a3-111">TargetFramework</span><span class="sxs-lookup"><span data-stu-id="a35a3-111">TargetFramework</span></span>

<span data-ttu-id="a35a3-112">`TargetFramework` 属性指定应用的目标框架版本，该版本隐式引用[元包](../packages.md#metapackages)。</span><span class="sxs-lookup"><span data-stu-id="a35a3-112">The `TargetFramework` property specifies the target framework version for the app, which implicitly references a [metapackage](../packages.md#metapackages).</span></span> <span data-ttu-id="a35a3-113">有关有效的目标框架名字对象的列表，请参阅 [SDK 样式项目中的目标框架](../../standard/frameworks.md#supported-target-framework-versions)。</span><span class="sxs-lookup"><span data-stu-id="a35a3-113">For a list of valid target framework monikers, see [Target frameworks in SDK-style projects](../../standard/frameworks.md#supported-target-framework-versions).</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <TargetFramework>netcoreapp3.1</TargetFramework>
  </PropertyGroup>
</Project>
```

<span data-ttu-id="a35a3-114">有关详细信息，请参阅 [SDK 样式项目中的目标框架](../../standard/frameworks.md)。</span><span class="sxs-lookup"><span data-stu-id="a35a3-114">For more information, see [Target frameworks in SDK-style projects](../../standard/frameworks.md).</span></span>

### <a name="targetframeworks"></a><span data-ttu-id="a35a3-115">TargetFrameworks</span><span class="sxs-lookup"><span data-stu-id="a35a3-115">TargetFrameworks</span></span>

<span data-ttu-id="a35a3-116">如果希望应用面向多个平台，请使用 `TargetFrameworks` 属性。</span><span class="sxs-lookup"><span data-stu-id="a35a3-116">Use the `TargetFrameworks` property when you want your app to target multiple platforms.</span></span> <span data-ttu-id="a35a3-117">有关有效的目标框架名字对象的列表，请参阅 [SDK 样式项目中的目标框架](../../standard/frameworks.md#supported-target-framework-versions)。</span><span class="sxs-lookup"><span data-stu-id="a35a3-117">For a list of valid target framework monikers, see [Target frameworks in SDK-style projects](../../standard/frameworks.md#supported-target-framework-versions).</span></span>

> [!NOTE]
> <span data-ttu-id="a35a3-118">如果指定了 `TargetFramework`（单数），则忽略此属性。</span><span class="sxs-lookup"><span data-stu-id="a35a3-118">This property is ignored if `TargetFramework` (singular) is specified.</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <TargetFrameworks>netcoreapp3.1;net462</TargetFrameworks>
  </PropertyGroup>
</Project>
```

<span data-ttu-id="a35a3-119">有关详细信息，请参阅 [SDK 样式项目中的目标框架](../../standard/frameworks.md)。</span><span class="sxs-lookup"><span data-stu-id="a35a3-119">For more information, see [Target frameworks in SDK-style projects](../../standard/frameworks.md).</span></span>

### <a name="netstandardimplicitpackageversion"></a><span data-ttu-id="a35a3-120">NetStandardImplicitPackageVersion</span><span class="sxs-lookup"><span data-stu-id="a35a3-120">NetStandardImplicitPackageVersion</span></span>

> [!NOTE]
> <span data-ttu-id="a35a3-121">此属性仅适用于使用 `netstandard1.x` 的项目。</span><span class="sxs-lookup"><span data-stu-id="a35a3-121">This property only applies to projects using `netstandard1.x`.</span></span> <span data-ttu-id="a35a3-122">它不适用于使用 `netstandard2.x` 的项目。</span><span class="sxs-lookup"><span data-stu-id="a35a3-122">It doesn't apply to projects that use `netstandard2.x`.</span></span>

<span data-ttu-id="a35a3-123">如果要指定低于[元包](../packages.md#metapackages)版本的框架版本，请使用 `NetStandardImplicitPackageVersion` 属性。</span><span class="sxs-lookup"><span data-stu-id="a35a3-123">Use the `NetStandardImplicitPackageVersion` property when you want to specify a framework version that's lower than the [metapackage](../packages.md#metapackages) version.</span></span> <span data-ttu-id="a35a3-124">以下示例中的项目文件以 `netstandard1.3` 为目标，但使用 `NETStandard.Library` 的 1.6.0 版本。</span><span class="sxs-lookup"><span data-stu-id="a35a3-124">The project file in the following example targets `netstandard1.3` but uses the 1.6.0 version of `NETStandard.Library`.</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <TargetFramework>netstandard1.3</TargetFramework>
    <NetStandardImplicitPackageVersion>1.6.0</NetStandardImplicitPackageVersion>
  </PropertyGroup>
</Project>
```

## <a name="publish-properties"></a><span data-ttu-id="a35a3-125">发布属性</span><span class="sxs-lookup"><span data-stu-id="a35a3-125">Publish properties</span></span>

- [<span data-ttu-id="a35a3-126">RuntimeIdentifier</span><span class="sxs-lookup"><span data-stu-id="a35a3-126">RuntimeIdentifier</span></span>](#runtimeidentifier)
- [<span data-ttu-id="a35a3-127">RuntimeIdentifiers</span><span class="sxs-lookup"><span data-stu-id="a35a3-127">RuntimeIdentifiers</span></span>](#runtimeidentifiers)
- [<span data-ttu-id="a35a3-128">UseAppHost</span><span class="sxs-lookup"><span data-stu-id="a35a3-128">UseAppHost</span></span>](#useapphost)

### <a name="runtimeidentifier"></a><span data-ttu-id="a35a3-129">RuntimeIdentifier</span><span class="sxs-lookup"><span data-stu-id="a35a3-129">RuntimeIdentifier</span></span>

<span data-ttu-id="a35a3-130">`RuntimeIdentifier` 属性可用于指定项目的单个[运行时标识符 (RID)](../rid-catalog.md)。</span><span class="sxs-lookup"><span data-stu-id="a35a3-130">The `RuntimeIdentifier` property lets you specify a single [runtime identifier (RID)](../rid-catalog.md) for the project.</span></span> <span data-ttu-id="a35a3-131">RID 支持发布独立部署。</span><span class="sxs-lookup"><span data-stu-id="a35a3-131">The RID enables publishing a self-contained deployment.</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <RuntimeIdentifier>ubuntu.16.04-x64</RuntimeIdentifier>
  </PropertyGroup>
</Project>
```

### <a name="runtimeidentifiers"></a><span data-ttu-id="a35a3-132">RuntimeIdentifiers</span><span class="sxs-lookup"><span data-stu-id="a35a3-132">RuntimeIdentifiers</span></span>

<span data-ttu-id="a35a3-133">`RuntimeIdentifiers` 属性可用于指定项目的[运行时标识符 (RID)](../rid-catalog.md) 的列表（以分号分隔）。</span><span class="sxs-lookup"><span data-stu-id="a35a3-133">The `RuntimeIdentifiers` property lets you specify a semicolon-delimited list of [runtime identifiers (RIDs)](../rid-catalog.md) for the project.</span></span> <span data-ttu-id="a35a3-134">如果需要为多个运行时发布，请使用此属性。</span><span class="sxs-lookup"><span data-stu-id="a35a3-134">Use this property if you need to publish for multiple runtimes.</span></span> <span data-ttu-id="a35a3-135">`RuntimeIdentifiers` 在还原时使用，以确保图中有适当的资产。</span><span class="sxs-lookup"><span data-stu-id="a35a3-135">`RuntimeIdentifiers` is used at restore time to ensure the right assets are in the graph.</span></span>

> [!TIP]
> <span data-ttu-id="a35a3-136">`RuntimeIdentifier`（单数）可以在只需要一个运行时时提供更快的生成。</span><span class="sxs-lookup"><span data-stu-id="a35a3-136">`RuntimeIdentifier` (singular) can provide faster builds when only a single runtime is required.</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <RuntimeIdentifiers>win10-x64;osx.10.11-x64;ubuntu.16.04-x64</RuntimeIdentifiers>
  </PropertyGroup>
</Project>
```

### <a name="useapphost"></a><span data-ttu-id="a35a3-137">UseAppHost</span><span class="sxs-lookup"><span data-stu-id="a35a3-137">UseAppHost</span></span>

<span data-ttu-id="a35a3-138">`UseAppHost` 属性是在 .NET Core SDK 的 2.1.400 版本中引入的。</span><span class="sxs-lookup"><span data-stu-id="a35a3-138">The `UseAppHost` property was introduced in the 2.1.400 version of the .NET Core SDK.</span></span> <span data-ttu-id="a35a3-139">它控制是否为部署创建本机可执行文件。</span><span class="sxs-lookup"><span data-stu-id="a35a3-139">It controls whether or not a native executable is created for a deployment.</span></span> <span data-ttu-id="a35a3-140">自包含部署需要本机可执行文件。</span><span class="sxs-lookup"><span data-stu-id="a35a3-140">A native executable is required for self-contained deployments.</span></span>

<span data-ttu-id="a35a3-141">在 .NET Core3.0 及更高版本中，默认情况下会创建依赖于框架的可执行文件。</span><span class="sxs-lookup"><span data-stu-id="a35a3-141">In .NET Core 3.0 and later versions, a framework-dependent executable is created by default.</span></span> <span data-ttu-id="a35a3-142">将 `UseAppHost` 属性设置为 `false` 可禁用可执行文件的生成。</span><span class="sxs-lookup"><span data-stu-id="a35a3-142">Set the `UseAppHost` property to `false` to disable generation of the executable.</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <UseAppHost>false</UseAppHost>
  </PropertyGroup>
</Project>
```

<span data-ttu-id="a35a3-143">有关部署的详细信息，请参阅 [.NET Core 应用程序部署](../deploying/index.md)。</span><span class="sxs-lookup"><span data-stu-id="a35a3-143">For more information about deployment, see [.NET Core application deployment](../deploying/index.md).</span></span>

## <a name="compile-properties"></a><span data-ttu-id="a35a3-144">编译属性</span><span class="sxs-lookup"><span data-stu-id="a35a3-144">Compile properties</span></span>

### <a name="langversion"></a><span data-ttu-id="a35a3-145">LangVersion</span><span class="sxs-lookup"><span data-stu-id="a35a3-145">LangVersion</span></span>

<span data-ttu-id="a35a3-146">`LangVersion` 属性可用于指定特定的编程语言版本。</span><span class="sxs-lookup"><span data-stu-id="a35a3-146">The `LangVersion` property lets you specify a specific programming language version.</span></span> <span data-ttu-id="a35a3-147">例如，如果要访问 C# 预览功能，请将 `LangVersion` 设置为 `preview`。</span><span class="sxs-lookup"><span data-stu-id="a35a3-147">For example, if you want access to C# preview features, set `LangVersion` to `preview`.</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <LangVersion>preview</LangVersion>
  </PropertyGroup>
</Project>
```

<span data-ttu-id="a35a3-148">有关详细信息，请参阅 [C# 语言版本控制](../../csharp/language-reference/configure-language-version.md#override-a-default)。</span><span class="sxs-lookup"><span data-stu-id="a35a3-148">For more information, see [C# language versioning](../../csharp/language-reference/configure-language-version.md#override-a-default).</span></span>

## <a name="nuget-packages"></a><span data-ttu-id="a35a3-149">NuGet 包</span><span class="sxs-lookup"><span data-stu-id="a35a3-149">NuGet packages</span></span>

- [<span data-ttu-id="a35a3-150">PackageReference</span><span class="sxs-lookup"><span data-stu-id="a35a3-150">PackageReference</span></span>](#packagereference)
- [<span data-ttu-id="a35a3-151">AssetTargetFallback</span><span class="sxs-lookup"><span data-stu-id="a35a3-151">AssetTargetFallback</span></span>](#assettargetfallback)

### <a name="packagereference"></a><span data-ttu-id="a35a3-152">PackageReference</span><span class="sxs-lookup"><span data-stu-id="a35a3-152">PackageReference</span></span>

<span data-ttu-id="a35a3-153">`PackageReference` 项可用于指定 NuGet 依赖项。</span><span class="sxs-lookup"><span data-stu-id="a35a3-153">The `PackageReference` item lets you specify a NuGet dependency.</span></span> <span data-ttu-id="a35a3-154">例如，你可能想要引用单个包而不是[元包](../packages.md#metapackages)。</span><span class="sxs-lookup"><span data-stu-id="a35a3-154">For example, you may want to reference a single package instead of a [metapackage](../packages.md#metapackages).</span></span> <span data-ttu-id="a35a3-155">`Include` 属性指定包 ID。</span><span class="sxs-lookup"><span data-stu-id="a35a3-155">The `Include` attribute specifies the package ID.</span></span> <span data-ttu-id="a35a3-156">以下示例中的项目文件片段引用 [System.Runtime](https://www.nuget.org/packages/System.Runtime/) 包。</span><span class="sxs-lookup"><span data-stu-id="a35a3-156">The project file snippet in the following example references the [System.Runtime](https://www.nuget.org/packages/System.Runtime/) package.</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">
  ...
  <ItemGroup>
    <PackageReference Include="System.Runtime" Version="4.3.0" />
  </ItemGroup>
</Project>
```

<span data-ttu-id="a35a3-157">有关详细信息，请参阅[项目文件中的包引用](/nuget/consume-packages/package-references-in-project-files)。</span><span class="sxs-lookup"><span data-stu-id="a35a3-157">For more information, see [Package references in project files](/nuget/consume-packages/package-references-in-project-files).</span></span>

### <a name="assettargetfallback"></a><span data-ttu-id="a35a3-158">AssetTargetFallback</span><span class="sxs-lookup"><span data-stu-id="a35a3-158">AssetTargetFallback</span></span>

<span data-ttu-id="a35a3-159">`AssetTargetFallback` 属性可用于为你的项目引用的项目以及你的项目所使用的 NuGet 包指定其他兼容的框架版本。</span><span class="sxs-lookup"><span data-stu-id="a35a3-159">The `AssetTargetFallback` property lets you specify additional compatible framework versions for projects that your project references and NuGet packages that your project consumes.</span></span> <span data-ttu-id="a35a3-160">例如，如果使用 `PackageReference` 指定包依赖项，但该包不包含与项目的 `TargetFramework` 兼容的资源，则可使用 `AssetTargetFallback` 属性。</span><span class="sxs-lookup"><span data-stu-id="a35a3-160">For example, if you specify a package dependency using `PackageReference` but that package doesn't contain assets that are compatible with your projects's `TargetFramework`, the `AssetTargetFallback` property comes into play.</span></span> <span data-ttu-id="a35a3-161">使用 `AssetTargetFallback` 中指定的每个目标框架重新检查引用包的兼容性。</span><span class="sxs-lookup"><span data-stu-id="a35a3-161">The compatibility of the referenced package is rechecked using each target framework that's specified in `AssetTargetFallback`.</span></span>

<span data-ttu-id="a35a3-162">可以将 `AssetTargetFallback` 属性设置为一个或多个[目标框架版本](../../standard/frameworks.md#supported-target-framework-versions)。</span><span class="sxs-lookup"><span data-stu-id="a35a3-162">You can set the `AssetTargetFallback` property to one or more [target framework versions](../../standard/frameworks.md#supported-target-framework-versions).</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">
  ...
  <PropertyGroup>
    <AssetTargetFallback>net461</AssetTargetFallback>
  </PropertyGroup>
</Project>
```

### <a name="pack-and-restore-targets"></a><span data-ttu-id="a35a3-163">包和还原目标</span><span class="sxs-lookup"><span data-stu-id="a35a3-163">Pack and restore targets</span></span>

<span data-ttu-id="a35a3-164">MSBuild 15.1 引入了 `pack` 和 `restore` 目标，用于创建和还原作为生成一部分的 NuGet 包。</span><span class="sxs-lookup"><span data-stu-id="a35a3-164">MSBuild 15.1 introduced `pack` and `restore` targets for creating and restoring NuGet packages as part of a build.</span></span> <span data-ttu-id="a35a3-165">有关这些目标（包括 `PackageTargetFallback`）的 MSBuild 属性的信息，请参阅[作为 MSBuild 目标的 NuGet 包和还原](/nuget/reference/msbuild-targets)。</span><span class="sxs-lookup"><span data-stu-id="a35a3-165">For information about the MSBuild properties for these targets, including `PackageTargetFallback`, see [NuGet pack and restore as MSBuild targets](/nuget/reference/msbuild-targets).</span></span>

## <a name="see-also"></a><span data-ttu-id="a35a3-166">请参阅</span><span class="sxs-lookup"><span data-stu-id="a35a3-166">See also</span></span>

- [<span data-ttu-id="a35a3-167">MSBuild 架构引用</span><span class="sxs-lookup"><span data-stu-id="a35a3-167">MSBuild schema reference</span></span>](/visualstudio/msbuild/msbuild-project-file-schema-reference)
- [<span data-ttu-id="a35a3-168">通用 MSBuild 属性</span><span class="sxs-lookup"><span data-stu-id="a35a3-168">Common MSBuild properties</span></span>](/visualstudio/msbuild/common-msbuild-project-properties)
- [<span data-ttu-id="a35a3-169">NuGet 包的 MSBuild 属性</span><span class="sxs-lookup"><span data-stu-id="a35a3-169">MSBuild properties for NuGet pack</span></span>](/nuget/reference/msbuild-targets#pack-target)
- [<span data-ttu-id="a35a3-170">NuGet 还原的 MSBuild 属性</span><span class="sxs-lookup"><span data-stu-id="a35a3-170">MSBuild properties for NuGet restore</span></span>](/nuget/reference/msbuild-targets#restore-properties)
- [<span data-ttu-id="a35a3-171">自定义生成</span><span class="sxs-lookup"><span data-stu-id="a35a3-171">Customize a build</span></span>](/visualstudio/msbuild/customize-your-build)
