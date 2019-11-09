---
title: 将 WCF 请求-答复服务迁移到 WCF 开发人员的 gRPC-gRPC
description: 了解如何将简单的请求-答复服务从 WCF 迁移到 gRPC。
author: markrendle
ms.date: 09/02/2019
ms.openlocfilehash: 12e042e8e7e3683cc4da1fedce2482e7199b04a7
ms.sourcegitcommit: 337bdc5a463875daf2cc6883e5a2da97d56f5000
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/24/2019
ms.locfileid: "73841503"
---
# <a name="migrate-a-wcf-request-reply-service-to-a-grpc-unary-rpc"></a><span data-ttu-id="4988d-103">将 WCF 请求-答复服务迁移到 gRPC 一元 RPC</span><span class="sxs-lookup"><span data-stu-id="4988d-103">Migrate a WCF request-reply service to a gRPC unary RPC</span></span>

<span data-ttu-id="4988d-104">本部分介绍如何将 WCF 中的基本请求-答复服务迁移到 ASP.NET Core gRPC 中的一元 RPC 服务。</span><span class="sxs-lookup"><span data-stu-id="4988d-104">This section covers how to migrate a basic request-reply service in WCF to a unary RPC service in ASP.NET Core gRPC.</span></span> <span data-ttu-id="4988d-105">这些服务是 Windows Communication Foundation （WCF）和 gRPC 中的最简单服务类型，因此，这是一个很好的起点。</span><span class="sxs-lookup"><span data-stu-id="4988d-105">These services are the simplest service types in both Windows Communication Foundation (WCF) and gRPC, so it's an excellent place to start.</span></span> <span data-ttu-id="4988d-106">迁移服务后，你将了解如何从同一 `.proto` 文件生成客户端库，以便从 .NET 客户端应用程序使用该服务。</span><span class="sxs-lookup"><span data-stu-id="4988d-106">After migrating the service, you'll learn how to generate a client library from the same `.proto` file to consume the service from a .NET client application.</span></span>

## <a name="the-wcf-solution"></a><span data-ttu-id="4988d-107">WCF 解决方案</span><span class="sxs-lookup"><span data-stu-id="4988d-107">The WCF solution</span></span>

<span data-ttu-id="4988d-108">[PortfoliosSample 解决方案](https://github.com/dotnet-architecture/grpc-for-wcf-developers/tree/master/PortfoliosSample/wcf/TraderSys)包括一个简单的请求-答复项目组合服务，可下载单个组合或给定交易的所有包。</span><span class="sxs-lookup"><span data-stu-id="4988d-108">The [PortfoliosSample solution](https://github.com/dotnet-architecture/grpc-for-wcf-developers/tree/master/PortfoliosSample/wcf/TraderSys) includes a simple Request-Reply Portfolio service to download a single portfolio, or all portfolios for a given Trader.</span></span> <span data-ttu-id="4988d-109">服务在接口 `IPortfolioService` 中使用 `ServiceContract` 属性定义：</span><span class="sxs-lookup"><span data-stu-id="4988d-109">The service is defined in the interface `IPortfolioService` with a `ServiceContract` attribute:</span></span>

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

<span data-ttu-id="4988d-110">`Portfolio` 模型是一个用C# [DataContract](xref:System.Runtime.Serialization.DataContractAttribute)标记的简单类，其中包括 `PortfolioItem` 对象的列表。</span><span class="sxs-lookup"><span data-stu-id="4988d-110">The `Portfolio` model is a simple C# class marked with [DataContract](xref:System.Runtime.Serialization.DataContractAttribute), including a list of `PortfolioItem` objects.</span></span> <span data-ttu-id="4988d-111">这些模型是在 `TraderSys.PortfolioData` 项目中定义的，以及一个表示数据访问抽象的存储库类。</span><span class="sxs-lookup"><span data-stu-id="4988d-111">These models are defined in the `TraderSys.PortfolioData` project, along with a repository class representing a data access abstraction.</span></span>

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

<span data-ttu-id="4988d-112">`ServiceContract` 实现使用通过依赖关系注入提供的存储库类，该依赖项注入返回 `DataContract` 类型的实例。</span><span class="sxs-lookup"><span data-stu-id="4988d-112">The `ServiceContract` implementation uses a repository class provided via dependency injection that returns instances of the `DataContract` types.</span></span>

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

## <a name="the-portfoliosproto-file"></a><span data-ttu-id="4988d-113">包 proto 文件</span><span class="sxs-lookup"><span data-stu-id="4988d-113">The portfolios.proto file</span></span>

<span data-ttu-id="4988d-114">如果按照上一部分中的说明进行操作，则应具有一个 gRPC 项目，其中包含如下所示的 `portfolios.proto` 文件。</span><span class="sxs-lookup"><span data-stu-id="4988d-114">If you followed the instructions in the previous section, you should have a gRPC project with a `portfolios.proto` file that looks like this.</span></span>

```protobuf
syntax = "proto3";

option csharp_namespace = "TraderSys.Portfolios.Protos";

package PortfolioServer;

service Portfolios {
  // RPCs will go here
}
```

<span data-ttu-id="4988d-115">第一步是将 `DataContract` 类迁移到它们的 Protobuf 等效项。</span><span class="sxs-lookup"><span data-stu-id="4988d-115">The first step is to migrate the `DataContract` classes to their Protobuf equivalents.</span></span>

## <a name="convert-the-datacontracts-to-grpc-messages"></a><span data-ttu-id="4988d-116">将 DataContracts 转换为 gRPC 消息</span><span class="sxs-lookup"><span data-stu-id="4988d-116">Convert the DataContracts to gRPC messages</span></span>

<span data-ttu-id="4988d-117">`PortfolioItem` 类将首先转换为 Protobuf 消息，因为 `Portfolio` 类依赖于它。</span><span class="sxs-lookup"><span data-stu-id="4988d-117">The `PortfolioItem` class will be converted to a Protobuf message first, as the `Portfolio` class depends on it.</span></span> <span data-ttu-id="4988d-118">类非常简单，并且三个属性直接映射到 gRPC 数据类型。</span><span class="sxs-lookup"><span data-stu-id="4988d-118">The class is very simple, and three of the properties map directly to gRPC data types.</span></span> <span data-ttu-id="4988d-119">`Cost` 属性表示购买的股票的价格，它是一个 `decimal` 字段，而 gRPC 仅支持 `float` 或 `double` 对于不适用于货币的实数。</span><span class="sxs-lookup"><span data-stu-id="4988d-119">The `Cost` property, representing the price paid for the shares at purchase, is a `decimal` field, and gRPC only supports `float` or `double` for real numbers, which aren't suitable for currency.</span></span> <span data-ttu-id="4988d-120">由于共享价格相差至少为1美分，因此成本可表示为 `int32` 美分。</span><span class="sxs-lookup"><span data-stu-id="4988d-120">Since share prices vary by a minimum of one cent, the cost can be expressed as an `int32` of cents.</span></span>

> [!NOTE]
> <span data-ttu-id="4988d-121">请记住使用 `.proto` 文件中字段名称的 `camelCase`;C#代码生成器会将它们转换为 `PascalCase`，而其他语言的用户则感谢您遵从它们的不同编码标准。</span><span class="sxs-lookup"><span data-stu-id="4988d-121">Remember to use `camelCase` for field names in your `.proto` file; the C# code generator will convert them to `PascalCase` for you, and users of other languages will thank you for respecting their different coding standards.</span></span>

```protobuf
message PortfolioItem {
    int32 id = 1;
    int32 share_id = 2;
    int32 holding = 3;
    int32 cost_cents = 4;
}
```

<span data-ttu-id="4988d-122">`Portfolio` 类稍微复杂一些。</span><span class="sxs-lookup"><span data-stu-id="4988d-122">The `Portfolio` class is a little more complicated.</span></span> <span data-ttu-id="4988d-123">在 WCF 代码中，开发人员使用 `TraderId` 属性的 `Guid`，并包含 `List<PortfolioItem>`。</span><span class="sxs-lookup"><span data-stu-id="4988d-123">In the WCF code, the developer used a `Guid` for the `TraderId` property, and contains a `List<PortfolioItem>`.</span></span> <span data-ttu-id="4988d-124">在 Protobuf 中没有第一类 `UUID` 类型的情况下，应将 `string` 用于 `traderId` 字段，并在自己的代码中对其进行分析。</span><span class="sxs-lookup"><span data-stu-id="4988d-124">In Protobuf, which doesn't have a first-class `UUID` type, you should use a `string` for the `traderId` field and parse it in your own code.</span></span> <span data-ttu-id="4988d-125">对于项列表，请对字段使用 `repeated` 关键字。</span><span class="sxs-lookup"><span data-stu-id="4988d-125">For the list of items, use the `repeated` keyword on the field.</span></span>

```protobuf
message Portfolio {
    int32 id = 1;
    string trader_id = 2;
    repeated PortfolioItem items = 3;
}
```

<span data-ttu-id="4988d-126">现在我们有了数据消息，可以声明服务 RPC 终结点。</span><span class="sxs-lookup"><span data-stu-id="4988d-126">Now we have our data messages, we can declare the service RPC endpoints.</span></span>

## <a name="convert-the-servicecontract-to-a-grpc-service"></a><span data-ttu-id="4988d-127">将 ServiceContract 转换为 gRPC 服务</span><span class="sxs-lookup"><span data-stu-id="4988d-127">Convert the ServiceContract to a gRPC service</span></span>

<span data-ttu-id="4988d-128">WCF `Get` 方法使用两个参数： `Guid traderId` 和 `int portfolioId`。</span><span class="sxs-lookup"><span data-stu-id="4988d-128">The WCF `Get` method takes two parameters: `Guid traderId` and `int portfolioId`.</span></span> <span data-ttu-id="4988d-129">gRPC 服务方法只能采用单个参数，因此必须创建消息来保存这两个值。</span><span class="sxs-lookup"><span data-stu-id="4988d-129">gRPC service methods can only take a single parameter, so a message must be created to hold the two values.</span></span> <span data-ttu-id="4988d-130">常见的做法是将这些请求对象命名为与方法相同的名称，并 `Request`后缀。</span><span class="sxs-lookup"><span data-stu-id="4988d-130">It's common practice to name these request objects with the same name as the method and the suffix `Request`.</span></span> <span data-ttu-id="4988d-131">同样，`string` 用于 `traderId` 字段，而不是 `Guid`。</span><span class="sxs-lookup"><span data-stu-id="4988d-131">Again, `string` is being used for the `traderId` field instead of `Guid`.</span></span>

<span data-ttu-id="4988d-132">该服务只是直接返回 `Portfolio` 消息，但这可能会影响将来的后向兼容性。</span><span class="sxs-lookup"><span data-stu-id="4988d-132">The service could just return a `Portfolio` message directly, but again, this could impact backward compatibility in the future.</span></span> <span data-ttu-id="4988d-133">最好为服务中的每个方法定义单独的 `Request` 和 `Response` 消息，即使它们现在很多都是相同的，因此请使用单个 `Portfolio` 字段声明 `GetResponse` 消息。</span><span class="sxs-lookup"><span data-stu-id="4988d-133">It's a good practice to define separate `Request` and `Response` messages for every method in a service, even if many of them are the same right now, so declare a `GetResponse` message with a single `Portfolio` field.</span></span>

<span data-ttu-id="4988d-134">下面的示例演示如何使用 `GetRequest` 消息声明 gRPC 服务方法：</span><span class="sxs-lookup"><span data-stu-id="4988d-134">The following example shows the declaration of the gRPC service method using the `GetRequest` message:</span></span>

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

<span data-ttu-id="4988d-135">WCF `GetAll` 方法只使用单个参数，`traderId`，因此，它可能看起来可以将 `string` 指定为参数类型，但 gRPC 需要定义的消息类型。</span><span class="sxs-lookup"><span data-stu-id="4988d-135">The WCF `GetAll` method only takes a single parameter, `traderId`, so it might seem that one could specify `string` as the parameter type, but gRPC requires a defined message type.</span></span> <span data-ttu-id="4988d-136">此要求可帮助强制执行将自定义消息用于所有输入和输出的操作，以便将来能够向后兼容。</span><span class="sxs-lookup"><span data-stu-id="4988d-136">This requirement helps to enforce the practice of using custom messages for all inputs and outputs, for future backward compatibility.</span></span>

<span data-ttu-id="4988d-137">WCF 方法还返回 `List<Portfolio>`，但出于同一原因，它不允许简单参数类型，gRPC 不允许 `repeated Portfolio` 作为返回类型。</span><span class="sxs-lookup"><span data-stu-id="4988d-137">The WCF method also returned a `List<Portfolio>`, but for the same reason it doesn't allow simple parameter types, gRPC won't allow `repeated Portfolio` as a return type.</span></span> <span data-ttu-id="4988d-138">而应创建一个 `GetAllResponse` 类型来包装列表。</span><span class="sxs-lookup"><span data-stu-id="4988d-138">Instead, create a `GetAllResponse` type to wrap the list.</span></span>

> [!WARNING]
> <span data-ttu-id="4988d-139">您可能会想创建一个 `PortfolioList` 消息或类似的消息，并跨多个服务方法使用它，但您应该不能做到这一点。</span><span class="sxs-lookup"><span data-stu-id="4988d-139">You may be tempted to create a `PortfolioList` message or similar and use it across multiple service methods, but you should resist this temptation.</span></span> <span data-ttu-id="4988d-140">不可能知道服务的各种方法在将来如何发展，因此请使其消息保持特定和明确的隔离。</span><span class="sxs-lookup"><span data-stu-id="4988d-140">It's impossible to know how the various methods on a service may evolve in the future, so keep their messages specific and cleanly separated.</span></span>

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

<span data-ttu-id="4988d-141">如果你使用这些更改保存你的项目，则 gRPC 生成目标将在后台运行并生成所有 Protobuf 消息类型以及可继承以实现该服务的基类。</span><span class="sxs-lookup"><span data-stu-id="4988d-141">If you save your project with these changes, the gRPC build target will run in the background and generate all the Protobuf message types and a base class you can inherit to implement the service.</span></span>

<span data-ttu-id="4988d-142">打开 `Services/GreeterService.cs` 类并删除示例代码。</span><span class="sxs-lookup"><span data-stu-id="4988d-142">Open up the `Services/GreeterService.cs` class and delete the example code.</span></span> <span data-ttu-id="4988d-143">现在，你可以添加项目组合服务实现。</span><span class="sxs-lookup"><span data-stu-id="4988d-143">Now you can add the Portfolio service implementation.</span></span> <span data-ttu-id="4988d-144">生成的基类将位于 `Protos` 命名空间中，并以嵌套类的形式生成。</span><span class="sxs-lookup"><span data-stu-id="4988d-144">The generated base class will be in the `Protos` namespace and is generated as a nested class.</span></span> <span data-ttu-id="4988d-145">gRPC 创建一个与 `.proto` 文件中的服务同名的静态类，然后在该静态类内创建一个具有后缀 `Base` 的基类，因此基类型的完整标识符 `TraderSys.Portfolios.Protos.Portfolios.PortfoliosBase`。</span><span class="sxs-lookup"><span data-stu-id="4988d-145">gRPC creates a static class with the same name as the service in the `.proto` file, and then a base class with the suffix `Base` inside that static class, so the full identifier for the base type is `TraderSys.Portfolios.Protos.Portfolios.PortfoliosBase`.</span></span>

```csharp
namespace TraderSys.Portfolios.Services
{
    public class PortfolioService : Protos.Portfolios.PortfoliosBase
    {
    }
}
```

<span data-ttu-id="4988d-146">基类声明可重写以实现服务 `virtual` 方法 `Get` 和 `GetAll`。</span><span class="sxs-lookup"><span data-stu-id="4988d-146">The base class declares `virtual` methods for `Get` and `GetAll` that can be overridden to implement the service.</span></span> <span data-ttu-id="4988d-147">方法是 `virtual` 而不是 `abstract`，因此，如果未实现这些方法，则服务可以返回显式 gRPC `Unimplemented` 状态代码，这与你可以在常规C#代码中引发 `NotImplementedException` 非常类似。</span><span class="sxs-lookup"><span data-stu-id="4988d-147">The methods are `virtual` rather than `abstract` so that if you don't implement them, the service can return an explicit gRPC `Unimplemented` status code, much like you might throw a `NotImplementedException` in regular C# code.</span></span>

<span data-ttu-id="4988d-148">ASP.NET Core 中所有 gRPC 一元服务方法的签名都是一致的。</span><span class="sxs-lookup"><span data-stu-id="4988d-148">The signature for all gRPC unary service methods in ASP.NET Core is consistent.</span></span> <span data-ttu-id="4988d-149">有两个参数：第一个参数是在 `.proto` 文件中声明的消息类型，第二个参数是类似于 ASP.NET Core 中的 `HttpContext` 的 `ServerCallContext`。</span><span class="sxs-lookup"><span data-stu-id="4988d-149">There are two parameters: the first is the message type declared in the `.proto` file, and the second is a `ServerCallContext` that works similarly to the `HttpContext` from ASP.NET Core.</span></span> <span data-ttu-id="4988d-150">事实上，在 `ServerCallContext` 类上有一个名为 `GetHttpContext` 的扩展方法，您可以使用该方法获取底层 `HttpContext`，不过您不需要经常使用它。</span><span class="sxs-lookup"><span data-stu-id="4988d-150">In fact, there's an extension method called `GetHttpContext` on the `ServerCallContext` class that you can use to get the underlying `HttpContext`, although you shouldn't need to use it often.</span></span> <span data-ttu-id="4988d-151">我们将在本章稍后部分以及讨论身份验证一章中介绍 `ServerCallContext`。</span><span class="sxs-lookup"><span data-stu-id="4988d-151">We'll take a look at `ServerCallContext` later in this chapter, and also in the chapter that discusses authentication.</span></span>

<span data-ttu-id="4988d-152">此方法的返回类型为 `Task<T>`，其中 `T` 为响应消息类型。</span><span class="sxs-lookup"><span data-stu-id="4988d-152">The method's return type is a `Task<T>` where `T` is the response message type.</span></span> <span data-ttu-id="4988d-153">所有 gRPC 服务方法都是异步的。</span><span class="sxs-lookup"><span data-stu-id="4988d-153">All gRPC service methods are asynchronous.</span></span>

## <a name="migrate-the-portfoliodata-library-to-net-core"></a><span data-ttu-id="4988d-154">将 PortfolioData 库迁移到 .NET Core</span><span class="sxs-lookup"><span data-stu-id="4988d-154">Migrate the PortfolioData library to .NET Core</span></span>

<span data-ttu-id="4988d-155">此时，项目需要 WCF 解决方案的 `TraderSys.PortfolioData` 类库中包含的项目组合存储库和模型。</span><span class="sxs-lookup"><span data-stu-id="4988d-155">At this point, the project needs the Portfolio repository and models contained in the `TraderSys.PortfolioData` class library in the WCF solution.</span></span> <span data-ttu-id="4988d-156">最简单的方法是使用 Visual Studio "**新建项目**" 对话框和 "类库 *（.NET Standard）* " 模板创建一个新的类库，或者使用 .NET Core CLI 从命令行中运行以下命令，从包含 `TraderSys.sln` 文件的目录中运行以下命令。</span><span class="sxs-lookup"><span data-stu-id="4988d-156">The easiest way to bring them across is to create a new class library using either the Visual Studio **New project** dialog with the *Class Library (.NET Standard)* template, or from the command line using the .NET Core CLI, running the following commands from the directory containing the `TraderSys.sln` file.</span></span>

```dotnetcli
dotnet new classlib -o src/TraderSys.PortfolioData
dotnet sln add src/TraderSys.PortfolioData
```

<span data-ttu-id="4988d-157">创建库并将其添加到解决方案后，删除生成的 `Class1.cs` 文件，并将文件从 WCF 解决方案的库复制到新的类库文件夹，同时保留文件夹结构。</span><span class="sxs-lookup"><span data-stu-id="4988d-157">Once the library has been created and added to the solution, delete the generated `Class1.cs` file and copy the files from the WCF solution's library into the new class library's folder, keeping the folder structure.</span></span>

```
Models
  Portfolio.cs
  PortfolioItem.cs
IPortfolioRepository.cs
PortfolioRepository.cs
```

<span data-ttu-id="4988d-158">SDK 样式的 .NET 项目会自动在其自己的目录中包含任何 `.cs` 文件，因此无需将其显式添加到项目。</span><span class="sxs-lookup"><span data-stu-id="4988d-158">SDK-style .NET projects automatically include any `.cs` files in or under their own directory, so there's no need to explicitly add them to the project.</span></span> <span data-ttu-id="4988d-159">剩下的唯一步骤是从 `Portfolio` 和 `PortfolioItem` 类中删除 `DataContract` 和 `DataMember` 属性，使其成为普通旧C#类。</span><span class="sxs-lookup"><span data-stu-id="4988d-159">The only step remaining is to remove the `DataContract` and `DataMember` attributes from the `Portfolio` and `PortfolioItem` classes so they're plain old C# classes.</span></span>

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

## <a name="use-aspnet-core-dependency-injection"></a><span data-ttu-id="4988d-160">使用 ASP.NET Core 依赖关系注入</span><span class="sxs-lookup"><span data-stu-id="4988d-160">Use ASP.NET Core dependency injection</span></span>

<span data-ttu-id="4988d-161">现在可以将对此库的引用添加到 gRPC 应用程序项目，并在 gRPC 服务实现中使用依赖关系注入来使用 `PortfolioRepository` 类。</span><span class="sxs-lookup"><span data-stu-id="4988d-161">Now you can add a reference to this library to the gRPC application project and consume the `PortfolioRepository` class using dependency injection in the gRPC service implementation.</span></span> <span data-ttu-id="4988d-162">在 WCF 应用程序中，依赖关系注入由 Autofac IoC 容器提供。</span><span class="sxs-lookup"><span data-stu-id="4988d-162">In the WCF application, dependency injection was provided by the Autofac IoC container.</span></span> <span data-ttu-id="4988d-163">ASP.NET Core 在中具有依赖关系注入融入;可以在 `Startup` 类的 `ConfigureServices` 方法中注册存储库。</span><span class="sxs-lookup"><span data-stu-id="4988d-163">ASP.NET Core has dependency injection baked in; the repository can be registered in the `ConfigureServices` method in the `Startup` class.</span></span>

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

<span data-ttu-id="4988d-164">现在可以在 `PortfolioService` 类中将 `IPortfolioRepository` 实现指定为构造函数参数，如下所示：</span><span class="sxs-lookup"><span data-stu-id="4988d-164">The `IPortfolioRepository` implementation can now be specified as a constructor parameter in the `PortfolioService` class, as follows:</span></span>

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

## <a name="implement-the-grpc-service"></a><span data-ttu-id="4988d-165">实现 gRPC 服务</span><span class="sxs-lookup"><span data-stu-id="4988d-165">Implement the gRPC service</span></span>

<span data-ttu-id="4988d-166">现在您已在 `portfolios.proto` 文件中声明了您的消息和服务，您必须在 `PortfolioService` 类中实现从 gRPC 生成的 `Portfolios.PortfoliosBase` 类继承的服务方法。</span><span class="sxs-lookup"><span data-stu-id="4988d-166">Now that you've declared your messages and your service in the `portfolios.proto` file, you have to implement the service methods in the `PortfolioService` class that inherits from the gRPC-generated `Portfolios.PortfoliosBase` class.</span></span> <span data-ttu-id="4988d-167">方法在基类中声明为 `virtual`。</span><span class="sxs-lookup"><span data-stu-id="4988d-167">The methods are declared as `virtual` in the base class.</span></span> <span data-ttu-id="4988d-168">如果不重写这些值，则默认情况下，它们将返回 "未实现" 状态代码 gRPC。</span><span class="sxs-lookup"><span data-stu-id="4988d-168">If you don't override them, they'll return a gRPC "Not Implemented" status code by default.</span></span>

<span data-ttu-id="4988d-169">首先实现 `Get` 方法。</span><span class="sxs-lookup"><span data-stu-id="4988d-169">Start by implementing the `Get` method.</span></span> <span data-ttu-id="4988d-170">默认重写类似于以下示例：</span><span class="sxs-lookup"><span data-stu-id="4988d-170">The default override looks like the following example:</span></span>

```csharp
public override Task<GetResponse> Get(GetRequest request, ServerCallContext context)
{
    return base.Get(request, context);
}
```

<span data-ttu-id="4988d-171">第一个问题是，`request.TraderId` 是一个字符串，并且该服务需要 `Guid`。</span><span class="sxs-lookup"><span data-stu-id="4988d-171">The first issue is that `request.TraderId` is a string, and the service requires a `Guid`.</span></span> <span data-ttu-id="4988d-172">即使字符串的预期格式是 `UUID`，代码也必须处理调用方发送了无效值并做出相应响应的可能性。</span><span class="sxs-lookup"><span data-stu-id="4988d-172">Even though the expected format for the string is a `UUID`, the code has to deal with the possibility that a caller has sent an invalid value and respond appropriately.</span></span> <span data-ttu-id="4988d-173">服务可以通过引发 `RpcException`来响应错误，并使用标准 `InvalidArgument` 状态代码来表示问题。</span><span class="sxs-lookup"><span data-stu-id="4988d-173">The service can respond with errors by throwing an `RpcException`, and use the standard `InvalidArgument` status code to express the problem.</span></span>

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

<span data-ttu-id="4988d-174">为 `traderId`提供适当的 `Guid` 值后，可以使用该存储库检索该组合并将其返回到客户端。</span><span class="sxs-lookup"><span data-stu-id="4988d-174">Once there's a proper `Guid` value for `traderId`, the repository can be used to retrieve the Portfolio and return it to the client.</span></span>

```csharp
    var response = new GetResponse
    {
        Portfolio = await _repository.GetAsync(request.TraderId, request.PortfolioId)
    };
```

### <a name="map-internal-models-to-grpc-messages"></a><span data-ttu-id="4988d-175">将内部模型映射到 gRPC 消息</span><span class="sxs-lookup"><span data-stu-id="4988d-175">Map internal models to gRPC messages</span></span>

<span data-ttu-id="4988d-176">前面的代码实际上不起作用，因为存储库返回自己的 POCO 模型 `Portfolio`，但 gRPC 需要*其自己的*Protobuf 消息 `Portfolio`。</span><span class="sxs-lookup"><span data-stu-id="4988d-176">The previous code doesn't actually work because the repository is returning its own POCO model `Portfolio`, but gRPC needs *its* own Protobuf message `Portfolio`.</span></span> <span data-ttu-id="4988d-177">与将实体框架类型映射到数据传输类型非常相似，最佳解决方案是在两者之间提供转换。</span><span class="sxs-lookup"><span data-stu-id="4988d-177">Much like mapping Entity Framework types to data transfer types, the best solution is to provide conversion between the two.</span></span> <span data-ttu-id="4988d-178">放置此代码的好地方是在 Protobuf 生成的类中，该类声明为一个 `partial` 类，因此可对其进行扩展。</span><span class="sxs-lookup"><span data-stu-id="4988d-178">A good place to put the code for this is in the Protobuf-generated class, which is declared as a `partial` class so it can be extended.</span></span>

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
> <span data-ttu-id="4988d-179">您可以使用类似[AutoMapper](https://automapper.org/)的库来处理从内部模型类到 Protobuf 类型的这种转换，前提是配置较低级别的类型转换，如 `string`/`Guid` 或 `decimal`/`double` 和列表映射。</span><span class="sxs-lookup"><span data-stu-id="4988d-179">You could use a library like [AutoMapper](https://automapper.org/) to handle this conversion from internal model classes to Protobuf types, as long as you configure the lower-level type conversions like `string`/`Guid` or `decimal`/`double` and the list mapping.</span></span>

<span data-ttu-id="4988d-180">转换代码准备就绪后，`Get` 方法实现即可完成。</span><span class="sxs-lookup"><span data-stu-id="4988d-180">With the conversion code in place, the `Get` method implementation can be completed.</span></span>

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

<span data-ttu-id="4988d-181">`GetAll` 方法的实现类似。</span><span class="sxs-lookup"><span data-stu-id="4988d-181">The implementation of the `GetAll` method is similar.</span></span> <span data-ttu-id="4988d-182">请注意，Protobuf 消息上的 `repeated` 字段将作为 `RepeatedField<T>`类型的 `readonly` 属性生成，因此你必须使用 `AddRange` 方法向其中添加项，如以下示例中所示：</span><span class="sxs-lookup"><span data-stu-id="4988d-182">Note that the `repeated` fields on Protobuf messages are generated as `readonly` properties of type `RepeatedField<T>`, so you have to add items to them using the `AddRange` method, like in the following example:</span></span>

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

<span data-ttu-id="4988d-183">已成功将 WCF 请求-答复服务迁移到 gRPC，我们来看看如何从 `.proto` 文件创建客户端。</span><span class="sxs-lookup"><span data-stu-id="4988d-183">Having successfully migrated the WCF request-reply service to gRPC, let's look at creating a client for it from the `.proto` file.</span></span>

## <a name="generate-client-code"></a><span data-ttu-id="4988d-184">生成客户端代码</span><span class="sxs-lookup"><span data-stu-id="4988d-184">Generate client code</span></span>

<span data-ttu-id="4988d-185">在同一解决方案中创建 .NET Standard 类库，以包含客户端。</span><span class="sxs-lookup"><span data-stu-id="4988d-185">Create a .NET Standard class library in the same solution to contain the client.</span></span> <span data-ttu-id="4988d-186">这主要是创建客户端代码的示例，但你可以使用 NuGet 打包此类库，并将其分发到供其他 .NET 团队使用的内部存储库中。</span><span class="sxs-lookup"><span data-stu-id="4988d-186">This is primarily an example of creating client code, but you could package such a library using NuGet and distribute it on an internal repository for other .NET teams to consume.</span></span> <span data-ttu-id="4988d-187">继续并向解决方案添加名为 `TraderSys.Portfolios.Client` 的新 .NET Standard 类库，并删除 `Class1.cs` 文件。</span><span class="sxs-lookup"><span data-stu-id="4988d-187">Go ahead and add a new .NET Standard Class Library called `TraderSys.Portfolios.Client` to the solution and delete the `Class1.cs` file.</span></span>

> [!CAUTION]
> <span data-ttu-id="4988d-188">[Grpc](https://www.nuget.org/packages/Grpc.Net.Client) NuGet 包需要 .net Core 3.0 （或另 .NET Standard 一个与2.1 兼容的运行时）。</span><span class="sxs-lookup"><span data-stu-id="4988d-188">The [Grpc.Net.Client](https://www.nuget.org/packages/Grpc.Net.Client) NuGet package requires .NET Core 3.0 (or another .NET Standard 2.1-compliant runtime).</span></span> <span data-ttu-id="4988d-189">[Grpc](https://www.nuget.org/packages/Grpc.Core) NuGet 包支持早期版本的 .NET FRAMEWORK 和 .net Core。</span><span class="sxs-lookup"><span data-stu-id="4988d-189">Earlier versions of .NET Framework and .NET Core are supported by the [Grpc.Core](https://www.nuget.org/packages/Grpc.Core) NuGet package.</span></span>

<span data-ttu-id="4988d-190">在 Visual Studio 2019 中，可以添加对 gRPC services 的引用，就像在 Visual Studio 的早期版本中将服务引用添加到 WCF 项目一样。</span><span class="sxs-lookup"><span data-stu-id="4988d-190">In Visual Studio 2019, you can add references to gRPC services similar to the way you'd add Service References to WCF projects in earlier versions of Visual Studio.</span></span> <span data-ttu-id="4988d-191">服务引用和连接的服务现在都是在同一个 UI 下管理的，你可以通过右键单击解决方案资源管理器中 `TraderSys.Portfolios.Client` 项目中的 "**依赖项**" 节点，然后选择 "**添加连接的服务**" 来访问它。</span><span class="sxs-lookup"><span data-stu-id="4988d-191">Service References and Connected Services are all managed under the same UI now, which you can access by right-clicking the **Dependencies** node in the `TraderSys.Portfolios.Client` project in Solution Explorer and selecting **Add Connected Service**.</span></span> <span data-ttu-id="4988d-192">在出现的工具窗口中，选择 "**服务引用**" 部分，然后单击 "**添加新的 gRPC 服务引用**"。</span><span class="sxs-lookup"><span data-stu-id="4988d-192">In the tool window that appears, select the **Service References** section and click **Add new gRPC service reference**.</span></span>

![Visual Studio 2019 中的连接的服务 UI](media/migrate-request-reply/add-connected-service.png)

<span data-ttu-id="4988d-194">浏览到 `TraderSys.Portfolios` 项目中的 `portfolios.proto` 文件，将**类的类型**保留为 "**客户端**"，然后单击 **"确定"** 。</span><span class="sxs-lookup"><span data-stu-id="4988d-194">Browse to the `portfolios.proto` file in the `TraderSys.Portfolios` project, leave the **type of class to be generated** as **Client**, and click **OK**.</span></span>

![Visual Studio 2019 中的 "添加新的 gRPC 服务引用" 对话框](media/migrate-request-reply/add-new-grpc-service-reference.png)

> [!TIP]
> <span data-ttu-id="4988d-196">请注意，此对话框还提供了 "URL" 字段。</span><span class="sxs-lookup"><span data-stu-id="4988d-196">Notice that this dialog also provides a URL field.</span></span> <span data-ttu-id="4988d-197">如果你的组织维护 `.proto` 文件的 web 访问目录，你只需通过设置此 URL 地址即可创建客户端。</span><span class="sxs-lookup"><span data-stu-id="4988d-197">If your organization maintains a web-accessible directory of `.proto` files, you can create clients just by setting this URL address.</span></span>

<span data-ttu-id="4988d-198">当使用 Visual Studio 的 "**添加连接服务**" 功能时，`portfolios.proto` 文件将作为*链接文件*添加到类库项目中，而不是复制，因此，对服务项目中的文件所做的更改将自动应用到客户端项目中。</span><span class="sxs-lookup"><span data-stu-id="4988d-198">When using the Visual Studio **Add Connected Service** feature, the `portfolios.proto` file is added to the Class Library project as a *linked file*, rather than copied, so changes to the file in the service project will automatically be applied in the client project.</span></span> <span data-ttu-id="4988d-199">`csproj` 文件中的 `<Protobuf>` 元素如下所示：</span><span class="sxs-lookup"><span data-stu-id="4988d-199">The `<Protobuf>` element in the `csproj` file looks like this:</span></span>

```xml
<Protobuf Include="..\TraderSys.Portfolios\Protos\portfolios.proto" GrpcServices="Client">
  <Link>Protos\portfolios.proto</Link>
</Protobuf>
```

> [!TIP]
> <span data-ttu-id="4988d-200">如果使用的不是 Visual Studio 或想要从命令行运行，则可以使用**dotnet-grpc**全局工具来管理 .net grpc 项目中的 Protobuf 引用。</span><span class="sxs-lookup"><span data-stu-id="4988d-200">If you are not using Visual Studio or prefer to work from the command line, you can use the **dotnet-grpc** global tool to manage Protobuf references within a .NET gRPC project.</span></span> <span data-ttu-id="4988d-201">[有关详细信息，请参阅**dotnet-grpc**文档](https://docs.microsoft.com/aspnet/core/grpc/dotnet-grpc)。</span><span class="sxs-lookup"><span data-stu-id="4988d-201">[Refer to the **dotnet-grpc** documentation for more information](https://docs.microsoft.com/aspnet/core/grpc/dotnet-grpc).</span></span>

### <a name="use-the-portfolios-service-from-a-client-application"></a><span data-ttu-id="4988d-202">使用客户端应用程序中的 "包" 服务</span><span class="sxs-lookup"><span data-stu-id="4988d-202">Use the Portfolios service from a client application</span></span>

<span data-ttu-id="4988d-203">下面的代码是在控制台应用程序中使用生成的客户端的简单示例。</span><span class="sxs-lookup"><span data-stu-id="4988d-203">The following code is a brief example of using the generated client in a console application.</span></span> <span data-ttu-id="4988d-204">本章末尾详细探讨了 gRPC 客户端代码。</span><span class="sxs-lookup"><span data-stu-id="4988d-204">A more detailed exploration of the gRPC client code is at the end of this chapter.</span></span>

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

<span data-ttu-id="4988d-205">现在，已将基本 WCF 应用程序迁移到 ASP.NET Core gRPC 服务并创建了客户端，以便从 .NET 应用程序使用该服务。</span><span class="sxs-lookup"><span data-stu-id="4988d-205">Now, you've migrated a basic WCF application to an ASP.NET Core gRPC service and created a client to consume the service from a .NET application.</span></span> <span data-ttu-id="4988d-206">下一节将介绍更多的 "双工" 服务。</span><span class="sxs-lookup"><span data-stu-id="4988d-206">The next section will cover the more involved "duplex" services.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="4988d-207">[上一页](create-project.md)
>[下一页](migrate-duplex-services.md)</span><span class="sxs-lookup"><span data-stu-id="4988d-207">[Previous](create-project.md)
[Next](migrate-duplex-services.md)</span></span>
