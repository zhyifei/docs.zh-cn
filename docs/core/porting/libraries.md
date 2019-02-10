---
title: 将库移植到 .NET Core
description: 了解如何将 .NET Framework 中的库项目移植到 .NET Core。
author: cartermp
ms.date: 12/7/2018
ms.custom: seodec18
ms.openlocfilehash: 8190dcfd3ffed9051c7724752a19d88e7bef4f4d
ms.sourcegitcommit: c6f69b0cf149f6b54483a6d5c2ece222913f43ce
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/08/2019
ms.locfileid: "55904703"
---
# <a name="port-net-framework-libraries-to-net-core"></a><span data-ttu-id="c3cff-103">将 .NET Framework 库移植到 .NET Core</span><span class="sxs-lookup"><span data-stu-id="c3cff-103">Port .NET Framework libraries to .NET Core</span></span>

<span data-ttu-id="c3cff-104">了解如何将 .NET Framework 库代码移植到 .NET Core，以跨平台运行并扩展使用该代码的应用的范围。</span><span class="sxs-lookup"><span data-stu-id="c3cff-104">Learn how to port .NET Framework library code to .NET Core, to run cross-platform and expand the reach of the apps that use it.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="c3cff-105">系统必备</span><span class="sxs-lookup"><span data-stu-id="c3cff-105">Prerequisites</span></span>

<span data-ttu-id="c3cff-106">本文假定你：</span><span class="sxs-lookup"><span data-stu-id="c3cff-106">This article assumes that you:</span></span>

- <span data-ttu-id="c3cff-107">正在使用 Visual Studio 2017 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="c3cff-107">Are using Visual Studio 2017 or later.</span></span>
  - <span data-ttu-id="c3cff-108">Visual Studio 的早期版本不支持 .NET Core</span><span class="sxs-lookup"><span data-stu-id="c3cff-108">.NET Core isn't supported on earlier versions of Visual Studio</span></span>
- <span data-ttu-id="c3cff-109">了解[推荐的移植过程](index.md)。</span><span class="sxs-lookup"><span data-stu-id="c3cff-109">Understand the [recommended porting process](index.md).</span></span>
- <span data-ttu-id="c3cff-110">已解决与[第三方依赖项](third-party-deps.md)有关的任何问题。</span><span class="sxs-lookup"><span data-stu-id="c3cff-110">Have resolved any issues with [third-party dependencies](third-party-deps.md).</span></span>

<span data-ttu-id="c3cff-111">还应熟悉下列主题的内容：</span><span class="sxs-lookup"><span data-stu-id="c3cff-111">You should also become familiar with the content of the following topics:</span></span>

<span data-ttu-id="c3cff-112">[.NET Standard](~/docs/standard/net-standard.md) </span><span class="sxs-lookup"><span data-stu-id="c3cff-112">[.NET Standard](~/docs/standard/net-standard.md) </span></span>  
<span data-ttu-id="c3cff-113">此主题介绍了适用于所有 .NET 实现代码的 .NET API 正式规范。</span><span class="sxs-lookup"><span data-stu-id="c3cff-113">This topic describes the formal specification of .NET APIs that are intended to be available on all .NET implementations.</span></span>

<span data-ttu-id="c3cff-114">[包、元包和框架](~/docs/core/packages.md) </span><span class="sxs-lookup"><span data-stu-id="c3cff-114">[Packages, Metapackages and Frameworks](~/docs/core/packages.md) </span></span>  
<span data-ttu-id="c3cff-115">这篇文章介绍了 .NET Core 如何定义和使用包，以及包如何支持多个 .NET 实现代码。</span><span class="sxs-lookup"><span data-stu-id="c3cff-115">This article discusses how .NET Core defines and uses packages and how packages support code running on multiple .NET implementations.</span></span>

<span data-ttu-id="c3cff-116">[使用跨平台工具开发库](~/docs/core/tutorials/libraries.md) </span><span class="sxs-lookup"><span data-stu-id="c3cff-116">[Developing Libraries with Cross Platform Tools](~/docs/core/tutorials/libraries.md) </span></span>  
<span data-ttu-id="c3cff-117">此主题介绍了如何使用跨平台 CLI 工具编写 .NET 的库。</span><span class="sxs-lookup"><span data-stu-id="c3cff-117">This topic explains how to write libraries for .NET using cross-platform CLI tools.</span></span>

<span data-ttu-id="c3cff-118">[.NET Core 的 csproj 格式的新增内容](~/docs/core/tools/csproj.md) </span><span class="sxs-lookup"><span data-stu-id="c3cff-118">[Additions to the *csproj* format for .NET Core](~/docs/core/tools/csproj.md) </span></span>  
<span data-ttu-id="c3cff-119">本文概述了作为从移动到 csproj 和 MSBuild 的一部分，添加到项目文件的更改。</span><span class="sxs-lookup"><span data-stu-id="c3cff-119">This article outlines the changes that were added to the project file as part of the move to *csproj* and MSBuild.</span></span>

<span data-ttu-id="c3cff-120">[移植到 .NET Core - 分析第三方依赖项](~/docs/core/porting/third-party-deps.md) </span><span class="sxs-lookup"><span data-stu-id="c3cff-120">[Porting to .NET Core - Analyzing your Third-Party Party Dependencies](~/docs/core/porting/third-party-deps.md) </span></span>  
<span data-ttu-id="c3cff-121">本主题介绍了第三方依赖项的可移植性及 NuGet 包依赖项无法在 .NET Core 上运行时要执行的操作。</span><span class="sxs-lookup"><span data-stu-id="c3cff-121">This topic discusses the portability of third-party dependencies and what to do when a NuGet package dependency doesn't run on .NET Core.</span></span>

## <a name="retargeting-your-net-framework-code-to-net-framework-472"></a><span data-ttu-id="c3cff-122">将 .NET Framework 代码重定向到 .NET Framework 4.7.2</span><span class="sxs-lookup"><span data-stu-id="c3cff-122">Retargeting your .NET Framework code to .NET Framework 4.7.2</span></span>

<span data-ttu-id="c3cff-123">如果代码不面向 .NET Framework 4.7.2，建议重定向到 .NET Framework 4.7.2。</span><span class="sxs-lookup"><span data-stu-id="c3cff-123">If your code isn't targeting .NET Framework 4.7.2, we recommended that you retarget to .NET Framework 4.7.2.</span></span> <span data-ttu-id="c3cff-124">在 .NET Standard 不支持现有 API 情况下，这可确保最新备用 API 的可用性。</span><span class="sxs-lookup"><span data-stu-id="c3cff-124">This ensures the availability of the latest API alternatives for cases where the .NET Standard doesn't support existing APIs.</span></span>

<span data-ttu-id="c3cff-125">对于 Visual Studio 中每个想要移植的项目，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="c3cff-125">For each of your projects in Visual Studio you wish to port, do the following:</span></span>

1. <span data-ttu-id="c3cff-126">右键单击该项目，然后选择“属性”。</span><span class="sxs-lookup"><span data-stu-id="c3cff-126">Right-click on the project and select **Properties**.</span></span>
1. <span data-ttu-id="c3cff-127">在“目标框架”下拉列表中，选择“.NET Framework 4.7.2”。</span><span class="sxs-lookup"><span data-stu-id="c3cff-127">In the **Target Framework** dropdown, select **.NET Framework 4.7.2**.</span></span>
1. <span data-ttu-id="c3cff-128">重新编译项目。</span><span class="sxs-lookup"><span data-stu-id="c3cff-128">Recompile your projects.</span></span>

<span data-ttu-id="c3cff-129">因为项目现在面向 .NET Framework 4.7.2，因此可使用该版本的 .NET Framework 作为移植代码的基准。</span><span class="sxs-lookup"><span data-stu-id="c3cff-129">Because your projects now target .NET Framework 4.7.2, use that version of the .NET Framework as your base for porting code.</span></span>

## <a name="determining-the-portability-of-your-code"></a><span data-ttu-id="c3cff-130">确定代码的可移植性</span><span class="sxs-lookup"><span data-stu-id="c3cff-130">Determining the portability of your code</span></span>

<span data-ttu-id="c3cff-131">下一步是运行 API 可移植性分析器 (ApiPort) 生成可供分析的可移植性报表。</span><span class="sxs-lookup"><span data-stu-id="c3cff-131">The next step is to run the API Portability Analyzer (ApiPort) to generate a portability report for analysis.</span></span>

<span data-ttu-id="c3cff-132">确保了解 [API 可移植性分析器 (ApiPort)](../../standard/analyzers/portability-analyzer.md) 及如何生成用于面向 .NET Core 的可移植性报表。</span><span class="sxs-lookup"><span data-stu-id="c3cff-132">Make sure you understand the [API Portability Analyzer (ApiPort)](../../standard/analyzers/portability-analyzer.md) and how to generate portability reports for targeting .NET Core.</span></span> <span data-ttu-id="c3cff-133">执行此操作的方式可能取决于需求和个人偏好。</span><span class="sxs-lookup"><span data-stu-id="c3cff-133">How you do this likely varies based on your needs and personal tastes.</span></span> <span data-ttu-id="c3cff-134">下面介绍了一些不同方法。</span><span class="sxs-lookup"><span data-stu-id="c3cff-134">What follows are a few different approaches.</span></span> <span data-ttu-id="c3cff-135">用户可能会发现自己根据生成代码的方式混合使用了这些方法中的步骤。</span><span class="sxs-lookup"><span data-stu-id="c3cff-135">You may find yourself mixing steps of these approaches depending on how your code is structured.</span></span>

### <a name="dealing-primarily-with-the-compiler"></a><span data-ttu-id="c3cff-136">主要处理编译器</span><span class="sxs-lookup"><span data-stu-id="c3cff-136">Dealing primarily with the compiler</span></span>

<span data-ttu-id="c3cff-137">此方法可能最适合小项目或不会用很多 .NET Framework API 的项目。</span><span class="sxs-lookup"><span data-stu-id="c3cff-137">This approach may be the best for small projects or projects which don't use many .NET Framework APIs.</span></span> <span data-ttu-id="c3cff-138">此方法很简单：</span><span class="sxs-lookup"><span data-stu-id="c3cff-138">The approach is simple:</span></span>

1. <span data-ttu-id="c3cff-139">可选择在项目上运行 ApiPort。</span><span class="sxs-lookup"><span data-stu-id="c3cff-139">Optionally, run ApiPort on your project.</span></span> <span data-ttu-id="c3cff-140">若运行 ApiPort，则从报告获取有关需要解决的问题的信息。</span><span class="sxs-lookup"><span data-stu-id="c3cff-140">If you run ApiPort, gain knowledge from the report on issues you'll need to address.</span></span>
1. <span data-ttu-id="c3cff-141">将所有代码复制到新的 .NET Core 项目。</span><span class="sxs-lookup"><span data-stu-id="c3cff-141">Copy all of your code over into a new .NET Core project.</span></span>
1. <span data-ttu-id="c3cff-142">查看可移植性报表（如果已生成）时，解决编译器错误，直至项目完全得到编译。</span><span class="sxs-lookup"><span data-stu-id="c3cff-142">While referring to the portability report (if generated), solve compiler errors until the project fully compiles.</span></span>

<span data-ttu-id="c3cff-143">尽管这种方法非常松散，但以代码为中心的方法通常可快速解决问题，并且可能是最适合小型项目或库的方法。</span><span class="sxs-lookup"><span data-stu-id="c3cff-143">Although this approach is unstructured, the code-focused approach often leads to resolving issues quickly and might be the best approach for smaller projects or libraries.</span></span> <span data-ttu-id="c3cff-144">只包含数据模型的项目可能是此方法的理想选择。</span><span class="sxs-lookup"><span data-stu-id="c3cff-144">A project that contains only data models might be an ideal candidate for this approach.</span></span>

### <a name="staying-on-the-net-framework-until-portability-issues-are-resolved"></a><span data-ttu-id="c3cff-145">可移植性问题得到解决前停留在 .NET Framework 上</span><span class="sxs-lookup"><span data-stu-id="c3cff-145">Staying on the .NET Framework until portability issues are resolved</span></span>

<span data-ttu-id="c3cff-146">如果更希望拥有在整个过程期间编译的代码，此方法可能是最佳选择。</span><span class="sxs-lookup"><span data-stu-id="c3cff-146">This approach might be the best if you prefer to have code that compiles during the entire process.</span></span> <span data-ttu-id="c3cff-147">该方法如下所示：</span><span class="sxs-lookup"><span data-stu-id="c3cff-147">The approach is as follows:</span></span>

1. <span data-ttu-id="c3cff-148">在项目上运行 ApiPort。</span><span class="sxs-lookup"><span data-stu-id="c3cff-148">Run ApiPort on a project.</span></span>
1. <span data-ttu-id="c3cff-149">通过使用可移植的不同 API 解决问题。</span><span class="sxs-lookup"><span data-stu-id="c3cff-149">Address issues by using different APIs that are portable.</span></span>
1. <span data-ttu-id="c3cff-150">记录阻止你使用直接替代方案的所有区域。</span><span class="sxs-lookup"><span data-stu-id="c3cff-150">Take note of any areas where you're prevented from using a direct alternative.</span></span>
1. <span data-ttu-id="c3cff-151">对所有要移植的项目重复前面的步骤，直到确信每个项目都做好被复制到新的 .NET Core 项目中的准备。</span><span class="sxs-lookup"><span data-stu-id="c3cff-151">Repeat the prior steps for all projects you're porting until you're confident each is ready to be copied over into a new .NET Core project.</span></span>
1. <span data-ttu-id="c3cff-152">将代码复制到新的 .NET Core 项目。</span><span class="sxs-lookup"><span data-stu-id="c3cff-152">Copy the code into a new .NET Core project.</span></span>
1. <span data-ttu-id="c3cff-153">解决所有已记录的不存在直接替代方案的问题。</span><span class="sxs-lookup"><span data-stu-id="c3cff-153">Work out any issues where you noted that a direct alternative doesn't exist.</span></span>

<span data-ttu-id="c3cff-154">这种谨慎的方法比单纯解决编译器错误更有条理，但相对而言，它仍以代码为中心，且优点是始终拥有编译的代码。</span><span class="sxs-lookup"><span data-stu-id="c3cff-154">This careful approach is more structured than simply working out compiler errors, but it's still relatively code-focused and has the benefit of always having code that compiles.</span></span> <span data-ttu-id="c3cff-155">解决不能通过只使用另一个 API 解决的某些问题的方法大不相同。</span><span class="sxs-lookup"><span data-stu-id="c3cff-155">The way you resolve certain issues that couldn't be addressed by just using another API varies greatly.</span></span> <span data-ttu-id="c3cff-156">你可能会发现对于某些项目，需要制定更全面的计划，这将在下一种方法中涉及到。</span><span class="sxs-lookup"><span data-stu-id="c3cff-156">You may find that you need to develop a more comprehensive plan for certain projects, which is covered as the next approach.</span></span>

### <a name="developing-a-comprehensive-plan-of-attack"></a><span data-ttu-id="c3cff-157">制定全面的施行计划</span><span class="sxs-lookup"><span data-stu-id="c3cff-157">Developing a comprehensive plan of attack</span></span>

<span data-ttu-id="c3cff-158">此方法可能最适合大型或更复杂的项目，在这种情况下，为支持 .NET Core，可能必需重构代码或将某些代码区域完全重写。</span><span class="sxs-lookup"><span data-stu-id="c3cff-158">This approach might be best for larger and more complex projects, where restructuring code or completely rewriting certain areas of code might be necessary to support .NET Core.</span></span> <span data-ttu-id="c3cff-159">该方法如下所示：</span><span class="sxs-lookup"><span data-stu-id="c3cff-159">The approach is as follows:</span></span>

1. <span data-ttu-id="c3cff-160">在项目上运行 ApiPort。</span><span class="sxs-lookup"><span data-stu-id="c3cff-160">Run ApiPort on a project.</span></span>
1. <span data-ttu-id="c3cff-161">了解每个非可移植类型使用的位置以及位置对整体可移植性的影响。</span><span class="sxs-lookup"><span data-stu-id="c3cff-161">Understand where each non-portable type is used and how that affects overall portability.</span></span>
   - <span data-ttu-id="c3cff-162">了解这些类型的特性。</span><span class="sxs-lookup"><span data-stu-id="c3cff-162">Understand the nature of those types.</span></span> <span data-ttu-id="c3cff-163">它们是否数量少，但使用频繁？</span><span class="sxs-lookup"><span data-stu-id="c3cff-163">Are they small in number but used frequently?</span></span> <span data-ttu-id="c3cff-164">它们是否数量大，但使用不频繁？</span><span class="sxs-lookup"><span data-stu-id="c3cff-164">Are they large in number but used infrequently?</span></span> <span data-ttu-id="c3cff-165">它们是串联使用，还是在整个代码中传播？</span><span class="sxs-lookup"><span data-stu-id="c3cff-165">Is their use concentrated, or is it spread throughout your code?</span></span>
   - <span data-ttu-id="c3cff-166">是否可以轻松隔离不可移植的代码，以便可以更有效地处理它？</span><span class="sxs-lookup"><span data-stu-id="c3cff-166">Is it easy to isolate code that isn't portable so that you can deal with it more effectively?</span></span>
   - <span data-ttu-id="c3cff-167">是否需要重构代码？</span><span class="sxs-lookup"><span data-stu-id="c3cff-167">Do you need to refactor your code?</span></span>
   - <span data-ttu-id="c3cff-168">对于这些不可移植的类型，是否存在可完成相同任务的备用 API？</span><span class="sxs-lookup"><span data-stu-id="c3cff-168">For those types which aren't portable, are there alternative APIs that accomplish the same task?</span></span> <span data-ttu-id="c3cff-169">例如，如果使用 <xref:System.Net.WebClient> 类，也许能够改用 <xref:System.Net.Http.HttpClient> 类。</span><span class="sxs-lookup"><span data-stu-id="c3cff-169">For example if you're using the <xref:System.Net.WebClient> class, you might be able to use the <xref:System.Net.Http.HttpClient> class instead.</span></span>
   - <span data-ttu-id="c3cff-170">是否存在其他可用于完成任务的可移植 API，即使它不是直接替代 API？</span><span class="sxs-lookup"><span data-stu-id="c3cff-170">Are there different portable APIs available to accomplish a task, even if it's not a drop-in replacement?</span></span> <span data-ttu-id="c3cff-171">例如，如果使用 <xref:System.Xml.Schema.XmlSchema> 来分析 XML，但是无需 XML 架构发现，则可使用 <xref:System.Xml.Linq> API 并自行实现分析，而不依赖于 API。</span><span class="sxs-lookup"><span data-stu-id="c3cff-171">For example if you're using <xref:System.Xml.Schema.XmlSchema> to parse XML but don't require XML schema discovery, you could use <xref:System.Xml.Linq> APIs and implement parsing yourself as opposed to relying on an API.</span></span>
1. <span data-ttu-id="c3cff-172">如果具有难以移植的程序集，是否值得将其暂时留在 .NET Framework 上？</span><span class="sxs-lookup"><span data-stu-id="c3cff-172">If you have assemblies that are difficult to port, is it worth leaving them on .NET Framework for now?</span></span> <span data-ttu-id="c3cff-173">以下是一些需要考虑的事项：</span><span class="sxs-lookup"><span data-stu-id="c3cff-173">Here are some things to consider:</span></span>
   - <span data-ttu-id="c3cff-174">库中可能具有某些与 .NET Core 不兼容的功能，因为它太依赖 .NET Framework 或 Windows 特定的功能。</span><span class="sxs-lookup"><span data-stu-id="c3cff-174">You may have some functionality in your library that's incompatible with .NET Core because it relies too heavily on .NET Framework or Windows-specific functionality.</span></span> <span data-ttu-id="c3cff-175">是否值得暂时搁置该功能并发布在资源可用于移植这些功能前暂具较少功能的库的 .NET Core 版本？</span><span class="sxs-lookup"><span data-stu-id="c3cff-175">Is it worth leaving that functionality behind for now and releasing a .NET Core version of your library with less features on a temporary basis until resources are available to port the features?</span></span>
   - <span data-ttu-id="c3cff-176">重构是否有用？</span><span class="sxs-lookup"><span data-stu-id="c3cff-176">Would a refactor help?</span></span>
1. <span data-ttu-id="c3cff-177">编写自己对不可用 .NET Framework API 的实现是否合理？</span><span class="sxs-lookup"><span data-stu-id="c3cff-177">Is it reasonable to write your own implementation of an unavailable .NET Framework API?</span></span>
   <span data-ttu-id="c3cff-178">可以考虑复制、修改，并使用 [.NET Framework 参考源](https://github.com/Microsoft/referencesource)中的代码。</span><span class="sxs-lookup"><span data-stu-id="c3cff-178">You could consider copying, modifying, and using code from the [.NET Framework Reference Source](https://github.com/Microsoft/referencesource).</span></span> <span data-ttu-id="c3cff-179">参考源代码已在 [MIT 许可证](https://github.com/Microsoft/referencesource/blob/master/LICENSE.txt)下获得许可，因此可以自由选择将此源作为自己代码的基础。</span><span class="sxs-lookup"><span data-stu-id="c3cff-179">The reference source code is licensed under the [MIT License](https://github.com/Microsoft/referencesource/blob/master/LICENSE.txt), so you have significant freedom to use the source as a basis for your own code.</span></span> <span data-ttu-id="c3cff-180">只需确保在代码中正确设置 Microsoft。</span><span class="sxs-lookup"><span data-stu-id="c3cff-180">Just be sure to properly attribute Microsoft in your code.</span></span>
1. <span data-ttu-id="c3cff-181">根据不同项目的需要，重复此过程。</span><span class="sxs-lookup"><span data-stu-id="c3cff-181">Repeat this process as needed for different projects.</span></span>
 
<span data-ttu-id="c3cff-182">分析阶段可能需要一些时间，具体取决于代码库的大小。</span><span class="sxs-lookup"><span data-stu-id="c3cff-182">The analysis phase could take some time depending on the size of your codebase.</span></span> <span data-ttu-id="c3cff-183">在此阶段花费时间（尤其是在具有复杂的代码库时），全面了解所需的更改范围并制定计划，从长远看通常可节省时间。</span><span class="sxs-lookup"><span data-stu-id="c3cff-183">Spending time in this phase to thoroughly understand the scope of changes needed and to develop a plan usually saves you time in the long run, particularly if you have a complex codebase.</span></span>

<span data-ttu-id="c3cff-184">计划可能包括对代码库做重大更改，同时面向 .NET Framework 4.7.2，使它成为前一种方法更有条理的版本。</span><span class="sxs-lookup"><span data-stu-id="c3cff-184">Your plan could involve making significant changes to your codebase while still targeting .NET Framework 4.7.2, making this a more structured version of the previous approach.</span></span> <span data-ttu-id="c3cff-185">着手执行计划的方式具体取决于代码库。</span><span class="sxs-lookup"><span data-stu-id="c3cff-185">How you go about executing your plan is dependent on your codebase.</span></span>

### <a name="mixing-approaches"></a><span data-ttu-id="c3cff-186">混合方法</span><span class="sxs-lookup"><span data-stu-id="c3cff-186">Mixing approaches</span></span>

<span data-ttu-id="c3cff-187">在每个项目的基础上，可能会将上述方法进行混合。</span><span class="sxs-lookup"><span data-stu-id="c3cff-187">It's likely that you'll mix the above approaches on a per-project basis.</span></span> <span data-ttu-id="c3cff-188">应该进行对你和代码库最有意义的操作。</span><span class="sxs-lookup"><span data-stu-id="c3cff-188">You should do what makes the most sense to you and for your codebase.</span></span>

## <a name="porting-your-tests"></a><span data-ttu-id="c3cff-189">移植测试</span><span class="sxs-lookup"><span data-stu-id="c3cff-189">Porting your tests</span></span>

<span data-ttu-id="c3cff-190">要确保移植代码后一切正常的最佳方式是在将代码移植到 .NET Core 时进行测试。</span><span class="sxs-lookup"><span data-stu-id="c3cff-190">The best way to make sure everything works when you've ported your code is to test your code as you port it to .NET Core.</span></span> <span data-ttu-id="c3cff-191">为此，需要使用将针对 .NET Core 生成和运行测试的测试框架。</span><span class="sxs-lookup"><span data-stu-id="c3cff-191">To do this, you'll need to use a testing framework that builds and runs tests for .NET Core.</span></span> <span data-ttu-id="c3cff-192">当前，有三个选择：</span><span class="sxs-lookup"><span data-stu-id="c3cff-192">Currently, you have three options:</span></span>

- [<span data-ttu-id="c3cff-193">xUnit</span><span class="sxs-lookup"><span data-stu-id="c3cff-193">xUnit</span></span>](https://xunit.github.io/)
  * [<span data-ttu-id="c3cff-194">入门</span><span class="sxs-lookup"><span data-stu-id="c3cff-194">Getting Started</span></span>](https://xunit.github.io/docs/getting-started-dotnet-core.html)
  * [<span data-ttu-id="c3cff-195">将 MSTest 项目转换为 xUnit 的工具</span><span class="sxs-lookup"><span data-stu-id="c3cff-195">Tool to convert an MSTest project to xUnit</span></span>](https://github.com/dotnet/codeformatter/tree/master/src/XUnitConverter)
- [<span data-ttu-id="c3cff-196">NUnit</span><span class="sxs-lookup"><span data-stu-id="c3cff-196">NUnit</span></span>](https://nunit.org/)
  * [<span data-ttu-id="c3cff-197">入门</span><span class="sxs-lookup"><span data-stu-id="c3cff-197">Getting Started</span></span>](https://github.com/nunit/docs/wiki/Installation)
  * [<span data-ttu-id="c3cff-198">关于从 MSTest 迁移到 NUnit 的博客文章</span><span class="sxs-lookup"><span data-stu-id="c3cff-198">Blog post about migrating from MSTest to NUnit</span></span>](https://www.florian-rappl.de/News/Page/275/convert-mstest-to-nunit)
- [<span data-ttu-id="c3cff-199">MSTest</span><span class="sxs-lookup"><span data-stu-id="c3cff-199">MSTest</span></span>](https://docs.microsoft.com/visualstudio/test/unit-test-basics)

## <a name="recommended-approach-to-porting"></a><span data-ttu-id="c3cff-200">移植的推荐方法</span><span class="sxs-lookup"><span data-stu-id="c3cff-200">Recommended approach to porting</span></span>

<span data-ttu-id="c3cff-201">从根本上讲，移植工作在很大程度上取决于生成 .NET Framework 代码的方式。</span><span class="sxs-lookup"><span data-stu-id="c3cff-201">Ultimately, the porting effort depends heavily on how your .NET Framework code is structured.</span></span> <span data-ttu-id="c3cff-202">移植代码的一个好方法是从库的基项开始，这是代码的基础组件。</span><span class="sxs-lookup"><span data-stu-id="c3cff-202">A good way to port your code is to begin with the *base* of your library, which are the foundational components of your code.</span></span> <span data-ttu-id="c3cff-203">这可能是数据模型或某些其他内容直接或间接使用的基本类和方法。</span><span class="sxs-lookup"><span data-stu-id="c3cff-203">This might be data models or some other foundational classes and methods that everything else uses directly or indirectly.</span></span>

1. <span data-ttu-id="c3cff-204">移植测试项目，该项目测试当前正在移植的库层。</span><span class="sxs-lookup"><span data-stu-id="c3cff-204">Port the test project that tests the layer of your library that you're currently porting.</span></span>
1. <span data-ttu-id="c3cff-205">将库中的基项复制到新的 .NET Core 项目，然后选择想要支持的 .NET Standard 版本。</span><span class="sxs-lookup"><span data-stu-id="c3cff-205">Copy over the base of your library into a new .NET Core project and select the version of the .NET Standard you wish to support.</span></span>
1. <span data-ttu-id="c3cff-206">进行任何所需的更改，使代码进行编译。</span><span class="sxs-lookup"><span data-stu-id="c3cff-206">Make any changes needed to get the code to compile.</span></span> <span data-ttu-id="c3cff-207">大部分内容可能会要求将 NuGet 包依赖项添加到 csproj 文件。</span><span class="sxs-lookup"><span data-stu-id="c3cff-207">Much of this may require adding NuGet package dependencies to your *csproj* file.</span></span>
1. <span data-ttu-id="c3cff-208">运行测试并进行任何所需调整。</span><span class="sxs-lookup"><span data-stu-id="c3cff-208">Run the tests and make any needed adjustments.</span></span>
1. <span data-ttu-id="c3cff-209">选择下一层代码进行移植，并重复前面的步骤。</span><span class="sxs-lookup"><span data-stu-id="c3cff-209">Pick the next layer of code to port over and repeat the prior steps.</span></span>

<span data-ttu-id="c3cff-210">如果从库的基项开始并从基项向外移动并根据需要测试每一层，移植将是一个系统化的过程，在这种情况下，问题可以一次隔离到一层代码中。</span><span class="sxs-lookup"><span data-stu-id="c3cff-210">If you start with the base of your library and move outward from the base and test each layer as needed, porting is a systematic process where problems are isolated to one layer of code at a time.</span></span>

>[!div class="step-by-step"]
>[<span data-ttu-id="c3cff-211">下一页</span><span class="sxs-lookup"><span data-stu-id="c3cff-211">Next</span></span>](project-structure.md)
