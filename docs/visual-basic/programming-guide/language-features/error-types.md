---
title: "错误类型 (Visual Basic 中) |Microsoft 文档"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- exceptions, types
- errors [Visual Basic], types
- errors [Visual Basic], logic
- errors [Visual Basic], syntax
- logic errors, Visual Basic
- run-time errors, types of errors
- syntax errors, Visual Basic
ms.assetid: 3048aabf-8c97-4e13-9150-853769cb5f6f
caps.latest.revision: 13
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 51cf5820e79ff9467357619d4f5b067bc4168bfb
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017

---
# <a name="error-types-visual-basic"></a><span data-ttu-id="c9e3b-102">错误类型 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c9e3b-102">Error Types (Visual Basic)</span></span>
<span data-ttu-id="c9e3b-103">在[!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]，错误 (也称为*异常*) 分为三个类别之一︰ 语法错误、 运行时错误和逻辑错误。</span><span class="sxs-lookup"><span data-stu-id="c9e3b-103">In [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)], errors (also called *exceptions*) fall into one of three categories: syntax errors, run-time errors, and logic errors.</span></span>  
  
## <a name="syntax-errors"></a><span data-ttu-id="c9e3b-104">语法错误</span><span class="sxs-lookup"><span data-stu-id="c9e3b-104">Syntax Errors</span></span>  
 <span data-ttu-id="c9e3b-105">*语法错误*是指那些编写代码时出现。</span><span class="sxs-lookup"><span data-stu-id="c9e3b-105">*Syntax errors* are those that appear while you write code.</span></span> [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]<span data-ttu-id="c9e3b-106">检查您的代码，并在您键入**代码编辑器**窗口，并提醒您，如果犯错，如拼错单词或不正确地使用一个语言元素。</span><span class="sxs-lookup"><span data-stu-id="c9e3b-106"> checks your code as you type it in the **Code Editor** window and alerts you if you make a mistake, such as misspelling a word or using a language element improperly.</span></span> <span data-ttu-id="c9e3b-107">语法错误则是最常见的错误类型。</span><span class="sxs-lookup"><span data-stu-id="c9e3b-107">Syntax errors are the most common type of errors.</span></span> <span data-ttu-id="c9e3b-108">您可以解决它们轻松地在编码的环境中就立即发生。</span><span class="sxs-lookup"><span data-stu-id="c9e3b-108">You can fix them easily in the coding environment as soon as they occur.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c9e3b-109">`Option Explicit`语句是一种避免语法错误。</span><span class="sxs-lookup"><span data-stu-id="c9e3b-109">The `Option Explicit` statement is one means of avoiding syntax errors.</span></span> <span data-ttu-id="c9e3b-110">它会强制您能够提前声明应用程序中使用的所有变量。</span><span class="sxs-lookup"><span data-stu-id="c9e3b-110">It forces you to declare, in advance, all the variables to be used in the application.</span></span> <span data-ttu-id="c9e3b-111">因此，当在代码中使用这些变量时，版式的任何错误都将被立即捕获，并且可以修复。</span><span class="sxs-lookup"><span data-stu-id="c9e3b-111">Therefore, when those variables are used in the code, any typographic errors are caught immediately and can be fixed.</span></span>  
  
## <a name="run-time-errors"></a><span data-ttu-id="c9e3b-112">运行时错误</span><span class="sxs-lookup"><span data-stu-id="c9e3b-112">Run-Time Errors</span></span>  
 <span data-ttu-id="c9e3b-113">*运行时错误*是指那些仅在编译并运行您的代码后，才出现。</span><span class="sxs-lookup"><span data-stu-id="c9e3b-113">*Run-time errors* are those that appear only after you compile and run your code.</span></span> <span data-ttu-id="c9e3b-114">这些技术包括可能看上去没有问题，因为它有没有语法错误，但不是会执行的代码。</span><span class="sxs-lookup"><span data-stu-id="c9e3b-114">These involve code that may appear to be correct in that it has no syntax errors, but that will not execute.</span></span> <span data-ttu-id="c9e3b-115">例如，您可能正确编写一行代码打开文件。</span><span class="sxs-lookup"><span data-stu-id="c9e3b-115">For example, you might correctly write a line of code to open a file.</span></span> <span data-ttu-id="c9e3b-116">如果该文件已损坏，无法执行该应用程序，但`Open`函数，并且它将停止运行。</span><span class="sxs-lookup"><span data-stu-id="c9e3b-116">But if the file is corrupted, the application cannot carry out the `Open` function, and it stops running.</span></span> <span data-ttu-id="c9e3b-117">通过重写了错误代码，然后重新编译并重新运行它，可以修复大多数运行时错误。</span><span class="sxs-lookup"><span data-stu-id="c9e3b-117">You can fix most run-time errors by rewriting the faulty code, and then recompiling and rerunning it.</span></span>  
  
## <a name="logic-errors"></a><span data-ttu-id="c9e3b-118">逻辑错误</span><span class="sxs-lookup"><span data-stu-id="c9e3b-118">Logic Errors</span></span>  
 <span data-ttu-id="c9e3b-119">*逻辑错误*是指那些正在使用应用程序后显示。</span><span class="sxs-lookup"><span data-stu-id="c9e3b-119">*Logic errors* are those that appear once the application is in use.</span></span> <span data-ttu-id="c9e3b-120">它们是以响应用户操作的大多数通常不需要的或意外结果。</span><span class="sxs-lookup"><span data-stu-id="c9e3b-120">They are most often unwanted or unexpected results in response to user actions.</span></span> <span data-ttu-id="c9e3b-121">例如，错误键入的键或其他外部影响可能会导致您的应用程序停止工作中预期的参数，或完全。</span><span class="sxs-lookup"><span data-stu-id="c9e3b-121">For example, a mistyped key or other outside influence might cause your application to stop working within expected parameters, or altogether.</span></span> <span data-ttu-id="c9e3b-122">逻辑错误通常是最难的类型，若要修复，因为它不是始终清除它们发生的位置。</span><span class="sxs-lookup"><span data-stu-id="c9e3b-122">Logic errors are generally the hardest type to fix, since it is not always clear where they originate.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c9e3b-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c9e3b-123">See Also</span></span>  
 <span data-ttu-id="c9e3b-124">[Try...Catch...Finally 语句](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md) </span><span class="sxs-lookup"><span data-stu-id="c9e3b-124">[Try...Catch...Finally Statement](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md) </span></span>  
<span data-ttu-id="c9e3b-125"> [调试器基础知识](https://docs.microsoft.com/visualstudio/debugger/debugger-basics)</span><span class="sxs-lookup"><span data-stu-id="c9e3b-125"> [Debugger Basics](https://docs.microsoft.com/visualstudio/debugger/debugger-basics)</span></span>
