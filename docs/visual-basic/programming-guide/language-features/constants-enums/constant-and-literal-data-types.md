---
title: 常量和 Literal 数据类型 (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- declaring constants [Visual Basic], literal data types
- data types [Visual Basic], declaring
- constants [Visual Basic], declaring
- explicit declarations
- literals [Visual Basic], coercing data type
- declarations [Visual Basic], data types
ms.assetid: 057206d2-3a5b-40b9-b3af-57446f9b52fa
ms.openlocfilehash: 8d110ec17bcdb03f339d779b2950ba56d77957cc
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33649843"
---
# <a name="constant-and-literal-data-types-visual-basic"></a><span data-ttu-id="ab5f6-102">常量和 Literal 数据类型 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ab5f6-102">Constant and Literal Data Types (Visual Basic)</span></span>
<span data-ttu-id="ab5f6-103">文本是一个值，表示为本身而不是变量的值或表达式，如数字 3 或字符串"Hello"的结果。</span><span class="sxs-lookup"><span data-stu-id="ab5f6-103">A literal is a value that is expressed as itself rather than as a variable's value or the result of an expression, such as the number 3 or the string "Hello".</span></span> <span data-ttu-id="ab5f6-104">常量是有意义的名称，它接受文本的位置，并保留在整个程序，而不是一个变量，其值可能会更改此相同的值。</span><span class="sxs-lookup"><span data-stu-id="ab5f6-104">A constant is a meaningful name that takes the place of a literal and retains this same value throughout the program, as opposed to a variable, whose value may change.</span></span>  
  
 <span data-ttu-id="ab5f6-105">当[Option Infer](../../../../visual-basic/language-reference/statements/option-infer-statement.md)是`Off`和[Option Strict](../../../../visual-basic/language-reference/statements/option-strict-statement.md)是`On`，你必须显式声明所有常量具有数据类型。</span><span class="sxs-lookup"><span data-stu-id="ab5f6-105">When [Option Infer](../../../../visual-basic/language-reference/statements/option-infer-statement.md) is `Off` and [Option Strict](../../../../visual-basic/language-reference/statements/option-strict-statement.md) is `On`, you must declare all constants explicitly with a data type.</span></span> <span data-ttu-id="ab5f6-106">以下示例中中的数据类型`MyByte`显式声明数据类型为`Byte`:</span><span class="sxs-lookup"><span data-stu-id="ab5f6-106">In the following example, the data type of `MyByte` is explicitly declared as data type `Byte`:</span></span>  
  
 [!code-vb[VbVbalrConstants#1](../../../../visual-basic/programming-guide/language-features/constants-enums/codesnippet/VisualBasic/constant-and-literal-data-types_1.vb)]  
  
 <span data-ttu-id="ab5f6-107">当`Option Infer`是`On`或`Option Strict`是`Off`，你可以声明变量，而无需指定的数据类型`As`子句。</span><span class="sxs-lookup"><span data-stu-id="ab5f6-107">When `Option Infer` is `On` or `Option Strict` is `Off`, you can declare a constant without specifying a data type with an `As` clause.</span></span> <span data-ttu-id="ab5f6-108">编译器确定常量的表达式的类型的类型。</span><span class="sxs-lookup"><span data-stu-id="ab5f6-108">The compiler determines the type of the constant from the type of the expression.</span></span> <span data-ttu-id="ab5f6-109">数字的整数文本被强制转换为默认情况下`Integer`数据类型。</span><span class="sxs-lookup"><span data-stu-id="ab5f6-109">A numeric integer literal is cast by default to the `Integer` data type.</span></span> <span data-ttu-id="ab5f6-110">默认数据类型为浮点数字`Double`，和关键字`True`和`False`指定`Boolean`常量。</span><span class="sxs-lookup"><span data-stu-id="ab5f6-110">The default data type for floating-point numbers is `Double`, and the keywords `True` and `False` specify a `Boolean` constant.</span></span>  
  
## <a name="literals-and-type-coercion"></a><span data-ttu-id="ab5f6-111">文本和类型强制</span><span class="sxs-lookup"><span data-stu-id="ab5f6-111">Literals and Type Coercion</span></span>  
 <span data-ttu-id="ab5f6-112">在某些情况下，你可能想要文本强制转换为特定的数据类型;例如，将特别大的整型文本值分配给类型的变量时`Decimal`。</span><span class="sxs-lookup"><span data-stu-id="ab5f6-112">In some cases, you might want to force a literal to a particular data type; for example, when assigning a particularly large integral literal value to a variable of type `Decimal`.</span></span> <span data-ttu-id="ab5f6-113">下面的示例将生成错误：</span><span class="sxs-lookup"><span data-stu-id="ab5f6-113">The following example produces an error:</span></span>  
  
```  
Dim myDecimal as Decimal  
myDecimal = 100000000000000000000   ' This causes a compiler error.  
```  
  
 <span data-ttu-id="ab5f6-114">中的文本表示形式的错误结果。</span><span class="sxs-lookup"><span data-stu-id="ab5f6-114">The error results from the representation of the literal.</span></span> <span data-ttu-id="ab5f6-115">`Decimal`数据类型可以保存值过大，但文本隐式表示为`Long`，哪些不能。</span><span class="sxs-lookup"><span data-stu-id="ab5f6-115">The `Decimal` data type can hold a value this large, but the literal is implicitly represented as a `Long`, which cannot.</span></span>  
  
 <span data-ttu-id="ab5f6-116">可以强制转换为特定数据类型以两种方式是文本： 通过将类型字符追加到它，或将它放置在封闭字符。</span><span class="sxs-lookup"><span data-stu-id="ab5f6-116">You can coerce a literal to a particular data type in two ways: by appending a type character to it, or by placing it within enclosing characters.</span></span> <span data-ttu-id="ab5f6-117">类型字符或封闭字符必须立即之前和/或之后的文本，没有干预空格或任何类型的字符。</span><span class="sxs-lookup"><span data-stu-id="ab5f6-117">A type character or enclosing characters must immediately precede and/or follow the literal, with no intervening space or characters of any kind.</span></span>  
  
 <span data-ttu-id="ab5f6-118">若要使前面的示例工作，你可以将附加`D`键入文本，使其表示为字符`Decimal`:</span><span class="sxs-lookup"><span data-stu-id="ab5f6-118">To make the previous example work, you can append the `D` type character to the literal, which causes it to be represented as a `Decimal`:</span></span>  
  
 [!code-vb[VbVbalrConstants#2](../../../../visual-basic/programming-guide/language-features/constants-enums/codesnippet/VisualBasic/constant-and-literal-data-types_2.vb)]  
  
 <span data-ttu-id="ab5f6-119">下面的示例演示如何正确使用类型字符和封闭字符：</span><span class="sxs-lookup"><span data-stu-id="ab5f6-119">The following example demonstrates correct usage of type characters and enclosing characters:</span></span>  
  
 [!code-vb[VbVbalrConstants#3](../../../../visual-basic/programming-guide/language-features/constants-enums/codesnippet/VisualBasic/constant-and-literal-data-types_3.vb)]  
  
 <span data-ttu-id="ab5f6-120">如下表所示的封闭字符和 Visual Basic 中可用的类型字符。</span><span class="sxs-lookup"><span data-stu-id="ab5f6-120">The following table shows the enclosing characters and type characters available in Visual Basic.</span></span>  
  
|<span data-ttu-id="ab5f6-121">数据类型</span><span class="sxs-lookup"><span data-stu-id="ab5f6-121">Data type</span></span>|<span data-ttu-id="ab5f6-122">封闭字符</span><span class="sxs-lookup"><span data-stu-id="ab5f6-122">Enclosing character</span></span>|<span data-ttu-id="ab5f6-123">追加的类型字符</span><span class="sxs-lookup"><span data-stu-id="ab5f6-123">Appended type character</span></span>|  
|---|---|---|  
|`Boolean`|<span data-ttu-id="ab5f6-124">(无)</span><span class="sxs-lookup"><span data-stu-id="ab5f6-124">(none)</span></span>|<span data-ttu-id="ab5f6-125">(无)</span><span class="sxs-lookup"><span data-stu-id="ab5f6-125">(none)</span></span>|  
|`Byte`|<span data-ttu-id="ab5f6-126">(无)</span><span class="sxs-lookup"><span data-stu-id="ab5f6-126">(none)</span></span>|<span data-ttu-id="ab5f6-127">(无)</span><span class="sxs-lookup"><span data-stu-id="ab5f6-127">(none)</span></span>|  
|`Char`|<span data-ttu-id="ab5f6-128">"</span><span class="sxs-lookup"><span data-stu-id="ab5f6-128">"</span></span>|<span data-ttu-id="ab5f6-129">C</span><span class="sxs-lookup"><span data-stu-id="ab5f6-129">C</span></span>|  
|`Date`|#|<span data-ttu-id="ab5f6-130">(无)</span><span class="sxs-lookup"><span data-stu-id="ab5f6-130">(none)</span></span>|  
|`Decimal`|<span data-ttu-id="ab5f6-131">(无)</span><span class="sxs-lookup"><span data-stu-id="ab5f6-131">(none)</span></span>|<span data-ttu-id="ab5f6-132">D 或 @</span><span class="sxs-lookup"><span data-stu-id="ab5f6-132">D or @</span></span>|  
|`Double`|<span data-ttu-id="ab5f6-133">(无)</span><span class="sxs-lookup"><span data-stu-id="ab5f6-133">(none)</span></span>|<span data-ttu-id="ab5f6-134">R 或 #</span><span class="sxs-lookup"><span data-stu-id="ab5f6-134">R or #</span></span>|  
|`Integer`|<span data-ttu-id="ab5f6-135">(无)</span><span class="sxs-lookup"><span data-stu-id="ab5f6-135">(none)</span></span>|<span data-ttu-id="ab5f6-136">I 或 %</span><span class="sxs-lookup"><span data-stu-id="ab5f6-136">I or %</span></span>|  
|`Long`|<span data-ttu-id="ab5f6-137">(无)</span><span class="sxs-lookup"><span data-stu-id="ab5f6-137">(none)</span></span>|<span data-ttu-id="ab5f6-138">L 或 （& a)</span><span class="sxs-lookup"><span data-stu-id="ab5f6-138">L or &</span></span>|  
|`Short`|<span data-ttu-id="ab5f6-139">(无)</span><span class="sxs-lookup"><span data-stu-id="ab5f6-139">(none)</span></span>|<span data-ttu-id="ab5f6-140">S</span><span class="sxs-lookup"><span data-stu-id="ab5f6-140">S</span></span>|  
|`Single`|<span data-ttu-id="ab5f6-141">(无)</span><span class="sxs-lookup"><span data-stu-id="ab5f6-141">(none)</span></span>|<span data-ttu-id="ab5f6-142">F 或 ！</span><span class="sxs-lookup"><span data-stu-id="ab5f6-142">F or !</span></span>|  
|`String`|<span data-ttu-id="ab5f6-143">"</span><span class="sxs-lookup"><span data-stu-id="ab5f6-143">"</span></span>|<span data-ttu-id="ab5f6-144">(无)</span><span class="sxs-lookup"><span data-stu-id="ab5f6-144">(none)</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ab5f6-145">请参阅</span><span class="sxs-lookup"><span data-stu-id="ab5f6-145">See Also</span></span>  
 [<span data-ttu-id="ab5f6-146">用户定义的常量</span><span class="sxs-lookup"><span data-stu-id="ab5f6-146">User-Defined Constants</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/user-defined-constants.md)  
 [<span data-ttu-id="ab5f6-147">如何：声明常量</span><span class="sxs-lookup"><span data-stu-id="ab5f6-147">How to: Declare A Constant</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-a-constant.md)  
 [<span data-ttu-id="ab5f6-148">常量概述</span><span class="sxs-lookup"><span data-stu-id="ab5f6-148">Constants Overview</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/constants-overview.md)  
 [<span data-ttu-id="ab5f6-149">Option Strict 语句</span><span class="sxs-lookup"><span data-stu-id="ab5f6-149">Option Strict Statement</span></span>](../../../../visual-basic/language-reference/statements/option-strict-statement.md)  
 [<span data-ttu-id="ab5f6-150">Option Explicit 语句</span><span class="sxs-lookup"><span data-stu-id="ab5f6-150">Option Explicit Statement</span></span>](../../../../visual-basic/language-reference/statements/option-explicit-statement.md)  
 [<span data-ttu-id="ab5f6-151">枚举概述</span><span class="sxs-lookup"><span data-stu-id="ab5f6-151">Enumerations Overview</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-overview.md)  
 [<span data-ttu-id="ab5f6-152">如何： 声明枚举</span><span class="sxs-lookup"><span data-stu-id="ab5f6-152">How to: Declare an Enumeration</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-enumerations.md)  
 [<span data-ttu-id="ab5f6-153">枚举和名称限定</span><span class="sxs-lookup"><span data-stu-id="ab5f6-153">Enumerations and Name Qualification</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md)  
 [<span data-ttu-id="ab5f6-154">数据类型</span><span class="sxs-lookup"><span data-stu-id="ab5f6-154">Data Types</span></span>](../../../../visual-basic/language-reference/data-types/data-type-summary.md)  
 [<span data-ttu-id="ab5f6-155">常量和枚举</span><span class="sxs-lookup"><span data-stu-id="ab5f6-155">Constants and Enumerations</span></span>](../../../../visual-basic/language-reference/constants-and-enumerations.md)
