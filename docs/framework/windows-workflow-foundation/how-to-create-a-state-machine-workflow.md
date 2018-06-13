---
title: 如何：创建状态机工作流
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 3ec60e8f-fad4-493e-a426-e7962d7aee8c
ms.openlocfilehash: 00f764421d3caf44d853d26d76c6b6d872ab1e3d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33520024"
---
# <a name="how-to-create-a-state-machine-workflow"></a>如何：创建状态机工作流
工作流可基于内置活动以及自定义活动来构造。 本主题将指导通过创建工作流使用这两个内置的活动，如<xref:System.Activities.Statements.StateMachine>活动和自定义活动与上一[如何： 创建活动](../../../docs/framework/windows-workflow-foundation/how-to-create-an-activity.md)主题。 该工作流模拟猜数游戏。  
  
> [!NOTE]
>  入门教程中的每个主题都依赖于前面的主题。 若要完成本主题，必须先完成[如何： 创建活动](../../../docs/framework/windows-workflow-foundation/how-to-create-an-activity.md)。  
  
> [!NOTE]
>  若要下载完整版教程，请参阅 [Windows Workflow Foundation (WF45) — 入门教程](http://go.microsoft.com/fwlink/?LinkID=248976)。  
  
### <a name="to-create-the-workflow"></a>创建工作流  
  
1.  右键单击**NumberGuessWorkflowActivities**中**解决方案资源管理器**和选择**添加**，**新项**。  
  
2.  在**已安装**，**通用项**节点中，选择**工作流**。 选择**活动**从**工作流**列表。  
  
3.  类型`StateMachineNumberGuessWorkflow`到**名称**框中，单击**添加**。  
  
4.  拖动**StateMachine**活动从**状态机**部分**工具箱**拖放到**将活动拖至此处**上的标签工作流设计图面。  
  
### <a name="to-create-the-workflow-variables-and-arguments"></a>创建工作流变量和自变量  
  
1.  双击**StateMachineNumberGuessWorkflow.xaml**中**解决方案资源管理器**如果未显示在设计器中显示工作流。  
  
2.  单击**参数**中要显示的工作流设计器左下方**参数**窗格。  
  
3.  单击**创建自变量**。  
  
4.  类型`MaxNumber`到**名称**框中，选择**中**从**方向**下拉列表中，选择**Int32**从**自变量类型**下拉列表，然后按 ENTER 保存该自变量。  
  
5.  单击**创建自变量**。  
  
6.  类型`Turns`到**名称**低于新添加的框`MaxNumber`自变量中，选择**出**从**方向**下拉列表中，选择**Int32**从**自变量类型**下拉列表，然后按 ENTER。  
  
7.  单击**参数**要关闭的活动设计器左下方**参数**窗格。  
  
8.  单击**变量**中要显示的工作流设计器左下方**变量**窗格。  
  
9. 单击**创建变量**。  
  
    > [!TIP]
    >  如果没有**创建变量**显示框中，单击<xref:System.Activities.Statements.StateMachine>活动在工作流设计图面上以将其选中。  
  
10. 类型`Guess`到**名称**框中，选择**Int32**从**变量类型**下拉列表，然后按 ENTER 保存该变量。  
  
11. 单击**创建变量**。  
  
12. 类型`Target`到**名称**框中，选择**Int32**从**变量类型**下拉列表，然后按 ENTER 保存该变量。  
  
13. 单击**变量**要关闭的活动设计器左下方**变量**窗格。  
  
### <a name="to-add-the-workflow-activities"></a>添加工作流活动  
  
1.  单击**State1**以将其选中。 在**属性窗口**，更改**DisplayName**到`Initialize Target`。  
  
    > [!TIP]
    >  如果**属性窗口**未显示，选择**属性窗口**从**视图**菜单。  
  
2.  双击刚刚重命名**Initialize Target**状态在工作流设计器中将其展开。  
  
3.  拖动**分配**活动从**基元**部分**工具箱**拖放到**条目**部分的状态。 类型`Target`到**到**框并将以下表达式键入**输入 C# 表达式**或**输入 VB 表达式**框。  
  
    ```vb  
    New System.Random().Next(1, MaxNumber + 1)  
    ```  
  
    ```csharp  
    new System.Random().Next(1, MaxNumber + 1)  
    ```  
  
    > [!TIP]
    >  如果**工具箱**不显示窗口中，选择**工具箱**从**视图**菜单。  
  
4.  返回对整体状态机工作流设计器中的视图，通过单击**StateMachine**的痕迹显示中的工作流设计器顶部。  
  
5.  拖动**状态**活动从**状态机**部分**工具箱**拖到工作流设计器并将其悬停**Initialize Target**状态。 请注意周围将出现四个三角形**Initialize Target**在其上的新状态时的状态。 立即低于的三角形上新状态放**Initialize Target**状态。 这将新状态拖动到工作流，并创建从**Initialize Target**状态到新状态。  
  
6.  单击**State1**以选择它，更改**DisplayName**到`Enter Guess`，然后双击以将其展开工作流设计器中的状态。  
  
7.  拖动**WriteLine**活动从**基元**部分**工具箱**拖放到**条目**部分的状态。  
  
8.  以下表达式键入**文本**属性框中的**WriteLine**。  
  
    ```vb  
    "Please enter a number between 1 and " & MaxNumber  
    ```  
  
    ```csharp  
    "Please enter a number between 1 and " + MaxNumber  
    ```  
  
9. 拖动**分配**活动从**基元**部分**工具箱**和拖放到**退出**部分的状态。  
  
10. 类型`Turns`到**到**框和`Turns + 1`到**输入 C# 表达式**或**输入 VB 表达式**框。  
  
11. 返回对整体状态机工作流设计器中的视图，通过单击**StateMachine**的痕迹显示中的工作流设计器顶部。  
  
12. 拖动**FinalState**活动从**状态机**部分**工具箱**，将鼠标悬停在**Enter Guess**状态，并将其放到的右侧将显示的三角形**Enter Guess**状态，以便之间创建转换**Enter Guess**和**FinalState**。  
  
13. 转换的默认名称是**T2**。 单击该转换在工作流设计器中选择它，并设置其**DisplayName**到**Guess Correct**。 然后单击并选择**FinalState**，并将其拖到右侧，以便为完整的转换名称，而不会覆盖两个状态之一显示留出空间。 这样可以方便完成本教程中的剩余步骤。  
  
14. 双击刚刚重命名**Guess Correct**转换中工作流设计器，以将其展开。  
  
15. 拖动**ReadInt**活动从**NumberGuessWorkflowActivities**部分**工具箱**拖放**触发器**部分转换。  
  
16. 在**属性窗口**为**ReadInt**活动中，键入`"EnterGuess"`包括引号**BookmarkName**属性值框中，并键入`Guess`到**结果**属性值框中  
  
17. 以下表达式键入**Guess Correct**转换的**条件**属性值框。  
  
    ```vb  
    Guess = Target  
    ```  
  
    ```csharp  
    Guess == Target  
    ```  
  
18. 返回对整体状态机工作流设计器中的视图，通过单击**StateMachine**的痕迹显示中的工作流设计器顶部。  
  
    > [!NOTE]
    >  当收到触发器事件和 <xref:System.Activities.Statements.Transition.Condition%2A>（如果存在）时，将发生转换，计算结果为 `True`。 对于此转换，如果用户的`Guess`匹配随机生成`Target`，则将控制传递到**FinalState**并且工作流完成。  
  
19. 根据猜测是否正确，工作流应转换到**FinalState**或移回**输入猜测**状态的再试一次。 这两个转换共享同一触发器，等待接收通过用户的猜测值**ReadInt**活动。 这称为共享转换。 若要创建共享的转换，请单击圆圈，以指示开始**Guess Correct**转换并将其拖到所需的状态。 在这种情况下的转换属自行转换，因此拖动的起始点**Guess Correct**过渡，并将其放回底部**Enter Guess**状态。 创建转换之后, 在工作流设计器中选择它，并设置其**DisplayName**属性**Guess Incorrect**。  
  
    > [!NOTE]
    >  创建共享的转换可以还从在转换设计器中通过单击**添加共享的触发器转换**底部的转换设计器，然后选择所需的目标状态从**连接的可用状态**下拉列表。  
  
    > [!NOTE]
    >  注意，如果转换的 <xref:System.Activities.Statements.Transition.Condition%2A> 计算结果为 `false`（或所有共享触发转换条件的计算结果均为 `false`），转换将不发生，并且此状态下的所有转换的所有触发将被重新计划。 在本教程中，由于配置条件的方式，这种情况不会发生（我们针对猜测是正确或者错误提供了具体的操作）。  
  
20. 双击**Guess Incorrect**转换中工作流设计器，以将其展开。 请注意，**触发器**已设置为相同**ReadInt**使用的活动**Guess Correct**转换。  
  
21. 以下表达式键入**条件**属性值框。  
  
    ```vb  
    Guess <> Target  
    ```  
  
    ```csharp  
    Guess != Target  
    ```  
  
22. 拖动**如果**活动从**控制流**部分**工具箱**拖放**操作**转换的部分。  
  
23. 以下表达式键入**如果**活动的**条件**属性值框。  
  
    ```
    Guess < Target  
    ```  
  
24. 将两个**WriteLine**从活动**基元**部分**工具箱**，而且，另一个中删除它们**然后**部分**如果**活动和一个处于**Else**部分。  
  
25. 单击**WriteLine**中的活动**然后**部分以选中它，并键入以下表达式键入**文本**属性值框。  
  
    ```
    "Your guess is too low."  
    ```  
  
26. 单击**WriteLine**中的活动**Else**部分以选中它，并键入以下表达式键入**文本**属性值框。  
  
    ```
    "Your guess is too high."  
    ```  
  
27. 返回对整体状态机工作流设计器中的视图，通过单击**StateMachine**的痕迹显示中的工作流设计器顶部。  
  
     下面的示例阐释已完成的工作流。  
  
     ![已完成状态机工作流](../../../docs/framework/windows-workflow-foundation/media/wfstatemachinegettingstartedtutorialcomplete.JPG "WFStateMachineGettingStartedTutorialComplete")  
  
### <a name="to-build-the-workflow"></a>生成工作流  
  
1.  按 Ctrl+Shift+B 生成解决方案。  
  
     有关如何运行工作流，说明，请参阅下一主题[如何： 运行工作流](../../../docs/framework/windows-workflow-foundation/how-to-run-a-workflow.md)。 如果你已经完成[如何： 运行工作流](../../../docs/framework/windows-workflow-foundation/how-to-run-a-workflow.md)用不同的样式，工作流的步骤和想要使用此步骤从状态机工作流运行，跳到[生成并运行应用程序](../../../docs/framework/windows-workflow-foundation/how-to-run-a-workflow.md#BKMK_ToRunTheApplication)部分[如何： 运行工作流](../../../docs/framework/windows-workflow-foundation/how-to-run-a-workflow.md)。  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Activities.Statements.Flowchart>  
 <xref:System.Activities.Statements.FlowDecision>  
 [Windows Workflow Foundation 编程](../../../docs/framework/windows-workflow-foundation/programming.md)  
 [设计工作流](../../../docs/framework/windows-workflow-foundation/designing-workflows.md)  
 [入门教程](../../../docs/framework/windows-workflow-foundation/getting-started-tutorial.md)  
 [如何：创建活动](../../../docs/framework/windows-workflow-foundation/how-to-create-an-activity.md)  
 [如何：运行工作流](../../../docs/framework/windows-workflow-foundation/how-to-run-a-workflow.md)
