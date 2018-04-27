---
title: 如何：调用运算符过程 (Visual Basic)
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- operator procedures [Visual Basic], calling
- procedures [Visual Basic], operator
- procedure calls [Visual Basic], operator overloading
- syntax [Visual Basic], Operator procedures
- operators [Visual Basic], overloading
- return values [Visual Basic], Operator procedures
- overloaded operators [Visual Basic], calling
- operator overloading
ms.assetid: 0dce42cc-f0b0-4c14-9f62-018b21f33497
caps.latest.revision: 16
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 21545f2488bfabd0abc9c6e316d21bbc4d5aeb91
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-call-an-operator-procedure-visual-basic"></a><span data-ttu-id="1bd4c-102">如何：调用运算符过程 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1bd4c-102">How to: Call an Operator Procedure (Visual Basic)</span></span>
<span data-ttu-id="1bd4c-103">通过在表达式中使用运算符调用运算符过程。</span><span class="sxs-lookup"><span data-stu-id="1bd4c-103">You call an operator procedure by using the operator symbol in an expression.</span></span> <span data-ttu-id="1bd4c-104">对于转换运算符，你调用[CType 函数](../../../../visual-basic/language-reference/functions/ctype-function.md)将值从一种数据类型转换为另一个。</span><span class="sxs-lookup"><span data-stu-id="1bd4c-104">In the case of a conversion operator, you call the [CType Function](../../../../visual-basic/language-reference/functions/ctype-function.md) to convert a value from one data type to another.</span></span>  
  
 <span data-ttu-id="1bd4c-105">不显式调用运算符过程。</span><span class="sxs-lookup"><span data-stu-id="1bd4c-105">You do not call operator procedures explicitly.</span></span> <span data-ttu-id="1bd4c-106">只需使用运算符，或`CType`函数，在赋值语句或表达式，通常使用运算符相同的方式。</span><span class="sxs-lookup"><span data-stu-id="1bd4c-106">You just use the operator, or the `CType` function, in an assignment statement or an expression, the same way you ordinarily use an operator.</span></span> <span data-ttu-id="1bd4c-107">Visual Basic 进行到运算符过程的调用。</span><span class="sxs-lookup"><span data-stu-id="1bd4c-107">Visual Basic makes the call to the operator procedure.</span></span>  
  
 <span data-ttu-id="1bd4c-108">在类或结构上定义一个运算符也称为*重载*运算符。</span><span class="sxs-lookup"><span data-stu-id="1bd4c-108">Defining an operator on a class or structure is also called *overloading* the operator.</span></span>  
  
### <a name="to-call-an-operator-procedure"></a><span data-ttu-id="1bd4c-109">若要调用运算符过程</span><span class="sxs-lookup"><span data-stu-id="1bd4c-109">To call an operator procedure</span></span>  
  
1.  <span data-ttu-id="1bd4c-110">运算符的表达式中使用普通的方式。</span><span class="sxs-lookup"><span data-stu-id="1bd4c-110">Use the operator symbol in an expression in the ordinary way.</span></span>  
  
2.  <span data-ttu-id="1bd4c-111">请确保操作数的数据类型是适合于运算符，且按正确的顺序。</span><span class="sxs-lookup"><span data-stu-id="1bd4c-111">Be sure the data types of the operands are appropriate for the operator, and in the correct order.</span></span>  
  
3.  <span data-ttu-id="1bd4c-112">按预期方式，运算符将分配给表达式的值。</span><span class="sxs-lookup"><span data-stu-id="1bd4c-112">The operator contributes to the value of the expression as expected.</span></span>  
  
### <a name="to-call-a-conversion-operator-procedure"></a><span data-ttu-id="1bd4c-113">若要调用转换运算符过程</span><span class="sxs-lookup"><span data-stu-id="1bd4c-113">To call a conversion operator procedure</span></span>  
  
1.  <span data-ttu-id="1bd4c-114">使用`CType`在表达式内部。</span><span class="sxs-lookup"><span data-stu-id="1bd4c-114">Use `CType` inside an expression.</span></span>  
  
2.  <span data-ttu-id="1bd4c-115">请确保数据类型的操作数不适合进行转换，且正确顺序。</span><span class="sxs-lookup"><span data-stu-id="1bd4c-115">Be sure the data types of the operands are appropriate for the conversion, and in the correct order.</span></span>  
  
3.  <span data-ttu-id="1bd4c-116">`CType` 调用转换运算符过程并返回转换后的值。</span><span class="sxs-lookup"><span data-stu-id="1bd4c-116">`CType` calls the conversion operator procedure and returns the converted value.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1bd4c-117">示例</span><span class="sxs-lookup"><span data-stu-id="1bd4c-117">Example</span></span>  
 <span data-ttu-id="1bd4c-118">下面的示例创建两个<xref:System.TimeSpan>结构，并将它们相加，并将结果存储在第三个<xref:System.TimeSpan>结构。</span><span class="sxs-lookup"><span data-stu-id="1bd4c-118">The following example creates two <xref:System.TimeSpan> structures, adds them together, and stores the result in a third <xref:System.TimeSpan> structure.</span></span> <span data-ttu-id="1bd4c-119"><xref:System.TimeSpan>结构定义运算符过程重载了几个标准运算符。</span><span class="sxs-lookup"><span data-stu-id="1bd4c-119">The <xref:System.TimeSpan> structure defines operator procedures to overload several standard operators.</span></span>  
  
 [!code-vb[VbVbcnProcedures#29](./codesnippet/VisualBasic/how-to-call-an-operator-procedure_1.vb)]  
  
 <span data-ttu-id="1bd4c-120">因为<xref:System.TimeSpan>重载标准`+`运算符，则在计算的值前面的示例调用运算符过程`combinedSpan`。</span><span class="sxs-lookup"><span data-stu-id="1bd4c-120">Because <xref:System.TimeSpan> overloads the standard `+` operator, the previous example calls an operator procedure when it calculates the value of `combinedSpan`.</span></span>  
  
 <span data-ttu-id="1bd4c-121">调用会话运算符过程的示例，请参阅[如何： 使用此类定义运算符的类](./how-to-use-a-class-that-defines-operators.md)。</span><span class="sxs-lookup"><span data-stu-id="1bd4c-121">For an example of calling a conversation operator procedure, see [How to: Use a Class that Defines Operators](./how-to-use-a-class-that-defines-operators.md).</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="1bd4c-122">编译代码</span><span class="sxs-lookup"><span data-stu-id="1bd4c-122">Compiling the Code</span></span>  
 <span data-ttu-id="1bd4c-123">请确保类或结构将定义你想要使用的运算符。</span><span class="sxs-lookup"><span data-stu-id="1bd4c-123">Be sure the class or structure you are using defines the operator you want to use.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1bd4c-124">请参阅</span><span class="sxs-lookup"><span data-stu-id="1bd4c-124">See Also</span></span>  
 [<span data-ttu-id="1bd4c-125">运算符过程</span><span class="sxs-lookup"><span data-stu-id="1bd4c-125">Operator Procedures</span></span>](./operator-procedures.md)  
 [<span data-ttu-id="1bd4c-126">如何：定义运算符</span><span class="sxs-lookup"><span data-stu-id="1bd4c-126">How to: Define an Operator</span></span>](./how-to-define-an-operator.md)  
 [<span data-ttu-id="1bd4c-127">如何：定义转换运算符</span><span class="sxs-lookup"><span data-stu-id="1bd4c-127">How to: Define a Conversion Operator</span></span>](./how-to-define-a-conversion-operator.md)  
 [<span data-ttu-id="1bd4c-128">Operator Statement</span><span class="sxs-lookup"><span data-stu-id="1bd4c-128">Operator Statement</span></span>](../../../../visual-basic/language-reference/statements/operator-statement.md)  
 [<span data-ttu-id="1bd4c-129">Widening</span><span class="sxs-lookup"><span data-stu-id="1bd4c-129">Widening</span></span>](../../../../visual-basic/language-reference/modifiers/widening.md)  
 [<span data-ttu-id="1bd4c-130">Narrowing</span><span class="sxs-lookup"><span data-stu-id="1bd4c-130">Narrowing</span></span>](../../../../visual-basic/language-reference/modifiers/narrowing.md)  
 [<span data-ttu-id="1bd4c-131">Structure 语句</span><span class="sxs-lookup"><span data-stu-id="1bd4c-131">Structure Statement</span></span>](../../../../visual-basic/language-reference/statements/structure-statement.md)  
 [<span data-ttu-id="1bd4c-132">如何：声明结构</span><span class="sxs-lookup"><span data-stu-id="1bd4c-132">How to: Declare a Structure</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/how-to-declare-a-structure.md)  
 [<span data-ttu-id="1bd4c-133">隐式转换和显式转换</span><span class="sxs-lookup"><span data-stu-id="1bd4c-133">Implicit and Explicit Conversions</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)  
 [<span data-ttu-id="1bd4c-134">扩大转换和收缩转换</span><span class="sxs-lookup"><span data-stu-id="1bd4c-134">Widening and Narrowing Conversions</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
