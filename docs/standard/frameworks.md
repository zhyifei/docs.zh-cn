---
title: SDK 样式项目中的目标框架 - .NET
description: 了解用于 .NET Core 应用和库的目标框架。
author: mairaw
ms.author: mairaw
ms.date: 12/03/2019
ms.custom: updateeachrelease
ms.technology: dotnet-standard
ms.openlocfilehash: 957671644ae333180b0c1ba4aae6d6e17ae6478b
ms.sourcegitcommit: a4f9b754059f0210e29ae0578363a27b9ba84b64
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/05/2019
ms.locfileid: "74838205"
---
# <a name="target-frameworks-in-sdk-style-projects"></a><span data-ttu-id="27880-103">SDK 样式项目中的目标框架</span><span class="sxs-lookup"><span data-stu-id="27880-103">Target frameworks in SDK-style projects</span></span>

<span data-ttu-id="27880-104">以应用或库中的框架为目标时，需要指定想要向应用或库提供的 API 集。</span><span class="sxs-lookup"><span data-stu-id="27880-104">When you target a framework in an app or library, you're specifying the set of APIs that you'd like to make available to the app or library.</span></span> <span data-ttu-id="27880-105">使用目标框架名字对象 (TFM) 在项目文件中指定目标框架。</span><span class="sxs-lookup"><span data-stu-id="27880-105">You specify the target framework in your project file using Target Framework Monikers (TFMs).</span></span>

<span data-ttu-id="27880-106">应用或库可以使用 [.NET Standard](net-standard.md) 版本作为目标。</span><span class="sxs-lookup"><span data-stu-id="27880-106">An app or library can target a version of [.NET Standard](net-standard.md).</span></span> <span data-ttu-id="27880-107">.NET Standard 版本表示所有 .NET 实现中的标准化 API 集。</span><span class="sxs-lookup"><span data-stu-id="27880-107">.NET Standard versions represent standardized sets of APIs across all .NET implementations.</span></span> <span data-ttu-id="27880-108">例如，库可以使用 .NET Standard 1.6 作为目标，并获得对可使用相同基本代码跨 .NET Core 和 .NET Framework 工作的 API 的访问权限。</span><span class="sxs-lookup"><span data-stu-id="27880-108">For example, a library can target .NET Standard 1.6 and gain access to APIs that function across .NET Core and .NET Framework using the same codebase.</span></span>

<span data-ttu-id="27880-109">应用或库还能以一个特定 .NET 实现为目标，获得特定于实现的 API 的访问权限。</span><span class="sxs-lookup"><span data-stu-id="27880-109">An app or library can also target a specific .NET implementation to gain access to implementation-specific APIs.</span></span> <span data-ttu-id="27880-110">例如，面向 Xamarin.iOS 的应用（如 `Xamarin.iOS10`）有权访问 Xamarin 提供的适用于 iOS 10 的 iOS API 包装器；面向通用 Windows 平台 (UWP) 的应用（如 `uap10.0`）有权访问为运行 Windows 10 的设备编译的 API。</span><span class="sxs-lookup"><span data-stu-id="27880-110">For example, an app that targets Xamarin.iOS (for example, `Xamarin.iOS10`) gets access to Xamarin-provided iOS API wrappers for iOS 10, or an app that targets the Universal Windows Platform (UWP, `uap10.0`) has access to APIs that compile for devices that run Windows 10.</span></span>

<span data-ttu-id="27880-111">对于某些目标框架（例如 .NET Framework），API 由框架在系统上安装的程序集定义，并且可能包括应用程序框架 API（例如 ASP.NET）。</span><span class="sxs-lookup"><span data-stu-id="27880-111">For some target frameworks (for example, the .NET Framework), the APIs are defined by the assemblies that the framework installs on a system and may include application framework APIs (for example, ASP.NET).</span></span>

<span data-ttu-id="27880-112">对于基于包的目标框架（例如 .NET Standard 和 .NET Core），API 由包含在应用或库中的包定义。</span><span class="sxs-lookup"><span data-stu-id="27880-112">For package-based target frameworks (for example, .NET Standard and .NET Core), the APIs are defined by the packages included in the app or library.</span></span> <span data-ttu-id="27880-113">元包  是一个 NuGet 包，NuGet 包本身不包含任何内容，只是一个依赖项列表（其他包）。</span><span class="sxs-lookup"><span data-stu-id="27880-113">A *metapackage* is a NuGet package that has no content of its own but is a list of dependencies (other packages).</span></span> <span data-ttu-id="27880-114">基于 NuGet 包的目标框架隐式指定一个元包，该元包引用一起构成框架的所有包。</span><span class="sxs-lookup"><span data-stu-id="27880-114">A NuGet package-based target framework implicitly specifies a metapackage that references all the packages that together make up the framework.</span></span>

## <a name="latest-target-framework-versions"></a><span data-ttu-id="27880-115">最新目标框架版本</span><span class="sxs-lookup"><span data-stu-id="27880-115">Latest target framework versions</span></span>

<span data-ttu-id="27880-116">下表定义了最常见的目标框架、如何引用这些框架，以及它们实现的 [.NET Standard](net-standard.md) 版本。</span><span class="sxs-lookup"><span data-stu-id="27880-116">The following table defines the most common target frameworks, how they're referenced, and which version of the [.NET Standard](net-standard.md) they implement.</span></span> <span data-ttu-id="27880-117">这些目标框架版本是最新的稳定版本。</span><span class="sxs-lookup"><span data-stu-id="27880-117">These target framework versions are the latest stable versions.</span></span> <span data-ttu-id="27880-118">预览版不会显示。</span><span class="sxs-lookup"><span data-stu-id="27880-118">Pre-release versions aren't shown.</span></span> <span data-ttu-id="27880-119">目标框架名字对象 (TFM) 是一个标准化令牌格式，用于指定 .NET 应用或库的目标框架。</span><span class="sxs-lookup"><span data-stu-id="27880-119">A Target Framework Moniker (TFM) is a standardized token format for specifying the target framework of a .NET app or library.</span></span>

| <span data-ttu-id="27880-120">目标 Framework</span><span class="sxs-lookup"><span data-stu-id="27880-120">Target Framework</span></span>      | <span data-ttu-id="27880-121">最新</span><span class="sxs-lookup"><span data-stu-id="27880-121">Latest</span></span> <br/> <span data-ttu-id="27880-122">稳定版本</span><span class="sxs-lookup"><span data-stu-id="27880-122">Stable Version</span></span> | <span data-ttu-id="27880-123">目标框架名字对象 (TFM)</span><span class="sxs-lookup"><span data-stu-id="27880-123">Target Framework Moniker (TFM)</span></span> | <span data-ttu-id="27880-124">已实现</span><span class="sxs-lookup"><span data-stu-id="27880-124">Implemented</span></span> <br/> <span data-ttu-id="27880-125">.NET Standard 版本</span><span class="sxs-lookup"><span data-stu-id="27880-125">.NET Standard Version</span></span> |
| :-------------------: | :-------------------------: | :----------------------------: | :-------------------------------------: |
| <span data-ttu-id="27880-126">.NET Standard</span><span class="sxs-lookup"><span data-stu-id="27880-126">.NET Standard</span></span>         | <span data-ttu-id="27880-127">2.1</span><span class="sxs-lookup"><span data-stu-id="27880-127">2.1</span></span>                         | <span data-ttu-id="27880-128">netstandard2.1</span><span class="sxs-lookup"><span data-stu-id="27880-128">netstandard2.1</span></span>                 | <span data-ttu-id="27880-129">不可用</span><span class="sxs-lookup"><span data-stu-id="27880-129">N/A</span></span>                                     |
| <span data-ttu-id="27880-130">.NET Core</span><span class="sxs-lookup"><span data-stu-id="27880-130">.NET Core</span></span>             | <span data-ttu-id="27880-131">3.1</span><span class="sxs-lookup"><span data-stu-id="27880-131">3.1</span></span>                         | <span data-ttu-id="27880-132">netcoreapp3.1</span><span class="sxs-lookup"><span data-stu-id="27880-132">netcoreapp3.1</span></span>                  | <span data-ttu-id="27880-133">2.1</span><span class="sxs-lookup"><span data-stu-id="27880-133">2.1</span></span>                                     |
| <span data-ttu-id="27880-134">.NET Framework</span><span class="sxs-lookup"><span data-stu-id="27880-134">.NET Framework</span></span>        | <span data-ttu-id="27880-135">4.8</span><span class="sxs-lookup"><span data-stu-id="27880-135">4.8</span></span>                         | <span data-ttu-id="27880-136">net48</span><span class="sxs-lookup"><span data-stu-id="27880-136">net48</span></span>                          | <span data-ttu-id="27880-137">2.0</span><span class="sxs-lookup"><span data-stu-id="27880-137">2.0</span></span>                                     |

## <a name="supported-target-framework-versions"></a><span data-ttu-id="27880-138">支持的目标框架版本</span><span class="sxs-lookup"><span data-stu-id="27880-138">Supported target framework versions</span></span>

<span data-ttu-id="27880-139">目标框架通常由 TFM 引用。</span><span class="sxs-lookup"><span data-stu-id="27880-139">A target framework is typically referenced by a TFM.</span></span> <span data-ttu-id="27880-140">下表显示 .NET Core SDK 和 NuGet 客户端支持的目标框架。</span><span class="sxs-lookup"><span data-stu-id="27880-140">The following table shows the target frameworks supported by the .NET Core SDK and the NuGet client.</span></span> <span data-ttu-id="27880-141">等效项显示在括号内。</span><span class="sxs-lookup"><span data-stu-id="27880-141">Equivalents are shown within brackets.</span></span> <span data-ttu-id="27880-142">例如，`win81` 对于 `netcore451` 来说等效于 TFM。</span><span class="sxs-lookup"><span data-stu-id="27880-142">For example, `win81` is an equivalent TFM to `netcore451`.</span></span>

| <span data-ttu-id="27880-143">目标 Framework</span><span class="sxs-lookup"><span data-stu-id="27880-143">Target Framework</span></span>           | <span data-ttu-id="27880-144">TFM</span><span class="sxs-lookup"><span data-stu-id="27880-144">TFM</span></span> |
| -------------------------- | --- |
| <span data-ttu-id="27880-145">.NET Standard</span><span class="sxs-lookup"><span data-stu-id="27880-145">.NET Standard</span></span>              | <span data-ttu-id="27880-146">netstandard1.0</span><span class="sxs-lookup"><span data-stu-id="27880-146">netstandard1.0</span></span><br><span data-ttu-id="27880-147">netstandard1.1</span><span class="sxs-lookup"><span data-stu-id="27880-147">netstandard1.1</span></span><br><span data-ttu-id="27880-148">netstandard1.2</span><span class="sxs-lookup"><span data-stu-id="27880-148">netstandard1.2</span></span><br><span data-ttu-id="27880-149">netstandard1.3</span><span class="sxs-lookup"><span data-stu-id="27880-149">netstandard1.3</span></span><br><span data-ttu-id="27880-150">netstandard1.4</span><span class="sxs-lookup"><span data-stu-id="27880-150">netstandard1.4</span></span><br><span data-ttu-id="27880-151">netstandard1.5</span><span class="sxs-lookup"><span data-stu-id="27880-151">netstandard1.5</span></span><br><span data-ttu-id="27880-152">netstandard1.6</span><span class="sxs-lookup"><span data-stu-id="27880-152">netstandard1.6</span></span><br><span data-ttu-id="27880-153">netstandard2.0</span><span class="sxs-lookup"><span data-stu-id="27880-153">netstandard2.0</span></span><br><span data-ttu-id="27880-154">netstandard2.1</span><span class="sxs-lookup"><span data-stu-id="27880-154">netstandard2.1</span></span> |
| <span data-ttu-id="27880-155">.NET Core</span><span class="sxs-lookup"><span data-stu-id="27880-155">.NET Core</span></span>                  | <span data-ttu-id="27880-156">netcoreapp1.0</span><span class="sxs-lookup"><span data-stu-id="27880-156">netcoreapp1.0</span></span><br><span data-ttu-id="27880-157">netcoreapp1.1</span><span class="sxs-lookup"><span data-stu-id="27880-157">netcoreapp1.1</span></span><br><span data-ttu-id="27880-158">netcoreapp2.0</span><span class="sxs-lookup"><span data-stu-id="27880-158">netcoreapp2.0</span></span><br><span data-ttu-id="27880-159">netcoreapp2.1</span><span class="sxs-lookup"><span data-stu-id="27880-159">netcoreapp2.1</span></span><br><span data-ttu-id="27880-160">netcoreapp2.2</span><span class="sxs-lookup"><span data-stu-id="27880-160">netcoreapp2.2</span></span><br><span data-ttu-id="27880-161">netcoreapp3.0</span><span class="sxs-lookup"><span data-stu-id="27880-161">netcoreapp3.0</span></span><br><span data-ttu-id="27880-162">netcoreapp3.1</span><span class="sxs-lookup"><span data-stu-id="27880-162">netcoreapp3.1</span></span> |
| <span data-ttu-id="27880-163">.NET Framework</span><span class="sxs-lookup"><span data-stu-id="27880-163">.NET Framework</span></span>             | <span data-ttu-id="27880-164">net11</span><span class="sxs-lookup"><span data-stu-id="27880-164">net11</span></span><br><span data-ttu-id="27880-165">net20</span><span class="sxs-lookup"><span data-stu-id="27880-165">net20</span></span><br><span data-ttu-id="27880-166">net35</span><span class="sxs-lookup"><span data-stu-id="27880-166">net35</span></span><br><span data-ttu-id="27880-167">net40</span><span class="sxs-lookup"><span data-stu-id="27880-167">net40</span></span><br><span data-ttu-id="27880-168">net403</span><span class="sxs-lookup"><span data-stu-id="27880-168">net403</span></span><br><span data-ttu-id="27880-169">net45</span><span class="sxs-lookup"><span data-stu-id="27880-169">net45</span></span><br><span data-ttu-id="27880-170">net451</span><span class="sxs-lookup"><span data-stu-id="27880-170">net451</span></span><br><span data-ttu-id="27880-171">net452</span><span class="sxs-lookup"><span data-stu-id="27880-171">net452</span></span><br><span data-ttu-id="27880-172">net46</span><span class="sxs-lookup"><span data-stu-id="27880-172">net46</span></span><br><span data-ttu-id="27880-173">net461</span><span class="sxs-lookup"><span data-stu-id="27880-173">net461</span></span><br><span data-ttu-id="27880-174">net462</span><span class="sxs-lookup"><span data-stu-id="27880-174">net462</span></span><br><span data-ttu-id="27880-175">net47</span><span class="sxs-lookup"><span data-stu-id="27880-175">net47</span></span><br><span data-ttu-id="27880-176">net471</span><span class="sxs-lookup"><span data-stu-id="27880-176">net471</span></span><br><span data-ttu-id="27880-177">net472</span><span class="sxs-lookup"><span data-stu-id="27880-177">net472</span></span><br><span data-ttu-id="27880-178">net48</span><span class="sxs-lookup"><span data-stu-id="27880-178">net48</span></span> |
| <span data-ttu-id="27880-179">Windows 应用商店</span><span class="sxs-lookup"><span data-stu-id="27880-179">Windows Store</span></span>              | <span data-ttu-id="27880-180">netcore [netcore45]</span><span class="sxs-lookup"><span data-stu-id="27880-180">netcore [netcore45]</span></span><br><span data-ttu-id="27880-181">netcore45 [win] [win8]</span><span class="sxs-lookup"><span data-stu-id="27880-181">netcore45 [win] [win8]</span></span><br><span data-ttu-id="27880-182">netcore451 [win81]</span><span class="sxs-lookup"><span data-stu-id="27880-182">netcore451 [win81]</span></span> |
| <span data-ttu-id="27880-183">.NET Micro Framework</span><span class="sxs-lookup"><span data-stu-id="27880-183">.NET Micro Framework</span></span>       | <span data-ttu-id="27880-184">netmf</span><span class="sxs-lookup"><span data-stu-id="27880-184">netmf</span></span> |
| <span data-ttu-id="27880-185">Silverlight</span><span class="sxs-lookup"><span data-stu-id="27880-185">Silverlight</span></span>                | <span data-ttu-id="27880-186">sl4</span><span class="sxs-lookup"><span data-stu-id="27880-186">sl4</span></span><br><span data-ttu-id="27880-187">sl5</span><span class="sxs-lookup"><span data-stu-id="27880-187">sl5</span></span> |
| <span data-ttu-id="27880-188">Windows Phone</span><span class="sxs-lookup"><span data-stu-id="27880-188">Windows Phone</span></span>              | <span data-ttu-id="27880-189">wp [wp7]</span><span class="sxs-lookup"><span data-stu-id="27880-189">wp [wp7]</span></span><br><span data-ttu-id="27880-190">wp7</span><span class="sxs-lookup"><span data-stu-id="27880-190">wp7</span></span><br><span data-ttu-id="27880-191">wp75</span><span class="sxs-lookup"><span data-stu-id="27880-191">wp75</span></span><br><span data-ttu-id="27880-192">wp8</span><span class="sxs-lookup"><span data-stu-id="27880-192">wp8</span></span><br><span data-ttu-id="27880-193">wp81</span><span class="sxs-lookup"><span data-stu-id="27880-193">wp81</span></span><br><span data-ttu-id="27880-194">wpa81</span><span class="sxs-lookup"><span data-stu-id="27880-194">wpa81</span></span> |
| <span data-ttu-id="27880-195">通用 Windows 平台</span><span class="sxs-lookup"><span data-stu-id="27880-195">Universal Windows Platform</span></span> | <span data-ttu-id="27880-196">uap [uap10.0]</span><span class="sxs-lookup"><span data-stu-id="27880-196">uap [uap10.0]</span></span><br><span data-ttu-id="27880-197">uap10.0 [win10] [netcore50]</span><span class="sxs-lookup"><span data-stu-id="27880-197">uap10.0 [win10] [netcore50]</span></span> |

## <a name="how-to-specify-target-frameworks"></a><span data-ttu-id="27880-198">如何指定目标框架</span><span class="sxs-lookup"><span data-stu-id="27880-198">How to specify target frameworks</span></span>

<span data-ttu-id="27880-199">在项目文件中指定目标框架。</span><span class="sxs-lookup"><span data-stu-id="27880-199">Target frameworks are specified in your project file.</span></span> <span data-ttu-id="27880-200">指定单个目标框架时，使用 TargetFramework  元素。</span><span class="sxs-lookup"><span data-stu-id="27880-200">When a single target framework is specified, use the **TargetFramework** element.</span></span> <span data-ttu-id="27880-201">以下控制台应用项目文件演示了如何以 .NET Core 3.0 为目标：</span><span class="sxs-lookup"><span data-stu-id="27880-201">The following console app project file demonstrates how to target .NET Core 3.0:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <OutputType>Exe</OutputType>
    <TargetFramework>netcoreapp3.0</TargetFramework>
  </PropertyGroup>

</Project>
```

<span data-ttu-id="27880-202">指定多个目标框架时，可有条件地为每个目标框架引用程序集。</span><span class="sxs-lookup"><span data-stu-id="27880-202">When you specify multiple target frameworks, you may conditionally reference assemblies for each target framework.</span></span> <span data-ttu-id="27880-203">在代码中，可使用具有 -if-then-else  逻辑的预处理器符号，有条件地针对这些程序集进行编译。</span><span class="sxs-lookup"><span data-stu-id="27880-203">In your code, you can conditionally compile against those assemblies by using preprocessor symbols with *if-then-else* logic.</span></span>

<span data-ttu-id="27880-204">以下库项目文件以 .NET Standard (`netstandard1.4`) 的 API 和 .NET Framework（`net40` 和 `net45`）的 API 作为目标。</span><span class="sxs-lookup"><span data-stu-id="27880-204">The following library project file targets APIs of .NET Standard (`netstandard1.4`) and APIs of the .NET Framework (`net40` and `net45`).</span></span> <span data-ttu-id="27880-205">将复数形式的 TargetFrameworks  元素与多个目标框架一起使用。</span><span class="sxs-lookup"><span data-stu-id="27880-205">Use the plural **TargetFrameworks** element with multiple target frameworks.</span></span> <span data-ttu-id="27880-206">请注意为两个 .NET Framework TFM 编译库时，`Condition` 属性包括特定于实现的包的方法：</span><span class="sxs-lookup"><span data-stu-id="27880-206">Note how the `Condition` attributes include implementation-specific packages when the library is compiled for the two .NET Framework TFMs:</span></span>

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

<span data-ttu-id="27880-207">在库或应用中，编写条件代码以为每个目标框架编译：</span><span class="sxs-lookup"><span data-stu-id="27880-207">Within your library or app, you write conditional code to compile for each target framework:</span></span>

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

<span data-ttu-id="27880-208">使用 SDK 样式项目时，生成系统可识别预处理器符号，这些符号表示[支持的目标框架版本](#supported-target-framework-versions)表中所示的目标框架。</span><span class="sxs-lookup"><span data-stu-id="27880-208">The build system is aware of preprocessor symbols representing the target frameworks shown in the [Supported target framework versions](#supported-target-framework-versions) table when you're using SDK-style projects.</span></span> <span data-ttu-id="27880-209">使用表示 .NET Standard 或 .NET Core TFM 的符号时，用下划线替代句点，并将小写字母转换为大写字母（例如，`netstandard1.4` 的符号是 `NETSTANDARD1_4`）。</span><span class="sxs-lookup"><span data-stu-id="27880-209">When using a symbol that represents a .NET Standard or .NET Core TFM, replace the dot with an underscore and change lowercase letters to uppercase (for example, the symbol for `netstandard1.4` is `NETSTANDARD1_4`).</span></span>

<span data-ttu-id="27880-210">完整的 .NET Core 目标框架的预处理器符号列表：</span><span class="sxs-lookup"><span data-stu-id="27880-210">The complete list of preprocessor symbols for .NET Core target frameworks is:</span></span>

[!INCLUDE [Preprocessor symbols](../../includes/preprocessor-symbols.md)]

## <a name="deprecated-target-frameworks"></a><span data-ttu-id="27880-211">已弃用的目标框架</span><span class="sxs-lookup"><span data-stu-id="27880-211">Deprecated target frameworks</span></span>

<span data-ttu-id="27880-212">以下目标框架已弃用。</span><span class="sxs-lookup"><span data-stu-id="27880-212">The following target frameworks are deprecated.</span></span> <span data-ttu-id="27880-213">以这些目标框架为目标的包应迁移到指明的替代框架。</span><span class="sxs-lookup"><span data-stu-id="27880-213">Packages targeting these target frameworks should migrate to the indicated replacements.</span></span>

| <span data-ttu-id="27880-214">已弃用的 TFM</span><span class="sxs-lookup"><span data-stu-id="27880-214">Deprecated TFM</span></span>                                                                             | <span data-ttu-id="27880-215">Replacement</span><span class="sxs-lookup"><span data-stu-id="27880-215">Replacement</span></span> |
| ------------------------------------------------------------------------------------------ | ----------- |
| <span data-ttu-id="27880-216">aspnet50</span><span class="sxs-lookup"><span data-stu-id="27880-216">aspnet50</span></span><br><span data-ttu-id="27880-217">aspnetcore50</span><span class="sxs-lookup"><span data-stu-id="27880-217">aspnetcore50</span></span><br><span data-ttu-id="27880-218">dnxcore50</span><span class="sxs-lookup"><span data-stu-id="27880-218">dnxcore50</span></span><br><span data-ttu-id="27880-219">dnx</span><span class="sxs-lookup"><span data-stu-id="27880-219">dnx</span></span><br><span data-ttu-id="27880-220">dnx45</span><span class="sxs-lookup"><span data-stu-id="27880-220">dnx45</span></span><br><span data-ttu-id="27880-221">dnx451</span><span class="sxs-lookup"><span data-stu-id="27880-221">dnx451</span></span><br><span data-ttu-id="27880-222">dnx452</span><span class="sxs-lookup"><span data-stu-id="27880-222">dnx452</span></span>                  | <span data-ttu-id="27880-223">netcoreapp</span><span class="sxs-lookup"><span data-stu-id="27880-223">netcoreapp</span></span>  |
| <span data-ttu-id="27880-224">dotnet</span><span class="sxs-lookup"><span data-stu-id="27880-224">dotnet</span></span><br><span data-ttu-id="27880-225">dotnet50</span><span class="sxs-lookup"><span data-stu-id="27880-225">dotnet50</span></span><br><span data-ttu-id="27880-226">dotnet51</span><span class="sxs-lookup"><span data-stu-id="27880-226">dotnet51</span></span><br><span data-ttu-id="27880-227">dotnet52</span><span class="sxs-lookup"><span data-stu-id="27880-227">dotnet52</span></span><br><span data-ttu-id="27880-228">dotnet53</span><span class="sxs-lookup"><span data-stu-id="27880-228">dotnet53</span></span><br><span data-ttu-id="27880-229">dotnet54</span><span class="sxs-lookup"><span data-stu-id="27880-229">dotnet54</span></span><br><span data-ttu-id="27880-230">dotnet55</span><span class="sxs-lookup"><span data-stu-id="27880-230">dotnet55</span></span><br><span data-ttu-id="27880-231">dotnet56</span><span class="sxs-lookup"><span data-stu-id="27880-231">dotnet56</span></span> | <span data-ttu-id="27880-232">netstandard</span><span class="sxs-lookup"><span data-stu-id="27880-232">netstandard</span></span> |
| <span data-ttu-id="27880-233">netcore50</span><span class="sxs-lookup"><span data-stu-id="27880-233">netcore50</span></span>                                                                                  | <span data-ttu-id="27880-234">uap10.0</span><span class="sxs-lookup"><span data-stu-id="27880-234">uap10.0</span></span>     |
| <span data-ttu-id="27880-235">win</span><span class="sxs-lookup"><span data-stu-id="27880-235">win</span></span>                                                                                        | <span data-ttu-id="27880-236">netcore45</span><span class="sxs-lookup"><span data-stu-id="27880-236">netcore45</span></span>   |
| <span data-ttu-id="27880-237">win8</span><span class="sxs-lookup"><span data-stu-id="27880-237">win8</span></span>                                                                                       | <span data-ttu-id="27880-238">netcore45</span><span class="sxs-lookup"><span data-stu-id="27880-238">netcore45</span></span>   |
| <span data-ttu-id="27880-239">win81</span><span class="sxs-lookup"><span data-stu-id="27880-239">win81</span></span>                                                                                      | <span data-ttu-id="27880-240">netcore451</span><span class="sxs-lookup"><span data-stu-id="27880-240">netcore451</span></span>  |
| <span data-ttu-id="27880-241">win10</span><span class="sxs-lookup"><span data-stu-id="27880-241">win10</span></span>                                                                                      | <span data-ttu-id="27880-242">uap10.0</span><span class="sxs-lookup"><span data-stu-id="27880-242">uap10.0</span></span>     |
| <span data-ttu-id="27880-243">winrt</span><span class="sxs-lookup"><span data-stu-id="27880-243">winrt</span></span>                                                                                      | <span data-ttu-id="27880-244">netcore45</span><span class="sxs-lookup"><span data-stu-id="27880-244">netcore45</span></span>   |

## <a name="see-also"></a><span data-ttu-id="27880-245">请参阅</span><span class="sxs-lookup"><span data-stu-id="27880-245">See also</span></span>

- [<span data-ttu-id="27880-246">包、元包和框架</span><span class="sxs-lookup"><span data-stu-id="27880-246">Packages, Metapackages and Frameworks</span></span>](../core/packages.md)
- [<span data-ttu-id="27880-247">使用跨平台工具开发库</span><span class="sxs-lookup"><span data-stu-id="27880-247">Developing Libraries with Cross Platform Tools</span></span>](../core/tutorials/libraries.md)
- [<span data-ttu-id="27880-248">.NET Standard</span><span class="sxs-lookup"><span data-stu-id="27880-248">.NET Standard</span></span>](net-standard.md)
- [<span data-ttu-id="27880-249">.NET Core 版本控制</span><span class="sxs-lookup"><span data-stu-id="27880-249">.NET Core Versioning</span></span>](../core/versions/index.md)
- [<span data-ttu-id="27880-250">dotnet/standard GitHub 存储库</span><span class="sxs-lookup"><span data-stu-id="27880-250">dotnet/standard GitHub repository</span></span>](https://github.com/dotnet/standard)
- [<span data-ttu-id="27880-251">NuGet 工具 GitHub 存储库</span><span class="sxs-lookup"><span data-stu-id="27880-251">NuGet Tools GitHub Repository</span></span>](https://github.com/joelverhagen/NuGetTools)
- [<span data-ttu-id="27880-252">.NET 中的框架配置文件</span><span class="sxs-lookup"><span data-stu-id="27880-252">Framework Profiles in .NET</span></span>](https://blog.stephencleary.com/2012/05/framework-profiles-in-net.html)
