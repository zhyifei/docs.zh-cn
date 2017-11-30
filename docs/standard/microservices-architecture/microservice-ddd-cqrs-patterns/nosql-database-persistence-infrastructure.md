---
title: "作为持久性基础结构使用 NoSQL 数据库"
description: "为容器化的.NET 应用程序的.NET 微服务体系结构 |作为持久性基础结构使用 NoSQL 数据库"
keywords: "Docker, 微服务, ASP.NET, 容器"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: e4b63511069b89cc5761ce7ed64f09e9035a56a3
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/22/2017
---
# <a name="using-nosql-databases-as-a-persistence-infrastructure"></a><span data-ttu-id="d4609-104">作为持久性基础结构使用 NoSQL 数据库</span><span class="sxs-lookup"><span data-stu-id="d4609-104">Using NoSQL databases as a persistence infrastructure</span></span>

<span data-ttu-id="d4609-105">当你为你基础结构的数据层使用 NoSQL 数据库时，通常不使用实体框架核心如 ORM。</span><span class="sxs-lookup"><span data-stu-id="d4609-105">When you use NoSQL databases for your infrastructure data tier, you typically do not use an ORM like Entity Framework Core.</span></span> <span data-ttu-id="d4609-106">相反，你使用 NoSQL 引擎，如 Azure Cosmos DB、 MongoDB、 Cassandra、 RavenDB、 CouchDB 或 Azure 存储表提供的 API。</span><span class="sxs-lookup"><span data-stu-id="d4609-106">Instead you use the API provided by the NoSQL engine, such as Azure Cosmos DB, MongoDB, Cassandra, RavenDB, CouchDB, or Azure Storage Tables.</span></span>

<span data-ttu-id="d4609-107">但是，当使用 NoSQL 数据库，尤其是面向文档数据库 Azure Cosmos DB、 CouchDB 或 RavenDB，如设计 DDD 聚合与模型的方式是部分类似于如何你可以执行此操作在 EF 核，关于的标识聚合根、 子实体类和值对象类。</span><span class="sxs-lookup"><span data-stu-id="d4609-107">However, when you use a NoSQL database, especially a document-oriented database like Azure Cosmos DB, CouchDB, or RavenDB, the way you design your model with DDD aggregates is partially similar to how you can do it in EF Core, in regards to the identification of aggregate roots, child entity classes, and value object classes.</span></span> <span data-ttu-id="d4609-108">但是，从根本上讲，数据库选择将影响你的设计中。</span><span class="sxs-lookup"><span data-stu-id="d4609-108">But, ultimately, the database selection will impact in your design.</span></span>

<span data-ttu-id="d4609-109">当使用面向文档的数据库时，你可以作为单个文档，在 JSON 或另一种格式中序列化实现聚合。</span><span class="sxs-lookup"><span data-stu-id="d4609-109">When you use a document-oriented database, you implement an aggregate as a single document, serialized in JSON or another format.</span></span> <span data-ttu-id="d4609-110">但是，使用数据库是从域模型代码角度来看透明的。</span><span class="sxs-lookup"><span data-stu-id="d4609-110">However, the use of the database is transparent from a domain model code point of view.</span></span> <span data-ttu-id="d4609-111">使用一种 NoSQL 数据库，你仍会使用实体类和聚合根类，但它具有更大的灵活性比时使用 EF 核心，因为持久性不是关系。</span><span class="sxs-lookup"><span data-stu-id="d4609-111">When using a NoSQL database, you still are using entity classes and aggregate root classes, but with more flexibility than when using EF Core because the persistence is not relational.</span></span>

<span data-ttu-id="d4609-112">区别在于如何存留该模型。</span><span class="sxs-lookup"><span data-stu-id="d4609-112">The difference is in how you persist that model.</span></span> <span data-ttu-id="d4609-113">如果你实施您基于 POCO 实体类的域模型，不可知的基础结构持久性，可能看起来像可以将移到不同的持久性基础结构，甚至从 NoSQL 到关系。</span><span class="sxs-lookup"><span data-stu-id="d4609-113">If you implemented your domain model based on POCO entity classes, agnostic to the infrastructure persistence, it might look like you could move to a different persistence infrastructure, even from relational to NoSQL.</span></span> <span data-ttu-id="d4609-114">但是，这应该不是你的目标。</span><span class="sxs-lookup"><span data-stu-id="d4609-114">However, that should not be your goal.</span></span> <span data-ttu-id="d4609-115">始终有不同的数据库中的约束将抵制你，因此你将不能具有相同的模型的关系或 NoSQL 数据库。</span><span class="sxs-lookup"><span data-stu-id="d4609-115">There are always constraints in the different databases will push you back, so you will not be able to have the same model for relational or NoSQL databases.</span></span> <span data-ttu-id="d4609-116">更改持久性模型并不是重要的因为事务和持久性操作将大不相同。</span><span class="sxs-lookup"><span data-stu-id="d4609-116">Changing persistence models would not be trivial, because transactions and persistence operations will be very different.</span></span>

<span data-ttu-id="d4609-117">例如，在面向文档的数据库中，是可以聚合根具有子集合的多个属性。</span><span class="sxs-lookup"><span data-stu-id="d4609-117">For example, in a document-oriented database, it is okay for an aggregate root to have multiple child collection properties.</span></span> <span data-ttu-id="d4609-118">在关系数据库中，查询多个子集合属性是很多次的因为你将联合的所有 SQL 语句取回从 EF。</span><span class="sxs-lookup"><span data-stu-id="d4609-118">In a relational database, querying multiple child collection properties is awful, because you get a UNION ALL SQL statement back from EF.</span></span> <span data-ttu-id="d4609-119">具有相同的域模型关系数据库或 NoSQL 数据库并不那么简单，并且您不应尝试它。</span><span class="sxs-lookup"><span data-stu-id="d4609-119">Having the same domain model for relational databases or NoSQL databases is not simple, and you should not try it.</span></span> <span data-ttu-id="d4609-120">您实际需要设计您了解如何将数据用于在每个特定数据库的模型。</span><span class="sxs-lookup"><span data-stu-id="d4609-120">You really have to design your model with an understanding of how the data is going to be used in each particular database.</span></span>

<span data-ttu-id="d4609-121">使用 NoSQL 数据库时的一项优势是实体属于多非规范化，因此你未设置的表映射。</span><span class="sxs-lookup"><span data-stu-id="d4609-121">A benefit when using NoSQL databases is that the entities are more denormalized, so you do not set a table mapping.</span></span> <span data-ttu-id="d4609-122">您的域模型可以是比时使用关系数据库更灵活。</span><span class="sxs-lookup"><span data-stu-id="d4609-122">Your domain model can be more flexible than when using a relational database.</span></span>

<span data-ttu-id="d4609-123">当设计您的域模型基于聚合，将移动到 NoSQL 和面向文档的数据库可能比使用关系数据库中，更轻松，因为你设计聚合是类似于序列化面向文档的数据库中的文档。</span><span class="sxs-lookup"><span data-stu-id="d4609-123">When you design your domain model based on aggregates, moving to NoSQL and document-oriented databases might be even easier than using a relational database, because the aggregates you design are similar to serialized documents in a document-oriented database.</span></span> <span data-ttu-id="d4609-124">然后您可以在包含这些"包"对于该聚合可能需要的所有信息。</span><span class="sxs-lookup"><span data-stu-id="d4609-124">Then you can include in those “bags” all the information you might need for that aggregate.</span></span>

<span data-ttu-id="d4609-125">例如，下面的 JSON 代码时的顺序聚合示例实现使用面向文档的数据库。</span><span class="sxs-lookup"><span data-stu-id="d4609-125">For instance, the following JSON code is a sample implementation of an order aggregate when using a document-oriented database.</span></span> <span data-ttu-id="d4609-126">它等同于我们实现在 eShopOnContainers 示例中，但没有使用下方的 EF 核心顺序聚合。</span><span class="sxs-lookup"><span data-stu-id="d4609-126">It is similar to the order aggregate we implemented in the eShopOnContainers sample, but without using EF Core underneath.</span></span>

```json
{
    "id": "2017001",
    "orderDate": "2/25/2017",
    "buyerId": "1234567",
    "address": [
        {
        "street": "100 One Microsoft Way",
        "city": "Redmond",
        "state": "WA",
        "zip": "98052",
        "country": "U.S."
        }
    ],
    "orderItems": [
        {"id": 20170011, "productId": "123456", "productName": ".NET T-Shirt",
        "unitPrice": 25, "units": 2, "discount": 0},
        {"id": 20170012, "productId": "123457", "productName": ".NET Mug",
        "unitPrice": 15, "units": 1, "discount": 0}
    ]
}
```

<span data-ttu-id="d4609-127">当你使用 C\#实现聚合以供 Azure Cosmos DB SDK，聚合类似的模型是类似于 C\# POCO 类与 EF 核心一起使用。</span><span class="sxs-lookup"><span data-stu-id="d4609-127">When you use a C\# model to implement the aggregate to be used by something like the Azure Cosmos DB SDK, the aggregate is similar to the C\# POCO classes used with EF Core.</span></span> <span data-ttu-id="d4609-128">区别在于它们使用从应用程序和基础结构层，如以下代码所示的方式：</span><span class="sxs-lookup"><span data-stu-id="d4609-128">The difference is in the way to use them from the application and infrastructure layers, as in the following code:</span></span>

```csharp
// C# EXAMPLE OF AN ORDER AGGREGATE BEING PERSISTED WITH DOCUMENTDB API
// *** Domain Model Code ***
// Aggregate: Create an Order object with its child entities and/or value objects.
// Then, use AggregateRoot’s methods to add the nested objects so invariants and
// logic is consistent across the nested properties (value objects and entities).
// This can be saved as JSON as is without converting into rows/columns.
Order orderAggregate = new Order
{
    Id = "2017001",
    OrderDate = new DateTime(2005, 7, 1),
    BuyerId = "1234567",
    PurchaseOrderNumber = "PO18009186470"
}

Address address = new Address
{
    Street = "100 One Microsoft Way",
    City = "Redmond",
    State = "WA",
    Zip = "98052",
    Country = "U.S."
}

orderAggregate.UpdateAddress(address);
OrderItem orderItem1 = new OrderItem
{
    Id = 20170011,
    ProductId = "123456",
    ProductName = ".NET T-Shirt",
    UnitPrice = 25,
    Units = 2,
    Discount = 0;
};

OrderItem orderItem2 = new OrderItem
{
    Id = 20170012,
    ProductId = "123457",
    ProductName = ".NET Mug",
    UnitPrice = 15,
    Units = 1,
    Discount = 0;
};

//Using methods with domain logic within the entity. No anemic-domain model
orderAggregate.AddOrderItem(orderItem1);
orderAggregate.AddOrderItem(orderItem2);

// *** End of Domain Model Code ***
//...
// *** Infrastructure Code using Cosmos DB Client API ***
Uri collectionUri = UriFactory.CreateDocumentCollectionUri(databaseName,
    collectionName);

await client.CreateDocumentAsync(collectionUri, order);

// As your app evolves, let's say your object has a new schema. You can insert
// OrderV2 objects without any changes to the database tier.
Order2 newOrder = GetOrderV2Sample("IdForSalesOrder2");
await client.CreateDocumentAsync(collectionUri, newOrder);
```

<span data-ttu-id="d4609-129">你可以看到您与您的域模型的工作方式可以是你时使用它在你的域模型层中的基础结构是 EF 工作方式相似。</span><span class="sxs-lookup"><span data-stu-id="d4609-129">You can see that the way you work with your domain model can be similar to the way you use it in your domain model layer when the infrastructure is EF.</span></span> <span data-ttu-id="d4609-130">你仍然使用相同的聚合根方法确保一致性，固定协定，并且在聚合中的验证。</span><span class="sxs-lookup"><span data-stu-id="d4609-130">You still use the same aggregate root methods to ensure consistency, invariants, and validations within the aggregate.</span></span>

<span data-ttu-id="d4609-131">但是，当您保留您的模型到 NoSQL 数据库、 代码和显著相比 EF 核心代码的 API 更改或与关系数据库相关的任何其他代码。</span><span class="sxs-lookup"><span data-stu-id="d4609-131">However, when you persist your model into the NoSQL database, the code and API change dramatically compared to EF Core code or any other code related to relational databases.</span></span>

#### <a name="additional-resources"></a><span data-ttu-id="d4609-132">其他资源</span><span class="sxs-lookup"><span data-stu-id="d4609-132">Additional resources</span></span>

-   <span data-ttu-id="d4609-133">**对 DocumentDB 中的数据进行建模**
    [*https://docs.microsoft.com/azure/documentdb/documentdb-modeling-data*](https://docs.microsoft.com/azure/documentdb/documentdb-modeling-data)</span><span class="sxs-lookup"><span data-stu-id="d4609-133">**Modeling data in DocumentDB**
[*https://docs.microsoft.com/azure/documentdb/documentdb-modeling-data*](https://docs.microsoft.com/azure/documentdb/documentdb-modeling-data)</span></span>

-   <span data-ttu-id="d4609-134">**Vaughn Vernon。理想域驱动设计聚合应用商店？** 
     [ *https://vaughnvernon.co/?p=942*](https://vaughnvernon.co/?p=942)</span><span class="sxs-lookup"><span data-stu-id="d4609-134">**Vaughn Vernon. The Ideal Domain-Driven Design Aggregate Store?**
[*https://vaughnvernon.co/?p=942*](https://vaughnvernon.co/?p=942)</span></span>

-   <span data-ttu-id="d4609-135">**持久性未知事件适用于.NET 的存储区。**</span><span class="sxs-lookup"><span data-stu-id="d4609-135">**A persistence agnostic Event Store for .NET.**</span></span> <span data-ttu-id="d4609-136">GitHub 存储库。</span><span class="sxs-lookup"><span data-stu-id="d4609-136">GitHub repo.</span></span>
    [<span data-ttu-id="d4609-137">*https://github.com/NEventStore/NEventStore*</span><span class="sxs-lookup"><span data-stu-id="d4609-137">*https://github.com/NEventStore/NEventStore*</span></span>](https://github.com/NEventStore/NEventStore)


>[!div class="step-by-step"]
<span data-ttu-id="d4609-138">[以前](infrastructure-persistence-layer-implemenation-entity-framework-core.md) [下一步] (microservice-application-layer-web-api-design.md)</span><span class="sxs-lookup"><span data-stu-id="d4609-138">[Previous] (infrastructure-persistence-layer-implemenation-entity-framework-core.md) [Next] (microservice-application-layer-web-api-design.md)</span></span>
