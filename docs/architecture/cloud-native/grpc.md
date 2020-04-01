---
title: gRPC
description: 了解 gRPC 及其在云原生应用程序中的角色，以及它与 HTTP RESTful 通信有何不同。
author: robvet
ms.date: 03/31/2020
ms.openlocfilehash: 28a07ad5ec105d3fc5b65e4cf0ac0cd85eb16627
ms.sourcegitcommit: 79b0dd8bfc63f33a02137121dd23475887ecefda
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/01/2020
ms.locfileid: "80524207"
---
# <a name="grpc"></a>gRPC

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

到目前为止，在这本书中，我们专注于[基于REST](https://docs.microsoft.com/azure/architecture/best-practices/api-design)的沟通。 我们已经看到 REST 是一种灵活的体系结构风格，它根据实体资源定义基于 CRUD 的操作。 客户端使用请求/响应通信模型跨 HTTP 与资源进行交互。 虽然 REST 得到了广泛实施，但一种较新的通信技术 gRPC 在整个云原生社区中获得了巨大的发展势头。

## <a name="what-is-grpc"></a>什么是 gRPC？

gRPC 是一个现代的高性能框架，它发展古老的[远程过程调用 （RPC）](https://en.wikipedia.org/wiki/Remote_procedure_call)协议。 在应用程序级别，gRPC 简化了客户端和后端服务之间的消息传递。 gRPC 源自 Google，是云[原生产品云原生计算基础 （CNCF）](https://www.cncf.io/)生态系统的一部分。 CNCF认为gRPC是一个[孵化项目](https://github.com/cncf/toc/blob/master/process/graduation_criteria.adoc)。 孵化意味着最终用户在生产应用程序中使用该技术，并且项目具有大量贡献者。

典型的 gRPC 客户端应用将公开实现业务操作的本地进程内函数。 在封面下，该本地函数调用远程计算机上的另一个函数。 看似本地呼叫的内容实质上变成了对远程服务的透明进程外调用。 RPC 管道抽象了计算机之间的点对点网络通信、序列化和执行。

在云原生应用程序中，开发人员通常跨编程语言、框架和技术工作。 这种*互操作性*使消息协定和跨平台通信所需的管道复杂化。  gRPC 提供了一个"统一的水平层"，用于抽象这些关注点。 开发人员在其本机平台中的代码侧重于业务功能，而 gRPC 处理通信管道。

gRPC 在最流行的开发堆栈中提供全面支持，包括 Java、JavaScript、C#、Go、Swift 和 NodeJS。

## <a name="grpc-benefits"></a>gRPC 优势

gRPC 使用 HTTP/2 进行传输协议。 虽然 HTTP/2 与 HTTP 1.1 兼容，但具有许多高级功能：

- 用于数据传输的二进制协议 - 与 HTTP 1.1 不同，HTTP 1.1 以明文形式发送数据。
- 跨行支持通过同一连接发送多个并行请求 - HTTP 1.1 将处理限制为一次一个请求/响应消息。
- 双向全双工通信，用于同时发送客户端请求和服务器响应。
- 内置流式处理，支持对异步流大型数据集的请求和响应。

gRPC 重量轻，性能高。 与 JSON 序列化相比，其速度可能高达 8 倍，消息小 60-80%。 用微软[视窗通信基金会（WCF）](https://docs.microsoft.com/dotnet/framework/wcf/whats-wcf)的话说，gRPC性能超过了高度优化的[NetTCP绑定](https://docs.microsoft.com/dotnet/api/system.servicemodel.nettcpbinding?view=netframework-4.8)的速度和效率。 与支持微软堆栈的 NetTCP 不同，gRPC 是跨平台的。

## <a name="protocol-buffers"></a>协议缓冲区

gRPC 采用一种称为[协议缓冲区的](https://developers.google.com/protocol-buffers/docs/overview)开源技术。 它们为序列化服务相互发送的结构化消息提供了高效且平台中立的序列化格式。 使用跨平台接口定义语言 （IDL），开发人员为每个微服务定义服务协定。 协定作为基于`.proto`文本的文件实现，描述每个服务的方法、输入和输出。 相同的合同文件可用于在不同开发平台上构建的 gRPC 客户端和服务。

使用 proto 文件 Protobuf 编译器`protoc`，为您的目标平台生成客户端和服务代码。 该代码包括以下组件：

- 由客户端和服务共享的强类型对象，表示消息的服务操作和数据元素。
- 具有远程 gRPC 服务可以继承和扩展所需的网络管道的强类型基类。
- 包含调用远程 gRPC 服务所需的管道的客户端存根。

在运行时，每条消息都序列化为标准 Protobuf 表示形式，并在客户端和远程服务之间交换。 与 JSON 或 XML 不同，Protobuf 消息被序列化为编译的二进制字节。

该书名为[gRPC，适用于 WCF 开发人员](https://docs.microsoft.com/dotnet/architecture/grpc-for-wcf-developers/)，可从 Microsoft 体系结构网站获得，提供 gRPC 和协议缓冲区的深入覆盖。

## <a name="grpc-support-in-net"></a>gRPC 支持 .NET

gRPC 集成到 .NET 核心 3.0 SDK 或更高版本中。 以下工具支持它：

- Visual Studio 2019，版本 16.3 或更高版本，安装了 Web 开发工作负载。
- Visual Studio Code
- 点网 CLI

SDK 包括用于端点路由、内置 IoC 和日志记录的工具。 开源 Kestrel Web 服务器支持 HTTP/2 连接。 图 4-20 显示了 Visual Studio 2019 模板，该模板为 gRPC 服务的脚架式骨架项目提供了支架。 请注意 .NET Core 如何完全支持 Windows、Linux 和 macOS。

![gRPC 支持视觉工作室 2019](./media/visual-studio-2019-grpc-template.png)

图 4-20****。 gRPC 支持视觉工作室 2019
  
图 4-21 显示了从 Visual Studio 2019 中包含的内置基架生成的骨架 gRPC 服务。  

![gRPC 项目在视觉工作室 2019](./media/grpc-project.png  )

图 4-21****。 gRPC 项目在视觉工作室 2019

在上图中，请注意原型描述文件和服务代码。 正如您稍后看到的，Visual Studio 会在启动类和基础项目文件中生成其他配置。

## <a name="grpc-usage"></a>gRPC 使用情况

以下方案有利于 gRPC：

- 同步后端微服务到微服务通信，需要立即响应才能继续处理。
- 需要支持混合编程平台的多面体环境。
- 低延迟和高吞吐量通信，其中性能至关重要。
- 点对点实时通信 - gRPC 无需轮询即可实时推送消息，并且对双向流流具有出色的支持。
- 网络受限环境 – 二进制 gRPC 消息始终小于等效的基于文本的 JSON 消息。

在撰写本文时，gRPC 主要用于后端服务。 大多数现代浏览器无法提供支持前端 gRPC 客户端所需的 HTTP/2 控制级别。 也就是说，有一[个早期计划](https://devblogs.microsoft.com/aspnet/grpc-web-experiment/)，支持 gRPC 通信从基于浏览器的应用程序构建与 JavaScript 或 Blazor WebAssembly 技术。 [gRPC-Web 表示 .NET，](https://github.com/grpc/grpc/blob/master/doc/PROTOCOL-WEB.md)支持ASP.NET核心 gRPC 应用，以支持浏览器应用中的 gRPC 功能：

- 强类型代码生成的客户端
- 紧凑型 Protobuf 消息
- 服务器流式处理

## <a name="grpc-implementation"></a>gRPC 实现

微软的微服务参考体系结构[，即容器上的eShop，](https://github.com/dotnet-architecture/eShopOnContainers)展示了如何在 .NET Core 应用程序中实现 gRPC 服务。 图 4-22 显示了后端体系结构。

![容器上 eShop 的后端体系结构](./media/eshop-with-aggregators.png)

**图 4-22**。 容器上 eShop 的后端体系结构

在上图中，请注意 eShop 如何通过公开多个 API 网关来拥抱[前端模式](https://docs.microsoft.com/azure/architecture/patterns/backends-for-frontends)（BFF） 的后端。 本章前面讨论了 BFF 模式。 密切关注位于 Web 购物 API 网关和后端购物微服务之间的聚合器微服务（灰色）。 聚合器接收来自客户端的单个请求，将其调度到各种微服务，聚合结果，并将它们发送回请求客户端。 此类操作通常需要同步通信才能立即产生响应。 在 eShop 中，聚合器的后端调用使用 gRPC 执行，如图 4-23 所示。

![gRPC 在容器上的 eShop 中](./media/grpc-implementation.png)

图 4-23****。 gRPC 在容器上的 eShop 中

gRPC 通信需要客户端和服务器组件。 在上图中，请注意购物聚合器如何实现 gRPC 客户端。 客户端对后端微服务进行同步 gRPC 调用（红色），每个微服务都实现 gRPC 服务器。 客户端和服务器都利用了 .NET Core 3.0 SDK 的内置 gRPC 管道。 客户端*存根*提供调用远程 gRPC 调用的管道。 服务器端组件提供自定义服务类可以继承和使用 gRPC 管道。

公开 RESTful API 和 gRPC 通信的微服务需要多个终结点来管理流量。 您将打开一个终结点，用于侦听呼叫的 HTTP 流量，为 gRPC 调用打开另一个终结点。 gRPC 终结点必须配置为 gRPC 通信所需的 HTTP/2 协议。

尽管我们努力使微服务与异步通信模式分离，但某些操作需要直接调用。 gRPC 应该是微服务之间直接同步通信的主要选择。 基于 HTTP/2 和协议缓冲区的高性能通信协议使其成为一个完美的选择。

## <a name="looking-ahead"></a>展望未来

展望未来，gRPC 将继续为云本机系统赢得牵引力。 性能优势和易于开发是引人注目的。 但是，REST 可能会出现很长时间。 它擅长公开公开的 API 和向后兼容性原因。

>[!div class="step-by-step"]
>[上一个](service-to-service-communication.md)
>[下一个](service-mesh-communication-infrastructure.md)
