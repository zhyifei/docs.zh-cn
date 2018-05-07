---
title: 什么是 Docker？
description: 使用 Microsoft 平台和工具的容器化 Docker 应用程序的生命周期
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 09/21/2017
ms.openlocfilehash: c566c4104f21ff6a55646d96e141cde4c7722735
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="what-is-docker"></a>什么是 Docker？

[Docker](https://www.docker.com/)是[开放源代码项目](https://github.com/docker/docker)用于自动执行与可以在云或本地运行的可移植的足容器应用程序的部署 (请参阅图 1-2）。 Docker 也是[公司](https://www.docker.com/)，推广并制定此技术，在与云，Linux 和 Windows 供应商，包括 Microsoft 协作中工作。

![](./media/image2.png)

图 1-2: Docker 部署在混合云中的所有层的容器

Docker 映像容器可以本机 Linux 和 Windows 上运行。 但是，Windows 映像可以仅在 Windows 主机上运行，并且可以仅在 Linux 主机，这意味着主机服务器或 VM 上运行 Linux 映像。

开发人员可以在 Windows、 Linux 或 macOS 上使用开发环境。 在开发计算机上开发人员运行到的 Docker 映像部署，包括应用程序和其依赖项的 Docker 主机。 开发人员在 Linux 上或在 Mac 上工作使用基于，Linux 的 Docker 主机，它们可以创建仅针对 Linux 容器映像。 (在 Mac 上工作的开发人员可以编辑代码或运行 Docker 命令行界面\[CLI\]从 macOS，但是，撰写本文时，容器不直接在 macOS 上运行。)在 Windows 处理开发人员可以为 Linux 或 Windows 容器创建映像。

若要承载在开发环境中的容器，并提供其他开发人员工具，Docker 附带[Docker 社区版 (CE)](https://www.docker.com/community-edition)为 Windows 或 macOS。 这些产品安装需要的 VM （Docker 主机） 来承载容器。 Docker 还可提供[Docker Enterprise Edition (EE)](https://www.docker.com/enterprise-edition)、 其用于企业开发，由 IT 团队生成、 装运，，和在生产中运行大型业务关键型应用程序。

若要运行[Windows 容器](https://msdn.microsoft.com/virtualization/windowscontainers/about/about_overview)，有两种类型的运行时：

-   **Windows Server 容器** 此运行时提供通过进程和命名空间隔离技术的应用程序隔离。 Windows Server 容器与容器主机和主机上运行的所有容器共享内核。

-   **HYPER-V 容器** 这会将对由 Windows Server 容器通过在高度优化的 VM 中运行每个容器提供的隔离上扩展。 在此配置中，容器主机的内核不与 Hyper-V 容器共享，以提供更好地隔离。

适用于这些容器的映像的创建相同的方式和功能相同。 区别在于如何从映像创建容器-运行 HYPER-V 容器需要使用额外的参数。 有关详细信息，请参阅 [Hyper-V 容器](https://msdn.microsoft.com/virtualization/windowscontainers/about/about_overview)。

## <a name="comparing-docker-containers-with-vms"></a>比较与 Vm 的 Docker 容器

图 1-3 显示的比较虚拟机和 Docker 容器。

因为容器需要数量少得多的资源 （例如，它们不需要完整的 OS），因此可以轻松部署和快速启动。 这使你能够更高的密度，这意味着，你可以在相同的硬件单元，从而降低成本上运行更多的服务。

在同一个内核上运行的副作用是，为你实现比 Vm 较少隔离。

映像的主要目标是使环境（依赖项）在不同的部署中保持不变。 也就是说，可以在计算机上调试它，然后将其部署到保证具有相同环境的另一台计算机上。

容器映像是一种方法来打包的应用或服务并将其部署以可靠且可重现的方式。 在这一方面，Docker 不是仅一种技术，也是基本原理和进程。

当使用 Docker，您将无法听到开发人员说，"It works 我在计算机上，不要在生产中？" 他们可以简单地说，"上运行 Docker，"因为打包的 Docker 应用程序可以运行任何受支持的 Docker 环境，并且它将重新运行安装程序为所有部署目标 （开发、 QA、 过渡，生产等。） 使用的方式运行。

![](./media/image3.png)

图 1-3： 的传统 Vm 到 Docker 容器的比较


>[!div class="step-by-step"]
[上一页] (index.md) [下一页] (docker-terminology.md)
