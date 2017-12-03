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
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 4818b43c447dbe279a67f372dc846b3b07ecd998
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2017
---
# <a name="how-to-create-a-custom-tracking-participant"></a>如何：创建自定义跟踪参与者
工作流跟踪用于查看工作流执行的状态。 工作流运行时发出跟踪记录，这些跟踪记录描述工作流生命周期事件、活动生命周期事件、书签摘要和故障。 这些跟踪记录供跟踪参与者使用。 [!INCLUDE[wf](../../../includes/wf-md.md)] 包括一个标准跟踪参与者，可将跟踪记录作为 Windows 事件跟踪 (ETW) 事件写入。 如果这不能满足您的要求，您还可以编写自定义跟踪参与者。 本教程步骤说明如何创建自定义跟踪参与者和跟踪配置文件，该配置文件捕获 `WriteLine` 活动的输出，以便将这些活动显示给用户。  
  
> [!NOTE]
>  入门教程中的每个主题都依赖于前面的主题。 若要完成本主题，必须先完成前面的主题。 若要下载完整的版本或观看教程视频演练，请参阅[Windows Workflow Foundation (WF45)-入门教程](http://go.microsoft.com/fwlink/?LinkID=248976)。  
  
## <a name="in-this-topic"></a>主题内容  
  
-   [若要创建自定义跟踪参与者](../../../docs/framework/windows-workflow-foundation/how-to-create-a-custom-tracking-participant.md#BKMK_CustomTrackingParticipant)  
  
-   [创建跟踪配置文件并注册跟踪参与者](../../../docs/framework/windows-workflow-foundation/how-to-create-a-custom-tracking-participant.md#BKMK_TrackingProfile)  
  
-   [若要显示的跟踪信息](../../../docs/framework/windows-workflow-foundation/how-to-create-a-custom-tracking-participant.md#BKMK_DisplayTracking)  
  
-   [若要生成并运行应用程序](../../../docs/framework/windows-workflow-foundation/how-to-create-a-custom-tracking-participant.md#BKMK_BuildAndRun)  
  
###  <a name="BKMK_CustomTrackingParticipant"></a>若要创建自定义跟踪参与者  
  
1.  右键单击**NumberGuessWorkflowHost**中**解决方案资源管理器**选择**添加**，**类**。 类型`StatusTrackingParticipant`到**名称**框中，然后单击**添加**。  
  
2.  在包含其他 `using`（或 `Imports`）语句的文件的顶部添加以下 `using`（或 `Imports`）语句。  
  
    ```vb  
    Imports System.Activities.Tracking  
    Imports System.IO  
    ```  
  
    ```csharp  
    using System.Activities.Tracking;  
    using System.IO;  
    ```  
  
3.  修改 `StatusTrackingParticipant` 类，使它从 `TrackingParticipant` 继承。  
  
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
  
4.  添加以下 `Track` 方法重写。 有多种不同类型的跟踪记录。 我们对 `WriteLine` 活动的输出十分感兴趣，这些活动包含在活动跟踪记录中。 如果 `TrackingRecord` 为 `ActivityTrackingRecord` 活动的 `WriteLine`，则 `Text` 的 `WriteLine` 将附加到工作流 `InstanceId` 后面的指定文件。 在本教程中，该文件将保存到宿主应用程序的当前文件夹中。  
  
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
  
     未指定跟踪配置文件时，使用默认跟踪配置文件。 使用默认跟踪配置文件时，将为所有 `ActivityStates` 发出跟踪记录。 因为我们只需在 `WriteLine` 活动的生命周期内捕获一次文本，所以我们仅从 `ActivityStates.Executing` 状态捕获文本。 在[创建跟踪配置文件并注册跟踪参与者](../../../docs/framework/windows-workflow-foundation/how-to-create-a-custom-tracking-participant.md#BKMK_TrackingProfile)，跟踪配置文件会创建一个仅指定`WriteLine``ActivityStates.Executing`发出跟踪记录。  
  
###  <a name="BKMK_TrackingProfile"></a>创建跟踪配置文件并注册跟踪参与者  
  
1.  右键单击**WorkflowHostForm**中**解决方案资源管理器**选择**查看代码**。  
  
2.  在包含其他 `using`（或 `Imports`）语句的文件的顶部添加以下 `using`（或 `Imports`）语句。  
  
    ```vb  
    Imports System.Activities.Tracking  
    ```  
  
    ```csharp  
    using System.Activities.Tracking;  
    ```  
  
3.  将以下代码添加到 `ConfigureWorkflowApplication`，紧接在将 `StringWriter` 添加到工作流扩展的代码之后和工作流生命周期处理程序之前。  
  
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
  
     此跟踪配置文件指定仅向自定义跟踪参与者发出处于 `WriteLine` 状态的 `Executing` 活动的活动状态记录。  
  
     在添加代码后，`ConfigureWorkflowApplication` 的开头将类似于以下示例。  
  
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
  
###  <a name="BKMK_DisplayTracking"></a>若要显示的跟踪信息  
  
1.  右键单击**WorkflowHostForm**中**解决方案资源管理器**选择**查看代码**。  
  
2.  在 `InstanceId_SelectedIndexChanged` 处理程序中，添加以下代码，紧接在清除状态窗口的代码之后。  
  
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
  
     在工作流列表中选择新工作流后，将加载该工作流的跟踪记录并将其显示在状态窗口中。 以下示例是完成的 `InstanceId_SelectedIndexChanged` 处理程序。  
  
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
  
###  <a name="BKMK_BuildAndRun"></a>若要生成并运行应用程序  
  
1.  按 Ctrl+Shift+B 生成应用程序。  
  
2.  按 Ctrl+F5 启动应用程序。  
  
3.  选择猜数游戏和工作流以启动，然后单击的类型的范围**新游戏**。 输入猜测值中的**猜测**框中，单击**转**提交该值。 可以看到，工作流的状态显示在状态窗口中。 此输出是从 `WriteLine` 活动捕获的。 切换到不同的工作流选择其中一个从**工作流实例 Id**组合框并记下的当前工作流的状态已删除。 切换回上一个工作流，可以看到其状态已恢复，与以下示例类似。  
  
    > [!NOTE]
    >  如果切换到启用跟踪之前启动的工作流，则不会显示状态。 但是，如果如果进行了其他猜数，则将保存其状态，因为现在启用了跟踪。  
  
 **请输入介于 1 和 10 之间的数字**  
**该值是过高。**   
**请输入介于 1 和 10 之间的数字**    
    > [!NOTE]
    >  此信息对于确定随机数的范围十分有用，但它并不包含有关先前进行的猜数的任何信息。 此信息，请参阅下一步， [How to： 主机多个版本的工作流通过并行](../../../docs/framework/windows-workflow-foundation/how-to-host-multiple-versions-of-a-workflow-side-by-side.md)。  
  
     记下工作流实例 ID，然后播放游戏，直到播完。  
  
4.  打开 Windows 资源管理器并导航到**NumberGuessWorkflowHost\bin\debug**文件夹 (或**bin\release**具体取决于项目设置)。 可以看到，除了项目可执行文件之外，还有包含 guid 文件名的文件。 确定与上一步中已完成工作流的工作流实例 ID 对应的工作流，然后用记事本打开它。 跟踪信息所包含的内容类似于以下内容。  
  
 **请输入介于 1 和 10 之间的数字**  
**该值是过高。**   
**请输入介于 1 和 10 之间的数字**   
**该值是过高。**   
**请输入介于 1 和 10 之间的大量**除了缺少用户的猜测值，此跟踪数据不包含有关的最终猜数工作流的信息。 这是因为，跟踪信息仅包含工作流的 `WriteLine` 输出，而在工作流完成后从 `Completed` 显示的最终消息也是这样的。 在下一步的教程， [How to： 主机多个版本的工作流通过并行](../../../docs/framework/windows-workflow-foundation/how-to-host-multiple-versions-of-a-workflow-side-by-side.md)，现有`WriteLine`活动被修改，以显示用户的猜测和额外`WriteLine`添加活动显示的最终结果。 集成这些更改后， [How to： 主机多个版本的工作流通过并行](../../../docs/framework/windows-workflow-foundation/how-to-host-multiple-versions-of-a-workflow-side-by-side.md)演示如何同时承载多个版本的工作流。
