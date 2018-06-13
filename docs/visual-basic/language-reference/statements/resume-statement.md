---
title: Resume 语句
ms.date: 07/20/2015
f1_keywords:
- vb.Resume
- vb.ResumeNext
helpviewer_keywords:
- Next statement [Visual Basic], Resume
- Resume Next statement [Visual Basic]
- execution [Visual Basic], resuming
- run-time errors [Visual Basic], resuming after
- Resume statement [Visual Basic], syntax
- errors [Visual Basic], resuming after
- Error statement [Visual Basic], and Resume statement
- execution
- Resume statement [Visual Basic]
ms.assetid: e24d058b-1a5c-4274-acb9-7d295d3ea537
ms.openlocfilehash: 1d03f631893be51529f29af824de0d684bf43804
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33603777"
---
# <a name="resume-statement"></a><span data-ttu-id="8a2ca-102">Resume 语句</span><span class="sxs-lookup"><span data-stu-id="8a2ca-102">Resume Statement</span></span>
<span data-ttu-id="8a2ca-103">错误处理例程完毕后恢复执行。</span><span class="sxs-lookup"><span data-stu-id="8a2ca-103">Resumes execution after an error-handling routine is finished.</span></span>  
  
 <span data-ttu-id="8a2ca-104">我们建议你使用结构化的异常处理，只要有可能，在代码中，而不是无需使用非结构化的异常处理和`On Error`和`Resume`语句。</span><span class="sxs-lookup"><span data-stu-id="8a2ca-104">We suggest that you use structured exception handling in your code whenever possible, rather than using unstructured exception handling and the `On Error` and `Resume` statements.</span></span> <span data-ttu-id="8a2ca-105">有关详细信息，请参阅 [Try...Catch...Finally 语句](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="8a2ca-105">For more information, see [Try...Catch...Finally Statement](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8a2ca-106">语法</span><span class="sxs-lookup"><span data-stu-id="8a2ca-106">Syntax</span></span>  
  
```  
Resume [ Next | line ]  
```  
  
## <a name="parts"></a><span data-ttu-id="8a2ca-107">部件</span><span class="sxs-lookup"><span data-stu-id="8a2ca-107">Parts</span></span>  
 `Resume`  
 <span data-ttu-id="8a2ca-108">必须的。</span><span class="sxs-lookup"><span data-stu-id="8a2ca-108">Required.</span></span> <span data-ttu-id="8a2ca-109">如果错误发生的错误处理程序相同的过程中，将导致错误的语句处继续执行。</span><span class="sxs-lookup"><span data-stu-id="8a2ca-109">If the error occurred in the same procedure as the error handler, execution resumes with the statement that caused the error.</span></span> <span data-ttu-id="8a2ca-110">如果在调用过程中出错，请在上一次调用不包含错误处理例程的过程的语句处继续执行。</span><span class="sxs-lookup"><span data-stu-id="8a2ca-110">If the error occurred in a called procedure, execution resumes at the statement that last called out of the procedure containing the error-handling routine.</span></span>  
  
 `Next`  
 <span data-ttu-id="8a2ca-111">可选。</span><span class="sxs-lookup"><span data-stu-id="8a2ca-111">Optional.</span></span> <span data-ttu-id="8a2ca-112">如果在错误处理程序相同的过程中出错，请将紧跟导致错误的语句的语句处继续执行。</span><span class="sxs-lookup"><span data-stu-id="8a2ca-112">If the error occurred in the same procedure as the error handler, execution resumes with the statement immediately following the statement that caused the error.</span></span> <span data-ttu-id="8a2ca-113">如果在调用过程中出错，请紧随上一次调用不包含错误处理例程的过程的语句处继续执行 (或`On Error Resume Next`语句)。</span><span class="sxs-lookup"><span data-stu-id="8a2ca-113">If the error occurred in a called procedure, execution resumes with the statement immediately following the statement that last called out of the procedure containing the error-handling routine (or `On Error Resume Next` statement).</span></span>  
  
 `line`  
 <span data-ttu-id="8a2ca-114">可选。</span><span class="sxs-lookup"><span data-stu-id="8a2ca-114">Optional.</span></span> <span data-ttu-id="8a2ca-115">指定所需的代码行处继续执行`line`自变量。</span><span class="sxs-lookup"><span data-stu-id="8a2ca-115">Execution resumes at the line specified in the required `line` argument.</span></span> <span data-ttu-id="8a2ca-116">`line`自变量是行标签或行号，并且必须在同一过程中的错误处理程序。</span><span class="sxs-lookup"><span data-stu-id="8a2ca-116">The `line` argument is a line label or line number and must be in the same procedure as the error handler.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8a2ca-117">备注</span><span class="sxs-lookup"><span data-stu-id="8a2ca-117">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8a2ca-118">我们建议你使用结构化的异常处理，只要有可能，在代码中，而不是无需使用非结构化的异常处理和`On Error`和`Resume`语句。</span><span class="sxs-lookup"><span data-stu-id="8a2ca-118">We recommend that you use structured exception handling in your code whenever possible, rather than using unstructured exception handling and the `On Error` and `Resume` statements.</span></span> <span data-ttu-id="8a2ca-119">有关详细信息，请参阅 [Try...Catch...Finally 语句](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="8a2ca-119">For more information, see [Try...Catch...Finally Statement](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md).</span></span>  
  
 <span data-ttu-id="8a2ca-120">如果你使用`Resume`语句中任意位置以外的其他错误处理例程中，将会出错。</span><span class="sxs-lookup"><span data-stu-id="8a2ca-120">If you use a `Resume` statement anywhere other than in an error-handling routine, an error occurs.</span></span>  
  
 <span data-ttu-id="8a2ca-121">`Resume`语句不能包含任何过程在`Try...Catch...Finally`语句。</span><span class="sxs-lookup"><span data-stu-id="8a2ca-121">The `Resume` statement cannot be used in any procedure that contains a `Try...Catch...Finally` statement.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8a2ca-122">示例</span><span class="sxs-lookup"><span data-stu-id="8a2ca-122">Example</span></span>  
 <span data-ttu-id="8a2ca-123">此示例使用`Resume`语句来结束的错误处理过程中，然后继续执行导致错误的语句。</span><span class="sxs-lookup"><span data-stu-id="8a2ca-123">This example uses the `Resume` statement to end error handling in a procedure and then resume execution with the statement that caused the error.</span></span> <span data-ttu-id="8a2ca-124">错误号 55 生成来演示使用`Resume`语句。</span><span class="sxs-lookup"><span data-stu-id="8a2ca-124">Error number 55 is generated to illustrate use of the `Resume` statement.</span></span>  
  
 [!code-vb[VbVbalrErrorHandling#16](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/resume-statement_1.vb)]  
  
## <a name="requirements"></a><span data-ttu-id="8a2ca-125">要求</span><span class="sxs-lookup"><span data-stu-id="8a2ca-125">Requirements</span></span>  
 <span data-ttu-id="8a2ca-126">**Namespace:** [Microsoft.VisualBasic](../../../visual-basic/language-reference/runtime-library-members.md)</span><span class="sxs-lookup"><span data-stu-id="8a2ca-126">**Namespace:** [Microsoft.VisualBasic](../../../visual-basic/language-reference/runtime-library-members.md)</span></span>  
  
 <span data-ttu-id="8a2ca-127">**程序集：** Visual Basic 运行库 （在 Microsoft.VisualBasic.dll 中)</span><span class="sxs-lookup"><span data-stu-id="8a2ca-127">**Assembly:** Visual Basic Runtime Library (in Microsoft.VisualBasic.dll)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8a2ca-128">请参阅</span><span class="sxs-lookup"><span data-stu-id="8a2ca-128">See Also</span></span>  
 [<span data-ttu-id="8a2ca-129">Try...Catch...Finally 语句</span><span class="sxs-lookup"><span data-stu-id="8a2ca-129">Try...Catch...Finally Statement</span></span>](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)  
 [<span data-ttu-id="8a2ca-130">Error 语句</span><span class="sxs-lookup"><span data-stu-id="8a2ca-130">Error Statement</span></span>](../../../visual-basic/language-reference/statements/error-statement.md)  
 [<span data-ttu-id="8a2ca-131">On Error 语句</span><span class="sxs-lookup"><span data-stu-id="8a2ca-131">On Error Statement</span></span>](../../../visual-basic/language-reference/statements/on-error-statement.md)
