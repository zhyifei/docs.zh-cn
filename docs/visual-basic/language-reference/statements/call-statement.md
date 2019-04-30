---
title: Call 语句 (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Call
helpviewer_keywords:
- procedures [Visual Basic], Call statement
- Call statement [Visual Basic]
- procedures [Visual Basic], calling
ms.assetid: e5b31571-6867-406f-b8e7-a3f9aae4723a
ms.openlocfilehash: 755443a99a1ad8b0430a76d2dba1ff27472d4c9d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61945062"
---
# <a name="call-statement-visual-basic"></a><span data-ttu-id="1e34d-102">Call 语句 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1e34d-102">Call Statement (Visual Basic)</span></span>
<span data-ttu-id="1e34d-103">将传输到的控件`Function`， `Sub`，或动态链接库 (DLL) 过程。</span><span class="sxs-lookup"><span data-stu-id="1e34d-103">Transfers control to a `Function`, `Sub`, or dynamic-link library (DLL) procedure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1e34d-104">语法</span><span class="sxs-lookup"><span data-stu-id="1e34d-104">Syntax</span></span>  
  
```  
[ Call ] procedureName [ (argumentList) ]  
```  
  
## <a name="parts"></a><span data-ttu-id="1e34d-105">部件</span><span class="sxs-lookup"><span data-stu-id="1e34d-105">Parts</span></span>  
|||
|---|---|
|`procedureName`|<span data-ttu-id="1e34d-106">必需。</span><span class="sxs-lookup"><span data-stu-id="1e34d-106">Required.</span></span> <span data-ttu-id="1e34d-107">要调用的过程的名称。</span><span class="sxs-lookup"><span data-stu-id="1e34d-107">Name of the procedure to call.</span></span>|
|`argumentList`|<span data-ttu-id="1e34d-108">可选。</span><span class="sxs-lookup"><span data-stu-id="1e34d-108">Optional.</span></span> <span data-ttu-id="1e34d-109">变量或表达式表示被调用时传递给过程的参数的列表。</span><span class="sxs-lookup"><span data-stu-id="1e34d-109">List of variables or expressions representing arguments that are passed to the procedure when it is called.</span></span> <span data-ttu-id="1e34d-110">由逗号分隔多个自变量。</span><span class="sxs-lookup"><span data-stu-id="1e34d-110">Multiple arguments are separated by commas.</span></span> <span data-ttu-id="1e34d-111">如果包含`argumentList`，必须将其括在括号中。</span><span class="sxs-lookup"><span data-stu-id="1e34d-111">If you include `argumentList`, you must enclose it in parentheses.</span></span>|
|||
  
## <a name="remarks"></a><span data-ttu-id="1e34d-112">备注</span><span class="sxs-lookup"><span data-stu-id="1e34d-112">Remarks</span></span>  
 <span data-ttu-id="1e34d-113">可以使用`Call`关键字调用过程时。</span><span class="sxs-lookup"><span data-stu-id="1e34d-113">You can use the `Call` keyword when you call a procedure.</span></span> <span data-ttu-id="1e34d-114">对于大多数过程调用，无需使用此关键字。</span><span class="sxs-lookup"><span data-stu-id="1e34d-114">For most procedure calls, you aren’t required to use this  keyword.</span></span>  
  
 <span data-ttu-id="1e34d-115">通常使用`Call`关键字时被调用的表达式不会启动与的标识符。</span><span class="sxs-lookup"><span data-stu-id="1e34d-115">You typically use the `Call` keyword when the called expression doesn’t start with an identifier.</span></span> <span data-ttu-id="1e34d-116">使用`Call`作他用的关键字不建议。</span><span class="sxs-lookup"><span data-stu-id="1e34d-116">Use of the `Call` keyword for other uses isn’t recommended.</span></span>  
  
 <span data-ttu-id="1e34d-117">如果该过程返回一个值，`Call`语句将其丢弃。</span><span class="sxs-lookup"><span data-stu-id="1e34d-117">If the procedure returns a value, the `Call` statement discards it.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1e34d-118">示例</span><span class="sxs-lookup"><span data-stu-id="1e34d-118">Example</span></span>  
 <span data-ttu-id="1e34d-119">下面的代码演示两个示例其中`Call`关键字才可调用的过程。</span><span class="sxs-lookup"><span data-stu-id="1e34d-119">The following code shows two examples where the `Call` keyword is necessary to call a procedure.</span></span> <span data-ttu-id="1e34d-120">在这两个示例中，被调用的表达式不会启动与的标识符。</span><span class="sxs-lookup"><span data-stu-id="1e34d-120">In both examples, the called expression doesn't start with an identifier.</span></span>  
  
 [!code-vb[VbVbalrStatements#97](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#97)]  
  
## <a name="see-also"></a><span data-ttu-id="1e34d-121">请参阅</span><span class="sxs-lookup"><span data-stu-id="1e34d-121">See also</span></span>

- [<span data-ttu-id="1e34d-122">Function 语句</span><span class="sxs-lookup"><span data-stu-id="1e34d-122">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)
- [<span data-ttu-id="1e34d-123">Sub 语句</span><span class="sxs-lookup"><span data-stu-id="1e34d-123">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)
- [<span data-ttu-id="1e34d-124">Declare 语句</span><span class="sxs-lookup"><span data-stu-id="1e34d-124">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)
- [<span data-ttu-id="1e34d-125">Lambda 表达式</span><span class="sxs-lookup"><span data-stu-id="1e34d-125">Lambda Expressions</span></span>](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)
