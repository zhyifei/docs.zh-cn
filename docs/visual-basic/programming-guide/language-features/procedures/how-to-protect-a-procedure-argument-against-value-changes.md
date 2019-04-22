---
title: 如何：防止过程自变量的值发生更改 (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- procedures [Visual Basic], arguments
- procedures [Visual Basic], parameters
- procedure arguments
- arguments [Visual Basic], passing by reference
- Visual Basic code, procedures
- arguments [Visual Basic], ByVal
- arguments [Visual Basic], passing by value
- procedure parameters
- procedures [Visual Basic], calling
- arguments [Visual Basic], ByRef
- arguments [Visual Basic], changing value
ms.assetid: d2b7c766-ce16-4d2c-8d79-3fc0e7ba2227
ms.openlocfilehash: 70378b57c6d3af5a98e0ba9c6e3aebc319561b1b
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "58837775"
---
# <a name="how-to-protect-a-procedure-argument-against-value-changes-visual-basic"></a><span data-ttu-id="7dc65-102">如何：防止过程自变量的值发生更改 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7dc65-102">How to: Protect a Procedure Argument Against Value Changes (Visual Basic)</span></span>
<span data-ttu-id="7dc65-103">如果一个过程声明为参数[ByRef](../../../../visual-basic/language-reference/modifiers/byref.md)，Visual Basic 使过程代码中调用代码参数的基础的编程元素直接引用。</span><span class="sxs-lookup"><span data-stu-id="7dc65-103">If a procedure declares a parameter as [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md), Visual Basic gives the procedure code a direct reference to the programming element underlying the argument in the calling code.</span></span> <span data-ttu-id="7dc65-104">这将允许更改调用代码中的实参的值的过程。</span><span class="sxs-lookup"><span data-stu-id="7dc65-104">This permits the procedure to change the value underlying the argument in the calling code.</span></span> <span data-ttu-id="7dc65-105">在某些情况下调用的代码可能想要防止此类更改。</span><span class="sxs-lookup"><span data-stu-id="7dc65-105">In some cases the calling code might want to protect against such a change.</span></span>  
  
 <span data-ttu-id="7dc65-106">你可以始终防止自变量的更改中通过声明的相应参数[ByVal](../../../../visual-basic/language-reference/modifiers/byval.md)过程中。</span><span class="sxs-lookup"><span data-stu-id="7dc65-106">You can always protect an argument from change by declaring the corresponding parameter [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) in the procedure.</span></span> <span data-ttu-id="7dc65-107">如果你想要将无法更改在某些情况下，而不是其他中给定的参数，可以将其声明`ByRef`并让调用代码确定每个调用中的传递机制。</span><span class="sxs-lookup"><span data-stu-id="7dc65-107">If you want to be able to change a given argument in some cases but not others, you can declare it `ByRef` and let the calling code determine the passing mechanism in each call.</span></span> <span data-ttu-id="7dc65-108">之所以如此是因为相应的参数中括号括起来，将它传递的值，或不将其括起来在括号中以通过引用进行传递。</span><span class="sxs-lookup"><span data-stu-id="7dc65-108">It does this by enclosing the corresponding argument in parentheses to pass it by value, or not enclosing it in parentheses to pass it by reference.</span></span> <span data-ttu-id="7dc65-109">有关详细信息，请参阅[如何：强制通过值传递自变量](./how-to-force-an-argument-to-be-passed-by-value.md)。</span><span class="sxs-lookup"><span data-stu-id="7dc65-109">For more information, see [How to: Force an Argument to Be Passed by Value](./how-to-force-an-argument-to-be-passed-by-value.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="7dc65-110">示例</span><span class="sxs-lookup"><span data-stu-id="7dc65-110">Example</span></span>  
 <span data-ttu-id="7dc65-111">下面的示例演示两个过程采用一个数组变量并运行它的元素。</span><span class="sxs-lookup"><span data-stu-id="7dc65-111">The following example shows two procedures that take an array variable and operate on its elements.</span></span> <span data-ttu-id="7dc65-112">`increase`过程只需添加一个到每个元素。</span><span class="sxs-lookup"><span data-stu-id="7dc65-112">The `increase` procedure simply adds one to each element.</span></span> <span data-ttu-id="7dc65-113">`replace`过程将一个新数组分配给该参数`a()`，然后添加一个到每个元素。</span><span class="sxs-lookup"><span data-stu-id="7dc65-113">The `replace` procedure assigns a new array to the parameter `a()` and then adds one to each element.</span></span> <span data-ttu-id="7dc65-114">但是，重新分配不影响调用代码中的基础数组变量。</span><span class="sxs-lookup"><span data-stu-id="7dc65-114">However, the reassignment does not affect the underlying array variable in the calling code.</span></span>  
  
 [!code-vb[VbVbcnProcedures#35](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#35)]  
  
 [!code-vb[VbVbcnProcedures#38](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#38)]  
  
 [!code-vb[VbVbcnProcedures#37](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#37)]  
  
 <span data-ttu-id="7dc65-115">第一个`MsgBox`调用显示"increase(n) 后：11, 21, 31, 41".</span><span class="sxs-lookup"><span data-stu-id="7dc65-115">The first `MsgBox` call displays "After increase(n): 11, 21, 31, 41".</span></span> <span data-ttu-id="7dc65-116">因为数组`n`是引用类型，`increase`可以更改其中一个成员，即使传递机制是`ByVal`。</span><span class="sxs-lookup"><span data-stu-id="7dc65-116">Because the array `n` is a reference type, `increase` can change its members, even though the passing mechanism is `ByVal`.</span></span>  
  
 <span data-ttu-id="7dc65-117">第二个`MsgBox`调用显示"replace(n) 后：11, 21, 31, 41".</span><span class="sxs-lookup"><span data-stu-id="7dc65-117">The second `MsgBox` call displays "After replace(n): 11, 21, 31, 41".</span></span> <span data-ttu-id="7dc65-118">因为`n`传递`ByVal`，`replace`不能修改变量`n`通过向它分配一个新数组，调用代码中。</span><span class="sxs-lookup"><span data-stu-id="7dc65-118">Because `n` is passed `ByVal`, `replace` cannot modify the variable `n` in the calling code by assigning a new array to it.</span></span> <span data-ttu-id="7dc65-119">当`replace`创建新的数组实例`k`并将其分配给本地变量`a`，它将失去对引用`n`由调用代码传入。</span><span class="sxs-lookup"><span data-stu-id="7dc65-119">When `replace` creates the new array instance `k` and assigns it to the local variable `a`, it loses the reference to `n` passed in by the calling code.</span></span> <span data-ttu-id="7dc65-120">当其更改的成员`a`，只有本地数组`k`受到影响。</span><span class="sxs-lookup"><span data-stu-id="7dc65-120">When it changes the members of `a`, only the local array `k` is affected.</span></span> <span data-ttu-id="7dc65-121">因此，`replace`不会增加数组的值`n`调用代码中。</span><span class="sxs-lookup"><span data-stu-id="7dc65-121">Therefore, `replace` does not increment the values of array `n` in the calling code.</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="7dc65-122">编译代码</span><span class="sxs-lookup"><span data-stu-id="7dc65-122">Compiling the Code</span></span>  
 <span data-ttu-id="7dc65-123">Visual Basic 中的默认值是按值传递参数。</span><span class="sxs-lookup"><span data-stu-id="7dc65-123">The default in Visual Basic is to pass arguments by value.</span></span> <span data-ttu-id="7dc65-124">但是，它是一个良好的编程做法包括[ByVal](../../../../visual-basic/language-reference/modifiers/byval.md)或[ByRef](../../../../visual-basic/language-reference/modifiers/byref.md)关键字与每个声明的参数。</span><span class="sxs-lookup"><span data-stu-id="7dc65-124">However, it is good programming practice to include either the [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) or [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md) keyword with every declared parameter.</span></span> <span data-ttu-id="7dc65-125">这使您的代码易于阅读。</span><span class="sxs-lookup"><span data-stu-id="7dc65-125">This makes your code easier to read.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7dc65-126">请参阅</span><span class="sxs-lookup"><span data-stu-id="7dc65-126">See also</span></span>

- [<span data-ttu-id="7dc65-127">过程</span><span class="sxs-lookup"><span data-stu-id="7dc65-127">Procedures</span></span>](./index.md)
- [<span data-ttu-id="7dc65-128">过程参数和自变量</span><span class="sxs-lookup"><span data-stu-id="7dc65-128">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="7dc65-129">如何：将参数传递给过程</span><span class="sxs-lookup"><span data-stu-id="7dc65-129">How to: Pass Arguments to a Procedure</span></span>](./how-to-pass-arguments-to-a-procedure.md)
- [<span data-ttu-id="7dc65-130">按值和按引用传递自变量</span><span class="sxs-lookup"><span data-stu-id="7dc65-130">Passing Arguments by Value and by Reference</span></span>](./passing-arguments-by-value-and-by-reference.md)
- [<span data-ttu-id="7dc65-131">可修改和不可修改自变量之间的差异</span><span class="sxs-lookup"><span data-stu-id="7dc65-131">Differences Between Modifiable and Nonmodifiable Arguments</span></span>](./differences-between-modifiable-and-nonmodifiable-arguments.md)
- [<span data-ttu-id="7dc65-132">通过值传递自变量和通过引用传递自变量之间的差异</span><span class="sxs-lookup"><span data-stu-id="7dc65-132">Differences Between Passing an Argument By Value and By Reference</span></span>](./differences-between-passing-an-argument-by-value-and-by-reference.md)
- [<span data-ttu-id="7dc65-133">如何：更改过程自变量的值</span><span class="sxs-lookup"><span data-stu-id="7dc65-133">How to: Change the Value of a Procedure Argument</span></span>](./how-to-change-the-value-of-a-procedure-argument.md)
- [<span data-ttu-id="7dc65-134">如何：强制通过值传递自变量</span><span class="sxs-lookup"><span data-stu-id="7dc65-134">How to: Force an Argument to Be Passed by Value</span></span>](./how-to-force-an-argument-to-be-passed-by-value.md)
- [<span data-ttu-id="7dc65-135">按位置和按名称传递自变量</span><span class="sxs-lookup"><span data-stu-id="7dc65-135">Passing Arguments by Position and by Name</span></span>](./passing-arguments-by-position-and-by-name.md)
- [<span data-ttu-id="7dc65-136">值类型和引用类型</span><span class="sxs-lookup"><span data-stu-id="7dc65-136">Value Types and Reference Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)
