---
title: "使用文本文件跟踪"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 56a82682-73c2-4b91-a206-4d8bb12c561b
caps.latest.revision: "13"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: a2725c34b79b8c9dd05a9f9a071ef52e29527e02
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="tracking-using-a-text-file"></a><span data-ttu-id="e2951-102">使用文本文件跟踪</span><span class="sxs-lookup"><span data-stu-id="e2951-102">Tracking Using a Text File</span></span>
<span data-ttu-id="e2951-103">此示例演示如何通过创建自定义跟踪参与者来扩展 [!INCLUDE[wf](../../../../includes/wf-md.md)] 中的跟踪。</span><span class="sxs-lookup"><span data-stu-id="e2951-103">This sample demonstrates how to extend tracking in [!INCLUDE[wf](../../../../includes/wf-md.md)] by creating a custom tracking participant.</span></span> <span data-ttu-id="e2951-104">跟踪参与者是一些 .NET Framework 类，这些类将接收从运行时发出的跟踪记录。</span><span class="sxs-lookup"><span data-stu-id="e2951-104">Tracking participants are .NET Framework classes that receive tracking records from the runtime as they are emitted.</span></span> <span data-ttu-id="e2951-105">可以创建一个跟踪参与者以将跟踪事件传输给方案所需的任何目标。</span><span class="sxs-lookup"><span data-stu-id="e2951-105">You can create a tracking participant to transport the tracking events to whichever destination is required for your scenario.</span></span> <span data-ttu-id="e2951-106">例如，ETW（Windows 事件跟踪）跟踪参与者将作为 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 的一部分提供。</span><span class="sxs-lookup"><span data-stu-id="e2951-106">For example, ETW (Event Tracing for Windows) Tracking Participant is provided as part of the [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)].</span></span> <span data-ttu-id="e2951-107">此示例中的跟踪参与者以 XML 格式将记录写入文本文件。</span><span class="sxs-lookup"><span data-stu-id="e2951-107">The tracking participant in this sample writes the records in XML format to a text file.</span></span>  
  
## <a name="sample-details"></a><span data-ttu-id="e2951-108">示例详细信息</span><span class="sxs-lookup"><span data-stu-id="e2951-108">Sample details</span></span>  
 <span data-ttu-id="e2951-109">若要优化跟踪参与者的有用性和可靠性，则必须完成一些附加步骤以将跟踪参与者连接到运行时。</span><span class="sxs-lookup"><span data-stu-id="e2951-109">To optimize the usefulness and robustness of your tracking participant, some additional steps must be completed to properly wire the tracking participant to the runtime.</span></span> <span data-ttu-id="e2951-110">下表描述此示例中用于创建遵循最佳实践的跟踪参与者的类。</span><span class="sxs-lookup"><span data-stu-id="e2951-110">The following table describes the classes used in this sample to create a tracking participant that complies with best practices.</span></span>  
  
|<span data-ttu-id="e2951-111">类</span><span class="sxs-lookup"><span data-stu-id="e2951-111">Class</span></span>|<span data-ttu-id="e2951-112">描述</span><span class="sxs-lookup"><span data-stu-id="e2951-112">Description</span></span>|  
|-----------|-----------------|  
|`TextFileTrackingExtensionElement`|<span data-ttu-id="e2951-113"><xref:System.ServiceModel.Configuration.BehaviorExtensionElement> 用于定义用来配置文本文件跟踪参与者的配置节。</span><span class="sxs-lookup"><span data-stu-id="e2951-113">A <xref:System.ServiceModel.Configuration.BehaviorExtensionElement> is used to define the configuration section used to configure the text file tracking participant.</span></span> <span data-ttu-id="e2951-114">这将允许用户使用标准 .NET Framework 配置文件来指定日志文件的目标。</span><span class="sxs-lookup"><span data-stu-id="e2951-114">This allows users to specify the destination of the log file using standard .NET Framework configuration files.</span></span>|  
|`TextFileTrackingBehavior`|<span data-ttu-id="e2951-115">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 中的行为允许用户将扩展注入运行时。</span><span class="sxs-lookup"><span data-stu-id="e2951-115">Behaviors in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] allow users to inject extensions into the runtime.</span></span> <span data-ttu-id="e2951-116">当服务启动时，此行为会将跟踪参与者添加到服务中。</span><span class="sxs-lookup"><span data-stu-id="e2951-116">This behavior adds the tracking participant to the service when the service starts.</span></span>|  
|`TextFileTrackingParticipant`|<span data-ttu-id="e2951-117">一个跟踪参与者，它在运行时接收跟踪参与者并以 XML 的形式将这些参与者存储在日志文件中。</span><span class="sxs-lookup"><span data-stu-id="e2951-117">The tracking participant that receives tracking participants at runtime and stores them to a log file as XML.</span></span>|  
  
## <a name="behavior-extension-elements-configuration"></a><span data-ttu-id="e2951-118">行为扩展元素配置</span><span class="sxs-lookup"><span data-stu-id="e2951-118">Behavior Extension Elements Configuration</span></span>  
 <span data-ttu-id="e2951-119">若要利用先前使用 .NET Framework 配置文件描述的行为扩展元素，需要再执行一个步骤。</span><span class="sxs-lookup"><span data-stu-id="e2951-119">One more step is required to make use of the behavior extension element previously described using .NET Framework configuration files.</span></span> <span data-ttu-id="e2951-120">必须将下面的配置置于要使用扩展的配置文件中。</span><span class="sxs-lookup"><span data-stu-id="e2951-120">The following configuration must be placed in configuration files where the extension is to be used.</span></span>  
  
```xml  
<system.serviceModel>  
    <extensions>  
      <behaviorExtensions>  
        <add name="textFileTracking" type="Microsoft.Samples.TextFileTracking.TextFileTrackingExtensionElement, WFStockPriceApplication, Version=1.0.0.0, Culture=neutral, PublicKeyToken=null" />  
      </behaviorExtensions>  
    </extensions>  
…  
  </system.serviceModel>  
```  
  
> [!NOTE]
>  <span data-ttu-id="e2951-121">有关行为扩展元素配置的完整示例用法，请参见示例中的 Web.config 文件。</span><span class="sxs-lookup"><span data-stu-id="e2951-121">See the Web.config file in the sample for a complete example usage of behavior extension elements configuration.</span></span>  
  
## <a name="custom-tracking-records"></a><span data-ttu-id="e2951-122">自定义跟踪记录</span><span class="sxs-lookup"><span data-stu-id="e2951-122">Custom Tracking Records</span></span>  
 <span data-ttu-id="e2951-123">GetStockPrices.cs 文件演示如何从 <xref:System.Activities.CodeActivity> 中创建自定义跟踪记录。</span><span class="sxs-lookup"><span data-stu-id="e2951-123">The GetStockPrices.cs file demonstrates how to create custom tracking records from within a <xref:System.Activities.CodeActivity>.</span></span> <span data-ttu-id="e2951-124">在运行示例时，请查找该记录。</span><span class="sxs-lookup"><span data-stu-id="e2951-124">Look for this record when running the sample.</span></span>  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="e2951-125">使用此示例</span><span class="sxs-lookup"><span data-stu-id="e2951-125">To use this sample</span></span>  
  
1.  <span data-ttu-id="e2951-126">使用 [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] 打开 WFStockPriceApplication.sln 解决方案文件。</span><span class="sxs-lookup"><span data-stu-id="e2951-126">Using [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], open the WFStockPriceApplication.sln solution file.</span></span>  
  
2.  <span data-ttu-id="e2951-127">要生成解决方案，按 Ctrl+Shift+B。</span><span class="sxs-lookup"><span data-stu-id="e2951-127">To build the solution, press CTRL+SHIFT+B.</span></span>  
  
3.  <span data-ttu-id="e2951-128">若要运行解决方案，请按 Ctrl+F5。</span><span class="sxs-lookup"><span data-stu-id="e2951-128">To run the solution, press CTRL+F5.</span></span>  
  
     <span data-ttu-id="e2951-129">浏览器窗口打开和显示侦听应用程序的目录。</span><span class="sxs-lookup"><span data-stu-id="e2951-129">The browser window opens and shows the directory listing for the application.</span></span>  
  
4.  <span data-ttu-id="e2951-130">在浏览器中，单击 StockPriceService.xamlx。</span><span class="sxs-lookup"><span data-stu-id="e2951-130">In the browser, click StockPriceService.xamlx.</span></span>  
  
5.  <span data-ttu-id="e2951-131">浏览器将显示**StockPriceService**页，其中包含本地服务 wsdl 地址。</span><span class="sxs-lookup"><span data-stu-id="e2951-131">The browser displays the **StockPriceService** page, which contains the local service wsdl address.</span></span> <span data-ttu-id="e2951-132">复制此地址。</span><span class="sxs-lookup"><span data-stu-id="e2951-132">Copy this address.</span></span>  
  
     <span data-ttu-id="e2951-133">本地服务 wsdl 地址的示例为 http://localhost:53797/StockPriceService.xamlx?wsdl。</span><span class="sxs-lookup"><span data-stu-id="e2951-133">An example of the local service wsdl address is http://localhost:53797/StockPriceService.xamlx?wsdl.</span></span>  
  
6.  <span data-ttu-id="e2951-134">通过使用[!INCLUDE[fileExplorer](../../../../includes/fileexplorer-md.md)]，转到 [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] 文件夹（默认安装文件夹为 %SystemDrive%\Program Files\Microsoft Visual Studio 10.0）。</span><span class="sxs-lookup"><span data-stu-id="e2951-134">Using [!INCLUDE[fileExplorer](../../../../includes/fileexplorer-md.md)], go to your [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] folder (the default installation folder is %SystemDrive%\Program Files\Microsoft Visual Studio 10.0).</span></span> <span data-ttu-id="e2951-135">然后找到 Common7\IDE\ 子文件夹。</span><span class="sxs-lookup"><span data-stu-id="e2951-135">Then locate the Common7\IDE\ subfolder.</span></span>  
  
7.  <span data-ttu-id="e2951-136">双击 WcfTestClient.exe 文件以启动 WCF 测试客户端。</span><span class="sxs-lookup"><span data-stu-id="e2951-136">Double-click the WcfTestClient.exe file to launch the WCF Test Client.</span></span>  
  
8.  <span data-ttu-id="e2951-137">在 WCF 测试客户端中，选择**添加服务...**</span><span class="sxs-lookup"><span data-stu-id="e2951-137">In the WCF Test Client, select **Add Service…**</span></span> <span data-ttu-id="e2951-138">从**文件**菜单。</span><span class="sxs-lookup"><span data-stu-id="e2951-138">from the **File** menu.</span></span>  
  
9. <span data-ttu-id="e2951-139">将刚刚复制的 URL 粘贴到文本框中。</span><span class="sxs-lookup"><span data-stu-id="e2951-139">Paste the URL you just copied into the text box.</span></span>  
  
10. <span data-ttu-id="e2951-140">单击**确定**关闭对话框。</span><span class="sxs-lookup"><span data-stu-id="e2951-140">Click **OK** to close the dialog.</span></span>  
  
11. <span data-ttu-id="e2951-141">使用 WCF 测试客户端来测试服务。</span><span class="sxs-lookup"><span data-stu-id="e2951-141">Test the service using the WCF Test Client.</span></span>  
  
    1.  <span data-ttu-id="e2951-142">在 WCF 测试客户端中，双击**getstockprice （)**下**IStockPriceService**节点。</span><span class="sxs-lookup"><span data-stu-id="e2951-142">In the WCF Test Client, double-click **GetStockPrice()** under the **IStockPriceService** node.</span></span>  
  
         <span data-ttu-id="e2951-143">**Getstockprice （)**方法将显示在右窗格中，带有一个参数。</span><span class="sxs-lookup"><span data-stu-id="e2951-143">The **GetStockPrice()** method appears in the right pane, with one parameter.</span></span>  
  
    2.  <span data-ttu-id="e2951-144">键入 Contoso 作为该参数的值。</span><span class="sxs-lookup"><span data-stu-id="e2951-144">Type in Contoso as the value for the parameter.</span></span>  
  
    3.  <span data-ttu-id="e2951-145">单击**调用**。</span><span class="sxs-lookup"><span data-stu-id="e2951-145">Click **Invoke**.</span></span>  
  
12. <span data-ttu-id="e2951-146">查看位于 %APPDATA%\trackingRecords.log 处的应用程序数据目录中的日志文件中的跟踪事件。</span><span class="sxs-lookup"><span data-stu-id="e2951-146">See the tracked events in the log file located in your application data directory at %APPDATA%\trackingRecords.log.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="e2951-147">%APPDATA%是一个环境变量，将解析为 %SystemDrive%\Users\\< 用户名\>中的 \AppData\Roaming [!INCLUDE[wv](../../../../includes/wv-md.md)]， [!INCLUDE[lserver](../../../../includes/lserver-md.md)]，或 Windows Server 2008。</span><span class="sxs-lookup"><span data-stu-id="e2951-147">The %APPDATA% is an environment variable that resolves to %SystemDrive%\Users\\<username\>\AppData\Roaming in [!INCLUDE[wv](../../../../includes/wv-md.md)], [!INCLUDE[lserver](../../../../includes/lserver-md.md)], or Windows Server 2008.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="e2951-148">您的计算机上可能已安装这些示例。</span><span class="sxs-lookup"><span data-stu-id="e2951-148">The samples may already be installed on your computer.</span></span> <span data-ttu-id="e2951-149">在继续操作之前，请先检查以下（默认）目录：</span><span class="sxs-lookup"><span data-stu-id="e2951-149">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="e2951-150">如果此目录不存在，请访问 [针对 .NET Framework 4 的 Windows Communication Foundation (WCF) 和 Windows Workflow Foundation (WF) 示例](http://go.microsoft.com/fwlink/?LinkId=150780) 以下载所有 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 和 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 示例。</span><span class="sxs-lookup"><span data-stu-id="e2951-150">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="e2951-151">此示例位于以下目录：</span><span class="sxs-lookup"><span data-stu-id="e2951-151">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Tracking\TextFileTracking`  
  
## <a name="see-also"></a><span data-ttu-id="e2951-152">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e2951-152">See Also</span></span>  
 [<span data-ttu-id="e2951-153">AppFabric 监视示例</span><span class="sxs-lookup"><span data-stu-id="e2951-153">AppFabric Monitoring Samples</span></span>](http://go.microsoft.com/fwlink/?LinkId=193959)
