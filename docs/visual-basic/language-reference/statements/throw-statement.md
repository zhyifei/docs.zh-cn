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
ms.openlocfilehash: 2494eac2f61f112f3ba6321ada7404f8cd618049
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/02/2019
ms.locfileid: "58821361"
---
# <a name="throw-statement-visual-basic"></a><span data-ttu-id="3d50e-102">Throw 语句 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3d50e-102">Throw Statement (Visual Basic)</span></span>
<span data-ttu-id="3d50e-103">引发异常过程中。</span><span class="sxs-lookup"><span data-stu-id="3d50e-103">Throws an exception within a procedure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3d50e-104">语法</span><span class="sxs-lookup"><span data-stu-id="3d50e-104">Syntax</span></span>  
  
```  
Throw [ expression ]  
```  
  
## <a name="part"></a><span data-ttu-id="3d50e-105">部件</span><span class="sxs-lookup"><span data-stu-id="3d50e-105">Part</span></span>  
 `expression`  
 <span data-ttu-id="3d50e-106">提供有关要引发的异常信息。</span><span class="sxs-lookup"><span data-stu-id="3d50e-106">Provides information about the exception to be thrown.</span></span> <span data-ttu-id="3d50e-107">驻留在中时是可选的`Catch`语句，另有要求。</span><span class="sxs-lookup"><span data-stu-id="3d50e-107">Optional when residing in a `Catch` statement, otherwise required.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3d50e-108">备注</span><span class="sxs-lookup"><span data-stu-id="3d50e-108">Remarks</span></span>  
 <span data-ttu-id="3d50e-109">`Throw`语句将引发异常，您可以使用结构化异常处理代码来处理 (`Try`...`Catch`...`Finally`) 或非结构化的异常处理代码 (`On Error GoTo`)。</span><span class="sxs-lookup"><span data-stu-id="3d50e-109">The `Throw` statement throws an exception that you can handle with structured exception-handling code (`Try`...`Catch`...`Finally`) or unstructured exception-handling code (`On Error GoTo`).</span></span> <span data-ttu-id="3d50e-110">可以使用`Throw`语句来捕获在代码中的错误，因为直到找到相应的异常处理代码，Visual Basic 调用堆栈向上移动。</span><span class="sxs-lookup"><span data-stu-id="3d50e-110">You can use the `Throw` statement to trap errors within your code because Visual Basic moves up the call stack until it finds the appropriate exception-handling code.</span></span>  
  
 <span data-ttu-id="3d50e-111">一个`Throw`不包含表达式的语句仅可在`Catch`语句，在其中 case 语句重新引发当前处理的异常`Catch`语句。</span><span class="sxs-lookup"><span data-stu-id="3d50e-111">A `Throw` statement with no expression can only be used in a `Catch` statement, in which case the statement rethrows the exception currently being handled by the `Catch` statement.</span></span>  
  
 <span data-ttu-id="3d50e-112">`Throw`语句将重置的调用堆栈`expression`异常。</span><span class="sxs-lookup"><span data-stu-id="3d50e-112">The `Throw` statement resets the call stack for the `expression` exception.</span></span> <span data-ttu-id="3d50e-113">如果`expression`未提供，调用堆栈将保持不变。</span><span class="sxs-lookup"><span data-stu-id="3d50e-113">If `expression` is not provided, the call stack is left unchanged.</span></span> <span data-ttu-id="3d50e-114">您可以访问通过异常的调用堆栈<xref:System.Exception.StackTrace%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="3d50e-114">You can access the call stack for the exception through the <xref:System.Exception.StackTrace%2A> property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3d50e-115">示例</span><span class="sxs-lookup"><span data-stu-id="3d50e-115">Example</span></span>  
 <span data-ttu-id="3d50e-116">下面的代码使用`Throw`语句引发异常：</span><span class="sxs-lookup"><span data-stu-id="3d50e-116">The following code uses the `Throw` statement to throw an exception:</span></span>  
  
 [!code-vb[VbVbalrStatements#84](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#84)]  
  
## <a name="requirements"></a><span data-ttu-id="3d50e-117">要求</span><span class="sxs-lookup"><span data-stu-id="3d50e-117">Requirements</span></span>  
 <span data-ttu-id="3d50e-118">**命名空间：**[Microsoft.VisualBasic](../../../visual-basic/language-reference/runtime-library-members.md)</span><span class="sxs-lookup"><span data-stu-id="3d50e-118">**Namespace:** [Microsoft.VisualBasic](../../../visual-basic/language-reference/runtime-library-members.md)</span></span>  
  
 <span data-ttu-id="3d50e-119">**模块：** `Interaction`</span><span class="sxs-lookup"><span data-stu-id="3d50e-119">**Module:** `Interaction`</span></span>  
  
 <span data-ttu-id="3d50e-120">**程序集：** Visual Basic 运行库（在 Microsoft.VisualBasic.dll 中）</span><span class="sxs-lookup"><span data-stu-id="3d50e-120">**Assembly:** Visual Basic Runtime Library (in Microsoft.VisualBasic.dll)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3d50e-121">请参阅</span><span class="sxs-lookup"><span data-stu-id="3d50e-121">See also</span></span>

- [<span data-ttu-id="3d50e-122">Try...Catch...Finally 语句</span><span class="sxs-lookup"><span data-stu-id="3d50e-122">Try...Catch...Finally Statement</span></span>](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)
- [<span data-ttu-id="3d50e-123">On Error 语句</span><span class="sxs-lookup"><span data-stu-id="3d50e-123">On Error Statement</span></span>](../../../visual-basic/language-reference/statements/on-error-statement.md)
