---
title: 定义类 (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- execution [Visual Basic], ending
- objects [Visual Basic], initializing
- Initialize event [Visual Basic]
- files [Visual Basic], closing
- programs [Visual Basic], quitting
- code, exiting
- objects [Visual Basic], creating
- program termination
- classes [Visual Basic], walkthroughs
- class modules, walkthroughs
- Terminate event [Visual Basic]
- execution [Visual Basic], stopping
ms.assetid: 07018828-2d49-4cf5-a44b-19fb15d9efea
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 9fc173ad853755c4b02a13abc0a80229bebffe64
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/26/2018
---
# <a name="walkthrough-defining-classes-visual-basic"></a>演练：定义类 (Visual Basic)

本演练演示如何定义类，你可以使用它来创建对象。 它还演示如何将属性和方法添加到新的类，并演示如何初始化的对象。  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
## <a name="to-define-a-class"></a>若要定义的类
  
1.  通过单击创建项目**新项目**上**文件**菜单。 此时将出现 “新建项目” 对话框。  
  
2.  从 Visual Basic 项目模板，以显示新的项目列表中选择 Windows 应用程序。  
  
3.  将新类添加到项目中，通过单击**添加类**上**项目**菜单。 “添加新项”对话框随即出现。  
  
4.  选择**类**模板。  
  
5.  将新类`UserNameInfo.vb`，然后单击**添加**以显示新的类的代码。  
  
     [!code-vb[VbVbalrOOP#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#5)]
  
    > [!NOTE]
    >  你可以使用 Visual Basic**代码编辑器**将类添加到启动窗体中，通过键入`Class`关键字后跟新类的名称。 **代码编辑器**提供相应`End Class`为你的语句。  
  
6.  通过添加下面的代码之间定义类的私有字段`Class`和`End Class`语句：  
  
     [!code-vb[VbVbalrOOP#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#7)]
  
     声明为字段`Private`意味着它可以仅在类内使用。 你可以使字段成为可从类外部的通过使用访问修饰符，如`Public`提供访问权限多。 有关详细信息，请参阅[访问 Visual Basic 中的级别](../../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)。  
  
7.  通过添加下面的代码中定义类的属性：  
  
     [!code-vb[VbVbalrOOP#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#8)]
  
8.  通过添加下面的代码中定义的类方法：  
  
     [!code-vb[VbVbalrOOP#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#9)]
  
9. 通过添加名为的过程中定义新类的参数化构造函数`Sub New`:  
  
     [!code-vb[VbVbalrOOP#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#10)]
  
     `Sub New`创建基于此类对象时自动调用构造函数。 此构造函数设置保留的用户名的字段的值。  
  
## <a name="to-create-a-button-to-test-the-class"></a>若要创建一个按钮以测试类
  
1.  将启动窗体更改为设计模式中，右键单击其名称中的**解决方案资源管理器**，然后单击**视图设计器**。 默认情况下，Windows 应用程序项目的启动窗体名为 form1.vb。 随后将显示主窗体。  
  
2.  向主窗体添加一个按钮并双击它以显示的代码`Button1_Click`事件处理程序。 添加以下代码以调用测试过程：  
  
     [!code-vb[VbVbalrOOP#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#12)]
  
## <a name="to-run-your-application"></a>运行应用程序
  
1.  按 F5 运行你的应用程序。 单击要调用的测试过程的窗体上的按钮。 它将显示一条消息表明原始`UserName`是"兵 BOBBY"，因为调用该过程`Capitalize`对象的方法。  
  
2.  单击**确定**关闭消息框。 `Button1 Click`过程更改的值`UserName`属性并显示的新值的消息，指出`UserName`是"Worden，Joe"。  
  
## <a name="see-also"></a>请参阅

[面向对象的编程 (Visual Basic)](../../concepts/object-oriented-programming.md)  
[对象和类](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)