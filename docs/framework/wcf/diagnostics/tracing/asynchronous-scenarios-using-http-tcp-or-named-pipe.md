---
title: 使用 HTTP、TCP 或命名管道的异步方案
ms.date: 03/30/2017
ms.assetid: a4d62402-43a4-48a4-9ced-220633ebc4ce
ms.openlocfilehash: d08f70186a59b8717c4441167ee720ba1c20b9dc
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61998219"
---
# <a name="asynchronous-scenarios-using-http-tcp-or-named-pipe"></a><span data-ttu-id="fc5a9-102">使用 HTTP、TCP 或命名管道的异步方案</span><span class="sxs-lookup"><span data-stu-id="fc5a9-102">Asynchronous Scenarios using HTTP, TCP, or Named-Pipe</span></span>
<span data-ttu-id="fc5a9-103">本主题描述不同异步请求/答复方案的活动和传输，这些异步方案包含使用 HTTP、TCP 或命名管道的多线程请求。</span><span class="sxs-lookup"><span data-stu-id="fc5a9-103">This topic describes the activities and transfers for different asynchronous request/reply scenarios, with multithreaded requests using HTTP, TCP, or named pipe.</span></span>  
  
## <a name="asynchronous-requestreply-without-errors"></a><span data-ttu-id="fc5a9-104">未发生错误的异步请求/答复</span><span class="sxs-lookup"><span data-stu-id="fc5a9-104">Asynchronous Request/Reply without Errors</span></span>  
 <span data-ttu-id="fc5a9-105">本节描述异步请求/答复方案的活动和传输，该方案包含多线程客户端。</span><span class="sxs-lookup"><span data-stu-id="fc5a9-105">This section describes the activities and transfers for an asynchronous request/reply scenario, with multithreaded clients.</span></span>  
  
 <span data-ttu-id="fc5a9-106">当 `beginCall` 返回且 `endCall` 返回时，调用方活动终止。</span><span class="sxs-lookup"><span data-stu-id="fc5a9-106">The caller activity terminates when `beginCall` returns, and `endCall` returns.</span></span> <span data-ttu-id="fc5a9-107">如果调用回调，则回调返回。</span><span class="sxs-lookup"><span data-stu-id="fc5a9-107">If a callback is called, the callback returns.</span></span>  
  
 <span data-ttu-id="fc5a9-108">当 `beginCall` 返回、`endCall` 返回，或者当回调返回（如果从被调用的活动中调用回调）时，被调用的活动将终止。</span><span class="sxs-lookup"><span data-stu-id="fc5a9-108">The called activity terminates when `beginCall` returns, `endCall` returns, or when the callback returns if it was called from that activity.</span></span>  
  
### <a name="asynchronous-client-without-callback"></a><span data-ttu-id="fc5a9-109">不执行回调的异步客户端</span><span class="sxs-lookup"><span data-stu-id="fc5a9-109">Asynchronous Client without Callback</span></span>  
  
#### <a name="propagation-is-enabled-on-both-sides-using-http"></a><span data-ttu-id="fc5a9-110">在使用 HTTP 的两端启用传播</span><span class="sxs-lookup"><span data-stu-id="fc5a9-110">Propagation is Enabled on Both Sides, using HTTP</span></span>  
 <span data-ttu-id="fc5a9-111">![异步方案](../../../../../docs/framework/wcf/diagnostics/tracing/media/asyn1.gif "Asyn1")</span><span class="sxs-lookup"><span data-stu-id="fc5a9-111">![Asynchronous scenarios](../../../../../docs/framework/wcf/diagnostics/tracing/media/asyn1.gif "Asyn1")</span></span>  
  
 <span data-ttu-id="fc5a9-112">图 1。</span><span class="sxs-lookup"><span data-stu-id="fc5a9-112">Figure 1.</span></span> <span data-ttu-id="fc5a9-113">异步客户端且不执行回调， `propagateActivity` = `true`双方，HTTP</span><span class="sxs-lookup"><span data-stu-id="fc5a9-113">Asynchronous client, no callback, `propagateActivity`=`true` on both sides, HTTP</span></span>  
  
 <span data-ttu-id="fc5a9-114">如果`propagateActivity` = `true`，ProcessMessage 指示要传送到哪个 ProcessAction 活动。</span><span class="sxs-lookup"><span data-stu-id="fc5a9-114">If `propagateActivity`=`true`, ProcessMessage indicates which ProcessAction activity to transfer to.</span></span>  
  
 <span data-ttu-id="fc5a9-115">对于基于 HTTP 的方案，ReceiveBytes 将在发送的第一条消息中调用，并在请求的生存期内存在。</span><span class="sxs-lookup"><span data-stu-id="fc5a9-115">For HTTP-based scenarios, ReceiveBytes is invoked on the first message to send, and exists for the lifetime of the request.</span></span>  
  
#### <a name="propagation-is-disabled-on-either-sides-using-http"></a><span data-ttu-id="fc5a9-116">在使用 HTTP 的任意一端上禁用传播</span><span class="sxs-lookup"><span data-stu-id="fc5a9-116">Propagation is Disabled on Either Sides, using HTTP</span></span>  
 <span data-ttu-id="fc5a9-117">如果`propagateActivity` = `false`任意一侧，ProcessMessage 不会指示要传送到哪个 ProcessAction 活动。</span><span class="sxs-lookup"><span data-stu-id="fc5a9-117">If `propagateActivity`=`false` on either side, ProcessMessage does not indicate which ProcessAction activity to transfer to.</span></span> <span data-ttu-id="fc5a9-118">因此，将调用一个具有新 ID 的新临时 ProcessAction 活动。</span><span class="sxs-lookup"><span data-stu-id="fc5a9-118">Therefore, a new temporary ProcessAction activity with a new ID is invoked.</span></span> <span data-ttu-id="fc5a9-119">当异步响应与 ServiceModel 代码中的请求匹配时，可从本地上下文中检索活动 ID。</span><span class="sxs-lookup"><span data-stu-id="fc5a9-119">When the asynchronous response is matched to the request in ServiceModel code, the Activity ID can be retrieved from the local context.</span></span> <span data-ttu-id="fc5a9-120">可以传送到具有该 ID 的实际 ProcessAction 活动。</span><span class="sxs-lookup"><span data-stu-id="fc5a9-120">The actual ProcessAction activity can be transferred to with that ID.</span></span>  
  
 <span data-ttu-id="fc5a9-121">![使用 HTTP 的异步方案&#47;TCP&#47;命名管道](../../../../../docs/framework/wcf/diagnostics/tracing/media/async2.gif "Async2")</span><span class="sxs-lookup"><span data-stu-id="fc5a9-121">![Asynchronous scenarios using HTTP&#47;TCP&#47;Named Pipe](../../../../../docs/framework/wcf/diagnostics/tracing/media/async2.gif "Async2")</span></span>  
  
 <span data-ttu-id="fc5a9-122">图 2.</span><span class="sxs-lookup"><span data-stu-id="fc5a9-122">Figure 2.</span></span> <span data-ttu-id="fc5a9-123">异步客户端且不执行回调， `propagateActivity` = `false`任意一端使用 HTTP</span><span class="sxs-lookup"><span data-stu-id="fc5a9-123">Asynchronous client, no callback, `propagateActivity`=`false` on either side, HTTP</span></span>  
  
 <span data-ttu-id="fc5a9-124">对于基于 HTTP 的方案，ReceiveBytes 将在发送的第一条消息中调用，并在请求的生存期内存在。</span><span class="sxs-lookup"><span data-stu-id="fc5a9-124">For HTTP-based scenarios, ReceiveBytes is invoked on the first message to send, and exists for the lifetime of the request.</span></span>  
  
 <span data-ttu-id="fc5a9-125">在异步客户端上创建 Processaction 活动时`propagateActivity` = `false`在调用方或被调用方，并当响应消息不包含 Action 标头。</span><span class="sxs-lookup"><span data-stu-id="fc5a9-125">A Process Action activity is created on an asynchronous client when `propagateActivity`=`false` at the caller or callee, and when the response message does not include an Action header.</span></span>  
  
#### <a name="propagation-is-enabled-on-both-sides-using-tcp-or-named-pipe"></a><span data-ttu-id="fc5a9-126">在使用 TCP 或命名管道的两端启用传播</span><span class="sxs-lookup"><span data-stu-id="fc5a9-126">Propagation is Enabled on Both Sides, using TCP or Named Pipe</span></span>  
 <span data-ttu-id="fc5a9-127">![使用 HTTP 的异步方案&#47;TCP&#47;命名管道](../../../../../docs/framework/wcf/diagnostics/tracing/media/async3.gif "Async3")</span><span class="sxs-lookup"><span data-stu-id="fc5a9-127">![Asynchronous scenarios using HTTP&#47;TCP&#47;Named Pipe](../../../../../docs/framework/wcf/diagnostics/tracing/media/async3.gif "Async3")</span></span>  
  
 <span data-ttu-id="fc5a9-128">图 3.</span><span class="sxs-lookup"><span data-stu-id="fc5a9-128">Figure 3.</span></span> <span data-ttu-id="fc5a9-129">异步客户端且不执行回调， `propagateActivity` = `true`两端使用命名管道 /TCP</span><span class="sxs-lookup"><span data-stu-id="fc5a9-129">Asynchronous client, no callback, `propagateActivity`=`true` on both sides, Named-Pipe/TCP</span></span>  
  
 <span data-ttu-id="fc5a9-130">对于命名管道或基于 TCP 的方案，ReceiveBytes 在客户端打开时进行调用，并在连接的生存期内存在。</span><span class="sxs-lookup"><span data-stu-id="fc5a9-130">For a Named-Pipe or TCP-based scenario, ReceiveBytes is invoked when the client is opened, and exists for the lifetime of the connection.</span></span>  
  
 <span data-ttu-id="fc5a9-131">类似于图 1，如果`propagateActivity` = `true`，ProcessMessage 指示要传送到哪个 ProcessAction 活动。</span><span class="sxs-lookup"><span data-stu-id="fc5a9-131">Similar to Figure 1, if `propagateActivity`=`true`, ProcessMessage indicates which ProcessAction activity to transfer to.</span></span>  
  
#### <a name="propagation-is-disabled-on-either-sides-using-tcp-or-named-pipe"></a><span data-ttu-id="fc5a9-132">在使用 TCP 或命名管道的任意一端上禁用传播</span><span class="sxs-lookup"><span data-stu-id="fc5a9-132">Propagation is Disabled on Either Sides, using TCP or Named Pipe</span></span>  
 <span data-ttu-id="fc5a9-133">对于命名管道或基于 TCP 的方案，ReceiveBytes 在客户端打开时进行调用，并在连接的生存期内存在。</span><span class="sxs-lookup"><span data-stu-id="fc5a9-133">For a Named-Pipe or TCP-based scenario, ReceiveBytes is invoked when the client is opened, and exists for the lifetime of the connection.</span></span>  
  
 <span data-ttu-id="fc5a9-134">类似于 Fig.2，如果`propagateActivity` = `false`任意一侧，ProcessMessage 不会指示要传送到哪个 ProcessAction 活动。</span><span class="sxs-lookup"><span data-stu-id="fc5a9-134">Similar to Fig.2, If `propagateActivity`=`false` on either side, ProcessMessage does not indicate which ProcessAction activity to transfer to.</span></span> <span data-ttu-id="fc5a9-135">因此，将调用一个具有新 ID 的新临时 ProcessAction 活动。</span><span class="sxs-lookup"><span data-stu-id="fc5a9-135">Therefore, a new temporary ProcessAction activity with a new ID is invoked.</span></span> <span data-ttu-id="fc5a9-136">当异步响应与 ServiceModel 代码中的请求匹配时，可从本地上下文中检索活动 ID。</span><span class="sxs-lookup"><span data-stu-id="fc5a9-136">When the asynchronous response is matched to the request in ServiceModel code, the Activity ID can be retrieved from the local context.</span></span> <span data-ttu-id="fc5a9-137">可以传送到具有该 ID 的实际 ProcessAction 活动。</span><span class="sxs-lookup"><span data-stu-id="fc5a9-137">The actual ProcessAction activity can be transferred to with that ID.</span></span>  
  
 <span data-ttu-id="fc5a9-138">![使用 HTTP 的异步方案&#47;TCP&#47; Named Pipes](../../../../../docs/framework/wcf/diagnostics/tracing/media/async4.gif "Async4")</span><span class="sxs-lookup"><span data-stu-id="fc5a9-138">![Asynchronous scenarios using HTTP&#47;TCP&#47; Named Pipes](../../../../../docs/framework/wcf/diagnostics/tracing/media/async4.gif "Async4")</span></span>  
  
 <span data-ttu-id="fc5a9-139">图 4。</span><span class="sxs-lookup"><span data-stu-id="fc5a9-139">Figure 4.</span></span> <span data-ttu-id="fc5a9-140">异步客户端且不执行回调， `propagateActivity` = `false`任意一端使用命名管道 /TCP</span><span class="sxs-lookup"><span data-stu-id="fc5a9-140">Asynchronous client, no callback, `propagateActivity`=`false` on either side, Named-Pipe/TCP</span></span>  
  
### <a name="asynchronous-client-with-callback"></a><span data-ttu-id="fc5a9-141">执行回调的异步客户端</span><span class="sxs-lookup"><span data-stu-id="fc5a9-141">Asynchronous client with Callback</span></span>  
 <span data-ttu-id="fc5a9-142">此方案将为回调和 `endCall` 添加活动 G 和 A’ 和它们的传入/传出。</span><span class="sxs-lookup"><span data-stu-id="fc5a9-142">This scenario adds activities G and A’, for the callback and `endCall`, and their transfers in/out.</span></span>  
  
 <span data-ttu-id="fc5a9-143">本节仅演示了如何使用具有 HTTP `propragateActivity` = `true`。</span><span class="sxs-lookup"><span data-stu-id="fc5a9-143">This section only demonstrates using HTTP with `propragateActivity`=`true`.</span></span> <span data-ttu-id="fc5a9-144">但是，其他活动和传送也适用于其他情况下 (即`propagateActivity` = `false`，使用 TCP 或命名管道)。</span><span class="sxs-lookup"><span data-stu-id="fc5a9-144">However, the additional activities and transfers also apply to the other cases (that is, `propagateActivity`=`false`, using TCP or Named-Pipe).</span></span>  
  
 <span data-ttu-id="fc5a9-145">当客户端调用用户代码通知结果已准备就绪时，回调将创建新的活动 (G)。</span><span class="sxs-lookup"><span data-stu-id="fc5a9-145">The callback creates a new activity (G) when the client calls user code to notify that results are ready.</span></span> <span data-ttu-id="fc5a9-146">然后，用户代码在回调过程中（如图 5 所示）或回调过程之外（如图 6 所示）调用 `endCall`。</span><span class="sxs-lookup"><span data-stu-id="fc5a9-146">User code then calls `endCall` within the callback (as shown in Figure 5) or outside the callback (Figure 6).</span></span> <span data-ttu-id="fc5a9-147">因为它不知道哪个用户活动`endCall`被调用，此活动标记为`A’`。</span><span class="sxs-lookup"><span data-stu-id="fc5a9-147">Because it is not known which user activity `endCall` is being called from, this activity is labeled `A’`.</span></span> <span data-ttu-id="fc5a9-148">A’ 可能与 A 相同，也可能不同。</span><span class="sxs-lookup"><span data-stu-id="fc5a9-148">It is possible that A’ can be identical to or different from A.</span></span>  
  
 <span data-ttu-id="fc5a9-149">![异步方案](../../../../../docs/framework/wcf/diagnostics/tracing/media/asynccallback1.gif "AsyncCallback1")</span><span class="sxs-lookup"><span data-stu-id="fc5a9-149">![Asynchronous scenarios](../../../../../docs/framework/wcf/diagnostics/tracing/media/asynccallback1.gif "AsyncCallback1")</span></span>  
  
 <span data-ttu-id="fc5a9-150">图 5。</span><span class="sxs-lookup"><span data-stu-id="fc5a9-150">Figure 5.</span></span> <span data-ttu-id="fc5a9-151">执行回调、并在回调过程中调用 `endCall` 的异步客户端</span><span class="sxs-lookup"><span data-stu-id="fc5a9-151">Asynchronous client with callback, `endCall` in Callback</span></span>  
  
 <span data-ttu-id="fc5a9-152">![异步方案](../../../../../docs/framework/wcf/diagnostics/tracing/media/asynccallback2.gif "AsyncCallback2")</span><span class="sxs-lookup"><span data-stu-id="fc5a9-152">![Asynchronous Scenarios](../../../../../docs/framework/wcf/diagnostics/tracing/media/asynccallback2.gif "AsyncCallback2")</span></span>  
  
 <span data-ttu-id="fc5a9-153">图 6。</span><span class="sxs-lookup"><span data-stu-id="fc5a9-153">Figure 6.</span></span> <span data-ttu-id="fc5a9-154">执行回调、并在回调过程之外调用 `endCall` 的异步客户端</span><span class="sxs-lookup"><span data-stu-id="fc5a9-154">Asynchronous client with callback, `endCall` outside of Callback</span></span>  
  
### <a name="asynchronous-server-with-callback"></a><span data-ttu-id="fc5a9-155">执行回调的异步服务器</span><span class="sxs-lookup"><span data-stu-id="fc5a9-155">Asynchronous Server with Callback</span></span>  
 <span data-ttu-id="fc5a9-156">![使用 HTTP 的异步方案&#47;TCP&#47;命名&#45;管道](../../../../../docs/framework/wcf/diagnostics/tracing/media/aynchserver.gif "AynchServer")</span><span class="sxs-lookup"><span data-stu-id="fc5a9-156">![Asynchronous scenarios using HTTP&#47;TCP&#47; Named&#45;Pipe](../../../../../docs/framework/wcf/diagnostics/tracing/media/aynchserver.gif "AynchServer")</span></span>  
  
 <span data-ttu-id="fc5a9-157">图 7。</span><span class="sxs-lookup"><span data-stu-id="fc5a9-157">Figure 7.</span></span> <span data-ttu-id="fc5a9-158">执行回调的异步服务器</span><span class="sxs-lookup"><span data-stu-id="fc5a9-158">Asynchronous server, with callback</span></span>  
  
 <span data-ttu-id="fc5a9-159">通道堆栈在消息接收过程中回调客户端：对此处理的跟踪在 ProcessRequest 活动本身中发出。</span><span class="sxs-lookup"><span data-stu-id="fc5a9-159">The channel stack calls back the client on Message Receive: traces for this processing are emitted in the ProcessRequest activity itself.</span></span>  
  
## <a name="asynchronous-requestreply-with-errors"></a><span data-ttu-id="fc5a9-160">发生错误的异步请求/答复</span><span class="sxs-lookup"><span data-stu-id="fc5a9-160">Asynchronous Request/Reply with Errors</span></span>  
 <span data-ttu-id="fc5a9-161">在 `endCall` 过程中接收到错误消息错误。</span><span class="sxs-lookup"><span data-stu-id="fc5a9-161">Fault message errors are received during `endCall`.</span></span> <span data-ttu-id="fc5a9-162">否则，活动和传输应与上面的方案类似。</span><span class="sxs-lookup"><span data-stu-id="fc5a9-162">Otherwise, activities and transfers are similar to previous scenarios.</span></span>  
  
## <a name="asynchronous-one-way-with-or-without-errors"></a><span data-ttu-id="fc5a9-163">发生错误或未发生错误的异步单向方案</span><span class="sxs-lookup"><span data-stu-id="fc5a9-163">Asynchronous One-Way with or without Errors</span></span>  
 <span data-ttu-id="fc5a9-164">不会向客户端返回任何响应或错误。</span><span class="sxs-lookup"><span data-stu-id="fc5a9-164">No response or fault is returned to the client.</span></span>
