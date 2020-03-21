---
title: 使用 HTTP、TCP 或命名管道的异步方案
ms.date: 03/30/2017
ms.assetid: a4d62402-43a4-48a4-9ced-220633ebc4ce
ms.openlocfilehash: 6ae96c0aac5010adf37eb78ed57d1549885ece58
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79185784"
---
# <a name="asynchronous-scenarios-using-http-tcp-or-named-pipe"></a><span data-ttu-id="22ab0-102">使用 HTTP、TCP 或命名管道的异步方案</span><span class="sxs-lookup"><span data-stu-id="22ab0-102">Asynchronous Scenarios using HTTP, TCP, or Named-Pipe</span></span>
<span data-ttu-id="22ab0-103">本主题描述不同异步请求/答复方案的活动和传输，这些异步方案包含使用 HTTP、TCP 或命名管道的多线程请求。</span><span class="sxs-lookup"><span data-stu-id="22ab0-103">This topic describes the activities and transfers for different asynchronous request/reply scenarios, with multithreaded requests using HTTP, TCP, or named pipe.</span></span>  
  
## <a name="asynchronous-requestreply-without-errors"></a><span data-ttu-id="22ab0-104">未发生错误的异步请求/答复</span><span class="sxs-lookup"><span data-stu-id="22ab0-104">Asynchronous Request/Reply without Errors</span></span>  
 <span data-ttu-id="22ab0-105">本节描述异步请求/答复方案的活动和传输，该方案包含多线程客户端。</span><span class="sxs-lookup"><span data-stu-id="22ab0-105">This section describes the activities and transfers for an asynchronous request/reply scenario, with multithreaded clients.</span></span>  
  
 <span data-ttu-id="22ab0-106">当 `beginCall` 返回且 `endCall` 返回时，调用方活动终止。</span><span class="sxs-lookup"><span data-stu-id="22ab0-106">The caller activity terminates when `beginCall` returns, and `endCall` returns.</span></span> <span data-ttu-id="22ab0-107">如果调用回调，则回调返回。</span><span class="sxs-lookup"><span data-stu-id="22ab0-107">If a callback is called, the callback returns.</span></span>  
  
 <span data-ttu-id="22ab0-108">当 `beginCall` 返回、`endCall` 返回，或者当回调返回（如果从被调用的活动中调用回调）时，被调用的活动将终止。</span><span class="sxs-lookup"><span data-stu-id="22ab0-108">The called activity terminates when `beginCall` returns, `endCall` returns, or when the callback returns if it was called from that activity.</span></span>  
  
### <a name="asynchronous-client-without-callback"></a><span data-ttu-id="22ab0-109">不执行回调的异步客户端</span><span class="sxs-lookup"><span data-stu-id="22ab0-109">Asynchronous Client without Callback</span></span>  
  
#### <a name="propagation-is-enabled-on-both-sides-using-http"></a><span data-ttu-id="22ab0-110">在使用 HTTP 的两端启用传播</span><span class="sxs-lookup"><span data-stu-id="22ab0-110">Propagation is Enabled on Both Sides, using HTTP</span></span>  
 ![无回调的异步客户端，其中传播活动在两侧设置为 true。](./media/asynchronous-scenarios-using-http-tcp-or-named-pipe/asynchronous-client-no-callback.gif)
  
 <span data-ttu-id="22ab0-112">如果`propagateActivity=true`，进程消息指示要传输到哪个进程操作活动。</span><span class="sxs-lookup"><span data-stu-id="22ab0-112">If `propagateActivity=true`, ProcessMessage indicates which ProcessAction activity to transfer to.</span></span>  
  
 <span data-ttu-id="22ab0-113">对于基于 HTTP 的方案，ReceiveBytes 将在发送的第一条消息中调用，并在请求的生存期内存在。</span><span class="sxs-lookup"><span data-stu-id="22ab0-113">For HTTP-based scenarios, ReceiveBytes is invoked on the first message to send, and exists for the lifetime of the request.</span></span>  
  
#### <a name="propagation-is-disabled-on-either-sides-using-http"></a><span data-ttu-id="22ab0-114">在使用 HTTP 的任意一端上禁用传播</span><span class="sxs-lookup"><span data-stu-id="22ab0-114">Propagation is Disabled on Either Sides, using HTTP</span></span>  
 <span data-ttu-id="22ab0-115">如果`propagateActivity=false`任一方面，ProcessMessage 并不指示要传输到哪个 ProcessAction 活动。</span><span class="sxs-lookup"><span data-stu-id="22ab0-115">If `propagateActivity=false` on either side, ProcessMessage does not indicate which ProcessAction activity to transfer to.</span></span> <span data-ttu-id="22ab0-116">因此，将调用一个具有新 ID 的新临时 ProcessAction 活动。</span><span class="sxs-lookup"><span data-stu-id="22ab0-116">Therefore, a new temporary ProcessAction activity with a new ID is invoked.</span></span> <span data-ttu-id="22ab0-117">当异步响应与 ServiceModel 代码中的请求匹配时，可从本地上下文中检索活动 ID。</span><span class="sxs-lookup"><span data-stu-id="22ab0-117">When the asynchronous response is matched to the request in ServiceModel code, the Activity ID can be retrieved from the local context.</span></span> <span data-ttu-id="22ab0-118">可以传送到具有该 ID 的实际 ProcessAction 活动。</span><span class="sxs-lookup"><span data-stu-id="22ab0-118">The actual ProcessAction activity can be transferred to with that ID.</span></span>  
  
 ![无回调的异步客户端，其中传播活动设置为 false。](./media/asynchronous-scenarios-using-http-tcp-or-named-pipe/asynchronous-scenario-propagation-disabled-either-side.gif)  

 <span data-ttu-id="22ab0-120">对于基于 HTTP 的方案，ReceiveBytes 将在发送的第一条消息中调用，并在请求的生存期内存在。</span><span class="sxs-lookup"><span data-stu-id="22ab0-120">For HTTP-based scenarios, ReceiveBytes is invoked on the first message to send, and exists for the lifetime of the request.</span></span>  
  
 <span data-ttu-id="22ab0-121">当调用方或被调用方时，以及响应消息`propagateActivity=false`不包含操作标头时，在异步客户端上创建进程操作活动。</span><span class="sxs-lookup"><span data-stu-id="22ab0-121">A Process Action activity is created on an asynchronous client when `propagateActivity=false` at the caller or callee, and when the response message does not include an Action header.</span></span>  
  
#### <a name="propagation-is-enabled-on-both-sides-using-tcp-or-named-pipe"></a><span data-ttu-id="22ab0-122">在使用 TCP 或命名管道的两端启用传播</span><span class="sxs-lookup"><span data-stu-id="22ab0-122">Propagation is Enabled on Both Sides, using TCP or Named Pipe</span></span>  
 ![无回调的异步客户端，其中传播活动在两侧设置为 true，并命名为管道/TCP。](./media/asynchronous-scenarios-using-http-tcp-or-named-pipe/asynchronous-scenario-propagation-enabled-using-tcp.gif)  
  
 <span data-ttu-id="22ab0-124">对于命名管道或基于 TCP 的方案，ReceiveBytes 在客户端打开时进行调用，并在连接的生存期内存在。</span><span class="sxs-lookup"><span data-stu-id="22ab0-124">For a Named-Pipe or TCP-based scenario, ReceiveBytes is invoked when the client is opened, and exists for the lifetime of the connection.</span></span>  
  
 <span data-ttu-id="22ab0-125">与第一个图像类似，如果`propagateActivity=true`"进程消息"指示要传输到哪个进程操作活动。</span><span class="sxs-lookup"><span data-stu-id="22ab0-125">Similar to the first image, if `propagateActivity=true`, ProcessMessage indicates which ProcessAction activity to transfer to.</span></span>  
  
#### <a name="propagation-is-disabled-on-either-sides-using-tcp-or-named-pipe"></a><span data-ttu-id="22ab0-126">在使用 TCP 或命名管道的任意一端上禁用传播</span><span class="sxs-lookup"><span data-stu-id="22ab0-126">Propagation is Disabled on Either Sides, using TCP or Named Pipe</span></span>  
 <span data-ttu-id="22ab0-127">对于命名管道或基于 TCP 的方案，ReceiveBytes 在客户端打开时进行调用，并在连接的生存期内存在。</span><span class="sxs-lookup"><span data-stu-id="22ab0-127">For a Named-Pipe or TCP-based scenario, ReceiveBytes is invoked when the client is opened, and exists for the lifetime of the connection.</span></span>  
  
 <span data-ttu-id="22ab0-128">与第二个映像类似，如果`propagateActivity=false`任一方面，ProcessMessage 不会指示要传输到哪个 ProcessAction 活动。</span><span class="sxs-lookup"><span data-stu-id="22ab0-128">Similar to the second image, if `propagateActivity=false` on either side, ProcessMessage does not indicate which ProcessAction activity to transfer to.</span></span> <span data-ttu-id="22ab0-129">因此，将调用一个具有新 ID 的新临时 ProcessAction 活动。</span><span class="sxs-lookup"><span data-stu-id="22ab0-129">Therefore, a new temporary ProcessAction activity with a new ID is invoked.</span></span> <span data-ttu-id="22ab0-130">当异步响应与 ServiceModel 代码中的请求匹配时，可从本地上下文中检索活动 ID。</span><span class="sxs-lookup"><span data-stu-id="22ab0-130">When the asynchronous response is matched to the request in ServiceModel code, the Activity ID can be retrieved from the local context.</span></span> <span data-ttu-id="22ab0-131">可以传送到具有该 ID 的实际 ProcessAction 活动。</span><span class="sxs-lookup"><span data-stu-id="22ab0-131">The actual ProcessAction activity can be transferred to with that ID.</span></span>  
  
 ![无回调的异步客户端，其中传播活动设置为 false，并且命名管道/TCP。](./media/asynchronous-scenarios-using-http-tcp-or-named-pipe/asynchronous-scenario-propagation-disabled-using-tcp.gif)  

### <a name="asynchronous-client-with-callback"></a><span data-ttu-id="22ab0-133">执行回调的异步客户端</span><span class="sxs-lookup"><span data-stu-id="22ab0-133">Asynchronous client with Callback</span></span>  
 <span data-ttu-id="22ab0-134">此方案将为回调和 `endCall` 添加活动 G 和 A’ 和它们的传入/传出。</span><span class="sxs-lookup"><span data-stu-id="22ab0-134">This scenario adds activities G and A’, for the callback and `endCall`, and their transfers in/out.</span></span>  
  
 <span data-ttu-id="22ab0-135">本节仅演示使用 HTTP`propagateActivity`=`true`与 。</span><span class="sxs-lookup"><span data-stu-id="22ab0-135">This section only demonstrates using HTTP with `propagateActivity`=`true`.</span></span> <span data-ttu-id="22ab0-136">但是，其他活动和传输也适用于其他情况（即`propagateActivity`=`false`，使用 TCP 或命名管道）。</span><span class="sxs-lookup"><span data-stu-id="22ab0-136">However, the additional activities and transfers also apply to the other cases (that is, `propagateActivity`=`false`, using TCP or Named-Pipe).</span></span>  
  
 <span data-ttu-id="22ab0-137">当客户端调用用户代码通知结果已准备就绪时，回调将创建新的活动 (G)。</span><span class="sxs-lookup"><span data-stu-id="22ab0-137">The callback creates a new activity (G) when the client calls user code to notify that results are ready.</span></span> <span data-ttu-id="22ab0-138">然后，用户代码在回调过程中（如图 5 所示）或回调过程之外（如图 6 所示）调用 `endCall`。</span><span class="sxs-lookup"><span data-stu-id="22ab0-138">User code then calls `endCall` within the callback (as shown in Figure 5) or outside the callback (Figure 6).</span></span> <span data-ttu-id="22ab0-139">由于不知道从哪个用户活动`endCall`调用，因此此活动被标记为`A’`。</span><span class="sxs-lookup"><span data-stu-id="22ab0-139">Because it is not known which user activity `endCall` is being called from, this activity is labeled `A’`.</span></span> <span data-ttu-id="22ab0-140">A’ 可能与 A 相同，也可能不同。</span><span class="sxs-lookup"><span data-stu-id="22ab0-140">It is possible that A’ can be identical to or different from A.</span></span>  
  
 ![显示具有回调的异步客户端，在回调中显示结束调用。](./media/asynchronous-scenarios-using-http-tcp-or-named-pipe/asynchronous-client-callback-endcall-in-callback.gif)  

 ![显示具有回调的异步客户端，在外部回调结束调用。](./media/asynchronous-scenarios-using-http-tcp-or-named-pipe/asynchronous-client-callback-endcall-outside-callback.gif)  

### <a name="asynchronous-server-with-callback"></a><span data-ttu-id="22ab0-143">执行回调的异步服务器</span><span class="sxs-lookup"><span data-stu-id="22ab0-143">Asynchronous Server with Callback</span></span>  
 ![显示带回调的异步服务器。](./media/asynchronous-scenarios-using-http-tcp-or-named-pipe/asynchronous-server-callback.gif)  

 <span data-ttu-id="22ab0-145">通道堆栈在消息接收过程中回调客户端：对此处理的跟踪在 ProcessRequest 活动本身中发出。</span><span class="sxs-lookup"><span data-stu-id="22ab0-145">The channel stack calls back the client on Message Receive: traces for this processing are emitted in the ProcessRequest activity itself.</span></span>  
  
## <a name="asynchronous-requestreply-with-errors"></a><span data-ttu-id="22ab0-146">发生错误的异步请求/答复</span><span class="sxs-lookup"><span data-stu-id="22ab0-146">Asynchronous Request/Reply with Errors</span></span>  
 <span data-ttu-id="22ab0-147">在 `endCall` 过程中接收到错误消息错误。</span><span class="sxs-lookup"><span data-stu-id="22ab0-147">Fault message errors are received during `endCall`.</span></span> <span data-ttu-id="22ab0-148">否则，活动和传输应与上面的方案类似。</span><span class="sxs-lookup"><span data-stu-id="22ab0-148">Otherwise, activities and transfers are similar to previous scenarios.</span></span>  
  
## <a name="asynchronous-one-way-with-or-without-errors"></a><span data-ttu-id="22ab0-149">发生错误或未发生错误的异步单向方案</span><span class="sxs-lookup"><span data-stu-id="22ab0-149">Asynchronous One-Way with or without Errors</span></span>  
 <span data-ttu-id="22ab0-150">不会向客户端返回任何响应或错误。</span><span class="sxs-lookup"><span data-stu-id="22ab0-150">No response or fault is returned to the client.</span></span>
