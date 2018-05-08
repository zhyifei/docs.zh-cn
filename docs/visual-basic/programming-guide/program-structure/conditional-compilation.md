---
title: Visual Basic 中的条件编译
ms.date: 07/20/2015
helpviewer_keywords:
- conditional compilation [Visual Basic], about conditional compilation
- compilation [Visual Basic], conditional
ms.assetid: 9c35e55e-7eee-44fb-a586-dad1f1884848
ms.openlocfilehash: 496df36242c6b43e7e3ec94ce675d11177e8b466
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="conditional-compilation-in-visual-basic"></a>Visual Basic 中的条件编译
在*条件编译*，而其他人将被忽略，将有选择地编译特定程序中的代码块。  
  
 例如，你可能想要编写调试语句来比较不同的方法的速度到相同的编程任务，或者让你可能想要本地化为多种语言应用程序。 条件编译语句旨在在编译期间，不在运行时运行。  
  
 表示要使用有条件地编译的代码块`#If...Then...#Else`指令。 例如，若要创建法语和德语版本从相同的相同应用程序源代码，嵌入特定于平台的代码段中`#If...Then`使用预定义的常量的语句`FrenchVersion`和`GermanVersion`。 下面的示例演示如何：  
  
 [!code-vb[VbVbalrConditionalComp#5](../../../visual-basic/language-reference/directives/codesnippet/VisualBasic/conditional-compilation_1.vb)]  
  
 如果你设置的值`FrenchVersion`条件编译常量为`True`在编译时，法语版本的条件的代码会编译。 如果你设置的值`GermanVersion`常量到`True`，编译器使用德语版本。 如果两者均未设置`True`，在最后一个代码`Else`块将运行。  
  
> [!NOTE]
>  自动完成功能将不函数时编辑代码，并使用条件编译指令，如果代码不是当前分支的一部分。  
  
## <a name="declaring-conditional-compilation-constants"></a>声明条件编译常量  
 在以下三种方式中，可以设置条件编译常量：  
  
-   在**项目设计器**  
  
-   在命令行使用命令行编译器时  
  
-   在代码中  
  
 条件编译常量具有特殊的作用域，并且不能从标准的代码访问。 条件编译常量的作用域是依赖于它的设置方式。 下表列出了使用每个上面提到的三种方式声明的常量的作用域。  
  
|如何设置常量|常量的作用域|  
|---|---|  
|**项目设计器**|在项目中的所有文件是公共的|  
|命令行|传递给命令行编译器的所有文件是公共的|  
|`#Const` 在代码中的语句|专用于在其中声明的文件|  
  
|在项目设计器中设置常量|  
|---|  
|-在创建可执行文件之前, 在中设置常量**项目设计器**中提供的步骤[管理项目和解决方案属性](/visualstudio/ide/managing-project-and-solution-properties)。|  
  
|要在命令行处设置常量|  
|---|  
|-使用 **/d**交换机输入条件编译常数，如以下示例所示：<br />     `vbc MyProj.vb /d:conFrenchVersion=–1:conANSI=0`<br />     则需要之间没有空间 **/d**开关与第一个常数。 有关详细信息，请参阅[/define (Visual Basic 中)](../../../visual-basic/reference/command-line-compiler/define.md)。<br />     命令行声明重写声明进入**项目设计器**，但不是清除它们。 设置参数**项目设计器**后续编译就保持有效。<br />     编写时常量中以及代码本身，没有严格的规则对其位置中，由于其作用域声明它们的整个模块。|  
  
|若要在代码中设置常量|  
|---|  
|-将常数放在声明块在其中使用它们的模块。 这有助于使代码保持有组织且更易读。|  
  
## <a name="related-topics"></a>相关主题  
  
|标题|描述|  
|---|---|  
|[程序结构和代码约定](../../../visual-basic/programming-guide/program-structure/program-structure-and-code-conventions.md)|提供使你的代码轻松地读取和维护的建议。|  
  
## <a name="reference"></a>参考  
 [#Const 指令](../../../visual-basic/language-reference/directives/const-directive.md)  
  
 [#If...Then...#Else 指令](../../../visual-basic/language-reference/directives/if-then-else-directives.md)  
  
 [/define (Visual Basic)](../../../visual-basic/reference/command-line-compiler/define.md)
