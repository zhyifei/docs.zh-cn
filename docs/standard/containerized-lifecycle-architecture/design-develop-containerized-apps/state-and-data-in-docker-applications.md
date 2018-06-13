---
title: Docker 应用程序中的状态和数据
description: 使用 Microsoft 平台和工具的容器化 Docker 应用程序的生命周期
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 09/22/2017
ms.openlocfilehash: b27be902779c7e22a568c679362851f745ea494d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33569676"
---
# <a name="state-and-data-in-docker-applications"></a>Docker 应用程序中的状态和数据

容器的基元是不可变性。 与 VM 相比，容器不会消失，作为一种常见情况。 在从死进程、 重载的 CPU 或完整或失败的磁盘的各种窗体中，VM 可能会失败。 但，我们希望在虚拟机可用并 RAID 驱动器是司空见惯以确保驱动器故障维护数据。

但是，容器是认为要是进程的实例。 进程不会继续持久状态。 即使一个容器可以写入其本地存储，假设，该实例都将围绕无限期地将等效于假定单复制内存将持久。 您应假定复制的容器，如进程，终止，或当使用容器 orchestrator 管理，则可能会将它们移。

Docker 使用一个称作功能*覆盖文件系统*来实现写入时复制流程存储任何更新信息到根文件系统中的容器，相比所基于的原始映像。 如果随后从系统中删除容器，这些更改将丢失。 一个容器，因此，不默认不具有持久存储。 但也可以保存容器的状态，设计解决此系统将为与容器体系结构原则冲突。

若要管理 Docker 应用程序中的持久性数据，还有常见解决方案：

-   [**数据卷**](https://docs.docker.com/engine/tutorials/dockervolumes/) 这些装载到刚设定的主机。

-   [**数据卷容器**](https://docs.docker.com/engine/tutorials/dockervolumes/#/creating-and-mounting-a-data-volume-container) 这些跨容器，使用可以循环外部容器提供共享的存储。

-   [**卷插件**](https://docs.docker.com/engine/tutorials/dockervolumes/#/mount-a-shared-storage-volume-as-a-data-volume) 这些装载到远程位置，提供长期的持久性的卷。

-   **远程数据源** 示例包括 SQL 和非 SQL 数据库或缓存 Redis 等服务。

-   [**Azure 存储**](https://docs.microsoft.com/azure/storage/) 这提供异地可分发平台即服务 (PaaS) 存储，提供容器的最佳为长期的持久性。

数据卷专门指定在跳过的一个或多个容器内的目录[联合的文件系统](https://docs.docker.com/v1.8/reference/glossary#union-file-system)。 数据卷用于维护数据，独立于容器的生命周期。 Docker 因此永远不会自动删除卷时您删除容器，也不能将它不再引用的容器的"垃圾收集"卷。 主机操作系统可以浏览和编辑中的任何卷的数据自由，这是另一个原因应谨慎使用数据卷。

A[数据卷容器](https://docs.docker.com/v1.8/userguide/dockervolumes/)是对常规数据卷的改进。 它是实质上是具有一个或多个数据卷 （如前面所述），在其中创建的休眠的容器。 数据卷容器从中央装入点提供对容器的访问。 访问此方法的好处是它提取原始数据，进行逻辑装入点的数据容器的位置。 它还允许访问数据容器卷以创建和销毁时将数据保存在专用的容器中持久保留的"应用程序"容器。

图 4-5 显示正则 Docker 卷可以置于存储容器本身外，但在主机服务器/VM 物理边界内。 *Docker 卷没有使用到另一台主机服务器/虚拟机从卷的能力*。

![](./media/image5.png)

图 4-5： 数据量和容器应用程序/容器的外部数据源

由于管理在单独的物理主机运行的容器之间共享的数据，建议你不使用卷业务数据除非 Docker 主机已固定的主机/VM，因为在 orchestrator 中使用 Docker 容器时容器应介于 1 到另一台主机，具体取决于要由群集执行的优化移动。

因此，正则数据卷的合适的机制用于跟踪文件、 临时文件或任何类似的概念，或如果你的容器将跨多个主机时并不影响业务数据一致性。

卷插件喜欢[Flocker](https://clusterhq.com/flocker/)跨群集中的所有主机提供数据。 尽管不是所有卷插件都是相同的卷插件通常会提供外部化持久的可靠存储来自不可变的容器。

远程数据源和类似 SQL 数据库、 DocumentDB、 或远程如 Redis 缓存的缓存可能与开发而容器没有相同。 这是一种的首选方法，并经过验证，以存储业务应用程序数据。


>[!div class="step-by-step"]
[以前] (monolithic-applications.md) [下一步] (soa-applications.md)
