---
title: WCF 分析跟踪
ms.date: 03/30/2017
ms.assetid: 6029c7c7-3515-4d36-9d43-13e8f4971790
ms.openlocfilehash: 3ed9c5f08e89d978f8290dcda5ab1ecfd8b9c56c
ms.sourcegitcommit: 011314e0c8eb4cf4a11d92078f58176c8c3efd2d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/09/2020
ms.locfileid: "77094821"
---
# <a name="wcf-analytic-tracing"></a><span data-ttu-id="a2e20-102">WCF 分析跟踪</span><span class="sxs-lookup"><span data-stu-id="a2e20-102">WCF Analytic Tracing</span></span>
<span data-ttu-id="a2e20-103">此示例演示如何将您自己的跟踪事件添加到分析跟踪流中，这些跟踪事件 Windows Communication Foundation （WCF）写入 [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)]中的 ETW。</span><span class="sxs-lookup"><span data-stu-id="a2e20-103">This sample demonstrates how to add your own tracing events into the stream of analytic traces that Windows Communication Foundation (WCF) writes to ETW in [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)].</span></span> <span data-ttu-id="a2e20-104">跟踪分析是为了便于查看服务，而不会导致较高性能损失。</span><span class="sxs-lookup"><span data-stu-id="a2e20-104">Analytic traces are meant to make it easy to get visibility into your services without paying a high performance penalty.</span></span> <span data-ttu-id="a2e20-105">此示例演示如何使用 <xref:System.Diagnostics.Eventing?displayProperty=nameWithType> Api 写入与 WCF 服务集成的事件。</span><span class="sxs-lookup"><span data-stu-id="a2e20-105">This sample shows how to use the <xref:System.Diagnostics.Eventing?displayProperty=nameWithType> APIs to write events that integrate with WCF services.</span></span>  
  
 <span data-ttu-id="a2e20-106">有关 <xref:System.Diagnostics.Eventing?displayProperty=nameWithType> Api 的详细信息，请参阅 <xref:System.Diagnostics.Eventing?displayProperty=nameWithType>。</span><span class="sxs-lookup"><span data-stu-id="a2e20-106">For more information about the <xref:System.Diagnostics.Eventing?displayProperty=nameWithType> APIs, see <xref:System.Diagnostics.Eventing?displayProperty=nameWithType>.</span></span>  
  
 <span data-ttu-id="a2e20-107">若要了解有关 Windows 中的事件跟踪的详细信息，请参阅[通过 ETW 改善调试和性能优化](https://docs.microsoft.com/archive/msdn-magazine/2007/april/event-tracing-improve-debugging-and-performance-tuning-with-etw)。</span><span class="sxs-lookup"><span data-stu-id="a2e20-107">To learn more about event tracing in Windows, see [Improve Debugging and Performance Tuning with ETW](https://docs.microsoft.com/archive/msdn-magazine/2007/april/event-tracing-improve-debugging-and-performance-tuning-with-etw).</span></span>  
  
## <a name="disposing-eventprovider"></a><span data-ttu-id="a2e20-108">释放 EventProvider</span><span class="sxs-lookup"><span data-stu-id="a2e20-108">Disposing EventProvider</span></span>  
 <span data-ttu-id="a2e20-109">此示例使用 <xref:System.Diagnostics.Eventing.EventProvider?displayProperty=nameWithType> 类，该类实现 <xref:System.IDisposable?displayProperty=nameWithType>。</span><span class="sxs-lookup"><span data-stu-id="a2e20-109">This sample uses the <xref:System.Diagnostics.Eventing.EventProvider?displayProperty=nameWithType> class, which implements <xref:System.IDisposable?displayProperty=nameWithType>.</span></span> <span data-ttu-id="a2e20-110">在为 WCF 服务实现跟踪时，可能会在服务的生存期内使用 <xref:System.Diagnostics.Eventing.EventProvider>的资源。</span><span class="sxs-lookup"><span data-stu-id="a2e20-110">When implementing tracing for a WCF service, it is likely that you may use the <xref:System.Diagnostics.Eventing.EventProvider>’s resources for the lifetime of the service.</span></span> <span data-ttu-id="a2e20-111">因此，为了便于阅读，此示例永远不会释放已包装的 <xref:System.Diagnostics.Eventing.EventProvider>。</span><span class="sxs-lookup"><span data-stu-id="a2e20-111">For this reason, and for readability, this sample never disposes of the wrapped <xref:System.Diagnostics.Eventing.EventProvider>.</span></span> <span data-ttu-id="a2e20-112">如果出于某种原因，您的服务具有不同的跟踪需求，并且必须释放此资源，则应根据释放非托管资源的最佳做法来修改此示例。</span><span class="sxs-lookup"><span data-stu-id="a2e20-112">If for some reason your service has different requirements for tracing and you must dispose of this resource, then you should modify this sample in accordance with the best practices for disposing of unmanaged resources.</span></span> <span data-ttu-id="a2e20-113">有关释放非托管资源的详细信息，请参阅[实现 Dispose 方法](https://docs.microsoft.com/dotnet/standard/garbage-collection/implementing-dispose)。</span><span class="sxs-lookup"><span data-stu-id="a2e20-113">For more information about disposing unmanaged resources, see [Implementing a Dispose Method](https://docs.microsoft.com/dotnet/standard/garbage-collection/implementing-dispose).</span></span>  
  
## <a name="self-hosting-vs-web-hosting"></a><span data-ttu-id="a2e20-114">自承载与 Web 承载</span><span class="sxs-lookup"><span data-stu-id="a2e20-114">Self-Hosting vs. Web Hosting</span></span>  
 <span data-ttu-id="a2e20-115">对于 Web 承载的服务，WCF 的分析跟踪提供了一个名为 "HostReference" 的字段，该字段用于标识发出跟踪的服务。</span><span class="sxs-lookup"><span data-stu-id="a2e20-115">For Web-hosted services, WCF’s analytic traces provide a field, called "HostReference", which is used to identify the service that is emitting the traces.</span></span> <span data-ttu-id="a2e20-116">可扩展的用户跟踪可以参与此模型，此示例演示执行该操作的最佳做法。</span><span class="sxs-lookup"><span data-stu-id="a2e20-116">The extensible user traces can participate in this model and this sample demonstrates best practices for doing so.</span></span> <span data-ttu-id="a2e20-117">当管道 "&#124;" 字符实际上出现在生成的字符串中时，Web 主机引用的格式可以是以下任意一种格式：</span><span class="sxs-lookup"><span data-stu-id="a2e20-117">The format of a Web host reference when the pipe ‘&#124;’ character actually appears in the resulting string can be any one of the following:</span></span>  
  
- <span data-ttu-id="a2e20-118">如果该应用程序不在根处。</span><span class="sxs-lookup"><span data-stu-id="a2e20-118">If the application is not at the root.</span></span>  
  
     <span data-ttu-id="a2e20-119">\<SiteName >\<ApplicationVirtualPath >&#124;\<>\<&#124; > ServiceName</span><span class="sxs-lookup"><span data-stu-id="a2e20-119">\<SiteName>\<ApplicationVirtualPath>&#124;\<ServiceVirtualPath>&#124;\<ServiceName></span></span>  
  
- <span data-ttu-id="a2e20-120">如果该应用程序在根处。</span><span class="sxs-lookup"><span data-stu-id="a2e20-120">If the application is at the root.</span></span>  
  
     <span data-ttu-id="a2e20-121">\<SiteName >&#124;\<ServiceVirtualPath >&#124;\<ServiceName ></span><span class="sxs-lookup"><span data-stu-id="a2e20-121">\<SiteName>&#124;\<ServiceVirtualPath>&#124;\<ServiceName></span></span>  
  
 <span data-ttu-id="a2e20-122">对于自承载服务，WCF 的分析跟踪不填充 "HostReference" 字段。</span><span class="sxs-lookup"><span data-stu-id="a2e20-122">For self-hosted services, WCF’s analytic traces do not populate the "HostReference" field.</span></span> <span data-ttu-id="a2e20-123">此示例中的 `WCFUserEventProvider` 类在由自承载服务使用时，其行为是一致的。</span><span class="sxs-lookup"><span data-stu-id="a2e20-123">The `WCFUserEventProvider` class in this sample behaves consistently when used by a self-hosted service.</span></span>  
  
## <a name="custom-event-details"></a><span data-ttu-id="a2e20-124">自定义事件详细信息</span><span class="sxs-lookup"><span data-stu-id="a2e20-124">Custom Event Details</span></span>  
 <span data-ttu-id="a2e20-125">WCF 的 ETW 事件提供程序清单定义了三个事件，这些事件旨在由 WCF 服务作者从服务代码中发出。</span><span class="sxs-lookup"><span data-stu-id="a2e20-125">WCF’s ETW Event Provider manifest defines three events that are designed to be emitted by WCF service authors from within service code.</span></span> <span data-ttu-id="a2e20-126">下表显示了这三个事件的分类。</span><span class="sxs-lookup"><span data-stu-id="a2e20-126">The following table shows a breakdown of the three events.</span></span>  
  
|<span data-ttu-id="a2e20-127">事件</span><span class="sxs-lookup"><span data-stu-id="a2e20-127">Event</span></span>|<span data-ttu-id="a2e20-128">说明</span><span class="sxs-lookup"><span data-stu-id="a2e20-128">Description</span></span>|<span data-ttu-id="a2e20-129">事件 ID</span><span class="sxs-lookup"><span data-stu-id="a2e20-129">Event ID</span></span>|  
|-----------|-----------------|--------------|  
|<span data-ttu-id="a2e20-130">UserDefinedInformationEventOccurred</span><span class="sxs-lookup"><span data-stu-id="a2e20-130">UserDefinedInformationEventOccurred</span></span>|<span data-ttu-id="a2e20-131">服务中发生的说明内容不是一个问题时发出此事件。</span><span class="sxs-lookup"><span data-stu-id="a2e20-131">Emit this event when something of note happens in your service that is not a problem.</span></span> <span data-ttu-id="a2e20-132">例如，可以在对数据库成功进行调用后发出一个事件。</span><span class="sxs-lookup"><span data-stu-id="a2e20-132">For example, you might emit an event after successfully making a call to a database.</span></span>|<span data-ttu-id="a2e20-133">301</span><span class="sxs-lookup"><span data-stu-id="a2e20-133">301</span></span>|  
|<span data-ttu-id="a2e20-134">UserDefinedWarningOccurred</span><span class="sxs-lookup"><span data-stu-id="a2e20-134">UserDefinedWarningOccurred</span></span>|<span data-ttu-id="a2e20-135">发生的问题可能导致将来出现错误时发出此事件。</span><span class="sxs-lookup"><span data-stu-id="a2e20-135">Emit this event when a problem occurs that may result in a failure in the future.</span></span> <span data-ttu-id="a2e20-136">例如，如果调用数据库失败，但能够通过回退到冗余数据存储区进行恢复，则可以发出一个警告事件。</span><span class="sxs-lookup"><span data-stu-id="a2e20-136">For example, you may emit a warning event when a call to a database fails but you were able to recover by falling back to a redundant data store.</span></span>|<span data-ttu-id="a2e20-137">302</span><span class="sxs-lookup"><span data-stu-id="a2e20-137">302</span></span>|  
|<span data-ttu-id="a2e20-138">UserDefinedErrorOccurred</span><span class="sxs-lookup"><span data-stu-id="a2e20-138">UserDefinedErrorOccurred</span></span>|<span data-ttu-id="a2e20-139">服务的行为方式不符合预期时发出此事件。</span><span class="sxs-lookup"><span data-stu-id="a2e20-139">Emit this event when your service fails to behave as expected.</span></span> <span data-ttu-id="a2e20-140">例如，如果调用数据库失败且无法从其他位置检索数据，则可能会发出一个事件。</span><span class="sxs-lookup"><span data-stu-id="a2e20-140">For example, you might emit an event if a call to a database fails and you could not retrieve the data from elsewhere.</span></span>|<span data-ttu-id="a2e20-141">303</span><span class="sxs-lookup"><span data-stu-id="a2e20-141">303</span></span>|  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="a2e20-142">使用此示例</span><span class="sxs-lookup"><span data-stu-id="a2e20-142">To use this sample</span></span>  
  
1. <span data-ttu-id="a2e20-143">使用 Visual Studio 2012 打开 WCFAnalyticTracingExtensibility 解决方案文件。</span><span class="sxs-lookup"><span data-stu-id="a2e20-143">Using Visual Studio 2012, open the WCFAnalyticTracingExtensibility.sln solution file.</span></span>  
  
2. <span data-ttu-id="a2e20-144">要生成解决方案，按 Ctrl+Shift+B。</span><span class="sxs-lookup"><span data-stu-id="a2e20-144">To build the solution, press CTRL+SHIFT+B.</span></span>  
  
3. <span data-ttu-id="a2e20-145">若要运行解决方案，请按 Ctrl+F5。</span><span class="sxs-lookup"><span data-stu-id="a2e20-145">To run the solution, press CTRL+F5.</span></span>  
  
     <span data-ttu-id="a2e20-146">在 Web 浏览器中，单击 "**计算器**"。</span><span class="sxs-lookup"><span data-stu-id="a2e20-146">In the Web browser, click **Calculator.svc**.</span></span> <span data-ttu-id="a2e20-147">服务的 WSDL 文档的 URI 应出现在浏览器中。</span><span class="sxs-lookup"><span data-stu-id="a2e20-147">The URI of the WSDL document for the service should appear in the browser.</span></span> <span data-ttu-id="a2e20-148">复制该 URI。</span><span class="sxs-lookup"><span data-stu-id="a2e20-148">Copy that URI.</span></span>  
  
4. <span data-ttu-id="a2e20-149">运行 WCF 测试客户端（Wcftestclient.exe）。</span><span class="sxs-lookup"><span data-stu-id="a2e20-149">Run the WCF test client (WcfTestClient.exe).</span></span>  
  
     <span data-ttu-id="a2e20-150">WCF 测试客户端（Wcftestclient.exe）位于 `\<Visual Studio 2012 Install Dir>\Common7\IDE\WcfTestClient.exe`。</span><span class="sxs-lookup"><span data-stu-id="a2e20-150">The WCF test client (WcfTestClient.exe) is located at `\<Visual Studio 2012 Install Dir>\Common7\IDE\WcfTestClient.exe`.</span></span> <span data-ttu-id="a2e20-151">默认的 Visual Studio 2012 安装目录为 `C:\Program Files\Microsoft Visual Studio 10.0`。</span><span class="sxs-lookup"><span data-stu-id="a2e20-151">The default Visual Studio 2012 install dir is `C:\Program Files\Microsoft Visual Studio 10.0`.</span></span>  
  
5. <span data-ttu-id="a2e20-152">在 WCF 测试客户端中，通过依次选择 "**文件**" 和 "**添加服务**" 来添加服务。</span><span class="sxs-lookup"><span data-stu-id="a2e20-152">Within the WCF test client, add the service by selecting **File**, and then **Add Service**.</span></span>  
  
     <span data-ttu-id="a2e20-153">在输入框中添加终结点地址。</span><span class="sxs-lookup"><span data-stu-id="a2e20-153">Add the endpoint address in the input box.</span></span>  
  
6. <span data-ttu-id="a2e20-154">单击 **“确定”** ，关闭对话框。</span><span class="sxs-lookup"><span data-stu-id="a2e20-154">Click **OK** to close the dialog.</span></span>  
  
     <span data-ttu-id="a2e20-155">ICalculator 服务将添加到 "**我的服务项目**" 下的左窗格中。</span><span class="sxs-lookup"><span data-stu-id="a2e20-155">The ICalculator service is added in the left pane under **My Service Projects**.</span></span>  
  
7. <span data-ttu-id="a2e20-156">打开事件查看器应用程序。</span><span class="sxs-lookup"><span data-stu-id="a2e20-156">Open the Event Viewer application.</span></span>  
  
     <span data-ttu-id="a2e20-157">在调用服务之前，请启动事件查看器并确保事件日志正在侦听从 WCF 服务发出的跟踪事件。</span><span class="sxs-lookup"><span data-stu-id="a2e20-157">Before invoking the service, start Event Viewer and ensure that the event log is listening for tracking events emitted from the WCF service.</span></span>  
  
8. <span data-ttu-id="a2e20-158">从 "**开始**" 菜单中选择 "**管理工具**"，然后**事件查看器**"。</span><span class="sxs-lookup"><span data-stu-id="a2e20-158">From the **Start** menu, select **Administrative Tools**, and then **Event Viewer**.</span></span> <span data-ttu-id="a2e20-159">启用**分析**日志和**调试**日志。</span><span class="sxs-lookup"><span data-stu-id="a2e20-159">Enable the **Analytic** and **Debug** logs.</span></span>  
  
9. <span data-ttu-id="a2e20-160">在事件查看器的树视图中，导航到 "**事件查看器**"、"**应用程序和服务日志**"、" **Microsoft**"、" **Windows**" 和 "**应用程序服务器应用程序**"。</span><span class="sxs-lookup"><span data-stu-id="a2e20-160">In the tree view in Event Viewer, navigate to **Event Viewer**, **Applications and Services Logs**, **Microsoft**, **Windows**, and then **Application Server-Applications**.</span></span> <span data-ttu-id="a2e20-161">右键单击 "**应用程序服务器-应用程序**"，选择 "**查看**"，然后**显示 "分析日志和调试日志**"。</span><span class="sxs-lookup"><span data-stu-id="a2e20-161">Right-click **Application Server-Applications**, select **View**, and then **Show Analytic and Debug Logs**.</span></span>  
  
     <span data-ttu-id="a2e20-162">确保选中 "**显示分析和调试日志**" 选项。</span><span class="sxs-lookup"><span data-stu-id="a2e20-162">Ensure that the **Show Analytic and Debug Logs** option is checked.</span></span> <span data-ttu-id="a2e20-163">启用**分析**日志。</span><span class="sxs-lookup"><span data-stu-id="a2e20-163">Enable the **Analytic** log.</span></span>  
  
     <span data-ttu-id="a2e20-164">在事件查看器中的树视图中，导航到 "**事件查看器**"、"**应用程序和服务日志**"、" **Microsoft** **"、** "**应用程序服务器"-** "应用程序" 和 "**分析**"。</span><span class="sxs-lookup"><span data-stu-id="a2e20-164">In the tree view in Event Viewer, navigate to **Event Viewer**, **Applications and Services Logs**, **Microsoft**, **Windows**, **Application Server-Applications**, and then **Analytic**.</span></span> <span data-ttu-id="a2e20-165">右键单击 "**分析**"，然后选择 "**启用日志**"。</span><span class="sxs-lookup"><span data-stu-id="a2e20-165">Right-click **Analytic** and select **Enable Log**.</span></span>  
  
10. <span data-ttu-id="a2e20-166">使用 WCF 测试客户端来测试服务。</span><span class="sxs-lookup"><span data-stu-id="a2e20-166">Test the service using the WCF Test Client.</span></span>  
  
    1. <span data-ttu-id="a2e20-167">在 WCF 测试客户端中，双击 "ICalculator" 服务节点下的 " **Add （）** "。</span><span class="sxs-lookup"><span data-stu-id="a2e20-167">In the WCF Test Client, double-click **Add()** under the ICalculator service node.</span></span>  
  
         <span data-ttu-id="a2e20-168">**Add （）** 方法显示在右窗格中，具有两个参数。</span><span class="sxs-lookup"><span data-stu-id="a2e20-168">The **Add()** method appears in the right pane with two parameters.</span></span>  
  
    2. <span data-ttu-id="a2e20-169">为第一个参数键入 2，为第二个参数键入 3。</span><span class="sxs-lookup"><span data-stu-id="a2e20-169">Type in 2 for the first parameter and 3 for the second parameter.</span></span>  
  
    3. <span data-ttu-id="a2e20-170">单击 "**调用**" 可调用方法。</span><span class="sxs-lookup"><span data-stu-id="a2e20-170">Click **Invoke** to invoke the method.</span></span>  
  
11. <span data-ttu-id="a2e20-171">中转到已打开的 "**事件查看器**" 窗口。</span><span class="sxs-lookup"><span data-stu-id="a2e20-171">Go to the **Event Viewer** window that you have already opened.</span></span> <span data-ttu-id="a2e20-172">导航到**事件查看器**、**应用程序和服务日志**、 **Microsoft**、 **Windows**、**应用程序服务器应用程序**。</span><span class="sxs-lookup"><span data-stu-id="a2e20-172">Navigate to **Event Viewer**, **Applications and Services Logs**, **Microsoft**, **Windows**, **Application Server-Applications**.</span></span>  
  
12. <span data-ttu-id="a2e20-173">右键单击 "**分析**" 节点，然后选择 "**刷新**"。</span><span class="sxs-lookup"><span data-stu-id="a2e20-173">Right-click the **Analytic** node and select **Refresh**.</span></span>  
  
     <span data-ttu-id="a2e20-174">事件将显示在右窗格中。</span><span class="sxs-lookup"><span data-stu-id="a2e20-174">The events appear in the right pane.</span></span>  
  
13. <span data-ttu-id="a2e20-175">使用 ID 303 来查找事件，然后双击该事件将其打开，并检查其内容。</span><span class="sxs-lookup"><span data-stu-id="a2e20-175">Locate the event with the ID of 303 and double-click it to open it up and inspect its contents.</span></span>  
  
     <span data-ttu-id="a2e20-176">此事件由 ICalculator 服务的 `Add()` 方法发出，其有效负载等于 "2 + 3 = 5"。</span><span class="sxs-lookup"><span data-stu-id="a2e20-176">This event was emitted by the `Add()` method of the ICalculator service and has a payload equal to "2+3=5".</span></span>  
  
#### <a name="to-clean-up-optional"></a><span data-ttu-id="a2e20-177">清理（可选）</span><span class="sxs-lookup"><span data-stu-id="a2e20-177">To clean up (Optional)</span></span>  
  
1. <span data-ttu-id="a2e20-178">打开“事件查看器”。</span><span class="sxs-lookup"><span data-stu-id="a2e20-178">Open **Event Viewer**.</span></span>  
  
2. <span data-ttu-id="a2e20-179">导航到**事件查看器**、**应用程序和服务日志**、 **Microsoft**、 **Windows**，然后**应用程序服务器应用程序**。</span><span class="sxs-lookup"><span data-stu-id="a2e20-179">Navigate to **Event Viewer**, **Applications and Services Logs**, **Microsoft**, **Windows**, and then **Application-Server-Applications**.</span></span> <span data-ttu-id="a2e20-180">右键单击 "**分析**"，然后选择 "**禁用日志**"。</span><span class="sxs-lookup"><span data-stu-id="a2e20-180">Right-click **Analytic** and select **Disable Log**.</span></span>  
  
3. <span data-ttu-id="a2e20-181">导航到**事件查看器**、**应用程序和服务日志**、 **Microsoft**、 **Windows**、**应用程序-服务器应用程序**，然后进行**分析**。</span><span class="sxs-lookup"><span data-stu-id="a2e20-181">Navigate to **Event Viewer**, **Applications and Services Logs**, **Microsoft**, **Windows**, **Application-Server-Applications**, and then **Analytic**.</span></span> <span data-ttu-id="a2e20-182">右键单击 "**分析**"，然后选择 "**清除日志**"。</span><span class="sxs-lookup"><span data-stu-id="a2e20-182">Right-click **Analytic** and select **Clear Log**.</span></span>  
  
4. <span data-ttu-id="a2e20-183">单击 "**清除**" 以清除事件。</span><span class="sxs-lookup"><span data-stu-id="a2e20-183">Click **Clear** to clear the events.</span></span>  
  
## <a name="known-issue"></a><span data-ttu-id="a2e20-184">已知问题</span><span class="sxs-lookup"><span data-stu-id="a2e20-184">Known Issue</span></span>  
 <span data-ttu-id="a2e20-185">**事件查看器**中存在一个已知问题，在这种情况下，可能无法解码 ETW 事件。</span><span class="sxs-lookup"><span data-stu-id="a2e20-185">There is a known issue in the **Event Viewer** where it may fail to decode ETW events.</span></span> <span data-ttu-id="a2e20-186">你可能会看到一条错误消息，指出： "来自源 Microsoft-Windows 应用程序服务器的事件 ID \<id > 的说明找不到。</span><span class="sxs-lookup"><span data-stu-id="a2e20-186">You may see an error message that says: "The description for Event ID \<id> from source Microsoft-Windows-Application Server-Applications cannot be found.</span></span> <span data-ttu-id="a2e20-187">未在本地计算机上安装引发此事件的组件，或者安装已损坏。</span><span class="sxs-lookup"><span data-stu-id="a2e20-187">Either the component that raises this event is not installed on your local computer or the installation is corrupted.</span></span> <span data-ttu-id="a2e20-188">您可以在本地计算机上安装或修复该组件。 "</span><span class="sxs-lookup"><span data-stu-id="a2e20-188">You can install or repair the component on the local computer."</span></span> <span data-ttu-id="a2e20-189">如果遇到此错误，请从 "**操作**" 菜单选择 "**刷新**"。</span><span class="sxs-lookup"><span data-stu-id="a2e20-189">If you encounter this error, select **Refresh** from the **Actions** menu.</span></span> <span data-ttu-id="a2e20-190">然后，该事件应能正确解码。</span><span class="sxs-lookup"><span data-stu-id="a2e20-190">The event should then decode properly.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="a2e20-191">您的计算机上可能已安装这些示例。</span><span class="sxs-lookup"><span data-stu-id="a2e20-191">The samples may already be installed on your computer.</span></span> <span data-ttu-id="a2e20-192">在继续操作之前，请先检查以下（默认）目录：</span><span class="sxs-lookup"><span data-stu-id="a2e20-192">Check for the following (default) directory before continuing.</span></span>  
>   
> `<InstallDrive>:\WF_WCF_Samples`  
>   
> <span data-ttu-id="a2e20-193">如果此目录不存在，请参阅[.NET Framework 4 的 Windows Communication Foundation （wcf）和 Windows Workflow Foundation （WF）示例](https://www.microsoft.com/download/details.aspx?id=21459)以下载所有 WINDOWS COMMUNICATION FOUNDATION （wcf）和 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 示例。</span><span class="sxs-lookup"><span data-stu-id="a2e20-193">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="a2e20-194">此示例位于以下目录：</span><span class="sxs-lookup"><span data-stu-id="a2e20-194">This sample is located in the following directory.</span></span>  
>   
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Management\ETWTrace`  
  
## <a name="see-also"></a><span data-ttu-id="a2e20-195">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a2e20-195">See also</span></span>

- <span data-ttu-id="a2e20-196">[AppFabric 监视示例](https://docs.microsoft.com/previous-versions/appfabric/ff383407(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="a2e20-196">[AppFabric Monitoring Samples](https://docs.microsoft.com/previous-versions/appfabric/ff383407(v=azure.10))</span></span>
