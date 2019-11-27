---
title: 堆栈空间不足
ms.date: 07/20/2015
f1_keywords:
- vbrID28
ms.assetid: bfcd792b-ac29-4158-81fc-ea0c13f4ffa2
ms.openlocfilehash: 9ae604a9727413f2705d42a4b68f5a50b7dd3feb
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74349187"
---
# <a name="out-of-stack-space-visual-basic"></a><span data-ttu-id="8dbcc-102">堆栈空间不足 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8dbcc-102">Out of stack space (Visual Basic)</span></span>
<span data-ttu-id="8dbcc-103">堆栈是内存的工作区，它随执行程序的需求动态地增长和收缩。</span><span class="sxs-lookup"><span data-stu-id="8dbcc-103">The stack is a working area of memory that grows and shrinks dynamically with the demands of your executing program.</span></span> <span data-ttu-id="8dbcc-104">已超过其限制。</span><span class="sxs-lookup"><span data-stu-id="8dbcc-104">Its limits have been exceeded.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="8dbcc-105">更正此错误</span><span class="sxs-lookup"><span data-stu-id="8dbcc-105">To correct this error</span></span>  
  
1. <span data-ttu-id="8dbcc-106">检查过程的嵌套太深。</span><span class="sxs-lookup"><span data-stu-id="8dbcc-106">Check that procedures are not nested too deeply.</span></span>  
  
2. <span data-ttu-id="8dbcc-107">请确保递归过程正确终止。</span><span class="sxs-lookup"><span data-stu-id="8dbcc-107">Make sure recursive procedures terminate properly.</span></span>  
  
3. <span data-ttu-id="8dbcc-108">如果本地变量需要的本地变量空间超过可用空间，请尝试在模块级别声明一些变量。</span><span class="sxs-lookup"><span data-stu-id="8dbcc-108">If local variables require more local variable space than is available, try declaring some variables at the module level.</span></span> <span data-ttu-id="8dbcc-109">还可以通过 `Static`将 `Property`、`Sub`或 `Function` 关键字之前的过程中的变量声明为 static。</span><span class="sxs-lookup"><span data-stu-id="8dbcc-109">You can also declare all variables in the procedure static by preceding the `Property`, `Sub`, or `Function` keyword with `Static`.</span></span> <span data-ttu-id="8dbcc-110">或者，可以使用 `Static` 语句在过程中声明单个静态变量。</span><span class="sxs-lookup"><span data-stu-id="8dbcc-110">Or you can use the `Static` statement to declare individual static variables within procedures.</span></span>  
  
4. <span data-ttu-id="8dbcc-111">将一些固定长度的字符串重新定义为可变长度字符串，因为固定长度字符串使用的堆栈空间多于可变长度字符串。</span><span class="sxs-lookup"><span data-stu-id="8dbcc-111">Redefine some of your fixed-length strings as variable-length strings, as fixed-length strings use more stack space than variable-length strings.</span></span> <span data-ttu-id="8dbcc-112">你还可以在模块级别定义不需要堆栈空间的字符串。</span><span class="sxs-lookup"><span data-stu-id="8dbcc-112">You can also define the string at module level where it requires no stack space.</span></span>  
  
5. <span data-ttu-id="8dbcc-113">通过使用 "`Calls`" 对话框查看在堆栈上处于活动状态的过程，检查嵌套 `DoEvents` 函数调用的数量。</span><span class="sxs-lookup"><span data-stu-id="8dbcc-113">Check the number of nested `DoEvents` function calls, by using the `Calls` dialog box to view which procedures are active on the stack.</span></span>  
  
6. <span data-ttu-id="8dbcc-114">请确保通过触发调用堆栈上已有的事件过程的事件，不会导致 "事件级联"。</span><span class="sxs-lookup"><span data-stu-id="8dbcc-114">Make sure you did not cause an "event cascade" by triggering an event that calls an event procedure already on the stack.</span></span> <span data-ttu-id="8dbcc-115">事件级联类似于未终止的递归过程调用，但不太明显，因为调用是通过 Visual Basic 而不是在代码中显式调用来进行的。</span><span class="sxs-lookup"><span data-stu-id="8dbcc-115">An event cascade is similar to an unterminated recursive procedure call, but it is less obvious, since the call is made by Visual Basic rather than an explicit call in the code.</span></span> <span data-ttu-id="8dbcc-116">使用 "`Calls`" 对话框可以查看在堆栈上处于活动状态的过程。</span><span class="sxs-lookup"><span data-stu-id="8dbcc-116">Use the `Calls` dialog box to view which procedures are active on the stack.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8dbcc-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8dbcc-117">See also</span></span>

- [<span data-ttu-id="8dbcc-118">“内存”窗口</span><span class="sxs-lookup"><span data-stu-id="8dbcc-118">Memory Windows</span></span>](/visualstudio/debugger/memory-windows)
