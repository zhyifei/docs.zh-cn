---
title: 针对 Windows 的 WCF 服务和事件跟踪
ms.date: 03/30/2017
ms.assetid: eda4355d-0bd0-4dc9-80a2-d2c832152272
ms.openlocfilehash: 11f476b966886d4a114f7870b4c029e200ee84e0
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/04/2018
ms.locfileid: "43504767"
---
# <a name="wcf-services-and-event-tracing-for-windows"></a><span data-ttu-id="c4d13-102">针对 Windows 的 WCF 服务和事件跟踪</span><span class="sxs-lookup"><span data-stu-id="c4d13-102">WCF Services and Event Tracing for Windows</span></span>
<span data-ttu-id="c4d13-103">此示例演示如何使用 Windows Communication Foundation (WCF) 中的分析跟踪来发出事件中事件跟踪 Windows (ETW)。</span><span class="sxs-lookup"><span data-stu-id="c4d13-103">This sample demonstrates how to use the analytic tracing in Windows Communication Foundation (WCF) to emit events in Event Tracing for Windows (ETW).</span></span> <span data-ttu-id="c4d13-104">分析跟踪是 WCF 堆栈中允许在生产环境中的 WCF 服务的故障排除的关键点处发出的事件。</span><span class="sxs-lookup"><span data-stu-id="c4d13-104">The analytic traces are events emitted at key points in the WCF stack that allow troubleshooting of WCF services in production environment.</span></span>  
  
 <span data-ttu-id="c4d13-105">WCF 服务中的分析跟踪跟踪，可以打开在生产环境中使用最小性能影响。</span><span class="sxs-lookup"><span data-stu-id="c4d13-105">Analytic trace in WCF services is tracing that can be turned on in a production environment with minimal impact on performance.</span></span> <span data-ttu-id="c4d13-106">这些跟踪都以事件的形式向 ETW 会话发出。</span><span class="sxs-lookup"><span data-stu-id="c4d13-106">These traces are emitted as events to an ETW session.</span></span>  
  
 <span data-ttu-id="c4d13-107">此示例包括在其中事件从服务发出到事件日志，可以使用事件查看器查看基本的 WCF 服务。</span><span class="sxs-lookup"><span data-stu-id="c4d13-107">This sample includes a basic WCF service in which events are emitted from the service to the event log, which can be viewed using Event Viewer.</span></span> <span data-ttu-id="c4d13-108">还有可能开始侦听来自 WCF 服务的事件的专用的 ETW 会话。</span><span class="sxs-lookup"><span data-stu-id="c4d13-108">It is also possible to start a dedicated ETW session that listens for events from the WCF service.</span></span> <span data-ttu-id="c4d13-109">该示例包括一个用于创建专用 ETW 会话的脚本，该会话将事件存储在可以使用事件查看器读取的二进制文件中。</span><span class="sxs-lookup"><span data-stu-id="c4d13-109">The sample includes a script to create a dedicated ETW session that stores events in a binary file that can be read using Event Viewer.</span></span>  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="c4d13-110">使用此示例</span><span class="sxs-lookup"><span data-stu-id="c4d13-110">To use this sample</span></span>  
  
1.  <span data-ttu-id="c4d13-111">使用 [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] 打开 EtwAnalyticTraceSample.sln 解决方案文件。</span><span class="sxs-lookup"><span data-stu-id="c4d13-111">Using [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)], open the EtwAnalyticTraceSample.sln solution file.</span></span>  
  
2.  <span data-ttu-id="c4d13-112">要生成解决方案，按 Ctrl+Shift+B。</span><span class="sxs-lookup"><span data-stu-id="c4d13-112">To build the solution, press CTRL+SHIFT+B.</span></span>  
  
3.  <span data-ttu-id="c4d13-113">若要运行解决方案，请按 Ctrl+F5。</span><span class="sxs-lookup"><span data-stu-id="c4d13-113">To run the solution, press CTRL+F5.</span></span>  
  
     <span data-ttu-id="c4d13-114">在 Web 浏览器中，单击**calculator.svc**。</span><span class="sxs-lookup"><span data-stu-id="c4d13-114">In the Web browser, click **Calculator.svc**.</span></span> <span data-ttu-id="c4d13-115">服务的 WSDL 文档的 URI 应出现在浏览器中。</span><span class="sxs-lookup"><span data-stu-id="c4d13-115">The URI of the WSDL document for the service should appear in the browser.</span></span> <span data-ttu-id="c4d13-116">复制该 URI。</span><span class="sxs-lookup"><span data-stu-id="c4d13-116">Copy that URI.</span></span>  
  
     <span data-ttu-id="c4d13-117">默认情况下，在服务启动端口 1378年上侦听请求 (http://localhost:1378/Calculator.svc)。</span><span class="sxs-lookup"><span data-stu-id="c4d13-117">By default, the service starts listening for requests on port 1378 (http://localhost:1378/Calculator.svc).</span></span>  
  
4.  <span data-ttu-id="c4d13-118">运行 WCF 测试客户端 (WcfTestClient.exe)。</span><span class="sxs-lookup"><span data-stu-id="c4d13-118">Run the WCF test client (WcfTestClient.exe).</span></span>  
  
     <span data-ttu-id="c4d13-119">WCF 测试客户端 (WcfTestClient.exe) 位于\<[!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)]安装目录 > \Common7\IDE\ WcfTestClient.exe (默认[!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)]安装目录为 C:\Program Files\Microsoft Visual Studio 10.0)。</span><span class="sxs-lookup"><span data-stu-id="c4d13-119">The WCF test client (WcfTestClient.exe) is located in the \<[!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] Install Dir>\Common7\IDE\ WcfTestClient.exe (default [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] install dir is C:\Program Files\Microsoft Visual Studio 10.0).</span></span>  
  
5.  <span data-ttu-id="c4d13-120">在 WCF 测试客户端，通过选择添加服务**文件**，然后**添加的服务**。</span><span class="sxs-lookup"><span data-stu-id="c4d13-120">Within the WCF test client, add the service by selecting **File**, and then **Add Service**.</span></span>  
  
     <span data-ttu-id="c4d13-121">在输入框中添加终结点地址。</span><span class="sxs-lookup"><span data-stu-id="c4d13-121">Add the endpoint address in the input box.</span></span> <span data-ttu-id="c4d13-122">默认值为 http://localhost:1378/Calculator.svc。</span><span class="sxs-lookup"><span data-stu-id="c4d13-122">The default is http://localhost:1378/Calculator.svc.</span></span>  
  
6.  <span data-ttu-id="c4d13-123">打开事件查看器应用程序。</span><span class="sxs-lookup"><span data-stu-id="c4d13-123">Open the Event Viewer application.</span></span>  
  
     <span data-ttu-id="c4d13-124">然后再调用该服务，启动事件查看器，并确保事件日志正在侦听从 WCF 服务发出的跟踪事件。</span><span class="sxs-lookup"><span data-stu-id="c4d13-124">Before invoking the service, start Event Viewer and ensure that the event log is listening for tracking events emitted from the WCF service.</span></span>  
  
7.  <span data-ttu-id="c4d13-125">从**启动**菜单中，选择**管理工具**，然后**事件查看器**。</span><span class="sxs-lookup"><span data-stu-id="c4d13-125">From the **Start** menu, select **Administrative Tools**, and then **Event Viewer**.</span></span>  <span data-ttu-id="c4d13-126">启用**Analytic**并**调试**日志。</span><span class="sxs-lookup"><span data-stu-id="c4d13-126">Enable the **Analytic** and **Debug** logs.</span></span>  
  
8.  <span data-ttu-id="c4d13-127">在事件查看器中树视图中，导航到**事件查看器**，**应用程序和服务日志**， **Microsoft**， **Windows**，，然后**应用程序服务器-应用程序**。</span><span class="sxs-lookup"><span data-stu-id="c4d13-127">In the tree view in Event Viewer, navigate to **Event Viewer**, **Applications and Services Logs**, **Microsoft**, **Windows**, and then **Application Server-Applications**.</span></span> <span data-ttu-id="c4d13-128">右键单击**应用程序服务器-应用程序**，选择**视图**，然后**显示分析和调试日志**。</span><span class="sxs-lookup"><span data-stu-id="c4d13-128">Right-click **Application Server-Applications**, select **View**, and then **Show Analytic and Debug Logs**.</span></span>  
  
     <span data-ttu-id="c4d13-129">絋粄**显示分析和调试日志**选项处于选中状态。</span><span class="sxs-lookup"><span data-stu-id="c4d13-129">Ensure that the **Show Analytic and Debug Logs** option is checked.</span></span>  
  
9. <span data-ttu-id="c4d13-130">启用**分析**日志。</span><span class="sxs-lookup"><span data-stu-id="c4d13-130">Enable the **Analytic** log.</span></span>  
  
     <span data-ttu-id="c4d13-131">在事件查看器中树视图中，导航到**事件查看器**，**应用程序和服务日志**， **Microsoft**， **Windows**，，然后**应用程序服务器-应用程序**。</span><span class="sxs-lookup"><span data-stu-id="c4d13-131">In the tree view in Event Viewer, navigate to **Event Viewer**, **Applications and Services Logs**, **Microsoft**, **Windows**, and then **Application Server-Applications**.</span></span> <span data-ttu-id="c4d13-132">右键单击**Analytic** ，然后选择**启用日志**。</span><span class="sxs-lookup"><span data-stu-id="c4d13-132">Right-click **Analytic** and select **Enable Log**.</span></span>  
  
#### <a name="to-test-the-service"></a><span data-ttu-id="c4d13-133">测试服务</span><span class="sxs-lookup"><span data-stu-id="c4d13-133">To test the service</span></span>  
  
1.  <span data-ttu-id="c4d13-134">切换回 WCF 测试客户端并双击`Divide`并保留默认值，指定分母为 0。</span><span class="sxs-lookup"><span data-stu-id="c4d13-134">Switch back to WCF test client and double-click `Divide` and keep the default values, which specify a denominator of 0.</span></span>  
  
     <span data-ttu-id="c4d13-135">如果分母为 0，则服务引发错误。</span><span class="sxs-lookup"><span data-stu-id="c4d13-135">If the denominator is 0, then the service throws a fault.</span></span>  
  
2.  <span data-ttu-id="c4d13-136">观察从服务发出的事件。</span><span class="sxs-lookup"><span data-stu-id="c4d13-136">Observe the events emitted from the service.</span></span>  
  
     <span data-ttu-id="c4d13-137">切换回事件查看器并导航到**事件查看器**，**应用程序和服务日志**， **Microsoft**， **Windows**，，然后**应用程序服务器-应用程序**。</span><span class="sxs-lookup"><span data-stu-id="c4d13-137">Switch back to Event Viewer and navigate to **Event Viewer**, **Applications and Services Logs**, **Microsoft**, **Windows**, and then **Application Server-Applications**.</span></span> <span data-ttu-id="c4d13-138">右键单击**Analytic** ，然后选择**刷新**。</span><span class="sxs-lookup"><span data-stu-id="c4d13-138">Right-click **Analytic** and select **Refresh**.</span></span>  
  
     <span data-ttu-id="c4d13-139">WCF 分析跟踪事件显示在事件查看器中。</span><span class="sxs-lookup"><span data-stu-id="c4d13-139">The WCF analytic trace events are displayed in the event viewer.</span></span> <span data-ttu-id="c4d13-140">请注意，因为服务引发了错误，所以事件查看器中会显示错误跟踪事件。</span><span class="sxs-lookup"><span data-stu-id="c4d13-140">Notice that because a fault was thrown by the service an error trace event is displayed in the event viewer.</span></span>  
  
3.  <span data-ttu-id="c4d13-141">重复步骤 1 和 2，但是使用有效的输入。</span><span class="sxs-lookup"><span data-stu-id="c4d13-141">Repeat steps 1 and 2, but with valid inputs.</span></span> <span data-ttu-id="c4d13-142">`N2` 参数的值可以为 0 之外的任何数。</span><span class="sxs-lookup"><span data-stu-id="c4d13-142">The value of the `N2` parameter can be any number other than 0.</span></span>  
  
     <span data-ttu-id="c4d13-143">刷新分析通道以查看 WCF 事件，可以看到不包含任何错误事件。</span><span class="sxs-lookup"><span data-stu-id="c4d13-143">Refresh the analytic channel to view the WCF events do not include any error events.</span></span>  
  
 <span data-ttu-id="c4d13-144">该示例演示从 WCF 服务发出的分析跟踪事件。</span><span class="sxs-lookup"><span data-stu-id="c4d13-144">The sample demonstrates the analytic trace events emitted from a WCF service.</span></span>  
  
#### <a name="to-cleanup-optional"></a><span data-ttu-id="c4d13-145">清理（可选）</span><span class="sxs-lookup"><span data-stu-id="c4d13-145">To cleanup (Optional)</span></span>  
  
1.  <span data-ttu-id="c4d13-146">打开事件查看器。</span><span class="sxs-lookup"><span data-stu-id="c4d13-146">Open Event Viewer.</span></span>  
  
2.  <span data-ttu-id="c4d13-147">导航到**事件查看器**，**应用程序和服务日志**， **Microsoft**， **Windows**，，然后**应用程序服务器-应用程序**。</span><span class="sxs-lookup"><span data-stu-id="c4d13-147">Navigate to **Event Viewer**, **Applications and Services Logs**, **Microsoft**, **Windows**, and then **Application-Server-Applications**.</span></span> <span data-ttu-id="c4d13-148">右键单击**Analytic** ，然后选择**禁用日志**。</span><span class="sxs-lookup"><span data-stu-id="c4d13-148">Right-click **Analytic** and select **Disable Log**.</span></span>  
  
3.  <span data-ttu-id="c4d13-149">导航到**事件查看器**，**应用程序和服务日志**， **Microsoft**， **Windows**，，然后**应用程序服务器-应用程序**。</span><span class="sxs-lookup"><span data-stu-id="c4d13-149">Navigate to **Event Viewer**, **Applications and Services Logs**, **Microsoft**, **Windows**, and then **Application-Server-Applications**.</span></span> <span data-ttu-id="c4d13-150">右键单击**Analytic** ，然后选择**清除日志**。</span><span class="sxs-lookup"><span data-stu-id="c4d13-150">Right-click **Analytic** and select **Clear Log**.</span></span>  
  
4.  <span data-ttu-id="c4d13-151">选择**清除**选项可清除这些事件。</span><span class="sxs-lookup"><span data-stu-id="c4d13-151">Choose the **Clear** option to clear the events.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="c4d13-152">您的计算机上可能已安装这些示例。</span><span class="sxs-lookup"><span data-stu-id="c4d13-152">The samples may already be installed on your computer.</span></span> <span data-ttu-id="c4d13-153">在继续操作之前，请先检查以下（默认）目录：</span><span class="sxs-lookup"><span data-stu-id="c4d13-153">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="c4d13-154">如果此目录不存在，请转到[Windows Communication Foundation (WCF) 和.NET Framework 4 的 Windows Workflow Foundation (WF) 示例](https://go.microsoft.com/fwlink/?LinkId=150780)若要下载所有 Windows Communication Foundation (WCF) 和[!INCLUDE[wf1](../../../../includes/wf1-md.md)]示例。</span><span class="sxs-lookup"><span data-stu-id="c4d13-154">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="c4d13-155">此示例位于以下目录：</span><span class="sxs-lookup"><span data-stu-id="c4d13-155">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Management\ETWTracing`  
  
## <a name="see-also"></a><span data-ttu-id="c4d13-156">请参阅</span><span class="sxs-lookup"><span data-stu-id="c4d13-156">See Also</span></span>  
 [<span data-ttu-id="c4d13-157">AppFabric 监视示例</span><span class="sxs-lookup"><span data-stu-id="c4d13-157">AppFabric Monitoring Samples</span></span>](https://go.microsoft.com/fwlink/?LinkId=193959)
