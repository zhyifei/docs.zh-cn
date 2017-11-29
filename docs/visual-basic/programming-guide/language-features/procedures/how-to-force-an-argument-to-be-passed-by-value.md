---
title: "如何：强制通过值传递自变量 (Visual Basic)"
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
- procedure arguments
- Visual Basic code, procedures
- arguments [Visual Basic], ByVal
- arguments [Visual Basic], passing by value
- procedure parameters
- procedures [Visual Basic], calling
- arguments [Visual Basic], in parentheses
- procedure arguments [Visual Basic], in parentheses
- arguments [Visual Basic], changing value
ms.assetid: 77b4f2d2-1055-4c2f-a521-874d1db86946
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: fdb2df7e114f49c23db9f5b322ca9dd32135ac88
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-force-an-argument-to-be-passed-by-value-visual-basic"></a><span data-ttu-id="10ceb-102">如何：强制通过值传递自变量 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="10ceb-102">How to: Force an Argument to Be Passed by Value (Visual Basic)</span></span>
<span data-ttu-id="10ceb-103">过程声明确定的传递机制。</span><span class="sxs-lookup"><span data-stu-id="10ceb-103">The procedure declaration determines the passing mechanism.</span></span> <span data-ttu-id="10ceb-104">如果在声明参数[ByRef](../../../../visual-basic/language-reference/modifiers/byref.md)，[!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]期望通过引用传递相应的自变量。</span><span class="sxs-lookup"><span data-stu-id="10ceb-104">If a parameter is declared [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md), [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] expects to pass the corresponding argument by reference.</span></span> <span data-ttu-id="10ceb-105">这允许更改基础中调用代码的自变量的编程元素的值的过程。</span><span class="sxs-lookup"><span data-stu-id="10ceb-105">This allows the procedure to change the value of the programming element underlying the argument in the calling code.</span></span> <span data-ttu-id="10ceb-106">如果你想要防止此类更改基础元素，则可以重写`ByRef`过程中的传递机制调用的自变量名称括在括号中。</span><span class="sxs-lookup"><span data-stu-id="10ceb-106">If you wish to protect the underlying element against such change, you can override the `ByRef` passing mechanism in the procedure call by enclosing the argument name in parentheses.</span></span> <span data-ttu-id="10ceb-107">除了括号之外的自变量列表的调用中，则这些括号。</span><span class="sxs-lookup"><span data-stu-id="10ceb-107">These parentheses are in addition to the parentheses enclosing the argument list in the call.</span></span>  
  
 <span data-ttu-id="10ceb-108">调用的代码不能重写[ByVal](../../../../visual-basic/language-reference/modifiers/byval.md)机制。</span><span class="sxs-lookup"><span data-stu-id="10ceb-108">The calling code cannot override a [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) mechanism.</span></span>  
  
### <a name="to-force-an-argument-to-be-passed-by-value"></a><span data-ttu-id="10ceb-109">若要强制通过值传递自变量</span><span class="sxs-lookup"><span data-stu-id="10ceb-109">To force an argument to be passed by value</span></span>  
  
-   <span data-ttu-id="10ceb-110">如果声明的相应参数`ByVal`在过程中，不需要执行任何其他步骤。</span><span class="sxs-lookup"><span data-stu-id="10ceb-110">If the corresponding parameter is declared `ByVal` in the procedure, you do not need to take any additional steps.</span></span> [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]<span data-ttu-id="10ceb-111">已希望按值传递自变量。</span><span class="sxs-lookup"><span data-stu-id="10ceb-111"> already expects to pass the argument by value.</span></span>  
  
-   <span data-ttu-id="10ceb-112">如果声明的相应参数`ByRef`在过程中，将括在过程调用中的括号中的自变量。</span><span class="sxs-lookup"><span data-stu-id="10ceb-112">If the corresponding parameter is declared `ByRef` in the procedure, enclose the argument in parentheses in the procedure call.</span></span>  
  
## <a name="example"></a><span data-ttu-id="10ceb-113">示例</span><span class="sxs-lookup"><span data-stu-id="10ceb-113">Example</span></span>  
 <span data-ttu-id="10ceb-114">下面的示例重写`ByRef`参数声明。</span><span class="sxs-lookup"><span data-stu-id="10ceb-114">The following example overrides a `ByRef` parameter declaration.</span></span> <span data-ttu-id="10ceb-115">强制的调用中`ByVal`，请注意两个级别的括号。</span><span class="sxs-lookup"><span data-stu-id="10ceb-115">In the call that forces `ByVal`, note the two levels of parentheses.</span></span>  
  
 [!code-vb[VbVbcnProcedures#39](./codesnippet/VisualBasic/how-to-force-an-argument-to-be-passed-by-value_1.vb)]  
  
 [!code-vb[VbVbcnProcedures#40](./codesnippet/VisualBasic/how-to-force-an-argument-to-be-passed-by-value_2.vb)]  
  
 <span data-ttu-id="10ceb-116">当`str`用自变量列表中的额外括号括起来`setNewString`过程不能更改在调用代码中，其值和`MsgBox`显示"无法替换如果传递 ByVal"。</span><span class="sxs-lookup"><span data-stu-id="10ceb-116">When `str` is enclosed in extra parentheses within the argument list, the `setNewString` procedure cannot change its value in the calling code, and `MsgBox` displays "Cannot be replaced if passed ByVal".</span></span> <span data-ttu-id="10ceb-117">当`str`不括在额外的括号内，则过程可以更改它，和`MsgBox`显示"This is inString 参数的一个新值"。</span><span class="sxs-lookup"><span data-stu-id="10ceb-117">When `str` is not enclosed in extra parentheses, the procedure can change it, and `MsgBox` displays "This is a new value for the inString argument."</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="10ceb-118">编译代码</span><span class="sxs-lookup"><span data-stu-id="10ceb-118">Compiling the Code</span></span>  
 <span data-ttu-id="10ceb-119">当通过引用传递的变量时，你必须使用`ByRef`关键字来指定此机制。</span><span class="sxs-lookup"><span data-stu-id="10ceb-119">When you pass a variable by reference, you must use the `ByRef` keyword to specify this mechanism.</span></span>  
  
 <span data-ttu-id="10ceb-120">中的默认值[!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]是按值传递自变量。</span><span class="sxs-lookup"><span data-stu-id="10ceb-120">The default in [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] is to pass arguments by value.</span></span> <span data-ttu-id="10ceb-121">但是，很好的编程做法包括[ByVal](../../../../visual-basic/language-reference/modifiers/byval.md)或[ByRef](../../../../visual-basic/language-reference/modifiers/byref.md)关键字后跟每个声明的参数。</span><span class="sxs-lookup"><span data-stu-id="10ceb-121">However, it is good programming practice to include either the [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) or [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md) keyword with every declared parameter.</span></span> <span data-ttu-id="10ceb-122">这使得你的代码易于阅读。</span><span class="sxs-lookup"><span data-stu-id="10ceb-122">This makes your code easier to read.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="10ceb-123">可靠编程</span><span class="sxs-lookup"><span data-stu-id="10ceb-123">Robust Programming</span></span>  
 <span data-ttu-id="10ceb-124">如果过程声明参数[ByRef](../../../../visual-basic/language-reference/modifiers/byref.md)，正确的执行代码的可能依赖于能够更改中调用代码的基础元素。</span><span class="sxs-lookup"><span data-stu-id="10ceb-124">If a procedure declares a parameter [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md), the correct execution of the code might depend on being able to change the underlying element in the calling code.</span></span> <span data-ttu-id="10ceb-125">如果调用代码重写此调用的机制，通过将实参括在括号内，或者如果它通过不可修改自变量，该过程不能更改基础元素。</span><span class="sxs-lookup"><span data-stu-id="10ceb-125">If the calling code overrides this calling mechanism by enclosing the argument in parentheses, or if it passes a nonmodifiable argument, the procedure cannot change the underlying element.</span></span> <span data-ttu-id="10ceb-126">这可能会产生意外的结果，调用代码中。</span><span class="sxs-lookup"><span data-stu-id="10ceb-126">This might produce unexpected results in the calling code.</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="10ceb-127">.NET Framework 安全性</span><span class="sxs-lookup"><span data-stu-id="10ceb-127">.NET Framework Security</span></span>  
 <span data-ttu-id="10ceb-128">允许一个过程来更改基础中调用代码的自变量的值始终没有潜在风险。</span><span class="sxs-lookup"><span data-stu-id="10ceb-128">There is always a potential risk in allowing a procedure to change the value underlying an argument in the calling code.</span></span> <span data-ttu-id="10ceb-129">请确保您希望此值可更改，并做好准备，然后再使用它的有效性检查它。</span><span class="sxs-lookup"><span data-stu-id="10ceb-129">Make sure you expect this value to be changed, and be prepared to check it for validity before using it.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="10ceb-130">另请参阅</span><span class="sxs-lookup"><span data-stu-id="10ceb-130">See Also</span></span>  
 [<span data-ttu-id="10ceb-131">过程</span><span class="sxs-lookup"><span data-stu-id="10ceb-131">Procedures</span></span>](./index.md)  
 [<span data-ttu-id="10ceb-132">过程参数和自变量</span><span class="sxs-lookup"><span data-stu-id="10ceb-132">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)  
 [<span data-ttu-id="10ceb-133">如何：将自变量传递给过程</span><span class="sxs-lookup"><span data-stu-id="10ceb-133">How to: Pass Arguments to a Procedure</span></span>](./how-to-pass-arguments-to-a-procedure.md)  
 [<span data-ttu-id="10ceb-134">按值和按引用传递自变量</span><span class="sxs-lookup"><span data-stu-id="10ceb-134">Passing Arguments by Value and by Reference</span></span>](./passing-arguments-by-value-and-by-reference.md)  
 [<span data-ttu-id="10ceb-135">可修改和不可修改自变量之间的差异</span><span class="sxs-lookup"><span data-stu-id="10ceb-135">Differences Between Modifiable and Nonmodifiable Arguments</span></span>](./differences-between-modifiable-and-nonmodifiable-arguments.md)  
 [<span data-ttu-id="10ceb-136">通过值传递自变量和通过引用传递自变量之间的差异</span><span class="sxs-lookup"><span data-stu-id="10ceb-136">Differences Between Passing an Argument By Value and By Reference</span></span>](./differences-between-passing-an-argument-by-value-and-by-reference.md)  
 [<span data-ttu-id="10ceb-137">如何：更改过程自变量的值</span><span class="sxs-lookup"><span data-stu-id="10ceb-137">How to: Change the Value of a Procedure Argument</span></span>](./how-to-change-the-value-of-a-procedure-argument.md)  
 [<span data-ttu-id="10ceb-138">如何：防止过程自变量的值被更改</span><span class="sxs-lookup"><span data-stu-id="10ceb-138">How to: Protect a Procedure Argument Against Value Changes</span></span>](./how-to-protect-a-procedure-argument-against-value-changes.md)  
 [<span data-ttu-id="10ceb-139">按位置和按名称传递自变量</span><span class="sxs-lookup"><span data-stu-id="10ceb-139">Passing Arguments by Position and by Name</span></span>](./passing-arguments-by-position-and-by-name.md)  
 [<span data-ttu-id="10ceb-140">值类型和引用类型</span><span class="sxs-lookup"><span data-stu-id="10ceb-140">Value Types and Reference Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)
