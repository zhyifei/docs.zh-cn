---
title: 组织项目以支持 .NET Framework 和 .NET Core
description: 帮助希望针对 .NET Framework 和 .NET Core 并行编译解决方案的项目所有者。
author: conniey
ms.author: mairaw
ms.date: 04/06/2017
ms.openlocfilehash: e6cd9c6d66996d9fd24fe71d48091723143e5849
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33211434"
---
# <a name="organizing-your-project-to-support-net-framework-and-net-core"></a><span data-ttu-id="530b4-103">组织项目以支持 .NET Framework 和 .NET Core</span><span class="sxs-lookup"><span data-stu-id="530b4-103">Organizing your project to support .NET Framework and .NET Core</span></span>

<span data-ttu-id="530b4-104">本文旨在帮助希望针对 .NET Framework 和 .NET Core 并行编译解决方案的项目所有者。</span><span class="sxs-lookup"><span data-stu-id="530b4-104">This article helps project owners who want to compile their solution against .NET Framework and .NET Core side-by-side.</span></span> <span data-ttu-id="530b4-105">它提供了多个可组织项目的选项以帮助开发人员实现此目标。</span><span class="sxs-lookup"><span data-stu-id="530b4-105">It provides several options to organize projects to help developers achieve this goal.</span></span> <span data-ttu-id="530b4-106">下列列表提供了一些在决定如何使用 .NET Core 设置项目时需考虑的典型方案。</span><span class="sxs-lookup"><span data-stu-id="530b4-106">The following list provides some typical scenarios to consider when you're deciding how to setup your project layout with .NET Core.</span></span> <span data-ttu-id="530b4-107">此列表可能无法涵盖所有要求；这些方案的优先级具体取决于项目需求。</span><span class="sxs-lookup"><span data-stu-id="530b4-107">The list may not cover everything you want; prioritize based on your project's needs.</span></span>

* <span data-ttu-id="530b4-108">[**将现有项目和 .NET Core 项目合并为单个项目**][option-csproj]</span><span class="sxs-lookup"><span data-stu-id="530b4-108">[**Combine existing projects and .NET Core projects into single projects**][option-csproj]</span></span>

  <span data-ttu-id="530b4-109">*此方案的好处：*</span><span class="sxs-lookup"><span data-stu-id="530b4-109">*What this is good for:*</span></span>
  * <span data-ttu-id="530b4-110">通过编译单个项目（而非多个项目）简化生成过程，每个项目针对不同的 .NET Framework 版本或平台。</span><span class="sxs-lookup"><span data-stu-id="530b4-110">Simplifying your build process by compiling a single project rather than compiling multiple projects, each targeting a different .NET Framework version or platform.</span></span>
  * <span data-ttu-id="530b4-111">由于需要管理单个项目文件，因此简化了多目标项目的源文件管理。</span><span class="sxs-lookup"><span data-stu-id="530b4-111">Simplifying source file management for multi-targeted projects because you must manage a single project file.</span></span> <span data-ttu-id="530b4-112">添加/删除源文件时，需要手动将备用文件与其他项目进行同步。</span><span class="sxs-lookup"><span data-stu-id="530b4-112">When adding/removing source files, the alternatives require you to manually sync these with your other projects.</span></span>
  * <span data-ttu-id="530b4-113">轻松生成可供使用的 NuGet 包。</span><span class="sxs-lookup"><span data-stu-id="530b4-113">Easily generating a NuGet package for consumption.</span></span>
  * <span data-ttu-id="530b4-114">允许通过使用编译器指令为库中特定的 .NET Framework 版本编写代码。</span><span class="sxs-lookup"><span data-stu-id="530b4-114">Allows you to write code for a specific .NET Framework version in your libraries through the use of compiler directives.</span></span>

  <span data-ttu-id="530b4-115">*不支持的方案：*</span><span class="sxs-lookup"><span data-stu-id="530b4-115">*Unsupported scenarios:*</span></span>
  * <span data-ttu-id="530b4-116">要求开发者使用 Visual Studio 2017 来打开现有项目。</span><span class="sxs-lookup"><span data-stu-id="530b4-116">Requires developers to use Visual Studio 2017 to open existing projects.</span></span> <span data-ttu-id="530b4-117">若要支持 Visual Studio 的早期版本，建议[将项目文件保存在不同的文件夹中](#support-vs)。</span><span class="sxs-lookup"><span data-stu-id="530b4-117">To support older versions of Visual Studio, [keeping your project files in different folders](#support-vs) is a better option.</span></span>

* <a name="support-vs"></a><span data-ttu-id="530b4-118">[**将现有项目和新的 .NET Core 项目分离**][option-csproj-folder]</span><span class="sxs-lookup"><span data-stu-id="530b4-118">[**Keep existing projects and new .NET Core projects separate**][option-csproj-folder]</span></span>

  <span data-ttu-id="530b4-119">*此方案的好处：*</span><span class="sxs-lookup"><span data-stu-id="530b4-119">*What this is good for:*</span></span>
  * <span data-ttu-id="530b4-120">继续支持现有项目的开发，而无需为没有安装 Visual Studio 2017 的开发人员/参与者进行升级。</span><span class="sxs-lookup"><span data-stu-id="530b4-120">Continuing to support development on existing projects without having to upgrade for developers/contributors who may not have Visual Studio 2017.</span></span>
  * <span data-ttu-id="530b4-121">减少现有项目中出现新 bug 的可能性，因为这些项目中不需要进行任何代码改动。</span><span class="sxs-lookup"><span data-stu-id="530b4-121">Decreasing the possibility of creating new bugs in existing projects because no code churn is required in those projects.</span></span>

## <a name="example"></a><span data-ttu-id="530b4-122">示例</span><span class="sxs-lookup"><span data-stu-id="530b4-122">Example</span></span>

<span data-ttu-id="530b4-123">请考虑以下存储库：</span><span class="sxs-lookup"><span data-stu-id="530b4-123">Consider the repository below:</span></span>

<span data-ttu-id="530b4-124">![现有项目][example-initial-project]</span><span class="sxs-lookup"><span data-stu-id="530b4-124">![Existing project][example-initial-project]</span></span>

<span data-ttu-id="530b4-125">[**源代码**][example-initial-project-code]</span><span class="sxs-lookup"><span data-stu-id="530b4-125">[**Source Code**][example-initial-project-code]</span></span>

<span data-ttu-id="530b4-126">根据现有项目的约束和复杂性，有几种不同的方法可为此存储库添加对 .NET Core 的支持，下面描述了这些方法。</span><span class="sxs-lookup"><span data-stu-id="530b4-126">The following describes several ways to add support for .NET Core for this repository depending on the constraints and complexity of the existing projects.</span></span>

## <a name="replace-existing-projects-with-a-multi-targeted-net-core-project"></a><span data-ttu-id="530b4-127">将现有项目替换为多目标的 .NET Core 项目</span><span class="sxs-lookup"><span data-stu-id="530b4-127">Replace existing projects with a multi-targeted .NET Core project</span></span>

<span data-ttu-id="530b4-128">重新组织存储库，以便删除任何现有的 \*.csproj 文件，并创建以多个框架为目标的单一 \*.csproj 文件。</span><span class="sxs-lookup"><span data-stu-id="530b4-128">Reorganize the repository so that any existing *\*.csproj* files are removed and a single *\*.csproj* file is created that targets multiple frameworks.</span></span> <span data-ttu-id="530b4-129">这是一项不错的选择，因为单个项目可以编译不同的框架。</span><span class="sxs-lookup"><span data-stu-id="530b4-129">This is a great option because a single project is able to compile for different frameworks.</span></span> <span data-ttu-id="530b4-130">它还可以处理每个目标框架的不同编译选项和依赖项。</span><span class="sxs-lookup"><span data-stu-id="530b4-130">It also has the power to handle different compilation options and dependencies per targeted framework.</span></span>

<span data-ttu-id="530b4-131">![创建以多个框架为目标的 csproj][example-csproj]</span><span class="sxs-lookup"><span data-stu-id="530b4-131">![Create an csproj that targets multiple frameworks][example-csproj]</span></span>

<span data-ttu-id="530b4-132">[**源代码**][example-csproj-code]</span><span class="sxs-lookup"><span data-stu-id="530b4-132">[**Source Code**][example-csproj-code]</span></span>

<span data-ttu-id="530b4-133">需注意的更改：</span><span class="sxs-lookup"><span data-stu-id="530b4-133">Changes to note are:</span></span>
* <span data-ttu-id="530b4-134">用新的 [.NET Core *\*.csproj*][example-csproj-netcore] 替换 packages.config 和 \*.csproj。</span><span class="sxs-lookup"><span data-stu-id="530b4-134">Replacement of *packages.config* and *\*.csproj* with a new [.NET Core *\*.csproj*][example-csproj-netcore].</span></span> <span data-ttu-id="530b4-135">NuGet 包是使用 `<PackageReference> ItemGroup` 指定的。</span><span class="sxs-lookup"><span data-stu-id="530b4-135">NuGet packages are specified with `<PackageReference> ItemGroup`.</span></span>

## <a name="keep-existing-projects-and-create-a-net-core-project"></a><span data-ttu-id="530b4-136">保留现有项目并创建 .NET Core 项目</span><span class="sxs-lookup"><span data-stu-id="530b4-136">Keep existing projects and create a .NET Core project</span></span>

<span data-ttu-id="530b4-137">如果存在以较旧框架为目标的现有项目，可能需要保留这些项目并将 .NET Core 项目用作将来框架的目标。</span><span class="sxs-lookup"><span data-stu-id="530b4-137">If there are existing projects that target older frameworks, you may want to leave these projects untouched and use a .NET Core project to target future frameworks.</span></span>

<span data-ttu-id="530b4-138">![不同文件夹中包含现有项目的 .NET Core 项目][example-csproj-different-folder]</span><span class="sxs-lookup"><span data-stu-id="530b4-138">![.NET Core project with existing project in different folder][example-csproj-different-folder]</span></span>

<span data-ttu-id="530b4-139">[**源代码**][example-csproj-different-code]</span><span class="sxs-lookup"><span data-stu-id="530b4-139">[**Source Code**][example-csproj-different-code]</span></span>

<span data-ttu-id="530b4-140">需注意的更改：</span><span class="sxs-lookup"><span data-stu-id="530b4-140">Changes to note are:</span></span>
* <span data-ttu-id="530b4-141">将 .NET Core 项目和现有项目保存在不同的文件夹中。</span><span class="sxs-lookup"><span data-stu-id="530b4-141">The .NET Core and existing projects are kept in separate folders.</span></span>
    * <span data-ttu-id="530b4-142">将项目保存在不同的文件夹中可以避免强制使用 Visual Studio 2017。</span><span class="sxs-lookup"><span data-stu-id="530b4-142">Keeping projects in separate folders avoids forcing you to have Visual Studio 2017.</span></span> <span data-ttu-id="530b4-143">可以创建仅打开旧项目的单独解决方案。</span><span class="sxs-lookup"><span data-stu-id="530b4-143">You can create a separate solution that only opens the old projects.</span></span>

## <a name="see-also"></a><span data-ttu-id="530b4-144">请参阅</span><span class="sxs-lookup"><span data-stu-id="530b4-144">See Also</span></span>

<span data-ttu-id="530b4-145">有关迁移到 .NET Core 的详细指南，请参阅 [.NET Core 移植文档][porting-doc]。</span><span class="sxs-lookup"><span data-stu-id="530b4-145">Please see the [.NET Core porting documentation][porting-doc] for more guidance on migrating to .NET Core.</span></span>

[porting-doc]: index.md
[example-initial-project]: media/project-structure/project.png "现有项目"
[example-initial-project-code]: https://github.com/dotnet/samples/tree/master/framework/libraries/migrate-library/

[example-csproj]: media/project-structure/project.csproj.png "创建以多个框架为目标的 csproj"
[example-csproj-code]: https://github.com/dotnet/samples/tree/master/framework/libraries/migrate-library-csproj/
[example-csproj-netcore]: https://github.com/dotnet/samples/tree/master/framework/libraries/migrate-library-csproj/src/Car/Car.csproj

[example-csproj-different-folder]: media/project-structure/project.csproj.different.png "不同文件夹中包含现有 PCL 的 .NET Core 项目"
[example-csproj-different-code]: https://github.com/dotnet/samples/tree/master/framework/libraries/migrate-library-csproj-keep-existing/

[option-csproj]: #replace-existing-projects-with-a-multi-targeted-net-core-project
[option-csproj-folder]: #keep-existing-projects-and-create-a-net-core-project
