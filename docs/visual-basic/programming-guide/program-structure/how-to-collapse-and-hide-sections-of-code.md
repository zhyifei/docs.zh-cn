---
title: "如何：折叠和隐藏代码节 (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- Visual Basic, code collapsing
- Visual Basic, code hiding
- Visual Basic code, collapsing and hiding
ms.assetid: b770e8f5-e07d-491a-ab4b-a977980f9ba2
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 56a31f0c8af9b84e87ebe1e5191d72d19be8340f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-collapse-and-hide-sections-of-code-visual-basic"></a><span data-ttu-id="e0712-102">如何：折叠和隐藏代码节 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e0712-102">How to: Collapse and Hide Sections of Code (Visual Basic)</span></span>
<span data-ttu-id="e0712-103">`#Region`指令可以折叠和隐藏中的代码段[!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]文件。</span><span class="sxs-lookup"><span data-stu-id="e0712-103">The `#Region` directive enables you to collapse and hide sections of code in [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] files.</span></span> <span data-ttu-id="e0712-104">`#Region`指令允许你在使用时指定的一段代码，你可以展开或折叠[!INCLUDE[vsprvs](~/includes/vsprvs-md.md)]代码编辑器。</span><span class="sxs-lookup"><span data-stu-id="e0712-104">The `#Region` directive lets you specify a block of code that you can expand or collapse when using the [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)] code editor.</span></span> <span data-ttu-id="e0712-105">有选择地隐藏代码的能力使你的文件更易于管理并且更易读。</span><span class="sxs-lookup"><span data-stu-id="e0712-105">The ability to hide code selectively makes your files more manageable and easier to read.</span></span> <span data-ttu-id="e0712-106">有关详细信息，请参阅[大纲显示](/visualstudio/ide/outlining)。</span><span class="sxs-lookup"><span data-stu-id="e0712-106">For more information, see [Outlining](/visualstudio/ide/outlining).</span></span>  
  
 <span data-ttu-id="e0712-107">`#Region`指令支持代码块语义，例如`#If...#End If`。</span><span class="sxs-lookup"><span data-stu-id="e0712-107">`#Region` directives support code block semantics such as `#If...#End If`.</span></span> <span data-ttu-id="e0712-108">这意味着它们不能在一个块开始和结束在另一个;开始和结束必须在同一个块中。</span><span class="sxs-lookup"><span data-stu-id="e0712-108">This means they cannot begin in one block and end in another; the start and end must be in the same block.</span></span> <span data-ttu-id="e0712-109">`#Region`指令不支持在函数内。</span><span class="sxs-lookup"><span data-stu-id="e0712-109">`#Region` directives are not supported within functions.</span></span>  
  
### <a name="to-collapse-and-hide-a-section-of-code"></a><span data-ttu-id="e0712-110">若要折叠和隐藏代码节</span><span class="sxs-lookup"><span data-stu-id="e0712-110">To collapse and hide a section of code</span></span>  
  
-   <span data-ttu-id="e0712-111">放置的之间的代码部分`#Region`和`#End Region`语句，如以下示例所示：</span><span class="sxs-lookup"><span data-stu-id="e0712-111">Place the section of code between the `#Region` and `#End Region` statements, as in the following example:</span></span>  
  
     [!code-vb[VbVbalrConditionalComp#6](../../../visual-basic/language-reference/directives/codesnippet/VisualBasic/how-to-collapse-and-hide-sections-of-code_1.vb)]  
  
     <span data-ttu-id="e0712-112">`#Region`块可以多次使用一个代码文件中; 因此，用户可以定义自己块的过程和可以反过来，折叠导航窗格的类。</span><span class="sxs-lookup"><span data-stu-id="e0712-112">The `#Region` block can be used multiple times in a code file; thus, users can define their own blocks of procedures and classes that can, in turn, be collapsed.</span></span> <span data-ttu-id="e0712-113">`#Region`块也可以嵌套在其他`#Region`块。</span><span class="sxs-lookup"><span data-stu-id="e0712-113">`#Region` blocks can also be nested within other `#Region` blocks.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="e0712-114">隐藏代码不会阻止从正在编译，不影响`#If...#End If`语句。</span><span class="sxs-lookup"><span data-stu-id="e0712-114">Hiding code does not prevent it from being compiled and does not affect `#If...#End If` statements.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e0712-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e0712-115">See Also</span></span>  
 [<span data-ttu-id="e0712-116">条件编译</span><span class="sxs-lookup"><span data-stu-id="e0712-116">Conditional Compilation</span></span>](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)  
 [<span data-ttu-id="e0712-117">#Region 指令</span><span class="sxs-lookup"><span data-stu-id="e0712-117">#Region Directive</span></span>](../../../visual-basic/language-reference/directives/region-directive.md)  
 [<span data-ttu-id="e0712-118">#If...Then...#Else 指令</span><span class="sxs-lookup"><span data-stu-id="e0712-118">#If...Then...#Else Directives</span></span>](../../../visual-basic/language-reference/directives/if-then-else-directives.md)  
 [<span data-ttu-id="e0712-119">大纲显示</span><span class="sxs-lookup"><span data-stu-id="e0712-119">Outlining</span></span>](/visualstudio/ide/outlining)
