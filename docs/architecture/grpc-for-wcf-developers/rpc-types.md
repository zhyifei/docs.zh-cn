---
title: 适用于 WCF 开发人员的 gRPC 类型
description: 查看 WCF 支持的远程过程调用的类型以及它们在 gRPC 中的等效项
ms.date: 09/02/2019
ms.openlocfilehash: 58f097bac61395e6810155e8ae9a6bbf2219ec5e
ms.sourcegitcommit: 515469828d0f040e01bde01df6b8e4eb43630b06
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2020
ms.locfileid: "78675158"
---
# <a name="types-of-rpc"></a><span data-ttu-id="65bd5-103">RPC 类型</span><span class="sxs-lookup"><span data-stu-id="65bd5-103">Types of RPC</span></span>

<span data-ttu-id="65bd5-104">作为 Windows Communication Foundation （WCF）开发人员，你可能习惯于处理以下类型的远程过程调用（RPC）：</span><span class="sxs-lookup"><span data-stu-id="65bd5-104">As a Windows Communication Foundation (WCF) developer, you're probably used to dealing with the following types of remote procedure call (RPC):</span></span>

- <span data-ttu-id="65bd5-105">请求/答复</span><span class="sxs-lookup"><span data-stu-id="65bd5-105">Request/reply</span></span>
- <span data-ttu-id="65bd5-106">模式</span><span class="sxs-lookup"><span data-stu-id="65bd5-106">Duplex:</span></span>
  - <span data-ttu-id="65bd5-107">会话的单向双工</span><span class="sxs-lookup"><span data-stu-id="65bd5-107">One-way duplex with session</span></span>
  - <span data-ttu-id="65bd5-108">带会话的全双工</span><span class="sxs-lookup"><span data-stu-id="65bd5-108">Full duplex with session</span></span>
- <span data-ttu-id="65bd5-109">单向</span><span class="sxs-lookup"><span data-stu-id="65bd5-109">One-way</span></span>

<span data-ttu-id="65bd5-110">可以非常自然地将这些 RPC 类型映射到现有的 gRPC 概念。</span><span class="sxs-lookup"><span data-stu-id="65bd5-110">It's possible to map these RPC types fairly naturally to existing gRPC concepts.</span></span> <span data-ttu-id="65bd5-111">本章将依次介绍每个区域。</span><span class="sxs-lookup"><span data-stu-id="65bd5-111">This chapter will look at each of these areas in turn.</span></span> <span data-ttu-id="65bd5-112">[第5章](migrate-wcf-to-grpc.md)将更深入地探讨相似的示例。</span><span class="sxs-lookup"><span data-stu-id="65bd5-112">[Chapter 5](migrate-wcf-to-grpc.md) will explore similar examples in greater depth.</span></span>

| <span data-ttu-id="65bd5-113">WCF</span><span class="sxs-lookup"><span data-stu-id="65bd5-113">WCF</span></span> | <span data-ttu-id="65bd5-114">gRPC</span><span class="sxs-lookup"><span data-stu-id="65bd5-114">gRPC</span></span> |
| --- | ---- |
| <span data-ttu-id="65bd5-115">常规请求/答复</span><span class="sxs-lookup"><span data-stu-id="65bd5-115">Regular request/reply</span></span> | <span data-ttu-id="65bd5-116">一元</span><span class="sxs-lookup"><span data-stu-id="65bd5-116">Unary</span></span> |
| <span data-ttu-id="65bd5-117">使用客户端回调接口进行会话的双工服务</span><span class="sxs-lookup"><span data-stu-id="65bd5-117">Duplex service with session using a client callback interface</span></span> | <span data-ttu-id="65bd5-118">服务器流式处理</span><span class="sxs-lookup"><span data-stu-id="65bd5-118">Server streaming</span></span> |
| <span data-ttu-id="65bd5-119">带会话的全双工服务</span><span class="sxs-lookup"><span data-stu-id="65bd5-119">Full duplex service with session</span></span> | <span data-ttu-id="65bd5-120">双向流式处理</span><span class="sxs-lookup"><span data-stu-id="65bd5-120">Bidirectional streaming</span></span> |
| <span data-ttu-id="65bd5-121">单向操作</span><span class="sxs-lookup"><span data-stu-id="65bd5-121">One-way operations</span></span> | <span data-ttu-id="65bd5-122">客户端流式处理</span><span class="sxs-lookup"><span data-stu-id="65bd5-122">Client streaming</span></span> |

## <a name="requestreply"></a><span data-ttu-id="65bd5-123">请求/答复</span><span class="sxs-lookup"><span data-stu-id="65bd5-123">Request/reply</span></span>

<span data-ttu-id="65bd5-124">对于采用并返回少量数据的简单请求/回复方法，请使用一元 RPC 的最简单的 gRPC 模式。</span><span class="sxs-lookup"><span data-stu-id="65bd5-124">For simple request/reply methods that take and return small amounts of data, use the simplest gRPC pattern, the unary RPC.</span></span>

```protobuf
service Things {
    rpc Get(GetThingRequest) returns (GetThingResponse);
}
```

```csharp
public class ThingService : Things.ThingsBase
{
    public override async Task<GetThingResponse> Get(GetThingRequest request, ServerCallContext context)
    {
        // Get thing from database
        return new GetThingResponse { Thing = thing };
    }
}
```

```csharp
public async Task ShowThing(int thingId)
{
    var thing = await _thingsClient.GetAsync(new GetThingRequest { ThingId = thingId });
    Console.WriteLine($"{thing.Name}");
}
```

<span data-ttu-id="65bd5-125">如您所见，实现 gRPC 一元 RPC 服务方法与实现 WCF 操作类似。</span><span class="sxs-lookup"><span data-stu-id="65bd5-125">As you can see, implementing a gRPC unary RPC service method is similar to implementing a WCF operation.</span></span> <span data-ttu-id="65bd5-126">不同之处在于，使用 gRPC 时，可以重写基类方法，而不是实现接口。</span><span class="sxs-lookup"><span data-stu-id="65bd5-126">The difference is that with gRPC, you override a base class method instead of implementing an interface.</span></span> <span data-ttu-id="65bd5-127">在服务器上，gRPC 基方法始终返回 <xref:System.Threading.Tasks.Task%601>，尽管客户端同时提供异步和阻塞方法来调用服务。</span><span class="sxs-lookup"><span data-stu-id="65bd5-127">On the server, gRPC base methods always return <xref:System.Threading.Tasks.Task%601>, although the client provides both async and blocking methods to call the service.</span></span>

## <a name="wcf-duplex-one-way-to-client"></a><span data-ttu-id="65bd5-128">WCF 双工，一种对客户端的方法</span><span class="sxs-lookup"><span data-stu-id="65bd5-128">WCF duplex, one way to client</span></span>

<span data-ttu-id="65bd5-129">WCF 应用程序（具有某些绑定）可以在客户端和服务器之间创建持久性连接。</span><span class="sxs-lookup"><span data-stu-id="65bd5-129">WCF applications (with certain bindings) can create a persistent connection between client and server.</span></span> <span data-ttu-id="65bd5-130">在连接关闭之前，服务器可以通过使用 <xref:System.ServiceModel.ServiceContractAttribute.CallbackContract%2A?displayProperty=nameWithType> 属性中指定的*回调接口*，将数据异步发送到客户端。</span><span class="sxs-lookup"><span data-stu-id="65bd5-130">The server can asynchronously send data to the client until the connection is closed, by using a *callback interface* specified in the <xref:System.ServiceModel.ServiceContractAttribute.CallbackContract%2A?displayProperty=nameWithType> property.</span></span>

<span data-ttu-id="65bd5-131">gRPC services 提供类似于消息流的功能。</span><span class="sxs-lookup"><span data-stu-id="65bd5-131">gRPC services provide similar functionality with message streams.</span></span> <span data-ttu-id="65bd5-132">流在实现方面并不*完全*映射到 WCF 双工服务，但你可以获得相同的结果。</span><span class="sxs-lookup"><span data-stu-id="65bd5-132">Streams don't map *exactly* to WCF duplex services in terms of implementation, but you can achieve the same results.</span></span>

### <a name="grpc-streaming"></a><span data-ttu-id="65bd5-133">gRPC 流式处理</span><span class="sxs-lookup"><span data-stu-id="65bd5-133">gRPC streaming</span></span>

<span data-ttu-id="65bd5-134">gRPC 支持从客户端到服务器以及从服务器到客户端创建持久流。</span><span class="sxs-lookup"><span data-stu-id="65bd5-134">gRPC supports the creation of persistent streams from client to server, and from server to client.</span></span> <span data-ttu-id="65bd5-135">这两种类型的流可以同时处于活动状态。</span><span class="sxs-lookup"><span data-stu-id="65bd5-135">Both types of stream can be active concurrently.</span></span> <span data-ttu-id="65bd5-136">此功能称为双向流式处理。</span><span class="sxs-lookup"><span data-stu-id="65bd5-136">This ability is called bidirectional streaming.</span></span> 

<span data-ttu-id="65bd5-137">可以将流用于一段时间内的任意异步消息传送。</span><span class="sxs-lookup"><span data-stu-id="65bd5-137">You can use streams for arbitrary, asynchronous messaging over time.</span></span> <span data-ttu-id="65bd5-138">也可以将其用于传递太大的数据集，以便在单个请求或响应中生成和发送。</span><span class="sxs-lookup"><span data-stu-id="65bd5-138">Or you can use them for passing large datasets that are too big to generate and send in a single request or response.</span></span>

<span data-ttu-id="65bd5-139">下面的示例演示了一个服务器流 RPC。</span><span class="sxs-lookup"><span data-stu-id="65bd5-139">The following example shows a server-streaming RPC.</span></span>

```protobuf
service ClockStreamer {
    rpc Subscribe(ClockSubscribeRequest) returns (stream ClockMessage);
}
```

```csharp
public class ClockStreamerService : ClockStreamer.ClockStreamerBase
{
    public override async Task Subscribe(ClockSubscribeRequest request,
        IServerStreamWriter<ClockMessage> responseStream,
        ServerCallContext context)
    {
        while (!context.CancellationToken.IsCancellationRequested)
        {
            var time = DateTimeOffset.UtcNow;
            await responseStream.WriteAsync(new ClockMessage { message = $"The time is {time:t}." });
            await Task.Delay(TimeSpan.FromSeconds(10), context.CancellationToken);
        }
    }
}
```

<span data-ttu-id="65bd5-140">此服务器流可以从客户端应用程序使用，如以下代码所示：</span><span class="sxs-lookup"><span data-stu-id="65bd5-140">This server stream can be consumed from a client application, as shown in the following code:</span></span>

```csharp
public async Task TellTheTimeAsync(CancellationToken token)
{
    var channel = GrpcChannel.ForAddress("https://localhost:5001");
    var client = new ClockStreamer.ClockStreamerClient(channel);

    var request = new ClockSubscribeRequest();
    var response = client.Subscribe(request);

    await foreach (var update in response.ResponseStream.ReadAllAsync(token))
    {
        Console.WriteLine(update.Message);
    }
}
```

> [!NOTE]
> <span data-ttu-id="65bd5-141">服务器流 Rpc 适用于订阅样式服务。</span><span class="sxs-lookup"><span data-stu-id="65bd5-141">Server-streaming RPCs are useful for subscription-style services.</span></span> <span data-ttu-id="65bd5-142">如果在内存中生成整个数据集的效率低下或不可能，则它们也适用于发送大型数据集。</span><span class="sxs-lookup"><span data-stu-id="65bd5-142">They're also useful for sending large datasets when it would be inefficient or impossible to build the entire dataset in memory.</span></span> <span data-ttu-id="65bd5-143">但是，流响应的速度不如在单个消息中发送 `repeated` 字段快。</span><span class="sxs-lookup"><span data-stu-id="65bd5-143">However, streaming responses isn't as fast as sending `repeated` fields in a single message.</span></span> <span data-ttu-id="65bd5-144">作为一种规则，流不应用于小型数据集。</span><span class="sxs-lookup"><span data-stu-id="65bd5-144">As a rule, streaming shouldn't be used for small datasets.</span></span>

### <a name="differences-from-wcf"></a><span data-ttu-id="65bd5-145">与 WCF 的差异</span><span class="sxs-lookup"><span data-stu-id="65bd5-145">Differences from WCF</span></span>

<span data-ttu-id="65bd5-146">WCF 双工服务使用可具有多个方法的客户端回调接口。</span><span class="sxs-lookup"><span data-stu-id="65bd5-146">A WCF duplex service uses a client callback interface that can have multiple methods.</span></span> <span data-ttu-id="65bd5-147">GRPC 服务器流式处理服务只能通过单个流发送消息。</span><span class="sxs-lookup"><span data-stu-id="65bd5-147">A gRPC server-streaming service can only send messages over a single stream.</span></span> <span data-ttu-id="65bd5-148">如果需要多个方法，请将消息类型与[Any 字段或字段之一](protobuf-any-oneof.md)一起使用，以发送不同的消息，并在客户端中编写代码来处理这些消息。</span><span class="sxs-lookup"><span data-stu-id="65bd5-148">If you need multiple methods, use a message type with either [an Any field or a oneof field](protobuf-any-oneof.md) to send different messages, and write code in the client to handle them.</span></span>

<span data-ttu-id="65bd5-149">在 WCF 中，具有会话的[ServiceContract](xref:System.ServiceModel.ServiceContractAttribute)类保持活动状态，直到关闭连接。</span><span class="sxs-lookup"><span data-stu-id="65bd5-149">In WCF, the [ServiceContract](xref:System.ServiceModel.ServiceContractAttribute) class with the session is kept alive until the connection is closed.</span></span> <span data-ttu-id="65bd5-150">可以在会话中调用多个方法。</span><span class="sxs-lookup"><span data-stu-id="65bd5-150">Multiple methods can be called within the session.</span></span> <span data-ttu-id="65bd5-151">在 gRPC 中，实现方法返回的 `Task` 不应完成，直到关闭连接。</span><span class="sxs-lookup"><span data-stu-id="65bd5-151">In gRPC, the `Task` that the implementation method returns shouldn't finish until the connection is closed.</span></span>

## <a name="wcf-one-way-operations-and-grpc-client-streaming"></a><span data-ttu-id="65bd5-152">WCF 单向操作和 gRPC 客户端流式处理</span><span class="sxs-lookup"><span data-stu-id="65bd5-152">WCF one-way operations and gRPC client streaming</span></span>

<span data-ttu-id="65bd5-153">WCF 提供返回传输特定确认的单向操作（标记为 `[OperationContract(IsOneWay = true)]`）。</span><span class="sxs-lookup"><span data-stu-id="65bd5-153">WCF provides one-way operations (marked with `[OperationContract(IsOneWay = true)]`) that return a transport-specific acknowledgement.</span></span> <span data-ttu-id="65bd5-154">gRPC 服务方法始终返回响应，即使它为空也是如此。</span><span class="sxs-lookup"><span data-stu-id="65bd5-154">gRPC service methods always return a response, even if it's empty.</span></span> <span data-ttu-id="65bd5-155">客户端应始终等待该响应。</span><span class="sxs-lookup"><span data-stu-id="65bd5-155">The client should always await that response.</span></span> <span data-ttu-id="65bd5-156">对于 gRPC 中的消息传递 "暂时" 样式，您可以创建客户端流式处理服务。</span><span class="sxs-lookup"><span data-stu-id="65bd5-156">For the "fire-and-forget" style of messaging in gRPC, you can create a client streaming service.</span></span>

### <a name="thing_logproto"></a><span data-ttu-id="65bd5-157">thing_log proto</span><span class="sxs-lookup"><span data-stu-id="65bd5-157">thing_log.proto</span></span>

```protobuf
service ThingLog {
  rpc OpenConnection(stream Thing) returns (ConnectionClosedResponse);
}
```

### <a name="thinglogservicecs"></a><span data-ttu-id="65bd5-158">ThingLogService.cs</span><span class="sxs-lookup"><span data-stu-id="65bd5-158">ThingLogService.cs</span></span>

```csharp
public class ThingLogService : Protos.ThingLog.ThingLogBase
{
    private static readonly ConnectionClosedResponse EmptyResponse = new ConnectionClosedResponse();
    private readonly ILogger<ThingLogService> _logger;
    public ThingLogService(ILogger<ThingLogService> logger)
    {
        _logger = logger;
    }

    public override async Task<CompletedResponse> OpenConnection(IAsyncStreamReader<Thing> requestStream, ServerCallContext context)
    {
        while (await requestStream.MoveNext(context.CancellationToken))
        {
            _logger.LogInformation(requestStream.Current.Description);
        }
        return EmptyResponse;
    }
}
```

### <a name="thinglog-client-example"></a><span data-ttu-id="65bd5-159">ThingLog 客户端示例</span><span class="sxs-lookup"><span data-stu-id="65bd5-159">ThingLog client example</span></span>

```csharp
public class ThingLogger : IAsyncDisposable
{
    private readonly ThingLog.ThingLogClient _client;
    private readonly AsyncClientStreamingCall<ThingLogRequest, CompletedResponse> _stream;

    public ThingLogger(ThingLog.ThingLogClient client)
    {
        _client = client;
        _stream = client.OpenConnection();
    }

    public async Task WriteAsync(string description)
    {
        await _stream.RequestStream.WriteAsync(new Thing
        {
            Description = description,
            Time = Timestamp.FromDateTimeOffset(DateTimeOffset.UtcNow)
        });
    }

    public async ValueTask DisposeAsync()
    {
        await _stream.RequestStream.CompleteAsync();
        _stream.Dispose();
    }
}
```

<span data-ttu-id="65bd5-160">如前面的示例所示，可以将客户端流式处理 Rpc 用于暂时消息消息处理。</span><span class="sxs-lookup"><span data-stu-id="65bd5-160">You can use client-streaming RPCs for fire-and-forget messaging, as shown in the previous example.</span></span> <span data-ttu-id="65bd5-161">你还可以使用它们向服务器发送非常大的数据集。</span><span class="sxs-lookup"><span data-stu-id="65bd5-161">You can also use them for sending very large datasets to the server.</span></span> <span data-ttu-id="65bd5-162">适用于性能的相同警告：对于较小的数据集，请使用 `repeated` 常规消息中的字段。</span><span class="sxs-lookup"><span data-stu-id="65bd5-162">The same warning about performance applies: for smaller datasets, use `repeated` fields in regular messages.</span></span>

## <a name="wcf-full-duplex-services"></a><span data-ttu-id="65bd5-163">WCF 全双工服务</span><span class="sxs-lookup"><span data-stu-id="65bd5-163">WCF full-duplex services</span></span>

<span data-ttu-id="65bd5-164">在服务接口和客户端回调接口上，WCF 双工绑定支持多个单向操作。</span><span class="sxs-lookup"><span data-stu-id="65bd5-164">WCF duplex binding supports multiple one-way operations on both the service interface and the client callback interface.</span></span> <span data-ttu-id="65bd5-165">此支持允许在客户端和服务器之间进行正在进行的会话。</span><span class="sxs-lookup"><span data-stu-id="65bd5-165">This support allows ongoing conversations between client and server.</span></span> <span data-ttu-id="65bd5-166">gRPC 支持类似于双向流式处理 Rpc 的内容，其中，两个参数都标记有 `stream` 修饰符。</span><span class="sxs-lookup"><span data-stu-id="65bd5-166">gRPC supports something similar with bidirectional streaming RPCs, where both parameters are marked with the `stream` modifier.</span></span>

### <a name="chatproto"></a><span data-ttu-id="65bd5-167">chat</span><span class="sxs-lookup"><span data-stu-id="65bd5-167">chat.proto</span></span>

```protobuf
service Chatter {
    rpc Connect(stream IncomingMessage) returns (stream OutgoingMessage);
}
```

### <a name="chatterservicecs"></a><span data-ttu-id="65bd5-168">ChatterService.cs</span><span class="sxs-lookup"><span data-stu-id="65bd5-168">ChatterService.cs</span></span>

```csharp
public class ChatterService : Chatter.ChatterBase
{
    private readonly IChatHub _hub;

    public ChatterService(IChatHub hub)
    {
        _hub = hub;
    }

    public override async Task Connect(IAsyncStreamReader<MessageRequest> requestStream, IServerStreamWriter<MessageResponse> responseStream, ServerCallContext context)
    {
        _hub.MessageReceived += async (sender, args) =>
            await responseStream.WriteAsync(new MessageResponse {Text = args.Message});

        while (await requestStream.MoveNext(context.CancellationToken))
        {
            await _hub.SendAsync(requestStream.Current.Text);
        }
    }
}
```

<span data-ttu-id="65bd5-169">在上面的示例中，你可以看到，实现方法收到请求流（`IAsyncStreamReader<MessageRequest>`）和响应流（`IServerStreamWriter<MessageResponse>`）。</span><span class="sxs-lookup"><span data-stu-id="65bd5-169">In the previous example, you can see that the implementation method receives both a request stream (`IAsyncStreamReader<MessageRequest>`) and a response stream (`IServerStreamWriter<MessageResponse>`).</span></span> <span data-ttu-id="65bd5-170">方法可以读取和写入消息，直到关闭连接。</span><span class="sxs-lookup"><span data-stu-id="65bd5-170">The method can read and write messages until the connection is closed.</span></span>

### <a name="chatter-client"></a><span data-ttu-id="65bd5-171">Chatter 客户端</span><span class="sxs-lookup"><span data-stu-id="65bd5-171">Chatter client</span></span>

```csharp
public class Chat : IAsyncDisposable
{
    private readonly Chatter.ChatterClient _client;
    private readonly AsyncDuplexStreamingCall<MessageRequest, MessageResponse> _stream;
    private readonly CancellationTokenSource _cancellationTokenSource;
    private readonly Task _readTask;

    public Chat(Chatter.ChatterClient client)
    {
        _client = client;
        _stream = _client.Connect();
        _cancellationTokenSource = new CancellationTokenSource();
        _readTask = ReadAsync(_cancellationTokenSource.Token);
    }

    public async Task SendAsync(string message)
    {
        await _stream.RequestStream.WriteAsync(new MessageRequest {Text = message});
    }

    private async Task ReadAsync(CancellationToken token)
    {
        while (await _stream.ResponseStream.MoveNext(token))
        {
            Console.WriteLine(_stream.ResponseStream.Current.Text);
        }
    }

    public async ValueTask DisposeAsync()
    {
        await _stream.RequestStream.CompleteAsync();
        await _readTask;
        _stream.Dispose();
    }
}
```

>[!div class="step-by-step"]
><span data-ttu-id="65bd5-172">[上一页](wcf-bindings.md)
>[下一页](metadata.md)</span><span class="sxs-lookup"><span data-stu-id="65bd5-172">[Previous](wcf-bindings.md)
[Next](metadata.md)</span></span>
