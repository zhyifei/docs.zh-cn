---
title: 体系结构部署方法-无服务器应用
description: 在 IaaS、PaaS、容器和无服务器之间进行比较时，可通过不同方式将企业体系结构部署到云中。
author: JEREMYLIKNESS
ms.author: jeliknes
ms.date: 06/26/2018
ms.openlocfilehash: 4cc8442509fc8a0e2cc0eb797365423458e77684
ms.sourcegitcommit: 8a0fe8a2227af612f8b8941bdb8b19d6268748e7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/03/2019
ms.locfileid: "71834340"
---
# <a name="architecture-deployment-approaches"></a>体系结构部署方法

无论用于设计业务应用程序的体系结构方法是什么，实现或这些应用程序的部署可能会有所不同。 企业从物理硬件到无服务器的功能托管应用程序。

## <a name="n-tier-applications"></a>N 层应用程序

[N 层体系结构模式](https://docs.microsoft.com/azure/architecture/guide/architecture-styles/n-tier)是一种成熟的体系结构，只是指将各种逻辑层分为单独的物理层的应用程序。 N 层体系结构是 N 层体系结构的物理实现。 此体系结构的最常见实现包括：

* 表示层，例如 web 应用。
* API 或数据访问层，如 REST API。
* 数据层，如 SQL 数据库。

![N 层体系结构](./media/n-tier-architecture.png)

N 层解决方案具有以下特征：

* 项目通常与层对齐。
* 层的测试可能以不同的方式进行。
* 层提供抽象层，例如，表示层通常未知的是数据层的实现细节。
* 通常，层只与相邻层交互。
* 版本通常在项目中进行管理，并因此进行层级管理。 简单的 API 更改可能需要整个中间层的新版本。

此方法具有多项优势，包括：

* 数据库的隔离（通常是前端不能直接访问数据库后端）。
* 重新使用 API （例如，移动、桌面和 web 应用客户端可以重复使用相同的 Api）。
* 相互独立地扩展层的能力。
* 重构隔离：可以重构一个层，而不会影响其他层。

## <a name="on-premises-and-infrastructure-as-a-service-iaas"></a>本地和基础结构即服务（IaaS）

托管应用程序的传统方法需要购买硬件，并管理所有软件安装（包括操作系统）。 最初，这涉及到昂贵的数据中心和物理硬件。 操作物理硬件附带的难题包括：

* 需要购买额外的 "以防万一" 或峰值需求方案。
* 保护对硬件的物理访问。
* 硬件故障（例如磁盘故障）的责任。
* 成本.
* 配置路由器和负载均衡器。
* 电源冗余。
* 保护软件访问。

![IaaS 方法](./media/iaas-approach.png)

硬件虚拟化（通过 "虚拟机"）可实现基础结构即服务（IaaS）。 有效地将主机分区为将资源提供给具有其自己的内存、CPU 和存储空间分配的实例。 团队预配必要的 Vm，并配置关联的网络和对存储的访问。

有关详细信息，请参阅[虚拟机 N 层参考体系结构](https://docs.microsoft.com/azure/architecture/reference-architectures/virtual-machines-windows/n-tier)。

尽管虚拟化和基础结构即服务（IaaS）在很多方面都需要考虑，但它仍会对基础结构团队产生很多责任。 此团队维护操作系统版本、应用安全修补程序，并在目标计算机上安装第三方依赖项。 与测试环境相比，应用在生产计算机上的行为方式有所不同。 由于不同的依赖项版本和/或操作系统 SKU 级别，导致出现问题。 尽管许多组织将 N 层应用程序部署到这些目标，但很多公司都受益于将部署到更多云本机模型（如[平台即服务](#platform-as-a-service-paas)）。 具有微服务的体系结构更具挑战性，因为需要进行扩展以实现弹性和复原。

有关详细信息，请参阅[虚拟机](https://docs.microsoft.com/azure/virtual-machines/)。

## <a name="platform-as-a-service-paas"></a>平台即服务 (PaaS)

平台即服务（PaaS）提供了已配置的解决方案，开发人员可以直接将其插入。 PaaS 是托管托管的另一种术语。 这样就无需管理基本操作系统、安全修补程序，在许多情况下，都有任何第三方依赖项。 平台示例包括 web 应用程序、数据库和移动后端。

PaaS 解决了 IaaS 常见的挑战。 PaaS 允许开发人员将精力集中在代码或数据库架构上，而不是部署方式。 PaaS 的优点包括：

* 为使用的模型付费，从而消除了在闲置计算机上投入的开销。
* 直接部署和改进的 DevOps、持续集成（CI）和持续交付（CD）管道。
* 自动升级、更新和安全修补程序。
* 向外扩展和向上扩展（弹性缩放）。

PaaS 的主要缺点是供应商锁定。 例如，某些 PaaS 提供程序仅支持 ASP.NET、node.js 或其他特定语言和平台。 诸如 Azure App Service 之类的产品已演变为满足多个平台的需要，并支持多种语言和框架来托管 web 应用。

![平台即服务体系结构](./media/paas-architecture.png)

## <a name="software-as-a-service-saas"></a>软件即服务 (SaaS)

软件即服务或 SaaS 集中托管，无需本地安装或预配即可使用。 SaaS 通常在 PaaS 的顶层托管为部署软件的平台。 SaaS 提供要运行的服务，并与现有软件连接。 SaaS 通常是行业特定的。 SaaS 经常获得许可，通常提供客户端/服务器模型。 大多数新式 SaaS 产品为客户端使用基于 web 的应用。 公司通常将 SaaS 视为许可证产品/服务的业务解决方案。 它不经常作为应用程序的可伸缩性和可维护性的体系结构注意事项来实现。 事实上，大多数 SaaS 解决方案都是在 IaaS、PaaS 和/或无服务器的后端上构建的。

通过[示例应用程序](https://docs.microsoft.com/azure/sql-database/saas-tenancy-welcome-wingtip-tickets-app)了解有关 SaaS 的详细信息。

## <a name="containers-and-functions-as-a-service-faas"></a>容器和作为服务的函数（FaaS）

容器是一种有趣的解决方案，可实现类似于 PaaS 的优点，而无需使用 IaaS 开销。 容器本质上是包含运行唯一应用程序所需的重要 essentials 的运行时。 主机操作系统的内核或核心部分以及存储等服务在主机上共享。 共享内核可使容器为轻型（与典型虚拟机的 gb 大小相比，一些容器的大小仅为兆字节）。 如果主机已在运行，则可以快速启动容器，从而实现高可用性。 快速启动容器还可以提供额外的复原层。 Docker 是最常用的容器实现之一。

容器的优点包括：

* 轻型和可移植
* 自包含，无需安装依赖项
* 提供一致的环境，不管主机（在便携式计算机上的便携式计算机上的运行完全相同）
* 可以快速预配以进行横向扩展
* 可以快速重新启动以从故障中恢复

容器在容器主机上运行（反过来可以在裸机计算机或虚拟机上运行）。 同一容器的多个容器或实例可以在单个主机上运行。 若要实现真正的故障转移和恢复，必须在主机之间扩展容器。

有关 Docker 容器的详细信息，请参阅[什么是 docker](../microservices/container-docker-introduction/docker-defined.md)。

跨主机管理容器通常需要一个业务流程工具，例如 Kubernetes。 配置和管理业务流程解决方案可能会增加项目的开销和复杂性。 幸运的是，许多云提供商通过 PaaS 解决方案提供业务流程服务，以简化容器的管理。

下图说明了 Kubernetes 安装示例。 安装地址中的节点向外扩展和故障转移。 它们运行由主服务器管理的 Docker 容器实例。 *Kubelet*是将命令从 Kubernetes 中继到 Docker 的客户端。

![Kubernetes](./media/kubernetes-example.png)

有关业务流程的详细信息，请参阅[Azure 上的 Kubernetes](https://docs.microsoft.com/azure/aks/intro-kubernetes)。

作为服务的功能（FaaS）是一种类似于无服务器的专用容器服务。 FaaS 的特定实现（称为[OpenFaaS](https://github.com/openfaas/faas)）位于容器顶层，可提供无服务器功能。 OpenFaaS 提供模板，用于打包运行代码片段所需的所有容器依赖项。 使用模板可以简化作为功能单元部署代码的过程。 OpenFaaS 面向已包含容器和协调器的体系结构，因为它可以使用现有基础结构。 尽管它提供无服务器功能，但它确实要求你使用 Docker 和 orchestrator。

## <a name="serverless"></a>无服务器

无服务器体系结构在代码与其宿主环境之间提供了明确的分离。 在由*触发器*调用的*函数*中实现代码。 退出该函数后，其所需的所有资源都可能会被释放。 该触发器可以是手动操作、定时进程、HTTP 请求或文件上传。 触发器的结果是代码的执行。 尽管无服务器平台有所不同，但大多数都提供对预定义 Api 和绑定的访问权限，以简化写入数据库或排队结果等任务。

无服务器是一种在很大程度上依赖于将代码嵌入到主机环境上的体系结构。 它可以被视为*更少的服务器*。

容器解决方案为开发人员提供了现有的生成脚本，以将代码发布到无服务器就绪映像。 其他实现使用现有 PaaS 解决方案来提供可缩放的体系结构。

抽象意味着 DevOps 团队无需预配或管理服务器，也无需设置特定的容器。 无服务器平台将代码作为使用相关 SDK 生成的脚本或打包的可执行文件承载，并为代码分配所需的资源以进行缩放。

下图演示了四个无服务器组件。 HTTP 请求导致签出 API 代码运行。 结帐 API 将代码插入到数据库中，并且插入操作将触发多个其他函数来执行任务，例如计算任务并完成顺序。

![无服务器实现](./media/serverless-implementation.png)

无服务器的优点包括：

* **高密度。** 与容器或虚拟机相比，同一个无服务器代码的多个实例可以在同一主机上运行。 实例扩展到多个主机的 scale out 和复原能力。
* **微计费**。 大多数无服务器提供程序基于无服务器执行计费，在某些情况下可节省大量成本。
* **即时缩放**。 无服务器可进行扩展以自动、快速地匹配工作负载。
* **缩短上市时间**开发人员专注于代码并直接部署到无服务器平台。 组件可以彼此独立地发布。

无服务器最常在计算的上下文中讨论，但也可以应用于数据。 例如， [AZURE SQL](https://docs.microsoft.com/azure/sql-database)和[Cosmos DB](https://docs.microsoft.com/azure/cosmos-db)都提供不要求你配置主机或群集的云数据库。 本书重点介绍无服务器计算。

## <a name="summary"></a>总结

有多种适用于体系结构的可用选项，包括混合方法。 无服务器以控制和可移植性为代价简化了应用程序功能的方法、管理和成本。 但是，许多无服务器平台确实会公开配置，以帮助优化解决方案。 好的编程做法还可以导致更易于移植的代码和更少的无服务器平台锁定。 下表说明了并行的结构方法。 根据规模需求选择无服务器，无论你是否想要管理运行时，以及你可以将工作负荷分解为小组件。 你将在下一章中了解有关无服务器和其他决策点的潜在挑战。

|         |IaaS     |PaaS     |容器|无服务器|
|---------|---------|---------|---------|----------|
|缩放|VM       |实例 |应用      |Functions  |
|**概括**|硬件|平台|OS 主机|运行时   |
|**单位** |VM       |项目  |图像    |代码      |
|**生存期**|个月|天到月|分钟到天|毫秒到分钟|
|**职责**|应用程序、依赖项、运行时和操作系统|应用程序和依赖项|应用程序、依赖项和运行时|Functions

* **Scale**指用于缩放应用程序的单位
* **抽象化**是指由实现抽象的层
* **单位**指的是部署的范围
* **生存期**指的是特定实例的典型运行时
* **责任**是指构建、部署和维护应用程序所产生的开销

下一章将重点介绍无服务器体系结构、用例和设计模式。

## <a name="recommended-resources"></a>推荐的资源

* [Azure 应用程序体系结构指南](https://docs.microsoft.com/azure/architecture/guide/)
* [Azure Cosmos DB](https://docs.microsoft.com/azure/cosmos-db)
* [Azure SQL](https://docs.microsoft.com/azure/sql-database)
* [N 层体系结构模式](https://docs.microsoft.com/azure/architecture/guide/architecture-styles/n-tier)
* [Azure 上的 Kubernetes](https://docs.microsoft.com/azure/aks/intro-kubernetes)
* [微服务](https://docs.microsoft.com/azure/architecture/guide/architecture-styles/microservices)
* [虚拟机 N 层参考体系结构](https://docs.microsoft.com/azure/architecture/reference-architectures/virtual-machines-windows/n-tier)
* [虚拟机](https://docs.microsoft.com/azure/virtual-machines/)
* [什么是 Docker？](../microservices/container-docker-introduction/docker-defined.md)
* [Wingtip 票证 SaaS 应用程序](https://docs.microsoft.com/azure/sql-database/saas-tenancy-welcome-wingtip-tickets-app)

>[!div class="step-by-step"]
>[上一页](architecture-approaches.md)
>[下一页](serverless-architecture.md)
