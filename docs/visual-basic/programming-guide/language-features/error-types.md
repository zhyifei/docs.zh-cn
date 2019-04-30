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
ms.openlocfilehash: 07db963ac3cf9d1c0d17c420480189d362cdaf2c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61973168"
---
# <a name="error-types-visual-basic"></a><span data-ttu-id="7dbc8-102">错误类型 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7dbc8-102">Error Types (Visual Basic)</span></span>
<span data-ttu-id="7dbc8-103">在 Visual Basic 中，错误 (也称为*异常*) 分为三个类别之一： 语法错误、 运行时错误和逻辑错误。</span><span class="sxs-lookup"><span data-stu-id="7dbc8-103">In Visual Basic, errors (also called *exceptions*) fall into one of three categories: syntax errors, run-time errors, and logic errors.</span></span>  
  
## <a name="syntax-errors"></a><span data-ttu-id="7dbc8-104">语法错误</span><span class="sxs-lookup"><span data-stu-id="7dbc8-104">Syntax Errors</span></span>  
 <span data-ttu-id="7dbc8-105">*语法错误*是编写代码时出现。</span><span class="sxs-lookup"><span data-stu-id="7dbc8-105">*Syntax errors* are those that appear while you write code.</span></span> <span data-ttu-id="7dbc8-106">Visual Basic 会检查你的代码，并在您键入**代码编辑器**窗口并向你发出警报，如果出现错误，例如拼错单词或不正确地使用一个语言元素。</span><span class="sxs-lookup"><span data-stu-id="7dbc8-106">Visual Basic checks your code as you type it in the **Code Editor** window and alerts you if you make a mistake, such as misspelling a word or using a language element improperly.</span></span> <span data-ttu-id="7dbc8-107">语法错误则是最常见的错误类型。</span><span class="sxs-lookup"><span data-stu-id="7dbc8-107">Syntax errors are the most common type of errors.</span></span> <span data-ttu-id="7dbc8-108">解决方法轻松地在编码的环境中就立即发生。</span><span class="sxs-lookup"><span data-stu-id="7dbc8-108">You can fix them easily in the coding environment as soon as they occur.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7dbc8-109">`Option Explicit`语句是一种避免语法错误。</span><span class="sxs-lookup"><span data-stu-id="7dbc8-109">The `Option Explicit` statement is one means of avoiding syntax errors.</span></span> <span data-ttu-id="7dbc8-110">它会强制你提前声明要使用的应用程序中的所有变量。</span><span class="sxs-lookup"><span data-stu-id="7dbc8-110">It forces you to declare, in advance, all the variables to be used in the application.</span></span> <span data-ttu-id="7dbc8-111">因此，当在代码中使用这些变量时，版式的任何错误立即捕获，并且可以修复。</span><span class="sxs-lookup"><span data-stu-id="7dbc8-111">Therefore, when those variables are used in the code, any typographic errors are caught immediately and can be fixed.</span></span>  
  
## <a name="run-time-errors"></a><span data-ttu-id="7dbc8-112">运行时错误</span><span class="sxs-lookup"><span data-stu-id="7dbc8-112">Run-Time Errors</span></span>  
 <span data-ttu-id="7dbc8-113">*运行时错误*是仅在编译和运行你的代码后出现。</span><span class="sxs-lookup"><span data-stu-id="7dbc8-113">*Run-time errors* are those that appear only after you compile and run your code.</span></span> <span data-ttu-id="7dbc8-114">这些技术包括可能看起来是正确的它不存在语法错误，但不是会执行的代码。</span><span class="sxs-lookup"><span data-stu-id="7dbc8-114">These involve code that may appear to be correct in that it has no syntax errors, but that will not execute.</span></span> <span data-ttu-id="7dbc8-115">例如，可以正确编写一行代码打开文件。</span><span class="sxs-lookup"><span data-stu-id="7dbc8-115">For example, you might correctly write a line of code to open a file.</span></span> <span data-ttu-id="7dbc8-116">如果该文件已损坏，无法执行该应用程序，但`Open`函数，并且它将停止运行。</span><span class="sxs-lookup"><span data-stu-id="7dbc8-116">But if the file is corrupted, the application cannot carry out the `Open` function, and it stops running.</span></span> <span data-ttu-id="7dbc8-117">通过重写了错误代码，然后重新编译和重新运行它，可以修复大多数运行时错误。</span><span class="sxs-lookup"><span data-stu-id="7dbc8-117">You can fix most run-time errors by rewriting the faulty code, and then recompiling and rerunning it.</span></span>  
  
## <a name="logic-errors"></a><span data-ttu-id="7dbc8-118">逻辑错误</span><span class="sxs-lookup"><span data-stu-id="7dbc8-118">Logic Errors</span></span>  
 <span data-ttu-id="7dbc8-119">*逻辑错误*是使用应用程序后出现的。</span><span class="sxs-lookup"><span data-stu-id="7dbc8-119">*Logic errors* are those that appear once the application is in use.</span></span> <span data-ttu-id="7dbc8-120">它们是以响应用户操作的大多数通常不需要的或意外结果。</span><span class="sxs-lookup"><span data-stu-id="7dbc8-120">They are most often unwanted or unexpected results in response to user actions.</span></span> <span data-ttu-id="7dbc8-121">例如，错误键入的键或其他外部影响可能会导致你的应用程序停止工作中所需的参数，或完全。</span><span class="sxs-lookup"><span data-stu-id="7dbc8-121">For example, a mistyped key or other outside influence might cause your application to stop working within expected parameters, or altogether.</span></span> <span data-ttu-id="7dbc8-122">逻辑错误通常是最难的类型，若要解决，因为它不是始终清除它们发生的位置。</span><span class="sxs-lookup"><span data-stu-id="7dbc8-122">Logic errors are generally the hardest type to fix, since it is not always clear where they originate.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7dbc8-123">请参阅</span><span class="sxs-lookup"><span data-stu-id="7dbc8-123">See also</span></span>

- [<span data-ttu-id="7dbc8-124">Try...Catch...Finally 语句</span><span class="sxs-lookup"><span data-stu-id="7dbc8-124">Try...Catch...Finally Statement</span></span>](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)
- [<span data-ttu-id="7dbc8-125">调试器基础知识</span><span class="sxs-lookup"><span data-stu-id="7dbc8-125">Debugger Basics</span></span>](/visualstudio/debugger/debugger-basics)
