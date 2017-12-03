---
title: "事务处理批处理"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ecd328ed-332e-479c-a894-489609bcddd2
caps.latest.revision: "23"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: cc04f0ce1d303a32cbf2232c76bfc4ef1143c9ea
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2017
---
# <a name="transacted-batching"></a><span data-ttu-id="27d2e-102">事务处理批处理</span><span class="sxs-lookup"><span data-stu-id="27d2e-102">Transacted Batching</span></span>
<span data-ttu-id="27d2e-103">本示例演示如何通过使用消息队列 (MSMQ) 来批处理事务处理读取。</span><span class="sxs-lookup"><span data-stu-id="27d2e-103">This sample demonstrates how to batch transacted reads by using Message Queuing (MSMQ).</span></span> <span data-ttu-id="27d2e-104">事务处理批处理是排队通信中事务处理读取的一种性能优化功能。</span><span class="sxs-lookup"><span data-stu-id="27d2e-104">Transacted Batching is a performance optimization feature for transacted reads in queued communication.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="27d2e-105">本主题的最后介绍了此示例的设置过程和生成说明。</span><span class="sxs-lookup"><span data-stu-id="27d2e-105">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="27d2e-106">在排队通信中，客户端使用队列与服务进行通信。</span><span class="sxs-lookup"><span data-stu-id="27d2e-106">In queued communication, the client communicates to the service using a queue.</span></span> <span data-ttu-id="27d2e-107">更确切地说，客户端向队列发送消息。</span><span class="sxs-lookup"><span data-stu-id="27d2e-107">More precisely, the client sends messages to a queue.</span></span> <span data-ttu-id="27d2e-108">服务从队列接收消息。</span><span class="sxs-lookup"><span data-stu-id="27d2e-108">The service receives messages from the queue.</span></span> <span data-ttu-id="27d2e-109">因此不必同时运行服务和客户端便可使用队列进行通信。</span><span class="sxs-lookup"><span data-stu-id="27d2e-109">The service and client therefore, do not have to be running at the same time to communicate using a queue.</span></span>  
  
 <span data-ttu-id="27d2e-110">本示例演示事务处理批处理。</span><span class="sxs-lookup"><span data-stu-id="27d2e-110">This sample demonstrates transacted batching.</span></span> <span data-ttu-id="27d2e-111">事务处理批处理是一种行为，通过该行为可以在读取队列中的多个消息并处理这些消息时使用单个事务。</span><span class="sxs-lookup"><span data-stu-id="27d2e-111">Transacted batching is a behavior that enables the use of a single transaction when reading many messages in the queue and processing them.</span></span>  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="27d2e-112">设置、生成和运行示例</span><span class="sxs-lookup"><span data-stu-id="27d2e-112">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="27d2e-113">确保已执行[的 Windows Communication Foundation 示例的一次性安装过程](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)。</span><span class="sxs-lookup"><span data-stu-id="27d2e-113">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2.  <span data-ttu-id="27d2e-114">如果先运行服务，则它将检查以确保队列存在。</span><span class="sxs-lookup"><span data-stu-id="27d2e-114">If the service is run first, it will check to ensure that the queue is present.</span></span> <span data-ttu-id="27d2e-115">如果队列不存在，则服务将创建一个队列。</span><span class="sxs-lookup"><span data-stu-id="27d2e-115">If the queue is not present, the service will create one.</span></span> <span data-ttu-id="27d2e-116">可以先运行服务以创建队列或通过 MSMQ 队列管理器创建一个队列。</span><span class="sxs-lookup"><span data-stu-id="27d2e-116">You can run the service first to create the queue, or you can create one via the MSMQ Queue Manager.</span></span> <span data-ttu-id="27d2e-117">执行下面的步骤来在 Windows 2008 中创建队列。</span><span class="sxs-lookup"><span data-stu-id="27d2e-117">Follow these steps to create a queue in Windows 2008.</span></span>  
  
    1.  <span data-ttu-id="27d2e-118">在 [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] 中打开服务器管理器。</span><span class="sxs-lookup"><span data-stu-id="27d2e-118">Open Server Manager in [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)].</span></span>  
  
    2.  <span data-ttu-id="27d2e-119">展开**功能**选项卡。</span><span class="sxs-lookup"><span data-stu-id="27d2e-119">Expand the **Features** tab.</span></span>  
  
    3.  <span data-ttu-id="27d2e-120">右键单击**私有消息队列**，然后选择**新建**，**专用队列**。</span><span class="sxs-lookup"><span data-stu-id="27d2e-120">Right-click **Private Message Queues**, and select **New**, **Private Queue**.</span></span>  
  
    4.  <span data-ttu-id="27d2e-121">检查**事务**框。</span><span class="sxs-lookup"><span data-stu-id="27d2e-121">Check the **Transactional** box.</span></span>  
  
    5.  <span data-ttu-id="27d2e-122">输入`ServiceModelSamplesTransacted`作为新队列的名称。</span><span class="sxs-lookup"><span data-stu-id="27d2e-122">Enter `ServiceModelSamplesTransacted` as the name of the new queue.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="27d2e-123">在此示例中，客户端将数以百计的消息作为批的一部分发送。</span><span class="sxs-lookup"><span data-stu-id="27d2e-123">In this sample the client sends hundreds of messages as part of the batch.</span></span> <span data-ttu-id="27d2e-124">通常，服务应用程序会花一些时间处理这些消息。</span><span class="sxs-lookup"><span data-stu-id="27d2e-124">It is normal for the service application to take some time to process these.</span></span>  
  
3.  <span data-ttu-id="27d2e-125">若要生成 C# 或 Visual Basic .NET 版本的解决方案，请按照 [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)中的说明进行操作。</span><span class="sxs-lookup"><span data-stu-id="27d2e-125">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
4.  <span data-ttu-id="27d2e-126">若要在单或跨计算机配置上运行示例，请按照中的说明[运行 Windows Communication Foundation 示例](../../../../docs/framework/wcf/samples/running-the-samples.md)。</span><span class="sxs-lookup"><span data-stu-id="27d2e-126">To run the sample in a single- or cross-computer configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
### <a name="to-run-the-sample-on-a-computer-joined-to-a-workgroup-or-without-active-directory-integration"></a><span data-ttu-id="27d2e-127">在加入到工作组或在没有 Active Directory 集成的计算机上运行示例</span><span class="sxs-lookup"><span data-stu-id="27d2e-127">To run the sample on a computer joined to a workgroup or without active directory integration</span></span>  
  
1.  <span data-ttu-id="27d2e-128">默认情况下使用 <xref:System.ServiceModel.NetMsmqBinding> 启用传输安全。</span><span class="sxs-lookup"><span data-stu-id="27d2e-128">By default with the <xref:System.ServiceModel.NetMsmqBinding>, transport security is enabled.</span></span> <span data-ttu-id="27d2e-129">有两个相关属性对于 MSMQ 传输安全，<xref:System.ServiceModel.MsmqTransportSecurity.MsmqAuthenticationMode%2A>和<xref:System.ServiceModel.MsmqTransportSecurity.MsmqProtectionLevel%2A>`.`默认情况下，身份验证模式设置为`Windows`和保护级别设置为`Sign`。</span><span class="sxs-lookup"><span data-stu-id="27d2e-129">There are two relevant properties for MSMQ transport security, <xref:System.ServiceModel.MsmqTransportSecurity.MsmqAuthenticationMode%2A> and <xref:System.ServiceModel.MsmqTransportSecurity.MsmqProtectionLevel%2A>`.` By default, the authentication mode is set to `Windows` and the protection level is set to `Sign`.</span></span> <span data-ttu-id="27d2e-130">为了使 MSMQ 提供身份验证和签名功能，MSMQ 必须是域的一部分，并且必须安装 MSMQ 的 Active Directory 集成选项。</span><span class="sxs-lookup"><span data-stu-id="27d2e-130">For MSMQ to provide the authentication and signing feature, it must be part of a domain and the active directory integration option for MSMQ must be installed.</span></span> <span data-ttu-id="27d2e-131">如果在不满足这些条件的计算机上运行此示例，将会收到错误。</span><span class="sxs-lookup"><span data-stu-id="27d2e-131">If you run this sample on a computer that does not satisfy these criteria you receive an error.</span></span>  
  
2.  <span data-ttu-id="27d2e-132">如果计算机不是域成员或尚未安装 Active Directory 集成，请将身份验证模式和保护级别设置为 `None` 以关闭传输安全性，如下面的示例配置所示：</span><span class="sxs-lookup"><span data-stu-id="27d2e-132">If your computer is not part of a domain or does not have active directory integration installed, turn off transport security by setting the authentication mode and protection level to `None` as shown in the following sample configuration:</span></span>  
  
    ```xml  
    <system.serviceModel>  
      <behaviors>  
        <serviceBehaviors>  
          <behavior name="ThrottlingBehavior">  
            <serviceMetadata httpGetEnabled="true"/>  
            <serviceThrottling maxConcurrentCalls="5"/>  
          </behavior>  
        </serviceBehaviors>  
  
        <endpointBehaviors>  
          <behavior name="BatchingBehavior">  
            <transactedBatching maxBatchSize="100"/>  
          </behavior>  
        </endpointBehaviors>  
      </behaviors>  
      <services>  
        <service   
            behaviorConfiguration="ThrottlingBehavior"   
            name="Microsoft.ServiceModel.Samples.OrderProcessorService">  
          <host>  
            <baseAddresses>  
              <add baseAddress="http://localhost:8000/orderProcessor/transactedBatchingSample"/>  
            </baseAddresses>  
          </host>  
          <!-- Define NetMsmqEndpoint -->  
          <endpoint address="net.msmq://localhost/private/ServiceModelSamplesTransactedBatching"  
                    binding="netMsmqBinding"  
                    bindingConfiguration="Binding1"   
                    behaviorConfiguration="BatchingBehavior"   
                    contract="Microsoft.ServiceModel.Samples.IOrderProcessor" />  
          <endpoint address="mex"  
                    binding="mexHttpBinding"  
                    contract="IMetadataExchange" />  
        </service>  
      </services>  
  
      <bindings>  
        <netMsmqBinding>  
          <binding name="Binding1">  
            <security mode="None" />  
          </binding>  
        </netMsmqBinding>  
      </bindings>  
  
    </system.serviceModel>  
    ```  
  
3.  <span data-ttu-id="27d2e-133">确保在运行示例前更改服务器和客户端上的配置。</span><span class="sxs-lookup"><span data-stu-id="27d2e-133">Ensure that you change the configuration on both the server and the client before you run the sample.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="27d2e-134">将 `security``mode` 设置为 `None` 等效于将 <xref:System.ServiceModel.MsmqTransportSecurity.MsmqAuthenticationMode%2A>、<xref:System.ServiceModel.MsmqTransportSecurity.MsmqProtectionLevel%2A> 和 `Message` 安全设置为 `None`。</span><span class="sxs-lookup"><span data-stu-id="27d2e-134">Setting `security``mode` to `None` is equivalent to setting <xref:System.ServiceModel.MsmqTransportSecurity.MsmqAuthenticationMode%2A>, <xref:System.ServiceModel.MsmqTransportSecurity.MsmqProtectionLevel%2A>, and `Message` security to `None`.</span></span>  
  
4.  <span data-ttu-id="27d2e-135">若要在远程计算机上运行数据库，请更改连接字符串，使其指向数据库所在的计算机。</span><span class="sxs-lookup"><span data-stu-id="27d2e-135">To run the database on a remote computer, change the connection string to point to the computer on which the database resides.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="27d2e-136">要求</span><span class="sxs-lookup"><span data-stu-id="27d2e-136">Requirements</span></span>  
 <span data-ttu-id="27d2e-137">若要运行此示例，必须安装 MSMQ 并需要使用 SQL 或 SQL Express。</span><span class="sxs-lookup"><span data-stu-id="27d2e-137">To run this sample, MSMQ must be installed and SQL or SQL Express is required.</span></span>  
  
## <a name="demonstrates"></a><span data-ttu-id="27d2e-138">演示</span><span class="sxs-lookup"><span data-stu-id="27d2e-138">Demonstrates</span></span>  
 <span data-ttu-id="27d2e-139">本示例演示事务处理批处理行为。</span><span class="sxs-lookup"><span data-stu-id="27d2e-139">The sample demonstrates transacted batching behavior.</span></span> <span data-ttu-id="27d2e-140">事务处理批处理是随 MSMQ 排队传输一起提供的一种性能优化功能。</span><span class="sxs-lookup"><span data-stu-id="27d2e-140">Transacted batching is a performance optimization feature provided with MSMQ queued transport.</span></span>  
  
 <span data-ttu-id="27d2e-141">当使用事务来发送和接收消息时，实际上有两个单独的事务。</span><span class="sxs-lookup"><span data-stu-id="27d2e-141">When transactions are used to send and receive messages there are actually 2 separate transactions.</span></span> <span data-ttu-id="27d2e-142">当客户端在事务范围内发送消息时，事务相对于客户端和客户端队列管理器来说是本地事务。</span><span class="sxs-lookup"><span data-stu-id="27d2e-142">When the client sends messages within the scope of a transaction, the transaction is local to the client and the client queue manager.</span></span> <span data-ttu-id="27d2e-143">当服务在事务范围内接收消息时，事务相对于服务和接收队列管理器来说是本地事务。</span><span class="sxs-lookup"><span data-stu-id="27d2e-143">When the service receives messages within the scope of the transaction, the transaction is local to the service and the receiving queue manager.</span></span> <span data-ttu-id="27d2e-144">务必要记住的是，客户端和服务不会参与同一个事务；实际上，它们在对队列执行操作（如发送和接收）时使用的是不同的事务。</span><span class="sxs-lookup"><span data-stu-id="27d2e-144">It is very important to remember that the client and the service are not participating in the same transaction; rather they are using different transactions when performing their operations (such as send and receive) with the queue.</span></span>  
  
 <span data-ttu-id="27d2e-145">在本示例中，我们将使用单个事务来执行多个服务操作。</span><span class="sxs-lookup"><span data-stu-id="27d2e-145">In the sample we use a single transaction for the execution of multiple service operations.</span></span> <span data-ttu-id="27d2e-146">这仅作为一种性能优化功能，并不影响应用程序的语义。</span><span class="sxs-lookup"><span data-stu-id="27d2e-146">This is used only as a performance optimization feature and does not impact the semantics of the application.</span></span> <span data-ttu-id="27d2e-147">示例基于[事务性 MSMQ 绑定](../../../../docs/framework/wcf/samples/transacted-msmq-binding.md)。</span><span class="sxs-lookup"><span data-stu-id="27d2e-147">The sample is based on [Transacted MSMQ Binding](../../../../docs/framework/wcf/samples/transacted-msmq-binding.md).</span></span>  
  
## <a name="comments"></a><span data-ttu-id="27d2e-148">注释</span><span class="sxs-lookup"><span data-stu-id="27d2e-148">Comments</span></span>  
 <span data-ttu-id="27d2e-149">在本示例中，客户端在事务范围内向服务发送一批消息。</span><span class="sxs-lookup"><span data-stu-id="27d2e-149">In this sample, the client sends a batch of messages to the service from within the scope of a transaction.</span></span> <span data-ttu-id="27d2e-150">为了演示性能优化，我们将发送大量消息，在本例中，最多达 2500 条消息。</span><span class="sxs-lookup"><span data-stu-id="27d2e-150">To show the performance optimization, we send a large number of messages; in this case, up to 2500 messages.</span></span>  
  
 <span data-ttu-id="27d2e-151">然后，服务在服务定义的事务范围内接收发送到队列的消息。</span><span class="sxs-lookup"><span data-stu-id="27d2e-151">The messages sent to the queue are then received by the service within the transaction scope defined by the service.</span></span> <span data-ttu-id="27d2e-152">如果不进行批处理，这将导致每次调用服务操作都会产生 2500 个事务。</span><span class="sxs-lookup"><span data-stu-id="27d2e-152">Without batching, this results in 2500 transactions for each invocation of the service operation.</span></span> <span data-ttu-id="27d2e-153">这会影响系统的性能。</span><span class="sxs-lookup"><span data-stu-id="27d2e-153">This impacts performance of the system.</span></span> <span data-ttu-id="27d2e-154">由于涉及到两个资源管理器（MSMQ 队列和 `Orders` 数据库），因此，每个这样的事务都是一个 DTC 事务。</span><span class="sxs-lookup"><span data-stu-id="27d2e-154">Because two resource managers are involved -the MSMQ queue and the `Orders` database- each such transaction is a DTC transaction.</span></span> <span data-ttu-id="27d2e-155">我们通过使用数量少得多的事务确保在单个事务中处理一批消息并进行服务操作调用，以此来进行优化。</span><span class="sxs-lookup"><span data-stu-id="27d2e-155">We optimize this by using a much smaller number of transactions by ensuring that a batch of messages and service operation invocations happen in a single transaction.</span></span>  
  
 <span data-ttu-id="27d2e-156">我们通过以下方式使用批处理功能：</span><span class="sxs-lookup"><span data-stu-id="27d2e-156">We use the batching feature by:</span></span>  
  
-   <span data-ttu-id="27d2e-157">在配置中指定事务处理批处理行为。</span><span class="sxs-lookup"><span data-stu-id="27d2e-157">Specifying transacted batching behavior in configuration.</span></span>  
  
-   <span data-ttu-id="27d2e-158">按照要使用单个事务读取的消息的数量来指定批次大小。</span><span class="sxs-lookup"><span data-stu-id="27d2e-158">Specifying a batch size in terms of number of messages to be read using a single transaction.</span></span>  
  
-   <span data-ttu-id="27d2e-159">指定要运行的并发批次的最大数量。</span><span class="sxs-lookup"><span data-stu-id="27d2e-159">Specifying the maximum number of concurrent batches to run.</span></span>  
  
 <span data-ttu-id="27d2e-160">在本示例中，我们通过减少事务数量，确保在提交事务之前在单个事务中调用 100 次服务操作，以此来演示性能的提升。</span><span class="sxs-lookup"><span data-stu-id="27d2e-160">In this example, we show performance gains by reducing the number of transactions by ensuring that 100 service operations are invoked in a single transaction before committing the transaction.</span></span>  
  
 <span data-ttu-id="27d2e-161">服务行为通过将 `TransactionScopeRequired` 设置为 `true` 来定义操作行为。</span><span class="sxs-lookup"><span data-stu-id="27d2e-161">The service behavior defines an operation behavior with `TransactionScopeRequired` set to `true`.</span></span> <span data-ttu-id="27d2e-162">这可确保此方法所访问的任何资源管理器都使用相同的事务范围从队列中检索消息。</span><span class="sxs-lookup"><span data-stu-id="27d2e-162">This ensures that the same transaction scope that is used to retrieve the message from the queue is used by any resource managers accessed by the method.</span></span> <span data-ttu-id="27d2e-163">在此示例中，我们使用一个基本数据库来存储消息中包含的采购订单信息。</span><span class="sxs-lookup"><span data-stu-id="27d2e-163">In this example, we use a basic database to store the purchase order information contained in the message.</span></span> <span data-ttu-id="27d2e-164">事务范围还可保证该方法引发异常时，消息将返回到队列。</span><span class="sxs-lookup"><span data-stu-id="27d2e-164">The transaction scope also guarantees that if the method throws an exception, the message is returned to the queue.</span></span> <span data-ttu-id="27d2e-165">如果不设置此操作行为，则队列通道会创建一个从队列中读取消息的事务，并在调度消息前自动提交事务，因此，如果操作失败，消息将丢失。</span><span class="sxs-lookup"><span data-stu-id="27d2e-165">Without setting this operation behavior, a queued channel creates a transaction to read the message from the queue and commits it automatically before it is dispatched so that if the operation fails, the message is lost.</span></span> <span data-ttu-id="27d2e-166">最常见的方案是在用于从队列中读取消息的事务中登记服务操作，如下面的代码所示。</span><span class="sxs-lookup"><span data-stu-id="27d2e-166">The most common scenario is for service operations to enlist in the transaction that is used to read the message from the queue as demonstrated in the following code.</span></span>  
  
 <span data-ttu-id="27d2e-167">请注意，`ReleaseServiceInstanceOnTransactionComplete` 设置为 `false`。</span><span class="sxs-lookup"><span data-stu-id="27d2e-167">Note that `ReleaseServiceInstanceOnTransactionComplete` is set to `false`.</span></span> <span data-ttu-id="27d2e-168">这是批处理的一个重要要求。</span><span class="sxs-lookup"><span data-stu-id="27d2e-168">This is an important requirement for batching.</span></span> <span data-ttu-id="27d2e-169">`ReleaseServiceInstanceOnTransactionComplete` 上的 `ServiceBehaviorAttribute` 属性指示事务完成后对服务实例执行什么操作。</span><span class="sxs-lookup"><span data-stu-id="27d2e-169">The property `ReleaseServiceInstanceOnTransactionComplete` on `ServiceBehaviorAttribute` indicates what to do with the service instance once the transaction is completed.</span></span> <span data-ttu-id="27d2e-170">默认情况下，事务一旦完成即释放服务实例。</span><span class="sxs-lookup"><span data-stu-id="27d2e-170">By default, the service instance is released upon completing the transaction.</span></span> <span data-ttu-id="27d2e-171">批处理的核心方面是使用单个事务来读取和调度队列中的许多消息。</span><span class="sxs-lookup"><span data-stu-id="27d2e-171">The core aspect to batching is the use of a single transaction for reading and dispatching many messages in the queue.</span></span> <span data-ttu-id="27d2e-172">因此，释放服务实例会导致事务结束，从而过早地取消批处理的真正使用。</span><span class="sxs-lookup"><span data-stu-id="27d2e-172">Therefore releasing the service instance ends up completing the transaction prematurely negating the very use of batching.</span></span> <span data-ttu-id="27d2e-173">如果此属性设置为 `true`，并且将事务处理批处理行为添加到终结点，则批处理验证行为将引发异常。</span><span class="sxs-lookup"><span data-stu-id="27d2e-173">If this property is set to `true` and transacted batching behavior is added to the endpoint, the batching validation behavior throws an exception.</span></span>  
  
```  
// Service class that implements the service contract.  
// Added code to write output to the console window.  
[ServiceBehavior(ReleaseServiceInstanceOnTransactionComplete=false,   
TransactionIsolationLevel=  
System.Transactions.IsolationLevel.Serializable, ConcurrencyMode=ConcurrencyMode.Multiple)]  
public class OrderProcessorService : IOrderProcessor  
{  
    [OperationBehavior(TransactionScopeRequired = true,  
                       TransactionAutoComplete = true)]  
    public void SubmitPurchaseOrder(PurchaseOrder po)  
    {  
        Orders.Add(po);  
        Console.WriteLine("Processing {0} ", po);  
    }  
    …  
}  
```  
  
 <span data-ttu-id="27d2e-174">`Orders` 类包装了订单处理。</span><span class="sxs-lookup"><span data-stu-id="27d2e-174">The `Orders` class encapsulates the processing of the order.</span></span> <span data-ttu-id="27d2e-175">在此示例中，它用采购订单信息更新数据库。</span><span class="sxs-lookup"><span data-stu-id="27d2e-175">In the sample, it updates the database with purchase order information.</span></span>  
  
```  
// Order Processing Logic  
public class Orders  
{  
    public static void Add(PurchaseOrder po)  
    {  
        // Insert purchase order.  
        SqlCommand insertPurchaseOrderCommand =   
        new SqlCommand(  
        "insert into PurchaseOrders(poNumber, customerId)   
                               values(@poNumber, @customerId)");  
        insertPurchaseOrderCommand.Parameters.Add("@poNumber",   
                                           SqlDbType.VarChar, 50);  
        insertPurchaseOrderCommand.Parameters.Add("@customerId",   
                                         SqlDbType.VarChar, 50);  
  
        // Insert product line item.  
        SqlCommand insertProductLineItemCommand =   
             new SqlCommand("insert into ProductLineItems(productId,   
                    unitCost, quantity, poNumber) values(@productId,   
                    @unitCost, @quantity, @poNumber)");  
        insertProductLineItemCommand.Parameters.Add("@productId",   
                                           SqlDbType.VarChar, 50);  
        insertProductLineItemCommand.Parameters.Add("@unitCost",   
                                                  SqlDbType.Float);  
        insertProductLineItemCommand.Parameters.Add("@quantity",   
                                                     SqlDbType.Int);  
        insertProductLineItemCommand.Parameters.Add("@poNumber",   
                                           SqlDbType.VarChar, 50);  
        int rowsAffected = 0;  
        using (TransactionScope scope =   
              new TransactionScope(TransactionScopeOption.Required))  
        {  
             using (SqlConnection conn = new   
                 SqlConnection(  
                 ConfigurationManager.AppSettings["connectionString"]))  
             {  
                 conn.Open();  
  
                // Insert into purchase order table.  
               insertPurchaseOrderCommand.Connection = conn;  
               insertPurchaseOrderCommand.Parameters["@poNumber"].Value   
                                                       = po.PONumber;  
             insertPurchaseOrderCommand.Parameters["@customerId"].Value   
                                                    =po.CustomerId;  
             insertPurchaseOrderCommand.ExecuteNonQuery();  
  
            // Insert into product line item table.  
            insertProductLineItemCommand.Connection = conn;  
            foreach (PurchaseOrderLineItem orderLineItem in   
                                        po.orderLineItems) {  
            insertProductLineItemCommand.Parameters["@poNumber"].Value   
                                                          =po.PONumber;  
            insertProductLineItemCommand.Parameters["@productId"].Value   
                                             = orderLineItem.ProductId;  
            insertProductLineItemCommand.Parameters["@unitCost"].Value   
                                             = orderLineItem.UnitCost;  
            insertProductLineItemCommand.Parameters["@quantity"].Value   
                                             = orderLineItem.Quantity;  
            rowsAffected +=   
            insertProductLineItemCommand.ExecuteNonQuery();  
            }  
            scope.Complete();  
        }  
     }  
     Console.WriteLine(  
     "Updated database with {0} product line items  for purchase order   
                                     {1} ", rowsAffected, po.PONumber);  
    }  
}  
```  
  
 <span data-ttu-id="27d2e-176">批处理行为及其配置在服务应用程序配置中指定。</span><span class="sxs-lookup"><span data-stu-id="27d2e-176">The batching behavior and its configuration are specified in the service application configuration.</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8" ?>  
<configuration>  
  <appSettings>  
    <!-- Use appSetting to configure MSMQ queue name. -->  
    <add key="queueName"   
     value=".\private$\ServiceModelSamplesTransactedBatching" />  
    <add key="baseAddress"   
     value=  
     "http://localhost:8000/orderProcessor/transactedBatchingSample"/>  
    <add key="connectionString" value="Data Source=.\SQLEXPRESS;AttachDbFilename=|DataDirectory|orders.mdf;Integrated Security=True;User Instance=True;" />  
  </appSettings>  
  
  <system.serviceModel>  
    <behaviors>  
      <serviceBehaviors>  
        <behavior name="ThrottlingBehavior">  
          <serviceThrottling maxConcurrentCalls="5"/>  
        </behavior>  
      </serviceBehaviors>  
  
      <endpointBehaviors>  
        <behavior name="BatchingBehavior">  
          <transactedBatching maxBatchSize="100"/>  
        </behavior>  
      </endpointBehaviors>  
    </behaviors>  
    <services>  
      <service   
          behaviorConfiguration="ThrottlingBehavior"   
          name="Microsoft.ServiceModel.Samples.OrderProcessorService">  
        <!-- Define NetMsmqEndpoint -->  
        <endpoint address=  
"net.msmq://localhost/private/ServiceModelSamplesTransactedBatching"  
                  binding="netMsmqBinding"  
                  behaviorConfiguration="BatchingBehavior"   
                  contract=  
                    "Microsoft.ServiceModel.Samples.IOrderProcessor" />  
      </service>  
    </services>  
  </system.serviceModel>  
</configuration>  
```  
  
> [!NOTE]
>  <span data-ttu-id="27d2e-177">批次大小是一种系统提示。</span><span class="sxs-lookup"><span data-stu-id="27d2e-177">The batch size is a hint to the system.</span></span> <span data-ttu-id="27d2e-178">例如，如果将批次大小指定为 20，则会使用单个事务读取和调度 20 条消息，然后提交事务。</span><span class="sxs-lookup"><span data-stu-id="27d2e-178">For example, if you specify a batch size of 20, then 20 messages would be read and dispatched using a single transaction and then the transaction is committed.</span></span> <span data-ttu-id="27d2e-179">但在有些情况下可能会在达到批次大小之前提交事务。</span><span class="sxs-lookup"><span data-stu-id="27d2e-179">But there are cases where the transaction may commit the batch before the batch size is reached.</span></span>  
>   
>  <span data-ttu-id="27d2e-180">每个事务都有一个与之关联的超时，事务创建后，超时就开始计时。</span><span class="sxs-lookup"><span data-stu-id="27d2e-180">Associated with every transaction is a timeout that starts ticking once the transaction is created.</span></span> <span data-ttu-id="27d2e-181">当此超时过期时，事务就会中止。</span><span class="sxs-lookup"><span data-stu-id="27d2e-181">When this timeout expires the transaction is aborted.</span></span> <span data-ttu-id="27d2e-182">在达到批次大小之前，此超时有可能过期。</span><span class="sxs-lookup"><span data-stu-id="27d2e-182">It is possible for this timeout to expire even before the batch size is reached.</span></span> <span data-ttu-id="27d2e-183">为了避免因中止而重新执行该批次，`TransactedBatchingBehavior` 会检查事务上剩余多少时间。</span><span class="sxs-lookup"><span data-stu-id="27d2e-183">To avoid re-working the batch because of the abort, the `TransactedBatchingBehavior` checks to see how much time is left on the transaction.</span></span> <span data-ttu-id="27d2e-184">如果已经用完事务超时的 80%，则会提交事务。</span><span class="sxs-lookup"><span data-stu-id="27d2e-184">If 80% of the transaction timeout is used up, then the transaction is committed.</span></span>  
>   
>  <span data-ttu-id="27d2e-185">如果队列中已没有其他消息，则 <xref:System.ServiceModel.Description.TransactedBatchingBehavior> 将会提交事务而不等待达到批次大小。</span><span class="sxs-lookup"><span data-stu-id="27d2e-185">If there are no more messages in the queue then instead of waiting for the fulfillment of the batch size the <xref:System.ServiceModel.Description.TransactedBatchingBehavior> commits the transaction.</span></span>  
>   
>  <span data-ttu-id="27d2e-186">批次大小的选择取决于应用程序。</span><span class="sxs-lookup"><span data-stu-id="27d2e-186">The choice of the batch size is dependent on your application.</span></span> <span data-ttu-id="27d2e-187">如果批次大小过小，则可能无法获得所需的性能。</span><span class="sxs-lookup"><span data-stu-id="27d2e-187">If the batch size is too small, you may not get the desired performance.</span></span> <span data-ttu-id="27d2e-188">另一方面，如果批次大小过大，则可能会使性能下降。</span><span class="sxs-lookup"><span data-stu-id="27d2e-188">On the other hand if the batch size is too big, it may deteriorate performance.</span></span> <span data-ttu-id="27d2e-189">例如，事务的生存期可能较长并对数据库保持锁定，或者事务可能会变为死锁状态，这会导致批处理回滚并重做工作。</span><span class="sxs-lookup"><span data-stu-id="27d2e-189">For example, your transaction could live longer and hold locks on your database or your transaction could become dead locked, which could cause the batch to get rolled back and to redo the work.</span></span>  
  
 <span data-ttu-id="27d2e-190">客户端创建事务范围。</span><span class="sxs-lookup"><span data-stu-id="27d2e-190">The client creates a transaction scope.</span></span> <span data-ttu-id="27d2e-191">与队列的通信发生在事务范围之内，从而可将该事务范围视为原子单元，其中所有消息均将发送到队列或者没有任何消息发送到队列。</span><span class="sxs-lookup"><span data-stu-id="27d2e-191">Communication with the queue takes place within the scope of the transaction, causing it to be treated as an atomic unit where all messages are sent to the queue or none of the messages are sent to the queue.</span></span> <span data-ttu-id="27d2e-192">通过在事务范围上调用 <xref:System.Transactions.TransactionScope.Complete%2A> 可以提交事务。</span><span class="sxs-lookup"><span data-stu-id="27d2e-192">The transaction is committed by calling <xref:System.Transactions.TransactionScope.Complete%2A> on the transaction scope.</span></span>  
  
```  
//Client implementation code.  
class Client  
{  
    static void Main()  
    {  
        Random randomGen = new Random();  
        for (int i = 0; i < 2500; i++)  
        {  
            // Create a client with given client endpoint configuration.  
            OrderProcessorClient client = new OrderProcessorClient("OrderProcessorEndpoint");  
  
            // Create the purchase order.  
            PurchaseOrder po = new PurchaseOrder();  
            po.CustomerId = "somecustomer" + i + ".com";  
            po.PONumber = Guid.NewGuid().ToString();  
  
            PurchaseOrderLineItem lineItem1 = new PurchaseOrderLineItem();  
            lineItem1.ProductId = "Blue Widget";  
            lineItem1.Quantity = randomGen.Next(1, 100);  
            lineItem1.UnitCost = (float)randomGen.NextDouble() * 10;  
  
            PurchaseOrderLineItem lineItem2 = new PurchaseOrderLineItem();  
            lineItem2.ProductId = "Red Widget";  
            lineItem2.Quantity = 890;  
            lineItem2.UnitCost = 45.89F;  
  
            po.orderLineItems = new PurchaseOrderLineItem[2];  
            po.orderLineItems[0] = lineItem1;  
            po.orderLineItems[1] = lineItem2;  
  
            //Create a transaction scope.  
            using (TransactionScope scope = new TransactionScope(TransactionScopeOption.Required))  
            {  
                // Make a queued call to submit the purchase order.  
                client.SubmitPurchaseOrder(po);  
                // Complete the transaction.  
                scope.Complete();  
            }  
  
            client.Close();  
        }  
        Console.WriteLine();  
        Console.WriteLine("Press <ENTER> to terminate client.");  
        Console.ReadLine();  
    }  
}  
```  
  
 <span data-ttu-id="27d2e-193">运行示例时，客户端和服务活动将显示在服务和客户端控制台窗口中。</span><span class="sxs-lookup"><span data-stu-id="27d2e-193">When you run the sample, the client and service activities are displayed in both the service and client console windows.</span></span> <span data-ttu-id="27d2e-194">您可以看到服务从客户端接收消息。</span><span class="sxs-lookup"><span data-stu-id="27d2e-194">You can see the service receive messages from the client.</span></span> <span data-ttu-id="27d2e-195">在每个控制台窗口中按 Enter 可以关闭服务和客户端。</span><span class="sxs-lookup"><span data-stu-id="27d2e-195">Press ENTER in each console window to shut down the service and client.</span></span> <span data-ttu-id="27d2e-196">请注意：由于正在使用队列，因此不必同时启动和运行客户端和服务。</span><span class="sxs-lookup"><span data-stu-id="27d2e-196">Note that because queuing is in use, the client and service do not have to be up and running at the same time.</span></span> <span data-ttu-id="27d2e-197">可以先运行客户端，再将其关闭，然后启动服务，这样服务仍然会收到客户端的消息。</span><span class="sxs-lookup"><span data-stu-id="27d2e-197">You can run the client, shut it down, and then start up the service and it still receives its messages.</span></span> <span data-ttu-id="27d2e-198">在批次中读取和处理消息时，可以看到滚动输出。</span><span class="sxs-lookup"><span data-stu-id="27d2e-198">You can see a rolling output as messages are read in a batch and processed.</span></span>  
  
```  
The service is ready.  
Press <ENTER> to terminate service.  
  
Updated database with 2 product line items for purchase order 493ac832-d216-4e94-b2a5-d7f492fb5e39  
Processing Purchase Order: 8b567f5b-0661-4662-aae2-6cef1bd6d278  
        Customer: somecustomer849.com  
        OrderDetails  
               Order LineItem: 80 of Blue Widget @unit price: $9.751623  
               Order LineItem: 890 of Red Widget @unit price: $45.89  
        Total cost of this order: $41622.23  
        Order status: Pending  
  
Updated database with 2 product line items for purchase order 41130b95-4ea8-40a9-91c3-2e129117fcb8  
Processing Purchase Order: 5ce2699d-9a31-4cc2-a8c5-64cda614b3c7  
        Customer: somecustomer850.com  
        OrderDetails  
               Order LineItem: 89 of Blue Widget @unit price: $6.369128  
               Order LineItem: 890 of Red Widget @unit price: $45.89  
        Total cost of this order: $41408.95  
        Order status: Pending  
  
Updated database with 2 product line items for purchase order 8b567f5b-0661-4662-aae2-6cef1bd6d278  
Processing Purchase Order: ea94486b-7c86-4309-a42d-2f06c00656cd  
        Customer: somecustomer851.com  
        OrderDetails  
             Order LineItem: 47 of Blue Widget @unit price: $0.9391424  
             Order LineItem: 890 of Red Widget @unit price: $45.89  
        Total cost of this order: $40886.24  
        Order status: Pending  
```  
  
> [!IMPORTANT]
>  <span data-ttu-id="27d2e-199">您的计算机上可能已安装这些示例。</span><span class="sxs-lookup"><span data-stu-id="27d2e-199">The samples may already be installed on your computer.</span></span> <span data-ttu-id="27d2e-200">在继续操作之前，请先检查以下（默认）目录：</span><span class="sxs-lookup"><span data-stu-id="27d2e-200">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="27d2e-201">如果此目录不存在，请访问 [针对 .NET Framework 4 的 Windows Communication Foundation (WCF) 和 Windows Workflow Foundation (WF) 示例](http://go.microsoft.com/fwlink/?LinkId=150780) 以下载所有 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 和 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 示例。</span><span class="sxs-lookup"><span data-stu-id="27d2e-201">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="27d2e-202">此示例位于以下目录：</span><span class="sxs-lookup"><span data-stu-id="27d2e-202">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Binding\Net\MSMQ\Batching`  
  
## <a name="see-also"></a><span data-ttu-id="27d2e-203">另请参阅</span><span class="sxs-lookup"><span data-stu-id="27d2e-203">See Also</span></span>
