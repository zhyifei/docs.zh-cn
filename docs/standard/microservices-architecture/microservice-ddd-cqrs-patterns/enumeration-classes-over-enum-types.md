---
title: 使用枚举类（而不是枚举类型）
description: 适用于容器化 .NET 应用程序的 .NET 微服务体系结构 | 使用枚举类（而不是枚举类型）
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 12/11/2017
ms.openlocfilehash: 1cb8c6115602d80b61f1116cbb1a8df4fbcee028
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="using-enumeration-classes-instead-of-enum-types"></a>使用枚举类（而不是枚举类型）

[枚举](../../../../docs/csharp/language-reference/keywords/enum.md)（或枚举类型）是围绕整型类型的精简语言包装器。 建议在存储一组封闭值中的一个值时，限制对它们的使用。 基于性别（例如，男性、女性、未知）或尺码（小号、中号、大号）进行的分类就是很好的示例。 对控制流或更强健的抽象使用枚举可成为[代码气味](http://deviq.com/code-smells/)。 这种使用方式会使代码很脆弱，并且会使许多控制流语句检查枚举值。

相反，你可以创建枚举类，启动面向对象语言的所有丰富功能。

但这不是关键点，在许多情况下，为了简便起见，如果喜欢，仍然可以使用常规[枚举类型](../../../../docs/csharp/language-reference/keywords/enum.md)。

## <a name="implementing-an-enumeration-base-class"></a>实现枚举基类

eShopOnContainers 中的订购微服务提供了一个示例枚举基类实现，如下例所示：

```csharp
public abstract class Enumeration : IComparable
{
    public string Name { get; }
    public int Id { get; }

    protected Enumeration()
    {
    }

    protected Enumeration(int id, string name)
    {
        Id = id;
        Name = name;
    }

    public override string ToString()
    {
        return Name;
    }

    public static IEnumerable<T> GetAll<T>() where T : Enumeration, new()
    {
        var type = typeof(T);
        var fields = type.GetTypeInfo().GetFields(BindingFlags.Public |
            BindingFlags.Static |
            BindingFlags.DeclaredOnly);
        foreach (var info in fields)
        {
            var instance = new T();
            var locatedValue = info.GetValue(instance) as T;
            if (locatedValue != null)
            {
                yield return locatedValue;
            }
        }
    }

    public override bool Equals(object obj)
    {
        var otherValue = obj as Enumeration;
        if (otherValue == null)
        {
            return false;
        }
        var typeMatches = GetType().Equals(obj.GetType());
        var valueMatches = Id.Equals(otherValue.Id);
        return typeMatches && valueMatches;
    }

    public int CompareTo(object other)
    {
        return Id.CompareTo(((Enumeration)other).Id);
    }

    // Other utility methods ...
}
```

在任何实体或值对象中，都可将下列 CardType 枚举类用作类型：

```csharp
public class CardType : Enumeration
{
    public static CardType Amex = new CardType(1, "Amex");
    public static CardType Visa = new CardType(2, "Visa");
    public static CardType MasterCard = new CardType(3, "MasterCard");

    protected CardType() { }

    public CardType(int id, string name)
        : base(id, name)
    {
    }

    public static IEnumerable<CardType> List()
    {
        return new[] { Amex, Visa, MasterCard };
    }
    // Other util methods
}
```

## <a name="additional-resources"></a>其他资源

-   **Enum’s are evil—update**
    [*https://www.planetgeek.ch/2009/07/01/enums-are-evil/*](https://www.planetgeek.ch/2009/07/01/enums-are-evil/)（枚举其实有弊无利：更新）

-   **Daniel Hardman.How Enums Spread Disease — And How To Cure It**
    [*https://codecraft.co/2012/10/29/how-enums-spread-disease-and-how-to-cure-it/*](https://codecraft.co/2012/10/29/how-enums-spread-disease-and-how-to-cure-it/)（枚举是如何扩大问题的，以及如何应对）

-   **Jimmy Bogard。Enumeration classes**
    [*https://lostechies.com/jimmybogard/2008/08/12/enumeration-classes/*](https://lostechies.com/jimmybogard/2008/08/12/enumeration-classes/)（枚举类）

-   **Steve Smith.Enum Alternatives in C#**
    [*https://ardalis.com/enum-alternatives-in-c*](https://ardalis.com/enum-alternatives-in-c)（C# 中枚举的替代方案）

-   **Enumeration.cs.** Base Enumeration class in eShopOnContainers[*https://github.com/dotnet/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.Domain/SeedWork/Enumeration.cs*](https://github.com/dotnet/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.Domain/SeedWork/Enumeration.cs)（eShopOnContainers 中的基础枚举类）

-   **CardType.cs**. eShopOnContainers 中的枚举类示例。
    [*https://github.com/dotnet/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.Domain/AggregatesModel/BuyerAggregate/CardType.cs*](https://github.com/dotnet/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.Domain/AggregatesModel/BuyerAggregate/CardType.cs)


>[!div class="step-by-step"]
[上一篇] (implement-value-objects.md) [下一篇] (domain-model-layer-validations.md)
