---
title: .NET Core 支持
description: 了解 .NET Core 不同版本系列（LTS 和当前版本）支持
author: kendrahavens
ms.author: mairaw
ms.date: 01/30/2017
ms.topic: conceptual
ms.prod: dotnet-core
ms.devlang: dotnet
ms.workload:
- dotnetcore
ms.openlocfilehash: 8bb2cd1895513ca2d895aa45671cb341193d2359
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2018
---
# <a name="net-core-support"></a><span data-ttu-id="5a4aa-103">.NET Core 支持</span><span class="sxs-lookup"><span data-stu-id="5a4aa-103">.NET Core Support</span></span>

<span data-ttu-id="5a4aa-104">本文概述了 .NET Core 支持。</span><span class="sxs-lookup"><span data-stu-id="5a4aa-104">This is a general description of .NET Core support.</span></span>

## <a name="lts-and-current-release-trains"></a><span data-ttu-id="5a4aa-105">LTS 和当前版本系列</span><span class="sxs-lookup"><span data-stu-id="5a4aa-105">LTS and Current Release Trains</span></span>

<span data-ttu-id="5a4aa-106">提供两个支持版本系列是整个软件领域的一个常见概念，特别是对于开放源代码项目（如 .NET Core）。</span><span class="sxs-lookup"><span data-stu-id="5a4aa-106">Having two support release trains is a common concept in use throughout the software world, specially for open-source projects like .NET Core.</span></span> <span data-ttu-id="5a4aa-107">.NET Core 提供以下支持版本系列：[长期支持 (LTS)](https://en.wikipedia.org/wiki/Long-term_support) 和当前版本。</span><span class="sxs-lookup"><span data-stu-id="5a4aa-107">.NET Core has the following support release trains: [Long Term Support (LTS)](https://en.wikipedia.org/wiki/Long-term_support) and Current.</span></span> <span data-ttu-id="5a4aa-108">维护 LTS 版本是为了在生命周期内确保稳定性，同时接收重要问题的修补程序和安全修补程序。</span><span class="sxs-lookup"><span data-stu-id="5a4aa-108">LTS releases are maintained for stability over their lifecycle, receiving fixes for important issues and security fixes.</span></span> <span data-ttu-id="5a4aa-109">不同的是，当前版本包含新功能和附加 bug 修补程序。</span><span class="sxs-lookup"><span data-stu-id="5a4aa-109">New feature work and additional bug fixes take place in Current releases.</span></span> <span data-ttu-id="5a4aa-110">从支持角度来看，这些版本系列具有以下支持生命周期特性。</span><span class="sxs-lookup"><span data-stu-id="5a4aa-110">From a support perspective, these release trains have the following support lifecycle attributes.</span></span>

<span data-ttu-id="5a4aa-111">LTS 版本</span><span class="sxs-lookup"><span data-stu-id="5a4aa-111">LTS releases are</span></span>
* <span data-ttu-id="5a4aa-112">自 LTS 版本发布之日起的三年内可获得支持</span><span class="sxs-lookup"><span data-stu-id="5a4aa-112">Supported for three years after the general availability date of a LTS release</span></span>
* <span data-ttu-id="5a4aa-113">或者，自后续 LTS 版本发布之日起的一年内可获得支持</span><span class="sxs-lookup"><span data-stu-id="5a4aa-113">Or one year after the general availability of a subsequent LTS release</span></span>

<span data-ttu-id="5a4aa-114">当前版本</span><span class="sxs-lookup"><span data-stu-id="5a4aa-114">Current releases are</span></span>
* <span data-ttu-id="5a4aa-115">与父 LTS 版本一样，在三年内可获得支持</span><span class="sxs-lookup"><span data-stu-id="5a4aa-115">Supported within the same three-year window as the parent LTS release</span></span>
* <span data-ttu-id="5a4aa-116">自后续当前版本发布之日起的三个月内可获得支持</span><span class="sxs-lookup"><span data-stu-id="5a4aa-116">Supported for three months after the general availability of a subsequent Current release</span></span>
* <span data-ttu-id="5a4aa-117">自后续 LTS 版本发布之日起的一年内可获得支持</span><span class="sxs-lookup"><span data-stu-id="5a4aa-117">And one year after the general availability of a subsequent LTS release</span></span>

## <a name="versioning"></a><span data-ttu-id="5a4aa-118">版本管理</span><span class="sxs-lookup"><span data-stu-id="5a4aa-118">Versioning</span></span>
<span data-ttu-id="5a4aa-119">若有新 LTS 版本，主版本号会递增。</span><span class="sxs-lookup"><span data-stu-id="5a4aa-119">New LTS releases are marked by an increase in the Major version number.</span></span> <span data-ttu-id="5a4aa-120">当前版本的主版本号与相应的 LTS 系列相同，但次要版本号会递增。</span><span class="sxs-lookup"><span data-stu-id="5a4aa-120">Current releases have the same Major number as the corresponding LTS train and are marked by an increase in the Minor version number.</span></span> <span data-ttu-id="5a4aa-121">例如，1.0.3 表示 LTS，1.1.0 表示当前版本。</span><span class="sxs-lookup"><span data-stu-id="5a4aa-121">For example, 1.0.3 would be LTS and 1.1.0 would be Current.</span></span> <span data-ttu-id="5a4aa-122">若有 bug 修补程序更新，要么系列会递增，要么修补程序版本号会递增。</span><span class="sxs-lookup"><span data-stu-id="5a4aa-122">Bug fix updates to either train increment the Patch version.</span></span> <span data-ttu-id="5a4aa-123">有关版本控制方案的详细信息，请参阅 [.NET Core 版本控制](index.md)。</span><span class="sxs-lookup"><span data-stu-id="5a4aa-123">For more information on the versioning scheme, see [.NET Core Versioning](index.md).</span></span>

## <a name="what-causes-updates-in-lts-and-current-trains"></a><span data-ttu-id="5a4aa-124">什么因素会导致 LTS 和当前版本系列发生更新？</span><span class="sxs-lookup"><span data-stu-id="5a4aa-124">What causes updates in LTS and Current trains?</span></span>
<span data-ttu-id="5a4aa-125">若要了解哪些特定更改（如 bug 修补程序或附加 API）会导致版本号发生更新，请查看[版本控制文档](index.md)中的“决策树”部分。</span><span class="sxs-lookup"><span data-stu-id="5a4aa-125">To understand what specific changes, such as bug fixes or the addition of APIs, cause updates to the version numbers review the Decision Tree section in the [Versioning Documentation](index.md).</span></span> <span data-ttu-id="5a4aa-126">决定要将哪些更改从当前版本拉取到 LTS 版本中时，没有一系列的黄金规则。</span><span class="sxs-lookup"><span data-stu-id="5a4aa-126">There is not a golden set of rules that decide what changes are pulled into the LTS branch from Current.</span></span> <span data-ttu-id="5a4aa-127">通常情况下，必要的安全更新程序和修复预期行为的修补程序会导致 LTS 版本发生更新。</span><span class="sxs-lookup"><span data-stu-id="5a4aa-127">Typically, necessary security updates and patches that fix expected behaviour are reasons to update the LTS branch.</span></span> <span data-ttu-id="5a4aa-128">我们还打算在 LTS 版本中支持最新的桌面开发者操作系统，尽管这不是总能实现。</span><span class="sxs-lookup"><span data-stu-id="5a4aa-128">We also intend to support recent desktop developer operating systems on the LTS branch, though this may not always be possible.</span></span> <span data-ttu-id="5a4aa-129">若要及时了解特定版本中支持哪些 API、修补程序和操作系统，一种很好的方式是在 GitHub 上参阅其[版本说明](https://github.com/dotnet/core/tree/master/release-notes)。</span><span class="sxs-lookup"><span data-stu-id="5a4aa-129">A good way to catch up on what APIs, fixes, and operating systems are supported in a certain release is to browse its [release notes](https://github.com/dotnet/core/tree/master/release-notes) on GitHub.</span></span>

### <a name="further-reading"></a><span data-ttu-id="5a4aa-130">其他阅读材料</span><span class="sxs-lookup"><span data-stu-id="5a4aa-130">Further Reading</span></span>
* [<span data-ttu-id="5a4aa-131">.NET Core 支持生命周期简报</span><span class="sxs-lookup"><span data-stu-id="5a4aa-131">.NET Core Support Lifecycle Fact Sheet</span></span>](https://www.microsoft.com/net/core/support)
* [<span data-ttu-id="5a4aa-132">当前支持的操作系统和版本</span><span class="sxs-lookup"><span data-stu-id="5a4aa-132">Currently supported operating systems and versions</span></span>](https://github.com/dotnet/core/blob/master/roadmap.md)
