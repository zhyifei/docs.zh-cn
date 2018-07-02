---
title: 使用枚举类（而不是枚举类型）
description: 适用于容器化 .NET 应用程序的 .NET 微服务体系结构 | 使用枚举类（而不是枚举类型）
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 12/11/2017
ms.openlocfilehash: eff87dbfad84ba5521f029064115a5fc54ee574b
ms.sourcegitcommit: 979597cd8055534b63d2c6ee8322938a27d0c87b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/29/2018
ms.locfileid: "37106105"
---
# <a name="using-enumeration-classes-instead-of-enum-types"></a><span data-ttu-id="1fe57-103">使用枚举类（而不是枚举类型）</span><span class="sxs-lookup"><span data-stu-id="1fe57-103">Using enumeration classes instead of enum types</span></span>

<span data-ttu-id="1fe57-104">[枚举](../../../../docs/csharp/language-reference/keywords/enum.md)（或枚举类型）是围绕整型类型的精简语言包装器。</span><span class="sxs-lookup"><span data-stu-id="1fe57-104">[Enumerations](../../../../docs/csharp/language-reference/keywords/enum.md) (or *enum types* for short) are a thin language wrapper around an integral type.</span></span> <span data-ttu-id="1fe57-105">建议在存储一组封闭值中的一个值时，限制对它们的使用。</span><span class="sxs-lookup"><span data-stu-id="1fe57-105">You might want to limit their use to when you are storing one value from a closed set of values.</span></span> <span data-ttu-id="1fe57-106">基于大小（小、中、大）的分类是一个很好的示例。</span><span class="sxs-lookup"><span data-stu-id="1fe57-106">Classification based on sizes (small, medium, large) is a good example.</span></span> <span data-ttu-id="1fe57-107">对控制流或更强健的抽象使用枚举可成为[代码气味](http://deviq.com/code-smells/)。</span><span class="sxs-lookup"><span data-stu-id="1fe57-107">Using enums for control flow or more robust abstractions can be a [code smell](http://deviq.com/code-smells/).</span></span> <span data-ttu-id="1fe57-108">这种使用方式会使代码很脆弱，并且会使许多控制流语句检查枚举值。</span><span class="sxs-lookup"><span data-stu-id="1fe57-108">This type of usage leads to fragile code with many control flow statements checking values of the enum.</span></span>

<span data-ttu-id="1fe57-109">相反，你可以创建枚举类，启动面向对象语言的所有丰富功能。</span><span class="sxs-lookup"><span data-stu-id="1fe57-109">Instead, you can create Enumeration classes that enable all the rich features of an object-oriented language.</span></span>

<span data-ttu-id="1fe57-110">但这不是关键点，在许多情况下，为了简便起见，如果喜欢，仍然可以使用常规[枚举类型](../../../../docs/csharp/language-reference/keywords/enum.md)。</span><span class="sxs-lookup"><span data-stu-id="1fe57-110">However, this isn't a critical topic and in many cases, for simplicity, you can still use regular [enum types](../../../../docs/csharp/language-reference/keywords/enum.md) if that's your preference.</span></span>

## <a name="implementing-an-enumeration-base-class"></a><span data-ttu-id="1fe57-111">实现枚举基类</span><span class="sxs-lookup"><span data-stu-id="1fe57-111">Implementing an Enumeration base class</span></span>

<span data-ttu-id="1fe57-112">eShopOnContainers 中的订购微服务提供了一个示例枚举基类实现，如下例所示：</span><span class="sxs-lookup"><span data-stu-id="1fe57-112">The ordering microservice in eShopOnContainers provides a sample Enumeration base class implementation, as shown in the following example:</span></span>

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

<span data-ttu-id="1fe57-113">在任何实体或值对象中，都可将下列 CardType 枚举类用作类型：</span><span class="sxs-lookup"><span data-stu-id="1fe57-113">You can use this class as a type in any entity or value object, as for the following CardType Enumeration class:</span></span>

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

## <a name="additional-resources"></a><span data-ttu-id="1fe57-114">其他资源</span><span class="sxs-lookup"><span data-stu-id="1fe57-114">Additional resources</span></span>

-   <span data-ttu-id="1fe57-115">**Enum’s are evil—update**
    [*https://www.planetgeek.ch/2009/07/01/enums-are-evil/*](https://www.planetgeek.ch/2009/07/01/enums-are-evil/)（枚举其实有弊无利：更新）</span><span class="sxs-lookup"><span data-stu-id="1fe57-115">**Enum’s are evil—update**
[*https://www.planetgeek.ch/2009/07/01/enums-are-evil/*](https://www.planetgeek.ch/2009/07/01/enums-are-evil/)</span></span>

-   <span data-ttu-id="1fe57-116">**Daniel Hardman.How Enums Spread Disease — And How To Cure It**
    [*https://codecraft.co/2012/10/29/how-enums-spread-disease-and-how-to-cure-it/*](https://codecraft.co/2012/10/29/how-enums-spread-disease-and-how-to-cure-it/)（枚举是如何扩大问题的，以及如何应对）</span><span class="sxs-lookup"><span data-stu-id="1fe57-116">**Daniel Hardman. How Enums Spread Disease — And How To Cure It**
[*https://codecraft.co/2012/10/29/how-enums-spread-disease-and-how-to-cure-it/*](https://codecraft.co/2012/10/29/how-enums-spread-disease-and-how-to-cure-it/)</span></span>

-   <span data-ttu-id="1fe57-117">**Jimmy Bogard。Enumeration classes**
    [*https://lostechies.com/jimmybogard/2008/08/12/enumeration-classes/*](https://lostechies.com/jimmybogard/2008/08/12/enumeration-classes/)（枚举类）</span><span class="sxs-lookup"><span data-stu-id="1fe57-117">**Jimmy Bogard. Enumeration classes**
[*https://lostechies.com/jimmybogard/2008/08/12/enumeration-classes/*](https://lostechies.com/jimmybogard/2008/08/12/enumeration-classes/)</span></span>

-   <span data-ttu-id="1fe57-118">**Steve Smith.Enum Alternatives in C#**
    [*https://ardalis.com/enum-alternatives-in-c*](https://ardalis.com/enum-alternatives-in-c)（C# 中枚举的替代方案）</span><span class="sxs-lookup"><span data-stu-id="1fe57-118">**Steve Smith. Enum Alternatives in C#**
[*https://ardalis.com/enum-alternatives-in-c*](https://ardalis.com/enum-alternatives-in-c)</span></span>

-   <span data-ttu-id="1fe57-119">**Enumeration.cs.**</span><span class="sxs-lookup"><span data-stu-id="1fe57-119">**Enumeration.cs.**</span></span> <span data-ttu-id="1fe57-120">Base Enumeration class in eShopOnContainers[*https://github.com/dotnet/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.Domain/SeedWork/Enumeration.cs*](https://github.com/dotnet/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.Domain/SeedWork/Enumeration.cs)（eShopOnContainers 中的基础枚举类）</span><span class="sxs-lookup"><span data-stu-id="1fe57-120">Base Enumeration class in eShopOnContainers [*https://github.com/dotnet/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.Domain/SeedWork/Enumeration.cs*](https://github.com/dotnet/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.Domain/SeedWork/Enumeration.cs)</span></span>

-   <span data-ttu-id="1fe57-121">**CardType.cs**.</span><span class="sxs-lookup"><span data-stu-id="1fe57-121">**CardType.cs**.</span></span> <span data-ttu-id="1fe57-122">eShopOnContainers 中的枚举类示例。</span><span class="sxs-lookup"><span data-stu-id="1fe57-122">Sample Enumeration class in eShopOnContainers.</span></span>
    [*https://github.com/dotnet/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.Domain/AggregatesModel/BuyerAggregate/CardType.cs*](https://github.com/dotnet/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.Domain/AggregatesModel/BuyerAggregate/CardType.cs)


>[!div class="step-by-step"]
<span data-ttu-id="1fe57-123">[上一页](implement-value-objects.md)
[下一页](domain-model-layer-validations.md)</span><span class="sxs-lookup"><span data-stu-id="1fe57-123">[Previous](implement-value-objects.md)
[Next](domain-model-layer-validations.md)</span></span>
