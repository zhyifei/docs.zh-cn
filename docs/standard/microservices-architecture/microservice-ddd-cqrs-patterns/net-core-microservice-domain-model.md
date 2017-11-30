---
title: "实现 microservice 域模型与.NET 核心"
description: "为容器化的.NET 应用程序的.NET 微服务体系结构 |实现 microservice 域模型与.NET 核心"
keywords: "Docker, 微服务, ASP.NET, 容器"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: 26c480a82ad7bb806734decebdfbe5b4a07998e6
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="implementing-a-microservice-domain-model-with-net-core"></a><span data-ttu-id="dfc1e-104">实现 microservice 域模型与.NET 核心</span><span class="sxs-lookup"><span data-stu-id="dfc1e-104">Implementing a microservice domain model with .NET Core</span></span> 

<span data-ttu-id="dfc1e-105">在上一节中所述的基本设计原则和设计域模型的模式。</span><span class="sxs-lookup"><span data-stu-id="dfc1e-105">In the previous section, the fundamental design principles and patterns for designing a domain model were explained.</span></span> <span data-ttu-id="dfc1e-106">现在就可以了解可能的方式实现域模型中使用.NET Core (纯 C\#代码) 和 EF 核心。</span><span class="sxs-lookup"><span data-stu-id="dfc1e-106">Now it is time to explore possible ways to implement the domain model by using .NET Core (plain C\# code) and EF Core.</span></span> <span data-ttu-id="dfc1e-107">请注意您的域模型将只需组成你的代码。</span><span class="sxs-lookup"><span data-stu-id="dfc1e-107">Note that your domain model will be composed simply of your code.</span></span> <span data-ttu-id="dfc1e-108">它将在 EF 上具有只 EF 核心模型要求，但不是实际依赖关系。</span><span class="sxs-lookup"><span data-stu-id="dfc1e-108">It will have just the EF Core model requirements, but not real dependencies on EF.</span></span> <span data-ttu-id="dfc1e-109">不应在你的域模型中具有的硬依赖项或对 EF 核心或其他 ORM 的引用。</span><span class="sxs-lookup"><span data-stu-id="dfc1e-109">You should not have hard dependencies or references to EF Core or any other ORM in your domain model.</span></span>

## <a name="domain-model-structure-in-a-custom-net-standard-library"></a><span data-ttu-id="dfc1e-110">自定义的标准.NET 库中的域模型结构</span><span class="sxs-lookup"><span data-stu-id="dfc1e-110">Domain model structure in a custom .NET Standard library</span></span>

<span data-ttu-id="dfc1e-111">用于 eShopOnContainers 引用应用程序的文件夹组织演示应用程序的 DDD 模型。</span><span class="sxs-lookup"><span data-stu-id="dfc1e-111">The folder organization used for the eShopOnContainers reference application demonstrates the DDD model for the application.</span></span> <span data-ttu-id="dfc1e-112">您可能发现不同文件夹组织更清楚地进行通信的应用程序所做的设计选择。</span><span class="sxs-lookup"><span data-stu-id="dfc1e-112">You might find that a different folder organization more clearly communicates the design choices made for your application.</span></span> <span data-ttu-id="dfc1e-113">正如您可以看到图 9-10，排序的域模型中有两个聚合，顺序聚合和 buyer 聚合。</span><span class="sxs-lookup"><span data-stu-id="dfc1e-113">As you can see in Figure 9-10, in the ordering domain model there are two aggregates, the order aggregate and the buyer aggregate.</span></span> <span data-ttu-id="dfc1e-114">每个聚合是一组域实体和值对象，但您可以对聚合以及组成的单一域实体 （聚合根或根实体）。</span><span class="sxs-lookup"><span data-stu-id="dfc1e-114">Each aggregate is a group of domain entities and value objects, although you could have an aggregate composed of a single domain entity (the aggregate root or root entity) as well.</span></span>

![](./media/image11.png)

<span data-ttu-id="dfc1e-115">**图 9-10**。</span><span class="sxs-lookup"><span data-stu-id="dfc1e-115">**Figure 9-10**.</span></span> <span data-ttu-id="dfc1e-116">在 eShopOnContainers 排序微服务构成的域模型结构</span><span class="sxs-lookup"><span data-stu-id="dfc1e-116">Domain model structure for the ordering microservice in eShopOnContainers</span></span>

<span data-ttu-id="dfc1e-117">此外，域模型层包括是您的域模型的基础结构要求的存储库协定 （接口）。</span><span class="sxs-lookup"><span data-stu-id="dfc1e-117">Additionally, the domain model layer includes the repository contracts (interfaces) that are the infrastructure requirements of your domain model.</span></span> <span data-ttu-id="dfc1e-118">换而言之，这些接口 express 基础结构层必须实现哪些存储库以及如何。</span><span class="sxs-lookup"><span data-stu-id="dfc1e-118">In other words, these interfaces express what repositories the infrastructure layer must implement and how.</span></span> <span data-ttu-id="dfc1e-119">很重要的存储库实现放置之外的域模型层，基础结构层库，所以，域模型层不"污染"通过 API 或从基础结构技术，如实体框架的类。</span><span class="sxs-lookup"><span data-stu-id="dfc1e-119">It is critical that the implementation of the repositories be placed outside of the domain model layer, in the infrastructure layer library, so the domain model layer is not “contaminated” by API or classes from infrastructure technologies, like Entity Framework.</span></span>

<span data-ttu-id="dfc1e-120">你还可以看到[SeedWork](https://martinfowler.com/bliki/Seedwork.html)包含可以用作基础域实体和值的自定义基类文件夹对象，因此你不需要在每个域的对象类冗余代码。</span><span class="sxs-lookup"><span data-stu-id="dfc1e-120">You can also see a [SeedWork](https://martinfowler.com/bliki/Seedwork.html) folder that contains custom base classes that you can use as a base for your domain entities and value objects, so you do not have redundant code in each domain’s object class.</span></span>

## <a name="structuring-aggregates-in-a-custom-net-standard-library"></a><span data-ttu-id="dfc1e-121">构造一个自定义的标准.NET 库中的聚合函数</span><span class="sxs-lookup"><span data-stu-id="dfc1e-121">Structuring aggregates in a custom .NET Standard library</span></span>

<span data-ttu-id="dfc1e-122">聚合是指组合在一起以匹配事务一致性的域对象的群集。</span><span class="sxs-lookup"><span data-stu-id="dfc1e-122">An aggregate refers to a cluster of domain objects grouped together to match transactional consistency.</span></span> <span data-ttu-id="dfc1e-123">这些对象可能是加上任何其他值对象 （其中之一是聚合根或根实体） 的实体的实例。</span><span class="sxs-lookup"><span data-stu-id="dfc1e-123">Those objects could be instances of entities (one of which is the aggregate root or root entity) plus any additional value objects.</span></span>

<span data-ttu-id="dfc1e-124">事务一致性意味着聚合保证一致且最新的业务操作的末尾。</span><span class="sxs-lookup"><span data-stu-id="dfc1e-124">Transactional consistency means that an aggregate is guaranteed to be consistent and up to date at the end of a business action.</span></span> <span data-ttu-id="dfc1e-125">例如，从排序 microservice 域模型 eShopOnContainers 顺序聚合由构成图 9-11 中所示。</span><span class="sxs-lookup"><span data-stu-id="dfc1e-125">For example, the order aggregate from the eShopOnContainers ordering microservice domain model is composed as shown in Figure 9-11.</span></span>

![](./media/image12.png)

<span data-ttu-id="dfc1e-126">**图 9-11**。</span><span class="sxs-lookup"><span data-stu-id="dfc1e-126">**Figure 9-11**.</span></span> <span data-ttu-id="dfc1e-127">在 Visual Studio 解决方案聚合顺序</span><span class="sxs-lookup"><span data-stu-id="dfc1e-127">The order aggregate in Visual Studio solution</span></span>

<span data-ttu-id="dfc1e-128">如果在聚合文件夹中打开的任何文件，你可以看到如何标记为自定义的基类或接口，实体或值与对象一样，当在中实现[Seedwork](https://github.com/dotnet-architecture/eShopOnContainers/tree/master/src/Services/Ordering/Ordering.Domain/SeedWork)文件夹。</span><span class="sxs-lookup"><span data-stu-id="dfc1e-128">If you open any of the files in an aggregate folder, you can see how it is marked as either a custom base class or interface, like entity or value object, as implemented in the [Seedwork](https://github.com/dotnet-architecture/eShopOnContainers/tree/master/src/Services/Ordering/Ordering.Domain/SeedWork) folder.</span></span>

## <a name="implementing-domain-entities-as-poco-classes"></a><span data-ttu-id="dfc1e-129">实现域实体作为 POCO 类</span><span class="sxs-lookup"><span data-stu-id="dfc1e-129">Implementing domain entities as POCO classes</span></span>

<span data-ttu-id="dfc1e-130">在.NET 中实现域模型，通过创建实现你的域实体的 POCO 类。</span><span class="sxs-lookup"><span data-stu-id="dfc1e-130">You implement a domain model in .NET by creating POCO classes that implement your domain entities.</span></span> <span data-ttu-id="dfc1e-131">以下示例中，在 Order 类定义实体，而且还为聚合根。</span><span class="sxs-lookup"><span data-stu-id="dfc1e-131">In the following example, the Order class is defined as an entity and also as an aggregate root.</span></span> <span data-ttu-id="dfc1e-132">由于 Order 类派生自的实体的基类，它可以重复使用与实体相关的常见代码。</span><span class="sxs-lookup"><span data-stu-id="dfc1e-132">Because the Order class derives from the Entity base class, it can reuse common code related to entities.</span></span> <span data-ttu-id="dfc1e-133">请记住，这些基类，这些类和接口都由你在域模型项目中，因此它是你的代码、 不是从如 EF ORM 的基础结构代码。</span><span class="sxs-lookup"><span data-stu-id="dfc1e-133">Bear in mind that these base classes and interfaces are defined by you in the domain model project, so it is your code, not infrastructure code from an ORM like EF.</span></span>

```csharp
// COMPATIBLE WITH ENTITY FRAMEWORK CORE 1.0
// Entity is a custom base class with the ID
public class Order : Entity, IAggregateRoot
{
    public int BuyerId { get; private set; }
    public DateTime OrderDate { get; private set; }
    public int StatusId { get; private set; }
    public ICollection<OrderItem> OrderItems { get; private set; }
    public Address ShippingAddress { get; private set; }
    public int PaymentId { get; private set; }
    protected Order() { } //Design constraint needed only by EF Core
    public Order(int buyerId, int paymentId)
    {
        BuyerId = buyerId;
        PaymentId = paymentId;
        StatusId = OrderStatus.InProcess.Id;
        OrderDate = DateTime.UtcNow;
        OrderItems = new List<OrderItem>();
    }

    public void AddOrderItem(productName,
        pictureUrl,
        unitPrice,
        discount,
        units)
    {
        //...
        // Domain rules/logic for adding the OrderItem to the order
        // ...
        OrderItem item = new OrderItem(this.Id, ProductId, productName,
            pictureUrl, unitPrice, discount, units);
  
        OrderItems.Add(item);
    }
    // ...
    // Additional methods with domain rules/logic related to the Order aggregate
    // ...
}
```

<span data-ttu-id="dfc1e-134">请务必注意这是作为 POCO 类实现一个域实体。</span><span class="sxs-lookup"><span data-stu-id="dfc1e-134">It is important to note that this is a domain entity implemented as a POCO class.</span></span> <span data-ttu-id="dfc1e-135">它没有任何直接依赖于实体框架核心或任何其他基础结构框架。</span><span class="sxs-lookup"><span data-stu-id="dfc1e-135">It does not have any direct dependency on Entity Framework Core or any other infrastructure framework.</span></span> <span data-ttu-id="dfc1e-136">此实现是因为它应该是的只需 C\#实现域模型的代码。</span><span class="sxs-lookup"><span data-stu-id="dfc1e-136">This implementation is as it should be, just C\# code implementing a domain model.</span></span>

<span data-ttu-id="dfc1e-137">此外，类进行了修饰名为 IAggregateRoot 接口。</span><span class="sxs-lookup"><span data-stu-id="dfc1e-137">In addition, the class is decorated with an interface named IAggregateRoot.</span></span> <span data-ttu-id="dfc1e-138">该接口是一个空的接口，有时称为*标记接口*，即只用于指示此实体类还进行聚合根。</span><span class="sxs-lookup"><span data-stu-id="dfc1e-138">That interface is an empty interface, sometimes called a *marker interface*, that is used just to indicate that this entity class is also an aggregate root.</span></span>

<span data-ttu-id="dfc1e-139">一种标记接口有时视为反模式;但是，还有一种标记类，该接口可能会不断发展时尤其是干净方式。</span><span class="sxs-lookup"><span data-stu-id="dfc1e-139">A marker interface is sometimes considered as an anti-pattern; however, it is also a clean way to mark a class, especially when that interface might be evolving.</span></span> <span data-ttu-id="dfc1e-140">属性可以标记，另一个选择但不要在上面类聚合特性标记的 IAggregate 接口旁边看到的基类 （实体） 速度更快。</span><span class="sxs-lookup"><span data-stu-id="dfc1e-140">An attribute could be the other choice for the marker, but it is quicker to see the base class (Entity) next to the IAggregate interface instead of putting an Aggregate attribute marker above the class.</span></span> <span data-ttu-id="dfc1e-141">它在任何情况下是首选项，metter。</span><span class="sxs-lookup"><span data-stu-id="dfc1e-141">It is a metter of preferences, in any case.</span></span>

<span data-ttu-id="dfc1e-142">具有聚合根表示与一致性相关的大部分代码，应作为 Order 聚合根类 (例如，AddOrderItem OrderItem 对象添加到聚合时) 中的方法实现的聚合的实体的业务规则.</span><span class="sxs-lookup"><span data-stu-id="dfc1e-142">Having an aggregate root means that most of the code related to consistency and business rules of the aggregate’s entities should be implemented as methods in the Order aggregate root class (for example, AddOrderItem when adding an OrderItem object to the aggregate).</span></span> <span data-ttu-id="dfc1e-143">不应该创建或更新 OrderItems 对象独立或直接调用控件和任何更新操作针对其子实体的一致性，必须保持 AggregateRoot 类。</span><span class="sxs-lookup"><span data-stu-id="dfc1e-143">You should not create or update OrderItems objects independently or directly; the AggregateRoot class must keep control and consistency of any update operation against its child entities.</span></span>

<span data-ttu-id="dfc1e-144">例如，你应*不*执行以下操作，从任何命令处理程序方法或应用程序层类：</span><span class="sxs-lookup"><span data-stu-id="dfc1e-144">For example, you should *not* do the following from any command handler method or application layer class:</span></span>

```csharp
// WRONG ACCORDING TO DDD PATTERNS – CODE AT THE APPLICATION LAYER OR
// COMMAND HANDLERS
// Code in command handler methods or Web API controllers
//... (WRONG) Some code with business logic out of the domain classes ...
OrderItem myNewOrderItem = new OrderItem(orderId, productId, productName,
    pictureUrl, unitPrice, discount, units);

//... (WRONG) Accessing the OrderItems colletion directly from the application layer // or command handlers
myOrder.OrderItems.Add(myNewOrderItem);
//...
```

<span data-ttu-id="dfc1e-145">在这种情况下，添加方法是只是一个操作以添加具有对 OrderItems 集合的直接访问数据。</span><span class="sxs-lookup"><span data-stu-id="dfc1e-145">In this case, the Add method is purely an operation to add data, with direct access to the OrderItems collection.</span></span> <span data-ttu-id="dfc1e-146">因此，大部分域逻辑、 规则或验证与相关的子实体的操作将能跨越应用程序层 （命令处理程序和 Web API 控制器）。</span><span class="sxs-lookup"><span data-stu-id="dfc1e-146">Therefore, most of the domain logic, rules, or validations related to that operation with the child entities will be spread across the application layer (command handlers and Web API controllers).</span></span>

<span data-ttu-id="dfc1e-147">如果你转围绕聚合根，聚合根无法保证其固定协定，其有效性或其一致性。</span><span class="sxs-lookup"><span data-stu-id="dfc1e-147">If you go around the aggregate root, the aggregate root cannot guarantee its invariants, its validity, or its consistency.</span></span> <span data-ttu-id="dfc1e-148">最终你将拥有复式代码或事务的脚本代码。</span><span class="sxs-lookup"><span data-stu-id="dfc1e-148">Eventually you will have spaghetti code or transactional script code.</span></span>

<span data-ttu-id="dfc1e-149">若要执行 DDD 模式，实体不能与公共 setter 中的任何实体属性。</span><span class="sxs-lookup"><span data-stu-id="dfc1e-149">To follow DDD patterns, entities must not have public setters in any entity property.</span></span> <span data-ttu-id="dfc1e-150">应通过显式方法显式无处不在语言，它们将执行实体中的更改的相关驱动中实体的更改。</span><span class="sxs-lookup"><span data-stu-id="dfc1e-150">Changes in an entity should be driven by explicit methods with explicit ubiquitous language about the change they are performing in the entity.</span></span>

<span data-ttu-id="dfc1e-151">此外，实体 （如订单项中） 中的集合中应为只读属性 （AsReadOnly 方法稍后进行说明）。</span><span class="sxs-lookup"><span data-stu-id="dfc1e-151">Furthermore, collections within the entity (like the order items) should be read-only properties (the AsReadOnly method explained later).</span></span> <span data-ttu-id="dfc1e-152">你应能够更新它只能从在聚合根类方法或子实体方法中。</span><span class="sxs-lookup"><span data-stu-id="dfc1e-152">You should be able to update it only from within the aggregate root class methods or the child entity methods.</span></span>

<span data-ttu-id="dfc1e-153">如你所见顺序聚合根的代码中，所有 setter 应都为 private 或至少是只读的外部使用，以便针对实体的数据或其子实体的任何操作必须通过在实体类的方法执行。</span><span class="sxs-lookup"><span data-stu-id="dfc1e-153">As you can see in the code for the Order aggregate root, all setters should be private or at least read-only externally, so that any operation against the entity’s data or its child entities has to be performed through methods in the entity class.</span></span> <span data-ttu-id="dfc1e-154">这将保持一致性而不是实现事务的脚本代码的受控和面向对象的方式。</span><span class="sxs-lookup"><span data-stu-id="dfc1e-154">This maintains consistency in a controlled and object-oriented way instead of implementing transactional script code.</span></span>

<span data-ttu-id="dfc1e-155">下面的代码段演示代码 OrderItem 对象添加到订单聚合的任务的正确方法。</span><span class="sxs-lookup"><span data-stu-id="dfc1e-155">The following code snippet shows the proper way to code the task of adding an OrderItem object to the Order aggregate.</span></span>

```csharp
// RIGHT ACCORDING TO DDD--CODE AT THE APPLICATION LAYER OR COMMAND HANDLERS
// The code in command handlers or WebAPI controllers, related only to application stuff
// There is NO code here related to OrderItem object’s business logic
myOrder.AddOrderItem(productId, productName, pictureUrl, unitPrice, discount, units);

// The code related to OrderItem params validations or domain rules should
// be WITHIN the AddOrderItem method.

//...
```

<span data-ttu-id="dfc1e-156">在此代码段，大部分验证或与创建 OrderItem 对象相关的逻辑将受控制的顺序聚合根-AddOrderItem 方法中-尤其是验证和逻辑相关的其他元素在聚合。</span><span class="sxs-lookup"><span data-stu-id="dfc1e-156">In this snippet, most of the validations or logic related to the creation of an OrderItem object will be under the control of the Order aggregate root—in the AddOrderItem method—especially validations and logic related to other elements in the aggregate.</span></span> <span data-ttu-id="dfc1e-157">例如，可能会收到相同的产品项作为对 AddOrderItem 的多个调用的结果。</span><span class="sxs-lookup"><span data-stu-id="dfc1e-157">For instance, you might get the same product item as the result of multiple calls to AddOrderItem.</span></span> <span data-ttu-id="dfc1e-158">在该方法中，你可以检查产品项并将相同的产品项整合到单个 OrderItem 对象具有几个单位。</span><span class="sxs-lookup"><span data-stu-id="dfc1e-158">In that method, you could examine the product items and consolidate the same product items into a single OrderItem object with several units.</span></span> <span data-ttu-id="dfc1e-159">此外，如果不同折扣金额，但产品 ID 都相同，你可能会应用更高版本的折扣。</span><span class="sxs-lookup"><span data-stu-id="dfc1e-159">Additionally, if there are different discount amounts but the product ID is the same, you would likely apply the higher discount.</span></span> <span data-ttu-id="dfc1e-160">此原则适用于任何其他域逻辑 OrderItem 对象。</span><span class="sxs-lookup"><span data-stu-id="dfc1e-160">This principle applies to any other domain logic for the OrderItem object.</span></span>

<span data-ttu-id="dfc1e-161">此外，新的 OrderItem(params) 操作将还控制并从顺序聚合根 AddOrderItem 方法执行。</span><span class="sxs-lookup"><span data-stu-id="dfc1e-161">In addition, the new OrderItem(params) operation will also be controlled and performed by the AddOrderItem method from the Order aggregate root.</span></span> <span data-ttu-id="dfc1e-162">因此，大部分逻辑或验证与相关的操作 （尤其是任何内容会影响其他子实体之间的一致性） 将会在聚合根中的单个位置。</span><span class="sxs-lookup"><span data-stu-id="dfc1e-162">Therefore, most of the logic or validations related to that operation (especially anything that impacts the consistency between other child entities) will be in a single place within the aggregate root.</span></span> <span data-ttu-id="dfc1e-163">这是聚合根模式的最终目的。</span><span class="sxs-lookup"><span data-stu-id="dfc1e-163">That is the ultimate purpose of the aggregate root pattern.</span></span>

<span data-ttu-id="dfc1e-164">当你使用 Entity Framework 1.1 时，DDD 实体可以更好地表示因为实体框架核心 1.1 的新功能之一是它允许[将映射到字段](https://docs.microsoft.com/ef/core/modeling/backing-field)除了属性外。</span><span class="sxs-lookup"><span data-stu-id="dfc1e-164">When you use Entity Framework 1.1, a DDD entity can be better expressed because one of the new features of Entity Framework Core 1.1 is that it allows [mapping to fields](https://docs.microsoft.com/ef/core/modeling/backing-field) in addition to properties.</span></span> <span data-ttu-id="dfc1e-165">保护子实体或值对象的集合时，这很有用。</span><span class="sxs-lookup"><span data-stu-id="dfc1e-165">This is useful when protecting collections of child entities or value objects.</span></span> <span data-ttu-id="dfc1e-166">对于此增强功能，你可以使用简单的私有字段，而不是属性，你可以在公共方法中实现任何更新的字段集合和通过 AsReadOnly 方法提供只读访问权限。</span><span class="sxs-lookup"><span data-stu-id="dfc1e-166">With this enhancement, you can use simple private fields instead of properties and you can implement any update to the field collection in public methods and provide read-only access through the AsReadOnly method.</span></span>

<span data-ttu-id="dfc1e-167">在你想要仅通过在实体 （或构造函数），以便控制任何固定和数据的一致性方法更新该实体的 DDD，因此属性定义仅具有一个 get 访问器。</span><span class="sxs-lookup"><span data-stu-id="dfc1e-167">In DDD you want to update the entity only through methods in the entity (or the constructor) in order to control any invariant and the consistency of the data, so properties are defined only with a get accessor.</span></span> <span data-ttu-id="dfc1e-168">属性有作为后盾私有字段。</span><span class="sxs-lookup"><span data-stu-id="dfc1e-168">The properties are backed by private fields.</span></span> <span data-ttu-id="dfc1e-169">私有成员仅可以从类中访问。</span><span class="sxs-lookup"><span data-stu-id="dfc1e-169">Private members can only be accessed from within the class.</span></span> <span data-ttu-id="dfc1e-170">但是，那里一个异常： EF 核心需要以及这些字段进行设置。</span><span class="sxs-lookup"><span data-stu-id="dfc1e-170">However, there one exception: EF Core needs to set these fields as well.</span></span>

```csharp
// ENTITY FRAMEWORK CORE 1.1 OR LATER
// Entity is a custom base class with the ID
public class Order : Entity, IAggregateRoot
{
    // DDD Patterns comment
    // Using private fields, allowed since EF Core 1.1, is a much better
    // encapsulation aligned with DDD aggregates and domain entities (instead of
    // properties and property collections)
    private bool _someOrderInternalState;
    private DateTime _orderDate;
    public Address Address { get; private set; }
    public Buyer Buyer { get; private set; }
    private int _buyerId;
    public OrderStatus OrderStatus { get; private set; }
    private int _orderStatusId;

    // DDD patterns comment
    // Using a private collection field is better for DDD aggregate encapsulation.
    // OrderItem objects cannot be added from outside the aggregate root
    // directly to the collection, but only through the
    // OrderAggrergateRoot.AddOrderItem method, which includes behavior.
    private readonly List<OrderItem> _orderItems;
    public IEnumerable<OrderItem> OrderItems => _orderItems.AsReadOnly();
    // Using List<>.AsReadOnly()
    // This will create a read-only wrapper around the private list so it is
    // protected against external updates. It's much cheaper than .ToList(),
    // because it will not have to copy all items in a new collection.
    // (Just one heap alloc for the wrapper instance)
    // https://msdn.microsoft.com/en-us/library/e78dcd75(v=vs.110).aspx
    public PaymentMethod PaymentMethod { get; private set; }
    private int _paymentMethodId;

    protected Order() { }

    public Order(int buyerId, int paymentMethodId, Address address)
    {
        _orderItems = new List<OrderItem>();
        _buyerId = buyerId;
        _paymentMethodId = paymentMethodId;
        _orderStatusId = OrderStatus.InProcess.Id;
        _orderDate = DateTime.UtcNow;
        Address = address;
    }

    // DDD patterns comment
    // The Order aggregate root method AddOrderitem() should be the only way
    // to add items to the Order object, so that any behavior (discounts, etc.)
    // and validations are controlled by the aggregate root in order to
    // maintain consistency within the whole aggregate.
    public void AddOrderItem(int productId, string productName, decimal unitPrice,
        decimal discount, string pictureUrl, int units = 1)
    {
        // ...
        // Domain rules/logic here for adding OrderItem objects to the order
        // ...
        OrderItem item = new OrderItem(this.Id, productId, productName,
            pictureUrl, unitPrice, discount, units);
        OrderItems.Add(item);
    }

    // ...
    // Additional methods with domain rules/logic related to the Order aggregate
    // ...
}
```

### <a name="mapping-properties-with-only-get-accessors-to-the-fields-in-the-database-table"></a><span data-ttu-id="dfc1e-171">并且仅带有映射属性 get 访问器对字段数据库表中</span><span class="sxs-lookup"><span data-stu-id="dfc1e-171">Mapping properties with only get accessors to the fields in the database table</span></span>

<span data-ttu-id="dfc1e-172">将属性映射到数据库表中各列不域责任，而基础结构和持久性层的一部分。</span><span class="sxs-lookup"><span data-stu-id="dfc1e-172">Mapping properties to the database table columns is not a domain responsibility, but part of the infrastructure and persistence layer.</span></span> <span data-ttu-id="dfc1e-173">我们提到此此处只是的因此你将了解到如何可以模型实体相关的 EF 1.1 中的新功能。</span><span class="sxs-lookup"><span data-stu-id="dfc1e-173">We mention this here just so you are aware of the new capabilities in EF 1.1 related to how you can model entities.</span></span> <span data-ttu-id="dfc1e-174">本主题的其他详细信息基础结构和持久性节所述。</span><span class="sxs-lookup"><span data-stu-id="dfc1e-174">Additional details on this topic are explained in the infrastructure and persistence section.</span></span>

<span data-ttu-id="dfc1e-175">当你使用 EF 1.0，需要映射到数据库表中的实际字段 getter 仅定义的属性的 DbContext 中。</span><span class="sxs-lookup"><span data-stu-id="dfc1e-175">When you use EF 1.0, within the DbContext you need to map the properties that are defined only with getters to the actual fields in the database table.</span></span> <span data-ttu-id="dfc1e-176">这是通过 PropertyBuilder 类的 HasField 方法完成的。</span><span class="sxs-lookup"><span data-stu-id="dfc1e-176">This is done with the HasField method of the PropertyBuilder class.</span></span>

### <a name="mapping-fields-without-properties"></a><span data-ttu-id="dfc1e-177">不使用属性的映射字段</span><span class="sxs-lookup"><span data-stu-id="dfc1e-177">Mapping fields without properties</span></span>

<span data-ttu-id="dfc1e-178">EF 核心 1.1 将列映射到字段中的新功能，还有可能不使用属性。</span><span class="sxs-lookup"><span data-stu-id="dfc1e-178">With the new feature in EF Core 1.1 to map columns to fields, it is also possible to not use properties.</span></span> <span data-ttu-id="dfc1e-179">相反，你可以只映射表中对字段的列。</span><span class="sxs-lookup"><span data-stu-id="dfc1e-179">Instead, you can just map columns from a table to fields.</span></span> <span data-ttu-id="dfc1e-180">此常见的用例是用于不需要从外部实体进行访问的内部状态的私有字段。</span><span class="sxs-lookup"><span data-stu-id="dfc1e-180">A common use case for this is private fields for an internal state that does not need to be accessed from outside the entity.</span></span>

<span data-ttu-id="dfc1e-181">例如，在前面的代码示例， \_someOrderInternalState 字段具有任何相关的属性 setter 或 getter。</span><span class="sxs-lookup"><span data-stu-id="dfc1e-181">For example, in the preceding code example, the \_someOrderInternalState field has no related property for either a setter or getter.</span></span> <span data-ttu-id="dfc1e-182">该字段也将计算顺序的业务逻辑中并从顺序的方法，但它需要在数据库和持久保留。</span><span class="sxs-lookup"><span data-stu-id="dfc1e-182">That field will also be calculated within the order’s business logic and used from the order’s methods, but it needs to be persisted in the database as well.</span></span> <span data-ttu-id="dfc1e-183">因此，EF 1.1 中没有办法将无相关属性的字段映射到数据库中的列。</span><span class="sxs-lookup"><span data-stu-id="dfc1e-183">So, in EF 1.1 there is a way to map a field without a related property to a column in the database.</span></span> <span data-ttu-id="dfc1e-184">这还介绍了在[基础结构层](#the-infrastructure-layer)本指南的部分。</span><span class="sxs-lookup"><span data-stu-id="dfc1e-184">This is also explained in the [Infrastructure layer](#the-infrastructure-layer) section of this guide.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="dfc1e-185">其他资源</span><span class="sxs-lookup"><span data-stu-id="dfc1e-185">Additional resources</span></span>

-   <span data-ttu-id="dfc1e-186">**Vaughn Vernon。建模 DDD 和实体框架使用的聚合函数。**</span><span class="sxs-lookup"><span data-stu-id="dfc1e-186">**Vaughn Vernon. Modeling Aggregates with DDD and Entity Framework.**</span></span> <span data-ttu-id="dfc1e-187">请注意，这是*不*实体框架核心。</span><span class="sxs-lookup"><span data-stu-id="dfc1e-187">Note that this is *not* Entity Framework Core.</span></span>
    [<span data-ttu-id="dfc1e-188">*https://vaughnvernon.co/?p=879*</span><span class="sxs-lookup"><span data-stu-id="dfc1e-188">*https://vaughnvernon.co/?p=879*</span></span>](https://vaughnvernon.co/?p=879)

-   <span data-ttu-id="dfc1e-189">**Julie Lerman。域驱动设计编码： 数据已设定焦点的开发人员的提示**
    [*https://msdn.microsoft.com/en-us/magazine/dn342868.aspx*](https://msdn.microsoft.com/en-us/magazine/dn342868.aspx)</span><span class="sxs-lookup"><span data-stu-id="dfc1e-189">**Julie Lerman. Coding for Domain-Driven Design: Tips for Data-Focused Devs**
[*https://msdn.microsoft.com/en-us/magazine/dn342868.aspx*](https://msdn.microsoft.com/en-us/magazine/dn342868.aspx)</span></span>

-   <span data-ttu-id="dfc1e-190">**Udi Dahan。如何创建完全封装域模型**
    [*http://udidahan.com/2008/02/29/how-to-create-fully-encapsulated-domain-models/*](http://udidahan.com/2008/02/29/how-to-create-fully-encapsulated-domain-models/)</span><span class="sxs-lookup"><span data-stu-id="dfc1e-190">**Udi Dahan. How to create fully encapsulated Domain Models**
[*http://udidahan.com/2008/02/29/how-to-create-fully-encapsulated-domain-models/*](http://udidahan.com/2008/02/29/how-to-create-fully-encapsulated-domain-models/)</span></span>


>[!div class="step-by-step"]
<span data-ttu-id="dfc1e-191">[以前](微服务构成的域-model.md) [下一步] (seedwork-domain-model-base-classes-interfaces.md)</span><span class="sxs-lookup"><span data-stu-id="dfc1e-191">[Previous] (microservice-domain-model.md) [Next] (seedwork-domain-model-base-classes-interfaces.md)</span></span>
