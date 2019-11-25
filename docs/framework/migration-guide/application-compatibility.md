---
title: 运行时和重定向更改 - .NET Framework
ms.date: 10/29/2019
helpviewer_keywords:
- application compatibility
- .NET Framework application compatibility
- .NET Framework changes
ms.assetid: c4ba3ff2-fe59-4c5d-9e0b-86bba3cd865c
ms.openlocfilehash: c46f781d495b87a4f24e77935df7c4814c8567ae
ms.sourcegitcommit: 5a28f8eb071fcc09b045b0c4ae4b96898673192e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2019
ms.locfileid: "73196695"
---
# <a name="application-compatibility-in-the-net-framework"></a><span data-ttu-id="57f0d-102">.NET Framework 中的应用程序兼容性</span><span class="sxs-lookup"><span data-stu-id="57f0d-102">Application compatibility in the .NET Framework</span></span>

<span data-ttu-id="57f0d-103">兼容性是每个 .NET 版本的重要目标。</span><span class="sxs-lookup"><span data-stu-id="57f0d-103">Compatibility is an important goal of each .NET release.</span></span> <span data-ttu-id="57f0d-104">兼容性可确保每个版本都具有累加特征，以便旧版本继续正常使用。</span><span class="sxs-lookup"><span data-stu-id="57f0d-104">Compatibility ensures that each version is additive, so previous versions will continue to work.</span></span> <span data-ttu-id="57f0d-105">然而，更改旧功能（例如，用来提升性能、解决安全性问题或修复 bug 等）可能会导致在更高版本 .NET 上运行的现有代码或应用程序出现兼容性问题。</span><span class="sxs-lookup"><span data-stu-id="57f0d-105">On the other hand, changes to previous functionality (for example, to improve performance, address security issues, or fix bugs) can cause compatibility problems in existing code or existing applications that run under a later version.</span></span>

<span data-ttu-id="57f0d-106">每个应用都通过以下方式面向特定版本的 .NET Framework：</span><span class="sxs-lookup"><span data-stu-id="57f0d-106">Each app targets a specific version of the .NET Framework by:</span></span>

- <span data-ttu-id="57f0d-107">在 Visual Studio 中定义目标框架。</span><span class="sxs-lookup"><span data-stu-id="57f0d-107">Defining a target framework in Visual Studio.</span></span>
- <span data-ttu-id="57f0d-108">在项目文件中指定目标框架。</span><span class="sxs-lookup"><span data-stu-id="57f0d-108">Specifying the target framework in a project file.</span></span>
- <span data-ttu-id="57f0d-109">向源代码应用 <xref:System.Runtime.Versioning.TargetFrameworkAttribute>。</span><span class="sxs-lookup"><span data-stu-id="57f0d-109">Applying a <xref:System.Runtime.Versioning.TargetFrameworkAttribute> to the source code.</span></span>

<span data-ttu-id="57f0d-110">从一个 .NET Framework 版本迁移到另一个版本时，需注意以下两种类型的更改：</span><span class="sxs-lookup"><span data-stu-id="57f0d-110">When migrating from one version of the .NET Framework to another, there are two types of changes to consider:</span></span>

- [<span data-ttu-id="57f0d-111">运行时更改</span><span class="sxs-lookup"><span data-stu-id="57f0d-111">Runtime changes</span></span>](#runtime-changes)
- [<span data-ttu-id="57f0d-112">重定目标更改</span><span class="sxs-lookup"><span data-stu-id="57f0d-112">Retargeting changes</span></span>](#retargeting-changes)

## <a name="runtime-changes"></a><span data-ttu-id="57f0d-113">运行时更改</span><span class="sxs-lookup"><span data-stu-id="57f0d-113">Runtime changes</span></span>

<span data-ttu-id="57f0d-114">运行时问题是指当新的运行时出现在计算机上并且应用的行为更改时出现的问题。</span><span class="sxs-lookup"><span data-stu-id="57f0d-114">Runtime issues are those that arise when a new runtime is placed on a machine and an app's behavior changes.</span></span> <span data-ttu-id="57f0d-115">如果应用在比目标 .NET 版本更高的版本上运行，.NET Framework 会通过怪异的行为来模拟旧版目标版本。 </span><span class="sxs-lookup"><span data-stu-id="57f0d-115">When running on a newer version than what was targeted, the .NET Framework uses *quirked* behavior to mimic the older targeted version.</span></span> <span data-ttu-id="57f0d-116">应用在较高的版本中运行，但其行为方式如同运行于较低版本中一样。</span><span class="sxs-lookup"><span data-stu-id="57f0d-116">The app runs on the newer version but acts as if it's running on the older version.</span></span> <span data-ttu-id="57f0d-117">.NET Framework 各版本之间的许多兼容性问题都是通过这种怪异的模型进行缓解。</span><span class="sxs-lookup"><span data-stu-id="57f0d-117">Many of the compatibility issues between versions of the .NET Framework are mitigated through this quirking model.</span></span> <span data-ttu-id="57f0d-118">例如，如果编译了用于 .NET Framework 4.0 的二进制文件，但在安装了 .NET Framework 4.5 或更高版本的计算机上运行它，它就会采用 .NET Framework 4.0 兼容模式运行。</span><span class="sxs-lookup"><span data-stu-id="57f0d-118">For example, if a binary was compiled for .NET Framework 4.0 but runs on a machine with .NET Framework 4.5 or later, it runs in .NET Framework 4.0 compatibility mode.</span></span> <span data-ttu-id="57f0d-119">这意味着，较高版本中的许多更改不影响此二进制文件。</span><span class="sxs-lookup"><span data-stu-id="57f0d-119">This means that many of the changes in the later version don't affect the binary.</span></span>

<span data-ttu-id="57f0d-120">应用程序面向的 .NET Framework 版本取决于运行代码的应用程序域的输入程序集的目标版本。</span><span class="sxs-lookup"><span data-stu-id="57f0d-120">The version of the .NET Framework that an application targets is determined by the target version of the entry assembly for the application domain that the code runs in.</span></span> <span data-ttu-id="57f0d-121">该应用程序域中加载的所有附加程序集都面向此版本。</span><span class="sxs-lookup"><span data-stu-id="57f0d-121">All additional assemblies loaded in that application domain target that version.</span></span> <span data-ttu-id="57f0d-122">例如，如果是可执行文件，则该可执行文件面向的版本就是一个兼容模式，应用程序域中的所有程序集都在这个兼容模式下运行。</span><span class="sxs-lookup"><span data-stu-id="57f0d-122">For example, in the case of an executable, the version that the executable targets is the compatibility mode all assemblies in that application domain run under.</span></span>

<span data-ttu-id="57f0d-123">如果要查看适用于你的环境的运行时更改列表，请选择当前面向的 .NET Framework 版本，然后选择要迁移到的版本：</span><span class="sxs-lookup"><span data-stu-id="57f0d-123">To see a list of runtime changes that apply to your environment, select the .NET Framework version you're currently targeting and then the version you wish to migrate to:</span></span>

[!INCLUDE[versionselector](../../../includes/migration-guide/runtime/versionselector.md)]

## <a name="retargeting-changes"></a><span data-ttu-id="57f0d-124">重定目标更改</span><span class="sxs-lookup"><span data-stu-id="57f0d-124">Retargeting changes</span></span>

<span data-ttu-id="57f0d-125">重定向更改是指在将程序集重写编译为面向较高版本时发生的更改。</span><span class="sxs-lookup"><span data-stu-id="57f0d-125">Retargeting changes are those that arise when an assembly is recompiled to target a newer version.</span></span> <span data-ttu-id="57f0d-126">面向较高版本意味着程序集会选择加入新功能，同时可能存在与旧功能的兼容性问题。</span><span class="sxs-lookup"><span data-stu-id="57f0d-126">Targeting a newer version means the assembly opts into the new features as well as potential compatibility issues for old features.</span></span>

<span data-ttu-id="57f0d-127">如果要查看适用于你的环境的重定目标更改列表，请选择当前面向的 .NET Framework 版本，然后选择要迁移到的版本：</span><span class="sxs-lookup"><span data-stu-id="57f0d-127">To see a list of retargeting changes that apply to your environment, select the .NET Framework version you're currently targeting and then the version you wish to migrate to:</span></span>

[!INCLUDE[versionselector](../../../includes/migration-guide/retargeting/versionselector.md)]

## <a name="impact-classification"></a><span data-ttu-id="57f0d-128">影响分类</span><span class="sxs-lookup"><span data-stu-id="57f0d-128">Impact classification</span></span>

<span data-ttu-id="57f0d-129">在介绍运行时和重定向更改的主题中（例如，[从 4.7.2 迁移到 4.8 的重定向更改](retargeting/4.7.2-4.8.md)），已根据其预期影响为各项进行了分类，如下所示：</span><span class="sxs-lookup"><span data-stu-id="57f0d-129">In the topics that describe runtime and retargeting changes, for example, [Retargeting changes for migrating from 4.7.2 to 4.8](retargeting/4.7.2-4.8.md), individual items are classified by their expected impact as follows:</span></span>

<span data-ttu-id="57f0d-130">**Major**</span><span class="sxs-lookup"><span data-stu-id="57f0d-130">**Major**</span></span>\
<span data-ttu-id="57f0d-131">显著的更改，可影响大量应用或需要修改大量代码。</span><span class="sxs-lookup"><span data-stu-id="57f0d-131">A significant change that affects a large number of apps or that requires substantial modification of code.</span></span>

<span data-ttu-id="57f0d-132">**Minor**</span><span class="sxs-lookup"><span data-stu-id="57f0d-132">**Minor**</span></span>\
<span data-ttu-id="57f0d-133">影响少量应用或需要修改少量代码的更改。</span><span class="sxs-lookup"><span data-stu-id="57f0d-133">A change that affects a small number of apps or that requires minor modification of code.</span></span>

<span data-ttu-id="57f0d-134">**边缘情况**</span><span class="sxs-lookup"><span data-stu-id="57f0d-134">**Edge case**</span></span>\
<span data-ttu-id="57f0d-135">仅在少数非常特定的情况下影响应用的更改。</span><span class="sxs-lookup"><span data-stu-id="57f0d-135">A change that affects apps under very specific scenarios that are not common.</span></span>

<span data-ttu-id="57f0d-136">**透明**</span><span class="sxs-lookup"><span data-stu-id="57f0d-136">**Transparent**</span></span>\
<span data-ttu-id="57f0d-137">对应用的开发人员或用户没有明显影响的更改。</span><span class="sxs-lookup"><span data-stu-id="57f0d-137">A change that has no noticeable effect on the app's developer or user.</span></span> <span data-ttu-id="57f0d-138">不需要由于此更改而修改应用。</span><span class="sxs-lookup"><span data-stu-id="57f0d-138">The app should not require modification because of this change.</span></span>

## <a name="see-also"></a><span data-ttu-id="57f0d-139">请参阅</span><span class="sxs-lookup"><span data-stu-id="57f0d-139">See also</span></span>

- [<span data-ttu-id="57f0d-140">版本和依赖关系</span><span class="sxs-lookup"><span data-stu-id="57f0d-140">Versions and dependencies</span></span>](versions-and-dependencies.md)
- [<span data-ttu-id="57f0d-141">新增功能</span><span class="sxs-lookup"><span data-stu-id="57f0d-141">What's new</span></span>](../whats-new/index.md)
- [<span data-ttu-id="57f0d-142">过时内容</span><span class="sxs-lookup"><span data-stu-id="57f0d-142">What's obsolete</span></span>](../whats-new/whats-obsolete.md)
