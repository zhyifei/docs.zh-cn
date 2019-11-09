---
title: Wcf 绑定和传输-适用于 WCF 开发人员的 gRPC
description: 了解不同的 WCF 绑定和传输如何与 gRPC 进行比较。
author: markrendle
ms.date: 09/02/2019
ms.openlocfilehash: 34321395ddd7059ac7e3c268e313a03251662911
ms.sourcegitcommit: 337bdc5a463875daf2cc6883e5a2da97d56f5000
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/24/2019
ms.locfileid: "73841317"
---
# <a name="wcf-bindings-and-transports"></a><span data-ttu-id="afa6c-103">WCF 绑定和传输</span><span class="sxs-lookup"><span data-stu-id="afa6c-103">WCF bindings and transports</span></span>

<span data-ttu-id="afa6c-104">WCF 具有许多不同的内置*绑定*，它们指定不同的网络协议、线路格式和其他实现详细信息。</span><span class="sxs-lookup"><span data-stu-id="afa6c-104">WCF has lots of different built-in *bindings* that specify different network protocols, wire formats, and other implementation details.</span></span> <span data-ttu-id="afa6c-105">gRPC 实际上只包含一个网络协议和一种线路格式（从技术上讲，*可以*自定义网络格式，但这超出了本书的范围）。</span><span class="sxs-lookup"><span data-stu-id="afa6c-105">gRPC effectively has just one network protocol and one wire format (technically the wire format *may* be customized, but that is beyond the scope of this book).</span></span> <span data-ttu-id="afa6c-106">在大多数情况下，你可能会发现 gRPC 提供了最佳解决方案。</span><span class="sxs-lookup"><span data-stu-id="afa6c-106">You are likely to discover that gRPC offers the best solution in most cases.</span></span> <span data-ttu-id="afa6c-107">下面是有关最相关的 WCF 绑定的简短讨论，以及它们如何与 gRPC 中的等效项进行比较。</span><span class="sxs-lookup"><span data-stu-id="afa6c-107">What follows is a short discussion about the most relevant WCF bindings and how they compare to their equivalent in gRPC.</span></span>

## <a name="nettcp"></a><span data-ttu-id="afa6c-108">Wcf-nettcp</span><span class="sxs-lookup"><span data-stu-id="afa6c-108">NetTCP</span></span>

<span data-ttu-id="afa6c-109">WCF 的 Wcf-nettcp 绑定允许永久性连接、小消息和双向消息传递，但只能在 .NET 客户端和服务器之间工作。</span><span class="sxs-lookup"><span data-stu-id="afa6c-109">WCF's NetTCP binding allows for persistent connections, small messages, and two-way messaging but only works between .NET clients and servers.</span></span> <span data-ttu-id="afa6c-110">gRPC 允许相同的功能，但跨多个编程语言和平台支持。</span><span class="sxs-lookup"><span data-stu-id="afa6c-110">gRPC allows the same functionality but is supported across multiple programming languages and platforms.</span></span> <span data-ttu-id="afa6c-111">gRPC 具有 WCF Wcf-nettcp 绑定的许多功能，但并不总是以相同的方式实现。</span><span class="sxs-lookup"><span data-stu-id="afa6c-111">gRPC has many of the features of WCF NetTCP binding, although not always implemented in the same way.</span></span> <span data-ttu-id="afa6c-112">例如，在 WCF 中，通过配置控制加密，并在框架中进行处理。</span><span class="sxs-lookup"><span data-stu-id="afa6c-112">For example, in WCF, encryption is controlled through configuration and handled in the framework.</span></span> <span data-ttu-id="afa6c-113">在 gRPC 中，使用 HTTP/2 over TLS 在连接级别实现加密。</span><span class="sxs-lookup"><span data-stu-id="afa6c-113">In gRPC, encryption is achieved at the connection level using HTTP/2 over TLS.</span></span>

## <a name="http"></a><span data-ttu-id="afa6c-114">HTTP</span><span class="sxs-lookup"><span data-stu-id="afa6c-114">HTTP</span></span>

<span data-ttu-id="afa6c-115">WCF 的 BasicHttpBinding 通常是基于文本的，它使用 SOAP 作为线路格式，并且比 Wcf-nettcp 绑定慢。</span><span class="sxs-lookup"><span data-stu-id="afa6c-115">WCF's BasicHttpBinding is usually text based, using SOAP as the wire format, and is slow compared to the NetTCP binding.</span></span> <span data-ttu-id="afa6c-116">它通常用于提供跨平台的互操作性或通过 internet 基础结构进行连接。</span><span class="sxs-lookup"><span data-stu-id="afa6c-116">It's generally used to provide cross-platform interoperability, or connection over internet infrastructure.</span></span> <span data-ttu-id="afa6c-117">GRPC 中的等效项，因为它使用 HTTP/2 作为消息的二进制 Protobuf 传输层的基础传输层，可以提供 Wcf-nettcp 的服务级别性能，但具有与所有新式编程语言和框架的完全跨平台互操作性。</span><span class="sxs-lookup"><span data-stu-id="afa6c-117">The equivalent in gRPC—because it uses HTTP/2 as the underlying transport layer with the binary Protobuf wire format for messages—can offer NetTCP service level performance but with full cross-platform interoperability with all modern programming languages and frameworks.</span></span>

## <a name="named-pipes"></a><span data-ttu-id="afa6c-118">命名管道</span><span class="sxs-lookup"><span data-stu-id="afa6c-118">Named Pipes</span></span>

<span data-ttu-id="afa6c-119">WCF 提供了一个命名管道绑定，用于在同一物理计算机上的进程之间进行通信。</span><span class="sxs-lookup"><span data-stu-id="afa6c-119">WCF provided a Named Pipes binding for communication between processes on the same physical machine.</span></span> <span data-ttu-id="afa6c-120">ASP.NET Core gRPC 的第一个版本不支持命名管道。</span><span class="sxs-lookup"><span data-stu-id="afa6c-120">Named pipes are not supported by the first release of ASP.NET Core gRPC.</span></span> <span data-ttu-id="afa6c-121">为命名管道（和 Unix 域套接字）添加客户端和服务器支持是将来版本的目标。</span><span class="sxs-lookup"><span data-stu-id="afa6c-121">Adding client and server support for named pipes (and Unix domain sockets) is a goal for a future release.</span></span>

## <a name="msmq"></a><span data-ttu-id="afa6c-122">MSMQ</span><span class="sxs-lookup"><span data-stu-id="afa6c-122">MSMQ</span></span>

<span data-ttu-id="afa6c-123">MSMQ 是专有的 Windows 消息队列。</span><span class="sxs-lookup"><span data-stu-id="afa6c-123">MSMQ is a proprietary Windows message queue.</span></span> <span data-ttu-id="afa6c-124">通过 WCF 绑定到 MSMQ，可以在将来随时处理的客户端发出 "火灾" 和 "忘记" 请求。</span><span class="sxs-lookup"><span data-stu-id="afa6c-124">WCF's binding to MSMQ enables "fire and forget" requests from clients that may be processed at any time in the future.</span></span> <span data-ttu-id="afa6c-125">gRPC 本身不提供任何消息队列功能。</span><span class="sxs-lookup"><span data-stu-id="afa6c-125">gRPC doesn't natively provide any message queue functionality.</span></span> <span data-ttu-id="afa6c-126">最佳的替代方法是直接使用消息传递系统，例如 Azure 服务总线、RabbitMQ 或 Kafka。</span><span class="sxs-lookup"><span data-stu-id="afa6c-126">The best alternative would be to directly use a messaging system like Azure Service Bus, RabbitMQ, or Kafka.</span></span> <span data-ttu-id="afa6c-127">这可以通过将消息直接放入队列的客户端来实现，也可以使用 gRPC 客户端流式处理服务（排队消息）来实现。</span><span class="sxs-lookup"><span data-stu-id="afa6c-127">This could be implemented with the client placing messages directly onto the queue, or a gRPC client streaming service that enqueues the messages.</span></span>

## <a name="webhttpbinding"></a><span data-ttu-id="afa6c-128">WebHttpBinding</span><span class="sxs-lookup"><span data-stu-id="afa6c-128">WebHttpBinding</span></span>

<span data-ttu-id="afa6c-129">使用 "`WebGet`" 和 "`WebInvoke`" 属性的 WebHttpBinding （也称为 WCF ReST），可以开发 ReSTful Api，在这种情况不太常见的情况下，这些 Api 可能会说出 JSON。</span><span class="sxs-lookup"><span data-stu-id="afa6c-129">The WebHttpBinding (also known as WCF ReST), with the `WebGet` and `WebInvoke` attributes, enabled you to develop ReSTful APIs that could speak JSON at a time when this was less common than now.</span></span> <span data-ttu-id="afa6c-130">因此，如果你有使用 WCF REST 生成的 RESTful API，请考虑将其迁移到常规 ASP.NET Core MVC Web API 应用程序，该应用程序将提供等效的功能，而不是转换为 gRPC。</span><span class="sxs-lookup"><span data-stu-id="afa6c-130">Therefore, if you have a RESTful API built with WCF REST, consider migrating it to a regular ASP.NET Core MVC Web API application, which would provide equivalent functionality, rather than converting to gRPC.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="afa6c-131">[上一页](wcf-endpoints-grpc-methods.md)
>[下一页](rpc-types.md)</span><span class="sxs-lookup"><span data-stu-id="afa6c-131">[Previous](wcf-endpoints-grpc-methods.md)
[Next](rpc-types.md)</span></span>
