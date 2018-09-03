---
title: 显式数值转换表（C# 参考）
ms.date: 07/20/2015
helpviewer_keywords:
- conversions [C#], explicit numeric
- numeric conversions [C#], explicit
- explicit numeric conversion [C#]
- numeric data types [C#]
- types [C#], explicit numeric conversions
- type conversion [C#], explicit numeric
ms.assetid: f3bb9e76-6b92-4df7-bc36-f866c24e1dfd
ms.openlocfilehash: 5ca052dea4ee4abc866d2b02055188b0707499d4
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/03/2018
ms.locfileid: "43475928"
---
# <a name="explicit-numeric-conversions-table-c-reference"></a><span data-ttu-id="50289-102">显式数值转换表（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="50289-102">Explicit Numeric Conversions Table (C# Reference)</span></span>
<span data-ttu-id="50289-103">显式数值转换用于使用强制转换表达式将任何数值类型转换为任何其他数值类型，其中不存在任何隐式转换。</span><span class="sxs-lookup"><span data-stu-id="50289-103">Explicit numeric conversion is used to convert any numeric type to any other numeric type, for which there is no implicit conversion, by using a cast expression.</span></span> <span data-ttu-id="50289-104">下表显示了这些转换。</span><span class="sxs-lookup"><span data-stu-id="50289-104">The following table shows these conversions.</span></span>  
  
 <span data-ttu-id="50289-105">有关转换的详细信息，请参阅[强制转换和类型转换](../../../csharp/programming-guide/types/casting-and-type-conversions.md)。</span><span class="sxs-lookup"><span data-stu-id="50289-105">For more information about conversions, see [Casting and Type Conversions](../../../csharp/programming-guide/types/casting-and-type-conversions.md).</span></span>  
  
|<span data-ttu-id="50289-106">From</span><span class="sxs-lookup"><span data-stu-id="50289-106">From</span></span>|<span data-ttu-id="50289-107">到</span><span class="sxs-lookup"><span data-stu-id="50289-107">To</span></span>|  
|----------|--------|  
|[<span data-ttu-id="50289-108">sbyte</span><span class="sxs-lookup"><span data-stu-id="50289-108">sbyte</span></span>](../../../csharp/language-reference/keywords/sbyte.md)|<span data-ttu-id="50289-109">`byte`、`ushort`、`uint`、`ulong` 或 `char`</span><span class="sxs-lookup"><span data-stu-id="50289-109">`byte`, `ushort`, `uint`, `ulong`, or `char`</span></span>|  
|[<span data-ttu-id="50289-110">byte</span><span class="sxs-lookup"><span data-stu-id="50289-110">byte</span></span>](../../../csharp/language-reference/keywords/byte.md)|<span data-ttu-id="50289-111">`Sbyte` 或 `char`</span><span class="sxs-lookup"><span data-stu-id="50289-111">`Sbyte` or `char`</span></span>|  
|[<span data-ttu-id="50289-112">short</span><span class="sxs-lookup"><span data-stu-id="50289-112">short</span></span>](../../../csharp/language-reference/keywords/short.md)|<span data-ttu-id="50289-113">`sbyte`、`byte`、`ushort`、`uint`、`ulong` 或 `char`</span><span class="sxs-lookup"><span data-stu-id="50289-113">`sbyte`, `byte`, `ushort`, `uint`, `ulong`, or `char`</span></span>|  
|[<span data-ttu-id="50289-114">ushort</span><span class="sxs-lookup"><span data-stu-id="50289-114">ushort</span></span>](../../../csharp/language-reference/keywords/ushort.md)|<span data-ttu-id="50289-115">`sbyte`、`byte`、`short` 或 `char`</span><span class="sxs-lookup"><span data-stu-id="50289-115">`sbyte`, `byte`, `short`, or `char`</span></span>|  
|[<span data-ttu-id="50289-116">int</span><span class="sxs-lookup"><span data-stu-id="50289-116">int</span></span>](../../../csharp/language-reference/keywords/int.md)|<span data-ttu-id="50289-117">`sbyte`、`byte`、`short`、`ushort`、`uint`、`ulong` 或 `char`</span><span class="sxs-lookup"><span data-stu-id="50289-117">`sbyte`, `byte`, `short`, `ushort`, `uint`, `ulong`,or `char`</span></span>|  
|[<span data-ttu-id="50289-118">uint</span><span class="sxs-lookup"><span data-stu-id="50289-118">uint</span></span>](../../../csharp/language-reference/keywords/uint.md)|<span data-ttu-id="50289-119">`sbyte`、`byte`、`short`、`ushort`、`int` 或 `char`</span><span class="sxs-lookup"><span data-stu-id="50289-119">`sbyte`, `byte`, `short`, `ushort`, `int`, or `char`</span></span>|  
|[<span data-ttu-id="50289-120">long</span><span class="sxs-lookup"><span data-stu-id="50289-120">long</span></span>](../../../csharp/language-reference/keywords/long.md)|<span data-ttu-id="50289-121">`sbyte`、`byte`、`short`、`ushort`、`int`、`uint`、`ulong` 或 `char`</span><span class="sxs-lookup"><span data-stu-id="50289-121">`sbyte`, `byte`, `short`, `ushort`, `int`, `uint`, `ulong`, or `char`</span></span>|  
|[<span data-ttu-id="50289-122">ulong</span><span class="sxs-lookup"><span data-stu-id="50289-122">ulong</span></span>](../../../csharp/language-reference/keywords/ulong.md)|<span data-ttu-id="50289-123">`sbyte`、`byte`、`short`、`ushort`、`int`、`uint`、`long` 或 `char`</span><span class="sxs-lookup"><span data-stu-id="50289-123">`sbyte`, `byte`, `short`, `ushort`, `int`, `uint`, `long`, or `char`</span></span>|  
|[<span data-ttu-id="50289-124">char</span><span class="sxs-lookup"><span data-stu-id="50289-124">char</span></span>](../../../csharp/language-reference/keywords/char.md)|<span data-ttu-id="50289-125">`sbyte`、`byte` 或 `short`</span><span class="sxs-lookup"><span data-stu-id="50289-125">`sbyte`, `byte`, or `short`</span></span>|  
|[<span data-ttu-id="50289-126">float</span><span class="sxs-lookup"><span data-stu-id="50289-126">float</span></span>](../../../csharp/language-reference/keywords/float.md)|<span data-ttu-id="50289-127">`sbyte`、`byte`、`short`、`ushort`、`int`、`uint`、`long`、`ulong`、`char` 或 `decimal`</span><span class="sxs-lookup"><span data-stu-id="50289-127">`sbyte`, `byte`, `short`, `ushort`, `int`, `uint`, `long`, `ulong`, `char`,or `decimal`</span></span>|  
|[<span data-ttu-id="50289-128">double</span><span class="sxs-lookup"><span data-stu-id="50289-128">double</span></span>](../../../csharp/language-reference/keywords/double.md)|<span data-ttu-id="50289-129">`sbyte`、`byte`、`short`、`ushort`、`int`、`uint`、`long`、`ulong`、`char`、`float` 或 `decimal`</span><span class="sxs-lookup"><span data-stu-id="50289-129">`sbyte`, `byte`, `short`, `ushort`, `int`, `uint`, `long`, `ulong`, `char`, `float`,or `decimal`</span></span>|  
|[<span data-ttu-id="50289-130">decimal</span><span class="sxs-lookup"><span data-stu-id="50289-130">decimal</span></span>](../../../csharp/language-reference/keywords/decimal.md)|<span data-ttu-id="50289-131">`sbyte`、`byte`、`short`、`ushort`、`int`、`uint`、`long`、`ulong`、`char`、`float` 或 `double`</span><span class="sxs-lookup"><span data-stu-id="50289-131">`sbyte`, `byte`, `short`, `ushort`, `int`, `uint`, `long`, `ulong`, `char`, `float`, or `double`</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="50289-132">备注</span><span class="sxs-lookup"><span data-stu-id="50289-132">Remarks</span></span>  
  
-   <span data-ttu-id="50289-133">显式数值转换可能会导致精度降低或导致引发异常。</span><span class="sxs-lookup"><span data-stu-id="50289-133">The explicit numeric conversion may cause loss of precision or result in throwing exceptions.</span></span>  
  
-   <span data-ttu-id="50289-134">将 `decimal` 值转换为整型类型时，此值会向零舍入到最接近的整数值。</span><span class="sxs-lookup"><span data-stu-id="50289-134">When you convert a `decimal` value to an integral type, this value is rounded towards zero to the nearest integral value.</span></span> <span data-ttu-id="50289-135">如果生成的整数值处于目标类型的范围之外，则会引发 <xref:System.OverflowException>。</span><span class="sxs-lookup"><span data-stu-id="50289-135">If the resulting integral value is outside the range of the destination type, an <xref:System.OverflowException> is thrown.</span></span>  
  
-   <span data-ttu-id="50289-136">从 `double` 或 `float` 值转换为整型类型时，会截断该值。</span><span class="sxs-lookup"><span data-stu-id="50289-136">When you convert from a `double` or `float` value to an integral type, the value is truncated.</span></span> <span data-ttu-id="50289-137">如果生成的整数值处于目标值范围之外，则结果会取决于溢出检查上下文。</span><span class="sxs-lookup"><span data-stu-id="50289-137">If the resulting integral value is outside the range of the destination value, the result depends on the overflow checking context.</span></span> <span data-ttu-id="50289-138">在已检查的上下文中，引发 `OverflowException`；而在未检查的上下文中，结果是目标类型的未指定值。</span><span class="sxs-lookup"><span data-stu-id="50289-138">In a checked context, an `OverflowException` is thrown, while in an unchecked context, the result is an unspecified value of the destination type.</span></span>  
  
-   <span data-ttu-id="50289-139">将 `double` 转换为 `float` 时，`double` 值舍入为最接近的 `float` 值。</span><span class="sxs-lookup"><span data-stu-id="50289-139">When you convert `double` to `float`, the `double` value is rounded to the nearest `float` value.</span></span> <span data-ttu-id="50289-140">如果 `double` 值太小或太大，无法匹配目标类型，结果将为零或无穷大。</span><span class="sxs-lookup"><span data-stu-id="50289-140">If the `double` value is too small or too large to fit into the destination type, the result will be zero or infinity.</span></span>  
  
-   <span data-ttu-id="50289-141">将 `float` 或 `double` 转换为 `decimal` 时，源值转换为 `decimal` 表示形式，并并五入到第 28 位小数后最接近的数（如果需要）。</span><span class="sxs-lookup"><span data-stu-id="50289-141">When you convert `float` or `double` to `decimal`, the source value is converted to `decimal` representation and rounded to the nearest number after the 28th decimal place if required.</span></span> <span data-ttu-id="50289-142">根据源值的值，可能出现以下结果之一：</span><span class="sxs-lookup"><span data-stu-id="50289-142">Depending on the value of the source value, one of the following results may occur:</span></span>  
  
    -   <span data-ttu-id="50289-143">如果源值太小，无法表示为 `decimal`，结果则为零。</span><span class="sxs-lookup"><span data-stu-id="50289-143">If the source value is too small to be represented as a `decimal`, the result becomes zero.</span></span>  
  
    -   <span data-ttu-id="50289-144">如果源值为 NaN（非数值）、无穷大或太大而无法表示为 `decimal`，则引发 `OverflowException`。</span><span class="sxs-lookup"><span data-stu-id="50289-144">If the source value is NaN (not a number), infinity, or too large to be represented as a `decimal`, an `OverflowException` is thrown.</span></span>  
  
-   <span data-ttu-id="50289-145">将 `decimal` 转换为 `float` 或 `double` 时，`decimal` 值舍入到最接近的 `double` 或 `float` 值。</span><span class="sxs-lookup"><span data-stu-id="50289-145">When you convert `decimal` to `float` or `double`, the `decimal` value is rounded to the nearest `double` or `float` value.</span></span>  
  
 <span data-ttu-id="50289-146">有关显式转换的详细信息，请参阅 C# 语言规范中的显式。</span><span class="sxs-lookup"><span data-stu-id="50289-146">For more information on explicit conversion, see Explicit in the C# Language Specification.</span></span> <span data-ttu-id="50289-147">有关如何访问此规范的详细信息，请参阅 [C# 语言规范](../../../csharp/language-reference/language-specification/index.md)。</span><span class="sxs-lookup"><span data-stu-id="50289-147">For more information on how to access the spec, see [C# Language Specification](../../../csharp/language-reference/language-specification/index.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="50289-148">请参阅</span><span class="sxs-lookup"><span data-stu-id="50289-148">See Also</span></span>

- [<span data-ttu-id="50289-149">C# 参考</span><span class="sxs-lookup"><span data-stu-id="50289-149">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="50289-150">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="50289-150">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="50289-151">强制转换和类型转换</span><span class="sxs-lookup"><span data-stu-id="50289-151">Casting and Type Conversions</span></span>](../../../csharp/programming-guide/types/casting-and-type-conversions.md)  
- [<span data-ttu-id="50289-152">() 运算符</span><span class="sxs-lookup"><span data-stu-id="50289-152">() Operator</span></span>](../../../csharp/language-reference/operators/invocation-operator.md)  
- [<span data-ttu-id="50289-153">整型表</span><span class="sxs-lookup"><span data-stu-id="50289-153">Integral Types Table</span></span>](../../../csharp/language-reference/keywords/integral-types-table.md)  
- [<span data-ttu-id="50289-154">内置类型表</span><span class="sxs-lookup"><span data-stu-id="50289-154">Built-In Types Table</span></span>](../../../csharp/language-reference/keywords/built-in-types-table.md)  
- [<span data-ttu-id="50289-155">隐式数值转换表</span><span class="sxs-lookup"><span data-stu-id="50289-155">Implicit Numeric Conversions Table</span></span>](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md)
