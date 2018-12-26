---
title: 什么是 Docker？
description: 使用 Microsoft 平台和工具的容器化 Docker 应用程序的生命周期
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 09/21/2017
ms.openlocfilehash: 056fb613c078cc407380060dc11890406ac8cffd
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/28/2018
ms.locfileid: "50197673"
---
# <a name="what-is-docker"></a>什么是 Docker？

[Docker](https://www.docker.com/)是一个[开源项目](https://github.com/docker/docker)，用于将应用程序自动部署为可移植，自给自足的容器，可以在云或本地运行（参见图1-2）。 Docker也是一家推广和开发这项技术的[公司](https://www.docker.com/)，与包括微软在内的云，Linux和Windows供应商合作。

![](./media/image2.png)

图 1-2: Docker 在混合云的所有层上部署容器

Docker 镜像容器可以在 Linux 和 Windows 上原生运行。 但是，Windows 映像只能在 Windows 主机上运行，而 Linux 映像只能在 Linux 主机上运行，作为主机服务器或VM。

开发人员可以在 Windows、Linux 或 macOS 上使用开发环境。 在开发计算机上，开发人员在运行到哪个 Docker 映像部署，包括应用程序和其依赖项的 Docker 主机。 在 Linux 或 Mac 上进行开发的开发人员使用基于 Linux 的 Docker 主机，并且他们可以仅为 Linux 容器创建映像。 (在 Mac 上工作的开发人员可以编辑代码或运行 Docker 命令行接口\[CLI\]从 macOS，但是，在撰写本文时，容器不直接在 macOS 上运行。)在 Windows 上进行开发的开发人员可以为 Linux 或 Windows 容器创建映像。

开发人员可以在 Windows、Linux 或 macOS 上使用开发环境。 在开发计算机上，开发人员运行部署了 Docker 映像的 Docker 主机，包括应用程序及其依赖项。 在 Linux 或 Mac 上工作的开发人员使用基于 Linux 的 Docker 主机，他们只能为 Linux 容器创建映像。 （在 Mac 上工作的开发人员可以编辑代码或从 macOS 运行Docker命令行界面\[CLI\]，但是，在撰写本文时，容器不能直接在 macOS 上运行。）在 Windows 上工作的开发人员可以为 Linux 或 Windows 容器创建映像。

为了在开发环境中托管容器，并提供其他开发人员工具，Docker 为 Windows 或 macOS 提供了 [Docker 社区版 (CE)](https://www.docker.com/community-edition)。 这些产品安装了托管容器所需的 VM（Docker 主机）。 Docker 还提供 [Docker 企业版 (EE)](https://www.docker.com/enterprise-edition)，该版本专为企业开发而设计，供生成、交付和在生产中运行大型业务关键型应用程序的 IT 团队使用。

若要运行 [Windows 容器](/virtualization/windowscontainers/about/)，有两种类型的运行时可供使用：

-   **Windows Server 容器** 此运行时通过进程和名称空间隔离技术提供应用程序隔离。 Windows Server 容器与容器主机和主机上运行的所有容器共享内核。

-   **HYPER-V 容器** 这会提供由 Windows Server 容器通过在高度优化的 VM 中运行每个容器的隔离上扩展。 在此配置中，容器主机的内核不与 Hyper-V 容器共享，以提供更好地隔离。

这些容器的映像以相同的方式创建并且功能相同。 区别在于如何从映像创建容器-运行 HYPER-V 容器需要一个额外的参数。 有关详细信息，请参阅 [Hyper-V 容器](/virtualization/windowscontainers/about/)。


## <a name="comparing-docker-containers-with-vms"></a>比较 Docker 容器和 Vm

图 1-3 显示了 VM 和 Docker 容器之间的比较

由于容器需要的资源少得多（例如，它们不需要完整的操作系统），因此它们易于部署并且启动速度快。这使您可以拥有更高的密度，这意味着您可以在同一硬件单元上运行更多服务，从而降低成本。

作为在同一内核上运行的副作用，您实现的隔离比VM少。

映像的主要目标是使环境（依赖项）在不同的部署中保持不变。 这意味着您可以在计算机上对其进行调试，然后将其部署到保证具有相同环境的另一台计算机上。

容器映像是一种打包应用程序或服务并以可靠且可重现的方式部署它的方法。在这方面，Docker 不仅是一种技术，它也是一种理念和过程。

当使用 Docker 时，您不会听到开发人员说：“它适用于我的机器，为什么不能在生产环境中使用？” 他们可以简单地说，“它在 Docker 上运行”，因为打包的 Docker 应用程序可以在任何受支持的 Docker 环境中运行，并且它将按照预期的方式运行在所有部署目标上（开发，QA，暂存，生产等）。


![](./media/image3.png)

图 1-3： 传统 VM 与 Docker 容器的比较


>[!div class="step-by-step"]
[上一页](index.md)
[下一页](docker-terminology.md)
