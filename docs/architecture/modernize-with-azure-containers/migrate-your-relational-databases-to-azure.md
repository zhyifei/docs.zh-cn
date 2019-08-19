---
title: 将关系数据库迁移到 azure
description: 通过 Azure 云和 Windows 容器实现现有 .NET 应用程序的现代化 |将关系数据库迁移到 azure
ms.date: 04/28/2018
ms.openlocfilehash: 3d4f03e61144bb6a442a50916d7fd024d38ec611
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/30/2019
ms.locfileid: "69578370"
---
# <a name="migrate-your-relational-databases-to-azure"></a>将关系数据库迁移到 azure

愿景：Azure 提供最全面的数据库迁移。

在 Azure 中, 可以直接将数据库服务器迁移到 IaaS Vm (纯粹的直接迁移), 也可以迁移到 Azure SQL 数据库, 以获得更多好处。 Azure SQL 数据库提供托管实例和完整的数据库即服务 (DBaaS) 选项。 图3-1 显示了 Azure 中提供的多个关系数据库迁移路径。

![Azure 中的数据库迁移路径](./media/image3-1.png)

> **图 3-1。** Azure 中的数据库迁移路径

## <a name="when-to-migrate-to-azure-sql-database-managed-instance"></a>何时迁移到 Azure SQL 数据库托管实例

在大多数情况下, 在将数据迁移到 Azure 时, Azure SQL 数据库托管实例是要考虑的最佳选择。 如果要迁移 SQL Server 数据库, 并且需要几乎 100% 的保证, 而无需重塑应用程序或更改数据或数据访问代码, 请选择 Azure SQL 数据库的托管实例功能。

如果对 SQL Server 实例级别的功能或除了标准 Azure SQL 数据库 (单一数据库模型) 中提供的功能之外的隔离要求有其他要求, Azure SQL 数据库托管实例是最佳选项。 这最后一种方法是最适合 PaaS 的选择, 但它并不提供与传统 SQL server 相同的功能。 迁移可能会摩擦。

例如, 在实例级 SQL Server 功能方面进行深层投资的组织将受益于迁移到 SQL 托管实例。 实例级 SQL Server 功能的示例包括 SQL 公共语言运行时 (CLR) 集成、SQL Server 代理和跨数据库查询。 对这些功能的支持在标准 Azure SQL 数据库 (单一数据库模型) 中不可用。

在高度管控行业中运作并且出于安全目的而需要维护隔离的组织, 还可以从选择 SQL 托管实例模型中获益。

Azure SQL 数据库中的托管实例具有以下特征:

- 通过 Azure 虚拟网络进行安全隔离

- 应用程序接口兼容性, 其中包含以下功能:

  - SQL Server 代理和 SQL Server Profiler

  - 跨数据库引用和查询、SQL CLR、复制、变更数据捕获 (CDC) 和 Service Broker

- 数据库最大大小为 35 TB

- 最小停机时间迁移, 其中包含以下功能:

  - Azure 数据库迁移服务

  - 本机备份和还原以及日志传送

借助这些功能, 在将现有应用程序数据库迁移到 Azure SQL 数据库时, 托管实例模型为 SQL Server 的 PaaS 提供将近 100% 的好处。 托管实例是一种 SQL Server 环境, 在此环境中, 你可以继续使用实例级功能, 而无需更改应用程序设计。

托管实例可能最适合当前正在使用 SQL Server 并且需要在云中的网络安全灵活性的企业。 这就像是为 SQL 数据库提供专用虚拟网络。

## <a name="when-to-migrate-to-azure-sql-database"></a>何时迁移到 Azure SQL Database

如前所述, 标准 Azure SQL 数据库是完全托管的关系 DBaaS。 SQL 数据库当前在世界各地跨38数据中心管理数百万个生产数据库。 它支持范围广泛的应用程序和工作负荷, 从管理简单的事务数据到驱动需要全球范围内的高级数据处理的数据密集型、任务关键型应用程序。

由于使用的是基本、标准 SQL 数据库和无其他实例功能, 因此, 如果应用程序使用的是基本的标准 SQL 数据库, 则应将其设置为 "按默认值", 而不是 "按默认选择", 则应将其设置为 "按默认值"。 标准 Azure SQL 数据库中不支持 SQL CLR 集成、SQL Server 代理和跨数据库查询等 SQL Server 功能。 这些功能仅在 Azure SQL 数据库托管实例模型中提供。

Azure SQL 数据库是为应用程序开发人员构建的唯一的智能云数据库服务。 这也是唯一一种无需停机即可实时缩放的云数据库服务, 可帮助你有效地交付多租户应用。 最终, Azure SQL 数据库可让您更好地创新, 并加速您的上市时间。 您可以使用您喜欢的语言和平台构建安全的应用程序并连接到您的 SQL 数据库。

Azure SQL 数据库具有以下优势:

- 可学习和适应应用的内置智能 (机器学习)

- 按需数据库预配

- 针对所有工作负荷的一系列产品/服务

- 99.99% 的可用性 SLA, 零维护

- 用于数据保护的异地复制和还原服务

- Azure SQL 数据库时间点还原功能

- 与 SQL Server 2016 兼容, 包括混合和迁移

标准 Azure SQL 数据库比 Azure SQL 数据库托管实例更接近于 PaaS。 首选标准 Azure SQL 数据库, 因为你将从托管云获得更多好处。 但是, Azure SQL 数据库与常规和本地 SQL Server 实例有一些重要差异。 根据你的现有应用程序的数据库要求以及企业需求和策略, 在规划迁移到云时, 这可能不是最佳选择。

## <a name="when-to-move-your-original-rdbms-to-a-vm-iaas"></a>何时将原始 RDBMS 移至 VM (IaaS)

其中一种迁移选项是将原始关系数据库管理系统 (RDBMS) (包括 Oracle、IBM DB2、MySQL、PostgreSQL 或 SQL Server) 移到运行在 Azure VM 上的类似服务器。 如果现有应用程序需要最快的迁移到云, 但更改最少, 或者根本没有任何更改, 则在云中直接迁移到 IaaS 可能是一个合理的选择。 这可能不是充分利用云的所有好处的最佳方法, 但它可能是最快的初始路径。

目前, Microsoft Azure 最多支持将[331 个不同的数据库服务器](https://azuremarketplace.microsoft.com/marketplace/apps/category/databases?page=1&subcategories=databases-all)部署为 IaaS vm。 其中包括 SQL Server、Oracle、MySQL、PostgreSQL 和 IBM DB2 等常见 RDBMS, 以及 MongoDB、Cassandra、DataStax、MariaDB 和 Cloudera 等许多其他 NoSQL 数据库。

> [!NOTE]
> 尽管将 RDBMS 迁移到 Azure VM 可能是将数据迁移到云的最快方法 (因为它是 IaaS), 但这种方法需要在 IT 团队 (数据库管理员和 IT 专业人员) 中投入大量投资。 企业团队需要能够为 SQL Server 设置和管理高可用性、灾难恢复和修补。 此上下文还需要具有完全管理权限的自定义环境。

## <a name="when-to-migrate-to-sql-server-as-a-vm-iaas"></a>何时迁移到 SQL Server 虚拟机 (IaaS)

在某些情况下, 你可能仍需要迁移到作为常规 VM SQL Server。 例如, 如果需要使用 SQL Server Reporting Services, 则会出现这种情况。 但在大多数情况下, Azure SQL 数据库托管实例可以提供从本地 SQL server 迁移所需的所有内容, 因此, 要尝试迁移到 SQL Server VM。

## <a name="use-azure-database-migration-service-to-migrate-your-relational-databases-to-azure"></a>使用 Azure 数据库迁移服务将关系数据库迁移到 Azure 

你可以使用 Azure 数据库迁移服务将 SQL Server、Oracle 和 MySQL 等关系数据库迁移到 Azure, 无论目标数据库是 Azure SQL 数据库、Azure SQL 数据库托管实例还是 Azure VM 上的 SQL Server。

带有评估报告功能的自动工作流将指导您完成在迁移数据库之前需要进行的更改。 准备就绪后, 服务会将源数据库迁移到 Azure。

只要更改原始 RDBMS, 就可能需要重新测试。 你还可能需要更改应用程序中的 SQL 语句或对象关系映射 (ORM) 代码, 具体取决于测试结果。

如果你有任何其他数据库 (例如, IBM DB2), 并且选择了提升和转移方法, 则可能需要继续将这些数据库用作 Azure 中的 IaaS Vm, 除非你愿意执行更复杂的数据迁移。 更复杂的数据迁移需要额外的精力, 因为你将使用新的架构和不同的编程库迁移到不同的数据库类型。

若要了解如何使用 Azure 数据库迁移服务迁移数据库, 请参阅[使用 Azure SQL 数据库托管实例和 Azure 数据库迁移服务更快地进入云](https://channel9.msdn.com/Events/Build/2017/P4008)。

## <a name="additional-resources"></a>其他资源

- **选择云 SQL Server 选项:Azure 虚拟机上的 azure SQL 数据库 (PaaS) 或 SQL Server (IaaS)**

    <https://docs.microsoft.com/azure/sql-database/sql-database-paas-vs-sql-server-iaas>

- **通过 Azure SQL DB 托管实例和数据库迁移服务更快地进入云**

    <https://channel9.msdn.com/Events/Build/2017/P4008>

- **将 SQL Server 数据库迁移到云中的 SQL 数据库**

    <https://docs.microsoft.com/azure/sql-database/sql-database-cloud-migrate>

- **Azure SQL 数据库**

    <https://azure.microsoft.com/services/sql-database/?v=16.50>

- **虚拟机上的 SQL Server**

    <https://azure.microsoft.com/services/virtual-machines/sql-server/>

> [!div class="step-by-step"]
> [上一页](lift-and-shift-existing-apps-azure-iaas.md)
> [下一页](modernize-existing-apps-to-cloud-optimized/index.md)
