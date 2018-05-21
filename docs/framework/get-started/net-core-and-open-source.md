---
title: .NET 核心和开放源代码
ms.date: 03/30/2017
ms.assetid: e6bd4655-ce37-4003-8462-468a6fe2c40f
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 707e73705e5e96e1b0b92976d22f763afef64929
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="net-core-and-open-source"></a><span data-ttu-id="a8348-102">.NET 核心和开放源代码</span><span class="sxs-lookup"><span data-stu-id="a8348-102">.NET Core and Open-Source</span></span>
<span data-ttu-id="a8348-103">本主题提供有关 .NET 核心概念的简要概述并展示如何查找更多信息。</span><span class="sxs-lookup"><span data-stu-id="a8348-103">This topic provides a brief overview  of what .NET Core is and shows how you can find more information.</span></span> <span data-ttu-id="a8348-104">若要查找有关 .NET Core 的完整主题列表，请访问 [.NET Core 指南](../../core/index.md)。</span><span class="sxs-lookup"><span data-stu-id="a8348-104">To find the complete list of topics for .NET Core, visit the [.NET Core Guide](../../core/index.md).</span></span>
  
<a name="BKMK_WhatisNETCore"></a>   
## <a name="what-is-net-core"></a><span data-ttu-id="a8348-105">.NET 核心是什么？</span><span class="sxs-lookup"><span data-stu-id="a8348-105">What is .NET Core?</span></span>  
 <span data-ttu-id="a8348-106">.NET Core 是 .NET 标准的常规用途、模块化、跨平台和开放源代码实现。</span><span class="sxs-lookup"><span data-stu-id="a8348-106">.NET Core is a general purpose, modular, cross-platform and open source implementation of the .NET Standard.</span></span> <span data-ttu-id="a8348-107">它包含 .NET Framework 这样的许多相同 API（但 .NET Core 是较小的集）并包括支持不同操作系统和芯片目标的运行时、框架、编译器和工具组件。</span><span class="sxs-lookup"><span data-stu-id="a8348-107">It contains many of the same APIs as the .NET Framework (but .NET Core is a smaller set) and includes runtime, framework, compiler and tools components that support a variety of operating systems and chip targets.</span></span> <span data-ttu-id="a8348-108">.NET Core 实现主要由 ASP.NET 核心工作负载驱动，但同时也由拥有一个更现代的实现这一需求和愿望驱动。</span><span class="sxs-lookup"><span data-stu-id="a8348-108">The .NET Core implementation was primarily driven by the ASP.NET Core workloads but also by the need and desire to have a more modern implementation.</span></span> <span data-ttu-id="a8348-109">它可以用于设备、云和嵌入式/IoT 方案。</span><span class="sxs-lookup"><span data-stu-id="a8348-109">It can be used in device, cloud and embedded/IoT scenarios.</span></span>  
  
 <span data-ttu-id="a8348-110">若要开始使用 .NET 核心，请访问 [.NET 核心主页](https://www.microsoft.com/net/core)。</span><span class="sxs-lookup"><span data-stu-id="a8348-110">To get started with .NET Core, please visit the [.NET Core homepage](https://www.microsoft.com/net/core).</span></span>  
  
 <span data-ttu-id="a8348-111">下面列出了 .NET 核心的主要特征：</span><span class="sxs-lookup"><span data-stu-id="a8348-111">Here are the main characteristics of .NET Core:</span></span>  
  
-   <span data-ttu-id="a8348-112">**跨平台：**.NET 核心提供了实现所需应用功能的关键功能，并且可以重用代码而不考虑平台目标。</span><span class="sxs-lookup"><span data-stu-id="a8348-112">**Cross-platform:** .NET Core provides key functionality to implement the app features you need and reuse this code regardless of your platform target.</span></span> <span data-ttu-id="a8348-113">它当前支持三种主要的操作系统 (OS)：Windows、 Linux 和 macOS。</span><span class="sxs-lookup"><span data-stu-id="a8348-113">It currently supports three main operating systems (OS): Windows, Linux and macOS.</span></span> <span data-ttu-id="a8348-114">可以编写无需修改即可跨受支持操作系统运行的应用和库。</span><span class="sxs-lookup"><span data-stu-id="a8348-114">You can write apps and libraries that run unmodified across supported operating systems.</span></span> <span data-ttu-id="a8348-115">若要查看受支持操作系统的列表，请访问 [.NET Core 路线图](https://github.com/dotnet/core/blob/master/roadmap.md)。</span><span class="sxs-lookup"><span data-stu-id="a8348-115">To see the list of supported operating systems, visit [.NET Core roadmap](https://github.com/dotnet/core/blob/master/roadmap.md).</span></span>
  
-   <span data-ttu-id="a8348-116">**开放源代码：**.NET 核心是 [.NET Foundation](http://www.dotnetfoundation.org/) 管理下的很多项目中的一个，并在 [GitHub](https://github.com/) 上提供。</span><span class="sxs-lookup"><span data-stu-id="a8348-116">**Open source:** .NET Core is one of the many projects under the stewardship of the [.NET Foundation](http://www.dotnetfoundation.org/) and is available on [GitHub](https://github.com/).</span></span>  <span data-ttu-id="a8348-117">将 .NET 核心作为开放源代码项目促使开发过程更加透明并能提升社区的活跃度及参与度。</span><span class="sxs-lookup"><span data-stu-id="a8348-117">Having .NET Core as an open source project promotes a more transparent development process and promotes an active and engaged community.</span></span>  
  
-   <span data-ttu-id="a8348-118">**灵活部署：** 部署应用有两种主要方法：依赖框架的部署或独立部署。</span><span class="sxs-lookup"><span data-stu-id="a8348-118">**Flexible deployment:** there are two main ways to deploy your app: framework-dependent deployment or self-contained deployment.</span></span> <span data-ttu-id="a8348-119">使用依赖框架的部署时，仅安装应用和第三方依赖关系，而应用依赖于存在系统范围版本的 .NET 核心。</span><span class="sxs-lookup"><span data-stu-id="a8348-119">With framework-dependent deployment, only your app and third-party dependencies are installed and your app depends on a system-wide version of .NET Core to be present.</span></span>  <span data-ttu-id="a8348-120">使用独立部署时，用于构建应用程序的 .NET 核心版本随应用和第三方依赖关系一同部署，并可与其他版本并行运行。</span><span class="sxs-lookup"><span data-stu-id="a8348-120">With self-contained deployment, the .NET Core version used to build your application is also deployed along with your app and third-party dependencies and can run side-by-side with other versions.</span></span>    <span data-ttu-id="a8348-121">有关详细信息，请参阅 [.NET 核心应用程序部署](../../core/deploying/index.md)。</span><span class="sxs-lookup"><span data-stu-id="a8348-121">For more information, see [.NET Core Application Deployment](../../core/deploying/index.md).</span></span>

-   <span data-ttu-id="a8348-122">模块化：.NET Core 为模块化，因为它通过 NuGet 以较小的程序集包发布。</span><span class="sxs-lookup"><span data-stu-id="a8348-122">**Modular:** .NET Core is modular because it's released through NuGet in smaller assembly packages.</span></span> <span data-ttu-id="a8348-123">与包含了大部分核心功能的大型程序集不同，.NET 核心作为以功能为中心的小型数据包提供。</span><span class="sxs-lookup"><span data-stu-id="a8348-123">Rather than one large assembly that contains most of the core functionality, .NET Core is made available as smaller feature-centric packages.</span></span> <span data-ttu-id="a8348-124">这为我们提供了更加灵活的开发模型，允许优化应用使其仅包含所需的 NuGet 程序包。</span><span class="sxs-lookup"><span data-stu-id="a8348-124">This enables a more agile development model for us and allows you to optimize your app to include just the NuGet packages you need.</span></span> <span data-ttu-id="a8348-125">较小的应用图面区域的优势包括：提升安全性、减少维护、提高性能并采用按使用情况付费的模式降低成本。</span><span class="sxs-lookup"><span data-stu-id="a8348-125">The benefits of a smaller app surface area include tighter security, reduced servicing, improved performance, and decreased costs in a pay-for-what-you-use model.</span></span>  
  
## <a name="the-net-core-platform"></a><span data-ttu-id="a8348-126">.NET 核心平台</span><span class="sxs-lookup"><span data-stu-id="a8348-126">The .NET Core Platform</span></span>  
 <span data-ttu-id="a8348-127">.NET 核心平台由一些组件构成，其中包括托管的编译器、运行时、基类库和大量应用程序模型，如 ASP.NET 核心。</span><span class="sxs-lookup"><span data-stu-id="a8348-127">The .NET Core platform is made of several components, which includes the managed compilers, the runtime, the base class libraries, and numerous application models, such as ASP.NET Core.</span></span> <span data-ttu-id="a8348-128">可以通过访问以下 [GitHub](https://github.com/) 存储库来了解更多关于不同组件的信息并参与进来：</span><span class="sxs-lookup"><span data-stu-id="a8348-128">You can learn more about the different components and get engaged, by visiting the following [GitHub](https://github.com/) repos:</span></span>  
  
-   [<span data-ttu-id="a8348-129">.NET Core</span><span class="sxs-lookup"><span data-stu-id="a8348-129">.NET Core</span></span>](https://github.com/dotnet/core)  
  
-   [<span data-ttu-id="a8348-130">CoreFX - .NET Core foundational libraries</span><span class="sxs-lookup"><span data-stu-id="a8348-130">CoreFX - .NET Core foundational libraries</span></span>](https://github.com/dotnet/corefx)  
  
-   [<span data-ttu-id="a8348-131">CoreCLR - .NET Core runtime</span><span class="sxs-lookup"><span data-stu-id="a8348-131">CoreCLR - .NET Core runtime</span></span>](https://github.com/dotnet/coreclr)  
  
-   [<span data-ttu-id="a8348-132">CLI - .NET Core command-line tools</span><span class="sxs-lookup"><span data-stu-id="a8348-132">CLI - .NET Core command-line tools</span></span>](https://github.com/dotnet/cli)  
  
-   [<span data-ttu-id="a8348-133">Roslyn - .NET Compiler Platform</span><span class="sxs-lookup"><span data-stu-id="a8348-133">Roslyn - .NET Compiler Platform</span></span>](https://github.com/dotnet/roslyn)  
  
-   [<span data-ttu-id="a8348-134">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="a8348-134">ASP.NET Core</span></span>](https://github.com/aspnet/home)  
  
## <a name="see-also"></a><span data-ttu-id="a8348-135">请参阅</span><span class="sxs-lookup"><span data-stu-id="a8348-135">See Also</span></span>  
 [<span data-ttu-id="a8348-136">.NET Core主页</span><span class="sxs-lookup"><span data-stu-id="a8348-136">.NET Core homepage</span></span>](https://www.microsoft.com/net/core)  
 [<span data-ttu-id="a8348-137">.NET Core 指南</span><span class="sxs-lookup"><span data-stu-id="a8348-137">.NET Core Guide</span></span>](../../core/index.md)  
 [<span data-ttu-id="a8348-138">ASP.NET 核心文档</span><span class="sxs-lookup"><span data-stu-id="a8348-138">ASP.NET Core Documentation</span></span>](/aspnet/core/)
