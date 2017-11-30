---
title: "如何：创建自定义跟踪参与者"
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
ms.assetid: 1b612c7e-2381-4a7c-b07a-77030415f2a3
caps.latest.revision: "6"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: ef647068e6ec757de391015f4959335c29038cfa
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-a-custom-tracking-participant"></a><span data-ttu-id="677aa-102">如何：创建自定义跟踪参与者</span><span class="sxs-lookup"><span data-stu-id="677aa-102">How to: Create a Custom Tracking Participant</span></span>
<span data-ttu-id="677aa-103">工作流跟踪用于查看工作流执行的状态。</span><span class="sxs-lookup"><span data-stu-id="677aa-103">Workflow tracking provides visibility into the status of workflow execution.</span></span> <span data-ttu-id="677aa-104">工作流运行时发出跟踪记录，这些跟踪记录描述工作流生命周期事件、活动生命周期事件、书签摘要和故障。</span><span class="sxs-lookup"><span data-stu-id="677aa-104">The workflow runtime emits tracking records that describe workflow lifecycle events, activity lifecycle events, bookmark resumptions, and faults.</span></span> <span data-ttu-id="677aa-105">这些跟踪记录供跟踪参与者使用。</span><span class="sxs-lookup"><span data-stu-id="677aa-105">These tracking records are consumed by tracking participants.</span></span> [!INCLUDE[wf](../../../includes/wf-md.md)]<span data-ttu-id="677aa-106"> 包括一个标准跟踪参与者，可将跟踪记录作为 Windows 事件跟踪 (ETW) 事件写入。</span><span class="sxs-lookup"><span data-stu-id="677aa-106"> includes a standard tracking participant that writes tracking records as Event Tracing for Windows (ETW) events.</span></span> <span data-ttu-id="677aa-107">如果这不能满足您的要求，您还可以编写自定义跟踪参与者。</span><span class="sxs-lookup"><span data-stu-id="677aa-107">If that does not meet your requirements, you can also write a custom tracking participant.</span></span> <span data-ttu-id="677aa-108">本教程步骤说明如何创建自定义跟踪参与者和跟踪配置文件，该配置文件捕获 `WriteLine` 活动的输出，以便将这些活动显示给用户。</span><span class="sxs-lookup"><span data-stu-id="677aa-108">This tutorial step describes how to create a custom tracking participant and tracking profile that capture the output of `WriteLine` activities so that they can be displayed to the user.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="677aa-109">入门教程中的每个主题都依赖于前面的主题。</span><span class="sxs-lookup"><span data-stu-id="677aa-109">Each topic in the Getting Started tutorial depends on the previous topics.</span></span> <span data-ttu-id="677aa-110">若要完成本主题，必须先完成前面的主题。</span><span class="sxs-lookup"><span data-stu-id="677aa-110">To complete this topic, you must first complete the previous topics.</span></span> <span data-ttu-id="677aa-111">若要下载完整的版本或观看教程视频演练，请参阅[Windows Workflow Foundation (WF45)-入门教程](http://go.microsoft.com/fwlink/?LinkID=248976)。</span><span class="sxs-lookup"><span data-stu-id="677aa-111">To download a completed version or view a video walkthrough of the tutorial, see [Windows Workflow Foundation (WF45) - Getting Started Tutorial](http://go.microsoft.com/fwlink/?LinkID=248976).</span></span>  
  
## <a name="in-this-topic"></a><span data-ttu-id="677aa-112">主题内容</span><span class="sxs-lookup"><span data-stu-id="677aa-112">In this topic</span></span>  
  
-   [<span data-ttu-id="677aa-113">若要创建自定义跟踪参与者</span><span class="sxs-lookup"><span data-stu-id="677aa-113">To create the custom tracking participant</span></span>](../../../docs/framework/windows-workflow-foundation/how-to-create-a-custom-tracking-participant.md#BKMK_CustomTrackingParticipant)  
  
-   [<span data-ttu-id="677aa-114">创建跟踪配置文件并注册跟踪参与者</span><span class="sxs-lookup"><span data-stu-id="677aa-114">To create the tracking profile and register the tracking participant</span></span>](../../../docs/framework/windows-workflow-foundation/how-to-create-a-custom-tracking-participant.md#BKMK_TrackingProfile)  
  
-   [<span data-ttu-id="677aa-115">若要显示的跟踪信息</span><span class="sxs-lookup"><span data-stu-id="677aa-115">To display the tracking information</span></span>](../../../docs/framework/windows-workflow-foundation/how-to-create-a-custom-tracking-participant.md#BKMK_DisplayTracking)  
  
-   [<span data-ttu-id="677aa-116">若要生成并运行应用程序</span><span class="sxs-lookup"><span data-stu-id="677aa-116">To build and run the application</span></span>](../../../docs/framework/windows-workflow-foundation/how-to-create-a-custom-tracking-participant.md#BKMK_BuildAndRun)  
  
###  <span data-ttu-id="677aa-117"><a name="BKMK_CustomTrackingParticipant"></a>若要创建自定义跟踪参与者</span><span class="sxs-lookup"><span data-stu-id="677aa-117"><a name="BKMK_CustomTrackingParticipant"></a> To create the custom tracking participant</span></span>  
  
1.  <span data-ttu-id="677aa-118">右键单击**NumberGuessWorkflowHost**中**解决方案资源管理器**选择**添加**，**类**。</span><span class="sxs-lookup"><span data-stu-id="677aa-118">Right-click **NumberGuessWorkflowHost** in **Solution Explorer** and choose **Add**, **Class**.</span></span> <span data-ttu-id="677aa-119">类型`StatusTrackingParticipant`到**名称**框中，然后单击**添加**。</span><span class="sxs-lookup"><span data-stu-id="677aa-119">Type `StatusTrackingParticipant` into the **Name** box, and click **Add**.</span></span>  
  
2.  <span data-ttu-id="677aa-120">在包含其他 `using`（或 `Imports`）语句的文件的顶部添加以下 `using`（或 `Imports`）语句。</span><span class="sxs-lookup"><span data-stu-id="677aa-120">Add the following `using` (or `Imports`) statements at the top of the file with the other `using` (or `Imports`) statements.</span></span>  
  
    ```vb  
    Imports System.Activities.Tracking  
    Imports System.IO  
    ```  
  
    ```csharp  
    using System.Activities.Tracking;  
    using System.IO;  
    ```  
  
3.  <span data-ttu-id="677aa-121">修改 `StatusTrackingParticipant` 类，使它从 `TrackingParticipant` 继承。</span><span class="sxs-lookup"><span data-stu-id="677aa-121">Modify the `StatusTrackingParticipant` class so that it inherits from `TrackingParticipant`.</span></span>  
  
    ```vb  
    Public Class StatusTrackingParticipant  
        Inherits TrackingParticipant  
  
    End Class  
    ```  
  
    ```csharp  
    class StatusTrackingParticipant : TrackingParticipant  
    {  
    }  
    ```  
  
4.  <span data-ttu-id="677aa-122">添加以下 `Track` 方法重写。</span><span class="sxs-lookup"><span data-stu-id="677aa-122">Add the following `Track` method override.</span></span> <span data-ttu-id="677aa-123">有多种不同类型的跟踪记录。</span><span class="sxs-lookup"><span data-stu-id="677aa-123">There are several different types of tracking records.</span></span> <span data-ttu-id="677aa-124">我们对 `WriteLine` 活动的输出十分感兴趣，这些活动包含在活动跟踪记录中。</span><span class="sxs-lookup"><span data-stu-id="677aa-124">We are interested in the output of `WriteLine` activities, which are contained in activity tracking records.</span></span> <span data-ttu-id="677aa-125">如果 `TrackingRecord` 为 `ActivityTrackingRecord` 活动的 `WriteLine`，则 `Text` 的 `WriteLine` 将附加到工作流 `InstanceId` 后面的指定文件。</span><span class="sxs-lookup"><span data-stu-id="677aa-125">If the `TrackingRecord` is an `ActivityTrackingRecord` for a `WriteLine` activity, the `Text` of the `WriteLine` is appended to a file named after the `InstanceId` of the workflow.</span></span> <span data-ttu-id="677aa-126">在本教程中，该文件将保存到宿主应用程序的当前文件夹中。</span><span class="sxs-lookup"><span data-stu-id="677aa-126">In this tutorial, the file is saved to the current folder of the host application.</span></span>  
  
    ```vb  
    Protected Overrides Sub Track(record As TrackingRecord, timeout As TimeSpan)  
        Dim asr As ActivityStateRecord = TryCast(record, ActivityStateRecord)  
  
        If Not asr Is Nothing Then  
            If asr.State = ActivityStates.Executing And _  
            asr.Activity.TypeName = "System.Activities.Statements.WriteLine" Then  
  
                'Append the WriteLine output to the tracking  
                'file for this instance.  
                Using writer As StreamWriter = File.AppendText(record.InstanceId.ToString())  
                    writer.WriteLine(asr.Arguments("Text"))  
                    writer.Close()  
                End Using  
            End If  
        End If  
    End Sub  
    ```  
  
    ```csharp  
    protected override void Track(TrackingRecord record, TimeSpan timeout)  
    {  
        ActivityStateRecord asr = record as ActivityStateRecord;  
  
        if (asr != null)  
        {  
            if (asr.State == ActivityStates.Executing &&  
                asr.Activity.TypeName == "System.Activities.Statements.WriteLine")  
            {  
                // Append the WriteLine output to the tracking  
                // file for this instance  
                using (StreamWriter writer = File.AppendText(record.InstanceId.ToString()))  
                {  
                    writer.WriteLine(asr.Arguments["Text"]);  
                    writer.Close();  
                }  
            }  
        }  
    }  
    ```  
  
     <span data-ttu-id="677aa-127">未指定跟踪配置文件时，使用默认跟踪配置文件。</span><span class="sxs-lookup"><span data-stu-id="677aa-127">When no tracking profile is specified, the default tracking profile is used.</span></span> <span data-ttu-id="677aa-128">使用默认跟踪配置文件时，将为所有 `ActivityStates` 发出跟踪记录。</span><span class="sxs-lookup"><span data-stu-id="677aa-128">When the default tracking profile is used, tracking records are emitted for all `ActivityStates`.</span></span> <span data-ttu-id="677aa-129">因为我们只需在 `WriteLine` 活动的生命周期内捕获一次文本，所以我们仅从 `ActivityStates.Executing` 状态捕获文本。</span><span class="sxs-lookup"><span data-stu-id="677aa-129">Because we only need to capture the text one time during the lifecycle of the `WriteLine` activity, we only extract the text from the `ActivityStates.Executing` state.</span></span> <span data-ttu-id="677aa-130">在[创建跟踪配置文件并注册跟踪参与者](../../../docs/framework/windows-workflow-foundation/how-to-create-a-custom-tracking-participant.md#BKMK_TrackingProfile)，跟踪配置文件会创建一个仅指定`WriteLine``ActivityStates.Executing`发出跟踪记录。</span><span class="sxs-lookup"><span data-stu-id="677aa-130">In [To create the tracking profile and register the tracking participant](../../../docs/framework/windows-workflow-foundation/how-to-create-a-custom-tracking-participant.md#BKMK_TrackingProfile), a tracking profile is created that specifies that only `WriteLine` `ActivityStates.Executing` tracking records are emitted.</span></span>  
  
###  <span data-ttu-id="677aa-131"><a name="BKMK_TrackingProfile"></a>创建跟踪配置文件并注册跟踪参与者</span><span class="sxs-lookup"><span data-stu-id="677aa-131"><a name="BKMK_TrackingProfile"></a> To create the tracking profile and register the tracking participant</span></span>  
  
1.  <span data-ttu-id="677aa-132">右键单击**WorkflowHostForm**中**解决方案资源管理器**选择**查看代码**。</span><span class="sxs-lookup"><span data-stu-id="677aa-132">Right-click **WorkflowHostForm** in **Solution Explorer** and choose **View Code**.</span></span>  
  
2.  <span data-ttu-id="677aa-133">在包含其他 `using`（或 `Imports`）语句的文件的顶部添加以下 `using`（或 `Imports`）语句。</span><span class="sxs-lookup"><span data-stu-id="677aa-133">Add the following `using` (or `Imports`) statement at the top of the file with the other `using` (or `Imports`) statements.</span></span>  
  
    ```vb  
    Imports System.Activities.Tracking  
    ```  
  
    ```csharp  
    using System.Activities.Tracking;  
    ```  
  
3.  <span data-ttu-id="677aa-134">将以下代码添加到 `ConfigureWorkflowApplication`，紧接在将 `StringWriter` 添加到工作流扩展的代码之后和工作流生命周期处理程序之前。</span><span class="sxs-lookup"><span data-stu-id="677aa-134">Add the following code to `ConfigureWorkflowApplication` just after the code that adds the `StringWriter` to the workflow extensions and before the workflow lifecycle handlers.</span></span>  
  
    ```vb  
    'Add the custom tracking participant with a tracking profile  
    'that only emits tracking records for WriteLine activities.  
    Dim query As New ActivityStateQuery()  
    query.ActivityName = "WriteLine"  
    query.States.Add(ActivityStates.Executing)  
    query.Arguments.Add("Text")  
  
    Dim profile As New TrackingProfile()  
    profile.Queries.Add(query)  
  
    Dim stp As New StatusTrackingParticipant()  
    stp.TrackingProfile = profile  
  
    wfApp.Extensions.Add(stp)  
    ```  
  
    ```csharp  
    // Add the custom tracking participant with a tracking profile  
    // that only emits tracking records for WriteLine activities.  
    StatusTrackingParticipant stp = new StatusTrackingParticipant  
    {  
        TrackingProfile = new TrackingProfile  
        {  
            Queries =   
            {  
                new ActivityStateQuery  
                {  
                    ActivityName = "WriteLine",  
                    States = { ActivityStates.Executing },  
                    Arguments = { "Text" }  
                }  
            }  
        }  
    };  
  
    wfApp.Extensions.Add(stp);  
    ```  
  
     <span data-ttu-id="677aa-135">此跟踪配置文件指定仅向自定义跟踪参与者发出处于 `WriteLine` 状态的 `Executing` 活动的活动状态记录。</span><span class="sxs-lookup"><span data-stu-id="677aa-135">This tracking profile specifies that only activity state records for `WriteLine` activities in the `Executing` state are emitted to the custom tracking participant.</span></span>  
  
     <span data-ttu-id="677aa-136">在添加代码后，`ConfigureWorkflowApplication` 的开头将类似于以下示例。</span><span class="sxs-lookup"><span data-stu-id="677aa-136">After adding the code, the start of `ConfigureWorkflowApplication` will look like the following example.</span></span>  
  
    ```vb  
    Private Sub ConfigureWorkflowApplication(wfApp As WorkflowApplication)  
        'Configure the persistence store.  
        wfApp.InstanceStore = store  
  
        'Add a StringWriter to the extensions. This captures the output  
        'from the WriteLine activities so we can display it in the form.  
        Dim sw As New StringWriter()  
        wfApp.Extensions.Add(sw)  
  
        'Add the custom tracking participant with a tracking profile  
        'that only emits tracking records for WriteLine activities.  
        Dim query As New ActivityStateQuery()  
        query.ActivityName = "WriteLine"  
        query.States.Add(ActivityStates.Executing)  
        query.Arguments.Add("Text")  
  
        Dim profile As New TrackingProfile()  
        profile.Queries.Add(query)  
  
        Dim stp As New StatusTrackingParticipant()  
        stp.TrackingProfile = profile  
  
        wfApp.Extensions.Add(stp)  
  
        'Workflow lifecycle handlers...  
    ```  
  
    ```csharp  
    private void ConfigureWorkflowApplication(WorkflowApplication wfApp)  
    {  
        // Configure the persistence store.  
        wfApp.InstanceStore = store;  
  
        // Add a StringWriter to the extensions. This captures the output  
        // from the WriteLine activities so we can display it in the form.  
        StringWriter sw = new StringWriter();  
        wfApp.Extensions.Add(sw);  
  
        // Add the custom tracking participant with a tracking profile  
        // that only emits tracking records for WriteLine activities.  
        StatusTrackingParticipant stp = new StatusTrackingParticipant  
        {  
            TrackingProfile = new TrackingProfile  
            {  
                Queries =   
                {  
                    new ActivityStateQuery  
                    {  
                        ActivityName = "WriteLine",  
                        States = { ActivityStates.Executing },  
                        Arguments = { "Text" }  
                    }  
                }  
            }  
        };  
  
        wfApp.Extensions.Add(stp);  
  
        // Workflow lifecycle handlers...  
    ```  
  
###  <span data-ttu-id="677aa-137"><a name="BKMK_DisplayTracking"></a>若要显示的跟踪信息</span><span class="sxs-lookup"><span data-stu-id="677aa-137"><a name="BKMK_DisplayTracking"></a> To display the tracking information</span></span>  
  
1.  <span data-ttu-id="677aa-138">右键单击**WorkflowHostForm**中**解决方案资源管理器**选择**查看代码**。</span><span class="sxs-lookup"><span data-stu-id="677aa-138">Right-click **WorkflowHostForm** in **Solution Explorer** and choose **View Code**.</span></span>  
  
2.  <span data-ttu-id="677aa-139">在 `InstanceId_SelectedIndexChanged` 处理程序中，添加以下代码，紧接在清除状态窗口的代码之后。</span><span class="sxs-lookup"><span data-stu-id="677aa-139">In the `InstanceId_SelectedIndexChanged` handler, add the following code immediately after the code that clears the status window.</span></span>  
  
    ```vb  
    'If there is tracking data for this workflow, display it  
    'in the status window.  
    If File.Exists(WorkflowInstanceId.ToString()) Then  
        Dim status As String = File.ReadAllText(WorkflowInstanceId.ToString())  
        UpdateStatus(status)  
    End If  
    ```  
  
    ```csharp  
    // If there is tracking data for this workflow, display it  
    // in the status window.  
    if (File.Exists(WorkflowInstanceId.ToString()))  
    {  
        string status = File.ReadAllText(WorkflowInstanceId.ToString());  
        UpdateStatus(status);  
    }  
    ```  
  
     <span data-ttu-id="677aa-140">在工作流列表中选择新工作流后，将加载该工作流的跟踪记录并将其显示在状态窗口中。</span><span class="sxs-lookup"><span data-stu-id="677aa-140">When a new workflow is selected in the workflow list, the tracking records for that workflow are loaded and displayed in the status window.</span></span> <span data-ttu-id="677aa-141">以下示例是完成的 `InstanceId_SelectedIndexChanged` 处理程序。</span><span class="sxs-lookup"><span data-stu-id="677aa-141">The following example is the completed `InstanceId_SelectedIndexChanged` handler.</span></span>  
  
    ```vb  
    Private Sub InstanceId_SelectedIndexChanged(sender As Object, e As EventArgs) Handles InstanceId.SelectedIndexChanged  
        If InstanceId.SelectedIndex = -1 Then  
            Return  
        End If  
  
        'Clear the status window.  
        WorkflowStatus.Clear()  
  
        'If there is tracking data for this workflow, display it  
        'in the status window.  
        If File.Exists(WorkflowInstanceId.ToString()) Then  
            Dim status As String = File.ReadAllText(WorkflowInstanceId.ToString())  
            UpdateStatus(status)  
        End If  
  
        'Get the workflow version and display it.  
        'If the workflow is just starting then this info will not  
        'be available in the persistence store so do not try and retrieve it.  
        If Not WorkflowStarting Then  
            Dim instance As WorkflowApplicationInstance = _  
                WorkflowApplication.GetInstance(WorkflowInstanceId, store)  
  
            WorkflowVersion.Text = _  
                WorkflowVersionMap.GetIdentityDescription(instance.DefinitionIdentity)  
  
            'Unload the instance.  
            instance.Abandon()  
        End If  
    End Sub  
    ```  
  
    ```csharp  
    private void InstanceId_SelectedIndexChanged(object sender, EventArgs e)  
    {  
        if (InstanceId.SelectedIndex == -1)  
        {  
            return;  
        }  
  
        // Clear the status window.  
        WorkflowStatus.Clear();  
  
        // If there is tracking data for this workflow, display it  
        // in the status window.  
        if (File.Exists(WorkflowInstanceId.ToString()))  
        {  
            string status = File.ReadAllText(WorkflowInstanceId.ToString());  
            UpdateStatus(status);  
        }  
  
        // Get the workflow version and display it.  
        // If the workflow is just starting then this info will not  
        // be available in the persistence store so do not try and retrieve it.  
        if (!WorkflowStarting)  
        {  
            WorkflowApplicationInstance instance =  
                WorkflowApplication.GetInstance(this.WorkflowInstanceId, store);  
  
            WorkflowVersion.Text =  
                WorkflowVersionMap.GetIdentityDescription(instance.DefinitionIdentity);  
  
            // Unload the instance.  
            instance.Abandon();  
        }  
    }  
    ```  
  
###  <span data-ttu-id="677aa-142"><a name="BKMK_BuildAndRun"></a>若要生成并运行应用程序</span><span class="sxs-lookup"><span data-stu-id="677aa-142"><a name="BKMK_BuildAndRun"></a> To build and run the application</span></span>  
  
1.  <span data-ttu-id="677aa-143">按 Ctrl+Shift+B 生成应用程序。</span><span class="sxs-lookup"><span data-stu-id="677aa-143">Press Ctrl+Shift+B to build the application.</span></span>  
  
2.  <span data-ttu-id="677aa-144">按 Ctrl+F5 启动应用程序。</span><span class="sxs-lookup"><span data-stu-id="677aa-144">Press Ctrl+F5 to start the application.</span></span>  
  
3.  <span data-ttu-id="677aa-145">选择猜数游戏和工作流以启动，然后单击的类型的范围**新游戏**。</span><span class="sxs-lookup"><span data-stu-id="677aa-145">Select a range for the guessing game and the type of workflow to start, and click **New Game**.</span></span> <span data-ttu-id="677aa-146">输入猜测值中的**猜测**框中，单击**转**提交该值。</span><span class="sxs-lookup"><span data-stu-id="677aa-146">Enter a guess in the **Guess** box and click **Go** to submit your guess.</span></span> <span data-ttu-id="677aa-147">可以看到，工作流的状态显示在状态窗口中。</span><span class="sxs-lookup"><span data-stu-id="677aa-147">Note that the status of the workflow is displayed in the status window.</span></span> <span data-ttu-id="677aa-148">此输出是从 `WriteLine` 活动捕获的。</span><span class="sxs-lookup"><span data-stu-id="677aa-148">This output is captured from the `WriteLine` activities.</span></span> <span data-ttu-id="677aa-149">切换到不同的工作流选择其中一个从**工作流实例 Id**组合框并记下的当前工作流的状态已删除。</span><span class="sxs-lookup"><span data-stu-id="677aa-149">Switch to a different workflow by selecting one from the **Workflow Instance Id** combo box and note that the status of the current workflow is removed.</span></span> <span data-ttu-id="677aa-150">切换回上一个工作流，可以看到其状态已恢复，与以下示例类似。</span><span class="sxs-lookup"><span data-stu-id="677aa-150">Switch back to the previous workflow and note that the status is restored, similar to the following example.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="677aa-151">如果切换到启用跟踪之前启动的工作流，则不会显示状态。</span><span class="sxs-lookup"><span data-stu-id="677aa-151">If you switch to a workflow that was started before tracking was enabled no status is displayed.</span></span> <span data-ttu-id="677aa-152">但是，如果如果进行了其他猜数，则将保存其状态，因为现在启用了跟踪。</span><span class="sxs-lookup"><span data-stu-id="677aa-152">However if you make additional guesses, their status is saved because tracking is now enabled.</span></span>  
  
 <span data-ttu-id="677aa-153">**请输入介于 1 和 10 之间的数字**</span><span class="sxs-lookup"><span data-stu-id="677aa-153">**Please enter a number between 1 and 10**</span></span>  
<span data-ttu-id="677aa-154">**该值是过高。** </span><span class="sxs-lookup"><span data-stu-id="677aa-154">**Your guess is too high.** </span></span>  
<span data-ttu-id="677aa-155">**请输入介于 1 和 10 之间的数字**</span><span class="sxs-lookup"><span data-stu-id="677aa-155">**Please enter a number between 1 and 10**</span></span>    
    > [!NOTE]
    >  <span data-ttu-id="677aa-156">此信息对于确定随机数的范围十分有用，但它并不包含有关先前进行的猜数的任何信息。</span><span class="sxs-lookup"><span data-stu-id="677aa-156">This information is useful for determining the range of the random number, but it does not contain any information about what guesses have been previously made.</span></span> <span data-ttu-id="677aa-157">此信息，请参阅下一步， [How to： 主机多个版本的工作流通过并行](../../../docs/framework/windows-workflow-foundation/how-to-host-multiple-versions-of-a-workflow-side-by-side.md)。</span><span class="sxs-lookup"><span data-stu-id="677aa-157">This information is in the next step, [How to: Host Multiple Versions of a Workflow Side-by-Side](../../../docs/framework/windows-workflow-foundation/how-to-host-multiple-versions-of-a-workflow-side-by-side.md).</span></span>  
  
     <span data-ttu-id="677aa-158">记下工作流实例 ID，然后播放游戏，直到播完。</span><span class="sxs-lookup"><span data-stu-id="677aa-158">Make a note of the workflow instance id, and play the game through to its completion.</span></span>  
  
4.  <span data-ttu-id="677aa-159">打开 Windows 资源管理器并导航到**NumberGuessWorkflowHost\bin\debug**文件夹 (或**bin\release**具体取决于项目设置)。</span><span class="sxs-lookup"><span data-stu-id="677aa-159">Open Windows Explorer and navigate to the **NumberGuessWorkflowHost\bin\debug** folder (or **bin\release** depending on your project settings).</span></span> <span data-ttu-id="677aa-160">可以看到，除了项目可执行文件之外，还有包含 guid 文件名的文件。</span><span class="sxs-lookup"><span data-stu-id="677aa-160">Note that in addition to the project executable files there are files with guid filenames.</span></span> <span data-ttu-id="677aa-161">确定与上一步中已完成工作流的工作流实例 ID 对应的工作流，然后用记事本打开它。</span><span class="sxs-lookup"><span data-stu-id="677aa-161">Identify the one that corresponds to the workflow instance id from the completed workflow in the previous step and open it in Notepad.</span></span> <span data-ttu-id="677aa-162">跟踪信息所包含的内容类似于以下内容。</span><span class="sxs-lookup"><span data-stu-id="677aa-162">The tracking information contains information similar to the following.</span></span>  
  
 <span data-ttu-id="677aa-163">**请输入介于 1 和 10 之间的数字**</span><span class="sxs-lookup"><span data-stu-id="677aa-163">**Please enter a number between 1 and 10**</span></span>  
<span data-ttu-id="677aa-164">**该值是过高。** </span><span class="sxs-lookup"><span data-stu-id="677aa-164">**Your guess is too high.** </span></span>  
<span data-ttu-id="677aa-165">**请输入介于 1 和 10 之间的数字** </span><span class="sxs-lookup"><span data-stu-id="677aa-165">**Please enter a number between 1 and 10** </span></span>  
<span data-ttu-id="677aa-166">**该值是过高。** </span><span class="sxs-lookup"><span data-stu-id="677aa-166">**Your guess is too high.** </span></span>  
<span data-ttu-id="677aa-167">**请输入介于 1 和 10 之间的大量**除了缺少用户的猜测值，此跟踪数据不包含有关的最终猜数工作流的信息。</span><span class="sxs-lookup"><span data-stu-id="677aa-167">**Please enter a number between 1 and 10**      In addition to the absence of the user's guesses, this tracking data does not contain information about the final guess of the workflow.</span></span> <span data-ttu-id="677aa-168">这是因为，跟踪信息仅包含工作流的 `WriteLine` 输出，而在工作流完成后从 `Completed` 显示的最终消息也是这样的。</span><span class="sxs-lookup"><span data-stu-id="677aa-168">That is because the tracking information consists only of the `WriteLine` output from the workflow, and the final message that is displayed is done so from the `Completed` handler after the workflow completes.</span></span> <span data-ttu-id="677aa-169">在下一步的教程， [How to： 主机多个版本的工作流通过并行](../../../docs/framework/windows-workflow-foundation/how-to-host-multiple-versions-of-a-workflow-side-by-side.md)，现有`WriteLine`活动被修改，以显示用户的猜测和额外`WriteLine`添加活动显示的最终结果。</span><span class="sxs-lookup"><span data-stu-id="677aa-169">In next step of the tutorial, [How to: Host Multiple Versions of a Workflow Side-by-Side](../../../docs/framework/windows-workflow-foundation/how-to-host-multiple-versions-of-a-workflow-side-by-side.md), the existing `WriteLine` activities are modified to display the user's guesses, and an additional `WriteLine` activity is added that displays the final results.</span></span> <span data-ttu-id="677aa-170">集成这些更改后， [How to： 主机多个版本的工作流通过并行](../../../docs/framework/windows-workflow-foundation/how-to-host-multiple-versions-of-a-workflow-side-by-side.md)演示如何同时承载多个版本的工作流。</span><span class="sxs-lookup"><span data-stu-id="677aa-170">After these changes are integrated, [How to: Host Multiple Versions of a Workflow Side-by-Side](../../../docs/framework/windows-workflow-foundation/how-to-host-multiple-versions-of-a-workflow-side-by-side.md) demonstrates how to host multiple versions of a workflow at the same time.</span></span>
