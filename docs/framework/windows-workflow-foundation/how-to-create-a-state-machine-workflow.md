---
title: 如何：创建状态机工作流
description: 本文创建一个工作流，该工作流使用内置活动，如 StateMachine 活动和自定义活动。
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 3ec60e8f-fad4-493e-a426-e7962d7aee8c
ms.openlocfilehash: 8a9342c07c15d65df0310c0cb35b4b2c6f2ba686
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/15/2020
ms.locfileid: "83419650"
---
# <a name="how-to-create-a-state-machine-workflow"></a><span data-ttu-id="6daf3-103">如何：创建状态机工作流</span><span class="sxs-lookup"><span data-stu-id="6daf3-103">How to: Create a State Machine Workflow</span></span>
<span data-ttu-id="6daf3-104">工作流可基于内置活动以及自定义活动来构造。</span><span class="sxs-lookup"><span data-stu-id="6daf3-104">Workflows can be constructed from built-in activities as well as from custom activities.</span></span> <span data-ttu-id="6daf3-105">本主题介绍如何创建一个工作流，该工作流使用内置活动（如 <xref:System.Activities.Statements.StateMachine> 活动）和前面的[如何：创建活动](how-to-create-an-activity.md)主题中的自定义活动。</span><span class="sxs-lookup"><span data-stu-id="6daf3-105">This topic steps through creating a workflow that uses both built-in activities such as the <xref:System.Activities.Statements.StateMachine> activity, and the custom activities from the previous [How to: Create an Activity](how-to-create-an-activity.md) topic.</span></span> <span data-ttu-id="6daf3-106">该工作流模拟猜数游戏。</span><span class="sxs-lookup"><span data-stu-id="6daf3-106">The workflow models a number guessing game.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="6daf3-107">入门教程中的每个主题都依赖于前面的主题。</span><span class="sxs-lookup"><span data-stu-id="6daf3-107">Each topic in the Getting Started tutorial depends on the previous topics.</span></span> <span data-ttu-id="6daf3-108">若要完成本主题，必须先完成[操作方法：创建活动](how-to-create-an-activity.md)。</span><span class="sxs-lookup"><span data-stu-id="6daf3-108">To complete this topic, you must first complete [How to: Create an Activity](how-to-create-an-activity.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="6daf3-109">若要下载完整版教程，请参阅 [Windows Workflow Foundation (WF45) — 入门教程](https://go.microsoft.com/fwlink/?LinkID=248976)。</span><span class="sxs-lookup"><span data-stu-id="6daf3-109">To download a completed version of the tutorial, see [Windows Workflow Foundation (WF45) - Getting Started Tutorial](https://go.microsoft.com/fwlink/?LinkID=248976).</span></span>  
  
### <a name="to-create-the-workflow"></a><span data-ttu-id="6daf3-110">创建工作流</span><span class="sxs-lookup"><span data-stu-id="6daf3-110">To create the workflow</span></span>  
  
1. <span data-ttu-id="6daf3-111">在**解决方案资源管理器**中右键单击 " **NumberGuessWorkflowActivities** "，然后选择 "**添加**"、"**新建项**"。</span><span class="sxs-lookup"><span data-stu-id="6daf3-111">Right-click **NumberGuessWorkflowActivities** in **Solution Explorer** and select **Add**, **New Item**.</span></span>  
  
2. <span data-ttu-id="6daf3-112">在 "**已安装**的**公共项**" 节点中，选择 "**工作流**"。</span><span class="sxs-lookup"><span data-stu-id="6daf3-112">In the **Installed**, **Common Items** node, select **Workflow**.</span></span> <span data-ttu-id="6daf3-113">从 **“工作流”** 列表中选择 **“活动”**。</span><span class="sxs-lookup"><span data-stu-id="6daf3-113">Select **Activity** from the **Workflow** list.</span></span>  
  
3. <span data-ttu-id="6daf3-114">`StateMachineNumberGuessWorkflow`在 "**名称**" 框中键入，然后单击 "**添加**"。</span><span class="sxs-lookup"><span data-stu-id="6daf3-114">Type `StateMachineNumberGuessWorkflow` into the **Name** box and click **Add**.</span></span>  
  
4. <span data-ttu-id="6daf3-115">将 " **StateMachine** " 活动从 "**工具箱**" 的 "**状态机**" 部分拖放到工作流设计图面上的 "在**此处放置活动**" 标签上。</span><span class="sxs-lookup"><span data-stu-id="6daf3-115">Drag a **StateMachine** activity from the **State Machine** section of the **Toolbox** and drop it onto the **Drop activity here** label on the workflow design surface.</span></span>  
  
### <a name="to-create-the-workflow-variables-and-arguments"></a><span data-ttu-id="6daf3-116">创建工作流变量和自变量</span><span class="sxs-lookup"><span data-stu-id="6daf3-116">To create the workflow variables and arguments</span></span>  
  
1. <span data-ttu-id="6daf3-117">在**解决方案资源管理器**中双击 " **statemachinenumberguessworkflow.xaml** " 以在设计器中显示工作流（如果尚未显示）。</span><span class="sxs-lookup"><span data-stu-id="6daf3-117">Double-click **StateMachineNumberGuessWorkflow.xaml** in **Solution Explorer** to display the workflow in the designer, if it is not already displayed.</span></span>  
  
2. <span data-ttu-id="6daf3-118">单击工作流设计器左下方的 "**参数**" 以显示 "**参数**" 窗格。</span><span class="sxs-lookup"><span data-stu-id="6daf3-118">Click **Arguments** in the lower-left side of the workflow designer to display the **Arguments** pane.</span></span>  
  
3. <span data-ttu-id="6daf3-119">单击 **“创建参数”**。</span><span class="sxs-lookup"><span data-stu-id="6daf3-119">Click **Create Argument**.</span></span>  
  
4. <span data-ttu-id="6daf3-120">在 `MaxNumber` "**名称**" 框中键入，从 "**方向**" 下拉列表**中**选择 "输入"，从 "**参数类型**" 下拉列表中选择 " **Int32** "，然后按 enter 保存该参数。</span><span class="sxs-lookup"><span data-stu-id="6daf3-120">Type `MaxNumber` into the **Name** box, select **In** from the **Direction** drop-down list, select **Int32** from the **Argument type** drop-down list, and then press ENTER to save the argument.</span></span>  
  
5. <span data-ttu-id="6daf3-121">单击 **“创建参数”**。</span><span class="sxs-lookup"><span data-stu-id="6daf3-121">Click **Create Argument**.</span></span>  
  
6. <span data-ttu-id="6daf3-122">在 `Turns` 新添加的参数下方的 "**名称**" 框中键入 `MaxNumber` ，从 "**方向**" 下拉列表中选择 "向**外**"，从 "**参数类型**" 下拉列表中选择 " **Int32** "，然后按 enter。</span><span class="sxs-lookup"><span data-stu-id="6daf3-122">Type `Turns` into the **Name** box that is below the newly added `MaxNumber` argument, select **Out** from the **Direction** drop-down list, select **Int32** from the **Argument type** drop-down list, and then press ENTER.</span></span>  
  
7. <span data-ttu-id="6daf3-123">单击活动设计器左下角的 **“参数”**，关闭 **“参数”** 窗格。</span><span class="sxs-lookup"><span data-stu-id="6daf3-123">Click **Arguments** in the lower-left side of the activity designer to close the **Arguments** pane.</span></span>  
  
8. <span data-ttu-id="6daf3-124">单击工作流设计器左下方的 "**变量**"，以显示 "**变量**" 窗格。</span><span class="sxs-lookup"><span data-stu-id="6daf3-124">Click **Variables** in the lower-left side of the workflow designer to display the **Variables** pane.</span></span>  
  
9. <span data-ttu-id="6daf3-125">单击 **“创建变量”**。</span><span class="sxs-lookup"><span data-stu-id="6daf3-125">Click **Create Variable**.</span></span>  
  
    > [!TIP]
    > <span data-ttu-id="6daf3-126">如果未显示 "**创建变量**" 框，请单击 <xref:System.Activities.Statements.StateMachine> 工作流设计器图面上的活动以选择它。</span><span class="sxs-lookup"><span data-stu-id="6daf3-126">If no **Create Variable** box is displayed, click the <xref:System.Activities.Statements.StateMachine> activity on the workflow designer surface to select it.</span></span>  
  
10. <span data-ttu-id="6daf3-127">在 `Guess` "**名称**" 框中键入，从 "**变量类型**" 下拉列表中选择 " **Int32** "，然后按 enter 保存变量。</span><span class="sxs-lookup"><span data-stu-id="6daf3-127">Type `Guess` into the **Name** box, select **Int32** from the **Variable type** drop-down list, and then press ENTER to save the variable.</span></span>  
  
11. <span data-ttu-id="6daf3-128">单击 **“创建变量”**。</span><span class="sxs-lookup"><span data-stu-id="6daf3-128">Click **Create Variable**.</span></span>  
  
12. <span data-ttu-id="6daf3-129">在 `Target` "**名称**" 框中键入，从 "**变量类型**" 下拉列表中选择 " **Int32** "，然后按 enter 保存变量。</span><span class="sxs-lookup"><span data-stu-id="6daf3-129">Type `Target` into the **Name** box, select **Int32** from the **Variable type** drop-down list, and then press ENTER to save the variable.</span></span>  
  
13. <span data-ttu-id="6daf3-130">单击活动设计器左下角的 **“变量”**，关闭 **“变量”** 窗格。</span><span class="sxs-lookup"><span data-stu-id="6daf3-130">Click **Variables** in the lower-left side of the activity designer to close the **Variables** pane.</span></span>  
  
### <a name="to-add-the-workflow-activities"></a><span data-ttu-id="6daf3-131">添加工作流活动</span><span class="sxs-lookup"><span data-stu-id="6daf3-131">To add the workflow activities</span></span>  
  
1. <span data-ttu-id="6daf3-132">单击**State1**以将其选中。</span><span class="sxs-lookup"><span data-stu-id="6daf3-132">Click **State1** to select it.</span></span> <span data-ttu-id="6daf3-133">在 "**属性" 窗口**中，将**DisplayName**更改为 `Initialize Target` 。</span><span class="sxs-lookup"><span data-stu-id="6daf3-133">In the **Properties Window**, change the **DisplayName** to `Initialize Target`.</span></span>  
  
    > [!TIP]
    > <span data-ttu-id="6daf3-134">如果未显示 "**属性" 窗口**，请从 "**视图**" 菜单中选择 "**属性窗口**"。</span><span class="sxs-lookup"><span data-stu-id="6daf3-134">If the **Properties Window** is not displayed, select **Properties Window** from the **View** menu.</span></span>  
  
2. <span data-ttu-id="6daf3-135">在工作流设计器中，双击新重命名的 "**初始化目标**" 状态以将其展开。</span><span class="sxs-lookup"><span data-stu-id="6daf3-135">Double-click the newly renamed **Initialize Target** state in the workflow designer to expand it.</span></span>  
  
3. <span data-ttu-id="6daf3-136">将 " **Assign** " 活动从 "**工具箱**" 的 "**基元**" 部分拖放到 "状态" 的 "**输入**" 部分。</span><span class="sxs-lookup"><span data-stu-id="6daf3-136">Drag an **Assign** activity from the **Primitives** section of the **Toolbox** and drop it onto the **Entry** section of the state.</span></span> <span data-ttu-id="6daf3-137">在 " `Target` **到**" 框中键入，然后在 "**输入 c # 表达式**" 或 "**输入 VB 表达式**" 框中键入以下表达式。</span><span class="sxs-lookup"><span data-stu-id="6daf3-137">Type `Target` into the **To** box and the following expression into the **Enter a C# expression** or **Enter a VB expression** box.</span></span>  
  
    ```vb  
    New System.Random().Next(1, MaxNumber + 1)  
    ```  
  
    ```csharp  
    new System.Random().Next(1, MaxNumber + 1)  
    ```  
  
    > [!TIP]
    > <span data-ttu-id="6daf3-138">如果未显示 **“工具箱”** 窗口，请从 **“视图”** 菜单中选择 **“工具箱”**。</span><span class="sxs-lookup"><span data-stu-id="6daf3-138">If the **Toolbox** window is not displayed, select **Toolbox** from the **View** menu.</span></span>  
  
4. <span data-ttu-id="6daf3-139">通过单击工作流设计器顶部显示的痕迹导航中的 "状态机"，返回到工作流设计**器中的**"总体状态机" 视图。</span><span class="sxs-lookup"><span data-stu-id="6daf3-139">Return to the overall state machine view in the workflow designer by clicking **StateMachine** in the breadcrumb display at the top of the workflow designer.</span></span>  
  
5. <span data-ttu-id="6daf3-140">将 "**状态**" 活动从 "**工具箱**" 的 "**状态机**" 部分拖到工作流设计器上，并将其悬停在 "**初始化目标**" 状态。</span><span class="sxs-lookup"><span data-stu-id="6daf3-140">Drag a **State** activity from the **State Machine** section of the **Toolbox** onto the workflow designer and hover it over the **Initialize Target** state.</span></span> <span data-ttu-id="6daf3-141">请注意，当新状态位于其上时，将在**初始化目标**状态周围显示四个三角形。</span><span class="sxs-lookup"><span data-stu-id="6daf3-141">Note that four triangles will appear around the **Initialize Target** state when the new state is over it.</span></span> <span data-ttu-id="6daf3-142">将新状态置于紧靠 "**初始化目标**" 状态下的三角形上。</span><span class="sxs-lookup"><span data-stu-id="6daf3-142">Drop the new state on the triangle that is immediately below the **Initialize Target** state.</span></span> <span data-ttu-id="6daf3-143">这会将新状态置于工作流上，并创建从**初始化目标**状态到新状态的转换。</span><span class="sxs-lookup"><span data-stu-id="6daf3-143">This places the new state onto the workflow and creates a transition from the **Initialize Target** state to the new state.</span></span>  
  
6. <span data-ttu-id="6daf3-144">单击 " **State1** " 将其选中，将 " **DisplayName** " 更改为 `Enter Guess` ，然后在工作流设计器中双击该状态以将其展开。</span><span class="sxs-lookup"><span data-stu-id="6daf3-144">Click **State1** to select it, change the **DisplayName** to `Enter Guess`, and then double-click the state in the workflow designer to expand it.</span></span>  
  
7. <span data-ttu-id="6daf3-145">将 " **WriteLine** " 活动从 "**工具箱**" 的 "**基元**" 部分拖放到 "状态" 的 "**输入**" 部分。</span><span class="sxs-lookup"><span data-stu-id="6daf3-145">Drag a **WriteLine** activity from the **Primitives** section of the **Toolbox** and drop it onto the **Entry** section of the state.</span></span>  
  
8. <span data-ttu-id="6daf3-146">在**WriteLine**的 "**文本**" 属性框中键入以下表达式。</span><span class="sxs-lookup"><span data-stu-id="6daf3-146">Type the following expression into the **Text** property box of the **WriteLine**.</span></span>  
  
    ```vb  
    "Please enter a number between 1 and " & MaxNumber  
    ```  
  
    ```csharp  
    "Please enter a number between 1 and " + MaxNumber  
    ```  
  
9. <span data-ttu-id="6daf3-147">将 " **Assign** " 活动从 "**工具箱**" 的 "**基元**" 部分拖放到状态的 "**退出**" 部分。</span><span class="sxs-lookup"><span data-stu-id="6daf3-147">Drag an **Assign** activity from the **Primitives** section of the **Toolbox** and drop onto the **Exit** section of the state.</span></span>  
  
10. <span data-ttu-id="6daf3-148">在 `Turns` "**到**" 框中键入，然后 `Turns + 1` 在 "**输入 c # 表达式**" 或 "**输入 VB 表达式**" 框中键入。</span><span class="sxs-lookup"><span data-stu-id="6daf3-148">Type `Turns` into the **To** box and `Turns + 1` into the **Enter a C# expression** or **Enter a VB expression** box.</span></span>  
  
11. <span data-ttu-id="6daf3-149">通过单击工作流设计器顶部显示的痕迹导航中的 "状态机"，返回到工作流设计**器中的**"总体状态机" 视图。</span><span class="sxs-lookup"><span data-stu-id="6daf3-149">Return to the overall state machine view in the workflow designer by clicking **StateMachine** in the breadcrumb display at the top of the workflow designer.</span></span>  
  
12. <span data-ttu-id="6daf3-150">从 "**工具箱**" 的 "**状态机**" 部分拖放 " **FinalState** " 活动，将其悬停在 "**输入推测**状态" 上，并将其放到 "**输入推测**" 状态右侧显示的三角形上，以便在 "**输入推测**" 和 " **FinalState**" 之间创建转换。</span><span class="sxs-lookup"><span data-stu-id="6daf3-150">Drag a **FinalState** activity from the **State Machine** section of the **Toolbox**, hover it over the **Enter Guess** state, and drop it onto the triangle that appears to the right of the **Enter Guess** state so that a transition is created between **Enter Guess** and **FinalState**.</span></span>  
  
13. <span data-ttu-id="6daf3-151">转换的默认名称为**T2**。</span><span class="sxs-lookup"><span data-stu-id="6daf3-151">The default name of the transition is **T2**.</span></span> <span data-ttu-id="6daf3-152">单击工作流设计器中的转换以将其选中，并将其**DisplayName**设置为 "**猜测正确**"。</span><span class="sxs-lookup"><span data-stu-id="6daf3-152">Click the transition in the workflow designer to select it, and set its **DisplayName** to **Guess Correct**.</span></span> <span data-ttu-id="6daf3-153">然后，单击并选择 " **FinalState**"，将其拖到右侧，以便在不覆盖两种状态之一的情况下显示完整转换名称的空间。</span><span class="sxs-lookup"><span data-stu-id="6daf3-153">Then click and select the **FinalState**, and drag it to the right so that there is room for the full transition name to be displayed without overlaying either of the two states.</span></span> <span data-ttu-id="6daf3-154">这样可以方便完成本教程中的剩余步骤。</span><span class="sxs-lookup"><span data-stu-id="6daf3-154">This will make it easier to complete the remaining steps in the tutorial.</span></span>  
  
14. <span data-ttu-id="6daf3-155">双击工作流设计器中新重命名的 "**猜测正确**转换"，将其展开。</span><span class="sxs-lookup"><span data-stu-id="6daf3-155">Double-click the newly renamed **Guess Correct** transition in the workflow designer to expand it.</span></span>  
  
15. <span data-ttu-id="6daf3-156">将 " **ReadInt** " 活动从 "**工具箱**" 的 " **NumberGuessWorkflowActivities** " 部分拖放到转换的 "**触发器**" 部分。</span><span class="sxs-lookup"><span data-stu-id="6daf3-156">Drag a **ReadInt** activity from the **NumberGuessWorkflowActivities** section of the **Toolbox** and drop it in the **Trigger** section of the transition.</span></span>  
  
16. <span data-ttu-id="6daf3-157">在 " **ReadInt** " 活动的 "**属性" 窗口**中，在 `"EnterGuess"` " **BookmarkName** " 属性值框中键入包含引号，然后在 `Guess` "**结果**属性值" 框中键入。</span><span class="sxs-lookup"><span data-stu-id="6daf3-157">In the **Properties Window** for the **ReadInt** activity, type `"EnterGuess"` including the quotes into the **BookmarkName** property value box, and type `Guess` into the **Result** property value box</span></span>  
  
17. <span data-ttu-id="6daf3-158">在 "**推测正确**转换的**条件**" 属性值框中键入以下表达式。</span><span class="sxs-lookup"><span data-stu-id="6daf3-158">Type the following expression into the **Guess Correct** transition’s **Condition** property value box.</span></span>  
  
    ```vb  
    Guess = Target  
    ```  
  
    ```csharp  
    Guess == Target  
    ```  
  
18. <span data-ttu-id="6daf3-159">通过单击工作流设计器顶部显示的痕迹导航中的 "状态机"，返回到工作流设计**器中的**"总体状态机" 视图。</span><span class="sxs-lookup"><span data-stu-id="6daf3-159">Return to the overall state machine view in the workflow designer by clicking **StateMachine** in the breadcrumb display at the top of the workflow designer.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="6daf3-160">当收到触发器事件和 <xref:System.Activities.Statements.Transition.Condition%2A>（如果存在）时，将发生转换，计算结果为 `True`。</span><span class="sxs-lookup"><span data-stu-id="6daf3-160">A transition occurs when the trigger event is received and the <xref:System.Activities.Statements.Transition.Condition%2A>, if present, evaluates to `True`.</span></span> <span data-ttu-id="6daf3-161">对于此转换，如果用户 `Guess` 与随机生成的匹配 `Target` ，则控制将传递到**FinalState** ，工作流完成。</span><span class="sxs-lookup"><span data-stu-id="6daf3-161">For this transition, if the user’s `Guess` matches the randomly generated `Target`, then control passes to the **FinalState** and the workflow completes.</span></span>  
  
19. <span data-ttu-id="6daf3-162">根据推测是否正确，工作流应转换为**FinalState**或返回到另一个 Try 的**进入推测**状态。</span><span class="sxs-lookup"><span data-stu-id="6daf3-162">Depending on whether the guess is correct, the workflow should transition either to the **FinalState** or back to the **Enter Guess** state for another try.</span></span> <span data-ttu-id="6daf3-163">这两个转换共享等待用户推测通过**ReadInt**活动接收的相同触发器。</span><span class="sxs-lookup"><span data-stu-id="6daf3-163">Both transitions share the same trigger of waiting for the user’s guess to be received via the **ReadInt** activity.</span></span> <span data-ttu-id="6daf3-164">这称为共享转换。</span><span class="sxs-lookup"><span data-stu-id="6daf3-164">This is called a shared transition.</span></span> <span data-ttu-id="6daf3-165">若要创建共享转换，请单击指示**推测正确**转换开始的圆圈，然后将其拖到所需状态。</span><span class="sxs-lookup"><span data-stu-id="6daf3-165">To create a shared transition, click the circle that indicates the start of the **Guess Correct** transition and drag it to the desired state.</span></span> <span data-ttu-id="6daf3-166">在这种情况下，转换是一种自转换，因此拖动**推测正确**转换的开始点，并将其放回**Enter 推测**状态的底部。</span><span class="sxs-lookup"><span data-stu-id="6daf3-166">In this case the transition is a self-transition, so drag the start point of the **Guess Correct** transition and drop it back onto the bottom of the **Enter Guess** state.</span></span> <span data-ttu-id="6daf3-167">创建转换后，在工作流设计器中选择该转换，并将其**DisplayName**属性设置为 "**猜测错误**"。</span><span class="sxs-lookup"><span data-stu-id="6daf3-167">After creating the transition, select it in the workflow designer and set its **DisplayName** property to **Guess Incorrect**.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="6daf3-168">还可以从转换设计器中创建共享的转换，方法是单击 "转换设计器" 底部的 "**添加共享触发器转换**"，然后从 "**可用状态到连接**" 下拉选择所需的目标状态。</span><span class="sxs-lookup"><span data-stu-id="6daf3-168">Shared transitions can also be created from within the transition designer by clicking **Add shared trigger transition** at the bottom of the transition designer, and then selecting the desired target state from the **Available states to connect** drop-down.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="6daf3-169">注意，如果转换的 <xref:System.Activities.Statements.Transition.Condition%2A> 计算结果为 `false`（或所有共享触发转换条件的计算结果均为 `false`），转换将不发生，并且此状态下的所有转换的所有触发将被重新计划。</span><span class="sxs-lookup"><span data-stu-id="6daf3-169">Note that if the <xref:System.Activities.Statements.Transition.Condition%2A> of a transition evaluates to `false` (or all of the conditions of a shared trigger transition evaluate to `false`), the transition will not occur and all triggers for all the transitions from the state will be rescheduled.</span></span> <span data-ttu-id="6daf3-170">在本教程中，由于配置条件的方式，这种情况不会发生（我们针对猜测是正确或者错误提供了具体的操作）。</span><span class="sxs-lookup"><span data-stu-id="6daf3-170">In this tutorial, this situation cannot happen because of the way the conditions are configured (we have specific actions for whether the guess is correct or incorrect).</span></span>  
  
20. <span data-ttu-id="6daf3-171">在工作流设计器中双击**推测错误**的转换，以将其展开。</span><span class="sxs-lookup"><span data-stu-id="6daf3-171">Double-click the **Guess Incorrect** transition in the workflow designer to expand it.</span></span> <span data-ttu-id="6daf3-172">请注意，**触发器**已设置为**推测正确**转换使用的相同**ReadInt**活动。</span><span class="sxs-lookup"><span data-stu-id="6daf3-172">Note that the **Trigger** is already set to the same **ReadInt** activity that was used by the **Guess Correct** transition.</span></span>  
  
21. <span data-ttu-id="6daf3-173">在 " **Condition** " 属性值框中键入以下表达式。</span><span class="sxs-lookup"><span data-stu-id="6daf3-173">Type the following expression into the **Condition** property value box.</span></span>  
  
    ```vb  
    Guess <> Target  
    ```  
  
    ```csharp  
    Guess != Target  
    ```  
  
22. <span data-ttu-id="6daf3-174">将 " **If** " 活动从 "**工具箱**" 的 "**控制流**" 部分拖放到转换的 "**操作**" 部分。</span><span class="sxs-lookup"><span data-stu-id="6daf3-174">Drag an **If** activity from the **Control Flow** section of the **Toolbox** and drop it in the **Action** section of the transition.</span></span>  
  
23. <span data-ttu-id="6daf3-175">在**If**活动的**Condition**属性值框中键入以下表达式。</span><span class="sxs-lookup"><span data-stu-id="6daf3-175">Type the following expression into the **If** activity’s **Condition** property value box.</span></span>  
  
    ```text
    Guess < Target
    ```  
  
24. <span data-ttu-id="6daf3-176">将两个 " **WriteLine** " 活动从 "**工具箱**" 的 "**基元**" 部分拖放到 " **If** " 活动的 " **Then** " 部分，另一个处于 " **Else** " 部分。</span><span class="sxs-lookup"><span data-stu-id="6daf3-176">Drag two **WriteLine** activities from the **Primitives** section of the **Toolbox** and drop them so that one is in the **Then** section of the **If** activity, and one is in the **Else** section.</span></span>  
  
25. <span data-ttu-id="6daf3-177">单击 " **Then** " 部分中的 " **WriteLine** " 活动将其选中，然后在 "**文本**属性值" 框中键入以下表达式。</span><span class="sxs-lookup"><span data-stu-id="6daf3-177">Click the **WriteLine** activity in the **Then** section to select it, and type the following expression into the **Text** property value box.</span></span>  
  
    ```text
    "Your guess is too low."  
    ```  
  
26. <span data-ttu-id="6daf3-178">单击 " **Else** " 部分中的 " **WriteLine** " 活动将其选中，然后在 "**文本**属性值" 框中键入以下表达式。</span><span class="sxs-lookup"><span data-stu-id="6daf3-178">Click the **WriteLine** activity in the **Else** section to select it, and type the following expression into the **Text** property value box.</span></span>  
  
    ```text
    "Your guess is too high."  
    ```  
  
27. <span data-ttu-id="6daf3-179">通过单击工作流设计器顶部显示的痕迹导航中的 "状态机"，返回到工作流设计**器中的**"总体状态机" 视图。</span><span class="sxs-lookup"><span data-stu-id="6daf3-179">Return to the overall state machine view in the workflow designer by clicking **StateMachine** in the breadcrumb display at the top of the workflow designer.</span></span>  
  
     <span data-ttu-id="6daf3-180">下面的示例阐释已完成的工作流。</span><span class="sxs-lookup"><span data-stu-id="6daf3-180">The following example illustrates the completed workflow.</span></span>  
  
     ![显示已完成状态机工作流的插图。](./media/how-to-create-a-state-machine-workflow/complete-state-machine-workflow.jpg)  
  
### <a name="to-build-the-workflow"></a><span data-ttu-id="6daf3-182">生成工作流</span><span class="sxs-lookup"><span data-stu-id="6daf3-182">To build the workflow</span></span>  
  
1. <span data-ttu-id="6daf3-183">按 CTRL+SHIFT+B 生成解决方案。</span><span class="sxs-lookup"><span data-stu-id="6daf3-183">Press CTRL+SHIFT+B to build the solution.</span></span>  
  
     <span data-ttu-id="6daf3-184">有关如何运行工作流的说明，请参阅下一主题[如何：运行工作流](how-to-run-a-workflow.md)。</span><span class="sxs-lookup"><span data-stu-id="6daf3-184">For instructions on how to run the workflow, please see the next topic, [How to: Run a Workflow](how-to-run-a-workflow.md).</span></span> <span data-ttu-id="6daf3-185">如果你已经完成了如何：使用不同的工作流样式[运行工作流](how-to-run-a-workflow.md)步骤，并希望使用此步骤中的状态机工作流运行它，请跳到[如何：运行工作流](how-to-run-a-workflow.md)的 "[生成并运行应用程序](how-to-run-a-workflow.md#BKMK_ToRunTheApplication)" 部分。</span><span class="sxs-lookup"><span data-stu-id="6daf3-185">If you have already completed the [How to: Run a Workflow](how-to-run-a-workflow.md) step with a different style of workflow and wish to run it using the state machine workflow from this step, skip ahead to the [To build and run the application](how-to-run-a-workflow.md#BKMK_ToRunTheApplication) section of [How to: Run a Workflow](how-to-run-a-workflow.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6daf3-186">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6daf3-186">See also</span></span>

- <xref:System.Activities.Statements.Flowchart>
- <xref:System.Activities.Statements.FlowDecision>
- [<span data-ttu-id="6daf3-187">Windows Workflow Foundation 编程</span><span class="sxs-lookup"><span data-stu-id="6daf3-187">Windows Workflow Foundation Programming</span></span>](programming.md)
- [<span data-ttu-id="6daf3-188">设计工作流</span><span class="sxs-lookup"><span data-stu-id="6daf3-188">Designing Workflows</span></span>](designing-workflows.md)
- [<span data-ttu-id="6daf3-189">入门教程</span><span class="sxs-lookup"><span data-stu-id="6daf3-189">Getting Started Tutorial</span></span>](getting-started-tutorial.md)
- [<span data-ttu-id="6daf3-190">如何：创建活动</span><span class="sxs-lookup"><span data-stu-id="6daf3-190">How to: Create an Activity</span></span>](how-to-create-an-activity.md)
- [<span data-ttu-id="6daf3-191">如何：运行工作流</span><span class="sxs-lookup"><span data-stu-id="6daf3-191">How to: Run a Workflow</span></span>](how-to-run-a-workflow.md)
