---
title: 如何：创建顺序工作流
description: 本文将创建一个工作流，该工作流使用内置活动，如 Sequence 活动和自定义活动。
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 5280e816-ae17-48c4-8de0-a1e6895dd8f0
ms.openlocfilehash: f80ac471fdcc425504b11b5fb17effa888aa9590
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/15/2020
ms.locfileid: "83419689"
---
# <a name="how-to-create-a-sequential-workflow"></a><span data-ttu-id="58bf2-103">如何：创建顺序工作流</span><span class="sxs-lookup"><span data-stu-id="58bf2-103">How to: Create a Sequential Workflow</span></span>

<span data-ttu-id="58bf2-104">工作流可基于内置活动以及自定义活动来构造。</span><span class="sxs-lookup"><span data-stu-id="58bf2-104">Workflows can be constructed from built-in activities as well as from custom activities.</span></span> <span data-ttu-id="58bf2-105">本主题介绍如何创建一个工作流，该工作流使用内置活动（如 <xref:System.Activities.Statements.Sequence> 活动）和前面的[如何：创建活动](how-to-create-an-activity.md)主题中的自定义活动。</span><span class="sxs-lookup"><span data-stu-id="58bf2-105">This topic steps through creating a workflow that uses both built-in activities such as the <xref:System.Activities.Statements.Sequence> activity, and the custom activities from the previous [How to: Create an Activity](how-to-create-an-activity.md) topic.</span></span> <span data-ttu-id="58bf2-106">该工作流模拟猜数游戏。</span><span class="sxs-lookup"><span data-stu-id="58bf2-106">The workflow models a number guessing game.</span></span>

> [!NOTE]
> <span data-ttu-id="58bf2-107">入门教程中的每个主题都依赖于前面的主题。</span><span class="sxs-lookup"><span data-stu-id="58bf2-107">Each topic in the Getting Started tutorial depends on the previous topics.</span></span> <span data-ttu-id="58bf2-108">若要完成本主题，必须先完成[操作方法：创建活动](how-to-create-an-activity.md)。</span><span class="sxs-lookup"><span data-stu-id="58bf2-108">To complete this topic, you must first complete [How to: Create an Activity](how-to-create-an-activity.md).</span></span>

> [!NOTE]
> <span data-ttu-id="58bf2-109">若要下载完整版教程，请参阅 [Windows Workflow Foundation (WF45) — 入门教程](https://go.microsoft.com/fwlink/?LinkID=248976)。</span><span class="sxs-lookup"><span data-stu-id="58bf2-109">To download a completed version of the tutorial, see [Windows Workflow Foundation (WF45) - Getting Started Tutorial](https://go.microsoft.com/fwlink/?LinkID=248976).</span></span>

## <a name="to-create-the-workflow"></a><span data-ttu-id="58bf2-110">创建工作流</span><span class="sxs-lookup"><span data-stu-id="58bf2-110">To create the workflow</span></span>

1. <span data-ttu-id="58bf2-111">在**解决方案资源管理器**中右键单击 " **NumberGuessWorkflowActivities** "，然后选择 "**添加**"、"**新建项**"。</span><span class="sxs-lookup"><span data-stu-id="58bf2-111">Right-click **NumberGuessWorkflowActivities** in **Solution Explorer** and select **Add**, **New Item**.</span></span>

2. <span data-ttu-id="58bf2-112">在 "**已安装**的**公共项**" 节点中，选择 "**工作流**"。</span><span class="sxs-lookup"><span data-stu-id="58bf2-112">In the **Installed**, **Common Items** node, select **Workflow**.</span></span> <span data-ttu-id="58bf2-113">从 **“工作流”** 列表中选择 **“活动”**。</span><span class="sxs-lookup"><span data-stu-id="58bf2-113">Select **Activity** from the **Workflow** list.</span></span>

3. <span data-ttu-id="58bf2-114">`SequentialNumberGuessWorkflow`在 "**名称**" 框中键入，然后单击 "**添加**"。</span><span class="sxs-lookup"><span data-stu-id="58bf2-114">Type `SequentialNumberGuessWorkflow` into the **Name** box and click **Add**.</span></span>

4. <span data-ttu-id="58bf2-115">将 "**序列**" 活动从 "**工具箱**" 的 "**控制流**" 部分拖放到工作流设计图面上的 "在**此处放置活动**" 标签上。</span><span class="sxs-lookup"><span data-stu-id="58bf2-115">Drag a **Sequence** activity from the **Control Flow** section of the **Toolbox** and drop it onto the **Drop activity here** label on the workflow design surface.</span></span>

## <a name="to-create-the-workflow-variables-and-arguments"></a><span data-ttu-id="58bf2-116">创建工作流变量和自变量</span><span class="sxs-lookup"><span data-stu-id="58bf2-116">To create the workflow variables and arguments</span></span>

1. <span data-ttu-id="58bf2-117">在**解决方案资源管理器**中双击 " **sequentialnumberguessworkflow.xaml** " 以在设计器中显示工作流（如果尚未显示）。</span><span class="sxs-lookup"><span data-stu-id="58bf2-117">Double-click **SequentialNumberGuessWorkflow.xaml** in **Solution Explorer** to display the workflow in the designer, if it is not already displayed.</span></span>

2. <span data-ttu-id="58bf2-118">单击工作流设计器左下方的 "**参数**" 以显示 "**参数**" 窗格。</span><span class="sxs-lookup"><span data-stu-id="58bf2-118">Click **Arguments** in the lower-left side of the workflow designer to display the **Arguments** pane.</span></span>

3. <span data-ttu-id="58bf2-119">单击 **“创建参数”**。</span><span class="sxs-lookup"><span data-stu-id="58bf2-119">Click **Create Argument**.</span></span>

4. <span data-ttu-id="58bf2-120">在 `MaxNumber` "**名称**" 框中键入，从 "**方向**" 下拉列表**中**选择 "输入"，从 "**参数类型**" 下拉列表中选择 " **Int32** "，然后按 enter 保存该参数。</span><span class="sxs-lookup"><span data-stu-id="58bf2-120">Type `MaxNumber` into the **Name** box, select **In** from the **Direction** drop-down list, select **Int32** from the **Argument type** drop-down list, and then press ENTER to save the argument.</span></span>

5. <span data-ttu-id="58bf2-121">单击 **“创建参数”**。</span><span class="sxs-lookup"><span data-stu-id="58bf2-121">Click **Create Argument**.</span></span>

6. <span data-ttu-id="58bf2-122">在 `Turns` 新添加的参数下方的 "**名称**" 框中键入 `MaxNumber` ，从 "**方向**" 下拉列表中选择 "向**外**"，从 "**参数类型**" 下拉列表中选择 " **Int32** "，然后按 enter。</span><span class="sxs-lookup"><span data-stu-id="58bf2-122">Type `Turns` into the **Name** box that is below the newly added `MaxNumber` argument, select **Out** from the **Direction** drop-down list, select **Int32** from the **Argument type** drop-down list, and then press ENTER.</span></span>

7. <span data-ttu-id="58bf2-123">单击活动设计器左下角的 **“参数”**，关闭 **“参数”** 窗格。</span><span class="sxs-lookup"><span data-stu-id="58bf2-123">Click **Arguments** in the lower-left side of the activity designer to close the **Arguments** pane.</span></span>

8. <span data-ttu-id="58bf2-124">单击工作流设计器左下方的 "**变量**"，以显示 "**变量**" 窗格。</span><span class="sxs-lookup"><span data-stu-id="58bf2-124">Click **Variables** in the lower-left side of the workflow designer to display the **Variables** pane.</span></span>

9. <span data-ttu-id="58bf2-125">单击 **“创建变量”**。</span><span class="sxs-lookup"><span data-stu-id="58bf2-125">Click **Create Variable**.</span></span>

    > [!TIP]
    > <span data-ttu-id="58bf2-126">如果未显示 "**创建变量**" 框，请单击工作流设计器图面上的 "**序列**" 活动将其选中。</span><span class="sxs-lookup"><span data-stu-id="58bf2-126">If no **Create Variable** box is displayed, click the **Sequence** activity on the workflow designer surface to select it.</span></span>

10. <span data-ttu-id="58bf2-127">在 `Guess` "**名称**" 框中键入，从 "**变量类型**" 下拉列表中选择 " **Int32** "，然后按 enter 保存变量。</span><span class="sxs-lookup"><span data-stu-id="58bf2-127">Type `Guess` into the **Name** box, select **Int32** from the **Variable type** drop-down list, and then press ENTER to save the variable.</span></span>

11. <span data-ttu-id="58bf2-128">单击 **“创建变量”**。</span><span class="sxs-lookup"><span data-stu-id="58bf2-128">Click **Create Variable**.</span></span>

12. <span data-ttu-id="58bf2-129">在 `Target` "**名称**" 框中键入，从 "**变量类型**" 下拉列表中选择 " **Int32** "，然后按 enter 保存变量。</span><span class="sxs-lookup"><span data-stu-id="58bf2-129">Type `Target` into the **Name** box, select **Int32** from the **Variable type** drop-down list, and then press ENTER to save the variable.</span></span>

13. <span data-ttu-id="58bf2-130">单击活动设计器左下角的 **“变量”**，关闭 **“变量”** 窗格。</span><span class="sxs-lookup"><span data-stu-id="58bf2-130">Click **Variables** in the lower-left side of the activity designer to close the **Variables** pane.</span></span>

## <a name="to-add-the-workflow-activities"></a><span data-ttu-id="58bf2-131">添加工作流活动</span><span class="sxs-lookup"><span data-stu-id="58bf2-131">To add the workflow activities</span></span>

1. <span data-ttu-id="58bf2-132">将 " **Assign** " 活动从 "**工具箱**" 的 "**基元**" 部分拖放到 " **Sequence** " 活动。</span><span class="sxs-lookup"><span data-stu-id="58bf2-132">Drag an **Assign** activity from the **Primitives** section of the **Toolbox** and drop it onto the **Sequence** activity.</span></span> <span data-ttu-id="58bf2-133">在 " `Target` **到**" 框中键入，然后在 "**输入 c # 表达式**" 或 "**输入 VB 表达式**" 框中键入以下表达式。</span><span class="sxs-lookup"><span data-stu-id="58bf2-133">Type `Target` into the **To** box and the following expression into the **Enter a C# expression** or **Enter a VB expression** box.</span></span>

    ```vb
    New System.Random().Next(1, MaxNumber + 1)
    ```

    ```csharp
    new System.Random().Next(1, MaxNumber + 1)
    ```

    > [!TIP]
    > <span data-ttu-id="58bf2-134">如果未显示 **“工具箱”** 窗口，请从 **“视图”** 菜单中选择 **“工具箱”**。</span><span class="sxs-lookup"><span data-stu-id="58bf2-134">If the **Toolbox** window is not displayed, select **Toolbox** from the **View** menu.</span></span>

2. <span data-ttu-id="58bf2-135">将 " **DoWhile** " 活动从 "**工具箱**" 的 "**控制流**" 部分拖放到工作流上，使其位于 "**分配**" 活动下。</span><span class="sxs-lookup"><span data-stu-id="58bf2-135">Drag a **DoWhile** activity from the **Control Flow** section of the **Toolbox** and drop it on the workflow so that it is below the **Assign** activity.</span></span>

3. <span data-ttu-id="58bf2-136">在 " **DoWhile** " 活动的 " **Condition** " 属性值框中键入以下表达式。</span><span class="sxs-lookup"><span data-stu-id="58bf2-136">Type the following expression into the **DoWhile** activity’s **Condition** property value box.</span></span>

    ```vb
    Guess <> Target
    ```

    ```csharp
    Guess != Target
    ```

     <span data-ttu-id="58bf2-137"><xref:System.Activities.Statements.DoWhile> 活动执行其子活动，然后计算其 <xref:System.Activities.Statements.DoWhile.Condition%2A>。</span><span class="sxs-lookup"><span data-stu-id="58bf2-137">A <xref:System.Activities.Statements.DoWhile> activity executes its child activities and then evaluates its <xref:System.Activities.Statements.DoWhile.Condition%2A>.</span></span> <span data-ttu-id="58bf2-138">如果 <xref:System.Activities.Statements.DoWhile.Condition%2A> 的计算结果为 `True`，则再次执行 <xref:System.Activities.Statements.DoWhile> 中的活动。</span><span class="sxs-lookup"><span data-stu-id="58bf2-138">If the <xref:System.Activities.Statements.DoWhile.Condition%2A> evaluates to `True`, then the activities in the <xref:System.Activities.Statements.DoWhile> execute again.</span></span> <span data-ttu-id="58bf2-139">在此示例中，将计算用户的猜测值，并且 <xref:System.Activities.Statements.DoWhile> 继续执行，直到猜测值正确。</span><span class="sxs-lookup"><span data-stu-id="58bf2-139">In this example, the user’s guess is evaluated and the <xref:System.Activities.Statements.DoWhile> continues until the guess is correct.</span></span>

4. <span data-ttu-id="58bf2-140">从 "**工具箱**" 的 " **NumberGuessWorkflowActivities** " 部分拖动 " **Prompt** " 活动，并将其放入上一步中的 " **DoWhile** " 活动。</span><span class="sxs-lookup"><span data-stu-id="58bf2-140">Drag a **Prompt** activity from the **NumberGuessWorkflowActivities** section of the **Toolbox** and drop it in the **DoWhile** activity from the previous step.</span></span>

5. <span data-ttu-id="58bf2-141">在 "**属性" 窗口**中，在 `"EnterGuess"` **Prompt**活动的 " **BookmarkName** " 属性值框中键入包含引号。</span><span class="sxs-lookup"><span data-stu-id="58bf2-141">In the **Properties Window**, type `"EnterGuess"` including the quotes into the **BookmarkName** property value box for the **Prompt** activity.</span></span> <span data-ttu-id="58bf2-142">`Guess`在 "**结果**属性值" 框中键入，然后在 "**文本**" 属性框中键入以下表达式。</span><span class="sxs-lookup"><span data-stu-id="58bf2-142">Type `Guess` into the **Result** property value box, and type the following expression into the **Text** property box.</span></span>

    ```vb
    "Please enter a number between 1 and " & MaxNumber
    ```

    ```csharp
    "Please enter a number between 1 and " + MaxNumber
    ```

    > [!TIP]
    > <span data-ttu-id="58bf2-143">如果未显示 "**属性" 窗口**，请从 "**视图**" 菜单中选择 "**属性窗口**"。</span><span class="sxs-lookup"><span data-stu-id="58bf2-143">If the **Properties Window** is not displayed, select **Properties Window** from the **View** menu.</span></span>

6. <span data-ttu-id="58bf2-144">将 " **Assign** " 活动从 "**工具箱**" 的 "**基元**" 部分拖放到 " **DoWhile** " 活动中，使其跟随 " **Prompt** " 活动。</span><span class="sxs-lookup"><span data-stu-id="58bf2-144">Drag an **Assign** activity from the **Primitives** section of the **Toolbox** and drop it in the **DoWhile** activity so that it follows the **Prompt** activity.</span></span>

    > [!NOTE]
    > <span data-ttu-id="58bf2-145">删除 "**分配**" 活动时，请注意工作流设计器如何自动添加**序列**活动，以同时包含**Prompt**活动和新添加的 "**分配**" 活动。</span><span class="sxs-lookup"><span data-stu-id="58bf2-145">When you drop the **Assign** activity, note how the workflow designer automatically adds a **Sequence** activity to contain both the **Prompt** activity and the newly added **Assign** activity.</span></span>

7. <span data-ttu-id="58bf2-146">在 `Turns` "**到**" 框中键入，然后 `Turns + 1` 在 "**输入 c # 表达式**" 或 "**输入 VB 表达式**" 框中键入。</span><span class="sxs-lookup"><span data-stu-id="58bf2-146">Type `Turns` into the **To** box and `Turns + 1` into the **Enter a C# expression** or **Enter a VB expression** box.</span></span>

8. <span data-ttu-id="58bf2-147">将 " **If** " 活动从 "工具箱" 的 "**控制流**" 部分拖放到 " **Sequence** " 活动中，使其位于新添加的 **"** **分配**" 活动之后。</span><span class="sxs-lookup"><span data-stu-id="58bf2-147">Drag an **If** activity from the **Control Flow** section of the **Toolbox** and drop it in the **Sequence** activity so that it follows the newly added **Assign** activity.</span></span>

9. <span data-ttu-id="58bf2-148">在**If**活动的**Condition**属性值框中键入以下表达式。</span><span class="sxs-lookup"><span data-stu-id="58bf2-148">Type the following expression into the **If** activity’s **Condition** property value box.</span></span>

    ```vb
    Guess <> Target
    ```

    ```csharp
    Guess != Target
    ```

10. <span data-ttu-id="58bf2-149">从 "**工具箱**" 的 "**控制流**" 部分中，将另一个 " **if** " 活动拖放到第一个 " **if** " 活动的 " **Then** " 部分。</span><span class="sxs-lookup"><span data-stu-id="58bf2-149">Drag another **If** activity from the **Control Flow** section of the **Toolbox** and drop it in the **Then** section of the first **If** activity.</span></span>

11. <span data-ttu-id="58bf2-150">在新添加的**If**活动的**Condition**属性值框中键入以下表达式。</span><span class="sxs-lookup"><span data-stu-id="58bf2-150">Type the following expression into the newly added **If** activity’s **Condition** property value box.</span></span>

    ```text
    Guess < Target
    ```

12. <span data-ttu-id="58bf2-151">从 "**工具箱**" 的 "**基元**" 部分拖放两个 " **WriteLine** " 活动，将其拖放到新添加的 " **If** " 活动的 " **Then** " 部分，另一个位于 " **Else** " 部分。</span><span class="sxs-lookup"><span data-stu-id="58bf2-151">Drag two **WriteLine** activities from the **Primitives** section of the **Toolbox** and drop them so that one is in the **Then** section of the newly added **If** activity, and one is in the **Else** section.</span></span>

13. <span data-ttu-id="58bf2-152">单击 " **Then** " 部分中的 " **WriteLine** " 活动将其选中，然后在 "**文本**属性值" 框中键入以下表达式。</span><span class="sxs-lookup"><span data-stu-id="58bf2-152">Click the **WriteLine** activity in the **Then** section to select it, and type the following expression into the **Text** property value box.</span></span>

    ```text
    "Your guess is too low."
    ```

14. <span data-ttu-id="58bf2-153">单击 " **Else** " 部分中的 " **WriteLine** " 活动将其选中，然后在 "**文本**属性值" 框中键入以下表达式。</span><span class="sxs-lookup"><span data-stu-id="58bf2-153">Click the **WriteLine** activity in the **Else** section to select it, and type the following expression into the **Text** property value box.</span></span>

    ```text
    "Your guess is too high."
    ```

     <span data-ttu-id="58bf2-154">下面的示例演示了已完成的工作流：</span><span class="sxs-lookup"><span data-stu-id="58bf2-154">The following example illustrates the completed workflow:</span></span>

     ![显示已完成的顺序工作流的屏幕截图。](./media/how-to-create-a-sequential-workflow/complete-sequential-workflow.jpg)

## <a name="to-build-the-workflow"></a><span data-ttu-id="58bf2-156">生成工作流</span><span class="sxs-lookup"><span data-stu-id="58bf2-156">To build the workflow</span></span>

1. <span data-ttu-id="58bf2-157">按 CTRL+SHIFT+B 生成解决方案。</span><span class="sxs-lookup"><span data-stu-id="58bf2-157">Press CTRL+SHIFT+B to build the solution.</span></span>

     <span data-ttu-id="58bf2-158">有关如何运行工作流的说明，请参阅下一主题[如何：运行工作流](how-to-run-a-workflow.md)。</span><span class="sxs-lookup"><span data-stu-id="58bf2-158">For instructions on how to run the workflow, please see the next topic, [How to: Run a Workflow](how-to-run-a-workflow.md).</span></span> <span data-ttu-id="58bf2-159">如果你已经完成了如何：使用不同的工作流样式[运行工作流](how-to-run-a-workflow.md)步骤，并希望使用此步骤中的顺序工作流运行它，请跳到[如何：运行工作流](how-to-run-a-workflow.md)的 "[生成并运行应用程序](how-to-run-a-workflow.md#BKMK_ToRunTheApplication)" 部分。</span><span class="sxs-lookup"><span data-stu-id="58bf2-159">If you have already completed the [How to: Run a Workflow](how-to-run-a-workflow.md) step with a different style of workflow and wish to run it using the sequential workflow from this step, skip ahead to the [To build and run the application](how-to-run-a-workflow.md#BKMK_ToRunTheApplication) section of [How to: Run a Workflow](how-to-run-a-workflow.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="58bf2-160">另请参阅</span><span class="sxs-lookup"><span data-stu-id="58bf2-160">See also</span></span>

- <xref:System.Activities.Statements.Flowchart>
- <xref:System.Activities.Statements.FlowDecision>
- [<span data-ttu-id="58bf2-161">Windows Workflow Foundation 编程</span><span class="sxs-lookup"><span data-stu-id="58bf2-161">Windows Workflow Foundation Programming</span></span>](programming.md)
- [<span data-ttu-id="58bf2-162">设计工作流</span><span class="sxs-lookup"><span data-stu-id="58bf2-162">Designing Workflows</span></span>](designing-workflows.md)
- [<span data-ttu-id="58bf2-163">入门教程</span><span class="sxs-lookup"><span data-stu-id="58bf2-163">Getting Started Tutorial</span></span>](getting-started-tutorial.md)
- [<span data-ttu-id="58bf2-164">如何：创建活动</span><span class="sxs-lookup"><span data-stu-id="58bf2-164">How to: Create an Activity</span></span>](how-to-create-an-activity.md)
- [<span data-ttu-id="58bf2-165">如何：运行工作流</span><span class="sxs-lookup"><span data-stu-id="58bf2-165">How to: Run a Workflow</span></span>](how-to-run-a-workflow.md)
