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
# <a name="implementing-value-objects"></a>实现值对象

在前面部分中讨论有关实体和聚合，标识是必不可少的实体。 但是，有许多对象和数据项不需要的标识和跟踪，例如值中的对象的标识的系统中。

值对象可以引用其他实体。 例如，在应用程序生成的路由，介绍如何从一个点来访问另一个字符串，该路由将值对象。 它将特定的路由上的点的快照，但此建议的路由将不具有有标识，即使它可能是内部指如市/县、 道路等实体。

图 9-13 显示顺序聚合中的地址值对象。

![](./media/image14.png)

**图 9-13**。 解决顺序聚合中的值对象

如所示图 9-13，实体通常由多个属性。 例如，可以建模为具有标识的实体顺序，将其内部组成的一组特性，例如 OrderId、 OrderDate、 OrderItems，等等。但组成国家/地区，街道、 城市的地址，这是只是一个复杂的值，必须建模等，并将其视为值对象。

## <a name="important-characteristics-of-value-objects"></a>值对象的重要特征

有两个值对象的主要特征：

-   它们具有任何标识。

-   它们是不可变。

已讨论的第一个特性。 不可变性是一个重要要求。 在创建对象后，值对象的值必须是不可变。 因此，当构造对象时，你必须提供所需的值，但则不能允许对其进行更改的对象的生存期内。

值对象，可以为性能，其不可变的性质感谢执行某些技巧。 这是系统中尤其如此其中可能有数千个值对象实例，其中的许多具有相同的值。 不可变本质使他们可以重用;它们可以是可互换的对象，因为它们的值都相同，并且它们具有任何标识。 有时，这种优化可以使运行速度慢的软件和软件性能良好之间存在的差异。 当然，，所有这些情况下将取决于应用程序环境以及部署上下文。

## <a name="value-object-implementation-in-c"></a>在 C 中的值对象实现\#

根据实现中，你可以具有等基于比较 （因为值对象不必须基于标识） 的所有属性和其他基本特征之间的相等性的基本实用程序方法的值对象基本类。 下面的示例演示在从 eShopOnContainers 排序微服务中使用的值对象基本类。

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

你可以使用此类时实现你实际值的对象，如下面的示例中显示的地址值对象：

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

## <a name="hiding-the-identity-characteristic-when-using-ef-core-to-persist-value-objects"></a>隐藏的标识特征时使用 EF 核心持久保存值对象

限制时使用 EF 核心，其当前版本 (EF 核心 1.1) 中不能使用[复杂类型](https://docs.microsoft.com/de-de/dotnet/api/system.componentmodel.dataannotations.schema.complextypeattribute?view=netframework-4.7)EF 中定义 6.x。 因此，你必须为 EF 实体来存储值对象。 但是，可以隐藏其 ID，因此你进行清除的标识不重要的模型的值对象中。 隐藏 ID 是作为卷影属性使用的 ID。 由于基础结构级别中设置了该配置用于隐藏在模型中的 ID，将为您的域模型，透明，其基础结构实现无法在以后发生更改。

在 eShopOnContainers，EF 核心基础结构所需的隐藏的 ID 实现在 DbContext 级别中，按以下方式使用 Fluent API 的基础结构项目。

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

因此，该 ID 隐藏的域模型角度来看，并在将来，值对象基础结构也都无法作为复杂类型或另一种方法实施。

## <a name="additional-resources"></a>其他资源

-   **Martin Fowler。ValueObject 模式**
    [*https://martinfowler.com/bliki/ValueObject.html*](https://martinfowler.com/bliki/ValueObject.html)

-   **Eric Evans。域驱动的设计： 解决软件核心的复杂性。** （本书; 包括的值对象的讨论）[ *https://www.amazon.com/Domain-Driven-Design-Tackling-Complexity-Software/dp/0321125215/*](https://www.amazon.com/Domain-Driven-Design-Tackling-Complexity-Software/dp/0321125215/)

-   **Vaughn Vernon。实现域驱动的设计。** （本书; 包括的值对象的讨论）[ *https://www.amazon.com/Implementing-Domain-Driven-Design-Vaughn-Vernon/dp/0321834577/*](https://www.amazon.com/Implementing-Domain-Driven-Design-Vaughn-Vernon/dp/0321834577/)

-   **隐藏属性**
    [*https://docs.microsoft.com/ef/core/modeling/shadow-properties*](https://docs.microsoft.com/ef/core/modeling/shadow-properties)

-   **复杂类型和/或值对象**。 在 EF 核心 GitHub 存储库 （问题选项卡） 中的讨论[ *https://github.com/aspnet/EntityFramework/issues/246*](https://github.com/aspnet/EntityFramework/issues/246)

-   **ValueObject.cs。** 中 eShopOnContainers 基值对象类。
    [*https://github.com/dotnet/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.Domain/SeedWork/ValueObject.cs*](https://github.com/dotnet/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.Domain/SeedWork/ValueObject.cs)

-   **地址类别。** 示例值中 eShopOnContainers 对象类。
    [*https://github.com/dotnet/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.Domain/AggregatesModel/OrderAggregate/Address.cs*](https://github.com/dotnet/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.Domain/AggregatesModel/OrderAggregate/Address.cs)


>[!div class="step-by-step"]
[以前](seedwork-domain-model-base-classes-interfaces.md) [下一步] (枚举-类-转移-枚举-types.md)
