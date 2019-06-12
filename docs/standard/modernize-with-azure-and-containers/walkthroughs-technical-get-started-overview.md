---
title: 演练和技术入门概述
description: 更新现有.NET 应用程序使用 Azure 云和 Windows 容器 |演练和技术可帮助入门的概述
ms.date: 04/28/2018
ms.openlocfilehash: 1ae6f3c1e739184356b97fa96e74bab402bf1d2a
ms.sourcegitcommit: 34593b4d0be779699d38a9949d6aec11561657ec
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2019
ms.locfileid: "66832959"
---
# <a name="walkthroughs-and-technical-get-started-overview"></a><span data-ttu-id="c8bd4-103">演练和技术入门概述</span><span class="sxs-lookup"><span data-stu-id="c8bd4-103">Walkthroughs and technical get started overview</span></span>

<span data-ttu-id="c8bd4-104">若要限制此电子书的大小，其他技术文档和完整的演练提供了在 GitHub 存储库中。</span><span class="sxs-lookup"><span data-stu-id="c8bd4-104">To limit the size of this e-book, additional technical documentation and the full walkthroughs were made available in a GitHub repository.</span></span> <span data-ttu-id="c8bd4-105">联机的此章中所述的演练一系列涵盖基于 Windows 容器和 Azure 上部署的多个环境的分步的设置。</span><span class="sxs-lookup"><span data-stu-id="c8bd4-105">The online series of walkthroughs that is described in this chapter covers the step-by-step setup of the multiple environments that are based on Windows Containers, and deployment to Azure.</span></span>

<span data-ttu-id="c8bd4-106">以下部分介绍每个演练有关其目标和高级愿景是什么，并提供了所涉及的任务的图表。</span><span class="sxs-lookup"><span data-stu-id="c8bd4-106">The following sections explain what each walkthrough is about, its objectives and high-level vision, and provides a diagram of the tasks that are involved.</span></span> <span data-ttu-id="c8bd4-107">可以获取自己的演练中*eShopModernizing*在应用 GitHub 存储库 wiki <https://github.com/dotnet-architecture/eShopModernizing/wiki>。</span><span class="sxs-lookup"><span data-stu-id="c8bd4-107">You can get the walkthroughs themselves in the *eShopModernizing* apps GitHub repo wiki at <https://github.com/dotnet-architecture/eShopModernizing/wiki>.</span></span>

## <a name="technical-walkthrough-list"></a><span data-ttu-id="c8bd4-108">技术演练列表</span><span class="sxs-lookup"><span data-stu-id="c8bd4-108">Technical walkthrough list</span></span>

<span data-ttu-id="c8bd4-109">下面的入门演练提供一致且全面的示例应用，你可以迁移使用容器，并在 Azure 中使用多个部署选项然后移动的技术指南。</span><span class="sxs-lookup"><span data-stu-id="c8bd4-109">The following get-started walkthroughs provide consistent and comprehensive technical guidance for sample apps that you can lift and shift by using containers, and then move by using multiple deployment choices in Azure.</span></span>

<span data-ttu-id="c8bd4-110">每个以下演练使用的新示例 eShopLegacy 和 eShopModernizing 应用，可在 GitHub 上<https://github.com/dotnet-architecture/eShopModernizing>。</span><span class="sxs-lookup"><span data-stu-id="c8bd4-110">Each of the following walkthroughs uses the new sample eShopLegacy and eShopModernizing apps, which are available on GitHub at <https://github.com/dotnet-architecture/eShopModernizing>.</span></span>

- <span data-ttu-id="c8bd4-111">**EShop 旧版应用 （基线应用实现现代化） 的教程**</span><span class="sxs-lookup"><span data-stu-id="c8bd4-111">**Tour of eShop legacy apps (baseline apps to modernize)**</span></span>

- <span data-ttu-id="c8bd4-112">**Windows 容器与容器化现有 ASP.NET web 应用 （WebForms 和 MVC）**</span><span class="sxs-lookup"><span data-stu-id="c8bd4-112">**Containerize your existing ASP.NET web apps (WebForms & MVC) with Windows Containers**</span></span>

- <span data-ttu-id="c8bd4-113">**容器化现有 WCF 服务 （N 层应用程序） 与 Windows 容器**</span><span class="sxs-lookup"><span data-stu-id="c8bd4-113">**Containerize your existing WCF services (N-Tier apps) with Windows Containers**</span></span>

- <span data-ttu-id="c8bd4-114">**将 Windows 基于容器的应用部署到 Azure Vm**</span><span class="sxs-lookup"><span data-stu-id="c8bd4-114">**Deploy your Windows Containers-based app to Azure VMs**</span></span>

- <span data-ttu-id="c8bd4-115">**将 Windows 基于容器的应用部署到 Azure 容器服务中 Kubernetes**</span><span class="sxs-lookup"><span data-stu-id="c8bd4-115">**Deploy your Windows Containers-based apps to Kubernetes in Azure Container Service**</span></span>

## <a name="walkthrough-1-tour-of-eshop-legacy-apps"></a><span data-ttu-id="c8bd4-116">演练 1:EShop 旧版应用的教程</span><span class="sxs-lookup"><span data-stu-id="c8bd4-116">Walkthrough 1: Tour of eShop legacy apps</span></span>

### <a name="technical-walkthrough-availability"></a><span data-ttu-id="c8bd4-117">技术演练可用性</span><span class="sxs-lookup"><span data-stu-id="c8bd4-117">Technical walkthrough availability</span></span>

<span data-ttu-id="c8bd4-118">全面的技术演练现已推出 eShopModernizing GitHub 存储库 wiki:</span><span class="sxs-lookup"><span data-stu-id="c8bd4-118">The full technical walkthrough is available in the eShopModernizing GitHub repo wiki:</span></span>

[<span data-ttu-id="c8bd4-119">eShopModernizing wiki 演练</span><span class="sxs-lookup"><span data-stu-id="c8bd4-119">eShopModernizing wiki walkthroughs</span></span>](https://github.com/dotnet-architecture/eShopModernizing/wiki)

### <a name="overview"></a><span data-ttu-id="c8bd4-120">概述</span><span class="sxs-lookup"><span data-stu-id="c8bd4-120">Overview</span></span>

<span data-ttu-id="c8bd4-121">在本演练中，可以浏览对旧版应用程序的三个示例的初始实现。</span><span class="sxs-lookup"><span data-stu-id="c8bd4-121">In this walkthrough, you can explore the initial implementation of three sample legacy applications.</span></span> <span data-ttu-id="c8bd4-122">前两个示例 web 应用具有单一式体系结构，并使用传统的 ASP.NET 创建的。</span><span class="sxs-lookup"><span data-stu-id="c8bd4-122">The first two sample web apps have a monolithic architecture, and were created by using classic ASP.NET.</span></span> <span data-ttu-id="c8bd4-123">一个应用程序基于 ASP.NET 4.x MVC;第二个应用程序基于 ASP.NET 4.x Web 窗体。</span><span class="sxs-lookup"><span data-stu-id="c8bd4-123">One application is based on ASP.NET 4.x MVC; the second application is based on ASP.NET 4.x Web Forms.</span></span>
<span data-ttu-id="c8bd4-124">第三个应用程序是由客户端 WinForms 应用程序和服务器端的 3 层应用程序[Windows Communication Foundation (WCF)](../../framework/wcf/whats-wcf.md)服务。</span><span class="sxs-lookup"><span data-stu-id="c8bd4-124">The third app is a 3-Tier app composed by a client WinForms app and a server-side [Windows Communication Foundation (WCF)](../../framework/wcf/whats-wcf.md) service.</span></span>

<span data-ttu-id="c8bd4-125">所有这些应用程序目前[eShopModernizing GitHub 存储库](https://github.com/dotnet-architecture/eShopModernizing)。</span><span class="sxs-lookup"><span data-stu-id="c8bd4-125">All these applications are available at the [eShopModernizing GitHub repo](https://github.com/dotnet-architecture/eShopModernizing).</span></span>

### <a name="goals"></a><span data-ttu-id="c8bd4-126">目标</span><span class="sxs-lookup"><span data-stu-id="c8bd4-126">Goals</span></span>

<span data-ttu-id="c8bd4-127">本演练中的主要目标是只需熟悉这些应用程序，以及其代码和配置。</span><span class="sxs-lookup"><span data-stu-id="c8bd4-127">The main goal of this walkthrough is simply to get familiar with these apps, and with their code and configuration.</span></span> <span data-ttu-id="c8bd4-128">可以配置应用程序，使它们生成和使用模拟数据，而无需使用 SQL 数据库中，出于测试目的。</span><span class="sxs-lookup"><span data-stu-id="c8bd4-128">You can configure the apps so that they generate and use mock data, without using the SQL database, for testing purposes.</span></span> <span data-ttu-id="c8bd4-129">此可选配置基于依赖关系注入，方法中。</span><span class="sxs-lookup"><span data-stu-id="c8bd4-129">This optional config is based on dependency injection, in a decoupled way.</span></span>

### <a name="scenario-1-aspnet-web-apps"></a><span data-ttu-id="c8bd4-130">方案 1:ASP.NET Web 应用程序</span><span class="sxs-lookup"><span data-stu-id="c8bd4-130">Scenario 1: ASP.NET Web apps</span></span>

<span data-ttu-id="c8bd4-131">下图显示了原始的旧版 ASP.NET web 应用程序的简单方案。</span><span class="sxs-lookup"><span data-stu-id="c8bd4-131">The figure below shows the simple scenario of the original legacy ASP.NET web applications.</span></span>

![简单的体系结构方案中的原始的旧版 ASP.NET web 应用程序](./media/image5-1.png)

<span data-ttu-id="c8bd4-133">从业务域的角度来看，这两个应用管理功能提供相同的目录。</span><span class="sxs-lookup"><span data-stu-id="c8bd4-133">From a business domain perspective, both apps offer the same catalog management features.</span></span> <span data-ttu-id="c8bd4-134">EShop 企业团队的成员将使用该应用可以查看和编辑产品目录。</span><span class="sxs-lookup"><span data-stu-id="c8bd4-134">Members of the eShop enterprise team would use the app to view and edit the product catalog.</span></span>

<span data-ttu-id="c8bd4-135">下图显示了初始应用程序的屏幕截图。</span><span class="sxs-lookup"><span data-stu-id="c8bd4-135">The next figure shows the initial app screenshots.</span></span>

![ASP.NET MVC 和 ASP.NET Web 窗体应用程序 （现有/旧版技术）](./media/image5-2.png)

<span data-ttu-id="c8bd4-137">依赖关系在 ASP.NET 4.x 或更早版本 （不管是 MVC 或 Web 窗体） 意味着除非通过使用 ASP.NET Core MVC 完全重写代码，这些应用程序不会运行.NET Core 上。</span><span class="sxs-lookup"><span data-stu-id="c8bd4-137">Dependencies in ASP.NET 4.x or earlier versions (either for MVC or for Web Forms) means that these applications won’t run on .NET Core unless the code is fully rewritten by using ASP.NET Core MVC.</span></span>

### <a name="scenario-2-wcf-service-and-winforms-client-app-3-tier-app"></a><span data-ttu-id="c8bd4-138">方案 2:WCF 服务和 WinForms 客户端应用程序 （第 3 层应用程序）</span><span class="sxs-lookup"><span data-stu-id="c8bd4-138">Scenario 2: WCF service and WinForms client app (3-Tier app)</span></span>

<span data-ttu-id="c8bd4-139">下图显示了原始的第 3 层旧应用程序的简单方案。</span><span class="sxs-lookup"><span data-stu-id="c8bd4-139">The figure below shows the simple scenario of the original 3-Tier legacy application.</span></span>

![简单的体系结构方案中的原始的旧版第 3 层应用程序与 WCF 服务和 WinForms 客户端应用程序](./media/image5-1.5.png)

### <a name="benefits"></a><span data-ttu-id="c8bd4-141">优点</span><span class="sxs-lookup"><span data-stu-id="c8bd4-141">Benefits</span></span>

<span data-ttu-id="c8bd4-142">本演练的好处很简单：只需熟悉的代码和初始应用程序。</span><span class="sxs-lookup"><span data-stu-id="c8bd4-142">The benefits of this walkthrough are simple: Just get familiar with the code and initial apps.</span></span>

### <a name="next-steps"></a><span data-ttu-id="c8bd4-143">后续步骤</span><span class="sxs-lookup"><span data-stu-id="c8bd4-143">Next steps</span></span>

<span data-ttu-id="c8bd4-144">浏览 GitHub wiki 上的更深入此内容：</span><span class="sxs-lookup"><span data-stu-id="c8bd4-144">Explore this content more in-depth on the GitHub wiki:</span></span>

- [<span data-ttu-id="c8bd4-145">教程基线 ASP.NET MVC 和 Web 窗体"传统"应用程序</span><span class="sxs-lookup"><span data-stu-id="c8bd4-145">Tour on the baseline ASP.NET MVC and Web Forms “legacy” apps</span></span>](https://github.com/dotnet-architecture/eShopModernizing/wiki/01.-Tour-on-the-ASP.NET-MVC-and-WebForms-apps-implementation-code)
- [<span data-ttu-id="c8bd4-146">基线 WCF 服务和 WinForms （3 层）"传统"应用程序的教程</span><span class="sxs-lookup"><span data-stu-id="c8bd4-146">Tour on the baseline WCF service and WinForms (3-Tier) “legacy” app</span></span>](https://github.com/dotnet-architecture/eShopModernizing/wiki/21.-Tour-on-the-WCF-service-and-WinForms-apps)

## <a name="walkthrough-2-containerize-your-existing-net-applications-with-windows-containers"></a><span data-ttu-id="c8bd4-147">演练 2:容器化现有.NET 应用程序与 Windows 容器</span><span class="sxs-lookup"><span data-stu-id="c8bd4-147">Walkthrough 2: Containerize your existing .NET applications with Windows Containers</span></span>

### <a name="overview"></a><span data-ttu-id="c8bd4-148">概述</span><span class="sxs-lookup"><span data-stu-id="c8bd4-148">Overview</span></span>

<span data-ttu-id="c8bd4-149">使用 Windows 容器可提高现有.NET 应用程序，如基于 MVC、 Web 窗体或 WCF，向生产、 开发和测试环境的部署。</span><span class="sxs-lookup"><span data-stu-id="c8bd4-149">Use Windows Containers to improve deployment of existing .NET applications, like those based on MVC, Web Forms, or WCF, to production, development, and test environments.</span></span>

### <a name="goals"></a><span data-ttu-id="c8bd4-150">目标</span><span class="sxs-lookup"><span data-stu-id="c8bd4-150">Goals</span></span>

<span data-ttu-id="c8bd4-151">本演练的目的是说明用于容器化现有.NET Framework 应用程序的多个选项。</span><span class="sxs-lookup"><span data-stu-id="c8bd4-151">The goal of this walkthrough is to show you several options for containerizing an existing .NET Framework application.</span></span> <span data-ttu-id="c8bd4-152">你可以：</span><span class="sxs-lookup"><span data-stu-id="c8bd4-152">You can:</span></span>

- <span data-ttu-id="c8bd4-153">通过使用容器化应用程序[Visual Studio 2017 Tools for Docker](/aspnet/core/host-and-deploy/docker/visual-studio-tools-for-docker) （Visual Studio 2017 或更高版本）。</span><span class="sxs-lookup"><span data-stu-id="c8bd4-153">Containerize your application by using [Visual Studio 2017 Tools for Docker](/aspnet/core/host-and-deploy/docker/visual-studio-tools-for-docker) (Visual Studio 2017 or later versions).</span></span>

- <span data-ttu-id="c8bd4-154">通过手动添加容器化应用程序[Dockerfile](https://docs.docker.com/engine/reference/builder/)，然后使用[Docker CLI](https://docs.docker.com/engine/reference/commandline/cli/)。</span><span class="sxs-lookup"><span data-stu-id="c8bd4-154">Containerize your application by manually adding a [Dockerfile](https://docs.docker.com/engine/reference/builder/), and then using the [Docker CLI](https://docs.docker.com/engine/reference/commandline/cli/).</span></span>

- <span data-ttu-id="c8bd4-155">通过使用容器化应用程序[Img2Docker](https://github.com/docker/communitytools-image2docker-win)工具 （Docker 的开放源代码工具）。</span><span class="sxs-lookup"><span data-stu-id="c8bd4-155">Containerize your application by using the [Img2Docker](https://github.com/docker/communitytools-image2docker-win) tool (an open-source tool from Docker).</span></span>

<span data-ttu-id="c8bd4-156">本演练重点介绍 Visual Studio 2017 Tools for Docker 方法，但其他两种方法是从使用 Dockerfile 非常相似。</span><span class="sxs-lookup"><span data-stu-id="c8bd4-156">This walkthrough focuses on the Visual Studio 2017 Tools for Docker approach, but the other two approaches are fairly similar in regard to using Dockerfiles.</span></span>

### <a name="scenario-1-containerized-aspnet-web-apps"></a><span data-ttu-id="c8bd4-157">方案 1:容器化的 ASP.NET web 应用</span><span class="sxs-lookup"><span data-stu-id="c8bd4-157">Scenario 1: Containerized ASP.NET web apps</span></span>

<span data-ttu-id="c8bd4-158">下图显示了容器化的 eShop 旧版 web 应用应用程序的方案。</span><span class="sxs-lookup"><span data-stu-id="c8bd4-158">Figure below shows the scenario for containerized eShop legacy web apps applications.</span></span>

![简化的体系结构关系图的适用于容器化 ASP.NET 应用程序在开发环境](./media/image5-3.png)

### <a name="scenario-2-containerized-wcf-service"></a><span data-ttu-id="c8bd4-160">方案 2:容器化的 WCF 服务</span><span class="sxs-lookup"><span data-stu-id="c8bd4-160">Scenario 2: Containerized WCF service</span></span>

<span data-ttu-id="c8bd4-161">下图显示了包含容器化的 WCF 服务的第 3 层应用程序的方案。</span><span class="sxs-lookup"><span data-stu-id="c8bd4-161">Figure below shows the scenario for a 3-Tier app with a containerized WCF service.</span></span>

![简化的开发环境中的容器化 WCF 服务的体系结构关系图](./media/image5-3.5.png)

### <a name="benefits"></a><span data-ttu-id="c8bd4-163">优点</span><span class="sxs-lookup"><span data-stu-id="c8bd4-163">Benefits</span></span>

<span data-ttu-id="c8bd4-164">有在容器中运行整体式应用程序的优点。</span><span class="sxs-lookup"><span data-stu-id="c8bd4-164">There are advantages to running your monolithic application in a container.</span></span> <span data-ttu-id="c8bd4-165">首先，创建用于应用程序的映像。</span><span class="sxs-lookup"><span data-stu-id="c8bd4-165">First, you create an image for the application.</span></span> <span data-ttu-id="c8bd4-166">从该点开始，每个部署在同一环境中运行。</span><span class="sxs-lookup"><span data-stu-id="c8bd4-166">From that point on, every deployment runs in the same environment.</span></span> <span data-ttu-id="c8bd4-167">每个容器使用相同的 OS 版本，具有相同版本的安装的依赖项、 使用相同的.NET framework 版本，并使用相同的过程生成。</span><span class="sxs-lookup"><span data-stu-id="c8bd4-167">Every container uses the same OS version, has the same version of dependencies installed, uses the same .NET framework version, and is built by using the same process.</span></span> <span data-ttu-id="c8bd4-168">基本上，使用的 Docker 映像控制你的应用程序的依赖项。</span><span class="sxs-lookup"><span data-stu-id="c8bd4-168">Basically, you control the dependencies of your application by using a Docker image.</span></span> <span data-ttu-id="c8bd4-169">部署容器时，依赖项与应用程序同步。</span><span class="sxs-lookup"><span data-stu-id="c8bd4-169">The dependencies travel with the application when you deploy the containers.</span></span>

<span data-ttu-id="c8bd4-170">另一个好处是开发人员可以在由 Windows 容器提供一致的环境中运行应用程序。</span><span class="sxs-lookup"><span data-stu-id="c8bd4-170">An additional benefit is that developers can run the application in the consistent environment that's provided by Windows Containers.</span></span> <span data-ttu-id="c8bd4-171">可以立即发现仅某些版本出现的问题，而不是在过渡或生产环境中呈现。</span><span class="sxs-lookup"><span data-stu-id="c8bd4-171">Issues that appear only with certain versions can be spotted immediately, instead of surfacing in a staging or production environment.</span></span> <span data-ttu-id="c8bd4-172">在开发环境中的开发团队成员使用的差异不那么重要应用程序在容器中运行时。</span><span class="sxs-lookup"><span data-stu-id="c8bd4-172">Differences in development environments used by members of the development team matter less when applications run in containers.</span></span>

<span data-ttu-id="c8bd4-173">容器化应用程序还具有 flatter 横向扩展曲线。</span><span class="sxs-lookup"><span data-stu-id="c8bd4-173">Containerized applications also have a flatter scale-out curve.</span></span> <span data-ttu-id="c8bd4-174">容器化应用程序，你有多个应用程序和服务实例 （基于容器） 中的 VM 或物理机到每台计算机的常规应用程序部署进行比较。</span><span class="sxs-lookup"><span data-stu-id="c8bd4-174">Containerized apps enable you to have more application and service instances (based on containers) in a VM or physical machine compared to regular application deployments per machine.</span></span> <span data-ttu-id="c8bd4-175">这会转换为更高的密度和更少所需的资源，尤其是当使用 Kubernetes 等业务流程协调程序。</span><span class="sxs-lookup"><span data-stu-id="c8bd4-175">This translates to higher density and fewer required resources, especially when you use orchestrators like Kubernetes.</span></span>

<span data-ttu-id="c8bd4-176">容器化，在理想情况下，不需要对应用程序代码进行任何更改 (C\#)。</span><span class="sxs-lookup"><span data-stu-id="c8bd4-176">Containerization, in ideal situations, does not require making any changes to the application code (C\#).</span></span> <span data-ttu-id="c8bd4-177">在大多数情况下，你只需 Docker 部署元数据文件 （Dockerfile 和 Docker Compose 文件）。</span><span class="sxs-lookup"><span data-stu-id="c8bd4-177">In most scenarios, you just need the Docker deployment metadata files (Dockerfiles and Docker Compose files).</span></span>

### <a name="next-steps"></a><span data-ttu-id="c8bd4-178">后续步骤</span><span class="sxs-lookup"><span data-stu-id="c8bd4-178">Next steps</span></span>

<span data-ttu-id="c8bd4-179">浏览 GitHub wiki 上的更深入此内容：</span><span class="sxs-lookup"><span data-stu-id="c8bd4-179">Explore this content more in-depth on the GitHub wiki:</span></span>

- [<span data-ttu-id="c8bd4-180">如何容器化.NET Framework web 应用程序使用 Windows 容器和 Docker</span><span class="sxs-lookup"><span data-stu-id="c8bd4-180">How to containerize the .NET Framework web apps with Windows Containers and Docker</span></span>](https://github.com/dotnet-architecture/eShopModernizing/wiki/02.-How-to-containerize-the-.NET-Framework-web-apps-with-Windows-Containers-and-Docker)
- [<span data-ttu-id="c8bd4-181">将 Docker 支持添加到 WCF 服务</span><span class="sxs-lookup"><span data-stu-id="c8bd4-181">Adding Docker Support to a WCF service</span></span>](https://github.com/dotnet-architecture/eShopModernizing/wiki/22.-Adding-Docker-Support)

## <a name="walkthrough-3-deploy-your-windows-containers-based-app-to-azure-vms"></a><span data-ttu-id="c8bd4-182">演练 3:将 Windows 基于容器的应用部署到 Azure Vm</span><span class="sxs-lookup"><span data-stu-id="c8bd4-182">Walkthrough 3: Deploy your Windows Containers-based app to Azure VMs</span></span>

### <a name="technical-walkthrough-availability"></a><span data-ttu-id="c8bd4-183">技术演练可用性</span><span class="sxs-lookup"><span data-stu-id="c8bd4-183">Technical walkthrough availability</span></span>

<span data-ttu-id="c8bd4-184">全面的技术演练现已推出 eShopModernizing GitHub 存储库 wiki: <https://github.com/dotnet-architecture/eShopModernizing/wiki/06.-Deploying-your-Windows-Containers-based-app-into-Azure-VMs-(Including-CI-CD)></span><span class="sxs-lookup"><span data-stu-id="c8bd4-184">The full technical walkthrough is available in the eShopModernizing GitHub repo wiki: <https://github.com/dotnet-architecture/eShopModernizing/wiki/06.-Deploying-your-Windows-Containers-based-app-into-Azure-VMs-(Including-CI-CD)></span></span>

### <a name="overview"></a><span data-ttu-id="c8bd4-185">概述</span><span class="sxs-lookup"><span data-stu-id="c8bd4-185">Overview</span></span>

<span data-ttu-id="c8bd4-186">部署到 Docker 主机在 Windows Server 2016 虚拟机 (VM) 上 Azure 中，可让你快速设置开发/测试/暂存环境。</span><span class="sxs-lookup"><span data-stu-id="c8bd4-186">Deploying to a Docker host on a Windows Server 2016 Virtual Machine (VM) in Azure lets you quickly set up development/test/staging environments.</span></span> <span data-ttu-id="c8bd4-187">它还使您的测试人员或业务用户若要验证该应用程序的常见位置。</span><span class="sxs-lookup"><span data-stu-id="c8bd4-187">It also gives you a common place for testers or business users to validate the app.</span></span> <span data-ttu-id="c8bd4-188">Vm 还可以作为有效的基础结构服务 (IaaS) 生产环境。</span><span class="sxs-lookup"><span data-stu-id="c8bd4-188">VMs also can be valid Infrastructure as a Service (IaaS) production environments.</span></span>

### <a name="goals"></a><span data-ttu-id="c8bd4-189">目标</span><span class="sxs-lookup"><span data-stu-id="c8bd4-189">Goals</span></span>

<span data-ttu-id="c8bd4-190">本演练的目的是说明将 Windows 容器部署到基于 Windows Server 2016 或更高版本的 Azure Vm 时，有多个备选方法。</span><span class="sxs-lookup"><span data-stu-id="c8bd4-190">The goal of this walkthrough is to show you the multiple alternatives you have when you deploy Windows Containers to Azure VMs that are based on Windows Server 2016 or later versions.</span></span>

### <a name="scenarios"></a><span data-ttu-id="c8bd4-191">方案</span><span class="sxs-lookup"><span data-stu-id="c8bd4-191">Scenarios</span></span>

<span data-ttu-id="c8bd4-192">在本演练涵盖了几个方案。</span><span class="sxs-lookup"><span data-stu-id="c8bd4-192">Several scenarios are covered in this walkthrough.</span></span>

#### <a name="scenario-a-deploy-to-an-azure-vm-from-a-dev-pc-through-docker-engine-connection"></a><span data-ttu-id="c8bd4-193">情况 a:从开发人员电脑通过 Docker 引擎连接部署到 Azure VM</span><span class="sxs-lookup"><span data-stu-id="c8bd4-193">Scenario A: Deploy to an Azure VM from a dev PC through Docker Engine connection</span></span>

![从开发人员电脑通过 Docker 引擎连接部署到 Azure VM](./media/image5-4.png)

<span data-ttu-id="c8bd4-195">**图 5-4**。</span><span class="sxs-lookup"><span data-stu-id="c8bd4-195">**Figure 5-4.**</span></span> <span data-ttu-id="c8bd4-196">从开发人员电脑通过 Docker 引擎连接部署到 Azure VM</span><span class="sxs-lookup"><span data-stu-id="c8bd4-196">Deploy to an Azure VM from a dev PC through a Docker Engine connection</span></span>

#### <a name="scenario-b-deploy-to-an-azure-vm-through-a-docker-registry"></a><span data-ttu-id="c8bd4-197">方案 b:部署到 Azure VM 通过 Docker 注册表</span><span class="sxs-lookup"><span data-stu-id="c8bd4-197">Scenario B: Deploy to an Azure VM through a Docker Registry</span></span>

![部署到 Azure VM 通过 Docker 注册表](./media/image5-5.png)

<span data-ttu-id="c8bd4-199">**图 5-5**。</span><span class="sxs-lookup"><span data-stu-id="c8bd4-199">**Figure 5-5.**</span></span> <span data-ttu-id="c8bd4-200">部署到 Azure VM 通过 Docker 注册表</span><span class="sxs-lookup"><span data-stu-id="c8bd4-200">Deploy to an Azure VM through a Docker Registry</span></span>

#### <a name="scenario-c-deploy-to-an-azure-vm-from-cicd-pipelines-in-azure-devops-services"></a><span data-ttu-id="c8bd4-201">方案 c:从 Azure DevOps 服务中的 CI/CD 管道部署到 Azure VM</span><span class="sxs-lookup"><span data-stu-id="c8bd4-201">Scenario C: Deploy to an Azure VM from CI/CD pipelines in Azure DevOps Services</span></span>

![从 Azure DevOps 服务中的 CI/CD 管道部署到 Azure VM](./media/image5-6.png)

<span data-ttu-id="c8bd4-203">**如 5-6**。</span><span class="sxs-lookup"><span data-stu-id="c8bd4-203">**Figure 5-6.**</span></span> <span data-ttu-id="c8bd4-204">从 Azure DevOps 服务中的 CI/CD 管道部署到 Azure VM</span><span class="sxs-lookup"><span data-stu-id="c8bd4-204">Deploy to an Azure VM from CI/CD pipelines in Azure DevOps Services</span></span>

### <a name="azure-vms-for-windows-containers"></a><span data-ttu-id="c8bd4-205">用于 Windows 容器的 azure Vm</span><span class="sxs-lookup"><span data-stu-id="c8bd4-205">Azure VMs for Windows Containers</span></span>

<span data-ttu-id="c8bd4-206">Windows 容器的 azure Vm 是基于 Windows Server 2016、 Windows 10 或更高版本的 Vm，它们都具有 Docker 引擎设置。</span><span class="sxs-lookup"><span data-stu-id="c8bd4-206">Azure VMs for Windows Containers are VMs based on Windows Server 2016, Windows 10, or later versions, both with Docker Engine set up.</span></span> <span data-ttu-id="c8bd4-207">在大多数情况下，Windows Server 2016 Azure Vm 中使用。</span><span class="sxs-lookup"><span data-stu-id="c8bd4-207">In most cases, Windows Server 2016 is used in the Azure VMs.</span></span>

<span data-ttu-id="c8bd4-208">Azure 当前提供了一个名为的虚拟机**Windows Server 2016 with Containers**。</span><span class="sxs-lookup"><span data-stu-id="c8bd4-208">Azure currently provides a VM named **Windows Server 2016 with Containers**.</span></span> <span data-ttu-id="c8bd4-209">可以使用此 VM 用于尝试新的 Windows Server 容器功能，与 Windows Server Core 或 Windows Nano Server。</span><span class="sxs-lookup"><span data-stu-id="c8bd4-209">You can use this VM to try the new Windows Server Container feature, with either Windows Server Core or Windows Nano Server.</span></span> <span data-ttu-id="c8bd4-210">安装容器操作系统映像，这样，VM 就可以使用 Docker。</span><span class="sxs-lookup"><span data-stu-id="c8bd4-210">Container OS images are installed, and then the VM is ready to use with Docker.</span></span>

### <a name="benefits"></a><span data-ttu-id="c8bd4-211">优点</span><span class="sxs-lookup"><span data-stu-id="c8bd4-211">Benefits</span></span>

<span data-ttu-id="c8bd4-212">虽然 Windows 容器部署到 Azure 时，可以将它们部署到的本地 Windows Server 2016 Vm，可以轻松地开始使用随时可用的 Windows Server 容器 Vm。</span><span class="sxs-lookup"><span data-stu-id="c8bd4-212">Although Windows Containers can be deployed to on-premises Windows Server 2016 VMs, when you deploy to Azure, you get an easier way to get started, with ready-to-use Windows Server Container VMs.</span></span> <span data-ttu-id="c8bd4-213">您还了解常见的联机位置都能访问的测试人员和通过 Azure 虚拟机规模集自动可伸缩性。</span><span class="sxs-lookup"><span data-stu-id="c8bd4-213">You also get a common online location that’s accessible to testers, and automatic scalability through Azure virtual machine scale sets.</span></span>

### <a name="next-steps"></a><span data-ttu-id="c8bd4-214">后续步骤</span><span class="sxs-lookup"><span data-stu-id="c8bd4-214">Next steps</span></span>

<span data-ttu-id="c8bd4-215">浏览 GitHub wiki 上的更深入此内容：</span><span class="sxs-lookup"><span data-stu-id="c8bd4-215">Explore this content more in-depth on the GitHub wiki:</span></span>

<https://github.com/dotnet-architecture/eShopModernizing/wiki/06.-Deploying-your-Windows-Containers-based-app-into-Azure-VMs-(Including-CI-CD)>

## <a name="walkthrough-4-deploy-your-windows-containers-based-apps-to-azure-container-instances-aci"></a><span data-ttu-id="c8bd4-216">演练 4:将 Windows 基于容器的应用部署到 Azure 容器实例 (ACI)</span><span class="sxs-lookup"><span data-stu-id="c8bd4-216">Walkthrough 4: Deploy your Windows Containers-based apps to Azure Container Instances (ACI)</span></span>

### <a name="technical-walkthrough-availability"></a><span data-ttu-id="c8bd4-217">技术演练可用性</span><span class="sxs-lookup"><span data-stu-id="c8bd4-217">Technical walkthrough availability</span></span>

<span data-ttu-id="c8bd4-218">全面的技术演练现已推出 eShopModernizing GitHub 存储库 wiki:</span><span class="sxs-lookup"><span data-stu-id="c8bd4-218">The full technical walkthrough is available in the eShopModernizing GitHub repo wiki:</span></span>

<span data-ttu-id="c8bd4-219">[将应用部署到 ACI （Azure 容器实例）](https://github.com/dotnet-architecture/eShopModernizing/wiki/05.-Deploying-the-Apps-to-ACI-(Azure-Container-Instances))</span><span class="sxs-lookup"><span data-stu-id="c8bd4-219">[Deploying the Apps to ACI (Azure Container Instances)](https://github.com/dotnet-architecture/eShopModernizing/wiki/05.-Deploying-the-Apps-to-ACI-(Azure-Container-Instances))</span></span>

### <a name="overview"></a><span data-ttu-id="c8bd4-220">概述</span><span class="sxs-lookup"><span data-stu-id="c8bd4-220">Overview</span></span>

<span data-ttu-id="c8bd4-221">[Azure 容器实例 (ACI)](https://docs.microsoft.com/azure/container-instances/)是具有可在其中部署容器的单个实例的容器开发/测试/暂存环境的最快方法。</span><span class="sxs-lookup"><span data-stu-id="c8bd4-221">[Azure Container Instances (ACI)](https://docs.microsoft.com/azure/container-instances/) is the quickest way to have a Containers dev/test/staging environment where you can deploy single instances of containers.</span></span>

### <a name="goals"></a><span data-ttu-id="c8bd4-222">目标</span><span class="sxs-lookup"><span data-stu-id="c8bd4-222">Goals</span></span>

<span data-ttu-id="c8bd4-223">本演练演示的主要方案时将 Windows 容器部署到 Azure 容器实例 (ACI) 和如何将 eShopModernizing 应用部署到 ACI。</span><span class="sxs-lookup"><span data-stu-id="c8bd4-223">This walkthrough shows you the main scenarios when deploying Windows Containers to Azure Container Instances (ACI) and how you can deploy eShopModernizing Apps into ACI.</span></span>

### <a name="scenarios"></a><span data-ttu-id="c8bd4-224">方案</span><span class="sxs-lookup"><span data-stu-id="c8bd4-224">Scenarios</span></span>

<span data-ttu-id="c8bd4-225">可以将 eShopModernizing 应用部署到 ACI 部署只需一个或所有应用 （MVC 应用程序，WebForms 应用程序或 WCF 服务） 等有关的变体。</span><span class="sxs-lookup"><span data-stu-id="c8bd4-225">There can be variations about deploying the eShopModernizing apps into ACI such as deploying just one or all of the apps (MVC app, WebForms app or WCF service).</span></span> <span data-ttu-id="c8bd4-226">如下所示的以下方案中您可以为容器看到到 ACI （Azure 容器实例） 的 ASP.NET MVC 应用程序以及这两个部署的 SQL Server 容器。</span><span class="sxs-lookup"><span data-stu-id="c8bd4-226">In the following scenario shown below you can see the ASP.NET MVC app plus the SQL Server container both of them deployed as containers into ACI (Azure Container Instances).</span></span>

![从开发环境部署到 ACI](./media/image5-3.5.6.png)

### <a name="benefits"></a><span data-ttu-id="c8bd4-228">优点</span><span class="sxs-lookup"><span data-stu-id="c8bd4-228">Benefits</span></span>

<span data-ttu-id="c8bd4-229">Azure 容器实例轻松创建和管理 Docker 容器在 Azure 中，而无需预配虚拟机或采用更高级别的服务。</span><span class="sxs-lookup"><span data-stu-id="c8bd4-229">Azure Container Instances makes it easy to create and manage Docker containers in Azure, without having to provision virtual machines or adopt a higher-level service.</span></span> <span data-ttu-id="c8bd4-230">使用 ACI，可以直接部署在 Azure 中的 Windows 容器并将其公开给 internet 完全限定的域名 (FQDN) 与在几秒内 （前提是必须准备的 Windows 容器映像中的 Docker 注册表，如 Docker 中心或 Azure 容器注册表中）。</span><span class="sxs-lookup"><span data-stu-id="c8bd4-230">With ACI, you can directly deploy a Windows container in Azure and expose it to the internet with a fully qualified domain name (FQDN) in a matter of seconds (Provided that you have the Windows Container image ready in a Docker registry like Docker Hub or Azure Container Registry).</span></span>

### <a name="considerations"></a><span data-ttu-id="c8bd4-231">注意事项</span><span class="sxs-lookup"><span data-stu-id="c8bd4-231">Considerations</span></span>

<span data-ttu-id="c8bd4-232">使用任一完整的.NET Framework 的 Windows 容器部署 ASP.NET 或 SQL Server 到 Azure 容器实例 (ACI) 不是与部署到常规的 Docker 主机 （如 Windows Server 2016 与 Windows 容器)，因为 Docker 映像必须相当快 /每次下载 （拉入从 Docker 注册表） 和 SQL 容器映像 (15.1 GB) 和 ASP.NET 容器映像 (13.9 GB) 的大小会非常大，但是它更廉价比维护你自己的 docker 主机 （永久联机使用 Windows 容器在 Azure 中的 VM 的 Windows Server 2016) 更不必说 Kubernetes 在 Azure (AKS) 中的是，但是，对于生产部署的不错选择等整个业务流程协调程序。</span><span class="sxs-lookup"><span data-stu-id="c8bd4-232">Deploying Windows Containers with either full .NET Framework / ASP.NET or SQL Server into Azure Container Instances (ACI) is not quite as fast as deploying to a regular Docker Host (like a Windows Server 2016 with Windows Containers) because the Docker image has to be downloaded (pulled from the Docker registry) every time and the sizes of the SQL container image (15.1 GB) and the ASP.NET container image (13.9 GB) are significantly large, however it is much cheaper than maintaining your own docker host (permanently on-line Windows Server 2016 with Windows Containers VM in Azure) not to mention a whole orchestrator like Kubernetes in Azure (AKS) which is, on the other hand, a great choice for production deployments.</span></span>

<span data-ttu-id="c8bd4-233">作为主结束时，使用 Azure 容器实例是一个非常引人注目的选项为开发/测试方案和 CI/CD 管道。</span><span class="sxs-lookup"><span data-stu-id="c8bd4-233">As main conclusion, using Azure Container Instances is a very compelling option for Dev/Test scenarios and for CI/CD pipelines.</span></span>

## <a name="next-steps"></a><span data-ttu-id="c8bd4-234">后续步骤</span><span class="sxs-lookup"><span data-stu-id="c8bd4-234">Next steps</span></span>

<span data-ttu-id="c8bd4-235">浏览 GitHub wiki 上的更深入此内容：</span><span class="sxs-lookup"><span data-stu-id="c8bd4-235">Explore this content more in-depth on the GitHub wiki:</span></span>

[https://github.com/dotnet-architecture/eShopModernizing/wiki/05.-Deploying-the-Apps-to-ACI-(Azure-Container-Instances)](https://github.com/dotnet-architecture/eShopModernizing/wiki/05.-Deploying-the-Apps-to-ACI-(Azure-Container-Instances))

## <a name="walkthrough-5-deploy-your-windows-containers-based-apps-to-kubernetes-in-azure-container-service"></a><span data-ttu-id="c8bd4-236">演练 5:将 Windows 基于容器的应用部署到 Azure 容器服务中 Kubernetes</span><span class="sxs-lookup"><span data-stu-id="c8bd4-236">Walkthrough 5: Deploy your Windows Containers-based apps to Kubernetes in Azure Container Service</span></span>

### <a name="technical-walkthrough-availability"></a><span data-ttu-id="c8bd4-237">技术演练可用性</span><span class="sxs-lookup"><span data-stu-id="c8bd4-237">Technical walkthrough availability</span></span>

<span data-ttu-id="c8bd4-238">全面的技术演练现已推出 eShopModernizing GitHub 存储库 wiki:</span><span class="sxs-lookup"><span data-stu-id="c8bd4-238">The full technical walkthrough is available in the eShopModernizing GitHub repo wiki:</span></span>

<https://github.com/dotnet-architecture/eShopModernizing/wiki/04.-How-to-deploy-your-Windows-Containers-based-apps-into-Kubernetes-in-Azure-Container-Service-(Including-CI-CD)>

### <a name="overview"></a><span data-ttu-id="c8bd4-239">概述</span><span class="sxs-lookup"><span data-stu-id="c8bd4-239">Overview</span></span>

<span data-ttu-id="c8bd4-240">基于 Windows 容器的应用程序需要快速使用从 IaaS Vm 即可移动更进一步的平台。</span><span class="sxs-lookup"><span data-stu-id="c8bd4-240">An application that's based on Windows Containers will quickly need to use platforms, moving even further away from IaaS VMs.</span></span> <span data-ttu-id="c8bd4-241">这需要能够轻松实现高可伸缩性和更好地自动可伸缩性，并得到显著提高自动执行部署和版本控制。</span><span class="sxs-lookup"><span data-stu-id="c8bd4-241">This is needed to easily achieve high scalability and better automated scalability, and for a significant improvement in automated deployments and versioning.</span></span> <span data-ttu-id="c8bd4-242">可以使用业务流程协调程序来实现这些目标[Kubernetes](https://kubernetes.io/)中的可用[Azure 容器服务](https://azure.microsoft.com/services/container-service/)。</span><span class="sxs-lookup"><span data-stu-id="c8bd4-242">You can achieve these goals by using the orchestrator [Kubernetes](https://kubernetes.io/), available in [Azure Container Services](https://azure.microsoft.com/services/container-service/).</span></span>

### <a name="goals"></a><span data-ttu-id="c8bd4-243">目标</span><span class="sxs-lookup"><span data-stu-id="c8bd4-243">Goals</span></span>

<span data-ttu-id="c8bd4-244">本演练的目的是了解如何基于 Windows 容器应用程序部署到 Kubernetes (也称为*K8s*) 在 Azure 容器服务中。</span><span class="sxs-lookup"><span data-stu-id="c8bd4-244">The goal of this walkthrough is to learn how to deploy a Windows Container–based application to Kubernetes (also called *K8s*) in Azure Container Service.</span></span> <span data-ttu-id="c8bd4-245">从零开始部署到 Kubernetes 是一个两步过程：</span><span class="sxs-lookup"><span data-stu-id="c8bd4-245">Deploying to Kubernetes from scratch is a two-step process:</span></span>

1. <span data-ttu-id="c8bd4-246">部署到 Azure 容器服务 Kubernetes 群集。</span><span class="sxs-lookup"><span data-stu-id="c8bd4-246">Deploy a Kubernetes cluster to Azure Container Service.</span></span>

2. <span data-ttu-id="c8bd4-247">将应用程序和相关的资源部署到 Kubernetes 群集。</span><span class="sxs-lookup"><span data-stu-id="c8bd4-247">Deploy the application and related resources to the Kubernetes cluster.</span></span>

### <a name="scenarios"></a><span data-ttu-id="c8bd4-248">方案</span><span class="sxs-lookup"><span data-stu-id="c8bd4-248">Scenarios</span></span>

#### <a name="scenario-a-deploy-directly-to-a-kubernetes-cluster-from-a-dev-environment"></a><span data-ttu-id="c8bd4-249">情况 a:将直接部署到 Kubernetes 群集从开发环境</span><span class="sxs-lookup"><span data-stu-id="c8bd4-249">Scenario A: Deploy directly to a Kubernetes cluster from a dev environment</span></span>

![将直接部署到 Kubernetes 群集从开发环境](./media/image5-7.png)

<span data-ttu-id="c8bd4-251">**图 5-7**。</span><span class="sxs-lookup"><span data-stu-id="c8bd4-251">**Figure 5-7.**</span></span> <span data-ttu-id="c8bd4-252">将直接部署到 Kubernetes 群集从开发环境</span><span class="sxs-lookup"><span data-stu-id="c8bd4-252">Deploy directly to a Kubernetes cluster from a development environment</span></span>

#### <a name="scenario-b-deploy-to-a-kubernetes-cluster-from-cicd-pipelines-in-azure-devops-services"></a><span data-ttu-id="c8bd4-253">方案 b:从 Azure DevOps 服务中的 CI/CD 管道部署到 Kubernetes 群集</span><span class="sxs-lookup"><span data-stu-id="c8bd4-253">Scenario B: Deploy to a Kubernetes cluster from CI/CD pipelines in Azure DevOps Services</span></span>

![从 Azure DevOps 服务中的 CI/CD 管道部署到 Kubernetes 群集](./media/image5-8.png)

<span data-ttu-id="c8bd4-255">**图 5-8**。</span><span class="sxs-lookup"><span data-stu-id="c8bd4-255">**Figure 5-8.**</span></span> <span data-ttu-id="c8bd4-256">从 Azure DevOps 服务中的 CI/CD 管道部署到 Kubernetes 群集</span><span class="sxs-lookup"><span data-stu-id="c8bd4-256">Deploy to a Kubernetes cluster from CI/CD pipelines in Azure DevOps Services</span></span>

### <a name="benefits"></a><span data-ttu-id="c8bd4-257">优点</span><span class="sxs-lookup"><span data-stu-id="c8bd4-257">Benefits</span></span>

<span data-ttu-id="c8bd4-258">有很多好处与部署到 Kubernetes 中的群集。</span><span class="sxs-lookup"><span data-stu-id="c8bd4-258">There are many benefits to deploying to a cluster in Kubernetes.</span></span> <span data-ttu-id="c8bd4-259">最大好处是，您将在其中可以扩大应用程序根据你想要使用 （内部的可伸缩性的现有节点中），并根据在群集 （节点或 Vm 的数量的容器实例数的生产就绪环境全局可伸缩性的群集）。</span><span class="sxs-lookup"><span data-stu-id="c8bd4-259">The biggest benefit is that you get a production-ready environment in which you can scale out the application based on the number of container instances you want to use (inner-scalability in the existing nodes), and based on the number of nodes or VMs in the cluster (global scalability of the cluster).</span></span>

<span data-ttu-id="c8bd4-260">Azure 容器服务特别为 Azure 优化了常用的开源工具和技术。</span><span class="sxs-lookup"><span data-stu-id="c8bd4-260">Azure Container Service optimizes popular open-source tools and technologies specifically for Azure.</span></span> <span data-ttu-id="c8bd4-261">获取打开的解决方案，提供可移植性，为你的容器和应用程序配置。</span><span class="sxs-lookup"><span data-stu-id="c8bd4-261">You get an open solution that offers portability, both for your containers and for your application configuration.</span></span> <span data-ttu-id="c8bd4-262">选择的大小，主机数和业务流程协调程序工具的容器服务可处理其他操作。</span><span class="sxs-lookup"><span data-stu-id="c8bd4-262">You select the size, the number of hosts, and the orchestrator tools-Container Service handles everything else.</span></span>

<span data-ttu-id="c8bd4-263">使用 Kubernetes，开发人员可以继续进行考虑物理机和虚拟机，从规划以容器为中心的基础结构，方便其他项中的以下功能：</span><span class="sxs-lookup"><span data-stu-id="c8bd4-263">With Kubernetes, developers can progress from thinking about physical and virtual machines, to planning a container-centric infrastructure that facilitates the following capabilities, among others:</span></span>

- <span data-ttu-id="c8bd4-264">基于多个容器的应用程序</span><span class="sxs-lookup"><span data-stu-id="c8bd4-264">Applications based on multiple containers</span></span>

- <span data-ttu-id="c8bd4-265">复制容器实例和水平自动缩放</span><span class="sxs-lookup"><span data-stu-id="c8bd4-265">Replicating container instances and horizontal autoscaling</span></span>

- <span data-ttu-id="c8bd4-266">命名和发现 (例如，内部 DNS)</span><span class="sxs-lookup"><span data-stu-id="c8bd4-266">Naming and discovering (for example, internal DNS)</span></span>

- <span data-ttu-id="c8bd4-267">均衡负载</span><span class="sxs-lookup"><span data-stu-id="c8bd4-267">Balancing loads</span></span>

- <span data-ttu-id="c8bd4-268">滚动更新</span><span class="sxs-lookup"><span data-stu-id="c8bd4-268">Rolling updates</span></span>

- <span data-ttu-id="c8bd4-269">分发机密</span><span class="sxs-lookup"><span data-stu-id="c8bd4-269">Distributing secrets</span></span>

- <span data-ttu-id="c8bd4-270">应用程序运行状况检查</span><span class="sxs-lookup"><span data-stu-id="c8bd4-270">Application health checks</span></span>

## <a name="next-steps"></a><span data-ttu-id="c8bd4-271">后续步骤</span><span class="sxs-lookup"><span data-stu-id="c8bd4-271">Next steps</span></span>

<span data-ttu-id="c8bd4-272">浏览 GitHub wiki 上的更深入此内容： <https://github.com/dotnet-architecture/eShopModernizing/wiki/04.-How-to-deploy-your-Windows-Containers-based-apps-into-Kubernetes-in-Azure-Container-Service-(Including-CI-CD)></span><span class="sxs-lookup"><span data-stu-id="c8bd4-272">Explore this content more in-depth on the GitHub wiki: <https://github.com/dotnet-architecture/eShopModernizing/wiki/04.-How-to-deploy-your-Windows-Containers-based-apps-into-Kubernetes-in-Azure-Container-Service-(Including-CI-CD)></span></span>

## <a name="walkthrough-6-deploy-your-windows-containers-based-apps-to-azure-app-service-for-containers"></a><span data-ttu-id="c8bd4-273">演练 6:将 Windows 基于容器的应用部署到用于容器的 Azure 应用服务</span><span class="sxs-lookup"><span data-stu-id="c8bd4-273">Walkthrough 6: Deploy your Windows Containers-based apps to Azure App Service for Containers</span></span>

### <a name="technical-walkthrough-availability"></a><span data-ttu-id="c8bd4-274">技术演练可用性</span><span class="sxs-lookup"><span data-stu-id="c8bd4-274">Technical walkthrough availability</span></span>

<span data-ttu-id="c8bd4-275">全面的技术演练现已推出 eShopModernizing GitHub 存储库 wiki:</span><span class="sxs-lookup"><span data-stu-id="c8bd4-275">The full technical walkthrough is available in the eShopModernizing GitHub repo wiki:</span></span>

<https://github.com/dotnet-architecture/eShopModernizing/wiki/Deploy-Windows-Container-to-Azure-App-Service>

### <a name="overview"></a><span data-ttu-id="c8bd4-276">概述</span><span class="sxs-lookup"><span data-stu-id="c8bd4-276">Overview</span></span>

<span data-ttu-id="c8bd4-277">使用 Windows 容器的简单容器化应用程序可轻松地部署到用于容器的 Azure 应用服务中。</span><span class="sxs-lookup"><span data-stu-id="c8bd4-277">A simple containerized application using Windows Containers can easily be deployed to Azure App Service for Containers.</span></span> <span data-ttu-id="c8bd4-278">这是大多数基于 Windows 容器的应用程序的推荐的方法。</span><span class="sxs-lookup"><span data-stu-id="c8bd4-278">This is the recommended approach for most Windows Container-based applications.</span></span>

### <a name="goals"></a><span data-ttu-id="c8bd4-279">目标</span><span class="sxs-lookup"><span data-stu-id="c8bd4-279">Goals</span></span>

<span data-ttu-id="c8bd4-280">本演练的目的是了解如何基于 Windows 容器应用程序部署到用于容器的 Azure 应用服务从注册表 （Docker 中心或 Azure 容器注册表）。</span><span class="sxs-lookup"><span data-stu-id="c8bd4-280">The goal of this walkthrough is to learn how to deploy a Windows Container–based application to Azure App Service for Containers from a registry (Docker Hub or Azure Container Registry).</span></span>

### <a name="scenario"></a><span data-ttu-id="c8bd4-281">方案</span><span class="sxs-lookup"><span data-stu-id="c8bd4-281">Scenario</span></span>

![Windows 基于容器的应用部署到用于容器的 Azure 应用服务](./media/image5-11.png)

### <a name="benefits"></a><span data-ttu-id="c8bd4-283">优点</span><span class="sxs-lookup"><span data-stu-id="c8bd4-283">Benefits</span></span>

<span data-ttu-id="c8bd4-284">部署到用于容器的 Azure 应用服务提供的容器的 Azure 应用服务 PaaS 的优势与配对的好处。</span><span class="sxs-lookup"><span data-stu-id="c8bd4-284">Deploying to Azure App Service for Containers offers the benefits of containers paired with the PaaS benefits of Azure App Service.</span></span> <span data-ttu-id="c8bd4-285">应用服务可以垂直和水平，同时轻松缩放，并且可以配置为自动缩放以满足不断变化的需求。</span><span class="sxs-lookup"><span data-stu-id="c8bd4-285">The app service can easily be scaled both vertically and horizontally, and can be configured to autoscale to meet changing demands.</span></span> <span data-ttu-id="c8bd4-286">零停机时间就可以执行更新，并轻松地还配置从注册表进行持续部署的配置。</span><span class="sxs-lookup"><span data-stu-id="c8bd4-286">Updates can be performed with zero downtime and configuration of continuous deployment from a registry is easily configured as well.</span></span>

## <a name="next-steps"></a><span data-ttu-id="c8bd4-287">后续步骤</span><span class="sxs-lookup"><span data-stu-id="c8bd4-287">Next steps</span></span>

<span data-ttu-id="c8bd4-288">浏览 GitHub wiki 上的更深入此内容： <https://github.com/dotnet-architecture/eShopModernizing/wiki/Deploy-Windows-Container-to-Azure-App-Service></span><span class="sxs-lookup"><span data-stu-id="c8bd4-288">Explore this content more in-depth on the GitHub wiki: <https://github.com/dotnet-architecture/eShopModernizing/wiki/Deploy-Windows-Container-to-Azure-App-Service></span></span>

> [!div class="step-by-step"]
> <span data-ttu-id="c8bd4-289">[上一页](lift-and-shift-existing-apps-devops/migrate-to-hybrid-cloud-scenarios.md)
> [下一页](conclusions.md)</span><span class="sxs-lookup"><span data-stu-id="c8bd4-289">[Previous](lift-and-shift-existing-apps-devops/migrate-to-hybrid-cloud-scenarios.md)
[Next](conclusions.md)</span></span>
