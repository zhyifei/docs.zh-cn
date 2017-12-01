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
# <a name="implementing-a-microservice-domain-model-with-net-core"></a>实现 microservice 域模型与.NET 核心 

在上一节中所述的基本设计原则和设计域模型的模式。 现在就可以了解可能的方式实现域模型中使用.NET Core (纯 C\#代码) 和 EF 核心。 请注意您的域模型将只需组成你的代码。 它将在 EF 上具有只 EF 核心模型要求，但不是实际依赖关系。 不应在你的域模型中具有的硬依赖项或对 EF 核心或其他 ORM 的引用。

## <a name="domain-model-structure-in-a-custom-net-standard-library"></a>自定义的标准.NET 库中的域模型结构

用于 eShopOnContainers 引用应用程序的文件夹组织演示应用程序的 DDD 模型。 您可能发现不同文件夹组织更清楚地进行通信的应用程序所做的设计选择。 正如您可以看到图 9-10，排序的域模型中有两个聚合，顺序聚合和 buyer 聚合。 每个聚合是一组域实体和值对象，但您可以对聚合以及组成的单一域实体 （聚合根或根实体）。

![](./media/image11.png)

**图 9-10**。 在 eShopOnContainers 排序微服务构成的域模型结构

此外，域模型层包括是您的域模型的基础结构要求的存储库协定 （接口）。 换而言之，这些接口 express 基础结构层必须实现哪些存储库以及如何。 很重要的存储库实现放置之外的域模型层，基础结构层库，所以，域模型层不"污染"通过 API 或从基础结构技术，如实体框架的类。

你还可以看到[SeedWork](https://martinfowler.com/bliki/Seedwork.html)包含可以用作基础域实体和值的自定义基类文件夹对象，因此你不需要在每个域的对象类冗余代码。

## <a name="structuring-aggregates-in-a-custom-net-standard-library"></a>构造一个自定义的标准.NET 库中的聚合函数

聚合是指组合在一起以匹配事务一致性的域对象的群集。 这些对象可能是加上任何其他值对象 （其中之一是聚合根或根实体） 的实体的实例。

事务一致性意味着聚合保证一致且最新的业务操作的末尾。 例如，从排序 microservice 域模型 eShopOnContainers 顺序聚合由构成图 9-11 中所示。

![](./media/image12.png)

**图 9-11**。 在 Visual Studio 解决方案聚合顺序

如果在聚合文件夹中打开的任何文件，你可以看到如何标记为自定义的基类或接口，实体或值与对象一样，当在中实现[Seedwork](https://github.com/dotnet-architecture/eShopOnContainers/tree/master/src/Services/Ordering/Ordering.Domain/SeedWork)文件夹。

## <a name="implementing-domain-entities-as-poco-classes"></a>实现域实体作为 POCO 类

在.NET 中实现域模型，通过创建实现你的域实体的 POCO 类。 以下示例中，在 Order 类定义实体，而且还为聚合根。 由于 Order 类派生自的实体的基类，它可以重复使用与实体相关的常见代码。 请记住，这些基类，这些类和接口都由你在域模型项目中，因此它是你的代码、 不是从如 EF ORM 的基础结构代码。

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

请务必注意这是作为 POCO 类实现一个域实体。 它没有任何直接依赖于实体框架核心或任何其他基础结构框架。 此实现是因为它应该是的只需 C\#实现域模型的代码。

此外，类进行了修饰名为 IAggregateRoot 接口。 该接口是一个空的接口，有时称为*标记接口*，即只用于指示此实体类还进行聚合根。

一种标记接口有时视为反模式;但是，还有一种标记类，该接口可能会不断发展时尤其是干净方式。 属性可以标记，另一个选择但不要在上面类聚合特性标记的 IAggregate 接口旁边看到的基类 （实体） 速度更快。 它在任何情况下是首选项，metter。

具有聚合根表示与一致性相关的大部分代码，应作为 Order 聚合根类 (例如，AddOrderItem OrderItem 对象添加到聚合时) 中的方法实现的聚合的实体的业务规则. 不应该创建或更新 OrderItems 对象独立或直接调用控件和任何更新操作针对其子实体的一致性，必须保持 AggregateRoot 类。

例如，你应*不*执行以下操作，从任何命令处理程序方法或应用程序层类：

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

在这种情况下，添加方法是只是一个操作以添加具有对 OrderItems 集合的直接访问数据。 因此，大部分域逻辑、 规则或验证与相关的子实体的操作将能跨越应用程序层 （命令处理程序和 Web API 控制器）。

如果你转围绕聚合根，聚合根无法保证其固定协定，其有效性或其一致性。 最终你将拥有复式代码或事务的脚本代码。

若要执行 DDD 模式，实体不能与公共 setter 中的任何实体属性。 应通过显式方法显式无处不在语言，它们将执行实体中的更改的相关驱动中实体的更改。

此外，实体 （如订单项中） 中的集合中应为只读属性 （AsReadOnly 方法稍后进行说明）。 你应能够更新它只能从在聚合根类方法或子实体方法中。

如你所见顺序聚合根的代码中，所有 setter 应都为 private 或至少是只读的外部使用，以便针对实体的数据或其子实体的任何操作必须通过在实体类的方法执行。 这将保持一致性而不是实现事务的脚本代码的受控和面向对象的方式。

下面的代码段演示代码 OrderItem 对象添加到订单聚合的任务的正确方法。

```csharp
// RIGHT ACCORDING TO DDD--CODE AT THE APPLICATION LAYER OR COMMAND HANDLERS
// The code in command handlers or WebAPI controllers, related only to application stuff
// There is NO code here related to OrderItem object’s business logic
myOrder.AddOrderItem(productId, productName, pictureUrl, unitPrice, discount, units);

// The code related to OrderItem params validations or domain rules should
// be WITHIN the AddOrderItem method.

//...
```

在此代码段，大部分验证或与创建 OrderItem 对象相关的逻辑将受控制的顺序聚合根-AddOrderItem 方法中-尤其是验证和逻辑相关的其他元素在聚合。 例如，可能会收到相同的产品项作为对 AddOrderItem 的多个调用的结果。 在该方法中，你可以检查产品项并将相同的产品项整合到单个 OrderItem 对象具有几个单位。 此外，如果不同折扣金额，但产品 ID 都相同，你可能会应用更高版本的折扣。 此原则适用于任何其他域逻辑 OrderItem 对象。

此外，新的 OrderItem(params) 操作将还控制并从顺序聚合根 AddOrderItem 方法执行。 因此，大部分逻辑或验证与相关的操作 （尤其是任何内容会影响其他子实体之间的一致性） 将会在聚合根中的单个位置。 这是聚合根模式的最终目的。

当你使用 Entity Framework 1.1 时，DDD 实体可以更好地表示因为实体框架核心 1.1 的新功能之一是它允许[将映射到字段](https://docs.microsoft.com/ef/core/modeling/backing-field)除了属性外。 保护子实体或值对象的集合时，这很有用。 对于此增强功能，你可以使用简单的私有字段，而不是属性，你可以在公共方法中实现任何更新的字段集合和通过 AsReadOnly 方法提供只读访问权限。

在你想要仅通过在实体 （或构造函数），以便控制任何固定和数据的一致性方法更新该实体的 DDD，因此属性定义仅具有一个 get 访问器。 属性有作为后盾私有字段。 私有成员仅可以从类中访问。 但是，那里一个异常： EF 核心需要以及这些字段进行设置。

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

### <a name="mapping-properties-with-only-get-accessors-to-the-fields-in-the-database-table"></a>并且仅带有映射属性 get 访问器对字段数据库表中

将属性映射到数据库表中各列不域责任，而基础结构和持久性层的一部分。 我们提到此此处只是的因此你将了解到如何可以模型实体相关的 EF 1.1 中的新功能。 本主题的其他详细信息基础结构和持久性节所述。

当你使用 EF 1.0，需要映射到数据库表中的实际字段 getter 仅定义的属性的 DbContext 中。 这是通过 PropertyBuilder 类的 HasField 方法完成的。

### <a name="mapping-fields-without-properties"></a>不使用属性的映射字段

EF 核心 1.1 将列映射到字段中的新功能，还有可能不使用属性。 相反，你可以只映射表中对字段的列。 此常见的用例是用于不需要从外部实体进行访问的内部状态的私有字段。

例如，在前面的代码示例， \_someOrderInternalState 字段具有任何相关的属性 setter 或 getter。 该字段也将计算顺序的业务逻辑中并从顺序的方法，但它需要在数据库和持久保留。 因此，EF 1.1 中没有办法将无相关属性的字段映射到数据库中的列。 这还介绍了在[基础结构层](#the-infrastructure-layer)本指南的部分。

### <a name="additional-resources"></a>其他资源

-   **Vaughn Vernon。建模 DDD 和实体框架使用的聚合函数。** 请注意，这是*不*实体框架核心。
    [*https://vaughnvernon.co/?p=879*](https://vaughnvernon.co/?p=879)

-   **Julie Lerman。域驱动设计编码： 数据已设定焦点的开发人员的提示**
    [*https://msdn.microsoft.com/en-us/magazine/dn342868.aspx*](https://msdn.microsoft.com/en-us/magazine/dn342868.aspx)

-   **Udi Dahan。如何创建完全封装域模型**
    [*http://udidahan.com/2008/02/29/how-to-create-fully-encapsulated-domain-models/*](http://udidahan.com/2008/02/29/how-to-create-fully-encapsulated-domain-models/)


>[!div class="step-by-step"]
[以前](微服务构成的域-model.md) [下一步] (seedwork-domain-model-base-classes-interfaces.md)
