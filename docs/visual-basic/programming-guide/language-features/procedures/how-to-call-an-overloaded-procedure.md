---
title: "如何：调用重载过程 (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- Visual Basic code, procedures
- procedures [Visual Basic], overloading
- procedures [Visual Basic], calling
- procedures [Visual Basic], multiple versions
- procedure calls [Visual Basic], overloaded
ms.assetid: 3bb331fb-f6bc-406f-9ca0-9609b497014c
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: ff5967c1b09ad59f249297b1cf0a4ed900faf4a1
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-call-an-overloaded-procedure-visual-basic"></a><span data-ttu-id="53690-102">如何：调用重载过程 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="53690-102">How to: Call an Overloaded Procedure (Visual Basic)</span></span>
<span data-ttu-id="53690-103">重载过程的优点是在调用的灵活性。</span><span class="sxs-lookup"><span data-stu-id="53690-103">The advantage of overloading a procedure is in the flexibility of the call.</span></span> <span data-ttu-id="53690-104">调用代码可以获得它需要传递给过程，然后调用的单一过程名称，无论它传递的哪些自变量的信息。</span><span class="sxs-lookup"><span data-stu-id="53690-104">The calling code can obtain the information it needs to pass to the procedure and then call a single procedure name, no matter what arguments it is passing.</span></span>  
  
### <a name="to-call-a-procedure-that-has-more-than-one-version-defined"></a><span data-ttu-id="53690-105">若要调用具有多个定义版本的过程</span><span class="sxs-lookup"><span data-stu-id="53690-105">To call a procedure that has more than one version defined</span></span>  
  
1.  <span data-ttu-id="53690-106">在调用代码中，确定要传递给过程的数据。</span><span class="sxs-lookup"><span data-stu-id="53690-106">In the calling code, determine which data to pass to the procedure.</span></span>  
  
2.  <span data-ttu-id="53690-107">以正常方式，参数列表中提供数据编写过程调用。</span><span class="sxs-lookup"><span data-stu-id="53690-107">Write the procedure call in the normal way, presenting the data in the argument list.</span></span> <span data-ttu-id="53690-108">请确保参数与参数列表中为过程定义的版本之一相匹配。</span><span class="sxs-lookup"><span data-stu-id="53690-108">Be sure the arguments match the parameter list in one of the versions defined for the procedure.</span></span>  
  
3.  <span data-ttu-id="53690-109">无需确定哪个版本的过程调用。</span><span class="sxs-lookup"><span data-stu-id="53690-109">You do not have to determine which version of the procedure to call.</span></span> [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]<span data-ttu-id="53690-110">将控制权传递给匹配自变量列表的版本。</span><span class="sxs-lookup"><span data-stu-id="53690-110"> passes control to the version matching your argument list.</span></span>  
  
     <span data-ttu-id="53690-111">下面的示例调用`post`过程中，声明[How to： 过程的定义多个版本](./how-to-define-multiple-versions-of-a-procedure.md)。</span><span class="sxs-lookup"><span data-stu-id="53690-111">The following example calls the `post` procedure declared in [How to: Define Multiple Versions of a Procedure](./how-to-define-multiple-versions-of-a-procedure.md).</span></span> <span data-ttu-id="53690-112">它会获取的客户标识，确定它是否`String`或`Integer`，然后在任一情况下调用相同的过程。</span><span class="sxs-lookup"><span data-stu-id="53690-112">It obtains the customer identification, determines whether it is a `String` or an `Integer`, and then in either case calls the same procedure.</span></span>  
  
     [!code-vb[VbVbcnProcedures#56](./codesnippet/VisualBasic/how-to-call-an-overloaded-procedure_1.vb)]  
  
     [!code-vb[VbVbcnProcedures#57](./codesnippet/VisualBasic/how-to-call-an-overloaded-procedure_2.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="53690-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="53690-113">See Also</span></span>  
 [<span data-ttu-id="53690-114">过程</span><span class="sxs-lookup"><span data-stu-id="53690-114">Procedures</span></span>](./index.md)  
 [<span data-ttu-id="53690-115">过程参数和自变量</span><span class="sxs-lookup"><span data-stu-id="53690-115">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)  
 [<span data-ttu-id="53690-116">过程重载</span><span class="sxs-lookup"><span data-stu-id="53690-116">Procedure Overloading</span></span>](./procedure-overloading.md)  
 [<span data-ttu-id="53690-117">过程疑难解答</span><span class="sxs-lookup"><span data-stu-id="53690-117">Troubleshooting Procedures</span></span>](./troubleshooting-procedures.md)  
 [<span data-ttu-id="53690-118">如何：定义一个过程的多个版本</span><span class="sxs-lookup"><span data-stu-id="53690-118">How to: Define Multiple Versions of a Procedure</span></span>](./how-to-define-multiple-versions-of-a-procedure.md)  
 [<span data-ttu-id="53690-119">如何：重载带有可选参数的过程</span><span class="sxs-lookup"><span data-stu-id="53690-119">How to: Overload a Procedure that Takes Optional Parameters</span></span>](./how-to-overload-a-procedure-that-takes-optional-parameters.md)  
 [<span data-ttu-id="53690-120">如何：重载参数数量不确定的过程</span><span class="sxs-lookup"><span data-stu-id="53690-120">How to: Overload a Procedure that Takes an Indefinite Number of Parameters</span></span>](./how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters.md)  
 [<span data-ttu-id="53690-121">重载过程注意事项</span><span class="sxs-lookup"><span data-stu-id="53690-121">Considerations in Overloading Procedures</span></span>](./considerations-in-overloading-procedures.md)  
 [<span data-ttu-id="53690-122">重载决策</span><span class="sxs-lookup"><span data-stu-id="53690-122">Overload Resolution</span></span>](./overload-resolution.md)  
 [<span data-ttu-id="53690-123">重载</span><span class="sxs-lookup"><span data-stu-id="53690-123">Overloads</span></span>](../../../../visual-basic/language-reference/modifiers/overloads.md)
