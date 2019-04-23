---
title: 如何：将参数传递给过程 (Visual Basic)
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
ms.openlocfilehash: 012ad8e6229958575030ee820a3b0b79cc50facc
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59333900"
---
# <a name="how-to-pass-arguments-to-a-procedure-visual-basic"></a><span data-ttu-id="ffab9-102">如何：将参数传递给过程 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ffab9-102">How to: Pass Arguments to a Procedure (Visual Basic)</span></span>
<span data-ttu-id="ffab9-103">在调用过程时，过程名后面加上括号中的参数列表。</span><span class="sxs-lookup"><span data-stu-id="ffab9-103">When you call a procedure, you follow the procedure name with an argument list in parentheses.</span></span> <span data-ttu-id="ffab9-104">你提供该过程定义，对应于每个所需的参数的自变量，则可以选择提供参数`Optional`参数。</span><span class="sxs-lookup"><span data-stu-id="ffab9-104">You supply an argument corresponding to every required parameter the procedure defines, and you can optionally supply arguments to the `Optional` parameters.</span></span> <span data-ttu-id="ffab9-105">如果不提供`Optional`中调用的参数，必须包含一个逗号来标记其原位置自变量列表中的，如果你提供的任何后续自变量。</span><span class="sxs-lookup"><span data-stu-id="ffab9-105">If you do not supply an `Optional` parameter in the call, you must include a comma to mark its place in the argument list if you are supplying any subsequent arguments.</span></span>  
  
 <span data-ttu-id="ffab9-106">如果你想要的自变量传递的数据类型不同于其相应的参数，如`Byte`到`String`，可以设置类型检查开关 ([Option Strict 语句](../../../../visual-basic/language-reference/statements/option-strict-statement.md)) 到`Off`。</span><span class="sxs-lookup"><span data-stu-id="ffab9-106">If you intend to pass an argument of a data type different from that of its corresponding parameter, such as `Byte` to `String`, you can set the type-checking switch ([Option Strict Statement](../../../../visual-basic/language-reference/statements/option-strict-statement.md)) to `Off`.</span></span> <span data-ttu-id="ffab9-107">如果`Option Strict`是`On`，则必须使用扩大转换或显式转换关键字。</span><span class="sxs-lookup"><span data-stu-id="ffab9-107">If `Option Strict` is `On`, you must use either widening conversions or explicit conversion keywords.</span></span> <span data-ttu-id="ffab9-108">有关详细信息，请参阅[Widening and Narrowing Conversions](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)并[类型转换函数](../../../../visual-basic/language-reference/functions/type-conversion-functions.md)。</span><span class="sxs-lookup"><span data-stu-id="ffab9-108">For more information, see [Widening and Narrowing Conversions](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md) and [Type Conversion Functions](../../../../visual-basic/language-reference/functions/type-conversion-functions.md).</span></span>  
  
 <span data-ttu-id="ffab9-109">有关详细信息，请参阅[过程形参和实参](./procedure-parameters-and-arguments.md)。</span><span class="sxs-lookup"><span data-stu-id="ffab9-109">For more information, see [Procedure Parameters and Arguments](./procedure-parameters-and-arguments.md).</span></span>  
  
### <a name="to-pass-one-or-more-arguments-to-a-procedure"></a><span data-ttu-id="ffab9-110">若要将一个或多个自变量传递给过程</span><span class="sxs-lookup"><span data-stu-id="ffab9-110">To pass one or more arguments to a procedure</span></span>  
  
1. <span data-ttu-id="ffab9-111">在调用语句中，过程名后面加上括号。</span><span class="sxs-lookup"><span data-stu-id="ffab9-111">In the calling statement, follow the procedure name with parentheses.</span></span>  
  
2. <span data-ttu-id="ffab9-112">在圆括号内放置的参数列表。</span><span class="sxs-lookup"><span data-stu-id="ffab9-112">Inside the parentheses, put an argument list.</span></span> <span data-ttu-id="ffab9-113">包括每个所需的参数的参数定义了该过程，以及用逗号分隔参数。</span><span class="sxs-lookup"><span data-stu-id="ffab9-113">Include an argument for each required parameter the procedure defines, and separate the arguments with commas.</span></span>  
  
3. <span data-ttu-id="ffab9-114">请确保每个自变量是有效的表达式的计算结果为一个数据类型可转换为该过程的类型定义的相应参数。</span><span class="sxs-lookup"><span data-stu-id="ffab9-114">Make sure each argument is a valid expression that evaluates to a data type convertible to the type the procedure defines for the corresponding parameter.</span></span>  
  
4. <span data-ttu-id="ffab9-115">如果参数指[可选](../../../../visual-basic/language-reference/modifiers/optional.md)，可以将其包含在参数列表或省略此参数。</span><span class="sxs-lookup"><span data-stu-id="ffab9-115">If a parameter is defined as [Optional](../../../../visual-basic/language-reference/modifiers/optional.md), you can either include it in the argument list or omit it.</span></span> <span data-ttu-id="ffab9-116">如果省略此参数，该过程将使用为该参数定义的默认值。</span><span class="sxs-lookup"><span data-stu-id="ffab9-116">If you omit it, the procedure uses the default value defined for that parameter.</span></span>  
  
5. <span data-ttu-id="ffab9-117">如果省略参数`Optional`参数和另一个参数之后没有它的参数列表中，可以将省略自变量的位置标记的参数列表中一个多余的逗号。</span><span class="sxs-lookup"><span data-stu-id="ffab9-117">If you omit an argument for an `Optional` parameter and there is another parameter after it in the parameter list, you can mark the place of the omitted argument by an extra comma in the argument list.</span></span>  
  
     <span data-ttu-id="ffab9-118">下面的示例调用 Visual Basic<xref:Microsoft.VisualBasic.Interaction.MsgBox%2A>函数。</span><span class="sxs-lookup"><span data-stu-id="ffab9-118">The following example calls the Visual Basic <xref:Microsoft.VisualBasic.Interaction.MsgBox%2A> function.</span></span>  
  
     [!code-vb[VbVbcnProcedures#34](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#34)]  
  
     <span data-ttu-id="ffab9-119">前面的示例中提供了所需的第一个参数，它是要显示的消息字符串。</span><span class="sxs-lookup"><span data-stu-id="ffab9-119">The preceding example supplies the required first argument, which is the message string to be displayed.</span></span> <span data-ttu-id="ffab9-120">它会省略了可选的第二个参数，它指定要在消息框上显示的按钮的参数。</span><span class="sxs-lookup"><span data-stu-id="ffab9-120">It omits an argument for the optional second parameter, which specifies the buttons to be displayed on the message box.</span></span> <span data-ttu-id="ffab9-121">在调用不会提供一个值，因为`MsgBox`使用默认值`MsgBoxStyle.OKOnly`，后者将仅显示**确定**按钮。</span><span class="sxs-lookup"><span data-stu-id="ffab9-121">Because the call does not supply a value, `MsgBox` uses the default value, `MsgBoxStyle.OKOnly`, which displays only an **OK** button.</span></span>  
  
     <span data-ttu-id="ffab9-122">参数列表中的第二个逗号将标记省略的第二个参数的位置和最后一个字符串传递给第三个可选参数`MsgBox`，这是要在标题栏中显示的文本。</span><span class="sxs-lookup"><span data-stu-id="ffab9-122">The second comma in the argument list marks the place of the omitted second argument, and the last string is passed to the optional third parameter of `MsgBox`, which is the text to be displayed in the title bar.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ffab9-123">请参阅</span><span class="sxs-lookup"><span data-stu-id="ffab9-123">See also</span></span>

- [<span data-ttu-id="ffab9-124">Sub 过程</span><span class="sxs-lookup"><span data-stu-id="ffab9-124">Sub Procedures</span></span>](./sub-procedures.md)
- [<span data-ttu-id="ffab9-125">Function 过程</span><span class="sxs-lookup"><span data-stu-id="ffab9-125">Function Procedures</span></span>](./function-procedures.md)
- [<span data-ttu-id="ffab9-126">属性过程</span><span class="sxs-lookup"><span data-stu-id="ffab9-126">Property Procedures</span></span>](./property-procedures.md)
- [<span data-ttu-id="ffab9-127">运算符过程</span><span class="sxs-lookup"><span data-stu-id="ffab9-127">Operator Procedures</span></span>](./operator-procedures.md)
- [<span data-ttu-id="ffab9-128">如何：为过程定义参数</span><span class="sxs-lookup"><span data-stu-id="ffab9-128">How to: Define a Parameter for a Procedure</span></span>](./how-to-define-a-parameter-for-a-procedure.md)
- [<span data-ttu-id="ffab9-129">按值和按引用传递自变量</span><span class="sxs-lookup"><span data-stu-id="ffab9-129">Passing Arguments by Value and by Reference</span></span>](./passing-arguments-by-value-and-by-reference.md)
- [<span data-ttu-id="ffab9-130">递归过程</span><span class="sxs-lookup"><span data-stu-id="ffab9-130">Recursive Procedures</span></span>](./recursive-procedures.md)
- [<span data-ttu-id="ffab9-131">过程重载</span><span class="sxs-lookup"><span data-stu-id="ffab9-131">Procedure Overloading</span></span>](./procedure-overloading.md)
- [<span data-ttu-id="ffab9-132">对象和类</span><span class="sxs-lookup"><span data-stu-id="ffab9-132">Objects and Classes</span></span>](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
- [<span data-ttu-id="ffab9-133">面向对象的编程 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ffab9-133">Object-Oriented Programming (Visual Basic)</span></span>](../../concepts/object-oriented-programming.md)
