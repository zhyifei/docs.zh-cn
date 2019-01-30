---
title: 将代码从 .NET Framework 移植到 .NET Core
description: 了解移植过程以及发现在将 .NET Framework 项目移植到 .NET Core 时可能有用的工具。
author: cartermp
ms.date: 12/04/2018
ms.custom: seodec18
ms.openlocfilehash: e29750340cf272c2e05287482bcbeca703d8720a
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/30/2019
ms.locfileid: "55266567"
---
# <a name="port-your-code-from-net-framework-to-net-core"></a><span data-ttu-id="970fe-103">将代码从 .NET Framework 移植到 .NET Core</span><span class="sxs-lookup"><span data-stu-id="970fe-103">Port your code from .NET Framework to .NET Core</span></span>

<span data-ttu-id="970fe-104">如果有在 .NET Framework 上运行的代码，用户也可能会对在 .NET Core 上运行代码感兴趣。</span><span class="sxs-lookup"><span data-stu-id="970fe-104">If you've got code that runs on the .NET Framework, you may be interested in running your code on .NET Core, too.</span></span> <span data-ttu-id="970fe-105">下面提供了移植过程的概述以及在将代码移植到 .NET Core 时可能非常有用的工具列表。</span><span class="sxs-lookup"><span data-stu-id="970fe-105">Here's an overview of the porting process and a list of the tools you may find helpful when porting your code to .NET Core.</span></span>

## <a name="overview-of-the-porting-process"></a><span data-ttu-id="970fe-106">移植过程概述</span><span class="sxs-lookup"><span data-stu-id="970fe-106">Overview of the porting process</span></span>

<span data-ttu-id="970fe-107">这是我们建议在将项目移植到.NET Core 时采取的过程。</span><span class="sxs-lookup"><span data-stu-id="970fe-107">This is the process we recommend you take when porting your project to .NET Core.</span></span> <span data-ttu-id="970fe-108">该过程的每个步骤将在以后的文章中详细介绍。</span><span class="sxs-lookup"><span data-stu-id="970fe-108">Each step of the process is covered in more detail in further articles.</span></span>

1. <span data-ttu-id="970fe-109">标识并记录第三方依赖项。</span><span class="sxs-lookup"><span data-stu-id="970fe-109">Identify and account for your third-party dependencies.</span></span>

   <span data-ttu-id="970fe-110">此步骤包含了解什么是第三方依赖项，如何依赖于它们，如何查看它们是否也在 .NET Core 上运行，以及如果没有在其上运行可以采取的步骤。</span><span class="sxs-lookup"><span data-stu-id="970fe-110">This step involves understanding what your third-party dependencies are, how you depend on them, how to check if they also run on .NET Core, and steps you can take if they don't.</span></span> <span data-ttu-id="970fe-111">它还介绍了如何将依赖项迁移到 .NET Core 中使用的 [PackageReference](/nuget/consume-packages/package-references-in-project-files) 格式。</span><span class="sxs-lookup"><span data-stu-id="970fe-111">It also covers how you can migrate your dependencies over to the [PackageReference](/nuget/consume-packages/package-references-in-project-files) format that is used in .NET Core.</span></span>

2. <span data-ttu-id="970fe-112">将希望移植的所有项目重定向到目标 .NET Framework 4.7.2 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="970fe-112">Retarget all projects you wish to port to target the .NET Framework 4.7.2 or higher.</span></span>

   <span data-ttu-id="970fe-113">此步骤可确保在 .NET Core 不支持特殊 API 的情况下，可以为特定于 .NET Framework 的目标使用备用 API。</span><span class="sxs-lookup"><span data-stu-id="970fe-113">This step ensures that you can use API alternatives for .NET Framework-specific targets when .NET Core doesn't support a particular API.</span></span>

3. <span data-ttu-id="970fe-114">使用 [.NET Portability Analyzer](../../standard/analyzers/portability-analyzer.md) 来分析程序集并基于结果制定移植计划。</span><span class="sxs-lookup"><span data-stu-id="970fe-114">Use the [.NET Portability Analyzer](../../standard/analyzers/portability-analyzer.md) to analyze your assemblies and develop a plan to port based on its results.</span></span>

   <span data-ttu-id="970fe-115">API Portability Analyzer 工具分析已编译的程序集并生成报表，该报表将显示高级可移植性摘要和不可用于 .NET Core 上的正在使用的每个 API 的细目。</span><span class="sxs-lookup"><span data-stu-id="970fe-115">The API Portability Analyzer tool analyzes your compiled assemblies and generates a report that shows a high-level portability summary and a breakdown of each API you're using that isn't available on .NET Core.</span></span> <span data-ttu-id="970fe-116">可以使用此报表和代码库的分析结果一起制定移植代码的计划。</span><span class="sxs-lookup"><span data-stu-id="970fe-116">You can use this report alongside an analysis of your codebase to develop a plan for how you'll port your code over.</span></span>

4. <span data-ttu-id="970fe-117">移植测试代码。</span><span class="sxs-lookup"><span data-stu-id="970fe-117">Port your tests code.</span></span>

   <span data-ttu-id="970fe-118">由于移植到 .NET Core 对代码库来说是很大的更改，因此强烈建议移植测试代码，以便在移植代码时可以进行测试。</span><span class="sxs-lookup"><span data-stu-id="970fe-118">Because porting to .NET Core is such a significant change to your codebase, it's highly recommended to get your tests ported, so that you can run tests as you port your code over.</span></span> <span data-ttu-id="970fe-119">MSTest、xUnit 和 NUnit 都支持 .NET Core。</span><span class="sxs-lookup"><span data-stu-id="970fe-119">MSTest, xUnit, and NUnit all support .NET Core.</span></span>

5. <span data-ttu-id="970fe-120">执行移植计划！</span><span class="sxs-lookup"><span data-stu-id="970fe-120">Execute your plan for porting!</span></span>

## <a name="tools-to-help"></a><span data-ttu-id="970fe-121">帮助工具</span><span class="sxs-lookup"><span data-stu-id="970fe-121">Tools to help</span></span>

<span data-ttu-id="970fe-122">以下列表显示了在移植过程中使用可能有所帮助的工具：</span><span class="sxs-lookup"><span data-stu-id="970fe-122">The following list shows tools you might find helpful to use during the porting process:</span></span>

* <span data-ttu-id="970fe-123">.NET Portability Analyzer - [命令行工具](https://github.com/Microsoft/dotnet-apiport/releases)或 [Visual Studio 扩展](https://marketplace.visualstudio.com/items?itemName=ConnieYau.NETPortabilityAnalyzer)，可生成有关 .NET Framework 和 .NET Core 之间代码移植性的报表的工具链，并且带有程序集到程序集的问题细目。</span><span class="sxs-lookup"><span data-stu-id="970fe-123">.NET Portability Analyzer - [command line tool](https://github.com/Microsoft/dotnet-apiport/releases) or [Visual Studio Extension](https://marketplace.visualstudio.com/items?itemName=ConnieYau.NETPortabilityAnalyzer), a toolchain that can generate a report of how portable your code is between .NET Framework and .NET Core, with an assembly-by-assembly breakdown of issues.</span></span> <span data-ttu-id="970fe-124">有关详细信息，请参阅 [.NET Portability Analyzer](../../standard/analyzers/portability-analyzer.md)。</span><span class="sxs-lookup"><span data-stu-id="970fe-124">For more information, see [.NET Portability Analyzer](../../standard/analyzers/portability-analyzer.md).</span></span>
* <span data-ttu-id="970fe-125">.NET API 分析器 - 一个 Roslyn 分析器，可用于发现不同平台上的潜在 C# API 兼容性风险，并检测是否调用了弃用的 API。</span><span class="sxs-lookup"><span data-stu-id="970fe-125">.NET API analyzer - A Roslyn analyzer that discovers potential compatibility risks for C# APIs on different platforms and detects calls to deprecated APIs.</span></span> <span data-ttu-id="970fe-126">有关详细信息，请参阅 [.NET API 分析器](../../standard/analyzers/api-analyzer.md)。</span><span class="sxs-lookup"><span data-stu-id="970fe-126">For more information, see [.NET API analyzer](../../standard/analyzers/api-analyzer.md).</span></span>
* <span data-ttu-id="970fe-127">Reverse Package Search - 一个[有用的 Web 服务](https://packagesearch.azurewebsites.net)，能够实现搜索某一类型并找到包含该类型的包。</span><span class="sxs-lookup"><span data-stu-id="970fe-127">Reverse Package Search - A [useful web service](https://packagesearch.azurewebsites.net) that allows you to search for a type and find packages containing that type.</span></span>

<span data-ttu-id="970fe-128">此外，可以尝试使用 [CsprojToVs2017](https://github.com/hvanbakel/CsprojToVs2017) 工具将较小的解决方案或单个项目移植到 .NET Core 项目文件格式。</span><span class="sxs-lookup"><span data-stu-id="970fe-128">Additionally, you can attempt to port smaller solutions or individual projects to the .NET Core project file format with the [CsprojToVs2017](https://github.com/hvanbakel/CsprojToVs2017) tool.</span></span>

> [!WARNING] 
> <span data-ttu-id="970fe-129">CsprojToVs2017 是第三方工具。</span><span class="sxs-lookup"><span data-stu-id="970fe-129">CsprojToVs2017 is a third-party tool.</span></span> <span data-ttu-id="970fe-130">不能保证它适用于所有项目，而且它可能会导致所依赖的行为发生细微变化。</span><span class="sxs-lookup"><span data-stu-id="970fe-130">There is no guarantee that it will work for all of your projects, and it may cause subtle changes in behavior that you depend on.</span></span> <span data-ttu-id="970fe-131">CsprojToVs2017 应作为一个起点，以自动化可自动执行的基本操作。</span><span class="sxs-lookup"><span data-stu-id="970fe-131">CsprojToVs2017 should be used as a _starting point_ that automates the basic things that can be automated.</span></span> <span data-ttu-id="970fe-132">它不是迁移项目文件格式的有保证的解决方案。</span><span class="sxs-lookup"><span data-stu-id="970fe-132">It is not a guaranteed solution to migrating project file formats.</span></span>

>[!div class="step-by-step"]
>[<span data-ttu-id="970fe-133">下一页</span><span class="sxs-lookup"><span data-stu-id="970fe-133">Next</span></span>](third-party-deps.md)
