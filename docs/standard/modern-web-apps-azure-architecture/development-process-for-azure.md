---
title: "Azure 的开发过程"
description: "设计使用 ASP.NET Core 和 Azure 的现代 Web 应用程序 |Azure 的开发过程"
author: ardalis
ms.author: wiwagn
ms.date: 10/08/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 21826e2c90d234d873cc06bfae3bd22ce89a62d2
ms.sourcegitcommit: 655fd4f78741967f80c409cef98347fdcf77857d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/28/2018
---
# <a name="development-process-for-azure"></a>Azure 的开发过程

> _"利用云，个人及小型企业可以对齐其指和立即设置企业级的服务。"_  
> _-Roy Stephan_

 ## <a name="vision"></a>Vision

> *开发设计良好的 ASP.NET 核心应用程序您喜欢使用 Visual Studio 或 dotnet CLI 和 Visual Studio Code 或首选编辑器的方法。*

## <a name="development-environment-for-aspnet-core-apps"></a>对于 ASP.NET Core 应用程序的开发环境

### <a name="development-tools-choices-ide-or-editor"></a>开发工具的选择： IDE 或编辑器

是否需要完整且功能强大的 IDE 或轻量，并灵活编辑器，则 Microsoft 将具有你开发 ASP.NET Core 应用程序时涉及。

**Visual Studio 2017.** 如果你使用*Visual Studio 2017*你可以生成 ASP.NET Core 应用程序，只要你有*.NET 核心跨平台开发*安装的工作负荷。 图 10-1 Visual Studio 2017 设置对话框中显示的所需的工作负荷。

![](./media/image10-1.png)

**图 10-1。** 在 Visual Studio 2017 中安装.NET 核心工作负荷。

[下载 Visual Studio 2017](https://aka.ms/vsdownload?utm_source=mscom&utm_campaign=msdocs)

**Visual Studio Code 和 dotnet CLI** （适用于 Mac、 Linux 和 Windows 的跨平台工具）。 如果需要支持任何开发语言的轻量和跨平台编辑器，可以使用 Microsoft Visual Studio 代码和 dotnet CLI。 这些产品提供简单而稳定可靠的体验，简化了开发人员工作流。 此外，Visual Studio Code 支持扩展 C\#和 web 开发，提供 intellisense 和快捷方式-对编辑器内的任务。

[下载.NET 核心 SDK](https://www.microsoft.com/net/download/core)

[下载 Visual Studio 代码](https://code.visualstudio.com/download)



## <a name="development-workflow-for-azure-hosted-aspnet-core-apps"></a>Azure 托管的 ASP.NET Core 应用的开发工作流

从每个开发人员的计算机，编码使用其首选的语言和本地测试的应用开始应用程序开发生命周期。 开发人员可以选择其首选的源代码管理系统和持续集成 (CI) 和/或连续传送/部署 (CD) 使用的生成服务器可以配置或基于 Azure 的内置功能。

若要开始开发使用 CI/CD 的 ASP.NET Core 应用程序，可以使用 Visual Studio Team Services 或您的组织拥有 Team Foundation Server (TFS)。

### <a name="initial-setup"></a>初始设置

若要创建您的应用程序的发行管道，你需要有源代码管理中的应用程序代码。 设置本地存储库并将其连接到团队项目的远程存储库。 请按照这些说明操作：

-   [使用 Git 和 Visual Studio 共享你的代码](https://docs.microsoft.com/vsts/git/share-your-code-in-git-vs)或

-   [与 TFVC 和 Visual Studio 共享你的代码](https://docs.microsoft.com/vsts/tfvc/share-your-code-in-tfvc-vs)

创建 Azure 应用程序服务，将在其中部署您的应用程序。 通过在 Azure 门户上转到应用程序服务边栏选项卡中创建 Web 应用。 单击 + 添加，选择 Web 应用程序模板、 单击创建和提供的名称和其他详细信息。 Web 应用程序可从 {name}.azurewebsites.net 处进行访问。

![AzureWebApp](./media/image10-2.png)

**图 10-2。** 在 Azure 门户中创建新的 Azure App Service Web 应用。

CI 生成过程将执行的自动的生成新代码时提交到项目的源控件存储库。 这使你的代码将生成的即时反馈 （和，理想情况下，通过自动的测试），可能被部署。 此 CI 生成将生成 web 部署包项目并将其发布供使用 CD 过程。

[定义 CI 生成过程](https://docs.microsoft.com/vsts/build-release/apps/aspnet/build-aspnet-core#ci)

请务必启用持续集成，以便系统才将在你的团队中有人在提交新代码时对生成进行排队。 测试生成并验证它是否生成 web 部署包作为其项目之一。

如果生成成功，CD 过程将将 CI 生成的结果，部署到 Azure web 应用。 若要配置这种情况，你可以创建和配置*版本*，这会将它们部署到你的 Azure 应用程序服务。

[定义 CD 发布过程](https://docs.microsoft.com/vsts/build-release/apps/aspnet/build-aspnet-core#cd)

CI/CD 管道配置后，只需对你的 web 应用进行更新并将它们提交到源代码管理，让他们部署。

### <a name="workflow-for-developing-azure-hosted-aspnet-core-applications"></a>有关开发 Azure 托管的 ASP.NET Core 应用程序的工作流

配置你的 Azure 帐户和你的 CI/CD 过程后，开发 Azure 托管的 ASP.NET Core 应用程序非常简单。 以下是你通常会生成一个图 10-3 中所示，在 Azure App Service 中为 Web 应用，托管的 ASP.NET Core 应用时的基本步骤。

![EndToEndDevDeployWorkflow](./media/image10-3.png)

**图 10-3。** 用于构建应用的 ASP.NET Core 和在 Azure 中承载它们的分步工作流

#### <a name="step-1-local-dev-environment-inner-loop"></a>步骤 1。 本地开发环境内部循环

开发以部署到 Azure ASP.NET Core 应用程序是与否则开发你的应用程序没有什么不同。 使用本地开发环境，您很熟悉，无论是 Visual Studio 2017 或 dotnet CLI 和 Visual Studio Code 或首选的编辑器。 您可以编写代码、 运行和调试所做的更改，运行自动的测试，并使本地提交到源代码管理，直到你准备好将更改推送到共享的源控件存储库。

#### <a name="step-2-application-code-repository"></a>步骤 2。 应用程序代码存储库

每当准备好与你的团队共享你的代码时，你应将所做的更改从本地源存储库推送到你的团队共享的源存储库。 如果你一直在自定义的分支中，此步骤通常涉及将你的代码合并到一个共享的分支 (可能通过的方式[拉取请求](https://docs.microsoft.com/vsts/git/pull-requests))。

#### <a name="step-3-build-server-continuous-integration-build-test-package"></a>步骤 3。 生成服务器： 持续集成。 生成，测试包

对共享的应用程序代码存储库进行新的提交时，将在生成服务器上触发新的生成。 CI 过程的一部分，为此生成应完全编译应用程序并运行自动的测试，以确认所有内容按预期工作。 CI 过程的最终结果应准备好进行部署的 web 应用的打包的版本。

#### <a name="step-4-build-server-continuous-delivery"></a>步骤 4。 生成服务器： 持续交付

一次成功的生成，CD 过程将选取生成的生成项目。 这将包括 web 部署包。 生成服务器会将此包部署到 Azure App Service，将替换为新创建的一个现有的任何服务。 此步骤通常面向过渡环境，但某些应用程序直接部署到生产通过 CD 过程。

#### <a name="step-5-azure-app-service-web-app"></a>步骤 5。 Azure App Service。 Web 应用。

部署后，ASP.NET Core 应用程序将在 Azure App Service Web 应用的上下文内运行。 此 Web 应用可以监视和进一步配置为使用 Azure 门户。

#### <a name="step-6-production-monitoring-and-diagnostics"></a>步骤 6。 生产监视和诊断

在 Web 应用运行时，你可以监视应用程序的运行状况，并收集诊断和用户行为数据。 Application Insights 包含在 Visual Studio 中，并提供有关 ASP.NET 应用程序的自动检测。 它可以为您提供使用情况、 异常、 请求、 性能和日志的信息。

## <a name="references"></a>参考资料

**生成和 ASP.NET Core 应用部署到 Azure**  
<https://docs.microsoft.com/vsts/build-release/apps/aspnet/build-aspnet-core>


>[!div class="step-by-step"]
[Previous] (test-asp-net-core-mvc-apps.md) [Next] (azure-hosting-recommendations-for-asp-net-web-apps.md)
