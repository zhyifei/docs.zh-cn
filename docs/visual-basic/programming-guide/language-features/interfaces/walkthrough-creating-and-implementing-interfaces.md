---
title: "创建和实现接口 (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- interfaces [Visual Basic], walkthroughs
- interfaces [Visual Basic], testing
- interface implementation [Visual Basic], walkthrough
- interfaces [Visual Basic], creating
ms.assetid: ded82af2-9f52-4232-98ef-fe458180f112
caps.latest.revision: "22"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 08bf6dc7344d4f83c8ab1908fdeb29eb4a53e142
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="walkthrough-creating-and-implementing-interfaces-visual-basic"></a>演练：创建和实现接口 (Visual Basic)
接口描述的属性、 方法和事件，特征，但保留最多结构或类的实现详细信息。  
  
 本演练演示如何声明和实现接口。  
  
> [!NOTE]
>  本演练不提供有关如何创建用户界面的信息。  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-define-an-interface"></a>若要定义一个接口  
  
1.  打开一个新的 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] Windows 应用程序项目。  
  
2.  向项目添加新的模块，通过单击**添加模块**上**项目**菜单。  
  
3.  命名新模块`Module1.vb`单击**添加**。 显示新的模块的代码。  
  
4.  定义一个接口，该接口名为`TestInterface`内`Module1`通过键入`Interface TestInterface`之间`Module`和`End Module`语句，并按 ENTER。 **代码编辑器**缩进`Interface`关键字，并将添加`End Interface`语句来形成代码块。  
  
5.  通过将下面的代码之间定义属性、 方法和事件接口`Interface`和`End Interface`语句：  
  
     [!code-vb[VbVbalrOOP#98](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-creating-and-implementing-interfaces_1.vb)]  
  
## <a name="implementation"></a>实现  
 你可能注意到用于声明的接口成员的语法是不同于用于声明类成员声明的语法。 这种差异反映接口不能包含实现代码的情况。  
  
#### <a name="to-implement-the-interface"></a>若要实现接口  
  
1.  添加一个名为类`ImplementationClass`通过添加以下语句到`Module1`后面`End Interface`语句之前`End Module`语句，并按 ENTER:  
  
     [!code-vb[VbVbalrOOP#99](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-creating-and-implementing-interfaces_2.vb)]  
  
     如果你正在集成的开发环境中中,**代码编辑器**提供一条匹配`End Class`语句时按 ENTER。  
  
2.  添加以下`Implements`语句`ImplementationClass`，命名的类接口实现：  
  
     [!code-vb[VbVbalrOOP#100](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-creating-and-implementing-interfaces_3.vb)]  
  
     当分别列出类或结构的顶部其他项的`Implements`语句指示类或结构实现的接口。  
  
     如果你正在集成的开发环境中中,**代码编辑器**实现所需的类成员`TestInterface`时按 ENTER，并且你可以跳过下一步。  
  
3.  如果你未在集成的开发环境中工作，则必须实现该接口的所有成员`MyInterface`。 以下代码添加到`ImplementationClass`实现`Event1`， `Method1`，和`Prop1`:  
  
     [!code-vb[VbVbalrOOP#101](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-creating-and-implementing-interfaces_4.vb)]  
  
     `Implements`语句指定的接口和所实现的接口成员。  
  
4.  完成的定义`Prop1`通过将私有字段添加到存储的属性值的类中：  
  
     [!code-vb[VbVbalrOOP#102](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-creating-and-implementing-interfaces_5.vb)]  
  
     返回的值`pval`从属性 get 访问器。  
  
     [!code-vb[VbVbalrOOP#103](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-creating-and-implementing-interfaces_6.vb)]  
  
     设置的值`pval`在属性 set 访问器。  
  
     [!code-vb[VbVbalrOOP#104](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-creating-and-implementing-interfaces_7.vb)]  
  
5.  完成的定义`Method1`通过添加下面的代码。  
  
     [!code-vb[VbVbalrOOP#105](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-creating-and-implementing-interfaces_8.vb)]  
  
#### <a name="to-test-the-implementation-of-the-interface"></a>若要测试的接口的实现  
  
1.  右键单击你的项目中的启动窗体**解决方案资源管理器**，然后单击**查看代码**。 编辑器将显示为启动窗体的类。 默认情况下，启动窗体称为`Form1`。  
  
2.  添加以下`testInstance`字段`Form1`类：  
  
     [!code-vb[VbVbalrOOP#120](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-creating-and-implementing-interfaces_9.vb)]  
  
     通过声明`testInstance`作为`WithEvents`、`Form1`类可以处理其事件。  
  
3.  添加到以下事件处理程序`Form1`类来处理引发的事件`testInstance`:  
  
     [!code-vb[VbVbalrOOP#106](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-creating-and-implementing-interfaces_10.vb)]  
  
4.  添加一个名为子例程`Test`到`Form1`类，以测试实现类：  
  
     [!code-vb[VbVbalrOOP#107](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-creating-and-implementing-interfaces_11.vb)]  
  
     `Test`过程创建的类的实现实例`MyInterface`，将分配到该实例`testInstance`字段中，设置一个属性，并运行通过接口的方法。  
  
5.  添加代码来调用`Test`过程从`Form1 Load`启动窗体的过程：  
  
     [!code-vb[VbVbalrOOP#108](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-creating-and-implementing-interfaces_12.vb)]  
  
6.  运行`Test`过程通过按 F5。 将显示消息"Prop1 已设置为 9"。 之后你单击确定，显示"Method1 X 参数为 5"的消息。 单击确定，并显示"事件处理程序捕获事件"的消息。  
  
## <a name="see-also"></a>另请参阅  
 [Implements 语句](../../../../visual-basic/language-reference/statements/implements-statement.md)  
 [接口](../../../../visual-basic/programming-guide/language-features/interfaces/index.md)  
 [Interface 语句](../../../../visual-basic/language-reference/statements/interface-statement.md)  
 [Event 语句](../../../../visual-basic/language-reference/statements/event-statement.md)
