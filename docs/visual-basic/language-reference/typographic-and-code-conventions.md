---
title: 版式和代码约定 (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- coding conventions [Visual Basic], Visual Basic
- best practices [Visual Basic], coding conventions
- conventions [Visual Basic], Visual Basic coding
- typographic conventions [Visual Basic]
- document conventions [Visual Basic]
- conventions [Visual Basic], documentation
- Visual Basic code, conventions
ms.assetid: 1916cd81-ea9d-4faa-81f7-4a0d864b60f4
ms.openlocfilehash: eb7a33ef21bf6beda730dffa8eb7ff9cabe599fb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="typographic-and-code-conventions-visual-basic"></a>版式和代码约定 (Visual Basic)
Visual Basic 文档将使用以下版式和代码约定。  
  
## <a name="typographic-conventions"></a>排字约定  
  
|示例|描述|  
|-------------|-----------------|  
|`Sub`, `If`, `ChDir`, `Print`, `True`, `Debug`|特定于语言的关键字和运行时成员的首字母大写，其格式如在此示例中所示。|  
|**SmallProject**， **ButtonCollection**|此示例中所示，单词和短语指示你键入的格式设置。|  
|[Module 语句](../../visual-basic/language-reference/statements/module-statement.md)|此示例中所示，你可以单击以转到另一个帮助页的链接进行格式化。|  
|*对象*， *variableName*， `argumentList`|此示例中所示的格式为你提供的信息的占位符。|  
|[阴影] [ *expressionList* ]|在语法中，可选项括在方括号中。|  
|{ `Public` &#124; `Friend` &#124; `Private` }|在语法中，你必须在两个或多个项之间进行选择时，物料被括在大括号中并由竖线分隔。<br /><br /> 您必须选择一个，且只有一个项。|  
|[ `Protected` &#124; `Friend` ]|在语法中，如果你具有两个或多个项之间进行选择的选项是括在方括号项并且由竖线分隔。<br /><br /> 你可以选择的项的任意组合或任何项。|  
|[{ `ByVal` &#124; `ByRef` }]|在语法中，你可以选择不超过一项，但也可以完全省略这些项时这些项包含在大括号括起来并由竖线分隔的方括号中。|  
|*memberName*1， *memberName*2， *memberName*3|相同的占位符的多个实例的区别在于下标，如示例所示。|  
|*m e 1*<br /><br /> ...<br /><br /> *memberNameN*|在语法中，省略号 （...） 用于指示立即前面省略号类型的项目数量不确定。<br /><br /> 在代码中，省略号表示为清楚起见省略的代码。|  
|ESC、 输入|密钥名称和键盘上的键顺序出现在全大写字母。|  
|ALT + F1|密钥名称之间出现加号 （+），你必须按另时按住一个键。 例如，ALT + F1 意味着在按 F1 键同时按住 ALT 键。|  
  
## <a name="code-conventions"></a>代码约定  
  
|示例|描述|  
|-------------|-----------------|  
|`sampleString = "Hello, world!"`|代码示例显示在固定间距字体，并且在此示例中所示进行格式化。|  
|上一条语句设置的值`sampleString`到"Hello，world ！"|此示例中所示，解释性文本中的代码元素出现在固定间距字体。|  
|`' This is a comment.`<br /><br /> `REM This is also a comment.`|撇号 （'） 或 REM 关键字的情况下，所引入代码注释。|  
|`sampleVar = "This is an " _`<br /><br /> `& "example" _`<br /><br /> `& " of how to continue code."`|跟下划线 (_) 行末尾的空格指示语句继续在下一行。|  
  
## <a name="see-also"></a>请参阅  
 [Visual Basic 语言参考](../../visual-basic/language-reference/index.md)  
 [关键字](../../visual-basic/language-reference/keywords/index.md)  
 [Visual Basic 运行库成员](../../visual-basic/language-reference/runtime-library-members.md)  
 [Visual Basic 命名约定](../../visual-basic/programming-guide/program-structure/naming-conventions.md)  
 [如何：在代码中拆分和合并语句](../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md)  
 [代码中的注释](../../visual-basic/programming-guide/program-structure/comments-in-code.md)
