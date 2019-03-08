---
title: 演练和技术可帮助入门的概述
description: 更新现有.NET 应用程序使用 Azure 云和 Windows 容器 |演练和技术可帮助入门的概述
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 04/28/2018
ms.openlocfilehash: 15ea074693a75aa04b4f3a03e6e5e3d7f748cea1
ms.sourcegitcommit: 58fc0e6564a37fa1b9b1b140a637e864c4cf696e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/08/2019
ms.locfileid: "57674934"
---
# <a name="walkthroughs-and-technical-get-started-overview"></a><span data-ttu-id="507da-103">演练和技术可帮助入门的概述</span><span class="sxs-lookup"><span data-stu-id="507da-103">Walkthroughs and technical get started overview</span></span>

<span data-ttu-id="507da-104">若要限制此电子书的大小，其他技术文档和完整的演练提供了在 GitHub 存储库中。</span><span class="sxs-lookup"><span data-stu-id="507da-104">To limit the size of this e-book, additional technical documentation and the full walkthroughs were made available in a GitHub repository.</span></span> <span data-ttu-id="507da-105">联机的此章中所述的演练一系列涵盖基于 Windows 容器和 Azure 上部署的多个环境的分步的设置。</span><span class="sxs-lookup"><span data-stu-id="507da-105">The online series of walkthroughs that is described in this chapter covers the step-by-step setup of the multiple environments that are based on Windows Containers, and deployment to Azure.</span></span>

<span data-ttu-id="507da-106">以下部分介绍每个演练有关其目标和高级愿景是什么，并提供了所涉及的任务的图表。</span><span class="sxs-lookup"><span data-stu-id="507da-106">The following sections explain what each walkthrough is about, its objectives and high-level vision, and provides a diagram of the tasks that are involved.</span></span> <span data-ttu-id="507da-107">可以获取自己的演练中*eShopModernizing*在应用 GitHub 存储库 wiki [ https://github.com/dotnet-architecture/eShopModernizing/wiki ](https://github.com/dotnet-architecture/eShopModernizing/wiki)。</span><span class="sxs-lookup"><span data-stu-id="507da-107">You can get the walkthroughs themselves in the *eShopModernizing* apps GitHub repo wiki at [https://github.com/dotnet-architecture/eShopModernizing/wiki](https://github.com/dotnet-architecture/eShopModernizing/wiki).</span></span>

## <a name="technical-walkthrough-list"></a><span data-ttu-id="507da-108">技术演练列表</span><span class="sxs-lookup"><span data-stu-id="507da-108">Technical walkthrough list</span></span>

<span data-ttu-id="507da-109">下面的入门演练提供一致且全面的示例应用，你可以迁移使用容器，并在 Azure 中使用多个部署选项然后移动的技术指南。</span><span class="sxs-lookup"><span data-stu-id="507da-109">The following get-started walkthroughs provide consistent and comprehensive technical guidance for sample apps that you can lift and shift by using containers, and then move by using multiple deployment choices in Azure.</span></span>

<span data-ttu-id="507da-110">每个以下演练使用的新示例 eShopLegacy 和 eShopModernizing 应用，可在 GitHub 上[ https://github.com/dotnet-architecture/eShopModernizing ](https://github.com/dotnet-architecture/eShopModernizing)。</span><span class="sxs-lookup"><span data-stu-id="507da-110">Each of the following walkthroughs uses the new sample eShopLegacy and eShopModernizing apps, which are available on GitHub at [https://github.com/dotnet-architecture/eShopModernizing](https://github.com/dotnet-architecture/eShopModernizing).</span></span>

- <span data-ttu-id="507da-111">**EShop 旧版应用 （基线应用实现现代化） 的教程**</span><span class="sxs-lookup"><span data-stu-id="507da-111">**Tour of eShop legacy apps (baseline apps to modernize)**</span></span>

- <span data-ttu-id="507da-112">**Windows 容器与容器化现有 ASP.NET web 应用 （WebForms 和 MVC）**</span><span class="sxs-lookup"><span data-stu-id="507da-112">**Containerize your existing ASP.NET web apps (WebForms & MVC) with Windows Containers**</span></span>

- <span data-ttu-id="507da-113">**容器化现有 WCF 服务 （N 层应用程序） 与 Windows 容器**</span><span class="sxs-lookup"><span data-stu-id="507da-113">**Containerize your existing WCF services (N-Tier apps) with Windows Containers**</span></span>

- <span data-ttu-id="507da-114">**将 Windows 基于容器的应用部署到 Azure Vm**</span><span class="sxs-lookup"><span data-stu-id="507da-114">**Deploy your Windows Containers-based app to Azure VMs**</span></span>

- <span data-ttu-id="507da-115">**将 Windows 基于容器的应用部署到 Azure 容器服务中 Kubernetes**</span><span class="sxs-lookup"><span data-stu-id="507da-115">**Deploy your Windows Containers-based apps to Kubernetes in Azure Container Service**</span></span>

- <span data-ttu-id="507da-116">**部署到 Azure Service Fabric Windows 基于容器的应用程序**</span><span class="sxs-lookup"><span data-stu-id="507da-116">**Deploy your Windows Containers-based apps to Azure Service Fabric**</span></span>

## <a name="walkthrough-1-tour-of-eshop-legacy-apps"></a><span data-ttu-id="507da-117">演练 1:EShop 旧版应用的教程</span><span class="sxs-lookup"><span data-stu-id="507da-117">Walkthrough 1: Tour of eShop legacy apps</span></span>

### <a name="technical-walkthrough-availability"></a><span data-ttu-id="507da-118">技术演练可用性</span><span class="sxs-lookup"><span data-stu-id="507da-118">Technical walkthrough availability</span></span>

<span data-ttu-id="507da-119">全面的技术演练现已推出 eShopModernizing GitHub 存储库 wiki:</span><span class="sxs-lookup"><span data-stu-id="507da-119">The full technical walkthrough is available in the eShopModernizing GitHub repo wiki:</span></span>

[<span data-ttu-id="507da-120">eShopModernizing wiki 演练</span><span class="sxs-lookup"><span data-stu-id="507da-120">eShopModernizing wiki walkthroughs</span></span>](https://github.com/dotnet-architecture/eShopModernizing/wiki)

### <a name="overview"></a><span data-ttu-id="507da-121">概述</span><span class="sxs-lookup"><span data-stu-id="507da-121">Overview</span></span>

<span data-ttu-id="507da-122">在本演练中，可以浏览对旧版应用程序的三个示例的初始实现。</span><span class="sxs-lookup"><span data-stu-id="507da-122">In this walkthrough, you can explore the initial implementation of three sample legacy applications.</span></span> <span data-ttu-id="507da-123">前两个示例 web 应用具有单一式体系结构，并使用传统的 ASP.NET 创建的。</span><span class="sxs-lookup"><span data-stu-id="507da-123">The first two sample web apps have a monolithic architecture, and were created by using classic ASP.NET.</span></span> <span data-ttu-id="507da-124">一个应用程序基于 ASP.NET 4.x MVC;第二个应用程序基于 ASP.NET 4.x Web 窗体。</span><span class="sxs-lookup"><span data-stu-id="507da-124">One application is based on ASP.NET 4.x MVC; the second application is based on ASP.NET 4.x Web Forms.</span></span>
<span data-ttu-id="507da-125">第三个应用程序是由客户端 WinForms 应用程序和服务器端的 3 层应用程序[Windows Communication Foundation (WCF)](../../framework/wcf/whats-wcf.md)服务。</span><span class="sxs-lookup"><span data-stu-id="507da-125">The third app is a 3-Tier app composed by a client WinForms app and a server-side [Windows Communication Foundation (WCF)](../../framework/wcf/whats-wcf.md) service.</span></span>

<span data-ttu-id="507da-126">所有这些应用程序目前[eShopModernizing GitHub 存储库](https://github.com/dotnet-architecture/eShopModernizing)。</span><span class="sxs-lookup"><span data-stu-id="507da-126">All these applications are available at the [eShopModernizing GitHub repo](https://github.com/dotnet-architecture/eShopModernizing).</span></span>

### <a name="goals"></a><span data-ttu-id="507da-127">目标</span><span class="sxs-lookup"><span data-stu-id="507da-127">Goals</span></span>

<span data-ttu-id="507da-128">本演练中的主要目标是只需熟悉这些应用程序，以及其代码和配置。</span><span class="sxs-lookup"><span data-stu-id="507da-128">The main goal of this walkthrough is simply to get familiar with these apps, and with their code and configuration.</span></span> <span data-ttu-id="507da-129">可以配置应用程序，使它们生成和使用模拟数据，而无需使用 SQL 数据库中，出于测试目的。</span><span class="sxs-lookup"><span data-stu-id="507da-129">You can configure the apps so that they generate and use mock data, without using the SQL database, for testing purposes.</span></span> <span data-ttu-id="507da-130">此可选配置基于依赖关系注入，方法中。</span><span class="sxs-lookup"><span data-stu-id="507da-130">This optional config is based on dependency injection, in a decoupled way.</span></span>

### <a name="scenario-1-aspnet-web-apps"></a><span data-ttu-id="507da-131">方案 1:ASP.NET Web 应用程序</span><span class="sxs-lookup"><span data-stu-id="507da-131">Scenario 1: ASP.NET Web apps</span></span>

<span data-ttu-id="507da-132">下图显示了原始的旧版 ASP.NET web 应用程序的简单方案。</span><span class="sxs-lookup"><span data-stu-id="507da-132">The figure below shows the simple scenario of the original legacy ASP.NET web applications.</span></span>

![简单的体系结构方案中的原始的旧版 ASP.NET web 应用程序](./media/image5-1.png)

<span data-ttu-id="507da-134">从业务域的角度来看，这两个应用管理功能提供相同的目录。</span><span class="sxs-lookup"><span data-stu-id="507da-134">From a business domain perspective, both apps offer the same catalog management features.</span></span> <span data-ttu-id="507da-135">EShop 企业团队的成员将使用该应用可以查看和编辑产品目录。</span><span class="sxs-lookup"><span data-stu-id="507da-135">Members of the eShop enterprise team would use the app to view and edit the product catalog.</span></span>

<span data-ttu-id="507da-136">下图显示了初始应用程序的屏幕截图。</span><span class="sxs-lookup"><span data-stu-id="507da-136">The next figure shows the initial app screenshots.</span></span>

![ASP.NET MVC 和 ASP.NET Web 窗体应用程序 （现有/旧版技术）](./media/image5-2.png)

<span data-ttu-id="507da-138">依赖关系在 ASP.NET 4.x 或更早版本 （不管是 MVC 或 Web 窗体） 意味着除非通过使用 ASP.NET Core MVC 完全重写代码，这些应用程序不会运行.NET Core 上。</span><span class="sxs-lookup"><span data-stu-id="507da-138">Dependencies in ASP.NET 4.x or earlier versions (either for MVC or for Web Forms) means that these applications won’t run on .NET Core unless the code is fully rewritten by using ASP.NET Core MVC.</span></span>

### <a name="scenario-2-wcf-service-and-winforms-client-app-3-tier-app"></a><span data-ttu-id="507da-139">方案 2:WCF 服务和 WinForms 客户端应用程序 （第 3 层应用程序）</span><span class="sxs-lookup"><span data-stu-id="507da-139">Scenario 2: WCF service and WinForms client app (3-Tier app)</span></span>

<span data-ttu-id="507da-140">下图显示了原始的第 3 层旧应用程序的简单方案。</span><span class="sxs-lookup"><span data-stu-id="507da-140">The figure below shows the simple scenario of the original 3-Tier legacy application.</span></span>

![简单的体系结构方案中的原始的旧版第 3 层应用程序与 WCF 服务和 WinForms 客户端应用程序](./media/image5-1.5.png)

### <a name="benefits"></a><span data-ttu-id="507da-142">优点</span><span class="sxs-lookup"><span data-stu-id="507da-142">Benefits</span></span>

<span data-ttu-id="507da-143">本演练的好处很简单：只需熟悉的代码和初始应用程序。</span><span class="sxs-lookup"><span data-stu-id="507da-143">The benefits of this walkthrough are simple: Just get familiar with the code and initial apps.</span></span>

### <a name="next-steps"></a><span data-ttu-id="507da-144">后续步骤</span><span class="sxs-lookup"><span data-stu-id="507da-144">Next steps</span></span>

<span data-ttu-id="507da-145">浏览 GitHub wiki 上的更深入此内容：</span><span class="sxs-lookup"><span data-stu-id="507da-145">Explore this content more in-depth on the GitHub wiki:</span></span>

- [<span data-ttu-id="507da-146">教程基线 ASP.NET MVC 和 Web 窗体"传统"应用程序</span><span class="sxs-lookup"><span data-stu-id="507da-146">Tour on the baseline ASP.NET MVC and Web Forms “legacy” apps</span></span>](https://github.com/dotnet-architecture/eShopModernizing/wiki/01.-Tour-on-the-ASP.NET-MVC-and-WebForms-apps-implementation-code)
-   [<span data-ttu-id="507da-147">基线 WCF 服务和 WinForms （3 层）"传统"应用程序的教程</span><span class="sxs-lookup"><span data-stu-id="507da-147">Tour on the baseline WCF service and WinForms (3-Tier) “legacy” app</span></span>](https://github.com/dotnet-architecture/eShopModernizing/wiki/21.-Tour-on-the-WCF-service-and-WinForms-apps)

## <a name="walkthrough-2-containerize-your-existing-net-applications-with-windows-containers"></a><span data-ttu-id="507da-148">演练 2:容器化现有.NET 应用程序与 Windows 容器</span><span class="sxs-lookup"><span data-stu-id="507da-148">Walkthrough 2: Containerize your existing .NET applications with Windows Containers</span></span>

### <a name="overview"></a><span data-ttu-id="507da-149">概述</span><span class="sxs-lookup"><span data-stu-id="507da-149">Overview</span></span>

<span data-ttu-id="507da-150">使用 Windows 容器可提高现有.NET 应用程序，如基于 MVC、 Web 窗体或 WCF，向生产、 开发和测试环境的部署。</span><span class="sxs-lookup"><span data-stu-id="507da-150">Use Windows Containers to improve deployment of existing .NET applications, like those based on MVC, Web Forms, or WCF, to production, development, and test environments.</span></span>

### <a name="goals"></a><span data-ttu-id="507da-151">目标</span><span class="sxs-lookup"><span data-stu-id="507da-151">Goals</span></span>

<span data-ttu-id="507da-152">本演练的目的是说明用于容器化现有.NET Framework 应用程序的多个选项。</span><span class="sxs-lookup"><span data-stu-id="507da-152">The goal of this walkthrough is to show you several options for containerizing an existing .NET Framework application.</span></span> <span data-ttu-id="507da-153">你可以：</span><span class="sxs-lookup"><span data-stu-id="507da-153">You can:</span></span>

- <span data-ttu-id="507da-154">通过使用容器化应用程序[Visual Studio 2017 Tools for Docker](/aspnet/core/host-and-deploy/docker/visual-studio-tools-for-docker) （Visual Studio 2017 或更高版本）。</span><span class="sxs-lookup"><span data-stu-id="507da-154">Containerize your application by using [Visual Studio 2017 Tools for Docker](/aspnet/core/host-and-deploy/docker/visual-studio-tools-for-docker) (Visual Studio 2017 or later versions).</span></span>

- <span data-ttu-id="507da-155">通过手动添加容器化应用程序[Dockerfile](https://docs.docker.com/engine/reference/builder/)，然后使用[Docker CLI](https://docs.docker.com/engine/reference/commandline/cli/)。</span><span class="sxs-lookup"><span data-stu-id="507da-155">Containerize your application by manually adding a [Dockerfile](https://docs.docker.com/engine/reference/builder/), and then using the [Docker CLI](https://docs.docker.com/engine/reference/commandline/cli/).</span></span>

- <span data-ttu-id="507da-156">通过使用容器化应用程序[Img2Docker](https://github.com/docker/communitytools-image2docker-win)工具 （Docker 的开放源代码工具）。</span><span class="sxs-lookup"><span data-stu-id="507da-156">Containerize your application by using the [Img2Docker](https://github.com/docker/communitytools-image2docker-win) tool (an open-source tool from Docker).</span></span>

<span data-ttu-id="507da-157">本演练重点介绍 Visual Studio 2017 Tools for Docker 方法，但其他两种方法是从使用 Dockerfile 非常相似。</span><span class="sxs-lookup"><span data-stu-id="507da-157">This walkthrough focuses on the Visual Studio 2017 Tools for Docker approach, but the other two approaches are fairly similar in regard to using Dockerfiles.</span></span>

### <a name="scenario-1-containerized-aspnet-web-apps"></a><span data-ttu-id="507da-158">方案 1:容器化的 ASP.NET web 应用</span><span class="sxs-lookup"><span data-stu-id="507da-158">Scenario 1: Containerized ASP.NET web apps</span></span>

<span data-ttu-id="507da-159">下图显示了容器化的 eShop 旧版 web 应用应用程序的方案。</span><span class="sxs-lookup"><span data-stu-id="507da-159">Figure below shows the scenario for containerized eShop legacy web apps applications.</span></span>

![简化的体系结构关系图的适用于容器化 ASP.NET 应用程序在开发环境](./media/image5-3.png)

### <a name="scenario-2-containerized-wcf-service"></a><span data-ttu-id="507da-161">方案 2:容器化的 WCF 服务</span><span class="sxs-lookup"><span data-stu-id="507da-161">Scenario 2: Containerized WCF service</span></span>

<span data-ttu-id="507da-162">下图显示了包含容器化的 WCF 服务的第 3 层应用程序的方案。</span><span class="sxs-lookup"><span data-stu-id="507da-162">Figure below shows the scenario for a 3-Tier app with a containerized WCF service.</span></span>

![简化的开发环境中的容器化 WCF 服务的体系结构关系图](./media/image5-3.5.png)

### <a name="benefits"></a><span data-ttu-id="507da-164">优点</span><span class="sxs-lookup"><span data-stu-id="507da-164">Benefits</span></span>

<span data-ttu-id="507da-165">有在容器中运行整体式应用程序的优点。</span><span class="sxs-lookup"><span data-stu-id="507da-165">There are advantages to running your monolithic application in a container.</span></span> <span data-ttu-id="507da-166">首先，创建用于应用程序的映像。</span><span class="sxs-lookup"><span data-stu-id="507da-166">First, you create an image for the application.</span></span> <span data-ttu-id="507da-167">从该点开始，每个部署在同一环境中运行。</span><span class="sxs-lookup"><span data-stu-id="507da-167">From that point on, every deployment runs in the same environment.</span></span> <span data-ttu-id="507da-168">每个容器使用相同的 OS 版本，具有相同版本的安装的依赖项、 使用相同的.NET framework 版本，并使用相同的过程生成。</span><span class="sxs-lookup"><span data-stu-id="507da-168">Every container uses the same OS version, has the same version of dependencies installed, uses the same .NET framework version, and is built by using the same process.</span></span> <span data-ttu-id="507da-169">基本上，使用的 Docker 映像控制你的应用程序的依赖项。</span><span class="sxs-lookup"><span data-stu-id="507da-169">Basically, you control the dependencies of your application by using a Docker image.</span></span> <span data-ttu-id="507da-170">部署容器时，依赖项与应用程序同步。</span><span class="sxs-lookup"><span data-stu-id="507da-170">The dependencies travel with the application when you deploy the containers.</span></span>

<span data-ttu-id="507da-171">另一个好处是开发人员可以在由 Windows 容器提供一致的环境中运行应用程序。</span><span class="sxs-lookup"><span data-stu-id="507da-171">An additional benefit is that developers can run the application in the consistent environment that's provided by Windows Containers.</span></span> <span data-ttu-id="507da-172">可以立即发现仅某些版本出现的问题，而不是在过渡或生产环境中呈现。</span><span class="sxs-lookup"><span data-stu-id="507da-172">Issues that appear only with certain versions can be spotted immediately, instead of surfacing in a staging or production environment.</span></span> <span data-ttu-id="507da-173">在开发环境中的开发团队成员使用的差异不那么重要应用程序在容器中运行时。</span><span class="sxs-lookup"><span data-stu-id="507da-173">Differences in development environments used by members of the development team matter less when applications run in containers.</span></span>

<span data-ttu-id="507da-174">容器化应用程序还具有 flatter 横向扩展曲线。</span><span class="sxs-lookup"><span data-stu-id="507da-174">Containerized applications also have a flatter scale-out curve.</span></span> <span data-ttu-id="507da-175">容器化应用程序，你有多个应用程序和服务实例 （基于容器） 中的 VM 或物理机到每台计算机的常规应用程序部署进行比较。</span><span class="sxs-lookup"><span data-stu-id="507da-175">Containerized apps enable you to have more application and service instances (based on containers) in a VM or physical machine compared to regular application deployments per machine.</span></span> <span data-ttu-id="507da-176">这会转换为更高的密度和更少所需的资源，尤其是当使用 Kubernetes 或 Service Fabric 等业务流程协调程序。</span><span class="sxs-lookup"><span data-stu-id="507da-176">This translates to higher density and fewer required resources, especially when you use orchestrators like Kubernetes or Service Fabric.</span></span>

<span data-ttu-id="507da-177">容器化，在理想情况下，不需要对应用程序代码进行任何更改 (C\#)。</span><span class="sxs-lookup"><span data-stu-id="507da-177">Containerization, in ideal situations, does not require making any changes to the application code (C\#).</span></span> <span data-ttu-id="507da-178">在大多数情况下，你只需 Docker 部署元数据文件 （Dockerfile 和 Docker Compose 文件）。</span><span class="sxs-lookup"><span data-stu-id="507da-178">In most scenarios, you just need the Docker deployment metadata files (Dockerfiles and Docker Compose files).</span></span>

### <a name="next-steps"></a><span data-ttu-id="507da-179">后续步骤</span><span class="sxs-lookup"><span data-stu-id="507da-179">Next steps</span></span>

<span data-ttu-id="507da-180">浏览 GitHub wiki 上的更深入此内容：</span><span class="sxs-lookup"><span data-stu-id="507da-180">Explore this content more in-depth on the GitHub wiki:</span></span>

- [<span data-ttu-id="507da-181">如何容器化.NET Framework web 应用程序使用 Windows 容器和 Docker</span><span class="sxs-lookup"><span data-stu-id="507da-181">How to containerize the .NET Framework web apps with Windows Containers and Docker</span></span>](https://github.com/dotnet-architecture/eShopModernizing/wiki/02.-How-to-containerize-the-.NET-Framework-web-apps-with-Windows-Containers-and-Docker)
- [<span data-ttu-id="507da-182">将 Docker 支持添加到 WCF 服务</span><span class="sxs-lookup"><span data-stu-id="507da-182">Adding Docker Support to a WCF service</span></span>](https://github.com/dotnet-architecture/eShopModernizing/wiki/22.-Adding-Docker-Support)

## <a name="walkthrough-3-deploy-your-windows-containers-based-app-to-azure-vms"></a><span data-ttu-id="507da-183">演练 3:将 Windows 基于容器的应用部署到 Azure Vm</span><span class="sxs-lookup"><span data-stu-id="507da-183">Walkthrough 3: Deploy your Windows Containers-based app to Azure VMs</span></span>

### <a name="technical-walkthrough-availability"></a><span data-ttu-id="507da-184">技术演练可用性</span><span class="sxs-lookup"><span data-stu-id="507da-184">Technical walkthrough availability</span></span>

<span data-ttu-id="507da-185">全面的技术演练现已推出 eShopModernizing GitHub 存储库 wiki: [https://github.com/dotnet-architecture/eShopModernizing/wiki/03.-How-to-deploy-your-Windows-Containers-based-app-into-Azure-VMs-(Including-CI-CD)](https://github.com/dotnet-architecture/eShopModernizing/wiki/03.-How-to-deploy-your-Windows-Containers-based-app-into-Azure-VMs-(Including-CI-CD))</span><span class="sxs-lookup"><span data-stu-id="507da-185">The full technical walkthrough is available in the eShopModernizing GitHub repo wiki: [https://github.com/dotnet-architecture/eShopModernizing/wiki/03.-How-to-deploy-your-Windows-Containers-based-app-into-Azure-VMs-(Including-CI-CD)](https://github.com/dotnet-architecture/eShopModernizing/wiki/03.-How-to-deploy-your-Windows-Containers-based-app-into-Azure-VMs-(Including-CI-CD))</span></span>

### <a name="overview"></a><span data-ttu-id="507da-186">概述</span><span class="sxs-lookup"><span data-stu-id="507da-186">Overview</span></span>

<span data-ttu-id="507da-187">部署到 Docker 主机在 Windows Server 2016 虚拟机 (VM) 上 Azure 中，可让你快速设置开发/测试/暂存环境。</span><span class="sxs-lookup"><span data-stu-id="507da-187">Deploying to a Docker host on a Windows Server 2016 Virtual Machine (VM) in Azure lets you quickly set up development/test/staging environments.</span></span> <span data-ttu-id="507da-188">它还使您的测试人员或业务用户若要验证该应用程序的常见位置。</span><span class="sxs-lookup"><span data-stu-id="507da-188">It also gives you a common place for testers or business users to validate the app.</span></span> <span data-ttu-id="507da-189">Vm 还可以作为有效的基础结构服务 (IaaS) 生产环境。</span><span class="sxs-lookup"><span data-stu-id="507da-189">VMs also can be valid Infrastructure as a Service (IaaS) production environments.</span></span>

### <a name="goals"></a><span data-ttu-id="507da-190">目标</span><span class="sxs-lookup"><span data-stu-id="507da-190">Goals</span></span>

<span data-ttu-id="507da-191">本演练的目的是说明将 Windows 容器部署到基于 Windows Server 2016 或更高版本的 Azure Vm 时，有多个备选方法。</span><span class="sxs-lookup"><span data-stu-id="507da-191">The goal of this walkthrough is to show you the multiple alternatives you have when you deploy Windows Containers to Azure VMs that are based on Windows Server 2016 or later versions.</span></span>

### <a name="scenarios"></a><span data-ttu-id="507da-192">方案</span><span class="sxs-lookup"><span data-stu-id="507da-192">Scenarios</span></span>

<span data-ttu-id="507da-193">在本演练涵盖了几个方案。</span><span class="sxs-lookup"><span data-stu-id="507da-193">Several scenarios are covered in this walkthrough.</span></span>

#### <a name="scenario-a-deploy-to-an-azure-vm-from-a-dev-pc-through-docker-engine-connection"></a><span data-ttu-id="507da-194">情况 a:从开发人员电脑通过 Docker 引擎连接部署到 Azure VM</span><span class="sxs-lookup"><span data-stu-id="507da-194">Scenario A: Deploy to an Azure VM from a dev PC through Docker Engine connection</span></span>

![从开发人员电脑通过 Docker 引擎连接部署到 Azure VM](./media/image5-4.png)

<span data-ttu-id="507da-196">**图 5-4**。</span><span class="sxs-lookup"><span data-stu-id="507da-196">**Figure 5-4.**</span></span> <span data-ttu-id="507da-197">从开发人员电脑通过 Docker 引擎连接部署到 Azure VM</span><span class="sxs-lookup"><span data-stu-id="507da-197">Deploy to an Azure VM from a dev PC through a Docker Engine connection</span></span>

#### <a name="scenario-b-deploy-to-an-azure-vm-through-a-docker-registry"></a><span data-ttu-id="507da-198">方案 b:部署到 Azure VM 通过 Docker 注册表</span><span class="sxs-lookup"><span data-stu-id="507da-198">Scenario B: Deploy to an Azure VM through a Docker Registry</span></span>

![部署到 Azure VM 通过 Docker 注册表](./media/image5-5.png)

<span data-ttu-id="507da-200">**图 5-5**。</span><span class="sxs-lookup"><span data-stu-id="507da-200">**Figure 5-5.**</span></span> <span data-ttu-id="507da-201">部署到 Azure VM 通过 Docker 注册表</span><span class="sxs-lookup"><span data-stu-id="507da-201">Deploy to an Azure VM through a Docker Registry</span></span>

#### <a name="scenario-c-deploy-to-an-azure-vm-from-cicd-pipelines-in-azure-devops-services"></a><span data-ttu-id="507da-202">方案 c:从 Azure DevOps 服务中的 CI/CD 管道部署到 Azure VM</span><span class="sxs-lookup"><span data-stu-id="507da-202">Scenario C: Deploy to an Azure VM from CI/CD pipelines in Azure DevOps Services</span></span>

![从 Azure DevOps 服务中的 CI/CD 管道部署到 Azure VM](./media/image5-6.png)

<span data-ttu-id="507da-204">**如 5-6**。</span><span class="sxs-lookup"><span data-stu-id="507da-204">**Figure 5-6.**</span></span> <span data-ttu-id="507da-205">从 Azure DevOps 服务中的 CI/CD 管道部署到 Azure VM</span><span class="sxs-lookup"><span data-stu-id="507da-205">Deploy to an Azure VM from CI/CD pipelines in Azure DevOps Services</span></span>

### <a name="azure-vms-for-windows-containers"></a><span data-ttu-id="507da-206">用于 Windows 容器的 azure Vm</span><span class="sxs-lookup"><span data-stu-id="507da-206">Azure VMs for Windows Containers</span></span>

<span data-ttu-id="507da-207">Windows 容器的 azure Vm 是基于 Windows Server 2016、 Windows 10 或更高版本的 Vm，它们都具有 Docker 引擎设置。</span><span class="sxs-lookup"><span data-stu-id="507da-207">Azure VMs for Windows Containers are VMs based on Windows Server 2016, Windows 10, or later versions, both with Docker Engine set up.</span></span> <span data-ttu-id="507da-208">在大多数情况下，Windows Server 2016 Azure Vm 中使用。</span><span class="sxs-lookup"><span data-stu-id="507da-208">In most cases, Windows Server 2016 is used in the Azure VMs.</span></span>

<span data-ttu-id="507da-209">Azure 当前提供了一个名为的虚拟机**Windows Server 2016 with Containers**。</span><span class="sxs-lookup"><span data-stu-id="507da-209">Azure currently provides a VM named **Windows Server 2016 with Containers**.</span></span> <span data-ttu-id="507da-210">可以使用此 VM 用于尝试新的 Windows Server 容器功能，与 Windows Server Core 或 Windows Nano Server。</span><span class="sxs-lookup"><span data-stu-id="507da-210">You can use this VM to try the new Windows Server Container feature, with either Windows Server Core or Windows Nano Server.</span></span> <span data-ttu-id="507da-211">安装容器操作系统映像，这样，VM 就可以使用 Docker。</span><span class="sxs-lookup"><span data-stu-id="507da-211">Container OS images are installed, and then the VM is ready to use with Docker.</span></span>

### <a name="benefits"></a><span data-ttu-id="507da-212">优点</span><span class="sxs-lookup"><span data-stu-id="507da-212">Benefits</span></span>

<span data-ttu-id="507da-213">虽然 Windows 容器部署到 Azure 时，可以将它们部署到的本地 Windows Server 2016 Vm，可以轻松地开始使用随时可用的 Windows Server 容器 Vm。</span><span class="sxs-lookup"><span data-stu-id="507da-213">Although Windows Containers can be deployed to on-premises Windows Server 2016 VMs, when you deploy to Azure, you get an easier way to get started, with ready-to-use Windows Server Container VMs.</span></span> <span data-ttu-id="507da-214">您还了解常见的联机位置都能访问的测试人员和通过 Azure 虚拟机规模集自动可伸缩性。</span><span class="sxs-lookup"><span data-stu-id="507da-214">You also get a common online location that’s accessible to testers, and automatic scalability through Azure virtual machine scale sets.</span></span>

### <a name="next-steps"></a><span data-ttu-id="507da-215">后续步骤</span><span class="sxs-lookup"><span data-stu-id="507da-215">Next steps</span></span>

<span data-ttu-id="507da-216">浏览 GitHub wiki 上的更深入此内容：</span><span class="sxs-lookup"><span data-stu-id="507da-216">Explore this content more in-depth on the GitHub wiki:</span></span>

[https://github.com/dotnet-architecture/eShopModernizing/wiki/03.-How-to-deploy-your-Windows-Containers-based-app-into-Azure-VMs-(Including-CI-CD)](https://github.com/dotnet-architecture/eShopModernizing/wiki/03.-How-to-deploy-your-Windows-Containers-based-app-into-Azure-VMs-(Including-CI-CD))

## <a name="walkthrough-4-deploy-your-windows-containers-based-apps-to-azure-container-instances-aci"></a><span data-ttu-id="507da-217">演练 4:将 Windows 基于容器的应用部署到 Azure 容器实例 (ACI)</span><span class="sxs-lookup"><span data-stu-id="507da-217">Walkthrough 4: Deploy your Windows Containers-based apps to Azure Container Instances (ACI)</span></span>

### <a name="technical-walkthrough-availability"></a><span data-ttu-id="507da-218">技术演练可用性</span><span class="sxs-lookup"><span data-stu-id="507da-218">Technical walkthrough availability</span></span>

<span data-ttu-id="507da-219">全面的技术演练现已推出 eShopModernizing GitHub 存储库 wiki:</span><span class="sxs-lookup"><span data-stu-id="507da-219">The full technical walkthrough is available in the eShopModernizing GitHub repo wiki:</span></span>

<span data-ttu-id="507da-220">[将应用部署到 ACI （Azure 容器实例）](https://github.com/dotnet-architecture/eShopModernizing/wiki/05.-Deploying-the-Apps-to-ACI-(Azure-Container-Instances))</span><span class="sxs-lookup"><span data-stu-id="507da-220">[Deploying the Apps to ACI (Azure Container Instances)](https://github.com/dotnet-architecture/eShopModernizing/wiki/05.-Deploying-the-Apps-to-ACI-(Azure-Container-Instances))</span></span>

### <a name="overview"></a><span data-ttu-id="507da-221">概述</span><span class="sxs-lookup"><span data-stu-id="507da-221">Overview</span></span>

<span data-ttu-id="507da-222">[Azure 容器实例 (ACI)](https://docs.microsoft.com/azure/container-instances/)是具有可在其中部署容器的单个实例的容器开发/测试/暂存环境的最快方法。</span><span class="sxs-lookup"><span data-stu-id="507da-222">[Azure Container Instances (ACI)](https://docs.microsoft.com/azure/container-instances/) is the quickest way to have a Containers dev/test/staging environment where you can deploy single instances of containers.</span></span>

### <a name="goals"></a><span data-ttu-id="507da-223">目标</span><span class="sxs-lookup"><span data-stu-id="507da-223">Goals</span></span>

<span data-ttu-id="507da-224">本演练演示的主要方案时将 Windows 容器部署到 Azure 容器实例 (ACI) 和如何将 eShopModernizing 应用部署到 ACI。</span><span class="sxs-lookup"><span data-stu-id="507da-224">This walkthrough shows you the main scenarios when deploying Windows Containers to Azure Container Instances (ACI) and how you can deploy eShopModernizing Apps into ACI.</span></span>

### <a name="scenarios"></a><span data-ttu-id="507da-225">方案</span><span class="sxs-lookup"><span data-stu-id="507da-225">Scenarios</span></span>

<span data-ttu-id="507da-226">可以将 eShopModernizing 应用部署到 ACI 部署只需一个或所有应用 （MVC 应用程序，WebForms 应用程序或 WCF 服务） 等有关的变体。</span><span class="sxs-lookup"><span data-stu-id="507da-226">There can be variations about deploying the eShopModernizing apps into ACI such as deploying just one or all of the apps (MVC app, WebForms app or WCF service).</span></span> <span data-ttu-id="507da-227">如下所示的以下方案中您可以为容器看到到 ACI （Azure 容器实例） 的 ASP.NET MVC 应用程序以及这两个部署的 SQL Server 容器。</span><span class="sxs-lookup"><span data-stu-id="507da-227">In the following scenario shown below you can see the ASP.NET MVC app plus the SQL Server container both of them deployed as containers into ACI (Azure Container Instances).</span></span>

![从开发环境部署到 ACI](./media/image5-3.5.6.png)

### <a name="benefits"></a><span data-ttu-id="507da-229">优点</span><span class="sxs-lookup"><span data-stu-id="507da-229">Benefits</span></span>

<span data-ttu-id="507da-230">Azure 容器实例轻松创建和管理 Docker 容器在 Azure 中，而无需预配虚拟机或采用更高级别的服务。</span><span class="sxs-lookup"><span data-stu-id="507da-230">Azure Container Instances makes it easy to create and manage Docker containers in Azure, without having to provision virtual machines or adopt a higher-level service.</span></span> <span data-ttu-id="507da-231">使用 ACI，可以直接部署在 Azure 中的 Windows 容器并将其公开给 internet 完全限定的域名 (FQDN) 与在几秒内 （前提是必须准备的 Windows 容器映像中的 Docker 注册表，如 Docker 中心或 Azure 容器注册表中）。</span><span class="sxs-lookup"><span data-stu-id="507da-231">With ACI, you can directly deploy a Windows container in Azure and expose it to the internet with a fully qualified domain name (FQDN) in a matter of seconds (Provided that you have the Windows Container image ready in a Docker registry like Docker Hub or Azure Container Registry).</span></span>

### <a name="considerations"></a><span data-ttu-id="507da-232">注意事项</span><span class="sxs-lookup"><span data-stu-id="507da-232">Considerations</span></span>

<span data-ttu-id="507da-233">使用任一完整的.NET Framework 的 Windows 容器部署 ASP.NET 或 SQL Server 到 Azure 容器实例 (ACI) 不是与部署到常规的 Docker 主机 （如 Windows Server 2016 与 Windows 容器)，因为 Docker 映像必须相当快 /每次下载 （拉入从 Docker 注册表） 和 SQL 容器映像 (15.1 GB) 和 ASP.NET 容器映像 (13.9 GB) 的大小会非常大，但是它更廉价比维护你自己的 docker 主机 （永久联机使用 Windows 容器在 Azure 中的 VM 的 Windows Server 2016) 更不必说一些，但是，对于生产部署的理想选择 Kubernetes 在 Azure (AKS/ACS) 或 Azure Service Fabric 等整个业务流程协调程序。</span><span class="sxs-lookup"><span data-stu-id="507da-233">Deploying Windows Containers with either full .NET Framework / ASP.NET or SQL Server into Azure Container Instances (ACI) is not quite as fast as deploying to a regular Docker Host (like a Windows Server 2016 with Windows Containers) because the Docker image has to be downloaded (pulled from the Docker registry) every time and the sizes of the SQL container image (15.1 GB) and the ASP.NET container image (13.9 GB) are significantly large, however it is much cheaper than maintaining your own docker host (permanently on-line Windows Server 2016 with Windows Containers VM in Azure) not to mention a whole orchestrator like Kubernetes in Azure (AKS/ACS) or Azure Service Fabric which are, on the other hand, great choices for production deployments.</span></span>

<span data-ttu-id="507da-234">作为主结束时，使用 Azure 容器实例是一个非常引人注目的选项为开发/测试方案和 CI/CD 管道。</span><span class="sxs-lookup"><span data-stu-id="507da-234">As main conclusion, using Azure Container Instances is a very compelling option for Dev/Test scenarios and for CI/CD pipelines.</span></span>

## <a name="next-steps"></a><span data-ttu-id="507da-235">后续步骤</span><span class="sxs-lookup"><span data-stu-id="507da-235">Next steps</span></span>

<span data-ttu-id="507da-236">浏览 GitHub wiki 上的更深入此内容：</span><span class="sxs-lookup"><span data-stu-id="507da-236">Explore this content more in-depth on the GitHub wiki:</span></span>

[https://github.com/dotnet-architecture/eShopModernizing/wiki/05.-Deploying-the-Apps-to-ACI-(Azure-Container-Instances)](https://github.com/dotnet-architecture/eShopModernizing/wiki/05.-Deploying-the-Apps-to-ACI-(Azure-Container-Instances)TBD)

## <a name="walkthrough-5-deploy-your-windows-containers-based-apps-to-kubernetes-in-azure-container-service"></a><span data-ttu-id="507da-237">演练 5:将 Windows 基于容器的应用部署到 Azure 容器服务中 Kubernetes</span><span class="sxs-lookup"><span data-stu-id="507da-237">Walkthrough 5: Deploy your Windows Containers-based apps to Kubernetes in Azure Container Service</span></span>

### <a name="technical-walkthrough-availability"></a><span data-ttu-id="507da-238">技术演练可用性</span><span class="sxs-lookup"><span data-stu-id="507da-238">Technical walkthrough availability</span></span>

<span data-ttu-id="507da-239">全面的技术演练现已推出 eShopModernizing GitHub 存储库 wiki:</span><span class="sxs-lookup"><span data-stu-id="507da-239">The full technical walkthrough is available in the eShopModernizing GitHub repo wiki:</span></span>

[https://github.com/dotnet-architecture/eShopModernizing/wiki/04.-How-to-deploy-your-Windows-Containers-based-apps-into-Kubernetes-in-Azure-Container-Service-(Including-C-CD)](https://github.com/dotnet-architecture/eShopModernizing/wiki/04.-How-to-deploy-your-Windows-Containers-based-apps-into-Kubernetes-in-Azure-Container-Service-(Including-C-CD))

### <a name="overview"></a><span data-ttu-id="507da-240">概述</span><span class="sxs-lookup"><span data-stu-id="507da-240">Overview</span></span>

<span data-ttu-id="507da-241">基于 Windows 容器的应用程序需要快速使用从 IaaS Vm 即可移动更进一步的平台。</span><span class="sxs-lookup"><span data-stu-id="507da-241">An application that's based on Windows Containers will quickly need to use platforms, moving even further away from IaaS VMs.</span></span> <span data-ttu-id="507da-242">这需要能够轻松实现高可伸缩性和更好地自动可伸缩性，并得到显著提高自动执行部署和版本控制。</span><span class="sxs-lookup"><span data-stu-id="507da-242">This is needed to easily achieve high scalability and better automated scalability, and for a significant improvement in automated deployments and versioning.</span></span> <span data-ttu-id="507da-243">可以使用业务流程协调程序来实现这些目标[Kubernetes](https://kubernetes.io/)中的可用[Azure 容器服务](https://azure.microsoft.com/services/container-service/)。</span><span class="sxs-lookup"><span data-stu-id="507da-243">You can achieve these goals by using the orchestrator [Kubernetes](https://kubernetes.io/), available in [Azure Container Services](https://azure.microsoft.com/services/container-service/).</span></span>

### <a name="goals"></a><span data-ttu-id="507da-244">目标</span><span class="sxs-lookup"><span data-stu-id="507da-244">Goals</span></span>

<span data-ttu-id="507da-245">本演练的目的是了解如何基于 Windows 容器应用程序部署到 Kubernetes (也称为*K8s*) 在 Azure 容器服务中。</span><span class="sxs-lookup"><span data-stu-id="507da-245">The goal of this walkthrough is to learn how to deploy a Windows Container–based application to Kubernetes (also called *K8s*) in Azure Container Service.</span></span> <span data-ttu-id="507da-246">从零开始部署到 Kubernetes 是一个两步过程：</span><span class="sxs-lookup"><span data-stu-id="507da-246">Deploying to Kubernetes from scratch is a two-step process:</span></span>

1. <span data-ttu-id="507da-247">部署到 Azure 容器服务 Kubernetes 群集。</span><span class="sxs-lookup"><span data-stu-id="507da-247">Deploy a Kubernetes cluster to Azure Container Service.</span></span>

2. <span data-ttu-id="507da-248">将应用程序和相关的资源部署到 Kubernetes 群集。</span><span class="sxs-lookup"><span data-stu-id="507da-248">Deploy the application and related resources to the Kubernetes cluster.</span></span>

### <a name="scenarios"></a><span data-ttu-id="507da-249">方案</span><span class="sxs-lookup"><span data-stu-id="507da-249">Scenarios</span></span>

#### <a name="scenario-a-deploy-directly-to-a-kubernetes-cluster-from-a-dev-environment"></a><span data-ttu-id="507da-250">情况 a:将直接部署到 Kubernetes 群集从开发环境</span><span class="sxs-lookup"><span data-stu-id="507da-250">Scenario A: Deploy directly to a Kubernetes cluster from a dev environment</span></span>

![将直接部署到 Kubernetes 群集从开发环境](./media/image5-7.png)

<span data-ttu-id="507da-252">**图 5-7**。</span><span class="sxs-lookup"><span data-stu-id="507da-252">**Figure 5-7.**</span></span> <span data-ttu-id="507da-253">将直接部署到 Kubernetes 群集从开发环境</span><span class="sxs-lookup"><span data-stu-id="507da-253">Deploy directly to a Kubernetes cluster from a development environment</span></span>

#### <a name="scenario-b-deploy-to-a-kubernetes-cluster-from-cicd-pipelines-in-azure-devops-services"></a><span data-ttu-id="507da-254">方案 b:从 Azure DevOps 服务中的 CI/CD 管道部署到 Kubernetes 群集</span><span class="sxs-lookup"><span data-stu-id="507da-254">Scenario B: Deploy to a Kubernetes cluster from CI/CD pipelines in Azure DevOps Services</span></span>

![从 Azure DevOps 服务中的 CI/CD 管道部署到 Kubernetes 群集](./media/image5-8.png)

<span data-ttu-id="507da-256">**图 5-8**。</span><span class="sxs-lookup"><span data-stu-id="507da-256">**Figure 5-8.**</span></span> <span data-ttu-id="507da-257">从 Azure DevOps 服务中的 CI/CD 管道部署到 Kubernetes 群集</span><span class="sxs-lookup"><span data-stu-id="507da-257">Deploy to a Kubernetes cluster from CI/CD pipelines in Azure DevOps Services</span></span>

### <a name="benefits"></a><span data-ttu-id="507da-258">优点</span><span class="sxs-lookup"><span data-stu-id="507da-258">Benefits</span></span>

<span data-ttu-id="507da-259">有很多好处与部署到 Kubernetes 中的群集。</span><span class="sxs-lookup"><span data-stu-id="507da-259">There are many benefits to deploying to a cluster in Kubernetes.</span></span> <span data-ttu-id="507da-260">最大好处是，您将在其中可以扩大应用程序根据你想要使用 （内部的可伸缩性的现有节点中），并根据在群集 （节点或 Vm 的数量的容器实例数的生产就绪环境全局可伸缩性的群集）。</span><span class="sxs-lookup"><span data-stu-id="507da-260">The biggest benefit is that you get a production-ready environment in which you can scale out the application based on the number of container instances you want to use (inner-scalability in the existing nodes), and based on the number of nodes or VMs in the cluster (global scalability of the cluster).</span></span>

<span data-ttu-id="507da-261">Azure 容器服务特别为 Azure 优化了常用的开源工具和技术。</span><span class="sxs-lookup"><span data-stu-id="507da-261">Azure Container Service optimizes popular open-source tools and technologies specifically for Azure.</span></span> <span data-ttu-id="507da-262">获取打开的解决方案，提供可移植性，为你的容器和应用程序配置。</span><span class="sxs-lookup"><span data-stu-id="507da-262">You get an open solution that offers portability, both for your containers and for your application configuration.</span></span> <span data-ttu-id="507da-263">选择的大小，主机数和业务流程协调程序工具的容器服务可处理其他操作。</span><span class="sxs-lookup"><span data-stu-id="507da-263">You select the size, the number of hosts, and the orchestrator tools-Container Service handles everything else.</span></span>

<span data-ttu-id="507da-264">使用 Kubernetes，开发人员可以继续进行考虑物理机和虚拟机，从规划以容器为中心的基础结构，方便其他项中的以下功能：</span><span class="sxs-lookup"><span data-stu-id="507da-264">With Kubernetes, developers can progress from thinking about physical and virtual machines, to planning a container-centric infrastructure that facilitates the following capabilities, among others:</span></span>

- <span data-ttu-id="507da-265">基于多个容器的应用程序</span><span class="sxs-lookup"><span data-stu-id="507da-265">Applications based on multiple containers</span></span>

- <span data-ttu-id="507da-266">复制容器实例和水平自动缩放</span><span class="sxs-lookup"><span data-stu-id="507da-266">Replicating container instances and horizontal autoscaling</span></span>

- <span data-ttu-id="507da-267">命名和发现 (例如，内部 DNS)</span><span class="sxs-lookup"><span data-stu-id="507da-267">Naming and discovering (for example, internal DNS)</span></span>

- <span data-ttu-id="507da-268">均衡负载</span><span class="sxs-lookup"><span data-stu-id="507da-268">Balancing loads</span></span>

- <span data-ttu-id="507da-269">滚动更新</span><span class="sxs-lookup"><span data-stu-id="507da-269">Rolling updates</span></span>

- <span data-ttu-id="507da-270">分发机密</span><span class="sxs-lookup"><span data-stu-id="507da-270">Distributing secrets</span></span>

- <span data-ttu-id="507da-271">应用程序运行状况检查</span><span class="sxs-lookup"><span data-stu-id="507da-271">Application health checks</span></span>

## <a name="next-steps"></a><span data-ttu-id="507da-272">后续步骤</span><span class="sxs-lookup"><span data-stu-id="507da-272">Next steps</span></span>

<span data-ttu-id="507da-273">浏览 GitHub wiki 上的更深入此内容： [https://github.com/dotnet-architecture/eShopModernizing/wiki/04.-How-to-deploy-your-Windows-Containers-based-apps-into-Kubernetes-in-Azure-Container-Service-(Including-C-CD)](https://github.com/dotnet-architecture/eShopModernizing/wiki/04.-How-to-deploy-your-Windows-Containers-based-apps-into-Kubernetes-in-Azure-Container-Service-(Including-C-CD))</span><span class="sxs-lookup"><span data-stu-id="507da-273">Explore this content more in-depth on the GitHub wiki: [https://github.com/dotnet-architecture/eShopModernizing/wiki/04.-How-to-deploy-your-Windows-Containers-based-apps-into-Kubernetes-in-Azure-Container-Service-(Including-C-CD)](https://github.com/dotnet-architecture/eShopModernizing/wiki/04.-How-to-deploy-your-Windows-Containers-based-apps-into-Kubernetes-in-Azure-Container-Service-(Including-C-CD))</span></span>

## <a name="walkthrough-6-deploy-your-windows-containers-based-apps-to-azure-service-fabric"></a><span data-ttu-id="507da-274">演练 6:部署到 Azure Service Fabric Windows 基于容器的应用程序</span><span class="sxs-lookup"><span data-stu-id="507da-274">Walkthrough 6: Deploy your Windows Containers-based apps to Azure Service Fabric</span></span>

### <a name="technical-walkthrough-availability"></a><span data-ttu-id="507da-275">技术演练可用性</span><span class="sxs-lookup"><span data-stu-id="507da-275">Technical walkthrough availability</span></span>

<span data-ttu-id="507da-276">全面的技术演练现已推出 eShopModernizing GitHub 存储库 wiki:</span><span class="sxs-lookup"><span data-stu-id="507da-276">The full technical walkthrough is available in the eShopModernizing GitHub repo wiki:</span></span>

[https://github.com/dotnet-architecture/eShopModernizing/wiki/05.-How-to-deploy-your-Windows-Containers-based-apps-into-Azure-Service-Fabric-(Including-CI-CD)](https://github.com/dotnet-architecture/eShopModernizing/wiki/05.-How-to-deploy-your-Windows-Containers-based-apps-into-Azure-Service-Fabric-(Including-CI-CD))

### <a name="overview"></a><span data-ttu-id="507da-277">概述</span><span class="sxs-lookup"><span data-stu-id="507da-277">Overview</span></span>

<span data-ttu-id="507da-278">基于 Windows 容器快速应用程序需要使用从 IaaS Vm 即可移动更进一步的平台。</span><span class="sxs-lookup"><span data-stu-id="507da-278">An application based on Windows Containers quickly needs to use platforms, moving even further away from IaaS VMs.</span></span> <span data-ttu-id="507da-279">这需要能够轻松实现高可伸缩性和更好地自动可伸缩性，并得到显著提高自动执行部署和版本控制。</span><span class="sxs-lookup"><span data-stu-id="507da-279">This is needed to easily achieve high scalability and better automated scalability, and for a significant improvement in automated deployments and versioning.</span></span> <span data-ttu-id="507da-280">通过使用业务流程协调程序 Azure Service Fabric 中，这是可在 Azure 云中，但也可使用在本地，或甚至在不同的公有云，可以实现这些目标。</span><span class="sxs-lookup"><span data-stu-id="507da-280">You can achieve these goals by using the orchestrator Azure Service Fabric, which is available in the Azure cloud, but also available to use on-premises, or even in a different public cloud.</span></span>

### <a name="goals"></a><span data-ttu-id="507da-281">目标</span><span class="sxs-lookup"><span data-stu-id="507da-281">Goals</span></span>

<span data-ttu-id="507da-282">本演练的目的是了解如何基于 Windows 容器应用程序部署到 Azure 中的 Service Fabric 群集。</span><span class="sxs-lookup"><span data-stu-id="507da-282">The goal of this walkthrough is to learn how to deploy a Windows Container–based application to a Service Fabric cluster in Azure.</span></span> <span data-ttu-id="507da-283">从零开始部署到 Service Fabric 是一个两步过程：</span><span class="sxs-lookup"><span data-stu-id="507da-283">Deploying to Service Fabric from scratch is a two-step process:</span></span>

1. <span data-ttu-id="507da-284">将 Service Fabric 群集部署到 Azure （或不同的环境）。</span><span class="sxs-lookup"><span data-stu-id="507da-284">Deploy a Service Fabric cluster to Azure (or to a different environment).</span></span>

2. <span data-ttu-id="507da-285">将应用程序和相关的资源部署到 Service Fabric 群集。</span><span class="sxs-lookup"><span data-stu-id="507da-285">Deploy the application and related resources to the Service Fabric cluster.</span></span>

### <a name="scenarios"></a><span data-ttu-id="507da-286">方案</span><span class="sxs-lookup"><span data-stu-id="507da-286">Scenarios</span></span>

#### <a name="scenario-a-deploy-directly-to-a-service-fabric-cluster-from-a-dev-environment"></a><span data-ttu-id="507da-287">情况 a:将直接部署到 Service Fabric 群集从开发环境</span><span class="sxs-lookup"><span data-stu-id="507da-287">Scenario A: Deploy directly to a Service Fabric cluster from a dev environment</span></span>

![将直接部署到 Service Fabric 群集从开发环境](./media/image5-9.png)

> <span data-ttu-id="507da-289">**图 5-9**。</span><span class="sxs-lookup"><span data-stu-id="507da-289">**Figure 5-9.**</span></span> <span data-ttu-id="507da-290">将直接部署到 Service Fabric 群集从开发环境</span><span class="sxs-lookup"><span data-stu-id="507da-290">Deploy directly to a Service Fabric cluster from a development environment</span></span>

### <a name="scenario-b-deploy-to-a-service-fabric-cluster-from-cicd-pipelines-in-azure-devops-services"></a><span data-ttu-id="507da-291">方案 b:从 Azure DevOps 服务中的 CI/CD 管道部署到 Service Fabric 群集</span><span class="sxs-lookup"><span data-stu-id="507da-291">Scenario B: Deploy to a Service Fabric cluster from CI/CD pipelines in Azure DevOps Services</span></span>

![从 Azure DevOps 服务中的 CI/CD 管道部署到 Service Fabric 群集](./media/image5-10.png)

<span data-ttu-id="507da-293">**图 5-10**。</span><span class="sxs-lookup"><span data-stu-id="507da-293">**Figure 5-10.**</span></span> <span data-ttu-id="507da-294">从 Azure DevOps 服务中的 CI/CD 管道部署到 Service Fabric 群集</span><span class="sxs-lookup"><span data-stu-id="507da-294">Deploy to a Service Fabric cluster from CI/CD pipelines in Azure DevOps Services</span></span>

## <a name="benefits"></a><span data-ttu-id="507da-295">优点</span><span class="sxs-lookup"><span data-stu-id="507da-295">Benefits</span></span>

<span data-ttu-id="507da-296">将部署到 Service Fabric 中的群集的优点是类似于使用 Kubernetes 的好处。</span><span class="sxs-lookup"><span data-stu-id="507da-296">The benefits of deploying to a cluster in Service Fabric are similar to the benefits of using Kubernetes.</span></span> <span data-ttu-id="507da-297">一个区别，不过，是 Service Fabric 是更成熟的生产环境的 Windows 应用程序相比 Kubernetes，Kubernetes 1.9 版中的 Windows 容器的 beta 阶段中是 (2017 年 12 月)。</span><span class="sxs-lookup"><span data-stu-id="507da-297">One difference, though, is that Service Fabric is a more mature production environment for Windows applications compared to Kubernetes, which is in a beta phase for Windows Containers in Kubernetes version 1.9 (December 2017).</span></span> <span data-ttu-id="507da-298">Kubernetes 是更成熟的环境，适用于 Linux。</span><span class="sxs-lookup"><span data-stu-id="507da-298">Kubernetes is a more mature environment for Linux.</span></span>

<span data-ttu-id="507da-299">使用 Azure Service Fabric 的主要优势是您获取在其中可以扩大应用程序根据你想要使用 （内部的可伸缩性的现有节点中），并根据的数量的容器实例数的生产就绪环境节点或群集 （群集的全局可伸缩性） 中的 Vm。</span><span class="sxs-lookup"><span data-stu-id="507da-299">The main benefit of using Azure Service Fabric is that you get a production-ready environment in which you can scale out the application based on the number of container instances you want to use (inner-scalability in the existing nodes), and based on the number of nodes or VMs in the cluster (global scalability of the cluster).</span></span>

<span data-ttu-id="507da-300">Azure Service Fabric 提供了容器和应用程序配置为可移植性。</span><span class="sxs-lookup"><span data-stu-id="507da-300">Azure Service Fabric offers portability both for your containers and for your application configuration.</span></span> <span data-ttu-id="507da-301">您可以在 Azure 中，群集或安装在自己的数据中心中的本地 Service Fabric。</span><span class="sxs-lookup"><span data-stu-id="507da-301">You can have a Service Fabric cluster in Azure, or install it on-premises in your own datacenter.</span></span> <span data-ttu-id="507da-302">您甚至可以安装 Service Fabric 群集在另一个云，如[Amazon AWS](https://blogs.msdn.microsoft.com/azureservicefabric/2017/05/18/tutorial-how-to-create-a-service-fabric-standalone-cluster-with-aws-ec2-instances/)。</span><span class="sxs-lookup"><span data-stu-id="507da-302">You can even install a Service Fabric cluster in a different cloud, like [Amazon AWS](https://blogs.msdn.microsoft.com/azureservicefabric/2017/05/18/tutorial-how-to-create-a-service-fabric-standalone-cluster-with-aws-ec2-instances/).</span></span>

<span data-ttu-id="507da-303">使用 Service Fabric，开发人员可以继续进行从思考物理机和虚拟机规划以容器为中心的基础结构，方便其他项中的以下功能：</span><span class="sxs-lookup"><span data-stu-id="507da-303">With Service Fabric, developers can progress from thinking about physical and virtual machines to planning a container-centric infrastructure that facilitates the following capabilities, among others:</span></span>

- <span data-ttu-id="507da-304">基于多个容器的应用程序。</span><span class="sxs-lookup"><span data-stu-id="507da-304">Applications based on multiple containers.</span></span>

- <span data-ttu-id="507da-305">复制容器实例和水平自动缩放。</span><span class="sxs-lookup"><span data-stu-id="507da-305">Replicating container instances and horizontal autoscaling.</span></span>

- <span data-ttu-id="507da-306">命名和发现 (例如，内部 DNS)。</span><span class="sxs-lookup"><span data-stu-id="507da-306">Naming and discovering (for example, internal DNS).</span></span>

- <span data-ttu-id="507da-307">平衡负载。</span><span class="sxs-lookup"><span data-stu-id="507da-307">Balancing loads.</span></span>

- <span data-ttu-id="507da-308">滚动更新。</span><span class="sxs-lookup"><span data-stu-id="507da-308">Rolling updates.</span></span>

- <span data-ttu-id="507da-309">分发机密。</span><span class="sxs-lookup"><span data-stu-id="507da-309">Distributing secrets.</span></span>

- <span data-ttu-id="507da-310">应用程序运行状况检查。</span><span class="sxs-lookup"><span data-stu-id="507da-310">Application health checks.</span></span>

<span data-ttu-id="507da-311">以下功能是以独占方式 Service Fabric （与其他业务流程协调程序相比）：</span><span class="sxs-lookup"><span data-stu-id="507da-311">The following capabilities are exclusive in Service Fabric (compared to other orchestrators):</span></span>

- <span data-ttu-id="507da-312">有状态服务功能，通过 Reliable Services 应用程序模型。</span><span class="sxs-lookup"><span data-stu-id="507da-312">Stateful services capability, through the Reliable Services application model.</span></span>

- <span data-ttu-id="507da-313">执行组件模式，通过 Reliable Actors 应用程序模型。</span><span class="sxs-lookup"><span data-stu-id="507da-313">Actors pattern, through the Reliable Actors application model.</span></span>

- <span data-ttu-id="507da-314">部署精简进程，除了 Windows 或 Linux 容器。</span><span class="sxs-lookup"><span data-stu-id="507da-314">Deploy bare-bone processes, in addition to Windows or Linux containers.</span></span>

- <span data-ttu-id="507da-315">高级滚动更新和运行状况检查。</span><span class="sxs-lookup"><span data-stu-id="507da-315">Advanced rolling updates and health checks.</span></span>

### <a name="next-steps"></a><span data-ttu-id="507da-316">后续步骤</span><span class="sxs-lookup"><span data-stu-id="507da-316">Next steps</span></span>

<span data-ttu-id="507da-317">浏览 GitHub wiki 上的更深入此内容：</span><span class="sxs-lookup"><span data-stu-id="507da-317">Explore this content more in-depth on the GitHub wiki:</span></span>

[https://github.com/dotnet-architecture/eShopModernizing/wiki/05.-How-to-deploy-your-Windows-Containers-based-apps-into-Azure-Service-Fabric-(Including-CI-CD)](https://github.com/dotnet-architecture/eShopModernizing/wiki/05.-How-to-deploy-your-Windows-Containers-based-apps-into-Azure-Service-Fabric-(Including-CI-CD))

> [!div class="step-by-step"]
> <span data-ttu-id="507da-318">[上一页](lift-and-shift-existing-apps-devops/migrate-to-hybrid-cloud-scenarios.md)
> [下一页](conclusions.md)</span><span class="sxs-lookup"><span data-stu-id="507da-318">[Previous](lift-and-shift-existing-apps-devops/migrate-to-hybrid-cloud-scenarios.md)
[Next](conclusions.md)</span></span>
