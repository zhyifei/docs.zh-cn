---
title: 如何：使用定义运算符的类 (Visual Basic)
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
ms.openlocfilehash: 7e1d5698c1e83f0adf1be67245e0726aecaabdac
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33650600"
---
# <a name="how-to-use-a-class-that-defines-operators-visual-basic"></a><span data-ttu-id="4d545-102">如何：使用定义运算符的类 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4d545-102">How to: Use a Class that Defines Operators (Visual Basic)</span></span>
<span data-ttu-id="4d545-103">如果你使用的类或结构，它定义自己的运算符，则可以从 Visual Basic 中访问这些运算符。</span><span class="sxs-lookup"><span data-stu-id="4d545-103">If you are using a class or structure that defines its own operators, you can access those operators from Visual Basic.</span></span>  
  
 <span data-ttu-id="4d545-104">在类或结构上定义一个运算符也称为*重载*运算符。</span><span class="sxs-lookup"><span data-stu-id="4d545-104">Defining an operator on a class or structure is also called *overloading* the operator.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4d545-105">示例</span><span class="sxs-lookup"><span data-stu-id="4d545-105">Example</span></span>  
 <span data-ttu-id="4d545-106">以下示例访问 SQL 结构<xref:System.Data.SqlTypes.SqlString>，后者定义转换运算符 ([CType 函数](../../../../visual-basic/language-reference/functions/ctype-function.md)) 中的 SQL 字符串和 Visual Basic 字符串之间的两个方向。</span><span class="sxs-lookup"><span data-stu-id="4d545-106">The following example accesses the SQL structure <xref:System.Data.SqlTypes.SqlString>, which defines the conversion operators ([CType Function](../../../../visual-basic/language-reference/functions/ctype-function.md)) in both directions between a SQL string and a Visual Basic string.</span></span> <span data-ttu-id="4d545-107">使用`CType(` *SQL 字符串表达式*，`String)`将 SQL 字符串转换为 Visual Basic 字符串，和`CType(` *Visual Basic 字符串表达式*， <xref:System.Data.SqlTypes.SqlString> `)`在另一个方向转换。</span><span class="sxs-lookup"><span data-stu-id="4d545-107">Use `CType(`*SQL string expression*, `String)` to convert a SQL string to a Visual Basic string, and `CType(`*Visual Basic string expression*, <xref:System.Data.SqlTypes.SqlString>`)` to convert in the other direction.</span></span>  
  
 [!code-vb[VbVbcnProcedures#30](./codesnippet/VisualBasic/how-to-use-a-class-that-defines-operators_1.vb)]  
  
 [!code-vb[VbVbcnProcedures#31](./codesnippet/VisualBasic/how-to-use-a-class-that-defines-operators_2.vb)]  
  
 <span data-ttu-id="4d545-108"><xref:System.Data.SqlTypes.SqlString>结构定义的转换运算符 ([CType 函数](../../../../visual-basic/language-reference/functions/ctype-function.md)) 从`String`到<xref:System.Data.SqlTypes.SqlString>，另一个从<xref:System.Data.SqlTypes.SqlString>到`String`。</span><span class="sxs-lookup"><span data-stu-id="4d545-108">The <xref:System.Data.SqlTypes.SqlString> structure defines a conversion operator ([CType Function](../../../../visual-basic/language-reference/functions/ctype-function.md)) from `String` to <xref:System.Data.SqlTypes.SqlString> and another from <xref:System.Data.SqlTypes.SqlString> to `String`.</span></span> <span data-ttu-id="4d545-109">将分配的语句`title`到`jobTitle`使用第一个运算符，与<xref:Microsoft.VisualBasic.Interaction.MsgBox%2A>函数调用使用第二个。</span><span class="sxs-lookup"><span data-stu-id="4d545-109">The statement that assigns `title` to `jobTitle` makes use of the first operator, and the <xref:Microsoft.VisualBasic.Interaction.MsgBox%2A> function call uses the second.</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="4d545-110">编译代码</span><span class="sxs-lookup"><span data-stu-id="4d545-110">Compiling the Code</span></span>  
 <span data-ttu-id="4d545-111">请确保类或结构将定义你想要使用的运算符。</span><span class="sxs-lookup"><span data-stu-id="4d545-111">Be sure the class or structure you are using defines the operator you want to use.</span></span> <span data-ttu-id="4d545-112">不要假定的类或结构已定义每个可用于重载的运算符。</span><span class="sxs-lookup"><span data-stu-id="4d545-112">Do not assume that the class or structure has defined every operator available for overloading.</span></span> <span data-ttu-id="4d545-113">可用运算符的列表，请参阅[Operator 语句](../../../../visual-basic/language-reference/statements/operator-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="4d545-113">For a list of available operators, see [Operator Statement](../../../../visual-basic/language-reference/statements/operator-statement.md).</span></span>  
  
 <span data-ttu-id="4d545-114">应包括适当`Imports`SQL 字符串的开头的源文件的语句 (在这种情况下<xref:System.Data.SqlTypes>)。</span><span class="sxs-lookup"><span data-stu-id="4d545-114">Include the appropriate `Imports` statement for the SQL string at the beginning of your source file (in this case <xref:System.Data.SqlTypes>).</span></span>  
  
 <span data-ttu-id="4d545-115">你的项目必须具有对 System.Data 和 System.XML 的引用。</span><span class="sxs-lookup"><span data-stu-id="4d545-115">Your project must have references to System.Data and System.XML.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4d545-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="4d545-116">See Also</span></span>  
 [<span data-ttu-id="4d545-117">运算符过程</span><span class="sxs-lookup"><span data-stu-id="4d545-117">Operator Procedures</span></span>](./operator-procedures.md)  
 [<span data-ttu-id="4d545-118">如何：定义运算符</span><span class="sxs-lookup"><span data-stu-id="4d545-118">How to: Define an Operator</span></span>](./how-to-define-an-operator.md)  
 [<span data-ttu-id="4d545-119">如何：定义转换运算符</span><span class="sxs-lookup"><span data-stu-id="4d545-119">How to: Define a Conversion Operator</span></span>](./how-to-define-a-conversion-operator.md)  
 [<span data-ttu-id="4d545-120">如何：调用运算符过程</span><span class="sxs-lookup"><span data-stu-id="4d545-120">How to: Call an Operator Procedure</span></span>](./how-to-call-an-operator-procedure.md)  
 [<span data-ttu-id="4d545-121">Widening</span><span class="sxs-lookup"><span data-stu-id="4d545-121">Widening</span></span>](../../../../visual-basic/language-reference/modifiers/widening.md)  
 [<span data-ttu-id="4d545-122">Narrowing</span><span class="sxs-lookup"><span data-stu-id="4d545-122">Narrowing</span></span>](../../../../visual-basic/language-reference/modifiers/narrowing.md)  
 [<span data-ttu-id="4d545-123">Structure 语句</span><span class="sxs-lookup"><span data-stu-id="4d545-123">Structure Statement</span></span>](../../../../visual-basic/language-reference/statements/structure-statement.md)  
 [<span data-ttu-id="4d545-124">如何：声明结构</span><span class="sxs-lookup"><span data-stu-id="4d545-124">How to: Declare a Structure</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/how-to-declare-a-structure.md)  
 [<span data-ttu-id="4d545-125">隐式转换和显式转换</span><span class="sxs-lookup"><span data-stu-id="4d545-125">Implicit and Explicit Conversions</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)  
 [<span data-ttu-id="4d545-126">扩大转换和收缩转换</span><span class="sxs-lookup"><span data-stu-id="4d545-126">Widening and Narrowing Conversions</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
