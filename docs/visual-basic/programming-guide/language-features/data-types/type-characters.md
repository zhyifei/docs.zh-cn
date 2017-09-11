---
title: "键入的字符 (Visual Basic 中) |Microsoft 文档"
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
- '&H prefix for hexadecimal values'
- hexadecimal literals
- F literal type character
- '& identifier type character'
- type characters
- octal literals
- literals, hexadecimal
- '&O prefix for octal values'
- literals, default types
- defaults, literal types
- C literal type character
- type characters, literal
- $ identifier type character
- L literal type character
- UI literal type characters
- default literal types
- D literal type character
- literals, octal
- S literal type character
- '! identifier type character'
- US literal type characters
- '% identifier type character'
- data types [Visual Basic], type characters
- characters, identifier type
- type characters, identifier
- '# identifier type character'
- identifier type characters
- literal type characters
- I literal type character
- R literal type character
- '@ identifier type character'
- UL literal type characters
- literal types, default
ms.assetid: 6353cb9b-6ee4-4af6-a5a8-88ce39f90cc5
caps.latest.revision: 22
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
ms.openlocfilehash: 335306eca12070de456a72e918bcbba1e22ab55b
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017

---
# <a name="type-characters-visual-basic"></a><span data-ttu-id="39e36-102">类型字符 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="39e36-102">Type Characters (Visual Basic)</span></span>
<span data-ttu-id="39e36-103">除了声明语句中指定的数据类型，您可以强制使用某些编程元素的数据类型*键入字符*。</span><span class="sxs-lookup"><span data-stu-id="39e36-103">In addition to specifying a data type in a declaration statement, you can force the data type of some programming elements with a *type character*.</span></span> <span data-ttu-id="39e36-104">类型字符必须紧跟具有任何类型不允许插入字符的元素。</span><span class="sxs-lookup"><span data-stu-id="39e36-104">The type character must immediately follow the element, with no intervening characters of any kind.</span></span>  
  
 <span data-ttu-id="39e36-105">类型字符不是名称的元素的一部分。</span><span class="sxs-lookup"><span data-stu-id="39e36-105">The type character is not part of the name of the element.</span></span> <span data-ttu-id="39e36-106">类型字符定义的元素可以引用不带类型字符。</span><span class="sxs-lookup"><span data-stu-id="39e36-106">An element defined with a type character can be referenced without the type character.</span></span>  
  
## <a name="identifier-type-characters"></a><span data-ttu-id="39e36-107">标识符类型字符</span><span class="sxs-lookup"><span data-stu-id="39e36-107">Identifier Type Characters</span></span>  
 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]<span data-ttu-id="39e36-108">提供一组*标识符类型字符串*，您可以用于在声明中指定的变量或常量的数据类型。</span><span class="sxs-lookup"><span data-stu-id="39e36-108"> supplies a set of *identifier type characters*, which you can use in a declaration to specify the data type of a variable or constant.</span></span> <span data-ttu-id="39e36-109">下表显示可用的标识符类型字符及其用法的示例。</span><span class="sxs-lookup"><span data-stu-id="39e36-109">The following table shows the available identifier type characters with examples of usage.</span></span>  
  
|<span data-ttu-id="39e36-110">标识符类型字符</span><span class="sxs-lookup"><span data-stu-id="39e36-110">Identifier type character</span></span>|<span data-ttu-id="39e36-111">数据类型</span><span class="sxs-lookup"><span data-stu-id="39e36-111">Data type</span></span>|<span data-ttu-id="39e36-112">示例</span><span class="sxs-lookup"><span data-stu-id="39e36-112">Example</span></span>|  
|-------------------------------|---------------|-------------|  
|`%`|`Integer`|`Dim L%`|  
|`&`|`Long`|`Dim M&`|  
|`@`|`Decimal`|`Const W@ = 37.5`|  
|`!`|`Single`|`Dim Q!`|  
|`#`|`Double`|`Dim X#`|  
|`$`|`String`|`Dim V$ = "Secret"`|  
  
 <span data-ttu-id="39e36-113">对于没有标识符类型字符串存在`Boolean`， `Byte`， `Char`， `Date`， `Object`， `SByte`， `Short`， `UInteger`， `ULong`，或`UShort`数据类型或任何复合数据类型，如数组或结构。</span><span class="sxs-lookup"><span data-stu-id="39e36-113">No identifier type characters exist for the `Boolean`, `Byte`, `Char`, `Date`, `Object`, `SByte`, `Short`, `UInteger`, `ULong`, or `UShort` data types, or for any composite data types such as arrays or structures.</span></span>  
  
 <span data-ttu-id="39e36-114">在某些情况下，您可以将附加`$`字符到[!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]正常工作，例如`Left$`而不是`Left`，以获取返回的值类型为`String`。</span><span class="sxs-lookup"><span data-stu-id="39e36-114">In some cases, you can append the `$` character to a [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] function, for example `Left$` instead of `Left`, to obtain a returned value of type `String`.</span></span>  
  
 <span data-ttu-id="39e36-115">在所有情况下，标识符类型字符必须紧跟在标识符名称。</span><span class="sxs-lookup"><span data-stu-id="39e36-115">In all cases, the identifier type character must immediately follow the identifier name.</span></span>  
  
## <a name="literal-type-characters"></a><span data-ttu-id="39e36-116">文本类型字符</span><span class="sxs-lookup"><span data-stu-id="39e36-116">Literal Type Characters</span></span>  
 <span data-ttu-id="39e36-117">一个*文字*是一种数据类型具有特定值的文本表示形式。</span><span class="sxs-lookup"><span data-stu-id="39e36-117">A *literal* is a textual representation of a particular value of a data type.</span></span>  
  
### <a name="default-literal-types"></a><span data-ttu-id="39e36-118">默认文本类型</span><span class="sxs-lookup"><span data-stu-id="39e36-118">Default Literal Types</span></span>  
 <span data-ttu-id="39e36-119">文本的形式通常出现在您的代码中确定其数据类型。</span><span class="sxs-lookup"><span data-stu-id="39e36-119">The form of a literal as it appears in your code ordinarily determines its data type.</span></span> <span data-ttu-id="39e36-120">下表显示这些默认类型。</span><span class="sxs-lookup"><span data-stu-id="39e36-120">The following table shows these default types.</span></span>  
  
|<span data-ttu-id="39e36-121">文本形式</span><span class="sxs-lookup"><span data-stu-id="39e36-121">Textual form of literal</span></span>|<span data-ttu-id="39e36-122">默认数据类型</span><span class="sxs-lookup"><span data-stu-id="39e36-122">Default data type</span></span>|<span data-ttu-id="39e36-123">示例</span><span class="sxs-lookup"><span data-stu-id="39e36-123">Example</span></span>|  
|-----------------------------|-----------------------|-------------|  
|<span data-ttu-id="39e36-124">数值，没有小数部分</span><span class="sxs-lookup"><span data-stu-id="39e36-124">Numeric, no fractional part</span></span>|`Integer`|`2147483647`|  
|<span data-ttu-id="39e36-125">数值，没有小数部分，对于来说太大`Integer`</span><span class="sxs-lookup"><span data-stu-id="39e36-125">Numeric, no fractional part, too large for `Integer`</span></span>|`Long`|`2147483648`|  
|<span data-ttu-id="39e36-126">数值，小数部分</span><span class="sxs-lookup"><span data-stu-id="39e36-126">Numeric, fractional part</span></span>|`Double`|`1.2`|  
|<span data-ttu-id="39e36-127">括在双引号内</span><span class="sxs-lookup"><span data-stu-id="39e36-127">Enclosed in double quotation marks</span></span>|`String`|`"A"`|  
|<span data-ttu-id="39e36-128">包含在数字符号</span><span class="sxs-lookup"><span data-stu-id="39e36-128">Enclosed within number signs</span></span>|`Date`|`#5/17/1993 9:32 AM#`|  
  
### <a name="forced-literal-types"></a><span data-ttu-id="39e36-129">强制文本类型</span><span class="sxs-lookup"><span data-stu-id="39e36-129">Forced Literal Types</span></span>  
 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]<span data-ttu-id="39e36-130">提供一组*文本类型字符*，这可用于强制文本采用一个数据类型不是它的形式表示。</span><span class="sxs-lookup"><span data-stu-id="39e36-130"> supplies a set of *literal type characters*, which you can use to force a literal to assume a data type other than the one its form indicates.</span></span> <span data-ttu-id="39e36-131">通过将字符追加到文本末尾执行此操作。</span><span class="sxs-lookup"><span data-stu-id="39e36-131">You do this by appending the character to the end of the literal.</span></span> <span data-ttu-id="39e36-132">下表显示可用的文本类型字符及其用法的示例。</span><span class="sxs-lookup"><span data-stu-id="39e36-132">The following table shows the available literal type characters with examples of usage.</span></span>  
  
|<span data-ttu-id="39e36-133">文本类型字符</span><span class="sxs-lookup"><span data-stu-id="39e36-133">Literal type character</span></span>|<span data-ttu-id="39e36-134">数据类型</span><span class="sxs-lookup"><span data-stu-id="39e36-134">Data type</span></span>|<span data-ttu-id="39e36-135">示例</span><span class="sxs-lookup"><span data-stu-id="39e36-135">Example</span></span>|  
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
  
 <span data-ttu-id="39e36-136">对于存在没有文本类型字符`Boolean`， `Byte`， `Date`， `Object`， `SByte`，或`String`数据类型或任何复合数据类型，如数组或结构。</span><span class="sxs-lookup"><span data-stu-id="39e36-136">No literal type characters exist for the `Boolean`, `Byte`, `Date`, `Object`, `SByte`, or `String` data types, or for any composite data types such as arrays or structures.</span></span>  
  
 <span data-ttu-id="39e36-137">文本也可以使用标识符类型字符 (`%`， `&`， `@`， `!`， `#`， `$`)，如可能是变量、 常量和表达式。</span><span class="sxs-lookup"><span data-stu-id="39e36-137">Literals can also use the identifier type characters (`%`, `&`, `@`, `!`, `#`, `$`), as can variables, constants, and expressions.</span></span> <span data-ttu-id="39e36-138">但是，文本类型字符 (`S`， `I`， `L`， `D`， `F`， `R`， `C`) 可仅与原义字符。</span><span class="sxs-lookup"><span data-stu-id="39e36-138">However, the literal type characters (`S`, `I`, `L`, `D`, `F`, `R`, `C`) can be used only with literals.</span></span>  
  
 <span data-ttu-id="39e36-139">在所有情况下，文本类型字符必须紧跟的文字值。</span><span class="sxs-lookup"><span data-stu-id="39e36-139">In all cases, the literal type character must immediately follow the literal value.</span></span>  
  
## <a name="hexadecimal-and-octal-literals"></a><span data-ttu-id="39e36-140">十六进制和八进制文本</span><span class="sxs-lookup"><span data-stu-id="39e36-140">Hexadecimal and Octal Literals</span></span>  
 <span data-ttu-id="39e36-141">通常，编译器将解释整数文字采用十进制 (基数为 10) 数字系统。</span><span class="sxs-lookup"><span data-stu-id="39e36-141">The compiler normally construes an integer literal to be in the decimal (base 10) number system.</span></span> <span data-ttu-id="39e36-142">您可以强制一个整数为十六进制 (基数为 16) 与`&H`前缀，并且您可以强制为八进制 (基数为 8) 与`&O`前缀。</span><span class="sxs-lookup"><span data-stu-id="39e36-142">You can force an integer literal to be hexadecimal (base 16) with the `&H` prefix, and you can force it to be octal (base 8) with the `&O` prefix.</span></span> <span data-ttu-id="39e36-143">跟在前缀的数字必须适合于数字系统。</span><span class="sxs-lookup"><span data-stu-id="39e36-143">The digits that follow the prefix must be appropriate for the number system.</span></span> <span data-ttu-id="39e36-144">下表阐释了这一点。</span><span class="sxs-lookup"><span data-stu-id="39e36-144">The following table illustrates this.</span></span>  
  
|<span data-ttu-id="39e36-145">号码基</span><span class="sxs-lookup"><span data-stu-id="39e36-145">Number base</span></span>|<span data-ttu-id="39e36-146">前缀</span><span class="sxs-lookup"><span data-stu-id="39e36-146">Prefix</span></span>|<span data-ttu-id="39e36-147">有效的数字值</span><span class="sxs-lookup"><span data-stu-id="39e36-147">Valid digit values</span></span>|<span data-ttu-id="39e36-148">示例</span><span class="sxs-lookup"><span data-stu-id="39e36-148">Example</span></span>|  
|-----------------|------------|------------------------|-------------|  
|<span data-ttu-id="39e36-149">十六进制（以 16 为基数）</span><span class="sxs-lookup"><span data-stu-id="39e36-149">Hexadecimal (base 16)</span></span>|`&H`|<span data-ttu-id="39e36-150">0-9 和 A-F</span><span class="sxs-lookup"><span data-stu-id="39e36-150">0-9 and A-F</span></span>|`&HFFFF`|  
|<span data-ttu-id="39e36-151">八进制（以 8 为基数）</span><span class="sxs-lookup"><span data-stu-id="39e36-151">Octal (base 8)</span></span>|`&O`|<span data-ttu-id="39e36-152">0-7</span><span class="sxs-lookup"><span data-stu-id="39e36-152">0-7</span></span>|`&O77`|  
  
 <span data-ttu-id="39e36-153">您可以按照与文本类型字符前缀的文本。</span><span class="sxs-lookup"><span data-stu-id="39e36-153">You can follow a prefixed literal with a literal type character.</span></span> <span data-ttu-id="39e36-154">下面的示例演示了此过程。</span><span class="sxs-lookup"><span data-stu-id="39e36-154">The following example shows this.</span></span>  
  
```  
Dim counter As Short = &H8000S  
Dim flags As UShort = &H8000US  
```  
  
 <span data-ttu-id="39e36-155">在上一示例中，`counter`的十进制值为-32768 和`flags`32768 的十进制值。</span><span class="sxs-lookup"><span data-stu-id="39e36-155">In the previous example, `counter` has the decimal value of -32768, and `flags` has the decimal value of +32768.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="39e36-156">另请参阅</span><span class="sxs-lookup"><span data-stu-id="39e36-156">See Also</span></span>  
 <span data-ttu-id="39e36-157">[数据类型](../../../../visual-basic/programming-guide/language-features/data-types/index.md) </span><span class="sxs-lookup"><span data-stu-id="39e36-157">[Data Types](../../../../visual-basic/programming-guide/language-features/data-types/index.md) </span></span>  
<span data-ttu-id="39e36-158"> [基本数据类型](../../../../visual-basic/programming-guide/language-features/data-types/elementary-data-types.md) </span><span class="sxs-lookup"><span data-stu-id="39e36-158"> [Elementary Data Types](../../../../visual-basic/programming-guide/language-features/data-types/elementary-data-types.md) </span></span>  
<span data-ttu-id="39e36-159"> [值类型和引用类型](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md) </span><span class="sxs-lookup"><span data-stu-id="39e36-159"> [Value Types and Reference Types](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md) </span></span>  
<span data-ttu-id="39e36-160"> [在 Visual Basic 中的类型转换](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md) </span><span class="sxs-lookup"><span data-stu-id="39e36-160"> [Type Conversions in Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md) </span></span>  
<span data-ttu-id="39e36-161"> [数据类型疑难解答](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md) </span><span class="sxs-lookup"><span data-stu-id="39e36-161"> [Troubleshooting Data Types](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md) </span></span>  
<span data-ttu-id="39e36-162"> [变量声明](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md) </span><span class="sxs-lookup"><span data-stu-id="39e36-162"> [Variable Declaration](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md) </span></span>  
<span data-ttu-id="39e36-163"> [数据类型](../../../../visual-basic/language-reference/data-types/data-type-summary.md)</span><span class="sxs-lookup"><span data-stu-id="39e36-163"> [Data Types](../../../../visual-basic/language-reference/data-types/data-type-summary.md)</span></span>
