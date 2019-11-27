---
title: 如何：将自变量传递给过程
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
ms.openlocfilehash: 0267eed7c145988d61de715fd661bd4906d8d57d
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74344847"
---
# <a name="how-to-pass-arguments-to-a-procedure-visual-basic"></a><span data-ttu-id="19d01-102">如何：将参数传递给过程 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="19d01-102">How to: Pass Arguments to a Procedure (Visual Basic)</span></span>
<span data-ttu-id="19d01-103">调用过程时，请在括号中使用参数列表的过程名称。</span><span class="sxs-lookup"><span data-stu-id="19d01-103">When you call a procedure, you follow the procedure name with an argument list in parentheses.</span></span> <span data-ttu-id="19d01-104">提供与过程定义的每个必需参数相对应的参数，可选择为 `Optional` 参数提供参数。</span><span class="sxs-lookup"><span data-stu-id="19d01-104">You supply an argument corresponding to every required parameter the procedure defines, and you can optionally supply arguments to the `Optional` parameters.</span></span> <span data-ttu-id="19d01-105">如果未在调用中提供 `Optional` 参数，则在提供任何后续参数时，必须包含一个逗号来标记其在参数列表中的位置。</span><span class="sxs-lookup"><span data-stu-id="19d01-105">If you do not supply an `Optional` parameter in the call, you must include a comma to mark its place in the argument list if you are supplying any subsequent arguments.</span></span>  
  
 <span data-ttu-id="19d01-106">如果要传递的参数的数据类型不同于其对应参数的参数（例如 `Byte` `String`，则可以将类型检查开关（[Option Strict 语句](../../../../visual-basic/language-reference/statements/option-strict-statement.md)）设置为 `Off`。</span><span class="sxs-lookup"><span data-stu-id="19d01-106">If you intend to pass an argument of a data type different from that of its corresponding parameter, such as `Byte` to `String`, you can set the type-checking switch ([Option Strict Statement](../../../../visual-basic/language-reference/statements/option-strict-statement.md)) to `Off`.</span></span> <span data-ttu-id="19d01-107">如果 `On``Option Strict`，则必须使用扩大转换或显式转换关键字。</span><span class="sxs-lookup"><span data-stu-id="19d01-107">If `Option Strict` is `On`, you must use either widening conversions or explicit conversion keywords.</span></span> <span data-ttu-id="19d01-108">有关详细信息，请参阅[扩大和收缩转换](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)和[类型转换函数](../../../../visual-basic/language-reference/functions/type-conversion-functions.md)。</span><span class="sxs-lookup"><span data-stu-id="19d01-108">For more information, see [Widening and Narrowing Conversions](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md) and [Type Conversion Functions](../../../../visual-basic/language-reference/functions/type-conversion-functions.md).</span></span>  
  
 <span data-ttu-id="19d01-109">有关详细信息，请参阅[过程参数和参数](./procedure-parameters-and-arguments.md)。</span><span class="sxs-lookup"><span data-stu-id="19d01-109">For more information, see [Procedure Parameters and Arguments](./procedure-parameters-and-arguments.md).</span></span>  
  
### <a name="to-pass-one-or-more-arguments-to-a-procedure"></a><span data-ttu-id="19d01-110">将一个或多个自变量传递给过程</span><span class="sxs-lookup"><span data-stu-id="19d01-110">To pass one or more arguments to a procedure</span></span>  
  
1. <span data-ttu-id="19d01-111">在调用语句中，在过程名称后面加上括号。</span><span class="sxs-lookup"><span data-stu-id="19d01-111">In the calling statement, follow the procedure name with parentheses.</span></span>  
  
2. <span data-ttu-id="19d01-112">在括号内，放入参数列表。</span><span class="sxs-lookup"><span data-stu-id="19d01-112">Inside the parentheses, put an argument list.</span></span> <span data-ttu-id="19d01-113">为过程定义的每个必需参数包含一个参数，并使用逗号分隔参数。</span><span class="sxs-lookup"><span data-stu-id="19d01-113">Include an argument for each required parameter the procedure defines, and separate the arguments with commas.</span></span>  
  
3. <span data-ttu-id="19d01-114">请确保每个参数都是一个有效的表达式，该表达式的计算结果为可转换为相应参数的过程定义的类型的数据类型。</span><span class="sxs-lookup"><span data-stu-id="19d01-114">Make sure each argument is a valid expression that evaluates to a data type convertible to the type the procedure defines for the corresponding parameter.</span></span>  
  
4. <span data-ttu-id="19d01-115">如果将某个参数定义为[可选](../../../../visual-basic/language-reference/modifiers/optional.md)参数，则可以将其包含在自变量列表中，或将其省略。</span><span class="sxs-lookup"><span data-stu-id="19d01-115">If a parameter is defined as [Optional](../../../../visual-basic/language-reference/modifiers/optional.md), you can either include it in the argument list or omit it.</span></span> <span data-ttu-id="19d01-116">如果省略该参数，则该过程将使用为该参数定义的默认值。</span><span class="sxs-lookup"><span data-stu-id="19d01-116">If you omit it, the procedure uses the default value defined for that parameter.</span></span>  
  
5. <span data-ttu-id="19d01-117">如果为 `Optional` 参数省略了一个参数，并且参数列表中后面有另一个参数，则可以在参数列表中用一个额外的逗号标记省略的参数的位置。</span><span class="sxs-lookup"><span data-stu-id="19d01-117">If you omit an argument for an `Optional` parameter and there is another parameter after it in the parameter list, you can mark the place of the omitted argument by an extra comma in the argument list.</span></span>  
  
     <span data-ttu-id="19d01-118">下面的示例调用 Visual Basic <xref:Microsoft.VisualBasic.Interaction.MsgBox%2A> 函数。</span><span class="sxs-lookup"><span data-stu-id="19d01-118">The following example calls the Visual Basic <xref:Microsoft.VisualBasic.Interaction.MsgBox%2A> function.</span></span>  
  
     [!code-vb[VbVbcnProcedures#34](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#34)]  
  
     <span data-ttu-id="19d01-119">前面的示例提供了必需的第一个参数，即要显示的消息字符串。</span><span class="sxs-lookup"><span data-stu-id="19d01-119">The preceding example supplies the required first argument, which is the message string to be displayed.</span></span> <span data-ttu-id="19d01-120">它省略了可选的第二个参数的参数，该参数指定要在消息框中显示的按钮。</span><span class="sxs-lookup"><span data-stu-id="19d01-120">It omits an argument for the optional second parameter, which specifies the buttons to be displayed on the message box.</span></span> <span data-ttu-id="19d01-121">由于调用不提供值，因此 `MsgBox` 使用默认值 `MsgBoxStyle.OKOnly`，该默认值仅显示 **"确定"** 按钮。</span><span class="sxs-lookup"><span data-stu-id="19d01-121">Because the call does not supply a value, `MsgBox` uses the default value, `MsgBoxStyle.OKOnly`, which displays only an **OK** button.</span></span>  
  
     <span data-ttu-id="19d01-122">自变量列表中的第二个逗号标记省略的第二个参数的位置，最后一个字符串传递给 `MsgBox`的可选第三个参数，即要在标题栏中显示的文本。</span><span class="sxs-lookup"><span data-stu-id="19d01-122">The second comma in the argument list marks the place of the omitted second argument, and the last string is passed to the optional third parameter of `MsgBox`, which is the text to be displayed in the title bar.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="19d01-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="19d01-123">See also</span></span>

- [<span data-ttu-id="19d01-124">Sub 过程</span><span class="sxs-lookup"><span data-stu-id="19d01-124">Sub Procedures</span></span>](./sub-procedures.md)
- [<span data-ttu-id="19d01-125">Function 过程</span><span class="sxs-lookup"><span data-stu-id="19d01-125">Function Procedures</span></span>](./function-procedures.md)
- [<span data-ttu-id="19d01-126">属性过程</span><span class="sxs-lookup"><span data-stu-id="19d01-126">Property Procedures</span></span>](./property-procedures.md)
- [<span data-ttu-id="19d01-127">运算符过程</span><span class="sxs-lookup"><span data-stu-id="19d01-127">Operator Procedures</span></span>](./operator-procedures.md)
- [<span data-ttu-id="19d01-128">如何：为过程定义参数</span><span class="sxs-lookup"><span data-stu-id="19d01-128">How to: Define a Parameter for a Procedure</span></span>](./how-to-define-a-parameter-for-a-procedure.md)
- [<span data-ttu-id="19d01-129">按值和按引用传递自变量</span><span class="sxs-lookup"><span data-stu-id="19d01-129">Passing Arguments by Value and by Reference</span></span>](./passing-arguments-by-value-and-by-reference.md)
- [<span data-ttu-id="19d01-130">递归过程</span><span class="sxs-lookup"><span data-stu-id="19d01-130">Recursive Procedures</span></span>](./recursive-procedures.md)
- [<span data-ttu-id="19d01-131">过程重载</span><span class="sxs-lookup"><span data-stu-id="19d01-131">Procedure Overloading</span></span>](./procedure-overloading.md)
- [<span data-ttu-id="19d01-132">对象和类</span><span class="sxs-lookup"><span data-stu-id="19d01-132">Objects and Classes</span></span>](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
- [<span data-ttu-id="19d01-133">面向对象的编程 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="19d01-133">Object-Oriented Programming (Visual Basic)</span></span>](../../concepts/object-oriented-programming.md)
