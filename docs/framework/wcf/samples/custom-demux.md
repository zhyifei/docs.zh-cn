---
title: "自定义多路分解器"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: fc54065c-518e-4146-b24a-0fe00038bfa7
caps.latest.revision: "41"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: d7c74648a249ec833f2b0fc8b8f5eea9247dc364
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="custom-demux"></a><span data-ttu-id="e7de7-102">自定义多路分解器</span><span class="sxs-lookup"><span data-stu-id="e7de7-102">Custom Demux</span></span>
<span data-ttu-id="e7de7-103">此示例演示如何将 MSMQ 消息头映射到不同服务操作，以便[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]服务使用<xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBinding>并不仅限于使用一个服务操作，如中所示[到消息队列Windows Communication Foundation](../../../../docs/framework/wcf/samples/message-queuing-to-wcf.md)和[Windows Communication Foundation 到消息队列](../../../../docs/framework/wcf/samples/wcf-to-message-queuing.md)示例。</span><span class="sxs-lookup"><span data-stu-id="e7de7-103">This sample demonstrates how MSMQ message headers can be mapped to different service operations so that [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] services that use <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBinding> are not limited to using one service operation as demonstrated in the [Message Queuing to Windows Communication Foundation](../../../../docs/framework/wcf/samples/message-queuing-to-wcf.md) and [Windows Communication Foundation to Message Queuing](../../../../docs/framework/wcf/samples/wcf-to-message-queuing.md) samples.</span></span>  
  
 <span data-ttu-id="e7de7-104">本示例中的服务是自承载控制台应用程序，通过它可以观察接收排队消息的服务。</span><span class="sxs-lookup"><span data-stu-id="e7de7-104">The service in this sample is a self-hosted console application to enable you to observe the service that receives queued messages.</span></span>  
  
 <span data-ttu-id="e7de7-105">此服务协定是 `IOrderProcessor`，它定义了适合与队列一起使用的单向服务。</span><span class="sxs-lookup"><span data-stu-id="e7de7-105">The service contract is `IOrderProcessor`, and defines a one-way service that is suitable for use with queues.</span></span>  
  
```  
[ServiceContract]  
[KnownType(typeof(PurchaseOrder))]  
[KnownType(typeof(String))]  
public interface IOrderProcessor  
{  
    [OperationContract(IsOneWay = true, Name = "SubmitPurchaseOrder")]  
    void SubmitPurchaseOrder(MsmqMessage<PurchaseOrder> msg);  
  
    [OperationContract(IsOneWay = true, Name = "CancelPurchaseOrder")]  
    void CancelPurchaseOrder(MsmqMessage<string> ponumber);  
}  
```  
  
 <span data-ttu-id="e7de7-106">MSMQ 消息没有 Action 标头。</span><span class="sxs-lookup"><span data-stu-id="e7de7-106">An MSMQ message does not have an Action header.</span></span> <span data-ttu-id="e7de7-107">无法自动将不同的 MSMQ 消息映射到操作协定。</span><span class="sxs-lookup"><span data-stu-id="e7de7-107">It is not possible to map different MSMQ messages to operation contracts automatically.</span></span> <span data-ttu-id="e7de7-108">所以只能有一个操作协定。</span><span class="sxs-lookup"><span data-stu-id="e7de7-108">Therefore, there can be only one operation contract.</span></span> <span data-ttu-id="e7de7-109">为了克服此限制，服务实现 <xref:System.ServiceModel.Dispatcher.IDispatchOperationSelector.SelectOperation%2A> 接口的 <xref:System.ServiceModel.Dispatcher.IDispatchOperationSelector> 方法。</span><span class="sxs-lookup"><span data-stu-id="e7de7-109">To overcome this limitation, the service implements the <xref:System.ServiceModel.Dispatcher.IDispatchOperationSelector.SelectOperation%2A> method of the <xref:System.ServiceModel.Dispatcher.IDispatchOperationSelector> interface.</span></span> <span data-ttu-id="e7de7-110">通过 <xref:System.ServiceModel.Dispatcher.IDispatchOperationSelector.SelectOperation%2A> 方法，服务可以将给定的消息头映射到特定服务操作。</span><span class="sxs-lookup"><span data-stu-id="e7de7-110">The <xref:System.ServiceModel.Dispatcher.IDispatchOperationSelector.SelectOperation%2A> method enables the service to map a given header of the message to a particular service operation.</span></span> <span data-ttu-id="e7de7-111">在本示例中，将消息的标签标头映射到服务操作。</span><span class="sxs-lookup"><span data-stu-id="e7de7-111">In this sample, the message's label header is mapped to the service operations.</span></span> <span data-ttu-id="e7de7-112">操作协定的 `Name` 参数确定必须为给定的消息标签调度哪个服务操作。</span><span class="sxs-lookup"><span data-stu-id="e7de7-112">The `Name` parameter of the operation contract determines which service operation must be dispatched for a given message label.</span></span> <span data-ttu-id="e7de7-113">例如，如果消息的标签标头包含“SubmitPurchaseOrder”，则调用“SubmitPurchaseOrder”服务操作。</span><span class="sxs-lookup"><span data-stu-id="e7de7-113">For example, if the message's label header contains "SubmitPurchaseOrder", the "SubmitPurchaseOrder" service operation is invoked.</span></span>  
  
```  
public class OperationSelector : IDispatchOperationSelector  
{  
    public string SelectOperation(ref System.ServiceModel.Channels.Message message)  
    {  
        MsmqIntegrationMessageProperty property = MsmqIntegrationMessageProperty.Get(message);  
        return property.Label;  
    }  
}  
```  
  
 <span data-ttu-id="e7de7-114">服务必须实现 <xref:System.ServiceModel.Description.IContractBehavior.ApplyDispatchBehavior%28System.ServiceModel.Description.ContractDescription%2CSystem.ServiceModel.Description.ServiceEndpoint%2CSystem.ServiceModel.Dispatcher.DispatchRuntime%29> 接口的 <xref:System.ServiceModel.Description.IContractBehavior> 方法，如下面的示例代码所示。</span><span class="sxs-lookup"><span data-stu-id="e7de7-114">The service must implement the <xref:System.ServiceModel.Description.IContractBehavior.ApplyDispatchBehavior%28System.ServiceModel.Description.ContractDescription%2CSystem.ServiceModel.Description.ServiceEndpoint%2CSystem.ServiceModel.Dispatcher.DispatchRuntime%29> method of the <xref:System.ServiceModel.Description.IContractBehavior> interface as shown in the following sample code.</span></span> <span data-ttu-id="e7de7-115">这会将自定义 `OperationSelector` 应用于服务框架调度运行时。</span><span class="sxs-lookup"><span data-stu-id="e7de7-115">This applies the custom `OperationSelector` to the service framework dispatch runtime.</span></span>  
  
```  
void IContractBehavior.ApplyDispatchBehavior(ContractDescription description, ServiceEndpoint endpoint, DispatchRuntime dispatch)  
{  
    dispatch.OperationSelector = new OperationSelector();  
}  
```  
  
 <span data-ttu-id="e7de7-116">在到达 OperationSelector 之前，消息必须通过调度程序的 <xref:System.ServiceModel.Dispatcher.EndpointDispatcher.ContractFilter%2A>。</span><span class="sxs-lookup"><span data-stu-id="e7de7-116">A message must pass through the dispatcher's <xref:System.ServiceModel.Dispatcher.EndpointDispatcher.ContractFilter%2A> before getting to the OperationSelector.</span></span> <span data-ttu-id="e7de7-117">默认情况下，如果在由服务实现的任何协定上找不到消息操作，则会拒绝该消息。</span><span class="sxs-lookup"><span data-stu-id="e7de7-117">By default a message is rejected if its action cannot be found on any contract implemented by the service.</span></span> <span data-ttu-id="e7de7-118">为了避免这种阻碍的发生，我们实现了一个名为 <xref:System.ServiceModel.Description.IEndpointBehavior> 的 `MatchAllFilterBehavior`，它通过应用 `ContractFilter` 允许任何消息通过 <xref:System.ServiceModel.Dispatcher.MatchAllMessageFilter>，如下所示。</span><span class="sxs-lookup"><span data-stu-id="e7de7-118">To avoid this check, we implement an <xref:System.ServiceModel.Description.IEndpointBehavior> named `MatchAllFilterBehavior`, which allows any message to pass through the `ContractFilter` by applying the <xref:System.ServiceModel.Dispatcher.MatchAllMessageFilter> as follows.</span></span>  
  
```  
public void ApplyDispatchBehavior(ServiceEndpoint serviceEndpoint, EndpointDispatcher endpointDispatcher)  
{  
    endpointDispatcher.ContractFilter = new MatchAllMessageFilter();  
}  
```  
  
 <span data-ttu-id="e7de7-119">当服务接收到消息时，会使用标签标头提供的信息调度相应的服务操作。</span><span class="sxs-lookup"><span data-stu-id="e7de7-119">When a message is received by the service, the appropriate service operation is dispatched using the information provided by the label header.</span></span> <span data-ttu-id="e7de7-120">消息正文反序列化为 `PurchaseOrder` 对象，如下面的示例代码所示。</span><span class="sxs-lookup"><span data-stu-id="e7de7-120">The body of the message is deserialized into a `PurchaseOrder` object, as shown in the following sample code.</span></span>  
  
```  
[OperationBehavior(TransactionScopeRequired = true, TransactionAutoComplete = true)]  
public void SubmitPurchaseOrder(MsmqMessage<PurchaseOrder> msg)  
{  
    PurchaseOrder po = (PurchaseOrder)msg.Body;  
    Random statusIndexer = new Random();  
    po.Status = (OrderStates)statusIndexer.Next(3);  
    Console.WriteLine("Processing {0} ", po);  
}  
```  
  
 <span data-ttu-id="e7de7-121">服务是自承载服务。</span><span class="sxs-lookup"><span data-stu-id="e7de7-121">The service is self-hosted.</span></span> <span data-ttu-id="e7de7-122">使用 MSMQ 时，必须提前创建所使用的队列。</span><span class="sxs-lookup"><span data-stu-id="e7de7-122">When using the MSMQ, the queue that is used must be created in advance.</span></span> <span data-ttu-id="e7de7-123">可以手动或通过代码完成此操作。</span><span class="sxs-lookup"><span data-stu-id="e7de7-123">This can be done manually or through code.</span></span> <span data-ttu-id="e7de7-124">在本示例中，服务包含用以检查队列是否存在的代码，并在队列不存在时创建该队列。</span><span class="sxs-lookup"><span data-stu-id="e7de7-124">In this sample, the service contains code to check for the existence of the queue and creates it if the queue does not exist.</span></span> <span data-ttu-id="e7de7-125">从配置文件中读取队列名称。</span><span class="sxs-lookup"><span data-stu-id="e7de7-125">The queue name is read from the configuration file.</span></span>  
  
```  
public static void Main()  
{  
    // Get MSMQ queue name from app settings in configuration  
    string queueName = ConfigurationManager.AppSettings["orderQueueName"];  
  
    // Create the transacted MSMQ queue if necessary.  
    if (!MessageQueue.Exists(queueName))  
        MessageQueue.Create(queueName, true);  
  
    // Create a ServiceHost for the CalculatorService type.  
    using (ServiceHost serviceHost = new ServiceHost(typeof(OrderProcessorService)))  
    {                 
        ServiceEndpoint endpoint = serviceHost.Description.Endpoints[0];  
        endpoint.Behaviors.Add(new MatchAllFilterBehavior());  
  
        //Open the ServiceHost to create listeners and start listening for messages.  
        serviceHost.Open();  
  
        // The service can now be accessed.  
        Console.WriteLine("The service is ready.");  
        Console.WriteLine("Press <ENTER> to terminate service.");  
        Console.ReadLine();  
  
        // Close the ServiceHost to shutdown the service.  
        serviceHost.Close();  
    }  
}  
```  
  
 <span data-ttu-id="e7de7-126">MSMQ 队列名称是在配置文件的 appSettings 节中指定的。</span><span class="sxs-lookup"><span data-stu-id="e7de7-126">The MSMQ queue name is specified in an appSettings section of the configuration file.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e7de7-127">队列名称为本地计算机使用圆点 (.)，并在其路径中使用反斜杠分隔符。</span><span class="sxs-lookup"><span data-stu-id="e7de7-127">The queue name uses a dot (.) for the local computer and backslash separators in its path.</span></span> <span data-ttu-id="e7de7-128">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 终结点地址指定 msmq.formatname 方案，并为本地计算机使用 localhost。</span><span class="sxs-lookup"><span data-stu-id="e7de7-128">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] endpoint address specifies a msmq.formatname scheme, and uses localhost for the local computer.</span></span> <span data-ttu-id="e7de7-129">方案后面是根据 MSMQ 格式名寻址指南正确格式化的队列地址。</span><span class="sxs-lookup"><span data-stu-id="e7de7-129">What follows the scheme is a properly formatted queue address according to the MSMQ Format name addressing guidelines.</span></span>  
  
```xml  
<appSettings>  
    <!-- Use appSetting to configure the MSMQ queue name. -->  
    <add key="queueName" value=".\private$\Orders" />  
</appSettings>  
```  
  
> [!NOTE]
>  <span data-ttu-id="e7de7-130">此示例需要安装[消息队列](http://go.microsoft.com/fwlink/?LinkId=95143)。</span><span class="sxs-lookup"><span data-stu-id="e7de7-130">This sample requires the installation of [Message Queuing](http://go.microsoft.com/fwlink/?LinkId=95143).</span></span>  
  
 <span data-ttu-id="e7de7-131">启动服务并运行客户端。</span><span class="sxs-lookup"><span data-stu-id="e7de7-131">Start the service and run the client.</span></span>  
  
 <span data-ttu-id="e7de7-132">下面的输出显示在客户端上。</span><span class="sxs-lookup"><span data-stu-id="e7de7-132">The following output is seen on the client.</span></span>  
  
```  
Placed the order:Purchase Order: 28fc457a-1a56-4fe0-9dde-156965c21ed6  
        Customer: somecustomer.com  
        OrderDetails  
                Order LineItem: 54 of Blue Widget @unit price: $29.99  
                Order LineItem: 890 of Red Widget @unit price: $45.89  
        Total cost of this order: $42461.56  
        Order status: Pending  
Canceled the Order: 28fc457a-1a56-4fe0-9dde-156965c21ed6  
Press <ENTER> to terminate client.  
```  
  
 <span data-ttu-id="e7de7-133">下面的输出必须显示在服务上。</span><span class="sxs-lookup"><span data-stu-id="e7de7-133">The following output must be seen on the service.</span></span>  
  
```  
The service is ready.  
Press <ENTER> to terminate service.  
Processing Purchase Order: 28fc457a-1a56-4fe0-9dde-156965c21ed6  
        Customer: somecustomer.com  
        OrderDetails  
                Order LineItem: 54 of Blue Widget @unit price: $29.99  
                Order LineItem: 890 of Red Widget @unit price: $45.89  
        Total cost of this order: $42461.56  
        Order status: Shipped  
Purchase Order 28fc457a-1a56-4fe0-9dde-156965c21ed6 is canceled  
```  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="e7de7-134">设置、生成和运行示例</span><span class="sxs-lookup"><span data-stu-id="e7de7-134">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="e7de7-135">确保已执行[的 Windows Communication Foundation 示例的一次性安装过程](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)。</span><span class="sxs-lookup"><span data-stu-id="e7de7-135">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2.  <span data-ttu-id="e7de7-136">如果先运行服务，则它将检查以确保队列存在。</span><span class="sxs-lookup"><span data-stu-id="e7de7-136">If the service is run first, it will check to ensure that the queue is present.</span></span> <span data-ttu-id="e7de7-137">如果队列不存在，则服务将创建一个队列。</span><span class="sxs-lookup"><span data-stu-id="e7de7-137">If the queue is not present, the service will create one.</span></span> <span data-ttu-id="e7de7-138">可以先运行服务以创建队列或通过 MSMQ 队列管理器创建一个队列。</span><span class="sxs-lookup"><span data-stu-id="e7de7-138">You can run the service first to create the queue, or you can create one via the MSMQ Queue Manager.</span></span> <span data-ttu-id="e7de7-139">执行下面的步骤来在 Windows 2008 中创建队列。</span><span class="sxs-lookup"><span data-stu-id="e7de7-139">Follow these steps to create a queue in Windows 2008.</span></span>  
  
    1.  <span data-ttu-id="e7de7-140">在 [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] 中打开服务器管理器。</span><span class="sxs-lookup"><span data-stu-id="e7de7-140">Open Server Manager in [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)].</span></span>  
  
    2.  <span data-ttu-id="e7de7-141">展开**功能**选项卡。</span><span class="sxs-lookup"><span data-stu-id="e7de7-141">Expand the **Features** tab.</span></span>  
  
    3.  <span data-ttu-id="e7de7-142">右键单击**私有消息队列**，然后选择**新建**，**专用队列**。</span><span class="sxs-lookup"><span data-stu-id="e7de7-142">Right-click **Private Message Queues**, and select **New**, **Private Queue**.</span></span>  
  
    4.  <span data-ttu-id="e7de7-143">检查**事务**框。</span><span class="sxs-lookup"><span data-stu-id="e7de7-143">Check the **Transactional** box.</span></span>  
  
    5.  <span data-ttu-id="e7de7-144">输入`ServiceModelSamplesTransacted`作为新队列的名称。</span><span class="sxs-lookup"><span data-stu-id="e7de7-144">Enter `ServiceModelSamplesTransacted` as the name of the new queue.</span></span>  
  
3.  <span data-ttu-id="e7de7-145">若要生成 C# 或 Visual Basic .NET 版本的解决方案，请按照 [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)中的说明进行操作。</span><span class="sxs-lookup"><span data-stu-id="e7de7-145">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
4.  <span data-ttu-id="e7de7-146">若要在单或跨计算机配置上运行示例，请按照中的说明[运行 Windows Communication Foundation 示例](../../../../docs/framework/wcf/samples/running-the-samples.md)。</span><span class="sxs-lookup"><span data-stu-id="e7de7-146">To run the sample in a single- or cross- computer configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
### <a name="to-run-the-sample-across-computers"></a><span data-ttu-id="e7de7-147">跨计算机运行示例</span><span class="sxs-lookup"><span data-stu-id="e7de7-147">To run the sample across computers</span></span>  
  
1.  <span data-ttu-id="e7de7-148">将 \service\bin\ 文件夹（在语言特定文件夹内）中的服务程序文件复制到服务计算机上。</span><span class="sxs-lookup"><span data-stu-id="e7de7-148">Copy the service program files from the \service\bin\ folder, under the language-specific folder, to the service computer.</span></span>  
  
2.  <span data-ttu-id="e7de7-149">将 \client\bin\ 文件夹（在语言特定文件夹内）中的客户端程序文件复制到客户端计算机上。</span><span class="sxs-lookup"><span data-stu-id="e7de7-149">Copy the client program files from the \client\bin\ folder, under the language-specific folder, to the client computer.</span></span>  
  
3.  <span data-ttu-id="e7de7-150">在 Client.exe.config 文件中，更改 orderQueueName 以指定服务计算机名称，而不是使用“.”。</span><span class="sxs-lookup"><span data-stu-id="e7de7-150">In the Client.exe.config file, change the orderQueueName to specify the service computer name instead of ".".</span></span>  
  
4.  <span data-ttu-id="e7de7-151">在服务计算机上，在命令提示符下启动 Service.exe。</span><span class="sxs-lookup"><span data-stu-id="e7de7-151">On the service computer, launch Service.exe from a command prompt.</span></span>  
  
5.  <span data-ttu-id="e7de7-152">在客户端计算机上，在命令提示符下启动 Client.exe。</span><span class="sxs-lookup"><span data-stu-id="e7de7-152">On the client computer, launch Client.exe from a command prompt.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="e7de7-153">您的计算机上可能已安装这些示例。</span><span class="sxs-lookup"><span data-stu-id="e7de7-153">The samples may already be installed on your computer.</span></span> <span data-ttu-id="e7de7-154">在继续操作之前，请先检查以下（默认）目录：</span><span class="sxs-lookup"><span data-stu-id="e7de7-154">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="e7de7-155">如果此目录不存在，请访问 [针对 .NET Framework 4 的 Windows Communication Foundation (WCF) 和 Windows Workflow Foundation (WF) 示例](http://go.microsoft.com/fwlink/?LinkId=150780) 以下载所有 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 和 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 示例。</span><span class="sxs-lookup"><span data-stu-id="e7de7-155">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="e7de7-156">此示例位于以下目录：</span><span class="sxs-lookup"><span data-stu-id="e7de7-156">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Binding\MSMQIntegration\CustomDemux`  
  
## <a name="see-also"></a><span data-ttu-id="e7de7-157">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e7de7-157">See Also</span></span>  
 [<span data-ttu-id="e7de7-158">在 WCF 中排队</span><span class="sxs-lookup"><span data-stu-id="e7de7-158">Queuing in WCF</span></span>](../../../../docs/framework/wcf/feature-details/queuing-in-wcf.md)  
 [<span data-ttu-id="e7de7-159">消息队列</span><span class="sxs-lookup"><span data-stu-id="e7de7-159">Message Queuing</span></span>](http://go.microsoft.com/fwlink/?LinkId=95143)
