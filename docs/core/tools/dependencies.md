---
title: 在 .NET Core 工具中管理依赖项
description: 介绍如何使用 .NET Core 工具管理依赖项。
ms.date: 03/06/2017
ms.openlocfilehash: 28280dc05e746cdef4e90870cd4cb528382c45bd
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/28/2020
ms.locfileid: "76787858"
---
# <a name="manage-dependencies-with-net-core-sdk-10"></a><span data-ttu-id="74ca1-103">使用 .NET Core SDK 1.0 管理依赖项</span><span class="sxs-lookup"><span data-stu-id="74ca1-103">Manage dependencies with .NET Core SDK 1.0</span></span>

<span data-ttu-id="74ca1-104">在 .NET Core 项目从 project.json 移动到 csproj 和 MSBuild 的同时，还投入了大笔资金将项目文件和资产统一，以便跟踪依赖项。</span><span class="sxs-lookup"><span data-stu-id="74ca1-104">With the move of .NET Core projects from project.json to csproj and MSBuild, a significant investment also happened that resulted in unification of the project file and assets that allow tracking of dependencies.</span></span> <span data-ttu-id="74ca1-105">对于 .NET Core 项目，这与 project.json 的做法类似。</span><span class="sxs-lookup"><span data-stu-id="74ca1-105">For .NET Core projects, this is similar to what project.json did.</span></span> <span data-ttu-id="74ca1-106">没有单独的 JSON 或 XML 文件来跟踪 NuGet 依赖项。</span><span class="sxs-lookup"><span data-stu-id="74ca1-106">There is no separate JSON or XML file that tracks NuGet dependencies.</span></span> <span data-ttu-id="74ca1-107">通过这种改变，我们还在名为 `<PackageReference>` 的 csproj 语法中引入了另一种类型的引用  。</span><span class="sxs-lookup"><span data-stu-id="74ca1-107">With this change, we've also introduced another type of *reference* into the csproj syntax called the `<PackageReference>`.</span></span>

<span data-ttu-id="74ca1-108">本文档介绍了新的引用类型。</span><span class="sxs-lookup"><span data-stu-id="74ca1-108">This document describes the new reference type.</span></span> <span data-ttu-id="74ca1-109">它还演示了如何使用此新引用类型将包依赖项添加到项目。</span><span class="sxs-lookup"><span data-stu-id="74ca1-109">It also shows how to add a package dependency using this new reference type to your project.</span></span>

## <a name="the-new-packagereference-element"></a><span data-ttu-id="74ca1-110">新 \<PackageReference> 元素</span><span class="sxs-lookup"><span data-stu-id="74ca1-110">The new \<PackageReference> element</span></span>

<span data-ttu-id="74ca1-111">`<PackageReference>` 具有下列基本结构：</span><span class="sxs-lookup"><span data-stu-id="74ca1-111">The `<PackageReference>` has the following basic structure:</span></span>

```xml
<PackageReference Include="PACKAGE_ID" Version="PACKAGE_VERSION" />
```

<span data-ttu-id="74ca1-112">如果你熟悉 MSBuild，则它看起来和已有的引用类型很相似。</span><span class="sxs-lookup"><span data-stu-id="74ca1-112">If you are familiar with MSBuild, it will look familiar to the other reference types that already exist.</span></span> <span data-ttu-id="74ca1-113">关键是 `Include` 语句，它指定要添加到项目的包 ID。</span><span class="sxs-lookup"><span data-stu-id="74ca1-113">The key is the `Include` statement, which specifies the package id that you wish to add to the project.</span></span> <span data-ttu-id="74ca1-114">`<Version>` 子元素指定要获取的版本。</span><span class="sxs-lookup"><span data-stu-id="74ca1-114">The `<Version>` child element specifies the version to get.</span></span> <span data-ttu-id="74ca1-115">根据 [NuGet 版本规则](/nuget/create-packages/dependency-versions#version-ranges)指定版本。</span><span class="sxs-lookup"><span data-stu-id="74ca1-115">The versions are specified as per [NuGet version rules](/nuget/create-packages/dependency-versions#version-ranges).</span></span>

> [!NOTE]
> <span data-ttu-id="74ca1-116">如果不熟悉整体 `csproj` 语法，可参阅 [MSBuild 项目参考](/visualstudio/msbuild/msbuild-project-file-schema-reference)文档了解详细信息。</span><span class="sxs-lookup"><span data-stu-id="74ca1-116">If you are not familiar with the overall `csproj` syntax, see the [MSBuild project reference](/visualstudio/msbuild/msbuild-project-file-schema-reference) documentation for more information.</span></span>

<span data-ttu-id="74ca1-117">使用类似以下示例中的条件添加仅在特定目标中可用的依赖项：</span><span class="sxs-lookup"><span data-stu-id="74ca1-117">Adding a dependency that is available only in a specific target is done using conditions like in the following example:</span></span>

```xml
<PackageReference Include="PACKAGE_ID" Version="PACKAGE_VERSION" Condition="'$(TargetFramework)' == 'netcoreapp2.1'" />
```

<span data-ttu-id="74ca1-118">上面的意思是，依赖项只有在对给定目标生成时才有效。</span><span class="sxs-lookup"><span data-stu-id="74ca1-118">The above means that the dependency will only be valid if the build is happening for that given target.</span></span> <span data-ttu-id="74ca1-119">条件中的 `$(TargetFramework)` 是将在项目中设置的 MSBuild 属性。</span><span class="sxs-lookup"><span data-stu-id="74ca1-119">The `$(TargetFramework)` in the condition is an MSBuild property that is being set in the project.</span></span> <span data-ttu-id="74ca1-120">对于大多数常见的 .NET Core 应用程序，无需这样做。</span><span class="sxs-lookup"><span data-stu-id="74ca1-120">For most common .NET Core applications, you will not need to do this.</span></span>

## <a name="add-a-dependency-to-the-project"></a><span data-ttu-id="74ca1-121">向项目添加依赖项</span><span class="sxs-lookup"><span data-stu-id="74ca1-121">Add a dependency to the project</span></span>

<span data-ttu-id="74ca1-122">向项目添加依赖项非常简单。</span><span class="sxs-lookup"><span data-stu-id="74ca1-122">Adding a dependency to your project is straightforward.</span></span> <span data-ttu-id="74ca1-123">下面是如何向项目添加 Json.NET 版本 `9.0.1` 的示例。</span><span class="sxs-lookup"><span data-stu-id="74ca1-123">Here is an example of how to add Json.NET version `9.0.1` to your project.</span></span> <span data-ttu-id="74ca1-124">当然，它也适用于其他任意 NuGet 依赖项。</span><span class="sxs-lookup"><span data-stu-id="74ca1-124">Of course, it is applicable to any other NuGet dependency.</span></span>

<span data-ttu-id="74ca1-125">打开项目文件时，将看到两个或多个 `<ItemGroup>` 节点。</span><span class="sxs-lookup"><span data-stu-id="74ca1-125">When you open your project file, you will see two or more `<ItemGroup>` nodes.</span></span> <span data-ttu-id="74ca1-126">你会注意到其中一个节点已有 `<PackageReference>` 元素。</span><span class="sxs-lookup"><span data-stu-id="74ca1-126">You will notice that one of the nodes already has `<PackageReference>` elements in it.</span></span> <span data-ttu-id="74ca1-127">可以向此节点添加新的依赖项，或创建一个新的依赖项；这取决于你，因为结果将是一样的。</span><span class="sxs-lookup"><span data-stu-id="74ca1-127">You can add your new dependency to this node, or create a new one; it is up to you, as the result will be the same.</span></span>

<span data-ttu-id="74ca1-128">下面的示例使用 `dotnet new console` 删除的默认模板。</span><span class="sxs-lookup"><span data-stu-id="74ca1-128">The following example uses the default template that's dropped by `dotnet new console`.</span></span> <span data-ttu-id="74ca1-129">这是一个简单的控制台应用程序。</span><span class="sxs-lookup"><span data-stu-id="74ca1-129">This is a simple console application.</span></span> <span data-ttu-id="74ca1-130">打开项目时，将找到 `<ItemGroup>`，其中包含已存在的 `<PackageReference>`。</span><span class="sxs-lookup"><span data-stu-id="74ca1-130">When you open up the project, you'll find the `<ItemGroup>` with already existing `<PackageReference>` in it.</span></span> <span data-ttu-id="74ca1-131">在其中添加以下代码：</span><span class="sxs-lookup"><span data-stu-id="74ca1-131">Add the following to it:</span></span>

```xml
<PackageReference Include="Newtonsoft.Json" Version="9.0.1" />
```

<span data-ttu-id="74ca1-132">之后，保存项目并运行 `dotnet restore` 命令以安装依赖项。</span><span class="sxs-lookup"><span data-stu-id="74ca1-132">After this, save the project and run the `dotnet restore` command to install the dependency.</span></span>

[!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]

<span data-ttu-id="74ca1-133">完整项目如下所示：</span><span class="sxs-lookup"><span data-stu-id="74ca1-133">The full project looks like this:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <OutputType>Exe</OutputType>
    <TargetFramework>netcoreapp2.1</TargetFramework>
  </PropertyGroup>

  <ItemGroup>
    <PackageReference Include="Newtonsoft.Json" Version="9.0.1" />
  </ItemGroup>
</Project>
```

## <a name="remove-a-dependency-from-the-project"></a><span data-ttu-id="74ca1-134">从项目中删除依赖项</span><span class="sxs-lookup"><span data-stu-id="74ca1-134">Remove a dependency from the project</span></span>

<span data-ttu-id="74ca1-135">从项目文件中删除依赖项只需从项目文件中删除 `<PackageReference>`。</span><span class="sxs-lookup"><span data-stu-id="74ca1-135">Removing a dependency from the project file involves simply removing the `<PackageReference>` from the project file.</span></span>
