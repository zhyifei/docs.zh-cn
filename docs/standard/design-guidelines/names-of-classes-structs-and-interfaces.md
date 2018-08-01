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
ms.openlocfilehash: a1841fbfcb76d5b56681b63ec4b39e9a7418707f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33576137"
---
# <a name="names-of-classes-structs-and-interfaces"></a><span data-ttu-id="afdb9-102">类、结构和接口的名称</span><span class="sxs-lookup"><span data-stu-id="afdb9-102">Names of Classes, Structs, and Interfaces</span></span>
<span data-ttu-id="afdb9-103">以下命名准则适用于常规类型命名。</span><span class="sxs-lookup"><span data-stu-id="afdb9-103">The naming guidelines that follow apply to general type naming.</span></span>  
  
 <span data-ttu-id="afdb9-104">**✓ DO** 命名类和结构与名词或名词短语，使用 PascalCasing。</span><span class="sxs-lookup"><span data-stu-id="afdb9-104">**✓ DO** name classes and structs with nouns or noun phrases, using PascalCasing.</span></span>  
  
 <span data-ttu-id="afdb9-105">这将类型名称与方法名称中带有谓词短语区分开来。</span><span class="sxs-lookup"><span data-stu-id="afdb9-105">This distinguishes type names from methods, which are named with verb phrases.</span></span>  
  
 <span data-ttu-id="afdb9-106">**✓ DO** 命名接口使用形容词短语或偶尔名词或名词短语。</span><span class="sxs-lookup"><span data-stu-id="afdb9-106">**✓ DO** name interfaces with adjective phrases, or occasionally with nouns or noun phrases.</span></span>  
  
 <span data-ttu-id="afdb9-107">应该很少使用名词和名词短语，并且它们可能指示该类型应为一个抽象类，并不是接口。</span><span class="sxs-lookup"><span data-stu-id="afdb9-107">Nouns and noun phrases should be used rarely and they might indicate that the type should be an abstract class, and not an interface.</span></span>  
  
 <span data-ttu-id="afdb9-108">**X DO NOT** 为前缀 (例如，"C") 的类名。</span><span class="sxs-lookup"><span data-stu-id="afdb9-108">**X DO NOT** give class names a prefix (e.g., "C").</span></span>  
  
 <span data-ttu-id="afdb9-109">**✓ CONSIDER** 结束的名称派生类同名的基类。</span><span class="sxs-lookup"><span data-stu-id="afdb9-109">**✓ CONSIDER** ending the name of derived classes with the name of the base class.</span></span>  
  
 <span data-ttu-id="afdb9-110">这是非常可读，并且清楚地说明关系。</span><span class="sxs-lookup"><span data-stu-id="afdb9-110">This is very readable and explains the relationship clearly.</span></span> <span data-ttu-id="afdb9-111">这在代码中的一些示例包括： `ArgumentOutOfRangeException`，这是一种类型的`Exception`，和`SerializableAttribute`，这是一种类型的`Attribute`。</span><span class="sxs-lookup"><span data-stu-id="afdb9-111">Some examples of this in code are: `ArgumentOutOfRangeException`, which is a kind of `Exception`, and `SerializableAttribute`, which is a kind of `Attribute`.</span></span> <span data-ttu-id="afdb9-112">但是，务必使用合理的判断，在将应用此原则;例如，`Button`类是一种类型的`Control`事件，尽管`Control`未出现在其名称。</span><span class="sxs-lookup"><span data-stu-id="afdb9-112">However, it is important to use reasonable judgment in applying this guideline; for example, the `Button` class is a kind of `Control` event, although `Control` doesn’t appear in its name.</span></span>  
  
 <span data-ttu-id="afdb9-113">**✓ DO** 前缀接口名称以字母 I，以指示类型是接口。</span><span class="sxs-lookup"><span data-stu-id="afdb9-113">**✓ DO** prefix interface names with the letter I, to indicate that the type is an interface.</span></span>  
  
 <span data-ttu-id="afdb9-114">例如， `IComponent` （描述性名词）， `ICustomAttributeProvider` （名词短语），和`IPersistable`（形容词） 是适当的接口名称。</span><span class="sxs-lookup"><span data-stu-id="afdb9-114">For example, `IComponent` (descriptive noun), `ICustomAttributeProvider` (noun phrase), and `IPersistable` (adjective) are appropriate interface names.</span></span> <span data-ttu-id="afdb9-115">与其他类型名称，避免缩写。</span><span class="sxs-lookup"><span data-stu-id="afdb9-115">As with other type names, avoid abbreviations.</span></span>  
  
 <span data-ttu-id="afdb9-116">**✓ DO** 确保的名称不同仅通过"I"前缀的接口名称定义其中类是接口的标准实现的类 – 接口对时。</span><span class="sxs-lookup"><span data-stu-id="afdb9-116">**✓ DO** ensure that the names differ only by the "I" prefix on the interface name when you are defining a class–interface pair where the class is a standard implementation of the interface.</span></span>  
  
## <a name="names-of-generic-type-parameters"></a><span data-ttu-id="afdb9-117">泛型类型参数的名称</span><span class="sxs-lookup"><span data-stu-id="afdb9-117">Names of Generic Type Parameters</span></span>  
 <span data-ttu-id="afdb9-118">泛型已添加到.NET Framework 2.0。</span><span class="sxs-lookup"><span data-stu-id="afdb9-118">Generics were added to .NET Framework 2.0.</span></span> <span data-ttu-id="afdb9-119">推出的功能的一种新的标识符称为*类型参数*。</span><span class="sxs-lookup"><span data-stu-id="afdb9-119">The feature introduced a new kind of identifier called *type parameter*.</span></span>  
  
 <span data-ttu-id="afdb9-120">**✓ DO** 使用描述性名称 name 泛型类型参数，除非单个字母的名称是完全一目了然，并且描述性的名称将不会增加价值。</span><span class="sxs-lookup"><span data-stu-id="afdb9-120">**✓ DO** name generic type parameters with descriptive names unless a single-letter name is completely self-explanatory and a descriptive name would not add value.</span></span>  
  
 <span data-ttu-id="afdb9-121">**✓ CONSIDER** 使用`T`作为具有一个单字母类型参数的类型的类型参数名称。</span><span class="sxs-lookup"><span data-stu-id="afdb9-121">**✓ CONSIDER** using `T` as the type parameter name for types with one single-letter type parameter.</span></span>  
  
```  
public int IComparer<T> { ... }  
public delegate bool Predicate<T>(T item);  
public struct Nullable<T> where T:struct { ... }  
```  
  
 <span data-ttu-id="afdb9-122">**✓ DO** 前缀描述性类型参数名的`T`。</span><span class="sxs-lookup"><span data-stu-id="afdb9-122">**✓ DO** prefix descriptive type parameter names with `T`.</span></span>  
  
```  
public interface ISessionChannel<TSession> where TSession : ISession{  
    TSession Session { get; }  
}  
```  
  
 <span data-ttu-id="afdb9-123">**✓ CONSIDER** ，该值指示约束放置在类型参数在参数名。</span><span class="sxs-lookup"><span data-stu-id="afdb9-123">**✓ CONSIDER** indicating constraints placed on a type parameter in the name of the parameter.</span></span>  
  
 <span data-ttu-id="afdb9-124">例如，将参数约束为`ISession`可能调用`TSession`。</span><span class="sxs-lookup"><span data-stu-id="afdb9-124">For example, a parameter constrained to `ISession` might be called `TSession`.</span></span>  
  
## <a name="names-of-common-types"></a><span data-ttu-id="afdb9-125">常见类型的名称</span><span class="sxs-lookup"><span data-stu-id="afdb9-125">Names of Common Types</span></span>  
 <span data-ttu-id="afdb9-126">**✓ DO** 遵循命名类型派生自或实现某些.NET Framework 类型时下表中所述的指南。</span><span class="sxs-lookup"><span data-stu-id="afdb9-126">**✓ DO** follow the guidelines described in the following table when naming types derived from or implementing certain .NET Framework types.</span></span>  
  
|<span data-ttu-id="afdb9-127">基类型</span><span class="sxs-lookup"><span data-stu-id="afdb9-127">Base Type</span></span>|<span data-ttu-id="afdb9-128">派生/实现类型准则</span><span class="sxs-lookup"><span data-stu-id="afdb9-128">Derived/Implementing Type Guideline</span></span>|  
|---------------|------------------------------------------|  
|`System.Attribute`|<span data-ttu-id="afdb9-129">**✓ DO** 将后缀"属性"添加到自定义特性类的名称。</span><span class="sxs-lookup"><span data-stu-id="afdb9-129">**✓ DO** add the suffix "Attribute" to names of custom attribute classes.</span></span>|  
|`System.Delegate`|<span data-ttu-id="afdb9-130">**✓ DO** 将后缀"EventHandler"添加到的事件中使用的委托的名称。</span><span class="sxs-lookup"><span data-stu-id="afdb9-130">**✓ DO** add the suffix "EventHandler" to names of delegates that are used in events.</span></span><br /><br /> <span data-ttu-id="afdb9-131">**✓ DO** 添加之外作为事件处理程序使用的后缀"Callback"的名称的委托。</span><span class="sxs-lookup"><span data-stu-id="afdb9-131">**✓ DO** add the suffix "Callback" to names of delegates other than those used as event handlers.</span></span><br /><br /> <span data-ttu-id="afdb9-132">**X DO NOT** 将后缀"委托"添加到委托。</span><span class="sxs-lookup"><span data-stu-id="afdb9-132">**X DO NOT** add the suffix "Delegate" to a delegate.</span></span>|  
|`System.EventArgs`|<span data-ttu-id="afdb9-133">**✓ DO** 添加后缀"EventArgs。"</span><span class="sxs-lookup"><span data-stu-id="afdb9-133">**✓ DO** add the suffix "EventArgs."</span></span>|  
|`System.Enum`|<span data-ttu-id="afdb9-134">**X DO NOT** 从此类派生; 使用改为支持你的语言关键字; 例如，在 C# 中，使用`enum`关键字。</span><span class="sxs-lookup"><span data-stu-id="afdb9-134">**X DO NOT** derive from this class; use the keyword supported by your language instead; for example, in C#, use the `enum` keyword.</span></span><br /><br /> <span data-ttu-id="afdb9-135">**X DO NOT** 添加后缀"枚举"或"标志"。</span><span class="sxs-lookup"><span data-stu-id="afdb9-135">**X DO NOT** add the suffix "Enum" or "Flag."</span></span>|  
|`System.Exception`|<span data-ttu-id="afdb9-136">**✓ DO** 添加后缀"异常"。</span><span class="sxs-lookup"><span data-stu-id="afdb9-136">**✓ DO** add the suffix "Exception."</span></span>|  
|`IDictionary` <br /> `IDictionary<TKey,TValue>`|<span data-ttu-id="afdb9-137">**✓ DO** 添加后缀"字典。"</span><span class="sxs-lookup"><span data-stu-id="afdb9-137">**✓ DO** add the suffix "Dictionary."</span></span> <span data-ttu-id="afdb9-138">请注意，`IDictionary`是特定类型的集合，但这一准则将优先于后面的更多常规集合准则。</span><span class="sxs-lookup"><span data-stu-id="afdb9-138">Note that `IDictionary` is a specific type of collection, but this guideline takes precedence over the more general collections guideline that follows.</span></span>|  
|`IEnumerable` <br /> `ICollection` <br /> `IList` <br /> `IEnumerable<T>` <br /> `ICollection<T>` <br /> `IList<T>`|<span data-ttu-id="afdb9-139">**✓ DO** 添加后缀"集合"。</span><span class="sxs-lookup"><span data-stu-id="afdb9-139">**✓ DO** add the suffix "Collection."</span></span>|  
|`System.IO.Stream`|<span data-ttu-id="afdb9-140">**✓ DO** 添加后缀"流"。</span><span class="sxs-lookup"><span data-stu-id="afdb9-140">**✓ DO** add the suffix "Stream."</span></span>|  
|`CodeAccessPermission IPermission`|<span data-ttu-id="afdb9-141">**✓ DO** 添加后缀"权限。"</span><span class="sxs-lookup"><span data-stu-id="afdb9-141">**✓ DO** add the suffix "Permission."</span></span>|  
  
## <a name="naming-enumerations"></a><span data-ttu-id="afdb9-142">命名枚举</span><span class="sxs-lookup"><span data-stu-id="afdb9-142">Naming Enumerations</span></span>  
 <span data-ttu-id="afdb9-143">一般情况下 （也称为枚举） 的枚举类型的名称应遵循的标准类型命名规则 （PascalCasing 等）。</span><span class="sxs-lookup"><span data-stu-id="afdb9-143">Names of enumeration types (also called enums) in general should follow the standard type-naming rules (PascalCasing, etc.).</span></span> <span data-ttu-id="afdb9-144">但是，有专门适用于枚举的其他指导原则。</span><span class="sxs-lookup"><span data-stu-id="afdb9-144">However, there are additional guidelines that apply specifically to enums.</span></span>  
  
 <span data-ttu-id="afdb9-145">**✓ DO** 使用枚举的单数形式的类型名称，除非其值是位域。</span><span class="sxs-lookup"><span data-stu-id="afdb9-145">**✓ DO** use a singular type name for an enumeration unless its values are bit fields.</span></span>  
  
 <span data-ttu-id="afdb9-146">**✓ DO** 使用位域的枚举的复数形式的类型名称将用作值，也称为标志枚举。</span><span class="sxs-lookup"><span data-stu-id="afdb9-146">**✓ DO** use a plural type name for an enumeration with bit fields as values, also called flags enum.</span></span>  
  
 <span data-ttu-id="afdb9-147">**X DO NOT** 在枚举类型名称中使用"枚举"后缀。</span><span class="sxs-lookup"><span data-stu-id="afdb9-147">**X DO NOT** use an "Enum" suffix in enum type names.</span></span>  
  
 <span data-ttu-id="afdb9-148">**X DO NOT** 使用"标志"或"标志"后缀枚举中的键入名称。</span><span class="sxs-lookup"><span data-stu-id="afdb9-148">**X DO NOT** use "Flag" or "Flags" suffixes in enum type names.</span></span>  
  
 <span data-ttu-id="afdb9-149">**X DO NOT** 针对多格式文本枚举等使用枚举值名称 (例如，"ad"对 ADO 枚举。)、"rtf"上的前缀。</span><span class="sxs-lookup"><span data-stu-id="afdb9-149">**X DO NOT** use a prefix on enumeration value names (e.g., "ad" for ADO enums, "rtf" for rich text enums, etc.).</span></span>  
  
 <span data-ttu-id="afdb9-150">*部分 © 2005年，2009 Microsoft Corporation。保留所有权利。*</span><span class="sxs-lookup"><span data-stu-id="afdb9-150">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="afdb9-151">*通过从皮尔逊教育版，Inc.的权限重新打印[Framework 设计准则： 约定、 语法和可重用.NET 库，版本 2 的模式](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619)通过 Krzysztof Cwalina 和 Brad Abrams，发布 2008 年 10 月 22，通过Microsoft Windows 开发系列的一部分的 Addison Wesley Professional。*</span><span class="sxs-lookup"><span data-stu-id="afdb9-151">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="afdb9-152">请参阅</span><span class="sxs-lookup"><span data-stu-id="afdb9-152">See Also</span></span>  
 [<span data-ttu-id="afdb9-153">框架设计指南</span><span class="sxs-lookup"><span data-stu-id="afdb9-153">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)  
 [<span data-ttu-id="afdb9-154">命名规则</span><span class="sxs-lookup"><span data-stu-id="afdb9-154">Naming Guidelines</span></span>](../../../docs/standard/design-guidelines/naming-guidelines.md)
