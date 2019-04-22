---
title: 如何：使用定义运算符 (Visual Basic) 的类
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
ms.openlocfilehash: bd512adf2f06ed0fbd3d36ed3175a0928bf1c57c
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "58829403"
---
# <a name="how-to-use-a-class-that-defines-operators-visual-basic"></a><span data-ttu-id="4accc-102">如何：使用定义运算符 (Visual Basic) 的类</span><span class="sxs-lookup"><span data-stu-id="4accc-102">How to: Use a Class that Defines Operators (Visual Basic)</span></span>
<span data-ttu-id="4accc-103">如果使用的类或结构，它定义自己的运算符，则可以在 Visual Basic 中访问这些运算符。</span><span class="sxs-lookup"><span data-stu-id="4accc-103">If you are using a class or structure that defines its own operators, you can access those operators from Visual Basic.</span></span>  
  
 <span data-ttu-id="4accc-104">在类或结构上定义一个运算符也称为*重载*运算符。</span><span class="sxs-lookup"><span data-stu-id="4accc-104">Defining an operator on a class or structure is also called *overloading* the operator.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4accc-105">示例</span><span class="sxs-lookup"><span data-stu-id="4accc-105">Example</span></span>  
 <span data-ttu-id="4accc-106">以下示例将访问 SQL 结构<xref:System.Data.SqlTypes.SqlString>，用于定义转换运算符 ([CType 函数](../../../../visual-basic/language-reference/functions/ctype-function.md)) 中的 SQL 字符串和 Visual Basic 字符串之间的两个方向。</span><span class="sxs-lookup"><span data-stu-id="4accc-106">The following example accesses the SQL structure <xref:System.Data.SqlTypes.SqlString>, which defines the conversion operators ([CType Function](../../../../visual-basic/language-reference/functions/ctype-function.md)) in both directions between a SQL string and a Visual Basic string.</span></span> <span data-ttu-id="4accc-107">使用`CType(` *SQL 字符串表达式*，`String)`若要将 SQL 字符串转换为 Visual Basic 字符串，并`CType(` *Visual Basic 字符串表达式*， <xref:System.Data.SqlTypes.SqlString> `)`将另一个方向。</span><span class="sxs-lookup"><span data-stu-id="4accc-107">Use `CType(`*SQL string expression*, `String)` to convert a SQL string to a Visual Basic string, and `CType(`*Visual Basic string expression*, <xref:System.Data.SqlTypes.SqlString>`)` to convert in the other direction.</span></span>  
  
 [!code-vb[VbVbcnProcedures#30](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#30)]  
  
 [!code-vb[VbVbcnProcedures#31](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#31)]  
  
 <span data-ttu-id="4accc-108"><xref:System.Data.SqlTypes.SqlString>结构定义转换运算符 ([CType Function](../../../../visual-basic/language-reference/functions/ctype-function.md)) 从`String`到<xref:System.Data.SqlTypes.SqlString>，从另一个<xref:System.Data.SqlTypes.SqlString>到`String`。</span><span class="sxs-lookup"><span data-stu-id="4accc-108">The <xref:System.Data.SqlTypes.SqlString> structure defines a conversion operator ([CType Function](../../../../visual-basic/language-reference/functions/ctype-function.md)) from `String` to <xref:System.Data.SqlTypes.SqlString> and another from <xref:System.Data.SqlTypes.SqlString> to `String`.</span></span> <span data-ttu-id="4accc-109">将分配的语句`title`到`jobTitle`利用了第一个运算符和<xref:Microsoft.VisualBasic.Interaction.MsgBox%2A>函数调用使用第二个。</span><span class="sxs-lookup"><span data-stu-id="4accc-109">The statement that assigns `title` to `jobTitle` makes use of the first operator, and the <xref:Microsoft.VisualBasic.Interaction.MsgBox%2A> function call uses the second.</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="4accc-110">编译代码</span><span class="sxs-lookup"><span data-stu-id="4accc-110">Compiling the Code</span></span>  
 <span data-ttu-id="4accc-111">请确保类或结构使用定义你想要使用的运算符。</span><span class="sxs-lookup"><span data-stu-id="4accc-111">Be sure the class or structure you are using defines the operator you want to use.</span></span> <span data-ttu-id="4accc-112">不要假定类或结构具有定义每个运算符可进行重载。</span><span class="sxs-lookup"><span data-stu-id="4accc-112">Do not assume that the class or structure has defined every operator available for overloading.</span></span> <span data-ttu-id="4accc-113">可用运算符列表，请参阅[Operator Statement](../../../../visual-basic/language-reference/statements/operator-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="4accc-113">For a list of available operators, see [Operator Statement](../../../../visual-basic/language-reference/statements/operator-statement.md).</span></span>  
  
 <span data-ttu-id="4accc-114">包括相应`Imports`语句处开始的 SQL 字符串的源文件 (在这种情况下<xref:System.Data.SqlTypes>)。</span><span class="sxs-lookup"><span data-stu-id="4accc-114">Include the appropriate `Imports` statement for the SQL string at the beginning of your source file (in this case <xref:System.Data.SqlTypes>).</span></span>  
  
 <span data-ttu-id="4accc-115">你的项目必须具有对 System.Data 和 System.XML 的引用。</span><span class="sxs-lookup"><span data-stu-id="4accc-115">Your project must have references to System.Data and System.XML.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4accc-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="4accc-116">See also</span></span>

- [<span data-ttu-id="4accc-117">运算符过程</span><span class="sxs-lookup"><span data-stu-id="4accc-117">Operator Procedures</span></span>](./operator-procedures.md)
- [<span data-ttu-id="4accc-118">如何：定义运算符</span><span class="sxs-lookup"><span data-stu-id="4accc-118">How to: Define an Operator</span></span>](./how-to-define-an-operator.md)
- [<span data-ttu-id="4accc-119">如何：定义转换运算符</span><span class="sxs-lookup"><span data-stu-id="4accc-119">How to: Define a Conversion Operator</span></span>](./how-to-define-a-conversion-operator.md)
- [<span data-ttu-id="4accc-120">如何：调用运算符过程</span><span class="sxs-lookup"><span data-stu-id="4accc-120">How to: Call an Operator Procedure</span></span>](./how-to-call-an-operator-procedure.md)
- [<span data-ttu-id="4accc-121">Widening</span><span class="sxs-lookup"><span data-stu-id="4accc-121">Widening</span></span>](../../../../visual-basic/language-reference/modifiers/widening.md)
- [<span data-ttu-id="4accc-122">Narrowing</span><span class="sxs-lookup"><span data-stu-id="4accc-122">Narrowing</span></span>](../../../../visual-basic/language-reference/modifiers/narrowing.md)
- [<span data-ttu-id="4accc-123">Structure 语句</span><span class="sxs-lookup"><span data-stu-id="4accc-123">Structure Statement</span></span>](../../../../visual-basic/language-reference/statements/structure-statement.md)
- [<span data-ttu-id="4accc-124">如何：声明结构</span><span class="sxs-lookup"><span data-stu-id="4accc-124">How to: Declare a Structure</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/how-to-declare-a-structure.md)
- [<span data-ttu-id="4accc-125">隐式转换和显式转换</span><span class="sxs-lookup"><span data-stu-id="4accc-125">Implicit and Explicit Conversions</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)
- [<span data-ttu-id="4accc-126">扩大转换和收缩转换</span><span class="sxs-lookup"><span data-stu-id="4accc-126">Widening and Narrowing Conversions</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
