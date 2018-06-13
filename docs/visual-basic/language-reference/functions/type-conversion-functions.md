---
title: 类型转换函数 (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.CUShort
- vb.csng
- vb.CDate
- CByte
- CSng
- vb.CDec
- CBool
- CStr
- vb.CULng
- CDec
- CVErr
- CDbl
- CShort
- vb.CObj
- vb.CVErr
- CULng
- vb.cdbl
- vb.cbool
- CObj
- CDate
- CLng
- vb.cstr
- vb.cbyte
- vb.clng
- vb.CChar
- CUShort
- vb.CUInt
- vb.cint
- vb.CShort
- CInt
- CUInt
- CChar
helpviewer_keywords:
- CDate function
- CByte function
- Integer data type [Visual Basic], converting
- string conversion [Visual Basic], conversion functions
- fractions
- data types [Visual Basic], converting
- text, converting
- CDec function
- Char data type [Visual Basic], converting
- type conversion [Visual Basic], functions for
- Single data type [Visual Basic], converting
- numbers [Visual Basic], rounding
- rounding numbers [Visual Basic], type conversion
- CUShort function
- Long data type [Visual Basic], converting
- return values [Visual Basic], data types
- single-precision numbers [Visual Basic], converting
- data type conversion [Visual Basic], functions for
- CStr function
- times [Visual Basic], converting
- CSng function
- conversions [Visual Basic], type conversion functions
- CBool function
- CDbl function
- CUInt function
- Currency data type [Visual Basic], conversion functions
- numbers [Visual Basic], converting
- Double data type [Visual Basic], converting
- CLng function
- CSByte function
- double-precision numbers
- Decimal data type [Visual Basic], converting
- Boolean data type [Visual Basic], converting
- integers [Visual Basic], type conversion functions
- dates [Visual Basic], converting
- CULng function
- CInt function
- Date data type [Visual Basic], converting
- Byte data type [Visual Basic], converting
- String data type [Visual Basic], converting
- CChar function
- banker's rounding
- Short data type [Visual Basic], converting
- rounding numbers [Visual Basic], banker's rounding
- type conversion [Visual Basic], Visual Basic vs. .NET Framework
ms.assetid: d9d8d165-f967-44ff-a6cd-598e4740a99e
ms.openlocfilehash: c9222bdb31f4fd7c792d5a50c100067e29e9d537
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33605077"
---
# <a name="type-conversion-functions-visual-basic"></a><span data-ttu-id="bcd51-102">类型转换函数 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="bcd51-102">Type Conversion Functions (Visual Basic)</span></span>
<span data-ttu-id="bcd51-103">这些函数已编译的内联，这意味着转换代码，计算表达式的代码的一部分。</span><span class="sxs-lookup"><span data-stu-id="bcd51-103">These functions are compiled inline, meaning the conversion code is part of the code that evaluates the expression.</span></span> <span data-ttu-id="bcd51-104">有时是没有调用的过程，以完成转换，这将提高性能。</span><span class="sxs-lookup"><span data-stu-id="bcd51-104">Sometimes there is no call to a procedure to accomplish the conversion, which improves performance.</span></span> <span data-ttu-id="bcd51-105">每个函数都强制转换为特定数据类型的表达式。</span><span class="sxs-lookup"><span data-stu-id="bcd51-105">Each function coerces an expression to a specific data type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bcd51-106">语法</span><span class="sxs-lookup"><span data-stu-id="bcd51-106">Syntax</span></span>  
  
```  
CBool(expression)  
CByte(expression)  
CChar(expression)  
CDate(expression)  
CDbl(expression)  
CDec(expression)  
CInt(expression)  
CLng(expression)  
CObj(expression)  
CSByte(expression)  
CShort(expression)  
CSng(expression)  
CStr(expression)  
CUInt(expression)  
CULng(expression)  
CUShort(expression)  
```  
  
## <a name="part"></a><span data-ttu-id="bcd51-107">部件</span><span class="sxs-lookup"><span data-stu-id="bcd51-107">Part</span></span>  
 `expression`  
 <span data-ttu-id="bcd51-108">必须的。</span><span class="sxs-lookup"><span data-stu-id="bcd51-108">Required.</span></span> <span data-ttu-id="bcd51-109">源数据类型的任何表达式。</span><span class="sxs-lookup"><span data-stu-id="bcd51-109">Any expression of the source data type.</span></span>  
  
## <a name="return-value-data-type"></a><span data-ttu-id="bcd51-110">返回值的数据类型</span><span class="sxs-lookup"><span data-stu-id="bcd51-110">Return Value Data Type</span></span>  
 <span data-ttu-id="bcd51-111">下表中所示，函数名称将确定它返回的值的数据类型。</span><span class="sxs-lookup"><span data-stu-id="bcd51-111">The function name determines the data type of the value it returns, as shown in the following table.</span></span>  
  
|<span data-ttu-id="bcd51-112">函数名</span><span class="sxs-lookup"><span data-stu-id="bcd51-112">Function name</span></span>|<span data-ttu-id="bcd51-113">返回数据类型</span><span class="sxs-lookup"><span data-stu-id="bcd51-113">Return data type</span></span>|<span data-ttu-id="bcd51-114">范围`expression`自变量</span><span class="sxs-lookup"><span data-stu-id="bcd51-114">Range for `expression` argument</span></span>|  
|-------------------|----------------------|-------------------------------------|  
|`CBool`|[<span data-ttu-id="bcd51-115">Boolean 数据类型</span><span class="sxs-lookup"><span data-stu-id="bcd51-115">Boolean Data Type</span></span>](../../../visual-basic/language-reference/data-types/boolean-data-type.md)|<span data-ttu-id="bcd51-116">任何有效`Char`或`String`或数值表达式。</span><span class="sxs-lookup"><span data-stu-id="bcd51-116">Any valid `Char` or `String` or numeric expression.</span></span>|  
|`CByte`|[<span data-ttu-id="bcd51-117">Byte 数据类型</span><span class="sxs-lookup"><span data-stu-id="bcd51-117">Byte Data Type</span></span>](../../../visual-basic/language-reference/data-types/byte-data-type.md)|<span data-ttu-id="bcd51-118">0 到 255 （无符号）;小数部分舍入。<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="bcd51-118">0 through 255 (unsigned); fractional parts are rounded.<sup>1</sup></span></span>|  
|`CChar`|[<span data-ttu-id="bcd51-119">Char 数据类型</span><span class="sxs-lookup"><span data-stu-id="bcd51-119">Char Data Type</span></span>](../../../visual-basic/language-reference/data-types/char-data-type.md)|<span data-ttu-id="bcd51-120">任何有效`Char`或`String`表达式; 仅第一个字符的`String`转换; 值可以是 0 到 65535 （无符号）。</span><span class="sxs-lookup"><span data-stu-id="bcd51-120">Any valid `Char` or `String` expression; only first character of a `String` is converted; value can be 0 through 65535 (unsigned).</span></span>|  
|`CDate`|[<span data-ttu-id="bcd51-121">Date 数据类型</span><span class="sxs-lookup"><span data-stu-id="bcd51-121">Date Data Type</span></span>](../../../visual-basic/language-reference/data-types/date-data-type.md)|<span data-ttu-id="bcd51-122">任何有效的表示形式的日期和时间。</span><span class="sxs-lookup"><span data-stu-id="bcd51-122">Any valid representation of a date and time.</span></span>|  
|`CDbl`|[<span data-ttu-id="bcd51-123">Double 数据类型</span><span class="sxs-lookup"><span data-stu-id="bcd51-123">Double Data Type</span></span>](../../../visual-basic/language-reference/data-types/double-data-type.md)|<span data-ttu-id="bcd51-124">-1.79769313486231570 e + 308 到-4.94065645841246544 e-324 负值;最大 4.94065645841246544 e-324 到 1.79769313486231570 e + 308 的正值。</span><span class="sxs-lookup"><span data-stu-id="bcd51-124">-1.79769313486231570E+308 through -4.94065645841246544E-324 for negative values; 4.94065645841246544E-324 through 1.79769313486231570E+308 for positive values.</span></span>|  
|`CDec`|[<span data-ttu-id="bcd51-125">Decimal 数据类型</span><span class="sxs-lookup"><span data-stu-id="bcd51-125">Decimal Data Type</span></span>](../../../visual-basic/language-reference/data-types/decimal-data-type.md)|<span data-ttu-id="bcd51-126">+ /-79228162514264337593543950335 为零的数字，即，没有小数位的数字。</span><span class="sxs-lookup"><span data-stu-id="bcd51-126">+/-79,228,162,514,264,337,593,543,950,335 for zero-scaled numbers, that is, numbers with no decimal places.</span></span> <span data-ttu-id="bcd51-127">对于具有 28 位小数的数字，范围为 + /-7.9228162514264337593543950335。</span><span class="sxs-lookup"><span data-stu-id="bcd51-127">For numbers with 28 decimal places, the range is +/-7.9228162514264337593543950335.</span></span> <span data-ttu-id="bcd51-128">可能的最小的非零值数为 0.0000000000000000000000000001 （+ /-1E-28)。</span><span class="sxs-lookup"><span data-stu-id="bcd51-128">The smallest possible non-zero number is 0.0000000000000000000000000001 (+/-1E-28).</span></span>|  
|`CInt`|[<span data-ttu-id="bcd51-129">Integer 数据类型</span><span class="sxs-lookup"><span data-stu-id="bcd51-129">Integer Data Type</span></span>](../../../visual-basic/language-reference/data-types/integer-data-type.md)|<span data-ttu-id="bcd51-130">-2147483648 到 2147483647;小数部分舍入。<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="bcd51-130">-2,147,483,648 through 2,147,483,647; fractional parts are rounded.<sup>1</sup></span></span>|  
|`CLng`|[<span data-ttu-id="bcd51-131">Long 数据类型</span><span class="sxs-lookup"><span data-stu-id="bcd51-131">Long Data Type</span></span>](../../../visual-basic/language-reference/data-types/long-data-type.md)|<span data-ttu-id="bcd51-132">-9223372036854775808 到 9223372036854775807;小数部分舍入。<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="bcd51-132">-9,223,372,036,854,775,808 through 9,223,372,036,854,775,807; fractional parts are rounded.<sup>1</sup></span></span>|  
|`CObj`|[<span data-ttu-id="bcd51-133">Object 数据类型</span><span class="sxs-lookup"><span data-stu-id="bcd51-133">Object Data Type</span></span>](../../../visual-basic/language-reference/data-types/object-data-type.md)|<span data-ttu-id="bcd51-134">任何有效表达式。</span><span class="sxs-lookup"><span data-stu-id="bcd51-134">Any valid expression.</span></span>|  
|`CSByte`|[<span data-ttu-id="bcd51-135">SByte 数据类型</span><span class="sxs-lookup"><span data-stu-id="bcd51-135">SByte Data Type</span></span>](../../../visual-basic/language-reference/data-types/sbyte-data-type.md)|<span data-ttu-id="bcd51-136">-128 到 127;小数部分舍入。<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="bcd51-136">-128 through 127; fractional parts are rounded.<sup>1</sup></span></span>|  
|`CShort`|[<span data-ttu-id="bcd51-137">Short 数据类型</span><span class="sxs-lookup"><span data-stu-id="bcd51-137">Short Data Type</span></span>](../../../visual-basic/language-reference/data-types/short-data-type.md)|<span data-ttu-id="bcd51-138">-32768 到 32767;小数部分舍入。<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="bcd51-138">-32,768 through 32,767; fractional parts are rounded.<sup>1</sup></span></span>|  
|`CSng`|[<span data-ttu-id="bcd51-139">Single 数据类型</span><span class="sxs-lookup"><span data-stu-id="bcd51-139">Single Data Type</span></span>](../../../visual-basic/language-reference/data-types/single-data-type.md)|<span data-ttu-id="bcd51-140">-3.402823 e + 38 到-1.401298 e-45 负值;1.401298 e-3.402823 e + 38 正值通过 45。</span><span class="sxs-lookup"><span data-stu-id="bcd51-140">-3.402823E+38 through -1.401298E-45 for negative values; 1.401298E-45 through 3.402823E+38 for positive values.</span></span>|  
|`CStr`|[<span data-ttu-id="bcd51-141">String 数据类型</span><span class="sxs-lookup"><span data-stu-id="bcd51-141">String Data Type</span></span>](../../../visual-basic/language-reference/data-types/string-data-type.md)|<span data-ttu-id="bcd51-142">返回`CStr`依赖于`expression`自变量。</span><span class="sxs-lookup"><span data-stu-id="bcd51-142">Returns for `CStr` depend on the `expression` argument.</span></span> <span data-ttu-id="bcd51-143">请参阅[CStr 函数的返回值](../../../visual-basic/language-reference/functions/return-values-for-the-cstr-function.md)。</span><span class="sxs-lookup"><span data-stu-id="bcd51-143">See [Return Values for the CStr Function](../../../visual-basic/language-reference/functions/return-values-for-the-cstr-function.md).</span></span>|  
|`CUInt`|[<span data-ttu-id="bcd51-144">UInteger 数据类型</span><span class="sxs-lookup"><span data-stu-id="bcd51-144">UInteger Data Type</span></span>](../../../visual-basic/language-reference/data-types/uinteger-data-type.md)|<span data-ttu-id="bcd51-145">0 到 4294967295 （无符号）;小数部分舍入。<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="bcd51-145">0 through 4,294,967,295 (unsigned); fractional parts are rounded.<sup>1</sup></span></span>|  
|`CULng`|[<span data-ttu-id="bcd51-146">ULong 数据类型</span><span class="sxs-lookup"><span data-stu-id="bcd51-146">ULong Data Type</span></span>](../../../visual-basic/language-reference/data-types/ulong-data-type.md)|<span data-ttu-id="bcd51-147">0 到 18446744073709551615 （无符号）;小数部分舍入。<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="bcd51-147">0 through 18,446,744,073,709,551,615 (unsigned); fractional parts are rounded.<sup>1</sup></span></span>|  
|`CUShort`|[<span data-ttu-id="bcd51-148">UShort 数据类型</span><span class="sxs-lookup"><span data-stu-id="bcd51-148">UShort Data Type</span></span>](../../../visual-basic/language-reference/data-types/ushort-data-type.md)|<span data-ttu-id="bcd51-149">0 到 65535 （无符号）;小数部分舍入。<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="bcd51-149">0 through 65,535 (unsigned); fractional parts are rounded.<sup>1</sup></span></span>|  
  
 <span data-ttu-id="bcd51-150"><sup>1</sup>小数部分时可能会出现一个特殊类型的舍入调用*银行家舍入法*。</span><span class="sxs-lookup"><span data-stu-id="bcd51-150"><sup>1</sup> Fractional parts can be subject to a special type of rounding called *banker's rounding*.</span></span> <span data-ttu-id="bcd51-151">有关详细信息，请参阅"备注"。</span><span class="sxs-lookup"><span data-stu-id="bcd51-151">See "Remarks" for more information.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bcd51-152">备注</span><span class="sxs-lookup"><span data-stu-id="bcd51-152">Remarks</span></span>  
 <span data-ttu-id="bcd51-153">一般来说，你应使用 Visual Basic 的类型转换函数的.NET Framework 方法优先如`ToString()`上,<xref:System.Convert>类或单个类型结构或类上。</span><span class="sxs-lookup"><span data-stu-id="bcd51-153">As a rule, you should use the Visual Basic type conversion functions in preference to the .NET Framework methods such as `ToString()`, either on the <xref:System.Convert> class or on an individual type structure or class.</span></span> <span data-ttu-id="bcd51-154">Visual Basic 函数旨在用于与 Visual Basic 代码的最佳交互，并且它们还使你更短且更易读的源代码。</span><span class="sxs-lookup"><span data-stu-id="bcd51-154">The Visual Basic functions are designed for optimal interaction with Visual Basic code, and they also make your source code shorter and easier to read.</span></span> <span data-ttu-id="bcd51-155">此外，.NET Framework 的转换方法不始终生成与 Visual Basic 函数，例如转换时相同的结果`Boolean`到`Integer`。</span><span class="sxs-lookup"><span data-stu-id="bcd51-155">In addition, the .NET Framework conversion methods do not always produce the same results as the Visual Basic functions, for example when converting `Boolean` to `Integer`.</span></span> <span data-ttu-id="bcd51-156">有关详细信息，请参阅[故障排除数据类型](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)。</span><span class="sxs-lookup"><span data-stu-id="bcd51-156">For more information, see [Troubleshooting Data Types](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md).</span></span>  
  
## <a name="behavior"></a><span data-ttu-id="bcd51-157">行为</span><span class="sxs-lookup"><span data-stu-id="bcd51-157">Behavior</span></span>  
  
-   <span data-ttu-id="bcd51-158">**强制。**</span><span class="sxs-lookup"><span data-stu-id="bcd51-158">**Coercion.**</span></span> <span data-ttu-id="bcd51-159">通常情况下，你可以使用数据类型转换函数要强制转换到特定的数据类型，而不是默认数据类型的操作的结果。</span><span class="sxs-lookup"><span data-stu-id="bcd51-159">In general, you can use the data type conversion functions to coerce the result of an operation to a particular data type rather than the default data type.</span></span> <span data-ttu-id="bcd51-160">例如，使用`CDec`强制执行在其中单精度、 双精度或整数算术将要通常发生的情况下的小数运算。</span><span class="sxs-lookup"><span data-stu-id="bcd51-160">For example, use `CDec` to force decimal arithmetic in cases where single-precision, double-precision, or integer arithmetic would normally take place.</span></span>  
  
-   <span data-ttu-id="bcd51-161">**失败的转换。**</span><span class="sxs-lookup"><span data-stu-id="bcd51-161">**Failed Conversions.**</span></span> <span data-ttu-id="bcd51-162">如果`expression`传递给函数是外部的数据类型范围它是要转换<xref:System.OverflowException>时发生。</span><span class="sxs-lookup"><span data-stu-id="bcd51-162">If the `expression` passed to the function is outside the range of the data type to which it is to be converted, an <xref:System.OverflowException> occurs.</span></span>  
  
-   <span data-ttu-id="bcd51-163">**小数部分。**</span><span class="sxs-lookup"><span data-stu-id="bcd51-163">**Fractional Parts.**</span></span> <span data-ttu-id="bcd51-164">当将非整型的值转换为整数类型，整数转换函数 (`CByte`， `CInt`， `CLng`， `CSByte`， `CShort`， `CUInt`， `CULng`，和`CUShort`) 删除小数部分和舍入到最接近的整数值。</span><span class="sxs-lookup"><span data-stu-id="bcd51-164">When you convert a nonintegral value to an integral type, the integer conversion functions (`CByte`, `CInt`, `CLng`, `CSByte`, `CShort`, `CUInt`, `CULng`, and `CUShort`) remove the fractional part and round the value to the closest integer.</span></span>  
  
     <span data-ttu-id="bcd51-165">如果小数部分正好是 0.5，整数转换函数其舍入为接近的偶数整数。</span><span class="sxs-lookup"><span data-stu-id="bcd51-165">If the fractional part is exactly 0.5, the integer conversion functions round it to the nearest even integer.</span></span> <span data-ttu-id="bcd51-166">例如，0.5 舍入为 0，1.5 和 2.5 舍入为 2。</span><span class="sxs-lookup"><span data-stu-id="bcd51-166">For example, 0.5 rounds to 0, and 1.5 and 2.5 both round to 2.</span></span> <span data-ttu-id="bcd51-167">这有时称为*银行家舍入法*，，其目的在于补偿时同时添加许多这样的数字可能会累积的偏差。</span><span class="sxs-lookup"><span data-stu-id="bcd51-167">This is sometimes called *banker's rounding*, and its purpose is to compensate for a bias that could accumulate when adding many such numbers together.</span></span>  
  
     <span data-ttu-id="bcd51-168">`CInt` 和`CLng`与不同<xref:Microsoft.VisualBasic.Conversion.Int%2A>和<xref:Microsoft.VisualBasic.Conversion.Fix%2A>函数，它截断，而不是舍入，大量的小数部分。</span><span class="sxs-lookup"><span data-stu-id="bcd51-168">`CInt` and `CLng` differ from the <xref:Microsoft.VisualBasic.Conversion.Int%2A> and <xref:Microsoft.VisualBasic.Conversion.Fix%2A> functions, which truncate, rather than round, the fractional part of a number.</span></span> <span data-ttu-id="bcd51-169">此外，`Fix`和`Int`始终返回相同的数据类型的值，当你在通过。</span><span class="sxs-lookup"><span data-stu-id="bcd51-169">Also, `Fix` and `Int` always return a value of the same data type as you pass in.</span></span>  
  
-   <span data-ttu-id="bcd51-170">**日期/时间转换。**</span><span class="sxs-lookup"><span data-stu-id="bcd51-170">**Date/Time Conversions.**</span></span> <span data-ttu-id="bcd51-171">使用<xref:Microsoft.VisualBasic.Information.IsDate%2A>函数来确定是否可以将一个值转换为日期和时间。</span><span class="sxs-lookup"><span data-stu-id="bcd51-171">Use the <xref:Microsoft.VisualBasic.Information.IsDate%2A> function to determine if a value can be converted to a date and time.</span></span> <span data-ttu-id="bcd51-172">`CDate` 识别的日期文本和时间文本，但不是数值。</span><span class="sxs-lookup"><span data-stu-id="bcd51-172">`CDate` recognizes date literals and time literals but not numeric values.</span></span> <span data-ttu-id="bcd51-173">要转换 Visual Basic 6.0`Date`值赋给`Date`在 Visual Basic 2005 中的值或更高版本，你可以使用<xref:System.DateTime.FromOADate%2A?displayProperty=nameWithType>方法。</span><span class="sxs-lookup"><span data-stu-id="bcd51-173">To convert a Visual Basic 6.0 `Date` value to a `Date` value in Visual Basic 2005 or later versions, you can use the <xref:System.DateTime.FromOADate%2A?displayProperty=nameWithType> method.</span></span>  
  
-   <span data-ttu-id="bcd51-174">**非特定日期/时间值。**</span><span class="sxs-lookup"><span data-stu-id="bcd51-174">**Neutral Date/Time Values.**</span></span> <span data-ttu-id="bcd51-175">[日期数据类型](../../../visual-basic/language-reference/data-types/date-data-type.md)始终包含日期和时间信息。</span><span class="sxs-lookup"><span data-stu-id="bcd51-175">The [Date Data Type](../../../visual-basic/language-reference/data-types/date-data-type.md) always contains both date and time information.</span></span> <span data-ttu-id="bcd51-176">为进行类型转换，Visual Basic 将将 1/1/0001 (年 1 月 1 年 1) 对要*中性值*次要非特定值的日期，和 00:00:00 （午夜）。</span><span class="sxs-lookup"><span data-stu-id="bcd51-176">For purposes of type conversion, Visual Basic considers 1/1/0001 (January 1 of the year 1) to be a *neutral value* for the date, and 00:00:00 (midnight) to be a neutral value for the time.</span></span> <span data-ttu-id="bcd51-177">如果你转换`Date`值为一个字符串，`CStr`不结果字符串中包括非特定值。</span><span class="sxs-lookup"><span data-stu-id="bcd51-177">If you convert a `Date` value to a string, `CStr` does not include neutral values in the resulting string.</span></span> <span data-ttu-id="bcd51-178">例如，如果你转换`#January 1, 0001 9:30:00#`为一个字符串，结果是"9:30:00 AM"; 取消显示的日期信息。</span><span class="sxs-lookup"><span data-stu-id="bcd51-178">For example, if you convert `#January 1, 0001 9:30:00#` to a string, the result is "9:30:00 AM"; the date information is suppressed.</span></span> <span data-ttu-id="bcd51-179">但是，日期信息是仍然存在于原始`Date`值，并可以使用函数如恢复<xref:Microsoft.VisualBasic.DateAndTime.DatePart%2A>函数。</span><span class="sxs-lookup"><span data-stu-id="bcd51-179">However, the date information is still present in the original `Date` value and can be recovered with functions such as <xref:Microsoft.VisualBasic.DateAndTime.DatePart%2A> function.</span></span>  
  
-   <span data-ttu-id="bcd51-180">**区域性的敏感性。**</span><span class="sxs-lookup"><span data-stu-id="bcd51-180">**Culture Sensitivity.**</span></span> <span data-ttu-id="bcd51-181">涉及到字符串的类型转换函数执行基于应用程序的当前区域性设置的转换。</span><span class="sxs-lookup"><span data-stu-id="bcd51-181">The type conversion functions involving strings perform conversions based on the current culture settings for the application.</span></span> <span data-ttu-id="bcd51-182">例如，`CDate`识别根据你的系统区域设置的日期格式。</span><span class="sxs-lookup"><span data-stu-id="bcd51-182">For example, `CDate` recognizes date formats according to the locale setting of your system.</span></span> <span data-ttu-id="bcd51-183">你必须提供日、 月和年正确顺序为你的区域设置，或可能不正确解释日期。</span><span class="sxs-lookup"><span data-stu-id="bcd51-183">You must provide the day, month, and year in the correct order for your locale, or the date might not be interpreted correctly.</span></span> <span data-ttu-id="bcd51-184">如果它包含一个星期的字符串，例如"Wednesday"无法识别的长日期格式。</span><span class="sxs-lookup"><span data-stu-id="bcd51-184">A long date format is not recognized if it contains a day-of-the-week string, such as "Wednesday".</span></span>  
  
     <span data-ttu-id="bcd51-185">如果你需要将转换为或从的字符串表示形式的格式不是由你的区域设置中的值，你无法使用 Visual Basic 的类型转换函数。</span><span class="sxs-lookup"><span data-stu-id="bcd51-185">If you need to convert to or from a string representation of a value in a format other than the one specified by your locale, you cannot use the Visual Basic type conversion functions.</span></span> <span data-ttu-id="bcd51-186">若要执行此操作，使用`ToString(IFormatProvider)`和`Parse(String, IFormatProvider)`该值的类型的方法。</span><span class="sxs-lookup"><span data-stu-id="bcd51-186">To do this, use the `ToString(IFormatProvider)` and `Parse(String, IFormatProvider)` methods of that value's type.</span></span> <span data-ttu-id="bcd51-187">例如，使用<xref:System.Double.Parse%2A?displayProperty=nameWithType>时将字符串转换`Double`，并使用<xref:System.Double.ToString%2A?displayProperty=nameWithType>转换类型的值时`Double`为字符串。</span><span class="sxs-lookup"><span data-stu-id="bcd51-187">For example, use <xref:System.Double.Parse%2A?displayProperty=nameWithType> when converting a string to a `Double`, and use <xref:System.Double.ToString%2A?displayProperty=nameWithType> when converting a value of type `Double` to a string.</span></span>  
  
## <a name="ctype-function"></a><span data-ttu-id="bcd51-188">CType Function</span><span class="sxs-lookup"><span data-stu-id="bcd51-188">CType Function</span></span>  
 <span data-ttu-id="bcd51-189">[CType 函数](../../../visual-basic/language-reference/functions/ctype-function.md)采用第二个自变量， `typename`，并将强制转换`expression`到`typename`，其中`typename`可以是任何数据类型、 结构、 类或接口到存在的有效转换。</span><span class="sxs-lookup"><span data-stu-id="bcd51-189">The [CType Function](../../../visual-basic/language-reference/functions/ctype-function.md) takes a second argument, `typename`, and coerces `expression` to `typename`, where `typename` can be any data type, structure, class, or interface to which there exists a valid conversion.</span></span>  
  
 <span data-ttu-id="bcd51-190">有关的比较`CType`与其他类型转换关键字，请参阅[DirectCast 运算符](../../../visual-basic/language-reference/operators/directcast-operator.md)和[TryCast 运算符](../../../visual-basic/language-reference/operators/trycast-operator.md)。</span><span class="sxs-lookup"><span data-stu-id="bcd51-190">For a comparison of `CType` with the other type conversion keywords, see [DirectCast Operator](../../../visual-basic/language-reference/operators/directcast-operator.md) and [TryCast Operator](../../../visual-basic/language-reference/operators/trycast-operator.md).</span></span>  
  
## <a name="cbool-example"></a><span data-ttu-id="bcd51-191">CBool 示例</span><span class="sxs-lookup"><span data-stu-id="bcd51-191">CBool Example</span></span>  
 <span data-ttu-id="bcd51-192">下面的示例使用`CBool`函数将表达式转换为`Boolean`值。</span><span class="sxs-lookup"><span data-stu-id="bcd51-192">The following example uses the `CBool` function to convert expressions to `Boolean` values.</span></span> <span data-ttu-id="bcd51-193">如果表达式计算结果为非零值，`CBool`返回`True`; 否则为它将返回`False`。</span><span class="sxs-lookup"><span data-stu-id="bcd51-193">If an expression evaluates to a nonzero value, `CBool` returns `True`; otherwise, it returns `False`.</span></span>  
  
 [!code-vb[VbVbalrFunctions#1](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/type-conversion-functions_1.vb)]  
  
## <a name="cbyte-example"></a><span data-ttu-id="bcd51-194">CByte 示例</span><span class="sxs-lookup"><span data-stu-id="bcd51-194">CByte Example</span></span>  
 <span data-ttu-id="bcd51-195">下面的示例使用`CByte`函数可将对表达式`Byte`。</span><span class="sxs-lookup"><span data-stu-id="bcd51-195">The following example uses the `CByte` function to convert an expression to a `Byte`.</span></span>  
  
 [!code-vb[VbVbalrFunctions#2](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/type-conversion-functions_2.vb)]  
  
## <a name="cchar-example"></a><span data-ttu-id="bcd51-196">CChar 示例</span><span class="sxs-lookup"><span data-stu-id="bcd51-196">CChar Example</span></span>  
 <span data-ttu-id="bcd51-197">下面的示例使用`CChar`函数将转换的第一个字符`String`表达式`Char`类型。</span><span class="sxs-lookup"><span data-stu-id="bcd51-197">The following example uses the `CChar` function to convert the first character of a `String` expression to a `Char` type.</span></span>  
  
 [!code-vb[VbVbalrFunctions#3](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/type-conversion-functions_3.vb)]  
  
 <span data-ttu-id="bcd51-198">输入自变量到`CChar`的数据类型必须为`Char`或`String`。</span><span class="sxs-lookup"><span data-stu-id="bcd51-198">The input argument to `CChar` must be of data type `Char` or `String`.</span></span> <span data-ttu-id="bcd51-199">不能使用`CChar`将数字转换为字符，因为`CChar`不能接受数值数据类型。</span><span class="sxs-lookup"><span data-stu-id="bcd51-199">You cannot use `CChar` to convert a number to a character, because `CChar` cannot accept a numeric data type.</span></span> <span data-ttu-id="bcd51-200">下面的示例获取表示的代码点 （字符代码） 的数字，并将其转换为对应的字符。</span><span class="sxs-lookup"><span data-stu-id="bcd51-200">The following example obtains a number representing a code point (character code) and converts it to the corresponding character.</span></span> <span data-ttu-id="bcd51-201">它使用<xref:Microsoft.VisualBasic.Interaction.InputBox%2A>函数来获取的数字，字符串`CInt`要转换的字符串类型`Integer`，和`ChrW`要转换的编号，以键入`Char`。</span><span class="sxs-lookup"><span data-stu-id="bcd51-201">It uses the <xref:Microsoft.VisualBasic.Interaction.InputBox%2A> function to obtain the string of digits, `CInt` to convert the string to type `Integer`, and `ChrW` to convert the number to type `Char`.</span></span>  
  
 [!code-vb[VbVbalrFunctions#4](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/type-conversion-functions_4.vb)]  
  
## <a name="cdate-example"></a><span data-ttu-id="bcd51-202">CDate 示例</span><span class="sxs-lookup"><span data-stu-id="bcd51-202">CDate Example</span></span>  
 <span data-ttu-id="bcd51-203">下面的示例使用`CDate`函数将字符串转换为`Date`值。</span><span class="sxs-lookup"><span data-stu-id="bcd51-203">The following example uses the `CDate` function to convert strings to `Date` values.</span></span> <span data-ttu-id="bcd51-204">一般情况下，不建议硬编码的日期和时间作为字符串 （如本示例中所示）。</span><span class="sxs-lookup"><span data-stu-id="bcd51-204">In general, hard-coding dates and times as strings (as shown in this example) is not recommended.</span></span> <span data-ttu-id="bcd51-205">使用日期文本和时间的文本，如 #Feb 12，1969 # 和 # 4:45:23 PM #，而是。</span><span class="sxs-lookup"><span data-stu-id="bcd51-205">Use date literals and time literals, such as #Feb 12, 1969# and #4:45:23 PM#, instead.</span></span>  
  
 [!code-vb[VbVbalrFunctions#5](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/type-conversion-functions_5.vb)]  
  
## <a name="cdbl-example"></a><span data-ttu-id="bcd51-206">CDbl 示例</span><span class="sxs-lookup"><span data-stu-id="bcd51-206">CDbl Example</span></span>  
 [!code-vb[VbVbalrFunctions#6](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/type-conversion-functions_6.vb)]  
  
## <a name="cdec-example"></a><span data-ttu-id="bcd51-207">CDec 示例</span><span class="sxs-lookup"><span data-stu-id="bcd51-207">CDec Example</span></span>  
 <span data-ttu-id="bcd51-208">下面的示例使用`CDec`函数将转换为数字值`Decimal`。</span><span class="sxs-lookup"><span data-stu-id="bcd51-208">The following example uses the `CDec` function to convert a numeric value to `Decimal`.</span></span>  
  
 [!code-vb[VbVbalrFunctions#7](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/type-conversion-functions_7.vb)]  
  
## <a name="cint-example"></a><span data-ttu-id="bcd51-209">CInt 示例</span><span class="sxs-lookup"><span data-stu-id="bcd51-209">CInt Example</span></span>  
 <span data-ttu-id="bcd51-210">下面的示例使用`CInt`函数将值转换为`Integer`。</span><span class="sxs-lookup"><span data-stu-id="bcd51-210">The following example uses the `CInt` function to convert a value to `Integer`.</span></span>  
  
 [!code-vb[VbVbalrFunctions#8](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/type-conversion-functions_8.vb)]  
  
## <a name="clng-example"></a><span data-ttu-id="bcd51-211">CLng 示例</span><span class="sxs-lookup"><span data-stu-id="bcd51-211">CLng Example</span></span>  
 <span data-ttu-id="bcd51-212">下面的示例使用`CLng`函数以将值转换为`Long`。</span><span class="sxs-lookup"><span data-stu-id="bcd51-212">The following example uses the `CLng` function to convert values to `Long`.</span></span>  
  
 [!code-vb[VbVbalrFunctions#9](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/type-conversion-functions_9.vb)]  
  
## <a name="cobj-example"></a><span data-ttu-id="bcd51-213">使用 CObj 示例</span><span class="sxs-lookup"><span data-stu-id="bcd51-213">CObj Example</span></span>  
 <span data-ttu-id="bcd51-214">下面的示例使用`CObj`函数将转换为数字值`Object`。</span><span class="sxs-lookup"><span data-stu-id="bcd51-214">The following example uses the `CObj` function to convert a numeric value to `Object`.</span></span> <span data-ttu-id="bcd51-215">`Object`变量本身包含仅一个四个字节的指针，用于指向`Double`分配给它的值。</span><span class="sxs-lookup"><span data-stu-id="bcd51-215">The `Object` variable itself contains only a four-byte pointer, which points to the `Double` value assigned to it.</span></span>  
  
 [!code-vb[VbVbalrFunctions#10](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/type-conversion-functions_10.vb)]  
  
## <a name="csbyte-example"></a><span data-ttu-id="bcd51-216">CSByte 示例</span><span class="sxs-lookup"><span data-stu-id="bcd51-216">CSByte Example</span></span>  
 <span data-ttu-id="bcd51-217">下面的示例使用`CSByte`函数将转换为数字值`SByte`。</span><span class="sxs-lookup"><span data-stu-id="bcd51-217">The following example uses the `CSByte` function to convert a numeric value to `SByte`.</span></span>  
  
 [!code-vb[VbVbalrFunctions#11](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/type-conversion-functions_11.vb)]  
  
## <a name="cshort-example"></a><span data-ttu-id="bcd51-218">CShort 示例</span><span class="sxs-lookup"><span data-stu-id="bcd51-218">CShort Example</span></span>  
 <span data-ttu-id="bcd51-219">下面的示例使用`CShort`函数将转换为数字值`Short`。</span><span class="sxs-lookup"><span data-stu-id="bcd51-219">The following example uses the `CShort` function to convert a numeric value to `Short`.</span></span>  
  
 [!code-vb[VbVbalrFunctions#12](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/type-conversion-functions_12.vb)]  
  
## <a name="csng-example"></a><span data-ttu-id="bcd51-220">CSng 示例</span><span class="sxs-lookup"><span data-stu-id="bcd51-220">CSng Example</span></span>  
 <span data-ttu-id="bcd51-221">下面的示例使用`CSng`函数以将值转换为`Single`。</span><span class="sxs-lookup"><span data-stu-id="bcd51-221">The following example uses the `CSng` function to convert values to `Single`.</span></span>  
  
 [!code-vb[VbVbalrFunctions#13](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/type-conversion-functions_13.vb)]  
  
## <a name="cstr-example"></a><span data-ttu-id="bcd51-222">CStr 示例</span><span class="sxs-lookup"><span data-stu-id="bcd51-222">CStr Example</span></span>  
 <span data-ttu-id="bcd51-223">下面的示例使用`CStr`函数将转换为数字值`String`。</span><span class="sxs-lookup"><span data-stu-id="bcd51-223">The following example uses the `CStr` function to convert a numeric value to `String`.</span></span>  
  
 [!code-vb[VbVbalrFunctions#14](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/type-conversion-functions_14.vb)]  
  
 <span data-ttu-id="bcd51-224">下面的示例使用`CStr`函数将转换`Date`值复制到`String`值。</span><span class="sxs-lookup"><span data-stu-id="bcd51-224">The following example uses the `CStr` function to convert `Date` values to `String` values.</span></span>  
  
 [!code-vb[VbVbalrFunctions#15](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/type-conversion-functions_15.vb)]  
  
 <span data-ttu-id="bcd51-225">`CStr` 始终呈现`Date`采用当前区域设置，例如，标准短格式的值"6/15/2003年 4:35:47 PM"。</span><span class="sxs-lookup"><span data-stu-id="bcd51-225">`CStr` always renders a `Date` value in the standard short format for the current locale, for example, "6/15/2003 4:35:47 PM".</span></span> <span data-ttu-id="bcd51-226">但是，`CStr`取消*中性值*1/1/0001 日期和时间的 00:00:00。</span><span class="sxs-lookup"><span data-stu-id="bcd51-226">However, `CStr` suppresses the *neutral values* of 1/1/0001 for the date and 00:00:00 for the time.</span></span>  
  
 <span data-ttu-id="bcd51-227">有关详细信息返回的值`CStr`，请参阅[CStr 函数的返回值](../../../visual-basic/language-reference/functions/return-values-for-the-cstr-function.md)。</span><span class="sxs-lookup"><span data-stu-id="bcd51-227">For more detail on the values returned by `CStr`, see [Return Values for the CStr Function](../../../visual-basic/language-reference/functions/return-values-for-the-cstr-function.md).</span></span>  
  
## <a name="cuint-example"></a><span data-ttu-id="bcd51-228">CUInt 示例</span><span class="sxs-lookup"><span data-stu-id="bcd51-228">CUInt Example</span></span>  
 <span data-ttu-id="bcd51-229">下面的示例使用`CUInt`函数将转换为数字值`UInteger`。</span><span class="sxs-lookup"><span data-stu-id="bcd51-229">The following example uses the `CUInt` function to convert a numeric value to `UInteger`.</span></span>  
  
 [!code-vb[VbVbalrFunctions#16](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/type-conversion-functions_16.vb)]  
  
## <a name="culng-example"></a><span data-ttu-id="bcd51-230">CULng 示例</span><span class="sxs-lookup"><span data-stu-id="bcd51-230">CULng Example</span></span>  
 <span data-ttu-id="bcd51-231">下面的示例使用`CULng`函数将转换为数字值`ULong`。</span><span class="sxs-lookup"><span data-stu-id="bcd51-231">The following example uses the `CULng` function to convert a numeric value to `ULong`.</span></span>  
  
 [!code-vb[VbVbalrFunctions#17](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/type-conversion-functions_17.vb)]  
  
## <a name="cushort-example"></a><span data-ttu-id="bcd51-232">CUShort 示例</span><span class="sxs-lookup"><span data-stu-id="bcd51-232">CUShort Example</span></span>  
 <span data-ttu-id="bcd51-233">下面的示例使用`CUShort`函数将转换为数字值`UShort`。</span><span class="sxs-lookup"><span data-stu-id="bcd51-233">The following example uses the `CUShort` function to convert a numeric value to `UShort`.</span></span>  
  
 [!code-vb[VbVbalrFunctions#18](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/type-conversion-functions_18.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="bcd51-234">请参阅</span><span class="sxs-lookup"><span data-stu-id="bcd51-234">See Also</span></span>  
 <xref:Microsoft.VisualBasic.Strings.Asc%2A>  
 <xref:Microsoft.VisualBasic.Strings.AscW%2A>  
 <xref:Microsoft.VisualBasic.Strings.Chr%2A>  
 <xref:Microsoft.VisualBasic.Strings.ChrW%2A>  
 <xref:Microsoft.VisualBasic.Conversion.Int%2A>  
 <xref:Microsoft.VisualBasic.Conversion.Fix%2A>  
 <xref:Microsoft.VisualBasic.Strings.Format%2A>  
 <xref:Microsoft.VisualBasic.Conversion.Hex%2A>  
 <xref:Microsoft.VisualBasic.Conversion.Oct%2A>  
 <xref:Microsoft.VisualBasic.Conversion.Str%2A>  
 <xref:Microsoft.VisualBasic.Conversion.Val%2A>  
 [<span data-ttu-id="bcd51-235">转换函数</span><span class="sxs-lookup"><span data-stu-id="bcd51-235">Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/conversion-functions.md)  
 [<span data-ttu-id="bcd51-236">在 Visual Basic 中的类型转换</span><span class="sxs-lookup"><span data-stu-id="bcd51-236">Type Conversions in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)
