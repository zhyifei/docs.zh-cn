---
title: Throw 语句
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
ms.openlocfilehash: 147345990b625e034e651e69b322bc098d0bd8de
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74352784"
---
# <a name="throw-statement-visual-basic"></a><span data-ttu-id="a7826-102">Throw 语句 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a7826-102">Throw Statement (Visual Basic)</span></span>

<span data-ttu-id="a7826-103">在过程中引发异常。</span><span class="sxs-lookup"><span data-stu-id="a7826-103">Throws an exception within a procedure.</span></span>

## <a name="syntax"></a><span data-ttu-id="a7826-104">语法</span><span class="sxs-lookup"><span data-stu-id="a7826-104">Syntax</span></span>

```vb
Throw [ expression ]
```

## <a name="part"></a><span data-ttu-id="a7826-105">部件</span><span class="sxs-lookup"><span data-stu-id="a7826-105">Part</span></span>

`expression`\
<span data-ttu-id="a7826-106">提供有关要引发的异常的信息。</span><span class="sxs-lookup"><span data-stu-id="a7826-106">Provides information about the exception to be thrown.</span></span> <span data-ttu-id="a7826-107">如果位于 `Catch` 语句中，则为可选; 否则为必需。</span><span class="sxs-lookup"><span data-stu-id="a7826-107">Optional when residing in a `Catch` statement, otherwise required.</span></span>

## <a name="remarks"></a><span data-ttu-id="a7826-108">备注</span><span class="sxs-lookup"><span data-stu-id="a7826-108">Remarks</span></span>

<span data-ttu-id="a7826-109">`Throw` 语句引发异常，你可以使用结构化异常处理代码（`Try`...`Catch`...`Finally`）或非结构化异常处理代码（`On Error GoTo`）处理该异常。</span><span class="sxs-lookup"><span data-stu-id="a7826-109">The `Throw` statement throws an exception that you can handle with structured exception-handling code (`Try`...`Catch`...`Finally`) or unstructured exception-handling code (`On Error GoTo`).</span></span> <span data-ttu-id="a7826-110">您可以使用 `Throw` 语句来捕获代码中的错误，因为 Visual Basic 会在调用堆栈中向上移动，直到找到相应的异常处理代码。</span><span class="sxs-lookup"><span data-stu-id="a7826-110">You can use the `Throw` statement to trap errors within your code because Visual Basic moves up the call stack until it finds the appropriate exception-handling code.</span></span>

<span data-ttu-id="a7826-111">不带 expression 的 `Throw` 语句只能在 `Catch` 语句中使用，在这种情况下，该语句再次引发 `Catch` 语句正在处理的异常。</span><span class="sxs-lookup"><span data-stu-id="a7826-111">A `Throw` statement with no expression can only be used in a `Catch` statement, in which case the statement rethrows the exception currently being handled by the `Catch` statement.</span></span>

<span data-ttu-id="a7826-112">`Throw` 语句重置 `expression` 异常的调用堆栈。</span><span class="sxs-lookup"><span data-stu-id="a7826-112">The `Throw` statement resets the call stack for the `expression` exception.</span></span> <span data-ttu-id="a7826-113">如果未提供 `expression`，则调用堆栈保持不变。</span><span class="sxs-lookup"><span data-stu-id="a7826-113">If `expression` is not provided, the call stack is left unchanged.</span></span> <span data-ttu-id="a7826-114">可以通过 <xref:System.Exception.StackTrace%2A> 属性访问异常的调用堆栈。</span><span class="sxs-lookup"><span data-stu-id="a7826-114">You can access the call stack for the exception through the <xref:System.Exception.StackTrace%2A> property.</span></span>

## <a name="example"></a><span data-ttu-id="a7826-115">示例</span><span class="sxs-lookup"><span data-stu-id="a7826-115">Example</span></span>

<span data-ttu-id="a7826-116">下面的代码使用 `Throw` 语句来引发异常：</span><span class="sxs-lookup"><span data-stu-id="a7826-116">The following code uses the `Throw` statement to throw an exception:</span></span>

[!code-vb[VbVbalrStatements#84](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#84)]

## <a name="see-also"></a><span data-ttu-id="a7826-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a7826-117">See also</span></span>

- [<span data-ttu-id="a7826-118">Try...Catch...Finally 语句</span><span class="sxs-lookup"><span data-stu-id="a7826-118">Try...Catch...Finally Statement</span></span>](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)
- [<span data-ttu-id="a7826-119">On Error 语句</span><span class="sxs-lookup"><span data-stu-id="a7826-119">On Error Statement</span></span>](../../../visual-basic/language-reference/statements/on-error-statement.md)
