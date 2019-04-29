---
title: 过程参数和自变量 (Visual Basic)
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
ms.openlocfilehash: 80065cabcacdcf44b04fef7bacb978ca9c8077ae
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61791895"
---
# <a name="procedure-parameters-and-arguments-visual-basic"></a><span data-ttu-id="97f14-102">过程参数和自变量 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="97f14-102">Procedure Parameters and Arguments (Visual Basic)</span></span>
<span data-ttu-id="97f14-103">在大多数情况下，一个过程需要一些信息已在其中调用它的情况。</span><span class="sxs-lookup"><span data-stu-id="97f14-103">In most cases, a procedure needs some information about the circumstances in which it has been called.</span></span> <span data-ttu-id="97f14-104">执行重复或共享任务的过程为每个调用使用不同的信息。</span><span class="sxs-lookup"><span data-stu-id="97f14-104">A procedure that performs repeated or shared tasks uses different information for each call.</span></span> <span data-ttu-id="97f14-105">此信息包括变量、 常量和表达式在调用时传递给该过程。</span><span class="sxs-lookup"><span data-stu-id="97f14-105">This information consists of variables, constants, and expressions that you pass to the procedure when you call it.</span></span>  
  
 <span data-ttu-id="97f14-106">一个*参数*表示一个值，此过程需要您提供时调用它。</span><span class="sxs-lookup"><span data-stu-id="97f14-106">A *parameter* represents a value that the procedure expects you to supply when you call it.</span></span> <span data-ttu-id="97f14-107">该过程的声明定义其参数。</span><span class="sxs-lookup"><span data-stu-id="97f14-107">The procedure's declaration defines its parameters.</span></span>  
  
 <span data-ttu-id="97f14-108">你可以定义不使用参数、 一个参数，或者多个过程。</span><span class="sxs-lookup"><span data-stu-id="97f14-108">You can define a procedure with no parameters, one parameter, or more than one.</span></span> <span data-ttu-id="97f14-109">指定的参数在过程定义的一部分被称作*参数列表*。</span><span class="sxs-lookup"><span data-stu-id="97f14-109">The part of the procedure definition that specifies the parameters is called the *parameter list*.</span></span>  
  
 <span data-ttu-id="97f14-110">*自变量*调用过程时对过程参数表示所提供的值。</span><span class="sxs-lookup"><span data-stu-id="97f14-110">An *argument* represents the value you supply to a procedure parameter when you call the procedure.</span></span> <span data-ttu-id="97f14-111">当调用该过程时，调用代码将提供参数。</span><span class="sxs-lookup"><span data-stu-id="97f14-111">The calling code supplies the arguments when it calls the procedure.</span></span> <span data-ttu-id="97f14-112">指定的参数在过程调用的一部分被称作*自变量列表*。</span><span class="sxs-lookup"><span data-stu-id="97f14-112">The part of the procedure call that specifies the arguments is called the *argument list*.</span></span>  
  
 <span data-ttu-id="97f14-113">下图显示了代码调用该过程`safeSquareRoot`从两个不同的位置。</span><span class="sxs-lookup"><span data-stu-id="97f14-113">The following illustration shows code calling the procedure `safeSquareRoot` from two different places.</span></span> <span data-ttu-id="97f14-114">第一次调用将变量的值传递`x`(4.0) 给参数`number`，和中的返回值`root`(2.0) 赋给变量`y`。</span><span class="sxs-lookup"><span data-stu-id="97f14-114">The first call passes the value of the variable `x` (4.0) to the parameter `number`, and the return value in `root` (2.0) is assigned to the variable `y`.</span></span> <span data-ttu-id="97f14-115">第二次调用将传递到的文本值 9.0 `number`，并将返回值 (3.0) 赋给变量`z`。</span><span class="sxs-lookup"><span data-stu-id="97f14-115">The second call passes the literal value 9.0 to `number`, and assigns the return value (3.0) to variable `z`.</span></span>  
  
 ![显示了将自变量传递给参数的关系图](./media/procedure-parameters-and-arguments/pass-argument-parameter.gif)  
  
 <span data-ttu-id="97f14-117">有关详细信息，请参阅[差异之间形参和实参](./differences-between-parameters-and-arguments.md)。</span><span class="sxs-lookup"><span data-stu-id="97f14-117">For more information, see [Differences Between Parameters and Arguments](./differences-between-parameters-and-arguments.md).</span></span>  
  
## <a name="parameter-data-type"></a><span data-ttu-id="97f14-118">参数数据类型</span><span class="sxs-lookup"><span data-stu-id="97f14-118">Parameter Data Type</span></span>  
 <span data-ttu-id="97f14-119">使用定义为参数的数据类型`As`其声明中的子句。</span><span class="sxs-lookup"><span data-stu-id="97f14-119">You define a data type for a parameter by using the `As` clause in its declaration.</span></span> <span data-ttu-id="97f14-120">例如，以下函数接受一个字符串和整数。</span><span class="sxs-lookup"><span data-stu-id="97f14-120">For example, the following function accepts a string and an integer.</span></span>  
  
 [!code-vb[VbVbcnProcedures#32](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#32)]  
  
 <span data-ttu-id="97f14-121">如果类型检查开关 ([Option Strict Statement](../../../../visual-basic/language-reference/statements/option-strict-statement.md)) 是`Off,``As`子句是可选的只不过如果任一参数使用它，则所有参数必须都使用它。</span><span class="sxs-lookup"><span data-stu-id="97f14-121">If the type checking switch ([Option Strict Statement](../../../../visual-basic/language-reference/statements/option-strict-statement.md)) is `Off,` the `As` clause is optional, except that if any one parameter uses it, all parameters must use it.</span></span> <span data-ttu-id="97f14-122">如果类型检查`On`，则`As`子句是必需的所有过程的参数。</span><span class="sxs-lookup"><span data-stu-id="97f14-122">If type checking is `On`, the `As` clause is required for all procedure parameters.</span></span>  
  
 <span data-ttu-id="97f14-123">如果调用代码需要具有数据类型不同于其相应的参数，如提供参数`Byte`到`String`参数，它必须执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="97f14-123">If the calling code expects to supply an argument with a data type different from that of its corresponding parameter, such as `Byte` to a `String` parameter, it must do one of the following:</span></span>  
  
- <span data-ttu-id="97f14-124">提供唯一的参数和扩大到参数的数据类型; 的数据类型</span><span class="sxs-lookup"><span data-stu-id="97f14-124">Supply only arguments with data types that widen to the parameter data type;</span></span>  
  
- <span data-ttu-id="97f14-125">设置`Option Strict Off`以允许隐式收缩转换; 或</span><span class="sxs-lookup"><span data-stu-id="97f14-125">Set `Option Strict Off` to allow implicit narrowing conversions; or</span></span>  
  
- <span data-ttu-id="97f14-126">使用转换关键字可以显式转换的数据类型。</span><span class="sxs-lookup"><span data-stu-id="97f14-126">Use a conversion keyword to explicitly convert the data type.</span></span>  
  
### <a name="type-parameters"></a><span data-ttu-id="97f14-127">类型参数</span><span class="sxs-lookup"><span data-stu-id="97f14-127">Type Parameters</span></span>  
 <span data-ttu-id="97f14-128">一个*泛型过程*还定义了一个或多个*类型参数*除了其正常参数。</span><span class="sxs-lookup"><span data-stu-id="97f14-128">A *generic procedure* also defines one or more *type parameters* in addition to its normal parameters.</span></span> <span data-ttu-id="97f14-129">泛型过程，调用代码，以便它可以调整每个调用的要求的数据类型，它调用过程时，每次传递不同的数据类型。</span><span class="sxs-lookup"><span data-stu-id="97f14-129">A generic procedure allows the calling code to pass different data types each time it calls the procedure, so it can tailor the data types to the requirements of each individual call.</span></span> <span data-ttu-id="97f14-130">请参阅 [Generic Procedures in Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/generic-procedures.md)。</span><span class="sxs-lookup"><span data-stu-id="97f14-130">See [Generic Procedures in Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/generic-procedures.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="97f14-131">请参阅</span><span class="sxs-lookup"><span data-stu-id="97f14-131">See also</span></span>

- [<span data-ttu-id="97f14-132">过程</span><span class="sxs-lookup"><span data-stu-id="97f14-132">Procedures</span></span>](./index.md)
- [<span data-ttu-id="97f14-133">Sub 过程</span><span class="sxs-lookup"><span data-stu-id="97f14-133">Sub Procedures</span></span>](./sub-procedures.md)
- [<span data-ttu-id="97f14-134">Function 过程</span><span class="sxs-lookup"><span data-stu-id="97f14-134">Function Procedures</span></span>](./function-procedures.md)
- [<span data-ttu-id="97f14-135">属性过程</span><span class="sxs-lookup"><span data-stu-id="97f14-135">Property Procedures</span></span>](./property-procedures.md)
- [<span data-ttu-id="97f14-136">运算符过程</span><span class="sxs-lookup"><span data-stu-id="97f14-136">Operator Procedures</span></span>](./operator-procedures.md)
- [<span data-ttu-id="97f14-137">如何：为过程定义参数</span><span class="sxs-lookup"><span data-stu-id="97f14-137">How to: Define a Parameter for a Procedure</span></span>](./how-to-define-a-parameter-for-a-procedure.md)
- [<span data-ttu-id="97f14-138">如何：将参数传递给过程</span><span class="sxs-lookup"><span data-stu-id="97f14-138">How to: Pass Arguments to a Procedure</span></span>](./how-to-pass-arguments-to-a-procedure.md)
- [<span data-ttu-id="97f14-139">按值和按引用传递自变量</span><span class="sxs-lookup"><span data-stu-id="97f14-139">Passing Arguments by Value and by Reference</span></span>](./passing-arguments-by-value-and-by-reference.md)
- [<span data-ttu-id="97f14-140">过程重载</span><span class="sxs-lookup"><span data-stu-id="97f14-140">Procedure Overloading</span></span>](./procedure-overloading.md)
- [<span data-ttu-id="97f14-141">在 Visual Basic 中的类型转换</span><span class="sxs-lookup"><span data-stu-id="97f14-141">Type Conversions in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)
