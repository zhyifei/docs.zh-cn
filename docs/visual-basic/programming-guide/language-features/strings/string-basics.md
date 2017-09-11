---
title: "在 Visual Basic 中的基础知识的字符串 |Microsoft 文档"
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
- strings [Visual Basic], Like operator
- strings [Visual Basic], Visual Basic
- strings [Visual Basic], regular expressions
ms.assetid: 5674418d-f00d-4f72-9f98-d15897793350
caps.latest.revision: 14
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
ms.openlocfilehash: 98c2707ef8aabc77951b21cfe9f4edcd3a88c863
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017

---
# <a name="string-basics-in-visual-basic"></a><span data-ttu-id="62369-102">字符串基础 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="62369-102">String Basics in Visual Basic</span></span>
<span data-ttu-id="62369-103">`String` 数据类型表示一系列字符（每个字符都进而表示 `Char` 数据类型的一个实例）。</span><span class="sxs-lookup"><span data-stu-id="62369-103">The `String` data type represents a series of characters (each representing in turn an instance of the `Char` data type).</span></span> <span data-ttu-id="62369-104">本主题介绍 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 中的字符串的基本概念。</span><span class="sxs-lookup"><span data-stu-id="62369-104">This topic introduces the basic concepts of strings in [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)].</span></span>  
  
## <a name="string-variables"></a><span data-ttu-id="62369-105">字符串变量</span><span class="sxs-lookup"><span data-stu-id="62369-105">String Variables</span></span>  
 <span data-ttu-id="62369-106">可以向字符串的实例分配表示一系列字符的文本值。</span><span class="sxs-lookup"><span data-stu-id="62369-106">An instance of a string can be assigned a literal value that represents a series of characters.</span></span> <span data-ttu-id="62369-107">例如: </span><span class="sxs-lookup"><span data-stu-id="62369-107">For example:</span></span>  
  
 <span data-ttu-id="62369-108">[!code-vb[VbVbalrStrings #&63;](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/string-basics_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="62369-108">[!code-vb[VbVbalrStrings#63](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/string-basics_1.vb)]</span></span>  
  
 <span data-ttu-id="62369-109">`String` 变量还可以接受计算结果为字符串的任何表达式。</span><span class="sxs-lookup"><span data-stu-id="62369-109">A `String` variable can also accept any expression that evaluates to a string.</span></span> <span data-ttu-id="62369-110">示例如下所示：</span><span class="sxs-lookup"><span data-stu-id="62369-110">Examples are shown below:</span></span>  
  
 <span data-ttu-id="62369-111">[!code-vb[VbVbalrStrings #&64;](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/string-basics_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="62369-111">[!code-vb[VbVbalrStrings#64](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/string-basics_2.vb)]</span></span>  
  
 <span data-ttu-id="62369-112">分配给 `String` 变量的任何文本都必须括在引号 ("") 内。</span><span class="sxs-lookup"><span data-stu-id="62369-112">Any literal that is assigned to a `String` variable must be enclosed in quotation marks ("").</span></span> <span data-ttu-id="62369-113">这意味着字符串中的引号不能使用引号进行表示。</span><span class="sxs-lookup"><span data-stu-id="62369-113">This means that a quotation mark within a string cannot be represented by a quotation mark.</span></span> <span data-ttu-id="62369-114">例如，下面的代码会导致编译器错误：</span><span class="sxs-lookup"><span data-stu-id="62369-114">For example, the following code causes a compiler error:</span></span>  
  
 <span data-ttu-id="62369-115">[!code-vb[VbVbalrStrings #&65;](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/string-basics_3.vb)]</span><span class="sxs-lookup"><span data-stu-id="62369-115">[!code-vb[VbVbalrStrings#65](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/string-basics_3.vb)]</span></span>  
  
 <span data-ttu-id="62369-116">此代码会导致错误，因为编译器会在第二个引号之后终止字符串，字符串的其余部分会解释为代码。</span><span class="sxs-lookup"><span data-stu-id="62369-116">This code causes an error because the compiler terminates the string after the second quotation mark, and the remainder of the string is interpreted as code.</span></span> <span data-ttu-id="62369-117">为了解决此问题，[!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 会将字符串中的两个引号解释为字符串中的一个引号。</span><span class="sxs-lookup"><span data-stu-id="62369-117">To solve this problem, [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] interprets two quotation marks in a string literal as one quotation mark in the string.</span></span> <span data-ttu-id="62369-118">下面的示例演示在字符串中包含引号的正确方法：</span><span class="sxs-lookup"><span data-stu-id="62369-118">The following example demonstrates the correct way to include a quotation mark in a string:</span></span>  
  
 <span data-ttu-id="62369-119">[!code-vb[VbVbalrStrings #&66;](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/string-basics_4.vb)]</span><span class="sxs-lookup"><span data-stu-id="62369-119">[!code-vb[VbVbalrStrings#66](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/string-basics_4.vb)]</span></span>  
  
 <span data-ttu-id="62369-120">在上面的示例中，字词 `Look` 前面的两个引号会成为字符串中的一个引号。</span><span class="sxs-lookup"><span data-stu-id="62369-120">In the preceding example, the two quotation marks preceding the word `Look` become one quotation mark in the string.</span></span> <span data-ttu-id="62369-121">行尾的三个引号表示字符串中的一个引号和字符串终止符。</span><span class="sxs-lookup"><span data-stu-id="62369-121">The three quotation marks at the end of the line represent one quotation mark in the string and the string termination character.</span></span>  
  
 <span data-ttu-id="62369-122">字符串可以包含多行：</span><span class="sxs-lookup"><span data-stu-id="62369-122">String literals can contain multiple lines:</span></span>  
  
```vb  
Dim x = "hello  
world"  
  
```  
  
 <span data-ttu-id="62369-123">生成的字符串包含在字符串中使用的换行符序列（vbcr、vbcrlf 等）。</span><span class="sxs-lookup"><span data-stu-id="62369-123">The resulting string contains newline sequences that you used in your string literal (vbcr, vbcrlf, etc.).</span></span>  <span data-ttu-id="62369-124">不再需要使用旧的解决方法：</span><span class="sxs-lookup"><span data-stu-id="62369-124">You no longer need to use the old workaround:</span></span>  
  
```vb  
Dim x = <xml><![CDATA[Hello  
World]]></xml>.Value  
  
```  
  
## <a name="characters-in-strings"></a><span data-ttu-id="62369-125">字符串中的字符</span><span class="sxs-lookup"><span data-stu-id="62369-125">Characters in Strings</span></span>  
 <span data-ttu-id="62369-126">可以将字符串视为一系列 `Char` 值，`String` 类型具有内置函数，可用于对字符串执行很多操作（类似于数组允许的操作）。</span><span class="sxs-lookup"><span data-stu-id="62369-126">A string can be thought of as a series of `Char` values, and the `String` type has built-in functions that allow you to perform many manipulations on a string that resemble the manipulations allowed by arrays.</span></span> <span data-ttu-id="62369-127">与 [!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort_md.md)] 中的所有数组一样，这些是从零开始的数组。</span><span class="sxs-lookup"><span data-stu-id="62369-127">Like all array in [!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort_md.md)], these are zero-based arrays.</span></span> <span data-ttu-id="62369-128">还可以通过 `Chars` 属性引用字符串中的特定字符，该属性提供了一种方法，用于通过字符在字符串中出现的位置来访问它。</span><span class="sxs-lookup"><span data-stu-id="62369-128">You may refer to a specific character in a string through the `Chars` property, which provides a way to access a character by the position in which it appears in the string.</span></span> <span data-ttu-id="62369-129">例如：</span><span class="sxs-lookup"><span data-stu-id="62369-129">For example:</span></span>  
  
 <span data-ttu-id="62369-130">[!code-vb[VbVbalrStrings #&67;](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/string-basics_5.vb)]</span><span class="sxs-lookup"><span data-stu-id="62369-130">[!code-vb[VbVbalrStrings#67](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/string-basics_5.vb)]</span></span>  
  
 <span data-ttu-id="62369-131">在上面的示例中，字符串的 `Chars` 属性返回字符串中的第四个字符（即 `D`），并将它分配给 `myChar`。</span><span class="sxs-lookup"><span data-stu-id="62369-131">In the above example, the `Chars` property of the string returns the fourth character in the string, which is `D`, and assigns it to `myChar`.</span></span> <span data-ttu-id="62369-132">还可以通过 `Length` 属性获取特定字符串的长度。</span><span class="sxs-lookup"><span data-stu-id="62369-132">You can also get the length of a particular string through the `Length` property.</span></span> <span data-ttu-id="62369-133">如果需要对字符串执行多个数组类型的操作，则可以使用字符串的 `ToCharArray` 函数将它转换为 `Char` 实例的数组。</span><span class="sxs-lookup"><span data-stu-id="62369-133">If you need to perform multiple array-type manipulations on a string, you can convert it to an array of `Char` instances using the `ToCharArray` function of the string.</span></span> <span data-ttu-id="62369-134">例如: </span><span class="sxs-lookup"><span data-stu-id="62369-134">For example:</span></span>  
  
 <span data-ttu-id="62369-135">[!code-vb[VbVbalrStrings #&68;](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/string-basics_6.vb)]</span><span class="sxs-lookup"><span data-stu-id="62369-135">[!code-vb[VbVbalrStrings#68](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/string-basics_6.vb)]</span></span>  
  
 <span data-ttu-id="62369-136">变量 `myArray` 现在包含 `Char` 值的数组，其中每个值都表示 `myString` 中的一个字符。</span><span class="sxs-lookup"><span data-stu-id="62369-136">The variable `myArray` now contains an array of `Char` values, each representing a character from `myString`.</span></span>  
  
## <a name="the-immutability-of-strings"></a><span data-ttu-id="62369-137">字符串的不可变性</span><span class="sxs-lookup"><span data-stu-id="62369-137">The Immutability of Strings</span></span>  
 <span data-ttu-id="62369-138">一个字符串是*不可变*，其值不能更改一次这意味着它已创建。</span><span class="sxs-lookup"><span data-stu-id="62369-138">A string is *immutable*, which means its value cannot be changed once it has been created.</span></span> <span data-ttu-id="62369-139">但是，这不会阻止你将多个值分配给字符串变量。</span><span class="sxs-lookup"><span data-stu-id="62369-139">However, this does not prevent you from assigning more than one value to a string variable.</span></span> <span data-ttu-id="62369-140">请看下面的示例：</span><span class="sxs-lookup"><span data-stu-id="62369-140">Consider the following example:</span></span>  
  
 <span data-ttu-id="62369-141">[!code-vb[VbVbalrStrings #&69;](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/string-basics_7.vb)]</span><span class="sxs-lookup"><span data-stu-id="62369-141">[!code-vb[VbVbalrStrings#69](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/string-basics_7.vb)]</span></span>  
  
 <span data-ttu-id="62369-142">这里会创建一个字符串变量（向它提供值），然后更改其值。</span><span class="sxs-lookup"><span data-stu-id="62369-142">Here, a string variable is created, given a value, and then its value is changed.</span></span>  
  
 <span data-ttu-id="62369-143">更具体地说，在第一行中，会创建类型 `String` 的实例，并提供值 `This string is immutable`。</span><span class="sxs-lookup"><span data-stu-id="62369-143">More specifically, in the first line, an instance of type `String` is created and given the value `This string is immutable`.</span></span> <span data-ttu-id="62369-144">在示例的第二个行中，会创建一个新实例并向它提供值 `Or is it?`，字符串变量会放弃它对第一个实例的引用，并存储对新实例的引用。</span><span class="sxs-lookup"><span data-stu-id="62369-144">In the second line of the example, a new instance is created and given the value `Or is it?`, and the string variable discards its reference to the first instance and stores a reference to the new instance.</span></span>  
  
 <span data-ttu-id="62369-145">与其他内部数据类型不同，`String` 是引用类型。</span><span class="sxs-lookup"><span data-stu-id="62369-145">Unlike other intrinsic data types, `String` is a reference type.</span></span> <span data-ttu-id="62369-146">当引用类型的变量作为参数传递给函数或子例程时，会传递对数据存储位置的内存地址的引用（而不是字符串的实际值）。</span><span class="sxs-lookup"><span data-stu-id="62369-146">When a variable of reference type is passed as an argument to a function or subroutine, a reference to the memory address where the data is stored is passed instead of the actual value of the string.</span></span> <span data-ttu-id="62369-147">因此在上面的示例中，变量的名称保持不变，但它会指向 `String` 类的另一个新实例（该实例会保存新值）。</span><span class="sxs-lookup"><span data-stu-id="62369-147">So in the previous example, the name of the variable remains the same, but it points to a new and different instance of the `String` class, which holds the new value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="62369-148">另请参阅</span><span class="sxs-lookup"><span data-stu-id="62369-148">See Also</span></span>  
 <span data-ttu-id="62369-149">[在 Visual Basic 中字符串的简介](../../../../visual-basic/programming-guide/language-features/strings/introduction-to-strings.md) </span><span class="sxs-lookup"><span data-stu-id="62369-149">[Introduction to Strings in Visual Basic](../../../../visual-basic/programming-guide/language-features/strings/introduction-to-strings.md) </span></span>  
<span data-ttu-id="62369-150"> [String 数据类型](../../../../visual-basic/language-reference/data-types/string-data-type.md) </span><span class="sxs-lookup"><span data-stu-id="62369-150"> [String Data Type](../../../../visual-basic/language-reference/data-types/string-data-type.md) </span></span>  
<span data-ttu-id="62369-151"> [Char 数据类型](../../../../visual-basic/language-reference/data-types/char-data-type.md) </span><span class="sxs-lookup"><span data-stu-id="62369-151"> [Char Data Type](../../../../visual-basic/language-reference/data-types/char-data-type.md) </span></span>  
<span data-ttu-id="62369-152"> [基本字符串操作](http://msdn.microsoft.com/library/8133d357-90b5-4b62-9927-43323d99b6b6)</span><span class="sxs-lookup"><span data-stu-id="62369-152"> [Basic String Operations](http://msdn.microsoft.com/library/8133d357-90b5-4b62-9927-43323d99b6b6)</span></span>
