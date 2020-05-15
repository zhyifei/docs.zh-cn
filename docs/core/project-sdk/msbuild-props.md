---
title: Microsoft.NET.Sdk 的 MSBuild 属性
description: .NET Core SDK 可以理解的 MSBuild 属性的引用。
ms.date: 02/14/2020
ms.topic: reference
ms.openlocfilehash: 800ff59310d8437d7f770bf20a5bdf37714f8515
ms.sourcegitcommit: de7f589de07a9979b6ac28f54c3e534a617d9425
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/05/2020
ms.locfileid: "82795568"
---
# <a name="msbuild-properties-for-net-core-sdk-projects"></a><span data-ttu-id="24d3f-103">.NET Core SDK 项目的 MSBuild 属性</span><span class="sxs-lookup"><span data-stu-id="24d3f-103">MSBuild properties for .NET Core SDK projects</span></span>

<span data-ttu-id="24d3f-104">本页介绍用于配置 .NET Core 项目的 MSBuild 属性。</span><span class="sxs-lookup"><span data-stu-id="24d3f-104">This page describes MSBuild properties for configuring .NET Core projects.</span></span> <span data-ttu-id="24d3f-105">可以将每个属性的元数据  指定为属性的子元素。</span><span class="sxs-lookup"><span data-stu-id="24d3f-105">You can specify *metadata* for each property as child elements of the property.</span></span>

> [!NOTE]
> <span data-ttu-id="24d3f-106">此页面正在运行中，未列出 .NET Core SDK 的所有有用的 MSBuild 属性。</span><span class="sxs-lookup"><span data-stu-id="24d3f-106">This page is a work in progress and does not list all of the useful MSBuild properties for the .NET Core SDK.</span></span> <span data-ttu-id="24d3f-107">有关通用 MSBuild 属性的列表，请参阅[通用 MSBuild 属性](/visualstudio/msbuild/common-msbuild-project-properties)。</span><span class="sxs-lookup"><span data-stu-id="24d3f-107">For a list of common MSBuild properties, see [Common MSBuild properties](/visualstudio/msbuild/common-msbuild-project-properties).</span></span>

## <a name="framework-properties"></a><span data-ttu-id="24d3f-108">框架属性</span><span class="sxs-lookup"><span data-stu-id="24d3f-108">Framework properties</span></span>

- [<span data-ttu-id="24d3f-109">TargetFramework</span><span class="sxs-lookup"><span data-stu-id="24d3f-109">TargetFramework</span></span>](#targetframework)
- [<span data-ttu-id="24d3f-110">TargetFrameworks</span><span class="sxs-lookup"><span data-stu-id="24d3f-110">TargetFrameworks</span></span>](#targetframeworks)
- [<span data-ttu-id="24d3f-111">NetStandardImplicitPackageVersion</span><span class="sxs-lookup"><span data-stu-id="24d3f-111">NetStandardImplicitPackageVersion</span></span>](#netstandardimplicitpackageversion)

### <a name="targetframework"></a><span data-ttu-id="24d3f-112">TargetFramework</span><span class="sxs-lookup"><span data-stu-id="24d3f-112">TargetFramework</span></span>

<span data-ttu-id="24d3f-113">`TargetFramework` 属性指定应用的目标框架版本，该版本隐式引用[元包](../packages.md#metapackages)。</span><span class="sxs-lookup"><span data-stu-id="24d3f-113">The `TargetFramework` property specifies the target framework version for the app, which implicitly references a [metapackage](../packages.md#metapackages).</span></span> <span data-ttu-id="24d3f-114">有关有效的目标框架名字对象的列表，请参阅 [SDK 样式项目中的目标框架](../../standard/frameworks.md#supported-target-framework-versions)。</span><span class="sxs-lookup"><span data-stu-id="24d3f-114">For a list of valid target framework monikers, see [Target frameworks in SDK-style projects](../../standard/frameworks.md#supported-target-framework-versions).</span></span>

```xml
<PropertyGroup>
  <TargetFramework>netcoreapp3.1</TargetFramework>
</PropertyGroup>
```

<span data-ttu-id="24d3f-115">有关详细信息，请参阅 [SDK 样式项目中的目标框架](../../standard/frameworks.md)。</span><span class="sxs-lookup"><span data-stu-id="24d3f-115">For more information, see [Target frameworks in SDK-style projects](../../standard/frameworks.md).</span></span>

### <a name="targetframeworks"></a><span data-ttu-id="24d3f-116">TargetFrameworks</span><span class="sxs-lookup"><span data-stu-id="24d3f-116">TargetFrameworks</span></span>

<span data-ttu-id="24d3f-117">如果希望应用面向多个平台，请使用 `TargetFrameworks` 属性。</span><span class="sxs-lookup"><span data-stu-id="24d3f-117">Use the `TargetFrameworks` property when you want your app to target multiple platforms.</span></span> <span data-ttu-id="24d3f-118">有关有效的目标框架名字对象的列表，请参阅 [SDK 样式项目中的目标框架](../../standard/frameworks.md#supported-target-framework-versions)。</span><span class="sxs-lookup"><span data-stu-id="24d3f-118">For a list of valid target framework monikers, see [Target frameworks in SDK-style projects](../../standard/frameworks.md#supported-target-framework-versions).</span></span>

> [!NOTE]
> <span data-ttu-id="24d3f-119">如果指定了 `TargetFramework`（单数），则忽略此属性。</span><span class="sxs-lookup"><span data-stu-id="24d3f-119">This property is ignored if `TargetFramework` (singular) is specified.</span></span>

```xml
<PropertyGroup>
  <TargetFrameworks>netcoreapp3.1;net462</TargetFrameworks>
</PropertyGroup>
```

<span data-ttu-id="24d3f-120">有关详细信息，请参阅 [SDK 样式项目中的目标框架](../../standard/frameworks.md)。</span><span class="sxs-lookup"><span data-stu-id="24d3f-120">For more information, see [Target frameworks in SDK-style projects](../../standard/frameworks.md).</span></span>

### <a name="netstandardimplicitpackageversion"></a><span data-ttu-id="24d3f-121">NetStandardImplicitPackageVersion</span><span class="sxs-lookup"><span data-stu-id="24d3f-121">NetStandardImplicitPackageVersion</span></span>

> [!NOTE]
> <span data-ttu-id="24d3f-122">此属性仅适用于使用 `netstandard1.x` 的项目。</span><span class="sxs-lookup"><span data-stu-id="24d3f-122">This property only applies to projects using `netstandard1.x`.</span></span> <span data-ttu-id="24d3f-123">它不适用于使用 `netstandard2.x` 的项目。</span><span class="sxs-lookup"><span data-stu-id="24d3f-123">It doesn't apply to projects that use `netstandard2.x`.</span></span>

<span data-ttu-id="24d3f-124">如果要指定低于[元包](../packages.md#metapackages)版本的框架版本，请使用 `NetStandardImplicitPackageVersion` 属性。</span><span class="sxs-lookup"><span data-stu-id="24d3f-124">Use the `NetStandardImplicitPackageVersion` property when you want to specify a framework version that's lower than the [metapackage](../packages.md#metapackages) version.</span></span> <span data-ttu-id="24d3f-125">以下示例中的项目文件以 `netstandard1.3` 为目标，但使用 `NETStandard.Library` 的 1.6.0 版本。</span><span class="sxs-lookup"><span data-stu-id="24d3f-125">The project file in the following example targets `netstandard1.3` but uses the 1.6.0 version of `NETStandard.Library`.</span></span>

```xml
<PropertyGroup>
  <TargetFramework>netstandard1.3</TargetFramework>
  <NetStandardImplicitPackageVersion>1.6.0</NetStandardImplicitPackageVersion>
</PropertyGroup>
```

## <a name="package-properties"></a><span data-ttu-id="24d3f-126">包属性</span><span class="sxs-lookup"><span data-stu-id="24d3f-126">Package properties</span></span>

<span data-ttu-id="24d3f-127">可以指定 `PackageId`、`PackageVersion`、`PackageIcon`、`Title` 和 `Description` 等属性来描述通过项目创建的包。</span><span class="sxs-lookup"><span data-stu-id="24d3f-127">You can specify properties such as `PackageId`, `PackageVersion`, `PackageIcon`, `Title`, and `Description` to describe the package that gets created from your project.</span></span> <span data-ttu-id="24d3f-128">若要了解这些属性和其他属性，请参阅[包目标](/nuget/reference/msbuild-targets#pack-target)。</span><span class="sxs-lookup"><span data-stu-id="24d3f-128">For information about these and other properties, see [pack target](/nuget/reference/msbuild-targets#pack-target).</span></span>

```xml
<PropertyGroup>
  ...
  <PackageId>ClassLibDotNetStandard</PackageId>
  <Version>1.0.0</Version>
  <Authors>John Doe</Authors>
  <Company>Contoso</Company>
</PropertyGroup>
```

## <a name="publish-properties"></a><span data-ttu-id="24d3f-129">发布属性</span><span class="sxs-lookup"><span data-stu-id="24d3f-129">Publish properties</span></span>

- [<span data-ttu-id="24d3f-130">RuntimeIdentifier</span><span class="sxs-lookup"><span data-stu-id="24d3f-130">RuntimeIdentifier</span></span>](#runtimeidentifier)
- [<span data-ttu-id="24d3f-131">RuntimeIdentifiers</span><span class="sxs-lookup"><span data-stu-id="24d3f-131">RuntimeIdentifiers</span></span>](#runtimeidentifiers)
- [<span data-ttu-id="24d3f-132">TrimmerRootAssembly</span><span class="sxs-lookup"><span data-stu-id="24d3f-132">TrimmerRootAssembly</span></span>](#trimmerrootassembly)
- [<span data-ttu-id="24d3f-133">UseAppHost</span><span class="sxs-lookup"><span data-stu-id="24d3f-133">UseAppHost</span></span>](#useapphost)

### <a name="runtimeidentifier"></a><span data-ttu-id="24d3f-134">RuntimeIdentifier</span><span class="sxs-lookup"><span data-stu-id="24d3f-134">RuntimeIdentifier</span></span>

<span data-ttu-id="24d3f-135">`RuntimeIdentifier` 属性可用于指定项目的单个[运行时标识符 (RID)](../rid-catalog.md)。</span><span class="sxs-lookup"><span data-stu-id="24d3f-135">The `RuntimeIdentifier` property lets you specify a single [runtime identifier (RID)](../rid-catalog.md) for the project.</span></span> <span data-ttu-id="24d3f-136">RID 支持发布独立部署。</span><span class="sxs-lookup"><span data-stu-id="24d3f-136">The RID enables publishing a self-contained deployment.</span></span>

```xml
<PropertyGroup>
  <RuntimeIdentifier>ubuntu.16.04-x64</RuntimeIdentifier>
</PropertyGroup>
```

### <a name="runtimeidentifiers"></a><span data-ttu-id="24d3f-137">RuntimeIdentifiers</span><span class="sxs-lookup"><span data-stu-id="24d3f-137">RuntimeIdentifiers</span></span>

<span data-ttu-id="24d3f-138">`RuntimeIdentifiers` 属性可用于指定项目的[运行时标识符 (RID)](../rid-catalog.md) 的列表（以分号分隔）。</span><span class="sxs-lookup"><span data-stu-id="24d3f-138">The `RuntimeIdentifiers` property lets you specify a semicolon-delimited list of [runtime identifiers (RIDs)](../rid-catalog.md) for the project.</span></span> <span data-ttu-id="24d3f-139">如果需要为多个运行时发布，请使用此属性。</span><span class="sxs-lookup"><span data-stu-id="24d3f-139">Use this property if you need to publish for multiple runtimes.</span></span> <span data-ttu-id="24d3f-140">`RuntimeIdentifiers` 在还原时使用，以确保图中有适当的资产。</span><span class="sxs-lookup"><span data-stu-id="24d3f-140">`RuntimeIdentifiers` is used at restore time to ensure the right assets are in the graph.</span></span>

> [!TIP]
> <span data-ttu-id="24d3f-141">`RuntimeIdentifier`（单数）可以在只需要一个运行时时提供更快的生成。</span><span class="sxs-lookup"><span data-stu-id="24d3f-141">`RuntimeIdentifier` (singular) can provide faster builds when only a single runtime is required.</span></span>

```xml
<PropertyGroup>
  <RuntimeIdentifiers>win10-x64;osx.10.11-x64;ubuntu.16.04-x64</RuntimeIdentifiers>
</PropertyGroup>
```

### <a name="trimmerrootassembly"></a><span data-ttu-id="24d3f-142">TrimmerRootAssembly</span><span class="sxs-lookup"><span data-stu-id="24d3f-142">TrimmerRootAssembly</span></span>

<span data-ttu-id="24d3f-143">`TrimmerRootAssembly` 项允许通过[修整](../deploying/trim-self-contained.md)排除程序集  。</span><span class="sxs-lookup"><span data-stu-id="24d3f-143">The `TrimmerRootAssembly` item lets you exclude an assembly from [*trimming*](../deploying/trim-self-contained.md).</span></span> <span data-ttu-id="24d3f-144">修整是从打包的应用程序中删除运行时未使用部分的过程。</span><span class="sxs-lookup"><span data-stu-id="24d3f-144">Trimming is the process of removing unused parts of the runtime from a packaged application.</span></span> <span data-ttu-id="24d3f-145">在某些情况下，修整可能会错误地删除所需的引用。</span><span class="sxs-lookup"><span data-stu-id="24d3f-145">In some cases, trimming might incorrectly remove required references.</span></span>

<span data-ttu-id="24d3f-146">以下 XML 通过修整排除 `System.Security` 程序集。</span><span class="sxs-lookup"><span data-stu-id="24d3f-146">The following XML excludes the `System.Security` assembly from trimming.</span></span>

```xml
<ItemGroup>
  <TrimmerRootAssembly Include="System.Security" />
</ItemGroup>
```

### <a name="useapphost"></a><span data-ttu-id="24d3f-147">UseAppHost</span><span class="sxs-lookup"><span data-stu-id="24d3f-147">UseAppHost</span></span>

<span data-ttu-id="24d3f-148">`UseAppHost` 属性是在 .NET Core SDK 的 2.1.400 版本中引入的。</span><span class="sxs-lookup"><span data-stu-id="24d3f-148">The `UseAppHost` property was introduced in the 2.1.400 version of the .NET Core SDK.</span></span> <span data-ttu-id="24d3f-149">它控制是否为部署创建本机可执行文件。</span><span class="sxs-lookup"><span data-stu-id="24d3f-149">It controls whether or not a native executable is created for a deployment.</span></span> <span data-ttu-id="24d3f-150">自包含部署需要本机可执行文件。</span><span class="sxs-lookup"><span data-stu-id="24d3f-150">A native executable is required for self-contained deployments.</span></span>

<span data-ttu-id="24d3f-151">在 .NET Core3.0 及更高版本中，默认情况下会创建依赖于框架的可执行文件。</span><span class="sxs-lookup"><span data-stu-id="24d3f-151">In .NET Core 3.0 and later versions, a framework-dependent executable is created by default.</span></span> <span data-ttu-id="24d3f-152">将 `UseAppHost` 属性设置为 `false` 可禁用可执行文件的生成。</span><span class="sxs-lookup"><span data-stu-id="24d3f-152">Set the `UseAppHost` property to `false` to disable generation of the executable.</span></span>

```xml
<PropertyGroup>
  <UseAppHost>false</UseAppHost>
</PropertyGroup>
```

<span data-ttu-id="24d3f-153">有关部署的详细信息，请参阅 [.NET Core 应用程序部署](../deploying/index.md)。</span><span class="sxs-lookup"><span data-stu-id="24d3f-153">For more information about deployment, see [.NET Core application deployment](../deploying/index.md).</span></span>

## <a name="compile-properties"></a><span data-ttu-id="24d3f-154">编译属性</span><span class="sxs-lookup"><span data-stu-id="24d3f-154">Compile properties</span></span>

- [<span data-ttu-id="24d3f-155">LangVersion</span><span class="sxs-lookup"><span data-stu-id="24d3f-155">LangVersion</span></span>](#langversion)

### <a name="langversion"></a><span data-ttu-id="24d3f-156">LangVersion</span><span class="sxs-lookup"><span data-stu-id="24d3f-156">LangVersion</span></span>

<span data-ttu-id="24d3f-157">`LangVersion` 属性可用于指定特定的编程语言版本。</span><span class="sxs-lookup"><span data-stu-id="24d3f-157">The `LangVersion` property lets you specify a specific programming language version.</span></span> <span data-ttu-id="24d3f-158">例如，如果要访问 C# 预览功能，请将 `LangVersion` 设置为 `preview`。</span><span class="sxs-lookup"><span data-stu-id="24d3f-158">For example, if you want access to C# preview features, set `LangVersion` to `preview`.</span></span>

```xml
<PropertyGroup>
  <LangVersion>preview</LangVersion>
</PropertyGroup>
```

<span data-ttu-id="24d3f-159">有关详细信息，请参阅 [C# 语言版本控制](../../csharp/language-reference/configure-language-version.md#override-a-default)。</span><span class="sxs-lookup"><span data-stu-id="24d3f-159">For more information, see [C# language versioning](../../csharp/language-reference/configure-language-version.md#override-a-default).</span></span>

## <a name="run-time-configuration-properties"></a><span data-ttu-id="24d3f-160">运行时配置属性</span><span class="sxs-lookup"><span data-stu-id="24d3f-160">Run-time configuration properties</span></span>

<span data-ttu-id="24d3f-161">可以通过在应用的项目文件中指定 MSBuild 属性来配置某些运行时行为。</span><span class="sxs-lookup"><span data-stu-id="24d3f-161">You can configure some run-time behaviors by specifying MSBuild properties in the project file of the app.</span></span> <span data-ttu-id="24d3f-162">有关配置运行时行为的其他方法的信息，请参阅 [.NET Core 运行时配置设置](../run-time-config/index.md)。</span><span class="sxs-lookup"><span data-stu-id="24d3f-162">For information about other ways of configuring run-time behavior, see [.NET Core run-time configuration settings](../run-time-config/index.md).</span></span>

- [<span data-ttu-id="24d3f-163">ConcurrentGarbageCollection</span><span class="sxs-lookup"><span data-stu-id="24d3f-163">ConcurrentGarbageCollection</span></span>](#concurrentgarbagecollection)
- [<span data-ttu-id="24d3f-164">InvariantGlobalization</span><span class="sxs-lookup"><span data-stu-id="24d3f-164">InvariantGlobalization</span></span>](#invariantglobalization)
- [<span data-ttu-id="24d3f-165">RetainVMGarbageCollection</span><span class="sxs-lookup"><span data-stu-id="24d3f-165">RetainVMGarbageCollection</span></span>](#retainvmgarbagecollection)
- [<span data-ttu-id="24d3f-166">ServerGarbageCollection</span><span class="sxs-lookup"><span data-stu-id="24d3f-166">ServerGarbageCollection</span></span>](#servergarbagecollection)
- [<span data-ttu-id="24d3f-167">ThreadPoolMaxThreads</span><span class="sxs-lookup"><span data-stu-id="24d3f-167">ThreadPoolMaxThreads</span></span>](#threadpoolmaxthreads)
- [<span data-ttu-id="24d3f-168">ThreadPoolMinThreads</span><span class="sxs-lookup"><span data-stu-id="24d3f-168">ThreadPoolMinThreads</span></span>](#threadpoolminthreads)
- [<span data-ttu-id="24d3f-169">TieredCompilation</span><span class="sxs-lookup"><span data-stu-id="24d3f-169">TieredCompilation</span></span>](#tieredcompilation)
- [<span data-ttu-id="24d3f-170">TieredCompilationQuickJit</span><span class="sxs-lookup"><span data-stu-id="24d3f-170">TieredCompilationQuickJit</span></span>](#tieredcompilationquickjit)
- [<span data-ttu-id="24d3f-171">TieredCompilationQuickJitForLoops</span><span class="sxs-lookup"><span data-stu-id="24d3f-171">TieredCompilationQuickJitForLoops</span></span>](#tieredcompilationquickjitforloops)

### <a name="concurrentgarbagecollection"></a><span data-ttu-id="24d3f-172">ConcurrentGarbageCollection</span><span class="sxs-lookup"><span data-stu-id="24d3f-172">ConcurrentGarbageCollection</span></span>

<span data-ttu-id="24d3f-173">`ConcurrentGarbageCollection` 属性配置是否启用 [后台（并发）垃圾回收](../../standard/garbage-collection/background-gc.md)。</span><span class="sxs-lookup"><span data-stu-id="24d3f-173">The `ConcurrentGarbageCollection` property configures whether [background (concurrent) garbage collection](../../standard/garbage-collection/background-gc.md) is enabled.</span></span> <span data-ttu-id="24d3f-174">将值设置为 `false` 以禁用后台垃圾回收。</span><span class="sxs-lookup"><span data-stu-id="24d3f-174">Set the value to `false` to disable background garbage collection.</span></span> <span data-ttu-id="24d3f-175">有关详细信息，请参阅 [System.GC.Concurrent/COMPlus_gcConcurrent](../run-time-config/garbage-collector.md#systemgcconcurrentcomplus_gcconcurrent)。</span><span class="sxs-lookup"><span data-stu-id="24d3f-175">For more information, see [System.GC.Concurrent/COMPlus_gcConcurrent](../run-time-config/garbage-collector.md#systemgcconcurrentcomplus_gcconcurrent).</span></span>

```xml
<PropertyGroup>
  <ConcurrentGarbageCollection>false</ConcurrentGarbageCollection>
</PropertyGroup>
```

### <a name="invariantglobalization"></a><span data-ttu-id="24d3f-176">InvariantGlobalization</span><span class="sxs-lookup"><span data-stu-id="24d3f-176">InvariantGlobalization</span></span>

<span data-ttu-id="24d3f-177">`InvariantGlobalization` 属性配置应用是否在全球化固定模式下运行，这意味着它无权访问特定于区域性的数据  。</span><span class="sxs-lookup"><span data-stu-id="24d3f-177">The `InvariantGlobalization` property configures whether the app runs in *globalization-invariant* mode, which means it doesn't have access to culture-specific data.</span></span> <span data-ttu-id="24d3f-178">将值设置为 `true` 以在全球化固定模式下运行。</span><span class="sxs-lookup"><span data-stu-id="24d3f-178">Set the value to `true` to run in globalization-invariant mode.</span></span> <span data-ttu-id="24d3f-179">有关详细信息，请参阅[固定模式](../run-time-config/globalization.md#invariant-mode)。</span><span class="sxs-lookup"><span data-stu-id="24d3f-179">For more information, see [Invariant mode](../run-time-config/globalization.md#invariant-mode).</span></span>

```xml
<PropertyGroup>
  <InvariantGlobalization>true</InvariantGlobalization>
</PropertyGroup>
```

### <a name="retainvmgarbagecollection"></a><span data-ttu-id="24d3f-180">RetainVMGarbageCollection</span><span class="sxs-lookup"><span data-stu-id="24d3f-180">RetainVMGarbageCollection</span></span>

<span data-ttu-id="24d3f-181">`RetainVMGarbageCollection` 属性配置垃圾回收器，以将已删除的内存段放置在备用列表上供将来使用或释放它们。</span><span class="sxs-lookup"><span data-stu-id="24d3f-181">The `RetainVMGarbageCollection` property configures the garbage collector to put deleted memory segments on a standby list for future use or release them.</span></span> <span data-ttu-id="24d3f-182">将值设置为 `true` 会告知垃圾回收器将段放在备用列表上。</span><span class="sxs-lookup"><span data-stu-id="24d3f-182">Setting the value to `true` tells the garbage collector to put the segments on a standby list.</span></span> <span data-ttu-id="24d3f-183">有关详细信息，请参阅 [System.GC.RetainVM/COMPlus_GCRetainVM](../run-time-config/garbage-collector.md#systemgcretainvmcomplus_gcretainvm)。</span><span class="sxs-lookup"><span data-stu-id="24d3f-183">For more information, see [System.GC.RetainVM/COMPlus_GCRetainVM](../run-time-config/garbage-collector.md#systemgcretainvmcomplus_gcretainvm).</span></span>

```xml
<PropertyGroup>
  <RetainVMGarbageCollection>true</RetainVMGarbageCollection>
</PropertyGroup>
```

### <a name="servergarbagecollection"></a><span data-ttu-id="24d3f-184">ServerGarbageCollection</span><span class="sxs-lookup"><span data-stu-id="24d3f-184">ServerGarbageCollection</span></span>

<span data-ttu-id="24d3f-185">`ServerGarbageCollection` 属性配置应用程序是使用[工作站垃圾回收还是服务器垃圾回收](../../standard/garbage-collection/workstation-server-gc.md)。</span><span class="sxs-lookup"><span data-stu-id="24d3f-185">The `ServerGarbageCollection` property configures whether the application uses [workstation garbage collection or server garbage collection](../../standard/garbage-collection/workstation-server-gc.md).</span></span> <span data-ttu-id="24d3f-186">将值设置为 `true` 以使用服务器垃圾回收。</span><span class="sxs-lookup"><span data-stu-id="24d3f-186">Set the value to `true` to use server garbage collection.</span></span> <span data-ttu-id="24d3f-187">有关详细信息，请参阅 [System.GC.Server/COMPlus_gcServer](../run-time-config/garbage-collector.md#systemgcservercomplus_gcserver)。</span><span class="sxs-lookup"><span data-stu-id="24d3f-187">For more information, see [System.GC.Server/COMPlus_gcServer](../run-time-config/garbage-collector.md#systemgcservercomplus_gcserver).</span></span>

```xml
<PropertyGroup>
  <ServerGarbageCollection>true</ServerGarbageCollection>
</PropertyGroup>
```

### <a name="threadpoolmaxthreads"></a><span data-ttu-id="24d3f-188">ThreadPoolMaxThreads</span><span class="sxs-lookup"><span data-stu-id="24d3f-188">ThreadPoolMaxThreads</span></span>

<span data-ttu-id="24d3f-189">`ThreadPoolMaxThreads` 属性配置工作线程池的最大线程数。</span><span class="sxs-lookup"><span data-stu-id="24d3f-189">The `ThreadPoolMaxThreads` property configures the maximum number of threads for the worker thread pool.</span></span> <span data-ttu-id="24d3f-190">有关详细信息，请参阅[最大线程数](../run-time-config/threading.md#maximum-threads)。</span><span class="sxs-lookup"><span data-stu-id="24d3f-190">For more information, see [Maximum threads](../run-time-config/threading.md#maximum-threads).</span></span>

```xml
<PropertyGroup>
  <ThreadPoolMaxThreads>20</ThreadPoolMaxThreads>
</PropertyGroup>
```

### <a name="threadpoolminthreads"></a><span data-ttu-id="24d3f-191">ThreadPoolMinThreads</span><span class="sxs-lookup"><span data-stu-id="24d3f-191">ThreadPoolMinThreads</span></span>

<span data-ttu-id="24d3f-192">`ThreadPoolMinThreads` 属性配置工作线程池的最小线程数。</span><span class="sxs-lookup"><span data-stu-id="24d3f-192">The `ThreadPoolMinThreads` property configures the minimum number of threads for the worker thread pool.</span></span> <span data-ttu-id="24d3f-193">有关详细信息，请参阅[最小线程数](../run-time-config/threading.md#minimum-threads)。</span><span class="sxs-lookup"><span data-stu-id="24d3f-193">For more information, see [Minimum threads](../run-time-config/threading.md#minimum-threads).</span></span>

```xml
<PropertyGroup>
  <ThreadPoolMinThreads>4</ThreadPoolMinThreads>
</PropertyGroup>
```

### <a name="tieredcompilation"></a><span data-ttu-id="24d3f-194">TieredCompilation</span><span class="sxs-lookup"><span data-stu-id="24d3f-194">TieredCompilation</span></span>

<span data-ttu-id="24d3f-195">`TieredCompilation` 属性配置实时 (JIT) 编译器是否使用[分层编译](../whats-new/dotnet-core-3-0.md#tiered-compilation)。</span><span class="sxs-lookup"><span data-stu-id="24d3f-195">The `TieredCompilation` property configures whether the just-in-time (JIT) compiler uses [tiered compilation](../whats-new/dotnet-core-3-0.md#tiered-compilation).</span></span> <span data-ttu-id="24d3f-196">将值设置为 `false` 以禁用分层编译。</span><span class="sxs-lookup"><span data-stu-id="24d3f-196">Set the value to `false` to disable tiered compilation.</span></span> <span data-ttu-id="24d3f-197">有关详细信息，请参阅[分层编译](../run-time-config/compilation.md#tiered-compilation)。</span><span class="sxs-lookup"><span data-stu-id="24d3f-197">For more information, see [Tiered compilation](../run-time-config/compilation.md#tiered-compilation).</span></span>

```xml
<PropertyGroup>
  <TieredCompilation>false</TieredCompilation>
</PropertyGroup>
```

### <a name="tieredcompilationquickjit"></a><span data-ttu-id="24d3f-198">TieredCompilationQuickJit</span><span class="sxs-lookup"><span data-stu-id="24d3f-198">TieredCompilationQuickJit</span></span>

<span data-ttu-id="24d3f-199">`TieredCompilationQuickJit` 属性配置 JIT 编译器是否使用快速 JIT。</span><span class="sxs-lookup"><span data-stu-id="24d3f-199">The `TieredCompilationQuickJit` property configures whether the JIT compiler uses quick JIT.</span></span> <span data-ttu-id="24d3f-200">将值设置为 `false` 以禁用快速 JIT。</span><span class="sxs-lookup"><span data-stu-id="24d3f-200">Set the value to `false` to disable quick JIT.</span></span> <span data-ttu-id="24d3f-201">有关详细信息，请参阅[快速 JIT](../run-time-config/compilation.md#quick-jit)。</span><span class="sxs-lookup"><span data-stu-id="24d3f-201">For more information, see [Quick JIT](../run-time-config/compilation.md#quick-jit).</span></span>

```xml
<PropertyGroup>
  <TieredCompilationQuickJit>false</TieredCompilationQuickJit>
</PropertyGroup>
```

### <a name="tieredcompilationquickjitforloops"></a><span data-ttu-id="24d3f-202">TieredCompilationQuickJitForLoops</span><span class="sxs-lookup"><span data-stu-id="24d3f-202">TieredCompilationQuickJitForLoops</span></span>

<span data-ttu-id="24d3f-203">`TieredCompilationQuickJitForLoops` 配置 JIT 编译器是否对包含循环的方法使用快速 JIT。</span><span class="sxs-lookup"><span data-stu-id="24d3f-203">The `TieredCompilationQuickJitForLoops` property configures whether the JIT compiler uses quick JIT on methods that contain loops.</span></span> <span data-ttu-id="24d3f-204">将值设置为 `true` 以对包含循环的方法启用快速 JIT。</span><span class="sxs-lookup"><span data-stu-id="24d3f-204">Set the value to `true` to enable quick JIT on methods that contain loops.</span></span> <span data-ttu-id="24d3f-205">有关详细信息，请参阅[适用于循环的快速 JIT](../run-time-config/compilation.md#quick-jit-for-loops)。</span><span class="sxs-lookup"><span data-stu-id="24d3f-205">For more information, see [Quick JIT for loops](../run-time-config/compilation.md#quick-jit-for-loops).</span></span>

```xml
<PropertyGroup>
  <TieredCompilationQuickJitForLoops>true</TieredCompilationQuickJitForLoops>
</PropertyGroup>
```

## <a name="reference-properties"></a><span data-ttu-id="24d3f-206">引用属性</span><span class="sxs-lookup"><span data-stu-id="24d3f-206">Reference properties</span></span>

- [<span data-ttu-id="24d3f-207">AssetTargetFallback</span><span class="sxs-lookup"><span data-stu-id="24d3f-207">AssetTargetFallback</span></span>](#assettargetfallback)
- [<span data-ttu-id="24d3f-208">PackageReference</span><span class="sxs-lookup"><span data-stu-id="24d3f-208">PackageReference</span></span>](#packagereference)
- [<span data-ttu-id="24d3f-209">ProjectReference</span><span class="sxs-lookup"><span data-stu-id="24d3f-209">ProjectReference</span></span>](#projectreference)
- [<span data-ttu-id="24d3f-210">引用</span><span class="sxs-lookup"><span data-stu-id="24d3f-210">Reference</span></span>](#reference)
- [<span data-ttu-id="24d3f-211">还原属性</span><span class="sxs-lookup"><span data-stu-id="24d3f-211">Restore properties</span></span>](#restore-properties)

### <a name="assettargetfallback"></a><span data-ttu-id="24d3f-212">AssetTargetFallback</span><span class="sxs-lookup"><span data-stu-id="24d3f-212">AssetTargetFallback</span></span>

<span data-ttu-id="24d3f-213">使用 `AssetTargetFallback` 属性，可以为项目引用和 NuGet 包指定其他兼容的框架版本。</span><span class="sxs-lookup"><span data-stu-id="24d3f-213">The `AssetTargetFallback` property lets you specify additional compatible framework versions for project references and NuGet packages.</span></span> <span data-ttu-id="24d3f-214">例如，如果使用 `PackageReference` 指定包依赖项，但该包不包含与项目的 `TargetFramework` 兼容的资源，则可使用 `AssetTargetFallback` 属性。</span><span class="sxs-lookup"><span data-stu-id="24d3f-214">For example, if you specify a package dependency using `PackageReference` but that package doesn't contain assets that are compatible with your projects's `TargetFramework`, the `AssetTargetFallback` property comes into play.</span></span> <span data-ttu-id="24d3f-215">使用 `AssetTargetFallback` 中指定的每个目标框架重新检查引用包的兼容性。</span><span class="sxs-lookup"><span data-stu-id="24d3f-215">The compatibility of the referenced package is rechecked using each target framework that's specified in `AssetTargetFallback`.</span></span>

<span data-ttu-id="24d3f-216">可以将 `AssetTargetFallback` 属性设置为一个或多个[目标框架版本](../../standard/frameworks.md#supported-target-framework-versions)。</span><span class="sxs-lookup"><span data-stu-id="24d3f-216">You can set the `AssetTargetFallback` property to one or more [target framework versions](../../standard/frameworks.md#supported-target-framework-versions).</span></span>

```xml
<PropertyGroup>
  <AssetTargetFallback>net461</AssetTargetFallback>
</PropertyGroup>
```

### <a name="packagereference"></a><span data-ttu-id="24d3f-217">PackageReference</span><span class="sxs-lookup"><span data-stu-id="24d3f-217">PackageReference</span></span>

<span data-ttu-id="24d3f-218">`PackageReference` 定义对 NuGet 包的引用。</span><span class="sxs-lookup"><span data-stu-id="24d3f-218">The `PackageReference` defines a reference to a NuGet package.</span></span> <span data-ttu-id="24d3f-219">例如，你可能想要引用单个包而不是[元包](../packages.md#metapackages)。</span><span class="sxs-lookup"><span data-stu-id="24d3f-219">For example, you may want to reference a single package instead of a [metapackage](../packages.md#metapackages).</span></span>

<span data-ttu-id="24d3f-220">`Include` 属性指定包 ID。</span><span class="sxs-lookup"><span data-stu-id="24d3f-220">The `Include` attribute specifies the package ID.</span></span> <span data-ttu-id="24d3f-221">`Version` 特性指定版本或版本范围。</span><span class="sxs-lookup"><span data-stu-id="24d3f-221">The `Version` attribute specifies the version or version range.</span></span> <span data-ttu-id="24d3f-222">若要了解如何指定最低版本、最高版本、范围或完全匹配，请参阅[版本范围](/nuget/concepts/package-versioning#version-ranges)。</span><span class="sxs-lookup"><span data-stu-id="24d3f-222">For information about how to specify a minimum version, maximum version, range, or exact match, see [Version ranges](/nuget/concepts/package-versioning#version-ranges).</span></span> <span data-ttu-id="24d3f-223">还可以将下面的元数据添加到项目引用中：`IncludeAssets`、`ExcludeAssets` 和 `PrivateAssets`。</span><span class="sxs-lookup"><span data-stu-id="24d3f-223">You can also add the following metadata to a project reference: `IncludeAssets`, `ExcludeAssets`, and `PrivateAssets`.</span></span>

<span data-ttu-id="24d3f-224">以下示例中的项目文件片段引用 [System.Runtime](https://www.nuget.org/packages/System.Runtime/) 包。</span><span class="sxs-lookup"><span data-stu-id="24d3f-224">The project file snippet in the following example references the [System.Runtime](https://www.nuget.org/packages/System.Runtime/) package.</span></span>

```xml
<ItemGroup>
  <PackageReference Include="System.Runtime" Version="4.3.0" />
</ItemGroup>
```

<span data-ttu-id="24d3f-225">有关详细信息，请参阅[项目文件中的包引用](/nuget/consume-packages/package-references-in-project-files)。</span><span class="sxs-lookup"><span data-stu-id="24d3f-225">For more information, see [Package references in project files](/nuget/consume-packages/package-references-in-project-files).</span></span>

### <a name="projectreference"></a><span data-ttu-id="24d3f-226">ProjectReference</span><span class="sxs-lookup"><span data-stu-id="24d3f-226">ProjectReference</span></span>

<span data-ttu-id="24d3f-227">`ProjectReference` 项定义对另一个项目的引用。</span><span class="sxs-lookup"><span data-stu-id="24d3f-227">The `ProjectReference` item defines a reference to another project.</span></span> <span data-ttu-id="24d3f-228">被引用的项目作为 NuGet 包依赖项添加，即它被视为与 `PackageReference` 相同。</span><span class="sxs-lookup"><span data-stu-id="24d3f-228">The referenced project is added as a NuGet package dependency, that is, it's treated the same as a `PackageReference`.</span></span>

<span data-ttu-id="24d3f-229">`Include` 特性指定项目路径。</span><span class="sxs-lookup"><span data-stu-id="24d3f-229">The `Include` attribute specifies the path to the project.</span></span> <span data-ttu-id="24d3f-230">还可以将下面的元数据添加到项目引用中：`IncludeAssets`、`ExcludeAssets` 和 `PrivateAssets`。</span><span class="sxs-lookup"><span data-stu-id="24d3f-230">You can also add the following metadata to a project reference: `IncludeAssets`, `ExcludeAssets`, and `PrivateAssets`.</span></span>

<span data-ttu-id="24d3f-231">以下示例中的项目文件片段引用名为 `Project2` 的项目。</span><span class="sxs-lookup"><span data-stu-id="24d3f-231">The project file snippet in the following example references a project named `Project2`.</span></span>

```xml
<ItemGroup>
  <ProjectReference Include="..\Project2.csproj" />
</ItemGroup>
```

### <a name="reference"></a><span data-ttu-id="24d3f-232">参考</span><span class="sxs-lookup"><span data-stu-id="24d3f-232">Reference</span></span>

<span data-ttu-id="24d3f-233">`Reference` 项定义对程序集文件的引用。</span><span class="sxs-lookup"><span data-stu-id="24d3f-233">The `Reference` item defines a reference to an assembly file.</span></span>

<span data-ttu-id="24d3f-234">`Include` 特性指定文件名，`HintPath` 子元素指定程序集路径。</span><span class="sxs-lookup"><span data-stu-id="24d3f-234">The `Include` attribute specifies the name of the file, and the `HintPath` child element specifies the path to the assembly.</span></span>

```xml
<ItemGroup>
  <Reference Include="MyAssembly">
    <HintPath>..\..\Assemblies\MyAssembly.dll</HintPath>
  </Reference>
</ItemGroup>
```

### <a name="restore-properties"></a><span data-ttu-id="24d3f-235">还原属性</span><span class="sxs-lookup"><span data-stu-id="24d3f-235">Restore properties</span></span>

<span data-ttu-id="24d3f-236">还原被引用的包会安装它的所有直接依赖项，以及这些依赖项的全部依赖项。</span><span class="sxs-lookup"><span data-stu-id="24d3f-236">Restoring a referenced package installs all of its direct dependencies and all the dependencies of those dependencies.</span></span> <span data-ttu-id="24d3f-237">可以通过指定 `RestorePackagesPath` 和 `RestoreIgnoreFailedSources` 等属性来自定义包还原。</span><span class="sxs-lookup"><span data-stu-id="24d3f-237">You can customize package restoration by specifying properties such as `RestorePackagesPath` and `RestoreIgnoreFailedSources`.</span></span> <span data-ttu-id="24d3f-238">若要详细了解这些属性和其他属性，请参阅[还原目标](/nuget/reference/msbuild-targets#restore-target)。</span><span class="sxs-lookup"><span data-stu-id="24d3f-238">For more information about these and other properties, see [restore target](/nuget/reference/msbuild-targets#restore-target).</span></span>

```xml
<PropertyGroup>
  <RestoreIgnoreFailedSource>true</RestoreIgnoreFailedSource>
</PropertyGroup>
```

## <a name="see-also"></a><span data-ttu-id="24d3f-239">请参阅</span><span class="sxs-lookup"><span data-stu-id="24d3f-239">See also</span></span>

- [<span data-ttu-id="24d3f-240">MSBuild 架构引用</span><span class="sxs-lookup"><span data-stu-id="24d3f-240">MSBuild schema reference</span></span>](/visualstudio/msbuild/msbuild-project-file-schema-reference)
- [<span data-ttu-id="24d3f-241">通用 MSBuild 属性</span><span class="sxs-lookup"><span data-stu-id="24d3f-241">Common MSBuild properties</span></span>](/visualstudio/msbuild/common-msbuild-project-properties)
- [<span data-ttu-id="24d3f-242">NuGet 包的 MSBuild 属性</span><span class="sxs-lookup"><span data-stu-id="24d3f-242">MSBuild properties for NuGet pack</span></span>](/nuget/reference/msbuild-targets#pack-target)
- [<span data-ttu-id="24d3f-243">NuGet 还原的 MSBuild 属性</span><span class="sxs-lookup"><span data-stu-id="24d3f-243">MSBuild properties for NuGet restore</span></span>](/nuget/reference/msbuild-targets#restore-properties)
- [<span data-ttu-id="24d3f-244">自定义生成</span><span class="sxs-lookup"><span data-stu-id="24d3f-244">Customize a build</span></span>](/visualstudio/msbuild/customize-your-build)
