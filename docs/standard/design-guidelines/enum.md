---
title: 枚举设计
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- type design guidelines, enumerations
- simple enumerations
- enumerations [.NET Framework], design guidelines
- class library design guidelines [.NET Framework], enumerations
- flags enumerations
ms.assetid: dd53c952-9d9a-4736-86ff-9540e815d545
author: KrzysztofCwalina
ms.openlocfilehash: c0645ba1179c4c6fd961b871b3061cd51174f427
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61669090"
---
# <a name="enum-design"></a><span data-ttu-id="931ee-102">枚举设计</span><span class="sxs-lookup"><span data-stu-id="931ee-102">Enum Design</span></span>
<span data-ttu-id="931ee-103">枚举是一种特殊的值类型。</span><span class="sxs-lookup"><span data-stu-id="931ee-103">Enums are a special kind of value type.</span></span> <span data-ttu-id="931ee-104">枚举分为两种类型：简单枚举和标志枚举。</span><span class="sxs-lookup"><span data-stu-id="931ee-104">There are two kinds of enums: simple enums and flag enums.</span></span>  
  
 <span data-ttu-id="931ee-105">简单枚举表示小型的封闭选项集。</span><span class="sxs-lookup"><span data-stu-id="931ee-105">Simple enums represent small closed sets of choices.</span></span> <span data-ttu-id="931ee-106">简单枚举的一个常见示例是一组颜色。</span><span class="sxs-lookup"><span data-stu-id="931ee-106">A common example of the simple enum is a set of colors.</span></span>  
  
 <span data-ttu-id="931ee-107">标志枚举旨在支持枚举值的按位运算。</span><span class="sxs-lookup"><span data-stu-id="931ee-107">Flag enums are designed to support bitwise operations on the enum values.</span></span> <span data-ttu-id="931ee-108">标志枚举的一个常见示例是选项列表。</span><span class="sxs-lookup"><span data-stu-id="931ee-108">A common example of the flags enum is a list of options.</span></span>  
  
 <span data-ttu-id="931ee-109">✓ 务必将枚举用于强类型参数、属性和表示一组值集的返回值。</span><span class="sxs-lookup"><span data-stu-id="931ee-109">**✓ DO** use an enum to strongly type parameters, properties, and return values that represent sets of values.</span></span>  
  
 <span data-ttu-id="931ee-110">✓ 务必首选使用枚举而不是静态常量。</span><span class="sxs-lookup"><span data-stu-id="931ee-110">**✓ DO** favor using an enum instead of static constants.</span></span>  
  
 <span data-ttu-id="931ee-111">X 切忌将枚举用于开放集（如操作系统版本、朋友的姓名等）。</span><span class="sxs-lookup"><span data-stu-id="931ee-111">**X DO NOT** use an enum for open sets (such as the operating system version, names of your friends, etc.).</span></span>  
  
 <span data-ttu-id="931ee-112">X 切忌提供供将来使用的保留枚举值。</span><span class="sxs-lookup"><span data-stu-id="931ee-112">**X DO NOT** provide reserved enum values that are intended for future use.</span></span>  
  
 <span data-ttu-id="931ee-113">在后面的阶段，可以随时向现有枚举添加值。</span><span class="sxs-lookup"><span data-stu-id="931ee-113">You can always simply add values to the existing enum at a later stage.</span></span> <span data-ttu-id="931ee-114">有关向枚举添加值的更多详细信息，请参阅[向枚举添加值](#add_value)。</span><span class="sxs-lookup"><span data-stu-id="931ee-114">See [Adding Values to Enums](#add_value) for more details on adding values to enums.</span></span> <span data-ttu-id="931ee-115">保留值只会污染实际的值集，并往往会导致用户错误。</span><span class="sxs-lookup"><span data-stu-id="931ee-115">Reserved values just pollute the set of real values and tend to lead to user errors.</span></span>  
  
 <span data-ttu-id="931ee-116">X 避免公开暴露只有一个值的枚举。</span><span class="sxs-lookup"><span data-stu-id="931ee-116">**X AVOID** publicly exposing enums with only one value.</span></span>  
  
 <span data-ttu-id="931ee-117">确保 C API 未来可扩展性的常见做法是向方法签名添加保留参数。</span><span class="sxs-lookup"><span data-stu-id="931ee-117">A common practice for ensuring future extensibility of C APIs is to add reserved parameters to method signatures.</span></span> <span data-ttu-id="931ee-118">这样的保留参数可以表示为具有单个默认值的枚举。</span><span class="sxs-lookup"><span data-stu-id="931ee-118">Such reserved parameters can be expressed as enums with a single default value.</span></span> <span data-ttu-id="931ee-119">这不应该在托管 API 中完成。</span><span class="sxs-lookup"><span data-stu-id="931ee-119">This should not be done in managed APIs.</span></span> <span data-ttu-id="931ee-120">方法重载允许在将来的版本中添加参数。</span><span class="sxs-lookup"><span data-stu-id="931ee-120">Method overloading allows adding parameters in future releases.</span></span>  
  
 <span data-ttu-id="931ee-121">**X 切忌**在枚举中包括 sentinel 值。</span><span class="sxs-lookup"><span data-stu-id="931ee-121">**X DO NOT** include sentinel values in enums.</span></span>  
  
 <span data-ttu-id="931ee-122">虽然它们有时对框架开发人员很有帮助，但是 sentinel 值会给框架的用户造成混淆。</span><span class="sxs-lookup"><span data-stu-id="931ee-122">Although they are sometimes helpful to framework developers, sentinel values are confusing to users of the framework.</span></span> <span data-ttu-id="931ee-123">它们用于跟踪枚举的状态，而不是枚举表示的集合中的一个值。</span><span class="sxs-lookup"><span data-stu-id="931ee-123">They are used to track the state of the enum rather than being one of the values from the set represented by the enum.</span></span>  
  
 <span data-ttu-id="931ee-124">**✓ 务必**为简单枚举提供零值。</span><span class="sxs-lookup"><span data-stu-id="931ee-124">**✓ DO** provide a value of zero on simple enums.</span></span>  
  
 <span data-ttu-id="931ee-125">考虑将值称为“None”等类似名称。</span><span class="sxs-lookup"><span data-stu-id="931ee-125">Consider calling the value something like "None."</span></span> <span data-ttu-id="931ee-126">如果此类值不适合此特定枚举，则应为该枚举的最常见默认值指定为零的基础值。</span><span class="sxs-lookup"><span data-stu-id="931ee-126">If such a value is not appropriate for this particular enum, the most common default value for the enum should be assigned the underlying value of zero.</span></span>  
  
 <span data-ttu-id="931ee-127">**✓ 考虑**使用 <xref:System.Int32>（大多数编程语言中的默认值）作为枚举的基础类型，除非满足以下任何条件：</span><span class="sxs-lookup"><span data-stu-id="931ee-127">**✓ CONSIDER** using <xref:System.Int32> (the default in most programming languages) as the underlying type of an enum unless any of the following is true:</span></span>  
  
- <span data-ttu-id="931ee-128">枚举是一个标志枚举，包含 32 个以上标志，或者将来可能有更多标志。</span><span class="sxs-lookup"><span data-stu-id="931ee-128">The enum is a flags enum and you have more than 32 flags, or expect to have more in the future.</span></span>  
  
- <span data-ttu-id="931ee-129">在枚举可能大小各不相同的情况下，基础类型需要与 <xref:System.Int32> 不同，以便更容易地与非托管代码进行互操作。</span><span class="sxs-lookup"><span data-stu-id="931ee-129">The underlying type needs to be different than <xref:System.Int32> for easier interoperability with unmanaged code expecting different-size enums.</span></span>  
  
- <span data-ttu-id="931ee-130">较小的基础类型将大大节省空间。</span><span class="sxs-lookup"><span data-stu-id="931ee-130">A smaller underlying type would result in substantial savings in space.</span></span> <span data-ttu-id="931ee-131">如果希望将枚举主要用作控制流的参数，则大小差别不大。</span><span class="sxs-lookup"><span data-stu-id="931ee-131">If you expect the enum to be used mainly as an argument for flow of control, the size makes little difference.</span></span> <span data-ttu-id="931ee-132">如果符合以下条件，则可以大大节省空间：</span><span class="sxs-lookup"><span data-stu-id="931ee-132">The size savings might be significant if:</span></span>  
  
    - <span data-ttu-id="931ee-133">希望将枚举在非常频繁实例化的结构或类中用作字段。</span><span class="sxs-lookup"><span data-stu-id="931ee-133">You expect the enum to be used as a field in a very frequently instantiated structure or class.</span></span>  
  
    - <span data-ttu-id="931ee-134">希望用户创建枚举实例的大型数组或集合。</span><span class="sxs-lookup"><span data-stu-id="931ee-134">You expect users to create large arrays or collections of the enum instances.</span></span>  
  
    - <span data-ttu-id="931ee-135">希望序列化大量枚举实例。</span><span class="sxs-lookup"><span data-stu-id="931ee-135">You expect a large number of instances of the enum to be serialized.</span></span>  
  
 <span data-ttu-id="931ee-136">对于内存中的用，请注意托管对象始终是 `DWORD` 对齐的，因此您需要在实例中有效地使用多个枚举或其他较小的结构来打包较小的枚举，这很重要，因为总实例大小总是要四舍五入到 `DWORD`。</span><span class="sxs-lookup"><span data-stu-id="931ee-136">For in-memory usage, be aware that managed objects are always `DWORD`-aligned, so you effectively need multiple enums or other small structures in an instance to pack a smaller enum with in order to make a difference, because the total instance size is always going to be rounded up to a `DWORD`.</span></span>  
  
 <span data-ttu-id="931ee-137">**✓ 务必**为标志枚举使用复数名词或名词短语命名，为简单枚举使用单数名词或名词短语命名。</span><span class="sxs-lookup"><span data-stu-id="931ee-137">**✓ DO** name flag enums with plural nouns or noun phrases and simple enums with singular nouns or noun phrases.</span></span>  
  
 <span data-ttu-id="931ee-138">**X 切忌**直接扩展 <xref:System.Enum?displayProperty=nameWithType>。</span><span class="sxs-lookup"><span data-stu-id="931ee-138">**X DO NOT** extend <xref:System.Enum?displayProperty=nameWithType> directly.</span></span>  
  
 <span data-ttu-id="931ee-139"><xref:System.Enum?displayProperty=nameWithType> 是 CLR 用于创建用户定义的枚举的特殊类型。</span><span class="sxs-lookup"><span data-stu-id="931ee-139"><xref:System.Enum?displayProperty=nameWithType> is a special type used by the CLR to create user-defined enumerations.</span></span> <span data-ttu-id="931ee-140">大多数编程语言都提供了一个编程元素，来使你可以使用此功能。</span><span class="sxs-lookup"><span data-stu-id="931ee-140">Most programming languages provide a programming element that gives you access to this functionality.</span></span> <span data-ttu-id="931ee-141">例如，在 C# 中，`enum` 关键字用于定义枚举。</span><span class="sxs-lookup"><span data-stu-id="931ee-141">For example, in C# the `enum` keyword is used to define an enumeration.</span></span>  
  
<a name="design"></a>   
### <a name="designing-flag-enums"></a><span data-ttu-id="931ee-142">设计标志枚举</span><span class="sxs-lookup"><span data-stu-id="931ee-142">Designing Flag Enums</span></span>  
 <span data-ttu-id="931ee-143">**✓ 务必**对标志枚举应用 <xref:System.FlagsAttribute?displayProperty=nameWithType>。</span><span class="sxs-lookup"><span data-stu-id="931ee-143">**✓ DO** apply the <xref:System.FlagsAttribute?displayProperty=nameWithType> to flag enums.</span></span> <span data-ttu-id="931ee-144">不要将此特性应用于简单枚举。</span><span class="sxs-lookup"><span data-stu-id="931ee-144">Do not apply this attribute to simple enums.</span></span>  
  
 <span data-ttu-id="931ee-145">**✓ 务必**对标志枚举值使用 2 的幂，以便可以使用按位 OR 运算自由组合它们。</span><span class="sxs-lookup"><span data-stu-id="931ee-145">**✓ DO** use powers of two for the flag enum values so they can be freely combined using the bitwise OR operation.</span></span>  
  
 <span data-ttu-id="931ee-146">**✓ 考虑**为常用的标志组合提供特殊的枚举值。</span><span class="sxs-lookup"><span data-stu-id="931ee-146">**✓ CONSIDER** providing special enum values for commonly used combinations of flags.</span></span>  
  
 <span data-ttu-id="931ee-147">按位运算是一种高级概念，简单任务应无需使用。</span><span class="sxs-lookup"><span data-stu-id="931ee-147">Bitwise operations are an advanced concept and should not be required for simple tasks.</span></span> <span data-ttu-id="931ee-148"><xref:System.IO.FileAccess.ReadWrite> 就是这种特殊值的一个例子。</span><span class="sxs-lookup"><span data-stu-id="931ee-148"><xref:System.IO.FileAccess.ReadWrite> is an example of such a special value.</span></span>  
  
 <span data-ttu-id="931ee-149">**X 避免**创建某些值组合无效的标志枚举。</span><span class="sxs-lookup"><span data-stu-id="931ee-149">**X AVOID** creating flag enums where certain combinations of values are invalid.</span></span>  
  
 <span data-ttu-id="931ee-150">**X 避免**使用值为零的标志枚举，除非该值表示“已清除所有标志”，并按照下一指南的规定进行适当命名。</span><span class="sxs-lookup"><span data-stu-id="931ee-150">**X AVOID** using flag enum values of zero unless the value represents "all flags are cleared" and is named appropriately, as prescribed by the next guideline.</span></span>  
  
 <span data-ttu-id="931ee-151">✓ 务必将值为零的标志枚举命名为 `None`。</span><span class="sxs-lookup"><span data-stu-id="931ee-151">**✓ DO** name the zero value of flag enums `None`.</span></span> <span data-ttu-id="931ee-152">于标志枚举，该值必须始终表示“已清除所有标志”。</span><span class="sxs-lookup"><span data-stu-id="931ee-152">For a flag enum, the value must always mean "all flags are cleared."</span></span>  
  
<a name="add_value"></a>   
### <a name="adding-value-to-enums"></a><span data-ttu-id="931ee-153">将值添加到枚举</span><span class="sxs-lookup"><span data-stu-id="931ee-153">Adding Value to Enums</span></span>  
 <span data-ttu-id="931ee-154">你常常会发现，需要在已发布枚举后向其添加一个值。</span><span class="sxs-lookup"><span data-stu-id="931ee-154">It is very common to discover that you need to add values to an enum after you have already shipped it.</span></span> <span data-ttu-id="931ee-155">从现有 API 返回新添加的值时，会存在潜在的应用程序兼容性问题，因为编写不当的应用程序可能无法正确处理新值。</span><span class="sxs-lookup"><span data-stu-id="931ee-155">There is a potential application compatibility problem when the newly added value is returned from an existing API, because poorly written applications might not handle the new value correctly.</span></span>  
  
 <span data-ttu-id="931ee-156">✓ 考虑将值添加到枚举，监管存在较低的兼容性风险。</span><span class="sxs-lookup"><span data-stu-id="931ee-156">**✓ CONSIDER** adding values to enums, despite a small compatibility risk.</span></span>  
  
 <span data-ttu-id="931ee-157">如果已获得了有关向枚举添加值而引起的应用程序不兼容性问题的实际数据，请考虑添加可返回新值和旧值的新 API，并弃用旧 API，该旧 API 应会继续仅返回旧值。</span><span class="sxs-lookup"><span data-stu-id="931ee-157">If you have real data about application incompatibilities caused by additions to an enum, consider adding a new API that returns the new and old values, and deprecate the old API, which should continue returning just the old values.</span></span> <span data-ttu-id="931ee-158">这将确保现有的应用程序保持兼容。</span><span class="sxs-lookup"><span data-stu-id="931ee-158">This will ensure that your existing applications remain compatible.</span></span>  
  
 <span data-ttu-id="931ee-159">*部分版权 © 2005, 2009 Microsoft Corporation。保留所有权利。*</span><span class="sxs-lookup"><span data-stu-id="931ee-159">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="931ee-160">*经 Pearson Education, Inc 授权，转载自[框架设计准则：可重用的 .NET 库的约定、习惯用语和模式，第 2 版](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) 作者：Krzysztof Cwalina 和 Brad Abrams，由 Addison Wesley Professional 于 2008 年 10 月 22 日印发，作为 Microsoft Windows 开发系列的一部分。*</span><span class="sxs-lookup"><span data-stu-id="931ee-160">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="931ee-161">请参阅</span><span class="sxs-lookup"><span data-stu-id="931ee-161">See also</span></span>

- [<span data-ttu-id="931ee-162">类型设计准则</span><span class="sxs-lookup"><span data-stu-id="931ee-162">Type Design Guidelines</span></span>](../../../docs/standard/design-guidelines/type.md)
- [<span data-ttu-id="931ee-163">框架设计指南</span><span class="sxs-lookup"><span data-stu-id="931ee-163">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
