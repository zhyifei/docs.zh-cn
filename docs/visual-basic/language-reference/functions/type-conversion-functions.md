---
title: 类型转换函数 (Visual Basic)
ms.date: 10/24/2018
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
ms.openlocfilehash: 56dad921b2900061dbe2db0d8f1faaf759641f87
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61802292"
---
# <a name="type-conversion-functions-visual-basic"></a><span data-ttu-id="a7f82-102">类型转换函数 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a7f82-102">Type Conversion Functions (Visual Basic)</span></span>
<span data-ttu-id="a7f82-103">这些函数是代码的内联方式编译，这意味着转换代码计算表达式的值的一部分。</span><span class="sxs-lookup"><span data-stu-id="a7f82-103">These functions are compiled inline, meaning the conversion code is part of the code that evaluates the expression.</span></span> <span data-ttu-id="a7f82-104">有时是没有调用过程，以完成转换，从而提高性能。</span><span class="sxs-lookup"><span data-stu-id="a7f82-104">Sometimes there is no call to a procedure to accomplish the conversion, which improves performance.</span></span> <span data-ttu-id="a7f82-105">每个函数都强制转换为特定的数据类型的表达式。</span><span class="sxs-lookup"><span data-stu-id="a7f82-105">Each function coerces an expression to a specific data type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a7f82-106">语法</span><span class="sxs-lookup"><span data-stu-id="a7f82-106">Syntax</span></span>  
  
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
  
## <a name="part"></a><span data-ttu-id="a7f82-107">部件</span><span class="sxs-lookup"><span data-stu-id="a7f82-107">Part</span></span>  
 `expression`  
 <span data-ttu-id="a7f82-108">必需。</span><span class="sxs-lookup"><span data-stu-id="a7f82-108">Required.</span></span> <span data-ttu-id="a7f82-109">源数据类型的任何表达式。</span><span class="sxs-lookup"><span data-stu-id="a7f82-109">Any expression of the source data type.</span></span>  
  
## <a name="return-value-data-type"></a><span data-ttu-id="a7f82-110">返回值的数据类型</span><span class="sxs-lookup"><span data-stu-id="a7f82-110">Return Value Data Type</span></span>  
 <span data-ttu-id="a7f82-111">下表中所示，函数名称确定它返回的值的数据类型。</span><span class="sxs-lookup"><span data-stu-id="a7f82-111">The function name determines the data type of the value it returns, as shown in the following table.</span></span>  
  
|<span data-ttu-id="a7f82-112">功能名称</span><span class="sxs-lookup"><span data-stu-id="a7f82-112">Function name</span></span>|<span data-ttu-id="a7f82-113">返回数据类型</span><span class="sxs-lookup"><span data-stu-id="a7f82-113">Return data type</span></span>|<span data-ttu-id="a7f82-114">为范围`expression`参数</span><span class="sxs-lookup"><span data-stu-id="a7f82-114">Range for `expression` argument</span></span>|  
|-------------------|----------------------|-------------------------------------|  
|`CBool`|[<span data-ttu-id="a7f82-115">Boolean 数据类型</span><span class="sxs-lookup"><span data-stu-id="a7f82-115">Boolean Data Type</span></span>](../../../visual-basic/language-reference/data-types/boolean-data-type.md)|<span data-ttu-id="a7f82-116">任何有效`Char`或`String`或数值表达式。</span><span class="sxs-lookup"><span data-stu-id="a7f82-116">Any valid `Char` or `String` or numeric expression.</span></span>|  
|`CByte`|[<span data-ttu-id="a7f82-117">Byte 数据类型</span><span class="sxs-lookup"><span data-stu-id="a7f82-117">Byte Data Type</span></span>](../../../visual-basic/language-reference/data-types/byte-data-type.md)|<span data-ttu-id="a7f82-118"><xref:System.Byte.MinValue?displayProperty=nameWithType> (0) 通过<xref:System.Byte.MaxValue?displayProperty=nameWithType>(255) （无符号）; 小数部分舍入。<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="a7f82-118"><xref:System.Byte.MinValue?displayProperty=nameWithType> (0) through <xref:System.Byte.MaxValue?displayProperty=nameWithType> (255) (unsigned); fractional parts are rounded.<sup>1</sup></span></span><br/><br/><span data-ttu-id="a7f82-119">从 Visual Basic 15.8 开始，Visual Basic 可优化的性能与字节转换为浮点`CByte`函数; 请参阅[备注](#remarks)部分，了解详细信息。</span><span class="sxs-lookup"><span data-stu-id="a7f82-119">Starting with Visual Basic 15.8, Visual Basic optimizes the performance of floating-point to byte conversion with the `CByte` function; see the [Remarks](#remarks) section for more information.</span></span> <span data-ttu-id="a7f82-120">请参阅[CInt 示例](#cint-example)有关示例。</span><span class="sxs-lookup"><span data-stu-id="a7f82-120">See the [CInt Example](#cint-example) section for an example.</span></span>|  
|`CChar`|[<span data-ttu-id="a7f82-121">Char 数据类型</span><span class="sxs-lookup"><span data-stu-id="a7f82-121">Char Data Type</span></span>](../../../visual-basic/language-reference/data-types/char-data-type.md)|<span data-ttu-id="a7f82-122">任何有效`Char`或`String`表达式; 仅第一个字符的`String`转换; 值可以是 0 到 65535 （无符号）。</span><span class="sxs-lookup"><span data-stu-id="a7f82-122">Any valid `Char` or `String` expression; only first character of a `String` is converted; value can be 0 through 65535 (unsigned).</span></span>|  
|`CDate`|[<span data-ttu-id="a7f82-123">Date 数据类型</span><span class="sxs-lookup"><span data-stu-id="a7f82-123">Date Data Type</span></span>](../../../visual-basic/language-reference/data-types/date-data-type.md)|<span data-ttu-id="a7f82-124">日期和时间的任何有效表示形式。</span><span class="sxs-lookup"><span data-stu-id="a7f82-124">Any valid representation of a date and time.</span></span>|  
|`CDbl`|[<span data-ttu-id="a7f82-125">Double 数据类型</span><span class="sxs-lookup"><span data-stu-id="a7f82-125">Double Data Type</span></span>](../../../visual-basic/language-reference/data-types/double-data-type.md)|<span data-ttu-id="a7f82-126">-1.79769313486231570 e + 308 到-4.94065645841246544 e-324 对于负值;4.94065645841246544 e-324 到 1.79769313486231570 e + 308 的正值。</span><span class="sxs-lookup"><span data-stu-id="a7f82-126">-1.79769313486231570E+308 through -4.94065645841246544E-324 for negative values; 4.94065645841246544E-324 through 1.79769313486231570E+308 for positive values.</span></span>|  
|`CDec`|[<span data-ttu-id="a7f82-127">Decimal 数据类型</span><span class="sxs-lookup"><span data-stu-id="a7f82-127">Decimal Data Type</span></span>](../../../visual-basic/language-reference/data-types/decimal-data-type.md)|<span data-ttu-id="a7f82-128">+ /-79228162514264337593543950335 为零的数字，即，没有小数位的数字。</span><span class="sxs-lookup"><span data-stu-id="a7f82-128">+/-79,228,162,514,264,337,593,543,950,335 for zero-scaled numbers, that is, numbers with no decimal places.</span></span> <span data-ttu-id="a7f82-129">对于具有 28 位小数的数字，范围为 + /--7.9228162514264337593543950335 之间。</span><span class="sxs-lookup"><span data-stu-id="a7f82-129">For numbers with 28 decimal places, the range is +/-7.9228162514264337593543950335.</span></span> <span data-ttu-id="a7f82-130">最小可能的非零数字为 0.0000000000000000000000000001 （+ /-1E 28)。</span><span class="sxs-lookup"><span data-stu-id="a7f82-130">The smallest possible non-zero number is 0.0000000000000000000000000001 (+/-1E-28).</span></span>|  
|`CInt`|[<span data-ttu-id="a7f82-131">Integer 数据类型</span><span class="sxs-lookup"><span data-stu-id="a7f82-131">Integer Data Type</span></span>](../../../visual-basic/language-reference/data-types/integer-data-type.md)|<span data-ttu-id="a7f82-132"><xref:System.Int32.MinValue?displayProperty=nameWithType> (-2,147,483,648) 通过<xref:System.Int32.MaxValue?displayProperty=nameWithType>(2,147,483,647); 小数部分舍入。<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="a7f82-132"><xref:System.Int32.MinValue?displayProperty=nameWithType> (-2,147,483,648) through <xref:System.Int32.MaxValue?displayProperty=nameWithType> (2,147,483,647); fractional parts are rounded.<sup>1</sup></span></span> <br/><br/><span data-ttu-id="a7f82-133">从 Visual Basic 15.8 开始，Visual Basic 可优化的性能与整数转换为浮点`CInt`函数; 请参阅[备注](#remarks)部分，了解详细信息。</span><span class="sxs-lookup"><span data-stu-id="a7f82-133">Starting with Visual Basic 15.8, Visual Basic optimizes the performance of floating-point to integer conversion with the `CInt` function; see the [Remarks](#remarks) section for more information.</span></span> <span data-ttu-id="a7f82-134">请参阅[CInt 示例](#cint-example)有关示例。</span><span class="sxs-lookup"><span data-stu-id="a7f82-134">See the [CInt Example](#cint-example) section for an example.</span></span> |  
|`CLng`|[<span data-ttu-id="a7f82-135">Long 数据类型</span><span class="sxs-lookup"><span data-stu-id="a7f82-135">Long Data Type</span></span>](../../../visual-basic/language-reference/data-types/long-data-type.md)|<span data-ttu-id="a7f82-136"><xref:System.Int64.MinValue?displayProperty=nameWithType> (-9223372036854775808) 通过<xref:System.Int64.MaxValue?displayProperty=nameWithType>(9,223,372,036,854,775,807); 小数部分舍入。<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="a7f82-136"><xref:System.Int64.MinValue?displayProperty=nameWithType> (-9,223,372,036,854,775,808) through <xref:System.Int64.MaxValue?displayProperty=nameWithType> (9,223,372,036,854,775,807); fractional parts are rounded.<sup>1</sup></span></span><br/><br/><span data-ttu-id="a7f82-137">从 Visual Basic 15.8 开始，Visual Basic 可优化的性能与 64 位整数转换为浮点`CLng`函数; 请参阅[备注](#remarks)部分，了解详细信息。</span><span class="sxs-lookup"><span data-stu-id="a7f82-137">Starting with Visual Basic 15.8, Visual Basic optimizes the performance of floating-point to 64-bit integer conversion with the `CLng` function; see the [Remarks](#remarks) section for more information.</span></span> <span data-ttu-id="a7f82-138">请参阅[CInt 示例](#cint-example)有关示例。</span><span class="sxs-lookup"><span data-stu-id="a7f82-138">See the [CInt Example](#cint-example) section for an example.</span></span>|  
|`CObj`|[<span data-ttu-id="a7f82-139">Object 数据类型</span><span class="sxs-lookup"><span data-stu-id="a7f82-139">Object Data Type</span></span>](../../../visual-basic/language-reference/data-types/object-data-type.md)|<span data-ttu-id="a7f82-140">任何有效表达式。</span><span class="sxs-lookup"><span data-stu-id="a7f82-140">Any valid expression.</span></span>|  
|`CSByte`|[<span data-ttu-id="a7f82-141">SByte 数据类型</span><span class="sxs-lookup"><span data-stu-id="a7f82-141">SByte Data Type</span></span>](../../../visual-basic/language-reference/data-types/sbyte-data-type.md)|<span data-ttu-id="a7f82-142"><xref:System.SByte.MinValue?displayProperty=nameWithType> (-128) 通过<xref:System.SByte.MaxValue?displayProperty=nameWithType>(127); 小数部分舍入。<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="a7f82-142"><xref:System.SByte.MinValue?displayProperty=nameWithType> (-128) through <xref:System.SByte.MaxValue?displayProperty=nameWithType> (127); fractional parts are rounded.<sup>1</sup></span></span><br/><br/><span data-ttu-id="a7f82-143">从 Visual Basic 15.8 开始，Visual Basic 来优化性能的使用的有符号的字节转换为浮点`CSByte`函数; 请参阅[备注](#remarks)部分，了解详细信息。</span><span class="sxs-lookup"><span data-stu-id="a7f82-143">Starting with Visual Basic 15.8, Visual Basic optimizes the performance of floating-point to signed byte conversion with the `CSByte` function; see the [Remarks](#remarks) section for more information.</span></span> <span data-ttu-id="a7f82-144">请参阅[CInt 示例](#cint-example)有关示例。</span><span class="sxs-lookup"><span data-stu-id="a7f82-144">See the [CInt Example](#cint-example) section for an example.</span></span>|  
|`CShort`|[<span data-ttu-id="a7f82-145">Short 数据类型</span><span class="sxs-lookup"><span data-stu-id="a7f82-145">Short Data Type</span></span>](../../../visual-basic/language-reference/data-types/short-data-type.md)|<span data-ttu-id="a7f82-146"><xref:System.Int16.MinValue?displayProperty=nameWithType> (-32,768) 通过<xref:System.Int16.MaxValue?displayProperty=nameWithType>(32,767); 小数部分舍入。<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="a7f82-146"><xref:System.Int16.MinValue?displayProperty=nameWithType> (-32,768) through <xref:System.Int16.MaxValue?displayProperty=nameWithType> (32,767); fractional parts are rounded.<sup>1</sup></span></span><br/><br/><span data-ttu-id="a7f82-147">从 Visual Basic 15.8 开始，Visual Basic 来优化性能的使用 16 位整数转换为浮点`CShort`函数; 请参阅[备注](#remarks)部分，了解详细信息。</span><span class="sxs-lookup"><span data-stu-id="a7f82-147">Starting with Visual Basic 15.8, Visual Basic optimizes the performance of floating-point to 16-bit integer conversion with the `CShort` function; see the [Remarks](#remarks) section for more information.</span></span> <span data-ttu-id="a7f82-148">请参阅[CInt 示例](#cint-example)有关示例。</span><span class="sxs-lookup"><span data-stu-id="a7f82-148">See the [CInt Example](#cint-example) section for an example.</span></span>|  
|`CSng`|[<span data-ttu-id="a7f82-149">Single 数据类型</span><span class="sxs-lookup"><span data-stu-id="a7f82-149">Single Data Type</span></span>](../../../visual-basic/language-reference/data-types/single-data-type.md)|<span data-ttu-id="a7f82-150">-3.402823e+38 到-1.401298E-45 对于负值;1.401298E-45 到 3.402823e+38 对于正值。</span><span class="sxs-lookup"><span data-stu-id="a7f82-150">-3.402823E+38 through -1.401298E-45 for negative values; 1.401298E-45 through 3.402823E+38 for positive values.</span></span>|  
|`CStr`|[<span data-ttu-id="a7f82-151">String 数据类型</span><span class="sxs-lookup"><span data-stu-id="a7f82-151">String Data Type</span></span>](../../../visual-basic/language-reference/data-types/string-data-type.md)|<span data-ttu-id="a7f82-152">返回有关`CStr`依赖于`expression`参数。</span><span class="sxs-lookup"><span data-stu-id="a7f82-152">Returns for `CStr` depend on the `expression` argument.</span></span> <span data-ttu-id="a7f82-153">请参阅[CStr 函数的返回值](../../../visual-basic/language-reference/functions/return-values-for-the-cstr-function.md)。</span><span class="sxs-lookup"><span data-stu-id="a7f82-153">See [Return Values for the CStr Function](../../../visual-basic/language-reference/functions/return-values-for-the-cstr-function.md).</span></span>|  
|`CUInt`|[<span data-ttu-id="a7f82-154">UInteger 数据类型</span><span class="sxs-lookup"><span data-stu-id="a7f82-154">UInteger Data Type</span></span>](../../../visual-basic/language-reference/data-types/uinteger-data-type.md)|<span data-ttu-id="a7f82-155"><xref:System.UInt32.MinValue?displayProperty=nameWithType> (0) 通过<xref:System.UInt32.MaxValue?displayProperty=nameWithType>(4,294,967,295) （无符号）; 小数部分舍入。<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="a7f82-155"><xref:System.UInt32.MinValue?displayProperty=nameWithType> (0) through <xref:System.UInt32.MaxValue?displayProperty=nameWithType> (4,294,967,295) (unsigned); fractional parts are rounded.<sup>1</sup></span></span><br/><br/><span data-ttu-id="a7f82-156">从 Visual Basic 15.8 开始，Visual Basic 可优化的性能与无符号的整数转换为浮点`CUInt`函数; 请参阅[备注](#remarks)部分，了解详细信息。</span><span class="sxs-lookup"><span data-stu-id="a7f82-156">Starting with Visual Basic 15.8, Visual Basic optimizes the performance of floating-point to unsigned integer conversion with the `CUInt` function; see the [Remarks](#remarks) section for more information.</span></span> <span data-ttu-id="a7f82-157">请参阅[CInt 示例](#cint-example)有关示例。</span><span class="sxs-lookup"><span data-stu-id="a7f82-157">See the [CInt Example](#cint-example) section for an example.</span></span>|  
|`CULng`|[<span data-ttu-id="a7f82-158">ULong 数据类型</span><span class="sxs-lookup"><span data-stu-id="a7f82-158">ULong Data Type</span></span>](../../../visual-basic/language-reference/data-types/ulong-data-type.md)|<span data-ttu-id="a7f82-159"><xref:System.UInt64.MinValue?displayProperty=nameWithType> (0) 通过<xref:System.UInt64.MaxValue?displayProperty=nameWithType>(18446744073709551615) （无符号）; 小数部分舍入。<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="a7f82-159"><xref:System.UInt64.MinValue?displayProperty=nameWithType> (0) through <xref:System.UInt64.MaxValue?displayProperty=nameWithType> (18,446,744,073,709,551,615) (unsigned); fractional parts are rounded.<sup>1</sup></span></span><br/><br/><span data-ttu-id="a7f82-160">从 Visual Basic 15.8 开始，Visual Basic 可优化的性能与无符号长整数转换为浮点`CULng`函数; 请参阅[备注](#remarks)部分，了解详细信息。</span><span class="sxs-lookup"><span data-stu-id="a7f82-160">Starting with Visual Basic 15.8, Visual Basic optimizes the performance of floating-point to unsigned long integer conversion with the `CULng` function; see the [Remarks](#remarks) section for more information.</span></span> <span data-ttu-id="a7f82-161">请参阅[CInt 示例](#cint-example)有关示例。</span><span class="sxs-lookup"><span data-stu-id="a7f82-161">See the [CInt Example](#cint-example) section for an example.</span></span>|  
|`CUShort`|[<span data-ttu-id="a7f82-162">UShort 数据类型</span><span class="sxs-lookup"><span data-stu-id="a7f82-162">UShort Data Type</span></span>](../../../visual-basic/language-reference/data-types/ushort-data-type.md)|<span data-ttu-id="a7f82-163"><xref:System.UInt16.MinValue?displayProperty=nameWithType> (0) 通过<xref:System.UInt16.MaxValue?displayProperty=nameWithType>(65535) （无符号）; 小数部分舍入。<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="a7f82-163"><xref:System.UInt16.MinValue?displayProperty=nameWithType> (0) through <xref:System.UInt16.MaxValue?displayProperty=nameWithType> (65,535) (unsigned); fractional parts are rounded.<sup>1</sup></span></span><br/><br/><span data-ttu-id="a7f82-164">从 Visual Basic 15.8 开始，Visual Basic 来优化性能的使用 16 位无符号的整数转换为浮点`CUShort`函数; 请参阅[备注](#remarks)部分，了解详细信息。</span><span class="sxs-lookup"><span data-stu-id="a7f82-164">Starting with Visual Basic 15.8, Visual Basic optimizes the performance of floating-point to unsigned 16-bit integer conversion with the `CUShort` function; see the [Remarks](#remarks) section for more information.</span></span> <span data-ttu-id="a7f82-165">请参阅[CInt 示例](#cint-example)有关示例。</span><span class="sxs-lookup"><span data-stu-id="a7f82-165">See the [CInt Example](#cint-example) section for an example.</span></span>|  
  
 <span data-ttu-id="a7f82-166"><sup>1</sup>小数部分时可能会出现一种特殊的舍入名为*银行家的舍入*。</span><span class="sxs-lookup"><span data-stu-id="a7f82-166"><sup>1</sup> Fractional parts can be subject to a special type of rounding called *banker's rounding*.</span></span> <span data-ttu-id="a7f82-167">有关详细信息，请参阅"备注"。</span><span class="sxs-lookup"><span data-stu-id="a7f82-167">See "Remarks" for more information.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a7f82-168">备注</span><span class="sxs-lookup"><span data-stu-id="a7f82-168">Remarks</span></span>  
 <span data-ttu-id="a7f82-169">通常，您应使用 Visual Basic 类型转换函数优先于.NET Framework 方法如`ToString()`，而是在<xref:System.Convert>类或各个类型结构或类上。</span><span class="sxs-lookup"><span data-stu-id="a7f82-169">As a rule, you should use the Visual Basic type conversion functions in preference to the .NET Framework methods such as `ToString()`, either on the <xref:System.Convert> class or on an individual type structure or class.</span></span> <span data-ttu-id="a7f82-170">Visual Basic 函数设计为与 Visual Basic 代码的最佳交互，并且它们还使得更短且更易于阅读源代码。</span><span class="sxs-lookup"><span data-stu-id="a7f82-170">The Visual Basic functions are designed for optimal interaction with Visual Basic code, and they also make your source code shorter and easier to read.</span></span> <span data-ttu-id="a7f82-171">此外，.NET Framework 转换方法不始终生成与 Visual Basic 函数，例如，在转换时相同的结果`Boolean`到`Integer`。</span><span class="sxs-lookup"><span data-stu-id="a7f82-171">In addition, the .NET Framework conversion methods do not always produce the same results as the Visual Basic functions, for example when converting `Boolean` to `Integer`.</span></span> <span data-ttu-id="a7f82-172">有关详细信息，请参阅[故障排除数据类型](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)。</span><span class="sxs-lookup"><span data-stu-id="a7f82-172">For more information, see [Troubleshooting Data Types](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md).</span></span>  

<span data-ttu-id="a7f82-173">从 Visual Basic 15.8 开始，浮点 point 到整数的转换的性能优化时将传递<xref:System.Single>或<xref:System.Double>返回值通过下列方法之一的整数转换函数 (`CByte`， `CShort`, `CInt`, `CLng`, `CSByte`, `CUShort`, `CUInt`, `CULng`):</span><span class="sxs-lookup"><span data-stu-id="a7f82-173">Starting with Visual Basic 15.8, the performance of floating-point-to-integer conversion is optimized when you pass the <xref:System.Single> or <xref:System.Double> value returned by the following methods to one of the integer conversion functions (`CByte`, `CShort`, `CInt`, `CLng`, `CSByte`, `CUShort`, `CUInt`, `CULng`):</span></span>

- <xref:Microsoft.VisualBasic.Conversion.Fix(System.Double)?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.Conversion.Fix(System.Object)?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.Conversion.Fix(System.Single)?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.Conversion.Int(System.Double)?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.Conversion.Int(System.Object)?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.Conversion.Int(System.Single)?displayProperty=nameWithType>
- <xref:System.Math.Ceiling(System.Double)?displayProperty=nameWithType>
- <xref:System.Math.Floor(System.Double)?displayProperty=nameWithType>
- <xref:System.Math.Round(System.Double)?displayProperty=nameWithType>
- <xref:System.Math.Truncate(System.Double)?displayProperty=nameWithType>

<span data-ttu-id="a7f82-174">这种优化允许代码执行大量的整数转换为两倍的速度运行。</span><span class="sxs-lookup"><span data-stu-id="a7f82-174">This optimization allows code that does a large number of integer conversions to run up to twice as fast.</span></span> <span data-ttu-id="a7f82-175">下面的示例说明了这些优化浮点 point 到整数转换：</span><span class="sxs-lookup"><span data-stu-id="a7f82-175">The following example illustrates these optimized floating-point-to-integer conversions:</span></span>

```vb
Dim s As Single = 173.7619
Dim d As Double = s 

Dim i1 As Integer = CInt(Fix(s))               ' Result: 173
Dim b1 As Byte = CByte(Int(d))                 ' Result: 173
Dim s1 AS Short = CShort(Math.Truncate(s))     ' Result: 173
Dim i2 As Integer = CInt(Math.Ceiling(d))      ' Result: 174
Dim i3 As Integer = CInt(Math.Round(s))        ' Result: 174
```

## <a name="behavior"></a><span data-ttu-id="a7f82-176">行为</span><span class="sxs-lookup"><span data-stu-id="a7f82-176">Behavior</span></span>  
  
-   <span data-ttu-id="a7f82-177">**强制转换。**</span><span class="sxs-lookup"><span data-stu-id="a7f82-177">**Coercion.**</span></span> <span data-ttu-id="a7f82-178">一般情况下，可以使用数据类型转换函数要强制转换到特定的数据类型，而不是默认数据类型操作的结果。</span><span class="sxs-lookup"><span data-stu-id="a7f82-178">In general, you can use the data type conversion functions to coerce the result of an operation to a particular data type rather than the default data type.</span></span> <span data-ttu-id="a7f82-179">例如，使用`CDec`强制执行在其中单精度、 双精度或整型运算将通常会发生的情况下小数运算。</span><span class="sxs-lookup"><span data-stu-id="a7f82-179">For example, use `CDec` to force decimal arithmetic in cases where single-precision, double-precision, or integer arithmetic would normally take place.</span></span>  
  
-   <span data-ttu-id="a7f82-180">**失败的转换。**</span><span class="sxs-lookup"><span data-stu-id="a7f82-180">**Failed Conversions.**</span></span> <span data-ttu-id="a7f82-181">如果`expression`传递给函数是外部的数据类型范围它是要转换<xref:System.OverflowException>时发生。</span><span class="sxs-lookup"><span data-stu-id="a7f82-181">If the `expression` passed to the function is outside the range of the data type to which it is to be converted, an <xref:System.OverflowException> occurs.</span></span>  
  
-   <span data-ttu-id="a7f82-182">**小数部分。**</span><span class="sxs-lookup"><span data-stu-id="a7f82-182">**Fractional Parts.**</span></span> <span data-ttu-id="a7f82-183">当将非整型值转换为整型类型，整数转换函数 (`CByte`， `CInt`， `CLng`， `CSByte`， `CShort`， `CUInt`， `CULng`，和`CUShort`) 中删除小数部分和舍入到最接近的整数值。</span><span class="sxs-lookup"><span data-stu-id="a7f82-183">When you convert a nonintegral value to an integral type, the integer conversion functions (`CByte`, `CInt`, `CLng`, `CSByte`, `CShort`, `CUInt`, `CULng`, and `CUShort`) remove the fractional part and round the value to the closest integer.</span></span>  
  
     <span data-ttu-id="a7f82-184">如果小数部分正好是 0.5，整数转换函数将其舍入为接近的偶数。</span><span class="sxs-lookup"><span data-stu-id="a7f82-184">If the fractional part is exactly 0.5, the integer conversion functions round it to the nearest even integer.</span></span> <span data-ttu-id="a7f82-185">例如，0.5 舍入为 0，和 1.5 和 2.5 舍入为 2。</span><span class="sxs-lookup"><span data-stu-id="a7f82-185">For example, 0.5 rounds to 0, and 1.5 and 2.5 both round to 2.</span></span> <span data-ttu-id="a7f82-186">这有时称为*银行家的舍入*，其目的是将许多这样的数字相加时可能会累积的偏补偿。</span><span class="sxs-lookup"><span data-stu-id="a7f82-186">This is sometimes called *banker's rounding*, and its purpose is to compensate for a bias that could accumulate when adding many such numbers together.</span></span>  
  
     <span data-ttu-id="a7f82-187">`CInt` 并`CLng`有所不同<xref:Microsoft.VisualBasic.Conversion.Int%2A>和<xref:Microsoft.VisualBasic.Conversion.Fix%2A>函数，它截断，而不是舍入的数字的小数部分。</span><span class="sxs-lookup"><span data-stu-id="a7f82-187">`CInt` and `CLng` differ from the <xref:Microsoft.VisualBasic.Conversion.Int%2A> and <xref:Microsoft.VisualBasic.Conversion.Fix%2A> functions, which truncate, rather than round, the fractional part of a number.</span></span> <span data-ttu-id="a7f82-188">此外，`Fix`和`Int`始终返回相同的数据类型的值与传入的。</span><span class="sxs-lookup"><span data-stu-id="a7f82-188">Also, `Fix` and `Int` always return a value of the same data type as you pass in.</span></span>  
  
-   <span data-ttu-id="a7f82-189">**日期/时间转换。**</span><span class="sxs-lookup"><span data-stu-id="a7f82-189">**Date/Time Conversions.**</span></span> <span data-ttu-id="a7f82-190">使用<xref:Microsoft.VisualBasic.Information.IsDate%2A>函数来确定一个值，是否可以转换为日期和时间。</span><span class="sxs-lookup"><span data-stu-id="a7f82-190">Use the <xref:Microsoft.VisualBasic.Information.IsDate%2A> function to determine if a value can be converted to a date and time.</span></span> <span data-ttu-id="a7f82-191">`CDate` 识别的日期文本和时间文本，但不是数字值。</span><span class="sxs-lookup"><span data-stu-id="a7f82-191">`CDate` recognizes date literals and time literals but not numeric values.</span></span> <span data-ttu-id="a7f82-192">转换 Visual Basic 6.0`Date`值设为`Date`在 Visual Basic 2005 中的值或更高版本，可以使用<xref:System.DateTime.FromOADate%2A?displayProperty=nameWithType>方法。</span><span class="sxs-lookup"><span data-stu-id="a7f82-192">To convert a Visual Basic 6.0 `Date` value to a `Date` value in Visual Basic 2005 or later versions, you can use the <xref:System.DateTime.FromOADate%2A?displayProperty=nameWithType> method.</span></span>  
  
-   <span data-ttu-id="a7f82-193">**非特定于日期/时间值。**</span><span class="sxs-lookup"><span data-stu-id="a7f82-193">**Neutral Date/Time Values.**</span></span> <span data-ttu-id="a7f82-194">[日期数据类型](../../../visual-basic/language-reference/data-types/date-data-type.md)始终包含日期和时间信息。</span><span class="sxs-lookup"><span data-stu-id="a7f82-194">The [Date Data Type](../../../visual-basic/language-reference/data-types/date-data-type.md) always contains both date and time information.</span></span> <span data-ttu-id="a7f82-195">为进行类型转换，Visual Basic 将 1/1/0001 (年 1 月 1 年 1) 要*中性值*次为非特定值的日期，和 00:00:00 （午夜）。</span><span class="sxs-lookup"><span data-stu-id="a7f82-195">For purposes of type conversion, Visual Basic considers 1/1/0001 (January 1 of the year 1) to be a *neutral value* for the date, and 00:00:00 (midnight) to be a neutral value for the time.</span></span> <span data-ttu-id="a7f82-196">如果您在转换`Date`值为一个字符串，`CStr`不在生成的字符串中包括非特定值。</span><span class="sxs-lookup"><span data-stu-id="a7f82-196">If you convert a `Date` value to a string, `CStr` does not include neutral values in the resulting string.</span></span> <span data-ttu-id="a7f82-197">例如，如果您将转换`#January 1, 0001 9:30:00#`为一个字符串，则结果为"9:30:00 AM"; 禁止显示日期信息。</span><span class="sxs-lookup"><span data-stu-id="a7f82-197">For example, if you convert `#January 1, 0001 9:30:00#` to a string, the result is "9:30:00 AM"; the date information is suppressed.</span></span> <span data-ttu-id="a7f82-198">但是，日期信息仍会在原始`Date`值和可恢复函数如<xref:Microsoft.VisualBasic.DateAndTime.DatePart%2A>函数。</span><span class="sxs-lookup"><span data-stu-id="a7f82-198">However, the date information is still present in the original `Date` value and can be recovered with functions such as <xref:Microsoft.VisualBasic.DateAndTime.DatePart%2A> function.</span></span>  
  
-   <span data-ttu-id="a7f82-199">**区域差异。**</span><span class="sxs-lookup"><span data-stu-id="a7f82-199">**Culture Sensitivity.**</span></span> <span data-ttu-id="a7f82-200">涉及到字符串类型转换函数执行基于应用程序的当前区域性设置的转换。</span><span class="sxs-lookup"><span data-stu-id="a7f82-200">The type conversion functions involving strings perform conversions based on the current culture settings for the application.</span></span> <span data-ttu-id="a7f82-201">例如，`CDate`识别根据您的系统的区域设置日期的格式。</span><span class="sxs-lookup"><span data-stu-id="a7f82-201">For example, `CDate` recognizes date formats according to the locale setting of your system.</span></span> <span data-ttu-id="a7f82-202">必须提供一天、 月和年按正确的顺序为区域设置，或可能不正确解释日期。</span><span class="sxs-lookup"><span data-stu-id="a7f82-202">You must provide the day, month, and year in the correct order for your locale, or the date might not be interpreted correctly.</span></span> <span data-ttu-id="a7f82-203">如果它包含一个星期的字符串，例如"Wednesday"无法识别的长日期格式。</span><span class="sxs-lookup"><span data-stu-id="a7f82-203">A long date format is not recognized if it contains a day-of-the-week string, such as "Wednesday".</span></span>  
  
     <span data-ttu-id="a7f82-204">如果需要将转换为或格式不是由您的区域设置指定的值的字符串表示形式，则不能使用 Visual Basic 类型转换函数。</span><span class="sxs-lookup"><span data-stu-id="a7f82-204">If you need to convert to or from a string representation of a value in a format other than the one specified by your locale, you cannot use the Visual Basic type conversion functions.</span></span> <span data-ttu-id="a7f82-205">若要执行此操作，请使用`ToString(IFormatProvider)`和`Parse(String, IFormatProvider)`该值的类型的方法。</span><span class="sxs-lookup"><span data-stu-id="a7f82-205">To do this, use the `ToString(IFormatProvider)` and `Parse(String, IFormatProvider)` methods of that value's type.</span></span> <span data-ttu-id="a7f82-206">例如，使用<xref:System.Double.Parse%2A?displayProperty=nameWithType>转换为字符串时`Double`，并使用<xref:System.Double.ToString%2A?displayProperty=nameWithType>类型的值转换时`Double`为字符串。</span><span class="sxs-lookup"><span data-stu-id="a7f82-206">For example, use <xref:System.Double.Parse%2A?displayProperty=nameWithType> when converting a string to a `Double`, and use <xref:System.Double.ToString%2A?displayProperty=nameWithType> when converting a value of type `Double` to a string.</span></span>  
  
## <a name="ctype-function"></a><span data-ttu-id="a7f82-207">CType Function</span><span class="sxs-lookup"><span data-stu-id="a7f82-207">CType Function</span></span>  
 <span data-ttu-id="a7f82-208">[CType Function](../../../visual-basic/language-reference/functions/ctype-function.md)采用第二个参数`typename`，并将强制`expression`到`typename`，其中`typename`可以是任何数据类型、 结构、 类或接口向其存在的有效转换。</span><span class="sxs-lookup"><span data-stu-id="a7f82-208">The [CType Function](../../../visual-basic/language-reference/functions/ctype-function.md) takes a second argument, `typename`, and coerces `expression` to `typename`, where `typename` can be any data type, structure, class, or interface to which there exists a valid conversion.</span></span>  
  
 <span data-ttu-id="a7f82-209">有关的比较`CType`与其他类型转换关键字，请参阅[DirectCast 运算符](../../../visual-basic/language-reference/operators/directcast-operator.md)并[TryCast 运算符](../../../visual-basic/language-reference/operators/trycast-operator.md)。</span><span class="sxs-lookup"><span data-stu-id="a7f82-209">For a comparison of `CType` with the other type conversion keywords, see [DirectCast Operator](../../../visual-basic/language-reference/operators/directcast-operator.md) and [TryCast Operator](../../../visual-basic/language-reference/operators/trycast-operator.md).</span></span>  
  
## <a name="cbool-example"></a><span data-ttu-id="a7f82-210">CBool 示例</span><span class="sxs-lookup"><span data-stu-id="a7f82-210">CBool Example</span></span>  
 <span data-ttu-id="a7f82-211">下面的示例使用`CBool`函数将表达式转换为`Boolean`值。</span><span class="sxs-lookup"><span data-stu-id="a7f82-211">The following example uses the `CBool` function to convert expressions to `Boolean` values.</span></span> <span data-ttu-id="a7f82-212">如果表达式计算结果为非零值，`CBool`将返回`True`; 否则为它将返回`False`。</span><span class="sxs-lookup"><span data-stu-id="a7f82-212">If an expression evaluates to a nonzero value, `CBool` returns `True`; otherwise, it returns `False`.</span></span>  
  
 [!code-vb[VbVbalrFunctions#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#1)]  
  
## <a name="cbyte-example"></a><span data-ttu-id="a7f82-213">CByte 示例</span><span class="sxs-lookup"><span data-stu-id="a7f82-213">CByte Example</span></span>  
 <span data-ttu-id="a7f82-214">下面的示例使用`CByte`函数将转换为表达式`Byte`。</span><span class="sxs-lookup"><span data-stu-id="a7f82-214">The following example uses the `CByte` function to convert an expression to a `Byte`.</span></span>  
  
 [!code-vb[VbVbalrFunctions#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#2)]  
  
## <a name="cchar-example"></a><span data-ttu-id="a7f82-215">CChar 示例</span><span class="sxs-lookup"><span data-stu-id="a7f82-215">CChar Example</span></span>  
 <span data-ttu-id="a7f82-216">下面的示例使用`CChar`函数将转换的第一个字符`String`表达式`Char`类型。</span><span class="sxs-lookup"><span data-stu-id="a7f82-216">The following example uses the `CChar` function to convert the first character of a `String` expression to a `Char` type.</span></span>  
  
 [!code-vb[VbVbalrFunctions#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#3)]  
  
 <span data-ttu-id="a7f82-217">输入的参数`CChar`的数据类型必须为`Char`或`String`。</span><span class="sxs-lookup"><span data-stu-id="a7f82-217">The input argument to `CChar` must be of data type `Char` or `String`.</span></span> <span data-ttu-id="a7f82-218">不能使用`CChar`若要将数字转换为字符，因为`CChar`不能接受数值数据类型。</span><span class="sxs-lookup"><span data-stu-id="a7f82-218">You cannot use `CChar` to convert a number to a character, because `CChar` cannot accept a numeric data type.</span></span> <span data-ttu-id="a7f82-219">以下示例获取一个表示码位 （字符代码） 的数字，并将其转换为相应的字符。</span><span class="sxs-lookup"><span data-stu-id="a7f82-219">The following example obtains a number representing a code point (character code) and converts it to the corresponding character.</span></span> <span data-ttu-id="a7f82-220">它使用<xref:Microsoft.VisualBasic.Interaction.InputBox%2A>函数获取数字的字符串`CInt`要转换为类型字符串`Integer`，和`ChrW`要转换的编号，以键入`Char`。</span><span class="sxs-lookup"><span data-stu-id="a7f82-220">It uses the <xref:Microsoft.VisualBasic.Interaction.InputBox%2A> function to obtain the string of digits, `CInt` to convert the string to type `Integer`, and `ChrW` to convert the number to type `Char`.</span></span>  
  
 [!code-vb[VbVbalrFunctions#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#4)]  
  
## <a name="cdate-example"></a><span data-ttu-id="a7f82-221">CDate 示例</span><span class="sxs-lookup"><span data-stu-id="a7f82-221">CDate Example</span></span>  
 <span data-ttu-id="a7f82-222">下面的示例使用`CDate`函数将字符串转换为`Date`值。</span><span class="sxs-lookup"><span data-stu-id="a7f82-222">The following example uses the `CDate` function to convert strings to `Date` values.</span></span> <span data-ttu-id="a7f82-223">一般情况下，不建议进行硬编码的日期和时间作为字符串 （如在此示例中所示）。</span><span class="sxs-lookup"><span data-stu-id="a7f82-223">In general, hard-coding dates and times as strings (as shown in this example) is not recommended.</span></span> <span data-ttu-id="a7f82-224">使用文字日期和时间文字，如 #Feb 12，1969 # 和 # 4:45:23 PM #，而是。</span><span class="sxs-lookup"><span data-stu-id="a7f82-224">Use date literals and time literals, such as #Feb 12, 1969# and #4:45:23 PM#, instead.</span></span>  
  
 [!code-vb[VbVbalrFunctions#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#5)]  
  
## <a name="cdbl-example"></a><span data-ttu-id="a7f82-225">CDbl 示例</span><span class="sxs-lookup"><span data-stu-id="a7f82-225">CDbl Example</span></span>  
 [!code-vb[VbVbalrFunctions#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#6)]  
  
## <a name="cdec-example"></a><span data-ttu-id="a7f82-226">CDec 示例</span><span class="sxs-lookup"><span data-stu-id="a7f82-226">CDec Example</span></span>  
 <span data-ttu-id="a7f82-227">下面的示例使用`CDec`函数将转换为数字值`Decimal`。</span><span class="sxs-lookup"><span data-stu-id="a7f82-227">The following example uses the `CDec` function to convert a numeric value to `Decimal`.</span></span>  
  
 [!code-vb[VbVbalrFunctions#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#7)]  
  
## <a name="cint-example"></a><span data-ttu-id="a7f82-228">CInt 示例</span><span class="sxs-lookup"><span data-stu-id="a7f82-228">CInt Example</span></span>  
 <span data-ttu-id="a7f82-229">下面的示例使用`CInt`函数将值转换为`Integer`。</span><span class="sxs-lookup"><span data-stu-id="a7f82-229">The following example uses the `CInt` function to convert a value to `Integer`.</span></span>  
  
 [!code-vb[VbVbalrFunctions#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#8)]  

## <a name="clng-example"></a><span data-ttu-id="a7f82-230">CLng 示例</span><span class="sxs-lookup"><span data-stu-id="a7f82-230">CLng Example</span></span>
 <span data-ttu-id="a7f82-231">下面的示例使用`CLng`函数以将值转换为`Long`。</span><span class="sxs-lookup"><span data-stu-id="a7f82-231">The following example uses the `CLng` function to convert values to `Long`.</span></span>  
  
 [!code-vb[VbVbalrFunctions#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#9)]  
  
## <a name="cobj-example"></a><span data-ttu-id="a7f82-232">示例中的 CObj</span><span class="sxs-lookup"><span data-stu-id="a7f82-232">CObj Example</span></span>  
 <span data-ttu-id="a7f82-233">下面的示例使用`CObj`函数将转换为数字值`Object`。</span><span class="sxs-lookup"><span data-stu-id="a7f82-233">The following example uses the `CObj` function to convert a numeric value to `Object`.</span></span> <span data-ttu-id="a7f82-234">`Object`变量本身包含仅一个四字节的指针，用于指向`Double`分配给它的值。</span><span class="sxs-lookup"><span data-stu-id="a7f82-234">The `Object` variable itself contains only a four-byte pointer, which points to the `Double` value assigned to it.</span></span>  
  
 [!code-vb[VbVbalrFunctions#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#10)]  
  
## <a name="csbyte-example"></a><span data-ttu-id="a7f82-235">CSByte 示例</span><span class="sxs-lookup"><span data-stu-id="a7f82-235">CSByte Example</span></span>  
 <span data-ttu-id="a7f82-236">下面的示例使用`CSByte`函数将转换为数字值`SByte`。</span><span class="sxs-lookup"><span data-stu-id="a7f82-236">The following example uses the `CSByte` function to convert a numeric value to `SByte`.</span></span>  
  
 [!code-vb[VbVbalrFunctions#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#11)]  
  
## <a name="cshort-example"></a><span data-ttu-id="a7f82-237">CShort 示例</span><span class="sxs-lookup"><span data-stu-id="a7f82-237">CShort Example</span></span>  
 <span data-ttu-id="a7f82-238">下面的示例使用`CShort`函数将转换为数字值`Short`。</span><span class="sxs-lookup"><span data-stu-id="a7f82-238">The following example uses the `CShort` function to convert a numeric value to `Short`.</span></span>  
  
 [!code-vb[VbVbalrFunctions#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#12)]  
  
## <a name="csng-example"></a><span data-ttu-id="a7f82-239">CSng 示例</span><span class="sxs-lookup"><span data-stu-id="a7f82-239">CSng Example</span></span>  
 <span data-ttu-id="a7f82-240">下面的示例使用`CSng`函数以将值转换为`Single`。</span><span class="sxs-lookup"><span data-stu-id="a7f82-240">The following example uses the `CSng` function to convert values to `Single`.</span></span>  
  
 [!code-vb[VbVbalrFunctions#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#13)]  
  
## <a name="cstr-example"></a><span data-ttu-id="a7f82-241">CStr 示例</span><span class="sxs-lookup"><span data-stu-id="a7f82-241">CStr Example</span></span>  
 <span data-ttu-id="a7f82-242">下面的示例使用`CStr`函数将转换为数字值`String`。</span><span class="sxs-lookup"><span data-stu-id="a7f82-242">The following example uses the `CStr` function to convert a numeric value to `String`.</span></span>  
  
 [!code-vb[VbVbalrFunctions#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#14)]  
  
 <span data-ttu-id="a7f82-243">下面的示例使用`CStr`函数将转换`Date`值到`String`值。</span><span class="sxs-lookup"><span data-stu-id="a7f82-243">The following example uses the `CStr` function to convert `Date` values to `String` values.</span></span>  
  
 [!code-vb[VbVbalrFunctions#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#15)]  
  
 <span data-ttu-id="a7f82-244">`CStr` 始终呈现`Date`采用当前区域设置，例如，标准的短格式的值"2003 年 6 月 15 日下午 4:35:47"。</span><span class="sxs-lookup"><span data-stu-id="a7f82-244">`CStr` always renders a `Date` value in the standard short format for the current locale, for example, "6/15/2003 4:35:47 PM".</span></span> <span data-ttu-id="a7f82-245">但是，`CStr`禁止*中性值*1/1/0001 的日期和时间的 00:00:00。</span><span class="sxs-lookup"><span data-stu-id="a7f82-245">However, `CStr` suppresses the *neutral values* of 1/1/0001 for the date and 00:00:00 for the time.</span></span>  
  
 <span data-ttu-id="a7f82-246">有关详细信息返回的值`CStr`，请参阅[CStr 函数的返回值](../../../visual-basic/language-reference/functions/return-values-for-the-cstr-function.md)。</span><span class="sxs-lookup"><span data-stu-id="a7f82-246">For more detail on the values returned by `CStr`, see [Return Values for the CStr Function](../../../visual-basic/language-reference/functions/return-values-for-the-cstr-function.md).</span></span>  
  
## <a name="cuint-example"></a><span data-ttu-id="a7f82-247">CUInt 示例</span><span class="sxs-lookup"><span data-stu-id="a7f82-247">CUInt Example</span></span>  
 <span data-ttu-id="a7f82-248">下面的示例使用`CUInt`函数将转换为数字值`UInteger`。</span><span class="sxs-lookup"><span data-stu-id="a7f82-248">The following example uses the `CUInt` function to convert a numeric value to `UInteger`.</span></span>  
  
 [!code-vb[VbVbalrFunctions#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#16)]  
  
## <a name="culng-example"></a><span data-ttu-id="a7f82-249">CULng 示例</span><span class="sxs-lookup"><span data-stu-id="a7f82-249">CULng Example</span></span>  
 <span data-ttu-id="a7f82-250">下面的示例使用`CULng`函数将转换为数字值`ULong`。</span><span class="sxs-lookup"><span data-stu-id="a7f82-250">The following example uses the `CULng` function to convert a numeric value to `ULong`.</span></span>  
  
 [!code-vb[VbVbalrFunctions#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#17)]  
  
## <a name="cushort-example"></a><span data-ttu-id="a7f82-251">CUShort 示例</span><span class="sxs-lookup"><span data-stu-id="a7f82-251">CUShort Example</span></span>  
 <span data-ttu-id="a7f82-252">下面的示例使用`CUShort`函数将转换为数字值`UShort`。</span><span class="sxs-lookup"><span data-stu-id="a7f82-252">The following example uses the `CUShort` function to convert a numeric value to `UShort`.</span></span>  
  
 [!code-vb[VbVbalrFunctions#18](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#18)]  
  
## <a name="see-also"></a><span data-ttu-id="a7f82-253">请参阅</span><span class="sxs-lookup"><span data-stu-id="a7f82-253">See also</span></span>

- <xref:Microsoft.VisualBasic.Strings.Asc%2A>
- <xref:Microsoft.VisualBasic.Strings.AscW%2A>
- <xref:Microsoft.VisualBasic.Strings.Chr%2A>
- <xref:Microsoft.VisualBasic.Strings.ChrW%2A>
- <xref:Microsoft.VisualBasic.Conversion.Int%2A>
- <xref:Microsoft.VisualBasic.Conversion.Fix%2A>
- <xref:Microsoft.VisualBasic.Strings.Format%2A>
- <xref:Microsoft.VisualBasic.Conversion.Hex%2A>
- <xref:Microsoft.VisualBasic.Conversion.Oct%2A>
- <xref:Microsoft.VisualBasic.Conversion.Str%2A>
- <xref:Microsoft.VisualBasic.Conversion.Val%2A>
- [<span data-ttu-id="a7f82-254">转换函数</span><span class="sxs-lookup"><span data-stu-id="a7f82-254">Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/conversion-functions.md)
- [<span data-ttu-id="a7f82-255">在 Visual Basic 中的类型转换</span><span class="sxs-lookup"><span data-stu-id="a7f82-255">Type Conversions in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)
