---
title: 处理事件
ms.date: 07/20/2015
helpviewer_keywords:
- event handling [Visual Basic], walkthroughs
- walkthroughs [Visual Basic], event handling
- variables [Visual Basic], WithEvents
- events [Visual Basic], walkthroughs
- WithEvents keyword [Visual Basic], walkthroughs
- event handlers [Visual Basic], walkthroughs
ms.assetid: f145b3fc-5ae0-4509-a2aa-1ff6934706bd
ms.openlocfilehash: cb42f2e41e366cf8765cb9395d1a5641434bab40
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74345074"
---
# <a name="walkthrough-handling-events-visual-basic"></a>演练：处理事件 (Visual Basic)
这是演示如何处理事件的两个主题中的第二个。 第一主题[演练：声明和引发事件](../../../../visual-basic/programming-guide/language-features/events/walkthrough-declaring-and-raising-events.md)，演示如何声明和引发事件。 本部分使用该演练中的窗体和类来演示如何在事件发生时对其进行处理。  
  
 `Widget` 类示例使用传统的事件处理语句。 Visual Basic 提供了用于处理事件的其他技术。 作为练习，您可以修改此示例以使用 `AddHandler` 和 `Handles` 语句。  
  
### <a name="to-handle-the-percentdone-event-of-the-widget-class"></a>处理小组件类的 PercentDone 事件  
  
1. 将以下代码放入 `Form1`：  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnWalkthroughDeclaringAndRaisingEvents/VB/Form1.vb#4)]  
  
     `WithEvents` 关键字指定变量 `mWidget` 用于处理对象的事件。 通过提供要从中创建对象的类的名称，指定对象的类型。  
  
     变量 `mWidget` 在 `Form1` 中声明，因为 `WithEvents` 变量必须是类级别。 无论你将其放入哪类类型，都是如此。  
  
     变量 `mblnCancel` 用于取消 `LongTask` 方法。  
  
## <a name="writing-code-to-handle-an-event"></a>编写代码来处理事件  
 一旦使用 `WithEvents`声明变量，变量名称就会出现在类的**代码编辑器**的左侧下拉列表中。 选择 `mWidget`时，`Widget` 类的事件将出现在右侧下拉列表中。 选择事件会显示相应的事件过程，前缀 `mWidget` 和下划线。 与 `WithEvents` 变量关联的所有事件过程都被赋予变量名称作为前缀。  
  
#### <a name="to-handle-an-event"></a>处理事件  
  
1. 从**代码编辑器**的左侧下拉列表中选择 "`mWidget`"。  
  
2. 从右侧下拉列表中选择 "`PercentDone`" 事件。 "**代码编辑器**" 将打开 `mWidget_PercentDone` 事件过程。  
  
    > [!NOTE]
    > **代码编辑器**对于插入新的事件处理程序非常有用，但不是必需的。 在本演练中，只需直接将事件处理程序复制到代码中即可。  
  
3. 将以下代码添加到 `mWidget_PercentDone` 事件处理程序中：  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnWalkthroughDeclaringAndRaisingEvents/VB/Form1.vb#5)]  
  
     每当引发 `PercentDone` 事件时，事件过程就会在 `Label` 控件中显示完成百分比。 `DoEvents` 方法允许重绘标签，并为用户提供单击 "**取消**" 按钮的机会。  
  
4. 为 `Button2_Click` 事件处理程序添加以下代码：  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnWalkthroughDeclaringAndRaisingEvents/VB/Form1.vb#6)]  
  
 如果用户在 `LongTask` 运行时单击 "**取消**" 按钮，则只要 `DoEvents` 语句允许事件处理，就会立即执行 `Button2_Click` 事件。 类级别变量 `mblnCancel` 设置为 `True`，`mWidget_PercentDone` 事件随后对其进行测试，并将 `ByRef Cancel` 参数设置为 `True`。  
  
## <a name="connecting-a-withevents-variable-to-an-object"></a>将 WithEvents 变量连接到对象  
 `Form1` 现已设置为处理 `Widget` 对象的事件。 剩下的就是在某个地方查找 `Widget`。  
  
 在设计时 `WithEvents` 声明变量时，不会将任何对象关联。 `WithEvents` 变量与任何其他对象变量一样。 您必须创建一个对象，并使用 `WithEvents` 变量为该对象分配一个引用。  
  
#### <a name="to-create-an-object-and-assign-a-reference-to-it"></a>创建对象并为其分配引用  
  
1. 从**代码编辑器**的左侧下拉列表中选择 " **（Form1 事件）** "。  
  
2. 从右侧下拉列表中选择 "`Load`" 事件。 "**代码编辑器**" 将打开 `Form1_Load` 事件过程。  
  
3. 为 `Form1_Load` 事件过程添加以下代码，以创建 `Widget`：  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnWalkthroughDeclaringAndRaisingEvents/VB/Form1.vb#7)]  
  
 执行此代码时，Visual Basic 创建 `Widget` 对象，并将其事件连接到与 `mWidget`关联的事件过程。 从该点开始，每当 `Widget` 引发其 `PercentDone` 事件时，都会执行 `mWidget_PercentDone` 事件过程。  
  
#### <a name="to-call-the-longtask-method"></a>调用 LongTask 方法  
  
- 将以下代码添加到 `Button1_Click` 事件处理程序中：  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnWalkthroughDeclaringAndRaisingEvents/VB/Form1.vb#8)]  
  
 在调用 `LongTask` 方法之前，必须初始化显示完成百分比的标签，并且用于取消方法的类级别 `Boolean` 标志必须设置为 `False`。  
  
 调用 `LongTask` 时，任务持续时间为12.2 秒。 每隔一秒引发一次 `PercentDone` 事件。 每次引发事件时，都会执行 `mWidget_PercentDone` 事件过程。  
  
 `LongTask` 完成后，`mblnCancel` 会进行测试，以确定 `LongTask` 正常结束，还是因为 `mblnCancel` 设置为 `True`而停止。 只有在前一种情况下才会更新完成百分比。  
  
#### <a name="to-run-the-program"></a>运行程序  
  
1. 按 F5 将项目置于运行模式。  
  
2. 单击 "**启动任务**" 按钮。 每次引发 `PercentDone` 事件时，都会将标签更新为已完成的任务的百分比。  
  
3. 单击 "**取消**" 按钮停止任务。 请注意，当你单击 "**取消**" 按钮时，该按钮的外观不会立即更改。 `Click` 事件无法发生，直到 `My.Application.DoEvents` 语句允许事件处理。  
  
    > [!NOTE]
    > `My.Application.DoEvents` 方法不以与窗体相同的方式处理事件。 例如，在本演练中，必须单击 "**取消**" 按钮两次。 若要允许窗体直接处理事件，可以使用多线程处理。 有关详细信息，请参阅[托管线程处理](../../../../standard/threading/index.md)。
  
 你可能会发现，通过 F11 运行程序并单步执行代码行来单步执行代码是有益的。 你可以清楚地了解执行如何进入 `LongTask`，然后在每次引发 `PercentDone` 事件 `Form1` 短暂重新进入。  
  
 如果在 `Form1`的代码中返回执行时，会发生什么情况，`LongTask` 方法会再次被调用？ 在最糟糕的情况下，如果每次引发事件时调用 `LongTask`，则可能会发生堆栈溢出。  
  
 您可以通过将对新 `Widget` 的引用分配给 `mWidget`，使变量 `mWidget` 处理其他 `Widget` 对象的事件。 事实上，你可以使中的代码 `Button1_Click` 在每次单击按钮时执行此操作。  
  
#### <a name="to-handle-events-for-a-different-widget"></a>处理不同小组件的事件  
  
- 将以下代码行添加到 `Button1_Click` 过程中，紧跟在读取 `mWidget.LongTask(12.2, 0.33)`的行之前：  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnWalkthroughDeclaringAndRaisingEvents/VB/Form1.vb#9)]  
  
 每次单击按钮时，上面的代码会创建一个新的 `Widget`。 一旦 `LongTask` 方法完成，对 `Widget` 的引用就会释放，并且 `Widget` 会被销毁。  
  
 一个 `WithEvents` 变量一次只能包含一个对象引用，因此，如果将不同的 `Widget` 对象分配给 `mWidget`，则将不再处理前面的 `Widget` 对象的事件。 如果 `mWidget` 是包含对旧 `Widget`的引用的唯一对象变量，则会销毁该对象。 如果要处理来自多个 `Widget` 对象的事件，请使用 `AddHandler` 语句分别处理每个对象中的事件。  
  
> [!NOTE]
> 您可以根据需要声明任意多个 `WithEvents` 变量，但不支持 `WithEvents` 变量的数组。  
  
## <a name="see-also"></a>另请参阅

- [演练：声明和引发事件](../../../../visual-basic/programming-guide/language-features/events/walkthrough-declaring-and-raising-events.md)
- [事件](../../../../visual-basic/programming-guide/language-features/events/index.md)
