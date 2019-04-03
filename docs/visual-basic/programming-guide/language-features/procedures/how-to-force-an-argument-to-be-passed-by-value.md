---
title: 如何：强制自变量传递的值 (Visual Basic)
ms.date: 07/20/2015
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
ms.openlocfilehash: 497ae11b858b7d164ba3b5607ff2109254a154de
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/02/2019
ms.locfileid: "58842039"
---
# <a name="how-to-force-an-argument-to-be-passed-by-value-visual-basic"></a><span data-ttu-id="e7442-102">如何：强制自变量传递的值 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e7442-102">How to: Force an Argument to Be Passed by Value (Visual Basic)</span></span>
<span data-ttu-id="e7442-103">过程声明确定的传递机制。</span><span class="sxs-lookup"><span data-stu-id="e7442-103">The procedure declaration determines the passing mechanism.</span></span> <span data-ttu-id="e7442-104">如果声明的参数[ByRef](../../../../visual-basic/language-reference/modifiers/byref.md)，Visual Basic 希望按引用传递相应的参数。</span><span class="sxs-lookup"><span data-stu-id="e7442-104">If a parameter is declared [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md), Visual Basic expects to pass the corresponding argument by reference.</span></span> <span data-ttu-id="e7442-105">这将允许过程来更改调用代码中的参数的基础编程元素的值。</span><span class="sxs-lookup"><span data-stu-id="e7442-105">This allows the procedure to change the value of the programming element underlying the argument in the calling code.</span></span> <span data-ttu-id="e7442-106">如果你想要防止此类更改基础元素，则可以重写`ByRef`传递机制在过程调用将参数名称括在括号中。</span><span class="sxs-lookup"><span data-stu-id="e7442-106">If you wish to protect the underlying element against such change, you can override the `ByRef` passing mechanism in the procedure call by enclosing the argument name in parentheses.</span></span> <span data-ttu-id="e7442-107">这些括号是除了括号之外的参数列表的调用中。</span><span class="sxs-lookup"><span data-stu-id="e7442-107">These parentheses are in addition to the parentheses enclosing the argument list in the call.</span></span>  
  
 <span data-ttu-id="e7442-108">调用代码不能重写[ByVal](../../../../visual-basic/language-reference/modifiers/byval.md)机制。</span><span class="sxs-lookup"><span data-stu-id="e7442-108">The calling code cannot override a [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) mechanism.</span></span>  
  
### <a name="to-force-an-argument-to-be-passed-by-value"></a><span data-ttu-id="e7442-109">若要强制通过值传递自变量</span><span class="sxs-lookup"><span data-stu-id="e7442-109">To force an argument to be passed by value</span></span>  
  
-   <span data-ttu-id="e7442-110">如果声明的相应参数`ByVal`在过程中，不需要执行任何其他步骤。</span><span class="sxs-lookup"><span data-stu-id="e7442-110">If the corresponding parameter is declared `ByVal` in the procedure, you do not need to take any additional steps.</span></span> <span data-ttu-id="e7442-111">Visual Basic 已预期按值传递参数。</span><span class="sxs-lookup"><span data-stu-id="e7442-111">Visual Basic already expects to pass the argument by value.</span></span>  
  
-   <span data-ttu-id="e7442-112">如果声明的相应参数`ByRef`在过程中，将括在括号中的过程调用中的参数。</span><span class="sxs-lookup"><span data-stu-id="e7442-112">If the corresponding parameter is declared `ByRef` in the procedure, enclose the argument in parentheses in the procedure call.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e7442-113">示例</span><span class="sxs-lookup"><span data-stu-id="e7442-113">Example</span></span>  
 <span data-ttu-id="e7442-114">下面的示例替代`ByRef`参数声明。</span><span class="sxs-lookup"><span data-stu-id="e7442-114">The following example overrides a `ByRef` parameter declaration.</span></span> <span data-ttu-id="e7442-115">强制在调用中`ByVal`，请注意两个级别的括号。</span><span class="sxs-lookup"><span data-stu-id="e7442-115">In the call that forces `ByVal`, note the two levels of parentheses.</span></span>  
  
 [!code-vb[VbVbcnProcedures#39](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#39)]  
  
 [!code-vb[VbVbcnProcedures#40](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#40)]  
  
 <span data-ttu-id="e7442-116">时`str`都包含在参数列表中的额外圆括号`setNewString`过程不能更改在调用代码中，其值和`MsgBox`显示"不能替换如果传递 ByVal"。</span><span class="sxs-lookup"><span data-stu-id="e7442-116">When `str` is enclosed in extra parentheses within the argument list, the `setNewString` procedure cannot change its value in the calling code, and `MsgBox` displays "Cannot be replaced if passed ByVal".</span></span> <span data-ttu-id="e7442-117">当`str`不包含在额外的括号，该过程可以更改它，和`MsgBox`显示"这是新 inString 参数的值"。</span><span class="sxs-lookup"><span data-stu-id="e7442-117">When `str` is not enclosed in extra parentheses, the procedure can change it, and `MsgBox` displays "This is a new value for the inString argument."</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="e7442-118">编译代码</span><span class="sxs-lookup"><span data-stu-id="e7442-118">Compiling the Code</span></span>  
 <span data-ttu-id="e7442-119">当通过引用传递变量时，必须使用`ByRef`关键字来指定此机制。</span><span class="sxs-lookup"><span data-stu-id="e7442-119">When you pass a variable by reference, you must use the `ByRef` keyword to specify this mechanism.</span></span>  
  
 <span data-ttu-id="e7442-120">Visual Basic 中的默认值是按值传递参数。</span><span class="sxs-lookup"><span data-stu-id="e7442-120">The default in Visual Basic is to pass arguments by value.</span></span> <span data-ttu-id="e7442-121">但是，它是一个良好的编程做法包括[ByVal](../../../../visual-basic/language-reference/modifiers/byval.md)或[ByRef](../../../../visual-basic/language-reference/modifiers/byref.md)关键字与每个声明的参数。</span><span class="sxs-lookup"><span data-stu-id="e7442-121">However, it is good programming practice to include either the [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) or [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md) keyword with every declared parameter.</span></span> <span data-ttu-id="e7442-122">这使您的代码易于阅读。</span><span class="sxs-lookup"><span data-stu-id="e7442-122">This makes your code easier to read.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="e7442-123">可靠编程</span><span class="sxs-lookup"><span data-stu-id="e7442-123">Robust Programming</span></span>  
 <span data-ttu-id="e7442-124">如果一个过程声明了形参[ByRef](../../../../visual-basic/language-reference/modifiers/byref.md)，正确执行代码可能依赖于无法更改调用代码中的基础元素。</span><span class="sxs-lookup"><span data-stu-id="e7442-124">If a procedure declares a parameter [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md), the correct execution of the code might depend on being able to change the underlying element in the calling code.</span></span> <span data-ttu-id="e7442-125">如果调用代码重写此调用的机制，通过将实参括在括号内，或者如果它传递不可修改自变量，该过程不能更改基础元素。</span><span class="sxs-lookup"><span data-stu-id="e7442-125">If the calling code overrides this calling mechanism by enclosing the argument in parentheses, or if it passes a nonmodifiable argument, the procedure cannot change the underlying element.</span></span> <span data-ttu-id="e7442-126">这可能会产生意外的结果调用代码中。</span><span class="sxs-lookup"><span data-stu-id="e7442-126">This might produce unexpected results in the calling code.</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="e7442-127">.NET Framework 安全性</span><span class="sxs-lookup"><span data-stu-id="e7442-127">.NET Framework Security</span></span>  
 <span data-ttu-id="e7442-128">允许更改基础调用代码中的自变量的值的过程中始终没有带来潜在的风险。</span><span class="sxs-lookup"><span data-stu-id="e7442-128">There is always a potential risk in allowing a procedure to change the value underlying an argument in the calling code.</span></span> <span data-ttu-id="e7442-129">请确保您希望此值可更改，并且准备好使用它之前检查其有效性。</span><span class="sxs-lookup"><span data-stu-id="e7442-129">Make sure you expect this value to be changed, and be prepared to check it for validity before using it.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e7442-130">请参阅</span><span class="sxs-lookup"><span data-stu-id="e7442-130">See also</span></span>

- [<span data-ttu-id="e7442-131">过程</span><span class="sxs-lookup"><span data-stu-id="e7442-131">Procedures</span></span>](./index.md)
- [<span data-ttu-id="e7442-132">过程参数和自变量</span><span class="sxs-lookup"><span data-stu-id="e7442-132">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="e7442-133">如何：将参数传递给过程</span><span class="sxs-lookup"><span data-stu-id="e7442-133">How to: Pass Arguments to a Procedure</span></span>](./how-to-pass-arguments-to-a-procedure.md)
- [<span data-ttu-id="e7442-134">按值和按引用传递自变量</span><span class="sxs-lookup"><span data-stu-id="e7442-134">Passing Arguments by Value and by Reference</span></span>](./passing-arguments-by-value-and-by-reference.md)
- [<span data-ttu-id="e7442-135">可修改和不可修改自变量之间的差异</span><span class="sxs-lookup"><span data-stu-id="e7442-135">Differences Between Modifiable and Nonmodifiable Arguments</span></span>](./differences-between-modifiable-and-nonmodifiable-arguments.md)
- [<span data-ttu-id="e7442-136">通过值传递自变量和通过引用传递自变量之间的差异</span><span class="sxs-lookup"><span data-stu-id="e7442-136">Differences Between Passing an Argument By Value and By Reference</span></span>](./differences-between-passing-an-argument-by-value-and-by-reference.md)
- [<span data-ttu-id="e7442-137">如何：更改过程自变量的值</span><span class="sxs-lookup"><span data-stu-id="e7442-137">How to: Change the Value of a Procedure Argument</span></span>](./how-to-change-the-value-of-a-procedure-argument.md)
- [<span data-ttu-id="e7442-138">如何：防止过程自变量的值更改</span><span class="sxs-lookup"><span data-stu-id="e7442-138">How to: Protect a Procedure Argument Against Value Changes</span></span>](./how-to-protect-a-procedure-argument-against-value-changes.md)
- [<span data-ttu-id="e7442-139">按位置和按名称传递自变量</span><span class="sxs-lookup"><span data-stu-id="e7442-139">Passing Arguments by Position and by Name</span></span>](./passing-arguments-by-position-and-by-name.md)
- [<span data-ttu-id="e7442-140">值类型和引用类型</span><span class="sxs-lookup"><span data-stu-id="e7442-140">Value Types and Reference Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)
