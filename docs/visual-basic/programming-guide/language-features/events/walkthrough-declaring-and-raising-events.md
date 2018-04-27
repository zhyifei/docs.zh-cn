---
title: 声明和引发事件 (Visual Basic)
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- declarations [Visual Basic], events
- events [Visual Basic], walkthroughs
- declaring events [Visual Basic], walkthroughs
- events [Visual Basic], declaring
- events [Visual Basic], raising
- raising events [Visual Basic], walkthroughs
ms.assetid: 8ffb3be8-097d-4d3c-b71e-04555ebda2a2
caps.latest.revision: 16
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 27db585084703607a7389f5a0aa3eba6f70dd793
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/26/2018
---
# <a name="walkthrough-declaring-and-raising-events-visual-basic"></a>演练：声明和引发事件 (Visual Basic)
本演练演示如何声明和引发事件的类名为`Widget`。 完成步骤后，你可能想要读取的配套主题，[演练： 处理事件](../../../../visual-basic/programming-guide/language-features/events/walkthrough-handling-events.md)，其中说明了如何使用事件从`Widget`对象提供在应用程序的状态信息。  
  
## <a name="the-widget-class"></a>小组件类  
 假定你有目前`Widget`类。 你`Widget`类具有方法可能需要很长时间才能执行，并且你希望你的应用程序要能够提供某种进度指示器。  
  
 当然，你可以进行`Widget`对象会显示完成百分比的对话框中，但这样你将会使用在其中每个项目中该对话框`Widget`类。 一个好的对象设计原则是让使用的对象的句柄的用户界面的应用程序，除非该对象的整个的用途是管理种窗体或对话框。  
  
 用途`Widget`是执行其他任务，所以最好添加`PercentDone`事件并让调用的过程`Widget`方法的处理事件和显示状态更新。 `PercentDone`事件还可以提供用于取消该任务的机制。  
  
#### <a name="to-build-the-code-example-for-this-topic"></a>若要生成本主题的代码示例  
  
1.  打开一个新的 Visual Basic Windows 应用程序项目并创建名为窗体`Form1`。  
  
2.  添加两个按钮和标签与`Form1`。  
  
3.  按下表所示命名对象。  
  
    |对象|属性|设置|  
    |------------|--------------|-------------|  
    |`Button1`|`Text`|启动任务|  
    |`Button2`|`Text`|取消|  
    |`Label`|`(Name)`, `Text`|lblPercentDone 0|  
  
4.  上**项目**菜单上，选择**添加类**添加一个名为类`Widget.vb`到项目。  
  
#### <a name="to-declare-an-event-for-the-widget-class"></a>若要声明小组件类事件  
  
-   使用`Event`关键字来声明中的一个事件`Widget`类。 请注意，事件可以具有`ByVal`和`ByRef`自变量，作为`Widget`的`PercentDone`事件所示：  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#1](../../../../visual-basic/programming-guide/language-features/events/codesnippet/VisualBasic/walkthrough-declaring-and-raising-events_1.vb)]  
  
 当调用的对象收到`PercentDone`事件，`Percent`参数中包含的任务已完成的百分比。 `Cancel`参数可以设置为`True`取消引发事件的方法。  
  
> [!NOTE]
>  你可以声明事件自变量，就像参数的过程，有以下例外： 事件不能有`Optional`或`ParamArray`参数，且事件不具有返回值。  
  
 `PercentDone`事件由引发`LongTask`方法`Widget`类。 `LongTask` 采用两个参数： 方法自称要工作和之前的最小时间间隔的时间长度`LongTask`暂停以引发`PercentDone`事件。  
  
#### <a name="to-raise-the-percentdone-event"></a>若要引发 PercentDone 事件  
  
1.  若要简化对访问`Timer`此类使用的属性添加`Imports`到你的类模块的声明部分顶部的语句上方`Class Widget`语句。  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#2](../../../../visual-basic/programming-guide/language-features/events/codesnippet/VisualBasic/walkthrough-declaring-and-raising-events_2.vb)]  
  
2.  将下面的代码添加到 `Widget` 类中:  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#3](../../../../visual-basic/programming-guide/language-features/events/codesnippet/VisualBasic/walkthrough-declaring-and-raising-events_3.vb)]  
  
 当你的应用程序调用`LongTask`方法，`Widget`类所引发`PercentDone`事件每个`MinimumInterval`秒。 当事件返回时，`LongTask`检查以查看是否`Cancel`参数已设置为`True`。  
  
 几个免责声明此处是必需的。 为简单起见，`LongTask`过程假定您事先知道任务将花费多长时间。 这几乎从未是这种情况。 将任务分割成多个大小相等的块可能很困难，且通常最关键的问题给用户只需在获得的内容所发生情况的指示之前所经过的时间量。  
  
 您可能已经发现了另一个缺点在此示例中。 `Timer`属性返回的自午夜以来经过的秒数; 因此，应用程序时遇到困难如果恰好在午夜之前启动。 更仔细的测量时间方法将采用边界情况，如这纳入考虑范围，或者完全避免使用属性类似于`Now`。  
  
 现在，`Widget`类可以引发事件，你可以将移动到下一个演练。 [演练： 处理事件](../../../../visual-basic/programming-guide/language-features/events/walkthrough-handling-events.md)演示如何使用`WithEvents`要关联的事件处理程序替换`PercentDone`事件。  
  
## <a name="see-also"></a>请参阅  
 <xref:Microsoft.VisualBasic.DateAndTime.Timer%2A>  
 <xref:Microsoft.VisualBasic.DateAndTime.Now%2A>  
 [演练：处理事件](../../../../visual-basic/programming-guide/language-features/events/walkthrough-handling-events.md)  
 [事件](../../../../visual-basic/programming-guide/language-features/events/index.md)
