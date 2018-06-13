---
title: ulong（C# 参考）
ms.date: 03/14/2017
f1_keywords:
- ulong_CSharpKeyword
- ulong
helpviewer_keywords:
- ulong keyword [C#]
ms.assetid: f2ece624-837a-40cf-92c5-343e7f33397c
ms.openlocfilehash: 1f291d2dd2706231f018a04f0af86051cef6c28a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33288302"
---
# <a name="ulong-c-reference"></a><span data-ttu-id="f16eb-102">ulong（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="f16eb-102">ulong (C# Reference)</span></span>

<span data-ttu-id="f16eb-103">`ulong` 关键字表示一种整型类型，该类型根据下表显示的大小和范围存储值。</span><span class="sxs-lookup"><span data-stu-id="f16eb-103">The `ulong` keyword denotes an integral type that stores values according to the size and range shown in the following table.</span></span>  
  
|<span data-ttu-id="f16eb-104">类型</span><span class="sxs-lookup"><span data-stu-id="f16eb-104">Type</span></span>|<span data-ttu-id="f16eb-105">范围</span><span class="sxs-lookup"><span data-stu-id="f16eb-105">Range</span></span>|<span data-ttu-id="f16eb-106">大小</span><span class="sxs-lookup"><span data-stu-id="f16eb-106">Size</span></span>|<span data-ttu-id="f16eb-107">.NET Framework 类型</span><span class="sxs-lookup"><span data-stu-id="f16eb-107">.NET Framework type</span></span>|  
|----------|-----------|----------|-------------------------|  
|`ulong`|<span data-ttu-id="f16eb-108">0 到 18,446,744,073,709,551,615</span><span class="sxs-lookup"><span data-stu-id="f16eb-108">0 to 18,446,744,073,709,551,615</span></span>|<span data-ttu-id="f16eb-109">无符号 64 位整数</span><span class="sxs-lookup"><span data-stu-id="f16eb-109">Unsigned 64-bit integer</span></span>|<xref:System.UInt64?displayProperty=nameWithType>|  
  
## <a name="literals"></a><span data-ttu-id="f16eb-110">文本</span><span class="sxs-lookup"><span data-stu-id="f16eb-110">Literals</span></span>  

<span data-ttu-id="f16eb-111">可以通过为其分配十进制文本、十六进制文本或（从 C# 7.0 开始）二进制文本来声明和初始化 `ulong` 变量。</span><span class="sxs-lookup"><span data-stu-id="f16eb-111">You can declare and initialize a `ulong` variable by assigning a decimal literal, a hexadecimal literal, or (starting with C# 7.0) a binary literal to it.</span></span>  <span data-ttu-id="f16eb-112">如果整数文本在 `ulong` 范围之外（即，如果它小于 <xref:System.UInt64.MinValue?displayProperty=nameWithType> 或大于 <xref:System.UInt64.MaxValue?displayProperty=nameWithType>），会发生编译错误。</span><span class="sxs-lookup"><span data-stu-id="f16eb-112">If the integer literal is outside the range of `ulong` (that is, if it is less than <xref:System.UInt64.MinValue?displayProperty=nameWithType> or greater than <xref:System.UInt64.MaxValue?displayProperty=nameWithType>), a compilation error occurs.</span></span> 

<span data-ttu-id="f16eb-113">在以下示例中，表示为十进制、十六进制和二进制文本且等于 7,934,076,125 的整数被分配给 `ulong` 值。</span><span class="sxs-lookup"><span data-stu-id="f16eb-113">In the following example, integers equal to 7,934,076,125 that are represented as decimal, hexadecimal, and binary literals are assigned to `ulong` values.</span></span>  
  
[!code-csharp[ulong](../../../../samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#ULong)]  

> [!NOTE] 
> <span data-ttu-id="f16eb-114">使用前缀 `0x` 或 `0X` 表示十六进制文本，使用前缀 `0b` 或 `0B` 表示二进制文本。</span><span class="sxs-lookup"><span data-stu-id="f16eb-114">You use the prefix `0x` or `0X` to denote a hexadecimal literal and the prefix `0b` or `0B` to denote a binary literal.</span></span> <span data-ttu-id="f16eb-115">十进制文本没有前缀。</span><span class="sxs-lookup"><span data-stu-id="f16eb-115">Decimal literals have no prefix.</span></span> 

<span data-ttu-id="f16eb-116">从 C# 7.0 开始，添加了一些功能以增强可读性。</span><span class="sxs-lookup"><span data-stu-id="f16eb-116">Starting with C# 7.0, a couple of features have been added to enhance readability.</span></span> 
 - <span data-ttu-id="f16eb-117">C# 7.0 允许将下划线字符 (`_`) 用作数字分隔符。</span><span class="sxs-lookup"><span data-stu-id="f16eb-117">C# 7.0 allows the usage of the underscore character, `_`, as a digit separator.</span></span>
 - <span data-ttu-id="f16eb-118">C# 7.2 允许将 `_` 用作二进制或十六进制文本的数字分隔符，位于前缀之后。</span><span class="sxs-lookup"><span data-stu-id="f16eb-118">C# 7.2 allows `_` to be used as a digit separator for a binary or hexadecimal literal, after the prefix.</span></span> <span data-ttu-id="f16eb-119">十进制文本不能够有前导下划线。</span><span class="sxs-lookup"><span data-stu-id="f16eb-119">A decimal literal isn't permitted to have a leading underscore.</span></span>

<span data-ttu-id="f16eb-120">下面是一些示例。</span><span class="sxs-lookup"><span data-stu-id="f16eb-120">Some examples are shown below.</span></span>

[!code-csharp[long](../../../../samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#LongS)]  
 
 <span data-ttu-id="f16eb-121">整数文本还可包含表示类型的后缀。</span><span class="sxs-lookup"><span data-stu-id="f16eb-121">Integer literals can also include a suffix that denotes the type.</span></span> <span data-ttu-id="f16eb-122">后缀 `UL` 或 `ul` 将数字文本明确标识为 `ulong` 值。</span><span class="sxs-lookup"><span data-stu-id="f16eb-122">The suffix `UL` or `ul` unambiguously identifies a numeric literal as a `ulong` value.</span></span> <span data-ttu-id="f16eb-123">如果文本值超过 <xref:System.Int64.MaxValue?displayProperty=nameWithType>，则 `L` 后缀表示 `ulong`。</span><span class="sxs-lookup"><span data-stu-id="f16eb-123">The `L` suffix denotes a `ulong` if the literal value exceeds <xref:System.Int64.MaxValue?displayProperty=nameWithType>.</span></span> <span data-ttu-id="f16eb-124">如果文本值超过 <xref:System.UInt32.MaxValue?displayProperty=nameWithType>，则 `U` 或 `u` 后缀表示 `ulong`。</span><span class="sxs-lookup"><span data-stu-id="f16eb-124">And the `U` or `u` suffix denotes a `ulong` if the literal value exceeds <xref:System.UInt32.MaxValue?displayProperty=nameWithType>.</span></span> <span data-ttu-id="f16eb-125">以下示例使用 `ul` 后缀来表示长整型：</span><span class="sxs-lookup"><span data-stu-id="f16eb-125">The following example uses the `ul` suffix to denote a long integer:</span></span>
 
[!code-csharp[ulsuffix](../../../../samples/snippets/csharp/language-reference/keywords/numeric-suffixes.cs#2)]

<span data-ttu-id="f16eb-126">如果整数文本没有后缀，则其类型为以下类型中可表示其值的第一个类型：</span><span class="sxs-lookup"><span data-stu-id="f16eb-126">If an integer literal has no suffix, its type is the first of the following types in which its value can be represented:</span></span> 

1. [<span data-ttu-id="f16eb-127">int</span><span class="sxs-lookup"><span data-stu-id="f16eb-127">int</span></span>](int.md)
2. [<span data-ttu-id="f16eb-128">uint</span><span class="sxs-lookup"><span data-stu-id="f16eb-128">uint</span></span>](../../../csharp/language-reference/keywords/uint.md)
3. [<span data-ttu-id="f16eb-129">long</span><span class="sxs-lookup"><span data-stu-id="f16eb-129">long</span></span>](long.md)
4. `ulong`

## <a name="compiler-overload-resolution"></a><span data-ttu-id="f16eb-130">编译器重载解析</span><span class="sxs-lookup"><span data-stu-id="f16eb-130">Compiler overload resolution</span></span>
  
 <span data-ttu-id="f16eb-131">此后缀常用于调用重载方法。</span><span class="sxs-lookup"><span data-stu-id="f16eb-131">A common use of the suffix is with calling overloaded methods.</span></span> <span data-ttu-id="f16eb-132">以下面使用 `ulong` 和 [int](../../../csharp/language-reference/keywords/int.md) 参数的重载方法为例：</span><span class="sxs-lookup"><span data-stu-id="f16eb-132">Consider, for example, the following overloaded methods that use `ulong` and [int](../../../csharp/language-reference/keywords/int.md) parameters:</span></span>  
  
```csharp  
public static void SampleMethod(int i) {}  
public static void SampleMethod(ulong l) {}  
```  
  
 <span data-ttu-id="f16eb-133">在 `ulong` 参数后加上后缀可保证调用正确的类型，例如：</span><span class="sxs-lookup"><span data-stu-id="f16eb-133">Using a suffix with the `ulong` parameter guarantees that the correct type is called, for example:</span></span>  
  
```csharp  
SampleMethod(5);    // Calling the method with the int parameter  
SampleMethod(5UL);  // Calling the method with the ulong parameter  
```  
  
## <a name="conversions"></a><span data-ttu-id="f16eb-134">转换</span><span class="sxs-lookup"><span data-stu-id="f16eb-134">Conversions</span></span>  
 <span data-ttu-id="f16eb-135">存在从 `ulong` 到 [float](../../../csharp/language-reference/keywords/float.md)、[double](../../../csharp/language-reference/keywords/double.md) 或 [decimal](../../../csharp/language-reference/keywords/decimal.md) 的预定义隐式转换。</span><span class="sxs-lookup"><span data-stu-id="f16eb-135">There is a predefined implicit conversion from `ulong` to [float](../../../csharp/language-reference/keywords/float.md), [double](../../../csharp/language-reference/keywords/double.md), or [decimal](../../../csharp/language-reference/keywords/decimal.md).</span></span>  
  
 <span data-ttu-id="f16eb-136">不存在从 `ulong` 到任何整型的隐式转换。</span><span class="sxs-lookup"><span data-stu-id="f16eb-136">There is no implicit conversion from `ulong` to any integral type.</span></span> <span data-ttu-id="f16eb-137">例如，如果不使用显式强制转换，以下语句会生成编译错误：</span><span class="sxs-lookup"><span data-stu-id="f16eb-137">For example, the following statement will produce a compilation error without an explicit cast:</span></span>  
  
```csharp  
long long1 = 8UL;   // Error: no implicit conversion from ulong  
```  
  
 <span data-ttu-id="f16eb-138">存在从 [byte](../../../csharp/language-reference/keywords/byte.md)、[ushort](../../../csharp/language-reference/keywords/ushort.md)、[uint](../../../csharp/language-reference/keywords/uint.md) 或 [char](../../../csharp/language-reference/keywords/char.md) 到 `ulong` 的预定义隐式转换。</span><span class="sxs-lookup"><span data-stu-id="f16eb-138">There is a predefined implicit conversion from [byte](../../../csharp/language-reference/keywords/byte.md), [ushort](../../../csharp/language-reference/keywords/ushort.md), [uint](../../../csharp/language-reference/keywords/uint.md), or [char](../../../csharp/language-reference/keywords/char.md) to `ulong`.</span></span>  
  
 <span data-ttu-id="f16eb-139">此外，不存在从浮点类型到 `ulong` 类型的隐式转换。</span><span class="sxs-lookup"><span data-stu-id="f16eb-139">Also, there is no implicit conversion from floating-point types to `ulong`.</span></span> <span data-ttu-id="f16eb-140">例如，除非使用显式强制转换，否则以下语句将生成编译器错误：</span><span class="sxs-lookup"><span data-stu-id="f16eb-140">For example, the following statement generates a compiler error unless an explicit cast is used:</span></span>  
  
```csharp  
// Error -- no implicit conversion from double:  
ulong x = 3.0;  
// OK -- explicit conversion:  
ulong y = (ulong)3.0;    
```  
  
 <span data-ttu-id="f16eb-141">有关兼用浮点类型和整型类型的算术表达式的信息，请参阅 [float](../../../csharp/language-reference/keywords/float.md) 和 [double](../../../csharp/language-reference/keywords/double.md)。</span><span class="sxs-lookup"><span data-stu-id="f16eb-141">For information on arithmetic expressions with mixed floating-point types and integral types, see [float](../../../csharp/language-reference/keywords/float.md) and [double](../../../csharp/language-reference/keywords/double.md).</span></span>  
  
 <span data-ttu-id="f16eb-142">有关隐式数值转换规则的详细信息，请参阅[隐式数值转换表](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md)。</span><span class="sxs-lookup"><span data-stu-id="f16eb-142">For more information on implicit numeric conversion rules, see the [Implicit Numeric Conversions Table](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md).</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="f16eb-143">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="f16eb-143">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="f16eb-144">请参阅</span><span class="sxs-lookup"><span data-stu-id="f16eb-144">See Also</span></span>  
 <xref:System.UInt64>  
 [<span data-ttu-id="f16eb-145">C# 参考</span><span class="sxs-lookup"><span data-stu-id="f16eb-145">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="f16eb-146">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="f16eb-146">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="f16eb-147">C# 关键字</span><span class="sxs-lookup"><span data-stu-id="f16eb-147">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="f16eb-148">整型表</span><span class="sxs-lookup"><span data-stu-id="f16eb-148">Integral Types Table</span></span>](../../../csharp/language-reference/keywords/integral-types-table.md)  
 [<span data-ttu-id="f16eb-149">内置类型表</span><span class="sxs-lookup"><span data-stu-id="f16eb-149">Built-In Types Table</span></span>](../../../csharp/language-reference/keywords/built-in-types-table.md)  
 [<span data-ttu-id="f16eb-150">隐式数值转换表</span><span class="sxs-lookup"><span data-stu-id="f16eb-150">Implicit Numeric Conversions Table</span></span>](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md)  
 [<span data-ttu-id="f16eb-151">显式数值转换表</span><span class="sxs-lookup"><span data-stu-id="f16eb-151">Explicit Numeric Conversions Table</span></span>](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md)
