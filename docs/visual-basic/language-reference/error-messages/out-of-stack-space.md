---
title: 堆栈空间不足 (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbrID28
ms.assetid: bfcd792b-ac29-4158-81fc-ea0c13f4ffa2
caps.latest.revision: 8
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 3959c24aa4e95204e156a9863ef0ce237af1fcda
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="out-of-stack-space-visual-basic"></a><span data-ttu-id="1d79f-102">堆栈空间不足 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1d79f-102">Out of stack space (Visual Basic)</span></span>
<span data-ttu-id="1d79f-103">堆栈是内存的动态与执行程序的需求的增长和缩减的工作区域。</span><span class="sxs-lookup"><span data-stu-id="1d79f-103">The stack is a working area of memory that grows and shrinks dynamically with the demands of your executing program.</span></span> <span data-ttu-id="1d79f-104">已超出其限制。</span><span class="sxs-lookup"><span data-stu-id="1d79f-104">Its limits have been exceeded.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="1d79f-105">更正此错误</span><span class="sxs-lookup"><span data-stu-id="1d79f-105">To correct this error</span></span>  
  
1.  <span data-ttu-id="1d79f-106">检查不太深嵌套过程。</span><span class="sxs-lookup"><span data-stu-id="1d79f-106">Check that procedures are not nested too deeply.</span></span>  
  
2.  <span data-ttu-id="1d79f-107">请确保正确终止递归过程。</span><span class="sxs-lookup"><span data-stu-id="1d79f-107">Make sure recursive procedures terminate properly.</span></span>  
  
3.  <span data-ttu-id="1d79f-108">如果本地变量所需的本地变量空间大于可用空间，请尝试在模块级别声明一些变量。</span><span class="sxs-lookup"><span data-stu-id="1d79f-108">If local variables require more local variable space than is available, try declaring some variables at the module level.</span></span> <span data-ttu-id="1d79f-109">你也可以声明该过程中的所有变量静态通过在前面`Property`， `Sub`，或`Function`关键字后的跟`Static`。</span><span class="sxs-lookup"><span data-stu-id="1d79f-109">You can also declare all variables in the procedure static by preceding the `Property`, `Sub`, or `Function` keyword with `Static`.</span></span> <span data-ttu-id="1d79f-110">也可以使用`Static`语句来声明过程内的单个静态变量。</span><span class="sxs-lookup"><span data-stu-id="1d79f-110">Or you can use the `Static` statement to declare individual static variables within procedures.</span></span>  
  
4.  <span data-ttu-id="1d79f-111">重新定义一些你固定长度字符串作为可变长度字符串，因为固定长度字符串使用比可变长度字符串的更多堆栈空间。</span><span class="sxs-lookup"><span data-stu-id="1d79f-111">Redefine some of your fixed-length strings as variable-length strings, as fixed-length strings use more stack space than variable-length strings.</span></span> <span data-ttu-id="1d79f-112">你还可以定义在模块级别，它不需要堆栈空间的字符串。</span><span class="sxs-lookup"><span data-stu-id="1d79f-112">You can also define the string at module level where it requires no stack space.</span></span>  
  
5.  <span data-ttu-id="1d79f-113">检查的数嵌套`DoEvents`使用函数调用，`Calls`到哪些过程是堆栈上处于活动状态的视图的对话框。</span><span class="sxs-lookup"><span data-stu-id="1d79f-113">Check the number of nested `DoEvents` function calls, by using the `Calls` dialog box to view which procedures are active on the stack.</span></span>  
  
6.  <span data-ttu-id="1d79f-114">请确保你不会触发的事件的事件过程调用在堆栈上的已导致"事件 cascade"。</span><span class="sxs-lookup"><span data-stu-id="1d79f-114">Make sure you did not cause an "event cascade" by triggering an event that calls an event procedure already on the stack.</span></span> <span data-ttu-id="1d79f-115">级联事件类似于未终止的递归过程调用，但它是不太明显的因为默认情况下，调用通过[!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]而不是代码中显式调用。</span><span class="sxs-lookup"><span data-stu-id="1d79f-115">An event cascade is similar to an unterminated recursive procedure call, but it is less obvious, since the call is made by [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] rather than an explicit call in the code.</span></span> <span data-ttu-id="1d79f-116">使用`Calls`到哪些过程是堆栈上处于活动状态的视图的对话框。</span><span class="sxs-lookup"><span data-stu-id="1d79f-116">Use the `Calls` dialog box to view which procedures are active on the stack.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1d79f-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1d79f-117">See Also</span></span>  
 [<span data-ttu-id="1d79f-118">“内存”窗口</span><span class="sxs-lookup"><span data-stu-id="1d79f-118">Memory Windows</span></span>](/visualstudio/debugger/memory-windows)
