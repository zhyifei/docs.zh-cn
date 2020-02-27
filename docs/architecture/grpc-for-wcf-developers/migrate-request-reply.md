---
title: 将 WCF 请求-答复服务迁移到 WCF 开发人员的 gRPC-gRPC
description: 了解如何将简单的请求-答复服务从 WCF 迁移到 gRPC。
ms.date: 09/02/2019
ms.openlocfilehash: 018aa94a15cdcb1e0f559afb7b3a88cd4f915398
ms.sourcegitcommit: 44a7cd8687f227fc6db3211ccf4783dc20235e51
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/26/2020
ms.locfileid: "77628548"
---
# <a name="migrate-a-wcf-request-reply-service-to-a-grpc-unary-rpc"></a><span data-ttu-id="bdcfd-103">将 WCF 请求-答复服务迁移到 gRPC 一元 RPC</span><span class="sxs-lookup"><span data-stu-id="bdcfd-103">Migrate a WCF request-reply service to a gRPC unary RPC</span></span>

<span data-ttu-id="bdcfd-104">本部分介绍如何将 WCF 中的基本请求-答复服务迁移到 ASP.NET Core gRPC 中的一元 RPC 服务。</span><span class="sxs-lookup"><span data-stu-id="bdcfd-104">This section covers how to migrate a basic request-reply service in WCF to a unary RPC service in ASP.NET Core gRPC.</span></span> <span data-ttu-id="bdcfd-105">这些服务是 Windows Communication Foundation （WCF）和 gRPC 中的最简单服务类型，因此，这是一个很好的起点。</span><span class="sxs-lookup"><span data-stu-id="bdcfd-105">These services are the simplest service types in both Windows Communication Foundation (WCF) and gRPC, so it's an excellent place to start.</span></span> <span data-ttu-id="bdcfd-106">迁移服务后，你将了解如何从同一 `.proto` 文件生成客户端库，以便从 .NET 客户端应用程序使用该服务。</span><span class="sxs-lookup"><span data-stu-id="bdcfd-106">After migrating the service, you'll learn how to generate a client library from the same `.proto` file to consume the service from a .NET client application.</span></span>

## <a name="the-wcf-solution"></a><span data-ttu-id="bdcfd-107">WCF 解决方案</span><span class="sxs-lookup"><span data-stu-id="bdcfd-107">The WCF solution</span></span>

<span data-ttu-id="bdcfd-108">[PortfoliosSample 解决方案](https://github.com/dotnet-architecture/grpc-for-wcf-developers/tree/master/PortfoliosSample/wcf/TraderSys)包括一个简单的请求-答复项目组合服务，可下载给定交易的单个项目组合或所有包。</span><span class="sxs-lookup"><span data-stu-id="bdcfd-108">The [PortfoliosSample solution](https://github.com/dotnet-architecture/grpc-for-wcf-developers/tree/master/PortfoliosSample/wcf/TraderSys) includes a simple request-reply Portfolio service to download either a single portfolio or all portfolios for a given trader.</span></span> <span data-ttu-id="bdcfd-109">服务在接口 `IPortfolioService` 中使用 `ServiceContract` 属性定义：</span><span class="sxs-lookup"><span data-stu-id="bdcfd-109">The service is defined in the interface `IPortfolioService` with a `ServiceContract` attribute:</span></span>

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

<span data-ttu-id="bdcfd-110">`Portfolio` 模型是一个用C# [DataContract](xref:System.Runtime.Serialization.DataContractAttribute)标记的简单类，其中包括 `PortfolioItem` 对象的列表。</span><span class="sxs-lookup"><span data-stu-id="bdcfd-110">The `Portfolio` model is a simple C# class marked with [DataContract](xref:System.Runtime.Serialization.DataContractAttribute) and including a list of `PortfolioItem` objects.</span></span> <span data-ttu-id="bdcfd-111">这些模型在 `TraderSys.PortfolioData` 项目以及一个表示数据访问抽象的存储库类中定义。</span><span class="sxs-lookup"><span data-stu-id="bdcfd-111">These models are defined in the `TraderSys.PortfolioData` project along with a repository class that represents a data access abstraction.</span></span>

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

<span data-ttu-id="bdcfd-112">`ServiceContract` 实现使用通过依赖关系注入提供的存储库类，该依赖项注入返回 `DataContract` 类型的实例：</span><span class="sxs-lookup"><span data-stu-id="bdcfd-112">The `ServiceContract` implementation uses a repository class provided via dependency injection that returns instances of the `DataContract` types:</span></span>

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

## <a name="the-portfoliosproto-file"></a><span data-ttu-id="bdcfd-113">包 proto 文件</span><span class="sxs-lookup"><span data-stu-id="bdcfd-113">The portfolios.proto file</span></span>

<span data-ttu-id="bdcfd-114">如果按照上一部分中的说明进行操作，则应具有一个 gRPC 项目，其中包含如下所示的 `portfolios.proto` 文件：</span><span class="sxs-lookup"><span data-stu-id="bdcfd-114">If you followed the instructions in the previous section, you should have a gRPC project with a `portfolios.proto` file that looks like this:</span></span>

```protobuf
syntax = "proto3";

option csharp_namespace = "TraderSys.Portfolios.Protos";

package PortfolioServer;

service Portfolios {
  // RPCs will go here
}
```

<span data-ttu-id="bdcfd-115">第一步是将 `DataContract` 类迁移到它们的 Protobuf 等效项。</span><span class="sxs-lookup"><span data-stu-id="bdcfd-115">The first step is to migrate the `DataContract` classes to their Protobuf equivalents.</span></span>

## <a name="convert-the-datacontract-classes-to-grpc-messages"></a><span data-ttu-id="bdcfd-116">将 DataContract 类转换为 gRPC 消息</span><span class="sxs-lookup"><span data-stu-id="bdcfd-116">Convert the DataContract classes to gRPC messages</span></span>

<span data-ttu-id="bdcfd-117">`PortfolioItem` 类将首先转换为 Protobuf 消息，因为 `Portfolio` 类依赖于它。</span><span class="sxs-lookup"><span data-stu-id="bdcfd-117">The `PortfolioItem` class will be converted to a Protobuf message first, because the `Portfolio` class depends on it.</span></span> <span data-ttu-id="bdcfd-118">类很简单，而三个属性直接映射到 gRPC 数据类型。</span><span class="sxs-lookup"><span data-stu-id="bdcfd-118">The class is simple, and three of the properties map directly to gRPC data types.</span></span> <span data-ttu-id="bdcfd-119">`Cost` 属性表示购买的股票的价格，是 `decimal` 字段。</span><span class="sxs-lookup"><span data-stu-id="bdcfd-119">The `Cost` property, which represents the price paid for the shares at purchase, is a `decimal` field.</span></span> <span data-ttu-id="bdcfd-120">gRPC 仅支持对实数 `float` 或 `double`，这不适用于货币。</span><span class="sxs-lookup"><span data-stu-id="bdcfd-120">gRPC supports only `float` or `double` for real numbers, which aren't suitable for currency.</span></span> <span data-ttu-id="bdcfd-121">由于共享价格的最小值仅有1美分，因此成本可表示为 `int32`。</span><span class="sxs-lookup"><span data-stu-id="bdcfd-121">Because share prices vary by a minimum of one cent, the cost can be expressed as an `int32` of cents.</span></span>

> [!NOTE]
> <span data-ttu-id="bdcfd-122">请记得在 `.proto` 文件中使用 camelCase 作为字段名称。</span><span class="sxs-lookup"><span data-stu-id="bdcfd-122">Remember to use camelCase for field names in your `.proto` file.</span></span> <span data-ttu-id="bdcfd-123">C#代码生成器会将它们转换为 PascalCase，而其他语言的用户则感谢您遵从它们的不同编码标准。</span><span class="sxs-lookup"><span data-stu-id="bdcfd-123">The C# code generator will convert them to PascalCase for you, and users of other languages will thank you for respecting their different coding standards.</span></span>

```protobuf
message PortfolioItem {
    int32 id = 1;
    int32 share_id = 2;
    int32 holding = 3;
    int32 cost_cents = 4;
}
```

<span data-ttu-id="bdcfd-124">`Portfolio` 类稍微复杂一些。</span><span class="sxs-lookup"><span data-stu-id="bdcfd-124">The `Portfolio` class is a little more complicated.</span></span> <span data-ttu-id="bdcfd-125">在 WCF 代码中，开发人员使用 `TraderId` 属性的 `Guid`，并包含 `List<PortfolioItem>`。</span><span class="sxs-lookup"><span data-stu-id="bdcfd-125">In the WCF code, the developer used a `Guid` for the `TraderId` property, and contains a `List<PortfolioItem>`.</span></span> <span data-ttu-id="bdcfd-126">在 Protobuf 中没有第一类 `UUID` 类型的情况下，应将 `string` 用于 `traderId` 字段，并在自己的代码中对其进行分析。</span><span class="sxs-lookup"><span data-stu-id="bdcfd-126">In Protobuf, which doesn't have a first-class `UUID` type, you should use a `string` for the `traderId` field and parse it in your own code.</span></span> <span data-ttu-id="bdcfd-127">对于项列表，请对字段使用 `repeated` 关键字。</span><span class="sxs-lookup"><span data-stu-id="bdcfd-127">For the list of items, use the `repeated` keyword on the field.</span></span>

```protobuf
message Portfolio {
    int32 id = 1;
    string trader_id = 2;
    repeated PortfolioItem items = 3;
}
```

<span data-ttu-id="bdcfd-128">现在，你已有了数据消息，可以声明服务 RPC 终结点了。</span><span class="sxs-lookup"><span data-stu-id="bdcfd-128">Now that you have the data messages, you can declare the service RPC endpoints.</span></span>

## <a name="convert-servicecontract-to-a-grpc-service"></a><span data-ttu-id="bdcfd-129">将 ServiceContract 转换为 gRPC 服务</span><span class="sxs-lookup"><span data-stu-id="bdcfd-129">Convert ServiceContract to a gRPC service</span></span>

<span data-ttu-id="bdcfd-130">WCF `Get` 方法使用两个参数： `Guid traderId` 和 `int portfolioId`。</span><span class="sxs-lookup"><span data-stu-id="bdcfd-130">The WCF `Get` method takes two parameters: `Guid traderId` and `int portfolioId`.</span></span> <span data-ttu-id="bdcfd-131">gRPC 服务方法只需要一个参数，因此需要创建一条消息来保存这两个值。</span><span class="sxs-lookup"><span data-stu-id="bdcfd-131">gRPC service methods can take only a single parameter, so you need to create a message to hold the two values.</span></span> <span data-ttu-id="bdcfd-132">常见的做法是将这些请求对象命名为与方法相同的名称，后面跟有后缀 `Request`。</span><span class="sxs-lookup"><span data-stu-id="bdcfd-132">It's common practice to name these request objects with the same name as the method followed by the suffix `Request`.</span></span> <span data-ttu-id="bdcfd-133">同样，`string` 用于 `traderId` 字段，而不是 `Guid`。</span><span class="sxs-lookup"><span data-stu-id="bdcfd-133">Again, `string` is being used for the `traderId` field instead of `Guid`.</span></span>

<span data-ttu-id="bdcfd-134">该服务只是直接返回 `Portfolio` 消息，但这可能会影响将来的向后兼容性。</span><span class="sxs-lookup"><span data-stu-id="bdcfd-134">The service could just return a `Portfolio` message directly, but again, this could affect backward compatibility in the future.</span></span> <span data-ttu-id="bdcfd-135">最好为服务中的每个方法定义单独的 `Request` 和 `Response` 消息，即使许多这些方法现在都是相同的。</span><span class="sxs-lookup"><span data-stu-id="bdcfd-135">It's a good practice to define separate `Request` and `Response` messages for every method in a service, even if many of them are the same right now.</span></span> <span data-ttu-id="bdcfd-136">因此，请使用单个 `Portfolio` 字段声明 `GetResponse` 消息。</span><span class="sxs-lookup"><span data-stu-id="bdcfd-136">So declare a `GetResponse` message with a single `Portfolio` field.</span></span>

<span data-ttu-id="bdcfd-137">此示例显示了 gRPC 服务方法的声明以及 `GetRequest` 消息：</span><span class="sxs-lookup"><span data-stu-id="bdcfd-137">This example shows the declaration of the gRPC service method with the `GetRequest` message:</span></span>

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

<span data-ttu-id="bdcfd-138">WCF `GetAll` 方法仅采用一个参数，`traderId`，因此您可能似乎将 `string` 指定为参数类型。</span><span class="sxs-lookup"><span data-stu-id="bdcfd-138">The WCF `GetAll` method takes only a single parameter, `traderId`, so it might seem that you could specify `string` as the parameter type.</span></span> <span data-ttu-id="bdcfd-139">但 gRPC 要求使用定义的消息类型。</span><span class="sxs-lookup"><span data-stu-id="bdcfd-139">But gRPC requires a defined message type.</span></span> <span data-ttu-id="bdcfd-140">此要求可帮助强制执行将自定义消息用于所有输入和输出的操作，以便将来能够向后兼容。</span><span class="sxs-lookup"><span data-stu-id="bdcfd-140">This requirement helps to enforce the practice of using custom messages for all inputs and outputs, for future backward compatibility.</span></span>

<span data-ttu-id="bdcfd-141">WCF 方法还会返回 `List<Portfolio>`，但出于相同的原因，它不允许简单参数类型，gRPC 不允许 `repeated Portfolio` 作为返回类型。</span><span class="sxs-lookup"><span data-stu-id="bdcfd-141">The WCF method also returns a `List<Portfolio>`, but for the same reason it doesn't allow simple parameter types, gRPC won't allow `repeated Portfolio` as a return type.</span></span> <span data-ttu-id="bdcfd-142">而应创建一个 `GetAllResponse` 类型来包装列表。</span><span class="sxs-lookup"><span data-stu-id="bdcfd-142">Instead, create a `GetAllResponse` type to wrap the list.</span></span>

> [!WARNING]
> <span data-ttu-id="bdcfd-143">你可能会想要创建 `PortfolioList` 消息或类似内容，并在多个服务方法中使用它，但你应该不能做到这一点。</span><span class="sxs-lookup"><span data-stu-id="bdcfd-143">You might be tempted to create a `PortfolioList` message or something similar and use it across multiple service methods, but you should resist this temptation.</span></span> <span data-ttu-id="bdcfd-144">不可能知道如何改进服务的各种方法，使其消息保持特定和明确的隔离。</span><span class="sxs-lookup"><span data-stu-id="bdcfd-144">It's impossible to know how the various methods on a service will evolve, so keep their messages specific and cleanly separated.</span></span>

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

<span data-ttu-id="bdcfd-145">如果你使用这些更改保存你的项目，则 gRPC 生成目标将在后台运行并生成所有 Protobuf 消息类型以及可继承以实现该服务的基类。</span><span class="sxs-lookup"><span data-stu-id="bdcfd-145">If you save your project with these changes, the gRPC build target will run in the background and generate all the Protobuf message types and a base class that you can inherit to implement the service.</span></span>

<span data-ttu-id="bdcfd-146">打开 `Services/GreeterService.cs` 类并删除示例代码。</span><span class="sxs-lookup"><span data-stu-id="bdcfd-146">Open the `Services/GreeterService.cs` class and delete the example code.</span></span> <span data-ttu-id="bdcfd-147">现在，你可以添加项目组合服务实现。</span><span class="sxs-lookup"><span data-stu-id="bdcfd-147">Now you can add the Portfolio service implementation.</span></span> <span data-ttu-id="bdcfd-148">生成的基类将位于 `Protos` 命名空间中，并以嵌套类的形式生成。</span><span class="sxs-lookup"><span data-stu-id="bdcfd-148">The generated base class will be in the `Protos` namespace and is generated as a nested class.</span></span> <span data-ttu-id="bdcfd-149">gRPC 创建一个静态类，该类与 `.proto` 文件中的服务具有相同的名称，并且在该静态类内创建一个具有后缀 `Base` 的基类，因此基类型的完整标识符 `TraderSys.Portfolios.Protos.Portfolios.PortfoliosBase`。</span><span class="sxs-lookup"><span data-stu-id="bdcfd-149">gRPC creates a static class with the same name as the service in the `.proto` file and a base class with the suffix `Base` inside that static class, so the full identifier for the base type is `TraderSys.Portfolios.Protos.Portfolios.PortfoliosBase`.</span></span>

```csharp
namespace TraderSys.Portfolios.Services
{
    public class PortfolioService : Protos.Portfolios.PortfoliosBase
    {
    }
}
```

<span data-ttu-id="bdcfd-150">基类声明可重写以实现服务 `virtual` 方法 `Get` 和 `GetAll`。</span><span class="sxs-lookup"><span data-stu-id="bdcfd-150">The base class declares `virtual` methods for `Get` and `GetAll` that can be overridden to implement the service.</span></span> <span data-ttu-id="bdcfd-151">方法是 `virtual` 而不是 `abstract`，因此，如果未实现这些方法，则服务可以返回显式 gRPC `Unimplemented` 状态代码，这与你可以在常规C#代码中引发 `NotImplementedException` 非常类似。</span><span class="sxs-lookup"><span data-stu-id="bdcfd-151">The methods are `virtual` rather than `abstract` so that if you don't implement them, the service can return an explicit gRPC `Unimplemented` status code, much like you might throw a `NotImplementedException` in regular C# code.</span></span>

<span data-ttu-id="bdcfd-152">ASP.NET Core 中所有 gRPC 一元服务方法的签名都是一致的。</span><span class="sxs-lookup"><span data-stu-id="bdcfd-152">The signature for all gRPC unary service methods in ASP.NET Core is consistent.</span></span> <span data-ttu-id="bdcfd-153">有两个参数：第一个参数是在 `.proto` 文件中声明的消息类型，第二个参数是类似于 ASP.NET Core 中的 `HttpContext` 的 `ServerCallContext`。</span><span class="sxs-lookup"><span data-stu-id="bdcfd-153">There are two parameters: the first is the message type declared in the `.proto` file, and the second is a `ServerCallContext` that works similarly to the `HttpContext` from ASP.NET Core.</span></span> <span data-ttu-id="bdcfd-154">事实上，在 `ServerCallContext` 类上有一个名为 `GetHttpContext` 的扩展方法，您可以使用该方法获取底层 `HttpContext`，不过您不需要经常使用它。</span><span class="sxs-lookup"><span data-stu-id="bdcfd-154">In fact, there's an extension method called `GetHttpContext` on the `ServerCallContext` class that you can use to get the underlying `HttpContext`, although you shouldn't need to use it often.</span></span> <span data-ttu-id="bdcfd-155">我们将在本章稍后部分以及讨论身份验证一章中介绍 `ServerCallContext`。</span><span class="sxs-lookup"><span data-stu-id="bdcfd-155">We'll take a look at `ServerCallContext` later in this chapter, and also in the chapter that discusses authentication.</span></span>

<span data-ttu-id="bdcfd-156">此方法的返回类型为 `Task<T>`，其中 `T` 为响应消息类型。</span><span class="sxs-lookup"><span data-stu-id="bdcfd-156">The method's return type is a `Task<T>`, where `T` is the response message type.</span></span> <span data-ttu-id="bdcfd-157">所有 gRPC 服务方法都是异步的。</span><span class="sxs-lookup"><span data-stu-id="bdcfd-157">All gRPC service methods are asynchronous.</span></span>

## <a name="migrate-the-portfoliodata-library-to-net-core"></a><span data-ttu-id="bdcfd-158">将 PortfolioData 库迁移到 .NET Core</span><span class="sxs-lookup"><span data-stu-id="bdcfd-158">Migrate the PortfolioData library to .NET Core</span></span>

<span data-ttu-id="bdcfd-159">此时，项目需要 WCF 解决方案的 `TraderSys.PortfolioData` 类库中包含的项目组合存储库和模型。</span><span class="sxs-lookup"><span data-stu-id="bdcfd-159">At this point, the project needs the Portfolio repository and models contained in the `TraderSys.PortfolioData` class library in the WCF solution.</span></span> <span data-ttu-id="bdcfd-160">最简单的方法是通过使用 Visual Studio "**新建项目**" 对话框和 "类库（.NET Standard）" 模板来创建一个新的类库，也可以通过使用 .NET Core CLI 从命令行运行以下 `TraderSys.sln` 命令：</span><span class="sxs-lookup"><span data-stu-id="bdcfd-160">The easiest way to bring them across is to create a new class library by using either the Visual Studio **New project** dialog box with the Class Library (.NET Standard) template, or from the command line by using the .NET Core CLI, running these commands from the directory that contains the `TraderSys.sln` file:</span></span>

```dotnetcli
dotnet new classlib -o src/TraderSys.PortfolioData
dotnet sln add src/TraderSys.PortfolioData
```

<span data-ttu-id="bdcfd-161">创建库并将其添加到解决方案中后，删除生成的 `Class1.cs` 文件，并将文件从 WCF 解决方案的库复制到新的类库文件夹，保留文件夹结构：</span><span class="sxs-lookup"><span data-stu-id="bdcfd-161">After you've created the library and added it to the solution, delete the generated `Class1.cs` file and copy the files from the WCF solution's library into the new class library's folder, keeping the folder structure:</span></span>

```
Models
  Portfolio.cs
  PortfolioItem.cs
IPortfolioRepository.cs
PortfolioRepository.cs
```

<span data-ttu-id="bdcfd-162">SDK 样式的 .NET 项目会自动在其自己的目录中包含任何 `.cs` 文件，因此无需将其显式添加到项目。</span><span class="sxs-lookup"><span data-stu-id="bdcfd-162">SDK-style .NET projects automatically include any `.cs` files in or under their own directory, so you don't need to explicitly add them to the project.</span></span> <span data-ttu-id="bdcfd-163">剩下的唯一步骤是从 `Portfolio` 和 `PortfolioItem` 类中删除 `DataContract` 和 `DataMember` 属性，使其成为普通旧C#类：</span><span class="sxs-lookup"><span data-stu-id="bdcfd-163">The only step remaining is to remove the `DataContract` and `DataMember` attributes from the `Portfolio` and `PortfolioItem` classes so they're plain old C# classes:</span></span>

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

## <a name="use-aspnet-core-dependency-injection"></a><span data-ttu-id="bdcfd-164">使用 ASP.NET Core 依赖关系注入</span><span class="sxs-lookup"><span data-stu-id="bdcfd-164">Use ASP.NET Core dependency injection</span></span>

<span data-ttu-id="bdcfd-165">现在，你可以将对此库的引用添加到 gRPC 应用程序项目，并在 gRPC 服务实现中使用依赖关系注入来使用 `PortfolioRepository` 类。</span><span class="sxs-lookup"><span data-stu-id="bdcfd-165">Now you can add a reference to this library to the gRPC application project and consume the `PortfolioRepository` class by using dependency injection in the gRPC service implementation.</span></span> <span data-ttu-id="bdcfd-166">在 WCF 应用程序中，依赖关系注入由 Autofac IoC 容器提供。</span><span class="sxs-lookup"><span data-stu-id="bdcfd-166">In the WCF application, dependency injection was provided by the Autofac IoC container.</span></span> <span data-ttu-id="bdcfd-167">ASP.NET Core 在中具有依赖关系注入融入。</span><span class="sxs-lookup"><span data-stu-id="bdcfd-167">ASP.NET Core has dependency injection baked in.</span></span> <span data-ttu-id="bdcfd-168">可以在 `Startup` 类的 `ConfigureServices` 方法中注册存储库：</span><span class="sxs-lookup"><span data-stu-id="bdcfd-168">You can register the repository in the `ConfigureServices` method in the `Startup` class:</span></span>

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

<span data-ttu-id="bdcfd-169">现在可以在 `PortfolioService` 类中将 `IPortfolioRepository` 实现指定为构造函数参数，如下所示：</span><span class="sxs-lookup"><span data-stu-id="bdcfd-169">The `IPortfolioRepository` implementation can now be specified as a constructor parameter in the `PortfolioService` class, as follows:</span></span>

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

## <a name="implement-the-grpc-service"></a><span data-ttu-id="bdcfd-170">实现 gRPC 服务</span><span class="sxs-lookup"><span data-stu-id="bdcfd-170">Implement the gRPC service</span></span>

<span data-ttu-id="bdcfd-171">现在您已在 `portfolios.proto` 文件中声明了您的消息和服务，您必须在 `PortfolioService` 类中实现从 gRPC 生成的 `Portfolios.PortfoliosBase` 类继承的服务方法。</span><span class="sxs-lookup"><span data-stu-id="bdcfd-171">Now that you've declared your messages and your service in the `portfolios.proto` file, you have to implement the service methods in the `PortfolioService` class that inherits from the gRPC-generated `Portfolios.PortfoliosBase` class.</span></span> <span data-ttu-id="bdcfd-172">方法在基类中声明为 `virtual`。</span><span class="sxs-lookup"><span data-stu-id="bdcfd-172">The methods are declared as `virtual` in the base class.</span></span> <span data-ttu-id="bdcfd-173">如果不重写这些值，则默认情况下，它们将返回 "未实现" 状态代码 gRPC。</span><span class="sxs-lookup"><span data-stu-id="bdcfd-173">If you don't override them, they'll return a gRPC "Not Implemented" status code by default.</span></span>

<span data-ttu-id="bdcfd-174">首先实现 `Get` 方法。</span><span class="sxs-lookup"><span data-stu-id="bdcfd-174">Start by implementing the `Get` method.</span></span> <span data-ttu-id="bdcfd-175">默认替代如下例所示：</span><span class="sxs-lookup"><span data-stu-id="bdcfd-175">The default override looks like this example:</span></span>

```csharp
public override Task<GetResponse> Get(GetRequest request, ServerCallContext context)
{
    return base.Get(request, context);
}
```

<span data-ttu-id="bdcfd-176">第一个问题是，`request.TraderId` 是一个字符串，并且该服务需要 `Guid`。</span><span class="sxs-lookup"><span data-stu-id="bdcfd-176">The first problem is that `request.TraderId` is a string, and the service requires a `Guid`.</span></span> <span data-ttu-id="bdcfd-177">即使 `UUID`字符串的预期格式，代码也必须处理调用方发送了无效值并做出相应响应的可能性。</span><span class="sxs-lookup"><span data-stu-id="bdcfd-177">Even though the expected format for the string is `UUID`, the code has to deal with the possibility that a caller has sent an invalid value and respond appropriately.</span></span> <span data-ttu-id="bdcfd-178">服务可以通过引发 `RpcException` 来响应错误，并使用标准 `InvalidArgument` 状态代码来表示问题：</span><span class="sxs-lookup"><span data-stu-id="bdcfd-178">The service can respond with errors by throwing an `RpcException` and use the standard `InvalidArgument` status code to express the problem:</span></span>

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

<span data-ttu-id="bdcfd-179">为 `traderId`提供正确 `Guid` 值后，你可以使用存储库来检索组合并将其返回到客户端：</span><span class="sxs-lookup"><span data-stu-id="bdcfd-179">After there's a proper `Guid` value for `traderId`, you can use the repository to retrieve the Portfolio and return it to the client:</span></span>

```csharp
    var response = new GetResponse
    {
        Portfolio = await _repository.GetAsync(request.TraderId, request.PortfolioId)
    };
```

### <a name="map-internal-models-to-grpc-messages"></a><span data-ttu-id="bdcfd-180">将内部模型映射到 gRPC 消息</span><span class="sxs-lookup"><span data-stu-id="bdcfd-180">Map internal models to gRPC messages</span></span>

<span data-ttu-id="bdcfd-181">前面的代码实际上不起作用，因为存储库返回自己的 POCO 模型 `Portfolio`，但 gRPC 需要其自己的 Protobuf 消息 `Portfolio`。</span><span class="sxs-lookup"><span data-stu-id="bdcfd-181">The previous code doesn't actually work because the repository is returning its own POCO model `Portfolio`, but gRPC needs its own Protobuf message `Portfolio`.</span></span> <span data-ttu-id="bdcfd-182">与将实体框架类型映射到数据传输类型一样，最佳解决方案是在两者之间提供转换。</span><span class="sxs-lookup"><span data-stu-id="bdcfd-182">As when you map Entity Framework types to data transfer types, the best solution is to provide a conversion between the two.</span></span> <span data-ttu-id="bdcfd-183">放置此转换的代码的好地方是在 Protobuf 生成的类中，该类被声明为 `partial` 类，以便可以进行扩展：</span><span class="sxs-lookup"><span data-stu-id="bdcfd-183">A good place to put the code for this conversion is in the Protobuf-generated class, which is declared as a `partial` class so it can be extended:</span></span>

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
> <span data-ttu-id="bdcfd-184">您可以使用类似[AutoMapper](https://automapper.org/)的库来处理从内部模型类到 Protobuf 类型的这种转换，前提是配置较低级别的类型转换，如 `string`/`Guid` 或 `decimal`/`double` 和列表映射。</span><span class="sxs-lookup"><span data-stu-id="bdcfd-184">You could use a library like [AutoMapper](https://automapper.org/) to handle this conversion from internal model classes to Protobuf types, as long as you configure the lower-level type conversions like `string`/`Guid` or `decimal`/`double` and the list mapping.</span></span>

<span data-ttu-id="bdcfd-185">现在，你已准备好转换代码，接下来可以完成 `Get` 方法实现：</span><span class="sxs-lookup"><span data-stu-id="bdcfd-185">Now that you have the conversion code in place, you can complete the `Get` method implementation:</span></span>

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

<span data-ttu-id="bdcfd-186">`GetAll` 方法的实现类似。</span><span class="sxs-lookup"><span data-stu-id="bdcfd-186">The implementation of the `GetAll` method is similar.</span></span> <span data-ttu-id="bdcfd-187">请注意，Protobuf 消息上的 `repeated` 字段将作为 `RepeatedField<T>`类型的 `readonly` 属性生成，因此你必须使用 `AddRange` 方法向其中添加项，如以下示例中所示：</span><span class="sxs-lookup"><span data-stu-id="bdcfd-187">Note that the `repeated` fields on Protobuf messages are generated as `readonly` properties of type `RepeatedField<T>`, so you have to add items to them by using the `AddRange` method, like in this example:</span></span>

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

<span data-ttu-id="bdcfd-188">已成功将 WCF 请求-答复服务迁移到 gRPC，我们来看看如何从 `.proto` 文件创建客户端。</span><span class="sxs-lookup"><span data-stu-id="bdcfd-188">Having successfully migrated the WCF request-reply service to gRPC, let's look at creating a client for it from the `.proto` file.</span></span>

## <a name="generate-client-code"></a><span data-ttu-id="bdcfd-189">生成客户端代码</span><span class="sxs-lookup"><span data-stu-id="bdcfd-189">Generate client code</span></span>

<span data-ttu-id="bdcfd-190">在同一解决方案中创建 .NET Standard 类库，以包含客户端。</span><span class="sxs-lookup"><span data-stu-id="bdcfd-190">Create a .NET Standard class library in the same solution to contain the client.</span></span> <span data-ttu-id="bdcfd-191">这主要是创建客户端代码的示例，但你可以使用 NuGet 打包此类库，并将其分发到供其他 .NET 团队使用的内部存储库中。</span><span class="sxs-lookup"><span data-stu-id="bdcfd-191">This is primarily an example of creating client code, but you could package such a library by using NuGet and distribute it on an internal repository for other .NET teams to consume.</span></span> <span data-ttu-id="bdcfd-192">继续并向解决方案添加名为 `TraderSys.Portfolios.Client` 的新 .NET Standard 类库，并删除 `Class1.cs` 文件。</span><span class="sxs-lookup"><span data-stu-id="bdcfd-192">Go ahead and add a new .NET Standard class library called `TraderSys.Portfolios.Client` to the solution and delete the `Class1.cs` file.</span></span>

> [!CAUTION]
> <span data-ttu-id="bdcfd-193">[Grpc](https://www.nuget.org/packages/Grpc.Net.Client) NuGet 包需要 .net Core 3.0 （或另 .NET Standard 一个与2.1 兼容的运行时）。</span><span class="sxs-lookup"><span data-stu-id="bdcfd-193">The [Grpc.Net.Client](https://www.nuget.org/packages/Grpc.Net.Client) NuGet package requires .NET Core 3.0 (or another .NET Standard 2.1-compliant runtime).</span></span> <span data-ttu-id="bdcfd-194">[Grpc](https://www.nuget.org/packages/Grpc.Core) NuGet 包支持早期版本的 .NET FRAMEWORK 和 .net Core。</span><span class="sxs-lookup"><span data-stu-id="bdcfd-194">Earlier versions of .NET Framework and .NET Core are supported by the [Grpc.Core](https://www.nuget.org/packages/Grpc.Core) NuGet package.</span></span>

<span data-ttu-id="bdcfd-195">在 Visual Studio 2019 中，可以通过类似于在 Visual Studio 早期版本中添加对 WCF 项目的服务引用的方式来添加对 gRPC 服务的引用。</span><span class="sxs-lookup"><span data-stu-id="bdcfd-195">In Visual Studio 2019, you can add references to gRPC services in a way that's similar to how you'd add service references to WCF projects in earlier versions of Visual Studio.</span></span> <span data-ttu-id="bdcfd-196">现在，服务引用和连接服务都是在同一个 UI 下进行管理。</span><span class="sxs-lookup"><span data-stu-id="bdcfd-196">Service references and connected services are all managed under the same UI now.</span></span> <span data-ttu-id="bdcfd-197">您可以通过右键单击解决方案资源管理器中 `TraderSys.Portfolios.Client` 项目中的 "**依赖项**" 节点，然后选择 "**添加连接的服务**" 来访问该 UI。</span><span class="sxs-lookup"><span data-stu-id="bdcfd-197">You can access the UI by right-clicking the **Dependencies** node in the `TraderSys.Portfolios.Client` project in Solution Explorer and selecting **Add Connected Service**.</span></span> <span data-ttu-id="bdcfd-198">在出现的工具窗口中，选择 "**服务引用**" 部分，然后选择 "**添加新的 gRPC 服务引用**"：</span><span class="sxs-lookup"><span data-stu-id="bdcfd-198">In the tool window that appears, select the **Service References** section and then select **Add new gRPC service reference**:</span></span>

![Visual Studio 2019 中的连接的服务 UI](media/migrate-request-reply/add-connected-service.png)

<span data-ttu-id="bdcfd-200">浏览到 `TraderSys.Portfolios` 项目中的 `portfolios.proto` 文件，将**客户端**保留在 "**选择要生成的类的类型**" 下，然后选择 **"确定"** ：</span><span class="sxs-lookup"><span data-stu-id="bdcfd-200">Browse to the `portfolios.proto` file in the `TraderSys.Portfolios` project, leave **Client** under **Select the type of class to be generated**, and then select **OK**:</span></span>

![Visual Studio 2019 中的 "添加新的 gRPC 服务引用" 对话框](media/migrate-request-reply/add-new-grpc-service-reference.png)

> [!TIP]
> <span data-ttu-id="bdcfd-202">请注意，此对话框还提供了 "URL" 字段。</span><span class="sxs-lookup"><span data-stu-id="bdcfd-202">Notice that this dialog box also provides a URL field.</span></span> <span data-ttu-id="bdcfd-203">如果你的组织维护 `.proto` 文件的 web 访问目录，你只需通过设置此 URL 地址即可创建客户端。</span><span class="sxs-lookup"><span data-stu-id="bdcfd-203">If your organization maintains a web-accessible directory of `.proto` files, you can create clients just by setting this URL address.</span></span>

<span data-ttu-id="bdcfd-204">当你使用 Visual Studio "**添加连接服务**" 功能时，`portfolios.proto` 文件将作为*链接文件*添加到类库项目中，而不是复制，因此，对服务项目中的文件所做的更改将自动应用到客户端项目中。</span><span class="sxs-lookup"><span data-stu-id="bdcfd-204">When you use the Visual Studio **Add Connected Service** feature, the `portfolios.proto` file is added to the class library project as a *linked file* rather than copied, so changes to the file in the service project will automatically be applied in the client project.</span></span> <span data-ttu-id="bdcfd-205">`csproj` 文件中的 `<Protobuf>` 元素如下所示：</span><span class="sxs-lookup"><span data-stu-id="bdcfd-205">The `<Protobuf>` element in the `csproj` file looks like this:</span></span>

```xml
<Protobuf Include="..\TraderSys.Portfolios\Protos\portfolios.proto" GrpcServices="Client">
  <Link>Protos\portfolios.proto</Link>
</Protobuf>
```

> [!TIP]
> <span data-ttu-id="bdcfd-206">如果未使用 Visual Studio 或想要从命令行运行，则可以使用 `dotnet-grpc` 全局工具来管理 .NET gRPC 项目中的 Protobuf 引用。</span><span class="sxs-lookup"><span data-stu-id="bdcfd-206">If you're not using Visual Studio or prefer to work from the command line, you can use the `dotnet-grpc` global tool to manage Protobuf references in a .NET gRPC project.</span></span> <span data-ttu-id="bdcfd-207">有关详细信息，请参阅[`dotnet-grpc` 文档](/aspnet/core/grpc/dotnet-grpc)。</span><span class="sxs-lookup"><span data-stu-id="bdcfd-207">For more information, see the [`dotnet-grpc` documentation](/aspnet/core/grpc/dotnet-grpc).</span></span>

### <a name="use-the-portfolios-service-from-a-client-application"></a><span data-ttu-id="bdcfd-208">使用客户端应用程序中的 "包" 服务</span><span class="sxs-lookup"><span data-stu-id="bdcfd-208">Use the Portfolios service from a client application</span></span>

<span data-ttu-id="bdcfd-209">以下代码是如何在控制台应用程序中使用生成的客户端的简单示例。</span><span class="sxs-lookup"><span data-stu-id="bdcfd-209">The following code is a brief example of how to use the generated client in a console application.</span></span> <span data-ttu-id="bdcfd-210">本章末尾详细探讨了 gRPC 客户端代码。</span><span class="sxs-lookup"><span data-stu-id="bdcfd-210">A more detailed exploration of the gRPC client code is at the end of this chapter.</span></span>

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

<span data-ttu-id="bdcfd-211">现在，已将基本 WCF 应用程序迁移到 ASP.NET Core gRPC 服务，并创建了客户端，以便从 .NET 应用程序使用该服务。</span><span class="sxs-lookup"><span data-stu-id="bdcfd-211">You've now migrated a basic WCF application to an ASP.NET Core gRPC service and created a client to consume the service from a .NET application.</span></span> <span data-ttu-id="bdcfd-212">下一节将介绍更多的双工服务。</span><span class="sxs-lookup"><span data-stu-id="bdcfd-212">The next section will cover the more involved duplex services.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="bdcfd-213">[上一页](create-project.md)
>[下一页](migrate-duplex-services.md)</span><span class="sxs-lookup"><span data-stu-id="bdcfd-213">[Previous](create-project.md)
[Next](migrate-duplex-services.md)</span></span>
