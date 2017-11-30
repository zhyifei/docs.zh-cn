---
title: "状态和 Docker 应用程序中的数据"
description: "为容器化的.NET 应用程序的.NET 微服务体系结构 |状态和 Docker 应用程序中的数据"
keywords: "Docker 微服务、 ASP.NET、 容器、 SQL、 CosmosDB、 Docker"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/18/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: 36d0fb9f27ef56b36c380e2fc972c79cff77003e
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/22/2017
---
# <a name="state-and-data-in-docker-applications"></a>状态和 Docker 应用程序中的数据

在大多数情况下，你可以将作为进程的实例的容器。 进程不维护持久状态。 容器可以写入其本地存储，而假定，实例都将围绕无限期地将将如下假设将持久内存中的单个位置。 应假定容器映像，如进程，拥有多个实例，或它们将最终终止;如果这些与容器 orchestrator 管理，它应假定，它们可能获取从一个节点或 VM 之间移动。

Docker 提供了一个名为功能*覆盖文件系统*。 这将实现存储到根文件系统容器的更新信息写入时复制任务。 该信息是此外到容器所基于的原始映像中。 如果从系统中删除容器，这些更改将丢失。 因此，虽然可能用于保存其本地存储中的容器的状态，但设计解决此系统与容器设计，它们的默认值是无状态的本地行冲突。

以下解决方案用于管理 Docker 应用程序中的持久性数据：

-   [数据卷](https://docs.docker.com/engine/tutorials/dockervolumes/)，装载到主机。

-   [数据卷容器](https://docs.docker.com/engine/tutorials/dockervolumes/#creating-and-mounting-a-data-volume-container)，在使用外部容器的容器内提供共享的存储。

-   [卷插件](https://docs.docker.com/engine/tutorials/dockervolumes/)装载卷，向远程服务，并提供长期的持久性。

-   [Azure 存储](https://docs.microsoft.com/azure/storage/)，它提供可异地分发存储，为容器提供很好的长期持久性解决方案。

-   远程关系数据库喜欢[Azure SQL 数据库](https://azure.microsoft.com/services/sql-database/)或 NoSQL 数据库，例如[Azure Cosmos DB](https://docs.microsoft.com/azure/cosmos-db/introduction)，或缓存服务，如[Redis](https://redis.io/)。

下面提供了有关这些选项的更多详细信息。

**数据卷**的主机操作系统从映射到容器中的目录的目录。 当容器中的代码有权访问实际上是为主机操作系统上的目录的目录。 此目录不绑定到的容器本身的生存期和可以直接在主机操作系统上运行的代码访问目录或通过另一个容器，可以将相同的主机目录映射到其自身。 因此，数据卷用于将独立于容器的生命周期的数据持久保存。 如果删除容器，或将图像从 Docker 主机，数据保留在数据量不会删除。 可以从主机操作系统以及访问在卷中的数据。

**数据卷容器**是演变而来的常规数据卷。 数据卷容器是具有在其中的一个或多个数据卷的简单容器。 通过中央装入点还原时，数据卷容器提供对容器的访问。 数据访问此方法是方便，因为它提取原始数据的位置。 除此之外，其行为是类似于常规数据卷，其中，使数据保持独立应用程序的容器的生命周期于此专用容器中。

如所示在图 4-5 中，在容器本身之外，但主机服务器或 VM 的物理边界内，也可以存储正则 Docker 卷。 但是，Docker 容器无法访问卷从一台主机服务器或 VM 到另一个。 换而言之，使用这些卷，不能用于管理在不同的 Docker 主机运行的容器之间共享的数据

![](./media/image5.png)

**图 4-5**。 数据卷和容器基于应用程序的外部数据源

此外，当通过 orchestrator 管理 Docker 容器时，容器可能""主机之间移动，具体取决于由群集执行的优化。 因此，不建议你使用的数据卷业务数据。 但它们是一种良好的机制，可以使用跟踪文件、 临时文件、 或类似，不会影响业务数据一致性。

**卷插件**如[Flocker](https://clusterhq.com/flocker/)跨群集中的所有主机提供数据访问。 而不是所有的卷插件都是相同的则卷插件通常提供外部化持久的可靠存储来自不可变的容器。

**远程数据源和缓存**工具，如 Azure SQL 数据库、 Azure Cosmos DB 或远程的缓存，如 Redis 可在容器应用程序相同的方式在没有容器的情况下开发时使用它们。 这是一种经过验证的方式来存储业务应用程序数据。

**Azure 存储空间。** 业务数据通常将需要放置外部资源或数据库，如 Azure 存储空间中。 具体中的 azure 存储提供了以下服务在云中：

-   Blob 存储存储非结构化的对象数据。 Blob 可以是任何类型的文本或二进制数据，如文档或媒体文件 （图像、 音频和视频文件）。 Blob 存储也称为对象存储。

-   文件存储为提供共享的存储使用标准 SMB 协议的旧版应用程序。 Azure 虚拟机和云服务可以在通过装载的共享的应用程序组件之间共享文件数据。 在本地应用程序可以访问通过文件服务 REST API 的共享中的文件数据。

-   表存储存储结构化数据集。 表存储是 NoSQL 键-属性数据存储，这将允许快速开发和快速访问大量数据。

**关系数据库和 NoSQL 数据库。** 有多种可供选择的外部数据库，从关系数据库，如 SQL Server、 PostgreSQL、 Oracle 或 NoSQL 数据库，如 Azure Cosmos DB、 MongoDB 等。这些数据库不会被解释为本指南的一部分，因为它们在完全不同的使用者。


>[!div class="step-by-step"]
[以前](化-整体-applications.md) [下一步] (服务-面向-architecture.md)
