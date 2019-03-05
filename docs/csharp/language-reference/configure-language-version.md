---
title: 选择 C# 语言版本 - C# 指南
description: 配置编译器以使用特定的编译器版本执行语法验证
ms.date: 02/28/2019
ms.openlocfilehash: 6d31a757171bd2eecdcc1fbd3da765dcb3fe45c0
ms.sourcegitcommit: 79066169e93d9d65203028b21983574ad9dcf6b4
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/01/2019
ms.locfileid: "57212022"
---
# <a name="select-the-c-language-version"></a><span data-ttu-id="e0f7d-103">选择 C# 语言版本</span><span class="sxs-lookup"><span data-stu-id="e0f7d-103">Select the C# language version</span></span>

<span data-ttu-id="e0f7d-104">C# 编译器根据项目的一个或多个目标框架确定默认语言版本。</span><span class="sxs-lookup"><span data-stu-id="e0f7d-104">The C# compiler determines a default language version based on your project's target framework or frameworks.</span></span> <span data-ttu-id="e0f7d-105">如果你的项目是以具有相应预览语言版本的预览框架为目标，那么使用的语言版本是预览语言版本。</span><span class="sxs-lookup"><span data-stu-id="e0f7d-105">When your project targets a preview framework that has a corresponding preview language version, the language version used is the preview language version.</span></span> <span data-ttu-id="e0f7d-106">如果你的项目不以预览框架为目标，则使用的语言版本是最新的次要版本。</span><span class="sxs-lookup"><span data-stu-id="e0f7d-106">When your project doesn't target a preview framework, the language version used is the latest minor version.</span></span>

<span data-ttu-id="e0f7d-107">例如，在 .NET Core 3.0 的预览版期间，任何以 `netcoreapp3.0` 或 `netstandard2.1` 为目标的项目（均为预览版）都将使用 C# 8.0 语言（同样为预览版）。</span><span class="sxs-lookup"><span data-stu-id="e0f7d-107">For example, during the preview period for .NET Core 3.0, any project that targets `netcoreapp3.0` or `netstandard2.1` (both in preview) will use the C# 8.0 language (also in preview).</span></span> <span data-ttu-id="e0f7d-108">以任何已发布版本为目标的项目将使用 C# 7.3（最新发布的版本）。</span><span class="sxs-lookup"><span data-stu-id="e0f7d-108">Projects targeting any released version will use C# 7.3 (the latest released version).</span></span> <span data-ttu-id="e0f7d-109">此行为意味着任何以 .NET Framework 为目标的项目都将使用最新版本 (C# 7.3)。</span><span class="sxs-lookup"><span data-stu-id="e0f7d-109">This behavior means that any project targeting .NET Framework will use latest (C# 7.3).</span></span> 

<span data-ttu-id="e0f7d-110">借助此功能，在开发环境中安装新版本的 SDK 和工具时，不必选择在项目中引入新的语言功能。</span><span class="sxs-lookup"><span data-stu-id="e0f7d-110">This capability decouples the decision to install new versions of the SDK and tools in your development environment from the decision to incorporate new language features in a project.</span></span> <span data-ttu-id="e0f7d-111">可以在生成计算机上安装最新的 SDK 和工具。</span><span class="sxs-lookup"><span data-stu-id="e0f7d-111">You can install the latest SDK and tools on your build machine.</span></span> <span data-ttu-id="e0f7d-112">每个项目可以配置为对其生成使用该语言的特定版本。</span><span class="sxs-lookup"><span data-stu-id="e0f7d-112">Each project can be configured to use a specific version of the language for its build.</span></span> <span data-ttu-id="e0f7d-113">默认行为意味着只有在项目以这些框架为目标时，才会启用依赖于新类型或新 CLR 行为的任何语言功能。</span><span class="sxs-lookup"><span data-stu-id="e0f7d-113">The default behavior means that any language features that rely on new types or new CLR behavior are enabled only when projects target those frameworks.</span></span>

<span data-ttu-id="e0f7d-114">可以通过指定语言版本来覆盖默认行为。</span><span class="sxs-lookup"><span data-stu-id="e0f7d-114">You can override the default behavior by specifying a language version.</span></span> <span data-ttu-id="e0f7d-115">有几种方法可以设置语言版本：</span><span class="sxs-lookup"><span data-stu-id="e0f7d-115">There are several ways to set the language version:</span></span>

- <span data-ttu-id="e0f7d-116">依靠 [Visual Studio 快速操作](#visual-studio-quick-action)。</span><span class="sxs-lookup"><span data-stu-id="e0f7d-116">Rely on a [Visual Studio quick action](#visual-studio-quick-action).</span></span>
- <span data-ttu-id="e0f7d-117">在 [Visual Studio UI](#set-the-language-version-in-visual-studio) 中设置语言版本。</span><span class="sxs-lookup"><span data-stu-id="e0f7d-117">Set the language version in the [Visual Studio UI](#set-the-language-version-in-visual-studio).</span></span>
- <span data-ttu-id="e0f7d-118">手动编辑 [.csproj 文件](#edit-the-csproj-file)。</span><span class="sxs-lookup"><span data-stu-id="e0f7d-118">Manually edit your [**.csproj** file](#edit-the-csproj-file).</span></span>
- <span data-ttu-id="e0f7d-119">为[子目录中的多个项目](#configure-multiple-projects)设置语言版本。</span><span class="sxs-lookup"><span data-stu-id="e0f7d-119">Set the language version [for multiple projects in a subdirectory](#configure-multiple-projects).</span></span>
- <span data-ttu-id="e0f7d-120">配置 [`-langversion` 编译器选项](#set-the-langversion-compiler-option)。</span><span class="sxs-lookup"><span data-stu-id="e0f7d-120">Configure the [`-langversion` compiler option](#set-the-langversion-compiler-option).</span></span>

## <a name="visual-studio-quick-action"></a><span data-ttu-id="e0f7d-121">Visual Studio 快速操作</span><span class="sxs-lookup"><span data-stu-id="e0f7d-121">Visual Studio quick action</span></span>

<span data-ttu-id="e0f7d-122">Visual Studio 可帮助你确定需要的语言版本。</span><span class="sxs-lookup"><span data-stu-id="e0f7d-122">Visual Studio helps you determine the language version you need.</span></span> <span data-ttu-id="e0f7d-123">如果你使用的语言功能不适合当前配置的版本，Visual Studio 会显示一项潜在修复来为项目更新语言版本。</span><span class="sxs-lookup"><span data-stu-id="e0f7d-123">If you use a language feature that is not available for the currently configured version, Visual Studio shows a potential fix to update the language version for the project.</span></span>

## <a name="set-the-language-version-in-visual-studio"></a><span data-ttu-id="e0f7d-124">在 Visual Studio 中设置语言版本</span><span class="sxs-lookup"><span data-stu-id="e0f7d-124">Set the language version in Visual Studio</span></span>

<span data-ttu-id="e0f7d-125">可以在 Visual Studio 中设置该版本。</span><span class="sxs-lookup"><span data-stu-id="e0f7d-125">You can set the version in Visual Studio.</span></span> <span data-ttu-id="e0f7d-126">右键单击“解决方案资源管理器”中的项目节点，然后选择“属性”。</span><span class="sxs-lookup"><span data-stu-id="e0f7d-126">Right-click on the project node in Solution Explorer and select **Properties**.</span></span> <span data-ttu-id="e0f7d-127">选择**生成**选项卡并选择**高级**按钮。</span><span class="sxs-lookup"><span data-stu-id="e0f7d-127">Select the **Build** tab and select the **Advanced** button.</span></span> <span data-ttu-id="e0f7d-128">在下拉列表中，选择版本。</span><span class="sxs-lookup"><span data-stu-id="e0f7d-128">In the dropdown, select the version.</span></span> <span data-ttu-id="e0f7d-129">下图显示“最新”设置：</span><span class="sxs-lookup"><span data-stu-id="e0f7d-129">The following image shows the "latest" setting:</span></span>

![高级生成设置的屏幕截图，在这里可以指定语言版本](./media/configure-language-version/advanced-build-settings.png)

> [!NOTE]
> <span data-ttu-id="e0f7d-131">如果使用 Visual Studio IDE 来更新 csproj 文件，IDE 将为每个生成配置创建单独的节点。</span><span class="sxs-lookup"><span data-stu-id="e0f7d-131">If you use the Visual Studio IDE to update your csproj files, the IDE creates separate nodes for each build configuration.</span></span> <span data-ttu-id="e0f7d-132">通常在所有生成配置中都设置相同的值，但你需要为每个生成配置显式地设置值，或在修改此设置时选择"所有配置"。</span><span class="sxs-lookup"><span data-stu-id="e0f7d-132">You'll typically set the value the same in all build configurations, but you need to set it explicitly for each build configuration, or select "All Configurations" when you modify this setting.</span></span> <span data-ttu-id="e0f7d-133">在 csproj 文件中，你可以看到如下内容：</span><span class="sxs-lookup"><span data-stu-id="e0f7d-133">You'll see the following in your csproj file:</span></span>
>
>```xml
> <PropertyGroup Condition="'$(Configuration)|$(Platform)'=='Release|AnyCPU'">
>  <LangVersion>latest</LangVersion>
></PropertyGroup>
>
> <PropertyGroup Condition="'$(Configuration)|$(Platform)'=='Debug|AnyCPU'">
>  <LangVersion>latest</LangVersion>
> </PropertyGroup>
> ```
>

## <a name="edit-the-csproj-file"></a><span data-ttu-id="e0f7d-134">编辑 csproj 文件</span><span class="sxs-lookup"><span data-stu-id="e0f7d-134">Edit the csproj file</span></span>

<span data-ttu-id="e0f7d-135">可在 .csproj 文件中设置语言版本。</span><span class="sxs-lookup"><span data-stu-id="e0f7d-135">You can set the language version in your **.csproj** file.</span></span> <span data-ttu-id="e0f7d-136">添加如下元素：</span><span class="sxs-lookup"><span data-stu-id="e0f7d-136">Add an element like the following:</span></span>

```xml
<PropertyGroup>
   <LangVersion>latest</LangVersion>
</PropertyGroup>
```

<span data-ttu-id="e0f7d-137">`latest` 值使用 C# 语言的最新次要版本。</span><span class="sxs-lookup"><span data-stu-id="e0f7d-137">The value `latest` uses the latest minor version of the C# language.</span></span> <span data-ttu-id="e0f7d-138">有效值为：</span><span class="sxs-lookup"><span data-stu-id="e0f7d-138">Valid values are:</span></span>

|<span data-ttu-id="e0f7d-139">值</span><span class="sxs-lookup"><span data-stu-id="e0f7d-139">Value</span></span>|<span data-ttu-id="e0f7d-140">含义</span><span class="sxs-lookup"><span data-stu-id="e0f7d-140">Meaning</span></span>|
|------------|-------------|
|<span data-ttu-id="e0f7d-141">preview</span><span class="sxs-lookup"><span data-stu-id="e0f7d-141">preview</span></span>|<span data-ttu-id="e0f7d-142">编译器接受最新预览版中的所有有效语言语法。</span><span class="sxs-lookup"><span data-stu-id="e0f7d-142">The compiler accepts all valid language syntax from the latest preview version.</span></span>|
|<span data-ttu-id="e0f7d-143">最新</span><span class="sxs-lookup"><span data-stu-id="e0f7d-143">latest</span></span>|<span data-ttu-id="e0f7d-144">编译器接受最新发布的编译器版本（包括次要版本）中的语法。</span><span class="sxs-lookup"><span data-stu-id="e0f7d-144">The compiler accepts syntax from the latest released version of the compiler (including minor version).</span></span>|
|<span data-ttu-id="e0f7d-145">latestMajor</span><span class="sxs-lookup"><span data-stu-id="e0f7d-145">latestMajor</span></span>|<span data-ttu-id="e0f7d-146">编译器接受最新发布的编译器主要版本中的语法。</span><span class="sxs-lookup"><span data-stu-id="e0f7d-146">The compiler accepts syntax from the latest released major version of the compiler.</span></span>|
|<span data-ttu-id="e0f7d-147">8.0</span><span class="sxs-lookup"><span data-stu-id="e0f7d-147">8.0</span></span>|<span data-ttu-id="e0f7d-148">编译器只接受 C# 8.0 或更低版本中所含的语法。</span><span class="sxs-lookup"><span data-stu-id="e0f7d-148">The compiler accepts only syntax that is included in C# 8.0 or lower.</span></span>|
|<span data-ttu-id="e0f7d-149">7.3</span><span class="sxs-lookup"><span data-stu-id="e0f7d-149">7.3</span></span>|<span data-ttu-id="e0f7d-150">编译器只接受 C# 7.3 或更低版本中所含的语法。</span><span class="sxs-lookup"><span data-stu-id="e0f7d-150">The compiler accepts only syntax that is included in C# 7.3 or lower.</span></span>|
|<span data-ttu-id="e0f7d-151">7.2</span><span class="sxs-lookup"><span data-stu-id="e0f7d-151">7.2</span></span>|<span data-ttu-id="e0f7d-152">编译器只接受 C# 7.2 或更低版本中所含的语法。</span><span class="sxs-lookup"><span data-stu-id="e0f7d-152">The compiler accepts only syntax that is included in C# 7.2 or lower.</span></span>|
|<span data-ttu-id="e0f7d-153">7.1</span><span class="sxs-lookup"><span data-stu-id="e0f7d-153">7.1</span></span>|<span data-ttu-id="e0f7d-154">编译器只接受 C# 7.1 或更低版本中所含的语法。</span><span class="sxs-lookup"><span data-stu-id="e0f7d-154">The compiler accepts only syntax that is included in C# 7.1 or lower.</span></span>|
|<span data-ttu-id="e0f7d-155">7</span><span class="sxs-lookup"><span data-stu-id="e0f7d-155">7</span></span>|<span data-ttu-id="e0f7d-156">编译器只接受 C# 7.0 或更低版本中所含的语法。</span><span class="sxs-lookup"><span data-stu-id="e0f7d-156">The compiler accepts only syntax that is included in C# 7.0 or lower.</span></span>|
|<span data-ttu-id="e0f7d-157">6</span><span class="sxs-lookup"><span data-stu-id="e0f7d-157">6</span></span>|<span data-ttu-id="e0f7d-158">编译器只接受 C# 6.0 或更低版本中所含的语法。</span><span class="sxs-lookup"><span data-stu-id="e0f7d-158">The compiler accepts only syntax that is included in C# 6.0 or lower.</span></span>|
|<span data-ttu-id="e0f7d-159">5</span><span class="sxs-lookup"><span data-stu-id="e0f7d-159">5</span></span>|<span data-ttu-id="e0f7d-160">编译器只接受 C# 5.0 或更低版本中所含的语法。</span><span class="sxs-lookup"><span data-stu-id="e0f7d-160">The compiler accepts only syntax that is included in C# 5.0 or lower.</span></span>|
|<span data-ttu-id="e0f7d-161">4</span><span class="sxs-lookup"><span data-stu-id="e0f7d-161">4</span></span>|<span data-ttu-id="e0f7d-162">编译器只接受 C# 4.0 或更低版本中所含的语法。</span><span class="sxs-lookup"><span data-stu-id="e0f7d-162">The compiler accepts only syntax that is included in C# 4.0 or lower.</span></span>|
|<span data-ttu-id="e0f7d-163">3</span><span class="sxs-lookup"><span data-stu-id="e0f7d-163">3</span></span>|<span data-ttu-id="e0f7d-164">编译器只接受 C# 3.0 或更低版本中所含的语法。</span><span class="sxs-lookup"><span data-stu-id="e0f7d-164">The compiler accepts only syntax that is included in C# 3.0 or lower.</span></span>|
|<span data-ttu-id="e0f7d-165">ISO-2</span><span class="sxs-lookup"><span data-stu-id="e0f7d-165">ISO-2</span></span>|<span data-ttu-id="e0f7d-166">编译器只接受 ISO/IEC 23270:2006 C# (2.0) 中所含的语法</span><span class="sxs-lookup"><span data-stu-id="e0f7d-166">The compiler accepts only syntax that is included in ISO/IEC 23270:2006 C# (2.0)</span></span> |
|<span data-ttu-id="e0f7d-167">ISO-1</span><span class="sxs-lookup"><span data-stu-id="e0f7d-167">ISO-1</span></span>|<span data-ttu-id="e0f7d-168">编译器只接受 ISO/IEC 23270:2003 C# (1.0/1.2) 中所含的语法</span><span class="sxs-lookup"><span data-stu-id="e0f7d-168">The compiler accepts only syntax that is included in ISO/IEC 23270:2003 C# (1.0/1.2)</span></span> |

## <a name="configure-multiple-projects"></a><span data-ttu-id="e0f7d-169">配置多个项目</span><span class="sxs-lookup"><span data-stu-id="e0f7d-169">Configure multiple projects</span></span>

<span data-ttu-id="e0f7d-170">可以创建包含 `<LangVersion>` 元素的 Directory.build.props 文件来配置多个目录。</span><span class="sxs-lookup"><span data-stu-id="e0f7d-170">You can create a **Directory.build.props** file that contains the `<LangVersion>` element to configure multiple directories.</span></span> <span data-ttu-id="e0f7d-171">通常是在解决方案目录中完成这件事。</span><span class="sxs-lookup"><span data-stu-id="e0f7d-171">You typically do that in your solution directory.</span></span> <span data-ttu-id="e0f7d-172">将以下内容添加到解决方案目录中的 Directory.build.props 文件：</span><span class="sxs-lookup"><span data-stu-id="e0f7d-172">Add the following to a **Directory.build.props** file in your solution directory:</span></span>

```xml
<Project>
 <PropertyGroup>
   <LangVersion>7.3</LangVersion>
 </PropertyGroup>
</Project>
```

<span data-ttu-id="e0f7d-173">现在，包含该文件的目录的每个子目录中的生成都将使用 C# 版本 7.3 语法。</span><span class="sxs-lookup"><span data-stu-id="e0f7d-173">Now, builds in every subdirectory of the directory containing that file will use C# version 7.3 syntax.</span></span> <span data-ttu-id="e0f7d-174">有关详细信息，请参阅关于[自定义生成](/visualstudio/msbuild/customize-your-build)的文章。</span><span class="sxs-lookup"><span data-stu-id="e0f7d-174">For more information, see the article on [Customize your build](/visualstudio/msbuild/customize-your-build).</span></span>

## <a name="set-the-langversion-compiler-option"></a><span data-ttu-id="e0f7d-175">选择 langversion 编译器选项</span><span class="sxs-lookup"><span data-stu-id="e0f7d-175">Set the langversion compiler option</span></span>

<span data-ttu-id="e0f7d-176">你可以使用 `-langversion` 命令行选项。</span><span class="sxs-lookup"><span data-stu-id="e0f7d-176">You can use the `-langversion` command-line option.</span></span> <span data-ttu-id="e0f7d-177">有关详细信息，请参阅关于 [/langversion](../language-reference/compiler-options/langversion-compiler-option.md) 编译器选项的文章。</span><span class="sxs-lookup"><span data-stu-id="e0f7d-177">For more information, see the article on the [-langversion](../language-reference/compiler-options/langversion-compiler-option.md) compiler option.</span></span> <span data-ttu-id="e0f7d-178">若要查看有效值的列表，请键入 `csc -langversion:?`。</span><span class="sxs-lookup"><span data-stu-id="e0f7d-178">You can see a list of the valid values by typing  `csc -langversion:?`.</span></span>
