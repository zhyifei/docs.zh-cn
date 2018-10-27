---
title: 单一式应用程序
description: 使用 Microsoft 平台和工具的容器化 Docker 应用程序的生命周期
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 09/22/2017
ms.openlocfilehash: a2fe2c325377ec49f89199ad2e36c950ebab6a24
ms.sourcegitcommit: b22705f1540b237c566721018f974822d5cd8758
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/22/2018
ms.locfileid: "49633893"
---
# <a name="monolithic-applications"></a>单一式应用程序

在此方案中，是构建单个和整体化 web 应用程序或服务，并将其部署为容器。 在应用程序中的结构可能不为整体化;它可能包含多个库、 组件或甚至层 （应用程序层、 域层、 数据访问层等）。 从外部看，它是单个容器，如单个进程、 单个 web 应用程序或单个服务。

若要管理此模型，可部署单个容器来表示应用程序。 若要缩放，只添加与负载均衡器在前几个更多副本。 简单起见，管理单个部署中的单个容器或虚拟机 (VM)。

以下容器做一件事，并会在一个进程中的主体，整体模式有冲突。 图 4-1 中所示，可以包含多个组件/库或内部层中每个容器。

![](./media/image1.png)

图 4-1： 整体式应用程序体系结构的示例

这种方法的缺点是如果或应用程序的增长，需要它进行缩放。 如果整个应用程序都已缩放，这就不是问题了。 但是，在大多数情况下，应用程序的几个部分是瓶颈，需要缩放，而不使用其他组件。

使用典型电子商务示例，您可能需要是缩放产品信息组件。 众多客户浏览产品，但并不购买它们。 使用购物车的顾客比使用付款管道的多。 较少的顾客会评论或查看购买记录。 并且你可能有少量的员工，在单个区域中，需要管理货物和营销活动。 通过缩放整体式设计，所有的代码是多次进行部署。

除了"小数位数的所有内容"问题，对单个组件的更改需要完全重新测试整个应用程序，以及完全重新部署所有实例。

整体式方法很常见，并且许多组织正在开发使用此体系结构方法。 很多享受好足够结果，而其他人会遇到限制。 许多设计应用程序在此模型中，由于工具和基础结构难以构建 Soa，且他们也没有发现需要 — 应用程序增长之前。

从基础结构的角度看，每个服务器可以运行在同一台主机的许多应用程序和中的资源使用情况，你具有可接受的效率比率，图 4-2 中所示。

![](./media/image2.png)

图 4-2: 运行多个应用/容器主机

可以通过使用每个实例的专用的 Vm 部署在 Azure 中的整体式应用程序。 使用[Azure VM 规模集](https://docs.microsoft.com/azure/virtual-machine-scale-sets/)，可以轻松地缩放 Vm。 [Azure 应用服务](https://azure.microsoft.com/services/app-service/) 可运行整体式应用程序并轻松缩放实例，无需管理 VM。 自 2016，Azure 应用服务就可以运行单个实例的 Docker 容器，以及简化部署。 然后使用 Docker，可以部署单个 VM 作为 Docker 主机并运行多个实例。 使用 Azure 均衡器，在图 4-3 所示，可以管理缩放。

![](./media/image3.png)

图 4-3： 多个主机向外扩展单个的 Docker 应用程序的应用/容器

你可以管理各种主机通过传统的部署技术部署。 可以使用类似的命令来管理 Docker 主机`docker run`手动，通过持续交付 (CD) 管道，我们介绍本电子书中更高版本之类的自动化。

## <a name="monolithic-application-deployed-as-a-container"></a>部署为容器的整体式应用程序

没有为使用容器管理整体式部署带来的好处。 缩放容器实例比部署额外的 VM 要快得多，也容易得多。 尽管 VM 规模集是一个非常不错的功能来缩放 Vm，所需托管 Docker 容器，但它们需要时间来设置。 部署为应用实例时，应用的配置将作为 VM 的一部分进行管理。

将更新部署为 Docker 映像会快得多，并且网络效率更高。 可以消除导致的更多 Vm 添加了的成本随着 Vn 1 实例，在同一主机上设置 Vn 实例。 Docker 映像通常会启动以秒为单位，加快了推出速度。 拆除 Docker 实例非常简单，只调用`docker stop`命令，通常少于一秒内完成。

由于容器本质上是不可变，按照设计，永远不需要担心 Vm 损坏，因为更新脚本忘记考虑某些特定配置或磁盘上剩余的文件。

尽管整体式应用可能得益于 Docker，但我们触摸上仅优势的提示。 使用管理各种实例和生命周期的每个容器实例的容器协调器部署来自管理容器的更大的好处。 将整体式应用程序分解为可以单独缩放、开发和部署的子系统是进入微服务领域的切入点。

## <a name="publishing-a-single-docker-container-app-to-azure-app-service"></a>单个 Docker 容器应用程序发布到 Azure 应用服务

或者由于你想要获取容器部署到 Azure 的快速验证或应用程序只需单容器应用程序，Azure 应用服务提供了提供可缩放的单个容器服务的好办法。

使用 Azure 应用服务是直观和您可以启动并快速运行，因为它提供了很好的 Git 集成，以获取代码，构建在 Microsoft Visual Studio 中，并直接将其部署到 Azure。 但是，传统上 （使用任何 Docker)，如果需要其他功能、 框架或不支持在应用服务中的依赖项需要等待，直到 Azure 团队更新应用服务中的这些依赖项或切换到其他服务，如Service Fabric、 云服务或甚至普通的 Vm，对其具有更多控件且可为你的应用程序安装的所需的组件或框架。

现在，但是，（宣布在 Microsoft Connect 2016 2016 年 11 月） 和图 4‑4 中所示，使用 Visual Studio 2017 时，Azure 应用服务中的容器支持使您能够包含任何所需的应用环境中。 如果因为在容器中运行，可添加到您的应用程序依赖关系，则会在 Dockerfile 或 Docker 映像中包括这些依赖项的功能。

![](./media/image4.png)

图 4-4： 发布到 Azure 应用服务从 Visual Studio 应用/容器的容器

图 4-4 还显示了发布流推送到容器注册表，可以是 Azure 容器注册表 （注册表附近你在 Azure 中的部署和保护的 Azure Active Directory 组和帐户） 或任何其他 Docker 注册表的映像如 Docker 中心或在本地注册表。


>[!div class="step-by-step"]
[上一页](common-container-design-principles.md)
[下一页](state-and-data-in-docker-applications.md)
