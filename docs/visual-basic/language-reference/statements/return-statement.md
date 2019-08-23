---
title: Return 语句 (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Return
helpviewer_keywords:
- Return statement [Visual Basic], syntax
- control flow [Visual Basic], returning control to expressions
- Return statement [Visual Basic]
- expressions [Visual Basic], returning control to
ms.assetid: ac86e7f0-5a67-42c3-9834-0e0381efa3ec
ms.openlocfilehash: af49ea95d7f9d01072190ac3ccf6ba2f1041347e
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69957678"
---
# <a name="return-statement-visual-basic"></a><span data-ttu-id="aa9b0-102">Return 语句 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="aa9b0-102">Return Statement (Visual Basic)</span></span>
<span data-ttu-id="aa9b0-103">将控件返回到调用`Function`、 `Sub`、 `Get`、 `Set`或`Operator`过程的代码。</span><span class="sxs-lookup"><span data-stu-id="aa9b0-103">Returns control to the code that called a `Function`, `Sub`, `Get`, `Set`, or `Operator` procedure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aa9b0-104">语法</span><span class="sxs-lookup"><span data-stu-id="aa9b0-104">Syntax</span></span>  
  
```  
Return  
-or-  
Return expression  
```  
  
## <a name="part"></a><span data-ttu-id="aa9b0-105">部件</span><span class="sxs-lookup"><span data-stu-id="aa9b0-105">Part</span></span>  
 `expression`  
 <span data-ttu-id="aa9b0-106">在、 `Function` `Get`或过程中是必需的。`Operator`</span><span class="sxs-lookup"><span data-stu-id="aa9b0-106">Required in a `Function`, `Get`, or `Operator` procedure.</span></span> <span data-ttu-id="aa9b0-107">表示要返回到调用代码的值的表达式。</span><span class="sxs-lookup"><span data-stu-id="aa9b0-107">Expression that represents the value to be returned to the calling code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="aa9b0-108">备注</span><span class="sxs-lookup"><span data-stu-id="aa9b0-108">Remarks</span></span>  
 <span data-ttu-id="aa9b0-109">`Return` `Exit Sub` `Exit Property` `expression`在或过程`Set`中, 语句等效于或语句, 不能提供。 `Sub`</span><span class="sxs-lookup"><span data-stu-id="aa9b0-109">In a `Sub` or `Set` procedure, the `Return` statement is equivalent to an `Exit Sub` or `Exit Property` statement, and `expression` must not be supplied.</span></span>  
  
 <span data-ttu-id="aa9b0-110">`expression` `expression`在、或过程`Operator`中,`Return`语句必须包含, 并且必须计算为可转换为过程返回类型的数据类型。 `Get` `Function`</span><span class="sxs-lookup"><span data-stu-id="aa9b0-110">In a `Function`, `Get`, or `Operator` procedure, the `Return` statement must include `expression`, and `expression` must evaluate to a data type that is convertible to the return type of the procedure.</span></span> <span data-ttu-id="aa9b0-111">`Exit Function` `Exit Property`在或过程`Get`中, 您还可以选择将表达式分配给过程名称以用作返回值, 然后执行或语句。 `Function`</span><span class="sxs-lookup"><span data-stu-id="aa9b0-111">In a `Function` or `Get` procedure, you also have the alternative of assigning an expression to the procedure name to serve as the return value, and then executing an `Exit Function` or `Exit Property` statement.</span></span> <span data-ttu-id="aa9b0-112">在过程中, 必须使用`Return expression`。 `Operator`</span><span class="sxs-lookup"><span data-stu-id="aa9b0-112">In an `Operator` procedure, you must use `Return expression`.</span></span>  
  
 <span data-ttu-id="aa9b0-113">可以在同一个过程`Return`中包含任意多个语句。</span><span class="sxs-lookup"><span data-stu-id="aa9b0-113">You can include as many `Return` statements as appropriate in the same procedure.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="aa9b0-114">`Finally`块中的代码在遇到`Try`或`Catch`块`Return`中的语句之后、但在执行该`Return`语句之前运行。</span><span class="sxs-lookup"><span data-stu-id="aa9b0-114">The code in a `Finally` block runs after a `Return` statement in a `Try` or `Catch` block is encountered, but before that `Return` statement executes.</span></span> <span data-ttu-id="aa9b0-115">语句不能包含`Finally`在块中。 `Return`</span><span class="sxs-lookup"><span data-stu-id="aa9b0-115">A `Return` statement cannot be included in a `Finally` block.</span></span>  
  
## <a name="example"></a><span data-ttu-id="aa9b0-116">示例</span><span class="sxs-lookup"><span data-stu-id="aa9b0-116">Example</span></span>  
 <span data-ttu-id="aa9b0-117">下面的示例多次使用`Return`语句, 以便在过程不需要执行任何其他操作时返回到调用代码。</span><span class="sxs-lookup"><span data-stu-id="aa9b0-117">The following example uses the `Return` statement several times to return to the calling code when the procedure does not have to do anything else.</span></span>  
  
 [!code-vb[VbVbalrStatements#53](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#53)]  
  
## <a name="see-also"></a><span data-ttu-id="aa9b0-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="aa9b0-118">See also</span></span>

- [<span data-ttu-id="aa9b0-119">Function 语句</span><span class="sxs-lookup"><span data-stu-id="aa9b0-119">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)
- [<span data-ttu-id="aa9b0-120">Sub 语句</span><span class="sxs-lookup"><span data-stu-id="aa9b0-120">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)
- [<span data-ttu-id="aa9b0-121">Get 语句</span><span class="sxs-lookup"><span data-stu-id="aa9b0-121">Get Statement</span></span>](../../../visual-basic/language-reference/statements/get-statement.md)
- [<span data-ttu-id="aa9b0-122">Set 语句</span><span class="sxs-lookup"><span data-stu-id="aa9b0-122">Set Statement</span></span>](../../../visual-basic/language-reference/statements/set-statement.md)
- [<span data-ttu-id="aa9b0-123">Operator Statement</span><span class="sxs-lookup"><span data-stu-id="aa9b0-123">Operator Statement</span></span>](../../../visual-basic/language-reference/statements/operator-statement.md)
- [<span data-ttu-id="aa9b0-124">Property 语句</span><span class="sxs-lookup"><span data-stu-id="aa9b0-124">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)
- [<span data-ttu-id="aa9b0-125">Exit 语句</span><span class="sxs-lookup"><span data-stu-id="aa9b0-125">Exit Statement</span></span>](../../../visual-basic/language-reference/statements/exit-statement.md)
- [<span data-ttu-id="aa9b0-126">Try...Catch...Finally 语句</span><span class="sxs-lookup"><span data-stu-id="aa9b0-126">Try...Catch...Finally Statement</span></span>](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)
