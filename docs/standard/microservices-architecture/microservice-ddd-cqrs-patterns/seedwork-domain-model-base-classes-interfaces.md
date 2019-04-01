---
title: Seedwork（适用于域模型的可重用基类和接口）
description: 适用于容器化 .NET 应用程序的 .NET 微服务体系结构 | 使用 seedwork 概念作为开始实现面向 DDD 的域模型的起点。
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/08/2018
ms.openlocfilehash: 38de5d686c17810f406a57d58554046ba2d888d9
ms.sourcegitcommit: 4a8c2b8d0df44142728b68ebc842575840476f6d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2019
ms.locfileid: "58545723"
---
# <a name="seedwork-reusable-base-classes-and-interfaces-for-your-domain-model"></a><span data-ttu-id="ad545-103">Seedwork（适用于域模型的可重用基类和接口）</span><span class="sxs-lookup"><span data-stu-id="ad545-103">Seedwork (reusable base classes and interfaces for your domain model)</span></span>

<span data-ttu-id="ad545-104">解决方案文件夹包含 SeedWork 文件夹。</span><span class="sxs-lookup"><span data-stu-id="ad545-104">The solution folder contains a *SeedWork* folder.</span></span> <span data-ttu-id="ad545-105">此文件夹包含可以用作域实体和值对象的基础的自定义基类。</span><span class="sxs-lookup"><span data-stu-id="ad545-105">This folder contains custom base classes that you can use as a base for your domain entities and value objects.</span></span> <span data-ttu-id="ad545-106">使用这些基类，从而在每个域的对象类中避免冗余代码。</span><span class="sxs-lookup"><span data-stu-id="ad545-106">Use these base classes so you do not have redundant code in each domain’s object class.</span></span> <span data-ttu-id="ad545-107">这些类型的类的文件夹称为 SeedWork，而不是类似于 Framework。</span><span class="sxs-lookup"><span data-stu-id="ad545-107">The folder for these types of classes is called *SeedWork* and not something like *Framework*.</span></span> <span data-ttu-id="ad545-108">它称为 SeedWork，因为该文件夹仅包含可重用类的一个小型子集，不能将其视为一个框架。</span><span class="sxs-lookup"><span data-stu-id="ad545-108">It's called *SeedWork* because the folder contains just a small subset of reusable classes which cannot really be considered a framework.</span></span> <span data-ttu-id="ad545-109"> Seedwork 是由 [Michael Feathers](https://www.artima.com/forums/flat.jsp?forum=106&thread=8826) 引入的一个术语，并且由 [Martin Fowler](https://martinfowler.com/bliki/Seedwork.html) 推广普及，但也可将该文件夹命名为 Common、SharedKernel 或类似名称。</span><span class="sxs-lookup"><span data-stu-id="ad545-109">*Seedwork* is a term introduced by [Michael Feathers](https://www.artima.com/forums/flat.jsp?forum=106&thread=8826) and popularized by [Martin Fowler](https://martinfowler.com/bliki/Seedwork.html) but you could also name that folder Common, SharedKernel, or similar.</span></span>

<span data-ttu-id="ad545-110">图 7-12 显示在排序的微服务中形成域模型的 seedwork 的类。</span><span class="sxs-lookup"><span data-stu-id="ad545-110">Figure 7-12 shows the classes that form the seedwork of the domain model in the ordering microservice.</span></span> <span data-ttu-id="ad545-111">它还包含 Entity、ValueObject 和 Enumeration 等自定义基类，以及一些接口。</span><span class="sxs-lookup"><span data-stu-id="ad545-111">It has a few custom base classes like Entity, ValueObject, and Enumeration, plus a few interfaces.</span></span> <span data-ttu-id="ad545-112">这些接口（IRepository 和 IUnitOfWork）告知基础结构层需要实现的内容。</span><span class="sxs-lookup"><span data-stu-id="ad545-112">These interfaces (IRepository and IUnitOfWork) inform the infrastructure layer about what needs to be implemented.</span></span> <span data-ttu-id="ad545-113">还可通过应用程序层中的依赖关系注入使用这些接口。</span><span class="sxs-lookup"><span data-stu-id="ad545-113">Those interfaces are also used through Dependency Injection from the application layer.</span></span>

![SeedWork 文件夹的详细内容，包含基类和接口：Entity.cs、Enumeration.cs、IAggregateRoot.cs、IRepository.cs、IUnitOfWork.cs 和 ValueObject.cs](./media/image13.PNG)

<span data-ttu-id="ad545-115">**图 7-12**。</span><span class="sxs-lookup"><span data-stu-id="ad545-115">**Figure 7-12**.</span></span> <span data-ttu-id="ad545-116">域模型“seedwork”基类和接口的示例集</span><span class="sxs-lookup"><span data-stu-id="ad545-116">A sample set of domain model “seedwork" base classes and interfaces</span></span>

<span data-ttu-id="ad545-117">这是许多开发者在项目之间共享的复制和粘贴重用类型，不是正式框架。</span><span class="sxs-lookup"><span data-stu-id="ad545-117">This is the type of copy and paste reuse that many developers share between projects, not a formal framework.</span></span> <span data-ttu-id="ad545-118">seedwork 可存在于任何层或库中。</span><span class="sxs-lookup"><span data-stu-id="ad545-118">You can have seedworks in any layer or library.</span></span> <span data-ttu-id="ad545-119">但是，如果类和接口的集足够大，可能需要创建单个类库。</span><span class="sxs-lookup"><span data-stu-id="ad545-119">However, if the set of classes and interfaces gets big enough, you might want to create a single class library.</span></span>

## <a name="the-custom-entity-base-class"></a><span data-ttu-id="ad545-120">自定义实体基类</span><span class="sxs-lookup"><span data-stu-id="ad545-120">The custom Entity base class</span></span>

<span data-ttu-id="ad545-121">以下代码是实体基类的示例，可在其中放置可由任何域实体以相同方式使用的代码，例如实体 ID、[相等运算符](~/docs/csharp/language-reference/operators/equality-operators.md)、每个实体的域事件列表等。</span><span class="sxs-lookup"><span data-stu-id="ad545-121">The following code is an example of an Entity base class where you can place code that can be used the same way by any domain entity, such as the entity ID, [equality operators](~/docs/csharp/language-reference/operators/equality-operators.md), a domain event list per entity, etc.</span></span>

```csharp
// COMPATIBLE WITH ENTITY FRAMEWORK CORE (1.1 and later)
public abstract class Entity
{
    int? _requestedHashCode;
    int _Id;    
    private List<INotification> _domainEvents;
    public virtual int Id 
    {
        get
        {
            return _Id;
        }
        protected set
        {
            _Id = value;
        }
    }

    public List<INotification> DomainEvents => _domainEvents;        
    public void AddDomainEvent(INotification eventItem)
    {
        _domainEvents = _domainEvents ?? new List<INotification>();
        _domainEvents.Add(eventItem);
    }
    public void RemoveDomainEvent(INotification eventItem)
    {
        if (_domainEvents is null) return;
        _domainEvents.Remove(eventItem);
    }

    public bool IsTransient()
    {
        return this.Id == default(Int32);
    }

    public override bool Equals(object obj)
    {
        if (obj == null || !(obj is Entity))
            return false;
        if (Object.ReferenceEquals(this, obj))
            return true;
        if (this.GetType() != obj.GetType())
            return false;
        Entity item = (Entity)obj;
        if (item.IsTransient() || this.IsTransient())
            return false;
        else
            return item.Id == this.Id;
    }

    public override int GetHashCode()
    {
        if (!IsTransient())
        {
            if (!_requestedHashCode.HasValue)
                _requestedHashCode = this.Id.GetHashCode() ^ 31;
            // XOR for random distribution. See:
            // https://blogs.msdn.microsoft.com/ericlippert/2011/02/28/guidelines-and-rules-for-gethashcode/
            return _requestedHashCode.Value;
        }
        else
            return base.GetHashCode();
    }
    public static bool operator ==(Entity left, Entity right)
    {
        if (Object.Equals(left, null))
            return (Object.Equals(right, null));
        else
            return left.Equals(right);
    }
    public static bool operator !=(Entity left, Entity right)
    {
        return !(left == right);
    }
}
```

<span data-ttu-id="ad545-122">使用每个实体的域事件列表的上一个代码将在下一部分（重点是域事件）介绍。</span><span class="sxs-lookup"><span data-stu-id="ad545-122">The previous code using a domain event list per entity will be explained in the next sections when focusing on domain events.</span></span>

## <a name="repository-contracts-interfaces-in-the-domain-model-layer"></a><span data-ttu-id="ad545-123">域模型层中的存储库协定（接口）</span><span class="sxs-lookup"><span data-stu-id="ad545-123">Repository contracts (interfaces) in the domain model layer</span></span>

<span data-ttu-id="ad545-124">存储库协定是表达存储库的协定要求的 .NET 接口，用于每个聚合。</span><span class="sxs-lookup"><span data-stu-id="ad545-124">Repository contracts are simply .NET interfaces that express the contract requirements of the repositories to be used for each aggregate.</span></span>

<span data-ttu-id="ad545-125">存储库本身（包含 EF Core 代码或其他任何基础结构依赖项和代码（Linq、SQL 等）不能在域模型内实现，存储库应仅实现你在域模型中定义的接口。</span><span class="sxs-lookup"><span data-stu-id="ad545-125">The repositories themselves, with EF Core code or any other infrastructure dependencies and code (Linq, SQL, etc.), must not be implemented within the domain model; the repositories should only implement the interfaces you define in the domain model.</span></span>

<span data-ttu-id="ad545-126">这种做法（在域模型层中放置存储库接口）的相关模式是分隔接口模式。</span><span class="sxs-lookup"><span data-stu-id="ad545-126">A pattern related to this practice (placing the repository interfaces in the domain model layer) is the Separated Interface pattern.</span></span> <span data-ttu-id="ad545-127">正如 Martin Fowler [所述](https://www.martinfowler.com/eaaCatalog/separatedInterface.html)，“使用分隔接口在一个包中定义接口，但在另一个包中实现它。</span><span class="sxs-lookup"><span data-stu-id="ad545-127">As [explained](https://www.martinfowler.com/eaaCatalog/separatedInterface.html) by Martin Fowler, “Use Separated Interface to define an interface in one package but implement it in another.</span></span> <span data-ttu-id="ad545-128">这样一来，需要接口依赖项的客户端可能完全不会识别出实现。”</span><span class="sxs-lookup"><span data-stu-id="ad545-128">This way a client that needs the dependency to the interface can be completely unaware of the implementation.”</span></span>

<span data-ttu-id="ad545-129">通过遵循分隔接口模式，应用程序层（在此情况下是微服务的 Web API 项目）可具有在域模型中定义的要求的依赖项，但没有基础结构/持久性层的直接依赖项。</span><span class="sxs-lookup"><span data-stu-id="ad545-129">Following the Separated Interface pattern enables the application layer (in this case, the Web API project for the microservice) to have a dependency on the requirements defined in the domain model, but not a direct dependency to the infrastructure/persistence layer.</span></span> <span data-ttu-id="ad545-130">此外，可以使用依赖项注入隔离实现，可在使用存储库的基础结构/持久性层中实现这一点。</span><span class="sxs-lookup"><span data-stu-id="ad545-130">In addition, you can use Dependency Injection to isolate the implementation, which is implemented in the infrastructure/ persistence layer using repositories.</span></span>

<span data-ttu-id="ad545-131">例如，包含 IOrderRepository 接口的下面的示例定义 OrderRepository 类在基础机构层中实现所需的操作。</span><span class="sxs-lookup"><span data-stu-id="ad545-131">For example, the following example with the IOrderRepository interface defines what operations the OrderRepository class will need to implement at the infrastructure layer.</span></span> <span data-ttu-id="ad545-132">在应用程序的当前实现中，代码只需将订单添加或更新到数据库，因为查询根据简化的 CQRS 方法拆分。</span><span class="sxs-lookup"><span data-stu-id="ad545-132">In the current implementation of the application, the code just needs to add or update orders to the database, since queries are split following the simplified CQRS approach.</span></span>

```csharp
// Defined at IOrderRepository.cs
public interface IOrderRepository : IRepository<Order>
{
    Order Add(Order order);

    void Update(Order order);

    Task<Order> GetAsync(int orderId);
}

// Defined at IRepository.cs (Part of the Domain Seedwork)
public interface IRepository<T> where T : IAggregateRoot
{
    IUnitOfWork UnitOfWork { get; }
}
```

## <a name="additional-resources"></a><span data-ttu-id="ad545-133">其他资源</span><span class="sxs-lookup"><span data-stu-id="ad545-133">Additional resources</span></span>

- <span data-ttu-id="ad545-134">**Martin Fowler。Separated Interface.**（分隔接口）</span><span class="sxs-lookup"><span data-stu-id="ad545-134">**Martin Fowler. Separated Interface.**</span></span> \
  [https://www.martinfowler.com/eaaCatalog/separatedInterface.html](https://www.martinfowler.com/eaaCatalog/separatedInterface.html)

>[!div class="step-by-step"]
><span data-ttu-id="ad545-135">[上一页](net-core-microservice-domain-model.md)
>[下一页](implement-value-objects.md)</span><span class="sxs-lookup"><span data-stu-id="ad545-135">[Previous](net-core-microservice-domain-model.md)
[Next](implement-value-objects.md)</span></span>
