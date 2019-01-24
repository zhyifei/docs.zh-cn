---
title: 堆栈空间不足 (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vbrID28
ms.assetid: bfcd792b-ac29-4158-81fc-ea0c13f4ffa2
ms.openlocfilehash: 2f91763888069b6dca90da03995dc1b6812fd426
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54655486"
---
# <a name="out-of-stack-space-visual-basic"></a><span data-ttu-id="627c8-102">堆栈空间不足 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="627c8-102">Out of stack space (Visual Basic)</span></span>
<span data-ttu-id="627c8-103">堆栈是内存的动态与正在执行程序的需求的增长和压缩的工作区域。</span><span class="sxs-lookup"><span data-stu-id="627c8-103">The stack is a working area of memory that grows and shrinks dynamically with the demands of your executing program.</span></span> <span data-ttu-id="627c8-104">已超出其限制。</span><span class="sxs-lookup"><span data-stu-id="627c8-104">Its limits have been exceeded.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="627c8-105">更正此错误</span><span class="sxs-lookup"><span data-stu-id="627c8-105">To correct this error</span></span>  
  
1.  <span data-ttu-id="627c8-106">检查不太深嵌套过程。</span><span class="sxs-lookup"><span data-stu-id="627c8-106">Check that procedures are not nested too deeply.</span></span>  
  
2.  <span data-ttu-id="627c8-107">请确保正确终止递归过程。</span><span class="sxs-lookup"><span data-stu-id="627c8-107">Make sure recursive procedures terminate properly.</span></span>  
  
3.  <span data-ttu-id="627c8-108">如果本地变量所需的本地变量空间大于可用空间，请尝试在模块级别声明一些变量。</span><span class="sxs-lookup"><span data-stu-id="627c8-108">If local variables require more local variable space than is available, try declaring some variables at the module level.</span></span> <span data-ttu-id="627c8-109">您也可以声明该过程中的所有变量静态通过前面`Property`， `Sub`，或`Function`关键字与`Static`。</span><span class="sxs-lookup"><span data-stu-id="627c8-109">You can also declare all variables in the procedure static by preceding the `Property`, `Sub`, or `Function` keyword with `Static`.</span></span> <span data-ttu-id="627c8-110">也可以使用`Static`语句声明过程内的单个静态变量。</span><span class="sxs-lookup"><span data-stu-id="627c8-110">Or you can use the `Static` statement to declare individual static variables within procedures.</span></span>  
  
4.  <span data-ttu-id="627c8-111">重新定义的一些可变长度字符串，作为你固定长度字符串作为固定长度字符串使用比可变长度字符串的更多堆栈空间。</span><span class="sxs-lookup"><span data-stu-id="627c8-111">Redefine some of your fixed-length strings as variable-length strings, as fixed-length strings use more stack space than variable-length strings.</span></span> <span data-ttu-id="627c8-112">此外可以定义在模块级别，它不需要堆栈空间的字符串。</span><span class="sxs-lookup"><span data-stu-id="627c8-112">You can also define the string at module level where it requires no stack space.</span></span>  
  
5.  <span data-ttu-id="627c8-113">检查的数量嵌套`DoEvents`通过使用函数调用，`Calls`对话框，以便查看活动在堆栈上的过程。</span><span class="sxs-lookup"><span data-stu-id="627c8-113">Check the number of nested `DoEvents` function calls, by using the `Calls` dialog box to view which procedures are active on the stack.</span></span>  
  
6.  <span data-ttu-id="627c8-114">请确保你不会通过触发的事件的事件过程调用堆栈上的已导致"事件级联"。</span><span class="sxs-lookup"><span data-stu-id="627c8-114">Make sure you did not cause an "event cascade" by triggering an event that calls an event procedure already on the stack.</span></span> <span data-ttu-id="627c8-115">级联事件类似于未终止的递归过程调用，但是它不太明显，因为默认情况下，调用由 Visual Basic 而不是在代码中显式调用。</span><span class="sxs-lookup"><span data-stu-id="627c8-115">An event cascade is similar to an unterminated recursive procedure call, but it is less obvious, since the call is made by Visual Basic rather than an explicit call in the code.</span></span> <span data-ttu-id="627c8-116">使用`Calls`对话框，以便查看活动在堆栈上的过程。</span><span class="sxs-lookup"><span data-stu-id="627c8-116">Use the `Calls` dialog box to view which procedures are active on the stack.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="627c8-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="627c8-117">See also</span></span>
- [<span data-ttu-id="627c8-118">“内存”窗口</span><span class="sxs-lookup"><span data-stu-id="627c8-118">Memory Windows</span></span>](/visualstudio/debugger/memory-windows)
