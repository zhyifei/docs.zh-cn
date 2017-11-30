---
title: "按位置和名称传递自变量 (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- arguments [Visual Basic], passing by name
- procedures [Visual Basic], arguments
- := passing arguments
- procedure arguments
- Visual Basic code, procedures
- named arguments [Visual Basic], passing arguments
- arguments [Visual Basic], passing by position
- Function procedures [Visual Basic], passing arguments
- named parameters [Visual Basic], passing arguments
- named arguments
- passing parameters [Visual Basic], named parameter arguments
- passing parameters [Visual Basic], by position
- procedures [Visual Basic], calling
- named parameters
- Sub procedures [Visual Basic], passing arguments
- argument passing
- passing parameters [Visual Basic], by name
- argument passing [Visual Basic], by position
- arguments [Visual Basic], listing by name
ms.assetid: 1ad7358f-1da9-48da-a95b-f3c7ed41eff3
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 164f69fcf23049441a0acbe05058c792d5363a03
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="passing-arguments-by-position-and-by-name-visual-basic"></a><span data-ttu-id="68897-102">按位置和名称传递自变量 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="68897-102">Passing Arguments by Position and by Name (Visual Basic)</span></span>
<span data-ttu-id="68897-103">当调用`Sub`或`Function`过程中，你可以将参数传递*按位置*— 在过程定义中出现的顺序 — 或将它们传递*按名称*，而无需考虑位置。</span><span class="sxs-lookup"><span data-stu-id="68897-103">When you call a `Sub` or `Function` procedure, you can pass arguments *by position* — in the order in which they appear in the procedure's definition — or you can pass them *by name*, without regard to position.</span></span>  
  
 <span data-ttu-id="68897-104">当你按名称传递自变量时，你指定参数的声明名称后跟冒号和等号 (`:=`) 后, 跟自变量值。</span><span class="sxs-lookup"><span data-stu-id="68897-104">When you pass an argument by name, you specify the argument's declared name followed by a colon and an equal sign (`:=`), followed by the argument value.</span></span> <span data-ttu-id="68897-105">你可以提供命名自变量的任何顺序。</span><span class="sxs-lookup"><span data-stu-id="68897-105">You can supply named arguments in any order.</span></span>  
  
 <span data-ttu-id="68897-106">例如，以下`Sub`过程使用三个参数：</span><span class="sxs-lookup"><span data-stu-id="68897-106">For example, the following `Sub` procedure takes three arguments:</span></span>  
  
 [!code-vb[VbVbcnProcedures#41](./codesnippet/VisualBasic/passing-arguments-by-position-and-by-name_1.vb)]  
  
 <span data-ttu-id="68897-107">在调用此过程时，你可以提供的自变量按位置、 按名称，或通过使用这两者的混合。</span><span class="sxs-lookup"><span data-stu-id="68897-107">When you call this procedure, you can supply the arguments by position, by name, or by using a mixture of both.</span></span>  
  
## <a name="passing-arguments-by-position"></a><span data-ttu-id="68897-108">按位置传递自变量</span><span class="sxs-lookup"><span data-stu-id="68897-108">Passing Arguments by Position</span></span>  
 <span data-ttu-id="68897-109">您可以调用过程`studentInfo`参数传递的位置并且用逗号分隔，如下面的示例中所示：</span><span class="sxs-lookup"><span data-stu-id="68897-109">You can call the procedure `studentInfo` with its arguments passed by position and delimited by commas, as shown in the following example:</span></span>  
  
 [!code-vb[VbVbcnProcedures#42](./codesnippet/VisualBasic/passing-arguments-by-position-and-by-name_2.vb)]  
  
 <span data-ttu-id="68897-110">如果省略可选的参数位置自变量列表中，你必须保留它用逗号分隔的位置。</span><span class="sxs-lookup"><span data-stu-id="68897-110">If you omit an optional argument in a positional argument list, you must hold its place with a comma.</span></span> <span data-ttu-id="68897-111">下面的示例调用`studentInfo`而无需`age`自变量：</span><span class="sxs-lookup"><span data-stu-id="68897-111">The following example calls `studentInfo` without the `age` argument:</span></span>  
  
 [!code-vb[VbVbcnProcedures#43](./codesnippet/VisualBasic/passing-arguments-by-position-and-by-name_3.vb)]  
  
## <a name="passing-arguments-by-name"></a><span data-ttu-id="68897-112">按名称传递自变量</span><span class="sxs-lookup"><span data-stu-id="68897-112">Passing Arguments by Name</span></span>  
 <span data-ttu-id="68897-113">或者，可以调用`studentInfo`按名称传递自变量也用逗号分隔，如下面的示例中所示：</span><span class="sxs-lookup"><span data-stu-id="68897-113">Alternatively, you can call `studentInfo` with the arguments passed by name, also delimited by commas, as shown in the following example:</span></span>  
  
 [!code-vb[VbVbcnProcedures#44](./codesnippet/VisualBasic/passing-arguments-by-position-and-by-name_4.vb)]  
  
## <a name="mixing-arguments-by-position-and-by-name"></a><span data-ttu-id="68897-114">混合自变量按位置和名称</span><span class="sxs-lookup"><span data-stu-id="68897-114">Mixing Arguments by Position and by Name</span></span>  
 <span data-ttu-id="68897-115">你可以提供自变量的位置和名称的单一过程调用中，如下面的示例中所示：</span><span class="sxs-lookup"><span data-stu-id="68897-115">You can supply arguments both by position and by name in a single procedure call, as shown in the following example:</span></span>  
  
 [!code-vb[VbVbcnProcedures#45](./codesnippet/VisualBasic/passing-arguments-by-position-and-by-name_5.vb)]  
  
 <span data-ttu-id="68897-116">在前面的示例中，没有多余的逗号是保存的省略的位置所需`age`自变量，因为`birth`按名称传递了。</span><span class="sxs-lookup"><span data-stu-id="68897-116">In the preceding example, no extra comma is necessary to hold the place of the omitted `age` argument, since `birth` is passed by name.</span></span>  
  
 <span data-ttu-id="68897-117">自变量提供的混合的位置和名称、 位置自变量时，都必须放在第一个。</span><span class="sxs-lookup"><span data-stu-id="68897-117">When you supply arguments by a mixture of position and name, the positional arguments must all come first.</span></span> <span data-ttu-id="68897-118">一旦你按名称提供自变量，其余的自变量都必须是按名称。</span><span class="sxs-lookup"><span data-stu-id="68897-118">Once you supply an argument by name, the remaining arguments must all be by name.</span></span>  
  
## <a name="supplying-optional-arguments-by-name"></a><span data-ttu-id="68897-119">提供按名称的可选自变量</span><span class="sxs-lookup"><span data-stu-id="68897-119">Supplying Optional Arguments by Name</span></span>  
 <span data-ttu-id="68897-120">在调用了具有多个可选参数的过程时，按名称传递自变量是特别有用。</span><span class="sxs-lookup"><span data-stu-id="68897-120">Passing arguments by name is especially useful when you call a procedure that has more than one optional argument.</span></span> <span data-ttu-id="68897-121">如果按名称提供自变量，你不需要使用连续的逗号来表示缺少位置自变量。</span><span class="sxs-lookup"><span data-stu-id="68897-121">If you supply arguments by name, you do not have to use consecutive commas to denote missing positional arguments.</span></span> <span data-ttu-id="68897-122">按名称传递自变量还可以更轻松地跟踪的哪些参数将传递和你省略哪些功能。</span><span class="sxs-lookup"><span data-stu-id="68897-122">Passing arguments by name also makes it easier to keep track of which arguments you are passing and which ones you are omitting.</span></span>  
  
## <a name="restrictions-on-supplying-arguments-by-name"></a><span data-ttu-id="68897-123">提供自变量按名称的限制</span><span class="sxs-lookup"><span data-stu-id="68897-123">Restrictions on Supplying Arguments by Name</span></span>  
 <span data-ttu-id="68897-124">你不能按名称来避免输入所需的参数传递自变量。</span><span class="sxs-lookup"><span data-stu-id="68897-124">You cannot pass arguments by name to avoid entering required arguments.</span></span> <span data-ttu-id="68897-125">可以省略仅的可选自变量。</span><span class="sxs-lookup"><span data-stu-id="68897-125">You can omit only the optional arguments.</span></span>  
  
 <span data-ttu-id="68897-126">你不能按名称传递参数数组。</span><span class="sxs-lookup"><span data-stu-id="68897-126">You cannot pass a parameter array by name.</span></span> <span data-ttu-id="68897-127">这是因为在调用过程时，你提供的参数数组中，逗号分隔的参数数量不确定，并且编译器不能将多个自变量与单个名称关联。</span><span class="sxs-lookup"><span data-stu-id="68897-127">This is because when you call the procedure, you supply an indefinite number of comma-separated arguments for the parameter array, and the compiler cannot associate more than one argument with a single name.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="68897-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="68897-128">See Also</span></span>  
 [<span data-ttu-id="68897-129">过程</span><span class="sxs-lookup"><span data-stu-id="68897-129">Procedures</span></span>](./index.md)  
 [<span data-ttu-id="68897-130">过程参数和自变量</span><span class="sxs-lookup"><span data-stu-id="68897-130">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)  
 [<span data-ttu-id="68897-131">如何：将自变量传递给过程</span><span class="sxs-lookup"><span data-stu-id="68897-131">How to: Pass Arguments to a Procedure</span></span>](./how-to-pass-arguments-to-a-procedure.md)  
 [<span data-ttu-id="68897-132">按值和按引用传递自变量</span><span class="sxs-lookup"><span data-stu-id="68897-132">Passing Arguments by Value and by Reference</span></span>](./passing-arguments-by-value-and-by-reference.md)  
 [<span data-ttu-id="68897-133">可选参数</span><span class="sxs-lookup"><span data-stu-id="68897-133">Optional Parameters</span></span>](./optional-parameters.md)  
 [<span data-ttu-id="68897-134">参数数组</span><span class="sxs-lookup"><span data-stu-id="68897-134">Parameter Arrays</span></span>](./parameter-arrays.md)  
 [<span data-ttu-id="68897-135">Optional</span><span class="sxs-lookup"><span data-stu-id="68897-135">Optional</span></span>](../../../../visual-basic/language-reference/modifiers/optional.md)  
 [<span data-ttu-id="68897-136">ParamArray</span><span class="sxs-lookup"><span data-stu-id="68897-136">ParamArray</span></span>](../../../../visual-basic/language-reference/modifiers/paramarray.md)
