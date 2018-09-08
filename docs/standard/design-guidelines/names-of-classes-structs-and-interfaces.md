---
title: 类、结构和接口的名称
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0c56f840bc5ebd5070c9b686384751acab3f0203
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/08/2018
ms.locfileid: "44197363"
---
# <a name="names-of-classes-structs-and-interfaces"></a><span data-ttu-id="a4c86-102">类、结构和接口的名称</span><span class="sxs-lookup"><span data-stu-id="a4c86-102">Names of Classes, Structs, and Interfaces</span></span>
<span data-ttu-id="a4c86-103">以下命名准则适用于常规类型命名。</span><span class="sxs-lookup"><span data-stu-id="a4c86-103">The naming guidelines that follow apply to general type naming.</span></span>  
  
 <span data-ttu-id="a4c86-104">**✓ 务必**通过使用 PascalCasing，用名词或名词短语命名类和结构。</span><span class="sxs-lookup"><span data-stu-id="a4c86-104">**✓ DO** name classes and structs with nouns or noun phrases, using PascalCasing.</span></span>  
  
 <span data-ttu-id="a4c86-105">这将类型名称与使用谓词短语命名的方法区分开来。</span><span class="sxs-lookup"><span data-stu-id="a4c86-105">This distinguishes type names from methods, which are named with verb phrases.</span></span>  
  
 <span data-ttu-id="a4c86-106">**✓ 务必**使用形容词短语命名接口，或偶尔用名词或名词短语命名接口。</span><span class="sxs-lookup"><span data-stu-id="a4c86-106">**✓ DO** name interfaces with adjective phrases, or occasionally with nouns or noun phrases.</span></span>  
  
 <span data-ttu-id="a4c86-107">应少使用名词和名词短语，它们可能会指示类型为抽象类而非接口。</span><span class="sxs-lookup"><span data-stu-id="a4c86-107">Nouns and noun phrases should be used rarely and they might indicate that the type should be an abstract class, and not an interface.</span></span>  
  
 <span data-ttu-id="a4c86-108">**X 不要**给类名加前缀（例如，"C"）。</span><span class="sxs-lookup"><span data-stu-id="a4c86-108">**X DO NOT** give class names a prefix (e.g., "C").</span></span>  
  
 <span data-ttu-id="a4c86-109">**✓ 考虑**使用基类的名称作为派生类名称的结尾部分。</span><span class="sxs-lookup"><span data-stu-id="a4c86-109">**✓ CONSIDER** ending the name of derived classes with the name of the base class.</span></span>  
  
 <span data-ttu-id="a4c86-110">这样可让名称非常易读，并清楚体现了关系。</span><span class="sxs-lookup"><span data-stu-id="a4c86-110">This is very readable and explains the relationship clearly.</span></span> <span data-ttu-id="a4c86-111">代码中的相关例子有：`ArgumentOutOfRangeException`，这是一种 `Exception`，还有 `SerializableAttribute`，这是一种 `Attribute`。</span><span class="sxs-lookup"><span data-stu-id="a4c86-111">Some examples of this in code are: `ArgumentOutOfRangeException`, which is a kind of `Exception`, and `SerializableAttribute`, which is a kind of `Attribute`.</span></span> <span data-ttu-id="a4c86-112">但是，在应用此准则时，务必应进行合理判断；例如，`Button` 类是一种 `Control` 事件，尽管其名称中并未出现 `Control`。</span><span class="sxs-lookup"><span data-stu-id="a4c86-112">However, it is important to use reasonable judgment in applying this guideline; for example, the `Button` class is a kind of `Control` event, although `Control` doesn’t appear in its name.</span></span>  
  
 <span data-ttu-id="a4c86-113">**✓ 务必**在接口名称前加上字母 I 作为前缀，以指示该类型是接口。</span><span class="sxs-lookup"><span data-stu-id="a4c86-113">**✓ DO** prefix interface names with the letter I, to indicate that the type is an interface.</span></span>  
  
 <span data-ttu-id="a4c86-114">例如，`IComponent`（描述性名词），`ICustomAttributeProvider`（名词短语）和 `IPersistable`（形容词）是合适的接口名称。与其他类型名称一样，应避免使用缩略形式。</span><span class="sxs-lookup"><span data-stu-id="a4c86-114">For example, `IComponent` (descriptive noun), `ICustomAttributeProvider` (noun phrase), and `IPersistable` (adjective) are appropriate interface names.</span></span> <span data-ttu-id="a4c86-115">与其他类型名称，避免缩写。</span><span class="sxs-lookup"><span data-stu-id="a4c86-115">As with other type names, avoid abbreviations.</span></span>  
  
 <span data-ttu-id="a4c86-116">**✓ 务必**确保在定义类和接口对时，类名称和接口名称的区别仅在于 "I" 前缀，其中类是接口的标准实现。</span><span class="sxs-lookup"><span data-stu-id="a4c86-116">**✓ DO** ensure that the names differ only by the "I" prefix on the interface name when you are defining a class–interface pair where the class is a standard implementation of the interface.</span></span>  
  
## <a name="names-of-generic-type-parameters"></a><span data-ttu-id="a4c86-117">泛型类型参数的名称</span><span class="sxs-lookup"><span data-stu-id="a4c86-117">Names of Generic Type Parameters</span></span>  
 <span data-ttu-id="a4c86-118">.NET Framework 2.0 中增添了泛型。</span><span class="sxs-lookup"><span data-stu-id="a4c86-118">Generics were added to .NET Framework 2.0.</span></span> <span data-ttu-id="a4c86-119">此功能引入了一种新的标识符称为*类型参数*。</span><span class="sxs-lookup"><span data-stu-id="a4c86-119">The feature introduced a new kind of identifier called *type parameter*.</span></span>  
  
 <span data-ttu-id="a4c86-120">**✓ 务必**使用描述性名称命名泛型参数，除非单字母名称可完整体现要传达的含义且描述性名称意义不大。</span><span class="sxs-lookup"><span data-stu-id="a4c86-120">**✓ DO** name generic type parameters with descriptive names unless a single-letter name is completely self-explanatory and a descriptive name would not add value.</span></span>  
  
 <span data-ttu-id="a4c86-121">**✓ 考虑**使用 `T` 作为具有一个单字母类型参数的类型的类型参数名称。</span><span class="sxs-lookup"><span data-stu-id="a4c86-121">**✓ CONSIDER** using `T` as the type parameter name for types with one single-letter type parameter.</span></span>  
  
```  
public int IComparer<T> { ... }  
public delegate bool Predicate<T>(T item);  
public struct Nullable<T> where T:struct { ... }  
```  
  
 <span data-ttu-id="a4c86-122">**✓ 务必**使用 `T` 作为描述性类型参数名称的前缀。</span><span class="sxs-lookup"><span data-stu-id="a4c86-122">**✓ DO** prefix descriptive type parameter names with `T`.</span></span>  
  
```  
public interface ISessionChannel<TSession> where TSession : ISession {  
    TSession Session { get; }  
}  
```  
  
 <span data-ttu-id="a4c86-123">**✓ 考虑**在参数名称中体现出对该类型参数设置的约束。</span><span class="sxs-lookup"><span data-stu-id="a4c86-123">**✓ CONSIDER** indicating constraints placed on a type parameter in the name of the parameter.</span></span>  
  
 <span data-ttu-id="a4c86-124">例如，被限制为 `ISession` 的参数可能名为 `TSession`。</span><span class="sxs-lookup"><span data-stu-id="a4c86-124">For example, a parameter constrained to `ISession` might be called `TSession`.</span></span>  
  
## <a name="names-of-common-types"></a><span data-ttu-id="a4c86-125">常见类型的名称</span><span class="sxs-lookup"><span data-stu-id="a4c86-125">Names of Common Types</span></span>  
 <span data-ttu-id="a4c86-126">**✓ 务必**在命名从某些 .NET Framework 类型派生的类型或在实现某些 .NET Framework 类型时，遵循下表所述准则。</span><span class="sxs-lookup"><span data-stu-id="a4c86-126">**✓ DO** follow the guidelines described in the following table when naming types derived from or implementing certain .NET Framework types.</span></span>  
  
|<span data-ttu-id="a4c86-127">基类型</span><span class="sxs-lookup"><span data-stu-id="a4c86-127">Base Type</span></span>|<span data-ttu-id="a4c86-128">派生的实现类型准则</span><span class="sxs-lookup"><span data-stu-id="a4c86-128">Derived/Implementing Type Guideline</span></span>|  
|---------------|------------------------------------------|  
|`System.Attribute`|<span data-ttu-id="a4c86-129">**✓ 务必**为自定义属性类的名称添加后缀 "Attribute"。</span><span class="sxs-lookup"><span data-stu-id="a4c86-129">**✓ DO** add the suffix "Attribute" to names of custom attribute classes.</span></span>|  
|`System.Delegate`|<span data-ttu-id="a4c86-130">**✓ 务必**向事件中所用委托的名称中添加后缀 "EventHandler"。</span><span class="sxs-lookup"><span data-stu-id="a4c86-130">**✓ DO** add the suffix "EventHandler" to names of delegates that are used in events.</span></span><br /><br /> <span data-ttu-id="a4c86-131">**✓ 务必**在用作事件处理程序的委托以外的委托名称中添加后缀 "Callback"。</span><span class="sxs-lookup"><span data-stu-id="a4c86-131">**✓ DO** add the suffix "Callback" to names of delegates other than those used as event handlers.</span></span><br /><br /> <span data-ttu-id="a4c86-132">**X 不要**将后缀 "Delegate" 添加到委托。</span><span class="sxs-lookup"><span data-stu-id="a4c86-132">**X DO NOT** add the suffix "Delegate" to a delegate.</span></span>|  
|`System.EventArgs`|<span data-ttu-id="a4c86-133">**✓ 务必**添加后缀 "EventArgs"。</span><span class="sxs-lookup"><span data-stu-id="a4c86-133">**✓ DO** add the suffix "EventArgs."</span></span>|  
|`System.Enum`|<span data-ttu-id="a4c86-134">**X 不要**从此类派生；而是使用所用语言支持的关键字；例如，在 C# 中，使用关键字 `enum`。</span><span class="sxs-lookup"><span data-stu-id="a4c86-134">**X DO NOT** derive from this class; use the keyword supported by your language instead; for example, in C#, use the `enum` keyword.</span></span><br /><br /> <span data-ttu-id="a4c86-135">**X 不要**添加后缀 "Enum" 或 "Flag"。</span><span class="sxs-lookup"><span data-stu-id="a4c86-135">**X DO NOT** add the suffix "Enum" or "Flag."</span></span>|  
|`System.Exception`|<span data-ttu-id="a4c86-136">**✓ 务必**添加后缀 "Exception"。</span><span class="sxs-lookup"><span data-stu-id="a4c86-136">**✓ DO** add the suffix "Exception."</span></span>|  
|`IDictionary` <br /> `IDictionary<TKey,TValue>`|<span data-ttu-id="a4c86-137">**✓ 务必**添加后缀 "Dictionary"。</span><span class="sxs-lookup"><span data-stu-id="a4c86-137">**✓ DO** add the suffix "Dictionary."</span></span> <span data-ttu-id="a4c86-138">请注意，`IDictionary` 是一种特定类型的集合，但此准则优先于后面更宽泛的集合准则。</span><span class="sxs-lookup"><span data-stu-id="a4c86-138">Note that `IDictionary` is a specific type of collection, but this guideline takes precedence over the more general collections guideline that follows.</span></span>|  
|`IEnumerable` <br /> `ICollection` <br /> `IList` <br /> `IEnumerable<T>` <br /> `ICollection<T>` <br /> `IList<T>`|<span data-ttu-id="a4c86-139">**✓ 务必**添加后缀 "Collection"。</span><span class="sxs-lookup"><span data-stu-id="a4c86-139">**✓ DO** add the suffix "Collection."</span></span>|  
|`System.IO.Stream`|<span data-ttu-id="a4c86-140">**✓ 务必**添加后缀 "Stream"。</span><span class="sxs-lookup"><span data-stu-id="a4c86-140">**✓ DO** add the suffix "Stream."</span></span>|  
|`CodeAccessPermission IPermission`|<span data-ttu-id="a4c86-141">**✓ 务必**添加后缀 "Permission"。</span><span class="sxs-lookup"><span data-stu-id="a4c86-141">**✓ DO** add the suffix "Permission."</span></span>|  
  
## <a name="naming-enumerations"></a><span data-ttu-id="a4c86-142">命名枚举</span><span class="sxs-lookup"><span data-stu-id="a4c86-142">Naming Enumerations</span></span>  
 <span data-ttu-id="a4c86-143">一般情况下，枚举类型（也称为枚举）的名称应遵循标准的类型命名规则（PascalCasing 等）。</span><span class="sxs-lookup"><span data-stu-id="a4c86-143">Names of enumeration types (also called enums) in general should follow the standard type-naming rules (PascalCasing, etc.).</span></span> <span data-ttu-id="a4c86-144">但还有专用于枚举的其他准则。</span><span class="sxs-lookup"><span data-stu-id="a4c86-144">However, there are additional guidelines that apply specifically to enums.</span></span>  
  
 <span data-ttu-id="a4c86-145">**✓ 务必**为枚举使用单数形式的类型名称，除非枚举值是位域。</span><span class="sxs-lookup"><span data-stu-id="a4c86-145">**✓ DO** use a singular type name for an enumeration unless its values are bit fields.</span></span>  
  
 <span data-ttu-id="a4c86-146">**✓ 务必**为值为位域的枚举使用复数形式的类型名称，这类枚举也称为标志枚举。</span><span class="sxs-lookup"><span data-stu-id="a4c86-146">**✓ DO** use a plural type name for an enumeration with bit fields as values, also called flags enum.</span></span>  
  
 <span data-ttu-id="a4c86-147">**X 不要**在枚举类型名称中使用 "Enum" 作为后缀。</span><span class="sxs-lookup"><span data-stu-id="a4c86-147">**X DO NOT** use an "Enum" suffix in enum type names.</span></span>  
  
 <span data-ttu-id="a4c86-148">**X 不要**在枚举类型名称中使用 "Flag" 或 "Flags" 作为后缀。</span><span class="sxs-lookup"><span data-stu-id="a4c86-148">**X DO NOT** use "Flag" or "Flags" suffixes in enum type names.</span></span>  
  
 <span data-ttu-id="a4c86-149">**X 不要**在枚举值名称中使用前缀（例如，对 ADO 枚举使用 "ad”，对富文本枚举使用 "rtf" 等）。</span><span class="sxs-lookup"><span data-stu-id="a4c86-149">**X DO NOT** use a prefix on enumeration value names (e.g., "ad" for ADO enums, "rtf" for rich text enums, etc.).</span></span>  
  
 <span data-ttu-id="a4c86-150">*部分版权 © 2005, 2009 Microsoft Corporation。保留所有权利。*</span><span class="sxs-lookup"><span data-stu-id="a4c86-150">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="a4c86-151">*经 Pearson Education, Inc 授权，转载自[框架设计准则：可重用的 .NET 库的约定、习惯用语和模式，第2版](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) 作者：Krzysztof Cwalina 和 Brad Abrams，由 Addison Wesley Professional 于 2008 年 10 月 22 日印发，作为 Microsoft Windows 开发系列的一部分。*</span><span class="sxs-lookup"><span data-stu-id="a4c86-151">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a4c86-152">请参阅</span><span class="sxs-lookup"><span data-stu-id="a4c86-152">See also</span></span>

- [<span data-ttu-id="a4c86-153">框架设计指南</span><span class="sxs-lookup"><span data-stu-id="a4c86-153">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)  
- [<span data-ttu-id="a4c86-154">命名规则</span><span class="sxs-lookup"><span data-stu-id="a4c86-154">Naming Guidelines</span></span>](../../../docs/standard/design-guidelines/naming-guidelines.md)
