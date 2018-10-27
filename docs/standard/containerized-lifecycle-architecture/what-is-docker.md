---
title: 什么是 Docker？
description: 使用 Microsoft 平台和工具的容器化 Docker 应用程序的生命周期
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 09/21/2017
ms.openlocfilehash: 056fb613c078cc407380060dc11890406ac8cffd
ms.sourcegitcommit: 9bd8f213b50f0e1a73e03bd1e840c917fbd6d20a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/25/2018
ms.locfileid: "50044725"
---
# <a name="what-is-docker"></a>什么是 Docker？

[Docker](https://www.docker.com/)是[开放源代码项目](https://github.com/docker/docker)用于将自动为可以在云或本地运行的可移植的独立容器的应用程序部署 (请参阅图 1-2）。 Docker 也是[公司](https://www.docker.com/)促进和发展这项技术，与云，Linux 和 Windows 供应商，包括 Microsoft 协作。

![](./media/image2.png)

图 1-2: Docker 部署混合云的所有层的容器

Docker 映像容器可以在 Linux 和 Windows 上本机运行。 但是，仅在 Windows 主机上可以运行 Windows 映像和 Linux 映像可以仅在 Linux 主机，这意味着主机服务器或 VM 上运行。

开发人员可以在 Windows、Linux 或 macOS 上使用开发环境。 在开发计算机上，开发人员在运行到哪个 Docker 映像部署，包括应用程序和其依赖项的 Docker 主机。 在 Linux 或 Mac 上进行开发的开发人员使用基于 Linux 的 Docker 主机，并且他们可以仅为 Linux 容器创建映像。 (在 Mac 上工作的开发人员可以编辑代码或运行 Docker 命令行接口\[CLI\]从 macOS，但是，在撰写本文时，容器不直接在 macOS 上运行。)在 Windows 上进行开发的开发人员可以为 Linux 或 Windows 容器创建映像。

为了在开发环境中承载容器，并提供其他开发人员工具，Docker 为 Windows 或 macOS 提供了 [Docker 社区版 (CE)](https://www.docker.com/community-edition)。 这些产品安装了承载容器所需的 VM（Docker 主机）。 Docker 还提供 [Docker 企业版 (EE)](https://www.docker.com/enterprise-edition)，该版本专为企业开发而设计，供生成、交付和在生产中运行大型业务关键型应用程序的 IT 团队使用。

若要运行 [Windows 容器](/virtualization/windowscontainers/about/)，有两种类型的运行时可供使用：

-   **Windows Server 容器** 此运行时提供应用程序通过进程和命名空间隔离技术隔离。 Windows Server 容器与容器主机和主机上运行的所有容器共享内核。

-   **HYPER-V 容器** 这会提供由 Windows Server 容器通过在高度优化的 VM 中运行每个容器的隔离上扩展。 在此配置中，容器主机的内核不与 Hyper-V 容器共享，以提供更好地隔离。

这些容器的映像创建相同的方式，并在功能上相同。 区别在于如何从映像创建容器-运行 HYPER-V 容器需要一个额外的参数。 有关详细信息，请参阅 [Hyper-V 容器](/virtualization/windowscontainers/about/)。

## <a name="comparing-docker-containers-with-vms"></a>比较 Docker 容器和 Vm

图 1-3 显示了比较虚拟机和 Docker 容器。

由于容器所需数量少得多的资源 （例如，它们不需要完整的操作系统），因此可以轻松部署和它们启动速度快。 这使你能够在更高的密度，这意味着你可以运行在同一硬件单元，从而降低成本的更多服务。

运行于同一个内核上产生了负面影响，您实现比 Vm 隔离更少。

映像的主要目标是使环境（依赖项）在不同的部署中保持不变。 也就是说，可以在计算机上调试它，然后将其部署到保证具有相同环境的另一台计算机上。

容器映像是一种方法来打包的应用或服务并将其部署可靠且可重现的方式。 在这一方面，Docker 不是只有一种技术，它也是一种原理和过程。

使用 Docker 时，您将听不到开发人员说，"适用于我的计算机，为什么不在生产环境中？" 他们可以只是说，"它在 Docker 上运行，"因为打包的 Docker 应用程序可以在任何受支持的 Docker 环境上运行，并且它将重新运行安装程序对所有部署目标 （开发、 QA、 暂存、 生产等。） 使用的方式运行。

![](./media/image3.png)

图 1-3： 比较的传统 Vm 到 Docker 容器


>[!div class="step-by-step"]
[上一页](index.md)
[下一页](docker-terminology.md)
