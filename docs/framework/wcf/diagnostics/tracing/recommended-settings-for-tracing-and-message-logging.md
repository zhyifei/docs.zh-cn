---
title: 跟踪和消息日志记录的推荐设置
ms.date: 03/30/2017
ms.assetid: c6aca6e8-704e-4779-a9ef-50c46850249e
ms.openlocfilehash: fa6dc74a26f6a76591a15c549a892f31a65c521e
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59132350"
---
# <a name="recommended-settings-for-tracing-and-message-logging"></a><span data-ttu-id="dfa15-102">跟踪和消息日志记录的推荐设置</span><span class="sxs-lookup"><span data-stu-id="dfa15-102">Recommended Settings for Tracing and Message Logging</span></span>
<span data-ttu-id="dfa15-103">本主题描述用于不同操作环境的跟踪和消息日志记录的推荐设置。</span><span class="sxs-lookup"><span data-stu-id="dfa15-103">This topic describes recommended tracing and message logging settings for different operating environments.</span></span>  
  
## <a name="recommended-settings-for-a-production-environment"></a><span data-ttu-id="dfa15-104">生产环境中的推荐设置</span><span class="sxs-lookup"><span data-stu-id="dfa15-104">Recommended Settings for a Production Environment</span></span>  
 <span data-ttu-id="dfa15-105">对于生产环境，如果您使用的是 WCF 跟踪源，请将 `switchValue` 设置为“警告”。</span><span class="sxs-lookup"><span data-stu-id="dfa15-105">For a production environment, if you are using WCF trace sources, set the `switchValue` to Warning.</span></span> <span data-ttu-id="dfa15-106">如果您使用的是 WCF `System.ServiceModel` 跟踪源，请将 `switchValue` 属性设置为 `Warning`，并将 `propagateActivity` 属性设置为 `true`。</span><span class="sxs-lookup"><span data-stu-id="dfa15-106">If you are using the WCF `System.ServiceModel` trace source, set the `switchValue` attribute to `Warning` and the `propagateActivity` attribute to `true`.</span></span> <span data-ttu-id="dfa15-107">如果您使用的是用户定义的跟踪源，请将 `switchValue` 属性设置为 `Warning, ActivityTracing`。</span><span class="sxs-lookup"><span data-stu-id="dfa15-107">If you are using a user-defined trace source, set the `switchValue` attribute to `Warning, ActivityTracing`.</span></span> <span data-ttu-id="dfa15-108">可以使用手动完成这[配置编辑器工具 (SvcConfigEditor.exe)](../../../../../docs/framework/wcf/configuration-editor-tool-svcconfigeditor-exe.md)。</span><span class="sxs-lookup"><span data-stu-id="dfa15-108">This can be done manually using the [Configuration Editor Tool (SvcConfigEditor.exe)](../../../../../docs/framework/wcf/configuration-editor-tool-svcconfigeditor-exe.md).</span></span> <span data-ttu-id="dfa15-109">如果你没有预测性能情况，则可以在上述所有情况中，将 `switchValue` 属性设置为 `Information`，这将生成大量的跟踪数据。</span><span class="sxs-lookup"><span data-stu-id="dfa15-109">If you do not anticipate a hit in performance, you can set the `switchValue` attribute to `Information` in all the previously mentioned cases, which generates a fairly large amount of trace data.</span></span> <span data-ttu-id="dfa15-110">下面的示例演示这些推荐的设置。</span><span class="sxs-lookup"><span data-stu-id="dfa15-110">The following example demonstrates these recommended settings.</span></span>  
  
```xml  
<configuration>  
 <system.diagnostics>  
  <sources>  
    <source name="System.ServiceModel"  
            switchValue="Warning"  
            propagateActivity="true" >  
      <listeners>  
        <add name="xml"/>  
      </listeners>  
    </source>  
    <source name="myUserTraceSource"  
            switchValue="Warning, ActivityTracing">  
      <listeners>  
        <add name="xml"/>  
      </listeners>  
    </source>  
  </sources>  
  <sharedListeners>  
    <add name="xml"  
         type="System.Diagnostics.XmlWriterTraceListener"  
               initializeData="C:\logs\Traces.svclog" />  
  </sharedListeners>  
 </system.diagnostics>  
  
<system.serviceModel>  
  <diagnostics wmiProviderEnabled="true">  
  </diagnostics>  
 </system.serviceModel>  
</configuration>  
```  
  
## <a name="recommended-settings-for-deployment-or-debugging"></a><span data-ttu-id="dfa15-111">用于部署或调试的推荐设置</span><span class="sxs-lookup"><span data-stu-id="dfa15-111">Recommended Settings for Deployment or Debugging</span></span>  
 <span data-ttu-id="dfa15-112">对于部署或调试环境，请为用户定义的或 `Information` 跟踪源选择 `Verbose` 或 `ActivityTracing`，以及 `System.ServiceModel`。</span><span class="sxs-lookup"><span data-stu-id="dfa15-112">For deployment or debugging environment, choose `Information` or `Verbose`, along with `ActivityTracing` for either a user-defined or `System.ServiceModel` trace source.</span></span> <span data-ttu-id="dfa15-113">若要增强调试功能，也应将其他跟踪源 (`System.ServiceModel.MessageLogging`) 添加到配置中以启用消息日志记录。</span><span class="sxs-lookup"><span data-stu-id="dfa15-113">To enhance debugging, you should also add an additional trace source (`System.ServiceModel.MessageLogging`) to the configuration to enable message logging.</span></span> <span data-ttu-id="dfa15-114">请注意，`switchValue` 属性对此跟踪源没有任何影响。</span><span class="sxs-lookup"><span data-stu-id="dfa15-114">Notice that the `switchValue` attribute has no impact on this trace source.</span></span>  
  
 <span data-ttu-id="dfa15-115">下面的示例通过使用利用了 `XmlWriterTraceListener` 的共享侦听器来演示推荐的设置。</span><span class="sxs-lookup"><span data-stu-id="dfa15-115">The following example demonstrates the recommended settings, using a shared listener that utilizes the `XmlWriterTraceListener`.</span></span>  
  
```xml  
<configuration>  
 <system.diagnostics>  
  <sources>  
    <source name="System.ServiceModel"  
            switchValue="Information, ActivityTracing"  
            propagateActivity="true" >  
      <listeners>  
        <add name="xml"/>  
      </listeners>  
    </source>  
    <source name="System.ServiceModel.MessageLogging">  
      <listeners>  
        <add name="xml"/>  
      </listeners>  
    </source>  
    <source name="myUserTraceSource"  
            switchValue="Information, ActivityTracing">  
      <listeners>  
        <add name="xml"/>  
      </listeners>  
    </source>  
  </sources>  
  <sharedListeners>  
    <add name="xml"  
         type="System.Diagnostics.XmlWriterTraceListener"  
               initializeData="C:\logs\Traces.svclog" />  
  </sharedListeners>  
 </system.diagnostics>  
  
 <system.serviceModel>  
  <diagnostics wmiProviderEnabled="true">  
      <messageLogging   
           logEntireMessage="true"   
           logMalformedMessages="true"  
           logMessagesAtServiceLevel="true"   
           logMessagesAtTransportLevel="true"  
           maxMessagesToLog="3000"   
       />  
  </diagnostics>  
 </system.serviceModel>  
</configuration>  
```  
  
## <a name="using-wmi-to-modify-settings"></a><span data-ttu-id="dfa15-116">使用 WMI 修改设置</span><span class="sxs-lookup"><span data-stu-id="dfa15-116">Using WMI to Modify Settings</span></span>  
 <span data-ttu-id="dfa15-117">可以使用 WMI 更改运行时的配置设置（通过按照上述配置示例，启用配置中的 `wmiProviderEnabled` 属性）。</span><span class="sxs-lookup"><span data-stu-id="dfa15-117">You can use WMI to change configuration settings at runtime (by enabling the `wmiProviderEnabled` attribute in the configuration, as demonstrated in the previously configuration example).</span></span> <span data-ttu-id="dfa15-118">例如，可以在运行时使用 CIM Studio 中的 WMI 将跟踪源级别从“警告”更改为“信息”。</span><span class="sxs-lookup"><span data-stu-id="dfa15-118">For example, you can use WMI within the CIM Studio to change the trace source levels from Warning to Information at runtime.</span></span> <span data-ttu-id="dfa15-119">应该注意，这种方式的即时调试的性能开销可能非常高。</span><span class="sxs-lookup"><span data-stu-id="dfa15-119">You should be aware that the performance cost of live debugging in this way can be very high.</span></span> <span data-ttu-id="dfa15-120">有关使用 WMI 的详细信息，请参阅[使用 Windows Management Instrumentation 进行诊断](../../../../../docs/framework/wcf/diagnostics/wmi/index.md)主题。</span><span class="sxs-lookup"><span data-stu-id="dfa15-120">For more information about using WMI, see the [Using Windows Management Instrumentation for Diagnostics](../../../../../docs/framework/wcf/diagnostics/wmi/index.md) topic.</span></span>  
  
## <a name="enable-correlated-events-in-aspnet-tracing"></a><span data-ttu-id="dfa15-121">在 ASP.NET 跟踪中启用相关事件</span><span class="sxs-lookup"><span data-stu-id="dfa15-121">Enable Correlated Events in ASP.NET Tracing</span></span>  
 <span data-ttu-id="dfa15-122">除非启用了 ASP.NET 事件跟踪，否则 ASP.NET 事件不会设置关联 ID (ActivityID)。</span><span class="sxs-lookup"><span data-stu-id="dfa15-122">ASP.NET events do not set the correlation ID (ActivityID) unless ASP.NET event tracing is turned on.</span></span> <span data-ttu-id="dfa15-123">若要正确查看相关的事件，必须启用 ASP.NET 事件跟踪命令控制台中使用以下命令，这可以通过转到**启动**，**运行**并键入**cmd**,</span><span class="sxs-lookup"><span data-stu-id="dfa15-123">To see correlated events properly, you have to turn on ASP.NET events tracing using the following command in the command console, which can be invoked by going to **Start**, **Run** and type **cmd**,</span></span>  
  
```  
logman start mytrace -pf logman.providers -o test.etl –ets  
```  
  
 <span data-ttu-id="dfa15-124">若要关闭 ASP.NET 事件跟踪，请使用以下命令：</span><span class="sxs-lookup"><span data-stu-id="dfa15-124">To turn off tracing of ASP.NET events, use the following command,</span></span>  
  
```  
logman stop mytrace -ets  
```  
  
## <a name="see-also"></a><span data-ttu-id="dfa15-125">请参阅</span><span class="sxs-lookup"><span data-stu-id="dfa15-125">See also</span></span>

- [<span data-ttu-id="dfa15-126">使用 Windows Management Instrumentation 进行诊断</span><span class="sxs-lookup"><span data-stu-id="dfa15-126">Using Windows Management Instrumentation for Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/index.md)
