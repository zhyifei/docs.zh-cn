---
title: "目标框架"
description: "了解用于 .NET Core 应用和库的目标框架。"
keywords: ".NET, .NET Core, 框架, TFM"
author: richlander
ms.author: mairaw
ms.date: 08/25/2017
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.assetid: 6ef56a2e-593d-497b-925a-1e25bb6df2e6
ms.translationtype: HT
ms.sourcegitcommit: 18b2f7a1c0857abb5f7e09a39ca120b521ba4ddc
ms.openlocfilehash: 7f25cdd52cf5249d3b201978eacb98aaa4a74fa9
ms.contentlocale: zh-cn
ms.lasthandoff: 08/25/2017

---

# <a name="target-frameworks"></a><span data-ttu-id="17783-104">目标框架</span><span class="sxs-lookup"><span data-stu-id="17783-104">Target frameworks</span></span>

<span data-ttu-id="17783-105">以应用或库中的框架为目标时，需要指定想要向应用或库提供的 API 集。</span><span class="sxs-lookup"><span data-stu-id="17783-105">When you target a framework in an app or library, you're specifying the set of APIs that you'd like to make available to the app or library.</span></span> <span data-ttu-id="17783-106">使用目标框架名字对象 (TFM) 在项目文件中指定目标框架。</span><span class="sxs-lookup"><span data-stu-id="17783-106">You specify the target framework in your project file using Target Framework Monikers (TFMs).</span></span>

<span data-ttu-id="17783-107">应用或库可以使用 [.NET Standard](~/docs/standard/net-standard.md) 版本作为目标。</span><span class="sxs-lookup"><span data-stu-id="17783-107">An app or library can target a version of [.NET Standard](~/docs/standard/net-standard.md).</span></span> <span data-ttu-id="17783-108">.NET Standard 版本表示所有 .NET 实现中的标准化 API 集。</span><span class="sxs-lookup"><span data-stu-id="17783-108">.NET Standard versions represent standardized sets of APIs across all .NET implementations.</span></span> <span data-ttu-id="17783-109">例如，库可以使用 .NET Standard 1.6 作为目标，并获得对可使用相同基本代码跨 .NET Core 和 .NET Framework 工作的 API 的访问权限。</span><span class="sxs-lookup"><span data-stu-id="17783-109">For example, a library can target .NET Standard 1.6 and gain access to APIs that function across .NET Core and .NET Framework using the same codebase.</span></span>

<span data-ttu-id="17783-110">应用或库还能以一个特定 .NET 实现为目标，获得特定于实现的 API 的访问权限。</span><span class="sxs-lookup"><span data-stu-id="17783-110">An app or library can also target a specific .NET implementation to gain access to implementation-specific APIs.</span></span> <span data-ttu-id="17783-111">例如，面向 Xamarin.iOS 的应用（如 `Xamarin.iOS10`）有权访问 Xamarin 提供的适用于 iOS 10 的 iOS API 包装器；面向通用 Windows 平台 (UWP) 的应用（如 `uap10.0`）有权访问为运行 Windows 10 的设备编译的 API。</span><span class="sxs-lookup"><span data-stu-id="17783-111">For example, an app that targets Xamarin.iOS (for example, `Xamarin.iOS10`) gets access to Xamarin-provided iOS API wrappers for iOS 10, or an app that targets the Universal Windows Platform (UWP, `uap10.0`) has access to APIs that compile for devices that run Windows 10.</span></span>

<span data-ttu-id="17783-112">对于某些目标框架（例如 .NET Framework），API 由框架在系统上安装的程序集定义，并且可能包括应用程序框架 API（例如 ASP.NET）。</span><span class="sxs-lookup"><span data-stu-id="17783-112">For some target frameworks (for example, the .NET Framework), the APIs are defined by the assemblies that the framework installs on a system and may include application framework APIs (for example, ASP.NET).</span></span>

<span data-ttu-id="17783-113">对于基于包的目标框架（例如 .NET Standard 和 .NET Core），API 由包含在应用或库中的包定义。</span><span class="sxs-lookup"><span data-stu-id="17783-113">For package-based target frameworks (for example, .NET Standard and .NET Core), the APIs are defined by the packages included in the app or library.</span></span> <span data-ttu-id="17783-114">元包是一个 NuGet 包，NuGet 包本身不包含任何内容，只是一个依赖项列表（其他包）。</span><span class="sxs-lookup"><span data-stu-id="17783-114">A *metapackage* is a NuGet package that has no content of its own but is a list of dependencies (other packages).</span></span> <span data-ttu-id="17783-115">基于 NuGet 包的目标框架隐式指定一个元包，该元包引用一起构成框架的所有包。</span><span class="sxs-lookup"><span data-stu-id="17783-115">A NuGet package-based target framework implicitly specifies a metapackage that references all the packages that together make up the framework.</span></span>

## <a name="latest-target-framework-versions"></a><span data-ttu-id="17783-116">最新目标框架版本</span><span class="sxs-lookup"><span data-stu-id="17783-116">Latest target framework versions</span></span>

<span data-ttu-id="17783-117">下表定义了最常见的目标框架、如何引用这些框架，以及它们实现的 [.NET Standard](~/docs/standard/net-standard.md) 版本。</span><span class="sxs-lookup"><span data-stu-id="17783-117">The following table defines the most common target frameworks, how they're referenced, and which version of the [.NET Standard](~/docs/standard/net-standard.md) they implement.</span></span> <span data-ttu-id="17783-118">这些目标框架版本是最新的稳定版本。</span><span class="sxs-lookup"><span data-stu-id="17783-118">These target framework versions are the latest stable versions.</span></span> <span data-ttu-id="17783-119">预览版不会显示。</span><span class="sxs-lookup"><span data-stu-id="17783-119">Pre-release versions aren't shown.</span></span> <span data-ttu-id="17783-120">目标框架名字对象 (TFM) 是一个标准化令牌格式，用于指定 .NET 应用或库的目标框架。</span><span class="sxs-lookup"><span data-stu-id="17783-120">A Target Framework Moniker (TFM) is a standardized token format for specifying the target framework of a .NET app or library.</span></span> 

| <span data-ttu-id="17783-121">目标 Framework</span><span class="sxs-lookup"><span data-stu-id="17783-121">Target Framework</span></span>      | <span data-ttu-id="17783-122">最新版本</span><span class="sxs-lookup"><span data-stu-id="17783-122">Latest Version</span></span> | <span data-ttu-id="17783-123">目标框架名字对象 (TFM)</span><span class="sxs-lookup"><span data-stu-id="17783-123">Target Framework Moniker (TFM)</span></span> | <span data-ttu-id="17783-124">.NET Standard 版本</span><span class="sxs-lookup"><span data-stu-id="17783-124">.NET Standard Version</span></span> | <span data-ttu-id="17783-125">元包</span><span class="sxs-lookup"><span data-stu-id="17783-125">Metapackage</span></span> |
| :-------------------: | :------------: | :----------------------------: | :-------------------: | :---------: |
| <span data-ttu-id="17783-126">.NET Standard</span><span class="sxs-lookup"><span data-stu-id="17783-126">.NET Standard</span></span>         | <span data-ttu-id="17783-127">2.0.0</span><span class="sxs-lookup"><span data-stu-id="17783-127">2.0.0</span></span>          | <span data-ttu-id="17783-128">netstandard2.0</span><span class="sxs-lookup"><span data-stu-id="17783-128">netstandard2.0</span></span>                 | <span data-ttu-id="17783-129">不可用</span><span class="sxs-lookup"><span data-stu-id="17783-129">N/A</span></span>                   | [<span data-ttu-id="17783-130">NETStandard.Library</span><span class="sxs-lookup"><span data-stu-id="17783-130">NETStandard.Library</span></span>](https://www.nuget.org/packages/NETStandard.Library) |
| <span data-ttu-id="17783-131">.NET Core 应用程序</span><span class="sxs-lookup"><span data-stu-id="17783-131">.NET Core Application</span></span> | <span data-ttu-id="17783-132">2.0.0</span><span class="sxs-lookup"><span data-stu-id="17783-132">2.0.0</span></span>          | <span data-ttu-id="17783-133">netcoreapp2.0</span><span class="sxs-lookup"><span data-stu-id="17783-133">netcoreapp2.0</span></span>                  | <span data-ttu-id="17783-134">2.0</span><span class="sxs-lookup"><span data-stu-id="17783-134">2.0</span></span>                   | [<span data-ttu-id="17783-135">Microsoft.NETCore.App</span><span class="sxs-lookup"><span data-stu-id="17783-135">Microsoft.NETCore.App</span></span>](https://www.nuget.org/packages/Microsoft.NETCore.App) |
| <span data-ttu-id="17783-136">.NET Framework</span><span class="sxs-lookup"><span data-stu-id="17783-136">.NET Framework</span></span>        | <span data-ttu-id="17783-137">4.7</span><span class="sxs-lookup"><span data-stu-id="17783-137">4.7</span></span>            | <span data-ttu-id="17783-138">net47</span><span class="sxs-lookup"><span data-stu-id="17783-138">net47</span></span>                          | <span data-ttu-id="17783-139">1.5</span><span class="sxs-lookup"><span data-stu-id="17783-139">1.5</span></span>                   | <span data-ttu-id="17783-140">不可用</span><span class="sxs-lookup"><span data-stu-id="17783-140">N/A</span></span> |

## <a name="supported-target-framework-versions"></a><span data-ttu-id="17783-141">支持的目标框架版本</span><span class="sxs-lookup"><span data-stu-id="17783-141">Supported target framework versions</span></span>

<span data-ttu-id="17783-142">目标框架通常由 TFM 引用。</span><span class="sxs-lookup"><span data-stu-id="17783-142">A target framework is typically referenced by a TFM.</span></span> <span data-ttu-id="17783-143">下表显示 .NET Core SDK 和 NuGet 客户端支持的目标框架。</span><span class="sxs-lookup"><span data-stu-id="17783-143">The following table shows the target frameworks supported by the .NET Core SDK and the NuGet client.</span></span> <span data-ttu-id="17783-144">等效项显示在括号内。</span><span class="sxs-lookup"><span data-stu-id="17783-144">Equivalents are shown within brackets.</span></span> <span data-ttu-id="17783-145">例如，`win81` 对于 `netcore451` 来说等效于 TFM。</span><span class="sxs-lookup"><span data-stu-id="17783-145">For example, `win81` is an equivalent TFM to `netcore451`.</span></span>

| <span data-ttu-id="17783-146">目标 Framework</span><span class="sxs-lookup"><span data-stu-id="17783-146">Target Framework</span></span>           | <span data-ttu-id="17783-147">TFM</span><span class="sxs-lookup"><span data-stu-id="17783-147">TFM</span></span> |
| -------------------------- | --- |
| <span data-ttu-id="17783-148">.NET Standard</span><span class="sxs-lookup"><span data-stu-id="17783-148">.NET Standard</span></span>              | <span data-ttu-id="17783-149">netstandard1.0</span><span class="sxs-lookup"><span data-stu-id="17783-149">netstandard1.0</span></span><br><span data-ttu-id="17783-150">netstandard1.1</span><span class="sxs-lookup"><span data-stu-id="17783-150">netstandard1.1</span></span><br><span data-ttu-id="17783-151">netstandard1.2</span><span class="sxs-lookup"><span data-stu-id="17783-151">netstandard1.2</span></span><br><span data-ttu-id="17783-152">netstandard1.3</span><span class="sxs-lookup"><span data-stu-id="17783-152">netstandard1.3</span></span><br><span data-ttu-id="17783-153">netstandard1.4</span><span class="sxs-lookup"><span data-stu-id="17783-153">netstandard1.4</span></span><br><span data-ttu-id="17783-154">netstandard1.5</span><span class="sxs-lookup"><span data-stu-id="17783-154">netstandard1.5</span></span><br><span data-ttu-id="17783-155">netstandard1.6</span><span class="sxs-lookup"><span data-stu-id="17783-155">netstandard1.6</span></span><br><span data-ttu-id="17783-156">netstandard2.0</span><span class="sxs-lookup"><span data-stu-id="17783-156">netstandard2.0</span></span> |
| <span data-ttu-id="17783-157">.NET 核心</span><span class="sxs-lookup"><span data-stu-id="17783-157">.NET Core</span></span>                  | <span data-ttu-id="17783-158">netcoreapp1.0</span><span class="sxs-lookup"><span data-stu-id="17783-158">netcoreapp1.0</span></span><br><span data-ttu-id="17783-159">netcoreapp1.1</span><span class="sxs-lookup"><span data-stu-id="17783-159">netcoreapp1.1</span></span><br><span data-ttu-id="17783-160">netcoreapp2.0</span><span class="sxs-lookup"><span data-stu-id="17783-160">netcoreapp2.0</span></span> |
| <span data-ttu-id="17783-161">.NET Framework</span><span class="sxs-lookup"><span data-stu-id="17783-161">.NET Framework</span></span>             | <span data-ttu-id="17783-162">net11</span><span class="sxs-lookup"><span data-stu-id="17783-162">net11</span></span><br><span data-ttu-id="17783-163">net20</span><span class="sxs-lookup"><span data-stu-id="17783-163">net20</span></span><br><span data-ttu-id="17783-164">net35</span><span class="sxs-lookup"><span data-stu-id="17783-164">net35</span></span><br><span data-ttu-id="17783-165">net40</span><span class="sxs-lookup"><span data-stu-id="17783-165">net40</span></span><br><span data-ttu-id="17783-166">net403</span><span class="sxs-lookup"><span data-stu-id="17783-166">net403</span></span><br><span data-ttu-id="17783-167">net45</span><span class="sxs-lookup"><span data-stu-id="17783-167">net45</span></span><br><span data-ttu-id="17783-168">net451</span><span class="sxs-lookup"><span data-stu-id="17783-168">net451</span></span><br><span data-ttu-id="17783-169">net452</span><span class="sxs-lookup"><span data-stu-id="17783-169">net452</span></span><br><span data-ttu-id="17783-170">net46</span><span class="sxs-lookup"><span data-stu-id="17783-170">net46</span></span><br><span data-ttu-id="17783-171">net461</span><span class="sxs-lookup"><span data-stu-id="17783-171">net461</span></span><br><span data-ttu-id="17783-172">net462</span><span class="sxs-lookup"><span data-stu-id="17783-172">net462</span></span><br><span data-ttu-id="17783-173">net47</span><span class="sxs-lookup"><span data-stu-id="17783-173">net47</span></span> |
| <span data-ttu-id="17783-174">Windows 应用商店</span><span class="sxs-lookup"><span data-stu-id="17783-174">Windows Store</span></span>              | <span data-ttu-id="17783-175">netcore [netcore45]</span><span class="sxs-lookup"><span data-stu-id="17783-175">netcore [netcore45]</span></span><br><span data-ttu-id="17783-176">netcore45 [win] [win8]</span><span class="sxs-lookup"><span data-stu-id="17783-176">netcore45 [win] [win8]</span></span><br><span data-ttu-id="17783-177">netcore451 [win81]</span><span class="sxs-lookup"><span data-stu-id="17783-177">netcore451 [win81]</span></span> |
| <span data-ttu-id="17783-178">.NET Micro Framework</span><span class="sxs-lookup"><span data-stu-id="17783-178">.NET Micro Framework</span></span>       | <span data-ttu-id="17783-179">netmf</span><span class="sxs-lookup"><span data-stu-id="17783-179">netmf</span></span> |
| <span data-ttu-id="17783-180">Silverlight</span><span class="sxs-lookup"><span data-stu-id="17783-180">Silverlight</span></span>                | <span data-ttu-id="17783-181">sl4</span><span class="sxs-lookup"><span data-stu-id="17783-181">sl4</span></span><br><span data-ttu-id="17783-182">sl5</span><span class="sxs-lookup"><span data-stu-id="17783-182">sl5</span></span> |
| <span data-ttu-id="17783-183">Windows Phone</span><span class="sxs-lookup"><span data-stu-id="17783-183">Windows Phone</span></span>              | <span data-ttu-id="17783-184">wp [wp7]</span><span class="sxs-lookup"><span data-stu-id="17783-184">wp [wp7]</span></span><br><span data-ttu-id="17783-185">wp7</span><span class="sxs-lookup"><span data-stu-id="17783-185">wp7</span></span><br><span data-ttu-id="17783-186">wp75</span><span class="sxs-lookup"><span data-stu-id="17783-186">wp75</span></span><br><span data-ttu-id="17783-187">wp8</span><span class="sxs-lookup"><span data-stu-id="17783-187">wp8</span></span><br><span data-ttu-id="17783-188">wp81</span><span class="sxs-lookup"><span data-stu-id="17783-188">wp81</span></span><br><span data-ttu-id="17783-189">wpa81</span><span class="sxs-lookup"><span data-stu-id="17783-189">wpa81</span></span> |
| <span data-ttu-id="17783-190">通用 Windows 平台</span><span class="sxs-lookup"><span data-stu-id="17783-190">Universal Windows Platform</span></span> | <span data-ttu-id="17783-191">uap [uap10.0]</span><span class="sxs-lookup"><span data-stu-id="17783-191">uap [uap10.0]</span></span><br><span data-ttu-id="17783-192">uap10.0 [win10] [netcore50]</span><span class="sxs-lookup"><span data-stu-id="17783-192">uap10.0 [win10] [netcore50]</span></span> |

## <a name="how-to-specify-target-frameworks"></a><span data-ttu-id="17783-193">如何指定目标框架</span><span class="sxs-lookup"><span data-stu-id="17783-193">How to specify target frameworks</span></span>

<span data-ttu-id="17783-194">在项目文件中指定目标框架。</span><span class="sxs-lookup"><span data-stu-id="17783-194">Target frameworks are specified in your project file.</span></span> <span data-ttu-id="17783-195">指定单个目标框架时，使用 TargetFramework 元素。</span><span class="sxs-lookup"><span data-stu-id="17783-195">When a single target framework is specified, use the **TargetFramework** element.</span></span> <span data-ttu-id="17783-196">以下控制台应用项目文件演示了如何以 .NET Core 2.0 为目标：</span><span class="sxs-lookup"><span data-stu-id="17783-196">The following console app project file demonstrates how to target .NET Core 2.0:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <OutputType>Exe</OutputType>
    <TargetFramework>netcoreapp2.0</TargetFramework>
  </PropertyGroup>

</Project>
```

<span data-ttu-id="17783-197">指定多个目标框架时，可有条件地为每个目标框架引用程序集。</span><span class="sxs-lookup"><span data-stu-id="17783-197">When you specify multiple target frameworks, you may conditionally reference assemblies for each target framework.</span></span> <span data-ttu-id="17783-198">在代码中，可使用具有 -if-then-else 逻辑的预处理器符号，有条件地针对这些程序集进行编译。</span><span class="sxs-lookup"><span data-stu-id="17783-198">In your code, you can conditionally compile against those assemblies by using preprocessor symbols with *if-then-else* logic.</span></span>

<span data-ttu-id="17783-199">以下库项目文件以 .NET Standard (`netstandard1.4`) 的 API 和 .NET Framework（`net40` 和 `net45`）的 API 作为目标。</span><span class="sxs-lookup"><span data-stu-id="17783-199">The following library project file targets APIs of .NET Standard (`netstandard1.4`) and APIs of the .NET Framework (`net40` and `net45`).</span></span> <span data-ttu-id="17783-200">将复数形式的 TargetFrameworks 元素与多个目标框架一起使用。</span><span class="sxs-lookup"><span data-stu-id="17783-200">Use the plural **TargetFrameworks** element with multiple target frameworks.</span></span> <span data-ttu-id="17783-201">请注意为两个 .NET Framework TFM 编译库时，`Condition` 属性包括特定于实现的包的方法：</span><span class="sxs-lookup"><span data-stu-id="17783-201">Note how the `Condition` attributes include implementation-specific packages when the library is compiled for the two .NET Framework TFMs:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <TargetFrameworks>netstandard1.4;net40;net45</TargetFrameworks>
  </PropertyGroup>

  <!-- Conditionally obtain references for the .NET Framework 4.0 target -->
  <ItemGroup Condition=" '$(TargetFramework)' == 'net40' ">
    <Reference Include="System.Net" />
  </ItemGroup>

  <!-- Conditionally obtain references for the .NET Framework 4.5 target -->
  <ItemGroup Condition=" '$(TargetFramework)' == 'net45' ">
    <Reference Include="System.Net.Http" />
    <Reference Include="System.Threading.Tasks" />
  </ItemGroup>

</Project>
```

<span data-ttu-id="17783-202">在库或应用中，编写条件代码以为每个目标框架编译：</span><span class="sxs-lookup"><span data-stu-id="17783-202">Within your library or app, you write conditional code to compile for each target framework:</span></span>

```csharp
public class MyClass
{
    static void Main()
    {
#if NET40
        Console.WriteLine("Target framework: .NET Framework 4.0");
#elif NET45  
        Console.WriteLine("Target framework: .NET Framework 4.5");
#else
        Console.WriteLine("Target framework: .NET Standard 1.4");
#endif
    }
}
```

<span data-ttu-id="17783-203">生成系统可识别预处理器符号，这些符号表示[支持的目标框架版本](#supported-target-framework-versions)表中所示的目标框架。</span><span class="sxs-lookup"><span data-stu-id="17783-203">The build system is aware of preprocessor symbols representing the target frameworks shown in the [Supported target framework versions](#supported-target-framework-versions) table.</span></span> <span data-ttu-id="17783-204">使用表示 .NET Standard 或 .NET Core TFM 的符号时，用下划线替代句点，并将小写字母转换为大写字母（例如，`netstandard1.4` 的符号是 `NETSTANDARD1_4`）。</span><span class="sxs-lookup"><span data-stu-id="17783-204">When using a symbol that represents a .NET Standard or .NET Core TFM, replace the dot with an underscore and change lowercase letters to uppercase (for example, the symbol for `netstandard1.4` is `NETSTANDARD1_4`).</span></span>

<span data-ttu-id="17783-205">完整的 .NET Core 目标框架的预处理器符号列表：</span><span class="sxs-lookup"><span data-stu-id="17783-205">The complete list of preprocessor symbols for .NET Core target frameworks is:</span></span>

[!INCLUDE [Preprocessor symbols](~/includes/preprocessor-symbols.md)]

## <a name="deprecated-target-frameworks"></a><span data-ttu-id="17783-206">已弃用的目标框架</span><span class="sxs-lookup"><span data-stu-id="17783-206">Deprecated target frameworks</span></span>

<span data-ttu-id="17783-207">以下目标框架已弃用。</span><span class="sxs-lookup"><span data-stu-id="17783-207">The following target frameworks are deprecated.</span></span> <span data-ttu-id="17783-208">以这些目标框架为目标的包应迁移到指明的替代框架。</span><span class="sxs-lookup"><span data-stu-id="17783-208">Packages targeting these target frameworks should migrate to the indicated replacements.</span></span>

| <span data-ttu-id="17783-209">已弃用的 TFM</span><span class="sxs-lookup"><span data-stu-id="17783-209">Deprecated TFM</span></span>                                                                             | <span data-ttu-id="17783-210">Replacement</span><span class="sxs-lookup"><span data-stu-id="17783-210">Replacement</span></span> |
| ------------------------------------------------------------------------------------------ | ----------- |
| <span data-ttu-id="17783-211">aspnet50</span><span class="sxs-lookup"><span data-stu-id="17783-211">aspnet50</span></span><br><span data-ttu-id="17783-212">aspnetcore50</span><span class="sxs-lookup"><span data-stu-id="17783-212">aspnetcore50</span></span><br><span data-ttu-id="17783-213">dnxcore50</span><span class="sxs-lookup"><span data-stu-id="17783-213">dnxcore50</span></span><br><span data-ttu-id="17783-214">dnx</span><span class="sxs-lookup"><span data-stu-id="17783-214">dnx</span></span><br><span data-ttu-id="17783-215">dnx45</span><span class="sxs-lookup"><span data-stu-id="17783-215">dnx45</span></span><br><span data-ttu-id="17783-216">dnx451</span><span class="sxs-lookup"><span data-stu-id="17783-216">dnx451</span></span><br><span data-ttu-id="17783-217">dnx452</span><span class="sxs-lookup"><span data-stu-id="17783-217">dnx452</span></span>                  | <span data-ttu-id="17783-218">netcoreapp</span><span class="sxs-lookup"><span data-stu-id="17783-218">netcoreapp</span></span>  |
| <span data-ttu-id="17783-219">dotnet</span><span class="sxs-lookup"><span data-stu-id="17783-219">dotnet</span></span><br><span data-ttu-id="17783-220">dotnet50</span><span class="sxs-lookup"><span data-stu-id="17783-220">dotnet50</span></span><br><span data-ttu-id="17783-221">dotnet51</span><span class="sxs-lookup"><span data-stu-id="17783-221">dotnet51</span></span><br><span data-ttu-id="17783-222">dotnet52</span><span class="sxs-lookup"><span data-stu-id="17783-222">dotnet52</span></span><br><span data-ttu-id="17783-223">dotnet53</span><span class="sxs-lookup"><span data-stu-id="17783-223">dotnet53</span></span><br><span data-ttu-id="17783-224">dotnet54</span><span class="sxs-lookup"><span data-stu-id="17783-224">dotnet54</span></span><br><span data-ttu-id="17783-225">dotnet55</span><span class="sxs-lookup"><span data-stu-id="17783-225">dotnet55</span></span><br><span data-ttu-id="17783-226">dotnet56</span><span class="sxs-lookup"><span data-stu-id="17783-226">dotnet56</span></span> | <span data-ttu-id="17783-227">netstandard</span><span class="sxs-lookup"><span data-stu-id="17783-227">netstandard</span></span> |
| <span data-ttu-id="17783-228">netcore50</span><span class="sxs-lookup"><span data-stu-id="17783-228">netcore50</span></span>                                                                                  | <span data-ttu-id="17783-229">uap10.0</span><span class="sxs-lookup"><span data-stu-id="17783-229">uap10.0</span></span>     |
| <span data-ttu-id="17783-230">win</span><span class="sxs-lookup"><span data-stu-id="17783-230">win</span></span>                                                                                        | <span data-ttu-id="17783-231">netcore45</span><span class="sxs-lookup"><span data-stu-id="17783-231">netcore45</span></span>   |
| <span data-ttu-id="17783-232">win8</span><span class="sxs-lookup"><span data-stu-id="17783-232">win8</span></span>                                                                                       | <span data-ttu-id="17783-233">netcore45</span><span class="sxs-lookup"><span data-stu-id="17783-233">netcore45</span></span>   |
| <span data-ttu-id="17783-234">win81</span><span class="sxs-lookup"><span data-stu-id="17783-234">win81</span></span>                                                                                      | <span data-ttu-id="17783-235">netcore451</span><span class="sxs-lookup"><span data-stu-id="17783-235">netcore451</span></span>  |
| <span data-ttu-id="17783-236">win10</span><span class="sxs-lookup"><span data-stu-id="17783-236">win10</span></span>                                                                                      | <span data-ttu-id="17783-237">uap10.0</span><span class="sxs-lookup"><span data-stu-id="17783-237">uap10.0</span></span>     |
| <span data-ttu-id="17783-238">winrt</span><span class="sxs-lookup"><span data-stu-id="17783-238">winrt</span></span>                                                                                      | <span data-ttu-id="17783-239">netcore45</span><span class="sxs-lookup"><span data-stu-id="17783-239">netcore45</span></span>   |

## <a name="see-also"></a><span data-ttu-id="17783-240">请参阅</span><span class="sxs-lookup"><span data-stu-id="17783-240">See also</span></span>

[<span data-ttu-id="17783-241">包、元包和框架</span><span class="sxs-lookup"><span data-stu-id="17783-241">Packages, Metapackages and Frameworks</span></span>](~/docs/core/packages.md)  
[<span data-ttu-id="17783-242">使用跨平台工具开发库</span><span class="sxs-lookup"><span data-stu-id="17783-242">Developing Libraries with Cross Platform Tools</span></span>](~/docs/core/tutorials/libraries.md)  
[<span data-ttu-id="17783-243">.NET Standard</span><span class="sxs-lookup"><span data-stu-id="17783-243">.NET Standard</span></span>](~/docs/standard/net-standard.md)  
[<span data-ttu-id="17783-244">.NET Core 版本控制</span><span class="sxs-lookup"><span data-stu-id="17783-244">.NET Core Versioning</span></span>](~/docs/core/versions/index.md)  
[<span data-ttu-id="17783-245">dotnet/standard GitHub 存储库</span><span class="sxs-lookup"><span data-stu-id="17783-245">dotnet/standard GitHub repository</span></span>](https://github.com/dotnet/standard)  
[<span data-ttu-id="17783-246">NuGet 工具 GitHub 存储库</span><span class="sxs-lookup"><span data-stu-id="17783-246">NuGet Tools GitHub Repository</span></span>](https://github.com/joelverhagen/NuGetTools)  
[<span data-ttu-id="17783-247">.NET 中的框架配置文件</span><span class="sxs-lookup"><span data-stu-id="17783-247">Framework Profiles in .NET</span></span>](http://blog.stephencleary.com/2012/05/framework-profiles-in-net.html)

