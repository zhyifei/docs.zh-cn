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
ms.openlocfilehash: e003f537c6f0f85b3b0ba932655ae2a54c980bc5
ms.sourcegitcommit: e2bf8e6bc365bd9a0e86fe81eeae7d14f85f48c1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/13/2018
---
# <a name="get-started-with-azure-table-storage-using-f"></a>要开始使用 Azure 表存储使用 F # #

Azure 表存储是将结构化的 NoSQL 数据存储在云中的服务。 表存储是具有无模式的设计的键/属性存储区。 表存储是无模式，因为它很容易使数据适应随着需求的应用程序发展变化。 对数据的访问是快速、 经济高效的所有类型的应用程序。 表存储是通常显著低于成本传统 SQL 相似的数据量。

你可以使用表存储来存储灵活的数据集，例如 web 应用程序、 通讯簿、 设备信息和的元数据，您的服务需要的任何其他类型的用户数据。 你可以在表中，存储任意数量的实体和存储帐户可以包含任意数量的表，直至达到存储帐户容量限制。

### <a name="about-this-tutorial"></a>关于本教程

本教程演示如何编写 F # 代码来执行一些常见的任务，使用 Azure 表存储，包括创建和删除表和插入、 更新、 删除和查询表数据。

有关表存储的概念概述，请参阅[表存储.NET 指南](/azure/storage/storage-dotnet-how-to-use-tables)

## <a name="prerequisites"></a>系统必备

若要使用本指南，你必须首先[创建 Azure 存储帐户](/azure/storage/storage-create-storage-account)。
此外需要为此帐户存储访问密钥。

## <a name="create-an-f-script-and-start-f-interactive"></a>创建的 F # 脚本并开始 F # 交互

这篇文章中的示例可在 F # 应用程序或 F # 脚本。 若要创建的 F # 脚本，创建具有的文件`.fsx`扩展，例如`tables.fsx`，F # 开发环境中。

接下来，使用[程序包管理器](package-management.md)如[Paket](https://fsprojects.github.io/Paket/)或[NuGet](https://www.nuget.org/)安装`WindowsAzure.Storage`包和引用`WindowsAzure.Storage.dll`在脚本中使用`#r`指令。 执行此再次为 Microsoft.WindowsAzure.ConfigurationManager 操作以获取 Microsoft.Azure 命名空间。

### <a name="add-namespace-declarations"></a>添加命名空间声明

添加以下`open`到顶部的语句`tables.fsx`文件：

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L1-L5)]

### <a name="get-your-connection-string"></a>获取连接字符串

对于本教程，你将需要一个 Azure 存储连接字符串。 有关连接字符串的详细信息，请参阅[配置存储连接字符串](/azure/storage/storage-configure-connection-string)。

对于本教程中，您将在脚本中，如下输入你的连接字符串：

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L11-L11)]

但是，这是**不建议**的实际项目。 你的存储帐户密钥是类似于你的存储帐户的根密码。 始终必须小心地保护你的存储帐户密钥。 避免将其分发给其他用户，硬编码，或将其保存在其他人可以访问的纯文本格式的文件。 你可以重新生成你使用 Azure 门户，如果你认为可能已泄露的密钥。

为实际的应用程序，维护存储连接字符串的最佳方法是在配置文件中。 若要从配置文件中提取的连接字符串，您可以执行此操作：

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L13-L15)]

使用 Azure 配置管理器是可选的。 你还可以使用 API，如.NET Framework 的`ConfigurationManager`类型。

### <a name="parse-the-connection-string"></a>分析连接字符串

若要分析的连接字符串，请使用：

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L21-L22)]

这将返回`CloudStorageAccount`。

### <a name="create-the-table-service-client"></a>创建表服务客户端

`CloudTableClient`类使你能够检索表和实体存储在表存储。 下面是创建服务客户端的一种方法：

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L28-L29)]

现在，你就可以编写代码，从读取数据并将数据写入表存储了。

## <a name="create-a-table"></a>创建表

此示例演示如何创建表，如果不存在：

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L35-L39)]

## <a name="add-an-entity-to-a-table"></a>向表中添加实体

实体必须具有从继承的类型`TableEntity`。 你可以扩展`TableEntity`中任何方式，但你类型*必须*具有无参数构造函数。 同时具有的属性`get`和`set`将存储在 Azure 表。

实体的分区键和行键唯一地标识表中的实体。 具有相同的分区键的实体的查询查询可以速度快于具有不同的分区键，但使用不同的分区键可实现的并行操作可伸缩性更好。

下面是一个示例的`Customer`使用`lastName`作为分区键和`firstName`作为行键。

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L45-L52)]

现在，我们将添加我们`Customer`到表。 若要执行此操作，你可以创建`TableOperation`，将在表上执行。 在这种情况下，创建`Insert`操作。

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L54-L55)]

## <a name="insert-a-batch-of-entities"></a>插入一批实体

你可以将一批实体插入表使用单个写入操作。 批处理操作允许您将操作合并为单个的执行，但它们具有一些限制：

- 你可以执行更新、 删除和插入相同的批处理操作中。
- 批处理操作可包含最多 100 个实体。
- 批处理操作中的所有实体都必须都具有相同的分区键。
- 可以通过批处理操作中执行查询时，它必须是批处理中仅有的操作。

下面是一些代码，将两个插入合并到批处理操作：

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L62-L71)]

## <a name="retrieve-all-entities-in-a-partition"></a>检索分区中的所有实体

若要查询表以获取分区中的所有实体，使用`TableQuery`对象。 在这里，你的筛选实体"Buster"所在的分区键。

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L77-L80)]

你现在打印结果：

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L84-L85)]


## <a name="retrieve-a-range-of-entities-in-a-partition"></a>检索分区中实体的一部分

如果你不想查询分区中的所有实体，你可以通过组合分区键筛选器与行键筛选器来指定一个范围。 在这里，你使用两个筛选器来获取"Buster"分区的所有实体，行键 （名字） 以字母开头早于字母表中的"M"。

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L91-L100)]

你现在打印结果：

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L102-L103)]

## <a name="retrieve-a-single-entity"></a>检索单个实体

你可以编写查询以检索单个特定实体。 在这里，使用`TableOperation`来指定客户"Larry Buster"。 而不是一个集合，则将取回`Customer`。 在查询中指定分区键和行键是从表服务中检索单个实体的最快方法。

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L109-L111)]

你现在打印结果：

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L113-L115)]


## <a name="replace-an-entity"></a>替换实体

若要更新实体，从表服务中检索它，修改实体对象，然后将所做的更改保存回表服务使用`Replace`操作。 这将导致在服务器上，将完全替换该实体，除非服务器上的该实体已更改自检索之后，在这种情况下，该操作将失败。 此失败将防止你的应用程序无意中覆盖从其他源的更改。

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L121-L128)]

## <a name="insert-or-replace-an-entity"></a>插入或替换实体

有时，你不知道或不实体是否存在于表。 并且如果是这样，不再需要存储在它的当前值。 你可以使用`InsertOrReplace`创建实体，或者将其替换如果它存在，而不考虑其状态。

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L134-L140)]

## <a name="query-a-subset-of-entity-properties"></a>查询实体属性子集

表查询可以检索的几个属性，而不是所有这些实体中。 此方法称为投影，可以提高查询性能，尤其适用于大型实体。 在这里，你返回仅电子邮件地址使用`DynamicTableEntity`和`EntityResolver`。 请注意，不支持投影在本地存储仿真程序，因此仅当你在上表服务使用的帐户时，在运行此代码。

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L146-L157)]

## <a name="retrieve-entities-in-pages-asynchronously"></a>以异步方式检索页中的实体

如果您正在读取大量实体，并且你想要在检索，而不是等待其全部返回，可以使用分段的查询时进行处理。 在这里，你结果在页中返回通过使用异步工作流，以便为大量要返回的结果在等待时，将不会阻止执行。

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L163-L177)]

你现在以同步方式执行此计算：

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L179-L179)]

## <a name="delete-an-entity"></a>删除实体

你可以在检索后删除实体。 使用更新实体，这将失败如果该实体自从你检索到它以后发生更改。

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L185-L186)]

## <a name="delete-a-table"></a>删除表

你可以从存储帐户中删除表。 已删除的表将不可用的一段时间之后必须重新创建。

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L192-L192)]

## <a name="next-steps"></a>后续步骤

现在，你已了解表存储的基础知识，单击下面的链接以了解更复杂的存储任务：

- [用于.NET 的 azure 存储 Api](/dotnet/api/overview/azure/storage)
- [Azure 存储类型提供程序](http://fsprojects.github.io/AzureStorageTypeProvider/)
- [Azure 存储团队博客](http://blogs.msdn.com/b/windowsazurestorage/)
- [配置 Azure 存储连接字符串](/azure/storage/common/storage-configure-connection-string)
- [在.NET 的 Azure 表存储入门](https://azure.microsoft.com/documentation/samples/storage-table-dotnet-getting-started/)
