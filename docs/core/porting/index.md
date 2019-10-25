---
title: 从 .NET Framework 移植到 .NET Core
description: 了解移植过程以及发现在将 .NET Framework 项目移植到 .NET Core 时可能有用的工具。
author: cartermp
ms.date: 10/22/2019
ms.custom: seodec18
ms.openlocfilehash: 0684be25cee6ae3f778e7134b4c3a29ac87caf25
ms.sourcegitcommit: 9bd1c09128e012b6e34bdcbdf3576379f58f3137
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/23/2019
ms.locfileid: "72798806"
---
# <a name="overview-of-the-porting-process-from-net-framework-to-net-core"></a><span data-ttu-id="0c0b8-103">从 .NET Framework 移植到 .NET Core 的过程概述</span><span class="sxs-lookup"><span data-stu-id="0c0b8-103">Overview of the porting process from .NET Framework to .NET Core</span></span>

<span data-ttu-id="0c0b8-104">你可能有些代码当前正在 .NET Framework 上运行，但你想将这些代码移植到 .NET Core。</span><span class="sxs-lookup"><span data-stu-id="0c0b8-104">You might have code that currently runs on the .NET Framework that you're interested in porting to .NET Core.</span></span> <span data-ttu-id="0c0b8-105">本文将提供：</span><span class="sxs-lookup"><span data-stu-id="0c0b8-105">This article provides:</span></span>

* <span data-ttu-id="0c0b8-106">移植过程概述。</span><span class="sxs-lookup"><span data-stu-id="0c0b8-106">An overview of the porting process.</span></span>
* <span data-ttu-id="0c0b8-107">在将代码移植到 .NET Core 时，可能会发现一系列有用的工具。</span><span class="sxs-lookup"><span data-stu-id="0c0b8-107">A list of the tools you may find helpful when you're porting your code to .NET Core.</span></span>

## <a name="overview-of-the-porting-process"></a><span data-ttu-id="0c0b8-108">移植过程概述</span><span class="sxs-lookup"><span data-stu-id="0c0b8-108">Overview of the porting process</span></span>

<span data-ttu-id="0c0b8-109">我们建议在将项目移植到 .NET Core 时使用以下过程：</span><span class="sxs-lookup"><span data-stu-id="0c0b8-109">We recommend you to use the following process when porting your project to .NET Core:</span></span>

1. <span data-ttu-id="0c0b8-110">将希望移植的所有项目重定向到目标 .NET Framework 4.7.2 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="0c0b8-110">Retarget all projects you wish to port to target the .NET Framework 4.7.2 or higher.</span></span>

   <span data-ttu-id="0c0b8-111">此步骤可确保在 .NET Core 不支持特殊 API 的情况下，可以为特定于 .NET Framework 的目标使用备用 API。</span><span class="sxs-lookup"><span data-stu-id="0c0b8-111">This step ensures that you can use API alternatives for .NET Framework-specific targets when .NET Core doesn't support a particular API.</span></span>

2. <span data-ttu-id="0c0b8-112">使用 [.NET 可移植性分析器](../../standard/analyzers/portability-analyzer.md)来分析程序集，并查看这些程序集是否可移植到 .NET Core。</span><span class="sxs-lookup"><span data-stu-id="0c0b8-112">Use the [.NET Portability Analyzer](../../standard/analyzers/portability-analyzer.md) to analyze your assemblies and see if they're portable to .NET Core.</span></span>

   <span data-ttu-id="0c0b8-113">API 可移植性分析器工具可分析已编译的程序集并生成报表。</span><span class="sxs-lookup"><span data-stu-id="0c0b8-113">The API Portability Analyzer tool analyzes your compiled assemblies and generates a report.</span></span> <span data-ttu-id="0c0b8-114">此报表显示高级别可移植性摘要，以及你所使用的不适用于 NET Core 的各个 API 细目。</span><span class="sxs-lookup"><span data-stu-id="0c0b8-114">This report shows a high-level portability summary and a breakdown of each API you're using that isn't available on NET Core.</span></span>

3. <span data-ttu-id="0c0b8-115">将 [.NET API 分析器](../../standard/analyzers/api-analyzer.md)安装到项目中，以识别在某些平台上会引发 <xref:System.PlatformNotSupportedException> 的 API 以及一些其他潜在的兼容性问题。</span><span class="sxs-lookup"><span data-stu-id="0c0b8-115">Install the [.NET API analyzer](../../standard/analyzers/api-analyzer.md) into your projects to identify APIs throwing <xref:System.PlatformNotSupportedException> on some platforms and some other potential compatibility issues.</span></span>

   <span data-ttu-id="0c0b8-116">此工具与可移植性分析器类似，但它不会分析是否可以在 .NET Core 上进行构建，而是分析你是否正在以会导致在运行时引发 <xref:System.PlatformNotSupportedException> 的某种方式使用 API。</span><span class="sxs-lookup"><span data-stu-id="0c0b8-116">This tool is similar to the portability analyzer, but instead of analyzing if things can build on .NET Core, it will analyze if you're using an API in a way that will throw the <xref:System.PlatformNotSupportedException> at runtime.</span></span> <span data-ttu-id="0c0b8-117">尽管这并不常见，但如果从 .NET Framework 4.7.2 或更高版本进行移动，最好进行检查。</span><span class="sxs-lookup"><span data-stu-id="0c0b8-117">Although this isn't common if you're moving from .NET Framework 4.7.2 or higher, it's good to check.</span></span>

4. <span data-ttu-id="0c0b8-118">通过 [Visual Studio 中的转换工具](/nuget/consume-packages/migrate-packages-config-to-package-reference)将所有 `packages.config` 依赖项转换为 [PackageReference](/nuget/consume-packages/package-references-in-project-files) 格式。</span><span class="sxs-lookup"><span data-stu-id="0c0b8-118">Convert all of your `packages.config` dependencies to the [PackageReference](/nuget/consume-packages/package-references-in-project-files) format with the [conversion tool in Visual Studio](/nuget/consume-packages/migrate-packages-config-to-package-reference).</span></span>

   <span data-ttu-id="0c0b8-119">此步骤涉及到转换旧 `packages.config` 格式的依赖项。</span><span class="sxs-lookup"><span data-stu-id="0c0b8-119">This step involves converting your dependencies from the legacy `packages.config` format.</span></span> <span data-ttu-id="0c0b8-120">`packages.config` 不适用于 .NET Core，因此，如果你有包依赖项，则需要进行此转换。</span><span class="sxs-lookup"><span data-stu-id="0c0b8-120">`packages.config` doesn't work on .NET Core, so this conversion is required if you have package dependencies.</span></span>

5. <span data-ttu-id="0c0b8-121">为 .NET Core 创建新项目并覆盖源文件，或尝试使用工具转换现有的项目文件。</span><span class="sxs-lookup"><span data-stu-id="0c0b8-121">Create new projects for .NET Core and copy over source files, or attempt to convert your existing project file with a tool.</span></span>

   <span data-ttu-id="0c0b8-122">.NET Core 使用不同于 .NET Framework 的更简化的[项目文件格式](../tools/csproj.md)。</span><span class="sxs-lookup"><span data-stu-id="0c0b8-122">.NET Core uses a simplified (and different) [project file format](../tools/csproj.md) than .NET Framework.</span></span> <span data-ttu-id="0c0b8-123">需要将项目文件转换为此格式才能继续操作。</span><span class="sxs-lookup"><span data-stu-id="0c0b8-123">You'll need to convert your project files into this format to continue.</span></span>

6. <span data-ttu-id="0c0b8-124">移植测试代码。</span><span class="sxs-lookup"><span data-stu-id="0c0b8-124">Port your test code.</span></span>

   <span data-ttu-id="0c0b8-125">由于移植到 .NET Core 对代码库来说是很大的更改，因此强烈建议移植测试代码，以便在移植代码时可以进行测试。</span><span class="sxs-lookup"><span data-stu-id="0c0b8-125">Because porting to .NET Core is such a significant change to your codebase, it's highly recommended to get your tests ported, so that you can run tests as you port your code over.</span></span> <span data-ttu-id="0c0b8-126">MSTest、xUnit 和 NUnit 都适用于 .NET Core。</span><span class="sxs-lookup"><span data-stu-id="0c0b8-126">MSTest, xUnit, and NUnit all work on .NET Core.</span></span>

<span data-ttu-id="0c0b8-127">此外，在某个操作中，可以尝试使用 [dotnet try-convert](https://github.com/dotnet/try-convert) 工具将较小的解决方案或单个项目移植到 .NET Core 项目文件格式。</span><span class="sxs-lookup"><span data-stu-id="0c0b8-127">Additionally, you can attempt to port smaller solutions or individual projects to the .NET Core project file format with the [dotnet try-convert](https://github.com/dotnet/try-convert) tool in one operation.</span></span> <span data-ttu-id="0c0b8-128">不能保证 `dotnet try-convert` 适用于所有项目，而且它可能会导致所依赖的行为发生细微变化。</span><span class="sxs-lookup"><span data-stu-id="0c0b8-128">`dotnet try-convert` is not guaranteedto work for all your projects, and it may cause subtle changes in behavior that you may find that you depended on.</span></span> <span data-ttu-id="0c0b8-129">应将它用作一个起点  ，以自动化可自动执行的基本操作。</span><span class="sxs-lookup"><span data-stu-id="0c0b8-129">It should be used as a _starting point_ that automates the basic things that can be automated.</span></span> <span data-ttu-id="0c0b8-130">作为用于迁移项目的一种解决方案，它并不是万无一失的。</span><span class="sxs-lookup"><span data-stu-id="0c0b8-130">It isn't a guaranteed solution to migrating a project.</span></span>

>[!div class="step-by-step"]
>[<span data-ttu-id="0c0b8-131">下一页</span><span class="sxs-lookup"><span data-stu-id="0c0b8-131">Next</span></span>](net-framework-tech-unavailable.md)
