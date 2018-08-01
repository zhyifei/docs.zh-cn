---
title: 运算符重载
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- operators [.NET Framework], overloads
- names [.NET Framework], overloaded operators
- member design guidelines, operators
- overloaded operators
ms.assetid: 37585bf2-4c27-4dee-849a-af70e3338cc1
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 747fc21aceae60e362c72391ae265e45d6f8445f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33579302"
---
# <a name="operator-overloads"></a><span data-ttu-id="e3142-102">运算符重载</span><span class="sxs-lookup"><span data-stu-id="e3142-102">Operator Overloads</span></span>
<span data-ttu-id="e3142-103">运算符重载允许起来就像它们是内置的语言基元的 framework 类型。</span><span class="sxs-lookup"><span data-stu-id="e3142-103">Operator overloads allow framework types to appear as if they were built-in language primitives.</span></span>  
  
 <span data-ttu-id="e3142-104">虽然允许，并且在某些情况下有用，应慎重使用运算符重载。</span><span class="sxs-lookup"><span data-stu-id="e3142-104">Although allowed and useful in some situations, operator overloads should be used cautiously.</span></span> <span data-ttu-id="e3142-105">有很多情况下在哪些运算符重载具有已被滥用，如 framework 设计器启动时若要使用的操作，应是简单的方法的运算符。</span><span class="sxs-lookup"><span data-stu-id="e3142-105">There are many cases in which operator overloading has been abused, such as when framework designers started to use operators for operations that should be simple methods.</span></span> <span data-ttu-id="e3142-106">以下准则可帮助您决定何时以及如何使用运算符重载。</span><span class="sxs-lookup"><span data-stu-id="e3142-106">The following guidelines should help you decide when and how to use operator overloading.</span></span>  
  
 <span data-ttu-id="e3142-107">**X AVOID** 定义运算符重载，除了应感觉基元 （内置） 类型的类型中。</span><span class="sxs-lookup"><span data-stu-id="e3142-107">**X AVOID** defining operator overloads, except in types that should feel like primitive (built-in) types.</span></span>  
  
 <span data-ttu-id="e3142-108">**✓ CONSIDER** 应感觉类似于基元类型的类型中定义运算符重载。</span><span class="sxs-lookup"><span data-stu-id="e3142-108">**✓ CONSIDER** defining operator overloads in a type that should feel like a primitive type.</span></span>  
  
 <span data-ttu-id="e3142-109">例如，<xref:System.String?displayProperty=nameWithType>具有`operator==`和`operator!=`定义。</span><span class="sxs-lookup"><span data-stu-id="e3142-109">For example, <xref:System.String?displayProperty=nameWithType> has `operator==` and `operator!=` defined.</span></span>  
  
 <span data-ttu-id="e3142-110">**✓ DO** 中表示的数字的结构定义运算符重载 (如<xref:System.Decimal?displayProperty=nameWithType>)。</span><span class="sxs-lookup"><span data-stu-id="e3142-110">**✓ DO** define operator overloads in structs that represent numbers (such as <xref:System.Decimal?displayProperty=nameWithType>).</span></span>  
  
 <span data-ttu-id="e3142-111">**X DO NOT** 过于刻意定义运算符重载时。</span><span class="sxs-lookup"><span data-stu-id="e3142-111">**X DO NOT** be cute when defining operator overloads.</span></span>  
  
 <span data-ttu-id="e3142-112">运算符重载可种情况下在其中显而易见将哪些操作的结果。</span><span class="sxs-lookup"><span data-stu-id="e3142-112">Operator overloading is useful in cases in which it is immediately obvious what the result of the operation will be.</span></span> <span data-ttu-id="e3142-113">例如，它有意义能够减去<xref:System.DateTime>从另一个`DateTime`并获取<xref:System.TimeSpan>。</span><span class="sxs-lookup"><span data-stu-id="e3142-113">For example, it makes sense to be able to subtract one <xref:System.DateTime> from another `DateTime` and get a <xref:System.TimeSpan>.</span></span> <span data-ttu-id="e3142-114">但是，不适合使用逻辑 union 运算符到联合的两个数据库查询，或使用移位运算符将写入到流。</span><span class="sxs-lookup"><span data-stu-id="e3142-114">However, it is not appropriate to use the logical union operator to union two database queries, or to use the shift operator to write to a stream.</span></span>  
  
 <span data-ttu-id="e3142-115">**X DO NOT** 提供运算符重载，除非至少其中一个操作数是定义重载的类型。</span><span class="sxs-lookup"><span data-stu-id="e3142-115">**X DO NOT** provide operator overloads unless at least one of the operands is of the type defining the overload.</span></span>  
  
 <span data-ttu-id="e3142-116">**✓ DO** 对称方式重载运算符。</span><span class="sxs-lookup"><span data-stu-id="e3142-116">**✓ DO** overload operators in a symmetric fashion.</span></span>  
  
 <span data-ttu-id="e3142-117">例如，如果重载`operator==`，还应该重载`operator!=`。</span><span class="sxs-lookup"><span data-stu-id="e3142-117">For example, if you overload the `operator==`, you should also overload the `operator!=`.</span></span> <span data-ttu-id="e3142-118">同样，如果重载`operator<`，还应该重载`operator>`，依次类推。</span><span class="sxs-lookup"><span data-stu-id="e3142-118">Similarly, if you overload the `operator<`, you should also overload the `operator>`, and so on.</span></span>  
  
 <span data-ttu-id="e3142-119">**✓ CONSIDER** 提供的友好名称的对应到每个重载运算符的方法。</span><span class="sxs-lookup"><span data-stu-id="e3142-119">**✓ CONSIDER** providing methods with friendly names that correspond to each overloaded operator.</span></span>  
  
 <span data-ttu-id="e3142-120">许多语言不支持运算符重载。</span><span class="sxs-lookup"><span data-stu-id="e3142-120">Many languages do not support operator overloading.</span></span> <span data-ttu-id="e3142-121">出于此原因，建议重载运算符的类型包括具有正确的特定于域的名称，它提供等效功能的辅助方法。</span><span class="sxs-lookup"><span data-stu-id="e3142-121">For this reason, it is recommended that types that overload operators include a secondary method with an appropriate domain-specific name that provides equivalent functionality.</span></span>  
  
 <span data-ttu-id="e3142-122">下表包含运算符和相应的友好的方法名称的列表。</span><span class="sxs-lookup"><span data-stu-id="e3142-122">The following table contains a list of operators and the corresponding friendly method names.</span></span>  
  
|<span data-ttu-id="e3142-123">C# 运算符</span><span class="sxs-lookup"><span data-stu-id="e3142-123">C# Operator Symbol</span></span>|<span data-ttu-id="e3142-124">元数据名称</span><span class="sxs-lookup"><span data-stu-id="e3142-124">Metadata Name</span></span>|<span data-ttu-id="e3142-125">友好名称</span><span class="sxs-lookup"><span data-stu-id="e3142-125">Friendly Name</span></span>|  
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
  
### <a name="overloading-operator-"></a><span data-ttu-id="e3142-126">重载运算符 = =</span><span class="sxs-lookup"><span data-stu-id="e3142-126">Overloading Operator ==</span></span>  
 <span data-ttu-id="e3142-127">重载`operator ==`非常复杂。</span><span class="sxs-lookup"><span data-stu-id="e3142-127">Overloading `operator ==` is quite complicated.</span></span> <span data-ttu-id="e3142-128">运算符的语义需要是符合几个其他成员，如<xref:System.Object.Equals%2A?displayProperty=nameWithType>。</span><span class="sxs-lookup"><span data-stu-id="e3142-128">The semantics of the operator need to be compatible with several other members, such as <xref:System.Object.Equals%2A?displayProperty=nameWithType>.</span></span>  
  
### <a name="conversion-operators"></a><span data-ttu-id="e3142-129">转换运算符</span><span class="sxs-lookup"><span data-stu-id="e3142-129">Conversion Operators</span></span>  
 <span data-ttu-id="e3142-130">转换运算符是一元运算符，从而允许从一种类型到另一个转换。</span><span class="sxs-lookup"><span data-stu-id="e3142-130">Conversion operators are unary operators that allow conversion from one type to another.</span></span> <span data-ttu-id="e3142-131">必须将运算符定义为操作数或返回类型上的静态成员。</span><span class="sxs-lookup"><span data-stu-id="e3142-131">The operators must be defined as static members on either the operand or the return type.</span></span> <span data-ttu-id="e3142-132">有两种类型的转换运算符： 隐式和显式。</span><span class="sxs-lookup"><span data-stu-id="e3142-132">There are two types of conversion operators: implicit and explicit.</span></span>  
  
 <span data-ttu-id="e3142-133">**X DO NOT** 提供转换运算符，如果最终用户未明确要求这种转换。</span><span class="sxs-lookup"><span data-stu-id="e3142-133">**X DO NOT** provide a conversion operator if such conversion is not clearly expected by the end users.</span></span>  
  
 <span data-ttu-id="e3142-134">**X DO NOT** 定义转换运算符之外的类型的域。</span><span class="sxs-lookup"><span data-stu-id="e3142-134">**X DO NOT** define conversion operators outside of a type’s domain.</span></span>  
  
 <span data-ttu-id="e3142-135">例如， <xref:System.Int32>， <xref:System.Double>，和<xref:System.Decimal>是所有数值类型，而<xref:System.DateTime>不是。</span><span class="sxs-lookup"><span data-stu-id="e3142-135">For example, <xref:System.Int32>, <xref:System.Double>, and <xref:System.Decimal> are all numeric types, whereas <xref:System.DateTime> is not.</span></span> <span data-ttu-id="e3142-136">因此，应该有任何转换运算符以转换`Double(long)`到`DateTime`。</span><span class="sxs-lookup"><span data-stu-id="e3142-136">Therefore, there should be no conversion operator to convert a `Double(long)` to a `DateTime`.</span></span> <span data-ttu-id="e3142-137">在这种情况下被首选构造函数。</span><span class="sxs-lookup"><span data-stu-id="e3142-137">A constructor is preferred in such a case.</span></span>  
  
 <span data-ttu-id="e3142-138">**X DO NOT** 提供隐式转换运算符，如果转换，则可能丢失信息。</span><span class="sxs-lookup"><span data-stu-id="e3142-138">**X DO NOT** provide an implicit conversion operator if the conversion is potentially lossy.</span></span>  
  
 <span data-ttu-id="e3142-139">例如，存在不应为隐式转换`Double`到`Int32`因为`Double`更广范围比`Int32`。</span><span class="sxs-lookup"><span data-stu-id="e3142-139">For example, there should not be an implicit conversion from `Double` to `Int32` because `Double` has a wider range than `Int32`.</span></span> <span data-ttu-id="e3142-140">可以提供显式转换运算符，即使该转换是可能丢失信息。</span><span class="sxs-lookup"><span data-stu-id="e3142-140">An explicit conversion operator can be provided even if the conversion is potentially lossy.</span></span>  
  
 <span data-ttu-id="e3142-141">**X DO NOT** 从隐式强制转换引发异常。</span><span class="sxs-lookup"><span data-stu-id="e3142-141">**X DO NOT** throw exceptions from implicit casts.</span></span>  
  
 <span data-ttu-id="e3142-142">它是最终用户了解发生了什么情况，因为它们可能不知道正在进行转换很难。</span><span class="sxs-lookup"><span data-stu-id="e3142-142">It is very difficult for end users to understand what is happening, because they might not be aware that a conversion is taking place.</span></span>  
  
 <span data-ttu-id="e3142-143">**✓ DO** 引发<xref:System.InvalidCastException?displayProperty=nameWithType>如果对强制转换运算符的调用导致有损转换和运算符的协定不允许丢失数据的转换。</span><span class="sxs-lookup"><span data-stu-id="e3142-143">**✓ DO** throw <xref:System.InvalidCastException?displayProperty=nameWithType> if a call to a cast operator results in a lossy conversion and the contract of the operator does not allow lossy conversions.</span></span>  
  
 <span data-ttu-id="e3142-144">*部分 © 2005年，2009 Microsoft Corporation。保留所有权利。*</span><span class="sxs-lookup"><span data-stu-id="e3142-144">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="e3142-145">*通过从皮尔逊教育版，Inc.的权限重新打印[Framework 设计准则： 约定、 语法和可重用.NET 库，版本 2 的模式](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619)通过 Krzysztof Cwalina 和 Brad Abrams，发布 2008 年 10 月 22，通过Microsoft Windows 开发系列的一部分的 Addison Wesley Professional。*</span><span class="sxs-lookup"><span data-stu-id="e3142-145">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e3142-146">请参阅</span><span class="sxs-lookup"><span data-stu-id="e3142-146">See Also</span></span>  
 [<span data-ttu-id="e3142-147">成员设计准则</span><span class="sxs-lookup"><span data-stu-id="e3142-147">Member Design Guidelines</span></span>](../../../docs/standard/design-guidelines/member.md)  
 [<span data-ttu-id="e3142-148">框架设计指南</span><span class="sxs-lookup"><span data-stu-id="e3142-148">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
