---
title: "在 Visual Basic 中的串联运算符 |Microsoft 文档"
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
- '& operator [Visual Basic], concatenation'
- concatenation operators
- operators [Visual Basic], concatenation
- Visual Basic code, operators
- + operator [Visual Basic], concatenation
- concatenation operators, Visual Basic strings
ms.assetid: e59908c3-89e0-41ae-933d-3e8826c16a04
caps.latest.revision: 18
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
ms.openlocfilehash: f255e168b9eb794ef846e0cc18dbbdba5941bec5
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017

---
# <a name="concatenation-operators-in-visual-basic"></a><span data-ttu-id="bf67f-102">串联运算符 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="bf67f-102">Concatenation Operators in Visual Basic</span></span>
<span data-ttu-id="bf67f-103">串联运算符将多个字符串联接为一个字符串。</span><span class="sxs-lookup"><span data-stu-id="bf67f-103">Concatenation operators join multiple strings into a single string.</span></span> <span data-ttu-id="bf67f-104">有两种串联运算符：`+` 和 `&`。</span><span class="sxs-lookup"><span data-stu-id="bf67f-104">There are two concatenation operators, `+` and `&`.</span></span> <span data-ttu-id="bf67f-105">这两种串联运算符都执行基本的串联运算，如下面的示例所示。</span><span class="sxs-lookup"><span data-stu-id="bf67f-105">Both carry out the basic concatenation operation, as the following example shows.</span></span>  
  
```vb
Dim x As String = "Mic" & "ro" & "soft" 
Dim y As String = "Mic" + "ro" + "soft" 
' The preceding statements set both x and y to "Microsoft".
```  
  
 <span data-ttu-id="bf67f-106">这两种运算符还可以串联 `String` 变量，如下面的示例所示。</span><span class="sxs-lookup"><span data-stu-id="bf67f-106">These operators can also concatenate `String` variables, as the following example shows.</span></span>  
  
 <span data-ttu-id="bf67f-107">[!code-vb[VbVbalrOperators #&76;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/concatenation-operators_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="bf67f-107">[!code-vb[VbVbalrOperators#76](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/concatenation-operators_1.vb)]</span></span>  
  
## <a name="differences-between-the-two-concatenation-operators"></a><span data-ttu-id="bf67f-108">两种串联运算符之间的区别</span><span class="sxs-lookup"><span data-stu-id="bf67f-108">Differences Between the Two Concatenation Operators</span></span>  
 <span data-ttu-id="bf67f-109">[+ 运算符](../../../../visual-basic/language-reference/operators/addition-operator.md)具有两个数字相加的主要目的。</span><span class="sxs-lookup"><span data-stu-id="bf67f-109">The [+ Operator](../../../../visual-basic/language-reference/operators/addition-operator.md) has the primary purpose of adding two numbers.</span></span> <span data-ttu-id="bf67f-110">然而，它还可以将数值操作数与字符串操作数串联起来。</span><span class="sxs-lookup"><span data-stu-id="bf67f-110">However, it can also concatenate numeric operands with string operands.</span></span> <span data-ttu-id="bf67f-111">`+`运算符具有一组复杂的规则，用于确定是要添加、 串联、 指示编译器错误还是引发运行时<xref:System.InvalidCastException>异常。</xref:System.InvalidCastException></span><span class="sxs-lookup"><span data-stu-id="bf67f-111">The `+` operator has a complex set of rules that determine whether to add, concatenate, signal a compiler error, or throw a run-time <xref:System.InvalidCastException> exception.</span></span>  
  
 <span data-ttu-id="bf67f-112">[& 运算符](../../../../visual-basic/language-reference/operators/concatenation-operator.md)仅为定义`String`操作数，而且始终将向其操作数扩展`String`，而不考虑设置的`Option Strict`。</span><span class="sxs-lookup"><span data-stu-id="bf67f-112">The [& Operator](../../../../visual-basic/language-reference/operators/concatenation-operator.md) is defined only for `String` operands, and it always widens its operands to `String`, regardless of the setting of `Option Strict`.</span></span> <span data-ttu-id="bf67f-113">对于字符串串联操作，建议使用 `&` 运算符，原因是它以独占方式为字符串定义，并降低产生意外转换的可能性。</span><span class="sxs-lookup"><span data-stu-id="bf67f-113">The `&` operator is recommended for string concatenation because it is defined exclusively for strings and reduces your chances of generating an unintended conversion.</span></span>  
  
## <a name="performance-string-and-stringbuilder"></a><span data-ttu-id="bf67f-114">性能：字符串和 StringBuilder</span><span class="sxs-lookup"><span data-stu-id="bf67f-114">Performance: String and StringBuilder</span></span>  
 <span data-ttu-id="bf67f-115">如果这样做很多操作在一个字符串，如串联、 删除或替换，您的性能可能会提高从<xref:System.Text.StringBuilder>类<xref:System.Text>命名空间。</xref:System.Text> </xref:System.Text.StringBuilder></span><span class="sxs-lookup"><span data-stu-id="bf67f-115">If you do a significant number of manipulations on a string, such as concatenations, deletions, and replacements, your performance might profit from the <xref:System.Text.StringBuilder> class in the <xref:System.Text> namespace.</span></span> <span data-ttu-id="bf67f-116">它采用额外指令来创建和初始化<xref:System.Text.StringBuilder>对象和其他指令将转换为其最终值`String`，但此时可能会因为恢复<xref:System.Text.StringBuilder>可以更快地执行。</xref:System.Text.StringBuilder> </xref:System.Text.StringBuilder></span><span class="sxs-lookup"><span data-stu-id="bf67f-116">It takes an extra instruction to create and initialize a <xref:System.Text.StringBuilder> object, and another instruction to convert its final value to a `String`, but you might recover this time because <xref:System.Text.StringBuilder> can perform faster.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bf67f-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="bf67f-117">See Also</span></span>  
 <span data-ttu-id="bf67f-118">[Option Strict 语句](../../../../visual-basic/language-reference/statements/option-strict-statement.md) </span><span class="sxs-lookup"><span data-stu-id="bf67f-118">[Option Strict Statement](../../../../visual-basic/language-reference/statements/option-strict-statement.md) </span></span>  
<span data-ttu-id="bf67f-119"> [在 Visual Basic 中的字符串操作方法的类型](../../../../visual-basic/programming-guide/language-features/strings/types-of-string-manipulation-methods.md) </span><span class="sxs-lookup"><span data-stu-id="bf67f-119"> [Types of String Manipulation Methods in Visual Basic](../../../../visual-basic/programming-guide/language-features/strings/types-of-string-manipulation-methods.md) </span></span>  
<span data-ttu-id="bf67f-120"> [在 Visual Basic 中的算术运算符](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md) </span><span class="sxs-lookup"><span data-stu-id="bf67f-120"> [Arithmetic Operators in Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md) </span></span>  
<span data-ttu-id="bf67f-121"> [在 Visual Basic 中的比较运算符](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md) </span><span class="sxs-lookup"><span data-stu-id="bf67f-121"> [Comparison Operators in Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md) </span></span>  
<span data-ttu-id="bf67f-122"> [在 Visual Basic 中的逻辑和按位运算符](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)</span><span class="sxs-lookup"><span data-stu-id="bf67f-122"> [Logical and Bitwise Operators in Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)</span></span>
