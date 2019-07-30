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
ms.openlocfilehash: a6d10982cf199e9285334e0d72e6622275d51b4d
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/30/2019
ms.locfileid: "68626192"
---
# <a name="throw-statement-visual-basic"></a><span data-ttu-id="45bf6-102">Throw 语句 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="45bf6-102">Throw Statement (Visual Basic)</span></span>
<span data-ttu-id="45bf6-103">在过程中引发异常。</span><span class="sxs-lookup"><span data-stu-id="45bf6-103">Throws an exception within a procedure.</span></span>

## <a name="syntax"></a><span data-ttu-id="45bf6-104">语法</span><span class="sxs-lookup"><span data-stu-id="45bf6-104">Syntax</span></span>

```vb
Throw [ expression ]
```

## <a name="part"></a><span data-ttu-id="45bf6-105">部件</span><span class="sxs-lookup"><span data-stu-id="45bf6-105">Part</span></span>
 <span data-ttu-id="45bf6-106">`expression`提供有关要引发的异常的信息。</span><span class="sxs-lookup"><span data-stu-id="45bf6-106">`expression` Provides information about the exception to be thrown.</span></span> <span data-ttu-id="45bf6-107">如果位于`Catch`语句中, 则为可选; 否则为必需。</span><span class="sxs-lookup"><span data-stu-id="45bf6-107">Optional when residing in a `Catch` statement, otherwise required.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="45bf6-108">备注</span><span class="sxs-lookup"><span data-stu-id="45bf6-108">Remarks</span></span>
 <span data-ttu-id="45bf6-109">语句引发异常, 你可以使用结构化异常处理代码 (`Try`... `Throw``Catch`...) 或非结构化异常处理代码`On Error GoTo`()。 `Finally`</span><span class="sxs-lookup"><span data-stu-id="45bf6-109">The `Throw` statement throws an exception that you can handle with structured exception-handling code (`Try`...`Catch`...`Finally`) or unstructured exception-handling code (`On Error GoTo`).</span></span> <span data-ttu-id="45bf6-110">您可以使用`Throw`语句来捕获代码中的错误, 因为 Visual Basic 在调用堆栈中向上移动, 直到找到相应的异常处理代码。</span><span class="sxs-lookup"><span data-stu-id="45bf6-110">You can use the `Throw` statement to trap errors within your code because Visual Basic moves up the call stack until it finds the appropriate exception-handling code.</span></span>
 
 <span data-ttu-id="45bf6-111">不带 expression 的`Catch` `Catch`语句只能用在语句中, 在这种情况下, 该语句重新引发语句当前正在处理的异常。 `Throw`</span><span class="sxs-lookup"><span data-stu-id="45bf6-111">A `Throw` statement with no expression can only be used in a `Catch` statement, in which case the statement rethrows the exception currently being handled by the `Catch` statement.</span></span>

 <span data-ttu-id="45bf6-112">语句重置`expression`异常的调用堆栈。 `Throw`</span><span class="sxs-lookup"><span data-stu-id="45bf6-112">The `Throw` statement resets the call stack for the `expression` exception.</span></span> <span data-ttu-id="45bf6-113">如果`expression`未提供, 则调用堆栈保持不变。</span><span class="sxs-lookup"><span data-stu-id="45bf6-113">If `expression` is not provided, the call stack is left unchanged.</span></span> <span data-ttu-id="45bf6-114">您可以通过<xref:System.Exception.StackTrace%2A>属性访问异常的调用堆栈。</span><span class="sxs-lookup"><span data-stu-id="45bf6-114">You can access the call stack for the exception through the <xref:System.Exception.StackTrace%2A> property.</span></span>

## <a name="example"></a><span data-ttu-id="45bf6-115">示例</span><span class="sxs-lookup"><span data-stu-id="45bf6-115">Example</span></span>
 <span data-ttu-id="45bf6-116">下面的代码使用`Throw`语句引发异常:</span><span class="sxs-lookup"><span data-stu-id="45bf6-116">The following code uses the `Throw` statement to throw an exception:</span></span>
 
 [!code-vb[VbVbalrStatements#84](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#84)]

  
## <a name="see-also"></a><span data-ttu-id="45bf6-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="45bf6-117">See also</span></span>

- [<span data-ttu-id="45bf6-118">Try...Catch...Finally 语句</span><span class="sxs-lookup"><span data-stu-id="45bf6-118">Try...Catch...Finally Statement</span></span>](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)
- [<span data-ttu-id="45bf6-119">On Error 语句</span><span class="sxs-lookup"><span data-stu-id="45bf6-119">On Error Statement</span></span>](../../../visual-basic/language-reference/statements/on-error-statement.md)
