---
title: "在 .NET Core 工具中管理依赖项"
description: "介绍如何使用 .NET Core 工具管理依赖项。"
keywords: "CLI, 扩展性, 自定义命令, .NET Core"
author: blackdwarf
ms.author: mairaw
ms.date: 03/06/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: 74b87cdb-a244-4c13-908c-539118bfeef9
ms.openlocfilehash: 21f42bbf4693c78a5be271b7769ef4489ed6d476
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="managing-dependencies-with-net-core-sdk-10"></a><span data-ttu-id="650b7-104">使用 .NET Core SDK 1.0 管理依赖项</span><span class="sxs-lookup"><span data-stu-id="650b7-104">Managing dependencies with .NET Core SDK 1.0</span></span>

<span data-ttu-id="650b7-105">在 .NET Core 项目从 project.json 移动到 csproj 和 MSBuild 的同时，还投入了大笔资金将项目文件和资产统一，以便跟踪依赖项。</span><span class="sxs-lookup"><span data-stu-id="650b7-105">With the move of .NET Core projects from project.json to csproj and MSBuild, a significant investment also happened that resulted in unification of the project file and assets that allow tracking of dependencies.</span></span> <span data-ttu-id="650b7-106">对于 .NET Core 项目，这与 project.json 的做法类似。</span><span class="sxs-lookup"><span data-stu-id="650b7-106">For .NET Core projects this is similar to what project.json did.</span></span> <span data-ttu-id="650b7-107">没有单独的 JSON 或 XML 文件来跟踪 NuGet 依赖项。</span><span class="sxs-lookup"><span data-stu-id="650b7-107">There is no separate JSON or XML file that tracks NuGet dependencies.</span></span> <span data-ttu-id="650b7-108">通过这种改变，我们还在名为 `<PackageReference>` 的 csproj 语法中引入了另一种类型的引用。</span><span class="sxs-lookup"><span data-stu-id="650b7-108">With this change, we've also introduced another type of *reference* into the csproj syntax called the `<PackageReference>`.</span></span> 

<span data-ttu-id="650b7-109">本文档介绍了新的引用类型。</span><span class="sxs-lookup"><span data-stu-id="650b7-109">This document describes the new reference type.</span></span> <span data-ttu-id="650b7-110">它还演示了如何使用此新引用类型将包依赖项添加到项目。</span><span class="sxs-lookup"><span data-stu-id="650b7-110">It also shows how to add a package dependency using this new reference type to your project.</span></span> 

## <a name="the-new-packagereference-element"></a><span data-ttu-id="650b7-111">新 \<PackageReference> 元素</span><span class="sxs-lookup"><span data-stu-id="650b7-111">The new \<PackageReference> element</span></span>
<span data-ttu-id="650b7-112">`<PackageReference>` 具有下列基本结构：</span><span class="sxs-lookup"><span data-stu-id="650b7-112">The `<PackageReference>` has the following basic structure:</span></span>

```xml
<PackageReference Include="PACKAGE_ID" Version="PACKAGE_VERSION" />
```

<span data-ttu-id="650b7-113">如果你熟悉 MSBuild，则它看起来和已有的引用类型很相似。</span><span class="sxs-lookup"><span data-stu-id="650b7-113">If you are familiar with MSBuild, it will look familiar to the other reference types that already exist.</span></span> <span data-ttu-id="650b7-114">关键是 `Include` 语句，它指定要添加到项目的包 ID。</span><span class="sxs-lookup"><span data-stu-id="650b7-114">The key is the `Include` statement which specifies the package id that you wish to add to the project.</span></span> <span data-ttu-id="650b7-115">`<Version>` 子元素指定要获取的版本。</span><span class="sxs-lookup"><span data-stu-id="650b7-115">The `<Version>` child element specifies the version to get.</span></span> <span data-ttu-id="650b7-116">根据 [NuGet 版本规则](/nuget/create-packages/dependency-versions#version-ranges)指定版本。</span><span class="sxs-lookup"><span data-stu-id="650b7-116">The versions are specified as per [NuGet version rules](/nuget/create-packages/dependency-versions#version-ranges).</span></span>

> [!NOTE]
> <span data-ttu-id="650b7-117">如果不熟悉整体 `csproj` 语法，可参阅 [MSBuild 项目参考](/visualstudio/msbuild/msbuild-project-file-schema-reference)文档了解详细信息。</span><span class="sxs-lookup"><span data-stu-id="650b7-117">If you are not familiar with the overall `csproj` syntax, see the [MSBuild project reference](/visualstudio/msbuild/msbuild-project-file-schema-reference) documentation for more information.</span></span>  

<span data-ttu-id="650b7-118">使用类似以下示例中的条件添加仅在特定目标中可用的依赖项：</span><span class="sxs-lookup"><span data-stu-id="650b7-118">Adding a dependency that is available only in a specific target is done using conditions like in the following example:</span></span>

```xml
<PackageReference Include="PACKAGE_ID" Version="PACKAGE_VERSION" Condition="'$(TargetFramework)' == 'netcoreapp1.0'" />
```

<span data-ttu-id="650b7-119">上面的意思是，依赖项只有在对给定目标生成时才有效。</span><span class="sxs-lookup"><span data-stu-id="650b7-119">The above means that the dependency will only be valid if the build is happening for that given target.</span></span> <span data-ttu-id="650b7-120">条件中的 `$(TargetFramework)` 是将在项目中设置的 MSBuild 属性。</span><span class="sxs-lookup"><span data-stu-id="650b7-120">The `$(TargetFramework)` in the condition is a MSBuild property that is being set in the project.</span></span> <span data-ttu-id="650b7-121">对于大多数常见的 .NET Core 应用程序，无需这样做。</span><span class="sxs-lookup"><span data-stu-id="650b7-121">For most common .NET Core applications, you will not need to do this.</span></span> 

## <a name="adding-a-dependency-to-your-project"></a><span data-ttu-id="650b7-122">向项目添加依赖项</span><span class="sxs-lookup"><span data-stu-id="650b7-122">Adding a dependency to your project</span></span>
<span data-ttu-id="650b7-123">向项目添加依赖项非常简单。</span><span class="sxs-lookup"><span data-stu-id="650b7-123">Adding a dependency to your project is straightforward.</span></span> <span data-ttu-id="650b7-124">下面是如何向项目添加 Json.NET 版本 `9.0.1` 的示例。</span><span class="sxs-lookup"><span data-stu-id="650b7-124">Here is an example of how to add Json.NET version `9.0.1` to your project.</span></span> <span data-ttu-id="650b7-125">当然，它也适用于其他任意 NuGet 依赖项。</span><span class="sxs-lookup"><span data-stu-id="650b7-125">Of course, it is applicable to any other NuGet dependency.</span></span> 

<span data-ttu-id="650b7-126">打开项目文件时，将看到两个或多个 `<ItemGroup>` 节点。</span><span class="sxs-lookup"><span data-stu-id="650b7-126">When you open your project file, you will see two or more `<ItemGroup>` nodes.</span></span> <span data-ttu-id="650b7-127">你会注意到其中一个节点已有 `<PackageReference>` 元素。</span><span class="sxs-lookup"><span data-stu-id="650b7-127">You will notice that one of the nodes already has `<PackageReference>` elements in it.</span></span> <span data-ttu-id="650b7-128">可以向此节点添加新的依赖项，或创建一个新的依赖项；这完全取决于你，因为其结果将是一样的。</span><span class="sxs-lookup"><span data-stu-id="650b7-128">You can add your new dependency to this node, or create a new one; it is completely up to you as the result will be the same.</span></span> 

<span data-ttu-id="650b7-129">在本示例中，将使用被 `dotnet new console` 删除的默认模板。</span><span class="sxs-lookup"><span data-stu-id="650b7-129">In this example we will use the default template that is dropped by `dotnet new console`.</span></span> <span data-ttu-id="650b7-130">这是一个简单的控制台应用程序。</span><span class="sxs-lookup"><span data-stu-id="650b7-130">This is a simple console application.</span></span> <span data-ttu-id="650b7-131">打开项目时，首先找到 `<ItemGroup>`，其中包含已存在的 `<PackageReference>`。</span><span class="sxs-lookup"><span data-stu-id="650b7-131">When we open up the project, we first find the `<ItemGroup>` with already existing `<PackageReference>` in it.</span></span> <span data-ttu-id="650b7-132">然后将下列内容添加进去：</span><span class="sxs-lookup"><span data-stu-id="650b7-132">We then add the following to it:</span></span>

```xml
<PackageReference Include="Newtonsoft.Json" Version="9.0.1" />
```
<span data-ttu-id="650b7-133">之后，保存项目并运行 `dotnet restore` 命令以安装依赖项。</span><span class="sxs-lookup"><span data-stu-id="650b7-133">After this, we save the project and run the `dotnet restore` command to install the dependency.</span></span> 

[!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]

<span data-ttu-id="650b7-134">完整项目如下所示：</span><span class="sxs-lookup"><span data-stu-id="650b7-134">The full project looks like this:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <OutputType>Exe</OutputType>
    <TargetFramework>netcoreapp1.0</TargetFramework>
  </PropertyGroup>

  <ItemGroup>
    <PackageReference Include="Newtonsoft.Json" Version="9.0.1" />
  </ItemGroup>
</Project>
```

## <a name="removing-a-dependency-from-the-project"></a><span data-ttu-id="650b7-135">从项目中删除依赖项</span><span class="sxs-lookup"><span data-stu-id="650b7-135">Removing a dependency from the project</span></span>
<span data-ttu-id="650b7-136">从项目文件中删除依赖项仅包含从项目文件中删除 `<PackageReference>`。</span><span class="sxs-lookup"><span data-stu-id="650b7-136">Removing a dependency from the project file involves simply removing the `<PackageReference>` from the project file.</span></span>
