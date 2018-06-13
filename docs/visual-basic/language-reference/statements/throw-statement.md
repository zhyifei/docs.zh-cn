---
title: Throw 语句 (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Throw
helpviewer_keywords:
- structured exception handling, throw statements
- try-catch exception handling, throw statements
- throw statement [Visual Basic], about throw statements
- throwing exceptions, throw statement
- exception handling, throw statement
- On Error statement [Visual Basic], throwing exceptions
- throwing exceptions
- exception handling, unstructured
- throw statement [Visual Basic]
ms.assetid: a6e07406-5c8a-4498-87a2-8339f3651d62
ms.openlocfilehash: cfa53b3585846da25711739fb7af4bde21746b29
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33602848"
---
# <a name="throw-statement-visual-basic"></a><span data-ttu-id="9b0d6-102">Throw 语句 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9b0d6-102">Throw Statement (Visual Basic)</span></span>
<span data-ttu-id="9b0d6-103">引发过程中的异常。</span><span class="sxs-lookup"><span data-stu-id="9b0d6-103">Throws an exception within a procedure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9b0d6-104">语法</span><span class="sxs-lookup"><span data-stu-id="9b0d6-104">Syntax</span></span>  
  
```  
Throw [ expression ]  
```  
  
## <a name="part"></a><span data-ttu-id="9b0d6-105">部件</span><span class="sxs-lookup"><span data-stu-id="9b0d6-105">Part</span></span>  
 `expression`  
 <span data-ttu-id="9b0d6-106">提供有关要引发的异常信息。</span><span class="sxs-lookup"><span data-stu-id="9b0d6-106">Provides information about the exception to be thrown.</span></span> <span data-ttu-id="9b0d6-107">可选时驻留在`Catch`语句，否则为必选项。</span><span class="sxs-lookup"><span data-stu-id="9b0d6-107">Optional when residing in a `Catch` statement, otherwise required.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9b0d6-108">备注</span><span class="sxs-lookup"><span data-stu-id="9b0d6-108">Remarks</span></span>  
 <span data-ttu-id="9b0d6-109">`Throw`语句将引发异常，你可以处理与结构化异常处理代码 (`Try`...`Catch`...`Finally`) 或非结构化的异常处理代码 (`On Error GoTo`)。</span><span class="sxs-lookup"><span data-stu-id="9b0d6-109">The `Throw` statement throws an exception that you can handle with structured exception-handling code (`Try`...`Catch`...`Finally`) or unstructured exception-handling code (`On Error GoTo`).</span></span> <span data-ttu-id="9b0d6-110">你可以使用`Throw`语句来捕获代码中的错误，因为 Visual Basic 移动在调用堆栈中向上，直到它找到相应的异常处理代码。</span><span class="sxs-lookup"><span data-stu-id="9b0d6-110">You can use the `Throw` statement to trap errors within your code because Visual Basic moves up the call stack until it finds the appropriate exception-handling code.</span></span>  
  
 <span data-ttu-id="9b0d6-111">A`Throw`不使用表达式的语句仅可在`Catch`语句，这种情况下该语句会再次引发当前处理的异常`Catch`语句。</span><span class="sxs-lookup"><span data-stu-id="9b0d6-111">A `Throw` statement with no expression can only be used in a `Catch` statement, in which case the statement rethrows the exception currently being handled by the `Catch` statement.</span></span>  
  
 <span data-ttu-id="9b0d6-112">`Throw`语句重置的调用堆栈`expression`异常。</span><span class="sxs-lookup"><span data-stu-id="9b0d6-112">The `Throw` statement resets the call stack for the `expression` exception.</span></span> <span data-ttu-id="9b0d6-113">如果`expression`未提供，调用堆栈保留不变。</span><span class="sxs-lookup"><span data-stu-id="9b0d6-113">If `expression` is not provided, the call stack is left unchanged.</span></span> <span data-ttu-id="9b0d6-114">你可以访问通过异常的调用堆栈<xref:System.Exception.StackTrace%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="9b0d6-114">You can access the call stack for the exception through the <xref:System.Exception.StackTrace%2A> property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9b0d6-115">示例</span><span class="sxs-lookup"><span data-stu-id="9b0d6-115">Example</span></span>  
 <span data-ttu-id="9b0d6-116">下面的代码使用`Throw`引发异常的语句：</span><span class="sxs-lookup"><span data-stu-id="9b0d6-116">The following code uses the `Throw` statement to throw an exception:</span></span>  
  
 [!code-vb[VbVbalrStatements#84](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/throw-statement_1.vb)]  
  
## <a name="requirements"></a><span data-ttu-id="9b0d6-117">要求</span><span class="sxs-lookup"><span data-stu-id="9b0d6-117">Requirements</span></span>  
 <span data-ttu-id="9b0d6-118">**Namespace:** [Microsoft.VisualBasic](../../../visual-basic/language-reference/runtime-library-members.md)</span><span class="sxs-lookup"><span data-stu-id="9b0d6-118">**Namespace:** [Microsoft.VisualBasic](../../../visual-basic/language-reference/runtime-library-members.md)</span></span>  
  
 <span data-ttu-id="9b0d6-119">**模块：** `Interaction`</span><span class="sxs-lookup"><span data-stu-id="9b0d6-119">**Module:** `Interaction`</span></span>  
  
 <span data-ttu-id="9b0d6-120">**程序集：** Visual Basic 运行库 （在 Microsoft.VisualBasic.dll 中)</span><span class="sxs-lookup"><span data-stu-id="9b0d6-120">**Assembly:** Visual Basic Runtime Library (in Microsoft.VisualBasic.dll)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9b0d6-121">请参阅</span><span class="sxs-lookup"><span data-stu-id="9b0d6-121">See Also</span></span>  
 [<span data-ttu-id="9b0d6-122">Try...Catch...Finally 语句</span><span class="sxs-lookup"><span data-stu-id="9b0d6-122">Try...Catch...Finally Statement</span></span>](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)  
 [<span data-ttu-id="9b0d6-123">On Error 语句</span><span class="sxs-lookup"><span data-stu-id="9b0d6-123">On Error Statement</span></span>](../../../visual-basic/language-reference/statements/on-error-statement.md)
