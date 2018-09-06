---
title: 如何：使用 WCF 终结点交换排队消息
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 938e7825-f63a-4c3d-b603-63772fabfdb3
ms.openlocfilehash: 185bcb64522115d0c60ae90ee22a73610139c8c3
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/06/2018
ms.locfileid: "43865590"
---
# <a name="how-to-exchange-queued-messages-with-wcf-endpoints"></a><span data-ttu-id="00b66-102">如何：使用 WCF 终结点交换排队消息</span><span class="sxs-lookup"><span data-stu-id="00b66-102">How to: Exchange Queued Messages with WCF Endpoints</span></span>
<span data-ttu-id="00b66-103">队列确保，可靠消息传递之间可能会出现在客户端和 Windows Communication Foundation (WCF) 服务，即使在通信时服务不可用。</span><span class="sxs-lookup"><span data-stu-id="00b66-103">Queues ensure that reliable messaging can occur between a client and a Windows Communication Foundation (WCF) service, even if the service is not available at the time of communication.</span></span> <span data-ttu-id="00b66-104">以下过程介绍如何确保实现 WCF 服务时，客户端和服务通过使用标准之间的持久性通信排队绑定。</span><span class="sxs-lookup"><span data-stu-id="00b66-104">The following procedures show how to ensure durable communication between a client and a service by using the standard queued binding when implementing the WCF service.</span></span>  
  
 <span data-ttu-id="00b66-105">本部分介绍如何使用<xref:System.ServiceModel.NetMsmqBinding>的 WCF 客户端和 WCF 服务之间的排队通信。</span><span class="sxs-lookup"><span data-stu-id="00b66-105">This section explains how to use <xref:System.ServiceModel.NetMsmqBinding> for queued communication between a WCF client and a WCF service.</span></span>  
  
### <a name="to-use-queuing-in-a-wcf-service"></a><span data-ttu-id="00b66-106">在 WCF 服务中使用队列</span><span class="sxs-lookup"><span data-stu-id="00b66-106">To use queuing in a WCF service</span></span>  
  
1.  <span data-ttu-id="00b66-107">使用用 <xref:System.ServiceModel.ServiceContractAttribute> 标记的接口定义服务协定。</span><span class="sxs-lookup"><span data-stu-id="00b66-107">Define a service contract using an interface marked with the <xref:System.ServiceModel.ServiceContractAttribute>.</span></span> <span data-ttu-id="00b66-108">用 <xref:System.ServiceModel.OperationContractAttribute> 来标记属于服务协定一部分的接口中的操作，并将它们指定为单向操作（因为不返回对该方法的任何响应）。</span><span class="sxs-lookup"><span data-stu-id="00b66-108">Mark the operations in the interface that are part of the service contract with the <xref:System.ServiceModel.OperationContractAttribute> and specify them as one-way because no response to the method is returned.</span></span> <span data-ttu-id="00b66-109">下面的代码提供了示例服务协定及其操作定义。</span><span class="sxs-lookup"><span data-stu-id="00b66-109">The following code provides an example service contract and its operation definition.</span></span>  
  
     [!code-csharp[S_Msmq_Transacted#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_msmq_transacted/cs/service.cs#1)]
     [!code-vb[S_Msmq_Transacted#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_msmq_transacted/vb/service.vb#1)]  
  
2.  <span data-ttu-id="00b66-110">当服务协定传递用户定义的类型时，您必须为这些类型定义数据协定。</span><span class="sxs-lookup"><span data-stu-id="00b66-110">When the service contract passes user-defined types, you must define data contracts for those types.</span></span> <span data-ttu-id="00b66-111">下面的代码演示了两个数据协定，`PurchaseOrder` 和 `PurchaseOrderLineItem`。</span><span class="sxs-lookup"><span data-stu-id="00b66-111">The following code shows two data contracts, `PurchaseOrder` and `PurchaseOrderLineItem`.</span></span> <span data-ttu-id="00b66-112">这两种类型定义了发送给服务的数据。</span><span class="sxs-lookup"><span data-stu-id="00b66-112">These two types define data that is sent to the service.</span></span> <span data-ttu-id="00b66-113">（请注意，定义该数据协定的类也定义了大量方法。</span><span class="sxs-lookup"><span data-stu-id="00b66-113">(Note that the classes that define this data contract also define a number of methods.</span></span> <span data-ttu-id="00b66-114">这些方法不被视为数据协定的一部分。</span><span class="sxs-lookup"><span data-stu-id="00b66-114">These methods are not considered part of the data contract.</span></span> <span data-ttu-id="00b66-115">只有那些使用 `DataMember` 属性声明的成员才是数据协定的一部分。）</span><span class="sxs-lookup"><span data-stu-id="00b66-115">Only those members that are declared with the `DataMember` attribute are part of the data contract.)</span></span>  
  
     [!code-csharp[S_Msmq_Transacted#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_msmq_transacted/cs/service.cs#2)]
     [!code-vb[S_Msmq_Transacted#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_msmq_transacted/vb/service.vb#2)]  
  
3.  <span data-ttu-id="00b66-116">实现在类中接口中定义的服务协定的方法。</span><span class="sxs-lookup"><span data-stu-id="00b66-116">Implement the methods of the service contract defined in the interface in a class.</span></span>  
  
     [!code-csharp[S_Msmq_Transacted#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_msmq_transacted/cs/service.cs#3)]
     [!code-vb[S_Msmq_Transacted#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_msmq_transacted/vb/service.vb#3)]  
  
     <span data-ttu-id="00b66-117">请注意放置在 <xref:System.ServiceModel.OperationBehaviorAttribute> 方法上的 `SubmitPurchaseOrder`。</span><span class="sxs-lookup"><span data-stu-id="00b66-117">Notice the <xref:System.ServiceModel.OperationBehaviorAttribute> placed on the `SubmitPurchaseOrder` method.</span></span> <span data-ttu-id="00b66-118">它指定了必须在某个事务内调用此操作，且当方法完成后，该事务会自动完成。</span><span class="sxs-lookup"><span data-stu-id="00b66-118">This specifies that this operation must be called within a transaction and that the transaction automatically completes when the method completes.</span></span>  
  
4.  <span data-ttu-id="00b66-119">使用 <xref:System.Messaging> 创建一个事务性队列。</span><span class="sxs-lookup"><span data-stu-id="00b66-119">Create a transactional queue using <xref:System.Messaging>.</span></span> <span data-ttu-id="00b66-120">可以选择使用 Microsoft 消息队列 (MSMQ) Microsoft 管理控制台 (MMC) 来创建队列。</span><span class="sxs-lookup"><span data-stu-id="00b66-120">You can choose to create the queue using Microsoft Message Queuing (MSMQ) Microsoft Management Console (MMC) instead.</span></span> <span data-ttu-id="00b66-121">如果这样，将确保创建事务性队列。</span><span class="sxs-lookup"><span data-stu-id="00b66-121">If so, make sure you create a transactional queue.</span></span>  
  
     [!code-csharp[S_Msmq_Transacted#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_msmq_transacted/cs/hostapp.cs#4)]
     [!code-vb[S_Msmq_Transacted#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_msmq_transacted/vb/hostapp.vb#4)]  
  
5.  <span data-ttu-id="00b66-122">在指定服务地址并使用标准 <xref:System.ServiceModel.Description.ServiceEndpoint> 绑定的配置中定义 <xref:System.ServiceModel.NetMsmqBinding>。</span><span class="sxs-lookup"><span data-stu-id="00b66-122">Define a <xref:System.ServiceModel.Description.ServiceEndpoint> in configuration that specifies the service address and uses the standard <xref:System.ServiceModel.NetMsmqBinding> binding.</span></span> <span data-ttu-id="00b66-123">有关使用 WCF 配置的详细信息，请参阅[配置 Windows Communication Foundation 应用程序](https://msdn.microsoft.com/library/13cb368e-88d4-4c61-8eed-2af0361c6d7a)。</span><span class="sxs-lookup"><span data-stu-id="00b66-123">For more information about using WCF configuration, see [Configuring Windows Communication Foundation Applications](https://msdn.microsoft.com/library/13cb368e-88d4-4c61-8eed-2af0361c6d7a).</span></span>  
  
  
  
6.  <span data-ttu-id="00b66-124">使用 `OrderProcessing` 为 <xref:System.ServiceModel.ServiceHost> 服务创建一个主机，该主机从队列读取消息并处理这些消息。</span><span class="sxs-lookup"><span data-stu-id="00b66-124">Create a host for the `OrderProcessing` service using <xref:System.ServiceModel.ServiceHost> that reads messages from the queue and processes them.</span></span> <span data-ttu-id="00b66-125">打开服务主机使服务处于可用状态。</span><span class="sxs-lookup"><span data-stu-id="00b66-125">Open the service host to make the service available.</span></span> <span data-ttu-id="00b66-126">显示一条消息，告知用户按任何键以终止服务。</span><span class="sxs-lookup"><span data-stu-id="00b66-126">Display a message that tells the user to press any key to terminate the service.</span></span> <span data-ttu-id="00b66-127">调用 `ReadLine` 等待按键，然后关闭服务。</span><span class="sxs-lookup"><span data-stu-id="00b66-127">Call `ReadLine` to wait for the key to be pressed and then close the service.</span></span>  
  
     [!code-csharp[S_Msmq_Transacted#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_msmq_transacted/cs/hostapp.cs#6)]
     [!code-vb[S_Msmq_Transacted#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_msmq_transacted/vb/hostapp.vb#6)]  
  
### <a name="to-create-a-client-for-the-queued-service"></a><span data-ttu-id="00b66-128">为排队服务创建客户端</span><span class="sxs-lookup"><span data-stu-id="00b66-128">To create a client for the queued service</span></span>  
  
1.  <span data-ttu-id="00b66-129">下面的示例演示如何运行托管应用程序并使用 Svcutil.exe 工具创建 WCF 客户端。</span><span class="sxs-lookup"><span data-stu-id="00b66-129">The following example shows how to run the hosting application and use the Svcutil.exe tool to create the WCF client.</span></span>  
  
    ```  
    svcutil http://localhost:8000/ServiceModelSamples/service  
    ```  
  
2.  <span data-ttu-id="00b66-130">在配置中定义 <xref:System.ServiceModel.Description.ServiceEndpoint>，指定地址并使用标准 <xref:System.ServiceModel.NetMsmqBinding> 绑定，如下面的示例所示。</span><span class="sxs-lookup"><span data-stu-id="00b66-130">Define a <xref:System.ServiceModel.Description.ServiceEndpoint> in configuration that specifies the address and uses the standard <xref:System.ServiceModel.NetMsmqBinding> binding, as shown in the following example.</span></span>  
  
  
  
3.  <span data-ttu-id="00b66-131">创建要写入事务性队列，调用的事务作用域`SubmitPurchaseOrder`操作并关闭 WCF 客户端，如下面的示例中所示。</span><span class="sxs-lookup"><span data-stu-id="00b66-131">Create a transaction scope to write to the transactional queue, call the `SubmitPurchaseOrder` operation and close the WCF client, as shown in the following example.</span></span>  
  
     [!code-csharp[S_Msmq_Transacted#8](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_msmq_transacted/cs/client.cs#8)]
     [!code-vb[S_Msmq_Transacted#8](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_msmq_transacted/vb/client.vb#8)]  
  
## <a name="example"></a><span data-ttu-id="00b66-132">示例</span><span class="sxs-lookup"><span data-stu-id="00b66-132">Example</span></span>  
 <span data-ttu-id="00b66-133">下面的示例演示了服务代码、主机应用程序、App.config 文件以及为此示例包含的客户端代码。</span><span class="sxs-lookup"><span data-stu-id="00b66-133">The following examples show the service code, hosting application, App.config file, and client code included for this example.</span></span>  
  
 [!code-csharp[S_Msmq_Transacted#9](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_msmq_transacted/cs/service.cs#9)]
 [!code-vb[S_Msmq_Transacted#9](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_msmq_transacted/vb/service.vb#9)]  
  
 [!code-csharp[S_Msmq_Transacted#10](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_msmq_transacted/cs/hostapp.cs#10)]
 [!code-vb[S_Msmq_Transacted#10](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_msmq_transacted/vb/hostapp.vb#10)]  
  
  
  
 [!code-csharp[S_Msmq_Transacted#12](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_msmq_transacted/cs/client.cs#12)]
 [!code-vb[S_Msmq_Transacted#12](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_msmq_transacted/vb/client.vb#12)]  
  
  
  
## <a name="see-also"></a><span data-ttu-id="00b66-134">请参阅</span><span class="sxs-lookup"><span data-stu-id="00b66-134">See Also</span></span>  
 <xref:System.ServiceModel.NetMsmqBinding>  
 [<span data-ttu-id="00b66-135">已进行事务处理的 MSMQ 绑定</span><span class="sxs-lookup"><span data-stu-id="00b66-135">Transacted MSMQ Binding</span></span>](../../../../docs/framework/wcf/samples/transacted-msmq-binding.md)  
 [<span data-ttu-id="00b66-136">在 WCF 中排队</span><span class="sxs-lookup"><span data-stu-id="00b66-136">Queuing in WCF</span></span>](../../../../docs/framework/wcf/feature-details/queuing-in-wcf.md)  
 [<span data-ttu-id="00b66-137">如何：与 WCF 终结点和消息队列应用程序交换消息</span><span class="sxs-lookup"><span data-stu-id="00b66-137">How to: Exchange Messages with WCF Endpoints and Message Queuing Applications</span></span>](../../../../docs/framework/wcf/feature-details/how-to-exchange-messages-with-wcf-endpoints-and-message-queuing-applications.md)  
 [<span data-ttu-id="00b66-138">Windows Communication Foundation 到消息队列</span><span class="sxs-lookup"><span data-stu-id="00b66-138">Windows Communication Foundation to Message Queuing</span></span>](../../../../docs/framework/wcf/samples/wcf-to-message-queuing.md)  
 [<span data-ttu-id="00b66-139">安装消息队列 (MSMQ)</span><span class="sxs-lookup"><span data-stu-id="00b66-139">Installing Message Queuing (MSMQ)</span></span>](../../../../docs/framework/wcf/samples/installing-message-queuing-msmq.md)  
 [<span data-ttu-id="00b66-140">消息队列集成绑定示例</span><span class="sxs-lookup"><span data-stu-id="00b66-140">Message Queuing Integration Binding Samples</span></span>](https://msdn.microsoft.com/library/997d11cb-f2c5-4ba0-9209-92843d4d0e1a)  
 [<span data-ttu-id="00b66-141">到 Windows Communication Foundation 的消息队列</span><span class="sxs-lookup"><span data-stu-id="00b66-141">Message Queuing to Windows Communication Foundation</span></span>](../../../../docs/framework/wcf/samples/message-queuing-to-wcf.md)  
 [<span data-ttu-id="00b66-142">基于消息队列的消息安全性</span><span class="sxs-lookup"><span data-stu-id="00b66-142">Message Security over Message Queuing</span></span>](../../../../docs/framework/wcf/samples/message-security-over-message-queuing.md)
