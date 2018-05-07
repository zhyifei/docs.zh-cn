---
title: 处理事件 (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- event handling [Visual Basic], walkthroughs
- walkthroughs [Visual Basic], event handling
- variables [Visual Basic], WithEvents
- events [Visual Basic], walkthroughs
- WithEvents keyword [Visual Basic], walkthroughs
- event handlers [Visual Basic], walkthroughs
ms.assetid: f145b3fc-5ae0-4509-a2aa-1ff6934706bd
ms.openlocfilehash: 0ac3514505ca42870d77317feec30a27e4384e6c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="walkthrough-handling-events-visual-basic"></a>演练：处理事件 (Visual Basic)
这是演示如何使用事件的两个主题的第二个。 第一个主题，[演练： 声明和引发事件](../../../../visual-basic/programming-guide/language-features/events/walkthrough-declaring-and-raising-events.md)，演示如何声明和引发事件。 本部分使用的窗体和该演练中的类以显示如何处理事件发生时。  
  
 `Widget`类的示例使用传统的事件处理语句。 Visual Basic 提供用于处理事件的其他技术。 作为练习，您可以修改此示例以使用`AddHandler`和`Handles`语句。  
  
### <a name="to-handle-the-percentdone-event-of-the-widget-class"></a>若要处理的 PercentDone 事件的小组件类  
  
1.  将以下代码中的`Form1`:  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#4](../../../../visual-basic/programming-guide/language-features/events/codesnippet/VisualBasic/walkthrough-handling-events_1.vb)]  
  
     `WithEvents`关键字指定变量`mWidget`用于处理对象的事件。 提供将从其创建对象的类名称指定的对象的类型。  
  
     变量`mWidget`中声明`Form1`因为`WithEvents`变量必须是类级。 这是 true 而不考虑你将其放置在类的类型。  
  
     变量`mblnCancel`用于取消`LongTask`方法。  
  
## <a name="writing-code-to-handle-an-event"></a>编写代码来处理事件  
 声明变量的使用时，就会立即`WithEvents`，变量的名称将显示在左侧的下拉列表的类的**代码编辑器**。 当选择`mWidget`、`Widget`类的事件将出现在右侧下拉列表。 选择一个事件将显示相应的事件过程，以前缀`mWidget`和一条下划线。 与关联的所有事件过程`WithEvents`变量提供变量的名称，作为前缀。  
  
#### <a name="to-handle-an-event"></a>若要处理的事件  
  
1.  选择`mWidget`从左侧的下拉列表中**代码编辑器**。  
  
2.  选择`PercentDone`从右侧下拉列表中的事件。 **代码编辑器**打开`mWidget_PercentDone`事件过程。  
  
    > [!NOTE]
    >  **代码编辑器**很有用，但不是必需，用于插入新的事件处理程序。 在本演练中，很多直接，只需的事件处理程序将直接复制到你的代码。  
  
3.  将以下代码添加到 `mWidget_PercentDone` 事件处理程序中：  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#5](../../../../visual-basic/programming-guide/language-features/events/codesnippet/VisualBasic/walkthrough-handling-events_2.vb)]  
  
     每当`PercentDone`引发事件，事件过程会显示在完成百分比`Label`控件。 `DoEvents`方法允许重新绘制标签，并且还为用户提供机会单击**取消**按钮。  
  
4.  添加以下代码`Button2_Click`事件处理程序：  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#6](../../../../visual-basic/programming-guide/language-features/events/codesnippet/VisualBasic/walkthrough-handling-events_3.vb)]  
  
 如果用户单击**取消**时的按钮`LongTask`正在运行，`Button2_Click`执行事件就会立即`DoEvents`语句允许发生的事件处理。 类级变量`mblnCancel`设置为`True`，和`mWidget_PercentDone`事件然后测试它，并设置`ByRef Cancel`参数`True`。  
  
## <a name="connecting-a-withevents-variable-to-an-object"></a>连接到一个对象的 WithEvents 变量  
 `Form1` 现在已设置好处理`Widget`对象的事件。 剩下的就是查找`Widget`某个位置。  
  
 当你声明一个变量`WithEvents`在设计时，没有对象，则与之关联。 A`WithEvents`变量是就像任何其他对象变量一样。 你必须创建一个对象，并为其分配引用与`WithEvents`变量。  
  
#### <a name="to-create-an-object-and-assign-a-reference-to-it"></a>若要创建一个对象，并分配对它的引用  
  
1.  选择**（Form1 事件）**从左侧的下拉列表中**代码编辑器**。  
  
2.  选择`Load`从右侧下拉列表中的事件。 **代码编辑器**打开`Form1_Load`事件过程。  
  
3.  添加以下代码`Form1_Load`事件过程中以创建`Widget`:  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#7](../../../../visual-basic/programming-guide/language-features/events/codesnippet/VisualBasic/walkthrough-handling-events_4.vb)]  
  
 在此代码的执行，Visual Basic 创建`Widget`对象，并将其事件连接到与关联的事件过程`mWidget`。 自此以后，每当`Widget`引发其`PercentDone`事件，`mWidget_PercentDone`执行事件过程。  
  
#### <a name="to-call-the-longtask-method"></a>若要调用 LongTask 方法  
  
-   将以下代码添加到 `Button1_Click` 事件处理程序中：  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#8](../../../../visual-basic/programming-guide/language-features/events/codesnippet/VisualBasic/walkthrough-handling-events_5.vb)]  
  
 之前`LongTask`调用方法时，标签，必须初始化的显示完成百分比和类级别`Boolean`标志取消方法必须设置为`False`。  
  
 `LongTask` 已调用 12.2 秒任务持续时间。 `PercentDone`引发事件一次每 1 / 3 的第二个。 引发事件时，每次`mWidget_PercentDone`执行事件过程。  
  
 当`LongTask`完成操作后，`mblnCancel`测试以查看是否`LongTask`正常结束，或如果它停止，因为`mblnCancel`已设置为`True`。 仅在前一种情况中，会更新完成百分比。  
  
#### <a name="to-run-the-program"></a>运行程序  
  
1.  按 F5，将在运行模式下的项目。  
  
2.  单击**启动任务**按钮。 每次`PercentDone`引发事件，标签更新与任务已完成的百分比。  
  
3.  单击**取消**按钮以停止该任务。 请注意的外观**取消**按钮不会更改立即当您单击的位置。 `Click`事件不会发生直到`My.Application.DoEvents`语句允许事件处理。  
  
    > [!NOTE]
    >  `My.Application.DoEvents`窗体一样方法不完全相同的方式中处理事件。 例如，在本演练中，你必须单击**取消**按钮两次。 若要使表单能够直接处理事件，可以使用多线程处理。 有关详细信息，请参阅[线程处理](http://msdn.microsoft.com/library/552f6c68-dbdb-4327-ae36-32cf9063d88c)。  
  
 您可能发现很有益按 f11 键运行程序并单步执行代码行一次。 你可以清楚地了解如何执行进入`LongTask`，，然后简要重新进入`Form1`每次`PercentDone`引发事件。  
  
 会发生什么情况如果是，在执行过程中的代码返回`Form1`、`LongTask`再次调用方法？ 如果在坏的情况下，可能发生堆栈溢出`LongTask`每次引发事件时调用。  
  
 你可能会导致变量`mWidget`来处理另一个事件`Widget`对象的引用赋给新`Widget`到`mWidget`。 事实上，你可以在代码`Button1_Click`每次单击按钮时执行此操作。  
  
#### <a name="to-handle-events-for-a-different-widget"></a>若要处理不同的小组件的事件  
  
-   添加以下代码的行`Button1_Click`过程中，读取的行的上一页`mWidget.LongTask(12.2, 0.33)`:  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#9](../../../../visual-basic/programming-guide/language-features/events/codesnippet/VisualBasic/walkthrough-handling-events_6.vb)]  
  
 上面的代码创建一个新`Widget`每次单击按钮。 只要`LongTask`方法完成时，对引用`Widget`发布后，与`Widget`被销毁。  
  
 A`WithEvents`变量可以包含一个对象引用，一次，因此，如果您分配一个不同`Widget`对象传递给`mWidget`上, 一个`Widget`对象的事件将无法再进行处理。 如果`mWidget`是唯一的对象变量包含对旧的引用`Widget`，对象被销毁。 如果你想要处理来自多个事件`Widget`对象，请使用`AddHandler`语句来单独处理从每个对象的事件。  
  
> [!NOTE]
>  你可以声明任意多个`WithEvents`需要为你的变量，但数组`WithEvents`不支持变量。  
  
## <a name="see-also"></a>请参阅  
 [演练：声明和引发事件](../../../../visual-basic/programming-guide/language-features/events/walkthrough-declaring-and-raising-events.md)  
 [事件](../../../../visual-basic/programming-guide/language-features/events/index.md)
