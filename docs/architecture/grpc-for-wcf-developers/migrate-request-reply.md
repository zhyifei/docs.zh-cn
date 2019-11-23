---
title: 将 WCF 请求-答复服务迁移到 WCF 开发人员的 gRPC-gRPC
description: 了解如何将简单的请求-答复服务从 WCF 迁移到 gRPC。
ms.date: 09/02/2019
ms.openlocfilehash: f0b20e7b374438f90d83aebc6035a4e4dd94ae18
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/12/2019
ms.locfileid: "73971783"
---
# <a name="migrate-a-wcf-request-reply-service-to-a-grpc-unary-rpc"></a>将 WCF 请求-答复服务迁移到 gRPC 一元 RPC

本部分介绍如何将 WCF 中的基本请求-答复服务迁移到 ASP.NET Core gRPC 中的一元 RPC 服务。 这些服务是 Windows Communication Foundation （WCF）和 gRPC 中的最简单服务类型，因此，这是一个很好的起点。 迁移服务后，你将了解如何从同一 `.proto` 文件生成客户端库，以便从 .NET 客户端应用程序使用该服务。

## <a name="the-wcf-solution"></a>WCF 解决方案

[PortfoliosSample 解决方案](https://github.com/dotnet-architecture/grpc-for-wcf-developers/tree/master/PortfoliosSample/wcf/TraderSys)包括一个简单的请求-答复项目组合服务，可下载单个组合或给定交易的所有包。 服务在接口 `IPortfolioService` 中使用 `ServiceContract` 属性定义：

```csharp
[ServiceContract]
public interface IPortfolioService
{
    [OperationContract]
    Task<Portfolio> Get(Guid traderId, int portfolioId);

    [OperationContract]
    Task<List<Portfolio>> GetAll(Guid traderId);
}
```

`Portfolio` 模型是一个用C# [DataContract](xref:System.Runtime.Serialization.DataContractAttribute)标记的简单类，其中包括 `PortfolioItem` 对象的列表。 这些模型是在 `TraderSys.PortfolioData` 项目中定义的，以及一个表示数据访问抽象的存储库类。

```csharp
[DataContract]
public class Portfolio
{
    [DataMember]
    public int Id { get; set; }

    [DataMember]
    public Guid TraderId { get; set; }

    [DataMember]
    public List<PortfolioItem> Items { get; set; }
}

[DataContract]
public class PortfolioItem
{
    [DataMember]
    public int Id { get; set; }

    [DataMember]
    public int ShareId { get; set; }

    [DataMember]
    public int Holding { get; set; }

    [DataMember]
    public decimal Cost { get; set; }
}
```

`ServiceContract` 实现使用通过依赖关系注入提供的存储库类，该依赖项注入返回 `DataContract` 类型的实例。

```csharp
public class PortfolioService : IPortfolioService
{
    private readonly IPortfolioRepository _repository;

    public PortfolioService(IPortfolioRepository repository)
    {
        _repository = repository;
    }

    public async Task<Portfolio> Get(Guid traderId, int portfolioId)
    {
        return await _repository.GetAsync(traderId, portfolioId);
    }

    public async Task<List<Portfolio>> GetAll(Guid traderId)
    {
        return await _repository.GetAllAsync(traderId);
    }
}
```

## <a name="the-portfoliosproto-file"></a>包 proto 文件

如果按照上一部分中的说明进行操作，则应具有一个 gRPC 项目，其中包含如下所示的 `portfolios.proto` 文件。

```protobuf
syntax = "proto3";

option csharp_namespace = "TraderSys.Portfolios.Protos";

package PortfolioServer;

service Portfolios {
  // RPCs will go here
}
```

第一步是将 `DataContract` 类迁移到它们的 Protobuf 等效项。

## <a name="convert-the-datacontracts-to-grpc-messages"></a>将 DataContracts 转换为 gRPC 消息

`PortfolioItem` 类将首先转换为 Protobuf 消息，因为 `Portfolio` 类依赖于它。 类非常简单，并且三个属性直接映射到 gRPC 数据类型。 `Cost` 属性表示购买的股票的价格，它是一个 `decimal` 字段，而 gRPC 仅支持 `float` 或 `double` 对于不适用于货币的实数。 由于共享价格相差至少为1美分，因此成本可表示为 `int32` 美分。

> [!NOTE]
> 请记住使用 `.proto` 文件中字段名称的 `camelCase`;C#代码生成器会将它们转换为 `PascalCase`，而其他语言的用户则感谢您遵从它们的不同编码标准。

```protobuf
message PortfolioItem {
    int32 id = 1;
    int32 share_id = 2;
    int32 holding = 3;
    int32 cost_cents = 4;
}
```

`Portfolio` 类稍微复杂一些。 在 WCF 代码中，开发人员使用 `TraderId` 属性的 `Guid`，并包含 `List<PortfolioItem>`。 在 Protobuf 中没有第一类 `UUID` 类型的情况下，应将 `string` 用于 `traderId` 字段，并在自己的代码中对其进行分析。 对于项列表，请对字段使用 `repeated` 关键字。

```protobuf
message Portfolio {
    int32 id = 1;
    string trader_id = 2;
    repeated PortfolioItem items = 3;
}
```

现在我们有了数据消息，可以声明服务 RPC 终结点。

## <a name="convert-the-servicecontract-to-a-grpc-service"></a>将 ServiceContract 转换为 gRPC 服务

WCF `Get` 方法使用两个参数： `Guid traderId` 和 `int portfolioId`。 gRPC 服务方法只能采用单个参数，因此必须创建消息来保存这两个值。 常见的做法是将这些请求对象命名为与方法相同的名称，并 `Request`后缀。 同样，`string` 用于 `traderId` 字段，而不是 `Guid`。

该服务只是直接返回 `Portfolio` 消息，但这可能会影响将来的后向兼容性。 最好为服务中的每个方法定义单独的 `Request` 和 `Response` 消息，即使它们现在很多都是相同的，因此请使用单个 `Portfolio` 字段声明 `GetResponse` 消息。

下面的示例演示如何使用 `GetRequest` 消息声明 gRPC 服务方法：

```protobuf
message GetRequest {
    string trader_id = 1;
    int32 portfolio_id = 2;
}

message GetResponse {
    Portfolio portfolio = 1;
}

service Portfolios {
    rpc Get(GetRequest) returns (GetResponse);
}
```

WCF `GetAll` 方法只使用单个参数，`traderId`，因此，它可能看起来可以将 `string` 指定为参数类型，但 gRPC 需要定义的消息类型。 此要求可帮助强制执行将自定义消息用于所有输入和输出的操作，以便将来能够向后兼容。

WCF 方法还返回 `List<Portfolio>`，但出于同一原因，它不允许简单参数类型，gRPC 不允许 `repeated Portfolio` 作为返回类型。 而应创建一个 `GetAllResponse` 类型来包装列表。

> [!WARNING]
> 您可能会想创建一个 `PortfolioList` 消息或类似的消息，并跨多个服务方法使用它，但您应该不能做到这一点。 不可能知道服务的各种方法在将来如何发展，因此请使其消息保持特定和明确的隔离。

```protobuf
message GetAllRequest {
    string trader_id = 1;
}

message PortfolioList {
    repeated Portfolio portfolios = 1;
}

service Portfolios {
    rpc Get(GetRequest) returns (Portfolio);
    rpc GetAll(GetAllRequest) returns (GetAllResponse);
}
```

如果你使用这些更改保存你的项目，则 gRPC 生成目标将在后台运行并生成所有 Protobuf 消息类型以及可继承以实现该服务的基类。

打开 `Services/GreeterService.cs` 类并删除示例代码。 现在，你可以添加项目组合服务实现。 生成的基类将位于 `Protos` 命名空间中，并以嵌套类的形式生成。 gRPC 创建一个与 `.proto` 文件中的服务同名的静态类，然后在该静态类内创建一个具有后缀 `Base` 的基类，因此基类型的完整标识符 `TraderSys.Portfolios.Protos.Portfolios.PortfoliosBase`。

```csharp
namespace TraderSys.Portfolios.Services
{
    public class PortfolioService : Protos.Portfolios.PortfoliosBase
    {
    }
}
```

基类声明可重写以实现服务 `virtual` 方法 `Get` 和 `GetAll`。 方法是 `virtual` 而不是 `abstract`，因此，如果未实现这些方法，则服务可以返回显式 gRPC `Unimplemented` 状态代码，这与你可以在常规C#代码中引发 `NotImplementedException` 非常类似。

ASP.NET Core 中所有 gRPC 一元服务方法的签名都是一致的。 有两个参数：第一个参数是在 `.proto` 文件中声明的消息类型，第二个参数是类似于 ASP.NET Core 中的 `HttpContext` 的 `ServerCallContext`。 事实上，在 `ServerCallContext` 类上有一个名为 `GetHttpContext` 的扩展方法，您可以使用该方法获取底层 `HttpContext`，不过您不需要经常使用它。 我们将在本章稍后部分以及讨论身份验证一章中介绍 `ServerCallContext`。

此方法的返回类型为 `Task<T>`，其中 `T` 为响应消息类型。 所有 gRPC 服务方法都是异步的。

## <a name="migrate-the-portfoliodata-library-to-net-core"></a>将 PortfolioData 库迁移到 .NET Core

此时，项目需要 WCF 解决方案的 `TraderSys.PortfolioData` 类库中包含的项目组合存储库和模型。 最简单的方法是使用 Visual Studio "**新建项目**" 对话框和 "类库 *（.NET Standard）* " 模板创建一个新的类库，或者使用 .NET Core CLI 从命令行中运行以下命令，从包含 `TraderSys.sln` 文件的目录中运行以下命令。

```dotnetcli
dotnet new classlib -o src/TraderSys.PortfolioData
dotnet sln add src/TraderSys.PortfolioData
```

创建库并将其添加到解决方案后，删除生成的 `Class1.cs` 文件，并将文件从 WCF 解决方案的库复制到新的类库文件夹，同时保留文件夹结构。

```
Models
  Portfolio.cs
  PortfolioItem.cs
IPortfolioRepository.cs
PortfolioRepository.cs
```

SDK 样式的 .NET 项目会自动在其自己的目录中包含任何 `.cs` 文件，因此无需将其显式添加到项目。 剩下的唯一步骤是从 `Portfolio` 和 `PortfolioItem` 类中删除 `DataContract` 和 `DataMember` 属性，使其成为普通旧C#类。

```csharp
public class Portfolio
{
    public int Id { get; set; }
    public Guid TraderId { get; set; }
    public List<PortfolioItem> Items { get; set; }
}

public class PortfolioItem
{
    public int Id { get; set; }
    public int ShareId { get; set; }
    public int Holding { get; set; }
    public decimal Cost { get; set; }
}
```

## <a name="use-aspnet-core-dependency-injection"></a>使用 ASP.NET Core 依赖关系注入

现在可以将对此库的引用添加到 gRPC 应用程序项目，并在 gRPC 服务实现中使用依赖关系注入来使用 `PortfolioRepository` 类。 在 WCF 应用程序中，依赖关系注入由 Autofac IoC 容器提供。 ASP.NET Core 在中具有依赖关系注入融入;可以在 `Startup` 类的 `ConfigureServices` 方法中注册存储库。

```csharp
public class Startup
{
    public void ConfigureServices(IServiceCollection services)
    {
        // Register the repository class as a scoped service (instance per request)
        services.AddScoped<IPortfolioRepository, PortfolioRepository>();

        services.AddGrpc();
    }

    // ...
}
```

现在可以在 `PortfolioService` 类中将 `IPortfolioRepository` 实现指定为构造函数参数，如下所示：

```csharp
public class PortfolioService : Protos.Portfolios.PortfoliosBase
{
    private readonly IPortfolioRepository _repository;

    public PortfolioService(IPortfolioRepository repository)
    {
        _repository = repository;
    }
}
```

## <a name="implement-the-grpc-service"></a>实现 gRPC 服务

现在您已在 `portfolios.proto` 文件中声明了您的消息和服务，您必须在 `PortfolioService` 类中实现从 gRPC 生成的 `Portfolios.PortfoliosBase` 类继承的服务方法。 方法在基类中声明为 `virtual`。 如果不重写这些值，则默认情况下，它们将返回 "未实现" 状态代码 gRPC。

首先实现 `Get` 方法。 默认重写类似于以下示例：

```csharp
public override Task<GetResponse> Get(GetRequest request, ServerCallContext context)
{
    return base.Get(request, context);
}
```

第一个问题是，`request.TraderId` 是一个字符串，并且该服务需要 `Guid`。 即使字符串的预期格式是 `UUID`，代码也必须处理调用方发送了无效值并做出相应响应的可能性。 服务可以通过引发 `RpcException`来响应错误，并使用标准 `InvalidArgument` 状态代码来表示问题。

```csharp
public override Task<GetResponse> Get(GetRequest request, ServerCallContext context)
{
    if (!Guid.TryParse(request.TraderId, out var traderId))
    {
        throw new RpcException(new Status(StatusCode.InvalidArgument, "traderId must be a UUID"));
    }

    return base.Get(request, context);
}
```

为 `traderId`提供适当的 `Guid` 值后，可以使用该存储库检索该组合并将其返回到客户端。

```csharp
    var response = new GetResponse
    {
        Portfolio = await _repository.GetAsync(request.TraderId, request.PortfolioId)
    };
```

### <a name="map-internal-models-to-grpc-messages"></a>将内部模型映射到 gRPC 消息

前面的代码实际上不起作用，因为存储库返回自己的 POCO 模型 `Portfolio`，但 gRPC 需要*其自己的*Protobuf 消息 `Portfolio`。 与将实体框架类型映射到数据传输类型非常相似，最佳解决方案是在两者之间提供转换。 放置此代码的好地方是在 Protobuf 生成的类中，该类声明为一个 `partial` 类，因此可对其进行扩展。

```csharp
namespace TraderSys.Portfolios.Protos
{
    public partial class PortfolioItem
    {
        public static PortfolioItem FromRepositoryModel(PortfolioData.Models.PortfolioItem source)
        {
            if (source is null) return null;

            return new PortfolioItem
            {
                Id = source.Id,
                ShareId = source.ShareId,
                Holding = source.Holding,
                CostCents = (int)(source.Cost * 100)
            };
        }
    }

    public partial class Portfolio
    {
        public static Portfolio FromRepositoryModel(PortfolioData.Models.Portfolio source)
        {
            if (source is null) return null;

            var target = new Portfolio
            {
                Id = source.Id,
                TraderId = source.TraderId.ToString(),
            };

            target.Items.AddRange(source.Items.Select(PortfolioItem.FromRepositoryModel));

            return target;
        }
    }
}
```

> [!NOTE]
> 您可以使用类似[AutoMapper](https://automapper.org/)的库来处理从内部模型类到 Protobuf 类型的这种转换，前提是配置较低级别的类型转换，如 `string`/`Guid` 或 `decimal`/`double` 和列表映射。

转换代码准备就绪后，`Get` 方法实现即可完成。

```csharp
public override async Task<GetResponse> Get(GetRequest request, ServerCallContext context)
{
    if (!Guid.TryParse(request.TraderId, out var traderId))
    {
        throw new RpcException(new Status(StatusCode.InvalidArgument, "traderId must be a UUID"));
    }

    var portfolio = await _repository.GetAsync(traderId, request.PortfolioId);

    return new GetResponse
    {
        Portfolio = Portfolio.FromRepositoryModel(portfolio)
    };
}

```

`GetAll` 方法的实现类似。 请注意，Protobuf 消息上的 `repeated` 字段将作为 `RepeatedField<T>`类型的 `readonly` 属性生成，因此你必须使用 `AddRange` 方法向其中添加项，如以下示例中所示：

```csharp
public override async Task<GetAllResponse> GetAll(GetAllRequest request, ServerCallContext context)
{
    if (!Guid.TryParse(request.TraderId, out var traderId))
    {
        throw new RpcException(new Status(StatusCode.InvalidArgument, "traderId must be a UUID"));
    }

    var portfolios = await _repository.GetAllAsync(traderId);

    var response = new GetAllResponse();
    response.Portfolios.AddRange(portfolios.Select(Portfolio.FromRepositoryModel));

    return response;
}
```

已成功将 WCF 请求-答复服务迁移到 gRPC，我们来看看如何从 `.proto` 文件创建客户端。

## <a name="generate-client-code"></a>生成客户端代码

在同一解决方案中创建 .NET Standard 类库，以包含客户端。 这主要是创建客户端代码的示例，但你可以使用 NuGet 打包此类库，并将其分发到供其他 .NET 团队使用的内部存储库中。 继续并向解决方案添加名为 `TraderSys.Portfolios.Client` 的新 .NET Standard 类库，并删除 `Class1.cs` 文件。

> [!CAUTION]
> [Grpc](https://www.nuget.org/packages/Grpc.Net.Client) NuGet 包需要 .net Core 3.0 （或另 .NET Standard 一个与2.1 兼容的运行时）。 [Grpc](https://www.nuget.org/packages/Grpc.Core) NuGet 包支持早期版本的 .NET FRAMEWORK 和 .net Core。

在 Visual Studio 2019 中，可以添加对 gRPC services 的引用，就像在 Visual Studio 的早期版本中将服务引用添加到 WCF 项目一样。 服务引用和连接的服务现在都是在同一个 UI 下管理的，你可以通过右键单击解决方案资源管理器中 `TraderSys.Portfolios.Client` 项目中的 "**依赖项**" 节点，然后选择 "**添加连接的服务**" 来访问它。 在出现的工具窗口中，选择 "**服务引用**" 部分，然后单击 "**添加新的 gRPC 服务引用**"。

![Visual Studio 2019 中的连接的服务 UI](media/migrate-request-reply/add-connected-service.png)

浏览到 `TraderSys.Portfolios` 项目中的 `portfolios.proto` 文件，将**类的类型**保留为 "**客户端**"，然后单击 **"确定"** 。

![Visual Studio 2019 中的 "添加新的 gRPC 服务引用" 对话框](media/migrate-request-reply/add-new-grpc-service-reference.png)

> [!TIP]
> 请注意，此对话框还提供了 "URL" 字段。 如果你的组织维护 `.proto` 文件的 web 访问目录，你只需通过设置此 URL 地址即可创建客户端。

当使用 Visual Studio 的 "**添加连接服务**" 功能时，`portfolios.proto` 文件将作为*链接文件*添加到类库项目中，而不是复制，因此，对服务项目中的文件所做的更改将自动应用到客户端项目中。 `csproj` 文件中的 `<Protobuf>` 元素如下所示：

```xml
<Protobuf Include="..\TraderSys.Portfolios\Protos\portfolios.proto" GrpcServices="Client">
  <Link>Protos\portfolios.proto</Link>
</Protobuf>
```

> [!TIP]
> 如果使用的不是 Visual Studio 或想要从命令行运行，则可以使用**dotnet-grpc**全局工具来管理 .net grpc 项目中的 Protobuf 引用。 [有关详细信息，请参阅**dotnet-grpc**文档](https://docs.microsoft.com/aspnet/core/grpc/dotnet-grpc)。

### <a name="use-the-portfolios-service-from-a-client-application"></a>使用客户端应用程序中的 "包" 服务

下面的代码是在控制台应用程序中使用生成的客户端的简单示例。 本章末尾详细探讨了 gRPC 客户端代码。

```csharp
public class Program
{
    public async Task Main(string[] args)
    {
        GetResponse response;

        using (var channel = GrpcChannel.ForAddress("https://localhost:5001"))
        {
            var client = new Protos.Portfolios.PortfoliosClient(channel);

            response = await client.GetAsync(new GetRequest
            {
                TraderId = args[0],
                PortfolioId = int.Parse(args[1])
            });
        }

        foreach (var item in response.Portfolio.Items)
        {
            Console.WriteLine($"Holding {item.Holding} of Share ID {item.ShareId}.");
        }
    }
}
```

现在，已将基本 WCF 应用程序迁移到 ASP.NET Core gRPC 服务并创建了客户端，以便从 .NET 应用程序使用该服务。 下一节将介绍更多的 "双工" 服务。

>[!div class="step-by-step"]
>[上一页](create-project.md)
>[下一页](migrate-duplex-services.md)
