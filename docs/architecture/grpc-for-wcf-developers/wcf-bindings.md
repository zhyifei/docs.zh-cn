---
title: Wcf 绑定和传输-适用于 WCF 开发人员的 gRPC
description: 了解不同的 WCF 绑定和传输如何与 gRPC 进行比较。
ms.date: 09/02/2019
ms.openlocfilehash: ebe324eace8f5f418b920c59f6d72eaaa686ef02
ms.sourcegitcommit: f38e527623883b92010cf4760246203073e12898
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/20/2020
ms.locfileid: "77503352"
---
# <a name="wcf-bindings-and-transports"></a><span data-ttu-id="56467-103">WCF 绑定和传输</span><span class="sxs-lookup"><span data-stu-id="56467-103">WCF bindings and transports</span></span>

<span data-ttu-id="56467-104">Windows Communication Foundation （WCF）具有指定不同网络协议、传输格式和其他实现详细信息的内置*绑定*。</span><span class="sxs-lookup"><span data-stu-id="56467-104">Windows Communication Foundation (WCF) has built-in *bindings* that specify different network protocols, wire formats, and other implementation details.</span></span> <span data-ttu-id="56467-105">gRPC 实际上只有一个网络协议和一种网络格式。</span><span class="sxs-lookup"><span data-stu-id="56467-105">gRPC effectively has just one network protocol and one wire format.</span></span> <span data-ttu-id="56467-106">（从技术上讲，你*可以*自定义网络格式，但这超出了本书的范围。）在大多数情况下，你可能会发现 gRPC 提供了最佳解决方案。</span><span class="sxs-lookup"><span data-stu-id="56467-106">(Technically you *can* customize the wire format, but that's beyond the scope of this book.) You're likely to discover that gRPC offers the best solution in most cases.</span></span> 

<span data-ttu-id="56467-107">下面是有关最相关的 WCF 绑定的简短讨论，以及它们如何与 gRPC 中的等效项进行比较。</span><span class="sxs-lookup"><span data-stu-id="56467-107">What follows is a short discussion about the most relevant WCF bindings and how they compare to their equivalents in gRPC.</span></span>

## <a name="nettcp"></a><span data-ttu-id="56467-108">Wcf-nettcp</span><span class="sxs-lookup"><span data-stu-id="56467-108">NetTCP</span></span>

<span data-ttu-id="56467-109">WCF 的 Wcf-nettcp 绑定允许永久性连接、小消息和双向消息传递。</span><span class="sxs-lookup"><span data-stu-id="56467-109">WCF's NetTCP binding allows for persistent connections, small messages, and two-way messaging.</span></span> <span data-ttu-id="56467-110">但它仅适用于 .NET 客户端和服务器。</span><span class="sxs-lookup"><span data-stu-id="56467-110">But it works only between .NET clients and servers.</span></span> <span data-ttu-id="56467-111">gRPC 允许相同的功能，但跨多个编程语言和平台支持。</span><span class="sxs-lookup"><span data-stu-id="56467-111">gRPC allows the same functionality but is supported across multiple programming languages and platforms.</span></span> 

<span data-ttu-id="56467-112">gRPC 具有 WCF 的 Wcf-nettcp 绑定的许多功能，但并不总是以相同的方式实现。</span><span class="sxs-lookup"><span data-stu-id="56467-112">gRPC has many features of WCF's NetTCP binding, but they're not always implemented in the same way.</span></span> <span data-ttu-id="56467-113">例如，在 WCF 中，通过配置控制加密，并在框架中进行处理。</span><span class="sxs-lookup"><span data-stu-id="56467-113">For example, in WCF, encryption is controlled through configuration and handled in the framework.</span></span> <span data-ttu-id="56467-114">在 gRPC 中，通过 TLS 上的 HTTP/2 在连接级别实现加密。</span><span class="sxs-lookup"><span data-stu-id="56467-114">In gRPC, encryption is achieved at the connection level through HTTP/2 over TLS.</span></span>

## <a name="http"></a><span data-ttu-id="56467-115">HTTP</span><span class="sxs-lookup"><span data-stu-id="56467-115">HTTP</span></span>

<span data-ttu-id="56467-116">调用 BasicHttpBinding 的 WCF 绑定通常基于文本，并使用 SOAP 作为网络格式。</span><span class="sxs-lookup"><span data-stu-id="56467-116">The WCF binding called BasicHttpBinding is usually text based and uses SOAP as the wire format.</span></span> <span data-ttu-id="56467-117">与 Wcf-nettcp 绑定相比，此方法更慢。</span><span class="sxs-lookup"><span data-stu-id="56467-117">It's slow compared to the NetTCP binding.</span></span> <span data-ttu-id="56467-118">它通常用于提供跨平台的互操作性或通过 internet 基础结构进行连接。</span><span class="sxs-lookup"><span data-stu-id="56467-118">It's generally used to provide cross-platform interoperability, or connection over internet infrastructure.</span></span> 

<span data-ttu-id="56467-119">GRPC 中的等效项使用 HTTP/2 作为消息的二进制 Protobuf 线路格式的基础传输层。</span><span class="sxs-lookup"><span data-stu-id="56467-119">The equivalent in gRPC uses HTTP/2 as the underlying transport layer with the binary Protobuf wire format for messages.</span></span> <span data-ttu-id="56467-120">因此，它可以在 Wcf-nettcp 服务级别提供性能，并通过所有新式编程语言和框架实现跨平台完全互操作性。</span><span class="sxs-lookup"><span data-stu-id="56467-120">So it can offer performance at the NetTCP service level and full cross-platform interoperability with all modern programming languages and frameworks.</span></span>

## <a name="named-pipes"></a><span data-ttu-id="56467-121">Named pipes</span><span class="sxs-lookup"><span data-stu-id="56467-121">Named pipes</span></span>

<span data-ttu-id="56467-122">WCF 提供了一个*命名管道*绑定，用于在同一物理计算机上的进程之间进行通信。</span><span class="sxs-lookup"><span data-stu-id="56467-122">WCF provided a *named pipes* binding for communication between processes on the same physical machine.</span></span> <span data-ttu-id="56467-123">ASP.NET Core gRPC 的第一个版本不支持命名管道。</span><span class="sxs-lookup"><span data-stu-id="56467-123">The first release of ASP.NET Core gRPC does not support named pipes.</span></span> <span data-ttu-id="56467-124">为命名管道（和 Unix 域套接字）添加客户端和服务器支持是将来版本的目标。</span><span class="sxs-lookup"><span data-stu-id="56467-124">Adding client and server support for named pipes (and Unix domain sockets) is a goal for a future release.</span></span>

## <a name="msmq"></a><span data-ttu-id="56467-125">MSMQ</span><span class="sxs-lookup"><span data-stu-id="56467-125">MSMQ</span></span>

<span data-ttu-id="56467-126">MSMQ 是专有的 Windows 消息队列。</span><span class="sxs-lookup"><span data-stu-id="56467-126">MSMQ is a proprietary Windows message queue.</span></span> <span data-ttu-id="56467-127">通过 WCF 绑定到 MSMQ，可以在将来随时处理的客户端发出 "火灾" 和 "忘记" 请求。</span><span class="sxs-lookup"><span data-stu-id="56467-127">WCF's binding to MSMQ enables "fire and forget" requests from clients that might be processed at any time in the future.</span></span> <span data-ttu-id="56467-128">gRPC 本身不提供任何消息队列功能。</span><span class="sxs-lookup"><span data-stu-id="56467-128">gRPC doesn't natively provide any message queue functionality.</span></span> 

<span data-ttu-id="56467-129">最佳的替代方法是直接使用消息传递系统，如 Azure 服务总线、RabbitMQ 或 Kafka。</span><span class="sxs-lookup"><span data-stu-id="56467-129">The best alternative is to directly use a messaging system like Azure Service Bus, RabbitMQ, or Kafka.</span></span> <span data-ttu-id="56467-130">可以通过将消息直接放入队列的客户端实现此，也可以使用 gRPC 客户端流式处理服务（排队消息）来实现。</span><span class="sxs-lookup"><span data-stu-id="56467-130">You can implement this with the client placing messages directly onto the queue, or a gRPC client streaming service that enqueues the messages.</span></span>

## <a name="webhttpbinding"></a><span data-ttu-id="56467-131">WebHttpBinding</span><span class="sxs-lookup"><span data-stu-id="56467-131">WebHttpBinding</span></span>

<span data-ttu-id="56467-132">WebHttpBinding （也称为 WCF REST），具有 `WebGet` 和 `WebInvoke` 属性，使你能够开发 RESTful Api，在这种情况不太常见的情况下，可能会说出 JSON。</span><span class="sxs-lookup"><span data-stu-id="56467-132">WebHttpBinding (also known as WCF REST), with the `WebGet` and `WebInvoke` attributes, enabled you to develop RESTful APIs that could speak JSON at a time when this was less common.</span></span> <span data-ttu-id="56467-133">如果有使用 WCF REST 生成的 RESTful API，请考虑将其迁移到常规 ASP.NET Core MVC Web API 应用程序。</span><span class="sxs-lookup"><span data-stu-id="56467-133">If you have a RESTful API built with WCF REST, consider migrating it to a regular ASP.NET Core MVC Web API application.</span></span> <span data-ttu-id="56467-134">此迁移将提供与转换为 gRPC 相同的功能。</span><span class="sxs-lookup"><span data-stu-id="56467-134">This migration would provide the same functionality as a conversion to gRPC.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="56467-135">[上一页](wcf-endpoints-grpc-methods.md)
>[下一页](rpc-types.md)</span><span class="sxs-lookup"><span data-stu-id="56467-135">[Previous](wcf-endpoints-grpc-methods.md)
[Next](rpc-types.md)</span></span>
