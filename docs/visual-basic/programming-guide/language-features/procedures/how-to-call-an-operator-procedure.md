---
title: 如何：调用运算符过程 (Visual Basic)
ms.date: 07/20/2015
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
ms.openlocfilehash: 46614ad43e7be72c8396f47ba7f5d02185f62827
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/02/2019
ms.locfileid: "58837086"
---
# <a name="how-to-call-an-operator-procedure-visual-basic"></a><span data-ttu-id="40508-102">如何：调用运算符过程 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="40508-102">How to: Call an Operator Procedure (Visual Basic)</span></span>
<span data-ttu-id="40508-103">通过在表达式中使用的运算符符号调用运算符过程。</span><span class="sxs-lookup"><span data-stu-id="40508-103">You call an operator procedure by using the operator symbol in an expression.</span></span> <span data-ttu-id="40508-104">转换运算符，如果您调用[CType 函数](../../../../visual-basic/language-reference/functions/ctype-function.md)将值从一种数据类型转换为另一个。</span><span class="sxs-lookup"><span data-stu-id="40508-104">In the case of a conversion operator, you call the [CType Function](../../../../visual-basic/language-reference/functions/ctype-function.md) to convert a value from one data type to another.</span></span>  
  
 <span data-ttu-id="40508-105">不显式调用运算符过程。</span><span class="sxs-lookup"><span data-stu-id="40508-105">You do not call operator procedures explicitly.</span></span> <span data-ttu-id="40508-106">只需使用运算符，或`CType`函数，在赋值语句或表达式，通常使用运算符的相同方式。</span><span class="sxs-lookup"><span data-stu-id="40508-106">You just use the operator, or the `CType` function, in an assignment statement or an expression, the same way you ordinarily use an operator.</span></span> <span data-ttu-id="40508-107">Visual Basic 进行到运算符过程调用。</span><span class="sxs-lookup"><span data-stu-id="40508-107">Visual Basic makes the call to the operator procedure.</span></span>  
  
 <span data-ttu-id="40508-108">在类或结构上定义一个运算符也称为*重载*运算符。</span><span class="sxs-lookup"><span data-stu-id="40508-108">Defining an operator on a class or structure is also called *overloading* the operator.</span></span>  
  
### <a name="to-call-an-operator-procedure"></a><span data-ttu-id="40508-109">若要调用运算符过程</span><span class="sxs-lookup"><span data-stu-id="40508-109">To call an operator procedure</span></span>  
  
1.  <span data-ttu-id="40508-110">以普通方式在表达式中使用的运算符符号。</span><span class="sxs-lookup"><span data-stu-id="40508-110">Use the operator symbol in an expression in the ordinary way.</span></span>  
  
2.  <span data-ttu-id="40508-111">请确保操作数的数据类型是相应的运算符和正确的顺序。</span><span class="sxs-lookup"><span data-stu-id="40508-111">Be sure the data types of the operands are appropriate for the operator, and in the correct order.</span></span>  
  
3.  <span data-ttu-id="40508-112">运算符按预期方式影响表达式的值。</span><span class="sxs-lookup"><span data-stu-id="40508-112">The operator contributes to the value of the expression as expected.</span></span>  
  
### <a name="to-call-a-conversion-operator-procedure"></a><span data-ttu-id="40508-113">若要调用的转换运算符过程</span><span class="sxs-lookup"><span data-stu-id="40508-113">To call a conversion operator procedure</span></span>  
  
1.  <span data-ttu-id="40508-114">使用`CType`在表达式中。</span><span class="sxs-lookup"><span data-stu-id="40508-114">Use `CType` inside an expression.</span></span>  
  
2.  <span data-ttu-id="40508-115">为确保操作数数据类型进行转换，并按正确的顺序。</span><span class="sxs-lookup"><span data-stu-id="40508-115">Be sure the data types of the operands are appropriate for the conversion, and in the correct order.</span></span>  
  
3.  <span data-ttu-id="40508-116">`CType` 调用转换运算符过程并返回转换后的值。</span><span class="sxs-lookup"><span data-stu-id="40508-116">`CType` calls the conversion operator procedure and returns the converted value.</span></span>  
  
## <a name="example"></a><span data-ttu-id="40508-117">示例</span><span class="sxs-lookup"><span data-stu-id="40508-117">Example</span></span>  
 <span data-ttu-id="40508-118">下面的示例创建两个<xref:System.TimeSpan>结构，并将它们相加，并将结果存储在第三个<xref:System.TimeSpan>结构。</span><span class="sxs-lookup"><span data-stu-id="40508-118">The following example creates two <xref:System.TimeSpan> structures, adds them together, and stores the result in a third <xref:System.TimeSpan> structure.</span></span> <span data-ttu-id="40508-119"><xref:System.TimeSpan>结构定义多个标准运算符重载的运算符过程。</span><span class="sxs-lookup"><span data-stu-id="40508-119">The <xref:System.TimeSpan> structure defines operator procedures to overload several standard operators.</span></span>  
  
 [!code-vb[VbVbcnProcedures#29](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#29)]  
  
 <span data-ttu-id="40508-120">因为<xref:System.TimeSpan>重载标准`+`运算符，则在计算的值前面的示例调用运算符过程`combinedSpan`。</span><span class="sxs-lookup"><span data-stu-id="40508-120">Because <xref:System.TimeSpan> overloads the standard `+` operator, the previous example calls an operator procedure when it calculates the value of `combinedSpan`.</span></span>  
  
 <span data-ttu-id="40508-121">调用会话运算符过程的示例，请参阅[如何：使用定义运算符的类](./how-to-use-a-class-that-defines-operators.md)。</span><span class="sxs-lookup"><span data-stu-id="40508-121">For an example of calling a conversation operator procedure, see [How to: Use a Class that Defines Operators](./how-to-use-a-class-that-defines-operators.md).</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="40508-122">编译代码</span><span class="sxs-lookup"><span data-stu-id="40508-122">Compiling the Code</span></span>  
 <span data-ttu-id="40508-123">请确保类或结构使用定义你想要使用的运算符。</span><span class="sxs-lookup"><span data-stu-id="40508-123">Be sure the class or structure you are using defines the operator you want to use.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="40508-124">请参阅</span><span class="sxs-lookup"><span data-stu-id="40508-124">See also</span></span>

- [<span data-ttu-id="40508-125">运算符过程</span><span class="sxs-lookup"><span data-stu-id="40508-125">Operator Procedures</span></span>](./operator-procedures.md)
- [<span data-ttu-id="40508-126">如何：定义运算符</span><span class="sxs-lookup"><span data-stu-id="40508-126">How to: Define an Operator</span></span>](./how-to-define-an-operator.md)
- [<span data-ttu-id="40508-127">如何：定义转换运算符</span><span class="sxs-lookup"><span data-stu-id="40508-127">How to: Define a Conversion Operator</span></span>](./how-to-define-a-conversion-operator.md)
- [<span data-ttu-id="40508-128">Operator Statement</span><span class="sxs-lookup"><span data-stu-id="40508-128">Operator Statement</span></span>](../../../../visual-basic/language-reference/statements/operator-statement.md)
- [<span data-ttu-id="40508-129">Widening</span><span class="sxs-lookup"><span data-stu-id="40508-129">Widening</span></span>](../../../../visual-basic/language-reference/modifiers/widening.md)
- [<span data-ttu-id="40508-130">Narrowing</span><span class="sxs-lookup"><span data-stu-id="40508-130">Narrowing</span></span>](../../../../visual-basic/language-reference/modifiers/narrowing.md)
- [<span data-ttu-id="40508-131">Structure 语句</span><span class="sxs-lookup"><span data-stu-id="40508-131">Structure Statement</span></span>](../../../../visual-basic/language-reference/statements/structure-statement.md)
- [<span data-ttu-id="40508-132">如何：声明结构</span><span class="sxs-lookup"><span data-stu-id="40508-132">How to: Declare a Structure</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/how-to-declare-a-structure.md)
- [<span data-ttu-id="40508-133">隐式转换和显式转换</span><span class="sxs-lookup"><span data-stu-id="40508-133">Implicit and Explicit Conversions</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)
- [<span data-ttu-id="40508-134">扩大转换和收缩转换</span><span class="sxs-lookup"><span data-stu-id="40508-134">Widening and Narrowing Conversions</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
