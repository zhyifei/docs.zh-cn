---
title: 声明和引发事件 (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- declarations [Visual Basic], events
- events [Visual Basic], walkthroughs
- declaring events [Visual Basic], walkthroughs
- events [Visual Basic], declaring
- events [Visual Basic], raising
- raising events [Visual Basic], walkthroughs
ms.assetid: 8ffb3be8-097d-4d3c-b71e-04555ebda2a2
ms.openlocfilehash: 20e2b0efbf40597049c515134f408927f18d5603
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69956334"
---
# <a name="walkthrough-declaring-and-raising-events-visual-basic"></a>演练：声明和引发事件 (Visual Basic)
本演练演示如何声明和引发名为`Widget`的类的事件。 完成这些步骤后, 你可能需要阅读相关主题[演练:处理事件](../../../../visual-basic/programming-guide/language-features/events/walkthrough-handling-events.md), 其中演示了如何使用`Widget`对象中的事件在应用程序中提供状态信息。  
  
## <a name="the-widget-class"></a>小组件类  
 假设你有一个`Widget`类。 你`Widget`的类有一个可能需要很长时间才能执行的方法, 并且你希望你的应用程序能够提供某种类型的完成指示器。  
  
 当然, 您可以使`Widget`对象显示一个完成百分比对话框, 但随后在您`Widget`使用该类的每个项目中都将出现该对话框。 对象设计的一个很好的原则是让使用对象的应用程序处理用户界面, 除非对象的全部用途是管理窗体或对话框。  
  
 的用途`Widget`是执行其他任务, 因此最好添加一个`PercentDone`事件并让调用`Widget`的方法的过程处理该事件并显示状态更新。 `PercentDone`事件还可以提供取消任务的机制。  
  
#### <a name="to-build-the-code-example-for-this-topic"></a>生成本主题的代码示例  
  
1. 打开一个新的 Visual Basic Windows 应用程序项目, 并创建`Form1`一个名为的窗体。  
  
2. 向添加两个按钮和一个`Form1`标签。  
  
3. 按下表所示命名对象。  
  
    |对象|属性|设置|  
    |------------|--------------|-------------|  
    |`Button1`|`Text`|启动任务|  
    |`Button2`|`Text`|取消|  
    |`Label`|`(Name)`， `Text`|lblPercentDone, 0|  
  
4. 在 "**项目**" 菜单上, 选择 "**添加类**", `Widget.vb`将名为的类添加到项目。  
  
#### <a name="to-declare-an-event-for-the-widget-class"></a>为小组件类声明事件  
  
- 使用关键字声明`Widget`类中的事件。 `Event` 请注意, 事件可以具有`ByVal`和`ByRef`参数, 如`Widget` `PercentDone`事件所示:  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnWalkthroughDeclaringAndRaisingEvents/VB/Widget.vb#1)]  
  
 调用对象收到`PercentDone`事件时, 该`Percent`参数包含已完成的任务的百分比。 参数可以设置为`True` , 以取消引发事件的方法。 `Cancel`  
  
> [!NOTE]
> 可以声明事件自变量, 就像处理过程的参数一样, 但以下情况例外:事件不能`Optional`包含`ParamArray`或参数, 并且事件没有返回值。  
  
 此事件由类`Widget`的方法引发。`LongTask` `PercentDone` `LongTask`采用两个参数: 方法在经过一段时间后进行工作, 并在暂停之前`LongTask`的最小时间间隔内`PercentDone`引发事件。  
  
#### <a name="to-raise-the-percentdone-event"></a>引发 PercentDone 事件  
  
1. 若要简化对此`Timer`类使用的属性的访问, 请`Imports`将语句添加到`Class Widget`类模块的 "声明" 部分的顶部、语句的上方。  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnWalkthroughDeclaringAndRaisingEvents/VB/Widget.vb#2)]  
  
2. 将下面的代码添加到 `Widget` 类中:  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnWalkthroughDeclaringAndRaisingEvents/VB/Widget.vb#3)]  
  
 当`LongTask`应用程序调用方法时`Widget` , 类每秒引发`PercentDone`一次`MinimumInterval`事件。 当事件返回时, `LongTask`将检查`Cancel`参数是否设置为`True`。  
  
 此处有一些免责声明是必需的。 为简单起见, `LongTask`该过程假定您事先知道任务将花多长时间。 几乎不会出现这种情况。 将任务划分为偶大的块可能比较困难, 通常, 用户最重要的是, 用户只需经过一段时间, 就能看出发生了什么情况。  
  
 在此示例中, 可能已发现另一个缺陷。 `Timer`属性返回从午夜开始经过的秒数; 因此, 如果该应用程序在午夜之前启动, 则会停滞。 更仔细地测量时间的方法会将这类边界情况 (例如这种情况) 考虑在内, 或使用属性 ( `Now`例如) 来避免这种情况。  
  
 `Widget`由于该类可以引发事件, 因此你可以转到下一个演练。 [演练：处理事件](../../../../visual-basic/programming-guide/language-features/events/walkthrough-handling-events.md)演示如何使用`WithEvents`将事件处理程序与`PercentDone`事件相关联。  
  
## <a name="see-also"></a>请参阅

- <xref:Microsoft.VisualBasic.DateAndTime.Timer%2A>
- <xref:Microsoft.VisualBasic.DateAndTime.Now%2A>
- [演练：处理事件](../../../../visual-basic/programming-guide/language-features/events/walkthrough-handling-events.md)
- [事件](../../../../visual-basic/programming-guide/language-features/events/index.md)
