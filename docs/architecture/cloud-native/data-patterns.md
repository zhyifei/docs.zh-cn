---
title: 云本机数据模式
description: 构建适用于 Azure 的云本机 .NET 应用 |云本机数据模式
ms.date: 06/30/2019
ms.openlocfilehash: 9e90409b0b633796b452cfcfecb3896e79002d4d
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/25/2019
ms.locfileid: "75337427"
---
# <a name="cloud-native-data-patterns"></a><span data-ttu-id="52a76-103">云本机数据模式</span><span class="sxs-lookup"><span data-stu-id="52a76-103">Cloud-native data patterns</span></span>

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

<span data-ttu-id="52a76-104">虽然分散的数据可能会提高性能、可伸缩性和节省成本，但它也带来了许多挑战。</span><span class="sxs-lookup"><span data-stu-id="52a76-104">While decentralized data can lead to improved performance, scalability, and cost savings, it also presents many challenges.</span></span> <span data-ttu-id="52a76-105">跨微服务查询数据非常复杂。</span><span class="sxs-lookup"><span data-stu-id="52a76-105">Querying for data across microservices is complex.</span></span> <span data-ttu-id="52a76-106">跨微服务的事务必须以编程方式进行管理，因为云本机应用程序中不支持分布式事务。</span><span class="sxs-lookup"><span data-stu-id="52a76-106">A transaction that spans microservices must be managed programmatically as distributed transactions aren't supported in cloud-native applications.</span></span> <span data-ttu-id="52a76-107">从一开始就是从*即时一致性*转变到*最终一致性*。</span><span class="sxs-lookup"><span data-stu-id="52a76-107">You  move from a world of *immediate consistency* to *eventual consistency*.</span></span>

<span data-ttu-id="52a76-108">现在我们讨论了这些难题。</span><span class="sxs-lookup"><span data-stu-id="52a76-108">We discuss these challenges now.</span></span>

## <a name="cross-service-queries"></a><span data-ttu-id="52a76-109">跨服务查询</span><span class="sxs-lookup"><span data-stu-id="52a76-109">Cross-service queries</span></span>

<span data-ttu-id="52a76-110">应用程序如何查询分散在多个独立微服务上的数据？</span><span class="sxs-lookup"><span data-stu-id="52a76-110">How does an application query data that is spread across many independent microservices?</span></span>

<span data-ttu-id="52a76-111">图5-4 显示了这种情况。</span><span class="sxs-lookup"><span data-stu-id="52a76-111">Figure 5-4 shows this scenario.</span></span>

![跨微服务进行查询](./media/cross-service-query.png)

<span data-ttu-id="52a76-113">**图 5-4**。</span><span class="sxs-lookup"><span data-stu-id="52a76-113">**Figure 5-4**.</span></span> <span data-ttu-id="52a76-114">跨微服务进行查询</span><span class="sxs-lookup"><span data-stu-id="52a76-114">Querying across microservices</span></span>

<span data-ttu-id="52a76-115">请注意，在上图中，如何查看购物篮微服务，将物品添加到用户的购物车。</span><span class="sxs-lookup"><span data-stu-id="52a76-115">Note how in the previous figure we see a shopping basket microservice that adds an item to a user's shopping cart.</span></span> <span data-ttu-id="52a76-116">尽管购物篮的数据存储包含购物篮和 lineItem 表，但它不包含产品或定价数据，因为在产品和价格微服务中找到这些项目。</span><span class="sxs-lookup"><span data-stu-id="52a76-116">While the shopping basket's data store contains a basket and lineItem table, it doesn't contain product or pricing data as those items are found in the product and price microservices.</span></span> <span data-ttu-id="52a76-117">若要添加项，购物篮微服务需要产品数据和定价数据。</span><span class="sxs-lookup"><span data-stu-id="52a76-117">To add an item, the shopping basket microservice needs product data and pricing data.</span></span> <span data-ttu-id="52a76-118">用于获取产品和定价数据的选项有哪些？</span><span class="sxs-lookup"><span data-stu-id="52a76-118">What are options to obtain the product and pricing data?</span></span>

<span data-ttu-id="52a76-119">图5-5 显示了微服务对产品目录和定价微服务进行直接 HTTP 调用的购物篮。</span><span class="sxs-lookup"><span data-stu-id="52a76-119">Figure 5-5 shows the shopping basket microservice making a direct HTTP call to both the product catalog and pricing microservices.</span></span>

![直接 http 通信](./media/direct-http-communication.png)

<span data-ttu-id="52a76-121">**图 5-5**。</span><span class="sxs-lookup"><span data-stu-id="52a76-121">**Figure 5-5**.</span></span> <span data-ttu-id="52a76-122">直接 HTTP 通信</span><span class="sxs-lookup"><span data-stu-id="52a76-122">Direct HTTP communication</span></span>

<span data-ttu-id="52a76-123">虽然实现可行，但在第4章介绍了如何在微服务中直接进行 HTTP 调用，而不是一种很好的做法。</span><span class="sxs-lookup"><span data-stu-id="52a76-123">While feasible to implement, in chapter 4 we discussed how direct HTTP calls across microservices couple the system and aren't considered a good practice.</span></span>

<span data-ttu-id="52a76-124">我们可以实现微服务图5-6 中所示的聚合器。</span><span class="sxs-lookup"><span data-stu-id="52a76-124">We could implement an aggregator microservice shown in Figure 5-6.</span></span>

![聚合微服务](./media/aggregator-microservice.png)

<span data-ttu-id="52a76-126">**如 5-6**。</span><span class="sxs-lookup"><span data-stu-id="52a76-126">**Figure 5-6.**</span></span> <span data-ttu-id="52a76-127">聚合微服务</span><span class="sxs-lookup"><span data-stu-id="52a76-127">Aggregator microservice</span></span>

<span data-ttu-id="52a76-128">虽然这种方法会在单独的微服务中封装业务操作工作流，但它增加了复杂性，但仍会导致直接 HTTP 调用。</span><span class="sxs-lookup"><span data-stu-id="52a76-128">While this approach encapsulates the business operation workflow in an individual microservice, it adds complexity and still results in direct HTTP calls.</span></span>

<span data-ttu-id="52a76-129">执行跨服务查询的常用方法是使用图5-7 中所示的[具体化视图模式](https://docs.microsoft.com/azure/architecture/patterns/materialized-view)。</span><span class="sxs-lookup"><span data-stu-id="52a76-129">A common approach for executing cross-service queries uses the [Materialized View Pattern](https://docs.microsoft.com/azure/architecture/patterns/materialized-view), shown in Figure 5-7.</span></span>

![具体化视图模式](./media/materialized-view-pattern.png)

<span data-ttu-id="52a76-131">**Figure5-7**。</span><span class="sxs-lookup"><span data-stu-id="52a76-131">**Figure5-7**.</span></span> <span data-ttu-id="52a76-132">具体化视图模式</span><span class="sxs-lookup"><span data-stu-id="52a76-132">Materialized View Pattern</span></span>

<span data-ttu-id="52a76-133">使用此模式，直接将本地表（称为 "*读取模型*"）放置在购物篮服务中，该服务包含产品和定价微服务所需的数据的非规范化副本。</span><span class="sxs-lookup"><span data-stu-id="52a76-133">With this pattern, you directly place a local table (known as a *read model*) in the shopping basket service that contains a denormalized copy of the data that is needed from the product and pricing microservices.</span></span> <span data-ttu-id="52a76-134">将这些数据放入购物篮微服务，无需调用昂贵的跨服务呼叫。</span><span class="sxs-lookup"><span data-stu-id="52a76-134">Placing that data inside the shopping basket microservice eliminates the need for invoking expensive cross-service calls.</span></span> <span data-ttu-id="52a76-135">利用服务的本地数据，可以提高响应时间和可靠性。</span><span class="sxs-lookup"><span data-stu-id="52a76-135">With the data local to the service, you improve response time and reliability.</span></span>

<span data-ttu-id="52a76-136">使用此方法时，有了系统中的重复数据。</span><span class="sxs-lookup"><span data-stu-id="52a76-136">The catch with this approach is you now have duplicate data in your system.</span></span> <span data-ttu-id="52a76-137">在云本机系统中，重复数据不会被视为[反模式](https://en.wikipedia.org/wiki/Anti-pattern)，并且通常在云本机系统中实现。</span><span class="sxs-lookup"><span data-stu-id="52a76-137">In cloud-native systems, duplicate data isn't considered an [anti-pattern](https://en.wikipedia.org/wiki/Anti-pattern) and is commonly implemented in cloud-native systems.</span></span> <span data-ttu-id="52a76-138">但是，其中一个系统可以是任何数据集的所有者，并且你需要为记录系统实现一种同步机制，以便在每次更改其基础数据时更新所有关联的读取模型。</span><span class="sxs-lookup"><span data-stu-id="52a76-138">However, one and only one system can be the owner of any dataset, and you'll need to implement a synchronization mechanism for the system of record to update all of the associated read models, whenever a change to its underlying data occurs.</span></span>

## <a name="transactional-support"></a><span data-ttu-id="52a76-139">事务支持</span><span class="sxs-lookup"><span data-stu-id="52a76-139">Transactional support</span></span>

<span data-ttu-id="52a76-140">尽管跨微服务的查询有挑战性，但跨微服务实现事务可能会很复杂。</span><span class="sxs-lookup"><span data-stu-id="52a76-140">While queries across microservices are challenging, implementing a transaction across microservices can be complex.</span></span> <span data-ttu-id="52a76-141">在驻留在不同微服务中的数据源之间维护数据一致性的固有挑战不能 understated。</span><span class="sxs-lookup"><span data-stu-id="52a76-141">The inherent challenge of maintaining data consistency across data sources that reside in different microservices can't be understated.</span></span> <span data-ttu-id="52a76-142">图5-8 显示了问题。</span><span class="sxs-lookup"><span data-stu-id="52a76-142">Figure 5-8 shows the problem.</span></span>

![Saga 模式中的事务](./media/saga-transaction-operation.png)

<span data-ttu-id="52a76-144">**图 5-8**。</span><span class="sxs-lookup"><span data-stu-id="52a76-144">**Figure 5-8**.</span></span> <span data-ttu-id="52a76-145">跨微服务实现事务</span><span class="sxs-lookup"><span data-stu-id="52a76-145">Implementing a transaction across microservices</span></span>

<span data-ttu-id="52a76-146">请注意上图中的第五个独立微服务如何参与分布式*创建订单*交易。</span><span class="sxs-lookup"><span data-stu-id="52a76-146">Note how in the previous figure five independent microservices all participate in a distributed *Create Order* transaction.</span></span> <span data-ttu-id="52a76-147">但是，五个单独微服务中的每一个都必须成功，否则必须中止并回滚操作。</span><span class="sxs-lookup"><span data-stu-id="52a76-147">However, the transaction for each of the five individual microservices must succeed, or all must abort and roll back the operation.</span></span> <span data-ttu-id="52a76-148">虽然内置事务支持在每个微服务中均可用，但不支持跨所有五项服务的分布式事务。</span><span class="sxs-lookup"><span data-stu-id="52a76-148">While built-in transactional support is available inside each of the microservices, there's no support for a distributed transaction across all five services.</span></span>

<span data-ttu-id="52a76-149">由于事务支持对于此操作至关重要，使每个微服务中的数据保持一致，因此必须以编程方式构造分布式事务。</span><span class="sxs-lookup"><span data-stu-id="52a76-149">Since transactional support is essential for this operation to keep the data consistent in each of the microservices, you have to programmatically construct a distributed transaction.</span></span>

<span data-ttu-id="52a76-150">以编程方式添加事务性支持的常见模式是[Saga 模式](https://blog.couchbase.com/saga-pattern-implement-business-transactions-using-microservices-part/)。</span><span class="sxs-lookup"><span data-stu-id="52a76-150">A popular pattern for programmatically adding transactional support is the [Saga pattern](https://blog.couchbase.com/saga-pattern-implement-business-transactions-using-microservices-part/).</span></span> <span data-ttu-id="52a76-151">这是通过将本地事务组合在一起并按顺序调用每个事务来实现的。</span><span class="sxs-lookup"><span data-stu-id="52a76-151">It's implemented by grouping local transactions together and sequentially invoking each one.</span></span> <span data-ttu-id="52a76-152">如果本地事务失败，Saga 将中止该操作，并调用一组[补偿事务](https://docs.microsoft.com/azure/architecture/patterns/compensating-transaction)来撤消前面的本地事务所做的更改。</span><span class="sxs-lookup"><span data-stu-id="52a76-152">If a local transaction fails, the Saga aborts the operation and invokes a set of [compensating transactions](https://docs.microsoft.com/azure/architecture/patterns/compensating-transaction) to undo the changes made by the preceding local transactions.</span></span> <span data-ttu-id="52a76-153">图5-9 显示了具有 Saga 模式的失败的事务。</span><span class="sxs-lookup"><span data-stu-id="52a76-153">Figure 5-9 shows a failed transaction with the Saga pattern.</span></span>

![在 saga 模式中回滚](./media/saga-rollback-operation.png)

<span data-ttu-id="52a76-155">**图 5-9**。</span><span class="sxs-lookup"><span data-stu-id="52a76-155">**Figure 5-9**.</span></span> <span data-ttu-id="52a76-156">回滚事务</span><span class="sxs-lookup"><span data-stu-id="52a76-156">Rolling back a transaction</span></span>

<span data-ttu-id="52a76-157">请注意上图中的如何*GenerateContent*操作在音乐微服务中失败。</span><span class="sxs-lookup"><span data-stu-id="52a76-157">Note how in the previous figure the *GenerateContent* operation has failed in the music microservice.</span></span> <span data-ttu-id="52a76-158">Saga 调用补偿事务（红色）以删除内容、取消付款并取消订单，并将每个微服务的数据返回到一致的状态。</span><span class="sxs-lookup"><span data-stu-id="52a76-158">The Saga invokes compensating transactions (in red) to remove the content, cancel the payment, and cancel the order, returning the data for each microservice back to a consistent state.</span></span>

<span data-ttu-id="52a76-159">Saga 模式通常编排为一系列相关事件，或作为一组相关命令进行协调。</span><span class="sxs-lookup"><span data-stu-id="52a76-159">Saga patterns are typically choreographed as a series of related events or orchestrated as a set of related commands.</span></span>

## <a name="cqrs-pattern"></a><span data-ttu-id="52a76-160">CQRS 模式</span><span class="sxs-lookup"><span data-stu-id="52a76-160">CQRS pattern</span></span>

<span data-ttu-id="52a76-161">CQRS 或[命令和查询责任分离](https://docs.microsoft.com/azure/architecture/patterns/cqrs)是一种体系结构模式，用于将读取数据的操作与写入数据的操作分离。</span><span class="sxs-lookup"><span data-stu-id="52a76-161">CQRS, or [Command and Query Responsibility Segregation](https://docs.microsoft.com/azure/architecture/patterns/cqrs), is an architectural pattern that separate operations that read data from those that write data.</span></span> <span data-ttu-id="52a76-162">此模式可帮助最大限度地提高性能、可伸缩性和安全性。</span><span class="sxs-lookup"><span data-stu-id="52a76-162">This pattern can help maximize performance, scalability, and security.</span></span>

<span data-ttu-id="52a76-163">在正常数据访问方案中，您实现了一个*同时*执行读写数据操作的单一模型（实体和存储库对象）。</span><span class="sxs-lookup"><span data-stu-id="52a76-163">In normal data access scenarios, you implement a single model (entity and repository object) that perform *both* read and write data operations.</span></span>

<span data-ttu-id="52a76-164">但是，更高级的数据访问方案可能会受益于用于读取和写入的单独的模型和数据表。</span><span class="sxs-lookup"><span data-stu-id="52a76-164">However, a more advanced data access scenario might benefit from separate models and data tables for reads and writes.</span></span> <span data-ttu-id="52a76-165">为了提高性能，读取操作（称为*查询*）可能会针对数据的高度非规范化表示，以避免重复的重复表联接。</span><span class="sxs-lookup"><span data-stu-id="52a76-165">To improve performance, the read operation, known as a *query*, might query against a highly denormalized representation of the data to avoid expensive repetitive table joins.</span></span> <span data-ttu-id="52a76-166">但*写入*操作（称为*命令*）可能会针对数据的完全标准化表示形式进行更新。</span><span class="sxs-lookup"><span data-stu-id="52a76-166">Whereas the *write* operation, known as a *command*, might update against a fully normalized representation of the data.</span></span> <span data-ttu-id="52a76-167">然后需要实现一种机制，使这两种表示形式保持同步。通常，只要修改写入表，就会引发将数据修改复制到读取表的事件。</span><span class="sxs-lookup"><span data-stu-id="52a76-167">You would then need to implement a mechanism to keep both representations in sync. Typically, whenever the write table is modified, it raises an event that replicates the data modification to the read table.</span></span>

<span data-ttu-id="52a76-168">图5-10 显示了 CQRS 模式的实现。</span><span class="sxs-lookup"><span data-stu-id="52a76-168">Figure 5-10 shows an implementation of the CQRS pattern.</span></span>

![CQRS 实现](./media/cqrs-implementation.png)

<span data-ttu-id="52a76-170">**图 5-10**。</span><span class="sxs-lookup"><span data-stu-id="52a76-170">**Figure 5-10**.</span></span> <span data-ttu-id="52a76-171">CQRS 实现</span><span class="sxs-lookup"><span data-stu-id="52a76-171">CQRS implementation</span></span>

<span data-ttu-id="52a76-172">请注意上图中如何实现不同的命令和查询模型。</span><span class="sxs-lookup"><span data-stu-id="52a76-172">Note how in the previous figure separate command and query models are implemented.</span></span> <span data-ttu-id="52a76-173">此外，每个数据写入操作都会保存到写入存储，然后传播到读取存储。</span><span class="sxs-lookup"><span data-stu-id="52a76-173">Moreover, each data write operation is saved to the write store and then propagated to the read store.</span></span> <span data-ttu-id="52a76-174">请密切注意传播过程如何按照[最终一致性](https://www.cloudcomputingpatterns.org/eventual_consistency/)原则操作，而读取模型最终与写入模型同步，但在此过程中可能会出现一些延迟。</span><span class="sxs-lookup"><span data-stu-id="52a76-174">Pay close attention to how the propagation process operates on the principle of [eventual consistency](https://www.cloudcomputingpatterns.org/eventual_consistency/), whereas the read model eventually synchronizes with the write model, but there may be some lag in the process.</span></span>

<span data-ttu-id="52a76-175">通过实现分离，可以单独缩放读取和写入。</span><span class="sxs-lookup"><span data-stu-id="52a76-175">By implementing separation, you have the ability to scale reads and writes separately.</span></span> <span data-ttu-id="52a76-176">同样，对写入操作的安全性可能比涉及读取操作的安全性更严格。</span><span class="sxs-lookup"><span data-stu-id="52a76-176">As well, you might impose tighter security on write operations than those concerning reads.</span></span>

<span data-ttu-id="52a76-177">通常，CQRS 模式根据特定需求应用于系统的有限部分。</span><span class="sxs-lookup"><span data-stu-id="52a76-177">Typically, CQRS patterns are applied to limited sections of your system based upon specific needs.</span></span>

## <a name="relational-vs-nosql"></a><span data-ttu-id="52a76-178">关系与 NoSQL</span><span class="sxs-lookup"><span data-stu-id="52a76-178">Relational vs NoSQL</span></span>

<span data-ttu-id="52a76-179">[NoSQL](https://www.geeksforgeeks.org/introduction-to-nosql/)技术的影响不能言过其实，尤其是对于分布式云本机系统。</span><span class="sxs-lookup"><span data-stu-id="52a76-179">The impact of [NoSQL](https://www.geeksforgeeks.org/introduction-to-nosql/) technologies can't be overstated, especially for distributed cloud-native systems.</span></span> <span data-ttu-id="52a76-180">这一领域新数据技术的激增导致了只依赖于关系数据库的解决方案。</span><span class="sxs-lookup"><span data-stu-id="52a76-180">The proliferation of new data technologies in this space has disrupted solutions that once exclusively relied on relational databases.</span></span>

<span data-ttu-id="52a76-181">另一方面，关系数据库是数十年的一项普遍技术。</span><span class="sxs-lookup"><span data-stu-id="52a76-181">On the one side, relational databases have been a prevalent technology for decades.</span></span> <span data-ttu-id="52a76-182">它们是成熟、经过验证且广泛实现的。</span><span class="sxs-lookup"><span data-stu-id="52a76-182">They're mature, proven, and widely implemented.</span></span> <span data-ttu-id="52a76-183">竞争的数据库产品、专业技能和工具 abounds。</span><span class="sxs-lookup"><span data-stu-id="52a76-183">Competing database products, expertise and tooling abounds.</span></span> <span data-ttu-id="52a76-184">关系数据库提供相关数据表的存储区。</span><span class="sxs-lookup"><span data-stu-id="52a76-184">Relational databases provide a store of related data tables.</span></span> <span data-ttu-id="52a76-185">这些表具有固定的架构，使用 SQL （结构化查询语言）来管理数据，并获得[ACID](https://www.geeksforgeeks.org/acid-properties-in-dbms/) （也称为原子性、一致性、隔离和持续性）。</span><span class="sxs-lookup"><span data-stu-id="52a76-185">These tables have a fixed schema, use SQL (Structured Query Language) to manage data and have [ACID](https://www.geeksforgeeks.org/acid-properties-in-dbms/) (also known as Atomicity, Consistency, Isolation, and Durability) guarantees.</span></span>

<span data-ttu-id="52a76-186">另一方面，非 SQL 数据库指的是高性能、非关系型数据存储。</span><span class="sxs-lookup"><span data-stu-id="52a76-186">No-SQL databases, on the other side, refer to high-performance, non-relational data stores.</span></span> <span data-ttu-id="52a76-187">它们采用易用性、可伸缩性、复原能力和可用性特征提供了方便。</span><span class="sxs-lookup"><span data-stu-id="52a76-187">They excel in their ease-of-use, scalability, resilience, and availability characteristics.</span></span> <span data-ttu-id="52a76-188">NoSQL 将自描述（无架构）数据通常存储在 JSON 文档中，而不是联接规范化数据的表。</span><span class="sxs-lookup"><span data-stu-id="52a76-188">Instead of joining tables of normalized data, NoSQL stores self-describing (schemaless) data typically in JSON documents.</span></span> <span data-ttu-id="52a76-189">它们不提供[ACID](https://www.geeksforgeeks.org/acid-properties-in-dbms/)保证。</span><span class="sxs-lookup"><span data-stu-id="52a76-189">They don't offer [ACID](https://www.geeksforgeeks.org/acid-properties-in-dbms/) guarantees.</span></span>

<span data-ttu-id="52a76-190">要了解这两种类型的数据库之间的差异，可以参阅[CAP 定理](https://towardsdatascience.com/cap-theorem-and-distributed-database-management-systems-5c2be977950e)（一组可应用于存储状态的分布式系统的原则）。</span><span class="sxs-lookup"><span data-stu-id="52a76-190">A way to understand the differences between these types of databases can be found in the [CAP theorem](https://towardsdatascience.com/cap-theorem-and-distributed-database-management-systems-5c2be977950e), a set of principles that can be applied to distributed systems that store state.</span></span> <span data-ttu-id="52a76-191">图5-11 显示了 CAP 定理的三个属性。</span><span class="sxs-lookup"><span data-stu-id="52a76-191">Figure 5-11 shows the three properties of the CAP theorem.</span></span>

![CAP 定理](./media/cap-theorem.png)

<span data-ttu-id="52a76-193">**图 5-11**。</span><span class="sxs-lookup"><span data-stu-id="52a76-193">**Figure 5-11**.</span></span> <span data-ttu-id="52a76-194">CAP 定理</span><span class="sxs-lookup"><span data-stu-id="52a76-194">The CAP theorem</span></span>

<span data-ttu-id="52a76-195">定理指出，任何分布式数据系统都将在一致性、可用性和分区容差之间提供折衷，并且任何数据库只能保证三个属性中的两个：</span><span class="sxs-lookup"><span data-stu-id="52a76-195">The theorem states that any distributed data system will offer a trade-off between consistency, availability, and partition tolerance, and that any database can only guarantee two of the three properties:</span></span>

- <span data-ttu-id="52a76-196">*一致性*：群集中的每个节点都将使用最新的数据做出响应，即使它需要阻塞请求，直到所有副本都得到正确更新。</span><span class="sxs-lookup"><span data-stu-id="52a76-196">*Consistency*: every node in the cluster will respond with the most recent data, even if it requires blocking a request until all replicas are correctly updated.</span></span>

- <span data-ttu-id="52a76-197">*可用性*：每个节点都将在合理的时间内返回响应，即使该响应不是最新的数据也是如此。</span><span class="sxs-lookup"><span data-stu-id="52a76-197">*Availability*: every node will return a response in a reasonable amount of time, even if that response isn't the most recent data.</span></span>

- <span data-ttu-id="52a76-198">*分区容差*：保证当某个节点出现故障或失去与其他节点的连接时，系统将继续运行。</span><span class="sxs-lookup"><span data-stu-id="52a76-198">*Partition Tolerance*: guarantees that the system will continue operating if a node fails or loses connectivity with another.</span></span>

<span data-ttu-id="52a76-199">关系数据库显示一致性和可用性，但不提供分区容差。</span><span class="sxs-lookup"><span data-stu-id="52a76-199">Relational databases exhibit consistency and availability, but not partition tolerance.</span></span> <span data-ttu-id="52a76-200">分区关系数据库（如分片）非常困难，可能会影响性能。</span><span class="sxs-lookup"><span data-stu-id="52a76-200">Partitioning a relational database, such as sharding, is difficult and can impact performance.</span></span>

<span data-ttu-id="52a76-201">另一方面，NoSQL 数据库通常会表现出分区容差（称为水平可伸缩性和高可用性）。</span><span class="sxs-lookup"><span data-stu-id="52a76-201">On the other hand, NoSQL databases typically exhibit partition tolerance, known as horizontal scalability, and high availability.</span></span> <span data-ttu-id="52a76-202">作为 CAP 定理指定，您只能有这三个原则中的两个，而您会丢失一致性属性。</span><span class="sxs-lookup"><span data-stu-id="52a76-202">As the CAP theorem specifies, you can only have two of the three principles, and you lose the  consistency property.</span></span>

<span data-ttu-id="52a76-203">NoSQL 数据库在商用服务器之间进行分发和一般横向扩展。</span><span class="sxs-lookup"><span data-stu-id="52a76-203">NoSQL databases are distributed and commonly scaled out across commodity servers.</span></span> <span data-ttu-id="52a76-204">这样做可以在地理区域内和跨地理区域提供高可用性，同时降低成本。</span><span class="sxs-lookup"><span data-stu-id="52a76-204">Doing so can provide great availability, both within and across geographical regions at a reduced cost.</span></span> <span data-ttu-id="52a76-205">可以在这些计算机或节点上对数据进行分区和复制，从而提供冗余和容错能力。</span><span class="sxs-lookup"><span data-stu-id="52a76-205">Data can be partitioned and replicated across these machines, or nodes, providing redundancy and fault tolerance.</span></span> <span data-ttu-id="52a76-206">缺点是一致性。</span><span class="sxs-lookup"><span data-stu-id="52a76-206">The downside is consistency.</span></span> <span data-ttu-id="52a76-207">对一个 NoSQL 节点上的数据所做的更改可能需要一段时间才能传播到其他节点。</span><span class="sxs-lookup"><span data-stu-id="52a76-207">A change to data on one NoSQL node can take some time to propagate to other nodes.</span></span> <span data-ttu-id="52a76-208">通常，NoSQL 数据库节点会立即响应查询，即使正在呈现的数据已过时，并且尚未更新。</span><span class="sxs-lookup"><span data-stu-id="52a76-208">Typically, a NoSQL database node will provide an immediate response to a query, even if the data that it is presenting is stale and has not been updated yet.</span></span>

<span data-ttu-id="52a76-209">这是已知的[最终一致性](https://www.cloudcomputingpatterns.org/eventual_consistency/)，即不支持 ACID 事务的分布式数据系统的特征。</span><span class="sxs-lookup"><span data-stu-id="52a76-209">This is known [eventual consistency](https://www.cloudcomputingpatterns.org/eventual_consistency/), a characteristic of distributed data systems where ACID transactions aren't supported.</span></span> <span data-ttu-id="52a76-210">在更新数据项目和将更新传播到每个副本节点所用的时间之间，会有短暂的延迟。</span><span class="sxs-lookup"><span data-stu-id="52a76-210">It's a brief delay between the update of a data item and time that it takes to propagate that update to each of the replica nodes.</span></span> <span data-ttu-id="52a76-211">如果在美国中更新 NoSQL 数据库中的产品项，但同时从欧洲的副本节点中查询同一数据项，则可以检索先前的产品信息-直到欧盟节点更新了产品更改。</span><span class="sxs-lookup"><span data-stu-id="52a76-211">If you update a product item in a NoSQL database in the United States, but at same time query that same data item from a replica node in Europe, you might retrieve the earlier product information - until the European node has been updated with product change.</span></span> <span data-ttu-id="52a76-212">权衡是指在返回查询结果[之前，要](https://en.wikipedia.org/wiki/Strong_consistency)等待所有副本节点进行更新，而不是在返回查询结果之前，您可以支持巨大的规模和流量，但可能会显示较旧的数据。</span><span class="sxs-lookup"><span data-stu-id="52a76-212">The trade-off is that by giving up [strong consistency](https://en.wikipedia.org/wiki/Strong_consistency),  waiting for all replica nodes to update before returning a query result, you can support enormous scale and traffic volume, but with the possibility of presenting older data.</span></span>

<span data-ttu-id="52a76-213">可以通过以下四个模型对 NoSQL 数据库进行分类：</span><span class="sxs-lookup"><span data-stu-id="52a76-213">NoSQL databases can be categorized by the following four models:</span></span>

- <span data-ttu-id="52a76-214">*文档存储区*（MongoDB、CouchDB、Couchbase）：数据（以及相应的元数据）在数据库中的基于非标准化 JSON 的文档中存储为非 relationally。</span><span class="sxs-lookup"><span data-stu-id="52a76-214">*Document Store* (MongoDB, CouchDB, Couchbase): data (and corresponding metadata) is stored non-relationally in denormalized JSON-based documents inside the database.</span></span>

- <span data-ttu-id="52a76-215">*键/值存储区*（Redis、Riak、memcached）：在简单的键值对中存储数据，这些键值对映射到用户数据值的唯一访问键执行系统操作。</span><span class="sxs-lookup"><span data-stu-id="52a76-215">*Key/Value Store* (Redis, Riak, memcached): data is stored in simple key-value pairs with system operations performed against a unique access key that is mapped to a value of user data.</span></span>

- <span data-ttu-id="52a76-216">*宽列存储*（HBase，Cassandra）：相关数据以纵栏式格式存储在单个列中，并以一组嵌套键/值对的形式存储在单个列中，数据通常以单个单元的形式进行检索，而不必将多个表联接在一起。</span><span class="sxs-lookup"><span data-stu-id="52a76-216">*Wide-Column Store* (HBase, Cassandra): related Data is stored in a columnar format as a set of nested-key/value pairs within a single column with data typically retrieved as a single unit without having to join multiple tables together.</span></span>

- <span data-ttu-id="52a76-217">*Graph 商店*（neo4j，titan）：数据存储为一个节点内的图形表示形式以及指定节点之间的关系的边缘。</span><span class="sxs-lookup"><span data-stu-id="52a76-217">*Graph stores* (neo4j, titan): data is stored as a graphical representation within a node along with edges that specify the relationship between the nodes.</span></span>

<span data-ttu-id="52a76-218">可以优化 NoSQL 数据库来处理大规模数据，尤其是在数据相对简单时。</span><span class="sxs-lookup"><span data-stu-id="52a76-218">NoSQL databases can be optimized to deal with large-scale data, especially when the data is relatively simple.</span></span> <span data-ttu-id="52a76-219">在以下情况时，请考虑 NoSQL 数据库：</span><span class="sxs-lookup"><span data-stu-id="52a76-219">Consider a NoSQL database when:</span></span>

- <span data-ttu-id="52a76-220">工作负荷需要大规模和高并发性。</span><span class="sxs-lookup"><span data-stu-id="52a76-220">Your workload requires a large scale and high concurrency.</span></span>
- <span data-ttu-id="52a76-221">用户数很多。</span><span class="sxs-lookup"><span data-stu-id="52a76-221">You have large numbers of users.</span></span>
- <span data-ttu-id="52a76-222">您的数据可以简单地表示而不是关系。</span><span class="sxs-lookup"><span data-stu-id="52a76-222">Your data can be expressed simply without relationships.</span></span>
- <span data-ttu-id="52a76-223">需要将数据分散到不同的位置。</span><span class="sxs-lookup"><span data-stu-id="52a76-223">You need to geographically distribute your data.</span></span>
- <span data-ttu-id="52a76-224">不需要 ACID 保证。</span><span class="sxs-lookup"><span data-stu-id="52a76-224">You don't need ACID guarantees.</span></span>
- <span data-ttu-id="52a76-225">将部署到商用硬件。</span><span class="sxs-lookup"><span data-stu-id="52a76-225">Will be deployed to commodity hardware.</span></span>

<span data-ttu-id="52a76-226">然后，在以下情况下考虑关系数据库：</span><span class="sxs-lookup"><span data-stu-id="52a76-226">Then, consider a relational database when:</span></span>

- <span data-ttu-id="52a76-227">你的工作负载需要大中型。</span><span class="sxs-lookup"><span data-stu-id="52a76-227">Your workloads require medium to large scale.</span></span>
- <span data-ttu-id="52a76-228">并发不是主要考虑因素。</span><span class="sxs-lookup"><span data-stu-id="52a76-228">Concurrency isn't a major concern.</span></span>
- <span data-ttu-id="52a76-229">需要 ACID 保证。</span><span class="sxs-lookup"><span data-stu-id="52a76-229">ACID guarantees are needed.</span></span>
- <span data-ttu-id="52a76-230">数据是最 relationally 的。</span><span class="sxs-lookup"><span data-stu-id="52a76-230">Data is best expressed relationally.</span></span>
- <span data-ttu-id="52a76-231">你的应用程序将部署到大型高端硬件。</span><span class="sxs-lookup"><span data-stu-id="52a76-231">Your application will be deployed to large, high-end hardware.</span></span>

<span data-ttu-id="52a76-232">接下来，我们来看看 Azure 云中的数据存储。</span><span class="sxs-lookup"><span data-stu-id="52a76-232">Next, we look at data storage in the Azure cloud.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="52a76-233">[上一页](distributed-data.md)
>[下一页](azure-data-storage.md)</span><span class="sxs-lookup"><span data-stu-id="52a76-233">[Previous](distributed-data.md)
[Next](azure-data-storage.md)</span></span>
