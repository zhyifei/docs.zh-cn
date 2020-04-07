---
title: 关系与NoSQL 数据
description: 了解云原生应用程序中的关系数据和 NoSQL 数据
author: robvet
ms.date: 01/22/2020
ms.openlocfilehash: 3fb3dcc3a87e278c05f3e15d261245f4d61453d1
ms.sourcegitcommit: f87ad41b8e62622da126aa928f7640108c4eff98
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/07/2020
ms.locfileid: "80805807"
---
# <a name="relational-vs-nosql-data"></a>关系与NoSQL 数据

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

关系和 NoSQL 是两种类型的数据库系统，通常在云本机应用程序中实现。 它们构建方式不同，存储数据不同，访问方式也不同。 在本节中，我们将介绍这两个。 在本章的后面部分，我们将介绍一种名为*NewSQL*的新兴数据库技术。

*几十年来，关系数据库*一直是一种流行的技术。 它们成熟、成熟且广泛实施。 竞争的数据库产品、工具和专业知识比比皆是。 关系数据库提供相关数据表的存储。 这些表具有固定的架构，使用 SQL（结构化查询语言）来管理数据，并支持 ACID 保证。

*无 SQL 数据库*是指高性能、非关系数据存储。 他们在易用性、可扩展性、弹性和可用性特性方面表现卓越。 NoSQL 不是联接规范化数据的表，而是存储非结构化或半结构化数据，通常存储在键值对或 JSON 文档中。 无 SQL 数据库通常不提供超出单个数据库分区范围的 ACID 保证。 需要次秒响应时间的高容量服务有利于 NoSQL 数据存储。

[NoSQL](https://www.geeksforgeeks.org/introduction-to-nosql/)技术对分布式云本机系统的影响怎么强调也不为过。 这一领域的新数据技术的激增打乱了曾经完全依赖关系数据库的解决方案。

NoSQL 数据库包括几个用于访问和管理数据的不同模型，每个模型都适合特定的用例。 图 5-9 显示了四种常见模型。

![无SQL数据模型](./media/types-of-nosql-datastores.png)

**图 5-9**： NoSQL 数据库的数据模型

| “模型” | 特征 |
| :-------- | :-------- |
| 文档存储 | 数据和元数据在数据库中基于 JSON 的文档中分层存储。 |
| 关键价值存储 | 作为 NoSQL 数据库中最简单的数据，数据表示为键值对的集合。 |
| 宽柱商店 | 相关数据存储在单个列中的一组嵌套键/值对中。 |
| 图形存储 | 数据存储在图形结构中作为节点、边和数据属性。 |

## <a name="the-cap-theorem"></a>CAP 定理

为了了解这些类型的数据库之间的差异，请考虑 CAP 定理，这是一组应用于存储状态的分布式系统的原则。 图 5-10 显示了 CAP 定理的三个属性。

![The CAP Theorem（CAP 定理）](./media/cap-theorem.png)

**图 5-10**. CAP 定理

该定理指出，分布式数据系统将在一致性、可用性和分区容差之间进行权衡。 而且，任何数据库只能保证三个属性中的*两*个：

- *一致性。* 群集中的每个节点都响应最新的数据，即使系统必须阻止请求，直到所有副本更新。 如果查询当前正在更新的项目的"一致系统"，则将等待该响应，直到所有副本成功更新。 但是，您将收到最新的数据。

- *可用 性。* 每个节点都会返回即时响应，即使该响应不是最新的数据。 如果查询正在更新的项目的"可用系统"，您将获得该服务此时可以提供的最佳答案。

- *分区容差。* 保证即使复制的数据节点发生故障或失去与其他复制数据节点的连接，系统也能继续运行。

关系数据库通常提供一致性和可用性，但不提供分区容差。 它们通常预配到单个服务器，并通过向计算机添加更多资源来垂直扩展。

许多关系数据库系统都支持内置复制功能，其中主数据库的副本可以制作到其他辅助服务器实例。 写入操作对主实例执行，并复制到每个辅助实例。 发生故障时，主实例可能会故障转移到辅助实例以提供高可用性。 辅助数据库还可用于分发读取操作。 虽然写入操作始终针对主副本，但读取操作可以路由到任何辅助副本，以减少系统负载。

数据也可以跨多个节点水平分区，例如分[片](https://docs.microsoft.com/azure/sql-database/sql-database-elastic-scale-introduction)。 但是，分片化通过将数据吐出许多不易通信的片段，大大增加了操作开销。 管理可能既昂贵又耗时。 它最终可能会影响性能、表联接和参考完整性。

如果数据副本在"高度一致"的关系数据库群集中失去网络连接，您将无法写入数据库。 系统将拒绝写入操作，因为它无法将该更改复制到其他数据副本。 每个数据副本都必须在事务完成之前进行更新。

NoSQL 数据库通常支持高可用性和分区容差。 它们横向扩展，通常跨商品服务器扩展。 这种方法在地理区域内和跨地理区域之间提供巨大的可用性，成本降低。 跨这些计算机或节点对数据进行分区和复制，从而提供冗余和容错能力。 缺点是一致性。 更改一个 NoSQL 节点上的数据可能需要一些时间才能传播到其他节点。 通常，NoSQL 数据库节点会立即响应查询 - 即使显示的数据已过时且尚未更新。

如果数据副本在"高度可用"的 NoSQL 数据库群集中失去连接，您仍然可以完成对数据库的写入操作。 数据库群集将允许写入操作，并在每个数据副本可用时更新它。

这种结果称为最终一致性，这是不支持 ACID 事务的分布式数据系统的一个特征。 在数据项的更新与将该更新传播到每个副本节点所需的时间之间，这是短暂的延迟。 在正常情况下，滞后通常是短的，但当出现问题时可能会增加。 例如，如果要更新美国 NoSQL 数据库中的产品项并从欧洲的副本节点查询同一数据项，会发生什么情况？ 您将收到较早的产品信息，直到群集更新带有产品更改的欧洲节点。 通过立即返回查询结果，而不是等待所有副本节点更新，您可以获得巨大的规模和卷，但可以呈现较旧的数据。

高可用性和大规模可扩展性通常比强一致性对业务更关键。 开发人员可以实施像 Sagas、CQRS 和异步消息传递这样的技术和模式，以拥抱最终的一致性。

> 如今，在约束 CAP 定理约束时必须小心谨慎。 一种称为NewSQL的新型数据库已经扩展了关系数据库引擎，以支持NoSQL系统的横向可扩展性和可扩展性能。

## <a name="considerations-for-relational-vs-nosql-systems"></a>关系与 NoSQL 系统的注意事项

根据特定数据要求，基于云的微服务可以实现关系、NoSQL 数据存储或两者。

|  在以下时间考虑 NoSQL 数据存储： | 在以下时间考虑关系数据库： |
| :-------- | :-------- |
| 您拥有需要大规模的高容量工作负载 | 您的工作负载量是一致的，需要大中型 |
| 您的工作负载不需要 ACID 保证 |  需要 ACID 保证 |
| 您的数据是动态的，并且经常更改 | 您的数据是可预测的，并且结构高度 |
| 数据可以在没有关系的情况下表达 | 数据最好以关系表示 |  
| 您需要快速写入，写入安全性不重要 | 写入安全是一项要求 |  
| 数据检索简单，趋于平面 | 您处理复杂的查询和报表|
| 您的数据需要广泛的地理分布 | 您的用户更集中 |
| 您的应用程序将部署到商用硬件，例如使用公共云 | 您的应用程序将部署到大型高端硬件 |
|||

在下一节中，我们将探讨 Azure 云中可用于存储和管理云原生数据的选项。

## <a name="database-as-a-service"></a>数据库即服务

首先，您可以预配 Azure 虚拟机，并为每个服务安装您选择的数据库。 虽然您可以完全控制环境，但您会放弃云平台的许多内置功能。 您还将负责管理每个服务的虚拟机和数据库。 这种方法可能很快变得耗时且成本高昂。

相反，云原生应用程序倾向于作为[数据库作为服务 （DBaaS）](https://www.stratoscale.com/blog/dbaas/what-is-database-as-a-service/)公开的数据服务。 这些服务完全由云供应商管理，可提供内置的安全性、可扩展性和监视。 您只需将其用作[支持服务](./definition.md#backing-services)，而不是拥有该服务。 提供商大规模运营资源，并负责性能和维护。

它们可以跨云可用性区域和区域进行配置，以实现高可用性。 他们都支持准时的容量和即用即付模式。 Azure 具有不同类型的托管数据服务选项，每个选项都有特定的优势。

我们首先将了解 Azure 中提供的关系 DBaaS 服务。 您将看到 Microsoft 的旗舰 SQL Server 数据库以及几个开源选项都可用。 然后，我们将讨论 Azure 中的 NoSQL 数据服务。

## <a name="azure-relational-databases"></a>Azure 关系数据库

对于需要关系数据的云原生微服务，Azure 提供四个托管关系数据库作为服务 （DBaaS） 产品，如图 5-11 所示。

![Azure 中的托管关系数据库](./media/azure-managed-databases.png)

**图5-11**. Azure 中提供的托管关系数据库

在上图中，请注意每个基础设施如何位于通用 DBaaS 基础结构上，该基础结构具有关键功能，无需额外费用。

这些功能对于提供大量数据库但管理这些数据库的资源有限的组织尤其重要。
通过选择处理核心、内存和基础存储的数量，可以在几分钟内预配 Azure 数据库。 您可以动态扩展数据库并动态调整资源，但停机时间很少或没有停机时间。

## <a name="azure-sql-database"></a>Azure SQL Database

具有 Microsoft SQL Server 专业知识的开发团队应考虑[Azure SQL 数据库](https://docs.microsoft.com/azure/sql-database/)。 它是基于 Microsoft SQL Server 数据库引擎的完全托管关系数据库即服务 （DBaaS）。 该服务共享 SQL Server 的本地版本中的许多功能，并运行 SQL Server 数据库引擎的最新稳定版本。

对于与云原生微服务一起使用，Azure SQL 数据库提供三个部署选项：

- 单个数据库表示在 Azure 云中的 Azure [SQL 数据库服务器上](https://docs.microsoft.com/azure/sql-database/sql-database-servers)运行的完全托管 SQL 数据库。 数据库被视为[*包含*](https://docs.microsoft.com/sql/relational-databases/databases/contained-databases)，因为它对基础数据库服务器上没有配置依赖项。
  
- [托管实例](https://docs.microsoft.com/azure/sql-database/sql-database-managed-instance)是 Microsoft SQL Server 数据库引擎的完全托管实例，它提供与本地 SQL Server 的近 100% 兼容性。 此选项支持更大的数据库（最多 35 TB）并放置在[Azure 虚拟网络中](https://docs.microsoft.com/azure/virtual-network/virtual-networks-overview)以更好的隔离。

- [Azure SQL 数据库无服务器](https://docs.microsoft.com/azure/sql-database/sql-database-serverless)是单个数据库的计算层，该数据库根据工作负载需求自动扩展。 它只对每秒使用的计算量进行账单。 该服务非常适合间歇性、不可预知的使用模式的工作负载，这些工作负载穿插于不活动期。 无服务器计算层还会在非活动期间自动暂停数据库，以便只收取存储费用。 当活动返回时，它会自动恢复。

除了传统的 Microsoft SQL Server 堆栈之外，Azure 还具有三个常用开源数据库的托管版本。

## <a name="open-source-databases-in-azure"></a>Azure 中的开源数据库

开源关系数据库已成为云原生应用程序的热门选择。 许多企业比商业数据库产品更青睐它们，尤其是为了节省成本。 许多开发团队都享有灵活性、社区支持的开发以及工具和扩展的生态系统。 开源数据库可以跨多个云提供商部署，有助于最大限度地减少"供应商锁定"的问题。

开发人员可以轻松地在 Azure VM 上自承载任何开源数据库。 在提供完全控制的同时，此方法使您能够对数据库和 VM 的管理、监视和维护。

但是，Microsoft 继续致力于将 Azure 作为*完全托管*的 DBaaS 服务提供几个流行的开源数据库，从而保持 Azure 的"开放平台"。

### <a name="azure-database-for-mysql"></a>Azure Database for MySQL

[MySQL](https://en.wikipedia.org/wiki/MySQL) 是一个开源关系数据库，是[建立在LAMP软件堆栈](https://en.wikipedia.org/wiki/LAMP_(software_bundle))上的应用程序的支柱。 广泛选择*阅读繁重的*工作量，它被许多大型组织使用，包括Facebook，Twitter和YouTube。 社区版免费提供，而企业版需要购买许可证。 该产品最初创建于1995年，于2008年被Sun微系统公司购买。 甲骨文于2010年收购了Sun和MySQL。

[MySQL 的 Azure 数据库](https://azure.microsoft.com/services/mysql/)是基于开源 MySQL Server 引擎的托管关系数据库服务。 它使用 MySQL 社区版本。 Azure MySQL 服务器是服务的管理点。 它与用于本地部署的 MySQL 服务器引擎相同。 引擎可以创建每个服务器的单个数据库，也可以创建每个共享资源的服务器的多个数据库。 您可以继续使用相同的开源工具管理数据，而无需学习新技能或管理虚拟机。

### <a name="azure-database-for-mariadb"></a>Azure Database for MariaDB

[玛丽亚DB](https://mariadb.com/)服务器是另一个流行的开源数据库服务器。 当甲骨文收购拥有MySQL的太阳微系统公司时，它被创建为MySQL的*分叉*。 目的是确保MariaDB保持开放源码。 由于 MariaDB 是 MySQL 的分叉，因此数据和表定义是兼容的，并且客户端协议、结构和 API 是紧密相连的。

MariaDB 拥有强大的社区，被许多大型企业所使用。 当 Oracle 继续维护、增强和支持 MySQL 时，MariaDB 基金会管理 MariaDB，允许对产品和文档进行公共贡献。

[MariaDB 的 Azure 数据库](https://azure.microsoft.com/services/mariadb/)是 Azure 云中完全托管的关系数据库，即服务。 该服务基于 MariaDB 社区版服务器引擎。 它能够处理任务关键型工作负载，具有可预测的性能和动态可扩展性。

### <a name="azure-database-for-postgresql"></a>Azure Database for PostgreSQL

[PostgreSQL](https://www.postgresql.org/)是一个开源关系数据库，拥有超过 30 年的积极发展。 PostgresSQL 在可靠性和数据完整性方面享有盛誉。 它功能丰富、SQL 兼容，并且被认为比 MySQL 更具性能- 尤其对于具有复杂查询和大量写入的工作负载。 许多大型企业，包括苹果，红帽和富士通已经建立了产品使用PostgreSQL。

[基于开源 Postgres 数据库引擎的 PostgreSQL Azure 数据库](https://azure.microsoft.com/services/postgresql/)是一个完全托管的关系数据库服务。 该服务支持许多开发平台，包括C++、Java、Python、Node、C\#和 PHP。 您可以使用[命令行接口](https://datamigration.microsoft.com/scenario/postgresql-to-azurepostgresql?step=1)工具或 Azure 数据迁移服务将 PostgreSQL 数据库迁移到该数据库。

用于 PostgreSQL 的 Azure 数据库提供两个部署选项：

- [单服务器](https://docs.microsoft.com/azure/postgresql/concepts-servers)部署选项是多个数据库的中心管理点，您可以向其部署多个数据库。 定价基于内核和存储，按服务器进行结构化。

- [超大规模 （Citus） 选项](https://azure.microsoft.com/blog/get-high-performance-scaling-for-your-azure-database-workloads-with-hyperscale/)由 Citus 数据技术提供支持。 通过跨数百个节点*水平扩展*单个数据库，实现高性能，从而提供快速性能和扩展。 此选项允许引擎在内存中容纳更多数据，跨数百个节点并行化查询，并更快地索引数据。

## <a name="nosql-data-in-azure"></a>Azure 中的无 SQL 数据

Cosmos DB 是 Azure 云中完全托管的全局分布的 NoSQL 数据库服务。 它已被世界各地的许多大公司采用，包括可口可乐、Skype、埃克森美孚和自由互助。

如果您的服务需要来自世界任何地方的快速响应、高可用性或弹性可扩展性，Cosmos DB 是一个很好的选择。 图 5-12 显示了宇宙 DB。

![宇宙 DB 概述](./media/cosmos-db-overview.png)

**图5-12**：宇宙DB概述

上图显示了 Cosmos DB 中可用的许多内置云原生功能。 在本节中，我们将仔细研究它们。

### <a name="global-support"></a>全球支持

云原生应用程序通常具有全球受众，需要全球扩展。

您可以跨地区或在世界各地分发 Cosmos 数据库，将数据放在用户附近，缩短响应时间并减少延迟。 您可以在不暂停或重新部署服务的情况下从区域添加或删除数据库。 在后台，Cosmos DB 透明地将数据复制到每个配置的区域。

Cosmos DB 支持全局级别的[活动/主动](https://kemptechnologies.com/white-papers/unfog-confusion-active-passive-activeactive-load-balancing/)群集，使您能够配置任何数据库区域以支持*写入和读取*。

[多主协议](https://docs.microsoft.com/azure/cosmos-db/multi-master-benefits)是 Cosmos DB 中的一个重要功能，可实现以下功能：

- 无限弹性写入和读取可伸缩性。

- 在全球 99.999% 的读写可用性。

- 在 99% 的时间内，在 10 毫秒内为读写提供服务。

使用 Cosmos DB[多宿主 API，](https://docs.microsoft.com/azure/cosmos-db/distribute-data-globally)微服务会自动知道最近的 Azure 区域并向其发送请求。 最近的区域由 Cosmos DB 标识，无需进行任何配置更改。 如果区域不可用，多宿主功能将自动将请求路由到下一个最近的可用区域。

### <a name="multi-model-support"></a>多型号支持

将单片应用程序重新编程到云原生体系结构时，开发团队有时必须迁移开源 NoSQL 数据存储。 Cosmos DB 可帮助您通过其*多模型*数据平台在这些 NoSQL 数据存储中保留投资。 图 5-13 显示了支持的 NoSQL[兼容性 API](https://www.wikiwand.com/en/Cosmos_DB)。

![宇宙数据库提供程序](./media/cosmos-db-providers.png)

**图 5-13**： 宇宙数据库提供程序

开发团队可以将现有的蒙戈、格雷姆林或卡桑德拉数据库迁移到 Cosmos DB，只需对数据或代码进行最少的更改。 对于新应用，开发团队可以选择开源选项或内置 SQL API 模型。

> 在内部，Cosmos 以由原始数据类型组成的简单结构格式存储数据。 对于每个请求，数据库引擎都会将原始数据转换为您选择的模型表示形式。

在上图 5-13 中，请注意[表 API](https://docs.microsoft.com/azure/cosmos-db/table-introduction)选项。 此 API 是 Azure 表存储的演变。 两者共享相同的基础表模型，但 Cosmos DB 表 API 添加了 Azure 存储 API 中不可用的高级增强功能。 这些功能在图 5-4 中进行了对比。

![Azure 表 API](media/azure-table-api.png)

**图 5-14**： Azure 表 API 提供程序

使用 Azure 表存储的微服务可以轻松地迁移到 Cosmos DB 表 API。 不需更改代码。

### <a name="tunable-consistency"></a>可调一致性

在 *"关系与NoSQL"* 部分的早些时候，我们讨论了*数据一致性*的主题。 数据一致性是指数据*的完整性*。 具有分布式数据的云原生服务依赖于复制，必须在读取一致性、可用性和延迟之间做出根本性的权衡。

大多数分布式数据库允许开发人员在两种一致性模型之间进行选择：强一致性和最终一致性。 *强一致性*是数据可编程性的黄金标准。 它保证查询将始终返回最新的数据 - 即使系统必须产生延迟等待更新在所有数据库副本之间复制。 虽然为*最终一致性*配置的数据库将立即返回数据，即使该数据不是最新的副本。 后一个选项可实现更高的可用性、更大的规模和更高的性能。

Azure Cosmos DB 提供了图 5-15 所示的五个定义良好的[一致性模型](https://docs.microsoft.com/azure/cosmos-db/consistency-levels)。

![宇宙 DB 一致性图](./media/cosmos-consistency-level-graph.png)

**图 5-15**： 宇宙 DB 一致性级别

 这些选项使您能够对数据的一致性、可用性和性能做出精确的选择和精细权衡。 图 5-16 描述了每个级别。

![宇宙数据库一致性级别](./media/cosmos-db-consistency-levels.png)

**图 5-16**： 宇宙 DB 一致性级别描述

在["9球背后：宇宙DB一致性水平解释"](https://blog.jeremylikness.com/blog/2018-03-23_getting-behind-the-9ball-cosmosdb-consistency-levels/)一文中，微软云开发者倡导者Jeremy Likeness对五种模型给出了极好的解释。

### <a name="partitioning"></a>分区

Azure Cosmos DB 采用自动[分区](https://docs.microsoft.com/azure/cosmos-db/partitioning-overview)来扩展数据库以满足云原生服务的性能需求。

通过创建数据库、容器和项来管理 Cosmos DB 数据中的数据。

容器位于 Cosmos DB 数据库中，表示与架构无关的项目分组。 项是添加到容器中的数据。 它们表示为文档、行、节点或边。 添加到容器的所有项目都将自动编制索引。

要对容器进行分区，项被划分为称为逻辑分区的不同子集。 逻辑分区是根据与容器中的每个项关联的分区键的值填充的。 图 5-18 显示了两个容器，每个容器都有一个基于分区键值的逻辑分区。

![宇宙数据库分区机制](./media/cosmos-db-partitioning.png)

**图 5-18**： 宇宙 DB 分区机制

请注意，在上图中，每个项目如何包含"城市"或"机场"的分区键。 键确定项的逻辑分区。 带有城市代码的项目将分配给左侧的容器，以及带有机场代码的项目分配给右侧的容器。 将分区键值与 ID 值合并将创建项的索引，该索引唯一地标识项。

在内部，Cosmos DB 自动管理[物理分区上的逻辑分区](https://docs.microsoft.com/azure/cosmos-db/partition-data)放置，以满足容器的可伸缩性和性能需求。 随着应用程序吞吐量和存储要求的提高，Azure Cosmos DB 会跨更多服务器重新分发逻辑分区。 重新分发操作由 Cosmos DB 管理，并在不中断或停机的情况下调用。

## <a name="newsql-databases"></a>新建 SQL 数据库

*NewSQL* 是一种新兴的数据库技术，它将 NoSQL 的分布式可扩展性与关系数据库的 ACID 保证相结合。 NewSQL 数据库对于必须在分布式环境中处理大量数据的业务系统非常重要，这些系统具有完全的事务支持和 ACID 合规性。 虽然 NoSQL 数据库可以提供海量可伸缩性，但它不能保证数据一致性。 数据不一致的间歇性问题可能会给开发团队带来负担。 开发人员必须在微服务代码中构造安全措施，以管理由不一致数据引起的问题。

云原生计算基础 （CNCF） 具有多个新 SQL 数据库项目。

| Project | 特征 |
| :-------- | :-------- |
| 蟑螂 DB |符合 ACID 的、全局扩展的关系数据库。 向群集添加新节点，而 CockroachDB 负责平衡跨实例和地理位置的数据。 它创建、管理和分发副本以确保可靠性。 它是开源的，免费提供。  |
| 提亚布 | 支持混合事务和分析处理 （HTAP） 工作负载的开源数据库。 它与 MySQL 兼容，具有水平可扩展性、强一致性和高可用性。  TiDB 充当 MySQL 服务器。 您可以继续使用现有的 MySQL 客户端库，而无需对应用程序进行大量代码更改。 |
| 尤加字节开发银行 | 开源、高性能、分布式 SQL 数据库。 它支持低查询延迟、抵御故障的弹性和全局数据分发。 YugabyDB 与后回归 SQL 兼容，可处理横向扩展 RDBMS 和 Internet 规模 OLTP 工作负载。 该产品还支持NoSQL，并与卡桑德拉兼容。 |
|维特斯 | ViTES 是一种数据库解决方案，用于部署、缩放和管理大型 MySQL 实例群集。 它可以在公共或私有云体系结构中运行。 它结合了并扩展了许多重要的 MySQL 功能，并具有垂直和水平分片支持功能。 Vites源自YouTube，自2011年以来一直提供所有YouTube数据库流量。 |

上图中的开源项目可从云原生计算基金会获得。 其中三种产品是完整的数据库产品，其中包括 .NET Core 支持。 另一个 Vites 是一个数据库群集系统，它水平缩放 MySQL 实例的大型群集。

NewSQL 数据库的关键设计目标是利用平台的弹性和可扩展性，在 Kubernetes 中本机工作。

NewSQL 数据库旨在在短暂的云环境中蓬勃发展，在临时云环境中，基础虚拟机可在接到通知后立即重新启动或重新安排。 数据库旨在抵御节点故障，而不会丢失数据或停机。 例如，CockroachDB 通过在群集中的节点上维护任何数据的三个一致副本，能够经受住计算机损失。

Kubernetes 使用*服务构造*允许客户端从单个 DNS 条目处理一组相同的 NewSQL 数据库进程。 通过将数据库实例与与其关联的服务地址分离，我们可以在不中断现有应用程序实例的情况下进行扩展。 在给定时间向任何服务发送请求将始终产生相同的结果。

在这种情况下，所有数据库实例都是相等的。 没有主关系或次要关系。 在 CockroachDB 中找到*的协商一致复制*等技术允许任何数据库节点处理任何请求。 如果接收负载平衡请求的节点具有本地所需的数据，它将立即响应。 如果没有，节点将成为网关，并将请求转发到相应的节点以获得正确答案。 从客户端的角度来看，每个数据库节点都是一样的：它们显示为单个*逻辑*数据库，具有单机系统的一致性保证，尽管有数十个甚至数百个节点在幕后工作。

有关 NewSQL 数据库背后的机制的详细信息，请参阅[DASH：库伯内斯-本机数据库的四个属性](https://thenewstack.io/dash-four-properties-of-kubernetes-native-databases/)一文。

## <a name="data-migration-to-the-cloud"></a>数据迁移到云

更耗时的任务之一是从一个数据平台将数据迁移到另一个数据平台。 [Azure 数据迁移服务](https://azure.microsoft.com/services/database-migration/)可帮助加快此类工作。 它可以将数据从多个外部数据库源迁移到 Azure 数据平台，但停机时间最少。 目标平台包括以下服务：

- Azure SQL Database
- Azure Database for MySQL
- Azure Database for MariaDB
- Azure Database for PostgreSQL
- CosmosDB
  
该服务提供建议，指导您完成执行迁移所需的更改，无论是小还是大。

>[!div class="step-by-step"]
>[上一页](database-per-microservice.md)
>[下一页](azure-caching.md)
