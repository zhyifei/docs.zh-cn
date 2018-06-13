---
title: 如何：调用不返回值的过程 (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- procedure calls [Visual Basic], returning values
- Visual Basic code, procedures
- procedures [Visual Basic], calling
ms.assetid: 259b49a3-a3c1-4254-ba8c-73cdc4127703
ms.openlocfilehash: cf136f1486645d6e8e4b5856c0b1baf9e99f6c50
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33649043"
---
# <a name="how-to-call-a-procedure-that-does-not-return-a-value-visual-basic"></a><span data-ttu-id="38aea-102">如何：调用不返回值的过程 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="38aea-102">How to: Call a Procedure that Does Not Return a Value (Visual Basic)</span></span>
<span data-ttu-id="38aea-103">A`Sub`过程不会返回到调用代码的值。</span><span class="sxs-lookup"><span data-stu-id="38aea-103">A `Sub` procedure does not return a value to the calling code.</span></span> <span data-ttu-id="38aea-104">显式调用该过程与独立的调用语句。</span><span class="sxs-lookup"><span data-stu-id="38aea-104">You call it explicitly with a stand-alone calling statement.</span></span> <span data-ttu-id="38aea-105">不能只需通过其名称在表达式中调用它。</span><span class="sxs-lookup"><span data-stu-id="38aea-105">You cannot call it by simply using its name within an expression.</span></span>  
  
### <a name="to-call-a-sub-procedure"></a><span data-ttu-id="38aea-106">调用 Sub 过程</span><span class="sxs-lookup"><span data-stu-id="38aea-106">To call a Sub procedure</span></span>  
  
1.  <span data-ttu-id="38aea-107">指定的名称`Sub`过程。</span><span class="sxs-lookup"><span data-stu-id="38aea-107">Specify the name of the `Sub` procedure.</span></span>  
  
2.  <span data-ttu-id="38aea-108">过程名后面加上括号将自变量列表括起来。</span><span class="sxs-lookup"><span data-stu-id="38aea-108">Follow the procedure name with parentheses to enclose the argument list.</span></span> <span data-ttu-id="38aea-109">如果不有任何自变量，你可以选择省略括号。</span><span class="sxs-lookup"><span data-stu-id="38aea-109">If there are no arguments, you can optionally omit the parentheses.</span></span> <span data-ttu-id="38aea-110">但是，使用括号使得你的代码易于阅读。</span><span class="sxs-lookup"><span data-stu-id="38aea-110">However, using the parentheses makes your code easier to read.</span></span>  
  
3.  <span data-ttu-id="38aea-111">将自变量放在括号里，用逗号分隔参数列表中。</span><span class="sxs-lookup"><span data-stu-id="38aea-111">Place the arguments in the argument list within the parentheses, separated by commas.</span></span> <span data-ttu-id="38aea-112">请确保你提供的相同顺序的自变量，`Sub`过程所定义的相应参数。</span><span class="sxs-lookup"><span data-stu-id="38aea-112">Be sure you supply the arguments in the same order that the `Sub` procedure defines the corresponding parameters.</span></span>  
  
     <span data-ttu-id="38aea-113">下面的示例调用 Visual Basic<xref:Microsoft.VisualBasic.Interaction.AppActivate%2A>函数来激活应用程序窗口。</span><span class="sxs-lookup"><span data-stu-id="38aea-113">The following example calls the Visual Basic <xref:Microsoft.VisualBasic.Interaction.AppActivate%2A> function to activate an application window.</span></span> <span data-ttu-id="38aea-114"><xref:Microsoft.VisualBasic.Interaction.AppActivate%2A> 将窗口标题作为其唯一的自变量。</span><span class="sxs-lookup"><span data-stu-id="38aea-114"><xref:Microsoft.VisualBasic.Interaction.AppActivate%2A> takes the window title as its sole argument.</span></span> <span data-ttu-id="38aea-115">它不会调用的代码返回一个值。</span><span class="sxs-lookup"><span data-stu-id="38aea-115">It does not return a value to the calling code.</span></span> <span data-ttu-id="38aea-116">如果未运行 Notepad 进程，本示例将引发<xref:System.ArgumentException>。</span><span class="sxs-lookup"><span data-stu-id="38aea-116">If a Notepad process is not running, the example throws an <xref:System.ArgumentException>.</span></span> <span data-ttu-id="38aea-117">`Shell`过程假定应用程序都位于指定的路径。</span><span class="sxs-lookup"><span data-stu-id="38aea-117">The `Shell` procedure assumes the applications are in the paths specified.</span></span>  
  
     [!code-vb[VbVbalrCatRef#11](./codesnippet/VisualBasic/how-to-call-a-procedure-that-does-not-return-a-value_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="38aea-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="38aea-118">See Also</span></span>  
 <xref:Microsoft.VisualBasic.Interaction.Shell%2A>  
 <xref:System.ArgumentException>  
 [<span data-ttu-id="38aea-119">过程</span><span class="sxs-lookup"><span data-stu-id="38aea-119">Procedures</span></span>](./index.md)  
 [<span data-ttu-id="38aea-120">Sub 过程</span><span class="sxs-lookup"><span data-stu-id="38aea-120">Sub Procedures</span></span>](./sub-procedures.md)  
 [<span data-ttu-id="38aea-121">过程参数和自变量</span><span class="sxs-lookup"><span data-stu-id="38aea-121">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)  
 [<span data-ttu-id="38aea-122">Sub 语句</span><span class="sxs-lookup"><span data-stu-id="38aea-122">Sub Statement</span></span>](../../../../visual-basic/language-reference/statements/sub-statement.md)  
 [<span data-ttu-id="38aea-123">如何：创建过程</span><span class="sxs-lookup"><span data-stu-id="38aea-123">How to: Create a Procedure</span></span>](./how-to-create-a-procedure.md)  
 [<span data-ttu-id="38aea-124">如何：调用返回值的过程</span><span class="sxs-lookup"><span data-stu-id="38aea-124">How to: Call a Procedure That Returns a Value</span></span>](./how-to-call-a-procedure-that-returns-a-value.md)  
 [<span data-ttu-id="38aea-125">如何： 在 Visual Basic 中调用事件处理程序</span><span class="sxs-lookup"><span data-stu-id="38aea-125">How to: Call an Event Handler in Visual Basic</span></span>](./how-to-call-an-event-handler.md)
