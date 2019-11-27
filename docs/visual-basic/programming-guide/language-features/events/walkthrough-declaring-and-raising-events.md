---
title: 声明和引发事件
ms.date: 07/20/2015
helpviewer_keywords:
- declarations [Visual Basic], events
- events [Visual Basic], walkthroughs
- declaring events [Visual Basic], walkthroughs
- events [Visual Basic], declaring
- events [Visual Basic], raising
- raising events [Visual Basic], walkthroughs
ms.assetid: 8ffb3be8-097d-4d3c-b71e-04555ebda2a2
ms.openlocfilehash: 6f4c303604f9cf55b4ecd500636e0d2772b6234c
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74345092"
---
# <a name="walkthrough-declaring-and-raising-events-visual-basic"></a>演练：声明和引发事件 (Visual Basic)
本演练演示如何为名为 `Widget`的类声明和引发事件。 完成这些步骤后，你可能需要阅读相关主题[演练：处理事件](../../../../visual-basic/programming-guide/language-features/events/walkthrough-handling-events.md)，其中显示了如何使用 `Widget` 对象中的事件来提供应用程序中的状态信息。  
  
## <a name="the-widget-class"></a>小组件类  
 假设你有一个 `Widget` 类。 您的 `Widget` 类有一个可能需要很长时间才能执行的方法，并且您希望您的应用程序能够提供某种类型的完成指示器。  
  
 当然，您可以使 `Widget` 对象显示一个百分比完成对话框，但随后在您使用 `Widget` 类的每个项目中都将出现该对话框。 对象设计的一个很好的原则是让使用对象的应用程序处理用户界面，除非对象的全部用途是管理窗体或对话框。  
  
 `Widget` 的目的是执行其他任务，因此最好添加 `PercentDone` 事件，并让调用 `Widget`的方法的过程处理该事件并显示状态更新。 `PercentDone` 事件还可以提供取消任务的机制。  
  
#### <a name="to-build-the-code-example-for-this-topic"></a>生成本主题的代码示例  
  
1. 打开一个新的 Visual Basic Windows 应用程序项目，并创建一个名为 `Form1`的窗体。  
  
2. 将两个按钮和一个标签添加到 `Form1`。  
  
3. 按下表所示命名对象。  
  
    |Object|属性|设置|  
    |------------|--------------|-------------|  
    |`Button1`|`Text`|启动任务|  
    |`Button2`|`Text`|取消|  
    |`Label`|`(Name)`, `Text`|lblPercentDone, 0|  
  
4. 在 "**项目**" 菜单上，选择 "**添加类**"，将名为 `Widget.vb` 的类添加到项目。  
  
#### <a name="to-declare-an-event-for-the-widget-class"></a>为小组件类声明事件  
  
- 使用 `Event` 关键字在 `Widget` 类中声明事件。 请注意，事件可以有 `ByVal` 和 `ByRef` 参数，如 `Widget``PercentDone` 事件所示：  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnWalkthroughDeclaringAndRaisingEvents/VB/Widget.vb#1)]  
  
 当调用对象收到 `PercentDone` 事件时，`Percent` 参数包含完成的任务的百分比。 `Cancel` 参数可以设置为 `True` 以取消引发事件的方法。  
  
> [!NOTE]
> 可以声明事件自变量，就像处理过程的参数一样，但有以下例外：事件不能具有 `Optional` 或 `ParamArray` 参数，并且事件没有返回值。  
  
 `PercentDone` 事件由 `Widget` 类的 `LongTask` 方法引发。 `LongTask` 采用以下两个参数：方法在经过一段时间后进行工作，并在 `LongTask` 暂停以引发 `PercentDone` 事件之前的最小时间间隔。  
  
#### <a name="to-raise-the-percentdone-event"></a>引发 PercentDone 事件  
  
1. 若要简化对此类使用的 `Timer` 属性的访问，请将 `Imports` 语句添加到类模块的 "声明" 部分的顶部，并在 `Class Widget` 语句的上方。  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnWalkthroughDeclaringAndRaisingEvents/VB/Widget.vb#2)]  
  
2. 将下面的代码添加到 `Widget` 类中:  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnWalkthroughDeclaringAndRaisingEvents/VB/Widget.vb#3)]  
  
 当应用程序调用 `LongTask` 方法时，`Widget` 类每 `MinimumInterval` 秒引发 `PercentDone` 事件。 当事件返回时，`LongTask` 会检查 `Cancel` 参数是否设置为 `True`。  
  
 此处有一些免责声明是必需的。 为简单起见，`LongTask` 过程假设您事先知道任务将花费多长时间。 几乎不会出现这种情况。 将任务划分为偶大的块可能比较困难，通常，用户最重要的是，用户只需经过一段时间，就能看出发生了什么情况。  
  
 在此示例中，可能已发现另一个缺陷。 `Timer` 属性返回从午夜开始经过的秒数;因此，如果应用程序在午夜之前启动，则该应用程序会停滞。 更仔细地测量时间的方法会将这种情况（例如这种情况）考虑在内，或者使用 `Now`等属性来完全避免这类情况。  
  
 现在 `Widget` 类可以引发事件，您可以转到下一个演练。 [演练：处理事件](../../../../visual-basic/programming-guide/language-features/events/walkthrough-handling-events.md)演示如何使用 `WithEvents` 将事件处理程序与 `PercentDone` 事件关联。  
  
## <a name="see-also"></a>另请参阅

- <xref:Microsoft.VisualBasic.DateAndTime.Timer%2A>
- <xref:Microsoft.VisualBasic.DateAndTime.Now%2A>
- [演练：处理事件](../../../../visual-basic/programming-guide/language-features/events/walkthrough-handling-events.md)
- [事件](../../../../visual-basic/programming-guide/language-features/events/index.md)
