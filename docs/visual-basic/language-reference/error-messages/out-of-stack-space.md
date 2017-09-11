---
title: "堆栈空间 (Visual Basic 中) |Microsoft 文档"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbrID28
dev_langs:
- VB
ms.assetid: bfcd792b-ac29-4158-81fc-ea0c13f4ffa2
caps.latest.revision: 8
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
ms.openlocfilehash: 256ef0c7fcb3632e0c13d12737d438225343884f
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017

---
# <a name="out-of-stack-space-visual-basic"></a><span data-ttu-id="731a1-102">堆栈空间不足 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="731a1-102">Out of stack space (Visual Basic)</span></span>
<span data-ttu-id="731a1-103">堆栈是内存的执行程序的要求使用动态增长和收缩的工作区域。</span><span class="sxs-lookup"><span data-stu-id="731a1-103">The stack is a working area of memory that grows and shrinks dynamically with the demands of your executing program.</span></span> <span data-ttu-id="731a1-104">已超出其限制。</span><span class="sxs-lookup"><span data-stu-id="731a1-104">Its limits have been exceeded.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="731a1-105">更正此错误</span><span class="sxs-lookup"><span data-stu-id="731a1-105">To correct this error</span></span>  
  
1.  <span data-ttu-id="731a1-106">检查不太深嵌套的过程。</span><span class="sxs-lookup"><span data-stu-id="731a1-106">Check that procedures are not nested too deeply.</span></span>  
  
2.  <span data-ttu-id="731a1-107">请确保正确终止递归过程。</span><span class="sxs-lookup"><span data-stu-id="731a1-107">Make sure recursive procedures terminate properly.</span></span>  
  
3.  <span data-ttu-id="731a1-108">如果本地变量所需的本地变量空间大于可用空间，请尝试在模块级别声明一些变量。</span><span class="sxs-lookup"><span data-stu-id="731a1-108">If local variables require more local variable space than is available, try declaring some variables at the module level.</span></span> <span data-ttu-id="731a1-109">您也可以声明该过程中的所有变量静态通过在其前面`Property`， `Sub`，或`Function`关键字与`Static`。</span><span class="sxs-lookup"><span data-stu-id="731a1-109">You can also declare all variables in the procedure static by preceding the `Property`, `Sub`, or `Function` keyword with `Static`.</span></span> <span data-ttu-id="731a1-110">也可以使用`Static`语句来声明过程中的单个静态变量。</span><span class="sxs-lookup"><span data-stu-id="731a1-110">Or you can use the `Static` statement to declare individual static variables within procedures.</span></span>  
  
4.  <span data-ttu-id="731a1-111">重新定义一些您固定长度的字符串为可变长度字符串，作为固定长度的字符串使用更多堆栈空间比可变长度字符串。</span><span class="sxs-lookup"><span data-stu-id="731a1-111">Redefine some of your fixed-length strings as variable-length strings, as fixed-length strings use more stack space than variable-length strings.</span></span> <span data-ttu-id="731a1-112">您还可以定义在模块级别，它不需要堆栈空间的字符串。</span><span class="sxs-lookup"><span data-stu-id="731a1-112">You can also define the string at module level where it requires no stack space.</span></span>  
  
5.  <span data-ttu-id="731a1-113">检查数嵌套`DoEvents`函数调用，通过使用`Calls`对话框查看哪些过程是否在堆栈上处于活动状态。</span><span class="sxs-lookup"><span data-stu-id="731a1-113">Check the number of nested `DoEvents` function calls, by using the `Calls` dialog box to view which procedures are active on the stack.</span></span>  
  
6.  <span data-ttu-id="731a1-114">请确保没有导致通过触发调用事件过程已在堆栈的事件"事件级联"。</span><span class="sxs-lookup"><span data-stu-id="731a1-114">Make sure you did not cause an "event cascade" by triggering an event that calls an event procedure already on the stack.</span></span> <span data-ttu-id="731a1-115">级联事件相似的终止的递归过程调用，但它是不太明显的因为默认情况下，调用通过[!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]而不是在代码中显式调用。</span><span class="sxs-lookup"><span data-stu-id="731a1-115">An event cascade is similar to an unterminated recursive procedure call, but it is less obvious, since the call is made by [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] rather than an explicit call in the code.</span></span> <span data-ttu-id="731a1-116">使用`Calls`对话框查看哪些过程是否在堆栈上处于活动状态。</span><span class="sxs-lookup"><span data-stu-id="731a1-116">Use the `Calls`dialog box to view which procedures are active on the stack.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="731a1-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="731a1-117">See Also</span></span>  
 [<span data-ttu-id="731a1-118">“内存”窗口</span><span class="sxs-lookup"><span data-stu-id="731a1-118">Memory Windows</span></span>](https://docs.microsoft.com/visualstudio/debugger/memory-windows)
