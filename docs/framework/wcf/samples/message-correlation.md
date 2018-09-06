---
title: 消息相关性
ms.date: 03/30/2017
ms.assetid: 3f62babd-c991-421f-bcd8-391655c82a1f
ms.openlocfilehash: e4cd5dfd6f03370a408dc6f8fb39c983db3d43df
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/05/2018
ms.locfileid: "43732733"
---
# <a name="message-correlation"></a><span data-ttu-id="01ee5-102">消息相关性</span><span class="sxs-lookup"><span data-stu-id="01ee5-102">Message Correlation</span></span>
<span data-ttu-id="01ee5-103">此示例演示消息队列 (MSMQ) 应用程序如何可以将 MSMQ 消息发送到 Windows Communication Foundation (WCF) 服务以及如何消息也可以在请求/响应方案中的发送方和接收方应用程序之间关联起来。</span><span class="sxs-lookup"><span data-stu-id="01ee5-103">This sample demonstrates how a Message Queuing (MSMQ) application can send an MSMQ message to a Windows Communication Foundation (WCF) service and how messages can be correlated between sender and receiver applications in a request/response scenario.</span></span> <span data-ttu-id="01ee5-104">此示例使用 msmqIntegrationBinding 绑定。</span><span class="sxs-lookup"><span data-stu-id="01ee5-104">This sample uses the msmqIntegrationBinding binding.</span></span> <span data-ttu-id="01ee5-105">这种情况下的服务是自承载控制台应用程序，通过它可以观察接收排队消息的服务。</span><span class="sxs-lookup"><span data-stu-id="01ee5-105">The service in this case is a self-hosted console application to allow you to observe the service that receives queued messages.</span></span> <span data-ttu-id="01ee5-106">k</span><span class="sxs-lookup"><span data-stu-id="01ee5-106">k</span></span>  
  
 <span data-ttu-id="01ee5-107">该服务处理接收的来自发送方的消息，并向发送方回发一个响应消息。</span><span class="sxs-lookup"><span data-stu-id="01ee5-107">The service processes the message received from the sender and sends a response message back to the sender.</span></span> <span data-ttu-id="01ee5-108">发送方将它收到的响应与其最初发送的请求关联。</span><span class="sxs-lookup"><span data-stu-id="01ee5-108">The sender correlates the response it received to the request it sent originally.</span></span> <span data-ttu-id="01ee5-109">可以使用消息的 `MessageID` 和 `CorrelationID` 属性将请求消息与响应消息关联。</span><span class="sxs-lookup"><span data-stu-id="01ee5-109">The `MessageID` and `CorrelationID` properties of the message are used to correlate the request and response messages.</span></span>  
  
 <span data-ttu-id="01ee5-110">`IOrderProcessor` 服务协定定义了适合与队列一起使用的单向服务操作。</span><span class="sxs-lookup"><span data-stu-id="01ee5-110">The `IOrderProcessor` service contract defines a one-way service operation that is suitable for use with queuing.</span></span> <span data-ttu-id="01ee5-111">MSMQ 消息没有 Action 标头，因此无法将不同的 MSMQ 消息自动映射到操作协定。</span><span class="sxs-lookup"><span data-stu-id="01ee5-111">An MSMQ message does not have an Action header, so it is not possible to map different MSMQ messages to operation contracts automatically.</span></span> <span data-ttu-id="01ee5-112">因此，在这种情况下只有一个操作协定。</span><span class="sxs-lookup"><span data-stu-id="01ee5-112">Therefore, there can be only one operation contract in this case.</span></span> <span data-ttu-id="01ee5-113">如果您希望在服务中定义更多的操作协定，则应用程序必须提供相关信息，如 MSMQ 消息中的哪个标头（例如标签或 correlationID）可用于确定要调度的操作协定。</span><span class="sxs-lookup"><span data-stu-id="01ee5-113">If you want to define more operation contracts in the service, the application must provide information as to which header in the MSMQ message (for example, the label, or correlationID) can be used to decide which operation contract to dispatch.</span></span> <span data-ttu-id="01ee5-114">了这一点[自定义多路分解器](../../../../docs/framework/wcf/samples/custom-demux.md)。</span><span class="sxs-lookup"><span data-stu-id="01ee5-114">This is demonstrated in the [Custom Demux](../../../../docs/framework/wcf/samples/custom-demux.md).</span></span>  
  
 <span data-ttu-id="01ee5-115">MSMQ 消息也不包含诸如哪些标头映射到操作协定的不同参数等信息。</span><span class="sxs-lookup"><span data-stu-id="01ee5-115">The MSMQ message also does not contain information as to which headers are mapped to the different parameters of the operation contract.</span></span> <span data-ttu-id="01ee5-116">因此，在该操作协定中只有一个参数。</span><span class="sxs-lookup"><span data-stu-id="01ee5-116">Therefore, there can be only one parameter in the operation contract.</span></span> <span data-ttu-id="01ee5-117">参数的类型是<!--zz <xref:System.ServiceModel.MSMQIntegration.MsmqMessage%601>`MsmqMessage<T>`-->，`System.ServiceModel.MSMQIntegration.MsmqMessage`其中包含基础 MSMQ 消息。</span><span class="sxs-lookup"><span data-stu-id="01ee5-117">The parameter is of type <!--zz <xref:System.ServiceModel.MSMQIntegration.MsmqMessage%601>`MsmqMessage<T>`--> , `System.ServiceModel.MSMQIntegration.MsmqMessage` which contains the underlying MSMQ message.</span></span> <span data-ttu-id="01ee5-118">`MsmqMessage<T>` 类中的“T”类型表示序列化到 MSMQ 消息正文中的数据。</span><span class="sxs-lookup"><span data-stu-id="01ee5-118">The type "T" in the `MsmqMessage<T>` class represents the data that is serialized into the MSMQ message body.</span></span> <span data-ttu-id="01ee5-119">在此示例中，`PurchaseOrder` 类型序列化到 MSMQ 消息正文中。</span><span class="sxs-lookup"><span data-stu-id="01ee5-119">In this sample, the `PurchaseOrder` type is serialized into the MSMQ message body.</span></span>  

```csharp
[ServiceContract(Namespace = "http://Microsoft.ServiceModel.Samples")]  
[ServiceKnownType(typeof(PurchaseOrder))]  
public interface IOrderProcessor  
{  
    [OperationContract(IsOneWay = true, Action = "*")]  
    void SubmitPurchaseOrder(MsmqMessage<PurchaseOrder> msg);  
}  
```

 <span data-ttu-id="01ee5-120">服务操作处理采购订单，并在服务控制台窗口中显示采购订单的内容及其状态。</span><span class="sxs-lookup"><span data-stu-id="01ee5-120">The service operation processes the purchase order and displays the contents of the purchase order and its status in the service console window.</span></span> <span data-ttu-id="01ee5-121"><xref:System.ServiceModel.OperationBehaviorAttribute> 使用队列配置要在事务中登记的操作并在返回操作时标记事务已完成。</span><span class="sxs-lookup"><span data-stu-id="01ee5-121">The <xref:System.ServiceModel.OperationBehaviorAttribute> configures the operation to enlist in a transaction with the queue and to mark the transaction complete when the operation returns.</span></span> <span data-ttu-id="01ee5-122">`PurchaseOrder` 包含必须由服务处理的订单详细信息。</span><span class="sxs-lookup"><span data-stu-id="01ee5-122">The `PurchaseOrder` contains the order details that must be processed by the service.</span></span>  

```csharp
// Service class that implements the service contract.  
public class OrderProcessorService : IOrderProcessor  
{  
   [OperationBehavior(TransactionScopeRequired = true,   
          TransactionAutoComplete = true)]  
   public void SubmitPurchaseOrder(MsmqMessage<PurchaseOrder> ordermsg)  
   {  
       PurchaseOrder po = (PurchaseOrder)ordermsg.Body;  
       Random statusIndexer = new Random();  
       po.Status = PurchaseOrder.OrderStates[statusIndexer.Next(3)];  
       Console.WriteLine("Processing {0} ", po);  
       //Send a response to the client that the order has been received   
         and is pending fullfillment.   
       SendResponse(ordermsg);  
    }  
  
    private void SendResponse(MsmqMessage<PurchaseOrder> ordermsg)  
    {  
        OrderResponseClient client = new OrderResponseClient("OrderResponseEndpoint");  
  
        //Set the correlation ID such that the client can correlate the response to the order.  
        MsmqMessage<PurchaseOrder> orderResponsemsg = new MsmqMessage<PurchaseOrder>(ordermsg.Body);  
        orderResponsemsg.CorrelationId = ordermsg.Id;  
        using (TransactionScope scope = new TransactionScope(TransactionScopeOption.Required))  
        {  
            client.SendOrderResponse(orderResponsemsg);  
            scope.Complete();  
        }  
  
        client.Close();  
    }  
}  
```

 <span data-ttu-id="01ee5-123">服务使用自定义客户端 `OrderResponseClient` 将 MSMQ 消息发送到队列。</span><span class="sxs-lookup"><span data-stu-id="01ee5-123">The service uses a custom client `OrderResponseClient` to send the MSMQ message to the queue.</span></span> <span data-ttu-id="01ee5-124">接收并处理该消息的应用程序是 MSMQ 应用程序并是 WCF 应用程序，因为没有任何隐式服务协定之间两个应用程序。</span><span class="sxs-lookup"><span data-stu-id="01ee5-124">Because the application that receives and processes the message is an MSMQ application and not a WCF application, there is no implicit service contract between the two applications.</span></span> <span data-ttu-id="01ee5-125">所以在此方案中，我们不能使用 Svcutil.exe 工具创建代理。</span><span class="sxs-lookup"><span data-stu-id="01ee5-125">So we cannot create a proxy using the Svcutil.exe tool in this scenario.</span></span>  
  
 <span data-ttu-id="01ee5-126">自定义代理实质上是相同的使用的所有 WCF 应用程序`msmqIntegrationBinding`绑定发送消息。</span><span class="sxs-lookup"><span data-stu-id="01ee5-126">The custom proxy is essentially the same for all WCF applications that use the `msmqIntegrationBinding` binding to send messages.</span></span> <span data-ttu-id="01ee5-127">与其他代理不同，它不包含一系列服务操作。</span><span class="sxs-lookup"><span data-stu-id="01ee5-127">Unlike other proxies, it does not include a range of service operations.</span></span> <span data-ttu-id="01ee5-128">它只是一个提交消息操作。</span><span class="sxs-lookup"><span data-stu-id="01ee5-128">It is a submit message operation only.</span></span>  

```csharp
[System.ServiceModel.ServiceContractAttribute(Namespace = "http://Microsoft.ServiceModel.Samples")]  
public interface IOrderResponse  
{  
  
    [System.ServiceModel.OperationContractAttribute(IsOneWay = true, Action = "*")]  
    void SendOrderResponse(MsmqMessage<PurchaseOrder> msg);  
}  
  
public partial class OrderResponseClient : System.ServiceModel.ClientBase<IOrderResponse>, IOrderResponse  
{  
  
    public OrderResponseClient()  
    { }  
  
    public OrderResponseClient(string configurationName)  
        : base(configurationName)  
    { }  
  
    public OrderResponseClient(System.ServiceModel.Channels.Binding binding, System.ServiceModel.EndpointAddress address)  
        : base(binding, address)  
    { }  
  
    public void SendOrderResponse(MsmqMessage<PurchaseOrder> msg)  
    {  
        base.Channel.SendOrderResponse(msg);  
    }  
}  
```

 <span data-ttu-id="01ee5-129">服务是自承载服务。</span><span class="sxs-lookup"><span data-stu-id="01ee5-129">The service is self hosted.</span></span> <span data-ttu-id="01ee5-130">使用 MSMQ 集成传输时，必须提前创建所使用的队列。</span><span class="sxs-lookup"><span data-stu-id="01ee5-130">When using the MSMQ integration transport, the queue used must be created in advance.</span></span> <span data-ttu-id="01ee5-131">可以手动或通过代码完成此操作。</span><span class="sxs-lookup"><span data-stu-id="01ee5-131">This can be done manually or through code.</span></span> <span data-ttu-id="01ee5-132">在此示例中，服务包含 <xref:System.Messaging> 代码，以检查队列是否存在并在必要时创建队列。</span><span class="sxs-lookup"><span data-stu-id="01ee5-132">In this sample, the service contains <xref:System.Messaging> code to check for the existence of the queue and create it if necessary.</span></span> <span data-ttu-id="01ee5-133">从配置文件中读取队列名称。</span><span class="sxs-lookup"><span data-stu-id="01ee5-133">The queue name is read from the configuration file.</span></span>  

```csharp
public static void Main()  
{  
       // Get the MSMQ queue name from application settings in configuration.  
      string queueName =   
                ConfigurationManager.AppSettings["orderQueueName"];  
      // Create the transacted MSMQ queue if necessary.  
      if (!MessageQueue.Exists(queueName))  
                MessageQueue.Create(queueName, true);  
     // Create a ServiceHost for the OrderProcessorService type.  
     using (ServiceHost serviceHost = new   
                   ServiceHost(typeof(OrderProcessorService)))  
     {  
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
  
 <span data-ttu-id="01ee5-134">订单请求发送至的 MSMQ 队列是在配置文件的 appSettings 节中指定的。</span><span class="sxs-lookup"><span data-stu-id="01ee5-134">The MSMQ queue to which the order requests are sent is specified in the appSettings section of the configuration file.</span></span> <span data-ttu-id="01ee5-135">客户端终结点和服务终结点是在配置文件的 system.serviceModel 节中定义的。</span><span class="sxs-lookup"><span data-stu-id="01ee5-135">The client and service endpoints are defined in the system.serviceModel section of the configuration file.</span></span> <span data-ttu-id="01ee5-136">二者均指定了 `msmqIntegrationbinding` 绑定。</span><span class="sxs-lookup"><span data-stu-id="01ee5-136">Both specify the `msmqIntegrationbinding` binding.</span></span>  
  
```xml  
<appSettings>  
  <add key="orderQueueName" value=".\private$\Orders" />  
</appSettings>  
  
<system.serviceModel>  
  <client>  
    <endpoint    name="OrderResponseEndpoint"   
              address="msmq.formatname:DIRECT=OS:.\private$\OrderResponse"  
              binding="msmqIntegrationBinding"  
              bindingConfiguration="OrderProcessorBinding"   
              contract="Microsoft.ServiceModel.Samples.IOrderResponse">  
    </endpoint>  
  </client>  
  
  <services>  
    <service   
      name="Microsoft.ServiceModel.Samples.OrderProcessorService">  
      <endpoint address="msmq.formatname:DIRECT=OS:.\private$\Orders"  
                            binding="msmqIntegrationBinding"  
                bindingConfiguration="OrderProcessorBinding"   
                contract="Microsoft.ServiceModel.Samples.IOrderProcessor">  
      </endpoint>  
    </service>  
  </services>  
  
  <bindings>  
    <msmqIntegrationBinding>  
      <binding name="OrderProcessorBinding" >  
        <security mode="None" />  
      </binding>  
    </msmqIntegrationBinding>  
  </bindings>  
  
</system.serviceModel>  
```  
  
 <span data-ttu-id="01ee5-137">客户端应用程序使用 <xref:System.Messaging> 向队列发送持久的事务性消息。</span><span class="sxs-lookup"><span data-stu-id="01ee5-137">The client application uses <xref:System.Messaging> to send a durable and transactional message to the queue.</span></span> <span data-ttu-id="01ee5-138">消息的正文包含采购订单。</span><span class="sxs-lookup"><span data-stu-id="01ee5-138">The message's body contains the purchase order.</span></span>  

```csharp
static void PlaceOrder()  
{  
    //Connect to the queue  
    MessageQueue orderQueue =   
            new MessageQueue(  
                    ConfigurationManager.AppSettings["orderQueueName"])   
    // Create the purchase order.  
    PurchaseOrder po = new PurchaseOrder();  
    po.CustomerId = "somecustomer.com";  
    po.PONumber = Guid.NewGuid().ToString();  
    PurchaseOrderLineItem lineItem1 = new PurchaseOrderLineItem();  
    lineItem1.ProductId = "Blue Widget";  
    lineItem1.Quantity = 54;  
    lineItem1.UnitCost = 29.99F;  
  
    PurchaseOrderLineItem lineItem2 = new PurchaseOrderLineItem();  
    lineItem2.ProductId = "Red Widget";  
    lineItem2.Quantity = 890;  
    lineItem2.UnitCost = 45.89F;  
  
    po.orderLineItems = new PurchaseOrderLineItem[2];  
    po.orderLineItems[0] = lineItem1;  
    po.orderLineItems[1] = lineItem2;  
  
    Message msg = new Message();  
    msg.UseDeadLetterQueue = true;  
    msg.Body = po;  
  
    //Create a transaction scope.  
    using (TransactionScope scope = new      
     TransactionScope(TransactionScopeOption.Required))  
    {  
        // Submit the purchase order.  
        orderQueue.Send(msg, MessageQueueTransactionType.Automatic);  
        // Complete the transaction.  
        scope.Complete();  
    }  
    //Save the messageID for order response correlation.  
    orderMessageID = msg.Id;  
    Console.WriteLine("Placed the order, waiting for response...");  
}  
```

 <span data-ttu-id="01ee5-139">从中接收订单响应的 MSMQ 队列是在配置文件的 appSettings 节中定义的，如下面的示例配置所示。</span><span class="sxs-lookup"><span data-stu-id="01ee5-139">The MSMQ queue from which the order responses are received is specified in an appSettings section of the configuration file, as shown in the following sample configuration.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="01ee5-140">队列名称为本地计算机使用圆点 (.)，并在其路径中使用反斜杠分隔符。</span><span class="sxs-lookup"><span data-stu-id="01ee5-140">The queue name uses a dot (.) for the local computer and backslash separators in its path.</span></span> <span data-ttu-id="01ee5-141">WCF 终结点地址指定 msmq.formatname 方案，并为本地计算机使用"localhost"。</span><span class="sxs-lookup"><span data-stu-id="01ee5-141">The WCF endpoint address specifies a msmq.formatname scheme, and uses "localhost" for the local computer.</span></span> <span data-ttu-id="01ee5-142">根据 MSMQ 准则，格式正确的格式名称应遵循 URI 中的 msmq.formatname。</span><span class="sxs-lookup"><span data-stu-id="01ee5-142">A properly formed format name follows msmq.formatname in the URI according to MSMQ guidelines.</span></span>  
  
```xml  
<appSettings>  
    <add key=" orderResponseQueueName" value=".\private$\Orders" />  
</appSettings>  
```  
  
 <span data-ttu-id="01ee5-143">客户端应用程序保存发送到服务的订单请求消息的 `messageID`，并等待服务响应。</span><span class="sxs-lookup"><span data-stu-id="01ee5-143">The client application saves the `messageID` of the order request message that it sends to the service and waits for a response from the service.</span></span> <span data-ttu-id="01ee5-144">一旦响应到达队列，客户端使用消息的 `correlationID` 属性将该响应与客户端发送的订单消息关联，此属性包含客户端最初向服务发送的订单消息的 `messageID`。</span><span class="sxs-lookup"><span data-stu-id="01ee5-144">Once a response arrives in the queue the client correlates it with the order message it sent using the `correlationID` property of the message, which contains the `messageID` of the order message that the client sent to the service originally.</span></span>  

```csharp
static void DisplayOrderStatus()  
{  
    MessageQueue orderResponseQueue = new   
     MessageQueue(ConfigurationManager.AppSettings              
                  ["orderResponseQueueName"]);  
    //Create a transaction scope.  
    bool responseReceived = false;  
    orderResponseQueue.MessageReadPropertyFilter.CorrelationId = true;  
    while (!responseReceived)  
    {  
       Message responseMsg;  
       using (TransactionScope scope2 = new    
         TransactionScope(TransactionScopeOption.Required))  
       {  
          //Receive the Order Response message.  
          responseMsg =   
              orderResponseQueue.Receive  
                   (MessageQueueTransactionType.Automatic);  
          scope2.Complete();  
     }  
     responseMsg.Formatter = new   
     System.Messaging.XmlMessageFormatter(new Type[] {   
         typeof(PurchaseOrder) });  
     PurchaseOrder responsepo = (PurchaseOrder)responseMsg.Body;  
    //Check if the response is for the order placed.  
    if (orderMessageID == responseMsg.CorrelationId)  
    {  
       responseReceived = true;  
       Console.WriteLine("Status of current Order: OrderID-{0},Order   
            Status-{1}", responsepo.PONumber, responsepo.Status);  
    }  
    else  
    {  
       Console.WriteLine("Status of previous Order: OrderID-{0},Order    
            Status-{1}", responsepo.PONumber, responsepo.Status);  
    }  
  }  
}  
```

 <span data-ttu-id="01ee5-145">运行示例时，客户端和服务活动将显示在服务和客户端控制台窗口中。</span><span class="sxs-lookup"><span data-stu-id="01ee5-145">When you run the sample, the client and service activities are displayed in both the service and client console windows.</span></span> <span data-ttu-id="01ee5-146">可以看到服务接收来自客户端的消息，并向客户端回发响应。</span><span class="sxs-lookup"><span data-stu-id="01ee5-146">You can see the service receive messages from the client and sends a response back to the client.</span></span> <span data-ttu-id="01ee5-147">客户端会显示来自服务的响应。</span><span class="sxs-lookup"><span data-stu-id="01ee5-147">The client displays the response received from the service.</span></span> <span data-ttu-id="01ee5-148">在每个控制台窗口中按 Enter 可以关闭服务和客户端。</span><span class="sxs-lookup"><span data-stu-id="01ee5-148">Press ENTER in each console window to shut down the service and client.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="01ee5-149">此示例要求安装消息队列 (MSMQ)。</span><span class="sxs-lookup"><span data-stu-id="01ee5-149">This sample requires the installation of Message Queuing (MSMQ).</span></span> <span data-ttu-id="01ee5-150">请参阅“请参见”部分中的 MSMQ 安装说明。</span><span class="sxs-lookup"><span data-stu-id="01ee5-150">See the MSMQ installation instructions in the See Also section.</span></span>  
  
### <a name="to-setup-build-and-run-the-sample"></a><span data-ttu-id="01ee5-151">设置、生成和运行示例</span><span class="sxs-lookup"><span data-stu-id="01ee5-151">To setup, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="01ee5-152">请确保您具有执行[的 Windows Communication Foundation 示例的一次性安装过程](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)。</span><span class="sxs-lookup"><span data-stu-id="01ee5-152">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2.  <span data-ttu-id="01ee5-153">如果先运行服务，则它将检查以确保队列存在。</span><span class="sxs-lookup"><span data-stu-id="01ee5-153">If the service is run first, it will check to ensure that the queue is present.</span></span> <span data-ttu-id="01ee5-154">如果队列不存在，则服务将创建一个队列。</span><span class="sxs-lookup"><span data-stu-id="01ee5-154">If the queue is not present, the service will create one.</span></span> <span data-ttu-id="01ee5-155">可以先运行服务以创建队列或通过 MSMQ 队列管理器创建一个队列。</span><span class="sxs-lookup"><span data-stu-id="01ee5-155">You can run the service first to create the queue, or you can create one via the MSMQ Queue Manager.</span></span> <span data-ttu-id="01ee5-156">执行下面的步骤来在 Windows 2008 中创建队列。</span><span class="sxs-lookup"><span data-stu-id="01ee5-156">Follow these steps to create a queue in Windows 2008.</span></span>  
  
    1.  <span data-ttu-id="01ee5-157">在 [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] 中打开服务器管理器。</span><span class="sxs-lookup"><span data-stu-id="01ee5-157">Open Server Manager in [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)].</span></span>  
  
    2.  <span data-ttu-id="01ee5-158">展开**功能**选项卡。</span><span class="sxs-lookup"><span data-stu-id="01ee5-158">Expand the **Features** tab.</span></span>  
  
    3.  <span data-ttu-id="01ee5-159">右键单击**私有消息队列**，然后选择**新建**，**专用队列**。</span><span class="sxs-lookup"><span data-stu-id="01ee5-159">Right-click **Private Message Queues**, and select **New**, **Private Queue**.</span></span>  
  
    4.  <span data-ttu-id="01ee5-160">检查**事务性**框。</span><span class="sxs-lookup"><span data-stu-id="01ee5-160">Check the **Transactional** box.</span></span>  
  
    5.  <span data-ttu-id="01ee5-161">输入`ServiceModelSamplesTransacted`作为新队列的名称。</span><span class="sxs-lookup"><span data-stu-id="01ee5-161">Enter `ServiceModelSamplesTransacted` as the name of the new queue.</span></span>  
  
3.  <span data-ttu-id="01ee5-162">若要生成 C# 或 Visual Basic .NET 版本的解决方案，请按照 [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)中的说明进行操作。</span><span class="sxs-lookup"><span data-stu-id="01ee5-162">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
4.  <span data-ttu-id="01ee5-163">若要在单计算机配置中运行示例，请按照中的说明[运行 Windows Communication Foundation 示例](../../../../docs/framework/wcf/samples/running-the-samples.md)。</span><span class="sxs-lookup"><span data-stu-id="01ee5-163">To run the sample in a single-computer configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
### <a name="to-run-the-sample-across-computers"></a><span data-ttu-id="01ee5-164">跨计算机运行示例</span><span class="sxs-lookup"><span data-stu-id="01ee5-164">To run the sample across computers</span></span>  
  
1.  <span data-ttu-id="01ee5-165">将 \service\bin\ 文件夹（在语言特定文件夹内）中的服务程序文件复制到服务计算机上。</span><span class="sxs-lookup"><span data-stu-id="01ee5-165">Copy the service program files from the \service\bin\ folder, under the language-specific folder, to the service computer.</span></span>  
  
2.  <span data-ttu-id="01ee5-166">将 \client\bin\ 文件夹（在语言特定文件夹内）中的客户端程序文件复制到客户端计算机上。</span><span class="sxs-lookup"><span data-stu-id="01ee5-166">Copy the client program files from the \client\bin\ folder, under the language-specific folder, to the client computer.</span></span>  
  
3.  <span data-ttu-id="01ee5-167">在 Client.exe.config 文件中，更改 orderQueueName 以指定服务计算机名称，而不是使用“.”。</span><span class="sxs-lookup"><span data-stu-id="01ee5-167">In the Client.exe.config file, change the orderQueueName to specify the service computer name instead of ".".</span></span>  
  
4.  <span data-ttu-id="01ee5-168">在 Service.exe.config 文件中，更改客户端终结点地址以指定客户端计算机名称，而不是使用“.”。</span><span class="sxs-lookup"><span data-stu-id="01ee5-168">In the Service.exe.config file, change the client endpoint address to specify the client computer name instead of ".".</span></span>  
  
5.  <span data-ttu-id="01ee5-169">在服务计算机上，在命令提示符下启动 Service.exe。</span><span class="sxs-lookup"><span data-stu-id="01ee5-169">On the service computer, launch Service.exe from a command prompt.</span></span>  
  
6.  <span data-ttu-id="01ee5-170">在客户端计算机上，在命令提示符下启动 Client.exe。</span><span class="sxs-lookup"><span data-stu-id="01ee5-170">On the client computer, launch Client.exe from a command prompt.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="01ee5-171">您的计算机上可能已安装这些示例。</span><span class="sxs-lookup"><span data-stu-id="01ee5-171">The samples may already be installed on your computer.</span></span> <span data-ttu-id="01ee5-172">在继续操作之前，请先检查以下（默认）目录：</span><span class="sxs-lookup"><span data-stu-id="01ee5-172">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="01ee5-173">如果此目录不存在，请转到[Windows Communication Foundation (WCF) 和.NET Framework 4 的 Windows Workflow Foundation (WF) 示例](https://go.microsoft.com/fwlink/?LinkId=150780)若要下载所有 Windows Communication Foundation (WCF) 和[!INCLUDE[wf1](../../../../includes/wf1-md.md)]示例。</span><span class="sxs-lookup"><span data-stu-id="01ee5-173">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="01ee5-174">此示例位于以下目录：</span><span class="sxs-lookup"><span data-stu-id="01ee5-174">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Binding\MSMQIntegration\MessageCorrelation`  
  
## <a name="see-also"></a><span data-ttu-id="01ee5-175">请参阅</span><span class="sxs-lookup"><span data-stu-id="01ee5-175">See Also</span></span>  
 [<span data-ttu-id="01ee5-176">在 WCF 中排队</span><span class="sxs-lookup"><span data-stu-id="01ee5-176">Queuing in WCF</span></span>](../../../../docs/framework/wcf/feature-details/queuing-in-wcf.md)  
 [<span data-ttu-id="01ee5-177">消息队列</span><span class="sxs-lookup"><span data-stu-id="01ee5-177">Message Queuing</span></span>](https://go.microsoft.com/fwlink/?LinkId=94968)
