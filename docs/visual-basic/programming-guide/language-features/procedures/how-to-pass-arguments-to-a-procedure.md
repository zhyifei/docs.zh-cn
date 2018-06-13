---
title: 如何：将自变量传递给过程 (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- arguments [Visual Basic], passing to procedures
- procedures [Visual Basic], arguments
- procedures [Visual Basic], parameters
- procedure arguments
- Visual Basic code, procedures
- procedure parameters
- procedures [Visual Basic], calling
- argument passing [Visual Basic], procedures
ms.assetid: 08723588-3890-4ddc-8249-79e049e0f241
ms.openlocfilehash: f393f17f87c5920fb9bfa2a2097c09d48bebdc16
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33650587"
---
# <a name="how-to-pass-arguments-to-a-procedure-visual-basic"></a><span data-ttu-id="8a2cc-102">如何：将自变量传递给过程 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8a2cc-102">How to: Pass Arguments to a Procedure (Visual Basic)</span></span>
<span data-ttu-id="8a2cc-103">当调用过程时，过程名后面加上括号中的参数列表。</span><span class="sxs-lookup"><span data-stu-id="8a2cc-103">When you call a procedure, you follow the procedure name with an argument list in parentheses.</span></span> <span data-ttu-id="8a2cc-104">你提供参数对应于每个所需的参数为过程所定义，并且 （可选） 可以提供自变量`Optional`参数。</span><span class="sxs-lookup"><span data-stu-id="8a2cc-104">You supply an argument corresponding to every required parameter the procedure defines, and you can optionally supply arguments to the `Optional` parameters.</span></span> <span data-ttu-id="8a2cc-105">如果未提供`Optional`调用中的参数，必须包含逗号来标记其位置自变量列表中的，如果你所提供的任何后续自变量。</span><span class="sxs-lookup"><span data-stu-id="8a2cc-105">If you do not supply an `Optional` parameter in the call, you must include a comma to mark its place in the argument list if you are supplying any subsequent arguments.</span></span>  
  
 <span data-ttu-id="8a2cc-106">如果你想要的自变量传递的数据类型不同于其对应的参数，如`Byte`到`String`，你可以设置类型检查开关 ([Option Strict 语句](../../../../visual-basic/language-reference/statements/option-strict-statement.md)) 到`Off`。</span><span class="sxs-lookup"><span data-stu-id="8a2cc-106">If you intend to pass an argument of a data type different from that of its corresponding parameter, such as `Byte` to `String`, you can set the type-checking switch ([Option Strict Statement](../../../../visual-basic/language-reference/statements/option-strict-statement.md)) to `Off`.</span></span> <span data-ttu-id="8a2cc-107">如果`Option Strict`是`On`，则必须使用扩大转换或显式转换关键字。</span><span class="sxs-lookup"><span data-stu-id="8a2cc-107">If `Option Strict` is `On`, you must use either widening conversions or explicit conversion keywords.</span></span> <span data-ttu-id="8a2cc-108">有关详细信息，请参阅[扩大和收缩转换](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)和[类型转换函数](../../../../visual-basic/language-reference/functions/type-conversion-functions.md)。</span><span class="sxs-lookup"><span data-stu-id="8a2cc-108">For more information, see [Widening and Narrowing Conversions](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md) and [Type Conversion Functions](../../../../visual-basic/language-reference/functions/type-conversion-functions.md).</span></span>  
  
 <span data-ttu-id="8a2cc-109">有关详细信息，请参阅[过程参数和自变量](./procedure-parameters-and-arguments.md)。</span><span class="sxs-lookup"><span data-stu-id="8a2cc-109">For more information, see [Procedure Parameters and Arguments](./procedure-parameters-and-arguments.md).</span></span>  
  
### <a name="to-pass-one-or-more-arguments-to-a-procedure"></a><span data-ttu-id="8a2cc-110">将一个或多个自变量传递给过程</span><span class="sxs-lookup"><span data-stu-id="8a2cc-110">To pass one or more arguments to a procedure</span></span>  
  
1.  <span data-ttu-id="8a2cc-111">在调用语句中，过程名后面加上括号。</span><span class="sxs-lookup"><span data-stu-id="8a2cc-111">In the calling statement, follow the procedure name with parentheses.</span></span>  
  
2.  <span data-ttu-id="8a2cc-112">在括号内，将自变量列表。</span><span class="sxs-lookup"><span data-stu-id="8a2cc-112">Inside the parentheses, put an argument list.</span></span> <span data-ttu-id="8a2cc-113">包括每个所需的参数的自变量为过程所定义，并且用逗号分隔参数。</span><span class="sxs-lookup"><span data-stu-id="8a2cc-113">Include an argument for each required parameter the procedure defines, and separate the arguments with commas.</span></span>  
  
3.  <span data-ttu-id="8a2cc-114">请确保每个自变量是一个有效表达式，计算结果为一个数据类型可转换为类型过程定义的相应参数。</span><span class="sxs-lookup"><span data-stu-id="8a2cc-114">Make sure each argument is a valid expression that evaluates to a data type convertible to the type the procedure defines for the corresponding parameter.</span></span>  
  
4.  <span data-ttu-id="8a2cc-115">如果参数定义为[可选](../../../../visual-basic/language-reference/modifiers/optional.md)，您可以将其包含自变量列表中，也可以省略此参数。</span><span class="sxs-lookup"><span data-stu-id="8a2cc-115">If a parameter is defined as [Optional](../../../../visual-basic/language-reference/modifiers/optional.md), you can either include it in the argument list or omit it.</span></span> <span data-ttu-id="8a2cc-116">如果省略此元素时，过程将使用为该参数定义的默认值。</span><span class="sxs-lookup"><span data-stu-id="8a2cc-116">If you omit it, the procedure uses the default value defined for that parameter.</span></span>  
  
5.  <span data-ttu-id="8a2cc-117">如果省略的自变量`Optional`参数并且有另一个参数之后在参数列表中，可以将省略的自变量的位置标记的参数列表中的额外逗号。</span><span class="sxs-lookup"><span data-stu-id="8a2cc-117">If you omit an argument for an `Optional` parameter and there is another parameter after it in the parameter list, you can mark the place of the omitted argument by an extra comma in the argument list.</span></span>  
  
     <span data-ttu-id="8a2cc-118">下面的示例调用 Visual Basic<xref:Microsoft.VisualBasic.Interaction.MsgBox%2A>函数。</span><span class="sxs-lookup"><span data-stu-id="8a2cc-118">The following example calls the Visual Basic <xref:Microsoft.VisualBasic.Interaction.MsgBox%2A> function.</span></span>  
  
     [!code-vb[VbVbcnProcedures#34](./codesnippet/VisualBasic/how-to-pass-arguments-to-a-procedure_1.vb)]  
  
     <span data-ttu-id="8a2cc-119">前面的示例提供了所需的第一个参数，这是要显示的消息字符串。</span><span class="sxs-lookup"><span data-stu-id="8a2cc-119">The preceding example supplies the required first argument, which is the message string to be displayed.</span></span> <span data-ttu-id="8a2cc-120">它省略了可选的第二个参数，它指定要在消息框上显示的按钮的自变量。</span><span class="sxs-lookup"><span data-stu-id="8a2cc-120">It omits an argument for the optional second parameter, which specifies the buttons to be displayed on the message box.</span></span> <span data-ttu-id="8a2cc-121">调用未提供一个值，因为`MsgBox`使用默认值， `MsgBoxStyle.OKOnly`，这将仅显示**确定**按钮。</span><span class="sxs-lookup"><span data-stu-id="8a2cc-121">Because the call does not supply a value, `MsgBox` uses the default value, `MsgBoxStyle.OKOnly`, which displays only an **OK** button.</span></span>  
  
     <span data-ttu-id="8a2cc-122">在自变量列表中的第二个逗号将标记的位置省略第二个参数，并且最后一个的字符串传递给的可选第三个参数`MsgBox`，即在标题栏中显示的文本。</span><span class="sxs-lookup"><span data-stu-id="8a2cc-122">The second comma in the argument list marks the place of the omitted second argument, and the last string is passed to the optional third parameter of `MsgBox`, which is the text to be displayed in the title bar.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8a2cc-123">请参阅</span><span class="sxs-lookup"><span data-stu-id="8a2cc-123">See also</span></span>

 [<span data-ttu-id="8a2cc-124">Sub 过程</span><span class="sxs-lookup"><span data-stu-id="8a2cc-124">Sub Procedures</span></span>](./sub-procedures.md)  
 [<span data-ttu-id="8a2cc-125">Function 过程</span><span class="sxs-lookup"><span data-stu-id="8a2cc-125">Function Procedures</span></span>](./function-procedures.md)  
 [<span data-ttu-id="8a2cc-126">属性过程</span><span class="sxs-lookup"><span data-stu-id="8a2cc-126">Property Procedures</span></span>](./property-procedures.md)  
 [<span data-ttu-id="8a2cc-127">运算符过程</span><span class="sxs-lookup"><span data-stu-id="8a2cc-127">Operator Procedures</span></span>](./operator-procedures.md)  
 [<span data-ttu-id="8a2cc-128">如何：为过程定义参数</span><span class="sxs-lookup"><span data-stu-id="8a2cc-128">How to: Define a Parameter for a Procedure</span></span>](./how-to-define-a-parameter-for-a-procedure.md)  
 [<span data-ttu-id="8a2cc-129">按值和按引用传递自变量</span><span class="sxs-lookup"><span data-stu-id="8a2cc-129">Passing Arguments by Value and by Reference</span></span>](./passing-arguments-by-value-and-by-reference.md)  
 [<span data-ttu-id="8a2cc-130">递归过程</span><span class="sxs-lookup"><span data-stu-id="8a2cc-130">Recursive Procedures</span></span>](./recursive-procedures.md)  
 [<span data-ttu-id="8a2cc-131">过程重载</span><span class="sxs-lookup"><span data-stu-id="8a2cc-131">Procedure Overloading</span></span>](./procedure-overloading.md)  
 [<span data-ttu-id="8a2cc-132">对象和类</span><span class="sxs-lookup"><span data-stu-id="8a2cc-132">Objects and Classes</span></span>](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)  
 [<span data-ttu-id="8a2cc-133">面向对象的编程 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8a2cc-133">Object-Oriented Programming (Visual Basic)</span></span>](../../concepts/object-oriented-programming.md)  
