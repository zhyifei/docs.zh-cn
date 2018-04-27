---
title: 字符串基础 (Visual Basic)
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- strings [Visual Basic], Like operator
- strings [Visual Basic], Visual Basic
- strings [Visual Basic], regular expressions
ms.assetid: 5674418d-f00d-4f72-9f98-d15897793350
caps.latest.revision: 14
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 4a40435b76b0eee4f4eca15d5ba1a31cc58698ab
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/26/2018
---
# <a name="string-basics-in-visual-basic"></a><span data-ttu-id="af986-102">字符串基础 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="af986-102">String Basics in Visual Basic</span></span>
<span data-ttu-id="af986-103">`String` 数据类型表示一系列字符（每个字符都进而表示 `Char` 数据类型的一个实例）。</span><span class="sxs-lookup"><span data-stu-id="af986-103">The `String` data type represents a series of characters (each representing in turn an instance of the `Char` data type).</span></span> <span data-ttu-id="af986-104">本主题介绍了在 Visual Basic 中的字符串的基本概念。</span><span class="sxs-lookup"><span data-stu-id="af986-104">This topic introduces the basic concepts of strings in Visual Basic.</span></span>  
  
## <a name="string-variables"></a><span data-ttu-id="af986-105">字符串变量</span><span class="sxs-lookup"><span data-stu-id="af986-105">String Variables</span></span>  
 <span data-ttu-id="af986-106">可以向字符串的实例分配表示一系列字符的文本值。</span><span class="sxs-lookup"><span data-stu-id="af986-106">An instance of a string can be assigned a literal value that represents a series of characters.</span></span> <span data-ttu-id="af986-107">例如：</span><span class="sxs-lookup"><span data-stu-id="af986-107">For example:</span></span>  
  
 [!code-vb[VbVbalrStrings#63](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/string-basics_1.vb)]  
  
 <span data-ttu-id="af986-108">`String` 变量还可以接受计算结果为字符串的任何表达式。</span><span class="sxs-lookup"><span data-stu-id="af986-108">A `String` variable can also accept any expression that evaluates to a string.</span></span> <span data-ttu-id="af986-109">示例如下所示：</span><span class="sxs-lookup"><span data-stu-id="af986-109">Examples are shown below:</span></span>  
  
 [!code-vb[VbVbalrStrings#64](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/string-basics_2.vb)]  
  
 <span data-ttu-id="af986-110">分配给 `String` 变量的任何文本都必须括在引号 ("") 内。</span><span class="sxs-lookup"><span data-stu-id="af986-110">Any literal that is assigned to a `String` variable must be enclosed in quotation marks ("").</span></span> <span data-ttu-id="af986-111">这意味着字符串中的引号不能使用引号进行表示。</span><span class="sxs-lookup"><span data-stu-id="af986-111">This means that a quotation mark within a string cannot be represented by a quotation mark.</span></span> <span data-ttu-id="af986-112">例如，下面的代码会导致编译器错误：</span><span class="sxs-lookup"><span data-stu-id="af986-112">For example, the following code causes a compiler error:</span></span>  
  
 [!code-vb[VbVbalrStrings#65](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/string-basics_3.vb)]  
  
 <span data-ttu-id="af986-113">此代码会导致错误，因为编译器会在第二个引号之后终止字符串，字符串的其余部分会解释为代码。</span><span class="sxs-lookup"><span data-stu-id="af986-113">This code causes an error because the compiler terminates the string after the second quotation mark, and the remainder of the string is interpreted as code.</span></span> <span data-ttu-id="af986-114">若要解决此问题，Visual Basic 会将文本字符串中的一个引号作为字符串中的两个引号解释。</span><span class="sxs-lookup"><span data-stu-id="af986-114">To solve this problem, Visual Basic interprets two quotation marks in a string literal as one quotation mark in the string.</span></span> <span data-ttu-id="af986-115">下面的示例演示在字符串中包含引号的正确方法：</span><span class="sxs-lookup"><span data-stu-id="af986-115">The following example demonstrates the correct way to include a quotation mark in a string:</span></span>  
  
 [!code-vb[VbVbalrStrings#66](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/string-basics_4.vb)]  
  
 <span data-ttu-id="af986-116">在上面的示例中，字词 `Look` 前面的两个引号会成为字符串中的一个引号。</span><span class="sxs-lookup"><span data-stu-id="af986-116">In the preceding example, the two quotation marks preceding the word `Look` become one quotation mark in the string.</span></span> <span data-ttu-id="af986-117">行尾的三个引号表示字符串中的一个引号和字符串终止符。</span><span class="sxs-lookup"><span data-stu-id="af986-117">The three quotation marks at the end of the line represent one quotation mark in the string and the string termination character.</span></span>  
  
 <span data-ttu-id="af986-118">字符串可以包含多行：</span><span class="sxs-lookup"><span data-stu-id="af986-118">String literals can contain multiple lines:</span></span>  
  
```vb  
Dim x = "hello  
world"  
```  
  
 <span data-ttu-id="af986-119">生成的字符串包含在字符串中使用的换行符序列（vbcr、vbcrlf 等）。</span><span class="sxs-lookup"><span data-stu-id="af986-119">The resulting string contains newline sequences that you used in your string literal (vbcr, vbcrlf, etc.).</span></span>  <span data-ttu-id="af986-120">不再需要使用旧的解决方法：</span><span class="sxs-lookup"><span data-stu-id="af986-120">You no longer need to use the old workaround:</span></span>  
  
```vb  
Dim x = <xml><![CDATA[Hello  
World]]></xml>.Value  
```  
  
## <a name="characters-in-strings"></a><span data-ttu-id="af986-121">字符串中的字符</span><span class="sxs-lookup"><span data-stu-id="af986-121">Characters in Strings</span></span>  
 <span data-ttu-id="af986-122">可以将字符串视为一系列 `Char` 值，`String` 类型具有内置函数，可用于对字符串执行很多操作（类似于数组允许的操作）。</span><span class="sxs-lookup"><span data-stu-id="af986-122">A string can be thought of as a series of `Char` values, and the `String` type has built-in functions that allow you to perform many manipulations on a string that resemble the manipulations allowed by arrays.</span></span> <span data-ttu-id="af986-123">与 [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] 中的所有数组一样，这些是从零开始的数组。</span><span class="sxs-lookup"><span data-stu-id="af986-123">Like all array in [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)], these are zero-based arrays.</span></span> <span data-ttu-id="af986-124">还可以通过 `Chars` 属性引用字符串中的特定字符，该属性提供了一种方法，用于通过字符在字符串中出现的位置来访问它。</span><span class="sxs-lookup"><span data-stu-id="af986-124">You may refer to a specific character in a string through the `Chars` property, which provides a way to access a character by the position in which it appears in the string.</span></span> <span data-ttu-id="af986-125">例如：</span><span class="sxs-lookup"><span data-stu-id="af986-125">For example:</span></span>  
  
 [!code-vb[VbVbalrStrings#67](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/string-basics_5.vb)]  
  
 <span data-ttu-id="af986-126">在上面的示例中，字符串的 `Chars` 属性返回字符串中的第四个字符（即 `D`），并将它分配给 `myChar`。</span><span class="sxs-lookup"><span data-stu-id="af986-126">In the above example, the `Chars` property of the string returns the fourth character in the string, which is `D`, and assigns it to `myChar`.</span></span> <span data-ttu-id="af986-127">还可以通过 `Length` 属性获取特定字符串的长度。</span><span class="sxs-lookup"><span data-stu-id="af986-127">You can also get the length of a particular string through the `Length` property.</span></span> <span data-ttu-id="af986-128">如果需要对字符串执行多个数组类型的操作，则可以使用字符串的 `ToCharArray` 函数将它转换为 `Char` 实例的数组。</span><span class="sxs-lookup"><span data-stu-id="af986-128">If you need to perform multiple array-type manipulations on a string, you can convert it to an array of `Char` instances using the `ToCharArray` function of the string.</span></span> <span data-ttu-id="af986-129">例如：</span><span class="sxs-lookup"><span data-stu-id="af986-129">For example:</span></span>  
  
 [!code-vb[VbVbalrStrings#68](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/string-basics_6.vb)]  
  
 <span data-ttu-id="af986-130">变量 `myArray` 现在包含 `Char` 值的数组，其中每个值都表示 `myString` 中的一个字符。</span><span class="sxs-lookup"><span data-stu-id="af986-130">The variable `myArray` now contains an array of `Char` values, each representing a character from `myString`.</span></span>  
  
## <a name="the-immutability-of-strings"></a><span data-ttu-id="af986-131">字符串的不可变性</span><span class="sxs-lookup"><span data-stu-id="af986-131">The Immutability of Strings</span></span>  
 <span data-ttu-id="af986-132">一个字符串是否为*不可变*，其值不能一次更改这意味着它已创建。</span><span class="sxs-lookup"><span data-stu-id="af986-132">A string is *immutable*, which means its value cannot be changed once it has been created.</span></span> <span data-ttu-id="af986-133">但是，这不会阻止你将多个值分配给字符串变量。</span><span class="sxs-lookup"><span data-stu-id="af986-133">However, this does not prevent you from assigning more than one value to a string variable.</span></span> <span data-ttu-id="af986-134">请看下面的示例：</span><span class="sxs-lookup"><span data-stu-id="af986-134">Consider the following example:</span></span>  
  
 [!code-vb[VbVbalrStrings#69](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/string-basics_7.vb)]  
  
 <span data-ttu-id="af986-135">这里会创建一个字符串变量（向它提供值），然后更改其值。</span><span class="sxs-lookup"><span data-stu-id="af986-135">Here, a string variable is created, given a value, and then its value is changed.</span></span>  
  
 <span data-ttu-id="af986-136">更具体地说，在第一行中，会创建类型 `String` 的实例，并提供值 `This string is immutable`。</span><span class="sxs-lookup"><span data-stu-id="af986-136">More specifically, in the first line, an instance of type `String` is created and given the value `This string is immutable`.</span></span> <span data-ttu-id="af986-137">在示例的第二个行中，会创建一个新实例并向它提供值 `Or is it?`，字符串变量会放弃它对第一个实例的引用，并存储对新实例的引用。</span><span class="sxs-lookup"><span data-stu-id="af986-137">In the second line of the example, a new instance is created and given the value `Or is it?`, and the string variable discards its reference to the first instance and stores a reference to the new instance.</span></span>  
  
 <span data-ttu-id="af986-138">与其他内部数据类型不同，`String` 是引用类型。</span><span class="sxs-lookup"><span data-stu-id="af986-138">Unlike other intrinsic data types, `String` is a reference type.</span></span> <span data-ttu-id="af986-139">当引用类型的变量作为参数传递给函数或子例程时，会传递对数据存储位置的内存地址的引用（而不是字符串的实际值）。</span><span class="sxs-lookup"><span data-stu-id="af986-139">When a variable of reference type is passed as an argument to a function or subroutine, a reference to the memory address where the data is stored is passed instead of the actual value of the string.</span></span> <span data-ttu-id="af986-140">因此在上面的示例中，变量的名称保持不变，但它会指向 `String` 类的另一个新实例（该实例会保存新值）。</span><span class="sxs-lookup"><span data-stu-id="af986-140">So in the previous example, the name of the variable remains the same, but it points to a new and different instance of the `String` class, which holds the new value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="af986-141">请参阅</span><span class="sxs-lookup"><span data-stu-id="af986-141">See Also</span></span>  
 [<span data-ttu-id="af986-142">Visual Basic 中的字符串简介</span><span class="sxs-lookup"><span data-stu-id="af986-142">Introduction to Strings in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/strings/introduction-to-strings.md)  
 [<span data-ttu-id="af986-143">String 数据类型</span><span class="sxs-lookup"><span data-stu-id="af986-143">String Data Type</span></span>](../../../../visual-basic/language-reference/data-types/string-data-type.md)  
 [<span data-ttu-id="af986-144">Char 数据类型</span><span class="sxs-lookup"><span data-stu-id="af986-144">Char Data Type</span></span>](../../../../visual-basic/language-reference/data-types/char-data-type.md)  
 [<span data-ttu-id="af986-145">基本字符串操作</span><span class="sxs-lookup"><span data-stu-id="af986-145">Basic String Operations</span></span>](../../../../standard/base-types/basic-string-operations.md)
