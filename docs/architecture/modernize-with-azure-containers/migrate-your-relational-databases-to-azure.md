---
title: 将关系数据库迁移到 azure
description: 通过 Azure 云和 Windows 容器实现现有 .NET 应用程序的现代化 |将关系数据库迁移到 azure
ms.date: 04/28/2018
ms.openlocfilehash: efd1548c3f74fc27450f4949d71a1c4d61907ba5
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73093617"
---
# <a name="migrate-your-relational-databases-to-azure"></a><span data-ttu-id="0d237-103">将关系数据库迁移到 azure</span><span class="sxs-lookup"><span data-stu-id="0d237-103">Migrate your relational databases to azure</span></span>

<span data-ttu-id="0d237-104">视觉： Azure 提供最全面的数据库迁移。</span><span class="sxs-lookup"><span data-stu-id="0d237-104">Vision: Azure offers the most comprehensive database migration.</span></span>

<span data-ttu-id="0d237-105">在 Azure 中，可以直接将数据库服务器迁移到 IaaS Vm （纯粹的直接迁移），也可以迁移到 Azure SQL 数据库，以获得更多好处。</span><span class="sxs-lookup"><span data-stu-id="0d237-105">In Azure, you can migrate your database servers directly to IaaS VMs (pure lift and shift), or you can migrate to Azure SQL Database, for additional benefits.</span></span> <span data-ttu-id="0d237-106">Azure SQL 数据库提供托管实例和完整的数据库即服务（DBaaS）选项。</span><span class="sxs-lookup"><span data-stu-id="0d237-106">Azure SQL Database offers managed instance and full database-as-a-service (DBaaS) options.</span></span> <span data-ttu-id="0d237-107">图3-1 显示了 Azure 中提供的多个关系数据库迁移路径。</span><span class="sxs-lookup"><span data-stu-id="0d237-107">Figure 3-1 shows the multiple relational database migration paths available in Azure.</span></span>

![Azure 中的数据库迁移路径](./media/image3-1.png)

<span data-ttu-id="0d237-109">**图 3-1。**</span><span class="sxs-lookup"><span data-stu-id="0d237-109">**Figure 3-1.**</span></span> <span data-ttu-id="0d237-110">Azure 中的数据库迁移路径</span><span class="sxs-lookup"><span data-stu-id="0d237-110">Database migration paths in Azure</span></span>

## <a name="when-to-migrate-to-azure-sql-database-managed-instance"></a><span data-ttu-id="0d237-111">何时迁移到 Azure SQL 数据库托管实例</span><span class="sxs-lookup"><span data-stu-id="0d237-111">When to migrate to Azure SQL Database Managed Instance</span></span>

<span data-ttu-id="0d237-112">在大多数情况下，在将数据迁移到 Azure 时，Azure SQL 数据库托管实例是要考虑的最佳选择。</span><span class="sxs-lookup"><span data-stu-id="0d237-112">In most cases, Azure SQL Database Managed Instance will be your best option to consider when you migrate your data to Azure.</span></span> <span data-ttu-id="0d237-113">如果要迁移 SQL Server 数据库，并且需要几乎100% 的保证，而无需重塑应用程序或更改数据或数据访问代码，请选择 Azure SQL 数据库的托管实例功能。</span><span class="sxs-lookup"><span data-stu-id="0d237-113">If you are migrating SQL Server databases and need nearly 100% assurance that you won't need to rearchitect your application or make changes to your data or data access code, choose the Managed Instance feature of Azure SQL Database.</span></span>

<span data-ttu-id="0d237-114">如果对 SQL Server 实例级别的功能或除了标准 Azure SQL 数据库（单一数据库模型）中提供的功能之外的隔离要求有其他要求，Azure SQL 数据库托管实例是最佳选项。</span><span class="sxs-lookup"><span data-stu-id="0d237-114">Azure SQL Database Managed Instance is the best option if you have additional requirements for SQL Server instance-level functionality, or isolation requirements beyond the features provided in a standard Azure SQL Database (single database model).</span></span> <span data-ttu-id="0d237-115">这最后一种方法是最适合 PaaS 的选择，但它并不提供与传统 SQL server 相同的功能。</span><span class="sxs-lookup"><span data-stu-id="0d237-115">This last one is the most PaaS-oriented choice, but it doesn't offer the same features as that of a traditional SQL server.</span></span> <span data-ttu-id="0d237-116">迁移可能会摩擦。</span><span class="sxs-lookup"><span data-stu-id="0d237-116">Migration might surface frictions.</span></span>

<span data-ttu-id="0d237-117">例如，在实例级 SQL Server 功能方面进行深层投资的组织将受益于迁移到 SQL 托管实例。</span><span class="sxs-lookup"><span data-stu-id="0d237-117">For example, an organization that has made deep investments in instance-level SQL Server capabilities would benefit from migrating to SQL Managed Instance.</span></span> <span data-ttu-id="0d237-118">实例级 SQL Server 功能的示例包括 SQL 公共语言运行时（CLR）集成、SQL Server 代理和跨数据库查询。</span><span class="sxs-lookup"><span data-stu-id="0d237-118">Examples of instance-level SQL Server capabilities include SQL common language runtime (CLR) integration, SQL Server Agent, and cross-database querying.</span></span> <span data-ttu-id="0d237-119">对这些功能的支持在标准 Azure SQL 数据库（单一数据库模型）中不可用。</span><span class="sxs-lookup"><span data-stu-id="0d237-119">Support for these features is not available in standard Azure SQL Database (a single-database model).</span></span>

<span data-ttu-id="0d237-120">在高度管控行业中运作并且出于安全目的而需要维护隔离的组织，还可以从选择 SQL 托管实例模型中获益。</span><span class="sxs-lookup"><span data-stu-id="0d237-120">An organization that operates in a highly regulated industry, and which needs to maintain isolation for security purposes, also might benefit from choosing the SQL Managed Instance model.</span></span>

<span data-ttu-id="0d237-121">Azure SQL 数据库中的托管实例具有以下特征：</span><span class="sxs-lookup"><span data-stu-id="0d237-121">Managed Instance in Azure SQL Database has the following characteristics:</span></span>

- <span data-ttu-id="0d237-122">通过 Azure 虚拟网络进行安全隔离</span><span class="sxs-lookup"><span data-stu-id="0d237-122">Security isolation through Azure Virtual Network</span></span>

- <span data-ttu-id="0d237-123">应用程序接口兼容性，其中包含以下功能：</span><span class="sxs-lookup"><span data-stu-id="0d237-123">Application surface compatibility, with these features:</span></span>

  - <span data-ttu-id="0d237-124">SQL Server 代理和 SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="0d237-124">SQL Server Agent and SQL Server Profiler</span></span>

  - <span data-ttu-id="0d237-125">跨数据库引用和查询、SQL CLR、复制、变更数据捕获（CDC）和 Service Broker</span><span class="sxs-lookup"><span data-stu-id="0d237-125">Cross-database references and queries, SQL CLR, replication, change data capture (CDC), and Service Broker</span></span>

- <span data-ttu-id="0d237-126">数据库最大大小为 35 TB</span><span class="sxs-lookup"><span data-stu-id="0d237-126">Database sizes up to 35 TB</span></span>

- <span data-ttu-id="0d237-127">最小停机时间迁移，其中包含以下功能：</span><span class="sxs-lookup"><span data-stu-id="0d237-127">Minimum-downtime migration, with these features:</span></span>

  - <span data-ttu-id="0d237-128">Azure 数据库迁移服务</span><span class="sxs-lookup"><span data-stu-id="0d237-128">Azure Database Migration Service</span></span>

  - <span data-ttu-id="0d237-129">本机备份和还原以及日志传送</span><span class="sxs-lookup"><span data-stu-id="0d237-129">Native backup and restore, and log shipping</span></span>

<span data-ttu-id="0d237-130">借助这些功能，在将现有应用程序数据库迁移到 Azure SQL 数据库时，托管实例模型为 SQL Server 的 PaaS 提供将近100% 的好处。</span><span class="sxs-lookup"><span data-stu-id="0d237-130">With these capabilities, when you migrate existing application databases to Azure SQL Database, the Managed Instance model offers nearly 100% of the benefits of PaaS for SQL Server.</span></span> <span data-ttu-id="0d237-131">托管实例是一种 SQL Server 环境，在此环境中，你可以继续使用实例级功能，而无需更改应用程序设计。</span><span class="sxs-lookup"><span data-stu-id="0d237-131">Managed Instance is a SQL Server environment where you continue using instance-level capabilities without changing your application design.</span></span>

<span data-ttu-id="0d237-132">托管实例可能最适合当前正在使用 SQL Server 并且需要在云中的网络安全灵活性的企业。</span><span class="sxs-lookup"><span data-stu-id="0d237-132">Managed Instance is probably the best fit for enterprises that currently are using SQL Server, and which require flexibility in their network security in the cloud.</span></span> <span data-ttu-id="0d237-133">这就像是为 SQL 数据库提供专用虚拟网络。</span><span class="sxs-lookup"><span data-stu-id="0d237-133">It's like having a private virtual network for your SQL databases.</span></span>

## <a name="when-to-migrate-to-azure-sql-database"></a><span data-ttu-id="0d237-134">何时迁移到 Azure SQL Database</span><span class="sxs-lookup"><span data-stu-id="0d237-134">When to migrate to Azure SQL Database</span></span>

<span data-ttu-id="0d237-135">如前所述，标准 Azure SQL 数据库是完全托管的关系 DBaaS。</span><span class="sxs-lookup"><span data-stu-id="0d237-135">As mentioned, the standard Azure SQL Database is a fully managed, relational DBaaS.</span></span> <span data-ttu-id="0d237-136">SQL 数据库当前在世界各地跨38数据中心管理数百万个生产数据库。</span><span class="sxs-lookup"><span data-stu-id="0d237-136">SQL Database currently manages millions of production databases, across 38 datacenters, around the world.</span></span> <span data-ttu-id="0d237-137">它支持范围广泛的应用程序和工作负荷，从管理简单的事务数据到驱动需要全球范围内的高级数据处理的数据密集型、任务关键型应用程序。</span><span class="sxs-lookup"><span data-stu-id="0d237-137">It supports a broad range of applications and workloads, from managing straightforward transactional data, to driving the most data-intensive, mission-critical applications that require advanced data processing at a global scale.</span></span>

<span data-ttu-id="0d237-138">由于使用的是基本、标准 SQL 数据库和无其他实例功能，因此，如果应用程序使用的是基本的标准 SQL 数据库，则应将其设置为 "按默认值"，而不是 "按默认选择"，则应将其设置为 "按默认值"。</span><span class="sxs-lookup"><span data-stu-id="0d237-138">Because of its full PaaS features, better pricing-and ultimately lower cost-you should move to the standard Azure SQL Database as your "by-default choice" if you have an application that uses basic, standard SQL databases, and no additional instance features.</span></span> <span data-ttu-id="0d237-139">标准 Azure SQL 数据库中不支持 SQL CLR 集成、SQL Server 代理和跨数据库查询等 SQL Server 功能。</span><span class="sxs-lookup"><span data-stu-id="0d237-139">SQL Server features like SQL CLR integration, SQL Server Agent, and cross-database querying are not supported in the standard Azure SQL Database.</span></span> <span data-ttu-id="0d237-140">这些功能仅在 Azure SQL 数据库托管实例模型中提供。</span><span class="sxs-lookup"><span data-stu-id="0d237-140">Those features are available only in the Azure SQL Database Managed Instance model.</span></span>

<span data-ttu-id="0d237-141">Azure SQL 数据库是为应用程序开发人员构建的唯一的智能云数据库服务。</span><span class="sxs-lookup"><span data-stu-id="0d237-141">Azure SQL Database is the only intelligent cloud database service that's built for app developers.</span></span> <span data-ttu-id="0d237-142">这也是唯一一种无需停机即可实时缩放的云数据库服务，可帮助你有效地交付多租户应用。</span><span class="sxs-lookup"><span data-stu-id="0d237-142">It's also the only cloud database service that scales on-the-fly, without downtime, to help you efficiently deliver multitenant apps.</span></span> <span data-ttu-id="0d237-143">最终，Azure SQL 数据库可让您更好地创新，并加速您的上市时间。</span><span class="sxs-lookup"><span data-stu-id="0d237-143">Ultimately, Azure SQL Database leaves you more time to innovate, and it accelerates your time to market.</span></span> <span data-ttu-id="0d237-144">您可以使用您喜欢的语言和平台构建安全的应用程序并连接到您的 SQL 数据库。</span><span class="sxs-lookup"><span data-stu-id="0d237-144">You can build secure apps and connect to your SQL database by using the languages and platforms that you prefer.</span></span>

<span data-ttu-id="0d237-145">Azure SQL 数据库具有以下优势：</span><span class="sxs-lookup"><span data-stu-id="0d237-145">Azure SQL Database offers the following benefits:</span></span>

- <span data-ttu-id="0d237-146">可学习和适应应用的内置智能（机器学习）</span><span class="sxs-lookup"><span data-stu-id="0d237-146">Built-in intelligence (machine learning) that learns and adapts to your app</span></span>

- <span data-ttu-id="0d237-147">按需数据库预配</span><span class="sxs-lookup"><span data-stu-id="0d237-147">On-demand database provisioning</span></span>

- <span data-ttu-id="0d237-148">针对所有工作负荷的一系列产品/服务</span><span class="sxs-lookup"><span data-stu-id="0d237-148">A range of offers, for all workloads</span></span>

- <span data-ttu-id="0d237-149">99.99% 的可用性 SLA，零维护</span><span class="sxs-lookup"><span data-stu-id="0d237-149">99.99% availability SLA, zero maintenance</span></span>

- <span data-ttu-id="0d237-150">用于数据保护的异地复制和还原服务</span><span class="sxs-lookup"><span data-stu-id="0d237-150">Geo-replication and restore services for data protection</span></span>

- <span data-ttu-id="0d237-151">Azure SQL 数据库时间点还原功能</span><span class="sxs-lookup"><span data-stu-id="0d237-151">Azure SQL Database Point in Time Restore feature</span></span>

- <span data-ttu-id="0d237-152">与 SQL Server 2016 兼容，包括混合和迁移</span><span class="sxs-lookup"><span data-stu-id="0d237-152">Compatibility with SQL Server 2016, including hybrid and migration</span></span>

<span data-ttu-id="0d237-153">标准 Azure SQL 数据库比 Azure SQL 数据库托管实例更接近于 PaaS。</span><span class="sxs-lookup"><span data-stu-id="0d237-153">The standard Azure SQL Database is closer to PaaS than Azure SQL Database Managed Instance.</span></span> <span data-ttu-id="0d237-154">首选标准 Azure SQL 数据库，因为你将从托管云获得更多好处。</span><span class="sxs-lookup"><span data-stu-id="0d237-154">Prefer the standard Azure SQL Database because you'll get more benefits from a managed cloud.</span></span> <span data-ttu-id="0d237-155">但是，Azure SQL 数据库与常规和本地 SQL Server 实例有一些重要差异。</span><span class="sxs-lookup"><span data-stu-id="0d237-155">However, Azure SQL Database has some key differences from regular and on-premises SQL Server instances.</span></span> <span data-ttu-id="0d237-156">根据你的现有应用程序的数据库要求以及企业需求和策略，在规划迁移到云时，这可能不是最佳选择。</span><span class="sxs-lookup"><span data-stu-id="0d237-156">Depending on your existing application's database requirements, and your enterprise requirements and policies, it might not be the best choice when you are planning your migration to the cloud.</span></span>

## <a name="when-to-move-your-original-rdbms-to-a-vm-iaas"></a><span data-ttu-id="0d237-157">何时将原始 RDBMS 移至 VM （IaaS）</span><span class="sxs-lookup"><span data-stu-id="0d237-157">When to move your original RDBMS to a VM (IaaS)</span></span>

<span data-ttu-id="0d237-158">其中一种迁移选项是将原始关系数据库管理系统（RDBMS）（包括 Oracle、IBM DB2、MySQL、PostgreSQL 或 SQL Server）移到运行在 Azure VM 上的类似服务器。</span><span class="sxs-lookup"><span data-stu-id="0d237-158">One of your migration options is to move your original relational database management system (RDBMS), including Oracle, IBM DB2, MySQL, PostgreSQL, or SQL Server, to a similar server that's running on an Azure VM.</span></span> <span data-ttu-id="0d237-159">如果现有应用程序需要最快的迁移到云，但更改最少，或者根本没有任何更改，则在云中直接迁移到 IaaS 可能是一个合理的选择。</span><span class="sxs-lookup"><span data-stu-id="0d237-159">If you have existing applications that require the fastest migration to the cloud with minimal changes, or no changes at all, a direct migration to IaaS in the cloud might be a fair option.</span></span> <span data-ttu-id="0d237-160">这可能不是充分利用云的所有好处的最佳方法，但它可能是最快的初始路径。</span><span class="sxs-lookup"><span data-stu-id="0d237-160">It might not be the best way to take advantage of all the cloud's benefits, but it's probably the fastest initial path.</span></span>

<span data-ttu-id="0d237-161">目前，Microsoft Azure 最多支持将[331 个不同的数据库服务器](https://azuremarketplace.microsoft.com/marketplace/apps/category/databases?page=1&subcategories=databases-all)部署为 IaaS vm。</span><span class="sxs-lookup"><span data-stu-id="0d237-161">Currently, Microsoft Azure supports up to [331 different database servers](https://azuremarketplace.microsoft.com/marketplace/apps/category/databases?page=1&subcategories=databases-all) deployed as IaaS VMs.</span></span> <span data-ttu-id="0d237-162">其中包括 SQL Server、Oracle、MySQL、PostgreSQL 和 IBM DB2 等常见 RDBMS，以及 MongoDB、Cassandra、DataStax、MariaDB 和 Cloudera 等许多其他 NoSQL 数据库。</span><span class="sxs-lookup"><span data-stu-id="0d237-162">These include popular RDBMS like SQL Server, Oracle, MySQL, PostgreSQL, and IBM DB2, and many other NoSQL databases like MongoDB, Cassandra, DataStax, MariaDB, and Cloudera.</span></span>

> [!NOTE]
> <span data-ttu-id="0d237-163">尽管将 RDBMS 迁移到 Azure VM 可能是将数据迁移到云的最快方法（因为它是 IaaS），但这种方法需要在 IT 团队（数据库管理员和 IT 专业人员）中投入大量投资。</span><span class="sxs-lookup"><span data-stu-id="0d237-163">Although moving your RDBMS to an Azure VM might be the fastest way to migrate your data to the cloud (because it is IaaS), this approach requires a significant investment in your IT teams (database administrators and IT pros).</span></span> <span data-ttu-id="0d237-164">企业团队需要能够为 SQL Server 设置和管理高可用性、灾难恢复和修补。</span><span class="sxs-lookup"><span data-stu-id="0d237-164">Enterprise teams need to be able to set up and manage high availability, disaster recovery, and patching for SQL Server.</span></span> <span data-ttu-id="0d237-165">此上下文还需要具有完全管理权限的自定义环境。</span><span class="sxs-lookup"><span data-stu-id="0d237-165">This context also needs a customized environment, with full administrative rights.</span></span>

## <a name="when-to-migrate-to-sql-server-as-a-vm-iaas"></a><span data-ttu-id="0d237-166">何时迁移到 SQL Server 虚拟机（IaaS）</span><span class="sxs-lookup"><span data-stu-id="0d237-166">When to migrate to SQL Server as a VM (IaaS)</span></span>

<span data-ttu-id="0d237-167">在某些情况下，你可能仍需要迁移到作为常规 VM SQL Server。</span><span class="sxs-lookup"><span data-stu-id="0d237-167">There might be a few cases where you still need to migrate to SQL Server as a regular VM.</span></span> <span data-ttu-id="0d237-168">例如，如果需要使用 SQL Server Reporting Services，则会出现这种情况。</span><span class="sxs-lookup"><span data-stu-id="0d237-168">An example scenario is if you need to use SQL Server Reporting Services.</span></span> <span data-ttu-id="0d237-169">但在大多数情况下，Azure SQL 数据库托管实例可以提供从本地 SQL server 迁移所需的所有内容，因此，要尝试迁移到 SQL Server VM。</span><span class="sxs-lookup"><span data-stu-id="0d237-169">In most cases, though, Azure SQL Database Managed Instance can provide everything you need to migrate from on-premises SQL servers, so migration to a SQL Server VM should be your last resort to try.</span></span>

## <a name="use-azure-database-migration-service-to-migrate-your-relational-databases-to-azure"></a><span data-ttu-id="0d237-170">使用 Azure 数据库迁移服务将关系数据库迁移到 Azure</span><span class="sxs-lookup"><span data-stu-id="0d237-170">Use Azure Database Migration Service to migrate your relational databases to Azure</span></span>

<span data-ttu-id="0d237-171">你可以使用 Azure 数据库迁移服务将 SQL Server、Oracle 和 MySQL 等关系数据库迁移到 Azure，无论目标数据库是 Azure SQL 数据库、Azure SQL 数据库托管实例还是 Azure VM 上的 SQL Server。</span><span class="sxs-lookup"><span data-stu-id="0d237-171">You can use Azure Database Migration Service to migrate relational databases like SQL Server, Oracle, and MySQL to Azure, whether your target database is Azure SQL Database, Azure SQL Database Managed Instance, or SQL Server on an Azure VM.</span></span>

<span data-ttu-id="0d237-172">带有评估报告功能的自动工作流将指导您完成在迁移数据库之前需要进行的更改。</span><span class="sxs-lookup"><span data-stu-id="0d237-172">The automated workflow, with assessment reporting, guides you through the changes you need to make before you migrate the database.</span></span> <span data-ttu-id="0d237-173">准备就绪后，服务会将源数据库迁移到 Azure。</span><span class="sxs-lookup"><span data-stu-id="0d237-173">When you are ready, the service migrates the source database to Azure.</span></span>

<span data-ttu-id="0d237-174">只要更改原始 RDBMS，就可能需要重新测试。</span><span class="sxs-lookup"><span data-stu-id="0d237-174">Whenever you change an original RDBMS, you might need to retest.</span></span> <span data-ttu-id="0d237-175">你还可能需要更改应用程序中的 SQL 语句或对象关系映射（ORM）代码，具体取决于测试结果。</span><span class="sxs-lookup"><span data-stu-id="0d237-175">You also might need to change the SQL sentences or Object-Relational Mapping (ORM) code in your application, depending on testing results.</span></span>

<span data-ttu-id="0d237-176">如果你有任何其他数据库（例如，IBM DB2），并且选择了提升和转移方法，则可能需要继续将这些数据库用作 Azure 中的 IaaS Vm，除非你愿意执行更复杂的数据迁移。</span><span class="sxs-lookup"><span data-stu-id="0d237-176">If you have any other database (for example, IBM DB2) and you opt for a lift and shift approach, you might want to continue using those databases as IaaS VMs in Azure, unless you are willing to perform a more complex data migration.</span></span> <span data-ttu-id="0d237-177">更复杂的数据迁移需要额外的精力，因为你将使用新的架构和不同的编程库迁移到不同的数据库类型。</span><span class="sxs-lookup"><span data-stu-id="0d237-177">A more complex data migration will require additional effort because you'd be migrating to a different database type with new schema and different programming libraries.</span></span>

<span data-ttu-id="0d237-178">若要了解如何使用 Azure 数据库迁移服务迁移数据库，请参阅[使用 Azure SQL 数据库托管实例和 Azure 数据库迁移服务更快地进入云](https://channel9.msdn.com/Events/Build/2017/P4008)。</span><span class="sxs-lookup"><span data-stu-id="0d237-178">To learn how to migrate databases by using Azure Database Migration Service, see [Get to the cloud faster with Azure SQL Database Managed Instance and Azure Database Migration Service](https://channel9.msdn.com/Events/Build/2017/P4008).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="0d237-179">其他资源</span><span class="sxs-lookup"><span data-stu-id="0d237-179">Additional resources</span></span>

- <span data-ttu-id="0d237-180">**选择云 SQL Server 选项： azure SQL 数据库（PaaS）或 Azure VM 上的 SQL Server （IaaS）**</span><span class="sxs-lookup"><span data-stu-id="0d237-180">**Choose a cloud SQL Server option: Azure SQL Database (PaaS) or SQL Server on Azure VM (IaaS)**</span></span>

    <https://docs.microsoft.com/azure/sql-database/sql-database-paas-vs-sql-server-iaas>

- <span data-ttu-id="0d237-181">**通过 Azure SQL DB 托管实例和数据库迁移服务更快地进入云**</span><span class="sxs-lookup"><span data-stu-id="0d237-181">**Get to the cloud faster with Azure SQL DB Managed Instance and Database Migration Service**</span></span>

    <https://channel9.msdn.com/Events/Build/2017/P4008>

- <span data-ttu-id="0d237-182">**将 SQL Server 数据库迁移到云中的 SQL 数据库**</span><span class="sxs-lookup"><span data-stu-id="0d237-182">**SQL Server database migration to SQL Database in the cloud**</span></span>

    <https://docs.microsoft.com/azure/sql-database/sql-database-cloud-migrate>

- <span data-ttu-id="0d237-183">**Azure SQL 数据库**</span><span class="sxs-lookup"><span data-stu-id="0d237-183">**Azure SQL Database**</span></span>

    <https://azure.microsoft.com/services/sql-database/?v=16.50>

- <span data-ttu-id="0d237-184">**虚拟机上的 SQL Server**</span><span class="sxs-lookup"><span data-stu-id="0d237-184">**SQL Server on virtual machines**</span></span>

    <https://azure.microsoft.com/services/virtual-machines/sql-server/>

> [!div class="step-by-step"]
> <span data-ttu-id="0d237-185">[上一页](lift-and-shift-existing-apps-azure-iaas.md)
> [下一页](modernize-existing-apps-to-cloud-optimized/index.md)</span><span class="sxs-lookup"><span data-stu-id="0d237-185">[Previous](lift-and-shift-existing-apps-azure-iaas.md)
[Next](modernize-existing-apps-to-cloud-optimized/index.md)</span></span> <!-- Next Chapter -->
