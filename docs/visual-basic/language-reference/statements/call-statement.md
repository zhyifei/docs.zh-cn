---
title: "Call 语句 (Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.Call
helpviewer_keywords:
- procedures [Visual Basic], Call statement
- Call statement [Visual Basic]
- procedures [Visual Basic], calling
ms.assetid: e5b31571-6867-406f-b8e7-a3f9aae4723a
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: c72450fd6f931f36f640d3e384a6fd38d57a7a23
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="call-statement-visual-basic"></a><span data-ttu-id="62241-102">Call 语句 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="62241-102">Call Statement (Visual Basic)</span></span>
<span data-ttu-id="62241-103">将传输到的控件`Function`， `Sub`，或动态链接库 (DLL) 过程。</span><span class="sxs-lookup"><span data-stu-id="62241-103">Transfers control to a `Function`, `Sub`, or dynamic-link library (DLL) procedure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="62241-104">语法</span><span class="sxs-lookup"><span data-stu-id="62241-104">Syntax</span></span>  
  
```  
[ Call ] procedureName [ (argumentList) ]  
```  
  
## <a name="parts"></a><span data-ttu-id="62241-105">部件</span><span class="sxs-lookup"><span data-stu-id="62241-105">Parts</span></span>  
 `procedureName`  
 <span data-ttu-id="62241-106">必需。</span><span class="sxs-lookup"><span data-stu-id="62241-106">Required.</span></span> <span data-ttu-id="62241-107">要调用的过程的名称。</span><span class="sxs-lookup"><span data-stu-id="62241-107">Name of the procedure to call.</span></span>  
  
 `argumentList`  
 <span data-ttu-id="62241-108">可选。</span><span class="sxs-lookup"><span data-stu-id="62241-108">Optional.</span></span> <span data-ttu-id="62241-109">变量或表达式表示被调用时传递给过程的自变量列表。</span><span class="sxs-lookup"><span data-stu-id="62241-109">List of variables or expressions representing arguments that are passed to the procedure when it is called.</span></span> <span data-ttu-id="62241-110">用逗号分隔多个自变量。</span><span class="sxs-lookup"><span data-stu-id="62241-110">Multiple arguments are separated by commas.</span></span> <span data-ttu-id="62241-111">如果包含`argumentList`，必须将它括在括号中。</span><span class="sxs-lookup"><span data-stu-id="62241-111">If you include `argumentList`, you must enclose it in parentheses.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="62241-112">备注</span><span class="sxs-lookup"><span data-stu-id="62241-112">Remarks</span></span>  
 <span data-ttu-id="62241-113">你可以使用`Call`关键字调用过程时。</span><span class="sxs-lookup"><span data-stu-id="62241-113">You can use the `Call` keyword when you call a procedure.</span></span> <span data-ttu-id="62241-114">对于大多数过程调用中，你不需要使用此关键字。</span><span class="sxs-lookup"><span data-stu-id="62241-114">For most procedure calls, you aren’t required to use this  keyword.</span></span>  
  
 <span data-ttu-id="62241-115">通常使用`Call`关键字时调用的表达式不能启动标识符与。</span><span class="sxs-lookup"><span data-stu-id="62241-115">You typically use the `Call` keyword when the called expression doesn’t start with an identifier.</span></span> <span data-ttu-id="62241-116">利用`Call`用于其他用途的关键字，则不建议。</span><span class="sxs-lookup"><span data-stu-id="62241-116">Use of the `Call` keyword for other uses isn’t recommended.</span></span>  
  
 <span data-ttu-id="62241-117">如果该过程返回一个值，`Call`语句将放弃它。</span><span class="sxs-lookup"><span data-stu-id="62241-117">If the procedure returns a value, the `Call` statement discards it.</span></span>  
  
## <a name="example"></a><span data-ttu-id="62241-118">示例</span><span class="sxs-lookup"><span data-stu-id="62241-118">Example</span></span>  
 <span data-ttu-id="62241-119">下面的代码演示两个示例其中`Call`关键字是必需调用过程。</span><span class="sxs-lookup"><span data-stu-id="62241-119">The following code shows two examples where the `Call` keyword is necessary to call a procedure.</span></span> <span data-ttu-id="62241-120">在这两个示例中，调用的表达式不能启动标识符与。</span><span class="sxs-lookup"><span data-stu-id="62241-120">In both examples, the called expression doesn't start with an identifier.</span></span>  
  
 [!code-vb[VbVbalrStatements#97](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/call-statement_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="62241-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="62241-121">See Also</span></span>  
 [<span data-ttu-id="62241-122">Function 语句</span><span class="sxs-lookup"><span data-stu-id="62241-122">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)  
 [<span data-ttu-id="62241-123">Sub 语句</span><span class="sxs-lookup"><span data-stu-id="62241-123">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
 [<span data-ttu-id="62241-124">Declare 语句</span><span class="sxs-lookup"><span data-stu-id="62241-124">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)  
 [<span data-ttu-id="62241-125">Lambda 表达式</span><span class="sxs-lookup"><span data-stu-id="62241-125">Lambda Expressions</span></span>](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)
