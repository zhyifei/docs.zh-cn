---
title: "参数和自变量之间的差异 (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- procedures [Visual Basic], arguments
- procedures [Visual Basic], parameters
- parameters [Visual Basic], and arguments
- procedure arguments
- Visual Basic code, procedures
- arguments [Visual Basic], and parameters
- procedure parameters
- parameters [Visual Basic], definition
ms.assetid: c237c056-74f4-4749-9f2c-15864f139a31
caps.latest.revision: "18"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: b6613c64a24ef18239422b69f8b5320eadc95b92
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="differences-between-parameters-and-arguments-visual-basic"></a><span data-ttu-id="3e16f-102">参数和自变量之间的差异 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3e16f-102">Differences Between Parameters and Arguments (Visual Basic)</span></span>
<span data-ttu-id="3e16f-103">在大多数情况下中的过程必须具有已在其中调用它的情况有关的一些信息。</span><span class="sxs-lookup"><span data-stu-id="3e16f-103">In most cases, a procedure must have some information about the circumstances in which it has been called.</span></span> <span data-ttu-id="3e16f-104">执行重复或共享任务过程每个调用使用不同的信息。</span><span class="sxs-lookup"><span data-stu-id="3e16f-104">A procedure that performs repeated or shared tasks uses different information for each call.</span></span> <span data-ttu-id="3e16f-105">此信息包含变量、 常量和调用它时传递给过程的表达式。</span><span class="sxs-lookup"><span data-stu-id="3e16f-105">This information consists of variables, constants, and expressions that you pass to the procedure when you call it.</span></span>  
  
 <span data-ttu-id="3e16f-106">此将信息传递给该过程，为过程所定义*参数*，然后调用代码将传递*参数*给该参数。</span><span class="sxs-lookup"><span data-stu-id="3e16f-106">To communicate this information to the procedure, the procedure defines a *parameter*, and the calling code passes an *argument* to that parameter.</span></span> <span data-ttu-id="3e16f-107">你可以将参数作为一个停车和当作一辆汽车的自变量。</span><span class="sxs-lookup"><span data-stu-id="3e16f-107">You can think of the parameter as a parking space and the argument as an automobile.</span></span> <span data-ttu-id="3e16f-108">就像不同的汽车可以在不同时间停放停车空间，调用代码可以传递不同的自变量相同的参数到每次调用过程时。</span><span class="sxs-lookup"><span data-stu-id="3e16f-108">Just as different automobiles can park in a parking space at different times, the calling code can pass a different argument to the same parameter every time that it calls the procedure.</span></span>  
  
## <a name="parameters"></a><span data-ttu-id="3e16f-109">参数</span><span class="sxs-lookup"><span data-stu-id="3e16f-109">Parameters</span></span>  
 <span data-ttu-id="3e16f-110">A*参数*表示过程希望在调用它时传递的值。</span><span class="sxs-lookup"><span data-stu-id="3e16f-110">A *parameter* represents a value that the procedure expects you to pass when you call it.</span></span> <span data-ttu-id="3e16f-111">过程声明定义其参数。</span><span class="sxs-lookup"><span data-stu-id="3e16f-111">The procedure's declaration defines its parameters.</span></span>  
  
 <span data-ttu-id="3e16f-112">在定义`Function`或`Sub`过程，你指定*参数列表*直接在过程名称后面的括号中。</span><span class="sxs-lookup"><span data-stu-id="3e16f-112">When you define a `Function` or `Sub` procedure, you specify a *parameter list* in parentheses immediately following the procedure name.</span></span> <span data-ttu-id="3e16f-113">对于每个参数，您可以指定名称、 数据类型和传递机制 ([ByVal](../../../../visual-basic/language-reference/modifiers/byval.md)或[ByRef](../../../../visual-basic/language-reference/modifiers/byref.md))。</span><span class="sxs-lookup"><span data-stu-id="3e16f-113">For each parameter, you specify a name, a data type, and a passing mechanism ([ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) or [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md)).</span></span> <span data-ttu-id="3e16f-114">您还可以指示参数是可选。</span><span class="sxs-lookup"><span data-stu-id="3e16f-114">You can also indicate that a parameter is optional.</span></span> <span data-ttu-id="3e16f-115">这意味着调用的代码不需要传递的值。</span><span class="sxs-lookup"><span data-stu-id="3e16f-115">This means that the calling code does not have to pass a value for it.</span></span>  
  
 <span data-ttu-id="3e16f-116">每个参数的名称用作*局部变量*过程中。</span><span class="sxs-lookup"><span data-stu-id="3e16f-116">The name of each parameter serves as a *local variable* in the procedure.</span></span> <span data-ttu-id="3e16f-117">你使用的参数名称相同的方式使用任何其他变量。</span><span class="sxs-lookup"><span data-stu-id="3e16f-117">You use the parameter name the same way you use any other variable.</span></span>  
  
## <a name="arguments"></a><span data-ttu-id="3e16f-118">参数</span><span class="sxs-lookup"><span data-stu-id="3e16f-118">Arguments</span></span>  
 <span data-ttu-id="3e16f-119">*参数*表示在调用过程时传递给过程参数的值。</span><span class="sxs-lookup"><span data-stu-id="3e16f-119">An *argument* represents the value that you pass to a procedure parameter when you call the procedure.</span></span> <span data-ttu-id="3e16f-120">在调用该过程时，调用代码将提供自变量。</span><span class="sxs-lookup"><span data-stu-id="3e16f-120">The calling code supplies the arguments when it calls the procedure.</span></span>  
  
 <span data-ttu-id="3e16f-121">当调用`Function`或`Sub`过程，包括*自变量列表*直接在过程名称后面的括号中。</span><span class="sxs-lookup"><span data-stu-id="3e16f-121">When you call a `Function` or `Sub` procedure, you include an *argument list* in parentheses immediately following the procedure name.</span></span> <span data-ttu-id="3e16f-122">每个自变量对应于列表中的相同位置中的参数。</span><span class="sxs-lookup"><span data-stu-id="3e16f-122">Each argument corresponds to the parameter in the same position in the list.</span></span>  
  
 <span data-ttu-id="3e16f-123">与参数定义自变量没有名称。</span><span class="sxs-lookup"><span data-stu-id="3e16f-123">In contrast to parameter definition, arguments do not have names.</span></span> <span data-ttu-id="3e16f-124">每个自变量是一个表达式，它可以包含零个或多个变量、 常量和文本。</span><span class="sxs-lookup"><span data-stu-id="3e16f-124">Each argument is an expression, which can contain zero or more variables, constants, and literals.</span></span> <span data-ttu-id="3e16f-125">计算的表达式的数据类型通常应匹配定义的相应参数的数据类型，并在任何情况下必须能够转换为参数类型。</span><span class="sxs-lookup"><span data-stu-id="3e16f-125">The data type of the evaluated expression should typically match the data type defined for the corresponding parameter, and in any case it must be convertible to the parameter type.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3e16f-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3e16f-126">See Also</span></span>  
 [<span data-ttu-id="3e16f-127">过程</span><span class="sxs-lookup"><span data-stu-id="3e16f-127">Procedures</span></span>](./index.md)  
 [<span data-ttu-id="3e16f-128">Sub 过程</span><span class="sxs-lookup"><span data-stu-id="3e16f-128">Sub Procedures</span></span>](./sub-procedures.md)  
 [<span data-ttu-id="3e16f-129">Function 过程</span><span class="sxs-lookup"><span data-stu-id="3e16f-129">Function Procedures</span></span>](./function-procedures.md)  
 [<span data-ttu-id="3e16f-130">属性过程</span><span class="sxs-lookup"><span data-stu-id="3e16f-130">Property Procedures</span></span>](./property-procedures.md)  
 [<span data-ttu-id="3e16f-131">运算符过程</span><span class="sxs-lookup"><span data-stu-id="3e16f-131">Operator Procedures</span></span>](./operator-procedures.md)  
 [<span data-ttu-id="3e16f-132">如何：为过程定义参数</span><span class="sxs-lookup"><span data-stu-id="3e16f-132">How to: Define a Parameter for a Procedure</span></span>](./how-to-define-a-parameter-for-a-procedure.md)  
 [<span data-ttu-id="3e16f-133">如何：将自变量传递给过程</span><span class="sxs-lookup"><span data-stu-id="3e16f-133">How to: Pass Arguments to a Procedure</span></span>](./how-to-pass-arguments-to-a-procedure.md)  
 [<span data-ttu-id="3e16f-134">按值和按引用传递自变量</span><span class="sxs-lookup"><span data-stu-id="3e16f-134">Passing Arguments by Value and by Reference</span></span>](./passing-arguments-by-value-and-by-reference.md)  
 [<span data-ttu-id="3e16f-135">递归过程</span><span class="sxs-lookup"><span data-stu-id="3e16f-135">Recursive Procedures</span></span>](./recursive-procedures.md)  
 [<span data-ttu-id="3e16f-136">过程重载</span><span class="sxs-lookup"><span data-stu-id="3e16f-136">Procedure Overloading</span></span>](./procedure-overloading.md)
