---
title: ".NET Framework 中的应用程序兼容性"
ms.custom: 
ms.date: 05/19/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
- app-compat
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- application compatibility
- .NET Framework application compatibility
- .NET Framework changes
caps.latest.revision: 19
ms.assetid: c4ba3ff2-fe59-4c5d-9e0b-86bba3cd865c
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: b3c7df2984c2c9e8af308ca8070f7207d11ba49e
ms.contentlocale: zh-cn
ms.lasthandoff: 07/28/2017

---

# <a name="application-compatibility-in-the-net-framework"></a><span data-ttu-id="b8e31-102">.NET Framework 中的应用程序兼容性</span><span class="sxs-lookup"><span data-stu-id="b8e31-102">Application Compatibility in the .NET Framework</span></span>

## <a name="introduction"></a><span data-ttu-id="b8e31-103">介绍</span><span class="sxs-lookup"><span data-stu-id="b8e31-103">Introduction</span></span>

<span data-ttu-id="b8e31-104">兼容性是每版 .NET 要实现的非常重要的目标。</span><span class="sxs-lookup"><span data-stu-id="b8e31-104">Compatibility is a very important goal of each .NET release.</span></span> <span data-ttu-id="b8e31-105">兼容性可确保每个版本都具有累加特征，以便旧版本仍能正常使用。</span><span class="sxs-lookup"><span data-stu-id="b8e31-105">Compatibility ensures that each version is additive, so previous versions will still work.</span></span> <span data-ttu-id="b8e31-106">然而，更改旧功能（以便提升性能、解决安全问题或修复 bug）可能会导致在更高版本 .NET 上运行的现有代码或应用出现兼容性问题。</span><span class="sxs-lookup"><span data-stu-id="b8e31-106">On the other hand, changes to previous functionality (to improve performance, address security issues, or fix bugs) can cause compatibility problems in existing code or existing applications that run under a later version.</span></span> <span data-ttu-id="b8e31-107">.NET Framework 可识别重定目标更改和运行时更改。</span><span class="sxs-lookup"><span data-stu-id="b8e31-107">The .NET Framework recognizes retargeting changes and runtime changes.</span></span> <span data-ttu-id="b8e31-108">重定目标更改会影响定位特定版本的 .NET Framework、但在更高版本 .NET 上运行的应用。</span><span class="sxs-lookup"><span data-stu-id="b8e31-108">Retargeting changes affect applications that target a specific version of the .NET Framework but are running on a later version.</span></span> <span data-ttu-id="b8e31-109">运行时更改会影响在特定版本 .NET 上运行的所有应用。</span><span class="sxs-lookup"><span data-stu-id="b8e31-109">Runtime changes affect all applications running on a particular version.</span></span>

<span data-ttu-id="b8e31-110">每个应用都定位特定版本的 .NET Framework，这可以通过下列方式指定：</span><span class="sxs-lookup"><span data-stu-id="b8e31-110">Each app targets a specific version of the .NET Framework, which can be specified by:</span></span>

- <span data-ttu-id="b8e31-111">在 Visual Studio 中定义目标框架。</span><span class="sxs-lookup"><span data-stu-id="b8e31-111">Defining a target framework in Visual Studio.</span></span>
- <span data-ttu-id="b8e31-112">在项目文件中指定目标框架。</span><span class="sxs-lookup"><span data-stu-id="b8e31-112">Specifying the target framework in a project file.</span></span>
- <span data-ttu-id="b8e31-113">向源代码应用 <xref:System.Runtime.Versioning.TargetFrameworkAttribute>。</span><span class="sxs-lookup"><span data-stu-id="b8e31-113">Applying a <xref:System.Runtime.Versioning.TargetFrameworkAttribute> to the source code.</span></span>

<span data-ttu-id="b8e31-114">如果应用在比目标 .NET 版本更高的版本上运行，.NET Framework 会通过怪异的行为来模拟旧版目标版本。</span><span class="sxs-lookup"><span data-stu-id="b8e31-114">When running on a newer version than what was targeted, the .NET Framework will use quirked behavior to mimic the older targeted version.</span></span> <span data-ttu-id="b8e31-115">也就是说，应用虽然在更高版本的 Framework 上运行，但行为就像在旧版本 .NET 上运行一样。</span><span class="sxs-lookup"><span data-stu-id="b8e31-115">In other words, the app will run on the newer version of the Framework, but act as if it's running on the older version.</span></span> <span data-ttu-id="b8e31-116">.NET Framework 各版本之间的许多兼容性问题都是通过这种怪异的模型进行缓解。</span><span class="sxs-lookup"><span data-stu-id="b8e31-116">Many of the compatibility issues between versions of the .NET Framework are mitigated through this quirking model.</span></span>

## <a name="runtime-changes"></a><span data-ttu-id="b8e31-117">运行时更改</span><span class="sxs-lookup"><span data-stu-id="b8e31-117">Runtime changes</span></span>

<span data-ttu-id="b8e31-118">运行时问题是指当新的运行时出现在计算机上、运行的二进制文件相同、但行为不同时出现的问题。</span><span class="sxs-lookup"><span data-stu-id="b8e31-118">Runtime issues are those that arise when a new runtime is placed on a machine and the same binaries are run, but different behavior is seen.</span></span> <span data-ttu-id="b8e31-119">如果二进制文件的编译目标为 .NET Framework 4.0，它将在 4.5 或更高版本上的 .NET Framework 4.0 兼容性模式下运行。</span><span class="sxs-lookup"><span data-stu-id="b8e31-119">If a binary was compiled for .NET Framework 4.0 it will run in .NET Framework 4.0 compatibility mode on 4.5 or later versions.</span></span> <span data-ttu-id="b8e31-120">许多影响 4.5 的更改将不会影响编译目标为 4.0 的二进制文件。</span><span class="sxs-lookup"><span data-stu-id="b8e31-120">Many of the changes that affect 4.5 will not affect a binary compiled for 4.0.</span></span> <span data-ttu-id="b8e31-121">这是 AppDomain 才会出现的问题，具体视输入程序集的设置而定。</span><span class="sxs-lookup"><span data-stu-id="b8e31-121">This is specific to the AppDomain and depends on the settings of the entry assembly.</span></span>

## <a name="retargeting-changes"></a><span data-ttu-id="b8e31-122">重定目标更改</span><span class="sxs-lookup"><span data-stu-id="b8e31-122">Retargeting changes</span></span>

<span data-ttu-id="b8e31-123">重定目标问题是指当原本定位 4.0 的程序集现在设为定位 4.5 时出现的问题。</span><span class="sxs-lookup"><span data-stu-id="b8e31-123">Retargeting issues are those that arise when an assembly that was targeting 4.0 is now set to target 4.5.</span></span> <span data-ttu-id="b8e31-124">此时，程序集启用新功能，并存在与旧功能的潜在兼容性问题。</span><span class="sxs-lookup"><span data-stu-id="b8e31-124">Now the assembly opts into the new features as well as potential compatibility issues to old features.</span></span> <span data-ttu-id="b8e31-125">再强调一遍，这取决于输入程序集，同样也取决于使用此程序集的控制台应用或引用此程序集的网站。</span><span class="sxs-lookup"><span data-stu-id="b8e31-125">Again, this is dictated by the entry assembly, so the console app that uses the assembly, or the website that references the assembly.</span></span>

## <a name="net-compatibility-diagnostics"></a><span data-ttu-id="b8e31-126">.NET 兼容性诊断</span><span class="sxs-lookup"><span data-stu-id="b8e31-126">.NET Compatibility Diagnostics</span></span>

<span data-ttu-id="b8e31-127">.NET 兼容性诊断是 Roslyn 提供技术支持的分析器，有助于确定 .NET Framework 不同版本之间的应用程序兼容性问题。</span><span class="sxs-lookup"><span data-stu-id="b8e31-127">The .NET Compatibility Diagnostics are Roslyn-powered analyzers that help identify application compatibility issues between versions of the .NET Framework.</span></span> <span data-ttu-id="b8e31-128">此列表包含所有可用的分析器，尽管仅部分分析器适用于任何具体的迁移。</span><span class="sxs-lookup"><span data-stu-id="b8e31-128">This list contains all of the analyzers available, although only a subset will apply to any specific migration.</span></span> <span data-ttu-id="b8e31-129">这些分析器可确定计划迁移会发生的问题，并仅显示这些问题。</span><span class="sxs-lookup"><span data-stu-id="b8e31-129">The analyzers will determine which issues are applicable for the planned migration and will only surface those.</span></span>

<span data-ttu-id="b8e31-130">每个问题包含以下信息：</span><span class="sxs-lookup"><span data-stu-id="b8e31-130">Each issue includes the following information:</span></span>

-   <span data-ttu-id="b8e31-131">从以前版本发生的更改的介绍。</span><span class="sxs-lookup"><span data-stu-id="b8e31-131">The description of what has changed from a previous version.</span></span>

-   <span data-ttu-id="b8e31-132">更改对客户造成了哪些影响，以及是否有任何解决办法可以保持各版本的兼容性。</span><span class="sxs-lookup"><span data-stu-id="b8e31-132">How the change affects customers and whether any workarounds are available to preserve compatibility across versions.</span></span>

-   <span data-ttu-id="b8e31-133">对于更改重要性的评估。</span><span class="sxs-lookup"><span data-stu-id="b8e31-133">An assessment of how important the change is.</span></span> <span data-ttu-id="b8e31-134">应用程序兼容性问题可分成以下几类：</span><span class="sxs-lookup"><span data-stu-id="b8e31-134">Application compatibility issue are categorized as follows:</span></span>

    |   |   |
    |---|---|
    |<span data-ttu-id="b8e31-135">主要</span><span class="sxs-lookup"><span data-stu-id="b8e31-135">Major</span></span>|<span data-ttu-id="b8e31-136">影响大量应用或需要修改大量代码的重大更改。</span><span class="sxs-lookup"><span data-stu-id="b8e31-136">A significant change that affects a large number of apps or requires substantial modification of code.</span></span>|
    |<span data-ttu-id="b8e31-137">次要</span><span class="sxs-lookup"><span data-stu-id="b8e31-137">Minor</span></span>|<span data-ttu-id="b8e31-138">影响少量应用或需要修改少量代码的更改。</span><span class="sxs-lookup"><span data-stu-id="b8e31-138">A change that affects a small number of apps or that requires minor modification of code.</span></span>|
    |<span data-ttu-id="b8e31-139">边缘情况</span><span class="sxs-lookup"><span data-stu-id="b8e31-139">Edge case</span></span>|<span data-ttu-id="b8e31-140">在极少数特定的情况下影响应用的更改。</span><span class="sxs-lookup"><span data-stu-id="b8e31-140">A change that affects apps under very specific, uncommon scenarios.</span></span>|
    |<span data-ttu-id="b8e31-141">透明</span><span class="sxs-lookup"><span data-stu-id="b8e31-141">Transparent</span></span>|<span data-ttu-id="b8e31-142">对应用开发者或用户没有造成显著影响的更改。</span><span class="sxs-lookup"><span data-stu-id="b8e31-142">A change with no noticeable effect on the application's developer or user.</span></span>|

-   <span data-ttu-id="b8e31-143">版本指示了更改首次出现在框架中的时间。</span><span class="sxs-lookup"><span data-stu-id="b8e31-143">Version indicates when the change first appears in the framework.</span></span> <span data-ttu-id="b8e31-144">某些更改会在特定版本中引入，并在以后的版本中进行还原；这也会在版本中指出。</span><span class="sxs-lookup"><span data-stu-id="b8e31-144">Some of the changes are introduced in a particular version and reverted in a later version; that is indicated as well.</span></span>

-   <span data-ttu-id="b8e31-145">更改类型：</span><span class="sxs-lookup"><span data-stu-id="b8e31-145">The type of change:</span></span>

    |   |   |
    |---|---|
    |<span data-ttu-id="b8e31-146">重定目标</span><span class="sxs-lookup"><span data-stu-id="b8e31-146">Retargeting</span></span>|<span data-ttu-id="b8e31-147">更改会影响重新编译以面向新版 .NET Framework 的应用。</span><span class="sxs-lookup"><span data-stu-id="b8e31-147">The change affects apps that are recompiled to target a new version of the .NET Framework.</span></span>|
    |<span data-ttu-id="b8e31-148">运行时</span><span class="sxs-lookup"><span data-stu-id="b8e31-148">Runtime</span></span>|<span data-ttu-id="b8e31-149">更改会影响面向以前版本的 .NET Framework 但在更高版本上运行的现有应用。</span><span class="sxs-lookup"><span data-stu-id="b8e31-149">The change affects an existing app that targets a previous version of the .NET Framework but runs on a later version.</span></span>|

-   <span data-ttu-id="b8e31-150">受影响的 API（如果有）。</span><span class="sxs-lookup"><span data-stu-id="b8e31-150">The affected APIS, if any.</span></span>

-   <span data-ttu-id="b8e31-151">可用诊断的 ID</span><span class="sxs-lookup"><span data-stu-id="b8e31-151">The IDs of the available diagnostics</span></span>

## <a name="usage"></a><span data-ttu-id="b8e31-152">用法</span><span class="sxs-lookup"><span data-stu-id="b8e31-152">Usage</span></span>

<span data-ttu-id="b8e31-153">首先，从下面选择一种兼容性更改类型：</span><span class="sxs-lookup"><span data-stu-id="b8e31-153">To begin, select the type of compatibility change below:</span></span>

- [<span data-ttu-id="b8e31-154">重定目标更改</span><span class="sxs-lookup"><span data-stu-id="b8e31-154">Retargeting Changes</span></span>](./retargeting/index.md)
- [<span data-ttu-id="b8e31-155">运行时更改</span><span class="sxs-lookup"><span data-stu-id="b8e31-155">Runtime Changes</span></span>](./runtime/index.md)


## <a name="see-also"></a><span data-ttu-id="b8e31-156">请参阅</span><span class="sxs-lookup"><span data-stu-id="b8e31-156">See also</span></span>

<span data-ttu-id="b8e31-157">[版本和依赖关系](../../../docs/framework/migration-guide/versions-and-dependencies.md) </span><span class="sxs-lookup"><span data-stu-id="b8e31-157">[Versions and Dependencies](../../../docs/framework/migration-guide/versions-and-dependencies.md) </span></span>  
<span data-ttu-id="b8e31-158">[新增功能](../../../docs/framework/whats-new/index.md) </span><span class="sxs-lookup"><span data-stu-id="b8e31-158">[What's New](../../../docs/framework/whats-new/index.md) </span></span>  
[<span data-ttu-id="b8e31-159">类库中过时的内容</span><span class="sxs-lookup"><span data-stu-id="b8e31-159">What's Obsolete in the Class Library</span></span>](../../../docs/framework/whats-new/whats-obsolete.md)

