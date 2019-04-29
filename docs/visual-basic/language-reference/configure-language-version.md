---
title: 选择 Visual Basic 语言版本
description: 配置编译器能够执行语法验证使用的特定编译器版本。
ms.date: 05/24/2018
ms.openlocfilehash: 3b6d8055dbf64f2a5c38f46b6d66794fc48a1cea
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61797028"
---
# <a name="select-the-visual-basic-language-version"></a><span data-ttu-id="0df79-103">选择 Visual Basic 语言版本</span><span class="sxs-lookup"><span data-stu-id="0df79-103">Select the Visual Basic language version</span></span>

<span data-ttu-id="0df79-104">Visual Basic 编译器将默认为已发布的语言的最新主版本。</span><span class="sxs-lookup"><span data-stu-id="0df79-104">The Visual Basic compiler defaults to the latest major version of the language that has been released.</span></span> <span data-ttu-id="0df79-105">你可以选择使用该语言的新单点版本编译任何项目。</span><span class="sxs-lookup"><span data-stu-id="0df79-105">You may choose to compile any project using a new point release of the language.</span></span> <span data-ttu-id="0df79-106">选择语言的较新版本，让你的项目可以使用最新的语言功能。</span><span class="sxs-lookup"><span data-stu-id="0df79-106">Choosing a newer version of the language enables your project to make use of the latest language features.</span></span> <span data-ttu-id="0df79-107">在其他情况下，可能需要在使用较旧的语言版本时验证项目的编译内容是否整齐。</span><span class="sxs-lookup"><span data-stu-id="0df79-107">In other scenarios, you may need to validate that a project compiles cleanly when using an older version of the language.</span></span>

<span data-ttu-id="0df79-108">借助此功能，在开发环境中安装新版本的 SDK 和工具时，不必选择在项目中引入新的语言功能。</span><span class="sxs-lookup"><span data-stu-id="0df79-108">This capability decouples the decision to install new versions of the SDK and tools in your development environment from the decision to incorporate new language features in a project.</span></span> <span data-ttu-id="0df79-109">可以在生成计算机上安装最新的 SDK 和工具。</span><span class="sxs-lookup"><span data-stu-id="0df79-109">You can install the latest SDK and tools on your build machine.</span></span> <span data-ttu-id="0df79-110">每个项目可以配置为对其生成使用该语言的特定版本。</span><span class="sxs-lookup"><span data-stu-id="0df79-110">Each project can be configured to use a specific version of the language for its build.</span></span>

<span data-ttu-id="0df79-111">有三种方法设置的语言版本：</span><span class="sxs-lookup"><span data-stu-id="0df79-111">There are three ways to set the language version:</span></span>

- <span data-ttu-id="0df79-112">手动编辑你[ **.vbproj**文件](#edit-the-vbproj-file)</span><span class="sxs-lookup"><span data-stu-id="0df79-112">Manually edit your [**.vbproj** file](#edit-the-vbproj-file)</span></span>
- <span data-ttu-id="0df79-113">设置的语言版本[的子目录中的多个项目](#configure-multiple-projects)</span><span class="sxs-lookup"><span data-stu-id="0df79-113">Set the language version [for multiple projects in a subdirectory](#configure-multiple-projects)</span></span>
- <span data-ttu-id="0df79-114">配置[`-langversion`编译器选项](#set-the-langversion-compiler-option)</span><span class="sxs-lookup"><span data-stu-id="0df79-114">Configure the [`-langversion` compiler option](#set-the-langversion-compiler-option)</span></span>

## <a name="edit-the-vbproj-file"></a><span data-ttu-id="0df79-115">编辑 vbproj 文件</span><span class="sxs-lookup"><span data-stu-id="0df79-115">Edit the vbproj file</span></span>

<span data-ttu-id="0df79-116">您可以设置的语言版本您 **.vbproj**文件。</span><span class="sxs-lookup"><span data-stu-id="0df79-116">You can set the language version in your **.vbproj** file.</span></span> <span data-ttu-id="0df79-117">添加以下元素：</span><span class="sxs-lookup"><span data-stu-id="0df79-117">Add the following element:</span></span>

```xml
<PropertyGroup>
   <LangVersion>latest</LangVersion>
</PropertyGroup>
```

<span data-ttu-id="0df79-118">值`latest`使用 Visual Basic 语言的最新次版本。</span><span class="sxs-lookup"><span data-stu-id="0df79-118">The value `latest` uses the latest minor version of the Visual Basic language.</span></span> <span data-ttu-id="0df79-119">有效值为：</span><span class="sxs-lookup"><span data-stu-id="0df79-119">Valid values are:</span></span>

|<span data-ttu-id="0df79-120">“值”</span><span class="sxs-lookup"><span data-stu-id="0df79-120">Value</span></span>|<span data-ttu-id="0df79-121">含义</span><span class="sxs-lookup"><span data-stu-id="0df79-121">Meaning</span></span>|
|------------|-------------|
|<span data-ttu-id="0df79-122">default</span><span class="sxs-lookup"><span data-stu-id="0df79-122">default</span></span>|<span data-ttu-id="0df79-123">编译器接受它可支持的最新主版本中的所有有效语言语法。</span><span class="sxs-lookup"><span data-stu-id="0df79-123">The compiler accepts all valid language syntax from the latest major version that it can support.</span></span>|
|<span data-ttu-id="0df79-124">9</span><span class="sxs-lookup"><span data-stu-id="0df79-124">9</span></span>|<span data-ttu-id="0df79-125">编译器接受仅包含在 Visual Basic 9.0 或更低的语法。</span><span class="sxs-lookup"><span data-stu-id="0df79-125">The compiler accepts only syntax that is included in Visual Basic 9.0 or lower.</span></span>|
|<span data-ttu-id="0df79-126">10</span><span class="sxs-lookup"><span data-stu-id="0df79-126">10</span></span>|<span data-ttu-id="0df79-127">编译器接受仅包含在 Visual Basic 10.0 或更低的语法。</span><span class="sxs-lookup"><span data-stu-id="0df79-127">The compiler accepts only syntax that is included in Visual Basic 10.0 or lower.</span></span>|
|<span data-ttu-id="0df79-128">11</span><span class="sxs-lookup"><span data-stu-id="0df79-128">11</span></span>|<span data-ttu-id="0df79-129">编译器接受仅包含在 Visual Basic 11.0 或更低的语法。</span><span class="sxs-lookup"><span data-stu-id="0df79-129">The compiler accepts only syntax that is included in Visual Basic 11.0 or lower.</span></span>|
|<span data-ttu-id="0df79-130">12</span><span class="sxs-lookup"><span data-stu-id="0df79-130">12</span></span>|<span data-ttu-id="0df79-131">编译器接受仅包含在 Visual Basic 12.0 或较低的语法。</span><span class="sxs-lookup"><span data-stu-id="0df79-131">The compiler accepts only syntax that is included in Visual Basic 12.0 or lower.</span></span>|
|<span data-ttu-id="0df79-132">14</span><span class="sxs-lookup"><span data-stu-id="0df79-132">14</span></span>|<span data-ttu-id="0df79-133">编译器接受仅包含在 Visual Basic 14.0 或更低的语法。</span><span class="sxs-lookup"><span data-stu-id="0df79-133">The compiler accepts only syntax that is included in Visual Basic 14.0 or lower.</span></span>|
|<span data-ttu-id="0df79-134">15</span><span class="sxs-lookup"><span data-stu-id="0df79-134">15</span></span>|<span data-ttu-id="0df79-135">编译器接受仅包含在 Visual Basic 15.0 或更低的语法。</span><span class="sxs-lookup"><span data-stu-id="0df79-135">The compiler accepts only syntax that is included in Visual Basic 15.0 or lower.</span></span>|
|<span data-ttu-id="0df79-136">15.3</span><span class="sxs-lookup"><span data-stu-id="0df79-136">15.3</span></span>|<span data-ttu-id="0df79-137">编译器接受仅包含在 Visual Basic 15.3 或更低的语法。</span><span class="sxs-lookup"><span data-stu-id="0df79-137">The compiler accepts only syntax that is included in Visual Basic 15.3 or lower.</span></span>|
|<span data-ttu-id="0df79-138">15.5</span><span class="sxs-lookup"><span data-stu-id="0df79-138">15.5</span></span>|<span data-ttu-id="0df79-139">编译器接受仅包含在 Visual Basic 15.5 或更低的语法。</span><span class="sxs-lookup"><span data-stu-id="0df79-139">The compiler accepts only syntax that is included in Visual Basic 15.5 or lower.</span></span>|
|<span data-ttu-id="0df79-140">最新</span><span class="sxs-lookup"><span data-stu-id="0df79-140">latest</span></span>|<span data-ttu-id="0df79-141">编译器接受它可支持的所有有效语言语法。</span><span class="sxs-lookup"><span data-stu-id="0df79-141">The compiler accepts all valid language syntax that it can support.</span></span>|

<span data-ttu-id="0df79-142">特殊字符串 `default` 和 `latest` 分别解析为生成计算机上安装的最新主要和次要语言版本。</span><span class="sxs-lookup"><span data-stu-id="0df79-142">The special strings `default` and `latest` resolve to the latest major and minor language versions installed on the build machine, respectively.</span></span>

## <a name="configure-multiple-projects"></a><span data-ttu-id="0df79-143">配置多个项目</span><span class="sxs-lookup"><span data-stu-id="0df79-143">Configure multiple projects</span></span>

<span data-ttu-id="0df79-144">可以创建包含 `<LangVersion>` 元素的 Directory.build.props 文件来配置多个目录。</span><span class="sxs-lookup"><span data-stu-id="0df79-144">You can create a **Directory.build.props** file that contains the `<LangVersion>` element to configure multiple directories.</span></span> <span data-ttu-id="0df79-145">通常是在解决方案目录中完成这件事。</span><span class="sxs-lookup"><span data-stu-id="0df79-145">You typically do that in your solution directory.</span></span> <span data-ttu-id="0df79-146">将以下内容添加到解决方案目录中的 Directory.build.props 文件：</span><span class="sxs-lookup"><span data-stu-id="0df79-146">Add the following to a **Directory.build.props** file in your solution directory:</span></span>

```xml
<Project>
 <PropertyGroup>
   <LangVersion>15.5</LangVersion>
 </PropertyGroup>
</Project>
```

<span data-ttu-id="0df79-147">现在，生成包含该文件的目录的每个子目录中将使用 Visual Basic 版本 15.5 语法。</span><span class="sxs-lookup"><span data-stu-id="0df79-147">Now, builds in every subdirectory of the directory containing that file will use Visual Basic version 15.5 syntax.</span></span> <span data-ttu-id="0df79-148">有关详细信息，请参阅关于[自定义生成](/visualstudio/msbuild/customize-your-build)的文章。</span><span class="sxs-lookup"><span data-stu-id="0df79-148">For more information, see the article on [Customize your build](/visualstudio/msbuild/customize-your-build).</span></span>

## <a name="set-the-langversion-compiler-option"></a><span data-ttu-id="0df79-149">选择 langversion 编译器选项</span><span class="sxs-lookup"><span data-stu-id="0df79-149">Set the langversion compiler option</span></span>

<span data-ttu-id="0df79-150">你可以使用 `-langversion` 命令行选项。</span><span class="sxs-lookup"><span data-stu-id="0df79-150">You can use the `-langversion` command-line option.</span></span> <span data-ttu-id="0df79-151">有关详细信息，请参阅关于 [/langversion](../reference/command-line-compiler/langversion.md) 编译器选项的文章。</span><span class="sxs-lookup"><span data-stu-id="0df79-151">For more information, see the article on the [-langversion](../reference/command-line-compiler/langversion.md) compiler option.</span></span> <span data-ttu-id="0df79-152">可以通过键入看到的有效值列表`vbc -langversion:?`。</span><span class="sxs-lookup"><span data-stu-id="0df79-152">You can see a list of the valid values by typing  `vbc -langversion:?` .</span></span>
