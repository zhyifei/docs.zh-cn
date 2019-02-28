---
title: 如何：折叠和隐藏代码 (Visual Basic 中) 的部分
ms.date: 07/20/2015
helpviewer_keywords:
- Visual Basic, code collapsing
- Visual Basic, code hiding
- Visual Basic code, collapsing and hiding
ms.assetid: b770e8f5-e07d-491a-ab4b-a977980f9ba2
ms.openlocfilehash: bbce0e4a2427843ed9d9d51b25684db8c54ba69a
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/28/2019
ms.locfileid: "56980121"
---
# <a name="how-to-collapse-and-hide-sections-of-code-visual-basic"></a><span data-ttu-id="b9da7-102">如何：折叠和隐藏代码 (Visual Basic 中) 的部分</span><span class="sxs-lookup"><span data-stu-id="b9da7-102">How to: Collapse and Hide Sections of Code (Visual Basic)</span></span>
<span data-ttu-id="b9da7-103">`#Region`指令，可折叠并隐藏 Visual Basic 文件中的代码段。</span><span class="sxs-lookup"><span data-stu-id="b9da7-103">The `#Region` directive enables you to collapse and hide sections of code in Visual Basic files.</span></span> <span data-ttu-id="b9da7-104">`#Region`指令，可以使用 Visual Studio 代码编辑器时指定的一段代码，你可以展开或折叠。</span><span class="sxs-lookup"><span data-stu-id="b9da7-104">The `#Region` directive lets you specify a block of code that you can expand or collapse when using the Visual Studio code editor.</span></span> <span data-ttu-id="b9da7-105">有选择地隐藏代码的功能使你的文件更易于管理且更易读取。</span><span class="sxs-lookup"><span data-stu-id="b9da7-105">The ability to hide code selectively makes your files more manageable and easier to read.</span></span> <span data-ttu-id="b9da7-106">有关详细信息，请参阅[大纲显示](/visualstudio/ide/outlining)。</span><span class="sxs-lookup"><span data-stu-id="b9da7-106">For more information, see [Outlining](/visualstudio/ide/outlining).</span></span>  
  
 <span data-ttu-id="b9da7-107">`#Region` 指令支持代码块语义，如`#If...#End If`。</span><span class="sxs-lookup"><span data-stu-id="b9da7-107">`#Region` directives support code block semantics such as `#If...#End If`.</span></span> <span data-ttu-id="b9da7-108">这意味着它们不能在一个块中开始和结束在另一个;开始和结束必须在同一个块中。</span><span class="sxs-lookup"><span data-stu-id="b9da7-108">This means they cannot begin in one block and end in another; the start and end must be in the same block.</span></span> <span data-ttu-id="b9da7-109">`#Region` 在函数中不支持指令。</span><span class="sxs-lookup"><span data-stu-id="b9da7-109">`#Region` directives are not supported within functions.</span></span>  
  
### <a name="to-collapse-and-hide-a-section-of-code"></a><span data-ttu-id="b9da7-110">若要折叠和隐藏代码节</span><span class="sxs-lookup"><span data-stu-id="b9da7-110">To collapse and hide a section of code</span></span>  
  
-   <span data-ttu-id="b9da7-111">放置之间的代码部分`#Region`和`#End Region`语句，如以下示例所示：</span><span class="sxs-lookup"><span data-stu-id="b9da7-111">Place the section of code between the `#Region` and `#End Region` statements, as in the following example:</span></span>  
  
     [!code-vb[VbVbalrConditionalComp#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrConditionalComp/VB/Class1.vb#6)]  
  
     <span data-ttu-id="b9da7-112">`#Region`块可以多次使用在代码文件中; 因此，用户可以定义他们自己块的过程和可，反过来，折叠的类。</span><span class="sxs-lookup"><span data-stu-id="b9da7-112">The `#Region` block can be used multiple times in a code file; thus, users can define their own blocks of procedures and classes that can, in turn, be collapsed.</span></span> <span data-ttu-id="b9da7-113">`#Region` 块也可以嵌套在其他`#Region`块。</span><span class="sxs-lookup"><span data-stu-id="b9da7-113">`#Region` blocks can also be nested within other `#Region` blocks.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="b9da7-114">隐藏代码不会阻止从正在编译，并且不影响`#If...#End If`语句。</span><span class="sxs-lookup"><span data-stu-id="b9da7-114">Hiding code does not prevent it from being compiled and does not affect `#If...#End If` statements.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b9da7-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="b9da7-115">See also</span></span>
- [<span data-ttu-id="b9da7-116">条件编译</span><span class="sxs-lookup"><span data-stu-id="b9da7-116">Conditional Compilation</span></span>](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)
- [<span data-ttu-id="b9da7-117">#Region 指令</span><span class="sxs-lookup"><span data-stu-id="b9da7-117">#Region Directive</span></span>](../../../visual-basic/language-reference/directives/region-directive.md)
- [<span data-ttu-id="b9da7-118">#If...Then...#Else 指令</span><span class="sxs-lookup"><span data-stu-id="b9da7-118">#If...Then...#Else Directives</span></span>](../../../visual-basic/language-reference/directives/if-then-else-directives.md)
- [<span data-ttu-id="b9da7-119">大纲显示</span><span class="sxs-lookup"><span data-stu-id="b9da7-119">Outlining</span></span>](/visualstudio/ide/outlining)
