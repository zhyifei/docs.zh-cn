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
ms.openlocfilehash: 544f617ca3a352814504125d7a61d70db5a81566
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="enum-design"></a><span data-ttu-id="a6650-102">枚举设计</span><span class="sxs-lookup"><span data-stu-id="a6650-102">Enum Design</span></span>
<span data-ttu-id="a6650-103">枚举是特殊类型的值类型。</span><span class="sxs-lookup"><span data-stu-id="a6650-103">Enums are a special kind of value type.</span></span> <span data-ttu-id="a6650-104">有两种枚举： 简单枚举和标志枚举。</span><span class="sxs-lookup"><span data-stu-id="a6650-104">There are two kinds of enums: simple enums and flag enums.</span></span>  
  
 <span data-ttu-id="a6650-105">简单枚举表示小闭的集的选择。</span><span class="sxs-lookup"><span data-stu-id="a6650-105">Simple enums represent small closed sets of choices.</span></span> <span data-ttu-id="a6650-106">简单枚举的一个常见示例是一组的颜色。</span><span class="sxs-lookup"><span data-stu-id="a6650-106">A common example of the simple enum is a set of colors.</span></span>  
  
 <span data-ttu-id="a6650-107">标志枚举旨在支持的枚举值的按位运算。</span><span class="sxs-lookup"><span data-stu-id="a6650-107">Flag enums are designed to support bitwise operations on the enum values.</span></span> <span data-ttu-id="a6650-108">标志枚举的一个常见示例是选项的列表。</span><span class="sxs-lookup"><span data-stu-id="a6650-108">A common example of the flags enum is a list of options.</span></span>  
  
 <span data-ttu-id="a6650-109">**✓ 执行**枚举用于强类型参数、 属性，并返回表示的值的集的值。</span><span class="sxs-lookup"><span data-stu-id="a6650-109">**✓ DO** use an enum to strongly type parameters, properties, and return values that represent sets of values.</span></span>  
  
 <span data-ttu-id="a6650-110">**✓ 执行**倾向于使用而不静态常量的枚举。</span><span class="sxs-lookup"><span data-stu-id="a6650-110">**✓ DO** favor using an enum instead of static constants.</span></span>  
  
 <span data-ttu-id="a6650-111">**X 不**枚举用于打开集 （如操作系统版本、 名称的友元，等等。）。</span><span class="sxs-lookup"><span data-stu-id="a6650-111">**X DO NOT** use an enum for open sets (such as the operating system version, names of your friends, etc.).</span></span>  
  
 <span data-ttu-id="a6650-112">**X 不**提供应保留的枚举值供将来使用。</span><span class="sxs-lookup"><span data-stu-id="a6650-112">**X DO NOT** provide reserved enum values that are intended for future use.</span></span>  
  
 <span data-ttu-id="a6650-113">你在以后的阶段始终只需向现有的枚举添加值。</span><span class="sxs-lookup"><span data-stu-id="a6650-113">You can always simply add values to the existing enum at a later stage.</span></span> <span data-ttu-id="a6650-114">请参阅[将值添加到枚举](#add_value)有关将值添加到枚举的详细信息。</span><span class="sxs-lookup"><span data-stu-id="a6650-114">See [Adding Values to Enums](#add_value) for more details on adding values to enums.</span></span> <span data-ttu-id="a6650-115">只需保留的值会污染的实际值集，并往往会导致用户错误。</span><span class="sxs-lookup"><span data-stu-id="a6650-115">Reserved values just pollute the set of real values and tend to lead to user errors.</span></span>  
  
 <span data-ttu-id="a6650-116">**请避免 x**公开使用只有一个值的枚举。</span><span class="sxs-lookup"><span data-stu-id="a6650-116">**X AVOID** publicly exposing enums with only one value.</span></span>  
  
 <span data-ttu-id="a6650-117">确保将来扩展的 C Api 的常见做法是将保留的参数添加到方法签名。</span><span class="sxs-lookup"><span data-stu-id="a6650-117">A common practice for ensuring future extensibility of C APIs is to add reserved parameters to method signatures.</span></span> <span data-ttu-id="a6650-118">此类保留的参数可以表示为具有一个默认值的枚举。</span><span class="sxs-lookup"><span data-stu-id="a6650-118">Such reserved parameters can be expressed as enums with a single default value.</span></span> <span data-ttu-id="a6650-119">这不应该在托管 Api 来完成。</span><span class="sxs-lookup"><span data-stu-id="a6650-119">This should not be done in managed APIs.</span></span> <span data-ttu-id="a6650-120">方法重载允许添加参数以后的版本。</span><span class="sxs-lookup"><span data-stu-id="a6650-120">Method overloading allows adding parameters in future releases.</span></span>  
  
 <span data-ttu-id="a6650-121">**X 不**在枚举中包括 sentinel 值。</span><span class="sxs-lookup"><span data-stu-id="a6650-121">**X DO NOT** include sentinel values in enums.</span></span>  
  
 <span data-ttu-id="a6650-122">尽管它们有时 framework 开发人员很有帮助，sentinel 值是给的 framework 的用户造成混淆。</span><span class="sxs-lookup"><span data-stu-id="a6650-122">Although they are sometimes helpful to framework developers, sentinel values are confusing to users of the framework.</span></span> <span data-ttu-id="a6650-123">它们用于从枚举所表示的集中跟踪枚举而不是正在值之一的状态。</span><span class="sxs-lookup"><span data-stu-id="a6650-123">They are used to track the state of the enum rather than being one of the values from the set represented by the enum.</span></span>  
  
 <span data-ttu-id="a6650-124">**✓ 执行**提供简单枚举零的值。</span><span class="sxs-lookup"><span data-stu-id="a6650-124">**✓ DO** provide a value of zero on simple enums.</span></span>  
  
 <span data-ttu-id="a6650-125">请考虑调用值类似于"None。</span><span class="sxs-lookup"><span data-stu-id="a6650-125">Consider calling the value something like "None."</span></span> <span data-ttu-id="a6650-126">如果这样的值不适合于此特定枚举，则应基础值零的分配的最常见的默认值为枚举。</span><span class="sxs-lookup"><span data-stu-id="a6650-126">If such a value is not appropriate for this particular enum, the most common default value for the enum should be assigned the underlying value of zero.</span></span>  
  
 <span data-ttu-id="a6650-127">**请考虑 ✓**使用<xref:System.Int32>（默认值在大多数编程语言） 作为枚举的基础类型除非以下任一条件成立：</span><span class="sxs-lookup"><span data-stu-id="a6650-127">**✓ CONSIDER** using <xref:System.Int32> (the default in most programming languages) as the underlying type of an enum unless any of the following is true:</span></span>  
  
-   <span data-ttu-id="a6650-128">枚举是标志枚举，您有 32 个以上的标志，或者希望有在将来的详细信息。</span><span class="sxs-lookup"><span data-stu-id="a6650-128">The enum is a flags enum and you have more than 32 flags, or expect to have more in the future.</span></span>  
  
-   <span data-ttu-id="a6650-129">基础类型必须是不同于<xref:System.Int32>更容易与预期不同大小的枚举的非托管代码的互操作性。</span><span class="sxs-lookup"><span data-stu-id="a6650-129">The underlying type needs to be different than <xref:System.Int32> for easier interoperability with unmanaged code expecting different-size enums.</span></span>  
  
-   <span data-ttu-id="a6650-130">小的基础类型将导致节省大量空间。</span><span class="sxs-lookup"><span data-stu-id="a6650-130">A smaller underlying type would result in substantial savings in space.</span></span> <span data-ttu-id="a6650-131">如果您希望主要用作有关控制流的参数将枚举，大小就不太重要。</span><span class="sxs-lookup"><span data-stu-id="a6650-131">If you expect the enum to be used mainly as an argument for flow of control, the size makes little difference.</span></span> <span data-ttu-id="a6650-132">节省的大小可能会很明显如果：</span><span class="sxs-lookup"><span data-stu-id="a6650-132">The size savings might be significant if:</span></span>  
  
    -   <span data-ttu-id="a6650-133">你预计将枚举用作非常频繁地实例化的结构或类中的字段。</span><span class="sxs-lookup"><span data-stu-id="a6650-133">You expect the enum to be used as a field in a very frequently instantiated structure or class.</span></span>  
  
    -   <span data-ttu-id="a6650-134">指望用户能创建大型数组或集合的枚举实例。</span><span class="sxs-lookup"><span data-stu-id="a6650-134">You expect users to create large arrays or collections of the enum instances.</span></span>  
  
    -   <span data-ttu-id="a6650-135">你预计大量枚举要序列化的实例。</span><span class="sxs-lookup"><span data-stu-id="a6650-135">You expect a large number of instances of the enum to be serialized.</span></span>  
  
 <span data-ttu-id="a6650-136">对于内存中的用法，请注意的托管的对象始终是`DWORD`-对齐，因此你有效地需要多个枚举中的或其他小结构一个实例，以便因为总实例大小始终会起作用，以便包较小枚举将会向上舍入到`DWORD`。</span><span class="sxs-lookup"><span data-stu-id="a6650-136">For in-memory usage, be aware that managed objects are always `DWORD`-aligned, so you effectively need multiple enums or other small structures in an instance to pack a smaller enum with in order to make a difference, because the total instance size is always going to be rounded up to a `DWORD`.</span></span>  
  
 <span data-ttu-id="a6650-137">**✓ 执行**命名为复数名词或名词短语的标志枚举和简单枚举用单数形式的名词或名词短语。</span><span class="sxs-lookup"><span data-stu-id="a6650-137">**✓ DO** name flag enums with plural nouns or noun phrases and simple enums with singular nouns or noun phrases.</span></span>  
  
 <span data-ttu-id="a6650-138">**X 不**扩展<xref:System.Enum?displayProperty=nameWithType>直接。</span><span class="sxs-lookup"><span data-stu-id="a6650-138">**X DO NOT** extend <xref:System.Enum?displayProperty=nameWithType> directly.</span></span>  
  
 <span data-ttu-id="a6650-139"><xref:System.Enum?displayProperty=nameWithType> 是一种特殊类型使用由 CLR 创建用户定义的枚举。</span><span class="sxs-lookup"><span data-stu-id="a6650-139"><xref:System.Enum?displayProperty=nameWithType> is a special type used by the CLR to create user-defined enumerations.</span></span> <span data-ttu-id="a6650-140">大多数编程语言提供与此功能使你可以访问的编程元素。</span><span class="sxs-lookup"><span data-stu-id="a6650-140">Most programming languages provide a programming element that gives you access to this functionality.</span></span> <span data-ttu-id="a6650-141">例如，在 C#`enum`关键字用于定义枚举。</span><span class="sxs-lookup"><span data-stu-id="a6650-141">For example, in C# the `enum` keyword is used to define an enumeration.</span></span>  
  
<a name="design"></a>   
### <a name="designing-flag-enums"></a><span data-ttu-id="a6650-142">设计标志枚举</span><span class="sxs-lookup"><span data-stu-id="a6650-142">Designing Flag Enums</span></span>  
 <span data-ttu-id="a6650-143">**✓ 执行**应用<xref:System.FlagsAttribute?displayProperty=nameWithType>到标志枚举。</span><span class="sxs-lookup"><span data-stu-id="a6650-143">**✓ DO** apply the <xref:System.FlagsAttribute?displayProperty=nameWithType> to flag enums.</span></span> <span data-ttu-id="a6650-144">不将此特性应用于简单枚举。</span><span class="sxs-lookup"><span data-stu-id="a6650-144">Do not apply this attribute to simple enums.</span></span>  
  
 <span data-ttu-id="a6650-145">**✓ 执行**使用幂的两个用于标志枚举值，因此它们可以自由地组合使用按位或运算。</span><span class="sxs-lookup"><span data-stu-id="a6650-145">**✓ DO** use powers of two for the flag enum values so they can be freely combined using the bitwise OR operation.</span></span>  
  
 <span data-ttu-id="a6650-146">**请考虑 ✓**通常提供特殊的枚举值使用标志的组合。</span><span class="sxs-lookup"><span data-stu-id="a6650-146">**✓ CONSIDER** providing special enum values for commonly used combinations of flags.</span></span>  
  
 <span data-ttu-id="a6650-147">按位运算是一个高级的概念，应该不需要用于简单任务。</span><span class="sxs-lookup"><span data-stu-id="a6650-147">Bitwise operations are an advanced concept and should not be required for simple tasks.</span></span> <span data-ttu-id="a6650-148"><xref:System.IO.FileAccess.ReadWrite> 是一个示例这样的特殊值。</span><span class="sxs-lookup"><span data-stu-id="a6650-148"><xref:System.IO.FileAccess.ReadWrite> is an example of such a special value.</span></span>  
  
 <span data-ttu-id="a6650-149">**请避免 x**创建标志枚举值的某些组合将无效。</span><span class="sxs-lookup"><span data-stu-id="a6650-149">**X AVOID** creating flag enums where certain combinations of values are invalid.</span></span>  
  
 <span data-ttu-id="a6650-150">**请避免 x**使用标志为零的枚举值，除非值表示"清除所有标志"，并且相应地下, 一项准则中规定名为。</span><span class="sxs-lookup"><span data-stu-id="a6650-150">**X AVOID** using flag enum values of zero unless the value represents "all flags are cleared" and is named appropriately, as prescribed by the next guideline.</span></span>  
  
 <span data-ttu-id="a6650-151">**✓ 执行**命名的零值的标志枚举`None`。</span><span class="sxs-lookup"><span data-stu-id="a6650-151">**✓ DO** name the zero value of flag enums `None`.</span></span> <span data-ttu-id="a6650-152">对于标志枚举，该值必须并始终表示"清除所有标志。"</span><span class="sxs-lookup"><span data-stu-id="a6650-152">For a flag enum, the value must always mean "all flags are cleared."</span></span>  
  
<a name="add_value"></a>   
### <a name="adding-value-to-enums"></a><span data-ttu-id="a6650-153">将值添加到枚举</span><span class="sxs-lookup"><span data-stu-id="a6650-153">Adding Value to Enums</span></span>  
 <span data-ttu-id="a6650-154">它是很常见，来发现你需要将值添加到枚举中，已发送了它后。</span><span class="sxs-lookup"><span data-stu-id="a6650-154">It is very common to discover that you need to add values to an enum after you have already shipped it.</span></span> <span data-ttu-id="a6650-155">时出现的潜在应用程序兼容性问题新添加的值返回从现有的 API，因为编写不佳的应用程序可能不会正确处理的新值。</span><span class="sxs-lookup"><span data-stu-id="a6650-155">There is a potential application compatibility problem when the newly added value is returned from an existing API, because poorly written applications might not handle the new value correctly.</span></span>  
  
 <span data-ttu-id="a6650-156">**请考虑 ✓**将值添加到枚举，尽管小兼容性风险。</span><span class="sxs-lookup"><span data-stu-id="a6650-156">**✓ CONSIDER** adding values to enums, despite a small compatibility risk.</span></span>  
  
 <span data-ttu-id="a6650-157">如果你具有有关应用程序不兼容问题引起向枚举添加内容的真实数据，请考虑将添加一个新 API，返回新值和旧值，并且否决旧 API，这应继续返回只是这些旧值。</span><span class="sxs-lookup"><span data-stu-id="a6650-157">If you have real data about application incompatibilities caused by additions to an enum, consider adding a new API that returns the new and old values, and deprecate the old API, which should continue returning just the old values.</span></span> <span data-ttu-id="a6650-158">这将确保你现有的应用程序仍保持兼容。</span><span class="sxs-lookup"><span data-stu-id="a6650-158">This will ensure that your existing applications remain compatible.</span></span>  
  
 <span data-ttu-id="a6650-159">*部分 © 2005年，2009 Microsoft Corporation。保留所有权利。*</span><span class="sxs-lookup"><span data-stu-id="a6650-159">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="a6650-160">*通过从皮尔逊教育版，Inc.的权限重新打印[Framework 设计准则： 约定、 语法和可重用.NET 库，版本 2 的模式](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619)通过 Krzysztof Cwalina 和 Brad Abrams，发布 2008 年 10 月 22，通过Microsoft Windows 开发系列的一部分的 Addison Wesley Professional。*</span><span class="sxs-lookup"><span data-stu-id="a6650-160">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a6650-161">请参阅</span><span class="sxs-lookup"><span data-stu-id="a6650-161">See Also</span></span>  
 [<span data-ttu-id="a6650-162">类型设计准则</span><span class="sxs-lookup"><span data-stu-id="a6650-162">Type Design Guidelines</span></span>](../../../docs/standard/design-guidelines/type.md)  
 [<span data-ttu-id="a6650-163">框架设计指南</span><span class="sxs-lookup"><span data-stu-id="a6650-163">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
