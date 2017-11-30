---
title: "Azure 的开发过程"
description: "设计使用 ASP.NET Core 和 Azure 的现代 Web 应用程序 |Azure 的开发过程"
author: ardalis
ms.author: wiwagn
ms.date: 10/08/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.openlocfilehash: e676c1225f7d11381808040cf101e897e0726ad4
ms.sourcegitcommit: bbde43da655ae7bea1977f7af7345eb87bd7fd5f
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/21/2017
---
# <a name="development-process-for-azure"></a><span data-ttu-id="dbad6-103">Azure 的开发过程</span><span class="sxs-lookup"><span data-stu-id="dbad6-103">Development process for Azure</span></span>

> <span data-ttu-id="dbad6-104">_"利用云，个人及小型企业可以对齐其指和立即设置企业级的服务。"_</span><span class="sxs-lookup"><span data-stu-id="dbad6-104">_"With the cloud, individuals and small businesses can snap their fingers and instantly set up enterprise-class services."_</span></span>  
> <span data-ttu-id="dbad6-105">_-Roy Stephan_</span><span class="sxs-lookup"><span data-stu-id="dbad6-105">_- Roy Stephan_</span></span>

 ## <a name="vision"></a><span data-ttu-id="dbad6-106">Vision</span><span class="sxs-lookup"><span data-stu-id="dbad6-106">Vision</span></span>

> <span data-ttu-id="dbad6-107">*开发设计良好的 ASP.NET 核心应用程序您喜欢使用 Visual Studio 或 dotnet CLI 和 Visual Studio Code 或首选编辑器的方法。*</span><span class="sxs-lookup"><span data-stu-id="dbad6-107">*Develop well-designed ASP .NET Core applications the way you like, using Visual Studio or the dotnet CLI and Visual Studio Code or your editor of choice.*</span></span>

## <a name="development-environment-for-aspnet-core-apps"></a><span data-ttu-id="dbad6-108">对于 ASP.NET Core 应用程序的开发环境</span><span class="sxs-lookup"><span data-stu-id="dbad6-108">Development environment for ASP.NET Core apps</span></span>

### <a name="development-tools-choices-ide-or-editor"></a><span data-ttu-id="dbad6-109">开发工具的选择： IDE 或编辑器</span><span class="sxs-lookup"><span data-stu-id="dbad6-109">Development tools choices: IDE or editor</span></span>

<span data-ttu-id="dbad6-110">是否需要完整且功能强大的 IDE 或轻量，并灵活编辑器，则 Microsoft 将具有你开发 ASP.NET Core 应用程序时涉及。</span><span class="sxs-lookup"><span data-stu-id="dbad6-110">Whether you prefer a full and powerful IDE or a lightweight and agile editor, Microsoft has you covered when developing ASP.NET Core applications.</span></span>

<span data-ttu-id="dbad6-111">**Visual Studio 2017 年。**</span><span class="sxs-lookup"><span data-stu-id="dbad6-111">**Visual Studio 2017.**</span></span> <span data-ttu-id="dbad6-112">如果你使用*Visual Studio 2017*你可以生成 ASP.NET Core 应用程序，只要你有*.NET 核心跨平台开发*安装的工作负荷。</span><span class="sxs-lookup"><span data-stu-id="dbad6-112">If you're using *Visual Studio 2017* you can build ASP.NET Core applications as long as you have the *.NET Core cross-platform development* workload installed.</span></span> <span data-ttu-id="dbad6-113">图 10-1 Visual Studio 2017 设置对话框中显示的所需的工作负荷。</span><span class="sxs-lookup"><span data-stu-id="dbad6-113">Figure 10-1 shows the required workload in the Visual Studio 2017 setup dialog.</span></span>

![](./media/image10-1.png)

<span data-ttu-id="dbad6-114">**图 10-1。**</span><span class="sxs-lookup"><span data-stu-id="dbad6-114">**Figure 10-1.**</span></span> <span data-ttu-id="dbad6-115">在 Visual Studio 2017 中安装.NET 核心工作负荷。</span><span class="sxs-lookup"><span data-stu-id="dbad6-115">Installing the .NET Core workload in Visual Studio 2017.</span></span>

[<span data-ttu-id="dbad6-116">下载 Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="dbad6-116">Download Visual Studio 2017</span></span>](https://www.visualstudio.com/downloads/)

<span data-ttu-id="dbad6-117">**Visual Studio Code 和 dotnet CLI** （适用于 Mac、 Linux 和 Windows 的跨平台工具）。</span><span class="sxs-lookup"><span data-stu-id="dbad6-117">**Visual Studio Code and dotnet CLI** (Cross-Platform Tools for Mac, Linux and Windows).</span></span> <span data-ttu-id="dbad6-118">如果需要支持任何开发语言的轻量和跨平台编辑器，可以使用 Microsoft Visual Studio 代码和 dotnet CLI。</span><span class="sxs-lookup"><span data-stu-id="dbad6-118">If you prefer a lightweight and cross-platform editor supporting any development language, you can use Microsoft Visual Studio Code and the dotnet CLI.</span></span> <span data-ttu-id="dbad6-119">这些产品提供简单而稳定可靠的体验，简化了开发人员工作流。</span><span class="sxs-lookup"><span data-stu-id="dbad6-119">These products provide a simple yet robust experience that streamlines the developer workflow.</span></span> <span data-ttu-id="dbad6-120">此外，Visual Studio Code 支持扩展 C\#和 web 开发，提供 intellisense 和快捷方式-对编辑器内的任务。</span><span class="sxs-lookup"><span data-stu-id="dbad6-120">Additionally, Visual Studio Code supports extensions for C\# and web development, providing intellisense and shortcut-tasks within the editor.</span></span>

[<span data-ttu-id="dbad6-121">下载.NET 核心 SDK</span><span class="sxs-lookup"><span data-stu-id="dbad6-121">Download the .NET Core SDK</span></span>](https://www.microsoft.com/net/download/core)

[<span data-ttu-id="dbad6-122">下载 Visual Studio 代码</span><span class="sxs-lookup"><span data-stu-id="dbad6-122">Download Visual Studio Code</span></span>](https://code.visualstudio.com/download)



## <a name="development-workflow-for-azure-hosted-aspnet-core-apps"></a><span data-ttu-id="dbad6-123">Azure 托管的 ASP.NET Core 应用的开发工作流</span><span class="sxs-lookup"><span data-stu-id="dbad6-123">Development workflow for Azure-hosted ASP.NET Core apps</span></span>

<span data-ttu-id="dbad6-124">从每个开发人员的计算机，编码使用其首选的语言和本地测试的应用开始应用程序开发生命周期。</span><span class="sxs-lookup"><span data-stu-id="dbad6-124">The application development lifecycle starts from each developer's machine, coding the app using their preferred language and testing it locally.</span></span> <span data-ttu-id="dbad6-125">开发人员可以选择其首选的源代码管理系统和持续集成 (CI) 和/或连续传送/部署 (CD) 使用的生成服务器可以配置或基于 Azure 的内置功能。</span><span class="sxs-lookup"><span data-stu-id="dbad6-125">Developers may choose their preferred source control system and can configure Continuous Integration (CI) and/or Continuous Delivery/Deployment (CD) using a build server or based on built-in Azure features.</span></span>

<span data-ttu-id="dbad6-126">若要开始开发使用 CI/CD 的 ASP.NET Core 应用程序，可以使用 Visual Studio Team Services 或您的组织拥有 Team Foundation Server (TFS)。</span><span class="sxs-lookup"><span data-stu-id="dbad6-126">To get started with developing an ASP.NET Core application using CI/CD, you can use Visual Studio Team Services or your organization's own Team Foundation Server (TFS).</span></span>

### <a name="initial-setup"></a><span data-ttu-id="dbad6-127">初始设置</span><span class="sxs-lookup"><span data-stu-id="dbad6-127">Initial Setup</span></span>

<span data-ttu-id="dbad6-128">若要创建您的应用程序的发行管道，你需要有源代码管理中的应用程序代码。</span><span class="sxs-lookup"><span data-stu-id="dbad6-128">To create a release pipeline for your app, you need to have your application code in source control.</span></span> <span data-ttu-id="dbad6-129">设置本地存储库并将其连接到团队项目的远程存储库。</span><span class="sxs-lookup"><span data-stu-id="dbad6-129">Set up a local repository and connect it to a remote repository in a team project.</span></span> <span data-ttu-id="dbad6-130">请按照这些说明操作：</span><span class="sxs-lookup"><span data-stu-id="dbad6-130">Follow these instructions:</span></span>

-   <span data-ttu-id="dbad6-131">[使用 Git 和 Visual Studio 共享你的代码](https://www.visualstudio.com/docs/git/share-your-code-in-git-vs)或</span><span class="sxs-lookup"><span data-stu-id="dbad6-131">[Share your code with Git and Visual Studio](https://www.visualstudio.com/docs/git/share-your-code-in-git-vs) or</span></span>

-   [<span data-ttu-id="dbad6-132">与 TFVC 和 Visual Studio 共享你的代码</span><span class="sxs-lookup"><span data-stu-id="dbad6-132">Share your code with TFVC and Visual Studio</span></span>](https://www.visualstudio.com/docs/tfvc/share-your-code-in-tfvc-vs)

<span data-ttu-id="dbad6-133">创建 Azure 应用程序服务，将在其中部署您的应用程序。</span><span class="sxs-lookup"><span data-stu-id="dbad6-133">Create an Azure App Service where you'll deploy your application.</span></span> <span data-ttu-id="dbad6-134">通过在 Azure 门户上转到应用程序服务边栏选项卡中创建 Web 应用。</span><span class="sxs-lookup"><span data-stu-id="dbad6-134">Create a Web App by going to the App Services blade on the Azure portal.</span></span> <span data-ttu-id="dbad6-135">单击 + 添加，选择 Web 应用程序模板、 单击创建和提供的名称和其他详细信息。</span><span class="sxs-lookup"><span data-stu-id="dbad6-135">Click +Add, select the Web App template, click Create, and provide a name and other details.</span></span> <span data-ttu-id="dbad6-136">Web 应用程序可从 {name}。.azurewebsites.net 处进行访问。</span><span class="sxs-lookup"><span data-stu-id="dbad6-136">The web app will be accessible from {name}.azurewebsites.net.</span></span>

![AzureWebApp](./media/image10-2.png)

<span data-ttu-id="dbad6-138">**图 10-2。**</span><span class="sxs-lookup"><span data-stu-id="dbad6-138">**Figure 10-2.**</span></span> <span data-ttu-id="dbad6-139">在 Azure 门户中创建新的 Azure App Service Web 应用。</span><span class="sxs-lookup"><span data-stu-id="dbad6-139">Creating a new Azure App Service Web App in the Azure Portal.</span></span>

<span data-ttu-id="dbad6-140">CI 生成过程将执行的自动的生成新代码时提交到项目的源控件存储库。</span><span class="sxs-lookup"><span data-stu-id="dbad6-140">Your CI build process will perform an automated build whenever new code is committed to the project's source control repository.</span></span> <span data-ttu-id="dbad6-141">这使你的代码将生成的即时反馈 （和，理想情况下，通过自动的测试），可能被部署。</span><span class="sxs-lookup"><span data-stu-id="dbad6-141">This gives you immediate feedback that the code builds (and, ideally, passes automated tests) and can potentially be deployed.</span></span> <span data-ttu-id="dbad6-142">此 CI 生成将生成 web 部署包项目并将其发布供使用 CD 过程。</span><span class="sxs-lookup"><span data-stu-id="dbad6-142">This CI build will produce a web deploy package artifact and publish it for consumption by your CD process.</span></span>

[<span data-ttu-id="dbad6-143">定义 CI 生成过程</span><span class="sxs-lookup"><span data-stu-id="dbad6-143">Define your CI build process</span></span>](https://www.visualstudio.com/docs/build/apps/aspnet/aspnetcore-to-azure#ci)

<span data-ttu-id="dbad6-144">请务必启用持续集成，以便系统才将在你的团队中有人在提交新代码时对生成进行排队。</span><span class="sxs-lookup"><span data-stu-id="dbad6-144">Be sure to enable continuous integration so the system will queue a build whenever someone on your team commits new code.</span></span> <span data-ttu-id="dbad6-145">测试生成并验证它是否生成 web 部署包作为其项目之一。</span><span class="sxs-lookup"><span data-stu-id="dbad6-145">Test the build and verify that it is producing a web deploy package as one of its artifacts.</span></span>

<span data-ttu-id="dbad6-146">如果生成成功，CD 过程将将 CI 生成的结果，部署到 Azure web 应用。</span><span class="sxs-lookup"><span data-stu-id="dbad6-146">When a build succeeds, your CD process will deploy the results of your CI build to your Azure web app.</span></span> <span data-ttu-id="dbad6-147">若要配置这种情况，你可以创建和配置*版本*，这会将它们部署到你的 Azure 应用程序服务。</span><span class="sxs-lookup"><span data-stu-id="dbad6-147">To configure this, you create and configure a *Release*, which will deploy to your Azure App Service.</span></span>

[<span data-ttu-id="dbad6-148">定义 CD 发布过程</span><span class="sxs-lookup"><span data-stu-id="dbad6-148">Define your CD release process</span></span>](https://www.visualstudio.com/docs/build/apps/aspnet/aspnetcore-to-azure#cd)

<span data-ttu-id="dbad6-149">CI/CD 管道配置后，只需对你的 web 应用进行更新并将它们提交到源代码管理，让他们部署。</span><span class="sxs-lookup"><span data-stu-id="dbad6-149">Once your CI/CD pipeline is configured, you can simply make updates to your web app and commit them to source control to have them deployed.</span></span>

### <a name="workflow-for-developing-azure-hosted-aspnet-core-applications"></a><span data-ttu-id="dbad6-150">有关开发 Azure 托管的 ASP.NET Core 应用程序的工作流</span><span class="sxs-lookup"><span data-stu-id="dbad6-150">Workflow for developing Azure-hosted ASP.NET Core applications</span></span>

<span data-ttu-id="dbad6-151">配置你的 Azure 帐户和你的 CI/CD 过程后，开发 Azure 托管的 ASP.NET Core 应用程序非常简单。</span><span class="sxs-lookup"><span data-stu-id="dbad6-151">Once you have configured your Azure account and your CI/CD process, developing Azure-hosted ASP.NET Core applications is simple.</span></span> <span data-ttu-id="dbad6-152">以下是你通常会生成一个图 10-3 中所示，在 Azure App Service 中为 Web 应用，托管的 ASP.NET Core 应用时的基本步骤。</span><span class="sxs-lookup"><span data-stu-id="dbad6-152">The following are the basic steps you usually take when building an ASP.NET Core app, hosted in Azure App Service as a Web App, as illustrated in Figure 10-3.</span></span>

![EndToEndDevDeployWorkflow](./media/image10-3.png)

<span data-ttu-id="dbad6-154">**图 10-3。**</span><span class="sxs-lookup"><span data-stu-id="dbad6-154">**Figure 10-3.**</span></span> <span data-ttu-id="dbad6-155">用于构建应用的 ASP.NET Core 和在 Azure 中承载它们的分步工作流</span><span class="sxs-lookup"><span data-stu-id="dbad6-155">Step-by-step workflow for building ASP.NET Core apps and hosting them in Azure</span></span>

#### <a name="step-1-local-dev-environment-inner-loop"></a><span data-ttu-id="dbad6-156">步骤 1。</span><span class="sxs-lookup"><span data-stu-id="dbad6-156">Step 1.</span></span> <span data-ttu-id="dbad6-157">本地开发环境内部循环</span><span class="sxs-lookup"><span data-stu-id="dbad6-157">Local Dev Environment Inner Loop</span></span>

<span data-ttu-id="dbad6-158">开发以部署到 Azure ASP.NET Core 应用程序是与否则开发你的应用程序没有什么不同。</span><span class="sxs-lookup"><span data-stu-id="dbad6-158">Developing your ASP.NET Core application for deployment to Azure is no different from developing your application otherwise.</span></span> <span data-ttu-id="dbad6-159">使用本地开发环境，您很熟悉，无论是 Visual Studio 2017 或 dotnet CLI 和 Visual Studio Code 或首选的编辑器。</span><span class="sxs-lookup"><span data-stu-id="dbad6-159">Use the local development environment you're comfortable with, whether that's Visual Studio 2017 or the dotnet CLI and Visual Studio Code or your preferred editor.</span></span> <span data-ttu-id="dbad6-160">您可以编写代码、 运行和调试所做的更改，运行自动的测试，并使本地提交到源代码管理，直到你准备好将更改推送到共享的源控件存储库。</span><span class="sxs-lookup"><span data-stu-id="dbad6-160">You can write code, run and debug your changes, run automated tests, and make local commits to source control until you're ready to push your changes to your shared source control repository.</span></span>

#### <a name="step-2-application-code-repository"></a><span data-ttu-id="dbad6-161">步骤 2。</span><span class="sxs-lookup"><span data-stu-id="dbad6-161">Step 2.</span></span> <span data-ttu-id="dbad6-162">应用程序代码存储库</span><span class="sxs-lookup"><span data-stu-id="dbad6-162">Application Code Repository</span></span>

<span data-ttu-id="dbad6-163">每当准备好与你的团队共享你的代码时，你应将所做的更改从本地源存储库推送到你的团队共享的源存储库。</span><span class="sxs-lookup"><span data-stu-id="dbad6-163">Whenever you're ready to share your code with your team, you should push your changes from your local source repository to your team's shared source repository.</span></span> <span data-ttu-id="dbad6-164">如果你一直在自定义的分支中，此步骤通常涉及将你的代码合并到一个共享的分支 (可能通过的方式[拉取请求](https://www.visualstudio.com/docs/git/pull-requests))。</span><span class="sxs-lookup"><span data-stu-id="dbad6-164">If you've been working in a custom branch, this step usually involves merging your code into a shared branch (perhaps by means of a [pull request](https://www.visualstudio.com/docs/git/pull-requests)).</span></span>

#### <a name="step-3-build-server-continuous-integration-build-test-package"></a><span data-ttu-id="dbad6-165">步骤 3。</span><span class="sxs-lookup"><span data-stu-id="dbad6-165">Step 3.</span></span> <span data-ttu-id="dbad6-166">生成服务器： 持续集成。</span><span class="sxs-lookup"><span data-stu-id="dbad6-166">Build Server: Continuous Integration.</span></span> <span data-ttu-id="dbad6-167">生成，测试包</span><span class="sxs-lookup"><span data-stu-id="dbad6-167">Build, Test, Package</span></span>

<span data-ttu-id="dbad6-168">对共享的应用程序代码存储库进行新的提交时，将在生成服务器上触发新的生成。</span><span class="sxs-lookup"><span data-stu-id="dbad6-168">A new build is triggered on the build server whenever a new commit is made to the shared application code repository.</span></span> <span data-ttu-id="dbad6-169">CI 过程的一部分，为此生成应完全编译应用程序并运行自动的测试，以确认所有内容按预期工作。</span><span class="sxs-lookup"><span data-stu-id="dbad6-169">As part of the CI process, this build should fully compile the application and run automated tests to confirm everything is working as expected.</span></span> <span data-ttu-id="dbad6-170">CI 过程的最终结果应准备好进行部署的 web 应用的打包的版本。</span><span class="sxs-lookup"><span data-stu-id="dbad6-170">The end result of the CI process should be a packaged version of the web app, ready for deployment.</span></span>

#### <a name="step-4-build-server-continuous-delivery"></a><span data-ttu-id="dbad6-171">步骤 4。</span><span class="sxs-lookup"><span data-stu-id="dbad6-171">Step 4.</span></span> <span data-ttu-id="dbad6-172">生成服务器： 持续交付</span><span class="sxs-lookup"><span data-stu-id="dbad6-172">Build Server: Continuous Delivery</span></span>

<span data-ttu-id="dbad6-173">一次成功的生成，CD 过程将选取生成的生成项目。</span><span class="sxs-lookup"><span data-stu-id="dbad6-173">Once a build as succeeded, the CD process will pick up the build artifacts produced.</span></span> <span data-ttu-id="dbad6-174">这将包括 web 部署包。</span><span class="sxs-lookup"><span data-stu-id="dbad6-174">This will include a web deploy package.</span></span> <span data-ttu-id="dbad6-175">生成服务器会将此包部署到 Azure App Service，将替换为新创建的一个现有的任何服务。</span><span class="sxs-lookup"><span data-stu-id="dbad6-175">The build server will deploy this package to Azure App Service, replacing any existing service with the newly created one.</span></span> <span data-ttu-id="dbad6-176">此步骤通常面向过渡环境，但某些应用程序直接部署到生产通过 CD 过程。</span><span class="sxs-lookup"><span data-stu-id="dbad6-176">Typically this step targets a staging environment, but some applications deploy directly to production through a CD process.</span></span>

#### <a name="step-5-azure-app-service-web-app"></a><span data-ttu-id="dbad6-177">步骤 5。</span><span class="sxs-lookup"><span data-stu-id="dbad6-177">Step 5.</span></span> <span data-ttu-id="dbad6-178">Azure App Service。</span><span class="sxs-lookup"><span data-stu-id="dbad6-178">Azure App Service.</span></span> <span data-ttu-id="dbad6-179">Web 应用。</span><span class="sxs-lookup"><span data-stu-id="dbad6-179">Web App.</span></span>

<span data-ttu-id="dbad6-180">部署后，ASP.NET Core 应用程序将在 Azure App Service Web 应用的上下文内运行。</span><span class="sxs-lookup"><span data-stu-id="dbad6-180">Once deployed, the ASP.NET Core application runs within the context of an Azure App Service Web App.</span></span> <span data-ttu-id="dbad6-181">此 Web 应用可以监视和进一步配置为使用 Azure 门户。</span><span class="sxs-lookup"><span data-stu-id="dbad6-181">This Web App can be monitored and further configured using the Azure Portal.</span></span>

#### <a name="step-6-production-monitoring-and-diagnostics"></a><span data-ttu-id="dbad6-182">步骤 6。</span><span class="sxs-lookup"><span data-stu-id="dbad6-182">Step 6.</span></span> <span data-ttu-id="dbad6-183">生产监视和诊断</span><span class="sxs-lookup"><span data-stu-id="dbad6-183">Production Monitoring and Diagnostics</span></span>

<span data-ttu-id="dbad6-184">在 Web 应用运行时，你可以监视应用程序的运行状况，并收集诊断和用户行为数据。</span><span class="sxs-lookup"><span data-stu-id="dbad6-184">While the Web App is running, you can monitor the health of the application and collect diagnostics and user behavior data.</span></span> <span data-ttu-id="dbad6-185">Application Insights 包含在 Visual Studio 中，并提供有关 ASP.NET 应用程序的自动检测。</span><span class="sxs-lookup"><span data-stu-id="dbad6-185">Application Insights is included in Visual Studio, and offers automatic instrumentation for ASP.NET apps.</span></span> <span data-ttu-id="dbad6-186">它可以为您提供使用情况、 异常、 请求、 性能和日志的信息。</span><span class="sxs-lookup"><span data-stu-id="dbad6-186">It can provide you with information on usage, exceptions, requests, performance, and logs.</span></span>

## <a name="references"></a><span data-ttu-id="dbad6-187">参考资料</span><span class="sxs-lookup"><span data-stu-id="dbad6-187">References</span></span>

<span data-ttu-id="dbad6-188">**生成和 ASP.NET Core 应用部署到 Azure**</span><span class="sxs-lookup"><span data-stu-id="dbad6-188">**Build and Deploy Your ASP.NET Core App to Azure**</span></span>  
<span data-ttu-id="dbad6-189"><https://www.visualstudio.com/docs/build/apps/aspnet/aspnetcore-to-azure></span><span class="sxs-lookup"><span data-stu-id="dbad6-189"><https://www.visualstudio.com/docs/build/apps/aspnet/aspnetcore-to-azure></span></span>


>[!div class="step-by-step"]
<span data-ttu-id="dbad6-190">[以前](test-asp-net-core-mvc-apps.md) [下一步] (azure-hosting-recommendations-for-asp-net-web-apps.md)</span><span class="sxs-lookup"><span data-stu-id="dbad6-190">[Previous] (test-asp-net-core-mvc-apps.md) [Next] (azure-hosting-recommendations-for-asp-net-web-apps.md)</span></span>
