---
title: 如何：创建状态机工作流
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 3ec60e8f-fad4-493e-a426-e7962d7aee8c
ms.openlocfilehash: 451f9581ae997ad86fee968fa978713db2049455
ms.sourcegitcommit: 581ab03291e91983459e56e40ea8d97b5189227e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/27/2019
ms.locfileid: "70044390"
---
# <a name="how-to-create-a-state-machine-workflow"></a><span data-ttu-id="ae646-102">如何：创建状态机工作流</span><span class="sxs-lookup"><span data-stu-id="ae646-102">How to: Create a State Machine Workflow</span></span>
<span data-ttu-id="ae646-103">工作流可基于内置活动以及自定义活动来构造。</span><span class="sxs-lookup"><span data-stu-id="ae646-103">Workflows can be constructed from built-in activities as well as from custom activities.</span></span> <span data-ttu-id="ae646-104">本主题介绍如何创建一个工作流，该工作流使用内置活动（如<xref:System.Activities.Statements.StateMachine>活动）和上一步[中的自定义活动如何：创建活动](how-to-create-an-activity.md)主题。</span><span class="sxs-lookup"><span data-stu-id="ae646-104">This topic steps through creating a workflow that uses both built-in activities such as the <xref:System.Activities.Statements.StateMachine> activity, and the custom activities from the previous [How to: Create an Activity](how-to-create-an-activity.md) topic.</span></span> <span data-ttu-id="ae646-105">该工作流模拟猜数游戏。</span><span class="sxs-lookup"><span data-stu-id="ae646-105">The workflow models a number guessing game.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="ae646-106">入门教程中的每个主题都依赖于前面的主题。</span><span class="sxs-lookup"><span data-stu-id="ae646-106">Each topic in the Getting Started tutorial depends on the previous topics.</span></span> <span data-ttu-id="ae646-107">若要完成本主题，必须先完成[以下操作：创建活动](how-to-create-an-activity.md)。</span><span class="sxs-lookup"><span data-stu-id="ae646-107">To complete this topic, you must first complete [How to: Create an Activity](how-to-create-an-activity.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="ae646-108">若要下载完整版教程，请参阅 [Windows Workflow Foundation (WF45) — 入门教程](https://go.microsoft.com/fwlink/?LinkID=248976)。</span><span class="sxs-lookup"><span data-stu-id="ae646-108">To download a completed version of the tutorial, see [Windows Workflow Foundation (WF45) - Getting Started Tutorial](https://go.microsoft.com/fwlink/?LinkID=248976).</span></span>  
  
### <a name="to-create-the-workflow"></a><span data-ttu-id="ae646-109">创建工作流</span><span class="sxs-lookup"><span data-stu-id="ae646-109">To create the workflow</span></span>  
  
1. <span data-ttu-id="ae646-110">在**解决方案资源管理器**中右键单击 " **NumberGuessWorkflowActivities** "，然后选择 "**添加**"、"**新建项**"。</span><span class="sxs-lookup"><span data-stu-id="ae646-110">Right-click **NumberGuessWorkflowActivities** in **Solution Explorer** and select **Add**, **New Item**.</span></span>  
  
2. <span data-ttu-id="ae646-111">在 "**已安装**的**公共项**" 节点中，选择 "**工作流**"。</span><span class="sxs-lookup"><span data-stu-id="ae646-111">In the **Installed**, **Common Items** node, select **Workflow**.</span></span> <span data-ttu-id="ae646-112">从 "**工作流**" 列表中选择 "**活动**"。</span><span class="sxs-lookup"><span data-stu-id="ae646-112">Select **Activity** from the **Workflow** list.</span></span>  
  
3. <span data-ttu-id="ae646-113">在`StateMachineNumberGuessWorkflow` "**名称**" 框中键入，然后单击 "**添加**"。</span><span class="sxs-lookup"><span data-stu-id="ae646-113">Type `StateMachineNumberGuessWorkflow` into the **Name** box and click **Add**.</span></span>  
  
4. <span data-ttu-id="ae646-114">将 " **StateMachine** " 活动从 "**工具箱**" 的 "**状态机**" 部分拖放到工作流设计图面上的 "在**此处放置活动**" 标签上。</span><span class="sxs-lookup"><span data-stu-id="ae646-114">Drag a **StateMachine** activity from the **State Machine** section of the **Toolbox** and drop it onto the **Drop activity here** label on the workflow design surface.</span></span>  
  
### <a name="to-create-the-workflow-variables-and-arguments"></a><span data-ttu-id="ae646-115">创建工作流变量和自变量</span><span class="sxs-lookup"><span data-stu-id="ae646-115">To create the workflow variables and arguments</span></span>  
  
1. <span data-ttu-id="ae646-116">在**解决方案资源管理器**中双击 " **statemachinenumberguessworkflow.xaml** " 以在设计器中显示工作流（如果尚未显示）。</span><span class="sxs-lookup"><span data-stu-id="ae646-116">Double-click **StateMachineNumberGuessWorkflow.xaml** in **Solution Explorer** to display the workflow in the designer, if it is not already displayed.</span></span>  
  
2. <span data-ttu-id="ae646-117">单击工作流设计器左下方的 "**参数**" 以显示 "**参数**" 窗格。</span><span class="sxs-lookup"><span data-stu-id="ae646-117">Click **Arguments** in the lower-left side of the workflow designer to display the **Arguments** pane.</span></span>  
  
3. <span data-ttu-id="ae646-118">单击 "**创建自变量**"。</span><span class="sxs-lookup"><span data-stu-id="ae646-118">Click **Create Argument**.</span></span>  
  
4. <span data-ttu-id="ae646-119">在`MaxNumber` "**名称**" 框中键入，从 "**方向**" 下拉列表**中**选择 "输入"，从 "**参数类型**" 下拉列表中选择 " **Int32** "，然后按 enter 保存该参数。</span><span class="sxs-lookup"><span data-stu-id="ae646-119">Type `MaxNumber` into the **Name** box, select **In** from the **Direction** drop-down list, select **Int32** from the **Argument type** drop-down list, and then press ENTER to save the argument.</span></span>  
  
5. <span data-ttu-id="ae646-120">单击 "**创建自变量**"。</span><span class="sxs-lookup"><span data-stu-id="ae646-120">Click **Create Argument**.</span></span>  
  
6. <span data-ttu-id="ae646-121">在`Turns`新添加    的参数下方的 "名称" 框中键入，从 "方向" 下拉列表中选择 "向外"，从 "参数类型" 下拉列表中选择 "Int32"，然后按 enter。 `MaxNumber`</span><span class="sxs-lookup"><span data-stu-id="ae646-121">Type `Turns` into the **Name** box that is below the newly added `MaxNumber` argument, select **Out** from the **Direction** drop-down list, select **Int32** from the **Argument type** drop-down list, and then press ENTER.</span></span>  
  
7. <span data-ttu-id="ae646-122">单击活动设计器左下方的 "**参数**"，以关闭 "**参数**" 窗格。</span><span class="sxs-lookup"><span data-stu-id="ae646-122">Click **Arguments** in the lower-left side of the activity designer to close the **Arguments** pane.</span></span>  
  
8. <span data-ttu-id="ae646-123">单击工作流设计器左下方的 "**变量**"，以显示 "**变量**" 窗格。</span><span class="sxs-lookup"><span data-stu-id="ae646-123">Click **Variables** in the lower-left side of the workflow designer to display the **Variables** pane.</span></span>  
  
9. <span data-ttu-id="ae646-124">单击 "**创建变量**"。</span><span class="sxs-lookup"><span data-stu-id="ae646-124">Click **Create Variable**.</span></span>  
  
    > [!TIP]
    > <span data-ttu-id="ae646-125">如果未显示 "**创建变量**" 框，请<xref:System.Activities.Statements.StateMachine>单击工作流设计器图面上的活动以选择它。</span><span class="sxs-lookup"><span data-stu-id="ae646-125">If no **Create Variable** box is displayed, click the <xref:System.Activities.Statements.StateMachine> activity on the workflow designer surface to select it.</span></span>  
  
10. <span data-ttu-id="ae646-126">在`Guess` "**名称**" 框中键入，从 "**变量类型**" 下拉列表中选择 " **Int32** "，然后按 enter 保存变量。</span><span class="sxs-lookup"><span data-stu-id="ae646-126">Type `Guess` into the **Name** box, select **Int32** from the **Variable type** drop-down list, and then press ENTER to save the variable.</span></span>  
  
11. <span data-ttu-id="ae646-127">单击 "**创建变量**"。</span><span class="sxs-lookup"><span data-stu-id="ae646-127">Click **Create Variable**.</span></span>  
  
12. <span data-ttu-id="ae646-128">在`Target` "**名称**" 框中键入，从 "**变量类型**" 下拉列表中选择 " **Int32** "，然后按 enter 保存变量。</span><span class="sxs-lookup"><span data-stu-id="ae646-128">Type `Target` into the **Name** box, select **Int32** from the **Variable type** drop-down list, and then press ENTER to save the variable.</span></span>  
  
13. <span data-ttu-id="ae646-129">单击活动设计器左下方的 "**变量**"，以关闭 "**变量**" 窗格。</span><span class="sxs-lookup"><span data-stu-id="ae646-129">Click **Variables** in the lower-left side of the activity designer to close the **Variables** pane.</span></span>  
  
### <a name="to-add-the-workflow-activities"></a><span data-ttu-id="ae646-130">添加工作流活动</span><span class="sxs-lookup"><span data-stu-id="ae646-130">To add the workflow activities</span></span>  
  
1. <span data-ttu-id="ae646-131">单击**State1**以将其选中。</span><span class="sxs-lookup"><span data-stu-id="ae646-131">Click **State1** to select it.</span></span> <span data-ttu-id="ae646-132">在 "**属性" 窗口**中，将**DisplayName**更改为`Initialize Target`。</span><span class="sxs-lookup"><span data-stu-id="ae646-132">In the **Properties Window**, change the **DisplayName** to `Initialize Target`.</span></span>  
  
    > [!TIP]
    > <span data-ttu-id="ae646-133">如果未显示 "**属性" 窗口**，请从 "**视图**" 菜单中选择 "**属性窗口**"。</span><span class="sxs-lookup"><span data-stu-id="ae646-133">If the **Properties Window** is not displayed, select **Properties Window** from the **View** menu.</span></span>  
  
2. <span data-ttu-id="ae646-134">在工作流设计器中，双击新重命名的 "**初始化目标**" 状态以将其展开。</span><span class="sxs-lookup"><span data-stu-id="ae646-134">Double-click the newly renamed **Initialize Target** state in the workflow designer to expand it.</span></span>  
  
3. <span data-ttu-id="ae646-135">将 " **Assign** " 活动从 "**工具箱**" 的 "**基元**" 部分拖放到 "状态" 的 "**输入**" 部分。</span><span class="sxs-lookup"><span data-stu-id="ae646-135">Drag an **Assign** activity from the **Primitives** section of the **Toolbox** and drop it onto the **Entry** section of the state.</span></span> <span data-ttu-id="ae646-136">在`Target` "**到**" 框中键入，然后在 "**输入C#表达式**" 或 "**输入 VB 表达式**" 框中键入以下表达式。</span><span class="sxs-lookup"><span data-stu-id="ae646-136">Type `Target` into the **To** box and the following expression into the **Enter a C# expression** or **Enter a VB expression** box.</span></span>  
  
    ```vb  
    New System.Random().Next(1, MaxNumber + 1)  
    ```  
  
    ```csharp  
    new System.Random().Next(1, MaxNumber + 1)  
    ```  
  
    > [!TIP]
    > <span data-ttu-id="ae646-137">如果 "**工具箱**" 窗口未显示，请从 "**视图**" 菜单中选择 **"工具箱**"。</span><span class="sxs-lookup"><span data-stu-id="ae646-137">If the **Toolbox** window is not displayed, select **Toolbox** from the **View** menu.</span></span>  
  
4. <span data-ttu-id="ae646-138">通过单击工作流设计器顶部显示的痕迹导航中的 "状态机"，返回到工作流设计**器中的**"总体状态机" 视图。</span><span class="sxs-lookup"><span data-stu-id="ae646-138">Return to the overall state machine view in the workflow designer by clicking **StateMachine** in the breadcrumb display at the top of the workflow designer.</span></span>  
  
5. <span data-ttu-id="ae646-139">将 "**状态**" 活动从 "**工具箱**" 的 "**状态机**" 部分拖到工作流设计器上，并将其悬停在 "**初始化目标**" 状态。</span><span class="sxs-lookup"><span data-stu-id="ae646-139">Drag a **State** activity from the **State Machine** section of the **Toolbox** onto the workflow designer and hover it over the **Initialize Target** state.</span></span> <span data-ttu-id="ae646-140">请注意，当新状态位于其上时，将在**初始化目标**状态周围显示四个三角形。</span><span class="sxs-lookup"><span data-stu-id="ae646-140">Note that four triangles will appear around the **Initialize Target** state when the new state is over it.</span></span> <span data-ttu-id="ae646-141">将新状态置于紧靠 "**初始化目标**" 状态下的三角形上。</span><span class="sxs-lookup"><span data-stu-id="ae646-141">Drop the new state on the triangle that is immediately below the **Initialize Target** state.</span></span> <span data-ttu-id="ae646-142">这会将新状态置于工作流上，并创建从**初始化目标**状态到新状态的转换。</span><span class="sxs-lookup"><span data-stu-id="ae646-142">This places the new state onto the workflow and creates a transition from the **Initialize Target** state to the new state.</span></span>  
  
6. <span data-ttu-id="ae646-143">单击 " **State1** " 将其选中，将 " `Enter Guess` **DisplayName** " 更改为，然后在工作流设计器中双击该状态以将其展开。</span><span class="sxs-lookup"><span data-stu-id="ae646-143">Click **State1** to select it, change the **DisplayName** to `Enter Guess`, and then double-click the state in the workflow designer to expand it.</span></span>  
  
7. <span data-ttu-id="ae646-144">将 " **WriteLine** " 活动从 "**工具箱**" 的 "**基元**" 部分拖放到 "状态" 的 "**输入**" 部分。</span><span class="sxs-lookup"><span data-stu-id="ae646-144">Drag a **WriteLine** activity from the **Primitives** section of the **Toolbox** and drop it onto the **Entry** section of the state.</span></span>  
  
8. <span data-ttu-id="ae646-145">在**WriteLine**的 "**文本**" 属性框中键入以下表达式。</span><span class="sxs-lookup"><span data-stu-id="ae646-145">Type the following expression into the **Text** property box of the **WriteLine**.</span></span>  
  
    ```vb  
    "Please enter a number between 1 and " & MaxNumber  
    ```  
  
    ```csharp  
    "Please enter a number between 1 and " + MaxNumber  
    ```  
  
9. <span data-ttu-id="ae646-146">将 " **Assign** " 活动从 "**工具箱**" 的 "**基元**" 部分拖放到状态的 "**退出**" 部分。</span><span class="sxs-lookup"><span data-stu-id="ae646-146">Drag an **Assign** activity from the **Primitives** section of the **Toolbox** and drop onto the **Exit** section of the state.</span></span>  
  
10. <span data-ttu-id="ae646-147">在`Turns` "**到**" 框中`Turns + 1`键入，然后在 "**输入C#表达式**" 或 "**输入 VB 表达式**" 框中键入。</span><span class="sxs-lookup"><span data-stu-id="ae646-147">Type `Turns` into the **To** box and `Turns + 1` into the **Enter a C# expression** or **Enter a VB expression** box.</span></span>  
  
11. <span data-ttu-id="ae646-148">通过单击工作流设计器顶部显示的痕迹导航中的 "状态机"，返回到工作流设计**器中的**"总体状态机" 视图。</span><span class="sxs-lookup"><span data-stu-id="ae646-148">Return to the overall state machine view in the workflow designer by clicking **StateMachine** in the breadcrumb display at the top of the workflow designer.</span></span>  
  
12. <span data-ttu-id="ae646-149">从 "**工具箱**" 的 "**状态机**" 部分拖放 " **FinalState** " 活动，将其悬停在 "**输入推测**状态" 上，并将其放到 "**输入推测**" 状态右侧显示的三角形上，以便转换在**输入 Guess**和**FinalState**之间创建。</span><span class="sxs-lookup"><span data-stu-id="ae646-149">Drag a **FinalState** activity from the **State Machine** section of the **Toolbox**, hover it over the **Enter Guess** state, and drop it onto the triangle that appears to the right of the **Enter Guess** state so that a transition is created between **Enter Guess** and **FinalState**.</span></span>  
  
13. <span data-ttu-id="ae646-150">转换的默认名称为**T2**。</span><span class="sxs-lookup"><span data-stu-id="ae646-150">The default name of the transition is **T2**.</span></span> <span data-ttu-id="ae646-151">单击工作流设计器中的转换以将其选中，并将其**DisplayName**设置为 "**猜测正确**"。</span><span class="sxs-lookup"><span data-stu-id="ae646-151">Click the transition in the workflow designer to select it, and set its **DisplayName** to **Guess Correct**.</span></span> <span data-ttu-id="ae646-152">然后，单击并选择 " **FinalState**"，将其拖到右侧，以便在不覆盖两种状态之一的情况下显示完整转换名称的空间。</span><span class="sxs-lookup"><span data-stu-id="ae646-152">Then click and select the **FinalState**, and drag it to the right so that there is room for the full transition name to be displayed without overlaying either of the two states.</span></span> <span data-ttu-id="ae646-153">这样可以方便完成本教程中的剩余步骤。</span><span class="sxs-lookup"><span data-stu-id="ae646-153">This will make it easier to complete the remaining steps in the tutorial.</span></span>  
  
14. <span data-ttu-id="ae646-154">双击工作流设计器中新重命名的 "**猜测正确**转换"，将其展开。</span><span class="sxs-lookup"><span data-stu-id="ae646-154">Double-click the newly renamed **Guess Correct** transition in the workflow designer to expand it.</span></span>  
  
15. <span data-ttu-id="ae646-155">将 " **ReadInt** " 活动从 "**工具箱**" 的 " **NumberGuessWorkflowActivities** " 部分拖放到转换的 "**触发器**" 部分。</span><span class="sxs-lookup"><span data-stu-id="ae646-155">Drag a **ReadInt** activity from the **NumberGuessWorkflowActivities** section of the **Toolbox** and drop it in the **Trigger** section of the transition.</span></span>  
  
16. <span data-ttu-id="ae646-156">在 " **ReadInt** " 活动的 "**属性" 窗口**中，在 " **BookmarkName** " 属性值框中键入`Guess` `"EnterGuess"`包含引号，然后在 "**结果**属性值" 框中键入。</span><span class="sxs-lookup"><span data-stu-id="ae646-156">In the **Properties Window** for the **ReadInt** activity, type `"EnterGuess"` including the quotes into the **BookmarkName** property value box, and type `Guess` into the **Result** property value box</span></span>  
  
17. <span data-ttu-id="ae646-157">在 "**推测正确**转换的**条件**" 属性值框中键入以下表达式。</span><span class="sxs-lookup"><span data-stu-id="ae646-157">Type the following expression into the **Guess Correct** transition’s **Condition** property value box.</span></span>  
  
    ```vb  
    Guess = Target  
    ```  
  
    ```csharp  
    Guess == Target  
    ```  
  
18. <span data-ttu-id="ae646-158">通过单击工作流设计器顶部显示的痕迹导航中的 "状态机"，返回到工作流设计**器中的**"总体状态机" 视图。</span><span class="sxs-lookup"><span data-stu-id="ae646-158">Return to the overall state machine view in the workflow designer by clicking **StateMachine** in the breadcrumb display at the top of the workflow designer.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="ae646-159">当收到触发器事件和 <xref:System.Activities.Statements.Transition.Condition%2A>（如果存在）时，将发生转换，计算结果为 `True`。</span><span class="sxs-lookup"><span data-stu-id="ae646-159">A transition occurs when the trigger event is received and the <xref:System.Activities.Statements.Transition.Condition%2A>, if present, evaluates to `True`.</span></span> <span data-ttu-id="ae646-160">对于此转换，如果用户`Guess`与随机生成`Target`的匹配，则控制将传递到**FinalState** ，工作流完成。</span><span class="sxs-lookup"><span data-stu-id="ae646-160">For this transition, if the user’s `Guess` matches the randomly generated `Target`, then control passes to the **FinalState** and the workflow completes.</span></span>  
  
19. <span data-ttu-id="ae646-161">根据推测是否正确，工作流应转换为**FinalState**或返回到另一个 Try 的**进入推测**状态。</span><span class="sxs-lookup"><span data-stu-id="ae646-161">Depending on whether the guess is correct, the workflow should transition either to the **FinalState** or back to the **Enter Guess** state for another try.</span></span> <span data-ttu-id="ae646-162">这两个转换共享等待用户推测通过**ReadInt**活动接收的相同触发器。</span><span class="sxs-lookup"><span data-stu-id="ae646-162">Both transitions share the same trigger of waiting for the user’s guess to be received via the **ReadInt** activity.</span></span> <span data-ttu-id="ae646-163">这称为共享转换。</span><span class="sxs-lookup"><span data-stu-id="ae646-163">This is called a shared transition.</span></span> <span data-ttu-id="ae646-164">若要创建共享转换，请单击指示**推测正确**转换开始的圆圈，然后将其拖到所需状态。</span><span class="sxs-lookup"><span data-stu-id="ae646-164">To create a shared transition, click the circle that indicates the start of the **Guess Correct** transition and drag it to the desired state.</span></span> <span data-ttu-id="ae646-165">在这种情况下，转换是一种自转换，因此拖动**推测正确**转换的开始点，并将其放回**Enter 推测**状态的底部。</span><span class="sxs-lookup"><span data-stu-id="ae646-165">In this case the transition is a self-transition, so drag the start point of the **Guess Correct** transition and drop it back onto the bottom of the **Enter Guess** state.</span></span> <span data-ttu-id="ae646-166">创建转换后，在工作流设计器中选择该转换，并将其**DisplayName**属性设置为 "**猜测错误**"。</span><span class="sxs-lookup"><span data-stu-id="ae646-166">After creating the transition, select it in the workflow designer and set its **DisplayName** property to **Guess Incorrect**.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="ae646-167">还可以从转换设计器中创建共享的转换，方法是单击 "转换设计器" 底部的 "**添加共享触发器转换**"，然后从可用状态中选择所需的目标状态**以进行连接**下拉。</span><span class="sxs-lookup"><span data-stu-id="ae646-167">Shared transitions can also be created from within the transition designer by clicking **Add shared trigger transition** at the bottom of the transition designer, and then selecting the desired target state from the **Available states to connect** drop-down.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="ae646-168">注意，如果转换的 <xref:System.Activities.Statements.Transition.Condition%2A> 计算结果为 `false`（或所有共享触发转换条件的计算结果均为 `false`），转换将不发生，并且此状态下的所有转换的所有触发将被重新计划。</span><span class="sxs-lookup"><span data-stu-id="ae646-168">Note that if the <xref:System.Activities.Statements.Transition.Condition%2A> of a transition evaluates to `false` (or all of the conditions of a shared trigger transition evaluate to `false`), the transition will not occur and all triggers for all the transitions from the state will be rescheduled.</span></span> <span data-ttu-id="ae646-169">在本教程中，由于配置条件的方式，这种情况不会发生（我们针对猜测是正确或者错误提供了具体的操作）。</span><span class="sxs-lookup"><span data-stu-id="ae646-169">In this tutorial, this situation cannot happen because of the way the conditions are configured (we have specific actions for whether the guess is correct or incorrect).</span></span>  
  
20. <span data-ttu-id="ae646-170">在工作流设计器中双击**推测错误**的转换，以将其展开。</span><span class="sxs-lookup"><span data-stu-id="ae646-170">Double-click the **Guess Incorrect** transition in the workflow designer to expand it.</span></span> <span data-ttu-id="ae646-171">请注意，**触发器**已设置为**推测正确**转换使用的相同**ReadInt**活动。</span><span class="sxs-lookup"><span data-stu-id="ae646-171">Note that the **Trigger** is already set to the same **ReadInt** activity that was used by the **Guess Correct** transition.</span></span>  
  
21. <span data-ttu-id="ae646-172">在 " **Condition** " 属性值框中键入以下表达式。</span><span class="sxs-lookup"><span data-stu-id="ae646-172">Type the following expression into the **Condition** property value box.</span></span>  
  
    ```vb  
    Guess <> Target  
    ```  
  
    ```csharp  
    Guess != Target  
    ```  
  
22. <span data-ttu-id="ae646-173">将 " **If** " 活动从 "**工具箱**" 的 "**控制流**" 部分拖放到转换的 "**操作**" 部分。</span><span class="sxs-lookup"><span data-stu-id="ae646-173">Drag an **If** activity from the **Control Flow** section of the **Toolbox** and drop it in the **Action** section of the transition.</span></span>  
  
23. <span data-ttu-id="ae646-174">在**If**活动的**Condition**属性值框中键入以下表达式。</span><span class="sxs-lookup"><span data-stu-id="ae646-174">Type the following expression into the **If** activity’s **Condition** property value box.</span></span>  
  
    ```
    Guess < Target  
    ```  
  
24. <span data-ttu-id="ae646-175">将两个 " **WriteLine** " 活动从 "**工具箱**" 的 "**基元**" 部分拖放到 " **If** " 活动的 " **Then** " 部分，另一个处于 " **Else** " 部分。</span><span class="sxs-lookup"><span data-stu-id="ae646-175">Drag two **WriteLine** activities from the **Primitives** section of the **Toolbox** and drop them so that one is in the **Then** section of the **If** activity, and one is in the **Else** section.</span></span>  
  
25. <span data-ttu-id="ae646-176">单击 " **Then** " 部分中的 " **WriteLine** " 活动将其选中，然后在 "**文本**属性值" 框中键入以下表达式。</span><span class="sxs-lookup"><span data-stu-id="ae646-176">Click the **WriteLine** activity in the **Then** section to select it, and type the following expression into the **Text** property value box.</span></span>  
  
    ```
    "Your guess is too low."  
    ```  
  
26. <span data-ttu-id="ae646-177">单击 " **Else** " 部分中的 " **WriteLine** " 活动将其选中，然后在 "**文本**属性值" 框中键入以下表达式。</span><span class="sxs-lookup"><span data-stu-id="ae646-177">Click the **WriteLine** activity in the **Else** section to select it, and type the following expression into the **Text** property value box.</span></span>  
  
    ```
    "Your guess is too high."  
    ```  
  
27. <span data-ttu-id="ae646-178">通过单击工作流设计器顶部显示的痕迹导航中的 "状态机"，返回到工作流设计**器中的**"总体状态机" 视图。</span><span class="sxs-lookup"><span data-stu-id="ae646-178">Return to the overall state machine view in the workflow designer by clicking **StateMachine** in the breadcrumb display at the top of the workflow designer.</span></span>  
  
     <span data-ttu-id="ae646-179">下面的示例阐释已完成的工作流。</span><span class="sxs-lookup"><span data-stu-id="ae646-179">The following example illustrates the completed workflow.</span></span>  
  
     ![显示已完成状态机工作流的插图。](./media/how-to-create-a-state-machine-workflow/complete-state-machine-workflow.jpg)  
  
### <a name="to-build-the-workflow"></a><span data-ttu-id="ae646-181">生成工作流</span><span class="sxs-lookup"><span data-stu-id="ae646-181">To build the workflow</span></span>  
  
1. <span data-ttu-id="ae646-182">按 Ctrl+Shift+B 生成解决方案。</span><span class="sxs-lookup"><span data-stu-id="ae646-182">Press CTRL+SHIFT+B to build the solution.</span></span>  
  
     <span data-ttu-id="ae646-183">有关如何运行工作流的说明，请参阅下一主题[how to：运行工作流](how-to-run-a-workflow.md)。</span><span class="sxs-lookup"><span data-stu-id="ae646-183">For instructions on how to run the workflow, please see the next topic, [How to: Run a Workflow](how-to-run-a-workflow.md).</span></span> <span data-ttu-id="ae646-184">如果你已经完成[了如何：运行具有不同样式的工作流的工作流](how-to-run-a-workflow.md)步骤，[并希望使用此步骤中的状态机工作流运行它，](how-to-run-a-workflow.md#BKMK_ToRunTheApplication)[请跳到如何：运行工作流](how-to-run-a-workflow.md)。</span><span class="sxs-lookup"><span data-stu-id="ae646-184">If you have already completed the [How to: Run a Workflow](how-to-run-a-workflow.md) step with a different style of workflow and wish to run it using the state machine workflow from this step, skip ahead to the [To build and run the application](how-to-run-a-workflow.md#BKMK_ToRunTheApplication) section of [How to: Run a Workflow](how-to-run-a-workflow.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ae646-185">请参阅</span><span class="sxs-lookup"><span data-stu-id="ae646-185">See also</span></span>

- <xref:System.Activities.Statements.Flowchart>
- <xref:System.Activities.Statements.FlowDecision>
- [<span data-ttu-id="ae646-186">Windows Workflow Foundation 编程</span><span class="sxs-lookup"><span data-stu-id="ae646-186">Windows Workflow Foundation Programming</span></span>](programming.md)
- [<span data-ttu-id="ae646-187">设计工作流</span><span class="sxs-lookup"><span data-stu-id="ae646-187">Designing Workflows</span></span>](designing-workflows.md)
- [<span data-ttu-id="ae646-188">入门教程</span><span class="sxs-lookup"><span data-stu-id="ae646-188">Getting Started Tutorial</span></span>](getting-started-tutorial.md)
- [<span data-ttu-id="ae646-189">如何：创建活动</span><span class="sxs-lookup"><span data-stu-id="ae646-189">How to: Create an Activity</span></span>](how-to-create-an-activity.md)
- [<span data-ttu-id="ae646-190">如何：运行工作流</span><span class="sxs-lookup"><span data-stu-id="ae646-190">How to: Run a Workflow</span></span>](how-to-run-a-workflow.md)
