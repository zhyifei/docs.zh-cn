---
title: 将关系数据库迁移到 azure
description: 更新现有的.NET 应用程序与 Azure 云和 Windows 容器 |将关系数据库迁移到 azure
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 04/28/2018
ms.openlocfilehash: fe1bf5820c2306beb380749b34d5a56964e016e4
ms.sourcegitcommit: 88f251b08bf0718ce119f3d7302f514b74895038
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/10/2018
ms.locfileid: "33956080"
---
# <a name="migrate-your-relational-databases-to-azure"></a><span data-ttu-id="159b5-103">将关系数据库迁移到 azure</span><span class="sxs-lookup"><span data-stu-id="159b5-103">Migrate your relational databases to azure</span></span>

<span data-ttu-id="159b5-104">设想： Azure 提供最全面的数据库迁移。</span><span class="sxs-lookup"><span data-stu-id="159b5-104">Vision: Azure offers the most comprehensive database migration.</span></span>

<span data-ttu-id="159b5-105">在 Azure 中，你可以将您的数据库服务器迁移直接到 IaaS Vm （纯提起并移动），或可以为其他好处迁移到 Azure SQL 数据库。</span><span class="sxs-lookup"><span data-stu-id="159b5-105">In Azure, you can migrate your database servers directly to IaaS VMs (pure lift and shift), or you can migrate to Azure SQL Database, for additional benefits.</span></span> <span data-ttu-id="159b5-106">Azure SQL 数据库提供托管的实例和完整数据库作为-服务 (DBaaS) 选项。</span><span class="sxs-lookup"><span data-stu-id="159b5-106">Azure SQL Database offers managed instance and full database-as-a-service (DBaaS) options.</span></span> <span data-ttu-id="159b5-107">图 3-1 显示多个关系数据库在 Azure 中可用的迁移路径。</span><span class="sxs-lookup"><span data-stu-id="159b5-107">Figure 3-1 shows the multiple relational database migration paths available in Azure.</span></span>

![在 Azure 中的数据库迁移路径](./media/image3-1.png)

> <span data-ttu-id="159b5-109">**图 3-1。**</span><span class="sxs-lookup"><span data-stu-id="159b5-109">**Figure 3-1.**</span></span> <span data-ttu-id="159b5-110">在 Azure 中的数据库迁移路径</span><span class="sxs-lookup"><span data-stu-id="159b5-110">Database migration paths in Azure</span></span>

## <a name="when-to-migrate-to-azure-sql-database-managed-instance"></a><span data-ttu-id="159b5-111">何时将迁移到 Azure SQL 数据库托管实例</span><span class="sxs-lookup"><span data-stu-id="159b5-111">When to migrate to Azure SQL Database Managed Instance</span></span>

<span data-ttu-id="159b5-112">在大多数情况下，Azure SQL 数据库托管实例将最好的选择将你的数据迁移到 Azure 时要考虑。</span><span class="sxs-lookup"><span data-stu-id="159b5-112">In most cases, Azure SQL Database Managed Instance will be your best option to consider when you migrate your data to Azure.</span></span> <span data-ttu-id="159b5-113">如果您要迁移 SQL Server 数据库，并且需要几乎无需构建你的应用程序或对您的数据或数据访问代码进行更改的 100%保障，选择 Azure SQL 数据库的托管实例功能。</span><span class="sxs-lookup"><span data-stu-id="159b5-113">If you are migrating SQL Server databases and need nearly 100% assurance that you won't need to rearchitect your application or make changes to your data or data access code, choose the Managed Instance feature of Azure SQL Database.</span></span>

<span data-ttu-id="159b5-114">如果你有其他要求 SQL Server 实例级功能或超出标准的 Azure SQL 数据库 （单个数据库模型） 中提供的功能的隔离要求，azure SQL 数据库托管实例是最佳选项。</span><span class="sxs-lookup"><span data-stu-id="159b5-114">Azure SQL Database Managed Instance is the best option if you have additional requirements for SQL Server instance-level functionality, or isolation requirements beyond the features provided in a standard Azure SQL Database (single database model).</span></span> <span data-ttu-id="159b5-115">此最后一项的最面向 PaaS 的选择，但它不提供与传统的 SQL server 的相同的功能。</span><span class="sxs-lookup"><span data-stu-id="159b5-115">This last one is the most PaaS-oriented choice, but it doesn't offer the same features as that of a traditional SQL server.</span></span> <span data-ttu-id="159b5-116">迁移可能会出现 frictions。</span><span class="sxs-lookup"><span data-stu-id="159b5-116">Migration might surface frictions.</span></span>

<span data-ttu-id="159b5-117">例如，组织已深层投资实例级 SQL Server 功能受益从迁移到 SQL 托管实例。</span><span class="sxs-lookup"><span data-stu-id="159b5-117">For example, an organization that has made deep investments in instance-level SQL Server capabilities would benefit from migrating to SQL Managed Instance.</span></span> <span data-ttu-id="159b5-118">实例级 SQL Server 功能的示例包括 SQL 公共语言运行时 (CLR) 集成，SQL Server 代理，以及跨数据库查询。</span><span class="sxs-lookup"><span data-stu-id="159b5-118">Examples of instance-level SQL Server capabilities include SQL common language runtime (CLR) integration, SQL Server Agent, and cross-database querying.</span></span> <span data-ttu-id="159b5-119">对这些功能的支持不是可用标准的 Azure SQL 数据库 （单一数据库模型） 中。</span><span class="sxs-lookup"><span data-stu-id="159b5-119">Support for these features is not available in standard Azure SQL Database (a single-database model).</span></span>

<span data-ttu-id="159b5-120">操作在高度管控行业中，且需要维护隔离出于安全考虑，组织还可能受益于选择的 SQL 托管实例模式。</span><span class="sxs-lookup"><span data-stu-id="159b5-120">An organization that operates in a highly regulated industry, and which needs to maintain isolation for security purposes, also might benefit from choosing the SQL Managed Instance model.</span></span>

<span data-ttu-id="159b5-121">Azure SQL 数据库中的托管的实例具有以下特征：</span><span class="sxs-lookup"><span data-stu-id="159b5-121">Managed Instance in Azure SQL Database has the following characteristics:</span></span>

- <span data-ttu-id="159b5-122">通过 Azure 虚拟网络的安全隔离</span><span class="sxs-lookup"><span data-stu-id="159b5-122">Security isolation through Azure Virtual Network</span></span>

- <span data-ttu-id="159b5-123">应用程序图面兼容性，具有这些功能：</span><span class="sxs-lookup"><span data-stu-id="159b5-123">Application surface compatibility, with these features:</span></span>

  - <span data-ttu-id="159b5-124">SQL Server 代理和 SQL Server 事件探查器</span><span class="sxs-lookup"><span data-stu-id="159b5-124">SQL Server Agent and SQL Server Profiler</span></span>

  - <span data-ttu-id="159b5-125">跨数据库引用和查询，SQL CLR 复制、 变更数据捕获 (CDC) 和 Service Broker</span><span class="sxs-lookup"><span data-stu-id="159b5-125">Cross-database references and queries, SQL CLR, replication, change data capture (CDC), and Service Broker</span></span>

- <span data-ttu-id="159b5-126">数据库大小最多 35 TB</span><span class="sxs-lookup"><span data-stu-id="159b5-126">Database sizes up to 35 TB</span></span>

- <span data-ttu-id="159b5-127">使用这些功能的最小停机时间迁移：</span><span class="sxs-lookup"><span data-stu-id="159b5-127">Minimum-downtime migration, with these features:</span></span>

  - <span data-ttu-id="159b5-128">Azure 数据库迁移服务</span><span class="sxs-lookup"><span data-stu-id="159b5-128">Azure Database Migration Service</span></span>

  - <span data-ttu-id="159b5-129">本机备份和还原和日志传送</span><span class="sxs-lookup"><span data-stu-id="159b5-129">Native backup and restore, and log shipping</span></span>

<span data-ttu-id="159b5-130">使用这些功能，当将现有应用程序数据库迁移到 Azure SQL 数据库的托管实例模型就提供近 100%的 Paas 的优势的 SQL Server。</span><span class="sxs-lookup"><span data-stu-id="159b5-130">With these capabilities, when you migrate existing application databases to Azure SQL Database, the Managed Instance model offers nearly 100% of the benefits of Paas for SQL Server.</span></span> <span data-ttu-id="159b5-131">托管的实例是继续使用实例级功能，而无需更改应用程序设计的其中一个 SQL Server 环境。</span><span class="sxs-lookup"><span data-stu-id="159b5-131">Managed Instance is a SQL Server environment where you continue using instance-level capabilities without changing your application design.</span></span>

<span data-ttu-id="159b5-132">托管的实例可能是最适合企业，当前正在使用 SQL Server，并且其需要灵活地在云中其网络安全。</span><span class="sxs-lookup"><span data-stu-id="159b5-132">Managed Instance is probably the best fit for enterprises that currently are using SQL Server, and which require flexibility in their network security in the cloud.</span></span> <span data-ttu-id="159b5-133">这就像有你的 SQL 数据库的专用虚拟网络。</span><span class="sxs-lookup"><span data-stu-id="159b5-133">It's like having a private virtual network for your SQL databases.</span></span>

## <a name="when-to-migrate-to-azure-sql-database"></a><span data-ttu-id="159b5-134">何时迁移到 Azure SQL Database</span><span class="sxs-lookup"><span data-stu-id="159b5-134">When to migrate to Azure SQL Database</span></span>

<span data-ttu-id="159b5-135">如前文所述，标准的 Azure SQL 数据库是完全托管的、 关系 DBaaS。</span><span class="sxs-lookup"><span data-stu-id="159b5-135">As mentioned, the standard Azure SQL Database is a fully managed, relational DBaaS.</span></span> <span data-ttu-id="159b5-136">SQL 数据库当前 38 与世界各地的数据中心管理数以百万计的生产数据库。</span><span class="sxs-lookup"><span data-stu-id="159b5-136">SQL Database currently manages millions of production databases, across 38 datacenters, around the world.</span></span> <span data-ttu-id="159b5-137">它支持广泛的应用程序和工作负荷，从管理简单的事务数据，为驱动的数据最密集、 任务关键型应用程序需要在全球范围内的高级的数据处理。</span><span class="sxs-lookup"><span data-stu-id="159b5-137">It supports a broad range of applications and workloads, from managing straightforward transactional data, to driving the most data-intensive, mission-critical applications that require advanced data processing at a global scale.</span></span>

<span data-ttu-id="159b5-138">由于其完整的 PaaS 功能，更好地定价-并最终降低成本-你应该将移到标准的 Azure SQL 数据库作为你": 默认情况下选择"如果你有一个应用程序，该使用基本、 标准 SQL 数据库和任何其他实例功能。</span><span class="sxs-lookup"><span data-stu-id="159b5-138">Because of its full PaaS features, better pricing-and ultimately lower cost-you should move to the standard Azure SQL Database as your "by-default choice" if you have an application that uses basic, standard SQL databases, and no additional instance features.</span></span> <span data-ttu-id="159b5-139">标准的 Azure SQL 数据库中不支持 SQL CLR 集成、 SQL Server 代理和跨数据库查询等的 SQL Server 功能。</span><span class="sxs-lookup"><span data-stu-id="159b5-139">SQL Server features like SQL CLR integration, SQL Server Agent, and cross-database querying are not supported in the standard Azure SQL Database.</span></span> <span data-ttu-id="159b5-140">仅在 Azure SQL 数据库托管实例模型中提供了这些功能。</span><span class="sxs-lookup"><span data-stu-id="159b5-140">Those features are available only in the Azure SQL Database Managed Instance model.</span></span>

<span data-ttu-id="159b5-141">Azure SQL 数据库是为应用程序开发人员生成的仅智能云数据库服务。</span><span class="sxs-lookup"><span data-stu-id="159b5-141">Azure SQL Database is the only intelligent cloud database service that's built for app developers.</span></span> <span data-ttu-id="159b5-142">它也是缩放上快速，而无需停机，来帮助你高效地提供多租户应用程序的唯一云数据库服务。</span><span class="sxs-lookup"><span data-stu-id="159b5-142">It's also the only cloud database service that scales on-the-fly, without downtime, to help you efficiently deliver multitenant apps.</span></span> <span data-ttu-id="159b5-143">从根本上讲，Azure SQL 数据库会使你更多的时间，以创新，并因此加快了上市时间。</span><span class="sxs-lookup"><span data-stu-id="159b5-143">Ultimately, Azure SQL Database leaves you more time to innovate, and it accelerates your time to market.</span></span> <span data-ttu-id="159b5-144">可以生成安全的应用，还可以使用的语言和平台所需连接到你的 SQL 数据库。</span><span class="sxs-lookup"><span data-stu-id="159b5-144">You can build secure apps and connect to your SQL database by using the languages and platforms that you prefer.</span></span>

<span data-ttu-id="159b5-145">Azure SQL 数据库提供以下好处：</span><span class="sxs-lookup"><span data-stu-id="159b5-145">Azure SQL Database offers the following benefits:</span></span>

- <span data-ttu-id="159b5-146">了解和适应你的应用程序的内置智能 （机器学习）</span><span class="sxs-lookup"><span data-stu-id="159b5-146">Built-in intelligence (machine learning) that learns and adapts to your app</span></span>

- <span data-ttu-id="159b5-147">按需数据库设置</span><span class="sxs-lookup"><span data-stu-id="159b5-147">On-demand database provisioning</span></span>

- <span data-ttu-id="159b5-148">一系列的优惠，为所有工作负荷</span><span class="sxs-lookup"><span data-stu-id="159b5-148">A range of offers, for all workloads</span></span>

- <span data-ttu-id="159b5-149">99.99%的可用性 SLA，零维护</span><span class="sxs-lookup"><span data-stu-id="159b5-149">99.99% availability SLA, zero maintenance</span></span>

- <span data-ttu-id="159b5-150">异地复制和还原服务的数据保护</span><span class="sxs-lookup"><span data-stu-id="159b5-150">Geo-replication and restore services for data protection</span></span>

- <span data-ttu-id="159b5-151">Azure SQL 数据库点时间还原功能</span><span class="sxs-lookup"><span data-stu-id="159b5-151">Azure SQL Database Point in Time Restore feature</span></span>

- <span data-ttu-id="159b5-152">与 SQL Server 2016，包括混合和迁移的兼容性</span><span class="sxs-lookup"><span data-stu-id="159b5-152">Compatibility with SQL Server 2016, including hybrid and migration</span></span>

<span data-ttu-id="159b5-153">标准的 Azure SQL Database 是更接近于 PaaS 比 Azure SQL 数据库托管实例。</span><span class="sxs-lookup"><span data-stu-id="159b5-153">The standard Azure SQL Database is closer to PaaS than Azure SQL Database Managed Instance.</span></span> <span data-ttu-id="159b5-154">更喜欢标准的 Azure SQL 数据库，因为你将从托管云中获取更多好处。</span><span class="sxs-lookup"><span data-stu-id="159b5-154">Prefer the standard Azure SQL Database because you'll get more benefits from a managed cloud.</span></span> <span data-ttu-id="159b5-155">但是，Azure SQL 数据库已从常规的主要区别和本地 SQL Server 实例。</span><span class="sxs-lookup"><span data-stu-id="159b5-155">However, Azure SQL Database has some key differences from regular and on-premises SQL Server instances.</span></span> <span data-ttu-id="159b5-156">根据现有应用程序的数据库要求和你的企业要求和策略，它可能规划你迁移到云时不是最佳选择。</span><span class="sxs-lookup"><span data-stu-id="159b5-156">Depending on your existing application's database requirements, and your enterprise requirements and policies, it might not be the best choice when you are planning your migration to the cloud.</span></span>

## <a name="when-to-move-your-original-rdbms-to-a-vm-iaas"></a><span data-ttu-id="159b5-157">何时将原始 RDBMS 移到虚拟机 (IaaS)</span><span class="sxs-lookup"><span data-stu-id="159b5-157">When to move your original RDBMS to a VM (IaaS)</span></span>

<span data-ttu-id="159b5-158">迁移选项之一是将你原始关系数据库管理系统 (RDBMS)，包括 Oracle、 IBM DB2、 MySQL、 PostgreSQL、 或 SQL Server，到在 Azure VM 运行的类似服务器。</span><span class="sxs-lookup"><span data-stu-id="159b5-158">One of your migration options is to move your original relational database management system (RDBMS), including Oracle, IBM DB2, MySQL, PostgreSQL, or SQL Server, to a similar server that's running on an Azure VM.</span></span> <span data-ttu-id="159b5-159">如果你的所有需要最快迁移到云中，而最小的更改或不需要更改的现有应用，直接迁移到云中的 IaaS 可能是合理的选项。</span><span class="sxs-lookup"><span data-stu-id="159b5-159">If you have existing applications that require the fastest migration to the cloud with minimal changes, or no changes at all, a direct migration to IaaS in the cloud might be a fair option.</span></span> <span data-ttu-id="159b5-160">它可能不会利用的所有云的优势的最佳方法，但它可能是最快的初始路径。</span><span class="sxs-lookup"><span data-stu-id="159b5-160">It might not be the best way to take advantage of all the cloud's benefits, but it's probably the fastest initial path.</span></span>

<span data-ttu-id="159b5-161">当前，Microsoft Azure 支持最多[331 不同数据库服务器](https://azuremarketplace.microsoft.com/en-us/marketplace/apps/category/databases?page=1&subcategories=databases-all)作为 IaaS Vm 部署。</span><span class="sxs-lookup"><span data-stu-id="159b5-161">Currently, Microsoft Azure supports up to [331 different database servers](https://azuremarketplace.microsoft.com/en-us/marketplace/apps/category/databases?page=1&subcategories=databases-all) deployed as IaaS VMs.</span></span> <span data-ttu-id="159b5-162">其中包括 SQL Server、 Oracle、 MySQL、 PostgreSQL、 和 IBM DB2，等的常用 RDBMS 和如 MongoDB、 Cassandra、 DataStax、 MariaDB 和 Cloudera 的许多其他 NoSQL 数据库。</span><span class="sxs-lookup"><span data-stu-id="159b5-162">These include popular RDBMS like SQL Server, Oracle, MySQL, PostgreSQL, and IBM DB2, and many other NoSQL databases like MongoDB, Cassandra, DataStax, MariaDB, and Cloudera.</span></span>

> [!NOTE]
> <span data-ttu-id="159b5-163">尽管移动到 Azure VM RDBMS 可能将你的数据迁移到云 （因为它是 IaaS） 的最快方法，此方法需要大量的投资，在你的 IT 团队 （数据库管理员和 IT 专业人员）。</span><span class="sxs-lookup"><span data-stu-id="159b5-163">Although moving your RDBMS to an Azure VM might be the fastest way to migrate your data to the cloud (because it is IaaS), this approach requires a significant investment in your IT teams (database administrators and IT pros).</span></span> <span data-ttu-id="159b5-164">企业团队需要能够设置和管理高可用性、 灾难恢复和 SQL Server 的修补。</span><span class="sxs-lookup"><span data-stu-id="159b5-164">Enterprise teams need to be able to set up and manage high availability, disaster recovery, and patching for SQL Server.</span></span> <span data-ttu-id="159b5-165">此上下文还需要具有完全管理权限的自定义的环境。</span><span class="sxs-lookup"><span data-stu-id="159b5-165">This context also needs a customized environment, with full administrative rights.</span></span>

## <a name="when-to-migrate-to-sql-server-as-a-vm-iaas"></a><span data-ttu-id="159b5-166">何时迁移到 SQL Server 作为虚拟机 (IaaS)</span><span class="sxs-lookup"><span data-stu-id="159b5-166">When to migrate to SQL Server as a VM (IaaS)</span></span>

<span data-ttu-id="159b5-167">可能有少数情况下，仍需要将迁移到 SQL Server 作为正则 VM。</span><span class="sxs-lookup"><span data-stu-id="159b5-167">There might be a few cases where you still need to migrate to SQL Server as a regular VM.</span></span> <span data-ttu-id="159b5-168">示例方案是如果你需要使用 SQL Server Reporting Services。</span><span class="sxs-lookup"><span data-stu-id="159b5-168">An example scenario is if you need to use SQL Server Reporting Services.</span></span> <span data-ttu-id="159b5-169">在大多数情况下，不过，Azure SQL 数据库托管实例可以提供你需要将从本地 SQL 服务器迁移，因此迁移到 SQL Server 虚拟机应该尝试你最后一招所有内容。</span><span class="sxs-lookup"><span data-stu-id="159b5-169">In most cases, though, Azure SQL Database Managed Instance can provide everything you need to migrate from on-premises SQL servers, so migration to a SQL Server VM should be your last resort to try.</span></span>

## <a name="use-azure-database-migration-service-to-migrate-your-relational-databases-to-azure"></a><span data-ttu-id="159b5-170">使用 Azure 数据库迁移服务将关系数据库迁移到 Azure</span><span class="sxs-lookup"><span data-stu-id="159b5-170">Use Azure Database Migration Service to migrate your relational databases to Azure</span></span> 

<span data-ttu-id="159b5-171">可以使用 Azure 数据库迁移服务将 SQL Server、 Oracle 和 MySQL 如关系数据库迁移到 Azure，无论你的目标数据库是 Azure SQL 数据库、 Azure SQL 数据库托管实例或在 Azure VM 上的 SQL Server。</span><span class="sxs-lookup"><span data-stu-id="159b5-171">You can use Azure Database Migration Service to migrate relational databases like SQL Server, Oracle, and MySQL to Azure, whether your target database is Azure SQL Database, Azure SQL Database Managed Instance, or SQL Server on an Azure VM.</span></span>

<span data-ttu-id="159b5-172">自动工作流，通过评估报告，将指导您完成需要迁移数据库之前进行的更改。</span><span class="sxs-lookup"><span data-stu-id="159b5-172">The automated workflow, with assessment reporting, guides you through the changes you need to make before you migrate the database.</span></span> <span data-ttu-id="159b5-173">准备就绪后，服务会将源数据库迁移到 Azure。</span><span class="sxs-lookup"><span data-stu-id="159b5-173">When you are ready, the service migrates the source database to Azure.</span></span>

<span data-ttu-id="159b5-174">每当你更改原始 RDBMS，你可能需要重新测试。</span><span class="sxs-lookup"><span data-stu-id="159b5-174">Whenever you change an original RDBMS, you might need to retest.</span></span> <span data-ttu-id="159b5-175">你还可能需要更改的 SQL 句子或应用程序，具体取决于测试结果中的对象关系映射 (ORM) 代码。</span><span class="sxs-lookup"><span data-stu-id="159b5-175">You also might need to change the SQL sentences or Object-Relational Mapping (ORM) code in your application, depending on testing results.</span></span>

<span data-ttu-id="159b5-176">如果你有任何其他数据库 (例如，IBM DB2)，并且你选择提起并移动方法，你可能想要继续使用这些数据库作为 IaaS Vm 在 Azure 中，除非您愿意为执行更复杂的数据迁移。</span><span class="sxs-lookup"><span data-stu-id="159b5-176">If you have any other database (for example, IBM DB2) and you opt for a lift and shift approach, you might want to continue using those databases as IaaS VMs in Azure, unless you are willing to perform a more complex data migration.</span></span> <span data-ttu-id="159b5-177">更复杂的数据迁移将需要额外的工作，因为你将迁移到新的架构和不同的编程库的不同的数据库类型。</span><span class="sxs-lookup"><span data-stu-id="159b5-177">A more complex data migration will require additional effort because you'd be migrating to a different database type with new schema and different programming libraries.</span></span>

<span data-ttu-id="159b5-178">若要了解如何将数据库迁移通过使用 Azure 数据库迁移服务，请参阅[到云使用 Azure SQL 数据库托管实例和 Azure 数据库迁移服务更快地获取](https://channel9.msdn.com/Events/Build/2017/P4008)。</span><span class="sxs-lookup"><span data-stu-id="159b5-178">To learn how to migrate databases by using Azure Database Migration Service, see [Get to the cloud faster with Azure SQL Database Managed Instance and Azure Database Migration Service](https://channel9.msdn.com/Events/Build/2017/P4008).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="159b5-179">其他资源</span><span class="sxs-lookup"><span data-stu-id="159b5-179">Additional resources</span></span>

- <span data-ttu-id="159b5-180">**选择云 SQL Server 选项： Azure SQL 数据库 (PaaS) 或 Azure VM (IaaS) 上的 SQL Server**</span><span class="sxs-lookup"><span data-stu-id="159b5-180">**Choose a cloud SQL Server option: Azure SQL Database (PaaS) or SQL Server on Azure VM (IaaS)**</span></span>

    [https://docs.microsoft.com/azure/sql-database/sql-database-paas-vs-sql-server-iaas](https://docs.microsoft.com/azure/sql-database/sql-database-paas-vs-sql-server-iaas)

- <span data-ttu-id="159b5-181">**获取与使用 Azure SQL DB 托管实例和数据库迁移服务更快地云**</span><span class="sxs-lookup"><span data-stu-id="159b5-181">**Get to the cloud faster with Azure SQL DB Managed Instance and Database Migration Service**</span></span>

    [https://channel9.msdn.com/Events/Build/2017/P4008](https://channel9.msdn.com/Events/Build/2017/P4008)

- <span data-ttu-id="159b5-182">**SQL Server 数据库迁移到云中的 SQL 数据库**</span><span class="sxs-lookup"><span data-stu-id="159b5-182">**SQL Server database migration to SQL Database in the cloud**</span></span>

    [https://docs.microsoft.com/azure/sql-database/sql-database-cloud-migrate](https://docs.microsoft.com/azure/sql-database/sql-database-cloud-migrate)

- <span data-ttu-id="159b5-183">**Azure SQL 数据库**</span><span class="sxs-lookup"><span data-stu-id="159b5-183">**Azure SQL Database**</span></span>

    [https://azure.microsoft.com/services/sql-database/?v=16.50](https://azure.microsoft.com/services/sql-database/?v=16.50)

- <span data-ttu-id="159b5-184">**在虚拟机上的 SQL Server**</span><span class="sxs-lookup"><span data-stu-id="159b5-184">**SQL Server on virtual machines**</span></span>

    [https://azure.microsoft.com/services/virtual-machines/sql-server/](https://azure.microsoft.com/services/virtual-machines/sql-server/)

>[!div class="step-by-step"]
<span data-ttu-id="159b5-185">[上一页](lift-and-shift-existing-apps-azure-iaas.md)
[下一页](modernize-existing-apps-to-cloud-optimized/index.md)</span><span class="sxs-lookup"><span data-stu-id="159b5-185">[Previous](lift-and-shift-existing-apps-azure-iaas.md)
[Next](modernize-existing-apps-to-cloud-optimized/index.md)</span></span>