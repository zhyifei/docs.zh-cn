---
title: "演练和技术获取启动的概述"
description: "更新现有的.NET 应用程序与 Azure 云和 Windows 容器 |演练和技术获取启动的概述"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/26/2017
ms.openlocfilehash: e78dd4a324ca9fc973f1aa0d8e6a9abe1341876c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="walkthroughs-and-technical-get-started-overview"></a>演练和技术获取启动的概述 

若要限制此图书的大小，我们进行了其他技术文档和完整的演练的 GitHub 存储库中可用。 此第章所述的演练联机系列介绍基于 Windows 容器和部署到 Azure 的多个环境的分步设置。

以下各节介绍了每个演练是有关及其目标，其高级愿景的并提供示意图所涉及的任务。 你可以获取本身的演练中*eShopModernizing*在应用程序 GitHub 存储库 wiki [https://github.com/dotnet-architecture/eShopModernizing/wiki](https://github.com/dotnet-architecture/eShopModernizing/wiki)。

# <a name="technical-walkthrough-list"></a>技术演练列表

以下入门演练提供了示例应用，你可以提升和移动通过使用容器，并且通过在 Azure 中使用多个部署选项然后移动的一致和全面技术指南。

下面的演练的每个使用新示例 eShopLegacy 和 eShopModernizing 应用程序，它们可在 GitHub 上[https://github.com/dotnet-architecture/eShopModernizing](https://github.com/dotnet-architecture/eShopModernizing)。

-   **电子商店旧应用的教程**

-   **化你现有的.NET 应用程序，与 Windows 容器**

-   **将 Windows 容器基于应用程序部署到 Azure Vm**

-   **将您的 Windows 容器基于应用程序部署到 Azure 容器服务中的 Kubernetes**

-   **将您的 Windows 容器基于应用程序部署到 Azure Service Fabric**

## <a name="walkthrough-1-tour-of-eshop-legacy-apps"></a>电子商店旧应用程序的演练 1： 教程

### <a name="technical-walkthrough-availability"></a>技术演练可用性

完整技术的演练会出现在 eShopModernizing GitHub 存储库 wiki:

[https://github.com/dotnet-architecture/eShopModernizing/wiki/01.-Tour-on-eShopModernizing-apps-implementation-code](https://github.com/dotnet-architecture/eShopModernizing/wiki/01.-Tour-on-eShopModernizing-apps-implementation-code)

### <a name="overview"></a>概述

在本演练中，你可以浏览初始实施中的两个示例旧版应用程序。 这两个示例应用具有单一的体系结构，并使用传统的 ASP.NET 创建的。 一个应用程序基于 ASP.NET 4.x MVC;第二个应用程序基于 ASP.NET 4.x Web 窗体。 这两个应用程序都位于[eShopModernizing GitHub 存储库](https://github.com/dotnet-architecture/eShopModernizing)。

你可以化这两个示例应用，方式类似于化经典[Windows Communication Foundation](https://docs.microsoft.com/dotnet/framework/wcf/whats-wcf) (WCF) 应用程序将使用作为桌面应用程序。 有关示例，请参阅[eShopModernizingWCFWinForms](https://github.com/dotnet-architecture/eShopModernizingWCFWinForms)。

### <a name="goals"></a>目标

本演练的主要目的只是以熟悉如何利用这些应用，并使用其代码和配置。 你可以配置的应用，以便它们生成和使用模拟数据，而无需使用 SQL 数据库，以进行测试。 此可选配置基于依赖关系注入分离的方式。

### <a name="scenario"></a>方案

图 5-1 显示简单的方案中的原始的旧版应用程序。

> ![简单的体系结构方案中的原始的旧版应用程序](./media/image5-1.png)
>
> **图 5-1。** 简单的体系结构方案中的原始的旧版应用程序

从业务域角度来看，这两个应用程序管理功能提供相同的目录。 电子商店企业团队的成员将使用应用来查看和编辑产品目录。 图 5-2 显示初始应用程序屏幕快照。

![ASP.NET MVC 和 ASP.NET Web 窗体应用程序 （现有/旧技术）](./media/image5-2.png)

> **图 5-2。** ASP.NET MVC 和 ASP.NET Web 窗体应用程序 （现有/旧技术）

这些是用于浏览和修改目录条目的 web 应用程序。 实际上，这两个应用提供相同的业务/功能的功能，我们只是为了进行比较。 你可以看到用于通过使用 ASP.NET MVC 和 ASP.NET Web 窗体框架的应用的类似现代化进程。

依赖项在 ASP.NET 4.x 或更早版本 （不管是针对 MVC 或 Web 窗体） 意味着除非通过使用 ASP.NET 核心 MVC 完全重新编写的代码，这些应用程序不会运行在.NET Core 上。 此示例演示的点，如果你不想重新设计，或重写代码，你可以化现有应用程序，并继续使用相同的.NET 技术和相同的代码。 你可以看到类似这样在容器中，而无需对旧代码的任何更改的应用程序的运行方式。

### <a name="benefits"></a>优点

本演练的好处很简单： 只需熟悉的代码和应用程序的配置，基于依赖关系注入。 然后，当你化并在将来部署到多个环境，您可以使用此方法尝试。

### <a name="next-steps"></a>后续步骤

在 GitHub wiki 上浏览此更深入的内容：

[https://github.com/dotnet-architecture/eShopModernizing/wiki/01.-Tour-on-eShopModernizing-apps-implementation-code](https://github.com/dotnet-architecture/eShopModernizing/wiki/01.-Tour-on-eShopModernizing-apps-implementation-code)

## <a name="walkthrough-2-containerize-your-existing-net-applications-with-windows-containers"></a>演练 2： 化你现有的.NET 应用程序，与 Windows 容器

### <a name="technical-walkthrough-availability"></a>技术演练可用性

完整技术的演练会出现在 eShopModernizing GitHub 存储库 wiki:

[https://github.com/dotnet-architecture/eShopModernizing/wiki/02.-How-to-containerized-the-.NET-Framework-web-apps-with-Windows-Containers-and-Docker](https://https://github.com/dotnet-architecture/eShopModernizing/wiki/02.-How-to-containerized-the-.NET-Framework-web-apps-with-Windows-Containers-and-DockerTBD)

### <a name="overview"></a>概述

使用 Windows 容器来提高部署的现有.NET 应用程序，如基于 MVC、 Web 窗体或 WCF，向生产、 开发和测试环境。

### <a name="goals"></a>目标

此演练的目的是显示 containerizing 现有.NET Framework 应用程序的几个选项。 你可以：

-   通过使用化你的应用程序[Visual Studio 2017 Tools for Docker](https://docs.microsoft.com/dotnet/core/docker/visual-studio-tools-for-docker) （Visual Studio 2017 年 1 或更高版本）。

-   通过手动添加化你的应用程序[Dockerfile](https://docs.docker.com/engine/reference/builder/)，，然后使用[Docker CLI](https://docs.docker.com/engine/reference/commandline/cli/)。

-   通过使用化你的应用程序[Img2Docker](https://github.com/docker/communitytools-image2docker-win)工具 （从 Docker 的开源工具）。

本演练主要针对 Visual Studio 2017 Tools for Docker 方法，但其他两种方法不符合使用 Dockerfile 非常相似。

### <a name="scenario"></a>方案

图 5-3 显示为容器化电子商店旧版应用程序方案。

> ![在开发环境中的容器化应用程序的简化的体系结构示意图](./media/image5-3.png)
>
> **图 5-3。** 在开发环境中的容器化应用程序的简化的体系结构示意图

### <a name="benefits"></a>优点

有在容器中运行你的整体应用程序的优点。 首先，你创建应用程序映像。 从那一刻开始，每个部署在相同环境中运行。 每个容器使用相同的操作系统版本、 具有相同版本的依赖项安装、 使用相同的.NET framework 版本，并且使用相同的过程生成。 基本上，你通过使用的 Docker 映像控制你的应用程序的依赖关系。 部署容器时，与应用程序传送依赖关系。

另一个好处是开发人员可以由 Windows 容器提供一致的环境中运行应用程序。 可以立即发现仅显示某些版本的问题，而不是在过渡或生产环境中提供。 在容器中运行应用程序，开发团队的成员使用的开发环境中的差异将重要小于。

容器化应用程序还具有更简单的横向扩展曲线。 容器化应用程序，可以有多个应用程序和服务实例 （基于容器） 中的 VM 或比较每个计算机的常规应用程序部署到的物理计算机。 这将转换为较高的密度和更少所需资源，尤其是当你使用 orchestrators Kubernetes 或 Service Fabric 等。

容器化，在理想情况下，不需要的应用程序代码进行任何更改 (C\#)。 在大多数情况下，你只需 Docker 部署元数据文件 （Dockerfile 和 Docker Compose 文件）。

### <a name="next-steps"></a>后续步骤

浏览 GitHub wiki 上的此内容更深入： [https://https://github.com/dotnet-architecture/eShopModernizing/wiki/02.-How-to-containerized-the-.NET-Framework-web-apps-with-Windows-Containers-and-Docker](https://https://github.com/dotnet-architecture/eShopModernizing/wiki/02.-How-to-containerized-the-.NET-Framework-web-apps-with-Windows-Containers-and-Docker)

## <a name="walkthrough-3-deploy-your-windows-containers-based-app-to-azure-vms"></a>演练 3： 将 Windows 容器基于应用程序部署到 Azure Vm

### <a name="technical-walkthrough-availability"></a>技术演练可用性

完整技术的演练会出现在 eShopModernizing GitHub 存储库 wiki:

[https://github.com/dotnet-architecture/eShopModernizing/wiki/03.-How-to-deploy-your-Windows-Containers-based-app-into-Azure-VMs-(Including-CI-CD)](https://github.com/dotnet-architecture/eShopModernizing/wiki/03.-How-to-deploy-your-Windows-Containers-based-app-into-Azure-VMs-(Including-CI-CD))

### <a name="overview"></a>概述

将部署到 Azure 中的 Windows Server 2016 VM 上的 Docker 主机，可以快速设置开发/测试/暂存环境。 它还会为你提供测试人员或业务用户，以验证应用程序的一个常见的位置。 Vm 还可以是有效的 IaaS 生产环境。

### <a name="goals"></a>目标

此演练的目的是显示到基于 Windows Server 2016 或更高版本的 Azure Vm 中部署 Windows 容器时，你有多个替代项。

### <a name="scenarios"></a>方案

在本演练涵盖多个方案。

#### <a name="scenario-a-deploy-to-an-azure-vm-from-a-dev-pc-through-docker-engine-connection"></a>方案 a： 部署到 Azure VM 从开发人员 PC 通过 Docker 引擎连接

![从开发人员 PC 通过 Docker 引擎连接到 Azure VM 部署](./media/image5-4.png)

> **图 5-4。** 从开发人员 PC 通过 Docker 引擎连接到 Azure VM 部署

#### <a name="scenario-b-deploy-to-an-azure-vm-through-a-docker-registry"></a>方案 b： 部署到 Azure VM 通过 Docker 注册表

![将部署到 Azure VM 通过 Docker 注册表](./media/image5-5.png)

> **图 5-5。** 将部署到 Azure VM 通过 Docker 注册表

#### <a name="scenario-c-deploy-to-an-azure-vm-from-cicd-pipelines-in-visual-studio-team-services"></a>方案 c: Azure VM 将从部署到 Visual Studio Team Services 中的 CI/CD 管道

![从 Visual Studio Team Services 中的 CI/CD 管道将部署到 Azure VM](./media/image5-6.png)

> **图 5-6。** 从 Visual Studio Team Services 中的 CI/CD 管道将部署到 Azure VM

### <a name="azure-vms-for-windows-containers"></a>Windows 容器的的 azure Vm

Azure Vm 的 Windows 容器是只是基于 Windows Server 2016，Windows 10 的 Vm 或更高版本，它们都具有 Docker 引擎设置。 在大多数情况下，你将在 Azure Vm 中使用 Windows Server 2016。

Azure 目前提供名为的 VM**与容器的 Windows Server 2016**。 可以使用此 VM 尝试新的 Windows Server 容器功能，与 Windows Server Core 或 Windows Nano Server。 安装容器操作系统映像以及然后 VM 已准备好与 Docker 一起使用。

### <a name="benefits"></a>优点

虽然 Windows 容器可部署到本地 Windows Server 2016 Vm 部署到 Azure 时，你将收到更简单的方法以开始使用准备就绪，可以使用 Windows Server 容器虚拟机。 你还可以获取测试人员和自动的可伸缩性，通过 Azure VM 缩放集可以访问的常见在线位置。

### <a name="next-steps"></a>后续步骤

在 GitHub wiki 上浏览此更深入的内容：

[https://github.com/dotnet-architecture/eShopModernizing/wiki/03.-How-to-deploy-your-Windows-Containers-based-app-into-Azure-VMs-(Including-CI-CD)](https://github.com/dotnet-architecture/eShopModernizing/wiki/03.-How-to-deploy-your-Windows-Containers-based-app-into-Azure-VMs-(Including-CI-CD))

## <a name="walkthrough-4-deploy-your-windows-containers-based-apps-to-kubernetes-in-azure-container-service"></a>演练 4： 将你的 Windows 容器基于应用部署到 Azure 容器服务中的 Kubernetes

### <a name="technical-walkthrough-availability"></a>技术演练可用性

完整技术的演练会出现在 eShopModernizing GitHub 存储库 wiki:

[https://github.com/dotnet-architecture/eShopModernizing/wiki/04.-How-to-deploy-your-Windows-Containers-based-apps-into-Kubernetes-in-Azure-Container-Service-(Including-C-CD)](https://github.com/dotnet-architecture/eShopModernizing/wiki/04.-How-to-deploy-your-Windows-Containers-based-apps-into-Kubernetes-in-Azure-Container-Service-(Including-C-CD))

### <a name="overview"></a>概述

应用程序依赖于使用 Windows 容器快速将需要使用从 IaaS Vm 消失移动甚至可更进一步的平台。 这需要能够轻松实现高可伸缩性和更好地自动可伸缩性，并针对中的重大进步自动部署和版本管理。 你可以通过使用 orchestrator 实现这些目标[Kubernetes](https://kubernetes.io/)中的可用[Azure 容器服务](https://azure.microsoft.com/services/container-service/)。

### <a name="goals"></a>目标

此演练的目的是了解如何基于 Windows 容器 – 将应用部署到 Kubernetes (也称为*K8s*) 在 Azure 容器服务。 将部署到 Kubernetes 从头是一个两步过程：

1.  将实现 Kubernetes 群集部署到 Azure 容器服务。

2.  向 Kubernetes 群集部署的应用程序和相关的资源。

### <a name="scenarios"></a>方案

#### <a name="scenario-a-deploy-directly-to-a-kubernetes-cluster-from-a-dev-environment"></a>方案 a： 部署到 Kubernetes 群集直接从开发环境

![从开发环境直接到 Kubernetes 群集部署](./media/image5-7.png)

> **图 5-7。** 从开发环境直接到 Kubernetes 群集部署

#### <a name="scenario-b-deploy-to-a-kubernetes-cluster-from-cicd-pipelines-in-team-services"></a>方案 b: Kubernetes 群集将从部署到 CI/CD 管道在 Team Services

![从 Team Services 中的 CI/CD 管道到 Kubernetes 群集部署](./media/image5-8.png)

> **图 5-8。** 从 Team Services 中的 CI/CD 管道到 Kubernetes 群集部署

### <a name="benefits"></a>优点

有很多好处与部署到在 Kubernetes 中的群集。 最大好处是您获得的生产就绪环境在其中你可以向外扩展应用程序根据你想要使用 （内部的可伸缩性的现有节点中），并根据在群集 （节点或 Vm 的数量的容器实例数全局可伸缩性的群集）。

Azure 容器服务专门针对 Azure 进行优化受欢迎的开源工具和技术。 获取一个打开的解决方案，它提供可移植性，对于你的容器和应用程序配置。 你选择的大小的主机，数量和 orchestrator 工具-容器服务将处理一切。

与 Kubernetes，开发人员都可以从思考一下物理机和虚拟机进行规划以容器为中心的基础结构，它方便了以下功能，以及其他正在：

-   基于多个容器的应用程序

-   复制容器实例和水平的自动缩放

-   命名和发现 (例如，内部 DNS)

-   平衡负载

-   滚动更新

-   分发机密

-   应用程序运行状况检查

## <a name="next-steps"></a>后续步骤

浏览 GitHub wiki 上的此内容更深入： [https://github.com/dotnet-architecture/eShopModernizing/wiki/04.-How-to-deploy-your-Windows-Containers-based-apps-into-Kubernetes-in-Azure-Container-Service-(Including-C-CD)](https://github.com/dotnet-architecture/eShopModernizing/wiki/04.-How-to-deploy-your-Windows-Containers-based-apps-into-Kubernetes-in-Azure-Container-Service-(Including-C-CD))

## <a name="walkthrough-5-deploy-your-windows-containers-based-apps-to-azure-service-fabric"></a>演练 5： 将你的 Windows 容器基于应用部署到 Azure Service Fabric

### <a name="technical-walkthrough-availability"></a>技术演练可用性

完整技术的演练会出现在 eShopModernizing GitHub 存储库 wiki:

[https://github.com/dotnet-architecture/eShopModernizing/wiki/05.-How-to-deploy-your-Windows-Containers-based-apps-into-Azure-Service-Fabric-(Including-CI-CD)](https://github.com/dotnet-architecture/eShopModernizing/wiki/05.-How-to-deploy-your-Windows-Containers-based-apps-into-Azure-Service-Fabric-(Including-CI-CD))

### <a name="overview"></a>概述

应用程序依赖于使用 Windows 容器快速将需要使用从 IaaS Vm 消失移动甚至可更进一步的平台。 这需要能够轻松实现高可伸缩性和更好地自动可伸缩性，并针对中的重大进步自动部署和版本管理。 使用 orchestrator Azure Service Fabric 中，这是可用在 Azure 云中，但也可用于在本地，或甚至在不同的公有云，可以实现这些目标。

### <a name="goals"></a>目标

此演练的目的是了解如何基于 Windows 容器 – 将应用部署到在 Azure 中的 Service Fabric 群集。 从零开始将部署到 Service Fabric 是一个两步过程：

1.  将 Service Fabric 群集部署到 Azure （或其他环境）。

2.  向 Service Fabric 群集中部署的应用程序和相关的资源。

### <a name="scenarios"></a>方案

#### <a name="scenario-a-deploy-directly-to-a-service-fabric-cluster-from-a-dev-environment"></a>方案 a： 部署到 Service Fabric 群集直接从开发环境

![从开发环境将部署直接到 Service Fabric 群集](./media/image5-9.png)

> **图 5-9。** 从开发环境将部署直接到 Service Fabric 群集

### <a name="scenario-b-deploy-to-a-service-fabric-cluster-from-cicd-pipelines-in-team-services"></a>方案 b: Service Fabric 群集将从部署到 CI/CD 管道在 Team Services

![从 Visual Studio Team Services 中的 CI/CD 管道将部署到 Service Fabric 群集](./media/image5-10.png)

> **图 5-10。** 从 Visual Studio Team Services 中的 CI/CD 管道将部署到 Service Fabric 群集

## <a name="benefits"></a>优点

向 Service Fabric 中的群集部署的优点是类似于使用 Kubernetes 的好处。 一个区别，不过，是 Service Fabric 是相比 Kubernetes，已在预览为 Windows 容器之前尽早在 2017年的 Windows 应用程序的非常成熟的生产环境。 （Kubernetes 是适用于 Linux 的更加成熟完善一些环境）。 

使用 Azure Service Fabric 的主要优势是获取生产就绪环境在其中你可以向外扩展应用程序根据你想要使用 （内部的可伸缩性的现有节点中），并根据的数量的容器实例数节点或群集 （群集的全局可伸缩性） 中的 Vm。

Azure Service Fabric 提供了可移植性对于你的容器和应用程序配置。 你可以 Service Fabric 群集在 Azure 中，或将其安装在本地在自己的数据中心。 你甚至可以安装的 Service Fabric 群集在另一个云，如[Amazon AWS](https://blogs.msdn.microsoft.com/azureservicefabric/2017/05/18/tutorial-how-to-create-a-service-fabric-standalone-cluster-with-aws-ec2-instances/)。

使用 Service Fabric，开发人员可以进行规划以容器为中心的基础结构，它方便了以下功能，以及其他进度从思考物理机和虚拟机：

-   根据应用程序的多个容器。

-   复制容器实例和水平的自动缩放。

-   命名和发现 (例如，内部 DNS)。

-   平衡负载。

-   滚动更新。

-   分发机密。

-   应用程序运行状况检查。

以下功能是独占的 （与其他 orchestrators 比较） 的 Service Fabric 在：

-   有状态服务功能，通过可靠的服务应用程序模型。

-   Actor 模式，通过 Reliable Actors 应用程序模型。

-   部署精简进程，除了 Windows 或 Linux 容器。

-   高级滚动更新和运行状况检查。

### <a name="next-steps"></a>后续步骤

在 GitHub wiki 上浏览此更深入的内容：

[https://github.com/dotnet-architecture/eShopModernizing/wiki/05.-How-to-deploy-your-Windows-Containers-based-apps-into-Azure-Service-Fabric-(Including-CI-CD)](https://github.com/dotnet-architecture/eShopModernizing/wiki/05.-How-to-deploy-your-Windows-Containers-based-apps-into-Azure-Service-Fabric-(Including-CI-CD))

>[!div class="step-by-step"]
[上一页](lift-and-shift-existing-apps-devops/migrate-to-hybrid-cloud-scenarios.md)
[下一页](conclusions.md)
