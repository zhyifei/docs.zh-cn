---
title: 过程参数和自变量
ms.date: 07/20/2015
helpviewer_keywords:
- procedures [Visual Basic], arguments
- procedures [Visual Basic], argument lists
- values [Visual Basic], passing to procedures
- arguments [Visual Basic], passing
- procedures [Visual Basic], parameters
- Visual Basic code, argument lists
- Visual Basic code, procedures
- parameters [Visual Basic], Visual Basic procedures
- parameters [Visual Basic], lists
- arguments [Visual Basic], Visual Basic procedures
- arguments [Visual Basic], procedures
- parameter lists [Visual Basic]
- Visual Basic code, parameter lists
- argument lists [Visual Basic]
- procedures [Visual Basic], parameter lists
ms.assetid: ff275aff-aa13-40df-bd4c-63486db8c1e9
ms.openlocfilehash: 7dfbbcb39cf7bb05c8a62a7a252e425f287c9a09
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74352583"
---
# <a name="procedure-parameters-and-arguments-visual-basic"></a><span data-ttu-id="0eae2-102">过程参数和自变量 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0eae2-102">Procedure Parameters and Arguments (Visual Basic)</span></span>
<span data-ttu-id="0eae2-103">在大多数情况下，过程需要一些有关调用环境的信息。</span><span class="sxs-lookup"><span data-stu-id="0eae2-103">In most cases, a procedure needs some information about the circumstances in which it has been called.</span></span> <span data-ttu-id="0eae2-104">执行重复或共享任务的过程对每个调用使用不同的信息。</span><span class="sxs-lookup"><span data-stu-id="0eae2-104">A procedure that performs repeated or shared tasks uses different information for each call.</span></span> <span data-ttu-id="0eae2-105">此信息包含变量、常量和在您调用过程时传递给该过程的表达式。</span><span class="sxs-lookup"><span data-stu-id="0eae2-105">This information consists of variables, constants, and expressions that you pass to the procedure when you call it.</span></span>  
  
 <span data-ttu-id="0eae2-106">*参数*表示一个值，该过程期望在调用时提供。</span><span class="sxs-lookup"><span data-stu-id="0eae2-106">A *parameter* represents a value that the procedure expects you to supply when you call it.</span></span> <span data-ttu-id="0eae2-107">过程声明定义了其参数。</span><span class="sxs-lookup"><span data-stu-id="0eae2-107">The procedure's declaration defines its parameters.</span></span>  
  
 <span data-ttu-id="0eae2-108">您可以定义没有参数、一个参数或多个参数的过程。</span><span class="sxs-lookup"><span data-stu-id="0eae2-108">You can define a procedure with no parameters, one parameter, or more than one.</span></span> <span data-ttu-id="0eae2-109">过程定义中指定参数的部分称为*参数列表*。</span><span class="sxs-lookup"><span data-stu-id="0eae2-109">The part of the procedure definition that specifies the parameters is called the *parameter list*.</span></span>  
  
 <span data-ttu-id="0eae2-110">*参数*表示在调用过程时提供给过程参数的值。</span><span class="sxs-lookup"><span data-stu-id="0eae2-110">An *argument* represents the value you supply to a procedure parameter when you call the procedure.</span></span> <span data-ttu-id="0eae2-111">调用代码在调用过程时提供自变量。</span><span class="sxs-lookup"><span data-stu-id="0eae2-111">The calling code supplies the arguments when it calls the procedure.</span></span> <span data-ttu-id="0eae2-112">过程调用中指定参数的部分称为*参数列表*。</span><span class="sxs-lookup"><span data-stu-id="0eae2-112">The part of the procedure call that specifies the arguments is called the *argument list*.</span></span>  
  
 <span data-ttu-id="0eae2-113">下图显示了从两个不同的位置调用过程 `safeSquareRoot` 的代码。</span><span class="sxs-lookup"><span data-stu-id="0eae2-113">The following illustration shows code calling the procedure `safeSquareRoot` from two different places.</span></span> <span data-ttu-id="0eae2-114">第一次调用将变量的值 `x` （4.0）传递给参数 `number`，并将 `root` （2.0）中的返回值分配给变量 `y`。</span><span class="sxs-lookup"><span data-stu-id="0eae2-114">The first call passes the value of the variable `x` (4.0) to the parameter `number`, and the return value in `root` (2.0) is assigned to the variable `y`.</span></span> <span data-ttu-id="0eae2-115">第二个调用将文本值9.0 传递到 `number`，并将返回值（3.0）分配给变量 `z`。</span><span class="sxs-lookup"><span data-stu-id="0eae2-115">The second call passes the literal value 9.0 to `number`, and assigns the return value (3.0) to variable `z`.</span></span>  
  
 ![显示将参数传递给参数的关系图](./media/procedure-parameters-and-arguments/pass-argument-parameter.gif)  
  
 <span data-ttu-id="0eae2-117">有关详细信息，请参阅[参数和参数之间的差异](./differences-between-parameters-and-arguments.md)。</span><span class="sxs-lookup"><span data-stu-id="0eae2-117">For more information, see [Differences Between Parameters and Arguments](./differences-between-parameters-and-arguments.md).</span></span>  
  
## <a name="parameter-data-type"></a><span data-ttu-id="0eae2-118">参数数据类型</span><span class="sxs-lookup"><span data-stu-id="0eae2-118">Parameter Data Type</span></span>  
 <span data-ttu-id="0eae2-119">可以通过在其声明中使用 `As` 子句来定义参数的数据类型。</span><span class="sxs-lookup"><span data-stu-id="0eae2-119">You define a data type for a parameter by using the `As` clause in its declaration.</span></span> <span data-ttu-id="0eae2-120">例如，以下函数接受字符串和整数。</span><span class="sxs-lookup"><span data-stu-id="0eae2-120">For example, the following function accepts a string and an integer.</span></span>  
  
 [!code-vb[VbVbcnProcedures#32](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#32)]  
  
 <span data-ttu-id="0eae2-121">如果类型检查开关（[Option Strict 语句](../../../../visual-basic/language-reference/statements/option-strict-statement.md)）为 `Off,` 则 `As` 子句是可选的，但如果有任何一个参数使用它，则所有参数都必须使用它。</span><span class="sxs-lookup"><span data-stu-id="0eae2-121">If the type checking switch ([Option Strict Statement](../../../../visual-basic/language-reference/statements/option-strict-statement.md)) is `Off,` the `As` clause is optional, except that if any one parameter uses it, all parameters must use it.</span></span> <span data-ttu-id="0eae2-122">如果 `On`类型检查，则所有过程参数都需要 `As` 子句。</span><span class="sxs-lookup"><span data-stu-id="0eae2-122">If type checking is `On`, the `As` clause is required for all procedure parameters.</span></span>  
  
 <span data-ttu-id="0eae2-123">如果调用代码需要提供的参数的数据类型与其对应参数的数据类型不同（例如 `Byte` 到 `String` 参数），则必须执行以下操作之一：</span><span class="sxs-lookup"><span data-stu-id="0eae2-123">If the calling code expects to supply an argument with a data type different from that of its corresponding parameter, such as `Byte` to a `String` parameter, it must do one of the following:</span></span>  
  
- <span data-ttu-id="0eae2-124">仅提供数据类型扩大到参数数据类型的自变量;</span><span class="sxs-lookup"><span data-stu-id="0eae2-124">Supply only arguments with data types that widen to the parameter data type;</span></span>  
  
- <span data-ttu-id="0eae2-125">将 `Option Strict Off` 设置为允许隐式收缩转换;或</span><span class="sxs-lookup"><span data-stu-id="0eae2-125">Set `Option Strict Off` to allow implicit narrowing conversions; or</span></span>  
  
- <span data-ttu-id="0eae2-126">使用转换关键字显式转换数据类型。</span><span class="sxs-lookup"><span data-stu-id="0eae2-126">Use a conversion keyword to explicitly convert the data type.</span></span>  
  
### <a name="type-parameters"></a><span data-ttu-id="0eae2-127">类型参数</span><span class="sxs-lookup"><span data-stu-id="0eae2-127">Type Parameters</span></span>  
 <span data-ttu-id="0eae2-128">*泛型过程*除了定义其正常参数外，还定义了一个或多个*类型参数*。</span><span class="sxs-lookup"><span data-stu-id="0eae2-128">A *generic procedure* also defines one or more *type parameters* in addition to its normal parameters.</span></span> <span data-ttu-id="0eae2-129">泛型过程允许调用代码在每次调用该过程时传递不同的数据类型，因此它可以根据每个调用的要求来定制数据类型。</span><span class="sxs-lookup"><span data-stu-id="0eae2-129">A generic procedure allows the calling code to pass different data types each time it calls the procedure, so it can tailor the data types to the requirements of each individual call.</span></span> <span data-ttu-id="0eae2-130">请参阅 [Generic Procedures in Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/generic-procedures.md)。</span><span class="sxs-lookup"><span data-stu-id="0eae2-130">See [Generic Procedures in Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/generic-procedures.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0eae2-131">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0eae2-131">See also</span></span>

- [<span data-ttu-id="0eae2-132">过程</span><span class="sxs-lookup"><span data-stu-id="0eae2-132">Procedures</span></span>](./index.md)
- [<span data-ttu-id="0eae2-133">Sub 过程</span><span class="sxs-lookup"><span data-stu-id="0eae2-133">Sub Procedures</span></span>](./sub-procedures.md)
- [<span data-ttu-id="0eae2-134">Function 过程</span><span class="sxs-lookup"><span data-stu-id="0eae2-134">Function Procedures</span></span>](./function-procedures.md)
- [<span data-ttu-id="0eae2-135">属性过程</span><span class="sxs-lookup"><span data-stu-id="0eae2-135">Property Procedures</span></span>](./property-procedures.md)
- [<span data-ttu-id="0eae2-136">运算符过程</span><span class="sxs-lookup"><span data-stu-id="0eae2-136">Operator Procedures</span></span>](./operator-procedures.md)
- [<span data-ttu-id="0eae2-137">如何：为过程定义参数</span><span class="sxs-lookup"><span data-stu-id="0eae2-137">How to: Define a Parameter for a Procedure</span></span>](./how-to-define-a-parameter-for-a-procedure.md)
- [<span data-ttu-id="0eae2-138">如何：将自变量传递给过程</span><span class="sxs-lookup"><span data-stu-id="0eae2-138">How to: Pass Arguments to a Procedure</span></span>](./how-to-pass-arguments-to-a-procedure.md)
- [<span data-ttu-id="0eae2-139">按值和按引用传递自变量</span><span class="sxs-lookup"><span data-stu-id="0eae2-139">Passing Arguments by Value and by Reference</span></span>](./passing-arguments-by-value-and-by-reference.md)
- [<span data-ttu-id="0eae2-140">过程重载</span><span class="sxs-lookup"><span data-stu-id="0eae2-140">Procedure Overloading</span></span>](./procedure-overloading.md)
- [<span data-ttu-id="0eae2-141">Visual Basic 中的类型转换</span><span class="sxs-lookup"><span data-stu-id="0eae2-141">Type Conversions in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)
