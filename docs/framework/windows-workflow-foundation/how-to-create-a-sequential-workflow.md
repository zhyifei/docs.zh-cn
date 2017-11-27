---
title: "如何：创建顺序工作流"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 5280e816-ae17-48c4-8de0-a1e6895dd8f0
caps.latest.revision: "7"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 3bf6d8b499903522ee09021bb9339ece6a5894eb
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-a-sequential-workflow"></a>如何：创建顺序工作流
工作流可基于内置活动以及自定义活动来构造。 本主题将指导通过创建工作流使用这两个内置的活动，如<xref:System.Activities.Statements.Sequence>活动和自定义活动与上一[如何： 创建活动](../../../docs/framework/windows-workflow-foundation/how-to-create-an-activity.md)主题。 该工作流模拟猜数游戏。  
  
> [!NOTE]
>  入门教程中的每个主题都依赖于前面的主题。 若要完成本主题，必须先完成[如何： 创建活动](../../../docs/framework/windows-workflow-foundation/how-to-create-an-activity.md)。  
  
> [!NOTE]
>  若要下载完整版教程，请参阅 [Windows Workflow Foundation (WF45) — 入门教程](http://go.microsoft.com/fwlink/?LinkID=248976)。  
  
### <a name="to-create-the-workflow"></a>创建工作流  
  
1.  右键单击**NumberGuessWorkflowActivities**中**解决方案资源管理器**和选择**添加**，**新项**。  
  
2.  在**已安装**，**通用项**节点中，选择**工作流**。 选择**活动**从**工作流**列表。  
  
3.  类型`SequentialNumberGuessWorkflow`到**名称**框中，单击**添加**。  
  
4.  拖动**序列**活动从**控制流**部分**工具箱**拖放到**将活动拖至此处**上的标签工作流设计图面。  
  
### <a name="to-create-the-workflow-variables-and-arguments"></a>创建工作流变量和自变量  
  
1.  双击**SequentialNumberGuessWorkflow.xaml**中**解决方案资源管理器**如果未显示在设计器中显示工作流。  
  
2.  单击**参数**中要显示的工作流设计器左下方**参数**窗格。  
  
3.  单击**创建自变量**。  
  
4.  类型`MaxNumber`到**名称**框中，选择**中**从**方向**下拉列表中，选择**Int32**从**自变量类型**下拉列表，然后按 ENTER 保存该自变量。  
  
5.  单击**创建自变量**。  
  
6.  类型`Turns`到**名称**低于新添加的框`MaxNumber`自变量中，选择**出**从**方向**下拉列表中，选择**Int32**从**自变量类型**下拉列表，然后按 ENTER。  
  
7.  单击**参数**要关闭的活动设计器左下方**参数**窗格。  
  
8.  单击**变量**中要显示的工作流设计器左下方**变量**窗格。  
  
9. 单击**创建变量**。  
  
    > [!TIP]
    >  如果没有**创建变量**显示框中，单击**序列**活动在工作流设计图面上以将其选中。  
  
10. 类型`Guess`到**名称**框中，选择**Int32**从**变量类型**下拉列表，然后按 ENTER 保存该变量。  
  
11. 单击**创建变量**。  
  
12. 类型`Target`到**名称**框中，选择**Int32**从**变量类型**下拉列表，然后按 ENTER 保存该变量。  
  
13. 单击**变量**要关闭的活动设计器左下方**变量**窗格。  
  
### <a name="to-add-the-workflow-activities"></a>添加工作流活动  
  
1.  拖动**分配**活动从**基元**部分**工具箱**拖放到**序列**活动。 类型`Target`到**到**框并将以下表达式键入**输入 C# 表达式**或**输入 VB 表达式**框。  
  
    ```vb  
    New System.Random().Next(1, MaxNumber + 1)  
    ```  
  
    ```csharp  
    new System.Random().Next(1, MaxNumber + 1)  
    ```  
  
    > [!TIP]
    >  如果**工具箱**不显示窗口中，选择**工具箱**从**视图**菜单。  
  
2.  拖动**DoWhile**活动从**控制流**部分**工具箱**拖放到工作流，以便它在之下**分配**活动。  
  
3.  以下表达式键入**DoWhile**活动的**条件**属性值框。  
  
    ```vb  
    Guess <> Target  
    ```  
  
    ```csharp  
    Guess != Target  
    ```  
  
     <xref:System.Activities.Statements.DoWhile> 活动执行其子活动，然后计算其 <xref:System.Activities.Statements.DoWhile.Condition%2A>。 如果 <xref:System.Activities.Statements.DoWhile.Condition%2A> 的计算结果为 `True`，则再次执行 <xref:System.Activities.Statements.DoWhile> 中的活动。 在此示例中，将计算用户的猜测值，并且 <xref:System.Activities.Statements.DoWhile> 继续执行，直到猜测值正确。  
  
4.  拖动**提示**活动从**NumberGuessWorkflowActivities**部分**工具箱**拖放**DoWhile**活动从前面的步骤。  
  
5.  在**属性窗口**，类型`"EnterGuess"`包括引号**BookmarkName**属性值框中为**提示**活动。 类型`Guess`到**结果**属性值框中，并键入以下表达式键入**文本**属性框。  
  
    ```vb  
    "Please enter a number between 1 and " & MaxNumber  
    ```  
  
    ```csharp  
    "Please enter a number between 1 and " + MaxNumber  
    ```  
  
    > [!TIP]
    >  如果**属性窗口**未显示，选择**属性窗口**从**视图**菜单。  
  
6.  拖动**分配**活动从**基元**部分**工具箱**拖放**DoWhile**活动以便它**提示**活动。  
  
    > [!NOTE]
    >  当删除**分配**活动时，注意如何工作流设计器自动添加**序列**活动使之同时包含**提示**活动和新添加**分配**活动。  
  
7.  类型`Turns`到**到**框和`Turns + 1`到**输入 C# 表达式**或**输入 VB 表达式**框。  
  
8.  拖动**如果**活动从**控制流**部分**工具箱**拖放**序列**活动以便它新添加的**分配**活动。  
  
9. 以下表达式键入**如果**活动的**条件**属性值框。  
  
    ```vb  
    Guess <> Target  
    ```  
  
    ```csharp  
    Guess != Target  
    ```  
  
10. 将另一个**如果**活动从**控制流**部分**工具箱**拖放**然后**部分的第一个**如果**活动。  
  
11. 以下表达式键入新添加**如果**活动的**条件**属性值框。  
  
    ```
    Guess < Target  
    ```  
  
12. 将两个**WriteLine**从活动**基元**部分**工具箱**，而且，另一个中删除它们**然后**部分新添加**如果**活动和一个处于**Else**部分。  
  
13. 单击**WriteLine**中的活动**然后**部分以选中它，并键入以下表达式键入**文本**属性值框。  
  
    ```vb  
    "Your guess is too low."  
    ```  
  
14. 单击**WriteLine**中的活动**Else**部分以选中它，并键入以下表达式键入**文本**属性值框。  
  
    ```vb  
    "Your guess is too high."  
    ```  
  
     下面的示例阐释已完成的工作流。  
  
     ![完成顺序工作流](../../../docs/framework/windows-workflow-foundation/media/wfsequentialgettingstartedtutorialcomplete.JPG "WFSequentialGettingStartedTutorialComplete")  
  
### <a name="to-build-the-workflow"></a>生成工作流  
  
1.  按 Ctrl+Shift+B 生成解决方案。  
  
     有关如何运行工作流，说明，请参阅下一主题[如何： 运行工作流](../../../docs/framework/windows-workflow-foundation/how-to-run-a-workflow.md)。 如果你已经完成[如何： 运行工作流](../../../docs/framework/windows-workflow-foundation/how-to-run-a-workflow.md)用不同的样式，工作流的步骤和想要使用此步骤中的顺序工作流运行，跳到[生成并运行应用程序](../../../docs/framework/windows-workflow-foundation/how-to-run-a-workflow.md#BKMK_ToRunTheApplication)部分[如何： 运行工作流](../../../docs/framework/windows-workflow-foundation/how-to-run-a-workflow.md)。  
  
## <a name="see-also"></a>另请参阅  
 <xref:System.Activities.Statements.Flowchart>  
 <xref:System.Activities.Statements.FlowDecision>  
 [Windows Workflow Foundation 编程](../../../docs/framework/windows-workflow-foundation/programming.md)  
 [设计工作流](../../../docs/framework/windows-workflow-foundation/designing-workflows.md)  
 [入门教程](../../../docs/framework/windows-workflow-foundation/getting-started-tutorial.md)  
 [如何：创建活动](../../../docs/framework/windows-workflow-foundation/how-to-create-an-activity.md)  
 [如何：运行工作流](../../../docs/framework/windows-workflow-foundation/how-to-run-a-workflow.md)
