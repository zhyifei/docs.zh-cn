---
title: "常量和 Literal 数据类型 (Visual Basic) |Microsoft 文档"
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
- declaring constants, literal data types
- data types [Visual Basic], declaring
- constants, declaring
- explicit declarations
- literals, coercing data type
- declarations, data types
ms.assetid: 057206d2-3a5b-40b9-b3af-57446f9b52fa
caps.latest.revision: 19
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
ms.openlocfilehash: 29a997ee0dd847e8505d1a5c24cacfdfdb0a42cc
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017

---
# <a name="constant-and-literal-data-types-visual-basic"></a><span data-ttu-id="55e8e-102">常量和 Literal 数据类型 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="55e8e-102">Constant and Literal Data Types (Visual Basic)</span></span>
<span data-ttu-id="55e8e-103">文本是一个值，表示为本身而不是变量的值或表达式，如数字 3 或字符串"Hello"的结果。</span><span class="sxs-lookup"><span data-stu-id="55e8e-103">A literal is a value that is expressed as itself rather than as a variable's value or the result of an expression, such as the number 3 or the string "Hello".</span></span> <span data-ttu-id="55e8e-104">常量是有意义的名称，取代了文字，但它保留在整个程序，而不是一个变量，其值可能会更改此相同的值。</span><span class="sxs-lookup"><span data-stu-id="55e8e-104">A constant is a meaningful name that takes the place of a literal and retains this same value throughout the program, as opposed to a variable, whose value may change.</span></span>  
  
 <span data-ttu-id="55e8e-105">当[Option Infer](../../../../visual-basic/language-reference/statements/option-infer-statement.md)是`Off`和[Option Strict](../../../../visual-basic/language-reference/statements/option-strict-statement.md)是`On`，您必须显式声明的所有常量具有数据类型。</span><span class="sxs-lookup"><span data-stu-id="55e8e-105">When [Option Infer](../../../../visual-basic/language-reference/statements/option-infer-statement.md) is `Off` and [Option Strict](../../../../visual-basic/language-reference/statements/option-strict-statement.md) is `On`, you must declare all constants explicitly with a data type.</span></span> <span data-ttu-id="55e8e-106">在下面的示例中的数据类型`MyByte`显式声明数据类型为`Byte`:</span><span class="sxs-lookup"><span data-stu-id="55e8e-106">In the following example, the data type of `MyByte` is explicitly declared as data type `Byte`:</span></span>  
  
 <span data-ttu-id="55e8e-107">[!code-vb[VbVbalrConstants #&1;](../../../../visual-basic/programming-guide/language-features/constants-enums/codesnippet/VisualBasic/constant-and-literal-data-types_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="55e8e-107">[!code-vb[VbVbalrConstants#1](../../../../visual-basic/programming-guide/language-features/constants-enums/codesnippet/VisualBasic/constant-and-literal-data-types_1.vb)]</span></span>  
  
 <span data-ttu-id="55e8e-108">当`Option Infer`是`On`或`Option Strict`是`Off`，您可以声明变量，而无需指定数据类型为`As`子句。</span><span class="sxs-lookup"><span data-stu-id="55e8e-108">When `Option Infer` is `On` or `Option Strict` is `Off`, you can declare a constant without specifying a data type with an `As` clause.</span></span> <span data-ttu-id="55e8e-109">编译器确定的常量表达式的类型的类型。</span><span class="sxs-lookup"><span data-stu-id="55e8e-109">The compiler determines the type of the constant from the type of the expression.</span></span> <span data-ttu-id="55e8e-110">一个数字的整数文本被强制转换到默认情况下`Integer`数据类型。</span><span class="sxs-lookup"><span data-stu-id="55e8e-110">A numeric integer literal is cast by default to the `Integer` data type.</span></span> <span data-ttu-id="55e8e-111">默认的数据类型为浮点数`Double`，和关键字`True`和`False`指定`Boolean`常量。</span><span class="sxs-lookup"><span data-stu-id="55e8e-111">The default data type for floating-point numbers is `Double`, and the keywords `True` and `False` specify a `Boolean` constant.</span></span>  
  
## <a name="literals-and-type-coercion"></a><span data-ttu-id="55e8e-112">文本和类型强制</span><span class="sxs-lookup"><span data-stu-id="55e8e-112">Literals and Type Coercion</span></span>  
 <span data-ttu-id="55e8e-113">在某些情况下，您可能想要将文本强制为特定的数据类型;例如，当将特别大的整数文字值分配给类型的变量`Decimal`。</span><span class="sxs-lookup"><span data-stu-id="55e8e-113">In some cases, you might want to force a literal to a particular data type; for example, when assigning a particularly large integral literal value to a variable of type `Decimal`.</span></span> <span data-ttu-id="55e8e-114">下面的示例将生成错误︰</span><span class="sxs-lookup"><span data-stu-id="55e8e-114">The following example produces an error:</span></span>  
  
```  
Dim myDecimal as Decimal  
myDecimal = 100000000000000000000   ' This causes a compiler error.  
```  
  
 <span data-ttu-id="55e8e-115">从文本表示形式会产生错误。</span><span class="sxs-lookup"><span data-stu-id="55e8e-115">The error results from the representation of the literal.</span></span> <span data-ttu-id="55e8e-116">`Decimal`数据类型可以保存一个值过大，但文本隐式地表示为`Long`，哪些不能执行。</span><span class="sxs-lookup"><span data-stu-id="55e8e-116">The `Decimal` data type can hold a value this large, but the literal is implicitly represented as a `Long`, which cannot.</span></span>  
  
 <span data-ttu-id="55e8e-117">您可以强制转换为两种方法中的特定数据类型的文字︰ 通过将类型字符追加到它，或将它置于封闭字符内。</span><span class="sxs-lookup"><span data-stu-id="55e8e-117">You can coerce a literal to a particular data type in two ways: by appending a type character to it, or by placing it within enclosing characters.</span></span> <span data-ttu-id="55e8e-118">类型字符或封闭字符必须立即之前和/或按照在文字之前，加没有插入空格或任何类型的字符。</span><span class="sxs-lookup"><span data-stu-id="55e8e-118">A type character or enclosing characters must immediately precede and/or follow the literal, with no intervening space or characters of any kind.</span></span>  
  
 <span data-ttu-id="55e8e-119">若要使上例正确运行，您可以将附加`D`类型，它使其表示为文本字符`Decimal`:</span><span class="sxs-lookup"><span data-stu-id="55e8e-119">To make the previous example work, you can append the `D` type character to the literal, which causes it to be represented as a `Decimal`:</span></span>  
  
 <span data-ttu-id="55e8e-120">[!code-vb[VbVbalrConstants #&2;](../../../../visual-basic/programming-guide/language-features/constants-enums/codesnippet/VisualBasic/constant-and-literal-data-types_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="55e8e-120">[!code-vb[VbVbalrConstants#2](../../../../visual-basic/programming-guide/language-features/constants-enums/codesnippet/VisualBasic/constant-and-literal-data-types_2.vb)]</span></span>  
  
 <span data-ttu-id="55e8e-121">下面的示例演示类型的字符和封闭字符的正确用法︰</span><span class="sxs-lookup"><span data-stu-id="55e8e-121">The following example demonstrates correct usage of type characters and enclosing characters:</span></span>  
  
 <span data-ttu-id="55e8e-122">[!code-vb[VbVbalrConstants #&3;](../../../../visual-basic/programming-guide/language-features/constants-enums/codesnippet/VisualBasic/constant-and-literal-data-types_3.vb)]</span><span class="sxs-lookup"><span data-stu-id="55e8e-122">[!code-vb[VbVbalrConstants#3](../../../../visual-basic/programming-guide/language-features/constants-enums/codesnippet/VisualBasic/constant-and-literal-data-types_3.vb)]</span></span>  
  
 <span data-ttu-id="55e8e-123">如下表所示的封闭字符和类型的字符位于[!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]。</span><span class="sxs-lookup"><span data-stu-id="55e8e-123">The following table shows the enclosing characters and type characters available in [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)].</span></span>  
  
|<span data-ttu-id="55e8e-124">数据类型</span><span class="sxs-lookup"><span data-stu-id="55e8e-124">Data type</span></span>|<span data-ttu-id="55e8e-125">封闭字符</span><span class="sxs-lookup"><span data-stu-id="55e8e-125">Enclosing character</span></span>|<span data-ttu-id="55e8e-126">追加的类型字符</span><span class="sxs-lookup"><span data-stu-id="55e8e-126">Appended type character</span></span>|  
|---|---|---|  
|`Boolean`|<span data-ttu-id="55e8e-127">（无）</span><span class="sxs-lookup"><span data-stu-id="55e8e-127">(none)</span></span>|<span data-ttu-id="55e8e-128">（无）</span><span class="sxs-lookup"><span data-stu-id="55e8e-128">(none)</span></span>|  
|`Byte`|<span data-ttu-id="55e8e-129">（无）</span><span class="sxs-lookup"><span data-stu-id="55e8e-129">(none)</span></span>|<span data-ttu-id="55e8e-130">（无）</span><span class="sxs-lookup"><span data-stu-id="55e8e-130">(none)</span></span>|  
|`Char`|<span data-ttu-id="55e8e-131">"</span><span class="sxs-lookup"><span data-stu-id="55e8e-131">"</span></span>|<span data-ttu-id="55e8e-132">C</span><span class="sxs-lookup"><span data-stu-id="55e8e-132">C</span></span>|  
|`Date`|#|<span data-ttu-id="55e8e-133">（无）</span><span class="sxs-lookup"><span data-stu-id="55e8e-133">(none)</span></span>|  
|`Decimal`|<span data-ttu-id="55e8e-134">（无）</span><span class="sxs-lookup"><span data-stu-id="55e8e-134">(none)</span></span>|<span data-ttu-id="55e8e-135">D 或 @</span><span class="sxs-lookup"><span data-stu-id="55e8e-135">D or @</span></span>|  
|`Double`|<span data-ttu-id="55e8e-136">（无）</span><span class="sxs-lookup"><span data-stu-id="55e8e-136">(none)</span></span>|<span data-ttu-id="55e8e-137">R 或</span><span class="sxs-lookup"><span data-stu-id="55e8e-137">R or</span></span> #|  
|`Integer`|<span data-ttu-id="55e8e-138">（无）</span><span class="sxs-lookup"><span data-stu-id="55e8e-138">(none)</span></span>|<span data-ttu-id="55e8e-139">I 或 %</span><span class="sxs-lookup"><span data-stu-id="55e8e-139">I or %</span></span>|  
|`Long`|<span data-ttu-id="55e8e-140">（无）</span><span class="sxs-lookup"><span data-stu-id="55e8e-140">(none)</span></span>|<span data-ttu-id="55e8e-141">L 或.</span><span class="sxs-lookup"><span data-stu-id="55e8e-141">L or &</span></span>|  
|`Short`|<span data-ttu-id="55e8e-142">（无）</span><span class="sxs-lookup"><span data-stu-id="55e8e-142">(none)</span></span>|<span data-ttu-id="55e8e-143">S</span><span class="sxs-lookup"><span data-stu-id="55e8e-143">S</span></span>|  
|`Single`|<span data-ttu-id="55e8e-144">（无）</span><span class="sxs-lookup"><span data-stu-id="55e8e-144">(none)</span></span>|<span data-ttu-id="55e8e-145">F 或 ！</span><span class="sxs-lookup"><span data-stu-id="55e8e-145">F or !</span></span>|  
|`String`|<span data-ttu-id="55e8e-146">"</span><span class="sxs-lookup"><span data-stu-id="55e8e-146">"</span></span>|<span data-ttu-id="55e8e-147">（无）</span><span class="sxs-lookup"><span data-stu-id="55e8e-147">(none)</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="55e8e-148">另请参阅</span><span class="sxs-lookup"><span data-stu-id="55e8e-148">See Also</span></span>  
 <span data-ttu-id="55e8e-149">[用户定义的常量](../../../../visual-basic/programming-guide/language-features/constants-enums/user-defined-constants.md) </span><span class="sxs-lookup"><span data-stu-id="55e8e-149">[User-Defined Constants](../../../../visual-basic/programming-guide/language-features/constants-enums/user-defined-constants.md) </span></span>  
<span data-ttu-id="55e8e-150"> [如何︰ 声明常量](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-a-constant.md) </span><span class="sxs-lookup"><span data-stu-id="55e8e-150"> [How to: Declare A Constant](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-a-constant.md) </span></span>  
<span data-ttu-id="55e8e-151"> [常量概述](../../../../visual-basic/programming-guide/language-features/constants-enums/constants-overview.md) </span><span class="sxs-lookup"><span data-stu-id="55e8e-151"> [Constants Overview](../../../../visual-basic/programming-guide/language-features/constants-enums/constants-overview.md) </span></span>  
<span data-ttu-id="55e8e-152"> [Option Strict 语句](../../../../visual-basic/language-reference/statements/option-strict-statement.md) </span><span class="sxs-lookup"><span data-stu-id="55e8e-152"> [Option Strict Statement](../../../../visual-basic/language-reference/statements/option-strict-statement.md) </span></span>  
<span data-ttu-id="55e8e-153"> [Option Explicit 语句](../../../../visual-basic/language-reference/statements/option-explicit-statement.md) </span><span class="sxs-lookup"><span data-stu-id="55e8e-153"> [Option Explicit Statement](../../../../visual-basic/language-reference/statements/option-explicit-statement.md) </span></span>  
<span data-ttu-id="55e8e-154"> [枚举概述](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-overview.md) </span><span class="sxs-lookup"><span data-stu-id="55e8e-154"> [Enumerations Overview](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-overview.md) </span></span>  
<span data-ttu-id="55e8e-155"> [如何︰ 声明枚举](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-enumerations.md) </span><span class="sxs-lookup"><span data-stu-id="55e8e-155"> [How to: Declare an Enumeration](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-enumerations.md) </span></span>  
<span data-ttu-id="55e8e-156"> [枚举和名称限定](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md) </span><span class="sxs-lookup"><span data-stu-id="55e8e-156"> [Enumerations and Name Qualification](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md) </span></span>  
<span data-ttu-id="55e8e-157"> [数据类型](../../../../visual-basic/language-reference/data-types/data-type-summary.md) </span><span class="sxs-lookup"><span data-stu-id="55e8e-157"> [Data Types](../../../../visual-basic/language-reference/data-types/data-type-summary.md) </span></span>  
<span data-ttu-id="55e8e-158"> [常量和枚举](../../../../visual-basic/language-reference/constants-and-enumerations.md)</span><span class="sxs-lookup"><span data-stu-id="55e8e-158"> [Constants and Enumerations](../../../../visual-basic/language-reference/constants-and-enumerations.md)</span></span>
