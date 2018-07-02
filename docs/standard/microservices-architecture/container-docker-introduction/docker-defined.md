---
title: 什么是 Docker？
description: 适用于容器化 .NET 应用程序的 .NET 微服务体系结构 | 什么是 Docker？
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.openlocfilehash: 06dd5199b8dbc42ce3e9ae35bc5c3673d01cb4de
ms.sourcegitcommit: 979597cd8055534b63d2c6ee8322938a27d0c87b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/29/2018
ms.locfileid: "37106796"
---
# <a name="what-is-docker"></a>什么是 Docker？

[Docker](https://www.docker.com/) 是一种[开源项目](https://github.com/docker/docker)，用于将应用程序自动部署为可在云或本地运行的便携式独立容器。 Docker 也是一家促进和发展这项技术的[公司](https://www.docker.com/)。 Docker 与云，Linux 和 Windows 供应商（包括 Microsoft）协作。

![](./media/image2.png)

**图 2-2**。 Docker 在混合云的所有层部署容器

Docker 映像容器在 Linux 和 Windows 上本机运行。 Windows 映像仅在 Windows 主机上运行，Linux 映像仅在 Linux 主机上运行。 主机指服务器或 VM。

可以在 Windows、Linux 或 macOS 上进行开发。 开发计算机运行部署了 Docker 映像（包括应用及其依赖项）的 Docker 主机。 在 Linux 或 macOS 上，使用基于 Linux 的 Docker 主机，并且只能为 Linux 容器创建映像。（在 macOS 上可以编辑代码或运行 Docker CLI，但在撰写本文时，容器不会直接在 macOS 上运行。）在 Windows 上，可以为 Linux 或 Windows 容器创建映像。

在 Windows 或 macOS 上，[Docker 社区版 (CE)](https://www.docker.com/community-edition) 在开发环境中承载容器，并提供其他开发人员工具。 [Docker 企业版 (EE)](https://www.docker.com/enterprise-edition) 由生成、交付和运行大型业务关键应用程序的 IT 团队使用。 ~这两种产品都安装了承载容器所需的 VM（Docker 主机）。~ 

[Windows 容器](https://msdn.microsoft.com/en-us/virtualization/windowscontainers/about/about_overview)适用于两种类型的运行时：

-   Windows Server 容器通过进程和命名空间隔离技术提供应用程序隔离。 Windows Server 容器与容器主机和主机上运行的所有容器共享内核。

-   Hyper-V 容器通过在高度优化的虚拟机中运行各容器来扩展 Windows Server 容器提供的隔离。 在此配置中，容器主机的内核不与 Hyper-V 容器共享，以提供更好地隔离。 Hyper-V 容器允许不受信任和恶意的多租户应用程序在同一主机上运行。 与 Windows Server 容器相比，Hyper-V 容器在启动时间和密度方面的效率要低一些。

这些容器的映像的创建和运行方式均相同。 它们的区别在于创建容器的方式。 有关详细信息，请参阅 [Hyper-V 容器](https://msdn.microsoft.com/en-us/virtualization/windowscontainers/about/about_overview)。

## <a name="comparing-docker-containers-with-virtual-machines"></a>比较 Docker 容器和虚拟机

图 2-3 显示了 VM 和 Docker 容器之间的比较。

  ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
  **虚拟机**                                                                                                                                                                  **Docker 容器**
                                                                                                                                                                                        
  ![](./media/image3.png)                                                                                                                                ![](./media/image4.png)
                                                                                                                                                                                        
  虚拟机包括应用程序、必需的库或二进制文件以及完整的来宾操作系统。 与比容器化相比，完全虚拟化需要更多资源。 容器包括应用程序及其所有依赖项。 但是，容器与其他容器共享 OS 内核。 容器作为主机操作系统上用户空间中的隔离进程运行。 Hyper-V 容器例外，其中的每个容器都在各容器特定虚拟机内部运行。
  ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

**图 2-3**。 比较传统虚拟机与 Docker 容器

由于容器所需的资源要少得多（例如，它们不需要一个完整的 OS），所以它们启动速度快且易于部署。 资源使用率较低，因此密度更高。 可以在同一硬件单元上运行更多服务并降低成本。

与 VM 相比，在同一内核上运行所提供的隔离更少。

映像的主要目标是使环境（依赖项）在不同的部署中保持不变。 也就是说，可以在计算机上调试它，然后将其部署到保证具有相同环境的另一台计算机上。

借助容器映像，可打包应用或服务并采用可靠且可重现的方式对其进行部署。 可以说 Docker 不只是一种技术，还是一种原理和过程。

Docker 开发人员不会说：“为什么它能在我的计算机上运行却不能在生产中运行？” 而会说：“它在 Docker 上运行”。 Docker 打包的应用可以在任何支持的 Docker 环境上执行。 Docker 打包的应用在所有部署目标（开发、质量保证、暂存、生产）上运行一致。

>[!div class="step-by-step"]
[上一页](index.md)
[下一页](docker-terminology.md)
