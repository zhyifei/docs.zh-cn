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
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/14/2020
ms.locfileid: "79401237"
---
# <a name="names-of-classes-structs-and-interfaces"></a><span data-ttu-id="8afa3-102">类、结构和接口的名称</span><span class="sxs-lookup"><span data-stu-id="8afa3-102">Names of Classes, Structs, and Interfaces</span></span>
<span data-ttu-id="8afa3-103">以下命名准则适用于常规类型命名。</span><span class="sxs-lookup"><span data-stu-id="8afa3-103">The naming guidelines that follow apply to general type naming.</span></span>

 <span data-ttu-id="8afa3-104">✔️使用 PascalCasing 命名类和带有名词或名词短语的结构。</span><span class="sxs-lookup"><span data-stu-id="8afa3-104">✔️ DO name classes and structs with nouns or noun phrases, using PascalCasing.</span></span>

 <span data-ttu-id="8afa3-105">这将类型名称与用动词短语命名的方法区分开来。</span><span class="sxs-lookup"><span data-stu-id="8afa3-105">This distinguishes type names from methods, which are named with verb phrases.</span></span>

 <span data-ttu-id="8afa3-106">✔️使用形容词短语，或偶尔使用名词或名词短语进行命名界面。</span><span class="sxs-lookup"><span data-stu-id="8afa3-106">✔️ DO name interfaces with adjective phrases, or occasionally with nouns or noun phrases.</span></span>

 <span data-ttu-id="8afa3-107">名词和名词短语应很少使用，它们可能表示类型应为抽象类，而不是接口。</span><span class="sxs-lookup"><span data-stu-id="8afa3-107">Nouns and noun phrases should be used rarely and they might indicate that the type should be an abstract class, and not an interface.</span></span>

 <span data-ttu-id="8afa3-108">❌不要给类名前缀（例如，"C"）。</span><span class="sxs-lookup"><span data-stu-id="8afa3-108">❌ DO NOT give class names a prefix (e.g., "C").</span></span>

 <span data-ttu-id="8afa3-109">✔️考虑用基类的名称结束派生类的名称。</span><span class="sxs-lookup"><span data-stu-id="8afa3-109">✔️ CONSIDER ending the name of derived classes with the name of the base class.</span></span>

 <span data-ttu-id="8afa3-110">这是非常可读的，并清楚地解释了这种关系。</span><span class="sxs-lookup"><span data-stu-id="8afa3-110">This is very readable and explains the relationship clearly.</span></span> <span data-ttu-id="8afa3-111">代码中这方面的一些示例是： `ArgumentOutOfRangeException`，这是一种`Exception`，和`SerializableAttribute`，是 一`Attribute`种 。</span><span class="sxs-lookup"><span data-stu-id="8afa3-111">Some examples of this in code are: `ArgumentOutOfRangeException`, which is a kind of `Exception`, and `SerializableAttribute`, which is a kind of `Attribute`.</span></span> <span data-ttu-id="8afa3-112">但是，在适用本准则时，必须运用合理的判断;例如，`Button`类是一种`Control`事件，尽管`Control`未出现在其名称中。</span><span class="sxs-lookup"><span data-stu-id="8afa3-112">However, it is important to use reasonable judgment in applying this guideline; for example, the `Button` class is a kind of `Control` event, although `Control` doesn’t appear in its name.</span></span>

 <span data-ttu-id="8afa3-113">✔️ DO 前缀接口名称与字母 I，以指示类型是接口。</span><span class="sxs-lookup"><span data-stu-id="8afa3-113">✔️ DO prefix interface names with the letter I, to indicate that the type is an interface.</span></span>

 <span data-ttu-id="8afa3-114">例如，（`IComponent`描述性名词）、（`ICustomAttributeProvider`名词短语）和`IPersistable`（形容词）是适当的接口名称。</span><span class="sxs-lookup"><span data-stu-id="8afa3-114">For example, `IComponent` (descriptive noun), `ICustomAttributeProvider` (noun phrase), and `IPersistable` (adjective) are appropriate interface names.</span></span> <span data-ttu-id="8afa3-115">与其他类型名称一样，请避免缩写。</span><span class="sxs-lookup"><span data-stu-id="8afa3-115">As with other type names, avoid abbreviations.</span></span>

 <span data-ttu-id="8afa3-116">✔️，在定义类接口对时，确保名称仅与接口名称上的"I"前缀不同，其中类是接口的标准实现。</span><span class="sxs-lookup"><span data-stu-id="8afa3-116">✔️ DO ensure that the names differ only by the "I" prefix on the interface name when you are defining a class–interface pair where the class is a standard implementation of the interface.</span></span>

## <a name="names-of-generic-type-parameters"></a><span data-ttu-id="8afa3-117">泛型类型参数的名称</span><span class="sxs-lookup"><span data-stu-id="8afa3-117">Names of Generic Type Parameters</span></span>
 <span data-ttu-id="8afa3-118">泛型已添加到 .NET 框架 2.0 中。</span><span class="sxs-lookup"><span data-stu-id="8afa3-118">Generics were added to .NET Framework 2.0.</span></span> <span data-ttu-id="8afa3-119">该功能引入了一种称为*类型参数*的标识符。</span><span class="sxs-lookup"><span data-stu-id="8afa3-119">The feature introduced a new kind of identifier called *type parameter*.</span></span>

 <span data-ttu-id="8afa3-120">✔️ DO 名称泛型类型参数（带有描述性名称）除非单字母名称完全不言自明，并且描述性名称不会增加值。</span><span class="sxs-lookup"><span data-stu-id="8afa3-120">✔️ DO name generic type parameters with descriptive names unless a single-letter name is completely self-explanatory and a descriptive name would not add value.</span></span>

 <span data-ttu-id="8afa3-121">✔️考虑使用`T`具有单字母类型参数的类型作为类型参数名称。</span><span class="sxs-lookup"><span data-stu-id="8afa3-121">✔️ CONSIDER using `T` as the type parameter name for types with one single-letter type parameter.</span></span>

```csharp
public int IComparer<T> { ... }
public delegate bool Predicate<T>(T item);
public struct Nullable<T> where T:struct { ... }
```

 <span data-ttu-id="8afa3-122">✔️ DO 前缀描述性`T`类型参数名称。</span><span class="sxs-lookup"><span data-stu-id="8afa3-122">✔️ DO prefix descriptive type parameter names with `T`.</span></span>

```csharp
public interface ISessionChannel<TSession> where TSession : ISession {
    TSession Session { get; }
}
```

 <span data-ttu-id="8afa3-123">✔️考虑指示在参数名称中对类型参数放置的约束。</span><span class="sxs-lookup"><span data-stu-id="8afa3-123">✔️ CONSIDER indicating constraints placed on a type parameter in the name of the parameter.</span></span>

 <span data-ttu-id="8afa3-124">例如，约束到`ISession`的参数可能称为`TSession`。</span><span class="sxs-lookup"><span data-stu-id="8afa3-124">For example, a parameter constrained to `ISession` might be called `TSession`.</span></span>

## <a name="names-of-common-types"></a><span data-ttu-id="8afa3-125">常见类型的名称</span><span class="sxs-lookup"><span data-stu-id="8afa3-125">Names of Common Types</span></span>
 <span data-ttu-id="8afa3-126">✔️命名派生自某些 .NET 框架类型或实现某些 .NET 框架类型时，请遵循下表中描述的准则。</span><span class="sxs-lookup"><span data-stu-id="8afa3-126">✔️ DO follow the guidelines described in the following table when naming types derived from or implementing certain .NET Framework types.</span></span>

|<span data-ttu-id="8afa3-127">基类型</span><span class="sxs-lookup"><span data-stu-id="8afa3-127">Base Type</span></span>|<span data-ttu-id="8afa3-128">派生/实现类型指南</span><span class="sxs-lookup"><span data-stu-id="8afa3-128">Derived/Implementing Type Guideline</span></span>|
|---------------|------------------------------------------|
|`System.Attribute`|<span data-ttu-id="8afa3-129">✔️DO将后缀"属性"添加到自定义属性类的名称中。</span><span class="sxs-lookup"><span data-stu-id="8afa3-129">✔️ DO add the suffix "Attribute" to names of custom attribute classes.</span></span>|
|`System.Delegate`|<span data-ttu-id="8afa3-130">✔️DO将后缀"事件处理程序"添加到事件中使用的委托名称中。</span><span class="sxs-lookup"><span data-stu-id="8afa3-130">✔️ DO add the suffix "EventHandler" to names of delegates that are used in events.</span></span><br /><br /> <span data-ttu-id="8afa3-131">✔️将后缀"回调"添加到用作事件处理程序的委托名称以外的委托名称中。</span><span class="sxs-lookup"><span data-stu-id="8afa3-131">✔️ DO add the suffix "Callback" to names of delegates other than those used as event handlers.</span></span><br /><br /> <span data-ttu-id="8afa3-132">❌不要将后缀"委托"添加到委托。</span><span class="sxs-lookup"><span data-stu-id="8afa3-132">❌ DO NOT add the suffix "Delegate" to a delegate.</span></span>|
|`System.EventArgs`|<span data-ttu-id="8afa3-133">✔️添加后缀"事件阿格"。</span><span class="sxs-lookup"><span data-stu-id="8afa3-133">✔️ DO add the suffix "EventArgs."</span></span>|
|`System.Enum`|<span data-ttu-id="8afa3-134">❌不要从此类派生;因此，请勿从此类派生。改用语言支持的关键字;例如，在 C# 中，`enum`使用 关键字。</span><span class="sxs-lookup"><span data-stu-id="8afa3-134">❌ DO NOT derive from this class; use the keyword supported by your language instead; for example, in C#, use the `enum` keyword.</span></span><br /><br /> <span data-ttu-id="8afa3-135">❌请勿添加后缀"枚举"或"标记"。</span><span class="sxs-lookup"><span data-stu-id="8afa3-135">❌ DO NOT add the suffix "Enum" or "Flag."</span></span>|
|`System.Exception`|<span data-ttu-id="8afa3-136">✔️添加后缀"异常"。</span><span class="sxs-lookup"><span data-stu-id="8afa3-136">✔️ DO add the suffix "Exception."</span></span>|
|`IDictionary` <br /> `IDictionary<TKey,TValue>`|<span data-ttu-id="8afa3-137">✔️添加后缀"字典"。</span><span class="sxs-lookup"><span data-stu-id="8afa3-137">✔️ DO add the suffix "Dictionary."</span></span> <span data-ttu-id="8afa3-138">请注意，`IDictionary`这是特定类型的集合，但此准则优先于以下更常规的集合准则。</span><span class="sxs-lookup"><span data-stu-id="8afa3-138">Note that `IDictionary` is a specific type of collection, but this guideline takes precedence over the more general collections guideline that follows.</span></span>|
|`IEnumerable` <br /> `ICollection` <br /> `IList` <br /> `IEnumerable<T>` <br /> `ICollection<T>` <br /> `IList<T>`|<span data-ttu-id="8afa3-139">✔️添加后缀"集合"。</span><span class="sxs-lookup"><span data-stu-id="8afa3-139">✔️ DO add the suffix "Collection."</span></span>|
|`System.IO.Stream`|<span data-ttu-id="8afa3-140">✔️添加后缀"流"。</span><span class="sxs-lookup"><span data-stu-id="8afa3-140">✔️ DO add the suffix "Stream."</span></span>|
|`CodeAccessPermission IPermission`|<span data-ttu-id="8afa3-141">✔️添加后缀"权限"。</span><span class="sxs-lookup"><span data-stu-id="8afa3-141">✔️ DO add the suffix "Permission."</span></span>|

## <a name="naming-enumerations"></a><span data-ttu-id="8afa3-142">命名枚举</span><span class="sxs-lookup"><span data-stu-id="8afa3-142">Naming Enumerations</span></span>
 <span data-ttu-id="8afa3-143">枚举类型（也称为枚举）的名称通常应遵循标准类型命名规则（PascalCasing 等）。</span><span class="sxs-lookup"><span data-stu-id="8afa3-143">Names of enumeration types (also called enums) in general should follow the standard type-naming rules (PascalCasing, etc.).</span></span> <span data-ttu-id="8afa3-144">但是，还有其他特别适用于枚举的准则。</span><span class="sxs-lookup"><span data-stu-id="8afa3-144">However, there are additional guidelines that apply specifically to enums.</span></span>

 <span data-ttu-id="8afa3-145">✔️DO使用单一类型名称进行枚举，除非其值为位字段。</span><span class="sxs-lookup"><span data-stu-id="8afa3-145">✔️ DO use a singular type name for an enumeration unless its values are bit fields.</span></span>

 <span data-ttu-id="8afa3-146">✔️DO使用复数类型名称进行枚举，其中位字段为值，也称为标志枚举。</span><span class="sxs-lookup"><span data-stu-id="8afa3-146">✔️ DO use a plural type name for an enumeration with bit fields as values, also called flags enum.</span></span>

 <span data-ttu-id="8afa3-147">❌请勿在枚举类型名称中使用"枚举"后缀。</span><span class="sxs-lookup"><span data-stu-id="8afa3-147">❌ DO NOT use an "Enum" suffix in enum type names.</span></span>

 <span data-ttu-id="8afa3-148">❌请勿在枚举类型名称中使用"标记"或"标记"后缀。</span><span class="sxs-lookup"><span data-stu-id="8afa3-148">❌ DO NOT use "Flag" or "Flags" suffixes in enum type names.</span></span>

 <span data-ttu-id="8afa3-149">❌请勿在枚举值名称上使用前缀（例如，ADO 枚举的"ad"，富文本枚举的"rtf"等）。</span><span class="sxs-lookup"><span data-stu-id="8afa3-149">❌ DO NOT use a prefix on enumeration value names (e.g., "ad" for ADO enums, "rtf" for rich text enums, etc.).</span></span>

 <span data-ttu-id="8afa3-150">*部分© 2005， 2009 微软公司.保留所有权利。*</span><span class="sxs-lookup"><span data-stu-id="8afa3-150">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>

 <span data-ttu-id="8afa3-151">*经 Pearson 教育公司许可，从[框架设计指南：可重用的约定、习语和模式 .NET 库重新打印，第二版](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619)由 Krzysztof Cwalina 和 Brad Abrams 出版，由艾迪森-韦斯利专业公司作为微软 Windows 开发系列的一部分于 2008 年 10 月 22 日出版。*</span><span class="sxs-lookup"><span data-stu-id="8afa3-151">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>

## <a name="see-also"></a><span data-ttu-id="8afa3-152">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8afa3-152">See also</span></span>

- [<span data-ttu-id="8afa3-153">框架设计准则</span><span class="sxs-lookup"><span data-stu-id="8afa3-153">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
- [<span data-ttu-id="8afa3-154">命名规则</span><span class="sxs-lookup"><span data-stu-id="8afa3-154">Naming Guidelines</span></span>](../../../docs/standard/design-guidelines/naming-guidelines.md)
