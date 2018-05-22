---
title: 整体应用程序
description: 使用 Microsoft 平台和工具的容器化 Docker 应用程序的生命周期
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 09/22/2017
ms.openlocfilehash: fe25fa8772c60625c5564d5e7194957366a6010a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="monolithic-applications"></a>整体应用程序

在此方案中，是生成单个和整体 web 应用程序或服务，并将其部署为一个容器。 在应用程序，该结构可能不是整体;它可能包含多个库、 组件或甚至层 （应用程序层、 域层、 数据访问层等）。 从外部看，它是单个容器中的，如单个进程、 单个 web 应用程序或单个服务。

若要管理此模型，可部署单个容器来表示应用程序。 若要缩放它，只需添加对负载平衡器在前面的几个更多副本。 为了简单起见来自于管理单个部署中的单个容器或虚拟机 (VM)。

以下主体做一件事，并会在一个进程中的容器的整体模式有冲突。 图 4-1 中所示，你可以包括多个组件/库或每个容器中的内部层。

![](./media/image1.png)

图 4-1： 的整体应用程序体系结构示例

如果或当应用程序扩展，需要进行调整时，将提供此方法的缺点。 如果整个应用程序都已缩放，这就不是问题了。 但是，在大多数情况下，应用程序的几个部分是压点需要缩放，而不太使用了其他组件。

使用典型电子商务示例，你可能需要是缩放产品信息组件。 众多客户浏览产品，但并不购买它们。 使用购物车的顾客比使用付款管道的多。 较少的顾客会评论或查看购买记录。 并且你可能有只有少量的员工组，在单个区域中，需要管理内容和市场营销活动。 通过缩放单一式设计，所有的代码被部署了多次。

除了"小数位数的所有内容"的问题，对单个组件的更改需要完成重新测试整个应用程序以及完成重新部署的所有实例。

整体方法很常见，并且许多组织正在开发使用此体系结构的方法。 许多不会有什么享受足够结果，而其他人会遇到限制。 许多设计其应用程序在此模型中，因为工具和基础结构已生成 SOAs，太困难，它们看不到需要-直到应用程序增长。

从基础结构的角度看，每个服务器可以运行在同一主机内的很多应用程序和在图 4-2 中所示在你的资源使用情况中具有的效率到可接受的比率。

![](./media/image2.png)

图 4-2: 运行多个应用程序/容器主机

你可以通过使用每个实例的专用的 Vm 部署在 Azure 中的单一应用程序。 使用[Azure VM 缩放集](https://docs.microsoft.com/azure/virtual-machine-scale-sets/)，你可以轻松地扩展 Vm。 [Azure 应用服务](https://azure.microsoft.com/en-us/services/app-service/) 可运行整体式应用程序并轻松缩放实例，无需管理 VM。 自 2016，Azure 应用程序服务就可以运行单一实例的 Docker 容器，以及，从而简化部署。 并使用 Docker，可以部署一个单独的 VM 为 Docker 主机，并运行多个实例。 使用 Azure 平衡器，在图 4-3 所示，你可以管理缩放。

![](./media/image3.png)

图 4-3： 多个主机扩展单个的 Docker 应用程序的应用/容器

你可以管理部署到各种主机通过传统部署技术。 你可以使用类似的命令来管理 Docker 主机`docker run`手动，通过如连续传送 (CD) 管道，我们介绍更高版本中此图书的自动化。

## <a name="monolithic-application-deployed-as-a-container"></a>部署为容器的整体式应用程序

没有为使用容器来管理整体部署的好处。 缩放容器实例比部署额外的 VM 要快得多，也容易得多。 虽然 VM 缩放集是一项强大功能来扩展 Vm，但这需要来承载你的 Docker 容器，它们需要时间来设置。 部署为应用实例时，应用的配置将作为 VM 的一部分进行管理。

将更新部署为 Docker 映像会快得多，并且网络效率更高。 可以在相同的主机 Vn 1 实例，消除增加的成本导致更多虚拟机上设置 Vn 实例。 Docker 映像通常情况下会以秒为单位，从而加快首次推出。 关闭的 Docker 实例非常简单，只需调用`docker stop`命令，通常少于一秒内完成。

容器是本质上是不可变的设计使然，由于从不需要担心损坏 Vm，因为更新脚本忘记某些特定配置或磁盘上剩余的文件的帐户。

尽管整体应用可以受益于 Docker，我们触摸上仅的好处的提示。 使用管理各种实例和每个容器实例的生命周期的容器 orchestrators 部署来自管理容器的更大好处。 将整体式应用程序分解为可以单独缩放、开发和部署的子系统是进入微服务领域的切入点。

## <a name="publishing-a-single-docker-container-app-to-azure-app-service"></a>单个的 Docker 容器应用程序发布到 Azure App Service

或者因为你想要收到部署到 Azure 的容器的快速验证，或者在应用程序只需单个容器应用程序，Azure 应用程序服务提供提供可缩放的单容器服务的好办法。

使用 Azure App Service 是直观和您能够快速安装和快速运行，因为它提供了很好 Git 集成，以获取你的代码，生成它在 Microsoft Visual Studio 中，直接将其部署到 Azure。 但是，传统上 （使用任何 Docker)，如果需要其他功能，框架或在应用程序服务中不受支持的依赖关系你需要以等待它之前 Azure 团队更新在 App Service 中的这些依赖项，或者切换到等其他服务Service Fabric、 云服务或甚至纯 Vm，对其具有进一步控制且可以为你的应用程序中安装所需的组件或框架。

现在，但 （宣布 Microsoft Connect 2016 在 2016 年 11 月） 和图 4‑4 中所示，使用 Visual Studio 2017 时，在 Azure App Service 中的容器支持使你能够包含任何所需的应用程序环境中。 如果因为容器中运行，可添加到你的应用，依赖关系，将获得你 Dockerfile 或 Docker 映像中包括这些依赖关系的功能。

![](./media/image4.png)

图 4-4： 发布到 Azure App Service 从 Visual Studio 应用程序/容器的容器

图 4-4 还显示发布流推送通过容器注册表中，可以是 Azure 容器注册表 （注册表附近你在 Azure 中的部署和保护的 Azure Active Directory 组和帐户） 或任何其他 Docker 注册表映像如 Docker Hub 或在本地注册表。


>[!div class="step-by-step"]
[以前] (common-container-design-principles.md) [下一步] (state-and-data-in-docker-applications.md)
