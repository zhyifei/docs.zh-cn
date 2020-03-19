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
ms.openlocfilehash: 0999e94c8d77396b237522e89c51206ce1226718
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/14/2020
ms.locfileid: "79401219"
---
# <a name="operator-overloads"></a><span data-ttu-id="b664c-102">运算符重载</span><span class="sxs-lookup"><span data-stu-id="b664c-102">Operator Overloads</span></span>
<span data-ttu-id="b664c-103">运算符重载允许框架类型显示为内置语言基元。</span><span class="sxs-lookup"><span data-stu-id="b664c-103">Operator overloads allow framework types to appear as if they were built-in language primitives.</span></span>

 <span data-ttu-id="b664c-104">尽管在某些情况下允许并且很有用，但应谨慎使用操作员过载。</span><span class="sxs-lookup"><span data-stu-id="b664c-104">Although allowed and useful in some situations, operator overloads should be used cautiously.</span></span> <span data-ttu-id="b664c-105">在许多情况下，运算符过载被滥用，例如框架设计器开始使用运算符执行应该简单的操作。</span><span class="sxs-lookup"><span data-stu-id="b664c-105">There are many cases in which operator overloading has been abused, such as when framework designers started to use operators for operations that should be simple methods.</span></span> <span data-ttu-id="b664c-106">以下指南将帮助您决定何时以及如何使用运算符重载。</span><span class="sxs-lookup"><span data-stu-id="b664c-106">The following guidelines should help you decide when and how to use operator overloading.</span></span>

 <span data-ttu-id="b664c-107">❌AVOID 定义运算符重载，但应感觉像基元（内置）类型的类型除外。</span><span class="sxs-lookup"><span data-stu-id="b664c-107">❌ AVOID defining operator overloads, except in types that should feel like primitive (built-in) types.</span></span>

 <span data-ttu-id="b664c-108">✔️考虑在应感觉像基元类型的类型中定义运算符重载。</span><span class="sxs-lookup"><span data-stu-id="b664c-108">✔️ CONSIDER defining operator overloads in a type that should feel like a primitive type.</span></span>

 <span data-ttu-id="b664c-109">例如，<xref:System.String?displayProperty=nameWithType>已`operator==`和`operator!=`已定义。</span><span class="sxs-lookup"><span data-stu-id="b664c-109">For example, <xref:System.String?displayProperty=nameWithType> has `operator==` and `operator!=` defined.</span></span>

 <span data-ttu-id="b664c-110">✔️DO在表示数字（如<xref:System.Decimal?displayProperty=nameWithType>）的结构中定义运算符重载。</span><span class="sxs-lookup"><span data-stu-id="b664c-110">✔️ DO define operator overloads in structs that represent numbers (such as <xref:System.Decimal?displayProperty=nameWithType>).</span></span>

 <span data-ttu-id="b664c-111">❌定义运算符过载时不要可爱。</span><span class="sxs-lookup"><span data-stu-id="b664c-111">❌ DO NOT be cute when defining operator overloads.</span></span>

 <span data-ttu-id="b664c-112">在操作结果立即明显的情况下，操作员重载非常有用。</span><span class="sxs-lookup"><span data-stu-id="b664c-112">Operator overloading is useful in cases in which it is immediately obvious what the result of the operation will be.</span></span> <span data-ttu-id="b664c-113">例如，能够从另<xref:System.DateTime>`DateTime`一个中减去一个并获取 一个<xref:System.TimeSpan>是有意义的。</span><span class="sxs-lookup"><span data-stu-id="b664c-113">For example, it makes sense to be able to subtract one <xref:System.DateTime> from another `DateTime` and get a <xref:System.TimeSpan>.</span></span> <span data-ttu-id="b664c-114">但是，使用逻辑联合运算符联合两个数据库查询或使用移位运算符写入流是不适当的。</span><span class="sxs-lookup"><span data-stu-id="b664c-114">However, it is not appropriate to use the logical union operator to union two database queries, or to use the shift operator to write to a stream.</span></span>

 <span data-ttu-id="b664c-115">❌除非至少有一个操作数是定义重载的类型，否则不要提供运算符重载。</span><span class="sxs-lookup"><span data-stu-id="b664c-115">❌ DO NOT provide operator overloads unless at least one of the operands is of the type defining the overload.</span></span>

 <span data-ttu-id="b664c-116">✔️以对称方式执行重载运算符。</span><span class="sxs-lookup"><span data-stu-id="b664c-116">✔️ DO overload operators in a symmetric fashion.</span></span>

 <span data-ttu-id="b664c-117">例如，如果重载`operator==`， 还应重载 。 `operator!=`</span><span class="sxs-lookup"><span data-stu-id="b664c-117">For example, if you overload the `operator==`, you should also overload the `operator!=`.</span></span> <span data-ttu-id="b664c-118">同样，如果重载`operator<`，也应重载`operator>`等。</span><span class="sxs-lookup"><span data-stu-id="b664c-118">Similarly, if you overload the `operator<`, you should also overload the `operator>`, and so on.</span></span>

 <span data-ttu-id="b664c-119">✔️考虑提供与每个重载运算符对应的友好名称的方法。</span><span class="sxs-lookup"><span data-stu-id="b664c-119">✔️ CONSIDER providing methods with friendly names that correspond to each overloaded operator.</span></span>

 <span data-ttu-id="b664c-120">许多语言不支持运算符重载。</span><span class="sxs-lookup"><span data-stu-id="b664c-120">Many languages do not support operator overloading.</span></span> <span data-ttu-id="b664c-121">因此，建议重载运算符的类型包括具有提供等效功能的适当特定于域的名称的辅助方法。</span><span class="sxs-lookup"><span data-stu-id="b664c-121">For this reason, it is recommended that types that overload operators include a secondary method with an appropriate domain-specific name that provides equivalent functionality.</span></span>

 <span data-ttu-id="b664c-122">下表包含运算符列表和相应的友好方法名称。</span><span class="sxs-lookup"><span data-stu-id="b664c-122">The following table contains a list of operators and the corresponding friendly method names.</span></span>

|<span data-ttu-id="b664c-123">C# 运算符符号</span><span class="sxs-lookup"><span data-stu-id="b664c-123">C# Operator Symbol</span></span>|<span data-ttu-id="b664c-124">元数据名称</span><span class="sxs-lookup"><span data-stu-id="b664c-124">Metadata Name</span></span>|<span data-ttu-id="b664c-125">友好名称</span><span class="sxs-lookup"><span data-stu-id="b664c-125">Friendly Name</span></span>|
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

### <a name="overloading-operator-"></a><span data-ttu-id="b664c-126">重载运算符 |</span><span class="sxs-lookup"><span data-stu-id="b664c-126">Overloading Operator ==</span></span>
 <span data-ttu-id="b664c-127">过载`operator ==`相当复杂。</span><span class="sxs-lookup"><span data-stu-id="b664c-127">Overloading `operator ==` is quite complicated.</span></span> <span data-ttu-id="b664c-128">运算符的语义需要与其他几个成员（如<xref:System.Object.Equals%2A?displayProperty=nameWithType>） 兼容。</span><span class="sxs-lookup"><span data-stu-id="b664c-128">The semantics of the operator need to be compatible with several other members, such as <xref:System.Object.Equals%2A?displayProperty=nameWithType>.</span></span>

### <a name="conversion-operators"></a><span data-ttu-id="b664c-129">转换运算符</span><span class="sxs-lookup"><span data-stu-id="b664c-129">Conversion Operators</span></span>
 <span data-ttu-id="b664c-130">转换运算符是允许从一种类型转换为另一种类型的单位运算符。</span><span class="sxs-lookup"><span data-stu-id="b664c-130">Conversion operators are unary operators that allow conversion from one type to another.</span></span> <span data-ttu-id="b664c-131">运算符必须定义为操作数或返回类型的静态成员。</span><span class="sxs-lookup"><span data-stu-id="b664c-131">The operators must be defined as static members on either the operand or the return type.</span></span> <span data-ttu-id="b664c-132">转换运算符有两种类型：隐式运算符和显式运算符。</span><span class="sxs-lookup"><span data-stu-id="b664c-132">There are two types of conversion operators: implicit and explicit.</span></span>

 <span data-ttu-id="b664c-133">❌如果最终用户没有明确预期此类转换，则不要提供转换运算符。</span><span class="sxs-lookup"><span data-stu-id="b664c-133">❌ DO NOT provide a conversion operator if such conversion is not clearly expected by the end users.</span></span>

 <span data-ttu-id="b664c-134">❌不要在类型域之外定义转换运算符。</span><span class="sxs-lookup"><span data-stu-id="b664c-134">❌ DO NOT define conversion operators outside of a type’s domain.</span></span>

 <span data-ttu-id="b664c-135"><xref:System.Int32>例如，<xref:System.Double>和<xref:System.Decimal>都是数字类型， 而不是。 <xref:System.DateTime></span><span class="sxs-lookup"><span data-stu-id="b664c-135">For example, <xref:System.Int32>, <xref:System.Double>, and <xref:System.Decimal> are all numeric types, whereas <xref:System.DateTime> is not.</span></span> <span data-ttu-id="b664c-136">因此，不应有转换运算符将`Double(long)`转换为 。 `DateTime`</span><span class="sxs-lookup"><span data-stu-id="b664c-136">Therefore, there should be no conversion operator to convert a `Double(long)` to a `DateTime`.</span></span> <span data-ttu-id="b664c-137">在这种情况下，构造函数是首选。</span><span class="sxs-lookup"><span data-stu-id="b664c-137">A constructor is preferred in such a case.</span></span>

 <span data-ttu-id="b664c-138">❌如果转换可能丢失，请不要提供隐式转换运算符。</span><span class="sxs-lookup"><span data-stu-id="b664c-138">❌ DO NOT provide an implicit conversion operator if the conversion is potentially lossy.</span></span>

 <span data-ttu-id="b664c-139">例如，`Double`不应有从 到`Int32`的隐式转换，`Double`因为 范围比`Int32`宽。</span><span class="sxs-lookup"><span data-stu-id="b664c-139">For example, there should not be an implicit conversion from `Double` to `Int32` because `Double` has a wider range than `Int32`.</span></span> <span data-ttu-id="b664c-140">即使转换可能丢失，也可以提供显式转换运算符。</span><span class="sxs-lookup"><span data-stu-id="b664c-140">An explicit conversion operator can be provided even if the conversion is potentially lossy.</span></span>

 <span data-ttu-id="b664c-141">❌不要从隐式强制转换中引发异常。</span><span class="sxs-lookup"><span data-stu-id="b664c-141">❌ DO NOT throw exceptions from implicit casts.</span></span>

 <span data-ttu-id="b664c-142">最终用户很难理解发生了什么，因为他们可能不知道正在进行转换。</span><span class="sxs-lookup"><span data-stu-id="b664c-142">It is very difficult for end users to understand what is happening, because they might not be aware that a conversion is taking place.</span></span>

 <span data-ttu-id="b664c-143">如果调用强制<xref:System.InvalidCastException?displayProperty=nameWithType>转换运算符导致亏损转换，并且操作员的合同不允许亏损转换，则✔️强制进行丢弃。</span><span class="sxs-lookup"><span data-stu-id="b664c-143">✔️ DO throw <xref:System.InvalidCastException?displayProperty=nameWithType> if a call to a cast operator results in a lossy conversion and the contract of the operator does not allow lossy conversions.</span></span>

 <span data-ttu-id="b664c-144">*部分© 2005， 2009 微软公司.保留所有权利。*</span><span class="sxs-lookup"><span data-stu-id="b664c-144">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>

 <span data-ttu-id="b664c-145">*经 Pearson 教育公司许可，从[框架设计指南：可重用的约定、习语和模式 .NET 库重新打印，第二版](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619)由 Krzysztof Cwalina 和 Brad Abrams 出版，由艾迪森-韦斯利专业公司作为微软 Windows 开发系列的一部分于 2008 年 10 月 22 日出版。*</span><span class="sxs-lookup"><span data-stu-id="b664c-145">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>

## <a name="see-also"></a><span data-ttu-id="b664c-146">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b664c-146">See also</span></span>

- [<span data-ttu-id="b664c-147">成员设计准则</span><span class="sxs-lookup"><span data-stu-id="b664c-147">Member Design Guidelines</span></span>](../../../docs/standard/design-guidelines/member.md)
- [<span data-ttu-id="b664c-148">框架设计准则</span><span class="sxs-lookup"><span data-stu-id="b664c-148">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
