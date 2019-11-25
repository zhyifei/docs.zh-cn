---
title: 如何：使用定义运算符的类
ms.date: 07/20/2015
helpviewer_keywords:
- operator procedures [Visual Basic], calling
- procedures [Visual Basic], operator
- procedures [Visual Basic], calling
- examples [Visual Basic], CType
- syntax [Visual Basic], Operator procedures
- operators [Visual Basic], overloading
- return values [Visual Basic], Operator procedures
- operator overloading
ms.assetid: 7ccce94a-6ca0-47d1-9f3f-13385d34f5d5
ms.openlocfilehash: 9ec4b4c07910100dd02cc86e882b44aa7dbd2ced
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74346035"
---
# <a name="how-to-use-a-class-that-defines-operators-visual-basic"></a><span data-ttu-id="959a2-102">如何：使用定义运算符的类 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="959a2-102">How to: Use a Class that Defines Operators (Visual Basic)</span></span>
<span data-ttu-id="959a2-103">If you are using a class or structure that defines its own operators, you can access those operators from Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="959a2-103">If you are using a class or structure that defines its own operators, you can access those operators from Visual Basic.</span></span>  
  
 <span data-ttu-id="959a2-104">Defining an operator on a class or structure is also called *overloading* the operator.</span><span class="sxs-lookup"><span data-stu-id="959a2-104">Defining an operator on a class or structure is also called *overloading* the operator.</span></span>  
  
## <a name="example"></a><span data-ttu-id="959a2-105">示例</span><span class="sxs-lookup"><span data-stu-id="959a2-105">Example</span></span>  
 <span data-ttu-id="959a2-106">The following example accesses the SQL structure <xref:System.Data.SqlTypes.SqlString>, which defines the conversion operators ([CType Function](../../../../visual-basic/language-reference/functions/ctype-function.md)) in both directions between a SQL string and a Visual Basic string.</span><span class="sxs-lookup"><span data-stu-id="959a2-106">The following example accesses the SQL structure <xref:System.Data.SqlTypes.SqlString>, which defines the conversion operators ([CType Function](../../../../visual-basic/language-reference/functions/ctype-function.md)) in both directions between a SQL string and a Visual Basic string.</span></span> <span data-ttu-id="959a2-107">Use `CType(`*SQL string expression*, `String)` to convert a SQL string to a Visual Basic string, and `CType(`*Visual Basic string expression*, <xref:System.Data.SqlTypes.SqlString>`)` to convert in the other direction.</span><span class="sxs-lookup"><span data-stu-id="959a2-107">Use `CType(`*SQL string expression*, `String)` to convert a SQL string to a Visual Basic string, and `CType(`*Visual Basic string expression*, <xref:System.Data.SqlTypes.SqlString>`)` to convert in the other direction.</span></span>  
  
 [!code-vb[VbVbcnProcedures#30](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#30)]  
  
 [!code-vb[VbVbcnProcedures#31](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#31)]  
  
 <span data-ttu-id="959a2-108">The <xref:System.Data.SqlTypes.SqlString> structure defines a conversion operator ([CType Function](../../../../visual-basic/language-reference/functions/ctype-function.md)) from `String` to <xref:System.Data.SqlTypes.SqlString> and another from <xref:System.Data.SqlTypes.SqlString> to `String`.</span><span class="sxs-lookup"><span data-stu-id="959a2-108">The <xref:System.Data.SqlTypes.SqlString> structure defines a conversion operator ([CType Function](../../../../visual-basic/language-reference/functions/ctype-function.md)) from `String` to <xref:System.Data.SqlTypes.SqlString> and another from <xref:System.Data.SqlTypes.SqlString> to `String`.</span></span> <span data-ttu-id="959a2-109">The statement that assigns `title` to `jobTitle` makes use of the first operator, and the <xref:Microsoft.VisualBasic.Interaction.MsgBox%2A> function call uses the second.</span><span class="sxs-lookup"><span data-stu-id="959a2-109">The statement that assigns `title` to `jobTitle` makes use of the first operator, and the <xref:Microsoft.VisualBasic.Interaction.MsgBox%2A> function call uses the second.</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="959a2-110">编译代码</span><span class="sxs-lookup"><span data-stu-id="959a2-110">Compiling the Code</span></span>  
 <span data-ttu-id="959a2-111">Be sure the class or structure you are using defines the operator you want to use.</span><span class="sxs-lookup"><span data-stu-id="959a2-111">Be sure the class or structure you are using defines the operator you want to use.</span></span> <span data-ttu-id="959a2-112">Do not assume that the class or structure has defined every operator available for overloading.</span><span class="sxs-lookup"><span data-stu-id="959a2-112">Do not assume that the class or structure has defined every operator available for overloading.</span></span> <span data-ttu-id="959a2-113">For a list of available operators, see [Operator Statement](../../../../visual-basic/language-reference/statements/operator-statement.md).</span><span class="sxs-lookup"><span data-stu-id="959a2-113">For a list of available operators, see [Operator Statement](../../../../visual-basic/language-reference/statements/operator-statement.md).</span></span>  
  
 <span data-ttu-id="959a2-114">Include the appropriate `Imports` statement for the SQL string at the beginning of your source file (in this case <xref:System.Data.SqlTypes>).</span><span class="sxs-lookup"><span data-stu-id="959a2-114">Include the appropriate `Imports` statement for the SQL string at the beginning of your source file (in this case <xref:System.Data.SqlTypes>).</span></span>  
  
 <span data-ttu-id="959a2-115">Your project must have references to System.Data and System.XML.</span><span class="sxs-lookup"><span data-stu-id="959a2-115">Your project must have references to System.Data and System.XML.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="959a2-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="959a2-116">See also</span></span>

- [<span data-ttu-id="959a2-117">运算符过程</span><span class="sxs-lookup"><span data-stu-id="959a2-117">Operator Procedures</span></span>](./operator-procedures.md)
- [<span data-ttu-id="959a2-118">如何：定义运算符</span><span class="sxs-lookup"><span data-stu-id="959a2-118">How to: Define an Operator</span></span>](./how-to-define-an-operator.md)
- [<span data-ttu-id="959a2-119">如何：定义转换运算符</span><span class="sxs-lookup"><span data-stu-id="959a2-119">How to: Define a Conversion Operator</span></span>](./how-to-define-a-conversion-operator.md)
- [<span data-ttu-id="959a2-120">如何：调用运算符过程</span><span class="sxs-lookup"><span data-stu-id="959a2-120">How to: Call an Operator Procedure</span></span>](./how-to-call-an-operator-procedure.md)
- [<span data-ttu-id="959a2-121">Widening</span><span class="sxs-lookup"><span data-stu-id="959a2-121">Widening</span></span>](../../../../visual-basic/language-reference/modifiers/widening.md)
- [<span data-ttu-id="959a2-122">Narrowing</span><span class="sxs-lookup"><span data-stu-id="959a2-122">Narrowing</span></span>](../../../../visual-basic/language-reference/modifiers/narrowing.md)
- [<span data-ttu-id="959a2-123">Structure 语句</span><span class="sxs-lookup"><span data-stu-id="959a2-123">Structure Statement</span></span>](../../../../visual-basic/language-reference/statements/structure-statement.md)
- [<span data-ttu-id="959a2-124">如何：声明结构</span><span class="sxs-lookup"><span data-stu-id="959a2-124">How to: Declare a Structure</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/how-to-declare-a-structure.md)
- [<span data-ttu-id="959a2-125">隐式转换和显式转换</span><span class="sxs-lookup"><span data-stu-id="959a2-125">Implicit and Explicit Conversions</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)
- [<span data-ttu-id="959a2-126">扩大转换和收缩转换</span><span class="sxs-lookup"><span data-stu-id="959a2-126">Widening and Narrowing Conversions</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
