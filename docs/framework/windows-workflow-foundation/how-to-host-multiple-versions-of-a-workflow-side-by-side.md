---
title: "如何：并行承载多个版本的工作流"
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
ms.assetid: 09c575df-e0a3-4f3b-9e01-a7ac59d65287
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 96ae4d3e02b923187b3e0f88a7b18e84094fa584
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-host-multiple-versions-of-a-workflow-side-by-side"></a><span data-ttu-id="46892-102">如何：并行承载多个版本的工作流</span><span class="sxs-lookup"><span data-stu-id="46892-102">How to: Host Multiple Versions of a Workflow Side-by-Side</span></span>
<span data-ttu-id="46892-103">`WorkflowIdentity` 为工作流应用程序开发人员提供了一种将名称和版本与工作流定义关联的方法，这种方法还可用于将此信息与持久化工作流实例相关联。</span><span class="sxs-lookup"><span data-stu-id="46892-103">`WorkflowIdentity` provides a way for workflow application developers to associate a name and a version with a workflow definition, and for this information to be associated with a persisted workflow instance.</span></span> <span data-ttu-id="46892-104">工作流应用程序开发人员可以使用这些标识信息，为一些情景（如并行执行一个工作流定义的多个版本）提供支持，并为其他功能（如动态更新）提供基础。</span><span class="sxs-lookup"><span data-stu-id="46892-104">This identity information can be used by workflow application developers to enable scenarios such as side-by-side execution of multiple versions of a workflow definition, and provides the cornerstone for other functionality such as dynamic update.</span></span> <span data-ttu-id="46892-105">该教程中的此步骤演示了如何使用 `WorkflowIdentity` 来同时承载多个版本的工作流。</span><span class="sxs-lookup"><span data-stu-id="46892-105">This step in the tutorial demonstrates how to use `WorkflowIdentity` to host multiple versions of a workflow at the same time.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="46892-106">若要下载完整的版本或观看教程视频演练，请参阅[Windows Workflow Foundation (WF45)-入门教程](http://go.microsoft.com/fwlink/?LinkID=248976)。</span><span class="sxs-lookup"><span data-stu-id="46892-106">To download a completed version or view a video walkthrough of the tutorial, see [Windows Workflow Foundation (WF45) - Getting Started Tutorial](http://go.microsoft.com/fwlink/?LinkID=248976).</span></span>  
  
## <a name="in-this-topic"></a><span data-ttu-id="46892-107">在本主题中</span><span class="sxs-lookup"><span data-stu-id="46892-107">In this topic</span></span>  
 <span data-ttu-id="46892-108">在该教程的此步骤中，工作流中的 `WriteLine` 活动已得到修改以提供其他信息，并且添加了一个新的 `WriteLine` 活动。</span><span class="sxs-lookup"><span data-stu-id="46892-108">In this step of the tutorial, the `WriteLine` activities in the workflow are modified to provide additional information, and a new `WriteLine` activity is added.</span></span> <span data-ttu-id="46892-109">将存储原始工作流程序集的副本，并更新主机应用程序以便其可同时在原始工作流和更新后的工作流中运行。</span><span class="sxs-lookup"><span data-stu-id="46892-109">A copy of the original workflow assembly is stored, and the host application is updated so that it can run both the original and the updated workflows at the same time.</span></span>  
  
-   [<span data-ttu-id="46892-110">要制作 NumberGuessWorkflowActivities 项目的副本</span><span class="sxs-lookup"><span data-stu-id="46892-110">To make a copy of the NumberGuessWorkflowActivities project</span></span>](../../../docs/framework/windows-workflow-foundation/how-to-host-multiple-versions-of-a-workflow-side-by-side.md#BKMK_BackupCopy)  
  
-   [<span data-ttu-id="46892-111">更新工作流</span><span class="sxs-lookup"><span data-stu-id="46892-111">To update the workflows</span></span>](../../../docs/framework/windows-workflow-foundation/how-to-host-multiple-versions-of-a-workflow-side-by-side.md#BKMK_UpdateWorkflows)  
  
    -   [<span data-ttu-id="46892-112">更新 StateMachine 工作流</span><span class="sxs-lookup"><span data-stu-id="46892-112">To update the StateMachine workflow</span></span>](../../../docs/framework/windows-workflow-foundation/how-to-host-multiple-versions-of-a-workflow-side-by-side.md#BKMK_UpdateStateMachine)  
  
    -   [<span data-ttu-id="46892-113">若要更新的流程图工作流</span><span class="sxs-lookup"><span data-stu-id="46892-113">To update the Flowchart workflow</span></span>](../../../docs/framework/windows-workflow-foundation/how-to-host-multiple-versions-of-a-workflow-side-by-side.md#BKMK_UpdateFlowchart)  
  
    -   [<span data-ttu-id="46892-114">若要更新的顺序工作流</span><span class="sxs-lookup"><span data-stu-id="46892-114">To update the Sequential workflow</span></span>](../../../docs/framework/windows-workflow-foundation/how-to-host-multiple-versions-of-a-workflow-side-by-side.md#BKMK_UpdateSequential)  
  
-   [<span data-ttu-id="46892-115">若要更新 WorkflowVersionMap 以包括以前的工作流版本</span><span class="sxs-lookup"><span data-stu-id="46892-115">To update WorkflowVersionMap to include the previous workflow versions</span></span>](../../../docs/framework/windows-workflow-foundation/how-to-host-multiple-versions-of-a-workflow-side-by-side.md#BKMK_UpdateWorkflowVersionMap)  
  
-   [<span data-ttu-id="46892-116">若要生成并运行应用程序</span><span class="sxs-lookup"><span data-stu-id="46892-116">To build and run the application</span></span>](../../../docs/framework/windows-workflow-foundation/how-to-host-multiple-versions-of-a-workflow-side-by-side.md#BKMK_BuildAndRun)  
  
> [!NOTE]
>  <span data-ttu-id="46892-117">在执行本主题中的步骤之前，请运行该应用程序，启动每个类型的多个工作流，并针对每个工作流进行一个或两个猜测。</span><span class="sxs-lookup"><span data-stu-id="46892-117">Before following the steps in this topic, run the application, start several workflows of each type, and making one or two guesses for each one.</span></span> <span data-ttu-id="46892-118">这些持久化工作流中此步骤和下面的步骤中所用[如何： 更新运行的工作流实例的定义](../../../docs/framework/windows-workflow-foundation/how-to-update-the-definition-of-a-running-workflow-instance.md)。</span><span class="sxs-lookup"><span data-stu-id="46892-118">These persisted workflows are used in this step and the following step, [How to: Update the Definition of a Running Workflow Instance](../../../docs/framework/windows-workflow-foundation/how-to-update-the-definition-of-a-running-workflow-instance.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="46892-119">入门教程中的每个步骤都依赖于前面的步骤。</span><span class="sxs-lookup"><span data-stu-id="46892-119">Each step in the Getting Started tutorial depends on the previous steps.</span></span> <span data-ttu-id="46892-120">如果未完成前面的步骤可以下载从本教程的完整的版本[Windows Workflow Foundation (WF45)-入门教程](http://go.microsoft.com/fwlink/?LinkID=248976)。</span><span class="sxs-lookup"><span data-stu-id="46892-120">If you did not complete the previous steps you can download a completed version of the tutorial from [Windows Workflow Foundation (WF45) - Getting Started Tutorial](http://go.microsoft.com/fwlink/?LinkID=248976).</span></span>  
  
###  <a name="BKMK_BackupCopy"></a><span data-ttu-id="46892-121">要制作 NumberGuessWorkflowActivities 项目的副本</span><span class="sxs-lookup"><span data-stu-id="46892-121">To make a copy of the NumberGuessWorkflowActivities project</span></span>  
  
1.  <span data-ttu-id="46892-122">打开**WF45GettingStartedTutorial**中的解决方案[!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)]如果未打开。</span><span class="sxs-lookup"><span data-stu-id="46892-122">Open the **WF45GettingStartedTutorial** solution in [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)] if it is not open.</span></span>  
  
2.  <span data-ttu-id="46892-123">按 Ctrl+Shift+B 生成解决方案。</span><span class="sxs-lookup"><span data-stu-id="46892-123">Press CTRL+SHIFT+B to build the solution.</span></span>  
  
3.  <span data-ttu-id="46892-124">关闭**WF45GettingStartedTutorial**解决方案。</span><span class="sxs-lookup"><span data-stu-id="46892-124">Close the **WF45GettingStartedTutorial** solution.</span></span>  
  
4.  <span data-ttu-id="46892-125">打开 Windows 资源管理器并定位到该教程解决方案文件和项目文件夹所在的文件夹。</span><span class="sxs-lookup"><span data-stu-id="46892-125">Open Windows Explorer and navigate to the folder where the tutorial solution file and the project folders are located.</span></span>  
  
5.  <span data-ttu-id="46892-126">创建一个名为的新文件夹**PreviousVersions**在所在的文件夹**NumberGuessWorkflowHost**和**NumberGuessWorkflowActivities**。</span><span class="sxs-lookup"><span data-stu-id="46892-126">Create a new folder named **PreviousVersions** in the same folder as **NumberGuessWorkflowHost** and **NumberGuessWorkflowActivities**.</span></span> <span data-ttu-id="46892-127">此文件夹用于放置包含在后续教程步骤中使用的不同版本工作流的程序集。</span><span class="sxs-lookup"><span data-stu-id="46892-127">This folder is used to contain the assemblies that contain the different versions of the workflows used in the subsequent tutorial steps.</span></span>  
  
6.  <span data-ttu-id="46892-128">导航到**NumberGuessWorkflowActivities\bin\debug**文件夹 (或**bin\release**具体取决于项目设置)。</span><span class="sxs-lookup"><span data-stu-id="46892-128">Navigate to the **NumberGuessWorkflowActivities\bin\debug** folder (or **bin\release** depending on your project settings).</span></span> <span data-ttu-id="46892-129">复制**NumberGuessWorkflowActivities.dll**将其粘贴到**PreviousVersions**文件夹。</span><span class="sxs-lookup"><span data-stu-id="46892-129">Copy **NumberGuessWorkflowActivities.dll** and paste it into the **PreviousVersions** folder.</span></span>  
  
7.  <span data-ttu-id="46892-130">重命名**NumberGuessWorkflowActivities.dll**中**PreviousVersions**文件夹**NumberGuessWorkflowActivities_v1.dll**。</span><span class="sxs-lookup"><span data-stu-id="46892-130">Rename **NumberGuessWorkflowActivities.dll** in the **PreviousVersions** folder to **NumberGuessWorkflowActivities_v1.dll**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="46892-131">本主题中的步骤演示了一种对用于包含多个版本的工作流的程序集进行管理的方法。</span><span class="sxs-lookup"><span data-stu-id="46892-131">The steps in this topic demonstrate one way to manage the assemblies used to contain multiple versions of the workflows.</span></span> <span data-ttu-id="46892-132">也可以使用其他方法，例如，对程序集进行强命名，并在全局程序集缓冲中注册这些程序集。</span><span class="sxs-lookup"><span data-stu-id="46892-132">Other methods such as strong naming the assemblies and registering them in the global assembly cache could also be used.</span></span>  
  
8.  <span data-ttu-id="46892-133">创建一个名为的新文件夹**NumberGuessWorkflowActivities_du**在所在的文件夹**NumberGuessWorkflowHost**， **NumberGuessWorkflowActivities**，与新添加**PreviousVersions**文件夹，并将所有文件和子文件夹中的复制**NumberGuessWorkflowActivities**文件夹导入到新**NumberGuessWorkflowActivities_du**文件夹。</span><span class="sxs-lookup"><span data-stu-id="46892-133">Create a new folder named **NumberGuessWorkflowActivities_du** in the same folder as **NumberGuessWorkflowHost**, **NumberGuessWorkflowActivities**, and the newly added **PreviousVersions** folder, and copy all of the files and subfolders from the **NumberGuessWorkflowActivities** folder into the new **NumberGuessWorkflowActivities_du** folder.</span></span> <span data-ttu-id="46892-134">在中使用此活动的初始版本的项目的备份副本[如何： 更新运行的工作流实例的定义](../../../docs/framework/windows-workflow-foundation/how-to-update-the-definition-of-a-running-workflow-instance.md)。</span><span class="sxs-lookup"><span data-stu-id="46892-134">This backup copy of the project for the initial version of the activities is used in [How to: Update the Definition of a Running Workflow Instance](../../../docs/framework/windows-workflow-foundation/how-to-update-the-definition-of-a-running-workflow-instance.md).</span></span>  
  
9. <span data-ttu-id="46892-135">重新打开**WF45GettingStartedTutorial**中的解决方案[!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="46892-135">Re-open the **WF45GettingStartedTutorial** solution in [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)].</span></span>  
  
###  <a name="BKMK_UpdateWorkflows"></a><span data-ttu-id="46892-136">更新工作流</span><span class="sxs-lookup"><span data-stu-id="46892-136">To update the workflows</span></span>  
 <span data-ttu-id="46892-137">在本节中，将会更新工作流定义。</span><span class="sxs-lookup"><span data-stu-id="46892-137">In this section, the workflow definitions are updated.</span></span> <span data-ttu-id="46892-138">将会更新针对用户猜测提供反馈的两个 `WriteLine` 活动，并添加一个新的 `WriteLine` 活动，此活动提供猜测了数字之后有关该游戏的其他信息。</span><span class="sxs-lookup"><span data-stu-id="46892-138">The two `WriteLine` activities that give feedback on the user's guess are updated, and a new `WriteLine` activity is added that provides additional information about the game once the number is guessed.</span></span>  
  
####  <a name="BKMK_UpdateStateMachine"></a><span data-ttu-id="46892-139">更新 StateMachine 工作流</span><span class="sxs-lookup"><span data-stu-id="46892-139">To update the StateMachine workflow</span></span>  
  
1.  <span data-ttu-id="46892-140">在**解决方案资源管理器**下**NumberGuessWorkflowActivities**项目中，双击**StateMachineNumberGuessWorkflow.xaml**。</span><span class="sxs-lookup"><span data-stu-id="46892-140">In **Solution Explorer**, under the **NumberGuessWorkflowActivities** project, double-click **StateMachineNumberGuessWorkflow.xaml**.</span></span>  
  
2.  <span data-ttu-id="46892-141">双击**Guess Incorrect**状态机上的转换。</span><span class="sxs-lookup"><span data-stu-id="46892-141">Double-click the **Guess Incorrect** transition on the state machine.</span></span>  
  
3.  <span data-ttu-id="46892-142">更新 `Text` 活动中最左侧 `WriteLine` 的 `If`。</span><span class="sxs-lookup"><span data-stu-id="46892-142">Update the `Text` of the left-most `WriteLine` in the `If` activity.</span></span>  
  
    ```vb  
    Guess & " is too low."  
    ```  
  
    ```csharp  
    Guess + " is too low."  
    ```  
  
4.  <span data-ttu-id="46892-143">更新 `Text` 活动中最右侧 `WriteLine` 的 `If`。</span><span class="sxs-lookup"><span data-stu-id="46892-143">Update the `Text` of the right-most `WriteLine` in the `If` activity.</span></span>  
  
    ```vb  
    Guess & " is too high."  
    ```  
  
    ```csharp  
    Guess + " is too high."  
    ```  
  
5.  <span data-ttu-id="46892-144">返回对整体状态机工作流设计器中的视图，通过单击**StateMachine**的痕迹显示中的工作流设计器顶部。</span><span class="sxs-lookup"><span data-stu-id="46892-144">Return to the overall state machine view in the workflow designer by clicking **StateMachine** in the breadcrumb display at the top of the workflow designer.</span></span>  
  
6.  <span data-ttu-id="46892-145">双击**Guess Correct**状态机上的转换。</span><span class="sxs-lookup"><span data-stu-id="46892-145">Double-click the **Guess Correct** transition on the state machine.</span></span>  
  
7.  <span data-ttu-id="46892-146">拖动**WriteLine**活动从**基元**部分**工具箱**拖放到**此处放置操作活动**标签转换。</span><span class="sxs-lookup"><span data-stu-id="46892-146">Drag a **WriteLine** activity from the **Primitives** section of the **Toolbox** and drop it on the **Drop Action activity here** label of the transition.</span></span>  
  
8.  <span data-ttu-id="46892-147">在 `Text` 属性框中键入以下表达式。</span><span class="sxs-lookup"><span data-stu-id="46892-147">Type the following expression into the `Text` property box.</span></span>  
  
    ```vb  
    Guess & " is correct. You guessed it in " & Turns & " turns."  
    ```  
  
    ```csharp  
    Guess + " is correct. You guessed it in " + Turns + " turns."  
    ```  
  
####  <a name="BKMK_UpdateFlowchart"></a><span data-ttu-id="46892-148">若要更新的流程图工作流</span><span class="sxs-lookup"><span data-stu-id="46892-148">To update the Flowchart workflow</span></span>  
  
1.  <span data-ttu-id="46892-149">在**解决方案资源管理器**下**NumberGuessWorkflowActivities**项目中，双击**FlowchartNumberGuessWorkflow.xaml**。</span><span class="sxs-lookup"><span data-stu-id="46892-149">In **Solution Explorer**, under the **NumberGuessWorkflowActivities** project, double-click **FlowchartNumberGuessWorkflow.xaml**.</span></span>  
  
2.  <span data-ttu-id="46892-150">更新最左侧 `Text` 活动的 `WriteLine`。</span><span class="sxs-lookup"><span data-stu-id="46892-150">Update the `Text` of the left-most `WriteLine` activity.</span></span>  
  
    ```vb  
    Guess & " is too low."  
    ```  
  
    ```csharp  
    Guess + " is too low."  
    ```  
  
3.  <span data-ttu-id="46892-151">更新最右侧 `Text` 活动的 `WriteLine`。</span><span class="sxs-lookup"><span data-stu-id="46892-151">Update the `Text` of the right-most `WriteLine` activity.</span></span>  
  
    ```vb  
    Guess & " is too high."  
    ```  
  
    ```csharp  
    Guess + " is too high."  
    ```  
  
4.  <span data-ttu-id="46892-152">拖动**WriteLine**活动从**基元**部分**工具箱**然后将其放置的放置点上`True`操作的最顶层`FlowDecision`.</span><span class="sxs-lookup"><span data-stu-id="46892-152">Drag a **WriteLine** activity from the **Primitives** section of the **Toolbox** and drop it on the drop point of the `True` action of the topmost `FlowDecision`.</span></span> <span data-ttu-id="46892-153">`WriteLine` 活动将添加到流程图并链接到 `True` 的 `FlowDecision` 操作。</span><span class="sxs-lookup"><span data-stu-id="46892-153">The `WriteLine` activity is added to the flowchart and linked to the `True` action of the `FlowDecision`.</span></span>  
  
5.  <span data-ttu-id="46892-154">在 `Text` 属性框中键入以下表达式。</span><span class="sxs-lookup"><span data-stu-id="46892-154">Type the following expression into the `Text` property box.</span></span>  
  
    ```vb  
    Guess & " is correct. You guessed it in " & Turns & " turns."  
    ```  
  
    ```csharp  
    Guess + " is correct. You guessed it in " + Turns + " turns."  
    ```  
  
####  <a name="BKMK_UpdateSequential"></a><span data-ttu-id="46892-155">若要更新的顺序工作流</span><span class="sxs-lookup"><span data-stu-id="46892-155">To update the Sequential workflow</span></span>  
  
1.  <span data-ttu-id="46892-156">在**解决方案资源管理器**下**NumberGuessWorkflowActivities**项目中，双击**SequentialNumberGuessWorkflow.xaml**。</span><span class="sxs-lookup"><span data-stu-id="46892-156">In **Solution Explorer**, under the **NumberGuessWorkflowActivities** project, double-click **SequentialNumberGuessWorkflow.xaml**.</span></span>  
  
2.  <span data-ttu-id="46892-157">更新 `Text` 活动中最左侧 `WriteLine` 的 `If`。</span><span class="sxs-lookup"><span data-stu-id="46892-157">Update the `Text` of the left-most `WriteLine` in the `If` activity.</span></span>  
  
    ```vb  
    Guess & " is too low."  
    ```  
  
    ```csharp  
    Guess + " is too low."  
    ```  
  
3.  <span data-ttu-id="46892-158">更新 `Text` 活动中最右侧 `WriteLine` 活动的 `If`。</span><span class="sxs-lookup"><span data-stu-id="46892-158">Update the `Text` of the right-most `WriteLine` activity in the `If` activity.</span></span>  
  
    ```vb  
    Guess & " is too high."  
    ```  
  
    ```csharp  
    Guess + " is too high."  
    ```  
  
4.  <span data-ttu-id="46892-159">拖动**WriteLine**活动从**基元**部分**工具箱**和将其放置**DoWhile**活动以便**WriteLine**是根目录中的最后一个活动`Sequence`活动。</span><span class="sxs-lookup"><span data-stu-id="46892-159">Drag a **WriteLine** activity from the **Primitives** section of the **Toolbox** and drop it after the **DoWhile** activity so that the **WriteLine** is the final activity in the root `Sequence` activity.</span></span>  
  
5.  <span data-ttu-id="46892-160">在 `Text` 属性框中键入以下表达式。</span><span class="sxs-lookup"><span data-stu-id="46892-160">Type the following expression into the `Text` property box.</span></span>  
  
    ```vb  
    Guess & " is correct. You guessed it in " & Turns & " turns."  
    ```  
  
    ```csharp  
    Guess + " is correct. You guessed it in " + Turns + " turns."  
    ```  
  
###  <a name="BKMK_UpdateWorkflowVersionMap"></a><span data-ttu-id="46892-161">若要更新 WorkflowVersionMap 以包括以前的工作流版本</span><span class="sxs-lookup"><span data-stu-id="46892-161">To update WorkflowVersionMap to include the previous workflow versions</span></span>  
  
1.  <span data-ttu-id="46892-162">双击**WorkflowVersionMap.cs** (或**WorkflowVersionMap.vb**) 下**NumberGuessWorkflowHost**项目以打开它。</span><span class="sxs-lookup"><span data-stu-id="46892-162">Double-click **WorkflowVersionMap.cs** (or **WorkflowVersionMap.vb**) under the **NumberGuessWorkflowHost** project to open it.</span></span>  
  
2.  <span data-ttu-id="46892-163">向包含其他 `using`（或 `Imports`）语句的文件的顶部添加以下 `using`（或 `Imports`）语句。</span><span class="sxs-lookup"><span data-stu-id="46892-163">Add the following `using` (or `Imports`) statements to the top of the file with the other `using` (or `Imports`) statements.</span></span>  
  
    ```vb  
    Imports System.Reflection  
    Imports System.IO  
    ```  
  
    ```csharp  
    using System.Reflection;  
    using System.IO;  
    ```  
  
3.  <span data-ttu-id="46892-164">紧接在现有的三个工作流标识声明下面添加三个新工作流标识。</span><span class="sxs-lookup"><span data-stu-id="46892-164">Add three new workflow identities just below the three existing workflow identity declarations.</span></span> <span data-ttu-id="46892-165">这些新的 `v1` 工作流标识用于为在进行更新前启动的工作流提供正确的工作流定义。</span><span class="sxs-lookup"><span data-stu-id="46892-165">These new `v1` workflow identities will be used provide the correct workflow definition to workflows started before the updates were made.</span></span>  
  
    ```vb  
    'Current version identities.  
    Public StateMachineNumberGuessIdentity As WorkflowIdentity  
    Public FlowchartNumberGuessIdentity As WorkflowIdentity  
    Public SequentialNumberGuessIdentity As WorkflowIdentity  
  
    'v1 Identities.  
    Public StateMachineNumberGuessIdentity_v1 As WorkflowIdentity  
    Public FlowchartNumberGuessIdentity_v1 As WorkflowIdentity  
    Public SequentialNumberGuessIdentity_v1 As WorkflowIdentity  
    ```  
  
    ```csharp  
    // Current version identities.  
    static public WorkflowIdentity StateMachineNumberGuessIdentity;  
    static public WorkflowIdentity FlowchartNumberGuessIdentity;  
    static public WorkflowIdentity SequentialNumberGuessIdentity;  
  
    // v1 identities.  
    static public WorkflowIdentity StateMachineNumberGuessIdentity_v1;  
    static public WorkflowIdentity FlowchartNumberGuessIdentity_v1;  
    static public WorkflowIdentity SequentialNumberGuessIdentity_v1;  
    ```  
  
4.  <span data-ttu-id="46892-166">在 `WorkflowVersionMap` 构造函数中，将三个当前工作流标识的 `Version` 属性更新为 `2.0.0.0`。</span><span class="sxs-lookup"><span data-stu-id="46892-166">In the `WorkflowVersionMap` constructor, update the `Version` property of the three current workflow identities to `2.0.0.0`.</span></span>  
  
    ```vb  
    'Add the current workflow version identities.  
    StateMachineNumberGuessIdentity = New WorkflowIdentity With  
    {  
        .Name = "StateMachineNumberGuessWorkflow",  
        .Version = New Version(2, 0, 0, 0)  
    }  
  
    FlowchartNumberGuessIdentity = New WorkflowIdentity With  
    {  
        .Name = "FlowchartNumberGuessWorkflow",  
        .Version = New Version(2, 0, 0, 0)  
    }  
  
    SequentialNumberGuessIdentity = New WorkflowIdentity With  
    {  
        .Name = "SequentialNumberGuessWorkflow",  
        .Version = New Version(2, 0, 0, 0)  
    }  
  
    map.Add(StateMachineNumberGuessIdentity, New StateMachineNumberGuessWorkflow())  
    map.Add(FlowchartNumberGuessIdentity, New FlowchartNumberGuessWorkflow())  
    map.Add(SequentialNumberGuessIdentity, New SequentialNumberGuessWorkflow())  
    ```  
  
    ```csharp  
    // Add the current workflow version identities.  
    StateMachineNumberGuessIdentity = new WorkflowIdentity  
    {  
        Name = "StateMachineNumberGuessWorkflow",  
        // Version = new Version(1, 0, 0, 0),  
        Version = new Version(2, 0, 0, 0)  
    };  
  
    FlowchartNumberGuessIdentity = new WorkflowIdentity  
    {  
        Name = "FlowchartNumberGuessWorkflow",  
        // Version = new Version(1, 0, 0, 0),  
        Version = new Version(2, 0, 0, 0)  
    };  
  
    SequentialNumberGuessIdentity = new WorkflowIdentity  
    {  
        Name = "SequentialNumberGuessWorkflow",  
        // Version = new Version(1, 0, 0, 0),  
        Version = new Version(2, 0, 0, 0)  
    };  
  
    map.Add(StateMachineNumberGuessIdentity, new StateMachineNumberGuessWorkflow());  
    map.Add(FlowchartNumberGuessIdentity, new FlowchartNumberGuessWorkflow());  
    map.Add(SequentialNumberGuessIdentity, new SequentialNumberGuessWorkflow());  
    ```  
  
     <span data-ttu-id="46892-167">向字典添加当前版本的工作流的代码使用项目中引用的当前版本，因此，无需对初始化工作流定义的代码进行更新。</span><span class="sxs-lookup"><span data-stu-id="46892-167">The code in that adds the current versions of the workflows to the dictionary uses the current versions that are referenced in the project, so the code that initializes the workflow definitions does not need to be updated.</span></span>  
  
5.  <span data-ttu-id="46892-168">紧接在向字典添加当前版本的代码的后面添加以下代码。</span><span class="sxs-lookup"><span data-stu-id="46892-168">Add the following code in the constructor just after the code that adds the current versions to the dictionary.</span></span>  
  
    ```vb  
    'Initialize the previous workflow version identities.  
    StateMachineNumberGuessIdentity_v1 = New WorkflowIdentity With  
    {  
        .Name = "StateMachineNumberGuessWorkflow",  
        .Version = New Version(1, 0, 0, 0)  
    }  
  
    FlowchartNumberGuessIdentity_v1 = New WorkflowIdentity With  
    {  
        .Name = "FlowchartNumberGuessWorkflow",  
        .Version = New Version(1, 0, 0, 0)  
    }  
  
    SequentialNumberGuessIdentity_v1 = New WorkflowIdentity With  
    {  
        .Name = "SequentialNumberGuessWorkflow",  
        .Version = New Version(1, 0, 0, 0)  
    }  
    ```  
  
    ```csharp  
    // Initialize the previous workflow version identities.  
    StateMachineNumberGuessIdentity_v1 = new WorkflowIdentity  
    {  
        Name = "StateMachineNumberGuessWorkflow",  
        Version = new Version(1, 0, 0, 0)  
    };  
  
    FlowchartNumberGuessIdentity_v1 = new WorkflowIdentity  
    {  
        Name = "FlowchartNumberGuessWorkflow",  
        Version = new Version(1, 0, 0, 0)  
    };  
  
    SequentialNumberGuessIdentity_v1 = new WorkflowIdentity  
    {  
        Name = "SequentialNumberGuessWorkflow",  
        Version = new Version(1, 0, 0, 0)  
    };  
    ```  
  
     <span data-ttu-id="46892-169">这些工作流标识与相应工作流定义的初始版本相关联。</span><span class="sxs-lookup"><span data-stu-id="46892-169">These workflow identities are associated with the initial versions of the corresponding workflow definitions.</span></span>  
  
6.  <span data-ttu-id="46892-170">接下来，加载包含初始版本的工作流定义的程序集，然后创建相应工作流定义，并将这些定义添加到字典。</span><span class="sxs-lookup"><span data-stu-id="46892-170">Next, load the assembly that contains the initial version of the workflow definitions, and create and add the corresponding workflow definitions to the dictionary.</span></span>  
  
    ```vb  
    'Add the previous version workflow identities to the dictionary along with  
    'the corresponding workflow definitions loaded from the v1 assembly.  
    'Assembly.LoadFile requires an absolute path so convert this relative path  
    'to an absolute path.  
    Dim v1AssemblyPath As String = "..\..\..\PreviousVersions\NumberGuessWorkflowActivities_v1.dll"  
    v1AssemblyPath = Path.GetFullPath(v1AssemblyPath)  
    Dim v1Assembly As Assembly = Assembly.LoadFile(v1AssemblyPath)  
  
    map.Add(StateMachineNumberGuessIdentity_v1,  
        v1Assembly.CreateInstance("NumberGuessWorkflowActivities.StateMachineNumberGuessWorkflow"))  
  
    map.Add(SequentialNumberGuessIdentity_v1,  
        v1Assembly.CreateInstance("NumberGuessWorkflowActivities.SequentialNumberGuessWorkflow"))  
  
    map.Add(FlowchartNumberGuessIdentity_v1,  
        v1Assembly.CreateInstance("NumberGuessWorkflowActivities.FlowchartNumberGuessWorkflow"))  
    ```  
  
    ```csharp  
    // Add the previous version workflow identities to the dictionary along with  
    // the corresponding workflow definitions loaded from the v1 assembly.  
    // Assembly.LoadFile requires an absolute path so convert this relative path  
    // to an absolute path.  
    string v1AssemblyPath = @"..\..\..\PreviousVersions\NumberGuessWorkflowActivities_v1.dll";  
    v1AssemblyPath = Path.GetFullPath(v1AssemblyPath);  
    Assembly v1Assembly = Assembly.LoadFile(v1AssemblyPath);  
  
    map.Add(StateMachineNumberGuessIdentity_v1,  
        v1Assembly.CreateInstance("NumberGuessWorkflowActivities.StateMachineNumberGuessWorkflow") as Activity);  
  
    map.Add(SequentialNumberGuessIdentity_v1,  
        v1Assembly.CreateInstance("NumberGuessWorkflowActivities.SequentialNumberGuessWorkflow") as Activity);  
  
    map.Add(FlowchartNumberGuessIdentity_v1,  
        v1Assembly.CreateInstance("NumberGuessWorkflowActivities.FlowchartNumberGuessWorkflow") as Activity);  
    ```  
  
     <span data-ttu-id="46892-171">下面的示例完整列出了已更新的 `WorkflowVersionMap` 类。</span><span class="sxs-lookup"><span data-stu-id="46892-171">The following example is the complete listing for the updated `WorkflowVersionMap` class.</span></span>  
  
    ```vb  
    Public Module WorkflowVersionMap  
        Dim map As Dictionary(Of WorkflowIdentity, Activity)  
  
        'Current version identities.  
        Public StateMachineNumberGuessIdentity As WorkflowIdentity  
        Public FlowchartNumberGuessIdentity As WorkflowIdentity  
        Public SequentialNumberGuessIdentity As WorkflowIdentity  
  
        'v1 Identities.  
        Public StateMachineNumberGuessIdentity_v1 As WorkflowIdentity  
        Public FlowchartNumberGuessIdentity_v1 As WorkflowIdentity  
        Public SequentialNumberGuessIdentity_v1 As WorkflowIdentity  
  
        Sub New()  
            map = New Dictionary(Of WorkflowIdentity, Activity)  
  
            'Add the current workflow version identities.  
            StateMachineNumberGuessIdentity = New WorkflowIdentity With  
            {  
                .Name = "StateMachineNumberGuessWorkflow",  
                .Version = New Version(2, 0, 0, 0)  
            }  
  
            FlowchartNumberGuessIdentity = New WorkflowIdentity With  
            {  
                .Name = "FlowchartNumberGuessWorkflow",  
                .Version = New Version(2, 0, 0, 0)  
            }  
  
            SequentialNumberGuessIdentity = New WorkflowIdentity With  
            {  
                .Name = "SequentialNumberGuessWorkflow",  
                .Version = New Version(2, 0, 0, 0)  
            }  
  
            map.Add(StateMachineNumberGuessIdentity, New StateMachineNumberGuessWorkflow())  
            map.Add(FlowchartNumberGuessIdentity, New FlowchartNumberGuessWorkflow())  
            map.Add(SequentialNumberGuessIdentity, New SequentialNumberGuessWorkflow())  
  
            'Initialize the previous workflow version identities.  
            StateMachineNumberGuessIdentity_v1 = New WorkflowIdentity With  
            {  
                .Name = "StateMachineNumberGuessWorkflow",  
                .Version = New Version(1, 0, 0, 0)  
            }  
  
            FlowchartNumberGuessIdentity_v1 = New WorkflowIdentity With  
            {  
                .Name = "FlowchartNumberGuessWorkflow",  
                .Version = New Version(1, 0, 0, 0)  
            }  
  
            SequentialNumberGuessIdentity_v1 = New WorkflowIdentity With  
            {  
                .Name = "SequentialNumberGuessWorkflow",  
                .Version = New Version(1, 0, 0, 0)  
            }  
  
            'Add the previous version workflow identities to the dictionary along with  
            'the corresponding workflow definitions loaded from the v1 assembly.  
            'Assembly.LoadFile requires an absolute path so convert this relative path  
            'to an absolute path.  
            Dim v1AssemblyPath As String = "..\..\..\PreviousVersions\NumberGuessWorkflowActivities_v1.dll"  
            v1AssemblyPath = Path.GetFullPath(v1AssemblyPath)  
            Dim v1Assembly As Assembly = Assembly.LoadFile(v1AssemblyPath)  
  
            map.Add(StateMachineNumberGuessIdentity_v1,  
                v1Assembly.CreateInstance("NumberGuessWorkflowActivities.StateMachineNumberGuessWorkflow"))  
  
            map.Add(SequentialNumberGuessIdentity_v1,  
                v1Assembly.CreateInstance("NumberGuessWorkflowActivities.SequentialNumberGuessWorkflow"))  
  
            map.Add(FlowchartNumberGuessIdentity_v1,  
                v1Assembly.CreateInstance("NumberGuessWorkflowActivities.FlowchartNumberGuessWorkflow"))  
        End Sub  
  
        Public Function GetWorkflowDefinition(identity As WorkflowIdentity) As Activity  
            Return map(identity)  
        End Function  
  
        Public Function GetIdentityDescription(identity As WorkflowIdentity) As String  
            Return identity.ToString()  
        End Function  
    End Module  
    ```  
  
    ```csharp  
    public static class WorkflowVersionMap  
    {  
        static Dictionary<WorkflowIdentity, Activity> map;  
  
        // Current version identities.  
        static public WorkflowIdentity StateMachineNumberGuessIdentity;  
        static public WorkflowIdentity FlowchartNumberGuessIdentity;  
        static public WorkflowIdentity SequentialNumberGuessIdentity;  
  
        // v1 identities.  
        static public WorkflowIdentity StateMachineNumberGuessIdentity_v1;  
        static public WorkflowIdentity FlowchartNumberGuessIdentity_v1;  
        static public WorkflowIdentity SequentialNumberGuessIdentity_v1;  
  
        static WorkflowVersionMap()  
        {  
            map = new Dictionary<WorkflowIdentity, Activity>();  
  
            // Add the current workflow version identities.  
            StateMachineNumberGuessIdentity = new WorkflowIdentity  
            {  
                Name = "StateMachineNumberGuessWorkflow",  
                // Version = new Version(1, 0, 0, 0),  
                Version = new Version(2, 0, 0, 0)  
            };  
  
            FlowchartNumberGuessIdentity = new WorkflowIdentity  
            {  
                Name = "FlowchartNumberGuessWorkflow",  
                // Version = new Version(1, 0, 0, 0),  
                Version = new Version(2, 0, 0, 0)  
            };  
  
            SequentialNumberGuessIdentity = new WorkflowIdentity  
            {  
                Name = "SequentialNumberGuessWorkflow",  
                // Version = new Version(1, 0, 0, 0),  
                Version = new Version(2, 0, 0, 0)  
            };  
  
            map.Add(StateMachineNumberGuessIdentity, new StateMachineNumberGuessWorkflow());  
            map.Add(FlowchartNumberGuessIdentity, new FlowchartNumberGuessWorkflow());  
            map.Add(SequentialNumberGuessIdentity, new SequentialNumberGuessWorkflow());  
  
            // Initialize the previous workflow version identities.  
            StateMachineNumberGuessIdentity_v1 = new WorkflowIdentity  
            {  
                Name = "StateMachineNumberGuessWorkflow",  
                Version = new Version(1, 0, 0, 0)  
            };  
  
            FlowchartNumberGuessIdentity_v1 = new WorkflowIdentity  
            {  
                Name = "FlowchartNumberGuessWorkflow",  
                Version = new Version(1, 0, 0, 0)  
            };  
  
            SequentialNumberGuessIdentity_v1 = new WorkflowIdentity  
            {  
                Name = "SequentialNumberGuessWorkflow",  
                Version = new Version(1, 0, 0, 0)  
            };  
  
            // Add the previous version workflow identities to the dictionary along with  
            // the corresponding workflow definitions loaded from the v1 assembly.  
            // Assembly.LoadFile requires an absolute path so convert this relative path  
            // to an absolute path.  
            string v1AssemblyPath = @"..\..\..\PreviousVersions\NumberGuessWorkflowActivities_v1.dll";  
            v1AssemblyPath = Path.GetFullPath(v1AssemblyPath);  
            Assembly v1Assembly = Assembly.LoadFile(v1AssemblyPath);  
  
            map.Add(StateMachineNumberGuessIdentity_v1,  
                v1Assembly.CreateInstance("NumberGuessWorkflowActivities.StateMachineNumberGuessWorkflow") as Activity);  
  
            map.Add(SequentialNumberGuessIdentity_v1,  
                v1Assembly.CreateInstance("NumberGuessWorkflowActivities.SequentialNumberGuessWorkflow") as Activity);  
  
            map.Add(FlowchartNumberGuessIdentity_v1,  
                v1Assembly.CreateInstance("NumberGuessWorkflowActivities.FlowchartNumberGuessWorkflow") as Activity);  
        }  
  
        public static Activity GetWorkflowDefinition(WorkflowIdentity identity)  
        {  
            return map[identity];  
        }  
  
        public static string GetIdentityDescription(WorkflowIdentity identity)  
        {  
            return identity.ToString();  
        }  
    }  
    ```  
  
###  <a name="BKMK_BuildAndRun"></a><span data-ttu-id="46892-172">若要生成并运行应用程序</span><span class="sxs-lookup"><span data-stu-id="46892-172">To build and run the application</span></span>  
  
1.  <span data-ttu-id="46892-173">按 Ctrl+Shift+B 以生成应用程序，然后按 Ctrl+F5 启动该应用程序。</span><span class="sxs-lookup"><span data-stu-id="46892-173">Press CTRL+SHIFT+B to build the application, and then CTRL+F5 to start.</span></span>  
  
2.  <span data-ttu-id="46892-174">通过单击启动新工作流**新游戏**。</span><span class="sxs-lookup"><span data-stu-id="46892-174">Start a new workflow by clicking **New Game**.</span></span> <span data-ttu-id="46892-175">工作流的版本显示在状态窗口下面，它反映了关联 `WorkflowIdentity` 的更新版本。</span><span class="sxs-lookup"><span data-stu-id="46892-175">The version of the workflow is displayed under the status window and reflects the updated version from the associated `WorkflowIdentity`.</span></span> <span data-ttu-id="46892-176">请记下 `InstanceId`，这样您就可以在工作流完成时查看该工作流的跟踪文件，然后在游戏完成之前输入猜测。</span><span class="sxs-lookup"><span data-stu-id="46892-176">Make a note of the `InstanceId` so you can view the tracking file for the workflow when it completes, and then enter guesses until the game is complete.</span></span> <span data-ttu-id="46892-177">请注意用户猜测基于 `WriteLine` 活动的更新在状态窗口中的信息中显示的方式。</span><span class="sxs-lookup"><span data-stu-id="46892-177">Note how the user's guess is displayed in the information displayed in the status window based on the updates to the `WriteLine` activities.</span></span>  
  
 <span data-ttu-id="46892-178">**请输入介于 1 和 10 之间的数字**</span><span class="sxs-lookup"><span data-stu-id="46892-178">**Please enter a number between 1 and 10**</span></span>  
<span data-ttu-id="46892-179">**5 之过高。** </span><span class="sxs-lookup"><span data-stu-id="46892-179">**5 is too high.** </span></span>  
<span data-ttu-id="46892-180">**请输入介于 1 和 10 之间的数字** </span><span class="sxs-lookup"><span data-stu-id="46892-180">**Please enter a number between 1 and 10** </span></span>  
<span data-ttu-id="46892-181">**3 是过高。** </span><span class="sxs-lookup"><span data-stu-id="46892-181">**3 is too high.** </span></span>  
<span data-ttu-id="46892-182">**请输入介于 1 和 10 之间的数字** </span><span class="sxs-lookup"><span data-stu-id="46892-182">**Please enter a number between 1 and 10** </span></span>  
<span data-ttu-id="46892-183">**1 表示太低。** </span><span class="sxs-lookup"><span data-stu-id="46892-183">**1 is too low.** </span></span>  
<span data-ttu-id="46892-184">**请输入介于 1 和 10 之间的数字** </span><span class="sxs-lookup"><span data-stu-id="46892-184">**Please enter a number between 1 and 10** </span></span>  
<span data-ttu-id="46892-185">**祝贺你，4 轮流猜数。**</span><span class="sxs-lookup"><span data-stu-id="46892-185">**Congratulations, you guessed the number in 4 turns.**</span></span>    
    > [!NOTE]
    >  <span data-ttu-id="46892-186">将显示 `WriteLine` 活动的更新文本，但不显示已在本主题中添加的最终 `WriteLine` 活动的输出。</span><span class="sxs-lookup"><span data-stu-id="46892-186">The updated text from the `WriteLine` activities is displayed, but the output of the final `WriteLine` activity that was added in this topic is not.</span></span> <span data-ttu-id="46892-187">这是因为，此状态窗口将由 `PersistableIdle` 处理程序进行更新。</span><span class="sxs-lookup"><span data-stu-id="46892-187">That is because the status window is updated by the `PersistableIdle` handler.</span></span> <span data-ttu-id="46892-188">由于该工作流在最终活动之后完成且不会转为空闲状态，因此不会调用 `PersistableIdle` 处理程序。</span><span class="sxs-lookup"><span data-stu-id="46892-188">Because the workflow completes and does not go idle after the final activity, the `PersistableIdle` handler is not called.</span></span> <span data-ttu-id="46892-189">但是，`Completed` 处理程序会在状态窗口中显示类似的消息。</span><span class="sxs-lookup"><span data-stu-id="46892-189">However, a similar message is displayed in the status window by the `Completed` handler.</span></span> <span data-ttu-id="46892-190">如果需要，可以向 `Completed` 处理程序添加代码，以便从 `StringWriter` 提取文本并在状态窗口中显示。</span><span class="sxs-lookup"><span data-stu-id="46892-190">If desired, code could be added to the `Completed` handler to extract the text from the `StringWriter` and display it to the status window.</span></span>  
  
3.  <span data-ttu-id="46892-191">打开 Windows 资源管理器并导航到**NumberGuessWorkflowHost\bin\debug**文件夹 (或**bin\release**具体取决于项目设置)，然后打开跟踪文件使用相对应的记事本为完成的工作流。</span><span class="sxs-lookup"><span data-stu-id="46892-191">Open Windows Explorer and navigate to the **NumberGuessWorkflowHost\bin\debug** folder (or **bin\release** depending on your project settings) and open the tracking file using Notepad that corresponds to the completed workflow.</span></span> <span data-ttu-id="46892-192">如果您不未记下`InstanceId`，你可以通过使用来确定正确的跟踪文件**修改日期**Windows 资源管理器中的信息。</span><span class="sxs-lookup"><span data-stu-id="46892-192">If you did not make a note of the `InstanceId`, you can identify the correct tracking file by using the **Date modified** information in Windows Explorer.</span></span>  
  
 <span data-ttu-id="46892-193">**请输入介于 1 和 10 之间的数字**</span><span class="sxs-lookup"><span data-stu-id="46892-193">**Please enter a number between 1 and 10**</span></span>  
<span data-ttu-id="46892-194">**5 之过高。** </span><span class="sxs-lookup"><span data-stu-id="46892-194">**5 is too high.** </span></span>  
<span data-ttu-id="46892-195">**请输入介于 1 和 10 之间的数字** </span><span class="sxs-lookup"><span data-stu-id="46892-195">**Please enter a number between 1 and 10** </span></span>  
<span data-ttu-id="46892-196">**3 是过高。** </span><span class="sxs-lookup"><span data-stu-id="46892-196">**3 is too high.** </span></span>  
<span data-ttu-id="46892-197">**请输入介于 1 和 10 之间的数字** </span><span class="sxs-lookup"><span data-stu-id="46892-197">**Please enter a number between 1 and 10** </span></span>  
<span data-ttu-id="46892-198">**1 表示太低。** </span><span class="sxs-lookup"><span data-stu-id="46892-198">**1 is too low.** </span></span>  
<span data-ttu-id="46892-199">**请输入介于 1 和 10 之间的数字** </span><span class="sxs-lookup"><span data-stu-id="46892-199">**Please enter a number between 1 and 10** </span></span>  
<span data-ttu-id="46892-200">**2 是正确的。4 轮流猜测了它。**</span><span class="sxs-lookup"><span data-stu-id="46892-200">**2 is correct. You guessed it in 4 turns.**</span></span>      <span data-ttu-id="46892-201">该跟踪文件中包含已更新的 `WriteLine` 输出，包括在本主题中添加的 `WriteLine` 的输出。</span><span class="sxs-lookup"><span data-stu-id="46892-201">The updated `WriteLine` output is contained within the tracking file, including the output of the `WriteLine` that was added in this topic.</span></span>  
  
4.  <span data-ttu-id="46892-202">切换回数字猜测应用程序，然后选择在进行更新前启动的一个工作流。</span><span class="sxs-lookup"><span data-stu-id="46892-202">Switch back to the number guessing application and select one of the workflows that was started before the updates were made.</span></span> <span data-ttu-id="46892-203">您可通过查看在状态窗口下面显示的版本信息来识别当前选择的工作流的版本。</span><span class="sxs-lookup"><span data-stu-id="46892-203">You can identify the version of the currently selected workflow by looking at the version information that is displayed below the status window.</span></span> <span data-ttu-id="46892-204">输入一些猜测，并注意状态更新与前一个版本的 `WriteLine` 活动输出相符，并且不包括用户猜测。</span><span class="sxs-lookup"><span data-stu-id="46892-204">Enter some guesses and note that the status updates match the `WriteLine` activity output from the previous version, and do not include the user's guess.</span></span> <span data-ttu-id="46892-205">这是因为，这些工作流使用的是不具有 `WriteLine` 更新的前一个工作流定义。</span><span class="sxs-lookup"><span data-stu-id="46892-205">That is because these workflows are using the previous workflow definition that does not have the `WriteLine` updates.</span></span>  
  
     <span data-ttu-id="46892-206">在下一步的步骤中，[如何： 更新运行的工作流实例的定义](../../../docs/framework/windows-workflow-foundation/how-to-update-the-definition-of-a-running-workflow-instance.md)，运行`v1`工作流实例会更新，因此，它们包含的新功能的方式`v2`实例。</span><span class="sxs-lookup"><span data-stu-id="46892-206">In the next step, [How to: Update the Definition of a Running Workflow Instance](../../../docs/framework/windows-workflow-foundation/how-to-update-the-definition-of-a-running-workflow-instance.md), the running `v1` workflow instances are updated so they contain the new functionality as the `v2` instances.</span></span>
