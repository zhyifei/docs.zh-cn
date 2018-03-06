---
title: "演练和技术获取启动的概述"
description: "更新现有的.NET 应用程序与 Azure 云和 Windows 容器 |演练和技术获取启动的概述"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/26/2017
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: bced3bed84d138dbda4f322322213b47c0159016
ms.sourcegitcommit: c3957fdb990060559d73cca44ab3e2c7b4d049c0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/05/2018
---
# <a name="walkthroughs-and-technical-get-started-overview"></a><span data-ttu-id="69c8d-103">演练和技术获取启动的概述</span><span class="sxs-lookup"><span data-stu-id="69c8d-103">Walkthroughs and technical get started overview</span></span> 

<span data-ttu-id="69c8d-104">若要限制此图书的大小，我们进行了其他技术文档和完整的演练的 GitHub 存储库中可用。</span><span class="sxs-lookup"><span data-stu-id="69c8d-104">To limit the size of this e-book, we've made additional technical documentation and the full walkthroughs available in a GitHub repo.</span></span> <span data-ttu-id="69c8d-105">此第章所述的演练联机系列介绍基于 Windows 容器和部署到 Azure 的多个环境的分步设置。</span><span class="sxs-lookup"><span data-stu-id="69c8d-105">The online series of walkthroughs that is described in this chapter covers the step-by-step setup of the multiple environments that are based on Windows Containers, and deployment to Azure.</span></span>

<span data-ttu-id="69c8d-106">以下各节介绍了每个演练是有关及其目标，其高级愿景的并提供示意图所涉及的任务。</span><span class="sxs-lookup"><span data-stu-id="69c8d-106">The following sections explain what each walkthrough is about-its objectives, its high-level vision-and provides a diagram of the tasks that are involved.</span></span> <span data-ttu-id="69c8d-107">你可以获取本身的演练中*eShopModernizing*在应用程序 GitHub 存储库 wiki [https://github.com/dotnet-architecture/eShopModernizing/wiki](https://github.com/dotnet-architecture/eShopModernizing/wiki)。</span><span class="sxs-lookup"><span data-stu-id="69c8d-107">You can get the walkthroughs themselves in the *eShopModernizing* apps GitHub repo wiki at [https://github.com/dotnet-architecture/eShopModernizing/wiki](https://github.com/dotnet-architecture/eShopModernizing/wiki).</span></span>

# <a name="technical-walkthrough-list"></a><span data-ttu-id="69c8d-108">技术演练列表</span><span class="sxs-lookup"><span data-stu-id="69c8d-108">Technical walkthrough list</span></span>

<span data-ttu-id="69c8d-109">以下入门演练提供了示例应用，你可以提升和移动通过使用容器，并且通过在 Azure 中使用多个部署选项然后移动的一致和全面技术指南。</span><span class="sxs-lookup"><span data-stu-id="69c8d-109">The following get-started walkthroughs provide consistent and comprehensive technical guidance for sample apps that you can lift and shift by using containers, and then move by using multiple deployment choices in Azure.</span></span>

<span data-ttu-id="69c8d-110">下面的演练的每个使用新示例 eShopLegacy 和 eShopModernizing 应用程序，它们可在 GitHub 上[https://github.com/dotnet-architecture/eShopModernizing](https://github.com/dotnet-architecture/eShopModernizing)。</span><span class="sxs-lookup"><span data-stu-id="69c8d-110">Each of the following walkthroughs uses the new sample eShopLegacy and eShopModernizing apps, which are available on GitHub at [https://github.com/dotnet-architecture/eShopModernizing](https://github.com/dotnet-architecture/eShopModernizing).</span></span>

-   <span data-ttu-id="69c8d-111">**电子商店旧应用的教程**</span><span class="sxs-lookup"><span data-stu-id="69c8d-111">**Tour of eShop legacy apps**</span></span>

-   <span data-ttu-id="69c8d-112">**化你现有的.NET 应用程序，与 Windows 容器**</span><span class="sxs-lookup"><span data-stu-id="69c8d-112">**Containerize your existing .NET applications with Windows Containers**</span></span>

-   <span data-ttu-id="69c8d-113">**将 Windows 容器基于应用程序部署到 Azure Vm**</span><span class="sxs-lookup"><span data-stu-id="69c8d-113">**Deploy your Windows Containers-based app to Azure VMs**</span></span>

-   <span data-ttu-id="69c8d-114">**将您的 Windows 容器基于应用程序部署到 Azure 容器服务中的 Kubernetes**</span><span class="sxs-lookup"><span data-stu-id="69c8d-114">**Deploy your Windows Containers-based apps to Kubernetes in Azure Container Service**</span></span>

-   <span data-ttu-id="69c8d-115">**将您的 Windows 容器基于应用程序部署到 Azure Service Fabric**</span><span class="sxs-lookup"><span data-stu-id="69c8d-115">**Deploy your Windows Containers-based apps to Azure Service Fabric**</span></span>

## <a name="walkthrough-1-tour-of-eshop-legacy-apps"></a><span data-ttu-id="69c8d-116">电子商店旧应用程序的演练 1： 教程</span><span class="sxs-lookup"><span data-stu-id="69c8d-116">Walkthrough 1: Tour of eShop legacy apps</span></span>

### <a name="technical-walkthrough-availability"></a><span data-ttu-id="69c8d-117">技术演练可用性</span><span class="sxs-lookup"><span data-stu-id="69c8d-117">Technical walkthrough availability</span></span>

<span data-ttu-id="69c8d-118">完整技术的演练会出现在 eShopModernizing GitHub 存储库 wiki:</span><span class="sxs-lookup"><span data-stu-id="69c8d-118">The full technical walkthrough is available in the eShopModernizing GitHub repo wiki:</span></span>

[<span data-ttu-id="69c8d-119">https://github.com/dotnet-architecture/eShopModernizing/wiki/01.-Tour-on-eShopModernizing-apps-implementation-code</span><span class="sxs-lookup"><span data-stu-id="69c8d-119">https://github.com/dotnet-architecture/eShopModernizing/wiki/01.-Tour-on-eShopModernizing-apps-implementation-code</span></span>](https://github.com/dotnet-architecture/eShopModernizing/wiki/01.-Tour-on-eShopModernizing-apps-implementation-code)

### <a name="overview"></a><span data-ttu-id="69c8d-120">概述</span><span class="sxs-lookup"><span data-stu-id="69c8d-120">Overview</span></span>

<span data-ttu-id="69c8d-121">在本演练中，你可以浏览初始实施中的两个示例旧版应用程序。</span><span class="sxs-lookup"><span data-stu-id="69c8d-121">In this walkthrough, you can explore the initial implementation of two sample legacy applications.</span></span> <span data-ttu-id="69c8d-122">这两个示例应用具有单一的体系结构，并使用传统的 ASP.NET 创建的。</span><span class="sxs-lookup"><span data-stu-id="69c8d-122">Both sample apps have a monolithic architecture, and were created by using classic ASP.NET.</span></span> <span data-ttu-id="69c8d-123">一个应用程序基于 ASP.NET 4.x MVC;第二个应用程序基于 ASP.NET 4.x Web 窗体。</span><span class="sxs-lookup"><span data-stu-id="69c8d-123">One application is based on ASP.NET 4.x MVC; the second application is based on ASP.NET 4.x Web Forms.</span></span> <span data-ttu-id="69c8d-124">这两个应用程序都位于[eShopModernizing GitHub 存储库](https://github.com/dotnet-architecture/eShopModernizing)。</span><span class="sxs-lookup"><span data-stu-id="69c8d-124">Both applications are in the [eShopModernizing GitHub repo](https://github.com/dotnet-architecture/eShopModernizing).</span></span>

<span data-ttu-id="69c8d-125">你可以化这两个示例应用，方式类似于化经典[Windows Communication Foundation](../../framework/wcf/whats-wcf.md) (WCF) 应用程序将使用作为桌面应用程序。</span><span class="sxs-lookup"><span data-stu-id="69c8d-125">You can containerize both sample apps, similar to the way you can containerize a classic [Windows Communication Foundation](../../framework/wcf/whats-wcf.md) (WCF) application to be consumed as a desktop application.</span></span> <span data-ttu-id="69c8d-126">有关示例，请参阅[eShopModernizingWCFWinForms](https://github.com/dotnet-architecture/eShopModernizingWCFWinForms)。</span><span class="sxs-lookup"><span data-stu-id="69c8d-126">For an example, see [eShopModernizingWCFWinForms](https://github.com/dotnet-architecture/eShopModernizingWCFWinForms).</span></span>

### <a name="goals"></a><span data-ttu-id="69c8d-127">目标</span><span class="sxs-lookup"><span data-stu-id="69c8d-127">Goals</span></span>

<span data-ttu-id="69c8d-128">本演练的主要目的只是以熟悉如何利用这些应用，并使用其代码和配置。</span><span class="sxs-lookup"><span data-stu-id="69c8d-128">The main goal of this walkthrough is simply to get familiar with these apps, and with their code and configuration.</span></span> <span data-ttu-id="69c8d-129">你可以配置的应用，以便它们生成和使用模拟数据，而无需使用 SQL 数据库，以进行测试。</span><span class="sxs-lookup"><span data-stu-id="69c8d-129">You can configure the apps so that they generate and use mock data, without using the SQL database, for testing purposes.</span></span> <span data-ttu-id="69c8d-130">此可选配置基于依赖关系注入分离的方式。</span><span class="sxs-lookup"><span data-stu-id="69c8d-130">This optional config is based on dependency injection, in a decoupled way.</span></span>

### <a name="scenario"></a><span data-ttu-id="69c8d-131">方案</span><span class="sxs-lookup"><span data-stu-id="69c8d-131">Scenario</span></span>

<span data-ttu-id="69c8d-132">图 5-1 显示简单的方案中的原始的旧版应用程序。</span><span class="sxs-lookup"><span data-stu-id="69c8d-132">Figure 5-1 shows the simple scenario of the original legacy applications.</span></span>

> ![简单的体系结构方案中的原始的旧版应用程序](./media/image5-1.png)
>
> <span data-ttu-id="69c8d-134">**图 5-1**。</span><span class="sxs-lookup"><span data-stu-id="69c8d-134">**Figure 5-1.**</span></span> <span data-ttu-id="69c8d-135">简单的体系结构方案中的原始的旧版应用程序</span><span class="sxs-lookup"><span data-stu-id="69c8d-135">Simple architecture scenario of the original legacy applications</span></span>

<span data-ttu-id="69c8d-136">从业务域角度来看，这两个应用程序管理功能提供相同的目录。</span><span class="sxs-lookup"><span data-stu-id="69c8d-136">From a business domain perspective, both apps offer the same catalog management features.</span></span> <span data-ttu-id="69c8d-137">电子商店企业团队的成员将使用应用来查看和编辑产品目录。</span><span class="sxs-lookup"><span data-stu-id="69c8d-137">Members of the eShop enterprise team would use the app to view and edit the product catalog.</span></span> <span data-ttu-id="69c8d-138">图 5-2 显示初始应用程序屏幕快照。</span><span class="sxs-lookup"><span data-stu-id="69c8d-138">Figure 5-2 shows the initial app screenshots.</span></span>

![ASP.NET MVC 和 ASP.NET Web 窗体应用程序 （现有/旧技术）](./media/image5-2.png)

> <span data-ttu-id="69c8d-140">**图 5-2。**</span><span class="sxs-lookup"><span data-stu-id="69c8d-140">**Figure 5-2.**</span></span> <span data-ttu-id="69c8d-141">ASP.NET MVC 和 ASP.NET Web 窗体应用程序 （现有/旧技术）</span><span class="sxs-lookup"><span data-stu-id="69c8d-141">ASP.NET MVC and ASP.NET Web Forms applications (existing/legacy technologies)</span></span>

<span data-ttu-id="69c8d-142">这些是用于浏览和修改目录条目的 web 应用程序。</span><span class="sxs-lookup"><span data-stu-id="69c8d-142">These are web applications that are used to browse and modify catalog entries.</span></span> <span data-ttu-id="69c8d-143">实际上，这两个应用提供相同的业务/功能的功能，我们只是为了进行比较。</span><span class="sxs-lookup"><span data-stu-id="69c8d-143">The fact that both apps deliver the same business/functional features is simply for comparison purposes.</span></span> <span data-ttu-id="69c8d-144">你可以看到用于通过使用 ASP.NET MVC 和 ASP.NET Web 窗体框架的应用的类似现代化进程。</span><span class="sxs-lookup"><span data-stu-id="69c8d-144">You can see a similar modernization process for apps that were created by using the ASP.NET MVC and ASP.NET Web Forms frameworks.</span></span>

<span data-ttu-id="69c8d-145">依赖项在 ASP.NET 4.x 或更早版本 （不管是针对 MVC 或 Web 窗体） 意味着除非通过使用 ASP.NET 核心 MVC 完全重新编写的代码，这些应用程序不会运行在.NET Core 上。</span><span class="sxs-lookup"><span data-stu-id="69c8d-145">Dependencies in ASP.NET 4.x or earlier versions (either for MVC or for Web Forms) means that these applications won't run on .NET Core unless the code is fully rewritten by using ASP.NET Core MVC.</span></span> <span data-ttu-id="69c8d-146">此示例演示的点，如果你不想重新设计，或重写代码，你可以化现有应用程序，并继续使用相同的.NET 技术和相同的代码。</span><span class="sxs-lookup"><span data-stu-id="69c8d-146">This demonstrates the point that if you don't want to re-architect or rewrite code, you can containerize existing applications, and still use the same .NET technologies and the same code.</span></span> <span data-ttu-id="69c8d-147">你可以看到类似这样在容器中，而无需对旧代码的任何更改的应用程序的运行方式。</span><span class="sxs-lookup"><span data-stu-id="69c8d-147">You can see how you can run applications like these in containers, without any changes to legacy code.</span></span>

### <a name="benefits"></a><span data-ttu-id="69c8d-148">优点</span><span class="sxs-lookup"><span data-stu-id="69c8d-148">Benefits</span></span>

<span data-ttu-id="69c8d-149">本演练的好处很简单： 只需熟悉的代码和应用程序的配置，基于依赖关系注入。</span><span class="sxs-lookup"><span data-stu-id="69c8d-149">The benefits of this walkthrough are simple: Just get familiar with the code and application configuration, based on dependency injection.</span></span> <span data-ttu-id="69c8d-150">然后，当你化并在将来部署到多个环境，您可以使用此方法尝试。</span><span class="sxs-lookup"><span data-stu-id="69c8d-150">Then, you can experiment with this approach when you containerize and deploy to multiple environments in the future.</span></span>

### <a name="next-steps"></a><span data-ttu-id="69c8d-151">后续步骤</span><span class="sxs-lookup"><span data-stu-id="69c8d-151">Next steps</span></span>

<span data-ttu-id="69c8d-152">在 GitHub wiki 上浏览此更深入的内容：</span><span class="sxs-lookup"><span data-stu-id="69c8d-152">Explore this content more in-depth on the GitHub wiki:</span></span>

[<span data-ttu-id="69c8d-153">https://github.com/dotnet-architecture/eShopModernizing/wiki/01.-Tour-on-eShopModernizing-apps-implementation-code</span><span class="sxs-lookup"><span data-stu-id="69c8d-153">https://github.com/dotnet-architecture/eShopModernizing/wiki/01.-Tour-on-eShopModernizing-apps-implementation-code</span></span>](https://github.com/dotnet-architecture/eShopModernizing/wiki/01.-Tour-on-eShopModernizing-apps-implementation-code)

## <a name="walkthrough-2-containerize-your-existing-net-applications-with-windows-containers"></a><span data-ttu-id="69c8d-154">演练 2： 化你现有的.NET 应用程序，与 Windows 容器</span><span class="sxs-lookup"><span data-stu-id="69c8d-154">Walkthrough 2: Containerize your existing .NET applications with Windows Containers</span></span>

### <a name="technical-walkthrough-availability"></a><span data-ttu-id="69c8d-155">技术演练可用性</span><span class="sxs-lookup"><span data-stu-id="69c8d-155">Technical walkthrough availability</span></span>

<span data-ttu-id="69c8d-156">完整技术的演练会出现在 eShopModernizing GitHub 存储库 wiki:</span><span class="sxs-lookup"><span data-stu-id="69c8d-156">The full technical walkthrough is available in the eShopModernizing GitHub repo wiki:</span></span>

[<span data-ttu-id="69c8d-157">https://github.com/dotnet-architecture/eShopModernizing/wiki/02.-How-to-containerize-the-.NET-Framework-web-apps-with-Windows-Containers-and-Docker</span><span class="sxs-lookup"><span data-stu-id="69c8d-157">https://github.com/dotnet-architecture/eShopModernizing/wiki/02.-How-to-containerize-the-.NET-Framework-web-apps-with-Windows-Containers-and-Docker</span></span>](https://github.com/dotnet-architecture/eShopModernizing/wiki/02.-How-to-containerize-the-.NET-Framework-web-apps-with-Windows-Containers-and-Docker)

### <a name="overview"></a><span data-ttu-id="69c8d-158">概述</span><span class="sxs-lookup"><span data-stu-id="69c8d-158">Overview</span></span>

<span data-ttu-id="69c8d-159">使用 Windows 容器来提高部署的现有.NET 应用程序，如基于 MVC、 Web 窗体或 WCF，向生产、 开发和测试环境。</span><span class="sxs-lookup"><span data-stu-id="69c8d-159">Use Windows Containers to improve deployment of existing .NET applications, like those based on MVC, Web Forms, or WCF, to production, development, and test environments.</span></span>

### <a name="goals"></a><span data-ttu-id="69c8d-160">目标</span><span class="sxs-lookup"><span data-stu-id="69c8d-160">Goals</span></span>

<span data-ttu-id="69c8d-161">此演练的目的是显示 containerizing 现有.NET Framework 应用程序的几个选项。</span><span class="sxs-lookup"><span data-stu-id="69c8d-161">The goal of this walkthrough is to show you several options for containerizing an existing .NET Framework application.</span></span> <span data-ttu-id="69c8d-162">你可以：</span><span class="sxs-lookup"><span data-stu-id="69c8d-162">You can:</span></span>

-   <span data-ttu-id="69c8d-163">通过使用化你的应用程序[Visual Studio 2017 Tools for Docker](/aspnet/core/host-and-deploy/docker/visual-studio-tools-for-docker) （Visual Studio 2017 年 1 或更高版本）。</span><span class="sxs-lookup"><span data-stu-id="69c8d-163">Containerize your application by using [Visual Studio 2017 Tools for Docker](/aspnet/core/host-and-deploy/docker/visual-studio-tools-for-docker) (Visual Studio 2017 or later versions).</span></span>

-   <span data-ttu-id="69c8d-164">通过手动添加化你的应用程序[Dockerfile](https://docs.docker.com/engine/reference/builder/)，，然后使用[Docker CLI](https://docs.docker.com/engine/reference/commandline/cli/)。</span><span class="sxs-lookup"><span data-stu-id="69c8d-164">Containerize your application by manually adding a [Dockerfile](https://docs.docker.com/engine/reference/builder/), and then using the [Docker CLI](https://docs.docker.com/engine/reference/commandline/cli/).</span></span>

-   <span data-ttu-id="69c8d-165">通过使用化你的应用程序[Img2Docker](https://github.com/docker/communitytools-image2docker-win)工具 （从 Docker 的开源工具）。</span><span class="sxs-lookup"><span data-stu-id="69c8d-165">Containerize your application by using the [Img2Docker](https://github.com/docker/communitytools-image2docker-win) tool (an open-source tool from Docker).</span></span>

<span data-ttu-id="69c8d-166">本演练主要针对 Visual Studio 2017 Tools for Docker 方法，但其他两种方法不符合使用 Dockerfile 非常相似。</span><span class="sxs-lookup"><span data-stu-id="69c8d-166">This walkthrough focuses on the Visual Studio 2017 Tools for Docker approach, but the other two approaches are fairly similar in regards to using Dockerfiles.</span></span>

### <a name="scenario"></a><span data-ttu-id="69c8d-167">方案</span><span class="sxs-lookup"><span data-stu-id="69c8d-167">Scenario</span></span>

<span data-ttu-id="69c8d-168">图 5-3 显示为容器化电子商店旧版应用程序方案。</span><span class="sxs-lookup"><span data-stu-id="69c8d-168">Figure 5-3 shows the scenario for containerized eShop legacy applications.</span></span>

> ![在开发环境中的容器化应用程序的简化的体系结构示意图](./media/image5-3.png)
>
> <span data-ttu-id="69c8d-170">**图 5-3。**</span><span class="sxs-lookup"><span data-stu-id="69c8d-170">**Figure 5-3.**</span></span> <span data-ttu-id="69c8d-171">在开发环境中的容器化应用程序的简化的体系结构示意图</span><span class="sxs-lookup"><span data-stu-id="69c8d-171">Simplified architecture diagram of containerized applications in a development environment</span></span>

### <a name="benefits"></a><span data-ttu-id="69c8d-172">优点</span><span class="sxs-lookup"><span data-stu-id="69c8d-172">Benefits</span></span>

<span data-ttu-id="69c8d-173">有在容器中运行你的整体应用程序的优点。</span><span class="sxs-lookup"><span data-stu-id="69c8d-173">There are advantages to running your monolithic application in a container.</span></span> <span data-ttu-id="69c8d-174">首先，你创建应用程序映像。</span><span class="sxs-lookup"><span data-stu-id="69c8d-174">First, you create an image for the application.</span></span> <span data-ttu-id="69c8d-175">从那一刻开始，每个部署在相同环境中运行。</span><span class="sxs-lookup"><span data-stu-id="69c8d-175">From that point on, every deployment runs in the same environment.</span></span> <span data-ttu-id="69c8d-176">每个容器使用相同的操作系统版本、 具有相同版本的依赖项安装、 使用相同的.NET framework 版本，并且使用相同的过程生成。</span><span class="sxs-lookup"><span data-stu-id="69c8d-176">Every container uses the same OS version, has the same version of dependencies installed, uses the same .NET framework version, and is built by using the same process.</span></span> <span data-ttu-id="69c8d-177">基本上，你通过使用的 Docker 映像控制你的应用程序的依赖关系。</span><span class="sxs-lookup"><span data-stu-id="69c8d-177">Basically, you control the dependencies of your application by using a Docker image.</span></span> <span data-ttu-id="69c8d-178">部署容器时，与应用程序传送依赖关系。</span><span class="sxs-lookup"><span data-stu-id="69c8d-178">The dependencies travel with the application when you deploy the containers.</span></span>

<span data-ttu-id="69c8d-179">另一个好处是开发人员可以由 Windows 容器提供一致的环境中运行应用程序。</span><span class="sxs-lookup"><span data-stu-id="69c8d-179">An additional benefit is that developers can run the application in the consistent environment that's provided by Windows Containers.</span></span> <span data-ttu-id="69c8d-180">可以立即发现仅显示某些版本的问题，而不是在过渡或生产环境中提供。</span><span class="sxs-lookup"><span data-stu-id="69c8d-180">Issues that appear only with certain versions can be spotted immediately, instead of surfacing in a staging or production environment.</span></span> <span data-ttu-id="69c8d-181">在容器中运行应用程序，开发团队的成员使用的开发环境中的差异将重要小于。</span><span class="sxs-lookup"><span data-stu-id="69c8d-181">Differences in development environments used by members of the development team matter less when applications run in containers.</span></span>

<span data-ttu-id="69c8d-182">容器化应用程序还具有更简单的横向扩展曲线。</span><span class="sxs-lookup"><span data-stu-id="69c8d-182">Containerized applications also have a flatter scale-out curve.</span></span> <span data-ttu-id="69c8d-183">容器化应用程序，可以有多个应用程序和服务实例 （基于容器） 中的 VM 或比较每个计算机的常规应用程序部署到的物理计算机。</span><span class="sxs-lookup"><span data-stu-id="69c8d-183">Containerized apps enable you to have more application and service instances (based on containers) in a VM or physical machine compared to regular application deployments per machine.</span></span> <span data-ttu-id="69c8d-184">这将转换为较高的密度和更少所需资源，尤其是当你使用 orchestrators Kubernetes 或 Service Fabric 等。</span><span class="sxs-lookup"><span data-stu-id="69c8d-184">This translates to higher density and fewer required resources, especially when you use orchestrators like Kubernetes or Service Fabric.</span></span>

<span data-ttu-id="69c8d-185">容器化，在理想情况下，不需要的应用程序代码进行任何更改 (C\#)。</span><span class="sxs-lookup"><span data-stu-id="69c8d-185">Containerization, in ideal situations, does not require making any changes to the application code (C\#).</span></span> <span data-ttu-id="69c8d-186">在大多数情况下，你只需 Docker 部署元数据文件 （Dockerfile 和 Docker Compose 文件）。</span><span class="sxs-lookup"><span data-stu-id="69c8d-186">In most scenarios, you just need the Docker deployment metadata files (Dockerfiles and Docker Compose files).</span></span>

### <a name="next-steps"></a><span data-ttu-id="69c8d-187">后续步骤</span><span class="sxs-lookup"><span data-stu-id="69c8d-187">Next steps</span></span>

<span data-ttu-id="69c8d-188">浏览 GitHub wiki 上的此内容更深入： [https://github.com/dotnet-architecture/eShopModernizing/wiki/02.-How-to-containerize-the-.NET-Framework-web-apps-with-Windows-Containers-and-Docker](https://github.com/dotnet-architecture/eShopModernizing/wiki/02.-How-to-containerize-the-.NET-Framework-web-apps-with-Windows-Containers-and-Docker)</span><span class="sxs-lookup"><span data-stu-id="69c8d-188">Explore this content more in-depth on the GitHub wiki: [https://github.com/dotnet-architecture/eShopModernizing/wiki/02.-How-to-containerize-the-.NET-Framework-web-apps-with-Windows-Containers-and-Docker](https://github.com/dotnet-architecture/eShopModernizing/wiki/02.-How-to-containerize-the-.NET-Framework-web-apps-with-Windows-Containers-and-Docker)</span></span>

## <a name="walkthrough-3-deploy-your-windows-containers-based-app-to-azure-vms"></a><span data-ttu-id="69c8d-189">演练 3： 将 Windows 容器基于应用程序部署到 Azure Vm</span><span class="sxs-lookup"><span data-stu-id="69c8d-189">Walkthrough 3: Deploy your Windows Containers-based app to Azure VMs</span></span>

### <a name="technical-walkthrough-availability"></a><span data-ttu-id="69c8d-190">技术演练可用性</span><span class="sxs-lookup"><span data-stu-id="69c8d-190">Technical walkthrough availability</span></span>

<span data-ttu-id="69c8d-191">完整技术的演练会出现在 eShopModernizing GitHub 存储库 wiki:</span><span class="sxs-lookup"><span data-stu-id="69c8d-191">The full technical walkthrough is available in the eShopModernizing GitHub repo wiki:</span></span>

<span data-ttu-id="69c8d-192">[https://github.com/dotnet-architecture/eShopModernizing/wiki/03.-How-to-deploy-your-Windows-Containers-based-app-into-Azure-VMs-(Including-CI-CD)](https://github.com/dotnet-architecture/eShopModernizing/wiki/03.-How-to-deploy-your-Windows-Containers-based-app-into-Azure-VMs-(Including-CI-CD))</span><span class="sxs-lookup"><span data-stu-id="69c8d-192">[https://github.com/dotnet-architecture/eShopModernizing/wiki/03.-How-to-deploy-your-Windows-Containers-based-app-into-Azure-VMs-(Including-CI-CD)](https://github.com/dotnet-architecture/eShopModernizing/wiki/03.-How-to-deploy-your-Windows-Containers-based-app-into-Azure-VMs-(Including-CI-CD))</span></span>

### <a name="overview"></a><span data-ttu-id="69c8d-193">概述</span><span class="sxs-lookup"><span data-stu-id="69c8d-193">Overview</span></span>

<span data-ttu-id="69c8d-194">将部署到 Azure 中的 Windows Server 2016 VM 上的 Docker 主机，可以快速设置开发/测试/暂存环境。</span><span class="sxs-lookup"><span data-stu-id="69c8d-194">Deploying to a Docker host on a Windows Server 2016 VM in Azure lets you quickly set up dev/test/staging environments.</span></span> <span data-ttu-id="69c8d-195">它还会为你提供测试人员或业务用户，以验证应用程序的一个常见的位置。</span><span class="sxs-lookup"><span data-stu-id="69c8d-195">It also gives you a common place for testers or business users to validate the app.</span></span> <span data-ttu-id="69c8d-196">Vm 还可以是有效的 IaaS 生产环境。</span><span class="sxs-lookup"><span data-stu-id="69c8d-196">VMs also can be valid IaaS production environments.</span></span>

### <a name="goals"></a><span data-ttu-id="69c8d-197">目标</span><span class="sxs-lookup"><span data-stu-id="69c8d-197">Goals</span></span>

<span data-ttu-id="69c8d-198">此演练的目的是显示到基于 Windows Server 2016 或更高版本的 Azure Vm 中部署 Windows 容器时，你有多个替代项。</span><span class="sxs-lookup"><span data-stu-id="69c8d-198">The goal of this walkthrough is to show you the multiple alternatives you have when you deploy Windows Containers to Azure VMs that are based on Windows Server 2016 or later versions.</span></span>

### <a name="scenarios"></a><span data-ttu-id="69c8d-199">方案</span><span class="sxs-lookup"><span data-stu-id="69c8d-199">Scenarios</span></span>

<span data-ttu-id="69c8d-200">在本演练涵盖多个方案。</span><span class="sxs-lookup"><span data-stu-id="69c8d-200">Several scenarios are covered in this walkthrough.</span></span>

#### <a name="scenario-a-deploy-to-an-azure-vm-from-a-dev-pc-through-docker-engine-connection"></a><span data-ttu-id="69c8d-201">方案 a： 部署到 Azure VM 从开发人员 PC 通过 Docker 引擎连接</span><span class="sxs-lookup"><span data-stu-id="69c8d-201">Scenario A: Deploy to an Azure VM from a dev PC through Docker Engine connection</span></span>

![从开发人员 PC 通过 Docker 引擎连接到 Azure VM 部署](./media/image5-4.png)

> <span data-ttu-id="69c8d-203">**图 5-4。**</span><span class="sxs-lookup"><span data-stu-id="69c8d-203">**Figure 5-4.**</span></span> <span data-ttu-id="69c8d-204">从开发人员 PC 通过 Docker 引擎连接到 Azure VM 部署</span><span class="sxs-lookup"><span data-stu-id="69c8d-204">Deploy to an Azure VM from a dev PC through a Docker Engine connection</span></span>

#### <a name="scenario-b-deploy-to-an-azure-vm-through-a-docker-registry"></a><span data-ttu-id="69c8d-205">方案 b： 部署到 Azure VM 通过 Docker 注册表</span><span class="sxs-lookup"><span data-stu-id="69c8d-205">Scenario B: Deploy to an Azure VM through a Docker Registry</span></span>

![将部署到 Azure VM 通过 Docker 注册表](./media/image5-5.png)

> <span data-ttu-id="69c8d-207">**图 5-5。**</span><span class="sxs-lookup"><span data-stu-id="69c8d-207">**Figure 5-5.**</span></span> <span data-ttu-id="69c8d-208">将部署到 Azure VM 通过 Docker 注册表</span><span class="sxs-lookup"><span data-stu-id="69c8d-208">Deploy to an Azure VM through a Docker Registry</span></span>

#### <a name="scenario-c-deploy-to-an-azure-vm-from-cicd-pipelines-in-visual-studio-team-services"></a><span data-ttu-id="69c8d-209">方案 c: Azure VM 将从部署到 Visual Studio Team Services 中的 CI/CD 管道</span><span class="sxs-lookup"><span data-stu-id="69c8d-209">Scenario C: Deploy to an Azure VM from CI/CD pipelines in Visual Studio Team Services</span></span>

![从 Visual Studio Team Services 中的 CI/CD 管道将部署到 Azure VM](./media/image5-6.png)

> <span data-ttu-id="69c8d-211">**如 5-6**。</span><span class="sxs-lookup"><span data-stu-id="69c8d-211">**Figure 5-6.**</span></span> <span data-ttu-id="69c8d-212">从 Visual Studio Team Services 中的 CI/CD 管道将部署到 Azure VM</span><span class="sxs-lookup"><span data-stu-id="69c8d-212">Deploy to an Azure VM from CI/CD pipelines in Visual Studio Team Services</span></span>

### <a name="azure-vms-for-windows-containers"></a><span data-ttu-id="69c8d-213">Windows 容器的的 azure Vm</span><span class="sxs-lookup"><span data-stu-id="69c8d-213">Azure VMs for Windows Containers</span></span>

<span data-ttu-id="69c8d-214">Azure Vm 的 Windows 容器是只是基于 Windows Server 2016，Windows 10 的 Vm 或更高版本，它们都具有 Docker 引擎设置。</span><span class="sxs-lookup"><span data-stu-id="69c8d-214">Azure VMs for Windows Containers are simply VMs that are based on Windows Server 2016, Windows 10, or later versions, both with Docker Engine set up.</span></span> <span data-ttu-id="69c8d-215">在大多数情况下，你将在 Azure Vm 中使用 Windows Server 2016。</span><span class="sxs-lookup"><span data-stu-id="69c8d-215">In most cases, you will use Windows Server 2016 in the Azure VMs.</span></span>

<span data-ttu-id="69c8d-216">Azure 目前提供名为的 VM**与容器的 Windows Server 2016**。</span><span class="sxs-lookup"><span data-stu-id="69c8d-216">Azure currently provides a VM named **Windows Server 2016 with Containers**.</span></span> <span data-ttu-id="69c8d-217">可以使用此 VM 尝试新的 Windows Server 容器功能，与 Windows Server Core 或 Windows Nano Server。</span><span class="sxs-lookup"><span data-stu-id="69c8d-217">You can use this VM to try the new Windows Server Container feature, with either Windows Server Core or Windows Nano Server.</span></span> <span data-ttu-id="69c8d-218">安装容器操作系统映像以及然后 VM 已准备好与 Docker 一起使用。</span><span class="sxs-lookup"><span data-stu-id="69c8d-218">Container OS images are installed, and then the VM is ready to use with Docker.</span></span>

### <a name="benefits"></a><span data-ttu-id="69c8d-219">优点</span><span class="sxs-lookup"><span data-stu-id="69c8d-219">Benefits</span></span>

<span data-ttu-id="69c8d-220">虽然 Windows 容器可部署到本地 Windows Server 2016 Vm 部署到 Azure 时，你将收到更简单的方法以开始使用准备就绪，可以使用 Windows Server 容器虚拟机。</span><span class="sxs-lookup"><span data-stu-id="69c8d-220">Although Windows Containers can be deployed to on-premises Windows Server 2016 VMs, when you deploy to Azure, you get an easier way to get started, with ready-to-use Windows Server Container VMs.</span></span> <span data-ttu-id="69c8d-221">你还可以获取测试人员和自动的可伸缩性，通过 Azure VM 缩放集可以访问的常见在线位置。</span><span class="sxs-lookup"><span data-stu-id="69c8d-221">You also get a common online location that’s accessible to testers, and automatic scalability through Azure VM scale sets.</span></span>

### <a name="next-steps"></a><span data-ttu-id="69c8d-222">后续步骤</span><span class="sxs-lookup"><span data-stu-id="69c8d-222">Next steps</span></span>

<span data-ttu-id="69c8d-223">在 GitHub wiki 上浏览此更深入的内容：</span><span class="sxs-lookup"><span data-stu-id="69c8d-223">Explore this content more in-depth on the GitHub wiki:</span></span>

<span data-ttu-id="69c8d-224">[https://github.com/dotnet-architecture/eShopModernizing/wiki/03.-How-to-deploy-your-Windows-Containers-based-app-into-Azure-VMs-(Including-CI-CD)](https://github.com/dotnet-architecture/eShopModernizing/wiki/03.-How-to-deploy-your-Windows-Containers-based-app-into-Azure-VMs-(Including-CI-CD))</span><span class="sxs-lookup"><span data-stu-id="69c8d-224">[https://github.com/dotnet-architecture/eShopModernizing/wiki/03.-How-to-deploy-your-Windows-Containers-based-app-into-Azure-VMs-(Including-CI-CD)](https://github.com/dotnet-architecture/eShopModernizing/wiki/03.-How-to-deploy-your-Windows-Containers-based-app-into-Azure-VMs-(Including-CI-CD))</span></span>

## <a name="walkthrough-4-deploy-your-windows-containers-based-apps-to-kubernetes-in-azure-container-service"></a><span data-ttu-id="69c8d-225">演练 4： 将你的 Windows 容器基于应用部署到 Azure 容器服务中的 Kubernetes</span><span class="sxs-lookup"><span data-stu-id="69c8d-225">Walkthrough 4: Deploy your Windows Containers-based apps to Kubernetes in Azure Container Service</span></span>

### <a name="technical-walkthrough-availability"></a><span data-ttu-id="69c8d-226">技术演练可用性</span><span class="sxs-lookup"><span data-stu-id="69c8d-226">Technical walkthrough availability</span></span>

<span data-ttu-id="69c8d-227">完整技术的演练会出现在 eShopModernizing GitHub 存储库 wiki:</span><span class="sxs-lookup"><span data-stu-id="69c8d-227">The full technical walkthrough is available in the eShopModernizing GitHub repo wiki:</span></span>

<span data-ttu-id="69c8d-228">[https://github.com/dotnet-architecture/eShopModernizing/wiki/04.-How-to-deploy-your-Windows-Containers-based-apps-into-Kubernetes-in-Azure-Container-Service-(Including-C-CD)](https://github.com/dotnet-architecture/eShopModernizing/wiki/04.-How-to-deploy-your-Windows-Containers-based-apps-into-Kubernetes-in-Azure-Container-Service-(Including-C-CD))</span><span class="sxs-lookup"><span data-stu-id="69c8d-228">[https://github.com/dotnet-architecture/eShopModernizing/wiki/04.-How-to-deploy-your-Windows-Containers-based-apps-into-Kubernetes-in-Azure-Container-Service-(Including-C-CD)](https://github.com/dotnet-architecture/eShopModernizing/wiki/04.-How-to-deploy-your-Windows-Containers-based-apps-into-Kubernetes-in-Azure-Container-Service-(Including-C-CD))</span></span>

### <a name="overview"></a><span data-ttu-id="69c8d-229">概述</span><span class="sxs-lookup"><span data-stu-id="69c8d-229">Overview</span></span>

<span data-ttu-id="69c8d-230">应用程序依赖于使用 Windows 容器快速将需要使用从 IaaS Vm 消失移动甚至可更进一步的平台。</span><span class="sxs-lookup"><span data-stu-id="69c8d-230">An application that's based on Windows Containers will quickly need to use platforms, moving even further away from IaaS VMs.</span></span> <span data-ttu-id="69c8d-231">这需要能够轻松实现高可伸缩性和更好地自动可伸缩性，并针对中的重大进步自动部署和版本管理。</span><span class="sxs-lookup"><span data-stu-id="69c8d-231">This is needed to easily achieve high scalability and better automated scalability, and for a significant improvement in automated deployments and versioning.</span></span> <span data-ttu-id="69c8d-232">你可以通过使用 orchestrator 实现这些目标[Kubernetes](https://kubernetes.io/)中的可用[Azure 容器服务](https://azure.microsoft.com/services/container-service/)。</span><span class="sxs-lookup"><span data-stu-id="69c8d-232">You can achieve these goals by using the orchestrator [Kubernetes](https://kubernetes.io/), available in [Azure Container Services](https://azure.microsoft.com/services/container-service/).</span></span>

### <a name="goals"></a><span data-ttu-id="69c8d-233">目标</span><span class="sxs-lookup"><span data-stu-id="69c8d-233">Goals</span></span>

<span data-ttu-id="69c8d-234">此演练的目的是了解如何基于 Windows 容器 – 将应用部署到 Kubernetes (也称为*K8s*) 在 Azure 容器服务。</span><span class="sxs-lookup"><span data-stu-id="69c8d-234">The goal of this walkthrough is to learn how to deploy a Windows Container–based application to Kubernetes (also called *K8s*) in Azure Container Service.</span></span> <span data-ttu-id="69c8d-235">将部署到 Kubernetes 从头是一个两步过程：</span><span class="sxs-lookup"><span data-stu-id="69c8d-235">Deploying to Kubernetes from scratch is a two-step process:</span></span>

1.  <span data-ttu-id="69c8d-236">将实现 Kubernetes 群集部署到 Azure 容器服务。</span><span class="sxs-lookup"><span data-stu-id="69c8d-236">Deploy a Kubernetes cluster to Azure Container Service.</span></span>

2.  <span data-ttu-id="69c8d-237">向 Kubernetes 群集部署的应用程序和相关的资源。</span><span class="sxs-lookup"><span data-stu-id="69c8d-237">Deploy the application and related resources to the Kubernetes cluster.</span></span>

### <a name="scenarios"></a><span data-ttu-id="69c8d-238">方案</span><span class="sxs-lookup"><span data-stu-id="69c8d-238">Scenarios</span></span>

#### <a name="scenario-a-deploy-directly-to-a-kubernetes-cluster-from-a-dev-environment"></a><span data-ttu-id="69c8d-239">方案 a： 部署到 Kubernetes 群集直接从开发环境</span><span class="sxs-lookup"><span data-stu-id="69c8d-239">Scenario A: Deploy directly to a Kubernetes cluster from a dev environment</span></span>

![从开发环境直接到 Kubernetes 群集部署](./media/image5-7.png)

> <span data-ttu-id="69c8d-241">**图 5-7。**</span><span class="sxs-lookup"><span data-stu-id="69c8d-241">**Figure 5-7.**</span></span> <span data-ttu-id="69c8d-242">从开发环境直接到 Kubernetes 群集部署</span><span class="sxs-lookup"><span data-stu-id="69c8d-242">Deploy directly to a Kubernetes cluster from a development environment</span></span>

#### <a name="scenario-b-deploy-to-a-kubernetes-cluster-from-cicd-pipelines-in-team-services"></a><span data-ttu-id="69c8d-243">方案 b: Kubernetes 群集将从部署到 CI/CD 管道在 Team Services</span><span class="sxs-lookup"><span data-stu-id="69c8d-243">Scenario B: Deploy to a Kubernetes cluster from CI/CD pipelines in Team Services</span></span>

![从 Team Services 中的 CI/CD 管道到 Kubernetes 群集部署](./media/image5-8.png)

> <span data-ttu-id="69c8d-245">**图 5-8。**</span><span class="sxs-lookup"><span data-stu-id="69c8d-245">**Figure 5-8.**</span></span> <span data-ttu-id="69c8d-246">从 Team Services 中的 CI/CD 管道到 Kubernetes 群集部署</span><span class="sxs-lookup"><span data-stu-id="69c8d-246">Deploy to a Kubernetes cluster from CI/CD pipelines in Team Services</span></span>

### <a name="benefits"></a><span data-ttu-id="69c8d-247">优点</span><span class="sxs-lookup"><span data-stu-id="69c8d-247">Benefits</span></span>

<span data-ttu-id="69c8d-248">有很多好处与部署到在 Kubernetes 中的群集。</span><span class="sxs-lookup"><span data-stu-id="69c8d-248">There are many benefits to deploying to a cluster in Kubernetes.</span></span> <span data-ttu-id="69c8d-249">最大好处是您获得的生产就绪环境在其中你可以向外扩展应用程序根据你想要使用 （内部的可伸缩性的现有节点中），并根据在群集 （节点或 Vm 的数量的容器实例数全局可伸缩性的群集）。</span><span class="sxs-lookup"><span data-stu-id="69c8d-249">The biggest benefit is that you get a production-ready environment in which you can scale-out the application based on the number of container instances you want to use (inner-scalability in the existing nodes), and based on the number of nodes or VMs in the cluster (global scalability of the cluster).</span></span>

<span data-ttu-id="69c8d-250">Azure 容器服务专门针对 Azure 进行优化受欢迎的开源工具和技术。</span><span class="sxs-lookup"><span data-stu-id="69c8d-250">Azure Container Service optimizes popular open-source tools and technologies specifically for Azure.</span></span> <span data-ttu-id="69c8d-251">获取一个打开的解决方案，它提供可移植性，对于你的容器和应用程序配置。</span><span class="sxs-lookup"><span data-stu-id="69c8d-251">You get an open solution that offers portability, both for your containers and for your application configuration.</span></span> <span data-ttu-id="69c8d-252">你选择的大小的主机，数量和 orchestrator 工具-容器服务将处理一切。</span><span class="sxs-lookup"><span data-stu-id="69c8d-252">You select the size, the number of hosts, and the orchestrator tools-Container Service handles everything else.</span></span>

<span data-ttu-id="69c8d-253">与 Kubernetes，开发人员都可以从思考一下物理机和虚拟机进行规划以容器为中心的基础结构，它方便了以下功能，以及其他正在：</span><span class="sxs-lookup"><span data-stu-id="69c8d-253">With Kubernetes, developers can progress from thinking about physical and virtual machines, to planning a container-centric infrastructure that facilitates the following capabilities, among others:</span></span>

-   <span data-ttu-id="69c8d-254">基于多个容器的应用程序</span><span class="sxs-lookup"><span data-stu-id="69c8d-254">Applications based on multiple containers</span></span>

-   <span data-ttu-id="69c8d-255">复制容器实例和水平的自动缩放</span><span class="sxs-lookup"><span data-stu-id="69c8d-255">Replicating container instances and horizontal autoscaling</span></span>

-   <span data-ttu-id="69c8d-256">命名和发现 (例如，内部 DNS)</span><span class="sxs-lookup"><span data-stu-id="69c8d-256">Naming and discovering (for example, internal DNS)</span></span>

-   <span data-ttu-id="69c8d-257">平衡负载</span><span class="sxs-lookup"><span data-stu-id="69c8d-257">Balancing loads</span></span>

-   <span data-ttu-id="69c8d-258">滚动更新</span><span class="sxs-lookup"><span data-stu-id="69c8d-258">Rolling updates</span></span>

-   <span data-ttu-id="69c8d-259">分发机密</span><span class="sxs-lookup"><span data-stu-id="69c8d-259">Distributing secrets</span></span>

-   <span data-ttu-id="69c8d-260">应用程序运行状况检查</span><span class="sxs-lookup"><span data-stu-id="69c8d-260">Application health checks</span></span>

## <a name="next-steps"></a><span data-ttu-id="69c8d-261">后续步骤</span><span class="sxs-lookup"><span data-stu-id="69c8d-261">Next steps</span></span>

<span data-ttu-id="69c8d-262">浏览 GitHub wiki 上的此内容更深入： [https://github.com/dotnet-architecture/eShopModernizing/wiki/04.-How-to-deploy-your-Windows-Containers-based-apps-into-Kubernetes-in-Azure-Container-Service-(Including-C-CD)](https://github.com/dotnet-architecture/eShopModernizing/wiki/04.-How-to-deploy-your-Windows-Containers-based-apps-into-Kubernetes-in-Azure-Container-Service-(Including-C-CD))</span><span class="sxs-lookup"><span data-stu-id="69c8d-262">Explore this content more in-depth on the GitHub wiki: [https://github.com/dotnet-architecture/eShopModernizing/wiki/04.-How-to-deploy-your-Windows-Containers-based-apps-into-Kubernetes-in-Azure-Container-Service-(Including-C-CD)](https://github.com/dotnet-architecture/eShopModernizing/wiki/04.-How-to-deploy-your-Windows-Containers-based-apps-into-Kubernetes-in-Azure-Container-Service-(Including-C-CD))</span></span>

## <a name="walkthrough-5-deploy-your-windows-containers-based-apps-to-azure-service-fabric"></a><span data-ttu-id="69c8d-263">演练 5： 将你的 Windows 容器基于应用部署到 Azure Service Fabric</span><span class="sxs-lookup"><span data-stu-id="69c8d-263">Walkthrough 5: Deploy your Windows Containers-based apps to Azure Service Fabric</span></span>

### <a name="technical-walkthrough-availability"></a><span data-ttu-id="69c8d-264">技术演练可用性</span><span class="sxs-lookup"><span data-stu-id="69c8d-264">Technical walkthrough availability</span></span>

<span data-ttu-id="69c8d-265">完整技术的演练会出现在 eShopModernizing GitHub 存储库 wiki:</span><span class="sxs-lookup"><span data-stu-id="69c8d-265">The full technical walkthrough is available in the eShopModernizing GitHub repo wiki:</span></span>

<span data-ttu-id="69c8d-266">[https://github.com/dotnet-architecture/eShopModernizing/wiki/05.-How-to-deploy-your-Windows-Containers-based-apps-into-Azure-Service-Fabric-(Including-CI-CD)](https://github.com/dotnet-architecture/eShopModernizing/wiki/05.-How-to-deploy-your-Windows-Containers-based-apps-into-Azure-Service-Fabric-(Including-CI-CD))</span><span class="sxs-lookup"><span data-stu-id="69c8d-266">[https://github.com/dotnet-architecture/eShopModernizing/wiki/05.-How-to-deploy-your-Windows-Containers-based-apps-into-Azure-Service-Fabric-(Including-CI-CD)](https://github.com/dotnet-architecture/eShopModernizing/wiki/05.-How-to-deploy-your-Windows-Containers-based-apps-into-Azure-Service-Fabric-(Including-CI-CD))</span></span>

### <a name="overview"></a><span data-ttu-id="69c8d-267">概述</span><span class="sxs-lookup"><span data-stu-id="69c8d-267">Overview</span></span>

<span data-ttu-id="69c8d-268">应用程序依赖于使用 Windows 容器快速将需要使用从 IaaS Vm 消失移动甚至可更进一步的平台。</span><span class="sxs-lookup"><span data-stu-id="69c8d-268">An application that's based on Windows Containers will quickly need to use platforms, moving even further away from IaaS VMs.</span></span> <span data-ttu-id="69c8d-269">这需要能够轻松实现高可伸缩性和更好地自动可伸缩性，并针对中的重大进步自动部署和版本管理。</span><span class="sxs-lookup"><span data-stu-id="69c8d-269">This is needed to easily achieve high scalability and better automated scalability, and for a significant improvement in automated deployments and versioning.</span></span> <span data-ttu-id="69c8d-270">使用 orchestrator Azure Service Fabric 中，这是可用在 Azure 云中，但也可用于在本地，或甚至在不同的公有云，可以实现这些目标。</span><span class="sxs-lookup"><span data-stu-id="69c8d-270">You can achieve these goals by using the orchestrator Azure Service Fabric, which is available in the Azure cloud, but also available to use on-premises, or even in a different public cloud.</span></span>

### <a name="goals"></a><span data-ttu-id="69c8d-271">目标</span><span class="sxs-lookup"><span data-stu-id="69c8d-271">Goals</span></span>

<span data-ttu-id="69c8d-272">此演练的目的是了解如何基于 Windows 容器 – 将应用部署到在 Azure 中的 Service Fabric 群集。</span><span class="sxs-lookup"><span data-stu-id="69c8d-272">The goal of this walkthrough is to learn how to deploy a Windows Container–based application to a Service Fabric cluster in Azure.</span></span> <span data-ttu-id="69c8d-273">从零开始将部署到 Service Fabric 是一个两步过程：</span><span class="sxs-lookup"><span data-stu-id="69c8d-273">Deploying to Service Fabric from scratch is a two-step process:</span></span>

1.  <span data-ttu-id="69c8d-274">将 Service Fabric 群集部署到 Azure （或其他环境）。</span><span class="sxs-lookup"><span data-stu-id="69c8d-274">Deploy a Service Fabric cluster to Azure (or to a different environment).</span></span>

2.  <span data-ttu-id="69c8d-275">向 Service Fabric 群集中部署的应用程序和相关的资源。</span><span class="sxs-lookup"><span data-stu-id="69c8d-275">Deploy the application and related resources to the Service Fabric cluster.</span></span>

### <a name="scenarios"></a><span data-ttu-id="69c8d-276">方案</span><span class="sxs-lookup"><span data-stu-id="69c8d-276">Scenarios</span></span>

#### <a name="scenario-a-deploy-directly-to-a-service-fabric-cluster-from-a-dev-environment"></a><span data-ttu-id="69c8d-277">方案 a： 部署到 Service Fabric 群集直接从开发环境</span><span class="sxs-lookup"><span data-stu-id="69c8d-277">Scenario A: Deploy directly to a Service Fabric cluster from a dev environment</span></span>

![从开发环境将部署直接到 Service Fabric 群集](./media/image5-9.png)

> <span data-ttu-id="69c8d-279">**图 5-9。**</span><span class="sxs-lookup"><span data-stu-id="69c8d-279">**Figure 5-9.**</span></span> <span data-ttu-id="69c8d-280">从开发环境将部署直接到 Service Fabric 群集</span><span class="sxs-lookup"><span data-stu-id="69c8d-280">Deploy directly to a Service Fabric cluster from a development environment</span></span>

### <a name="scenario-b-deploy-to-a-service-fabric-cluster-from-cicd-pipelines-in-team-services"></a><span data-ttu-id="69c8d-281">方案 b: Service Fabric 群集将从部署到 CI/CD 管道在 Team Services</span><span class="sxs-lookup"><span data-stu-id="69c8d-281">Scenario B: Deploy to a Service Fabric cluster from CI/CD pipelines in Team Services</span></span>

![从 Visual Studio Team Services 中的 CI/CD 管道将部署到 Service Fabric 群集](./media/image5-10.png)

> <span data-ttu-id="69c8d-283">**图 5-10。**</span><span class="sxs-lookup"><span data-stu-id="69c8d-283">**Figure 5-10.**</span></span> <span data-ttu-id="69c8d-284">从 Visual Studio Team Services 中的 CI/CD 管道将部署到 Service Fabric 群集</span><span class="sxs-lookup"><span data-stu-id="69c8d-284">Deploy to a Service Fabric cluster from CI/CD pipelines in Visual Studio Team Services</span></span>

## <a name="benefits"></a><span data-ttu-id="69c8d-285">优点</span><span class="sxs-lookup"><span data-stu-id="69c8d-285">Benefits</span></span>

<span data-ttu-id="69c8d-286">向 Service Fabric 中的群集部署的优点是类似于使用 Kubernetes 的好处。</span><span class="sxs-lookup"><span data-stu-id="69c8d-286">The benefits of deploying to a cluster in Service Fabric are similar to the benefits of using Kubernetes.</span></span> <span data-ttu-id="69c8d-287">一个区别，不过，是 Service Fabric 是相比 Kubernetes，已在预览为 Windows 容器之前尽早在 2017年的 Windows 应用程序的非常成熟的生产环境。</span><span class="sxs-lookup"><span data-stu-id="69c8d-287">One difference, though, is that Service Fabric is a very mature production environment for Windows applications compared to Kubernetes, which was in preview for Windows Containers until early fall of 2017.</span></span> <span data-ttu-id="69c8d-288">（Kubernetes 是适用于 Linux 的更加成熟完善一些环境）。</span><span class="sxs-lookup"><span data-stu-id="69c8d-288">(Kubernetes is a more mature environment for Linux).</span></span> 

<span data-ttu-id="69c8d-289">使用 Azure Service Fabric 的主要优势是获取生产就绪环境在其中你可以向外扩展应用程序根据你想要使用 （内部的可伸缩性的现有节点中），并根据的数量的容器实例数节点或群集 （群集的全局可伸缩性） 中的 Vm。</span><span class="sxs-lookup"><span data-stu-id="69c8d-289">The main benefit of using Azure Service Fabric is that you get a production-ready environment in which you can scale-out the application based on the number of container instances you want to use (inner-scalability in the existing nodes), and based on the number of nodes or VMs in the cluster (global scalability of the cluster).</span></span>

<span data-ttu-id="69c8d-290">Azure Service Fabric 提供了可移植性对于你的容器和应用程序配置。</span><span class="sxs-lookup"><span data-stu-id="69c8d-290">Azure Service Fabric offers portability both for your containers and for your application configuration.</span></span> <span data-ttu-id="69c8d-291">你可以 Service Fabric 群集在 Azure 中，或将其安装在本地在自己的数据中心。</span><span class="sxs-lookup"><span data-stu-id="69c8d-291">You can have a Service Fabric cluster in Azure, or install it on-premises in your own datacenter.</span></span> <span data-ttu-id="69c8d-292">你甚至可以安装的 Service Fabric 群集在另一个云，如[Amazon AWS](https://blogs.msdn.microsoft.com/azureservicefabric/2017/05/18/tutorial-how-to-create-a-service-fabric-standalone-cluster-with-aws-ec2-instances/)。</span><span class="sxs-lookup"><span data-stu-id="69c8d-292">You can even install a Service Fabric cluster in a different cloud, like [Amazon AWS](https://blogs.msdn.microsoft.com/azureservicefabric/2017/05/18/tutorial-how-to-create-a-service-fabric-standalone-cluster-with-aws-ec2-instances/).</span></span>

<span data-ttu-id="69c8d-293">使用 Service Fabric，开发人员可以进行规划以容器为中心的基础结构，它方便了以下功能，以及其他进度从思考物理机和虚拟机：</span><span class="sxs-lookup"><span data-stu-id="69c8d-293">With Service Fabric, developers can progress from thinking about physical and virtual machines to planning a container-centric infrastructure that facilitates the following capabilities, among others:</span></span>

-   <span data-ttu-id="69c8d-294">根据应用程序的多个容器。</span><span class="sxs-lookup"><span data-stu-id="69c8d-294">Applications based on multiple containers.</span></span>

-   <span data-ttu-id="69c8d-295">复制容器实例和水平的自动缩放。</span><span class="sxs-lookup"><span data-stu-id="69c8d-295">Replicating container instances and horizontal autoscaling.</span></span>

-   <span data-ttu-id="69c8d-296">命名和发现 (例如，内部 DNS)。</span><span class="sxs-lookup"><span data-stu-id="69c8d-296">Naming and discovering (for example, internal DNS).</span></span>

-   <span data-ttu-id="69c8d-297">平衡负载。</span><span class="sxs-lookup"><span data-stu-id="69c8d-297">Balancing loads.</span></span>

-   <span data-ttu-id="69c8d-298">滚动更新。</span><span class="sxs-lookup"><span data-stu-id="69c8d-298">Rolling updates.</span></span>

-   <span data-ttu-id="69c8d-299">分发机密。</span><span class="sxs-lookup"><span data-stu-id="69c8d-299">Distributing secrets.</span></span>

-   <span data-ttu-id="69c8d-300">应用程序运行状况检查。</span><span class="sxs-lookup"><span data-stu-id="69c8d-300">Application health checks.</span></span>

<span data-ttu-id="69c8d-301">以下功能是独占的 （与其他 orchestrators 比较） 的 Service Fabric 在：</span><span class="sxs-lookup"><span data-stu-id="69c8d-301">The following capabilities are exclusive in Service Fabric (compared to other orchestrators):</span></span>

-   <span data-ttu-id="69c8d-302">有状态服务功能，通过可靠的服务应用程序模型。</span><span class="sxs-lookup"><span data-stu-id="69c8d-302">Stateful services capability, through the Reliable Services application model.</span></span>

-   <span data-ttu-id="69c8d-303">Actor 模式，通过 Reliable Actors 应用程序模型。</span><span class="sxs-lookup"><span data-stu-id="69c8d-303">Actors pattern, through the Reliable Actors application model.</span></span>

-   <span data-ttu-id="69c8d-304">部署精简进程，除了 Windows 或 Linux 容器。</span><span class="sxs-lookup"><span data-stu-id="69c8d-304">Deploy bare-bone processes, in addition to Windows or Linux containers.</span></span>

-   <span data-ttu-id="69c8d-305">高级滚动更新和运行状况检查。</span><span class="sxs-lookup"><span data-stu-id="69c8d-305">Advanced rolling updates and health checks.</span></span>

### <a name="next-steps"></a><span data-ttu-id="69c8d-306">后续步骤</span><span class="sxs-lookup"><span data-stu-id="69c8d-306">Next steps</span></span>

<span data-ttu-id="69c8d-307">在 GitHub wiki 上浏览此更深入的内容：</span><span class="sxs-lookup"><span data-stu-id="69c8d-307">Explore this content more in-depth on the GitHub wiki:</span></span>

<span data-ttu-id="69c8d-308">[https://github.com/dotnet-architecture/eShopModernizing/wiki/05.-How-to-deploy-your-Windows-Containers-based-apps-into-Azure-Service-Fabric-(Including-CI-CD)](https://github.com/dotnet-architecture/eShopModernizing/wiki/05.-How-to-deploy-your-Windows-Containers-based-apps-into-Azure-Service-Fabric-(Including-CI-CD))</span><span class="sxs-lookup"><span data-stu-id="69c8d-308">[https://github.com/dotnet-architecture/eShopModernizing/wiki/05.-How-to-deploy-your-Windows-Containers-based-apps-into-Azure-Service-Fabric-(Including-CI-CD)](https://github.com/dotnet-architecture/eShopModernizing/wiki/05.-How-to-deploy-your-Windows-Containers-based-apps-into-Azure-Service-Fabric-(Including-CI-CD))</span></span>

>[!div class="step-by-step"]
<span data-ttu-id="69c8d-309">[上一页](lift-and-shift-existing-apps-devops/migrate-to-hybrid-cloud-scenarios.md)
[下一页](conclusions.md)</span><span class="sxs-lookup"><span data-stu-id="69c8d-309">[Previous](lift-and-shift-existing-apps-devops/migrate-to-hybrid-cloud-scenarios.md)
[Next](conclusions.md)</span></span>
