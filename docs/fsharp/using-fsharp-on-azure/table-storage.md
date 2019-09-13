---
title: 通过 F# 实现 Azure 表格存储入门
description: 使用 Azure 表存储或 Azure Cosmos DB 在云中存储结构化数据。
author: sylvanc
ms.date: 03/26/2018
ms.openlocfilehash: f5fe2fe667b6d529bba4d29729a975c7890b5aba
ms.sourcegitcommit: 33c8d6f7342a4bb2c577842b7f075b0e20a2fa40
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/12/2019
ms.locfileid: "70928994"
---
# <a name="get-started-with-azure-table-storage-and-the-azure-cosmos-db-table-api-using-f"></a><span data-ttu-id="2accc-103">开始使用 Azure 表存储和 Azure Cosmos DB 表 API 使用 F\#</span><span class="sxs-lookup"><span data-stu-id="2accc-103">Get started with Azure Table storage and the Azure Cosmos DB Table API using F\#</span></span>

<span data-ttu-id="2accc-104">Azure 表存储是一项用于在云中存储结构化 NoSQL 数据的服务。</span><span class="sxs-lookup"><span data-stu-id="2accc-104">Azure Table storage is a service that stores structured NoSQL data in the cloud.</span></span> <span data-ttu-id="2accc-105">表存储是具有无架构设计的键/属性存储。</span><span class="sxs-lookup"><span data-stu-id="2accc-105">Table storage is a key/attribute store with a schemaless design.</span></span> <span data-ttu-id="2accc-106">因为表存储是无架构的，所以在应用程序的需求不断变化时，可以轻松地调整数据。</span><span class="sxs-lookup"><span data-stu-id="2accc-106">Because Table storage is schemaless, it's easy to adapt your data as the needs of your application evolve.</span></span> <span data-ttu-id="2accc-107">对于所有类型的应用程序，访问数据的速度都迅速且经济高效。</span><span class="sxs-lookup"><span data-stu-id="2accc-107">Access to data is fast and cost-effective for all kinds of applications.</span></span> <span data-ttu-id="2accc-108">对于相似的数据量，表存储的成本通常显著低于传统的 SQL。</span><span class="sxs-lookup"><span data-stu-id="2accc-108">Table storage is typically significantly lower in cost than traditional SQL for similar volumes of data.</span></span>

<span data-ttu-id="2accc-109">可以使用表存储来存储灵活的数据集，例如 web 应用程序的用户数据、通讯簿、设备信息，以及服务需要的任何其他类型的元数据。</span><span class="sxs-lookup"><span data-stu-id="2accc-109">You can use Table storage to store flexible datasets, such as user data for web applications, address books, device information, and any other type of metadata that your service requires.</span></span> <span data-ttu-id="2accc-110">您可以在表中存储任意数量的实体，并且一个存储帐户可以包含任意数目的表，直至达到存储帐户的容量限制。</span><span class="sxs-lookup"><span data-stu-id="2accc-110">You can store any number of entities in a table, and a storage account may contain any number of tables, up to the capacity limit of the storage account.</span></span>

<span data-ttu-id="2accc-111">Azure Cosmos DB 提供了为 Azure 表存储编写的应用程序的表 API，以及需要高级功能的应用程序，例如：</span><span class="sxs-lookup"><span data-stu-id="2accc-111">Azure Cosmos DB provides the Table API for applications that are written for Azure Table storage and that require premium capabilities such as:</span></span>

- <span data-ttu-id="2accc-112">全包式全局分布。</span><span class="sxs-lookup"><span data-stu-id="2accc-112">Turnkey global distribution.</span></span>
- <span data-ttu-id="2accc-113">全球专用吞吐量。</span><span class="sxs-lookup"><span data-stu-id="2accc-113">Dedicated throughput worldwide.</span></span>
- <span data-ttu-id="2accc-114">99% 百分点处的一位数毫秒延迟。</span><span class="sxs-lookup"><span data-stu-id="2accc-114">Single-digit millisecond latencies at the 99th percentile.</span></span>
- <span data-ttu-id="2accc-115">保证高可用性。</span><span class="sxs-lookup"><span data-stu-id="2accc-115">Guaranteed high availability.</span></span>
- <span data-ttu-id="2accc-116">自动辅助索引。</span><span class="sxs-lookup"><span data-stu-id="2accc-116">Automatic secondary indexing.</span></span>

<span data-ttu-id="2accc-117">为 Azure 表存储编写的应用程序可以通过使用表 API 迁移到 Azure Cosmos DB，无需更改代码并利用高级功能。</span><span class="sxs-lookup"><span data-stu-id="2accc-117">Applications written for Azure Table storage can migrate to Azure Cosmos DB by using the Table API with no code changes and take advantage of premium capabilities.</span></span> <span data-ttu-id="2accc-118">表 API 提供适用于 .NET、Java、Python 和 node.js 的客户端 Sdk。</span><span class="sxs-lookup"><span data-stu-id="2accc-118">The Table API has client SDKs available for .NET, Java, Python, and Node.js.</span></span>

<span data-ttu-id="2accc-119">有关详细信息，请参阅[Azure Cosmos DB 表 API 简介](https://docs.microsoft.com/azure/cosmos-db/table-introduction)。</span><span class="sxs-lookup"><span data-stu-id="2accc-119">For more information, see [Introduction to Azure Cosmos DB Table API](https://docs.microsoft.com/azure/cosmos-db/table-introduction).</span></span>

## <a name="about-this-tutorial"></a><span data-ttu-id="2accc-120">关于本教程</span><span class="sxs-lookup"><span data-stu-id="2accc-120">About this tutorial</span></span>

<span data-ttu-id="2accc-121">本教程说明如何编写F#代码来使用 Azure 表存储或 Azure Cosmos DB 表 API 执行一些常见任务，包括创建和删除表以及插入、更新、删除和查询表数据。</span><span class="sxs-lookup"><span data-stu-id="2accc-121">This tutorial shows how to write F# code to do some common tasks using Azure Table storage or the Azure Cosmos DB Table API, including creating and deleting a table and inserting, updating, deleting, and querying table data.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="2accc-122">系统必备</span><span class="sxs-lookup"><span data-stu-id="2accc-122">Prerequisites</span></span>

<span data-ttu-id="2accc-123">若要使用本指南，必须先[创建 Azure 存储帐户](/azure/storage/storage-create-storage-account)或[Azure Cosmos DB 帐户](https://azure.microsoft.com/try/cosmosdb/)。</span><span class="sxs-lookup"><span data-stu-id="2accc-123">To use this guide, you must first [create an Azure storage account](/azure/storage/storage-create-storage-account) or [Azure Cosmos DB account](https://azure.microsoft.com/try/cosmosdb/).</span></span>

## <a name="create-an-f-script-and-start-f-interactive"></a><span data-ttu-id="2accc-124">创建F#脚本并开始F#交互式</span><span class="sxs-lookup"><span data-stu-id="2accc-124">Create an F# Script and Start F# Interactive</span></span>

<span data-ttu-id="2accc-125">本文中的示例可用于F#应用程序或F#脚本。</span><span class="sxs-lookup"><span data-stu-id="2accc-125">The samples in this article can be used in either an F# application or an F# script.</span></span> <span data-ttu-id="2accc-126">若要创建F#脚本，请在`.fsx` F#开发环境中创建`tables.fsx`扩展名为的文件。</span><span class="sxs-lookup"><span data-stu-id="2accc-126">To create an F# script, create a file with the `.fsx` extension, for example `tables.fsx`, in your F# development environment.</span></span>

<span data-ttu-id="2accc-127">接下来，使用[包管理器](package-management.md)（如`#r` [Paket](https://fsprojects.github.io/Paket/)或`WindowsAzure.Storage` [NuGet](https://www.nuget.org/) ）通过指令在脚本`WindowsAzure.Storage.dll`中安装包和引用。</span><span class="sxs-lookup"><span data-stu-id="2accc-127">Next, use a [package manager](package-management.md) such as [Paket](https://fsprojects.github.io/Paket/) or [NuGet](https://www.nuget.org/) to install the `WindowsAzure.Storage` package and reference `WindowsAzure.Storage.dll` in your script using a `#r` directive.</span></span> <span data-ttu-id="2accc-128">为`Microsoft.WindowsAzure.ConfigurationManager`获取 Microsoft Azure 命名空间，请再次执行此操作。</span><span class="sxs-lookup"><span data-stu-id="2accc-128">Do it again for `Microsoft.WindowsAzure.ConfigurationManager` in order to get the Microsoft.Azure namespace.</span></span>

### <a name="add-namespace-declarations"></a><span data-ttu-id="2accc-129">添加命名空间声明</span><span class="sxs-lookup"><span data-stu-id="2accc-129">Add namespace declarations</span></span>

<span data-ttu-id="2accc-130">将以下`open`语句添加到`tables.fsx`文件顶部：</span><span class="sxs-lookup"><span data-stu-id="2accc-130">Add the following `open` statements to the top of the `tables.fsx` file:</span></span>

[!code-fsharp[TableStorage](~/samples/snippets/fsharp/azure/table-storage.fsx#L1-L5)]

### <a name="get-your-azure-storage-connection-string"></a><span data-ttu-id="2accc-131">获取 Azure 存储连接字符串</span><span class="sxs-lookup"><span data-stu-id="2accc-131">Get your Azure Storage connection string</span></span>

<span data-ttu-id="2accc-132">如果要连接到 Azure 存储表服务，则需要为本教程提供连接字符串。</span><span class="sxs-lookup"><span data-stu-id="2accc-132">If you're connecting to Azure Storage Table service, you'll need your connection string for this tutorial.</span></span> <span data-ttu-id="2accc-133">可以从 Azure 门户复制连接字符串。</span><span class="sxs-lookup"><span data-stu-id="2accc-133">You can copy your connection string from the Azure portal.</span></span> <span data-ttu-id="2accc-134">有关连接字符串的详细信息，请参阅[配置存储连接字符串](/azure/storage/storage-configure-connection-string)。</span><span class="sxs-lookup"><span data-stu-id="2accc-134">For more information about connection strings, see [Configure Storage Connection Strings](/azure/storage/storage-configure-connection-string).</span></span>

### <a name="get-your-azure-cosmos-db-connection-string"></a><span data-ttu-id="2accc-135">获取 Azure Cosmos DB 连接字符串</span><span class="sxs-lookup"><span data-stu-id="2accc-135">Get your Azure Cosmos DB connection string</span></span>

<span data-ttu-id="2accc-136">如果要连接到 Azure Cosmos DB，则需要此教程的连接字符串。</span><span class="sxs-lookup"><span data-stu-id="2accc-136">If you're connecting to Azure Cosmos DB, you'll need your connection string for this tutorial.</span></span> <span data-ttu-id="2accc-137">可以从 Azure 门户复制连接字符串。</span><span class="sxs-lookup"><span data-stu-id="2accc-137">You can copy your connection string from the Azure portal.</span></span> <span data-ttu-id="2accc-138">在 Azure 门户的 Cosmos DB 帐户中，选择 "**设置** > " "**连接字符串**"，然后单击 "**复制**" 按钮复制主连接字符串。</span><span class="sxs-lookup"><span data-stu-id="2accc-138">In the Azure portal, in your Cosmos DB account, go to **Settings** > **Connection String**, and click the **Copy** button to copy your Primary Connection String.</span></span> 

<span data-ttu-id="2accc-139">对于本教程，请在脚本中输入连接字符串，如下面的示例所示：</span><span class="sxs-lookup"><span data-stu-id="2accc-139">For the tutorial, enter your connection string in your script, like the following example:</span></span>

[!code-fsharp[TableStorage](~/samples/snippets/fsharp/azure/table-storage.fsx#L11-L11)]

<span data-ttu-id="2accc-140">但对于实际项目，**不建议这样做**。</span><span class="sxs-lookup"><span data-stu-id="2accc-140">However, this is **not recommended** for real projects.</span></span> <span data-ttu-id="2accc-141">存储帐户密钥类似于存储帐户的根密码。</span><span class="sxs-lookup"><span data-stu-id="2accc-141">Your storage account key is similar to the root password for your storage account.</span></span> <span data-ttu-id="2accc-142">务必小心保护存储帐户密钥。</span><span class="sxs-lookup"><span data-stu-id="2accc-142">Always be careful to protect your storage account key.</span></span> <span data-ttu-id="2accc-143">避免将其分发给其他用户、对其进行硬编码或将其保存在其他人可以访问的纯文本文件中。</span><span class="sxs-lookup"><span data-stu-id="2accc-143">Avoid distributing it to other users, hard-coding it, or saving it in a plain-text file that is accessible to others.</span></span> <span data-ttu-id="2accc-144">如果你认为密钥可能已泄漏，你可以使用 Azure 门户重新生成密钥。</span><span class="sxs-lookup"><span data-stu-id="2accc-144">You can regenerate your key using the Azure Portal if you believe it may have been compromised.</span></span>

<span data-ttu-id="2accc-145">对于实际应用程序，维护存储连接字符串的最佳方式是在配置文件中。</span><span class="sxs-lookup"><span data-stu-id="2accc-145">For real applications, the best way to maintain your storage connection string is in a configuration file.</span></span> <span data-ttu-id="2accc-146">若要从配置文件中提取连接字符串，可以执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="2accc-146">To fetch the connection string from a configuration file, you can do this:</span></span>

[!code-fsharp[TableStorage](~/samples/snippets/fsharp/azure/table-storage.fsx#L13-L15)]

<span data-ttu-id="2accc-147">使用 Azure Configuration Manager 是可选的。</span><span class="sxs-lookup"><span data-stu-id="2accc-147">Using Azure Configuration Manager is optional.</span></span> <span data-ttu-id="2accc-148">你还可以使用 API，例如 .NET Framework 的`ConfigurationManager`类型。</span><span class="sxs-lookup"><span data-stu-id="2accc-148">You can also use an API such as the .NET Framework's `ConfigurationManager` type.</span></span>

### <a name="parse-the-connection-string"></a><span data-ttu-id="2accc-149">分析连接字符串</span><span class="sxs-lookup"><span data-stu-id="2accc-149">Parse the connection string</span></span>

<span data-ttu-id="2accc-150">若要分析连接字符串，请使用：</span><span class="sxs-lookup"><span data-stu-id="2accc-150">To parse the connection string, use:</span></span>

[!code-fsharp[TableStorage](~/samples/snippets/fsharp/azure/table-storage.fsx#L21-L22)]

<span data-ttu-id="2accc-151">这会返回`CloudStorageAccount`一个。</span><span class="sxs-lookup"><span data-stu-id="2accc-151">This returns a `CloudStorageAccount`.</span></span>

### <a name="create-the-table-service-client"></a><span data-ttu-id="2accc-152">创建表服务客户端</span><span class="sxs-lookup"><span data-stu-id="2accc-152">Create the Table service client</span></span>

<span data-ttu-id="2accc-153">利用`CloudTableClient`类，您可以检索表存储中的表和实体。</span><span class="sxs-lookup"><span data-stu-id="2accc-153">The `CloudTableClient` class enables you to retrieve tables and entities in Table storage.</span></span> <span data-ttu-id="2accc-154">下面是创建服务客户端的一种方法：</span><span class="sxs-lookup"><span data-stu-id="2accc-154">Here's one way to create the service client:</span></span>

[!code-fsharp[TableStorage](~/samples/snippets/fsharp/azure/table-storage.fsx#L28-L29)]

<span data-ttu-id="2accc-155">现在，你已准备好编写从表存储读取数据并将数据写入表存储的代码。</span><span class="sxs-lookup"><span data-stu-id="2accc-155">Now you are ready to write code that reads data from and writes data to Table storage.</span></span>

### <a name="create-a-table"></a><span data-ttu-id="2accc-156">创建表</span><span class="sxs-lookup"><span data-stu-id="2accc-156">Create a table</span></span>

<span data-ttu-id="2accc-157">此示例演示如何创建表（如果该表尚不存在）：</span><span class="sxs-lookup"><span data-stu-id="2accc-157">This example shows how to create a table if it does not already exist:</span></span>

[!code-fsharp[TableStorage](~/samples/snippets/fsharp/azure/table-storage.fsx#L35-L39)]

### <a name="add-an-entity-to-a-table"></a><span data-ttu-id="2accc-158">向表中添加实体</span><span class="sxs-lookup"><span data-stu-id="2accc-158">Add an entity to a table</span></span>

<span data-ttu-id="2accc-159">实体必须具有从`TableEntity`继承的类型。</span><span class="sxs-lookup"><span data-stu-id="2accc-159">An entity has to have a type that inherits from `TableEntity`.</span></span> <span data-ttu-id="2accc-160">您可以采用`TableEntity`任何喜欢的方式进行扩展，但您的类型*必须*具有无参数的构造函数。</span><span class="sxs-lookup"><span data-stu-id="2accc-160">You can extend `TableEntity` in any way you like, but your type *must* have a parameter-less constructor.</span></span> <span data-ttu-id="2accc-161">只有具有`get`和`set`的属性存储在 Azure 表中。</span><span class="sxs-lookup"><span data-stu-id="2accc-161">Only properties that have both `get` and `set` are stored in your Azure Table.</span></span>

<span data-ttu-id="2accc-162">实体的分区和行键唯一标识表中的实体。</span><span class="sxs-lookup"><span data-stu-id="2accc-162">An entity's partition and row key uniquely identify the entity in the table.</span></span> <span data-ttu-id="2accc-163">查询分区键相同的实体的速度快于查询分区键不同的实体的速度，但使用不同的分区键可实现更高的并行操作可伸缩性。</span><span class="sxs-lookup"><span data-stu-id="2accc-163">Entities with the same partition key can be queried faster than those with different partition keys, but using diverse partition keys allows for greater scalability of parallel operations.</span></span>

<span data-ttu-id="2accc-164">下面的示例`Customer` `lastName`使用作为分区键，并`firstName`使用作为行键。</span><span class="sxs-lookup"><span data-stu-id="2accc-164">Here's an example of a `Customer` that uses the `lastName` as the partition key and the `firstName` as the row key.</span></span>

[!code-fsharp[TableStorage](~/samples/snippets/fsharp/azure/table-storage.fsx#L45-L52)]

<span data-ttu-id="2accc-165">现在将`Customer`添加到表中。</span><span class="sxs-lookup"><span data-stu-id="2accc-165">Now add `Customer` to the table.</span></span> <span data-ttu-id="2accc-166">为此，请创建一个`TableOperation`对表执行的。</span><span class="sxs-lookup"><span data-stu-id="2accc-166">To do so, create a `TableOperation` that executes on the table.</span></span> <span data-ttu-id="2accc-167">在这种情况下，你`Insert`将创建一个操作。</span><span class="sxs-lookup"><span data-stu-id="2accc-167">In this case, you create an `Insert` operation.</span></span>

[!code-fsharp[TableStorage](~/samples/snippets/fsharp/azure/table-storage.fsx#L54-L55)]

### <a name="insert-a-batch-of-entities"></a><span data-ttu-id="2accc-168">插入一批实体</span><span class="sxs-lookup"><span data-stu-id="2accc-168">Insert a batch of entities</span></span>

<span data-ttu-id="2accc-169">您可以使用单个写入操作将一批实体插入到表中。</span><span class="sxs-lookup"><span data-stu-id="2accc-169">You can insert a batch of entities into a table using a single write operation.</span></span> <span data-ttu-id="2accc-170">批处理操作允许将操作组合成单个执行，但有一些限制：</span><span class="sxs-lookup"><span data-stu-id="2accc-170">Batch operations allow you to combine operations into a single execution, but they have some restrictions:</span></span>

- <span data-ttu-id="2accc-171">可以在同一批处理操作中执行更新、删除和插入操作。</span><span class="sxs-lookup"><span data-stu-id="2accc-171">You can perform updates, deletes, and inserts in the same batch operation.</span></span>
- <span data-ttu-id="2accc-172">一个批处理操作最多可包含100个实体。</span><span class="sxs-lookup"><span data-stu-id="2accc-172">A batch operation can include up to 100 entities.</span></span>
- <span data-ttu-id="2accc-173">批处理操作中的所有实体都必须具有相同的分区键。</span><span class="sxs-lookup"><span data-stu-id="2accc-173">All entities in a batch operation must have the same partition key.</span></span>
- <span data-ttu-id="2accc-174">尽管可以在批处理操作中执行查询，但它必须是批处理中的唯一操作。</span><span class="sxs-lookup"><span data-stu-id="2accc-174">While it is possible to perform a query in a batch operation, it must be the only operation in the batch.</span></span>

<span data-ttu-id="2accc-175">下面是将两个插入合并为一个批处理操作的一些代码：</span><span class="sxs-lookup"><span data-stu-id="2accc-175">Here's some code that combines two inserts into a batch operation:</span></span>

[!code-fsharp[TableStorage](~/samples/snippets/fsharp/azure/table-storage.fsx#L62-L71)]

### <a name="retrieve-all-entities-in-a-partition"></a><span data-ttu-id="2accc-176">检索分区中的所有实体</span><span class="sxs-lookup"><span data-stu-id="2accc-176">Retrieve all entities in a partition</span></span>

<span data-ttu-id="2accc-177">若要查询表以获取分区中的所有实体，请`TableQuery`使用对象。</span><span class="sxs-lookup"><span data-stu-id="2accc-177">To query a table for all entities in a partition, use a `TableQuery` object.</span></span> <span data-ttu-id="2accc-178">在这里，您将筛选 "Smith" 为分区键的实体。</span><span class="sxs-lookup"><span data-stu-id="2accc-178">Here, you filter for entities where "Smith" is the partition key.</span></span>

[!code-fsharp[TableStorage](~/samples/snippets/fsharp/azure/table-storage.fsx#L77-L82)]

<span data-ttu-id="2accc-179">现在可以打印结果：</span><span class="sxs-lookup"><span data-stu-id="2accc-179">You now print the results:</span></span>

[!code-fsharp[TableStorage](~/samples/snippets/fsharp/azure/table-storage.fsx#L84-L85)]

### <a name="retrieve-a-range-of-entities-in-a-partition"></a><span data-ttu-id="2accc-180">检索分区中的一系列实体</span><span class="sxs-lookup"><span data-stu-id="2accc-180">Retrieve a range of entities in a partition</span></span>

<span data-ttu-id="2accc-181">如果不想查询分区中的所有实体，则可以通过将分区键筛选器与行键筛选器结合来指定一个范围。</span><span class="sxs-lookup"><span data-stu-id="2accc-181">If you don't want to query all the entities in a partition, you can specify a range by combining the partition key filter with a row key filter.</span></span> <span data-ttu-id="2accc-182">在这里，您将使用两个筛选器来获取 "Smith" 分区中的所有实体，其中，行键（名字）以字母表中字母 "M" 前面的字母开头。</span><span class="sxs-lookup"><span data-stu-id="2accc-182">Here, you use two filters to get all entities in the "Smith" partition where the row key (first name) starts with a letter earlier than "M" in the alphabet.</span></span>

[!code-fsharp[TableStorage](~/samples/snippets/fsharp/azure/table-storage.fsx#L91-L100)]

<span data-ttu-id="2accc-183">现在可以打印结果：</span><span class="sxs-lookup"><span data-stu-id="2accc-183">You now print the results:</span></span>

[!code-fsharp[TableStorage](~/samples/snippets/fsharp/azure/table-storage.fsx#L102-L103)]

### <a name="retrieve-a-single-entity"></a><span data-ttu-id="2accc-184">检索单个实体</span><span class="sxs-lookup"><span data-stu-id="2accc-184">Retrieve a single entity</span></span>

<span data-ttu-id="2accc-185">您可以编写查询以检索单个特定实体。</span><span class="sxs-lookup"><span data-stu-id="2accc-185">You can write a query to retrieve a single, specific entity.</span></span> <span data-ttu-id="2accc-186">在这里，您将`TableOperation`使用来指定客户 "Ben Smith"。</span><span class="sxs-lookup"><span data-stu-id="2accc-186">Here, you use a `TableOperation` to specify the customer "Ben Smith".</span></span> <span data-ttu-id="2accc-187">返回，而不是集合`Customer`。</span><span class="sxs-lookup"><span data-stu-id="2accc-187">Instead of a collection, you get back a `Customer`.</span></span> <span data-ttu-id="2accc-188">在查询中同时指定分区键和行键是从表服务中检索单个实体的最快方法。</span><span class="sxs-lookup"><span data-stu-id="2accc-188">Specifying both the partition key and the row key in a query is the fastest way to retrieve a single entity from the Table service.</span></span>

[!code-fsharp[TableStorage](~/samples/snippets/fsharp/azure/table-storage.fsx#L109-L111)]

<span data-ttu-id="2accc-189">现在可以打印结果：</span><span class="sxs-lookup"><span data-stu-id="2accc-189">You now print the results:</span></span>

[!code-fsharp[TableStorage](~/samples/snippets/fsharp/azure/table-storage.fsx#L113-L115)]

### <a name="replace-an-entity"></a><span data-ttu-id="2accc-190">替换实体</span><span class="sxs-lookup"><span data-stu-id="2accc-190">Replace an entity</span></span>

<span data-ttu-id="2accc-191">若要更新实体，请从表服务中检索它，修改实体对象，然后使用`Replace`操作将更改保存回表服务。</span><span class="sxs-lookup"><span data-stu-id="2accc-191">To update an entity, retrieve it from the Table service, modify the entity object, and then save the changes back to the Table service using a `Replace` operation.</span></span> <span data-ttu-id="2accc-192">这会导致在服务器上完全替换该实体，除非服务器上的该实体自检索后已更改，在这种情况下，该操作将失败。</span><span class="sxs-lookup"><span data-stu-id="2accc-192">This causes the entity to be fully replaced on the server, unless the entity on the server has changed since it was retrieved, in which case the operation fails.</span></span> <span data-ttu-id="2accc-193">此失败是为了防止应用程序无意中覆盖其他源的更改。</span><span class="sxs-lookup"><span data-stu-id="2accc-193">This failure is to prevent your application from inadvertently overwriting changes from other sources.</span></span>

[!code-fsharp[TableStorage](~/samples/snippets/fsharp/azure/table-storage.fsx#L121-L128)]

### <a name="insert-or-replace-an-entity"></a><span data-ttu-id="2accc-194">插入或替换实体</span><span class="sxs-lookup"><span data-stu-id="2accc-194">Insert-or-replace an entity</span></span>

<span data-ttu-id="2accc-195">有时，您不知道实体是否存在于表中。</span><span class="sxs-lookup"><span data-stu-id="2accc-195">Sometimes, you don't know whether an entity exists in the table.</span></span> <span data-ttu-id="2accc-196">如果是这样，则不再需要存储在其中的当前值。</span><span class="sxs-lookup"><span data-stu-id="2accc-196">And if it does, the current values stored in it are no longer needed.</span></span> <span data-ttu-id="2accc-197">如果实体存在`InsertOrReplace` ，则可以使用创建实体，而不考虑其状态。</span><span class="sxs-lookup"><span data-stu-id="2accc-197">You can use `InsertOrReplace` to create the entity, or replace it if it exists, regardless of its state.</span></span>

[!code-fsharp[TableStorage](~/samples/snippets/fsharp/azure/table-storage.fsx#L134-L141)]

### <a name="query-a-subset-of-entity-properties"></a><span data-ttu-id="2accc-198">查询实体属性的子集</span><span class="sxs-lookup"><span data-stu-id="2accc-198">Query a subset of entity properties</span></span>

<span data-ttu-id="2accc-199">表查询可以只检索实体中的几个属性，而不是所有这些属性。</span><span class="sxs-lookup"><span data-stu-id="2accc-199">A table query can retrieve just a few properties from an entity instead of all of them.</span></span> <span data-ttu-id="2accc-200">此方法称为 "投影"，可提高查询性能，尤其适用于大型实体。</span><span class="sxs-lookup"><span data-stu-id="2accc-200">This technique, called projection, can improve query performance, especially for large entities.</span></span> <span data-ttu-id="2accc-201">此处，使用`DynamicTableEntity`和`EntityResolver`仅返回电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="2accc-201">Here, you return only email addresses using `DynamicTableEntity` and `EntityResolver`.</span></span> <span data-ttu-id="2accc-202">请注意，本地存储模拟器不支持投影，因此此代码仅在使用表服务中的帐户时运行。</span><span class="sxs-lookup"><span data-stu-id="2accc-202">Note that projection is not supported on the local storage emulator, so this code runs only when you're using an account on the Table service.</span></span>

[!code-fsharp[TableStorage](~/samples/snippets/fsharp/azure/table-storage.fsx#L147-L158)]

### <a name="retrieve-entities-in-pages-asynchronously"></a><span data-ttu-id="2accc-203">以异步方式检索页中的实体</span><span class="sxs-lookup"><span data-stu-id="2accc-203">Retrieve entities in pages asynchronously</span></span>

<span data-ttu-id="2accc-204">如果正在读取大量实体，并且想要在检索它们时处理它们，而不是等待返回全部实体，则可以使用分段查询。</span><span class="sxs-lookup"><span data-stu-id="2accc-204">If you are reading a large number of entities, and you want to process them as they are retrieved rather than waiting for them all to return, you can use a segmented query.</span></span> <span data-ttu-id="2accc-205">在这里，你将使用异步工作流返回页面结果，以便在你等待返回大量结果时不会阻止执行。</span><span class="sxs-lookup"><span data-stu-id="2accc-205">Here, you return results in pages by using an async workflow so that execution is not blocked while you're waiting for a large set of results to return.</span></span>

[!code-fsharp[TableStorage](~/samples/snippets/fsharp/azure/table-storage.fsx#L163-L178)]

<span data-ttu-id="2accc-206">现在，你可以同步执行此计算：</span><span class="sxs-lookup"><span data-stu-id="2accc-206">You now execute this computation synchronously:</span></span>

[!code-fsharp[TableStorage](~/samples/snippets/fsharp/azure/table-storage.fsx#L180-L180)]

### <a name="delete-an-entity"></a><span data-ttu-id="2accc-207">删除实体</span><span class="sxs-lookup"><span data-stu-id="2accc-207">Delete an entity</span></span>

<span data-ttu-id="2accc-208">检索实体后，可以将其删除。</span><span class="sxs-lookup"><span data-stu-id="2accc-208">You can delete an entity after you have retrieved it.</span></span> <span data-ttu-id="2accc-209">与更新实体一样，如果实体在检索后发生更改，则此操作将失败。</span><span class="sxs-lookup"><span data-stu-id="2accc-209">As with updating an entity, this fails if the entity has changed since you retrieved it.</span></span>

[!code-fsharp[TableStorage](~/samples/snippets/fsharp/azure/table-storage.fsx#L186-L187)]

### <a name="delete-a-table"></a><span data-ttu-id="2accc-210">删除表</span><span class="sxs-lookup"><span data-stu-id="2accc-210">Delete a table</span></span>

<span data-ttu-id="2accc-211">可以从存储帐户中删除表。</span><span class="sxs-lookup"><span data-stu-id="2accc-211">You can delete a table from a storage account.</span></span> <span data-ttu-id="2accc-212">删除的表将无法在删除后的一段时间内重新创建。</span><span class="sxs-lookup"><span data-stu-id="2accc-212">A table that has been deleted will be unavailable to be re-created for a period of time following the deletion.</span></span>

[!code-fsharp[TableStorage](~/samples/snippets/fsharp/azure/table-storage.fsx#L193-L193)]

## <a name="next-steps"></a><span data-ttu-id="2accc-213">后续步骤</span><span class="sxs-lookup"><span data-stu-id="2accc-213">Next steps</span></span>

<span data-ttu-id="2accc-214">现在，你已了解有关表存储的基础知识，请单击下面的链接了解更复杂的存储任务和 Azure Cosmos DB 表 API。</span><span class="sxs-lookup"><span data-stu-id="2accc-214">Now that you've learned the basics of Table storage, follow these links to learn about more complex storage tasks and the Azure Cosmos DB Table API.</span></span>

- [<span data-ttu-id="2accc-215">Azure Cosmos DB 简介表 API</span><span class="sxs-lookup"><span data-stu-id="2accc-215">Introduction to Azure Cosmos DB Table API</span></span>](https://docs.microsoft.com/azure/cosmos-db/table-introduction)
- [<span data-ttu-id="2accc-216">适用于 .NET 的存储客户端库参考</span><span class="sxs-lookup"><span data-stu-id="2accc-216">Storage Client Library for .NET reference</span></span>](https://docs.microsoft.com/dotnet/api/overview/azure/storage?view=azure-dotnet)
- [<span data-ttu-id="2accc-217">Azure 存储类型提供程序</span><span class="sxs-lookup"><span data-stu-id="2accc-217">Azure Storage Type Provider</span></span>](https://fsprojects.github.io/AzureStorageTypeProvider/)
- [<span data-ttu-id="2accc-218">Azure 存储团队博客</span><span class="sxs-lookup"><span data-stu-id="2accc-218">Azure Storage Team Blog</span></span>](https://blogs.msdn.microsoft.com/windowsazurestorage/)
- [<span data-ttu-id="2accc-219">配置连接字符串</span><span class="sxs-lookup"><span data-stu-id="2accc-219">Configuring Connection Strings</span></span>](https://docs.microsoft.com/azure/storage/common/storage-configure-connection-string)
- [<span data-ttu-id="2accc-220">通过 .NET 中的 Azure 表存储入门</span><span class="sxs-lookup"><span data-stu-id="2accc-220">Getting Started with Azure Table Storage in .NET</span></span>](https://azure.microsoft.com/resources/samples/storage-table-dotnet-getting-started/)
