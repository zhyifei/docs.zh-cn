---
title: "使用枚举类，而不枚举类型"
description: "为容器化的.NET 应用程序的.NET 微服务体系结构 |使用枚举类，而不枚举类型"
keywords: "Docker, 微服务, ASP.NET, 容器"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: 1745198720fd12a9d26aab2d2afb2c5dd6b6b49d
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="using-enumeration-classes-instead-of-enum-types"></a><span data-ttu-id="c6d10-104">使用枚举类，而不枚举类型</span><span class="sxs-lookup"><span data-stu-id="c6d10-104">Using Enumeration classes instead of enum types</span></span>

<span data-ttu-id="c6d10-105">[枚举](https://msdn.microsoft.com/en-us/library/sbbt4032.aspx)(*枚举*简称) 是整数类型的精简语言包装。</span><span class="sxs-lookup"><span data-stu-id="c6d10-105">[Enumerations](https://msdn.microsoft.com/en-us/library/sbbt4032.aspx) (*enums* for short) are a thin language wrapper around an integral type.</span></span> <span data-ttu-id="c6d10-106">你可能想要限制对其使用时将存储从已关闭的一组值的一个值。</span><span class="sxs-lookup"><span data-stu-id="c6d10-106">You might want to limit their use to when you are storing one value from a closed set of values.</span></span> <span data-ttu-id="c6d10-107">典型示例是基于性别 (例如，男性，female，未知) 或大小 (S、 M、 L、 XL) 的分类。</span><span class="sxs-lookup"><span data-stu-id="c6d10-107">Classification based on gender (for example, male, female, unknown), or sizes (S, M, L, XL) are good examples.</span></span> <span data-ttu-id="c6d10-108">可以使用枚举的控制流或更可靠的抽象[代码告知](http://deviq.com/code-smells/)。</span><span class="sxs-lookup"><span data-stu-id="c6d10-108">Using enums for control flow or more robust abstractions can be a [code smell](http://deviq.com/code-smells/).</span></span> <span data-ttu-id="c6d10-109">这种类型的使用情况将导致与检查枚举值的多个控制流语句脆弱的代码。</span><span class="sxs-lookup"><span data-stu-id="c6d10-109">This type of usage will lead to fragile code with many control flow statements checking values of the enum.</span></span>

<span data-ttu-id="c6d10-110">相反，你可以创建可启用的面向对象语言中的所有丰富功能的枚举类。</span><span class="sxs-lookup"><span data-stu-id="c6d10-110">Instead, you can create Enumeration classes that enable all the rich features of an object-oriented language.</span></span> <span data-ttu-id="c6d10-111">但是，这不是一个关键问题并在许多情况下，为简单起见，你仍可以使用正则枚举这就是您的首选项。</span><span class="sxs-lookup"><span data-stu-id="c6d10-111">However, this is not a critical issue and in many cases, for simplicity, you can still use regular enums if that is your preference.</span></span>

## <a name="implementing-enumeration-classes"></a><span data-ttu-id="c6d10-112">实现枚举类</span><span class="sxs-lookup"><span data-stu-id="c6d10-112">Implementing Enumeration classes</span></span>

<span data-ttu-id="c6d10-113">在 eShopOnContainers 排序微服务提供示例枚举基类实现，如下面的示例中所示：</span><span class="sxs-lookup"><span data-stu-id="c6d10-113">The ordering microservice in eShopOnContainers provides a sample Enumeration base class implementation, as shown in the following example:</span></span>

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

<span data-ttu-id="c6d10-114">为任何实体或值的对象，与以下 CardType 枚举类中的类型，可以使用此类。</span><span class="sxs-lookup"><span data-stu-id="c6d10-114">You can use this class as a type in any entity or value object, as for the following CardType Enumeration class.</span></span>

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

## <a name="additional-resources"></a><span data-ttu-id="c6d10-115">其他资源</span><span class="sxs-lookup"><span data-stu-id="c6d10-115">Additional resources</span></span>

-   <span data-ttu-id="c6d10-116">**枚举的是恶魔-更新**
    [*http://www.planetgeek.ch/2009/07/01/enums-are-evil/*](http://www.planetgeek.ch/2009/07/01/enums-are-evil/)</span><span class="sxs-lookup"><span data-stu-id="c6d10-116">**Enum’s are evil—update**
[*http://www.planetgeek.ch/2009/07/01/enums-are-evil/*](http://www.planetgeek.ch/2009/07/01/enums-are-evil/)</span></span>

-   <span data-ttu-id="c6d10-117">**Daniel Hardman。如何枚举分布疾病-以及如何硬化它**
    [*https://codecraft.co/2012/10/29/how-enums-spread-disease-and-how-to-cure-it/*](https://codecraft.co/2012/10/29/how-enums-spread-disease-and-how-to-cure-it/)</span><span class="sxs-lookup"><span data-stu-id="c6d10-117">**Daniel Hardman. How Enums Spread Disease — And How To Cure It**
[*https://codecraft.co/2012/10/29/how-enums-spread-disease-and-how-to-cure-it/*](https://codecraft.co/2012/10/29/how-enums-spread-disease-and-how-to-cure-it/)</span></span>

-   <span data-ttu-id="c6d10-118">**Jimmy Bogard。枚举类**
    [*https://lostechies.com/jimmybogard/2008/08/12/enumeration-classes/*](https://lostechies.com/jimmybogard/2008/08/12/enumeration-classes/)</span><span class="sxs-lookup"><span data-stu-id="c6d10-118">**Jimmy Bogard. Enumeration classes**
[*https://lostechies.com/jimmybogard/2008/08/12/enumeration-classes/*](https://lostechies.com/jimmybogard/2008/08/12/enumeration-classes/)</span></span>

-   <span data-ttu-id="c6d10-119">**Steve Smith。枚举在 C# 中的替代项**
    [*http://ardalis.com/enum-alternatives-in-c*](http://ardalis.com/enum-alternatives-in-c)</span><span class="sxs-lookup"><span data-stu-id="c6d10-119">**Steve Smith. Enum Alternatives in C#**
[*http://ardalis.com/enum-alternatives-in-c*](http://ardalis.com/enum-alternatives-in-c)</span></span>

-   <span data-ttu-id="c6d10-120">**Enumeration.cs。**</span><span class="sxs-lookup"><span data-stu-id="c6d10-120">**Enumeration.cs.**</span></span> <span data-ttu-id="c6d10-121">枚举基类中 eShopOnContainers [ *https://github.com/dotnet/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.Domain/SeedWork/Enumeration.cs*](https://github.com/dotnet/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.Domain/SeedWork/Enumeration.cs)</span><span class="sxs-lookup"><span data-stu-id="c6d10-121">Base Enumeration class in eShopOnContainers [*https://github.com/dotnet/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.Domain/SeedWork/Enumeration.cs*](https://github.com/dotnet/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.Domain/SeedWork/Enumeration.cs)</span></span>

-   <span data-ttu-id="c6d10-122">**CardType.cs**。</span><span class="sxs-lookup"><span data-stu-id="c6d10-122">**CardType.cs**.</span></span> <span data-ttu-id="c6d10-123">示例中 eShopOnContainers 枚举类。</span><span class="sxs-lookup"><span data-stu-id="c6d10-123">Sample Enumeration class in eShopOnContainers.</span></span>
    [<span data-ttu-id="c6d10-124">*https://github.com/dotnet/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.Domain/AggregatesModel/BuyerAggregate/CardType.cs*</span><span class="sxs-lookup"><span data-stu-id="c6d10-124">*https://github.com/dotnet/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.Domain/AggregatesModel/BuyerAggregate/CardType.cs*</span></span>](https://github.com/dotnet/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.Domain/AggregatesModel/BuyerAggregate/CardType.cs)


>[!div class="step-by-step"]
<span data-ttu-id="c6d10-125">[以前](实现的值-objects.md) [下一步] (域-模型-层-validations.md)</span><span class="sxs-lookup"><span data-stu-id="c6d10-125">[Previous] (implement-value-objects.md) [Next] (domain-model-layer-validations.md)</span></span>
