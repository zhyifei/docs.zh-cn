---
title: 适用于 WCF 开发人员的 gRPC 类型
description: 查看 WCF 支持的远程过程调用的类型以及它们在 gRPC 中的等效项
author: markrendle
ms.date: 09/02/2019
ms.openlocfilehash: ce5bf03b01dff3f7bb201ff08c9065abc2e58360
ms.sourcegitcommit: 337bdc5a463875daf2cc6883e5a2da97d56f5000
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/24/2019
ms.locfileid: "73841377"
---
# <a name="types-of-rpc"></a>RPC 类型

作为 Windows Communication Foundation （WCF）开发人员，你可能习惯于处理以下类型的远程过程调用（RPC）：

- 请求/答复
- 模式
  - 会话的单向双工
  - 带会话的全双工
- 单向

可以非常自然地将这些 RPC 类型映射到现有的 gRPC 概念，本章将依次查看每个区域。 [第5章](migrate-wcf-to-grpc.md)将更深入地探讨类似的示例。

| WCF | gRPC |
| --- | ---- |
| 常规请求/答复 | 一元 |
| 使用客户端回调接口进行会话的双工服务 | 服务器流式处理 |
| 带会话的全双工服务 | 双向流式处理 |
| 单向操作 | 客户端流式处理 |

## <a name="requestreply"></a>请求/答复

对于采用并返回少量数据的简单请求/回复方法，请使用一元 RPC 的最简单的 gRPC 模式。

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

如您所见，实现 gRPC 一元 RPC 服务方法与实现 WCF 操作非常相似，不同之处在于使用 gRPC 可以重写基类方法而不是实现接口。 请注意，在服务器上，gRPC 基方法始终返回 <xref:System.Threading.Tasks.Task%601>，不过，客户端同时提供 async 和阻塞方法来调用服务。

## <a name="wcf-duplex-one-way-to-client"></a>WCF 双工，客户端单向

WCF 应用程序（具有某些绑定）可以在客户端和服务器之间创建持久性连接，并且在使用 <xref:System.ServiceModel.ServiceContractAttribute.CallbackContract%2A?displayProperty=nameWithType> 属性中指定的*回调接口*关闭连接之前，服务器可以将数据异步发送到客户端。

gRPC services 提供类似于消息流的功能。 流在实现方面并不*完全*映射到 WCF 双工服务，但也可以实现相同的结果。

### <a name="grpc-streaming"></a>gRPC 流式处理

gRPC 支持从客户端到服务器以及从服务器到客户端创建持久流。 这两种类型的流可以同时处于活动状态;这称为双向流式处理。 流可用于随时间推移的任意异步消息传送，或者用于传递太大的数据集，以便在单个请求或响应中生成和发送。

下面的示例演示了服务器流式处理 RPC。

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

此服务器流可以从客户端应用程序使用，如以下代码所示：

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
> 服务器流式处理 Rpc 对于订阅样式服务非常有用，还用于发送非常大的数据集，但在内存中生成整个数据集是低效或可能造成的。 但是，流响应的速度不如在单个消息中发送 `repeated` 字段快，因此，不应将规则流式处理用于小型数据集。

### <a name="differences-to-wcf"></a>与 WCF 的差异

WCF 双工服务使用可具有多个方法的客户端回调接口。 GRPC 服务器流式处理服务只能通过单个流发送消息。 如果需要多个方法，请将消息类型与[Any 字段或字段之一](protobuf-any-oneof.md)一起使用，以发送不同的消息，并在客户端中编写代码来处理这些消息。

在 WCF 中，具有会话的[ServiceContract](xref:System.ServiceModel.ServiceContractAttribute)类将一直保持活动状态，直到关闭连接，并在会话中调用多个方法。 在 gRPC 中，实现方法返回的 `Task` 不应完成，直到关闭连接。

## <a name="wcf-one-way-operations-and-grpc-client-streaming"></a>WCF 单向操作和 gRPC 客户端流式处理

WCF 提供返回传输特定确认的单向操作（标记为 `[OperationContract(IsOneWay = true)]`）。 gRPC 服务方法始终返回响应（即使它是空的），并且客户端应始终等待该响应。 对于 gRPC 中的 "火灾和遗忘" 样式消息，可以创建客户端流式处理服务。

### <a name="thing_logproto"></a>thing_log proto

```protobuf
service ThingLog {
  rpc OpenConnection(stream Thing) returns (ConnectionClosedResponse);
}
```

### <a name="thinglogservicecs"></a>ThingLogService.cs

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

### <a name="thinglog-client-example"></a>ThingLog 客户端示例

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

同样，可以将客户端流式处理 Rpc 用于前面的示例中所示的暂时消息传递 Rpc，还可以将非常大的数据集发送到服务器。 适用于性能的相同警告：对于较小的数据集，请使用 `repeated` 常规消息中的字段。

## <a name="wcf-full-duplex-services"></a>WCF 全双工服务

WCF 双工绑定支持服务接口和客户端回调接口上的多个单向操作，允许在客户端和服务器之间进行正在进行的会话。 gRPC 支持类似于双向流式处理 Rpc 的内容，其中，两个参数都标记有 `stream` 修饰符。

### <a name="chatproto"></a>chat

```protobuf
service Chatter {
    rpc Connect(stream IncomingMessage) returns (stream OutgoingMessage);
}
```

### <a name="chatterservicecs"></a>ChatterService.cs

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

在上面的示例中，你可以看到，实现方法接收请求流（`IAsyncStreamReader<MessageRequest>`）和响应流（`IServerStreamWriter<MessageResponse>`），并可以在连接关闭之前读取和写入消息。

### <a name="chatter-client"></a>Chatter 客户端

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
>[上一页](wcf-bindings.md)
>[下一页](metadata.md)
