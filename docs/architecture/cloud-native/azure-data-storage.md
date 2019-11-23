---
title: Azure 中的数据存储
description: 构建适用于 Azure 的云本机 .NET 应用 |Azure 中的数据存储
ms.date: 06/30/2019
ms.openlocfilehash: 1a86cecf005c6dbdfda5cf4cacfafaad4711c076
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73841893"
---
# <a name="data-storage-in-azure"></a>Azure 中的数据存储

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

正如我们在本书中看到的那样，云正在改变应用程序的设计、部署和管理方式。 迁移到云时，重要的问题是如何移动数据？ 幸运的是，Azure 云提供了许多选项。

只需预配 Azure 虚拟机并安装所选的数据库即可。 这称为[基础结构即服务（IaaS）](https://www.techopedia.com/definition/141/infrastructure-as-a-service-iaas)。 此方法简化了将本地数据库迁移到云中的工作，但又将管理虚拟机和数据库的负担转移到了你。

相反，完全托管的[数据库即服务（DBaaS）](https://www.stratoscale.com/blog/dbaas/what-is-database-as-a-service/)是一个更好的选择。 你获取了许多内置功能，而托管、维护和授权由 Microsoft 管理。 Azure 具有不同种类的完全托管的数据存储选项，每个选项都有特定的优点。 它们都支持实时容量和即用即付模型。

接下来，我们将了解 Azure 中提供的 DBaaS 选项。 你将了解 Microsoft 如何继续为 Azure 提供 "开放平台"，为许多开源关系和 NoSQL 数据库提供托管支持，并为活动成员提供对各种开源基础的关键贡献。

## <a name="azure-sql-database"></a>Azure SQL 数据库

[AZURE SQL 数据库](https://docs.microsoft.com/azure/sql-database/)是一种功能丰富的通用关系数据库即服务（DBaaS），基于 Microsoft SQL Server 数据库引擎。 它完全由 Microsoft 管理，并且是高性能、可靠且安全的云数据库。 该服务共享 SQL Server 的本地版本中发现的许多功能。

你可以在几分钟内预配 SQL 数据库服务器和数据库。 当你的应用程序的需求从几个客户增长到数百万个时，Azure SQL 数据库会动态缩放，并且停机时间最短。 可以动态添加或删除资源，包括 CPU 能力、内存、IO 吞吐量和分配给数据库的存储空间。

图5-12 显示了 Azure SQL 数据库的部署选项。

![Azure SQL 部署选项](./media/azure-sql-database-deployment-options.png)

**图 5-12**。 Azure SQL 部署选项

部署 SQL 数据库时，请注意上图中的替代项：

- [单个数据库](https://docs.microsoft.com/azure/sql-database/sql-database-single-database) 包含由[SQL 数据库服务器](https://docs.microsoft.com/azure/sql-database/sql-database-servers)管理的一组资源。 单个数据库类似于在本地 SQL Server 部署中  [包含的数据库](https://docs.microsoft.com/sql/relational-databases/databases/contained-databases)。

- 一种[弹性池](https://docs.microsoft.com/azure/sql-database/sql-database-elastic-pool)，其中的 sql 数据库集合按固定价格共享一个 sql 数据库服务器。 可以根据需要将单个数据库移入和移出弹性池，以优化一组数据库的价格性能。

- 一个[托管实例](https://docs.microsoft.com/azure/sql-database/sql-database-managed-instance)，它是系统和用户数据库的集合，提供与本地 SQL Server 近乎100% 的兼容性。 此选项支持较大的数据库，最大可达 35 TB，并将其放在[Azure 虚拟网络](https://docs.microsoft.com/azure/virtual-network/virtual-networks-overview)中，以便更好地进行隔离。

Azure SQL 数据库是一种完全托管的[平台即服务（PaaS）数据库引擎](https://docs.microsoft.com/azure/sql-database/sql-database-paas)，无需用户干预即可处理升级、修补、备份和监视。 它始终运行 SQL Server 的最新稳定版本数据库引擎和修补的操作系统，保证99.99% 的可用性。 一项功能，[活动异地复制](https://docs.microsoft.com/azure/sql-database/sql-database-active-geo-replication)可让你在相同或不同的 Azure 数据中心内创建可读的辅助数据库。 发生故障时，可以启动到辅助数据库的故障转移。 此时，其他辅助数据库会自动链接到新的主副本。 同一区域或不同区域中最多支持四个辅助副本，这些辅助副本也可用于只读访问查询。

Azure SQL 数据库包括[内置的监视和智能优化](https://docs.microsoft.com/azure/sql-database/sql-database-monitoring-tuning-index)功能，可帮助你最大限度地提高性能和降低运营成本。 例如，[自动优化](https://docs.microsoft.com/azure/sql-database/sql-database-automatic-tuning)功能基于 AI 和机器学习提供持续的性能优化。 该服务从正在运行的工作负荷中学习，并可应用优化建议。 Azure SQL 数据库在启用自动优化的情况下运行的时间越长，性能就越好。

[AZURE SQL 数据库无服务器](https://docs.microsoft.com/azure/sql-database/sql-database-serverless)（在撰写本书时可用于预览）是单个数据库的计算层，可根据工作负荷需求自动缩放，并按每秒使用的计算量进行计费。 无服务器计算层还会在非活动期间自动暂停数据库，以便只对存储费用收费。 当活动返回时，它将自动恢复。

最后，还提供了新的[AZURE SQL Database 超大规模](https://azure.microsoft.com/services/sql-database/)定价层。 它由高度可扩展的存储体系结构提供支持，并使数据库可根据需要增长，从而无需预配存储资源。 你可以独立缩放计算和存储资源，为每个工作负荷提供优化性能的灵活性。 Azure SQL Database 超大规模针对[OLTP](https://en.wikipedia.org/wiki/Online_transaction_processing)处理和高吞吐量分析工作负荷进行了优化，存储最大为 100 TB。  使用读取密集型工作负荷时，超大规模可以根据需要预配额外的读取副本，以卸载读取工作负荷。

除了传统的 Microsoft SQL Server 堆栈以外，Azure 还提供多个常用开源数据库的托管版本。

## <a name="azure-database-for-mysql"></a>Azure Database for MySQL

[MySQL](https://en.wikipedia.org/wiki/MySQL) 是 [开源](https://en.wikipedia.org/wiki/Open-source_software) [关系数据库](https://en.wikipedia.org/wiki/Relational_database_management_system)。 它是[灯泡软件堆栈](https://en.wikipedia.org/wiki/LAMP_(software_bundle))中的一个组件，由许多大型组织（包括 Facebook、Twitter 和 YouTube）使用。 社区版免费提供，enterprise edition 需要购买许可证。 此产品最初是在1995中创建的，它是由的 2008 Sun 购买的，由 Oracle 在2010中获取。

[Azure Database for MySQL](https://azure.microsoft.com/services/mysql/)是一项完全托管的企业就绪关系数据库服务，它基于开源 MySQL 服务器引擎。 实现 MySQL 社区版包含以下 PaaS 功能，无需额外付费：

- 内置的[高可用性](https://docs.microsoft.com/azure/mysql/concepts-high-availability)。

- 使用非独占即用即[付定价](https://docs.microsoft.com/azure/mysql/concepts-pricing-tiers)可预测的性能。

- 在几秒内根据需要进行[缩放](https://docs.microsoft.com/azure/mysql/concepts-high-availability)。

- 保护以保护静态和动态敏感数据。

- [自动备份](https://docs.microsoft.com/azure/mysql/concepts-backup)和[时间点还原](https://docs.microsoft.com/azure/mysql/concepts-backup)最多35天。

- 企业级安全性和符合性。

这些内置的 PaaS 功能对于在其数据中心拥有数百个 "战术性" （非战略）数据库的组织非常重要，但没有资源来执行修补、备份、安全和性能监视。

此外， [Azure 数据迁移服务](https://azure.microsoft.com/services/database-migration/)可将来自多个数据库源的数据迁移到 Azure 数据平台，并且停机时间最短。 服务将生成评估报告，并提供建议，指导你完成执行迁移所需的更改，这两种情况都很小或大。

托管的[Azure MySQL 服务器](https://docs.microsoft.com/azure/mysql/concepts-servers)是服务的中心管理点。 它是用于本地部署的相同 MySQL 服务器引擎。 使用它，你可以为每个服务器创建一个数据库来使用所有资源，或者为每个服务器创建多个数据库来共享资源。 你的团队可以继续通过你选择的开源工具和平台来开发应用程序，而无需学习新技能或管理虚拟机和基础结构。

## <a name="azure-database-for-mariadb"></a>Azure Database for MariaDB

[MariaDB](https://mariadb.com/)服务器是另一个受欢迎的开源数据库服务器。 它在 Oracle 最初开发的 mysql 开发人员（其拥有 MySQL 的 Sun Microsystems）上创建为 MySQL 的分叉。 目的是确保 MariaDB 保持开源。

由于 MariaDB 是[MySQL 的分叉](https://blog.panoply.io/a-comparative-vmariadb-vs-mysql)，因此，数据和表定义是兼容的，客户端协议、结构和 api 是编织的。 MySQL 数据连接器无需修改即可 MariaDB 工作。

MariaDB 具有强大的功能，由许多大型企业使用。 尽管 Oracle 继续维护、增强和支持 MySQL，但 MariaDB 由 MariaDB 基础进行管理，允许对产品和文档公开贡献。

[Azure Database for MariaDB](https://azure.microsoft.com/services/mariadb/)是 Azure 云中完全托管的数据库即服务。 它基于 [MariaDB 社区版](https://mariadb.org/download/)服务器引擎。 它可以处理具有可预测性能和动态可伸缩性的任务关键型工作负荷。 类似于其他 Azure 数据库平台，它包含许多平台即服务功能，无需额外付费：

- 内置的[高可用性](https://docs.microsoft.com/azure/mariadb/concepts-high-availability)。

- 使用非独占即用即[付定价](https://docs.microsoft.com/azure/mariadb/concepts-pricing-tiers)可预测的性能。

- 在几秒内根据需要进行[缩放](https://docs.microsoft.com/azure/mariadb/concepts-high-availability)。

- 保护静态和动态敏感数据的安全。

- [自动备份](https://docs.microsoft.com/azure/mariadb/concepts-backup)和[时间点还原](https://docs.microsoft.com/azure/mariadb/concepts-backup)最多35天。

- 企业级安全性和符合性。

## <a name="azure-database-for-postgresql"></a>Azure Database for PostgreSQL

[PostgreSQL](https://www.postgresql.org/)是另一个流行的开源关系数据库，具有30年以上的活动开发。 这是一个常规用途和对象关系数据库管理系统。 它的许可被认为是 "自由" 的，产品可免费使用、修改和分发任何形式。 许多大型企业（包括 Apple、Red Hat 和 Fujitsu）都使用 PostgreSQL 构建了产品。

[Azure Database for PostgreSQL](https://azure.microsoft.com/services/postgresql/)是一项完全托管的关系数据库服务，它基于开源 Postgres 数据库引擎。 它可以处理任务关键型工作负荷，并提供可预测的性能、安全性、高可用性和动态可伸缩性。 它支持多种开源框架和语言，包括C++、Java、Python、Node、C\#和 PHP。 它通过命令行接口或[Azure 数据迁移服务](https://azure.microsoft.com/services/database-migration/)实现 PostgreSQL 数据库的[迁移](https://datamigration.microsoft.com/scenario/postgresql-to-azurepostgresql?step=1)。

该服务包含的[内置智能](https://docs.microsoft.com/azure/postgresql/concepts-monitoring)可研究您独特的数据库模式，并提供自定义的建议和见解，帮助您最大程度地提高 PostgreSQL 数据库的性能。 [高级威胁防护](https://docs.microsoft.com/azure/postgresql/concepts-data-access-and-security-threat-protection)会围绕时钟监视数据库，检测潜在的恶意活动，并在检测时发出警报，以便你可以立即进行干预。

Azure Database for PostgreSQL 提供了两个部署选项：单一服务器和超大规模（Citus），可在本书撰写时预览

- [单服务器](https://docs.microsoft.com/azure/postgresql/concepts-servers)部署选项是多个数据库的中心管理点。 它是可用于本地部署的相同 PostgreSQL 服务器引擎。 使用它，你可以为每个服务器创建一个数据库来使用所有资源，或创建多个数据库来共享资源。 根据内核和存储，定价按服务器进行组织。

- [超大规模（Citus）选项](https://azure.microsoft.com/blog/get-high-performance-scaling-for-your-azure-database-workloads-with-hyperscale/)由 [Citus Data](https://www.citusdata.com/) 技术提供支持。 它通过水平缩放数百个节点上的单个数据库来实现高性能缩放，以提供超快的快速性能和缩放性。 此选项允许引擎在内存中容纳更多数据、跨数百个节点进行并行化查询，并更快地为数据编制索引。 超大规模功能与 PostgreSQL 的最新创新、版本和工具兼容，因此你可以利用现有的 PostgreSQL 专业知识。

## <a name="cosmos-db"></a>Cosmos DB

Azure Cosmos DB 是一种完全托管的全球分布式 NoSQL 数据库服务，旨在提供低延迟、弹性可伸缩性、托管数据一致性和高可用性。 简而言之，如果你的应用程序需要在世界各地的任何地方保证快速响应时间，则如果需要始终处于联机状态并且需要吞吐量和存储的无限制和弹性可伸缩性，则 Cosmos DB 是一项很好的选择。 图5-13 显示了 Cosmos DB 的高级概述。

![Cosmos DB 概述](./media/cosmos-db-overview.png)

**图 5-13**： Cosmos DB 概述

请注意，在图5-13 中，如何 Cosmos DB 是一种功能强大、高度多样的数据库服务，具有许多内置的云本机功能。 在本部分中，我们将详细介绍它们。

### <a name="global-support"></a>全球支持

你可以在世界各地跨所有 Azure 区域全局分发 Cosmos 数据库，将数据放置到用户附近，缩短响应时间并减少延迟。 无需暂停或重新部署应用程序，即可在区域中添加或删除数据库。 在后台，Cosmos DB 以透明方式将数据复制到所有已配置的区域。

Cosmos DB 支持全局级别的[主动/主动](https://kemptechnologies.com/white-papers/unfog-confusion-active-passive-activeactive-load-balancing/)群集，使你能够将任何或所有数据库区域配置为支持写入和读取。

Cosmos DB 中的[多主机](https://docs.microsoft.com/azure/cosmos-db/how-to-multi-master)协议功能可实现以下功能：

- 无限制弹性写入和读取可伸缩性。

- 99.999 读写所有世界各地的可用性。

- 有保证的读取和写入在99% 百分位的时间不到10毫秒。

在内部，Cosmos DB 处理具有一致性级别保证和财务支持的服务级别协议的区域之间的数据复制。

利用 Cosmos DB[多宿主 api](https://docs.microsoft.com/azure/cosmos-db/distribute-data-globally)，你的应用程序可以自动识别最近的 Azure 区域并向其发送请求。 最近的区域由 Cosmos DB 标识，无需进行任何配置更改。 如果某个区域变得不可用，Cosmos DB 支持自动故障转移，并且多宿主功能会自动将请求路由到下一个最近的可用区域。

### <a name="multi-model-support"></a>多模型支持

Cosmos DB 是一种*多模型数据平台*，可让你使用多种受支持的 NoSQL 模型与数据进行交互，包括文档、键/值对、宽列和图形表示。 在内部，数据以由基元数据类型（包括字符串、布尔和数字）组成的简单[结构](https://docs.microsoft.com/dotnet/csharp/programming-guide/classes-and-structs/using-structs)格式存储。 对于每个请求，数据库引擎将数据转换为所选的模型表示形式。 可以从基于 SQL 的 Cosmos DB 专有 API 或图5-14 中所示的任何[兼容性 api](https://www.wikiwand.com/en/Cosmos_DB)中进行选择。

![Cosmos DB 提供程序](./media/cosmos-db-providers.png)

**图 5-14**： Cosmos DB 提供程序

请注意，如图5-14 如何支持[表存储](https://azure.microsoft.com/services/storage/tables/)Cosmos DB。 Cosmos DB 和[Azure 表存储](https://docs.microsoft.com/azure/cosmos-db/table-storage-overview)共享同一个基础表模型并公开了许多相同的表操作。 但是， [Cosmos DB 表 API](https://docs.microsoft.com/azure/cosmos-db/table-introduction)提供了许多在 AZURE 存储 API 中不可用的高级增强功能。 这些功能在图5-15 中是相对的。

![Azure 表 API](./media/azure-table-api.png)

**图 5-15**： Azure 表 API

为 Azure 表存储编写的应用程序可以使用表 API 迁移到 Azure Cosmos DB，而无任何代码更改。

在[要重建 mqtt](https://en.wikipedia.org/wiki/Brownfield_(software_development))应用程序方案中，开发团队可以将现有的 Mongo、Gremlin 或 Cassandra 数据库迁移到 Cosmos DB，对现有数据或应用程序代码进行少量更改。 对于[领域](https://en.wikipedia.org/wiki/Greenfield_project)方案，开发团队可以选择最符合其要求和首选项的数据模型，包括 MongoDB、Cassandra 和 Gremlin 平台的完全受支持的开源选项。

### <a name="consistency-models"></a>一致性模型

在*关系与 NoSQL*部分的前面部分中，我们讨论了*数据一致性*的主题，这是一个表示数据完整性的术语。 依赖于复制以实现高可用性和/或低延迟的分布式数据库必须在读取一致性、可用性和延迟之间做出根本性的权衡。

大多数分布式数据库允许开发人员在两种一致性模型之间进行选择： [强一致性](https://en.wikipedia.org/wiki/Strong_consistency)和 [最终一致性](https://en.wikipedia.org/wiki/Eventual_consistency)。 *强一致性*是数据可编程性的黄金标准。 它保证查询结果将始终返回最新的数据，即使系统必须在等待更新复制到所有数据库副本时产生延迟。 另一方面，配置为*最终一致性*的系统会立即返回数据，即使该数据不是最新的副本。 此选项可实现更高的可用性、更高的规模和更高的性能。

Azure Cosmos DB 提供了一系列[定义完善的一致性模型](https://docs.microsoft.com/azure/cosmos-db/consistency-levels)，如图5-16 所示。 这些选项使你能够根据应用程序的需要，对可用性和性能做出精确的选择和精细的权衡。 这些模型由服务级别协议（Sla）定义完善、直观且受支持。

![Cosmos DB 一致性级别](./media/cosmos-db-consistency-levels.png)

**图 5-16**： Cosmos DB 一致性级别

### <a name="partitioning"></a>分区

Azure Cosmos DB 使用自动[分区](https://docs.microsoft.com/azure/cosmos-db/partitioning-overview)来缩放数据库，以满足应用程序的性能需求。

可以通过创建[数据库、容器和项](https://docs.microsoft.com/azure/cosmos-db/databases-containers-items)（如图5-17 所示）来管理 Cosmos DB 数据中的数据。

![Cosmos DB 实体](./media/cosmos-db-entities.png)

**图 5-17**： Cosmos DB 实体的层次结构

请注意，在图5-17 中，如何从在数据库帐户内创建 Cosmos DB 数据库着手。 该数据库成为一组容器的管理单元。 容器是项的架构无关分组，可根据所选的 API 提供程序（前面的部分中所述）表示为集合、表或关系图。 项是添加到容器中的数据，表示为文档、行、节点或边缘。 默认情况下，你添加到容器中的所有项都将自动编制索引，而无需显式索引或架构管理。

若要将容器分区，项被分为称为 [逻辑分区](https://docs.microsoft.com/azure/cosmos-db/partition-data)的不同子集。 逻辑分区是根据与容器中每一项关联的分区键的值创建的。 图5-18 显示了逻辑分区中的所有项如何具有相同的分区键值。

![Cosmos DB 分区机制](./media/cosmos-db-partitioning.png)

**图 5-18**： Cosmos DB 分区机制

请注意，在图5-18 中，每个项都包含 "city" 或 "机场" 的分区键。 此分区键确定项的逻辑分区。 每个城市代码都将分配给左侧容器中的一个逻辑分区，并将具有机场代码的逻辑分区分配给右侧的容器。 将分区键值与项的 ID 值组合将创建项的索引，该索引唯一标识该项。

在内部，Cosmos DB 自动管理[物理分区](https://docs.microsoft.com/azure/cosmos-db/partition-data)上的[逻辑分区](https://docs.microsoft.com/azure/cosmos-db/partition-data)位置，以有效地满足容器的可伸缩性和性能需求。 随着应用程序的吞吐量和存储要求的增加，Azure Cosmos DB 会移动逻辑分区，以便在更多的服务器之间重新分发负载。 这些再分发操作由 Cosmos DB 管理，并在没有任何中断或停机时间的情况下执行。

## <a name="azure-redis-cache"></a>Azure Redis Cache

充分了解缓存的优点，提高性能和伸缩性。

对于云本机应用程序，添加缓存的一个常见位置是在 API 网关中。 该网关充当所有传入请求的前端。 通过添加缓存，可以通过返回缓存的数据，避免到本地数据库或下游服务的往返，提高性能和响应能力。 图5-19 显示了云本机应用程序的缓存体系结构。

![在云本机应用中缓存](./media/caching-in-a-cloud-native-app.png)

**图 5-19**：在云本机应用中进行缓存

常见的缓存模式是[缓存的模式](https://docs.microsoft.com/azure/architecture/patterns/cache-aside)。 对于传入请求，先查询缓存中的响应，如图5-19 中的步骤 #1 所示。 如果找到，则立即返回数据。 如果缓存中不存在数据（称为[缓存未命中](https://www.techopedia.com/definition/6308/cache-miss)），则会从本地数据库或下游服务（步骤 #2）中检索数据，并将其写入缓存供将来请求（步骤 #3），并返回给调用方。 务必要定期逐出缓存的数据，以便系统保持一致且准确。

此外，请注意，图5-19 中的缓存未在服务边界内本地实现，而是作为基于云的支持服务使用，如第1章所述。

[Azure Redis 缓存](https://azure.microsoft.com/services/cache/)是一种数据缓存和消息代理服务。 它为应用程序提供高吞吐量和低延迟的数据访问。 它完全由 Microsoft 托管，托管在 Azure 中，并且可供 Azure 内部或外部的任何应用程序访问。

在内部，Redis 的 Azure 缓存由开源[Redis 服务器](https://redis.io/)提供支持，并以本机方式支持数据结构，例如[字符串](https://redis.io/topics/data-types#strings)、[哈希](https://redis.io/topics/data-types#hashes)、[列表](https://redis.io/topics/data-types#sets)、[集](https://redis.io/topics/data-types#sets)和[排序集](https://redis.io/topics/data-types#sorted-sets)。 如果你的应用程序使用 Redis，则它将按原样使用 Azure Cache for Redis。

适用于 Redis 的 Azure 缓存还可用作内存中数据缓存、分布式非关系数据库和消息代理。 它在三个不同的定价层中提供。 高级层的功能包括多种企业级功能，如群集、数据持久性、异地复制，以及虚拟网络安全性和隔离性。

>[!div class="step-by-step"]
>[上一页](data-patterns.md)
>[下一页](resiliency.md)
