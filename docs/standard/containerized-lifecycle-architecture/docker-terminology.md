---
title: "Docker 术语"
description: "使用 Microsoft 平台和工具的容器化 Docker 应用程序的生命周期"
keywords: "Docker, 微服务, ASP.NET, 容器"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 09/21/2017
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: a622b2949c1d2277bb3e82617a5bc2d8cb432263
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/23/2017
---
# <a name="docker-terminology"></a>Docker 术语

本部分列出术语和定义与其应与你熟悉之前深入了解更深入地 Docker (有关进一步定义，请参阅对各种[术语表](https://docs.docker.com/glossary/)由在 Docker <https://docs.docker.com/glossary/>:

-   **容器映像** 的所有依赖关系和创建容器所需信息的包。 映像包括所有依赖项 （如框架） 以及部署和使用由容器运行时配置。 通常情况下，映像派生自多个基映像，层将堆积一个之上打开另一个用于窗体的容器的文件系统。 它已被创建后，映像是不可变。

-   **容器** Docker 映像的实例。 容器表示为单个应用程序、 进程或服务的运行时。 它包含的内容的 Docker 映像、 运行时环境和一组标准的说明。 缩放服务，当你从相同的映像创建多个容器实例。 或者，批处理作业可以从同一个映像，将不同的参数传递给每个实例创建多个容器。

-   **标记** 标记或标签，以便可以确定不同的映像或相同的映像 （具体取决于的版本号或目标环境） 的版本，可以应用于映像。

-   **Dockerfile** 文本文件，其中包含有关如何生成的 Docker 映像的说明。

-   **生成** 上的信息和上下文由其 Dockerfile，以及在其中生成映像的文件夹中的其他文件基于生成的容器映像的操作。 你可以通过使用 Docker docker 生成命令生成映像。

-   **存储库 （也称为存储库）** 相关的标记，该值指示映像版本标记为的 Docker 映像的集合。 某些存储库包含多个不同版本的特定映像，如包含映像包含仅运行时 （较亮） 的 Sdk （更大） 的映像，依此类推。 这些变体可以使用标记进行标记。 单个存储库可以包含平台的不同版本，如 Linux 映像和 Windows 映像。

-   **注册表** 提供对存储库的访问的服务。 大多数公共映像的默认注册表是[Docker Hub](https://hub.docker.com/) （归作为组织的 Docker）。 注册表通常包含多个团队从存储库。 通常，公司具有私有注册表来存储和管理他们创建的映像。 *Azure 容器注册表*是另一个示例。

-   **Docker Hub** 公共注册表将图像上载和使用它们。 Docker Hub 提供 Docker 映像托管、 公共或私有注册表，生成触发器和 web 挂钩，以及与 GitHub 和 Bitbucket 集成。

-   **Azure 容器注册表** 使用 Docker 映像和在 Azure 中的及其组件的公共资源。 这提供了的注册表，即将在 Azure 中部署和，它将授予控制访问权限，使其可以使用你的 Azure Active Directory 组和权限。

-   **Docker 受信任注册表 (DTR)** 可以安装的 Docker 注册表服务 （从 Docker) 本地，以便它位于内组织的数据中心和网络。 这将为应在企业内管理的专用映像方便。 Docker 受信任注册表是 Docker 数据中心产品的一部分包括。 有关详细信息，请转到[https://docs.docker.com/docker-trusted-registry/overview/](https://docs.docker.com/docker-trusted-registry/overview/)。

-   **Docker 社区版 (CE)** 适用于 Windows 和 macOS 有关生成、 运行和测试容器本地的开发工具。 CE 用于 Windows 的 docker 提供适用于 Linux 和 Windows 容器的开发环境。 在 Windows 上的 Linux Docker 主机基于[HYPER-V](https://www.microsoft.com/en-us/server-cloud/solutions/virtualization.aspx) VM。 为 Windows 容器主机直接基于 Windows。 适用于 Mac 的 docker CE 基于 Apple 虚拟机监控程序 framework 和[xhyve 虚拟机监控程序](https://github.com/mist64/xhyve)，提供了 Linux Docker 宿主 VM 上 Mac OS X.CE 用于 Windows 的 Docker 和适用于 Mac 替换 Docker 工具箱中，基于 Oracle VirtualBox。

-   **Docker Enterprise Edition (EE)** 企业级版本的 Linux 和 Windows 开发的 Docker 工具。

-   **撰写** 命令行工具和 YAML 文件元数据的定义和运行 multicontainer 应用程序的格式。 你可以定义单个应用程序基于与一个或多个可以重写值根据环境的.yml 文件的多个映像。 你已创建定义后，你可以使用单个命令部署整个 multicontainer 应用程序 (docker-向上撰写) 在 Docker 主机上创建每个图像的容器。

-   **群集** 分布在群集中的多个主机的 Docker 主机公开就像它们是一台虚拟 Docker 主机，以便应用程序可以扩展到服务的多个实例的集合。 你可以通过使用 Docker Swarm、 Mesosphere DC/OS、 Kubernetes 和 Azure Service Fabric 创建 Docker 群集。 (如果使用 Docker Swarm 进行管理的群集，你通常是指将群集作为*swarm*而不是群集。)

-   **Orchestrator** 简化了群集和 Docker 主机的管理工具。 使用 orchestrators，可以管理其映像、 容器和主机通过 CLI 或图形用户界面。 你可以管理容器网络、 配置、 负载平衡，服务发现、 高可用性，Docker 主机配置和的详细信息。 Orchestrator 负责运行、 分发、 缩放和跨节点集合的修复工作负荷。 通常情况下，orchestrator 产品是提供群集基础结构，如 Mesosphere DC/OS、 Kubernetes、 Docker Swarm，和 Azure Service Fabric 的同一个产品。


>[!div class="step-by-step"]
[Previous] (what-is-docker.md) [Next] (docker-containers-images-and-registries.md)
