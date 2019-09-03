---
title: C# 语言版本控制 - C# 指南
description: 了解如何根据项目确定 C# 语言版本，以及可以手动调整的不同值。
ms.date: 07/10/2019
ms.openlocfilehash: fae36f5305e23fbfa1c55c5881e37391670f93ab
ms.sourcegitcommit: 581ab03291e91983459e56e40ea8d97b5189227e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/27/2019
ms.locfileid: "70040354"
---
# <a name="c-language-versioning"></a><span data-ttu-id="3e431-103">C# 语言版本控制</span><span class="sxs-lookup"><span data-stu-id="3e431-103">C# language versioning</span></span>

<span data-ttu-id="3e431-104">最新的 C# 编译器根据项目的一个或多个目标框架确定默认语言版本。</span><span class="sxs-lookup"><span data-stu-id="3e431-104">The latest C# compiler determines a default language version based on your project's target framework or frameworks.</span></span> <span data-ttu-id="3e431-105">这是因为 C# 语言可能具有依赖于每个 .NET 实现中不提供的类型或运行时组件的功能。</span><span class="sxs-lookup"><span data-stu-id="3e431-105">This is because the C# language may have features that rely on types or runtime components that are not available in every .NET implementation.</span></span> <span data-ttu-id="3e431-106">这也确保了无论根据哪种目标构建项目，默认情况下你都将获得最兼容的语言版本。</span><span class="sxs-lookup"><span data-stu-id="3e431-106">This also ensures that for whatever target your project is built against, you get the highest compatible language version by default.</span></span>

<span data-ttu-id="3e431-107">本文中的规则适用于随 Visual Studio 2019 或 .NET Core 3.0 SDK 一起提供的编译器。</span><span class="sxs-lookup"><span data-stu-id="3e431-107">The rules in this article apply to the compiler delivered with Visual Studio 2019, or the .NET Core 3.0 SDK.</span></span> <span data-ttu-id="3e431-108">默认情况下，Visual Studio 2017 安装或早期 .NET Core SDK 版本中包含的 C# 编译器以 C# 7.0 为目标。</span><span class="sxs-lookup"><span data-stu-id="3e431-108">The C# compilers that are part of the Visual Studio 2017 installation or earlier .NET Core SDK versions target C# 7.0 by default.</span></span> 

## <a name="defaults"></a><span data-ttu-id="3e431-109">默认值</span><span class="sxs-lookup"><span data-stu-id="3e431-109">Defaults</span></span>

<span data-ttu-id="3e431-110">编译器根据以下规则确定默认值：</span><span class="sxs-lookup"><span data-stu-id="3e431-110">The compiler determines a default based on these rules:</span></span>

|<span data-ttu-id="3e431-111">目标框架</span><span class="sxs-lookup"><span data-stu-id="3e431-111">Target framework</span></span>|<span data-ttu-id="3e431-112">version</span><span class="sxs-lookup"><span data-stu-id="3e431-112">version</span></span>|<span data-ttu-id="3e431-113">C# 语言版本的默认值</span><span class="sxs-lookup"><span data-stu-id="3e431-113">C# language version default</span></span>|
|----------------|-------|---------------------------|
|<span data-ttu-id="3e431-114">.NET Core</span><span class="sxs-lookup"><span data-stu-id="3e431-114">.NET Core</span></span>|<span data-ttu-id="3e431-115">3.x</span><span class="sxs-lookup"><span data-stu-id="3e431-115">3.x</span></span>|<span data-ttu-id="3e431-116">C# 8.0</span><span class="sxs-lookup"><span data-stu-id="3e431-116">C# 8.0</span></span>|
|<span data-ttu-id="3e431-117">.NET Core</span><span class="sxs-lookup"><span data-stu-id="3e431-117">.NET Core</span></span>|<span data-ttu-id="3e431-118">2.x</span><span class="sxs-lookup"><span data-stu-id="3e431-118">2.x</span></span>|<span data-ttu-id="3e431-119">C# 7.3</span><span class="sxs-lookup"><span data-stu-id="3e431-119">C# 7.3</span></span>|
|<span data-ttu-id="3e431-120">.NET Standard</span><span class="sxs-lookup"><span data-stu-id="3e431-120">.NET Standard</span></span>|<span data-ttu-id="3e431-121">全部</span><span class="sxs-lookup"><span data-stu-id="3e431-121">all</span></span>|<span data-ttu-id="3e431-122">C# 7.3</span><span class="sxs-lookup"><span data-stu-id="3e431-122">C# 7.3</span></span>|
|<span data-ttu-id="3e431-123">.NET Framework</span><span class="sxs-lookup"><span data-stu-id="3e431-123">.NET Framework</span></span>|<span data-ttu-id="3e431-124">全部</span><span class="sxs-lookup"><span data-stu-id="3e431-124">all</span></span>|<span data-ttu-id="3e431-125">C# 7.3</span><span class="sxs-lookup"><span data-stu-id="3e431-125">C# 7.3</span></span>|

## <a name="default-for-previews"></a><span data-ttu-id="3e431-126">默认值适用于预览版</span><span class="sxs-lookup"><span data-stu-id="3e431-126">Default for previews</span></span>

<span data-ttu-id="3e431-127">如果你的项目是以具有相应预览语言版本的预览框架为目标，那么使用的语言版本是预览语言版本。</span><span class="sxs-lookup"><span data-stu-id="3e431-127">When your project targets a preview framework that has a corresponding preview language version, the language version used is the preview language version.</span></span> <span data-ttu-id="3e431-128">这可确保你可以使用保证在任何环境中都可用的预览提供的最新功能，而不会影响面向发布的 .NET Core 版本的项目。</span><span class="sxs-lookup"><span data-stu-id="3e431-128">This ensures that you can use the latest features that are guaranteed to work with that preview in any environment without affecting your projects that target a released .NET Core version.</span></span>

## <a name="override-a-default"></a><span data-ttu-id="3e431-129">替代默认值</span><span class="sxs-lookup"><span data-stu-id="3e431-129">Override a default</span></span>

<span data-ttu-id="3e431-130">如果必须明确指定 C# 版本，可以通过以下几种方式实现：</span><span class="sxs-lookup"><span data-stu-id="3e431-130">If you must specify your C# version explicitly, you can do so in several ways:</span></span>

- <span data-ttu-id="3e431-131">手动编辑[项目文件](#edit-the-project-file)。</span><span class="sxs-lookup"><span data-stu-id="3e431-131">Manually edit your [project file](#edit-the-project-file).</span></span>
- <span data-ttu-id="3e431-132">为[子目录中的多个项目](#configure-multiple-projects)设置语言版本。</span><span class="sxs-lookup"><span data-stu-id="3e431-132">Set the language version [for multiple projects in a subdirectory](#configure-multiple-projects).</span></span>
- <span data-ttu-id="3e431-133">配置 [`-langversion` 编译器选项](compiler-options/langversion-compiler-option.md)</span><span class="sxs-lookup"><span data-stu-id="3e431-133">Configure the [`-langversion` compiler option](compiler-options/langversion-compiler-option.md)</span></span>

### <a name="edit-the-project-file"></a><span data-ttu-id="3e431-134">编辑项目文件</span><span class="sxs-lookup"><span data-stu-id="3e431-134">Edit the project file</span></span>

<span data-ttu-id="3e431-135">可在项目文件中设置语言版本。</span><span class="sxs-lookup"><span data-stu-id="3e431-135">You can set the language version in your project file.</span></span> <span data-ttu-id="3e431-136">例如，如果你明确希望访问预览功能，请添加如下元素：</span><span class="sxs-lookup"><span data-stu-id="3e431-136">For example, if you explicitly want access to preview features, add an element like this:</span></span>

```xml
<PropertyGroup>
   <LangVersion>preview</LangVersion>
</PropertyGroup>
```

<span data-ttu-id="3e431-137">值 `preview` 使用编译器支持的最新可用的预览 C# 语言版本。</span><span class="sxs-lookup"><span data-stu-id="3e431-137">The value `preview` uses the latest available preview C# language version that your compiler supports.</span></span>

### <a name="configure-multiple-projects"></a><span data-ttu-id="3e431-138">配置多个项目</span><span class="sxs-lookup"><span data-stu-id="3e431-138">Configure multiple projects</span></span>

<span data-ttu-id="3e431-139">可以创建包含 `<LangVersion>` 元素的 Directory.Build.props  文件来配置多个目录。</span><span class="sxs-lookup"><span data-stu-id="3e431-139">You can create a **Directory.Build.props** file that contains the `<LangVersion>` element to configure multiple directories.</span></span> <span data-ttu-id="3e431-140">通常是在解决方案目录中完成这件事。</span><span class="sxs-lookup"><span data-stu-id="3e431-140">You typically do that in your solution directory.</span></span> <span data-ttu-id="3e431-141">将以下内容添加到解决方案目录中的 Directory.Build.props  文件：</span><span class="sxs-lookup"><span data-stu-id="3e431-141">Add the following to a **Directory.Build.props** file in your solution directory:</span></span>

```xml
<Project>
 <PropertyGroup>
   <LangVersion>preview</LangVersion>
 </PropertyGroup>
</Project>
```

<span data-ttu-id="3e431-142">现在，包含该文件的目录的每个子目录中的版本都将使用 C# 预览版。</span><span class="sxs-lookup"><span data-stu-id="3e431-142">Now, builds in every subdirectory of the directory containing that file will use the preview C# version.</span></span> <span data-ttu-id="3e431-143">有关详细信息，请参阅关于[自定义生成](/visualstudio/msbuild/customize-your-build)的文章。</span><span class="sxs-lookup"><span data-stu-id="3e431-143">For more information, see the article on [Customize your build](/visualstudio/msbuild/customize-your-build).</span></span>

## <a name="c-language-version-reference"></a><span data-ttu-id="3e431-144">C# 语言版本引用</span><span class="sxs-lookup"><span data-stu-id="3e431-144">C# language version reference</span></span>

<span data-ttu-id="3e431-145">下表显示当前所有 C# 语言版本。</span><span class="sxs-lookup"><span data-stu-id="3e431-145">The following table shows all current C# language versions.</span></span> <span data-ttu-id="3e431-146">如果编译器较旧，它可能不一定了解每个值。</span><span class="sxs-lookup"><span data-stu-id="3e431-146">Your compiler may not necessarily understand every value if it is older.</span></span> <span data-ttu-id="3e431-147">如果安装的是 .NET Core 3.0，则你可以访问列出的所有内容。</span><span class="sxs-lookup"><span data-stu-id="3e431-147">If you install .NET Core 3.0, then you will have access to everything listed.</span></span>

|<span data-ttu-id="3e431-148">值</span><span class="sxs-lookup"><span data-stu-id="3e431-148">Value</span></span>|<span data-ttu-id="3e431-149">含义</span><span class="sxs-lookup"><span data-stu-id="3e431-149">Meaning</span></span>|
|------------|-------------|
|<span data-ttu-id="3e431-150">preview</span><span class="sxs-lookup"><span data-stu-id="3e431-150">preview</span></span>|<span data-ttu-id="3e431-151">编译器接受最新预览版中的所有有效语言语法。</span><span class="sxs-lookup"><span data-stu-id="3e431-151">The compiler accepts all valid language syntax from the latest preview version.</span></span>|
|<span data-ttu-id="3e431-152">最新</span><span class="sxs-lookup"><span data-stu-id="3e431-152">latest</span></span>|<span data-ttu-id="3e431-153">编译器接受最新发布的编译器版本（包括次要版本）中的语法。</span><span class="sxs-lookup"><span data-stu-id="3e431-153">The compiler accepts syntax from the latest released version of the compiler (including minor version).</span></span>|
|<span data-ttu-id="3e431-154">latestMajor</span><span class="sxs-lookup"><span data-stu-id="3e431-154">latestMajor</span></span>|<span data-ttu-id="3e431-155">编译器接受最新发布的编译器主要版本中的语法。</span><span class="sxs-lookup"><span data-stu-id="3e431-155">The compiler accepts syntax from the latest released major version of the compiler.</span></span>|
|<span data-ttu-id="3e431-156">8.0</span><span class="sxs-lookup"><span data-stu-id="3e431-156">8.0</span></span>|<span data-ttu-id="3e431-157">编译器只接受 C# 8.0 或更低版本中所含的语法。</span><span class="sxs-lookup"><span data-stu-id="3e431-157">The compiler accepts only syntax that is included in C# 8.0 or lower.</span></span>|
|<span data-ttu-id="3e431-158">7.3</span><span class="sxs-lookup"><span data-stu-id="3e431-158">7.3</span></span>|<span data-ttu-id="3e431-159">编译器只接受 C# 7.3 或更低版本中所含的语法。</span><span class="sxs-lookup"><span data-stu-id="3e431-159">The compiler accepts only syntax that is included in C# 7.3 or lower.</span></span>|
|<span data-ttu-id="3e431-160">7.2</span><span class="sxs-lookup"><span data-stu-id="3e431-160">7.2</span></span>|<span data-ttu-id="3e431-161">编译器只接受 C# 7.2 或更低版本中所含的语法。</span><span class="sxs-lookup"><span data-stu-id="3e431-161">The compiler accepts only syntax that is included in C# 7.2 or lower.</span></span>|
|<span data-ttu-id="3e431-162">7.1</span><span class="sxs-lookup"><span data-stu-id="3e431-162">7.1</span></span>|<span data-ttu-id="3e431-163">编译器只接受 C# 7.1 或更低版本中所含的语法。</span><span class="sxs-lookup"><span data-stu-id="3e431-163">The compiler accepts only syntax that is included in C# 7.1 or lower.</span></span>|
|<span data-ttu-id="3e431-164">7</span><span class="sxs-lookup"><span data-stu-id="3e431-164">7</span></span>|<span data-ttu-id="3e431-165">编译器只接受 C# 7.0 或更低版本中所含的语法。</span><span class="sxs-lookup"><span data-stu-id="3e431-165">The compiler accepts only syntax that is included in C# 7.0 or lower.</span></span>|
|<span data-ttu-id="3e431-166">6</span><span class="sxs-lookup"><span data-stu-id="3e431-166">6</span></span>|<span data-ttu-id="3e431-167">编译器只接受 C# 6.0 或更低版本中所含的语法。</span><span class="sxs-lookup"><span data-stu-id="3e431-167">The compiler accepts only syntax that is included in C# 6.0 or lower.</span></span>|
|<span data-ttu-id="3e431-168">5</span><span class="sxs-lookup"><span data-stu-id="3e431-168">5</span></span>|<span data-ttu-id="3e431-169">编译器只接受 C# 5.0 或更低版本中所含的语法。</span><span class="sxs-lookup"><span data-stu-id="3e431-169">The compiler accepts only syntax that is included in C# 5.0 or lower.</span></span>|
|<span data-ttu-id="3e431-170">4</span><span class="sxs-lookup"><span data-stu-id="3e431-170">4</span></span>|<span data-ttu-id="3e431-171">编译器只接受 C# 4.0 或更低版本中所含的语法。</span><span class="sxs-lookup"><span data-stu-id="3e431-171">The compiler accepts only syntax that is included in C# 4.0 or lower.</span></span>|
|<span data-ttu-id="3e431-172">3</span><span class="sxs-lookup"><span data-stu-id="3e431-172">3</span></span>|<span data-ttu-id="3e431-173">编译器只接受 C# 3.0 或更低版本中所含的语法。</span><span class="sxs-lookup"><span data-stu-id="3e431-173">The compiler accepts only syntax that is included in C# 3.0 or lower.</span></span>|
|<span data-ttu-id="3e431-174">ISO-2</span><span class="sxs-lookup"><span data-stu-id="3e431-174">ISO-2</span></span>|<span data-ttu-id="3e431-175">编译器只接受 ISO/IEC 23270:2006 C# (2.0) 中所含的语法</span><span class="sxs-lookup"><span data-stu-id="3e431-175">The compiler accepts only syntax that is included in ISO/IEC 23270:2006 C# (2.0)</span></span> |
|<span data-ttu-id="3e431-176">ISO-1</span><span class="sxs-lookup"><span data-stu-id="3e431-176">ISO-1</span></span>|<span data-ttu-id="3e431-177">编译器只接受 ISO/IEC 23270:2003 C# (1.0/1.2) 中所含的语法</span><span class="sxs-lookup"><span data-stu-id="3e431-177">The compiler accepts only syntax that is included in ISO/IEC 23270:2003 C# (1.0/1.2)</span></span> |
