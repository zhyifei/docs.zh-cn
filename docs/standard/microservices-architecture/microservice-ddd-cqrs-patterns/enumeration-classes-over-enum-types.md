---
title: "使用枚举类（而不是枚举类型）"
description: "适用于容器化 .NET 应用程序的 .NET 微服务体系结构 | 使用枚举类（而不是枚举类型）"
keywords: "Docker, 微服务, ASP.NET, 容器"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 12/11/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 4b190ee9dde5628bf16fe9c483d3636539c29361
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/23/2017
---
# <a name="using-enumeration-classes-instead-of-enum-types"></a><span data-ttu-id="08591-104">使用枚举类（而不是枚举类型）</span><span class="sxs-lookup"><span data-stu-id="08591-104">Using enumeration classes instead of enum types</span></span>

<span data-ttu-id="08591-105">[枚举](../../../../docs/csharp/language-reference/keywords/enum.md)（或枚举类型）是围绕整型类型的精简语言包装器。</span><span class="sxs-lookup"><span data-stu-id="08591-105">[Enumerations](../../../../docs/csharp/language-reference/keywords/enum.md) (or *enum types* for short) are a thin language wrapper around an integral type.</span></span> <span data-ttu-id="08591-106">建议在存储一组封闭值中的一个值时，限制对它们的使用。</span><span class="sxs-lookup"><span data-stu-id="08591-106">You might want to limit their use to when you are storing one value from a closed set of values.</span></span> <span data-ttu-id="08591-107">基于性别（例如，男性、女性、未知）或尺码（小号、中号、大号）进行的分类就是很好的示例。</span><span class="sxs-lookup"><span data-stu-id="08591-107">Classification based on gender (for example, male, female, unknown) or sizes (small, medium, large) are good examples.</span></span> <span data-ttu-id="08591-108">对控制流或更强健的抽象使用枚举可成为[代码气味](http://deviq.com/code-smells/)。</span><span class="sxs-lookup"><span data-stu-id="08591-108">Using enums for control flow or more robust abstractions can be a [code smell](http://deviq.com/code-smells/).</span></span> <span data-ttu-id="08591-109">这种使用方式会使代码很脆弱，并且会使许多控制流语句检查枚举值。</span><span class="sxs-lookup"><span data-stu-id="08591-109">This type of usage leads to fragile code with many control flow statements checking values of the enum.</span></span>

<span data-ttu-id="08591-110">相反，你可以创建枚举类，启动面向对象语言的所有丰富功能。</span><span class="sxs-lookup"><span data-stu-id="08591-110">Instead, you can create Enumeration classes that enable all the rich features of an object-oriented language.</span></span>

<span data-ttu-id="08591-111">但这不是关键点，在许多情况下，为了简便起见，如果喜欢，仍然可以使用常规[枚举类型](../../../../docs/csharp/language-reference/keywords/enum.md)。</span><span class="sxs-lookup"><span data-stu-id="08591-111">However, this isn't a critical topic and in many cases, for simplicity, you can still use regular [enum types](../../../../docs/csharp/language-reference/keywords/enum.md) if that's your preference.</span></span>

## <a name="implementing-an-enumeration-base-class"></a><span data-ttu-id="08591-112">实现枚举基类</span><span class="sxs-lookup"><span data-stu-id="08591-112">Implementing an Enumeration base class</span></span>

<span data-ttu-id="08591-113">eShopOnContainers 中的订购微服务提供了一个示例枚举基类实现，如下例所示：</span><span class="sxs-lookup"><span data-stu-id="08591-113">The ordering microservice in eShopOnContainers provides a sample Enumeration base class implementation, as shown in the following example:</span></span>

```csharp
public abstract class Enumeration : IComparable
{
    public string Name { get; private set; }
    public int Id { get; private set; }

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

<span data-ttu-id="08591-114">在任何实体或值对象中，都可将下列 CardType 枚举类用作类型：</span><span class="sxs-lookup"><span data-stu-id="08591-114">You can use this class as a type in any entity or value object, as for the following CardType Enumeration class:</span></span>

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

## <a name="additional-resources"></a><span data-ttu-id="08591-115">其他资源</span><span class="sxs-lookup"><span data-stu-id="08591-115">Additional resources</span></span>

-   <span data-ttu-id="08591-116">**Enum’s are evil—update（枚举并非善茬 - 更新）**
    [http://www.planetgeek.ch/2009/07/01/enums-are-evil/](http://www.planetgeek.ch/2009/07/01/enums-are-evil/)</span><span class="sxs-lookup"><span data-stu-id="08591-116">**Enum’s are evil—update**
[*http://www.planetgeek.ch/2009/07/01/enums-are-evil/*](http://www.planetgeek.ch/2009/07/01/enums-are-evil/)</span></span>

-   <span data-ttu-id="08591-117">**Daniel Hardman.How Enums Spread Disease — And How To Cure It**（枚举传播疾病的方式 - 以及疾病治愈方式）
    [https://codecraft.co/2012/10/29/how-enums-spread-disease-and-how-to-cure-it/](https://codecraft.co/2012/10/29/how-enums-spread-disease-and-how-to-cure-it/)</span><span class="sxs-lookup"><span data-stu-id="08591-117">**Daniel Hardman. How Enums Spread Disease — And How To Cure It**
[*https://codecraft.co/2012/10/29/how-enums-spread-disease-and-how-to-cure-it/*](https://codecraft.co/2012/10/29/how-enums-spread-disease-and-how-to-cure-it/)</span></span>

-   <span data-ttu-id="08591-118">**Jimmy Bogard。Enumeration classes**（枚举类）
    [https://lostechies.com/jimmybogard/2008/08/12/enumeration-classes/](https://lostechies.com/jimmybogard/2008/08/12/enumeration-classes/)</span><span class="sxs-lookup"><span data-stu-id="08591-118">**Jimmy Bogard. Enumeration classes**
[*https://lostechies.com/jimmybogard/2008/08/12/enumeration-classes/*](https://lostechies.com/jimmybogard/2008/08/12/enumeration-classes/)</span></span>

-   <span data-ttu-id="08591-119">**Steve Smith.Enum Alternatives in C#（C# 中的枚举替代方案）**
    [http://ardalis.com/enum-alternatives-in-c](http://ardalis.com/enum-alternatives-in-c)</span><span class="sxs-lookup"><span data-stu-id="08591-119">**Steve Smith. Enum Alternatives in C#**
[*http://ardalis.com/enum-alternatives-in-c*](http://ardalis.com/enum-alternatives-in-c)</span></span>

-   <span data-ttu-id="08591-120">**Enumeration.cs.**</span><span class="sxs-lookup"><span data-stu-id="08591-120">**Enumeration.cs.**</span></span> <span data-ttu-id="08591-121">Base Enumeration class in eShopOnContainers（eShopOnContainers 中的枚举基类）[https://github.com/dotnet/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.Domain/SeedWork/Enumeration.cs](https://github.com/dotnet/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.Domain/SeedWork/Enumeration.cs)</span><span class="sxs-lookup"><span data-stu-id="08591-121">Base Enumeration class in eShopOnContainers [*https://github.com/dotnet/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.Domain/SeedWork/Enumeration.cs*](https://github.com/dotnet/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.Domain/SeedWork/Enumeration.cs)</span></span>

-   <span data-ttu-id="08591-122">**CardType.cs**.</span><span class="sxs-lookup"><span data-stu-id="08591-122">**CardType.cs**.</span></span> <span data-ttu-id="08591-123">eShopOnContainers 中的枚举类示例。</span><span class="sxs-lookup"><span data-stu-id="08591-123">Sample Enumeration class in eShopOnContainers.</span></span>
    [<span data-ttu-id="08591-124">https://github.com/dotnet/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.Domain/AggregatesModel/BuyerAggregate/CardType.cs</span><span class="sxs-lookup"><span data-stu-id="08591-124">*https://github.com/dotnet/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.Domain/AggregatesModel/BuyerAggregate/CardType.cs*</span></span>](https://github.com/dotnet/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.Domain/AggregatesModel/BuyerAggregate/CardType.cs)


>[!div class="step-by-step"]
<span data-ttu-id="08591-125">[上一篇] (implement-value-objects.md) [下一篇] (domain-model-layer-validations.md)</span><span class="sxs-lookup"><span data-stu-id="08591-125">[Previous] (implement-value-objects.md) [Next] (domain-model-layer-validations.md)</span></span>
