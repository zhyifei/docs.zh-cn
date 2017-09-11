---
title: "如何︰ 强制通过值 (Visual Basic 中) 传递参数 |Microsoft 文档"
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
- procedures, arguments
- procedures, parameters
- procedure arguments
- Visual Basic code, procedures
- arguments [Visual Basic], ByVal
- arguments [Visual Basic], passing by value
- procedure parameters
- procedures, calling
- arguments [Visual Basic], in parentheses
- procedure arguments, in parentheses
- arguments [Visual Basic], changing value
ms.assetid: 77b4f2d2-1055-4c2f-a521-874d1db86946
caps.latest.revision: 16
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
ms.openlocfilehash: b151c319489ccda357faa082ce0b3c1addad0458
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017

---
# <a name="how-to-force-an-argument-to-be-passed-by-value-visual-basic"></a><span data-ttu-id="f9561-102">如何：强制通过值传递自变量 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f9561-102">How to: Force an Argument to Be Passed by Value (Visual Basic)</span></span>
<span data-ttu-id="f9561-103">过程声明确定传递机制。</span><span class="sxs-lookup"><span data-stu-id="f9561-103">The procedure declaration determines the passing mechanism.</span></span> <span data-ttu-id="f9561-104">如果在声明参数[ByRef](../../../../visual-basic/language-reference/modifiers/byref.md)，[!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]期望通过引用传递相应的参数。</span><span class="sxs-lookup"><span data-stu-id="f9561-104">If a parameter is declared [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md), [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] expects to pass the corresponding argument by reference.</span></span> <span data-ttu-id="f9561-105">这允许更改调用代码中的实参的编程元素的值的过程。</span><span class="sxs-lookup"><span data-stu-id="f9561-105">This allows the procedure to change the value of the programming element underlying the argument in the calling code.</span></span> <span data-ttu-id="f9561-106">如果你想要防止此类更改基础元素，则可以重写`ByRef`传递机制在过程中的调用的参数名称括在括号内。</span><span class="sxs-lookup"><span data-stu-id="f9561-106">If you wish to protect the underlying element against such change, you can override the `ByRef` passing mechanism in the procedure call by enclosing the argument name in parentheses.</span></span> <span data-ttu-id="f9561-107">这些括号是除了括号之外的参数列表的调用中。</span><span class="sxs-lookup"><span data-stu-id="f9561-107">These parentheses are in addition to the parentheses enclosing the argument list in the call.</span></span>  
  
 <span data-ttu-id="f9561-108">调用代码不能重写[ByVal](../../../../visual-basic/language-reference/modifiers/byval.md)机制。</span><span class="sxs-lookup"><span data-stu-id="f9561-108">The calling code cannot override a [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) mechanism.</span></span>  
  
### <a name="to-force-an-argument-to-be-passed-by-value"></a><span data-ttu-id="f9561-109">若要强制通过值传递参数</span><span class="sxs-lookup"><span data-stu-id="f9561-109">To force an argument to be passed by value</span></span>  
  
-   <span data-ttu-id="f9561-110">如果对应的形参声明为`ByVal`在过程中，不需要采取任何额外的步骤。</span><span class="sxs-lookup"><span data-stu-id="f9561-110">If the corresponding parameter is declared `ByVal` in the procedure, you do not need to take any additional steps.</span></span> [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]<span data-ttu-id="f9561-111">已经期望通过值传递参数。</span><span class="sxs-lookup"><span data-stu-id="f9561-111"> already expects to pass the argument by value.</span></span>  
  
-   <span data-ttu-id="f9561-112">如果对应的形参声明为`ByRef`在过程中，将括在圆括号中的过程调用参数。</span><span class="sxs-lookup"><span data-stu-id="f9561-112">If the corresponding parameter is declared `ByRef` in the procedure, enclose the argument in parentheses in the procedure call.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f9561-113">示例</span><span class="sxs-lookup"><span data-stu-id="f9561-113">Example</span></span>  
 <span data-ttu-id="f9561-114">下面的示例重写`ByRef`参数声明。</span><span class="sxs-lookup"><span data-stu-id="f9561-114">The following example overrides a `ByRef` parameter declaration.</span></span> <span data-ttu-id="f9561-115">在强制调用`ByVal`，请注意括号的两个级别。</span><span class="sxs-lookup"><span data-stu-id="f9561-115">In the call that forces `ByVal`, note the two levels of parentheses.</span></span>  
  
 <span data-ttu-id="f9561-116">[!code-vb[VbVbcnProcedures #&39;](./codesnippet/VisualBasic/how-to-force-an-argument-to-be-passed-by-value_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="f9561-116">[!code-vb[VbVbcnProcedures#39](./codesnippet/VisualBasic/how-to-force-an-argument-to-be-passed-by-value_1.vb)]</span></span>  
  
 <span data-ttu-id="f9561-117">[!code-vb[VbVbcnProcedures #&40;](./codesnippet/VisualBasic/how-to-force-an-argument-to-be-passed-by-value_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="f9561-117">[!code-vb[VbVbcnProcedures#40](./codesnippet/VisualBasic/how-to-force-an-argument-to-be-passed-by-value_2.vb)]</span></span>  
  
 <span data-ttu-id="f9561-118">当`str`括在参数列表中的额外括号中`setNewString`过程不能更改在调用代码中，其值和`MsgBox`显示"无法替换如果传递 ByVal"。</span><span class="sxs-lookup"><span data-stu-id="f9561-118">When `str` is enclosed in extra parentheses within the argument list, the `setNewString` procedure cannot change its value in the calling code, and `MsgBox` displays "Cannot be replaced if passed ByVal".</span></span> <span data-ttu-id="f9561-119">当`str`不括在额外的圆括号，过程可以更改它，和`MsgBox`显示"这是 inString 参数的一个新值"。</span><span class="sxs-lookup"><span data-stu-id="f9561-119">When `str` is not enclosed in extra parentheses, the procedure can change it, and `MsgBox` displays "This is a new value for the inString argument."</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="f9561-120">编译代码</span><span class="sxs-lookup"><span data-stu-id="f9561-120">Compiling the Code</span></span>  
 <span data-ttu-id="f9561-121">当通过引用传递变量时，则必须使用`ByRef`关键字来指定此机制。</span><span class="sxs-lookup"><span data-stu-id="f9561-121">When you pass a variable by reference, you must use the `ByRef` keyword to specify this mechanism.</span></span>  
  
 <span data-ttu-id="f9561-122">中的默认设置[!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]是按值传递参数。</span><span class="sxs-lookup"><span data-stu-id="f9561-122">The default in [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] is to pass arguments by value.</span></span> <span data-ttu-id="f9561-123">但是，很好的编程做法包括[ByVal](../../../../visual-basic/language-reference/modifiers/byval.md)或[ByRef](../../../../visual-basic/language-reference/modifiers/byref.md)关键字用于声明的每个参数。</span><span class="sxs-lookup"><span data-stu-id="f9561-123">However, it is good programming practice to include either the [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) or [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md) keyword with every declared parameter.</span></span> <span data-ttu-id="f9561-124">这使您的代码易于阅读。</span><span class="sxs-lookup"><span data-stu-id="f9561-124">This makes your code easier to read.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="f9561-125">可靠编程</span><span class="sxs-lookup"><span data-stu-id="f9561-125">Robust Programming</span></span>  
 <span data-ttu-id="f9561-126">如果过程声明参数[ByRef](../../../../visual-basic/language-reference/modifiers/byref.md)，正确的执行代码的可能依赖于能够更改调用代码中的基础元素。</span><span class="sxs-lookup"><span data-stu-id="f9561-126">If a procedure declares a parameter [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md), the correct execution of the code might depend on being able to change the underlying element in the calling code.</span></span> <span data-ttu-id="f9561-127">如果调用代码重写此调用的机制，通过将实参括在括号内，或者如果它通过一个不可修改参数，该过程不能更改基础元素。</span><span class="sxs-lookup"><span data-stu-id="f9561-127">If the calling code overrides this calling mechanism by enclosing the argument in parentheses, or if it passes a nonmodifiable argument, the procedure cannot change the underlying element.</span></span> <span data-ttu-id="f9561-128">这可能会产生意外的结果调用的代码中。</span><span class="sxs-lookup"><span data-stu-id="f9561-128">This might produce unexpected results in the calling code.</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="f9561-129">.NET Framework 安全性</span><span class="sxs-lookup"><span data-stu-id="f9561-129">.NET Framework Security</span></span>  
 <span data-ttu-id="f9561-130">在允许一个过程来更改基础调用代码中的参数的值都具有潜在的风险。</span><span class="sxs-lookup"><span data-stu-id="f9561-130">There is always a potential risk in allowing a procedure to change the value underlying an argument in the calling code.</span></span> <span data-ttu-id="f9561-131">请确保您希望此值可更改，并做好准备，然后再使用它的有效性检查它。</span><span class="sxs-lookup"><span data-stu-id="f9561-131">Make sure you expect this value to be changed, and be prepared to check it for validity before using it.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f9561-132">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f9561-132">See Also</span></span>  
 <span data-ttu-id="f9561-133">[过程](./index.md) </span><span class="sxs-lookup"><span data-stu-id="f9561-133">[Procedures](./index.md) </span></span>  
<span data-ttu-id="f9561-134"> [过程参数和变量](./procedure-parameters-and-arguments.md) </span><span class="sxs-lookup"><span data-stu-id="f9561-134"> [Procedure Parameters and Arguments](./procedure-parameters-and-arguments.md) </span></span>  
<span data-ttu-id="f9561-135"> [如何︰ 将参数传递给过程](./how-to-pass-arguments-to-a-procedure.md) </span><span class="sxs-lookup"><span data-stu-id="f9561-135"> [How to: Pass Arguments to a Procedure](./how-to-pass-arguments-to-a-procedure.md) </span></span>  
<span data-ttu-id="f9561-136"> [通过值和通过引用传递参数](./passing-arguments-by-value-and-by-reference.md) </span><span class="sxs-lookup"><span data-stu-id="f9561-136"> [Passing Arguments by Value and by Reference](./passing-arguments-by-value-and-by-reference.md) </span></span>  
<span data-ttu-id="f9561-137"> [可修改和不可修改参数之间的差异](./differences-between-modifiable-and-nonmodifiable-arguments.md) </span><span class="sxs-lookup"><span data-stu-id="f9561-137"> [Differences Between Modifiable and Nonmodifiable Arguments](./differences-between-modifiable-and-nonmodifiable-arguments.md) </span></span>  
<span data-ttu-id="f9561-138"> [通过值和通过引用传递参数之间的差异](./differences-between-passing-an-argument-by-value-and-by-reference.md) </span><span class="sxs-lookup"><span data-stu-id="f9561-138"> [Differences Between Passing an Argument By Value and By Reference](./differences-between-passing-an-argument-by-value-and-by-reference.md) </span></span>  
<span data-ttu-id="f9561-139"> [如何︰ 更改过程参数的值](./how-to-change-the-value-of-a-procedure-argument.md) </span><span class="sxs-lookup"><span data-stu-id="f9561-139"> [How to: Change the Value of a Procedure Argument](./how-to-change-the-value-of-a-procedure-argument.md) </span></span>  
<span data-ttu-id="f9561-140"> [如何︰ 防止过程参数的值更改](./how-to-protect-a-procedure-argument-against-value-changes.md) </span><span class="sxs-lookup"><span data-stu-id="f9561-140"> [How to: Protect a Procedure Argument Against Value Changes](./how-to-protect-a-procedure-argument-against-value-changes.md) </span></span>  
<span data-ttu-id="f9561-141"> [按位置和按名称传递参数](./passing-arguments-by-position-and-by-name.md) </span><span class="sxs-lookup"><span data-stu-id="f9561-141"> [Passing Arguments by Position and by Name](./passing-arguments-by-position-and-by-name.md) </span></span>  
<span data-ttu-id="f9561-142"> [值类型和引用类型](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)</span><span class="sxs-lookup"><span data-stu-id="f9561-142"> [Value Types and Reference Types](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)</span></span>
