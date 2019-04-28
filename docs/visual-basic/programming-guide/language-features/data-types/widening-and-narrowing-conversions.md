---
title: 扩大转换和收缩转换 (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- widening conversions [Visual Basic]
- narrowing conversions [Visual Basic]
- conversions [Visual Basic], type
- data types [Visual Basic], changing
- variables [Visual Basic], changing data type
- conversions [Visual Basic], exceptions during conversion
- type conversion [Visual Basic], exceptions during conversion
- conversions [Visual Basic], data type
- conversions [Visual Basic], narrowing
- type conversion [Visual Basic], narrowing
- data type conversion [Visual Basic], widening
- data type conversion [Visual Basic], narrowing
- changing data types [Visual Basic]
- type conversion [Visual Basic], widening
- data type conversion [Visual Basic], exceptions during conversion
- conversions [Visual Basic], widening
ms.assetid: 058c3152-6c28-4268-af44-2209e774f0bd
ms.openlocfilehash: 9f1a71e8e2e3e4ebb9b412be74b5ea8702eb164f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61827151"
---
# <a name="widening-and-narrowing-conversions-visual-basic"></a><span data-ttu-id="10795-102">扩大转换和收缩转换 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="10795-102">Widening and Narrowing Conversions (Visual Basic)</span></span>
<span data-ttu-id="10795-103">类型转换的一个重要考虑因素是转换的结果是否在目标数据类型的范围内。</span><span class="sxs-lookup"><span data-stu-id="10795-103">An important consideration with a type conversion is whether the result of the conversion is within the range of the destination data type.</span></span>  
  
 <span data-ttu-id="10795-104">一个*扩大转换*值更改为可实现任何可能值的原始数据的数据类型。</span><span class="sxs-lookup"><span data-stu-id="10795-104">A *widening conversion* changes a value to a data type that can allow for any possible value of the original data.</span></span>  <span data-ttu-id="10795-105">扩大转换保留源值，但可以更改它的表示形式。</span><span class="sxs-lookup"><span data-stu-id="10795-105">Widening conversions preserve the source value but can change its representation.</span></span> <span data-ttu-id="10795-106">发生这种情况是如果将从整型类型转换`Decimal`，或从`Char`到`String`。</span><span class="sxs-lookup"><span data-stu-id="10795-106">This occurs if you convert from an integral type to `Decimal`, or from `Char` to `String`.</span></span>  
  
 <span data-ttu-id="10795-107">*“收缩转换”* 将值更改为可能无法保存某些可能值的数据类型。</span><span class="sxs-lookup"><span data-stu-id="10795-107">A *narrowing conversion* changes a value to a data type that might not be able to hold some of the possible values.</span></span> <span data-ttu-id="10795-108">小数部分值转换为整型类型，并转换为数值类型时，舍入`Boolean`减少至任一`True`或`False`。</span><span class="sxs-lookup"><span data-stu-id="10795-108">For example, a fractional value is rounded when it is converted to an integral type, and a numeric type being converted to `Boolean` is reduced to either `True` or `False`.</span></span>  
  
## <a name="widening-conversions"></a><span data-ttu-id="10795-109">扩大转换</span><span class="sxs-lookup"><span data-stu-id="10795-109">Widening Conversions</span></span>  
 <span data-ttu-id="10795-110">下表显示了标准的扩大转换。</span><span class="sxs-lookup"><span data-stu-id="10795-110">The following table shows the standard widening conversions.</span></span>  
  
|<span data-ttu-id="10795-111">数据类型</span><span class="sxs-lookup"><span data-stu-id="10795-111">Data type</span></span>|<span data-ttu-id="10795-112">扩大的数据类型为<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="10795-112">Widens to data types <sup>1</sup></span></span>|  
|---|---|  
|[<span data-ttu-id="10795-113">SByte</span><span class="sxs-lookup"><span data-stu-id="10795-113">SByte</span></span>](../../../../visual-basic/language-reference/data-types/sbyte-data-type.md)|<span data-ttu-id="10795-114">`SByte`, `Short`, `Integer`, `Long`, `Decimal`, `Single`, `Double`</span><span class="sxs-lookup"><span data-stu-id="10795-114">`SByte`, `Short`, `Integer`, `Long`, `Decimal`, `Single`, `Double`</span></span>|  
|[<span data-ttu-id="10795-115">Byte</span><span class="sxs-lookup"><span data-stu-id="10795-115">Byte</span></span>](../../../../visual-basic/language-reference/data-types/byte-data-type.md)|<span data-ttu-id="10795-116">`Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long`, `ULong`, `Decimal`, `Single`, `Double`</span><span class="sxs-lookup"><span data-stu-id="10795-116">`Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long`, `ULong`, `Decimal`, `Single`, `Double`</span></span>|  
|[<span data-ttu-id="10795-117">Short</span><span class="sxs-lookup"><span data-stu-id="10795-117">Short</span></span>](../../../../visual-basic/language-reference/data-types/short-data-type.md)|<span data-ttu-id="10795-118">`Short`, `Integer`, `Long`, `Decimal`, `Single`, `Double`</span><span class="sxs-lookup"><span data-stu-id="10795-118">`Short`, `Integer`, `Long`, `Decimal`, `Single`, `Double`</span></span>|  
|[<span data-ttu-id="10795-119">UShort</span><span class="sxs-lookup"><span data-stu-id="10795-119">UShort</span></span>](../../../../visual-basic/language-reference/data-types/ushort-data-type.md)|<span data-ttu-id="10795-120">`UShort`, `Integer`, `UInteger`, `Long`, `ULong`, `Decimal`, `Single`, `Double`</span><span class="sxs-lookup"><span data-stu-id="10795-120">`UShort`, `Integer`, `UInteger`, `Long`, `ULong`, `Decimal`, `Single`, `Double`</span></span>|  
|[<span data-ttu-id="10795-121">Integer</span><span class="sxs-lookup"><span data-stu-id="10795-121">Integer</span></span>](../../../../visual-basic/language-reference/data-types/integer-data-type.md)|<span data-ttu-id="10795-122">`Integer`, `Long`, `Decimal`, `Single`, `Double`<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="10795-122">`Integer`, `Long`, `Decimal`, `Single`, `Double`<sup>2</sup></span></span>|  
|[<span data-ttu-id="10795-123">UInteger</span><span class="sxs-lookup"><span data-stu-id="10795-123">UInteger</span></span>](../../../../visual-basic/language-reference/data-types/uinteger-data-type.md)|<span data-ttu-id="10795-124">`UInteger`, `Long`, `ULong`, `Decimal`, `Single`, `Double`<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="10795-124">`UInteger`, `Long`, `ULong`, `Decimal`, `Single`, `Double`<sup>2</sup></span></span>|  
|[<span data-ttu-id="10795-125">Long</span><span class="sxs-lookup"><span data-stu-id="10795-125">Long</span></span>](../../../../visual-basic/language-reference/data-types/long-data-type.md)|<span data-ttu-id="10795-126">`Long`, `Decimal`, `Single`, `Double`<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="10795-126">`Long`, `Decimal`, `Single`, `Double`<sup>2</sup></span></span>|  
|[<span data-ttu-id="10795-127">ULong</span><span class="sxs-lookup"><span data-stu-id="10795-127">ULong</span></span>](../../../../visual-basic/language-reference/data-types/ulong-data-type.md)|<span data-ttu-id="10795-128">`ULong`, `Decimal`, `Single`, `Double`<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="10795-128">`ULong`, `Decimal`, `Single`, `Double`<sup>2</sup></span></span>|  
|[<span data-ttu-id="10795-129">小数</span><span class="sxs-lookup"><span data-stu-id="10795-129">Decimal</span></span>](../../../../visual-basic/language-reference/data-types/decimal-data-type.md)|<span data-ttu-id="10795-130">`Decimal`, `Single`, `Double`<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="10795-130">`Decimal`, `Single`, `Double`<sup>2</sup></span></span>|  
|[<span data-ttu-id="10795-131">Single</span><span class="sxs-lookup"><span data-stu-id="10795-131">Single</span></span>](../../../../visual-basic/language-reference/data-types/single-data-type.md)|<span data-ttu-id="10795-132">`Single`， `Double`</span><span class="sxs-lookup"><span data-stu-id="10795-132">`Single`, `Double`</span></span>|  
|[<span data-ttu-id="10795-133">Double</span><span class="sxs-lookup"><span data-stu-id="10795-133">Double</span></span>](../../../../visual-basic/language-reference/data-types/double-data-type.md)|`Double`|  
|<span data-ttu-id="10795-134">任何枚举类型 ([枚举](../../../../visual-basic/language-reference/statements/enum-statement.md))</span><span class="sxs-lookup"><span data-stu-id="10795-134">Any enumerated type ([Enum](../../../../visual-basic/language-reference/statements/enum-statement.md))</span></span>|<span data-ttu-id="10795-135">其基础整型类型和任何类型的基础类型扩大。</span><span class="sxs-lookup"><span data-stu-id="10795-135">Its underlying integral type and any type to which the underlying type widens.</span></span>|  
|[<span data-ttu-id="10795-136">Char</span><span class="sxs-lookup"><span data-stu-id="10795-136">Char</span></span>](../../../../visual-basic/language-reference/data-types/char-data-type.md)|<span data-ttu-id="10795-137">`Char`， `String`</span><span class="sxs-lookup"><span data-stu-id="10795-137">`Char`, `String`</span></span>|  
|<span data-ttu-id="10795-138">`Char` 数组</span><span class="sxs-lookup"><span data-stu-id="10795-138">`Char` array</span></span>|<span data-ttu-id="10795-139">`Char` 数组， `String`</span><span class="sxs-lookup"><span data-stu-id="10795-139">`Char` array, `String`</span></span>|  
|<span data-ttu-id="10795-140">任何类型</span><span class="sxs-lookup"><span data-stu-id="10795-140">Any type</span></span>|[<span data-ttu-id="10795-141">Object</span><span class="sxs-lookup"><span data-stu-id="10795-141">Object</span></span>](../../../../visual-basic/language-reference/data-types/object-data-type.md)|  
|<span data-ttu-id="10795-142">任何派生的类型</span><span class="sxs-lookup"><span data-stu-id="10795-142">Any derived type</span></span>|<span data-ttu-id="10795-143">任何基的类型派生自<sup>3</sup>。</span><span class="sxs-lookup"><span data-stu-id="10795-143">Any base type from which it is derived <sup>3</sup>.</span></span>|  
|<span data-ttu-id="10795-144">任何类型</span><span class="sxs-lookup"><span data-stu-id="10795-144">Any type</span></span>|<span data-ttu-id="10795-145">它实现任何接口。</span><span class="sxs-lookup"><span data-stu-id="10795-145">Any interface it implements.</span></span>|  
|[<span data-ttu-id="10795-146">Nothing</span><span class="sxs-lookup"><span data-stu-id="10795-146">Nothing</span></span>](../../../../visual-basic/language-reference/nothing.md)|<span data-ttu-id="10795-147">任何数据类型或对象类型。</span><span class="sxs-lookup"><span data-stu-id="10795-147">Any data type or object type.</span></span>|  
  
 <span data-ttu-id="10795-148"><sup>1</sup>根据定义，每个数据类型加宽到本身。</span><span class="sxs-lookup"><span data-stu-id="10795-148"><sup>1</sup> By definition, every data type widens to itself.</span></span>  
  
 <span data-ttu-id="10795-149"><sup>2</sup>从小`Integer`， `UInteger`， `Long`， `ULong`，或`Decimal`到`Single`或`Double`可能导致丢失精度，但永远不会导致丢失量值。</span><span class="sxs-lookup"><span data-stu-id="10795-149"><sup>2</sup> Conversions from `Integer`, `UInteger`, `Long`, `ULong`, or `Decimal` to `Single` or `Double` might result in loss of precision, but never in loss of magnitude.</span></span> <span data-ttu-id="10795-150">在这种情况下它们不会产生信息丢失。</span><span class="sxs-lookup"><span data-stu-id="10795-150">In this sense they do not incur information loss.</span></span>  
  
 <span data-ttu-id="10795-151"><sup>3</sup>它可能看起来令人惊讶的扩大转换从派生类型转换为其基类型之一。</span><span class="sxs-lookup"><span data-stu-id="10795-151"><sup>3</sup> It might seem surprising that a conversion from a derived type to one of its base types is widening.</span></span> <span data-ttu-id="10795-152">理由是派生的类型包含基类型的所有成员，因此它被称为基类型的实例。</span><span class="sxs-lookup"><span data-stu-id="10795-152">The justification is that the derived type contains all the members of the base type, so it qualifies as an instance of the base type.</span></span> <span data-ttu-id="10795-153">在相反方向的基类型不包含由派生的类型定义任何新成员。</span><span class="sxs-lookup"><span data-stu-id="10795-153">In the opposite direction, the base type does not contain any new members defined by the derived type.</span></span>  
  
 <span data-ttu-id="10795-154">扩大转换在运行时始终成功，并且永远不会导致数据丢失。</span><span class="sxs-lookup"><span data-stu-id="10795-154">Widening conversions always succeed at run time and never incur data loss.</span></span> <span data-ttu-id="10795-155">始终可以隐式执行它们，是否[Option Strict Statement](../../../../visual-basic/language-reference/statements/option-strict-statement.md)设置类型检查开关`On`或`Off`。</span><span class="sxs-lookup"><span data-stu-id="10795-155">You can always perform them implicitly, whether the [Option Strict Statement](../../../../visual-basic/language-reference/statements/option-strict-statement.md) sets the type checking switch to `On` or to `Off`.</span></span>  
  
## <a name="narrowing-conversions"></a><span data-ttu-id="10795-156">收缩转换</span><span class="sxs-lookup"><span data-stu-id="10795-156">Narrowing Conversions</span></span>  
 <span data-ttu-id="10795-157">标准的收缩转换如下所示：</span><span class="sxs-lookup"><span data-stu-id="10795-157">The standard narrowing conversions include the following:</span></span>  
  
- <span data-ttu-id="10795-158">在前面的扩大转换的相反方向表 （不过，每个类型扩大到自身）</span><span class="sxs-lookup"><span data-stu-id="10795-158">The reverse directions of the widening conversions in the preceding table (except that every type widens to itself)</span></span>  
  
- <span data-ttu-id="10795-159">在任一方向之间的转换[布尔](../../../../visual-basic/language-reference/data-types/boolean-data-type.md)和任何数值类型</span><span class="sxs-lookup"><span data-stu-id="10795-159">Conversions in either direction between [Boolean](../../../../visual-basic/language-reference/data-types/boolean-data-type.md) and any numeric type</span></span>  
  
- <span data-ttu-id="10795-160">从任何数值类型转换为任何枚举类型 (`Enum`)</span><span class="sxs-lookup"><span data-stu-id="10795-160">Conversions from any numeric type to any enumerated type (`Enum`)</span></span>  
  
- <span data-ttu-id="10795-161">在任一方向之间的转换[字符串](../../../../visual-basic/language-reference/data-types/string-data-type.md)和任何数值类型`Boolean`，或[日期](../../../../visual-basic/language-reference/data-types/date-data-type.md)</span><span class="sxs-lookup"><span data-stu-id="10795-161">Conversions in either direction between [String](../../../../visual-basic/language-reference/data-types/string-data-type.md) and any numeric type, `Boolean`, or [Date](../../../../visual-basic/language-reference/data-types/date-data-type.md)</span></span>  
  
- <span data-ttu-id="10795-162">从数据类型或对象类型转换为其派生的类型</span><span class="sxs-lookup"><span data-stu-id="10795-162">Conversions from a data type or object type to a type derived from it</span></span>  
  
 <span data-ttu-id="10795-163">收缩转换执行不总是在运行时，成功和可以故障或会导致数据丢失。</span><span class="sxs-lookup"><span data-stu-id="10795-163">Narrowing conversions do not always succeed at run time, and can fail or incur data loss.</span></span> <span data-ttu-id="10795-164">如果目标数据类型不能接收要转换的值，就会出错。</span><span class="sxs-lookup"><span data-stu-id="10795-164">An error occurs if the destination data type cannot receive the value being converted.</span></span> <span data-ttu-id="10795-165">例如，数值的转换导致溢出。</span><span class="sxs-lookup"><span data-stu-id="10795-165">For example, a numeric conversion can result in an overflow.</span></span> <span data-ttu-id="10795-166">编译器不允许您以隐式执行收缩转换，除非[Option Strict Statement](../../../../visual-basic/language-reference/statements/option-strict-statement.md)设置类型检查开关`Off`。</span><span class="sxs-lookup"><span data-stu-id="10795-166">The compiler does not allow you to perform narrowing conversions implicitly unless the [Option Strict Statement](../../../../visual-basic/language-reference/statements/option-strict-statement.md) sets the type checking switch to `Off`.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="10795-167">收缩转换错误则会取消对从中的元素的转换`For Each…Next`循环控制变量的集合。</span><span class="sxs-lookup"><span data-stu-id="10795-167">The narrowing-conversion error is suppressed for conversions from the elements in a `For Each…Next` collection to the loop control variable.</span></span> <span data-ttu-id="10795-168">有关详细信息和示例，请参阅中的"收缩转换"部分[为每个...下一条语句](../../../../visual-basic/language-reference/statements/for-each-next-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="10795-168">For more information and examples, see the "Narrowing Conversions" section in [For Each...Next Statement](../../../../visual-basic/language-reference/statements/for-each-next-statement.md).</span></span>  
  
### <a name="when-to-use-narrowing-conversions"></a><span data-ttu-id="10795-169">何时使用收缩转换</span><span class="sxs-lookup"><span data-stu-id="10795-169">When to Use Narrowing Conversions</span></span>  
 <span data-ttu-id="10795-170">当您知道源值可以转换为无错误或数据丢失的目标数据类型时使用收缩转换。</span><span class="sxs-lookup"><span data-stu-id="10795-170">You use a narrowing conversion when you know the source value can be converted to the destination data type without error or data loss.</span></span> <span data-ttu-id="10795-171">例如，如果你有`String`，您知道包含"True"False"，您可以使用`CBool`关键字将其转换为`Boolean`。</span><span class="sxs-lookup"><span data-stu-id="10795-171">For example, if you have a `String` that you know contains either "True" or "False," you can use the `CBool` keyword to convert it to `Boolean`.</span></span>  
  
## <a name="exceptions-during-conversion"></a><span data-ttu-id="10795-172">转换期间的异常</span><span class="sxs-lookup"><span data-stu-id="10795-172">Exceptions During Conversion</span></span>  
 <span data-ttu-id="10795-173">由于扩大转换始终成功，它们不会引发异常。</span><span class="sxs-lookup"><span data-stu-id="10795-173">Because widening conversions always succeed, they do not throw exceptions.</span></span> <span data-ttu-id="10795-174">收缩转换，在故障时最常引发以下异常：</span><span class="sxs-lookup"><span data-stu-id="10795-174">Narrowing conversions, when they fail, most commonly throw the following exceptions:</span></span>  
  
- <span data-ttu-id="10795-175"><xref:System.InvalidCastException> -如果两个类型之间不定义任何转换</span><span class="sxs-lookup"><span data-stu-id="10795-175"><xref:System.InvalidCastException> — if no conversion is defined between the two types</span></span>  
  
- <span data-ttu-id="10795-176"><xref:System.OverflowException> -（仅限整型） 如果转换后的值的目标类型太大</span><span class="sxs-lookup"><span data-stu-id="10795-176"><xref:System.OverflowException> — (integral types only) if the converted value is too large for the target type</span></span>  
  
 <span data-ttu-id="10795-177">如果类或结构定义了[CType Function](../../../../visual-basic/language-reference/functions/ctype-function.md)转换运算符到或从该类或结构，作为的`CType`可以引发任何它认为适当的任何异常。</span><span class="sxs-lookup"><span data-stu-id="10795-177">If a class or structure defines a [CType Function](../../../../visual-basic/language-reference/functions/ctype-function.md) to serve as a conversion operator to or from that class or structure, that `CType` can throw any exception it deems appropriate.</span></span> <span data-ttu-id="10795-178">此外，该`CType`可能会调用 Visual Basic 函数或[!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)]又可能会引发多种异常的方法。</span><span class="sxs-lookup"><span data-stu-id="10795-178">In addition, that `CType` might call Visual Basic functions or [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] methods, which in turn could throw a variety of exceptions.</span></span>  
  
## <a name="changes-during-reference-type-conversions"></a><span data-ttu-id="10795-179">引用类型转换过程中的更改</span><span class="sxs-lookup"><span data-stu-id="10795-179">Changes During Reference Type Conversions</span></span>  
 <span data-ttu-id="10795-180">从转换*引用类型*只复制的指针的值。</span><span class="sxs-lookup"><span data-stu-id="10795-180">A conversion from a *reference type* copies only the pointer to the value.</span></span> <span data-ttu-id="10795-181">值本身不复制也不以任何方式更改。</span><span class="sxs-lookup"><span data-stu-id="10795-181">The value itself is neither copied nor changed in any way.</span></span> <span data-ttu-id="10795-182">可以更改的唯一事情是变量的包含指针的数据类型。</span><span class="sxs-lookup"><span data-stu-id="10795-182">The only thing that can change is the data type of the variable holding the pointer.</span></span> <span data-ttu-id="10795-183">在以下示例中，数据类型从派生类转换为它的基类，但这两个变量现在指向的对象保持不变。</span><span class="sxs-lookup"><span data-stu-id="10795-183">In the following example, the data type is converted from the derived class to its base class, but the object that both variables now point to is unchanged.</span></span>  
  
```  
' Assume class cSquare inherits from class cShape.  
Dim shape As cShape  
Dim square As cSquare = New cSquare  
' The following statement performs a widening  
' conversion from a derived class to its base class.  
shape = square  
```  
  
## <a name="see-also"></a><span data-ttu-id="10795-184">请参阅</span><span class="sxs-lookup"><span data-stu-id="10795-184">See also</span></span>

- [<span data-ttu-id="10795-185">数据类型</span><span class="sxs-lookup"><span data-stu-id="10795-185">Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/index.md)
- [<span data-ttu-id="10795-186">在 Visual Basic 中的类型转换</span><span class="sxs-lookup"><span data-stu-id="10795-186">Type Conversions in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)
- [<span data-ttu-id="10795-187">隐式转换和显式转换</span><span class="sxs-lookup"><span data-stu-id="10795-187">Implicit and Explicit Conversions</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)
- [<span data-ttu-id="10795-188">字符串和其他类型之间的转换</span><span class="sxs-lookup"><span data-stu-id="10795-188">Conversions Between Strings and Other Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/conversions-between-strings-and-other-types.md)
- [<span data-ttu-id="10795-189">如何：将对象转换为 Visual Basic 中的另一种类型</span><span class="sxs-lookup"><span data-stu-id="10795-189">How to: Convert an Object to Another Type in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/how-to-convert-an-object-to-another-type.md)
- [<span data-ttu-id="10795-190">数组转换</span><span class="sxs-lookup"><span data-stu-id="10795-190">Array Conversions</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/array-conversions.md)
- [<span data-ttu-id="10795-191">数据类型</span><span class="sxs-lookup"><span data-stu-id="10795-191">Data Types</span></span>](../../../../visual-basic/language-reference/data-types/index.md)
- [<span data-ttu-id="10795-192">类型转换函数</span><span class="sxs-lookup"><span data-stu-id="10795-192">Type Conversion Functions</span></span>](../../../../visual-basic/language-reference/functions/type-conversion-functions.md)
