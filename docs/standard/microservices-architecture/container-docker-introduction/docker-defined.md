---
title: "什么是 Docker？"
description: "为容器化的.NET 应用程序的.NET 微服务体系结构 |什么是 Docker？"
keywords: "Docker, 微服务, ASP.NET, 容器"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: aa9cb379628fa91e5dc5b1b529f92db98fa59305
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="what-is-docker"></a>什么是 Docker？

[Docker](https://www.docker.com/)是[开放源代码项目](https://github.com/docker/docker)用于自动执行与可以在云中或本地运行的可移植的足容器应用程序的部署。 Docker 也是[公司](https://www.docker.com/)，提升和发展此技术。 Docker 适用于与云，Linux 和 Windows 供应商，包括 Microsoft 的协作。

![](./media/image2.png)

**图 2-2**。 Docker 将部署在混合云中的所有层的容器

Docker 映像容器在 Linux 和 Windows 上本机运行。 仅在 Windows 主机上运行的 Windows 映像，并仅在 Linux 主机上运行的 Linux 映像。 主机是服务器或 VM。

你可以在 Windows、 Linux 或 macOS 上进行开发。 在开发计算机运行的 Docker 主机的 Docker 映像的部署位置，包括应用程序和其依赖项。 在 Linux 或 macOS 上，你使用的是 Linux 基础的可以创建仅针对 Linux 容器映像的 Docker 主机。（在 macOS 上你可以编辑代码，或运行 Docker CLI，但截至撰写本文时，容器不会运行直接在 macOS 上。）在 Windows 上，你可以为 Linux 或 Windows 容器创建映像。

在 Windows 或 macOS 上, [Docker 社区版 (CE)](https://www.docker.com/community-edition)承载在开发环境中的容器，并提供其他开发人员工具。 [Docker Enterprise Edition (EE)](https://www.docker.com/enterprise-edition)由 IT 团队生成、 提供，并运行大型业务关键型应用程序。 ~ 这两种产品安装需要的 VM （Docker 主机） 来承载容器。 ~ 

[Windows 容器](https://msdn.microsoft.com/en-us/virtualization/windowscontainers/about/about_overview)适用于两种类型的运行时：

-   Windows Server 容器提供通过进程和命名空间隔离技术的应用程序隔离。 Windows Server 容器与容器主机和与主机上运行的所有容器共享内核。

-   HYPER-V 容器 Windows Server 容器通过在高度优化的虚拟机中运行每个容器提供的隔离上扩展。 在此配置中，容器主机的内核不与 HYPER-V 容器，提供更好地隔离共享。 HYPER-V 容器允许不受信任和*恶意的多租户*同一主机上运行的应用程序。 HYPER-V 容器中启动的时间和比 Windows Server 容器密度的具有少效率。

适用于这些容器的映像的创建和功能相同的方式。 它们的区别在于如何创建容器。 有关详细信息，请参阅[HYPER-V 容器](https://msdn.microsoft.com/en-us/virtualization/windowscontainers/about/about_overview)。

## <a name="comparing-docker-containers-with-virtual-machines"></a>与虚拟机的比较 Docker 容器

图 2-3 显示的比较虚拟机和 Docker 容器。

  ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
  **虚拟机****Docker 容器** 
                                                                                                                                                                                        
  ![](./media/image3.png)                                                                                                                                ![](./media/image4.png)
                                                                                                                                                                                        
  虚拟机包括应用程序、 所需的库或二进制文件和完整的来宾操作系统。 完整的虚拟化需要比容器化的更多资源。 容器包括应用程序和其所有依赖项。 但是，容器与其他容器共享 OS 内核。 在主机操作系统上作为用户空间中的独立进程运行容器。 除非在 HYPER-V 容器，其中每个容器都在特定的虚拟机，每个容器内部运行。
  ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

**图 2-3**。 到 Docker 容器的传统虚拟机的比较

因为容器需要数量少得多的资源 （例如，它们不需要完整的 OS），快速启动并可轻松地部署。 资源使用率较低允许更高的密度。 您可以在相同的硬件单元上运行多个服务，并降低成本。

在相同的内核将导致不是虚拟机提供更少隔离上运行。

映像的主要目标是使其进行环境 （依赖关系） 相同跨不同的部署。 也就是说，你可以在您的计算机上进行调试它，然后使用相同的环境保证将其部署到另一台计算机。

容器映像是一种方法来打包的应用或服务并将其部署可靠且可重现的方式。 你可以假定，Docker 不只是一种技术，但还基本原理、 进程。

Docker 开发人员不要说，"It works 我在计算机上，不要在生产中？" 他们说，"上运行 Docker"。 Docker 打包应用程序可以在任何支持的 Docker 环境上执行。 Docker 封装在所有的部署目标 （开发、 QA、 过渡或生产） 上一致地运行的应用。

>[!div class="step-by-step"]
[以前](index.md) [下一步] (docker terminology.md)
