---
title: "如何︰ 调用运算符过程 (Visual Basic 中) |Microsoft 文档"
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
- operator procedures, calling
- procedures, operator
- procedure calls, operator overloading
- syntax, Operator procedures
- operators [Visual Basic], overloading
- return values, Operator procedures
- overloaded operators, calling
- operator overloading
ms.assetid: 0dce42cc-f0b0-4c14-9f62-018b21f33497
caps.latest.revision: 16
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
ms.openlocfilehash: cd85a14a6f5534e90497268134f4b2b0cc292249
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017

---
# <a name="how-to-call-an-operator-procedure-visual-basic"></a><span data-ttu-id="7c5bd-102">如何：调用运算符过程 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7c5bd-102">How to: Call an Operator Procedure (Visual Basic)</span></span>
<span data-ttu-id="7c5bd-103">通过在表达式中使用的运算符符号调用运算符过程。</span><span class="sxs-lookup"><span data-stu-id="7c5bd-103">You call an operator procedure by using the operator symbol in an expression.</span></span> <span data-ttu-id="7c5bd-104">对于转换运算符，则调用[CType 函数](../../../../visual-basic/language-reference/functions/ctype-function.md)将值从一种数据类型转换到另一个。</span><span class="sxs-lookup"><span data-stu-id="7c5bd-104">In the case of a conversion operator, you call the [CType Function](../../../../visual-basic/language-reference/functions/ctype-function.md) to convert a value from one data type to another.</span></span>  
  
 <span data-ttu-id="7c5bd-105">不显式调用运算符过程。</span><span class="sxs-lookup"><span data-stu-id="7c5bd-105">You do not call operator procedures explicitly.</span></span> <span data-ttu-id="7c5bd-106">只需使用该运算符或`CType`函数，在赋值语句或表达式，通常使用的运算符相同的方式。</span><span class="sxs-lookup"><span data-stu-id="7c5bd-106">You just use the operator, or the `CType` function, in an assignment statement or an expression, the same way you ordinarily use an operator.</span></span> [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]<span data-ttu-id="7c5bd-107">在调用运算符过程。</span><span class="sxs-lookup"><span data-stu-id="7c5bd-107"> makes the call to the operator procedure.</span></span>  
  
 <span data-ttu-id="7c5bd-108">也称为上类或结构定义一个运算符*重载*运算符。</span><span class="sxs-lookup"><span data-stu-id="7c5bd-108">Defining an operator on a class or structure is also called *overloading* the operator.</span></span>  
  
### <a name="to-call-an-operator-procedure"></a><span data-ttu-id="7c5bd-109">若要调用运算符过程</span><span class="sxs-lookup"><span data-stu-id="7c5bd-109">To call an operator procedure</span></span>  
  
1.  <span data-ttu-id="7c5bd-110">以正常方式在表达式中使用运算符符号。</span><span class="sxs-lookup"><span data-stu-id="7c5bd-110">Use the operator symbol in an expression in the ordinary way.</span></span>  
  
2.  <span data-ttu-id="7c5bd-111">请确保操作数的数据类型是适合于该运算符，且按正确的顺序。</span><span class="sxs-lookup"><span data-stu-id="7c5bd-111">Be sure the data types of the operands are appropriate for the operator, and in the correct order.</span></span>  
  
3.  <span data-ttu-id="7c5bd-112">运算符可按预期方式的表达式值发挥作用。</span><span class="sxs-lookup"><span data-stu-id="7c5bd-112">The operator contributes to the value of the expression as expected.</span></span>  
  
### <a name="to-call-a-conversion-operator-procedure"></a><span data-ttu-id="7c5bd-113">若要调用的转换运算符过程</span><span class="sxs-lookup"><span data-stu-id="7c5bd-113">To call a conversion operator procedure</span></span>  
  
1.  <span data-ttu-id="7c5bd-114">使用`CType`在表达式内。</span><span class="sxs-lookup"><span data-stu-id="7c5bd-114">Use `CType` inside an expression.</span></span>  
  
2.  <span data-ttu-id="7c5bd-115">请确保操作数的数据类型进行转换，并以正确的顺序。</span><span class="sxs-lookup"><span data-stu-id="7c5bd-115">Be sure the data types of the operands are appropriate for the conversion, and in the correct order.</span></span>  
  
3.  <span data-ttu-id="7c5bd-116">`CType`调用转换运算符过程并返回转换后的值。</span><span class="sxs-lookup"><span data-stu-id="7c5bd-116">`CType` calls the conversion operator procedure and returns the converted value.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7c5bd-117">示例</span><span class="sxs-lookup"><span data-stu-id="7c5bd-117">Example</span></span>  
 <span data-ttu-id="7c5bd-118">下面的示例创建两个<xref:System.TimeSpan>结构，并将它们相加，并将结果存储在第三个<xref:System.TimeSpan>结构。</xref:System.TimeSpan> </xref:System.TimeSpan></span><span class="sxs-lookup"><span data-stu-id="7c5bd-118">The following example creates two <xref:System.TimeSpan> structures, adds them together, and stores the result in a third <xref:System.TimeSpan> structure.</span></span> <span data-ttu-id="7c5bd-119"><xref:System.TimeSpan>结构定义运算符过程来重载了几个标准运算符。</xref:System.TimeSpan></span><span class="sxs-lookup"><span data-stu-id="7c5bd-119">The <xref:System.TimeSpan> structure defines operator procedures to overload several standard operators.</span></span>  
  
 <span data-ttu-id="7c5bd-120">[!code-vb[VbVbcnProcedures #&29;](./codesnippet/VisualBasic/how-to-call-an-operator-procedure_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="7c5bd-120">[!code-vb[VbVbcnProcedures#29](./codesnippet/VisualBasic/how-to-call-an-operator-procedure_1.vb)]</span></span>  
  
 <span data-ttu-id="7c5bd-121">因为<xref:System.TimeSpan>重载标准`+`运算符，则在计算的值前面的示例调用运算符过程`combinedSpan`。</xref:System.TimeSpan></span><span class="sxs-lookup"><span data-stu-id="7c5bd-121">Because <xref:System.TimeSpan> overloads the standard `+` operator, the previous example calls an operator procedure when it calculates the value of `combinedSpan`.</span></span>  
  
 <span data-ttu-id="7c5bd-122">调用转换运算符过程的示例，请参阅[如何︰ 使用此类定义运算符的类](./how-to-use-a-class-that-defines-operators.md)。</span><span class="sxs-lookup"><span data-stu-id="7c5bd-122">For an example of calling a conversation operator procedure, see [How to: Use a Class that Defines Operators](./how-to-use-a-class-that-defines-operators.md).</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="7c5bd-123">编译代码</span><span class="sxs-lookup"><span data-stu-id="7c5bd-123">Compiling the Code</span></span>  
 <span data-ttu-id="7c5bd-124">请确保类或结构正在使用定义你想要使用的运算符。</span><span class="sxs-lookup"><span data-stu-id="7c5bd-124">Be sure the class or structure you are using defines the operator you want to use.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7c5bd-125">请参见</span><span class="sxs-lookup"><span data-stu-id="7c5bd-125">See Also</span></span>  
 <span data-ttu-id="7c5bd-126">[运算符过程](./operator-procedures.md) </span><span class="sxs-lookup"><span data-stu-id="7c5bd-126">[Operator Procedures](./operator-procedures.md) </span></span>  
<span data-ttu-id="7c5bd-127"> [如何︰ 定义运算符](./how-to-define-an-operator.md) </span><span class="sxs-lookup"><span data-stu-id="7c5bd-127"> [How to: Define an Operator](./how-to-define-an-operator.md) </span></span>  
<span data-ttu-id="7c5bd-128"> [如何︰ 定义转换运算符](./how-to-define-a-conversion-operator.md) </span><span class="sxs-lookup"><span data-stu-id="7c5bd-128"> [How to: Define a Conversion Operator](./how-to-define-a-conversion-operator.md) </span></span>  
<span data-ttu-id="7c5bd-129"> [Operator 语句](../../../../visual-basic/language-reference/statements/operator-statement.md) </span><span class="sxs-lookup"><span data-stu-id="7c5bd-129"> [Operator Statement](../../../../visual-basic/language-reference/statements/operator-statement.md) </span></span>  
<span data-ttu-id="7c5bd-130"> [扩大转换](../../../../visual-basic/language-reference/modifiers/widening.md) </span><span class="sxs-lookup"><span data-stu-id="7c5bd-130"> [Widening](../../../../visual-basic/language-reference/modifiers/widening.md) </span></span>  
<span data-ttu-id="7c5bd-131"> [收缩转换](../../../../visual-basic/language-reference/modifiers/narrowing.md) </span><span class="sxs-lookup"><span data-stu-id="7c5bd-131"> [Narrowing](../../../../visual-basic/language-reference/modifiers/narrowing.md) </span></span>  
<span data-ttu-id="7c5bd-132"> [Structure 语句](../../../../visual-basic/language-reference/statements/structure-statement.md) </span><span class="sxs-lookup"><span data-stu-id="7c5bd-132"> [Structure Statement](../../../../visual-basic/language-reference/statements/structure-statement.md) </span></span>  
<span data-ttu-id="7c5bd-133"> [如何︰ 声明结构](../../../../visual-basic/programming-guide/language-features/data-types/how-to-declare-a-structure.md) </span><span class="sxs-lookup"><span data-stu-id="7c5bd-133"> [How to: Declare a Structure](../../../../visual-basic/programming-guide/language-features/data-types/how-to-declare-a-structure.md) </span></span>  
<span data-ttu-id="7c5bd-134"> [隐式和显式转换](../../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md) </span><span class="sxs-lookup"><span data-stu-id="7c5bd-134"> [Implicit and Explicit Conversions](../../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md) </span></span>  
<span data-ttu-id="7c5bd-135"> [扩大转换和收缩转换](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)</span><span class="sxs-lookup"><span data-stu-id="7c5bd-135"> [Widening and Narrowing Conversions](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)</span></span>
