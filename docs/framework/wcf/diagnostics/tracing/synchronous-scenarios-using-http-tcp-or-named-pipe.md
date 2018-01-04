---
title: "使用 HTTP、TCP 或命名管道的同步方案"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7e90af1b-f8f6-41b9-a63a-8490ada502b1
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 428e8852c9b1706e88b1688b4a1f2e36c167fe28
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="synchronous-scenarios-using-http-tcp-or-named-pipe"></a><span data-ttu-id="0e826-102">使用 HTTP、TCP 或命名管道的同步方案</span><span class="sxs-lookup"><span data-stu-id="0e826-102">Synchronous Scenarios using HTTP, TCP or Named-Pipe</span></span>
<span data-ttu-id="0e826-103">本主题描述不同的同步请求/答复方案的活动和转换，这些同步方案使用单线程客户端以及 HTTP、TCP 或命名管道。</span><span class="sxs-lookup"><span data-stu-id="0e826-103">This topic describes the activities and transfers for different synchronous request/reply scenarios, with a single-threaded client, using HTTP, TCP or named pipe.</span></span> <span data-ttu-id="0e826-104">请参阅[使用 HTTP、 TCP 或命名管道的异步方案](../../../../../docs/framework/wcf/diagnostics/tracing/asynchronous-scenarios-using-http-tcp-or-named-pipe.md)有关多线程请求的详细信息。</span><span class="sxs-lookup"><span data-stu-id="0e826-104">See [Asynchronous Scenarios using HTTP, TCP, or Named-Pipe](../../../../../docs/framework/wcf/diagnostics/tracing/asynchronous-scenarios-using-http-tcp-or-named-pipe.md) for more information on multi-threaded requests.</span></span>  
  
## <a name="synchronous-requestreply-without-errors"></a><span data-ttu-id="0e826-105">不返回错误的同步请求/答复</span><span class="sxs-lookup"><span data-stu-id="0e826-105">Synchronous Request/Reply without Errors</span></span>  
 <span data-ttu-id="0e826-106">本节描述有效的同步请求/答复方案的活动和转换，该方案使用单线程客户端。</span><span class="sxs-lookup"><span data-stu-id="0e826-106">This section describes the activities and transfers for a valid synchronous request/reply scenario, with single-threaded client.</span></span>  
  
### <a name="client"></a><span data-ttu-id="0e826-107">客户端</span><span class="sxs-lookup"><span data-stu-id="0e826-107">Client</span></span>  
  
#### <a name="establishing-communication-with-service-endpoint"></a><span data-ttu-id="0e826-108">与服务终结点建立通信</span><span class="sxs-lookup"><span data-stu-id="0e826-108">Establishing Communication with Service Endpoint</span></span>  
 <span data-ttu-id="0e826-109">构造并打开了一个客户端。</span><span class="sxs-lookup"><span data-stu-id="0e826-109">A client is constructed and opened.</span></span> <span data-ttu-id="0e826-110">对于每个这些步骤，环境活动 （A） 传输到"构造客户端"（B） 和"打开的客户端"（C） 活动分别。</span><span class="sxs-lookup"><span data-stu-id="0e826-110">For each of these steps, the ambient activity (A) is transferred to a "Construct Client" (B) and "Open Client" (C) activity respectively.</span></span> <span data-ttu-id="0e826-111">对于转换到的每个活动，都将挂起环境活动，直到传回消息为止，即直到执行 ServiceModel 代码为止。</span><span class="sxs-lookup"><span data-stu-id="0e826-111">For each activity being transferred to, the ambient activity is suspended until there is a transfer back, that is, until ServiceModel code is executed.</span></span>  
  
#### <a name="making-a-request-to-service-endpoint"></a><span data-ttu-id="0e826-112">向服务终结点发出请求</span><span class="sxs-lookup"><span data-stu-id="0e826-112">Making a Request to Service Endpoint</span></span>  
 <span data-ttu-id="0e826-113">环境活动传输到"ProcessAction"(D) 活动。</span><span class="sxs-lookup"><span data-stu-id="0e826-113">The ambient activity is transferred to a "ProcessAction" (D) activity.</span></span> <span data-ttu-id="0e826-114">在此活动内，将发送请求消息并接收响应消息。</span><span class="sxs-lookup"><span data-stu-id="0e826-114">Within this activity, a request message is sent, and a response message is received.</span></span> <span data-ttu-id="0e826-115">此活动在控制返回到用户代码时结束。</span><span class="sxs-lookup"><span data-stu-id="0e826-115">The activity ends when control returns to user code.</span></span> <span data-ttu-id="0e826-116">因为这是一个同步请求，因此环境活动在控制返回前将一直挂起。</span><span class="sxs-lookup"><span data-stu-id="0e826-116">Because this is a synchronous request, the ambient activity suspends until control returns.</span></span>  
  
#### <a name="closing-communication-with-service-endpoint"></a><span data-ttu-id="0e826-117">关闭与服务终结点的通信</span><span class="sxs-lookup"><span data-stu-id="0e826-117">Closing Communication with Service Endpoint</span></span>  
 <span data-ttu-id="0e826-118">客户端的关闭活动 (I) 是从环境活动中创建的。</span><span class="sxs-lookup"><span data-stu-id="0e826-118">The client's close activity (I) is created from the ambient activity.</span></span> <span data-ttu-id="0e826-119">这与新建和打开活动完全相同。</span><span class="sxs-lookup"><span data-stu-id="0e826-119">This is identical to new and open.</span></span>  
  
### <a name="server"></a><span data-ttu-id="0e826-120">服务器</span><span class="sxs-lookup"><span data-stu-id="0e826-120">Server</span></span>  
  
#### <a name="setting-up-a-service-host"></a><span data-ttu-id="0e826-121">设置服务主机</span><span class="sxs-lookup"><span data-stu-id="0e826-121">Setting up a Service Host</span></span>  
 <span data-ttu-id="0e826-122">ServiceHost 的新建和打开活动（N 和 O）是从环境活动 (M) 中创建的。</span><span class="sxs-lookup"><span data-stu-id="0e826-122">The ServiceHost’s new and open activities (N and O) are created from the ambient activity (M).</span></span>  
  
 <span data-ttu-id="0e826-123">侦听器活动 (P) 是从为每个侦听器打开一个 ServiceHost 的活动中创建的。</span><span class="sxs-lookup"><span data-stu-id="0e826-123">A listener activity (P) is created from opening a ServiceHost for each listener.</span></span> <span data-ttu-id="0e826-124">侦听器活动等待接收和处理数据。</span><span class="sxs-lookup"><span data-stu-id="0e826-124">The listener activity waits to receive and process data.</span></span>  
  
#### <a name="receiving-data-on-the-wire"></a><span data-ttu-id="0e826-125">在网络上接收数据</span><span class="sxs-lookup"><span data-stu-id="0e826-125">Receiving Data on the Wire</span></span>  
 <span data-ttu-id="0e826-126">当数据到达时在网络上时，如果它尚不存在 (Q) 来处理接收到的数据，则创建"ReceiveBytes"活动。</span><span class="sxs-lookup"><span data-stu-id="0e826-126">When data arrives on the wire, a "ReceiveBytes" activity is created if it does not already exist (Q) to process the received data.</span></span> <span data-ttu-id="0e826-127">此活动可针对连接或队列中的多个消息重用。</span><span class="sxs-lookup"><span data-stu-id="0e826-127">This activity can be reused for multiple messages within a connection or queue.</span></span>  
  
 <span data-ttu-id="0e826-128">如果 ReceiveBytes 具有足够的数据形成一个 SOAP 操作消息，则该活动将启动一个 ProcessMessage 活动 (R)。</span><span class="sxs-lookup"><span data-stu-id="0e826-128">The ReceiveBytes activity launches a ProcessMessage activity (R) if it has enough data to form a SOAP action message.</span></span>  
  
 <span data-ttu-id="0e826-129">在活动 R 中，将对消息头进行处理，并验证 activityID 标头。</span><span class="sxs-lookup"><span data-stu-id="0e826-129">In activity R, the message headers are processed, and the activityID header is verified.</span></span> <span data-ttu-id="0e826-130">如果此标头存在，则将活动 ID 设置为 ProcessAction 活动；否则创建一个新的 ID。</span><span class="sxs-lookup"><span data-stu-id="0e826-130">If this header is present, the activity ID is set to the ProcessAction activity; otherwise, a new ID is created.</span></span>  
  
 <span data-ttu-id="0e826-131">处理调用时，将创建 ProcessAction 活动 (S) 并转换到该活动。</span><span class="sxs-lookup"><span data-stu-id="0e826-131">ProcessAction activity (S) is created and being transferred to, when the call is processed.</span></span> <span data-ttu-id="0e826-132">此活动在与传入消息有关的所有处理（包括执行用户代码 (T) 和发送响应消息（如果适用））都完成时结束。</span><span class="sxs-lookup"><span data-stu-id="0e826-132">This activity ends when all processing related to the incoming message is completed, including executing user code (T) and sending the response message if applicable.</span></span>  
  
#### <a name="closing-a-service-host"></a><span data-ttu-id="0e826-133">关闭服务主机</span><span class="sxs-lookup"><span data-stu-id="0e826-133">Closing a Service Host</span></span>  
 <span data-ttu-id="0e826-134">ServiceHost 的关闭活动 (Z) 是从环境活动中创建的。</span><span class="sxs-lookup"><span data-stu-id="0e826-134">The ServiceHost’s close activity (Z) is created from the ambient activity.</span></span>  
  
 <span data-ttu-id="0e826-135">![使用 HTTP 和 #47; 的同步方案TCP 和 #47;命名管道](../../../../../docs/framework/wcf/diagnostics/tracing/media/sync.gif "同步")</span><span class="sxs-lookup"><span data-stu-id="0e826-135">![Synchronous scenarios using HTTP&#47;TCP&#47; Named Pipes](../../../../../docs/framework/wcf/diagnostics/tracing/media/sync.gif "Sync")</span></span>  
  
 <span data-ttu-id="0e826-136">在\<答： 名称 >，`A`是描述在上一个文本和表 3 中的活动的快捷符号。</span><span class="sxs-lookup"><span data-stu-id="0e826-136">In \<A: name>, `A` is a shortcut symbol that describes the activity in the previous text and in table 3.</span></span> <span data-ttu-id="0e826-137">`Name` 是活动的短名称。</span><span class="sxs-lookup"><span data-stu-id="0e826-137">`Name` is a shortened name of the activity.</span></span>  
  
 <span data-ttu-id="0e826-138">如果`propagateActivity` = `true`，客户端和服务上的 Process Action 具有相同活动 id。</span><span class="sxs-lookup"><span data-stu-id="0e826-138">If `propagateActivity`=`true`, Process Action on both the client and service have the same activity ID.</span></span>  
  
## <a name="synchronous-requestreply-with-errors"></a><span data-ttu-id="0e826-139">返回错误的同步请求/答复</span><span class="sxs-lookup"><span data-stu-id="0e826-139">Synchronous Request/Reply with Errors</span></span>  
 <span data-ttu-id="0e826-140">该方案与前一方案的唯一区别是将 SOAP 错误消息作为响应消息返回。</span><span class="sxs-lookup"><span data-stu-id="0e826-140">The only difference with the previous scenario is that a SOAP fault message is returned as a response message.</span></span> <span data-ttu-id="0e826-141">如果`propagateActivity` = `true`，请求消息的活动 ID 添加到 SOAP 错误消息。</span><span class="sxs-lookup"><span data-stu-id="0e826-141">If `propagateActivity`=`true`, the activity ID of the request message is added to the SOAP fault message.</span></span>  
  
## <a name="synchronous-one-way-without-errors"></a><span data-ttu-id="0e826-142">不返回错误的同步单向方案</span><span class="sxs-lookup"><span data-stu-id="0e826-142">Synchronous One-Way without Errors</span></span>  
 <span data-ttu-id="0e826-143">该方案与第一个方案的唯一区别是不向服务器返回任何消息。</span><span class="sxs-lookup"><span data-stu-id="0e826-143">The only difference with the first scenario is that no message is returned to the server.</span></span> <span data-ttu-id="0e826-144">对于基于 HTTP 的协议，仍会将状态（有效或错误）返回到客户端。</span><span class="sxs-lookup"><span data-stu-id="0e826-144">For HTTP-based protocols, a status (valid or error) is still returned to the client.</span></span> <span data-ttu-id="0e826-145">这是因为 HTTP 是唯一一个具有属于 [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] 协议堆栈的请求-响应语义的协议。</span><span class="sxs-lookup"><span data-stu-id="0e826-145">This is because HTTP is the only protocol with a request-response semantics that is part of the [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] protocol stack.</span></span> <span data-ttu-id="0e826-146">因为 TCP 处理对于 [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] 是隐藏的，所以不会将任何确认消息发送到客户端。</span><span class="sxs-lookup"><span data-stu-id="0e826-146">Because TCP processing is hidden from [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)], no acknowledgement is sent to the client.</span></span>  
  
## <a name="synchronous-one-way-with-errors"></a><span data-ttu-id="0e826-147">返回错误的同步单向方案</span><span class="sxs-lookup"><span data-stu-id="0e826-147">Synchronous One-Way with Errors</span></span>  
 <span data-ttu-id="0e826-148">如果在处理消息期间（Q 或后续活动）出现错误，不会将任何通知返回到客户端。</span><span class="sxs-lookup"><span data-stu-id="0e826-148">If an error occurs while processing the message (Q or beyond), no notification is returned to the client.</span></span> <span data-ttu-id="0e826-149">这与“不返回错误的同步单向方案”方案完全相同。</span><span class="sxs-lookup"><span data-stu-id="0e826-149">This is identical to the "Synchronous One-Way without Errors" scenario.</span></span> <span data-ttu-id="0e826-150">如果希望接收错误消息，则不应使用单向方案。</span><span class="sxs-lookup"><span data-stu-id="0e826-150">You should not use a One-Way scenario if you want to receive an error message.</span></span>  
  
## <a name="duplex"></a><span data-ttu-id="0e826-151">双工</span><span class="sxs-lookup"><span data-stu-id="0e826-151">Duplex</span></span>  
 <span data-ttu-id="0e826-152">与上述方案的区别在于客户端充当服务，并在此服务中创建 ReceiveBytes 和 ProcessMessage 活动，这与异步方案相似。</span><span class="sxs-lookup"><span data-stu-id="0e826-152">The difference with the previous scenarios is that the client acts as a service, in which it creates the ReceiveBytes and ProcessMessage activities, similar to the Asynchronous scenarios.</span></span>
