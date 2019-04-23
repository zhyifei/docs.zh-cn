---
title: 使用枚举类（而不是枚举类型）
description: 适用于容器化 .NET 应用程序的 .NET 微服务体系结构 | 了解如何使用枚举类来解决枚举的某些局限性。
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/08/2018
ms.openlocfilehash: d2d4b191ed4cb8f2f8b9b0a34fe99e65d4596a72
ms.sourcegitcommit: 438919211260bb415fc8f96ca3eabc33cf2d681d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2019
ms.locfileid: "59613559"
---
# <a name="use-enumeration-classes-instead-of-enum-types"></a><span data-ttu-id="401d5-103">使用枚举类（而不是枚举类型）</span><span class="sxs-lookup"><span data-stu-id="401d5-103">Use enumeration classes instead of enum types</span></span>

<span data-ttu-id="401d5-104">[枚举](../../../../docs/csharp/language-reference/keywords/enum.md)（或枚举类型）是围绕整型类型的精简语言包装器。</span><span class="sxs-lookup"><span data-stu-id="401d5-104">[Enumerations](../../../../docs/csharp/language-reference/keywords/enum.md) (or *enum types* for short) are a thin language wrapper around an integral type.</span></span> <span data-ttu-id="401d5-105">建议在存储一组封闭值中的一个值时，限制对它们的使用。</span><span class="sxs-lookup"><span data-stu-id="401d5-105">You might want to limit their use to when you are storing one value from a closed set of values.</span></span> <span data-ttu-id="401d5-106">基于大小（小、中、大）的分类是一个很好的示例。</span><span class="sxs-lookup"><span data-stu-id="401d5-106">Classification based on sizes (small, medium, large) is a good example.</span></span> <span data-ttu-id="401d5-107">对控制流或更强健的抽象使用枚举可成为[代码气味](https://deviq.com/code-smells/)。</span><span class="sxs-lookup"><span data-stu-id="401d5-107">Using enums for control flow or more robust abstractions can be a [code smell](https://deviq.com/code-smells/).</span></span> <span data-ttu-id="401d5-108">这种使用方式会使代码很脆弱，并且会使许多控制流语句检查枚举值。</span><span class="sxs-lookup"><span data-stu-id="401d5-108">This type of usage leads to fragile code with many control flow statements checking values of the enum.</span></span>

<span data-ttu-id="401d5-109">相反，你可以创建枚举类，启动面向对象语言的所有丰富功能。</span><span class="sxs-lookup"><span data-stu-id="401d5-109">Instead, you can create Enumeration classes that enable all the rich features of an object-oriented language.</span></span>

<span data-ttu-id="401d5-110">但这不是关键点，在许多情况下，为了简便起见，如果喜欢，仍然可以使用常规[枚举类型](../../../csharp/language-reference/keywords/enum.md)。</span><span class="sxs-lookup"><span data-stu-id="401d5-110">However, this isn't a critical topic and in many cases, for simplicity, you can still use regular [enum types](../../../csharp/language-reference/keywords/enum.md) if that's your preference.</span></span> <span data-ttu-id="401d5-111">总之，枚举类的使用与业务相关概念的关系更密切。</span><span class="sxs-lookup"><span data-stu-id="401d5-111">Anyway, the use of enumeration classes is more related to business-related concepts.</span></span>

## <a name="implement-an-enumeration-base-class"></a><span data-ttu-id="401d5-112">实现枚举基类</span><span class="sxs-lookup"><span data-stu-id="401d5-112">Implement an Enumeration base class</span></span>

<span data-ttu-id="401d5-113">eShopOnContainers 中的订购微服务提供了一个示例枚举基类实现，如下例所示：</span><span class="sxs-lookup"><span data-stu-id="401d5-113">The ordering microservice in eShopOnContainers provides a sample Enumeration base class implementation, as shown in the following example:</span></span>

```csharp
public abstract class Enumeration : IComparable
{
    public string Name { get; private set; }

    public int Id { get; private set; }

    protected Enumeration(int id, string name) 
    {
        Id = id; 
        Name = name; 
    }

    public override string ToString() => Name;

    public static IEnumerable<T> GetAll<T>() where T : Enumeration
    {
        var fields = typeof(T).GetFields(BindingFlags.Public | 
                                         BindingFlags.Static | 
                                         BindingFlags.DeclaredOnly); 

        return fields.Select(f => f.GetValue(null)).Cast<T>();
    }

    public override bool Equals(object obj) 
    {
        var otherValue = obj as Enumeration; 

        if (otherValue == null) 
            return false;

        var typeMatches = GetType().Equals(obj.GetType());
        var valueMatches = Id.Equals(otherValue.Id);

        return typeMatches && valueMatches;
    }

    public int CompareTo(object other) => Id.CompareTo(((Enumeration)other).Id); 

    // Other utility methods ... 
}
```

<span data-ttu-id="401d5-114">可将此类用作任何实体或值对象中的类型，如以下 `CardType` : `Enumeration` 类：</span><span class="sxs-lookup"><span data-stu-id="401d5-114">You can use this class as a type in any entity or value object, as for the following `CardType` : `Enumeration` class:</span></span>

```csharp
public abstract class CardType : Enumeration
{
    public static CardType Amex = new CardType(1, "Amex");
    public static CardType Visa = new CardType(2, "Visa");
    public static CardType MasterCard = new CardType(3, "MasterCard");

    public CardType(int id, string name)
        : base(id, name)
    {
    }
}
```

## <a name="additional-resources"></a><span data-ttu-id="401d5-115">其他资源</span><span class="sxs-lookup"><span data-stu-id="401d5-115">Additional resources</span></span>

- <span data-ttu-id="401d5-116">**Enum’s are evil—update** \（枚举有弊无利：更新）</span><span class="sxs-lookup"><span data-stu-id="401d5-116">**Enum’s are evil—update** \\</span></span>
  <https://www.planetgeek.ch/2009/07/01/enums-are-evil/>

- <span data-ttu-id="401d5-117">**Daniel Hardman.How Enums Spread Disease — And How To Cure It** \（枚举如何扩大问题以及如何应对）</span><span class="sxs-lookup"><span data-stu-id="401d5-117">**Daniel Hardman. How Enums Spread Disease — And How To Cure It** \\</span></span>
  <https://codecraft.co/2012/10/29/how-enums-spread-disease-and-how-to-cure-it/>

- <span data-ttu-id="401d5-118">**Jimmy Bogard。Enumeration classes** \（枚举类）</span><span class="sxs-lookup"><span data-stu-id="401d5-118">**Jimmy Bogard. Enumeration classes** \\</span></span>
  <https://lostechies.com/jimmybogard/2008/08/12/enumeration-classes/>

- <span data-ttu-id="401d5-119">**Steve Smith.Enum Alternatives in C#** \（C# 中枚举的替代方案）</span><span class="sxs-lookup"><span data-stu-id="401d5-119">**Steve Smith. Enum Alternatives in C#** \\</span></span>
  <https://ardalis.com/enum-alternatives-in-c>

- <span data-ttu-id="401d5-120">**Enumeration.cs.**</span><span class="sxs-lookup"><span data-stu-id="401d5-120">**Enumeration.cs.**</span></span> <span data-ttu-id="401d5-121">eShopOnContainers 中的基础枚举类</span><span class="sxs-lookup"><span data-stu-id="401d5-121">Base Enumeration class in eShopOnContainers \\</span></span>
  <https://github.com/dotnet-architecture/eShopOnContainers/blob/dev/src/Services/Ordering/Ordering.Domain/SeedWork/Enumeration.cs>

- <span data-ttu-id="401d5-122">**CardType.cs**.</span><span class="sxs-lookup"><span data-stu-id="401d5-122">**CardType.cs**.</span></span> <span data-ttu-id="401d5-123">eShopOnContainers 中的枚举类示例。</span><span class="sxs-lookup"><span data-stu-id="401d5-123">Sample Enumeration class in eShopOnContainers.</span></span> \
  <https://github.com/dotnet-architecture/eShopOnContainers/blob/dev/src/Services/Ordering/Ordering.Domain/AggregatesModel/BuyerAggregate/CardType.cs>
    
- <span data-ttu-id="401d5-124">**SmartEnum**。</span><span class="sxs-lookup"><span data-stu-id="401d5-124">**SmartEnum**.</span></span> <span data-ttu-id="401d5-125">Ardalis - 帮助在 .NET 中生成强类型智能枚举的类。</span><span class="sxs-lookup"><span data-stu-id="401d5-125">Ardalis - Classes to help produce strongly typed smarter enums in .NET.</span></span> \
  <https://www.nuget.org/packages/Ardalis.SmartEnum/>

>[!div class="step-by-step"]
><span data-ttu-id="401d5-126">[上一页](implement-value-objects.md)
>[下一页](domain-model-layer-validations.md)</span><span class="sxs-lookup"><span data-stu-id="401d5-126">[Previous](implement-value-objects.md)
[Next](domain-model-layer-validations.md)</span></span>
