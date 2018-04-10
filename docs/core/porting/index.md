---
title: 从 .NET Framework 移植到 .NET Core
description: 了解移植过程以及发现在将 .NET Framework 项目移植到 .NET Core 时可能有用的工具。
keywords: .NET, .NET Core
author: cartermp
ms.author: mairaw
ms.date: 06/20/2016
ms.topic: article
ms.prod: .net-core
ms.devlang: dotnet
ms.assetid: 00d00d38-99af-44f4-a75f-defcd9729dc5
ms.workload:
- dotnetcore
ms.openlocfilehash: 3413b73c2a0a3c3ebf49b0b3ec81d00c6558d9a8
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/23/2017
---
# <a name="porting-to-net-core-from-net-framework"></a><span data-ttu-id="f7c50-104">从 .NET Framework 移植到 .NET Core</span><span class="sxs-lookup"><span data-stu-id="f7c50-104">Porting to .NET Core from .NET Framework</span></span>

<span data-ttu-id="f7c50-105">如果已在 .NET Framework 上运行了代码，则可能会对在 .NET Core 1.0 上运行代码感兴趣。</span><span class="sxs-lookup"><span data-stu-id="f7c50-105">If you've got code running on the .NET Framework, you may be interested in running your code on .NET Core 1.0.</span></span>  <span data-ttu-id="f7c50-106">本文提供移植过程的概述以及在移植到 .NET Core 时可能非常有用的工具列表。</span><span class="sxs-lookup"><span data-stu-id="f7c50-106">This article covers an overview of the porting process and a list of the tools you may find helpful when porting to .NET Core.</span></span>

## <a name="overview-of-the-porting-process"></a><span data-ttu-id="f7c50-107">移植过程概述</span><span class="sxs-lookup"><span data-stu-id="f7c50-107">Overview of the Porting Process</span></span>

<span data-ttu-id="f7c50-108">建议按照以下步骤进行移植过程。</span><span class="sxs-lookup"><span data-stu-id="f7c50-108">The recommended process for porting follows the following series of steps.</span></span>  <span data-ttu-id="f7c50-109">该步骤的每个部分将在以后的文章中详细介绍。</span><span class="sxs-lookup"><span data-stu-id="f7c50-109">Each of these parts of the process are covered in more detail in further articles.</span></span>

1. <span data-ttu-id="f7c50-110">标识并记录第三方依赖项。</span><span class="sxs-lookup"><span data-stu-id="f7c50-110">Identify and account for your third-party dependencies.</span></span>

   <span data-ttu-id="f7c50-111">因此需要了解什么是第三方依赖项，如何依赖于它们，如何查看它们是否也在 .NET Core 上运行，以及如果没有在其上运行可以采取的步骤。</span><span class="sxs-lookup"><span data-stu-id="f7c50-111">This will involve understanding what your third-party dependencies are, how you depend on them, how to see if they also run on .NET Core, and steps you can take if they don't.</span></span>
   
2. <span data-ttu-id="f7c50-112">将希望移植的所有项目重定向目标到目标 .NET Framework 4.6.2。</span><span class="sxs-lookup"><span data-stu-id="f7c50-112">Retarget all projects you wish to port to target .NET Framework 4.6.2.</span></span>

   <span data-ttu-id="f7c50-113">这可确保在 .NET Core 不支持特殊 API 的情况下，可以为特定于 .NET Framework 的目标使用备用 API。</span><span class="sxs-lookup"><span data-stu-id="f7c50-113">This ensures that you can use API alternatives for .NET Framework-specific targets in the cases where .NET Core can't support a particular API.</span></span>
   
3. <span data-ttu-id="f7c50-114">使用 [API Portability Analyzer 工具](https://github.com/Microsoft/dotnet-apiport/)来分析程序集并基于结果制定移植计划。</span><span class="sxs-lookup"><span data-stu-id="f7c50-114">Use the [API Portability Analyzer tool](https://github.com/Microsoft/dotnet-apiport/) to analyze your assemblies and develop a plan to port based on its results.</span></span>

   <span data-ttu-id="f7c50-115">API Portability Analyzer 工具将分析已编译的程序集并生成报表，该报表将显示高级可移植性摘要和不可用于 .NET Core 上的正在使用的每个 API 的细目。</span><span class="sxs-lookup"><span data-stu-id="f7c50-115">The API Portability Analyzer tool will analyze your compiled assemblies and generate a report which shows a high-level portability summary and a breakdown of each API you're using that isn't available on .NET Core.</span></span>  <span data-ttu-id="f7c50-116">可以使用此报表和代码库的分析结果一起制定移植代码的计划。</span><span class="sxs-lookup"><span data-stu-id="f7c50-116">You can use this report alongside an analysis of your codebase to develop a plan for how you'll port your code over.</span></span>
   
4. <span data-ttu-id="f7c50-117">移植测试代码。</span><span class="sxs-lookup"><span data-stu-id="f7c50-117">Port your tests code.</span></span>

   <span data-ttu-id="f7c50-118">由于移植到 .NET Core 对代码库来说是很大的更改，因此强烈建议移植测试代码，以便在移植代码时可以进行测试。</span><span class="sxs-lookup"><span data-stu-id="f7c50-118">Because porting to .NET Core is such a big change to your codebase, it's highly recommended to get your tests ported so that you can run tests as you port code over.</span></span>  <span data-ttu-id="f7c50-119">如今，MSTest、xUnit 和 NUnit 都支持 .NET Core 1.0。</span><span class="sxs-lookup"><span data-stu-id="f7c50-119">MSTest, xUnit, and NUnit all support .NET Core 1.0 today.</span></span>
   
6. <span data-ttu-id="f7c50-120">执行移植计划！</span><span class="sxs-lookup"><span data-stu-id="f7c50-120">Execute your plan for porting!</span></span>

## <a name="tools-to-help"></a><span data-ttu-id="f7c50-121">帮助工具</span><span class="sxs-lookup"><span data-stu-id="f7c50-121">Tools to help</span></span>

<span data-ttu-id="f7c50-122">以下是非常有用的工具的简短列表：</span><span class="sxs-lookup"><span data-stu-id="f7c50-122">Here's a short list of the tools you'll find helpful:</span></span>

* <span data-ttu-id="f7c50-123">NuGet - [Nuget 客户端](https://dist.nuget.org/index.html)或 [NuGet Package Explorer](https://github.com/NuGetPackageExplorer/NuGetPackageExplorer)，是 Microsoft 针对 .NET 实现的包管理器。</span><span class="sxs-lookup"><span data-stu-id="f7c50-123">NuGet - [Nuget Client](https://dist.nuget.org/index.html) or [NuGet Package Explorer](https://github.com/NuGetPackageExplorer/NuGetPackageExplorer), Microsoft's package manager for .NET implementations.</span></span>
* <span data-ttu-id="f7c50-124">Api Portability Analyzer - [命令行工具](https://github.com/Microsoft/dotnet-apiport/releases)或 [Visual Studio 扩展](https://visualstudiogallery.msdn.microsoft.com/1177943e-cfb7-4822-a8a6-e56c7905292b)，可生成有关 .NET Framework 和 .NET Core 之间代码移植性的报表的工具链，并且带有程序集到程序集的问题细目。</span><span class="sxs-lookup"><span data-stu-id="f7c50-124">Api Portability Analyzer - [command line tool](https://github.com/Microsoft/dotnet-apiport/releases) or [Visual Studio Extension](https://visualstudiogallery.msdn.microsoft.com/1177943e-cfb7-4822-a8a6-e56c7905292b), a toolchain that can generate a report of how portable your code is between .NET Framework and .NET Core, with an assembly-by-assembly breakdown of issues.</span></span>  <span data-ttu-id="f7c50-125">有关详细信息，请参阅 [Tooling to help you on the process](https://github.com/Microsoft/dotnet-apiport/blob/master/docs/HowTo/)（过程中使用的帮助工具）。</span><span class="sxs-lookup"><span data-stu-id="f7c50-125">See [Tooling to help you on the process](https://github.com/Microsoft/dotnet-apiport/blob/master/docs/HowTo/) for more information.</span></span>
* <span data-ttu-id="f7c50-126">Reverse Package Search - 一个[有用的 Web 服务](https://packagesearch.azurewebsites.net)，能够实现搜索某一类型并找到包含该类型的包。</span><span class="sxs-lookup"><span data-stu-id="f7c50-126">Reverse Package Search - A [useful web service](https://packagesearch.azurewebsites.net) that allows you to search for a type and find packages containing that type.</span></span>

## <a name="next-steps"></a><span data-ttu-id="f7c50-127">后续步骤</span><span class="sxs-lookup"><span data-stu-id="f7c50-127">Next steps</span></span>

[<span data-ttu-id="f7c50-128">分析第三方依赖项。</span><span class="sxs-lookup"><span data-stu-id="f7c50-128">Analyzing your third-party dependencies.</span></span>](third-party-deps.md)
   
