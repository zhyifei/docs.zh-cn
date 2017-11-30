---
title: "Seedwork （可重用基类，这些类和接口，您的域模型）"
description: "为容器化的.NET 应用程序的.NET 微服务体系结构 |Seedwork （可重用基类，这些类和接口，您的域模型）"
keywords: "Docker, 微服务, ASP.NET, 容器"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: 17602d94ea167997389a77f0d2358326258a8219
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="seedwork-reusable-base-classes-and-interfaces-for-your-domain-model"></a><span data-ttu-id="2ae10-104">Seedwork （可重用基类，这些类和接口，您的域模型）</span><span class="sxs-lookup"><span data-stu-id="2ae10-104">Seedwork (reusable base classes and interfaces for your domain model)</span></span>

<span data-ttu-id="2ae10-105">解决方案文件夹包含*SeedWork*文件夹。</span><span class="sxs-lookup"><span data-stu-id="2ae10-105">The solution folder contains a *SeedWork* folder.</span></span> <span data-ttu-id="2ae10-106">*SeedWork*文件夹包含可以用作基础域实体和值对象的自定义基类。</span><span class="sxs-lookup"><span data-stu-id="2ae10-106">The *SeedWork* folder contains custom base classes that you can use as a base for your domain entities and value objects.</span></span> <span data-ttu-id="2ae10-107">使用这些基类的类，因此你不需要在每个域的对象类冗余代码。</span><span class="sxs-lookup"><span data-stu-id="2ae10-107">Use these base classes so you do not have redundant code in each domain’s object class.</span></span> <span data-ttu-id="2ae10-108">此文件夹为这些类型的类称为*SeedWork*和不类似于*Framework*。</span><span class="sxs-lookup"><span data-stu-id="2ae10-108">The folder for these types of classes is called *SeedWork* and not something like *Framework*.</span></span> <span data-ttu-id="2ae10-109">它称为*SeedWork*因为该文件夹包含仅的可重用的类不能真正将其视为一个框架的一小部分。</span><span class="sxs-lookup"><span data-stu-id="2ae10-109">It's called *SeedWork* because the folder contains just a small subset of reusable classes which cannot really be considered a framework.</span></span> <span data-ttu-id="2ae10-110">*Seedwork*由此引入一个术语[Michael 羽化](http://www.artima.com/forums/flat.jsp?forum=106&thread=8826)和普遍通过[Martin Fowler](https://martinfowler.com/bliki/Seedwork.html)但你还可将该文件夹、 常用 SharedKernel，或类似。</span><span class="sxs-lookup"><span data-stu-id="2ae10-110">*Seedwork* is a term introduced by [Michael Feathers](http://www.artima.com/forums/flat.jsp?forum=106&thread=8826) and popularized by [Martin Fowler](https://martinfowler.com/bliki/Seedwork.html) but you could also name that folder Common, SharedKernel, or similar.</span></span>

<span data-ttu-id="2ae10-111">图 9-12 显示排序的微服务中的窗体的域模型 seedwork 的类。</span><span class="sxs-lookup"><span data-stu-id="2ae10-111">Figure 9-12 shows the classes that form the seedwork of the domain model in the ordering microservice.</span></span> <span data-ttu-id="2ae10-112">它还具有几个自定义的基本类，如实体、 ValueObject 和枚举，加上的几个接口。</span><span class="sxs-lookup"><span data-stu-id="2ae10-112">It has a few custom base classes like Entity, ValueObject, and Enumeration, plus a few interfaces.</span></span> <span data-ttu-id="2ae10-113">（IRepository 和 IUnitOfWork） 这些接口需要实现有关通知基础结构层。</span><span class="sxs-lookup"><span data-stu-id="2ae10-113">These interfaces (IRepository and IUnitOfWork) inform the infrastructure layer about what needs to be implemented.</span></span> <span data-ttu-id="2ae10-114">这些接口还使用通过依赖关系注入从应用程序层。</span><span class="sxs-lookup"><span data-stu-id="2ae10-114">Those interfaces are also used through Dependency Injection from the application layer.</span></span>

![](./media/image13.PNG)

<span data-ttu-id="2ae10-115">**图 9-12**。</span><span class="sxs-lookup"><span data-stu-id="2ae10-115">**Figure 9-12**.</span></span> <span data-ttu-id="2ae10-116">示例设置的域模型"seedwork"基本类和接口</span><span class="sxs-lookup"><span data-stu-id="2ae10-116">A sample set of domain model “seedwork" base classes and interfaces</span></span>

<span data-ttu-id="2ae10-117">这是许多开发人员共享项目，不正式 framework 之间的复制和粘贴重用的类型。</span><span class="sxs-lookup"><span data-stu-id="2ae10-117">This is the type of copy and paste reuse that many developers share between projects, not a formal framework.</span></span> <span data-ttu-id="2ae10-118">你可以在任何层或库中的 seedworks。</span><span class="sxs-lookup"><span data-stu-id="2ae10-118">You can have seedworks in any layer or library.</span></span> <span data-ttu-id="2ae10-119">但是，如果组类和接口获取到足够大，你可能想要创建一个单个的类库。</span><span class="sxs-lookup"><span data-stu-id="2ae10-119">However, if the set of classes and interfaces gets big enough, you might want to create a single class library.</span></span>

## <a name="the-custom-entity-base-class"></a><span data-ttu-id="2ae10-120">自定义实体基类</span><span class="sxs-lookup"><span data-stu-id="2ae10-120">The custom Entity base class</span></span>

<span data-ttu-id="2ae10-121">下面的代码是实体基本类的一个示例可以由任何域实体，如实体 ID 相同的方式使用代码的放置位置[相等运算符](https://msdn.microsoft.com/en-us/library/c35t2ffz.aspx)，等等。</span><span class="sxs-lookup"><span data-stu-id="2ae10-121">The following code is an example of an Entity base class where you can place code that can be used the same way by any domain entity, such as the entity ID, [equality operators](https://msdn.microsoft.com/en-us/library/c35t2ffz.aspx), etc.</span></span>

```csharp
// ENTITY FRAMEWORK CORE 1.1
public abstract class Entity
{
    int? _requestedHashCode;
    int _Id;

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
                _requestedHashCode = this.Id.GetHashCode() \^ 31;
            // XOR for random distribution. See:
            // http://blogs.msdn.com/b/ericlippert/archive/2011/02/28/guidelines-and-rules-for-gethashcode.aspx
            return _requestedHashCode.Value;
        }
        else
            return base.GetHashCode();
    }

    public static bool operator ==(Entity left, Entity right)
    {
        if (Object.Equals(left, null))
            return (Object.Equals(right, null)) ? true : false;
        else
            return left.Equals(right);
    }

    public static bool operator !=(Entity left, Entity right)
    {
        return !(left == right);
    }
}
```

## <a name="repository-contracts-interfaces-in-the-domain-model-layer"></a><span data-ttu-id="2ae10-122">域模型层中的存储库协定 （接口）</span><span class="sxs-lookup"><span data-stu-id="2ae10-122">Repository contracts (interfaces) in the domain model layer</span></span>

<span data-ttu-id="2ae10-123">存储库协定都是只需.NET express 的存储库的协定要求对于每个聚合中使用的接口。</span><span class="sxs-lookup"><span data-stu-id="2ae10-123">Repository contracts are simply .NET interfaces that express the contract requirements of the repositories to be used for each aggregate.</span></span> <span data-ttu-id="2ae10-124">必须在域模型中; 实现的存储库本身，与 EF 核心代码或任何其他基础结构依赖关系和代码，存储库应仅实现你定义的接口。</span><span class="sxs-lookup"><span data-stu-id="2ae10-124">The repositories themselves, with EF Core code or any other infrastructure dependencies and code, must not be implemented within the domain model; the repositories should only implement the interfaces you define.</span></span>

<span data-ttu-id="2ae10-125">这种做法 （在域模型层中放置存储库接口） 相关的模式是分隔接口模式。</span><span class="sxs-lookup"><span data-stu-id="2ae10-125">A pattern related to this practice (placing the repository interfaces in the domain model layer) is the Separated Interface pattern.</span></span> <span data-ttu-id="2ae10-126">作为[所述](http://www.martinfowler.com/eaaCatalog/separatedInterface.html)Martin Fowler 通过"使用分隔接口接口定义为在一个包，但在另一个中实现它。</span><span class="sxs-lookup"><span data-stu-id="2ae10-126">As [explained](http://www.martinfowler.com/eaaCatalog/separatedInterface.html) by Martin Fowler, “Use Separated Interface to define an interface in one package but implement it in another.</span></span> <span data-ttu-id="2ae10-127">这种方式可以客户端所需的依赖关系的接口的实现完全不能识别。"</span><span class="sxs-lookup"><span data-stu-id="2ae10-127">This way a client that needs the dependency to the interface can be completely unaware of the implementation.”</span></span>

<span data-ttu-id="2ae10-128">执行分隔接口模式启用应用程序层 （在此情况下，微服务的 Web API 项目） 能够依赖于在域模型中，定义的要求，但不是直接依赖到基础结构/持久性层。</span><span class="sxs-lookup"><span data-stu-id="2ae10-128">Following the Separated Interface pattern enables the application layer (in this case, the Web API project for the microservice) to have a dependency on the requirements defined in the domain model, but not a direct dependency to the infrastructure/persistence layer.</span></span> <span data-ttu-id="2ae10-129">此外，你可以使用依赖关系注入隔离实现，它可以实现基础结构中持久性层使用存储库。</span><span class="sxs-lookup"><span data-stu-id="2ae10-129">In addition, you can use Dependency Injection to isolate the implementation, which is implemented in the infrastructure/ persistence layer using repositories.</span></span>

<span data-ttu-id="2ae10-130">例如，下面的示例使用 IOrderRepository 界面定义 OrderRepository 类将需要在基础结构层实现的操作。</span><span class="sxs-lookup"><span data-stu-id="2ae10-130">For example, the following example with the IOrderRepository interface defines what operations the OrderRepository class will need to implement at the infrastructure layer.</span></span> <span data-ttu-id="2ae10-131">在应用程序的当前实现中，代码只需要将顺序添加到数据库，由于查询拆分以下未实现 CQS 方法和订单的更新。</span><span class="sxs-lookup"><span data-stu-id="2ae10-131">In the current implementation of the application, the code just needs to add the order to the database, since queries are split following the CQS approach, and updates to orders are not implemented.</span></span>

```csharp
public interface IOrderRepository : IRepository<Order>
{
    Order Add(Order order);
}

public interface IRepository<T> where T : IAggregateRoot
{
    IUnitOfWork UnitOfWork { get; }
}
```

## <a name="additional-resources"></a><span data-ttu-id="2ae10-132">其他资源</span><span class="sxs-lookup"><span data-stu-id="2ae10-132">Additional resources</span></span>

-   <span data-ttu-id="2ae10-133">**Martin Fowler。分隔的接口。** 
     [ *http://www.martinfowler.com/eaaCatalog/separatedInterface.html*](http://www.martinfowler.com/eaaCatalog/separatedInterface.html%20)</span><span class="sxs-lookup"><span data-stu-id="2ae10-133">**Martin Fowler. Separated Interface.**
[*http://www.martinfowler.com/eaaCatalog/separatedInterface.html*](http://www.martinfowler.com/eaaCatalog/separatedInterface.html%20)</span></span>


>[!div class="step-by-step"]
<span data-ttu-id="2ae10-134">[以前](net-核心-微服务构成的域-model.md) [下一步] (实现值 objects.md)</span><span class="sxs-lookup"><span data-stu-id="2ae10-134">[Previous] (net-core-microservice-domain-model.md) [Next] (implement-value-objects.md)</span></span>
