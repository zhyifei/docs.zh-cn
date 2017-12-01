---
title: "Containerizing 整体应用程序"
description: "为容器化的.NET 应用程序的.NET 微服务体系结构 |Containerizing 整体应用程序"
keywords: "Docker, 微服务, ASP.NET, 容器"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: 11e2c24403b9b61584e424696c844e00e5d34b03
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="containerizing-monolithic-applications"></a>Containerizing 整体应用程序

你可能想要生成的单个、 monolithically 部署 web 应用程序或服务并将其部署为一个容器。 应用程序本身可能不是内部整体，但结构化几个库、 组件或甚至层 （应用程序层、 域层、 数据访问层等）。 外部使用，但是，它是单个容器-单个进程、 单个 web 应用程序或单个服务。

若要管理此模型，你可以部署单个容器来表示应用程序。 若要向上扩展，只需添加对负载平衡器在前面的更多副本。 为了简单起见来自于管理单个部署中的单个容器或 VM。

![](./media/image1.png)

**图 4-1**。 容器化的整体应用程序的体系结构示例

图 4-1 中所示，可以在每个容器，包括多个组件、 库或内部的层。 但是，此整体模式可能与"容器做一件事，而不在一个进程中"，但可能容器原则冲突是某些情况下为确定。

此方法的缺点中变得显而易见，如果应用程序的增长，需要进行调整。 如果可以缩放整个应用程序，它不是真正的问题。 但是，在大多数情况下，应用程序只需几部分是，需要进行缩放外，其他组件时使用小于压点。

例如，在典型的电子商务应用程序中，你可能需要缩放产品信息子系统，因为许多更多的客户浏览产品不是购买必需的许可证。 更多的客户使用他们的购物篮不是使用付款管道。 更少的客户添加注释，或查看其购买历史记录。 并且你可能有只有少量的员工组，需要管理内容和市场营销活动。 如果缩放单一式设计，这些不同的任务的所有代码是部署多个时间，并且扩展在同一级。

有多种方法来缩放应用程序-水平重复，拆分的应用程序和分区的业务概念相似或数据的不同区域。 但是，除了缩放所有组件的问题，对单个组件的更改需要完成重新测试整个应用程序，以及完成重新部署的所有实例。

但是，整体方法非常常见，，因为应用程序的开发是更容易微服务方法最初。 因此，许多组织开发使用此体系结构的方法。 某些组织有不会有什么足够结果，而其他人已达到限制。 许多组织设计使用此模型，因为工具和基础结构变得太困难生成服务面向体系结构 (SOA) 几年前，及它们看不到需要其应用程序，直到应用程序增长。

从基础结构的角度看，每个服务器可以运行在同一主机内的很多应用程序和在图 4-2 中所示在资源用法中，具有到可接受的比率的效率。

![](./media/image2.png)

**图 4-2**。 整体方法： 托管运行多个应用作为容器运行每个应用程序

可以为每个实例使用专用的虚拟机部署在 Microsoft Azure 中的单一应用程序。 此外，使用[Azure VM 缩放集](https://docs.microsoft.com/azure/virtual-machine-scale-sets/)，你可以轻松地缩放 Vm。 [Azure App Service](https://azure.microsoft.com/services/app-service/)可以还运行的单一应用程序并轻松缩放而无需管理虚拟机的实例。 自 2016，Azure 应用程序服务就可以运行单一实例的 Docker 容器都一样，从而简化部署。

作为 QA 环境或有限的生成环境，可部署多个 Docker 主机 Vm 和平衡它们使用 Azure 平衡器，如图 4-3 中所示。 这允许你管理使用粗粒度方法时，缩放，因为整个应用程序存在于单个容器中。

![](./media/image3.png)

**图 4-3**。 纵向扩展单个容器应用程序的多个主机的示例

部署到各种主机可通过传统部署技术。 可以使用类似的命令管理 docker 主机`docker run`或`docker-compose`执行手动或通过如持续交付 (CD) 管道的自动化。

## <a name="deploying-a-monolithic-application-as-a-container"></a>部署容器作为一个整体应用程序

没有为使用容器来管理整体应用程序部署的好处。 缩放容器实例是得更快比更容易地部署其他虚拟机。 即使你使用 VM 缩放集，Vm 将花时间才能启动。 在部署为而不是容器的传统应用程序实例，应用程序配置作为一部分进行管理的虚拟机，这并不理想。

部署更新，因为 Docker 映像是得相当快和高效的网络。 Docker 映像通常将启动以秒为单位，― 加快了首次推出。 关闭的 Docker 映像实例非常简单，只需为颁发`docker stop`命令，并完成此过程通常少于一秒。

容器是设计使然不可变，因为无需担心如何损坏的 Vm。 与此相反，为 VM 的更新脚本可能会忘记某些特定配置或磁盘上剩余的文件的帐户。

尽管单一应用程序可以受益于 Docker，我们相互接触仅在好处上。 使用管理各种实例和每个容器实例的生命周期的容器 orchestrators 部署来自管理容器的其他好处。 中断此整体应用程序分解可以缩放、 开发和部署单独的子系统是微服务的领域你入口点。

## <a name="publishing-a-single-container-based-application-to-azure-app-service"></a>单容器基于应用程序发布到 Azure App Service

你是否想要进行验证的部署到 Azure 的容器或应用程序只需单个容器应用程序时，Azure App Service 提供了提供可缩放的单容器基于服务的好办法。 使用 Azure App Service 是简单的。 它提供了使用 Git，以便可以方便地获取你的代码，生成它在 Visual Studio 中，并将其部署到 Azure 直接极好的集成。

![](./media/image4.png)

**图 4-4**。 单容器应用程序发布到 Azure App Service 从 Visual Studio

而无需 Docker，如果需要其他功能，框架或不支持在 Azure App Service 中的依赖项必须等待，直到 Azure 团队更新在 App Service 中的这些依赖关系。 或者，你必须切换到 Azure Service Fabric、 Azure 云服务或甚至虚拟机，其中进一步控件并且你无法安装所需的组件或 framework 应用程序等其他服务。

在 Visual Studio 2017 容器支持使你能够包括任何你想在应用程序环境中，在图 4-4 中所示。 由于你已经运行在容器中，如果将一个依赖项添加到你的应用程序，你可以在 Dockerfile 或 Docker 映像中包括依赖关系。

此外显示在图 4-4 中，发布流将映像推送通过容器注册表中。 这可以是 Azure 容器注册表 （注册表关闭你在 Azure 中的部署和保护的 Azure Active Directory 组和帐户） 或任何其他 Docker 注册表，如 Docker Hub 或在本地注册表。


>[!div class="step-by-step"]
[以前](index.md) [下一步] (docker-应用程序的状态-data.md)
