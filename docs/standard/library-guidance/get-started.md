---
title: 开始创建高质量的 .NET 库
description: 开始构建 .NET 库。
author: jamesnk
ms.author: mairaw
ms.date: 10/02/2018
ms.openlocfilehash: 6377e3fe606bf7603b418decdd0e3f9d2de6a510
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/28/2018
ms.locfileid: "50201238"
---
# <a name="get-started"></a><span data-ttu-id="5182a-103">入门</span><span class="sxs-lookup"><span data-stu-id="5182a-103">Get started</span></span>

## <a name="cross-platform-targetingcross-platform-targetingmd"></a>[<span data-ttu-id="5182a-104">跨平台定位</span><span class="sxs-lookup"><span data-stu-id="5182a-104">Cross-platform targeting</span></span>](./cross-platform-targeting.md)

<span data-ttu-id="5182a-105">如何使用 .NET Standard 和多目标来创建跨平台库。</span><span class="sxs-lookup"><span data-stu-id="5182a-105">How to use .NET Standard and multi-targeting to create cross-platform libraries.</span></span> <span data-ttu-id="5182a-106">.NET 可以在许多平台上运行，优秀的 .NET 库应能尽量为尽可能多的平台和开发人员提供支持。</span><span class="sxs-lookup"><span data-stu-id="5182a-106">.NET runs in many places, and good .NET libraries should strive to support as many platforms and developers as possible.</span></span>

## <a name="strong-namingstrong-namingmd"></a>[<span data-ttu-id="5182a-107">强命名</span><span class="sxs-lookup"><span data-stu-id="5182a-107">Strong naming</span></span>](./strong-naming.md)

<span data-ttu-id="5182a-108">了解强命名及其优点和缺点。</span><span class="sxs-lookup"><span data-stu-id="5182a-108">Learn about strong naming and its advantages and disadvantages.</span></span> <span data-ttu-id="5182a-109">对 .NET 库进行强命名可以让大多数开发者使用它，这是推荐的最佳做法。</span><span class="sxs-lookup"><span data-stu-id="5182a-109">Strong naming a .NET library allows the most developers to use it and is a recommended best practice.</span></span>

## <a name="nuget-and-open-source-librariesnugetmd"></a>[<span data-ttu-id="5182a-110">NuGet 和开放源代码库</span><span class="sxs-lookup"><span data-stu-id="5182a-110">NuGet and open-source libraries</span></span>](./nuget.md)

<span data-ttu-id="5182a-111">为开放源代码 .NET 库创建 NuGet 包的最佳方法，包括在 NuGet.org 上公开发布的所有包的推荐元数据。</span><span class="sxs-lookup"><span data-stu-id="5182a-111">The best way to create NuGet packages for open-source .NET libraries, including recommended metadata for all packages published publicly on NuGet.org.</span></span>

### <a name="dependenciesdependenciesmd"></a>[<span data-ttu-id="5182a-112">依赖项</span><span class="sxs-lookup"><span data-stu-id="5182a-112">Dependencies</span></span>](./dependencies.md)

<span data-ttu-id="5182a-113">NuGet 使构建 .NET 库时可以轻松地使用现有包。</span><span class="sxs-lookup"><span data-stu-id="5182a-113">NuGet makes it easy to use existing packages when building a .NET library.</span></span> <span data-ttu-id="5182a-114">了解 NuGet 依赖项的常见冲突来源以及如何避免冲突。</span><span class="sxs-lookup"><span data-stu-id="5182a-114">Learn about NuGet dependencies' common sources of friction and how to avoid them.</span></span>

### <a name="sourcelinksourcelinkmd"></a>[<span data-ttu-id="5182a-115">SourceLink</span><span class="sxs-lookup"><span data-stu-id="5182a-115">SourceLink</span></span>](./sourcelink.md)

<span data-ttu-id="5182a-116">SourceLink 是一个很棒的工具，.NET 库的用户在调试时可以使用它进入其源代码。</span><span class="sxs-lookup"><span data-stu-id="5182a-116">SourceLink is a great tool that allows users of your .NET library to step into its source code while debugging.</span></span> <span data-ttu-id="5182a-117">本文概述了 SourceLink 是什么以及为什么要使用它。</span><span class="sxs-lookup"><span data-stu-id="5182a-117">This article is an overview of what SourceLink is and why you should use it.</span></span>

### <a name="publishingpublish-nuget-packagemd"></a>[<span data-ttu-id="5182a-118">发布</span><span class="sxs-lookup"><span data-stu-id="5182a-118">Publishing</span></span>](./publish-nuget-package.md)

<span data-ttu-id="5182a-119">虽然 NuGet.org 是最广为人知和使用范围最广的存储库，但有很多平台可以发布 NuGet 包。</span><span class="sxs-lookup"><span data-stu-id="5182a-119">While NuGet.org is the most widely known and used repository, there are many places to publish NuGet packages.</span></span> <span data-ttu-id="5182a-120">了解可用的不同 NuGet 包存储库以及发布 .NET 库的安全性最佳做法。</span><span class="sxs-lookup"><span data-stu-id="5182a-120">Learn about the different NuGet package repositories available, and security best practices for publishing a .NET library.</span></span>

## <a name="versioningversioningmd"></a>[<span data-ttu-id="5182a-121">版本控制</span><span class="sxs-lookup"><span data-stu-id="5182a-121">Versioning</span></span>](./versioning.md)

<span data-ttu-id="5182a-122">优秀的 .NET 库可以随着时间的推移不断发展：增加功能、修复 bug 并提高后续版本的性能。</span><span class="sxs-lookup"><span data-stu-id="5182a-122">Good .NET libraries evolve over time, adding features, fixing bugs, and improving performance in later releases.</span></span> <span data-ttu-id="5182a-123">了解各种版本号以及如何向开发人员传达重大更改。</span><span class="sxs-lookup"><span data-stu-id="5182a-123">Learn about the various version numbers and how to communicate breaking changes to developers.</span></span>

### <a name="breaking-changesbreaking-changesmd"></a>[<span data-ttu-id="5182a-124">中断性变更</span><span class="sxs-lookup"><span data-stu-id="5182a-124">Breaking changes</span></span>](./breaking-changes.md)

<span data-ttu-id="5182a-125">对于 .NET 库而言，在现有用户的稳定性与未来的创新之间找到平衡点非常重要。</span><span class="sxs-lookup"><span data-stu-id="5182a-125">It's important for a .NET library to find a balance between stability for existing users and innovation for the future.</span></span> <span data-ttu-id="5182a-126">了解不同类型的重大更改和添加新功能的策略，同时保持向后兼容性。</span><span class="sxs-lookup"><span data-stu-id="5182a-126">Learn about the different kinds of breaking changes and strategies for adding new features while maintaining backwards compatibility.</span></span>

>[!div class="step-by-step"]
<span data-ttu-id="5182a-127">[上一页](./index.md)
[下一页](./cross-platform-targeting.md)</span><span class="sxs-lookup"><span data-stu-id="5182a-127">[Previous](./index.md)
[Next](./cross-platform-targeting.md)</span></span>
