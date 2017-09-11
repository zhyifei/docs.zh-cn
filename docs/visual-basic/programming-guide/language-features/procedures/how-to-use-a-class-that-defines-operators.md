---
title: "如何︰ 使用类定义的运算符 (Visual Basic 中) |Microsoft 文档"
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
- procedures, calling
- examples [Visual Basic], CType
- syntax, Operator procedures
- operators [Visual Basic], overloading
- return values, Operator procedures
- operator overloading
ms.assetid: 7ccce94a-6ca0-47d1-9f3f-13385d34f5d5
caps.latest.revision: 21
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
ms.openlocfilehash: e4d76788346e08123102d56088c0a1e0f5f2238f
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017

---
# <a name="how-to-use-a-class-that-defines-operators-visual-basic"></a><span data-ttu-id="1cb6f-102">如何：使用定义运算符的类 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1cb6f-102">How to: Use a Class that Defines Operators (Visual Basic)</span></span>
<span data-ttu-id="1cb6f-103">如果使用类或结构，它定义自己的运算符，您可以访问这些运算符从[!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]。</span><span class="sxs-lookup"><span data-stu-id="1cb6f-103">If you are using a class or structure that defines its own operators, you can access those operators from [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)].</span></span>  
  
 <span data-ttu-id="1cb6f-104">也称为上类或结构定义一个运算符*重载*运算符。</span><span class="sxs-lookup"><span data-stu-id="1cb6f-104">Defining an operator on a class or structure is also called *overloading* the operator.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1cb6f-105">示例</span><span class="sxs-lookup"><span data-stu-id="1cb6f-105">Example</span></span>  
 <span data-ttu-id="1cb6f-106">以下示例将访问 SQL 结构<xref:System.Data.SqlTypes.SqlString>，它定义转换运算符 ([CType 函数](../../../../visual-basic/language-reference/functions/ctype-function.md)) 中的 SQL 字符串之间进行双向和[!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]字符串。</xref:System.Data.SqlTypes.SqlString></span><span class="sxs-lookup"><span data-stu-id="1cb6f-106">The following example accesses the SQL structure <xref:System.Data.SqlTypes.SqlString>, which defines the conversion operators ([CType Function](../../../../visual-basic/language-reference/functions/ctype-function.md)) in both directions between a SQL string and a [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] string.</span></span> <span data-ttu-id="1cb6f-107">使用`CType(` *SQL 字符串表达式*， `String)` SQL 将字符串转换为[!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]字符串，并`CType(` *Visual Basic 字符串表达式*，<xref:System.Data.SqlTypes.SqlString>`)`在反向转换。</xref:System.Data.SqlTypes.SqlString></span><span class="sxs-lookup"><span data-stu-id="1cb6f-107">Use `CType(`*SQL string expression*, `String)` to convert a SQL string to a [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] string, and `CType(`*Visual Basic string expression*, <xref:System.Data.SqlTypes.SqlString>`)` to convert in the other direction.</span></span>  
  
 <span data-ttu-id="1cb6f-108">[!code-vb[VbVbcnProcedures #&30;](./codesnippet/VisualBasic/how-to-use-a-class-that-defines-operators_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="1cb6f-108">[!code-vb[VbVbcnProcedures#30](./codesnippet/VisualBasic/how-to-use-a-class-that-defines-operators_1.vb)]</span></span>  
  
 <span data-ttu-id="1cb6f-109">[!code-vb[VbVbcnProcedures #&31;](./codesnippet/VisualBasic/how-to-use-a-class-that-defines-operators_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="1cb6f-109">[!code-vb[VbVbcnProcedures#31](./codesnippet/VisualBasic/how-to-use-a-class-that-defines-operators_2.vb)]</span></span>  
  
 <span data-ttu-id="1cb6f-110"><xref:System.Data.SqlTypes.SqlString>结构定义的转换运算符 ([CType 函数](../../../../visual-basic/language-reference/functions/ctype-function.md)) 从`String`到<xref:System.Data.SqlTypes.SqlString>，另一个从<xref:System.Data.SqlTypes.SqlString>到`String`。</xref:System.Data.SqlTypes.SqlString> </xref:System.Data.SqlTypes.SqlString> </xref:System.Data.SqlTypes.SqlString></span><span class="sxs-lookup"><span data-stu-id="1cb6f-110">The <xref:System.Data.SqlTypes.SqlString> structure defines a conversion operator ([CType Function](../../../../visual-basic/language-reference/functions/ctype-function.md)) from `String` to <xref:System.Data.SqlTypes.SqlString> and another from <xref:System.Data.SqlTypes.SqlString> to `String`.</span></span> <span data-ttu-id="1cb6f-111">将分配的语句`title`到`jobTitle`利用了第一个运算符，与<xref:Microsoft.VisualBasic.Interaction.MsgBox%2A>函数调用时，使用第二个。</xref:Microsoft.VisualBasic.Interaction.MsgBox%2A></span><span class="sxs-lookup"><span data-stu-id="1cb6f-111">The statement that assigns `title` to `jobTitle` makes use of the first operator, and the <xref:Microsoft.VisualBasic.Interaction.MsgBox%2A> function call uses the second.</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="1cb6f-112">编译代码</span><span class="sxs-lookup"><span data-stu-id="1cb6f-112">Compiling the Code</span></span>  
 <span data-ttu-id="1cb6f-113">请确保类或结构正在使用定义你想要使用的运算符。</span><span class="sxs-lookup"><span data-stu-id="1cb6f-113">Be sure the class or structure you are using defines the operator you want to use.</span></span> <span data-ttu-id="1cb6f-114">不要假定类或结构已定义每个运算符可进行重载。</span><span class="sxs-lookup"><span data-stu-id="1cb6f-114">Do not assume that the class or structure has defined every operator available for overloading.</span></span> <span data-ttu-id="1cb6f-115">可用运算符的列表，请参阅[Operator 语句](../../../../visual-basic/language-reference/statements/operator-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="1cb6f-115">For a list of available operators, see [Operator Statement](../../../../visual-basic/language-reference/statements/operator-statement.md).</span></span>  
  
 <span data-ttu-id="1cb6f-116">包括相应`Imports`SQL 字符串的开头的源文件的语句 (在这种情况下<xref:System.Data.SqlTypes>)。</xref:System.Data.SqlTypes></span><span class="sxs-lookup"><span data-stu-id="1cb6f-116">Include the appropriate `Imports` statement for the SQL string at the beginning of your source file (in this case <xref:System.Data.SqlTypes>).</span></span>  
  
 <span data-ttu-id="1cb6f-117">您的项目必须具有对 System.Data 和 System.XML 的引用。</span><span class="sxs-lookup"><span data-stu-id="1cb6f-117">Your project must have references to System.Data and System.XML.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1cb6f-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1cb6f-118">See Also</span></span>  
 <span data-ttu-id="1cb6f-119">[运算符过程](./operator-procedures.md) </span><span class="sxs-lookup"><span data-stu-id="1cb6f-119">[Operator Procedures](./operator-procedures.md) </span></span>  
<span data-ttu-id="1cb6f-120"> [如何︰ 定义运算符](./how-to-define-an-operator.md) </span><span class="sxs-lookup"><span data-stu-id="1cb6f-120"> [How to: Define an Operator](./how-to-define-an-operator.md) </span></span>  
<span data-ttu-id="1cb6f-121"> [如何︰ 定义转换运算符](./how-to-define-a-conversion-operator.md) </span><span class="sxs-lookup"><span data-stu-id="1cb6f-121"> [How to: Define a Conversion Operator](./how-to-define-a-conversion-operator.md) </span></span>  
<span data-ttu-id="1cb6f-122"> [如何︰ 调用运算符过程](./how-to-call-an-operator-procedure.md) </span><span class="sxs-lookup"><span data-stu-id="1cb6f-122"> [How to: Call an Operator Procedure](./how-to-call-an-operator-procedure.md) </span></span>  
<span data-ttu-id="1cb6f-123"> [扩大转换](../../../../visual-basic/language-reference/modifiers/widening.md) </span><span class="sxs-lookup"><span data-stu-id="1cb6f-123"> [Widening](../../../../visual-basic/language-reference/modifiers/widening.md) </span></span>  
<span data-ttu-id="1cb6f-124"> [收缩转换](../../../../visual-basic/language-reference/modifiers/narrowing.md) </span><span class="sxs-lookup"><span data-stu-id="1cb6f-124"> [Narrowing](../../../../visual-basic/language-reference/modifiers/narrowing.md) </span></span>  
<span data-ttu-id="1cb6f-125"> [Structure 语句](../../../../visual-basic/language-reference/statements/structure-statement.md) </span><span class="sxs-lookup"><span data-stu-id="1cb6f-125"> [Structure Statement](../../../../visual-basic/language-reference/statements/structure-statement.md) </span></span>  
<span data-ttu-id="1cb6f-126"> [如何︰ 声明结构](../../../../visual-basic/programming-guide/language-features/data-types/how-to-declare-a-structure.md) </span><span class="sxs-lookup"><span data-stu-id="1cb6f-126"> [How to: Declare a Structure](../../../../visual-basic/programming-guide/language-features/data-types/how-to-declare-a-structure.md) </span></span>  
<span data-ttu-id="1cb6f-127"> [隐式和显式转换](../../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md) </span><span class="sxs-lookup"><span data-stu-id="1cb6f-127"> [Implicit and Explicit Conversions](../../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md) </span></span>  
<span data-ttu-id="1cb6f-128"> [扩大转换和收缩转换](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)</span><span class="sxs-lookup"><span data-stu-id="1cb6f-128"> [Widening and Narrowing Conversions](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)</span></span>
