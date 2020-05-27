---
title: ''
description: ''
no-loc:
- dotnet add package
- dotnet remove package
- dotnet list package
ms.date: ''
ms.openlocfilehash: 667b2d4d68edd82a4d18c370e45ea18f4d4b379a
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2020
ms.locfileid: "83702841"
---
# <a name="manage-dependencies-in-net-core-applications"></a><span data-ttu-id="f7d65-101">管理 .NET Core 应用程序中的依赖项</span><span class="sxs-lookup"><span data-stu-id="f7d65-101">Manage dependencies in .NET Core applications</span></span>

<span data-ttu-id="f7d65-102">本文介绍如何通过编辑项目文件或使用 CLI 来添加和删除依赖项。</span><span class="sxs-lookup"><span data-stu-id="f7d65-102">This article explains how to add and remove dependencies by editing the project file or by using the CLI.</span></span>

## <a name="the-packagereference-element"></a><span data-ttu-id="f7d65-103">\<PackageReference> 元素</span><span class="sxs-lookup"><span data-stu-id="f7d65-103">The \<PackageReference> element</span></span>

<span data-ttu-id="f7d65-104">`<PackageReference>` 项目文件元素具有以下结构：</span><span class="sxs-lookup"><span data-stu-id="f7d65-104">The `<PackageReference>` project file element has the following structure:</span></span>

```xml
<PackageReference Include="PACKAGE_ID" Version="PACKAGE_VERSION" />
```

<span data-ttu-id="f7d65-105">`Include` 特性指定要添加到项目的包的 ID。</span><span class="sxs-lookup"><span data-stu-id="f7d65-105">The `Include` attribute specifies the ID of the package to add to the project.</span></span> <span data-ttu-id="f7d65-106">`Version` 特性指定要获取的版本。</span><span class="sxs-lookup"><span data-stu-id="f7d65-106">The `Version` attribute specifies the version to get.</span></span> <span data-ttu-id="f7d65-107">版本根据 [NuGet 版本规则](/nuget/create-packages/dependency-versions#version-ranges)进行指定。</span><span class="sxs-lookup"><span data-stu-id="f7d65-107">Versions are specified as per [NuGet version rules](/nuget/create-packages/dependency-versions#version-ranges).</span></span>

> [!NOTE]
> <span data-ttu-id="f7d65-108">如果不熟悉“项目-文件”语法，可参阅 [MSBuild 项目参考](/visualstudio/msbuild/msbuild-project-file-schema-reference)文档了解详细信息。</span><span class="sxs-lookup"><span data-stu-id="f7d65-108">If you're not familiar with project-file syntax, see the [MSBuild project reference](/visualstudio/msbuild/msbuild-project-file-schema-reference) documentation for more information.</span></span>

<span data-ttu-id="f7d65-109">使用条件来添加仅在特定目标中可用的依赖项，如以下示例所示：</span><span class="sxs-lookup"><span data-stu-id="f7d65-109">Use conditions to add a dependency that's available only in a specific target, as shown in the following example:</span></span>

```xml
<PackageReference Include="PACKAGE_ID" Version="PACKAGE_VERSION" Condition="'$(TargetFramework)' == 'netcoreapp2.1'" />
```

<span data-ttu-id="f7d65-110">上述示例中的依赖项只有在对给定目标生成时才有效。</span><span class="sxs-lookup"><span data-stu-id="f7d65-110">The dependency in the preceding example will only be valid if the build is happening for that given target.</span></span> <span data-ttu-id="f7d65-111">条件中的 `$(TargetFramework)` 是将在项目中设置的 MSBuild 属性。</span><span class="sxs-lookup"><span data-stu-id="f7d65-111">The `$(TargetFramework)` in the condition is an MSBuild property that's being set in the project.</span></span> <span data-ttu-id="f7d65-112">对于大多数常见的 .NET Core 应用程序，无需这样做。</span><span class="sxs-lookup"><span data-stu-id="f7d65-112">For most common .NET Core applications, you don't need to do this.</span></span>

## <a name="add-a-dependency-by-editing-the-project-file"></a><span data-ttu-id="f7d65-113">通过编辑项目文件添加依赖项</span><span class="sxs-lookup"><span data-stu-id="f7d65-113">Add a dependency by editing the project file</span></span>

<span data-ttu-id="f7d65-114">若要添加依赖项，请在 `<ItemGroup>` 元素内添加 `<PackageReference>` 元素。</span><span class="sxs-lookup"><span data-stu-id="f7d65-114">To add a dependency, add a `<PackageReference>` element inside an `<ItemGroup>` element.</span></span> <span data-ttu-id="f7d65-115">可以添加到现有 `<ItemGroup>`，也可以新建一个元素。</span><span class="sxs-lookup"><span data-stu-id="f7d65-115">You can add to an existing `<ItemGroup>` or create a new one.</span></span> <span data-ttu-id="f7d65-116">下面的示例使用 `dotnet new console` 创建的默认控制台应用程序项目：</span><span class="sxs-lookup"><span data-stu-id="f7d65-116">The following example uses the default console application project that's created by `dotnet new console`:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk.Web">

  <PropertyGroup>
    <TargetFramework>netcoreapp3.1</TargetFramework>
  </PropertyGroup>

  <ItemGroup>
    <PackageReference Include="Microsoft.EntityFrameworkCore" Version="3.1.2" />
  </ItemGroup>

</Project>
```

## <a name="add-a-dependency-by-using-the-cli"></a><span data-ttu-id="f7d65-117">使用 CLI 添加依赖项</span><span class="sxs-lookup"><span data-stu-id="f7d65-117">Add a dependency by using the CLI</span></span>

<span data-ttu-id="f7d65-118">若要添加依赖项，请运行 [dotnet add package](dotnet-add-package.md) 命令，如以下示例中所示：</span><span class="sxs-lookup"><span data-stu-id="f7d65-118">To add a dependency, run the [dotnet add package](dotnet-add-package.md) command, as shown in the following example:</span></span>

```dotnetcli
dotnet add package Microsoft.EntityFrameworkCore
```

## <a name="remove-a-dependency-by-editing-the-project-file"></a><span data-ttu-id="f7d65-119">通过编辑项目文件删除依赖项</span><span class="sxs-lookup"><span data-stu-id="f7d65-119">Remove a dependency by editing the project file</span></span>

<span data-ttu-id="f7d65-120">若要删除依赖项，请从项目文件中删除其 `<PackageReference>` 元素。</span><span class="sxs-lookup"><span data-stu-id="f7d65-120">To remove a dependency, remove its `<PackageReference>` element from the project file.</span></span>

## <a name="remove-a-dependency-by-using-the-cli"></a><span data-ttu-id="f7d65-121">使用 CLI 删除依赖项</span><span class="sxs-lookup"><span data-stu-id="f7d65-121">Remove a dependency by using the CLI</span></span>

<span data-ttu-id="f7d65-122">若要删除依赖项，请运行 [dotnet remove package](dotnet-remove-package.md) 命令，如以下示例中所示：</span><span class="sxs-lookup"><span data-stu-id="f7d65-122">To remove a dependency, run the [dotnet remove package](dotnet-remove-package.md) command, as shown in the following example:</span></span>

```dotnetcli
dotnet remove package Microsoft.EntityFrameworkCore
```

## <a name="see-also"></a><span data-ttu-id="f7d65-123">请参阅</span><span class="sxs-lookup"><span data-stu-id="f7d65-123">See also</span></span>

* [<span data-ttu-id="f7d65-124">项目文件中的包引用</span><span class="sxs-lookup"><span data-stu-id="f7d65-124">Package references in project files</span></span>](../project-sdk/msbuild-props.md#reference-properties-and-items)
* <span data-ttu-id="f7d65-125">[dotnet list package 命令](dotnet-list-package.md)</span><span class="sxs-lookup"><span data-stu-id="f7d65-125">[dotnet list package command](dotnet-list-package.md)</span></span>
