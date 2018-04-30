---
title: Docker 应用程序的外部循环 DevOps 工作流中的步骤
description: 使用 Microsoft 平台和工具的容器化 Docker 应用程序的生命周期
ms.prod: .net
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 09/22/2017
ms.topic: article
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 7a85f42969a3bc1476367203415eb6898641e33a
ms.sourcegitcommit: 2e8acae16ae802f2d6d04e3ce0a6dbf04e476513
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2018
---
# <a name="steps-in-the-outer-loop-devops-workflow-for-a-docker-application"></a>Docker 应用程序的外部循环 DevOps 工作流中的步骤

图 5-1 显示构成 DevOps 外部循环工作流的步骤的端到端描述。

![](./media/image1.png)

使用 Microsoft tools Docker 应用程序的图 5-1: DevOps 外部循环工作流

现在，让我们检查每个步骤中更多详细信息。

## <a name="step-1-inner-loop-development-workflow"></a>步骤 1： 内部循环开发工作流

第 4 章中的详细阐述此步骤，但简单概述一下，下面是其中外部循环开始时，开发人员将推送到源控件管理系统 （如 Git) 的代码启动 CI 管道操作的时刻。

## <a name="step-2-source-code-control-integration-and-management-with-visual-studio-team-services-and-git"></a>步骤 2： 源代码管理集成和使用 Visual Studio Team Services 和 Git 管理

在此步骤中，你需要的版本控制系统，以收集来自不同的开发人员团队中的所有代码合并的版本。

即使源代码管理 (SCC) 和源代码管理可能看似秒性质周期的对大多数开发人员，在 DevOps 现实生活中创建 Docker 应用程序时，务必强调你必须提交与应用程序的 Docker 映像直接对全局 Docker 注册表 （如 Azure 容器注册表或 Docker Hub） 从开发人员的计算机。 相反，必须在全局生成或基于你的源代码存储库 （如 Git) 的 CI 管道仅在集成的源代码上创建发布和部署到生产环境的 Docker 映像。

他们自己的计算机中测试时，应仅由开发人员使用开发人员本身也由生成的本地映像。 这是非常关键能够 DevOps 管道 SCC 代码中激活的原因。

Visual Studio Team Services 和 Team Foundation Server 支持 Git 和 Team Foundation 版本控制。 你可以选择它们，并使用它以端到端的 Microsoft 体验。 但是，还可以管理外部存储库 （如 GitHub、 本地 Git 存储库，或子版本号） 中的代码和仍将能够连接到它并获取 DevOps CI 管道作为起始点的代码。

## <a name="step-3-build-ci-integrate-and-test-with-visual-studio-team-services-and-docker"></a>步骤 3： 生成、 CI 使用，请将集成，并测试使用 Visual Studio Team Services 和 Docker

CI 已成为一种标准现代软件测试和传递。 Docker 解决方案维护明显的开发和操作团队之间的问题。 Docker 映像的不可变性可确保内容具有开发、 测试 CI 使用，请通过和在生产中运行之间的可重复部署。 开发人员便携式计算机跨部署 docker 引擎并测试基础结构使容器可移植的环境。

此时，提交的正确代码中具有的版本控制系统后，你需要*生成服务*选取代码并运行全局生成和测试。

此步骤 （CI 使用，请生成，测试） 的内部工作流是关于你的生成服务器 (Visual Studio Team Services)，Docker 引擎和 Docker 注册表包含 （Git 等），你的代码存储库的 CI 管道构造。

你可以使用 Visual Studio Team Services 作为基础用于构建你的应用程序和设置 CI 管道，并且用于发布生成"项目"到"项目存储库，"下一步中说明。

对于部署，"最后一个项目"中使用 Docker 时要部署与你的应用程序或服务的 Docker 映像中嵌入它们。 这些映像都推送或发布到*Docker 注册表*（如你可以在 Azure 容器注册表中或一个公共如 Docker Hub 注册表，通常用于正式基映像的专用存储库）。

此处是一个基本概念： CI 管道都将启动的关闭通过 Git 等源代码管理存储库的提交。 提交将导致 Visual Studio Team Services 运行 Docker 容器中的生成作业，并在该作业成功完成，将 Docker 映像推送到 Docker 注册表中，在图 5-2 中所示。

![](./media/image2.png)

图 5-2： 所涉及的步骤在 CI 中

以下是使用 Docker 和 Visual Studio Team Services 的基本 CI 工作流步骤：

1.  开发人员将提交推送到 SCC 存储库 （Git/Visual Studio Team Services、 GitHub 等）。

2.  如果你使用 Visual Studio Team Services 或 Git，CI 是内置的中,，这意味着很像在 Visual Studio Team Services 选中复选框一样简单。 如果你使用的外部 （例如 GitHub)、 SCC *webhook*将通知的更新的 Visual Studio Team Services 或推送到 Git/GitHub。

3.  Visual Studio Team Services 中提取 SCC 存储库，包括 DockerFile 描述图像，以及应用程序和测试代码。

4.  Visual Studio Team Services 生成的 Docker 映像，并使用生成号对其进行标记。

5.  Visual Studio Team Services 实例化中预配 Docker 主机的 Docker 容器，并且运行的相应测试。

6.  如果测试成功，映像第一次重新标记为有意义的名称，以便你知道它是"blessed 的 build"(如"/ 1.0.0"或任何其他标签)，，然后推送到你的 Docker 注册表 （Docker Hub、 Azure 容器注册表、 DTR 等）

### <a name="implementing-the-ci-pipeline-with-visual-studio-team-services-and-the-docker-extension-for-visual-studio-team-services"></a>对 Visual Studio Team Services 实施 CI 管道使用 Visual Studio Team Services 和 Docker 扩展

[Visual Studio Team Services Docker 扩展](https://aka.ms/vstsdockerextension)向 CI 管道与其可以生成 Docker 图像、 Docker 图像推送到经过身份验证的 Docker 注册表、 运行 Docker 映像，或运行提供的其他操作添加任务Docker CLI。 它还添加了可用于生成、 推送和运行 multicontainer Docker 应用程序，或运行提供的 Docker Compose CLI 其他操作，在图 5-3 中所示的 Docker Compose 任务。

![](./media/image3.png)

图 5-3： 在 Visual Studio Team Services Docker CI 管道

Docker 扩展可将服务终结点，用于 Docker 主机和容器或映像注册表。 任务默认为使用本地 Docker 主机，如果可用 （这当前需要自定义 Visual Studio Team Services 代理）;否则，它们需要你提供 Docker 主机的连接。 依赖于向 Docker 注册表，如推送一个映像，正在进行身份验证的操作要求你在注册表连接提供的 Docker。

Visual Studio Team Services Docker 扩展 Visual Studio Team Services 帐户中安装以下组件：

-   用于连接到 Docker 注册表的服务终结点

-   用于连接到 Docker 容器主机的服务终结点

-   Docker 执行以下任务：

-   生成的映像

-   将图像或存储库推送到注册表

-   在容器中运行映像

-   运行 Docker 命令

-   Docker Compose 任务以运行 Docker Compose 命令

Visual Studio Team Services 这些任务中，生成 Linux Docker 主机/虚拟机在 Azure 中设置和你首选的 Docker 注册表 （Azure 容器注册表、 Docker Hub、 私有 Docker DTR 或任何其他 Docker 注册表） 你可以将组合在 Docker CI 管道非常一致的方式。

***要求：***

-   Visual Studio Team Services，或对于本地安装，Team Foundation Server 2015 Update 3 或更高版本。

-   一种 Visual Studio Team Services 代理，它具有的 Docker 二进制文件。

创建以下方法之一的简单办法是使用 Docker 运行基于 Visual Studio Team Services 代理 Docker 映像的容器。

**详细信息** 用于读取有关将 Visual Studio Team Services Docker CI 的详细信息管道，若要查看演练，请访问以下站点：

Docker 容器形式运行 Visual Studio Team Services 代理： [ https://hub.docker.com/r/\ microsoft/vsts 代理 /](https://hub.docker.com/r/microsoft/vsts-agent/)

VSTS Docker 扩展： <https://aka.ms/vstsdockerextension>

构建利用 Visual Studio Team Services 的.NET 核心 Linux Docker 映像： <https://blogs.msdn.microsoft.com/stevelasker/2016/06/13/building-net-core-linux-docker-images-with-visual-studio-team-services/>

构建 Docker 支持与基于 Linux 的 Visual Studio 团队服务生成计算机： <http://donovanbrown.com/post/2016/06/03/Building-a-Linux-Based-Visual-Studio-Team-Service-Build-Machine-with-Docker-Support>

### <a name="integrate-test-and-validate-multicontainer-docker-applications"></a>集成、 测试和验证 multicontainer Docker 应用程序

通常情况下，大多数 Docker 应用程序由多个容器，而不是单个容器组成。 一个很好示例是一个面向微服务的应用程序，您将对其具有每个微服务构成的一个容器。 但是，即使没有严格遵循了微服务方法模式，则很可能你 Docker 的应用程序将组成多个容器或服务。

因此，在生成 CI 管道中的应用程序容器之后, 你还需要部署、 集成和测试应用程序作为一个整体与其所有容器集成 Docker 主机中或甚至到你的容器都对该测试群集分发。

如果你使用的一台主机，则可以使用 Docker 命令，例如 docker-撰写可以生成和部署相关的容器，以测试和验证中的单个 VM 的 Docker 环境。 但是，如果你正在使用如 DC/OS、 Kubernetes，或 Docker Swarm 的 orchestrator 群集，则需要部署你通过不同的机制或 orchestrator，具体取决于你所选群集/计划程序的容器。

以下是几种类型的测试，你可以针对 Docker 容器运行：

-   Docker 容器的单元测试

-   测试又彼此相关的应用程序或微服务的组

-   在生产环境和"加那利"版本中测试

重要的一点是，当运行时集成和功能测试，你必须运行从容器外部这些测试。 测试必须不定义和在部署时，容器内运行，因为容器基于应为那些你将部署到生产环境完全一样的静态图像。

测试更高级的方案，如测试多个群集 （群集、 过渡群集和生产群集测试） 时是非常可行选项是将映像发布到测试各种群集中的注册表。

### <a name="push-the-custom-application-docker-image-into-your-global-docker-registry"></a>将自定义应用程序的 Docker 映像推送到全局 Docker 注册表

测试和验证的 Docker 映像后，你将想要标记并将其发布到 Docker 注册表。 Docker 注册表在 Docker 应用程序生命周期中是一条关键，因为它是你在其中存储你自定义的测试 （也称为"blessed 映像"） 将其部署到 QA 和生产环境的中央位置。

与如何在你的 SCC 存储库 （Git 等） 中存储的应用程序代码是你"资料来源"类似，Docker 注册表是你"资料来源"二进制应用程序或 bits 要部署到 QA 或生产环境。

通常情况下，你可能想要自定义映像的专用存储库在专用的存储库 Azure 容器注册表中或 Docker 受信任注册表，如本地注册表或公共云注册表项 （如限制访问权限Docker Hub)，尽管在此最后一个的情况下，如果你的代码不是开源，必须先信任供应商的安全。 无论哪种方式，依据你执行此操作的方法是十分相似并且最终基于 docker 推送命令，同时在图 5-4 中所示。

![](./media/image4.png)

图 5-4： 将自定义映像发布到 Docker 注册表

不存在的 Docker 注册表，如 Azure 容器注册表、 Amazon Web Services 容器注册表、 Google 容器注册表、 Quay 注册表和等等的云供应商的多个产品。

使用 Visual Studio Team Services Docker 扩展，你可以在图 5-5 中所示推送服务映像由 docker-compose.yml 文件，使用多个标记，到经过身份验证的 Docker 注册表 （如 Azure 容器注册表中），定义一组。

![](./media/image5.png)

图 5-5： 使用 Visual Studio Team Services 到发布到 Docker 注册表的自定义映像

**详细信息** 以便阅读更多有关 Visual Studio Team Services Docker 扩展，请转到<https://aka.ms/vstsdockerextension>。 若要了解有关 Azure 容器注册表中的详细信息，请转到<https://aka.ms/azurecontainerregistry>。

## <a name="step-4-cd-deploy"></a>步骤 4: CD，部署

Docker 映像的不可变性可确保具有什么已开发、 测试通过 CI，并在生产中运行的可重复部署。 （专用或公用） 你 Docker 注册表中发布的应用程序 Docker 映像后，你可以将它们部署到可能具有多个环境 (生产、 QA、 过渡，等) 从使用 Visual Studio Team Services CD 管道管道任务或 Visual Studio Team Services Release Management。

但是，此时它依赖于要部署的 Docker 应用程序类型。 部署简单应用程序 （从组合和部署的角度来看） 如整体应用程序包含几个容器或服务及已部署到几个服务器或 Vm 是非常不同的部署更复杂的应用程序，如面向微服务的应用程序具有超大规模功能。 下列部分中解释了这两个方案。

### <a name="deploying-composed-docker-applications-to-multiple-docker-environments"></a>部署组成 Docker 应用程序到多个 Docker 环境

让我们应当首先查看不太复杂方案： 将部署到单个环境或多个环境中的简单 Docker 主机 （Vm 或服务器） (QA、 过渡和生产)。 在此方案中，内部 CD 管道可以使用 docker-撰写 （从你的 Visual Studio Team Services 部署任务） 部署的 Docker 应用程序使用其相关的一组的容器或服务，如图 5-6 中所示。

![](./media/image6.png)

图 5-6： 将应用程序容器部署到简单 Docker 主机环境注册表

图 5-7 突出显示了如何连接生成 CI 到 QA/测试环境，通过 Visual Studio Team Services 通过单击添加任务对话框中的 Docker Compose。 但是，在部署到过渡环境或生产环境，你通常将处理多个环境版本管理功能 (如 QA、 过渡和生产)。 如果你正在将部署到单个 Docker 主机，它使用 Visual Studio Team Services"Docker Compose"任务 (这调用 docker-撰写实质上的命令)。 如果你正在将部署到 Azure 容器服务，它使用 Docker 部署任务，如上一节中所述。

![](./media/image7.png)

图 5-7： 在 Visual Studio Team Services 管道中添加 Docker Compose 任务

当你在 Visual Studio Team Services 中创建发布时，它将使用输入项目的一组。 这些重载可以跨多个环境的整个生存期内版本不可变。 在引入容器时，输入的项目标识部署的注册表中的映像。 具体取决于这些标识过程，它们不保证都保持不变，则整个版本，最明显的情况下，正在从 docker-compose 文件引用"myimage:latest"时的持续时间。

用于 Visual Studio Team Services 的 Docker 扩展使您生成包含特定的注册表的映像的生成项目的功能摘要，可保证能唯一标识相同的二进制映像。 这些是你确实要用作输入的发行版。

### <a name="managing-releases-to-docker-environments-by-using-visual-studio-team-services-release-management"></a>使用 Visual Studio Team Services Release Management 管理发布到 Docker 环境

通过 Visual Studio Team Services 扩展中，你可以生成新映像、 将其发布到 Docker 注册表、 运行 Linux 或 Windows 主机上并使用如 docker 命令的撰写将多个容器部署为整个应用程序，通过该视觉对象Studio 团队服务版本管理功能，适用于多个环境，如图 5-8 所示。

![](./media/image8.png)

图 5-8： 配置 Visual Studio Team Services Docker Compose 任务从 Visual Studio Team Services Release Management

但是，请记住，显示在图 5-6 中和实现图 5-8 的方案是相当基本的 （它部署到简单 Docker 主机和虚拟机，并且会有单个容器或每个图像的实例），可能仅应该用于开发或测试 scenarios。 在大多数企业生产方案中，你将想要高可用性 (HA)，并且轻松管理负载平衡跨多个节点、 服务器和虚拟机，以及"智能故障转移"因此，如果服务器或节点的可伸缩性失败，其服务和容器将移到另一个主机服务器或 VM。 在这种情况下，你需要更高级的技术，如容器群集、 orchestrators 和计划程序。 因此，将部署到这些群集的方法是精确地通过在下一部分中所述的高级方案。

### <a name="deploying-complex-docker-applications-to-docker-clusters-dcos-kubernetes-and-docker-swarm"></a>部署到 Docker 群集 （DC/OS、 Kubernetes，和 Docker Swarm） 的复杂 Docker 应用程序

性质的分布式应用程序需要，还将分散的计算资源。 若要进行生产缩放功能，你需要具有群集提供高度可缩放性的功能和 HA 基于共用资源。

你无法容器手动部署到这些群集从 Docker Swarm 之类的 CLI 工具 (如使用[docker 服务创建](https://docs.docker.com/engine/swarm/swarm-tutorial/deploy-service/)) 或 web UI 如[Mesosphere Marathon](https://mesosphere.github.io/marathon/docs/marathon-ui.html)为 DC/OS 群集，但你应仅用于测试 punctual 部署或管理目的，如向外缩放或监视的目的，请保留的。

从 CD 的角度来看，Visual Studio Team Services 具体而言，你可以运行和专门发出的部署任务从你的 Visual Studio Team Services Release Management 环境将部署到分布式群集，在你容器化应用程序容器服务，如图 5-9 中所示。

![](./media/image9.png)

图 5-9： 部署到容器服务的分布式应用程序

最初，在部署到特定的群集或 orchestrators 时，你会传统上使用特定的部署脚本和每个每个 orchestrator （即，Mesosphere DC/OS 或 Kubernetes 具有不同的部署机制比 Docker 和 Docker 的机制Swarm) 而不是更简单且易于使用 docker-撰写基于 docker-compose.yml 定义文件的工具。 但是，Microsoft Visual Studio Team Services Docker 部署任务，如图 5-10 示感谢你现在还可以向部署 DC/OS 只需使用你熟悉 docker-compose.yml 文件，因为 Microsoft 为您执行该"翻译"(从你docker-compose.yml 文件为所需的 DC/OS 其他格式）。

![](./media/image10.png)

图 5-10: Docker 部署任务添加到你的环境 RM

图 5-11 演示如何编辑 Docker 部署任务和指定目标类型 （Azure 容器服务 DC/操作系统，在此情况下）、 Docker Compose 文件和 Docker 注册表连接 （如 Azure 容器注册表或 Docker Hub）。 这是该任务将在其中检索准备就绪，可以使用自定义 Docker 映像若要部署为 DC/OS 群集中的容器。

![](./media/image11.png)

图 5-11: Docker 部署任务定义部署 Azure 容器服务 DC/OS 到

**详细信息** 以便阅读更多有关使用 Visual Studio Team Services 和 Docker CD 管道，请访问以下站点：

Docker 和 Azure 容器服务的 visual Studio Team Services 扩展： [ https://aka.ms/\ vstsdockerextension](https://aka.ms/vstsdockerextension)

Azure 容器服务： <https://aka.ms/azurecontainerservice>

Mesosphere DC/OS: <https://mesosphere.com/product/>

## <a name="step-5-run-and-manage"></a>步骤 5： 运行和管理

因为运行和管理应用程序在企业生产级别是主要使用者中和自身，以及由于的操作类型，而在该级别 （IT 运营） 以及此区域的大范围的人员，我们具有专门用于整个下一步解释它的章节。

## <a name="step-6-monitor-and-diagnose"></a>步骤 6： 监视和诊断

本主题还介绍了在下一章中的 IT 运营执行生产系统; 中的任务的一部分但是，务必突出显示，以便不断改进应用程序在此步骤中获得的见解必须源回开发团队。 从该角度来看，它也是的一部分 DevOps，尽管通常执行的任务和操作 IT。

仅当时监视和诊断中的 DevOps 领域的 100%被监视的进程和由开发团队针对测试或 beta 环境执行的分析。 通过执行负载测试或只需通过监视 beta 或 QA 环境，beta 测试人员要新版本，则是完成此操作。

>[!div class="step-by-step"]
[以前](index.md) [下一步] (.../run-manage-monitor-docker-environments/index.md)
