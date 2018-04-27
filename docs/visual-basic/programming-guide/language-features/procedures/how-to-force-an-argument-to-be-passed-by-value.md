---
title: 如何：强制通过值传递自变量 (Visual Basic)
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
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
caps.latest.revision: 16
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 30f5e5fe7b9c92f90673dc99a0e299136a38305b
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-force-an-argument-to-be-passed-by-value-visual-basic"></a><span data-ttu-id="d947b-102">如何：强制通过值传递自变量 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d947b-102">How to: Force an Argument to Be Passed by Value (Visual Basic)</span></span>
<span data-ttu-id="d947b-103">过程声明确定的传递机制。</span><span class="sxs-lookup"><span data-stu-id="d947b-103">The procedure declaration determines the passing mechanism.</span></span> <span data-ttu-id="d947b-104">如果在声明参数[ByRef](../../../../visual-basic/language-reference/modifiers/byref.md)，Visual Basic 期望通过引用传递相应的自变量。</span><span class="sxs-lookup"><span data-stu-id="d947b-104">If a parameter is declared [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md), Visual Basic expects to pass the corresponding argument by reference.</span></span> <span data-ttu-id="d947b-105">这允许更改基础中调用代码的自变量的编程元素的值的过程。</span><span class="sxs-lookup"><span data-stu-id="d947b-105">This allows the procedure to change the value of the programming element underlying the argument in the calling code.</span></span> <span data-ttu-id="d947b-106">如果你想要防止此类更改基础元素，则可以重写`ByRef`过程中的传递机制调用的自变量名称括在括号中。</span><span class="sxs-lookup"><span data-stu-id="d947b-106">If you wish to protect the underlying element against such change, you can override the `ByRef` passing mechanism in the procedure call by enclosing the argument name in parentheses.</span></span> <span data-ttu-id="d947b-107">除了括号之外的自变量列表的调用中，则这些括号。</span><span class="sxs-lookup"><span data-stu-id="d947b-107">These parentheses are in addition to the parentheses enclosing the argument list in the call.</span></span>  
  
 <span data-ttu-id="d947b-108">调用的代码不能重写[ByVal](../../../../visual-basic/language-reference/modifiers/byval.md)机制。</span><span class="sxs-lookup"><span data-stu-id="d947b-108">The calling code cannot override a [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) mechanism.</span></span>  
  
### <a name="to-force-an-argument-to-be-passed-by-value"></a><span data-ttu-id="d947b-109">若要强制通过值传递自变量</span><span class="sxs-lookup"><span data-stu-id="d947b-109">To force an argument to be passed by value</span></span>  
  
-   <span data-ttu-id="d947b-110">如果声明的相应参数`ByVal`在过程中，不需要执行任何其他步骤。</span><span class="sxs-lookup"><span data-stu-id="d947b-110">If the corresponding parameter is declared `ByVal` in the procedure, you do not need to take any additional steps.</span></span> <span data-ttu-id="d947b-111">Visual Basic 已希望按值传递自变量。</span><span class="sxs-lookup"><span data-stu-id="d947b-111">Visual Basic already expects to pass the argument by value.</span></span>  
  
-   <span data-ttu-id="d947b-112">如果声明的相应参数`ByRef`在过程中，将括在过程调用中的括号中的自变量。</span><span class="sxs-lookup"><span data-stu-id="d947b-112">If the corresponding parameter is declared `ByRef` in the procedure, enclose the argument in parentheses in the procedure call.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d947b-113">示例</span><span class="sxs-lookup"><span data-stu-id="d947b-113">Example</span></span>  
 <span data-ttu-id="d947b-114">下面的示例重写`ByRef`参数声明。</span><span class="sxs-lookup"><span data-stu-id="d947b-114">The following example overrides a `ByRef` parameter declaration.</span></span> <span data-ttu-id="d947b-115">强制的调用中`ByVal`，请注意两个级别的括号。</span><span class="sxs-lookup"><span data-stu-id="d947b-115">In the call that forces `ByVal`, note the two levels of parentheses.</span></span>  
  
 [!code-vb[VbVbcnProcedures#39](./codesnippet/VisualBasic/how-to-force-an-argument-to-be-passed-by-value_1.vb)]  
  
 [!code-vb[VbVbcnProcedures#40](./codesnippet/VisualBasic/how-to-force-an-argument-to-be-passed-by-value_2.vb)]  
  
 <span data-ttu-id="d947b-116">当`str`用自变量列表中的额外括号括起来`setNewString`过程不能更改在调用代码中，其值和`MsgBox`显示"无法替换如果传递 ByVal"。</span><span class="sxs-lookup"><span data-stu-id="d947b-116">When `str` is enclosed in extra parentheses within the argument list, the `setNewString` procedure cannot change its value in the calling code, and `MsgBox` displays "Cannot be replaced if passed ByVal".</span></span> <span data-ttu-id="d947b-117">当`str`不括在额外的括号内，则过程可以更改它，和`MsgBox`显示"This is inString 参数的一个新值"。</span><span class="sxs-lookup"><span data-stu-id="d947b-117">When `str` is not enclosed in extra parentheses, the procedure can change it, and `MsgBox` displays "This is a new value for the inString argument."</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="d947b-118">编译代码</span><span class="sxs-lookup"><span data-stu-id="d947b-118">Compiling the Code</span></span>  
 <span data-ttu-id="d947b-119">当通过引用传递的变量时，你必须使用`ByRef`关键字来指定此机制。</span><span class="sxs-lookup"><span data-stu-id="d947b-119">When you pass a variable by reference, you must use the `ByRef` keyword to specify this mechanism.</span></span>  
  
 <span data-ttu-id="d947b-120">Visual Basic 中的默认值是通过值传递自变量。</span><span class="sxs-lookup"><span data-stu-id="d947b-120">The default in Visual Basic is to pass arguments by value.</span></span> <span data-ttu-id="d947b-121">但是，很好的编程做法包括[ByVal](../../../../visual-basic/language-reference/modifiers/byval.md)或[ByRef](../../../../visual-basic/language-reference/modifiers/byref.md)关键字后跟每个声明的参数。</span><span class="sxs-lookup"><span data-stu-id="d947b-121">However, it is good programming practice to include either the [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) or [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md) keyword with every declared parameter.</span></span> <span data-ttu-id="d947b-122">这使得你的代码易于阅读。</span><span class="sxs-lookup"><span data-stu-id="d947b-122">This makes your code easier to read.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="d947b-123">可靠编程</span><span class="sxs-lookup"><span data-stu-id="d947b-123">Robust Programming</span></span>  
 <span data-ttu-id="d947b-124">如果过程声明参数[ByRef](../../../../visual-basic/language-reference/modifiers/byref.md)，正确的执行代码的可能依赖于能够更改中调用代码的基础元素。</span><span class="sxs-lookup"><span data-stu-id="d947b-124">If a procedure declares a parameter [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md), the correct execution of the code might depend on being able to change the underlying element in the calling code.</span></span> <span data-ttu-id="d947b-125">如果调用代码重写此调用的机制，通过将实参括在括号内，或者如果它通过不可修改自变量，该过程不能更改基础元素。</span><span class="sxs-lookup"><span data-stu-id="d947b-125">If the calling code overrides this calling mechanism by enclosing the argument in parentheses, or if it passes a nonmodifiable argument, the procedure cannot change the underlying element.</span></span> <span data-ttu-id="d947b-126">这可能会产生意外的结果，调用代码中。</span><span class="sxs-lookup"><span data-stu-id="d947b-126">This might produce unexpected results in the calling code.</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="d947b-127">.NET Framework 安全性</span><span class="sxs-lookup"><span data-stu-id="d947b-127">.NET Framework Security</span></span>  
 <span data-ttu-id="d947b-128">允许一个过程来更改基础中调用代码的自变量的值始终没有潜在风险。</span><span class="sxs-lookup"><span data-stu-id="d947b-128">There is always a potential risk in allowing a procedure to change the value underlying an argument in the calling code.</span></span> <span data-ttu-id="d947b-129">请确保您希望此值可更改，并做好准备，然后再使用它的有效性检查它。</span><span class="sxs-lookup"><span data-stu-id="d947b-129">Make sure you expect this value to be changed, and be prepared to check it for validity before using it.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d947b-130">请参阅</span><span class="sxs-lookup"><span data-stu-id="d947b-130">See Also</span></span>  
 [<span data-ttu-id="d947b-131">过程</span><span class="sxs-lookup"><span data-stu-id="d947b-131">Procedures</span></span>](./index.md)  
 [<span data-ttu-id="d947b-132">过程参数和自变量</span><span class="sxs-lookup"><span data-stu-id="d947b-132">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)  
 [<span data-ttu-id="d947b-133">如何：将自变量传递给过程</span><span class="sxs-lookup"><span data-stu-id="d947b-133">How to: Pass Arguments to a Procedure</span></span>](./how-to-pass-arguments-to-a-procedure.md)  
 [<span data-ttu-id="d947b-134">按值和按引用传递自变量</span><span class="sxs-lookup"><span data-stu-id="d947b-134">Passing Arguments by Value and by Reference</span></span>](./passing-arguments-by-value-and-by-reference.md)  
 [<span data-ttu-id="d947b-135">可修改和不可修改自变量之间的差异</span><span class="sxs-lookup"><span data-stu-id="d947b-135">Differences Between Modifiable and Nonmodifiable Arguments</span></span>](./differences-between-modifiable-and-nonmodifiable-arguments.md)  
 [<span data-ttu-id="d947b-136">通过值传递自变量和通过引用传递自变量之间的差异</span><span class="sxs-lookup"><span data-stu-id="d947b-136">Differences Between Passing an Argument By Value and By Reference</span></span>](./differences-between-passing-an-argument-by-value-and-by-reference.md)  
 [<span data-ttu-id="d947b-137">如何：更改过程自变量的值</span><span class="sxs-lookup"><span data-stu-id="d947b-137">How to: Change the Value of a Procedure Argument</span></span>](./how-to-change-the-value-of-a-procedure-argument.md)  
 [<span data-ttu-id="d947b-138">如何：防止过程自变量的值被更改</span><span class="sxs-lookup"><span data-stu-id="d947b-138">How to: Protect a Procedure Argument Against Value Changes</span></span>](./how-to-protect-a-procedure-argument-against-value-changes.md)  
 [<span data-ttu-id="d947b-139">按位置和按名称传递自变量</span><span class="sxs-lookup"><span data-stu-id="d947b-139">Passing Arguments by Position and by Name</span></span>](./passing-arguments-by-position-and-by-name.md)  
 [<span data-ttu-id="d947b-140">值类型和引用类型</span><span class="sxs-lookup"><span data-stu-id="d947b-140">Value Types and Reference Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)
