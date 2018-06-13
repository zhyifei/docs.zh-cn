---
title: '要开始使用 Azure 表存储使用 F #'
description: 在云中使用 Azure 表存储或 Azure Cosmos DB 存储结构化的数据。
author: sylvanc
ms.date: 03/26/2018
ms.openlocfilehash: ac81bc88db1436aa4d5f576da61a90839df04b99
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33575387"
---
# <a name="get-started-with-azure-table-storage-and-the-azure-cosmos-db-table-api-using-f"></a><span data-ttu-id="717ad-103">开始使用 Azure 表存储和使用 F # Azure Cosmos DB 表 API</span><span class="sxs-lookup"><span data-stu-id="717ad-103">Get started with Azure Table storage and the Azure Cosmos DB Table API using F#</span></span> # 

<span data-ttu-id="717ad-104">Azure 表存储是将结构化的 NoSQL 数据存储在云中的服务。</span><span class="sxs-lookup"><span data-stu-id="717ad-104">Azure Table storage is a service that stores structured NoSQL data in the cloud.</span></span> <span data-ttu-id="717ad-105">表存储是具有无模式的设计的键/属性存储区。</span><span class="sxs-lookup"><span data-stu-id="717ad-105">Table storage is a key/attribute store with a schemaless design.</span></span> <span data-ttu-id="717ad-106">表存储是无模式，因为它很容易使数据适应随着需求的应用程序发展变化。</span><span class="sxs-lookup"><span data-stu-id="717ad-106">Because Table storage is schemaless, it's easy to adapt your data as the needs of your application evolve.</span></span> <span data-ttu-id="717ad-107">对数据的访问是快速、 经济高效的所有类型的应用程序。</span><span class="sxs-lookup"><span data-stu-id="717ad-107">Access to data is fast and cost-effective for all kinds of applications.</span></span> <span data-ttu-id="717ad-108">表存储是通常显著低于成本传统 SQL 相似的数据量。</span><span class="sxs-lookup"><span data-stu-id="717ad-108">Table storage is typically significantly lower in cost than traditional SQL for similar volumes of data.</span></span>

<span data-ttu-id="717ad-109">你可以使用表存储来存储灵活的数据集，例如 web 应用程序、 通讯簿、 设备信息和的元数据，您的服务需要的任何其他类型的用户数据。</span><span class="sxs-lookup"><span data-stu-id="717ad-109">You can use Table storage to store flexible datasets, such as user data for web applications, address books, device information, and any other type of metadata that your service requires.</span></span> <span data-ttu-id="717ad-110">你可以在表中，存储任意数量的实体和存储帐户可以包含任意数量的表，直至达到存储帐户容量限制。</span><span class="sxs-lookup"><span data-stu-id="717ad-110">You can store any number of entities in a table, and a storage account may contain any number of tables, up to the capacity limit of the storage account.</span></span>

<span data-ttu-id="717ad-111">Azure Cosmos DB 为应用程序编写为 Azure 表存储以及如要求高级功能提供表 API:</span><span class="sxs-lookup"><span data-stu-id="717ad-111">Azure Cosmos DB provides the Table API for applications that are written for Azure Table storage and that require premium capabilities such as:</span></span>

- <span data-ttu-id="717ad-112">关守全局分发。</span><span class="sxs-lookup"><span data-stu-id="717ad-112">Turnkey global distribution.</span></span>
- <span data-ttu-id="717ad-113">全球范围内的专用的吞吐量。</span><span class="sxs-lookup"><span data-stu-id="717ad-113">Dedicated throughput worldwide.</span></span>
- <span data-ttu-id="717ad-114">在的 99%的单位数的毫秒延迟。</span><span class="sxs-lookup"><span data-stu-id="717ad-114">Single-digit millisecond latencies at the 99th percentile.</span></span>
- <span data-ttu-id="717ad-115">保证高可用性。</span><span class="sxs-lookup"><span data-stu-id="717ad-115">Guaranteed high availability.</span></span>
- <span data-ttu-id="717ad-116">自动辅助索引。</span><span class="sxs-lookup"><span data-stu-id="717ad-116">Automatic secondary indexing.</span></span>

<span data-ttu-id="717ad-117">为 Azure 表存储编写的应用程序可以通过使用表 API 进行任何代码更改，将迁移到 Azure Cosmos DB，并充分利用高级功能。</span><span class="sxs-lookup"><span data-stu-id="717ad-117">Applications written for Azure Table storage can migrate to Azure Cosmos DB by using the Table API with no code changes and take advantage of premium capabilities.</span></span> <span data-ttu-id="717ad-118">表 API 具有可用的客户端 Sdk for.NET、 Java、 Python 和 Node.js。</span><span class="sxs-lookup"><span data-stu-id="717ad-118">The Table API has client SDKs available for .NET, Java, Python, and Node.js.</span></span>

<span data-ttu-id="717ad-119">有关详细信息，请参阅[简介 Azure Cosmos DB 表 API](https://docs.microsoft.com/azure/cosmos-db/table-introduction)。</span><span class="sxs-lookup"><span data-stu-id="717ad-119">For more information, see [Introduction to Azure Cosmos DB Table API](https://docs.microsoft.com/azure/cosmos-db/table-introduction).</span></span>

## <a name="about-this-tutorial"></a><span data-ttu-id="717ad-120">关于本教程</span><span class="sxs-lookup"><span data-stu-id="717ad-120">About this tutorial</span></span>

<span data-ttu-id="717ad-121">本教程演示如何编写 F # 代码来执行一些常见的任务，使用 Azure 表存储或 Azure Cosmos DB 表 API，包括创建和删除表和插入、 更新、 删除和查询表数据。</span><span class="sxs-lookup"><span data-stu-id="717ad-121">This tutorial shows how to write F# code to do some common tasks using Azure Table storage or the Azure Cosmos DB Table API, including creating and deleting a table and inserting, updating, deleting, and querying table data.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="717ad-122">系统必备</span><span class="sxs-lookup"><span data-stu-id="717ad-122">Prerequisites</span></span>

<span data-ttu-id="717ad-123">若要使用本指南，你必须首先[创建 Azure 存储帐户](/azure/storage/storage-create-storage-account)或[Azure Cosmos DB 帐户](https://azure.microsoft.com/try/cosmosdb/)。</span><span class="sxs-lookup"><span data-stu-id="717ad-123">To use this guide, you must first [create an Azure storage account](/azure/storage/storage-create-storage-account) or [Azure Cosmos DB account](https://azure.microsoft.com/try/cosmosdb/).</span></span>


## <a name="create-an-f-script-and-start-f-interactive"></a><span data-ttu-id="717ad-124">创建的 F # 脚本并开始 F # 交互</span><span class="sxs-lookup"><span data-stu-id="717ad-124">Create an F# Script and Start F# Interactive</span></span>

<span data-ttu-id="717ad-125">这篇文章中的示例可在 F # 应用程序或 F # 脚本。</span><span class="sxs-lookup"><span data-stu-id="717ad-125">The samples in this article can be used in either an F# application or an F# script.</span></span> <span data-ttu-id="717ad-126">若要创建的 F # 脚本，创建具有的文件`.fsx`扩展，例如`tables.fsx`，F # 开发环境中。</span><span class="sxs-lookup"><span data-stu-id="717ad-126">To create an F# script, create a file with the `.fsx` extension, for example `tables.fsx`, in your F# development environment.</span></span>

<span data-ttu-id="717ad-127">接下来，使用[程序包管理器](package-management.md)如[Paket](https://fsprojects.github.io/Paket/)或[NuGet](https://www.nuget.org/)安装`WindowsAzure.Storage`包和引用`WindowsAzure.Storage.dll`在脚本中使用`#r`指令。</span><span class="sxs-lookup"><span data-stu-id="717ad-127">Next, use a [package manager](package-management.md) such as [Paket](https://fsprojects.github.io/Paket/) or [NuGet](https://www.nuget.org/) to install the `WindowsAzure.Storage` package and reference `WindowsAzure.Storage.dll` in your script using a `#r` directive.</span></span> <span data-ttu-id="717ad-128">不要针对重新`Microsoft.WindowsAzure.ConfigurationManager`以获取 Microsoft.Azure 命名空间。</span><span class="sxs-lookup"><span data-stu-id="717ad-128">Do it again for `Microsoft.WindowsAzure.ConfigurationManager` in order to get the Microsoft.Azure namespace.</span></span>

### <a name="add-namespace-declarations"></a><span data-ttu-id="717ad-129">添加命名空间声明</span><span class="sxs-lookup"><span data-stu-id="717ad-129">Add namespace declarations</span></span>

<span data-ttu-id="717ad-130">添加以下`open`到顶部的语句`tables.fsx`文件：</span><span class="sxs-lookup"><span data-stu-id="717ad-130">Add the following `open` statements to the top of the `tables.fsx` file:</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L1-L5)]

### <a name="get-your-azure-storage-connection-string"></a><span data-ttu-id="717ad-131">获取 Azure 存储连接字符串</span><span class="sxs-lookup"><span data-stu-id="717ad-131">Get your Azure Storage connection string</span></span>

<span data-ttu-id="717ad-132">如果您正在连接到 Azure 存储表服务，你将对于本教程需要你的连接字符串。</span><span class="sxs-lookup"><span data-stu-id="717ad-132">If you're connecting to Azure Storage Table service, you'll need your connection string for this tutorial.</span></span> <span data-ttu-id="717ad-133">你可以从 Azure 门户复制你的连接字符串。</span><span class="sxs-lookup"><span data-stu-id="717ad-133">You can copy your connection string from the Azure portal.</span></span> <span data-ttu-id="717ad-134">有关连接字符串的详细信息，请参阅[配置存储连接字符串](/azure/storage/storage-configure-connection-string)。</span><span class="sxs-lookup"><span data-stu-id="717ad-134">For more information about connection strings, see [Configure Storage Connection Strings](/azure/storage/storage-configure-connection-string).</span></span>

### <a name="get-your-azure-cosmos-db-connection-string"></a><span data-ttu-id="717ad-135">获取 Azure Cosmos DB 连接字符串</span><span class="sxs-lookup"><span data-stu-id="717ad-135">Get your Azure Cosmos DB connection string</span></span>

<span data-ttu-id="717ad-136">如果您正在连接到 Azure Cosmos DB，你将对于本教程需要你的连接字符串。</span><span class="sxs-lookup"><span data-stu-id="717ad-136">If you're connecting to Azure Cosmos DB, you'll need your connection string for this tutorial.</span></span> <span data-ttu-id="717ad-137">你可以从 Azure 门户复制你的连接字符串。</span><span class="sxs-lookup"><span data-stu-id="717ad-137">You can copy your connection string from the Azure portal.</span></span> <span data-ttu-id="717ad-138">在 Azure 门户中，在你 Cosmos DB 的帐户，请转到**设置** > **连接字符串**，然后单击**复制**按钮以复制主连接字符串。</span><span class="sxs-lookup"><span data-stu-id="717ad-138">In the Azure portal, in your Cosmos DB account, go to **Settings** > **Connection String**, and click the **Copy** button to copy your Primary Connection String.</span></span> 

<span data-ttu-id="717ad-139">本教程中，在脚本中，如下例所示输入您的连接字符串：</span><span class="sxs-lookup"><span data-stu-id="717ad-139">For the tutorial, enter your connection string in your script, like the following example:</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L11-L11)]

<span data-ttu-id="717ad-140">但是，这是**不建议**的实际项目。</span><span class="sxs-lookup"><span data-stu-id="717ad-140">However, this is **not recommended** for real projects.</span></span> <span data-ttu-id="717ad-141">你的存储帐户密钥是类似于你的存储帐户的根密码。</span><span class="sxs-lookup"><span data-stu-id="717ad-141">Your storage account key is similar to the root password for your storage account.</span></span> <span data-ttu-id="717ad-142">始终必须小心地保护你的存储帐户密钥。</span><span class="sxs-lookup"><span data-stu-id="717ad-142">Always be careful to protect your storage account key.</span></span> <span data-ttu-id="717ad-143">避免将其分发给其他用户，硬编码，或将其保存在其他人可以访问的纯文本格式的文件。</span><span class="sxs-lookup"><span data-stu-id="717ad-143">Avoid distributing it to other users, hard-coding it, or saving it in a plain-text file that is accessible to others.</span></span> <span data-ttu-id="717ad-144">你可以重新生成你使用 Azure 门户，如果你认为可能已泄露的密钥。</span><span class="sxs-lookup"><span data-stu-id="717ad-144">You can regenerate your key using the Azure Portal if you believe it may have been compromised.</span></span>

<span data-ttu-id="717ad-145">为实际的应用程序，维护存储连接字符串的最佳方法是在配置文件中。</span><span class="sxs-lookup"><span data-stu-id="717ad-145">For real applications, the best way to maintain your storage connection string is in a configuration file.</span></span> <span data-ttu-id="717ad-146">若要从配置文件中提取的连接字符串，您可以执行此操作：</span><span class="sxs-lookup"><span data-stu-id="717ad-146">To fetch the connection string from a configuration file, you can do this:</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L13-L15)]

<span data-ttu-id="717ad-147">使用 Azure 配置管理器是可选的。</span><span class="sxs-lookup"><span data-stu-id="717ad-147">Using Azure Configuration Manager is optional.</span></span> <span data-ttu-id="717ad-148">你还可以使用 API，如.NET Framework 的`ConfigurationManager`类型。</span><span class="sxs-lookup"><span data-stu-id="717ad-148">You can also use an API such as the .NET Framework's `ConfigurationManager` type.</span></span>

### <a name="parse-the-connection-string"></a><span data-ttu-id="717ad-149">分析连接字符串</span><span class="sxs-lookup"><span data-stu-id="717ad-149">Parse the connection string</span></span>

<span data-ttu-id="717ad-150">若要分析的连接字符串，请使用：</span><span class="sxs-lookup"><span data-stu-id="717ad-150">To parse the connection string, use:</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L21-L22)]

<span data-ttu-id="717ad-151">这将返回`CloudStorageAccount`。</span><span class="sxs-lookup"><span data-stu-id="717ad-151">This returns a `CloudStorageAccount`.</span></span>

### <a name="create-the-table-service-client"></a><span data-ttu-id="717ad-152">创建表服务客户端</span><span class="sxs-lookup"><span data-stu-id="717ad-152">Create the Table service client</span></span>

<span data-ttu-id="717ad-153">`CloudTableClient`类使你能够检索表和表存储中的实体。</span><span class="sxs-lookup"><span data-stu-id="717ad-153">The `CloudTableClient` class enables you to retrieve tables and entities in Table storage.</span></span> <span data-ttu-id="717ad-154">下面是创建服务客户端的一种方法：</span><span class="sxs-lookup"><span data-stu-id="717ad-154">Here's one way to create the service client:</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L28-L29)]

<span data-ttu-id="717ad-155">现在，你就可以编写代码，从读取数据并将数据写入表存储了。</span><span class="sxs-lookup"><span data-stu-id="717ad-155">Now you are ready to write code that reads data from and writes data to Table storage.</span></span>

### <a name="create-a-table"></a><span data-ttu-id="717ad-156">创建表</span><span class="sxs-lookup"><span data-stu-id="717ad-156">Create a table</span></span>

<span data-ttu-id="717ad-157">此示例演示如何创建表，如果不存在：</span><span class="sxs-lookup"><span data-stu-id="717ad-157">This example shows how to create a table if it does not already exist:</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L35-L39)]

### <a name="add-an-entity-to-a-table"></a><span data-ttu-id="717ad-158">向表中添加实体</span><span class="sxs-lookup"><span data-stu-id="717ad-158">Add an entity to a table</span></span>

<span data-ttu-id="717ad-159">实体必须具有从继承的类型`TableEntity`。</span><span class="sxs-lookup"><span data-stu-id="717ad-159">An entity has to have a type that inherits from `TableEntity`.</span></span> <span data-ttu-id="717ad-160">你可以扩展`TableEntity`中任何方式，但你类型*必须*具有无参数构造函数。</span><span class="sxs-lookup"><span data-stu-id="717ad-160">You can extend `TableEntity` in any way you like, but your type *must* have a parameter-less constructor.</span></span> <span data-ttu-id="717ad-161">同时具有的属性`get`和`set`存储在 Azure 表。</span><span class="sxs-lookup"><span data-stu-id="717ad-161">Only properties that have both `get` and `set` are stored in your Azure Table.</span></span>

<span data-ttu-id="717ad-162">实体的分区键和行键唯一地标识表中的实体。</span><span class="sxs-lookup"><span data-stu-id="717ad-162">An entity's partition and row key uniquely identify the entity in the table.</span></span> <span data-ttu-id="717ad-163">具有相同的分区键的实体的查询查询可以速度快于具有不同的分区键，但使用不同的分区键可实现的并行操作可伸缩性更好。</span><span class="sxs-lookup"><span data-stu-id="717ad-163">Entities with the same partition key can be queried faster than those with different partition keys, but using diverse partition keys allows for greater scalability of parallel operations.</span></span>

<span data-ttu-id="717ad-164">下面是一个示例的`Customer`使用`lastName`作为分区键和`firstName`作为行键。</span><span class="sxs-lookup"><span data-stu-id="717ad-164">Here's an example of a `Customer` that uses the `lastName` as the partition key and the `firstName` as the row key.</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L45-L52)]

<span data-ttu-id="717ad-165">现在添加`Customer`到表。</span><span class="sxs-lookup"><span data-stu-id="717ad-165">Now add `Customer` to the table.</span></span> <span data-ttu-id="717ad-166">为此，请创建`TableOperation`对表执行。</span><span class="sxs-lookup"><span data-stu-id="717ad-166">To do so, create a `TableOperation` that executes on the table.</span></span> <span data-ttu-id="717ad-167">在这种情况下，创建`Insert`操作。</span><span class="sxs-lookup"><span data-stu-id="717ad-167">In this case, you create an `Insert` operation.</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L54-L55)]

### <a name="insert-a-batch-of-entities"></a><span data-ttu-id="717ad-168">插入一批实体</span><span class="sxs-lookup"><span data-stu-id="717ad-168">Insert a batch of entities</span></span>

<span data-ttu-id="717ad-169">你可以将一批实体插入表使用单个写入操作。</span><span class="sxs-lookup"><span data-stu-id="717ad-169">You can insert a batch of entities into a table using a single write operation.</span></span> <span data-ttu-id="717ad-170">批处理操作允许您将操作合并为单个的执行，但它们具有一些限制：</span><span class="sxs-lookup"><span data-stu-id="717ad-170">Batch operations allow you to combine operations into a single execution, but they have some restrictions:</span></span>

- <span data-ttu-id="717ad-171">你可以执行更新、 删除和插入相同的批处理操作中。</span><span class="sxs-lookup"><span data-stu-id="717ad-171">You can perform updates, deletes, and inserts in the same batch operation.</span></span>
- <span data-ttu-id="717ad-172">批处理操作可包含最多 100 个实体。</span><span class="sxs-lookup"><span data-stu-id="717ad-172">A batch operation can include up to 100 entities.</span></span>
- <span data-ttu-id="717ad-173">批处理操作中的所有实体都必须都具有相同的分区键。</span><span class="sxs-lookup"><span data-stu-id="717ad-173">All entities in a batch operation must have the same partition key.</span></span>
- <span data-ttu-id="717ad-174">可以通过批处理操作中执行查询时，它必须是批处理中仅有的操作。</span><span class="sxs-lookup"><span data-stu-id="717ad-174">While it is possible to perform a query in a batch operation, it must be the only operation in the batch.</span></span>

<span data-ttu-id="717ad-175">下面是一些代码，将两个插入合并到批处理操作：</span><span class="sxs-lookup"><span data-stu-id="717ad-175">Here's some code that combines two inserts into a batch operation:</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L62-L71)]

### <a name="retrieve-all-entities-in-a-partition"></a><span data-ttu-id="717ad-176">检索分区中的所有实体</span><span class="sxs-lookup"><span data-stu-id="717ad-176">Retrieve all entities in a partition</span></span>

<span data-ttu-id="717ad-177">若要查询表以获取分区中的所有实体，使用`TableQuery`对象。</span><span class="sxs-lookup"><span data-stu-id="717ad-177">To query a table for all entities in a partition, use a `TableQuery` object.</span></span> <span data-ttu-id="717ad-178">在这里，你的筛选实体"Smith"所在的分区键。</span><span class="sxs-lookup"><span data-stu-id="717ad-178">Here, you filter for entities where "Smith" is the partition key.</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L77-L82)]

<span data-ttu-id="717ad-179">你现在打印结果：</span><span class="sxs-lookup"><span data-stu-id="717ad-179">You now print the results:</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L84-L85)]


### <a name="retrieve-a-range-of-entities-in-a-partition"></a><span data-ttu-id="717ad-180">检索分区中实体的一部分</span><span class="sxs-lookup"><span data-stu-id="717ad-180">Retrieve a range of entities in a partition</span></span>

<span data-ttu-id="717ad-181">如果你不想查询分区中的所有实体，你可以通过组合分区键筛选器与行键筛选器来指定一个范围。</span><span class="sxs-lookup"><span data-stu-id="717ad-181">If you don't want to query all the entities in a partition, you can specify a range by combining the partition key filter with a row key filter.</span></span> <span data-ttu-id="717ad-182">在这里，你使用两个筛选器来获取"Smith"分区的所有实体，行键 （名字） 以字母开头早于字母表中的"M"。</span><span class="sxs-lookup"><span data-stu-id="717ad-182">Here, you use two filters to get all entities in the "Smith" partition where the row key (first name) starts with a letter earlier than "M" in the alphabet.</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L91-L100)]

<span data-ttu-id="717ad-183">你现在打印结果：</span><span class="sxs-lookup"><span data-stu-id="717ad-183">You now print the results:</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L102-L103)]

### <a name="retrieve-a-single-entity"></a><span data-ttu-id="717ad-184">检索单个实体</span><span class="sxs-lookup"><span data-stu-id="717ad-184">Retrieve a single entity</span></span>

<span data-ttu-id="717ad-185">你可以编写查询以检索单个特定实体。</span><span class="sxs-lookup"><span data-stu-id="717ad-185">You can write a query to retrieve a single, specific entity.</span></span> <span data-ttu-id="717ad-186">在这里，使用`TableOperation`来指定客户"Ben Smith"。</span><span class="sxs-lookup"><span data-stu-id="717ad-186">Here, you use a `TableOperation` to specify the customer "Ben Smith".</span></span> <span data-ttu-id="717ad-187">而不是一个集合，则将取回`Customer`。</span><span class="sxs-lookup"><span data-stu-id="717ad-187">Instead of a collection, you get back a `Customer`.</span></span> <span data-ttu-id="717ad-188">在查询中指定分区键和行键是从表服务中检索单个实体的最快方法。</span><span class="sxs-lookup"><span data-stu-id="717ad-188">Specifying both the partition key and the row key in a query is the fastest way to retrieve a single entity from the Table service.</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L109-L111)]

<span data-ttu-id="717ad-189">你现在打印结果：</span><span class="sxs-lookup"><span data-stu-id="717ad-189">You now print the results:</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L113-L115)]


### <a name="replace-an-entity"></a><span data-ttu-id="717ad-190">替换实体</span><span class="sxs-lookup"><span data-stu-id="717ad-190">Replace an entity</span></span>

<span data-ttu-id="717ad-191">若要更新实体，从表服务中检索它，修改实体对象，然后将所做的更改保存回表服务使用`Replace`操作。</span><span class="sxs-lookup"><span data-stu-id="717ad-191">To update an entity, retrieve it from the Table service, modify the entity object, and then save the changes back to the Table service using a `Replace` operation.</span></span> <span data-ttu-id="717ad-192">这将导致在服务器上，将完全替换该实体，除非服务器上的该实体已更改自检索之后，在这种情况下则操作将失败。</span><span class="sxs-lookup"><span data-stu-id="717ad-192">This causes the entity to be fully replaced on the server, unless the entity on the server has changed since it was retrieved, in which case the operation fails.</span></span> <span data-ttu-id="717ad-193">此失败将防止你的应用程序无意中覆盖从其他源的更改。</span><span class="sxs-lookup"><span data-stu-id="717ad-193">This failure is to prevent your application from inadvertently overwriting changes from other sources.</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L121-L128)]

### <a name="insert-or-replace-an-entity"></a><span data-ttu-id="717ad-194">插入或替换实体</span><span class="sxs-lookup"><span data-stu-id="717ad-194">Insert-or-replace an entity</span></span>

<span data-ttu-id="717ad-195">有时，你不知道表中是否存在实体。</span><span class="sxs-lookup"><span data-stu-id="717ad-195">Sometimes, you don't know whether an entity exists in the table.</span></span> <span data-ttu-id="717ad-196">并且如果是这样，不再需要存储在它的当前值。</span><span class="sxs-lookup"><span data-stu-id="717ad-196">And if it does, the current values stored in it are no longer needed.</span></span> <span data-ttu-id="717ad-197">你可以使用`InsertOrReplace`创建实体，或者将其替换如果它存在，而不考虑其状态。</span><span class="sxs-lookup"><span data-stu-id="717ad-197">You can use `InsertOrReplace` to create the entity, or replace it if it exists, regardless of its state.</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L134-L141)]

### <a name="query-a-subset-of-entity-properties"></a><span data-ttu-id="717ad-198">查询实体属性子集</span><span class="sxs-lookup"><span data-stu-id="717ad-198">Query a subset of entity properties</span></span>

<span data-ttu-id="717ad-199">表查询可以检索的几个属性，而不是所有这些实体中。</span><span class="sxs-lookup"><span data-stu-id="717ad-199">A table query can retrieve just a few properties from an entity instead of all of them.</span></span> <span data-ttu-id="717ad-200">此方法称为投影，可以提高查询性能，尤其适用于大型实体。</span><span class="sxs-lookup"><span data-stu-id="717ad-200">This technique, called projection, can improve query performance, especially for large entities.</span></span> <span data-ttu-id="717ad-201">在这里，你返回仅电子邮件地址使用`DynamicTableEntity`和`EntityResolver`。</span><span class="sxs-lookup"><span data-stu-id="717ad-201">Here, you return only email addresses using `DynamicTableEntity` and `EntityResolver`.</span></span> <span data-ttu-id="717ad-202">请注意，不支持投影在本地存储仿真程序，因此仅当你在上表服务使用的帐户时，在运行此代码。</span><span class="sxs-lookup"><span data-stu-id="717ad-202">Note that projection is not supported on the local storage emulator, so this code runs only when you're using an account on the Table service.</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L147-L158)]

### <a name="retrieve-entities-in-pages-asynchronously"></a><span data-ttu-id="717ad-203">以异步方式检索页中的实体</span><span class="sxs-lookup"><span data-stu-id="717ad-203">Retrieve entities in pages asynchronously</span></span>

<span data-ttu-id="717ad-204">如果您正在读取大量实体，并且你想要在检索，而不是等待其全部返回，可以使用分段的查询时进行处理。</span><span class="sxs-lookup"><span data-stu-id="717ad-204">If you are reading a large number of entities, and you want to process them as they are retrieved rather than waiting for them all to return, you can use a segmented query.</span></span> <span data-ttu-id="717ad-205">在这里，你结果在页中返回通过使用异步工作流，以便为大量要返回的结果在等待时，将不会阻止执行。</span><span class="sxs-lookup"><span data-stu-id="717ad-205">Here, you return results in pages by using an async workflow so that execution is not blocked while you're waiting for a large set of results to return.</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L163-L178)]

<span data-ttu-id="717ad-206">你现在以同步方式执行此计算：</span><span class="sxs-lookup"><span data-stu-id="717ad-206">You now execute this computation synchronously:</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L180-L180)]

### <a name="delete-an-entity"></a><span data-ttu-id="717ad-207">删除实体</span><span class="sxs-lookup"><span data-stu-id="717ad-207">Delete an entity</span></span>

<span data-ttu-id="717ad-208">你可以在检索后删除实体。</span><span class="sxs-lookup"><span data-stu-id="717ad-208">You can delete an entity after you have retrieved it.</span></span> <span data-ttu-id="717ad-209">使用更新实体，此操作失败如果该实体自从你检索到它以后发生更改。</span><span class="sxs-lookup"><span data-stu-id="717ad-209">As with updating an entity, this fails if the entity has changed since you retrieved it.</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L186-L187)]

### <a name="delete-a-table"></a><span data-ttu-id="717ad-210">删除表</span><span class="sxs-lookup"><span data-stu-id="717ad-210">Delete a table</span></span>

<span data-ttu-id="717ad-211">你可以从存储帐户中删除表。</span><span class="sxs-lookup"><span data-stu-id="717ad-211">You can delete a table from a storage account.</span></span> <span data-ttu-id="717ad-212">已删除的表将不可用的一段时间之后必须重新创建。</span><span class="sxs-lookup"><span data-stu-id="717ad-212">A table that has been deleted will be unavailable to be re-created for a period of time following the deletion.</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L193-L193)]

## <a name="next-steps"></a><span data-ttu-id="717ad-213">后续步骤</span><span class="sxs-lookup"><span data-stu-id="717ad-213">Next steps</span></span>

<span data-ttu-id="717ad-214">现在，你已了解表存储的基础知识，单击下面的链接以了解更复杂的存储任务和 Azure Cosmos DB 表 API。</span><span class="sxs-lookup"><span data-stu-id="717ad-214">Now that you've learned the basics of Table storage, follow these links to learn about more complex storage tasks and the Azure Cosmos DB Table API.</span></span>

- [<span data-ttu-id="717ad-215">Azure Cosmos DB 表 API 简介</span><span class="sxs-lookup"><span data-stu-id="717ad-215">Introduction to Azure Cosmos DB Table API</span></span>](https://docs.microsoft.com/azure/cosmos-db/table-introduction)
- [<span data-ttu-id="717ad-216">存储客户端库.NET 参考</span><span class="sxs-lookup"><span data-stu-id="717ad-216">Storage Client Library for .NET reference</span></span>](https://docs.microsoft.com/dotnet/api/overview/azure/storage?view=azure-dotnet)
- [<span data-ttu-id="717ad-217">Azure 存储类型提供程序</span><span class="sxs-lookup"><span data-stu-id="717ad-217">Azure Storage Type Provider</span></span>](http://fsprojects.github.io/AzureStorageTypeProvider/)
- [<span data-ttu-id="717ad-218">Azure 存储团队博客</span><span class="sxs-lookup"><span data-stu-id="717ad-218">Azure Storage Team Blog</span></span>](http://blogs.msdn.com/b/windowsazurestorage/)
- [<span data-ttu-id="717ad-219">配置连接字符串</span><span class="sxs-lookup"><span data-stu-id="717ad-219">Configuring Connection Strings</span></span>](https://docs.microsoft.com/azure/storage/common/storage-configure-connection-string)
- [<span data-ttu-id="717ad-220">在.NET 的 Azure 表存储入门</span><span class="sxs-lookup"><span data-stu-id="717ad-220">Getting Started with Azure Table Storage in .NET</span></span>](https://azure.microsoft.com/resources/samples/storage-table-dotnet-getting-started/)
