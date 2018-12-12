---
title: Docker 应用程序中的状态和数据
description: 使用 Microsoft 平台和工具的容器化 Docker 应用程序的生命周期
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 09/22/2017
ms.openlocfilehash: 7454b25cdb1bede87c6f0bd179fcabd489922263
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2018
ms.locfileid: "53154172"
---
# <a name="state-and-data-in-docker-applications"></a>Docker 应用程序中的状态和数据

容器的基元是不可变性。 与 VM 相比，容器将不会作为一种常见情况消失。 在从死信进程、 重载的 CPU 或完整或失败的磁盘的各种窗体中，VM 可能会失败。 我们希望在可用的 VM 和 RAID 驱动器来确保驱动器故障维护的数据。

但是，容器被认为是非进程的实例。 进程不维护持久状态。 即使容器可以写入其本地存储，假定将无限期地将围绕该实例将等效于假定单副本内存将持久。 您应假定复制的容器与进程一样，，已终止，或者，当托管容器业务流程协调程序时，可能会将它们移动。

Docker 使用一项功能称为*覆盖文件系统*实现写入时复制过程，用于存储任何更新信息到容器，相比原始映像所基于的根文件系统。 如果随后从系统删除该容器，这些更改将丢失。 一个容器，因此，不具有持久性存储区默认情况下。 尽管可以保存容器的状态，但设计系统解决此问题是与容器体系结构原则冲突。

若要管理 Docker 应用程序中的持久性数据，还有常见解决方案：

-   [**数据卷**](https://docs.docker.com/engine/tutorials/dockervolumes/) 这些装载到主机，只需特别说明。

-   [**数据卷容器**](https://docs.docker.com/engine/tutorials/dockervolumes/#/creating-and-mounting-a-data-volume-container) 这些跨容器，使用可以循环的外部容器提供共享的存储。

-   [**卷插件**](https://docs.docker.com/engine/tutorials/dockervolumes/#/mount-a-shared-storage-volume-as-a-data-volume) 这些卷装载到远程位置，提供持久性。

-   **远程数据源** 示例包括 SQL 数据库和无 SQL 数据库或缓存服务，如 Redis。

-   [**Azure 存储**](https://docs.microsoft.com/azure/storage/) 这提供异地可分发平台即服务 (PaaS) 存储，提供最佳的容器为持久性。

数据卷被专门指定跳过的一个或多个容器内的目录[联合的文件系统](https://docs.docker.com/glossary/?term=Union%20file%20system)。 数据卷用于维护数据，独立于容器的生命周期。 Docker 因此永远不会自动删除卷时您删除容器，也不能将它不再引用的容器的"垃圾收集"的卷。 主机操作系统可以浏览和编辑任何卷中的数据公开发布，这是尽量少使用的数据卷的只是另一个原因。

一个[数据卷容器](https://docs.docker.com/glossary/?term=volume)是对常规数据卷的改进。 实质上是处于休眠状态容器具有一个或多个数据卷 （如前面所述），在其中创建它。 数据卷容器从中央装入点提供对容器的访问。 访问此方法的优点是它抽象出原始数据，使逻辑装入点的数据容器的位置。 它还允许访问的数据容器卷来创建和销毁时将数据保存在专用容器中持久保留的"应用程序"容器。

图 4-5 显示了常规 Docker 卷可以置于存储超出容器本身，但在主机服务器/VM 物理边界内。 *Docker 卷不能使用到另一个将卷从一台主机服务器/VM*。

![](./media/image5.png)

图 4-5:数据卷和用于容器的应用/容器的外部数据源

因为无法管理在单独的物理主机运行的容器之间共享的数据，建议不使用卷用于业务数据除非 Docker 主机是固定的主机/VM，因为在业务流程协调程序中使用 Docker 容器时容器应介于 1 到另一台主机，具体取决于要由群集执行的优化移动。

因此，常规数据卷是一个良好的机制用于跟踪文件、 临时文件或任何类似的概念，并不影响业务数据一致性，如果或跨多个主机移动用户的容器。

[卷插件](https://docs.docker.com/engine/extend/plugins_volume/)跨群集中的所有主机提供的数据。 尽管并非所有卷插件都是相同的但卷插件通常提供外部化不可变的容器中的持久可靠存储。

远程数据源和 SQL 数据库、 DocumentDB、 或的远程如 Redis 缓存等缓存应该是与开发不带容器相同。 这是一种首选方法，且经实践证明的业务应用程序数据存储。

>[!div class="step-by-step"]
>[上一页](monolithic-applications.md)
>[下一页](soa-applications.md)