---
title: 显式数值转换表（C# 参考）
ms.date: 09/06/2018
helpviewer_keywords:
- conversions [C#], explicit numeric
- numeric conversions [C#], explicit
- explicit numeric conversion [C#]
- numeric data types [C#]
- types [C#], explicit numeric conversions
- type conversion [C#], explicit numeric
ms.assetid: f3bb9e76-6b92-4df7-bc36-f866c24e1dfd
ms.openlocfilehash: 22bb2117e7b78596e1fb6af63584f51b066564c9
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/17/2018
ms.locfileid: "45594529"
---
# <a name="explicit-numeric-conversions-table-c-reference"></a><span data-ttu-id="c65a8-102">显式数值转换表（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="c65a8-102">Explicit numeric conversions table (C# Reference)</span></span>

<span data-ttu-id="c65a8-103">下表显示没有[隐式转换](implicit-numeric-conversions-table.md)的 .NET 数值类型之间的预定义显式转换。</span><span class="sxs-lookup"><span data-stu-id="c65a8-103">The following table shows the predefined explicit conversions between .NET numeric types for which there is no [implicit conversion](implicit-numeric-conversions-table.md).</span></span>

|<span data-ttu-id="c65a8-104">From</span><span class="sxs-lookup"><span data-stu-id="c65a8-104">From</span></span>|<span data-ttu-id="c65a8-105">到</span><span class="sxs-lookup"><span data-stu-id="c65a8-105">To</span></span>|  
|----------|--------|  
|[<span data-ttu-id="c65a8-106">sbyte</span><span class="sxs-lookup"><span data-stu-id="c65a8-106">sbyte</span></span>](sbyte.md)|<span data-ttu-id="c65a8-107">`byte`、`ushort`、`uint`、`ulong` 或 `char`</span><span class="sxs-lookup"><span data-stu-id="c65a8-107">`byte`, `ushort`, `uint`, `ulong`, or `char`</span></span>|  
|[<span data-ttu-id="c65a8-108">byte</span><span class="sxs-lookup"><span data-stu-id="c65a8-108">byte</span></span>](byte.md)|<span data-ttu-id="c65a8-109">`sbyte` 或 `char`</span><span class="sxs-lookup"><span data-stu-id="c65a8-109">`sbyte` or `char`</span></span>|  
|[<span data-ttu-id="c65a8-110">short</span><span class="sxs-lookup"><span data-stu-id="c65a8-110">short</span></span>](short.md)|<span data-ttu-id="c65a8-111">`sbyte`、`byte`、`ushort`、`uint`、`ulong` 或 `char`</span><span class="sxs-lookup"><span data-stu-id="c65a8-111">`sbyte`, `byte`, `ushort`, `uint`, `ulong`, or `char`</span></span>|  
|[<span data-ttu-id="c65a8-112">ushort</span><span class="sxs-lookup"><span data-stu-id="c65a8-112">ushort</span></span>](ushort.md)|<span data-ttu-id="c65a8-113">`sbyte`、`byte`、`short` 或 `char`</span><span class="sxs-lookup"><span data-stu-id="c65a8-113">`sbyte`, `byte`, `short`, or `char`</span></span>|  
|[<span data-ttu-id="c65a8-114">int</span><span class="sxs-lookup"><span data-stu-id="c65a8-114">int</span></span>](int.md)|<span data-ttu-id="c65a8-115">`sbyte`、`byte`、`short`、`ushort`、`uint`、`ulong` 或 `char`</span><span class="sxs-lookup"><span data-stu-id="c65a8-115">`sbyte`, `byte`, `short`, `ushort`, `uint`, `ulong`,or `char`</span></span>|  
|[<span data-ttu-id="c65a8-116">uint</span><span class="sxs-lookup"><span data-stu-id="c65a8-116">uint</span></span>](uint.md)|<span data-ttu-id="c65a8-117">`sbyte`、`byte`、`short`、`ushort`、`int` 或 `char`</span><span class="sxs-lookup"><span data-stu-id="c65a8-117">`sbyte`, `byte`, `short`, `ushort`, `int`, or `char`</span></span>|  
|[<span data-ttu-id="c65a8-118">long</span><span class="sxs-lookup"><span data-stu-id="c65a8-118">long</span></span>](long.md)|<span data-ttu-id="c65a8-119">`sbyte`、`byte`、`short`、`ushort`、`int`、`uint`、`ulong` 或 `char`</span><span class="sxs-lookup"><span data-stu-id="c65a8-119">`sbyte`, `byte`, `short`, `ushort`, `int`, `uint`, `ulong`, or `char`</span></span>|  
|[<span data-ttu-id="c65a8-120">ulong</span><span class="sxs-lookup"><span data-stu-id="c65a8-120">ulong</span></span>](ulong.md)|<span data-ttu-id="c65a8-121">`sbyte`、`byte`、`short`、`ushort`、`int`、`uint`、`long` 或 `char`</span><span class="sxs-lookup"><span data-stu-id="c65a8-121">`sbyte`, `byte`, `short`, `ushort`, `int`, `uint`, `long`, or `char`</span></span>|  
|[<span data-ttu-id="c65a8-122">char</span><span class="sxs-lookup"><span data-stu-id="c65a8-122">char</span></span>](char.md)|<span data-ttu-id="c65a8-123">`sbyte`、`byte` 或 `short`</span><span class="sxs-lookup"><span data-stu-id="c65a8-123">`sbyte`, `byte`, or `short`</span></span>|  
|[<span data-ttu-id="c65a8-124">float</span><span class="sxs-lookup"><span data-stu-id="c65a8-124">float</span></span>](float.md)|<span data-ttu-id="c65a8-125">`sbyte`、`byte`、`short`、`ushort`、`int`、`uint`、`long`、`ulong`、`char` 或 `decimal`</span><span class="sxs-lookup"><span data-stu-id="c65a8-125">`sbyte`, `byte`, `short`, `ushort`, `int`, `uint`, `long`, `ulong`, `char`,or `decimal`</span></span>|  
|[<span data-ttu-id="c65a8-126">double</span><span class="sxs-lookup"><span data-stu-id="c65a8-126">double</span></span>](double.md)|<span data-ttu-id="c65a8-127">`sbyte`、`byte`、`short`、`ushort`、`int`、`uint`、`long`、`ulong`、`char`、`float` 或 `decimal`</span><span class="sxs-lookup"><span data-stu-id="c65a8-127">`sbyte`, `byte`, `short`, `ushort`, `int`, `uint`, `long`, `ulong`, `char`, `float`,or `decimal`</span></span>|  
|[<span data-ttu-id="c65a8-128">decimal</span><span class="sxs-lookup"><span data-stu-id="c65a8-128">decimal</span></span>](decimal.md)|<span data-ttu-id="c65a8-129">`sbyte`、`byte`、`short`、`ushort`、`int`、`uint`、`long`、`ulong`、`char`、`float` 或 `double`</span><span class="sxs-lookup"><span data-stu-id="c65a8-129">`sbyte`, `byte`, `short`, `ushort`, `int`, `uint`, `long`, `ulong`, `char`, `float`, or `double`</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c65a8-130">备注</span><span class="sxs-lookup"><span data-stu-id="c65a8-130">Remarks</span></span>  
  
- <span data-ttu-id="c65a8-131">显式数值转换可能会导致精度降低或导致引发异常，通常为 <xref:System.OverflowException>。</span><span class="sxs-lookup"><span data-stu-id="c65a8-131">The explicit numeric conversion may cause loss of precision or result in throwing an exception, typically an <xref:System.OverflowException>.</span></span>  

- <span data-ttu-id="c65a8-132">将整数类型的值转换为另一个整数类型时，结果取决于溢出[检查上下文](checked-and-unchecked.md)。</span><span class="sxs-lookup"><span data-stu-id="c65a8-132">When you convert a value of an integral type to another integral type, the result depends on the overflow [checking context](checked-and-unchecked.md).</span></span> <span data-ttu-id="c65a8-133">在已检查的上下文中，如果源值在目标类型的范围内，则转换成功。</span><span class="sxs-lookup"><span data-stu-id="c65a8-133">In a checked context, the conversion succeeds if the source value is within the range of the destination type.</span></span> <span data-ttu-id="c65a8-134">否则会引发 <xref:System.OverflowException>。</span><span class="sxs-lookup"><span data-stu-id="c65a8-134">Otherwise, an <xref:System.OverflowException> is thrown.</span></span> <span data-ttu-id="c65a8-135">在未检查的上下文中，转换始终成功，并按如下方式进行：</span><span class="sxs-lookup"><span data-stu-id="c65a8-135">In an unchecked context, the conversion always succeeds, and proceeds as follows:</span></span>

  - <span data-ttu-id="c65a8-136">如果源类型大于目标类型，则通过放弃其“额外”最高有效位来截断源值。</span><span class="sxs-lookup"><span data-stu-id="c65a8-136">If the source type is larger than the destination type, then the source value is truncated by discarding its "extra" most significant bits.</span></span> <span data-ttu-id="c65a8-137">结果会被视为目标类型的值。</span><span class="sxs-lookup"><span data-stu-id="c65a8-137">The result is then treated as a value of the destination type.</span></span>

  - <span data-ttu-id="c65a8-138">如果源类型小于目标类型，则源值是符号扩展或零扩展，以使其与目标类型的大小相同。</span><span class="sxs-lookup"><span data-stu-id="c65a8-138">If the source type is smaller than the destination type, then the source value is either sign-extended or zero-extended so that it is the same size as the destination type.</span></span> <span data-ttu-id="c65a8-139">如果源类型带符号，则是符号扩展；如果源类型是无符号的，则是零扩展。</span><span class="sxs-lookup"><span data-stu-id="c65a8-139">Sign-extension is used if the source type is signed; zero-extension is used if the source type is unsigned.</span></span> <span data-ttu-id="c65a8-140">结果会被视为目标类型的值。</span><span class="sxs-lookup"><span data-stu-id="c65a8-140">The result is then treated as a value of the destination type.</span></span>

  - <span data-ttu-id="c65a8-141">如果源类型与目标类型的大小相同，则源值将被视为目标类型的值。</span><span class="sxs-lookup"><span data-stu-id="c65a8-141">If the source type is the same size as the destination type, then the source value is treated as a value of the destination type.</span></span>
  
- <span data-ttu-id="c65a8-142">将 `decimal` 值转换为整型类型时，此值会向零舍入到最接近的整数值。</span><span class="sxs-lookup"><span data-stu-id="c65a8-142">When you convert a `decimal` value to an integral type, this value is rounded towards zero to the nearest integral value.</span></span> <span data-ttu-id="c65a8-143">如果生成的整数值处于目标类型的范围之外，则会引发 <xref:System.OverflowException>。</span><span class="sxs-lookup"><span data-stu-id="c65a8-143">If the resulting integral value is outside the range of the destination type, an <xref:System.OverflowException> is thrown.</span></span>  
  
- <span data-ttu-id="c65a8-144">将 `double` 或 `float` 值转换为整型类型时，此值会向零舍入到最接近的整数值。</span><span class="sxs-lookup"><span data-stu-id="c65a8-144">When you convert a `double` or `float` value to an integral type, this value is rounded towards zero to the nearest integral value.</span></span> <span data-ttu-id="c65a8-145">如果生成的整数值处于目标类型范围之外，则结果会取决于溢出[上下文](checked-and-unchecked.md)。</span><span class="sxs-lookup"><span data-stu-id="c65a8-145">If the resulting integral value is outside the range of the destination type, the result depends on the overflow [checking context](checked-and-unchecked.md).</span></span> <span data-ttu-id="c65a8-146">在已检查的上下文中，引发 <xref:System.OverflowException>；而在未检查的上下文中，结果是目标类型的未指定值。</span><span class="sxs-lookup"><span data-stu-id="c65a8-146">In a checked context, an <xref:System.OverflowException> is thrown, while in an unchecked context, the result is an unspecified value of the destination type.</span></span>  
  
- <span data-ttu-id="c65a8-147">将 `double` 转换为 `float` 时，`double` 值舍入为最接近的 `float` 值。</span><span class="sxs-lookup"><span data-stu-id="c65a8-147">When you convert `double` to `float`, the `double` value is rounded to the nearest `float` value.</span></span> <span data-ttu-id="c65a8-148">如果 `double` 值太小或太大，无法匹配目标类型，结果将为零或无穷大。</span><span class="sxs-lookup"><span data-stu-id="c65a8-148">If the `double` value is too small or too large to fit into the destination type, the result will be zero or infinity.</span></span>  
  
- <span data-ttu-id="c65a8-149">将 `float` 或 `double` 转换为 `decimal` 时，源值转换为 `decimal` 表示形式，并并五入到第 28 位小数后最接近的数（如果需要）。</span><span class="sxs-lookup"><span data-stu-id="c65a8-149">When you convert `float` or `double` to `decimal`, the source value is converted to `decimal` representation and rounded to the nearest number after the 28th decimal place if required.</span></span> <span data-ttu-id="c65a8-150">根据源值的值，可能出现以下结果之一：</span><span class="sxs-lookup"><span data-stu-id="c65a8-150">Depending on the value of the source value, one of the following results may occur:</span></span>  

  - <span data-ttu-id="c65a8-151">如果源值太小，无法表示为 `decimal`，结果则为零。</span><span class="sxs-lookup"><span data-stu-id="c65a8-151">If the source value is too small to be represented as a `decimal`, the result becomes zero.</span></span>  

  - <span data-ttu-id="c65a8-152">如果源值为 NaN（非数值）、无穷大或太大而无法表示为 `decimal`，则引发 <xref:System.OverflowException>。</span><span class="sxs-lookup"><span data-stu-id="c65a8-152">If the source value is NaN (not a number), infinity, or too large to be represented as a `decimal`, an <xref:System.OverflowException> is thrown.</span></span>  
  
- <span data-ttu-id="c65a8-153">将 `decimal` 转换为 `float` 或 `double` 时，`decimal` 值舍入到最接近的 `double` 或 `float` 值。</span><span class="sxs-lookup"><span data-stu-id="c65a8-153">When you convert `decimal` to `float` or `double`, the `decimal` value is rounded to the nearest `double` or `float` value.</span></span>  
  
 <span data-ttu-id="c65a8-154">有关显式转换的详细信息，请参阅 [C# 语言规范](../language-specification/index.md)的[显式转换](/dotnet/csharp/language-reference/language-specification/conversions#explicit-conversions)章节。</span><span class="sxs-lookup"><span data-stu-id="c65a8-154">For more information about explicit conversions, see the [Explicit conversions](/dotnet/csharp/language-reference/language-specification/conversions#explicit-conversions) section of the [C# language specification](../language-specification/index.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="c65a8-155">请参阅</span><span class="sxs-lookup"><span data-stu-id="c65a8-155">See also</span></span>

- [<span data-ttu-id="c65a8-156">C# 参考</span><span class="sxs-lookup"><span data-stu-id="c65a8-156">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="c65a8-157">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="c65a8-157">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="c65a8-158">强制转换和类型转换</span><span class="sxs-lookup"><span data-stu-id="c65a8-158">Casting and type conversions</span></span>](../../programming-guide/types/casting-and-type-conversions.md)
- [<span data-ttu-id="c65a8-159">() 运算符</span><span class="sxs-lookup"><span data-stu-id="c65a8-159">() Operator</span></span>](../operators/invocation-operator.md)
- [<span data-ttu-id="c65a8-160">整型类型表</span><span class="sxs-lookup"><span data-stu-id="c65a8-160">Integral types table</span></span>](integral-types-table.md)
- [<span data-ttu-id="c65a8-161">浮点型表</span><span class="sxs-lookup"><span data-stu-id="c65a8-161">Floating-point types table</span></span>](floating-point-types-table.md)
- [<span data-ttu-id="c65a8-162">内置类型表</span><span class="sxs-lookup"><span data-stu-id="c65a8-162">Built-in types table</span></span>](built-in-types-table.md)
- [<span data-ttu-id="c65a8-163">隐式数值转换表</span><span class="sxs-lookup"><span data-stu-id="c65a8-163">Implicit numeric conversions table</span></span>](implicit-numeric-conversions-table.md)
