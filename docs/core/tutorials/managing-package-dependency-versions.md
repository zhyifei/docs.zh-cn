---
title: 如何管理 .NET Core 1.0 的包依赖项版本
description: 了解 .NET Core 库和应用的包依赖项版本管理。
author: cartermp
ms.author: mairaw
ms.date: 06/20/2016
ms.openlocfilehash: 96d154f045303e32de606475e77ab2e6b4f7bcda
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33211333"
---
# <a name="how-to-manage-package-dependency-versions-for-net-core-10"></a><span data-ttu-id="08f9d-103">如何管理 .NET Core 1.0 的包依赖项版本</span><span class="sxs-lookup"><span data-stu-id="08f9d-103">How to Manage Package Dependency Versions for .NET Core 1.0</span></span>

<span data-ttu-id="08f9d-104">本文介绍需要了解的 .NET Core 库和应用的包版本信息。</span><span class="sxs-lookup"><span data-stu-id="08f9d-104">This article covers what you need to know about package versions for your .NET Core libraries and apps.</span></span>

## <a name="glossary"></a><span data-ttu-id="08f9d-105">词汇表</span><span class="sxs-lookup"><span data-stu-id="08f9d-105">Glossary</span></span>

<span data-ttu-id="08f9d-106">**修复** - 修复依赖项意味着使用 .NET Core 1.0 NuGet 上发布的相同“系列”的包。</span><span class="sxs-lookup"><span data-stu-id="08f9d-106">**Fix** - Fixing dependencies means you are using the same "family" of packages released on NuGet for .NET Core 1.0.</span></span>

<span data-ttu-id="08f9d-107">**元包** - 表示一组 NuGet 包的 NuGet 包。</span><span class="sxs-lookup"><span data-stu-id="08f9d-107">**Metapackage** - A NuGet package that represents a set of NuGet packages.</span></span>

<span data-ttu-id="08f9d-108">**修整** - 从元包删除不依赖的包的操作。</span><span class="sxs-lookup"><span data-stu-id="08f9d-108">**Trimming** - The act of removing the packages you do not depend on from a metapackage.</span></span>  <span data-ttu-id="08f9d-109">这与 NuGet 包作者有关。</span><span class="sxs-lookup"><span data-stu-id="08f9d-109">This is something relevant for NuGet package authors.</span></span>  <span data-ttu-id="08f9d-110">有关详细信息，请参阅[减少 project.json 的包依赖项](../deploying/reducing-dependencies.md)。</span><span class="sxs-lookup"><span data-stu-id="08f9d-110">See [Reducing Package Dependencies with project.json](../deploying/reducing-dependencies.md) for more information.</span></span> 

## <a name="fix-your-dependencies-to-net-core-10"></a><span data-ttu-id="08f9d-111">将依赖项修复为 .NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="08f9d-111">Fix your dependencies to .NET Core 1.0</span></span>

<span data-ttu-id="08f9d-112">若要可靠地恢复包并编写可靠代码，将依赖项修复为随 .NET Core 1.0 一起提供的包版本，这很重要。</span><span class="sxs-lookup"><span data-stu-id="08f9d-112">To reliably restore packages and write reliable code, it's important that you fix your dependencies to the versions of packages shipping alongside .NET Core 1.0.</span></span>  <span data-ttu-id="08f9d-113">这意味着每个包应具有单个版本，且没有额外的限定符。</span><span class="sxs-lookup"><span data-stu-id="08f9d-113">This means every package should have a single version with no additional qualifiers.</span></span>

<span data-ttu-id="08f9d-114">**已修复为 1.0 的包示例**</span><span class="sxs-lookup"><span data-stu-id="08f9d-114">**Examples of packages fixed to 1.0**</span></span>

`"System.Collections":"4.0.11"`

`"NETStandard.Library":"1.6.0"`

`"Microsoft.NETCore.App":"1.0.0"`

<span data-ttu-id="08f9d-115">**未修复为 1.0 的包示例**</span><span class="sxs-lookup"><span data-stu-id="08f9d-115">**Examples of packages that are NOT fixed to 1.0**</span></span>

`"Microsoft.NETCore.App":"1.0.0-rc4-00454-00"`

`"System.Net.Http":"4.1.0-*"`

`"System.Text.RegularExpressions":"4.0.10-rc3-24021-00"`

### <a name="why-does-this-matter"></a><span data-ttu-id="08f9d-116">为什么这很重要？</span><span class="sxs-lookup"><span data-stu-id="08f9d-116">Why does this matter?</span></span>

<span data-ttu-id="08f9d-117">如果将依赖项修复为随 .NET Core 1.0 一起提供的版本，我们保证这些包都可协同运作。</span><span class="sxs-lookup"><span data-stu-id="08f9d-117">We guarantee that if you fix your dependencies to what ships alongside .NET Core 1.0, those packages will all work together.</span></span> <span data-ttu-id="08f9d-118">如果使用未通过此方式修复的包，则无法做出这种保证。</span><span class="sxs-lookup"><span data-stu-id="08f9d-118">There is no such guarantee if you use packages which aren't fixed in this way.</span></span>

### <a name="scenarios"></a><span data-ttu-id="08f9d-119">方案</span><span class="sxs-lookup"><span data-stu-id="08f9d-119">Scenarios</span></span>

<span data-ttu-id="08f9d-120">虽然所有包及其随 .NET Core 1.0 发布的版本包含在一个大列表中，但如果在某些情况下代码失败，不必逐条查看此列表。</span><span class="sxs-lookup"><span data-stu-id="08f9d-120">Although there is a big list of all packages and their versions released with .NET Core 1.0, you may not have to look through it if your code falls under certain scenarios.</span></span>

<span data-ttu-id="08f9d-121">**是否仅依赖** `NETStandard.Library`**？**</span><span class="sxs-lookup"><span data-stu-id="08f9d-121">**Are you depending only on** `NETStandard.Library`**?**</span></span>

<span data-ttu-id="08f9d-122">如果是，应将 `NETStandard.Library` 包修复为版本 `1.6`。</span><span class="sxs-lookup"><span data-stu-id="08f9d-122">If so, you should fix your `NETStandard.Library` package to version `1.6`.</span></span>  <span data-ttu-id="08f9d-123">由于这是策划元包，也会将其闭包修复为 1.0。</span><span class="sxs-lookup"><span data-stu-id="08f9d-123">Because this is a curated metapackage, its package closure is also fixed to 1.0.</span></span>

<span data-ttu-id="08f9d-124">**是否仅依赖** `Microsoft.NETCore.App`**？**</span><span class="sxs-lookup"><span data-stu-id="08f9d-124">**Are you depending only on** `Microsoft.NETCore.App`**?**</span></span>

<span data-ttu-id="08f9d-125">如果是，应将 `Microsoft.NETCore.App` 包修复为版本 `1.0.0`。</span><span class="sxs-lookup"><span data-stu-id="08f9d-125">If so, you should fix your `Microsoft.NETCore.App` package to version `1.0.0`.</span></span>  <span data-ttu-id="08f9d-126">由于这是策划元包，也会将其闭包修复为 1.0。</span><span class="sxs-lookup"><span data-stu-id="08f9d-126">Because this is a curated metapackage, its package closure is also fixed to 1.0.</span></span>

<span data-ttu-id="08f9d-127">**是否[修整](../deploying/reducing-dependencies.md)** `NETStandard.Library` **或** `Microsoft.NETCore.App` **元包依赖项？**</span><span class="sxs-lookup"><span data-stu-id="08f9d-127">**Are you [trimming](../deploying/reducing-dependencies.md) your** `NETStandard.Library` **or** `Microsoft.NETCore.App` **metapackage dependencies?**</span></span>

<span data-ttu-id="08f9d-128">如果是，应确保开始修整的元包也修复为 1.0。</span><span class="sxs-lookup"><span data-stu-id="08f9d-128">If so, you should ensure that the metapackage you start with is fixed to 1.0.</span></span>  <span data-ttu-id="08f9d-129">修整后依赖的各个包也修复为 1.0。</span><span class="sxs-lookup"><span data-stu-id="08f9d-129">The individual packages you depend on after trimming are also fixed to 1.0.</span></span>

<span data-ttu-id="08f9d-130">**是否依赖** `NETStandard.Library` **或** `Microsoft.NETCore.App` **元包之外的包？**</span><span class="sxs-lookup"><span data-stu-id="08f9d-130">**Are you depending on packages outside the** `NETStandard.Library` **or** `Microsoft.NETCore.App` **metapackages?**</span></span>

<span data-ttu-id="08f9d-131">如果是，需要将其他依赖项修复到 1.0。</span><span class="sxs-lookup"><span data-stu-id="08f9d-131">If so, you need to fix your other dependencies to 1.0.</span></span>  <span data-ttu-id="08f9d-132">请查看本文末尾的正确包版本和生成号。</span><span class="sxs-lookup"><span data-stu-id="08f9d-132">See the correct package versions and build numbers at the end of this article.</span></span>

### <a name="a-note-on-using-a-splat-string--when-versioning"></a><span data-ttu-id="08f9d-133">版本控制时使用 splat 字符串 (\*) 的注释</span><span class="sxs-lookup"><span data-stu-id="08f9d-133">A note on using a splat string (\*) when versioning</span></span>

<span data-ttu-id="08f9d-134">你可能已采用了如下所示使用 splat (\*) 字符串的版本控制模式：`"System.Collections":"4.0.11-*"`。</span><span class="sxs-lookup"><span data-stu-id="08f9d-134">You may have adopted a versioning pattern which uses a splat (\*) string like this: `"System.Collections":"4.0.11-*"`.</span></span>

<span data-ttu-id="08f9d-135">**不应这样做**。</span><span class="sxs-lookup"><span data-stu-id="08f9d-135">**You should not do this**.</span></span>  <span data-ttu-id="08f9d-136">使用 splat 字符串可能会导致从不同的版本恢复包，其中某些版本可能比 .NET Core 1.0 更新。</span><span class="sxs-lookup"><span data-stu-id="08f9d-136">Using the splat string could result in restoring packages from different builds, some of which may be further along than .NET Core 1.0.</span></span>  <span data-ttu-id="08f9d-137">这可能导致某些包不兼容。</span><span class="sxs-lookup"><span data-stu-id="08f9d-137">This could then result in some packages being incompatible.</span></span>

## <a name="packages-and-version-numbers-organized-by-metapackage"></a><span data-ttu-id="08f9d-138">由元包组织的包和版本号</span><span class="sxs-lookup"><span data-stu-id="08f9d-138">Packages and Version Numbers organized by Metapackage</span></span>

<span data-ttu-id="08f9d-139">[所有 .NET Standard 包及其针对 1.0 的版本列表](https://github.com/dotnet/versions/blob/master/build-info/dotnet/corefx/release/1.0.0/Latest_Packages.txt)。</span><span class="sxs-lookup"><span data-stu-id="08f9d-139">[List of all .NET Standard packages and their versions for 1.0](https://github.com/dotnet/versions/blob/master/build-info/dotnet/corefx/release/1.0.0/Latest_Packages.txt).</span></span>

<span data-ttu-id="08f9d-140">[所有运行时包及其针对 1.0 的版本列表](https://github.com/dotnet/versions/blob/master/build-info/dotnet/coreclr/release/1.0.0/LKG_Packages.txt)。</span><span class="sxs-lookup"><span data-stu-id="08f9d-140">[List of all runtime packages and their versions for 1.0](https://github.com/dotnet/versions/blob/master/build-info/dotnet/coreclr/release/1.0.0/LKG_Packages.txt).</span></span>

<span data-ttu-id="08f9d-141">[所有 .NET Core 应用包及其针对 1.0 的版本列表](https://github.com/dotnet/versions/blob/master/build-info/dotnet/core-setup/release/1.0.0/Latest_Packages.txt)。</span><span class="sxs-lookup"><span data-stu-id="08f9d-141">[List of all .NET Core application packages and their versions for 1.0](https://github.com/dotnet/versions/blob/master/build-info/dotnet/core-setup/release/1.0.0/Latest_Packages.txt).</span></span>
