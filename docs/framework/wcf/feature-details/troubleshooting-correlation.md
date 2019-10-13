---
title: 针对相关的疑难解答
ms.date: 03/30/2017
ms.assetid: 98003875-233d-4512-a688-4b2a1b0b5371
ms.openlocfilehash: d4b7b4ecd724416256cf0b2499d7180200f4e75c
ms.sourcegitcommit: 9c3a4f2d3babca8919a1e490a159c1500ba7a844
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/12/2019
ms.locfileid: "72291552"
---
# <a name="troubleshooting-correlation"></a><span data-ttu-id="9c0df-102">针对相关的疑难解答</span><span class="sxs-lookup"><span data-stu-id="9c0df-102">Troubleshooting Correlation</span></span>
<span data-ttu-id="9c0df-103">相关用于在工作流服务消息之间和工作流服务消息与正确的工作流实例之间建立关联，如果未正确配置相关，则将接收不到消息，且应用程序无法正常运行。</span><span class="sxs-lookup"><span data-stu-id="9c0df-103">Correlation is used to relate workflow service messages to each other and to the correct workflow instance, but if it is not configured correctly, messages will not be received and applications will not work correctly.</span></span> <span data-ttu-id="9c0df-104">本主题概述了对相关问题进行疑难解答的几种方法，还列出了使用相关时可能出现的一些常见问题。</span><span class="sxs-lookup"><span data-stu-id="9c0df-104">This topic provides an overview of several methods for troubleshooting correlation issues, and also lists some common issues that can occur when you use correlation.</span></span>

## <a name="handle-the-unknownmessagereceived-event"></a><span data-ttu-id="9c0df-105">处理 UnknownMessageReceived 事件</span><span class="sxs-lookup"><span data-stu-id="9c0df-105">Handle the UnknownMessageReceived Event</span></span>
 <span data-ttu-id="9c0df-106">服务接收到未知消息（包括无法与现有实例关联的消息）时，将发生 <xref:System.ServiceModel.ServiceHostBase.UnknownMessageReceived> 事件。</span><span class="sxs-lookup"><span data-stu-id="9c0df-106">The <xref:System.ServiceModel.ServiceHostBase.UnknownMessageReceived> event occurs when an unknown message is received by a service, including messages that cannot be correlated to an existing instance.</span></span> <span data-ttu-id="9c0df-107">对于自承载服务，可在主机应用程序中处理此事件。</span><span class="sxs-lookup"><span data-stu-id="9c0df-107">For self-hosted services, this event can be handled in the host application.</span></span>

```csharp
host.UnknownMessageReceived += delegate(object sender, UnknownMessageReceivedEventArgs e)
{
    Console.WriteLine("Unknown Message Received:");
    Console.WriteLine(e.Message);
};
```

 <span data-ttu-id="9c0df-108">对于 Web 承载的服务，可通过从 <xref:System.ServiceModel.Activities.Activation.WorkflowServiceHostFactory> 派生类并重写  <xref:System.ServiceModel.Activities.Activation.WorkflowServiceHostFactory.CreateWorkflowServiceHost%2A> 来处理此事件。</span><span class="sxs-lookup"><span data-stu-id="9c0df-108">For Web-hosted services, this event can be handled by deriving a class from <xref:System.ServiceModel.Activities.Activation.WorkflowServiceHostFactory> and overriding <xref:System.ServiceModel.Activities.Activation.WorkflowServiceHostFactory.CreateWorkflowServiceHost%2A>.</span></span>

```csharp
class CustomFactory : WorkflowServiceHostFactory
{
    protected override WorkflowServiceHost CreateWorkflowServiceHost(Activity activity, Uri[] baseAddresses)
    {
        // Create the WorkflowServiceHost.
        WorkflowServiceHost host = new WorkflowServiceHost(activity, baseAddresses);

        // Handle the UnknownMessageReceived event.
        host.UnknownMessageReceived += delegate(object sender, UnknownMessageReceivedEventArgs e)
        {
            Console.WriteLine("Unknown Message Received:");
            Console.WriteLine(e.Message);
        };

        return host;
    }
}
```

 <span data-ttu-id="9c0df-109">随后可在服务的 <xref:System.ServiceModel.Activities.Activation.WorkflowServiceHostFactory> 文件中指定此自定义 `svc`。</span><span class="sxs-lookup"><span data-stu-id="9c0df-109">This custom <xref:System.ServiceModel.Activities.Activation.WorkflowServiceHostFactory> can then be specified in the `svc` file for the service.</span></span>

```
<% @ServiceHost Language="C#" Service="OrderServiceWorkflow" Factory="CustomFactory" %>
```

 <span data-ttu-id="9c0df-110">调用此处理程序时，消息可以使用 <xref:System.ServiceModel.UnknownMessageReceivedEventArgs.Message%2A> 的 <xref:System.ServiceModel.UnknownMessageReceivedEventArgs> 属性进行检索，并且类似于下面的消息。</span><span class="sxs-lookup"><span data-stu-id="9c0df-110">When this handler is invoked, the message can be retrieved by using the <xref:System.ServiceModel.UnknownMessageReceivedEventArgs.Message%2A> property of the <xref:System.ServiceModel.UnknownMessageReceivedEventArgs>, and will resemble the following message.</span></span>

```xml
<s:Envelope xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">
  <s:Header>
    <To s:mustUnderstand="1" xmlns="http://schemas.microsoft.com/ws/2005/05/addressing/none">http://localhost:8080/OrderService</To>
    <Action s:mustUnderstand="1" xmlns="http://schemas.microsoft.com/ws/2005/05/addressing/none">http://tempuri.org/IService/AddItem</Action>
  </s:Header>
  <s:Body>
    <AddItem xmlns="http://tempuri.org/">
      <Item>Books</Item>
    </AddItem>
  </s:Body>
</s:Envelope>
```

 <span data-ttu-id="9c0df-111">检查调度到 <xref:System.ServiceModel.ServiceHostBase.UnknownMessageReceived> 处理程序的消息可能会提供有关消息未与工作流服务实例关联的原因的线索。</span><span class="sxs-lookup"><span data-stu-id="9c0df-111">Inspecting messages dispatched to the <xref:System.ServiceModel.ServiceHostBase.UnknownMessageReceived> handler may provide clues about why the message did not correlate to an instance of the workflow service.</span></span>

## <a name="use-tracking-to-monitor-the-progress-of-the-workflow"></a><span data-ttu-id="9c0df-112">使用跟踪监视工作流进度</span><span class="sxs-lookup"><span data-stu-id="9c0df-112">Use Tracking to Monitor the Progress of the Workflow</span></span>
 <span data-ttu-id="9c0df-113">通过跟踪可监视工作流的进度。</span><span class="sxs-lookup"><span data-stu-id="9c0df-113">Tracking provides a way to monitor the progress of a workflow.</span></span> <span data-ttu-id="9c0df-114">默认情况下，将针对工作流生命周期事件、活动生命周期事件、错误传播以及书签恢复发出跟踪记录。</span><span class="sxs-lookup"><span data-stu-id="9c0df-114">By default, tracking records are emitted for workflow life-cycle events, activity life-cycle events, fault propagation, and bookmark resumption.</span></span> <span data-ttu-id="9c0df-115">此外，自定义活动也可以发出自定义跟踪记录。</span><span class="sxs-lookup"><span data-stu-id="9c0df-115">Additionally, custom tracking records can be emitted by custom activities.</span></span> <span data-ttu-id="9c0df-116">对相关问题进行疑难解答时，活动跟踪记录、书签恢复记录以及错误传播记录是最有用的。</span><span class="sxs-lookup"><span data-stu-id="9c0df-116">When troubleshooting correlation, the activity tracking records, the bookmark resumption records, and the fault propagation records are the most useful.</span></span> <span data-ttu-id="9c0df-117">活动跟踪记录可用于确定工作流的当前进度，并有助于识别当前正等待消息的消息传递活动。</span><span class="sxs-lookup"><span data-stu-id="9c0df-117">The activity tracking records can be used to determine the current progress of the workflow and can help identify which messaging activity is currently waiting for messages.</span></span> <span data-ttu-id="9c0df-118">书签恢复记录很有用是因为这些记录可指示工作流已接收到消息，而错误传播记录则提供工作流中所有错误的记录。</span><span class="sxs-lookup"><span data-stu-id="9c0df-118">Bookmark resumption records are useful because they indicate that a message was received by the workflow, and fault propagation records provide a record of any faults in the workflow.</span></span> <span data-ttu-id="9c0df-119">若要启用跟踪，请在 <xref:System.Activities.Tracking.TrackingParticipant> 的 <xref:System.ServiceModel.Activities.WorkflowServiceHost.WorkflowExtensions%2A> 中指定所需 <xref:System.ServiceModel.Activities.WorkflowServiceHost>。</span><span class="sxs-lookup"><span data-stu-id="9c0df-119">To enable tracking, specify the desired <xref:System.Activities.Tracking.TrackingParticipant> in the <xref:System.ServiceModel.Activities.WorkflowServiceHost.WorkflowExtensions%2A> of the <xref:System.ServiceModel.Activities.WorkflowServiceHost>.</span></span> <span data-ttu-id="9c0df-120">在下面的示例中，使用默认跟踪配置文件配置 @no__t 0 （来自[自定义跟踪](../../../../docs/framework/windows-workflow-foundation/samples/custom-tracking.md)示例）。</span><span class="sxs-lookup"><span data-stu-id="9c0df-120">In the following example, the `ConsoleTrackingParticipant` (from the [Custom Tracking](../../../../docs/framework/windows-workflow-foundation/samples/custom-tracking.md) sample) is configured by using the default tracking profile.</span></span>

```csharp
host.WorkflowExtensions.Add(new ConsoleTrackingParticipant());
```

 <span data-ttu-id="9c0df-121">跟踪参与者（如 ConsoleTrackingParticipant）对于具有控制台窗口的自承载工作流服务很有用。</span><span class="sxs-lookup"><span data-stu-id="9c0df-121">A tracking participant such as the ConsoleTrackingParticipant is useful for self-hosted workflow services that have a console window.</span></span> <span data-ttu-id="9c0df-122">对于 Web 承载的服务，应使用将跟踪信息记录到持久存储区的跟踪参与者，例如内置 @no__t 0 或将信息记录到文件的自定义跟踪参与者。</span><span class="sxs-lookup"><span data-stu-id="9c0df-122">For a Web-hosted service, a tracking participant that logs the tracking information to a durable store should be used, such as the built-in <xref:System.Activities.Tracking.EtwTrackingParticipant>, or a custom tracking participant that logs the information to a file.</span></span>

 <span data-ttu-id="9c0df-123">有关跟踪和配置 Web 承载的工作流服务跟踪的详细信息，请参阅[工作流跟踪和跟踪](../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)、[为工作流配置跟踪](../../../../docs/framework/windows-workflow-foundation/configuring-tracking-for-a-workflow.md)和[跟踪&#91;WF 示例&#93; ](../../../../docs/framework/windows-workflow-foundation/samples/tracking.md)示例。</span><span class="sxs-lookup"><span data-stu-id="9c0df-123">For more information about tracking and configuring tracking for a Web-hosted workflow service, see [Workflow Tracking and Tracing](../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md), [Configuring Tracking for a Workflow](../../../../docs/framework/windows-workflow-foundation/configuring-tracking-for-a-workflow.md), and the [Tracking &#91;WF Samples&#93;](../../../../docs/framework/windows-workflow-foundation/samples/tracking.md) samples.</span></span>

## <a name="use-wcf-tracing"></a><span data-ttu-id="9c0df-124">使用 WCF 跟踪</span><span class="sxs-lookup"><span data-stu-id="9c0df-124">Use WCF Tracing</span></span>
 <span data-ttu-id="9c0df-125">WCF 跟踪提供对发往和来自工作流服务的消息流的跟踪。</span><span class="sxs-lookup"><span data-stu-id="9c0df-125">WCF tracing provides tracing of the flow of messages to and from a workflow service.</span></span> <span data-ttu-id="9c0df-126">对相关问题（尤其是基于内容的相关）进行疑难解答时，此跟踪信息很有用。</span><span class="sxs-lookup"><span data-stu-id="9c0df-126">This tracing information is useful when troubleshooting correlation issues, especially for content-based correlation.</span></span> <span data-ttu-id="9c0df-127">若要启用跟踪，对于 Web 承载的工作流服务，请在 `system.diagnostics` 文件的 `web.config` 节中指定所需跟踪侦听器，对于自承载的工作流服务，请在 `app.config` 文件中指定所需跟踪侦听器。</span><span class="sxs-lookup"><span data-stu-id="9c0df-127">To enable tracing, specify the desired trace listeners in the `system.diagnostics` section of the `web.config` file if the workflow service is Web-hosted, or the `app.config` file if the workflow service is self-hosted.</span></span> <span data-ttu-id="9c0df-128">若要在跟踪文件中包括消息内容，请在 `true` 的 `logEntireMessage` 节的 `messageLogging` 元素中将 `diagnostics` 指定为 `system.serviceModel`。</span><span class="sxs-lookup"><span data-stu-id="9c0df-128">To include the contents of the messages in the trace file, specify `true` for `logEntireMessage` in the `messageLogging` element in the `diagnostics` section of `system.serviceModel`.</span></span> <span data-ttu-id="9c0df-129">在下面的示例中，将包括消息内容的跟踪信息配置为写入名为 `service.svclog` 的文件。</span><span class="sxs-lookup"><span data-stu-id="9c0df-129">In the following example, tracing information, including the content of the messages, is configured to be written to a file that is named `service.svclog`.</span></span>

```xml
<?xml version="1.0" encoding="utf-8" ?>
<configuration>
  <system.diagnostics>
    <sources>
      <source name="System.ServiceModel" switchValue="Information" propagateActivity="true">
        <listeners>
          <add name="corr"/>
        </listeners>
      </source>
      <source name="System.ServiceModel.MessageLogging">
        <listeners>
          <add name="corr"/>
        </listeners>
      </source>
    </sources>

    <sharedListeners>
      <add name="corr" type="System.Diagnostics.XmlWriterTraceListener" initializeData="c:\logs\service.svclog">
      </add>
    </sharedListeners>
  </system.diagnostics>

  <system.serviceModel>
    <diagnostics>
      <messageLogging logEntireMessage="true" logMalformedMessages="false"
         logMessagesAtServiceLevel="false" logMessagesAtTransportLevel="true" maxSizeOfMessageToLog="2147483647">
      </messageLogging>
    </diagnostics>
  </system.serviceModel>
</configuration>
```

 <span data-ttu-id="9c0df-130">若要查看 `service.svclog` 中包含的跟踪信息，请使用[服务跟踪查看器工具（svctraceviewer.exe）](../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md) 。</span><span class="sxs-lookup"><span data-stu-id="9c0df-130">To view the trace information that is contained in `service.svclog`, the [Service Trace Viewer Tool (SvcTraceViewer.exe)](../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md) is used.</span></span> <span data-ttu-id="9c0df-131">对基于内容的相关问题进行疑难解答时，此工具尤其有用，因为您可查看消息内容，并准确了解传递的内容以及它是否与基于内容的相关的 <xref:System.ServiceModel.CorrelationQuery> 匹配。</span><span class="sxs-lookup"><span data-stu-id="9c0df-131">This is especially useful when troubleshooting content-based correlation issues because you can view the message contents and see exactly what is being passed, and whether it matches the <xref:System.ServiceModel.CorrelationQuery> for the content-based correlation.</span></span> <span data-ttu-id="9c0df-132">有关 WCF 跟踪的详细信息，请参阅[服务跟踪查看器工具（svctraceviewer.exe）](../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md)、[配置跟踪](../../../../docs/framework/wcf/diagnostics/tracing/configuring-tracing.md)和[使用跟踪对应用程序进行故障排除](../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)。</span><span class="sxs-lookup"><span data-stu-id="9c0df-132">For more information about WCF tracing, see [Service Trace Viewer Tool (SvcTraceViewer.exe)](../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md), [Configuring Tracing](../../../../docs/framework/wcf/diagnostics/tracing/configuring-tracing.md), and [Using Tracing to Troubleshoot Your Application](../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md).</span></span>

## <a name="common-context-exchange-correlation-issues"></a><span data-ttu-id="9c0df-133">常见上下文交换相关问题</span><span class="sxs-lookup"><span data-stu-id="9c0df-133">Common Context Exchange Correlation Issues</span></span>
 <span data-ttu-id="9c0df-134">某些类型的相关需要使用特定类型的绑定才能正常工作。</span><span class="sxs-lookup"><span data-stu-id="9c0df-134">Certain types of correlation require that a specific type of binding is used for the correlation to work correctly.</span></span> <span data-ttu-id="9c0df-135">例如需要双向绑定（如 <xref:System.ServiceModel.BasicHttpBinding>）的请求-答复相关和需要基于上下文的绑定（如 <xref:System.ServiceModel.BasicHttpContextBinding>）的上下文交换相关。</span><span class="sxs-lookup"><span data-stu-id="9c0df-135">Examples include request-reply correlation, which requires a two-way binding such as <xref:System.ServiceModel.BasicHttpBinding>, and context exchange correlation, which requires a context-based binding such as <xref:System.ServiceModel.BasicHttpContextBinding>.</span></span> <span data-ttu-id="9c0df-136">大多数绑定支持双向操作，因此这对于请求-答复相关并不是常见问题，但是只有几种基于上下文的绑定，包括 <xref:System.ServiceModel.BasicHttpContextBinding>、<xref:System.ServiceModel.WSHttpContextBinding> 和 <xref:System.ServiceModel.NetTcpContextBinding>。</span><span class="sxs-lookup"><span data-stu-id="9c0df-136">Most bindings support two-way operations so this is not a common issue for request-reply correlation, but there are only a handful of context-based bindings including <xref:System.ServiceModel.BasicHttpContextBinding>, <xref:System.ServiceModel.WSHttpContextBinding>, and <xref:System.ServiceModel.NetTcpContextBinding>.</span></span> <span data-ttu-id="9c0df-137">如果未使用这些绑定中的一种，则对工作流服务的初次调用会成功，但是后续调用会失败并出现下面的 <xref:System.ServiceModel.FaultException>。</span><span class="sxs-lookup"><span data-stu-id="9c0df-137">If one of these bindings is not used, the initial call to a workflow service will succeed, but subsequent calls will fail with the following <xref:System.ServiceModel.FaultException>.</span></span>

```output
There is no context attached to the incoming message for the service
and the current operation is not marked with "CanCreateInstance = true".
In order to communicate with this service check whether the incoming binding
supports the context protocol and has a valid context initialized.
```

 <span data-ttu-id="9c0df-138">用于上下文相关的上下文信息可由 <xref:System.ServiceModel.Activities.SendReply> 返回到 <xref:System.ServiceModel.Activities.Receive> 活动，该活动在使用双向操作时初始化上下文相关，如果操作是单向的，则上下文信息也可由调用方指定。</span><span class="sxs-lookup"><span data-stu-id="9c0df-138">The context information that is used for context correlation can be returned by the <xref:System.ServiceModel.Activities.SendReply> to the <xref:System.ServiceModel.Activities.Receive> activity that initializes the context correlation when using a two-way operation, or it can be specified by the caller if the operation is one-way.</span></span> <span data-ttu-id="9c0df-139">如果调用方未发送上下文，或工作流服务未返回上下文，则当调用后续操作时，会返回前面介绍的 <xref:System.ServiceModel.FaultException>。</span><span class="sxs-lookup"><span data-stu-id="9c0df-139">If the context is not sent by the caller or returned by the workflow service, then the same <xref:System.ServiceModel.FaultException> described previously will be returned when a subsequent operation is invoked.</span></span>

## <a name="common-request-reply-correlation-issues"></a><span data-ttu-id="9c0df-140">常见请求-答复相关问题</span><span class="sxs-lookup"><span data-stu-id="9c0df-140">Common Request-Reply Correlation Issues</span></span>
 <span data-ttu-id="9c0df-141">请求-答复相关与 <xref:System.ServiceModel.Activities.Receive> @ no__t-1 @ no__t-2 对一起使用，以便在工作流服务中实现双向操作，并使用 @no__t 3 @ no__t @ no__t-5 对调用另一个 Web 服务中的双向操作。</span><span class="sxs-lookup"><span data-stu-id="9c0df-141">Request-reply correlation is used with a <xref:System.ServiceModel.Activities.Receive>/<xref:System.ServiceModel.Activities.SendReply> pair to implement a two-way operation in a workflow service and with a <xref:System.ServiceModel.Activities.Send>/<xref:System.ServiceModel.Activities.ReceiveReply> pair that invokes a two-way operation in another Web service.</span></span> <span data-ttu-id="9c0df-142">在 WCF 服务中调用双向操作时，该服务可以是传统的基于命令性代码的 WCF 服务，也可以是工作流服务。</span><span class="sxs-lookup"><span data-stu-id="9c0df-142">When invoking a two-way operation in a WCF service, the service can be either a traditional imperative code-based WCF service or it can be a workflow service.</span></span> <span data-ttu-id="9c0df-143">若要使用请求-答复相关，必须使用双向绑定（如 <xref:System.ServiceModel.BasicHttpBinding>），且操作则必须是双向的。</span><span class="sxs-lookup"><span data-stu-id="9c0df-143">To use request-reply correlation a two-way binding must be used, such as <xref:System.ServiceModel.BasicHttpBinding>, and the operations must be two-way.</span></span>

 <span data-ttu-id="9c0df-144">如果工作流服务有并行的双向操作，或者重叠 <xref:System.ServiceModel.Activities.Receive> @ no__t-1 @ no__t; 或 <xref:System.ServiceModel.Activities.Send> @ no__t @ no__t 对，则 <xref:System.ServiceModel.Activities.WorkflowServiceHost> 提供的隐式相关句柄管理可能不足，尤其是在高压力方案和消息可能无法正确路由。</span><span class="sxs-lookup"><span data-stu-id="9c0df-144">If the workflow service has two-way operations in parallel, or overlapping <xref:System.ServiceModel.Activities.Receive>/<xref:System.ServiceModel.Activities.SendReply> or <xref:System.ServiceModel.Activities.Send>/<xref:System.ServiceModel.Activities.ReceiveReply> pairs, then the implicit correlation handle management provided by <xref:System.ServiceModel.Activities.WorkflowServiceHost> may not be sufficient, especially in high-stress scenarios, and messages may not be correctly routed.</span></span> <span data-ttu-id="9c0df-145">若要防止此问题发生，我们建议您在使用请求-答复相关时，始终显式指定 <xref:System.ServiceModel.Activities.CorrelationHandle>。</span><span class="sxs-lookup"><span data-stu-id="9c0df-145">To prevent this issue from occurring, we recommend that you always explicitly specify a <xref:System.ServiceModel.Activities.CorrelationHandle> when using request-reply correlation.</span></span> <span data-ttu-id="9c0df-146">使用工作流设计器中 "**工具箱**" 的 "消息传送" 部分中的**SendAndReceiveReply**和**ReceiveAndSendReply**模板时，默认情况下会显式配置 @no__t。</span><span class="sxs-lookup"><span data-stu-id="9c0df-146">When using the **SendAndReceiveReply** and **ReceiveAndSendReply** templates from the Messaging section of the **Toolbox** in the workflow designer, a <xref:System.ServiceModel.Activities.CorrelationHandle> is explicitly configured by default.</span></span> <span data-ttu-id="9c0df-147">使用代码生成工作流时，将在对中第一个活动的 <xref:System.ServiceModel.Activities.CorrelationHandle> 中指定 <xref:System.ServiceModel.Activities.Receive.CorrelationInitializers%2A>。</span><span class="sxs-lookup"><span data-stu-id="9c0df-147">When building a workflow by using code, the <xref:System.ServiceModel.Activities.CorrelationHandle> is specified in the <xref:System.ServiceModel.Activities.Receive.CorrelationInitializers%2A> of the first activity in the pair.</span></span> <span data-ttu-id="9c0df-148">在下面的示例中，使用 <xref:System.ServiceModel.Activities.Receive> 中指定的显式 <xref:System.ServiceModel.Activities.CorrelationInitializer.CorrelationHandle%2A> 来配置 <xref:System.ServiceModel.Activities.RequestReplyCorrelationInitializer> 活动。</span><span class="sxs-lookup"><span data-stu-id="9c0df-148">In the following example, a <xref:System.ServiceModel.Activities.Receive> activity is configured with an explicit <xref:System.ServiceModel.Activities.CorrelationInitializer.CorrelationHandle%2A> specified in the <xref:System.ServiceModel.Activities.RequestReplyCorrelationInitializer>.</span></span>

```csharp
Variable<CorrelationHandle> RRHandle = new Variable<CorrelationHandle>();

Receive StartOrder = new Receive
{
    CanCreateInstance = true,
    ServiceContractName = OrderContractName,
    OperationName = "StartOrder",
    CorrelationInitializers =
    {
        new RequestReplyCorrelationInitializer
        {
            CorrelationHandle = RRHandle
        }
    }
};

SendReply ReplyToStartOrder = new SendReply
{
    Request = StartOrder,
    Content = ... // Contains the return value, if any.
};

// Construct a workflow using StartOrder and ReplyToStartOrder.
```

 <span data-ttu-id="9c0df-149">不允许在 <xref:System.ServiceModel.Activities.Receive> @ no__t-1 @ no__t-2 对或 <xref:System.ServiceModel.Activities.Send> @ no__t @ no__t 对之间使用持久性。</span><span class="sxs-lookup"><span data-stu-id="9c0df-149">Persistence is not permitted between a <xref:System.ServiceModel.Activities.Receive>/<xref:System.ServiceModel.Activities.SendReply> pair or a <xref:System.ServiceModel.Activities.Send>/<xref:System.ServiceModel.Activities.ReceiveReply> pair.</span></span> <span data-ttu-id="9c0df-150">会创建一个非永久性区域，该区域会持续到两个活动都已完成。</span><span class="sxs-lookup"><span data-stu-id="9c0df-150">A no-persist zone is created that lasts until both activities have completed.</span></span> <span data-ttu-id="9c0df-151">如果某个活动（如延迟活动）处于此非永久性区域中，并使工作流成为空闲状态，则工作流不会持久，即使主机配置为在工作流成为空闲状态时保持工作流也是如此。</span><span class="sxs-lookup"><span data-stu-id="9c0df-151">If an activity, such as a delay activity, is in this no-persist zone and causes the workflow to become idle, the workflow will not persist even if it the host is configured to persist workflows when they become idle.</span></span> <span data-ttu-id="9c0df-152">如果某个活动（如 Persist 活动）尝试在非永久性区域中显式保持，则会引发严重异常，工作流会中止，并将 <xref:System.ServiceModel.FaultException> 返回给调用方。</span><span class="sxs-lookup"><span data-stu-id="9c0df-152">If an activity, such as a persist activity, attempts to explicitly persist in the no-persist zone, a fatal exception is thrown, the workflow aborts, and a <xref:System.ServiceModel.FaultException> is returned to the caller.</span></span> <span data-ttu-id="9c0df-153">严重异常消息为 "InvalidOperationException：不能在无持久性块中包含持久活动。 "。</span><span class="sxs-lookup"><span data-stu-id="9c0df-153">The fatal exception message is "System.InvalidOperationException: Persist activities cannot be contained within no persistence blocks.".</span></span> <span data-ttu-id="9c0df-154">此异常不会返回给调用方，但是可以观察到（如果启用了跟踪）。</span><span class="sxs-lookup"><span data-stu-id="9c0df-154">This exception is not returned to the caller but can be observed if tracking is enabled.</span></span> <span data-ttu-id="9c0df-155">返回给调用方的 <xref:System.ServiceModel.FaultException> 消息为“无法执行操作，因为 WorkflowInstance‘5836145b-7da2-49d0-a052-a49162adeab6’已完成”。</span><span class="sxs-lookup"><span data-stu-id="9c0df-155">The message for the <xref:System.ServiceModel.FaultException> returned to the caller is "The operation could not be performed because WorkflowInstance '5836145b-7da2-49d0-a052-a49162adeab6' has completed".</span></span>

 <span data-ttu-id="9c0df-156">有关请求-答复相关性的详细信息，请参阅[请求-答复](../../../../docs/framework/wcf/feature-details/request-reply-correlation.md)。</span><span class="sxs-lookup"><span data-stu-id="9c0df-156">For more information about request-reply correlation, see [Request-Reply](../../../../docs/framework/wcf/feature-details/request-reply-correlation.md).</span></span>

## <a name="common-content-correlation-issues"></a><span data-ttu-id="9c0df-157">常见内容相关问题</span><span class="sxs-lookup"><span data-stu-id="9c0df-157">Common Content Correlation Issues</span></span>
 <span data-ttu-id="9c0df-158">当工作流服务接收到多个消息，且交换的消息中的一段数据标识了所需实例时，会使用基于内容的相关。</span><span class="sxs-lookup"><span data-stu-id="9c0df-158">Content-based correlation is used when a workflow service receives multiple messages and a piece of data in the exchanged messages identifies the desired instance.</span></span> <span data-ttu-id="9c0df-159">基于内容的相关使用消息中的此数据（如客户编号或订单 ID）将消息路由到正确的工作流实例。</span><span class="sxs-lookup"><span data-stu-id="9c0df-159">Content-based correlation uses this data in the message, such as a customer number or order ID, to route messages to the correct workflow instance.</span></span> <span data-ttu-id="9c0df-160">本节描述使用基于内容的相关时可能出现的几个常见问题。</span><span class="sxs-lookup"><span data-stu-id="9c0df-160">This section describes several common issues that may occur when using content-based correlation.</span></span>

### <a name="ensure-the-identifying-data-is-unique"></a><span data-ttu-id="9c0df-161">确保标识数据唯一</span><span class="sxs-lookup"><span data-stu-id="9c0df-161">Ensure the Identifying Data Is Unique</span></span>
 <span data-ttu-id="9c0df-162">用于标识实例的数据经过哈希运算之后即可成为相关键。</span><span class="sxs-lookup"><span data-stu-id="9c0df-162">The data that is used to identify the instance is hashed into a correlation key.</span></span> <span data-ttu-id="9c0df-163">必须小心确保用于相关的数据是唯一的，否则经过哈希运算的键中可能会出现冲突，从而导致错误路由消息。</span><span class="sxs-lookup"><span data-stu-id="9c0df-163">Care must be taken to guarantee that the data that is used for correlation is unique or else collisions in the hashed key might occur and cause messages to be misrouted.</span></span> <span data-ttu-id="9c0df-164">例如，仅基于客户姓名的相关可能会导致冲突，因为可能存在多个具有相同姓名的客户。</span><span class="sxs-lookup"><span data-stu-id="9c0df-164">For example, a correlation based only on a customer name may cause a collision because there may be multiple customers who have the same name.</span></span> <span data-ttu-id="9c0df-165">在使消息彼此相关所采用的数据中，不得使用冒号 (:)，因为冒号已用于分隔消息查询的键和值以便构成将在随后进行哈希运算的字符串。</span><span class="sxs-lookup"><span data-stu-id="9c0df-165">The colon (:) should not be used as part of the data that is used to correlate the message because it is already used to delimit the message query’s key and value to form the string that is subsequently hashed.</span></span> <span data-ttu-id="9c0df-166">如果使用持久性，请确保以前保留的实例未使用当前标识数据。</span><span class="sxs-lookup"><span data-stu-id="9c0df-166">If persistence is being used, make sure that the current identifying data has not been used by a previously persisted instance.</span></span> <span data-ttu-id="9c0df-167">暂时禁用持久性可有助于确定此问题。</span><span class="sxs-lookup"><span data-stu-id="9c0df-167">Temporarily disabling persistence can help identify this issue.</span></span> <span data-ttu-id="9c0df-168">WCF 跟踪可用于查看计算出的相关键，对于调试此类问题十分有用。</span><span class="sxs-lookup"><span data-stu-id="9c0df-168">WCF tracing can be used to view the calculated correlation key and is useful for debugging this kind of issue.</span></span>

### <a name="race-conditions"></a><span data-ttu-id="9c0df-169">争用条件</span><span class="sxs-lookup"><span data-stu-id="9c0df-169">Race Conditions</span></span>
 <span data-ttu-id="9c0df-170">在服务接收消息到实际初始化相关之间有一小段时间间隙，在这段时间内将忽略后续的消息。</span><span class="sxs-lookup"><span data-stu-id="9c0df-170">There is a small gap in time between the service receiving a message and the correlation actually being initialized, during which follow-up messages will be ignored.</span></span> <span data-ttu-id="9c0df-171">如果工作流服务使用通过单向操作从客户机传递的数据来初始化基于内容的相关，且调用方立即发送后续消息，则在这段时间间隔内会忽略这些消息。</span><span class="sxs-lookup"><span data-stu-id="9c0df-171">If a workflow service initializes the content-based correlation by using data passed from the client over a one-way operation, and the caller sends immediate follow-up messages, these messages will be ignored during this interval.</span></span> <span data-ttu-id="9c0df-172">可通过使用双向操作初始化相关，或通过使用 <xref:System.ServiceModel.Activities.TransactedReceiveScope> 来避免发生这种情况。</span><span class="sxs-lookup"><span data-stu-id="9c0df-172">This can be avoided by using a two-way operation to initialize the correlation, or by using a <xref:System.ServiceModel.Activities.TransactedReceiveScope>.</span></span>

### <a name="correlation-query-issues"></a><span data-ttu-id="9c0df-173">相关查询问题</span><span class="sxs-lookup"><span data-stu-id="9c0df-173">Correlation Query Issues</span></span>
 <span data-ttu-id="9c0df-174">相关查询用于指定消息中的哪些数据用于使消息相关。</span><span class="sxs-lookup"><span data-stu-id="9c0df-174">Correlation queries are used to specify what data in a message is used to correlate the message.</span></span> <span data-ttu-id="9c0df-175">这些数据使用 XPath 查询进行指定。</span><span class="sxs-lookup"><span data-stu-id="9c0df-175">This data is specified by using an XPath query.</span></span> <span data-ttu-id="9c0df-176">如果即使看起来一切正常，但仍未调度传递给服务的消息，则一种疑难解答策略是指定与消息数据的值匹配的文本值（而不是 XPath 查询）。</span><span class="sxs-lookup"><span data-stu-id="9c0df-176">If messages to a service are not being dispatched even though everything appears to be correct, one strategy for troubleshooting is to specify a literal value that matches the value of the message data instead of an XPath query.</span></span> <span data-ttu-id="9c0df-177">若要指定文本值，请使用 `string` 函数。</span><span class="sxs-lookup"><span data-stu-id="9c0df-177">To specify a literal value, use the `string` function.</span></span> <span data-ttu-id="9c0df-178">在下面的示例中，<xref:System.ServiceModel.MessageQuerySet> 配置为对 `11445` 使用文本值 `OrderId`，而注释掉 XPath 查询。</span><span class="sxs-lookup"><span data-stu-id="9c0df-178">In the following example, a <xref:System.ServiceModel.MessageQuerySet> is configured to use a literal value of `11445` for the `OrderId` and the XPath query is commented out.</span></span>

```csharp
MessageQuerySet = new MessageQuerySet
{
    {
        "OrderId",
        //new XPathMessageQuery("sm:body()/tempuri:StartOrderResponse/tempuri:OrderId")
        new XPathMessageQuery("string('11445')")
    }
}
```

 <span data-ttu-id="9c0df-179">如果未正确配置 XPath 查询以便检索不到相关数据，则会返回带有以下消息的错误："相关查询生成了一个空的结果集。</span><span class="sxs-lookup"><span data-stu-id="9c0df-179">If an XPath query is configured incorrectly such that no correlation data is retrieved, a fault is returned with the following message: "A correlation query yielded an empty result set.</span></span> <span data-ttu-id="9c0df-180">请确保正确配置了终结点的相关查询。”</span><span class="sxs-lookup"><span data-stu-id="9c0df-180">Please ensure correlation queries for the endpoint are correctly configured."</span></span> <span data-ttu-id="9c0df-181">解决此问题的一种快速方式是将 XPath 查询替换为文本值，如上一节中所述。</span><span class="sxs-lookup"><span data-stu-id="9c0df-181">One quick way to troubleshoot this is to replace the XPath query with a literal value as described in the previous section.</span></span> <span data-ttu-id="9c0df-182">如果使用 "**添加相关初始值设定项**" 或 " **CorrelatesOn 定义**" 对话框中的 XPath 查询生成器，并且工作流服务使用消息协定，则会出现此问题。</span><span class="sxs-lookup"><span data-stu-id="9c0df-182">This issue can occur if you use the XPath query builder in the **Add Correlation Initializers** or **CorrelatesOn Definition** dialog boxes and your workflow service uses message contracts.</span></span> <span data-ttu-id="9c0df-183">下面的示例定义了一个消息协定类。</span><span class="sxs-lookup"><span data-stu-id="9c0df-183">In the following example, a message contract class is defined.</span></span>

```csharp
[MessageContract]
public class AddItemMessage
{
    [MessageHeader]
    public string CartId;

    [MessageBodyMember]
    public string Item;
}
```

 <span data-ttu-id="9c0df-184">此消息协定由 <xref:System.ServiceModel.Activities.Receive> 活动在工作流中使用。</span><span class="sxs-lookup"><span data-stu-id="9c0df-184">This message contract is used by a <xref:System.ServiceModel.Activities.Receive> activity in a workflow.</span></span> <span data-ttu-id="9c0df-185">消息标头中的 `CartId` 用于将消息与正确实例相关。</span><span class="sxs-lookup"><span data-stu-id="9c0df-185">The `CartId` in the header of the message is used to correlate the message to the correct instance.</span></span> <span data-ttu-id="9c0df-186">如果使用工作流设计器中的相关对话框创建检索 `CartId` 的 XPath 查询，则会生成以下不正确的 XPath 查询。</span><span class="sxs-lookup"><span data-stu-id="9c0df-186">If the XPath query that retrieves the `CartId` is created using the correlation dialogs in the workflow designer, the following incorrect XPath query is generated.</span></span>

```
sm:body()/xg0:AddItemMessage/xg0:CartId
```

 <span data-ttu-id="9c0df-187">如果 <xref:System.ServiceModel.Activities.Receive> 活动使用数据的参数，则此 XPath 查询是正确的，但是由于它使用消息协定，因此是不正确的。</span><span class="sxs-lookup"><span data-stu-id="9c0df-187">This XPath query would be correct if the <xref:System.ServiceModel.Activities.Receive> activity used parameters for the data, but since it is using a message contract it is incorrect.</span></span> <span data-ttu-id="9c0df-188">下面的 XPath 查询是用于从标头检索 `CartId` 的正确 XPath 查询。</span><span class="sxs-lookup"><span data-stu-id="9c0df-188">The following XPath query is the correct XPath query to retrieve the `CartId` from the header.</span></span>

```
sm:header()/tempuri:CartId
```

<span data-ttu-id="9c0df-189">可以通过检查消息正文确认此情况。</span><span class="sxs-lookup"><span data-stu-id="9c0df-189">This can be confirmed by examining the body of the message.</span></span>

```xml
<s:Envelope xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">
  <s:Header>
    <Action s:mustUnderstand="1" xmlns="http://schemas.microsoft.com/ws/2005/05/addressing/none">http://tempuri.org/IService/AddItem</Action>
    <h:CartId xmlns:h="http://tempuri.org/">80c95b41-c98d-4660-a6c1-99412206e54c</h:CartId>
  </s:Header>
  <s:Body>
    <AddItemMessage xmlns="http://tempuri.org/">
      <Item>Books</Item>
    </AddItemMessage>
  </s:Body>
</s:Envelope>
```

<span data-ttu-id="9c0df-190">下面的示例演示一个 <xref:System.ServiceModel.Activities.Receive> 活动，该活动针对使用以前的消息协定检索数据的 `AddItem` 操作而配置。</span><span class="sxs-lookup"><span data-stu-id="9c0df-190">The following example shows a <xref:System.ServiceModel.Activities.Receive> activity configured for an `AddItem` operation that uses the previous message contract to receive data.</span></span> <span data-ttu-id="9c0df-191">XPath 查询进行了正确配置。</span><span class="sxs-lookup"><span data-stu-id="9c0df-191">The XPath query is correctly configured.</span></span>

```xaml
<Receive CorrelatesWith="[CCHandle] OperationName="AddItem" ServiceContractName="p:IService">
  <Receive.CorrelatesOn>
    <XPathMessageQuery x:Key="key1">
      <XPathMessageQuery.Namespaces>
        <ssx:XPathMessageContextMarkup>
          <x:String x:Key="xg0">http://schemas.datacontract.org/2004/07/MessageContractWFService</x:String>
        </ssx:XPathMessageContextMarkup>
      </XPathMessageQuery.Namespaces>sm:header()/tempuri:CartId</XPathMessageQuery>
  </Receive.CorrelatesOn>
  <ReceiveMessageContent DeclaredMessageType="m:AddItemMessage">
    <p1:OutArgument x:TypeArguments="m:AddItemMessage">[AddItemMessage]</p1:OutArgument>
  </ReceiveMessageContent>
</Receive>
```
