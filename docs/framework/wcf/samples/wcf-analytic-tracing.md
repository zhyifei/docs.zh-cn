---
title: WCF 分析跟踪
ms.date: 03/30/2017
ms.assetid: 6029c7c7-3515-4d36-9d43-13e8f4971790
ms.openlocfilehash: e13aa0f7d0dbc48bedad0a9c639695ed038b9303
ms.sourcegitcommit: 15109844229ade1c6449f48f3834db1b26907824
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2018
---
# <a name="wcf-analytic-tracing"></a><span data-ttu-id="f21e5-102">WCF 分析跟踪</span><span class="sxs-lookup"><span data-stu-id="f21e5-102">WCF Analytic Tracing</span></span>
<span data-ttu-id="f21e5-103">此示例演示如何将您自己的跟踪事件添加到 Windows Communication Foundation (WCF) 将写入到 ETW 中的分析跟踪流[!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="f21e5-103">This sample demonstrates how to add your own tracing events into the stream of analytic traces that Windows Communication Foundation (WCF) writes to ETW in [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)].</span></span> <span data-ttu-id="f21e5-104">跟踪分析是为了便于查看服务，而不会导致较高性能损失。</span><span class="sxs-lookup"><span data-stu-id="f21e5-104">Analytic traces are meant to make it easy to get visibility into your services without paying a high performance penalty.</span></span> <span data-ttu-id="f21e5-105">此示例演示如何使用<xref:System.Diagnostics.Eventing?displayProperty=nameWithType>Api 与 WCF 服务集成的写入事件。</span><span class="sxs-lookup"><span data-stu-id="f21e5-105">This sample shows how to use the <xref:System.Diagnostics.Eventing?displayProperty=nameWithType> APIs to write events that integrate with WCF services.</span></span>  
  
 <span data-ttu-id="f21e5-106">有关详细信息<xref:System.Diagnostics.Eventing?displayProperty=nameWithType>Api，请参阅<xref:System.Diagnostics.Eventing?displayProperty=nameWithType>。</span><span class="sxs-lookup"><span data-stu-id="f21e5-106">For more information about the <xref:System.Diagnostics.Eventing?displayProperty=nameWithType> APIs, see <xref:System.Diagnostics.Eventing?displayProperty=nameWithType>.</span></span>  
  
 <span data-ttu-id="f21e5-107">若要了解有关 Windows 中的事件跟踪的详细信息，请参阅[改进调试和性能优化使用 ETW](http://go.microsoft.com/fwlink/?LinkId=166488)。</span><span class="sxs-lookup"><span data-stu-id="f21e5-107">To learn more about event tracing in Windows, see [Improve Debugging and Performance Tuning with ETW](http://go.microsoft.com/fwlink/?LinkId=166488).</span></span>  
  
## <a name="disposing-eventprovider"></a><span data-ttu-id="f21e5-108">释放 EventProvider</span><span class="sxs-lookup"><span data-stu-id="f21e5-108">Disposing EventProvider</span></span>  
 <span data-ttu-id="f21e5-109">此示例使用 <xref:System.Diagnostics.Eventing.EventProvider?displayProperty=nameWithType> 类，该类实现 <xref:System.IDisposable?displayProperty=nameWithType>。</span><span class="sxs-lookup"><span data-stu-id="f21e5-109">This sample uses the <xref:System.Diagnostics.Eventing.EventProvider?displayProperty=nameWithType> class, which implements <xref:System.IDisposable?displayProperty=nameWithType>.</span></span> <span data-ttu-id="f21e5-110">在实现跟踪的 WCF 服务时，很可能你可能使用<xref:System.Diagnostics.Eventing.EventProvider>的服务的生存期内的资源。</span><span class="sxs-lookup"><span data-stu-id="f21e5-110">When implementing tracing for a WCF service, it is likely that you may use the <xref:System.Diagnostics.Eventing.EventProvider>’s resources for the lifetime of the service.</span></span> <span data-ttu-id="f21e5-111">因此，为了便于阅读，此示例永远不会释放已包装的 <xref:System.Diagnostics.Eventing.EventProvider>。</span><span class="sxs-lookup"><span data-stu-id="f21e5-111">For this reason, and for readability, this sample never disposes of the wrapped <xref:System.Diagnostics.Eventing.EventProvider>.</span></span> <span data-ttu-id="f21e5-112">如果出于某种原因，您的服务具有不同的跟踪需求，并且必须释放此资源，则应根据释放非托管资源的最佳做法来修改此示例。</span><span class="sxs-lookup"><span data-stu-id="f21e5-112">If for some reason your service has different requirements for tracing and you must dispose of this resource, then you should modify this sample in accordance with the best practices for disposing of unmanaged resources.</span></span> <span data-ttu-id="f21e5-113">有关释放非托管的资源的详细信息，请参阅[实现 Dispose 方法](http://go.microsoft.com/fwlink/?LinkId=166436)。</span><span class="sxs-lookup"><span data-stu-id="f21e5-113">For more information about disposing unmanaged resources, see [Implementing a Dispose Method](http://go.microsoft.com/fwlink/?LinkId=166436).</span></span>  
  
## <a name="self-hosting-vs-web-hosting"></a><span data-ttu-id="f21e5-114">自我承载与Web 承载</span><span class="sxs-lookup"><span data-stu-id="f21e5-114">Self-Hosting vs. Web Hosting</span></span>  
 <span data-ttu-id="f21e5-115">对于 Web 承载的服务，WCF 的分析跟踪提供了一个名为"HostReference"，用于标识发出这些跟踪的服务的字段。</span><span class="sxs-lookup"><span data-stu-id="f21e5-115">For Web-hosted services, WCF’s analytic traces provide a field, called "HostReference", which is used to identify the service that is emitting the traces.</span></span> <span data-ttu-id="f21e5-116">可扩展的用户跟踪可以参与此模型，此示例演示执行该操作的最佳做法。</span><span class="sxs-lookup"><span data-stu-id="f21e5-116">The extensible user traces can participate in this model and this sample demonstrates best practices for doing so.</span></span> <span data-ttu-id="f21e5-117">Web 宿主引用的格式时管道&#124;实际显示在随后出现的字符字符串可以是以下任何一个：</span><span class="sxs-lookup"><span data-stu-id="f21e5-117">The format of a Web host reference when the pipe ‘&#124;’ character actually appears in the resulting string can be any one of the following:</span></span>  
  
-   <span data-ttu-id="f21e5-118">如果该应用程序不在根处。</span><span class="sxs-lookup"><span data-stu-id="f21e5-118">If the application is not at the root.</span></span>  
  
     <span data-ttu-id="f21e5-119">\<SiteName >\<ApplicationVirtualPath >&#124;\<ServiceVirtualPath >&#124;\<ServiceName ></span><span class="sxs-lookup"><span data-stu-id="f21e5-119">\<SiteName>\<ApplicationVirtualPath>&#124;\<ServiceVirtualPath>&#124;\<ServiceName></span></span>  
  
-   <span data-ttu-id="f21e5-120">如果该应用程序在根处。</span><span class="sxs-lookup"><span data-stu-id="f21e5-120">If the application is at the root.</span></span>  
  
     <span data-ttu-id="f21e5-121">\<SiteName >&#124;\<ServiceVirtualPath >&#124;\<ServiceName ></span><span class="sxs-lookup"><span data-stu-id="f21e5-121">\<SiteName>&#124;\<ServiceVirtualPath>&#124;\<ServiceName></span></span>  
  
 <span data-ttu-id="f21e5-122">对于自承载服务，WCF 的分析跟踪不会填充"HostReference"字段。</span><span class="sxs-lookup"><span data-stu-id="f21e5-122">For self-hosted services, WCF’s analytic traces do not populate the "HostReference" field.</span></span> <span data-ttu-id="f21e5-123">此示例中的 `WCFUserEventProvider` 类在由自承载服务使用时，其行为是一致的。</span><span class="sxs-lookup"><span data-stu-id="f21e5-123">The `WCFUserEventProvider` class in this sample behaves consistently when used by a self-hosted service.</span></span>  
  
## <a name="custom-event-details"></a><span data-ttu-id="f21e5-124">自定义事件详细信息</span><span class="sxs-lookup"><span data-stu-id="f21e5-124">Custom Event Details</span></span>  
 <span data-ttu-id="f21e5-125">WCF 的 ETW 事件提供程序清单定义了三个旨在通过 WCF 服务作者从服务代码内发出的事件。</span><span class="sxs-lookup"><span data-stu-id="f21e5-125">WCF’s ETW Event Provider manifest defines three events that are designed to be emitted by WCF service authors from within service code.</span></span> <span data-ttu-id="f21e5-126">下表显示了这三个事件的分类。</span><span class="sxs-lookup"><span data-stu-id="f21e5-126">The following table shows a breakdown of the three events.</span></span>  
  
|<span data-ttu-id="f21e5-127">事件</span><span class="sxs-lookup"><span data-stu-id="f21e5-127">Event</span></span>|<span data-ttu-id="f21e5-128">描述</span><span class="sxs-lookup"><span data-stu-id="f21e5-128">Description</span></span>|<span data-ttu-id="f21e5-129">事件 ID</span><span class="sxs-lookup"><span data-stu-id="f21e5-129">Event ID</span></span>|  
|-----------|-----------------|--------------|  
|<span data-ttu-id="f21e5-130">UserDefinedInformationEventOccurred</span><span class="sxs-lookup"><span data-stu-id="f21e5-130">UserDefinedInformationEventOccurred</span></span>|<span data-ttu-id="f21e5-131">服务中发生的说明内容不是一个问题时发出此事件。</span><span class="sxs-lookup"><span data-stu-id="f21e5-131">Emit this event when something of note happens in your service that is not a problem.</span></span> <span data-ttu-id="f21e5-132">例如，可以在对数据库成功进行调用后发出一个事件。</span><span class="sxs-lookup"><span data-stu-id="f21e5-132">For example, you might emit an event after successfully making a call to a database.</span></span>|<span data-ttu-id="f21e5-133">301</span><span class="sxs-lookup"><span data-stu-id="f21e5-133">301</span></span>|  
|<span data-ttu-id="f21e5-134">UserDefinedWarningOccurred</span><span class="sxs-lookup"><span data-stu-id="f21e5-134">UserDefinedWarningOccurred</span></span>|<span data-ttu-id="f21e5-135">发生的问题可能导致将来出现错误时发出此事件。</span><span class="sxs-lookup"><span data-stu-id="f21e5-135">Emit this event when a problem occurs that may result in a failure in the future.</span></span> <span data-ttu-id="f21e5-136">例如，如果调用数据库失败，但能够通过回退到冗余数据存储区进行恢复，则可以发出一个警告事件。</span><span class="sxs-lookup"><span data-stu-id="f21e5-136">For example, you may emit a warning event when a call to a database fails but you were able to recover by falling back to a redundant data store.</span></span>|<span data-ttu-id="f21e5-137">302</span><span class="sxs-lookup"><span data-stu-id="f21e5-137">302</span></span>|  
|<span data-ttu-id="f21e5-138">UserDefinedErrorOccurred</span><span class="sxs-lookup"><span data-stu-id="f21e5-138">UserDefinedErrorOccurred</span></span>|<span data-ttu-id="f21e5-139">服务的行为方式不符合预期时发出此事件。</span><span class="sxs-lookup"><span data-stu-id="f21e5-139">Emit this event when your service fails to behave as expected.</span></span> <span data-ttu-id="f21e5-140">例如，如果调用数据库失败且无法从其他位置检索数据，则可能会发出一个事件。</span><span class="sxs-lookup"><span data-stu-id="f21e5-140">For example, you might emit an event if a call to a database fails and you could not retrieve the data from elsewhere.</span></span>|<span data-ttu-id="f21e5-141">303</span><span class="sxs-lookup"><span data-stu-id="f21e5-141">303</span></span>|  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="f21e5-142">使用此示例</span><span class="sxs-lookup"><span data-stu-id="f21e5-142">To use this sample</span></span>  
  
1.  <span data-ttu-id="f21e5-143">使用 [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] 打开 WCFAnalyticTracingExtensibility.sln 解决方案文件。</span><span class="sxs-lookup"><span data-stu-id="f21e5-143">Using [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)], open the WCFAnalyticTracingExtensibility.sln solution file.</span></span>  
  
2.  <span data-ttu-id="f21e5-144">要生成解决方案，按 Ctrl+Shift+B。</span><span class="sxs-lookup"><span data-stu-id="f21e5-144">To build the solution, press CTRL+SHIFT+B.</span></span>  
  
3.  <span data-ttu-id="f21e5-145">若要运行解决方案，请按 Ctrl+F5。</span><span class="sxs-lookup"><span data-stu-id="f21e5-145">To run the solution, press CTRL+F5.</span></span>  
  
     <span data-ttu-id="f21e5-146">在 Web 浏览器中，单击**Calculator.svc**。</span><span class="sxs-lookup"><span data-stu-id="f21e5-146">In the Web browser, click **Calculator.svc**.</span></span> <span data-ttu-id="f21e5-147">服务的 WSDL 文档的 URI 应出现在浏览器中。</span><span class="sxs-lookup"><span data-stu-id="f21e5-147">The URI of the WSDL document for the service should appear in the browser.</span></span> <span data-ttu-id="f21e5-148">复制该 URI。</span><span class="sxs-lookup"><span data-stu-id="f21e5-148">Copy that URI.</span></span>  
  
4.  <span data-ttu-id="f21e5-149">运行 WCF 测试客户端 (WcfTestClient.exe)。</span><span class="sxs-lookup"><span data-stu-id="f21e5-149">Run the WCF test client (WcfTestClient.exe).</span></span>  
  
     <span data-ttu-id="f21e5-150">WCF 测试客户端 (WcfTestClient.exe) 位于\<[!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)]安装目录 > \Common7\IDE\ WcfTestClient.exe (默认[!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)]安装目录为 C:\Program Files\Microsoft Visual Studio 10.0)。</span><span class="sxs-lookup"><span data-stu-id="f21e5-150">The WCF test client (WcfTestClient.exe) is located in the \<[!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] Install Dir>\Common7\IDE\ WcfTestClient.exe (default [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] install dir is C:\Program Files\Microsoft Visual Studio 10.0).</span></span>  
  
5.  <span data-ttu-id="f21e5-151">在 WCF 测试客户端，通过选择添加服务**文件**，，然后**添加服务**。</span><span class="sxs-lookup"><span data-stu-id="f21e5-151">Within the WCF test client, add the service by selecting **File**, and then **Add Service**.</span></span>  
  
     <span data-ttu-id="f21e5-152">在输入框中添加终结点地址。</span><span class="sxs-lookup"><span data-stu-id="f21e5-152">Add the endpoint address in the input box.</span></span>  
  
6.  <span data-ttu-id="f21e5-153">单击**确定**关闭对话框。</span><span class="sxs-lookup"><span data-stu-id="f21e5-153">Click **OK** to close the dialog.</span></span>  
  
     <span data-ttu-id="f21e5-154">在下方的左窗格中添加 ICalculator 服务**我的服务项目**。</span><span class="sxs-lookup"><span data-stu-id="f21e5-154">The ICalculator service is added in the left pane under **My Service Projects**.</span></span>  
  
7.  <span data-ttu-id="f21e5-155">打开事件查看器应用程序。</span><span class="sxs-lookup"><span data-stu-id="f21e5-155">Open the Event Viewer application.</span></span>  
  
     <span data-ttu-id="f21e5-156">然后再调用服务，启动事件查看器，并确保事件日志正在侦听从 WCF 服务发出的跟踪事件。</span><span class="sxs-lookup"><span data-stu-id="f21e5-156">Before invoking the service, start Event Viewer and ensure that the event log is listening for tracking events emitted from the WCF service.</span></span>  
  
8.  <span data-ttu-id="f21e5-157">从**启动**菜单上，选择**管理工具**，，然后**事件查看器**。</span><span class="sxs-lookup"><span data-stu-id="f21e5-157">From the **Start** menu, select **Administrative Tools**, and then **Event Viewer**.</span></span> <span data-ttu-id="f21e5-158">启用**分析**和**调试**日志。</span><span class="sxs-lookup"><span data-stu-id="f21e5-158">Enable the **Analytic** and **Debug** logs.</span></span>  
  
9. <span data-ttu-id="f21e5-159">在事件查看器中的树视图中，导航到**事件查看器**， **Applications and Services Logs**， **Microsoft**， **Windows**，，然后**应用程序服务器-应用程序**。</span><span class="sxs-lookup"><span data-stu-id="f21e5-159">In the tree view in Event Viewer, navigate to **Event Viewer**, **Applications and Services Logs**, **Microsoft**, **Windows**, and then **Application Server-Applications**.</span></span> <span data-ttu-id="f21e5-160">右键单击**应用程序服务器-应用程序**，选择**视图**，，然后**显示分析和调试日志**。</span><span class="sxs-lookup"><span data-stu-id="f21e5-160">Right-click **Application Server-Applications**, select **View**, and then **Show Analytic and Debug Logs**.</span></span>  
  
     <span data-ttu-id="f21e5-161">确保**显示分析和调试日志**选项处于选中状态。</span><span class="sxs-lookup"><span data-stu-id="f21e5-161">Ensure that the **Show Analytic and Debug Logs** option is checked.</span></span> <span data-ttu-id="f21e5-162">启用**分析**日志。</span><span class="sxs-lookup"><span data-stu-id="f21e5-162">Enable the **Analytic** log.</span></span>  
  
     <span data-ttu-id="f21e5-163">在事件查看器中的树视图中，导航到**事件查看器**， **Applications and Services Logs**， **Microsoft**， **Windows**， **应用程序服务器-应用程序**，，然后**分析**。</span><span class="sxs-lookup"><span data-stu-id="f21e5-163">In the tree view in Event Viewer, navigate to **Event Viewer**, **Applications and Services Logs**, **Microsoft**, **Windows**, **Application Server-Applications**, and then **Analytic**.</span></span> <span data-ttu-id="f21e5-164">右键单击**分析**和选择**启用日志**。</span><span class="sxs-lookup"><span data-stu-id="f21e5-164">Right-click **Analytic** and select **Enable Log**.</span></span>  
  
10. <span data-ttu-id="f21e5-165">使用 WCF 测试客户端来测试服务。</span><span class="sxs-lookup"><span data-stu-id="f21e5-165">Test the service using the WCF Test Client.</span></span>  
  
    1.  <span data-ttu-id="f21e5-166">在 WCF 测试客户端中，双击**add （)** ICalculator 服务节点下。</span><span class="sxs-lookup"><span data-stu-id="f21e5-166">In the WCF Test Client, double-click **Add()** under the ICalculator service node.</span></span>  
  
         <span data-ttu-id="f21e5-167">**Add （)** 方法将显示在右窗格中，带有两个参数。</span><span class="sxs-lookup"><span data-stu-id="f21e5-167">The **Add()** method appears in the right pane with two parameters.</span></span>  
  
    2.  <span data-ttu-id="f21e5-168">为第一个参数键入 2，为第二个参数键入 3。</span><span class="sxs-lookup"><span data-stu-id="f21e5-168">Type in 2 for the first parameter and 3 for the second parameter.</span></span>  
  
    3.  <span data-ttu-id="f21e5-169">单击**Invoke**来调用的方法。</span><span class="sxs-lookup"><span data-stu-id="f21e5-169">Click **Invoke** to invoke the method.</span></span>  
  
11. <span data-ttu-id="f21e5-170">转到**事件查看器**已打开的窗口。</span><span class="sxs-lookup"><span data-stu-id="f21e5-170">Go to the **Event Viewer** window that you have already opened.</span></span> <span data-ttu-id="f21e5-171">导航到**事件查看器**， **Applications and Services Logs**， **Microsoft**， **Windows**，**应用程序服务器应用程序**。</span><span class="sxs-lookup"><span data-stu-id="f21e5-171">Navigate to **Event Viewer**, **Applications and Services Logs**, **Microsoft**, **Windows**, **Application Server-Applications**.</span></span>  
  
12. <span data-ttu-id="f21e5-172">右键单击**分析**节点，然后选择**刷新**。</span><span class="sxs-lookup"><span data-stu-id="f21e5-172">Right-click the **Analytic** node and select **Refresh**.</span></span>  
  
     <span data-ttu-id="f21e5-173">事件将显示在右窗格中。</span><span class="sxs-lookup"><span data-stu-id="f21e5-173">The events appear in the right pane.</span></span>  
  
13. <span data-ttu-id="f21e5-174">使用 ID 303 来查找事件，然后双击该事件将其打开，并检查其内容。</span><span class="sxs-lookup"><span data-stu-id="f21e5-174">Locate the event with the ID of 303 and double-click it to open it up and inspect its contents.</span></span>  
  
     <span data-ttu-id="f21e5-175">已发出此事件`Add()`ICalculator 服务的方法和具有负载等于"2 + 3 = 5"。</span><span class="sxs-lookup"><span data-stu-id="f21e5-175">This event was emitted by the `Add()` method of the ICalculator service and has a payload equal to "2+3=5".</span></span>  
  
#### <a name="to-clean-up-optional"></a><span data-ttu-id="f21e5-176">清理（可选）</span><span class="sxs-lookup"><span data-stu-id="f21e5-176">To clean up (Optional)</span></span>  
  
1.  <span data-ttu-id="f21e5-177">打开**事件查看器**。</span><span class="sxs-lookup"><span data-stu-id="f21e5-177">Open **Event Viewer**.</span></span>  
  
2.  <span data-ttu-id="f21e5-178">导航到**事件查看器**， **Applications and Services Logs**， **Microsoft**， **Windows**，，然后**应用程序服务器-应用程序**。</span><span class="sxs-lookup"><span data-stu-id="f21e5-178">Navigate to **Event Viewer**, **Applications and Services Logs**, **Microsoft**, **Windows**, and then **Application-Server-Applications**.</span></span> <span data-ttu-id="f21e5-179">右键单击**分析**和选择**禁用日志**。</span><span class="sxs-lookup"><span data-stu-id="f21e5-179">Right-click **Analytic** and select **Disable Log**.</span></span>  
  
3.  <span data-ttu-id="f21e5-180">导航到**事件查看器**， **Applications and Services Logs**， **Microsoft**， **Windows**， **应用程序服务器-应用程序**，，然后**分析**。</span><span class="sxs-lookup"><span data-stu-id="f21e5-180">Navigate to **Event Viewer**, **Applications and Services Logs**, **Microsoft**, **Windows**, **Application-Server-Applications**, and then **Analytic**.</span></span> <span data-ttu-id="f21e5-181">右键单击**分析**和选择**清除日志**。</span><span class="sxs-lookup"><span data-stu-id="f21e5-181">Right-click **Analytic** and select **Clear Log**.</span></span>  
  
4.  <span data-ttu-id="f21e5-182">单击**清除**以清除事件。</span><span class="sxs-lookup"><span data-stu-id="f21e5-182">Click **Clear** to clear the events.</span></span>  
  
## <a name="known-issue"></a><span data-ttu-id="f21e5-183">已知问题</span><span class="sxs-lookup"><span data-stu-id="f21e5-183">Known Issue</span></span>  
 <span data-ttu-id="f21e5-184">没有中的已知的问题**事件查看器**即可能无法解码 ETW 事件。</span><span class="sxs-lookup"><span data-stu-id="f21e5-184">There is a known issue in the **Event Viewer** where it may fail to decode ETW events.</span></span> <span data-ttu-id="f21e5-185">你可能会看到一条显示的错误消息:"事件 ID 的描述\<id > 从源无法找到 Microsoft Windows 应用程序服务器-应用程序。</span><span class="sxs-lookup"><span data-stu-id="f21e5-185">You may see an error message that says: "The description for Event ID \<id> from source Microsoft-Windows-Application Server-Applications cannot be found.</span></span> <span data-ttu-id="f21e5-186">本地计算机上未安装引发此事件的组件，或者安装已损坏。</span><span class="sxs-lookup"><span data-stu-id="f21e5-186">Either the component that raises this event is not installed on your local computer or the installation is corrupted.</span></span> <span data-ttu-id="f21e5-187">你可以安装或修复本地计算机上的组件。"</span><span class="sxs-lookup"><span data-stu-id="f21e5-187">You can install or repair the component on the local computer."</span></span> <span data-ttu-id="f21e5-188">如果你遇到此错误，则选择**刷新**从**操作**菜单。</span><span class="sxs-lookup"><span data-stu-id="f21e5-188">If you encounter this error, select **Refresh** from the **Actions** menu.</span></span> <span data-ttu-id="f21e5-189">然后，该事件应能正确解码。</span><span class="sxs-lookup"><span data-stu-id="f21e5-189">The event should then decode properly.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="f21e5-190">您的计算机上可能已安装这些示例。</span><span class="sxs-lookup"><span data-stu-id="f21e5-190">The samples may already be installed on your computer.</span></span> <span data-ttu-id="f21e5-191">在继续操作之前，请先检查以下（默认）目录：</span><span class="sxs-lookup"><span data-stu-id="f21e5-191">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="f21e5-192">如果此目录不存在，请转到[Windows Communication Foundation (WCF) 和针对.NET Framework 4 的 Windows Workflow Foundation (WF) 示例](http://go.microsoft.com/fwlink/?LinkId=150780)下载所有 Windows Communication Foundation (WCF) 和[!INCLUDE[wf1](../../../../includes/wf1-md.md)]示例。</span><span class="sxs-lookup"><span data-stu-id="f21e5-192">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="f21e5-193">此示例位于以下目录：</span><span class="sxs-lookup"><span data-stu-id="f21e5-193">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Management\ETWTrace`  
  
## <a name="see-also"></a><span data-ttu-id="f21e5-194">请参阅</span><span class="sxs-lookup"><span data-stu-id="f21e5-194">See Also</span></span>  
 [<span data-ttu-id="f21e5-195">AppFabric 监视示例</span><span class="sxs-lookup"><span data-stu-id="f21e5-195">AppFabric Monitoring Samples</span></span>](http://go.microsoft.com/fwlink/?LinkId=193959)
