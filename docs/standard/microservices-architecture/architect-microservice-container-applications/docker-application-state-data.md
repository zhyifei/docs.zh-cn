---
title: Docker 应用程序中的状态和数据
description: 适用于容器化 .NET 应用程序的 .NET 微服务体系结构 | Docker 应用程序中的状态和数据
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/18/2017
ms.openlocfilehash: 1469038af29167f7dbb1a161b951eee742cf4bec
ms.sourcegitcommit: 979597cd8055534b63d2c6ee8322938a27d0c87b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/29/2018
ms.locfileid: "37105613"
---
# <a name="state-and-data-in-docker-applications"></a>Docker 应用程序中的状态和数据

在大多数情况下，可以将容器视为进程的实例。 进程不维护持久状态。 虽然容器可以写入其本地存储，但假设一个实例将无限期地存在，就像假设内存中的单个位置将是持久的一样。 与进程一样，容器映像应该被假定有多个实例，或它们最终将会终止；如果它们是用容器业务流程协调程序管理的，那么应该假定它们可能从一个节点或 VM 移动到另一个节点或 VM。

Docker 提供一个名为“覆盖文件系统”的功能。 这实现了写入时复制任务，该任务将更新后的信息存储到容器的根文件系统中。 该信息是容器所基于的原始映射之外的信息。 如果从系统中删除容器，则这些更改将丢失。 因此，虽然可以在其本地存储中保存容器的状态，但围绕这一点设计一个系统将与容器设计的前提相冲突，而容器设计在默认情况下是无状态的。

以下解决方案用于管理 Docker 应用程序中的持久性数据：

-   装载到主机的[数据卷](https://docs.docker.com/engine/tutorials/dockervolumes/)。

-   使用外部容器提供跨容器共享存储的[数据卷容器](https://docs.docker.com/engine/tutorials/dockervolumes/#creating-and-mounting-a-data-volume-container)。

-   将卷装载到远程服务以提供持久性的[卷插件](https://docs.docker.com/engine/tutorials/dockervolumes/)。

-   [Azure 存储](https://docs.microsoft.com/azure/storage/)，提供可异地分发存储，为容器提供良好的持久性解决方案。

-   远程关系数据库（如 [Azure SQL 数据库](https://azure.microsoft.com/services/sql-database/)）或 NoSQL 数据库（如 [Azure Cosmos DB](https://docs.microsoft.com/azure/cosmos-db/introduction)）或缓存服务（如 [Redis](https://redis.io/)）。

下面提供了有关这些选项的更多详细信息。

数据卷是从主机操作系统映射到容器中目录的目录。 当容器中的代码访问该目录时，该访问实际上是对主机操作系统上的一个目录的访问。 此目录不与容器本身的生存期相关联，并且可以通过直接在主机操作系统上运行的代码或将同一主机目录映射到自身的另一个容器访问该目录。 因此，数据卷用于将独立于容器的生命周期的数据持久保存。 如果从 Docker 主机中删除容器或图像，不会删除数据卷中保留的数据。 也可以从主机操作系统访问卷中的数据。

数据卷容器是常规数据卷的演变。 数据卷容器是一个简单的容器，其中包含一个或多个数据卷。 数据卷容器从中央装入点提供对容器的访问。 这种数据访问方法由于提取了原始数据的位置，因而更方便。 除此之外，其行为类似于常规数据卷，因此数据独立于应用程序容器的生命周期，保留于此专用容器中。

如图 4-5 所示，常规 Docker 卷可以存储在容器本身之外，但是在主机服务器或 VM 的物理边界内。 但是，Docker 容器不能从一个主机服务器或 VM 访问另一个主机服务器或 VM 的卷。 换而言之，使用这些卷，不能用于管理在不同的 Docker 主机运行的容器之间共享的数据

![](./media/image5.png)

**图 4-5**。 基于容器的应用程序的数据卷和外部数据源

此外，当 Docker 容器由业务流程协调程序管理时，容器可能会在主机之间“移动”，这取决于集群所执行的优化。 因此，不建议将数据卷用于业务数据。 但它们是一种良好的机制，可以处理跟踪文件、时态文件或类似的不会影响业务数据一致性的文件。

卷插件（如 [Flocker](https://clusterhq.com/flocker/)）提供了集群中所有主机的数据访问。 虽然并非所有卷插件都是相同的，但卷插件通常从不可变的容器中提供外部化的持久可靠存储。

远程数据源和缓存工具（如 Azure SQL 数据库、Azure Cosmos DB）或远程缓存（如 Redis）可以在容器化应用程序中使用，与开发时没有容器的使用方式相同。 这是存储业务应用程序数据的一种行之有效的方法。

Azure 存储。 业务数据通常需要放在外部资源或数据库中，如 Azure 存储。 Azure 存储在云中具体提供以下服务：

-   Blob 存储存储非结构化的对象数据。 Blob 可以是任何类型的文本或二进制数据，如文档或媒体文件（图像、音频和视频文件）。 Blob 存储也称为对象存储。

-   文件存储为使用标准 SMB 协议的旧版应用程序提供共享存储。 Azure 虚拟机和云服务可以通过装载的共享在应用程序组件之间共享文件数据。 本地应用程序可以通过文件服务 REST API 访问共享中的文件数据。

-   表存储存储结构化数据集。 表存储是 NoSQL 键属性数据存储，它允许快速开发和快速访问大量数据。

关系数据库和 NoSQL 数据库。 外部数据库有很多选择，包括关系数据库（如 SQL Server、PostgreSQL、Oracle）或 NoSQL 数据库（如 Azure Cosmos DB、MongoDB）等。这些数据库将不会作为本指南的一部分加以解释，因为它们在一个完全不同的主题中。


>[!div class="step-by-step"]
[上一页](containerize-monolithic-applications.md)
[下一页](service-oriented-architecture.md)
