---
title: "使用跟踪提取 WF 数据"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e30c68f5-8c6a-495a-bd20-667a4364c68e
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 4d6c269dc9c8b5a0050cfc3ffcefc3160b07c897
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="extract-wf-data-using-tracking"></a><span data-ttu-id="c4815-102">使用跟踪提取 WF 数据</span><span class="sxs-lookup"><span data-stu-id="c4815-102">Extract WF Data using Tracking</span></span>
<span data-ttu-id="c4815-103">此示例演示如何使用工作流跟踪从活动中提取工作流变量和自变量。</span><span class="sxs-lookup"><span data-stu-id="c4815-103">This sample demonstrates how to use workflow tracking to extract workflow variables and arguments from activities.</span></span> <span data-ttu-id="c4815-104">它还演示如何为跟踪记录添加批注以及如何从自定义跟踪记录中提取数据负载。</span><span class="sxs-lookup"><span data-stu-id="c4815-104">It also shows the addition of annotations to tracking records and the extraction of data payload within custom tracking records.</span></span> <span data-ttu-id="c4815-105">此示例使用 Windows 事件跟踪 (ETW) 跟踪参与者来提取工作流中的数据。</span><span class="sxs-lookup"><span data-stu-id="c4815-105">The sample uses the Event Tracing for Windows (ETW) tracking participant to extract data from the workflow.</span></span>  
  
## <a name="sample-details"></a><span data-ttu-id="c4815-106">示例详细信息</span><span class="sxs-lookup"><span data-stu-id="c4815-106">Sample Details</span></span>  
 [!INCLUDE[wf](../../../../includes/wf-md.md)]<span data-ttu-id="c4815-107"> 提供跟踪以查看工作流实例的执行情况。</span><span class="sxs-lookup"><span data-stu-id="c4815-107"> provides tracking to gain visibility into the execution of a workflow instance.</span></span> <span data-ttu-id="c4815-108">跟踪运行时在工作流执行过程中会发出工作流跟踪记录。</span><span class="sxs-lookup"><span data-stu-id="c4815-108">The tracking runtime emits workflow tracking records during the execution of the workflow.</span></span> <span data-ttu-id="c4815-109">除工作流跟踪记录以外，还可以从工作流提取工作流实例中的数据。</span><span class="sxs-lookup"><span data-stu-id="c4815-109">Along with the workflow tracking records, data within the workflow instance can be extracted from the workflow.</span></span> <span data-ttu-id="c4815-110">下面的列表详述了可从跟踪记录中提取的数据的类型：</span><span class="sxs-lookup"><span data-stu-id="c4815-110">The following list details the types of data that can be extracted from tracking records:</span></span>  
  
1.  <span data-ttu-id="c4815-111">活动中的工作流变量和活动执行过程中的跟踪记录。</span><span class="sxs-lookup"><span data-stu-id="c4815-111">Workflow variables within an activity and tracking records during activity execution.</span></span>  
  
     <span data-ttu-id="c4815-112">为了提取工作流变量，将在一个配置文件中指定要提取的变量。</span><span class="sxs-lookup"><span data-stu-id="c4815-112">To extract workflow variables, the variables to be extracted are specified in a profile.</span></span> <span data-ttu-id="c4815-113">只能使用 `ActivityStateQueries` 来指定要提取的变量。</span><span class="sxs-lookup"><span data-stu-id="c4815-113">Variables to be extracted can only be specified with `ActivityStateQueries`.</span></span> <span data-ttu-id="c4815-114">下面的代码示例演示用于从活动中提取工作流变量的跟踪配置文件。</span><span class="sxs-lookup"><span data-stu-id="c4815-114">The following code example demonstrates a tracking profile used to extract the workflow variable from an activity.</span></span>  
  
    ```xml  
    <activityStateQuery activityName="StockPriceService">  
         <states>  
              <state name="Closed"/>  
         </states>  
         <variables>  
              <variable name="symbol"/>  
         </variables>  
    </activityStateQuery>  
    ```  
  
2.  <span data-ttu-id="c4815-115">活动参数和活动状态跟踪记录。</span><span class="sxs-lookup"><span data-stu-id="c4815-115">Activity arguments and activity state tracking records.</span></span>  
  
     <span data-ttu-id="c4815-116">参数可定义数据流入或流出活动的方式。</span><span class="sxs-lookup"><span data-stu-id="c4815-116">Arguments define the way data flows in or out of an activity.</span></span> <span data-ttu-id="c4815-117">使用 <xref:System.Activities.Tracking.ActivityStateQuery> 来指定要提取的参数。下面的代码示例是一个提取 `Value` 参数的跟踪配置文件。</span><span class="sxs-lookup"><span data-stu-id="c4815-117">Arguments to be extracted are specified using an <xref:System.Activities.Tracking.ActivityStateQuery>.The following code example is a tracking profile that extracts the `Value` argument.</span></span>  
  
    ```xml  
    <activityStateQuery activityName="GetStockPrice">  
         <states>  
              <state name="Closed"/>  
         </states>  
         <arguments>  
              <argument name="Value"/>  
         </arguments>  
    </activityStateQuery>  
    ```  
  
3.  <span data-ttu-id="c4815-118">批注是可添加到发出的任何跟踪记录的键/值对。</span><span class="sxs-lookup"><span data-stu-id="c4815-118">Annotations are key/value pairs that can be added to any tracking record that is emitted.</span></span>  
  
     <span data-ttu-id="c4815-119">批注用作跟踪记录的标记机制。</span><span class="sxs-lookup"><span data-stu-id="c4815-119">Annotations serve as a tagging mechanism for tracking records.</span></span> <span data-ttu-id="c4815-120">通过跟踪配置文件将批注添加到跟踪记录中。</span><span class="sxs-lookup"><span data-stu-id="c4815-120">Annotations are added to tracking records through a tracking profile.</span></span> <span data-ttu-id="c4815-121">可将批注添加到任何类型的工作流跟踪查询中。</span><span class="sxs-lookup"><span data-stu-id="c4815-121">Annotations can be added to any type of a workflow tracking query.</span></span> <span data-ttu-id="c4815-122">下面的代码示例是一个跟踪配置文件，它演示如何将批注添加到跟踪记录中。</span><span class="sxs-lookup"><span data-stu-id="c4815-122">The following code example is a tracking profile that shows how an annotation can be added to a tracking record.</span></span>  
  
    ```xml  
    <workflowInstanceQuery>  
         <states>  
              <state name="Started"/>  
         </states>  
         <annotations>  
              <annotation name="StockPriceWorkflow" value="Begin"/>  
         </annotations>  
    </workflowInstanceQuery>  
    ```  
  
4.  <span data-ttu-id="c4815-123">从用户定义的活动发出自定义跟踪记录。</span><span class="sxs-lookup"><span data-stu-id="c4815-123">Custom tracking records are emitted from user-defined activities.</span></span>  
  
     <span data-ttu-id="c4815-124">自定义跟踪记录可包含此活动中定义的负载数据。</span><span class="sxs-lookup"><span data-stu-id="c4815-124">Custom tracking records can carry payload data defined within this activity.</span></span> <span data-ttu-id="c4815-125">通过订阅跟踪配置文件中的自定义跟踪记录，可从跟踪记录中提取负载。</span><span class="sxs-lookup"><span data-stu-id="c4815-125">Subscribing for custom tracking records in a tracking profile allows the extraction of the payload within the tracking record.</span></span> <span data-ttu-id="c4815-126">可使用自定义 <xref:System.Activities.Tracking.TrackingQuery> 来提取自定义跟踪记录。</span><span class="sxs-lookup"><span data-stu-id="c4815-126">The custom tracking records can be extracted with custom a <xref:System.Activities.Tracking.TrackingQuery>.</span></span> <span data-ttu-id="c4815-127">下面的代码示例是一个跟踪配置文件，它将提取自定义跟踪记录及其负载。</span><span class="sxs-lookup"><span data-stu-id="c4815-127">The following code example is a tracking profile that extracts a custom tracking record along with its payload.</span></span>  
  
    ```xml  
    <customTrackingQuery name="QuoteLookupEvent" activityName="GetStockPrice"/>  
    ```  
  
 <span data-ttu-id="c4815-128">此示例演示如何使用 Web.config 中指定的配置文件来提取变量、参数和自定义记录，以及添加批注。通过添加 `<etwTracking>` 行为元素对示例工作流服务启用跟踪。</span><span class="sxs-lookup"><span data-stu-id="c4815-128">The sample demonstrates the extraction of a variables, arguments, custom records and adding annotations using a profile specified in a Web.config. Tracking is enabled on the sample workflow service by adding an `<etwTracking>` behavior element.</span></span> <span data-ttu-id="c4815-129">下面的代码示例为 `ExtractWorkflowVariables` 跟踪配置文件启用了跟踪。</span><span class="sxs-lookup"><span data-stu-id="c4815-129">The following code example enables tracking for the `ExtractWorkflowVariables` tracking profile.</span></span>  
  
```xml  
<serviceBehaviors>  
     <behavior>  
               <etwTracking profileName="ExtractWorkflowVariables"/>  
     </behavior>  
</serviceBehaviors>  
```  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="c4815-130">使用此示例</span><span class="sxs-lookup"><span data-stu-id="c4815-130">To use this sample</span></span>  
  
1.  <span data-ttu-id="c4815-131">使用 [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] 打开 WFStockPriceApplication.sln 解决方案文件。</span><span class="sxs-lookup"><span data-stu-id="c4815-131">Using [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], open the WFStockPriceApplication.sln solution file.</span></span>  
  
2.  <span data-ttu-id="c4815-132">要生成解决方案，按 Ctrl+Shift+B。</span><span class="sxs-lookup"><span data-stu-id="c4815-132">To build the solution, press CTRL+SHIFT+B.</span></span>  
  
3.  <span data-ttu-id="c4815-133">若要运行解决方案，请按 F5。</span><span class="sxs-lookup"><span data-stu-id="c4815-133">To run the solution, press F5.</span></span>  
  
     <span data-ttu-id="c4815-134">浏览器窗口打开和显示侦听应用程序的目录。</span><span class="sxs-lookup"><span data-stu-id="c4815-134">The browser window opens and shows the directory listing for the application.</span></span>  
  
4.  <span data-ttu-id="c4815-135">在浏览器中，单击 StockPriceService.xamlx。</span><span class="sxs-lookup"><span data-stu-id="c4815-135">In the browser, click StockPriceService.xamlx.</span></span>  
  
5.  <span data-ttu-id="c4815-136">浏览器显示 StockPriceService 页，其中包含本地服务 WSDL 地址。</span><span class="sxs-lookup"><span data-stu-id="c4815-136">The browser displays the StockPriceService page, which contains the local service WSDL address.</span></span> <span data-ttu-id="c4815-137">复制此地址。</span><span class="sxs-lookup"><span data-stu-id="c4815-137">Copy this address.</span></span>  
  
     <span data-ttu-id="c4815-138">下面的示例演示本地服务 WSDL 地址。</span><span class="sxs-lookup"><span data-stu-id="c4815-138">The following example shows a local service WSDL address.</span></span> `http://localhost:53797/StockPriceService.xamlx?wsdl`  
  
6.  <span data-ttu-id="c4815-139">在调用服务之前，请启动事件查看器并确保事件日志正在侦听从工作流服务发出的跟踪事件。</span><span class="sxs-lookup"><span data-stu-id="c4815-139">Before invoking the service, start Event Viewer and ensure that the event log is listening for tracking events emitted from the workflow service.</span></span>  
  
7.  <span data-ttu-id="c4815-140">从**启动**菜单上，选择**管理工具**然后**事件查看器**。</span><span class="sxs-lookup"><span data-stu-id="c4815-140">From the **Start** menu, select **Administrative Tools** and then **Event Viewer**.</span></span>  
  
8.  <span data-ttu-id="c4815-141">在事件查看器中的树视图中，导航到**事件查看器**， **Applications and Services Logs**，和**Microsoft**。</span><span class="sxs-lookup"><span data-stu-id="c4815-141">In the tree view in Event Viewer, navigate to **Event Viewer**, **Applications and Services Logs**, and **Microsoft**.</span></span> <span data-ttu-id="c4815-142">右键单击**Microsoft**和选择**视图**然后**显示分析和调试日志**。</span><span class="sxs-lookup"><span data-stu-id="c4815-142">Right-click **Microsoft** and select **View** and then **Show Analytic and Debug Logs**.</span></span>  
  
     <span data-ttu-id="c4815-143">确保**显示分析和调试日志**选项处于选中状态。</span><span class="sxs-lookup"><span data-stu-id="c4815-143">Ensure that the **Show Analytic and Debug Logs** option is checked.</span></span>  
  
9. <span data-ttu-id="c4815-144">在事件查看器中的树视图中，导航到**事件查看器**， **Applications and Services Logs**， **Microsoft**， **Windows**， **应用程序服务器-应用程序**。</span><span class="sxs-lookup"><span data-stu-id="c4815-144">In the tree view in Event Viewer, navigate to **Event Viewer**, **Applications and Services Logs**, **Microsoft**, **Windows**, **Application Server-Applications**.</span></span> <span data-ttu-id="c4815-145">右键单击**分析**和选择**启用日志**。</span><span class="sxs-lookup"><span data-stu-id="c4815-145">Right-click **Analytic** and select **Enable Log**.</span></span>  
  
10. <span data-ttu-id="c4815-146">使用 [!INCLUDE[fileExplorer](../../../../includes/fileexplorer-md.md)]，打开 WCF 测试客户端。</span><span class="sxs-lookup"><span data-stu-id="c4815-146">Using [!INCLUDE[fileExplorer](../../../../includes/fileexplorer-md.md)], open the WCF test client.</span></span>  
  
     <span data-ttu-id="c4815-147">WCF 测试客户端 (WcfTestClient.exe) 位于\<[!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]安装文件夹 > \Common7\IDE\ 文件夹。</span><span class="sxs-lookup"><span data-stu-id="c4815-147">The WCF test client (WcfTestClient.exe) is located in the \<[!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] installation folder>\Common7\IDE\ folder.</span></span>  
  
     <span data-ttu-id="c4815-148">默认的 [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] 安装文件夹为 C:\Program Files\Microsoft Visual Studio 10.0。</span><span class="sxs-lookup"><span data-stu-id="c4815-148">The default [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] installation folder is C:\Program Files\Microsoft Visual Studio 10.0.</span></span>  
  
11. <span data-ttu-id="c4815-149">在 WCF 测试客户端，选择**添加服务**从**文件**菜单。</span><span class="sxs-lookup"><span data-stu-id="c4815-149">In WCF test client, select **Add Service** from the **File** menu.</span></span>  
  
     <span data-ttu-id="c4815-150">在输入框中添加您先前复制的本地服务 WSDL 地址。</span><span class="sxs-lookup"><span data-stu-id="c4815-150">Add the local service WSDL address you copied earlier in the input box.</span></span>  
  
12. <span data-ttu-id="c4815-151">在 WCF 测试客户端中，双击 `GetStockPrice`。</span><span class="sxs-lookup"><span data-stu-id="c4815-151">In WCF test client, double-click `GetStockPrice`.</span></span>  
  
     <span data-ttu-id="c4815-152">这会打开 `GetStockPrice` 方法。</span><span class="sxs-lookup"><span data-stu-id="c4815-152">This opens the `GetStockPrice` method.</span></span> <span data-ttu-id="c4815-153">此请求会接受一个参数。</span><span class="sxs-lookup"><span data-stu-id="c4815-153">The request accepts one parameter.</span></span> <span data-ttu-id="c4815-154">使用值**Contoso**。</span><span class="sxs-lookup"><span data-stu-id="c4815-154">Use the value **Contoso**.</span></span>  
  
13. <span data-ttu-id="c4815-155">单击**调用**。</span><span class="sxs-lookup"><span data-stu-id="c4815-155">Click **Invoke**.</span></span>  
  
14. <span data-ttu-id="c4815-156">切换回事件查看器并导航到**事件查看器**， **Applications and Services Logs**， **Microsoft**， **Windows**， **应用程序服务器-应用程序**。</span><span class="sxs-lookup"><span data-stu-id="c4815-156">Switch back to Event Viewer and navigate to **Event Viewer**, **Applications and Services Logs**, **Microsoft**, **Windows**, **Application Server-Applications**.</span></span> <span data-ttu-id="c4815-157">右键单击**分析**和选择**刷新**。</span><span class="sxs-lookup"><span data-stu-id="c4815-157">Right-click **Analytic** and select **Refresh**.</span></span> <span data-ttu-id="c4815-158">工作流事件的事件 ID 位于 100-199 范围内。</span><span class="sxs-lookup"><span data-stu-id="c4815-158">The workflow events are in the event ID ranges 100-199.</span></span>  
  
     <span data-ttu-id="c4815-159">事件包含批注、变量、参数和自定义跟踪记录，可在事件查看器中查看这些内容。</span><span class="sxs-lookup"><span data-stu-id="c4815-159">The events contain the annotations, variables, arguments and custom tracking records that can be viewed in the event viewer.</span></span>  
  
## <a name="cleaning-up-in-the-event-viewer"></a><span data-ttu-id="c4815-160">清除事件查看器中的内容</span><span class="sxs-lookup"><span data-stu-id="c4815-160">Cleaning up in the Event Viewer</span></span>  
 <span data-ttu-id="c4815-161">通过执行以下操作，可在事件查看器中清除事件日志中的分析通道。</span><span class="sxs-lookup"><span data-stu-id="c4815-161">The analytic channel in the event log can be cleaned up in the Event Viewer by doing the following.</span></span>  
  
#### <a name="to-clean-up-optional"></a><span data-ttu-id="c4815-162">清理（可选）</span><span class="sxs-lookup"><span data-stu-id="c4815-162">To clean up (Optional)</span></span>  
  
1.  <span data-ttu-id="c4815-163">打开事件查看器。</span><span class="sxs-lookup"><span data-stu-id="c4815-163">Open Event Viewer.</span></span>  
  
2.  <span data-ttu-id="c4815-164">导航到**事件查看器**， **Applications and Services Logs**， **Microsoft**， **Windows**，**应用程序服务器应用程序**。</span><span class="sxs-lookup"><span data-stu-id="c4815-164">Navigate to **Event Viewer**, **Applications and Services Logs**, **Microsoft**, **Windows**, **Application Server-Applications**.</span></span> <span data-ttu-id="c4815-165">右键单击**分析**和选择**禁用日志**。</span><span class="sxs-lookup"><span data-stu-id="c4815-165">Right-click **Analytic** and select **Disable Log**.</span></span>  
  
3.  <span data-ttu-id="c4815-166">导航到**事件查看器**， **Applications and Services Logs**， **Microsoft**， **Windows**，**应用程序服务器应用程序**。</span><span class="sxs-lookup"><span data-stu-id="c4815-166">Navigate to **Event Viewer**, **Applications and Services Logs**, **Microsoft**, **Windows**, **Application Server-Applications**.</span></span> <span data-ttu-id="c4815-167">右键单击**分析**和选择**清除日志**。</span><span class="sxs-lookup"><span data-stu-id="c4815-167">Right-click **Analytic** and select **Clear Log**.</span></span>  
  
     <span data-ttu-id="c4815-168">选择**清除**选项以清除事件。</span><span class="sxs-lookup"><span data-stu-id="c4815-168">Choose the **Clear** option to clear the events.</span></span>  
  
## <a name="known-issue"></a><span data-ttu-id="c4815-169">已知问题</span><span class="sxs-lookup"><span data-stu-id="c4815-169">Known Issue</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c4815-170">事件查看器中存在一个已知问题，即可能无法解码 ETW 事件。</span><span class="sxs-lookup"><span data-stu-id="c4815-170">There is a known issue in the Event Viewer where it may fail to decode ETW events.</span></span> <span data-ttu-id="c4815-171">您可能会看到与下面类似的错误消息。</span><span class="sxs-lookup"><span data-stu-id="c4815-171">You may see an error message that looks like the following.</span></span>  
>   
>  `The description for Event ID <id> from source Microsoft-Windows-Application Server-Applications cannot be found. Either the component that raises this event is not installed on your local computer or the installation is corrupted. You can install or repair the component on the local computer.`  
>   
>  <span data-ttu-id="c4815-172">如果你遇到此错误，请单击**刷新**在操作窗格中。</span><span class="sxs-lookup"><span data-stu-id="c4815-172">If you encounter this error, click **Refresh** in the actions pane.</span></span> <span data-ttu-id="c4815-173">事件现在应能正确解码。</span><span class="sxs-lookup"><span data-stu-id="c4815-173">The event should now decode properly.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="c4815-174">您的计算机上可能已安装这些示例。</span><span class="sxs-lookup"><span data-stu-id="c4815-174">The samples may already be installed on your computer.</span></span> <span data-ttu-id="c4815-175">在继续操作之前，请先检查以下（默认）目录：</span><span class="sxs-lookup"><span data-stu-id="c4815-175">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="c4815-176">如果此目录不存在，请访问 [针对 .NET Framework 4 的 Windows Communication Foundation (WCF) 和 Windows Workflow Foundation (WF) 示例](http://go.microsoft.com/fwlink/?LinkId=150780) 以下载所有 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 和 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 示例。</span><span class="sxs-lookup"><span data-stu-id="c4815-176">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="c4815-177">此示例位于以下目录：</span><span class="sxs-lookup"><span data-stu-id="c4815-177">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Tracking\ExtractWfData`  
  
## <a name="see-also"></a><span data-ttu-id="c4815-178">请参阅</span><span class="sxs-lookup"><span data-stu-id="c4815-178">See Also</span></span>  
 [<span data-ttu-id="c4815-179">AppFabric 监视示例</span><span class="sxs-lookup"><span data-stu-id="c4815-179">AppFabric Monitoring Samples</span></span>](http://go.microsoft.com/fwlink/?LinkId=193959)
