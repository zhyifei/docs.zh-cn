---
title: 运算符重载
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- operators [.NET Framework], overloads
- names [.NET Framework], overloaded operators
- member design guidelines, operators
- overloaded operators
ms.assetid: 37585bf2-4c27-4dee-849a-af70e3338cc1
author: KrzysztofCwalina
ms.openlocfilehash: d1b9d8bc1f5f6f83a50dbd798894f94937320d2b
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2018
ms.locfileid: "53152131"
---
# <a name="operator-overloads"></a><span data-ttu-id="30002-102">运算符重载</span><span class="sxs-lookup"><span data-stu-id="30002-102">Operator Overloads</span></span>
<span data-ttu-id="30002-103">运算符重载允许框架类型的外观类似内置语言基元。</span><span class="sxs-lookup"><span data-stu-id="30002-103">Operator overloads allow framework types to appear as if they were built-in language primitives.</span></span>  
  
 <span data-ttu-id="30002-104">虽然在某些情况下允许使用运算符重载并且有用，但应谨慎使用。</span><span class="sxs-lookup"><span data-stu-id="30002-104">Although allowed and useful in some situations, operator overloads should be used cautiously.</span></span> <span data-ttu-id="30002-105">在许多情况下，运算符重载受到滥用，例如框架设计者开始使用运算符进行本应是简单方法的操作。</span><span class="sxs-lookup"><span data-stu-id="30002-105">There are many cases in which operator overloading has been abused, such as when framework designers started to use operators for operations that should be simple methods.</span></span> <span data-ttu-id="30002-106">以下准则可帮助你确定何时以及如何使用运算符重载。</span><span class="sxs-lookup"><span data-stu-id="30002-106">The following guidelines should help you decide when and how to use operator overloading.</span></span>  
  
 <span data-ttu-id="30002-107">**X 避免**定义运算符重载，但对于看似基元（内置）类型的类型除外。</span><span class="sxs-lookup"><span data-stu-id="30002-107">**X AVOID** defining operator overloads, except in types that should feel like primitive (built-in) types.</span></span>  
  
 <span data-ttu-id="30002-108">**✓ 考虑**在一个感觉应该像基元类型的类型中定义运算符重载。</span><span class="sxs-lookup"><span data-stu-id="30002-108">**✓ CONSIDER** defining operator overloads in a type that should feel like a primitive type.</span></span>  
  
 <span data-ttu-id="30002-109">例如，<xref:System.String?displayProperty=nameWithType> 定义 `operator==` 和 `operator!=`。</span><span class="sxs-lookup"><span data-stu-id="30002-109">For example, <xref:System.String?displayProperty=nameWithType> has `operator==` and `operator!=` defined.</span></span>  
  
 <span data-ttu-id="30002-110">**✓ 务必**在表示数字的结构中定义运算符重载（例如 <xref:System.Decimal?displayProperty=nameWithType> ）。</span><span class="sxs-lookup"><span data-stu-id="30002-110">**✓ DO** define operator overloads in structs that represent numbers (such as <xref:System.Decimal?displayProperty=nameWithType>).</span></span>  
  
 <span data-ttu-id="30002-111">**X 切忌**在定义运算符重载时过于刻意。</span><span class="sxs-lookup"><span data-stu-id="30002-111">**X DO NOT** be cute when defining operator overloads.</span></span>  
  
 <span data-ttu-id="30002-112">如果操作结果直观而明显，则运算符重载非常有用。</span><span class="sxs-lookup"><span data-stu-id="30002-112">Operator overloading is useful in cases in which it is immediately obvious what the result of the operation will be.</span></span> <span data-ttu-id="30002-113">例如，能够从一个 <xref:System.DateTime> 中减去另一个 `DateTime`，并得到 <xref:System.TimeSpan>，这是有意义的。</span><span class="sxs-lookup"><span data-stu-id="30002-113">For example, it makes sense to be able to subtract one <xref:System.DateTime> from another `DateTime` and get a <xref:System.TimeSpan>.</span></span> <span data-ttu-id="30002-114">但是，使用逻辑 union 运算符来合并两个数据库查询或使用 shift 运算符写入流则是不合适的。</span><span class="sxs-lookup"><span data-stu-id="30002-114">However, it is not appropriate to use the logical union operator to union two database queries, or to use the shift operator to write to a stream.</span></span>  
  
 <span data-ttu-id="30002-115">**X 切忌**提供运算符重载，除非至少其中一个运算数是定义重载的类型。</span><span class="sxs-lookup"><span data-stu-id="30002-115">**X DO NOT** provide operator overloads unless at least one of the operands is of the type defining the overload.</span></span>  
  
 <span data-ttu-id="30002-116">**X 切忌**在定义运算符重载时过于刻意。</span><span class="sxs-lookup"><span data-stu-id="30002-116">**✓ DO** overload operators in a symmetric fashion.</span></span>  
  
 <span data-ttu-id="30002-117">例如，如果重载了 `operator==`，则还应该重载 `operator!=`。</span><span class="sxs-lookup"><span data-stu-id="30002-117">For example, if you overload the `operator==`, you should also overload the `operator!=`.</span></span> <span data-ttu-id="30002-118">同样，如果重载了 `operator<`，则还应该重载 `operator>`，以此类推。</span><span class="sxs-lookup"><span data-stu-id="30002-118">Similarly, if you overload the `operator<`, you should also overload the `operator>`, and so on.</span></span>  
  
 <span data-ttu-id="30002-119">**✓ 考虑**提供与每个重载运算符对应的具有友好名称的方法。</span><span class="sxs-lookup"><span data-stu-id="30002-119">**✓ CONSIDER** providing methods with friendly names that correspond to each overloaded operator.</span></span>  
  
 <span data-ttu-id="30002-120">许多语言不支持运算符重载。</span><span class="sxs-lookup"><span data-stu-id="30002-120">Many languages do not support operator overloading.</span></span> <span data-ttu-id="30002-121">因此，建议重载运算符的类型包括具有适当的特定于域的名称的辅助方法，该方法提供等效功能。</span><span class="sxs-lookup"><span data-stu-id="30002-121">For this reason, it is recommended that types that overload operators include a secondary method with an appropriate domain-specific name that provides equivalent functionality.</span></span>  
  
 <span data-ttu-id="30002-122">下表包含一系列运算符和相应的友好方法名称。</span><span class="sxs-lookup"><span data-stu-id="30002-122">The following table contains a list of operators and the corresponding friendly method names.</span></span>  
  
|<span data-ttu-id="30002-123">C# 运算符符号</span><span class="sxs-lookup"><span data-stu-id="30002-123">C# Operator Symbol</span></span>|<span data-ttu-id="30002-124">元数据名称</span><span class="sxs-lookup"><span data-stu-id="30002-124">Metadata Name</span></span>|<span data-ttu-id="30002-125">友好名称</span><span class="sxs-lookup"><span data-stu-id="30002-125">Friendly Name</span></span>|  
|-------------------------|-------------------|-------------------|  
|`N/A`|`op_Implicit`|`To<TypeName>/From<TypeName>`|  
|`N/A`|`op_Explicit`|`To<TypeName>/From<TypeName>`|  
|`+ (binary)`|`op_Addition`|`Add`|  
|`- (binary)`|`op_Subtraction`|`Subtract`|  
|`* (binary)`|`op_Multiply`|`Multiply`|  
|`/`|`op_Division`|`Divide`|  
|`%`|`op_Modulus`|`Mod or Remainder`|  
|`^`|`op_ExclusiveOr`|`Xor`|  
|`& (binary)`|`op_BitwiseAnd`|`BitwiseAnd`|  
|<code>&#124;</code>|`op_BitwiseOr`|`BitwiseOr`|  
|`&&`|`op_LogicalAnd`|`And`|  
|<code>&#124;&#124;</code>|`op_LogicalOr`|`Or`|  
|`=`|`op_Assign`|`Assign`|  
|`<<`|`op_LeftShift`|`LeftShift`|  
|`>>`|`op_RightShift`|`RightShift`|  
|`N/A`|`op_SignedRightShift`|`SignedRightShift`|  
|`N/A`|`op_UnsignedRightShift`|`UnsignedRightShift`|  
|`==`|`op_Equality`|`Equals`|  
|`!=`|`op_Inequality`|`Equals`|  
|`>`|`op_GreaterThan`|`CompareTo`|  
|`<`|`op_LessThan`|`CompareTo`|  
|`>=`|`op_GreaterThanOrEqual`|`CompareTo`|  
|`<=`|`op_LessThanOrEqual`|`CompareTo`|  
|`*=`|`op_MultiplicationAssignment`|`Multiply`|  
|`-=`|`op_SubtractionAssignment`|`Subtract`|  
|`^=`|`op_ExclusiveOrAssignment`|`Xor`|  
|`<<=`|`op_LeftShiftAssignment`|`LeftShift`|  
|`%=`|`op_ModulusAssignment`|`Mod`|  
|`+=`|`op_AdditionAssignment`|`Add`|  
|`&=`|`op_BitwiseAndAssignment`|`BitwiseAnd`|  
|<code>&#124;=</code>|`op_BitwiseOrAssignment`|`BitwiseOr`|  
|`,`|`op_Comma`|`Comma`|  
|`/=`|`op_DivisionAssignment`|`Divide`|  
|`--`|`op_Decrement`|`Decrement`|  
|`++`|`op_Increment`|`Increment`|  
|`- (unary)`|`op_UnaryNegation`|`Negate`|  
|`+ (unary)`|`op_UnaryPlus`|`Plus`|  
|`~`|`op_OnesComplement`|`OnesComplement`|  
  
### <a name="overloading-operator-"></a><span data-ttu-id="30002-126">重载运算符 ==</span><span class="sxs-lookup"><span data-stu-id="30002-126">Overloading Operator ==</span></span>  
 <span data-ttu-id="30002-127">重载 `operator ==` 非常复杂。</span><span class="sxs-lookup"><span data-stu-id="30002-127">Overloading `operator ==` is quite complicated.</span></span> <span data-ttu-id="30002-128">运算符的语义需要与其他几个其他成员兼容，如 <xref:System.Object.Equals%2A?displayProperty=nameWithType>。</span><span class="sxs-lookup"><span data-stu-id="30002-128">The semantics of the operator need to be compatible with several other members, such as <xref:System.Object.Equals%2A?displayProperty=nameWithType>.</span></span>  
  
### <a name="conversion-operators"></a><span data-ttu-id="30002-129">转换运算符</span><span class="sxs-lookup"><span data-stu-id="30002-129">Conversion Operators</span></span>  
 <span data-ttu-id="30002-130">转换运算符是一元运算符，允许从一种类型转换为另一种类型。</span><span class="sxs-lookup"><span data-stu-id="30002-130">Conversion operators are unary operators that allow conversion from one type to another.</span></span> <span data-ttu-id="30002-131">必须在操作数或返回类型上将运算符定义为静态成员。</span><span class="sxs-lookup"><span data-stu-id="30002-131">The operators must be defined as static members on either the operand or the return type.</span></span> <span data-ttu-id="30002-132">有两种类型的转换运算符：隐式和显式。</span><span class="sxs-lookup"><span data-stu-id="30002-132">There are two types of conversion operators: implicit and explicit.</span></span>  
  
 <span data-ttu-id="30002-133">**X 切忌**提供转换运算符，如果最终用户未明确要求这种转换。</span><span class="sxs-lookup"><span data-stu-id="30002-133">**X DO NOT** provide a conversion operator if such conversion is not clearly expected by the end users.</span></span>  
  
 <span data-ttu-id="30002-134">**X 切忌**定义类型域外的转换运算符。</span><span class="sxs-lookup"><span data-stu-id="30002-134">**X DO NOT** define conversion operators outside of a type’s domain.</span></span>  
  
 <span data-ttu-id="30002-135">例如， <xref:System.Int32>、<xref:System.Double> 和 <xref:System.Decimal> 都是数字类型，而 <xref:System.DateTime> 不是。</span><span class="sxs-lookup"><span data-stu-id="30002-135">For example, <xref:System.Int32>, <xref:System.Double>, and <xref:System.Decimal> are all numeric types, whereas <xref:System.DateTime> is not.</span></span> <span data-ttu-id="30002-136">因此，不应该存在将 `Double(long)` 转换到 `DateTime` 的转换运算符。</span><span class="sxs-lookup"><span data-stu-id="30002-136">Therefore, there should be no conversion operator to convert a `Double(long)` to a `DateTime`.</span></span> <span data-ttu-id="30002-137">在这种情况中，应该首选构造函数。</span><span class="sxs-lookup"><span data-stu-id="30002-137">A constructor is preferred in such a case.</span></span>  
  
 <span data-ttu-id="30002-138">**X 切忌**在转换可能产生损耗的情况下提供隐式转换运算符。</span><span class="sxs-lookup"><span data-stu-id="30002-138">**X DO NOT** provide an implicit conversion operator if the conversion is potentially lossy.</span></span>  
  
 <span data-ttu-id="30002-139">例如，不应该存在从 `Double` 到 `Int32` 的隐式转换，因为 `Double` 比 `Int32` 的范围更大。</span><span class="sxs-lookup"><span data-stu-id="30002-139">For example, there should not be an implicit conversion from `Double` to `Int32` because `Double` has a wider range than `Int32`.</span></span> <span data-ttu-id="30002-140">可以提供显式转换运算符，即使转换可能产生损耗。</span><span class="sxs-lookup"><span data-stu-id="30002-140">An explicit conversion operator can be provided even if the conversion is potentially lossy.</span></span>  
  
 <span data-ttu-id="30002-141">**X 切忌**从隐式转换中引发异常。</span><span class="sxs-lookup"><span data-stu-id="30002-141">**X DO NOT** throw exceptions from implicit casts.</span></span>  
  
 <span data-ttu-id="30002-142">最终用户将难以理解当前出现的情况，因为他们可能不知道转换正在进行。</span><span class="sxs-lookup"><span data-stu-id="30002-142">It is very difficult for end users to understand what is happening, because they might not be aware that a conversion is taking place.</span></span>  
  
 <span data-ttu-id="30002-143">**✓ 务必**引发 <xref:System.InvalidCastException?displayProperty=nameWithType>，如果对转换运算符的调用会导致有损转换，并且运算符的协定不允许丢失数据的转换。</span><span class="sxs-lookup"><span data-stu-id="30002-143">**✓ DO** throw <xref:System.InvalidCastException?displayProperty=nameWithType> if a call to a cast operator results in a lossy conversion and the contract of the operator does not allow lossy conversions.</span></span>  
  
 <span data-ttu-id="30002-144">*部分版权 © 2005, 2009 Microsoft Corporation。保留所有权利。*</span><span class="sxs-lookup"><span data-stu-id="30002-144">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="30002-145">*通过从 Pearson Education，Inc.的权限重新打印[Framework 设计准则：约定、 语法和模式的可重用.NET 库，第 2 版](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619)Krzysztof Cwalina 和 Brad Abrams，作为 Microsoft Windows 开发系列的一部分发布 2008 年 10 月 22 日由 Addison-wesley 专业人员。*</span><span class="sxs-lookup"><span data-stu-id="30002-145">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="30002-146">请参阅</span><span class="sxs-lookup"><span data-stu-id="30002-146">See also</span></span>

- [<span data-ttu-id="30002-147">成员设计准则</span><span class="sxs-lookup"><span data-stu-id="30002-147">Member Design Guidelines</span></span>](../../../docs/standard/design-guidelines/member.md)  
- [<span data-ttu-id="30002-148">框架设计指南</span><span class="sxs-lookup"><span data-stu-id="30002-148">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
