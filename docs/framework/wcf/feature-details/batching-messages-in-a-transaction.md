---
title: "在事务中对消息进行批处理"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: batching messages [WCF]
ms.assetid: 53305392-e82e-4e89-aedc-3efb6ebcd28c
caps.latest.revision: "19"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 2aa633d2e89612549d1dbe6703e80f4a5e713bf0
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="batching-messages-in-a-transaction"></a><span data-ttu-id="088b0-102">在事务中对消息进行批处理</span><span class="sxs-lookup"><span data-stu-id="088b0-102">Batching Messages in a Transaction</span></span>
<span data-ttu-id="088b0-103">排队的应用程序使用事务来确保消息的正确性以及传递的可靠性。</span><span class="sxs-lookup"><span data-stu-id="088b0-103">Queued applications use transactions to ensure correctness and reliable delivery of messages.</span></span> <span data-ttu-id="088b0-104">但是，事务是一种成本较高的操作，可能会大幅度降低消息吞吐量。</span><span class="sxs-lookup"><span data-stu-id="088b0-104">Transactions, however, are expensive operations and can dramatically reduce message throughput.</span></span> <span data-ttu-id="088b0-105">提高消息吞吐量的一个方法是让一个应用程序在单个事务内读取和处理多个消息。</span><span class="sxs-lookup"><span data-stu-id="088b0-105">One way to improve message throughput is to have an application read and process multiple messages within a single transaction.</span></span> <span data-ttu-id="088b0-106">这需要在性能和恢复之间进行权衡；随着批处理中消息数量的增加，事务回滚时所需完成的恢复工作的工作量也会增加。</span><span class="sxs-lookup"><span data-stu-id="088b0-106">The trade-off is between performance and recovery: as the number of messages in a batch increases, so does the amount of recovery work that required if transactions are rolled back.</span></span> <span data-ttu-id="088b0-107">需要注意的是，在事务中对消息进行批处理与会话是不同的。</span><span class="sxs-lookup"><span data-stu-id="088b0-107">It is important to note the difference between batching messages in a transaction and sessions.</span></span> <span data-ttu-id="088b0-108">A*会话*是一组相关的消息由单个应用程序处理并作为一个单元提交消息。</span><span class="sxs-lookup"><span data-stu-id="088b0-108">A *session* is a grouping of related messages that are processed by a single application and committed as a single unit.</span></span> <span data-ttu-id="088b0-109">当必须将一组相关消息一起进行处理的时候，通常使用会话。</span><span class="sxs-lookup"><span data-stu-id="088b0-109">Sessions are generally used when a group of related messages must be processed together.</span></span> <span data-ttu-id="088b0-110">这方面的一个例子是在线购物网站。</span><span class="sxs-lookup"><span data-stu-id="088b0-110">An example of this is an online shopping Web site.</span></span> <span data-ttu-id="088b0-111">*批处理*用于处理多个、 不相关的消息以增加消息吞吐量的方式。</span><span class="sxs-lookup"><span data-stu-id="088b0-111">*Batches* are used to process multiple, unrelated messages in a way that increases message throughput.</span></span> [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="088b0-112">会话，请参阅[分组会话中的排队消息](../../../../docs/framework/wcf/feature-details/grouping-queued-messages-in-a-session.md)。</span><span class="sxs-lookup"><span data-stu-id="088b0-112"> sessions, see [Grouping Queued Messages in a Session](../../../../docs/framework/wcf/feature-details/grouping-queued-messages-in-a-session.md).</span></span> <span data-ttu-id="088b0-113">批处理中的消息也是由单个应用程序处理，并且作为一个单元提交，但批处理中的消息之间可能没有任何关系。</span><span class="sxs-lookup"><span data-stu-id="088b0-113">Messages in a batch are also processed by a single application and committed as a single unit, but there may be no relationship between the messages in the batch.</span></span> <span data-ttu-id="088b0-114">在事务中对消息进行批处理是一种优化方法，它不会改变应用程序的运行方式。</span><span class="sxs-lookup"><span data-stu-id="088b0-114">Batching messages in a transaction is an optimization that does not change how the application runs.</span></span>  
  
## <a name="entering-batching-mode"></a><span data-ttu-id="088b0-115">进入批处理模式</span><span class="sxs-lookup"><span data-stu-id="088b0-115">Entering Batching Mode</span></span>  
 <span data-ttu-id="088b0-116"><xref:System.ServiceModel.Description.TransactedBatchingBehavior> 终结点行为对批处理进行控制。</span><span class="sxs-lookup"><span data-stu-id="088b0-116">The <xref:System.ServiceModel.Description.TransactedBatchingBehavior> endpoint behavior controls batching.</span></span> <span data-ttu-id="088b0-117">将此终结点行为添加到服务终结点会通知 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 在事务中对消息进行批处理。</span><span class="sxs-lookup"><span data-stu-id="088b0-117">Adding this endpoint behavior to a service endpoint tells [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] to batch messages in a transaction.</span></span> <span data-ttu-id="088b0-118">并非所有消息都需要事务，因此只都需要一个事务的消息放到批处理中，并且唯一的消息操作所发送的标有`TransactionScopeRequired`  =  `true`和`TransactionAutoComplete`  =  `true`是被视为一批。</span><span class="sxs-lookup"><span data-stu-id="088b0-118">Not all messages require a transaction, so only messages that require a transaction are placed in a batch, and only messages sent from operations marked with `TransactionScopeRequired` = `true` and `TransactionAutoComplete` = `true` are considered for a batch.</span></span> <span data-ttu-id="088b0-119">如果服务协定上的所有操作将都标有`TransactionScopeRequired`  =  `false`和`TransactionAutoComplete`  =  `false`，则永远不会进入批处理模式。</span><span class="sxs-lookup"><span data-stu-id="088b0-119">If all operations on the service contract are marked with `TransactionScopeRequired` = `false` and `TransactionAutoComplete` = `false`, then batching mode is never entered.</span></span>  
  
## <a name="committing-a-transaction"></a><span data-ttu-id="088b0-120">提交事务</span><span class="sxs-lookup"><span data-stu-id="088b0-120">Committing a Transaction</span></span>  
 <span data-ttu-id="088b0-121">根据以下因素提交批处理事务：</span><span class="sxs-lookup"><span data-stu-id="088b0-121">A batched transaction is committed based on the following:</span></span>  
  
-   <span data-ttu-id="088b0-122">`MaxBatchSize`。</span><span class="sxs-lookup"><span data-stu-id="088b0-122">`MaxBatchSize`.</span></span> <span data-ttu-id="088b0-123"><xref:System.ServiceModel.Description.TransactedBatchingBehavior> 行为的一个属性。</span><span class="sxs-lookup"><span data-stu-id="088b0-123">A property of the <xref:System.ServiceModel.Description.TransactedBatchingBehavior> behavior.</span></span> <span data-ttu-id="088b0-124">此属性确定放入批处理中的消息的最大数量。</span><span class="sxs-lookup"><span data-stu-id="088b0-124">This property determines the maximum number of messages that are placed into a batch.</span></span> <span data-ttu-id="088b0-125">一旦达到此数量，批处理便会被提交。</span><span class="sxs-lookup"><span data-stu-id="088b0-125">When this number is reached, the batch is committed.</span></span> <span data-ttu-id="088b0-126">该值并不是一个严格的限制，在接收到这一数量的消息之前也可以提交批处理。</span><span class="sxs-lookup"><span data-stu-id="088b0-126">This is value is not a strict limit, it is possible to commit a batch before receiving this number of messages.</span></span>  
  
-   <span data-ttu-id="088b0-127">`Transaction Timeout`。</span><span class="sxs-lookup"><span data-stu-id="088b0-127">`Transaction Timeout`.</span></span> <span data-ttu-id="088b0-128">当事务的超时时间已经过去 80% 之后，系统会提交批处理，并且创建一个新的批处理。</span><span class="sxs-lookup"><span data-stu-id="088b0-128">After 80 percent of the transaction's time-out has elapsed, the batch is committed and a new batch is created.</span></span> <span data-ttu-id="088b0-129">这表示如果为事务完成所分配的时间只剩下 20% 或更少，系统便会提交批处理。</span><span class="sxs-lookup"><span data-stu-id="088b0-129">This means that if 20 percent or less of the time given for a transaction to complete remains, the batch is committed.</span></span>  
  
-   <span data-ttu-id="088b0-130">`TransactionScopeRequired`。</span><span class="sxs-lookup"><span data-stu-id="088b0-130">`TransactionScopeRequired`.</span></span> <span data-ttu-id="088b0-131">当处理一批消息，如果[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]发现一个带有`TransactionScopeRequired`  =  `false`，它提交批处理，并重新打开一个新的批处理，在使用第一条消息的接收`TransactionScopeRequired`  =  `true`和`TransactionAutoComplete` = `true`.</span><span class="sxs-lookup"><span data-stu-id="088b0-131">When processing a batch of messages, if [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] finds one that has `TransactionScopeRequired` = `false`, it commits the batch and reopens a new batch on receipt of the first message with `TransactionScopeRequired` = `true` and `TransactionAutoComplete` = `true`.</span></span>  
  
-   <span data-ttu-id="088b0-132">如果队列中不再有其他消息，则即使尚未达到 `MaxBatchSize` 或事务的超时时间尚未过去 80%，系统也会提交当前的批处理。</span><span class="sxs-lookup"><span data-stu-id="088b0-132">If no more messages exist in the queue, then the current batch is committed, even if the `MaxBatchSize` has not been reached or 80 percent of the transaction's time-out has not elapsed.</span></span>  
  
## <a name="leaving-batching-mode"></a><span data-ttu-id="088b0-133">离开批处理模式</span><span class="sxs-lookup"><span data-stu-id="088b0-133">Leaving Batching Mode</span></span>  
 <span data-ttu-id="088b0-134">如果批处理中的消息导致事务中止，则会执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="088b0-134">If a message in a batch causes the transaction to abort, the following steps occur:</span></span>  
  
1.  <span data-ttu-id="088b0-135">回滚整个消息批处理。</span><span class="sxs-lookup"><span data-stu-id="088b0-135">The entire batch of messages is rolled back.</span></span>  
  
2.  <span data-ttu-id="088b0-136">一次只读取一个消息，直到所读取的消息数量超过最大批次大小的两倍为止。</span><span class="sxs-lookup"><span data-stu-id="088b0-136">Messages are read one at a time until the number of messages read exceeds twice the maximum batch size.</span></span>  
  
3.  <span data-ttu-id="088b0-137">重新进入批处理模式。</span><span class="sxs-lookup"><span data-stu-id="088b0-137">Batch mode is re-entered.</span></span>  
  
## <a name="choosing-the-batch-size"></a><span data-ttu-id="088b0-138">选择批次大小</span><span class="sxs-lookup"><span data-stu-id="088b0-138">Choosing the Batch Size</span></span>  
 <span data-ttu-id="088b0-139">批次大小依应用程序而定。</span><span class="sxs-lookup"><span data-stu-id="088b0-139">The size of a batch is application-dependent.</span></span> <span data-ttu-id="088b0-140">经验性方法是达到应用程序的最佳批次大小的最好方式。</span><span class="sxs-lookup"><span data-stu-id="088b0-140">The empirical method is the best way to arrive at an optimal batch size for the application.</span></span> <span data-ttu-id="088b0-141">请一定牢记，在选择批次大小时，要根据应用程序的实际部署模型来选择大小。</span><span class="sxs-lookup"><span data-stu-id="088b0-141">It is important to remember when choosing a batch size to choose the size according to your application's actual deployment model.</span></span> <span data-ttu-id="088b0-142">例如，在部署应用程序时，如果需要位于远程计算机上的 SQL Server 以及一个横跨队列和该 SQL Server 的事务，则最好通过运行此确切配置来确定批次大小。</span><span class="sxs-lookup"><span data-stu-id="088b0-142">For example, when deploying the application, if you need an SQL server on a remote machine and a transaction that spans the queue and the SQL server, then the batch size is best determined by running this exact configuration.</span></span>  
  
## <a name="concurrency-and-batching"></a><span data-ttu-id="088b0-143">并发和批处理</span><span class="sxs-lookup"><span data-stu-id="088b0-143">Concurrency and Batching</span></span>  
 <span data-ttu-id="088b0-144">若要增加吞吐量，还可以同时运行多个批处理。</span><span class="sxs-lookup"><span data-stu-id="088b0-144">To increase throughput, you can also have many batches run concurrently.</span></span> <span data-ttu-id="088b0-145">通过设置 `ConcurrencyMode.Multiple` 中的 `ServiceBehaviorAttribute` 可以启用并发批处理。</span><span class="sxs-lookup"><span data-stu-id="088b0-145">By setting `ConcurrencyMode.Multiple` in `ServiceBehaviorAttribute`, you enable concurrent batching.</span></span>  
  
 <span data-ttu-id="088b0-146">*服务遏制*是一种服务行为，用于指示可以对该服务发出多少的最大并发调用。</span><span class="sxs-lookup"><span data-stu-id="088b0-146">*Service throttling* is a service behavior that is used to indicate how many maximum concurrent calls can be made on the service.</span></span> <span data-ttu-id="088b0-147">在将其与批处理结合使用时，可以将其解释为可以运行的并发批处理的数量。</span><span class="sxs-lookup"><span data-stu-id="088b0-147">When used with batching, this is interpreted as how many concurrent batches can be run.</span></span> <span data-ttu-id="088b0-148">如果未设置服务遏制，则 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 将最大并发调用数量默认为 16。</span><span class="sxs-lookup"><span data-stu-id="088b0-148">If the service throttling is not set, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] defaults the maximum concurrent calls to 16.</span></span> <span data-ttu-id="088b0-149">因此，如果在默认情况下添加批处理行为，则最多会有 16 个批处理同时处于活动状态。</span><span class="sxs-lookup"><span data-stu-id="088b0-149">Thus, if batching behavior were added by default, a maximum of 16 batches can be active at the same time.</span></span> <span data-ttu-id="088b0-150">最好根据系统处理能力来调整服务遏制和批处理。</span><span class="sxs-lookup"><span data-stu-id="088b0-150">It is best to tune the service throttling and batching based on your capacity.</span></span> <span data-ttu-id="088b0-151">例如，如果队列中有 100 个消息并且将批次大小设置为 20 是比较理想的，那么将最大并发调用数设置为 16 是没有用处的，因为根据吞吐量，可能有 16 个事务处于活动状态，这与未启用批处理的结果类似。</span><span class="sxs-lookup"><span data-stu-id="088b0-151">For example, if the queue has 100 messages and a batch of 20 is desired, having the maximum concurrent calls set to 16 is not useful because, depending on throughput, 16 transactions could be active, similar to not having batching turned on.</span></span> <span data-ttu-id="088b0-152">因此，在对这些设置进行微调以提高性能时，要么干脆不使用并发批处理，否则就要使并发批处理具有正确的服务遏制大小。</span><span class="sxs-lookup"><span data-stu-id="088b0-152">Therefore, when fine-tuning for performance, either do not have concurrent batching or have concurrent batching with the correct service throttle size.</span></span>  
  
## <a name="batching-and-multiple-endpoints"></a><span data-ttu-id="088b0-153">批处理和多个终结点</span><span class="sxs-lookup"><span data-stu-id="088b0-153">Batching and Multiple Endpoints</span></span>  
 <span data-ttu-id="088b0-154">终结点由地址和协定组成。</span><span class="sxs-lookup"><span data-stu-id="088b0-154">An endpoint is composed of an address and a contract.</span></span> <span data-ttu-id="088b0-155">可能有多个终结点共享同一个绑定。</span><span class="sxs-lookup"><span data-stu-id="088b0-155">There may be multiple endpoints that share the same binding.</span></span> <span data-ttu-id="088b0-156">两个终结点可以共享同一个绑定，并侦听统一资源标识符 (URI)，即队列地址。</span><span class="sxs-lookup"><span data-stu-id="088b0-156">It is possible for two endpoints to share the same binding and listen Uniform Resource Identifier (URI), or queue address.</span></span> <span data-ttu-id="088b0-157">如果两个终结点从同一个队列中进行读取，并且两个终结点都添加了事务处理批处理行为，则指定的批次大小可能会发生冲突。</span><span class="sxs-lookup"><span data-stu-id="088b0-157">If two endpoints are reading from the same queue, and transacted batching behavior is added to both endpoints, a conflict in the batch sizes specified could arise.</span></span> <span data-ttu-id="088b0-158">使用在两个事务处理批处理行为之间指定的最小批次大小来实现批处理，可以解决该冲突。</span><span class="sxs-lookup"><span data-stu-id="088b0-158">This is resolved by implementing batching using the minimal batch size specified between the two transacted batching behaviors.</span></span> <span data-ttu-id="088b0-159">在此方案中，如果其中一个终结点未指定事务处理批处理，则两个终结点都不会使用批处理。</span><span class="sxs-lookup"><span data-stu-id="088b0-159">In this scenario, if one of the endpoints does not specify transacted batching, then both endpoints would not use batching.</span></span>  
  
## <a name="example"></a><span data-ttu-id="088b0-160">示例</span><span class="sxs-lookup"><span data-stu-id="088b0-160">Example</span></span>  
 <span data-ttu-id="088b0-161">下面的示例演示如何在配置文件中指定 `TransactedBatchingBehavior`。</span><span class="sxs-lookup"><span data-stu-id="088b0-161">The following example shows how to specify the `TransactedBatchingBehavior` in a configuration file.</span></span>  
  
```xml  
<behaviors>
  <endpointBehaviors>
    <behavior name="TransactedBatchingBehavior"
              maxBatchSize="100" />
  </endpointBehaviors>
</behaviors>
```  
  
 <span data-ttu-id="088b0-162">下面的示例演示如何在代码中指定 <xref:System.ServiceModel.Description.TransactedBatchingBehavior>。</span><span class="sxs-lookup"><span data-stu-id="088b0-162">The following example shows how to specify the <xref:System.ServiceModel.Description.TransactedBatchingBehavior> in code.</span></span>  
  
```csharp
using (ServiceHost serviceHost = new ServiceHost(typeof(OrderProcessorService)))
{
     ServiceEndpoint sep = ServiceHost.AddServiceEndpoint(typeof(IOrderProcessor), new NetMsmqBinding(), "net.msmq://localhost/private/ServiceModelSamplesTransacted");
     sep.Behaviors.Add(new TransactedBatchingBehavior(100));
     
     // Open the ServiceHost to create listeners and start listening for messages.
    serviceHost.Open();
  
    // The service can now be accessed.
    Console.WriteLine("The service is ready.");
    Console.WriteLine("Press <ENTER> to terminate service.");
    Console.WriteLine();
    Console.ReadLine();
  
    // Close the ServiceHostB to shut down the service.
    serviceHost.Close();
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="088b0-163">另请参阅</span><span class="sxs-lookup"><span data-stu-id="088b0-163">See Also</span></span>  
 [<span data-ttu-id="088b0-164">队列概述</span><span class="sxs-lookup"><span data-stu-id="088b0-164">Queues Overview</span></span>](../../../../docs/framework/wcf/feature-details/queues-overview.md)  
 [<span data-ttu-id="088b0-165">在 WCF 中排队</span><span class="sxs-lookup"><span data-stu-id="088b0-165">Queuing in WCF</span></span>](../../../../docs/framework/wcf/feature-details/queuing-in-wcf.md)
