---
title: "设计 microservice 域模型"
description: "为容器化的.NET 应用程序的.NET 微服务体系结构 |设计 microservice 域模型"
keywords: "Docker, 微服务, ASP.NET, 容器"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: 455a2c5a39fb9b765b557610ab108f8c75882dbd
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="designing-a-microservice-domain-model"></a><span data-ttu-id="25e0c-104">设计 microservice 域模型</span><span class="sxs-lookup"><span data-stu-id="25e0c-104">Designing a microservice domain model</span></span>

<span data-ttu-id="25e0c-105">*定义为每个业务 microservice 或绑定上下文的一个丰富的域模型*</span><span class="sxs-lookup"><span data-stu-id="25e0c-105">*Define one rich domain model for each business microservice or Bounded Context*</span></span>

<span data-ttu-id="25e0c-106">你的目标是创建每个业务 microservice 或绑定上下文 (BC) 的单个凝聚力域模型。</span><span class="sxs-lookup"><span data-stu-id="25e0c-106">Your goal is to create a single cohesive domain model for each business microservice or Bounded Context (BC).</span></span> <span data-ttu-id="25e0c-107">请记住，但是的业务连续性或业务 microservice 有时无法组成共享单一域模型的多个物理服务。</span><span class="sxs-lookup"><span data-stu-id="25e0c-107">Keep in mind, however, that a BC or business microservice could sometimes be composed of several physical services that share a single domain model.</span></span> <span data-ttu-id="25e0c-108">域模型必须捕获规则、 行为、 业务语言和单个绑定上下文或业务 microservice 它所表示的约束。</span><span class="sxs-lookup"><span data-stu-id="25e0c-108">The domain model must capture the rules, behavior, business language, and constraints of the single Bounded Context or business microservice that it represents.</span></span>

## <a name="the-domain-entity-pattern"></a><span data-ttu-id="25e0c-109">域实体模式</span><span class="sxs-lookup"><span data-stu-id="25e0c-109">The Domain Entity pattern</span></span>

<span data-ttu-id="25e0c-110">实体表示域对象，并由其标识、 连续性和持久性随着时间推移，以及不仅包含它们的属性主要定义。</span><span class="sxs-lookup"><span data-stu-id="25e0c-110">Entities represent domain objects and are primarily defined by their identity, continuity, and persistence over time, and not only by the attributes that comprise them.</span></span> <span data-ttu-id="25e0c-111">如 Eric Evans 说:"主要由其标识定义的对象称为实体。"</span><span class="sxs-lookup"><span data-stu-id="25e0c-111">As Eric Evans says, “an object primarily defined by its identity is called an Entity.”</span></span> <span data-ttu-id="25e0c-112">实体是在域模型中中, 非常重要，因为它们是一种模型的基。</span><span class="sxs-lookup"><span data-stu-id="25e0c-112">Entities are very important in the domain model, since they are the base for a model.</span></span> <span data-ttu-id="25e0c-113">因此，你应确定并仔细设计它们。</span><span class="sxs-lookup"><span data-stu-id="25e0c-113">Therefore, you should identify and design them carefully.</span></span>

<span data-ttu-id="25e0c-114">*实体的标识可以跨多个微服务或绑定上下文。*</span><span class="sxs-lookup"><span data-stu-id="25e0c-114">*An entity’s identity can cross multiple microservices or Bounded Contexts.*</span></span>

<span data-ttu-id="25e0c-115">相同的标识 （但不相同的实体） 可以跨多个绑定的上下文或微服务建模。</span><span class="sxs-lookup"><span data-stu-id="25e0c-115">The same identity (though not the same entity) can be modeled across multiple Bounded Contexts or microservices.</span></span> <span data-ttu-id="25e0c-116">但是，，并不意味着，将在多个绑定的上下文中实现相同的实体，具有相同的属性和逻辑。</span><span class="sxs-lookup"><span data-stu-id="25e0c-116">However, that does not imply that the same entity, with the same attributes and logic would be implemented in multiple Bounded Contexts.</span></span> <span data-ttu-id="25e0c-117">相反，每个绑定的上下文中的实体限制它们的属性和行为所需的绑定上下文的域中。</span><span class="sxs-lookup"><span data-stu-id="25e0c-117">Instead, entities in each Bounded Context limit their attributes and behaviors to those required in that Bounded Context’s domain.</span></span>

<span data-ttu-id="25e0c-118">例如，buyer 实体可能具有大部分中配置文件或标识微服务，包括标识中的用户实体定义的人员的属性。</span><span class="sxs-lookup"><span data-stu-id="25e0c-118">For instance, the buyer entity might have most of a person’s attributes that are defined in the user entity in the profile or identity microservice, including the identity.</span></span> <span data-ttu-id="25e0c-119">但中排序微服务构成的 buyer 实体可能具有较少的属性，因为仅某些 buyer 数据与订单过程。</span><span class="sxs-lookup"><span data-stu-id="25e0c-119">But the buyer entity in the ordering microservice might have fewer attributes, because only certain buyer data is related to the order process.</span></span> <span data-ttu-id="25e0c-120">每个微服务构成的上下文或绑定上下文会影响其域模型。</span><span class="sxs-lookup"><span data-stu-id="25e0c-120">The context of each microservice or Bounded Context impacts its domain model.</span></span>

<span data-ttu-id="25e0c-121">*域实体必须实现除了实现数据属性的行为*</span><span class="sxs-lookup"><span data-stu-id="25e0c-121">*Domain entities must implement behavior in addition to implementing data attributes*</span></span>

<span data-ttu-id="25e0c-122">DDD 中的域实体必须实现的域逻辑或与实体数据 （在内存中访问的对象） 相关的行为。</span><span class="sxs-lookup"><span data-stu-id="25e0c-122">A domain entity in DDD must implement the domain logic or behavior related to the entity data (the object accessed in memory).</span></span> <span data-ttu-id="25e0c-123">例如，作为 order 实体类的一部分必须具有业务逻辑和操作作为任务，如添加顺序项、 数据验证和总计算的方法实现。</span><span class="sxs-lookup"><span data-stu-id="25e0c-123">For example, as part of an order entity class you must have business logic and operations implemented as methods for tasks such as adding an order item, data validation, and total calculation.</span></span> <span data-ttu-id="25e0c-124">实体的方法负责的固定条件及而不是让分布在应用程序层这些规则的实体的规则。</span><span class="sxs-lookup"><span data-stu-id="25e0c-124">The entity’s methods take care of the invariants and rules of the entity instead of having those rules spread across the application layer.</span></span>

<span data-ttu-id="25e0c-125">图 9-8 显示实现不仅数据属性，但操作或具有相关的域逻辑的方法的域实体。</span><span class="sxs-lookup"><span data-stu-id="25e0c-125">Figure 9-8 shows a domain entity that implements not only data attributes but operations or methods with related domain logic.</span></span>

![](./media/image9.png)

<span data-ttu-id="25e0c-126">**图 9-8**。</span><span class="sxs-lookup"><span data-stu-id="25e0c-126">**Figure 9-8**.</span></span> <span data-ttu-id="25e0c-127">实现的数据以及行为域实体设计的示例</span><span class="sxs-lookup"><span data-stu-id="25e0c-127">Example of a domain entity design implementing data plus behavior</span></span>

<span data-ttu-id="25e0c-128">当然，有时你可以具有的未作为实体类的一部分实现的任何逻辑实体。</span><span class="sxs-lookup"><span data-stu-id="25e0c-128">Of course, sometimes you can have entities that do not implement any logic as part of the entity class.</span></span> <span data-ttu-id="25e0c-129">如果子实体没有任何特殊逻辑，因为在聚合根中定义的大部分逻辑，这可能发生在聚合子实体中。</span><span class="sxs-lookup"><span data-stu-id="25e0c-129">This can happen in child entities within an aggregate if the child entity does not have any special logic because most of the logic is defined in the aggregate root.</span></span> <span data-ttu-id="25e0c-130">如果你有具有大量逻辑而不是域实体中的服务类中实现的复杂微服务，你无法落到贫乏域模型中下, 一节中所述。</span><span class="sxs-lookup"><span data-stu-id="25e0c-130">If you have a complex microservice that has a lot of logic implemented in the service classes instead of in the domain entities, you could be falling into the anemic domain model, explained in the following section.</span></span>

### <a name="rich-domain-model-versus-anemic-domain-model"></a><span data-ttu-id="25e0c-131">与贫乏域模型的丰富域模型</span><span class="sxs-lookup"><span data-stu-id="25e0c-131">Rich domain model versus anemic domain model</span></span>

<span data-ttu-id="25e0c-132">在他的博客文章[AnemicDomainModel](https://martinfowler.com/bliki/AnemicDomainModel.html)，Martin Fowler 描述贫乏域模型这种方式：</span><span class="sxs-lookup"><span data-stu-id="25e0c-132">In his post [AnemicDomainModel](https://martinfowler.com/bliki/AnemicDomainModel.html), Martin Fowler describes an anemic domain model this way:</span></span>

<span data-ttu-id="25e0c-133">贫乏的域模型的基本症状是，乍一看上去像真实存在。</span><span class="sxs-lookup"><span data-stu-id="25e0c-133">The basic symptom of an Anemic Domain Model is that at first blush it looks like the real thing.</span></span> <span data-ttu-id="25e0c-134">没有对象，许多命名的名词中的域空间中，并且这些对象已连接到的丰富关系和 true 域模型具有的结构。</span><span class="sxs-lookup"><span data-stu-id="25e0c-134">There are objects, many named after the nouns in the domain space, and these objects are connected with the rich relationships and structure that true domain models have.</span></span> <span data-ttu-id="25e0c-135">在 catch 时看行为，且您实现这些对象上没有几乎任何行为稍有多个包的 getter 和 setter 使它们提出建议。</span><span class="sxs-lookup"><span data-stu-id="25e0c-135">The catch comes when you look at the behavior, and you realize that there is hardly any behavior on these objects, making them little more than bags of getters and setters.</span></span>

<span data-ttu-id="25e0c-136">当然，当你使用贫乏域模型，这些数据模型将使用从一组的服务对象 (传统上命名*业务层*) 的捕获所有的域或业务逻辑。</span><span class="sxs-lookup"><span data-stu-id="25e0c-136">Of course, when you use an anemic domain model, those data models will be used from a set of service objects (traditionally named the *business layer*) which capture all the domain or business logic.</span></span> <span data-ttu-id="25e0c-137">业务层位于数据模型之上，并且只需将数据模型用作数据。</span><span class="sxs-lookup"><span data-stu-id="25e0c-137">The business layer sits on top of the data model and uses the data model just as data.</span></span>

<span data-ttu-id="25e0c-138">贫乏域模型是只是一种过程样式设计。</span><span class="sxs-lookup"><span data-stu-id="25e0c-138">The anemic domain model is just a procedural style design.</span></span> <span data-ttu-id="25e0c-139">贫乏实体对象不是真正的对象，因为它们缺少行为 （方法）。</span><span class="sxs-lookup"><span data-stu-id="25e0c-139">Anemic entity objects are not real objects because they lack behavior (methods).</span></span> <span data-ttu-id="25e0c-140">它们只包含数据属性，因此它不是面向对象的设计。</span><span class="sxs-lookup"><span data-stu-id="25e0c-140">They only hold data properties and thus it is not object-oriented design.</span></span> <span data-ttu-id="25e0c-141">通过将缩小置于服务对象 （业务层） 的所有行为你实质上是最终得到[复式代码](https://en.wikipedia.org/wiki/Spaghetti_code)或[事务脚本](https://martinfowler.com/eaaCatalog/transactionScript.html)，并因此会丢失优点，域模型提供。</span><span class="sxs-lookup"><span data-stu-id="25e0c-141">By putting all the behavior out into service objects (the business layer) you essentially end up with [spaghetti code](https://en.wikipedia.org/wiki/Spaghetti_code) or [transaction scripts](https://martinfowler.com/eaaCatalog/transactionScript.html), and therefore you lose the advantages that a domain model provides.</span></span>

<span data-ttu-id="25e0c-142">不论你的 microservice 或绑定上下文不非常简单 （CRUD 服务），只需数据属性的实体对象的形式贫乏域模型可能已经足够，好和可能不值得实现更复杂的 DDD 模式。</span><span class="sxs-lookup"><span data-stu-id="25e0c-142">Regardless, if your microservice or Bounded Context is very simple (a CRUD service), the anemic domain model in the form of entity objects with just data properties might be good enough, and it might not be worth implementing more complex DDD patterns.</span></span> <span data-ttu-id="25e0c-143">在这种情况下，它将只需持久性模型，因为您有意使用仅供 CRUD 的数据创建实体。</span><span class="sxs-lookup"><span data-stu-id="25e0c-143">In that case, it will be simply a persistence model, because you have intentionally created an entity with only data for CRUD purposes.</span></span>

<span data-ttu-id="25e0c-144">这是为什么微服务体系结构是特别适合于一种多体系结构方法，具体取决于每个绑定的上下文。</span><span class="sxs-lookup"><span data-stu-id="25e0c-144">That is why microservices architectures are perfect for a multi-architectural approach depending on each Bounded Context.</span></span> <span data-ttu-id="25e0c-145">例如，在 eShopOnContainers，排序 microservice 实现 DDD 模式，但目录微服务，这是一个简单 CRUD 服务，不。</span><span class="sxs-lookup"><span data-stu-id="25e0c-145">For instance, in eShopOnContainers, the ordering microservice implements DDD patterns, but the catalog microservice, which is a simple CRUD service, does not.</span></span>

<span data-ttu-id="25e0c-146">一些人有提示贫乏域模型是反模式。</span><span class="sxs-lookup"><span data-stu-id="25e0c-146">Some people say that the anemic domain model is an anti-pattern.</span></span> <span data-ttu-id="25e0c-147">它实际上取决于你要实现。</span><span class="sxs-lookup"><span data-stu-id="25e0c-147">It really depends on what you are implementing.</span></span> <span data-ttu-id="25e0c-148">如果要创建 microservice 是简单足够 （例如，CRUD 服务），以下贫乏域模型中不是反模式。</span><span class="sxs-lookup"><span data-stu-id="25e0c-148">If the microservice you are creating is simple enough (for example, a CRUD service), following the anemic domain model it is not an anti-pattern.</span></span> <span data-ttu-id="25e0c-149">但是，如果你需要为处理独特的微服务构成的域中具有大量不断变化的业务规则的复杂性，贫乏域模型可能会为该 microservice 或绑定上下文反模式。</span><span class="sxs-lookup"><span data-stu-id="25e0c-149">However, if you need to tackle the complexity of a microservice’s domain that has a lot of ever-changing business rules, the anemic domain model might be an anti-pattern for that microservice or Bounded Context.</span></span> <span data-ttu-id="25e0c-150">在这种情况下，将其设计为丰富的模型包含的数据以及行为，以及实现其他 DDD 模式 （聚合、 值对象等） 的实体可能具有长期成功的微服务构成的巨大优势。</span><span class="sxs-lookup"><span data-stu-id="25e0c-150">In that case, designing it as a rich model with entities containing data plus behavior as well as implementing additional DDD patterns (aggregates, value objects, etc.) might have huge benefits for the long-term success of such a microservice.</span></span>

#### <a name="additional-resources"></a><span data-ttu-id="25e0c-151">其他资源</span><span class="sxs-lookup"><span data-stu-id="25e0c-151">Additional resources</span></span>

-   <span data-ttu-id="25e0c-152">**DevIQ。域实体**
    [*http://deviq.com/entity/*](http://deviq.com/entity/)</span><span class="sxs-lookup"><span data-stu-id="25e0c-152">**DevIQ. Domain Entity**
[*http://deviq.com/entity/*](http://deviq.com/entity/)</span></span>

-   <span data-ttu-id="25e0c-153">**Martin Fowler。域模型**
    [*https://martinfowler.com/eaaCatalog/domainModel.html*](https://martinfowler.com/eaaCatalog/domainModel.html)</span><span class="sxs-lookup"><span data-stu-id="25e0c-153">**Martin Fowler. The Domain Model**
[*https://martinfowler.com/eaaCatalog/domainModel.html*](https://martinfowler.com/eaaCatalog/domainModel.html)</span></span>

-   <span data-ttu-id="25e0c-154">**Martin Fowler。贫乏域模型**</span><span class="sxs-lookup"><span data-stu-id="25e0c-154">**Martin Fowler. The Anemic Domain Model**</span></span>

    <span data-ttu-id="25e0c-155"><https://martinfowler.com/bliki/AnemicDomainModel.html></span><span class="sxs-lookup"><span data-stu-id="25e0c-155"><https://martinfowler.com/bliki/AnemicDomainModel.html></span></span>

### <a name="the-value-object-pattern"></a><span data-ttu-id="25e0c-156">值对象模式</span><span class="sxs-lookup"><span data-stu-id="25e0c-156">The Value Object pattern</span></span>

<span data-ttu-id="25e0c-157">如 Eric Evans 已经注意到，"许多对象没有概念的标识。</span><span class="sxs-lookup"><span data-stu-id="25e0c-157">As Eric Evans has noted, “Many objects do not have conceptual identity.</span></span> <span data-ttu-id="25e0c-158">这些对象描述一件事情某些的特征"。</span><span class="sxs-lookup"><span data-stu-id="25e0c-158">These objects describe certain characteristics of a thing.”</span></span>

<span data-ttu-id="25e0c-159">实体需要有标识，但不是这样做，系统中有多个对象与值对象模式。</span><span class="sxs-lookup"><span data-stu-id="25e0c-159">An entity requires an identity, but there are many objects in a system that do not, like the Value Object pattern.</span></span> <span data-ttu-id="25e0c-160">值对象是具有描述域方面没有概念标识的对象。</span><span class="sxs-lookup"><span data-stu-id="25e0c-160">A value object is an object with no conceptual identity that describes a domain aspect.</span></span> <span data-ttu-id="25e0c-161">这些是在实例化来表示仅暂时有关你的设计元素的对象。</span><span class="sxs-lookup"><span data-stu-id="25e0c-161">These are objects that you instantiate to represent design elements that only concern you temporarily.</span></span> <span data-ttu-id="25e0c-162">你关注*什么*它们是，不*人员*它们。</span><span class="sxs-lookup"><span data-stu-id="25e0c-162">You care about *what* they are, not *who* they are.</span></span> <span data-ttu-id="25e0c-163">示例包括数字和字符串，但也可以是类似的特性组的更高级别的概念。</span><span class="sxs-lookup"><span data-stu-id="25e0c-163">Examples include numbers and strings, but can also be higher-level concepts like groups of attributes.</span></span>

<span data-ttu-id="25e0c-164">因为在第二个情况下，绑定上下文可能具有不同的含义，这一点微服务中的实体可能不是另一个微服务中的实体。</span><span class="sxs-lookup"><span data-stu-id="25e0c-164">Something that is an entity in a microservice might not be an entity in another microservice, because in the second case, the Bounded Context might have a different meaning.</span></span> <span data-ttu-id="25e0c-165">例如，电子商务应用程序中的地址可能没有标识，因为它也可以仅表示一组个人或公司的客户的配置文件的属性。</span><span class="sxs-lookup"><span data-stu-id="25e0c-165">For example, an address in an e-commerce application might not have an identity at all, since it might only represent a group of attributes of the customer’s profile for a person or company.</span></span> <span data-ttu-id="25e0c-166">在这种情况下，该地址应归类为值对象。</span><span class="sxs-lookup"><span data-stu-id="25e0c-166">In this case, the address should be classified as a value object.</span></span> <span data-ttu-id="25e0c-167">但是，电力实用工具公司的应用程序，客户地址可能是重要的业务领域。</span><span class="sxs-lookup"><span data-stu-id="25e0c-167">However, in an application for an electric power utility company, the customer address could be important for the business domain.</span></span> <span data-ttu-id="25e0c-168">因此，该地址必须具有一个标识，因此计费系统可以直接链接到的地址。</span><span class="sxs-lookup"><span data-stu-id="25e0c-168">Therefore, the address must have an identity so the billing system can be directly linked to the address.</span></span> <span data-ttu-id="25e0c-169">在这种情况下，一个地址应归类为域实体。</span><span class="sxs-lookup"><span data-stu-id="25e0c-169">In that case, an address should be classified as a domain entity.</span></span>

<span data-ttu-id="25e0c-170">具有名称和姓氏的用户通常是一个实体由于个人具有标识，即使与另一组值的名称和姓氏同时发生，例如，如果这些名称还指另一个人。</span><span class="sxs-lookup"><span data-stu-id="25e0c-170">A person with a name and surname is usually an entity because a person has identity, even if the name and surname coincide with another set of values, such as if those names also refers to a different person.</span></span>

<span data-ttu-id="25e0c-171">值对象难以管理中的关系数据库和 EF，如 Orm 而文档中面向它们是更轻松地实现和使用的数据库。</span><span class="sxs-lookup"><span data-stu-id="25e0c-171">Value objects are hard to manage in relational databases and ORMs like EF, whereas in document oriented databases they are easier to implement and use.</span></span>

#### <a name="additional-resources"></a><span data-ttu-id="25e0c-172">其他资源</span><span class="sxs-lookup"><span data-stu-id="25e0c-172">Additional resources</span></span>

-   <span data-ttu-id="25e0c-173">**Martin Fowler。值对象模式**
    [*https://martinfowler.com/bliki/ValueObject.html*](https://martinfowler.com/bliki/ValueObject.html)</span><span class="sxs-lookup"><span data-stu-id="25e0c-173">**Martin Fowler. Value Object pattern**
[*https://martinfowler.com/bliki/ValueObject.html*](https://martinfowler.com/bliki/ValueObject.html)</span></span>

-   <span data-ttu-id="25e0c-174">**值对象**
    [*http://deviq.com/value-object/*](http://deviq.com/value-object/)</span><span class="sxs-lookup"><span data-stu-id="25e0c-174">**Value Object**
[*http://deviq.com/value-object/*](http://deviq.com/value-object/)</span></span>

-   <span data-ttu-id="25e0c-175">**值 Test-Driven 开发中的对象**
    [*https://leanpub.com/tdd-ebook/read\#leanpub 自动值对象*](https://leanpub.com/tdd-ebook/read#leanpub-auto-value-objects)</span><span class="sxs-lookup"><span data-stu-id="25e0c-175">**Value Objects in Test-Driven Development**
[*https://leanpub.com/tdd-ebook/read\#leanpub-auto-value-objects*](https://leanpub.com/tdd-ebook/read#leanpub-auto-value-objects)</span></span>

-   <span data-ttu-id="25e0c-176">**Eric Evans。域驱动的设计： 解决软件核心的复杂性。**</span><span class="sxs-lookup"><span data-stu-id="25e0c-176">**Eric Evans. Domain-Driven Design: Tackling Complexity in the Heart of Software.**</span></span> <span data-ttu-id="25e0c-177">（本书; 包括的值对象的讨论）[ *https://www.amazon.com/Domain-Driven-Design-Tackling-Complexity-Software/dp/0321125215/*](https://www.amazon.com/Domain-Driven-Design-Tackling-Complexity-Software/dp/0321125215/)</span><span class="sxs-lookup"><span data-stu-id="25e0c-177">(Book; includes a discussion of value objects) [*https://www.amazon.com/Domain-Driven-Design-Tackling-Complexity-Software/dp/0321125215/*](https://www.amazon.com/Domain-Driven-Design-Tackling-Complexity-Software/dp/0321125215/)</span></span>

### <a name="the-aggregate-pattern"></a><span data-ttu-id="25e0c-178">聚合模式</span><span class="sxs-lookup"><span data-stu-id="25e0c-178">The Aggregate pattern</span></span>

<span data-ttu-id="25e0c-179">域模型包含不同的数据实体和可以控制功能，如顺序执行或清单的重要区域的进程的群集。</span><span class="sxs-lookup"><span data-stu-id="25e0c-179">A domain model contains clusters of different data entities and processes that can control a significant area of functionality, such as order fulfilment or inventory.</span></span> <span data-ttu-id="25e0c-180">更细粒度的 DDD 单位是聚合计算，其中介绍了的群集或组的实体和被视为凝聚力单元的行为。</span><span class="sxs-lookup"><span data-stu-id="25e0c-180">A more fine-grained DDD unit is the aggregate, which describes a cluster or group of entities and behaviors that can be treated as a cohesive unit.</span></span>

<span data-ttu-id="25e0c-181">通常定义基于所需的事务的聚合。</span><span class="sxs-lookup"><span data-stu-id="25e0c-181">You usually define an aggregate based on the transactions that you need.</span></span> <span data-ttu-id="25e0c-182">一个典型示例是也包含订单项的列表顺序。</span><span class="sxs-lookup"><span data-stu-id="25e0c-182">A classic example is an order that also contains a list of order items.</span></span> <span data-ttu-id="25e0c-183">订单项通常为实体。</span><span class="sxs-lookup"><span data-stu-id="25e0c-183">An order item will usually be an entity.</span></span> <span data-ttu-id="25e0c-184">但是，它将顺序聚合，还将包含作为其根实体，通常称为聚合根的订单实体中的一个子实体。</span><span class="sxs-lookup"><span data-stu-id="25e0c-184">But it will be a child entity within the order aggregate, which will also contain the order entity as its root entity, typically called an aggregate root.</span></span>

<span data-ttu-id="25e0c-185">标识聚合会感到不便。</span><span class="sxs-lookup"><span data-stu-id="25e0c-185">Identifying aggregates can be hard.</span></span> <span data-ttu-id="25e0c-186">聚合是一组一起使用，必须使用相同的对象，但你无法只选择一组对象并将其标记聚合。</span><span class="sxs-lookup"><span data-stu-id="25e0c-186">An aggregate is a group of objects that must be consistent together, but you cannot just pick a group of objects and label them an aggregate.</span></span> <span data-ttu-id="25e0c-187">您必须首先域概念，考虑到这一概念相关的最常见事务中使用的实体。</span><span class="sxs-lookup"><span data-stu-id="25e0c-187">You must start with a domain concept and think about the entities that are used in the most common transactions related to that concept.</span></span> <span data-ttu-id="25e0c-188">需要事务上一致的那些实体是什么窗体聚合。</span><span class="sxs-lookup"><span data-stu-id="25e0c-188">Those entities that need to be transactionally consistent are what forms an aggregate.</span></span> <span data-ttu-id="25e0c-189">考虑事务操作可能是标识聚合的最佳方法。</span><span class="sxs-lookup"><span data-stu-id="25e0c-189">Thinking about transaction operations is probably the best way to identify aggregates.</span></span>

### <a name="the-aggregate-root-or-root-entity-pattern"></a><span data-ttu-id="25e0c-190">聚合根或根实体模式</span><span class="sxs-lookup"><span data-stu-id="25e0c-190">The Aggregate Root or Root Entity pattern</span></span>

<span data-ttu-id="25e0c-191">聚合组成，至少一个实体： 也称为根实体或主 ientity 的聚合根。</span><span class="sxs-lookup"><span data-stu-id="25e0c-191">An aggregate is composed of at least one entity: the aggregate root, also called root entity or primary ientity.</span></span> <span data-ttu-id="25e0c-192">此外，它可具有多个子实体和值对象，包含所有实体和协同工作以便实现所需的行为和事务的对象。</span><span class="sxs-lookup"><span data-stu-id="25e0c-192">Additionally, it can have multiple child entities and value objects, with all entities and objects working together to implement required behavior and transactions.</span></span>

<span data-ttu-id="25e0c-193">聚合根的目的是确保聚合; 的一致性它应为通过方法对聚合的更新的唯一入口点，或者操作在聚合根类。</span><span class="sxs-lookup"><span data-stu-id="25e0c-193">The purpose of an aggregate root is to ensure the consistency of the aggregate; it should be the only entry point for updates to the aggregate through methods or operations in the aggregate root class.</span></span> <span data-ttu-id="25e0c-194">你应更改仅通过聚合根聚合内的实体。</span><span class="sxs-lookup"><span data-stu-id="25e0c-194">You should make changes to entities within the aggregate only via the aggregate root.</span></span> <span data-ttu-id="25e0c-195">它是聚合的一致性的保护者，考虑到所有固定条件及可能需要符合你聚合中的一致性规则。</span><span class="sxs-lookup"><span data-stu-id="25e0c-195">It is the aggregate’s consistency guardian, taking into account all the invariants and consistency rules you might need to comply with in your aggregate.</span></span> <span data-ttu-id="25e0c-196">如果更改了独立的子实体或值对象，聚合的根不能确保聚合处于有效状态。</span><span class="sxs-lookup"><span data-stu-id="25e0c-196">If you change a child entity or value object independently, the aggregate root cannot ensure that the aggregate is in a valid state.</span></span> <span data-ttu-id="25e0c-197">它就好像具有松散路线的表。</span><span class="sxs-lookup"><span data-stu-id="25e0c-197">It would be like a table with a loose leg.</span></span> <span data-ttu-id="25e0c-198">维护一致性是聚合根的主要用途。</span><span class="sxs-lookup"><span data-stu-id="25e0c-198">Maintaining consistency is the main purpose of the aggregate root.</span></span>

<span data-ttu-id="25e0c-199">在图 9-9 中，你可以看到 buyer 聚合，其中包含单个实体 （聚合根 Buyer） 类似的示例聚合。</span><span class="sxs-lookup"><span data-stu-id="25e0c-199">In Figure 9-9, you can see sample aggregates like the buyer aggregate, which contains a single entity (the aggregate root Buyer).</span></span> <span data-ttu-id="25e0c-200">顺序聚合包含多个实体和值对象。</span><span class="sxs-lookup"><span data-stu-id="25e0c-200">The order aggregate contains multiple entities and a value object.</span></span>

![](./media/image10.png)

<span data-ttu-id="25e0c-201">**图 9-9**。</span><span class="sxs-lookup"><span data-stu-id="25e0c-201">**Figure 9-9**.</span></span> <span data-ttu-id="25e0c-202">使用多个聚合函数的示例或单个实体</span><span class="sxs-lookup"><span data-stu-id="25e0c-202">Example of aggregates with multiple or single entities</span></span>

<span data-ttu-id="25e0c-203">请注意，Buyer 聚合无法其他子实体，具体取决于你的域，eShopOnContainers 引用应用程序中排序的微服务中的一样。</span><span class="sxs-lookup"><span data-stu-id="25e0c-203">Note that the Buyer aggregate could have additional child entities, depending on your domain, as it does in the ordering microservice in the eShopOnContainers reference application.</span></span> <span data-ttu-id="25e0c-204">图 9-9 只阐释了在其中买家单个实体，已作为示例，了解包含仅聚合根的聚合的情况。</span><span class="sxs-lookup"><span data-stu-id="25e0c-204">Figure 9-9 just illustrates a case in which the buyer has a single entity, as an example of an aggregate that contains only an aggregate root.</span></span>

<span data-ttu-id="25e0c-205">在 DDD 域模型中不允许直接导航之间聚合并仅具有外键 (FK) 字段中，实现的一样好的做法是为了维护的聚合的分离，并保留它们间的清晰边界，请[排序 microservice 域模型](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.Domain/AggregatesModel/OrderAggregate/Order.cs)eShopOnContainers 中。</span><span class="sxs-lookup"><span data-stu-id="25e0c-205">In order to maintain separation of aggregates and keep clear boundaries between them, it is a good practice in a DDD domain model to disallow direct navigation between aggregates and only having the foreign key (FK) field, as implemented in the [Ordering microservice domain model](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.Domain/AggregatesModel/OrderAggregate/Order.cs) in eShopOnContainers.</span></span> <span data-ttu-id="25e0c-206">订单实体只有 FK 字段 buyer，但不是 EF 核心导航属性，如下面的代码中所示：</span><span class="sxs-lookup"><span data-stu-id="25e0c-206">The Order entity only has a FK field for the buyer, but not an EF Core navigation property, as shown in the following code:</span></span>

```csharp
public class Order : Entity, IAggregateRoot
{
    private DateTime _orderDate;
    public Address Address { get; private set; }
    private int? _buyerId; //FK pointing to a different aggregate root
    public OrderStatus OrderStatus { get; private set; }
}
```

<span data-ttu-id="25e0c-207">标识和使用聚合需要研究和体验。</span><span class="sxs-lookup"><span data-stu-id="25e0c-207">Identifying and working with aggregates requires research and experience.</span></span> <span data-ttu-id="25e0c-208">有关详细信息，请参阅以下的其他资源列表。</span><span class="sxs-lookup"><span data-stu-id="25e0c-208">For more information, see the following Additional resources list.</span></span>

#### <a name="additional-resources"></a><span data-ttu-id="25e0c-209">其他资源</span><span class="sxs-lookup"><span data-stu-id="25e0c-209">Additional resources</span></span>

-   <span data-ttu-id="25e0c-210">**Vaughn Vernon。有效的聚合设计的一部分： 建模单个聚合**
    [*https://vaughnvernon.co/wordpress/wp-content/uploads/2014/10/DDD\_社区\_论述\_聚合\_一部分\_1.pdf*](https://vaughnvernon.co/wordpress/wp-content/uploads/2014/10/DDD_COMMUNITY_ESSAY_AGGREGATES_PART_1.pdf)</span><span class="sxs-lookup"><span data-stu-id="25e0c-210">**Vaughn Vernon. Effective Aggregate Design - Part I: Modeling a Single Aggregate**
[*https://vaughnvernon.co/wordpress/wp-content/uploads/2014/10/DDD\_COMMUNITY\_ESSAY\_AGGREGATES\_PART\_1.pdf*](https://vaughnvernon.co/wordpress/wp-content/uploads/2014/10/DDD_COMMUNITY_ESSAY_AGGREGATES_PART_1.pdf)</span></span>

-   <span data-ttu-id="25e0c-211">**Vaughn Vernon。有效的聚合设计的第二部分： 进行聚合工作一起**
    *<https://vaughnvernon.co/wordpress/wp-content/uploads/2014/10/DDD_COMMUNITY_ESSAY_AGGREGATES_PART_2.pdf>*</span><span class="sxs-lookup"><span data-stu-id="25e0c-211">**Vaughn Vernon. Effective Aggregate Design - Part II: Making Aggregates Work Together**
*<https://vaughnvernon.co/wordpress/wp-content/uploads/2014/10/DDD_COMMUNITY_ESSAY_AGGREGATES_PART_2.pdf> *</span></span>

-   <span data-ttu-id="25e0c-212">**Vaughn Vernon。有效的聚合设计的第三部分： 深入探索通过发现**
    *<https://vaughnvernon.co/wordpress/wp-content/uploads/2014/10/DDD_COMMUNITY_ESSAY_AGGREGATES_PART_3.pdf>*</span><span class="sxs-lookup"><span data-stu-id="25e0c-212">**Vaughn Vernon. Effective Aggregate Design - Part III: Gaining Insight Through Discovery**
*<https://vaughnvernon.co/wordpress/wp-content/uploads/2014/10/DDD_COMMUNITY_ESSAY_AGGREGATES_PART_3.pdf> *</span></span>

-   <span data-ttu-id="25e0c-213">**Sergey Grybniak。DDD 战术性设计模式**
    [*https://www.codeproject.com/Articles/1164363/Domain-Driven-Design-Tactical-Design-Patterns-Part*](https://www.codeproject.com/Articles/1164363/Domain-Driven-Design-Tactical-Design-Patterns-Part)</span><span class="sxs-lookup"><span data-stu-id="25e0c-213">**Sergey Grybniak. DDD Tactical Design Patterns**
[*https://www.codeproject.com/Articles/1164363/Domain-Driven-Design-Tactical-Design-Patterns-Part*](https://www.codeproject.com/Articles/1164363/Domain-Driven-Design-Tactical-Design-Patterns-Part)</span></span>

-   <span data-ttu-id="25e0c-214">**Chris Richardson。开发使用聚合的事务微服务**
    [*https://www.infoq.com/articles/microservices-aggregates-events-cqrs-part-1-richardson*](https://www.infoq.com/articles/microservices-aggregates-events-cqrs-part-1-richardson)</span><span class="sxs-lookup"><span data-stu-id="25e0c-214">**Chris Richardson. Developing Transactional Microservices Using Aggregates**
[*https://www.infoq.com/articles/microservices-aggregates-events-cqrs-part-1-richardson*](https://www.infoq.com/articles/microservices-aggregates-events-cqrs-part-1-richardson)</span></span>

-   <span data-ttu-id="25e0c-215">**DevIQ。聚合模式**
    [*http://deviq.com/aggregate-pattern/*](http://deviq.com/aggregate-pattern/)</span><span class="sxs-lookup"><span data-stu-id="25e0c-215">**DevIQ. The Aggregate pattern**
[*http://deviq.com/aggregate-pattern/*](http://deviq.com/aggregate-pattern/)</span></span>


>[!div class="step-by-step"]
<span data-ttu-id="25e0c-216">[以前](ddd-面向-microservice.md) [下一步] (net-核心-微服务构成的域-model.md)</span><span class="sxs-lookup"><span data-stu-id="25e0c-216">[Previous] (ddd-oriented-microservice.md) [Next] (net-core-microservice-domain-model.md)</span></span>
