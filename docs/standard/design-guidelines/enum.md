---
title: 枚举设计
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- type design guidelines, enumerations
- simple enumerations
- enumerations [.NET Framework], design guidelines
- class library design guidelines [.NET Framework], enumerations
- flags enumerations
ms.assetid: dd53c952-9d9a-4736-86ff-9540e815d545
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9dea187b5f3911114e551d640e0bb0aa6fac1143
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/06/2018
ms.locfileid: "43891228"
---
# <a name="enum-design"></a><span data-ttu-id="299e0-102">枚举设计</span><span class="sxs-lookup"><span data-stu-id="299e0-102">Enum Design</span></span>
<span data-ttu-id="299e0-103">枚举都是一种特殊的值类型。</span><span class="sxs-lookup"><span data-stu-id="299e0-103">Enums are a special kind of value type.</span></span> <span data-ttu-id="299e0-104">有两种类型的枚举： 简单枚举和标志枚举。</span><span class="sxs-lookup"><span data-stu-id="299e0-104">There are two kinds of enums: simple enums and flag enums.</span></span>  
  
 <span data-ttu-id="299e0-105">简单枚举表示小闭的集的选择。</span><span class="sxs-lookup"><span data-stu-id="299e0-105">Simple enums represent small closed sets of choices.</span></span> <span data-ttu-id="299e0-106">简单枚举的一个常见示例是一组颜色。</span><span class="sxs-lookup"><span data-stu-id="299e0-106">A common example of the simple enum is a set of colors.</span></span>  
  
 <span data-ttu-id="299e0-107">标志枚举可以支持的枚举值的按位运算。</span><span class="sxs-lookup"><span data-stu-id="299e0-107">Flag enums are designed to support bitwise operations on the enum values.</span></span> <span data-ttu-id="299e0-108">标志枚举的一个常见示例是一系列选项。</span><span class="sxs-lookup"><span data-stu-id="299e0-108">A common example of the flags enum is a list of options.</span></span>  
  
 <span data-ttu-id="299e0-109">**✓ DO** 枚举用于强类型参数、 属性，并返回表示的值的集的值。</span><span class="sxs-lookup"><span data-stu-id="299e0-109">**✓ DO** use an enum to strongly type parameters, properties, and return values that represent sets of values.</span></span>  
  
 <span data-ttu-id="299e0-110">**✓ DO** 倾向于使用而不静态常量的枚举。</span><span class="sxs-lookup"><span data-stu-id="299e0-110">**✓ DO** favor using an enum instead of static constants.</span></span>  
  
 <span data-ttu-id="299e0-111">**X DO NOT** 枚举用于打开集 （如操作系统版本、 名称的友元，等等。）。</span><span class="sxs-lookup"><span data-stu-id="299e0-111">**X DO NOT** use an enum for open sets (such as the operating system version, names of your friends, etc.).</span></span>  
  
 <span data-ttu-id="299e0-112">**X DO NOT** 提供应保留的枚举值供将来使用。</span><span class="sxs-lookup"><span data-stu-id="299e0-112">**X DO NOT** provide reserved enum values that are intended for future use.</span></span>  
  
 <span data-ttu-id="299e0-113">在后面的阶段始终只需向现有的枚举添加值。</span><span class="sxs-lookup"><span data-stu-id="299e0-113">You can always simply add values to the existing enum at a later stage.</span></span> <span data-ttu-id="299e0-114">请参阅[添加到枚举的值](#add_value)有关的详细信息添加到枚举的值。</span><span class="sxs-lookup"><span data-stu-id="299e0-114">See [Adding Values to Enums](#add_value) for more details on adding values to enums.</span></span> <span data-ttu-id="299e0-115">只需保留的值污染的实际值集，并往往会导致用户错误。</span><span class="sxs-lookup"><span data-stu-id="299e0-115">Reserved values just pollute the set of real values and tend to lead to user errors.</span></span>  
  
 <span data-ttu-id="299e0-116">**X AVOID** 公开使用只有一个值的枚举。</span><span class="sxs-lookup"><span data-stu-id="299e0-116">**X AVOID** publicly exposing enums with only one value.</span></span>  
  
 <span data-ttu-id="299e0-117">确保将来扩展的 C Api 的常见做法是将保留的参数添加到方法签名。</span><span class="sxs-lookup"><span data-stu-id="299e0-117">A common practice for ensuring future extensibility of C APIs is to add reserved parameters to method signatures.</span></span> <span data-ttu-id="299e0-118">此类保留的参数可以表示为具有一个默认值的枚举。</span><span class="sxs-lookup"><span data-stu-id="299e0-118">Such reserved parameters can be expressed as enums with a single default value.</span></span> <span data-ttu-id="299e0-119">这不应托管的 Api 中完成。</span><span class="sxs-lookup"><span data-stu-id="299e0-119">This should not be done in managed APIs.</span></span> <span data-ttu-id="299e0-120">方法重载允许添加参数在将来的版本。</span><span class="sxs-lookup"><span data-stu-id="299e0-120">Method overloading allows adding parameters in future releases.</span></span>  
  
 <span data-ttu-id="299e0-121">**X DO NOT** 在枚举中包括 sentinel 值。</span><span class="sxs-lookup"><span data-stu-id="299e0-121">**X DO NOT** include sentinel values in enums.</span></span>  
  
 <span data-ttu-id="299e0-122">尽管它们是有时对 framework 开发人员有帮助，sentinel 值是给 framework 的用户造成混淆。</span><span class="sxs-lookup"><span data-stu-id="299e0-122">Although they are sometimes helpful to framework developers, sentinel values are confusing to users of the framework.</span></span> <span data-ttu-id="299e0-123">它们用于从表示枚举集跟踪枚举而不是一个值的状态。</span><span class="sxs-lookup"><span data-stu-id="299e0-123">They are used to track the state of the enum rather than being one of the values from the set represented by the enum.</span></span>  
  
 <span data-ttu-id="299e0-124">**✓ DO** 提供简单枚举零的值。</span><span class="sxs-lookup"><span data-stu-id="299e0-124">**✓ DO** provide a value of zero on simple enums.</span></span>  
  
 <span data-ttu-id="299e0-125">请考虑调用值类似于"None。</span><span class="sxs-lookup"><span data-stu-id="299e0-125">Consider calling the value something like "None."</span></span> <span data-ttu-id="299e0-126">如果此类值不适合于此特定枚举，则应基础值零分配的最常见的默认值为枚举。</span><span class="sxs-lookup"><span data-stu-id="299e0-126">If such a value is not appropriate for this particular enum, the most common default value for the enum should be assigned the underlying value of zero.</span></span>  
  
 <span data-ttu-id="299e0-127">**✓ CONSIDER** 使用<xref:System.Int32>（默认值在大多数编程语言） 作为枚举的基础类型除非以下任一条件成立：</span><span class="sxs-lookup"><span data-stu-id="299e0-127">**✓ CONSIDER** using <xref:System.Int32> (the default in most programming languages) as the underlying type of an enum unless any of the following is true:</span></span>  
  
-   <span data-ttu-id="299e0-128">枚举是标志枚举，包含 32 个以上的标志，或希望在将来的详细信息。</span><span class="sxs-lookup"><span data-stu-id="299e0-128">The enum is a flags enum and you have more than 32 flags, or expect to have more in the future.</span></span>  
  
-   <span data-ttu-id="299e0-129">基础类型必须是不同于<xref:System.Int32>更轻松互操作性与非托管代码应为不同大小的枚举。</span><span class="sxs-lookup"><span data-stu-id="299e0-129">The underlying type needs to be different than <xref:System.Int32> for easier interoperability with unmanaged code expecting different-size enums.</span></span>  
  
-   <span data-ttu-id="299e0-130">小的基础类型将导致节省大量空间。</span><span class="sxs-lookup"><span data-stu-id="299e0-130">A smaller underlying type would result in substantial savings in space.</span></span> <span data-ttu-id="299e0-131">如果希望将枚举主要用作有关控制流的参数，则大小就不太重要。</span><span class="sxs-lookup"><span data-stu-id="299e0-131">If you expect the enum to be used mainly as an argument for flow of control, the size makes little difference.</span></span> <span data-ttu-id="299e0-132">节省的大小可能会很明显如果：</span><span class="sxs-lookup"><span data-stu-id="299e0-132">The size savings might be significant if:</span></span>  
  
    -   <span data-ttu-id="299e0-133">您将发现要用作非常频繁地实例化的结构或类中的字段的枚举。</span><span class="sxs-lookup"><span data-stu-id="299e0-133">You expect the enum to be used as a field in a very frequently instantiated structure or class.</span></span>  
  
    -   <span data-ttu-id="299e0-134">你希望用户用户创建大型数组或集合的枚举实例。</span><span class="sxs-lookup"><span data-stu-id="299e0-134">You expect users to create large arrays or collections of the enum instances.</span></span>  
  
    -   <span data-ttu-id="299e0-135">您将发现大量枚举要序列化的实例。</span><span class="sxs-lookup"><span data-stu-id="299e0-135">You expect a large number of instances of the enum to be serialized.</span></span>  
  
 <span data-ttu-id="299e0-136">对于内存中使用情况，请注意的托管的对象始终是`DWORD`-对齐，因此您有效地需要多个枚举或实例因为实例总计大小始终是为了使差异，打包具有较小枚举中的其他小结构要四舍五入为`DWORD`。</span><span class="sxs-lookup"><span data-stu-id="299e0-136">For in-memory usage, be aware that managed objects are always `DWORD`-aligned, so you effectively need multiple enums or other small structures in an instance to pack a smaller enum with in order to make a difference, because the total instance size is always going to be rounded up to a `DWORD`.</span></span>  
  
 <span data-ttu-id="299e0-137">**✓ DO** 命名为复数名词或名词短语的标志枚举和简单枚举用单数形式的名词或名词短语。</span><span class="sxs-lookup"><span data-stu-id="299e0-137">**✓ DO** name flag enums with plural nouns or noun phrases and simple enums with singular nouns or noun phrases.</span></span>  
  
 <span data-ttu-id="299e0-138">**X DO NOT** 扩展<xref:System.Enum?displayProperty=nameWithType>直接。</span><span class="sxs-lookup"><span data-stu-id="299e0-138">**X DO NOT** extend <xref:System.Enum?displayProperty=nameWithType> directly.</span></span>  
  
 <span data-ttu-id="299e0-139"><xref:System.Enum?displayProperty=nameWithType> 是一种特殊类型用于由 CLR 创建用户定义的枚举。</span><span class="sxs-lookup"><span data-stu-id="299e0-139"><xref:System.Enum?displayProperty=nameWithType> is a special type used by the CLR to create user-defined enumerations.</span></span> <span data-ttu-id="299e0-140">大多数编程语言提供此功能可让你访问的编程元素。</span><span class="sxs-lookup"><span data-stu-id="299e0-140">Most programming languages provide a programming element that gives you access to this functionality.</span></span> <span data-ttu-id="299e0-141">例如，在 C#`enum`关键字用于定义的枚举。</span><span class="sxs-lookup"><span data-stu-id="299e0-141">For example, in C# the `enum` keyword is used to define an enumeration.</span></span>  
  
<a name="design"></a>   
### <a name="designing-flag-enums"></a><span data-ttu-id="299e0-142">设计标志枚举</span><span class="sxs-lookup"><span data-stu-id="299e0-142">Designing Flag Enums</span></span>  
 <span data-ttu-id="299e0-143">**✓ DO** 应用<xref:System.FlagsAttribute?displayProperty=nameWithType>到标志枚举。</span><span class="sxs-lookup"><span data-stu-id="299e0-143">**✓ DO** apply the <xref:System.FlagsAttribute?displayProperty=nameWithType> to flag enums.</span></span> <span data-ttu-id="299e0-144">不将此特性应用于简单枚举。</span><span class="sxs-lookup"><span data-stu-id="299e0-144">Do not apply this attribute to simple enums.</span></span>  
  
 <span data-ttu-id="299e0-145">**✓ DO** 使用幂的两个用于标志枚举值，因此它们可以自由地组合使用按位或运算。</span><span class="sxs-lookup"><span data-stu-id="299e0-145">**✓ DO** use powers of two for the flag enum values so they can be freely combined using the bitwise OR operation.</span></span>  
  
 <span data-ttu-id="299e0-146">**✓ CONSIDER** 通常提供特殊的枚举值使用标志的组合。</span><span class="sxs-lookup"><span data-stu-id="299e0-146">**✓ CONSIDER** providing special enum values for commonly used combinations of flags.</span></span>  
  
 <span data-ttu-id="299e0-147">按位操作是一种高级的概念，并且不应要求对简单的任务。</span><span class="sxs-lookup"><span data-stu-id="299e0-147">Bitwise operations are an advanced concept and should not be required for simple tasks.</span></span> <span data-ttu-id="299e0-148"><xref:System.IO.FileAccess.ReadWrite> 是这样的特殊值的示例。</span><span class="sxs-lookup"><span data-stu-id="299e0-148"><xref:System.IO.FileAccess.ReadWrite> is an example of such a special value.</span></span>  
  
 <span data-ttu-id="299e0-149">**X AVOID** 创建标志枚举值的某些组合将无效。</span><span class="sxs-lookup"><span data-stu-id="299e0-149">**X AVOID** creating flag enums where certain combinations of values are invalid.</span></span>  
  
 <span data-ttu-id="299e0-150">**X AVOID** 使用标志为零的枚举值，除非值表示"清除所有标志"，并且相应地下, 一项准则中规定名为。</span><span class="sxs-lookup"><span data-stu-id="299e0-150">**X AVOID** using flag enum values of zero unless the value represents "all flags are cleared" and is named appropriately, as prescribed by the next guideline.</span></span>  
  
 <span data-ttu-id="299e0-151">**✓ DO** 命名的零值的标志枚举`None`。</span><span class="sxs-lookup"><span data-stu-id="299e0-151">**✓ DO** name the zero value of flag enums `None`.</span></span> <span data-ttu-id="299e0-152">对于标志枚举值必须并始终意味着"清除所有标志。"</span><span class="sxs-lookup"><span data-stu-id="299e0-152">For a flag enum, the value must always mean "all flags are cleared."</span></span>  
  
<a name="add_value"></a>   
### <a name="adding-value-to-enums"></a><span data-ttu-id="299e0-153">将值添加到枚举</span><span class="sxs-lookup"><span data-stu-id="299e0-153">Adding Value to Enums</span></span>  
 <span data-ttu-id="299e0-154">它是很常见，来发现您需要将值添加到枚举后对已发布它。</span><span class="sxs-lookup"><span data-stu-id="299e0-154">It is very common to discover that you need to add values to an enum after you have already shipped it.</span></span> <span data-ttu-id="299e0-155">没有潜在的应用程序兼容性问题时新添加的值返回从现有的 API，因为编写不佳的应用程序可能不会正确处理的新值。</span><span class="sxs-lookup"><span data-stu-id="299e0-155">There is a potential application compatibility problem when the newly added value is returned from an existing API, because poorly written applications might not handle the new value correctly.</span></span>  
  
 <span data-ttu-id="299e0-156">**✓ CONSIDER** 将值添加到枚举，尽管小兼容性风险。</span><span class="sxs-lookup"><span data-stu-id="299e0-156">**✓ CONSIDER** adding values to enums, despite a small compatibility risk.</span></span>  
  
 <span data-ttu-id="299e0-157">如果已将有关应用程序不兼容问题引起的新增功能的枚举的实际数据，请考虑添加一个新 API，则返回新的和旧值，并弃用旧的 API，应继续返回旧的值。</span><span class="sxs-lookup"><span data-stu-id="299e0-157">If you have real data about application incompatibilities caused by additions to an enum, consider adding a new API that returns the new and old values, and deprecate the old API, which should continue returning just the old values.</span></span> <span data-ttu-id="299e0-158">这将确保现有的应用程序保持兼容。</span><span class="sxs-lookup"><span data-stu-id="299e0-158">This will ensure that your existing applications remain compatible.</span></span>  
  
 <span data-ttu-id="299e0-159">*部分版权 © 2005, 2009 Microsoft Corporation。保留所有权利。*</span><span class="sxs-lookup"><span data-stu-id="299e0-159">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="299e0-160">*经 Pearson Education, Inc 授权，转载自[框架设计准则：可重用的 .NET 库的约定、习惯用语和模式，第2版](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) 作者：Krzysztof Cwalina 和 Brad Abrams，由 Addison Wesley Professional 于 2008 年 10 月 22 日印发，作为 Microsoft Windows 开发系列的一部分。*</span><span class="sxs-lookup"><span data-stu-id="299e0-160">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="299e0-161">请参阅</span><span class="sxs-lookup"><span data-stu-id="299e0-161">See also</span></span>

- [<span data-ttu-id="299e0-162">类型设计准则</span><span class="sxs-lookup"><span data-stu-id="299e0-162">Type Design Guidelines</span></span>](../../../docs/standard/design-guidelines/type.md)  
- [<span data-ttu-id="299e0-163">框架设计指南</span><span class="sxs-lookup"><span data-stu-id="299e0-163">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
