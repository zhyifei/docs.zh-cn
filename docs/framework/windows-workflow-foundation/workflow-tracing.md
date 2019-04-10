---
title: 工作流跟踪
ms.date: 03/30/2017
ms.assetid: 18737989-0502-4367-b5f6-617ebfb77c96
ms.openlocfilehash: 92497768e7e8d720cdcc7c8f2c7c04b4dfcc47b4
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59224931"
---
# <a name="workflow-tracing"></a><span data-ttu-id="0bf55-102">工作流跟踪</span><span class="sxs-lookup"><span data-stu-id="0bf55-102">Workflow Tracing</span></span>
<span data-ttu-id="0bf55-103">工作流跟踪提供了一种使用 .NET Framework 跟踪侦听器捕获诊断信息的方法。</span><span class="sxs-lookup"><span data-stu-id="0bf55-103">Workflow tracing offers a way to capture diagnostic information using .NET Framework trace listeners.</span></span> <span data-ttu-id="0bf55-104">如果检测到应用程序存在问题，可以启用跟踪，然后在解决问题之后再次禁用跟踪。</span><span class="sxs-lookup"><span data-stu-id="0bf55-104">Tracing can be enabled if a problem is detected with the application and then disabled again once the problem is resolved.</span></span> <span data-ttu-id="0bf55-105">可以通过两种方法为工作流启用调试跟踪。</span><span class="sxs-lookup"><span data-stu-id="0bf55-105">There are two ways you could enable debug tracing for workflows.</span></span> <span data-ttu-id="0bf55-106">您可以使用事件跟踪查看器配置调试跟踪，也可以使用 <xref:System.Diagnostics> 向文件发送跟踪事件。</span><span class="sxs-lookup"><span data-stu-id="0bf55-106">You can configure it using the Event Trace viewer or you can use <xref:System.Diagnostics> to send trace events to a file.</span></span>  
  
## <a name="enabling-debug-tracing-in-etw"></a><span data-ttu-id="0bf55-107">在 ETW 中启用调试跟踪</span><span class="sxs-lookup"><span data-stu-id="0bf55-107">Enabling Debug Tracing in ETW</span></span>  
 <span data-ttu-id="0bf55-108">若要使用 ETW 启用跟踪，请在事件查看器中启用调试通道：</span><span class="sxs-lookup"><span data-stu-id="0bf55-108">To enable tracing using ETW, enable the Debug channel in Event Viewer:</span></span>  
  
1.  <span data-ttu-id="0bf55-109">在事件查看器中导航到分析和调试日志节点。</span><span class="sxs-lookup"><span data-stu-id="0bf55-109">Navigate to analytic and debug logs node in Event Viewer.</span></span>  
  
2.  <span data-ttu-id="0bf55-110">在事件查看器中树视图中，导航到**事件查看器-> 应用程序和服务日志-> Microsoft-> Windows-> 应用程序服务器-应用程序**。</span><span class="sxs-lookup"><span data-stu-id="0bf55-110">In the tree view in Event Viewer, navigate to **Event Viewer->Applications and Services Logs->Microsoft->Windows->Application Server-Applications**.</span></span> <span data-ttu-id="0bf55-111">右键单击**应用程序服务器-应用程序**，然后选择**视图-> 显示分析和调试日志**。</span><span class="sxs-lookup"><span data-stu-id="0bf55-111">Right-click **Application Server-Applications** and select **View->Show Analytic and Debug Logs**.</span></span> <span data-ttu-id="0bf55-112">右键单击**调试**，然后选择**启用日志**。</span><span class="sxs-lookup"><span data-stu-id="0bf55-112">Right-click **Debug** and select **Enable Log**.</span></span>  
  
3.  <span data-ttu-id="0bf55-113">当工作流运行调试并将跟踪发出到 ETW 调试通道时，即可在事件查看器中查看这些跟踪。</span><span class="sxs-lookup"><span data-stu-id="0bf55-113">When a workflow runs the debug and traces are emitted to ETW debug channel, they can be viewed in the Event Viewer.</span></span> <span data-ttu-id="0bf55-114">导航到**事件查看器-> 应用程序和服务日志-> Microsoft-> Windows-> 应用程序服务器-应用程序**。</span><span class="sxs-lookup"><span data-stu-id="0bf55-114">Navigate to **Event Viewer->Applications and Services Logs->Microsoft->Windows->Application Server-Applications**.</span></span> <span data-ttu-id="0bf55-115">右键单击**调试**，然后选择**刷新**。</span><span class="sxs-lookup"><span data-stu-id="0bf55-115">Right-click **Debug** and select **Refresh**.</span></span>  
  
4.  <span data-ttu-id="0bf55-116">默认跟踪分析缓冲区大小仅为 4 KB；建议将此大小增大到 32 KB。</span><span class="sxs-lookup"><span data-stu-id="0bf55-116">The default analytic trace buffer size is only 4 kilobytes (KB); it is recommended to increase the size to 32 KB.</span></span> <span data-ttu-id="0bf55-117">为此，请执行下列步骤。</span><span class="sxs-lookup"><span data-stu-id="0bf55-117">To do this, perform the following steps.</span></span>  
  
    1.  <span data-ttu-id="0bf55-118">在当前框架目录 (例如，C:\Windows\Microsoft.NET\Framework\v4.0.21203) 中执行以下命令：</span><span class="sxs-lookup"><span data-stu-id="0bf55-118">Execute the following command in the current framework directory (for example, C:\Windows\Microsoft.NET\Framework\v4.0.21203):</span></span> `wevtutil um Microsoft.Windows.ApplicationServer.Applications.man`  
  
    2.  <span data-ttu-id="0bf55-119">更改\<bufferSize > 为 32 Windows.ApplicationServer.Applications.man 文件中的值。</span><span class="sxs-lookup"><span data-stu-id="0bf55-119">Change the \<bufferSize> value in the Windows.ApplicationServer.Applications.man file to 32.</span></span>  
  
        ```xml  
        <channel name="Microsoft-Windows-Application Server-Applications/Analytic" chid="ANALYTIC_CHANNEL" symbol="ANALYTIC_CHANNEL" type="Analytic" enabled="false" isolation="Application" message="$(string.MICROSOFT_WINDOWS_APPLICATIONSERVER_APPLICATIONS.channel.ANALYTIC_CHANNEL.message)" >  
                    <publishing>  
                      <bufferSize>32</bufferSize>  
                    </publishing>  
                  </channel>  
        ```  
  
    3.  <span data-ttu-id="0bf55-120">在当前框架目录 (例如，C:\Windows\Microsoft.NET\Framework\v4.0.21203) 中执行以下命令：</span><span class="sxs-lookup"><span data-stu-id="0bf55-120">Execute the following command in the current framework directory (for example, C:\Windows\Microsoft.NET\Framework\v4.0.21203):</span></span> `wevtutil im Microsoft.Windows.ApplicationServer.Applications.man`  
  
> [!NOTE]
>  <span data-ttu-id="0bf55-121">如果使用.NET Framework 4 Client Profile，必须先从.NET Framework 4 目录运行以下命令来注册 ETW 清单：</span><span class="sxs-lookup"><span data-stu-id="0bf55-121">If you are using the .NET Framework 4 Client Profile, you must first register the ETW manifest by running the following command from the .NET Framework 4 directory:</span></span> `ServiceModelReg.exe –i –c:etw`  
  
## <a name="enabling-debug-tracing-using-systemdiagnostics"></a><span data-ttu-id="0bf55-122">使用 System.Diagnostics 启用调试跟踪</span><span class="sxs-lookup"><span data-stu-id="0bf55-122">Enabling Debug Tracing using System.Diagnostics</span></span>  
 <span data-ttu-id="0bf55-123">上述侦听器可以在工作流应用程序的 App.config 文件或工作流服务的 Web.config 中配置。</span><span class="sxs-lookup"><span data-stu-id="0bf55-123">These listeners can be configured in the App.config file of the workflow application, or the Web.config for a workflow service.</span></span> <span data-ttu-id="0bf55-124">在此示例中， [TextWriterTraceListener](https://go.microsoft.com/fwlink/?LinkId=165424)配置为在当前目录的 MyTraceLog.txt 文件中保存跟踪信息。</span><span class="sxs-lookup"><span data-stu-id="0bf55-124">In this example, a [TextWriterTraceListener](https://go.microsoft.com/fwlink/?LinkId=165424) is configured to save tracing information to the MyTraceLog.txt file in the current directory.</span></span>  
  
```xml  
<configuration>  
  <system.diagnostics>  
    <sources>  
      <source name="System.Activities" switchValue="Information">  
        <listeners>  
          <add name="textListener" />  
          <remove name="Default" />  
        </listeners>  
      </source>  
    </sources>  
    <sharedListeners>  
      <add name="textListener"  
           type="System.Diagnostics.TextWriterTraceListener"  
           initializeData="MyTraceLog.txt"  
           traceOutputOptions="ProcessId, DateTime" />  
    </sharedListeners>  
    <trace autoflush="true" indentsize="4">  
      <listeners>  
        <add name="textListener" />  
      </listeners>  
    </trace>  
  </system.diagnostics>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="0bf55-125">请参阅</span><span class="sxs-lookup"><span data-stu-id="0bf55-125">See also</span></span>

- [<span data-ttu-id="0bf55-126">Windows Server App Fabric 监视</span><span class="sxs-lookup"><span data-stu-id="0bf55-126">Windows Server App Fabric Monitoring</span></span>](https://go.microsoft.com/fwlink/?LinkId=201273)
- [<span data-ttu-id="0bf55-127">使用 App Fabric 监视应用程序</span><span class="sxs-lookup"><span data-stu-id="0bf55-127">Monitoring Applications with App Fabric</span></span>](https://go.microsoft.com/fwlink/?LinkId=201275)
