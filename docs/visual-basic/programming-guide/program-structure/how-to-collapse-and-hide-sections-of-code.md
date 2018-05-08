---
title: 如何：折叠和隐藏代码节 (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- Visual Basic, code collapsing
- Visual Basic, code hiding
- Visual Basic code, collapsing and hiding
ms.assetid: b770e8f5-e07d-491a-ab4b-a977980f9ba2
ms.openlocfilehash: f6c272b7ac016258d99873512cb789bba6739727
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-collapse-and-hide-sections-of-code-visual-basic"></a>如何：折叠和隐藏代码节 (Visual Basic)
`#Region`指令，可折叠并隐藏 Visual Basic 文件中的代码段。 `#Region`指令允许你使用 Visual Studio 代码编辑器时指定的一段代码，你可以展开或折叠。 有选择地隐藏代码的能力使你的文件更易于管理并且更易读。 有关详细信息，请参阅[大纲显示](/visualstudio/ide/outlining)。  
  
 `#Region` 指令支持代码块语义，例如`#If...#End If`。 这意味着它们不能在一个块开始和结束在另一个;开始和结束必须在同一个块中。 `#Region` 指令不支持在函数内。  
  
### <a name="to-collapse-and-hide-a-section-of-code"></a>若要折叠和隐藏代码节  
  
-   放置的之间的代码部分`#Region`和`#End Region`语句，如以下示例所示：  
  
     [!code-vb[VbVbalrConditionalComp#6](../../../visual-basic/language-reference/directives/codesnippet/VisualBasic/how-to-collapse-and-hide-sections-of-code_1.vb)]  
  
     `#Region`块可以多次使用一个代码文件中; 因此，用户可以定义自己块的过程和可以反过来，折叠导航窗格的类。 `#Region` 块也可以嵌套在其他`#Region`块。  
  
    > [!NOTE]
    >  隐藏代码不会阻止从正在编译，不影响`#If...#End If`语句。  
  
## <a name="see-also"></a>请参阅  
 [条件编译](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)  
 [#Region 指令](../../../visual-basic/language-reference/directives/region-directive.md)  
 [#If...Then...#Else 指令](../../../visual-basic/language-reference/directives/if-then-else-directives.md)  
 [大纲显示](/visualstudio/ide/outlining)
