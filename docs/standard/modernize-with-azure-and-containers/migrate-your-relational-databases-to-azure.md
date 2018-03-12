---
title: "将关系数据库迁移到 azure"
description: "更新现有的.NET 应用程序与 Azure 云和 Windows 容器 |将关系数据库迁移到 azure"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/26/2017
ms.prod: .net
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 9189de8d083c8f9dea8c53b428e6cd34ae6dad15
ms.sourcegitcommit: d3cfda0943364aaf6ccd574f55f584576c8a4fee
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/08/2018
---
# <a name="migrate-your-relational-databases-to-azure"></a>将关系数据库迁移到 azure

设想： Azure 提供最全面的数据库迁移。

在 Azure 中，你可以将您的数据库服务器迁移直接到 IaaS Vm （纯提起并移动），或可以为其他好处迁移到 Azure SQL 数据库。 Azure SQL 数据库提供托管的实例和完整数据库作为-服务 (DBaaS) 选项。 图 3-1 显示多个关系数据库在 Azure 中可用的迁移路径。

![在 Azure 中的数据库迁移路径](./media/image3-1.png)

> **图 3-1。** 在 Azure 中的数据库迁移路径

## <a name="when-to-migrate-to-azure-sql-database-managed-instance"></a>何时将迁移到 Azure SQL 数据库托管实例

在大多数情况下，Azure SQL 数据库托管实例将最好的选择将你的数据迁移到 Azure 时要考虑。 如果您要迁移 SQL Server 数据库，并且需要几乎无需重新设计你的应用程序或对您的数据或数据访问代码进行更改的 100%保障，选择 Azure SQL 数据库的托管实例功能。

如果你有其他要求 SQL Server 实例级功能或超出标准的 Azure SQL 数据库 （单个数据库模型） 中提供的功能的隔离要求，azure SQL 数据库托管实例是最佳选项。 此最后一项的最面向 PaaS 的选择，但它不提供与传统的 SQL server 的相同的功能。 迁移可能会出现 frictions。

例如，组织已深层投资实例级 SQL Server 功能受益从迁移到 SQL 托管实例。 实例级 SQL Server 功能的示例包括 SQL 公共语言运行时 (CLR) 集成，SQL Server 代理，以及跨数据库查询。 对这些功能的支持中均不提供标准的 Azure SQL 数据库 （单一数据库模型）。

操作在高度管控行业中，且需要维护隔离出于安全考虑，组织还可能受益于选择的 SQL 托管实例模式。

Azure SQL 数据库中的托管的实例具有以下特征：

- 通过 Azure 虚拟网络的安全隔离

- 应用程序图面兼容性，具有这些功能：

  - SQL Server 代理和 SQL Server 事件探查器

  - 跨数据库引用和查询，SQL CLR 复制、 变更数据捕获 (CDC) 和 Service Broker

- 数据库大小最多 35 TB

- 使用这些功能的最小停机时间迁移：

  - Azure 数据库迁移服务

  - 本机备份和还原和日志传送

使用这些功能，当将现有应用程序数据库迁移到 Azure SQL 数据库的托管实例模型就提供近 100%的 Paas 的优势的 SQL Server。 托管的实例是继续使用实例级功能，而无需更改应用程序设计的其中一个 SQL Server 环境。

托管的实例可能是最适合企业，当前正在使用 SQL Server，并且其需要灵活地在云中其网络安全。 这就像有你的 SQL 数据库的专用虚拟网络。

## <a name="when-to-migrate-to-azure-sql-database"></a>何时迁移到 Azure SQL Database

如前文所述，标准的 Azure SQL 数据库是完全托管的、 关系 DBaaS。 SQL 数据库当前 38 与世界各地的数据中心管理数以百万计的生产数据库。 它支持广泛的应用程序和工作负荷，从管理简单的事务数据，为驱动的数据最密集、 任务关键型应用程序需要在全球范围内的高级的数据处理。

由于其完整的 PaaS 功能，并更好地定价-并最终降低成本-你应该将移到标准的 Azure SQL 数据库作为你": 默认情况下选择"如果你有一个应用程序，该使用基本、 标准 SQL 数据库和任何其他实例功能。 标准的 Azure SQL 数据库中不支持 SQL CLR 集成、 SQL Server 代理和跨数据库查询等的 SQL Server 功能。 仅在 Azure SQL 数据库托管实例模型中提供了这些功能。

Azure SQL 数据库是为应用程序开发人员生成的仅智能云数据库服务。 它也是缩放上快速，而无需停机，来帮助你高效地提供多租户应用程序的唯一云数据库服务。 从根本上讲，Azure SQL 数据库会使你更多的时间，以创新，并因此加快了上市时间。 你可以生成安全的应用程序，并使用的语言和平台所需连接到你的 SQL 数据库。

Azure SQL 数据库提供以下好处：

- 了解和适应你的应用程序的内置智能 （机器学习）

- 按需数据库设置

- 一系列的优惠，为所有工作负荷

- 99.99%的可用性 SLA，零维护

- 异地复制和还原服务的数据保护

- Azure SQL 数据库点时间还原功能

- 与 SQL Server 2016，包括混合和迁移的兼容性

标准的 Azure SQL Database 是更接近于 PaaS 比 Azure SQL 数据库托管实例。 你应尝试使用它，如果可能，因为你将从托管云中获取更多好处。 但是，Azure SQL 数据库已从常规的主要区别和本地 SQL Server 实例。 根据现有应用程序的数据库要求和你的企业要求和策略，它可能规划你迁移到云时不是最佳选择。

## <a name="when-to-move-your-original-rdbms-to-a-vm-iaas"></a>何时将原始 RDBMS 移到虚拟机 (IaaS)

迁移选项之一是将你原始关系数据库管理系统 (RDBMS)，包括 Oracle、 IBM DB2、 MySQL、 PostgreSQL、 或 SQL Server，到在 Azure VM 运行的类似服务器。 如果你的所有需要最快迁移到云中，而最小的更改或不需要更改的现有应用，直接迁移到云中的 IaaS 可能是合理的选项。 它可能不会利用的所有云的优势的最佳方法，但它可能是最快的初始路径。

当前，Microsoft Azure 支持最多[331 不同数据库服务器](https://azuremarketplace.microsoft.com/en-us/marketplace/apps/category/databases?page=1&subcategories=databases-all)作为 IaaS Vm 部署。 其中包括 SQL Server、 Oracle、 MySQL、 PostgreSQL、 和 IBM DB2，等的常用 Rdbms 和如 MongoDB、 Cassandra、 DataStax、 MariaDB 和 Cloudera 的许多其他 NoSQL 数据库。

> [!NOTE]
> 尽管移动到 Azure VM RDBMS 可能将你的数据迁移到云 （因为它是 IaaS） 的最快方法，此方法需要大量的投资，在你的 IT 团队 （数据库管理员和 IT 专业人员）。 企业团队需要能够设置和管理高可用性、 灾难恢复和 SQL Server 的修补。 此上下文还需要具有完全管理权限的自定义的环境。

## <a name="when-to-migrate-to-sql-server-as-a-vm-iaas"></a>何时迁移到 SQL Server 作为虚拟机 (IaaS)

可能有少数情况下，仍需要将迁移到 SQL Server 作为正则 VM。 示例方案是如果你需要使用 SQL Server Reporting Services。 在大多数情况下，不过，Azure SQL 数据库托管实例可以提供你需要将从本地 SQL 服务器迁移，因此迁移到 SQL Server 虚拟机应该尝试你最后一招所有内容。

## <a name="use-azure-database-migration-service-to-migrate-your-relational-databases-to-azure"></a>使用 Azure 数据库迁移服务将关系数据库迁移到 Azure 

可以使用 Azure 数据库迁移服务将 SQL Server、 Oracle 和 MySQL 如关系数据库迁移到 Azure，无论你的目标数据库是 Azure SQL 数据库、 Azure SQL 数据库托管实例或在 Azure VM 上的 SQL Server。

自动工作流，通过评估报告，将指导您完成需要迁移数据库之前进行的更改。 准备就绪后，服务会将源数据库迁移到 Azure。

每当你更改原始 RDBMS，你可能需要重新测试。 你还可能需要更改的 SQL 句子或应用程序，具体取决于测试结果中的对象关系映射 (ORM) 代码。

如果你有任何其他数据库 (例如，IBM DB2)，并且你选择提起并移动方法，你可能想要继续使用这些数据库作为 IaaS Vm 在 Azure 中，除非您愿意为执行更复杂的数据迁移。 更复杂的数据迁移将需要额外的工作，因为你将迁移到新的架构和不同的编程库的不同的数据库类型。

若要了解如何将数据库迁移通过使用 Azure 数据库迁移服务，请参阅[到云使用 Azure SQL 数据库托管实例和 Azure 数据库迁移服务更快地获取](https://channel9.msdn.com/Events/Build/2017/P4008)。

## <a name="additional-resources"></a>其他资源

- **选择云 SQL Server 选项： Azure SQL 数据库 (PaaS) 或 Azure VM (IaaS) 上的 SQL Server**

    [https://docs.microsoft.com/azure/sql-database/sql-database-paas-vs-sql-server-iaas](https://docs.microsoft.com/azure/sql-database/sql-database-paas-vs-sql-server-iaas)

- **获取与使用 Azure SQL DB 托管实例和数据库迁移服务更快地云**

    [https://channel9.msdn.com/Events/Build/2017/P4008](https://channel9.msdn.com/Events/Build/2017/P4008)

- **SQL Server 数据库迁移到云中的 SQL 数据库**

    [https://docs.microsoft.com/azure/sql-database/sql-database-cloud-migrate](https://docs.microsoft.com/azure/sql-database/sql-database-cloud-migrate)

- **Azure SQL 数据库**

    [https://azure.microsoft.com/services/sql-database/?v=16.50](https://azure.microsoft.com/services/sql-database/?v=16.50)

- **在虚拟机上的 SQL Server**

    [https://azure.microsoft.com/services/virtual-machines/sql-server/](https://azure.microsoft.com/services/virtual-machines/sql-server/)

>[!div class="step-by-step"]
[上一页](lift-and-shift-existing-apps-azure-iaas.md)
[下一页](lift-and-shift-existing-apps-devops/index.md)