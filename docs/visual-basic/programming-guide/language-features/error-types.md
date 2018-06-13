---
title: 错误类型 (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- exceptions, types
- errors [Visual Basic], types
- errors [Visual Basic], logic
- errors [Visual Basic], syntax
- logic errors [Visual Basic], Visual Basic
- run-time errors [Visual Basic], types of errors
- syntax errors [Visual Basic], Visual Basic
ms.assetid: 3048aabf-8c97-4e13-9150-853769cb5f6f
ms.openlocfilehash: c11b7f41dee57fc52ca1dff75734ad0b27b6a43a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33647106"
---
# <a name="error-types-visual-basic"></a><span data-ttu-id="e4ee5-102">错误类型 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e4ee5-102">Error Types (Visual Basic)</span></span>
<span data-ttu-id="e4ee5-103">在 Visual Basic 中，错误 (也称为*异常*) 分为三个类别之一： 语法错误、 运行时错误和逻辑错误。</span><span class="sxs-lookup"><span data-stu-id="e4ee5-103">In Visual Basic, errors (also called *exceptions*) fall into one of three categories: syntax errors, run-time errors, and logic errors.</span></span>  
  
## <a name="syntax-errors"></a><span data-ttu-id="e4ee5-104">语法错误</span><span class="sxs-lookup"><span data-stu-id="e4ee5-104">Syntax Errors</span></span>  
 <span data-ttu-id="e4ee5-105">*语法错误*是指那些编写代码时出现。</span><span class="sxs-lookup"><span data-stu-id="e4ee5-105">*Syntax errors* are those that appear while you write code.</span></span> <span data-ttu-id="e4ee5-106">Visual Basic 检查你的代码，并在你键入**代码编辑器**窗口，并提醒你如果你的错误，如拼错单词或不正确地使用一个语言元素。</span><span class="sxs-lookup"><span data-stu-id="e4ee5-106">Visual Basic checks your code as you type it in the **Code Editor** window and alerts you if you make a mistake, such as misspelling a word or using a language element improperly.</span></span> <span data-ttu-id="e4ee5-107">语法错误是最常见的错误类型。</span><span class="sxs-lookup"><span data-stu-id="e4ee5-107">Syntax errors are the most common type of errors.</span></span> <span data-ttu-id="e4ee5-108">你可以轻松地更正这些编码的环境中就会立即发生。</span><span class="sxs-lookup"><span data-stu-id="e4ee5-108">You can fix them easily in the coding environment as soon as they occur.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e4ee5-109">`Option Explicit`语句是一种避免语法错误。</span><span class="sxs-lookup"><span data-stu-id="e4ee5-109">The `Option Explicit` statement is one means of avoiding syntax errors.</span></span> <span data-ttu-id="e4ee5-110">它会强制您可以声明，提前，所有应用程序中使用的变量。</span><span class="sxs-lookup"><span data-stu-id="e4ee5-110">It forces you to declare, in advance, all the variables to be used in the application.</span></span> <span data-ttu-id="e4ee5-111">因此，如果这些变量将用在代码中，任何排字错误立即捕获，并且可以固定的。</span><span class="sxs-lookup"><span data-stu-id="e4ee5-111">Therefore, when those variables are used in the code, any typographic errors are caught immediately and can be fixed.</span></span>  
  
## <a name="run-time-errors"></a><span data-ttu-id="e4ee5-112">运行时错误</span><span class="sxs-lookup"><span data-stu-id="e4ee5-112">Run-Time Errors</span></span>  
 <span data-ttu-id="e4ee5-113">*运行时错误*是指那些仅在编译和运行你的代码后，才出现。</span><span class="sxs-lookup"><span data-stu-id="e4ee5-113">*Run-time errors* are those that appear only after you compile and run your code.</span></span> <span data-ttu-id="e4ee5-114">这些技术包括可能看起来是正确的因为它具有语法错误，但不是会执行的代码。</span><span class="sxs-lookup"><span data-stu-id="e4ee5-114">These involve code that may appear to be correct in that it has no syntax errors, but that will not execute.</span></span> <span data-ttu-id="e4ee5-115">例如，你可以正确编写一行代码以打开文件。</span><span class="sxs-lookup"><span data-stu-id="e4ee5-115">For example, you might correctly write a line of code to open a file.</span></span> <span data-ttu-id="e4ee5-116">如果文件已损坏，无法执行应用程序，但`Open`函数，它会停止运行。</span><span class="sxs-lookup"><span data-stu-id="e4ee5-116">But if the file is corrupted, the application cannot carry out the `Open` function, and it stops running.</span></span> <span data-ttu-id="e4ee5-117">你可以通过重写故障代码，然后重新编译并重新运行该解决大多数运行时错误。</span><span class="sxs-lookup"><span data-stu-id="e4ee5-117">You can fix most run-time errors by rewriting the faulty code, and then recompiling and rerunning it.</span></span>  
  
## <a name="logic-errors"></a><span data-ttu-id="e4ee5-118">逻辑错误</span><span class="sxs-lookup"><span data-stu-id="e4ee5-118">Logic Errors</span></span>  
 <span data-ttu-id="e4ee5-119">*逻辑错误*是指那些出现一次应用程序正在使用。</span><span class="sxs-lookup"><span data-stu-id="e4ee5-119">*Logic errors* are those that appear once the application is in use.</span></span> <span data-ttu-id="e4ee5-120">它们是以响应用户操作的大多数通常不需要或意外结果。</span><span class="sxs-lookup"><span data-stu-id="e4ee5-120">They are most often unwanted or unexpected results in response to user actions.</span></span> <span data-ttu-id="e4ee5-121">例如，键入的密钥或其他外部的影响可能会导致应用程序停止工作预期参数中或完全。</span><span class="sxs-lookup"><span data-stu-id="e4ee5-121">For example, a mistyped key or other outside influence might cause your application to stop working within expected parameters, or altogether.</span></span> <span data-ttu-id="e4ee5-122">逻辑错误通常是最难的类型，若要解决，因为并不总是清除它们发生的位置。</span><span class="sxs-lookup"><span data-stu-id="e4ee5-122">Logic errors are generally the hardest type to fix, since it is not always clear where they originate.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e4ee5-123">请参阅</span><span class="sxs-lookup"><span data-stu-id="e4ee5-123">See Also</span></span>  
 [<span data-ttu-id="e4ee5-124">Try...Catch...Finally 语句</span><span class="sxs-lookup"><span data-stu-id="e4ee5-124">Try...Catch...Finally Statement</span></span>](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)  
 [<span data-ttu-id="e4ee5-125">调试器基础知识</span><span class="sxs-lookup"><span data-stu-id="e4ee5-125">Debugger Basics</span></span>](/visualstudio/debugger/debugger-basics)
