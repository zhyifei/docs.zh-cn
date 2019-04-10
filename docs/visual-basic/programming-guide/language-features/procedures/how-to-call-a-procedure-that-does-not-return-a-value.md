---
title: 如何：调用不返回值 (Visual Basic 中) 的过程
ms.date: 07/20/2015
helpviewer_keywords:
- procedure calls [Visual Basic], returning values
- Visual Basic code, procedures
- procedures [Visual Basic], calling
ms.assetid: 259b49a3-a3c1-4254-ba8c-73cdc4127703
ms.openlocfilehash: 6e3ce2a184ca5411a6a016929a16bf3d67e669ca
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2019
ms.locfileid: "59335467"
---
# <a name="how-to-call-a-procedure-that-does-not-return-a-value-visual-basic"></a><span data-ttu-id="5a01d-102">如何：调用不返回值 (Visual Basic 中) 的过程</span><span class="sxs-lookup"><span data-stu-id="5a01d-102">How to: Call a Procedure that Does Not Return a Value (Visual Basic)</span></span>
<span data-ttu-id="5a01d-103">一个`Sub`过程不会返回到调用代码的值。</span><span class="sxs-lookup"><span data-stu-id="5a01d-103">A `Sub` procedure does not return a value to the calling code.</span></span> <span data-ttu-id="5a01d-104">显式调用该过程与独立的调用语句。</span><span class="sxs-lookup"><span data-stu-id="5a01d-104">You call it explicitly with a stand-alone calling statement.</span></span> <span data-ttu-id="5a01d-105">不能只需使用其名称的表达式内调用它。</span><span class="sxs-lookup"><span data-stu-id="5a01d-105">You cannot call it by simply using its name within an expression.</span></span>  
  
### <a name="to-call-a-sub-procedure"></a><span data-ttu-id="5a01d-106">若要调用的 Sub 过程</span><span class="sxs-lookup"><span data-stu-id="5a01d-106">To call a Sub procedure</span></span>  
  
1. <span data-ttu-id="5a01d-107">指定的名称`Sub`过程。</span><span class="sxs-lookup"><span data-stu-id="5a01d-107">Specify the name of the `Sub` procedure.</span></span>  
  
2. <span data-ttu-id="5a01d-108">过程名后面加上括号将参数列表括起来。</span><span class="sxs-lookup"><span data-stu-id="5a01d-108">Follow the procedure name with parentheses to enclose the argument list.</span></span> <span data-ttu-id="5a01d-109">如果没有任何自变量，可以选择性地省略括号。</span><span class="sxs-lookup"><span data-stu-id="5a01d-109">If there are no arguments, you can optionally omit the parentheses.</span></span> <span data-ttu-id="5a01d-110">但是，使用括号使您的代码易于阅读。</span><span class="sxs-lookup"><span data-stu-id="5a01d-110">However, using the parentheses makes your code easier to read.</span></span>  
  
3. <span data-ttu-id="5a01d-111">将参数放在括号中，由逗号分隔参数列表中。</span><span class="sxs-lookup"><span data-stu-id="5a01d-111">Place the arguments in the argument list within the parentheses, separated by commas.</span></span> <span data-ttu-id="5a01d-112">请确保提供的相同顺序中的自变量的`Sub`过程定义的相应参数。</span><span class="sxs-lookup"><span data-stu-id="5a01d-112">Be sure you supply the arguments in the same order that the `Sub` procedure defines the corresponding parameters.</span></span>  
  
     <span data-ttu-id="5a01d-113">下面的示例调用 Visual Basic<xref:Microsoft.VisualBasic.Interaction.AppActivate%2A>函数以激活应用程序窗口。</span><span class="sxs-lookup"><span data-stu-id="5a01d-113">The following example calls the Visual Basic <xref:Microsoft.VisualBasic.Interaction.AppActivate%2A> function to activate an application window.</span></span> <xref:Microsoft.VisualBasic.Interaction.AppActivate%2A> <span data-ttu-id="5a01d-114">将窗口标题作为其唯一的参数。</span><span class="sxs-lookup"><span data-stu-id="5a01d-114">takes the window title as its sole argument.</span></span> <span data-ttu-id="5a01d-115">不会返回到调用代码的值。</span><span class="sxs-lookup"><span data-stu-id="5a01d-115">It does not return a value to the calling code.</span></span> <span data-ttu-id="5a01d-116">如果未运行 Notepad 进程，则本示例引发<xref:System.ArgumentException>。</span><span class="sxs-lookup"><span data-stu-id="5a01d-116">If a Notepad process is not running, the example throws an <xref:System.ArgumentException>.</span></span> <span data-ttu-id="5a01d-117">`Shell`过程假设应用程序中指定的路径。</span><span class="sxs-lookup"><span data-stu-id="5a01d-117">The `Shell` procedure assumes the applications are in the paths specified.</span></span>  
  
     [!code-vb[VbVbalrCatRef#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCatRef/VB/Class1.vb#11)]  
  
## <a name="see-also"></a><span data-ttu-id="5a01d-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="5a01d-118">See also</span></span>

- <xref:Microsoft.VisualBasic.Interaction.Shell%2A>
- <xref:System.ArgumentException>
- [<span data-ttu-id="5a01d-119">过程</span><span class="sxs-lookup"><span data-stu-id="5a01d-119">Procedures</span></span>](./index.md)
- [<span data-ttu-id="5a01d-120">Sub 过程</span><span class="sxs-lookup"><span data-stu-id="5a01d-120">Sub Procedures</span></span>](./sub-procedures.md)
- [<span data-ttu-id="5a01d-121">过程形参和实参</span><span class="sxs-lookup"><span data-stu-id="5a01d-121">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="5a01d-122">Sub 语句</span><span class="sxs-lookup"><span data-stu-id="5a01d-122">Sub Statement</span></span>](../../../../visual-basic/language-reference/statements/sub-statement.md)
- [<span data-ttu-id="5a01d-123">如何：创建过程</span><span class="sxs-lookup"><span data-stu-id="5a01d-123">How to: Create a Procedure</span></span>](./how-to-create-a-procedure.md)
- [<span data-ttu-id="5a01d-124">如何：调用返回值的过程</span><span class="sxs-lookup"><span data-stu-id="5a01d-124">How to: Call a Procedure That Returns a Value</span></span>](./how-to-call-a-procedure-that-returns-a-value.md)
- [<span data-ttu-id="5a01d-125">如何：在 Visual Basic 中调用事件处理程序</span><span class="sxs-lookup"><span data-stu-id="5a01d-125">How to: Call an Event Handler in Visual Basic</span></span>](./how-to-call-an-event-handler.md)
