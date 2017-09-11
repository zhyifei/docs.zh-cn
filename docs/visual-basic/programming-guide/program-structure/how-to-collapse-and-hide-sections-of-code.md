---
title: "如何︰ 折叠和隐藏代码 (Visual Basic 中) 的部分 |Microsoft 文档"
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
- Visual Basic, code collapsing
- Visual Basic, code hiding
- Visual Basic code, collapsing and hiding
ms.assetid: b770e8f5-e07d-491a-ab4b-a977980f9ba2
caps.latest.revision: 11
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
ms.openlocfilehash: 4dcd5cd5d79629fd008534112cb72d5bcfec476e
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017

---
# <a name="how-to-collapse-and-hide-sections-of-code-visual-basic"></a><span data-ttu-id="e8c3b-102">如何：折叠和隐藏代码节 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e8c3b-102">How to: Collapse and Hide Sections of Code (Visual Basic)</span></span>
<span data-ttu-id="e8c3b-103">`#Region`指令，可以折叠和隐藏代码节[!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]文件。</span><span class="sxs-lookup"><span data-stu-id="e8c3b-103">The `#Region` directive enables you to collapse and hide sections of code in [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] files.</span></span> <span data-ttu-id="e8c3b-104">`#Region`指令可让您在使用时指定的一段代码，你可以展开或折叠[!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)]代码编辑器中。</span><span class="sxs-lookup"><span data-stu-id="e8c3b-104">The `#Region` directive lets you specify a block of code that you can expand or collapse when using the [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)] code editor.</span></span> <span data-ttu-id="e8c3b-105">有选择地隐藏代码的能力使您的文件更易于管理且更易于阅读。</span><span class="sxs-lookup"><span data-stu-id="e8c3b-105">The ability to hide code selectively makes your files more manageable and easier to read.</span></span> <span data-ttu-id="e8c3b-106">有关详细信息，请参阅[大纲显示](https://docs.microsoft.com/visualstudio/ide/outlining)。</span><span class="sxs-lookup"><span data-stu-id="e8c3b-106">For more information, see [Outlining](https://docs.microsoft.com/visualstudio/ide/outlining).</span></span>  
  
 <span data-ttu-id="e8c3b-107">`#Region`指令支持代码块语义，如`#If...#End If`。</span><span class="sxs-lookup"><span data-stu-id="e8c3b-107">`#Region` directives support code block semantics such as `#If...#End If`.</span></span> <span data-ttu-id="e8c3b-108">这意味着它们不能在一个块中开始和结束在另一个;开始和结束必须位于同一个块。</span><span class="sxs-lookup"><span data-stu-id="e8c3b-108">This means they cannot begin in one block and end in another; the start and end must be in the same block.</span></span> <span data-ttu-id="e8c3b-109">`#Region`指令不支持在函数内。</span><span class="sxs-lookup"><span data-stu-id="e8c3b-109">`#Region` directives are not supported within functions.</span></span>  
  
### <a name="to-collapse-and-hide-a-section-of-code"></a><span data-ttu-id="e8c3b-110">若要折叠和隐藏代码节</span><span class="sxs-lookup"><span data-stu-id="e8c3b-110">To collapse and hide a section of code</span></span>  
  
-   <span data-ttu-id="e8c3b-111">将之间的代码节放`#Region`和`#End Region`语句，如以下示例所示︰</span><span class="sxs-lookup"><span data-stu-id="e8c3b-111">Place the section of code between the `#Region` and `#End Region` statements, as in the following example:</span></span>  
  
     <span data-ttu-id="e8c3b-112">[!code-vb[VbVbalrConditionalComp #&6;](../../../visual-basic/language-reference/directives/codesnippet/VisualBasic/how-to-collapse-and-hide-sections-of-code_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="e8c3b-112">[!code-vb[VbVbalrConditionalComp#6](../../../visual-basic/language-reference/directives/codesnippet/VisualBasic/how-to-collapse-and-hide-sections-of-code_1.vb)]</span></span>  
  
     <span data-ttu-id="e8c3b-113">`#Region`块可以多次使用的代码文件中; 因此，用户可以定义自己的块过程和，反过来，可折叠的类。</span><span class="sxs-lookup"><span data-stu-id="e8c3b-113">The `#Region` block can be used multiple times in a code file; thus, users can define their own blocks of procedures and classes that can, in turn, be collapsed.</span></span> <span data-ttu-id="e8c3b-114">`#Region`块也可以嵌套在其他`#Region`块。</span><span class="sxs-lookup"><span data-stu-id="e8c3b-114">`#Region` blocks can also be nested within other `#Region` blocks.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="e8c3b-115">隐藏代码不会阻止它正在编译，并且不影响`#If...#End If`语句。</span><span class="sxs-lookup"><span data-stu-id="e8c3b-115">Hiding code does not prevent it from being compiled and does not affect `#If...#End If` statements.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e8c3b-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e8c3b-116">See Also</span></span>  
 <span data-ttu-id="e8c3b-117">[条件编译](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md) </span><span class="sxs-lookup"><span data-stu-id="e8c3b-117">[Conditional Compilation](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md) </span></span>  
<span data-ttu-id="e8c3b-118"> [#Region 指令](../../../visual-basic/language-reference/directives/region-directive.md) </span><span class="sxs-lookup"><span data-stu-id="e8c3b-118"> [#Region Directive](../../../visual-basic/language-reference/directives/region-directive.md) </span></span>  
<span data-ttu-id="e8c3b-119"> [#If...Then...#Else 指令](../../../visual-basic/language-reference/directives/if-then-else-directives.md) </span><span class="sxs-lookup"><span data-stu-id="e8c3b-119"> [#If...Then...#Else Directives](../../../visual-basic/language-reference/directives/if-then-else-directives.md) </span></span>  
<span data-ttu-id="e8c3b-120"> [大纲显示](https://docs.microsoft.com/visualstudio/ide/outlining)</span><span class="sxs-lookup"><span data-stu-id="e8c3b-120"> [Outlining](https://docs.microsoft.com/visualstudio/ide/outlining)</span></span>
