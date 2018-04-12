---
title: Return 语句 (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.Return
helpviewer_keywords:
- Return statement [Visual Basic], syntax
- control flow [Visual Basic], returning control to expressions
- Return statement [Visual Basic]
- expressions [Visual Basic], returning control to
ms.assetid: ac86e7f0-5a67-42c3-9834-0e0381efa3ec
caps.latest.revision: 15
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: b66d16a249164b8989f05f10c785b97055bfde9e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="return-statement-visual-basic"></a><span data-ttu-id="dead2-102">Return 语句 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="dead2-102">Return Statement (Visual Basic)</span></span>
<span data-ttu-id="dead2-103">将控制权返回给调用的代码`Function`， `Sub`， `Get`， `Set`，或`Operator`过程。</span><span class="sxs-lookup"><span data-stu-id="dead2-103">Returns control to the code that called a `Function`, `Sub`, `Get`, `Set`, or `Operator` procedure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dead2-104">语法</span><span class="sxs-lookup"><span data-stu-id="dead2-104">Syntax</span></span>  
  
```  
Return  
-or-  
Return expression  
```  
  
## <a name="part"></a><span data-ttu-id="dead2-105">部件</span><span class="sxs-lookup"><span data-stu-id="dead2-105">Part</span></span>  
 `expression`  
 <span data-ttu-id="dead2-106">中所需`Function`， `Get`，或`Operator`过程。</span><span class="sxs-lookup"><span data-stu-id="dead2-106">Required in a `Function`, `Get`, or `Operator` procedure.</span></span> <span data-ttu-id="dead2-107">表示要返回到调用代码的值的表达式。</span><span class="sxs-lookup"><span data-stu-id="dead2-107">Expression that represents the value to be returned to the calling code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="dead2-108">备注</span><span class="sxs-lookup"><span data-stu-id="dead2-108">Remarks</span></span>  
 <span data-ttu-id="dead2-109">在`Sub`或`Set`过程中，`Return`语句是等效于`Exit Sub`或`Exit Property`语句，和`expression`必须未提供。</span><span class="sxs-lookup"><span data-stu-id="dead2-109">In a `Sub` or `Set` procedure, the `Return` statement is equivalent to an `Exit Sub` or `Exit Property` statement, and `expression` must not be supplied.</span></span>  
  
 <span data-ttu-id="dead2-110">在`Function`， `Get`，或`Operator`过程中，`Return`语句必须包含`expression`，和`expression`计算结果必须为可以转换为的过程的返回类型的数据类型。</span><span class="sxs-lookup"><span data-stu-id="dead2-110">In a `Function`, `Get`, or `Operator` procedure, the `Return` statement must include `expression`, and `expression` must evaluate to a data type that is convertible to the return type of the procedure.</span></span> <span data-ttu-id="dead2-111">在`Function`或`Get`过程中，你还可以选择表达式分配到过程名称以作为返回值，然后执行`Exit Function`或`Exit Property`语句。</span><span class="sxs-lookup"><span data-stu-id="dead2-111">In a `Function` or `Get` procedure, you also have the alternative of assigning an expression to the procedure name to serve as the return value, and then executing an `Exit Function` or `Exit Property` statement.</span></span> <span data-ttu-id="dead2-112">在`Operator`过程中，你必须使用`Return``expression`。</span><span class="sxs-lookup"><span data-stu-id="dead2-112">In an `Operator` procedure, you must use `Return``expression`.</span></span>  
  
 <span data-ttu-id="dead2-113">可以包括任意多个`Return`应在相同的过程中适当的语句。</span><span class="sxs-lookup"><span data-stu-id="dead2-113">You can include as many `Return` statements as appropriate in the same procedure.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="dead2-114">中的代码`Finally`块之后运行`Return`中的语句`Try`或`Catch`块是遇到，但在此之前`Return`执行语句。</span><span class="sxs-lookup"><span data-stu-id="dead2-114">The code in a `Finally` block runs after a `Return` statement in a `Try` or `Catch` block is encountered, but before that `Return` statement executes.</span></span> <span data-ttu-id="dead2-115">A`Return`语句不能包含在`Finally`块。</span><span class="sxs-lookup"><span data-stu-id="dead2-115">A `Return` statement cannot be included in a `Finally` block.</span></span>  
  
## <a name="example"></a><span data-ttu-id="dead2-116">示例</span><span class="sxs-lookup"><span data-stu-id="dead2-116">Example</span></span>  
 <span data-ttu-id="dead2-117">下面的示例使用`Return`语句数次以返回到调用代码时不需要执行任何其他操作过程。</span><span class="sxs-lookup"><span data-stu-id="dead2-117">The following example uses the `Return` statement several times to return to the calling code when the procedure does not have to do anything else.</span></span>  
  
 [!code-vb[VbVbalrStatements#53](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/return-statement_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="dead2-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="dead2-118">See Also</span></span>  
 [<span data-ttu-id="dead2-119">Function 语句</span><span class="sxs-lookup"><span data-stu-id="dead2-119">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)  
 [<span data-ttu-id="dead2-120">Sub 语句</span><span class="sxs-lookup"><span data-stu-id="dead2-120">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
 [<span data-ttu-id="dead2-121">Get 语句</span><span class="sxs-lookup"><span data-stu-id="dead2-121">Get Statement</span></span>](../../../visual-basic/language-reference/statements/get-statement.md)  
 [<span data-ttu-id="dead2-122">Set 语句</span><span class="sxs-lookup"><span data-stu-id="dead2-122">Set Statement</span></span>](../../../visual-basic/language-reference/statements/set-statement.md)  
 [<span data-ttu-id="dead2-123">Operator Statement</span><span class="sxs-lookup"><span data-stu-id="dead2-123">Operator Statement</span></span>](../../../visual-basic/language-reference/statements/operator-statement.md)  
 [<span data-ttu-id="dead2-124">Property 语句</span><span class="sxs-lookup"><span data-stu-id="dead2-124">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)  
 [<span data-ttu-id="dead2-125">Exit 语句</span><span class="sxs-lookup"><span data-stu-id="dead2-125">Exit Statement</span></span>](../../../visual-basic/language-reference/statements/exit-statement.md)  
 [<span data-ttu-id="dead2-126">Try...Catch...Finally 语句</span><span class="sxs-lookup"><span data-stu-id="dead2-126">Try...Catch...Finally Statement</span></span>](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)
