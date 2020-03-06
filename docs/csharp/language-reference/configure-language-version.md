---
title: C# 语言版本控制 - C# 指南
description: 了解如何根据项目确定 C# 语言版本，以及背后的原因。 了解如何手动重写默认值。
ms.date: 02/21/2020
ms.openlocfilehash: 2be76fdac471a7175b661d896b0da2910b3609f3
ms.sourcegitcommit: 44a7cd8687f227fc6db3211ccf4783dc20235e51
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/26/2020
ms.locfileid: "77626759"
---
# <a name="c-language-versioning"></a><span data-ttu-id="945fa-104">C# 语言版本控制</span><span class="sxs-lookup"><span data-stu-id="945fa-104">C# language versioning</span></span>

<span data-ttu-id="945fa-105">最新的 C# 编译器根据项目的一个或多个目标框架确定默认语言版本。</span><span class="sxs-lookup"><span data-stu-id="945fa-105">The latest C# compiler determines a default language version based on your project's target framework or frameworks.</span></span> <span data-ttu-id="945fa-106">Visual Studio 不提供用于更改值的 UI，但可以通过编辑 .csproj 文件来更改值  。</span><span class="sxs-lookup"><span data-stu-id="945fa-106">Visual Studio doesn't provide a UI to change the value, but you can change it by editing the *csproj* file.</span></span> <span data-ttu-id="945fa-107">此默认选择可确保使用与目标框架兼容的最新语言版本。</span><span class="sxs-lookup"><span data-stu-id="945fa-107">The choice of default ensures that you use the latest language version compatible with your target framework.</span></span> <span data-ttu-id="945fa-108">你将从访问与项目目标兼容的最新语言功能中受益。</span><span class="sxs-lookup"><span data-stu-id="945fa-108">You benefit from access to the latest language features compatible with your project's target.</span></span> <span data-ttu-id="945fa-109">此默认选择还可确保不会使用需要类型或运行时行为在目标框架中不可用的语言。</span><span class="sxs-lookup"><span data-stu-id="945fa-109">This default choice also ensures you don't use a language that requires types or runtime behavior not available in your target framework.</span></span> <span data-ttu-id="945fa-110">选择比默认版本更高的语言版本可能导致难以诊断编译时和运行时错误。</span><span class="sxs-lookup"><span data-stu-id="945fa-110">Choosing a language version newer than the default can cause hard to diagnose compile-time and runtime errors.</span></span>

<span data-ttu-id="945fa-111">C# 8.0（和更高版本）仅在 .NET Core 3.x 和更高版本上受支持。</span><span class="sxs-lookup"><span data-stu-id="945fa-111">C# 8.0 (and higher) is supported only on .NET Core 3.x and newer versions.</span></span> <span data-ttu-id="945fa-112">许多最新功能需要 .NET Core 3.x 中引入的库和运行时功能：</span><span class="sxs-lookup"><span data-stu-id="945fa-112">Many of the newest features require library and runtime features introduced in .NET Core 3.x:</span></span>

- <span data-ttu-id="945fa-113">默认接口成员实现需要使用 .NET Core 3.0 CLR 中的新功能。</span><span class="sxs-lookup"><span data-stu-id="945fa-113">Default interface member implementation requires new features in the .NET Core 3.0 CLR.</span></span>
- <span data-ttu-id="945fa-114">异步流需要使用新类型 <xref:System.IAsyncDisposable?displayProperty=nameWithType>、<xref:System.Collections.Generic.IAsyncEnumerable%601?displayProperty=nameWithType> 和 <xref:System.Collections.Generic.IAsyncEnumerator%601?displayProperty=nameWithType>。</span><span class="sxs-lookup"><span data-stu-id="945fa-114">Async streams require the new types <xref:System.IAsyncDisposable?displayProperty=nameWithType>, <xref:System.Collections.Generic.IAsyncEnumerable%601?displayProperty=nameWithType>, and <xref:System.Collections.Generic.IAsyncEnumerator%601?displayProperty=nameWithType>.</span></span>
- <span data-ttu-id="945fa-115">索引和范围需要新类型 <xref:System.Index?displayProperty=nameWithType> 和 <xref:System.Range?displayProperty=nameWithType>。</span><span class="sxs-lookup"><span data-stu-id="945fa-115">Indexes and Ranges require the new types <xref:System.Index?displayProperty=nameWithType> and <xref:System.Range?displayProperty=nameWithType>.</span></span>
- <span data-ttu-id="945fa-116">可为 null 的引用类型利用几个[特性](../nullable-attributes.md)来提供更准确的警告。</span><span class="sxs-lookup"><span data-stu-id="945fa-116">Nullable reference types make use of several [attributes](../nullable-attributes.md) to provide better warnings.</span></span> <span data-ttu-id="945fa-117">这些特性是在 .NET Core 3.0 中添加的。</span><span class="sxs-lookup"><span data-stu-id="945fa-117">Those attributes were added in .NET Core 3.0.</span></span> <span data-ttu-id="945fa-118">其他目标框架并未使用这些特性中的任何一种进行批注。</span><span class="sxs-lookup"><span data-stu-id="945fa-118">Other target frameworks haven't been annotated with any of these attributes.</span></span> <span data-ttu-id="945fa-119">这意味着可为 null 的警告可能无法准确反映潜在问题。</span><span class="sxs-lookup"><span data-stu-id="945fa-119">That means nullable warnings may not accurately reflect potential issues.</span></span>

## <a name="defaults"></a><span data-ttu-id="945fa-120">默认值</span><span class="sxs-lookup"><span data-stu-id="945fa-120">Defaults</span></span>

<span data-ttu-id="945fa-121">编译器根据以下规则确定默认值：</span><span class="sxs-lookup"><span data-stu-id="945fa-121">The compiler determines a default based on these rules:</span></span>

|<span data-ttu-id="945fa-122">目标框架</span><span class="sxs-lookup"><span data-stu-id="945fa-122">Target framework</span></span>|<span data-ttu-id="945fa-123">version</span><span class="sxs-lookup"><span data-stu-id="945fa-123">version</span></span>|<span data-ttu-id="945fa-124">C# 语言版本的默认值</span><span class="sxs-lookup"><span data-stu-id="945fa-124">C# language version default</span></span>|
|----------------|-------|---------------------------|
|<span data-ttu-id="945fa-125">.NET Core</span><span class="sxs-lookup"><span data-stu-id="945fa-125">.NET Core</span></span>|<span data-ttu-id="945fa-126">3.x</span><span class="sxs-lookup"><span data-stu-id="945fa-126">3.x</span></span>|<span data-ttu-id="945fa-127">C# 8.0</span><span class="sxs-lookup"><span data-stu-id="945fa-127">C# 8.0</span></span>|
|<span data-ttu-id="945fa-128">.NET Core</span><span class="sxs-lookup"><span data-stu-id="945fa-128">.NET Core</span></span>|<span data-ttu-id="945fa-129">2.x</span><span class="sxs-lookup"><span data-stu-id="945fa-129">2.x</span></span>|<span data-ttu-id="945fa-130">C# 7.3</span><span class="sxs-lookup"><span data-stu-id="945fa-130">C# 7.3</span></span>|
|<span data-ttu-id="945fa-131">.NET Standard</span><span class="sxs-lookup"><span data-stu-id="945fa-131">.NET Standard</span></span>|<span data-ttu-id="945fa-132">2.1</span><span class="sxs-lookup"><span data-stu-id="945fa-132">2.1</span></span>|<span data-ttu-id="945fa-133">C# 8.0</span><span class="sxs-lookup"><span data-stu-id="945fa-133">C# 8.0</span></span>|
|<span data-ttu-id="945fa-134">.NET Standard</span><span class="sxs-lookup"><span data-stu-id="945fa-134">.NET Standard</span></span>|<span data-ttu-id="945fa-135">2.0</span><span class="sxs-lookup"><span data-stu-id="945fa-135">2.0</span></span>|<span data-ttu-id="945fa-136">C# 7.3</span><span class="sxs-lookup"><span data-stu-id="945fa-136">C# 7.3</span></span>|
|<span data-ttu-id="945fa-137">.NET Standard</span><span class="sxs-lookup"><span data-stu-id="945fa-137">.NET Standard</span></span>|<span data-ttu-id="945fa-138">1.x</span><span class="sxs-lookup"><span data-stu-id="945fa-138">1.x</span></span>|<span data-ttu-id="945fa-139">C# 7.3</span><span class="sxs-lookup"><span data-stu-id="945fa-139">C# 7.3</span></span>|
|<span data-ttu-id="945fa-140">.NET Framework</span><span class="sxs-lookup"><span data-stu-id="945fa-140">.NET Framework</span></span>|<span data-ttu-id="945fa-141">全部</span><span class="sxs-lookup"><span data-stu-id="945fa-141">all</span></span>|<span data-ttu-id="945fa-142">C# 7.3</span><span class="sxs-lookup"><span data-stu-id="945fa-142">C# 7.3</span></span>|

<span data-ttu-id="945fa-143">如果你的项目是以具有相应预览语言版本的预览框架为目标，那么使用的语言版本是预览语言版本。</span><span class="sxs-lookup"><span data-stu-id="945fa-143">When your project targets a preview framework that has a corresponding preview language version, the language version used is the preview language version.</span></span> <span data-ttu-id="945fa-144">你可在任何环境中使用该预览版提供的最新功能，而不会影响面向已发布 .NET Core 版本的项目。</span><span class="sxs-lookup"><span data-stu-id="945fa-144">You use the latest features with that preview in any environment, without affecting projects that target a released .NET Core version.</span></span>

## <a name="override-a-default"></a><span data-ttu-id="945fa-145">替代默认值</span><span class="sxs-lookup"><span data-stu-id="945fa-145">Override a default</span></span>

<span data-ttu-id="945fa-146">如果必须明确指定 C# 版本，可以通过以下几种方式实现：</span><span class="sxs-lookup"><span data-stu-id="945fa-146">If you must specify your C# version explicitly, you can do so in several ways:</span></span>

- <span data-ttu-id="945fa-147">手动编辑[项目文件](#edit-the-project-file)。</span><span class="sxs-lookup"><span data-stu-id="945fa-147">Manually edit your [project file](#edit-the-project-file).</span></span>
- <span data-ttu-id="945fa-148">为[子目录中的多个项目](#configure-multiple-projects)设置语言版本。</span><span class="sxs-lookup"><span data-stu-id="945fa-148">Set the language version [for multiple projects in a subdirectory](#configure-multiple-projects).</span></span>
- <span data-ttu-id="945fa-149">配置 [`-langversion` 编译器选项](compiler-options/langversion-compiler-option.md)。</span><span class="sxs-lookup"><span data-stu-id="945fa-149">Configure the [`-langversion` compiler option](compiler-options/langversion-compiler-option.md).</span></span>

### <a name="edit-the-project-file"></a><span data-ttu-id="945fa-150">编辑项目文件</span><span class="sxs-lookup"><span data-stu-id="945fa-150">Edit the project file</span></span>

<span data-ttu-id="945fa-151">可在项目文件中设置语言版本。</span><span class="sxs-lookup"><span data-stu-id="945fa-151">You can set the language version in your project file.</span></span> <span data-ttu-id="945fa-152">例如，如果你明确希望访问预览功能，请添加如下元素：</span><span class="sxs-lookup"><span data-stu-id="945fa-152">For example, if you explicitly want access to preview features, add an element like this:</span></span>

```xml
<PropertyGroup>
   <LangVersion>preview</LangVersion>
</PropertyGroup>
```

<span data-ttu-id="945fa-153">值 `preview` 使用编译器支持的最新可用的预览 C# 语言版本。</span><span class="sxs-lookup"><span data-stu-id="945fa-153">The value `preview` uses the latest available preview C# language version that your compiler supports.</span></span>

### <a name="configure-multiple-projects"></a><span data-ttu-id="945fa-154">配置多个项目</span><span class="sxs-lookup"><span data-stu-id="945fa-154">Configure multiple projects</span></span>

<span data-ttu-id="945fa-155">若要配置多个目录，可以创建包含 `<LangVersion>` 元素的 Directory.Build.props  文件。</span><span class="sxs-lookup"><span data-stu-id="945fa-155">To configure multiple projects, you can create a **Directory.Build.props** file that contains the `<LangVersion>` element.</span></span> <span data-ttu-id="945fa-156">通常是在解决方案目录中完成这件事。</span><span class="sxs-lookup"><span data-stu-id="945fa-156">You typically do that in your solution directory.</span></span> <span data-ttu-id="945fa-157">将以下内容添加到解决方案目录中的 Directory.Build.props  文件：</span><span class="sxs-lookup"><span data-stu-id="945fa-157">Add the following to a **Directory.Build.props** file in your solution directory:</span></span>

```xml
<Project>
 <PropertyGroup>
   <LangVersion>preview</LangVersion>
 </PropertyGroup>
</Project>
```

<span data-ttu-id="945fa-158">包含该文件的目录的所有子目录中的版本都将使用 C# 预览版。</span><span class="sxs-lookup"><span data-stu-id="945fa-158">Builds in all subdirectories of the directory containing that file will use the preview C# version.</span></span> <span data-ttu-id="945fa-159">有关详细信息，请参阅关于[自定义生成](/visualstudio/msbuild/customize-your-build)的文章。</span><span class="sxs-lookup"><span data-stu-id="945fa-159">For more information, see the article on [Customize your build](/visualstudio/msbuild/customize-your-build).</span></span>

## <a name="c-language-version-reference"></a><span data-ttu-id="945fa-160">C# 语言版本引用</span><span class="sxs-lookup"><span data-stu-id="945fa-160">C# language version reference</span></span>

<span data-ttu-id="945fa-161">下表显示当前所有 C# 语言版本。</span><span class="sxs-lookup"><span data-stu-id="945fa-161">The following table shows all current C# language versions.</span></span> <span data-ttu-id="945fa-162">如果编译器较旧，它可能不一定能识别每个值。</span><span class="sxs-lookup"><span data-stu-id="945fa-162">Your compiler may not necessarily understand every value if it's older.</span></span> <span data-ttu-id="945fa-163">如果安装的是 .NET Core 3.0 或更高版本，则可以访问列出的所有内容。</span><span class="sxs-lookup"><span data-stu-id="945fa-163">If you install .NET Core 3.0 or later, then you have access to everything listed.</span></span>

|<span data-ttu-id="945fa-164">“值”</span><span class="sxs-lookup"><span data-stu-id="945fa-164">Value</span></span>|<span data-ttu-id="945fa-165">含义</span><span class="sxs-lookup"><span data-stu-id="945fa-165">Meaning</span></span>|
|------------|-------------|
|<span data-ttu-id="945fa-166">preview</span><span class="sxs-lookup"><span data-stu-id="945fa-166">preview</span></span>|<span data-ttu-id="945fa-167">编译器接受最新预览版中的所有有效语言语法。</span><span class="sxs-lookup"><span data-stu-id="945fa-167">The compiler accepts all valid language syntax from the latest preview version.</span></span>|
|<span data-ttu-id="945fa-168">latest</span><span class="sxs-lookup"><span data-stu-id="945fa-168">latest</span></span>|<span data-ttu-id="945fa-169">编译器接受最新发布的编译器版本（包括次要版本）中的语法。</span><span class="sxs-lookup"><span data-stu-id="945fa-169">The compiler accepts syntax from the latest released version of the compiler (including minor version).</span></span>|
|<span data-ttu-id="945fa-170">latestMajor</span><span class="sxs-lookup"><span data-stu-id="945fa-170">latestMajor</span></span>|<span data-ttu-id="945fa-171">编译器接受最新发布的编译器主要版本中的语法。</span><span class="sxs-lookup"><span data-stu-id="945fa-171">The compiler accepts syntax from the latest released major version of the compiler.</span></span>|
|<span data-ttu-id="945fa-172">8.0</span><span class="sxs-lookup"><span data-stu-id="945fa-172">8.0</span></span>|<span data-ttu-id="945fa-173">编译器只接受 C# 8.0 或更低版本中所含的语法。</span><span class="sxs-lookup"><span data-stu-id="945fa-173">The compiler accepts only syntax that is included in C# 8.0 or lower.</span></span>|
|<span data-ttu-id="945fa-174">7.3</span><span class="sxs-lookup"><span data-stu-id="945fa-174">7.3</span></span>|<span data-ttu-id="945fa-175">编译器只接受 C# 7.3 或更低版本中所含的语法。</span><span class="sxs-lookup"><span data-stu-id="945fa-175">The compiler accepts only syntax that is included in C# 7.3 or lower.</span></span>|
|<span data-ttu-id="945fa-176">7.2</span><span class="sxs-lookup"><span data-stu-id="945fa-176">7.2</span></span>|<span data-ttu-id="945fa-177">编译器只接受 C# 7.2 或更低版本中所含的语法。</span><span class="sxs-lookup"><span data-stu-id="945fa-177">The compiler accepts only syntax that is included in C# 7.2 or lower.</span></span>|
|<span data-ttu-id="945fa-178">7.1</span><span class="sxs-lookup"><span data-stu-id="945fa-178">7.1</span></span>|<span data-ttu-id="945fa-179">编译器只接受 C# 7.1 或更低版本中所含的语法。</span><span class="sxs-lookup"><span data-stu-id="945fa-179">The compiler accepts only syntax that is included in C# 7.1 or lower.</span></span>|
|<span data-ttu-id="945fa-180">7</span><span class="sxs-lookup"><span data-stu-id="945fa-180">7</span></span>|<span data-ttu-id="945fa-181">编译器只接受 C# 7.0 或更低版本中所含的语法。</span><span class="sxs-lookup"><span data-stu-id="945fa-181">The compiler accepts only syntax that is included in C# 7.0 or lower.</span></span>|
|<span data-ttu-id="945fa-182">6</span><span class="sxs-lookup"><span data-stu-id="945fa-182">6</span></span>|<span data-ttu-id="945fa-183">编译器只接受 C# 6.0 或更低版本中所含的语法。</span><span class="sxs-lookup"><span data-stu-id="945fa-183">The compiler accepts only syntax that is included in C# 6.0 or lower.</span></span>|
|<span data-ttu-id="945fa-184">5</span><span class="sxs-lookup"><span data-stu-id="945fa-184">5</span></span>|<span data-ttu-id="945fa-185">编译器只接受 C# 5.0 或更低版本中所含的语法。</span><span class="sxs-lookup"><span data-stu-id="945fa-185">The compiler accepts only syntax that is included in C# 5.0 or lower.</span></span>|
|<span data-ttu-id="945fa-186">4</span><span class="sxs-lookup"><span data-stu-id="945fa-186">4</span></span>|<span data-ttu-id="945fa-187">编译器只接受 C# 4.0 或更低版本中所含的语法。</span><span class="sxs-lookup"><span data-stu-id="945fa-187">The compiler accepts only syntax that is included in C# 4.0 or lower.</span></span>|
|<span data-ttu-id="945fa-188">3</span><span class="sxs-lookup"><span data-stu-id="945fa-188">3</span></span>|<span data-ttu-id="945fa-189">编译器只接受 C# 3.0 或更低版本中所含的语法。</span><span class="sxs-lookup"><span data-stu-id="945fa-189">The compiler accepts only syntax that is included in C# 3.0 or lower.</span></span>|
|<span data-ttu-id="945fa-190">ISO-2</span><span class="sxs-lookup"><span data-stu-id="945fa-190">ISO-2</span></span>|<span data-ttu-id="945fa-191">编译器只接受 ISO/IEC 23270:2006 C# (2.0) 中所含的语法。</span><span class="sxs-lookup"><span data-stu-id="945fa-191">The compiler accepts only syntax that is included in ISO/IEC 23270:2006 C# (2.0).</span></span> |
|<span data-ttu-id="945fa-192">ISO-1</span><span class="sxs-lookup"><span data-stu-id="945fa-192">ISO-1</span></span>|<span data-ttu-id="945fa-193">编译器只接受 ISO/IEC 23270:2003 C# (1.0/1.2) 中所含的语法。</span><span class="sxs-lookup"><span data-stu-id="945fa-193">The compiler accepts only syntax that is included in ISO/IEC 23270:2003 C# (1.0/1.2).</span></span> |
