---
title: 如何：创建状态机工作流
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 3ec60e8f-fad4-493e-a426-e7962d7aee8c
ms.openlocfilehash: 8098ab4b056ad6375c248e803134c35d67e3f27b
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/04/2018
ms.locfileid: "43519816"
---
# <a name="how-to-create-a-state-machine-workflow"></a><span data-ttu-id="831f4-102">如何：创建状态机工作流</span><span class="sxs-lookup"><span data-stu-id="831f4-102">How to: Create a State Machine Workflow</span></span>
<span data-ttu-id="831f4-103">工作流可基于内置活动以及自定义活动来构造。</span><span class="sxs-lookup"><span data-stu-id="831f4-103">Workflows can be constructed from built-in activities as well as from custom activities.</span></span> <span data-ttu-id="831f4-104">本主题将指导逐步创建如使用这两个内置的活动的工作流<xref:System.Activities.Statements.StateMachine>活动，并从以前的自定义活动[如何： 创建活动](../../../docs/framework/windows-workflow-foundation/how-to-create-an-activity.md)主题。</span><span class="sxs-lookup"><span data-stu-id="831f4-104">This topic steps through creating a workflow that uses both built-in activities such as the <xref:System.Activities.Statements.StateMachine> activity, and the custom activities from the previous [How to: Create an Activity](../../../docs/framework/windows-workflow-foundation/how-to-create-an-activity.md) topic.</span></span> <span data-ttu-id="831f4-105">该工作流模拟猜数游戏。</span><span class="sxs-lookup"><span data-stu-id="831f4-105">The workflow models a number guessing game.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="831f4-106">入门教程中的每个主题都依赖于前面的主题。</span><span class="sxs-lookup"><span data-stu-id="831f4-106">Each topic in the Getting Started tutorial depends on the previous topics.</span></span> <span data-ttu-id="831f4-107">若要完成本主题，必须先完成[如何： 创建活动](../../../docs/framework/windows-workflow-foundation/how-to-create-an-activity.md)。</span><span class="sxs-lookup"><span data-stu-id="831f4-107">To complete this topic, you must first complete [How to: Create an Activity](../../../docs/framework/windows-workflow-foundation/how-to-create-an-activity.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="831f4-108">若要下载本教程的完整的版本，请参阅[Windows Workflow Foundation (WF45)-入门教程](https://go.microsoft.com/fwlink/?LinkID=248976)。</span><span class="sxs-lookup"><span data-stu-id="831f4-108">To download a completed version of the tutorial, see [Windows Workflow Foundation (WF45) - Getting Started Tutorial](https://go.microsoft.com/fwlink/?LinkID=248976).</span></span>  
  
### <a name="to-create-the-workflow"></a><span data-ttu-id="831f4-109">创建工作流</span><span class="sxs-lookup"><span data-stu-id="831f4-109">To create the workflow</span></span>  
  
1.  <span data-ttu-id="831f4-110">右键单击**NumberGuessWorkflowActivities**中**解决方案资源管理器**，然后选择**添加**，**新项**。</span><span class="sxs-lookup"><span data-stu-id="831f4-110">Right-click **NumberGuessWorkflowActivities** in **Solution Explorer** and select **Add**, **New Item**.</span></span>  
  
2.  <span data-ttu-id="831f4-111">在中**已安装**，**常见项**节点中，选择**工作流**。</span><span class="sxs-lookup"><span data-stu-id="831f4-111">In the **Installed**, **Common Items** node, select **Workflow**.</span></span> <span data-ttu-id="831f4-112">选择**活动**从**工作流**列表。</span><span class="sxs-lookup"><span data-stu-id="831f4-112">Select **Activity** from the **Workflow** list.</span></span>  
  
3.  <span data-ttu-id="831f4-113">类型`StateMachineNumberGuessWorkflow`成**名称**框，然后单击**添加**。</span><span class="sxs-lookup"><span data-stu-id="831f4-113">Type `StateMachineNumberGuessWorkflow` into the **Name** box and click **Add**.</span></span>  
  
4.  <span data-ttu-id="831f4-114">拖动**StateMachine**活动从**状态机**一部分**工具箱**放到**在此处放置活动**上的标签工作流设计图面。</span><span class="sxs-lookup"><span data-stu-id="831f4-114">Drag a **StateMachine** activity from the **State Machine** section of the **Toolbox** and drop it onto the **Drop activity here** label on the workflow design surface.</span></span>  
  
### <a name="to-create-the-workflow-variables-and-arguments"></a><span data-ttu-id="831f4-115">创建工作流变量和自变量</span><span class="sxs-lookup"><span data-stu-id="831f4-115">To create the workflow variables and arguments</span></span>  
  
1.  <span data-ttu-id="831f4-116">双击**StateMachineNumberGuessWorkflow.xaml**中**解决方案资源管理器**如果未显示在设计器中，显示工作流。</span><span class="sxs-lookup"><span data-stu-id="831f4-116">Double-click **StateMachineNumberGuessWorkflow.xaml** in **Solution Explorer** to display the workflow in the designer, if it is not already displayed.</span></span>  
  
2.  <span data-ttu-id="831f4-117">单击**自变量**左下角的工作流设计器，以显示**自变量**窗格。</span><span class="sxs-lookup"><span data-stu-id="831f4-117">Click **Arguments** in the lower-left side of the workflow designer to display the **Arguments** pane.</span></span>  
  
3.  <span data-ttu-id="831f4-118">单击**创建参数**。</span><span class="sxs-lookup"><span data-stu-id="831f4-118">Click **Create Argument**.</span></span>  
  
4.  <span data-ttu-id="831f4-119">类型`MaxNumber`成**名称**框中，选择**中**从**方向**下拉列表中，选择**Int32**从**自变量类型**下拉列表，然后按 ENTER 保存该自变量。</span><span class="sxs-lookup"><span data-stu-id="831f4-119">Type `MaxNumber` into the **Name** box, select **In** from the **Direction** drop-down list, select **Int32** from the **Argument type** drop-down list, and then press ENTER to save the argument.</span></span>  
  
5.  <span data-ttu-id="831f4-120">单击**创建参数**。</span><span class="sxs-lookup"><span data-stu-id="831f4-120">Click **Create Argument**.</span></span>  
  
6.  <span data-ttu-id="831f4-121">类型`Turns`成**名称**低于新添加的框`MaxNumber`参数中，选择**Out**从**方向**下拉列表中选择**Int32**从**自变量类型**下拉列表，然后按 ENTER。</span><span class="sxs-lookup"><span data-stu-id="831f4-121">Type `Turns` into the **Name** box that is below the newly added `MaxNumber` argument, select **Out** from the **Direction** drop-down list, select **Int32** from the **Argument type** drop-down list, and then press ENTER.</span></span>  
  
7.  <span data-ttu-id="831f4-122">单击**自变量**左下角的活动设计器，以关闭**自变量**窗格。</span><span class="sxs-lookup"><span data-stu-id="831f4-122">Click **Arguments** in the lower-left side of the activity designer to close the **Arguments** pane.</span></span>  
  
8.  <span data-ttu-id="831f4-123">单击**变量**左下角的工作流设计器，以显示**变量**窗格。</span><span class="sxs-lookup"><span data-stu-id="831f4-123">Click **Variables** in the lower-left side of the workflow designer to display the **Variables** pane.</span></span>  
  
9. <span data-ttu-id="831f4-124">单击**创建的变量**。</span><span class="sxs-lookup"><span data-stu-id="831f4-124">Click **Create Variable**.</span></span>  
  
    > [!TIP]
    >  <span data-ttu-id="831f4-125">如果没有**创建变量**框中显示，请单击<xref:System.Activities.Statements.StateMachine>活动工作流设计器图面以将其选中。</span><span class="sxs-lookup"><span data-stu-id="831f4-125">If no **Create Variable** box is displayed, click the <xref:System.Activities.Statements.StateMachine> activity on the workflow designer surface to select it.</span></span>  
  
10. <span data-ttu-id="831f4-126">类型`Guess`成**名称**框中，选择**Int32**从**变量类型**下拉列表，然后按 ENTER 保存该变量。</span><span class="sxs-lookup"><span data-stu-id="831f4-126">Type `Guess` into the **Name** box, select **Int32** from the **Variable type** drop-down list, and then press ENTER to save the variable.</span></span>  
  
11. <span data-ttu-id="831f4-127">单击**创建的变量**。</span><span class="sxs-lookup"><span data-stu-id="831f4-127">Click **Create Variable**.</span></span>  
  
12. <span data-ttu-id="831f4-128">类型`Target`成**名称**框中，选择**Int32**从**变量类型**下拉列表，然后按 ENTER 保存该变量。</span><span class="sxs-lookup"><span data-stu-id="831f4-128">Type `Target` into the **Name** box, select **Int32** from the **Variable type** drop-down list, and then press ENTER to save the variable.</span></span>  
  
13. <span data-ttu-id="831f4-129">单击**变量**左下角的活动设计器，以关闭**变量**窗格。</span><span class="sxs-lookup"><span data-stu-id="831f4-129">Click **Variables** in the lower-left side of the activity designer to close the **Variables** pane.</span></span>  
  
### <a name="to-add-the-workflow-activities"></a><span data-ttu-id="831f4-130">添加工作流活动</span><span class="sxs-lookup"><span data-stu-id="831f4-130">To add the workflow activities</span></span>  
  
1.  <span data-ttu-id="831f4-131">单击**State1**以将其选中。</span><span class="sxs-lookup"><span data-stu-id="831f4-131">Click **State1** to select it.</span></span> <span data-ttu-id="831f4-132">在中**属性窗口**，更改**DisplayName**到`Initialize Target`。</span><span class="sxs-lookup"><span data-stu-id="831f4-132">In the **Properties Window**, change the **DisplayName** to `Initialize Target`.</span></span>  
  
    > [!TIP]
    >  <span data-ttu-id="831f4-133">如果**属性窗口**未显示，选择**属性窗口**从**视图**菜单。</span><span class="sxs-lookup"><span data-stu-id="831f4-133">If the **Properties Window** is not displayed, select **Properties Window** from the **View** menu.</span></span>  
  
2.  <span data-ttu-id="831f4-134">双击刚刚重命名**Initialize Target**状态处于工作流设计器，以将其展开。</span><span class="sxs-lookup"><span data-stu-id="831f4-134">Double-click the newly renamed **Initialize Target** state in the workflow designer to expand it.</span></span>  
  
3.  <span data-ttu-id="831f4-135">拖动**分配**活动从**基元**一部分**工具箱**放到**条目**状态的部分。</span><span class="sxs-lookup"><span data-stu-id="831f4-135">Drag an **Assign** activity from the **Primitives** section of the **Toolbox** and drop it onto the **Entry** section of the state.</span></span> <span data-ttu-id="831f4-136">类型`Target`成**到**框中，以下表达式**输入 C# 表达式**或**输入 VB 表达式**框。</span><span class="sxs-lookup"><span data-stu-id="831f4-136">Type `Target` into the **To** box and the following expression into the **Enter a C# expression** or **Enter a VB expression** box.</span></span>  
  
    ```vb  
    New System.Random().Next(1, MaxNumber + 1)  
    ```  
  
    ```csharp  
    new System.Random().Next(1, MaxNumber + 1)  
    ```  
  
    > [!TIP]
    >  <span data-ttu-id="831f4-137">如果**工具箱**不显示窗口中，选择**工具箱**从**视图**菜单。</span><span class="sxs-lookup"><span data-stu-id="831f4-137">If the **Toolbox** window is not displayed, select **Toolbox** from the **View** menu.</span></span>  
  
4.  <span data-ttu-id="831f4-138">返回到整体状态机工作流设计器中的视图，通过单击**StateMachine**痕迹导航中显示在工作流设计器的顶部。</span><span class="sxs-lookup"><span data-stu-id="831f4-138">Return to the overall state machine view in the workflow designer by clicking **StateMachine** in the breadcrumb display at the top of the workflow designer.</span></span>  
  
5.  <span data-ttu-id="831f4-139">拖动**状态**活动从**状态机**一部分**工具箱**拖到工作流设计器并将它悬停**Initialize Target**状态。</span><span class="sxs-lookup"><span data-stu-id="831f4-139">Drag a **State** activity from the **State Machine** section of the **Toolbox** onto the workflow designer and hover it over the **Initialize Target** state.</span></span> <span data-ttu-id="831f4-140">请注意周围会出现四个三角形**Initialize Target**新状态位于其上方时的状态。</span><span class="sxs-lookup"><span data-stu-id="831f4-140">Note that four triangles will appear around the **Initialize Target** state when the new state is over it.</span></span> <span data-ttu-id="831f4-141">下面是立即的三角形上新的状态放**Initialize Target**状态。</span><span class="sxs-lookup"><span data-stu-id="831f4-141">Drop the new state on the triangle that is immediately below the **Initialize Target** state.</span></span> <span data-ttu-id="831f4-142">这将放置到工作流的新状态，并创建从过渡**Initialize Target**状态到新状态。</span><span class="sxs-lookup"><span data-stu-id="831f4-142">This places the new state onto the workflow and creates a transition from the **Initialize Target** state to the new state.</span></span>  
  
6.  <span data-ttu-id="831f4-143">单击**State1**以选择它，更改**DisplayName**到`Enter Guess`，然后双击以将其展开工作流设计器中的状态。</span><span class="sxs-lookup"><span data-stu-id="831f4-143">Click **State1** to select it, change the **DisplayName** to `Enter Guess`, and then double-click the state in the workflow designer to expand it.</span></span>  
  
7.  <span data-ttu-id="831f4-144">拖动**WriteLine**活动从**基元**一部分**工具箱**放到**条目**状态的部分。</span><span class="sxs-lookup"><span data-stu-id="831f4-144">Drag a **WriteLine** activity from the **Primitives** section of the **Toolbox** and drop it onto the **Entry** section of the state.</span></span>  
  
8.  <span data-ttu-id="831f4-145">将以下表达式键入**文本**属性框**WriteLine**。</span><span class="sxs-lookup"><span data-stu-id="831f4-145">Type the following expression into the **Text** property box of the **WriteLine**.</span></span>  
  
    ```vb  
    "Please enter a number between 1 and " & MaxNumber  
    ```  
  
    ```csharp  
    "Please enter a number between 1 and " + MaxNumber  
    ```  
  
9. <span data-ttu-id="831f4-146">拖动**分配**活动从**基元**一部分**工具箱**拖放**退出**状态的部分。</span><span class="sxs-lookup"><span data-stu-id="831f4-146">Drag an **Assign** activity from the **Primitives** section of the **Toolbox** and drop onto the **Exit** section of the state.</span></span>  
  
10. <span data-ttu-id="831f4-147">类型`Turns`成**到**框和`Turns + 1`到**输入 C# 表达式**或**输入 VB 表达式**框。</span><span class="sxs-lookup"><span data-stu-id="831f4-147">Type `Turns` into the **To** box and `Turns + 1` into the **Enter a C# expression** or **Enter a VB expression** box.</span></span>  
  
11. <span data-ttu-id="831f4-148">返回到整体状态机工作流设计器中的视图，通过单击**StateMachine**痕迹导航中显示在工作流设计器的顶部。</span><span class="sxs-lookup"><span data-stu-id="831f4-148">Return to the overall state machine view in the workflow designer by clicking **StateMachine** in the breadcrumb display at the top of the workflow designer.</span></span>  
  
12. <span data-ttu-id="831f4-149">拖动**FinalState**活动从**状态机**一部分**工具箱**，通过将鼠标悬停在**Enter Guess**状态，并将其放上的右侧显示的三角形**Enter Guess**状态，以便之间创建转换**Enter Guess**并**FinalState**。</span><span class="sxs-lookup"><span data-stu-id="831f4-149">Drag a **FinalState** activity from the **State Machine** section of the **Toolbox**, hover it over the **Enter Guess** state, and drop it onto the triangle that appears to the right of the **Enter Guess** state so that a transition is created between **Enter Guess** and **FinalState**.</span></span>  
  
13. <span data-ttu-id="831f4-150">过渡的默认名称是**T2**。</span><span class="sxs-lookup"><span data-stu-id="831f4-150">The default name of the transition is **T2**.</span></span> <span data-ttu-id="831f4-151">单击以选中它，并设置工作流设计器中的该转换将其**DisplayName**到**Guess Correct**。</span><span class="sxs-lookup"><span data-stu-id="831f4-151">Click the transition in the workflow designer to select it, and set its **DisplayName** to **Guess Correct**.</span></span> <span data-ttu-id="831f4-152">然后单击并选择**FinalState**，并将其拖到右侧，以便为完整的转换名称，而不会覆盖两种状态之一显示留出空间。</span><span class="sxs-lookup"><span data-stu-id="831f4-152">Then click and select the **FinalState**, and drag it to the right so that there is room for the full transition name to be displayed without overlaying either of the two states.</span></span> <span data-ttu-id="831f4-153">这样可以方便完成本教程中的剩余步骤。</span><span class="sxs-lookup"><span data-stu-id="831f4-153">This will make it easier to complete the remaining steps in the tutorial.</span></span>  
  
14. <span data-ttu-id="831f4-154">双击刚刚重命名**Guess Correct**转换中工作流设计器，以将其展开。</span><span class="sxs-lookup"><span data-stu-id="831f4-154">Double-click the newly renamed **Guess Correct** transition in the workflow designer to expand it.</span></span>  
  
15. <span data-ttu-id="831f4-155">拖动**ReadInt**活动从**NumberGuessWorkflowActivities**一部分**工具箱**并将其放置**触发器**部分转换。</span><span class="sxs-lookup"><span data-stu-id="831f4-155">Drag a **ReadInt** activity from the **NumberGuessWorkflowActivities** section of the **Toolbox** and drop it in the **Trigger** section of the transition.</span></span>  
  
16. <span data-ttu-id="831f4-156">在中**属性窗口**有关**ReadInt**活动中，键入`"EnterGuess"`包括引号**BookmarkName**属性值框，然后键入`Guess`成**结果**属性值框</span><span class="sxs-lookup"><span data-stu-id="831f4-156">In the **Properties Window** for the **ReadInt** activity, type `"EnterGuess"` including the quotes into the **BookmarkName** property value box, and type `Guess` into the **Result** property value box</span></span>  
  
17. <span data-ttu-id="831f4-157">将以下表达式键入**Guess Correct**转换的**条件**属性值框。</span><span class="sxs-lookup"><span data-stu-id="831f4-157">Type the following expression into the **Guess Correct** transition’s **Condition** property value box.</span></span>  
  
    ```vb  
    Guess = Target  
    ```  
  
    ```csharp  
    Guess == Target  
    ```  
  
18. <span data-ttu-id="831f4-158">返回到整体状态机工作流设计器中的视图，通过单击**StateMachine**痕迹导航中显示在工作流设计器的顶部。</span><span class="sxs-lookup"><span data-stu-id="831f4-158">Return to the overall state machine view in the workflow designer by clicking **StateMachine** in the breadcrumb display at the top of the workflow designer.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="831f4-159">当收到触发器事件和 <xref:System.Activities.Statements.Transition.Condition%2A>（如果存在）时，将发生转换，计算结果为 `True`。</span><span class="sxs-lookup"><span data-stu-id="831f4-159">A transition occurs when the trigger event is received and the <xref:System.Activities.Statements.Transition.Condition%2A>, if present, evaluates to `True`.</span></span> <span data-ttu-id="831f4-160">对于此转换，如果用户的`Guess`匹配随机生成`Target`，则将控制传递到**FinalState**和工作流完成。</span><span class="sxs-lookup"><span data-stu-id="831f4-160">For this transition, if the user’s `Guess` matches the randomly generated `Target`, then control passes to the **FinalState** and the workflow completes.</span></span>  
  
19. <span data-ttu-id="831f4-161">根据猜测是否正确，工作流应转换到**FinalState**或回**输入猜测**另一次尝试的状态。</span><span class="sxs-lookup"><span data-stu-id="831f4-161">Depending on whether the guess is correct, the workflow should transition either to the **FinalState** or back to the **Enter Guess** state for another try.</span></span> <span data-ttu-id="831f4-162">这两个转换共享同一触发器，等待用户的猜测，若要通过接收**ReadInt**活动。</span><span class="sxs-lookup"><span data-stu-id="831f4-162">Both transitions share the same trigger of waiting for the user’s guess to be received via the **ReadInt** activity.</span></span> <span data-ttu-id="831f4-163">这称为共享转换。</span><span class="sxs-lookup"><span data-stu-id="831f4-163">This is called a shared transition.</span></span> <span data-ttu-id="831f4-164">若要创建共享的转换，请单击圆圈，以指示开头**Guess Correct**转换并将其拖到所需的状态。</span><span class="sxs-lookup"><span data-stu-id="831f4-164">To create a shared transition, click the circle that indicates the start of the **Guess Correct** transition and drag it to the desired state.</span></span> <span data-ttu-id="831f4-165">在这种情况下转换属自行转换，因此拖动的起点**Guess Correct**过渡并将其放回的底部**Enter Guess**状态。</span><span class="sxs-lookup"><span data-stu-id="831f4-165">In this case the transition is a self-transition, so drag the start point of the **Guess Correct** transition and drop it back onto the bottom of the **Enter Guess** state.</span></span> <span data-ttu-id="831f4-166">在创建转换，在工作流设计器中选择它并设置其**DisplayName**属性设置为**Guess Incorrect**。</span><span class="sxs-lookup"><span data-stu-id="831f4-166">After creating the transition, select it in the workflow designer and set its **DisplayName** property to **Guess Incorrect**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="831f4-167">共享的转换还可以创建从在转换设计器通过单击**添加共享的触发器转换**底部的转换设计器，然后选择所需的目标状态从**若要连接的可用状态**下拉列表。</span><span class="sxs-lookup"><span data-stu-id="831f4-167">Shared transitions can also be created from within the transition designer by clicking **Add shared trigger transition** at the bottom of the transition designer, and then selecting the desired target state from the **Available states to connect** drop-down.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="831f4-168">注意，如果转换的 <xref:System.Activities.Statements.Transition.Condition%2A> 计算结果为 `false`（或所有共享触发转换条件的计算结果均为 `false`），转换将不发生，并且此状态下的所有转换的所有触发将被重新计划。</span><span class="sxs-lookup"><span data-stu-id="831f4-168">Note that if the <xref:System.Activities.Statements.Transition.Condition%2A> of a transition evaluates to `false` (or all of the conditions of a shared trigger transition evaluate to `false`), the transition will not occur and all triggers for all the transitions from the state will be rescheduled.</span></span> <span data-ttu-id="831f4-169">在本教程中，由于配置条件的方式，这种情况不会发生（我们针对猜测是正确或者错误提供了具体的操作）。</span><span class="sxs-lookup"><span data-stu-id="831f4-169">In this tutorial, this situation cannot happen because of the way the conditions are configured (we have specific actions for whether the guess is correct or incorrect).</span></span>  
  
20. <span data-ttu-id="831f4-170">双击**Guess Incorrect**转换中工作流设计器，以将其展开。</span><span class="sxs-lookup"><span data-stu-id="831f4-170">Double-click the **Guess Incorrect** transition in the workflow designer to expand it.</span></span> <span data-ttu-id="831f4-171">请注意，**触发器**已设置为相同**ReadInt**使用的活动**Guess Correct**转换。</span><span class="sxs-lookup"><span data-stu-id="831f4-171">Note that the **Trigger** is already set to the same **ReadInt** activity that was used by the **Guess Correct** transition.</span></span>  
  
21. <span data-ttu-id="831f4-172">将以下表达式键入**条件**属性值框。</span><span class="sxs-lookup"><span data-stu-id="831f4-172">Type the following expression into the **Condition** property value box.</span></span>  
  
    ```vb  
    Guess <> Target  
    ```  
  
    ```csharp  
    Guess != Target  
    ```  
  
22. <span data-ttu-id="831f4-173">拖动**如果**活动从**控制流**一部分**工具箱**拖放**操作**过渡的部分。</span><span class="sxs-lookup"><span data-stu-id="831f4-173">Drag an **If** activity from the **Control Flow** section of the **Toolbox** and drop it in the **Action** section of the transition.</span></span>  
  
23. <span data-ttu-id="831f4-174">将以下表达式键入**如果**活动的**条件**属性值框。</span><span class="sxs-lookup"><span data-stu-id="831f4-174">Type the following expression into the **If** activity’s **Condition** property value box.</span></span>  
  
    ```
    Guess < Target  
    ```  
  
24. <span data-ttu-id="831f4-175">将两个**WriteLine**中的活动**基元**部分**工具箱**并将它们放这样一个都位于**然后**部分**如果**活动和一个处于**Else**部分。</span><span class="sxs-lookup"><span data-stu-id="831f4-175">Drag two **WriteLine** activities from the **Primitives** section of the **Toolbox** and drop them so that one is in the **Then** section of the **If** activity, and one is in the **Else** section.</span></span>  
  
25. <span data-ttu-id="831f4-176">单击**WriteLine**中的活动**然后**部分以选中它，并键入以下表达式**文本**属性值框。</span><span class="sxs-lookup"><span data-stu-id="831f4-176">Click the **WriteLine** activity in the **Then** section to select it, and type the following expression into the **Text** property value box.</span></span>  
  
    ```
    "Your guess is too low."  
    ```  
  
26. <span data-ttu-id="831f4-177">单击**WriteLine**中的活动**Else**部分以选中它，并键入以下表达式**文本**属性值框。</span><span class="sxs-lookup"><span data-stu-id="831f4-177">Click the **WriteLine** activity in the **Else** section to select it, and type the following expression into the **Text** property value box.</span></span>  
  
    ```
    "Your guess is too high."  
    ```  
  
27. <span data-ttu-id="831f4-178">返回到整体状态机工作流设计器中的视图，通过单击**StateMachine**痕迹导航中显示在工作流设计器的顶部。</span><span class="sxs-lookup"><span data-stu-id="831f4-178">Return to the overall state machine view in the workflow designer by clicking **StateMachine** in the breadcrumb display at the top of the workflow designer.</span></span>  
  
     <span data-ttu-id="831f4-179">下面的示例阐释已完成的工作流。</span><span class="sxs-lookup"><span data-stu-id="831f4-179">The following example illustrates the completed workflow.</span></span>  
  
     <span data-ttu-id="831f4-180">![完整的状态机工作流](../../../docs/framework/windows-workflow-foundation/media/wfstatemachinegettingstartedtutorialcomplete.JPG "WFStateMachineGettingStartedTutorialComplete")</span><span class="sxs-lookup"><span data-stu-id="831f4-180">![Completed State Machine Workflow](../../../docs/framework/windows-workflow-foundation/media/wfstatemachinegettingstartedtutorialcomplete.JPG "WFStateMachineGettingStartedTutorialComplete")</span></span>  
  
### <a name="to-build-the-workflow"></a><span data-ttu-id="831f4-181">生成工作流</span><span class="sxs-lookup"><span data-stu-id="831f4-181">To build the workflow</span></span>  
  
1.  <span data-ttu-id="831f4-182">按 Ctrl+Shift+B 生成解决方案。</span><span class="sxs-lookup"><span data-stu-id="831f4-182">Press CTRL+SHIFT+B to build the solution.</span></span>  
  
     <span data-ttu-id="831f4-183">有关如何运行工作流，说明，请参阅下一主题[如何： 运行工作流](../../../docs/framework/windows-workflow-foundation/how-to-run-a-workflow.md)。</span><span class="sxs-lookup"><span data-stu-id="831f4-183">For instructions on how to run the workflow, please see the next topic, [How to: Run a Workflow](../../../docs/framework/windows-workflow-foundation/how-to-run-a-workflow.md).</span></span> <span data-ttu-id="831f4-184">如果你已完成[如何： 运行工作流](../../../docs/framework/windows-workflow-foundation/how-to-run-a-workflow.md)使用不同样式的工作流步骤并希望使用此步骤中的状态机工作流运行它，请直接跳转到[生成并运行应用程序](../../../docs/framework/windows-workflow-foundation/how-to-run-a-workflow.md#BKMK_ToRunTheApplication)一部分[如何： 运行工作流](../../../docs/framework/windows-workflow-foundation/how-to-run-a-workflow.md)。</span><span class="sxs-lookup"><span data-stu-id="831f4-184">If you have already completed the [How to: Run a Workflow](../../../docs/framework/windows-workflow-foundation/how-to-run-a-workflow.md) step with a different style of workflow and wish to run it using the state machine workflow from this step, skip ahead to the [To build and run the application](../../../docs/framework/windows-workflow-foundation/how-to-run-a-workflow.md#BKMK_ToRunTheApplication) section of [How to: Run a Workflow](../../../docs/framework/windows-workflow-foundation/how-to-run-a-workflow.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="831f4-185">请参阅</span><span class="sxs-lookup"><span data-stu-id="831f4-185">See Also</span></span>  
 <xref:System.Activities.Statements.Flowchart>  
 <xref:System.Activities.Statements.FlowDecision>  
 [<span data-ttu-id="831f4-186">Windows Workflow Foundation 编程</span><span class="sxs-lookup"><span data-stu-id="831f4-186">Windows Workflow Foundation Programming</span></span>](../../../docs/framework/windows-workflow-foundation/programming.md)  
 [<span data-ttu-id="831f4-187">设计工作流</span><span class="sxs-lookup"><span data-stu-id="831f4-187">Designing Workflows</span></span>](../../../docs/framework/windows-workflow-foundation/designing-workflows.md)  
 [<span data-ttu-id="831f4-188">入门教程</span><span class="sxs-lookup"><span data-stu-id="831f4-188">Getting Started Tutorial</span></span>](../../../docs/framework/windows-workflow-foundation/getting-started-tutorial.md)  
 [<span data-ttu-id="831f4-189">如何：创建活动</span><span class="sxs-lookup"><span data-stu-id="831f4-189">How to: Create an Activity</span></span>](../../../docs/framework/windows-workflow-foundation/how-to-create-an-activity.md)  
 [<span data-ttu-id="831f4-190">如何：运行工作流</span><span class="sxs-lookup"><span data-stu-id="831f4-190">How to: Run a Workflow</span></span>](../../../docs/framework/windows-workflow-foundation/how-to-run-a-workflow.md)
