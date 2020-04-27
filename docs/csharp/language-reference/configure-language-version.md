---
title: C# 语言版本控制 - C# 指南
description: 了解如何根据项目确定 C# 语言版本，以及背后的原因。 了解如何手动重写默认值。
ms.date: 02/21/2020
ms.openlocfilehash: 850c4a860878593d80aaa3b7b38efaff9e003f43
ms.sourcegitcommit: 73aa9653547a1cd70ee6586221f79cc29b588ebd
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2020
ms.locfileid: "82102653"
---
# <a name="c-language-versioning"></a><span data-ttu-id="eec82-104">C# 语言版本控制</span><span class="sxs-lookup"><span data-stu-id="eec82-104">C# language versioning</span></span>

<span data-ttu-id="eec82-105">最新的 C# 编译器根据项目的一个或多个目标框架确定默认语言版本。</span><span class="sxs-lookup"><span data-stu-id="eec82-105">The latest C# compiler determines a default language version based on your project's target framework or frameworks.</span></span> <span data-ttu-id="eec82-106">Visual Studio 不提供用于更改值的 UI，但可以通过编辑 .csproj 文件来更改值  。</span><span class="sxs-lookup"><span data-stu-id="eec82-106">Visual Studio doesn't provide a UI to change the value, but you can change it by editing the *csproj* file.</span></span> <span data-ttu-id="eec82-107">此默认选择可确保使用与目标框架兼容的最新语言版本。</span><span class="sxs-lookup"><span data-stu-id="eec82-107">The choice of default ensures that you use the latest language version compatible with your target framework.</span></span> <span data-ttu-id="eec82-108">你将从访问与项目目标兼容的最新语言功能中受益。</span><span class="sxs-lookup"><span data-stu-id="eec82-108">You benefit from access to the latest language features compatible with your project's target.</span></span> <span data-ttu-id="eec82-109">此默认选择还可确保不会使用需要类型或运行时行为在目标框架中不可用的语言。</span><span class="sxs-lookup"><span data-stu-id="eec82-109">This default choice also ensures you don't use a language that requires types or runtime behavior not available in your target framework.</span></span> <span data-ttu-id="eec82-110">选择比默认版本更高的语言版本可能导致难以诊断编译时和运行时错误。</span><span class="sxs-lookup"><span data-stu-id="eec82-110">Choosing a language version newer than the default can cause hard to diagnose compile-time and runtime errors.</span></span>

<span data-ttu-id="eec82-111">本文中的规则适用于随 Visual Studio 2019 或 .NET Core 3.0 SDK 一起提供的编译器。</span><span class="sxs-lookup"><span data-stu-id="eec82-111">The rules in this article apply to the compiler delivered with Visual Studio 2019 or the .NET Core 3.0 SDK.</span></span> <span data-ttu-id="eec82-112">默认情况下，Visual Studio 2017 安装或早期 .NET Core SDK 版本中包含的 C# 编译器以 C# 7.0 为目标。</span><span class="sxs-lookup"><span data-stu-id="eec82-112">The C# compilers that are part of the Visual Studio 2017 installation or earlier .NET Core SDK versions target C# 7.0 by default.</span></span>

<span data-ttu-id="eec82-113">C# 8.0（和更高版本）仅在 .NET Core 3.x 和更高版本上受支持。</span><span class="sxs-lookup"><span data-stu-id="eec82-113">C# 8.0 (and higher) is supported only on .NET Core 3.x and newer versions.</span></span> <span data-ttu-id="eec82-114">许多最新功能需要 .NET Core 3.x 中引入的库和运行时功能：</span><span class="sxs-lookup"><span data-stu-id="eec82-114">Many of the newest features require library and runtime features introduced in .NET Core 3.x:</span></span>

- <span data-ttu-id="eec82-115">默认接口成员实现需要使用 .NET Core 3.0 CLR 中的新功能。</span><span class="sxs-lookup"><span data-stu-id="eec82-115">Default interface member implementation requires new features in the .NET Core 3.0 CLR.</span></span>
- <span data-ttu-id="eec82-116">异步流需要使用新类型 <xref:System.IAsyncDisposable?displayProperty=nameWithType>、<xref:System.Collections.Generic.IAsyncEnumerable%601?displayProperty=nameWithType> 和 <xref:System.Collections.Generic.IAsyncEnumerator%601?displayProperty=nameWithType>。</span><span class="sxs-lookup"><span data-stu-id="eec82-116">Async streams require the new types <xref:System.IAsyncDisposable?displayProperty=nameWithType>, <xref:System.Collections.Generic.IAsyncEnumerable%601?displayProperty=nameWithType>, and <xref:System.Collections.Generic.IAsyncEnumerator%601?displayProperty=nameWithType>.</span></span>
- <span data-ttu-id="eec82-117">索引和范围需要新类型 <xref:System.Index?displayProperty=nameWithType> 和 <xref:System.Range?displayProperty=nameWithType>。</span><span class="sxs-lookup"><span data-stu-id="eec82-117">Indexes and Ranges require the new types <xref:System.Index?displayProperty=nameWithType> and <xref:System.Range?displayProperty=nameWithType>.</span></span>
- <span data-ttu-id="eec82-118">可为 null 的引用类型利用几个[特性](attributes/nullable-analysis.md)来提供更准确的警告。</span><span class="sxs-lookup"><span data-stu-id="eec82-118">Nullable reference types make use of several [attributes](attributes/nullable-analysis.md) to provide better warnings.</span></span> <span data-ttu-id="eec82-119">这些特性是在 .NET Core 3.0 中添加的。</span><span class="sxs-lookup"><span data-stu-id="eec82-119">Those attributes were added in .NET Core 3.0.</span></span> <span data-ttu-id="eec82-120">其他目标框架并未使用这些特性中的任何一种进行批注。</span><span class="sxs-lookup"><span data-stu-id="eec82-120">Other target frameworks haven't been annotated with any of these attributes.</span></span> <span data-ttu-id="eec82-121">这意味着可为 null 的警告可能无法准确反映潜在问题。</span><span class="sxs-lookup"><span data-stu-id="eec82-121">That means nullable warnings may not accurately reflect potential issues.</span></span>

## <a name="defaults"></a><span data-ttu-id="eec82-122">默认值</span><span class="sxs-lookup"><span data-stu-id="eec82-122">Defaults</span></span>

<span data-ttu-id="eec82-123">编译器根据以下规则确定默认值：</span><span class="sxs-lookup"><span data-stu-id="eec82-123">The compiler determines a default based on these rules:</span></span>

|<span data-ttu-id="eec82-124">目标框架</span><span class="sxs-lookup"><span data-stu-id="eec82-124">Target framework</span></span>|<span data-ttu-id="eec82-125">version</span><span class="sxs-lookup"><span data-stu-id="eec82-125">version</span></span>|<span data-ttu-id="eec82-126">C# 语言版本的默认值</span><span class="sxs-lookup"><span data-stu-id="eec82-126">C# language version default</span></span>|
|----------------|-------|---------------------------|
|<span data-ttu-id="eec82-127">.NET Core</span><span class="sxs-lookup"><span data-stu-id="eec82-127">.NET Core</span></span>|<span data-ttu-id="eec82-128">3.x</span><span class="sxs-lookup"><span data-stu-id="eec82-128">3.x</span></span>|<span data-ttu-id="eec82-129">C# 8.0</span><span class="sxs-lookup"><span data-stu-id="eec82-129">C# 8.0</span></span>|
|<span data-ttu-id="eec82-130">.NET Core</span><span class="sxs-lookup"><span data-stu-id="eec82-130">.NET Core</span></span>|<span data-ttu-id="eec82-131">2.x</span><span class="sxs-lookup"><span data-stu-id="eec82-131">2.x</span></span>|<span data-ttu-id="eec82-132">C# 7.3</span><span class="sxs-lookup"><span data-stu-id="eec82-132">C# 7.3</span></span>|
|<span data-ttu-id="eec82-133">.NET Standard</span><span class="sxs-lookup"><span data-stu-id="eec82-133">.NET Standard</span></span>|<span data-ttu-id="eec82-134">2.1</span><span class="sxs-lookup"><span data-stu-id="eec82-134">2.1</span></span>|<span data-ttu-id="eec82-135">C# 8.0</span><span class="sxs-lookup"><span data-stu-id="eec82-135">C# 8.0</span></span>|
|<span data-ttu-id="eec82-136">.NET Standard</span><span class="sxs-lookup"><span data-stu-id="eec82-136">.NET Standard</span></span>|<span data-ttu-id="eec82-137">2.0</span><span class="sxs-lookup"><span data-stu-id="eec82-137">2.0</span></span>|<span data-ttu-id="eec82-138">C# 7.3</span><span class="sxs-lookup"><span data-stu-id="eec82-138">C# 7.3</span></span>|
|<span data-ttu-id="eec82-139">.NET Standard</span><span class="sxs-lookup"><span data-stu-id="eec82-139">.NET Standard</span></span>|<span data-ttu-id="eec82-140">1.x</span><span class="sxs-lookup"><span data-stu-id="eec82-140">1.x</span></span>|<span data-ttu-id="eec82-141">C# 7.3</span><span class="sxs-lookup"><span data-stu-id="eec82-141">C# 7.3</span></span>|
|<span data-ttu-id="eec82-142">.NET Framework</span><span class="sxs-lookup"><span data-stu-id="eec82-142">.NET Framework</span></span>|<span data-ttu-id="eec82-143">全部</span><span class="sxs-lookup"><span data-stu-id="eec82-143">all</span></span>|<span data-ttu-id="eec82-144">C# 7.3</span><span class="sxs-lookup"><span data-stu-id="eec82-144">C# 7.3</span></span>|

<span data-ttu-id="eec82-145">如果你的项目是以具有相应预览语言版本的预览框架为目标，那么使用的语言版本是预览语言版本。</span><span class="sxs-lookup"><span data-stu-id="eec82-145">When your project targets a preview framework that has a corresponding preview language version, the language version used is the preview language version.</span></span> <span data-ttu-id="eec82-146">你可在任何环境中使用该预览版提供的最新功能，而不会影响面向已发布 .NET Core 版本的项目。</span><span class="sxs-lookup"><span data-stu-id="eec82-146">You use the latest features with that preview in any environment, without affecting projects that target a released .NET Core version.</span></span>

## <a name="override-a-default"></a><span data-ttu-id="eec82-147">替代默认值</span><span class="sxs-lookup"><span data-stu-id="eec82-147">Override a default</span></span>

<span data-ttu-id="eec82-148">如果必须明确指定 C# 版本，可以通过以下几种方式实现：</span><span class="sxs-lookup"><span data-stu-id="eec82-148">If you must specify your C# version explicitly, you can do so in several ways:</span></span>

- <span data-ttu-id="eec82-149">手动编辑[项目文件](#edit-the-project-file)。</span><span class="sxs-lookup"><span data-stu-id="eec82-149">Manually edit your [project file](#edit-the-project-file).</span></span>
- <span data-ttu-id="eec82-150">为[子目录中的多个项目](#configure-multiple-projects)设置语言版本。</span><span class="sxs-lookup"><span data-stu-id="eec82-150">Set the language version [for multiple projects in a subdirectory](#configure-multiple-projects).</span></span>
- <span data-ttu-id="eec82-151">配置 [`-langversion` 编译器选项](compiler-options/langversion-compiler-option.md)。</span><span class="sxs-lookup"><span data-stu-id="eec82-151">Configure the [`-langversion` compiler option](compiler-options/langversion-compiler-option.md).</span></span>

### <a name="edit-the-project-file"></a><span data-ttu-id="eec82-152">编辑项目文件</span><span class="sxs-lookup"><span data-stu-id="eec82-152">Edit the project file</span></span>

<span data-ttu-id="eec82-153">可在项目文件中设置语言版本。</span><span class="sxs-lookup"><span data-stu-id="eec82-153">You can set the language version in your project file.</span></span> <span data-ttu-id="eec82-154">例如，如果你明确希望访问预览功能，请添加如下元素：</span><span class="sxs-lookup"><span data-stu-id="eec82-154">For example, if you explicitly want access to preview features, add an element like this:</span></span>

```xml
<PropertyGroup>
   <LangVersion>preview</LangVersion>
</PropertyGroup>
```

<span data-ttu-id="eec82-155">值 `preview` 使用编译器支持的最新可用的预览 C# 语言版本。</span><span class="sxs-lookup"><span data-stu-id="eec82-155">The value `preview` uses the latest available preview C# language version that your compiler supports.</span></span>

### <a name="configure-multiple-projects"></a><span data-ttu-id="eec82-156">配置多个项目</span><span class="sxs-lookup"><span data-stu-id="eec82-156">Configure multiple projects</span></span>

<span data-ttu-id="eec82-157">若要配置多个目录，可以创建包含 `<LangVersion>` 元素的 Directory.Build.props  文件。</span><span class="sxs-lookup"><span data-stu-id="eec82-157">To configure multiple projects, you can create a **Directory.Build.props** file that contains the `<LangVersion>` element.</span></span> <span data-ttu-id="eec82-158">通常是在解决方案目录中完成这件事。</span><span class="sxs-lookup"><span data-stu-id="eec82-158">You typically do that in your solution directory.</span></span> <span data-ttu-id="eec82-159">将以下内容添加到解决方案目录中的 Directory.Build.props  文件：</span><span class="sxs-lookup"><span data-stu-id="eec82-159">Add the following to a **Directory.Build.props** file in your solution directory:</span></span>

```xml
<Project>
 <PropertyGroup>
   <LangVersion>preview</LangVersion>
 </PropertyGroup>
</Project>
```

<span data-ttu-id="eec82-160">包含该文件的目录的所有子目录中的版本都将使用 C# 预览版。</span><span class="sxs-lookup"><span data-stu-id="eec82-160">Builds in all subdirectories of the directory containing that file will use the preview C# version.</span></span> <span data-ttu-id="eec82-161">有关详细信息，请参阅关于[自定义生成](/visualstudio/msbuild/customize-your-build)的文章。</span><span class="sxs-lookup"><span data-stu-id="eec82-161">For more information, see the article on [Customize your build](/visualstudio/msbuild/customize-your-build).</span></span>

## <a name="c-language-version-reference"></a><span data-ttu-id="eec82-162">C# 语言版本引用</span><span class="sxs-lookup"><span data-stu-id="eec82-162">C# language version reference</span></span>

<span data-ttu-id="eec82-163">下表显示当前所有 C# 语言版本。</span><span class="sxs-lookup"><span data-stu-id="eec82-163">The following table shows all current C# language versions.</span></span> <span data-ttu-id="eec82-164">如果编译器较旧，它可能不一定能识别每个值。</span><span class="sxs-lookup"><span data-stu-id="eec82-164">Your compiler may not necessarily understand every value if it's older.</span></span> <span data-ttu-id="eec82-165">如果安装的是 .NET Core 3.0 或更高版本，则可以访问列出的所有内容。</span><span class="sxs-lookup"><span data-stu-id="eec82-165">If you install .NET Core 3.0 or later, then you have access to everything listed.</span></span>

|<span data-ttu-id="eec82-166">“值”</span><span class="sxs-lookup"><span data-stu-id="eec82-166">Value</span></span>|<span data-ttu-id="eec82-167">含义</span><span class="sxs-lookup"><span data-stu-id="eec82-167">Meaning</span></span>|
|------------|-------------|
|<span data-ttu-id="eec82-168">preview</span><span class="sxs-lookup"><span data-stu-id="eec82-168">preview</span></span>|<span data-ttu-id="eec82-169">编译器接受最新预览版中的所有有效语言语法。</span><span class="sxs-lookup"><span data-stu-id="eec82-169">The compiler accepts all valid language syntax from the latest preview version.</span></span>|
|<span data-ttu-id="eec82-170">latest</span><span class="sxs-lookup"><span data-stu-id="eec82-170">latest</span></span>|<span data-ttu-id="eec82-171">编译器接受最新发布的编译器版本（包括次要版本）中的语法。</span><span class="sxs-lookup"><span data-stu-id="eec82-171">The compiler accepts syntax from the latest released version of the compiler (including minor version).</span></span>|
|<span data-ttu-id="eec82-172">latestMajor</span><span class="sxs-lookup"><span data-stu-id="eec82-172">latestMajor</span></span>|<span data-ttu-id="eec82-173">编译器接受最新发布的编译器主要版本中的语法。</span><span class="sxs-lookup"><span data-stu-id="eec82-173">The compiler accepts syntax from the latest released major version of the compiler.</span></span>|
|<span data-ttu-id="eec82-174">8.0</span><span class="sxs-lookup"><span data-stu-id="eec82-174">8.0</span></span>|<span data-ttu-id="eec82-175">编译器只接受 C# 8.0 或更低版本中所含的语法。</span><span class="sxs-lookup"><span data-stu-id="eec82-175">The compiler accepts only syntax that is included in C# 8.0 or lower.</span></span>|
|<span data-ttu-id="eec82-176">7.3</span><span class="sxs-lookup"><span data-stu-id="eec82-176">7.3</span></span>|<span data-ttu-id="eec82-177">编译器只接受 C# 7.3 或更低版本中所含的语法。</span><span class="sxs-lookup"><span data-stu-id="eec82-177">The compiler accepts only syntax that is included in C# 7.3 or lower.</span></span>|
|<span data-ttu-id="eec82-178">7.2</span><span class="sxs-lookup"><span data-stu-id="eec82-178">7.2</span></span>|<span data-ttu-id="eec82-179">编译器只接受 C# 7.2 或更低版本中所含的语法。</span><span class="sxs-lookup"><span data-stu-id="eec82-179">The compiler accepts only syntax that is included in C# 7.2 or lower.</span></span>|
|<span data-ttu-id="eec82-180">7.1</span><span class="sxs-lookup"><span data-stu-id="eec82-180">7.1</span></span>|<span data-ttu-id="eec82-181">编译器只接受 C# 7.1 或更低版本中所含的语法。</span><span class="sxs-lookup"><span data-stu-id="eec82-181">The compiler accepts only syntax that is included in C# 7.1 or lower.</span></span>|
|<span data-ttu-id="eec82-182">7</span><span class="sxs-lookup"><span data-stu-id="eec82-182">7</span></span>|<span data-ttu-id="eec82-183">编译器只接受 C# 7.0 或更低版本中所含的语法。</span><span class="sxs-lookup"><span data-stu-id="eec82-183">The compiler accepts only syntax that is included in C# 7.0 or lower.</span></span>|
|<span data-ttu-id="eec82-184">6</span><span class="sxs-lookup"><span data-stu-id="eec82-184">6</span></span>|<span data-ttu-id="eec82-185">编译器只接受 C# 6.0 或更低版本中所含的语法。</span><span class="sxs-lookup"><span data-stu-id="eec82-185">The compiler accepts only syntax that is included in C# 6.0 or lower.</span></span>|
|<span data-ttu-id="eec82-186">5</span><span class="sxs-lookup"><span data-stu-id="eec82-186">5</span></span>|<span data-ttu-id="eec82-187">编译器只接受 C# 5.0 或更低版本中所含的语法。</span><span class="sxs-lookup"><span data-stu-id="eec82-187">The compiler accepts only syntax that is included in C# 5.0 or lower.</span></span>|
|<span data-ttu-id="eec82-188">4</span><span class="sxs-lookup"><span data-stu-id="eec82-188">4</span></span>|<span data-ttu-id="eec82-189">编译器只接受 C# 4.0 或更低版本中所含的语法。</span><span class="sxs-lookup"><span data-stu-id="eec82-189">The compiler accepts only syntax that is included in C# 4.0 or lower.</span></span>|
|<span data-ttu-id="eec82-190">3</span><span class="sxs-lookup"><span data-stu-id="eec82-190">3</span></span>|<span data-ttu-id="eec82-191">编译器只接受 C# 3.0 或更低版本中所含的语法。</span><span class="sxs-lookup"><span data-stu-id="eec82-191">The compiler accepts only syntax that is included in C# 3.0 or lower.</span></span>|
|<span data-ttu-id="eec82-192">ISO-2</span><span class="sxs-lookup"><span data-stu-id="eec82-192">ISO-2</span></span>|<span data-ttu-id="eec82-193">编译器只接受 ISO/IEC 23270:2006 C# (2.0) 中所含的语法。</span><span class="sxs-lookup"><span data-stu-id="eec82-193">The compiler accepts only syntax that is included in ISO/IEC 23270:2006 C# (2.0).</span></span> |
|<span data-ttu-id="eec82-194">ISO-1</span><span class="sxs-lookup"><span data-stu-id="eec82-194">ISO-1</span></span>|<span data-ttu-id="eec82-195">编译器只接受 ISO/IEC 23270:2003 C# (1.0/1.2) 中所含的语法。</span><span class="sxs-lookup"><span data-stu-id="eec82-195">The compiler accepts only syntax that is included in ISO/IEC 23270:2003 C# (1.0/1.2).</span></span> |
