---
title: SRMP
ms.date: 03/30/2017
ms.assetid: cf37078c-dcb4-45e0-acaf-2f196521b226
ms.openlocfilehash: 736633733ab9c882c1d1520a5acf20c49324eeb3
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/02/2019
ms.locfileid: "58828017"
---
# <a name="srmp"></a><span data-ttu-id="70df7-102">SRMP</span><span class="sxs-lookup"><span data-stu-id="70df7-102">SRMP</span></span>
<span data-ttu-id="70df7-103">本示例演示如何使用 HTTP 上的消息队列 (MSMQ) 来执行事务处理排队通信。</span><span class="sxs-lookup"><span data-stu-id="70df7-103">This sample demonstrates how to perform transacted queued communication by using Message Queuing (MSMQ) over HTTP.</span></span>  
  
 <span data-ttu-id="70df7-104">在排队通信中，客户端使用队列与服务进行通信。</span><span class="sxs-lookup"><span data-stu-id="70df7-104">In queued communication, the client communicates to the service using a queue.</span></span> <span data-ttu-id="70df7-105">更确切地说，客户端向队列发送消息。</span><span class="sxs-lookup"><span data-stu-id="70df7-105">More precisely, the client sends messages to a queue.</span></span> <span data-ttu-id="70df7-106">服务从队列接收消息。</span><span class="sxs-lookup"><span data-stu-id="70df7-106">The service receives messages from the queue.</span></span> <span data-ttu-id="70df7-107">因此不必同时运行服务和客户端便可使用队列进行通信。</span><span class="sxs-lookup"><span data-stu-id="70df7-107">The service and client therefore, do not have to be running at the same time to communicate using a queue.</span></span>  
  
 <span data-ttu-id="70df7-108">MSMQ 启用 HTTP（包括启用 HTTPS）来向队列发送消息。</span><span class="sxs-lookup"><span data-stu-id="70df7-108">MSMQ enables the use of HTTP (including the use of HTTPS) to send messages to a queue.</span></span> <span data-ttu-id="70df7-109">在此示例中，我们将演示使用 Windows Communication Foundation (WCF) 排队通信，以及如何通过 HTTP 发送消息。</span><span class="sxs-lookup"><span data-stu-id="70df7-109">In this example, we demonstrate using Windows Communication Foundation (WCF) queued communication and how to send messages over HTTP.</span></span> <span data-ttu-id="70df7-110">MSMQ 使用一种称为 SRMP 的协议，此协议是一种用于通过 HTTP 进行通信的基于 SOAP 的协议。</span><span class="sxs-lookup"><span data-stu-id="70df7-110">MSMQ uses a protocol called SRMP, which is a SOAP-based protocol for communication over HTTP.</span></span>  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="70df7-111">设置、生成和运行示例</span><span class="sxs-lookup"><span data-stu-id="70df7-111">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="70df7-112">请确保您具有执行[的 Windows Communication Foundation 示例的一次性安装过程](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)。</span><span class="sxs-lookup"><span data-stu-id="70df7-112">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2.  <span data-ttu-id="70df7-113">若要生成 C# 或 Visual Basic .NET 版本的解决方案，请按照 [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)中的说明进行操作。</span><span class="sxs-lookup"><span data-stu-id="70df7-113">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3.  <span data-ttu-id="70df7-114">若要在单或跨计算机配置中运行示例，请按照中的说明[运行 Windows Communication Foundation 示例](../../../../docs/framework/wcf/samples/running-the-samples.md)。</span><span class="sxs-lookup"><span data-stu-id="70df7-114">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
4.  <span data-ttu-id="70df7-115">运行示例之前**添加/删除 Windows 组件**，确保安装了 MSMQ 和 HTTP 支持。</span><span class="sxs-lookup"><span data-stu-id="70df7-115">Before running the sample in **Add/Remove Windows Components**, ensure that MSMQ is installed with HTTP support.</span></span> <span data-ttu-id="70df7-116">安装 HTTP 支持时，会自动安装 Internet 信息服务 (IIS)，并会在 IIS 中添加对 MSMQ 的协议支持。</span><span class="sxs-lookup"><span data-stu-id="70df7-116">Installing HTTP support automatically installs Internet Information Services (IIS) and adds the protocol support in IIS for MSMQ.</span></span>  
  
5.  <span data-ttu-id="70df7-117">如果想要确保使用 HTTP 进行通信，则可以启用 MSMQ 以便在加强模式中运行。</span><span class="sxs-lookup"><span data-stu-id="70df7-117">If you want to be certain that HTTP is used for communication, you can enable MSMQ to run in hardened mode.</span></span> <span data-ttu-id="70df7-118">这可确保任何消息都不能使用任何非 HTTP 传输到达计算机上承载的任何队列。</span><span class="sxs-lookup"><span data-stu-id="70df7-118">This ensures that no messages to any queue hosted on the machine can arrive using any non-HTTP transport.</span></span>  
  
6.  <span data-ttu-id="70df7-119">选择 MSMQ 以在加强模式中运行后，如果系统为 [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)]，计算机需要重新启动。</span><span class="sxs-lookup"><span data-stu-id="70df7-119">After you have selected MSMQ to run in hardened mode, the machine requires a re-boot on [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)].</span></span>  
  
7.  <span data-ttu-id="70df7-120">运行服务。</span><span class="sxs-lookup"><span data-stu-id="70df7-120">Run the service.</span></span>  
  
8.  <span data-ttu-id="70df7-121">运行客户端。</span><span class="sxs-lookup"><span data-stu-id="70df7-121">Run the client.</span></span> <span data-ttu-id="70df7-122">确保将终结点地址更改为指向计算机名或 IP 地址而不是 localhost。</span><span class="sxs-lookup"><span data-stu-id="70df7-122">Ensure that you change the endpoint address to point to the machine name or IP address instead of localhost.</span></span> <span data-ttu-id="70df7-123">客户端将发送消息并退出。</span><span class="sxs-lookup"><span data-stu-id="70df7-123">The client sends a message and exits.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="70df7-124">要求</span><span class="sxs-lookup"><span data-stu-id="70df7-124">Requirements</span></span>  
 <span data-ttu-id="70df7-125">若要运行此示例，服务计算机和客户端计算机上除了 MSMQ 外，还必须安装 IIS。</span><span class="sxs-lookup"><span data-stu-id="70df7-125">To run this sample, IIS must be installed on both the service and the client machines in addition to MSMQ.</span></span>  
  
## <a name="demonstrates"></a><span data-ttu-id="70df7-126">演示</span><span class="sxs-lookup"><span data-stu-id="70df7-126">Demonstrates</span></span>  
 <span data-ttu-id="70df7-127">此示例演示如何将 WCF 发送排队消息通过 HTTP 使用 MSMQ。</span><span class="sxs-lookup"><span data-stu-id="70df7-127">The sample demonstrates sending WCF queued messages using MSMQ over HTTP.</span></span> <span data-ttu-id="70df7-128">这也称为 SRMP 消息传递。</span><span class="sxs-lookup"><span data-stu-id="70df7-128">This is also called SRMP messaging.</span></span> <span data-ttu-id="70df7-129">发送排队消息时，发送方计算机上的 MSMQ 通过 TCP 或 HTTP 传输将消息传送到接收队列管理器。</span><span class="sxs-lookup"><span data-stu-id="70df7-129">When a queued message is sent, MSMQ on the sending machine transfers the messages to the receiving queue manager over TCP or HTTP transport.</span></span> <span data-ttu-id="70df7-130">通过选择 SRMP，用户可以指示选择 HTTP 作为队列传送的传输协议。</span><span class="sxs-lookup"><span data-stu-id="70df7-130">By choosing SRMP, the user indicates the choice of HTTP as a transport for queue transfer.</span></span> <span data-ttu-id="70df7-131">SRMP 安全启用 HTTPS。</span><span class="sxs-lookup"><span data-stu-id="70df7-131">SRMP Secure enables the use of HTTPS.</span></span>  
  
## <a name="example"></a><span data-ttu-id="70df7-132">示例</span><span class="sxs-lookup"><span data-stu-id="70df7-132">Example</span></span>  
 <span data-ttu-id="70df7-133">示例代码基于事务处理示例。</span><span class="sxs-lookup"><span data-stu-id="70df7-133">The sample code is based on the transacted sample.</span></span> <span data-ttu-id="70df7-134">使用 SRMP 将消息发送到队列和从队列中接收消息的方式与使用本机协议发送和接收消息的方式相同。</span><span class="sxs-lookup"><span data-stu-id="70df7-134">How you send a message to the queue and receive a message from the queue using SRMP is the same as sending and receiving messages using a Native protocol.</span></span>  
  
 <span data-ttu-id="70df7-135">客户端的配置将会发生更改以指示选择队列传输协议。</span><span class="sxs-lookup"><span data-stu-id="70df7-135">The configuration for the client is changed to indicate the choice of the queue transfer protocol.</span></span> <span data-ttu-id="70df7-136">队列传输协议可以是本机、SRMP 或 SrmpSecure 之一。</span><span class="sxs-lookup"><span data-stu-id="70df7-136">The queue transfer protocol can be one of Native, SRMP or SrmpSecure.</span></span> <span data-ttu-id="70df7-137">默认情况下，传输协议为“本机”。</span><span class="sxs-lookup"><span data-stu-id="70df7-137">By default, the transfer protocol is Native.</span></span> <span data-ttu-id="70df7-138">在此示例中，客户端和服务在配置中指定使用 SRMP。</span><span class="sxs-lookup"><span data-stu-id="70df7-138">The client and service specify in the configuration to use SRMP in this example.</span></span>  
  
 <span data-ttu-id="70df7-139">SRMP 存在与传输安全相关的限制。</span><span class="sxs-lookup"><span data-stu-id="70df7-139">There are limitations to SRMP in relation to transport security.</span></span> <span data-ttu-id="70df7-140">默认 MSMQ 传输安全需要使用 Active Directory，而 Active Directory 要求发送队列管理器和接收队列管理器位于同一个 Windows 域中。</span><span class="sxs-lookup"><span data-stu-id="70df7-140">The default MSMQ transport security requires Active Directory that requires that the sending queue manager and the receiving queue manager reside in the same Windows domain.</span></span> <span data-ttu-id="70df7-141">这在通过 HTTP 边界发送消息时是不可能的。</span><span class="sxs-lookup"><span data-stu-id="70df7-141">This is not possible when sending messages over HTTP boundary.</span></span> <span data-ttu-id="70df7-142">因此，无法使用默认传输安全。</span><span class="sxs-lookup"><span data-stu-id="70df7-142">As such, the default transport security does not work.</span></span> <span data-ttu-id="70df7-143">如果需要传输安全，则传输安全必须设置为“证书”。</span><span class="sxs-lookup"><span data-stu-id="70df7-143">The transport security must be set to Certificate if transport security is desired.</span></span> <span data-ttu-id="70df7-144">消息安全也可用于保护消息。</span><span class="sxs-lookup"><span data-stu-id="70df7-144">Message security can also be used to secure the message.</span></span> <span data-ttu-id="70df7-145">在本示例中，为说明 SRMP 消息传递，关闭了传输和消息安全。</span><span class="sxs-lookup"><span data-stu-id="70df7-145">In this sample, both transport and message security is turned off to illustrate SRMP messaging.</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8" ?>  
<configuration>  
  
  <system.serviceModel>  
  
    <client>  
      <!-- Define NetMsmqEndpoint -->  
      <endpoint name="OrderProcessorEndpoint"  
           address=  
          "net.msmq://localhost/private/ServiceModelSamplesSrmp"   
           bindingConfiguration="srmpBinding"   
           binding="netMsmqBinding"   
           contract="IOrderProcessor" />  
    </client>  
    <bindings>  
      <netMsmqBinding>  
        <binding name="srmpBinding"  
                 queueTransferProtocol="Srmp">  
          <security mode="None" />  
        </binding>  
      </netMsmqBinding>  
    </bindings>  
  </system.serviceModel>  
  
</configuration>  
```  
  
 <span data-ttu-id="70df7-146">运行此示例可生成下面的输出。</span><span class="sxs-lookup"><span data-stu-id="70df7-146">Running the sample yields the following output.</span></span>  
  
```  
Processing Purchase Order: 556b70be-31ee-4a3b-8df4-ed5e538015a4   
Customer: somecustomer.com   
OrderDetails   
    Order LineItem: 54 of Blue Widget @unit price: $29.99   
    Order LineItem: 890 of Red Widget @unit price: $45.89   
    Total cost of this order: $42461.56   
    Order status: Pending  
```  
  
> [!IMPORTANT]
>  <span data-ttu-id="70df7-147">您的计算机上可能已安装这些示例。</span><span class="sxs-lookup"><span data-stu-id="70df7-147">The samples may already be installed on your machine.</span></span> <span data-ttu-id="70df7-148">在继续操作之前，请先检查以下（默认）目录：</span><span class="sxs-lookup"><span data-stu-id="70df7-148">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="70df7-149">如果此目录不存在，请转到[Windows Communication Foundation (WCF) 和.NET Framework 4 的 Windows Workflow Foundation (WF) 示例](https://go.microsoft.com/fwlink/?LinkId=150780)若要下载所有 Windows Communication Foundation (WCF) 和[!INCLUDE[wf1](../../../../includes/wf1-md.md)]示例。</span><span class="sxs-lookup"><span data-stu-id="70df7-149">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="70df7-150">此示例位于以下目录：</span><span class="sxs-lookup"><span data-stu-id="70df7-150">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Binding\Net\MSMQ\SRMP`  
  
