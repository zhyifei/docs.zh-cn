---
title: "一般性指导原则"
description: "为容器化的.NET 应用程序的.NET 微服务体系结构 |一般性指导原则"
keywords: "Docker, 微服务, ASP.NET, 容器"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/18/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: 22dea926e77079e4f543934613ced13a28b2dae6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="general-guidance"></a><span data-ttu-id="f1fdc-104">一般性指导原则</span><span class="sxs-lookup"><span data-stu-id="f1fdc-104">General guidance</span></span>

<span data-ttu-id="f1fdc-105">本部分提供何时选择.NET 核心或.NET Framework 的摘要。</span><span class="sxs-lookup"><span data-stu-id="f1fdc-105">This section provides a summary of when to choose .NET Core or .NET Framework.</span></span> <span data-ttu-id="f1fdc-106">我们提供有关以下各节中的这些选项的更多详细信息。</span><span class="sxs-lookup"><span data-stu-id="f1fdc-106">We provide more details about these choices in the sections that follow.</span></span>

<span data-ttu-id="f1fdc-107">你应该用于.NET 核心与 Linux 或 Windows 容器，容器化 Docker 服务器应用程序时：</span><span class="sxs-lookup"><span data-stu-id="f1fdc-107">You should use .NET Core, with Linux or Windows Containers, for your containerized Docker server application when:</span></span>

-   <span data-ttu-id="f1fdc-108">用户有跨平台需求。</span><span class="sxs-lookup"><span data-stu-id="f1fdc-108">You have cross-platform needs.</span></span> <span data-ttu-id="f1fdc-109">例如，你想要使用 Linux 和 Windows 容器。</span><span class="sxs-lookup"><span data-stu-id="f1fdc-109">For example, you want to use both Linux and Windows Containers.</span></span>

-   <span data-ttu-id="f1fdc-110">你的应用程序体系结构基于微服务。</span><span class="sxs-lookup"><span data-stu-id="f1fdc-110">Your application architecture is based on microservices.</span></span>

-   <span data-ttu-id="f1fdc-111">你需要以快速启动容器并需要每个容器，以实现更好的密度或每个硬件单位的多个容器内存占用较小，以便降低成本。</span><span class="sxs-lookup"><span data-stu-id="f1fdc-111">You need to start containers fast and want a small footprint per container to achieve better density or more containers per hardware unit in order to lower your costs.</span></span>

<span data-ttu-id="f1fdc-112">简单地说，在创建新容器化的.NET 应用程序时，你应考虑.NET 核心作为默认选项。</span><span class="sxs-lookup"><span data-stu-id="f1fdc-112">In short, when you create new containerized .NET applications, you should consider .NET Core as the default choice.</span></span> <span data-ttu-id="f1fdc-113">它具有许多好处，并最能满足容器基本原理和使用的样式。</span><span class="sxs-lookup"><span data-stu-id="f1fdc-113">It has many benefits and fits best with the containers philosophy and style of working.</span></span>

<span data-ttu-id="f1fdc-114">使用.NET Core 的另一个好处是你可以运行在同一台计算机中的应用程序的并行.NET 版本。</span><span class="sxs-lookup"><span data-stu-id="f1fdc-114">An additional benefit of using .NET Core is that you can run side by side .NET versions for applications within the same machine.</span></span> <span data-ttu-id="f1fdc-115">这一优势是为服务器或虚拟机不使用容器，更重要，因为容器隔离的.NET 应用程序所需的版本。</span><span class="sxs-lookup"><span data-stu-id="f1fdc-115">This benefit is more important for servers or VMs that do not use containers, because containers isolate the versions of .NET that the app needs.</span></span> <span data-ttu-id="f1fdc-116">（只要它们是与基础操作系统兼容。）</span><span class="sxs-lookup"><span data-stu-id="f1fdc-116">(As long as they are compatible with the underlying OS.)</span></span>

<span data-ttu-id="f1fdc-117">应使用.NET Framework 中，使用 Windows 容器，容器化 Docker 服务器应用程序时：</span><span class="sxs-lookup"><span data-stu-id="f1fdc-117">You should use .NET Framework, with Windows Containers, for your containerized Docker server application when:</span></span>

-   <span data-ttu-id="f1fdc-118">你的应用程序当前使用.NET Framework 和 Windows 上具有强依赖关系。</span><span class="sxs-lookup"><span data-stu-id="f1fdc-118">Your application currently uses .NET Framework and has strong dependencies on Windows.</span></span>

-   <span data-ttu-id="f1fdc-119">你需要使用.NET Core 不支持的 Windows Api。</span><span class="sxs-lookup"><span data-stu-id="f1fdc-119">You need to use Windows APIs that are not supported by .NET Core.</span></span>

-   <span data-ttu-id="f1fdc-120">你需要使用第三方.NET 库或不可用于.NET 核心的 NuGet 包。</span><span class="sxs-lookup"><span data-stu-id="f1fdc-120">You need to use third-party .NET libraries or NuGet packages that are not available for .NET Core.</span></span>

<span data-ttu-id="f1fdc-121">在 Docker 上使用.NET Framework 可以提高你的部署体验通过最大限度部署问题。</span><span class="sxs-lookup"><span data-stu-id="f1fdc-121">Using .NET Framework on Docker can improve your deployment experiences by minimizing deployment issues.</span></span> <span data-ttu-id="f1fdc-122">这[ *"提升和移动方案*](https://aka.ms/liftandshiftwithcontainersebook)对于 containerizing 旧开发的应用程序最初使用传统的.NET Framework 中，如 ASP.NET WebForms，MVC web 应用程序或 WCF （非常重要Windows Communication Foundation) 服务。</span><span class="sxs-lookup"><span data-stu-id="f1fdc-122">This [*"lift and shift" scenario*](https://aka.ms/liftandshiftwithcontainersebook) is important for containerizing legacy applications that were originally developed with the traditional .NET Framework, like ASP.NET WebForms, MVC web apps or WCF (Windows Communication Foundation) services.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="f1fdc-123">其他资源</span><span class="sxs-lookup"><span data-stu-id="f1fdc-123">Additional resources</span></span>

-   <span data-ttu-id="f1fdc-124">**电子书： 更新现有的.NET Framework 应用程序与 Azure 和 Windows 容器**
    [*https://aka.ms/liftandshiftwithcontainersebook*](https://aka.ms/liftandshiftwithcontainersebook)</span><span class="sxs-lookup"><span data-stu-id="f1fdc-124">**e-book: Modernize existing .NET Framework applications with Azure and Windows Containers**
[*https://aka.ms/liftandshiftwithcontainersebook*](https://aka.ms/liftandshiftwithcontainersebook)</span></span>

-   <span data-ttu-id="f1fdc-125">**示例应用程序： 现代化的旧新的 ASP.NET web 应用程序可通过使用 Windows 容器**
    [*https://aka.ms/eshopmodernizing*](https://aka.ms/eshopmodernizing)</span><span class="sxs-lookup"><span data-stu-id="f1fdc-125">**Sample apps: Modernization of legacy ASP.NET web apps by using Windows Containers**
[*https://aka.ms/eshopmodernizing*](https://aka.ms/eshopmodernizing)</span></span>


>[!div class="step-by-step"]
<span data-ttu-id="f1fdc-126">[以前](index.md) [下一步] (net-核心-容器-scenarios.md)</span><span class="sxs-lookup"><span data-stu-id="f1fdc-126">[Previous] (index.md) [Next] (net-core-container-scenarios.md)</span></span>
