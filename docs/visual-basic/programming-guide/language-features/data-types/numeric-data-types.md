---
title: "数值数据类型 (Visual Basic 中) |Microsoft 文档"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- integral types, Visual Basic
- Short data type, numeric data types
- Double data type, numeric data types
- Long data type, Visual Basic numeric data types
- numbers, whole
- fractions
- numbers
- whole numbers
- integer numbers
- numbers, integer
- fractional data types
- mantissas, of fractional numbers
- mantissas
- data types [Visual Basic], numeric
- Integer data type, numeric data types
- exponent, of fractional numbers
- integers
- numeric data types, Visual Basic
- Single data type, numeric types
- Decimal data type, numeric data types
ms.assetid: a27bd4d0-7e14-43eb-9cc4-b42eaab323c9
caps.latest.revision: 25
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: af87b895c04cf89ba217c9c3a46dc259103d50b4
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017

---
# <a name="numeric-data-types-visual-basic"></a><span data-ttu-id="15986-102">数值型数据类型 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="15986-102">Numeric Data Types (Visual Basic)</span></span>
[!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]<span data-ttu-id="15986-103">提供几个*数值数据类型*来处理各种表示形式之间的数字。</span><span class="sxs-lookup"><span data-stu-id="15986-103"> supplies several *numeric data types* for handling numbers in various representations.</span></span> <span data-ttu-id="15986-104">*整型*类型只表示整数 （正数、 负数和零），和*nonintegral*类型带有整数和小数部分表示的数字。</span><span class="sxs-lookup"><span data-stu-id="15986-104">*Integral* types represent only whole numbers (positive, negative, and zero), and *nonintegral* types represent numbers with both integer and fractional parts.</span></span>  
  
 <span data-ttu-id="15986-105">显示通过并行进行比较的表为[!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]数据类型，请参阅[数据类型](../../../../visual-basic/language-reference/data-types/data-type-summary.md)。</span><span class="sxs-lookup"><span data-stu-id="15986-105">For a table showing a side-by-side comparison of the [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] data types, see [Data Types](../../../../visual-basic/language-reference/data-types/data-type-summary.md).</span></span>  
  
## <a name="integral-numeric-types"></a><span data-ttu-id="15986-106">整型数值类型</span><span class="sxs-lookup"><span data-stu-id="15986-106">Integral Numeric Types</span></span>  
 <span data-ttu-id="15986-107">*整数数据类型*是指那些表示没有小数部分的唯一数字。</span><span class="sxs-lookup"><span data-stu-id="15986-107">*Integral data types* are those that represent only numbers without fractional parts.</span></span>  
  
 <span data-ttu-id="15986-108">*签名*整数数据类型是[SByte 数据类型](../../../../visual-basic/language-reference/data-types/sbyte-data-type.md)（8 位）、 [Short 数据类型](../../../../visual-basic/language-reference/data-types/short-data-type.md)（16 位）、[整数数据类型](../../../../visual-basic/language-reference/data-types/integer-data-type.md)（32-位） 和[Long 数据类型](../../../../visual-basic/language-reference/data-types/long-data-type.md)（64 位）。</span><span class="sxs-lookup"><span data-stu-id="15986-108">The *signed* integral data types are [SByte Data Type](../../../../visual-basic/language-reference/data-types/sbyte-data-type.md) (8-bit), [Short Data Type](../../../../visual-basic/language-reference/data-types/short-data-type.md) (16-bit), [Integer Data Type](../../../../visual-basic/language-reference/data-types/integer-data-type.md) (32-bit), and [Long Data Type](../../../../visual-basic/language-reference/data-types/long-data-type.md) (64-bit).</span></span> <span data-ttu-id="15986-109">如果某个变量总是存储整数而不是小数数字，将其声明为这些类型之一。</span><span class="sxs-lookup"><span data-stu-id="15986-109">If a variable always stores integers rather than fractional numbers, declare it as one of these types.</span></span>  
  
 <span data-ttu-id="15986-110">*无符号*整型[Byte 数据类型](../../../../visual-basic/language-reference/data-types/byte-data-type.md)（8 位）、 [UShort 数据类型](../../../../visual-basic/language-reference/data-types/ushort-data-type.md)（16 位）、 [UInteger 数据类型](../../../../visual-basic/language-reference/data-types/uinteger-data-type.md)（32-位） 和[ULong 数据类型](../../../../visual-basic/language-reference/data-types/ulong-data-type.md)（64 位）。</span><span class="sxs-lookup"><span data-stu-id="15986-110">The *unsigned* integral types are [Byte Data Type](../../../../visual-basic/language-reference/data-types/byte-data-type.md) (8-bit), [UShort Data Type](../../../../visual-basic/language-reference/data-types/ushort-data-type.md) (16-bit), [UInteger Data Type](../../../../visual-basic/language-reference/data-types/uinteger-data-type.md) (32-bit), and [ULong Data Type](../../../../visual-basic/language-reference/data-types/ulong-data-type.md) (64-bit).</span></span> <span data-ttu-id="15986-111">如果某个变量包含二进制数据或未知种类的数据，将其声明为这些类型之一。</span><span class="sxs-lookup"><span data-stu-id="15986-111">If a variable contains binary data, or data of unknown nature, declare it as one of these types.</span></span>  
  
### <a name="performance"></a><span data-ttu-id="15986-112">性能</span><span class="sxs-lookup"><span data-stu-id="15986-112">Performance</span></span>  
 <span data-ttu-id="15986-113">算术运算是更快速度和整数类型，而不与其他数据类型。</span><span class="sxs-lookup"><span data-stu-id="15986-113">Arithmetic operations are faster with integral types than with other data types.</span></span> <span data-ttu-id="15986-114">它们是使用最快`Integer`和`UInteger`中的类型[!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]。</span><span class="sxs-lookup"><span data-stu-id="15986-114">They are fastest with the `Integer` and `UInteger` types in [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)].</span></span>  
  
### <a name="large-integers"></a><span data-ttu-id="15986-115">大整数</span><span class="sxs-lookup"><span data-stu-id="15986-115">Large Integers</span></span>  
 <span data-ttu-id="15986-116">如果您需要存储的整数大于`Integer`可以容纳的数据类型，则可以使用`Long`改为数据类型。</span><span class="sxs-lookup"><span data-stu-id="15986-116">If you need to hold an integer larger than the `Integer` data type can hold, you can use the `Long` data type instead.</span></span> <span data-ttu-id="15986-117">`Long`变量可以存储从-9223372036854775808 到 9223372036854775807 的数字。</span><span class="sxs-lookup"><span data-stu-id="15986-117">`Long` variables can hold numbers from -9,223,372,036,854,775,808 through 9,223,372,036,854,775,807.</span></span> <span data-ttu-id="15986-118">使用操作`Long`速度稍慢于具有`Integer`。</span><span class="sxs-lookup"><span data-stu-id="15986-118">Operations with `Long` are slightly slower than with `Integer`.</span></span>  
  
 <span data-ttu-id="15986-119">如果您需要更大的值，则可以使用[Decimal 数据类型](../../../../visual-basic/language-reference/data-types/decimal-data-type.md)。</span><span class="sxs-lookup"><span data-stu-id="15986-119">If you need even larger values, you can use the [Decimal Data Type](../../../../visual-basic/language-reference/data-types/decimal-data-type.md).</span></span> <span data-ttu-id="15986-120">您可以存储从-79228162514264337593543950335 到 79228162514264337593543950335 的数字`Decimal`如果不使用任何小数位数的变量。</span><span class="sxs-lookup"><span data-stu-id="15986-120">You can hold numbers from -79,228,162,514,264,337,593,543,950,335 through 79,228,162,514,264,337,593,543,950,335 in a `Decimal` variable if you do not use any decimal places.</span></span> <span data-ttu-id="15986-121">但是，操作与`Decimal`数字是远远慢于速度与任何其他数值数据类型。</span><span class="sxs-lookup"><span data-stu-id="15986-121">However, operations with `Decimal` numbers are considerably slower than with any other numeric data type.</span></span>  
  
### <a name="small-integers"></a><span data-ttu-id="15986-122">小整数</span><span class="sxs-lookup"><span data-stu-id="15986-122">Small Integers</span></span>  
 <span data-ttu-id="15986-123">如果您不需要的全部`Integer`数据类型，则可以使用`Short`数据类型，它包含从-32768 到 32767 的整数。</span><span class="sxs-lookup"><span data-stu-id="15986-123">If you do not need the full range of the `Integer` data type, you can use the `Short` data type, which can hold integers from -32,768 through 32,767.</span></span> <span data-ttu-id="15986-124">对于最小的整数范围，`SByte`数据类型都包含从-128 到 127 的整数。</span><span class="sxs-lookup"><span data-stu-id="15986-124">For the smallest integer range, the `SByte` data type holds integers from -128 through 127.</span></span> <span data-ttu-id="15986-125">如果您有大量的变量包含小整数，公共语言运行时可以有时将存储您`Short`和`SByte`变量更高效地，以节省内存消耗。</span><span class="sxs-lookup"><span data-stu-id="15986-125">If you have a very large number of variables that hold small integers, the common language runtime can sometimes store your `Short` and `SByte` variables more efficiently and save memory consumption.</span></span> <span data-ttu-id="15986-126">但是，操作与`Short`和`SByte`会稍微慢一些比与`Integer`。</span><span class="sxs-lookup"><span data-stu-id="15986-126">However, operations with `Short` and `SByte` are somewhat slower than with `Integer`.</span></span>  
  
### <a name="unsigned-integers"></a><span data-ttu-id="15986-127">无符号的整数</span><span class="sxs-lookup"><span data-stu-id="15986-127">Unsigned Integers</span></span>  
 <span data-ttu-id="15986-128">如果您知道您的变量永远不需要保存为负数，则可以使用*无符号类型*`Byte`， `UShort`， `UInteger`，和`ULong`。</span><span class="sxs-lookup"><span data-stu-id="15986-128">If you know that your variable never needs to hold a negative number, you can use the *unsigned types*`Byte`, `UShort`, `UInteger`, and `ULong`.</span></span> <span data-ttu-id="15986-129">上述每种数据类型可以容纳一个正整数值大小的两倍作为其相应的有符号类型 (`SByte`， `Short`， `Integer`，和`Long`)。</span><span class="sxs-lookup"><span data-stu-id="15986-129">Each of these data types can hold a positive integer twice as large as its corresponding signed type (`SByte`, `Short`, `Integer`, and `Long`).</span></span> <span data-ttu-id="15986-130">就性能来说，每个无符号的类型是效率及其对应的有符号类型一样。</span><span class="sxs-lookup"><span data-stu-id="15986-130">In terms of performance, each unsigned type is exactly as efficient as its corresponding signed type.</span></span> <span data-ttu-id="15986-131">具体而言，`UInteger`与共享`Integer`都被认为最有效的所有基本数值数据类型。</span><span class="sxs-lookup"><span data-stu-id="15986-131">In particular, `UInteger` shares with `Integer` the distinction of being the most efficient of all the elementary numeric data types.</span></span>  
  
## <a name="nonintegral-numeric-types"></a><span data-ttu-id="15986-132">非整型数值类型</span><span class="sxs-lookup"><span data-stu-id="15986-132">Nonintegral Numeric Types</span></span>  
 <span data-ttu-id="15986-133">*非整数数据类型*是指那些表示带有整数和小数部分的数字。</span><span class="sxs-lookup"><span data-stu-id="15986-133">*Nonintegral data types* are those that represent numbers with both integer and fractional parts.</span></span>  
  
 <span data-ttu-id="15986-134">非整型数值数据类型为`Decimal`（128 位定点）[单一数据类型](../../../../visual-basic/language-reference/data-types/single-data-type.md)（32 位浮点） 和[Double 数据类型](../../../../visual-basic/language-reference/data-types/double-data-type.md)（64 位浮点数）。</span><span class="sxs-lookup"><span data-stu-id="15986-134">The nonintegral numeric data types are `Decimal` (128-bit fixed point), [Single Data Type](../../../../visual-basic/language-reference/data-types/single-data-type.md) (32-bit floating point), and [Double Data Type](../../../../visual-basic/language-reference/data-types/double-data-type.md) (64-bit floating point).</span></span> <span data-ttu-id="15986-135">它们是已全部签名的类型。</span><span class="sxs-lookup"><span data-stu-id="15986-135">They are all signed types.</span></span> <span data-ttu-id="15986-136">如果一个变量可以包含一小部分，将其声明为这些类型之一。</span><span class="sxs-lookup"><span data-stu-id="15986-136">If a variable can contain a fraction, declare it as one of these types.</span></span>  
  
 <span data-ttu-id="15986-137">`Decimal`不是浮点数据类型。</span><span class="sxs-lookup"><span data-stu-id="15986-137">`Decimal` is not a floating-point data type.</span></span> <span data-ttu-id="15986-138">`Decimal`数字具有二进制整数值和一个指定的值的哪一部分是小数部分的整数比例因子。</span><span class="sxs-lookup"><span data-stu-id="15986-138">`Decimal` numbers have a binary integer value and an integer scaling factor that specifies what portion of the value is a decimal fraction.</span></span>  
  
 <span data-ttu-id="15986-139">您可以使用`Decimal`货币值的变量。</span><span class="sxs-lookup"><span data-stu-id="15986-139">You can use `Decimal` variables for money values.</span></span> <span data-ttu-id="15986-140">优点是值的精度。</span><span class="sxs-lookup"><span data-stu-id="15986-140">The advantage is the precision of the values.</span></span> <span data-ttu-id="15986-141">`Double`数据类型是速度更快，并且需要更少的内存，但它可能会发生舍入误差。</span><span class="sxs-lookup"><span data-stu-id="15986-141">The `Double` data type is faster and requires less memory, but it is subject to rounding errors.</span></span> <span data-ttu-id="15986-142">`Decimal`数据类型可保持完整精度为 28 位小数。</span><span class="sxs-lookup"><span data-stu-id="15986-142">The `Decimal` data type retains complete accuracy to 28 decimal places.</span></span>  
  
 <span data-ttu-id="15986-143">浮点 (`Single`和`Double`) 数字具有更大范围比`Decimal`数字，但可能会导致舍入误差。</span><span class="sxs-lookup"><span data-stu-id="15986-143">Floating-point (`Single` and `Double`) numbers have larger ranges than `Decimal` numbers but can be subject to rounding errors.</span></span> <span data-ttu-id="15986-144">浮点类型都支持有效位比`Decimal`，但可以表示更大的值。</span><span class="sxs-lookup"><span data-stu-id="15986-144">Floating-point types support fewer significant digits than `Decimal` but can represent values of greater magnitude.</span></span>  
  
 <span data-ttu-id="15986-145">非整型数值可以用来表示为 mmmEeee，mmm 即*尾数*（有效位） 和 eee 是*指数*（10 的幂）。</span><span class="sxs-lookup"><span data-stu-id="15986-145">Nonintegral number values can be expressed as mmmEeee, in which mmm is the *mantissa* (the significant digits) and eee is the *exponent* (a power of 10).</span></span> <span data-ttu-id="15986-146">非整型的最高的正值将为 7.9228162514264337593543950335 e + 28 `Decimal`，3.4028235 e + 38 个`Single`，1.79769313486231570 e + 308 `Double`。</span><span class="sxs-lookup"><span data-stu-id="15986-146">The highest positive values of the nonintegral types are 7.9228162514264337593543950335E+28 for `Decimal`, 3.4028235E+38 for `Single`, and 1.79769313486231570E+308 for `Double`.</span></span>  
  
### <a name="performance"></a><span data-ttu-id="15986-147">性能</span><span class="sxs-lookup"><span data-stu-id="15986-147">Performance</span></span>  
 <span data-ttu-id="15986-148">`Double`因为当前平台上的处理器执行以双精度浮点运算，则是最有效的小数数据类型。</span><span class="sxs-lookup"><span data-stu-id="15986-148">`Double` is the most efficient of the fractional data types, because the processors on current platforms perform floating-point operations in double precision.</span></span> <span data-ttu-id="15986-149">但是，操作与`Double`与整数类型，如速度快`Integer`。</span><span class="sxs-lookup"><span data-stu-id="15986-149">However, operations with `Double` are not as fast as with the integral types such as `Integer`.</span></span>  
  
### <a name="small-magnitudes"></a><span data-ttu-id="15986-150">小量值</span><span class="sxs-lookup"><span data-stu-id="15986-150">Small Magnitudes</span></span>  
 <span data-ttu-id="15986-151">对于具有最小可能的数值 （接近 0），数字`Double`变量可以存储数字越小越-4.94065645841246544 e-324 的负值，4.94065645841246544 e-324 的正值。</span><span class="sxs-lookup"><span data-stu-id="15986-151">For numbers with the smallest possible magnitude (closest to 0), `Double` variables can hold numbers as small as -4.94065645841246544E-324 for negative values and 4.94065645841246544E-324 for positive values.</span></span>  
  
### <a name="small-fractional-numbers"></a><span data-ttu-id="15986-152">小小数位的数字</span><span class="sxs-lookup"><span data-stu-id="15986-152">Small Fractional Numbers</span></span>  
 <span data-ttu-id="15986-153">如果您不需要的全部`Double`数据类型，则可以使用`Single`数据类型，它可以存储从-3.4028235 e + 38 到 3.4028235 e + 38 之间的浮点数。</span><span class="sxs-lookup"><span data-stu-id="15986-153">If you do not need the full range of the `Double` data type, you can use the `Single` data type, which can hold floating-point numbers from -3.4028235E+38 through 3.4028235E+38.</span></span> <span data-ttu-id="15986-154">最小最小量值为`Single`变量为-1.401298 e-45 对于负值，范围为 1.401298 e-45, 正值 45。</span><span class="sxs-lookup"><span data-stu-id="15986-154">The smallest magnitudes for `Single` variables are -1.401298E-45 for negative values and 1.401298E-45 for positive values.</span></span> <span data-ttu-id="15986-155">如果您有大量的变量包含小浮点数，公共语言运行时可以有时将存储您`Single`变量更高效地，以节省内存消耗。</span><span class="sxs-lookup"><span data-stu-id="15986-155">If you have a very large number of variables that hold small floating-point numbers, the common language runtime can sometimes store your `Single` variables more efficiently and save memory consumption.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="15986-156">另请参阅</span><span class="sxs-lookup"><span data-stu-id="15986-156">See Also</span></span>  
 <span data-ttu-id="15986-157">[基本数据类型](../../../../visual-basic/programming-guide/language-features/data-types/elementary-data-types.md) </span><span class="sxs-lookup"><span data-stu-id="15986-157">[Elementary Data Types](../../../../visual-basic/programming-guide/language-features/data-types/elementary-data-types.md) </span></span>  
<span data-ttu-id="15986-158"> [字符数据类型](../../../../visual-basic/programming-guide/language-features/data-types/character-data-types.md) </span><span class="sxs-lookup"><span data-stu-id="15986-158"> [Character Data Types](../../../../visual-basic/programming-guide/language-features/data-types/character-data-types.md) </span></span>  
<span data-ttu-id="15986-159"> [其他数据类型](../../../../visual-basic/programming-guide/language-features/data-types/miscellaneous-data-types.md) </span><span class="sxs-lookup"><span data-stu-id="15986-159"> [Miscellaneous Data Types](../../../../visual-basic/programming-guide/language-features/data-types/miscellaneous-data-types.md) </span></span>  
<span data-ttu-id="15986-160"> [数据类型疑难解答](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md) </span><span class="sxs-lookup"><span data-stu-id="15986-160"> [Troubleshooting Data Types](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md) </span></span>  
<span data-ttu-id="15986-161"> [如何：调用采用无符号类型的 Windows 函数](../../../../visual-basic/programming-guide/com-interop/how-to-call-a-windows-function-that-takes-unsigned-types.md)</span><span class="sxs-lookup"><span data-stu-id="15986-161"> [How to: Call a Windows Function that Takes Unsigned Types](../../../../visual-basic/programming-guide/com-interop/how-to-call-a-windows-function-that-takes-unsigned-types.md)</span></span>
