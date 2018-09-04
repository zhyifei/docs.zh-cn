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
ms.openlocfilehash: 1d030f8058cd497212c20bca8f064f2bedc99fce
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/04/2018
ms.locfileid: "43507812"
---
# <a name="constant-and-literal-data-types-visual-basic"></a><span data-ttu-id="c7ecf-102">常量和 Literal 数据类型 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c7ecf-102">Constant and Literal Data Types (Visual Basic)</span></span>
<span data-ttu-id="c7ecf-103">文本是一个值，表示为本身而不是变量的值或表达式，如数字 3 或字符串"Hello"的结果。</span><span class="sxs-lookup"><span data-stu-id="c7ecf-103">A literal is a value that is expressed as itself rather than as a variable's value or the result of an expression, such as the number 3 or the string "Hello".</span></span> <span data-ttu-id="c7ecf-104">常量是有意义的名称，它接受文本的位置，并将保留在整个程序，而不是变量，其值可能会更改此相同的值。</span><span class="sxs-lookup"><span data-stu-id="c7ecf-104">A constant is a meaningful name that takes the place of a literal and retains this same value throughout the program, as opposed to a variable, whose value may change.</span></span>  
  
 <span data-ttu-id="c7ecf-105">当[Option Infer](../../../../visual-basic/language-reference/statements/option-infer-statement.md)是`Off`并[Option Strict](../../../../visual-basic/language-reference/statements/option-strict-statement.md)是`On`，您必须显式声明的所有常量具有数据类型。</span><span class="sxs-lookup"><span data-stu-id="c7ecf-105">When [Option Infer](../../../../visual-basic/language-reference/statements/option-infer-statement.md) is `Off` and [Option Strict](../../../../visual-basic/language-reference/statements/option-strict-statement.md) is `On`, you must declare all constants explicitly with a data type.</span></span> <span data-ttu-id="c7ecf-106">在下面的示例中的数据类型`MyByte`显式声明数据类型为`Byte`:</span><span class="sxs-lookup"><span data-stu-id="c7ecf-106">In the following example, the data type of `MyByte` is explicitly declared as data type `Byte`:</span></span>  
  
 [!code-vb[VbVbalrConstants#1](../../../../visual-basic/programming-guide/language-features/constants-enums/codesnippet/VisualBasic/constant-and-literal-data-types_1.vb)]  
  
 <span data-ttu-id="c7ecf-107">当`Option Infer`是`On`或`Option Strict`是`Off`，你可以声明变量，而无需指定数据类型为`As`子句。</span><span class="sxs-lookup"><span data-stu-id="c7ecf-107">When `Option Infer` is `On` or `Option Strict` is `Off`, you can declare a constant without specifying a data type with an `As` clause.</span></span> <span data-ttu-id="c7ecf-108">编译器确定的常量表达式的类型的类型。</span><span class="sxs-lookup"><span data-stu-id="c7ecf-108">The compiler determines the type of the constant from the type of the expression.</span></span> <span data-ttu-id="c7ecf-109">默认情况下强制转换数字的整数文本`Integer`数据类型。</span><span class="sxs-lookup"><span data-stu-id="c7ecf-109">A numeric integer literal is cast by default to the `Integer` data type.</span></span> <span data-ttu-id="c7ecf-110">默认数据类型为浮点数`Double`，和关键字`True`并`False`指定`Boolean`常量。</span><span class="sxs-lookup"><span data-stu-id="c7ecf-110">The default data type for floating-point numbers is `Double`, and the keywords `True` and `False` specify a `Boolean` constant.</span></span>  
  
## <a name="literals-and-type-coercion"></a><span data-ttu-id="c7ecf-111">文本和类型强制转换</span><span class="sxs-lookup"><span data-stu-id="c7ecf-111">Literals and Type Coercion</span></span>  
 <span data-ttu-id="c7ecf-112">在某些情况下，你可能想要将文本强制为特定的数据类型;例如，如果将特别大的整数文字值分配到类型的变量的`Decimal`。</span><span class="sxs-lookup"><span data-stu-id="c7ecf-112">In some cases, you might want to force a literal to a particular data type; for example, when assigning a particularly large integral literal value to a variable of type `Decimal`.</span></span> <span data-ttu-id="c7ecf-113">下面的示例将生成错误：</span><span class="sxs-lookup"><span data-stu-id="c7ecf-113">The following example produces an error:</span></span>  
  
```  
Dim myDecimal as Decimal  
myDecimal = 100000000000000000000   ' This causes a compiler error.  
```  
  
 <span data-ttu-id="c7ecf-114">从文本表示形式会导致错误。</span><span class="sxs-lookup"><span data-stu-id="c7ecf-114">The error results from the representation of the literal.</span></span> <span data-ttu-id="c7ecf-115">`Decimal`数据类型可以保存值过大，但文本隐式表示为`Long`，哪些不能。</span><span class="sxs-lookup"><span data-stu-id="c7ecf-115">The `Decimal` data type can hold a value this large, but the literal is implicitly represented as a `Long`, which cannot.</span></span>  
  
 <span data-ttu-id="c7ecf-116">您可以强制转换为两种方法中的特定数据类型的文字： 通过将类型字符追加到它，或将其放在封闭字符。</span><span class="sxs-lookup"><span data-stu-id="c7ecf-116">You can coerce a literal to a particular data type in two ways: by appending a type character to it, or by placing it within enclosing characters.</span></span> <span data-ttu-id="c7ecf-117">类型字符或封闭字符必须立即之前和/或按照文本，不带任何干预空格或任何类型的字符。</span><span class="sxs-lookup"><span data-stu-id="c7ecf-117">A type character or enclosing characters must immediately precede and/or follow the literal, with no intervening space or characters of any kind.</span></span>  
  
 <span data-ttu-id="c7ecf-118">若要使上一个示例工作，您可以将附加`D`类型为文本，这会导致它无法表示为字符`Decimal`:</span><span class="sxs-lookup"><span data-stu-id="c7ecf-118">To make the previous example work, you can append the `D` type character to the literal, which causes it to be represented as a `Decimal`:</span></span>  
  
 [!code-vb[VbVbalrConstants#2](../../../../visual-basic/programming-guide/language-features/constants-enums/codesnippet/VisualBasic/constant-and-literal-data-types_2.vb)]  
  
 <span data-ttu-id="c7ecf-119">下面的示例演示如何正确使用类型字符和封闭字符：</span><span class="sxs-lookup"><span data-stu-id="c7ecf-119">The following example demonstrates correct usage of type characters and enclosing characters:</span></span>  
  
 [!code-vb[VbVbalrConstants#3](../../../../visual-basic/programming-guide/language-features/constants-enums/codesnippet/VisualBasic/constant-and-literal-data-types_3.vb)]  
  
 <span data-ttu-id="c7ecf-120">如下表所示的封闭字符和 Visual Basic 中可用的类型字符。</span><span class="sxs-lookup"><span data-stu-id="c7ecf-120">The following table shows the enclosing characters and type characters available in Visual Basic.</span></span>  
  
|<span data-ttu-id="c7ecf-121">数据类型</span><span class="sxs-lookup"><span data-stu-id="c7ecf-121">Data type</span></span>|<span data-ttu-id="c7ecf-122">封闭字符</span><span class="sxs-lookup"><span data-stu-id="c7ecf-122">Enclosing character</span></span>|<span data-ttu-id="c7ecf-123">追加的类型字符</span><span class="sxs-lookup"><span data-stu-id="c7ecf-123">Appended type character</span></span>|  
|---|---|---|  
|`Boolean`|<span data-ttu-id="c7ecf-124">(无)</span><span class="sxs-lookup"><span data-stu-id="c7ecf-124">(none)</span></span>|<span data-ttu-id="c7ecf-125">(无)</span><span class="sxs-lookup"><span data-stu-id="c7ecf-125">(none)</span></span>|  
|`Byte`|<span data-ttu-id="c7ecf-126">(无)</span><span class="sxs-lookup"><span data-stu-id="c7ecf-126">(none)</span></span>|<span data-ttu-id="c7ecf-127">(无)</span><span class="sxs-lookup"><span data-stu-id="c7ecf-127">(none)</span></span>|  
|`Char`|<span data-ttu-id="c7ecf-128">"</span><span class="sxs-lookup"><span data-stu-id="c7ecf-128">"</span></span>|<span data-ttu-id="c7ecf-129">C</span><span class="sxs-lookup"><span data-stu-id="c7ecf-129">C</span></span>|  
|`Date`|#|<span data-ttu-id="c7ecf-130">(无)</span><span class="sxs-lookup"><span data-stu-id="c7ecf-130">(none)</span></span>|  
|`Decimal`|<span data-ttu-id="c7ecf-131">(无)</span><span class="sxs-lookup"><span data-stu-id="c7ecf-131">(none)</span></span>|<span data-ttu-id="c7ecf-132">D 或使用 @</span><span class="sxs-lookup"><span data-stu-id="c7ecf-132">D or @</span></span>|  
|`Double`|<span data-ttu-id="c7ecf-133">(无)</span><span class="sxs-lookup"><span data-stu-id="c7ecf-133">(none)</span></span>|<span data-ttu-id="c7ecf-134">R 或 #</span><span class="sxs-lookup"><span data-stu-id="c7ecf-134">R or #</span></span>|  
|`Integer`|<span data-ttu-id="c7ecf-135">(无)</span><span class="sxs-lookup"><span data-stu-id="c7ecf-135">(none)</span></span>|<span data-ttu-id="c7ecf-136">I 或 %</span><span class="sxs-lookup"><span data-stu-id="c7ecf-136">I or %</span></span>|  
|`Long`|<span data-ttu-id="c7ecf-137">(无)</span><span class="sxs-lookup"><span data-stu-id="c7ecf-137">(none)</span></span>|<span data-ttu-id="c7ecf-138">L 或 （& a)</span><span class="sxs-lookup"><span data-stu-id="c7ecf-138">L or &</span></span>|  
|`Short`|<span data-ttu-id="c7ecf-139">(无)</span><span class="sxs-lookup"><span data-stu-id="c7ecf-139">(none)</span></span>|<span data-ttu-id="c7ecf-140">S</span><span class="sxs-lookup"><span data-stu-id="c7ecf-140">S</span></span>|  
|`Single`|<span data-ttu-id="c7ecf-141">(无)</span><span class="sxs-lookup"><span data-stu-id="c7ecf-141">(none)</span></span>|<span data-ttu-id="c7ecf-142">F 或 ！</span><span class="sxs-lookup"><span data-stu-id="c7ecf-142">F or !</span></span>|  
|`String`|<span data-ttu-id="c7ecf-143">"</span><span class="sxs-lookup"><span data-stu-id="c7ecf-143">"</span></span>|<span data-ttu-id="c7ecf-144">(无)</span><span class="sxs-lookup"><span data-stu-id="c7ecf-144">(none)</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c7ecf-145">请参阅</span><span class="sxs-lookup"><span data-stu-id="c7ecf-145">See Also</span></span>  
 [<span data-ttu-id="c7ecf-146">用户定义的常量</span><span class="sxs-lookup"><span data-stu-id="c7ecf-146">User-Defined Constants</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/user-defined-constants.md)  
 [<span data-ttu-id="c7ecf-147">如何：声明常量</span><span class="sxs-lookup"><span data-stu-id="c7ecf-147">How to: Declare A Constant</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-a-constant.md)  
 [<span data-ttu-id="c7ecf-148">常量概述</span><span class="sxs-lookup"><span data-stu-id="c7ecf-148">Constants Overview</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/constants-overview.md)  
 [<span data-ttu-id="c7ecf-149">Option Strict 语句</span><span class="sxs-lookup"><span data-stu-id="c7ecf-149">Option Strict Statement</span></span>](../../../../visual-basic/language-reference/statements/option-strict-statement.md)  
 [<span data-ttu-id="c7ecf-150">Option Explicit 语句</span><span class="sxs-lookup"><span data-stu-id="c7ecf-150">Option Explicit Statement</span></span>](../../../../visual-basic/language-reference/statements/option-explicit-statement.md)  
 [<span data-ttu-id="c7ecf-151">枚举概述</span><span class="sxs-lookup"><span data-stu-id="c7ecf-151">Enumerations Overview</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-overview.md)  
 [<span data-ttu-id="c7ecf-152">如何： 声明枚举</span><span class="sxs-lookup"><span data-stu-id="c7ecf-152">How to: Declare an Enumeration</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-enumerations.md)  
 [<span data-ttu-id="c7ecf-153">枚举和名称限定</span><span class="sxs-lookup"><span data-stu-id="c7ecf-153">Enumerations and Name Qualification</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md)  
 [<span data-ttu-id="c7ecf-154">数据类型</span><span class="sxs-lookup"><span data-stu-id="c7ecf-154">Data Types</span></span>](../../../../visual-basic/language-reference/data-types/index.md)  
 [<span data-ttu-id="c7ecf-155">常量和枚举</span><span class="sxs-lookup"><span data-stu-id="c7ecf-155">Constants and Enumerations</span></span>](../../../../visual-basic/language-reference/constants-and-enumerations.md)
