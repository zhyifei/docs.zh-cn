---
title: "要开始使用 Azure 表存储使用 F #"
description: "在云中使用 Azure 表存储，NoSQL 数据存储中存储结构化的数据。"
keywords: "visual f #、 f # 中，函数编程，.NET，.NET 核心，Azure"
author: sylvanc
ms.author: phcart
ms.date: 09/20/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 9e5d6cea-a98c-461e-a5cc-75f1d154eafd
ms.openlocfilehash: 905374a60261b0c2a863edb956943d41ae80f04d
ms.sourcegitcommit: 655fd4f78741967f80c409cef98347fdcf77857d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/28/2018
---
# <a name="get-started-with-azure-table-storage-using-f"></a><span data-ttu-id="adef2-104">要开始使用 Azure 表存储使用 F #</span><span class="sxs-lookup"><span data-stu-id="adef2-104">Get started with Azure Table storage using F#</span></span> #

<span data-ttu-id="adef2-105">Azure 表存储是将结构化的 NoSQL 数据存储在云中的服务。</span><span class="sxs-lookup"><span data-stu-id="adef2-105">Azure Table storage is a service that stores structured NoSQL data in the cloud.</span></span> <span data-ttu-id="adef2-106">表存储是具有无模式的设计的键/属性存储区。</span><span class="sxs-lookup"><span data-stu-id="adef2-106">Table storage is a key/attribute store with a schemaless design.</span></span> <span data-ttu-id="adef2-107">表存储是无模式，因为它很容易使数据适应随着需求的应用程序发展变化。</span><span class="sxs-lookup"><span data-stu-id="adef2-107">Because Table storage is schemaless, it's easy to adapt your data as the needs of your application evolve.</span></span> <span data-ttu-id="adef2-108">对数据的访问是快速、 经济高效的所有类型的应用程序。</span><span class="sxs-lookup"><span data-stu-id="adef2-108">Access to data is fast and cost-effective for all kinds of applications.</span></span> <span data-ttu-id="adef2-109">表存储是通常显著低于成本传统 SQL 相似的数据量。</span><span class="sxs-lookup"><span data-stu-id="adef2-109">Table storage is typically significantly lower in cost than traditional SQL for similar volumes of data.</span></span>

<span data-ttu-id="adef2-110">你可以使用表存储来存储灵活的数据集，例如 web 应用程序、 通讯簿、 设备信息和的元数据，您的服务需要的任何其他类型的用户数据。</span><span class="sxs-lookup"><span data-stu-id="adef2-110">You can use Table storage to store flexible datasets, such as user data for web applications, address books, device information, and any other type of metadata that your service requires.</span></span> <span data-ttu-id="adef2-111">你可以在表中，存储任意数量的实体和存储帐户可以包含任意数量的表，直至达到存储帐户容量限制。</span><span class="sxs-lookup"><span data-stu-id="adef2-111">You can store any number of entities in a table, and a storage account may contain any number of tables, up to the capacity limit of the storage account.</span></span>

### <a name="about-this-tutorial"></a><span data-ttu-id="adef2-112">关于本教程</span><span class="sxs-lookup"><span data-stu-id="adef2-112">About this tutorial</span></span>

<span data-ttu-id="adef2-113">本教程演示如何编写 F # 代码来执行一些常见的任务，使用 Azure 表存储，包括创建和删除表和插入、 更新、 删除和查询表数据。</span><span class="sxs-lookup"><span data-stu-id="adef2-113">This tutorial shows how to write F# code to do some common tasks using Azure Table storage, including creating and deleting a table and inserting, updating, deleting, and querying table data.</span></span>

<span data-ttu-id="adef2-114">有关表存储的概念概述，请参阅[表存储.NET 指南](/azure/storage/storage-dotnet-how-to-use-tables)</span><span class="sxs-lookup"><span data-stu-id="adef2-114">For a conceptual overview of table storage, please see [the .NET guide for table storage](/azure/storage/storage-dotnet-how-to-use-tables)</span></span>

## <a name="prerequisites"></a><span data-ttu-id="adef2-115">系统必备</span><span class="sxs-lookup"><span data-stu-id="adef2-115">Prerequisites</span></span>

<span data-ttu-id="adef2-116">若要使用本指南，你必须首先[创建 Azure 存储帐户](/azure/storage/storage-create-storage-account)。</span><span class="sxs-lookup"><span data-stu-id="adef2-116">To use this guide, you must first [create an Azure storage account](/azure/storage/storage-create-storage-account).</span></span>
<span data-ttu-id="adef2-117">此外需要为此帐户存储访问密钥。</span><span class="sxs-lookup"><span data-stu-id="adef2-117">You'll also need your storage access key for this account.</span></span>

## <a name="create-an-f-script-and-start-f-interactive"></a><span data-ttu-id="adef2-118">创建的 F # 脚本并开始 F # 交互</span><span class="sxs-lookup"><span data-stu-id="adef2-118">Create an F# Script and Start F# Interactive</span></span>

<span data-ttu-id="adef2-119">这篇文章中的示例可在 F # 应用程序或 F # 脚本。</span><span class="sxs-lookup"><span data-stu-id="adef2-119">The samples in this article can be used in either an F# application or an F# script.</span></span> <span data-ttu-id="adef2-120">若要创建的 F # 脚本，创建具有的文件`.fsx`扩展，例如`tables.fsx`，F # 开发环境中。</span><span class="sxs-lookup"><span data-stu-id="adef2-120">To create an F# script, create a file with the `.fsx` extension, for example `tables.fsx`, in your F# development environment.</span></span>

<span data-ttu-id="adef2-121">接下来，使用[程序包管理器](package-management.md)如[Paket](https://fsprojects.github.io/Paket/)或[NuGet](https://www.nuget.org/)安装`WindowsAzure.Storage`包和引用`WindowsAzure.Storage.dll`在脚本中使用`#r`指令。</span><span class="sxs-lookup"><span data-stu-id="adef2-121">Next, use a [package manager](package-management.md) such as [Paket](https://fsprojects.github.io/Paket/) or [NuGet](https://www.nuget.org/) to install the `WindowsAzure.Storage` package and reference `WindowsAzure.Storage.dll` in your script using a `#r` directive.</span></span> <span data-ttu-id="adef2-122">执行此再次为 Microsoft.WindowsAzure.ConfigurationManager 操作以获取 Microsoft.Azure 命名空间。</span><span class="sxs-lookup"><span data-stu-id="adef2-122">Do it again for \`Microsoft.WindowsAzure.ConfigurationManager' in order to get the Microsoft.Azure namespace.</span></span>

### <a name="add-namespace-declarations"></a><span data-ttu-id="adef2-123">添加命名空间声明</span><span class="sxs-lookup"><span data-stu-id="adef2-123">Add namespace declarations</span></span>

<span data-ttu-id="adef2-124">添加以下`open`到顶部的语句`tables.fsx`文件：</span><span class="sxs-lookup"><span data-stu-id="adef2-124">Add the following `open` statements to the top of the `tables.fsx` file:</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L1-L5)]

### <a name="get-your-connection-string"></a><span data-ttu-id="adef2-125">获取连接字符串</span><span class="sxs-lookup"><span data-stu-id="adef2-125">Get your connection string</span></span>

<span data-ttu-id="adef2-126">对于本教程，你将需要一个 Azure 存储连接字符串。</span><span class="sxs-lookup"><span data-stu-id="adef2-126">You'll need an Azure Storage connection string for this tutorial.</span></span> <span data-ttu-id="adef2-127">有关连接字符串的详细信息，请参阅[配置存储连接字符串](/azure/storage/storage-configure-connection-string)。</span><span class="sxs-lookup"><span data-stu-id="adef2-127">For more information about connection strings, see [Configure Storage Connection Strings](/azure/storage/storage-configure-connection-string).</span></span>

<span data-ttu-id="adef2-128">对于本教程中，您将在脚本中，如下输入你的连接字符串：</span><span class="sxs-lookup"><span data-stu-id="adef2-128">For the tutorial, you'll enter your connection string in your script, like this:</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L11-L11)]

<span data-ttu-id="adef2-129">但是，这是**不建议**的实际项目。</span><span class="sxs-lookup"><span data-stu-id="adef2-129">However, this is **not recommended** for real projects.</span></span> <span data-ttu-id="adef2-130">你的存储帐户密钥是类似于你的存储帐户的根密码。</span><span class="sxs-lookup"><span data-stu-id="adef2-130">Your storage account key is similar to the root password for your storage account.</span></span> <span data-ttu-id="adef2-131">始终必须小心地保护你的存储帐户密钥。</span><span class="sxs-lookup"><span data-stu-id="adef2-131">Always be careful to protect your storage account key.</span></span> <span data-ttu-id="adef2-132">避免将其分发给其他用户，硬编码，或将其保存在其他人可以访问的纯文本格式的文件。</span><span class="sxs-lookup"><span data-stu-id="adef2-132">Avoid distributing it to other users, hard-coding it, or saving it in a plain-text file that is accessible to others.</span></span> <span data-ttu-id="adef2-133">你可以重新生成你使用 Azure 门户，如果你认为可能已泄露的密钥。</span><span class="sxs-lookup"><span data-stu-id="adef2-133">You can regenerate your key using the Azure Portal if you believe it may have been compromised.</span></span>

<span data-ttu-id="adef2-134">为实际的应用程序，维护存储连接字符串的最佳方法是在配置文件中。</span><span class="sxs-lookup"><span data-stu-id="adef2-134">For real applications, the best way to maintain your storage connection string is in a configuration file.</span></span> <span data-ttu-id="adef2-135">若要从配置文件中提取的连接字符串，您可以执行此操作：</span><span class="sxs-lookup"><span data-stu-id="adef2-135">To fetch the connection string from a configuration file, you can do this:</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L13-L15)]

<span data-ttu-id="adef2-136">使用 Azure 配置管理器是可选的。</span><span class="sxs-lookup"><span data-stu-id="adef2-136">Using Azure Configuration Manager is optional.</span></span> <span data-ttu-id="adef2-137">你还可以使用 API，如.NET Framework 的`ConfigurationManager`类型。</span><span class="sxs-lookup"><span data-stu-id="adef2-137">You can also use an API such as the .NET Framework's `ConfigurationManager` type.</span></span>

### <a name="parse-the-connection-string"></a><span data-ttu-id="adef2-138">分析连接字符串</span><span class="sxs-lookup"><span data-stu-id="adef2-138">Parse the connection string</span></span>

<span data-ttu-id="adef2-139">若要分析的连接字符串，请使用：</span><span class="sxs-lookup"><span data-stu-id="adef2-139">To parse the connection string, use:</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L21-L22)]

<span data-ttu-id="adef2-140">这将返回`CloudStorageAccount`。</span><span class="sxs-lookup"><span data-stu-id="adef2-140">This will return a `CloudStorageAccount`.</span></span>

### <a name="create-the-table-service-client"></a><span data-ttu-id="adef2-141">创建表服务客户端</span><span class="sxs-lookup"><span data-stu-id="adef2-141">Create the Table service client</span></span>

<span data-ttu-id="adef2-142">`CloudTableClient`类使你能够检索表和实体存储在表存储。</span><span class="sxs-lookup"><span data-stu-id="adef2-142">The `CloudTableClient` class enables you to retrieve tables and entities stored in Table storage.</span></span> <span data-ttu-id="adef2-143">下面是创建服务客户端的一种方法：</span><span class="sxs-lookup"><span data-stu-id="adef2-143">Here's one way to create the service client:</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L28-L29)]

<span data-ttu-id="adef2-144">现在，你就可以编写代码，从读取数据并将数据写入表存储了。</span><span class="sxs-lookup"><span data-stu-id="adef2-144">Now you are ready to write code that reads data from and writes data to Table storage.</span></span>

## <a name="create-a-table"></a><span data-ttu-id="adef2-145">创建表</span><span class="sxs-lookup"><span data-stu-id="adef2-145">Create a table</span></span>

<span data-ttu-id="adef2-146">此示例演示如何创建表，如果不存在：</span><span class="sxs-lookup"><span data-stu-id="adef2-146">This example shows how to create a table if it does not already exist:</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L35-L39)]

## <a name="add-an-entity-to-a-table"></a><span data-ttu-id="adef2-147">向表中添加实体</span><span class="sxs-lookup"><span data-stu-id="adef2-147">Add an entity to a table</span></span>

<span data-ttu-id="adef2-148">实体必须具有从继承的类型`TableEntity`。</span><span class="sxs-lookup"><span data-stu-id="adef2-148">An entity has to have a type that inherits from `TableEntity`.</span></span> <span data-ttu-id="adef2-149">你可以扩展`TableEntity`中任何方式，但你类型*必须*具有无参数构造函数。</span><span class="sxs-lookup"><span data-stu-id="adef2-149">You can extend `TableEntity` in any way you like, but your type *must* have a parameter-less constructor.</span></span> <span data-ttu-id="adef2-150">同时具有的属性`get`和`set`将存储在 Azure 表。</span><span class="sxs-lookup"><span data-stu-id="adef2-150">Only properties that have both `get` and `set` will be stored in your Azure Table.</span></span>

<span data-ttu-id="adef2-151">实体的分区键和行键唯一地标识表中的实体。</span><span class="sxs-lookup"><span data-stu-id="adef2-151">An entity's partition and row key uniquely identify the entity in the table.</span></span> <span data-ttu-id="adef2-152">具有相同的分区键的实体的查询查询可以速度快于具有不同的分区键，但使用不同的分区键可实现的并行操作可伸缩性更好。</span><span class="sxs-lookup"><span data-stu-id="adef2-152">Entities with the same partition key can be queried faster than those with different partition keys, but using diverse partition keys allows for greater scalability of parallel operations.</span></span>

<span data-ttu-id="adef2-153">下面是一个示例的`Customer`使用`lastName`作为分区键和`firstName`作为行键。</span><span class="sxs-lookup"><span data-stu-id="adef2-153">Here's an example of a `Customer` that uses the `lastName` as the partition key and the `firstName` as the row key.</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L45-L52)]

<span data-ttu-id="adef2-154">现在，我们将添加我们`Customer`到表。</span><span class="sxs-lookup"><span data-stu-id="adef2-154">Now we'll add our `Customer` to the table.</span></span> <span data-ttu-id="adef2-155">若要执行此操作，你可以创建`TableOperation`，将在表上执行。</span><span class="sxs-lookup"><span data-stu-id="adef2-155">To do so, you create a `TableOperation` that will execute on the table.</span></span> <span data-ttu-id="adef2-156">在这种情况下，创建`Insert`操作。</span><span class="sxs-lookup"><span data-stu-id="adef2-156">In this case, you create an `Insert` operation.</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L54-L55)]

## <a name="insert-a-batch-of-entities"></a><span data-ttu-id="adef2-157">插入一批实体</span><span class="sxs-lookup"><span data-stu-id="adef2-157">Insert a batch of entities</span></span>

<span data-ttu-id="adef2-158">你可以将一批实体插入表使用单个写入操作。</span><span class="sxs-lookup"><span data-stu-id="adef2-158">You can insert a batch of entities into a table using a single write operation.</span></span> <span data-ttu-id="adef2-159">批处理操作允许您将操作合并为单个的执行，但它们具有一些限制：</span><span class="sxs-lookup"><span data-stu-id="adef2-159">Batch operations allow you to combine operations into a single execution, but they have some restrictions:</span></span>

- <span data-ttu-id="adef2-160">你可以执行更新、 删除和插入相同的批处理操作中。</span><span class="sxs-lookup"><span data-stu-id="adef2-160">You can perform updates, deletes, and inserts in the same batch operation.</span></span>
- <span data-ttu-id="adef2-161">批处理操作可包含最多 100 个实体。</span><span class="sxs-lookup"><span data-stu-id="adef2-161">A batch operation can include up to 100 entities.</span></span>
- <span data-ttu-id="adef2-162">批处理操作中的所有实体都必须都具有相同的分区键。</span><span class="sxs-lookup"><span data-stu-id="adef2-162">All entities in a batch operation must have the same partition key.</span></span>
- <span data-ttu-id="adef2-163">可以通过批处理操作中执行查询时，它必须是批处理中仅有的操作。</span><span class="sxs-lookup"><span data-stu-id="adef2-163">While it is possible to perform a query in a batch operation, it must be the only operation in the batch.</span></span>

<span data-ttu-id="adef2-164">下面是一些代码，将两个插入合并到批处理操作：</span><span class="sxs-lookup"><span data-stu-id="adef2-164">Here's some code that combines two inserts into a batch operation:</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L62-L71)]

## <a name="retrieve-all-entities-in-a-partition"></a><span data-ttu-id="adef2-165">检索分区中的所有实体</span><span class="sxs-lookup"><span data-stu-id="adef2-165">Retrieve all entities in a partition</span></span>

<span data-ttu-id="adef2-166">若要查询表以获取分区中的所有实体，使用`TableQuery`对象。</span><span class="sxs-lookup"><span data-stu-id="adef2-166">To query a table for all entities in a partition, use a `TableQuery` object.</span></span> <span data-ttu-id="adef2-167">在这里，你的筛选实体"Buster"所在的分区键。</span><span class="sxs-lookup"><span data-stu-id="adef2-167">Here, you filter for entities where "Buster" is the partition key.</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L77-L80)]

<span data-ttu-id="adef2-168">你现在打印结果：</span><span class="sxs-lookup"><span data-stu-id="adef2-168">You now print the results:</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L84-L85)]


## <a name="retrieve-a-range-of-entities-in-a-partition"></a><span data-ttu-id="adef2-169">检索分区中实体的一部分</span><span class="sxs-lookup"><span data-stu-id="adef2-169">Retrieve a range of entities in a partition</span></span>

<span data-ttu-id="adef2-170">如果你不想查询分区中的所有实体，你可以通过组合分区键筛选器与行键筛选器来指定一个范围。</span><span class="sxs-lookup"><span data-stu-id="adef2-170">If you don't want to query all the entities in a partition, you can specify a range by combining the partition key filter with a row key filter.</span></span> <span data-ttu-id="adef2-171">在这里，你使用两个筛选器来获取"Buster"分区的所有实体，行键 （名字） 以字母开头早于字母表中的"M"。</span><span class="sxs-lookup"><span data-stu-id="adef2-171">Here, you use two filters to get all entities in the "Buster" partition where the row key (first name) starts with a letter earlier than "M" in the alphabet.</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L91-L100)]

<span data-ttu-id="adef2-172">你现在打印结果：</span><span class="sxs-lookup"><span data-stu-id="adef2-172">You now print the results:</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L102-L103)]

## <a name="retrieve-a-single-entity"></a><span data-ttu-id="adef2-173">检索单个实体</span><span class="sxs-lookup"><span data-stu-id="adef2-173">Retrieve a single entity</span></span>

<span data-ttu-id="adef2-174">你可以编写查询以检索单个特定实体。</span><span class="sxs-lookup"><span data-stu-id="adef2-174">You can write a query to retrieve a single, specific entity.</span></span> <span data-ttu-id="adef2-175">在这里，使用`TableOperation`来指定客户"Larry Buster"。</span><span class="sxs-lookup"><span data-stu-id="adef2-175">Here, you use a `TableOperation` to specify the customer "Larry Buster".</span></span> <span data-ttu-id="adef2-176">而不是一个集合，则将取回`Customer`。</span><span class="sxs-lookup"><span data-stu-id="adef2-176">Instead of a collection, you get back a `Customer`.</span></span> <span data-ttu-id="adef2-177">在查询中指定分区键和行键是从表服务中检索单个实体的最快方法。</span><span class="sxs-lookup"><span data-stu-id="adef2-177">Specifying both the partition key and the row key in a query is the fastest way to retrieve a single entity from the Table service.</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L109-L111)]

<span data-ttu-id="adef2-178">你现在打印结果：</span><span class="sxs-lookup"><span data-stu-id="adef2-178">You now print the results:</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L113-L115)]


## <a name="replace-an-entity"></a><span data-ttu-id="adef2-179">替换实体</span><span class="sxs-lookup"><span data-stu-id="adef2-179">Replace an entity</span></span>

<span data-ttu-id="adef2-180">若要更新实体，从表服务中检索它，修改实体对象，然后将所做的更改保存回表服务使用`Replace`操作。</span><span class="sxs-lookup"><span data-stu-id="adef2-180">To update an entity, retrieve it from the Table service, modify the entity object, and then save the changes back to the Table service using a `Replace` operation.</span></span> <span data-ttu-id="adef2-181">这将导致在服务器上，将完全替换该实体，除非服务器上的该实体已更改自检索之后，在这种情况下，该操作将失败。</span><span class="sxs-lookup"><span data-stu-id="adef2-181">This causes the entity to be fully replaced on the server, unless the entity on the server has changed since it was retrieved, in which case the operation will fail.</span></span> <span data-ttu-id="adef2-182">此失败将防止你的应用程序无意中覆盖从其他源的更改。</span><span class="sxs-lookup"><span data-stu-id="adef2-182">This failure is to prevent your application from inadvertently overwriting changes from other sources.</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L121-L128)]

## <a name="insert-or-replace-an-entity"></a><span data-ttu-id="adef2-183">插入或替换实体</span><span class="sxs-lookup"><span data-stu-id="adef2-183">Insert-or-replace an entity</span></span>

<span data-ttu-id="adef2-184">有时，你不知道或不实体是否存在于表。</span><span class="sxs-lookup"><span data-stu-id="adef2-184">Sometimes, you don't know if the entity exists in the table or not.</span></span> <span data-ttu-id="adef2-185">并且如果是这样，不再需要存储在它的当前值。</span><span class="sxs-lookup"><span data-stu-id="adef2-185">And if it does, the current values stored in it are no longer needed.</span></span> <span data-ttu-id="adef2-186">你可以使用`InsertOrReplace`创建实体，或者将其替换如果它存在，而不考虑其状态。</span><span class="sxs-lookup"><span data-stu-id="adef2-186">You can use `InsertOrReplace` to create the entity, or replace it if it exists, regardless of its state.</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L134-L140)]

## <a name="query-a-subset-of-entity-properties"></a><span data-ttu-id="adef2-187">查询实体属性子集</span><span class="sxs-lookup"><span data-stu-id="adef2-187">Query a subset of entity properties</span></span>

<span data-ttu-id="adef2-188">表查询可以检索的几个属性，而不是所有这些实体中。</span><span class="sxs-lookup"><span data-stu-id="adef2-188">A table query can retrieve just a few properties from an entity instead of all of them.</span></span> <span data-ttu-id="adef2-189">此方法称为投影，可以提高查询性能，尤其适用于大型实体。</span><span class="sxs-lookup"><span data-stu-id="adef2-189">This technique, called projection, can improve query performance, especially for large entities.</span></span> <span data-ttu-id="adef2-190">在这里，你返回仅电子邮件地址使用`DynamicTableEntity`和`EntityResolver`。</span><span class="sxs-lookup"><span data-stu-id="adef2-190">Here, you return only email addresses using `DynamicTableEntity` and `EntityResolver`.</span></span> <span data-ttu-id="adef2-191">请注意，不支持投影在本地存储仿真程序，因此仅当你在上表服务使用的帐户时，在运行此代码。</span><span class="sxs-lookup"><span data-stu-id="adef2-191">Note that projection is not supported on the local storage emulator, so this code runs only when you're using an account on the Table service.</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L146-L157)]

## <a name="retrieve-entities-in-pages-asynchronously"></a><span data-ttu-id="adef2-192">以异步方式检索页中的实体</span><span class="sxs-lookup"><span data-stu-id="adef2-192">Retrieve entities in pages asynchronously</span></span>

<span data-ttu-id="adef2-193">如果您正在读取大量实体，并且你想要在检索，而不是等待其全部返回，可以使用分段的查询时进行处理。</span><span class="sxs-lookup"><span data-stu-id="adef2-193">If you are reading a large number of entities, and you want to process them as they are retrieved rather than waiting for them all to return, you can use a segmented query.</span></span> <span data-ttu-id="adef2-194">在这里，你结果在页中返回通过使用异步工作流，以便为大量要返回的结果在等待时，将不会阻止执行。</span><span class="sxs-lookup"><span data-stu-id="adef2-194">Here, you return results in pages by using an async workflow so that execution is not blocked while you're waiting for a large set of results to return.</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L163-L177)]

<span data-ttu-id="adef2-195">你现在以同步方式执行此计算：</span><span class="sxs-lookup"><span data-stu-id="adef2-195">You now execute this computation synchronously:</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L179-L179)]

## <a name="delete-an-entity"></a><span data-ttu-id="adef2-196">删除实体</span><span class="sxs-lookup"><span data-stu-id="adef2-196">Delete an entity</span></span>

<span data-ttu-id="adef2-197">你可以在检索后删除实体。</span><span class="sxs-lookup"><span data-stu-id="adef2-197">You can delete an entity after you have retrieved it.</span></span> <span data-ttu-id="adef2-198">使用更新实体，这将失败如果该实体自从你检索到它以后发生更改。</span><span class="sxs-lookup"><span data-stu-id="adef2-198">As with updating an entity, this will fail if the entity has changed since you retrieved it.</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L185-L186)]

## <a name="delete-a-table"></a><span data-ttu-id="adef2-199">删除表</span><span class="sxs-lookup"><span data-stu-id="adef2-199">Delete a table</span></span>

<span data-ttu-id="adef2-200">你可以从存储帐户中删除表。</span><span class="sxs-lookup"><span data-stu-id="adef2-200">You can delete a table from a storage account.</span></span> <span data-ttu-id="adef2-201">已删除的表将不可用的一段时间之后必须重新创建。</span><span class="sxs-lookup"><span data-stu-id="adef2-201">A table that has been deleted will be unavailable to be re-created for a period of time following the deletion.</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L192-L192)]

## <a name="next-steps"></a><span data-ttu-id="adef2-202">后续步骤</span><span class="sxs-lookup"><span data-stu-id="adef2-202">Next steps</span></span>

<span data-ttu-id="adef2-203">现在，你已了解表存储的基础知识，单击下面的链接以了解更复杂的存储任务：</span><span class="sxs-lookup"><span data-stu-id="adef2-203">Now that you've learned the basics of Table storage, follow these links to learn about more complex storage tasks:</span></span>

- [<span data-ttu-id="adef2-204">用于.NET 的 azure 存储 Api</span><span class="sxs-lookup"><span data-stu-id="adef2-204">Azure Storage APIs for .NET</span></span>](/dotnet/api/overview/azure/storage)
- [<span data-ttu-id="adef2-205">Azure 存储类型提供程序</span><span class="sxs-lookup"><span data-stu-id="adef2-205">Azure Storage Type Provider</span></span>](https://fsprojects.github.io/AzureStorageTypeProvider/)
- [<span data-ttu-id="adef2-206">Azure 存储团队博客</span><span class="sxs-lookup"><span data-stu-id="adef2-206">Azure Storage Team Blog</span></span>](https://blogs.msdn.microsoft.com/b/windowsazurestorage/)
- [<span data-ttu-id="adef2-207">配置 Azure 存储连接字符串</span><span class="sxs-lookup"><span data-stu-id="adef2-207">Configure Azure Storage connection strings</span></span>](/azure/storage/common/storage-configure-connection-string)
- [<span data-ttu-id="adef2-208">在.NET 的 Azure 表存储入门</span><span class="sxs-lookup"><span data-stu-id="adef2-208">Getting Started with Azure Table Storage in .NET</span></span>](https://azure.microsoft.com/documentation/samples/storage-table-dotnet-getting-started/)
