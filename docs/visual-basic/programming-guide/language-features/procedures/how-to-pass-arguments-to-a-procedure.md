---
title: "如何︰ 将参数传递给过程 (Visual Basic 中) |Microsoft 文档"
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
- arguments [Visual Basic], passing to procedures
- procedures, arguments
- procedures, parameters
- procedure arguments
- Visual Basic code, procedures
- procedure parameters
- procedures, calling
- argument passing, procedures
ms.assetid: 08723588-3890-4ddc-8249-79e049e0f241
caps.latest.revision: 14
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
ms.openlocfilehash: 1e0a8d5e798f25f22f53f56a7c01bd69e3e14463
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017

---
# <a name="how-to-pass-arguments-to-a-procedure-visual-basic"></a><span data-ttu-id="afebe-102">如何：将自变量传递给过程 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="afebe-102">How to: Pass Arguments to a Procedure (Visual Basic)</span></span>
<span data-ttu-id="afebe-103">当调用过程时，过程名后面加上括号中的参数列表。</span><span class="sxs-lookup"><span data-stu-id="afebe-103">When you call a procedure, you follow the procedure name with an argument list in parentheses.</span></span> <span data-ttu-id="afebe-104">不提供参数对应于每个所需的参数定义了该过程，并可以选择提供参数`Optional`参数。</span><span class="sxs-lookup"><span data-stu-id="afebe-104">You supply an argument corresponding to every required parameter the procedure defines, and you can optionally supply arguments to the `Optional` parameters.</span></span> <span data-ttu-id="afebe-105">如果不提供`Optional`中调用的参数，必须包括逗号来标记其位置在参数列表中的，如果要提供任何后续的参数。</span><span class="sxs-lookup"><span data-stu-id="afebe-105">If you do not supply an `Optional` parameter in the call, you must include a comma to mark its place in the argument list if you are supplying any subsequent arguments.</span></span>  
  
 <span data-ttu-id="afebe-106">如果您想要的参数传递的数据类型不同于其对应的参数，如`Byte`到`String`，可设置类型检查开关 ([Option Strict 语句](../../../../visual-basic/language-reference/statements/option-strict-statement.md)) 到`Off`。</span><span class="sxs-lookup"><span data-stu-id="afebe-106">If you intend to pass an argument of a data type different from that of its corresponding parameter, such as `Byte` to `String`, you can set the type-checking switch ([Option Strict Statement](../../../../visual-basic/language-reference/statements/option-strict-statement.md)) to `Off`.</span></span> <span data-ttu-id="afebe-107">如果`Option Strict`是`On`，则必须使用扩大转换或显式转换的关键字。</span><span class="sxs-lookup"><span data-stu-id="afebe-107">If `Option Strict` is `On`, you must use either widening conversions or explicit conversion keywords.</span></span> <span data-ttu-id="afebe-108">有关详细信息，请参阅[扩大和收缩转换](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)和[类型转换函数](../../../../visual-basic/language-reference/functions/type-conversion-functions.md)。</span><span class="sxs-lookup"><span data-stu-id="afebe-108">For more information, see [Widening and Narrowing Conversions](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md) and [Type Conversion Functions](../../../../visual-basic/language-reference/functions/type-conversion-functions.md).</span></span>  
  
 <span data-ttu-id="afebe-109">有关详细信息，请参阅[过程参数和变量](./procedure-parameters-and-arguments.md)。</span><span class="sxs-lookup"><span data-stu-id="afebe-109">For more information, see [Procedure Parameters and Arguments](./procedure-parameters-and-arguments.md).</span></span>  
  
### <a name="to-pass-one-or-more-arguments-to-a-procedure"></a><span data-ttu-id="afebe-110">若要将一个或多个参数传递给过程</span><span class="sxs-lookup"><span data-stu-id="afebe-110">To pass one or more arguments to a procedure</span></span>  
  
1.  <span data-ttu-id="afebe-111">在调用的语句中，请按照带括号的过程名称。</span><span class="sxs-lookup"><span data-stu-id="afebe-111">In the calling statement, follow the procedure name with parentheses.</span></span>  
  
2.  <span data-ttu-id="afebe-112">在括号内，将参数列表。</span><span class="sxs-lookup"><span data-stu-id="afebe-112">Inside the parentheses, put an argument list.</span></span> <span data-ttu-id="afebe-113">包括每个所需的参数的参数定义了该过程，并且用逗号分隔参数。</span><span class="sxs-lookup"><span data-stu-id="afebe-113">Include an argument for each required parameter the procedure defines, and separate the arguments with commas.</span></span>  
  
3.  <span data-ttu-id="afebe-114">请确保每个参数是一个有效表达式，计算结果为数据类型转换为该过程的类型定义的相应参数。</span><span class="sxs-lookup"><span data-stu-id="afebe-114">Make sure each argument is a valid expression that evaluates to a data type convertible to the type the procedure defines for the corresponding parameter.</span></span>  
  
4.  <span data-ttu-id="afebe-115">如果参数定义为[可选](../../../../visual-basic/language-reference/modifiers/optional.md)，您可以将其包括在参数列表或省略此参数。</span><span class="sxs-lookup"><span data-stu-id="afebe-115">If a parameter is defined as [Optional](../../../../visual-basic/language-reference/modifiers/optional.md), you can either include it in the argument list or omit it.</span></span> <span data-ttu-id="afebe-116">如果省略此参数，该过程将使用定义为该参数的默认值。</span><span class="sxs-lookup"><span data-stu-id="afebe-116">If you omit it, the procedure uses the default value defined for that parameter.</span></span>  
  
5.  <span data-ttu-id="afebe-117">如果省略一个参数`Optional`参数并且没有另一个参数在它后面的参数列表中，您可以将省略参数的位置标记的参数列表中一个多余的逗号。</span><span class="sxs-lookup"><span data-stu-id="afebe-117">If you omit an argument for an `Optional` parameter and there is another parameter after it in the parameter list, you can mark the place of the omitted argument by an extra comma in the argument list.</span></span>  
  
     <span data-ttu-id="afebe-118">下面的示例调用[!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]<xref:Microsoft.VisualBasic.Interaction.MsgBox%2A>函数。</xref:Microsoft.VisualBasic.Interaction.MsgBox%2A></span><span class="sxs-lookup"><span data-stu-id="afebe-118">The following example calls the [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] <xref:Microsoft.VisualBasic.Interaction.MsgBox%2A> function.</span></span>  
  
     <span data-ttu-id="afebe-119">[!code-vb[VbVbcnProcedures #&34;](./codesnippet/VisualBasic/how-to-pass-arguments-to-a-procedure_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="afebe-119">[!code-vb[VbVbcnProcedures#34](./codesnippet/VisualBasic/how-to-pass-arguments-to-a-procedure_1.vb)]</span></span>  
  
     <span data-ttu-id="afebe-120">前面的示例中提供所需的第一个参数，这是要显示的消息字符串。</span><span class="sxs-lookup"><span data-stu-id="afebe-120">The preceding example supplies the required first argument, which is the message string to be displayed.</span></span> <span data-ttu-id="afebe-121">它会省略了可选的第二个参数，它指定要在消息框上显示的按钮的参数。</span><span class="sxs-lookup"><span data-stu-id="afebe-121">It omits an argument for the optional second parameter, which specifies the buttons to be displayed on the message box.</span></span> <span data-ttu-id="afebe-122">调用不会提供一个值，因为`MsgBox`使用默认值， `MsgBoxStyle.OKOnly`，后者将只显示**确定**按钮。</span><span class="sxs-lookup"><span data-stu-id="afebe-122">Because the call does not supply a value, `MsgBox` uses the default value, `MsgBoxStyle.OKOnly`, which displays only an **OK** button.</span></span>  
  
     <span data-ttu-id="afebe-123">在参数列表中的第二个逗号标记省略的第二个参数的位置和最后一个的字符串传递给第三个可选参数`MsgBox`，即在标题栏中显示的文本。</span><span class="sxs-lookup"><span data-stu-id="afebe-123">The second comma in the argument list marks the place of the omitted second argument, and the last string is passed to the optional third parameter of `MsgBox`, which is the text to be displayed in the title bar.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="afebe-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="afebe-124">See Also</span></span>  
 <span data-ttu-id="afebe-125">[Sub 过程](./sub-procedures.md) </span><span class="sxs-lookup"><span data-stu-id="afebe-125">[Sub Procedures](./sub-procedures.md) </span></span>  
<span data-ttu-id="afebe-126"> [Function 过程](./function-procedures.md) </span><span class="sxs-lookup"><span data-stu-id="afebe-126"> [Function Procedures](./function-procedures.md) </span></span>  
<span data-ttu-id="afebe-127"> [属性过程](./property-procedures.md) </span><span class="sxs-lookup"><span data-stu-id="afebe-127"> [Property Procedures](./property-procedures.md) </span></span>  
<span data-ttu-id="afebe-128"> [运算符过程](./operator-procedures.md) </span><span class="sxs-lookup"><span data-stu-id="afebe-128"> [Operator Procedures](./operator-procedures.md) </span></span>  
<span data-ttu-id="afebe-129"> [如何︰ 为过程定义参数](./how-to-define-a-parameter-for-a-procedure.md) </span><span class="sxs-lookup"><span data-stu-id="afebe-129"> [How to: Define a Parameter for a Procedure](./how-to-define-a-parameter-for-a-procedure.md) </span></span>  
<span data-ttu-id="afebe-130"> [通过值和通过引用传递参数](./passing-arguments-by-value-and-by-reference.md) </span><span class="sxs-lookup"><span data-stu-id="afebe-130"> [Passing Arguments by Value and by Reference](./passing-arguments-by-value-and-by-reference.md) </span></span>  
<span data-ttu-id="afebe-131"> [递归过程](./recursive-procedures.md) </span><span class="sxs-lookup"><span data-stu-id="afebe-131"> [Recursive Procedures](./recursive-procedures.md) </span></span>  
<span data-ttu-id="afebe-132"> [过程重载](./procedure-overloading.md) </span><span class="sxs-lookup"><span data-stu-id="afebe-132"> [Procedure Overloading](./procedure-overloading.md) </span></span>  
<span data-ttu-id="afebe-133"> [对象和类](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md) </span><span class="sxs-lookup"><span data-stu-id="afebe-133"> [Objects and Classes](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md) </span></span>  
<span data-ttu-id="afebe-134"> [面向对象的编程](http://msdn.microsoft.com/library/1cf6e655-3f30-45f1-9a5d-4a88ca24a1c2)</span><span class="sxs-lookup"><span data-stu-id="afebe-134"> [Object-Oriented Programming](http://msdn.microsoft.com/library/1cf6e655-3f30-45f1-9a5d-4a88ca24a1c2)</span></span>
