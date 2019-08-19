---
title: 演练和技术入门概述
description: 通过 Azure 云和 Windows 容器实现现有 .NET 应用程序的现代化 |演练和技术入门概述
ms.date: 04/28/2018
ms.openlocfilehash: 81f7d9fbf596a23b83e2dc9251788b33a8817e16
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/30/2019
ms.locfileid: "69577850"
---
# <a name="walkthroughs-and-technical-get-started-overview"></a>演练和技术入门概述

为了限制此电子书的大小, GitHub 存储库中提供了其他技术文档和完整演练。 本章中所述的联机演练系列介绍了多个基于 Windows 容器和部署到 Azure 的环境的分步设置。

以下各节说明每个演练的具体内容、其目标和高级构想, 并提供所涉及任务的关系图。 你可以在*eShopModernizing* apps GitHub 存储库 wiki <https://github.com/dotnet-architecture/eShopModernizing/wiki>中获取这些演练本身。

## <a name="technical-walkthrough-list"></a>技术演练列表

以下入门演练提供适用于示例应用的一致且全面的技术指南, 你可以使用容器进行抬起和移动, 然后在 Azure 中使用多个部署选项。

以下每个演练使用新的示例 eShopLegacy 和 eShopModernizing 应用, 这些应用可在 GitHub <https://github.com/dotnet-architecture/eShopModernizing>上的获取。

- **EShop 旧版应用 (基准应用与现代化) 简介**

- **将现有的 ASP.NET web 应用 (WebForms & MVC) 与 Windows 容器容器化**

- **将现有 WCF 服务 (N 层应用) 与 Windows 容器容器化**

- **将基于 Windows 容器的应用部署到 Azure Vm**

- **将基于 Windows 容器的应用部署到 Azure 容器服务中的 Kubernetes**

## <a name="walkthrough-1-tour-of-eshop-legacy-apps"></a>演练 1:EShop 旧版应用的教程

### <a name="technical-walkthrough-availability"></a>技术演练可用性

EShopModernizing GitHub 存储库 wiki 中提供了完整的技术演练:

[eShopModernizing wiki 演练](https://github.com/dotnet-architecture/eShopModernizing/wiki)

### <a name="overview"></a>概述

在本演练中, 您可以浏览三个示例旧应用程序的初始实现。 前两个示例 web 应用都有单一体系结构, 并且是使用经典 ASP.NET 创建的。 一个应用程序基于 ASP.NET 4.x MVC;第二个应用程序基于 ASP.NET 4.x Web 窗体。
第三个应用是由客户端 WinForms 应用程序和服务器端[Windows Communication Foundation (WCF)](../../framework/wcf/whats-wcf.md)服务组成的3层应用程序。

所有这些应用程序均可在[EShopModernizing GitHub](https://github.com/dotnet-architecture/eShopModernizing)存储库中找到。

### <a name="goals"></a>目标

本演练的主要目的只是熟悉这些应用以及其代码和配置。 你可以配置应用, 使其生成并使用模拟数据, 而无需使用 SQL 数据库来进行测试。 此可选配置以分离的方式基于依赖项注入。

### <a name="scenario-1-aspnet-web-apps"></a>方案 1:ASP.NET Web 应用

下图显示了原始旧的 ASP.NET web 应用程序的简单方案。

![原始旧的 ASP.NET web 应用程序的简单体系结构方案](./media/image5-1.png)

从业务域角度来看, 这两种应用都提供相同的目录管理功能。 EShop 企业团队的成员将使用该应用来查看和编辑产品目录。

下图显示了初始应用屏幕截图。

![ASP.NET MVC 和 ASP.NET Web 窗体应用程序 (现有/旧技术)](./media/image5-2.png)

ASP.NET 4.x 或更早版本中的依赖项 (对于 MVC 或 Web 窗体) 意味着这些应用程序不会在 .NET Core 上运行, 除非使用 ASP.NET Core MVC 来完全重写代码。

### <a name="scenario-2-wcf-service-and-winforms-client-app-3-tier-app"></a>方案 2：WCF 服务和 WinForms 客户端应用 (3 层应用)

下图显示了原始的3层旧应用程序的简单方案。

![具有 WCF 服务和 WinForms 客户端应用程序的原始旧版3层应用程序的简单体系结构方案](./media/image5-1.5.png)

### <a name="benefits"></a>优点

此演练的优点非常简单:只需熟悉代码和初始应用即可。

### <a name="next-steps"></a>后续步骤

更深入了解 GitHub wiki:

- [有关基线 ASP.NET MVC 和 Web 窗体 "旧版" 应用的教程](https://github.com/dotnet-architecture/eShopModernizing/wiki/01.-Tour-on-the-ASP.NET-MVC-and-WebForms-apps-implementation-code)
- [有关基线 WCF 服务和 WinForms (3 层) "旧版" 应用的教程](https://github.com/dotnet-architecture/eShopModernizing/wiki/21.-Tour-on-the-WCF-service-and-WinForms-apps)

## <a name="walkthrough-2-containerize-your-existing-net-applications-with-windows-containers"></a>演练 2:将现有 .NET 应用程序与 Windows 容器容器化

### <a name="overview"></a>概述

使用 Windows 容器来改善现有 .NET 应用程序的部署, 如基于 MVC、Web 窗体或 WCF 的应用程序, 到生产、开发和测试环境。

### <a name="goals"></a>目标

本演练的目的是说明用于容器化现有 .NET Framework 应用程序的多个选项。 你可以：

- 使用[Visual studio 2017 用于 Docker 的工具](/aspnet/core/host-and-deploy/docker/visual-studio-tools-for-docker)(visual studio 2017 或更高版本) 容器化应用程序。

- 通过手动添加[Dockerfile](https://docs.docker.com/engine/reference/builder/), 然后使用[Docker CLI](https://docs.docker.com/engine/reference/commandline/cli/)容器化你的应用程序。

- 使用[Img2Docker](https://github.com/docker/communitytools-image2docker-win)工具 (Docker 中的开源工具) 容器化应用程序。

本演练重点介绍 Visual Studio 2017 Tools for Docker 方法, 但另外两种方法与使用 Dockerfile 非常相似。

### <a name="scenario-1-containerized-aspnet-web-apps"></a>方案 1:容器化 ASP.NET web 应用

下图显示容器化 eShop 旧版 web 应用应用程序的方案。

![开发环境中容器化 ASP.NET 应用程序的简化体系结构示意图](./media/image5-3.png)

### <a name="scenario-2-containerized-wcf-service"></a>方案 2：容器化 WCF 服务

下图显示了具有容器化 WCF 服务的3层应用程序的方案。

![开发环境中容器化 WCF 服务的简化体系结构图](./media/image5-3.5.png)

### <a name="benefits"></a>优点

在容器中运行单一应用程序有一些优点。 首先, 为应用程序创建一个映像。 从此时开始, 每个部署都在同一环境中运行。 每个容器均使用相同的操作系统版本, 安装相同版本的依赖项, 使用相同的 .NET framework 版本, 并使用相同的过程构建。 基本上, 使用 Docker 映像控制应用程序的依赖关系。 部署容器时, 依赖项会随应用程序一起移动。

另一个好处是, 开发人员可以在 Windows 容器提供的一致环境中运行该应用程序。 仅在某些版本中出现的问题可以立即得到发现, 而不是在过渡环境或生产环境中呈现。 开发团队成员使用的开发环境不同于在容器中运行应用程序的情况。

容器化应用程序还具有更简单的向外扩展曲线。 容器化应用使你能够在 VM 或物理计算机上拥有更多应用程序和服务实例 (与每台计算机的常规应用程序部署相比)。 这会转换为更高的密度和更少的所需资源, 尤其是在使用协调器 (如 Kubernetes) 时。

在理想情况下, 容器化不需要对应用程序代码进行任何更改 (C\#)。 在大多数情况下, 只需要 Docker 部署元数据文件 (Dockerfile 和 Docker Compose 文件)。

### <a name="next-steps"></a>后续步骤

更深入了解 GitHub wiki:

- [如何通过 Windows 容器和 Docker 容器化 .NET Framework web 应用](https://github.com/dotnet-architecture/eShopModernizing/wiki/02.-How-to-containerize-the-.NET-Framework-web-apps-with-Windows-Containers-and-Docker)
- [将 Docker 支持添加到 WCF 服务](https://github.com/dotnet-architecture/eShopModernizing/wiki/22.-Adding-Docker-Support)

## <a name="walkthrough-3-deploy-your-windows-containers-based-app-to-azure-vms"></a>演练 3:将基于 Windows 容器的应用部署到 Azure Vm

### <a name="technical-walkthrough-availability"></a>技术演练可用性

EShopModernizing GitHub 存储库 wiki 中提供了完整的技术演练:<https://github.com/dotnet-architecture/eShopModernizing/wiki/06.-Deploying-your-Windows-Containers-based-app-into-Azure-VMs-(Including-CI-CD)>

### <a name="overview"></a>概述

在 Azure 中的 Windows Server 2016 虚拟机 (VM) 上部署到 Docker 主机后, 可以快速设置开发/测试/过渡环境。 它还为测试人员或业务用户提供了一个用于验证应用程序的常见位置。 Vm 还可以是有效的基础结构即服务 (IaaS) 生产环境。

### <a name="goals"></a>目标

本演练的目的是向你显示在将 Windows 容器部署到基于 Windows Server 2016 或更高版本的 Azure Vm 时所拥有的多种替代方法。

### <a name="scenarios"></a>方案

本演练介绍了多个方案。

#### <a name="scenario-a-deploy-to-an-azure-vm-from-a-dev-pc-through-docker-engine-connection"></a>方案 A:通过 Docker 引擎连接从开发 PC 部署到 Azure VM

![通过 Docker 引擎连接从开发 PC 部署到 Azure VM](./media/image5-4.png)

**图 5-4**。 通过 Docker 引擎连接从开发 PC 部署到 Azure VM

#### <a name="scenario-b-deploy-to-an-azure-vm-through-a-docker-registry"></a>方案 B:通过 Docker 注册表部署到 Azure VM

![通过 Docker 注册表部署到 Azure VM](./media/image5-5.png)

**图 5-5**。 通过 Docker 注册表部署到 Azure VM

#### <a name="scenario-c-deploy-to-an-azure-vm-from-cicd-pipelines-in-azure-devops-services"></a>方案 C:通过 Azure DevOps Services 中的 CI/CD 管道部署到 Azure VM

![通过 Azure DevOps Services 中的 CI/CD 管道部署到 Azure VM](./media/image5-6.png)

**如 5-6**。 通过 Azure DevOps Services 中的 CI/CD 管道部署到 Azure VM

### <a name="azure-vms-for-windows-containers"></a>适用于 Windows 容器的 Azure Vm

适用于 Windows 容器的 Azure Vm 是基于 Windows Server 2016、Windows 10 或更高版本的 Vm, 同时安装了 Docker 引擎。 大多数情况下, 在 Azure Vm 中使用 Windows Server 2016。

Azure 当前提供名为**Windows Server 2016 With 容器**的 VM。 使用 Windows Server Core 或 Windows Nano Server, 可使用此 VM 尝试新的 Windows Server 容器功能。 安装容器操作系统映像, 然后 VM 即可用于 Docker。

### <a name="benefits"></a>优点

尽管可以将 Windows 容器部署到本地 Windows Server 2016 Vm, 但在部署到 Azure 时, 可以使用随时可用的 Windows Server 容器 Vm 来更轻松地入门。 你还可以获取可通过 Azure 虚拟机规模集访问的公共联机位置, 并可通过 Azure 虚拟机规模集进行自动缩放。

### <a name="next-steps"></a>后续步骤

更深入了解 GitHub wiki:

<https://github.com/dotnet-architecture/eShopModernizing/wiki/06.-Deploying-your-Windows-Containers-based-app-into-Azure-VMs-(Including-CI-CD)>

## <a name="walkthrough-4-deploy-your-windows-containers-based-apps-to-azure-container-instances-aci"></a>演练 4:将基于 Windows 容器的应用部署到 Azure 容器实例 (ACI)

### <a name="technical-walkthrough-availability"></a>技术演练可用性

EShopModernizing GitHub 存储库 wiki 中提供了完整的技术演练:

[将应用部署到 ACI (Azure 容器实例)](https://github.com/dotnet-architecture/eShopModernizing/wiki/05.-Deploying-the-Apps-to-ACI-(Azure-Container-Instances))

### <a name="overview"></a>概述

[Azure 容器实例 (ACI)](https://docs.microsoft.com/azure/container-instances/)是具有容器开发/测试/过渡环境的最快捷方式, 可以在其中部署容器的单个实例。

### <a name="goals"></a>目标

本演练演示了将 Windows 容器部署到 Azure 容器实例 (ACI) 以及如何将 eShopModernizing 应用部署到 ACI 的主要方案。

### <a name="scenarios"></a>方案

将 eShopModernizing 应用程序部署到 ACI 中可能有一些变化, 例如仅部署一个或所有应用 (MVC 应用、WebForms 应用或 WCF 服务)。 在下面显示的以下方案中, 你可以看到 ASP.NET MVC 应用和 SQL Server 容器, 它们都作为容器部署到 ACI (Azure 容器实例) 中。

![从开发环境部署到 ACI](./media/image5-3.5.6.png)

### <a name="benefits"></a>优点

使用 azure 容器实例可以轻松地在 Azure 中创建和管理 Docker 容器, 而无需预配虚拟机或采用更高级别的服务。 使用 ACI, 你可以直接在 Azure 中部署 Windows 容器, 并在几秒钟内使用完全限定的域名 (FQDN) 向 internet 公开该容器 (前提是在 docker 注册表中准备好 Windows 容器映像, 如 Docker 中心或 Azure 容器)注册表)。

### <a name="considerations"></a>注意事项

将具有完全 .NET Framework/ASP.NET 或 SQL Server 的 Windows 容器部署到 Azure 容器实例 (ACI) 不如部署到常规 Docker 主机 (例如 Windows Server 2016 with Windows 容器) 的速度快, 因为 Docker 映像必须是每次都已下载 (从 Docker 注册表中提取) 和 SQL 容器映像 (15.1 GB) 和 ASP.NET 容器映像 (13.9 GB) 的大小很大, 但它比维护自己的 Docker 主机 (永久在线) 要便宜得多。Windows Server 2016 在 Azure 中使用 Windows 容器 VM, 而不是将整个 orchestrator (如 Azure 中的 Kubernetes (AKS)) 提到, 而是生产部署的一个不错选择。

作为 main 结论, 使用 Azure 容器实例是一种非常引人注目的选项, 适用于开发/测试方案和 CI/CD 管道。

## <a name="next-steps"></a>后续步骤

更深入了解 GitHub wiki:

[https://github.com/dotnet-architecture/eShopModernizing/wiki/05.-Deploying-the-Apps-to-ACI-(Azure-Container-Instances)](https://github.com/dotnet-architecture/eShopModernizing/wiki/05.-Deploying-the-Apps-to-ACI-(Azure-Container-Instances))

## <a name="walkthrough-5-deploy-your-windows-containers-based-apps-to-kubernetes-in-azure-container-service"></a>演练 5:将基于 Windows 容器的应用部署到 Azure 容器服务中的 Kubernetes

### <a name="technical-walkthrough-availability"></a>技术演练可用性

EShopModernizing GitHub 存储库 wiki 中提供了完整的技术演练:

<https://github.com/dotnet-architecture/eShopModernizing/wiki/04.-How-to-deploy-your-Windows-Containers-based-apps-into-Kubernetes-in-Azure-Container-Service-(Including-CI-CD)>

### <a name="overview"></a>概述

基于 Windows 容器的应用程序很快需要使用平台, 甚至可以从 IaaS Vm 进一步移动。 这是为了轻松实现高可伸缩性和更好的自动伸缩性, 并为自动化部署和版本控制提供了显著改进。 可以通过使用[Azure 容器服务](https://azure.microsoft.com/services/container-service/)中提供的 orchestrator [Kubernetes](https://kubernetes.io/)来实现这些目标。

### <a name="goals"></a>目标

本演练的目的是了解如何在 Azure 容器服务中将基于 Windows 容器的应用程序部署到 Kubernetes (也称为*K8s*)。 从头开始部署到 Kubernetes 的过程分为两个步骤:

1. 将 Kubernetes 群集部署到 Azure 容器服务。

2. 将应用程序和相关资源部署到 Kubernetes 群集。

### <a name="scenarios"></a>方案

#### <a name="scenario-a-deploy-directly-to-a-kubernetes-cluster-from-a-dev-environment"></a>方案 A:直接从开发环境部署到 Kubernetes 群集

![直接从开发环境部署到 Kubernetes 群集](./media/image5-7.png)

**图 5-7**。 直接从开发环境部署到 Kubernetes 群集

#### <a name="scenario-b-deploy-to-a-kubernetes-cluster-from-cicd-pipelines-in-azure-devops-services"></a>方案 B:从 Azure DevOps Services 中的 CI/CD 管道部署到 Kubernetes 群集

![从 Azure DevOps Services 中的 CI/CD 管道部署到 Kubernetes 群集](./media/image5-8.png)

**图 5-8**。 从 Azure DevOps Services 中的 CI/CD 管道部署到 Kubernetes 群集

### <a name="benefits"></a>优点

部署到 Kubernetes 中的群集有很多好处。 最大的好处是, 你可以获得一个生产就绪的环境, 在该环境中, 你可以根据要使用的容器实例数 (现有节点中的内部可伸缩性) 以及群集中的节点或 Vm 的数目来扩展应用程序 (群集的全局可伸缩性)。

Azure 容器服务专门为 Azure 优化了常用开源工具和技术。 你将获得一个开放式解决方案, 该解决方案为你的容器和应用程序配置提供可移植性。 选择大小、主机数和 orchestrator 工具-容器服务处理其他所有内容。

使用 Kubernetes, 开发人员可从考虑物理机和虚拟机中取得进展, 从而规划以容器为中心的基础结构, 从而促进以下功能, 还有其他功能:

- 基于多个容器的应用程序

- 复制容器实例和水平自动缩放

- 命名和发现 (例如内部 DNS)

- 平衡负载

- 滚动更新

- 分发机密

- 应用程序运行状况检查

## <a name="next-steps"></a>后续步骤

更深入了解 GitHub wiki:<https://github.com/dotnet-architecture/eShopModernizing/wiki/04.-How-to-deploy-your-Windows-Containers-based-apps-into-Kubernetes-in-Azure-Container-Service-(Including-CI-CD)>

## <a name="walkthrough-6-deploy-your-windows-containers-based-apps-to-azure-app-service-for-containers"></a>演练 6:将基于 Windows 容器的应用部署到容器 Azure App Service

### <a name="technical-walkthrough-availability"></a>技术演练可用性

EShopModernizing GitHub 存储库 wiki 中提供了完整的技术演练:

<https://github.com/dotnet-architecture/eShopModernizing/wiki/Deploy-Windows-Container-to-Azure-App-Service>

### <a name="overview"></a>概述

可以轻松地将使用 Windows 容器的简单容器化应用程序部署到容器 Azure App Service。 对于大多数基于 Windows 容器的应用程序, 建议使用这种方法。

### <a name="goals"></a>目标

本演练的目的是了解如何将基于 Windows 容器的应用程序部署到注册表中的容器 Azure App Service (Docker 中心或 Azure 容器注册表)。

### <a name="scenario"></a>应用场景

![将基于 Windows 容器的应用部署到容器 Azure App Service](./media/image5-11.png)

### <a name="benefits"></a>优点

部署到容器 Azure App Service 提供与 Azure App Service 的 PaaS 优点配对的容器的优点。 应用服务可以轻松地在垂直和水平方向上缩放, 并且可以配置为自动缩放以满足不断变化的需求。 可以通过零停机时间来执行更新, 也可以轻松地配置注册表中的持续部署。

## <a name="next-steps"></a>后续步骤

更深入了解 GitHub wiki:<https://github.com/dotnet-architecture/eShopModernizing/wiki/Deploy-Windows-Container-to-Azure-App-Service>

> [!div class="step-by-step"]
> [上一页](modernize-existing-apps-to-cloud-optimized/migrate-to-hybrid-cloud-scenarios.md)
> [下一页](conclusions.md)
