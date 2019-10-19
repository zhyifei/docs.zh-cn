---
title: Resume 语句（Visual Basic）
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
ms.openlocfilehash: 7b8c2e123c04ff9720d690507ee41a6b52f40c3f
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2019
ms.locfileid: "72583276"
---
# <a name="resume-statement"></a><span data-ttu-id="ea6a4-102">Resume 语句</span><span class="sxs-lookup"><span data-stu-id="ea6a4-102">Resume Statement</span></span>
<span data-ttu-id="ea6a4-103">完成错误处理例程后，继续执行。</span><span class="sxs-lookup"><span data-stu-id="ea6a4-103">Resumes execution after an error-handling routine is finished.</span></span>  
  
 <span data-ttu-id="ea6a4-104">建议尽可能地在代码中使用结构化异常处理，而不是使用非结构化异常处理和 `On Error` 和 `Resume` 语句。</span><span class="sxs-lookup"><span data-stu-id="ea6a4-104">We suggest that you use structured exception handling in your code whenever possible, rather than using unstructured exception handling and the `On Error` and `Resume` statements.</span></span> <span data-ttu-id="ea6a4-105">有关详细信息，请参阅 [Try...Catch...Finally 语句](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="ea6a4-105">For more information, see [Try...Catch...Finally Statement](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ea6a4-106">语法</span><span class="sxs-lookup"><span data-stu-id="ea6a4-106">Syntax</span></span>  
  
```vb  
Resume [ Next | line ]  
```  
  
## <a name="parts"></a><span data-ttu-id="ea6a4-107">部件</span><span class="sxs-lookup"><span data-stu-id="ea6a4-107">Parts</span></span>  
 `Resume`  
 <span data-ttu-id="ea6a4-108">必须的。</span><span class="sxs-lookup"><span data-stu-id="ea6a4-108">Required.</span></span> <span data-ttu-id="ea6a4-109">如果错误发生在与错误处理程序相同的过程中，则执行将继续执行导致错误的语句。</span><span class="sxs-lookup"><span data-stu-id="ea6a4-109">If the error occurred in the same procedure as the error handler, execution resumes with the statement that caused the error.</span></span> <span data-ttu-id="ea6a4-110">如果错误发生在调用的过程中，则执行将在最近从包含错误处理例程的过程中调用的语句处继续。</span><span class="sxs-lookup"><span data-stu-id="ea6a4-110">If the error occurred in a called procedure, execution resumes at the statement that last called out of the procedure containing the error-handling routine.</span></span>  
  
 `Next`  
 <span data-ttu-id="ea6a4-111">可选。</span><span class="sxs-lookup"><span data-stu-id="ea6a4-111">Optional.</span></span> <span data-ttu-id="ea6a4-112">如果错误发生在与错误处理程序相同的过程中，则执行将继续执行导致错误的语句之后的语句。</span><span class="sxs-lookup"><span data-stu-id="ea6a4-112">If the error occurred in the same procedure as the error handler, execution resumes with the statement immediately following the statement that caused the error.</span></span> <span data-ttu-id="ea6a4-113">如果在被调用的过程中发生错误，则继续执行，并在最后调用包含错误处理例程（或 `On Error Resume Next` 语句）的过程后的语句之后的语句之后继续执行。</span><span class="sxs-lookup"><span data-stu-id="ea6a4-113">If the error occurred in a called procedure, execution resumes with the statement immediately following the statement that last called out of the procedure containing the error-handling routine (or `On Error Resume Next` statement).</span></span>  
  
 `line`  
 <span data-ttu-id="ea6a4-114">可选。</span><span class="sxs-lookup"><span data-stu-id="ea6a4-114">Optional.</span></span> <span data-ttu-id="ea6a4-115">执行在所需 `line` 参数中指定的行处恢复。</span><span class="sxs-lookup"><span data-stu-id="ea6a4-115">Execution resumes at the line specified in the required `line` argument.</span></span> <span data-ttu-id="ea6a4-116">@No__t_0 参数是行标签或行号，必须与错误处理程序位于同一过程中。</span><span class="sxs-lookup"><span data-stu-id="ea6a4-116">The `line` argument is a line label or line number and must be in the same procedure as the error handler.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ea6a4-117">备注</span><span class="sxs-lookup"><span data-stu-id="ea6a4-117">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="ea6a4-118">建议尽可能地在代码中使用结构化异常处理，而不是使用非结构化异常处理和 `On Error` 和 `Resume` 语句。</span><span class="sxs-lookup"><span data-stu-id="ea6a4-118">We recommend that you use structured exception handling in your code whenever possible, rather than using unstructured exception handling and the `On Error` and `Resume` statements.</span></span> <span data-ttu-id="ea6a4-119">有关详细信息，请参阅 [Try...Catch...Finally 语句](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="ea6a4-119">For more information, see [Try...Catch...Finally Statement](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md).</span></span>  
  
 <span data-ttu-id="ea6a4-120">如果在错误处理例程中的任意位置使用 `Resume` 语句，则会发生错误。</span><span class="sxs-lookup"><span data-stu-id="ea6a4-120">If you use a `Resume` statement anywhere other than in an error-handling routine, an error occurs.</span></span>  
  
 <span data-ttu-id="ea6a4-121">不能在包含 `Try...Catch...Finally` 语句的任何过程中使用 `Resume` 语句。</span><span class="sxs-lookup"><span data-stu-id="ea6a4-121">The `Resume` statement cannot be used in any procedure that contains a `Try...Catch...Finally` statement.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ea6a4-122">示例</span><span class="sxs-lookup"><span data-stu-id="ea6a4-122">Example</span></span>  
 <span data-ttu-id="ea6a4-123">此示例使用 `Resume` 语句来结束过程中的错误处理，然后使用导致错误的语句继续执行。</span><span class="sxs-lookup"><span data-stu-id="ea6a4-123">This example uses the `Resume` statement to end error handling in a procedure and then resume execution with the statement that caused the error.</span></span> <span data-ttu-id="ea6a4-124">生成错误号55以说明 `Resume` 语句的使用。</span><span class="sxs-lookup"><span data-stu-id="ea6a4-124">Error number 55 is generated to illustrate use of the `Resume` statement.</span></span>  
  
 [!code-vb[VbVbalrErrorHandling#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrErrorHandling/VB/Class1.vb#16)]  
  
## <a name="requirements"></a><span data-ttu-id="ea6a4-125">要求</span><span class="sxs-lookup"><span data-stu-id="ea6a4-125">Requirements</span></span>  
 <span data-ttu-id="ea6a4-126">**命名空间：** [Microsoft](../../../visual-basic/language-reference/runtime-library-members.md)</span><span class="sxs-lookup"><span data-stu-id="ea6a4-126">**Namespace:** [Microsoft.VisualBasic](../../../visual-basic/language-reference/runtime-library-members.md)</span></span>  
  
 <span data-ttu-id="ea6a4-127">**程序集：** Visual Basic 运行时库（在 Microsoft. .dll 中）</span><span class="sxs-lookup"><span data-stu-id="ea6a4-127">**Assembly:** Visual Basic Runtime Library (in Microsoft.VisualBasic.dll)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ea6a4-128">请参阅</span><span class="sxs-lookup"><span data-stu-id="ea6a4-128">See also</span></span>

- [<span data-ttu-id="ea6a4-129">Try...Catch...Finally 语句</span><span class="sxs-lookup"><span data-stu-id="ea6a4-129">Try...Catch...Finally Statement</span></span>](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)
- [<span data-ttu-id="ea6a4-130">Error 语句</span><span class="sxs-lookup"><span data-stu-id="ea6a4-130">Error Statement</span></span>](../../../visual-basic/language-reference/statements/error-statement.md)
- [<span data-ttu-id="ea6a4-131">On Error 语句</span><span class="sxs-lookup"><span data-stu-id="ea6a4-131">On Error Statement</span></span>](../../../visual-basic/language-reference/statements/on-error-statement.md)
