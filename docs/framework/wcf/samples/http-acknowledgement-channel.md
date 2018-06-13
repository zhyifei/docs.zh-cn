---
title: HTTP 确认通道
ms.date: 03/30/2017
ms.assetid: 469f3056-5ef2-4753-8acf-b574d23d83cf
ms.openlocfilehash: c56b2fbe9d0bac3143ee7d234fd36a75f7b8071c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33502827"
---
# <a name="http-acknowledgement-channel"></a><span data-ttu-id="70d73-102">HTTP 确认通道</span><span class="sxs-lookup"><span data-stu-id="70d73-102">HTTP Acknowledgement Channel</span></span>
<span data-ttu-id="70d73-103">HTTP 确认通道是一个更改单向消息传递模式的分层通道示例，它允许服务确认或拒绝传入的消息，而不是在接收时自动发送确认。</span><span class="sxs-lookup"><span data-stu-id="70d73-103">The HTTP Acknowledgement Channel is an example of a layered channel that changes the one-way messaging pattern, allowing a service to acknowledge or refuse incoming messages rather than automatically sending an acknowledgement on receipt.</span></span> <span data-ttu-id="70d73-104">HTTP 确认通道还允许服务延迟确认，直到服务可以做出将对消息进行处理的业务级别的保证。</span><span class="sxs-lookup"><span data-stu-id="70d73-104">The HTTP Acknowledgement Channel also allows the service to delay acknowledgement until it can make a business-level guarantee that the message will be processed.</span></span>  
  
## <a name="demonstrates"></a><span data-ttu-id="70d73-105">演示</span><span class="sxs-lookup"><span data-stu-id="70d73-105">Demonstrates</span></span>  
 <span data-ttu-id="70d73-106"><xref:System.ServiceModel.Channels.ReceiveContext>，分层通道示例（HTTP 确认通道）。</span><span class="sxs-lookup"><span data-stu-id="70d73-106"><xref:System.ServiceModel.Channels.ReceiveContext>, Layered channel example (HTTP Acknowledgement channel).</span></span>  
  
## <a name="discussion"></a><span data-ttu-id="70d73-107">讨论</span><span class="sxs-lookup"><span data-stu-id="70d73-107">Discussion</span></span>  
 <span data-ttu-id="70d73-108">HTTP 确认通道实现 <xref:System.ServiceModel.Channels.ReceiveContext>，通过延迟确认将 HTTP 请求-答复消息传递模式重设为单向模式。</span><span class="sxs-lookup"><span data-stu-id="70d73-108">The HTTP Acknowledgement Channel implements <xref:System.ServiceModel.Channels.ReceiveContext> to reshape the HTTP request-reply messaging pattern to a one-way pattern with delayed acknowledgement.</span></span> <span data-ttu-id="70d73-109">使用此新模式，服务可以确保进行消息处理，方法是以 HTTP OK 状态代码 200 的形式发送确认而不阻止客户端，直到消息处理完成；或者可以 HTTP 内部服务器错误状态代码 500 的形式将失败消息发送到客户端。</span><span class="sxs-lookup"><span data-stu-id="70d73-109">Using this new pattern, a service can ensure message processing by sending an acknowledgement in the form of an HTTP OK status code of 200 without blocking the client until message processing completes or can send a failure message to the client in the form of an HTTP Internal Server error status code of 500.</span></span> <span data-ttu-id="70d73-110">例如，服务可在将一条消息写入队列后发送确认，然后继续以异步方式处理该消息。</span><span class="sxs-lookup"><span data-stu-id="70d73-110">For example, a service could send an acknowledgement after writing a message to a queue, and then continue processing the message asynchronously.</span></span> <span data-ttu-id="70d73-111">在此方案中，如果客户端在收到来自服务的确认之前重新发送每条消息，则该客户端可以确信其消息已至少由该服务处理一次。</span><span class="sxs-lookup"><span data-stu-id="70d73-111">In this scenario, a client could be assured its messages were processed at least once by the service, if it re-sent each message until it received an acknowledgement from the service.</span></span> <span data-ttu-id="70d73-112">请注意，如果服务要求通过 HTTP 进行快速异步消息处理而没有任何消息处理保证，则 <xref:System.ServiceModel.Channels.OneWayBindingElement> 是更合适的选择。</span><span class="sxs-lookup"><span data-stu-id="70d73-112">Note that, if a service requires fast asynchronous message processing over HTTP without any message processing guarantees, then the <xref:System.ServiceModel.Channels.OneWayBindingElement> is a more appropriate choice.</span></span>  
  
 <span data-ttu-id="70d73-113"><xref:System.ServiceModel.Channels.ReceiveContext> 用于在确定是否可以在服务上处理该消息时就地保存该消息。</span><span class="sxs-lookup"><span data-stu-id="70d73-113"><xref:System.ServiceModel.Channels.ReceiveContext> is used to hold the message in place while it is determined whether the message can be processed at the service.</span></span> <span data-ttu-id="70d73-114">通过在发送 HTTP OK 状态代码的 <xref:System.ServiceModel.Channels.ReceiveContext> 对象上调用 Complete，可以指示服务成功处理消息的能力；通过在 <xref:System.ServiceModel.Channels.ReceiveContext> 对象（发送 HTTP 内部服务器错误状态代码）上调用 `Abandon` 的 <xref:System.ServiceModel.Channels.ReceiveContext> 方法，可以指示服务是否能够处理该消息。</span><span class="sxs-lookup"><span data-stu-id="70d73-114">The ability of a service to successfully process the message is indicated by calling Complete on the <xref:System.ServiceModel.Channels.ReceiveContext> object that sends an HTTP OK status code and whether the service can process the message is indicated by calling <xref:System.ServiceModel.Channels.ReceiveContext>’s `Abandon` method on the <xref:System.ServiceModel.Channels.ReceiveContext> object, which sends an HTTP Internal Server error status code.</span></span>  
  
 <span data-ttu-id="70d73-115">在此示例中，客户端通过发送员工 ID 来请求处理信息。</span><span class="sxs-lookup"><span data-stu-id="70d73-115">In this example, the client requests processing information by sending an employee ID.</span></span> <span data-ttu-id="70d73-116">在服务端，如果收到的员工 ID 大于 50，则该服务将 HTTP 状态代码 500（内部服务器错误）发送回客户端，否则假定可以成功进行处理，并将 HTTP 状态代码 200（成功）发送到客户端。</span><span class="sxs-lookup"><span data-stu-id="70d73-116">On the service end, if the employee ID received is greater than 50, the service sends an HTTP Status code of 500 (Internal Server Error) back to the client, otherwise it is assumed that the processing can be successfully done and sends an HTTP Status code of 200 (Successful) to the client.</span></span>  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="70d73-117">设置、生成和运行示例</span><span class="sxs-lookup"><span data-stu-id="70d73-117">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="70d73-118">使用管理员权限打开 [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="70d73-118">Open [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] with Administrator privileges.</span></span>  
  
2.  <span data-ttu-id="70d73-119">打开**httpackchannel**解决方案。</span><span class="sxs-lookup"><span data-stu-id="70d73-119">Open the **HttpAckChannel** solution.</span></span>  
  
3.  <span data-ttu-id="70d73-120">启动的新实例**服务**通过右键单击中的项目的项目**解决方案资源管理器**，并选择**调试**，**启动新实例**从上下文菜单。</span><span class="sxs-lookup"><span data-stu-id="70d73-120">Start a new instance of the **Service** project by right clicking the project in **Solution Explorer**, and selecting **Debug**, **Start new instance** from the context menu.</span></span>  
  
4.  <span data-ttu-id="70d73-121">启动的新实例**客户端**通过右键单击中的项目的项目**解决方案资源管理器**，并选择**调试**，和**启动新实例**从上下文菜单。</span><span class="sxs-lookup"><span data-stu-id="70d73-121">Start a new instance of the **Client** project by right clicking the project in **Solution Explorer**, and selecting **Debug**, and **Start new instance** from the context menu.</span></span>  
  
5.  <span data-ttu-id="70d73-122">启动服务后，在客户端窗口中按 Enter 让客户端向服务发送一条消息。</span><span class="sxs-lookup"><span data-stu-id="70d73-122">Once the service has started, press ENTER in the client window to let the client send a message to the service.</span></span>  
  
6.  <span data-ttu-id="70d73-123">第一条消息在该服务上进行处理，然后它将一个 HTTP OK 状态代码发送回客户端。</span><span class="sxs-lookup"><span data-stu-id="70d73-123">The first message is processed on the service, and it sends an HTTP OK status code back to the client.</span></span>  
  
7.  <span data-ttu-id="70d73-124">第二条消息不成功，它将一个 HTTP 内部服务器错误代码发送回客户端，这将在客户端上引发 <xref:System.ServiceModel.CommunicationException>。</span><span class="sxs-lookup"><span data-stu-id="70d73-124">The second message is unsuccessful, and it sends an HTTP Internal Server error status code back to the client, which raises a <xref:System.ServiceModel.CommunicationException> on the client.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="70d73-125">您的计算机上可能已安装这些示例。</span><span class="sxs-lookup"><span data-stu-id="70d73-125">The samples may already be installed on your machine.</span></span> <span data-ttu-id="70d73-126">在继续操作之前，请先检查以下（默认）目录：</span><span class="sxs-lookup"><span data-stu-id="70d73-126">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="70d73-127">如果此目录不存在，请转到[Windows Communication Foundation (WCF) 和针对.NET Framework 4 的 Windows Workflow Foundation (WF) 示例](http://go.microsoft.com/fwlink/?LinkId=150780)下载所有 Windows Communication Foundation (WCF) 和[!INCLUDE[wf1](../../../../includes/wf1-md.md)]示例。</span><span class="sxs-lookup"><span data-stu-id="70d73-127">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="70d73-128">此示例位于以下目录：</span><span class="sxs-lookup"><span data-stu-id="70d73-128">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\Channels\HttpAckChannel`
