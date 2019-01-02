---
title: .NET Core CLI 扩展性模型
description: 了解如何扩展命令行接口 (CLI) 工具。
author: blackdwarf
ms.date: 04/12/2017
ms.custom: seodec18
ms.openlocfilehash: 3aedd1d507fde1cd7402ef97fa00d0c7f13005e3
ms.sourcegitcommit: e6ad58812807937b03f5c581a219dcd7d1726b1d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2018
ms.locfileid: "53170231"
---
# <a name="net-core-cli-tools-extensibility-model"></a><span data-ttu-id="0d99a-103">.NET Core CLI 工具扩展性模型</span><span class="sxs-lookup"><span data-stu-id="0d99a-103">.NET Core CLI tools extensibility model</span></span>

<span data-ttu-id="0d99a-104">本文档介绍扩展 .NET Core 命令行接口 (CLI) 工具的多种方式，并解释驱动每个方式的不同方案。</span><span class="sxs-lookup"><span data-stu-id="0d99a-104">This document covers the different ways you can extend the .NET Core Command-line Interface (CLI) tools and explain the scenarios that drive each one of them.</span></span>
<span data-ttu-id="0d99a-105">还将介绍如何使用这些工具，以及如何生成不同类型的工具。</span><span class="sxs-lookup"><span data-stu-id="0d99a-105">You'll see how to consume the tools as well as how to build the different types of tools.</span></span>

## <a name="how-to-extend-cli-tools"></a><span data-ttu-id="0d99a-106">如何扩展 CLI 工具</span><span class="sxs-lookup"><span data-stu-id="0d99a-106">How to extend CLI tools</span></span>
<span data-ttu-id="0d99a-107">主要可以通过以下三种方式扩展 CLI 工具：</span><span class="sxs-lookup"><span data-stu-id="0d99a-107">The CLI tools can be extended in three main ways:</span></span>

1. [<span data-ttu-id="0d99a-108">通过基于每个项目的 NuGet 包</span><span class="sxs-lookup"><span data-stu-id="0d99a-108">Via NuGet packages on a per-project basis</span></span>](#per-project-based-extensibility)

   <span data-ttu-id="0d99a-109">基于项目的工具包含在项目上下文中，但允许通过还原轻松安装。</span><span class="sxs-lookup"><span data-stu-id="0d99a-109">Per-project tools are contained within the project's context, but they allow easy installation through restoration.</span></span>

2. [<span data-ttu-id="0d99a-110">通过具有自定义目标的 NuGet 包</span><span class="sxs-lookup"><span data-stu-id="0d99a-110">Via NuGet packages with custom targets</span></span>](#custom-targets)

   <span data-ttu-id="0d99a-111">通过自定义目标，可使用自定义任务轻松扩展生成过程。</span><span class="sxs-lookup"><span data-stu-id="0d99a-111">Custom targets allow you to easily extend the build process with custom tasks.</span></span>

3. [<span data-ttu-id="0d99a-112">通过系统路径</span><span class="sxs-lookup"><span data-stu-id="0d99a-112">Via the system's PATH</span></span>](#path-based-extensibility)

   <span data-ttu-id="0d99a-113">基于路径的工具非常适合可在一台计算机上使用的常规、跨项目工具。</span><span class="sxs-lookup"><span data-stu-id="0d99a-113">PATH-based tools are good for general, cross-project tools that are usable on a single machine.</span></span>

<span data-ttu-id="0d99a-114">上方列出的三种扩展性机制并不相互排斥。</span><span class="sxs-lookup"><span data-stu-id="0d99a-114">The three extensibility mechanisms outlined above are not exclusive.</span></span> <span data-ttu-id="0d99a-115">可以单独使用、同时使用或结合使用。</span><span class="sxs-lookup"><span data-stu-id="0d99a-115">You can use one, or all, or a combination of them.</span></span> <span data-ttu-id="0d99a-116">选择何种机制很大程度上取决于希望通过扩展实现的目标。</span><span class="sxs-lookup"><span data-stu-id="0d99a-116">Which one to pick depends largely on the goal you are trying to achieve with your extension.</span></span>

## <a name="per-project-based-extensibility"></a><span data-ttu-id="0d99a-117">基于每个项目的扩展性</span><span class="sxs-lookup"><span data-stu-id="0d99a-117">Per-project based extensibility</span></span>
<span data-ttu-id="0d99a-118">基于项目的工具是作为 NuGet 包分布的[依赖框架的部署](../deploying/index.md#framework-dependent-deployments-fdd)。</span><span class="sxs-lookup"><span data-stu-id="0d99a-118">Per-project tools are [framework-dependent deployments](../deploying/index.md#framework-dependent-deployments-fdd) that are distributed as NuGet packages.</span></span> <span data-ttu-id="0d99a-119">工具仅在项目的上下文中可用，这些工具被该项目引用或为该项目还原。</span><span class="sxs-lookup"><span data-stu-id="0d99a-119">Tools are only available in the context of the project that references them and for which they are restored.</span></span> <span data-ttu-id="0d99a-120">项目上下文外（例如，包含该项目的目录外）的调用将因无法找到命令而失败。</span><span class="sxs-lookup"><span data-stu-id="0d99a-120">Invocation outside of the context of the project (for example, outside of the directory that contains the project) will fail because the command cannot be found.</span></span>

<span data-ttu-id="0d99a-121">这些工具非常适合生成服务器，因为除项目文件外不需要任何条件。</span><span class="sxs-lookup"><span data-stu-id="0d99a-121">These tools are perfect for build servers, since nothing outside of the project file is needed.</span></span> <span data-ttu-id="0d99a-122">生成过程会对所生成的项目运行还原操作，并且工具可用。</span><span class="sxs-lookup"><span data-stu-id="0d99a-122">The build process runs restore for the project it builds and tools will be available.</span></span> <span data-ttu-id="0d99a-123">语言项目（如 F#）也属于此类别；因为只能采用某种特定语言编写每个项目。</span><span class="sxs-lookup"><span data-stu-id="0d99a-123">Language projects, such as F#, are also in this category since each project can only be written in one specific language.</span></span>

<span data-ttu-id="0d99a-124">最后，此扩展性模型支持创建需要访问项目生成输出的工具。</span><span class="sxs-lookup"><span data-stu-id="0d99a-124">Finally, this extensibility model provides support for creation of tools that need access to the built output of the project.</span></span> <span data-ttu-id="0d99a-125">例如，[ASP.NET](https://www.asp.net/) MVC 应用程序中的多种 Razor 视图工具均属于此类别。</span><span class="sxs-lookup"><span data-stu-id="0d99a-125">For instance, various Razor view tools in [ASP.NET](https://www.asp.net/) MVC applications fall into this category.</span></span>

### <a name="consuming-per-project-tools"></a><span data-ttu-id="0d99a-126">使用基于项目的工具</span><span class="sxs-lookup"><span data-stu-id="0d99a-126">Consuming per-project tools</span></span>
<span data-ttu-id="0d99a-127">使用这些工具要求将想要使用的每个工具的 `<DotNetCliToolReference>` 元素添加到项目文件。</span><span class="sxs-lookup"><span data-stu-id="0d99a-127">Consuming these tools requires you to add a `<DotNetCliToolReference>` element to your project file for each tool you want to use.</span></span> <span data-ttu-id="0d99a-128">在 `<DotNetCliToolReference>` 元素中，引用该工具所在的包并指定所需的版本。</span><span class="sxs-lookup"><span data-stu-id="0d99a-128">Inside the `<DotNetCliToolReference>` element, you reference the package in which the tool resides and specify the version you need.</span></span> <span data-ttu-id="0d99a-129">运行 [`dotnet restore`](dotnet-restore.md) 后，将还原该工具及其依赖项。</span><span class="sxs-lookup"><span data-stu-id="0d99a-129">After running [`dotnet restore`](dotnet-restore.md), the tool and its dependencies are restored.</span></span>

[!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]

<span data-ttu-id="0d99a-130">对于需要加载用于执行的项目生成输出的工具，通常还有一个依赖项，它位于项目文件中的常规依赖项下。</span><span class="sxs-lookup"><span data-stu-id="0d99a-130">For tools that need to load the build output of the project for execution, there is usually another dependency which is listed under the regular dependencies in the project file.</span></span> <span data-ttu-id="0d99a-131">由于 CLI 使用 MSBuild 作为其生成引擎，因此建议将该工具的这些部分作为自定义 MSBuild [目标](/visualstudio/msbuild/msbuild-targets)和[任务](/visualstudio/msbuild/msbuild-tasks)写入，以便这些部分可以参与整个生成过程。</span><span class="sxs-lookup"><span data-stu-id="0d99a-131">Since CLI uses MSBuild as its build engine, we recommend that these parts of the tool be written as custom MSBuild [targets](/visualstudio/msbuild/msbuild-targets) and [tasks](/visualstudio/msbuild/msbuild-tasks), since they can then take part in the overall build process.</span></span> <span data-ttu-id="0d99a-132">此外，它们还可以轻松获取通过该生成产生的所有数据（例如，输出文件的位置、正在生成的当前配置等）。所有此类信息将成为一组可从任意目标中读取的 MSBuild 属性。</span><span class="sxs-lookup"><span data-stu-id="0d99a-132">Also, they can get any and all data easily that is produced via the build, such as the location of the output files, the current configuration being built, etc. All this information becomes a set of MSBuild properties that can be read from any target.</span></span> <span data-ttu-id="0d99a-133">本文档的后面将介绍如何使用 NuGet 添加自定义目标。</span><span class="sxs-lookup"><span data-stu-id="0d99a-133">You can see how to add a custom target using NuGet later in this document.</span></span>

<span data-ttu-id="0d99a-134">我们来看看将简单的工具专用工具添加到简单项目的示例。</span><span class="sxs-lookup"><span data-stu-id="0d99a-134">Let's review an example of adding a simple tools-only tool to a simple project.</span></span> <span data-ttu-id="0d99a-135">假定示例命令称为 `dotnet-api-search`，通过它可搜索指定 API 的所有 NuGet 包，以下是使用该工具的控制台应用程序的项目文件：</span><span class="sxs-lookup"><span data-stu-id="0d99a-135">Given an example command called `dotnet-api-search` that allows you to search through the NuGet packages for the specified API, here is a console application's project file that uses that tool:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <OutputType>Exe</OutputType>
    <TargetFramework>netcoreapp2.1</TargetFramework>
  </PropertyGroup>

  <!-- The tools reference -->
  <ItemGroup>
    <DotNetCliToolReference Include="dotnet-api-search" Version="1.0.0" />
  </ItemGroup>
</Project>
```

<span data-ttu-id="0d99a-136">`<DotNetCliToolReference>` 元素采用与 `<PackageReference>` 元素相同的方式进行结构化。</span><span class="sxs-lookup"><span data-stu-id="0d99a-136">The `<DotNetCliToolReference>` element is structured in a similar way as the `<PackageReference>` element.</span></span> <span data-ttu-id="0d99a-137">它需要包含该工具及其可还原版本的包的包 ID。</span><span class="sxs-lookup"><span data-stu-id="0d99a-137">It needs the package ID of the package containing the tool and its version to be able to restore.</span></span>

### <a name="building-tools"></a><span data-ttu-id="0d99a-138">生成工具</span><span class="sxs-lookup"><span data-stu-id="0d99a-138">Building tools</span></span>
<span data-ttu-id="0d99a-139">如前所述，工具仅仅是可移植控制台应用程序。</span><span class="sxs-lookup"><span data-stu-id="0d99a-139">As mentioned, tools are just portable console applications.</span></span> <span data-ttu-id="0d99a-140">可以采用与生成其他控制台应用程序类似的方式生成工具。</span><span class="sxs-lookup"><span data-stu-id="0d99a-140">You build tools as you would build any other console application.</span></span>
<span data-ttu-id="0d99a-141">生成后，使用 [`dotnet pack`](dotnet-pack.md) 命令创建 NuGet 包（.nupkg 文件），其中包含代码和依赖项等相关信息。</span><span class="sxs-lookup"><span data-stu-id="0d99a-141">After you build it, you use the [`dotnet pack`](dotnet-pack.md) command to create a NuGet package (.nupkg file) that contains your code, information about its dependencies, and so on.</span></span> <span data-ttu-id="0d99a-142">可以随意命名包，但内部应用程序（即实际的工具二进制文件）必须遵循 `dotnet-<command>` 的约定，以便 `dotnet` 能够调用它。</span><span class="sxs-lookup"><span data-stu-id="0d99a-142">You can give any name to the package, but the application inside, the actual tool binary, has to conform to the convention of `dotnet-<command>` in order for `dotnet` to be able to invoke it.</span></span>

> [!NOTE]
> <span data-ttu-id="0d99a-143">在低于 RC3 版本的 .NET Core 命令行工具中，`dotnet pack` 命令存在一个 bug，导致 `runtime.config.json` 无法与该工具一起打包。</span><span class="sxs-lookup"><span data-stu-id="0d99a-143">In pre-RC3 versions of the .NET Core command-line tools, the `dotnet pack` command had a bug that caused the `runtime.config.json` to not be packed with the tool.</span></span> <span data-ttu-id="0d99a-144">缺少该文件导致发生运行时错误。</span><span class="sxs-lookup"><span data-stu-id="0d99a-144">Lacking that file results in errors at runtime.</span></span> <span data-ttu-id="0d99a-145">如果遇到此行为，请务必更新到最新工具，然后重试 `dotnet pack`。</span><span class="sxs-lookup"><span data-stu-id="0d99a-145">If you encounter this behavior, be sure to update to the latest tooling and try the `dotnet pack` again.</span></span>

<span data-ttu-id="0d99a-146">由于工具是可移植应用程序，因此使用该工具的用户必须拥有生成该工具时所针对的 .NET Core 库版本，以便运行此工具。</span><span class="sxs-lookup"><span data-stu-id="0d99a-146">Since tools are portable applications, the user consuming the tool must have the version of the .NET Core libraries that the tool was built against in order to run the tool.</span></span> <span data-ttu-id="0d99a-147">工具使用的以及 .NET Core 库未包含的其他任何依赖项均被还原并放置在 NuGet 缓存中。</span><span class="sxs-lookup"><span data-stu-id="0d99a-147">Any other dependency that the tool uses and that is not contained within the .NET Core libraries is restored and placed in the NuGet cache.</span></span> <span data-ttu-id="0d99a-148">因此，使用 .NET Core 库和 NuGet 缓存中的程序集可以运行整个工具。</span><span class="sxs-lookup"><span data-stu-id="0d99a-148">The entire tool is, therefore, run using the assemblies from the .NET Core libraries as well as assemblies from the NuGet cache.</span></span>

<span data-ttu-id="0d99a-149">这些类型的工具含有依赖项关系图，它完全独立于使用这些工具的项目的依赖项关系图。</span><span class="sxs-lookup"><span data-stu-id="0d99a-149">These kinds of tools have a dependency graph that is completely separate from the dependency graph of the project that uses them.</span></span> <span data-ttu-id="0d99a-150">还原过程将首先还原项目的依赖项，然后还原每个工具及其依赖项。</span><span class="sxs-lookup"><span data-stu-id="0d99a-150">The restore process first restores the project's dependencies and then restores each of the tools and their dependencies.</span></span>

<span data-ttu-id="0d99a-151">可在 [.NET Core CLI 存储库](https://github.com/dotnet/cli/tree/release/2.1/TestAssets/TestProjects)中找到有关此过程的更多示例和不同组合。</span><span class="sxs-lookup"><span data-stu-id="0d99a-151">You can find richer examples and different combinations of this in the [.NET Core CLI repo](https://github.com/dotnet/cli/tree/release/2.1/TestAssets/TestProjects).</span></span>
<span data-ttu-id="0d99a-152">还可以在相同存储库中查看[所用工具的实现](https://github.com/dotnet/cli/tree/release/2.1/TestAssets/TestPackages)。</span><span class="sxs-lookup"><span data-stu-id="0d99a-152">You can also see the [implementation of tools used](https://github.com/dotnet/cli/tree/release/2.1/TestAssets/TestPackages) in the same repo.</span></span>

### <a name="custom-targets"></a><span data-ttu-id="0d99a-153">自定义目标</span><span class="sxs-lookup"><span data-stu-id="0d99a-153">Custom targets</span></span>
<span data-ttu-id="0d99a-154">NuGet 可将[自定义 MSBuild 目标和属性文件打包](/nuget/create-packages/creating-a-package#including-msbuild-props-and-targets-in-a-package)。</span><span class="sxs-lookup"><span data-stu-id="0d99a-154">NuGet has the capability to [package custom MSBuild targets and props files](/nuget/create-packages/creating-a-package#including-msbuild-props-and-targets-in-a-package).</span></span> <span data-ttu-id="0d99a-155">在移动 .NET Core CLI 工具以使用 MSBuild 后，会对 .NET Core 项目应用可扩展性的相同机制。</span><span class="sxs-lookup"><span data-stu-id="0d99a-155">With the move of the .NET Core CLI tools to use MSBuild, the same mechanism of extensibility now applies to .NET Core projects.</span></span> <span data-ttu-id="0d99a-156">若要扩展生成过程、访问生成过程中的任何项目（如生成的文件）或检查调用生成时使用的配置等，建议使用该类型的扩展。</span><span class="sxs-lookup"><span data-stu-id="0d99a-156">You would use this type of extensibility when you want to extend the build process, or when you want to access any of the artifacts in the build process, such as generated files, or you want to inspect the configuration under which the build is invoked, etc.</span></span>

<span data-ttu-id="0d99a-157">在下面的示例中，可看到目标的项目文件，它使用的是 `csproj` 语法。</span><span class="sxs-lookup"><span data-stu-id="0d99a-157">In the following example, you can see the target's project file using the `csproj` syntax.</span></span> <span data-ttu-id="0d99a-158">该语法指示 [`dotnet pack`](dotnet-pack.md) 命令对哪些内容打包，以便将目标文件和程序集放在包中的 build 文件夹内。</span><span class="sxs-lookup"><span data-stu-id="0d99a-158">This instructs the [`dotnet pack`](dotnet-pack.md) command what to package, placing the targets files as well as the assemblies into the *build* folder inside the package.</span></span> <span data-ttu-id="0d99a-159">请注意将 `Label` 属性设置为 `dotnet pack instructions` 的 `<ItemGroup>` 元素，以及在其下定义的目标。</span><span class="sxs-lookup"><span data-stu-id="0d99a-159">Notice the `<ItemGroup>` element that has the `Label` property set to `dotnet pack instructions`, and the Target defined beneath it.</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <Description>Sample Packer</Description>
    <VersionPrefix>0.1.0-preview</VersionPrefix>
    <TargetFramework>netstandard1.3</TargetFramework>
    <DebugType>portable</DebugType>
    <AssemblyName>SampleTargets.PackerTarget</AssemblyName>
  </PropertyGroup>
  <ItemGroup>
    <EmbeddedResource Include="Resources\Pkg\dist-template.xml;compiler\resources\**\*" Exclude="bin\**;obj\**;**\*.xproj;packages\**" />
    <None Include="build\SampleTargets.PackerTarget.targets" />
  </ItemGroup>
  <ItemGroup Label="dotnet pack instructions">
    <Content Include="build\*.targets">
      <Pack>true</Pack>
      <PackagePath>build\</PackagePath>
    </Content>
  </ItemGroup>
  <Target Name="CollectRuntimeOutputs" BeforeTargets="_GetPackageFiles">
    <!-- Collect these items inside a target that runs after build but before packaging. -->
    <ItemGroup>
      <Content Include="$(OutputPath)\*.dll;$(OutputPath)\*.json">
        <Pack>true</Pack>
        <PackagePath>build\</PackagePath>
      </Content>
    </ItemGroup>
  </Target>
  <ItemGroup>
    <PackageReference Include="Microsoft.Extensions.DependencyModel" Version="1.0.1-beta-000933"/>
    <PackageReference Include="Microsoft.Build.Framework" Version="0.1.0-preview-00028-160627" />
    <PackageReference Include="Microsoft.Build.Utilities.Core" Version="0.1.0-preview-00028-160627" />
    <PackageReference Include="Newtonsoft.Json" Version="9.0.1" />
  </ItemGroup>
  <ItemGroup />
  <PropertyGroup Label="Globals">
    <ProjectGuid>463c66f0-921d-4d34-8bde-7c9d0bffaf7b</ProjectGuid>
  </PropertyGroup>
  <PropertyGroup Condition=" '$(TargetFramework)' == 'netstandard1.3' ">
    <DefineConstants>$(DefineConstants);NETSTANDARD1_3</DefineConstants>
  </PropertyGroup>
  <PropertyGroup Condition=" '$(Configuration)' == 'Release' ">
    <DefineConstants>$(DefineConstants);RELEASE</DefineConstants>
  </PropertyGroup>
</Project>
```

<span data-ttu-id="0d99a-160">若要使用自定义目标，请提供指向此程序包的 `<PackageReference>` 以及项目内正在进行扩展的该程序包版本。</span><span class="sxs-lookup"><span data-stu-id="0d99a-160">Consuming custom targets is done by providing a `<PackageReference>` that points to the package and its version inside the project that is being extended.</span></span> <span data-ttu-id="0d99a-161">与工具不同，自定义目标包未包含在使用项目中的依赖项结尾。</span><span class="sxs-lookup"><span data-stu-id="0d99a-161">Unlike the tools, the custom targets package does get included into the consuming project's dependency closure.</span></span>

<span data-ttu-id="0d99a-162">使用自定义目标仅取决于配置方式。</span><span class="sxs-lookup"><span data-stu-id="0d99a-162">Using the custom target depends solely on how you configure it.</span></span> <span data-ttu-id="0d99a-163">由于它是 MSBuild 目标，因此会依赖于给定的目标并在另一个目标后运行，也可使用 `dotnet msbuild -t:<target-name>` 命令手动调用。</span><span class="sxs-lookup"><span data-stu-id="0d99a-163">Since it's an MSBuild target, it can depend on a given target, run after another target and can also be manually invoked using the `dotnet msbuild -t:<target-name>` command.</span></span>

<span data-ttu-id="0d99a-164">但是，如果要为用户提供更好的用户体验，可以合并基于项目的工具和自定义目标。</span><span class="sxs-lookup"><span data-stu-id="0d99a-164">However, if you want to provide a better user experience to your users, you can combine per-project tools and custom targets.</span></span> <span data-ttu-id="0d99a-165">在这种情况下，基于项目的工具实质上只需接受任何所需的参数并将其转换为执行目标所需的 [`dotnet msbuild`](dotnet-msbuild.md) 调用。</span><span class="sxs-lookup"><span data-stu-id="0d99a-165">In this scenario, the per-project tool would essentially just accept whatever needed parameters and would translate that into the required [`dotnet msbuild`](dotnet-msbuild.md) invocation that would execute the target.</span></span> <span data-ttu-id="0d99a-166">有关此类协同作用的示例，请访问 [`dotnet-packer`](https://github.com/dotnet/MVPSummitHackathon2016/tree/master/dotnet-packer) 项目中的 [2016 年编程马拉松 MVP 峰会示例](https://github.com/dotnet/MVPSummitHackathon2016)存储库。</span><span class="sxs-lookup"><span data-stu-id="0d99a-166">You can see a sample of this kind of synergy on the [MVP Summit 2016 Hackathon samples](https://github.com/dotnet/MVPSummitHackathon2016) repo in the [`dotnet-packer`](https://github.com/dotnet/MVPSummitHackathon2016/tree/master/dotnet-packer) project.</span></span>

### <a name="path-based-extensibility"></a><span data-ttu-id="0d99a-167">基于路径的扩展</span><span class="sxs-lookup"><span data-stu-id="0d99a-167">PATH-based extensibility</span></span>
<span data-ttu-id="0d99a-168">基于路径的扩展常用于开发计算机，此计算机需要在概念上涵盖多个项目的工具。</span><span class="sxs-lookup"><span data-stu-id="0d99a-168">PATH-based extensibility is usually used for development machines where you need a tool that conceptually covers more than a single project.</span></span> <span data-ttu-id="0d99a-169">此扩展机制的主要缺点在于必须将其关联到工具所在的计算机。</span><span class="sxs-lookup"><span data-stu-id="0d99a-169">The main drawback of this extension mechanism is that it's tied to the machine where the tool exists.</span></span> <span data-ttu-id="0d99a-170">如果其他计算机上需要该机制，则必须对其进行部署。</span><span class="sxs-lookup"><span data-stu-id="0d99a-170">If you need it on another machine, you would have to deploy it.</span></span>

<span data-ttu-id="0d99a-171">此 CLI 工具集扩展的模式就非常简单。</span><span class="sxs-lookup"><span data-stu-id="0d99a-171">This pattern of CLI toolset extensibility is very simple.</span></span> <span data-ttu-id="0d99a-172">正如 [.NET Core CLI 概述](index.md)中所述，`dotnet` 驱动程序可以运行以 `dotnet-<command>` 约定命名的任何命令。</span><span class="sxs-lookup"><span data-stu-id="0d99a-172">As covered in the [.NET Core CLI overview](index.md), `dotnet` driver can run any command that is named after the `dotnet-<command>` convention.</span></span> <span data-ttu-id="0d99a-173">默认的解析逻辑将首先探测多个位置，最后探测系统路径。</span><span class="sxs-lookup"><span data-stu-id="0d99a-173">The default resolution logic first probes several locations and finally falls back to the system PATH.</span></span> <span data-ttu-id="0d99a-174">如果请求的命令存在于系统路径中并且属于可调用的二进制文件，则 `dotnet` 驱动程序将调用它。</span><span class="sxs-lookup"><span data-stu-id="0d99a-174">If the requested command exists in the system PATH and is a binary that can be invoked, `dotnet` driver will invoke it.</span></span>

<span data-ttu-id="0d99a-175">文件必须是可执行的。</span><span class="sxs-lookup"><span data-stu-id="0d99a-175">The file must be executable.</span></span> <span data-ttu-id="0d99a-176">在 Unix 系统上，这表示通过 `chmod +x` 设置了执行位的任何内容。</span><span class="sxs-lookup"><span data-stu-id="0d99a-176">On Unix systems, this means anything that has the execute bit set via `chmod +x`.</span></span> <span data-ttu-id="0d99a-177">在 Windows 上，可使用 cmd 文件。</span><span class="sxs-lookup"><span data-stu-id="0d99a-177">On Windows, you can use *cmd* files.</span></span>

<span data-ttu-id="0d99a-178">来看看非常简单的“Hello World”工具的实现。</span><span class="sxs-lookup"><span data-stu-id="0d99a-178">Let's take a look at the very simple implementation of a "Hello World" tool.</span></span> <span data-ttu-id="0d99a-179">我们将在 Windows 上同时使用 `bash` 和 `cmd`。</span><span class="sxs-lookup"><span data-stu-id="0d99a-179">We will use both `bash` and `cmd` on Windows.</span></span>
<span data-ttu-id="0d99a-180">下列命令将简单地向控制台回显“Hello World”。</span><span class="sxs-lookup"><span data-stu-id="0d99a-180">The following command will simply echo "Hello World" to the console.</span></span>

```bash
#!/bin/bash

echo "Hello World!"
```

```cmd
echo "Hello World"
```

<span data-ttu-id="0d99a-181">在 macOS 上，可以将此脚本另存为 `dotnet-hello` 并使用 `chmod +x dotnet-hello` 设置其可执行位。</span><span class="sxs-lookup"><span data-stu-id="0d99a-181">On macOS, we can save this script as `dotnet-hello` and set its executable bit with `chmod +x dotnet-hello`.</span></span> <span data-ttu-id="0d99a-182">然后，可以使用命令 `ln -s <full_path>/dotnet-hello /usr/local/bin/` 在 `/usr/local/bin` 中创建其符号链接。</span><span class="sxs-lookup"><span data-stu-id="0d99a-182">We can then create a symbolic link to it in `/usr/local/bin` using the command `ln -s <full_path>/dotnet-hello /usr/local/bin/`.</span></span> <span data-ttu-id="0d99a-183">这样，就可以使用 `dotnet hello` 语法调用命令。</span><span class="sxs-lookup"><span data-stu-id="0d99a-183">This will make it possible to invoke the command using the `dotnet hello` syntax.</span></span>

<span data-ttu-id="0d99a-184">在 Windows 上，可将此脚本另存为 `dotnet-hello.cmd`，并放在系统路径中（也可以将其添加到已位于该路径中的文件夹内）。</span><span class="sxs-lookup"><span data-stu-id="0d99a-184">On Windows, we can save this script as `dotnet-hello.cmd` and put it in a location that is in a system path (or you can add it to a folder that is already in the path).</span></span> <span data-ttu-id="0d99a-185">然后，只需使用 `dotnet hello` 即可运行此示例。</span><span class="sxs-lookup"><span data-stu-id="0d99a-185">After this, you can just use `dotnet hello` to run this example.</span></span>
