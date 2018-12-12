---
title: Docker 术语
description: 使用 Microsoft 平台和工具的容器化 Docker 应用程序的生命周期
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 09/21/2017
ms.openlocfilehash: 1efb2fa567bd452f0a0a5ee5afb6f759511e4145
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2018
ms.locfileid: "53151300"
---
# <a name="docker-terminology"></a>Docker 术语

本部分列出了术语和定义与应与你熟悉在深入探讨更深层次 Docker 之前 (有关进一步的定义，请参阅广泛[词汇表](https://docs.docker.com/glossary/)提供的 Docker 在<https://docs.docker.com/glossary/>:

-   **容器映像** 具有的所有依赖项和创建容器所需信息的包。 映像包括所有依赖项 （例如框架） 以及部署和配置由容器运行时使用。 通常情况下，映像派生自多个基础映像，层上下堆积在另一个以形成容器的文件系统。 已创建后不可变映像。

-   **容器** Docker 映像的实例。 容器表示单个应用程序、 进程或服务运行时。 它包含的内容的 Docker 映像、 运行时环境中，以及一组标准的说明。 在缩放服务时，可以从相同的映像创建多个容器实例。 或者，批处理作业可以从同一个映像，将不同的参数传递给每个实例创建多个容器。

-   **标记** 的标记或标签，以便可以识别不同的映像或版本 （具体取决于版本号或目标环境） 的相同映像，可以应用于映像。

-   **Dockerfile** 包含有关如何生成 Docker 映像的说明的文本文件。

-   **构建** 上的信息和上下文由其 Dockerfile，以及生成映像的文件夹中的其他文件提供基于生成容器映像的操作。 可以通过使用 Docker docker 生成命令生成映像。

-   **存储库 （也称为存储库）** 带有指示映像版本标记相关的 Docker 映像的集合。 某些存储库包含多个变体的特定映像，如包含 Sdk （较重） 包含仅运行时 （较轻） 的图像的图像，等等。 这些变量可以使用标记进行标记。 单个存储库可以包含平台变量，如 Linux 映像和 Windows 映像。

-   **注册表** 提供存储库访问权限的服务。 大多数公共映像的默认注册表是 [Docker 中心](https://hub.docker.com/)（归作为组织的 Docker 所有）。 注册表通常包含来自多个团队的存储库。 公司通常使用私有注册表来存储和管理他们创建的映像。 *Azure 容器注册表*是另一个示例。

-   **Docker 中心** 公共注册表，以将图像上传和处理它们。 Docker 中心提供 Docker 映像托管、公共或私有注册表，生成触发器和 Web 挂钩，以及与 GitHub 和 Bitbucket 集成。

-   **Azure 容器注册表** 使用 Docker 映像和在 Azure 中的及其组件的公共资源。 这提供了接近 Azure 中部署的注册表，授予控制访问权限，使其可以使用 Azure Active Directory 组和权限。

-   **Docker 受信任注册表 (DTR)** 可以安装的 Docker 注册表服务 （来自 Docker) 在本地，以便其所在组织的数据中心和网络。 这对于应该在企业内部管理的私有映像来说很方便。 Docker 受信任注册表是 Docker 数据中心产品的一部分。 有关详细信息，请转到[ https://docs.docker.com/docker-trusted-registry/overview/ ](https://docs.docker.com/docker-trusted-registry/overview/)。

-   **Docker 社区版 (CE)** 适用于 Windows 和 macOS 在构建、 运行和测试本地容器开发工具。 适用于 Windows 的 Docker CE 为 Linux 和 Windows 容器提供了开发环境。 在 Windows 上的 Linux Docker 主机基于[HYPER-V](https://www.microsoft.com/en-us/server-cloud/solutions/virtualization.aspx) VM。 适用于 Windows 容器的主机直接基于 Windows。 适用于 Mac 的 docker CE 基于 Apple 虚拟机监控程序框架和[xhyve 虚拟机监控程序](https://github.com/mist64/xhyve)，其中提供了 Linux Docker 主机 VM，在 Mac OS x。 Docker CE 为 Windows 和 Mac 替换了 Docker 工具箱，后者基于 Oracle VirtualBox。

-   **Docker 企业版 (EE)** 适用于 Linux 和 Windows 开发的 Docker 工具企业级版本。

-   **撰写** 命令行工具和 YAML 文件用于定义和运行多容器应用程序的元数据的格式。 基于多个映像定义单个应用程序，其中包含一个或多个 .yml 文件，这些文件可以根据环境替代值。 你已创建定义后，可以使用单个命令部署整个多容器应用程序 (docker-compose up) 的 Docker 主机上创建每个映像的容器。

-   **群集** 的 Docker 主机公开就像单个虚拟 Docker 主机，以便应用程序可以扩展到多个实例的服务集合分布到群集内的多个主机。 可以通过使用 Docker Swarm、 Mesosphere DC/OS、 Kubernetes 和 Azure Service Fabric 创建 Docker 群集。 （如果使用 Docker Swarm 来管理群集，通常是指将群集作为 swarm 而不是群集。）

-   **业务流程协调程序** 简化了群集和 Docker 主机的管理工具。 使用业务流程协调程序，可以管理其映像、 容器和主机通过 CLI 或图形用户界面。 可以管理容器网络、配置、负载均衡、服务发现、高可用性、Docker 主机配置等。 业务流程协调程序负责跨节点集合运行、分发、缩放和修复工作负荷。 通常情况下，业务流程协调程序产品是提供群集基础结构的同一产品，如 Mesosphere DC/OS、Kubernetes、Docker Swarm 和 Azure Service Fabric。

>[!div class="step-by-step"]
>[上一页](what-is-docker.md)
>[下一页](docker-containers-images-and-registries.md)