---
title: 隐式转换和显式转换
ms.date: 07/20/2015
helpviewer_keywords:
- conversions [Visual Basic], type
- variables [Visual Basic], changing data type
- casting
- conversions [Visual Basic], data type
- type conversion [Visual Basic], implicit conversions
- CType function [Visual Basic], conversions
- casting, data types
- data type conversion [Visual Basic], explicit
- type conversion [Visual Basic], explicit conversions
- data types [Visual Basic], casting
- conversions [Visual Basic], implicit
- explicit data type conversions [Visual Basic]
- conversions [Visual Basic]
- changing data types [Visual Basic]
- conversions [Visual Basic], explicit
- data type conversion [Visual Basic], implicit
- implicit data type conversions [Visual Basic]
ms.assetid: 77de1659-af8a-492c-967e-e7ef60ccce66
ms.openlocfilehash: b7215933cec89b7023f08e8996a283b39b3a3c83
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74346361"
---
# <a name="implicit-and-explicit-conversions-visual-basic"></a><span data-ttu-id="54710-102">隐式转换和显式转换 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="54710-102">Implicit and Explicit Conversions (Visual Basic)</span></span>

<span data-ttu-id="54710-103">*隐式转换*在源代码中无需任何特殊语法。</span><span class="sxs-lookup"><span data-stu-id="54710-103">An *implicit conversion* does not require any special syntax in the source code.</span></span> <span data-ttu-id="54710-104">在下面的示例中，Visual Basic 将 `k` 的值隐式转换为单精度浮点值，然后将其分配给 `q`。</span><span class="sxs-lookup"><span data-stu-id="54710-104">In the following example, Visual Basic implicitly converts the value of `k` to a single-precision floating-point value before assigning it to `q`.</span></span>

```vb
Dim k As Integer
Dim q As Double
' Integer widens to Double, so you can do this with Option Strict On.
k = 432
q = k
```

<span data-ttu-id="54710-105">*显式转换*使用类型转换关键字。</span><span class="sxs-lookup"><span data-stu-id="54710-105">An *explicit conversion* uses a type conversion keyword.</span></span> <span data-ttu-id="54710-106">Visual Basic 提供了几个这样的关键字，这些关键字将括号中的表达式强制转换为所需的数据类型。</span><span class="sxs-lookup"><span data-stu-id="54710-106">Visual Basic provides several such keywords, which coerce an expression in parentheses to the desired data type.</span></span> <span data-ttu-id="54710-107">这些关键字的作用类似于函数，但编译器将生成内联代码，因此执行速度要比使用函数调用稍快。</span><span class="sxs-lookup"><span data-stu-id="54710-107">These keywords act like functions, but the compiler generates the code inline, so execution is slightly faster than with a function call.</span></span>

<span data-ttu-id="54710-108">在前面的示例的以下扩展中，`CInt` 关键字将 `q` 的值转换回整数，然后将其分配给 `k`。</span><span class="sxs-lookup"><span data-stu-id="54710-108">In the following extension of the preceding example, the `CInt` keyword converts the value of `q` back to an integer before assigning it to `k`.</span></span>

```vb
' q had been assigned the value 432 from k.
q = Math.Sqrt(q)
k = CInt(q)
' k now has the value 21 (rounded square root of 432).
```

## <a name="conversion-keywords"></a><span data-ttu-id="54710-109">转换关键字</span><span class="sxs-lookup"><span data-stu-id="54710-109">Conversion Keywords</span></span>

<span data-ttu-id="54710-110">下表显示了可用的转换关键字。</span><span class="sxs-lookup"><span data-stu-id="54710-110">The following table shows the available conversion keywords.</span></span>

|<span data-ttu-id="54710-111">类型转换关键字</span><span class="sxs-lookup"><span data-stu-id="54710-111">Type conversion keyword</span></span>|<span data-ttu-id="54710-112">将表达式转换为数据类型</span><span class="sxs-lookup"><span data-stu-id="54710-112">Converts an expression to data type</span></span>|<span data-ttu-id="54710-113">允许转换的表达式的数据类型</span><span class="sxs-lookup"><span data-stu-id="54710-113">Allowable data types of expression to be converted</span></span>|
|---|---|---|
|`CBool`|[<span data-ttu-id="54710-114">Boolean 数据类型</span><span class="sxs-lookup"><span data-stu-id="54710-114">Boolean Data Type</span></span>](../../../../visual-basic/language-reference/data-types/boolean-data-type.md)|<span data-ttu-id="54710-115">任何数值类型（包括 `Byte`、`SByte`和枚举类型）、`String``Object`</span><span class="sxs-lookup"><span data-stu-id="54710-115">Any numeric type (including `Byte`, `SByte`, and enumerated types), `String`, `Object`</span></span>|
|`CByte`|[<span data-ttu-id="54710-116">Byte 数据类型</span><span class="sxs-lookup"><span data-stu-id="54710-116">Byte Data Type</span></span>](../../../../visual-basic/language-reference/data-types/byte-data-type.md)|<span data-ttu-id="54710-117">任何数值类型（包括 `SByte` 和枚举类型）、`Boolean`、`String``Object`</span><span class="sxs-lookup"><span data-stu-id="54710-117">Any numeric type (including `SByte` and enumerated types), `Boolean`, `String`, `Object`</span></span>|
|`CChar`|[<span data-ttu-id="54710-118">Char 数据类型</span><span class="sxs-lookup"><span data-stu-id="54710-118">Char Data Type</span></span>](../../../../visual-basic/language-reference/data-types/char-data-type.md)|<span data-ttu-id="54710-119">`String`, `Object`</span><span class="sxs-lookup"><span data-stu-id="54710-119">`String`, `Object`</span></span>|
|`CDate`|[<span data-ttu-id="54710-120">Date 数据类型</span><span class="sxs-lookup"><span data-stu-id="54710-120">Date Data Type</span></span>](../../../../visual-basic/language-reference/data-types/date-data-type.md)|<span data-ttu-id="54710-121">`String`, `Object`</span><span class="sxs-lookup"><span data-stu-id="54710-121">`String`, `Object`</span></span>|
|`CDbl`|[<span data-ttu-id="54710-122">Double 数据类型</span><span class="sxs-lookup"><span data-stu-id="54710-122">Double Data Type</span></span>](../../../../visual-basic/language-reference/data-types/double-data-type.md)|<span data-ttu-id="54710-123">任何数值类型（包括 `Byte`、`SByte`和枚举类型）、`Boolean`、`String`、`Object`</span><span class="sxs-lookup"><span data-stu-id="54710-123">Any numeric type (including `Byte`, `SByte`, and enumerated types), `Boolean`, `String`, `Object`</span></span>|
|`CDec`|[<span data-ttu-id="54710-124">Decimal 数据类型</span><span class="sxs-lookup"><span data-stu-id="54710-124">Decimal Data Type</span></span>](../../../../visual-basic/language-reference/data-types/decimal-data-type.md)|<span data-ttu-id="54710-125">任何数值类型（包括 `Byte`、`SByte`和枚举类型）、`Boolean`、`String`、`Object`</span><span class="sxs-lookup"><span data-stu-id="54710-125">Any numeric type (including `Byte`, `SByte`, and enumerated types), `Boolean`, `String`, `Object`</span></span>|
|`CInt`|[<span data-ttu-id="54710-126">Integer 数据类型</span><span class="sxs-lookup"><span data-stu-id="54710-126">Integer Data Type</span></span>](../../../../visual-basic/language-reference/data-types/integer-data-type.md)|<span data-ttu-id="54710-127">任何数值类型（包括 `Byte`、`SByte`和枚举类型）、`Boolean`、`String`、`Object`</span><span class="sxs-lookup"><span data-stu-id="54710-127">Any numeric type (including `Byte`, `SByte`, and enumerated types), `Boolean`, `String`, `Object`</span></span>|
|`CLng`|[<span data-ttu-id="54710-128">Long 数据类型</span><span class="sxs-lookup"><span data-stu-id="54710-128">Long Data Type</span></span>](../../../../visual-basic/language-reference/data-types/long-data-type.md)|<span data-ttu-id="54710-129">任何数值类型（包括 `Byte`、`SByte`和枚举类型）、`Boolean`、`String`、`Object`</span><span class="sxs-lookup"><span data-stu-id="54710-129">Any numeric type (including `Byte`, `SByte`, and enumerated types), `Boolean`, `String`, `Object`</span></span>|
|`CObj`|[<span data-ttu-id="54710-130">Object 数据类型</span><span class="sxs-lookup"><span data-stu-id="54710-130">Object Data Type</span></span>](../../../../visual-basic/language-reference/data-types/object-data-type.md)|<span data-ttu-id="54710-131">任何类型</span><span class="sxs-lookup"><span data-stu-id="54710-131">Any type</span></span>|
|`CSByte`|[<span data-ttu-id="54710-132">SByte 数据类型</span><span class="sxs-lookup"><span data-stu-id="54710-132">SByte Data Type</span></span>](../../../../visual-basic/language-reference/data-types/sbyte-data-type.md)|<span data-ttu-id="54710-133">任何数值类型（包括 `Byte` 和枚举类型）、`Boolean`、`String``Object`</span><span class="sxs-lookup"><span data-stu-id="54710-133">Any numeric type (including `Byte` and enumerated types), `Boolean`, `String`, `Object`</span></span>|
|`CShort`|[<span data-ttu-id="54710-134">Short 数据类型</span><span class="sxs-lookup"><span data-stu-id="54710-134">Short Data Type</span></span>](../../../../visual-basic/language-reference/data-types/short-data-type.md)|<span data-ttu-id="54710-135">任何数值类型（包括 `Byte`、`SByte`和枚举类型）、`Boolean`、`String`、`Object`</span><span class="sxs-lookup"><span data-stu-id="54710-135">Any numeric type (including `Byte`, `SByte`, and enumerated types), `Boolean`, `String`, `Object`</span></span>|
|`CSng`|[<span data-ttu-id="54710-136">Single 数据类型</span><span class="sxs-lookup"><span data-stu-id="54710-136">Single Data Type</span></span>](../../../../visual-basic/language-reference/data-types/single-data-type.md)|<span data-ttu-id="54710-137">任何数值类型（包括 `Byte`、`SByte`和枚举类型）、`Boolean`、`String`、`Object`</span><span class="sxs-lookup"><span data-stu-id="54710-137">Any numeric type (including `Byte`, `SByte`, and enumerated types), `Boolean`, `String`, `Object`</span></span>|
|`CStr`|[<span data-ttu-id="54710-138">String 数据类型</span><span class="sxs-lookup"><span data-stu-id="54710-138">String Data Type</span></span>](../../../../visual-basic/language-reference/data-types/string-data-type.md)|<span data-ttu-id="54710-139">任何数值类型（包括 `Byte`、`SByte`和枚举类型）、`Boolean`、`Char`、`Char` 数组、`Date`、`Object`</span><span class="sxs-lookup"><span data-stu-id="54710-139">Any numeric type (including `Byte`, `SByte`, and enumerated types), `Boolean`, `Char`, `Char` array, `Date`, `Object`</span></span>|
|`CType`|<span data-ttu-id="54710-140">在逗号（`,`）之后指定的类型</span><span class="sxs-lookup"><span data-stu-id="54710-140">Type specified following the comma (`,`)</span></span>|<span data-ttu-id="54710-141">转换为*基本数据类型*（包括基本类型的数组）时，为相应的转换关键字允许的相同类型</span><span class="sxs-lookup"><span data-stu-id="54710-141">When converting to an *elementary data type* (including an array of an elementary type), the same types as allowed for the corresponding conversion keyword</span></span><br /><br /> <span data-ttu-id="54710-142">转换为*复合数据类型*时，它实现的接口和它所继承的类</span><span class="sxs-lookup"><span data-stu-id="54710-142">When converting to a *composite data type*, the interfaces it implements and the classes from which it inherits</span></span><br /><br /> <span data-ttu-id="54710-143">转换为您在其上重载 `CType`的类或结构时，该类或结构</span><span class="sxs-lookup"><span data-stu-id="54710-143">When converting to a class or structure on which you have overloaded `CType`, that class or structure</span></span>|
|`CUInt`|[<span data-ttu-id="54710-144">UInteger 数据类型</span><span class="sxs-lookup"><span data-stu-id="54710-144">UInteger Data Type</span></span>](../../../../visual-basic/language-reference/data-types/uinteger-data-type.md)|<span data-ttu-id="54710-145">任何数值类型（包括 `Byte`、`SByte`和枚举类型）、`Boolean`、`String`、`Object`</span><span class="sxs-lookup"><span data-stu-id="54710-145">Any numeric type (including `Byte`, `SByte`, and enumerated types), `Boolean`, `String`, `Object`</span></span>|
|`CULng`|[<span data-ttu-id="54710-146">ULong 数据类型</span><span class="sxs-lookup"><span data-stu-id="54710-146">ULong Data Type</span></span>](../../../../visual-basic/language-reference/data-types/ulong-data-type.md)|<span data-ttu-id="54710-147">任何数值类型（包括 `Byte`、`SByte`和枚举类型）、`Boolean`、`String`、`Object`</span><span class="sxs-lookup"><span data-stu-id="54710-147">Any numeric type (including `Byte`, `SByte`, and enumerated types), `Boolean`, `String`, `Object`</span></span>|
|`CUShort`|[<span data-ttu-id="54710-148">UShort 数据类型</span><span class="sxs-lookup"><span data-stu-id="54710-148">UShort Data Type</span></span>](../../../../visual-basic/language-reference/data-types/ushort-data-type.md)|<span data-ttu-id="54710-149">任何数值类型（包括 `Byte`、`SByte`和枚举类型）、`Boolean`、`String`、`Object`</span><span class="sxs-lookup"><span data-stu-id="54710-149">Any numeric type (including `Byte`, `SByte`, and enumerated types), `Boolean`, `String`, `Object`</span></span>|

## <a name="the-ctype-function"></a><span data-ttu-id="54710-150">CType 函数</span><span class="sxs-lookup"><span data-stu-id="54710-150">The CType Function</span></span>

<span data-ttu-id="54710-151">[CType 函数](../../../../visual-basic/language-reference/functions/ctype-function.md)对两个参数进行运算。</span><span class="sxs-lookup"><span data-stu-id="54710-151">The [CType Function](../../../../visual-basic/language-reference/functions/ctype-function.md) operates on two arguments.</span></span> <span data-ttu-id="54710-152">第一个是要转换的表达式，第二个是目标数据类型或对象类。</span><span class="sxs-lookup"><span data-stu-id="54710-152">The first is the expression to be converted, and the second is the destination data type or object class.</span></span> <span data-ttu-id="54710-153">请注意，第一个参数必须是表达式，而不能是类型。</span><span class="sxs-lookup"><span data-stu-id="54710-153">Note that the first argument must be an expression, not a type.</span></span>

<span data-ttu-id="54710-154">`CType` 是*内联函数*，这意味着编译的代码通常会进行转换，而不会生成函数调用。</span><span class="sxs-lookup"><span data-stu-id="54710-154">`CType` is an *inline function*, meaning the compiled code makes the conversion, often without generating a function call.</span></span> <span data-ttu-id="54710-155">这可以提高性能。</span><span class="sxs-lookup"><span data-stu-id="54710-155">This improves performance.</span></span>

<span data-ttu-id="54710-156">有关使用其他类型转换关键字的 `CType` 比较，请参阅[DirectCast operator](../../../../visual-basic/language-reference/operators/directcast-operator.md) And [TryCast operator](../../../../visual-basic/language-reference/operators/trycast-operator.md)。</span><span class="sxs-lookup"><span data-stu-id="54710-156">For a comparison of `CType` with the other type conversion keywords, see [DirectCast Operator](../../../../visual-basic/language-reference/operators/directcast-operator.md) and [TryCast Operator](../../../../visual-basic/language-reference/operators/trycast-operator.md).</span></span>

### <a name="elementary-types"></a><span data-ttu-id="54710-157">基本类型</span><span class="sxs-lookup"><span data-stu-id="54710-157">Elementary Types</span></span>

<span data-ttu-id="54710-158">以下示例演示了 `CType` 的用法。</span><span class="sxs-lookup"><span data-stu-id="54710-158">The following example demonstrates the use of `CType`.</span></span>

```vb
k = CType(q, Integer)
' The following statement coerces w to the specific object class Label.
f = CType(w, Label)
```

### <a name="composite-types"></a><span data-ttu-id="54710-159">复合类型</span><span class="sxs-lookup"><span data-stu-id="54710-159">Composite Types</span></span>

<span data-ttu-id="54710-160">您可以使用 `CType` 将值转换为复合数据类型以及基本类型。</span><span class="sxs-lookup"><span data-stu-id="54710-160">You can use `CType` to convert values to composite data types as well as to elementary types.</span></span> <span data-ttu-id="54710-161">你还可以使用它将对象类强制转换为它的某个接口的类型，如下例所示。</span><span class="sxs-lookup"><span data-stu-id="54710-161">You can also use it to coerce an object class to the type of one of its interfaces, as in the following example.</span></span>

```vb
' Assume class cZone implements interface iZone.
Dim h As Object
' The first argument to CType must be an expression, not a type.
Dim cZ As cZone
' The following statement coerces a cZone object to its interface iZone.
h = CType(cZ, iZone)
```

### <a name="array-types"></a><span data-ttu-id="54710-162">数组类型</span><span class="sxs-lookup"><span data-stu-id="54710-162">Array Types</span></span>

<span data-ttu-id="54710-163">`CType` 还可以转换数组数据类型，如下面的示例中所示。</span><span class="sxs-lookup"><span data-stu-id="54710-163">`CType` can also convert array data types, as in the following example.</span></span>

```vb
Dim v() As classV
Dim obArray() As Object
' Assume some object array has been assigned to obArray.
' Check for run-time type compatibility.
If TypeOf obArray Is classV()
    ' obArray can be converted to classV.
    v = CType(obArray, classV())
End If
```

<span data-ttu-id="54710-164">有关详细信息和示例，请参阅[数组转换](../../../../visual-basic/programming-guide/language-features/data-types/array-conversions.md)。</span><span class="sxs-lookup"><span data-stu-id="54710-164">For more information and an example, see [Array Conversions](../../../../visual-basic/programming-guide/language-features/data-types/array-conversions.md).</span></span>

### <a name="types-defining-ctype"></a><span data-ttu-id="54710-165">定义 CType 的类型</span><span class="sxs-lookup"><span data-stu-id="54710-165">Types Defining CType</span></span>

<span data-ttu-id="54710-166">可以在已定义的类或结构上定义 `CType`。</span><span class="sxs-lookup"><span data-stu-id="54710-166">You can define `CType` on a class or structure you have defined.</span></span> <span data-ttu-id="54710-167">这使你可以将值转换为类或结构的类型。</span><span class="sxs-lookup"><span data-stu-id="54710-167">This allows you to convert values to and from the type of your class or structure.</span></span> <span data-ttu-id="54710-168">有关详细信息和示例，请参阅[如何：定义转换运算符](../../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md)。</span><span class="sxs-lookup"><span data-stu-id="54710-168">For more information and an example, see [How to: Define a Conversion Operator](../../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md).</span></span>

> [!NOTE]
> <span data-ttu-id="54710-169">与转换关键字一起使用的值必须对目标数据类型有效，否则会发生错误。</span><span class="sxs-lookup"><span data-stu-id="54710-169">Values used with a conversion keyword must be valid for the destination data type, or an error occurs.</span></span> <span data-ttu-id="54710-170">例如，如果尝试将 `Long` 转换为 `Integer`，则 `Long` 的值必须在 `Integer` 数据类型的有效范围内。</span><span class="sxs-lookup"><span data-stu-id="54710-170">For example, if you attempt to convert a `Long` to an `Integer`, the value of the `Long` must be within the valid range for the `Integer` data type.</span></span>

> [!CAUTION]
> <span data-ttu-id="54710-171">如果源类型不是派生自目标类型，则指定 `CType` 在运行时将其转换为另一类类型会失败。</span><span class="sxs-lookup"><span data-stu-id="54710-171">Specifying `CType` to convert from one class type to another fails at run time if the source type does not derive from the destination type.</span></span> <span data-ttu-id="54710-172">此类故障会引发 <xref:System.InvalidCastException> 异常。</span><span class="sxs-lookup"><span data-stu-id="54710-172">Such a failure throws an <xref:System.InvalidCastException> exception.</span></span>

<span data-ttu-id="54710-173">但是，如果其中一个类型是你已定义的结构或类，并且在该结构或类上定义 `CType`，则转换如果满足 `CType`的要求，则可能会成功。</span><span class="sxs-lookup"><span data-stu-id="54710-173">However, if one of the types is a structure or class you have defined, and if you have defined `CType` on that structure or class, a conversion can succeed if it satisfies the requirements of your `CType`.</span></span> <span data-ttu-id="54710-174">请参阅[如何：定义转换运算符](../../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md)。</span><span class="sxs-lookup"><span data-stu-id="54710-174">See [How to: Define a Conversion Operator](../../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md).</span></span>

<span data-ttu-id="54710-175">执行显式转换也称为将表达式*强制转换*为给定的数据类型或对象类。</span><span class="sxs-lookup"><span data-stu-id="54710-175">Performing an explicit conversion is also known as *casting* an expression to a given data type or object class.</span></span>

## <a name="see-also"></a><span data-ttu-id="54710-176">另请参阅</span><span class="sxs-lookup"><span data-stu-id="54710-176">See also</span></span>

- [<span data-ttu-id="54710-177">Visual Basic 中的类型转换</span><span class="sxs-lookup"><span data-stu-id="54710-177">Type Conversions in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)
- [<span data-ttu-id="54710-178">字符串和其他类型之间的转换</span><span class="sxs-lookup"><span data-stu-id="54710-178">Conversions Between Strings and Other Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/conversions-between-strings-and-other-types.md)
- [<span data-ttu-id="54710-179">如何：在 Visual Basic 中将对象转换为另一种类型</span><span class="sxs-lookup"><span data-stu-id="54710-179">How to: Convert an Object to Another Type in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/how-to-convert-an-object-to-another-type.md)
- [<span data-ttu-id="54710-180">结构</span><span class="sxs-lookup"><span data-stu-id="54710-180">Structures</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/structures.md)
- [<span data-ttu-id="54710-181">数据类型</span><span class="sxs-lookup"><span data-stu-id="54710-181">Data Types</span></span>](../../../../visual-basic/language-reference/data-types/index.md)
- [<span data-ttu-id="54710-182">Type Conversion Functions</span><span class="sxs-lookup"><span data-stu-id="54710-182">Type Conversion Functions</span></span>](../../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [<span data-ttu-id="54710-183">数据类型疑难解答</span><span class="sxs-lookup"><span data-stu-id="54710-183">Troubleshooting Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)
