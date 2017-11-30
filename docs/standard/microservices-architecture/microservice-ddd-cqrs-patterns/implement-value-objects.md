---
title: "实现值对象"
description: "为容器化的.NET 应用程序的.NET 微服务体系结构 |实现值对象"
keywords: "Docker, 微服务, ASP.NET, 容器"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: c20bc80d2ddb864a3a0172beb211974426a278a8
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="implementing-value-objects"></a><span data-ttu-id="612fe-104">实现值对象</span><span class="sxs-lookup"><span data-stu-id="612fe-104">Implementing value objects</span></span>

<span data-ttu-id="612fe-105">在前面部分中讨论有关实体和聚合，标识是必不可少的实体。</span><span class="sxs-lookup"><span data-stu-id="612fe-105">As discussed in earlier sections about entities and aggregates, identity is fundamental for entities.</span></span> <span data-ttu-id="612fe-106">但是，有许多对象和数据项不需要的标识和跟踪，例如值中的对象的标识的系统中。</span><span class="sxs-lookup"><span data-stu-id="612fe-106">However, there are many objects and data items in a system that do not require an identity and identity tracking, such as value objects.</span></span>

<span data-ttu-id="612fe-107">值对象可以引用其他实体。</span><span class="sxs-lookup"><span data-stu-id="612fe-107">A value object can reference other entities.</span></span> <span data-ttu-id="612fe-108">例如，在应用程序生成的路由，介绍如何从一个点来访问另一个字符串，该路由将值对象。</span><span class="sxs-lookup"><span data-stu-id="612fe-108">For example, in an application that generates a route that describes how to get from one point to another, that route would be a value object.</span></span> <span data-ttu-id="612fe-109">它将特定的路由上的点的快照，但此建议的路由将不具有有标识，即使它可能是内部指如市/县、 道路等实体。</span><span class="sxs-lookup"><span data-stu-id="612fe-109">It would be a snapshot of points on a specific route, but this suggested route would not have an identity, even though internally it might refer to entities like City, Road, etc.</span></span>

<span data-ttu-id="612fe-110">图 9-13 显示顺序聚合中的地址值对象。</span><span class="sxs-lookup"><span data-stu-id="612fe-110">Figure 9-13 shows the Address value object within the Order aggregate.</span></span>

![](./media/image14.png)

<span data-ttu-id="612fe-111">**图 9-13**。</span><span class="sxs-lookup"><span data-stu-id="612fe-111">**Figure 9-13**.</span></span> <span data-ttu-id="612fe-112">解决顺序聚合中的值对象</span><span class="sxs-lookup"><span data-stu-id="612fe-112">Address value object within the Order aggregate</span></span>

<span data-ttu-id="612fe-113">如所示图 9-13，实体通常由多个属性。</span><span class="sxs-lookup"><span data-stu-id="612fe-113">As shown in Figure 9-13, an entity is usually composed of multiple attributes.</span></span> <span data-ttu-id="612fe-114">例如，可以建模为具有标识的实体顺序，将其内部组成的一组特性，例如 OrderId、 OrderDate、 OrderItems，等等。但组成国家/地区，街道、 城市的地址，这是只是一个复杂的值，必须建模等，并将其视为值对象。</span><span class="sxs-lookup"><span data-stu-id="612fe-114">For example, Order can be modeled as an entity with an identity and composed internally of a set of attributes such as OrderId, OrderDate, OrderItems, etc. But the address, which is simply a complex value composed of country, street, city, etc. must be modeled and treated as a value object.</span></span>

## <a name="important-characteristics-of-value-objects"></a><span data-ttu-id="612fe-115">值对象的重要特征</span><span class="sxs-lookup"><span data-stu-id="612fe-115">Important characteristics of value objects</span></span>

<span data-ttu-id="612fe-116">有两个值对象的主要特征：</span><span class="sxs-lookup"><span data-stu-id="612fe-116">There are two main characteristics for value objects:</span></span>

-   <span data-ttu-id="612fe-117">它们具有任何标识。</span><span class="sxs-lookup"><span data-stu-id="612fe-117">They have no identity.</span></span>

-   <span data-ttu-id="612fe-118">它们是不可变。</span><span class="sxs-lookup"><span data-stu-id="612fe-118">They are immutable.</span></span>

<span data-ttu-id="612fe-119">已讨论的第一个特性。</span><span class="sxs-lookup"><span data-stu-id="612fe-119">The first characteristic was already discussed.</span></span> <span data-ttu-id="612fe-120">不可变性是一个重要要求。</span><span class="sxs-lookup"><span data-stu-id="612fe-120">Immutability is an important requirement.</span></span> <span data-ttu-id="612fe-121">在创建对象后，值对象的值必须是不可变。</span><span class="sxs-lookup"><span data-stu-id="612fe-121">The values of a value object must be immutable once the object is created.</span></span> <span data-ttu-id="612fe-122">因此，当构造对象时，你必须提供所需的值，但则不能允许对其进行更改的对象的生存期内。</span><span class="sxs-lookup"><span data-stu-id="612fe-122">Therefore, when the object is constructed, you must provide the required values, but you must not allow them to change during the object’s lifetime.</span></span>

<span data-ttu-id="612fe-123">值对象，可以为性能，其不可变的性质感谢执行某些技巧。</span><span class="sxs-lookup"><span data-stu-id="612fe-123">Value objects allow you to perform certain tricks for performance, thanks to their immutable nature.</span></span> <span data-ttu-id="612fe-124">这是系统中尤其如此其中可能有数千个值对象实例，其中的许多具有相同的值。</span><span class="sxs-lookup"><span data-stu-id="612fe-124">This is especially true in systems where there may be thousands of value object instances, many of which have the same values.</span></span> <span data-ttu-id="612fe-125">不可变本质使他们可以重用;它们可以是可互换的对象，因为它们的值都相同，并且它们具有任何标识。</span><span class="sxs-lookup"><span data-stu-id="612fe-125">Their immutable nature allows them to be reused; they can be interchangeable objects, since their values are the same and they have no identity.</span></span> <span data-ttu-id="612fe-126">有时，这种优化可以使运行速度慢的软件和软件性能良好之间存在的差异。</span><span class="sxs-lookup"><span data-stu-id="612fe-126">This type of optimization can sometimes make a difference between software that runs slowly and software with good performance.</span></span> <span data-ttu-id="612fe-127">当然，，所有这些情况下将取决于应用程序环境以及部署上下文。</span><span class="sxs-lookup"><span data-stu-id="612fe-127">Of course, all these cases depend on the application environment and deployment context.</span></span>

## <a name="value-object-implementation-in-c"></a><span data-ttu-id="612fe-128">在 C 中的值对象实现\#</span><span class="sxs-lookup"><span data-stu-id="612fe-128">Value object implementation in C\#</span></span>

<span data-ttu-id="612fe-129">根据实现中，你可以具有等基于比较 （因为值对象不必须基于标识） 的所有属性和其他基本特征之间的相等性的基本实用程序方法的值对象基本类。</span><span class="sxs-lookup"><span data-stu-id="612fe-129">In terms of implementation, you can have a value object base class that has basic utility methods like equality based on comparison between all the attributes (since a value object must not be based on identity) and other fundamental characteristics.</span></span> <span data-ttu-id="612fe-130">下面的示例演示在从 eShopOnContainers 排序微服务中使用的值对象基本类。</span><span class="sxs-lookup"><span data-stu-id="612fe-130">The following example shows a value object base class used in the ordering microservice from eShopOnContainers.</span></span>

```csharp
public abstract class ValueObject
{
    protected static bool EqualOperator(ValueObject left, ValueObject right)
    {
        if (ReferenceEquals(left, null) ^ ReferenceEquals(right, null))
        {
            return false;
        }
        return ReferenceEquals(left, null) || left.Equals(right);
    }

    protected static bool NotEqualOperator(ValueObject left, ValueObject right)
    {
        return !(EqualOperator(left, right));
    }

    protected abstract IEnumerable<object> GetAtomicValues();

    public override bool Equals(object obj)
    {
        if (obj == null || obj.GetType() != GetType())
        {
            return false;
        }

        ValueObject other = (ValueObject)obj;
        IEnumerator<object> thisValues = GetAtomicValues().GetEnumerator();
        IEnumerator<object> otherValues = other.GetAtomicValues().GetEnumerator();
        while (thisValues.MoveNext() && otherValues.MoveNext())
        {
            if (ReferenceEquals(thisValues.Current, null) ^
                ReferenceEquals(otherValues.Current, null))
            {
                return false;
            }

            if (thisValues.Current != null &&
                !thisValues.Current.Equals(otherValues.Current))
            {
                return false;
            }
        }
        return !thisValues.MoveNext() && !otherValues.MoveNext();
    }
    // Other utilility methods
}
```

<span data-ttu-id="612fe-131">你可以使用此类时实现你实际值的对象，如下面的示例中显示的地址值对象：</span><span class="sxs-lookup"><span data-stu-id="612fe-131">You can use this class when implementing your actual value object, as with the Address value object shown in the following example:</span></span>

```csharp
public class Address : ValueObject
{
    public String Street { get; private set; }
    public String City { get; private set; }
    public String State { get; private set; }
    public String Country { get; private set; }
    public String ZipCode { get; private set; }

    public Address(string street, string city, string state,
        string country, string zipcode)
    {
        Street = street;
        City = city;
        State = state;
        Country = country;
        ZipCode = zipcode;
    }

    protected override IEnumerable<object> GetAtomicValues()
    {
        yield return Street;
        yield return City;
        yield return State;
        yield return Country;
        yield return ZipCode;
    }
}
```

## <a name="hiding-the-identity-characteristic-when-using-ef-core-to-persist-value-objects"></a><span data-ttu-id="612fe-132">隐藏的标识特征时使用 EF 核心持久保存值对象</span><span class="sxs-lookup"><span data-stu-id="612fe-132">Hiding the identity characteristic when using EF Core to persist value objects</span></span>

<span data-ttu-id="612fe-133">限制时使用 EF 核心，其当前版本 (EF 核心 1.1) 中不能使用[复杂类型](https://docs.microsoft.com/de-de/dotnet/api/system.componentmodel.dataannotations.schema.complextypeattribute?view=netframework-4.7)EF 中定义 6.x。</span><span class="sxs-lookup"><span data-stu-id="612fe-133">A limitation when using EF Core is that in its current version (EF Core 1.1) you cannot use [complex types](https://docs.microsoft.com/de-de/dotnet/api/system.componentmodel.dataannotations.schema.complextypeattribute?view=netframework-4.7) as defined in EF 6.x.</span></span> <span data-ttu-id="612fe-134">因此，你必须为 EF 实体来存储值对象。</span><span class="sxs-lookup"><span data-stu-id="612fe-134">Therefore, you must store your value object as an EF entity.</span></span> <span data-ttu-id="612fe-135">但是，可以隐藏其 ID，因此你进行清除的标识不重要的模型的值对象中。</span><span class="sxs-lookup"><span data-stu-id="612fe-135">However, you can hide its ID so you make clear that the identity is not important in the model that the value object is part of.</span></span> <span data-ttu-id="612fe-136">隐藏 ID 是作为卷影属性使用的 ID。</span><span class="sxs-lookup"><span data-stu-id="612fe-136">You hide the ID is by using the ID as a shadow property.</span></span> <span data-ttu-id="612fe-137">由于基础结构级别中设置了该配置用于隐藏在模型中的 ID，将为您的域模型，透明，其基础结构实现无法在以后发生更改。</span><span class="sxs-lookup"><span data-stu-id="612fe-137">Since that configuration for hiding the ID in the model is set up in the infrastructure level, it will be transparent for your domain model, and its infrastructure implementation could change in the future.</span></span>

<span data-ttu-id="612fe-138">在 eShopOnContainers，EF 核心基础结构所需的隐藏的 ID 实现在 DbContext 级别中，按以下方式使用 Fluent API 的基础结构项目。</span><span class="sxs-lookup"><span data-stu-id="612fe-138">In eShopOnContainers, the hidden ID needed by EF Core infrastructure is implemented in the following way in the DbContext level, using Fluent API at the infrastructure project.</span></span>

```csharp
// Fluent API within the OrderingContext:DbContext in the
// Ordering.Infrastructure project

void ConfigureAddress(EntityTypeBuilder<Address> addressConfiguration)
{
    addressConfiguration.ToTable("address", DEFAULT_SCHEMA);
    addressConfiguration.Property<int>("Id").IsRequired();
    addressConfiguration.HasKey("Id");
}
```

<span data-ttu-id="612fe-139">因此，该 ID 隐藏的域模型角度来看，并在将来，值对象基础结构也都无法作为复杂类型或另一种方法实施。</span><span class="sxs-lookup"><span data-stu-id="612fe-139">Therefore, the ID is hidden from the domain model point of view, and in the future, the value object infrastructure could also be implemented as a complex type or another way.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="612fe-140">其他资源</span><span class="sxs-lookup"><span data-stu-id="612fe-140">Additional resources</span></span>

-   <span data-ttu-id="612fe-141">**Martin Fowler。ValueObject 模式**
    [*https://martinfowler.com/bliki/ValueObject.html*](https://martinfowler.com/bliki/ValueObject.html)</span><span class="sxs-lookup"><span data-stu-id="612fe-141">**Martin Fowler. ValueObject pattern**
[*https://martinfowler.com/bliki/ValueObject.html*](https://martinfowler.com/bliki/ValueObject.html)</span></span>

-   <span data-ttu-id="612fe-142">**Eric Evans。域驱动的设计： 解决软件核心的复杂性。**</span><span class="sxs-lookup"><span data-stu-id="612fe-142">**Eric Evans. Domain-Driven Design: Tackling Complexity in the Heart of Software.**</span></span> <span data-ttu-id="612fe-143">（本书; 包括的值对象的讨论）[ *https://www.amazon.com/Domain-Driven-Design-Tackling-Complexity-Software/dp/0321125215/*](https://www.amazon.com/Domain-Driven-Design-Tackling-Complexity-Software/dp/0321125215/)</span><span class="sxs-lookup"><span data-stu-id="612fe-143">(Book; includes a discussion of value objects) [*https://www.amazon.com/Domain-Driven-Design-Tackling-Complexity-Software/dp/0321125215/*](https://www.amazon.com/Domain-Driven-Design-Tackling-Complexity-Software/dp/0321125215/)</span></span>

-   <span data-ttu-id="612fe-144">**Vaughn Vernon。实现域驱动的设计。**</span><span class="sxs-lookup"><span data-stu-id="612fe-144">**Vaughn Vernon. Implementing Domain-Driven Design.**</span></span> <span data-ttu-id="612fe-145">（本书; 包括的值对象的讨论）[ *https://www.amazon.com/Implementing-Domain-Driven-Design-Vaughn-Vernon/dp/0321834577/*](https://www.amazon.com/Implementing-Domain-Driven-Design-Vaughn-Vernon/dp/0321834577/)</span><span class="sxs-lookup"><span data-stu-id="612fe-145">(Book; includes a discussion of value objects) [*https://www.amazon.com/Implementing-Domain-Driven-Design-Vaughn-Vernon/dp/0321834577/*](https://www.amazon.com/Implementing-Domain-Driven-Design-Vaughn-Vernon/dp/0321834577/)</span></span>

-   <span data-ttu-id="612fe-146">**隐藏属性**
    [*https://docs.microsoft.com/ef/core/modeling/shadow-properties*](https://docs.microsoft.com/ef/core/modeling/shadow-properties)</span><span class="sxs-lookup"><span data-stu-id="612fe-146">**Shadow Properties**
[*https://docs.microsoft.com/ef/core/modeling/shadow-properties*](https://docs.microsoft.com/ef/core/modeling/shadow-properties)</span></span>

-   <span data-ttu-id="612fe-147">**复杂类型和/或值对象**。</span><span class="sxs-lookup"><span data-stu-id="612fe-147">**Complex types and/or value objects**.</span></span> <span data-ttu-id="612fe-148">在 EF 核心 GitHub 存储库 （问题选项卡） 中的讨论[ *https://github.com/aspnet/EntityFramework/issues/246*](https://github.com/aspnet/EntityFramework/issues/246)</span><span class="sxs-lookup"><span data-stu-id="612fe-148">Discussion in the EF Core GitHub repo (Issues tab) [*https://github.com/aspnet/EntityFramework/issues/246*](https://github.com/aspnet/EntityFramework/issues/246)</span></span>

-   <span data-ttu-id="612fe-149">**ValueObject.cs。**</span><span class="sxs-lookup"><span data-stu-id="612fe-149">**ValueObject.cs.**</span></span> <span data-ttu-id="612fe-150">中 eShopOnContainers 基值对象类。</span><span class="sxs-lookup"><span data-stu-id="612fe-150">Base value object class in eShopOnContainers.</span></span>
    [<span data-ttu-id="612fe-151">*https://github.com/dotnet/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.Domain/SeedWork/ValueObject.cs*</span><span class="sxs-lookup"><span data-stu-id="612fe-151">*https://github.com/dotnet/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.Domain/SeedWork/ValueObject.cs*</span></span>](https://github.com/dotnet/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.Domain/SeedWork/ValueObject.cs)

-   <span data-ttu-id="612fe-152">**地址类别。**</span><span class="sxs-lookup"><span data-stu-id="612fe-152">**Address class.**</span></span> <span data-ttu-id="612fe-153">示例值中 eShopOnContainers 对象类。</span><span class="sxs-lookup"><span data-stu-id="612fe-153">Sample value object class in eShopOnContainers.</span></span>
    [<span data-ttu-id="612fe-154">*https://github.com/dotnet/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.Domain/AggregatesModel/OrderAggregate/Address.cs*</span><span class="sxs-lookup"><span data-stu-id="612fe-154">*https://github.com/dotnet/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.Domain/AggregatesModel/OrderAggregate/Address.cs*</span></span>](https://github.com/dotnet/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.Domain/AggregatesModel/OrderAggregate/Address.cs)


>[!div class="step-by-step"]
<span data-ttu-id="612fe-155">[以前](seedwork-domain-model-base-classes-interfaces.md) [下一步] (枚举-类-转移-枚举-types.md)</span><span class="sxs-lookup"><span data-stu-id="612fe-155">[Previous] (seedwork-domain-model-base-classes-interfaces.md) [Next] (enumeration-classes-over-enum-types.md)</span></span>
