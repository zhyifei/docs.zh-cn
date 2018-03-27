---
title: 在生产环境中运行由和基于微服务的应用程序
description: 使用 Microsoft 平台和工具的容器化 Docker 应用程序的生命周期
keywords: Docker, 微服务, ASP.NET, 容器
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 09/22/2017
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 0d7611d07c9995984269e3f7b071154d9b861367
ms.sourcegitcommit: c883637b41ee028786edceece4fa872939d2e64c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/26/2018
---
# <a name="run-composed-and-microservices-based-applications-in-production-environments"></a>在生产环境中运行由和基于微服务的应用程序

由多个微服务的应用程序需要将其部署到 orchestrator 群集为了简化部署的复杂性和使其从 IT 角度来看可行。 如果 orchestrator 群集中，没有它将是部署和向外扩展复杂微服务应用程序非常困难。

## <a name="introduction-to-orchestrators-schedulers-and-container-clusters"></a>Orchestrators、 计划程序时和容器群集简介

前面的此电子书，我们引入了*群集*和*计划程序*上软件体系结构和开发的讨论的一部分。 Docker 群集的示例包括 Docker Swarm 和 Mesosphere 的数据中心操作系统 (DC/OS)。 这两个可以作为 Microsoft Azure 容器服务提供的基础结构的一部分运行。

当应用程序是向外扩展的跨多个主机系统时，管理每个主机系统和抽象化基础平台的复杂性的能力变得极具吸引力。 这就确切地说是 orchestrators 和计划程序提供的内容。 看看简要此处所示：

-   **计划程序 * * * *"计划"指的管理员可以将服务文件加载到建立如何运行特定容器的主机系统的能力。 启动 Docker 群集中的容器往往会被称为计划。 虽然计划针对加载的更多常规的意义上中的服务定义的特定行为的是计划程序负责将挂钩到主机的 init 系统中任何所需的容量的服务进行管理。

一个群集计划程序有多个目标： 有效地使用群集的资源，使用用户提供的放置约束，计划应用程序快速不将它们保留在挂起状态，具有在一定程度"的公平性，"正在可靠的错误，并始终为可用。

-   **业务流程 * * * *平台扩展到部署在主机群集上的复杂、 multicontainer 工作负荷的生命周期管理功能。 通过使宿主基础结构的抽象化，业务流程工具将向用户授予了如何将整个群集视为单个部署目标。

业务流程的过程包括工具和一个平台，它可以自动执行的应用程序管理从初始放置或每个容器; 的部署的所有方面将容器移动到不同的主机，具体取决于其主机的运行状况或性能;版本控制和滚动更新以及运行状况监视功能的支持缩放和故障转移;还有更多。

Orchestration 是广泛的术语，表示与容器计划、 群集管理和可能设置的其他主机。

提供 orchestrators 和计划程序的功能很非常复杂，开发并从从头开始创建，因此你通常想要使由供应商提供的业务流程解决方案使用。


>[!div class="step-by-step"]
[以前](index.md) [下一步] (管理-生产-docker-environments.md)
