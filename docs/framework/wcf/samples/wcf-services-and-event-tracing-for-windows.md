---
title: "针对 Windows 的 WCF 服务和事件跟踪"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: eda4355d-0bd0-4dc9-80a2-d2c832152272
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: ed3b7b370ed6b1d9a900579ff0e6f1b0a22290c3
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2017
---
# <a name="wcf-services-and-event-tracing-for-windows"></a><span data-ttu-id="9a20b-102">针对 Windows 的 WCF 服务和事件跟踪</span><span class="sxs-lookup"><span data-stu-id="9a20b-102">WCF Services and Event Tracing for Windows</span></span>
<span data-ttu-id="9a20b-103">此示例演示如何使用 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 中的分析跟踪在 Windows 事件跟踪 (ETW) 中发出事件。</span><span class="sxs-lookup"><span data-stu-id="9a20b-103">This sample demonstrates how to use the analytic tracing in [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] to emit events in Event Tracing for Windows (ETW).</span></span> <span data-ttu-id="9a20b-104">分析跟踪是在 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 堆栈中的关键点处发出的事件，用于在生产环境中排除 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 服务的故障。</span><span class="sxs-lookup"><span data-stu-id="9a20b-104">The analytic traces are events emitted at key points in the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] stack that allow troubleshooting of [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] services in production environment.</span></span>  
  
 <span data-ttu-id="9a20b-105">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 服务中的分析跟踪是可以在生产环境中以最小性能影响启用的跟踪。</span><span class="sxs-lookup"><span data-stu-id="9a20b-105">Analytic trace in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] services is tracing that can be turned on in a production environment with minimal impact on performance.</span></span> <span data-ttu-id="9a20b-106">这些跟踪都以事件的形式向 ETW 会话发出。</span><span class="sxs-lookup"><span data-stu-id="9a20b-106">These traces are emitted as events to an ETW session.</span></span>  
  
 <span data-ttu-id="9a20b-107">此示例包括一个基本 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 服务，事件从该服务向事件日志发出，使用事件查看器可以查看这些事件。</span><span class="sxs-lookup"><span data-stu-id="9a20b-107">This sample includes a basic [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service in which events are emitted from the service to the event log, which can be viewed using Event Viewer.</span></span> <span data-ttu-id="9a20b-108">该示例还可以启动一个专用 ETW 会话，用于侦听来自 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 服务的事件。</span><span class="sxs-lookup"><span data-stu-id="9a20b-108">It is also possible to start a dedicated ETW session that listens for events from the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service.</span></span> <span data-ttu-id="9a20b-109">该示例包括一个用于创建专用 ETW 会话的脚本，该会话将事件存储在可以使用事件查看器读取的二进制文件中。</span><span class="sxs-lookup"><span data-stu-id="9a20b-109">The sample includes a script to create a dedicated ETW session that stores events in a binary file that can be read using Event Viewer.</span></span>  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="9a20b-110">使用此示例</span><span class="sxs-lookup"><span data-stu-id="9a20b-110">To use this sample</span></span>  
  
1.  <span data-ttu-id="9a20b-111">使用 [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] 打开 EtwAnalyticTraceSample.sln 解决方案文件。</span><span class="sxs-lookup"><span data-stu-id="9a20b-111">Using [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)], open the EtwAnalyticTraceSample.sln solution file.</span></span>  
  
2.  <span data-ttu-id="9a20b-112">要生成解决方案，按 Ctrl+Shift+B。</span><span class="sxs-lookup"><span data-stu-id="9a20b-112">To build the solution, press CTRL+SHIFT+B.</span></span>  
  
3.  <span data-ttu-id="9a20b-113">若要运行解决方案，请按 Ctrl+F5。</span><span class="sxs-lookup"><span data-stu-id="9a20b-113">To run the solution, press CTRL+F5.</span></span>  
  
     <span data-ttu-id="9a20b-114">在 Web 浏览器中，单击**Calculator.svc**。</span><span class="sxs-lookup"><span data-stu-id="9a20b-114">In the Web browser, click **Calculator.svc**.</span></span> <span data-ttu-id="9a20b-115">服务的 WSDL 文档的 URI 应出现在浏览器中。</span><span class="sxs-lookup"><span data-stu-id="9a20b-115">The URI of the WSDL document for the service should appear in the browser.</span></span> <span data-ttu-id="9a20b-116">复制该 URI。</span><span class="sxs-lookup"><span data-stu-id="9a20b-116">Copy that URI.</span></span>  
  
     <span data-ttu-id="9a20b-117">默认情况下，服务开始在端口 1378 上侦听请求 (http://localhost:1378/Calculator.svc)。</span><span class="sxs-lookup"><span data-stu-id="9a20b-117">By default, the service starts listening for requests on port 1378 (http://localhost:1378/Calculator.svc).</span></span>  
  
4.  <span data-ttu-id="9a20b-118">运行 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 测试客户端 (WcfTestClient.exe)。</span><span class="sxs-lookup"><span data-stu-id="9a20b-118">Run the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] test client (WcfTestClient.exe).</span></span>  
  
     <span data-ttu-id="9a20b-119">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]测试客户端 (WcfTestClient.exe) 位于\<[!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)]安装目录 > \Common7\IDE\ WcfTestClient.exe (默认[!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)]安装目录为 C:\Program Files\Microsoft Visual Studio 10.0)。</span><span class="sxs-lookup"><span data-stu-id="9a20b-119">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] test client (WcfTestClient.exe) is located in the \<[!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] Install Dir>\Common7\IDE\ WcfTestClient.exe (default [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] install dir is C:\Program Files\Microsoft Visual Studio 10.0).</span></span>  
  
5.  <span data-ttu-id="9a20b-120">在[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]测试客户端，通过选择添加服务**文件**，，然后**添加服务**。</span><span class="sxs-lookup"><span data-stu-id="9a20b-120">Within the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] test client, add the service by selecting **File**, and then **Add Service**.</span></span>  
  
     <span data-ttu-id="9a20b-121">在输入框中添加终结点地址。</span><span class="sxs-lookup"><span data-stu-id="9a20b-121">Add the endpoint address in the input box.</span></span> <span data-ttu-id="9a20b-122">默认值为 http://localhost:1378/Calculator.svc。</span><span class="sxs-lookup"><span data-stu-id="9a20b-122">The default is http://localhost:1378/Calculator.svc.</span></span>  
  
6.  <span data-ttu-id="9a20b-123">打开事件查看器应用程序。</span><span class="sxs-lookup"><span data-stu-id="9a20b-123">Open the Event Viewer application.</span></span>  
  
     <span data-ttu-id="9a20b-124">在调用服务之前，请启动事件查看器并确保事件日志正在侦听从 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 服务发出的跟踪事件。</span><span class="sxs-lookup"><span data-stu-id="9a20b-124">Before invoking the service, start Event Viewer and ensure that the event log is listening for tracking events emitted from the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service.</span></span>  
  
7.  <span data-ttu-id="9a20b-125">从**启动**菜单上，选择**管理工具**，，然后**事件查看器**。</span><span class="sxs-lookup"><span data-stu-id="9a20b-125">From the **Start** menu, select **Administrative Tools**, and then **Event Viewer**.</span></span>  <span data-ttu-id="9a20b-126">启用**分析**和**调试**日志。</span><span class="sxs-lookup"><span data-stu-id="9a20b-126">Enable the **Analytic** and **Debug** logs.</span></span>  
  
8.  <span data-ttu-id="9a20b-127">在事件查看器中的树视图中，导航到**事件查看器**， **Applications and Services Logs**， **Microsoft**， **Windows**，，然后**应用程序服务器-应用程序**。</span><span class="sxs-lookup"><span data-stu-id="9a20b-127">In the tree view in Event Viewer, navigate to **Event Viewer**, **Applications and Services Logs**, **Microsoft**, **Windows**, and then **Application Server-Applications**.</span></span> <span data-ttu-id="9a20b-128">右键单击**应用程序服务器-应用程序**，选择**视图**，，然后**显示分析和调试日志**。</span><span class="sxs-lookup"><span data-stu-id="9a20b-128">Right-click **Application Server-Applications**, select **View**, and then **Show Analytic and Debug Logs**.</span></span>  
  
     <span data-ttu-id="9a20b-129">确保**显示分析和调试日志**选项处于选中状态。</span><span class="sxs-lookup"><span data-stu-id="9a20b-129">Ensure that the **Show Analytic and Debug Logs** option is checked.</span></span>  
  
9. <span data-ttu-id="9a20b-130">启用**分析**日志。</span><span class="sxs-lookup"><span data-stu-id="9a20b-130">Enable the **Analytic** log.</span></span>  
  
     <span data-ttu-id="9a20b-131">在事件查看器中的树视图中，导航到**事件查看器**， **Applications and Services Logs**， **Microsoft**， **Windows**，，然后**应用程序服务器-应用程序**。</span><span class="sxs-lookup"><span data-stu-id="9a20b-131">In the tree view in Event Viewer, navigate to **Event Viewer**, **Applications and Services Logs**, **Microsoft**, **Windows**, and then **Application Server-Applications**.</span></span> <span data-ttu-id="9a20b-132">右键单击**分析**和选择**启用日志**。</span><span class="sxs-lookup"><span data-stu-id="9a20b-132">Right-click **Analytic** and select **Enable Log**.</span></span>  
  
#### <a name="to-test-the-service"></a><span data-ttu-id="9a20b-133">测试服务</span><span class="sxs-lookup"><span data-stu-id="9a20b-133">To test the service</span></span>  
  
1.  <span data-ttu-id="9a20b-134">切换回 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 测试客户端，然后双击 `Divide` 并保留默认值（指定分母为 0）。</span><span class="sxs-lookup"><span data-stu-id="9a20b-134">Switch back to [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] test client and double-click `Divide` and keep the default values, which specify a denominator of 0.</span></span>  
  
     <span data-ttu-id="9a20b-135">如果分母为 0，则服务引发错误。</span><span class="sxs-lookup"><span data-stu-id="9a20b-135">If the denominator is 0, then the service throws a fault.</span></span>  
  
2.  <span data-ttu-id="9a20b-136">观察从服务发出的事件。</span><span class="sxs-lookup"><span data-stu-id="9a20b-136">Observe the events emitted from the service.</span></span>  
  
     <span data-ttu-id="9a20b-137">切换回事件查看器并导航到**事件查看器**， **Applications and Services Logs**， **Microsoft**， **Windows**，，然后**应用程序服务器-应用程序**。</span><span class="sxs-lookup"><span data-stu-id="9a20b-137">Switch back to Event Viewer and navigate to **Event Viewer**, **Applications and Services Logs**, **Microsoft**, **Windows**, and then **Application Server-Applications**.</span></span> <span data-ttu-id="9a20b-138">右键单击**分析**和选择**刷新**。</span><span class="sxs-lookup"><span data-stu-id="9a20b-138">Right-click **Analytic** and select **Refresh**.</span></span>  
  
     <span data-ttu-id="9a20b-139">WCF 分析跟踪事件显示在事件查看器中。</span><span class="sxs-lookup"><span data-stu-id="9a20b-139">The WCF analytic trace events are displayed in the event viewer.</span></span> <span data-ttu-id="9a20b-140">请注意，因为服务引发了错误，所以事件查看器中会显示错误跟踪事件。</span><span class="sxs-lookup"><span data-stu-id="9a20b-140">Notice that because a fault was thrown by the service an error trace event is displayed in the event viewer.</span></span>  
  
3.  <span data-ttu-id="9a20b-141">重复步骤 1 和 2，但是使用有效的输入。</span><span class="sxs-lookup"><span data-stu-id="9a20b-141">Repeat steps 1 and 2, but with valid inputs.</span></span> <span data-ttu-id="9a20b-142">`N2` 参数的值可以为 0 之外的任何数。</span><span class="sxs-lookup"><span data-stu-id="9a20b-142">The value of the `N2` parameter can be any number other than 0.</span></span>  
  
     <span data-ttu-id="9a20b-143">刷新分析通道以查看 WCF 事件，可以看到不包含任何错误事件。</span><span class="sxs-lookup"><span data-stu-id="9a20b-143">Refresh the analytic channel to view the WCF events do not include any error events.</span></span>  
  
 <span data-ttu-id="9a20b-144">该示例演示从 WCF 服务发出的分析跟踪事件。</span><span class="sxs-lookup"><span data-stu-id="9a20b-144">The sample demonstrates the analytic trace events emitted from a WCF service.</span></span>  
  
#### <a name="to-cleanup-optional"></a><span data-ttu-id="9a20b-145">清理（可选）</span><span class="sxs-lookup"><span data-stu-id="9a20b-145">To cleanup (Optional)</span></span>  
  
1.  <span data-ttu-id="9a20b-146">打开事件查看器。</span><span class="sxs-lookup"><span data-stu-id="9a20b-146">Open Event Viewer.</span></span>  
  
2.  <span data-ttu-id="9a20b-147">导航到**事件查看器**， **Applications and Services Logs**， **Microsoft**， **Windows**，，然后**应用程序服务器-应用程序**。</span><span class="sxs-lookup"><span data-stu-id="9a20b-147">Navigate to **Event Viewer**, **Applications and Services Logs**, **Microsoft**, **Windows**, and then **Application-Server-Applications**.</span></span> <span data-ttu-id="9a20b-148">右键单击**分析**和选择**禁用日志**。</span><span class="sxs-lookup"><span data-stu-id="9a20b-148">Right-click **Analytic** and select **Disable Log**.</span></span>  
  
3.  <span data-ttu-id="9a20b-149">导航到**事件查看器**， **Applications and Services Logs**， **Microsoft**， **Windows**，，然后**应用程序服务器-应用程序**。</span><span class="sxs-lookup"><span data-stu-id="9a20b-149">Navigate to **Event Viewer**, **Applications and Services Logs**, **Microsoft**, **Windows**, and then **Application-Server-Applications**.</span></span> <span data-ttu-id="9a20b-150">右键单击**分析**和选择**清除日志**。</span><span class="sxs-lookup"><span data-stu-id="9a20b-150">Right-click **Analytic** and select **Clear Log**.</span></span>  
  
4.  <span data-ttu-id="9a20b-151">选择**清除**选项以清除事件。</span><span class="sxs-lookup"><span data-stu-id="9a20b-151">Choose the **Clear** option to clear the events.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="9a20b-152">您的计算机上可能已安装这些示例。</span><span class="sxs-lookup"><span data-stu-id="9a20b-152">The samples may already be installed on your computer.</span></span> <span data-ttu-id="9a20b-153">在继续操作之前，请先检查以下（默认）目录：</span><span class="sxs-lookup"><span data-stu-id="9a20b-153">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="9a20b-154">如果此目录不存在，请访问 [针对 .NET Framework 4 的 Windows Communication Foundation (WCF) 和 Windows Workflow Foundation (WF) 示例](http://go.microsoft.com/fwlink/?LinkId=150780) 以下载所有 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 和 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 示例。</span><span class="sxs-lookup"><span data-stu-id="9a20b-154">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="9a20b-155">此示例位于以下目录：</span><span class="sxs-lookup"><span data-stu-id="9a20b-155">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Management\ETWTracing`  
  
## <a name="see-also"></a><span data-ttu-id="9a20b-156">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9a20b-156">See Also</span></span>  
 [<span data-ttu-id="9a20b-157">AppFabric 监视示例</span><span class="sxs-lookup"><span data-stu-id="9a20b-157">AppFabric Monitoring Samples</span></span>](http://go.microsoft.com/fwlink/?LinkId=193959)
