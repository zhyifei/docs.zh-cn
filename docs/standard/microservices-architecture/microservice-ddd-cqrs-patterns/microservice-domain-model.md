---
title: 设计微服务域模型
description: 适用于容器化 .NET 应用程序的 .NET 微服务体系结构 | 设计微服务域模型
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 11/09/2017
ms.openlocfilehash: 2776412b96d4ed141f48814d19d2deaa1a71520d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33579452"
---
# <a name="designing-a-microservice-domain-model"></a><span data-ttu-id="bd764-103">设计微服务域模型</span><span class="sxs-lookup"><span data-stu-id="bd764-103">Designing a microservice domain model</span></span>

<span data-ttu-id="bd764-104">*为每个业务微服务或绑定上下文定义一个丰富域模型*</span><span class="sxs-lookup"><span data-stu-id="bd764-104">*Define one rich domain model for each business microservice or Bounded Context*</span></span>

<span data-ttu-id="bd764-105">你的目标是为每个业务微服务或绑定上下文 (BC) 创建一个内聚域模型。</span><span class="sxs-lookup"><span data-stu-id="bd764-105">Your goal is to create a single cohesive domain model for each business microservice or Bounded Context (BC).</span></span> <span data-ttu-id="bd764-106">但请记住，BC 或业务微服务有时可能由共享一个域模型的多个物理服务组成。</span><span class="sxs-lookup"><span data-stu-id="bd764-106">Keep in mind, however, that a BC or business microservice could sometimes be composed of several physical services that share a single domain model.</span></span> <span data-ttu-id="bd764-107">域模型必须捕获它所代表的单个绑定上下文或业务微服务的规则、行为、业务语言和约束。</span><span class="sxs-lookup"><span data-stu-id="bd764-107">The domain model must capture the rules, behavior, business language, and constraints of the single Bounded Context or business microservice that it represents.</span></span>

## <a name="the-domain-entity-pattern"></a><span data-ttu-id="bd764-108">域实体模式</span><span class="sxs-lookup"><span data-stu-id="bd764-108">The Domain Entity pattern</span></span>

<span data-ttu-id="bd764-109">实体表示域对象，主要由其标识、连续性和随时间推移的持久性来定义，而不仅仅由构成它们的属性来定义。</span><span class="sxs-lookup"><span data-stu-id="bd764-109">Entities represent domain objects and are primarily defined by their identity, continuity, and persistence over time, and not only by the attributes that comprise them.</span></span> <span data-ttu-id="bd764-110">正如 Eric Evans 所说，“主要由其标识定义的对象称为实体”。</span><span class="sxs-lookup"><span data-stu-id="bd764-110">As Eric Evans says, “an object primarily defined by its identity is called an Entity.”</span></span> <span data-ttu-id="bd764-111">实体在域模型中非常重要，因为它们是模型的基础。</span><span class="sxs-lookup"><span data-stu-id="bd764-111">Entities are very important in the domain model, since they are the base for a model.</span></span> <span data-ttu-id="bd764-112">因此，应对其进行仔细识别和设计。</span><span class="sxs-lookup"><span data-stu-id="bd764-112">Therefore, you should identify and design them carefully.</span></span>

<span data-ttu-id="bd764-113">*实体的标识可以跨多个微服务或绑定上下文。*</span><span class="sxs-lookup"><span data-stu-id="bd764-113">*An entity’s identity can cross multiple microservices or Bounded Contexts.*</span></span>

<span data-ttu-id="bd764-114">同一标识（但不是同一实体）可以跨多个绑定上下文或微服务建模。</span><span class="sxs-lookup"><span data-stu-id="bd764-114">The same identity (though not the same entity) can be modeled across multiple Bounded Contexts or microservices.</span></span> <span data-ttu-id="bd764-115">不过，这并不意味着具有相同属性和逻辑的相同实体会在多个绑定上下文中实现。</span><span class="sxs-lookup"><span data-stu-id="bd764-115">However, that does not imply that the same entity, with the same attributes and logic would be implemented in multiple Bounded Contexts.</span></span> <span data-ttu-id="bd764-116">相反，每个绑定上下文中的实体会将其属性和行为限制为该绑定上下文域中所需的属性和行为。</span><span class="sxs-lookup"><span data-stu-id="bd764-116">Instead, entities in each Bounded Context limit their attributes and behaviors to those required in that Bounded Context’s domain.</span></span>

<span data-ttu-id="bd764-117">例如，买家实体可能具有某个人的大部分属性，这些属性在配置文件或标识微服务的用户实体中定义，其中包括标识。</span><span class="sxs-lookup"><span data-stu-id="bd764-117">For instance, the buyer entity might have most of a person’s attributes that are defined in the user entity in the profile or identity microservice, including the identity.</span></span> <span data-ttu-id="bd764-118">但是订购微服务中的买家实体可能具有较少的属性，因为只有某些买家数据与订单流程相关。</span><span class="sxs-lookup"><span data-stu-id="bd764-118">But the buyer entity in the ordering microservice might have fewer attributes, because only certain buyer data is related to the order process.</span></span> <span data-ttu-id="bd764-119">每个微服务的上下文或每个绑定上下文都会影响其域模型。</span><span class="sxs-lookup"><span data-stu-id="bd764-119">The context of each microservice or Bounded Context impacts its domain model.</span></span>

<span data-ttu-id="bd764-120">*除了实现数据属性外，域实体还必须实现行为*</span><span class="sxs-lookup"><span data-stu-id="bd764-120">*Domain entities must implement behavior in addition to implementing data attributes*</span></span>

<span data-ttu-id="bd764-121">DDD 中的域实体必须实现与实体数据（在内存中访问的对象）相关的域逻辑或行为。</span><span class="sxs-lookup"><span data-stu-id="bd764-121">A domain entity in DDD must implement the domain logic or behavior related to the entity data (the object accessed in memory).</span></span> <span data-ttu-id="bd764-122">例如，作为订单实体类的一部分，你必须将业务逻辑和操作作为任务（例如添加订单项、数据验证和总计算）的方法实现。</span><span class="sxs-lookup"><span data-stu-id="bd764-122">For example, as part of an order entity class you must have business logic and operations implemented as methods for tasks such as adding an order item, data validation, and total calculation.</span></span> <span data-ttu-id="bd764-123">实体的方法负责处理实体的不变量和规则，而不是将这些规则分布在应用层中。</span><span class="sxs-lookup"><span data-stu-id="bd764-123">The entity’s methods take care of the invariants and rules of the entity instead of having those rules spread across the application layer.</span></span>

<span data-ttu-id="bd764-124">图 9-8 展示了一个域实体，它不仅实现数据属性，还实现具有相关域逻辑的操作或方法。</span><span class="sxs-lookup"><span data-stu-id="bd764-124">Figure 9-8 shows a domain entity that implements not only data attributes but operations or methods with related domain logic.</span></span>

![](./media/image9.png)

<span data-ttu-id="bd764-125">**图 9-8**.</span><span class="sxs-lookup"><span data-stu-id="bd764-125">**Figure 9-8**.</span></span> <span data-ttu-id="bd764-126">实现数据加行为的域实体设计示例</span><span class="sxs-lookup"><span data-stu-id="bd764-126">Example of a domain entity design implementing data plus behavior</span></span>

<span data-ttu-id="bd764-127">当然，实体有时可能不会在实体类中实现任何逻辑。</span><span class="sxs-lookup"><span data-stu-id="bd764-127">Of course, sometimes you can have entities that do not implement any logic as part of the entity class.</span></span> <span data-ttu-id="bd764-128">如果某个聚合内的子实体没有任何特殊逻辑，因为大多数逻辑都在聚合根中定义，则该子实体可能出现这种情况。</span><span class="sxs-lookup"><span data-stu-id="bd764-128">This can happen in child entities within an aggregate if the child entity does not have any special logic because most of the logic is defined in the aggregate root.</span></span> <span data-ttu-id="bd764-129">如果你有一个复杂的微服务，它在服务类而非域实体中实现了大量逻辑，那么你可能会陷入贫乏域模型中，下一节将对此进行解释。</span><span class="sxs-lookup"><span data-stu-id="bd764-129">If you have a complex microservice that has a lot of logic implemented in the service classes instead of in the domain entities, you could be falling into the anemic domain model, explained in the following section.</span></span>

### <a name="rich-domain-model-versus-anemic-domain-model"></a><span data-ttu-id="bd764-130">丰富域模型与贫乏域模型</span><span class="sxs-lookup"><span data-stu-id="bd764-130">Rich domain model versus anemic domain model</span></span>

<span data-ttu-id="bd764-131">Martin Fowler 在他的博客文章 [AnemicDomainModel](https://martinfowler.com/bliki/AnemicDomainModel.html) 中是这样描述贫乏域模型的：</span><span class="sxs-lookup"><span data-stu-id="bd764-131">In his post [AnemicDomainModel](https://martinfowler.com/bliki/AnemicDomainModel.html), Martin Fowler describes an anemic domain model this way:</span></span>

<span data-ttu-id="bd764-132">贫乏域模型的基本症状是，乍一看上去像是真实存在的。</span><span class="sxs-lookup"><span data-stu-id="bd764-132">The basic symptom of an Anemic Domain Model is that at first blush it looks like the real thing.</span></span> <span data-ttu-id="bd764-133">它包含一些对象，许多以域空间中的名词命名，这些对象与真实域模型具有的丰富关系和结构相关联。</span><span class="sxs-lookup"><span data-stu-id="bd764-133">There are objects, many named after the nouns in the domain space, and these objects are connected with the rich relationships and structure that true domain models have.</span></span> <span data-ttu-id="bd764-134">但当你观察它的行为时，问题来了，你发现这些对象几乎没有任何行为，完全就是一些 getter 和 setter 而已。</span><span class="sxs-lookup"><span data-stu-id="bd764-134">The catch comes when you look at the behavior, and you realize that there is hardly any behavior on these objects, making them little more than bags of getters and setters.</span></span>

<span data-ttu-id="bd764-135">当然，使用贫乏域模型时，将从一组可捕获所有域或业务逻辑的服务对象（传统上称为*业务层*）中使用这些数据模型。</span><span class="sxs-lookup"><span data-stu-id="bd764-135">Of course, when you use an anemic domain model, those data models will be used from a set of service objects (traditionally named the *business layer*) which capture all the domain or business logic.</span></span> <span data-ttu-id="bd764-136">业务层位于数据模型之上，就像使用数据一样使用数据模型。</span><span class="sxs-lookup"><span data-stu-id="bd764-136">The business layer sits on top of the data model and uses the data model just as data.</span></span>

<span data-ttu-id="bd764-137">贫乏域模型就是一种程序化样式设计。</span><span class="sxs-lookup"><span data-stu-id="bd764-137">The anemic domain model is just a procedural style design.</span></span> <span data-ttu-id="bd764-138">贫乏实体对象不是真实的对象，因为它们缺乏行为（方法）。</span><span class="sxs-lookup"><span data-stu-id="bd764-138">Anemic entity objects are not real objects because they lack behavior (methods).</span></span> <span data-ttu-id="bd764-139">它们只保存数据属性，因此它不是一种面向对象的设计。</span><span class="sxs-lookup"><span data-stu-id="bd764-139">They only hold data properties and thus it is not object-oriented design.</span></span> <span data-ttu-id="bd764-140">通过将所有行为放到服务对象（业务层）中，实质上最终会产生[面条式代码](https://en.wikipedia.org/wiki/Spaghetti_code)或[事务脚本](https://martinfowler.com/eaaCatalog/transactionScript.html)，因而失去域模型提供的优势。</span><span class="sxs-lookup"><span data-stu-id="bd764-140">By putting all the behavior out into service objects (the business layer) you essentially end up with [spaghetti code](https://en.wikipedia.org/wiki/Spaghetti_code) or [transaction scripts](https://martinfowler.com/eaaCatalog/transactionScript.html), and therefore you lose the advantages that a domain model provides.</span></span>

<span data-ttu-id="bd764-141">不管怎样，如果微服务或绑定上下文非常简单（CRUD 服务），仅包含数据属性的实体对象形式的贫乏域模型可能已经足够，没必要实现更复杂的 DDD 模式。</span><span class="sxs-lookup"><span data-stu-id="bd764-141">Regardless, if your microservice or Bounded Context is very simple (a CRUD service), the anemic domain model in the form of entity objects with just data properties might be good enough, and it might not be worth implementing more complex DDD patterns.</span></span> <span data-ttu-id="bd764-142">在这种情况下，它就是一个持久性模型，因为你特意创建了一个仅包含用于 CRUD 的数据的实体。</span><span class="sxs-lookup"><span data-stu-id="bd764-142">In that case, it will be simply a persistence model, because you have intentionally created an entity with only data for CRUD purposes.</span></span>

<span data-ttu-id="bd764-143">这就是为什么微服务体系结构特别适用于多体系结构方法（具体取决于每个绑定上下文）。</span><span class="sxs-lookup"><span data-stu-id="bd764-143">That is why microservices architectures are perfect for a multi-architectural approach depending on each Bounded Context.</span></span> <span data-ttu-id="bd764-144">例如，在 eShopOnContainers 中，订购微服务实现了 DDD 模式，但目录微服务（一种简单的 CRUD 服务）没有。</span><span class="sxs-lookup"><span data-stu-id="bd764-144">For instance, in eShopOnContainers, the ordering microservice implements DDD patterns, but the catalog microservice, which is a simple CRUD service, does not.</span></span>

<span data-ttu-id="bd764-145">有人说贫乏域模型是一种反模式。</span><span class="sxs-lookup"><span data-stu-id="bd764-145">Some people say that the anemic domain model is an anti-pattern.</span></span> <span data-ttu-id="bd764-146">这真的取决于你要实现什么。</span><span class="sxs-lookup"><span data-stu-id="bd764-146">It really depends on what you are implementing.</span></span> <span data-ttu-id="bd764-147">如果你创建的微服务足够简单（例如，CRUD 服务），则采用贫乏域模型，它不是反模式。</span><span class="sxs-lookup"><span data-stu-id="bd764-147">If the microservice you are creating is simple enough (for example, a CRUD service), following the anemic domain model it is not an anti-pattern.</span></span> <span data-ttu-id="bd764-148">但是，如果需要解决包含大量不断变化的业务规则的微服务域的复杂性，那么贫乏域模型可能是该微服务或绑定上下文的反模式。</span><span class="sxs-lookup"><span data-stu-id="bd764-148">However, if you need to tackle the complexity of a microservice’s domain that has a lot of ever-changing business rules, the anemic domain model might be an anti-pattern for that microservice or Bounded Context.</span></span> <span data-ttu-id="bd764-149">在这种情况下，将其设计为具有包含数据加行为的实体的丰富模型并实现附加 DDD 模式（聚合、值对象等）可能对这种微服务的长期成功具有极大的好处。</span><span class="sxs-lookup"><span data-stu-id="bd764-149">In that case, designing it as a rich model with entities containing data plus behavior as well as implementing additional DDD patterns (aggregates, value objects, etc.) might have huge benefits for the long-term success of such a microservice.</span></span>

#### <a name="additional-resources"></a><span data-ttu-id="bd764-150">其他资源</span><span class="sxs-lookup"><span data-stu-id="bd764-150">Additional resources</span></span>

-   <span data-ttu-id="bd764-151">**DevIQ.域实体**
    [*http://deviq.com/entity/*](http://deviq.com/entity/)</span><span class="sxs-lookup"><span data-stu-id="bd764-151">**DevIQ. Domain Entity**
[*http://deviq.com/entity/*](http://deviq.com/entity/)</span></span>

-   <span data-ttu-id="bd764-152">**Martin Fowler。域模型**
    [*https://martinfowler.com/eaaCatalog/domainModel.html*](https://martinfowler.com/eaaCatalog/domainModel.html)</span><span class="sxs-lookup"><span data-stu-id="bd764-152">**Martin Fowler. The Domain Model**
[*https://martinfowler.com/eaaCatalog/domainModel.html*](https://martinfowler.com/eaaCatalog/domainModel.html)</span></span>

-   <span data-ttu-id="bd764-153">**Martin Fowler。The Anemic Domain Model**（贫乏域模型）</span><span class="sxs-lookup"><span data-stu-id="bd764-153">**Martin Fowler. The Anemic Domain Model**</span></span>

    <https://martinfowler.com/bliki/AnemicDomainModel.html>

### <a name="the-value-object-pattern"></a><span data-ttu-id="bd764-154">值对象模式</span><span class="sxs-lookup"><span data-stu-id="bd764-154">The Value Object pattern</span></span>

<span data-ttu-id="bd764-155">正如 Eric Evans 所指出的，“许多对象没有概念标识。</span><span class="sxs-lookup"><span data-stu-id="bd764-155">As Eric Evans has noted, “Many objects do not have conceptual identity.</span></span> <span data-ttu-id="bd764-156">这些对象用于描述某个事物的某些特征。”</span><span class="sxs-lookup"><span data-stu-id="bd764-156">These objects describe certain characteristics of a thing.”</span></span>

<span data-ttu-id="bd764-157">实体需要标识，但系统中的许多对象不需要，例如值对象模式。</span><span class="sxs-lookup"><span data-stu-id="bd764-157">An entity requires an identity, but there are many objects in a system that do not, like the Value Object pattern.</span></span> <span data-ttu-id="bd764-158">值对象是一种没有概念标识的对象，用于描述域方面。</span><span class="sxs-lookup"><span data-stu-id="bd764-158">A value object is an object with no conceptual identity that describes a domain aspect.</span></span> <span data-ttu-id="bd764-159">这些对象实例化后可表示设计元素，你只会暂时关注它们。</span><span class="sxs-lookup"><span data-stu-id="bd764-159">These are objects that you instantiate to represent design elements that only concern you temporarily.</span></span> <span data-ttu-id="bd764-160">你只关心它们是*什么*，而不关心它们是*谁*。</span><span class="sxs-lookup"><span data-stu-id="bd764-160">You care about *what* they are, not *who* they are.</span></span> <span data-ttu-id="bd764-161">其示例包括数字和字符串，但也可以是更高级别的概念，例如属性组。</span><span class="sxs-lookup"><span data-stu-id="bd764-161">Examples include numbers and strings, but can also be higher-level concepts like groups of attributes.</span></span>

<span data-ttu-id="bd764-162">一个微服务中的实体在另一个微服务中可能就不是实体，因为在第二种情况下，绑定上下文可能具有不同的含义。</span><span class="sxs-lookup"><span data-stu-id="bd764-162">Something that is an entity in a microservice might not be an entity in another microservice, because in the second case, the Bounded Context might have a different meaning.</span></span> <span data-ttu-id="bd764-163">例如，电子商务应用程序中的地址可能根本没有标识，因为它可能仅表示个人或公司的客户资料的一组属性。</span><span class="sxs-lookup"><span data-stu-id="bd764-163">For example, an address in an e-commerce application might not have an identity at all, since it might only represent a group of attributes of the customer’s profile for a person or company.</span></span> <span data-ttu-id="bd764-164">在这种情况下，地址应归类为值对象。</span><span class="sxs-lookup"><span data-stu-id="bd764-164">In this case, the address should be classified as a value object.</span></span> <span data-ttu-id="bd764-165">但是，在电力公司的应用程序中，客户地址对于业务领域可能很重要。</span><span class="sxs-lookup"><span data-stu-id="bd764-165">However, in an application for an electric power utility company, the customer address could be important for the business domain.</span></span> <span data-ttu-id="bd764-166">因此，该地址必须具有标识，以便计费系统直接链接到该地址。</span><span class="sxs-lookup"><span data-stu-id="bd764-166">Therefore, the address must have an identity so the billing system can be directly linked to the address.</span></span> <span data-ttu-id="bd764-167">在这种情况下，地址应归类为域实体。</span><span class="sxs-lookup"><span data-stu-id="bd764-167">In that case, an address should be classified as a domain entity.</span></span>

<span data-ttu-id="bd764-168">有名字和姓氏的人通常是一个实体，因为这个人具有标识，即使其名字和姓氏与另一组值重合（例如这些名字还指另一个人）也是如此。</span><span class="sxs-lookup"><span data-stu-id="bd764-168">A person with a name and surname is usually an entity because a person has identity, even if the name and surname coincide with another set of values, such as if those names also refers to a different person.</span></span>

<span data-ttu-id="bd764-169">值对象在关系数据库和 ORM（如 EF）中很难管理，而在面向文档的数据库中，它们更易于实现和使用。</span><span class="sxs-lookup"><span data-stu-id="bd764-169">Value objects are hard to manage in relational databases and ORMs like EF, whereas in document oriented databases they are easier to implement and use.</span></span>

#### <a name="additional-resources"></a><span data-ttu-id="bd764-170">其他资源</span><span class="sxs-lookup"><span data-stu-id="bd764-170">Additional resources</span></span>

-   <span data-ttu-id="bd764-171">**Martin Fowler。值对象模式**
    [*https://martinfowler.com/bliki/ValueObject.html*](https://martinfowler.com/bliki/ValueObject.html)</span><span class="sxs-lookup"><span data-stu-id="bd764-171">**Martin Fowler. Value Object pattern**
[*https://martinfowler.com/bliki/ValueObject.html*](https://martinfowler.com/bliki/ValueObject.html)</span></span>

-   <span data-ttu-id="bd764-172">**值对象**
    [*http://deviq.com/value-object/*](http://deviq.com/value-object/)</span><span class="sxs-lookup"><span data-stu-id="bd764-172">**Value Object**
[*http://deviq.com/value-object/*](http://deviq.com/value-object/)</span></span>

-   <span data-ttu-id="bd764-173">**测试驱动开发中的值对象**
    [*https://leanpub.com/tdd-ebook/read\#leanpub-auto-value-objects*](https://leanpub.com/tdd-ebook/read#leanpub-auto-value-objects)</span><span class="sxs-lookup"><span data-stu-id="bd764-173">**Value Objects in Test-Driven Development**
[*https://leanpub.com/tdd-ebook/read\#leanpub-auto-value-objects*](https://leanpub.com/tdd-ebook/read#leanpub-auto-value-objects)</span></span>

-   <span data-ttu-id="bd764-174">**Eric Evans。Domain-Driven Design: Tackling Complexity in the Heart of Software.**（域驱动设计：软件核心复杂性应对之道。）</span><span class="sxs-lookup"><span data-stu-id="bd764-174">**Eric Evans. Domain-Driven Design: Tackling Complexity in the Heart of Software.**</span></span> <span data-ttu-id="bd764-175">（书；包括值对象的讨论）[https://www.amazon.com/Domain-Driven-Design-Tackling-Complexity-Software/dp/0321125215/](https://www.amazon.com/Domain-Driven-Design-Tackling-Complexity-Software/dp/0321125215/)</span><span class="sxs-lookup"><span data-stu-id="bd764-175">(Book; includes a discussion of value objects) [*https://www.amazon.com/Domain-Driven-Design-Tackling-Complexity-Software/dp/0321125215/*](https://www.amazon.com/Domain-Driven-Design-Tackling-Complexity-Software/dp/0321125215/)</span></span>

### <a name="the-aggregate-pattern"></a><span data-ttu-id="bd764-176">聚合模式</span><span class="sxs-lookup"><span data-stu-id="bd764-176">The Aggregate pattern</span></span>

<span data-ttu-id="bd764-177">域模型包含不同数据实体和进程的群集，可以控制功能的重要方面，例如订单履行或库存。</span><span class="sxs-lookup"><span data-stu-id="bd764-177">A domain model contains clusters of different data entities and processes that can control a significant area of functionality, such as order fulfilment or inventory.</span></span> <span data-ttu-id="bd764-178">聚合是一种粒度更细的 DDD 单元，用于描述一群或一组可视为内聚单元的实体和行为。</span><span class="sxs-lookup"><span data-stu-id="bd764-178">A more fine-grained DDD unit is the aggregate, which describes a cluster or group of entities and behaviors that can be treated as a cohesive unit.</span></span>

<span data-ttu-id="bd764-179">通常基于所需事务来定义聚合。</span><span class="sxs-lookup"><span data-stu-id="bd764-179">You usually define an aggregate based on the transactions that you need.</span></span> <span data-ttu-id="bd764-180">一个典型的例子就是订单，订单中还包含订单项列表。</span><span class="sxs-lookup"><span data-stu-id="bd764-180">A classic example is an order that also contains a list of order items.</span></span> <span data-ttu-id="bd764-181">订单项通常是一个实体。</span><span class="sxs-lookup"><span data-stu-id="bd764-181">An order item will usually be an entity.</span></span> <span data-ttu-id="bd764-182">但它是订单聚合内的子实体，该聚合还包含订单实体作为其根实体，通常称为聚合根。</span><span class="sxs-lookup"><span data-stu-id="bd764-182">But it will be a child entity within the order aggregate, which will also contain the order entity as its root entity, typically called an aggregate root.</span></span>

<span data-ttu-id="bd764-183">识别聚合可能很难。</span><span class="sxs-lookup"><span data-stu-id="bd764-183">Identifying aggregates can be hard.</span></span> <span data-ttu-id="bd764-184">聚合是一组必须一致的对象，但不能按此挑选一组对象就将它们标记为聚合。</span><span class="sxs-lookup"><span data-stu-id="bd764-184">An aggregate is a group of objects that must be consistent together, but you cannot just pick a group of objects and label them an aggregate.</span></span> <span data-ttu-id="bd764-185">你必须从域概念开始，并考虑在与该概念相关的最常见事务中使用的实体。</span><span class="sxs-lookup"><span data-stu-id="bd764-185">You must start with a domain concept and think about the entities that are used in the most common transactions related to that concept.</span></span> <span data-ttu-id="bd764-186">那些需要在事务上一致的实体就形成一个聚合。</span><span class="sxs-lookup"><span data-stu-id="bd764-186">Those entities that need to be transactionally consistent are what forms an aggregate.</span></span> <span data-ttu-id="bd764-187">考虑事务操作可能是识别聚合的最佳方式。</span><span class="sxs-lookup"><span data-stu-id="bd764-187">Thinking about transaction operations is probably the best way to identify aggregates.</span></span>

### <a name="the-aggregate-root-or-root-entity-pattern"></a><span data-ttu-id="bd764-188">聚合根或根实体模式</span><span class="sxs-lookup"><span data-stu-id="bd764-188">The Aggregate Root or Root Entity pattern</span></span>

<span data-ttu-id="bd764-189">聚合由至少一个实体组成：聚合根，也称为根实体或主实体。</span><span class="sxs-lookup"><span data-stu-id="bd764-189">An aggregate is composed of at least one entity: the aggregate root, also called root entity or primary entity.</span></span> <span data-ttu-id="bd764-190">此外，它还可以有多个子实体和值对象，所有实体和对象一起共同实现所需的行为和事务。</span><span class="sxs-lookup"><span data-stu-id="bd764-190">Additionally, it can have multiple child entities and value objects, with all entities and objects working together to implement required behavior and transactions.</span></span>

<span data-ttu-id="bd764-191">聚合根的目的是确保聚合的一致性；它应该是通过聚合根类中的方法或操作更新聚合的唯一入口点。</span><span class="sxs-lookup"><span data-stu-id="bd764-191">The purpose of an aggregate root is to ensure the consistency of the aggregate; it should be the only entry point for updates to the aggregate through methods or operations in the aggregate root class.</span></span> <span data-ttu-id="bd764-192">只能通过聚合根对聚合内的实体进行更改。</span><span class="sxs-lookup"><span data-stu-id="bd764-192">You should make changes to entities within the aggregate only via the aggregate root.</span></span> <span data-ttu-id="bd764-193">它是聚合的一致性守护者，它会考虑到可能需要在聚合中遵守的所有不变量和一致性规则。</span><span class="sxs-lookup"><span data-stu-id="bd764-193">It is the aggregate’s consistency guardian, taking into account all the invariants and consistency rules you might need to comply with in your aggregate.</span></span> <span data-ttu-id="bd764-194">如果单独更改某个子实体或值对象，聚合根无法确保聚合处于有效状态。</span><span class="sxs-lookup"><span data-stu-id="bd764-194">If you change a child entity or value object independently, the aggregate root cannot ensure that the aggregate is in a valid state.</span></span> <span data-ttu-id="bd764-195">这就像一张桌脚松动了的桌子。</span><span class="sxs-lookup"><span data-stu-id="bd764-195">It would be like a table with a loose leg.</span></span> <span data-ttu-id="bd764-196">保持一致性是聚合根的主要目的。</span><span class="sxs-lookup"><span data-stu-id="bd764-196">Maintaining consistency is the main purpose of the aggregate root.</span></span>

<span data-ttu-id="bd764-197">在图 9-9 中，可以看到一些示例聚合，例如买家聚合，其中包含一个实体（聚合根 Buyer）。</span><span class="sxs-lookup"><span data-stu-id="bd764-197">In Figure 9-9, you can see sample aggregates like the buyer aggregate, which contains a single entity (the aggregate root Buyer).</span></span> <span data-ttu-id="bd764-198">订单聚合包含多个实体和一个值对象。</span><span class="sxs-lookup"><span data-stu-id="bd764-198">The order aggregate contains multiple entities and a value object.</span></span>

![](./media/image10.png)

<span data-ttu-id="bd764-199">**图 9-9**.</span><span class="sxs-lookup"><span data-stu-id="bd764-199">**Figure 9-9**.</span></span> <span data-ttu-id="bd764-200">包含多个或单个实体的聚合示例</span><span class="sxs-lookup"><span data-stu-id="bd764-200">Example of aggregates with multiple or single entities</span></span>

<span data-ttu-id="bd764-201">请注意，视你的域而定，Buyer 聚合可能会有其他子实体，就像在 eShopOnContainers 参考应用程序的订购微服务中那样。</span><span class="sxs-lookup"><span data-stu-id="bd764-201">Note that the Buyer aggregate could have additional child entities, depending on your domain, as it does in the ordering microservice in the eShopOnContainers reference application.</span></span> <span data-ttu-id="bd764-202">图 9-9 仅列举了买家具有单个实体的情况，作为仅包含聚合根的聚合示例。</span><span class="sxs-lookup"><span data-stu-id="bd764-202">Figure 9-9 just illustrates a case in which the buyer has a single entity, as an example of an aggregate that contains only an aggregate root.</span></span>

<span data-ttu-id="bd764-203">为了让聚合一直相互隔离并保持它们之间的清晰界限，建议禁止在 DDD 域模型中的聚合之间直接导航，并且模型仅具有外键 (FK) 字段，正如在 eShopOnContainers 的[订购微服务域模型](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.Domain/AggregatesModel/OrderAggregate/Order.cs)中所实现的那样。</span><span class="sxs-lookup"><span data-stu-id="bd764-203">In order to maintain separation of aggregates and keep clear boundaries between them, it is a good practice in a DDD domain model to disallow direct navigation between aggregates and only having the foreign key (FK) field, as implemented in the [Ordering microservice domain model](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.Domain/AggregatesModel/OrderAggregate/Order.cs) in eShopOnContainers.</span></span> <span data-ttu-id="bd764-204">Order 实体针对买家只有 FK 字段，没有 EF Core 导航属性，如以下代码所示：</span><span class="sxs-lookup"><span data-stu-id="bd764-204">The Order entity only has a FK field for the buyer, but not an EF Core navigation property, as shown in the following code:</span></span>

```csharp
public class Order : Entity, IAggregateRoot
{
    private DateTime _orderDate;
    public Address Address { get; private set; }
    private int? _buyerId; //FK pointing to a different aggregate root
    public OrderStatus OrderStatus { get; private set; }
    private readonly List<OrderItem> _orderItems;
    public IReadOnlyCollection<OrderItem> OrderItems => _orderItems;
    // ... Additional code
}
```

<span data-ttu-id="bd764-205">识别和使用聚合需要经过大量探索与体会。</span><span class="sxs-lookup"><span data-stu-id="bd764-205">Identifying and working with aggregates requires research and experience.</span></span> <span data-ttu-id="bd764-206">有关详细信息，请参阅下面的“其他资源”列表。</span><span class="sxs-lookup"><span data-stu-id="bd764-206">For more information, see the following Additional resources list.</span></span>

#### <a name="additional-resources"></a><span data-ttu-id="bd764-207">其他资源</span><span class="sxs-lookup"><span data-stu-id="bd764-207">Additional resources</span></span>

-   <span data-ttu-id="bd764-208">**Vaughn Vernon。高效聚合设计 - 第 I 部分：创建单个聚合模型**
    [*https://vaughnvernon.co/wordpress/wp-content/uploads/2014/10/DDD\_COMMUNITY\_ESSAY\_AGGREGATES\_PART\_1.pdf*](https://vaughnvernon.co/wordpress/wp-content/uploads/2014/10/DDD_COMMUNITY_ESSAY_AGGREGATES_PART_1.pdf)</span><span class="sxs-lookup"><span data-stu-id="bd764-208">**Vaughn Vernon. Effective Aggregate Design - Part I: Modeling a Single Aggregate**
[*https://vaughnvernon.co/wordpress/wp-content/uploads/2014/10/DDD\_COMMUNITY\_ESSAY\_AGGREGATES\_PART\_1.pdf*](https://vaughnvernon.co/wordpress/wp-content/uploads/2014/10/DDD_COMMUNITY_ESSAY_AGGREGATES_PART_1.pdf)</span></span>

-   <span data-ttu-id="bd764-209">**Vaughn Vernon。高效聚合设计 - 第 II 部分：协同聚合**
    *<https://vaughnvernon.co/wordpress/wp-content/uploads/2014/10/DDD_COMMUNITY_ESSAY_AGGREGATES_PART_2.pdf>*</span><span class="sxs-lookup"><span data-stu-id="bd764-209">**Vaughn Vernon. Effective Aggregate Design - Part II: Making Aggregates Work Together**
*<https://vaughnvernon.co/wordpress/wp-content/uploads/2014/10/DDD_COMMUNITY_ESSAY_AGGREGATES_PART_2.pdf> *</span></span>

-   <span data-ttu-id="bd764-210">**Vaughn Vernon。高效聚合设计 - 第 III 部分：通过发现获得见解**
    *<https://vaughnvernon.co/wordpress/wp-content/uploads/2014/10/DDD_COMMUNITY_ESSAY_AGGREGATES_PART_3.pdf>*</span><span class="sxs-lookup"><span data-stu-id="bd764-210">**Vaughn Vernon. Effective Aggregate Design - Part III: Gaining Insight Through Discovery**
*<https://vaughnvernon.co/wordpress/wp-content/uploads/2014/10/DDD_COMMUNITY_ESSAY_AGGREGATES_PART_3.pdf> *</span></span>

-   <span data-ttu-id="bd764-211">**Sergey Grybniak。DDD 战术设计模式**
    [*https://www.codeproject.com/Articles/1164363/Domain-Driven-Design-Tactical-Design-Patterns-Part*](https://www.codeproject.com/Articles/1164363/Domain-Driven-Design-Tactical-Design-Patterns-Part)</span><span class="sxs-lookup"><span data-stu-id="bd764-211">**Sergey Grybniak. DDD Tactical Design Patterns**
[*https://www.codeproject.com/Articles/1164363/Domain-Driven-Design-Tactical-Design-Patterns-Part*](https://www.codeproject.com/Articles/1164363/Domain-Driven-Design-Tactical-Design-Patterns-Part)</span></span>

-   <span data-ttu-id="bd764-212">**Chris Richardson.使用聚合开发事务微服务**
    [*https://www.infoq.com/articles/microservices-aggregates-events-cqrs-part-1-richardson*](https://www.infoq.com/articles/microservices-aggregates-events-cqrs-part-1-richardson)</span><span class="sxs-lookup"><span data-stu-id="bd764-212">**Chris Richardson. Developing Transactional Microservices Using Aggregates**
[*https://www.infoq.com/articles/microservices-aggregates-events-cqrs-part-1-richardson*](https://www.infoq.com/articles/microservices-aggregates-events-cqrs-part-1-richardson)</span></span>

-   <span data-ttu-id="bd764-213">**DevIQ.聚合模式**
    [*http://deviq.com/aggregate-pattern/*](http://deviq.com/aggregate-pattern/)</span><span class="sxs-lookup"><span data-stu-id="bd764-213">**DevIQ. The Aggregate pattern**
[*http://deviq.com/aggregate-pattern/*](http://deviq.com/aggregate-pattern/)</span></span>


>[!div class="step-by-step"]
<span data-ttu-id="bd764-214">[上一篇] (ddd-oriented-microservice.md) [下一篇] (net-core-microservice-domain-model.md)</span><span class="sxs-lookup"><span data-stu-id="bd764-214">[Previous] (ddd-oriented-microservice.md) [Next] (net-core-microservice-domain-model.md)</span></span>
