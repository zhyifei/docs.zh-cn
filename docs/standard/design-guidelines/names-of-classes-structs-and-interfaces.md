---
title: 类、结构和接口的名称
ms.date: 10/22/2008
helpviewer_keywords:
- type names, guidelines
- classes [.NET Framework], names
- enumerations [.NET Framework], names
- names [.NET Framework], interfaces
- common type names
- names [.NET Framework], type names
- names [.NET Framework], classes
- interfaces [.NET Framework], names
- generic type parameters
ms.assetid: 87a4b0da-ed64-43b1-ac43-968576c444ce
ms.openlocfilehash: 2c528348c0e84037a80df9797c56f03b51c73adc
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2020
ms.locfileid: "76727785"
---
# <a name="names-of-classes-structs-and-interfaces"></a><span data-ttu-id="dd0e3-102">类、结构和接口的名称</span><span class="sxs-lookup"><span data-stu-id="dd0e3-102">Names of Classes, Structs, and Interfaces</span></span>
<span data-ttu-id="dd0e3-103">以下命名准则适用于常规类型命名。</span><span class="sxs-lookup"><span data-stu-id="dd0e3-103">The naming guidelines that follow apply to general type naming.</span></span>

 <span data-ttu-id="dd0e3-104">✔️使用 PascalCasing 将类和结构命名为名词或名词短语。</span><span class="sxs-lookup"><span data-stu-id="dd0e3-104">✔️ DO name classes and structs with nouns or noun phrases, using PascalCasing.</span></span>

 <span data-ttu-id="dd0e3-105">这将类型名称与使用谓词短语命名的方法区分开来。</span><span class="sxs-lookup"><span data-stu-id="dd0e3-105">This distinguishes type names from methods, which are named with verb phrases.</span></span>

 <span data-ttu-id="dd0e3-106">✔️利用形容词短语或偶尔用名词或名词短语来命名接口。</span><span class="sxs-lookup"><span data-stu-id="dd0e3-106">✔️ DO name interfaces with adjective phrases, or occasionally with nouns or noun phrases.</span></span>

 <span data-ttu-id="dd0e3-107">应少使用名词和名词短语，它们可能会指示类型为抽象类而非接口。</span><span class="sxs-lookup"><span data-stu-id="dd0e3-107">Nouns and noun phrases should be used rarely and they might indicate that the type should be an abstract class, and not an interface.</span></span>

 <span data-ttu-id="dd0e3-108">❌ 不要为类名称指定前缀（例如，"C"）。</span><span class="sxs-lookup"><span data-stu-id="dd0e3-108">❌ DO NOT give class names a prefix (e.g., "C").</span></span>

 <span data-ttu-id="dd0e3-109">✔️考虑用基类的名称结束派生类的名称。</span><span class="sxs-lookup"><span data-stu-id="dd0e3-109">✔️ CONSIDER ending the name of derived classes with the name of the base class.</span></span>

 <span data-ttu-id="dd0e3-110">这样可让名称非常易读，并清楚体现了关系。</span><span class="sxs-lookup"><span data-stu-id="dd0e3-110">This is very readable and explains the relationship clearly.</span></span> <span data-ttu-id="dd0e3-111">代码中的一些示例包括： `ArgumentOutOfRangeException`，这是一种 `Exception`，`SerializableAttribute`，这是一种 `Attribute`。</span><span class="sxs-lookup"><span data-stu-id="dd0e3-111">Some examples of this in code are: `ArgumentOutOfRangeException`, which is a kind of `Exception`, and `SerializableAttribute`, which is a kind of `Attribute`.</span></span> <span data-ttu-id="dd0e3-112">但是，在应用此准则时使用合理的判断非常重要;例如，`Button` 类是一种 `Control` 事件，尽管 `Control` 不会在其名称中出现。</span><span class="sxs-lookup"><span data-stu-id="dd0e3-112">However, it is important to use reasonable judgment in applying this guideline; for example, the `Button` class is a kind of `Control` event, although `Control` doesn’t appear in its name.</span></span>

 <span data-ttu-id="dd0e3-113">✔️使用字母 I 来为接口名称加上前缀，以指示该类型是接口。</span><span class="sxs-lookup"><span data-stu-id="dd0e3-113">✔️ DO prefix interface names with the letter I, to indicate that the type is an interface.</span></span>

 <span data-ttu-id="dd0e3-114">例如，`IComponent` （描述性名词）、`ICustomAttributeProvider` （名词短语）和 `IPersistable` （形容词）均为适当的接口名称。</span><span class="sxs-lookup"><span data-stu-id="dd0e3-114">For example, `IComponent` (descriptive noun), `ICustomAttributeProvider` (noun phrase), and `IPersistable` (adjective) are appropriate interface names.</span></span> <span data-ttu-id="dd0e3-115">对于其他类型名称，请避免缩写形式。</span><span class="sxs-lookup"><span data-stu-id="dd0e3-115">As with other type names, avoid abbreviations.</span></span>

 <span data-ttu-id="dd0e3-116">✔️确保在定义类接口对（其中类是接口的标准实现）时，接口名称上的 "I" 前缀仅有不同的名称。</span><span class="sxs-lookup"><span data-stu-id="dd0e3-116">✔️ DO ensure that the names differ only by the "I" prefix on the interface name when you are defining a class–interface pair where the class is a standard implementation of the interface.</span></span>

## <a name="names-of-generic-type-parameters"></a><span data-ttu-id="dd0e3-117">泛型类型参数的名称</span><span class="sxs-lookup"><span data-stu-id="dd0e3-117">Names of Generic Type Parameters</span></span>
 <span data-ttu-id="dd0e3-118">.NET Framework 2.0 中增添了泛型。</span><span class="sxs-lookup"><span data-stu-id="dd0e3-118">Generics were added to .NET Framework 2.0.</span></span> <span data-ttu-id="dd0e3-119">此功能引入了一种称为*类型参数*的新标识符。</span><span class="sxs-lookup"><span data-stu-id="dd0e3-119">The feature introduced a new kind of identifier called *type parameter*.</span></span>

 <span data-ttu-id="dd0e3-120">✔️使用描述性名称命名泛型类型参数，除非单个字母名称完全一目了然，并且描述性名称不会添加值。</span><span class="sxs-lookup"><span data-stu-id="dd0e3-120">✔️ DO name generic type parameters with descriptive names unless a single-letter name is completely self-explanatory and a descriptive name would not add value.</span></span>

 <span data-ttu-id="dd0e3-121">✔️考虑使用 `T` 作为具有一个单字母类型参数的类型的类型参数名称。</span><span class="sxs-lookup"><span data-stu-id="dd0e3-121">✔️ CONSIDER using `T` as the type parameter name for types with one single-letter type parameter.</span></span>

```csharp
public int IComparer<T> { ... }
public delegate bool Predicate<T>(T item);
public struct Nullable<T> where T:struct { ... }
```

 <span data-ttu-id="dd0e3-122">✔️用 `T`为描述性类型参数名称加上前缀。</span><span class="sxs-lookup"><span data-stu-id="dd0e3-122">✔️ DO prefix descriptive type parameter names with `T`.</span></span>

```csharp
public interface ISessionChannel<TSession> where TSession : ISession {
    TSession Session { get; }
}
```

 <span data-ttu-id="dd0e3-123">✔️考虑，指示对参数名称中的类型参数施加的约束。</span><span class="sxs-lookup"><span data-stu-id="dd0e3-123">✔️ CONSIDER indicating constraints placed on a type parameter in the name of the parameter.</span></span>

 <span data-ttu-id="dd0e3-124">例如，可能会 `TSession`中调用约束为 `ISession` 的参数。</span><span class="sxs-lookup"><span data-stu-id="dd0e3-124">For example, a parameter constrained to `ISession` might be called `TSession`.</span></span>

## <a name="names-of-common-types"></a><span data-ttu-id="dd0e3-125">常见类型的名称</span><span class="sxs-lookup"><span data-stu-id="dd0e3-125">Names of Common Types</span></span>
 <span data-ttu-id="dd0e3-126">当命名类型派生自或实现某些 .NET Framework 类型时，✔️按照下表中所述的指导原则进行操作。</span><span class="sxs-lookup"><span data-stu-id="dd0e3-126">✔️ DO follow the guidelines described in the following table when naming types derived from or implementing certain .NET Framework types.</span></span>

|<span data-ttu-id="dd0e3-127">Base Type</span><span class="sxs-lookup"><span data-stu-id="dd0e3-127">Base Type</span></span>|<span data-ttu-id="dd0e3-128">派生/实现类型准则</span><span class="sxs-lookup"><span data-stu-id="dd0e3-128">Derived/Implementing Type Guideline</span></span>|
|---------------|------------------------------------------|
|`System.Attribute`|<span data-ttu-id="dd0e3-129">✔️将后缀 "Attribute" 添加到自定义特性类的名称中。</span><span class="sxs-lookup"><span data-stu-id="dd0e3-129">✔️ DO add the suffix "Attribute" to names of custom attribute classes.</span></span>|
|`System.Delegate`|<span data-ttu-id="dd0e3-130">✔️将后缀 "EventHandler" 添加到在事件中使用的委托的名称。</span><span class="sxs-lookup"><span data-stu-id="dd0e3-130">✔️ DO add the suffix "EventHandler" to names of delegates that are used in events.</span></span><br /><br /> <span data-ttu-id="dd0e3-131">✔️将后缀 "Callback" 添加到作为事件处理程序使用的委托的名称。</span><span class="sxs-lookup"><span data-stu-id="dd0e3-131">✔️ DO add the suffix "Callback" to names of delegates other than those used as event handlers.</span></span><br /><br /> <span data-ttu-id="dd0e3-132">❌ 不要将后缀 "Delegate" 添加到委托。</span><span class="sxs-lookup"><span data-stu-id="dd0e3-132">❌ DO NOT add the suffix "Delegate" to a delegate.</span></span>|
|`System.EventArgs`|<span data-ttu-id="dd0e3-133">✔️添加后缀 "EventArgs"。</span><span class="sxs-lookup"><span data-stu-id="dd0e3-133">✔️ DO add the suffix "EventArgs."</span></span>|
|`System.Enum`|<span data-ttu-id="dd0e3-134">❌ 不从此类派生;改为使用您的语言支持的关键字;例如，在中C#，请使用 `enum` 关键字。</span><span class="sxs-lookup"><span data-stu-id="dd0e3-134">❌ DO NOT derive from this class; use the keyword supported by your language instead; for example, in C#, use the `enum` keyword.</span></span><br /><br /> <span data-ttu-id="dd0e3-135">❌ 不要添加后缀 "Enum" 或 "标志"。</span><span class="sxs-lookup"><span data-stu-id="dd0e3-135">❌ DO NOT add the suffix "Enum" or "Flag."</span></span>|
|`System.Exception`|<span data-ttu-id="dd0e3-136">✔️添加后缀 "Exception"。</span><span class="sxs-lookup"><span data-stu-id="dd0e3-136">✔️ DO add the suffix "Exception."</span></span>|
|`IDictionary` <br /> `IDictionary<TKey,TValue>`|<span data-ttu-id="dd0e3-137">✔️添加后缀 "Dictionary"。</span><span class="sxs-lookup"><span data-stu-id="dd0e3-137">✔️ DO add the suffix "Dictionary."</span></span> <span data-ttu-id="dd0e3-138">请注意，`IDictionary` 是特定类型的集合，但是此准则优先于下面更常见的集合原则。</span><span class="sxs-lookup"><span data-stu-id="dd0e3-138">Note that `IDictionary` is a specific type of collection, but this guideline takes precedence over the more general collections guideline that follows.</span></span>|
|`IEnumerable` <br /> `ICollection` <br /> `IList` <br /> `IEnumerable<T>` <br /> `ICollection<T>` <br /> `IList<T>`|<span data-ttu-id="dd0e3-139">✔️添加后缀 "Collection"。</span><span class="sxs-lookup"><span data-stu-id="dd0e3-139">✔️ DO add the suffix "Collection."</span></span>|
|`System.IO.Stream`|<span data-ttu-id="dd0e3-140">✔️添加后缀 "Stream"。</span><span class="sxs-lookup"><span data-stu-id="dd0e3-140">✔️ DO add the suffix "Stream."</span></span>|
|`CodeAccessPermission IPermission`|<span data-ttu-id="dd0e3-141">✔️添加后缀 "权限"。</span><span class="sxs-lookup"><span data-stu-id="dd0e3-141">✔️ DO add the suffix "Permission."</span></span>|

## <a name="naming-enumerations"></a><span data-ttu-id="dd0e3-142">命名枚举</span><span class="sxs-lookup"><span data-stu-id="dd0e3-142">Naming Enumerations</span></span>
 <span data-ttu-id="dd0e3-143">一般情况下，枚举类型（也称为枚举）的名称应遵循标准的类型命名规则（PascalCasing 等）。</span><span class="sxs-lookup"><span data-stu-id="dd0e3-143">Names of enumeration types (also called enums) in general should follow the standard type-naming rules (PascalCasing, etc.).</span></span> <span data-ttu-id="dd0e3-144">但还有专用于枚举的其他准则。</span><span class="sxs-lookup"><span data-stu-id="dd0e3-144">However, there are additional guidelines that apply specifically to enums.</span></span>

 <span data-ttu-id="dd0e3-145">✔️为枚举使用单数类型名称，除非其值为位域。</span><span class="sxs-lookup"><span data-stu-id="dd0e3-145">✔️ DO use a singular type name for an enumeration unless its values are bit fields.</span></span>

 <span data-ttu-id="dd0e3-146">✔️对将位域作为值的枚举使用复数类型名称，也称为标志枚举。</span><span class="sxs-lookup"><span data-stu-id="dd0e3-146">✔️ DO use a plural type name for an enumeration with bit fields as values, also called flags enum.</span></span>

 <span data-ttu-id="dd0e3-147">❌ 不要在枚举类型名称中使用 "Enum" 后缀。</span><span class="sxs-lookup"><span data-stu-id="dd0e3-147">❌ DO NOT use an "Enum" suffix in enum type names.</span></span>

 <span data-ttu-id="dd0e3-148">❌ 不要在枚举类型名称中使用 "Flags" 或 "Flags" 后缀。</span><span class="sxs-lookup"><span data-stu-id="dd0e3-148">❌ DO NOT use "Flag" or "Flags" suffixes in enum type names.</span></span>

 <span data-ttu-id="dd0e3-149">❌ 不在枚举值名称（例如，用于 ADO 枚举的 "ad"、用于丰富文本枚举的 "rtf" 等）上使用前缀。</span><span class="sxs-lookup"><span data-stu-id="dd0e3-149">❌ DO NOT use a prefix on enumeration value names (e.g., "ad" for ADO enums, "rtf" for rich text enums, etc.).</span></span>

 <span data-ttu-id="dd0e3-150">*部分©2005，2009 Microsoft Corporation。保留所有权利。*</span><span class="sxs-lookup"><span data-stu-id="dd0e3-150">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>

 <span data-ttu-id="dd0e3-151">\*在 Pearson Education, Inc. 授权下，由 Addison-Wesley Professional 作为 Microsoft Windows 开发系列的一部分再版自 [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619)（Framework 设计准则：可重用 .NET 库的约定、惯例和模式第 2 版），由 Krzysztof Cwalina 和 Brad Abrams 发布于 2008 年 10 月 22 日。</span><span class="sxs-lookup"><span data-stu-id="dd0e3-151">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>

## <a name="see-also"></a><span data-ttu-id="dd0e3-152">另请参阅</span><span class="sxs-lookup"><span data-stu-id="dd0e3-152">See also</span></span>

- [<span data-ttu-id="dd0e3-153">框架设计指南</span><span class="sxs-lookup"><span data-stu-id="dd0e3-153">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
- [<span data-ttu-id="dd0e3-154">命名规则</span><span class="sxs-lookup"><span data-stu-id="dd0e3-154">Naming Guidelines</span></span>](../../../docs/standard/design-guidelines/naming-guidelines.md)
