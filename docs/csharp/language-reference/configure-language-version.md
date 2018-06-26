---
title: 选择 C# 语言版本 - C# 指南
description: 配置编译器以使用特定的编译器版本执行语法验证
ms.date: 05/24/2018
ms.openlocfilehash: 9b91e62168ced0f373e1a55def8b279dc64833d8
ms.sourcegitcommit: 6bc4efca63e526ce6f2d257fa870f01f8c459ae4
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/19/2018
ms.locfileid: "36207869"
---
# <a name="select-the-c-language-version"></a><span data-ttu-id="27d76-103">选择 C# 语言版本</span><span class="sxs-lookup"><span data-stu-id="27d76-103">Select the C# language version</span></span>

<span data-ttu-id="27d76-104">C# 编译器默认采用语言已发布的最新主版本。</span><span class="sxs-lookup"><span data-stu-id="27d76-104">The C# compiler defaults to the latest major version of the language that has been released.</span></span> <span data-ttu-id="27d76-105">你可以选择使用该语言的新单点版本编译任何项目。</span><span class="sxs-lookup"><span data-stu-id="27d76-105">You may choose to compile any project using a new point release of the language.</span></span> <span data-ttu-id="27d76-106">选择语言的较新版本，让你的项目可以使用最新的语言功能。</span><span class="sxs-lookup"><span data-stu-id="27d76-106">Choosing a newer version of the language enables your project to make use of the latest language features.</span></span> <span data-ttu-id="27d76-107">在其他情况下，可能需要在使用较旧的语言版本时验证项目的编译内容是否整齐。</span><span class="sxs-lookup"><span data-stu-id="27d76-107">In other scenarios, you may need to validate that a project compiles cleanly when using an older version of the language.</span></span>

<span data-ttu-id="27d76-108">借助此功能，在开发环境中安装新版本的 SDK 和工具时，不必选择在项目中引入新的语言功能。</span><span class="sxs-lookup"><span data-stu-id="27d76-108">This capability decouples the decision to install new versions of the SDK and tools in your development environment from the decision to incorporate new language features in a project.</span></span> <span data-ttu-id="27d76-109">可以在生成计算机上安装最新的 SDK 和工具。</span><span class="sxs-lookup"><span data-stu-id="27d76-109">You can install the latest SDK and tools on your build machine.</span></span> <span data-ttu-id="27d76-110">每个项目可以配置为对其生成使用该语言的特定版本。</span><span class="sxs-lookup"><span data-stu-id="27d76-110">Each project can be configured to use a specific version of the language for its build.</span></span>

<span data-ttu-id="27d76-111">有几种方法可以设置语言版本：</span><span class="sxs-lookup"><span data-stu-id="27d76-111">There are several ways to set the language version:</span></span>

- <span data-ttu-id="27d76-112">依靠 [Visual Studio 快速操作](#visual-studio-quick-action)。</span><span class="sxs-lookup"><span data-stu-id="27d76-112">Rely on a [Visual Studio quick action](#visual-studio-quick-action).</span></span>
- <span data-ttu-id="27d76-113">在 [Visual Studio UI](#set-the-language-version-in-visual-studio) 中设置语言版本。</span><span class="sxs-lookup"><span data-stu-id="27d76-113">Set the language version in the [Visual Studio UI](#set-the-language-version-in-visual-studio).</span></span>
- <span data-ttu-id="27d76-114">手动编辑 [.csproj 文件](#edit-the-csproj-file)。</span><span class="sxs-lookup"><span data-stu-id="27d76-114">Manually edit your [**.csproj** file](#edit-the-csproj-file).</span></span>
- <span data-ttu-id="27d76-115">为[子目录中的多个项目](#configure-multiple-projects)设置语言版本。</span><span class="sxs-lookup"><span data-stu-id="27d76-115">Set the language version [for multiple projects in a subdirectory](#configure-multiple-projects).</span></span>
- <span data-ttu-id="27d76-116">配置 [`-langversion` 编译器选项](#set-the-langversion-compiler-option)。</span><span class="sxs-lookup"><span data-stu-id="27d76-116">Configure the [`-langversion` compiler option](#set-the-langversion-compiler-option).</span></span>

## <a name="visual-studio-quick-action"></a><span data-ttu-id="27d76-117">Visual Studio 快速操作</span><span class="sxs-lookup"><span data-stu-id="27d76-117">Visual Studio quick action</span></span>

<span data-ttu-id="27d76-118">Visual Studio 可帮助你确定需要的语言版本。</span><span class="sxs-lookup"><span data-stu-id="27d76-118">Visual Studio helps you determine the language version you need.</span></span> <span data-ttu-id="27d76-119">如果你使用的语言功能不适合当前配置的版本，Visual Studio 会显示一项潜在修复来为项目更新语言版本。</span><span class="sxs-lookup"><span data-stu-id="27d76-119">If you use a language feature that is not available for the currently configured version, Visual Studio shows a potential fix to update the language version for the project.</span></span>

## <a name="set-the-language-version-in-visual-studio"></a><span data-ttu-id="27d76-120">在 Visual Studio 中设置语言版本</span><span class="sxs-lookup"><span data-stu-id="27d76-120">Set the language version in Visual Studio</span></span>

<span data-ttu-id="27d76-121">可以在 Visual Studio 中设置该版本。</span><span class="sxs-lookup"><span data-stu-id="27d76-121">You can set the version in Visual Studio.</span></span> <span data-ttu-id="27d76-122">右键单击“解决方案资源管理器”中的项目节点，然后选择“属性”。</span><span class="sxs-lookup"><span data-stu-id="27d76-122">Right-click on the project node in Solution Explorer and select **Properties**.</span></span> <span data-ttu-id="27d76-123">选择**生成**选项卡并选择**高级**按钮。</span><span class="sxs-lookup"><span data-stu-id="27d76-123">Select the **Build** tab and select the **Advanced** button.</span></span> <span data-ttu-id="27d76-124">在下拉列表中，选择版本。</span><span class="sxs-lookup"><span data-stu-id="27d76-124">In the dropdown, select the version.</span></span> <span data-ttu-id="27d76-125">下图显示“最新”设置：</span><span class="sxs-lookup"><span data-stu-id="27d76-125">The following image shows the "latest" setting:</span></span>

![高级生成设置的屏幕截图，在这里可以指定语言版本](./media/configure-language-version/advanced-build-settings.png)

> [!NOTE]
> <span data-ttu-id="27d76-127">如果使用 Visual Studio IDE 来更新 csproj 文件，IDE 将为每个生成配置创建单独的节点。</span><span class="sxs-lookup"><span data-stu-id="27d76-127">If you use the Visual Studio IDE to update your csproj files, the IDE creates separate nodes for each build configuration.</span></span> <span data-ttu-id="27d76-128">通常在所有生成配置中都设置相同的值，但你需要为每个生成配置显式地设置值，或在修改此设置时选择"所有配置"。</span><span class="sxs-lookup"><span data-stu-id="27d76-128">You'll typically set the value the same in all build configurations, but you need to set it explicitly for each build configuration, or select "All Configurations" when you modify this setting.</span></span> <span data-ttu-id="27d76-129">在 csproj 文件中，你可以看到如下内容：</span><span class="sxs-lookup"><span data-stu-id="27d76-129">You'll see the following in your csproj file:</span></span>
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

## <a name="edit-the-csproj-file"></a><span data-ttu-id="27d76-130">编辑 csproj 文件</span><span class="sxs-lookup"><span data-stu-id="27d76-130">Edit the csproj file</span></span>

<span data-ttu-id="27d76-131">可在 .csproj 文件中设置语言版本。</span><span class="sxs-lookup"><span data-stu-id="27d76-131">You can set the language version in your **.csproj** file.</span></span> <span data-ttu-id="27d76-132">添加如下元素：</span><span class="sxs-lookup"><span data-stu-id="27d76-132">Add an element like the following:</span></span>

```xml
<PropertyGroup>
   <LangVersion>latest</LangVersion>
</PropertyGroup>
```

<span data-ttu-id="27d76-133">`latest` 值使用 C# 语言的最新次要版本。</span><span class="sxs-lookup"><span data-stu-id="27d76-133">The value `latest` uses the latest minor version of the C# language.</span></span> <span data-ttu-id="27d76-134">有效值为：</span><span class="sxs-lookup"><span data-stu-id="27d76-134">Valid values are:</span></span>

|<span data-ttu-id="27d76-135">“值”</span><span class="sxs-lookup"><span data-stu-id="27d76-135">Value</span></span>|<span data-ttu-id="27d76-136">含义</span><span class="sxs-lookup"><span data-stu-id="27d76-136">Meaning</span></span>|
|------------|-------------|
|<span data-ttu-id="27d76-137">default</span><span class="sxs-lookup"><span data-stu-id="27d76-137">default</span></span>|<span data-ttu-id="27d76-138">编译器接受它可支持的最新主版本中的所有有效语言语法。</span><span class="sxs-lookup"><span data-stu-id="27d76-138">The compiler accepts all valid language syntax from the latest major version that it can support.</span></span>|
|<span data-ttu-id="27d76-139">ISO-1</span><span class="sxs-lookup"><span data-stu-id="27d76-139">ISO-1</span></span>|<span data-ttu-id="27d76-140">编译器只接受 ISO/IEC 23270:2003 C# (1.0/1.2) 中所含的语法</span><span class="sxs-lookup"><span data-stu-id="27d76-140">The compiler accepts only syntax that is included in ISO/IEC 23270:2003 C# (1.0/1.2)</span></span> |
|<span data-ttu-id="27d76-141">ISO-2</span><span class="sxs-lookup"><span data-stu-id="27d76-141">ISO-2</span></span>|<span data-ttu-id="27d76-142">编译器只接受 ISO/IEC 23270:2006 C# (2.0) 中所含的语法</span><span class="sxs-lookup"><span data-stu-id="27d76-142">The compiler accepts only syntax that is included in ISO/IEC 23270:2006 C# (2.0)</span></span> |
|<span data-ttu-id="27d76-143">3</span><span class="sxs-lookup"><span data-stu-id="27d76-143">3</span></span>|<span data-ttu-id="27d76-144">编译器只接受 C# 3.0 或更低版本中所含的语法。</span><span class="sxs-lookup"><span data-stu-id="27d76-144">The compiler accepts only syntax that is included in C# 3.0 or lower.</span></span>|
|<span data-ttu-id="27d76-145">4</span><span class="sxs-lookup"><span data-stu-id="27d76-145">4</span></span>|<span data-ttu-id="27d76-146">编译器只接受 C# 4.0 或更低版本中所含的语法。</span><span class="sxs-lookup"><span data-stu-id="27d76-146">The compiler accepts only syntax that is included in C# 4.0 or lower.</span></span>|
|<span data-ttu-id="27d76-147">5</span><span class="sxs-lookup"><span data-stu-id="27d76-147">5</span></span>|<span data-ttu-id="27d76-148">编译器只接受 C# 5.0 或更低版本中所含的语法。</span><span class="sxs-lookup"><span data-stu-id="27d76-148">The compiler accepts only syntax that is included in C# 5.0 or lower.</span></span>|
|<span data-ttu-id="27d76-149">6</span><span class="sxs-lookup"><span data-stu-id="27d76-149">6</span></span>|<span data-ttu-id="27d76-150">编译器只接受 C# 6.0 或更低版本中所含的语法。</span><span class="sxs-lookup"><span data-stu-id="27d76-150">The compiler accepts only syntax that is included in C# 6.0 or lower.</span></span>|
|<span data-ttu-id="27d76-151">7</span><span class="sxs-lookup"><span data-stu-id="27d76-151">7</span></span>|<span data-ttu-id="27d76-152">编译器只接受 C# 7.0 或更低版本中所含的语法。</span><span class="sxs-lookup"><span data-stu-id="27d76-152">The compiler accepts only syntax that is included in C# 7.0 or lower.</span></span>|
|<span data-ttu-id="27d76-153">7.1</span><span class="sxs-lookup"><span data-stu-id="27d76-153">7.1</span></span>|<span data-ttu-id="27d76-154">编译器只接受 C# 7.1 或更低版本中所含的语法。</span><span class="sxs-lookup"><span data-stu-id="27d76-154">The compiler accepts only syntax that is included in C# 7.1 or lower.</span></span>|
|<span data-ttu-id="27d76-155">7.2</span><span class="sxs-lookup"><span data-stu-id="27d76-155">7.2</span></span>|<span data-ttu-id="27d76-156">编译器只接受 C# 7.2 或更低版本中所含的语法。</span><span class="sxs-lookup"><span data-stu-id="27d76-156">The compiler accepts only syntax that is included in C# 7.2 or lower.</span></span>|
|<span data-ttu-id="27d76-157">7.3</span><span class="sxs-lookup"><span data-stu-id="27d76-157">7.3</span></span>|<span data-ttu-id="27d76-158">编译器只接受 C# 7.3 或更低版本中所含的语法。</span><span class="sxs-lookup"><span data-stu-id="27d76-158">The compiler accepts only syntax that is included in C# 7.3 or lower.</span></span>|
|<span data-ttu-id="27d76-159">最新</span><span class="sxs-lookup"><span data-stu-id="27d76-159">latest</span></span>|<span data-ttu-id="27d76-160">编译器接受它可支持的所有有效语言语法。</span><span class="sxs-lookup"><span data-stu-id="27d76-160">The compiler accepts all valid language syntax that it can support.</span></span>|

<span data-ttu-id="27d76-161">特殊字符串 `default` 和 `latest` 分别解析为生成计算机上安装的最新主要语言版本 (C# 7.0) 和次要语言版本 (C# 7.3)。</span><span class="sxs-lookup"><span data-stu-id="27d76-161">The special strings `default` and `latest` resolve to the latest major (C# 7.0) and minor (C# 7.3) language versions installed on the build machine, respectively.</span></span>

## <a name="configure-multiple-projects"></a><span data-ttu-id="27d76-162">配置多个项目</span><span class="sxs-lookup"><span data-stu-id="27d76-162">Configure multiple projects</span></span>

<span data-ttu-id="27d76-163">可以创建包含 `<LangVersion>` 元素的 Directory.build.props 文件来配置多个目录。</span><span class="sxs-lookup"><span data-stu-id="27d76-163">You can create a **Directory.build.props** file that contains the `<LangVersion>` element to configure multiple directories.</span></span> <span data-ttu-id="27d76-164">通常是在解决方案目录中完成这件事。</span><span class="sxs-lookup"><span data-stu-id="27d76-164">You typically do that in your solution directory.</span></span> <span data-ttu-id="27d76-165">将以下内容添加到解决方案目录中的 Directory.build.props 文件：</span><span class="sxs-lookup"><span data-stu-id="27d76-165">Add the following to a **Directory.build.props** file in your solution directory:</span></span>

```xml
<Project>
 <PropertyGroup>
   <LangVersion>7.3</LangVersion>
 </PropertyGroup>
</Project>
```

<span data-ttu-id="27d76-166">现在，包含该文件的目录的每个子目录中的生成都将使用 C# 版本 7.3 语法。</span><span class="sxs-lookup"><span data-stu-id="27d76-166">Now, builds in every subdirectory of the directory containing that file will use C# version 7.3 syntax.</span></span> <span data-ttu-id="27d76-167">有关详细信息，请参阅关于[自定义生成](/visualstudio/msbuild/customize-your-build)的文章。</span><span class="sxs-lookup"><span data-stu-id="27d76-167">For more information, see the article on [Customize your build](/visualstudio/msbuild/customize-your-build).</span></span>

## <a name="set-the-langversion-compiler-option"></a><span data-ttu-id="27d76-168">选择 langversion 编译器选项</span><span class="sxs-lookup"><span data-stu-id="27d76-168">Set the langversion compiler option</span></span>

<span data-ttu-id="27d76-169">你可以使用 `-langversion` 命令行选项。</span><span class="sxs-lookup"><span data-stu-id="27d76-169">You can use the `-langversion` command-line option.</span></span> <span data-ttu-id="27d76-170">有关详细信息，请参阅关于 [/langversion](../language-reference/compiler-options/langversion-compiler-option.md) 编译器选项的文章。</span><span class="sxs-lookup"><span data-stu-id="27d76-170">For more information, see the article on the [-langversion](../language-reference/compiler-options/langversion-compiler-option.md) compiler option.</span></span> <span data-ttu-id="27d76-171">若要查看有效值的列表，请键入 `csc -langversion:?`。</span><span class="sxs-lookup"><span data-stu-id="27d76-171">You can see a list of the valid values by typing  `csc -langversion:?`.</span></span>
