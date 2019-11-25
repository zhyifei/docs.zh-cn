---
ms.openlocfilehash: 394ed636cece766d61b1a10403b98c73f1d3cb93
ms.sourcegitcommit: ad800f019ac976cb669e635fb0ea49db740e6890
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/29/2019
ms.locfileid: "73041259"
---
# <a name="labels-and-projects-roadmap"></a><span data-ttu-id="01aec-101">标签和项目路线图</span><span class="sxs-lookup"><span data-stu-id="01aec-101">Labels and projects roadmap</span></span>

<span data-ttu-id="01aec-102">.NET 文档团队广泛使用 [GitHub 标签](https://github.com/dotnet/docs/labels)来组织我们的工作。</span><span class="sxs-lookup"><span data-stu-id="01aec-102">The .NET docs team makes extensive use of [GitHub labels](https://github.com/dotnet/docs/labels) to organize our work.</span></span> <span data-ttu-id="01aec-103">通过按标签组合进行筛选，我们可以在 [.NET 文档网站](https://docs.microsoft.com/dotnet)中迅速找到所感兴趣的部分。</span><span class="sxs-lookup"><span data-stu-id="01aec-103">By filtering on combinations of labels, we can quickly focus on sections of interest on the [.NET docs website](https://docs.microsoft.com/dotnet).</span></span> 

<span data-ttu-id="01aec-104">此外，我们还使用 [GitHub 项目](https://github.com/dotnet/docs/projects)组织冲刺和其他实现目标的长篇故事。</span><span class="sxs-lookup"><span data-stu-id="01aec-104">We also use [GitHub projects](https://github.com/dotnet/docs/projects) to organize sprints and other goal-oriented epics.</span></span>

<span data-ttu-id="01aec-105">此路线图说明了我们使用这些组织工具的方式，并提供了用于查找感兴趣内容的便捷筛选器的链接。</span><span class="sxs-lookup"><span data-stu-id="01aec-105">This roadmap explains how we use these organizational tools and has links to handy filters we use to find areas of interest.</span></span>

## <a name="labels"></a><span data-ttu-id="01aec-106">标签</span><span class="sxs-lookup"><span data-stu-id="01aec-106">Labels</span></span>

<span data-ttu-id="01aec-107">如果这你是首次体验参与 [dotnet/docs](https://github.com/dotnet/docs)，请从[容易作答](https://github.com/dotnet/docs/labels/up-for-grabs)的问题开始。</span><span class="sxs-lookup"><span data-stu-id="01aec-107">If this is your first experience contributing to [dotnet/docs](https://github.com/dotnet/docs), start with the [up-for-grabs](https://github.com/dotnet/docs/labels/up-for-grabs) issues.</span></span> <span data-ttu-id="01aec-108">这些问题针对的范围更加集中。</span><span class="sxs-lookup"><span data-stu-id="01aec-108">These are issues that have a more focused scope.</span></span> <span data-ttu-id="01aec-109">从此类问题入手是完成首次参与的好方式。</span><span class="sxs-lookup"><span data-stu-id="01aec-109">They are a great way to make your first contribution.</span></span> <span data-ttu-id="01aec-110">从“容易作答”视图中，你可以进一步根据区域和优先级筛选问题。</span><span class="sxs-lookup"><span data-stu-id="01aec-110">From the up-for-grabs view, you can further filter issues based on areas and priority.</span></span> <span data-ttu-id="01aec-111">我们已使用 [good-first-issue](https://github.com/dotnet/docs/labels/good-first-issue) 标签标识出适合新手回答的问题，以便于你完成首次小小的参与。</span><span class="sxs-lookup"><span data-stu-id="01aec-111">We've identified good issues for beginners with the [good-first-issue](https://github.com/dotnet/docs/labels/good-first-issue) if you want to try a smaller first contribution.</span></span>

<span data-ttu-id="01aec-112">我们使用标签以多种不同方式来分类问题：</span><span class="sxs-lookup"><span data-stu-id="01aec-112">We use labels to classify issues in many different ways:</span></span>

- <span data-ttu-id="01aec-113">[.NET 指南](#find-a-single-net-guide)和[指南章节](#search-one-section-of-a-guide)。</span><span class="sxs-lookup"><span data-stu-id="01aec-113">[.NET Guides](#find-a-single-net-guide) and [sections of a guide](#search-one-section-of-a-guide).</span></span>
- [<span data-ttu-id="01aec-114">目标版本</span><span class="sxs-lookup"><span data-stu-id="01aec-114">Target release</span></span>](#releases)
- [<span data-ttu-id="01aec-115">优先级</span><span class="sxs-lookup"><span data-stu-id="01aec-115">Priority</span></span>](#priority)

<span data-ttu-id="01aec-116">你可以合并每组（指南、版本、优先级）中的标签，以缩小关注范围，查找你想要解决的问题。</span><span class="sxs-lookup"><span data-stu-id="01aec-116">You can combine a label from each set (guide, release, priority) to create a narrow focus to find issues you want to work on.</span></span>

### <a name="find-a-single-net-guide"></a><span data-ttu-id="01aec-117">查找单个 .NET 指南</span><span class="sxs-lookup"><span data-stu-id="01aec-117">Find a single .NET guide</span></span>

<span data-ttu-id="01aec-118">我们针对各个体系结构电子书以及各个 .NET 指南使用标签。</span><span class="sxs-lookup"><span data-stu-id="01aec-118">We use labels for each of the architecture e-books and for each .NET Guide.</span></span> 

<span data-ttu-id="01aec-119">![:book: guide on light green background](./images/guide.png "体系结构指南标签的前缀")</span><span class="sxs-lookup"><span data-stu-id="01aec-119">![:book: guide on light green background](./images/guide.png "Prefix for architecture guide labels")</span></span>

<span data-ttu-id="01aec-120">体系结构电子书标有 `:book: guide` 前缀，并且使用浅绿色背景。</span><span class="sxs-lookup"><span data-stu-id="01aec-120">Architecture e-books are noted with the `:book: guide` prefix and have a light green background.</span></span> <span data-ttu-id="01aec-121">这些是长格式区域，其中包含推荐的体系结构。</span><span class="sxs-lookup"><span data-stu-id="01aec-121">These are the long-form areas that cover recommended architecture.</span></span> <span data-ttu-id="01aec-122">以下是针对各个 .NET 体系结构指南筛选出的当前问题。</span><span class="sxs-lookup"><span data-stu-id="01aec-122">Here are current issues filtered for each of the .NET architecture guides.</span></span>

- [<span data-ttu-id="01aec-123">ASP.NET Core Web 应用</span><span class="sxs-lookup"><span data-stu-id="01aec-123">ASP.NET Core web apps</span></span>](https://github.com/dotnet/docs/labels/%3Abook%3A%20guide%20-%20ASP.NET%20Core%20web%20apps)
- [<span data-ttu-id="01aec-124">Blazor</span><span class="sxs-lookup"><span data-stu-id="01aec-124">Blazor</span></span>](https://github.com/dotnet/docs/labels/%3Abook%3A%20guide%20-%20Blazor)
- [<span data-ttu-id="01aec-125">云原生</span><span class="sxs-lookup"><span data-stu-id="01aec-125">Cloud Native</span></span>](https://github.com/dotnet/docs/labels/%3Abook%3A%20guide%20-%20Cloud%20Native)
- [<span data-ttu-id="01aec-126">Docker 生命周期</span><span class="sxs-lookup"><span data-stu-id="01aec-126">Docker lifecycle</span></span>](https://github.com/dotnet/docs/labels/%3Abook%3A%20guide%20-%20Docker%20lifecycle)
- [<span data-ttu-id="01aec-127">gRPC</span><span class="sxs-lookup"><span data-stu-id="01aec-127">gRPC</span></span>](https://github.com/dotnet/docs/labels/%3Abook%3A%20guide%20-%20gRPC)
- [<span data-ttu-id="01aec-128">通过 Windows 容器实现现代化</span><span class="sxs-lookup"><span data-stu-id="01aec-128">Modernizing w/ Windows containers</span></span>](https://github.com/dotnet/docs/labels/%3Abook%3A%20guide%20-%20Modernizing%20w%2F%20Windows%20containers)
- [<span data-ttu-id="01aec-129">.NET 微服务</span><span class="sxs-lookup"><span data-stu-id="01aec-129">.NET Microservices</span></span>](https://github.com/dotnet/docs/labels/%3Abook%3A%20guide%20-%20.NET%20Microservices)
- [<span data-ttu-id="01aec-130">无服务器应用</span><span class="sxs-lookup"><span data-stu-id="01aec-130">Serverless apps</span></span>](https://github.com/dotnet/docs/labels/%3Abook%3A%20guide%20-%20Serverless%20apps)

<span data-ttu-id="01aec-131">此标签样式也适用于 [Framework 设计准则](https://github.com/dotnet/docs/labels/%3Abook%3A%20guide%20-%20Framework%20Design%20Guidelines)。</span><span class="sxs-lookup"><span data-stu-id="01aec-131">This label style is also applied to the [Framework design guidelines](https://github.com/dotnet/docs/labels/%3Abook%3A%20guide%20-%20Framework%20Design%20Guidelines).</span></span> <span data-ttu-id="01aec-132">此区域使用相同的标签设计，但不建议对它执行社区拉取请求。</span><span class="sxs-lookup"><span data-stu-id="01aec-132">This area has the same label design, but community PRs are discouraged.</span></span> <span data-ttu-id="01aec-133">此为经许可后转载的材料，请勿进行编辑。</span><span class="sxs-lookup"><span data-stu-id="01aec-133">This is material reprinted with permission and should not be edited.</span></span>

<span data-ttu-id="01aec-134">![:books:Area on dark blue background](./images/area.png ".NET 指南区域标签的前缀")</span><span class="sxs-lookup"><span data-stu-id="01aec-134">![:books: Area on dark blue background](./images/area.png "Prefix for .NET Guide area labels")</span></span>

<span data-ttu-id="01aec-135">每个 .NET 指南都标有 `:books: Area` 前缀，并且使用深蓝色背景。</span><span class="sxs-lookup"><span data-stu-id="01aec-135">Each .NET Guide is noted with the `:books: Area` prefix and has a dark blue background.</span></span> <span data-ttu-id="01aec-136">以下是针对各个 .NET 指南筛选出的当前问题。</span><span class="sxs-lookup"><span data-stu-id="01aec-136">Here are current issues filtered for each of the .NET guides.</span></span>

- [<span data-ttu-id="01aec-137">API 参考</span><span class="sxs-lookup"><span data-stu-id="01aec-137">API Reference</span></span>](https://github.com/dotnet/docs/labels/%3Abooks%3A%20Area%20-%20API%20Reference)
- [<span data-ttu-id="01aec-138">Azure .NET SDK</span><span class="sxs-lookup"><span data-stu-id="01aec-138">Azure .NET SDK</span></span>](https://github.com/dotnet/docs/labels/%3Abooks%3A%20Area%20-%20Azure%20.NET%20SDk)
- [<span data-ttu-id="01aec-139">C# 指南</span><span class="sxs-lookup"><span data-stu-id="01aec-139">C# Guide</span></span>](https://github.com/dotnet/docs/labels/%3Abooks%3A%20Area%20-%20C%23%20Guide)
- [<span data-ttu-id="01aec-140">桌面指南</span><span class="sxs-lookup"><span data-stu-id="01aec-140">Desktop Guide</span></span>](https://github.com/dotnet/docs/labels/%3Abooks%3A%20Area%20-%20Desktop%20Guide)
- [<span data-ttu-id="01aec-141">F# 指南</span><span class="sxs-lookup"><span data-stu-id="01aec-141">F# Guide</span></span>](https://github.com/dotnet/docs/labels/%3Abooks%3A%20Area%20-%20F%23%20Guide)
- [<span data-ttu-id="01aec-142">ML.NET 指南</span><span class="sxs-lookup"><span data-stu-id="01aec-142">ML.NET Guide</span></span>](https://github.com/dotnet/docs/labels/%3Abooks%3A%20Area%20-%20ML.NET%20Guide)
- <span data-ttu-id="01aec-143">[.NET 体系结构指南](https://github.com/dotnet/docs/labels/%3Abooks%3A%20Area%20-%20.NET%20Architecture%20Guide) - 可以删除</span><span class="sxs-lookup"><span data-stu-id="01aec-143">[.NET Architecture Guide](https://github.com/dotnet/docs/labels/%3Abooks%3A%20Area%20-%20.NET%20Architecture%20Guide) - Could be removed</span></span>
- [<span data-ttu-id="01aec-144">.NET Core 指南</span><span class="sxs-lookup"><span data-stu-id="01aec-144">.NET Core Guide</span></span>](https://github.com/dotnet/docs/labels/%3Abooks%3A%20Area%20-%20.NET%20Core%20Guide)
- [<span data-ttu-id="01aec-145">.NET for Apache Spark 指南</span><span class="sxs-lookup"><span data-stu-id="01aec-145">.NET for Apache Spark Guide</span></span>](https://github.com/dotnet/docs/labels/%3Abooks%3A%20Area%20-%20.NET%20for%20Apache%20Spark%20Guide)
- [<span data-ttu-id="01aec-146">.NET Framework 指南</span><span class="sxs-lookup"><span data-stu-id="01aec-146">.NET Framework Guide</span></span>](https://github.com/dotnet/docs/labels/%3Abooks%3A%20Area%20-%20.NET%20Framework%20Guide)
- [<span data-ttu-id="01aec-147">.NET 指南</span><span class="sxs-lookup"><span data-stu-id="01aec-147">.NET Guide</span></span>](https://github.com/dotnet/docs/labels/%3Abooks%3A%20Area%20-%20.NET%20Guide)
- <span data-ttu-id="01aec-148">[Roslyn API 参考](https://github.com/dotnet/docs/labels/%3Abooks%3A%20Area%20-%20Roslyn%20API%20Reference) - 可以删除。</span><span class="sxs-lookup"><span data-stu-id="01aec-148">[Roslyn API Reference](https://github.com/dotnet/docs/labels/%3Abooks%3A%20Area%20-%20Roslyn%20API%20Reference) - could be removed.</span></span>
- [<span data-ttu-id="01aec-149">Visual Basic 指南</span><span class="sxs-lookup"><span data-stu-id="01aec-149">Visual Basic Guide</span></span>](https://github.com/dotnet/docs/labels/%3Abooks%3A%20Area%20-%20Visual%20Basic%20Guide)

#### <a name="search-one-section-of-a-guide"></a><span data-ttu-id="01aec-150">搜索指南的某个章节</span><span class="sxs-lookup"><span data-stu-id="01aec-150">Search one section of a guide</span></span>

<span data-ttu-id="01aec-151">![:card_file_box:Area on medium blue background](./images/technology.png ".NET 指南子区域标签的前缀")</span><span class="sxs-lookup"><span data-stu-id="01aec-151">![:card_file_box: Area on medium blue background](./images/technology.png "Prefix for .NET Guide sub-area labels")</span></span>

<span data-ttu-id="01aec-152">.NET 指南范围较大，因此，这些标签按指南章节对范围做了进一步限制。</span><span class="sxs-lookup"><span data-stu-id="01aec-152">The .NET guides are large, so these labels further limit the scope by a section of a guide.</span></span> <span data-ttu-id="01aec-153">每个 .NET 指南的子区域都标有 `:card_file_box: Technology` 前缀，并且使用中蓝色背景。</span><span class="sxs-lookup"><span data-stu-id="01aec-153">Each .NET Guide subarea is noted with the `:card_file_box: Technology` prefix and has a medium blue background.</span></span> <span data-ttu-id="01aec-154">其中许多标签适用于多个指南，而有些标签仅适用于一个指南。</span><span class="sxs-lookup"><span data-stu-id="01aec-154">Many of these labels apply to multiple guides, while others are in only one guide.</span></span> <span data-ttu-id="01aec-155">基于区域筛选后，添加其中一种标签，进一步限制问题的范围。</span><span class="sxs-lookup"><span data-stu-id="01aec-155">After filtering on an area, add one of these labels to further limit the scope of issues.</span></span>

- <span data-ttu-id="01aec-156">AppCompat</span><span class="sxs-lookup"><span data-stu-id="01aec-156">AppCompat</span></span>
- <span data-ttu-id="01aec-157">异步任务</span><span class="sxs-lookup"><span data-stu-id="01aec-157">Async Task</span></span>
- <span data-ttu-id="01aec-158">C# 高级概念</span><span class="sxs-lookup"><span data-stu-id="01aec-158">C# Advanced concepts</span></span>
- <span data-ttu-id="01aec-159">C# 编译器</span><span class="sxs-lookup"><span data-stu-id="01aec-159">C# compiler</span></span>
- <span data-ttu-id="01aec-160">C# 基础知识</span><span class="sxs-lookup"><span data-stu-id="01aec-160">C# Fundamentals</span></span>
- <span data-ttu-id="01aec-161">C# 入门</span><span class="sxs-lookup"><span data-stu-id="01aec-161">C# Get Started</span></span>
- <span data-ttu-id="01aec-162">C# 语言参考</span><span class="sxs-lookup"><span data-stu-id="01aec-162">C# Language Reference</span></span>
- <span data-ttu-id="01aec-163">C# Null 安全性</span><span class="sxs-lookup"><span data-stu-id="01aec-163">C# Null safety</span></span>
- <span data-ttu-id="01aec-164">C# 新增功能</span><span class="sxs-lookup"><span data-stu-id="01aec-164">C# What's new</span></span>
- <span data-ttu-id="01aec-165">CLI</span><span class="sxs-lookup"><span data-stu-id="01aec-165">CLI</span></span>
- <span data-ttu-id="01aec-166">数据访问</span><span class="sxs-lookup"><span data-stu-id="01aec-166">Data Access</span></span>
- <span data-ttu-id="01aec-167">Docker</span><span class="sxs-lookup"><span data-stu-id="01aec-167">Docker</span></span>
- <span data-ttu-id="01aec-168">安装程序</span><span class="sxs-lookup"><span data-stu-id="01aec-168">Installers</span></span>
- <span data-ttu-id="01aec-169">LINQ</span><span class="sxs-lookup"><span data-stu-id="01aec-169">LINQ</span></span>
- <span data-ttu-id="01aec-170">NCL</span><span class="sxs-lookup"><span data-stu-id="01aec-170">NCL</span></span>
- <span data-ttu-id="01aec-171">.NET Standard</span><span class="sxs-lookup"><span data-stu-id="01aec-171">.NET Standard</span></span>
- <span data-ttu-id="01aec-172">Roslyn API</span><span class="sxs-lookup"><span data-stu-id="01aec-172">Roslyn APIs</span></span>
- <span data-ttu-id="01aec-173">安全性</span><span class="sxs-lookup"><span data-stu-id="01aec-173">Security</span></span>
- <span data-ttu-id="01aec-174">WCF</span><span class="sxs-lookup"><span data-stu-id="01aec-174">WCF</span></span>
- <span data-ttu-id="01aec-175">WF</span><span class="sxs-lookup"><span data-stu-id="01aec-175">WF</span></span>
- <span data-ttu-id="01aec-176">WIF</span><span class="sxs-lookup"><span data-stu-id="01aec-176">WIF</span></span>
- <span data-ttu-id="01aec-177">WinForms</span><span class="sxs-lookup"><span data-stu-id="01aec-177">WinForms</span></span>
- <span data-ttu-id="01aec-178">WPF</span><span class="sxs-lookup"><span data-stu-id="01aec-178">WPF</span></span>

### <a name="releases"></a><span data-ttu-id="01aec-179">发布</span><span class="sxs-lookup"><span data-stu-id="01aec-179">Releases</span></span>

<span data-ttu-id="01aec-180">![:checkered_flag:Release: on dark yellow](./images/release.png "版本标签的前缀")</span><span class="sxs-lookup"><span data-stu-id="01aec-180">![:checkered_flag: Release: on dark yellow](./images/release.png "Prefix for release labels")</span></span>

<span data-ttu-id="01aec-181">针对特定版本标记的问题标有 `:checkered_flag: Release:` 前缀，并且使用深黄色背景。</span><span class="sxs-lookup"><span data-stu-id="01aec-181">Issues tagged for a specific release are noted with the `:checkered_flag: Release:` prefix and have a dark yellow background.</span></span> 

- <span data-ttu-id="01aec-182">.NET Core 2.2</span><span class="sxs-lookup"><span data-stu-id="01aec-182">.NET Core 2.2</span></span>
- <span data-ttu-id="01aec-183">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="01aec-183">.NET Core 3.0</span></span>

### <a name="priority"></a><span data-ttu-id="01aec-184">Priority</span><span class="sxs-lookup"><span data-stu-id="01aec-184">Priority</span></span>

<span data-ttu-id="01aec-185">优先级标签由 `P` 及其后面的单个数字构成。</span><span class="sxs-lookup"><span data-stu-id="01aec-185">Priority labels are all `P` followed by a single digit.</span></span> <span data-ttu-id="01aec-186">数字越小表示优先级越高：</span><span class="sxs-lookup"><span data-stu-id="01aec-186">Lower numbers are higher priority:</span></span>

- <span data-ttu-id="01aec-187">P0</span><span class="sxs-lookup"><span data-stu-id="01aec-187">P0</span></span>
- <span data-ttu-id="01aec-188">P1</span><span class="sxs-lookup"><span data-stu-id="01aec-188">P1</span></span>
- <span data-ttu-id="01aec-189">P2</span><span class="sxs-lookup"><span data-stu-id="01aec-189">P2</span></span>

### <a name="what-about-the-other-labels"></a><span data-ttu-id="01aec-190">其他还有哪些标签？</span><span class="sxs-lookup"><span data-stu-id="01aec-190">What about the other labels?</span></span>

<span data-ttu-id="01aec-191">内容团队还使用了许多其他标签来管理各种问题分类。</span><span class="sxs-lookup"><span data-stu-id="01aec-191">There are many other labels used by the content teams to manage different classifications of issues.</span></span> <span data-ttu-id="01aec-192">如果你不属于内容团队，则可以忽略其他这些标签。</span><span class="sxs-lookup"><span data-stu-id="01aec-192">If you're not on the content team, you can ignore these other labels.</span></span>

## <a name="projects"></a><span data-ttu-id="01aec-193">项目</span><span class="sxs-lookup"><span data-stu-id="01aec-193">Projects</span></span>

<span data-ttu-id="01aec-194">参与者应查看[适用于 .NET 社区协作者的项目](https://github.com/dotnet/docs/projects/35)。</span><span class="sxs-lookup"><span data-stu-id="01aec-194">Contributors should check the [Projects for .NET community collaborators](https://github.com/dotnet/docs/projects/35).</span></span> <span data-ttu-id="01aec-195">我们已针对维护、文档更新和新内容任务创建了不同的列。</span><span class="sxs-lookup"><span data-stu-id="01aec-195">We've created different columns for maintenance, document updates, and new content tasks.</span></span> <span data-ttu-id="01aec-196">这也是一种查找感兴趣任务的方法。</span><span class="sxs-lookup"><span data-stu-id="01aec-196">This can be a way to find tasks of interest.</span></span> <span data-ttu-id="01aec-197">（请注意，可以使用上述标签筛选项目视图。）</span><span class="sxs-lookup"><span data-stu-id="01aec-197">(Note that the project view can be filtered using the labels described above.)</span></span> 

<span data-ttu-id="01aec-198">此外，我们还通过其他两种方式使用项目：</span><span class="sxs-lookup"><span data-stu-id="01aec-198">We also use projects in two other ways:</span></span>

- <span data-ttu-id="01aec-199">Month YYYY 项目类型：这些是每月工作计划的任务板。</span><span class="sxs-lookup"><span data-stu-id="01aec-199">Month YYYY project types: These are scrum boards for each month's working plan.</span></span>
- <span data-ttu-id="01aec-200">长时间运行的长篇故事：当工作将在几个月内完成时，使用它们来组织实现目标的任务。</span><span class="sxs-lookup"><span data-stu-id="01aec-200">Long-running epics: These are used to organize tasks toward a goal when the work will occur over several months.</span></span>
