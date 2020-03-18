---
title: WCF 绑定和传输 - gRPC 面向 WCF 开发人员
description: 了解不同的 WCF 绑定和传输与 gRPC 的比较情况。
ms.date: 09/02/2019
ms.openlocfilehash: 3a295268b486578c70c2c98f1d05f89070daaeb3
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79147719"
---
# <a name="wcf-bindings-and-transports"></a><span data-ttu-id="29ba5-103">WCF 绑定和传输</span><span class="sxs-lookup"><span data-stu-id="29ba5-103">WCF bindings and transports</span></span>

<span data-ttu-id="29ba5-104">Windows 通信基础 （WCF） 具有内置*绑定*，用于指定不同的网络协议、线格式和其他实现详细信息。</span><span class="sxs-lookup"><span data-stu-id="29ba5-104">Windows Communication Foundation (WCF) has built-in *bindings* that specify different network protocols, wire formats, and other implementation details.</span></span> <span data-ttu-id="29ba5-105">gRPC 实际上只有一个网络协议和一个线格式。</span><span class="sxs-lookup"><span data-stu-id="29ba5-105">gRPC effectively has just one network protocol and one wire format.</span></span> <span data-ttu-id="29ba5-106">（从技术上讲，*您可以*自定义线格式，但这超出了本书的范围。您可能会发现 gRPC 在大多数情况下提供了最佳解决方案。</span><span class="sxs-lookup"><span data-stu-id="29ba5-106">(Technically you *can* customize the wire format, but that's beyond the scope of this book.) You're likely to discover that gRPC offers the best solution in most cases.</span></span>

<span data-ttu-id="29ba5-107">以下是关于最相关的 WCF 绑定及其与 gRPC 中的等效绑定的比较的简短讨论。</span><span class="sxs-lookup"><span data-stu-id="29ba5-107">What follows is a short discussion about the most relevant WCF bindings and how they compare to their equivalents in gRPC.</span></span>

## <a name="nettcp"></a><span data-ttu-id="29ba5-108">NetTCP</span><span class="sxs-lookup"><span data-stu-id="29ba5-108">NetTCP</span></span>

<span data-ttu-id="29ba5-109">WCF 的 NetTCP 绑定允许持久连接、小消息和双向消息传送。</span><span class="sxs-lookup"><span data-stu-id="29ba5-109">WCF's NetTCP binding allows for persistent connections, small messages, and two-way messaging.</span></span> <span data-ttu-id="29ba5-110">但它仅在 .NET 客户端和服务器之间工作。</span><span class="sxs-lookup"><span data-stu-id="29ba5-110">But it works only between .NET clients and servers.</span></span> <span data-ttu-id="29ba5-111">gRPC 允许相同的功能，但支持跨多个编程语言和平台。</span><span class="sxs-lookup"><span data-stu-id="29ba5-111">gRPC allows the same functionality but is supported across multiple programming languages and platforms.</span></span>

<span data-ttu-id="29ba5-112">gRPC 具有 WCF NetTCP 绑定的许多功能，但它们并不总是以相同的方式实现。</span><span class="sxs-lookup"><span data-stu-id="29ba5-112">gRPC has many features of WCF's NetTCP binding, but they're not always implemented in the same way.</span></span> <span data-ttu-id="29ba5-113">例如，在 WCF 中，加密通过配置进行控制，并在框架中处理。</span><span class="sxs-lookup"><span data-stu-id="29ba5-113">For example, in WCF, encryption is controlled through configuration and handled in the framework.</span></span> <span data-ttu-id="29ba5-114">在 gRPC 中，通过 TLS 的 HTTP/2 在连接级别实现加密。</span><span class="sxs-lookup"><span data-stu-id="29ba5-114">In gRPC, encryption is achieved at the connection level through HTTP/2 over TLS.</span></span>

## <a name="http"></a><span data-ttu-id="29ba5-115">HTTP</span><span class="sxs-lookup"><span data-stu-id="29ba5-115">HTTP</span></span>

<span data-ttu-id="29ba5-116">称为 BasicHttpBinding 的 WCF 绑定通常基于文本，并使用 SOAP 作为线格式。</span><span class="sxs-lookup"><span data-stu-id="29ba5-116">The WCF binding called BasicHttpBinding is usually text based and uses SOAP as the wire format.</span></span> <span data-ttu-id="29ba5-117">与 NetTCP 绑定相比，它的速度很慢。</span><span class="sxs-lookup"><span data-stu-id="29ba5-117">It's slow compared to the NetTCP binding.</span></span> <span data-ttu-id="29ba5-118">它通常用于提供跨平台互操作性或通过 Internet 基础结构进行连接。</span><span class="sxs-lookup"><span data-stu-id="29ba5-118">It's generally used to provide cross-platform interoperability, or connection over internet infrastructure.</span></span>

<span data-ttu-id="29ba5-119">gRPC 中的等效项使用 HTTP/2 作为具有二进制 Protobuf 线格式的消息的基础传输层。</span><span class="sxs-lookup"><span data-stu-id="29ba5-119">The equivalent in gRPC uses HTTP/2 as the underlying transport layer with the binary Protobuf wire format for messages.</span></span> <span data-ttu-id="29ba5-120">因此，它可以提供 NetTCP 服务级别的性能，并与所有现代编程语言和框架实现全跨平台互操作性。</span><span class="sxs-lookup"><span data-stu-id="29ba5-120">So it can offer performance at the NetTCP service level and full cross-platform interoperability with all modern programming languages and frameworks.</span></span>

## <a name="named-pipes"></a><span data-ttu-id="29ba5-121">Named pipes</span><span class="sxs-lookup"><span data-stu-id="29ba5-121">Named pipes</span></span>

<span data-ttu-id="29ba5-122">WCF 提供了一*个命名管道*绑定，用于在同一物理计算机上的进程之间的通信。</span><span class="sxs-lookup"><span data-stu-id="29ba5-122">WCF provided a *named pipes* binding for communication between processes on the same physical machine.</span></span> <span data-ttu-id="29ba5-123">ASP.NET核心 gRPC 的第一个版本不支持命名管道。</span><span class="sxs-lookup"><span data-stu-id="29ba5-123">The first release of ASP.NET Core gRPC does not support named pipes.</span></span> <span data-ttu-id="29ba5-124">添加命名管道（和 Unix 域套接字）的客户端和服务器支持是未来版本的目标。</span><span class="sxs-lookup"><span data-stu-id="29ba5-124">Adding client and server support for named pipes (and Unix domain sockets) is a goal for a future release.</span></span>

## <a name="msmq"></a><span data-ttu-id="29ba5-125">MSMQ</span><span class="sxs-lookup"><span data-stu-id="29ba5-125">MSMQ</span></span>

<span data-ttu-id="29ba5-126">MSMQ 是一个专有的 Windows 消息队列。</span><span class="sxs-lookup"><span data-stu-id="29ba5-126">MSMQ is a proprietary Windows message queue.</span></span> <span data-ttu-id="29ba5-127">WCF 与 MSMQ 的绑定允许来自客户端的"触发和忘记"请求，这些请求将来可能随时处理。</span><span class="sxs-lookup"><span data-stu-id="29ba5-127">WCF's binding to MSMQ enables "fire and forget" requests from clients that might be processed at any time in the future.</span></span> <span data-ttu-id="29ba5-128">gRPC 不本机提供任何消息队列功能。</span><span class="sxs-lookup"><span data-stu-id="29ba5-128">gRPC doesn't natively provide any message queue functionality.</span></span>

<span data-ttu-id="29ba5-129">最好的选择是直接使用消息传递系统，如 Azure 服务总线、兔子MQ或 Kafka。</span><span class="sxs-lookup"><span data-stu-id="29ba5-129">The best alternative is to directly use a messaging system like Azure Service Bus, RabbitMQ, or Kafka.</span></span> <span data-ttu-id="29ba5-130">可以通过将消息直接放在队列上的客户端或对消息进行排队的 gRPC 客户端流服务来实现此项。</span><span class="sxs-lookup"><span data-stu-id="29ba5-130">You can implement this with the client placing messages directly onto the queue, or a gRPC client streaming service that enqueues the messages.</span></span>

## <a name="webhttpbinding"></a><span data-ttu-id="29ba5-131">WebHttpBinding</span><span class="sxs-lookup"><span data-stu-id="29ba5-131">WebHttpBinding</span></span>

<span data-ttu-id="29ba5-132">WebHttpBinding（也称为 WCF REST），具有`WebGet`和`WebInvoke`属性，使您能够开发 RESTful API，在不太常见时可以讲 JSON。</span><span class="sxs-lookup"><span data-stu-id="29ba5-132">WebHttpBinding (also known as WCF REST), with the `WebGet` and `WebInvoke` attributes, enabled you to develop RESTful APIs that could speak JSON at a time when this was less common.</span></span> <span data-ttu-id="29ba5-133">如果使用 WCF REST 构建了 RESTful API，请考虑将其迁移到常规ASP.NET核心 MVC Web API 应用程序。</span><span class="sxs-lookup"><span data-stu-id="29ba5-133">If you have a RESTful API built with WCF REST, consider migrating it to a regular ASP.NET Core MVC Web API application.</span></span> <span data-ttu-id="29ba5-134">此迁移将提供与转换为 gRPC 相同的功能。</span><span class="sxs-lookup"><span data-stu-id="29ba5-134">This migration would provide the same functionality as a conversion to gRPC.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="29ba5-135">[上一个](wcf-endpoints-grpc-methods.md)
>[下一个](rpc-types.md)</span><span class="sxs-lookup"><span data-stu-id="29ba5-135">[Previous](wcf-endpoints-grpc-methods.md)
[Next](rpc-types.md)</span></span>
