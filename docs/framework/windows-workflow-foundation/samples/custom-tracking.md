---
title: 自定义跟踪
ms.date: 03/30/2017
ms.assetid: 2d191c9f-62f4-4c63-92dd-cda917fcf254
ms.openlocfilehash: 2b100b877bbc8c6d830f09a4a59decffde511511
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182843"
---
# <a name="custom-tracking"></a><span data-ttu-id="2b1bd-102">自定义跟踪</span><span class="sxs-lookup"><span data-stu-id="2b1bd-102">Custom Tracking</span></span>
<span data-ttu-id="2b1bd-103">此示例演示如何创建自定义跟踪参与者并将跟踪数据的内容写入控制台。</span><span class="sxs-lookup"><span data-stu-id="2b1bd-103">This sample demonstrates how to create a custom tracking participant and write the contents of the tracking data to console.</span></span> <span data-ttu-id="2b1bd-104">另外，此示例还演示如何发出使用用户定义的数据填充的 <xref:System.Activities.Tracking.CustomTrackingRecord> 对象。</span><span class="sxs-lookup"><span data-stu-id="2b1bd-104">In addition, the sample demonstrates how to emit <xref:System.Activities.Tracking.CustomTrackingRecord> objects populated with user defined data.</span></span> <span data-ttu-id="2b1bd-105">基于控制台的跟踪参与者将使用代码中创建的跟踪配置文件对象来筛选由工作流发出的 <xref:System.Activities.Tracking.TrackingRecord> 对象。</span><span class="sxs-lookup"><span data-stu-id="2b1bd-105">The console-based tracking participant filters the <xref:System.Activities.Tracking.TrackingRecord> objects emitted by the workflow using a tracking profile object created in code.</span></span>

## <a name="sample-details"></a><span data-ttu-id="2b1bd-106">示例详细信息</span><span class="sxs-lookup"><span data-stu-id="2b1bd-106">Sample Details</span></span>
 <span data-ttu-id="2b1bd-107">Windows 工作流基础 （WF） 提供跟踪基础结构来跟踪工作流实例的执行。</span><span class="sxs-lookup"><span data-stu-id="2b1bd-107">Windows Workflow Foundation (WF) provides a tracking infrastructure to track execution of a workflow instance.</span></span> <span data-ttu-id="2b1bd-108">跟踪运行时实现一个工作流实例，以便发出与工作流生命周期有关的事件、来自工作流活动的事件和自定义跟踪事件。</span><span class="sxs-lookup"><span data-stu-id="2b1bd-108">The tracking runtime implements a workflow instance to emit events related to the workflow lifecycle, events from workflow activities and custom tracking events.</span></span> <span data-ttu-id="2b1bd-109">下表详细介绍了跟踪基础结构的主要组件。</span><span class="sxs-lookup"><span data-stu-id="2b1bd-109">The following table details the primary components of the tracking infrastructure.</span></span>

|<span data-ttu-id="2b1bd-110">组件</span><span class="sxs-lookup"><span data-stu-id="2b1bd-110">Component</span></span>|<span data-ttu-id="2b1bd-111">说明</span><span class="sxs-lookup"><span data-stu-id="2b1bd-111">Description</span></span>|
|---------------|-----------------|
|<span data-ttu-id="2b1bd-112">跟踪运行时</span><span class="sxs-lookup"><span data-stu-id="2b1bd-112">Tracking runtime</span></span>|<span data-ttu-id="2b1bd-113">提供基础结构以发出跟踪记录。</span><span class="sxs-lookup"><span data-stu-id="2b1bd-113">Provides the infrastructure to emit tracking records.</span></span>|
|<span data-ttu-id="2b1bd-114">跟踪参与者</span><span class="sxs-lookup"><span data-stu-id="2b1bd-114">Tracking participants</span></span>|<span data-ttu-id="2b1bd-115">使用跟踪记录。</span><span class="sxs-lookup"><span data-stu-id="2b1bd-115">Consumes the tracking records.</span></span> <span data-ttu-id="2b1bd-116">.NET 框架 4 附带一个跟踪参与者，该跟踪参与者将跟踪记录写入 Windows （ETW） 事件的事件跟踪。</span><span class="sxs-lookup"><span data-stu-id="2b1bd-116">.NET Framework 4 ships with a tracking participant that writes tracking records as Event Tracing for Windows (ETW) events.</span></span>|
|<span data-ttu-id="2b1bd-117">跟踪配置文件</span><span class="sxs-lookup"><span data-stu-id="2b1bd-117">Tracking profile</span></span>|<span data-ttu-id="2b1bd-118">筛选机制，允许跟踪参与者订阅从工作流实例发出的跟踪记录的子集。</span><span class="sxs-lookup"><span data-stu-id="2b1bd-118">A filtering mechanism that allows a tracking participant to subscribe for a subset of the tracking records emitted from a workflow instance.</span></span>|

 <span data-ttu-id="2b1bd-119">下表详细介绍工作流运行时发出的跟踪记录。</span><span class="sxs-lookup"><span data-stu-id="2b1bd-119">The following table details the tracking records that the workflow runtime emits.</span></span>

|<span data-ttu-id="2b1bd-120">跟踪记录</span><span class="sxs-lookup"><span data-stu-id="2b1bd-120">Tracking Record</span></span>|<span data-ttu-id="2b1bd-121">说明</span><span class="sxs-lookup"><span data-stu-id="2b1bd-121">Description</span></span>|
|---------------------|-----------------|
|<span data-ttu-id="2b1bd-122">工作流实例跟踪记录。</span><span class="sxs-lookup"><span data-stu-id="2b1bd-122">Workflow instance tracking records.</span></span>|<span data-ttu-id="2b1bd-123">描述工作流实例的生命周期。</span><span class="sxs-lookup"><span data-stu-id="2b1bd-123">Describes the life cycle of the workflow instance.</span></span> <span data-ttu-id="2b1bd-124">例如，当工作流启动或完成时发出一个实例记录。</span><span class="sxs-lookup"><span data-stu-id="2b1bd-124">For example, an instance record is emitted when the workflow starts or completes.</span></span>|
|<span data-ttu-id="2b1bd-125">活动状态跟踪记录。</span><span class="sxs-lookup"><span data-stu-id="2b1bd-125">Activity state Tracking Records.</span></span>|<span data-ttu-id="2b1bd-126">详细说明活动执行情况。</span><span class="sxs-lookup"><span data-stu-id="2b1bd-126">Details activity execution.</span></span> <span data-ttu-id="2b1bd-127">这些记录指示工作流活动的状态，例如，当安排活动时、活动完成时或引发错误时。</span><span class="sxs-lookup"><span data-stu-id="2b1bd-127">These records indicate the state of a workflow activity such as when an activity is scheduled or when the activity completes or when a fault is thrown.</span></span>|
|<span data-ttu-id="2b1bd-128">书签恢复记录。</span><span class="sxs-lookup"><span data-stu-id="2b1bd-128">Bookmark resumption record.</span></span>|<span data-ttu-id="2b1bd-129">当恢复工作流实例中的书签时发出。</span><span class="sxs-lookup"><span data-stu-id="2b1bd-129">Emitted whenever a bookmark within a workflow instance is resumed.</span></span>|
|<span data-ttu-id="2b1bd-130">自定义跟踪记录。</span><span class="sxs-lookup"><span data-stu-id="2b1bd-130">Custom Tracking Records.</span></span>|<span data-ttu-id="2b1bd-131">工作流作者可以在自定义活动中创建并发出自定义跟踪记录。</span><span class="sxs-lookup"><span data-stu-id="2b1bd-131">A workflow author can create Custom Tracking Records and emit them within the custom activity.</span></span>|

 <span data-ttu-id="2b1bd-132">跟踪参与者使用跟踪配置文件来订阅已发出 <xref:System.Activities.Tracking.TrackingRecord> 对象的子集。</span><span class="sxs-lookup"><span data-stu-id="2b1bd-132">The tracking participant subscribes for a subset of the emitted <xref:System.Activities.Tracking.TrackingRecord> objects using tracking profiles.</span></span> <span data-ttu-id="2b1bd-133">跟踪配置文件包含允许订阅特定跟踪记录类型的跟踪查询。</span><span class="sxs-lookup"><span data-stu-id="2b1bd-133">A tracking profile contains tracking queries that allow subscribing for a particular tracking record type.</span></span> <span data-ttu-id="2b1bd-134">可以在代码或配置中指定跟踪配置文件。</span><span class="sxs-lookup"><span data-stu-id="2b1bd-134">Tracking profiles can be specified in code or in configuration.</span></span>

### <a name="custom-tracking-participant"></a><span data-ttu-id="2b1bd-135">自定义跟踪参与者</span><span class="sxs-lookup"><span data-stu-id="2b1bd-135">Custom Tracking Participant</span></span>
 <span data-ttu-id="2b1bd-136">跟踪参与者 API 允许以用户提供的跟踪参与者扩展跟踪运行时，该用户提供的跟踪参与者可包括用于对工作流运行时发出的 <xref:System.Activities.Tracking.TrackingRecord> 对象进行处理的自定义逻辑。</span><span class="sxs-lookup"><span data-stu-id="2b1bd-136">The tracking participant API allows extension of the tracking runtime with a user provided tracking participant that can include custom logic to handle <xref:System.Activities.Tracking.TrackingRecord> objects emitted by the workflow runtime.</span></span>

 <span data-ttu-id="2b1bd-137">若要编写跟踪参与者，用户必须实现 <xref:System.Activities.Tracking.TrackingParticipant>。</span><span class="sxs-lookup"><span data-stu-id="2b1bd-137">To write a tracking participant the user must implement <xref:System.Activities.Tracking.TrackingParticipant>.</span></span> <span data-ttu-id="2b1bd-138">具体而言，<xref:System.Activities.Tracking.TrackingParticipant.Track%2A> 方法必须由自定义参与者实现。</span><span class="sxs-lookup"><span data-stu-id="2b1bd-138">Specifically, the <xref:System.Activities.Tracking.TrackingParticipant.Track%2A> method has to be implemented by the custom participant.</span></span> <span data-ttu-id="2b1bd-139">此方法在工作流运行时发出 <xref:System.Activities.Tracking.TrackingRecord> 时调用。</span><span class="sxs-lookup"><span data-stu-id="2b1bd-139">This method is called when a <xref:System.Activities.Tracking.TrackingRecord> is emitted by the workflow runtime.</span></span>

```csharp
public abstract class TrackingParticipant
{
    protected TrackingParticipant();

    public virtual TrackingProfile TrackingProfile { get; set; }
    public abstract void Track(TrackingRecord record, TimeSpan timeout);
}
```

 <span data-ttu-id="2b1bd-140">完整的跟踪参与者在ConsoleTrackingParticipant.cs文件中实现。</span><span class="sxs-lookup"><span data-stu-id="2b1bd-140">The complete tracking participant is implemented in the ConsoleTrackingParticipant.cs file.</span></span> <span data-ttu-id="2b1bd-141">以下代码示例是<xref:System.Activities.Tracking.TrackingParticipant.Track%2A>自定义跟踪参与者的方法。</span><span class="sxs-lookup"><span data-stu-id="2b1bd-141">The following code example is the <xref:System.Activities.Tracking.TrackingParticipant.Track%2A> method for the custom tracking participant.</span></span>

```csharp
protected override void Track(TrackingRecord record, TimeSpan timeout)
{
    ...
    WorkflowInstanceRecord workflowInstanceRecord = record as WorkflowInstanceRecord;
    if (workflowInstanceRecord != null)
    {
        Console.WriteLine(String.Format(CultureInfo.InvariantCulture,
            " Workflow InstanceID: {0} Workflow instance state: {1}",
            record.InstanceId, workflowInstanceRecord.State));
    }

    ActivityStateRecord activityStateRecord = record as ActivityStateRecord;
    if (activityStateRecord != null)
    {
        IDictionary<String, object> variables = activityStateRecord.Variables;
        StringBuilder vars = new StringBuilder();

        if (variables.Count > 0)
        {
            vars.AppendLine("\n\tVariables:");
            foreach (KeyValuePair<string, object> variable in variables)
            {
                vars.AppendLine(String.Format(
                    "\t\tName: {0} Value: {1}", variable.Key, variable.Value));
            }
        }
        Console.WriteLine(String.Format(CultureInfo.InvariantCulture,
            " :Activity DisplayName: {0} :ActivityInstanceState: {1} {2}",
                activityStateRecord.Activity.Name, activityStateRecord.State,
            ((variables.Count > 0) ? vars.ToString() : String.Empty)));
    }

    CustomTrackingRecord customTrackingRecord = record as CustomTrackingRecord;

    if ((customTrackingRecord != null) && (customTrackingRecord.Data.Count > 0))
    {
        ...
    }
    Console.WriteLine();

}
```

 <span data-ttu-id="2b1bd-142">下面的代码示例将向工作流调用程序添加控制台参与者。</span><span class="sxs-lookup"><span data-stu-id="2b1bd-142">The following code example adds the console participant to the workflow invoker.</span></span>

```csharp
ConsoleTrackingParticipant customTrackingParticipant = new ConsoleTrackingParticipant()
{
    ...
    // The tracking profile is set here, refer to Program.CS
...
}

WorkflowInvoker invoker = new WorkflowInvoker(BuildSampleWorkflow());
invoker.Extensions.Add(customTrackingParticipant);
```

### <a name="emitting-custom-tracking-records"></a><span data-ttu-id="2b1bd-143">发出自定义跟踪记录</span><span class="sxs-lookup"><span data-stu-id="2b1bd-143">Emitting Custom Tracking Records</span></span>
 <span data-ttu-id="2b1bd-144">此示例还演示从自定义工作流活动发出 <xref:System.Activities.Tracking.CustomTrackingRecord> 对象的功能：</span><span class="sxs-lookup"><span data-stu-id="2b1bd-144">This sample also demonstrates the ability to emit <xref:System.Activities.Tracking.CustomTrackingRecord> objects from a custom workflow activity:</span></span>

- <span data-ttu-id="2b1bd-145">创建 <xref:System.Activities.Tracking.CustomTrackingRecord> 对象，并使用用户定义的数据（此数据必须与记录一起发出）对其进行填充。</span><span class="sxs-lookup"><span data-stu-id="2b1bd-145">The <xref:System.Activities.Tracking.CustomTrackingRecord> objects are created and populated with user-defined data that is desired to be emitted with the record.</span></span>

- <span data-ttu-id="2b1bd-146"><xref:System.Activities.Tracking.CustomTrackingRecord>通过调用 的<xref:System.Activities.ActivityContext>跟踪方法发出 。</span><span class="sxs-lookup"><span data-stu-id="2b1bd-146">The <xref:System.Activities.Tracking.CustomTrackingRecord> is emitted by calling the track method of the <xref:System.Activities.ActivityContext>.</span></span>

 <span data-ttu-id="2b1bd-147">下面的示例演示如何发出自定义活动内的 <xref:System.Activities.Tracking.CustomTrackingRecord> 对象。</span><span class="sxs-lookup"><span data-stu-id="2b1bd-147">The following example demonstrates how to emit <xref:System.Activities.Tracking.CustomTrackingRecord> objects within a custom activity.</span></span>

```csharp
// Create the Custom Tracking Record
CustomTrackingRecord customRecord = new CustomTrackingRecord("OrderIn")
{
    Data =
    {
        {"OrderId", 200},
        {"OrderDate", "20 Aug 2001"}
    }
};

// Emit custom tracking record
context.Track(customRecord);
```

#### <a name="to-use-this-sample"></a><span data-ttu-id="2b1bd-148">使用此示例</span><span class="sxs-lookup"><span data-stu-id="2b1bd-148">To use this sample</span></span>

1. <span data-ttu-id="2b1bd-149">使用 Visual Studio 2010，打开自定义跟踪采样.sln 解决方案文件。</span><span class="sxs-lookup"><span data-stu-id="2b1bd-149">Using Visual Studio 2010, open the CustomTrackingSample.sln solution file.</span></span>

2. <span data-ttu-id="2b1bd-150">要生成解决方案，按 Ctrl+Shift+B。</span><span class="sxs-lookup"><span data-stu-id="2b1bd-150">To build the solution, press CTRL+SHIFT+B.</span></span>

3. <span data-ttu-id="2b1bd-151">若要运行解决方案，请按 Ctrl+F5。</span><span class="sxs-lookup"><span data-stu-id="2b1bd-151">To run the solution, press CTRL+F5.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2b1bd-152">您的计算机上可能已安装这些示例。</span><span class="sxs-lookup"><span data-stu-id="2b1bd-152">The samples may already be installed on your computer.</span></span> <span data-ttu-id="2b1bd-153">在继续操作之前，请先检查以下（默认）目录：</span><span class="sxs-lookup"><span data-stu-id="2b1bd-153">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="2b1bd-154">如果此目录不存在，请转到[Windows 通信基础 （WCF） 和 Windows 工作流基础 （WF） 示例 .NET 框架 4](https://www.microsoft.com/download/details.aspx?id=21459)以下载[!INCLUDE[wf1](../../../../includes/wf1-md.md)]所有 Windows 通信基础 （WCF） 和示例。</span><span class="sxs-lookup"><span data-stu-id="2b1bd-154">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="2b1bd-155">此示例位于以下目录：</span><span class="sxs-lookup"><span data-stu-id="2b1bd-155">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Tracking\CustomTracking`  
  
## <a name="see-also"></a><span data-ttu-id="2b1bd-156">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2b1bd-156">See also</span></span>

- <span data-ttu-id="2b1bd-157">[AppFabric 监视示例](https://docs.microsoft.com/previous-versions/appfabric/ff383407(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="2b1bd-157">[AppFabric Monitoring Samples](https://docs.microsoft.com/previous-versions/appfabric/ff383407(v=azure.10))</span></span>
