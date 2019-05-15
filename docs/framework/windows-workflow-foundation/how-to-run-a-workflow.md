---
title: 如何：运行工作流
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: f814ff82-fe2b-4614-aebb-b768c3e61179
ms.openlocfilehash: c47e1ba89179b38055244c01507318836c899fda
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/15/2019
ms.locfileid: "65637522"
---
# <a name="how-to-run-a-workflow"></a><span data-ttu-id="bfefe-102">如何：运行工作流</span><span class="sxs-lookup"><span data-stu-id="bfefe-102">How to: Run a Workflow</span></span>
<span data-ttu-id="bfefe-103">本主题是 Windows Workflow Foundation 入门教程的延续，讨论如何创建工作流宿主并运行在以前定义的工作流[如何：创建工作流](how-to-create-a-workflow.md)主题。</span><span class="sxs-lookup"><span data-stu-id="bfefe-103">This topic is a continuation of the Windows Workflow Foundation Getting Started tutorial and discusses how to create a workflow host and run the workflow defined in the previous [How to: Create a Workflow](how-to-create-a-workflow.md) topic.</span></span>

> [!NOTE]
>  <span data-ttu-id="bfefe-104">入门教程中的每个主题都依赖于前面的主题。</span><span class="sxs-lookup"><span data-stu-id="bfefe-104">Each topic in the Getting Started tutorial depends on the previous topics.</span></span> <span data-ttu-id="bfefe-105">若要完成本主题，必须首先完成[如何：创建活动](how-to-create-an-activity.md)和[如何：创建工作流](how-to-create-a-workflow.md)。</span><span class="sxs-lookup"><span data-stu-id="bfefe-105">To complete this topic you must first complete [How to: Create an Activity](how-to-create-an-activity.md) and [How to: Create a Workflow](how-to-create-a-workflow.md).</span></span>

> [!NOTE]
>  <span data-ttu-id="bfefe-106">若要下载完整版教程，请参阅 [Windows Workflow Foundation (WF45) — 入门教程](https://go.microsoft.com/fwlink/?LinkID=248976)。</span><span class="sxs-lookup"><span data-stu-id="bfefe-106">To download a completed version of the tutorial, see [Windows Workflow Foundation (WF45) - Getting Started Tutorial](https://go.microsoft.com/fwlink/?LinkID=248976).</span></span>  
  
### <a name="to-create-the-workflow-host-project"></a><span data-ttu-id="bfefe-107">创建工作流宿主项目</span><span class="sxs-lookup"><span data-stu-id="bfefe-107">To create the workflow host project</span></span>  
  
1. <span data-ttu-id="bfefe-108">从以前打开的解决方案[如何：创建活动](how-to-create-an-activity.md)通过使用 Visual Studio 2012 的主题。</span><span class="sxs-lookup"><span data-stu-id="bfefe-108">Open the solution from the previous [How to: Create an Activity](how-to-create-an-activity.md) topic by using Visual Studio 2012.</span></span>  
  
2. <span data-ttu-id="bfefe-109">在 **解决方案资源管理器** 中右键单击 **WF45GettingStartedTutorial** 解决方案，选择 **“添加”** 和 **“新建项目”**。</span><span class="sxs-lookup"><span data-stu-id="bfefe-109">Right-click the **WF45GettingStartedTutorial** solution in **Solution Explorer** and select **Add**, **New Project**.</span></span>  
  
    > [!TIP]
    >  <span data-ttu-id="bfefe-110">如果未显示 **解决方案资源管理器** 窗口，请从 **“视图”** 菜单选择 **“解决方案资源管理器** 。</span><span class="sxs-lookup"><span data-stu-id="bfefe-110">If the **Solution Explorer** window is not displayed, select **Solution Explorer** from the **View** menu.</span></span>

3. <span data-ttu-id="bfefe-111">在 **“已安装”** 节点中，选择 **“Visual C#”**、 **“工作流”** （或 **“Visual Basic”**、 **“工作流”**）。</span><span class="sxs-lookup"><span data-stu-id="bfefe-111">In the **Installed** node, select **Visual C#**, **Workflow** (or **Visual Basic**, **Workflow**).</span></span>

    > [!NOTE]
    >  <span data-ttu-id="bfefe-112">根据在 Visual Studio 中配置为主要语言的编程语言的不同， **“Visual C#”** 或 **“Visual Basic”** 节点可能位于 **“已安装”** 节点下的 **“其他语言”** 节点中。</span><span class="sxs-lookup"><span data-stu-id="bfefe-112">Depending on which programming language is configured as the primary language in Visual Studio, the **Visual C#** or **Visual Basic** node may be under the **Other Languages** node in the **Installed** node.</span></span>

     <span data-ttu-id="bfefe-113">请确保在 .NET Framework 版本下拉列表中选择 **“.NET Framework 4.5”** 。</span><span class="sxs-lookup"><span data-stu-id="bfefe-113">Ensure that **.NET Framework 4.5** is selected in the .NET Framework version drop-down list.</span></span> <span data-ttu-id="bfefe-114">从 **“工作流”** 列表中选择 **“工作流控制台应用程序”** 。</span><span class="sxs-lookup"><span data-stu-id="bfefe-114">Select **Workflow Console Application** from the **Workflow** list.</span></span> <span data-ttu-id="bfefe-115">类型`NumberGuessWorkflowHost`成**名称**框，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="bfefe-115">Type `NumberGuessWorkflowHost` into the **Name** box and click **OK**.</span></span> <span data-ttu-id="bfefe-116">这将创建适合初学者的工作流应用程序，它具备基本的工作流承载支持。</span><span class="sxs-lookup"><span data-stu-id="bfefe-116">This creates a starter workflow application with basic workflow hosting support.</span></span> <span data-ttu-id="bfefe-117">基本承载代码将修改用于运行工作流应用程序。</span><span class="sxs-lookup"><span data-stu-id="bfefe-117">This basic hosting code is modified and used to run the workflow application.</span></span>

4. <span data-ttu-id="bfefe-118">在 **解决方案资源管理器** 中右键单击新添加的 **NumberGuessWorkflowHost** ，然后选择 **“添加引用”**。</span><span class="sxs-lookup"><span data-stu-id="bfefe-118">Right-click the newly added **NumberGuessWorkflowHost** project in **Solution Explorer** and select **Add Reference**.</span></span> <span data-ttu-id="bfefe-119">在 **“添加引用”** 列表中选择 **“解决方案”** ，选中 **NumberGuessWorkflowActivities**旁边的复选框，然后单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="bfefe-119">Select **Solution** from the **Add Reference** list, check the checkbox beside **NumberGuessWorkflowActivities**, and then click **OK**.</span></span>

5. <span data-ttu-id="bfefe-120">在 **解决方案资源管理器** 中右键单击 **Workflow1.xaml** ，然后选择 **“删除”**。</span><span class="sxs-lookup"><span data-stu-id="bfefe-120">Right-click **Workflow1.xaml** in **Solution Explorer** and choose **Delete**.</span></span> <span data-ttu-id="bfefe-121">单击 **“确定”** 以确认。</span><span class="sxs-lookup"><span data-stu-id="bfefe-121">Click **OK** to confirm.</span></span>

### <a name="to-modify-the-workflow-hosting-code"></a><span data-ttu-id="bfefe-122">修改工作流承载代码</span><span class="sxs-lookup"><span data-stu-id="bfefe-122">To modify the workflow hosting code</span></span>

1. <span data-ttu-id="bfefe-123">在 **解决方案资源管理器** 中双击 **“Program.cs”** 或 **“Module1.vb”** ，以显示其代码。</span><span class="sxs-lookup"><span data-stu-id="bfefe-123">Double-click **Program.cs** or **Module1.vb** in **Solution Explorer** to display the code.</span></span>

    > [!TIP]
    >  <span data-ttu-id="bfefe-124">如果未显示 **解决方案资源管理器** 窗口，请从 **“视图”** 菜单选择 **“解决方案资源管理器** 。</span><span class="sxs-lookup"><span data-stu-id="bfefe-124">If the **Solution Explorer** window is not displayed, select **Solution Explorer** from the **View** menu.</span></span>

     <span data-ttu-id="bfefe-125">因为此项目是用 **“工作流控制台应用程序”** 模板创建的，所以 **“Program.cs”** 或 **“Module1.vb”** 包含以下基本工作流承载代码。</span><span class="sxs-lookup"><span data-stu-id="bfefe-125">Because this project was created by using the **Workflow Console Application** template, **Program.cs** or **Module1.vb** contains the following basic workflow hosting code.</span></span>

    ```vb
    ' Create and cache the workflow definition
    Activity workflow1 = new Workflow1()
    WorkflowInvoker.Invoke(workflow1)
    ```

    ```csharp
    // Create and cache the workflow definition
    Activity workflow1 = new Workflow1();
    WorkflowInvoker.Invoke(workflow1);
    ```

     <span data-ttu-id="bfefe-126">生成的承载代码使用 <xref:System.Activities.WorkflowInvoker>。</span><span class="sxs-lookup"><span data-stu-id="bfefe-126">This generated hosting code uses <xref:System.Activities.WorkflowInvoker>.</span></span> <span data-ttu-id="bfefe-127"><xref:System.Activities.WorkflowInvoker> 提供一种简单工作流调用方法，就像方法调用一样，仅可用于不使用持久性的工作流。</span><span class="sxs-lookup"><span data-stu-id="bfefe-127"><xref:System.Activities.WorkflowInvoker> provides a simple way for invoking a workflow as if it were a method call and can be used only for workflows that do not use persistence.</span></span> <span data-ttu-id="bfefe-128"><xref:System.Activities.WorkflowApplication> 为执行工作流（包括生命周期事件通知、执行控制、书签恢复和持久性）提供更丰富的模型。</span><span class="sxs-lookup"><span data-stu-id="bfefe-128"><xref:System.Activities.WorkflowApplication> provides a richer model for executing workflows that includes notification of life-cycle events, execution control, bookmark resumption, and persistence.</span></span> <span data-ttu-id="bfefe-129">此示例使用书签并且将 <xref:System.Activities.WorkflowApplication> 用于承载工作流。</span><span class="sxs-lookup"><span data-stu-id="bfefe-129">This example uses bookmarks and <xref:System.Activities.WorkflowApplication> is used for hosting the workflow.</span></span> <span data-ttu-id="bfefe-130">在 `using` Program.cs **或** Module1.vb **顶部的现有** using **或** Imports **语句下面，添加以下** 或 **Imports** 语句。</span><span class="sxs-lookup"><span data-stu-id="bfefe-130">Add the following `using` or **Imports** statement at the top of **Program.cs** or **Module1.vb** below the existing **using** or **Imports** statements.</span></span>

    ```vb
    Imports NumberGuessWorkflowActivities
    Imports System.Threading
    ```

    ```csharp
    using NumberGuessWorkflowActivities;
    using System.Threading;
    ```

     <span data-ttu-id="bfefe-131">用以下基本 <xref:System.Activities.WorkflowInvoker> 承载代码替换使用 <xref:System.Activities.WorkflowApplication> 的代码行。</span><span class="sxs-lookup"><span data-stu-id="bfefe-131">Replace the lines of code that use <xref:System.Activities.WorkflowInvoker> with the following basic <xref:System.Activities.WorkflowApplication> hosting code.</span></span> <span data-ttu-id="bfefe-132">此示例承载代码演示承载和调用工作流的基本步骤，但尚不包含用于成功运行本主题中的工作流的功能。</span><span class="sxs-lookup"><span data-stu-id="bfefe-132">This sample hosting code demonstrates the basic steps for hosting and invoking a workflow, but does not yet contain the functionality to successfully run the workflow from this topic.</span></span> <span data-ttu-id="bfefe-133">在以下步骤中，将修改此基本代码并添加其他功能，直到完成应用程序。</span><span class="sxs-lookup"><span data-stu-id="bfefe-133">In the following steps, this basic code is modified and additional features are added until the application is complete.</span></span>

    > [!NOTE]
    >  <span data-ttu-id="bfefe-134">请替换`Workflow1`在这些示例中使用`FlowchartNumberGuessWorkflow`， `SequentialNumberGuessWorkflow`，或`StateMachineNumberGuessWorkflow`，具体在以前完成的工作流取决于[如何：创建工作流](how-to-create-a-workflow.md)步骤。</span><span class="sxs-lookup"><span data-stu-id="bfefe-134">Please replace `Workflow1` in these examples with `FlowchartNumberGuessWorkflow`, `SequentialNumberGuessWorkflow`, or `StateMachineNumberGuessWorkflow`, depending on which workflow you completed in the previous [How to: Create a Workflow](how-to-create-a-workflow.md) step.</span></span> <span data-ttu-id="bfefe-135">如果不替换 `Workflow1` ，在尝试生成或运行工作流时会出现生成错误。</span><span class="sxs-lookup"><span data-stu-id="bfefe-135">If you do not replace `Workflow1` then you will get build errors when you try and build or run the workflow.</span></span>

     [!code-csharp[CFX_WF_GettingStarted#4](~/samples/snippets/csharp/VS_Snippets_CFX/cfx_wf_gettingstarted/cs/extrasnippets.cs#4)]
     [!code-vb[CFX_WF_GettingStarted#4](~/samples/snippets/visualbasic/VS_Snippets_CFX/cfx_wf_gettingstarted/vb/extrasnippets.vb#4)]

     <span data-ttu-id="bfefe-136">此代码将创建一个 <xref:System.Activities.WorkflowApplication>，订阅三个工作流生命周期事件，通过调用 <xref:System.Activities.WorkflowApplication.Run%2A>来启动工作流，然后等待工作流完成。</span><span class="sxs-lookup"><span data-stu-id="bfefe-136">This code creates a <xref:System.Activities.WorkflowApplication>, subscribes to three workflow life-cycle events, starts the workflow with a call to <xref:System.Activities.WorkflowApplication.Run%2A>, and then waits for the workflow to complete.</span></span> <span data-ttu-id="bfefe-137">工作流完成时，将设置 <xref:System.Threading.AutoResetEvent> ，并且宿主应用程序也完成。</span><span class="sxs-lookup"><span data-stu-id="bfefe-137">When the workflow completes, the <xref:System.Threading.AutoResetEvent> is set and the host application completes.</span></span>

### <a name="to-set-input-arguments-of-a-workflow"></a><span data-ttu-id="bfefe-138">设置工作流的输入参数</span><span class="sxs-lookup"><span data-stu-id="bfefe-138">To set input arguments of a workflow</span></span>

1. <span data-ttu-id="bfefe-139">在 **“Program.cs”** 或 **“Module1.vb”** 顶部的现有 `using` 或 `Imports` 语句下面，添加以下语句。</span><span class="sxs-lookup"><span data-stu-id="bfefe-139">Add the following statement at the top of **Program.cs** or **Module1.vb** below the existing `using` or `Imports` statements.</span></span>

     [!code-csharp[CFX_WF_GettingStarted#5](~/samples/snippets/csharp/VS_Snippets_CFX/cfx_wf_gettingstarted/cs/program.cs#5)]
     [!code-vb[CFX_WF_GettingStarted#5](~/samples/snippets/visualbasic/VS_Snippets_CFX/cfx_wf_gettingstarted/vb/module1.vb#5)]

2. <span data-ttu-id="bfefe-140">将创建新 <xref:System.Activities.WorkflowApplication> 的代码行替换为以下代码，该代码创建一个参数字典并在创建后将其传递给工作流。</span><span class="sxs-lookup"><span data-stu-id="bfefe-140">Replace the line of code that creates the new <xref:System.Activities.WorkflowApplication> with the following code that creates and passes a dictionary of parameters to the workflow when it is created.</span></span>

    > [!NOTE]
    >  <span data-ttu-id="bfefe-141">请替换`Workflow1`在这些示例中使用`FlowchartNumberGuessWorkflow`， `SequentialNumberGuessWorkflow`，或`StateMachineNumberGuessWorkflow`，具体在以前完成的工作流取决于[如何：创建工作流](how-to-create-a-workflow.md)步骤。</span><span class="sxs-lookup"><span data-stu-id="bfefe-141">Please replace `Workflow1` in these examples with `FlowchartNumberGuessWorkflow`, `SequentialNumberGuessWorkflow`, or `StateMachineNumberGuessWorkflow`, depending on which workflow you completed in the previous [How to: Create a Workflow](how-to-create-a-workflow.md) step.</span></span> <span data-ttu-id="bfefe-142">如果不替换 `Workflow1` ，在尝试生成或运行工作流时会出现生成错误。</span><span class="sxs-lookup"><span data-stu-id="bfefe-142">If you do not replace `Workflow1` then you will get build errors when you try and build or run the workflow.</span></span>

     [!code-csharp[CFX_WF_GettingStarted#6](~/samples/snippets/csharp/VS_Snippets_CFX/cfx_wf_gettingstarted/cs/program.cs#6)]
     [!code-vb[CFX_WF_GettingStarted#6](~/samples/snippets/visualbasic/VS_Snippets_CFX/cfx_wf_gettingstarted/vb/module1.vb#6)]

     <span data-ttu-id="bfefe-143">此字典包含一个键为 `MaxNumber`的元素。</span><span class="sxs-lookup"><span data-stu-id="bfefe-143">This dictionary contains one element with a key of `MaxNumber`.</span></span> <span data-ttu-id="bfefe-144">输入字典中的键对应工作流根活动的输入参数。</span><span class="sxs-lookup"><span data-stu-id="bfefe-144">Keys in the input dictionary correspond to input arguments on the root activity of the workflow.</span></span> <span data-ttu-id="bfefe-145">工作流使用`MaxNumber` 来确定随机生成数的上边界。</span><span class="sxs-lookup"><span data-stu-id="bfefe-145">`MaxNumber` is used by the workflow to determine the upper bound for the randomly generated number.</span></span>

### <a name="to-retrieve-output-arguments-of-a-workflow"></a><span data-ttu-id="bfefe-146">检索工作流的输出参数</span><span class="sxs-lookup"><span data-stu-id="bfefe-146">To retrieve output arguments of a workflow</span></span>

1. <span data-ttu-id="bfefe-147">修改 <xref:System.Activities.WorkflowApplication.Completed%2A> 处理程序以检索并显示工作流使用的轮数。</span><span class="sxs-lookup"><span data-stu-id="bfefe-147">Modify the <xref:System.Activities.WorkflowApplication.Completed%2A> handler to retrieve and display the number of turns used by the workflow.</span></span>

     [!code-csharp[CFX_WF_GettingStarted#7](~/samples/snippets/csharp/VS_Snippets_CFX/cfx_wf_gettingstarted/cs/program.cs#7)]
     [!code-vb[CFX_WF_GettingStarted#7](~/samples/snippets/visualbasic/VS_Snippets_CFX/cfx_wf_gettingstarted/vb/module1.vb#7)]

### <a name="to-resume-a-bookmark"></a><span data-ttu-id="bfefe-148">继续执行书签</span><span class="sxs-lookup"><span data-stu-id="bfefe-148">To resume a bookmark</span></span>

1. <span data-ttu-id="bfefe-149">将以下代码添加到 `Main` 方法顶部，紧接在现有 <xref:System.Threading.AutoResetEvent> 声明之后。</span><span class="sxs-lookup"><span data-stu-id="bfefe-149">Add the following code at the top of the `Main` method just after the existing <xref:System.Threading.AutoResetEvent> declaration.</span></span>

     [!code-csharp[CFX_WF_GettingStarted#8](~/samples/snippets/csharp/VS_Snippets_CFX/cfx_wf_gettingstarted/cs/program.cs#8)]
     [!code-vb[CFX_WF_GettingStarted#8](~/samples/snippets/visualbasic/VS_Snippets_CFX/cfx_wf_gettingstarted/vb/module1.vb#8)]

2. <span data-ttu-id="bfefe-150">将以下 <xref:System.Activities.WorkflowApplication.Idle%2A> 处理程序添加到 `Main`中，紧接在现有的三个工作流生命周期处理程序的下面。</span><span class="sxs-lookup"><span data-stu-id="bfefe-150">Add the following <xref:System.Activities.WorkflowApplication.Idle%2A> handler just below the existing three workflow life-cycle handlers in `Main`.</span></span>

     [!code-csharp[CFX_WF_GettingStarted#9](~/samples/snippets/csharp/VS_Snippets_CFX/cfx_wf_gettingstarted/cs/program.cs#9)]
     [!code-vb[CFX_WF_GettingStarted#9](~/samples/snippets/visualbasic/VS_Snippets_CFX/cfx_wf_gettingstarted/vb/module1.vb#9)]

     <span data-ttu-id="bfefe-151">每次工作流变为空闲状态等待下一个猜测时，都会调用此处理程序并设置 `idleAction` <xref:System.Threading.AutoResetEvent> 。</span><span class="sxs-lookup"><span data-stu-id="bfefe-151">Each time the workflow becomes idle waiting for the next guess, this handler is called and the `idleAction` <xref:System.Threading.AutoResetEvent> is set.</span></span> <span data-ttu-id="bfefe-152">下面步骤中的代码使用 `idleEvent` 和 `syncEvent` 来确定工作流是在等待下一个猜测还是已完成。</span><span class="sxs-lookup"><span data-stu-id="bfefe-152">The code in the following step uses `idleEvent` and `syncEvent` to determine whether the workflow is waiting for the next guess or is complete.</span></span>

    > [!NOTE]
    >  <span data-ttu-id="bfefe-153">在本示例中，宿主应用程序在 <xref:System.Activities.WorkflowApplication.Completed%2A> 和 <xref:System.Activities.WorkflowApplication.Idle%2A> 处理程序中使用自动重置事件将宿主应用程序与工作流的进度同步。</span><span class="sxs-lookup"><span data-stu-id="bfefe-153">In this example, the host application uses auto-reset events in the <xref:System.Activities.WorkflowApplication.Completed%2A> and <xref:System.Activities.WorkflowApplication.Idle%2A> handlers to synchronize the host application with the progress of the workflow.</span></span> <span data-ttu-id="bfefe-154">在继续执行书签之前，不需要阻止并等待工作流变为空闲状态，但在此示例中需要同步事件，以使宿主知道工作流是否已完成，或是否在等待使用 <xref:System.Activities.Bookmark>的更多用户输入。</span><span class="sxs-lookup"><span data-stu-id="bfefe-154">It is not necessary to block and wait for the workflow to become idle before resuming a bookmark, but in this example the synchronization events are required so the host knows whether the workflow is complete or whether it is waiting on more user input by using the <xref:System.Activities.Bookmark>.</span></span> <span data-ttu-id="bfefe-155">有关详细信息，请参阅[书签](bookmarks.md)。</span><span class="sxs-lookup"><span data-stu-id="bfefe-155">For more information, see [Bookmarks](bookmarks.md).</span></span>

3. <span data-ttu-id="bfefe-156">移除对 `WaitOne`的调用，并替换为收集用户输入并恢复 <xref:System.Activities.Bookmark>的代码。</span><span class="sxs-lookup"><span data-stu-id="bfefe-156">Remove the call to `WaitOne`, and replace it with code to gather input from the user and resume the <xref:System.Activities.Bookmark>.</span></span>

     <span data-ttu-id="bfefe-157">移除下面的代码行。</span><span class="sxs-lookup"><span data-stu-id="bfefe-157">Remove the following line of code.</span></span>

     [!code-csharp[CFX_WF_GettingStarted#10](~/samples/snippets/csharp/VS_Snippets_CFX/cfx_wf_gettingstarted/cs/extrasnippets.cs#10)]
     [!code-vb[CFX_WF_GettingStarted#10](~/samples/snippets/visualbasic/VS_Snippets_CFX/cfx_wf_gettingstarted/vb/extrasnippets.vb#10)]

     <span data-ttu-id="bfefe-158">使用下面的示例替换它。</span><span class="sxs-lookup"><span data-stu-id="bfefe-158">Replace it with the following example.</span></span>

     [!code-csharp[CFX_WF_GettingStarted#11](~/samples/snippets/csharp/VS_Snippets_CFX/cfx_wf_gettingstarted/cs/program.cs#11)]
     [!code-vb[CFX_WF_GettingStarted#11](~/samples/snippets/visualbasic/VS_Snippets_CFX/cfx_wf_gettingstarted/vb/module1.vb#11)]

## <a name="BKMK_ToRunTheApplication"></a> <span data-ttu-id="bfefe-159">生成并运行应用程序</span><span class="sxs-lookup"><span data-stu-id="bfefe-159">To build and run the application</span></span>

1. <span data-ttu-id="bfefe-160">在 **解决方案资源管理器** 中，右键单击 **NumberGuessWorkflowHost** 项目，然后选择 **“设为启动项目”**。</span><span class="sxs-lookup"><span data-stu-id="bfefe-160">Right-click **NumberGuessWorkflowHost** in **Solution Explorer** and select **Set as StartUp Project**.</span></span>

2. <span data-ttu-id="bfefe-161">按 Ctrl+F5 生成并运行应用程序。</span><span class="sxs-lookup"><span data-stu-id="bfefe-161">Press CTRL+F5 to build and run the application.</span></span> <span data-ttu-id="bfefe-162">尝试以尽可能少的次数猜出该数。</span><span class="sxs-lookup"><span data-stu-id="bfefe-162">Try to guess the number in as few turns as possible.</span></span>

     <span data-ttu-id="bfefe-163">要尝试其他工作流样式的应用程序，请用 `Workflow1` 、 <xref:System.Activities.WorkflowApplication> 或 `FlowchartNumberGuessWorkflow`（取决于所需工作流样式）替换代码中用于创建 `SequentialNumberGuessWorkflow`的 `StateMachineNumberGuessWorkflow`。</span><span class="sxs-lookup"><span data-stu-id="bfefe-163">To try the application with one of the other styles of workflow, replace `Workflow1` in the code that creates the <xref:System.Activities.WorkflowApplication> with `FlowchartNumberGuessWorkflow`, `SequentialNumberGuessWorkflow`, or `StateMachineNumberGuessWorkflow`, depending on which workflow style you desire.</span></span>

     [!code-csharp[CFX_WF_GettingStarted#6](~/samples/snippets/csharp/VS_Snippets_CFX/cfx_wf_gettingstarted/cs/program.cs#6)]
     [!code-vb[CFX_WF_GettingStarted#6](~/samples/snippets/visualbasic/VS_Snippets_CFX/cfx_wf_gettingstarted/vb/module1.vb#6)]

     <span data-ttu-id="bfefe-164">有关如何向工作流应用程序添加持久性的说明，请参阅下一主题[如何：创建和运行长时间运行工作流](how-to-create-and-run-a-long-running-workflow.md)。</span><span class="sxs-lookup"><span data-stu-id="bfefe-164">For instructions about how to add persistence to a workflow application, see the next topic, [How to: Create and Run a Long Running Workflow](how-to-create-and-run-a-long-running-workflow.md).</span></span>

## <a name="example"></a><span data-ttu-id="bfefe-165">示例</span><span class="sxs-lookup"><span data-stu-id="bfefe-165">Example</span></span>
 <span data-ttu-id="bfefe-166">下面的示例是 `Main` 方法的完整代码清单。</span><span class="sxs-lookup"><span data-stu-id="bfefe-166">The following example is the complete code listing for the `Main` method.</span></span>

> [!NOTE]
>  <span data-ttu-id="bfefe-167">请替换`Workflow1`在这些示例中使用`FlowchartNumberGuessWorkflow`， `SequentialNumberGuessWorkflow`，或`StateMachineNumberGuessWorkflow`，具体在以前完成的工作流取决于[如何：创建工作流](how-to-create-a-workflow.md)步骤。</span><span class="sxs-lookup"><span data-stu-id="bfefe-167">Please replace `Workflow1` in these examples with `FlowchartNumberGuessWorkflow`, `SequentialNumberGuessWorkflow`, or `StateMachineNumberGuessWorkflow`, depending on which workflow you completed in the previous [How to: Create a Workflow](how-to-create-a-workflow.md) step.</span></span> <span data-ttu-id="bfefe-168">如果不替换 `Workflow1` ，在尝试生成或运行工作流时会出现生成错误。</span><span class="sxs-lookup"><span data-stu-id="bfefe-168">If you do not replace `Workflow1` then you will get build errors when you try and build or run the workflow.</span></span>

 [!code-csharp[CFX_WF_GettingStarted#12](~/samples/snippets/csharp/VS_Snippets_CFX/cfx_wf_gettingstarted/cs/program.cs#12)]
 [!code-vb[CFX_WF_GettingStarted#12](~/samples/snippets/visualbasic/VS_Snippets_CFX/cfx_wf_gettingstarted/vb/module1.vb#12)]

## <a name="see-also"></a><span data-ttu-id="bfefe-169">请参阅</span><span class="sxs-lookup"><span data-stu-id="bfefe-169">See also</span></span>

- <xref:System.Activities.WorkflowApplication>
- <xref:System.Activities.Bookmark>
- [<span data-ttu-id="bfefe-170">Windows Workflow Foundation 编程</span><span class="sxs-lookup"><span data-stu-id="bfefe-170">Windows Workflow Foundation Programming</span></span>](programming.md)
- [<span data-ttu-id="bfefe-171">入门教程</span><span class="sxs-lookup"><span data-stu-id="bfefe-171">Getting Started Tutorial</span></span>](getting-started-tutorial.md)
- [<span data-ttu-id="bfefe-172">如何：创建工作流</span><span class="sxs-lookup"><span data-stu-id="bfefe-172">How to: Create a Workflow</span></span>](how-to-create-a-workflow.md)
- [<span data-ttu-id="bfefe-173">如何：创建和运行长时间运行工作流</span><span class="sxs-lookup"><span data-stu-id="bfefe-173">How to: Create and Run a Long Running Workflow</span></span>](how-to-create-and-run-a-long-running-workflow.md)
- [<span data-ttu-id="bfefe-174">在工作流中等待输入</span><span class="sxs-lookup"><span data-stu-id="bfefe-174">Waiting for Input in a Workflow</span></span>](waiting-for-input-in-a-workflow.md)
- [<span data-ttu-id="bfefe-175">托管工作流</span><span class="sxs-lookup"><span data-stu-id="bfefe-175">Hosting Workflows</span></span>](hosting-workflows.md)
