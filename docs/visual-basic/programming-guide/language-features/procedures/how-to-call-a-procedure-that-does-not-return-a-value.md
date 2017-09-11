---
title: "如何︰ 调用不返回值 (Visual Basic 中) 的过程 |Microsoft 文档"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- procedure calls, returning values
- Visual Basic code, procedures
- procedures, calling
ms.assetid: 259b49a3-a3c1-4254-ba8c-73cdc4127703
caps.latest.revision: 17
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
ms.openlocfilehash: 26120b763d2ecedb3aa43adb08e4c87c2b1e0be1
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017

---
# <a name="how-to-call-a-procedure-that-does-not-return-a-value-visual-basic"></a><span data-ttu-id="49d58-102">如何：调用不返回值的过程 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="49d58-102">How to: Call a Procedure that Does Not Return a Value (Visual Basic)</span></span>
<span data-ttu-id="49d58-103">一个`Sub`过程不返回到调用代码的一个值。</span><span class="sxs-lookup"><span data-stu-id="49d58-103">A `Sub` procedure does not return a value to the calling code.</span></span> <span data-ttu-id="49d58-104">显式调用该过程与独立的调用语句。</span><span class="sxs-lookup"><span data-stu-id="49d58-104">You call it explicitly with a stand-alone calling statement.</span></span> <span data-ttu-id="49d58-105">不能只需使用其名称在表达式中调用它。</span><span class="sxs-lookup"><span data-stu-id="49d58-105">You cannot call it by simply using its name within an expression.</span></span>  
  
### <a name="to-call-a-sub-procedure"></a><span data-ttu-id="49d58-106">若要调用 Sub 过程</span><span class="sxs-lookup"><span data-stu-id="49d58-106">To call a Sub procedure</span></span>  
  
1.  <span data-ttu-id="49d58-107">指定的名称`Sub`过程。</span><span class="sxs-lookup"><span data-stu-id="49d58-107">Specify the name of the `Sub` procedure.</span></span>  
  
2.  <span data-ttu-id="49d58-108">过程名后面加上括号将参数列表括起来。</span><span class="sxs-lookup"><span data-stu-id="49d58-108">Follow the procedure name with parentheses to enclose the argument list.</span></span> <span data-ttu-id="49d58-109">如果不有任何参数，可以选择省略括号。</span><span class="sxs-lookup"><span data-stu-id="49d58-109">If there are no arguments, you can optionally omit the parentheses.</span></span> <span data-ttu-id="49d58-110">但是，使用括号使代码易于阅读。</span><span class="sxs-lookup"><span data-stu-id="49d58-110">However, using the parentheses makes your code easier to read.</span></span>  
  
3.  <span data-ttu-id="49d58-111">将参数放在括号内，用逗号分隔参数列表中。</span><span class="sxs-lookup"><span data-stu-id="49d58-111">Place the arguments in the argument list within the parentheses, separated by commas.</span></span> <span data-ttu-id="49d58-112">请确保您的相同顺序的参数提供的`Sub`过程定义对应的参数。</span><span class="sxs-lookup"><span data-stu-id="49d58-112">Be sure you supply the arguments in the same order that the `Sub` procedure defines the corresponding parameters.</span></span>  
  
     <span data-ttu-id="49d58-113">下面的示例调用[!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]<xref:Microsoft.VisualBasic.Interaction.AppActivate%2A>函数以激活应用程序窗口。</xref:Microsoft.VisualBasic.Interaction.AppActivate%2A></span><span class="sxs-lookup"><span data-stu-id="49d58-113">The following example calls the [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] <xref:Microsoft.VisualBasic.Interaction.AppActivate%2A> function to activate an application window.</span></span> <span data-ttu-id="49d58-114"><xref:Microsoft.VisualBasic.Interaction.AppActivate%2A>将窗口标题作为其唯一的参数。</xref:Microsoft.VisualBasic.Interaction.AppActivate%2A></span><span class="sxs-lookup"><span data-stu-id="49d58-114"><xref:Microsoft.VisualBasic.Interaction.AppActivate%2A> takes the window title as its sole argument.</span></span> <span data-ttu-id="49d58-115">不返回到调用代码的一个值。</span><span class="sxs-lookup"><span data-stu-id="49d58-115">It does not return a value to the calling code.</span></span> <span data-ttu-id="49d58-116">如果未运行记事本过程，本示例将引发<xref:System.ArgumentException>。</xref:System.ArgumentException></span><span class="sxs-lookup"><span data-stu-id="49d58-116">If a Notepad process is not running, the example throws an <xref:System.ArgumentException>.</span></span> <span data-ttu-id="49d58-117">`Shell`过程假定应用程序是否在指定的路径。</span><span class="sxs-lookup"><span data-stu-id="49d58-117">The `Shell` procedure assumes the applications are in the paths specified.</span></span>  
  
     <span data-ttu-id="49d58-118">[!code-vb[VbVbalrCatRef #&11;](./codesnippet/VisualBasic/how-to-call-a-procedure-that-does-not-return-a-value_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="49d58-118">[!code-vb[VbVbalrCatRef#11](./codesnippet/VisualBasic/how-to-call-a-procedure-that-does-not-return-a-value_1.vb)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="49d58-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="49d58-119">See Also</span></span>  
 <span data-ttu-id="49d58-120"><xref:Microsoft.VisualBasic.Interaction.Shell%2A></xref:Microsoft.VisualBasic.Interaction.Shell%2A></span><span class="sxs-lookup"><span data-stu-id="49d58-120"><xref:Microsoft.VisualBasic.Interaction.Shell%2A></span></span>   
 <span data-ttu-id="49d58-121"><xref:System.ArgumentException></xref:System.ArgumentException></span><span class="sxs-lookup"><span data-stu-id="49d58-121"><xref:System.ArgumentException></span></span>   
<span data-ttu-id="49d58-122"> [过程](./index.md) </span><span class="sxs-lookup"><span data-stu-id="49d58-122"> [Procedures](./index.md) </span></span>  
<span data-ttu-id="49d58-123"> [Sub 过程](./sub-procedures.md) </span><span class="sxs-lookup"><span data-stu-id="49d58-123"> [Sub Procedures](./sub-procedures.md) </span></span>  
<span data-ttu-id="49d58-124"> [过程参数和变量](./procedure-parameters-and-arguments.md) </span><span class="sxs-lookup"><span data-stu-id="49d58-124"> [Procedure Parameters and Arguments](./procedure-parameters-and-arguments.md) </span></span>  
<span data-ttu-id="49d58-125"> [Sub 语句](../../../../visual-basic/language-reference/statements/sub-statement.md) </span><span class="sxs-lookup"><span data-stu-id="49d58-125"> [Sub Statement](../../../../visual-basic/language-reference/statements/sub-statement.md) </span></span>  
<span data-ttu-id="49d58-126"> [如何︰ 创建过程](./how-to-create-a-procedure.md) </span><span class="sxs-lookup"><span data-stu-id="49d58-126"> [How to: Create a Procedure](./how-to-create-a-procedure.md) </span></span>  
<span data-ttu-id="49d58-127"> [如何︰ 调用返回一个值的过程](./how-to-call-a-procedure-that-returns-a-value.md) </span><span class="sxs-lookup"><span data-stu-id="49d58-127"> [How to: Call a Procedure That Returns a Value](./how-to-call-a-procedure-that-returns-a-value.md) </span></span>  
<span data-ttu-id="49d58-128"> [如何︰ 在 Visual Basic 中调用事件处理程序](./how-to-call-an-event-handler.md)</span><span class="sxs-lookup"><span data-stu-id="49d58-128"> [How to: Call an Event Handler in Visual Basic](./how-to-call-an-event-handler.md)</span></span>
