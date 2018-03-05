---
title: "实现值对象"
description: "适用于容器化 .NET 应用程序的 .NET 微服务体系结构 | 实现值对象"
keywords: "Docker, 微服务, ASP.NET, 容器"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 12/12/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: e6ac6f2d316a94e69c2599acf07aaaf6361b3e5a
ms.sourcegitcommit: c3957fdb990060559d73cca44ab3e2c7b4d049c0
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/05/2018
---
# <a name="implementing-value-objects"></a><span data-ttu-id="bc3db-104">实现值对象</span><span class="sxs-lookup"><span data-stu-id="bc3db-104">Implementing value objects</span></span>

<span data-ttu-id="bc3db-105">如前面部分有关实体和聚合的讨论，标识对于实体是必不可少的。</span><span class="sxs-lookup"><span data-stu-id="bc3db-105">As discussed in earlier sections about entities and aggregates, identity is fundamental for entities.</span></span> <span data-ttu-id="bc3db-106">但是，系统中有许多对象和数据项不需要标识和标识跟踪，例如值对象。</span><span class="sxs-lookup"><span data-stu-id="bc3db-106">However, there are many objects and data items in a system that do not require an identity and identity tracking, such as value objects.</span></span>

<span data-ttu-id="bc3db-107">值对象可以引用其他实体。</span><span class="sxs-lookup"><span data-stu-id="bc3db-107">A value object can reference other entities.</span></span> <span data-ttu-id="bc3db-108">例如，在生成描述如何从一个点转到另一点的路由时，该路由应为值对象。</span><span class="sxs-lookup"><span data-stu-id="bc3db-108">For example, in an application that generates a route that describes how to get from one point to another, that route would be a value object.</span></span> <span data-ttu-id="bc3db-109">它将是特定路由上的点的快照，但此建议的路由将不具有标识，即使在内部它可能指 City、Road 等实体。</span><span class="sxs-lookup"><span data-stu-id="bc3db-109">It would be a snapshot of points on a specific route, but this suggested route would not have an identity, even though internally it might refer to entities like City, Road, etc.</span></span>

<span data-ttu-id="bc3db-110">图 9-13 显示 Order 聚合中的 Address 值对象。</span><span class="sxs-lookup"><span data-stu-id="bc3db-110">Figure 9-13 shows the Address value object within the Order aggregate.</span></span>

![](./media/image14.png)

<span data-ttu-id="bc3db-111">图 9-13。</span><span class="sxs-lookup"><span data-stu-id="bc3db-111">**Figure 9-13**.</span></span> <span data-ttu-id="bc3db-112">Order 聚合中的 Address 值对象</span><span class="sxs-lookup"><span data-stu-id="bc3db-112">Address value object within the Order aggregate</span></span>

<span data-ttu-id="bc3db-113">如图 9-13 所示，实体通常由多个属性组成。</span><span class="sxs-lookup"><span data-stu-id="bc3db-113">As shown in Figure 9-13, an entity is usually composed of multiple attributes.</span></span> <span data-ttu-id="bc3db-114">例如，`Order` 实体可以建模为具有标识的实体，在内部由一组特性组成，例如 OrderId、OrderDate、OrderItems 等。但地址这个作为由国家/地区、街道、城市等组成的复杂值，必须建模或处理为值对象。</span><span class="sxs-lookup"><span data-stu-id="bc3db-114">For example, the `Order` entity can be modeled as an entity with an identity and composed internally of a set of attributes such as OrderId, OrderDate, OrderItems, etc. But the address, which is simply a complex value composed of country, street, city, etc. and has no identity in this domain,  must be modeled and treated as a value object.</span></span>

## <a name="important-characteristics-of-value-objects"></a><span data-ttu-id="bc3db-115">值对象的重要特征</span><span class="sxs-lookup"><span data-stu-id="bc3db-115">Important characteristics of value objects</span></span>

<span data-ttu-id="bc3db-116">值对象有两个主要特征：</span><span class="sxs-lookup"><span data-stu-id="bc3db-116">There are two main characteristics for value objects:</span></span>

-   <span data-ttu-id="bc3db-117">它们没有任何标识。</span><span class="sxs-lookup"><span data-stu-id="bc3db-117">They have no identity.</span></span>

-   <span data-ttu-id="bc3db-118">它们是不可变的。</span><span class="sxs-lookup"><span data-stu-id="bc3db-118">They are immutable.</span></span>

<span data-ttu-id="bc3db-119">第一个特征上面讨论了。</span><span class="sxs-lookup"><span data-stu-id="bc3db-119">The first characteristic was already discussed.</span></span> <span data-ttu-id="bc3db-120">不可变性是一个重要要求。</span><span class="sxs-lookup"><span data-stu-id="bc3db-120">Immutability is an important requirement.</span></span> <span data-ttu-id="bc3db-121">创建对象后，值对象的值必须是不可变的。</span><span class="sxs-lookup"><span data-stu-id="bc3db-121">The values of a value object must be immutable once the object is created.</span></span> <span data-ttu-id="bc3db-122">因此，当构造对象时，必须提供所需的值，但不得允许它们在对象生存期内进行更改。</span><span class="sxs-lookup"><span data-stu-id="bc3db-122">Therefore, when the object is constructed, you must provide the required values, but you must not allow them to change during the object’s lifetime.</span></span>

<span data-ttu-id="bc3db-123">因其不可变性，值对象允许采取某些技巧来提升性能。</span><span class="sxs-lookup"><span data-stu-id="bc3db-123">Value objects allow you to perform certain tricks for performance, thanks to their immutable nature.</span></span> <span data-ttu-id="bc3db-124">当系统有成千上万个值对象实例且其中很多具有相同值时，这特别有用。</span><span class="sxs-lookup"><span data-stu-id="bc3db-124">This is especially true in systems where there may be thousands of value object instances, many of which have the same values.</span></span> <span data-ttu-id="bc3db-125">不可变本质使它们可以重用；它们可以是可互换对象，因为值都相同，且没有任何标识。</span><span class="sxs-lookup"><span data-stu-id="bc3db-125">Their immutable nature allows them to be reused; they can be interchangeable objects, since their values are the same and they have no identity.</span></span> <span data-ttu-id="bc3db-126">有时，这种优化可以在运行缓慢的软件和性能良好的软件之间制造差异。</span><span class="sxs-lookup"><span data-stu-id="bc3db-126">This type of optimization can sometimes make a difference between software that runs slowly and software with good performance.</span></span> <span data-ttu-id="bc3db-127">当然，所有这些将取决于应用程序环境和部署上下文。</span><span class="sxs-lookup"><span data-stu-id="bc3db-127">Of course, all these cases depend on the application environment and deployment context.</span></span>

## <a name="value-object-implementation-in-c"></a><span data-ttu-id="bc3db-128">C\# 中的值对象实现</span><span class="sxs-lookup"><span data-stu-id="bc3db-128">Value object implementation in C\#</span></span>

<span data-ttu-id="bc3db-129">就实现而言，你可以拥有值对象基类，它具有基于所有特性（因值对象不得基于标识）和其他基本特征间的对比的基本实用工具方法，如相等。</span><span class="sxs-lookup"><span data-stu-id="bc3db-129">In terms of implementation, you can have a value object base class that has basic utility methods like equality based on comparison between all the attributes (since a value object must not be based on identity) and other fundamental characteristics.</span></span> <span data-ttu-id="bc3db-130">下面的示例演示用于 eShopOnContainers 订购微服务中的值对象基类。</span><span class="sxs-lookup"><span data-stu-id="bc3db-130">The following example shows a value object base class used in the ordering microservice from eShopOnContainers.</span></span>

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

<span data-ttu-id="bc3db-131">实现实际值对象时可以使用此类，如下面实例中显示的 Address 值对象：</span><span class="sxs-lookup"><span data-stu-id="bc3db-131">You can use this class when implementing your actual value object, as with the Address value object shown in the following example:</span></span>

```csharp
public class Address : ValueObject
{
    public String Street { get; private set; }
    public String City { get; private set; }
    public String State { get; private set; }
    public String Country { get; private set; }
    public String ZipCode { get; private set; }

    private Address() { }

    public Address(string street, string city, string state, string country, string zipcode)
    {
        Street = street;
        City = city;
        State = state;
        Country = country;
        ZipCode = zipcode;
    }

    protected override IEnumerable<object> GetAtomicValues()
    {
        // Using a yield return statement to return each element one at a time
        yield return Street;
        yield return City;
        yield return State;
        yield return Country;
        yield return ZipCode;
    }
}
```

## <a name="how-to-persist-value-objects-in-the-database-with-ef-core-20"></a><span data-ttu-id="bc3db-132">如何通过 EF Core 2.0 在数据库中持久保存值对象</span><span class="sxs-lookup"><span data-stu-id="bc3db-132">How to persist value objects in the database with EF Core 2.0</span></span>

<span data-ttu-id="bc3db-133">你刚才看到如何在域模型中定义值对象。</span><span class="sxs-lookup"><span data-stu-id="bc3db-133">You just saw how to define a value object in your domain model.</span></span> <span data-ttu-id="bc3db-134">但是，如何切实地通过一般使用标识确定实体的 Entity Framework (EF) Core 来将其持久保存在数据库中呢？</span><span class="sxs-lookup"><span data-stu-id="bc3db-134">But, how can you actually persist it into the database through Entity Framework (EF) Core which usually targets entities with identity?</span></span>

### <a name="background-and-older-approaches-using-ef-core-11"></a><span data-ttu-id="bc3db-135">背景和较早的方法（使用 EF Core 1.1）</span><span class="sxs-lookup"><span data-stu-id="bc3db-135">Background and older approaches using EF Core 1.1</span></span>

<span data-ttu-id="bc3db-136">背景：使用 EF Core 1.0 和 1.1 版时的限制是不能使用传统 .NET Framework 的 EF 6.x 中所定义的[复杂类型](xref:System.ComponentModel.DataAnnotations.Schema.ComplexTypeAttribute)。</span><span class="sxs-lookup"><span data-stu-id="bc3db-136">As background, a limitation when using EF Core 1.0 and 1.1 was that you cannot use  [complex types](xref:System.ComponentModel.DataAnnotations.Schema.ComplexTypeAttribute) as defined in EF 6.x in the traditional .NET Framework.</span></span> <span data-ttu-id="bc3db-137">因此，如果使用 EF Core 1.0 或 1.1，则需要将值对象存储为具有 ID 字段的 EF 实体。</span><span class="sxs-lookup"><span data-stu-id="bc3db-137">Therefore, if using EF Core 1.0 or 1.1, you needed to store your value object as an EF entity with an ID field.</span></span> <span data-ttu-id="bc3db-138">然后，为使它看起来像没有任何标识的值对象，你可以隐藏其 ID：表明值对象的标识在域模型中不重要。</span><span class="sxs-lookup"><span data-stu-id="bc3db-138">Then, so it looked more like a value object with no identity, you could hide its ID so you make clear that the identity of a value object is not important in the domain model.</span></span> <span data-ttu-id="bc3db-139">可以通过将该 ID 用作[阴影属性](https://docs.microsoft.com/ef/core/modeling/shadow-properties )来隐藏其 ID。</span><span class="sxs-lookup"><span data-stu-id="bc3db-139">You could hide that ID by using the ID as a [shadow property](https://docs.microsoft.com/ef/core/modeling/shadow-properties ).</span></span> <span data-ttu-id="bc3db-140">由于在模型中隐藏 ID 的配置是在 EF 基础结构级别中设置的，ID 对于域模型好似透明的。</span><span class="sxs-lookup"><span data-stu-id="bc3db-140">Since that configuration for hiding the ID in the model is set up in the EF infrastructure level, it would be kind of transparent for your domain model.</span></span>

<span data-ttu-id="bc3db-141">在 eShopOnContainers (.NET Core 1.1) 的初始版本中，EF Core 基础结构所需的隐藏 ID 在 DbContext 级别上采用基础结构项目中的 Fluent API 通过以下方式来实现。</span><span class="sxs-lookup"><span data-stu-id="bc3db-141">In the initial version of eShopOnContainers (.NET Core 1.1), the hidden ID needed by EF Core infrastructure was implemented in the following way in the DbContext level, using Fluent API at the infrastructure project.</span></span> <span data-ttu-id="bc3db-142">因此，该 ID 从域模型角度看是隐藏的，但仍存于基础结构中。</span><span class="sxs-lookup"><span data-stu-id="bc3db-142">Therefore, the ID was hidden from the domain model point of view, but still present in the infrastructure.</span></span>

```csharp
// Old approach with EF Core 1.1
// Fluent API within the OrderingContext:DbContext in the Infrastructure project
void ConfigureAddress(EntityTypeBuilder<Address> addressConfiguration) 
{
    addressConfiguration.ToTable("address", DEFAULT_SCHEMA); 

    addressConfiguration.Property<int>("Id")  // Id is a shadow property
        .IsRequired();
    addressConfiguration.HasKey("Id");   // Id is a shadow property
}
```

<span data-ttu-id="bc3db-143">但是，将值对象持久保存在数据库中执行起来如同将常规实体持久保存在不同表中。</span><span class="sxs-lookup"><span data-stu-id="bc3db-143">However, the persistence of that value object into the database was performed like a regular entity in a different table.</span></span>

<span data-ttu-id="bc3db-144">使用 EF Core 2.0 时，有更好的新方法来持久保存值对象。</span><span class="sxs-lookup"><span data-stu-id="bc3db-144">With EF Core 2.0, there are new and better ways to persist value objects.</span></span>

## <a name="persist-value-objects-as-owned-entity-types-in-ef-core-20"></a><span data-ttu-id="bc3db-145">在 EF Core 2.0 中以固有实体类型形式来持久保存值对象</span><span class="sxs-lookup"><span data-stu-id="bc3db-145">Persist value objects as owned entity types in EF Core 2.0</span></span>

<span data-ttu-id="bc3db-146">即使 EF Core 中的固有实体类型与 DDD 中的规范值对象模式之间存在一些差距，当前它是在 EF Core 2.0 中持久保存值对象的最佳方式。</span><span class="sxs-lookup"><span data-stu-id="bc3db-146">Even with some gaps between the canonical value object pattern in DDD and the owned entity type in EF Core, it's currently the best way to persist value objects with EF Core 2.0.</span></span> <span data-ttu-id="bc3db-147">将在本部分末尾看到限制。</span><span class="sxs-lookup"><span data-stu-id="bc3db-147">You can see limitations at the end of this section.</span></span>

<span data-ttu-id="bc3db-148">固有实体类型功能已添加到 EF Core 2.0 及以上版本。</span><span class="sxs-lookup"><span data-stu-id="bc3db-148">The owned entity type feature was added to EF Core since version 2.0.</span></span>

<span data-ttu-id="bc3db-149">固有实体类型允许在任何实体内映射具有以下特征的类型：用作属性且不具有在域模型中显式定义的自己的标识，如值对象。</span><span class="sxs-lookup"><span data-stu-id="bc3db-149">An owned entity type allows you to map types that do not have their own identity explicitely defined in the domain model and are used as properties, such as a value object, within any of your entities.</span></span> <span data-ttu-id="bc3db-150">固有实体类型与其他实体类型共享相同的 CLR 类型。</span><span class="sxs-lookup"><span data-stu-id="bc3db-150">An owned entity type shares the same CLR type with another entity type.</span></span> <span data-ttu-id="bc3db-151">包含定义性导航的实体是所有者实体。</span><span class="sxs-lookup"><span data-stu-id="bc3db-151">The entity containing the defining navigation is the owner entity.</span></span> <span data-ttu-id="bc3db-152">查询所有者时，固有类型将默认包含在内。</span><span class="sxs-lookup"><span data-stu-id="bc3db-152">When querying the owner, the owned types are included by default.</span></span>

<span data-ttu-id="bc3db-153">查看一下域模型，固有类型看上去似乎没有任何标识。</span><span class="sxs-lookup"><span data-stu-id="bc3db-153">Just by looking at the domain model, an owned type looks like it doesn’t have any identity.</span></span>
<span data-ttu-id="bc3db-154">但是事实上，固有类型确有标识，但所有者导航属性为此标识的一部分。</span><span class="sxs-lookup"><span data-stu-id="bc3db-154">However, under the covers, owned types do have identity, but the owner navigation property is part of this identity.</span></span>

<span data-ttu-id="bc3db-155">自己的类型的实例的标识不完全是自己的。</span><span class="sxs-lookup"><span data-stu-id="bc3db-155">The identity of instances of own types is not completely their own.</span></span> <span data-ttu-id="bc3db-156">它由三个部分组成：</span><span class="sxs-lookup"><span data-stu-id="bc3db-156">It consists of three components:</span></span>

- <span data-ttu-id="bc3db-157">所有者标识</span><span class="sxs-lookup"><span data-stu-id="bc3db-157">The identity of the owner</span></span>

- <span data-ttu-id="bc3db-158">指向它们的导航属性</span><span class="sxs-lookup"><span data-stu-id="bc3db-158">The navigation property pointing to them</span></span>

- <span data-ttu-id="bc3db-159">对于固有类型的集合，一个独立的组成部分（EF Core 2.0 中尚不支持）。</span><span class="sxs-lookup"><span data-stu-id="bc3db-159">In the case of collections of owned types, an independent component (not yet supported in EF Core 2.0).</span></span>

<span data-ttu-id="bc3db-160">例如，在 eShopOnContainers 的订购域模型中，作为 Order 实体的一部分，Address 值对象在所有者实体（即 Order 实体）内作为固有实体类型实现。</span><span class="sxs-lookup"><span data-stu-id="bc3db-160">For example, in the Ordering domain model at eShopOnContainers, as part of the Order entity, the Address value object is implemented as an owned entity type within the owner entity, which is the Order entity.</span></span> <span data-ttu-id="bc3db-161">Address 是域模型中定义的没有标识属性的类型。</span><span class="sxs-lookup"><span data-stu-id="bc3db-161">Address is a type with no identity property defined in the domain model.</span></span> <span data-ttu-id="bc3db-162">它用作 Order 类型的属性来指定特定订单的发货地址。</span><span class="sxs-lookup"><span data-stu-id="bc3db-162">It is used as a property of the Order type to specify the shipping address for a particular order.</span></span>

<span data-ttu-id="bc3db-163">依照约定，将为固有类型创建一个阴影主键，并通过表拆分将其映射到与所有者相同的表。</span><span class="sxs-lookup"><span data-stu-id="bc3db-163">By convention, a shadow primary key is created for the owned type and it will be mapped to the same table as the owner by using table splitting.</span></span> <span data-ttu-id="bc3db-164">这样就可以通过类似于传统 .NET Framework 的 EF6 中复杂类型的用法来使用固有类型。</span><span class="sxs-lookup"><span data-stu-id="bc3db-164">This allows to use owned types similarly to how complex types are used in EF6 in the traditional .NET Framework.</span></span>

<span data-ttu-id="bc3db-165">请务必注意，固有类型在 EF Core 中永远不会由约定发现，因此你必须显式声明它们。</span><span class="sxs-lookup"><span data-stu-id="bc3db-165">It is important to note that owned types are never discovered by convention in EF Core, so you have to declare them explicitly.</span></span>

<span data-ttu-id="bc3db-166">在 eShopOnContainers 的 OrderingContext.cs 中，在 OnModelCreating() 方法内，应用了多个基础结构配置。</span><span class="sxs-lookup"><span data-stu-id="bc3db-166">In eShopOnContainers, at the OrderingContext.cs, within the OnModelCreating() method, there are multiple infrastructure configuration being applied.</span></span> <span data-ttu-id="bc3db-167">其中之一与 Order 实体相关。</span><span class="sxs-lookup"><span data-stu-id="bc3db-167">One of them is related to the Order entity.</span></span>

```csharp
// Part of the OrderingContext.cs class at the Ordering.Infrastructure project
// 
protected override void OnModelCreating(ModelBuilder modelBuilder)
{
    modelBuilder.ApplyConfiguration(new ClientRequestEntityTypeConfiguration());
    modelBuilder.ApplyConfiguration(new PaymentMethodEntityTypeConfiguration());
    modelBuilder.ApplyConfiguration(new OrderEntityTypeConfiguration());
    modelBuilder.ApplyConfiguration(new OrderItemEntityTypeConfiguration());
    //...Additional type configurations
}
```

<span data-ttu-id="bc3db-168">在下面的代码中，针对 Order 实体定义了持久性基础结构：</span><span class="sxs-lookup"><span data-stu-id="bc3db-168">In the following code, the persistence infrastructure is defined for the Order entity:</span></span>

```csharp
// Part of the OrderEntityTypeConfiguration.cs class 
// 
public void Configure(EntityTypeBuilder<Order> orderConfiguration)
{
    orderConfiguration.ToTable("orders", OrderingContext.DEFAULT_SCHEMA);
    orderConfiguration.HasKey(o => o.Id);
    orderConfiguration.Ignore(b => b.DomainEvents);
    orderConfiguration.Property(o => o.Id)
        .ForSqlServerUseSequenceHiLo("orderseq", OrderingContext.DEFAULT_SCHEMA);

    //Address value object persisted as owned entity in EF Core 2.0
    orderConfiguration.OwnsOne(o => o.Address);

    orderConfiguration.Property<DateTime>("OrderDate").IsRequired();
    
    //...Additional validations, constraints and code...
    //...
}
```

<span data-ttu-id="bc3db-169">在前面的代码中，`orderConfiguration.OwnsOne(o => o.Address)` 方法指定了 `Address` 属性是 `Order` 类型的固有实体。</span><span class="sxs-lookup"><span data-stu-id="bc3db-169">In the previous code, the `orderConfiguration.OwnsOne(o => o.Address)` method specifies that the `Address` property is an owned entity of the `Order` type.</span></span>

<span data-ttu-id="bc3db-170">默认情况下，EF Core 约定将固有实体类型属性的数据库列命名为 `EntityProperty_OwnedEntityProperty`。</span><span class="sxs-lookup"><span data-stu-id="bc3db-170">By default, EF Core conventions name the database columns for the properties of the owned entity type as `EntityProperty_OwnedEntityProperty`.</span></span> <span data-ttu-id="bc3db-171">因此，`Address` 的内部属性将以 `Address_Street`、`Address_City` 这样的名称（对于 `State``Country` 和 `ZipCode` 可进行类推）出现在 `Orders` 表中。</span><span class="sxs-lookup"><span data-stu-id="bc3db-171">Therefore, the internal properties of `Address` will appear in the `Orders` table with the names `Address_Street`, `Address_City` (and so on for `State`, `Country` and `ZipCode`).</span></span>

<span data-ttu-id="bc3db-172">可以附加 `Property().HasColumnName()` 连贯性方法来重命名这些列。</span><span class="sxs-lookup"><span data-stu-id="bc3db-172">You can append the `Property().HasColumnName()` fluent method to rename those columns.</span></span> <span data-ttu-id="bc3db-173">如果 `Address` 是公共属性，映射将如下所示：</span><span class="sxs-lookup"><span data-stu-id="bc3db-173">In the case where `Address` is a public property, the mappings would be like the following:</span></span>

```csharp
orderConfiguration.OwnsOne(p => p.Address)
                            .Property(p=>p.Street).HasColumnName("ShippingStreet");

orderConfiguration.OwnsOne(p => p.Address)
                            .Property(p=>p.City).HasColumnName("ShippingCity");
```

<span data-ttu-id="bc3db-174">可以将 `OwnsOne` 方法链接到连贯性映射。</span><span class="sxs-lookup"><span data-stu-id="bc3db-174">It is possible to chain the `OwnsOne` method in a fluent mapping.</span></span> <span data-ttu-id="bc3db-175">在以下假设示例中，`OrderDetails` 拥有 `BillingAddress` 和 `ShippingAddress`，它们均为 `Address` 类型。</span><span class="sxs-lookup"><span data-stu-id="bc3db-175">In the following hypothetical example, `OrderDetails` owns `BillingAddress` and `ShippingAddress`, which are both `Address` types.</span></span> <span data-ttu-id="bc3db-176">然后 `OrderDetails` 归 `Order` 类型所有。</span><span class="sxs-lookup"><span data-stu-id="bc3db-176">Then `OrderDetails` is owned by the `Order` type.</span></span>

```csharp
orderConfiguration.OwnsOne(p => p.OrderDetails, cb =>
    {
        cb.OwnsOne(c => c.BillingAddress);
        cb.OwnsOne(c => c.ShippingAddress);
    });
//...
//...
public class Order
{
    public int Id { get; set; }
    public OrderDetails OrderDetails { get; set; }
}

public class OrderDetails
{
    public Address BillingAddress { get; set; }
    public Address ShippingAddress { get; set; }
}

public class Address
{
    public string Street { get; set; }
    public string City { get; set; }
}
```

### <a name="additional-details-on-owned-entity-types"></a><span data-ttu-id="bc3db-177">固有实体类型上的其他详细信息</span><span class="sxs-lookup"><span data-stu-id="bc3db-177">Additional details on owned entity types</span></span>

<span data-ttu-id="bc3db-178">•   使用 OwnsOne Fluent API 将导航属性配置为特定类型时即定义固有类型。</span><span class="sxs-lookup"><span data-stu-id="bc3db-178">•   Owned types are defined when you configure a navigation property to a particular type using the OwnsOne fluent API.</span></span>

<span data-ttu-id="bc3db-179">•   我们元数据模型中固有类型的定义为以下各项的组合：所有者类型、导航属性，以及固有类型的 CLR 类型。</span><span class="sxs-lookup"><span data-stu-id="bc3db-179">•   The definition of an owned type in our metadata model is a composite of: the owner type, the navigation property, and the CLR type of the owned type.</span></span>

<span data-ttu-id="bc3db-180">•   我们堆栈中固有类型实例的标识（键）即为所有者类型标识和固有类型定义的组合。</span><span class="sxs-lookup"><span data-stu-id="bc3db-180">•   The identity (key) of an owned type instance in our stack is a composite of the identity of the owner type and the definition of the owned type.</span></span>

#### <a name="owned-entities-capabilities"></a><span data-ttu-id="bc3db-181">固有实体功能：</span><span class="sxs-lookup"><span data-stu-id="bc3db-181">Owned entities capabilities:</span></span>

<span data-ttu-id="bc3db-182">•   固有类型可以引用其他实体，固有（嵌套固有类型）或非固有（其他实体的常规引用导航属性）均可。</span><span class="sxs-lookup"><span data-stu-id="bc3db-182">•   Owned type can reference other entities, either owned (nested owned types) or non-owned (regular reference navigation properties to other entities).</span></span>

<span data-ttu-id="bc3db-183">•   可以通过单独的导航属性在同一所有者实体中以不同固有类型的形式来映射相同的 CLR 类型。</span><span class="sxs-lookup"><span data-stu-id="bc3db-183">•   You can map the same CLR type as different owned types in the same owner entity through separate navigation properties.</span></span>

<span data-ttu-id="bc3db-184">•   表拆分由约定设置，但可以通过使用 ToTable 将固有类型映射到其他表来另行选择。</span><span class="sxs-lookup"><span data-stu-id="bc3db-184">•   Table splitting is setup by convention, but you can opt out by mapping the owned type to a different table using ToTable.</span></span>

<span data-ttu-id="bc3db-185">•   立即加载对于固有类型自动执行，即无需对查询调用 Include()。</span><span class="sxs-lookup"><span data-stu-id="bc3db-185">•   Eager loading is performed automatically on owned types, i.e. no need to call Include() on the query.</span></span>

#### <a name="owned-entities-limitations"></a><span data-ttu-id="bc3db-186">固有实体的限制：</span><span class="sxs-lookup"><span data-stu-id="bc3db-186">Owned entities limitations:</span></span>

<span data-ttu-id="bc3db-187">•   不能创建固有类型的 DbSet<T>（按照设计）。</span><span class="sxs-lookup"><span data-stu-id="bc3db-187">•   You cannot create a DbSet<T> of an owned type (by design).</span></span>

<span data-ttu-id="bc3db-188">•   不能在固有类型上调用 ModelBuilder.Entity<T>()（当前按照设计）。</span><span class="sxs-lookup"><span data-stu-id="bc3db-188">•   You cannot call ModelBuilder.Entity<T>() on owned types (currently by design).</span></span>

<span data-ttu-id="bc3db-189">•   尚且没有固有类型的集合（但在 EF Core 2.0 之后的版本会支持）。</span><span class="sxs-lookup"><span data-stu-id="bc3db-189">•   No collections of owned types yet (but they will be supported in versions after EF Core 2.0).</span></span>

<span data-ttu-id="bc3db-190">•   不支持通过特性对它们进行配置。</span><span class="sxs-lookup"><span data-stu-id="bc3db-190">•   No support for configuring them via an attribute.</span></span>

<span data-ttu-id="bc3db-191">•   不支持使用同一表格中所有者映射的可选（即可以为 null）固有类型（即使用表格拆分）。</span><span class="sxs-lookup"><span data-stu-id="bc3db-191">•   No support for optional (i.e. nullable) owned types that are mapped with the owner in the same table (i.e. using table splitting).</span></span> <span data-ttu-id="bc3db-192">这是因为我们对 null 没有单独的 sentinel。</span><span class="sxs-lookup"><span data-stu-id="bc3db-192">This is because we don't have a separate sentinel for the null.</span></span>

<span data-ttu-id="bc3db-193">•   没有对固有类型的继承映射支持，但应能够以不同固有类型的形式映射同一继承层次结构的两个叶类型。</span><span class="sxs-lookup"><span data-stu-id="bc3db-193">•   No inheritance mapping support for owned types, but you should be able to map two leaf types of the same inheritance hierarchies as different owned types.</span></span> <span data-ttu-id="bc3db-194">EF Core 不会就它们不属于同一层次结构的事实进行推断。</span><span class="sxs-lookup"><span data-stu-id="bc3db-194">EF Core will not reason about the fact that they are part of the same hierarchy.</span></span>

#### <a name="main-differences-with-ef6s-complex-types"></a><span data-ttu-id="bc3db-195">与 EF6 的复杂类型的主要差异</span><span class="sxs-lookup"><span data-stu-id="bc3db-195">Main differences with EF6's complex types</span></span>

<span data-ttu-id="bc3db-196">•   表拆分是可选的，即可以根据需要将它们映射到单独的表并仍属固有类型。</span><span class="sxs-lookup"><span data-stu-id="bc3db-196">•   Table splitting is optional, i.e. they can optionally be mapped to a separate table and still be owned types.</span></span>

<span data-ttu-id="bc3db-197">•   它们可以引用其他实体（即它们可以充当关系上其他非固有类型的依赖端）。</span><span class="sxs-lookup"><span data-stu-id="bc3db-197">•   They can reference other entities (i.e. they can act as the dependent side on relationships to other non-owned types).</span></span>


## <a name="additional-resources"></a><span data-ttu-id="bc3db-198">其他资源</span><span class="sxs-lookup"><span data-stu-id="bc3db-198">Additional resources</span></span>

-   <span data-ttu-id="bc3db-199">**Martin Fowler。ValueObject 模式**
    [https://martinfowler.com/bliki/ValueObject.html](https://martinfowler.com/bliki/ValueObject.html)</span><span class="sxs-lookup"><span data-stu-id="bc3db-199">**Martin Fowler. ValueObject pattern**
[*https://martinfowler.com/bliki/ValueObject.html*](https://martinfowler.com/bliki/ValueObject.html)</span></span>

-   <span data-ttu-id="bc3db-200">**Eric Evans。Domain-Driven Design: Tackling Complexity in the Heart of Software.**（域驱动设计：软件核心复杂性应对之道。）</span><span class="sxs-lookup"><span data-stu-id="bc3db-200">**Eric Evans. Domain-Driven Design: Tackling Complexity in the Heart of Software.**</span></span> <span data-ttu-id="bc3db-201">（书籍，包括对值对象的讨论）[https://www.amazon.com/Domain-Driven-Design-Tackling-Complexity-Software/dp/0321125215/](https://www.amazon.com/Domain-Driven-Design-Tackling-Complexity-Software/dp/0321125215/)</span><span class="sxs-lookup"><span data-stu-id="bc3db-201">(Book; includes a discussion of value objects) [*https://www.amazon.com/Domain-Driven-Design-Tackling-Complexity-Software/dp/0321125215/*](https://www.amazon.com/Domain-Driven-Design-Tackling-Complexity-Software/dp/0321125215/)</span></span>

-   <span data-ttu-id="bc3db-202">**Vaughn Vernon。实现域驱动设计。**</span><span class="sxs-lookup"><span data-stu-id="bc3db-202">**Vaughn Vernon. Implementing Domain-Driven Design.**</span></span> <span data-ttu-id="bc3db-203">（书籍，包括对值对象的讨论）[https://www.amazon.com/Implementing-Domain-Driven-Design-Vaughn-Vernon/dp/0321834577/](https://www.amazon.com/Implementing-Domain-Driven-Design-Vaughn-Vernon/dp/0321834577/)</span><span class="sxs-lookup"><span data-stu-id="bc3db-203">(Book; includes a discussion of value objects) [*https://www.amazon.com/Implementing-Domain-Driven-Design-Vaughn-Vernon/dp/0321834577/*](https://www.amazon.com/Implementing-Domain-Driven-Design-Vaughn-Vernon/dp/0321834577/)</span></span>

-   <span data-ttu-id="bc3db-204">**阴影属性**
    [https://docs.microsoft.com/ef/core/modeling/shadow-properties](https://docs.microsoft.com/ef/core/modeling/shadow-properties)</span><span class="sxs-lookup"><span data-stu-id="bc3db-204">**Shadow Properties**
[*https://docs.microsoft.com/ef/core/modeling/shadow-properties*](https://docs.microsoft.com/ef/core/modeling/shadow-properties)</span></span>

-   <span data-ttu-id="bc3db-205">**复杂类型和/或值对象**。</span><span class="sxs-lookup"><span data-stu-id="bc3db-205">**Complex types and/or value objects**.</span></span> <span data-ttu-id="bc3db-206">EF Core GitHub 存储库（“问题”标签页）中的讨论[https://github.com/aspnet/EntityFramework/issues/246](https://github.com/aspnet/EntityFramework/issues/246)</span><span class="sxs-lookup"><span data-stu-id="bc3db-206">Discussion in the EF Core GitHub repo (Issues tab) [*https://github.com/aspnet/EntityFramework/issues/246*](https://github.com/aspnet/EntityFramework/issues/246)</span></span>

-   <span data-ttu-id="bc3db-207">**ValueObject.cs.**</span><span class="sxs-lookup"><span data-stu-id="bc3db-207">**ValueObject.cs.**</span></span> <span data-ttu-id="bc3db-208">eShopOnContainers 中的基值对象类。</span><span class="sxs-lookup"><span data-stu-id="bc3db-208">Base value object class in eShopOnContainers.</span></span>
    [<span data-ttu-id="bc3db-209">https://github.com/dotnet/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.Domain/SeedWork/ValueObject.cs</span><span class="sxs-lookup"><span data-stu-id="bc3db-209">*https://github.com/dotnet/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.Domain/SeedWork/ValueObject.cs*</span></span>](https://github.com/dotnet/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.Domain/SeedWork/ValueObject.cs)

-   <span data-ttu-id="bc3db-210">**地址类。**</span><span class="sxs-lookup"><span data-stu-id="bc3db-210">**Address class.**</span></span> <span data-ttu-id="bc3db-211">eShopOnContainers 中的示例值对象类。</span><span class="sxs-lookup"><span data-stu-id="bc3db-211">Sample value object class in eShopOnContainers.</span></span>
    [<span data-ttu-id="bc3db-212">https://github.com/dotnet/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.Domain/AggregatesModel/OrderAggregate/Address.cs</span><span class="sxs-lookup"><span data-stu-id="bc3db-212">*https://github.com/dotnet/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.Domain/AggregatesModel/OrderAggregate/Address.cs*</span></span>](https://github.com/dotnet/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.Domain/AggregatesModel/OrderAggregate/Address.cs)



>[!div class="step-by-step"]
<span data-ttu-id="bc3db-213">[上一页] (seedwork-domain-model-base-classes-interfaces.md) [下一页] (enumeration-classes-over-enum-types.md)</span><span class="sxs-lookup"><span data-stu-id="bc3db-213">[Previous] (seedwork-domain-model-base-classes-interfaces.md) [Next] (enumeration-classes-over-enum-types.md)</span></span>
