---
title: "类型字符 (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- '&H prefix for hexadecimal values'
- hexadecimal literals [Visual Basic]
- F literal type character [Visual Basic]
- '& identifier type character'
- type characters [Visual Basic]
- octal literals [Visual Basic]
- literals [Visual Basic], hexadecimal
- '&O prefix for octal values'
- literals [Visual Basic], default types
- defaults, literal types
- C literal type character [Visual Basic]
- type characters [Visual Basic], literal
- $ identifier type character
- L literal type character [Visual Basic]
- UI literal type characters [Visual Basic]
- default literal types [Visual Basic]
- D literal type character [Visual Basic]
- literals [Visual Basic], octal
- S literal type character [Visual Basic]
- '! identifier type character'
- US literal type characters [Visual Basic]
- '% identifier type character'
- data types [Visual Basic], type characters
- characters [Visual Basic], identifier type
- type characters [Visual Basic], identifier
- '# identifier type character'
- identifier type characters [Visual Basic]
- literal type characters [Visual Basic]
- I literal type character [Visual Basic]
- R literal type character [Visual Basic]
- '@ identifier type character'
- UL literal type characters [Visual Basic]
- literal types [Visual Basic], default
ms.assetid: 6353cb9b-6ee4-4af6-a5a8-88ce39f90cc5
caps.latest.revision: "22"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 2bd017db40fc28c78e960a889947cc7323e3e156
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="type-characters-visual-basic"></a><span data-ttu-id="e686b-102">键入字符 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e686b-102">Type characters (Visual Basic)</span></span>

<span data-ttu-id="e686b-103">除了在声明语句中指定的数据类型，你可以强制使用某些编程元素的数据类型*键入字符*。</span><span class="sxs-lookup"><span data-stu-id="e686b-103">In addition to specifying a data type in a declaration statement, you can force the data type of some programming elements with a *type character*.</span></span> <span data-ttu-id="e686b-104">类型字符必须紧跟具有不允许插入字符的任何类型的元素。</span><span class="sxs-lookup"><span data-stu-id="e686b-104">The type character must immediately follow the element, with no intervening characters of any kind.</span></span>

<span data-ttu-id="e686b-105">类型字符不是名称的元素的一部分。</span><span class="sxs-lookup"><span data-stu-id="e686b-105">The type character is not part of the name of the element.</span></span> <span data-ttu-id="e686b-106">使用类型字符定义的元素可以引用不带类型字符。</span><span class="sxs-lookup"><span data-stu-id="e686b-106">An element defined with a type character can be referenced without the type character.</span></span>

## <a name="identifier-type-characters"></a><span data-ttu-id="e686b-107">标识符类型字符</span><span class="sxs-lookup"><span data-stu-id="e686b-107">Identifier type characters</span></span>

<span data-ttu-id="e686b-108">Visual Basic 提供的一组*标识符类型字符*，可用于在声明中指定的变量或常量的数据类型。</span><span class="sxs-lookup"><span data-stu-id="e686b-108">Visual Basic supplies a set of *identifier type characters* that you can use in a declaration to specify the data type of a variable or constant.</span></span> <span data-ttu-id="e686b-109">下表显示可用的标识符类型字符及其用法的示例。</span><span class="sxs-lookup"><span data-stu-id="e686b-109">The following table shows the available identifier type characters with examples of usage.</span></span>
  
|<span data-ttu-id="e686b-110">标识符类型字符</span><span class="sxs-lookup"><span data-stu-id="e686b-110">Identifier type character</span></span>|<span data-ttu-id="e686b-111">数据类型</span><span class="sxs-lookup"><span data-stu-id="e686b-111">Data type</span></span>|<span data-ttu-id="e686b-112">示例</span><span class="sxs-lookup"><span data-stu-id="e686b-112">Example</span></span>|  
|-------------------------------|---------------|-------------|  
|`%`|`Integer`|`Dim L%`|  
|`&`|`Long`|`Dim M&`|  
|`@`|`Decimal`|`Const W@ = 37.5`|  
|`!`|`Single`|`Dim Q!`|  
|`#`|`Double`|`Dim X#`|  
|`$`|`String`|`Dim V$ = "Secret"`|  
  
 <span data-ttu-id="e686b-113">任何标识符类型字符存在`Boolean`， `Byte`， `Char`， `Date`， `Object`， `SByte`， `Short`， `UInteger`， `ULong`，或`UShort`数据类型或任何复合数据类型，如数组或结构。</span><span class="sxs-lookup"><span data-stu-id="e686b-113">No identifier type characters exist for the `Boolean`, `Byte`, `Char`, `Date`, `Object`, `SByte`, `Short`, `UInteger`, `ULong`, or `UShort` data types, or for any composite data types such as arrays or structures.</span></span>

<span data-ttu-id="e686b-114">在某些情况下，你可以将附加`$`字符到 Visual Basic 函数，例如`Left$`而不是`Left`，以获取类型的返回的值`String`。</span><span class="sxs-lookup"><span data-stu-id="e686b-114">In some cases, you can append the `$` character to a Visual Basic function, for example `Left$` instead of `Left`, to obtain a returned value of type `String`.</span></span>

<span data-ttu-id="e686b-115">在所有情况下，标识符类型字符必须紧跟标识符名称。</span><span class="sxs-lookup"><span data-stu-id="e686b-115">In all cases, the identifier type character must immediately follow the identifier name.</span></span>

## <a name="literal-type-characters"></a><span data-ttu-id="e686b-116">文本类型字符</span><span class="sxs-lookup"><span data-stu-id="e686b-116">Literal type characters</span></span>

<span data-ttu-id="e686b-117">A*文本*是数据类型的特定值的文本表示。</span><span class="sxs-lookup"><span data-stu-id="e686b-117">A *literal* is a textual representation of a particular value of a data type.</span></span>  

### <a name="default-literal-types"></a><span data-ttu-id="e686b-118">默认文本类型</span><span class="sxs-lookup"><span data-stu-id="e686b-118">Default literal types</span></span>

<span data-ttu-id="e686b-119">文本的形式通常出现在你的代码中确定其数据类型。</span><span class="sxs-lookup"><span data-stu-id="e686b-119">The form of a literal as it appears in your code ordinarily determines its data type.</span></span> <span data-ttu-id="e686b-120">下表显示这些默认类型。</span><span class="sxs-lookup"><span data-stu-id="e686b-120">The following table shows these default types.</span></span>  
  
|<span data-ttu-id="e686b-121">文本形式的文本</span><span class="sxs-lookup"><span data-stu-id="e686b-121">Textual form of literal</span></span>|<span data-ttu-id="e686b-122">默认数据类型</span><span class="sxs-lookup"><span data-stu-id="e686b-122">Default data type</span></span>|<span data-ttu-id="e686b-123">示例</span><span class="sxs-lookup"><span data-stu-id="e686b-123">Example</span></span>|  
|-----------------------------|-----------------------|-------------|  
|<span data-ttu-id="e686b-124">数值，没有小数部分</span><span class="sxs-lookup"><span data-stu-id="e686b-124">Numeric, no fractional part</span></span>|`Integer`|`2147483647`|  
|<span data-ttu-id="e686b-125">数值，没有小数部分，对于来说太大`Integer`</span><span class="sxs-lookup"><span data-stu-id="e686b-125">Numeric, no fractional part, too large for `Integer`</span></span>|`Long`|`2147483648`|  
|<span data-ttu-id="e686b-126">数值，小数部分</span><span class="sxs-lookup"><span data-stu-id="e686b-126">Numeric, fractional part</span></span>|`Double`|`1.2`|  
|<span data-ttu-id="e686b-127">用双引号括起来</span><span class="sxs-lookup"><span data-stu-id="e686b-127">Enclosed in double quotation marks</span></span>|`String`|`"A"`|  
|<span data-ttu-id="e686b-128">包含在数字符号</span><span class="sxs-lookup"><span data-stu-id="e686b-128">Enclosed within number signs</span></span>|`Date`|`#5/17/1993 9:32 AM#`|  

### <a name="forced-literal-types"></a><span data-ttu-id="e686b-129">强制文本类型</span><span class="sxs-lookup"><span data-stu-id="e686b-129">Forced literal types</span></span>

<span data-ttu-id="e686b-130">Visual Basic 提供的一组*文本类型字符*，你可以使用强制文本采用其窗体的数据类型不是一个指示。</span><span class="sxs-lookup"><span data-stu-id="e686b-130">Visual Basic supplies a set of *literal type characters*, which you can use to force a literal to assume a data type other than the one its form indicates.</span></span> <span data-ttu-id="e686b-131">通过将字符追加到文本末尾来执行此操作。</span><span class="sxs-lookup"><span data-stu-id="e686b-131">You do this by appending the character to the end of the literal.</span></span> <span data-ttu-id="e686b-132">下表显示可用的文本类型字符及其用法的示例。</span><span class="sxs-lookup"><span data-stu-id="e686b-132">The following table shows the available literal type characters with examples of usage.</span></span>
  
|<span data-ttu-id="e686b-133">文本类型字符</span><span class="sxs-lookup"><span data-stu-id="e686b-133">Literal type character</span></span>|<span data-ttu-id="e686b-134">数据类型</span><span class="sxs-lookup"><span data-stu-id="e686b-134">Data type</span></span>|<span data-ttu-id="e686b-135">示例</span><span class="sxs-lookup"><span data-stu-id="e686b-135">Example</span></span>|  
|----------------------------|---------------|-------------|  
|`S`|`Short`|`I = 347S`|
|`I`|`Integer`|`J = 347I`|
|`L`|`Long`|`K = 347L`|
|`D`|`Decimal`|`X = 347D`|
|`F`|`Single`|`Y = 347F`|
|`R`|`Double`|`Z = 347R`|
|`US`|`UShort`|`L = 347US`|
|`UI`|`UInteger`|`M = 347UI`|
|`UL`|`ULong`|`N = 347UL`|
|`C`|`Char`|`Q = "."C`|

<span data-ttu-id="e686b-136">没有文本类型字符存在`Boolean`， `Byte`， `Date`， `Object`， `SByte`，或`String`数据类型或任何复合数据类型，如数组或结构。</span><span class="sxs-lookup"><span data-stu-id="e686b-136">No literal type characters exist for the `Boolean`, `Byte`, `Date`, `Object`, `SByte`, or `String` data types, or for any composite data types such as arrays or structures.</span></span>

<span data-ttu-id="e686b-137">文本也可以使用标识符类型字符 (`%`， `&`， `@`， `!`， `#`， `$`)，如可以变量、 常量和表达式。</span><span class="sxs-lookup"><span data-stu-id="e686b-137">Literals can also use the identifier type characters (`%`, `&`, `@`, `!`, `#`, `$`), as can variables, constants, and expressions.</span></span> <span data-ttu-id="e686b-138">但是，文本类型字符 (`S`， `I`， `L`， `D`， `F`， `R`， `C`) 可以仅用于文本。</span><span class="sxs-lookup"><span data-stu-id="e686b-138">However, the literal type characters (`S`, `I`, `L`, `D`, `F`, `R`, `C`) can be used only with literals.</span></span>

<span data-ttu-id="e686b-139">在所有情况下，文本类型字符必须紧跟文字值。</span><span class="sxs-lookup"><span data-stu-id="e686b-139">In all cases, the literal type character must immediately follow the literal value.</span></span>

## <a name="hexadecimal-binary-and-octal-literals"></a><span data-ttu-id="e686b-140">十六进制、 二进制和八进制文本</span><span class="sxs-lookup"><span data-stu-id="e686b-140">Hexadecimal, binary, and octal literals</span></span>

<span data-ttu-id="e686b-141">编译器通常会解释整数文本处于十进制 (基数为 10) 数字系统。</span><span class="sxs-lookup"><span data-stu-id="e686b-141">The compiler normally interprets an integer literal to be in the decimal (base 10) number system.</span></span> <span data-ttu-id="e686b-142">你还可以定义一个整数为十六进制 (基数为 16) 数字，`&H`前缀，为带二进制 (基数为 2) 数字`&B`前缀，八进制 (基数为 8)，以及带有`&O`前缀。</span><span class="sxs-lookup"><span data-stu-id="e686b-142">You can also define an integer literal as a hexadecimal (base 16) number with the `&H` prefix, as a binary (base 2) number with the `&B` prefix, and as an octal (base 8) number with the `&O` prefix.</span></span> <span data-ttu-id="e686b-143">跟在前缀的数字必须适合于数字系统。</span><span class="sxs-lookup"><span data-stu-id="e686b-143">The digits that follow the prefix must be appropriate for the number system.</span></span> <span data-ttu-id="e686b-144">下表阐释了这一点。</span><span class="sxs-lookup"><span data-stu-id="e686b-144">The following table illustrates this.</span></span>  
  
|<span data-ttu-id="e686b-145">数基</span><span class="sxs-lookup"><span data-stu-id="e686b-145">Number base</span></span>|<span data-ttu-id="e686b-146">前缀</span><span class="sxs-lookup"><span data-stu-id="e686b-146">Prefix</span></span>|<span data-ttu-id="e686b-147">有效的数字值</span><span class="sxs-lookup"><span data-stu-id="e686b-147">Valid digit values</span></span>|<span data-ttu-id="e686b-148">示例</span><span class="sxs-lookup"><span data-stu-id="e686b-148">Example</span></span>|
|-----------------|------------|------------------------|-------------|
|<span data-ttu-id="e686b-149">十六进制（以 16 为基数）</span><span class="sxs-lookup"><span data-stu-id="e686b-149">Hexadecimal (base 16)</span></span>|`&H`|<span data-ttu-id="e686b-150">0-9 和 A F</span><span class="sxs-lookup"><span data-stu-id="e686b-150">0-9 and A-F</span></span>|`&HFFFF`|
|<span data-ttu-id="e686b-151">二进制 (基数为 2)</span><span class="sxs-lookup"><span data-stu-id="e686b-151">Binary (base 2)</span></span>|`0B`|<span data-ttu-id="e686b-152">0-1</span><span class="sxs-lookup"><span data-stu-id="e686b-152">0-1</span></span>|`&B01111100`|
|<span data-ttu-id="e686b-153">八进制（以 8 为基数）</span><span class="sxs-lookup"><span data-stu-id="e686b-153">Octal (base 8)</span></span>|`&O`|<span data-ttu-id="e686b-154">0-7</span><span class="sxs-lookup"><span data-stu-id="e686b-154">0-7</span></span>|`&O77`|

<span data-ttu-id="e686b-155">从 Visual Basic 自 2017 年开始，你可以使用下划线字符 (`_`) 作为组分隔符以增强整型文本的可读性。</span><span class="sxs-lookup"><span data-stu-id="e686b-155">Starting in Visual Basic 2017, you can use the underscore character (`_`) as a group separator to enhance the readability of an integral literal.</span></span> <span data-ttu-id="e686b-156">下面的示例使用`_`字符，以便将分组到 8 位组的二进制文本：</span><span class="sxs-lookup"><span data-stu-id="e686b-156">The following example uses the `_` character to group a binary literal into 8-bit groups:</span></span>

```vb
Dim number As Integer = &B00100010_11000101_11001111_11001101
```

<span data-ttu-id="e686b-157">你可以按照在前缀的文本与文本类型字符。</span><span class="sxs-lookup"><span data-stu-id="e686b-157">You can follow a prefixed literal with a literal type character.</span></span> <span data-ttu-id="e686b-158">下面的示例演示了此过程。</span><span class="sxs-lookup"><span data-stu-id="e686b-158">The following example shows this.</span></span>

```vb
Dim counter As Short = &H8000S
Dim flags As UShort = &H8000US
```

<span data-ttu-id="e686b-159">在前面的示例中， `counter` -32768，十进制值和`flags`32768 的十进制值。</span><span class="sxs-lookup"><span data-stu-id="e686b-159">In the previous example, `counter` has the decimal value of -32768, and `flags` has the decimal value of +32768.</span></span>

## <a name="see-also"></a><span data-ttu-id="e686b-160">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e686b-160">See Also</span></span>

 [<span data-ttu-id="e686b-161">数据类型</span><span class="sxs-lookup"><span data-stu-id="e686b-161">Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/index.md)  
 [<span data-ttu-id="e686b-162">基本数据类型</span><span class="sxs-lookup"><span data-stu-id="e686b-162">Elementary Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/elementary-data-types.md)  
 [<span data-ttu-id="e686b-163">值类型和引用类型</span><span class="sxs-lookup"><span data-stu-id="e686b-163">Value Types and Reference Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)  
 [<span data-ttu-id="e686b-164">在 Visual Basic 中的类型转换</span><span class="sxs-lookup"><span data-stu-id="e686b-164">Type Conversions in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)  
 [<span data-ttu-id="e686b-165">数据类型疑难解答</span><span class="sxs-lookup"><span data-stu-id="e686b-165">Troubleshooting Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)  
 [<span data-ttu-id="e686b-166">变量声明</span><span class="sxs-lookup"><span data-stu-id="e686b-166">Variable Declaration</span></span>](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)  
 [<span data-ttu-id="e686b-167">数据类型</span><span class="sxs-lookup"><span data-stu-id="e686b-167">Data Types</span></span>](../../../../visual-basic/language-reference/data-types/data-type-summary.md)
